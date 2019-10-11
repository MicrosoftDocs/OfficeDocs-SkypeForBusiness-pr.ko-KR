---
title: Microsoft 팀에서 앱 권한 정책 관리
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: rarang
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Microsoft 팀에서 앱 권한 정책에 대해 알아보고,이를 사용 하 여 조직의 사용자가 사용할 수 있는 앱을 제어 하는 방법에 대해 알아봅니다.
f1keywords:
- ms.teamsadmincenter.apppermspolicies.overview
- ms.teamsadmincenter.appsetuppolicies.addpinnedapp.permissions
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: b6b655fd60687cb24ed6c2c8721bd889ea97548b
ms.sourcegitcommit: cf97815f18b08fd67479844170540edc7b467099
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/10/2019
ms.locfileid: "37449725"
---
# <a name="manage-app-permission-policies-in-microsoft-teams"></a><span data-ttu-id="49358-103">Microsoft 팀에서 앱 권한 정책 관리</span><span class="sxs-lookup"><span data-stu-id="49358-103">Manage app permission policies in Microsoft Teams</span></span>

<span data-ttu-id="49358-104">관리자는 앱 권한 정책을 사용 하 여 조직의 Microsoft 팀 사용자가 사용할 수 있는 앱을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49358-104">As an admin, you can use app permission policies to control what apps are available to Microsoft Teams users in your organization.</span></span> <span data-ttu-id="49358-105">Microsoft, 타사, 조직에서 게시 한 앱 또는 특정 앱을 모두 허용 하거나 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49358-105">You can allow or block all apps or specific apps published by Microsoft, third-parties, and your organization.</span></span> <span data-ttu-id="49358-106">앱을 차단 하는 경우 사용자는 팀 앱 스토어에서이를 설치할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="49358-106">When you block an app, users are unable to install it from the Teams app store.</span></span>

<span data-ttu-id="49358-107">Microsoft 팀 관리 센터에서 앱 권한 정책을 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="49358-107">You manage app permission policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="49358-108">설정을 전체에 적용 하 고 전역 (조직 차원의 기본) 정책을 사용 하 고 개별 사용자 또는 그룹의 사용자에 게 사용자 지정 정책을 만들어 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49358-108">You can apply settings org-wide, use the global (Org-wide default) policy, and create and assign custom policies to individual users or users in a group.</span></span>  

![앱 사용 권한 정책의 스크린샷](media/app-permission-policies.png)

> [!NOTE]
> <span data-ttu-id="49358-110">사용자 지정 정책을 만들고 할당 하지 않으면 조직의 사용자가 자동으로 전역 정책을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="49358-110">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="49358-111">조직 전체 앱 설정은 전역 정책 및 사용자가 만들고 할당 하는 사용자 지정 정책을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="49358-111">Org-wide app settings override the global policy and any custom policies that you create and assign to users.</span></span>

<span data-ttu-id="49358-112">조직이 이미 팀에 있는 경우 Microsoft 365 관리 센터의 **테 넌 트 전체 설정** 에서 구성한 앱 설정이 조직 전체 앱 설정에 반영 됩니다.</span><span class="sxs-lookup"><span data-stu-id="49358-112">If your organization is already on Teams, the app settings you configured in **Tenant-wide settings** in the Microsoft 365 admin center are reflected in org-wide app settings.</span></span> <span data-ttu-id="49358-113">팀을 처음 접하는 경우에는 기본적으로 모든 앱을 전역 정책에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49358-113">If you're new to Teams and just getting started, by default, all apps are allowed in the global policy.</span></span> <span data-ttu-id="49358-114">여기에는 Microsoft, 타사, 조직에서 게시 한 앱이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="49358-114">This includes apps published by Microsoft, third-parties, and your organization.</span></span>

