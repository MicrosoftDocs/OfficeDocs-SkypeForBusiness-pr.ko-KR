---
title: 오디오 회의를 위한 네트워크 회의
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: oscarr
ms.topic: conceptual
ms.tgt.pltfrm: cloud
audience: admin
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
- m365initiative-meetings
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 다음은 오디오 회의를 위한 네트워크의 오픈 미리 보기 기능에 대해 설명하고 있습니다.
ms.openlocfilehash: 1ae61034ef083c89e14c67cef0effa1c105de758
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031864"
---
# <a name="open-preview-of-on-network-conferencing-for-audio-conferencing"></a>오디오 회의용 네트워크 회의 미리 보기 열기

모든 고객이 네트워크 회의의 미리 보기를 열 수 있습니다. 조직에서는 네트워크 회의를 통해 직접 라우팅을 통해 인바운드 및 아웃바운드 오디오 회의 호출을 Microsoft 전화 접속 번호로 보낼 수 있습니다. 이 기능은 오디오 회의 지원을 타사 전화 접속 번호로 확장하기 위한 것이 아니라 타사 전화 접속 전화 번호를 통해 오디오 회의 서비스에 인바운드 호출을 라우팅하는 데 사용되는 경우 네트워크 회의가 지원되지 않습니다.

이 문서에서는 조직에 대한 네트워크 회의를 사용하도록 설정하는 데 필요한 필수 구성 항목 및 구성 단계를 설명하고 있습니다.

> [!IMPORTANT]
> 인도의 전화 통신 장비와 함께 네트워크 회의를 배포하지 말아야 합니다.
  
## <a name="prerequisites"></a>필수 구성 요소

네트워크 회의를 구성하기 전에 조직이 다음 요건을 충족하는지 확인합니다. 

- 오디오 회의를 사용하도록 설정하거나 사용하도록 설정한 조직의 모든 사용자가 모든 모임에 Teams를 사용하고 있는지 확인합니다. 네트워크 회의를 통한 인바운드 및 아웃바운드 오디오 회의 통화 라우팅은 Teams 모임에서만 지원됩니다.

- 네트워크 회의를 사용할 모든 사용자에게 오디오 회의 라이선스를 할당합니다.

- 오디오 회의 서비스를 설치합니다. 자세한 내용은 Microsoft Teams에 대한 오디오 회의 [설정을 참조하세요.](set-up-audio-conferencing-in-teams.md)

- 직접 라우팅을 위해 SBC(세션 테두리 컨트롤러)를 설정합니다. 자세한 내용은 직접 라우팅 계획 및 [직접](direct-routing-plan.md) 라우팅 [구성을 참조하세요.](direct-routing-configure.md) 

  오디오 회의 목적으로만 직접 라우팅을 설정하는 경우 네트워크 회의에 대해 "1단계: SBC 연결"만 완료하면 됩니다.
  
## <a name="enable-the-routing-of-dial-in-calls-to-microsoft-audio-conferencing-through-direct-routing"></a>직접 라우팅을 통해 Microsoft 오디오 회의에 대한 전화 접속 통화 라우팅 사용 

직접 라우팅을 통해 프레미스 사용자가 만든 전화 접속 통화를 오디오 회의 서비스로 라우팅하려면 SBC 및 개인 분기 교환(PBX)에 대한 적절한 라우팅 규칙을 구성해야 합니다.

직접 라우팅 트렁크를 통해 조직의 전화 회의 브리지의 모든 서비스 번호로 통화를 라우팅하도록 사이트의 전화 통신 장비를 구성해야 합니다.

Teams 관리 센터의 모임 **->** 회의 브리지에서 또는 비즈니스용 Skype Online PowerShell cmdlet Get-CsOnlineDialInConferencingBridge를 사용하여 서비스 번호를 찾을 수 있습니다. 자세한 내용은 Microsoft Teams의 오디오 회의 번호 목록을 [참조하세요.](see-a-list-of-audio-conferencing-numbers-in-teams.md)

> [!NOTE]
> 이 기능은 분당 유료 오디오 회의 라이선스가 있는 사용자에게는 제공되지 않습니다.

## <a name="enable-the-routing-of-teams-meeting-dial-out-calls-through-direct-routing"></a>직접 라우팅을 통해 Teams 모임 전화 걸기 라우팅 사용

