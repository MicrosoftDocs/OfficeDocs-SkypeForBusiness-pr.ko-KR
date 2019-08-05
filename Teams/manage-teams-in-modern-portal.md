---
title: Microsoft 팀원 관리 센터에서 팀 관리
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/08/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: islubin
description: Microsoft 팀 관리 센터에서 팀을 보거나 업데이트 하는 방법에 대해 알아봅니다.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c205c8d3b4f57935c1882530815643a90357d1aa
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "36183860"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a>Microsoft 팀원 관리 센터에서 팀 관리
==========================================


## <a name="overview"></a>개요

IT 관리자는 조직이 공동 작업을 위해 설정한 팀을 확인 하거나 업데이트 해야 하거나 팀 구성원 수 감소에 대 한 소유자 할당과 같은 재구성 작업을 수행 해야 할 수도 있습니다. Microsoft 팀 PowerShell 모듈 및 Microsoft 팀 관리 센터를 통해 조직에서 사용 되는 팀을 관리할 수 있습니다. 이러한 두 도구 집합을 사용 하는 전체 관리 기능을 보려면 다음 역할 중 하나를 할당 했는지 확인 해야 합니다.

- 전역 관리자
- 팀 서비스 관리자

팀에서 관리자 역할에 대 한 자세한 정보를 확인 하 여 팀을 [관리 하](using-admin-roles.md)고, [microsoft 팀 cmdlet 참조](https://docs.microsoft.com/powershell/teams/?view=teams-ps)에서 팀을 관리 하는 PowerShell cmdlet을 사용 하는 방법에 대해 자세히 알아볼 수 있습니다.  

이 문서에서는 Microsoft 팀 관리 센터의 팀을 위한 관리 도구에 대 한 개요를 제공 합니다.

## <a name="teams-overview-grid"></a>팀 개요 그리드

팀의 관리 도구는 Microsoft 팀 관리 센터의 **팀** 노드 아래에 있습니다. (관리 센터에서 팀 **** > **관리**를 선택 합니다.) 각 팀은 Office 365 그룹에서 지원 되며,이 노드는 조직에서 Microsoft 팀을 사용 하도록 설정 된 그룹의 보기를 제공 합니다.

![팀 개요 그리드 스크린샷](media/manage-teams-in-modern-portal-image1.png)  

눈금에는 다음 속성이 표시 됩니다.

- **팀 이름**
- **채널** -기본 일반 채널을 포함 하 여 팀에 있는 모든 채널의 수입니다.
- **사용자** -테 넌 트의 소유자, 게스트 및 구성원을 비롯 한 총 사용자 수입니다.
- **소유자** -이 팀의 소유자 수입니다.
- **게스트** -이 팀의 구성원 인 Azure ACTIVE Directory B2B 게스트 사용자의 수입니다.
- **프라이버시** -Office 365의 지원 그룹의 가시성/AccessType.
- **상태** -이 팀의 보관 또는 활성 상태입니다.  [보관 또는 팀 복원](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)에 대 한 팀의 보관에 대해 자세히 알아보세요.
- **GroupID** -지원 Office 365 그룹의 고유 GroupID입니다.
- **분류** -조직에서 사용 되는 경우 지원 Office 365 그룹에 할당 된 분류입니다.  [조직의 Office 그룹에 대 한 만들기 분류의](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization)분류에 대해 자세히 알아보세요.
- **Description** -Office 백업 365 그룹에 대 한 설명

### <a name="search"></a>찾아

검색에서는 현재 "시작 문자" 문자열을 지원 하 고 **팀 이름** 필드를 검색 합니다.

### <a name="edit"></a>편집한

표에서 팀을 선택한 다음 **편집** 단추를 선택 하 여 그룹 및 팀 관련 설정을 편집할 수 있습니다.

![팀 편집 옵션 스크린샷](media/manage-teams-in-modern-portal-image2.png)

## <a name="team-profile"></a>팀 프로필

팀 이름을 클릭 하 여 주 팀 개요 표에서 팀의 팀 프로필 페이지로 이동할 수 있습니다. 팀 프로필 페이지에는 팀 (및 해당 지원 O365 그룹)에 속한 구성원, 소유자, 게스트, 팀의 채널 및 설정도 표시 됩니다. 팀 프로필 페이지에서 다음을 수행할 수 있습니다.

- 구성원 및 소유자를 추가 하거나 제거 합니다.
- 채널 추가 또는 제거 (일반 채널은 제거할 수 없음)
- 팀 및 그룹 설정을 업데이트 합니다.
 
![예제 팀 프로필 스크린샷](media/manage-teams-in-modern-portal-image3.png)

## <a name="making-changes-to-teams"></a>팀 변경 하기

팀의 다음 요소를 변경할 수 있습니다.
- **팀의 사용자** -구성원을 추가 또는 제거 하 고 소유자의 상태를 올리거나 내릴 수 있습니다.
- **채널** -새 채널을 추가 하거나 기존 채널을 제거할 수 있습니다.  기본 "일반" 채널을 삭제할 수 없으며, 만든 후에는 채널 이름만 편집할 수 있습니다 (설명은 아님).
- **팀 이름**
- **팀 설명**
- **팀 개인 정보** -공개 또는 비공개
- **팀 분류** -Office 365 그룹 분류에 의해 지원 됩니다.
- **팀 구성원 설정** -팀 구성원 설정 선택

## <a name="other-supported-changes-to-teams"></a>팀에 대해 지원 되는 다른 변경 사항

- **삭제** -팀은 팀 및 해당 하는 Office 365 그룹의 일시 삭제입니다.  실수로 삭제 된 팀을 복원 하려면 [삭제 된 Office 365 그룹 복원](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide)의 지침을 따릅니다.
- **보관** -팀을 Microsoft 팀 내에서 읽기 전용 모드로 전환 합니다.  관리자는 관리 포털을 통해 조직을 대신 하 여 팀을 보관 하 고 보관할 수 있습니다.


팀에 대해 변경한 내용이 기록 됩니다. 그룹 설정을 수정 하는 경우 (이름, 설명, 사진, 개인 정보, 분류 또는 팀 구성원을 변경 하는 경우), 감사 파이프라인을 통해 이러한 변경 내용이 적용 됩니다. 팀 관련 설정에 대해 작업을 수행 하는 경우 변경 내용이 추적 되어 팀의 일반 채널에서 사용자에 게 특성화 됩니다.

## <a name="troubleshooting"></a>해결사

**문제: 팀 개요 표에서 누락 된 팀**

Microsoft 팀 관리 센터에 진입 하는 경우 팀의 **** 일부 팀이 팀 개요 그리드 목록에서 누락 되었습니다.

**원인**:이 문제는 시스템에서 앱을 잘못 (또는 아직) 프로 파일링 했을 때 해당 항목이 인식 될 수 있는 속성 누락으로 이어질 때 발생 합니다.

**해결: MS Graph를 통해 수동으로 속성을 올바른 값으로 설정 합니다.**

**"[UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** cmdlet을 사용 하 여 "**Externaldirectoryobjectid**" 특성으로 Exchange Online powershell을 통해 얻을 수 있는 실제 groupid 인 쿼리의 **{groupid}** 을 (를) 바꿉니다.

1. Access [그래프 탐색기](https://developer.microsoft.com/en-us/graph/graph-explorer)

2. 왼쪽 메뉴의 그래프 탐색기에 로그인

3. 쿼리 줄을 다음으로 변경: 패치 > v 1.0 >https://graph.microsoft.com/v1.0/groups/{groupid}

4. 요청 본문에 다음 값을 추가 합니다. {"resourceProvisioningOptions": ["팀"]}

5. 오른쪽 위에서 쿼리를 실행 합니다.

6. Microsoft 팀 관리 센터에서 팀이 올바르게 표시 되는지 확인-팀 개요


## <a name="learn-more"></a>더 알아보세요

[Microsoft 팀 cmdlet 참조](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
[Microsoft 팀의 관리자 역할](using-admin-roles.md)
<!--
[Plan for Teams Lifecycle Management](plan-for-teams-lifecycle-management.md)
-->

