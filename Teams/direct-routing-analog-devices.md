---
title: 직접 라우팅 - 아날로그 디바이스 연결
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Microsoft Phone System Direct Routing에서 아날로그 디바이스를 사용하는 방법을 알아보는 이 문서를 읽어 읽습니다.
ms.openlocfilehash: 855bf0dd21659c43037b6171f523983d67c4e755
ms.sourcegitcommit: 1889ca28b9cb952b13c84efa3588957a327f9702
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841489"
---
# <a name="how-to-use-analog-devices-with-phone-system-direct-routing"></a>전화 시스템 직접 라우팅과 함께 아날로그 디바이스를 사용하는 방법

이 문서에서는 전화 시스템 직접 라우팅과 함께 아날로그 디바이스를 사용하는 방법을 설명하고 있습니다. 아날로그 디바이스를 직접 라우팅에 연결하려면 ATA(아날로그 전화 통신 어댑터)를 사용해야 합니다. 이 어댑터는 SBC(인증된 세션 테두리 컨트롤러) 공급업체에서 지원해야 합니다. 

사용자가 아날로그 디바이스에서 전화를 걸 때 신호 및 미디어는 ATA(Analog Telephony Adapter)를 통해 SBC로 전달됩니다.  SBC는 내부 라우팅 테이블에 따라 Microsoft Teams 엔드포인트 또는 PSTN(공용 전환 전화 네트워크)으로 통화를 전송합니다.  디바이스가 호출을 할 때 사용하는 경로는 디바이스에 대해 만든 라우팅 정책에 따라 달라 졌습니다.

다음 다이어그램에서 직접 라우팅은 Teams에서 +1425 4XX XX XX와 +1425 5XX 사이의 번호에서 호출하는 모든 팀이 빨간색 경로(점선)를 취해야 하도록 구성됩니다. 그리고 +1425 4XX XX XX와 숫자 범위 +1425 5XX XX XX를 제외한 다른 번호 사이의 모든 PSTN 통화는 파란색 경로(실선)를 취해야 합니다. 

> [!div class="mx-imgBorder"]
> ![직접 라우팅 구성을 보여주는 다이어그램](media/direct-routing-analog-device.png)

## <a name="example--how-to-configure-the-use-of-analog-devices-with-direct-routing"></a>예: 직접 라우팅을 사용하여 아날로그 디바이스 사용을 구성하는 방법

직접 라우팅을 사용하여 아날로그 디바이스 사용을 구성하려면 아날로그 Telephony 어댑터를 SBC에 연결하고 직접 라우팅과 작동하도록 SBC를 구성해야 합니다. 

이 예제에서는 다음 단계를 단계로 진행합니다.

1. SBC를 직접 라우팅에 연결합니다.
2. PSTN 사용량을 생성합니다.
3. 음성 경로를 만들고 PSTN 사용량과 연결합니다.
4. 음성 경로를 PSTN 사용량에 할당합니다.
5. 온라인 사용자를 사용하도록 설정합니다.
6. 사용자에게 음성 경로 정책을 할당합니다.
7. 아날로그 디바이스에 대한 음성 경로를 만들 수 있습니다.

ATA를 SBC에 연결하고 SBC를 구성하는 방법에 대한 자세한 내용은 SBC 제조업체 구성 가이드를 참조하세요.