Teams 모임 전화 걸기 통화는 조직의 모임 내에서 PSTN 번호로 시작하며, 통화 시 통화 및 새 참가자를 모임에 참가할 수 있습니다. 

네트워크 사용자에게 직접 라우팅을 통해 Teams 모임 전화 접속 라우팅을 사용하도록 설정하려면 "OnlineAudioConferencingRoutingPolicy"라는 오디오 회의 라우팅 정책을 만들고 할당해야 합니다. 

OnlineAudioConferencingRoutingPolicy 정책은 직접 라우팅을 통한 1:1 PSTN 호출에 대한 CsOnlineVoiceRoutingPolicy와 동일합니다. OnlineAudioConferencingRoutingPolicy 정책은 다음 cmdlet을 사용하여 관리할 수 있습니다.

-   New-CsOnlineAudioConferencingRoutingPolicy
- Set-CsOnlineAudioConferencingRoutingPolicy
- Get-CsOnlineAudioConferencingRoutingPolicy
- Grant-CsOnlineAudioConferencingRoutingPolicy
- Remove-CsOnlineAudioConferencingRoutingPolicy

직접 라우팅에 대한 라우팅에 대한 자세한 내용은 직접 라우팅에 대한 음성 라우팅 구성을 [참조하세요.](direct-routing-voice-routing.md)


직접 라우팅을 통해 모임 전화 접속 통화의 라우팅을 사용하도록 설정하려면 다음을 해야 합니다. 

- 오디오 회의 라우팅 정책 구성
- 조직의 전화 통신 장비에서 라우팅 구성
- (선택 사항) 다이얼 플랜 구성

Teams 모임의 전화 걸기 통화는 전화 회의 브리지의 기본 서비스 번호에서 온 것입니다. 오디오 회의 브리지의 기본 서비스 번호에 대한 자세한 내용은 오디오 회의 브리지의 전화 번호 변경을 [참조하세요.](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)

### <a name="configure-audio-conferencing-routing-policies"></a>오디오 회의 라우팅 정책 구성

오디오 회의 라우팅 정책 OnlineAudioConferencingRoutingPolicy는 직접 라우팅 트렁크로 라우팅되는 모임 전화 걸기 통화를 결정합니다. CsOnlineVoiceRoutingPolicy 정책에 익숙한 경우 이 정책은 매우 유사한 방식으로 작동합니다.

오디오 회의 라우팅 정책을 설정하려면 다음 단계가 필요합니다.
1.  PSTN 사용량 만들기
2.  음성 경로 구성
3.  오디오 회의 음성 라우팅 정책 만들기
4.  사용자에게 정책 할당


#### <a name="create-pstn-usages"></a>PSTN 사용량 만들기

PSTN 사용량은 음성 경로의 컬렉션입니다. 특정 이끌이의 모임에서 전화 걸기 통화가 시작될 때 음성 경로는 사용자의 음성 라우팅 정책을 통해 사용자에게 연결된 PSTN 사용량에 따라 통화의 라우팅 경로를 결정하는 데 사용됩니다.

"Set-CsOnlinePstnUsage" cmdlet을 사용하여 PSTN 사용량을 만들 수 있습니다. 예를 들어:

```powershell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

#### <a name="configure-voice-routes"></a>음성 경로 구성

음성 경로는 Teams 모임에서 전화가 걸린 전화 번호를 기반으로 통화를 라우팅하는 데 사용할 PSTN 게이트웨이를 결정합니다. 음성 경로는 Teams 모임에서 전화가 걸린 전화 번호를 regex 패턴과 일치하여 특정 통화를 라우팅하는 데 사용할 PSTN 게이트웨이를 결정합니다. 음성 경로를 만들 때 경로는 하나 이상의 PSTN 사용량에 연결되어야 합니다.

"New-CsOnlineVoiceRoute" cmdlet을 사용하여 음성 경로를 만들고 음성 경로와 연결될 regex 및 게이트웨이를 정의할 수 있습니다. 예를 들어:

```powershell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

#### <a name="create-audio-conferencing-voice-routing-policies"></a>오디오 회의 음성 라우팅 정책 만들기

오디오 회의 음성 라우팅 정책은 모임 전화 걸기 통화의 대상 전화 번호를 기반으로 이끌이의 모임에서 시작된 통화를 라우팅하는 데 사용할 수 있는 가능한 경로를 결정합니다. 오디오 회의 음성 라우팅 정책은 하나 이상의 PSTN 사용량에 연결됩니다. 이 경우 정책과 연결된 이끌이의 모임 전화 걸기 통화에 사용할 수 있는 경로가 결정됩니다.

