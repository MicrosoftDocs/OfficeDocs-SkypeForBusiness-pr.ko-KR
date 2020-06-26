---
title: Microsoft 팀에서 팀 정책 관리
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 조직에서 팀 정책을 사용 하 고 관리 하 여 팀과 채널에서 사용자가 수행할 수 있는 작업을 제어 하는 방법에 대해 알아봅니다.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discoverteams
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.createchannels
- ms.teamsadmincenter.teams.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discover
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.create
ms.openlocfilehash: b28b61a6b2d4c441fc69d0e50124df50f95b4a49
ms.sourcegitcommit: 2e8a61abdd586bf8f0f88cac3b7d4ca4b9d9be34
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2020
ms.locfileid: "44889977"
---
# <a name="manage-teams-policies-in-microsoft-teams"></a><span data-ttu-id="1216d-103">Microsoft 팀에서 팀 정책 관리</span><span class="sxs-lookup"><span data-stu-id="1216d-103">Manage teams policies in Microsoft Teams</span></span>

<span data-ttu-id="1216d-104">관리자는 Microsoft 팀에서 팀 정책을 사용 하 여 팀과 채널에서 조직의 사용자가 수행할 수 있는 작업을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1216d-104">As an admin, you can use teams policies in Microsoft Teams to control what users in your organization can do in teams and channels.</span></span> <span data-ttu-id="1216d-105">예를 들어 사용자가 검색 결과 및 팀 갤러리에서 비공개 팀을 검색 하도록 허용할지 여부와 사용자가 개인 채널을 만들 수 있도록 허용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1216d-105">For example, you can set whether users are allowed to discover private teams in search results and in the team gallery and whether users are allowed to create private channels.</span></span>

<span data-ttu-id="1216d-106">**Teams**  >  Microsoft 팀 관리 센터에서 팀**팀 정책** 으로 이동해 서 팀 정책을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1216d-106">You manage teams policies by going to **Teams** > **Teams policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="1216d-107">전역(조직 전체 기본값) 정책을 사용하거나 사용자 지정 정책을 만들어 사용자에게 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1216d-107">You can use the global (Org-wide default) policy or create custom policies and assign them to users.</span></span> <span data-ttu-id="1216d-108">사용자 지정 정책을 만들고 할당하지 않으면 조직의 사용자에게 전역 정책이 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1216d-108">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

<span data-ttu-id="1216d-109">전역 정책을 편집 하거나 사용자 지정 정책을 만들고 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1216d-109">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="1216d-110">사용자가 사용자 지정 정책을 할당 한 경우 해당 정책이 사용자에 게 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1216d-110">If a user is assigned a custom policy, that policy applies to the user.</span></span> <span data-ttu-id="1216d-111">사용자가 사용자 지정 정책을 할당 하지 않으면 전역 정책이 사용자에 게 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1216d-111">If a user isn't assigned a custom policy, the global policy applies to the user.</span></span> <span data-ttu-id="1216d-112">전역 정책을 편집 하거나 정책을 할당 한 후 변경 내용을 적용 하는 데 몇 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1216d-112">After you edit the global policy or assign a policy, it can take a few hours for changes to take effect.</span></span>

## <a name="create-a-custom-teams-policy"></a><span data-ttu-id="1216d-113">사용자 지정 팀 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="1216d-113">Create a custom teams policy</span></span>

1. <span data-ttu-id="1216d-114">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **팀**  >  **팀 정책**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="1216d-114">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="1216d-115">**추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1216d-115">Click **Add**.</span></span>
3. <span data-ttu-id="1216d-116">정책의 이름과 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="1216d-116">Enter a name and description for the policy.</span></span>

    ![팀 정책 설정 스크린샷](media/teams-policies.png)
4. <span data-ttu-id="1216d-118">원하는 설정을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1216d-118">Choose the settings that you want:</span></span>

