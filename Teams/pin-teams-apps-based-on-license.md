---
title: 프런트 Teams 앱 맞춤 설정
author: LanaChin
ms.author: v-lanachin
ms.reviewer: aaglick
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 고객사 일선 근로자에 대한 맞춤형 앱 Teams.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: b526733558570e4903d9dce43094c7ffa0f7de17
ms.sourcegitcommit: b91d83739a078b175770c797c17d602eb5c83a4f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2022
ms.locfileid: "63774187"
---
# <a name="tailor-teams-apps-for-your-frontline-workers"></a>프런트 Teams 앱 맞춤 설정

> [!NOTE]
> [!INCLUDE [new-feature-coming-soon-section](includes/new-feature-coming-soon-section.md)]

## <a name="overview"></a>개요

Teams 작업자를 위한 앱을 쉽게 고정할 수 있습니다. 이 기능은 라이선스에 따라 앱을 고정하여 프런트라인 작업자에게 요구에 맞게 Teams 바로 사용할 수 있는 환경을 제공합니다.

맞춤형 프런트라인 앱 환경을 통해 프런트라인 작업자는 관리자에게 필요한 조치 없이 Teams 가장 관련성이 높은 앱을 제공합니다.

## <a name="tailored-frontline-app-experience"></a>맞춤형 프런트라인 앱 환경

앱은 앱 표시줄에 고정되어 있으며, 이 막대는 Teams(iOS 및 Android) 및 데스크톱 클라이언트의 Teams 있습니다. F 라이선스가 있는 사용자를 위해 다음 앱이 [고정됩니다](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt).

