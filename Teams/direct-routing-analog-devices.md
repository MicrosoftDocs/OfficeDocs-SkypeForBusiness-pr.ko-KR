---
title: 직접 라우팅-아날로그 장치 연결
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
description: 이 문서에서는 Microsoft 전화 시스템 다이렉트 라우팅으로 아날로그 장치를 사용 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: c1720a7f702babbf677ab8f1de75014c629e6d76
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192171"
---
# <a name="how-to-use-analog-devices-with-phone-system-direct-routing"></a>전화 시스템 다이렉트 라우팅과 함께 아날로그 장치를 사용 하는 방법

이 문서에서는 전화 시스템 다이렉트 라우팅과 함께 아날로그 장치를 사용 하는 방법을 설명 합니다. 아날로그 장치를 직접 라우팅에 연결 하려면, 아날로그 전화 통신 어댑터 (ATA)를 사용 해야 하며,이 어댑터는 인증 된 세션 경계 컨트롤러 (SBC) 공급 업체에서 지원 해야 합니다. 

사용자가 아날로그 장치에서 전화를 걸 때 신호 및 미디어는 아날로그 통신 어댑터 (ATA)를 통해 SBC로 흐릅니다.  SBC는 내부 라우팅 테이블을 기반으로 Microsoft 팀 끝점 또는 PSTN (공개 통신 네트워크)로 전화를 보냅니다.  장치에서 전화를 걸 때 사용 하는 경로는 디바이스에 대해 생성 된 라우팅 정책에 따라 달라 집니다.

다음 다이어그램에서는 + 1425 4XX XX XX와 + 1425 5XX XX XX 사이의 번호로 전화를 걸고 받는 모든 팀이 빨간색 경로 (점선)를 사용 해야 하며 + 1425 4XX XX XX과 (와)를 제외한 다른 숫자와의 모든 PSTN 통화 및 기타 번호를 표시 하도록 직접 라우팅이 구성 되었습니다.  숫자 범위 + 1425 5XX XX XX는 파란색 경로 (실선)를 사용 해야 합니다. 

![직접 라우팅 구성을 보여 주는 다이어그램](media/direct-routing-analog-device.png)

## <a name="example--how-to-configure-the-use-of-analog-devices-with-direct-routing"></a>예: 직접 라우팅을 사용 하 여 아날로그 장치 사용을 구성 하는 방법

직접 라우팅이 있는 아날로그 장치를 사용 하도록 구성 하려면 아날로그 전화 통신 어댑터를 SBC에 연결 하 고 직접 라우팅과 함께 사용할 수 있도록 SBC를 구성 해야 합니다. 

이 예제에서는 다음 단계를 안내 합니다.

1. 직접 라우팅에 SBC 연결
2. PSTN 사용 만들기
3. 음성 경로를 만들어 PSTN 사용에 연결
4. PSTN 사용에 음성 경로 할당
5. 온라인 사용자 설정
6. 사용자에 게 음성 경로 정책 할당
7. 아날로그 장치에 음성 경로 정책 지정

