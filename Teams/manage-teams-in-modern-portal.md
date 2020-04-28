---
title: Microsoft 팀원 관리 센터에서 팀 관리
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: islubin, jastark
description: 조직에서 Microsoft 팀 관리 센터의 공동 작업에 대해 설정한 팀을 확인 하거나 업데이트 하는 방법에 대해 알아봅니다.
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8c83d985a277c8341565e44878ba03385e23a358
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905000"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a>Microsoft 팀원 관리 센터에서 팀 관리
==========================================

## <a name="overview"></a>개요

이 문서에서는 Microsoft 팀 관리 센터의 팀을 위한 관리 도구에 대 한 개요를 제공 합니다.

관리자는 조직에서 공동 작업을 위해 설정한 팀을 보거나 업데이트 해야 하거나, 소유 하는 팀이 적은 사용자를 지정 하는 등의 재구성 작업을 수행 해야 할 수 있습니다. Microsoft 팀 PowerShell 모듈 및 Microsoft 팀 관리 센터를 통해 조직에서 사용 되는 팀을 관리할 수 있습니다. 이러한 두 도구 집합을 사용 하는 전체 관리 기능을 보려면 다음 역할 중 하나를 할당 했는지 확인 해야 합니다.

- 전역 관리자
- Teams 서비스 관리자