- <span data-ttu-id="1216d-119">**비공개 팀 검색** (비공개 미리 보기):<a name="discoverteams"> </a> 사용자가 검색 결과 및 팀 갤러리에서 비공개 팀을 검색할 수 있도록 하려면이 설정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1216d-119">**Discover private teams** (in private preview):<a name="discoverteams"> </a> Turn on this setting to allow users to discover private teams in search results and in the team gallery.</span></span>
- <span data-ttu-id="1216d-120">**개인 채널 만들기**: <a name="createchannels"> </a>이 설정을 사용 하면 사용자가 개인 채널을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1216d-120">**Create private channels**: <a name="createchannels"> </a>Turn on this setting to allow users to create private channels.</span></span>

5. <span data-ttu-id="1216d-121">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1216d-121">Click **Save**.</span></span>

## <a name="edit-a-teams-policy"></a><span data-ttu-id="1216d-122">팀 정책 편집</span><span class="sxs-lookup"><span data-stu-id="1216d-122">Edit a teams policy</span></span>

<span data-ttu-id="1216d-123">만든 전역 정책 또는 사용자 지정 정책을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1216d-123">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="1216d-124">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **팀**  >  **팀 정책**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="1216d-124">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="1216d-125">정책 이름 왼쪽을 클릭 하 여 정책을 선택한 다음 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1216d-125">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="1216d-126">원하는 설정을 켜거나 끈 다음 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1216d-126">Turn on or turn off the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-teams-policy-to-users"></a><span data-ttu-id="1216d-127">사용자에 게 사용자 지정 팀 정책 할당</span><span class="sxs-lookup"><span data-stu-id="1216d-127">Assign a custom teams policy to users</span></span>

<span data-ttu-id="1216d-128">Microsoft 팀 관리 센터를 사용 하 여 한 명 이상의 사용자 또는 비즈니스용 Skype PowerShell 모듈에 사용자 지정 정책을 할당 하 여 보안 그룹 또는 메일 그룹과 같은 사용자 그룹에 사용자 지정 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1216d-128">You can use the Microsoft Teams admin center to assign a custom policy to one or more users or the Skype for Business PowerShell module to assign a custom policy to groups of users, such as a security group or distribution group.</span></span>

### <a name="assign-a-custom-teams-policy-to-users"></a><span data-ttu-id="1216d-129">사용자에 게 사용자 지정 팀 정책 할당</span><span class="sxs-lookup"><span data-stu-id="1216d-129">Assign a custom teams policy to users</span></span>

<span data-ttu-id="1216d-130">한 사용자에 게 정책을 할당 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1216d-130">To assign a policy to one user:</span></span>

1. <span data-ttu-id="1216d-131">Microsoft Teams 관리 센터의 왼쪽 탐색 창에서 **사용자**로 이동한 후 해당 사용자를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1216d-131">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="1216d-132">**정책을**클릭 한 다음 **할당 된 정책**옆에 있는 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1216d-132">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="1216d-133">**팀 정책**에서 할당 하려는 정책을 선택한 다음 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1216d-133">Under **Teams policies**, select the policy you want to assign, and then click **Save**.</span></span>

<span data-ttu-id="1216d-134">한 번에 여러 사용자에게 정책을 할당하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="1216d-134">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="1216d-135">Microsoft Teams 관리 센터의 왼쪽 탐색에서 **사용자**로 이동한 다음, 사용자를 검색하거나 보기를 필터링하여 원하는 사용자를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="1216d-135">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="1216d-136">**&#x2713;**(확인 표시) 열에서 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1216d-136">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="1216d-137">모든 사용자를 선택하려면 표 맨 위에서 &#x2713;(확인 표시)를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1216d-137">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="1216d-138">**설정 편집**을 클릭하고 원하는 대로 변경한 다음, **적용**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1216d-138">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>  

<span data-ttu-id="1216d-139">또는 다음을 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1216d-139">Or, you can also do the following:</span></span>

