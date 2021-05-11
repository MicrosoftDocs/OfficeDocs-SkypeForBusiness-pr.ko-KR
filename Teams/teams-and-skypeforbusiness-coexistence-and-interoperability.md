---
title: Microsoft Teams 및 비즈니스용 Skype 상호운용성 이해
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 비즈니스용 Skype 및 Microsoft Teams 옵션의 세부 정보 및 비즈니스용 Skype 상호 Teams.
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
ms.openlocfilehash: 809de40e8c97eefbd3fc1a938e53328c3be0020f
ms.sourcegitcommit: 17ad87556fb8e0de3c498e53f98f951ae3fa526b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/10/2021
ms.locfileid: "52306032"
---
# <a name="understand-microsoft-teams-and-skype-for-business-coexistence-and-interoperability"></a>Microsoft Teams 및 비즈니스용 Skype 상호운용성 이해

![업그레이드 여정 다이어그램, Project 단계 강조](media/upgrade-banner-project-definition.png "업그레이드 단계( 정의 단계에 Project 단계")

이 문서는 업그레이드 Project 정의 단계의 일부입니다. 후원 연대 및 프로젝트 팀을 만든 후 완료하고 프로젝트의 범위, 목표 및 계획을 정의합니다. 계속하기 전에 다음 작업을 완료한지 확인합니다.

- [프로젝트 관계자 인리스트](upgrade-enlist-stakeholders.md)
- [프로젝트 범위 정의](./upgrade-define-project-scope.md)

조직에서 현재 비즈니스용 Skype 사용 중이면 Teams 비즈니스용 Skype Teams 업그레이드를 시작하거나 업그레이드를 시작하려는 경우, 두 애플리케이션이 어떻게 공존하는지, 언제 어떻게 상호 운영하는지, 사용자 마이그레이션을 최종 업그레이드에서 최종 업그레이드로 비즈니스용 Skype Teams.

