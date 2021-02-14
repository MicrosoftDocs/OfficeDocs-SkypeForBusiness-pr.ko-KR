---
title: 비즈니스용 Skype-프레미스 배포에서 Teams로 업그레이드 - Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 비즈니스용 Skype에서 Teams로 업그레이드
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2dc8afc48db6264cef5c5ad959f33dd7e738e116
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515795"
---
# <a name="upgrade-methods-mdash-for-it-administrators"></a>IT &mdash; 관리자를 위한 업그레이드 방법

이 문서에서는 Teams로 마이그레이션하기 위한 업그레이드 방법을 설명하고 있습니다. 이 문서는 IT 관리자를 위한 업그레이드 개념 및 구현을 설명하는 몇 가지 중 두 번째 문서입니다.  

- [개요](upgrade-to-teams-on-prem-overview.md)
- **업그레이드 방법(이** 문서)
- [업그레이드를 관리하기 위한 도구](upgrade-to-teams-on-prem-tools.md)
- [비즈니스용 Skype가 있는 조직에 대한 추가 고려 사항](upgrade-to-teams-on-prem-considerations.md)
- [업그레이드 구현](upgrade-to-teams-on-prem-implement.md)
- [PSTN(공용 전환 전화 네트워크) 고려 사항](upgrade-to-teams-on-prem-pstn-considerations.md)

또한 다음 문서에서는 중요한 업그레이드 개념 및 공존 동작을 설명하고 있습니다.

- [Teams 및 비즈니스용 Skype의 공존](upgrade-to-teams-on-prem-coexistence.md)
- [공존 모드 - 참조](migration-interop-guidance-for-teams-with-skype.md)
- [Teams 클라이언트 환경 및 공존 모드 준수](teams-client-experience-and-conformance-to-coexistence-modes.md)


## <a name="upgrade-methods"></a>업그레이드 방법

비즈니스용 Skype를 사용하여 기존 조직을 Teams로 업그레이드하는 방법에는 두 가지가 있습니다( 겹치는 기능 방법 및 기능 선택 방법). 이 문서는 두 방법을 설명하고 각 방법의 장단을 제시하여 조직에 적합한 방법을 선택하는 데 도움이 됩니다. 

