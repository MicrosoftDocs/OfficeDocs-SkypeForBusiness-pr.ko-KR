---
title: 관리 센터에서 Microsoft Teams 관리
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: islubin, jastark
description: 조직이 관리 센터에서 공동 작업을 위해 설정한 팀을 보거나 업데이트하는 Microsoft Teams 방법을 알아보습니다.
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
ms.openlocfilehash: ea81ad854224e08142f9c87725d25176dcc60d44
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237544"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a>관리 센터에서 Microsoft Teams 관리
==========================================

## <a name="overview"></a>개요

이 문서에서는 관리 센터의 Teams 관리 Microsoft Teams 제공합니다.

관리자는 조직에서 공동 작업을 위해 설정한 팀을 보거나 업데이트해야 할 수 있습니다. 또는 소유자 없는 팀에 소유자 할당과 같은 수정 작업을 수행해야 할 수 있습니다. PowerShell 모듈 및 Microsoft Teams 관리 센터를 통해 조직에서 Microsoft Teams 수 있습니다. 에서 관리 센터에 액세스할 수 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 있습니다. 이러한 두 도구세트를 사용하는 전체 관리 기능의 경우 다음 역할 중 하나를 할당해야 합니다.

- 전역 관리자
- Teams 관리자

관리자 역할 사용 Teams 관리 Microsoft Teams 관리자 [](using-admin-roles.md)역할에 대한 자세한 내용은 Teams cmdlet에서 팀 관리에 PowerShell [cmdlet을](/powershell/teams/?view=teams-ps)사용하는 방법에 대해 Microsoft Teams 있습니다.



## <a name="teams-overview-grid"></a>Teams 개요 눈금

팀에 대한 관리 도구는 Teams **관리** 센터의 Microsoft Teams 노드 아래에 있습니다. (관리 센터에서   >  Teams **팀 관리**.) 각 팀은 Microsoft 365 지원하며, 이 노드는 조직에서 지원된 Microsoft Teams 보기를 제공합니다.

![개요 Teams 스크린샷](media/manage-teams-in-modern-portal-grid.png)  

눈금에는 다음 속성이 표시됩니다.

- **팀 이름**
- **채널** - 기본 일반 채널을 포함하여 팀의 모든 채널의 수입니다.
- **팀 구성원** - 테넌트의 소유자, 게스트 및 구성원을 포함하여 총 사용자 수입니다.
- **소유자** - 이 팀의 소유자 수입니다.
- **게스트** - 이 팀의 Azure Active Directory B2B 게스트 사용자의 수입니다.
- **개인 정보** - 백업 그룹의 가시성/AccessType Microsoft 365 있습니다.
- **상태** - 이 팀의 보관 상태 또는 활성 상태입니다. 팀 보관 또는 팀 복원에 대해 [자세히 알아보면 됩니다.](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)
- **설명** - 백업 그룹 Microsoft 365 설명입니다.
- **분류** - 백업 그룹에 할당된 분류(조직에서 사용되는 경우) Microsoft 365. 조직의 그룹에 대한 분류 [만들기에서 분류에 Office 자세히 알아보습니다.](/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization)
- **GroupID** - 백업 그룹의 고유한 GroupID Microsoft 365 있습니다.

> [!NOTE]
> 눈금에 이러한 속성이 모두 표시되지 않는 경우 열 편집 **아이콘을** 클릭합니다. 열 **편집** 창에서 토글을 사용하여 눈금에서 열을 켜거나 해제할 수 있습니다. 완료되면 적용 을 **클릭합니다.**

### <a name="add"></a>추가

새 팀을 추가하려면 추가를 **클릭합니다.** 새 **팀** 추가 창에서 팀에 이름과 설명을 지정하고, 개인 팀 또는 공용 팀으로 만들지 여부를 설정하고 분류를 설정합니다.

> [!NOTE]
> 새로 만든 팀은 관리 센터에서 바로 관리할 수 Teams 같은 다른 클라이언트의 환경과 달리 관리 센터에서 Outlook.

### <a name="edit"></a>편집

그룹 및 팀별 설정을 편집하려면 팀 이름의 왼쪽을 클릭하여 팀을 선택한 다음 **편집을 선택합니다.**

### <a name="archive"></a>보관

팀을 보관할 수 있습니다. 팀을 보관하면 팀을 읽기 전용 모드로 전환할 수 Teams. 관리자는 관리 센터에서 조직을 대신하여 팀을 보관하고 보관을 언아이저장할 수 있습니다. 

