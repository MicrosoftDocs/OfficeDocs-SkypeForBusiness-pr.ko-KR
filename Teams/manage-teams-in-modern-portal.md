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
description: Microsoft 팀 관리 센터에서 팀을 보거나 업데이트 하는 방법에 대해 알아봅니다.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0c7adfc2762d632f600f2982445f381139263894
ms.sourcegitcommit: ed7439d03e37c9c0184daf5215a68c5492932a83
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "38290938"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="c8436-103">Microsoft 팀원 관리 센터에서 팀 관리</span><span class="sxs-lookup"><span data-stu-id="c8436-103">Manage teams in the Microsoft Teams admin center</span></span>
==========================================

## <a name="overview"></a><span data-ttu-id="c8436-104">개요</span><span class="sxs-lookup"><span data-stu-id="c8436-104">Overview</span></span>

<span data-ttu-id="c8436-105">이 문서에서는 Microsoft 팀 관리 센터의 팀을 위한 관리 도구에 대 한 개요를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8436-105">This article provides an overview of the management tools for Teams in the Microsoft Teams admin center.</span></span> <span data-ttu-id="c8436-106">이 짧은 비디오를 보고 시작 합니다 (3 분).</span><span class="sxs-lookup"><span data-stu-id="c8436-106">Start by watching this short video (3 minutes):</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE476Yi]

<span data-ttu-id="c8436-107">관리자는 조직에서 공동 작업을 위해 설정한 팀을 보거나 업데이트 해야 하거나, 소유 하는 팀이 적은 사용자를 지정 하는 등의 재구성 작업을 수행 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8436-107">As an admin, you may need to view or update the teams that your organization set up for collaboration, or you might need to perform remediation actions such as assigning owners for ownerless teams.</span></span> <span data-ttu-id="c8436-108">Microsoft 팀 PowerShell 모듈 및 Microsoft 팀 관리 센터를 통해 조직에서 사용 되는 팀을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8436-108">You can manage the teams used in your organization through both the Microsoft Teams PowerShell module and the Microsoft Teams admin center.</span></span> <span data-ttu-id="c8436-109">이러한 두 도구 집합을 사용 하는 전체 관리 기능을 보려면 다음 역할 중 하나를 할당 했는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8436-109">For full administration capabilities using these two toolsets, you should make sure that you are assigned one of the following roles:</span></span>

- <span data-ttu-id="c8436-110">전역 관리자</span><span class="sxs-lookup"><span data-stu-id="c8436-110">Global Administrator</span></span>
- <span data-ttu-id="c8436-111">Teams 서비스 관리자</span><span class="sxs-lookup"><span data-stu-id="c8436-111">Teams Service Administrator</span></span>

