---
title: Microsoft Teams 관리 센터에서 팀 관리
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: islubin, jastark
description: Microsoft Teams 관리 센터에서 조직에서 공동 작업을 위해 설정한 팀을 보거나 업데이트하는 방법을 배워야 합니다.
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
ms.openlocfilehash: c736cf17d263f097e97b32f856bc83cf2fe42a35
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814557"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터에서 팀 관리
==========================================

## <a name="overview"></a>개요

이 문서에서는 Microsoft Teams 관리 센터의 Teams용 관리 도구에 대한 개요를 제공합니다.

관리자는 조직에서 공동 작업을 위해 설정한 팀을 보거나 업데이트해야 할 수도 있습니다. 또는 소유자가 없는 팀에 소유자를 할당하는 등의 수정 작업을 수행해야 할 수도 있습니다. Microsoft Teams PowerShell 모듈과 Microsoft Teams 관리 센터를 통해 조직에서 사용되는 팀을 관리할 수 있습니다. .에서 관리 센터에 액세스할 수 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 있습니다. 이러한 두 도구 도구를 사용하는 전체 관리 기능의 경우 다음 역할 중 하나를 할당해야 합니다.

- 전역 관리자
- Teams 서비스 관리자

[Microsoft Teams](using-admin-roles.md)관리자 역할을 사용하여 Teams를 관리하는 Teams의 관리자 역할에 대해 자세히 알아보고, [Microsoft Teams cmdlet](https://docs.microsoft.com/powershell/teams/?view=teams-ps)참조에서 PowerShell cmdlet을 사용하여 팀을 관리하는 방법에 대해 자세히 읽어 볼 수 있습니다.



## <a name="teams-overview-grid"></a>Teams 개요 눈금

팀을 위한 관리 도구는 Microsoft Teams 관리 **센터의 Teams** 노드 아래에 있습니다. (관리 센터에서 **Teams 선택**  >  **팀 관리.)** 각 팀은 Microsoft 365 그룹에서 지원하며, 이 노드는 조직에서 Microsoft Teams를 사용하도록 설정된 그룹의 보기를 제공합니다.

![Teams 개요 눈금 스크린샷](media/manage-teams-in-modern-portal-grid.png)  

그리드에 다음 속성이 표시됩니다.

- **팀 이름**
- **채널** - 기본 일반 채널을 포함하여 팀의 모든 채널 수입니다.
- **팀 구성원** - 소유자, 게스트 및 테넌트의 구성원을 포함한 총 사용자 수입니다.
- **소유자** - 이 팀의 소유자 수입니다.
- **게스트** - 이 팀의 구성원인 Azure Active Directory B2B 게스트 사용자 수입니다.
- **개인 정보** 보호 - 지원 Microsoft 365 그룹의 가시성/AccessType입니다.
- **상태** - 이 팀의 보관 또는 활성 상태입니다. 팀을 보관하거나 팀을 복원하는 [방법을 자세히 배워볼 수 있습니다.](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)
- **설명** - 지원 Microsoft 365 그룹에 대한 설명입니다.
- **분류** - 백업 Microsoft 365 그룹에 할당된 분류(조직에서 사용되는 경우)입니다. 조직의 Office 그룹에 대한 분류 만들기에서 [분류에 대해 자세히 배워야 합니다.](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization)
- **GroupID** - 지원 Microsoft 365 그룹의 고유한 GroupID입니다.

> [!NOTE]
> 눈금에 이러한 속성이 모두 표시되지 않는 경우 열 편집 **아이콘을** 클릭합니다. 열 **편집** 창에서 토글을 사용하여 눈금에서 열을 켜거나 끄면 됩니다. 완료되면 적용을 **클릭합니다.**

### <a name="add"></a>추가

새 팀을 추가하려면 추가를 **클릭합니다.** 새 **팀** 추가 창에서 팀에 이름과 설명을 지정하고, 비공개 또는 공개 팀으로 만들지 여부를 설정하고, 분류를 설정할 수 있습니다.

> [!NOTE]
> 새로 만든 팀은 Outlook과 같은 다른 클라이언트의 환경과 달리 Teams 관리 센터에서 바로 관리할 수 있습니다.

### <a name="edit"></a>편집

그룹 및 팀별 설정을 편집하려면 팀 이름 왼쪽을 클릭하여 팀을 선택한 다음 편집을 **선택합니다.**

### <a name="archive"></a>보관

팀을 보관할 수 있습니다. 팀을 보관하면 팀이 Teams 내에서 읽기 전용 모드로 전환됩니다. 관리자는 관리 센터에서 조직을 대신하여 팀을 보관 및 보관해제할 수 있습니다. 

### <a name="delete"></a>삭제

팀 삭제는 팀 및 해당 Microsoft 365 그룹의 소프트 삭제입니다. 실수로 삭제된 팀을 복원하려면 삭제된 그룹 복원의 [지침을 따릅니다.](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group)

### <a name="search"></a>검색

검색은 현재 문자열 "Begins with"를 지원하고 팀 이름 **필드를 검색합니다.**

## <a name="team-profile"></a>팀 프로필

팀 이름을 클릭하여 주 팀 개요 그리드에서 모든 팀의 팀 프로필 페이지로 이동할 수 있습니다. 팀 프로필 페이지에는 팀(및 해당 지원 Microsoft 365 그룹)에 속한 구성원, 소유자 및 게스트와 팀의 채널 및 설정이 표시됩니다. 팀 프로필 페이지에서 다음을 할 수 있습니다.

- 구성원 및 소유자를 추가하거나 제거합니다.
- 채널을 추가하거나 제거합니다(일반 채널은 제거할 수 없습니다).
- 팀 및 그룹 설정을 변경합니다.
 
![팀 프로필 예제 스크린샷](media/manage-teams-in-modern-portal-team-profile-page.png)

## <a name="making-changes-to-teams"></a>팀 변경

팀의 프로필 페이지에서 팀의 다음 요소를 변경할 수 있습니다.

- **구성원** - 구성원을 추가 또는 제거하고 소유자를 승격 또는 강도합니다.
- **채널** - 새 채널을 추가하고 기존 채널을 편집하거나 제거합니다. 기본 일반 채널은 삭제할 수 없습니다.
- **팀 이름**
- **설명**
- **개인** 정보 보호 - 팀이 공개인지 비공개인지 여부를 설정합니다.
- **분류** - Microsoft 365 그룹 분류에서 지원됩니다. **기밀,** **매우 기밀 또는** 일반을 선택 **합니다.**
- **대화 설정** - 구성원이 보낸 메시지를 편집하고 삭제할 수 있는지 여부를 설정합니다.
- **채널 설정** - 구성원이 새 채널을 만들고 기존 채널을 편집할 수 있는지 여부를 설정하고 탭, 커넥터 및 앱을 추가, 편집 및 제거합니다.

팀에 대한 변경 내용이 기록됩니다. 그룹 설정(이름, 설명, 사진, 개인 정보, 분류 또는 팀 구성원 변경)을 수정하는 경우 변경 내용은 감사 파이프라인을 통해 변경됩니다. Teams 관련 설정에 대해 작업을 수행하는 경우 변경 내용이 추적 및 팀의 일반 채널에서 사용자에 대한 특성이 지정됩니다.

## <a name="troubleshooting"></a>문제 해결

**문제: 팀 개요 눈금에서 팀이 누락된 경우**

일부 팀이 Teams 개요 그리드의 팀 목록에서 누락됩니다.

**원인:** 이 문제는 시스템에서 팀이 잘못 프로파일링된 경우(또는 아직) 인식할 수 있는 속성이 누락될 수 있는 경우 발생합니다.

**해결: 수동으로 MS Graph를 통해 속성을 올바른 값으로 설정**

문제의 실제 GroupId에 대한 쿼리에서 **{groupid}를** 바꾸고, Exchange Online powershell을 통해 얻을 수 있습니다. **["Get-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** cmdlet을 **"ExternalDirectoryObjectId"** 특성으로 사용합니다.

1. Access [Graph Explorer.](https://developer.microsoft.com/graph/graph-explorer)

2. 왼쪽 메뉴에서 Graph Explorer에 로그인합니다.

3. 쿼리 줄을 PATCH > v1.0 https://graph.microsoft.com/v1.0/groups/{groupid} >.

4. 요청 본문에 {"resourceProvisioningOptions": ["Team"]}의 값을 추가합니다.

5. 오른쪽 위에서 쿼리를 실행합니다.

6. Microsoft Teams 관리 센터 - 팀 개요에 팀이 올바르게 나타나는지 확인합니다.

## <a name="learn-more"></a>자세히 알아보기

- [Teams cmdlet 참조](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
- [Teams 관리자 역할을 사용하여 Teams 관리](using-admin-roles.md)
- [Teams에서 수명 주기 관리 계획](plan-teams-lifecycle.md)
