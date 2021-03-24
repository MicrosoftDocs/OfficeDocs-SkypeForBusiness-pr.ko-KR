---
title: Microsoft Teams 및 비즈니스용 Skype 공존 및 상호 연동성 이해
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 비즈니스용 Skype 및 Microsoft Teams 공존 옵션에 대한 세부 정보 및 비즈니스용 Skype와 Teams 간의 상호 연동성에 대한 세부 정보입니다.
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
ms.openlocfilehash: 3332ec1a5c5bc05bc833511a3b33e0f4dff6cccc
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111134"
---
# <a name="understand-microsoft-teams-and-skype-for-business-coexistence-and-interoperability"></a>Microsoft Teams 및 비즈니스용 Skype 공존 및 상호 연동성 이해

![프로젝트 정의 스테이지를 강조하는 업그레이드 여정 다이어그램](media/upgrade-banner-project-definition.png "프로젝트 정의 단계에 강조를 두는 업그레이드 여정의 단계")

이 문서는 업그레이드 여정의 프로젝트 정의 단계의 일부입니다. 후원 연대 및 프로젝트 팀을 만든 후 완료하고 프로젝트의 범위, 목표 및 계획을 정의합니다. 계속하기 전에 다음 작업을 완료한지 확인합니다.

- [프로젝트 관계자 인리스트](upgrade-enlist-stakeholders.md)
- [프로젝트 범위 정의](./upgrade-define-project-scope.md)

조직에서 오늘날 비즈니스용 Skype를 사용하고 비즈니스용 Skype와 함께 Teams를 사용하기 시작하거나 Teams로 업그레이드를 시작하는 경우 두 애플리케이션이 어떻게 공존하는지, 언제, 어떻게 상호 운영하는지, 사용자의 마이그레이션을 비즈니스용 Skype에서 Teams로 최종 업그레이드하는 방법을 이해하는 것이 중요합니다.

