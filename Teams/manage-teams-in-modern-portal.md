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
description: Microsoft Teams 관리 센터에서 조직에서 공동 작업을 위해 설정한 팀을 보거나 업데이트하는 방법에 대해 자세히 알아보습니다.
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
ms.openlocfilehash: 6bf864fefd3ac60c7531bd339a5587c8f2f0dd72
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094238"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="f36b1-103">Microsoft Teams 관리 센터에서 팀 관리</span><span class="sxs-lookup"><span data-stu-id="f36b1-103">Manage teams in the Microsoft Teams admin center</span></span>
==========================================

## <a name="overview"></a><span data-ttu-id="f36b1-104">개요</span><span class="sxs-lookup"><span data-stu-id="f36b1-104">Overview</span></span>

<span data-ttu-id="f36b1-105">이 문서에서는 Microsoft Teams 관리 센터의 Teams에 대한 관리 도구에 대한 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f36b1-105">This article provides an overview of the management tools for Teams in the Microsoft Teams admin center.</span></span>

<span data-ttu-id="f36b1-106">관리자는 조직에서 공동 작업을 위해 설정한 팀을 보거나 업데이트해야 할 수 있습니다. 또는 소유자 없는 팀에 소유자 할당과 같은 수정 작업을 수행해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f36b1-106">As an admin, you may need to view or update the teams that your organization set up for collaboration, or you might need to perform remediation actions such as assigning owners for ownerless teams.</span></span> <span data-ttu-id="f36b1-107">Microsoft Teams PowerShell 모듈과 Microsoft Teams 관리 센터를 통해 조직에서 사용되는 팀을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f36b1-107">You can manage the teams used in your organization through both the Microsoft Teams PowerShell module and the Microsoft Teams admin center.</span></span> <span data-ttu-id="f36b1-108">에서 관리 센터에 액세스할 수 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f36b1-108">You can access the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span> <span data-ttu-id="f36b1-109">이러한 두 도구세트를 사용하는 전체 관리 기능의 경우 다음 역할 중 하나를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f36b1-109">For full administration capabilities using these two toolsets, you should make sure that you are assigned one of the following roles:</span></span>

- <span data-ttu-id="f36b1-110">전역 관리자</span><span class="sxs-lookup"><span data-stu-id="f36b1-110">Global Administrator</span></span>
- <span data-ttu-id="f36b1-111">Teams 서비스 관리자</span><span class="sxs-lookup"><span data-stu-id="f36b1-111">Teams Service Administrator</span></span>

<span data-ttu-id="f36b1-112">Microsoft Teams 관리자 역할 사용에서 Teams에서 관리자 역할에 대해 자세히 알아보고 Microsoft [Teams](using-admin-roles.md)cmdlet 참조에서 팀을 관리하기 위해 PowerShell [cmdlet을](/powershell/teams/?view=teams-ps)사용하는 방법에 대해 자세히 알아보면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f36b1-112">You can learn more about admin roles in Teams in [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md), and you can read more about how to use the PowerShell cmdlets for managing teams in the [Microsoft Teams cmdlet reference](/powershell/teams/?view=teams-ps).</span></span>



## <a name="teams-overview-grid"></a><span data-ttu-id="f36b1-113">Teams 개요 눈금</span><span class="sxs-lookup"><span data-stu-id="f36b1-113">Teams overview grid</span></span>

<span data-ttu-id="f36b1-114">팀에 대한 관리 도구는 Microsoft Teams 관리 센터의 **Teams** 노드 아래에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f36b1-114">Management tools for teams are under the **Teams** node in the Microsoft Teams admin center.</span></span> <span data-ttu-id="f36b1-115">(관리 센터에서 Teams를 **선택합니다.**  >  **팀 관리**.) 각 팀은 Microsoft 365 그룹에서 지원하며 이 노드는 조직에서 Microsoft Teams를 사용하도록 설정한 그룹의 보기를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f36b1-115">(In the admin center, select **Teams** > **Manage teams**.) Each team is backed by a Microsoft 365 Group, and this node provides a view of groups that have been Microsoft Teams-enabled in your organization.</span></span>

![Teams 개요 눈금 스크린샷](media/manage-teams-in-modern-portal-grid.png)  

