---
title: Microsoft Teams에서 태그 관리
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: acolonna, salu
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Microsoft Teams의 조직에서 태그를 사용하는 방법을 알아봅니다.
ms.openlocfilehash: 9c2da438d3f88a172759ec13672aec663ae6add9
ms.sourcegitcommit: 41a75f1ba5ceb09f8db7d468aa41b63a89ab9c30
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2022
ms.locfileid: "67647432"
---
# <a name="manage-tags-in-microsoft-teams"></a>Microsoft Teams에서 태그 관리

Microsoft Teams의 태그를 사용하면 사용자가 팀의 사용자 하위 집합과 빠르고 쉽게 연결할 수 있습니다. 사용자 지정 태그를 만들고 할당하여 역할, 프로젝트, 기술 또는 위치와 같은 특성에 따라 사람을 분류할 수 있습니다. 또는 [Shifts 앱](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6)의 일정 및 교대 근무 정보에 따라 사용자에게 태그를 자동으로 할당할 수 있습니다. 태그가 하나 또는 여러 팀 구성원에 추가된 후 채널 게시물에서 팀의 모든 사용자가 @mentions 사용하여 대화의 태그가 할당된 사용자만 알릴 수 있습니다.

앞에서 설명한 것처럼 Teams에는 두 가지 종류의 태그가 있습니다.

- **사용자 지정 태그**: 팀 소유자 및 팀 구성원(권한이 있는 경우)은 수동으로 태그를 만들고 사용자에게 할당할 수 있습니다. 예를 들어 "디자이너" 또는 "방사선 전문의" 태그는 이름을 입력하지 않고도 팀의 해당 사용자 집합에 도달합니다.
- **교대 근무로 태그 지정**: 이 기능을 사용하면 Teams의 [Shifts 앱](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_usetags) 에서 일정 및 교대 근무 그룹 이름과 일치하는 태그가 자동으로 할당됩니다. 예를 들어 "EngineerOnCall" 태그는 채팅 또는 채널 게시물에서 태그를 사용할 때 작동하도록 Shifts에서 예약된 모든 엔지니어에게 도달합니다. 교대 근무로 태그를 지정하면 Teams는 사용자가 정보를 신속하게 릴레이해야 할 때 교대 근무 중인 직원의 이름을 알지 못하는 추측을 수행합니다.

> [!NOTE]
> 태그는 비공개 또는 공유 채널에서 지원되지 않습니다.

## <a name="how-tags-work"></a>태그 작동 방식

Shifts 앱에서 Shifts를 설정하여 태그를 수동으로 추가(사용자 지정 태그)하거나 특정 팀의 사람에게 자동으로 할당할 수 있습니다. 태그는 채팅에서 **To** 줄의 @mentions 또는 팀의 표준 채널에 있는 게시물에 사용할 수 있습니다. 다음은 Teams에서 태그를 사용하는 방법의 몇 가지 예입니다.

- 매장 관리자는 모든 점원에게 알리기 위해 채널에 공지 사항을 게시합니다.
- 병원 관리자는 채널의 모든 방사선 전문의에게 메시지를 보냅니다.
- 마케팅 관리자는 모든 디자이너와 그룹 채팅을 시작합니다.
- 간호사가 모든 온-콜 심장 전문의에게 메시지를 보냅니다.
- 시스템 엔지니어가 모든 교대 근무 현장 엔지니어에게 알리기 위해 채널에 공지 사항을 게시합니다.

채널 대화에서 태그가 @mentioned 경우 태그와 연결된 팀 구성원은 다른 @mention 마찬가지로 알림을 받습니다.

## <a name="manage-tags-for-your-organization"></a>조직의 태그 관리

관리자는 Microsoft Teams 관리 센터에서 조직 전체에서 태그를 사용하는 방법을 제어할 수 있습니다. PowerShell을 사용하여 태그를 관리할 수 없습니다.

:::image type="content" source="media/manage-tags-admin-settings-shifts.png" alt-text="Microsoft Teams 관리 센터의 태그 지정 설정 스크린샷":::

팀에는 최대 100개의 태그가 있고, 태그에 최대 200명의 팀 구성원을 할당할 수 있으며, 동일한 팀의 태그는 최대 25개까지 단일 사용자에게 할당됩니다.

### <a name="set-who-can-manage-tags"></a>태그를 관리할 수 있는 사용자 설정

기본적으로 팀 소유자는 태그를 만들고, 편집하고, 삭제할 수 있습니다. 팀 소유자와 팀 구성원이 **태그를 관리할 수 있도록 태그 설정을 관리할 수 있는 사용자를** 변경하거나 조직의 태그를 해제할 수 있습니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색 영역에서 **Teams Teams** \> **설정을** 클릭합니다.

2. **태그 지정** 에서 **태그를 관리할 수 있는 사용자 옆에 있는** 다음 옵션 중 하나를 선택합니다.

    - **팀 소유자 및 구성원**: 팀 소유자와 구성원이 태그를 관리할 수 있도록 허용합니다.
    - **팀 소유자**: 팀 소유자가 태그를 관리할 수 있도록 허용합니다.
    - **사용할 수 없음**: 태그를 끕니다.

### <a name="configure-tagging-settings"></a>태그 지정 설정 구성

다음 태그 설정을 구성하여 조직 전체에서 태그를 사용하는 방법을 제어할 수 있습니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색 영역에서 **Teams Teams** \> **설정을** 클릭합니다.

2. **태그 지정** 에서 조직의 요구 사항에 따라 다음을 설정합니다.

    - **팀 소유자는 태그를 관리할 수 있는 사용자를 변경할 수 있습니다**. 이 설정을 켜면 팀 소유자는 팀 구성원이 팀 내에서 태그를 만들고 관리할 수 있는지 여부를 설정할 수 있으며 **태그 설정을 관리할 수 있는 사람의** 값은 각 팀의 기본값입니다. 이 설정을 해제하면 팀별로 태그 설정을 **변경할 수** 없습니다.
    - **제안된 태그**: 이 태그를 사용하여 기본 태그 집합을 추가합니다. 최대 25개의 태그를 추가할 수 있으며 각 태그는 최대 25자를 포함할 수 있습니다. 팀 소유자와 구성원(기능이 사용하도록 설정된 경우)은 이러한 제안을 사용하거나, 추가하거나, 새 태그 집합을 만들 수 있습니다.
    - **사용자 지정 태그**: 사용자가 설정한 제안된 기본 태그 이외의 태그를 추가할 수 있도록 이 설정을 켭니다. 이 기능을 해제하면 제안된 기본 태그만 사용할 수 있습니다. 이 옵션을 해제하는 경우 하나 이상의 기본 태그를 추가해야 합니다.
    - **Shifts 앱은 태그를 적용할 수 있습니다**. 이 설정을 켜면 Shifts 앱이 실시간으로 교대 근무 중인 사용자에게 태그를 자동으로 할당할 수 있습니다. 이러한 태그는 Shifts에서 사용자의 일정 및 그룹 이름과 일치합니다. 알림은 채팅 또는 채널 게시물에서 태그를 사용할 때 교대 근무 중인 사용자에게만 전송됩니다.

## <a name="related-topics"></a>관련 주제

[Teams에서 태그 사용](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)

[Shifts 앱 관리](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)

[Shifts 도움말 설명서](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