> [!Tip]
> 다음 세션을 시청하여 공존 및 상호 연동성에 [대해 알아보고자 합니다.](https://aka.ms/teams-upgrade-coexistence-interop)
>
> 또한 업그레이드 계획 및 구현을 시작하도록 설계된 지침, 모범 사례 및 리소스를 공유하는 라이브 대화형 워크샵에 참가할 수 있습니다.
>
> 먼저 [업그레이드 계획 세션에](./upgrade-workshops-landing-page.yml) 참가하여 시작할 수 있습니다.

## <a name="coexistence-of-teams-and-skype-for-business-overview"></a>개요 및 Teams 비즈니스용 Skype 공존

다음 섹션에서는 업그레이드를 업그레이드할 때 사용할 수 있는 공존 모드와 각 Teams 제공하는 기능을 설명합니다. 또한 비즈니스용 클라이언트의 사용자와 Skype 클라이언트의 사용자 간에 발생하는 상호 Teams 상호운용성(interop)과 선택한 공존 모드의 영향을 받는 방법에 대해 설명합니다.

 Teams, 채팅, 통화 및 모임 기능을 제공합니다. 배포하도록 선택하는 방법에 따라 이러한 Teams 해당 사용자에 대해 비즈니스용 Skype 기능과 겹칠 수 있습니다. 기본 모드는 기능과 Teams 함께 비즈니스용 Skype 실행하는 것입니다. 그러나 사용자는 이러한 기능이 해당 사용자에 대해 겹치지 않도록 설계된 여러 공존 모드(업그레이드 모드라고도도)Teams 비즈니스용 Skype 있습니다. 예를 들어 복잡한 비즈니스용 Skype 서버 프레미스 자산이 Enterprise Voice 있지만 사용자가 최신 모임을 최대한 빨리 즐기길 원할 경우 모임 우선을 [](meetings-first.md) 대체 경로로 평가할 수 있습니다.

조직에 적합한 경로를 결정하기 위해 다음 공존 모드를 검토하는 것이 좋습니다.

> [!Important]
> 공존 모드는 2021년 7월 31일 비즈니스용 Skype 온라인을 사용 중지한 후에도 계속 존재하지만, 프레미스가 배포된 조직에만 비즈니스용 Skype 서버. 사용 중지 직전에 프레미스 배포에 있는 사용자에게 TeamsOnly 외의 모든 모드를 할당할 수 있습니다. 그러나 온라인 사용 중지 후 비즈니스용 Skype 클라우드에 있는 사용자는 TeamsOnly일 수 있습니다.

### <a name="islands-mode"></a>섬 모드

기본적으로 사용자는 유사하고 Teams 기능을 제공하는 두 개의 별도 비즈니스용 Skype 솔루션과 함께 실행될 수 있습니다. 기능에는 현재 상태, 채팅, 통화 및 모임이 포함됩니다. Teams 사용자들은 팀 및 채널과 같은 새로운 공동 작업 기능, Microsoft 365 또는 애플리케이션의 파일에 Office 365 수 있습니다.

이 공존 **모드에서는 Islands라는** 각 클라이언트 애플리케이션이 별도 섬으로 작동합니다. 비즈니스용 Skype 대화를 비즈니스용 Skype, Teams 대화를 Teams. 사용자는 두 클라이언트를 모두 실행해야 하고 통신이 시작된 클라이언트에서 기본적으로 통신할 수 있습니다. 따라서 섬 모드에서 상호 연동성이 **필요하지** 않습니다.

혼란스럽거나 회귀된 비즈니스용 Skype 방지하기 위해 비즈니스용 Skype 섬 모드에서 처리되지 않는 다음 통합을 Teams **처리합니다.**

- 외부(페더리화) 통신.
- PSTN 음성 서비스 및 음성 애플리케이션, Office 통합합니다.
- USB 디바이스에 대한 HID 컨트롤입니다.
- 다른 몇 가지 통합.  

전화 시스템 아일랜드 모드에서는 Teams **지원되지** 않습니다. **섬 모드는** 클라이언트가 Enterprise Voice 지원하지 비즈니스용 Skype.

> [!Important]
> 아일랜드 **모드에서** 페더리드 사용자(조직 외부 사용자)의 모든 메시지와 통화가 비즈니스용 Skype. Teams **전용** 모드로 업그레이드한 후 조직 외부의 모든 메시지와 통화가 Teams.

> [!Tip]
> 비즈니스용 Skype 온라인 고객이 권장하는 경로는  기본 제도 모드로 시작하고, 조직에서 Teams 채도 포화 상태로 이동한 다음 빠르게 Teams 전용 모드로 **이동하는** 것입니다. 프레미스 및 하이브리드 고객, 특히 복잡한 고객은  비즈니스용 Skype Teams 공동 작업 모드를 시작점으로 배포하고,  비즈니스용 Skype **Teams** 모임 모드(즉, 모임 우선)를 Teams 조직에서 채택할 준비가 된 Teams 모드로  진행하는 것이 Teams.

### <a name="teams-only"></a>Teams 전용

Teams  사용자(업그레이드된 사용자라고도도  하는 사용자)는 해당 사용자에 있는 모든 기능에 Teams. 업그레이드되지 않은 비즈니스용 Skype 외부 당사자가 구성한 비즈니스용 Skype 모임에 참가할 수 있는 클라이언트를 유지할 수 있습니다. 업그레이드된 사용자는 여전히 비즈니스용 Skype 다른 사용자와 계속 통신할 수 있습니다(Teams 비즈니스용 Skype 비즈니스용 Skype 사용자가 아일랜드 모드가 아닌 경우).  그러나 업그레이드된 사용자는 채팅, 통화 또는 비즈니스용 Skype 시작할 수 없습니다.

조직에서 일부 또는 모든 사용자가 통신 및 공동 작업 도구로 Teams 준비가 되자마자 해당 사용자를 Teams **모드로** 업그레이드합니다. 제도 모드에서 업그레이드하는  경우 업그레이드 프로세스를 시작하기 전에 먼저 조직 전체에 Teams 포화하는 것이 좋습니다. 이 채택은 상호 연동성을 제공하지 않는 **제도** 모드로 인해 통신 시나리오가 손상되지 않도록 방지합니다.

전용 **Teams 경우** Teams SIP/Tel 프로토콜의 기본 앱입니다. 통화 또는 채팅에 대한 사용자의 Outlook 대화 카드의 링크는 Teams.

전용 모드로 이동하는  Teams 추가 고려 사항은 Teams 모드 고려 사항을 [참조합니다.](teams-only-mode-considerations.md)

![확인 메시지의 Teams 스크린샷](media/teams-and-skypeforbusiness-coexistence-and-interop-image1.png "비즈니스용 Skype 전용 사용자로 업그레이드한 후 특수 모드에서 Teams 클라이언트")

### <a name="skype-for-business-only"></a>비즈니스용 Skype 전용

이 공존 모드에서는 채팅, 비즈니스용 Skype, Teams 기능을 사용할 수 없는 상태로 유지하며 팀 및 채널에 Teams 사용하지 않습니다. 이 모드는 오늘 사용할 수 있습니다. 그러나 현재 구현에서는 사용자에 대해 팀 및 채널이 자동으로 해제되지 않습니다. 앱 설정 정책을 사용하여 팀 및 파일을 숨길 수 있습니다.

이 모드는 관리되는 배포를 시작하기 전에 사용할 수 Teams 준비를 미리 Teams 시작할 수 없습니다. 또한 이 모드는 사용자에 대한 라이선스가 부여된 Teams 사용자에 대한 비즈니스용 Skype 인증된 참여를 사용하도록 Teams.

### <a name="skype-for-business-with-teams-collaboration"></a>비즈니스용 Skype 공동 작업 Teams 사용

이 모드를 사용하여 Teams 기존 투자를 계속 사용하는 동안 환경에 비즈니스용 Skype. 채팅비즈니스용 Skype 통화 및 모임 기능에 대해 다른 기능을 그대로 떠날 수 있습니다. 공동 작업 Teams 추가합니다.

- Teams 및 채널입니다.
- 파일 또는 Microsoft 365 파일에 Office 365.
- 애플리케이션. Teams 채팅, 통화 및 모임을 계획하는 통신 기능을 제공합니다.

Teams 채팅, 통화 및 모임 계획은 기본적으로 이 모드에서 해제됩니다.

프레미스 또는 비즈니스용 Skype 서버 시작 지점이 있는 조직은 사용자에게 통신에  대한 상호 운영성과 예측성을 제공하려는 경우 이 모드를 아일랜드 모드의 대안으로 고려해야 합니다(섬 모드에서 채택 포화에 대한 Teams) 예측 가능한 타임라인을 갖는 것이 좋습니다. 

### <a name="skype-for-business-with-teams-collaboration-and-meetings-also-known-as-meetings-first"></a>비즈니스용 Skype Teams 공동 작업 및 모임을 사용할 수 있습니다.

이 공존 모드를 사용하여 조직의 Teams 공동 작업 기능의 가용성을 가속화합니다. 공존 모드를 사용하면 사용자가 우수한 모임 환경을 Teams 수 있습니다.

- 좋은 품질.
- 전사 및 번역.
- 배경 흐림.
- 모바일 장치 및 브라우저를 비롯한 모든 플랫폼에서 뛰어난 사용자 환경.

이 모드에서는 팀 및 Teams 채널 기반 대화에 대한 사용과 함께 사용자가 모임을 예약하고 Teams 수 있습니다. 개인 채팅 및 통화는 계속 비즈니스용 Skype. Teams 비즈니스용 Skype 상태 조정, 자동 보류/보류 및 HID 디바이스 지원과 같은 다양한 "더 나은 함께" 기능의 이점을 제공합니다. 앱 설정 정책을 사용하여 원하는 경우 팀 및 채널을 숨길 수 있습니다.

이 공존 모드는 비즈니스용 Skype 프레미스와 함께 비즈니스용 Skype 조직에 Enterprise Voice. 이러한 조직은 업그레이드하는 데 시간이 다소 걸릴 Teams 가능한 한 빨리 우수한 Teams 혜택을 원할 수 있습니다.

> [!TIP]
> 사용 중일 때 사용하려는 기능에 따라 권장 업그레이드 모드를 식별하려면 Teams 비즈니스용 Skype 업그레이드 마법사를 Skype Teams [활용합니다.](https://aka.ms/SkypeToTeamsWizard)

공존 모드, 전제 구성 및 관리에 대한 자세한 내용은 공유 및 Teams 및 비즈니스용 Skype 및 업그레이드 설정과 함께 조직에 대한 마이그레이션 [및 상호운용성](./migration-interop-guidance-for-teams-with-skype.md) 지침을 [참조하세요.](./setting-your-coexistence-and-upgrade-settings.md)

|의사 결정점 아이콘 |아이콘 정의 |설명 |
|---|---|---|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|결정 지점|<ul><li>조직 및 사용자의 요구에 가장 적합한 공존 모드는 무엇입니까?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next step"/>|다음 단계|<ul><li>업그레이드 여정에 가장 적합한 방법을 선택하세요.</li></ul>|

### <a name="interoperability-of-teams-and-skype-for-business"></a>Teams 및 비즈니스용 Skype

상호 운영성은 동일한 조직의 Teams 비즈니스용 Skype 사용자와 사용자 간 통신할 Teams 비즈니스용 Skype.

상호 운영성은 수신기의 공존 모드(업그레이드 모드라고도 합니다)에 의해 관리됩니다. 수신기가 섬 모드에 있는 경우 상호 **연동성이** 없습니다.

> [!Note]
> **섬을** 제외한 모든 공존 모드로 배포되는 경우 Teams 및 비즈니스용 Skype [](#interoperability-of-teams-and-skype-for-business)상호 작동할 수 있으므로 사용자가 채팅하고 통화할 수 있으며 업그레이드를 진행하는 동안 조직 전체에서 통신이 유동적으로 유지될 수 Teams. 공존 모드는 상호 연동성을 관리합니다. 수신기의 공존 모드는 상호 연동성을 사용할 수 있는지 여부를 결정합니다. 예를 들어 수신기가 한 클라이언트에서만 채팅을 사용할 수 있는 모드인 경우(예: Teams) 시작자가 다른 클라이언트를 사용하여 채팅을 시작하는 경우 채팅 상호 비즈니스용 Skype 사용할 수 있습니다. 반면 수신기가 두 클라이언트(섬 모드)에서 채팅을 사용할 수 있는 모드에 있는 경우 채팅에 상호 가동성을 사용할 수 없습니다. 이 메시지는 시작자가 채팅을 시작한 동일한 클라이언트에서 받는 사람에 의해 수신됩니다. 따라서 제도 모드에서 적절한 **통신을** 위해서는 Teams 채도가 필요합니다. 즉, 모든 사용자가 두 클라이언트를 적극적으로 사용하고 모니터링합니다.

> [!Note]
> **최신 공존 환경을 사용하려면 클라이언트 버전이 사용자의 배포 채널에서 사용 가능한 최신 Office 있어야 합니다.**

#### <a name="native-interop-and-interop-escalation"></a>네이티브 interop 및 interop 에스컬레이터

네이티브 및 인터팝 에스컬레이터에는 두 가지 유형의 상호프 환경이 있습니다.

- 사용자가 현재 사용하고 있는 클라이언트에서 네이티브 _interop_ 환경이 발생합니다. 한 사용자가 비즈니스용 Skype 클라이언트에 Teams. 네이티브 인터팝 환경은 통신을 위해 다른 클라이언트로 연결되지 않습니다. 사용자는 현재 사용 중인 클라이언트에서 대화를 진행할 수 있습니다. 네이티브 인터팝 환경은 일대일 채팅 및 통화입니다.
- _상호 운영 에스컬레이터_ 환경은 사용자가 데스크톱 공유와 같은 고급 작업을 수행하는 데 도움이 되는 일부로, 클라이언트는 사용자가 참가하여 해당 모임의 환경을 계속할 수 있도록 모임을 쉽게 만들 수 있습니다. 모임은 작업의 시작자 플랫폼에서 만들어집니다. 해당 플랫폼에 없는 사용자 또는 사용자는 모임 참가 링크를 수신합니다. 이 링크를 클릭하면 호환되는 클라이언트(브라우저, 웹앱 또는 전체 클라이언트)에서 모임에 조인됩니다(구성에 따라). 클라이언트에서 상호 비즈니스용 Skype 클라이언트가 필요합니다. 이제 Teams 인터로프 에스컬레이터를 사용할 수 있습니다. 둘 다 테넌트 내 및 페더리드 통신 교차 테넌트에 대해 상호 연동성 환경에서 지원됩니다.

#### <a name="native-interop-experiences"></a>네이티브 인터팝 환경

사용자에게 할당된 공존 모드(이전에 설명한 바와 같이)에 따라 다음 네이티브 인터프 환경을 사용할 수 있습니다.

비즈니스용 Skype 사용자와 일대일 채팅을 Teams 수 있습니다. 그 반대의 경우도 마찬가지입니다. 인터팝 채팅은 클라우드 서비스의 일부인 Teams 게이트웨이를 통과해야 합니다(따라서 온라인에만 존재). 대화형 채팅은 일반 텍스트입니다. 풍부한 텍스트와 이모티콘은 지원되지 않습니다. 사용자 Teams 및 비즈니스용 Skype 대화가 상호 대화인 것으로 알림을 습니다.

<!--![Screen shot of Interop chat experience from Teams](media/Interop_chat_experience_from_Teams.png "Interop chat experience from Teams")-->

비즈니스용 Skype 사용자가 일대일 음성 및 화상 통화를 할 수 Teams 사용자가 동일한 작업을 Teams 수 있습니다.

<!--![Screen shot of Interop calling experience from Teams](media/Interop_calling_experience_from_Teams.png "Interop calling experience from Teams")-->

> [!Important]
> 프레미스 배포와의 상호 비즈니스용 Skype 프레미스 환경이 하이브리드 모드인 Microsoft 365 Office 365 비즈니스용 Skype. 자세한 내용은 마이그레이션 및 상호 [연동성 지침을 참조하세요.](./migration-interop-guidance-for-teams-with-skype.md)

이러한 상호 작업 환경은 다음 공동 작업 모드 중 하나를 할당한 사용자 간에 사용할 수 있습니다.  비즈니스용 Skype 공동 작업과 Teams 비즈니스용 Skype Teams 및 비즈니스용 Skype 전용 또는 Teams **있습니다.** 섬 모드에서는 사용자에게 상호 **연동성이** 없습니다.

#### <a name="native-interop-experience-limitations"></a>네이티브 인터팝 환경 제한 사항

프로토콜과 기술의 차이로 인하여 모든 기능을 기본적으로 지원할 수 없습니다. 특히 다음 기능을 사용할 수 없습니다.

- Markdown, rich text 및 전체 이모티콘 집합은 Teams 또는 비즈니스용 Skype. 채팅의 작성 상자의 Teams 다른 네이티브 기능은 지원되지 않습니다.
- 화면 공유(데스크톱 또는 앱 공유) Teams 및 비즈니스용 Skype 기본적으로 지원되지 않습니다. 그러나 인터프 에스컬레이터를 통해 지원됩니다.
- 그룹 채팅(다중 파티 대화)은 Teams 그룹 채팅을 사용하는 참가자만 포함할 수 Teams.
- 그룹의 여러 파티 IM 대화(그룹 채팅)는 비즈니스용 Skype 대화를 사용하는 참가자만 포함할 수 비즈니스용 Skype. 그러나 다중 파티로의 상호프 에스컬레이터는 비즈니스용 Skype.
- 지속적인 피어 투 피어 음성 또는 비디오 통화를 여러 파티 통화로 에스컬링하여 사용자와 사용자 Teams 비즈니스용 Skype 모두 지원되지 않습니다.
- 양자 채팅에 대한 파일 전송 또는 그룹 채팅에서 파일 Teams 비즈니스용 Skype 파일 전송은 지원되지 않습니다.
- 영구 채팅과 상호 비즈니스용 Skype 없습니다.

이러한 모든 제한 사항(영구 채팅 제외)의 경우 한 사용자가 모임을 시작하고 다른 사용자를 초대하여 모임에 참가하도록 초대할 수 있습니다.

이 해결은 상호 에스컬레이터의 기본입니다. 특히 다중파트로 화면 공유 및 에스컬레이터는 기본적으로 달성할 수 없지만 상호 에스컬레이터를 통해 지원됩니다.

#### <a name="interop-escalation-experiences"></a>상호 에스컬레이터 환경

Interop 에스컬레이터는 관리되는 에스컬레이터를 통해 모임에 대한 네이티브 인터로프 기능을 보완하는 것으로 구성됩니다. 모임은 어떤 클라이언트에 관계 없이 누구나 사용할 수 있는 풍부한 환경을 제공합니다.

사용자에 의해 인터팝 에스컬레이터가 트리거되면 Teams 모임이 Teams 생성됩니다. 사용자에 의해 트리거되면 비즈니스용 Skype 모임이 비즈니스용 Skype 생성됩니다. 두 경우 모두 만든 모임은 모임 현재 모임입니다. 이 모임은 사용자의 일정에 반영되지 않습니다. 

다른 파티는 상호 채팅을 통해 모임 조인 링크를 수신하고 해당 링크를 클릭하여 조인합니다. 사용자 비즈니스용 Skype 계정이 Teams 사용자가 초대한 Teams 인증된 모임에 참가합니다. 그렇지 않으면 익명 참가자로 참가합니다. 반대로 Teams 사용자는 거의 항상 비즈니스용 Skype 및 비즈니스용 Skype 클라이언트를 사용하여 인증된 비즈니스용 Skype 모임에 참가할 수 있지만 익명 참가자로 참가할 수도 있습니다(예: Skype 모임 앱 사용).

당사자가 모임에 참가하면 데스크톱 또는 콘텐츠 공유, 파일 공유 또는 전송, 다른 참가자 추가 등 모임에서 지원되는 모든 활동을 할 수 있습니다.

#### <a name="interop-escalation-from-skype-for-business"></a>에스컬레이터에서 비즈니스용 Skype

월간 C2R의 2019년 7월 빌드에서 비즈니스용 Skype 인터오프 에스컬레이터가 업데이트되었습니다. 이전에는 비즈니스용 Skype 원격 파티가 사용 중이었다는 사전 인식이 Teams. 세션이 설정된 후에 수신된 신호에서만 해당 것으로 나타날 수 있습니다.

신호가 응답이 인터프 게이트웨이에서(또는 통과)되었음을 나타내면 다른 사용자가 응답을 사용하지 않았다는 것을 나타내는 노란색 비즈니스 표시줄(배너)을 비즈니스용 Skype. 서비스의 발전으로 인해 사용자가 실제 사용자만이 아닌 비즈니스용 Skype 서비스 또는 기타 클라우드 음성 서비스에 연결될 때 비즈니스 클라우드 음성 사서함 표시줄을 볼 수 Teams **결과로** 이어졌습니다.

이러한 거짓 긍정을 방지하기 위해 현재 상태 서비스는 이제 다른 비즈니스용 Skype 사용자만 Teams 클라이언트에 **알릴** 것입니다. 이렇게 하면 비즈니스용 Skype 만들기보다 먼저 상호프 대화를 만들어야 하며 대화 창은 상호op에 특정해야 하다는 것을 인식할 수 있습니다.

![사용자와 Teams 대화를 만들 수 있는 비즈니스용 Skype 스크린샷](media/teams-and-skypeforbusiness-coexistence-and-interop-create-conversation-with-skype-user.png)

예를 비즈니스용 Skype 사용자가 데스크톱을 공유하려는 경우 모임을 시작하고 단계를 안내합니다.

![Teams 사용자와 모임을 시작하는 Teams 스크린샷](media/teams-and-skypeforbusiness-coexistence-and-interop-start-meeting-with-teams-user.png)

한편, Teams 사용자가 모임에 대한 링크가 있는 들어오는 채팅 메시지를 수신하고 참가하도록 안내됩니다.

이 에스컬레이터를 비즈니스용 Skype 테넌트 인터팝 및 테넌트 간 페더레이터 통화 및 채팅 모두에서 사용할 수 있습니다. 기본적으로 설정되어 있으며 관리자가 프로비전해야 하는 설정이 없습니다.

#### <a name="interop-escalation-from-teams"></a>에스컬레이터에서 Teams

이제 Teams Teams 사용자와의 테넌트 내 Teams 스레드에서 데스크톱 공유 단추를 선택하거나 테넌트 간 비즈니스용 Skype 페더링 스레드에서 데스크톱 공유 단추를 선택할 때 Teams 모임으로 상호 에스컬레이터를 사용할 수 있습니다. Interop 에스컬레이터는 1:1 채팅 대화 또는 1:1 통화에서 지원됩니다.

이 기능은 Teams 클라이언트 버전과 통신하는 동안 Windows Mac용 Teams 데스크톱 클라이언트 및 콘텐츠 공유가 지원되는 브라우저의 Teams 웹 클라이언트에서 지원되는 비즈니스용 Skype 지원됩니다.

상호 실행성 스레드 및 페더링 상호 연동성 스레드에서 Teams 사용자에 이제 콘텐츠 공유를 시작하는 컨트롤(단추)이 있습니다. 사용자가 Teams 단추를 선택하면 콘텐츠를 공유하려면 모임을 시작해야 하도록 알리는 추가 메뉴가 Teams 표시됩니다.

사용자가 통화 중이면 메뉴에서 사용자 모임에 Teams 비즈니스용 Skype 통화가 종료될 Teams 경고합니다. 선택한 경우 수락하기 전에 비즈니스용 Skype 경고할 수 있습니다.

![Teams 사용자와 모임을 공유하기 위한 비즈니스용 Skype 스크린샷](media/teams-and-skypeforbusiness-coexistence-and-interop-share-meeting-with-skype-user.png)

수락하면 모임에 Teams 합니다. 모임의 공유 트레이에서 공유를 시작해야 합니다.

한편, 비즈니스용 Skype 사용자가 모임에 대한 링크가 있는 들어오는 채팅 메시지를 수신하고 참가하도록 안내됩니다.

이 에스컬레이터는 Teams 테넌트 내 페더레이터 통화 및 채팅 모두에서 사용할 수 있습니다. 기본적으로 설정되어 있으며 관리자가 프로비전해야 하는 설정이 없습니다. 그러나 관리자가 에 를 설정하는 경우 사용자에 대해 ``-AllowPrivateMeetNow`` ``CsTeamsMeetingPolicy`` ``$false`` 해제됩니다.

이 문서를 검토한 후 업그레이드 여정 [선택,](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)마이그레이션 및 [](coexistence-chat-calls-presence.md)상호 운영성 [지침,](./migration-interop-guidance-for-teams-with-skype.md)비즈니스용 Skype [](./setting-your-coexistence-and-upgrade-settings.md) 공존 및 구현 세부 정보를 위한 업그레이드 설정을 참조하세요. 또한 비디오: [SfB와 SfB](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11) 간의 공존 및 상호 운영성 관리 Teams

## <a name="technical-details-of-teams-and-skype-for-business-coexistence"></a>공존성 및 Teams 기술 비즈니스용 Skype 세부 정보

다음 섹션에서는 사용 중인 모드와 업그레이드 방법에 관계없이 동일한 조직에서 Teams 비즈니스용 Skype 클라이언트를 실행하는 경우 경험할 수 있는 동작을 요약합니다.

- [모임](#meetings)
- [상호 연동성](#interoperability)
- [Interop 및 네이티브 대화 스레드](#interop-versus-native-conversation-threads)
- [현재 상태](#presence)
- [페더레이션](#federation)
- [연락처](#contacts)

### <a name="meetings"></a>모임

모드에 관계 없이 사용자는 항상 초대된 모든 유형의 모임에 참가할 수 있습니다. 이 모임이 비즈니스용 Skype 또는 Teams.  그러나 사용자는 모임 유형과 일치하는 해당 클라이언트로 모임에 참가해야 합니다.

- 모임이 Teams 모든 참가자(TeamsOnly, Islands 또는 비즈니스용 Skype 사용자)는 Teams 클라이언트를 사용하여 모임에 참가합니다. Teams 설치되지 않은 경우 사용자는 모임에 참가하려고 할 때 웹으로 연결됩니다.

- 모임이 비즈니스용 Skype 모든 참가자(TeamsOnly, Islands 또는 비즈니스용 Skype 사용자)는 비즈니스용 Skype 클라이언트를 사용하여 모임에 참가합니다. 비즈니스용 Skype 클라이언트가 설치되어 있지 않은 경우 사용자는 웹으로 연결하여 앱을 통해 Skype 모임 합니다.

모임을 구성할 때 예약되는 모임 유형은 다음 표와 같이 이끌이의 모드를 기반으로 합니다.

| 이끌이 모드    |      동작 |
| :------------------ | :---------------- |
| TeamsOnly, SfbWithTeamsCollabAndMeetings |    예약된 모든 Teams. 비즈니스용 Skype 추가 기능을 사용할 수 Outlook. | 
| SfbWithTeamsCollab, SfbOnly   | 모든 모임이 비즈니스용 Skype. Teams 추가 기능을 사용할 수 Outlook. | 
| 아일랜드 | 기본적으로 모임은 비즈니스용 Skype 또는 Teams. 두 추가 기능을 모두 Outlook. Teams 그러나 선택적으로 섬의 사용자가 항상 PreferredMeetingProviderForIslandsMode=Teams TeamsMeetingPolicy 인스턴스를 할당하여 Teams.| 


### <a name="interoperability"></a>상호 연동성

위에서 설명한 [](#interoperability-of-teams-and-skype-for-business)대로 Teams 및 비즈니스용 Skype 상호 Teams 시나리오에서 비즈니스용 Skype 상호 비즈니스용 Skype 지원합니다. Interop 통신은 사용자와 비즈니스용 Skype 사용자 간에 채팅 또는 Teams 참조합니다.  상호 통신은 두 사용자 간에만 가능합니다. 다자 채팅/통화 또는 추가 사용자 추가는 지원되지 않습니다.

다음 각이 true일 때 두 사용자 간에 상호 채팅 또는 통화가 만들어집니다.

- 한 사용자가 Teams 사용하고 다른 사용자는 비즈니스용 Skype.

- 초기 통신을 받는 사람의 모드는 NOT Islands(그렇지 않으면 통신이 동일한 클라이언트에 착륙)입니다. 두 사용자가 동일한 조직에 있는 경우. 페더리된 시나리오에서 보내는 Teams 사용 중이고 받는 사람이 TeamsOnly 모드가 아닙니다. 

- 또한 Teams 사용자에게는 비즈니스용 Skype 계정이 없습니다.

상호 통신 내에서 채팅은 일반 텍스트만 사용할 수 있습니다. 또한 파일 공유 및 화면 공유는 인터팝 채팅 자체에서 *사용할 수 없습니다.* 그러나 인터프 대화의 사용자는 아래 설명된 바와 같이 인터팝 채팅 내에서 수요에 따라 모임을 만들어 파일 및/또는 화면 공유를 쉽게 달성할 수 있습니다.

- 사용자가 Teams 공유를 시도하면 요청 시 Teams 모임이 자동으로 생성되고 해당 모임에 대한 초대 링크가 비즈니스용 Skype 클라이언트로 전송됩니다. 링크를 클릭하면 비즈니스용 Skype 사용자가 Teams 열고 모임에 참가합니다. 이제 두 사용자 모두 Teams 모임에 참석하고 있으며 필요한 경우 공유할 수 있습니다.

- 비즈니스용 Skype 사용자가 2018년 이상에서 클라이언트를 사용하고 콘텐츠를 공유하려고 시도하는 경우 요청 시 비즈니스용 Skype 모임이 자동으로 생성되고 해당 모임에 대한 초대 Teams 사용자의 클라이언트로 전송됩니다. 링크를 클릭하면 사용자가 Teams 모임에 참가하려고 비즈니스용 Skype 합니다. Teams 클라이언트가 비즈니스용 Skype 있는 경우 해당 클라이언트가 열리며 사용자가 로그인하라는 메시지가 표시됩니다(아직 로그인하지 않은 경우).  Teams 클라이언트가 비즈니스용 Skype 없는 경우 웹 버전을 사용하라는 메시지가 표시됩니다. 두 사용자가 로그인하면 모임에 비즈니스용 Skype 있으며 필요한 경우 공유할 수 있습니다.

### <a name="interop-versus-native-conversation-threads"></a>Interop 및 네이티브 대화 스레드

상호 운영 통신은 네이티브 대화의 모든 기능을 Teams 지원하지 Teams 클라이언트는 Teams Teams 및 Teams 비즈니스용 Skype 통신을 유지 관리합니다. 이러한 대화는 사용자 인터페이스에서 다르게 렌더링됩니다. Interop 스레드는 다음을 통해 일반 네이티브 스레드와 Teams 수 있습니다.

- 풍부한 텍스트, 파일/화면 공유, 사용자를 추가할 수 없는 컨트롤이 없습니다.
- 대상 사용자의 아이콘에 대한 "S"를 표시하는 수정 비즈니스용 Skype.

이러한 차이점은 다음 스크린샷에 표시됩니다.

사용자 Teams 테스트와 Teams 기본 대화

![네이티브 Teams 대화를 Teams 다이어그램](media/teams-upgrade-native-thread.png)

동일한 사용자 G3 테스트와의 상호 대화

![인터팝 Teams 대화를 Teams 다이어그램](media/teams-upgrade-interop-thread.png)

대화 스레드가 만들어지면 해당 형식은 변경되지 않습니다. 만든 후, Teams 인터프 스레드는 항상 대상 사용자의 클라이언트로 비즈니스용 Skype 합니다. 네이티브 스레드는 항상 대상 사용자의 클라이언트로 Teams 합니다.  받는 사람의 모드가 변경되면 해당 Teams 스레드가 더 이상 작동하지 않습니다. 다음 스크린샷과 같이 새 네이티브 대화를 시작하는 링크가 있는 메모가 해당 채팅에 표시됩니다.

![업그레이드된 사용자와 채팅을 보여 비즈니스용 Skype 다이어그램](media/teams-upgrade-chat-with-upgraded-sfb-user.png)

### <a name="presence"></a>현재 상태

주어진 사용자의 현재 상태는 클라이언트를 통해 서비스의 사용자의 활동을 기반으로 합니다. 그러면 다른 사용자가 볼 수 있도록 현재 상태가 게시됩니다.  비즈니스용 Skype 및 Teams 서비스는 별도의 클라이언트가 있는 별도의 서비스이기 때문에 각 서비스에는 사용자에 대한 자체 현재 상태 상태가 있습니다.   또한 현재 상태 서비스 간에 Teams 온라인에서 비즈니스용 Skype 있습니다.  이렇게 하면 한 서비스가 필요한 경우 다른 서비스에서 사용자의 존재를 잠재적으로 게시할 수 있습니다. 

현재 상태 게시 동작은 사용자의 모드를 기반으로 합니다. 세 가지 기본 사례가 있습니다.

- 사용자가 TeamsOnly 모드인 경우 다른 모든 Teams 사용 클라이언트에 관계없이 해당 사용자의 현재 상태는 표시됩니다.

- 사용자가 모든 비즈니스용 Skype 있는 경우 다른 모든 사용자는 사용하는 클라이언트에 비즈니스용 Skype 사용자에 대한 비즈니스용 Skype 표시됩니다.

- 사용자가 제도 모드에 있는 경우 해당 비즈니스용 Skype Teams 게시된 현재 상태는 독립적이기 때문에 동일한 조직 내의 사용자에게 표시되는 현재 상태는 다른 사용자의 클라이언트에 따라 달라 갑니다. 페더러드 조직의 사용자는 해당 비즈니스용 Skype 사용자에 대한 페더리드 트래픽이 해당 비즈니스용 Skype.

예를 들어 사용자 A가 섬 모드로 가정합니다. 사용자 A가 Teams 활성화되어 있지만 로그인하지 않은 경우 다른 비즈니스용 Skype 클라이언트에서 사용자 A를 활성으로 Teams 클라이언트에서 비즈니스용 Skype 클라이언트에서 사용자 A를 오프라인으로 볼 수 있습니다. 클라이언트를 실행하지 않는 경우 사용자 A에 도달할 수 없습니다. 


### <a name="federation"></a>페더레이션

Teams 페더전을 사용하여 다른 사용자로 비즈니스용 Skype Teams 사용자가 온라인에 비즈니스용 Skype. TeamsUpgradePolicy는 들어오는 페더링된 채팅 및 통화에 대한 라우팅을 관리합니다. 페더리드 라우팅 동작은 아일랜드 모드를 제외한 동일한 테넌트 시나리오와 동일합니다. 받는 사람이 제도 모드인 경우:

- 수신자가 페더리드 테넌트에 Teams 경우 비즈니스용 Skype 토지에서 시작된 채팅 및 통화입니다.
- 받는 사람이 동일한 테넌트에 Teams Teams 토지에서 시작된 채팅 및 통화입니다.
- 비즈니스용 Skype 시작된 채팅 및 통화는 항상 비즈니스용 Skype.

페더리된 채팅은 네이티브 스레드 또는 인터프 스레드일 수 있습니다. 네이티브 대화 스레드와 [Interop을 참조합니다.](#interop-versus-native-conversation-threads)

- 받는 사람 및 보낸 사람이 TeamsOnly 업그레이드 모드인 경우 대화는 모든 풍부한 메시징 및 통화 기능을 포함하는 네이티브 채팅 환경이 됩니다. 자세한 내용은 의 [외부(페더리화)](native-chat-for-external-users.md)사용자에 대한 네이티브 채팅 환경을 Teams. 

- 대화 참가자 중 하나가 TeamsOnly 업그레이드 모드가 아닌 경우 대화는 텍스트 전용 메시지와 상호 운영 환경으로 남아 있습니다. 사용자 인터페이스는 사용자가 외부임을 나타내는 메모가 있는 경우를 제외하고 동일한 테넌트 인터팝 스레드와 유사한 방식으로 페더링된 채팅을 노출합니다.

자세한 내용은 [Microsoft Teams](manage-external-access.md) (페더리화) 사용자에 대한 외부 액세스 및 네이티브 채팅 환경의 외부 액세스 [관리를 Teams.](native-chat-for-external-users.md)

### <a name="contacts"></a>연락처

Teams 비즈니스용 Skype 연락처 목록이 있습니다. 즉, 한 시스템에서 만든 연락처 추가, 제거 및 수정이 다른 시스템에 동기화되지 않습니다. 그러나 두 가지 특정 비즈니스용 Skype 발생할 때 Teams 연락처가 자동으로 복사됩니다. 

- 모든 비즈니스용 Skype 온라인 사용자의 경우 처음 Teams 로그온할 때 비즈니스용 Skype 연락처를 복사하여 Teams.  이 동작은 프레미스에 있는 프레미스 계정이 있는 사용자에게는 사용할 수 비즈니스용 Skype 서버.  

- 사용자가 TeamsOnly로 업그레이드된 후(TeamsUpgradePolicy를 할당하거나 Move-CsUser -MoveToTeams를 통해) 다음에 사용자가 로그인할 때 Teams 사용자의 기존 연락처가 비즈니스용 Skype 이미 있는 기존 연락처와 Teams. 이 동작은 사용자가 On-프레미스 또는 온라인에서 TeamsOnly로 이동된지 여부에 따라 발생합니다. 

두 경우 모두 연락처를 비즈니스용 Skype Teams 비동기적이기 때문에 연락처가 비동기에 표시되기 몇 분 정도 Teams. 위의 두 이벤트는 복사를 트리거하는 이벤트입니다.  

### <a name="related-links"></a>관련 링크

[조직과 함께 Teams 조직에 대한 마이그레이션 및 상호 비즈니스용 Skype](migration-interop-guidance-for-teams-with-skype.md) 

[비즈니스용 Skype 서버 및 Microsoft 365 Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[온-프레미스와 클라우드 간에 사용자 이동](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[공존 및 업그레이드 설정 설정](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[MMS(모임 마이그레이션 서비스) 사용](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
