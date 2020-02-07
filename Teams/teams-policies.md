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
ms.openlocfilehash: dc3d5fa4880f3255017b535657a4a32a51789c82
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836968"
---
# <a name="manage-teams-policies-in-microsoft-teams"></a><span data-ttu-id="b04be-103">Microsoft 팀에서 팀 정책 관리</span><span class="sxs-lookup"><span data-stu-id="b04be-103">Manage teams policies in Microsoft Teams</span></span>

<span data-ttu-id="b04be-104">관리자는 Microsoft 팀에서 팀 정책을 사용 하 여 팀과 채널에서 조직의 사용자가 수행할 수 있는 작업을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b04be-104">As an admin, you can use teams policies in Microsoft Teams to control what users in your organization can do in teams and channels.</span></span> <span data-ttu-id="b04be-105">예를 들어 사용자가 검색 결과 및 팀 갤러리에서 비공개 팀을 검색 하도록 허용할지 여부와 사용자가 개인 채널을 만들 수 있도록 허용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b04be-105">For example, you can set whether users are allowed to discover private teams in search results and in the team gallery and whether users are allowed to create private channels.</span></span>

<span data-ttu-id="b04be-106">Microsoft 팀 관리 센터에서 **팀** > **팀 정책** 으로 이동해 서 팀 정책을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b04be-106">You manage teams policies by going to **Teams** > **Teams policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="b04be-107">전역 (조직 차원의 기본) 정책을 사용 하거나 사용자 지정 정책을 만들어 사용자에 게 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b04be-107">You can use the global (Org-wide default) policy or create custom policies and assign them to users.</span></span> <span data-ttu-id="b04be-108">사용자 지정 정책을 만들고 할당 하지 않으면 조직의 사용자가 자동으로 전역 정책을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="b04be-108">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

<span data-ttu-id="b04be-109">전역 정책을 편집 하거나 사용자 지정 정책을 만들고 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b04be-109">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="b04be-110">사용자가 사용자 지정 정책을 할당 한 경우 해당 정책이 사용자에 게 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b04be-110">If a user is assigned a custom policy, that policy applies to the user.</span></span> <span data-ttu-id="b04be-111">사용자가 사용자 지정 정책을 할당 하지 않으면 전역 정책이 사용자에 게 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b04be-111">If a user isn't assigned a custom policy, the global policy applies to the user.</span></span> <span data-ttu-id="b04be-112">전역 정책을 편집 하거나 정책을 할당 한 후 변경 내용이 적용 되는 데 최대 24 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b04be-112">After you edit the global policy or assign a policy, it can take up to 24 hours for changes to take effect.</span></span>

## <a name="create-a-custom-teams-policy"></a><span data-ttu-id="b04be-113">사용자 지정 팀 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="b04be-113">Create a custom teams policy</span></span>

1. <span data-ttu-id="b04be-114">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **팀** > **팀 정책**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b04be-114">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="b04be-115">**추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b04be-115">Click **Add**.</span></span>
3. <span data-ttu-id="b04be-116">정책의 이름 및 설명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="b04be-116">Enter a name and description for the policy.</span></span>

    ![팀 정책 설정 스크린샷](media/teams-policies.png)
4. <span data-ttu-id="b04be-118">원하는 설정을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b04be-118">Choose the settings that you want:</span></span>

- <span data-ttu-id="b04be-119">**개인 팀**검색:<a name="discoverteams"> </a> 이 설정을 사용 하면 사용자가 검색 결과 및 팀 갤러리에서 비공개 팀을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b04be-119">**Discover private teams**:<a name="discoverteams"> </a> Turn on this setting to allow users to discover private teams in search results and in the team gallery.</span></span>
- <span data-ttu-id="b04be-120">**개인 채널 만들기**: <a name="createchannels"> </a>이 설정을 사용 하면 사용자가 개인 채널을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b04be-120">**Create private channels**: <a name="createchannels"> </a>Turn on this setting to allow users to create private channels.</span></span>

5. <span data-ttu-id="b04be-121">**저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b04be-121">Click **Save**.</span></span>

## <a name="edit-a-teams-policy"></a><span data-ttu-id="b04be-122">팀 정책 편집</span><span class="sxs-lookup"><span data-stu-id="b04be-122">Edit a teams policy</span></span>

<span data-ttu-id="b04be-123">만든 전역 정책 또는 사용자 지정 정책을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b04be-123">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="b04be-124">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **팀** > **팀 정책**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b04be-124">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="b04be-125">정책 이름 왼쪽을 클릭 하 여 정책을 선택한 다음 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b04be-125">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="b04be-126">원하는 설정을 켜거나 끈 다음 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b04be-126">Turn on or turn off the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-teams-policy-to-users"></a><span data-ttu-id="b04be-127">사용자에 게 사용자 지정 팀 정책 할당</span><span class="sxs-lookup"><span data-stu-id="b04be-127">Assign a custom teams policy to users</span></span>

<span data-ttu-id="b04be-128">Microsoft 팀 관리 센터를 사용 하 여 한 명 이상의 사용자 또는 비즈니스용 Skype PowerShell 모듈에 사용자 지정 정책을 할당 하 여 보안 그룹 또는 메일 그룹과 같은 사용자 그룹에 사용자 지정 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b04be-128">You can use the Microsoft Teams admin center to assign a custom policy to one or more users or the Skype for Business PowerShell module to assign a custom policy to groups of users, such as a security group or distribution group.</span></span>

