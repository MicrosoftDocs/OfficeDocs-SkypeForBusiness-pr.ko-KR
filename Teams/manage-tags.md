---
title: Microsoft 팀의 태그 관리
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: acolonna
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
ms.openlocfilehash: 5fbfa980f1cf6acd8ce32af810bf2527ece3d1fa
ms.sourcegitcommit: 0549714f17f9994cf832a303ec9bc58a537c3a51
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2020
ms.locfileid: "42951553"
---
# <a name="manage-tags-in-microsoft-teams"></a>Microsoft 팀의 태그 관리

Microsoft 팀의 태그를 통해 사용자가 팀의 일부 사용자와 통신할 수 있습니다. 한 명 또는 여러 팀 구성원에 게 태그를 추가 하 여 사용자의 올바른 하위 집합으로 쉽게 연결할 수 있습니다. 팀 소유자 및 구성원 (기능을 사용 하도록 설정 된 경우) 사용자에 게 하나 이상의 태그를 추가할 수 있습니다. 그런 다음 팀의 모든 사용자가 채널을 게시할 때 태그를 사용 하거나 해당 태그를 할당 한 사람만 대화를 시작 하는 것을 @mentions 수 있습니다.

> [!NOTE]
> 태그는 개인 채널에서 아직 지원 되지 않습니다. 미국 정부 커뮤니티 클라우드 (GCC), GCC High 또는 보안 부서 (DoD) 조직에서는 아직 태그를 사용할 수 없습니다. 

## <a name="how-tags-work"></a>태그가 작동 하는 방식

특정 팀의 사용자에 게 태그를 추가할 수 있습니다. 태그를 추가한 후에는 채팅 또는 팀의 표준 채널에서 @mentions에 사용할 수 있습니다. 다음은 팀에서 태그를 사용 하는 방법에 대 한 몇 가지 예입니다.

- 스토어 관리자가 채널에 알림을 게시 하 고 모든 cashiers에 게 알려야 합니다.
- 그룹 제품 관리자가 채널의 모든 제품 관리자에 게 메시지를 전송 하려고 합니다.
- 병원 관리자가 채널의 모든 radiologists에 게 메시지를 보내려고 합니다.
- 마케팅 관리자가 모든 설계자와 그룹 채팅을 시작 하려고 합니다. 

자세한 내용은 [팀에서 태그를 사용 하 여](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)확인해 보세요.

## <a name="manage-tags-for-your-organization"></a>조직의 태그 관리

관리자는 Microsoft 팀 관리 센터에서 태그를 추가할 수 있는 사람과 사용자의 조직에서 태그를 사용 하는 방법을 제어할 수 있습니다.

![Microsoft 팀 관리 센터의 태그 설정 스크린샷](media/manage-tags-admin-settings.png)

### <a name="set-who-can-add-tags"></a>태그를 추가할 수 있는 사용자 설정

기본적으로 팀 소유자는 태그를 추가할 수 있습니다. 팀 소유자와 팀 구성원이 태그를 추가할 수 있도록이 설정을 변경 하거나 조직의 태그를 해제할 수 있습니다.

1. Microsoft 팀 관리 센터의 왼쪽 탐색 모음에서 **조직 전체 설정** > **팀 설정을**클릭 합니다.
2. **태깅**아래에서 **태그**지정 옆에 있는에서 다음 옵션 중 하나를 선택 합니다.

    - **팀 소유자 및 구성원**: 팀 소유자 및 구성원이 태그를 추가할 수 있도록 허용 합니다.
    - **팀 소유자**: 팀 소유자가 태그를 추가할 수 있도록 허용 합니다.
    - **사용 안 함**: 태그 끄기.

### <a name="configure-tags-settings"></a>태그 설정 구성

조직에서 태그를 사용 하는 방법을 제어 하도록 다음 태그 설정을 구성할 수 있습니다.

1. Microsoft 팀 관리 센터의 왼쪽 탐색 모음에서 **조직 전체 설정** > **팀 설정을**클릭 합니다.
2. **태그**아래에서 조직의 요구 사항에 따라 다음을 설정 합니다.

    - **팀 소유자는 태그를 적용할 수 있는 사람을 무시할 수**있습니다 .이 옵션이 설정 되어 있는 경우 팀 소유자는 구성원에 게 팀 설정에서 태그를 추가 하도록 허용 하거나 허용 하지 않을 수 있습니다.
    - **구성원은 추가 태그를 추가할 수**있습니다. 팀 구성원이 태그를 추가할 수 있도록 허용 하는 경우, 사용자가 설정한 제안 된 기본 태그 이외의 태그를 팀 구성원이 추가 하도록 설정 합니다. 이 옵션이 해제 되어 있는 경우 팀 구성원은 기본 태그만 사용할 수 있습니다.
    - **제안 된 기본 태그**:이를 사용 하 여 기본 태그 집합을 추가 합니다. 태그는 최대 25 개까지 추가할 수 있으며, 각 태그는 25 자까지 입력할 수 있습니다. 팀 소유자 및 구성원 (해당 기능이 해당 기능을 사용 하도록 설정 된 경우)을 사용 하거나, 해당 제안에 추가 하거나, 새 태그 집합을 만들 수 있습니다.

## <a name="manage-tags-settings-for-a-team"></a>팀의 태그 설정 관리

팀 소유자가 Microsoft 팀 관리 센터에서 **태그를 적용할 수 있는 사용자를 재정의할 수** 있는 경우 팀 소유자는 멤버가 팀 수준에서 태그를 추가할 수 있는지 여부를 설정할 수 있습니다. 이렇게 하려면 팀의 **설정** 탭에서 **태그로**이동한 다음 태그를 추가할 수 있는 사용자를 선택 합니다.

![팀 수준의 태그 설정 스크린샷](media/manage-tags-team-settings.png)

## <a name="add-tags-in-teams"></a>팀에서 태그 추가

팀에서 팀원에 대 한 팀 관리 페이지의 **구성원** 탭에는 **태그** 열이 포함 됩니다. 팀 소유자 및 구성원 (이 기능을 사용 하도록 설정 된 경우) 구성원 옆에 있는 **태그 관리** 를 클릭 하 여 해당 구성원에 대 한 추천 태그 목록을 표시 하 고 목록에 태그를 추가할 수 있습니다.

![팀 클라이언트에서 태그를 적용 하는 방법 스크린샷 ](media/manage-tags-teams.png) 
