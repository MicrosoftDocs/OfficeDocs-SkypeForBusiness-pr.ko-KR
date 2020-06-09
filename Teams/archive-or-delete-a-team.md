---
title: Microsoft Teams에서 팀 보관 또는 삭제하기
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: jastark
search.appverid: MET150
description: 이 문서에서는 Microsoft 팀에서 팀을 보관 하거나 영구적으로 삭제 하는 방법에 대해 설명 합니다.
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
ms.openlocfilehash: 907138205d4d5e7be1933f00f0a7ace0340d858f
ms.sourcegitcommit: fa567451f8f7af6d915e33809d88f26b415db54c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "44611007"
---
<a name="archive-or-delete-a-team-in-microsoft-teams"></a><span data-ttu-id="4ebe7-103">Microsoft Teams에서 팀 보관 또는 삭제하기</span><span class="sxs-lookup"><span data-stu-id="4ebe7-103">Archive or delete a team in Microsoft Teams</span></span>
===========================================

<span data-ttu-id="4ebe7-104">시간이 지남에 따라 Microsoft Teams에서 만든 팀이 사용되지 않거나 프로젝트가 끝날 때 팀을 보관하거나 삭제하려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ebe7-104">Over time, a team created in Microsoft Teams might fall out of use or you might want to archive or delete a team at the end of a project.</span></span> <span data-ttu-id="4ebe7-105">Microsoft Teams 관리자인 경우 이 문서에 나와 있는 단계를 따라 더 이상 필요하지 않은 팀을 보관하거나 삭제하세요.</span><span class="sxs-lookup"><span data-stu-id="4ebe7-105">If you're a Microsoft Teams admin, follow the steps in this article to archive or delete a team that's no longer needed.</span></span>

<span data-ttu-id="4ebe7-106">팀을 보관하면 해당 팀에 대한 모든 활동이 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ebe7-106">When you archive a team, all activity for that team ceases.</span></span> <span data-ttu-id="4ebe7-107">팀을 보관하면 팀의 개인 채널과 연결된 사이트 모음도 보관됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ebe7-107">Archiving a team also archives private channels in the team and their associated site collections.</span></span>  <span data-ttu-id="4ebe7-108">그러나 관리자가 계속해서 구성원을 추가 또는 제거하고 역할을 업데이트할 수 있으며, 표준 및 개인 채널, 파일 및 채팅에서 모든 팀 활동을 계속 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ebe7-108">However, you can still add or remove members and update roles and you can still view all the team activity in standard and private channels, files, and chats.</span></span>

<span data-ttu-id="4ebe7-109">팀을 삭제하면 표준 및 개인 채널(및 연결된 사이트 모음)에서 팀 활동, 파일 및 채팅도 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ebe7-109">When you delete a team, team activity in standard and private channels (and associated site collections), files, and chats is also deleted.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4ebe7-110">보관된 팀은 다시 활성화될 수 있지만 삭제된 팀은 직접 복원할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4ebe7-110">Archived teams can be reactivated, but you can’t directly restore a team that has been deleted.</span></span> <span data-ttu-id="4ebe7-111">먼저 팀을 보관하고 팀이 더 이상 필요하지 않을 때까지 삭제를 연기하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4ebe7-111">Consider archiving the team first, and postpone the deletion until you're sure that you no longer need the team.</span></span>

## <a name="archive-a-team"></a><span data-ttu-id="4ebe7-112">팀 보관하기</span><span class="sxs-lookup"><span data-stu-id="4ebe7-112">Archive a team</span></span>

<span data-ttu-id="4ebe7-113">팀을 보관하려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="4ebe7-113">Follow these steps to archive a team.</span></span>

1. <span data-ttu-id="4ebe7-114">관리 센터에서 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> **팀**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ebe7-114">In the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>, select **Teams**.</span></span>
2. <span data-ttu-id="4ebe7-115">팀 이름을 클릭하여 팀을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4ebe7-115">Select a team by clicking the team name.</span></span>
3. <span data-ttu-id="4ebe7-116">**보관**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4ebe7-116">Select **Archive**.</span></span> <span data-ttu-id="4ebe7-117">다음 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ebe7-117">The following message will appear.</span></span>

    ![Teams 보관 메시지 스크린샷](media/teams-archive-message.png)

