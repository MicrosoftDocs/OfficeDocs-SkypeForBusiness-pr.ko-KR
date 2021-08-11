---
title: Microsoft Teams에서 팀 소유자와 팀 구성원 할당
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: dansteve
search.appverid: MET150
description: 팀 작성 권한을 포함하여 Microsoft Teams 내에서 팀 소유자와 구성원 역할 및 권한을 할당하는 방법을 알아봅니다.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b574c04acdf466f2ad8a46401dd347ff2a82b876eaa61815d0d3ea07d7d9cb8b
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54331100"
---
# <a name="assign-team-owners-and-members-in-microsoft-teams"></a>Microsoft Teams에서 팀 소유자와 팀 구성원 할당

Microsoft Teams에는 **소유자** 와 **구성원** 이라는 두 가지 사용자 역할이 있습니다. 새 팀을 만든 사용자에게는 기본적으로 소유자 상태가 부여됩니다. 또한 소유자 및 구성원은 변조가 설정된 경우 채널에 대한 진행자 권한을 가질 수 있습니다. 팀이 기존 Microsoft 365 그룹에서 만들어지는 경우, 해당 그룹에서 권한이 상속됩니다.

다음 표에는 소유자와 구성원 간의 권한 차이점이 나와 있습니다.


|    작업                                | 팀 소유자 | 팀 구성원 |
|-----------------------------------|------------|-------------|
|          **팀 만들기**          |    예<sup>1</sup>     |     아니요      |
|          **팀 탈퇴**           |    예     |     예     |
|  **팀 이름/설명 편집**   |    예     |     아니요      |
|          **팀 삭제**          |    예     |     아니요      |
|          **표준 채널 추가**          |    예     |    예<sup>2</sup>|
| **표준 채널 이름/설명 편집** |    예     |    예<sup>2</sup>|
|        **표준 채널 삭제**         |    예     |    예<sup>2</sup>|
|          ***비공개 채널 편집**          |    예     |    예<sup>2</sup>|
| ***개인 채널 이름/설명 편집** |    아니요     |    해당 없음|
|        ***개인 채널 삭제**         |    예     |    아니요|
|          **구성원 추가**          |  예<sup>3</sup>   |     아니요<sup>4</sup>    |
|          **구성원 추가 요청**          |  해당 없음   |     예<sup>5</sup>     |
|           **앱 추가**            |    예     |    예<sup>2</sup>|

<sup>1</sup> 팀 소유자는 제한되지 않는 한 팀을 구성할 수 있습니다. [팀을 생성할 수 있는 권한](#permissions-to-create-teams) 아래.<br>
<sup>2</sup> 소유자는 팀 수준에서 항목을 해제할 수 있습니다. 이 경우 구성원은 항목에 액세스할 수 없습니다.<br>
<sup>3</sup> 팀에 구성원을 추가한 후 소유자는 구성원을 소유자로 승격할 수도 있습니다. 소유자는 자신의 상태를 구성원으로 강등시킬 수도 있습니다.<br>
<sup>4</sup> 팀 구성원은 다른 구성원을 공개 팀에 추가할 수 있습니다.<br>
<sup>5</sup> 팀 구성원은 개인 팀에 구성원을 직접 추가할 수 없지만, 이미 구성원이 된 팀에 구성원을 추가하도록 요청할 수 있습니다. 구성원이 팀에 추가할 것을 요청할 때 팀 소유자는 보류 중인 요청을 수락하거나 거부할 수 있다는 알림을 받습니다.

*개인 채널의 사용 권한에 대한 자세한 내용은 [Teams 개인 채널](private-channels.md)을 참조하세요.

> [!NOTE]
> 소유자는 **팀 보기** 옵션에서 다른 구성원의 소유자를 만들 수 있습니다. 팀은 최대 100명의 소유자를 가질 수 있습니다. 팀을 관리하는 데 도움이 되는 소유자가 최소 몇 명 있는 것이 좋습니다. 이렇게 하면 단독 소유자가 조직을 떠나는 경우에도 분리된 그룹을 방지할 수 있습니다. 분리된 그룹에 대한 자세한 내용은 [분리된 그룹에 새 소유자 할당](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732)을 참조하세요.

## <a name="moderator-capabilities"></a>중재자 기능

다른 기능 외에도, 팀 소유자와 구성원은 채널에 대한 진행자 기능을 가질 수 있습니다(팀에 대해 조정 기능이 설정되어 있는 경우). 중재자는 채널에서 새 게시물을 시작하고 팀 구성원이 기존 채널 메시지에 회신할 수 있는지 여부를 제어할 수 있습니다. 또한 중재자는 봇과 커넥터가 채널 메시지를 제출할 수 있는지 여부를 제어합니다.

중재자 역량은 채널 수준에서 할당됩니다. 팀 소유자에게는 기본적으로 중재자 역량이 있습니다. 팀 구성원은 기본적으로 중재자 역량이 없지만, 팀 소유자가 채널에 대한 중재자 역량을 팀 구성원에게 부여할 수 있습니다. 채널 내의 중재자는 해당 채널 내에서 다른 중재자를 추가하고 제거할 수 있습니다.

중재자 기능에 대한 자세한 정보는 [Microsoft Teams에서 채널 조정 설정 및 관리](manage-channel-moderation-in-teams.md)를 참조하세요.

## <a name="assign-a-user-role"></a>사용자 역할 할당

사용자 역할을 할당하려면 Teams에서 팀 이름을 선택하고 **추가 옵션** > **팀 관리** 를 선택하세요. **구성원** 탭에서 구성원을 추가하고 소유자 및 중재자를 선택할 수 있습니다(충분한 권한이 있는 경우). 자세한 내용은 [Teams 팀 설정 변경](https://support.office.com/article/ce053b04-1b8e-4796-baa8-90dc427b3acc)을 참조하세요.

## <a name="permissions-to-create-teams"></a>팀 생성 권한

기본적으로 Exchange Online에 편지함이 있는 모든 사용자는 Microsoft 365 그룹 및 Microsoft Teams 내의 팀을 생성할 수 있는 권한을 가집니다. 그룹 생성 및 관리 권한을 사용자 집합에 위임하여 새로운 팀 생성을 더욱 엄격하게 제어하고 제한하여 새로운 Microsoft 365 그룹을 새로 만들 수 있습니다. 자세한 지침은 [Microsoft 365 그룹 생성 가능 사용자 관리](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618)를 참조하세요.