<span data-ttu-id="f36b1-117">눈금에는 다음 속성이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f36b1-117">The grid displays the following properties:</span></span>

- <span data-ttu-id="f36b1-118">**팀 이름**</span><span class="sxs-lookup"><span data-stu-id="f36b1-118">**Team name**</span></span>
- <span data-ttu-id="f36b1-119">**채널** - 기본 일반 채널을 포함하여 팀의 모든 채널의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="f36b1-119">**Channels** - a count of all channels in the team, including the default General channel.</span></span>
- <span data-ttu-id="f36b1-120">**팀 구성원** - 테넌트의 소유자, 게스트 및 구성원을 포함하여 총 사용자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="f36b1-120">**Team members** - a count of total users, including owners, guests, and members from your tenant.</span></span>
- <span data-ttu-id="f36b1-121">**소유자** - 이 팀의 소유자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="f36b1-121">**Owners** - a count of owners for this team.</span></span>
- <span data-ttu-id="f36b1-122">**게스트** - 이 팀의 구성원인 Azure Active Directory B2B 게스트 사용자의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="f36b1-122">**Guests** - a count of Azure Active Directory B2B guest users who are members of this team.</span></span>
- <span data-ttu-id="f36b1-123">**개인 정보** - 지원 Microsoft 365 그룹의 가시성/AccessType입니다.</span><span class="sxs-lookup"><span data-stu-id="f36b1-123">**Privacy** - the Visibility/AccessType of the backing Microsoft 365 group.</span></span>
- <span data-ttu-id="f36b1-124">**상태** - 이 팀의 보관 상태 또는 활성 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="f36b1-124">**Status** - the Archived or Active status for this team.</span></span> <span data-ttu-id="f36b1-125">팀 보관 또는 팀 복원에 대해 [자세히 알아보면 됩니다.](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)</span><span class="sxs-lookup"><span data-stu-id="f36b1-125">Learn more about archiving teams in [Archive or restore a team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span></span>
- <span data-ttu-id="f36b1-126">**설명** - 지원 Microsoft 365 그룹에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="f36b1-126">**Description** - the description of the backing Microsoft 365 group.</span></span>
- <span data-ttu-id="f36b1-127">**분류** - 지원 Microsoft 365 그룹에 할당된 분류(조직에서 사용되는 경우)입니다.</span><span class="sxs-lookup"><span data-stu-id="f36b1-127">**Classification** - the classification (if used in your organization) assigned to the backing Microsoft 365 group.</span></span> <span data-ttu-id="f36b1-128">조직의 Office 그룹에 대한 분류 만들기 에서 [분류에 대해 자세히 알아보습니다.](/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization)</span><span class="sxs-lookup"><span data-stu-id="f36b1-128">Learn more about classifications at [Create classifications for Office groups in your organization](/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).</span></span>
- <span data-ttu-id="f36b1-129">**GroupID** - 지원 Microsoft 365 그룹의 고유한 GroupID입니다.</span><span class="sxs-lookup"><span data-stu-id="f36b1-129">**GroupID** - the unique GroupID of the backing Microsoft 365 group.</span></span>

> [!NOTE]
> <span data-ttu-id="f36b1-130">눈금에 이러한 속성이 모두 표시되지 않는 경우 열 편집 **아이콘을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f36b1-130">If you don't see all these properties in the grid, click the **Edit columns** icon.</span></span> <span data-ttu-id="f36b1-131">열 **편집** 창에서 토글을 사용하여 눈금에서 열을 켜거나 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f36b1-131">In the **Edit columns** pane, you can use the toggles to turn on or turn off columns in the grid.</span></span> <span data-ttu-id="f36b1-132">완료되면 적용 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f36b1-132">When you're finished, click **Apply**.</span></span>

### <a name="add"></a><span data-ttu-id="f36b1-133">추가</span><span class="sxs-lookup"><span data-stu-id="f36b1-133">Add</span></span>

<span data-ttu-id="f36b1-134">새 팀을 추가하려면 추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f36b1-134">To add a new team, click **Add**.</span></span> <span data-ttu-id="f36b1-135">새 **팀** 추가 창에서 팀에 이름과 설명을 지정하고, 개인 팀 또는 공용 팀으로 만들지 여부를 설정하고 분류를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f36b1-135">In the **Add a new team** pane, give the team a name and description, set whether you want to make it a private or public team, and set the classification.</span></span>

> [!NOTE]
> <span data-ttu-id="f36b1-136">새로 만든 팀은 Outlook과 같은 다른 클라이언트의 환경과 달리 Teams 관리 센터에서 바로 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f36b1-136">Newly created teams can be managed right away in the Teams Admin Center, unlike the experience in other clients like, Outlook.</span></span>

### <a name="edit"></a><span data-ttu-id="f36b1-137">편집</span><span class="sxs-lookup"><span data-stu-id="f36b1-137">Edit</span></span>

<span data-ttu-id="f36b1-138">그룹 및 팀별 설정을 편집하려면 팀 이름의 왼쪽을 클릭하여 팀을 선택한 다음 **편집을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="f36b1-138">To edit group and team-specific settings, select the team by clicking to the left of the team name, and then select **Edit**.</span></span>

### <a name="archive"></a><span data-ttu-id="f36b1-139">보관</span><span class="sxs-lookup"><span data-stu-id="f36b1-139">Archive</span></span>

<span data-ttu-id="f36b1-140">팀을 보관할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f36b1-140">You can archive a team.</span></span> <span data-ttu-id="f36b1-141">팀을 보관하면 Teams 내에서 팀을 읽기 전용 모드로 전환합니다.</span><span class="sxs-lookup"><span data-stu-id="f36b1-141">Archiving a team puts the team into read-only mode within Teams.</span></span> <span data-ttu-id="f36b1-142">관리자는 관리 센터에서 조직을 대신하여 팀을 보관하고 보관을 언아이저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f36b1-142">As an admin, you can archive and un-archive teams on behalf of your organization in the admin center.</span></span> 

### <a name="delete"></a><span data-ttu-id="f36b1-143">삭제</span><span class="sxs-lookup"><span data-stu-id="f36b1-143">Delete</span></span>

<span data-ttu-id="f36b1-144">팀 삭제는 팀과 해당 Microsoft 365 그룹의 소프트 삭제입니다.</span><span class="sxs-lookup"><span data-stu-id="f36b1-144">Deleting a team is a soft-delete of the team and corresponding Microsoft 365 group.</span></span> <span data-ttu-id="f36b1-145">잘못 삭제된 팀을 복원하려면 삭제된 그룹 복원의 [지침을 따릅니다.](/microsoft-365/admin/create-groups/restore-deleted-group)</span><span class="sxs-lookup"><span data-stu-id="f36b1-145">To restore a mistakenly deleted team, follow the instructions in [Restore a deleted Group](/microsoft-365/admin/create-groups/restore-deleted-group).</span></span>

### <a name="search"></a><span data-ttu-id="f36b1-146">검색</span><span class="sxs-lookup"><span data-stu-id="f36b1-146">Search</span></span>

<span data-ttu-id="f36b1-147">검색은 현재 문자열 "시작"을 지원하고 팀 이름 **필드를 검색합니다.**</span><span class="sxs-lookup"><span data-stu-id="f36b1-147">Search currently supports the string "Begins with" and searches the **Team name** field.</span></span>

## <a name="team-profile"></a><span data-ttu-id="f36b1-148">팀 프로필</span><span class="sxs-lookup"><span data-stu-id="f36b1-148">Team profile</span></span>

<span data-ttu-id="f36b1-149">팀 이름을 클릭하여 주 팀 개요 눈금에서 모든 팀의 팀 프로필 페이지로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f36b1-149">You can navigate to the team profile page of any team from the main teams overview grid by clicking  the team name.</span></span> <span data-ttu-id="f36b1-150">팀 프로필 페이지에는 팀에 속한 구성원, 소유자 및 게스트(및 해당 지원 Microsoft 365 그룹)와 팀의 채널 및 설정이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f36b1-150">The team profile page shows the members, owners, and guests that belong to the team (and its backing Microsoft 365 group), as well as the team's channels and settings.</span></span> <span data-ttu-id="f36b1-151">팀 프로필 페이지에서 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f36b1-151">From the team profile page, you can:</span></span>

- <span data-ttu-id="f36b1-152">구성원 및 소유자를 추가하거나 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f36b1-152">Add or remove members and owners.</span></span>
- <span data-ttu-id="f36b1-153">채널을 추가하거나 제거합니다(일반 채널을 제거할 수 없습니다).</span><span class="sxs-lookup"><span data-stu-id="f36b1-153">Add or remove channels (note that you can't remove the General channel).</span></span>
- <span data-ttu-id="f36b1-154">팀 및 그룹 설정을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="f36b1-154">Change team and group settings.</span></span>
 
![예제 팀 프로필 스크린샷](media/manage-teams-in-modern-portal-team-profile-page.png)

## <a name="making-changes-to-teams"></a><span data-ttu-id="f36b1-156">팀 변경</span><span class="sxs-lookup"><span data-stu-id="f36b1-156">Making changes to teams</span></span>

<span data-ttu-id="f36b1-157">팀의 프로필 페이지에서 팀의 다음 요소를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f36b1-157">On the team's profile page, you can change the following elements of a team:</span></span>

- <span data-ttu-id="f36b1-158">**멤버** - 구성원을 추가하거나 제거하고 소유자를 승격하거나 강하합니다.</span><span class="sxs-lookup"><span data-stu-id="f36b1-158">**Members** - add or remove members and promote or demote owners.</span></span>
- <span data-ttu-id="f36b1-159">**채널** - 새 채널을 추가하고 기존 채널을 편집하거나 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f36b1-159">**Channels** - add new channels, and edit or remove existing channels.</span></span> <span data-ttu-id="f36b1-160">기본 일반 채널은 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f36b1-160">Remember that you can't delete the default General channel.</span></span>
- <span data-ttu-id="f36b1-161">**팀 이름**</span><span class="sxs-lookup"><span data-stu-id="f36b1-161">**Team name**</span></span>
- <span data-ttu-id="f36b1-162">**설명**</span><span class="sxs-lookup"><span data-stu-id="f36b1-162">**Description**</span></span>
- <span data-ttu-id="f36b1-163">**개인 정보** - 팀이 공용인지 비공개인지 여부를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f36b1-163">**Privacy** - set whether the team is public or private.</span></span>
- <span data-ttu-id="f36b1-164">**분류** - Microsoft 365 그룹 분류에 의해 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="f36b1-164">**Classification** - this is backed by your Microsoft 365 group classifications.</span></span> <span data-ttu-id="f36b1-165">**기밀,** **기밀성,** 일반 을 **선택하십시오.**</span><span class="sxs-lookup"><span data-stu-id="f36b1-165">Choose **Confidential**, **Highly Confidential**, or **General**.</span></span>
- <span data-ttu-id="f36b1-166">**대화 설정** - 구성원이 보낸 메시지를 편집하고 삭제할 수 있는지 여부를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f36b1-166">**Conversations settings** - set whether members can edit and delete sent messages.</span></span>
- <span data-ttu-id="f36b1-167">**채널 설정** - 구성원이 새 채널을 만들고 기존 채널을 편집할 수 있는지 여부를 설정하고 탭, 커넥터 및 앱을 추가, 편집 및 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f36b1-167">**Channels settings** - set whether members can create new channels and edit existing ones, and add, edit, and remove tabs, connectors, and apps.</span></span>

<span data-ttu-id="f36b1-168">팀에 대한 변경 내용이 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="f36b1-168">The changes that you make to a team are logged.</span></span> <span data-ttu-id="f36b1-169">그룹 설정을 수정하는 경우(이름, 설명, 사진, 개인 정보, 분류 또는 팀 구성원 변경) 변경 내용은 감사 파이프라인을 통해 사용자에 기인합니다.</span><span class="sxs-lookup"><span data-stu-id="f36b1-169">If you're modifying group settings (changing the name, description, photo, privacy, classification, or team members), the changes are attributed to you through the audit pipeline.</span></span> <span data-ttu-id="f36b1-170">Teams별 설정에 대해 작업을 수행하는 경우 변경 내용을 추적하고 팀의 일반 채널에서 사용자에 기인합니다.</span><span class="sxs-lookup"><span data-stu-id="f36b1-170">If you're performing actions against Teams-specific settings, your changes are tracked and attributed to you in the General channel of the team.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="f36b1-171">문제 해결</span><span class="sxs-lookup"><span data-stu-id="f36b1-171">Troubleshooting</span></span>

<span data-ttu-id="f36b1-172">**문제: 팀 개요 눈금에서 팀이 누락된 경우**</span><span class="sxs-lookup"><span data-stu-id="f36b1-172">**Issue: Teams missing from the Team overview grid**</span></span>

<span data-ttu-id="f36b1-173">일부 팀은 Teams 개요 눈금의 팀 목록에서 누락됩니다.</span><span class="sxs-lookup"><span data-stu-id="f36b1-173">Some of your teams are missing from the list of teams in the Teams overview grid.</span></span>

<span data-ttu-id="f36b1-174">**원인**: 팀이 시스템에 의해 프로파일링되지 않았거나 아직 프로필이 없는 경우 이 문제가 발생하여 인식할 속성이 누락될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f36b1-174">**Cause**: This issue occurs when the team was incorrectly (or not yet) profiled by the system which can lead to a missing property for it to be recognized.</span></span>

<span data-ttu-id="f36b1-175">**해결: MS Graph를 통해 속성을 올바른 값으로 수동으로 설정**</span><span class="sxs-lookup"><span data-stu-id="f36b1-175">**Resolution: Manually set the property to the correct value via MS Graph**</span></span>

<span data-ttu-id="f36b1-176">Exchange Online powershell을 통해 얻을 수 있는 문제의 쿼리에서 **{groupid}를** **"ExternalDirectoryObjectId"** 특성으로 "Get-UnifiedGroup" cmdlet으로 바 대체합니다. **[](/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)**</span><span class="sxs-lookup"><span data-stu-id="f36b1-176">Replace **{groupid}** in the Query for the actual GroupId in question, which you can get via the Exchange Online powershell, with the **"[Get-UnifiedGroup](/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** cmdlet, as the "**ExternalDirectoryObjectId**" attribute.</span></span>

1. <span data-ttu-id="f36b1-177">Access [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer)입니다.</span><span class="sxs-lookup"><span data-stu-id="f36b1-177">Access [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

2. <span data-ttu-id="f36b1-178">왼쪽 메뉴에서 Graph Explorer에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="f36b1-178">Sign in to Graph Explorer on the left menu.</span></span>

3. <span data-ttu-id="f36b1-179">쿼리 줄을 : 패치 > v1.0 https://graph.microsoft.com/v1.0/groups/{groupid} >.</span><span class="sxs-lookup"><span data-stu-id="f36b1-179">Change the query line to: PATCH > v1.0 > https://graph.microsoft.com/v1.0/groups/{groupid}.</span></span>

4. <span data-ttu-id="f36b1-180">요청 본문에 {"resourceProvisioningOptions": ["Team"]}을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f36b1-180">Add the following value on the request body: {"resourceProvisioningOptions": ["Team"]}.</span></span>

5. <span data-ttu-id="f36b1-181">오른쪽 위에서 쿼리를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f36b1-181">Run the query on the top-right.</span></span>

6. <span data-ttu-id="f36b1-182">Microsoft Teams 관리 센터 - 팀 개요에 팀이 올바르게 나타나는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f36b1-182">Confirm the team appears correctly in the Microsoft Teams admin center - Team Overview.</span></span>

## <a name="learn-more"></a><span data-ttu-id="f36b1-183">자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="f36b1-183">Learn more</span></span>

- [<span data-ttu-id="f36b1-184">Teams cmdlet 참조</span><span class="sxs-lookup"><span data-stu-id="f36b1-184">Teams cmdlet reference</span></span>](/powershell/teams/?view=teams-ps)  
- [<span data-ttu-id="f36b1-185">Teams 관리자 역할을 사용하여 Teams 관리</span><span class="sxs-lookup"><span data-stu-id="f36b1-185">Use Teams administrator roles to manage Teams</span></span>](using-admin-roles.md)
- [<span data-ttu-id="f36b1-186">Teams에서 수명 주기 관리 계획</span><span class="sxs-lookup"><span data-stu-id="f36b1-186">Plan for lifecycle management in Teams</span></span>](plan-teams-lifecycle.md)