- [겹치는 기능 방법(제도 모드 사용)](#overlapping-capabilities-method-using-islands-mode)

   전환 단계에서 두 클라이언트를 모두 사용할 수 있도록 기존 비즈니스용 Skype 조직의 사용자가 Teams에 도입됩니다. 이 기간에는 Teams의 모든 기능을 사용할 수 있지만 대부분의 기능을 사용할 수 있습니다. 이 구성의 모드를 '제도'라고 합니다. 이 모드는 비즈니스용 Skype를 사용 하는 기존 조직의 기본 모드입니다. 조직이 준비되면 관리자가 사용자를 TeamsOnly 모드로 전환합니다.

- [기능 선택 방법(비즈니스용 Skype 모드 중 하나 이상 사용)](#select-capabilities-method-using-skype-for-business-modes)

   관리자는 조직의 사용자에 대한 채팅, 통화 및 모임 계획 기능의 전환(비즈니스용 Skype에서 Teams로)을 관리합니다.  이러한 각 기능은 비즈니스용 Skype 또는 Teams에서 사용할 수 있지만 둘 다 사용할 수 없습니다. 관리자는 TeamsUpgradePolicy를 사용하여 사용자의 이 기능을 Teams로 전환할 때를 제어합니다. 아직 TeamsOnly 모드에 있지 않은 사용자는 채팅 및 통화에 비즈니스용 Skype를 계속 사용하고 두 사용자 집합은 상호Op 기능을 통해 통신할 수 있습니다. 관리자는 더 많은 사용자를 TeamsOnly 모드로 점진적으로 마이그레이션하여 전환을 관리합니다.  

업그레이드 방법을 이해하고 선택한 후 조직의 Teams 업그레이드를 관리하기 [위한 도구에 대해 알 수 있습니다.](upgrade-to-teams-on-prem-tools.md)

## <a name="overlapping-capabilities-method-using-islands-mode"></a>겹치는 기능 방법(제도 모드 사용)

겹치는 기능 방법으로 사용자는 채팅, VoIP 통화 및 모임에 Teams 및 비즈니스용 Skype 클라이언트를 모두 사용할 수 있습니다. 비즈니스용 Skype 및 Teams의 통신 트래픽이 별개로 유지(동일한 사용자에 대해) 두 클라이언트가 서로 통신하지 못하기 때문에 이 상태를 "제도" 모드라고 합니다.(동일한 조직 내의 사용자에 대해) 서로 통신하지 않습니다. 예를 들어 받는 사람 사용자 A가 제도 모드에 있는 것으로 가정합니다.

- 다른 사용자의 비즈니스용 Skype 클라이언트에서 시작된 통신은 항상 사용자 A의 비즈니스용 Skype 클라이언트에 있습니다.

- 다른 사용자의 Teams 클라이언트에서 시작된 통신은 다른 사용자가 동일한 조직에 있는 경우 항상 사용자 A의 Teams *클라이언트에 연결됩니다.* 

- 다른 사용자의 Teams 클라이언트에서 시작된 통신은 다른 사용자가 페더러드 조직에 있는 경우 항상 사용자 A의 비즈니스용 Skype 클라이언트에 *연결됩니다.*

제도 모드는 아직 TeamsOnly로 업그레이드되지 않은 기존 조직에 TeamsUpgradePolicy의 기본 모드입니다. Microsoft 365 또는 Office 365 라이선스를 할당하면 기본적으로 Teams 및 비즈니스용 Skype Online 라이선스가 모두 할당됩니다. (사용자가 비즈니스용 Skype Server의 집을 프레미스에 있는 경우에도 마찬가지입니다. 사용자가 현재 전체 Teams 기능에 필요하기 때문에 사용자가 홈 또는 온라인에 있는 경우 비즈니스용 Skype Online 라이선스를 사용하도록 설정합니다.) 실제로 기본 구성을 변경하는 단계를 수행하지 않은 경우 조직에서 Teams를 이미 대폭 사용할 수 있습니다.  이는 겹치는 기능 접근 방식의 이점 중 하나입니다. 이를 통해 조직 내에서 최종 사용자 중심의 신속한 채택이 허용됩니다.

이 방법을 효과적으로 작동하려면 모든 사용자가 두 클라이언트를 동시에 실행해야 합니다. 조직 내에서 제도 모드의 사용자로 들어오는 채팅 및 통화는 비즈니스용 Skype 또는 Teams 클라이언트에 연결될 수 있으며 받는 사람의 제어 하에 있지 않습니다. 보낸 사람 및 받는 사람이 동일한 조직에 있는 경우 보낸 사람이 통신을 시작하는 데 사용하는 클라이언트에 따라 달라 습니다. 보낸 사람 및 받는 사람이 다른 조직에 있는 경우, 제도 모드에서 사용자에게 수신 전화 및 채팅은 항상 비즈니스용 Skype 클라이언트에 있습니다.  

예를 들어, 제도 모드 받는 사람이 비즈니스용 Skype를 실행 중이지만 Teams는 실행하지 않는 경우 같은 조직의 누군가가 Teams에서 메시지를 보낸 경우, 제도 모드 받는 사람은 메시지를 볼 수 없습니다(하지만 결국에는 Teams에서 메시지를 놓쳤다는 전자 메일이 전송됩니다). 마찬가지로 사용자가 Teams를 실행하고 있지만 비즈니스용 Skype는 실행하고 있지 않은 경우 비즈니스용 Skype의 사용자가 보낸 메시지는 해당 채팅을 볼 수 없습니다.  부재 중 메시지가 있는 전자 메일이 전송됩니다. 이러한 각 경우의 동작은 호출과 유사합니다. 사용자가 두 클라이언트를 모두 실행하지 않는 경우 쉽게 좌절할 수 있습니다.

사용자 A가 제도 모드에 있는 경우 Teams 및 비즈니스용 Skype의 다른 사용자가 볼 수 있는 사용자 A의 현재 상태는 독립적입니다.

- Teams를 사용할 때 다른 사용자는 Teams에서 사용자 A의 활동을 기반으로 하여 현재 상태 표시를 볼 수 있습니다. 
- 비즈니스용 Skype를 사용할 때 다른 사용자는 비즈니스용 Skype에서 사용자 A의 활동을 기반으로 현재 상태 표시를 볼 수 있습니다. 

즉, 다른 사용자가 사용하는 클라이언트에 따라 사용자 A에 대한 다른 현재 상태 표시가 표시될 수 있습니다. 자세한 내용은 현재 상태 [를 참조하세요.](upgrade-to-teams-on-prem-coexistence.md#presence)

사용자를 TeamsOnly 모드로 업그레이드할 준비가 됐을 때 사용자를 개별적으로 업그레이드하거나 테넌트 전체 정책을 사용하여 전체 테넌트를 한 시에 업그레이드할 수 있습니다. 사용자가 TeamsOnly 모드로 업그레이드된 후 Teams에서 들어오는 모든 채팅 및 통화를 수신합니다. (비즈니스용 Skype 모임을 Teams 모임으로 마이그레이션하는 것은 테넌트별이 아닌 개별 사용자에게 TeamsUpgradePolicy를 적용할 때만 트리거됩니다. 자세한 [내용은 모임 마이그레이션을](upgrade-to-teams-on-prem-tools.md#meeting-migration) 참조합니다.)

그러나 제도 모드에서 업그레이드되지 않은 받는 사람은 비즈니스용 Skype 또는 Teams 클라이언트에서 TeamsOnly 사용자로부터 채팅 및 통화를 계속 받을 수 있습니다.  Teams 클라이언트가 동일한 사용자에 대해 Teams 간 및 Teams-To-Business 통신을 위해 별도의 대화 스레드를 유지 관리하기 때문에입니다.  (Teams 대화 - Interop 및 네이티브 [스레드를 참조합니다.)](upgrade-to-teams-on-prem-coexistence.md#teams-conversations---interop-versus-native-threads)  예를 들어, Islands User A가 Teams를 사용하여 TeamsOnly 사용자 B에게 메시지를 보내었다고 가정합니다. 사용자 B가 해당 채팅에 응답하면 통신이 사용자 A의 Teams 클라이언트에 연결됩니다. 이제 사용자 A가 비즈니스용 Skype 클라이언트를 사용하여 TeamsOnly 사용자 B에게 메시지를 보낸 것으로 가정합니다. 사용자 B는 Teams에서 채팅을 받게 되지만 다른 대화와 비교하여 사용자 B의 Teams 클라이언트에서 별도의 대화가 됩니다. 사용자 B가 사용자 A와 이 대화에 회신하면 사용자 A의 비즈니스용 Skype 클라이언트로 연결됩니다. 

다음 표에서는 제도 모드와 TeamsOnly 모드 모두에 대한 Teams 환경을 요약합니다.  

| Teams 환경 | 제도 모드에서 | TeamsOnly 모드에서 |
|:------------------ | :------------------- | :------------------ |
| 수신된 채팅 및 통화:|  Teams 또는 비즈니스용 Skype | Teams |
| 수신된 PSTN 호출: | 비즈니스용 Skype <br>(Teams에서 PSTN 기능을 사용하는 것은 제도 모드에서는 지원되지 않습니다.)    | Teams |   
 |현재 상태  | 비즈니스용 Skype 및 Teams의 현재 상태는 독립적입니다. 사용자는 사용하는 클라이언트에 따라 동일한 제도 사용자에 대해 서로 다른 주를 볼 수 있습니다. | 현재 상태는 Teams에서 사용자의 활동만 기반으로 합니다. 사용하는 클라이언트에 관계없이 다른 모든 사용자는 해당 현재 상태입니다. | 
 | 모임일정   | 기본적으로 사용자는 Teams 또는 비즈니스용 Skype에서 모임을 예약할 수 있습니다. Outlook에 두 추가 기능을 모두 볼 수 있습니다. |   사용자는 Teams에서만 모임을 예약합니다. Teams 추가 기능만 Outlook에서 사용할 수 있습니다. | 

다음 표에는 겹치는 기능 방법을 사용하여 조직을 Teams로 마이그레이션할 때의 장단점에 대해 요약되어 있습니다.

| Pros     |       Cons |
| :------------------ | :---------------- |
| 조직 내에서 신속한 채택을 허용합니다.| 유사한 기능이 있지만 다른 사용자 인터페이스가 있는 두 개의 클라이언트가 있기 때문에 최종 사용자 혼동 가능성이 있습니다. 또한 들어오는 채팅/통화가 들어오는 클라이언트를 제어할 수 없습니다. |
| 사용자가 비즈니스용 Skype에 대한 모든 권한을 하면서 Teams를 배우고 익히는 데 사용할 수 있습니다. | 사용자가 두 클라이언트를 모두 실행하지 않는 경우 부재 중 메시지로 인해 최종 사용자 불만이 발생할 수 있습니다. 사용자는 메시지를 받지 못했다고 불만을 표시할 수 있습니다.|
| Teams에서 시작하기 위한 최소한의 관리 노력. | 조직의 모든 사용자가 Teams를 사용하고 있지 않은 경우 특히 Teams에서 모든 사용자가 활성이 아닌 경우 "제도에서 나갑니다" 모드를 사용하고 TeamsOnly 모드로 전환하기가 어려울 수 있습니다. 예를 들어 사용자의 하위 집합이 TeamsOnly 모드로 업그레이드된 경우 해당 사용자는 Teams에서만 전송됩니다. 제도 모드에서 나머지 모집단의 경우 이러한 메시지는 항상 Teams에 표시됩니다. 하지만 해당 인구 중 일부가 Teams를 실행하지 않는 경우 이러한 메시지를 부재 중 메시지로 인식합니다. |
|  | Teams를 사용하는 경우 비즈니스용 Skype Server에 프레미스 계정이 있는 사용자에게는 Interop 또는 페더전 지원이 없습니다.  이렇게 하여 비즈니스용 Skype Online과 비즈니스용 Skype의 일부에 있는 여러 섬 사용자가 혼합되어 있는 경우 혼동을 주게 될 수 있습니다.   |

## <a name="select-capabilities-method-using-skype-for-business-modes"></a>기능 선택 방법(비즈니스용 Skype 모드 사용)

일부 조직에서는 조직이 비즈니스용 Skype에서 Teams로 전환될 때 최종 사용자에게 보다 간단하고 예측 가능한 환경을 제공할 수 있습니다. 이 모델에서 IT 관리자는 TeamsOnly 모드로 마이그레이션하기 전에 TeamsUpgradePolicy의 비즈니스용 Skype 모드 중 하나를 사용하여 비즈니스용 Skype에 남아 있는 사용자를 명시적으로 지정합니다. 선택한 사용자를 TeamsOnly 모드로 전환할 준비가 되면 관리자는 해당 사용자의 모드를 TeamsOnly로 업데이트합니다. 배포가 진행될수록 비즈니스용 Skype에서 TeamsOnly 모드로 전환되는 사용자도 더 많이 있습니다.  이 전환 중:

- 비즈니스용 Skype를 사용 중이신 사용자는 다른 사용자의 Teams 또는 비즈니스용 Skype 클라이언트에서 시작된 통신 여부에 관계없이 비즈니스용 Skype 클라이언트에서 들어오는 모든 채팅 및 통화를 수신합니다. 또한 이러한 비즈니스용 Skype 사용자의 경우 최종 사용자 혼동을 방지하고 적절한 라우팅을 보장하기 위해 Teams 클라이언트의 통화 및 채팅 기능을 사용할 수 없습니다. 

- TeamsOnly 모드의 사용자는 Teams, 비즈니스용 Skype 또는 모든 종류의 페더러드 사용자로부터 통신이 시작된 위치와 관계없이 Teams 클라이언트에서 들어오는 모든 채팅 및 통화를 수신합니다. 

Islands 방법과 달리, 선택 기능 방법에서는 비즈니스용 Skype 사용자와 TeamsOnly 사용자가 서로 통신할 수 있습니다. 비즈니스용 Skype 사용자와 Teams 사용자 간의 통신을 상호 연동성 또는 "interop"이라고 합니다. 상호 통신은 비즈니스용 Skype 사용자와 Teams의 다른 사용자 간에 채팅 및 통화를 위해 일대일로 가능합니다. 그러나 일부 고급 기능을 사용할 수 없습니다. (상호 [연동성 참조)](upgrade-to-teams-on-prem-coexistence.md#interoperability) 또한 초대된 사용자는 항상 비즈니스용 Skype 또는 Teams 모임에 참가할 수 있습니다. 그러나 모임 유형에 해당하는 클라이언트를 사용해야 합니다. 자세한 내용은 모임을 [참조하세요.](upgrade-to-teams-on-prem-coexistence.md#meetings)

선택 기능 전환의 사용자는 일반적으로 제도 모드가 아니기 때문에 다른 사용자가 사용하는 클라이언트에 관계없이 사용자의 현재 상태는 일관됩니다. 사용자가 비즈니스용 Skype 모드 중 하나에 있는 경우 다른 모든 사용자는 비즈니스용 Skype에서 해당 사용자의 활동을 기반으로 현재 상태 표시를 볼 수 있습니다. 마찬가지로 사용자가 TeamsOnly 모드에 있는 경우 다른 모든 사용자는 Teams에서 해당 사용자의 활동을 기반으로 하여 현재 상태 표시를 볼 수 있습니다. 자세한 내용은 현재 상태 [를 참조합니다.](upgrade-to-teams-on-prem-coexistence.md#presence)

아직 Teams 사용을 시작하지 않은 조직의 경우 관리자는 테넌트 전체 모드를 Islands에서 SfbWithTeamsCollab으로 변경해야 합니다. (이미 Teams 사용량이 있는 조직의 경우 관리자는 Teams에서 이미 활성 상태인 사용자를 "할아버지"에게 "조부"하여 이 변경이 적용되지 않도록 해야 합니다. 자세한 내용은 이미 제도 모드에서 Teams를 사용하고 있는 조직의 A 선택 기능 [방법을 참조합니다.](upgrade-to-teams-on-prem-implement.md#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)

모드가 Islands에서 SfbWithTeamsCollab으로 변경될 때 Teams를 사용한 적이 없는 사용자는 비즈니스용 Skype를 사용하는 방법에 차이가 없습니다. 그러나 해당 사용자가 Teams를 사용하기 시작하면 Teams & 채널 및 파일과 같은 기능에만 노출됩니다. 관리자가 해당 기능에 대해 원하는 클라이언트로 비즈니스용 Skype를 지정하기 때문에 Teams에서는 채팅, 통화 및 모임을 사용할 수 없습니다.  

참고: 사용자 A가 제도에서 비즈니스용 Skype 모드 중 하나로 변경하는 경우 사용자 A와 통신하는 다른 사용자의 Teams 클라이언트는 사용자 A의 모드가 변경된 것을 알고 사용자 A에 대한 적절한 클라이언트로 통신을 라우팅할 수 있습니다.  사용자 A와의 기본 Teams-Teams 채팅을 이미 설정한 사용자의 경우 다른 사용자의 Teams 클라이언트가 제도에서 비즈니스용 Skype 모드로 모드 변경을 인식하는 데 최대 36시간이 걸릴 수 있습니다.   반면에 기존 사용자를 TeamsOnly 모드로 변경한 내용은 2시간 이내에 다른 클라이언트에서 검색됩니다.

관리자가 준비되면 사용자의 모드를 TeamsOnly로 업데이트하여 특정 사용자에 대한 채팅, 통화 및 모임 예약을 Teams로 동시에 전환할 수 있습니다.  

또는 관리자는 먼저 SfBWithTeamsCollabAndMeetings 모드를 사용하여 비즈니스용 Skype에서 채팅 및 통화 기능을 나가는 동안 모임 예정만 Teams로 전환할 수 있습니다. 이 모드를 사용하면 사용자가 TeamsOnly 모드로 이동할 준비가 되지 않은 경우(일반적으로 기존 PSTN 기능을 마이그레이션하는 데 더 많은 시간이 필요할 수 있기 때문에) 조직에서 모임을 위해 Teams로 전환할 수 있습니다. 이 전환 시나리오를 모임 [우선이라고 합니다.](meetings-first.md)

다음 표에서는 비즈니스용 Skype 모드를 TeamsOnly 모드로 전환하는 단계로 사용하는 장단점에 대해 요약합니다.


| Pros     |       Cons |
| :------------------ | :---------------- |
| 최종 사용자에 대한 예측 가능한 라우팅입니다.  모든 통화 및 채팅은 관리자 선택에 따라 비즈니스용 Skype 또는 Teams(둘 다 아우는 것)에 있습니다.  | Interop 대화에는 풍부한 텍스트, 파일 공유 및 화면 공유가 지원되지 않습니다.  이는 수요가 있는 모임에서 해결될 수 있지만 원활하지는 않습니다.  |
| 주어진 기능을 한 클라이언트에서만 사용할 수 있기 때문에 최종 사용자 혼동을 제거합니다.  | 사용자는 동일한 기능 집합에 대해 두 클라이언트를 나란히 시도할 수 없습니다. 이는 사용자가 비즈니스용 Skype에서 Teams로의 전환을 주요 패러다임 전환으로 인식하는 경우 특히 그 요인이 될 수 있습니다. |
| Teams를 증분 도입할 수 있습니다.  |  | |
| 관리자는 비즈니스용 Skype에서 Teams로의 전환을 전제로 합니다. |  | | 
| 아직 TeamsOnly 모드로 완전히 이동할 준비가 되지 않은 경우에도 조직에서 모임에 Teams를 사용할 수 있습니다. |  | |
| 다른 사용자가 본 주어진 사용자의 현재 상태는 사용하는 클라이언트에 관계없이 동일합니다.  |  | |

## <a name="summary-of-upgrade-methods"></a>업그레이드 방법 요약

다음 표에서는 업그레이드 방법을 요약합니다.

| 겹치는 기능(제도 모드 사용)     |      기능 선택(비즈니스용 Skype 모드 사용) |
| :------------------ | :---------------- |
| TeamsOnly로 업그레이드하기 전에 수신 채팅 및 통화가 두 클라이언트에 모두 연결될 수 있도록 두 클라이언트를 동시에 실행해야 합니다.   | 채팅 및 통화는 받는 사람의 모드에 따라 하나의 클라이언트에만 있습니다. 업그레이드되지 않은 사용자는 두 클라이언트를 모두 실행할 수 있지만 기능 겹침이 없습니다(Teams에서는 통화 및 채팅을 사용할 수 없음).  관리자는 사용자가 Teams 또는 비즈니스용 Skype에서 모임을 예약하는지 여부를 제어할 수도 있습니다.   |
| 사용자는 동일한 기능을 위해 비즈니스용 Skype와 Teams를 나란히 사용할 수 있습니다.   | 관리자가 비즈니스용 Skype에도 존재하는 동일한 기능을 제공하지 않고도 최종 사용자(Teams 및 채널)에게 Teams의 새로운 기능을 소개할 수 있습니다.   |
|두 사용자가 모두 제도 모드에 있는 동안에는 비즈니스용 Skype와 Teams 간의 Interop이 존재하지 않습니다. 일부 사용자가 TeamsOnly로 업그레이드된 후 해당 사용자와 여전히 제도 모드에 있는 다른 사용자 간에 상호 운영 대화가 발생할 수 있습니다. 그러나 제도 사용자는 Teams를 사용하여 상호 대화를 피할 수 있습니다. | 비즈니스용 Skype와 Teams 사용자 간의 통신에는 Interop이 필요합니다.   |


## <a name="related-links"></a>관련 링크

[비즈니스용 Skype와 함께 Teams를 사용하는 조직을 위한 마이그레이션 및 상호 연동성 지침](migration-interop-guidance-for-teams-with-skype.md) 

[비즈니스용 Skype Server와 Microsoft 365 또는 Office 365 간의 하이브리드 연결 구성](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[온-프레미스와 클라우드 간에 사용자 이동](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[공존 및 업그레이드 설정 설정](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[MMS(모임 마이그레이션 서비스) 사용](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