### <a name="delete"></a>삭제

팀을 삭제하는 것은 팀 및 해당 팀 그룹에서 Microsoft 365 삭제합니다. 잘못 삭제된 팀을 복원하려면 삭제된 그룹 복원의 [지침을 따릅니다.](/microsoft-365/admin/create-groups/restore-deleted-group)

### <a name="search"></a>검색

검색은 현재 문자열 "시작"을 지원하고 팀 이름 **필드를 검색합니다.**

## <a name="team-profile"></a>팀 프로필

팀 이름을 클릭하여 주 팀 개요 눈금에서 모든 팀의 팀 프로필 페이지로 이동할 수 있습니다. 팀 프로필 페이지에는 팀에 속한 멤버, 소유자 및 게스트(및 해당 Microsoft 365 그룹) 및 팀의 채널 및 설정이 표시됩니다. 팀 프로필 페이지에서 다음을 할 수 있습니다.

- 구성원 및 소유자를 추가하거나 제거합니다.
- 채널을 추가하거나 제거합니다(일반 채널을 제거할 수 없습니다).
- 팀 및 그룹 설정을 변경합니다.
 
![예제 팀 프로필 스크린샷](media/manage-teams-in-modern-portal-team-profile-page.png)

## <a name="making-changes-to-teams"></a>팀 변경

팀의 프로필 페이지에서 팀의 다음 요소를 변경할 수 있습니다.

- **멤버** - 구성원을 추가하거나 제거하고 소유자를 승격하거나 강하합니다.
- **채널** - 새 채널을 추가하고 기존 채널을 편집하거나 제거합니다. 기본 일반 채널은 삭제할 수 없습니다.
- **팀 이름**
- **설명**
- **개인 정보** - 팀이 공용인지 비공개인지 여부를 설정합니다.
- **분류** - 그룹 분류가 Microsoft 365 뒷부분입니다. **기밀,** **기밀성,** 일반 을 **선택하십시오.**
- **대화 설정** - 구성원이 보낸 메시지를 편집하고 삭제할 수 있는지 여부를 설정합니다.
- **채널 설정** - 구성원이 새 채널을 만들고 기존 채널을 편집할 수 있는지 여부를 설정하고 탭, 커넥터 및 앱을 추가, 편집 및 제거합니다.

팀에 대한 변경 내용이 기록됩니다. 그룹 설정을 수정하는 경우(이름, 설명, 사진, 개인 정보, 분류 또는 팀 구성원 변경) 변경 내용은 감사 파이프라인을 통해 사용자에 기인합니다. 특정 설정에 대해 작업을 Teams 변경 내용을 추적하고 팀의 일반 채널에서 사용자에 기인합니다.

## <a name="troubleshooting"></a>문제 해결

**문제: Teams 개요 눈금에서 누락된 경우**

일부 팀은 개요 눈금의 팀 목록에서 Teams 없습니다.

**원인**: 팀이 시스템에 의해 프로파일링되지 않았거나 아직 프로필이 없는 경우 이 문제가 발생하여 인식할 속성이 누락될 수 있습니다.

**해결: MS를 통해 속성을 올바른 값으로 수동으로 Graph**

문제의 실제 GroupId에 대한 쿼리에서 **{groupid}를** **["Get-UnifiedGroup"](/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)** cmdlet을 **"externalDirectoryObjectId"** 특성으로 Exchange Online 파워 셸을 통해 얻을 수 있습니다.

1. 탐색기 [Graph 액세스합니다.](https://developer.microsoft.com/graph/graph-explorer)

2. 왼쪽 메뉴에서 Graph 탐색기에 로그인합니다.

3. 쿼리 줄을 : 패치 > v1.0 https://graph.microsoft.com/v1.0/groups/{groupid} >.

4. 요청 본문에 {"resourceProvisioningOptions": ["Team"]}을 추가합니다.

5. 오른쪽 위에서 쿼리를 실행합니다.

6. 팀이 관리 센터에 Microsoft Teams 확인 - 팀 개요입니다.

## <a name="learn-more"></a>자세히 알아보기

- [Teams cmdlet 참조](/powershell/teams/?view=teams-ps)  
- [관리자 Teams 관리자 역할을 사용하여 Teams](using-admin-roles.md)
- [Teams에서 수명 주기 관리 계획](plan-teams-lifecycle.md)