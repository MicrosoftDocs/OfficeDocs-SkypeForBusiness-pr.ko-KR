---
title: Teams 관리 센터에서 칭찬 앱 관리
author: LanaChin
ms.author: v-lanachin
manager: samanro
ms.reviewer: rjam
audience: admin
ms.topic: how-to
ms.service: msteams
ms.localizationpriority: medium
description: Microsoft Teams 관리 센터에서 칭찬 앱을 관리하는 방법을 알아봅니다.
ms.collection:
- M365-collaboration
- m365-frontline
- tier2
- highpri
ms.openlocfilehash: 31a185239607c2458636dd6cadc83b7462135112
ms.sourcegitcommit: ff161779577ce9cc892f1b6b8861ad49ff4c3ca3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2022
ms.locfileid: "69131177"
---
# <a name="manage-the-praise-app-in-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터에서 칭찬 앱 관리

Microsoft Teams의 칭찬 앱을 사용하면 사용자가 조직 또는 교실 구성원에게 감사를 표시할 수 있습니다. 칭찬의 배지는 교육자부터 최전방 작업자에 이르기까지 Teams 사용자가 수행하는 광범위한 작업에 대한 노력을 인식할 수 있도록 설계되었습니다. 자세한 내용은 [사람들에게 칭찬 보내기를 참조하세요](https://support.microsoft.com/office/send-praise-to-people-50f26b47-565f-40fe-8642-5ca2a5ed261e).

관리자는 이 기능에 액세스하려면 Teams 라이선스가 있어야 합니다. Teams 라이선스 없이 이 기능에 액세스하려고 하면 오류 메시지가 표시됩니다.

> [!NOTE]
> 칭찬 앱은 GCC 클라우드 환경에서 사용할 수 있지만 GCC High 또는 DoD에서는 사용할 수 없습니다.

## <a name="enable-or-disable-praise-in-your-organization"></a>조직에서 칭찬 사용 또는 사용 안 함

칭찬은 조직의 모든 Teams 사용자에 대해 기본적으로 사용하도록 설정됩니다. Microsoft Teams 관리자 센터의 [앱 관리](manage-apps.md) 페이지에서 조직 수준에서 앱을 끄거나 켤 수 있습니다.

:::image type="content" source="media/manage-praise-app-admin-center.png" alt-text="상태 토글을 보여 주는 Teams 관리 센터의 칭찬 앱 세부 정보 페이지 스크린샷":::

1. Microsoft Teams 관리 센터의 왼쪽 창에서 **Teams 앱** > **앱 관리** 로 이동합니다.
2. 앱 목록에서 칭찬 앱을 검색하고 선택한 다음 **상태** 토글을 **차단** 됨 또는 **허용** 됨으로 전환합니다.

이 설정은 Teams의 Viva Insights 앱에서 칭찬 앱과 칭찬 기능에 모두 영향을 줍니다.

상태를 차단됨으로 설정하면 Teams에 대해 몇 분 이내에 칭찬 앱이 차단됩니다. 그러나 Viva Insights 칭찬은 차단되는 데 7-9일이 걸릴 수 있습니다.

## <a name="enable-or-disable-praise-for-specific-users-in-your-organization"></a>조직의 특정 사용자에 대해 칭찬 사용 또는 사용 안 함

조직의 특정 사용자가 칭찬 사용을 허용하거나 차단하려면 [앱 관리](manage-apps.md) 페이지에서 조직에 대해 칭찬이 켜져 있는지 확인합니다. 그런 다음 앱 권한에 대한 사용자 지정 정책을 만들고 해당 사용자에게 할당합니다. 자세한 내용은 [Teams에서 앱 권한 정책 관리](teams-app-permission-policies.md)를 참조하세요.

## <a name="badges"></a>배지

다음은 칭찬의 기본 배지 집합입니다. 조직의 Teams 사용자는 이러한 배지를 사용하여 동료가 업무상 위와 그 이상으로 나아가는 것을 인식할 수 있습니다.

:::image type="content" source="media/default-set-praise.png" alt-text="기본 배지 집합의 배지 이미지입니다.":::

> [!NOTE]
> 2022년 2월부터 사용자는 기본 배지만 보내고 받을 수 있습니다. 사용자 지정 배지는 더 이상 사용할 수 없으며 사용자 지정 배지에 대한 옵션이 Teams 관리 센터에서 제거되었습니다.

## <a name="related-articles"></a>관련 기사

[Microsoft Teams 관리 센터에서 앱 관리](manage-apps.md)
