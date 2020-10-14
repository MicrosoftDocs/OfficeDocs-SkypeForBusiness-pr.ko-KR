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
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 다음은 오디오 회의를 위한 네트워크의 열기 미리 보기 기능에 대 한 설명입니다.
ms.openlocfilehash: 18bd33281379efe7dd2e64019e20a66a2dbec920
ms.sourcegitcommit: c48a5aca37220ac6a797ac88b09cf80090b1b7df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/13/2020
ms.locfileid: "48444214"
---
# <a name="open-preview-of-on-network-conferencing-for-audio-conferencing"></a>오디오 회의를 위한 네트워크 회의 미리 보기 열기

네트워크 회의의 열려 있는 미리 보기는 모든 고객에 게 제공 됩니다. 네트워크 회의를 통해 조직에서 직접 라우팅을 통해 Microsoft 전화 접속 번호로 인바운드 및 아웃 바운드 오디오 회의 전화를 보낼 수 있습니다. 이 접근 권한 값은 타사 전화 접속 번호에 대 한 오디오 회의 지원을 확장 하기 위한 것이 아닙니다. 타사 전화 접속 전화 번호로 음성 회의 서비스에 대 한 인바운드 호출을 라우팅하는 데 사용 되는 네트워크 회의는 지원 되지 않습니다.

이 문서에서는 조직에 대 한 네트워크 회의를 사용 하도록 설정 하는 데 필요한 전제 조건 및 구성 단계에 대해 설명 합니다.

> [!IMPORTANT]
> 인도에서 전화 접속 장비를 사용 하 여 네트워크 회의를 배포 해서는 안 됩니다.
  
## <a name="prerequisites"></a>필수 구성 요소

네트워크 회의를 구성 하기 전에 조직이 다음 필수 조건을 충족 하는지 확인 합니다. 

- 오디오 회의에 대해 사용 하도록 설정 되어 있거나 사용할 수 있는 조직의 모든 사용자가 모든 모임에 대해 팀을 사용 하 고 있는지 확인 합니다. 네트워크 회의를 통한 인바운드 및 아웃 바운드 오디오 회의 호출은 팀 모임에 대해서만 지원 됩니다.

- 네트워크 회의를 사용 하는 모든 사용자에 게 오디오 회의 라이선스를 할당 합니다.

- 오디오 회의 서비스를 설정 합니다. 자세한 내용은 [Microsoft 팀을 위한 오디오 회의 설정을](set-up-audio-conferencing-in-teams.md)참조 하세요.

- 직접 라우팅에 대 한 SBC (세션 경계 컨트롤러)를 설정 합니다. 자세한 내용은 [직접 라우팅 계획](direct-routing-plan.md) 및 [직접 라우팅 구성을](direct-routing-configure.md)참조 하세요. 

  오디오 회의 목적 으로만 직접 라우팅을 설정 하는 경우에는 네트워크 회의에 대 한 "1 단계: SBC 연결"만 완료 해야 합니다.
  
## <a name="enable-the-routing-of-dial-in-calls-to-microsoft-audio-conferencing-through-direct-routing"></a>다이렉트 라우팅을 통해 Microsoft 오디오 회의로 전화 접속 통화를 라우팅할 수 있습니다. 

온-프레미스 사용자가 직접 라우팅을 통해 음성 회의 서비스에 대 한 전화 접속 통화를 라우팅 하려면 사용자의 SBCs 및 개인 분기 교환 (Pbx)에 적절 한 라우팅 규칙을 구성 해야 합니다.

직접 라우팅 트렁크를 통해 조직의 컨퍼런스 서비스 번호로 통화를 라우팅하도록 사이트의 전화 통신 장비를 구성 해야 합니다.

**모임 > 회의 브리지** 또는 비즈니스용 Skype Online PowerShell cmdlet CsOnlineDialInConferencingBridge을 사용 하 여 팀 관리 센터에서 서비스 번호를 찾을 수 있습니다. 자세한 내용은 [Microsoft 팀의 오디오 회의 번호](see-a-list-of-audio-conferencing-numbers-in-teams.md)목록을 참조 하세요.

> [!NOTE]
> 분당 오디오 회의 라이선스가 있는 사용자는이 기능을 사용할 수 없습니다.

## <a name="enable-the-routing-of-teams-meeting-dial-out-calls-through-direct-routing"></a>다이렉트 라우팅을 통해 팀의 모임 전화 접속 통화 회람 사용

