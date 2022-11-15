---
title: Microsoft Teams 관리 센터에서 팀 소유자 및 구성원 할당
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: dansteve
search.appverid: MET150
description: 팀 작성 권한을 포함하여 Microsoft Teams 내에서 팀 소유자와 구성원 역할 및 권한을 할당하는 방법을 알아봅니다.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e0f259a7a24552988d4eca503deeb9151dde144d
ms.sourcegitcommit: 0760416ee0bead3ada93f4d37f8aebc74222bd3c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2022
ms.locfileid: "69019414"
---
# <a name="assign-team-owners-and-members-in-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터에서 팀 소유자 및 구성원 할당

**소유자** 와 **구성원** 은 Microsoft Teams 내의 두 사용자 역할입니다. 새 팀을 만드는 사용자에게는 기본적으로 소유자 상태가 부여됩니다. 소유자와 구성원은 팀 및 채널과 상호 작용할 때 다양한 유형의 권한과 기능을 갖습니다. Teams의 역할에 대한 자세한 내용은 [Microsoft Teams의 팀 및 채널 개요](teams-channels-overview.md) 를 참조하세요.

> [!NOTE]
> 기존 Microsoft 365 그룹에서 팀을 만든 경우 사용 권한이 상속됩니다.

## <a name="assign-a-user-role-in-teams-admin-center"></a>Teams 관리 센터에서 사용자 역할 할당

1. Teams 관리 센터에서 **Teams** 를 확장하고 **팀 관리를** 선택합니다.
2. 표시 이름 열 아래에서 팀 이름을 선택합니다.
3. 멤버 탭에서 멤버를 추가하거나 제거하고 소유자 및 중재자 역할을 멤버에게 할당할 수 있습니다.

## <a name="restrict-permission-to-create-teams"></a>팀을 만들 수 있는 권한 제한

Exchange Online 사서함이 있는 모든 사용자에게는 Microsoft Teams 내에서 Microsoft 365 그룹 및 팀을 만들 수 있는 권한이 있습니다. 그룹 만들기 및 관리 권한을 사용자 집합에 위임하여 사용자가 새 팀 및 Microsoft 365 그룹을 만들지 못하도록 제한합니다. 이 제한이 활성화된 경우 팀 소유자나 구성원 모두 새 팀을 만들 수 없습니다. 자세한 내용은 [Microsoft 365 그룹 생성 가능 사용자 관리](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618)를 참조하세요.

## <a name="user-permissions-based-on-assigned-roles"></a>할당된 역할에 따른 사용자 권한

다음 표에는 소유자와 구성원 간의 권한 차이점이 나와 있습니다.

### <a name="teams"></a>Teams

|Teams 작업| 팀 소유자 | 팀 구성원 |
|---------|---------|---------|
|팀 만들기/삭제  |    예     |     아니요    |
|팀 이름/설명 편집   |     예    |     아니요     |
|프라이빗 팀에 구성원 추가    |     예    |  아니요 |
|공용 팀에 구성원 추가    |     예    |     예   |
|새 멤버 추가 요청   |     해당 없음    |    예   |
|사용자 상태 승격/강등 | 예 | 아니요 |
|팀 탈퇴  |    예     |     예    |
|앱 추가/제거   |     예    |     예, 팀 소유자가 사용하도록 설정한 경우     |

### <a name="channels"></a>채널

|***표준 채널 작업** _ | _ *팀 소유자** | **팀 구성원**|
|----|----|----|
|채널 만들기/삭제  |     예    |    예, 팀 소유자가 사용하도록 설정한 경우      |
|채널 이름/설명 편집    |    예     |     예, 팀 소유자가 사용하도록 설정한 경우    |
|***프라이빗 채널 작업***|
|채널 만들기    |    예     |    예, 팀 소유자가 사용하도록 설정한 경우      |
|채널 삭제    |    예     |    아니요     |
|채널 이름/설명 편집 |     아니요    |    해당 없음     |
|***공유 채널 작업***
|채널 만들기    |    예     |     아니요    |
|채널 삭제 | 예 | 아니요 |
|채널 이름/설명 편집    |    아니요     |     아니요    |