팀에서 관리자 역할에 대 한 자세한 정보를 확인 하 여 팀을 [관리 하](using-admin-roles.md)고, [microsoft 팀 cmdlet 참조](https://docs.microsoft.com/powershell/teams/?view=teams-ps)에서 팀을 관리 하는 PowerShell cmdlet을 사용 하는 방법에 대해 자세히 알아볼 수 있습니다.



## <a name="teams-overview-grid"></a>팀 개요 그리드

팀의 관리 도구는 Microsoft 팀 관리 센터의 **팀** 노드 아래에 있습니다. (관리 센터 **에서 팀** > **관리**를 선택 합니다.) 각 팀은 Office 365 그룹에서 지원 되며,이 노드는 조직에서 Microsoft 팀을 사용 하도록 설정 된 그룹의 보기를 제공 합니다.

![팀 개요 그리드 스크린샷](media/manage-teams-in-modern-portal-grid.png)  

눈금에는 다음 속성이 표시 됩니다.

- **팀 이름**
- **채널** -기본 일반 채널을 포함 하 여 팀에 있는 모든 채널의 수입니다.
- **팀 구성원** -소유자, 게스트 및 테 넌 트의 구성원을 비롯 한 총 사용자의 수입니다.
- **소유자** -이 팀의 소유자 수입니다.
- **게스트** -이 팀의 구성원 인 Azure ACTIVE Directory B2B 게스트 사용자의 수입니다.
- **프라이버시** -Office 365의 지원 그룹의 가시성/AccessType.
- **상태** -이 팀의 보관 또는 활성 상태입니다. 자세한 내용은 [팀 보관 또는 복원](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)의 팀을 참고 하세요.
- **Description** -Office 백업 365 그룹에 대 한 설명입니다.
- **분류** -조직에서 사용 되는 경우 지원 Office 365 그룹에 할당 된 분류입니다. [조직의 Office 그룹에 대 한 만들기 분류의](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization)분류에 대해 자세히 알아보세요.
- **GroupID** -지원 Office 365 그룹의 고유 GroupID입니다.

> [!NOTE]
> 이러한 속성이 모두 눈금에 표시 되지 않으면 **열 편집** 아이콘을 클릭 합니다. **열 편집** 창에서 토글을 사용 하 여 모눈의 열을 설정 하거나 해제할 수 있습니다. 완료 되 면 **적용**을 클릭 합니다.

### <a name="add"></a>추가

새 팀을 추가 하려면 **추가**를 클릭 합니다. **새 팀 추가** 창에서 팀에 이름과 설명을 지정 하 고, 비공개 또는 공용 팀으로 만들 것인지, 분류를 설정할지를 설정 합니다.

### <a name="edit"></a>편집한

그룹 및 팀 관련 설정을 편집 하려면 팀 이름 왼쪽에 있는을 클릭 하 여 팀을 선택한 다음 **편집**을 선택 합니다.

### <a name="archive"></a>보관할

팀을 보관할 수 있습니다. 팀을 보관 하면 팀 내에서 읽기 전용 모드로 전환 됩니다. 관리자는 관리 센터에서 조직을 대신 하 여 팀을 보관 하 고 보관을 취소할 수 있습니다. 

### <a name="delete"></a>삭제

팀 삭제는 팀 및 해당 하는 Office 365 그룹의 일시 삭제입니다. 실수로 삭제 된 팀을 복원 하려면 [삭제 된 Office 365 그룹 복원](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide)의 지침을 따릅니다.

### <a name="search"></a>찾아

검색에서는 현재 "시작 문자" 문자열을 지원 하 고 **팀 이름** 필드를 검색 합니다.

## <a name="team-profile"></a>팀 프로필

팀 이름을 클릭 하 여 주 팀 개요 표에서 팀의 팀 프로필 페이지로 이동할 수 있습니다. 팀 프로필 페이지에는 팀 (및 해당 지원 Office 365 그룹)에 속하는 구성원, 소유자, 게스트 및 팀의 채널 및 설정도 표시 됩니다. 팀 프로필 페이지에서 다음을 수행할 수 있습니다.

- 구성원 및 소유자를 추가 하거나 제거 합니다.
- 채널을 추가 하거나 제거 합니다 (일반 채널을 제거할 수 없음).
- 팀 및 그룹 설정을 변경 합니다.
 
![팀 프로필 예제 스크린샷](media/manage-teams-in-modern-portal-team-profile-page.png)

## <a name="making-changes-to-teams"></a>팀 변경 하기

팀 프로필 페이지에서 팀의 다음과 같은 요소를 변경할 수 있습니다.

- **구성원** -구성원을 추가 또는 제거 하 고 소유자의 수준을 올리거나 내립니다.
- **채널** -새 채널을 추가 하 고 기존 채널을 편집 또는 제거 합니다. 기본 일반 채널을 삭제할 수 없다는 점에 유의 하세요.
- **팀 이름**
- **설명**
- **개인 정보** -팀이 공개 인지 또는 전용인 지 설정 합니다.
- **분류** -이는 Office 365 그룹 분류가 지원 합니다. **기밀**, **기밀**, **일반**중에서 선택 합니다.
- **대화 설정** -구성원이 보낸 메시지를 편집 하 고 삭제할 수 있는지 여부를 설정 합니다.
- **채널 설정** -구성원이 새 채널을 만들 수 있는지 여부를 지정 하 고, 탭, 커넥터 및 앱을 추가, 편집 및 제거 합니다.

팀에 대해 변경한 내용이 기록 됩니다. 그룹 설정을 수정 하는 경우 (이름, 설명, 사진, 개인 정보, 분류 또는 팀 구성원을 변경 하는 경우), 감사 파이프라인을 통해 변경 내용이 사용자에 게 특성화 됩니다. 팀 특정 설정에 대해 작업을 수행 하는 경우 팀의 일반 채널에서 변경 내용이 추적 되 고 특성이 지정 됩니다.

## <a name="troubleshooting"></a>문제 해결

**문제: 팀 개요 표에서 누락 된 팀**

팀 목록에 팀의 일부가 누락 되었습니다.

**원인**:이 문제는 시스템에서 앱을 잘못 (또는 아직) 프로 파일링 했을 때 해당 항목이 인식 될 수 있는 속성 누락으로 이어질 때 발생 합니다.

**해결: MS Graph를 통해 수동으로 속성을 올바른 값으로 설정 합니다.**

**"[UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** cmdlet을 사용 하 여 "**Externaldirectoryobjectid**" 특성으로 Exchange Online powershell을 통해 얻을 수 있는 실제 groupid 인 쿼리의 **{groupid}** 을 (를) 바꿉니다.

1. Access [Graph 탐색기](https://developer.microsoft.com/graph/graph-explorer)

2. 왼쪽 메뉴에서 Graph 탐색기에 로그인 합니다.

3. 쿼리 줄을 다음과 같이 변경 합니다. > v 1.0 https://graph.microsoft.com/v1.0/groups/{groupid}의 패치 >.

4. 요청 본문에 다음 값을 추가 합니다: {"resourceProvisioningOptions": ["팀"]}.

5. 오른쪽 위에서 쿼리를 실행 합니다.

6. 팀이 Microsoft 팀 관리 센터-팀 개요에 올바르게 표시 되는지 확인 합니다.

## <a name="learn-more"></a>자세히 알아보기

- [팀 cmdlet 참조](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
- [팀 관리자 역할을 사용 하 여 팀 관리](using-admin-roles.md)
- [Teams에서 수명 주기 관리 계획](plan-teams-lifecycle.md)