1. <span data-ttu-id="1216d-140">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **팀**  >  **팀 정책**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="1216d-140">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="1216d-141">정책 이름의 왼쪽을 클릭하여 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1216d-141">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="1216d-142">**사용자 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1216d-142">Select **Manage users**.</span></span>
4. <span data-ttu-id="1216d-143">**사용자 관리** 창에서 표시 이름 또는 사용자 이름으로 사용자를 검색하고 이름을 선택한 다음, **추가**를 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="1216d-143">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="1216d-144">추가할 각 사용자에 대해 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="1216d-144">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="1216d-145">사용자 추가를 마쳤으면 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1216d-145">When you're finished adding users, click **Save**.</span></span>

### <a name="assign-a-custom-teams-policy-to-users-in-a-group"></a><span data-ttu-id="1216d-146">그룹의 사용자에 게 사용자 지정 팀 정책 할당</span><span class="sxs-lookup"><span data-stu-id="1216d-146">Assign a custom teams policy to users in a group</span></span>

<span data-ttu-id="1216d-147">이미 식별 한 여러 사용자에 게 사용자 지정 팀 정책을 할당 하려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1216d-147">You may want to assign a custom teams policy to multiple users that you've already identified.</span></span> <span data-ttu-id="1216d-148">예를 들어 보안 그룹의 모든 사용자에 게 정책을 할당 하려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1216d-148">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="1216d-149">그래프 모듈의 Azure Active Directory PowerShell 및 비즈니스용 Skype PowerShell 모듈에 연결 하 여이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1216d-149">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="1216d-150">PowerShell을 사용 하 여 팀을 관리 하는 방법에 대 한 자세한 내용은 [팀 Powershell 개요](teams-powershell-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1216d-150">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

<span data-ttu-id="1216d-151">이 예제에서는 마케팅 팀 정책 이라는 팀 정책을 Contoso 마케팅 그룹의 모든 사용자에 게 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="1216d-151">In this example, we assign a teams policy called Marketing Teams Policy to all users in the Contoso Marketing group.</span></span>  

> [!NOTE]
> <span data-ttu-id="1216d-152">먼저 [모든 Microsoft 365 또는 Office 365 서비스에 연결의 단계를 단일 Windows powershell 창에](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)따라 Graph 모듈 및 비즈니스용 Skype powershell 모듈에 대 한 Azure Active Directory powershell에 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1216d-152">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="1216d-153">특정 그룹의 GroupObjectId를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1216d-153">Get the GroupObjectId of the particular group.</span></span>
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Marketing"
```
<span data-ttu-id="1216d-154">지정 된 그룹의 구성원을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1216d-154">Get the members of the specified group.</span></span>
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="1216d-155">특정 팀 정책에 그룹의 모든 사용자를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="1216d-155">Assign all users in the group to a particular teams policy.</span></span> <span data-ttu-id="1216d-156">이 예제에서는 마케팅 팀 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="1216d-156">In this example, it's Marketing Teams Policy.</span></span>
```PowerShell
$members | ForEach-Object { Grant-CsTeamsChannelsPolicy -PolicyName "Marketing Teams Policy" -Identity $_.UserPrincipalName}
``` 
<span data-ttu-id="1216d-157">그룹의 구성원 수에 따라이 명령을 실행 하는 데 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1216d-157">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="related-topics"></a><span data-ttu-id="1216d-158">관련 항목</span><span class="sxs-lookup"><span data-stu-id="1216d-158">Related topics</span></span>

- [<span data-ttu-id="1216d-159">Teams에서 비공개 팀의 검색 관리</span><span class="sxs-lookup"><span data-stu-id="1216d-159">Manage discovery of private teams in Teams</span></span>](manage-discovery-of-private-teams.md)
- [<span data-ttu-id="1216d-160">팀의 비공개 채널</span><span class="sxs-lookup"><span data-stu-id="1216d-160">Private channels in Teams</span></span>](private-channels.md)
- [<span data-ttu-id="1216d-161">팀에서 사용자에 게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="1216d-161">Assign policies to your users in Teams</span></span>](assign-policies.md)