ATA를 SBC에 연결 하 고 SBC를 구성 하는 방법에 대 한 자세한 내용은 SBC 제조업체 구성 가이드를 참조 하세요.
- [오디오 코드 구성 설명서](https://www.audiocodes.com/media/14278/connecting-audiocodes-sbc-with-analog-device-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf)

## <a name="step-1--connect-the-sbc-to-direct-routing"></a>1 단계.  직접 라우팅에 SBC 연결

다음 명령은 아래와 같이 SBC 연결을 구성 합니다.

- FQDN sbc.contoso.com
- 신호 포트 5068
- 미디어 우회 모드
- SBC로 착신 전환 된 통화 기록 정보
- P-어설션된-통화와 함께 Id (PAI) 헤더가 전달 됨 

```
PS C:\> New-CsOnlinePSTNGateway -FQDN sbc.contoso.com -SIPSignalingPort 5068 -ForwardCallHistory $true -ForwardPAI $true -MediaBypass $true -Enabled $true 
```

## <a name="step-2--create-the-pstn-usage"></a>2 단계: PSTN 사용 만들기 

다음 명령은 빈 PSTN 사용량을 만듭니다. 온라인 PSTN 사용량은 통화 승인에 사용 되는 문자열 값입니다. 온라인 PSTN 사용은 온라인 음성 정책을 경로에 연결 합니다. 이 예제에서는 사용 가능한 PSTN 사용량의 현재 목록에 "Interop" 문자열을 추가 합니다. 

```
PS C:\> Set-CsOnlinePstnUsage -Identity global -Usage @{add="Interop"} 
```

## <a name="step-3--create-a-voice-route-and-associate-it-with-the-pstn-usage"></a>3 단계: 음성 경로를 만들어 PSTN 사용에 연결 합니다.

이 명령은 숫자 범위 + 1425 XXX XX XX에 대 한 id "아날로그-interop"를 사용 하 여 새 온라인 음성 경로를 만듭니다.  음성 경로는 온라인 게이트웨이 sbc.contoso.com 목록에 적용 되며, 경로를 온라인 PSTN 사용 "Interop"와 연결 합니다. 음성 경로에는 특정 음성 경로를 통해 라우팅되는 전화 번호를 식별 하는 정규식이 포함 됩니다.

```
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(425)(\d{7}])$" -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "
```

## <a name="step-4-assign-the-voice-route-to-the-pstn-usage"></a>4 단계: PSTN 사용에 대 한 음성 경로 할당:

이 명령은 Id "AnalogInteropPolicy"와 함께 새 사용자 단위 음성 라우팅 정책을 만듭니다. 이 정책에는 단일 온라인 PSTN 사용 ("Interop")이 할당 됩니다.

```
PS C:\> New-CsOnlineVoiceRoutingPolicy -Identity "AnalogInteropPolicy" -Name "AnalogInteropPolicy" -OnlinePstnUsages "Interop"
```

## <a name="step-5-enable-the-online-user"></a>5 단계: 온라인 사용자 설정

이 명령은 Id exampleuser@contoso.com를 사용 하 여 사용자 계정을 수정 합니다. 이 경우에는 음성 메일을 사용 하도록 설정 된 VoIP의 Microsoft 구현 인 Enterprise Voice를 사용 하도록 계정이 수정 되 고이 사용자에 게 번호 + 142억5500만를 할당 합니다.  이 명령은 회사 테 넌 트에서 각 팀 사용자 (ATA 장치 사용자 제외)에 대해 실행 되어야 합니다.

```
PS C:\> Set-CsUser -Identity "exampleuser@contoso.com" -EnterpriseVoiceEnabled $True -HostedVoiceMail $True -OnPremLineUri "tel:+14255000000"
```

## <a name="step-6-assign-the-voice-route-policy-to-a-user"></a>6 단계: 사용자에 게 음성 경로 정책 할당

이 명령은 사용자 단위 온라인 음성 라우팅 정책 AnalogInteropPolicy를 id exampleuser@contoso.com를 사용 하 여 사용자에 게 할당 합니다.  이 명령은 회사 테 넌 트에서 각 팀 사용자 (ATA 장치 사용자 제외)에 대해 실행 되어야 합니다.

```
PS C:\> Grant-CsOnlineVoiceRoutingPolicy -Identity "exampleuser@contoso.com" -PolicyName "AnalogInteropPolicy" 
```

## <a name="step-7--assign-a-voice-route-to-an-analog-device"></a>7 단계: 아날로그 장치에 음성 경로 할당

이 명령은 온라인 게이트웨이 sbc.contoso.com 목록에 적용할 수 있는 숫자 범위 + 1425 4XX XX XX에 대 한 id "아날로그-interop"를 사용 하 여 온라인 음성 경로를 만들고 온라인 PSTN 사용 "Interop"와 연결 합니다.  적절 한 전화 번호 패턴으로 각 아날로그 장치에 대해이 명령을 실행 해야 합니다. 또는 이전 단계 중 하나에서 온라인 음성 경로를 구성 하는 동안 아날로그 장치에 대 한 적절 한 번호 패턴을 사용할 수 있습니다.

```
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(4254)(\d{6}])$"  -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="considerations"></a>고려 사항

- 다른 언급이 없는 한 아날로그 장치는 전화를 걸기 위해 DTMF 번호를 보낼 수 있는 장치입니다. 예를 들어 아날로그 전화, 팩스 시스템, 간접비 호출기 등이 있습니다.
- ATA에 연결 된 아날로그 전화기는 팀에서 검색할 수 없습니다. 팀 사용자는 장치에 연결 된 전화 번호를 수동으로 입력 하 여 해당 장치를 호출 해야 합니다.  
 

## <a name="see-also"></a>참고 항목

[직접 라우팅 계획](direct-routing-plan.md)

[직접 라우팅 구성](direct-routing-configure.md)
