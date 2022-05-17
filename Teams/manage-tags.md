---
title: Microsoft Teams 태그 관리
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.reviewer: acolonna, salu
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Microsoft Teams 조직에서 태그를 사용하는 방법을 관리하는 방법을 알아봅니다.
ms.openlocfilehash: 0fa615f2bbcdd7965777925b2413717779ad4a7a
ms.sourcegitcommit: 54cb804e6e8338f2d09499e53416e6d55ef1cc40
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/17/2022
ms.locfileid: "65442014"
---
# <a name="manage-tags-in-microsoft-teams"></a>Microsoft Teams 태그 관리

## <a name="overview"></a>개요

Microsoft Teams 태그를 사용하면 사용자가 팀의 사용자 하위 집합과 빠르고 쉽게 연결할 수 있습니다. 사용자 지정 태그를 만들고 할당하여 역할, 프로젝트, 기술 또는 위치와 같은 특성에 따라 사람을 분류할 수 있습니다. 또는 [Shifts 앱](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Shifts)의 일정 및 교대 근무 정보에 따라 사용자에게 태그를 자동으로 할당할 수 있습니다. 태그가 하나 또는 여러 팀 구성원에 추가된 후 채널 게시물에서 팀의 모든 사용자가 @mentions 사용하거나 해당 태그가 할당된 사용자와만 대화를 시작하는 데 사용할 수 있습니다.

앞에서 설명한 대로 Teams 두 종류의 태그가 있습니다.

