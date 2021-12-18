---
title: 업그레이드 여정을 비즈니스용 Skype Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl, bjwhalen
description: 비즈니스용 Skype 및 Microsoft Teams 옵션 및 예제 시나리오를 사용하여 Teams 업그레이드를 위한 가능한 업그레이드 여정에 대한 세부 정보입니다.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- ms.teamsadmincenter.orgwidesettings.teamsfeatures.upgradetoteamsarticle
- ms.teamsadmincenter.upgradeoverride.learnmore
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: deb64412a96ece539decd8dc2145067a91a1b95f
ms.sourcegitcommit: b0bb7db41856ee377dbe4ca8c9dff56385bf120d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/17/2021
ms.locfileid: "61562820"
---
# <a name="choose-your-upgrade-journey-from-skype-for-business-to-teams"></a>업그레이드 여정을 비즈니스용 Skype Teams

![여정 다이어그램을 업그레이드하여 정의 Project 강조합니다.](media/upgrade-banner-project-definition.png "업그레이드 단계( 정의 단계에 Project 단계")

이 문서는 업그레이드 Project 정의 단계의 일부입니다. 계속하기 전에 다음 작업을 완료한지 확인합니다.

- [프로젝트 관계자 인리스트](upgrade-enlist-stakeholders.md)
- [프로젝트 범위 정의](./upgrade-define-project-scope.md)
- [비즈니스용 Skype 및 상호운용성을 Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)

기존 비즈니스용 Skype 고객으로 전환하는 데 Teams 시간이 걸릴 수 있습니다. 그러나 사용자가 사용자와 함께 Teams 사용할 수 있도록 하여 현재 Teams 값을 비즈니스용 Skype. 두 앱 간에 일부 겹치는 기능이 있는 경우 사용 가능한 공존 및 업그레이드 모드를 검토하여 조직에 적합한 경로를 확인하는 것이 좋습니다. 예를 들어 상호 작업성 없이 두 솔루션의 모든 워크로드를 사용하도록 설정할 수 있습니다. 또는 조직에서 모든 사용자를 업그레이드할 준비가 Teams 때까지 사용자 환경을 점진적으로 Teams 또는 선택 기능을 위해 사용자 그룹을 대상으로 지정하여 사용자 환경을 관리할 Teams. 파일럿의 결과를 사용하여 조직에 대한 올바른 업그레이드 여정을 평가할 수 있습니다.

> [!IMPORTANT]
> 비즈니스용 Skype 온라인이 2021년 7월 31일 사용 중지됩니다. 혜택 현실화를 최대화하고 조직에서 업그레이드를 구현할 적절한 시간을 확보하기 위해 현재 업그레이드를 위한 여정을 Microsoft Teams 권장됩니다.

이 문서에서는 사용자가 사용할 수 있는 비즈니스용 Skype Teams 다양한 모드를 간략하게 간략하게 설명합니다. 모든 배포와 함께 조직을 업그레이드하기 전에 선택한 사용자 그룹과 함께 의도한 계획을 파일럿하는 것이 Teams. [](pilot-essentials.md) 새 기술을 도입하는 것이 사용자에게 방해가 될 수 있습니다. 여기에 설명된 모드를 구현하기 전에 사용자 준비 상태를 평가하고 통신 및 교육 계획을 구현하는 데 시간이 걸릴 수 있습니다.

> [!TIP]
> 업그레이드 계획 및 구현을 시작하도록 설계된 지침, 모범 사례 및 리소스를 공유하는 라이브 대화형 워크샵에 참여하세요.
>
>먼저 [업그레이드 계획 세션에](./upgrade-workshops-landing-page.yml) 참가하여 시작할 수 있습니다.


## <a name="upgrade-journey-building-blocks"></a>업그레이드 여정 구성 요소

조직을 공식적으로 준비하기 위해 Teams 조직이 단독 통신 및 공동 작업 솔루션으로 완전히 Teams 업그레이드 시나리오를 계획하기 시작해야 합니다.

