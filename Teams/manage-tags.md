---
title: Microsoft Teams에서 태그 관리
author: cichur
ms.author: v-cichur
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
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams에서 조직에서 태그를 사용하는 방법을 관리하는 방법을 배워야 합니다.
ms.openlocfilehash: 9d9ba4584572ad1e1707c250ee92c49e9aaec7fa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831238"
---
# <a name="manage-tags-in-microsoft-teams"></a>Microsoft Teams에서 태그 관리

> [!NOTE]
> 이 문서에서 설명하는 기능 중 하나인 Shift로 태그 **지정은** 아직 릴리스되지 않았습니다. 발표가 됐고 곧 출시될 예정입니다. 관리자인 경우 메시지 센터(Microsoft 365 관리 센터)에서 이 기능이 [릴리스될 때를 찾을 수 있습니다.](https://portal.office.com/adminportal/home) 예정된 Teams 기능을 계속 사용하길 [원하면 Microsoft 365 로드맵을 확인해 보아야 합니다.](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams)

## <a name="overview"></a>개요

Microsoft Teams의 태그를 통해 사용자는 팀의 일부 사용자와 빠르고 쉽게 연결할 수 있습니다. 사용자 지정 태그를 만들고 할당하여 역할, 프로젝트, 기술 또는 위치와 같은 특성에 따라 다른 사용자로 분류할 수 있습니다. 또는 [Shifts](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Shifts) 앱의 일정 및 교대 근무 정보에 따라 태그를 사용자에게 자동으로 할당할 수 있습니다(출시 예정). 태그가 하나 또는 여러 팀 구성원에게 추가된 후 채널 게시물에서 @mentions 팀의 모든 사용자가 태그를 추가하거나 해당 태그가 할당된 사용자와의 대화를 시작할 수 있습니다.

앞에서 설명한 대로 Teams에는 두 종류의 태그가 있습니다.

- **사용자 지정 태그:** 팀 소유자 및 팀 구성원(기능이 사용하도록 설정된 경우)은 수동으로 태그를 만들고 사용자에게 할당할 수 있습니다. 예를 들어 "Designer" 또는 "Radiologist" 태그는 이름을 입력할 필요 없이 팀의 사용자 집합에 도달합니다.
- **교대 근무에 따라** 태그 지정(출시 예정): 이 기능을 사용하면 Teams의 [Shifts](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop) 앱에서 일정 및 교대 근무 그룹 이름과 일치하는 태그가 자동으로 할당됩니다. 예를 들어 "EngineerOnCall" 태그는 채팅 또는 채널 게시물에서 태그를 사용할 때 Shifts에서 작업할 예정인 모든 엔지니어에게 도달합니다. 교대 근무에 따라 태그를 지정하면 Teams는 사용자가 정보를 빠르게 릴레이해야 할 때 교대 근무 직원의 이름을 알지 수 없습니다. Shift에 따라 태그 지정은 Teams에서 Shifts와 통합하여 JDA, Kronos 및 AMiON과 같은 주요 인력 관리 시스템에서 지원할 수도 있습니다. 이 기능을 설정하는 방법에 대한 자세한 내용은 Shift를 사용하여 태그 [지정을 참조합니다.](#set-up-tagging-by-shift-coming-soon)

> [!NOTE]
> 태그는 비공개 채널에서 아직 지원되지 않습니다. 태그는 아직 미국 GCC(Government Community Cloud), GCC High 또는 DoD(국방부) 조직에서 사용할 수 없습니다. 

## <a name="how-tags-work"></a>태그 작동 방식

태그를 수동으로 추가하거나 특정 팀의 한 사용자에게 자동으로 할당할 수 있습니다. 그런 다음 채팅의 to 줄에  @mentions 또는 팀의 표준 채널에 있는 게시물에서 사용할 수 있습니다. Teams에서 태그를 사용하는 방법에 대한 몇 가지 예는 다음과 같습니다.

- 매장 관리자는 채널에 공지 사항을 게시하여 모든 계산원에게 알릴 수 있습니다.
- 병원 관리자가 채널의 모든 방사성 환자에게 메시지를 전송합니다.
- 마케팅 관리자가 모든 디자이너와 그룹 채팅을 시작합니다.
- 간호사는 모든 통화 중리과 의사에게 메시지를 전송합니다. (곧 지원됨)
- 시스템 엔지니어는 모든 교대 근무 현장 엔지니어에게 알리기 위해 채널에 공지를 게시합니다. (곧 지원됨)

태그가 채널 @mentioned 경우 태그와 연결된 팀 구성원은 다른 모든 사용자와 마찬가지로 알림을 @mention.

## <a name="manage-custom-tags-for-your-organization"></a>조직의 사용자 지정 태그 관리

관리자는 Microsoft Teams 관리 센터에서 조직 전체에서 태그를 사용하는 방법을 제어할 수 있습니다. 현재 PowerShell을 사용하여 태그를 관리할 수 없습니다.

![Microsoft Teams 관리 센터의 태그 지정 설정 스크린샷](media/manage-tags-admin-settings.png)

팀에는 최대 100개 태그가 있을 수 있으며, 최대 100명까지 팀 구성원을 태그에 할당할 수 있으며, 단일 사용자에게 최대 25개 태그를 할당할 수 있습니다. 

### <a name="set-who-can-add-custom-tags"></a>사용자 지정 태그를 추가할 수 있는 사용자 설정

기본적으로 팀 소유자는 사용자 지정 태그를 추가할 수 있습니다. 팀 소유자와 팀 구성원이 태그를 만들고 편집, 삭제 및 관리할 수 있도록 이 설정을 변경하거나 조직의 태그를 해제할 수 있습니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 전체 **설정** Teams 설정을  >  **클릭합니다.**
2. 태그 **지정 아래에서** 태그 옆에 있는 다음 옵션 중 하나를 선택합니다. 

    - **팀 소유자 및 구성원:** 팀 소유자와 구성원이 태그를 관리할 수 있도록 허용합니다.
    - **팀 소유자:** 팀 소유자가 태그를 관리할 수 있도록 허용합니다.
    - **사용 안 선:** 태그를 해제합니다.

### <a name="configure-custom-tags-settings"></a>사용자 지정 태그 설정 구성

조직 전체에서 사용자 지정 태그를 사용하는 방법을 제어하도록 다음 태그 설정을 구성할 수 있습니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 전체 **설정** Teams 설정을  >  **클릭합니다.**
2. 태그 **지정 아래에서** 조직의 요구에 따라 다음을 설정하세요.

    - **태그를** 관리할 수 있는 팀 소유자를 우선할 수 있습니다. 이 설정을 설정하면 팀 소유자는 팀 구성원이 팀  내에서 태그를 만들고 관리할 수 있는지 여부를 설정할 수 있으며 태그 값은 각 팀의 기본값으로 설정하여 관리할 수 있습니다. 이 설정을 해제하면 태그는 팀당 변경할 수 없는 설정으로 관리됩니다. 
    - **권장 기본 태그:** 이 태그를 사용하여 기본 태그 집합을 추가합니다. 최대 25개 태그를 추가할 수 있으며 각 태그는 최대 25자까지 포함할 수 있습니다. 팀 소유자 및 구성원(기능이 사용하도록 설정된 경우)은 이러한 제안을 사용하여 추가하거나 새 태그 집합을 만들 수 있습니다.
    - **사용자 지정 태그를** 만들 수 있습니다. 이 설정을 켜서 사람들이 설정한 제안된 기본 태그가 다른 태그를 추가할 수 있습니다. 이 기능을 해제하면 사용자가 제안된 기본 태그만 사용할 수 있습니다. 이 기능을 해제하는 경우 하나 이상의 기본 태그를 추가해야 합니다.

## <a name="manage-custom-tags-settings-for-a-team"></a>팀에 대한 사용자 지정 태그 설정 관리

팀 소유자가  Microsoft Teams 관리 센터에서 태그 설정을 관리할 수 있는 권한을 우선적으로 설정한 경우 팀 소유자는 구성원이 팀 수준에서 태그를 추가할 수 있는지 여부를 설정할 수 있습니다. 이렇게하려면 팀의  설정 탭에서 태그로 이동한 다음 태그를 추가할 수 있는 사용자 선택

![팀 수준의 태그 설정 스크린샷](media/manage-tags-team-settings.png)

## <a name="use-tags"></a>태그 사용

다음은 사용자 지정 태그를 추가하는 방법과 Shift를 통해 태그 지정을 설정하는 방법(Teams에서 Shifts 앱을 사용하는 경우)입니다. 자세한 내용은 Teams에서 태그 [사용에 대해 자세히 알아보고](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)

### <a name="create-and-assign-custom-tags"></a>사용자 지정 태그 만들기 및 할당

사용자 지정 태그를 만들고 할당하려면 앱 왼쪽에 있는 **Teams를** 선택한 다음 목록에서 팀을 찾아야 합니다. 추가 **̇ ̇ ̇** 선택하고 태그 관리를 **선택합니다.** 여기에서 태그를 만들고 팀의 사용자에게 할당할 수 있습니다.

![Teams 클라이언트에서 태그를 적용하는 방법 스크린샷 ](media/manage-tags-teams.png)

태그를 삭제하려면 태그 **̇ ̇ ̇ 추가** 옵션을 선택한 다음 태그 **삭제를 선택합니다.**

### <a name="set-up-tagging-by-shift-coming-soon"></a>Shift를 통해 태그 지정 설정(출시 예정)

1. Teams에서 [Shifts 앱으로 이동하세요.](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop)
2. 교대 [근무 그룹을 만들고](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea#bkmk_organizeshiftsbygroup) 역할과 같은 특성 다음에 이름을 지정합니다. 예를 들어 EngineerOnCall입니다. 교대 근무 그룹 이름은 태그의 이름이 됩니다.
3. [팀 구성원에게](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea) 교대 근무를 할당하여 일정을 작성합니다. 완료되면 Shifts 앱의 오른쪽 위 모서리에서 팀과 **공유를 선택합니다.**
4. 예약된 교대 근무가 태그 지정 서비스를 채우기까지 15분 정도 기다립니다.
5. Teams에서 태그를 사용하는 모든 곳에서 태그를 사용하세요.

교대 근무에 따라 태그를 지정하면 사용자가 실시간으로 교대 근무에 있는 사용자에게 도달할 수 있습니다. 알림은 태그를 사용하여 채팅을 시작하거나 채널 게시물에서 교대 근무 중일 때만 전송됩니다.

## <a name="related-topics"></a>관련 항목

[Teams에서 태그 사용](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)

[Teams에서 조직의 교대 근무 앱 관리](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)

[Shifts 도움말 설명서](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
