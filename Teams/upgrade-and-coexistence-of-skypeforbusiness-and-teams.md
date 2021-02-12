---
title: 비즈니스용 Skype에서 Microsoft Teams로의 업그레이드 여정 선택
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl, bjwhalen
description: 비즈니스용 Skype 및 Microsoft Teams 공존 옵션에 대한 세부 정보 및 예제 시나리오를 사용하여 Teams로의 업그레이드 여정을 자세히 설명합니다.
localization_priority: Normal
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
ms.openlocfilehash: 23a71a075730f1447259d6e3a4a3dd21f650bfd7
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578161"
---
# <a name="choose-your-upgrade-journey-from-skype-for-business-to-teams"></a>비즈니스용 Skype에서 Teams로의 업그레이드 여정 선택

![프로젝트 정의 스테이지를 강조하는 업그레이드 여정 다이어그램](media/upgrade-banner-project-definition.png "프로젝트 정의 단계에 강조를 두는 업그레이드 단계")

이 문서는 업그레이드 여정의 프로젝트 정의 단계의 일부입니다. 계속하기 전에 다음 활동을 완료해야 합니다.

- [프로젝트 관련자에 참여](upgrade-enlist-stakeholders.md)
- [프로젝트 범위 정의](https://aka.ms/SkypetoTeams-Scope)
- [비즈니스용 Skype 및 Teams의 공존 및 상호 연동성 이해](https://aka.ms/SkypeToTeams-Coexist)

기존 비즈니스용 Skype 고객은 Teams로의 전체 전환에 다소 시간이 걸릴 수 있습니다. 그러나 사용자가 비즈니스용 Skype와 함께 Teams를 사용할 수 있도록 하여 지금 Teams의 가치를 인식할 수 있습니다. 두 앱 간에 일부 겹치는 기능이 있는 경우 사용 가능한 공존 및 업그레이드 모드를 검토하여 조직에 적합한 경로를 확인하는 것이 좋습니다. 예를 들어 상호 연동성 없이 두 솔루션의 모든 워크로드를 사용하도록 선택할 수 있습니다. 또는 조직이 모든 사용자를 Teams로 업그레이드할 준비가 될 때까지 Teams 기능을 점진적으로 도입하거나 선택 기능에 대한 사용자 그룹을 대상으로 지정하여 사용자 환경을 관리하도록 결정할 수 있습니다. 파일럿의 결과를 사용하여 조직에 적합한 업그레이드 여정을 평가할 수 있습니다.

> [!IMPORTANT]
> 비즈니스용 Skype Online은 2021년 7월 31일에 서비스가 종료되며 이후에는 더 이상 액세스할 수 없게 되거나 지원되지 않습니다. 혜택 구현을 극대화하고 조직이 업그레이드를 구현할 수 있는 적절한 시간을 확보하려면 지금 Microsoft Teams로의 여정을 시작하는 것이 권장됩니다.

이 문서에서는 사용자가 사용할 수 있는 비즈니스용 Skype 및 Teams에서 어떤 모드를 관리할 수 있는 다양한 모드를 간략하게 설명하고 있습니다. 배포와 달리 조직을 Teams로 [](pilot-essentials.md) 업그레이드하기 전에 선택한 사용자 그룹과 함께 의도한 계획을 시험해보는 것이 좋습니다. 새 기술을 도입하는 것이 사용자에게 방해가 될 수 있습니다. 여기에 설명된 모드를 구현하기 전에 사용자 준비 상태를 평가하고 통신 및 교육 계획을 구현하는 데 시간이 걸릴 수 있습니다.

> [!TIP]
> 업그레이드 계획 및 구현을 시작하도록 설계된 지침, 모범 사례 및 리소스를 공유하는 라이브 대화형 워크샵에 참여하세요.
>
>먼저 [업그레이드 세션 계획에](https://aka.ms/SkypeToTeamsPlanning) 참가하여 시작할 수 있습니다.


## <a name="upgrade-journey-building-blocks"></a>업그레이드 여정 구성 요소

Teams에 대한 여정을 위해 조직을 공식적으로 준비하려면 조직이 유일한 통신 및 공동 작업 솔루션으로 Teams를 완전히 수용할 수 있도록 하는 업그레이드 시나리오에 대한 계획을 시작해야 합니다.

의사 결정 프로세스를 안내하기 위해 비즈니스용 Skype에서 Teams로 업그레이드하는 데 관련된 다양한 모드, 개념 및 용어에 익숙해지세요. 자세한 내용은 Microsoft Teams 및 비즈니스용 Skype 공존 및 상호 [연동성을 참조하세요.](https://aka.ms/SkypeToTeams-Coexist)

> [!NOTE]
> 음성 마이그레이션 시나리오도 고려해야 합니다. 전화 시스템은 Microsoft 365 또는 Office 365 클라우드에서 통화 제어 및 PBX(Private Branch Exchange) 기능을 사용하도록 설정하기 위한 Microsoft의 기술입니다. 사용자가 전 세계에 전화를 걸 수 있도록 전화 시스템을 PSTN(공용 전환 전화 네트워크)에 연결하려면 비즈니스 필요에 따라 옵션을 사용할 수 있습니다. 전화 시스템 및 PSTN 연결 옵션에 대한 자세한 내용은 음성 - 전화 시스템 및 [PSTN 연결을 참조하세요.](cloud-voice-landing-page.md)

Teams로 마이그레이션된 사용자는 비즈니스용 Skype에서 호스트된 모임에 참가하는 것 외에는 더 이상 비즈니스용 Skype 클라이언트를 사용할 수 없습니다. 받는 모든 채팅 및 통화는 보낸 사람이 Teams 또는 비즈니스용 Skype를 사용하는지 여부에 관계없이 사용자의 Teams 클라이언트에 있습니다. 업그레이드된 사용자가 구성한 모든 새 모임은 Teams 모임으로 예약됩니다. 사용자가 비즈니스용 Skype 클라이언트를 사용하려고 시도하면 채팅 및 통화 시작이<sup>차단됩니다.</sup> 그러나 사용자는 여전히 비즈니스용 Skype 클라이언트를 사용하여 초대된 모임에 참가할 수 있으며 반드시 해야 합니다.

관리자는 [TeamsUpgradePolicy의](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps) [](migration-interop-guidance-for-teams-with-skype.md)속성인 모드 개념을 사용하여 Teams로의 전환을 관리합니다. 위에서 설명한 대로 Teams로 마이그레이션된 사용자는 "TeamsOnly" 모드입니다. Teams로 마이그레이션하는 조직의 경우 궁극적인 목표는 모든 사용자를 TeamsOnly 모드로 이동하는 것입니다.

비즈니스용 Skype를 사용하여 기존 조직을 Teams로 마이그레이션하는 방법에는 두 가지가 있습니다(온라인 또는 프레미스와 무관).

- **겹치는** 기능 방법(제도 모드 사용): 전환 단계에서 두 클라이언트를 나란히 사용할 수 있도록 기존 비즈니스용 Skype 조직의 사용자가 Teams에 도입됩니다. 이 기간에는 Teams의 모든 기능을 사용할 수 있지만 대부분의 기능을 사용할 수 있습니다. 이 구성의 모드를 '제도'라고 합니다. 이 모드는 비즈니스용 Skype를 사용 하는 기존 조직의 기본 모드입니다. 조직이 준비되면 관리자는 사용자를 TeamsOnly 모드로 전환합니다.

- **기능 선택** 방법(비즈니스용 Skype 모드 중 하나 이상 사용): 관리자는 조직의 사용자에 대한 채팅, 통화 및 모임 예정 기능의 전환(비즈니스용 Skype에서 Teams로)을 관리합니다. 이러한 각 기능은 비즈니스용 Skype 또는 Teams에서 사용할 수 있지만 둘 다 사용할 수 없습니다. 관리자는 TeamsUpgradePolicy를 사용하여 사용자의 이 기능을 Teams로 전환할 때를 제어합니다. 아직 TeamsOnly 모드에 있지 않은 사용자는 채팅 및 통화에 비즈니스용 Skype를 계속 사용하고 두 사용자 집합은 상호Op 기능을 통해 통신할 수 있습니다. 관리자는 더 많은 사용자를 TeamsOnly 모드로 점진적으로 마이그레이션하여 전환을 관리합니다.

<sup>2017년</sup> 전에 제공된 이전 비즈니스용 Skype 클라이언트 1명은 TeamsUpgradePolicy를 존중하지 않습니다. Office 채널에서 사용할 수 있는 최신 비즈니스용 Skype 클라이언트를 사용하고 있는지 확인

다음은 조직에 적합한 경로를 결정하는 데 도움이 되는 주요 요소입니다. 

## <a name="overlapping-capabilities-method-using-islands-mode"></a>겹치는 기능 방법(제도 모드 사용)

겹치는 기능 방법으로 사용자는 채팅, VoIP 통화 및 모임에 Teams 및 비즈니스용 Skype 클라이언트를 모두 사용할 수 있습니다. 이 방법에서는 Teams의 채팅 및 VOIP 통화가 조직 내부에 집중된 반면 비즈니스용 Skype는 외부 조직과의 채팅 및 VOIP/PSTN 통화(구성된 경우)를 사용할 수 있습니다. 두 제품 모두에서 모임을 예약하고 참석할 수 있습니다.

겹치는 기능 방법을 사용하는 경우 비즈니스용 Skype 및 Teams의 통신 트래픽은 별개로 유지(동일한 사용자도 마찬가지) 두 클라이언트가 서로 통신하지 않습니다(동일한 조직 내 사용자용). 사용자 환경은 받는 사람의 구성을 기반으로 합니다. 예를 들어 받는 사람 사용자 A가 이 업그레이드 방법을 사용 중이라 가정합니다.

- 다른 사용자의 비즈니스용 Skype 클라이언트에서 시작된 통신은 항상 사용자 A의 비즈니스용 Skype 클라이언트에 있습니다.

- 동일한 조직의 사용자로부터 Teams 클라이언트로부터 시작된 *통신은* 항상 사용자 A의 Teams 클라이언트에 있습니다.

- 외부 조직의 사용자로부터 Teams  클라이언트로부터 시작된 통신은 항상 사용자 A의 비즈니스용 Skype 클라이언트에 있습니다.

사용자에게 Microsoft 365 또는 Office 365 라이선스를 할당한 경우 조직의 기본 업그레이드 환경이 됩니다. Microsoft 365 또는 Office 365 라이선스를 할당하면 기본적으로 Teams 및 비즈니스용 Skype Online 라이선스가 모두 할당됩니다. <sup>2</sup>

이 방법을 효과적으로 작동하려면 모든 사용자가 두 클라이언트를 동시에 실행해야 합니다. 조직 내에서 제도 모드의 사용자로 들어오는 채팅 및 통화는 비즈니스용 Skype 또는 Teams 클라이언트에 연결될 수 있으며 받는 사람의 제어 하에 있지 않습니다. 발신자에서 통신을 시작하는 데 사용하는 클라이언트에 따라 달라 습니다. 보낸 사람 및 받는 사람이 다른 조직에 있는 경우, 제도 모드에서 사용자에게 수신 전화 및 채팅은 항상 비즈니스용 Skype 클라이언트에 있습니다.

예를 들어, 제도 모드 받는 사람이 비즈니스용 Skype에 로그인하고 Teams에서 메시지를 보내지 않는 경우, 제도 모드 받는 사람은 메시지를 볼 수 없습니다(하지만 결국 Teams에서 메시지를 놓쳤다는 전자 메일이 전송됩니다). 마찬가지로 사용자가 Teams를 실행하고 있지만 비즈니스용 Skype는 실행하고 있지 않은 경우 비즈니스용 Skype의 사용자가 보낸 메시지는 해당 채팅을 볼 수 없습니다. 이러한 각 경우의 동작은 호출과 유사합니다. 사용자가 두 클라이언트를 모두 실행하지 않는 경우 쉽게 좌절할 수 있습니다.

또한 현재 상태는 이 업그레이드 방법을 사용하여 Teams와 비즈니스용 Skype 간에 독립적으로 작동됩니다. 즉, 다른 사용자가 사용하는 클라이언트에 따라 사용자 A에 대한 다른 현재 상태 표시가 표시될 수 있습니다. 자세한 내용은 현재 상태 [를 참조합니다.](upgrade-to-Teams-on-prem-coexistence.md#presence)

- Teams를 사용할 때 다른 사용자는 Teams에서 사용자 A의 활동을 기반으로 하여 현재 상태 표시를 볼 수 있습니다.

- 비즈니스용 Skype를 사용할 때 다른 사용자는 비즈니스용 Skype에서 사용자 A의 활동을 기반으로 현재 상태 표시를 볼 수 있습니다.

사용자를 TeamsOnly 모드로 업그레이드할 준비가 되면 사용자를 개별적으로 업그레이드하거나 테넌트 전체 정책<sup>3을</sup>사용하여 전체 테넌트를 한 번 업그레이드할 수 있습니다. 사용자가 TeamsOnly 모드로 업그레이드된 후 Teams에서 들어오는 모든 채팅 및 통화를 수신합니다.

그러나 제도 모드에서 업그레이드되지 않은 받는 사람은 비즈니스용 Skype 또는 Teams 클라이언트에서 TeamsOnly 사용자로부터 채팅 및 통화를 계속 받을 수 있습니다. 기존 대화의 경우 TeamsOnly 사용자는 보낸 사람이 채팅 또는 통화를 시작한 클라이언트에 회신합니다. 

TeamsOnly 사용자의 새로운 보기에서 새로운 대화의 경우 채팅 또는 통화는 항상 제도 모드 사용자 Teams 클라이언트로 이동됩니다. Teams 클라이언트가 동일한 사용자에 대해 Teams 간 및 Teams-To-Business 통신을 위해 별도의 대화 스레드를 유지 관리하기 때문에입니다. 자세한 내용은 Teams 대화 - Interop 및 네이티브 [스레드를 참조합니다.](upgrade-to-teams-on-prem-coexistence.md#teams-conversations---interop-versus-native-threads)

다음 표에서는 제도 모드와 TeamsOnly 모드 모두에 대한 Teams 환경을 요약합니다.

| Teams 환경 | 제도 모드에서 | TeamsOnly 모드에서 |
|:------------------ | :------------------- | :------------------ |
| 수신된 채팅 및 통화:|  Teams 또는 비즈니스용 Skype | Teams |
| 수신된 PSTN 호출: | 비즈니스용 Skype <br>(Teams에서 PSTN 기능을 사용하는 것은 제도 모드에서는 지원되지 않습니다.)     | Teams |   
 |현재 상태    | 비즈니스용 Skype 및 Teams의 현재 상태는 독립적입니다. 사용자는 사용하는 클라이언트에 따라 동일한 제도 사용자에 대해 서로 다른 주를 볼 수 있습니다. | 현재 상태는 Teams에서 사용자의 활동만 기반으로 합니다. 사용하는 클라이언트에 관계없이 다른 모든 사용자는 해당 현재 상태입니다. | 
 | 모임일정    | 사용자는 Teams 또는 비즈니스용 Skype에서 모임을 예약할 수 있습니다. 기본적으로 Outlook에 두 추가 기능을 모두 볼 수 있습니다. Teams 모임 정책을 설정하여 사용자가 Teams 모임 추가 기능만 사용할 수 있는지 아니면 Teams 모임과 비즈니스용 Skype 모임 추가 기능을 모두 사용할 수 있는지 여부를 제어할 수 있습니다. 자세한 내용은 제도 모드에서 사용자에 대한 모임 [공급자 설정을 참조하세요.](meeting-policies-in-teams.md#meeting-policy-settings---meeting-provider-for-islands-mode) |     사용자는 Teams에서만 모임을 예약합니다. Teams 추가 기능만 Outlook에서 사용할 수 있습니다. | 

다음 표에는 겹치는 기능 방법을 사용하여 조직을 Teams로 마이그레이션할 때의 장단점에 대해 요약되어 있습니다.

| Pros     |       Cons |
| :------------------ | :---------------- |
| 조직 내에서 신속한 채택을 허용합니다.| 유사한 기능이 있지만 다른 사용자 인터페이스가 있는 두 개의 클라이언트가 있기 때문에 최종 사용자 혼동 가능성이 있습니다. 또한 들어오는 채팅/통화가 들어오는 클라이언트를 제어할 수 없습니다. |
| 사용자가 비즈니스용 Skype에 대한 모든 권한을 하면서 Teams를 배우고 익히는 데 사용할 수 있습니다. | 사용자가 두 클라이언트를 모두 실행하지 않는 경우 부재 중 메시지로 인해 최종 사용자 불만이 발생할 수 있습니다.|
| Teams에서 시작하기 위한 최소한의 관리 노력. | 사용자와 정기적으로 통신하는 사용자가 Teams를 사용하지 않는 경우 "제도에서 나갑니다" 모드를 사용하고 TeamsOnly 모드로 전환하기가 어려울 수 있습니다.|
|사용자가 기능을 활용하여 비즈니스용 Skype에서 사용할 수 없는 팀워크를 향상시킬 수 있습니다.| 비즈니스용 Skype를 사용하는 사용자가 프레미스 및 Teams에서 비즈니스용 Skype를 사용하고 있지만 Teams가 없는 다른 사용자와 Teams에서 통신할 수 없습니다.  |

<sup>2</sup> 사용자가 비즈니스용 Skype Server의 홈인 경우라도 마찬가지입니다. 사용자가 현재 전체 Teams 기능에 필요하기 때문에 사용자가 홈 또는 온라인에 있는 경우 비즈니스용 Skype Online 라이선스를 사용하도록 설정합니다.

<sup>3</sup> 비즈니스용 Skype 모임을 Teams 모임으로 마이그레이션하는 것은 테넌트별이 아닌 개별 사용자에게 TeamsUpgradePolicy를 적용할 때만 트리거됩니다. 자세한 [내용은 모임 마이그레이션을](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms) 참조합니다.

## <a name="select-capabilities-method-using-skype-for-business-modes"></a>기능 선택 방법(비즈니스용 Skype 모드 사용)

일부 조직에서는 조직이 비즈니스용 Skype에서 Teams로 전환될 때 최종 사용자에게 보다 예측 가능한 환경을 제공할 수 있습니다. 이 모델에서 IT 관리자는 TeamsOnly 모드로 마이그레이션하기 전에 TeamsUpgradePolicy의 비즈니스용 Skype 모드 중 하나를 사용하여 비즈니스용 Skype에 남아 있는 기능을 명시적으로 지정합니다. 선택한 기능을 TeamsOnly 모드로 전환할 준비가 됐을 때 관리자는 해당 사용자의 모드를 TeamsOnly로 업데이트합니다. 이 전환 중:

- 관리자는 사용자가 TeamsOnly 환경으로 이동하기 전에 비즈니스용 Skype에서 채팅 및 통화 기능을 유지하면서 특정 Teams 기능을 사용하도록 설정할 수 있습니다. 관리는 Teams 공동 작업 기능 또는 Teams 모임 + 공동 작업 기능을 사용하도록 설정할 수 있습니다.

- 비즈니스용 Skype를 사용 중이신 사용자는 다른 사용자의 Teams 또는 비즈니스용 Skype 클라이언트에서 시작된 통신 여부에 관계없이 비즈니스용 Skype 클라이언트에서 들어오는 모든 채팅 및 통화를 수신합니다. 또한 이러한 비즈니스용 Skype 사용자의 경우 Teams 클라이언트의 통화 및 채팅 기능은 최종 사용자의 혼동을 방지하고 적절한 라우팅 및 현재 상태 확인을 위해 비활성화됩니다.

- TeamsOnly 모드의 사용자는 Teams 클라이언트에서 들어오는 모든 채팅 및 통화를 받고, 현재 상태는 Teams, 비즈니스용 Skype 또는 모든 종류의 페더러드 사용자로부터 시작된 통신 위치와 관계없이 Teams에서 제공됩니다.

겹치는 기능 방법과 달리, 선택 기능 방법에서는 비즈니스용 Skype를 사용하는 사용자가 TeamsOnly에 있는 사용자와 통신할 수 있습니다. 비즈니스용 Skype 사용자와 Teams 사용자 간의 통신을 상호 연동성 [또는](upgrade-to-Teams-on-prem-coexistence.md#interoperability) "interop"이라고 합니다. 상호 통신은 비즈니스용 Skype 사용자와 Teams의 다른 사용자 간에 채팅 및 통화를 위해 일대일로 가능합니다. 또한 초대된 사용자는 항상 비즈니스용 Skype 또는 Teams 모임에 참가할 수 있습니다. 그러나 모임 유형에 해당하는 클라이언트를 사용해야 합니다. 자세한 내용은 모임을 [참조하세요.](upgrade-to-Teams-on-prem-coexistence.md#meetings)

선택 기능 메서드의 사용자의 경우 다른 사용자가 사용하는 클라이언트에 관계없이 사용자에 대한 현재 상태는 일관됩니다. 사용자가 비즈니스용 Skype 모드 중 하나에 있는 경우 다른 모든 사용자는 비즈니스용 Skype에서 해당 사용자의 활동을 기반으로 현재 상태 표시를 볼 수 있습니다. 마찬가지로 사용자가 TeamsOnly 모드에 있는 경우 다른 모든 사용자는 Teams에서 해당 사용자의 활동을 기반으로 하여 현재 상태 표시를 볼 수 있습니다. 자세한 내용은 현재 상태 [를 참조합니다.](upgrade-to-Teams-on-prem-coexistence.md#presence)

선택 기능 방법을 따르기로 선택한 조직의 경우 관리자는 테넌트 전체 모드를 아일랜드에서 적절한 비즈니스용 Skype 공존 모드(SfbWithTeamsCollab 또는 SfBWithTeamsCollabAndMeetings)로 변경해야 합니다.  

게스트 사용자 환경은 테넌트에 할당된 공존 모드를 준수합니다. 테넌트 수준에서 비즈니스용 Skype 모드를 설정한 경우 게스트는 채팅, 통화 또는 현재 상태 표시를 할 수 없습니다. 자세한 내용은 [Teams의 게스트 액세스](guest-access.md)를 참조하세요.

모드가 Islands에서 SfbWithTeamsCollab으로 변경될 때 Teams를 사용한 적이 없는 사용자는 비즈니스용 Skype를 사용하는 방법에 차이가 없습니다. 그러나 해당 사용자가 Teams를 사용하기 시작하면 Teams & 채널 및 파일과 같은 기능에만 노출됩니다. 관리자가 해당 기능에 대해 원하는 클라이언트로 비즈니스용 Skype를 지정하기 때문에 Teams에서는 채팅, 통화 및 모임을 사용할 수 없습니다.

> [!NOTE]
> 사용자 A가 제도에서 비즈니스용 Skype 모드 중 하나로 변경된 경우 사용자 A와 통신하는 다른 사용자의 Teams 클라이언트는 사용자 A의 모드가 변경된 것을 알고 사용자 A에 대한 적절한 클라이언트로 통신을 라우팅할 수 있습니다. 사용자 A와의 기본 Teams-Teams 채팅을 이미 설정한 모든 사용자의 경우 다른 사용자의 Teams 클라이언트가 제도에서 비즈니스용 Skype 모드로 모드 변경을 인식하는 데 시간이 걸릴 수 있습니다. 관리자가 준비되면 사용자의 모드를 TeamsOnly로 업데이트하여 특정 사용자에 대한 채팅, 통화 및 모임 예약을 Teams로 동시에 전환할 수 있습니다.

또는 관리자는 먼저 SfBWithTeamsCollabAndMeetings 모드를 사용하여 비즈니스용 Skype에서 채팅 및 통화 기능을 나가는 동안 모임 예정만 Teams로 전환할 수 있습니다. 이 모드를 사용하면 조직에서 모임을 위해 Teams로 전환할 수 있습니다. 사용자가 TeamsOnly 모드로 이동할 준비가 되지 않은 경우(예: 기존 PSTN 기능을 아직 마이그레이션할 준비가 되지 않은 경우). 이 전환 시나리오를 모임 [우선이라고 합니다.](meetings-first.md)


|Teams 환경  |SfBWithTeamsCollab 모드에서 |SfBWithTeamsCollabAndMeetings 모드에서 |TeamsOnly 모드에서  |
|---------|---------|---------|---------|
|조직 내 사용자로부터 수신된 채팅 및 VOIP 통화:     | 비즈니스용 Skype        | 비즈니스용 Skype       | Teams        |
|수신된 PSTN 호출:     | 비즈니스용 Skype        |비즈니스용 Skype         | Teams        |
|현재 상태     | 비즈니스용 Skype        |비즈니스용 Skype         | Teams        |
|모임일정     | 비즈니스용 Skype         | Teams        | Teams        |


다음 표에서는 비즈니스용 Skype 모드를 TeamsOnly 모드로 전환하는 단계로 사용하는 장단점에 대해 요약합니다.

| Pros     |       Cons |
| :------------------ | :---------------- |
| 최종 사용자에 대한 예측 가능한 라우팅입니다. 모든 통화 및 채팅은 관리자 선택에 따라 비즈니스용 Skype 또는 Teams(둘 다 아우는 것)에 있습니다.|Interop 대화에는 풍부한 텍스트, 파일 공유 및 화면 공유가 지원되지 않습니다. 모임을 시작하는 데 모임 시작 기능을 활용하는 경우 이 작업을 할 수 있습니다. |
|주어진 기능은 한 클라이언트에서만 사용할 수 있기 때문에 최종 사용자 혼동을 줄일 수 있습니다. | 사용자는 TeamsOnly로 업그레이드하기 전 채팅 및 통화와 같은 비즈니스용 Skype에서 수행되는 일반적인 활동을 위해 Teams에 액세스할 수 없습니다.|
|관리자는 비즈니스용 Skype에서 Teams로 전환하는 동안 사용자가 사용할 수 있는 기능 집합에 대한 제어를 강화했습니다. | |
| 아직 TeamsOnly 모드로 완전히 이동할 준비가 되지 않은 경우에도 조직에서 모임에 Teams를 사용할 수 있습니다.||
|다른 사용자가 본 주어진 사용자의 현재 상태는 사용하는 클라이언트에 관계없이 동일합니다.||

## <a name="summary-of-upgrade-methods"></a>업그레이드 방법 요약
다음 표에서는 업그레이드 방법을 요약합니다.


|겹치는 기능(제도 모드 사용)  |선택한 기능(비즈니스용 Skype 모드 사용)  |
|---------|---------|
|TeamsOnly로 업그레이드하기 전에 수신 채팅 및 통화가 두 클라이언트에 모두 연결될 수 있도록 두 클라이언트를 동시에 실행해야 합니다.     | 채팅 및 통화는 받는 사람의 모드에 따라 하나의 클라이언트에만 있습니다. 업그레이드되지 않은 사용자는 두 클라이언트를 모두 실행할 수 있지만 기능 겹침이 없습니다(Teams에서는 통화 및 채팅을 사용할 수 없음).         |
|관리자가 비즈니스용 Skype와 Teams의 겹치는 기능(채팅, 모임, VOIP 통화)을 최종 사용자에게 소개하고 Teams의 새로운 기능(Teams 및 채널)을 소개할 수 있습니다.     | 관리자가 비즈니스용 Skype에도 존재하는 동일한 기능을 제공하지 않고도 최종 사용자(Teams 및 채널)에게 Teams의 선택된 기능을 소개할 수 있습니다.        |
|두 사용자가 모두 제도 모드에 있는 동안에는 비즈니스용 Skype와 Teams 간의 Interop이 존재하지 않습니다.      |비즈니스용 Skype와 Teams 사용자 간의 통신에는 Interop이 필요합니다.         |

> [!NOTE]
> 비즈니스용 Skype Server 사용자를 Teams로 마이그레이션하기 위해 지원되는 방법을 따를 수 없는 경우 Active Directory에서 비즈니스용 Skype Server 및 모든 관련 사용자 특성을 제거하여 사용자를 Teams로 전환할 수 있습니다. 사용자가 비즈니스용 Skype Server 특성의 지우고 DNS 레코드가 Microsoft 365 또는 Office 365로 다시 포인터가 추가된 경우 Microsoft 365 또는 Office 365의 사용자에게 라이선스를 부여하고 Teams로 업그레이드할 수 있습니다. 

> [!IMPORTANT]
> 인계 마이그레이션을 통해 연락처 데이터 및 모임 데이터는 프레미스 환경에서 Microsoft Teams로 마이그레이션되지 않습니다.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>의사 결정 지점</td><td><ul> 조직의 비즈니스 요구 사항에 적합한 업그레이드 여정은 무엇입니까?<br><br></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next step"/><br/>다음 단계</td><td><ul> 현재 배포 모델, 사용 사례 시나리오 및 조직의 주요 고려 사항을 식별하면 조직에 가장 적합한 Teams로의 여정을 알릴 수 있습니다.<br><br></ul></td></tr>
</table>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>의사 결정 지점</td><td><ul> 조직에 적용할 수 있는 업그레이드 시나리오는 무엇입니까?<br><br></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>다음 단계</td><td><ul> 메시징, 모임 및 비즈니스 요구 사항 호출에 따라 조직의 업그레이드 여정의 타임라인을 결정하세요.<br><br> 업그레이드 여정을 완료하는 데 필요한 추가 작업을 결정하세요.<br><br></ul></td></tr>
</table>

조직에 가장 적합한 업그레이드 여정을 선택한 후 [Teams로 업그레이드합니다.](https://aka.ms/SkypeToTeams-Upgrade)