<span data-ttu-id="49358-115">예를 들어 모든 타사 앱을 차단 하 고 조직의 HR 팀에 대해 Microsoft의 특정 앱을 허용 하려는 경우를 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="49358-115">Say, for example, you want to block all third-party apps and allow specific apps from Microsoft for the HR team in your organization.</span></span> <span data-ttu-id="49358-116">HR 앱 권한 정책 이라는 사용자 지정 정책을 만들고, 원하는 앱을 차단 하 고 허용 하도록 설정한 다음 HR 팀에서 사용자에 게 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="49358-116">You would create a custom policy named HR App Permission Policy, set it to block and allow the apps that you want, and then assign it to users on the HR team.</span></span>

## <a name="manage-org-wide-app-settings"></a><span data-ttu-id="49358-117">조직 전체 앱 설정 관리</span><span class="sxs-lookup"><span data-stu-id="49358-117">Manage org-wide app settings</span></span>

<span data-ttu-id="49358-118">조직 전체에서 사용할 수 있는 앱을 제어 하려면 org 앱 설정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="49358-118">Use org-wide app settings to control which apps are available across your organization.</span></span> <span data-ttu-id="49358-119">조직 전체 앱 설정은 모든 사용자의 동작을 제어 하 고 사용자에 게 할당 된 다른 앱 사용 권한 정책을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="49358-119">Org-wide app settings govern the behavior for all users and override any other app permission policies assigned to users.</span></span> <span data-ttu-id="49358-120">이를 사용 하 여 악의적 이거나 문제가 있는 앱을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49358-120">You can use them to control malicious or problematic apps.</span></span>

1. <span data-ttu-id="49358-121">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **팀 앱** > **권한 정책**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="49358-121">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="49358-122">**조직 전체 설정을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="49358-122">Select **Org-wide settings**.</span></span> <span data-ttu-id="49358-123">그런 다음 패널에서 원하는 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49358-123">You can then configure the settings you want in the panel.</span></span> 
    <span data-ttu-id="49358-124">![새 앱 권한 정책의 스크린샷](media/app-permission-policies-org-wide-settings.png)</span><span class="sxs-lookup"><span data-stu-id="49358-124">![Screenshot of new app permission policy](media/app-permission-policies-org-wide-settings.png)</span></span>
3. <span data-ttu-id="49358-125">타사 앱에 대 한 액세스를 제어 하기 위해이 설정을 설정 하거나 **해제 합니다.**</span><span class="sxs-lookup"><span data-stu-id="49358-125">Under **Third-party apps**, turn off or turn on these settings to control access to third-party apps:</span></span>

    - <span data-ttu-id="49358-126">**팀에서 타사 또는 사용자 지정 앱 허용**:이는 사용자가 타사 또는 사용자 지정 앱을 사용할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="49358-126">**Allow third-party or custom apps in Teams**: This controls whether users can use third-party or custom apps.</span></span>
    - <span data-ttu-id="49358-127">**기본적으로 저장소에 게시 된 새 타사 앱 허용**: 팀 앱 스토어에 게시 되는 새로운 타사 앱을 팀에서 자동으로 사용할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="49358-127">**Allow any new third-party apps published to the store by default**: This controls whether new third-party apps that are published to the Teams app store become automatically available in Teams.</span></span> <span data-ttu-id="49358-128">타사 앱을 허용 하는 경우에만이 옵션을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49358-128">You can only set this option if you allow third-party apps.</span></span>

4. <span data-ttu-id="49358-129">**사용자 지정 앱**에서 **사용자 지정 앱과의 상호 작용 허용**을 설정 하거나 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="49358-129">Under **Custom apps**, turn off or turn on **Allow interaction with custom apps**.</span></span> <span data-ttu-id="49358-130">이 설정은 사용자가 사용자 지정 (테스트용으로 로드) 앱을 조작할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="49358-130">This setting controls whether users can interact with custom (sideloaded) apps.</span></span> <span data-ttu-id="49358-131">이는 사용자가 사용자 지정 앱을 *업로드* 하는 것을 허용 하는 것과 다르다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="49358-131">Keep in mind that this is different from allowing users to *upload* custom apps.</span></span>
5. <span data-ttu-id="49358-132">**차단 된 앱**에서 조직 내에서 차단 하려는 앱을 검색 하 여 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="49358-132">Under **Blocked apps**, search for and add the apps that you want to block across your organization.</span></span> <span data-ttu-id="49358-133">테 넌 트 앱 카탈로그 또는 팀 앱 스토어에서 앱을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49358-133">You can choose apps from the tenant app catalog or the Teams app store.</span></span>
6. <span data-ttu-id="49358-134">**저장** 을 클릭 하 여 조직 전체 앱 설정을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="49358-134">Click **Save** for org-wide app settings to take effect.</span></span>

