---
title: 비즈니스용 Skype와 Microsoft Teams 간의 상호 연동성
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 비즈니스용 Skype와 Microsoft Teams 공존 옵션 및 비즈니스용 Skype와 Teams 간의 상호 연동성에 대한 세부 정보입니다.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7ffc673ade43e8acdb258c9364b3023ba21da2a7
ms.sourcegitcommit: 774c2fdc71df430674493c33b609523af3cbda4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/16/2021
ms.locfileid: "50260350"
---
# <a name="understand-microsoft-teams-and-skype-for-business-coexistence-and-interoperability"></a>Microsoft Teams 및 비즈니스용 Skype 공존 및 상호 연동성 이해

![프로젝트 정의 스테이지를 강조하는 업그레이드 여정 다이어그램](media/upgrade-banner-project-definition.png "프로젝트 정의 단계에 강조를 두는 업그레이드 단계")

이 문서는 업그레이드 여정의 프로젝트 정의 단계의 일부입니다. 후원 연계 및 프로젝트 팀을 만들고 프로젝트의 범위, 목표 및 계획을 정의한 후 완료합니다. 계속하기 전에 다음 활동을 완료해야 합니다.

- [프로젝트 관련자에 참여](upgrade-enlist-stakeholders.md)
- [프로젝트 범위 정의](https://aka.ms/SkypetoTeams-Scope)

현재 조직에서 비즈니스용 Skype를 사용하고 비즈니스용 Skype와 함께 Teams를 사용하기 시작하거나 Teams로 업그레이드를 시작하는 경우 다음 항목을 이해하는 것이 중요합니다.

- 두 애플리케이션이 공존하는 방식입니다.
- 상호 연동하는 경우 및 방법.
- 비즈니스용 Skype에서 Teams로의 최종 업그레이드까지 사용자의 마이그레이션을 관리하는 방법

> [!Tip]
> 공존 및 상호 연동성에 대해 알아보는 다음 [세션을 시청합니다.](https://aka.ms/teams-upgrade-coexistence-interop)
>
> 또한 업그레이드 계획 및 구현을 시작하도록 설계된 지침, 모범 사례 및 리소스를 공유하는 라이브 대화형 워크샵에 참여할 수 있습니다.
>
> 먼저 [업그레이드 세션 계획에](https://aka.ms/SkypeToTeamsPlanning) 참가하여 시작할 수 있습니다.

## <a name="coexistence-of-teams-and-skype-for-business"></a>Teams 및 비즈니스용 Skype의 공존

 Teams는 공동 작업 기능, 채팅, 통화 및 모임 기능을 제공합니다. Teams를 배포하는 방법에 따라 이러한 기능은 특정 사용자에 대해 비즈니스용 Skype에서 제공한 기능과 겹칠 수 있습니다. 기본 모드는 기능이 겹치는 비즈니스용 Skype와 함께 Teams를 실행하는 것입니다. 그러나 이러한 기능이 해당 사용자에 대해 겹치지 않도록 설계된 여러 공존 모드(업그레이드 모드라고도 하는) 중 하나를 사용자에게 할당할 수 있습니다(이 경우 Teams와 비즈니스용 Skype 간의 상호 운영성을 사용할 수 있습니다). 예를 들어 복잡한 Enterprise Voice 배포가 있는 중요한 비즈니스용 Skype Server의 자산이 있지만 사용자가 최신 모임을 최대한 빨리 즐기고 싶은 경우 모임 [우선을](meetings-first.md) 대체 경로로 평가할 수 있습니다.

조직에 적합한 경로를 결정하기 위해 다음 공존 모드를 검토하는 것이 좋습니다.

> [!Important]
> 새로운 기술을 도입하거나 익숙한 기존 비즈니스용 Skype 환경을 변경하는 동시에 새로운 비즈니스 혜택을 제공하는 것이 사용자에게 방해가 될 수 있습니다. 이 문서에 설명된 변경 내용을 구현하기 전에 사용자 준비 상태를 평가하고 통신 및 교육 계획을 구현하는 데 시간이 걸릴 수 있습니다. 또한 조직 전체에서 구현하기 전에 선택한 사용자 그룹과 함께 계획을 파일럿하는 것이 가장 권장됩니다.

### <a name="islands-mode"></a>제도 모드

기본적으로 사용자는 유사하고 겹치는 기능을 제공하는 두 가지 별도 솔루션으로 비즈니스용 Skype와 함께 Teams를 실행할 수 있습니다. 기능에는 현재 상태, 채팅, 통화 및 모임이 포함됩니다. Teams 사용자는 팀 및 채널, Microsoft 365 또는 Office 365의 파일에 대한 액세스 및 응용 프로그램과 같은 새로운 공동 작업 기능을 활용할 수도 있습니다.

'제도'라는 공존 모드에서는 각 클라이언트 애플리케이션이 별도의 섬으로 운영됩니다.  비즈니스용 Skype는 비즈니스용 Skype와 대화하고 Teams는 Teams와 대화합니다. 사용자는 두 클라이언트를 모두 실행해야 하고 통신이 시작된 클라이언트에서 기본적으로 통신할 수 있습니다. 따라서 제도 모드에서 상호 연동성이 **필요하지** 않습니다.

혼동되거나 회귀된 비즈니스용 Skype 환경을 방지하기 위해 비즈니스용 Skype는 Teams 제도 모드에서 처리되지 않는 다음 통합을 **처리합니다.**

- 외부(페더러화) 통신.
- PSTN 음성 서비스 및 음성 응용 프로그램, Office 통합.
- USB 디바이스에 대한 HID 컨트롤입니다.
- 다른 여러 통합.  

전화 시스템은 제도 모드의 **Teams에서 지원되지** 않습니다. **제도 모드는** 비즈니스용 Skype Enterprise Voice 지원하지 않습니다.

> [!Important]
> 제도 **모드에서는** 페더러드 사용자(조직 외부 사용자)의 모든 메시지와 통화가 비즈니스용 Skype로 배달됩니다. **Teams** 전용 모드로 업그레이드하면 조직 외부의 모든 메시지와 통화가 Teams로 전달됩니다.

> [!Tip]
> 비즈니스용 Skype Online 고객이 권장하는 경로는 기본 제도 모드로 시작하고, 조직에서 Teams 채택 포화상을 주도한 **다음, Teams** 전용 모드로 빠르게 전환하는 것입니다.  특히 복잡한 프레미스 및 하이브리드 고객은 Teams 공동 작업 모드가 아닌 시작 지점으로 Teams  공동 작업 모드를 통해  비즈니스용 **Skype를** 배포하고, 적절한 경우 Teams 공동 작업 및 모임 모드(즉, 모임 우선) 및 조직이 **Teams를** 채택할 준비가 된 경우 Teams 전용 모드로 진행하는 것이 도움이 될 수 있습니다.

### <a name="teams-only"></a>Teams만 해당

**Teams 전용** 사용자(업그레이드된  사용자라고도 합니다)는 Teams의 모든 기능에 액세스할 수 있습니다. 업그레이드되지 않은 사용자 또는 외부 당사자가 구성한 비즈니스용 Skype에서 모임에 참가하기 위해 비즈니스용 Skype 클라이언트를 유지할 수 있습니다. 업그레이드된 사용자는 Teams와 비즈니스용 Skype 간의 상호 운영성 기능을 사용하여 여전히 비즈니스용 Skype를 사용하는 조직의 다른 사용자와 계속 통신할  수 있습니다(비즈니스용 Skype 사용자가 제도 모드에 있지 않은 경우). 그러나 업그레이드된 사용자는 비즈니스용 Skype 채팅, 통화 또는 모임을 시작할 수 없습니다.

조직에서 일부 또는 모든 사용자가 Teams를 유일한 통신 및 공동 작업 도구로 사용할 준비가 되면 해당 사용자를 Teams 전용 모드로 **업그레이드합니다.** 제도 모드에서 업그레이드하는  경우 업그레이드 프로세스를 시작하기 전에 먼저 조직 전체에서 Teams 채택을 포화하는 것이 좋습니다. 이 채택은 제도 모드가  상호 연동성을 제공하지 못하기 때문에 통신 시나리오가 손상되지 않도록 방지합니다.

Teams 전용 **모드에서는** Teams가 SIP/Tel 프로토콜의 기본 앱입니다. 통화 또는 채팅을 위해 Outlook의 사용자의 대화처 카드에 있는 링크는 Teams에서 처리됩니다.

Teams 전용 모드로  전환하는 데 대한 추가 고려 사항은 Teams 전용 [모드 고려 사항을 참조합니다.](teams-only-mode-considerations.md)

![Teams 확인 메시지 스크린샷](media/teams-and-skypeforbusiness-coexistence-and-interop-image1.png "사용자가 Teams 전용 사용자로 업그레이드된 후 특수 모드에서 실행되는 비즈니스용 Skype 클라이언트")

### <a name="skype-for-business-only"></a>비즈니스용 Skype 전용

이 공존 모드에서 사용자는 채팅, 모임 및 통화 기능을 위해 Teams가 아닌 비즈니스용 Skype에 남아 있으며 팀 및 채널에 Teams를 사용하지 않습니다. 이 모드는 현재 사용할 수 있습니다. 그러나 현재 구현에서는 팀 및 채널이 사용자에 대해 자동으로 꺼지지 않습니다. 앱 설정 정책을 사용하여 팀과 파일을 숨기면 됩니다.

이 모드는 사용자가 준비를 구축하기 전에 Teams를 사용하기 시작하지 못하게 Teams의 관리 배포를 시작하기 전에 사용할 수 있습니다. 이 모드는 사용자에게 Teams 라이선스가 부여된 경우 비즈니스용 Skype 사용자를 위한 Teams 모임에 인증된 참가를 활성화하는 방법도 있습니다.

### <a name="skype-for-business-with-teams-collaboration"></a>Teams 공동 작업을 통해 비즈니스용 Skype

이 모드를 사용하여 비즈니스용 Skype의 기존 투자를 계속 사용하는 동안 사용자 환경에 Teams를 소개합니다. 채팅, 통화 및 모임 기능에 대해 비즈니스용 Skype를 그대로 떠날 수 있습니다. Teams 공동 작업 기능 추가:

- 팀 및 채널.
- Microsoft 365 또는 Office 365의 파일에 액세스합니다.
- 애플리케이션. Teams 커뮤니케이션 기능( 비공개 채팅, 통화 및 모임 계획)

이 모드에서는 Teams 비공개 채팅, 통화 및 모임 계획이 기본적으로 해제되어 있습니다.

비즈니스용 Skype 서버의 시작점이 프레미스 또는 하이브리드인 조직은  사용자에게 상호 운영성 및 통신의 예측 가능성뿐만 아니라 Teams로 업그레이드하기 위한 예측 가능한 타임라인을 제공하려는 경우(제도 모드의 채택 포화에  대한 사용이 아니라) 이 모드를 제도 모드의 대안으로 고려해야 합니다.

### <a name="skype-for-business-with-teams-collaboration-and-meetings-also-known-as-meetings-first"></a>Teams 공동 작업 및 모임이 있는 비즈니스용 Skype( 모임 우선)라고도 합니다.

이 공존 모드를 사용하여 조직의 Teams 모임 및 공동 작업 기능을 가속화할 수 있습니다. 공존 모드를 사용하면 사용자가 우수한 Teams 모임 환경을 활용할 수 있습니다.

- 훌륭한 품질입니다.
- 전사 및 번역입니다.
- 배경 흐리게
- 모바일 장치 및 브라우저를 포함하여 모든 플랫폼에서 뛰어난 사용자 환경.

이 모드에서는 Teams를 사용하여 팀과 채널 기반 대화를 할 수 있으며, 사용자는 Teams를 사용하여 모임을 예약하고 진행합니다. 비공개 채팅 및 통화는 비즈니스용 Skype에 남아 있습니다. Teams 및 비즈니스용 Skype는 현재 상태 조정, 자동 보류/언홀드, 두 응용 프로그램 전반에 걸쳐 HID 장치 지원과 같은 다양한 "더 나은 함께" 기능을 제공합니다. 원하는 경우 앱 설정 정책을 사용하여 팀과 채널을 숨길 수 있습니다.

이 공존 모드는 비즈니스용 Skype의 프레미스 배포가 있는 조직에 특히 Enterprise Voice. 이러한 조직은 Teams로 업그레이드하는 데 다소 시간이 걸릴 수 있으며, 가능한 한 빨리 우수한 Teams 모임을 통해 혜택을 받을 수 있습니다.

> [!TIP]
> 비즈니스용 Skype가 계속 사용 중일 때 Teams에서 사용하려는 기능에 따라 권장되는 업그레이드 모드를 식별하려면 Skype to Teams 업그레이드 마법사를 [활용하세요.](https://aka.ms/SkypeToTeamsWizard)

공존 모드, 전제 구성성 및 관리에 대한 자세한 내용은 [비즈니스용 Skype와](https://aka.ms/SkypeToTeams-Interop) 함께 Teams를 사용하는 조직에 [](https://aka.ms/SkypeToTeams-SetCoexistence)대한 마이그레이션 및 상호 운영성 지침 및 공존 및 업그레이드 설정을 참조하세요.

|의사 결정점 아이콘 |아이콘 정의 |설명 |
|---|---|---|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|의사 결정 지점|<ul><li>조직 및 사용자의 요구에 가장 적합한 공존 모드는 무엇입니까?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next step"/>|다음 단계|<ul><li>업그레이드 여정에 가장 적합한 방법을 선택하세요.</li></ul>|

## <a name="interoperability-of-teams-and-skype-for-business"></a>Teams 및 비즈니스용 Skype의 상호 연동성

상호 운영성은 동일한 조직의 Teams 및 비즈니스용 Skype 사용자가 Teams 및 비즈니스용 Skype에서 통신할 수 있는 능력입니다.

상호 운영성은 수신기의 공존 모드(업그레이드 모드라고도 하는)에 의해 관리됩니다. 수신기가 제도 모드인 경우 상호 **연동성이** 없습니다.

> [!Note]
> 제도를 제외한 모든 공존 모드로 배포되면 Teams 및 [](#interoperability-of-teams-and-skype-for-business)비즈니스용 Skype가 상호 협력하여 사용자가 서로 채팅하고 전화를 걸 수 있으며 Teams로 업그레이드하는 동안 조직 전체에서 통신이 유연하게 유지될 수 있습니다. 공존 모드는 상호 연동성을 관리합니다. 수신기의 공존 모드는 상호 연동성을 사용할 수 있는지 여부를 판단합니다. 예를 들어 수신기가 한 클라이언트(예: Teams)에서만 채팅을 사용할 수 있는 모드인 경우 초기자가 다른 클라이언트(이 경우 비즈니스용 Skype)를 사용하여 채팅을 시작하는 경우 일반적으로 채팅 상호 연동성을 사용할 수 있습니다. 반면 수신기가 두 클라이언트(제도 모드)에서 채팅을 사용할 수 있는 모드에 있는 경우 채팅에 상호 연동성을 사용할 수 없습니다. 이 메시지는 초기자가 채팅을 시작한 동일한 클라이언트의 받는 사람에 의해 수신됩니다. 따라서 제도 모드에서 적절한 **통신을** 위해서는 Teams 채택 포화가 필요합니다. 즉, 모든 사용자가 두 클라이언트를 적극적으로 사용하고 모니터링합니다.

> [!Note]
> **최신 공존 환경을 사용하려면 클라이언트 버전이 사용자의 Office 배포 채널에서 사용 가능한 최신 클라이언트가 되어야 합니다.**

### <a name="native-interop-and-interop-escalation"></a>네이티브 interop 및 interop 에스컬ation

네이티브 및 Interop 에스컬레이터의 두 가지 유형의 Interop 환경이 있습니다.

- 사용자가 현재 사용하고 있는 클라이언트에서 네이티브 _interop_ 환경이 발생합니다. 한 사용자는 비즈니스용 Skype 클라이언트에, 다른 하나는 Teams에 있습니다. 네이티브 Interop 환경은 통신하기 위해 다른 클라이언트로 전달되지 않습니다. 사용자는 현재 사용 중인 클라이언트에서 대화를 진행할 수 있습니다. 기본 Interop 환경은 일대일 채팅 및 통화입니다.
- _상호 운영 에스컬링_ 환경은 사용자가 데스크톱 공유와 같은 고급 작업을 수행할 수 있도록 돕는 작업의 일부로, 클라이언트는 사용자가 모임에 참가하여 해당 모임의 환경을 계속 진행할 수 있도록 하는 모임을 쉽게 만들 수 있도록 합니다. 모임은 작업의 초기자 플랫폼에서 만들어집니다. 해당 플랫폼에 없는 사용자 또는 사용자는 모임 참가 링크를 수신합니다. 이 링크를 클릭하면 호환되는 클라이언트(브라우저, 웹앱 또는 구성에 따라 전체 클라이언트)에서 모임에 참가합니다. 비즈니스용 Skype에서 Interop 에스컬레이터를 사용하려면 최신 클라이언트가 필요합니다. 이제 Teams에서 Interop 에스컬레이터를 사용할 수 있습니다. 둘 다 테넌트 내 상호 연동성 환경 및 페더러드 통신 교차 테넌트에서 지원됩니다.

### <a name="native-interop-experiences"></a>네이티브 Interop 환경

사용자에게 할당된 공존 모드에 따라(앞서 설명한) 다음과 같은 네이티브 Interop 환경을 사용할 수 있습니다.

비즈니스용 Skype 사용자는 Teams 사용자와 일대일 채팅을 할 수 있으며, 그 반대의 경우도 마찬가지입니다. Interop 채팅은 Teams 클라우드 서비스의 일부인 Interop 게이트웨이를 통과해야 합니다(따라서 온라인에만 존재). 상호 채팅은 일반 텍스트입니다. 풍부한 텍스트와 이모티콘은 지원되지 않습니다. Teams 및 비즈니스용 Skype의 사용자에게는 대화가 상호 대화인 것으로 통보됩니다.

<!--![Screen shot of Interop chat experience from Teams](media/Interop_chat_experience_from_Teams.png "Interop chat experience from Teams")-->

비즈니스용 Skype 사용자는 Teams 사용자에게 일대일 음성 및 영상 통화를 걸 수 있으며 Teams 사용자는 동일한 작업을 할 수 있습니다.

<!--![Screen shot of Interop calling experience from Teams](media/Interop_calling_experience_from_Teams.png "Interop calling experience from Teams")-->

> [!Important]
> 비즈니스용 Skype의 프레미스 배포와 상호 작업 환경을 사용하려면 Microsoft 365 또는 Office 365 비즈니스용 Skype를 통해 하이브리드 모드에 있는 비즈니스용 Skype 환경이 필요합니다. 자세한 내용은 마이그레이션 및 상호 [연동성 지침을 참조하세요.](https://aka.ms/SkypeToTeams-Interop)

이러한 상호 작업 환경은 Teams 공동 작업이 있는 비즈니스용 **Skype, Teams** 공동 작업 및 모임이 있는 **비즈니스용 Skype,** 비즈니스용 **Skype만** 또는 **Teams만이** 할당된 사용자 간에 사용할 수 있습니다. 제도 모드에서는 사용자에게 상호 **연동성이** 없습니다.

### <a name="native-interop-experience-limitations"></a>네이티브 Interop 환경 제한 사항

프로토콜과 기술의 차이로 인하여 모든 기능을 기본적으로 지원할 수 없습니다. 특히 다음 기능을 사용할 수 없습니다.

- Markdown, 풍부한 텍스트 및 전체 이모티콘 집합은 Teams 또는 비즈니스용 Skype에서 지원되지 않습니다. Teams 채팅의 작성 상자의 다른 기본 기능은 지원되지 않습니다.
- Teams와 비즈니스용 Skype 간의 화면 공유(데스크톱 또는 앱 공유)는 기본적으로 지원되지 않습니다. 그러나 Interop 에스컬레이터를 통해 지원됩니다.
- Teams의 그룹 채팅(다중 파티 대화)에는 Teams를 사용하는 참가자만 포함할 수 있습니다.
- 비즈니스용 Skype의 여러 파티 IM 대화(그룹 채팅)에는 비즈니스용 Skype를 사용하는 참가자만 포함할 수 있습니다. 그러나 비즈니스용 Skype에서 다중 파티에 대한 상호Op 에스컬레이터를 사용할 수 있습니다.
- Teams 및 비즈니스용 Skype 사용자 모두와 관련된 다중 파티 통화로 진행되는 피어 투 피어 음성 또는 비디오 통화를 에스컬링하는 것은 지원되지 않습니다.
- 두 파티 채팅 또는 그룹 채팅의 파일 첨부 파일을 Teams에서 비즈니스용 Skype로 전송하는 파일 전송은 지원되지 않습니다.
- 비즈니스용 Skype 영구 채팅과 상호 연동성은 없습니다.

이러한 모든 제한 사항(영구 채팅 제외)의 경우 한 사용자가 모임을 시작하고 다른 사용자를 초대하여 모임에 참가하도록 초대할 수 있습니다.

이 해결은 상호Op 에스컬레이터의 기초입니다. 특히 다중파트에 대한 화면 공유 및 에스컬링은 기본적으로 달성할 수 없지만 상호Op 에스컬링을 통해 지원됩니다.

### <a name="interop-escalation-experiences"></a>Interop 에스컬레이터 환경

Interop 에스컬링은 모임에 관리되는 에스컬링을 통해 네이티브 Interop 기능을 보완하는 것으로 구성됩니다. 모임은 어떤 클라이언트를 사용하건 누구나 사용할 수 있는 풍부한 환경을 제공합니다.

Teams 사용자가 Interop 에스컬링을 트리거하면 Teams 모임이 생성됩니다. 비즈니스용 Skype 사용자가 트리거하면 비즈니스용 Skype 모임이 만들어집니다. 두 경우 모두 만든 모임은 **모임** 시작 모임으로, 사용자의 일정에 반영되지 않습니다.

다른 파티는 interop 채팅을 통해 모임 참가 링크를 받고 해당 링크를 클릭하여 참가합니다. 비즈니스용 Skype 사용자에게 Teams 계정이 있으며 Teams 사용자가 초대한 경우 인증된 모임에 참가하게 됩니다. 그렇지 않으면 익명 참가자로 참가합니다. 반대로, Teams 사용자는 거의 항상 비즈니스용 Skype 계정과 비즈니스용 Skype 클라이언트를 사용하여 인증된 참가자로 비즈니스용 Skype 모임에 참가할 수 있지만, 익명 참가자로 참가할 수도 있습니다(예: Skype 모임 앱 사용).

당사자가 모임에 참가하면 데스크톱 또는 콘텐츠 공유, 파일 공유 또는 전송, 다른 참가자 추가 등 모임에서 지원되는 모든 활동을 진행할 수 있습니다.

#### <a name="interop-escalation-from-skype-for-business"></a>비즈니스용 Skype의 Interop 에스컬레이터

비즈니스용 Skype의 Interop 및 Interop 에스컬레이터는 2019년 7월 월간 C2R 빌드에서 업데이트되었습니다. 이전에는 비즈니스용 Skype는 원격 파티가 Teams를 사용하고 있는 것을 사전에 인식하지 못했습니다. 세션이 설정된 후에 수신된 신호에서만 해당 것으로 나타날 수 있습니다.

신호가 Interop 게이트웨이에서(또는 통과) 응답을 왔다고 표시하면 다른 사용자가 비즈니스용 Skype를 사용하지 않았다는 노란색 비즈니스 표시줄(배너)이 표시됩니다. 서비스의 발전으로 인해 비즈니스용 Skype 사용자가 실제 Teams 전용 사용자보다는 클라우드 음성 서비스 또는 기타 클라우드 음성 서비스에 연결될 때 비즈니스 바를 볼 수 있는 거짓 긍정이 **일어났습니다.**

이러한 거짓 긍정을 방지하기 위해 현재 상태 서비스는 다른 사용자가 Teams 전용 실제 사용자일 때 비즈니스용 Skype 클라이언트에 **알릴** 것입니다. 이를 통해 비즈니스용 Skype는 대화 창이 만들어지기 전 상호 작업 대화를 만들어야 하며 대화 창은 interop과 관련이 있어야 하다는 것을 알 수 있습니다.

![비즈니스용 Skype 사용자와 상호 작업 대화를 만드는 Teams 메시지 스크린샷](media/teams-and-skypeforbusiness-coexistence-and-interop-create-conversation-with-skype-user.png)

예를 들어 비즈니스용 Skype 사용자가 데스크톱을 공유하려는 경우 모임을 시작하고 단계를 안내합니다.

![Teams 사용자와 모임을 시작하는 Teams 메시지 스크린샷](media/teams-and-skypeforbusiness-coexistence-and-interop-start-meeting-with-teams-user.png)

그 동안 Teams 사용자는 모임 링크가 있는 들어오는 채팅 메시지를 받고 참가하도록 안내됩니다.

비즈니스용 Skype 모임으로의 이 에스컬레이터는 테넌트 내 Interop 및 테넌트 간 페더레이터 통화 및 채팅 모두에 사용할 수 있습니다. 기본적으로 설정되어 있으며 관리자가 프로비전해야 하는 설정은 없습니다.

#### <a name="interop-escalation-from-teams"></a>Teams의 Interop 에스컬레이터

Teams에서 Teams 모임으로의 Interop 에스컬링은 Teams 사용자가 비즈니스용 Skype 사용자 또는 테넌트 간 Interop 페더링 스레드에서 테넌트 내 interop 스레드에서 데스크톱 공유 단추를 선택하면 사용할 수 있습니다. Interop 에스컬레이터는 1:1 채팅 대화 또는 1:1 통화에서 지원됩니다.

이 기능은 Windows용 Teams 데스크톱 클라이언트, Mac용 Teams 데스크톱 클라이언트, 콘텐츠 공유가 지원되는 브라우저의 Teams 웹 클라이언트에서 지원되는 반면 비즈니스용 Skype 클라이언트 버전과 통신할 수 있습니다.

상호 연동성 스레드 및 페더링 상호 연동성 스레드에서 Teams 사용자는 이제 콘텐츠 공유를 시작할 수 있는 컨트롤(단추)을 가졌다. Teams 사용자가 단추를 선택하면 콘텐츠를 공유하려면 Teams 모임을 시작해야 하다는 내용의 추가 메뉴가 표시됩니다.

사용자가 통화 중이면 메뉴에서 Teams 모임에 참가하면 Teams와 비즈니스용 Skype 간의 현재 통화가 종료된다고 경고합니다. 선택한 경우 수락하기 전에 비즈니스용 Skype 사용자에게 경고를 할 수 있습니다.

![비즈니스용 Skype 사용자와 모임을 공유하기 위한 Teams 메시지 스크린샷](media/teams-and-skypeforbusiness-coexistence-and-interop-share-meeting-with-skype-user.png)

수락하면 Teams 모임에 참가합니다. 모임의 공유 트레이에서 공유를 시작해야 합니다.

한편 비즈니스용 Skype 사용자는 모임 링크가 있는 들어오는 채팅 메시지를 받고 참가하도록 안내됩니다.

Teams 모임에 대한 이 에스컬레이터는 테넌트 내 Interop 및 테넌트 간 페더레이터 통화 및 채팅 모두에 사용할 수 있습니다. 기본적으로 설정되어 있으며 관리자가 프로비전해야 하는 설정은 없습니다. 그러나 관리자가 에 설정하는 경우 사용자에 대해 ``-AllowPrivateMeetNow`` ``CsTeamsMeetingPolicy`` 해제되어 ``$false`` 있습니다.

이 문서를 검토한 후 다음 관련 문서를 참조하세요.

- [업그레이드 여정 선택](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [마이그레이션 및 상호 연동성 지침](https://aka.ms/SkypeToTeams-Interop)
- [비즈니스용 Skype와 공존](coexistence-chat-calls-presence.md)
-  [구현 세부 정보를 위해](https://aka.ms/SkypeToTeams-SetCoexistence) 공존 및 업그레이드 설정을 설정합니다.

## <a name="related-links"></a>관련 링크

[비디오: SfB와 Teams 간의 공존 및 상호 운영성 관리](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)