의사 결정 프로세스를 안내하는 데 도움이 될 수 있도록, 업그레이드와 관련된 다양한 모드, 개념 및 용어를 익숙하게 비즈니스용 Skype Teams. 자세한 내용은 공존 및 Microsoft Teams 비즈니스용 Skype 를 [참조하세요.](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)

> [!NOTE]
> 음성 마이그레이션 시나리오도 고려해야 합니다. 전화 시스템 클라우드 또는 클라우드에서 통화 제어 및 PBX(Private Branch Exchange) 기능을 사용하도록 Microsoft 365 Office 365 기술입니다. 사용자가 전화 시스템 수 있도록 PSTN(공용 전환 전화 네트워크)에 연결하려면 비즈니스 필요에 따라 옵션이 있습니다. 전화 시스템 및 PSTN 연결 옵션에 대한 자세한 내용은 Voice - 전화 시스템 [및 PSTN 연결 을 참조하세요.](cloud-voice-landing-page.md)

마이그레이션된 사용자는 Teams 호스트된 모임에 비즈니스용 Skype 클라이언트를 더 이상 비즈니스용 Skype. 수신되는 모든 채팅 및 호출은 보낸 사람이 Teams 여부에 관계없이 사용자의 Teams 클라이언트에서 토지 Teams 비즈니스용 Skype. 업그레이드된 사용자가 구성한 모든 새 모임은 Teams 예약됩니다. 사용자가 클라이언트를 비즈니스용 Skype 경우 채팅 및 통화 시작이<sup>차단됩니다.</sup> 그러나 사용자는 여전히 비즈니스용 Skype 클라이언트를 사용하여 초대된 모임에 참가할 수 있습니다.

관리자는 [teamsUpgradePolicy의](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps&preserve-view=true)속성인 [](migration-interop-guidance-for-teams-with-skype.md)Teams 개념을 사용하여 전환을 관리합니다. 위에서 설명한 대로 Teams "TeamsOnly" 모드로 마이그레이션된 사용자입니다. 조직으로 마이그레이션하는 조직의 경우 Teams 궁극적인 목표는 모든 사용자를 TeamsOnly 모드로 이동하는 것입니다.

기존 조직을 온라인 또는 비즈니스용 Skype 사용하여 기존 조직을 마이그레이션하는 두 가지 방법이 Teams.

- **겹치는** 기능 방법(섬 모드 사용): 기존 비즈니스용 Skype 조직에 Teams 두 클라이언트를 나란히 사용할 수 있도록 조직에 도입됩니다. 이 기간 동안 대부분의 기능을 사용할 수 있지만 Teams 사용할 수 있습니다. 이 구성의 모드를 섬이라고 합니다. 이 모드는 기존 조직에 대해 기본 모드로 비즈니스용 Skype. 조직이 준비되면 관리자는 사용자를 TeamsOnly 모드로 이동합니다.

- **기능 메서드를** 선택합니다(비즈니스용 Skype 모드 중 하나 이상 사용): 관리자는 조직의 사용자에 대한 채팅, 통화 및 모임 비즈니스용 Skype Teams 전환을 관리합니다. 이러한 각 함수는 비즈니스용 Skype 또는 Teams 사용할 수 있지만 둘 다 사용할 수 없습니다. 관리자는 TeamsUpgradePolicy를 사용하여 사용자에 대해 이 기능을 Teams 제어합니다. TeamsOnly 모드에 있지 않은 사용자는 채팅 및 비즈니스용 Skype 계속 사용할 수 있으며, 두 사용자 집합은 상호op 기능을 통해 통신할 수 있습니다. 관리자는 더 많은 사용자를 TeamsOnly 모드로 점진적으로 마이그레이션하여 전환을 관리합니다.