## <a name="create-a-custom-app-permission-policy"></a><span data-ttu-id="49358-135">사용자 지정 앱 권한 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="49358-135">Create a custom app permission policy</span></span>

<span data-ttu-id="49358-136">조직의 다른 사용자 그룹에 대해 사용할 수 있는 앱을 제어 하려는 경우 하나 이상의 사용자 지정 앱 권한 정책을 만들고 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="49358-136">If you want to control the apps that are available for different groups of users in your organization, create and assign one or more custom app permission policies.</span></span> <span data-ttu-id="49358-137">앱이 Microsoft, 타사 또는 조직에 의해 게시 되었는지 여부에 따라 별도의 사용자 지정 정책을 만들고 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49358-137">You can create and assign separate custom policies based on whether apps are published by Microsoft, third-parties, or your organization.</span></span> <span data-ttu-id="49358-138">사용자 지정 정책을 만든 후에는 조직 전체 설정에서 타사 앱을 사용 하지 않도록 설정한 경우 변경할 수 없다는 것을 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="49358-138">It's important to know that after you create a custom policy, you can't change it if third-party apps are disabled in org-wide settings.</span></span> 

1. <span data-ttu-id="49358-139">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **팀 앱** > **권한 정책**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="49358-139">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="49358-140">**추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="49358-140">Click **Add**.</span></span>
    <span data-ttu-id="49358-141">![새 앱 권한 정책의 스크린샷](media/app-permission-policies-new-policy.png)</span><span class="sxs-lookup"><span data-stu-id="49358-141">![Screenshot of new app permission policy](media/app-permission-policies-new-policy.png)</span></span>
3. <span data-ttu-id="49358-142">정책의 이름 및 설명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="49358-142">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="49358-143">**Microsoft 앱**, 타사 **앱**및 **테 넌 트 앱**에서 다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="49358-143">Under **Microsoft apps**, **Third-party apps**, and **Tenant apps**, select one of the following:</span></span>

    - <span data-ttu-id="49358-144">**모든 앱 허용**</span><span class="sxs-lookup"><span data-stu-id="49358-144">**Allow all apps**</span></span>
    - <span data-ttu-id="49358-145">**특정 앱 허용 및 다른 사용자 모두 차단**</span><span class="sxs-lookup"><span data-stu-id="49358-145">**Allow specific apps and block all others**</span></span>
    - <span data-ttu-id="49358-146">**특정 앱을 차단 하 고 다른 사용자 허용**</span><span class="sxs-lookup"><span data-stu-id="49358-146">**Block specific apps and allow all others**</span></span>
    - <span data-ttu-id="49358-147">**모든 앱 차단**</span><span class="sxs-lookup"><span data-stu-id="49358-147">**Block all apps**</span></span>

