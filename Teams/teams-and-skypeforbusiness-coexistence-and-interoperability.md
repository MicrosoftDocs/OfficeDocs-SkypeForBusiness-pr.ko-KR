---
title: Microsoft Teams 및 비즈니스용 Skype 공존 및 상호 운용성 이해
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 비즈니스용 Skype 및 Microsoft Teams 공존 옵션 및 비즈니스용 Skype Teams 간의 결과 상호 운용성에 대한 세부 정보입니다.
ms.localizationpriority: medium
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
ms.openlocfilehash: 6d1b5604d5b76d0f642fe26a4ec9777060b9d5ef
ms.sourcegitcommit: 9de6b0b03f433e71fe239d292387eed33c11b531
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/13/2022
ms.locfileid: "67657338"
---
# <a name="understand-microsoft-teams-and-skype-for-business-coexistence-and-interoperability"></a>Microsoft Teams 및 비즈니스용 Skype 공존 및 상호 운용성 이해

![프로젝트 정의 단계를 강조하는 업그레이드 경험 다이어그램](media/upgrade-banner-project-definition.png "프로젝트 정의 단계에 중점을 둔 업그레이드 과정의 단계")

이 문서는 업그레이드 과정의 프로젝트 정의 단계의 일부입니다. 스폰서쉽 연합 및 프로젝트 팀을 만들고 프로젝트의 범위, 목표 및 계획을 정의한 후 완료합니다. 계속하기 전에 다음 작업을 완료했는지 확인합니다.

- [프로젝트 관련자 참여](upgrade-enlist-stakeholders.md)
- [프로젝트 범위 정의](./upgrade-define-project-scope.md)

조직에서 현재 비즈니스용 Skype 사용하고 비즈니스용 Skype 함께 Teams를 사용하기 시작했거나 Teams로 업그레이드하기 시작한 경우 두 애플리케이션이 공존하는 방식, 상호 운용 시기 및 방법, 비즈니스용 Skype 최종 업그레이드까지 사용자의 마이그레이션을 관리하는 방법을 이해하는 것이 중요합니다.

