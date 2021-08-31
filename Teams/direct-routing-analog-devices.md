---
title: 직접 라우팅 - 아날로그 디바이스 연결
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: conceptual
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 시스템 직접 라우팅과 함께 아날로그 디바이스를 사용하는 Microsoft 전화 이 문서를 읽어보아야 합니다.
ms.openlocfilehash: 083c5dd5b577e319a9e5308a4ec3630614254628
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58733497"
---
# <a name="how-to-use-analog-devices-with-phone-system-direct-routing"></a>직접 라우팅과 함께 아날로그 전화 시스템 방법

이 문서에서는 직접 라우팅과 함께 아날로그 전화 시스템 방법을 설명합니다. 직접 라우팅에 아날로그 디바이스를 연결하려면 ATA(Analog Telephony 어댑터)를 사용해야 합니다. 이 어댑터는 인증된 SBC(세션 경계 컨트롤러) 공급업체에서 지원해야 합니다. 

사용자가 아날로그 장치에서 전화를 걸면 ATA(Analog Telephony 어댑터)를 통해 SBC로 신호 및 미디어가 흐르게 됩니다.  SBC는 내부 라우팅 테이블을 기반으로 Microsoft Teams PSTN(공용 전환 전화 네트워크)으로 호출을 전송합니다.  디바이스가 전화를 걸 때 걸리는 경로는 디바이스에 대해 만든 라우팅 정책에 따라 달라 니다.

다음 다이어그램에서 직접 라우팅은 +1425 4XX XX XX 및 +1425 5XX XX XX 사이의 숫자를 Teams 호출할 때 빨간색 경로(점선)를 취해야 하도록 구성됩니다. 줄) 및 번호 범위 +1425 5XX XX XX를 제외한 모든 다른 번호 사이의 숫자와 1425 4XX XX XX 사이의 모든 PSTN 호출은 파란색 경로(단선)를 취해야 합니다. 

> [!div class="mx-imgBorder"]
> ![직접 라우팅 구성을 보여주는 다이어그램입니다.](media/direct-routing-analog-device.png)

## <a name="example--how-to-configure-the-use-of-analog-devices-with-direct-routing"></a>예: 직접 라우팅을 사용하여 아날로그 디바이스 사용을 구성하는 방법

직접 라우팅을 사용하여 아날로그 디바이스 사용을 구성하려면 아날로그 전화 어댑터를 SBC에 연결하고 직접 라우팅을 사용하도록 SBC를 구성해야 합니다. 

이 예제에서는 다음 단계를 진행합니다.

1. 커넥트 라우팅에 SBC를 연결합니다.
2. PSTN 사용량을 생성합니다.
3. 음성 경로를 만들고 PSTN 사용량과 연결합니다.
4. 음성 경로를 PSTN 사용량에 할당합니다.
5. 온라인 사용자를 사용하도록 설정합니다.
6. 사용자에게 음성 경로 정책을 할당합니다.
7. 아날로그 디바이스에 대한 음성 경로를 생성합니다.

ATA를 SBC에 연결하고 SBC를 구성하는 방법에 대한 자세한 내용은 SBC 제조업체 구성 가이드를 참조하세요.