팀 모임 전화 접속 통화는 조직의 모임 내에서 전화 통화 및 통화를 포함 하 여 새 참가자를 모임에 가져오는 등의 PSTN 번호로 시작 됩니다. 

다이렉트 라우팅을 통해 팀 모임 다이얼 아웃 라우팅을 사용 하도록 설정 하려면 "OnlineAudioConferencingRoutingPolicy" 이라는 오디오 회의 라우팅 정책을 만들어 할당 해야 합니다. 

OnlineAudioConferencingRoutingPolicy 정책은 직접 라우팅을 통한 1:1 PSTN 통화에 대 한 CsOnlineVoiceRoutingPolicy와 동일 합니다. OnlineAudioConferencingRoutingPolicy 정책은 다음 cmdlet을 사용 하 여 관리할 수 있습니다.

-   New-CsOnlineAudioConferencingRoutingPolicy
- Set-CsOnlineAudioConferencingRoutingPolicy
- Get-CsOnlineAudioConferencingRoutingPolicy
- Grant-CsOnlineAudioConferencingRoutingPolicy
- Remove-CsOnlineAudioConferencingRoutingPolicy

직접 라우팅을 위한 라우팅에 대 한 자세한 내용은 [직접 라우팅에 대 한 음성 라우팅 구성을](direct-routing-voice-routing.md)참조 하세요.


다이렉트 라우팅을 통해 모임 전화 접속 통화를 회람할 수 있도록 설정 하려면 다음을 수행 해야 합니다. 

- 오디오 회의 라우팅 정책 구성
- 조직의 전화 통신 장비에서 라우팅 구성
- ) 다이얼 플랜 구성

팀 회의의 전화 접속 통화는 회의 브리지의 기본 서비스 번호에서 가져옵니다. 오디오 회의 브리지의 기본 서비스 번호에 대 한 자세한 내용은 [오디오 회의 브리지에서 전화 번호 변경을](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)참조 하세요.

### <a name="configure-audio-conferencing-routing-policies"></a>오디오 회의 라우팅 정책 구성

오디오 회의 라우팅 정책 OnlineAudioConferencingRoutingPolicy는 직접 라우팅 trunks 라우팅되는 모임 전화 접속 통화를 결정 합니다. CsOnlineVoiceRoutingPolicy 정책에 익숙한 경우이 정책은 매우 비슷한 방식으로 작동 합니다.

오디오 회의 라우팅 정책을 설정 하려면 다음 단계를 수행 해야 합니다.
1.  PSTN 용도 만들기
2.  음성 경로 구성
3.  오디오 회의 음성 라우팅 정책 만들기
4.  사용자에 게 정책 할당


#### <a name="create-pstn-usages"></a>PSTN 용도 만들기

PSTN 용도는 음성 경로의 모음입니다. 특정 이끌이의 모임에서 전화를 걸거나 받을 때 음성 경로는 사용자의 음성 라우팅 정책을 통해 사용자와 연결 된 PSTN 용도에 따라 통화의 라우팅 경로를 결정 하는 데 사용 됩니다.

"Set-CsOnlinePstnUsage" cmdlet을 사용 하 여 PSTN 사용을 만들 수 있습니다. 예를 들어:

```powershell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

#### <a name="configure-voice-routes"></a>음성 경로 구성

음성 경로는 팀 모임에서 전화를 거는 전화 번호를 기준으로 통화를 라우팅하는 데 사용 되는 PSTN 게이트웨이를 결정 합니다. 음성 경로는 팀 모임에서 보낸 전화 번호를 regex 패턴으로 사용 하 여 지정 된 통화를 라우팅하는 데 사용 되는 PSTN 게이트웨이를 결정 합니다. 음성 경로를 만들 때 경로는 하나 이상의 PSTN 용도에 연결 되어 있어야 합니다.

"CsOnlineVoiceRoute" cmdlet을 사용 하 여 음성 경로를 만들고 음성 경로와 연결할 regex 및 게이트웨이를 정의할 수 있습니다. 예를 들어:

```powershell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

#### <a name="create-audio-conferencing-voice-routing-policies"></a>오디오 회의 음성 라우팅 정책 만들기

오디오 회의 음성 라우팅 정책은 모임 전화 접속 통화의 대상 전화 번호를 기준으로 이끌이의 모임에서 발생 하는 통화를 라우팅하는 데 사용할 수 있는 경로를 결정 합니다. 오디오 회의 음성 라우팅 정책은 하나 이상의 PSTN 용도에 연결 되며, 그에 따라 정책에 연결 된 이끌이의 모임 전화 접속 통화에 사용할 가능한 경로를 결정 합니다.