- **사용자 지정 태그**: 팀 소유자 및 팀 구성원(기능이 사용하도록 설정된 경우)은 수동으로 태그를 만들고 사용자에게 할당할 수 있습니다. 예를 들어 "디자이너" 또는 "방사선 전문의" 태그는 이름을 입력하지 않고도 팀의 해당 사용자 집합에 도달합니다.
- **교대 근무로 태그 지정**: 이 기능을 사용하면 Teams [Shifts 앱](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop)에서 일정 및 교대 근무 그룹 이름과 일치하는 태그가 자동으로 할당됩니다. 예를 들어 "EngineerOnCall" 태그는 채팅 또는 채널 게시물에서 태그를 사용할 때 작동하도록 Shifts에서 예약된 모든 엔지니어에게 도달합니다. 교대 근무로 태그를 지정하면 Teams 사용자가 정보를 신속하게 릴레이해야 할 때 교대 근무 직원의 이름을 알지 못하는 추측을 수행합니다. 교대 근무에 의한 태그 지정은 JDA, Kronos 및 AMiON과 같은 주요 인력 관리 시스템에서 Teams Shifts와 통합하여 지원될 수도 있습니다. 이 기능을 설정하는 방법에 대한 자세한 내용은 [Shift로 태그 지정 설정을](#set-up-tagging-by-shift) 참조하세요.

> [!NOTE]
> 태그는 비공개 또는 공유 채널에서 지원되지 않습니다.  

## <a name="how-tags-work"></a>태그 작동 방식

태그를 수동으로 추가하거나 특정 팀의 사람에게 자동으로 할당할 수 있습니다. 그런 다음 채팅에서 **To** 줄의 @mentions 또는 팀의 표준 채널에 있는 게시물에 사용할 수 있습니다. Teams 태그를 사용하는 방법에 대한 몇 가지 예는 다음과 같습니다.

- 매장 관리자는 모든 점원에게 알리기 위해 채널에 공지 사항을 게시합니다.
- 병원 관리자는 채널의 모든 방사선 전문의에게 메시지를 보냅니다.
- 마케팅 관리자는 모든 디자이너와 그룹 채팅을 시작합니다.
- 간호사가 모든 온-콜 심장 전문의에게 메시지를 보냅니다. (곧 지원됨)
- 시스템 엔지니어가 모든 교대 근무 현장 엔지니어에게 알리기 위해 채널에 공지 사항을 게시합니다. (곧 지원됨)

채널 대화에서 태그가 @mentioned 경우 태그와 연결된 팀 구성원은 다른 @mention 마찬가지로 알림을 받습니다.

## <a name="manage-custom-tags-for-your-organization"></a>조직의 사용자 지정 태그 관리

관리자는 Microsoft Teams 관리 센터에서 조직 전체에서 태그를 사용하는 방법을 제어할 수 있습니다. 현재는 PowerShell을 사용하여 태그를 관리할 수 없습니다.

![Microsoft Teams 관리 센터의 태그 지정 설정 스크린샷](media/manage-tags-admin-settings.png)

팀에는 최대 100개의 태그가 있고, 태그에 최대 200명의 팀 구성원을 할당할 수 있으며, 동일한 팀의 태그를 최대 25개까지 단일 사용자에게 할당할 수 있습니다. 

### <a name="set-who-can-add-custom-tags"></a>사용자 지정 태그를 추가할 수 있는 사용자 설정

기본적으로 팀 소유자는 사용자 지정 태그를 추가할 수 있습니다. 팀 소유자와 팀 구성원이 태그를 만들고, 편집하고, 삭제하고, 관리할 수 있도록 이 설정을 변경하거나 조직의 태그를 해제할 수 있습니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색 영역에서 **Teams** >  **Teams 설정을** 클릭합니다.
2. **태그 지정** 에서 **태그 옆의 관리 대상은** 다음 옵션 중 하나를 선택합니다.

    - **팀 소유자 및 구성원**: 팀 소유자와 구성원이 태그를 관리할 수 있도록 허용합니다.
    - **팀 소유자**: 팀 소유자가 태그를 관리할 수 있도록 허용합니다.
    - **사용 안 함**: 태그를 끕니다.

### <a name="configure-custom-tags-settings"></a>사용자 지정 태그 설정 구성

다음 태그 설정을 구성하여 조직 전체에서 사용자 지정 태그를 사용하는 방법을 제어할 수 있습니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색 영역에서 **Teams** >  **Teams 설정을** 클릭합니다.
2. **태그 지정** 에서 조직의 요구 사항에 따라 다음을 설정합니다.

    - **팀 소유자가 태그를 관리할 수 있는 사용자를 재정** 의할 수 있도록 합니다. 이 설정을 켜면 팀 소유자는 팀 구성원이 팀 내에서 태그를 만들고 관리할 수 있는지 여부를 설정할 수 있으며 태그 값은 각 팀의 기본값으로 설정 **하여 관리됩니다** . 이 설정을 해제하면 팀별로 **태그를** 변경할 수 없습니다.
    - **제안된 기본 태그**: 기본 태그 집합을 추가하려면 이 태그를 사용합니다. 최대 25개의 태그를 추가할 수 있으며 각 태그는 최대 25자를 포함할 수 있습니다. 팀 소유자와 구성원(기능이 사용하도록 설정된 경우)은 이러한 제안을 사용하거나, 추가하거나, 새 태그 집합을 만들 수 있습니다.
    - **사용자 지정 태그 만들기**: 사용자가 설정한 제안된 기본 태그 이외의 태그를 추가할 수 있도록 하려면 이 설정을 켭니다. 이 기능을 해제하면 제안된 기본 태그만 사용할 수 있습니다. 이 옵션을 해제하는 경우 하나 이상의 기본 태그를 추가해야 합니다.

## <a name="manage-custom-tags-settings-for-a-team"></a>팀의 사용자 지정 태그 설정 관리

Let 팀 소유자가 Microsoft Teams 관리 센터에서 **태그 설정을 관리할 수 있는 사용자를 재정** 의하도록 설정하면 팀 소유자는 구성원이 팀 수준에서 태그를 추가할 수 있는지 여부를 설정할 수 있습니다. 이렇게 하려면 팀의 **설정** 탭에서 **태그** 로 이동한 다음 태그를 추가할 수 있는 사용자를 선택합니다.

![팀 수준의 태그 설정 스크린샷.](media/manage-tags-team-settings.png)

## <a name="use-tags"></a>태그 사용

사용자 지정 태그를 추가하는 방법과 교대 근무로 태그 지정을 설정하는 방법(Teams Shifts 앱을 사용하는 경우). 자세한 내용은 [Teams 태그 사용을](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e) 확인하세요.

### <a name="create-and-assign-custom-tags"></a>사용자 지정 태그 만들기 및 할당

사용자 지정 태그를 만들고 할당하려면 앱 왼쪽에서 **Teams** 선택한 다음 목록에서 팀을 찾습니다. **3개의 추가 옵션을** 선택한 다음 **태그 관리를** 선택합니다. 여기서 태그를 만들어 팀의 사용자에게 할당할 수 있습니다.

![Teams 클라이언트에서 태그를 적용하는 방법의 스크린샷.](media/manage-tags-teams.png)

태그를 삭제하려면 태그 옆에 있는 **1개의 추가 옵션을** 선택한 다음, **태그 삭제** 를 선택합니다.

### <a name="set-up-tagging-by-shift"></a>교대 근무로 태그 지정 설정

교대 근무로 태그를 지정하면 사용자가 실시간으로 교대 근무 중인 사용자에게 연결할 수 있습니다. Teams Shifts 앱에서 일정 및 교대 근무 그룹 이름과 일치하는 태그가 있는 사용자를 자동으로 할당하여 동적 역할 기반 메시징을 사용하도록 설정합니다. 알림은 태그를 사용하여 채팅을 시작하거나 채널 게시물에서 교대 근무 중인 사용자에게만 전송됩니다. 

1. Teams [Shifts 앱](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop)으로 이동합니다.
2. [교대 근무 그룹을](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea#bkmk_organizeshiftsbygroup) 만들고 역할과 같은 특성의 이름을 지정합니다. 예를 들어 EngineerOnCall입니다. Shift 그룹 이름은 태그의 이름이 됩니다.
3. 팀 구성원에게 교대 근무를 할당하여 [일정을 채웁니다](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea). 완료되면 Shifts 앱의 오른쪽 위 모서리에서 **팀과 공유** 를 선택합니다.
4. 예약된 교대 근무가 태그 지정 서비스를 채울 때까지 15분 정도 기다립니다.
5. Teams 태그를 사용하는 모든 위치에서 태그를 사용합니다.

## <a name="related-topics"></a>관련 주제

[Teams 태그 사용](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)

[Teams에서 조직의 교대 근무 앱 관리](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)

[Shifts 도움말 설명서](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