<sup>1</sup> 비즈니스용 Skype 이전 클라이언트는 TeamsUpgradePolicy를 존중하지 않습니다. 사용자 채널에서 사용할 수 있는 최신 비즈니스용 Skype 클라이언트를 사용하고 있는지 Office 합니다.

업그레이드 방법을 이해하고 선택한 후 조직의 업그레이드를 관리하기 위한 도구에 대해 [Teams.](upgrade-to-teams-on-prem-tools.md)

다음은 조직의 적절한 경로를 결정하는 데 도움이 되는 주요 요소입니다.

## <a name="overlapping-capabilities-method-using-islands-mode"></a>겹치는 기능 메서드(제도 모드 사용)

겹치는 기능 메서드를 사용하여 사용자는 채팅, VoIP Teams 및 비즈니스용 Skype 클라이언트를 모두 사용할 수 있습니다. 이 메서드에서는 조직의 채팅 및 VOIP Teams 조직 내 포커스가 비즈니스용 Skype 외부 조직과의 채팅 및 VOIP/PSTN 통화를 사용할 수 있습니다(구성된 경우). 두 제품 모두에서 모임을 예약하고 참석할 수 있습니다.

겹치는 기능 메서드를 사용하는 경우 동일한 사용자에 대해 비즈니스용 Skype Teams 통신 트래픽은 별개로 유지될 수 있으며( 동일한 조직 내의 사용자에 대해) 서로 통신하지 않습니다. 사용자 환경은 받는 사람의 구성을 기반으로 합니다. 예를 들어 받는 사람 사용자 A가 제도 모드에 있는 것으로 가정합니다.

- 다른 사용자의 비즈니스용 Skype 클라이언트에서 시작된 통신은 항상 사용자 A의 비즈니스용 Skype 클라이언트에 연결됩니다.

- 동일한 조직의 Teams 클라이언트에서 시작된  통신은 항상 사용자 A의 Teams 클라이언트에 연결됩니다.

- 외부 조직의 Teams 클라이언트에서 시작된  통신은 항상 사용자 A의 비즈니스용 Skype 합니다.

사용자에게 Microsoft 365 Office 365 라이선스를 할당한 경우 조직의 기본 업그레이드 환경이 됩니다. 라이선스 또는 Microsoft 365 Office 365 할당하면 기본적으로 Teams 비즈니스용 Skype 라이선스가 할당됩니다.<sup> 2</sup>

이 메서드가 효과적으로 작동하려면 모든 사용자가 두 클라이언트를 동시에 실행해야 합니다. 조직 내에서 섬 모드의 사용자로 들어오는 채팅 및 호출은 비즈니스용 Skype 또는 Teams 클라이언트에 착륙할 수 있으며 받는 사람의 제어에 속하지 않습니다. 보낸 사람이 통신을 시작하는 데 사용하는 클라이언트에 따라 달라 습니다. 보낸 사람 및 받는 사람이 서로 다른 조직에 있는 경우, 섬 모드의 사용자에 대한 수신 통화 및 채팅은 항상 비즈니스용 Skype 클라이언트에 있습니다.