### <a name="assign-a-custom-teams-policy-to-a-user"></a><span data-ttu-id="b04be-129">사용자에 게 사용자 지정 팀 정책 할당</span><span class="sxs-lookup"><span data-stu-id="b04be-129">Assign a custom teams policy to a user</span></span>

1. <span data-ttu-id="b04be-130">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **사용자**로 이동한 다음 사용자를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b04be-130">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click  the user.</span></span>
2. <span data-ttu-id="b04be-131">**정책을**클릭 한 다음 **할당 된 정책**옆에 있는 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b04be-131">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="b04be-132">**팀 정책**에서 할당 하려는 정책을 선택한 다음 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b04be-132">Under **Teams policies**, select the policy you want to assign, and then click **Save**.</span></span>

<span data-ttu-id="b04be-133">사용자 지정 팀 정책을 한 번에 여러 사용자에 게 할당 하려면 [팀 사용자 설정을 일괄적으로 편집](edit-user-settings-in-bulk.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b04be-133">To assign a custom teams policy to multiple users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="b04be-134">또는 다음을 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b04be-134">Or, you can also do the following:</span></span>

1. <span data-ttu-id="b04be-135">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **팀** > **팀 정책**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b04be-135">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="b04be-136">정책 이름 왼쪽에 있는을 클릭 하 여 정책을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b04be-136">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="b04be-137">**사용자 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b04be-137">Select **Manage users**.</span></span>
4. <span data-ttu-id="b04be-138">**사용자 관리** 창에서 표시 이름 또는 사용자 이름을 사용 하 여 사용자를 검색 하 고 이름을 선택한 다음 **추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b04be-138">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="b04be-139">추가 하려는 각 사용자에 대해이 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="b04be-139">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="b04be-140">사용자 추가를 마쳤으면 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b04be-140">When you're finished adding users, click **Save**.</span></span>

### <a name="assign-a-custom-teams-policy-to-users-in-a-group"></a><span data-ttu-id="b04be-141">그룹의 사용자에 게 사용자 지정 팀 정책 할당</span><span class="sxs-lookup"><span data-stu-id="b04be-141">Assign a custom teams policy to users in a group</span></span>

<span data-ttu-id="b04be-142">이미 식별 한 여러 사용자에 게 사용자 지정 팀 정책을 할당 하려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b04be-142">You may want to assign a custom teams policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="b04be-143">예를 들어 보안 그룹의 모든 사용자에 게 정책을 할당 하려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b04be-143">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="b04be-144">그래프 모듈의 Azure Active Directory PowerShell 및 비즈니스용 Skype PowerShell 모듈에 연결 하 여이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b04be-144">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="b04be-145">PowerShell을 사용 하 여 팀을 관리 하는 방법에 대 한 자세한 내용은 [팀 Powershell 개요](teams-powershell-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b04be-145">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

<span data-ttu-id="b04be-146">이 예제에서는 마케팅 팀 정책 이라는 팀 정책을 Contoso 마케팅 그룹의 모든 사용자에 게 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b04be-146">In this example, we assign a teams policy called Marketing Teams Policy to all users in the Contoso Marketing group.</span></span>  

> [!NOTE]
> <span data-ttu-id="b04be-147">먼저 [단일 Windows powershell 창에서 모든 Office 365 서비스에 연결](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)의 단계를 따라 Graph 모듈 및 비즈니스용 Skype powershell 모듈에 대 한 Azure Active Directory powershell에 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b04be-147">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="b04be-148">특정 그룹의 GroupObjectId를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b04be-148">Get the GroupObjectId of the particular group.</span></span>
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Marketing"
```
<span data-ttu-id="b04be-149">지정 된 그룹의 구성원을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b04be-149">Get the members of the specified group.</span></span>
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="b04be-150">특정 팀 정책에 그룹의 모든 사용자를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b04be-150">Assign all users in the group to a particular teams policy.</span></span> <span data-ttu-id="b04be-151">이 예제에서는 마케팅 팀 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="b04be-151">In this example, it's Marketing Teams Policy.</span></span>
```PowerShell
$members | ForEach-Object { Grant-CsTeamsChannelsPolicy -PolicyName "Marketing Teams Policy" -Identity $_.UserPrincipalName}
``` 
<span data-ttu-id="b04be-152">그룹의 구성원 수에 따라이 명령을 실행 하는 데 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b04be-152">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b04be-153">관련 항목</span><span class="sxs-lookup"><span data-stu-id="b04be-153">Related topics</span></span>

- [<span data-ttu-id="b04be-154">Teams에서 비공개 팀의 검색 관리</span><span class="sxs-lookup"><span data-stu-id="b04be-154">Manage discovery of private teams in Teams</span></span>](manage-discovery-of-private-teams.md)
- [<span data-ttu-id="b04be-155">팀의 비공개 채널</span><span class="sxs-lookup"><span data-stu-id="b04be-155">Private channels in Teams</span></span>](private-channels.md)