<span data-ttu-id="c8436-112">팀에서 관리자 역할에 대 한 자세한 정보를 확인 하 여 팀을 [관리 하](using-admin-roles.md)고, [microsoft 팀 cmdlet 참조](https://docs.microsoft.com/powershell/teams/?view=teams-ps)에서 팀을 관리 하는 PowerShell cmdlet을 사용 하는 방법에 대해 자세히 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8436-112">You can learn more about admin roles in Teams in [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md), and you can read more about how to use the PowerShell cmdlets for managing teams in the [Microsoft Teams cmdlet reference](https://docs.microsoft.com/powershell/teams/?view=teams-ps).</span></span>



## <a name="teams-overview-grid"></a><span data-ttu-id="c8436-113">팀 개요 그리드</span><span class="sxs-lookup"><span data-stu-id="c8436-113">Teams overview grid</span></span>

<span data-ttu-id="c8436-114">팀의 관리 도구는 Microsoft 팀 관리 센터의 **팀** 노드 아래에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8436-114">Management tools for teams are under the **Teams** node in the Microsoft Teams admin center.</span></span> <span data-ttu-id="c8436-115">(관리 센터 **에서 팀** > **관리**를 선택 합니다.) 각 팀은 Office 365 그룹에서 지원 되며,이 노드는 조직에서 Microsoft 팀을 사용 하도록 설정 된 그룹의 보기를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8436-115">(In the admin center, select **Teams** > **Manage teams**.) Each team is backed by an Office 365 group, and this node provides a view of groups that have been Microsoft Teams-enabled in your organization.</span></span>

![팀 개요 그리드 스크린샷](media/manage-teams-in-modern-portal-grid.png)  

<span data-ttu-id="c8436-117">눈금에는 다음 속성이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8436-117">The grid displays the following properties:</span></span>

- <span data-ttu-id="c8436-118">**팀 이름**</span><span class="sxs-lookup"><span data-stu-id="c8436-118">**Team name**</span></span>
- <span data-ttu-id="c8436-119">**채널** -기본 일반 채널을 포함 하 여 팀에 있는 모든 채널의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="c8436-119">**Channels** - a count of all channels in the team, including the default General channel.</span></span>
- <span data-ttu-id="c8436-120">**팀 구성원** -소유자, 게스트 및 테 넌 트의 구성원을 비롯 한 총 사용자의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="c8436-120">**Team members** - a count of total users, including owners, guests, and members from your tenant.</span></span>
- <span data-ttu-id="c8436-121">**소유자** -이 팀의 소유자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="c8436-121">**Owners** - a count of owners for this team.</span></span>
- <span data-ttu-id="c8436-122">**게스트** -이 팀의 구성원 인 Azure ACTIVE Directory B2B 게스트 사용자의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="c8436-122">**Guests** - a count of Azure Active Directory B2B guest users who are members of this team.</span></span>
- <span data-ttu-id="c8436-123">**프라이버시** -Office 365의 지원 그룹의 가시성/AccessType.</span><span class="sxs-lookup"><span data-stu-id="c8436-123">**Privacy** - the Visibility/AccessType of the backing Office 365 group.</span></span>
- <span data-ttu-id="c8436-124">**상태** -이 팀의 보관 또는 활성 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="c8436-124">**Status** - the Archived or Active status for this team.</span></span> <span data-ttu-id="c8436-125">자세한 내용은 [팀 보관 또는 복원](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)의 팀을 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="c8436-125">Learn more about archiving teams in [Archive or restore a team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span></span>
- <span data-ttu-id="c8436-126">**Description** -Office 백업 365 그룹에 대 한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="c8436-126">**Description** - the description of the backing Office 365 group.</span></span>
- <span data-ttu-id="c8436-127">**분류** -조직에서 사용 되는 경우 지원 Office 365 그룹에 할당 된 분류입니다.</span><span class="sxs-lookup"><span data-stu-id="c8436-127">**Classification** - the classification (if used in your organization) assigned to the backing Office 365 group.</span></span> <span data-ttu-id="c8436-128">[조직의 Office 그룹에 대 한 만들기 분류의](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization)분류에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="c8436-128">Learn more about classifications at [Create classifications for Office groups in your organization](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).</span></span>
- <span data-ttu-id="c8436-129">**GroupID** -지원 Office 365 그룹의 고유 GroupID입니다.</span><span class="sxs-lookup"><span data-stu-id="c8436-129">**GroupID** - the unique GroupID of the backing Office 365 group.</span></span>

> [!NOTE]
> <span data-ttu-id="c8436-130">이러한 속성이 모두 눈금에 표시 되지 않으면 **열 편집** 아이콘을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8436-130">If you don't see all these properties in the grid, click the **Edit columns** icon.</span></span> <span data-ttu-id="c8436-131">**열 편집** 창에서 토글을 사용 하 여 모눈의 열을 설정 하거나 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8436-131">In the **Edit columns** pane, you can use the toggles to turn on or turn off columns in the grid.</span></span> <span data-ttu-id="c8436-132">완료 되 면 **적용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8436-132">When you're finished, click **Apply**.</span></span>

### <a name="add"></a><span data-ttu-id="c8436-133">추가</span><span class="sxs-lookup"><span data-stu-id="c8436-133">Add</span></span>

<span data-ttu-id="c8436-134">새 팀을 추가 하려면 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8436-134">To add a new team, click **Add**.</span></span> <span data-ttu-id="c8436-135">**새 팀 추가** 창에서 팀에 이름과 설명을 지정 하 고, 비공개 또는 공용 팀으로 만들 것인지, 분류를 설정할지를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8436-135">In the **Add a new team** pane, give the team a name and description, set whether you want to make it a private or public team, and set the classification.</span></span>

### <a name="edit"></a><span data-ttu-id="c8436-136">편집한</span><span class="sxs-lookup"><span data-stu-id="c8436-136">Edit</span></span>

<span data-ttu-id="c8436-137">그룹 및 팀 관련 설정을 편집 하려면 팀 이름 왼쪽에 있는을 클릭 하 여 팀을 선택한 다음 **편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8436-137">To edit group and team-specific settings, select the team by clicking to the left of the team name, and then select **Edit**.</span></span>

### <a name="archive"></a><span data-ttu-id="c8436-138">보관할</span><span class="sxs-lookup"><span data-stu-id="c8436-138">Archive</span></span>

<span data-ttu-id="c8436-139">팀을 보관할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8436-139">You can archive a team.</span></span> <span data-ttu-id="c8436-140">팀을 보관 하면 팀 내에서 읽기 전용 모드로 전환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8436-140">Archiving a team puts the team into read-only mode within Teams.</span></span> <span data-ttu-id="c8436-141">관리자는 관리 센터에서 조직을 대신 하 여 팀을 보관 하 고 보관을 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8436-141">As an admin, you can archive and un-archive teams on behalf of your organization in the admin center.</span></span> 

### <a name="delete"></a><span data-ttu-id="c8436-142">삭제</span><span class="sxs-lookup"><span data-stu-id="c8436-142">Delete</span></span>

<span data-ttu-id="c8436-143">팀 삭제는 팀 및 해당 하는 Office 365 그룹의 일시 삭제입니다.</span><span class="sxs-lookup"><span data-stu-id="c8436-143">Deleting a team is a soft-delete of the team and corresponding Office 365 group.</span></span> <span data-ttu-id="c8436-144">실수로 삭제 된 팀을 복원 하려면 [삭제 된 Office 365 그룹 복원](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="c8436-144">To restore a mistakenly deleted team, follow the instructions in [Restore a deleted Office 365 Group](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide).</span></span>

### <a name="search"></a><span data-ttu-id="c8436-145">찾아</span><span class="sxs-lookup"><span data-stu-id="c8436-145">Search</span></span>

<span data-ttu-id="c8436-146">검색에서는 현재 "시작 문자" 문자열을 지원 하 고 **팀 이름** 필드를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8436-146">Search currently supports the string "Begins with" and searches the **Team name** field.</span></span>

## <a name="team-profile"></a><span data-ttu-id="c8436-147">팀 프로필</span><span class="sxs-lookup"><span data-stu-id="c8436-147">Team profile</span></span>

<span data-ttu-id="c8436-148">팀 이름을 클릭 하 여 주 팀 개요 표에서 팀의 팀 프로필 페이지로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8436-148">You can navigate to the team profile page of any team from the main teams overview grid by clicking  the team name.</span></span> <span data-ttu-id="c8436-149">팀 프로필 페이지에는 팀 (및 해당 지원 Office 365 그룹)에 속하는 구성원, 소유자, 게스트 및 팀의 채널 및 설정도 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8436-149">The team profile page shows the members, owners, and guests that belong to the team (and its backing Office 365 group), as well as the team’s channels and settings.</span></span> <span data-ttu-id="c8436-150">팀 프로필 페이지에서 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8436-150">From the team profile page, you can:</span></span>

- <span data-ttu-id="c8436-151">구성원 및 소유자를 추가 하거나 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8436-151">Add or remove members and owners.</span></span>
- <span data-ttu-id="c8436-152">채널을 추가 하거나 제거 합니다 (일반 채널을 제거할 수 없음).</span><span class="sxs-lookup"><span data-stu-id="c8436-152">Add or remove channels (note that you can't remove the General channel).</span></span>
- <span data-ttu-id="c8436-153">팀 및 그룹 설정을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8436-153">Change team and group settings.</span></span>
 
![팀 프로필 예제 스크린샷](media/manage-teams-in-modern-portal-team-profile-page.png)

## <a name="making-changes-to-teams"></a><span data-ttu-id="c8436-155">팀 변경 하기</span><span class="sxs-lookup"><span data-stu-id="c8436-155">Making changes to teams</span></span>

<span data-ttu-id="c8436-156">팀 프로필 페이지에서 팀의 다음과 같은 요소를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8436-156">On the team's profile page, you can change the following elements of a team:</span></span>

- <span data-ttu-id="c8436-157">**구성원** -구성원을 추가 또는 제거 하 고 소유자의 수준을 올리거나 내립니다.</span><span class="sxs-lookup"><span data-stu-id="c8436-157">**Members** - add or remove members and promote or demote owners.</span></span>
- <span data-ttu-id="c8436-158">**채널** -새 채널을 추가 하 고 기존 채널을 편집 또는 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8436-158">**Channels** - add new channels, and edit or remove existing channels.</span></span> <span data-ttu-id="c8436-159">기본 일반 채널을 삭제할 수 없다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="c8436-159">Remember that you can't delete the default General channel.</span></span>
- <span data-ttu-id="c8436-160">**팀 이름**</span><span class="sxs-lookup"><span data-stu-id="c8436-160">**Team name**</span></span>
- <span data-ttu-id="c8436-161">**설명**</span><span class="sxs-lookup"><span data-stu-id="c8436-161">**Description**</span></span>
- <span data-ttu-id="c8436-162">**개인 정보** -팀이 공개 인지 또는 전용인 지 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8436-162">**Privacy** - set whether the team is public or private.</span></span>
- <span data-ttu-id="c8436-163">**분류** -이는 Office 365 그룹 분류가 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8436-163">**Classification** - this is backed by your Office 365 group classifications.</span></span> <span data-ttu-id="c8436-164">**기밀**, **기밀**, **일반**중에서 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8436-164">Choose **Confidential**, **Highly Confidential**, or **General**.</span></span>
- <span data-ttu-id="c8436-165">**대화 설정** -구성원이 보낸 메시지를 편집 하 고 삭제할 수 있는지 여부를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8436-165">**Conversations settings** - set whether members can edit and delete sent messages.</span></span>
- <span data-ttu-id="c8436-166">**채널 설정** -구성원이 새 채널을 만들 수 있는지 여부를 지정 하 고, 탭, 커넥터 및 앱을 추가, 편집 및 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8436-166">**Channels settings** - set whether members can create new channels and edit existing ones, and add, edit, and remove tabs, connectors, and apps.</span></span>

<span data-ttu-id="c8436-167">팀에 대해 변경한 내용이 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8436-167">The changes that you make to a team are logged.</span></span> <span data-ttu-id="c8436-168">그룹 설정을 수정 하는 경우 (이름, 설명, 사진, 개인 정보, 분류 또는 팀 구성원을 변경 하는 경우), 감사 파이프라인을 통해 변경 내용이 사용자에 게 특성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8436-168">If you're modifying group settings (changing the name, description, photo, privacy, classification, or team members), the changes are attributed to you through the audit pipeline.</span></span> <span data-ttu-id="c8436-169">팀 특정 설정에 대해 작업을 수행 하는 경우 팀의 일반 채널에서 변경 내용이 추적 되 고 특성이 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8436-169">If you're performing actions against Teams-specific settings, your changes are tracked and attributed to you in the General channel of the team.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="c8436-170">해결사</span><span class="sxs-lookup"><span data-stu-id="c8436-170">Troubleshooting</span></span>

<span data-ttu-id="c8436-171">**문제: 팀 개요 표에서 누락 된 팀**</span><span class="sxs-lookup"><span data-stu-id="c8436-171">**Issue: Teams missing from the Team overview grid**</span></span>

<span data-ttu-id="c8436-172">팀 목록에 팀의 일부가 누락 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c8436-172">Some of your teams are missing from the list of teams in the Teams overview grid.</span></span>

<span data-ttu-id="c8436-173">**원인**:이 문제는 시스템에서 앱을 잘못 (또는 아직) 프로 파일링 했을 때 해당 항목이 인식 될 수 있는 속성 누락으로 이어질 때 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8436-173">**Cause**: This issue occurs when the team was incorrectly (or not yet) profiled by the system which can lead to a missing property for it to be recognized.</span></span>

<span data-ttu-id="c8436-174">**해결: MS Graph를 통해 수동으로 속성을 올바른 값으로 설정 합니다.**</span><span class="sxs-lookup"><span data-stu-id="c8436-174">**Resolution: Manually set the property to the correct value via MS Graph**</span></span>

<span data-ttu-id="c8436-175">**"[UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** cmdlet을 사용 하 여 "**Externaldirectoryobjectid**" 특성으로 Exchange Online powershell을 통해 얻을 수 있는 실제 groupid 인 쿼리의 **{groupid}** 을 (를) 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="c8436-175">Replace **{groupid}** in the Query for the actual GroupId in question, which you can get via the Exchange Online powershell, with the **"[Get-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** cmdlet, as the "**ExternalDirectoryObjectId**" attribute.</span></span>

1. <span data-ttu-id="c8436-176">Access [Graph 탐색기](https://developer.microsoft.com/graph/graph-explorer)</span><span class="sxs-lookup"><span data-stu-id="c8436-176">Access [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

2. <span data-ttu-id="c8436-177">왼쪽 메뉴에서 Graph 탐색기에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8436-177">Sign in to Graph Explorer on the left menu.</span></span>

3. <span data-ttu-id="c8436-178">쿼리 줄을 다음과 같이 변경 합니다. > v 1.0 https://graph.microsoft.com/v1.0/groups/{groupid}의 패치 >.</span><span class="sxs-lookup"><span data-stu-id="c8436-178">Change the query line to: PATCH > v1.0 > https://graph.microsoft.com/v1.0/groups/{groupid}.</span></span>

4. <span data-ttu-id="c8436-179">요청 본문에 다음 값을 추가 합니다: {"resourceProvisioningOptions": ["팀"]}.</span><span class="sxs-lookup"><span data-stu-id="c8436-179">Add the following value on the request body: {"resourceProvisioningOptions": ["Team"]}.</span></span>

5. <span data-ttu-id="c8436-180">오른쪽 위에서 쿼리를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8436-180">Run the query on the top-right.</span></span>

6. <span data-ttu-id="c8436-181">팀이 Microsoft 팀 관리 센터-팀 개요에 올바르게 표시 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8436-181">Confirm the team appears correctly in the Microsoft Teams admin center - Team Overview.</span></span>

## <a name="learn-more"></a><span data-ttu-id="c8436-182">더 알아보세요</span><span class="sxs-lookup"><span data-stu-id="c8436-182">Learn more</span></span>

- [<span data-ttu-id="c8436-183">팀 cmdlet 참조</span><span class="sxs-lookup"><span data-stu-id="c8436-183">Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
- [<span data-ttu-id="c8436-184">팀 관리자 역할을 사용 하 여 팀 관리</span><span class="sxs-lookup"><span data-stu-id="c8436-184">Use Teams administrator roles to manage Teams</span></span>](using-admin-roles.md)
- [<span data-ttu-id="c8436-185">Teams에서 수명 주기 관리 계획</span><span class="sxs-lookup"><span data-stu-id="c8436-185">Plan for lifecycle management in Teams</span></span>](plan-teams-lifecycle.md)