5. <span data-ttu-id="49358-148">**특정 앱 허용 및 다른 사용자 차단**을 선택한 경우 허용 하려는 앱을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="49358-148">If you selected **Allow specific apps and block others**, add the apps that you want to allow:</span></span>

    1. <span data-ttu-id="49358-149">**앱 허용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="49358-149">Select **Allow apps**.</span></span>
    1. <span data-ttu-id="49358-150">허용 하려는 앱을 검색 한 다음 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="49358-150">Search for the apps that you want to allow, and then click **Add**.</span></span> <span data-ttu-id="49358-151">검색 결과가 앱 게시자 (**Microsoft 앱**, 타사 **앱**또는 **테 넌 트 앱**)로 필터링 됩니다.</span><span class="sxs-lookup"><span data-stu-id="49358-151">The search results are filtered to the app publisher (**Microsoft apps**, **Third-party apps**, or **Tenant apps**).</span></span>
    1. <span data-ttu-id="49358-152">앱 목록을 선택 했으면 **허용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="49358-152">When you've chosen the list of apps, click **Allow**.</span></span>

6. <span data-ttu-id="49358-153">마찬가지로 **특정 앱을 차단 하 고 다른 모든 사용자 허용**을 선택한 경우 차단 하려는 앱을 검색 하 여 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="49358-153">Similarly, if you selected **Block specific apps and allow all others**, search for and add the apps that you want to block.</span></span>
7. <span data-ttu-id="49358-154">**저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="49358-154">Click **Save**.</span></span>

## <a name="edit-an-app-permission-policy"></a><span data-ttu-id="49358-155">앱 권한 정책 편집</span><span class="sxs-lookup"><span data-stu-id="49358-155">Edit an app permission policy</span></span>

<span data-ttu-id="49358-156">Microsoft 팀 관리 센터를 사용 하 여 글로벌 정책 및 만든 사용자 지정 정책을 비롯 한 정책을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49358-156">You can use the Microsoft Teams admin center to edit a policy, including the global policy and custom policies that you create.</span></span>

1. <span data-ttu-id="49358-157">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **팀 앱** > **권한 정책**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="49358-157">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="49358-158">정책 이름 왼쪽을 클릭 하 여 정책을 선택한 다음 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="49358-158">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="49358-159">여기서 원하는 대로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="49358-159">From here, make the changes that you want.</span></span> <span data-ttu-id="49358-160">앱 게시자에 따라 설정을 관리 하 고 허용/차단 설정에 따라 앱을 추가 및 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49358-160">You can manage settings based on the app publisher and add and remove apps based on the allow/block setting.</span></span>
4. <span data-ttu-id="49358-161">**저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="49358-161">Click **Save**.</span></span>

## <a name="assign-a-custom-app-permission-policy-to-users"></a><span data-ttu-id="49358-162">사용자에 게 사용자 지정 앱 권한 정책 할당</span><span class="sxs-lookup"><span data-stu-id="49358-162">Assign a custom app permission policy to users</span></span>

<span data-ttu-id="49358-163">Microsoft 팀 관리 센터를 사용 하 여 한 명 이상의 사용자 또는 비즈니스용 Skype PowerShell 모듈에 사용자 지정 정책을 할당 하 여 보안 그룹 또는 메일 그룹의 모든 사용자와 같은 사용자 그룹에 사용자 지정 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49358-163">You can use the Microsoft Teams admin center to assign a custom policy to one or more users or the Skype for Business PowerShell module to assign a custom policy to groups of users, such as all users in a security group or distribution group.</span></span>

### <a name="assign-a-custom-app-permission-policy-to-a-user"></a><span data-ttu-id="49358-164">사용자에 게 사용자 지정 앱 권한 정책 할당</span><span class="sxs-lookup"><span data-stu-id="49358-164">Assign a custom app permission policy to a user</span></span>

1. <span data-ttu-id="49358-165">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **사용자**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="49358-165">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="49358-166">사용자 이름 왼쪽의을 클릭 하 여 사용자를 선택 하 고 **설정 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="49358-166">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="49358-167">**앱 권한 정책**에서 할당할 앱 권한 정책을 선택한 다음 **적용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="49358-167">Under **App permission policy**, select the app permission policy you want to assign, and then click **Apply**.</span></span>

