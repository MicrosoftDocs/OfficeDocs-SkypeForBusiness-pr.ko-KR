---
title: 라이선스에 Teams 앱 맞춤 설정
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaglick
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 라이선스를 기반으로 조직의 Teams 앱을 고정하는 방법에 대해 자세히 알아보습니다.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: a82dbf888fcd6fd0b05816e3edb390b79c9a9e3f
ms.sourcegitcommit: 8f999bd2e20f177c6c6d8b174ededbff43ff5076
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2022
ms.locfileid: "62055318"
---
# <a name="tailor-your-teams-apps-based-on-license"></a>라이선스에 Teams 앱 맞춤 설정

> [!NOTE]
> [!INCLUDE [new-feature-coming-soon-section](includes/new-feature-coming-soon-section.md)]

> [!NOTE]
> 현재 이 기능은 F 라이선스에 적용됩니다. 따라서 이 문서에서는 최전선 작업자 환경을 중점적으로 다합니다. 다른 라이선스 유형은 향후 지원될 예정입니다.

## <a name="overview"></a>개요

Teams 기반 앱을 고정하는 방법을 제공합니다. 사용자가 사용자에 Teams 사용 설정된 앱 환경을 사용하도록 설정하면 사용자는 라이선스에 따라 맞춤 설정된 앱 환경을 얻습니다.

이 기능은 사용자에게 관리자에게 필요한 작업 없이 Teams 가장 관련성이 높은 앱을 제공합니다.

## <a name="tailored-app-experience"></a>맞춤형 앱 환경

앱은 앱 표시줄에 고정됩니다. 이 막대는 데스크톱 클라이언트의 Teams 및 모바일 클라이언트(iOS 및 Android) Teams 아래쪽에 있습니다.

F 라이선스가 있는 사용자를 위해 고정된 앱:

- 활동
- 채팅
- Teams
- 교대 근무
- 작업
- 워키토키

## <a name="admin-controls"></a>관리자 컨트롤

> [!NOTE]
> 이 기능을 적용하려면 전역(org-wide [default)](teams-app-setup-policies.md) 앱 설정 정책에서 사용자 고정을 설정해야 합니다.

맞춤형 앱 환경 기능은 관리 센터의 앱 관리 페이지에서 라이선스 또는 전체 앱 [](manage-apps.md#manage-org-wide-app-settings) 설정을 기반으로 맞춤 앱 표시에 Teams 제어됩니다.  기능이 설정된 경우 F 라이선스가 있는 조직의 모든 사용자가 맞춤형 앱 환경을 얻을 수 있습니다.

사용자에게 할당된 사용자 지정 앱 설정 정책이 우선 순위에 따라 결정됩니다. 즉, 사용자에게 사용자 지정 앱 설정 정책이 이미 할당되어 있는 경우 사용자는 사용자 지정 앱 설정 정책에 정의된 구성을 얻습니다. 이 기능이 조직에서 적용한 기존 앱 설정 정책과 함께 작동하는 방법에 대한 자세한 내용은 이 문서의 [시나리오](#scenarios) 섹션을 참조하세요.

이 기능은 기본적으로 켜져 있습니다. 그러나 Microsoft에서 제공하는 맞춤형 앱 환경을 원하지 않는 경우 기능을 해제할 수 있습니다. 기능을 끄거나 끄는 경우:

1. 관리 센터의 왼쪽 탐색에서 Microsoft Teams 앱 관리 Teams 앱 관리로 이동한 다음,  >   **Org-wide 앱** 설정을 선택합니다.
2. 맞춤 **앱에서** 라이선스에  따라 맞춤 앱 표시 토글을 해제 또는 **켜기로** **전환합니다.**

    :::image type="content" source="media/pin-teams-apps-based-on-license.png" alt-text="앱 관리 페이지의 스크린샷, 라이선스 전체 앱 설정에 따라 맞춤 앱 표시" lightbox="media/pin-teams-apps-based-on-license.png":::

## <a name="scenarios"></a>시나리오

이 표의 정보를 사용하여 기존 앱 설정 정책을 적용한 경우를 포함하여 다양한 시나리오에서 맞춤형 앱 환경 기능이 작동하는 방법을 알아보겠습니다.

|경우...  |그런 다음... |
|---------|---------|
|사용자에게 전역 앱 설정 정책이 있으며 기능이 설정되었습니다.     | 사용자는 맞춤형 앱 환경을 얻습니다.        |
|사용자에게 사용자 지정 앱 설정 정책이 있으며 기능이 설정되었습니다.    |사용자는 사용자 지정 앱 설정 정책에 정의된 구성을 얻습니다.          |
|이 기능이 설정되어 있으며 전역 앱 설정 정책을 업데이트합니다.     |사용자는 라이선스에 따라 맞춤형 앱 환경을 얻습니다. 전역 앱 설정 정책에 정의된 앱은 여전히 고정되어 고정된 앱 목록에 더 아래로 표시됩니다.          |
|기능이 꺼져 있습니다.   | 사용자는 글로벌 앱 설정 정책 또는 사용자에게 할당된 사용자 지정 앱 설정 정책에 정의된 환경을 얻습니다.          |
|사용자에게 E, A 또는 G 라이선스가 있으며 기능이 설정됩니다.   | 사용자는 맞춤형 앱 환경을 얻지 못합니다. 현재 맞춤 앱 환경은 F 라이선스가 있는 사용자에게만 적용됩니다.        |
|사용자 또는 조직에 대한 맞춤 앱 환경의 앱이 차단됩니다.      |맞춤 앱 환경은 앱 사용 권한 정책을 존중합니다. 앱이 차단된 경우 사용자가 차단된 앱을 볼 수 없습니다.           |
|맞춤 앱 환경의 앱은 이미 앱 설정 정책에 정의되어 있으며 기능이 설정되어 있습니다. |앱은 맞춤 앱 환경이 정의한 순서에 따라 고정됩니다.        |

> [!NOTE]
> 맞춤 앱 환경의 앱 또는 앱 순서를 변경할 수 없습니다. 지금은 변경하려는 경우 사용자 지정 환경을 설정할 수 있습니다. 이렇게 하여 먼저 기능을 해제합니다. 그런 다음 사용자 지정 앱 설정 [정책을](teams-app-setup-policies.md)만들고 사용자 또는 그룹에 [할당합니다.](assign-policies-users-and-groups.md)

## <a name="related-articles"></a>관련 기사

- [Teams에서 앱 설정 정책 관리](teams-app-setup-policies.md)
- [Teams에서 앱 사용 권한 정책 관리](teams-app-permission-policies.md)