> [!Tip]
> [공존 및 상호 운용성에](https://aka.ms/teams-upgrade-coexistence-interop) 대해 알아보려면 다음 세션을 시청하세요.
>
> 또한 업그레이드 계획 및 구현을 시작하도록 설계된 지침, 모범 사례 및 리소스를 공유하는 라이브 대화형 워크샵에 참여할 수 있습니다.
>
> [먼저 업그레이드 세션 계획에](./upgrade-workshops-landing-page.yml) 참가하여 시작합니다.

## <a name="coexistence-of-teams-and-skype-for-business-overview"></a>Teams 공존 및 비즈니스용 Skype 개요

다음 섹션에서는 Teams로 업그레이드할 때 사용할 수 있는 공존 모드와 각 모드에서 제공하는 기능에 대해 설명합니다. 또한 비즈니스용 Skype 클라이언트의 사용자와 Teams 클라이언트의 사용자 간에 발생하는 상호 운용성(interop)과 선택한 공존 모드의 interop 영향을 설명합니다.

Teams는 공동 작업 기능, 채팅, 통화 및 모임 기능을 제공합니다. Teams를 배포하는 방법에 따라 이러한 기능은 지정된 사용자에 대해 비즈니스용 Skype 제공하는 기능과 겹칠 수 있습니다. 기본 모드는 기능이 겹치는 비즈니스용 Skype 함께 Teams를 실행하는 것입니다. 그러나 이러한 기능이 해당 사용자에 대해 겹치지 않도록 설계된 여러 공존 모드(업그레이드 모드라고도 함) 중 하나를 사용자에게 할당할 수 있습니다(이 경우 Teams와 비즈니스용 Skype 간의 상호 운용성을 사용할 수 있음). 예를 들어 복잡한 Enterprise Voice 배포를 통해 온-프레미스 자산에 상당한 비즈니스용 Skype 서버 있지만 사용자가 가능한 한 빨리 최신 모임을 즐기도록 하려면 [모임 우선](meetings-first.md)을 대체 경로로 평가할 수 있습니다.

조직에 적합한 경로를 결정하는 데 도움이 되도록 다음 공존 모드를 검토하는 것이 좋습니다.

> [!Important]
> 비즈니스용 Skype Online이 사용 중지된 후에도 공존 모드가 계속 존재합니다. 그러나 온라인이 있는 사용자는 TeamsOnly 모드만 사용할 수 있습니다. 더 이상 TeamsOnly 이외의 모드를 온라인 홈 사용자에 할당할 수 없습니다.  비즈니스용 Skype Online이 사용 중지되기 전의 경우와 마찬가지로 온-프레미스에 있는 사용자는 *TeamsOnly 이외의* 모드를 할당할 수 있습니다.

### <a name="islands-mode"></a>아일랜드 모드

기본적으로 사용자는 비즈니스용 Skype 함께 Teams를 유사하고 겹치는 기능을 제공하는 두 개의 별도 솔루션으로 실행할 수 있습니다. 기능에는 현재 상태, 채팅, 통화 및 모임이 포함됩니다. Teams 사용자는 팀 및 채널, Microsoft 365의 파일에 대한 액세스 및 애플리케이션과 같은 새로운 공동 작업 기능을 활용할 수도 있습니다.

**아일랜드** 라고 하는 이 공존 모드에서는 각 클라이언트 애플리케이션이 별도의 섬으로 작동합니다. 비즈니스용 Skype 비즈니스용 Skype 대화하고 Teams는 Teams와 대화합니다. 사용자는 항상 두 클라이언트를 모두 실행해야 하며 통신이 시작된 클라이언트에서 기본적으로 통신할 수 있습니다. 따라서 **아일랜드** 모드에서는 상호 운용성이 필요하지 않습니다.

혼동되거나 회귀된 비즈니스용 Skype 환경을 방지하기 위해 비즈니스용 Skype Teams **Islands** 모드에서 처리되지 않는 다음 통합을 처리합니다.

- 외부(페더레이션된) 통신.
- PSTN 음성 서비스 및 음성 응용 프로그램, Office 통합.
- USB 디바이스에 대한 HID 컨트롤입니다.
- 몇 가지 다른 통합.

**전화 시스템은 아일랜드** 모드의 Teams에서 지원되지 않습니다. **아일랜드** 모드는 클라이언트가 비즈니스용 Skype Enterprise Voice 지원하지 않습니다.

> [!Important]
> **아일랜드** 모드에서는 페더레이션된 사용자(조직 외부 사용자)의 모든 메시지와 통화가 비즈니스용 Skype 전달됩니다. **Teams 전용** 모드로 업그레이드하면 조직 외부의 모든 메시지와 통화가 Teams로 전달됩니다.

### <a name="teams-only"></a>Teams만

**Teams 전용** 사용자(*업그레이드된* 사용자라고도 함)는 Teams의 모든 기능에 액세스할 수 있습니다. 업그레이드되지 않은 사용자 또는 외부 당사자가 구성한 비즈니스용 Skype 모임에 참가하도록 비즈니스용 Skype 클라이언트를 유지할 수 있습니다. 업그레이드된 사용자는 Teams와 비즈니스용 Skype 간의 상호 운용성 기능을 사용하여 여전히 비즈니스용 Skype 사용하고 있는 조직의 다른 사용자와 계속 통신할 수 있습니다(비즈니스용 Skype 사용자가 **아일랜드** 모드에 없는 경우). 그러나 업그레이드된 사용자는 비즈니스용 Skype 채팅, 통화 또는 모임을 시작할 수 없습니다.

조직에서 일부 또는 모든 사용자가 Teams를 유일한 커뮤니케이션 및 공동 작업 도구로 사용할 준비가 되면 해당 사용자를 **Teams 전용** 모드로 업그레이드합니다. **Islands** 모드에서 업그레이드하는 경우 업그레이드 프로세스를 시작하기 전에 먼저 조직 전체에서 Teams 채택을 포화시키는 것이 좋습니다. 이 채택은 **아일랜드** 모드가 상호 운용성을 제공하지 않아 통신 시나리오가 끊어지는 것을 방지합니다.

**Teams 전용** 모드에서 Teams는 SIP/Tel 프로토콜의 기본 앱입니다. 통화 또는 채팅을 위해 Outlook에서 사용자의 연락처 카드에 있는 링크는 Teams에서 처리됩니다.

**Teams 전용** 모드로 전환하는 방법에 대한 추가 고려 사항은 [Teams 전용 모드 고려 사항을 참조하세요](teams-only-mode-considerations.md).

![Teams 확인 메시지의 스크린샷.](media/teams-and-skypeforbusiness-coexistence-and-interop-image1.png "사용자가 Teams 전용 사용자로 업그레이드된 후 특수 모드에서 실행되는 클라이언트를 비즈니스용 Skype")

### <a name="skype-for-business-only"></a>비즈니스용 Skype 전용

이 공존 모드에서 사용자는 채팅, 모임 및 통화 기능에 대해 Teams가 아닌 비즈니스용 Skype 유지되며 팀 및 채널에는 Teams를 사용하지 않습니다. 이 모드는 현재 사용할 수 있습니다. 그러나 현재 구현에서는 사용자에 대해 팀 및 채널이 자동으로 꺼지지 않습니다. 이 작업은 앱 설정 정책을 사용하여 팀 및 파일을 숨겨서 수행할 수 있습니다.

이 모드는 Teams의 관리되는 배포를 시작하기 전에 사용자가 빌드된 준비 상태보다 먼저 Teams를 사용하기 시작하지 못하도록 하기 전에 사용할 수 있습니다. 또한 이 모드는 사용자에게 Teams 라이선스가 부여된 경우 비즈니스용 Skype 사용자에 대해 Teams 모임에 인증된 참여를 가능하게 하는 방법입니다.

### <a name="skype-for-business-with-teams-collaboration"></a>Teams 협업을 사용하여 비즈니스용 Skype

비즈니스용 Skype 기존 투자를 계속 사용하는 동안 이 모드를 사용하여 환경에 Teams를 도입할 수 있습니다. 채팅, 통화 및 모임 기능에 대해 비즈니스용 Skype 변경하지 않은 상태로 둡니다. Teams 공동 작업 기능 추가:

- 팀 및 채널.
- Microsoft 365 또는 Office 365 파일에 액세스합니다.
- 응용 프로그램. Teams 통신 기능- 비공개 채팅, 통화 및 모임 예약.

Teams 비공개 채팅, 통화 및 예약 모임은 기본적으로 이 모드에서 해제됩니다.

온-프레미스 또는 하이브리드의 시작점이 비즈니스용 Skype 서버 조직은 사용자에게 통신에 대한 상호 운용성 및 예측 가능성을 제공하고 Teams로 업그레이드할 수 있는 예측 가능한 타임라인을 제공하려는 경우(**아일랜드** 모드의 채택 포화에 의존하는 것이 아니라) 이 모드를 **아일랜드** 모드의 대안으로 고려해야 합니다.

### <a name="skype-for-business-with-teams-collaboration-and-meetings-also-known-as-meetings-first"></a>Teams 협업 및 모임을 사용하여 비즈니스용 Skype( 모임 우선이라고도 함)

이 공존 모드를 사용하여 조직에서 Teams 모임 및 공동 작업 기능의 가용성을 가속화할 수 있습니다. 공존 모드를 사용하면 사용자가 우수한 Teams 모임 환경을 활용할 수 있습니다.

- 좋은 품질.
- 전사 및 번역.
- 배경이 흐리게 표시됩니다.
- 모바일 디바이스 및 브라우저를 비롯한 모든 플랫폼에서 뛰어난 사용자 환경

사용자는 이 모드에서 팀 및 채널 기반 대화에 Teams를 사용하는 것 외에도 Teams를 사용하여 모임을 예약하고 진행합니다. 비공개 채팅 및 통화는 비즈니스용 Skype 유지됩니다. Teams와 비즈니스용 Skype 두 애플리케이션에서 현재 상태 조정, 자동 보류/보류 해제 및 HID 디바이스 지원과 같은 다양한 "더 나은 함께" 기능을 활용할 수 있습니다. 원하는 경우 앱 설정 정책을 사용하여 팀 및 채널을 숨길 수 있습니다.

이 공존 모드는 Enterprise Voice 비즈니스용 Skype 온-프레미스 배포를 사용하는 조직에 특히 유용합니다. 이러한 조직은 Teams로 업그레이드하는 데 다소 시간이 걸릴 수 있으며 가능한 한 빨리 우수한 Teams 모임의 혜택을 원할 수 있습니다.

> [!TIP]
> 비즈니스용 Skype 사용 중인 동안 Teams에서 사용하려는 기능을 기반으로 권장 업그레이드 모드를 식별하려면 [Skype에서 Teams로 업그레이드 마법사를](https://aka.ms/SkypeToTeamsWizard) 활용하세요.

공존 모드, 필수 구성 요소 및 관리에 대한 자세한 내용은 비즈니스용 Skype 및 공존 및 [업그레이드 설정 설정](./setting-your-coexistence-and-upgrade-settings.md)[과 함께 Teams를 사용하는 조직에 대한 마이그레이션 및 상호 운용성 지침을](./migration-interop-guidance-for-teams-with-skype.md) 참조하세요.

|의사 결정 지점 아이콘 |아이콘 정의 |설명 |
|---|---|---|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|의사 결정 지점|<ul><li>조직 및 사용자의 요구에 가장 적합한 공존 모드는 무엇인가요?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next step"/>|다음 단계|<ul><li>업그레이드 여정에 가장 적합한 방법을 선택합니다.</li></ul>|

### <a name="interoperability-of-teams-and-skype-for-business"></a>Teams 및 비즈니스용 Skype 상호 운용성

상호 운용성은 Teams 및 비즈니스용 Skype 동일한 조직의 사용자가 Teams 및 비즈니스용 Skype 간에 통신할 수 있는 기능입니다.

상호 운용성은 수신기의 공존 모드(업그레이드 모드라고도 함)에 의해 제어됩니다. 수신기가 **아일랜드** 모드인 경우 상호 운용성이 없습니다.

> [!Note]
> **Islands**, Teams 및 비즈니스용 Skype 제외한 모든 공존 모드로 배포된 경우 [상호 운용](#interoperability-of-teams-and-skype-for-business)할 수 있으므로 사용자가 서로 채팅하고 통화할 수 있으며 Teams로 업그레이드하는 동안 조직 전체에서 통신이 유동적으로 유지되도록 할 수 있습니다. 공존 모드는 상호 운용성을 제어합니다. 수신기의 공존 모드는 상호 운용성을 사용할 수 있는지 여부를 결정합니다. 예를 들어 수신자가 한 클라이언트(예: Teams)에서만 채팅을 사용할 수 있는 모드에 있는 경우, 초기자가 다른 클라이언트(이 경우 비즈니스용 Skype)를 사용하여 채팅을 시작하는 경우 일반적으로 채팅 상호 운용성을 사용할 수 있습니다. 반면, 수신자가 두 클라이언트(아일랜드 모드)에서 채팅을 사용할 수 있는 모드인 경우 채팅에 상호 운용성을 사용할 수 없습니다. 초기자가 채팅을 시작한 동일한 클라이언트의 수신자가 메시지를 받습니다. 따라서 **아일랜드** 모드에서 적절한 통신을 수행하려면 Teams 채택 포화가 필요합니다. 즉, 모든 사용자가 두 클라이언트를 적극적으로 사용하고 모니터링합니다.

> [!Note]
> **최신 공존 환경을 사용하려면 클라이언트 버전이 사용자의 Office 배포 채널에서 사용 가능한 최신 클라이언트여야 합니다.**

#### <a name="native-interop-and-interop-escalation"></a>네이티브 interop 및 interop 에스컬레이션

interop 환경의 두 가지 유형은 네이티브 및 interop 에스컬레이션입니다.

- _네이티브 interop_ 환경은 사용자가 현재 사용 중인 클라이언트에서 발생합니다. 한 사용자는 비즈니스용 Skype 클라이언트에 있고 다른 하나는 Teams에 있습니다. 네이티브 interop 환경은 통신하기 위해 다른 클라이언트로 이동하지 않습니다. 사용자는 현재 사용 중인 클라이언트에서 대화를 수행할 수 있습니다. 네이티브 interop 환경은 일대일 채팅 및 통화입니다.
- _interop 에스컬레이션_ 환경은 사용자가 고급 작업(예: 데스크톱 공유)을 수행하는 데 도움을 주는 일환으로, 클라이언트가 사용자가 참가하여 해당 모임에서 환경을 계속 진행할 수 있는 모임을 쉽게 만들 수 있음을 의미합니다. 모임은 작업 개시자의 플랫폼에서 만들어집니다. 해당 플랫폼에 없는 사용자 또는 사용자는 모임 참가 링크를 받습니다. 이 링크를 클릭하면 호환되는 클라이언트(구성에 따라 브라우저, 웹앱 또는 전체 클라이언트)에서 모임에 참가합니다. 비즈니스용 Skype Interop 에스컬레이션에는 최근 클라이언트가 필요합니다. 이제 Teams에서 Interop 에스컬레이션을 사용할 수 있습니다. 둘 다 테넌트 내의 상호 운용성 환경 및 페더레이션된 통신 교차 테넌트에서 지원됩니다.

#### <a name="native-interop-experiences"></a>네이티브 interop 환경

이전에 설명한 대로 사용자에게 할당된 공존 모드에 따라 다음과 같은 네이티브 interop 환경을 사용할 수 있습니다.

비즈니스용 Skype 사용자는 Teams 사용자와 일대일로 채팅할 수 있으며 그 반대의 경우도 마찬가지입니다. interop 채팅은 Teams 클라우드 서비스의 일부인 interop 게이트웨이를 통과해야 하며 따라서 온라인만 존재합니다. Interop 채팅은 일반 텍스트입니다. 서식 있는 텍스트 및 이모티콘은 지원되지 않습니다. Teams 및 비즈니스용 Skype 사용자는 대화가 interop 대화라는 알림을 받습니다.

<!--![Screen shot of Interop chat experience from Teams.](media/Interop_chat_experience_from_Teams.png "Interop chat experience from Teams")-->

비즈니스용 Skype 사용자는 Teams 사용자에게 일대일 음성 및 영상 통화를 할 수 있으며 Teams 사용자도 동일한 작업을 수행할 수 있습니다.

<!--![Screen shot of Interop calling experience from Teams.](media/Interop_calling_experience_from_Teams.png "Interop calling experience from Teams")-->

> [!Important]
> 비즈니스용 Skype 온-프레미스 배포를 사용하는 Interop 환경을 사용하려면 온-프레미스 환경이 Teams와 하이브리드 모드에 있어야 합니다. 자세한 내용은 [비즈니스용 Skype 서버 Microsoft 365 또는 Office 365 간의 하이브리드 연결을 구성](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)합니다.

이러한 interop 환경은 **Teams 협업을 사용한 비즈니스용 Skype, Teams 공동 작업** 및 모임 비즈니스용 Skype, **비즈니스용 Skype** 전용 또는 **Teams 전용** 이라는 공존 모드 중 하나가 할당된 사용자 간에 사용할 수 있습니다.  **아일랜드** 모드에서는 사용자에 대한 상호 운용성이 없습니다.

#### <a name="native-interop-experience-limitations"></a>네이티브 interop 환경 제한 사항

프로토콜과 기술의 차이로 인해 모든 기능을 기본적으로 지원할 수 없습니다. 특히 다음 기능은 사용할 수 없습니다.

- Markdown, 서식 있는 텍스트 및 전체 이모티콘 세트는 Teams 또는 비즈니스용 Skype 지원되지 않습니다. Teams 채팅에서 작성 상자의 다른 네이티브 기능은 지원되지 않습니다.
- Teams와 비즈니스용 Skype 간의 화면 공유(데스크톱 또는 앱 공유)는 기본적으로 지원되지 않습니다. 그러나 interop 에스컬레이션을 통해 지원됩니다.
- Teams의 그룹 채팅(다자간 대화)에는 Teams를 사용하는 참가자만 포함될 수 있습니다.
- 비즈니스용 Skype 다자간 메신저 대화(그룹 채팅)는 비즈니스용 Skype 사용하는 참가자만 포함할 수 있습니다. 그러나 비즈니스용 Skype 다중 당사자로의 interop 에스컬레이션을 사용할 수 있습니다.
- 진행 중인 피어 투 피어 음성 또는 화상 통화를 Teams 및 비즈니스용 Skype 사용자와 관련된 다자간 통화로 에스컬레이션하는 것은 지원되지 않습니다.
- 두 당사자 채팅에 대한 파일 전송 또는 Teams에서 비즈니스용 Skype 그룹 채팅의 파일 첨부 파일은 지원되지 않습니다.
- 비즈니스용 Skype 영구 채팅과의 상호 운용성은 없습니다.

이러한 모든 제한 사항(영구 채팅 제외)의 한 가지 해결 방법은 한 사용자가 모임을 시작하고 다른 사용자를 초대하여 모임에 참가하도록 초대하는 것입니다.

이 해결 방법은 interop 에스컬레이션의 기초입니다. 특히 다중 파티로의 화면 공유 및 에스컬레이션은 기본적으로 달성할 수 없지만 interop 에스컬레이션을 통해 지원됩니다.

#### <a name="interop-escalation-experiences"></a>Interop 에스컬레이션 환경

Interop 에스컬레이션은 모임에 대한 관리되는 에스컬레이션으로 네이티브 interop 기능을 보완하는 것으로 구성됩니다. 모임은 어떤 클라이언트를 가지고 있든 관계없이 누구나 사용할 수 있는 풍부한 환경을 제공합니다.

Teams 사용자가 interop 에스컬레이션을 트리거하면 Teams 모임이 만들어집니다. 비즈니스용 Skype 사용자가 트리거하면 비즈니스용 Skype 모임이 만들어집니다. 두 경우 모두 만든 모임은 모임 **지금** 모임이며 사용자의 일정에 반영되지 않습니다.

상대방은 interop 채팅을 통해 모임 참가 링크를 받고 해당 링크를 클릭하여 참가합니다. 비즈니스용 Skype 사용자에게 Teams 계정이 있고 Teams 사용자가 초대한 경우 인증된 모임에 참가합니다. 그렇지 않으면 익명 참가자로 참가합니다. 반대로 Teams 사용자는 거의 항상 인증된 참가자로 비즈니스용 Skype 모임에 참가하는 데 사용할 수 있는 비즈니스용 Skype 계정과 비즈니스용 Skype 클라이언트를 가지고 있지만, Skype 모임 앱을 사용하는 등 익명 참가자로 참가할 수도 있습니다.

모임에 참가한 당사자는 데스크톱 또는 콘텐츠 공유, 파일 공유 또는 전송, 다른 참가자 추가 등 모임에서 지원되는 모든 활동을 수행할 수 있습니다.

#### <a name="interop-escalation-from-skype-for-business"></a>비즈니스용 Skype Interop 에스컬레이션

비즈니스용 Skype Interop 및 interop 에스컬레이션은 월간 C2R의 2019년 7월 빌드에서 업데이트되었습니다. 이전에는 비즈니스용 Skype 원격 당사자가 Teams를 사용하고 있다는 사실을 사전에 인식하지 못했습니다. 세션이 설정된 후 받은 신호에서만 추측했습니다.

응답이 interop 게이트웨이에서 온 것임을 나타내는 신호가 표시되면 상대방이 비즈니스용 Skype 사용하고 있지 않음을 나타내는 노란색 비즈니스 표시줄(배너)이 표시됩니다. 서비스의 발전으로 인해 실제 **Teams 전용** 사용자가 아닌 비즈니스용 Skype 사용자가 클라우드 음성 사서함 서비스 또는 기타 클라우드 음성 서비스에 연결되었을 때 비즈니스 표시줄을 볼 수 있는 가양성도 발생했습니다.

이러한 가양성 방지를 위해 현재 상태 서비스는 이제 상대방이 **Teams 전용** 실제 사용자인 경우 비즈니스용 Skype 클라이언트에 알릴 수 있습니다. 이를 통해 비즈니스용 Skype interop을 만들기 전에 interop 대화를 만들어야 하며 대화 창이 interop에 특정되어야 한다는 것을 인식할 수 있습니다.

![비즈니스용 Skype 사용자와 interop 대화를 만드는 Teams 메시지 스크린샷](media/teams-and-skypeforbusiness-coexistence-and-interop-create-conversation-with-skype-user.png)

예를 들어 비즈니스용 Skype 사용자가 데스크톱을 공유하려는 경우 모임을 시작하고 단계를 안내한다는 알림이 표시됩니다.

![Teams 사용자와의 모임을 시작하는 Teams 메시지의 스크린샷.](media/teams-and-skypeforbusiness-coexistence-and-interop-start-meeting-with-teams-user.png)

한편 Teams 사용자는 모임 링크가 포함된 들어오는 채팅 메시지를 받고 참가 안내를 받습니다.

비즈니스용 Skype 모임으로의 이 에스컬레이션은 테넌트 내 interop 및 테넌트 간 페더레이션 통화 및 채팅 모두에 사용할 수 있습니다. 기본적으로 설정되며 관리자가 프로비전해야 하는 설정은 없습니다.

#### <a name="interop-escalation-from-teams"></a>Teams에서 Interop 에스컬레이션

이제 Teams 사용자가 비즈니스용 Skype 사용자와 테넌트 내 interop 스레드 또는 테넌트 간 interop 페더레이션 스레드에서 데스크톱 공유 단추를 선택하면 Teams에서 Teams로의 Interop 에스컬레이션을 사용할 수 있습니다. Interop 에스컬레이션은 1:1 채팅 대화 또는 1:1 통화에서 지원됩니다.

이 기능은 Windows용 Teams 데스크톱 클라이언트, Mac용 Teams 데스크톱 클라이언트 및 콘텐츠 공유가 지원되는 브라우저의 Teams 웹 클라이언트에서 지원되며 비즈니스용 Skype 클라이언트 버전과 통신합니다.

상호 운용성 스레드 및 페더레이션 상호 운용성 스레드에서 Teams 사용자는 이제 콘텐츠 공유를 시작할 컨트롤(단추)을 했습니다. Teams 사용자가 단추를 선택하면 콘텐츠를 공유하려면 Teams 모임을 시작해야 한다는 것을 알리는 추가 메뉴가 표시됩니다.

사용자가 통화 중이면 Teams 모임에 참가할 때 Teams와 비즈니스용 Skype 간의 현재 통화가 종료될 것임을 경고합니다. 선택하는 경우 수락하기 전에 비즈니스용 Skype 사용자에게 경고할 수 있습니다.

![비즈니스용 Skype 사용자와 모임을 공유하는 Teams 메시지 스크린샷](media/teams-and-skypeforbusiness-coexistence-and-interop-share-meeting-with-skype-user.png)

수락하면 Teams 모임에 포함됩니다. 모임의 공유 트레이에서 공유를 시작해야 합니다.

한편, 비즈니스용 Skype 사용자는 모임에 대한 링크가 포함된 들어오는 채팅 메시지를 수신하고 참가 안내를 받습니다.

Teams 모임에 대한 이러한 에스컬레이션은 테넌트 내 interop 및 테넌트 간 페더레이션 통화 및 채팅 모두에 사용할 수 있습니다. 기본적으로 설정되며 관리자가 프로비전해야 하는 설정은 없습니다. 그러나 관리자가 .로 설정 ``-AllowPrivateMeetNow`` ``CsTeamsMeetingPolicy`` ``$false``하면 사용자에 대해 해제됩니다.

이 문서를 검토한 후 [업그레이드 경험 선택](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md), [마이그레이션 및 상호 운용성 지침](./migration-interop-guidance-for-teams-with-skype.md), [비즈니스용 Skype 공존](coexistence-chat-calls-presence.md), 구현 세부 정보에 대한 [공존 및 업그레이드 설정 설정을 참조하세요](./setting-your-coexistence-and-upgrade-settings.md). 비디오 [: SfB와 Teams 간의 공존 및 상호 운용성 관리](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)

## <a name="technical-details-of-teams-and-skype-for-business-coexistence"></a>Teams 및 비즈니스용 Skype 공존에 대한 기술 세부 정보

다음 섹션에서는 어떤 모드와 어떤 업그레이드 방법을 사용하는지에 관계없이 동일한 조직에서 Teams 및 비즈니스용 Skype 클라이언트를 실행할 때 발생할 수 있는 동작을 요약합니다.

- [모임](#meetings)
- [상호 운용성](#interoperability)
- [Interop 및 네이티브 대화 스레드](#interop-versus-native-conversation-threads)
- [현재 상태](#presence)
- [페더레이션](#federation)
- [연락처](#contacts)

### <a name="meetings"></a>모임

모드에 관계없이 사용자는 초대된 모든 유형의 모임에 비즈니스용 Skype 또는 Teams에 언제든지 참가할 수 있습니다.  그러나 사용자는 모임 유형과 일치하는 해당 클라이언트와 모임에 참가해야 합니다.

- 모임이 Teams 모임인 경우 모든 참가자(TeamsOnly, 아일랜드 또는 비즈니스용 Skype 사용자)는 Teams 클라이언트를 사용하여 모임에 참가합니다. Teams가 설치되지 않은 경우 사용자는 모임에 참가하려고 할 때 웹으로 전송됩니다.

- 모임이 비즈니스용 Skype 모임인 경우 모든 참가자(TeamsOnly, 아일랜드 또는 비즈니스용 Skype 사용자)는 비즈니스용 Skype 클라이언트를 사용하여 모임에 참가합니다. 비즈니스용 Skype 클라이언트가 설치되지 않은 경우 사용자는 웹으로 이동하여 Skype 모임 앱을 통해 조인합니다. 

  경우에 따라 TeamsOnly 모드의 참가자는 익명 사용자로 비즈니스용 Skype Web App 또는 Skype 모임 앱을 사용하여 비즈니스용 Skype 모임에 참가할 수 있습니다. 결국 TeamsOnly 모드의 모든 사용자에 대해 이 사례가 true가 됩니다. 자세한 내용은 [비즈니스용 Skype Online 사용 중지](skype-for-business-online-retirement.md#what-to-expect-post-retirement)를 참조하세요.

모임을 구성할 때 예약되는 모임 유형은 다음 표와 같이 이끌이의 모드를 기반으로 합니다.

| 이끌이 모드    |      동작 |
| :------------------ | :---------------- |
| TeamsOnly, SfbWithTeamsCollabAndMeetings | Teams에서 예약된 모든 모임 비즈니스용 Skype 추가 기능은 Outlook에서 사용할 수 없습니다. |
| SfbWithTeamsCollab, SfbOnly | 비즈니스용 Skype 예약된 모든 모임. Outlook에서는 Teams 추가 기능을 사용할 수 없습니다. |
| 아일랜드 | 기본적으로 모임은 비즈니스용 Skype 또는 Teams에서 예약할 수 있습니다. 두 추가 기능은 모두 Outlook에서 사용할 수 있습니다. 그러나 필요에 따라 아일랜드 사용자는 PreferredMeetingProviderForIslandsMode=Teams를 사용하여 TeamsMeetingPolicy의 인스턴스를 할당하여 항상 Teams에서 모임을 예약하도록 요구할 수 있습니다.|

### <a name="interoperability"></a>상호 운용성

[Teams 및 비즈니스용 Skype 상호 운용성에](#interoperability-of-teams-and-skype-for-business) 위에서 설명한 대로 Teams는 특정 시나리오에서 비즈니스용 Skype 상호 운용성을 지원합니다. Interop 통신은 비즈니스용 Skype 사용자와 Teams 사용자 간의 채팅 또는 통화를 나타냅니다.  Interop 통신은 두 사용자 간에만 가능합니다. 다자간 채팅/통화 또는 추가 사용자 추가는 지원되지 않습니다.

다음 각각이 true이면 두 사용자 간의 interop 채팅 또는 통화가 만들어집니다.

- 한 사용자가 Teams를 사용하고 다른 사용자는 비즈니스용 Skype 사용하고 있습니다.

- 두 사용자가 동일한 조직에 있는 경우 초기 통신 수신자의 모드는 NOT Islands(그렇지 않으면 통신이 동일한 클라이언트에 배치됨)입니다. 페더레이션된 시나리오에서 보내는 사용자는 Teams를 사용하고 받는 사람은 TeamsOnly 모드가 아닙니다.

- Teams 사용자에게 온-프레미스에 비즈니스용 Skype 계정이 없습니다.

interop 통신 내에서 채팅은 일반 텍스트로만 사용됩니다. 또한 *interop 채팅 자체에서는* 파일 공유 및 화면 공유가 불가능합니다. 그러나 interop 대화의 사용자는 아래 설명된 대로 interop 채팅 내에서 주문형 모임을 만들어 파일 및/또는 화면 공유를 쉽게 달성할 수 있습니다.

- Teams 사용자가 화면을 공유하려고 하면 주문형 Teams 모임이 자동으로 만들어지고 해당 모임에 대한 초대 링크가 비즈니스용 Skype 사용자의 클라이언트로 전송됩니다. 링크를 클릭하면 비즈니스용 Skype 사용자가 Teams를 열고 모임에 참가합니다. 이제 두 사용자 모두 Teams 모임에 참가하고 있으며 필요에 따라 공유할 수 있습니다.

- 비즈니스용 Skype 사용자가 2018 이상에서 클라이언트를 사용하고 콘텐츠를 공유하려고 하면 주문형 비즈니스용 Skype 모임이 자동으로 만들어지고 해당 모임에 대한 초대 링크가 Teams 사용자의 클라이언트로 전송됩니다. 링크를 클릭하면 Teams 사용자가 비즈니스용 Skype 모임에 참가하려고 시도합니다. Teams 사용자에게 비즈니스용 Skype 클라이언트가 설치되어 있으면 클라이언트가 열리고 사용자에게 로그인하라는 메시지가 표시됩니다(아직 로그인하지 않은 경우).  Teams 사용자에게 비즈니스용 Skype 클라이언트가 설치되어 있지 않으면 웹 버전을 사용하라는 메시지가 표시됩니다. 두 사용자가 모두 로그인되면 비즈니스용 Skype 모임에 참가하고 필요에 따라 공유할 수 있습니다.

### <a name="interop-versus-native-conversation-threads"></a>Interop 및 네이티브 대화 스레드

interop 통신은 네이티브 Teams 대화의 모든 기능을 지원하지 않으므로 Teams 클라이언트는 Teams 간 및 Teams 간 통신을 위해 별도의 대화 스레드를 유지 관리 비즈니스용 Skype합니다. 이러한 대화는 사용자 인터페이스에서 다르게 렌더링됩니다. Interop 스레드는 다음을 통해 일반 네이티브 Teams 스레드와 구별할 수 있습니다.

- 서식 있는 텍스트, 파일/화면 공유, 사용자를 추가할 수 없는 컨트롤이 없습니다.
- 대상 사용자의 아이콘을 수정하여 비즈니스용 Skype 대한 "S"를 표시합니다.

이러한 차이점은 다음 스크린샷에 표시됩니다.

사용자 G3 테스트와 네이티브 Teams 간 대화

![네이티브 Teams 간 대화를 보여 주는 다이어그램.](media/teams-upgrade-native-thread.png)

동일한 사용자 G3 테스트와의 interop 대화

![interop Teams 간 대화를 보여 주는 다이어그램](media/teams-upgrade-interop-thread.png)

대화 스레드가 만들어지면 해당 형식은 변경되지 않습니다. 일단 만들어지면 Teams의 interop 스레드는 항상 대상 사용자의 비즈니스용 Skype 클라이언트로 라우팅됩니다. 네이티브 스레드는 항상 대상 사용자의 Teams 클라이언트로 라우팅됩니다.  받는 사람 사용자의 모드가 변경되면 해당 사용자에 대한 기존 Teams 스레드가 더 이상 작동하지 않으며 다음 스크린샷과 같이 새 네이티브 대화를 시작하는 링크가 포함된 메모가 해당 채팅에 표시됩니다.

![업그레이드된 비즈니스용 Skype 사용자와의 채팅을 보여 주는 다이어그램](media/teams-upgrade-chat-with-upgraded-sfb-user.png)

### <a name="presence"></a>현재 상태

지정된 사용자의 현재 상태는 클라이언트를 통해 서비스에서 사용자의 활동을 기반으로 합니다. 그러면 다른 사용자가 볼 수 있도록 현재 상태가 게시됩니다.  비즈니스용 Skype 및 Teams는 별도의 클라이언트가 있는 별도의 서비스이므로 각 서비스에는 사용자에 대한 자체의 현재 상태입니다.   Teams와 비즈니스용 Skype Online의 현재 상태 서비스 간에도 동기화가 있습니다.  이렇게 하면 한 서비스가 필요한 경우 다른 서비스에서 사용자의 현재 상태를 게시할 수 있습니다.

현재 상태 게시 동작은 사용자의 모드를 기반으로 합니다. 다음과 같은 세 가지 기본 사례가 있습니다.

- 사용자가 TeamsOnly 모드에 있는 경우 다른 모든 사용자는 사용하는 클라이언트에 관계없이 해당 사용자에 대한 Teams 현재 상태를 볼 수 있습니다.

- 사용자가 비즈니스용 Skype 모드에 있는 경우 다른 모든 사용자는 사용하는 클라이언트에 관계없이 해당 사용자에 대한 비즈니스용 Skype 현재 상태를 볼 수 있습니다.

- 사용자가 아일랜드 모드에 있는 경우 비즈니스용 Skype 및 Teams에 게시된 현재 상태는 독립적이므로 동일한 조직 내의 사용자에게 표시되는 현재 상태는 다른 사용자의 클라이언트에 따라 달라집니다. 페더레이션된 조직의 사용자는 아일랜드 모드 사용자에 대한 페더레이션 트래픽이 비즈니스용 Skype 있기 때문에 비즈니스용 Skype 활동을 기반으로 해당 사용자의 존재를 볼 수 있습니다.

예를 들어 사용자 A가 아일랜드 모드에 있다고 가정합니다. 사용자 A가 Teams에서 활성 상태이지만 비즈니스용 Skype 로그인하지 않은 경우 다른 사용자는 Teams 클라이언트에서 사용자 A를 활성으로 표시하지만 비즈니스용 Skype 클라이언트에서 사용자 A를 오프라인으로 표시합니다. 클라이언트를 실행하지 않는 경우 사용자 A에 연결할 수 없으므로 이는 의도적으로 수행됩니다.


### <a name="federation"></a>페더레이션

비즈니스용 Skype 사용하여 Teams에서 다른 사용자로 페더레이션하려면 Teams 사용자가 비즈니스용 Skype 온라인으로 홈페이지에 있어야 합니다. TeamsUpgradePolicy는 들어오는 페더레이션 채팅 및 통화에 대한 라우팅을 제어합니다. 페더레이션 라우팅 동작은 아일랜드 모드를 제외하고 동일한 테넌트 시나리오의 경우와 동일합니다. 수신자가 아일랜드 모드인 경우:

- Teams에서 시작된 채팅 및 통화는 수신자가 페더레이션된 테넌트에 있는 경우 비즈니스용 Skype.
- 받는 사람이 동일한 테넌트에 있는 경우 Teams에서 시작된 채팅 및 통화가 Teams에 배치됩니다.
- 비즈니스용 Skype 시작된 채팅과 통화는 항상 비즈니스용 Skype.

페더레이션된 채팅은 네이티브 스레드 또는 interop 스레드일 수 있습니다. [Interop 및 네이티브 대화 스레드를 참조하세요](#interop-versus-native-conversation-threads).

- 받는 사람 및 발신자가 TeamsOnly 업그레이드 모드에 있는 경우 대화는 모든 풍부한 메시징 및 통화 기능을 포함하는 네이티브 채팅 환경이 됩니다. 자세한 내용은 [Teams의 외부(페더레이션) 사용자에 대한 네이티브 채팅 환경을](native-chat-for-external-users.md) 읽어보세요.

- 대화 참가자 중 하나가 TeamsOnly 업그레이드 모드가 아닌 경우 대화는 텍스트 전용 메시지와의 interop 환경으로 유지됩니다. 사용자 인터페이스는 사용자가 외부임을 나타내는 메모가 있다는 점을 제외하고 동일한 테넌트 interop 스레드와 비슷한 방식으로 페더레이션된 채팅을 노출합니다.

자세한 내용은 [Microsoft Teams의 외부 액세스 관리 및 Teams의 외부](manage-external-access.md)[(페더레이션된) 사용자에 대한 네이티브 채팅 환경을 참조하세요](native-chat-for-external-users.md).

### <a name="contacts"></a>연락처

팀과 비즈니스용 Skype 별도의 연락처 목록이 있습니다. 즉, 한 시스템에서 수행된 연락처 추가, 제거 및 수정 사항이 다른 시스템과 동기화되지 않습니다. 그러나 두 가지 특정 이벤트 중 하나가 발생하면 비즈니스용 Skype 연락처가 Teams에 자동으로 복사됩니다.

- 모든 비즈니스용 Skype Online 사용자의 경우 Teams에 처음 로그인하면 비즈니스용 Skype 연락처가 Teams로 복사됩니다.  비즈니스용 Skype 서버 온-프레미스 계정이 있는 사용자는 이 동작을 사용할 수 없습니다.

- 사용자가 TeamsOnly로 업그레이드된 후(TeamsUpgradePolicy 할당 또는 Move-CsUser -MoveToTeams를 통해) 다음에 사용자가 Teams에 로그인하면 비즈니스용 Skype 기존 연락처가 Teams에 이미 있는 기존 연락처와 병합됩니다. 이 동작은 사용자가 온-프레미스 또는 온라인에서 TeamsOnly로 이동되었는지 여부에 관계없이 발생합니다.

두 경우 모두 비즈니스용 Skype Teams로의 연락처 전송은 비동기적이므로 연락처가 Teams에 표시되기까지 몇 분 정도 소요될 수 있습니다. 위의 두 이벤트는 복사본을 트리거하는 이벤트입니다.

### <a name="related-links"></a>관련 링크

[Teams를 사용하는 조직을 위한 마이그레이션 및 상호 운용성 지침과 비즈니스용 Skype](migration-interop-guidance-for-teams-with-skype.md)

[비즈니스용 Skype 서버 Microsoft 365 또는 Office 365 간의 하이브리드 연결 구성](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[온-프레미스와 클라우드 간에 사용자 이동](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[공존 및 업그레이드 설정 설정](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy)

[MMS(모임 마이그레이션 서비스) 사용](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
