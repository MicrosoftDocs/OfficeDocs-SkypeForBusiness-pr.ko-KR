---
title: Microsoft 팀에서 팀 소유자 및 구성원 지정
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: dansteve
search.appverid: MET150
description: 팀을 만들 수 있는 권한을 포함 하 여 Microsoft 팀에서 팀 소유자 및 구성원 역할 및 권한을 할당 하는 방법을 알아봅니다.
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6757f7200535dc8fb687915ec033712b2654723b
ms.sourcegitcommit: 9fd23cf0e03dd8fcf7ed04ef09dcdac048ebb44a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2019
ms.locfileid: "37517051"
---
<a name="assign-team-owners-and-members-in-microsoft-teams"></a>Microsoft 팀에서 팀 소유자 및 구성원 지정
=================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Microsoft 팀 내에는 **소유자** 와 **구성원**의 두 가지 사용자 역할이 있습니다. 기본적으로 새 팀을 만드는 사용자에 게는 소유자 상태가 부여 됩니다. 또한 소유자와 구성원은 채널에 대 한 중재자 기능을 가질 수 있습니다 (중재가 설정 된 경우). 기존 Office 365 그룹에서 팀을 만든 경우 사용 권한이 상속 됩니다.

다음 표에서는 소유자와 구성원 간의 사용 권한 차이를 보여 줍니다.


|                                   | 팀 소유자 | 팀 구성원 |
|-----------------------------------|------------|-------------|
|          **팀 만들기**          |    예<sup>1</sup>     |     아니요      |
|          **팀 나가기**           |    '     |     '     |
|  **팀 이름/설명 편집**   |    '     |     아니요      |
|          **팀 삭제**          |    '     |     아니요      |
|          **채널 추가**          |    '     |    예<sup>2</sup>|
| **채널 이름/설명 편집** |    '     |    예<sup>2</sup>|
|        **채널 삭제**         |    '     |    예<sup>2</sup>|
|          **구성원 추가**          |  예<sup>3</sup>   |     없음<sup>4</sup>    |
|          **회원 추가 요청**          |  해당 없음   |     예<sup>5</sup>     |
|           **탭 추가**            |    '     |    예<sup>2</sup>|
|        **연결선 추가**         |    '     |    예<sup>2</sup>|
|           **인공 지능 추가**            |    '     |    예<sup>2</sup>|

<sup>1</sup> 명의 팀 소유자는이 작업을 제한 하지 않는 한 팀을 만들 수 있습니다. 아래 [에서 팀을 만들 수 있는 권한](#permissions-to-create-teams) .<br>
><sup>2</sup> 소유자는 팀 수준에서 이러한 항목을 해제할 수 있으며,이 경우 구성원은 액세스할 권한이 없습니다.<br>
<sup>3</sup> 팀에 구성원을 추가한 후 소유자는 구성원을 소유자 상태로 올릴 수도 있습니다. 소유자가 자신의 상태를 구성원으로 강등 시킬 수도 있습니다.<br>
<sup>4</sup> 팀 구성원은 다른 구성원을 공용 팀에 추가할 수 있습니다.<br>
<sup>5</sup> 팀 구성원이 개인 팀에 구성원을 직접 추가할 수는 없지만 이미 구성원 인 팀에 다른 사용자를 추가할 수 있도록 요청할 수도 있습니다. 구성원이 팀에 추가 하도록 요청 하는 경우 팀 소유자는 해당 사용자에 게 수락 하거나 거부할 수 있는 보류 요청이 있다는 알림을 받습니다.

> [!NOTE]
> 소유자는 **팀 보기** 옵션에서 다른 구성원의 소유자를 만들 수 있습니다. 팀은 최대 100 명의 소유자를 가질 수 있습니다. 팀을 관리 하는 데 도움이 되는 소유자가 최소한 몇 개 있는 것이 좋습니다. 이렇게 하면 단독 소유자가 조직을 떠나는 경우 고아 그룹도 차단 됩니다. 고아 그룹에 대 한 자세한 내용은 [고아 그룹에 새 소유자 할당](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732)을 참조 하세요.

## <a name="moderator-capabilities"></a>중재자 기능

팀 소유자 및 구성원은 다른 기능 외에도 팀에 대 한 중재가 설정 된 경우 채널에 대 한 중재자 기능을 가질 수 있습니다. 중재자는 채널에서 새 게시물을 시작 하 고 팀 구성원이 기존 채널 메시지에 회신할 수 있는지 여부를 제어할 수 있습니다. 또한 인공 지능 커넥터는 채널 메시지를 제출할 수 있는지 여부를 제어할 수 있습니다.

중재자 기능은 채널 수준에서 지정 됩니다. 팀 소유자는 기본적으로 중재자 기능을 보유 합니다. 팀 구성원은 기본적으로 중재자 기능을 사용 하지 않도록 설정 되어 있지만 팀 소유자는 팀 구성원에 게 채널에 대 한 중재자 기능을 제공할 수 있습니다. 채널 내의 중재자는 해당 채널 내에서 다른 중재자를 추가 하 고 제거할 수 있습니다.

중재자 기능에 대 한 자세한 내용은 [Microsoft 팀에서 채널 중재 설정 및 관리](manage-channel-moderation-in-teams.md)를 참조 하세요.

## <a name="assign-a-user-role"></a>사용자 역할 할당

사용자 역할을 할당 하려면 팀에서 팀 이름을 선택 하 고 **추가 옵션** > 을 클릭 하 여**팀 관리**하세요. **구성원** 탭에서 구성원을 추가 하 고 소유자 및 중재자를 선택할 수 있습니다 (충분 한 권한이 있는 경우). 자세한 내용은 [팀에서 팀 설정 변경을](https://support.office.com/article/ce053b04-1b8e-4796-baa8-90dc427b3acc)참조 하세요.

## <a name="permissions-to-create-teams"></a>팀을 만들 수 있는 권한

기본적으로 Exchange Online에서 사서함을 사용 하는 모든 사용자에 게 Office 365 그룹을 만들 수 있는 사용 권한이 있으며, 따라서 Microsoft 팀 내에서 팀이 됩니다. 그룹 만들기 및 관리 권한을 사용자 집합에 위임 하 여 더욱 엄격한 제어 및 새 팀 만들기를 제한 하 여 새 Office 365 그룹을 만들 수 있습니다. 지침은 [Office 365 그룹을 만들 수 있는 사용자 관리](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618)를 참조 하세요.


||||
|---------|---------|---------|
| ![결정 지점을 나타내는 아이콘](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |판단 요점         |모든 Microsoft 팀 사용자가 팀을 만들 수 있습니까 (권장)?         |
| ![다음 단계를 나타내는 아이콘](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |다음 단계         |팀을 만들 수 있는 사용자를 제한 해야 하는 경우 Office 365 그룹을 만들 수 있는 사용자의 기본 사용 권한을 수정 합니다.         |
