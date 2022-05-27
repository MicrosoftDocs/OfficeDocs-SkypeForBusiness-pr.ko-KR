---
title: 최전방 직원을 위한 맞춤형 Teams 앱
author: LanaChin
ms.author: v-lanachin
ms.reviewer: aaglick
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Teams 일선 작업자를 위한 맞춤형 앱 환경에 대해 알아봅니다.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: b59753e1ad1e5a0be36ed8a0d924d7fa6d6658a2
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675520"
---
# <a name="tailor-teams-apps-for-your-frontline-workers"></a>최전방 직원을 위한 맞춤형 Teams 앱

> [!NOTE]
> 이 기능은 현재 배포 중이며 조직에서 아직 제공되지 않을 수 있습니다. 예정된 Teams 기능을 계속 활용하려면 [Microsoft 365 로드맵](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams)을 확인하세요.

## <a name="overview"></a>개요

Teams 라이선스에 따라 앱을 고정하여 일선 근로자에게 요구 사항에 맞는 Teams 기본 제공 환경을 제공합니다. 

맞춤형 최전방 앱 환경을 통해 최전방 작업자는 관리자에게 필요한 조치 없이 Teams 가장 관련성이 큰 앱을 얻을 수 있습니다.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4VuCH]

## <a name="tailored-frontline-app-experience"></a>맞춤형 최전방 앱 환경

앱은 Teams 모바일 클라이언트(iOS 및 Android)의 아래쪽과 Teams 데스크톱 클라이언트의 측면에 있는 막대인 앱 바에 고정됩니다. 다음 앱은 [F 라이선스](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt)가 있는 사용자에 대해 고정됩니다.