- [AudioCodes 구성 설명서](https://www.audiocodes.com/media/14278/connecting-audiocodes-sbc-with-analog-device-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf)

- [리본 메뉴 구성 설명서](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)
- [Oracle 구성 설명서](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams)

## <a name="step-1--connect-the-sbc-to-direct-routing"></a>1단계.  직접 라우팅에 SBC 연결

다음 명령은 다음과 같이 SBC 연결을 구성합니다.

- FQDN sbc.contoso.com
- 신호 포트 5068
- 미디어 우회 모드
- SBC로 전달된 통화 기록 정보
- 호출과 함께 전달된 PAI(P-Asserted-Identity) 헤더 

```powershell
PS C:\> New-CsOnlinePSTNGateway -FQDN sbc.contoso.com -SIPSignalingPort 5068 -ForwardCallHistory $true -ForwardPAI $true -MediaBypass $true -Enabled $true 
```

## <a name="step-2--create-the-pstn-usage"></a>2단계: PSTN 사용량 만들기 

다음 명령은 빈 PSTN 사용량을 만듭니다. 온라인 PSTN 사용량은 호출 권한 부여에 사용되는 문자열 값입니다. 온라인 PSTN 사용은 온라인 음성 정책을 경로에 연결합니다. 이 예제에서는 사용 가능한 PSTN 사용 현황 목록에 "Interop" 문자열을 추가합니다. 

```powershell
PS C:\> Set-CsOnlinePstnUsage -Identity global -Usage @{add="Interop"} 
```

## <a name="step-3--create-a-voice-route-and-associate-it-with-the-pstn-usage"></a>3단계: 음성 경로를 만들고 PSTN 사용량과 연결합니다.

이 명령은 숫자 범위 +1425 XXX XX XX에 대한 ID "analog-interop"을 사용하여 새 온라인 음성 경로를 만듭니다.  음성 경로는 온라인 게이트웨이 목록에 적용될 수 sbc.contoso.com 온라인 PSTN 사용 "Interop"과 연결됩니다. 음성 경로에는 특정 음성 경로를 통해 라우팅될 전화 번호를 식별하는 정규식이 포함됩니다.

```powershell
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(425)(\d{7}])$" -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="step-4-assign-the-voice-route-to-the-pstn-usage"></a>4단계: PSTN 사용에 음성 경로 할당:

이 명령은 ID "AnalogInteropPolicy"를 사용하여 새 온라인 사용자당 음성 라우팅 정책을 만듭니다. 이 정책에는 단일 온라인 PSTN 사용: "Interop"이 할당됩니다.

```powershell
PS C:\> New-CsOnlineVoiceRoutingPolicy -Identity "AnalogInteropPolicy" -Name "AnalogInteropPolicy" -OnlinePstnUsages "Interop"
```

## <a name="step-5-enable-the-online-user"></a>5단계: 온라인 사용자 사용

이 명령은 ID 계정으로 사용자 계정을 exampleuser@contoso.com. 이 경우 계정은 음성 메일을 사용하도록 Enterprise Voice Microsoft 구현인 VoIP를 사용하도록 수정하고 이 사용자에게 +14255000000 번호를 할당합니다.  이 명령은 회사 테넌트의 각 Teams 사용자(ATA 장치 사용자 제외)에 대해 실행해야 합니다.

```powershell
PS C:\> Set-CsUser -Identity "exampleuser@contoso.com" -EnterpriseVoiceEnabled $True -HostedVoiceMail $True -OnPremLineUri "tel:+14255000000"
```

## <a name="step-6-assign-the-voice-route-policy-to-a-user"></a>6단계: 사용자에게 음성 경로 정책 할당

이 명령은 ID가 할당된 사용자당 온라인 음성 라우팅 정책 AnalogInteropPolicy를 사용자에게 exampleuser@contoso.com.  이 명령은 회사 테넌트의 각 Teams 사용자(ATA 장치 사용자 제외)에 대해 실행해야 합니다.

```powershell
PS C:\> Grant-CsOnlineVoiceRoutingPolicy -Identity "exampleuser@contoso.com" -PolicyName "AnalogInteropPolicy" 
```

## <a name="step-7--create-a-voice-route-for-an-analog-device"></a>7단계: 아날로그 디바이스에 대한 음성 경로 만들기

이 명령은 번호 범위 +1425 4XX XX XX에 ID가 "analog-interop"인 온라인 음성 경로를 만들고 sbc.contoso.com 온라인 PSTN 사용 "Interop"과 연결합니다.  이 명령은 적절한 전화 번호 패턴을 사용하여 각 아날로그 디바이스에 대해 실행해야 합니다. 또는 이전 단계 중 하나에서 온라인 음성 경로를 구성하는 동안 아날로그 디바이스에 적절한 숫자 패턴을 사용할 수 있습니다.

```powershell
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(4254)(\d{6}])$"  -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="considerations"></a>고려 사항

- 달리 기록하지 않는 한 아날로그 디바이스는 DTMF 숫자를 전송하여 전화를 걸 수 있는 디바이스입니다. 예를 들어 아날로그 전화기, 팩스 머신 및 오버헤드 페이저입니다.

- ATA에 연결된 아날로그 휴대폰은 Teams에서 검색할 수 없습니다. Teams 사용자는 디바이스와 연결된 전화 번호를 수동으로 입력하여 해당 디바이스를 호출해야 합니다.  
 

## <a name="see-also"></a>참고 항목

[직접 라우팅 계획](direct-routing-plan.md)

[직접 라우팅 구성](direct-routing-configure.md)