예를 들어 섬 모드 받는 사람이 로그인하여 비즈니스용 Skype Teams 다른 사람이 해당 메시지를 Teams 경우, 섬 모드 받는 사람이 메시지를 볼 수 없습니다(하지만 결국 해당 수신자는 메시지를 누락했다는 전자 메일을 Teams. 마찬가지로 사용자가 Teams 비즈니스용 Skype 실행 중이면 다른 사용자가 비즈니스용 Skype 해당 채팅을 볼 수 없습니다. 이러한 각 경우의 동작은 호출과 비슷합니다. 사용자가 두 클라이언트를 모두 실행하지 않는 경우 쉽게 좌절할 수 있습니다.

또한 현재 상태는 이 업그레이드 방법을 사용할 때 Teams 비즈니스용 Skype 간에 독립적으로 작동합니다. 즉, 다른 사용자가 사용하는 클라이언트에 따라 사용자 A에 대한 다른 현재 상태 표시가 표시될 수 있습니다. 자세한 내용은 현재 상태 [를 참조합니다.](teams-and-skypeforbusiness-coexistence-and-interoperability.md#presence)

- 다른 사용자는 Teams 사용자의 활동에 따라 현재 상태는 Teams.

- 다른 사용자는 비즈니스용 Skype 사용자 A의 활동에 따라 현재 상태 비즈니스용 Skype.

TeamsOnly 모드로 사용자를 업그레이드할 준비가 되면 사용자를 개별적으로 업그레이드하거나 테넌트 전체 정책 3 을 사용하여 한 번씩 전체 테넌트를 업그레이드할 수<sup>있습니다.</sup> 사용자가 TeamsOnly 모드로 업그레이드된 후 모든 수신 채팅 및 통화를 Teams. (비즈니스용 Skype 모임으로 Teams 마이그레이션은 테넌트당이 아닌 개별 사용자에게 TeamsUpgradePolicy를 적용할 때만 트리거됩니다. 자세한 [내용은 모임](upgrade-to-teams-on-prem-tools.md#meeting-migration) 마이그레이션을 참조합니다.)

그러나 제도 모드에서 업그레이드되지 않은 받는 사람은 해당 클라이언트 또는 클라이언트에서 TeamsOnly 사용자로부터 채팅 및 비즈니스용 Skype Teams 수 있습니다. 기존 대화의 경우 TeamsOnly 사용자는 보낸 사람이 채팅 또는 통화를 시작한 클라이언트에 회신합니다. 

TeamsOnly 사용자의 시점에서 새 대화의 경우 채팅 또는 통화는 항상 클라이언트의 섬 모드 Teams 됩니다. 이는 Teams 클라이언트가 동일한 사용자도 Teams Teams Teams 비즈니스용 Skype 대화 스레드를 유지 관리하기 때문에입니다. 자세한 내용은 Teams 대화 - Interop 및 네이티브 [스레드를 참조합니다.](teams-and-skypeforbusiness-coexistence-and-interoperability.md#interoperability)

다음 표에서는 섬 모드와 TeamsOnly 모드에 Teams 환경이 요약되어 있습니다.

| Teams 경험 | 제도 모드에서 | TeamsOnly 모드에서 |
|:------------------ | :------------------- | :------------------ |
| 수신 채팅 및 통화:|  Teams 비즈니스용 Skype | Teams |
| 에서 수신된 PSTN 호출: | 비즈니스용 Skype <br>(Teams 모드에서 PSTN 기능을 사용하는 것은 지원되지 않습니다.)     | Teams |   
 |현재 상태    | 비즈니스용 Skype 및 Teams 상태는 독립적입니다. 사용자가 사용하는 클라이언트에 따라 동일한 아일랜드 사용자에 대해 서로 다른 상태가 표시될 수 있습니다. | 현재 상태는 사용자의 활동만 기반으로 Teams. 사용하는 클라이언트에 관계없이 다른 모든 사용자는 해당 현재 상태 를 참조합니다. | 
 | 모임일정    | 사용자는 모임을 예약할 수 Teams 또는 비즈니스용 Skype. 기본적으로 두 추가 기능을 모두 Outlook. 사용자가 모임 Teams 추가 기능만 사용할 수 있는지 또는 Teams 모임 및 모임 추가 Teams 둘 다를 비즈니스용 Skype 설정할 수 있습니다. 자세한 내용은 Islands 모드에서 사용자에 대한 모임 공급자 [설정 을 참조하세요.](meeting-policies-in-teams-general.md#meeting-provider-for-islands-mode) |     사용자만 모임을 예약할 Teams. 추가 Teams 추가 기능만 사용할 수 Outlook. | 

다음 표에서는 겹치는 기능 메서드를 사용하여 조직을 마이그레이션할 때의 장단 Teams.

| Pros     |       Cons |
| :------------------ | :---------------- |
| 조직 내에서 신속한 채택을 허용합니다.| 유사한 기능이 있는 두 개의 클라이언트가 있지만 다른 사용자 인터페이스가 있기 때문에 최종 사용자 혼란이 발생할 수 있습니다. 또한 들어오는 채팅/호출이 들어오는 클라이언트를 제어할 수 없습니다. |
| 사용자가 사용자에 대한 전체 액세스 권한을 Teams 학습하고 익숙해 비즈니스용 Skype. | 사용자가 두 클라이언트를 모두 실행하지 않는 경우 누락된 메시지로 인해 최종 사용자 불만이 발생할 수 있습니다.|
| 관리에서 시작하기 위한 최소한의 Teams. | 사용자와 정기적으로 통신하는 사용자가 적극적으로 사용하지 않는 경우 "제도에서 아웃" 모드로 전환하고 TeamsOnly 모드로 Teams. 예를 들어 사용자의 하위 집합이 TeamsOnly 모드로 업그레이드된 후 해당 사용자는 해당 사용자만 Teams. 섬 모드의 나머지 모집단의 경우 해당 메시지는 항상 Teams. 그러나 해당 인구 중 일부가 실행되지 Teams 메시지를 누락된 것으로 인식합니다.|
|사용자가 기능을 활용하여 사용자에서 사용할 수 없는 팀워크를 향상할 수 비즈니스용 Skype.| 프레미스 및 비즈니스용 Skype 및 Teams 사용자는 Teams 프레미스에서 비즈니스용 Skype 사용자와 통신할 수 Teams.  |
|  | Teams 사용할 때, 비즈니스용 Skype 서버 프레미스 계정이 있는 사용자에게는 interop 또는 페더연맹 지원이 없습니다.  이로 인하여 Islands 사용자가 혼합되어 있는 경우 혼동을 줄 수 있습니다. 일부 사용자는 비즈니스용 Skype 온라인에 비즈니스용 Skype 있습니다.   |

<sup>2</sup> 사용자가 프레미스에 홈이 있는 경우에도 비즈니스용 Skype 서버. 사용자가 홈온-프레미스인지 온라인인지 여부에 비즈니스용 Skype 전체 기능을 위해 현재 필요하기 때문에 온라인 라이선스를 사용하도록 Teams 있습니다.

<sup>3</sup> 테넌트당 비즈니스용 Skype 아닌 개별 사용자에게 TeamsUpgradePolicy를 적용하는 Teams 모임으로의 마이그레이션이 트리거됩니다. 자세한 [내용은 모임](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms) 마이그레이션을 참조합니다.

## <a name="select-capabilities-method-using-skype-for-business-modes"></a>기능 메서드 선택(비즈니스용 Skype 모드 사용)

일부 조직에서는 조직이 조직에서 조직으로 전환될 때 최종 사용자에게 보다 예측 가능한 환경을 비즈니스용 Skype Teams. 이 모델에서 IT 관리자는 TeamsUpgradePolicy의 비즈니스용 Skype 모드 중 하나를 사용하여 TeamsOnly 모드로 마이그레이션하기 전에 비즈니스용 Skype 남아 있는 기능을 명시적으로 지정합니다. 선택한 기능을 TeamsOnly 모드로 전환할 준비가 되면 관리자는 해당 사용자의 모드를 TeamsOnly로 업데이트합니다. 이 전환하는 동안:

- 관리자는 사용자가 TeamsOnly 환경으로 이동하기 Teams 채팅 및 통화 기능을 유지하면서 사용자에게 특정 비즈니스용 Skype 기능을 사용하도록 설정할 수 있습니다. 관리는 공동 작업 Teams 또는 모임 Teams 공동 작업 기능을 사용하도록 설정할 수 있습니다.

- 여전히 비즈니스용 Skype 사용자는 다른 사용자의 비즈니스용 Skype 클라이언트에서 통신이 시작된지 여부에 관계없이 해당 클라이언트에서 들어오는 모든 채팅 및 Teams 비즈니스용 Skype 수신합니다. 또한 이러한 비즈니스용 Skype 사용자의 경우 최종 사용자 혼동을 방지하고 적절한 라우팅 및 현재 Teams 클라이언트의 통화 및 채팅 기능을 사용하지 않도록 설정됩니다.

- TeamsOnly 모드의 사용자는 모든 수신 채팅 및 Teams 클라이언트에서 수신하고 현재 상태는 Teams, Teams, 비즈니스용 Skype 페더러드 사용자에 관계 없이 제공됩니다.

겹치는 기능(제도) 메서드와 달리, 선택 기능 메서드에서 비즈니스용 Skype 사용자가 TeamsOnly에 있는 사용자와 통신할 수 있습니다. 사용자와 비즈니스용 Skype 사용자 간의 통신을 Teams 또는 [](teams-and-skypeforbusiness-coexistence-and-interoperability.md#interoperability) "interop"이라고 합니다. 인터팝 통신은 일대일로 채팅 및 통화를 위해 비즈니스용 Skype 사용자와 다른 사용자 간에 Teams. 또한 초대된 사용자는 항상 모임 또는 비즈니스용 Skype Teams 참가할 수 있습니다. 그러나 모임 유형에 해당하는 클라이언트를 사용해야 합니다. 자세한 내용은 모임 [을 참조하세요.](teams-and-skypeforbusiness-coexistence-and-interoperability.md#meetings)

선택 기능 전환 메서드의 사용자의 경우 다른 사용자가 사용하는 클라이언트에 관계없이 사용자에 대한 현재 상태는 일관됩니다. 사용자가 해당 비즈니스용 Skype 모드 중 하나에 있는 경우 다른 모든 사용자는 해당 사용자의 활동에 따라 현재 비즈니스용 Skype. 마찬가지로 사용자가 TeamsOnly 모드에 있는 경우 다른 모든 사용자는 해당 사용자의 활동에 따라 현재 Teams. 자세한 내용은 현재 상태 [를 참조합니다.](teams-and-skypeforbusiness-coexistence-and-interoperability.md#presence)

아직 테넌트 사용을 시작하지 않은 조직의 Teams 관리자는 테넌트 전체 모드를 섬에서 SfbWithTeamsCollab으로 변경해야 합니다. (이미 일부 사용량이 Teams 조직의 경우 관리자는 이 변경이 해당 사용자에게 적용되지 않도록 Teams 이미 활성 상태인 "할아버지" 사용자를 "할아버지"로 설정해야 합니다. 자세한 내용은 아일랜드 모드에서 이미 Teams 조직에 대한 기능 선택 메서드를 [참조합니다.](upgrade-to-teams-on-prem-implement.md#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode) 

게스트 사용자 환경은 테넌트에 할당된 공존 모드를 준수합니다. 테넌트 수준에서 비즈니스용 Skype 경우 게스트는 채팅, 통화 또는 현재 상태 표시를 할 수 없습니다. 자세한 내용은 [Teams의 게스트 액세스](guest-access.md)를 참조하세요.

모드가 섬에서 SfbWithTeamsCollab으로 변경되는 경우, 이 모드를 사용하지 Teams 사용자가 해당 기능을 사용하는 방식에 비즈니스용 Skype. 그러나 해당 사용자가 채널을 사용하기 Teams 채널 및 파일과 같은 기능에만 Teams & 것입니다. 관리자가 해당 함수에 대해 원하는 클라이언트로 (Teams 비즈니스용 Skype) 지정되어 있는 경우 채팅, 통화 및 모임 Teams 사용할 수 없습니다.

> [!NOTE]
> 사용자 A가 비즈니스용 Skype 모드 중 하나로 변경하면 사용자 A와 통신하는 Teams 다른 사용자의 클라이언트가 사용자 A에 대한 적절한 클라이언트로 통신을 라우팅할 수 있도록 사용자 A의 모드가 변경된 것을 알아야 합니다. 사용자 A와 Teams Teams 기본 채팅을 설정한 모든 사용자의 경우 이러한 다른 사용자의 Teams 클라이언트가 섬에서 모든 비즈니스용 Skype 인식하는 데 최대 36시간이 비즈니스용 Skype 있습니다. 반면에 기존 사용자의 TeamsOnly 모드 변경은 2시간 이내에 다른 클라이언트에서 검색됩니다.<br>
> 관리자가 준비되면 특정 사용자의 채팅, 통화 및 모임 예약을 한 Teams 모드를 TeamsOnly로 업데이트하여 한 Teams 전환할 수 있습니다.

또는 관리자는 먼저 SfBWithTeamsCollabAndMeetings 모드를 사용하여 채팅 및 Teams 함수를 비즈니스용 Skype 수 있습니다. 이 모드를 사용하면 사용자가 TeamsOnly 모드로 Teams 준비가 되지 않은 경우(예: 기존 PSTN 기능을 마이그레이션할 준비가 되지 않은 경우) 조직에서 모임을 위한 모임으로 전환할 수 있습니다. 이 전환 시나리오를 모임 [우선이라고 합니다.](meetings-first.md)


|Teams 경험  |SfBWithTeamsCollab 모드에서 |SfBWithTeamsCollabAndMeetings 모드에서 |TeamsOnly 모드에서  |
|---------|---------|---------|---------|
|수신된 조직의 사용자로부터 들어오는 채팅 및 VOIP 통화:     | 비즈니스용 Skype        | 비즈니스용 Skype       | Teams        |
|에서 수신된 PSTN 호출:     | 비즈니스용 Skype        |비즈니스용 Skype         | Teams        |
|현재 상태     | 비즈니스용 Skype        |비즈니스용 Skype         | Teams        |
|모임일정     | 비즈니스용 Skype         | Teams        | Teams        |


다음 표에서는 TeamsOnly 모드에 대한 전환 단계로 비즈니스용 Skype 모드 사용의 장단점과 장단점에 대해 요약합니다.

| Pros     |       Cons |
| :------------------ | :---------------- |
| 최종 사용자의 예측 가능한 라우팅입니다. 모든 통화 및 채팅은 관리자 선택에 따라 비즈니스용 Skype Teams(둘 다 아우지 않습니다)에 있습니다.|상호 대화는 풍부한 텍스트, 파일 공유 및 화면 공유에 대한 지원이 부족합니다. 모임을 시작하기 위해 Meet Now 기능을 활용하는 데 사용할 수 있습니다. |
|주어진 기능은 한 클라이언트에서만 사용할 수 있기 때문에 최종 사용자 혼동을 줄일 수 있습니다. | 사용자가 TeamsOnly로 업그레이드되기 전에 채팅 및 통화와 같은 Teams 수행되는 일반적인 비즈니스용 Skype 액세스할 수 없습니다. 즉, 나란히 기능이 없습니다.|
|관리자는 사용자가 사용할 수 있는 기능 집합을 제어할 수 비즈니스용 Skype Teams. 이 컨트롤에는 확장 기능을 증분적으로 소개하는 Teams 포함됩니다. | |
| 아직 teamsOnly 모드로 Teams 준비가 되지 않았어도 조직에서 모임에 사용할 수 있습니다.||
|다른 사용자가 보는 것으로 주어진 사용자의 현재 상태는 사용하는 클라이언트에 관계없이 동일합니다.||

## <a name="summary-of-upgrade-methods"></a>업그레이드 방법 요약
다음 표에서는 업그레이드 방법을 요약합니다.


|겹치는 기능(제도 모드 사용)  |선택한 기능(비즈니스용 Skype 모드 사용)  |
|---------|---------|
|TeamsOnly로 업그레이드하기 전에 들어오는 채팅 및 통화가 두 클라이언트에 모두 제공될 수 있습니다.     | 받는 사람의 모드에 따라 채팅 및 통화는 하나의 클라이언트에만 착륙합니다. 업그레이드되지 않은 사용자는 두 클라이언트를 모두 실행할 수 있지만 기능 중복이 없습니다(통화 및 채팅은 해당 클라이언트에서 사용할 수 Teams. 관리자는 사용자가 모임을 예약할지 또는 Teams 여부를 비즈니스용 Skype.         |
|관리자가 최종 사용자에 대한 비즈니스용 Skype Teams(나란히 기능 허용) 및 새 기능(Teams 및 채널)에 겹치는 기능(채팅, 모임, VOIP 호출)을 Teams.     | 관리자가 동일한 기능을 제공하지 않고 최종 사용자(Teams 및 채널)에 Teams 선택 기능을 소개할 수 비즈니스용 Skype.        |
|두 사용자가 비즈니스용 Skype Teams 동안에는 인터팝이 없습니다. 일부 사용자가 TeamsOnly로 업그레이드된 후 해당 사용자와 여전히 아일랜드 모드인 다른 사용자 간에 대화가 발생할 수 있습니다. 그러나 Islands 사용자는 이 옵션을 사용하여 상호 Teams 방지할 수 있습니다.      |Interop은 사용자와 사용자 간의 비즈니스용 Skype Teams 필요합니다.         |

> [!NOTE]
> 사용자를 마이그레이션하기 위해 지원되는 방법을 비즈니스용 Skype 서버 Teams 경우 Active Directory에서 사용자 Teams 모든 관련 비즈니스용 Skype 서버 제거하여 사용자를 Teams 전환할 수 있습니다. 사용자가 Azure Active Directory 특성이 지워진 비즈니스용 Skype 서버 및 DNS 레코드가 Microsoft 365 또는 Office 365 다시 지적된 경우 사용자 라이선스를 Microsoft 365 Office 365 및 업그레이드하여 Teams. 

> [!IMPORTANT]
> 컷오버 마이그레이션을 통해 연락처 데이터 및 모임 데이터는 프레미스 환경에서 프레미스 환경으로 마이그레이션되지 Microsoft Teams.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>결정 지점</td><td><ul> 조직의 비즈니스 요구 사항에 적합한 업그레이드 여정은 무엇입니까?<br><br></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next step"/><br/>다음 단계</td><td><ul> 현재 배포 모델, 사용 사례 시나리오 및 조직에 대한 주요 고려 사항을 식별하면 조직에 가장 적합한 Teams 방법을 알릴 수 있습니다.<br><br></ul></td></tr>
</table>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>결정 지점</td><td><ul> 조직에 적용할 수 있는 업그레이드 시나리오는 무엇입니까?<br><br></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>다음 단계</td><td><ul> 메시징, 모임 및 호출 비즈니스 요구 사항에 따라 조직의 업그레이드 여정의 타임라인을 결정합니다.<br><br> 업그레이드 여정을 완료하는 데 필요한 추가 작업을 결정합니다.<br><br></ul></td></tr>
</table>

조직에 가장 적합한 업그레이드 여정을 선택한 후 업그레이드를 [Teams.](./upgrade-to-teams.md)

## <a name="related-links"></a>관련 링크

[조직과 함께 Teams 조직에 대한 마이그레이션 및 상호 비즈니스용 Skype](migration-interop-guidance-for-teams-with-skype.md) 

[비즈니스용 Skype 서버 및 Microsoft 365 Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[온-프레미스와 클라우드 간에 사용자 이동](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[공존 및 업그레이드 설정 설정](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps&preserve-view=true)

[MMS(모임 마이그레이션 서비스) 사용](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)