> [!Tip]
> 다음 세션을 시청하여 공존 및 상호 연동성에 [대해 알아보고자 합니다.](https://aka.ms/teams-upgrade-coexistence-interop)
>
> 또한 업그레이드 계획 및 구현을 시작하도록 설계된 지침, 모범 사례 및 리소스를 공유하는 라이브 대화형 워크샵에 참가할 수 있습니다.
>
> 먼저 [업그레이드 계획 세션에](./upgrade-workshops-landing-page.yml) 참가하여 시작할 수 있습니다.

## <a name="coexistence-of-teams-and-skype-for-business-overview"></a>Teams 및 비즈니스용 Skype 개요의 공존

다음 섹션에서는 Teams로 업그레이드할 때 사용할 수 있는 공존 모드와 각 모드가 제공하는 기능을 설명합니다. 또한 Skype-for-Business 클라이언트의 사용자와 Teams 클라이언트의 사용자 간에 발생하는 상호 연동성(interop)과 선택한 공존 모드의 영향을 받는 상호Op에 대해 설명합니다.

 Teams는 공동 작업 기능, 채팅, 통화 및 모임 기능을 제공합니다. Teams를 배포하는 방법에 따라 이러한 기능은 특정 사용자에 대해 비즈니스용 Skype에서 제공한 기능과 겹칠 수 있습니다. 기본 모드는 기능이 겹치는 비즈니스용 Skype와 함께 Teams를 실행하는 것입니다. 그러나 사용자는 이러한 기능이 해당 사용자에 대해 겹치지 않도록 설계된 여러 공존 모드(업그레이드 모드)중 하나를 할당할 수 있습니다(이 경우 Teams 및 Skype for Business 간 상호 운영성을 사용할 수 있습니다). 예를 들어 복잡한 배포를 통해 비즈니스용 Skype Server Enterprise Voice 자산이 있지만 사용자가 최신 모임을 최대한 빨리 즐기길 원할 경우 [](meetings-first.md) 모임 우선을 대체 경로로 평가할 수 있습니다.

조직에 적합한 경로를 결정하기 위해 다음 공존 모드를 검토하는 것이 좋습니다.

> [!Important]
> 새로운 기술을 도입하거나 익숙한 기존 비즈니스용 Skype 환경을 변경하는 동시에 새로운 비즈니스 혜택을 제공하는 동시에 사용자에게 방해가 될 수 있습니다. 이 문서에 설명된 변경 내용을 구현하기 전에 사용자 준비 상태를 평가하고 통신 및 교육 계획을 구현하는 데 시간이 걸릴 수 있습니다. 또한 조직 전체에서 구현하기 전에 선택한 사용자 그룹으로 계획을 파일럿하는 것이 권장됩니다.

### <a name="islands-mode"></a>섬 모드

기본적으로 사용자는 비즈니스용 Skype와 함께 유사하고 겹치는 기능을 제공하는 두 개의 별도 솔루션으로 Teams를 실행할 수 있습니다. 기능에는 현재 상태, 채팅, 통화 및 모임이 포함됩니다. 또한 Teams 사용자는 팀 및 채널과 같은 새로운 공동 작업 기능, Microsoft 365 또는 Office 365의 파일에 대한 액세스 및 애플리케이션을 활용할 수 있습니다.

이 공존 **모드에서는 Islands라는** 각 클라이언트 애플리케이션이 별도 섬으로 작동합니다. 비즈니스용 Skype는 비즈니스용 Skype와 대화하고 Teams는 Teams와 대화합니다. 사용자는 두 클라이언트를 모두 실행해야 하고 통신이 시작된 클라이언트에서 기본적으로 통신할 수 있습니다. 따라서 섬 모드에서 상호 연동성이 **필요하지** 않습니다.

비즈니스용 Skype 환경을 혼동하거나 회귀하지 않도록 비즈니스용 Skype는 Teams **Islands** 모드에서 처리되지 않는 다음 통합을 처리합니다.

- 외부(페더리화) 통신.
- PSTN 음성 서비스 및 음성 애플리케이션, Office 통합.
- USB 디바이스에 대한 HID 컨트롤입니다.
- 다른 몇 가지 통합.  

전화 시스템은 제도의 Teams 모드에서 **지원되지** 않습니다. **아일랜드 모드는** 비즈니스용 Skype Enterprise Voice 지원하지 않습니다.

> [!Important]
> 제도 **모드에서** 페더리드 사용자(조직 외부 사용자)의 모든 메시지와 통화가 비즈니스용 Skype로 배달됩니다. **Teams Only** 모드로 업그레이드한 후 조직 외부의 모든 메시지와 통화가 Teams로 배달됩니다.

> [!Tip]
> 비즈니스용 Skype Online 고객이 권장하는 경로는 기본 제도 모드로 시작하고, 조직에서 Teams 채택 포화 상태로 이동한 다음 **Teams 전용** 모드로 빠르게 이동하는 것입니다.  프레미스 및 하이브리드 고객, 특히 복잡한 고객은  팀 공동 작업 모드가 아닌 시작 지점으로 비즈니스용 Skype 공동  작업 모드를 배포하고, 적절한 경우 팀 공동 작업 및 모임 모드(즉, 모임 우선)를 통해 비즈니스용 Skype로 진행하고 조직에서 Teams를 채택할 준비가 된 경우 **Teams 전용** 모드로 진행할 수 있습니다. 

### <a name="teams-only"></a>Teams Only

Teams **Only** 사용자(업그레이드된  사용자라고도 하는 사용자)는 Teams의 모든 기능에 액세스할 수 있습니다. 업그레이드되지 않은 사용자 또는 외부 당사자가 구성한 비즈니스용 Skype에서 모임에 참가하기 위해 비즈니스용 Skype 클라이언트를 유지할 수 있습니다. 업그레이드된 사용자는 Teams와 비즈니스용 Skype 간의 상호 운영성 기능을 사용하여 여전히 비즈니스용 Skype를 사용하는 조직의 다른 사용자와 계속 통신할  수 있습니다(비즈니스용 Skype 사용자가 아일랜드 모드에 있지 않은 경우). 그러나 업그레이드된 사용자는 비즈니스용 Skype 채팅, 통화 또는 모임을 시작할 수 없습니다.

조직에서 일부 또는 모든 사용자가 Teams를 유일한 통신 및 공동 작업 도구로 사용할 준비가 되자마자 해당 사용자를 Teams 전용 모드로 **업그레이드합니다.** 제도 모드에서 업그레이드하는  경우 업그레이드 프로세스를 시작하기 전에 먼저 조직 전체에서 Teams 채택을 포화하는 것이 좋습니다. 이 채택은 상호 연동성을 제공하지 않는 **제도** 모드로 인해 통신 시나리오가 손상되지 않도록 방지합니다.

Teams **전용 모드에서 Teams는** SIP/Tel 프로토콜의 기본 앱입니다. 통화 또는 채팅용 Outlook의 사용자의 연락처 카드의 링크는 Teams에서 처리됩니다.

**Teams 전용** 모드로 이동하는 데 대한 추가 고려 사항은 Teams 전용 모드 고려 [사항을 참조합니다.](teams-only-mode-considerations.md)

![Teams 확인 메시지의 스크린샷](media/teams-and-skypeforbusiness-coexistence-and-interop-image1.png "사용자가 Teams 전용 사용자로 업그레이드된 후 특수 모드로 실행되는 비즈니스용 Skype 클라이언트")

### <a name="skype-for-business-only"></a>비즈니스용 Skype 전용

이 공존 모드에서 사용자는 채팅, 모임 및 통화 기능을 위해 Teams가 아닌 비즈니스용 Skype에 남아 있으며 팀 및 채널에 Teams를 사용하지 않습니다. 이 모드는 오늘 사용할 수 있습니다. 그러나 현재 구현에서는 사용자에 대해 팀 및 채널이 자동으로 해제되지 않습니다. 앱 설정 정책을 사용하여 팀 및 파일을 숨길 수 있습니다.

이 모드는 Teams의 관리되는 배포를 시작하기 전에 사용할 수 있습니다. 이 모드는 사용자가 미리 준비 준비를 하여 Teams를 사용하기 시작하지 못하게 할 수 있습니다. 또한 이 모드는 사용자가 Teams에 대해 라이선스를 부여한 경우 비즈니스용 Skype 사용자를 위한 Teams 모임에 인증된 참여를 사용하도록 설정하는 방법도 있습니다.

### <a name="skype-for-business-with-teams-collaboration"></a>Teams 공동 작업을 통해 비즈니스용 Skype

이 모드를 사용하여 비즈니스용 Skype에 대한 기존 투자를 계속 사용하는 동안 사용자 환경에 Teams를 소개합니다. 채팅, 통화 및 모임 기능에 대해 비즈니스용 Skype를 그대로 떠날 수 있습니다. Teams 공동 작업 기능 추가:

- 팀 및 채널.
- Microsoft 365 또는 Office 365의 파일에 액세스합니다.
- 애플리케이션. 팀 통신 기능- 비공개 채팅, 통화 및 모임 계획.

팀 개인 채팅, 통화 및 모임 계획은 기본적으로 이 모드에서 해제됩니다.

비즈니스용 Skype 서버의 시작 지점을 프레미스 또는 하이브리드로 전환하는 조직은 사용자에게 통신에 대한 상호 운영성과 예측성을 제공하려는 경우 이 모드를 아일랜드 모드의 대안으로 고려해야 합니다( 아일랜드 모드에서 채택 포화에 대한 사용이 아니라 Teams로의 업그레이드를 예측할 수 있는 타임라인을 갖는 경우).  

### <a name="skype-for-business-with-teams-collaboration-and-meetings-also-known-as-meetings-first"></a>Teams 공동 작업 및 모임이 있는 비즈니스용 Skype(모임 우선)라고도 합니다.

이 공존 모드를 사용하여 조직의 Teams 모임 및 공동 작업 기능의 가용성을 가속화합니다. 공존 모드를 사용하면 사용자가 우수한 Teams 모임 환경을 활용할 수 있습니다.

- 좋은 품질.
- 전사 및 번역.
- 배경 흐림.
- 모바일 장치 및 브라우저를 비롯한 모든 플랫폼에서 뛰어난 사용자 환경.

이 모드에서는 Teams for teams 및 채널 기반 대화와 함께 사용자가 Teams를 사용하여 모임을 예약하고 진행합니다. 개인 채팅 및 통화는 비즈니스용 Skype에 남아 있습니다. 팀 및 비즈니스용 Skype는 두 애플리케이션에서 현재 상태 조정, 자동 보류/보류 및 HID 디바이스 지원과 같은 다양한 "더 나은 함께" 기능의 이점을 제공합니다. 앱 설정 정책을 사용하여 원하는 경우 팀 및 채널을 숨길 수 있습니다.

이 공존 모드는 비즈니스용 Skype-프레미스 배포가 있는 조직에 특히 Enterprise Voice. 이러한 조직은 Teams로 업그레이드하는 데 다소 시간이 걸릴 수 있으며 가능한 한 빨리 우수한 Teams 모임의 혜택을 받을 수 있습니다.

> [!TIP]
> 비즈니스용 Skype가 여전히 사용 중일 때 Teams에서 사용하도록 설정하려는 기능에 따라 권장 업그레이드 모드를 식별하려면 Skype to Teams 업그레이드 [마법사를 활용하세요.](https://aka.ms/SkypeToTeamsWizard)

공존 모드, 전제 구성 및 관리에 대한 자세한 내용은 비즈니스용 Skype와 함께 [Teams를](./migration-interop-guidance-for-teams-with-skype.md) 사용하는 조직에 대한 마이그레이션 및 상호 운영성 지침을 참조하고 공존 및 업그레이드 설정 설정을 [참조하세요.](./setting-your-coexistence-and-upgrade-settings.md)

|의사 결정점 아이콘 |아이콘 정의 |설명 |
|---|---|---|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|결정 지점|<ul><li>조직 및 사용자의 요구에 가장 적합한 공존 모드는 무엇입니까?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next step"/>|다음 단계|<ul><li>업그레이드 여정에 가장 적합한 방법을 선택하세요.</li></ul>|

### <a name="interoperability-of-teams-and-skype-for-business"></a>Teams 및 비즈니스용 Skype의 상호 연동성

상호 운영성은 동일한 조직의 Teams 및 비즈니스용 Skype 사용자가 Teams 및 비즈니스용 Skype에서 통신할 수 있는 능력입니다.

상호 운영성은 수신기의 공존 모드(업그레이드 모드라고도 합니다)에 의해 관리됩니다. 수신기가 섬 모드에 있는 경우 상호 **연동성이** 없습니다.

> [!Note]
> 제도를 제외한 모든 공존 모드로 배포되는 경우 Teams [](#interoperability-of-teams-and-skype-for-business)및 비즈니스용 Skype가 상호 작동하여 사용자가 채팅하고 통화할 수 있으며, Teams로 업그레이드하는 동안 조직 전체에서 통신이 유동적으로 유지될 수 있습니다. 공존 모드는 상호 연동성을 관리합니다. 수신기의 공존 모드는 상호 연동성을 사용할 수 있는지 여부를 결정합니다. 예를 들어 수신기가 한 클라이언트(예: Teams)에서만 채팅을 사용할 수 있는 모드인 경우, 초기자가 다른 클라이언트(이 경우 비즈니스용 Skype)를 사용하여 채팅을 시작하는 경우 채팅 상호 연동성을 사용할 수 있습니다. 반면 수신기가 두 클라이언트(섬 모드)에서 채팅을 사용할 수 있는 모드에 있는 경우 채팅에 상호 가동성을 사용할 수 없습니다. 이 메시지는 시작자가 채팅을 시작한 동일한 클라이언트에서 받는 사람에 의해 수신됩니다. 따라서 제도 모드에서 적절한 **통신을** 위해서는 Teams 채택 포화가 필요합니다. 즉, 모든 사용자가 두 클라이언트를 적극적으로 사용하고 모니터링합니다.

> [!Note]
> **최신 공존 환경을 사용하려면 클라이언트 버전이 사용자의 Office 배포 채널에서 사용 가능한 최신 클라이언트가 되어야 합니다.**

#### <a name="native-interop-and-interop-escalation"></a>네이티브 interop 및 interop 에스컬레이터

네이티브 및 인터팝 에스컬레이터에는 두 가지 유형의 상호프 환경이 있습니다.

- 사용자가 현재 사용하고 있는 클라이언트에서 네이티브 _interop_ 환경이 발생합니다. 한 사용자는 비즈니스용 Skype 클라이언트에, 다른 사용자는 Teams에 있습니다. 네이티브 인터팝 환경은 통신을 위해 다른 클라이언트로 연결되지 않습니다. 사용자는 현재 사용 중인 클라이언트에서 대화를 진행할 수 있습니다. 네이티브 인터팝 환경은 일대일 채팅 및 통화입니다.
- _상호 운영 에스컬레이터_ 환경은 사용자가 데스크톱 공유와 같은 고급 작업을 수행하는 데 도움이 되는 일부로, 클라이언트는 사용자가 참가하여 해당 모임의 환경을 계속할 수 있도록 모임을 쉽게 만들 수 있습니다. 모임은 작업의 시작자 플랫폼에서 만들어집니다. 해당 플랫폼에 없는 사용자 또는 사용자는 모임 참가 링크를 수신합니다. 이 링크를 클릭하면 호환되는 클라이언트(브라우저, 웹앱 또는 전체 클라이언트)에서 모임에 조인됩니다(구성에 따라). 비즈니스용 Skype에서 인터오프 에스컬레이터하려면 최근 클라이언트가 필요합니다. 이제 Teams에서 인터팝 에스컬레이터를 사용할 수 있습니다. 둘 다 테넌트 내 및 페더리드 통신 교차 테넌트에 대해 상호 연동성 환경에서 지원됩니다.

#### <a name="native-interop-experiences"></a>네이티브 인터팝 환경

사용자에게 할당된 공존 모드(이전에 설명한 바와 같이)에 따라 다음 네이티브 인터프 환경을 사용할 수 있습니다.

비즈니스용 Skype 사용자는 Teams 사용자와 일대일 채팅을 할 수 있으며 그 반대의 경우도 마찬가지입니다. Interop 채팅은 Teams 클라우드 서비스의 일부인 인터프 게이트웨이를 통과해야 합니다(따라서 온라인에만 존재). 대화형 채팅은 일반 텍스트입니다. 풍부한 텍스트와 이모티콘은 지원되지 않습니다. Teams 및 비즈니스용 Skype의 사용자는 대화가 상호 대화인 것으로 통보됩니다.

<!--![Screen shot of Interop chat experience from Teams](media/Interop_chat_experience_from_Teams.png "Interop chat experience from Teams")-->

비즈니스용 Skype 사용자는 Teams 사용자에게 일대일 음성 및 화상 통화를 할 수 있으며 Teams 사용자는 동일한 작업을 할 수 있습니다.

<!--![Screen shot of Interop calling experience from Teams](media/Interop_calling_experience_from_Teams.png "Interop calling experience from Teams")-->

> [!Important]
> 비즈니스용 Skype의 프레미스 배포와의 상호 작업 환경은 Microsoft 365 또는 Office 365 비즈니스용 Skype를 통해 프레미스 환경이 하이브리드 모드로 설정되어 있는 것이 필요합니다. 자세한 내용은 마이그레이션 및 상호 [연동성 지침을 참조하세요.](./migration-interop-guidance-for-teams-with-skype.md)

이러한 상호 작업 환경은 다음 공존 모드 중 하나를 할당한 사용자 간에 사용할 수 **있습니다.** 팀 공동 작업으로 비즈니스용 **Skype,** Teams 공동 작업 및 모임이 있는 비즈니스용 Skype, **비즈니스용 Skype** 전용 또는 Teams **전용입니다.** 섬 모드에서는 사용자에게 상호 **연동성이** 없습니다.

#### <a name="native-interop-experience-limitations"></a>네이티브 인터팝 환경 제한 사항

프로토콜과 기술의 차이로 인하여 모든 기능을 기본적으로 지원할 수 없습니다. 특히 다음 기능을 사용할 수 없습니다.

- Markdown, rich text 및 전체 이모티콘 집합은 Teams 또는 비즈니스용 Skype에서 지원되지 않습니다. Teams 채팅의 작성 상자의 다른 네이티브 기능은 지원되지 않습니다.
- Teams와 비즈니스용 Skype 간에 화면 공유(데스크톱 또는 앱 공유)는 기본적으로 지원되지 않습니다. 그러나 인터프 에스컬레이터를 통해 지원됩니다.
- Teams의 그룹 채팅(다중 파티 대화)은 Teams를 사용하는 참가자만 포함할 수 있습니다.
- 비즈니스용 Skype의 다중 파티 IM 대화(그룹 채팅)에는 비즈니스용 Skype를 사용하는 참가자만 포함할 수 있습니다. 그러나 비즈니스용 Skype에서 다중 파티로의 상호프 에스컬레이터를 사용할 수 있습니다.
- Teams 및 Skype for Business 사용자가 모두 관련된 다중 파티 통화로 진행되는 피어 투 피어 음성 또는 화상 통화를 에스컬링하는 것은 지원되지 않습니다.
- 양자 채팅에 대한 파일 전송 또는 그룹 채팅의 파일 첨부 파일 전송(Teams에서 비즈니스용 Skype로, 그 반대의 경우도 마찬가지)은 지원되지 않습니다.
- 비즈니스용 Skype 영구 채팅과 상호 연동성은 없습니다.

이러한 모든 제한 사항(영구 채팅 제외)의 경우 한 사용자가 모임을 시작하고 다른 사용자를 초대하여 모임에 참가하도록 초대할 수 있습니다.

이 해결은 상호 에스컬레이터의 기본입니다. 특히 다중파트로 화면 공유 및 에스컬레이터는 기본적으로 달성할 수 없지만 상호 에스컬레이터를 통해 지원됩니다.

#### <a name="interop-escalation-experiences"></a>상호 에스컬레이터 환경

Interop 에스컬레이터는 관리되는 에스컬레이터를 통해 모임에 대한 네이티브 인터로프 기능을 보완하는 것으로 구성됩니다. 모임은 어떤 클라이언트에 관계 없이 누구나 사용할 수 있는 풍부한 환경을 제공합니다.

Teams 사용자가 인터프 에스컬레이터를 트리거하면 Teams 모임이 만들어집니다. 비즈니스용 Skype 사용자가 트리거하면 비즈니스용 Skype 모임이 만들어집니다. 두 경우 모두 만든 모임은 모임 현재 모임입니다. 이 모임은 사용자의 일정에 반영되지 않습니다. 

다른 파티는 상호 채팅을 통해 모임 조인 링크를 수신하고 해당 링크를 클릭하여 조인합니다. 비즈니스용 Skype 사용자에게 Teams 계정이 있으며 Teams 사용자가 초대하는 경우 인증된 모임에 참가합니다. 그렇지 않으면 익명 참가자로 참가합니다. 반대로 Teams 사용자는 거의 항상 비즈니스용 Skype 계정과 비즈니스용 Skype 클라이언트를 사용하여 인증된 참가자로 비즈니스용 Skype 모임에 참가할 수 있지만, 예를 들어 Skype 모임 앱을 사용하여 익명 참가자로 참가할 수도 있습니다.

당사자가 모임에 참가하면 데스크톱 또는 콘텐츠 공유, 파일 공유 또는 전송, 다른 참가자 추가 등 모임에서 지원되는 모든 활동을 할 수 있습니다.

#### <a name="interop-escalation-from-skype-for-business"></a>비즈니스용 Skype에서 Interop 에스컬레이터

비즈니스용 Skype의 Interop 및 interop 에스컬레이터는 월간 C2R의 2019년 7월 빌드에서 업데이트되었습니다. 이전에는 비즈니스용 Skype는 원격 파티가 Teams를 사용 중이었다는 인식을 미리 인식하지 못했습니다. 세션이 설정된 후에 수신된 신호에서만 해당 것으로 나타날 수 있습니다.

신호가 응답이 인터프 게이트웨이에서(또는 통과)되었음을 나타내면 다른 사용자가 비즈니스용 Skype를 사용하지 않았다는 것을 나타내는 노란색 비즈니스 표시줄(배너)이 표시됩니다. 서비스의 발전으로 인해 비즈니스용 Skype 사용자가 실제 Teams 전용 사용자보다는 Cloud Voicemail 서비스 또는 기타 클라우드 음성 서비스에 연결될 때 비즈니스 표시줄을 볼 수 있는 거짓 긍정이 **일어났습니다.**

이러한 거짓 긍정을 방지하기 위해 현재 상태 서비스는 이제 다른 사용자가 Teams 전용 실제 사용자일 때 비즈니스용 **Skype** 클라이언트에 알릴 것입니다. 이를 통해 비즈니스용 Skype는 대화 창이 만들어지기보다 먼저 상호 작업 대화를 만들어야 하며 대화 창은 상호OP에 특정해야 하다는 것을 인식할 수 있습니다.

![비즈니스용 Skype 사용자와 상호 대화를 만드는 Teams 메시지 스크린샷](media/teams-and-skypeforbusiness-coexistence-and-interop-create-conversation-with-skype-user.png)

비즈니스용 Skype 사용자가 데스크톱을 공유하려는 경우 모임을 시작하고 단계를 안내합니다.

![Teams 사용자와 모임을 시작하는 Teams 메시지의 스크린샷](media/teams-and-skypeforbusiness-coexistence-and-interop-start-meeting-with-teams-user.png)

한편 Teams 사용자는 모임에 대한 링크가 있는 들어오는 채팅 메시지를 수신하고 참가하도록 안내됩니다.

비즈니스용 Skype 모임으로 이 에스컬레이터는 테넌트 내 인터팝 및 테넌트 간 페더레이터 통화 및 채팅 모두에서 사용할 수 있습니다. 기본적으로 설정되어 있으며 관리자가 프로비전해야 하는 설정이 없습니다.

#### <a name="interop-escalation-from-teams"></a>Teams에서 Interop 에스컬레이터

이제 Teams 사용자가 비즈니스용 Skype 사용자 또는 테넌트 간 상호 연맹 스레드에서 테넌트 내 인터프 스레드에서 데스크톱 공유 단추를 선택할 때 Teams에서 Teams 모임으로 상호 에스컬레이터를 사용할 수 있습니다. Interop 에스컬레이터는 1:1 채팅 대화 또는 1:1 통화에서 지원됩니다.

이 기능은 Windows용 Teams 데스크톱 클라이언트, Mac용 Teams 데스크톱 클라이언트 및 콘텐츠 공유가 지원되는 브라우저의 Teams 웹 클라이언트에서 지원되는 반면 비즈니스용 Skype 클라이언트 버전과 통신할 수 있습니다.

상호 실행성 스레드 및 페더링 상호 실행성 스레드에서 Teams 사용자에게 이제 콘텐츠 공유를 시작하는 컨트롤(단추)이 있습니다. Teams 사용자가 단추를 선택하면 콘텐츠를 공유하려면 Teams 모임을 시작해야 하도록 알리는 추가 메뉴가 표시됩니다.

사용자가 통화 중이면 메뉴에서 Teams와 비즈니스용 Skype 간의 현재 통화가 Teams 모임에 추가될 때 종료될 것 을 경고합니다. 선택한 경우 수락하기 전에 비즈니스용 Skype 사용자에게 경고할 수 있습니다.

![비즈니스용 Skype 사용자와 모임을 공유할 Teams 메시지 스크린샷](media/teams-and-skypeforbusiness-coexistence-and-interop-share-meeting-with-skype-user.png)

수락하면 Teams 모임에 넣게 됐다. 모임의 공유 트레이에서 공유를 시작해야 합니다.

한편 비즈니스용 Skype 사용자는 모임에 대한 링크가 있는 들어오는 채팅 메시지를 수신하고 참가하도록 안내됩니다.

Teams 모임으로의 이 에스컬레이터는 테넌트 내 인터팝 및 테넌트 간 페더레이터 통화 및 채팅 모두에서 사용할 수 있습니다. 기본적으로 설정되어 있으며 관리자가 프로비전해야 하는 설정이 없습니다. 그러나 관리자가 에 를 설정하는 경우 사용자에 대해 ``-AllowPrivateMeetNow`` ``CsTeamsMeetingPolicy`` ``$false`` 해제됩니다.

이 문서를 검토한 후 업그레이드 여정 [선택,](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)마이그레이션 및 상호 [운영성](./migration-interop-guidance-for-teams-with-skype.md)지침, 비즈니스용 [](./setting-your-coexistence-and-upgrade-settings.md) [Skype와](coexistence-chat-calls-presence.md)공존, 구현 세부 정보를 위한 공존 및 업그레이드 설정 설정을 참조하세요. 또한 비디오: [SfB와](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11) Teams 간의 공존 및 상호 운영성 관리

## <a name="technical-details-of-teams-and-skype-for-business-coexistence"></a>Teams 및 비즈니스용 Skype 공존의 기술 세부 정보

다음 섹션에서는 어떤 모드와 사용 중인 업그레이드 방법에 관계없이 동일한 조직에서 Teams 및 비즈니스용 Skype 클라이언트를 둘 다 실행하는 경우 경험할 수 있는 동작을 요약합니다.

- [모임](#meetings)
- [상호 연동성](#interoperability)
- [Interop 및 네이티브 대화 스레드](#interop-versus-native-conversation-threads)
- [현재 상태](#presence)
- [페더레이션](#federation)
- [연락처](#contacts)

### <a name="meetings"></a>모임

사용자 모드에 관계없이 사용자는 비즈니스용 Skype 또는 Teams에 관계없이 초대되는 모든 유형의 모임에 항상 참가할 수 있습니다.  그러나 사용자는 모임 유형과 일치하는 해당 클라이언트로 모임에 참가해야 합니다.

- 모임이 Teams 모임인 경우 모든 참가자(TeamsOnly, Islands 또는 Skype for Business 사용자)는 Teams 클라이언트를 사용하여 모임에 참가합니다. Teams가 설치되지 않은 경우 사용자는 모임에 참가하려고 할 때 웹으로 연결됩니다.

- 모임이 비즈니스용 Skype 모임인 경우 모든 참가자(TeamsOnly, Islands 또는 비즈니스용 Skype 사용자)는 비즈니스용 Skype 클라이언트를 사용하여 모임에 참가합니다. 비즈니스용 Skype 클라이언트가 설치되어 있지 않은 경우 사용자는 Skype 모임 앱을 통해 참가하도록 웹으로 연결됩니다.

모임을 구성할 때 예약되는 모임 유형은 다음 표와 같이 이끌이의 모드를 기반으로 합니다.

| 이끌이 모드    |      동작 |
| :------------------ | :---------------- |
| TeamsOnly, SfbWithTeamsCollabAndMeetings |    Teams에서 예약된 모든 모임입니다. 비즈니스용 Skype 추가 기능을 Outlook에서 사용할 수 없습니다. | 
| SfbWithTeamsCollab, SfbOnly   | 비즈니스용 Skype에서 예약된 모든 모임입니다. Outlook에서 팀 추가 기능을 사용할 수 없습니다. | 
| Islands | 기본적으로 비즈니스용 Skype 또는 Teams에서 모임을 예약할 수 있습니다. 두 추가 기능을 모두 Outlook에서 사용할 수 있습니다. 그러나 선택적으로 아일랜드의 사용자가 PreferredMeetingProviderForIslandsMode=Teams를 사용하여 TeamsMeetingPolicy 인스턴스를 할당하여 항상 Teams에서 모임을 예약할 수 있도록 요구할 수 있습니다.| 


### <a name="interoperability"></a>상호 연동성

Teams 및 [비즈니스용](#interoperability-of-teams-and-skype-for-business)Skype의 상호 연동성에서 위에서 설명한 대로 Teams는 특정 시나리오에서 비즈니스용 Skype와 상호 연동을 지원합니다. Interop 통신은 비즈니스용 Skype 사용자와 Teams 사용자 간에 채팅 또는 통화를 참조합니다.  상호 통신은 두 사용자 간에만 가능합니다. 다자 채팅/통화 또는 추가 사용자 추가는 지원되지 않습니다.

다음 각이 true일 때 두 사용자 간에 상호 채팅 또는 통화가 만들어집니다.

- 한 사용자가 Teams를 사용하고 다른 사용자는 비즈니스용 Skype를 사용하는 것입니다.

- 초기 통신을 받는 사람의 모드는 NOT Islands(그렇지 않으면 통신이 동일한 클라이언트에 착륙)입니다. 두 사용자가 동일한 조직에 있는 경우. 페더리된 시나리오에서 보내는 사용자가 Teams를 사용하고 받는 사람이 TeamsOnly 모드가 아닙니다. 

- Teams 사용자에게는 비즈니스용 Skype 계정도 없습니다.

상호 통신 내에서 채팅은 일반 텍스트만 사용할 수 있습니다. 또한 파일 공유 및 화면 공유는 인터팝 채팅 자체에서 *사용할 수 없습니다.* 그러나 인터프 대화의 사용자는 아래 설명된 바와 같이 인터팝 채팅 내에서 수요에 따라 모임을 만들어 파일 및/또는 화면 공유를 쉽게 달성할 수 있습니다.

- Teams 사용자가 화면을 공유하려고 하는 경우 요청 시 Teams 모임이 자동으로 생성되고 해당 모임에 대한 초대 링크가 비즈니스용 Skype 사용자의 클라이언트로 전송됩니다. 링크를 클릭하면 비즈니스용 Skype 사용자가 Teams를 열고 모임에 참가합니다. 이제 두 사용자가 Teams 모임에 참석하고 있으며 필요한 경우 공유할 수 있습니다.

- 비즈니스용 Skype 사용자가 2018 이상에서 클라이언트를 사용하고 콘텐츠를 공유하려고 하는 경우 비즈니스용 Skype 모임이 자동으로 생성되고 해당 모임에 대한 초대 링크가 Teams 사용자의 클라이언트로 전송됩니다. 링크를 클릭하면 Teams 사용자가 비즈니스용 Skype 모임에 참가하려고 합니다. Teams 사용자에게 비즈니스용 Skype 클라이언트가 설치되어 있는 경우 해당 클라이언트가 열리며 사용자가 로그인하라는 메시지가 표시됩니다(아직 로그인하지 않은 경우).  Teams 사용자에게 비즈니스용 Skype 클라이언트가 설치되어 있지 않은 경우 웹 버전을 사용하라는 메시지가 표시됩니다. 두 사용자가 모두 로그인하면 비즈니스용 Skype 모임에 있으며 필요한 경우 공유할 수 있습니다.

### <a name="interop-versus-native-conversation-threads"></a>Interop 및 네이티브 대화 스레드

상호 운영 통신은 네이티브 Teams 대화의 모든 기능을 지원하지 않습니다. Teams 클라이언트는 Teams-to-Teams 및 Teams-to-Skype 비즈니스 통신에 대해 별도의 대화 스레드를 유지 관리합니다. 이러한 대화는 사용자 인터페이스에서 다르게 렌더링됩니다. Interop 스레드는 다음을 통해 일반 네이티브 Teams 스레드와 차별화할 수 있습니다.

- 풍부한 텍스트, 파일/화면 공유, 사용자를 추가할 수 없는 컨트롤이 없습니다.
- 비즈니스용 Skype에 대한 "S"를 표시하는 대상 사용자의 아이콘을 수정합니다.

이러한 차이점은 다음 스크린샷에 표시됩니다.

사용자 G3 테스트와의 네이티브 Teams-To-Teams 대화

![네이티브 Teams-To-Teams 대화를 보여주는 다이어그램](media/teams-upgrade-native-thread.png)

동일한 사용자 G3 테스트와의 상호 대화

![팀 간 대화를 보여주는 다이어그램](media/teams-upgrade-interop-thread.png)

대화 스레드가 만들어지면 해당 형식은 변경되지 않습니다. 만든 후 Teams의 Interop 스레드는 항상 대상 사용자의 비즈니스용 Skype 클라이언트로 라우팅됩니다. 네이티브 스레드는 항상 대상 사용자의 Teams 클라이언트로 라우팅됩니다.  받는 사람의 모드가 변경되면 해당 사용자에게 기존 Teams 스레드가 더 이상 작동하지 않습니다. 다음 스크린샷과 같이 새 네이티브 대화를 시작하는 링크가 있는 메모가 해당 채팅에 표시됩니다.

![비즈니스용 Skype 사용자와 채팅을 보여주는 다이어그램](media/teams-upgrade-chat-with-upgraded-sfb-user.png)

### <a name="presence"></a>현재 상태

주어진 사용자의 현재 상태는 클라이언트를 통해 서비스의 사용자의 활동을 기반으로 합니다. 그러면 다른 사용자가 볼 수 있도록 현재 상태가 게시됩니다.  비즈니스용 Skype 및 Teams는 별도의 클라이언트가 있는 별도의 서비스이기 때문에 각 서비스에는 사용자에 대한 자체 존재 상태가 있습니다.   Teams의 현재 상태 서비스와 비즈니스용 Skype Online 간에도 동기화가 있습니다.  이렇게 하면 한 서비스가 필요한 경우 다른 서비스에서 사용자의 존재를 잠재적으로 게시할 수 있습니다. 

현재 상태 게시 동작은 사용자의 모드를 기반으로 합니다. 세 가지 기본 사례가 있습니다.

- 사용자가 TeamsOnly 모드인 경우 다른 모든 사용자는 사용하는 클라이언트에 관계없이 해당 사용자에 대한 Teams 존재를 볼 수 있습니다.

- 사용자가 비즈니스용 Skype 모드에 있는 경우 다른 모든 사용자는 사용하는 클라이언트에 관계없이 해당 사용자의 비즈니스용 Skype 존재를 볼 수 있습니다.

- 사용자가 제도 모드인 경우 비즈니스용 Skype 및 Teams에 게시된 현재 상태는 독립적이기 때문에 동일한 조직 내의 사용자에게 표시되는 현재 상태는 다른 사용자의 클라이언트에 따라 달라 갑니다. 페더러드 조직의 사용자는 비즈니스용 Skype에 대한 페더리드 트래픽이 비즈니스용 Skype에 기반하기 때문에 비즈니스용 Skype 활동에 따라 해당 사용자의 존재를 볼 수 있습니다.

예를 들어 사용자 A가 섬 모드로 가정합니다. 사용자 A가 Teams에서 활성 상태이지만 비즈니스용 Skype에 로그인되지 않은 경우 다른 사용자는 Teams 클라이언트에서 사용자 A를 활성으로 보지만 비즈니스용 Skype 클라이언트에서 사용자 A를 오프라인으로 볼 수 있습니다. 클라이언트를 실행하지 않는 경우 사용자 A에 도달할 수 없습니다. 


### <a name="federation"></a>페더레이션

비즈니스용 Skype를 사용하여 Teams에서 다른 사용자로 페더전을 수행하려면 Teams 사용자가 비즈니스용 Skype에서 온라인으로 홈으로 돌아와야 합니다. TeamsUpgradePolicy는 들어오는 페더링된 채팅 및 통화에 대한 라우팅을 관리합니다. 페더리드 라우팅 동작은 아일랜드 모드를 제외한 동일한 테넌트 시나리오와 동일합니다. 받는 사람이 제도 모드인 경우:

- 받는 사람이 페더리드 테넌트에 있는 경우 Teams에서 시작된 채팅 및 통화는 비즈니스용 Skype에 있습니다.
- 받는 사람이 동일한 테넌트에 있는 경우 Teams에서 시작된 채팅 및 통화가 Teams에 있습니다.
- 비즈니스용 Skype에서 시작된 채팅 및 통화는 항상 비즈니스용 Skype에 있습니다.

페더리된 채팅은 네이티브 스레드 또는 인터프 스레드일 수 있습니다. 네이티브 대화 스레드와 [Interop을 참조합니다.](#interop-versus-native-conversation-threads)

- 받는 사람 및 보낸 사람이 TeamsOnly 업그레이드 모드인 경우 대화는 모든 풍부한 메시징 및 통화 기능을 포함하는 네이티브 채팅 환경이 됩니다. 자세한 내용은 Teams의 외부(페더리화) 사용자에 대한 네이티브 채팅 환경을 [읽어보아야 합니다.](native-chat-for-external-users.md) 

- 대화 참가자 중 하나가 TeamsOnly 업그레이드 모드가 아닌 경우 대화는 텍스트 전용 메시지와 상호 운영 환경으로 남아 있습니다. 사용자 인터페이스는 사용자가 외부임을 나타내는 메모가 있는 경우를 제외하고 동일한 테넌트 인터팝 스레드와 유사한 방식으로 페더링된 채팅을 노출합니다.

자세한 내용은 [Teams의](manage-external-access.md) 외부 사용자에 대한 Microsoft Teams 및 네이티브 채팅 환경의 외부 액세스 관리를 [참조하세요.](native-chat-for-external-users.md)

### <a name="contacts"></a>연락처

Teams 및 Skype for Business에는 별도의 연락처 목록이 있습니다. 즉, 한 시스템에서 만든 연락처 추가, 제거 및 수정이 다른 시스템에 동기화되지 않습니다. 그러나 비즈니스용 Skype의 연락처는 다음 두 가지 특정 이벤트 중 하나에 대해 발생하는 경우 Teams로 자동으로 복사됩니다. 

- 비즈니스용 Skype Online 사용자의 경우 Teams에 처음으로 로그온하면 비즈니스용 Skype의 연락처가 Teams로 복사됩니다.  비즈니스용 Skype 서버의 프레미스 계정이 있는 사용자는 이 동작을 사용할 수 없습니다.  

- 사용자가 TeamsOnly로 업그레이드된 후(TeamsUpgradePolicy를 할당하거나 Move-CsUser -MoveToTeams를 통해) 다음에 사용자가 Teams에 로그인하면 비즈니스용 Skype의 기존 연락처가 Teams에 이미 있는 기존 연락처와 병합됩니다. 이 동작은 사용자의 비즈니스용 Skype 계정이온-프레미스 또는 온라인에 있는지 여부에 따라 발생합니다. 

두 경우 모두 비즈니스용 Skype에서 Teams로 연락처를 전송하는 것은 비동기적이기 때문에 연락처가 Teams에 표시되기까지 몇 분 정도가 소요될 수 있습니다. 위의 두 이벤트는 복사를 트리거하는 이벤트입니다.  

### <a name="related-links"></a>관련 링크

[비즈니스용 Skype와 함께 Teams를 사용하는 조직에 대한 마이그레이션 및 상호 연동성 지침](migration-interop-guidance-for-teams-with-skype.md) 

[비즈니스용 Skype 서버와 Microsoft 365 또는 Office 365 간에 하이브리드 연결 구성](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[온-프레미스와 클라우드 간에 사용자 이동](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[공존 및 업그레이드 설정 설정](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[MMS(모임 마이그레이션 서비스) 사용](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)