4. <span data-ttu-id="4ebe7-119">팀의 SharePoint 사이트를 읽기 전용으로 설정하려면 해당 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4ebe7-119">If you would like to make the SharePoint site for the team read-only, select the check box.</span></span>
5. <span data-ttu-id="4ebe7-120">**보관**을 선택하여 팀을 보관합니다.</span><span class="sxs-lookup"><span data-stu-id="4ebe7-120">Select **Archive** to archive the team.</span></span> <span data-ttu-id="4ebe7-121">팀의 상태가 **보관됨**으로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ebe7-121">The team’s status will change to **Archived**.</span></span>

## <a name="make-an-archived-team-active"></a><span data-ttu-id="4ebe7-122">보관된 팀을 활성화하기</span><span class="sxs-lookup"><span data-stu-id="4ebe7-122">Make an archived team active</span></span>

<span data-ttu-id="4ebe7-123">보관된 팀을 다시 활성화하려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="4ebe7-123">Follow these steps to make an archived team active again.</span></span>

1. <span data-ttu-id="4ebe7-124"><a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">관리 센터</a>에서 **팀**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ebe7-124">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>, select **Teams**.</span></span>
2. <span data-ttu-id="4ebe7-125">팀 이름을 클릭하여 팀을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4ebe7-125">Select a team by clicking the team name.</span></span>
3. <span data-ttu-id="4ebe7-126">**보관 취소**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4ebe7-126">Select **Unarchive**.</span></span> <span data-ttu-id="4ebe7-127">팀의 상태가 **활성**으로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ebe7-127">The team’s status will change to **Active**.</span></span>

## <a name="delete-a-team"></a><span data-ttu-id="4ebe7-128">팀 삭제하기</span><span class="sxs-lookup"><span data-stu-id="4ebe7-128">Delete a team</span></span>

<span data-ttu-id="4ebe7-129">나중에 팀이 필요하지 않은 경우에는 팀을 보관하지 않고 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ebe7-129">If the team will not be required in the future, then you can delete it rather than archiving it.</span></span> <span data-ttu-id="4ebe7-130">팀을 삭제하려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="4ebe7-130">Follow these steps to delete a team.</span></span>

1.  <span data-ttu-id="4ebe7-131"><a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">관리 센터</a>에서 **팀**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ebe7-131">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>, select **Teams**.</span></span>
2.  <span data-ttu-id="4ebe7-132">팀 이름을 클릭하여 팀을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4ebe7-132">Select a team by clicking the team name.</span></span>
3.  <span data-ttu-id="4ebe7-133">**삭제**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4ebe7-133">Select **Delete**.</span></span> <span data-ttu-id="4ebe7-134">확인 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ebe7-134">A confirmation message will appear.</span></span>
4.  <span data-ttu-id="4ebe7-135">팀을 영구적으로 삭제하려면 **삭제**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4ebe7-135">Select **Delete** to permanently delete the team.</span></span>

## <a name="restore-a-deleted-team"></a><span data-ttu-id="4ebe7-136">삭제된 작업 복원하기</span><span class="sxs-lookup"><span data-stu-id="4ebe7-136">Restore a deleted team</span></span>

<span data-ttu-id="4ebe7-137">팀과 연결 된 Microsoft 365 그룹을 복원 하 여 삭제 된 팀을 복원 하려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="4ebe7-137">Follow these steps to restore a deleted team by restoring the Microsoft 365 group that's associated with the team.</span></span> <span data-ttu-id="4ebe7-138">팀에 대 한 Microsoft 365 그룹을 복원 하면 탭, 표준 채널, 개인 채널 및 연결 된 사이트 모음을 비롯 한 팀 콘텐츠가 복원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ebe7-138">Restoring the Microsoft 365 group for a team restores team content, including tabs, standard channels, and private channels and their associated site collections.</span></span>