"New- CsOnlineAudioConferencingRoutingPolicy" cmdlet을 사용하여 오디오 회의 음성 라우팅 정책을 만들 수 있습니다. 예를 들어:

```powershell
New-CsOnlineAudioConferencingRoutingPolicy "Policy 1" -OnlinePstnUsages "US and Canada"
```

정책이 사용자에게 할당된 후 사용자의 모임 중 하나에서 모임 전화 걸기 통화가 시작될 때 사용자의 음성 라우팅 정책을 통해 이끌이와 연결된 PSTN 사용의 음성 경로가 평가됩니다. 모임 전화 걸기 통화 대상이 이끌이와 연결된 음성 경로 중 하나의 regex와 일치하는 경우 모임 전화 걸기 통화는 음성 경로에 정의된 PSTN 게이트웨이로 라우팅됩니다. 모임 전화 접속 통화 대상이 이끌이와 연결된 음성 경로와 일치하지 않는 경우 Microsoft에서 모임 전화 걸기 통화를 라우팅합니다.

#### <a name="assign-a-policy-to-your-users"></a>사용자에게 정책 할당

오디오 회의 라우팅 정책이 정의되고 나면 사용자에게 할당할 수 있습니다. 정책이 할당된 후 해당 라우팅 경로를 결정하기 위해 모임 전화 걸기 통화를 평가합니다. 오디오 회의 라우팅 정책은 모임 전화 접속 통화를 시작하는 모임의 사용자와는 독립적으로 모임 이끌이에 따라 항상 평가됩니다.

"Grant-CsOnlineAudioConferencingRoutingPolicy" cmdlet을 사용하여 사용자에게 오디오 회의 음성 라우팅 정책을 할당할 수 있습니다. 예를 들면 다음과 같습니다.

```powershell
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity "<User Identity>" -PolicyName "Policy 1”
```


### <a name="configure-routing-on-the-telephony-equipment-of-your-organization"></a>조직의 전화 통신 장비에 라우팅 구성

조직의 전화 통신 장비에서 직접 라우팅을 통해 라우팅된 모임 전화 걸기 통화가 의도한 네트워크 대상으로 라우팅되도록 해야 합니다.


### <a name="optional-configure-a-dial-plan"></a>(선택 사항) 다이얼 플랜 구성

다이얼 플랜은 통화 권한 부여 및 통화 라우팅을 위해 개별 사용자의 전화 번호를 대체 형식(일반적으로 E.164)으로 변환하는 정규화 규칙 집합입니다.

기본적으로 Teams 사용자는 E.164 형식(예: + )으로 PSTN 번호로 전화를 걸 수 \<country code\> \<number\> 있습니다. 그러나 전화 요금제는 사용자가 다른 형식(예: 4자리 내선 번호)으로 전화 번호를 걸 수 있도록 하는 데 사용할 수 있습니다.

네트워크 회의를 통해 확장 기반 전화 걸기를 사용하도록 설정하려면 내선 번호 패턴과 조직의 전화 번호 범위에 일치하도록 다이얼 플랜을 설정할 수 있습니다. 다이얼 플랜을 설정하는 경우 전화 요금제 만들기 [및 관리를 참조합니다.](create-and-manage-dial-plans.md)


## <a name="known-issues-in-open-preview"></a>오픈 미리 보기의 알려진 문제

다음은 현재 네트워크 회의의 오픈 미리 보기 릴리스에 있는 알려진 문제 목록입니다. Microsoft는 이러한 문제를 해결하기 위해 작업 중입니다.

| 문제 | 해결 해결 |
| :--- | :--- |
| 네트워크 회의를 통해 라우팅되는 익명/숨겨진 발신자 번호가 있는 전화 접속 통화는 모임에 연결할 수 없습니다. | 가능한 경우 PBX 또는 SBC에서 구성을 설정하여 항상 네트워크 회의를 통해 라우팅된 호출에 대한 호출자 ID를 전송합니다.|
| 경우에 따라 사용자가 서비스에 전화를 걸 때 재생된 환영 메시지("오디오 회의 서비스 시작...")가 잘리며 사용자가 "시작" 단어를 듣지 못합니다.| 현재 이 문제의 해결 해결은 없습니다. |




## <a name="related-topics"></a>관련 항목


