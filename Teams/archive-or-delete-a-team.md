---
title: Microsoft Teams에서 팀 보관 또는 삭제하기
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: jastark
search.appverid: MET150
description: 이 문서에서는 Microsoft Teams에서 팀을 보관하거나 영구적으로 삭제하는 방법에 대해 알아보고 있습니다.
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
ms.openlocfilehash: da2d330986ca2fd924df75e0fcae6fc4388c5d48
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120840"
---
<a name="archive-or-delete-a-team-in-microsoft-teams"></a><span data-ttu-id="faf30-103">Microsoft Teams에서 팀 보관 또는 삭제하기</span><span class="sxs-lookup"><span data-stu-id="faf30-103">Archive or delete a team in Microsoft Teams</span></span>
===========================================

<span data-ttu-id="faf30-104">시간이 지남에 따라 Microsoft Teams에서 만든 팀이 사용되지 않거나 프로젝트가 끝날 때 팀을 보관하거나 삭제하려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faf30-104">Over time, a team created in Microsoft Teams might fall out of use or you might want to archive or delete a team at the end of a project.</span></span> <span data-ttu-id="faf30-105">Microsoft Teams 관리자인 경우 이 문서에 나와 있는 단계를 따라 더 이상 필요하지 않은 팀을 보관하거나 삭제하세요.</span><span class="sxs-lookup"><span data-stu-id="faf30-105">If you're a Microsoft Teams admin, follow the steps in this article to archive or delete a team that's no longer needed.</span></span>

<span data-ttu-id="faf30-106">팀을 보관하면 해당 팀에 대한 모든 활동이 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="faf30-106">When you archive a team, all activity for that team ceases.</span></span> <span data-ttu-id="faf30-107">팀을 보관하면 팀의 개인 채널과 연결된 사이트 모음도 보관됩니다.</span><span class="sxs-lookup"><span data-stu-id="faf30-107">Archiving a team also archives private channels in the team and their associated site collections.</span></span>  <span data-ttu-id="faf30-108">그러나 관리자가 계속해서 구성원을 추가 또는 제거하고 역할을 업데이트할 수 있으며, 표준 및 개인 채널, 파일 및 채팅에서 모든 팀 활동을 계속 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faf30-108">However, you can still add or remove members and update roles and you can still view all the team activity in standard and private channels, files, and chats.</span></span>

<span data-ttu-id="faf30-109">팀을 삭제하면 표준 및 개인 채널(및 연결된 사이트 모음)에서 팀 활동, 파일 및 채팅도 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="faf30-109">When you delete a team, team activity in standard and private channels (and associated site collections), files, and chats is also deleted.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="faf30-110">보관된 팀은 다시 활성화될 수 있지만 삭제된 팀은 직접 복원할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="faf30-110">Archived teams can be reactivated, but you can’t directly restore a team that has been deleted.</span></span> <span data-ttu-id="faf30-111">먼저 팀을 보관하고 팀이 더 이상 필요하지 않을 때까지 삭제를 연기하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="faf30-111">Consider archiving the team first, and postpone the deletion until you're sure that you no longer need the team.</span></span>

## <a name="archive-a-team"></a><span data-ttu-id="faf30-112">팀 보관하기</span><span class="sxs-lookup"><span data-stu-id="faf30-112">Archive a team</span></span>