<span data-ttu-id="4ebe7-139">기본적으로 삭제 된 Microsoft 365 그룹은 30 일 동안 보존 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ebe7-139">By default, a deleted Microsoft 365 group is retained for 30 days.</span></span> <span data-ttu-id="4ebe7-140">이 30일의 기간을 “일시 삭제”라고 하며 이 기간 동안 그룹을 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ebe7-140">This 30-day period is called "soft-delete" because you can restore the group.</span></span> <span data-ttu-id="4ebe7-141">자세히 알아보려면 [삭제 된 Microsoft 365 그룹 복원을](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4ebe7-141">To learn more, see [Restore a deleted Microsoft 365 Group](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group).</span></span>

### <a name="install-the-azureadpreview-module"></a><span data-ttu-id="4ebe7-142">AzureADPreview 모듈 설치하기</span><span class="sxs-lookup"><span data-stu-id="4ebe7-142">Install the AzureADPreview module</span></span>

1. <span data-ttu-id="4ebe7-143">관리자 권한으로 Windows PowerShell을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4ebe7-143">Open Windows PowerShell as an admin.</span></span>
2. <span data-ttu-id="4ebe7-144">이전 버전의 AzureADPreview 모듈 또는 AzureAD module이 설치되어 있는 경우 다음 중 하나를 실행하여 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="4ebe7-144">If you have an earlier version of the AzureADPreview module installed or the AzureAD module installed, uninstall it by running one of the following:</span></span>

    ```PowerShell 
    Uninstall-Module AzureADPreview
    ```

    ```PowerShell
    Uninstall-Module AzureAD
    ```
3. <span data-ttu-id="4ebe7-145">다음을 실행하여 최신 버전의 AzureADPreview 모듈을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="4ebe7-145">Install the latest version of the AzureADPreview module by running the following:</span></span>

    ```PowerShell
    Install-Module AzureADPreview
    ```    

### <a name="restore-the-deleted-microsoft-365-group"></a><span data-ttu-id="4ebe7-146">삭제 된 Microsoft 365 그룹 복원</span><span class="sxs-lookup"><span data-stu-id="4ebe7-146">Restore the deleted Microsoft 365 group</span></span>

1. <span data-ttu-id="4ebe7-147">다음을 실행하여 Azure AD에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="4ebe7-147">Connect to Azure AD by running the following:</span></span>
    ```PowerShell
    Connect-AzureAD
    ```
    <span data-ttu-id="4ebe7-148">메시지가 표시되면 관리자 계정 및 암호를 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="4ebe7-148">When you're prompted, sign in using your admin account and password.</span></span>  
2. <span data-ttu-id="4ebe7-149">다음을 실행 하 여 30 일 보존 기간 내에 있는 모든 일시 삭제 된 Microsoft 365 그룹의 목록을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ebe7-149">Run the following to display a list of all soft-deleted Microsoft 365 groups that are still within the 30-day retention period.</span></span> <span data-ttu-id="4ebe7-150">그룹이 많이 있는 경우 **-All $True** 매개 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4ebe7-150">Use the **-All $True** parameter if you have a lot of groups.</span></span>
    ```PowerShell
    Get-AzureADMSDeletedGroup
    ``` 
3. <span data-ttu-id="4ebe7-151">복원하려는 그룹을 찾은 다음 해당 Id를 기록해 둡니다.</span><span class="sxs-lookup"><span data-stu-id="4ebe7-151">Find the group that you want to restore, and then make a note of the Id.</span></span>
4. <span data-ttu-id="4ebe7-152">다음을 실행하여 해당 그룹을 복원합니다. 여기서 [Id]는 그룹 Id입니다.</span><span class="sxs-lookup"><span data-stu-id="4ebe7-152">Run the following to restore the group, where [Id] is the group Id.</span></span>
    ```PowerShell
    Restore-AzureADMSDeletedDirectoryObject -Id [Id]
    ```
5.  <span data-ttu-id="4ebe7-153">다음을 실행하여 그룹이 성공적으로 복원되었는지 확인합니다. 여기서 [Id]는 그룹 Id입니다.</span><span class="sxs-lookup"><span data-stu-id="4ebe7-153">Run the following to verify the group was successfully restored, where [Id] is the group Id.</span></span>
    ```PowerShell
    Get-AzureADGroup -ObjectId [Id]
    ```

    <span data-ttu-id="4ebe7-154">복원 프로세스가 완료되는 데 최대 24시간이 걸릴 수 있으며, 복원된 후에는 팀과 탭과 채널을 포함하는 팀과 연결된 콘텐츠가 팀에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ebe7-154">It can take up to 24 hours for the restore process to complete, after which the team and content associated with the team, including tabs and channels, is displayed in Teams.</span></span>