"New-CsOnlineAudioConferencingRoutingPolicy" cmdlet을 사용 하 여 오디오 회의 음성 라우팅 정책을 만들 수 있습니다. 예를 들어:

```powershell
New-CsOnlineAudioConferencingRoutingPolicy "Policy 1" -OnlinePstnUsages "US and Canada"
```

정책이 사용자에 게 할당 되 고 사용자의 모임 중 하나에서 모임 전화 접속 통화가 시작 되 면 사용자의 음성 라우팅 정책을 통해 구성 도우미에 연결 된 PSTN 사용의 음성 경로가 평가 됩니다. 모임 전화 접속 통화 대상이 이끌이와 연결 된 음성 경로 중 하나에서 regex와 일치 하는 경우 모임 전화 접속 전화는 음성 경로에 정의 된 PSTN 게이트웨이로 라우팅됩니다. 모임 전화 접속 통화 대상이 이끌이에 연결 된 음성 경로와 일치 하지 않는 경우 모임 전화 접속 통화는 Microsoft에서 라우팅합니다.

#### <a name="assign-a-policy-to-your-users"></a>사용자에 게 정책 할당

오디오 회의 라우팅 정책이 정의 되 면 이제 사용자에 게 할당할 수 있습니다. 정책이 할당 되 면 해당 라우팅 경로를 결정 하기 위해 모임 전화 접속 호출이 평가 됩니다. 오디오 회의 라우팅 정책은 모임 전화 접속 통화를 시작 하는 모임 사용자와 별개로 모임 이끌이를 기준으로 항상 평가 됩니다.

"CsOnlineAudioConferencingRoutingPolicy" cmdlet을 사용 하 여 사용자에 게 오디오 회의 음성 라우팅 정책을 할당할 수 있습니다. 예를 들면 다음과 같습니다.

```powershell
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity "<User Identity>" -PolicyName "Policy 1”
```


### <a name="configure-routing-on-the-telephony-equipment-of-your-organization"></a>조직의 전화 통신 장비에 대 한 라우팅 구성

조직의 전화 통신 장비에서 직접 라우팅을 통해 라우팅되는 모임 전화 접속 통화는 의도 된 네트워크 대상에 라우팅 되어야 합니다.


### <a name="optional-configure-a-dial-plan"></a>) 다이얼 플랜 구성

다이얼 플랜은 통화 권한 부여 및 통화 라우팅과 같은 목적으로 개별 사용자가 사용 하는 전화 번호를 대체 형식 (일반적으로 E-164)으로 변환 하는 정규화 규칙 집합입니다.

기본적으로 팀 사용자는 E-164 형식의 PSTN 번호에 전화를 걸 수 있으며, 즉 + \<country code\> \<number\> . 그러나 전화 걸기 계획을 사용 하 여 사용자가 다른 형식의 전화 번호 (예를 들어, 4 자리 확장명)로 전화를 걸 수 있습니다.

네트워크 회의를 통해 내선 번호로 전화를 걸 수 있도록 하려면 다이얼 플랜을 조직의 전화 번호 범위에 맞게 내선 번호 지정으로 설정 하는 것이 좋을 수 있습니다. 다이얼 플랜을 설정 하려면 [다이얼 플랜 만들기 및 관리](create-and-manage-dial-plans.md)를 참조 하세요.


## <a name="known-issues-in-open-preview"></a>열려 있는 미리 보기의 알려진 문제점

다음은 현재 네트워크 회의의 열려 있는 Preview 릴리스에 표시 된 알려진 문제 목록입니다. Microsoft는 이러한 문제를 해결 하기 위해 노력 하 고 있습니다.

| 문제 | 방법을 |
| :--- | :--- |
| 네트워크 회의를 통해 라우팅되는 익명/숨김 발신자 Id를 사용 하는 전화 접속 통화는 모임에 연결할 수 없습니다. | 가능 하다 면 PBX 또는 SBC에서 구성을 설정 하 여 항상 네트워크 회의를 통해 라우팅된 통화에 대 한 발신자 ID를 보냅니다.|
| 경우에 따라 서비스에 전화 접속을 할 때 사용자에 게 재생 되는 시작 메시지 ("오디오 회의 서비스 시작 ...")가 잘리고 사용자가 "시작" 단어를 듣지 못합니다.| 현재이 문제에 대 한 해결 방법은 없습니다. |




## <a name="related-topics"></a>관련 항목