<span data-ttu-id="49358-168">한 번에 여러 사용자에 게 정책을 할당 하려면 [팀 사용자 설정을 일괄적으로 편집](edit-user-settings-in-bulk.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="49358-168">To assign a policy to multiple users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="49358-169">또는 다음을 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49358-169">Or, you can also do the following:</span></span>

1. <span data-ttu-id="49358-170">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **팀 앱** > **권한 정책**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="49358-170">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="49358-171">정책 이름 왼쪽에 있는을 클릭 하 여 정책을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="49358-171">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="49358-172">**사용자 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="49358-172">Select **Manage users**.</span></span>
4. <span data-ttu-id="49358-173">**사용자 관리** 창에서 표시 이름 또는 사용자 이름을 사용 하 여 사용자를 검색 하 고 이름을 선택한 다음 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="49358-173">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="49358-174">추가 하려는 각 사용자에 대해이 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="49358-174">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="49358-175">사용자 추가를 마쳤으면 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="49358-175">When you're finished adding users, click **Save**.</span></span>

### <a name="assign-a-custom-app-permission-policy-to-users-in-a-group"></a><span data-ttu-id="49358-176">그룹의 사용자에 게 사용자 지정 앱 권한 정책 할당</span><span class="sxs-lookup"><span data-stu-id="49358-176">Assign a custom app permission policy to users in a group</span></span>

<span data-ttu-id="49358-177">이미 식별 한 여러 사용자에 게 사용자 지정 앱 사용 권한 정책을 할당 하려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49358-177">You may want to assign a custom app permission policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="49358-178">예를 들어 보안 그룹의 모든 사용자에 게 정책을 할당 하려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49358-178">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="49358-179">그래프 모듈의 Azure Active Directory PowerShell 및 비즈니스용 Skype PowerShell 모듈에 연결 하 여이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49358-179">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="49358-180">PowerShell을 사용 하 여 팀을 관리 하는 방법에 대 한 자세한 내용은 [팀 Powershell 개요](teams-powershell-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="49358-180">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

<span data-ttu-id="49358-181">이 예제에서는 Contoso 금강 HR 프로젝트 그룹의 모든 사용자에 게 HR 앱 권한 정책 이라는 사용자 지정 앱 권한 정책을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="49358-181">In this example, we assign a custom app permission policy called HR App Permission Policy to all users in the Contoso Pharmaceuticals HR Project group.</span></span>  

> [!NOTE]
> <span data-ttu-id="49358-182">먼저 [단일 Windows powershell 창에서 모든 Office 365 서비스에 연결](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)의 단계를 따라 Graph 모듈 및 비즈니스용 Skype powershell 모듈에 대 한 Azure Active Directory powershell에 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="49358-182">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="49358-183">특정 그룹의 GroupObjectId를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="49358-183">Get the GroupObjectId of the particular group.</span></span>
```
$group = Get-AzureADGroup -SearchString "Contoso Pharmaceuticals HR Project"
```
<span data-ttu-id="49358-184">지정 된 그룹의 구성원을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="49358-184">Get the members of the specified group.</span></span>
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="49358-185">그룹의 모든 사용자를 특정 앱 권한 정책에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="49358-185">Assign all users in the group to a particular app permission policy.</span></span> <span data-ttu-id="49358-186">이 예제에서는 HR 앱 권한 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="49358-186">In this example, it's HR App Permission Policy.</span></span>
```
$members | ForEach-Object { Grant-CsTeamsAppPermissionPolicy -PolicyName "HR App Permission Policy" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="49358-187">그룹의 구성원 수에 따라이 명령을 실행 하는 데 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49358-187">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="faq"></a><span data-ttu-id="49358-188">자주 묻는 질문(FAQ)</span><span class="sxs-lookup"><span data-stu-id="49358-188">FAQ</span></span>

### <a name="working-with-app-permission-policies"></a><span data-ttu-id="49358-189">앱 권한 정책 사용</span><span class="sxs-lookup"><span data-stu-id="49358-189">Working with app permission policies</span></span>

#### <a name="can-i-control-line-of-business-lob-apps"></a><span data-ttu-id="49358-190">LOB (기간 업무) 앱을 제어할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="49358-190">Can I control line of business (LOB) apps?</span></span>
<span data-ttu-id="49358-191">예, 앱 사용 권한 정책을 사용 하 여 사용자 지정 (LOB) 앱의 출시 및 배포를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49358-191">Yes, you can use app permission policies to control the rollout and distribution of custom (LOB) apps.</span></span> <span data-ttu-id="49358-192">사용자 지정 정책을 만들거나 전역 정책을 편집 하 여 조직의 요구 사항에 따라 사용자 지정 앱을 허용 하거나 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49358-192">You can create a custom policy or edit the global policy to allow or block custom apps based on the needs of your organization.</span></span>

#### <a name="how-do-app-permission-policies-relate-to-pinned-apps-and-app-setup-policies"></a><span data-ttu-id="49358-193">앱 권한 정책은 고정 된 앱 및 앱 설정 정책과 어떻게 관련 되나요?</span><span class="sxs-lookup"><span data-stu-id="49358-193">How do app permission policies relate to pinned apps and app setup policies?</span></span>

<span data-ttu-id="49358-194">앱 설치 정책은 앱 권한 정책과 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49358-194">You can use app setup policies together with app permission policies.</span></span> <span data-ttu-id="49358-195">미리 고정 된 앱은 사용자의 활성화 된 앱 집합에서 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="49358-195">Pre-pinned apps are selected from the set of enabled apps for a user.</span></span> <span data-ttu-id="49358-196">또한 사용자에 게 앱 설정 정책에서 앱을 차단 하는 앱 권한 정책이 있는 경우 해당 앱은 팀에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="49358-196">Additionally, if a user has an app permission policy that blocks an app in their app setup policy, that app won't appear in Teams.</span></span>

#### <a name="can-i-use-app-permission-policies-to-restrict-uploading-custom-apps-also-known-as-sideloading"></a><span data-ttu-id="49358-197">앱 권한 정책을 사용 하 여 사용자 지정 앱 (테스트용 로드 라고도 함) 업로드를 제한할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="49358-197">Can I use app permission policies to restrict uploading custom apps (also known as sideloading)?</span></span>

<span data-ttu-id="49358-198">앱 권한 정책에서 조직 전체 설정을 사용 하 여 조직의 사용자 지정 앱 업로드를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49358-198">Use org-wide settings in app permission policies to restrict uploading custom apps for your organization.</span></span>  

<span data-ttu-id="49358-199">특정 사용자가 사용자 지정 앱을 업로드 하지 못하도록 제한 하려면 사용자 지정 앱 정책 (제공 예정)을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="49358-199">To restrict specific users from uploading custom apps, use custom app policies (coming soon).</span></span> <span data-ttu-id="49358-200">자세히 알아보려면 [팀에서 사용자 지정 앱 정책 및 설정 관리](teams-custom-app-policies-and-settings.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="49358-200">To learn more, see [Manage custom app policies and settings in Teams](teams-custom-app-policies-and-settings.md).</span></span>

#### <a name="does-blocking-an-app-apply-to-teams-mobile-clients"></a><span data-ttu-id="49358-201">앱이 팀 모바일 클라이언트에 적용 되는 것을 차단 합니까?</span><span class="sxs-lookup"><span data-stu-id="49358-201">Does blocking an app apply to Teams mobile clients?</span></span>

<span data-ttu-id="49358-202">예, 앱을 차단 하면 모든 팀 클라이언트에서 앱이 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="49358-202">Yes, when you block an app, that app is blocked across all Teams clients.</span></span>  

### <a name="user-experience"></a><span data-ttu-id="49358-203">사용자 환경</span><span class="sxs-lookup"><span data-stu-id="49358-203">User experience</span></span>

#### <a name="what-does-a-user-experience-when-an-app-is-blocked"></a><span data-ttu-id="49358-204">앱이 차단 되는 경우 사용자 환경</span><span class="sxs-lookup"><span data-stu-id="49358-204">What does a user experience when an app is blocked?</span></span>

<span data-ttu-id="49358-205">사용자는 차단 된 앱 또는 인공 지능, 탭, 메시징 확장과 같은 기능을 조작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="49358-205">Users can't interact with a blocked app or its capabilities, such bots, tabs, and messaging extensions.</span></span> <span data-ttu-id="49358-206">팀 또는 그룹 채팅 같은 공유 컨텍스트에서이는 해당 컨텍스트의 모든 참가자에 게 메시지를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49358-206">In a shared context, such as a team or group chat, bots can still send messages to all participants of that context.</span></span> <span data-ttu-id="49358-207">앱이 차단 되 면 팀에서 사용자에 게 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="49358-207">Teams indicates to the user when an app is blocked.</span></span>

<span data-ttu-id="49358-208">예를 들어 앱이 차단 되 면 사용자는 다음을 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="49358-208">For example, when an app is blocked, users can't do any of the following:</span></span>

- <span data-ttu-id="49358-209">개인적으로 또는 채팅 또는 팀에 앱 추가</span><span class="sxs-lookup"><span data-stu-id="49358-209">Add the app personally or to a chat or team</span></span>
- <span data-ttu-id="49358-210">앱의 bot에 메시지 보내기</span><span class="sxs-lookup"><span data-stu-id="49358-210">Send messages to the app’s bot</span></span>
- <span data-ttu-id="49358-211">처리 가능한 메시지 등의 정보를 앱으로 다시 보내는 단추 작업 수행</span><span class="sxs-lookup"><span data-stu-id="49358-211">Perform button actions that send information back to the app, such as actionable messages</span></span>  
- <span data-ttu-id="49358-212">앱의 탭 보기</span><span class="sxs-lookup"><span data-stu-id="49358-212">View the app’s tab</span></span>
- <span data-ttu-id="49358-213">알림을 받도록 커넥터 설정</span><span class="sxs-lookup"><span data-stu-id="49358-213">Set up connectors to receive notifications</span></span>
- <span data-ttu-id="49358-214">앱의 메시징 확장 사용</span><span class="sxs-lookup"><span data-stu-id="49358-214">Use the app’s messaging extension</span></span>

<span data-ttu-id="49358-215">레거시 포털은 조직 수준에서 앱을 제어할 수 있으며,이는 앱이 차단 되는 경우 조직의 모든 사용자에 대해 차단 됨을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="49358-215">The legacy portal allowed controlling apps at the organization level, which means when an app is blocked, it's blocked for all users in the organization.</span></span> <span data-ttu-id="49358-216">앱 권한 정책의 조직 전체 앱 설정은 정확히 동일한 방식으로 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="49358-216">The org-wide app setting in app permission policies works exactly the same way.</span></span>

<span data-ttu-id="49358-217">특정 사용자에 게 할당 된 앱 권한 정책의 경우, 봇 또는 커넥터 기능이 있는 앱이 허용 된 후 차단 되며,이 앱이 공유 컨텍스트의 일부 사용자 에게만 허용 되는 경우 해당 앱에 대 한 권한이 없는 그룹 채팅 또는 채널의 구성원  봇 또는 커넥터에 의해 게시 된 메시지 기록 및 메시지를 볼 수 있지만 대화형 작업할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="49358-217">For app permission policies assigned to specific users, if an app with bot or connector capability was allowed and then blocked, and if the app is then allowed only for some users in a shared context, members of a group chat or channel that don't have permission to that app can see the message history and messages that were posted by the bot or connector, but can't interact with it.</span></span>

 ## <a name="related-topics"></a><span data-ttu-id="49358-218">관련 항목</span><span class="sxs-lookup"><span data-stu-id="49358-218">Related topics</span></span>
- [<span data-ttu-id="49358-219">팀의 앱에 대 한 관리자 설정</span><span class="sxs-lookup"><span data-stu-id="49358-219">Admin settings for apps in Teams</span></span>](admin-settings.md)