<span data-ttu-id="faf30-113">팀을 보관하려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="faf30-113">Follow these steps to archive a team.</span></span> <span data-ttu-id="faf30-114">이러한 정책을 관리하려면 전역 관리자 또는 Teams 서비스 관리자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="faf30-114">You must be a Teams service admin to make these changes.</span></span> <span data-ttu-id="faf30-115">관리 역할 및 사용 권한 가져오기에 대한 내용은 [Teams 관리자 역할 사용](./using-admin-roles.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="faf30-115">See [Use Teams administrator roles to manage Teams](./using-admin-roles.md) to read about getting admin roles and permissions.</span></span>

1. <span data-ttu-id="faf30-116">관리 센터에서 **Teams 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="faf30-116">In the admin center, select **Teams**.</span></span>
2. <span data-ttu-id="faf30-117">팀 이름을 클릭하여 팀을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="faf30-117">Select a team by clicking the team name.</span></span>
3. <span data-ttu-id="faf30-118">**보관** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="faf30-118">Select **Archive**.</span></span> <span data-ttu-id="faf30-119">다음 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="faf30-119">The following message will appear.</span></span>

    ![Teams 보관 메시지 스크린샷](media/teams-archive-message.png)

4. <span data-ttu-id="faf30-121">팀과 연결된 SharePoint 사이트 및 위키 탭에서 콘텐츠를 편집하지 못하게하려면 팀 구성원에 대해 SharePoint 사이트 읽기 **전용으로 만들기를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="faf30-121">To prevent people from editing the content in the SharePoint site and Wiki tab associated with the team, select **Make the SharePoint site read-only for team members**.</span></span> <span data-ttu-id="faf30-122">(Teams 소유자는 여전히 이 콘텐츠를 편집할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="faf30-122">(Teams owners will still be able to edit this content.)</span></span>
5. <span data-ttu-id="faf30-123">**보관** 을 선택하여 팀을 보관합니다.</span><span class="sxs-lookup"><span data-stu-id="faf30-123">Select **Archive** to archive the team.</span></span> <span data-ttu-id="faf30-124">팀의 상태가 **보관됨** 으로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="faf30-124">The team’s status will change to **Archived**.</span></span>

## <a name="make-an-archived-team-active"></a><span data-ttu-id="faf30-125">보관된 팀을 활성화하기</span><span class="sxs-lookup"><span data-stu-id="faf30-125">Make an archived team active</span></span>

<span data-ttu-id="faf30-126">보관된 팀을 다시 활성화하려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="faf30-126">Follow these steps to make an archived team active again.</span></span>

1. <span data-ttu-id="faf30-127">관리 센터에서 **Teams 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="faf30-127">In the admin center, select **Teams**.</span></span>
2. <span data-ttu-id="faf30-128">팀 이름을 클릭하여 팀을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="faf30-128">Select a team by clicking the team name.</span></span>
3. <span data-ttu-id="faf30-129">**보관 취소** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="faf30-129">Select **Unarchive**.</span></span> <span data-ttu-id="faf30-130">팀의 상태가 **활성** 으로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="faf30-130">The team’s status will change to **Active**.</span></span>

## <a name="delete-a-team"></a><span data-ttu-id="faf30-131">팀 삭제하기</span><span class="sxs-lookup"><span data-stu-id="faf30-131">Delete a team</span></span>

<span data-ttu-id="faf30-132">나중에 팀이 필요하지 않은 경우에는 팀을 보관하지 않고 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faf30-132">If the team will not be required in the future, then you can delete it rather than archiving it.</span></span> <span data-ttu-id="faf30-133">팀을 삭제하려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="faf30-133">Follow these steps to delete a team.</span></span>

1.  <span data-ttu-id="faf30-134">관리 센터에서 **Teams 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="faf30-134">In the admin center, select **Teams**.</span></span>
2.  <span data-ttu-id="faf30-135">팀 이름을 클릭하여 팀을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="faf30-135">Select a team by clicking the team name.</span></span>
3.  <span data-ttu-id="faf30-136">**삭제** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="faf30-136">Select **Delete**.</span></span> <span data-ttu-id="faf30-137">확인 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="faf30-137">A confirmation message will appear.</span></span>
4.  <span data-ttu-id="faf30-138">팀을 영구적으로 삭제하려면 **삭제** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="faf30-138">Select **Delete** to permanently delete the team.</span></span>

## <a name="restore-a-deleted-team"></a><span data-ttu-id="faf30-139">삭제된 작업 복원하기</span><span class="sxs-lookup"><span data-stu-id="faf30-139">Restore a deleted team</span></span>

<span data-ttu-id="faf30-140">다음 단계를 수행하여 팀과 연결된 Microsoft 365 그룹을 복원하여 삭제된 팀을 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="faf30-140">Follow these steps to restore a deleted team by restoring the Microsoft 365 group that's associated with the team.</span></span> <span data-ttu-id="faf30-141">팀에 대한 Microsoft 365 그룹을 복원하면 탭, 표준 채널 및 개인 채널 및 관련 사이트 모음을 비롯한 팀 콘텐츠가 복원됩니다.</span><span class="sxs-lookup"><span data-stu-id="faf30-141">Restoring the Microsoft 365 group for a team restores team content, including tabs, standard channels, and private channels and their associated site collections.</span></span>

<span data-ttu-id="faf30-142">기본적으로 삭제된 Microsoft 365 그룹은 30일 동안 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="faf30-142">By default, a deleted Microsoft 365 group is retained for 30 days.</span></span> <span data-ttu-id="faf30-143">이 30일의 기간을 “일시 삭제”라고 하며 이 기간 동안 그룹을 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faf30-143">This 30-day period is called "soft-delete" because you can restore the group.</span></span> <span data-ttu-id="faf30-144">자세한 내용은 삭제된 [그룹 복원을 참조합니다.](/microsoft-365/admin/create-groups/restore-deleted-group)</span><span class="sxs-lookup"><span data-stu-id="faf30-144">To learn more, see [Restore a deleted Group](/microsoft-365/admin/create-groups/restore-deleted-group).</span></span>

### <a name="install-the-azureadpreview-module"></a><span data-ttu-id="faf30-145">AzureADPreview 모듈 설치하기</span><span class="sxs-lookup"><span data-stu-id="faf30-145">Install the AzureADPreview module</span></span>

1. <span data-ttu-id="faf30-146">관리자 권한으로 Windows PowerShell을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="faf30-146">Open Windows PowerShell as an admin.</span></span>
2. <span data-ttu-id="faf30-147">이전 버전의 AzureADPreview 모듈 또는 AzureAD module이 설치되어 있는 경우 다음 중 하나를 실행하여 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="faf30-147">If you have an earlier version of the AzureADPreview module installed or the AzureAD module installed, uninstall it by running one of the following:</span></span>

    ```PowerShell
    Uninstall-Module AzureADPreview
    ```

    ```PowerShell
    Uninstall-Module AzureAD
    ```
3. <span data-ttu-id="faf30-148">다음을 실행하여 최신 버전의 AzureADPreview 모듈을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="faf30-148">Install the latest version of the AzureADPreview module by running the following:</span></span>

    ```PowerShell
    Install-Module AzureADPreview
    ```

### <a name="restore-the-deleted-microsoft-365-group"></a><span data-ttu-id="faf30-149">삭제된 Microsoft 365 그룹 복원</span><span class="sxs-lookup"><span data-stu-id="faf30-149">Restore the deleted Microsoft 365 group</span></span>

1. <span data-ttu-id="faf30-150">다음을 실행하여 Azure AD에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="faf30-150">Connect to Azure AD by running the following:</span></span>
    ```PowerShell
    Connect-AzureAD
    ```
    <span data-ttu-id="faf30-151">메시지가 표시되면 관리자 계정 및 암호를 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="faf30-151">When you're prompted, sign in using your admin account and password.</span></span>  
2. <span data-ttu-id="faf30-152">다음을 실행하여 30일 보존 기간 내에 있는 모든 소프트 삭제된 Microsoft 365 그룹 목록을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="faf30-152">Run the following to display a list of all soft-deleted Microsoft 365 groups that are still within the 30-day retention period.</span></span> <span data-ttu-id="faf30-153">그룹이 많이 있는 경우 **-All $True** 매개 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="faf30-153">Use the **-All $True** parameter if you have a lot of groups.</span></span>
    ```PowerShell
    Get-AzureADMSDeletedGroup
    ```
3. <span data-ttu-id="faf30-154">복원하려는 그룹을 찾은 다음 해당 Id를 기록해 둡니다.</span><span class="sxs-lookup"><span data-stu-id="faf30-154">Find the group that you want to restore, and then make a note of the Id.</span></span>
4. <span data-ttu-id="faf30-155">다음을 실행하여 해당 그룹을 복원합니다. 여기서 [Id]는 그룹 Id입니다.</span><span class="sxs-lookup"><span data-stu-id="faf30-155">Run the following to restore the group, where [Id] is the group Id.</span></span>
    ```PowerShell
    Restore-AzureADMSDeletedDirectoryObject -Id [Id]
    ```
5.  <span data-ttu-id="faf30-156">다음을 실행하여 그룹이 성공적으로 복원되었는지 확인합니다. 여기서 [Id]는 그룹 Id입니다.</span><span class="sxs-lookup"><span data-stu-id="faf30-156">Run the following to verify the group was successfully restored, where [Id] is the group Id.</span></span>
    ```PowerShell
    Get-AzureADGroup -ObjectId [Id]
    ```

    <span data-ttu-id="faf30-157">복원 프로세스가 완료되는 데 최대 24시간이 걸릴 수 있으며, 복원된 후에는 팀과 탭과 채널을 포함하는 팀과 연결된 콘텐츠가 팀에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="faf30-157">It can take up to 24 hours for the restore process to complete, after which the team and content associated with the team, including tabs and channels, is displayed in Teams.</span></span>