- [활동](https://support.microsoft.com/office/explore-the-activity-feed-in-teams-91c635a1-644a-4c60-9c98-233db3e13a56)
- [채팅](https://support.microsoft.com/office/get-started-with-chat-0b506ce2-eb6d-4fca-9668-e56980ba755e)
- [Teams](https://support.microsoft.com/office/teams-and-channels-in-microsoft-teams-c6d0e61d-a61e-44a6-a972-04f2a8fa4155)
- [워키토키](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [작업](https://support.microsoft.com/office/use-the-tasks-app-in-teams-e32639f3-2e07-4b62-9a8c-fd706c12c070)
- [교대 근무](https://support.microsoft.com/office/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821)
- [승인](https://support.microsoft.com/office/what-is-approvals-a9a01c95-e0bf-4d20-9ada-f7be3fc283d3)

**Teams 모바일**

:::image type="content" source="media/tailored-teams-apps-mobile.png" alt-text="모바일에서 맞춤형 프런트라인 앱 Teams 경험" lightbox="media/tailored-teams-apps-mobile.png"::: 

**Teams 데스크톱**

:::image type="content" source="media/tailored-teams-apps-desktop.png" alt-text="데스크톱에서 맞춤형 프런트라인 앱 Teams 환경" lightbox="media/tailored-teams-apps-desktop.png"::: 

## <a name="admin-controls"></a>관리자 컨트롤

> [!NOTE]
> 이 **기능을** 적용하려면 전역(org-wide [default) 앱](teams-app-setup-policies.md) 설정 정책에서 사용자 고정 설정을 설정해야 합니다.

맞춤형 프런트라인 앱 환경은 관리 센터의 앱 관리 페이지에서  맞춤 앱 또는 전체 앱 Teams 제어됩니다.[](manage-apps.md#manage-org-wide-app-settings) 기능이 설정된 경우 F 라이선스가 있는 조직의 모든 사용자가 맞춤형 앱 환경을 얻을 수 있습니다.

사용자에게 할당된 사용자 지정 앱 [](teams-app-setup-policies.md) 설정 정책이 우선 순위에 따라 결정됩니다. 즉, 사용자에게 사용자 지정 앱 설정 정책이 이미 할당되어 있는 경우 사용자는 사용자 지정 앱 설정 정책에 정의된 구성을 얻습니다. 이 기능이 글로벌 앱 설정 정책을 포함하여 Teams 앱 정책과 함께 작동하는 방법에 대한 자세한 내용은 이 문서의 의 1부 시나리오 섹션 [](#scenarios) 을 참조하세요.

이 기능은 기본적으로 켜져 있습니다. 그러나 Microsoft에서 제공하는 맞춤형 프런트라인 앱 환경을 원하지 않는 경우 기능을 해제할 수 있습니다. 기능을 끄거나 끄는 경우:

1. 관리 센터의 왼쪽 탐색에서 Microsoft Teams **AppsManage** >  앱 Teams 이동한 다음, **Org-wide 앱 설정을 선택합니다**.
2. 맞춤 **앱 아래** 에서 맞춤 앱 표시  토글을 해제 또는 **켜** 기로 **전환합니다**.

    :::image type="content" source="media/tailored-teams-apps-admin-center.png" alt-text="관리 센터의 앱 관리 페이지에서 맞춤 앱 표시 Teams 스크린샷" lightbox="media/tailored-teams-apps-admin-center.png":::

## <a name="scenarios"></a>시나리오

### <a name="how-does-the-tailored-frontline-app-experience-affect-my-global-app-setup-policy"></a>맞춤형 프런트라인 앱 환경이 글로벌 앱 설정 정책에 어떤 영향을 미치나요?

맞춤형 프런트라인 앱 환경이 글로벌 앱 설정 정책과 함께 작동하는 방법을 알아보습니다. 이 표의 시나리오는 사용자 고정이 켜져 있는 F 라이선스 및 전역 앱 설치 정책이 있는 일선 작업자 **에게** 적용됩니다.

|경우... |그런 다음... |
|---------|---------|
|프런트라인 작업자에는 전역 앱 설정 정책이 있으며 기능이 꺼집니다. |프런트라인 작업원은 전역 앱 설정 정책에 정의된 앱을 얻습니다.|
|프런트라인 작업자에는 전역 앱 설정 정책이 있으며 기능이 설정되었습니다.     | 프런트라인 작업원은 맞춤형 프런트라인 앱 환경을 제공합니다. 글로벌 앱 설정 정책에 정의된 앱은 맞춤 앱 아래에 고정됩니다.      |
|전역 앱 설정 정책을 업데이트하고 기능이 설정되어 있습니다.     |프런트라인 작업원은 맞춤형 프런트라인 앱 환경을 얻게 되고 글로벌 앱 설정 정책에 정의된 앱이 맞춤 앱 아래에 고정됩니다.         |
|프런트라인 작업자에는 전역 앱 설정 정책이 있으며 **사용자** 고정이 해제됩니다. |프런트라인 작업원은 전역 앱 설정 정책에 정의된 앱을 얻습니다.|
|프런트라인 작업자에는 전역 앱 설정 정책이 있으며 전역 앱 설정 정책이 앱 목록의 두 번째 위치에 LOB(줄 바인 비즈니스) 앱을 포함하게 변경됩니다. |LOB 앱이 맞춤 앱 아래에 고정됩니다. 프런트라인 작업원은 사용자 고정이 설정된 경우 앱 순서를 **변경할 수 있습니다** .         |
|프런트라인 작업자에는 전역 설정 정책이 있으며 전역 앱 설정 정책이 첫 번째 위치에 Shifts를 포함하게 변경됩니다.  |교대 근무는 맞춤형 프런트라인 앱 경험에 의해 정의된 6번째 위치에 고정됩니다. 프런트라인 작업원은 사용자 고정이 설정된 경우 앱 순서를 **변경할 수 있습니다** .          |

### <a name="how-does-the-tailored-frontline-app-experience-work-with-other-teams-app-policies"></a>맞춤형 프런트라인 앱 환경이 다른 앱 정책과 Teams 어떻게 작동하나요?

맞춤형 프런트라인 앱 환경이 다른 앱 정책과 어떻게 Teams 알아보는 방법.

|경우...  |그런 다음... |
|---------|---------|
기능이 꺼집니다.   | 프런트라인 작업 담당자는 글로벌 앱 설정 정책 또는 사용자 지정 앱 설정 정책에 정의된 앱을 제공합니다.          |
|프런트라인 작업자에는 사용자 지정 앱 설정 정책이 있으며 기능이 설정되었습니다.    |프런트라인 작업원은 사용자 지정 앱 설정 정책에 정의된 앱을 얻습니다.          |
|사용자 또는 조직에 맞게 맞춤된 프런트라인 앱 환경의 앱이 차단됩니다.      |맞춤형 프런트라인 앱 환경은 앱 [사용 권한 정책을 존중합니다](teams-app-permission-policies.md). 앱이 차단된 경우 프런트라인 작업원이 차단된 앱을 볼 수 없습니다.           |
|맞춤형 프런트라인 앱 환경의 앱은 이미 앱 설정 정책에 정의되어 있으며 기능이 설정되어 있습니다. |앱은 맞춤 앱 목록에 정의된 순서에 따라 고정됩니다.        |
|사용자에게 E, A 또는 G 라이선스가 있으며 기능이 설정됩니다.   | 사용자는 맞춤형 프런트라인 앱 환경을 얻지 못합니다. 현재 환경은 F 라이선스가 있는 사용자에게만 적용됩니다.        |

> [!NOTE]
> 맞춤형 프런트라인 앱 환경에서는 앱 또는 앱 순서를 변경할 수 없습니다. 지금은 변경하려는 경우 사용자 지정 환경을 설정할 수 있습니다. 이렇게 하여 먼저 기능을 해제합니다. 그런 다음 사용자 [지정 앱 설정 정책을 만들고](teams-app-setup-policies.md) 사용자 또는 그룹에 [할당합니다](assign-policies-users-and-groups.md).

## <a name="related-articles"></a>관련 기사

- [에서 Walkie Talkie 앱을 Teams](walkie-talkie.md)
- [작업 앱 관리 Teams](manage-tasks-app.md)
- [앱에서 Shifts 앱을 Teams](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)
- [승인 앱 관리 Teams](approval-admin.md)
- [Teams에서 앱 설정 정책 관리](teams-app-setup-policies.md)
- [Teams에서 앱 사용 권한 정책 관리](teams-app-permission-policies.md)