- [활동](https://support.microsoft.com/office/explore-the-activity-feed-in-teams-91c635a1-644a-4c60-9c98-233db3e13a56)
- [채팅](https://support.microsoft.com/office/get-started-with-chat-0b506ce2-eb6d-4fca-9668-e56980ba755e)
- [Teams](https://support.microsoft.com/office/teams-and-channels-in-microsoft-teams-c6d0e61d-a61e-44a6-a972-04f2a8fa4155)
- [워키토키](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [작업](https://support.microsoft.com/office/use-the-tasks-app-in-teams-e32639f3-2e07-4b62-9a8c-fd706c12c070)
- [교대 근무](https://support.microsoft.com/office/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821)
- [승인](https://support.microsoft.com/office/what-is-approvals-a9a01c95-e0bf-4d20-9ada-f7be3fc283d3)

**모바일 Teams**

:::image type="content" source="media/tailored-teams-apps-mobile.png" alt-text="Teams 모바일의 맞춤형 최전방 앱 환경" lightbox="media/tailored-teams-apps-mobile.png"::: 

**Teams 데스크톱**

:::image type="content" source="media/tailored-teams-apps-desktop.png" alt-text="Teams 데스크톱의 맞춤형 최전방 앱 환경" lightbox="media/tailored-teams-apps-desktop.png"::: 

## <a name="admin-controls"></a>관리 컨트롤

> [!NOTE]
> 이 기능을 적용하려면 전역(조직 전체 기본) [앱 설정 정책](teams-app-setup-policies.md)에서 **사용자 고정** 설정을 설정해야 합니다.

맞춤형 최전방 앱 환경은 Teams 관리 센터의 앱 [관리](manage-apps.md#manage-org-wide-app-settings) 페이지에서 **맞춤형 앱** 조직 전체 앱 설정에 의해 제어됩니다. 기능이 켜진 경우 F 라이선스가 있는 조직의 모든 사용자는 맞춤형 앱 환경을 얻게 됩니다.

사용자에게 할당된 모든 사용자 지정 [앱 설정 정책이](teams-app-setup-policies.md) 우선합니다. 즉, 사용자에게 사용자 지정 앱 설정 정책이 이미 할당된 경우 사용자는 사용자 지정 앱 설정 정책에 정의된 구성을 가져옵니다. 글로벌 앱 설정 정책을 포함하여 Teams 앱 정책에서 기능이 작동하는 방식에 대한 자세한 내용은 이 문서의 뒷부분에 있는 [시나리오](#scenarios) 섹션을 참조하세요.

이 기능은 기본적으로 켜져 있습니다. 그러나 Microsoft에서 제공하는 맞춤형 최전방 앱 환경을 원하지 않는 경우 이 기능을 해제할 수 있습니다. 기능을 끄거나 켜려면:

1. Microsoft Teams 관리 센터의 왼쪽 탐색에서 **Teams 앱****관리 앱** > 으로 이동한 다음 **조직 전체 앱 설정을** 선택합니다.
2. **맞춤형 앱** 에서 **맞춤 앱 표시** 토글을 **끄** 거나 켜기로 전환 **합니다**.

    :::image type="content" source="media/tailored-teams-apps-admin-center.png" alt-text="Teams 관리 센터의 앱 관리 페이지에 있는 맞춤형 앱 표시 설정 스크린샷" lightbox="media/tailored-teams-apps-admin-center.png":::

## <a name="scenarios"></a>시나리오

### <a name="how-does-the-tailored-frontline-app-experience-affect-my-global-app-setup-policy"></a>맞춤형 최전방 앱 환경이 글로벌 앱 설정 정책에 어떤 영향을 주나요?

맞춤형 최전방 앱 환경이 글로벌 앱 설정 정책과 함께 작동하는 방법을 알아봅니다. 이 표의 시나리오는 **사용자 고정** 이 켜져 있는 F 라이선스 및 글로벌 앱 설정 정책이 있는 일선 작업자에게 적용됩니다.

|경우... |다음... |
|---------|---------|
|일선 작업자는 전역 앱 설정 정책을 가지고 있으며 기능이 꺼져 있습니다. |최전방 작업자는 전역 앱 설정 정책에 정의된 앱을 가져옵니다.|
|일선 작업자는 전역 앱 설정 정책을 가지고 있으며 기능이 켜집니다.     | 최전방 작업자는 맞춤형 최전방 앱 환경을 가져옵니다. 전역 앱 설정 정책에 정의된 앱은 맞춤형 앱 아래에 고정됩니다.      |
|전역 앱 설정 정책을 업데이트하고 기능이 켜집니다.     |일선 작업자는 맞춤형 최전방 앱 환경을 가져오고 전역 앱 설정 정책에 정의된 앱은 맞춤형 앱 아래에 고정됩니다.         |
|일선 작업자는 전역 앱 설정 정책을 가지고 있으며 **사용자 고정** 이 꺼져 있습니다. |최전방 작업자는 전역 앱 설정 정책에 정의된 앱을 가져옵니다.|
|일선 작업자는 전역 앱 설정 정책을 가지고 있으며, 글로벌 앱 설정 정책은 앱 목록의 두 번째 위치에 LOB(기간 업무) 앱을 포함하도록 변경됩니다. |LOB 앱은 맞춤형 앱 아래에 고정됩니다. 일선 작업자는 **사용자 고정** 이 켜진 경우 앱 순서를 변경할 수 있습니다.         |
|일선 작업자는 전역 설정 정책을 가지고 있으며 전역 앱 설정 정책이 첫 번째 위치에 Shifts를 포함하도록 변경됩니다.  |시프트는 맞춤형 최전방 앱 환경에 정의된 대로 여섯 번째 위치에 고정됩니다. 일선 작업자는 **사용자 고정** 이 켜진 경우 앱 순서를 변경할 수 있습니다.          |

### <a name="how-does-the-tailored-frontline-app-experience-work-with-other-teams-app-policies"></a>맞춤형 최전방 앱 환경은 다른 Teams 앱 정책과 어떻게 작동하나요?

맞춤형 최전방 앱 환경이 다른 Teams 앱 정책과 어떻게 작동하는지 알아봅니다.

|경우...  |다음... |
|---------|---------|
기능이 꺼져 있습니다.   | 일선 작업자는 전역 앱 설정 정책 또는 할당된 사용자 지정 앱 설정 정책에 정의된 앱을 가져옵니다.          |
|일선 작업자는 사용자 지정 앱 설정 정책을 가지고 있으며 기능이 켜집니다.    |일선 작업자는 사용자 지정 앱 설정 정책에 정의된 앱을 가져옵니다.          |
|사용자 또는 조직에 맞게 조정된 최전방 앱 환경의 앱이 차단됩니다.      |맞춤형 최전방 앱 환경은 [앱 사용 권한 정책을](teams-app-permission-policies.md) 적용합니다. 앱이 차단되면 최전방 작업자가 차단된 앱을 볼 수 없습니다.           |
|맞춤형 최전방 앱 환경의 앱은 이미 앱 설정 정책에 정의되어 있으며 기능이 켜집니다. |앱은 맞춤형 앱 목록에서 정의한 순서에 따라 고정됩니다.        |
|사용자에게 E, A 또는 G 라이선스가 있고 기능이 켜집니다.   | 사용자는 맞춤형 최전방 앱 환경을 얻지 못합니다. 현재 이 환경은 F 라이선스가 있는 사용자에게만 적용됩니다.        |

> [!NOTE]
> 맞춤형 최전방 앱 환경에서는 앱 또는 앱의 순서를 변경할 수 없습니다. 지금은 변경하려는 경우 사용자 지정 환경을 직접 설정할 수 있습니다. 이렇게 하려면 먼저 기능을 끕니다. 그런 다음 [사용자 지정 앱 설정 정책을 만들고](teams-app-setup-policies.md) [사용자 또는 그룹에 할당](assign-policies-users-and-groups.md)합니다.

## <a name="related-articles"></a>관련 기사

- [Teams Walkie Talkie 앱 관리](walkie-talkie.md)
- [Teams 작업 앱 관리](manage-tasks-app.md)
- [Teams Shifts 앱 관리](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)
- [Teams 승인 앱 관리](approval-admin.md)
- [Teams에서 앱 설정 정책 관리](teams-app-setup-policies.md)
- [Teams에서 앱 사용 권한 정책 관리](teams-app-permission-policies.md)
