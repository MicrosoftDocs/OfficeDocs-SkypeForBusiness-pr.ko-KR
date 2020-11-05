---
title: Microsoft 팀의 태그 관리
author: lanachin
ms.author: v-lanac
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
description: Microsoft 팀에서 조직에 태그를 사용 하는 방법을 관리 하는 방법을 알아봅니다.
ms.openlocfilehash: 718a2401aa8e015a6dec2b6a4c6116a567aaf82d
ms.sourcegitcommit: 20f881285edf699ebf36320664166c95ccd6df35
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2020
ms.locfileid: "48919060"
---
# <a name="manage-tags-in-microsoft-teams"></a>Microsoft 팀의 태그 관리

> [!NOTE]
> 이 문서에서 설명 하는 **shift의 태그** 지정 기능 중 하나가 아직 해제 되지 않았습니다. 발표 되었으며 곧 제공 될 예정입니다. 관리자 인 경우 [Microsoft 365 관리 센터](https://portal.office.com/adminportal/home)의 메시지 센터에서이 기능을 언제 릴리스할 것인지 확인할 수 있습니다. 예정 된 팀 기능을 계속 유지 하려면 [Microsoft 365 로드맵을](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams)확인 하세요.

## <a name="overview"></a>개요

Microsoft 팀의 태그를 통해 사용자는 팀의 일부 사용자와 빠르고 쉽게 연결할 수 있습니다. 사용자 지정 태그를 만들고 지정 하 여 특성 (예: 역할, 프로젝트, 기술 또는 위치)을 기준으로 사용자를 분류할 수 있습니다. 또는 [교대 근무](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Shifts) (출시 예정)의 일정 및 교대 정보에 따라 태그를 사용자에 게 자동으로 배정할 수 있습니다. 한 명 또는 여러 팀 구성원에 게 태그를 추가한 후에는 팀의 모든 사용자가 채널을 게시할 수 있도록 하거나 해당 태그를 할당 한 사람만 대화를 시작 하는 등의 작업을 하는 것이 @mentions에 사용 됩니다.

앞에서 언급 한 것 처럼 팀에는 두 종류의 태그가 있습니다.

- **사용자 지정 태그** : 팀 소유자 및 팀 구성원 (해당 기능이 설정 된 경우)에서 수동으로 태그를 만들고 사용자에 게 할당할 수 있습니다. 예를 들어 "Designer" 또는 "Radiologist" 태그는 해당 이름을 입력할 필요 없이 팀의 여러 사용자 집합에 도달 합니다.
- **교대 근무 태그** 지정 (출시 예정):이 기능을 사용 하면 팀의 [교대 근무 앱](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop) 에서 일정 및 이동 그룹 이름과 일치 하는 태그를 자동으로 할당 받습니다. 예를 들어 "EngineerOnCall" 태그는 채팅 또는 채널 게시물에서 태그를 사용 하는 시점에 작업 교대 근무에 예약 된 모든 엔지니어에 게 도달 합니다. 교대 근무 태그를 사용 하면 사용자가 정보를 빠르게 전달 해야 할 때 교대 근무 직원의 이름을 인식 하는 데 도움이 됩니다. Shift 키를 사용 하 여 태그를 지정 하는 것은 JDA, 크로노스, AMiON 등의 주요 직원 관리 시스템을 팀의 교대 근무와 통합 하 여 백업할 수도 있습니다. 이 기능을 설정 하는 방법에 대해 자세히 알아보려면 [shift 키를 사용한 태그](#set-up-tagging-by-shift-coming-soon)지정을 참조 하세요.

> [!NOTE]
> 태그는 개인 채널에서 아직 지원 되지 않습니다. 미국 정부 커뮤니티 클라우드 (GCC), GCC High 또는 보안 부서 (DoD) 조직에서는 아직 태그를 사용할 수 없습니다. 

## <a name="how-tags-work"></a>태그가 작동 하는 방식

태그는 특정 팀의 사용자에 게 수동으로 추가 하거나 자동으로 할당할 수 있습니다. 그런 다음 채팅의 **받는** 사람 줄에 있는 @mentions 또는 팀의 표준 채널에 있는 게시물에서 사용할 수 있습니다. 다음은 팀에서 태그를 사용 하는 방법에 대 한 몇 가지 예입니다.

- Store manager는 채널에 알림을 게시 하 여 모든 cashiers에 알립니다.
- 병원 관리자는 채널의 모든 radiologists에 메시지를 보냅니다.
- 마케팅 관리자는 모든 디자이너와 그룹 채팅을 시작 합니다.
- Nurse는 모든 통화 cardiologists에 메시지를 보냅니다. (곧 지원됨)
- 시스템 엔지니어가 모든 on shift 필드 엔지니어에 게 알림을 알리기 위해 채널에 공지를 게시 합니다. (곧 지원됨)

채널 대화에서 태그를 @mentioned 하는 경우 태그와 연결 된 팀 구성원은 다른 @mention 같은 방법으로 알림을 받습니다.

## <a name="manage-custom-tags-for-your-organization"></a>조직의 사용자 지정 태그 관리

관리자는 Microsoft 팀 관리 센터에서 조직 간에 태그를 사용 하는 방법을 제어할 수 있습니다. 현재는 PowerShell을 사용 하 여 태그를 관리할 수 없습니다.

![Microsoft 팀 관리 센터의 태그 설정 스크린샷](media/manage-tags-admin-settings.png)

팀은 최대 100 태그를 포함할 수 있으며, 태그에는 최대 100 팀 구성원을 배정할 수 있으며 최대 25 개의 태그를 단일 사용자에 게 할당할 수 있습니다. 

### <a name="set-who-can-add-custom-tags"></a>사용자 지정 태그를 추가할 수 있는 사용자 설정

기본적으로 팀 소유자는 사용자 지정 태그를 추가할 수 있습니다. 팀 소유자와 팀 구성원이 태그를 만들거나, 편집 하거나, 삭제 하 고, 관리 하는 데 사용할 수 있도록이 설정을 변경 하거나 조직의 태그를 해제할 수 있습니다.

1. Microsoft 팀 관리 센터의 왼쪽 탐색 모음에서 **조직 전체 설정**  >  **팀 설정을** 클릭 합니다.
2. **태깅** 아래에서 다음 옵션 중 하나를 선택 하 **여 태그** 옆에 있는을 (를) 관리 합니다.

    - **팀 소유자 및 구성원** : 팀 소유자 및 구성원이 태그를 관리할 수 있도록 허용 합니다.
    - **팀 소유자** : 팀 소유자가 태그를 관리할 수 있도록 허용 합니다.
    - **사용 안 함** : 태그 끄기.

### <a name="configure-custom-tags-settings"></a>사용자 지정 태그 설정 구성

조직에서 사용자 지정 태그를 사용 하는 방법을 제어 하도록 다음 태그 설정을 구성할 수 있습니다.

1. Microsoft 팀 관리 센터의 왼쪽 탐색 모음에서 **조직 전체 설정**  >  **팀 설정을** 클릭 합니다.
2. **태그** 아래에서 조직의 요구 사항에 따라 다음을 설정 합니다.

    - **팀 소유자가 태그를 관리할 수 있는 사용자를 재정의 하도록** 설정: 팀 소유자는 팀 구성원이 팀 내에서 태그를 만들고 관리할 수 있는지 여부와 태그의 값을 각 팀의 기본값을 설정 **하 여** 관리할 수 있습니다. 이 설정을 해제 하는 경우 태그를 **관리 하** 는 설정을 팀 당 변경할 수 없습니다.
    - **제안 된 기본 태그** :이를 사용 하 여 기본 태그 집합을 추가 합니다. 태그는 최대 25 개까지 추가할 수 있으며, 각 태그는 25 자까지 입력할 수 있습니다. 팀 소유자 및 구성원 (해당 기능이 해당 기능을 사용 하도록 설정 된 경우)을 사용 하거나, 해당 제안에 추가 하거나, 새 태그 집합을 만들 수 있습니다.
    - **사용자 지정 태그를 만들 수** 있습니다 .이 설정을 사용 하면 사용자가 설정한 제안 된 기본 태그 대신 태그를 추가할 수 있습니다. 이 기능을 끄면 사용자는 제안 된 기본 태그만 사용할 수 있습니다. 이 기능을 해제 한 경우 하나 이상의 기본 태그를 추가 했는지 확인 합니다.

## <a name="manage-custom-tags-settings-for-a-team"></a>팀에 대 한 사용자 지정 태그 설정 관리

팀 소유자가 Microsoft 팀 관리 센터에서 **태그를 관리할 수 있는 사용자를 재정의 하도록** 설정한 경우 팀 소유자는 멤버가 팀 수준에서 태그를 추가할 수 있는지 여부를 설정할 수 있습니다. 이렇게 하려면 팀의 **설정** 탭에서 **태그로** 이동한 다음 태그를 추가할 수 있는 사용자를 선택 합니다.

![팀 수준의 태그 설정 스크린샷](media/manage-tags-team-settings.png)

## <a name="use-tags"></a>태그 사용

사용자 지정 태그를 추가 하는 방법과 shift 키를 사용 하 여 태그를 설정 하는 방법에 대해 설명 합니다 (팀에서 이동 하는 앱의 경우). 자세한 내용은 [팀에서 태그를 사용 하 여](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)확인해 보세요.

### <a name="create-and-assign-custom-tags"></a>사용자 지정 태그 만들기 및 할당

사용자 지정 태그를 만들고 할당 하려면 앱의 왼쪽에서 **팀** 을 선택한 다음 목록에서 팀을 찾습니다. **̇ ̇ ̇ 추가 옵션** 을 선택한 다음, **태그 관리** 를 선택 합니다. 여기서는 태그를 만들어 팀 구성원에 게 할당할 수 있습니다.

![팀 클라이언트에서 태그를 적용 하는 방법 스크린샷 ](media/manage-tags-teams.png)

태그를 삭제 하려면 태그 옆에 있는 **̇ ̇ ̇ 추가 옵션** 을 선택한 다음 **태그 삭제** 를 선택 합니다.

### <a name="set-up-tagging-by-shift-coming-soon"></a>교대 근무 태그 설정 (예정 대로)

1. 팀에서 [교대 근무 앱](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop)으로 이동 합니다.
2. [Shift 그룹](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea#bkmk_organizeshiftsbygroup) 을 만들고 역할과 같은 특성 뒤에 이름을 이름으로 만듭니다. 예를 EngineerOnCall. Shift 그룹 이름에는 태그의 이름이 지정 됩니다.
3. 팀 구성원에 게 교대 근무를 배정 하 여 [일정을 작성](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea) 합니다. 완료 되 면 이동 앱의 오른쪽 위 모서리에서 **팀과 공유** 를 선택 합니다.
4. 태그 서비스를 채우기 위해 예정 된 교대 근무에 대해 15 분간 기다립니다.
5. 팀에서 태그를 사용 하는 곳 어디에서 든 태그를 사용 하세요.

Shift 키를 사용 하 여 태그를 지정 하면 사용자가 실시간으로 이동 하는 사람에 게 연락을 주고 받을 수 있습니다. 알림은 태그를 사용 하 여 채팅을 시작 하거나 채널을 게시할 때 교대 근무 사용자 에게만 전송 됩니다.

## <a name="related-topics"></a>관련 항목

[팀에서 태그 사용](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)

[Teams에서 조직의 교대 근무 앱 관리](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)

[도움말 문서 이동](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