- [AudioCodes 구성 설명서](https://www.audiocodes.com/media/14278/connecting-audiocodes-sbc-with-analog-device-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf)

- [리본 구성 설명서](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)
- [Oracle 구성 설명서](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams)

## <a name="step-1--connect-the-sbc-to-direct-routing"></a>1단계.  커넥트 SBC에서 직접 라우팅으로 연결

다음 명령은 다음과 같이 SBC 연결을 구성합니다.

- FQDN sbc.contoso.com
- 신호 포트 5068
- 미디어 우회 모드
- SBC로 전달된 통화 기록 정보
- 호출과 함께 전달된 PAI(PAI) 헤더 

```powershell
PS C:\> New-CsOnlinePSTNGateway -FQDN sbc.contoso.com -SIPSignalingPort 5068 -ForwardCallHistory $true -ForwardPAI $true -MediaBypass $true -Enabled $true 
```

## <a name="step-2--create-the-pstn-usage"></a>2단계: PSTN 사용량 만들기 

다음 명령은 빈 PSTN 사용량을 만듭니다. 온라인 PSTN 사용량은 호출 권한 부여에 사용되는 문자열 값입니다. 온라인 PSTN 사용량은 온라인 음성 정책을 경로에 연결합니다. 이 예제에서는 사용 가능한 PSTN 사용 현황 목록에 "Interop" 문자열을 추가합니다. 

```powershell
PS C:\> Set-CsOnlinePstnUsage -Identity global -Usage @{add="Interop"} 
```

## <a name="step-3--create-a-voice-route-and-associate-it-with-the-pstn-usage"></a>3단계: 음성 경로를 만들고 PSTN 사용량과 연결합니다.

이 명령은 숫자 범위 +1425 XXX XX에 대한 ID "analog-interop"을 사용하여 새 온라인 음성 경로를 만듭니다.  음성 경로는 온라인 게이트웨이 목록에 적용될 수 sbc.contoso.com 온라인 PSTN 사용 "Interop"과 연결됩니다. 음성 경로에는 특정 음성 경로를 통해 라우팅될 전화 번호를 식별하는 정규식이 포함됩니다.

```powershell
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(425)(\d{7})$" -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="step-4-assign-the-voice-route-to-the-pstn-usage"></a>4단계: PSTN 사용량에 음성 경로를 할당합니다.

이 명령은 ID "AnalogInteropPolicy"를 사용하여 사용자당 새 온라인 음성 라우팅 정책을 만듭니다. 이 정책은 단일 온라인 PSTN 사용량인 "Interop"을 할당합니다.

```powershell
PS C:\> New-CsOnlineVoiceRoutingPolicy -Identity "AnalogInteropPolicy" -Name "AnalogInteropPolicy" -OnlinePstnUsages "Interop"
```

## <a name="step-5-enable-the-online-user"></a>5단계: 온라인 사용자 사용

이 명령은 ID를 사용하여 사용자 계정을 exampleuser@contoso.com. 이 경우 계정은 VoIP의 Microsoft 구현인 VoIP를 사용하도록 Enterprise Voice 음성 메일을 사용하도록 수정하고 이 사용자에게 번호 +14255000000000을 할당합니다.  이 명령은 회사 테넌트의 Teams 사용자(ATA 디바이스 사용자 제외)에 대해 실행해야 합니다.

```powershell
PS C:\> Set-CsUser -Identity "exampleuser@contoso.com" -EnterpriseVoiceEnabled $True -HostedVoiceMail $True -OnPremLineUri "tel:+14255000000"
```

## <a name="step-6-assign-the-voice-route-policy-to-a-user"></a>6단계: 사용자에게 음성 경로 정책 할당

이 명령은 사용자당 온라인 음성 라우팅 정책 AnalogInteropPolicy를 ID를 사용하여 사용자에게 할당 exampleuser@contoso.com.  이 명령은 회사 테넌트의 Teams 사용자(ATA 디바이스 사용자 제외)에 대해 실행해야 합니다.

```powershell
PS C:\> Grant-CsOnlineVoiceRoutingPolicy -Identity "exampleuser@contoso.com" -PolicyName "AnalogInteropPolicy" 
```

## <a name="step-7--create-a-voice-route-for-an-analog-device"></a>7단계: 아날로그 디바이스에 대한 음성 경로 만들기

이 명령은 온라인 게이트웨이 목록에 적용할 수 있는 번호 범위 +1425 4XX XX XX에 대한 ID "analog-interop"을 사용하여 온라인 음성 경로를 만들고 sbc.contoso.com PSTN 사용 "Interop"과 연결합니다.  이 명령은 적절한 전화 번호 패턴을 사용하여 각 아날로그 디바이스에 대해 실행해야 합니다. 또는 이전 단계 중 하나에서 온라인 음성 경로를 구성하는 동안 아날로그 디바이스에 대한 적절한 숫자 패턴을 사용할 수 있습니다.

```powershell
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(4254)(\d{6})$"  -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="considerations"></a>고려 사항

- 그렇지 않으면 아날로그 디바이스는 전화를 걸기 위해 DTMF 숫자를 보낼 수 있는 모든 디바이스입니다. 예를 들어 아날로그 전화, 팩스 머신 및 오버헤드 페이저를 예로 들 수 있습니다.

- ATA에 연결된 아날로그 휴대폰은 ATA에서 검색할 수 Teams. Teams 디바이스를 호출하려면 디바이스와 연결된 전화 번호를 수동으로 입력해야 합니다.  
 

## <a name="see-also"></a>참고 항목

[직접 라우팅 계획](direct-routing-plan.md)

[직접 라우팅 구성](direct-routing-configure.md)
