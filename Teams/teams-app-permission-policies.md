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
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Microsoft 팀에서 앱 권한 정책에 대해 알아보고,이를 사용 하 여 조직의 사용자가 사용할 수 있는 앱을 제어 하는 방법에 대해 알아봅니다.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.overview
- ms.teamsadmincenter.appsetuppolicies.addpinnedapp.permissions
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: ed568fe0354f009656e3837d36701a94f0765340
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837408"
---
# <a name="manage-app-permission-policies-in-microsoft-teams"></a><span data-ttu-id="0b7d0-103">Microsoft 팀에서 앱 권한 정책 관리</span><span class="sxs-lookup"><span data-stu-id="0b7d0-103">Manage app permission policies in Microsoft Teams</span></span>

<span data-ttu-id="0b7d0-104">관리자는 앱 권한 정책을 사용 하 여 조직의 Microsoft 팀 사용자가 사용할 수 있는 앱을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-104">As an admin, you can use app permission policies to control what apps are available to Microsoft Teams users in your organization.</span></span> <span data-ttu-id="0b7d0-105">Microsoft, 타사, 조직에서 게시 한 앱 또는 특정 앱을 모두 허용 하거나 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-105">You can allow or block all apps or specific apps published by Microsoft, third-parties, and your organization.</span></span> <span data-ttu-id="0b7d0-106">앱을 차단 하는 경우 사용자는 팀 앱 스토어에서이를 설치할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-106">When you block an app, users are unable to install it from the Teams app store.</span></span>

<span data-ttu-id="0b7d0-107">Microsoft 팀 관리 센터에서 앱 권한 정책을 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-107">You manage app permission policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="0b7d0-108">설정을 전체에 적용 하 고 전역 (조직 차원의 기본) 정책을 사용 하 고 개별 사용자 또는 그룹의 사용자에 게 사용자 지정 정책을 만들어 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-108">You can apply settings org-wide, use the global (Org-wide default) policy, and create and assign custom policies to individual users or users in a group.</span></span>  

![앱 사용 권한 정책의 스크린샷](media/app-permission-policies.png)

> [!NOTE]
> <span data-ttu-id="0b7d0-110">사용자 지정 정책을 만들고 할당 하지 않으면 조직의 사용자가 자동으로 전역 정책을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-110">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="0b7d0-111">조직 전체 앱 설정은 전역 정책 및 사용자가 만들고 할당 하는 사용자 지정 정책을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-111">Org-wide app settings override the global policy and any custom policies that you create and assign to users.</span></span>

<span data-ttu-id="0b7d0-112">조직이 이미 팀에 있는 경우 Microsoft 365 관리 센터의 **테 넌 트 전체 설정** 에서 구성한 앱 설정이 조직 전체 앱 설정에 반영 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-112">If your organization is already on Teams, the app settings you configured in **Tenant-wide settings** in the Microsoft 365 admin center are reflected in org-wide app settings.</span></span> <span data-ttu-id="0b7d0-113">팀을 처음 접하는 경우에는 기본적으로 모든 앱을 전역 정책에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-113">If you're new to Teams and just getting started, by default, all apps are allowed in the global policy.</span></span> <span data-ttu-id="0b7d0-114">여기에는 Microsoft, 타사, 조직에서 게시 한 앱이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-114">This includes apps published by Microsoft, third-parties, and your organization.</span></span>

<span data-ttu-id="0b7d0-115">예를 들어 모든 타사 앱을 차단 하 고 조직의 HR 팀에 대해 Microsoft의 특정 앱을 허용 하려는 경우를 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-115">Say, for example, you want to block all third-party apps and allow specific apps from Microsoft for the HR team in your organization.</span></span> <span data-ttu-id="0b7d0-116">HR 앱 권한 정책 이라는 사용자 지정 정책을 만들고, 원하는 앱을 차단 하 고 허용 하도록 설정한 다음 HR 팀에서 사용자에 게 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-116">You would create a custom policy named HR App Permission Policy, set it to block and allow the apps that you want, and then assign it to users on the HR team.</span></span>

> [!NOTE]
> <span data-ttu-id="0b7d0-117">Microsoft 365 정부-GCC 환경에서 팀을 배포한 경우 gcc에 고유한 타사 앱 설정에 대 한 자세한 내용은 [gcc 용 앱 권한 정책을](#app-permission-policies-for-gcc) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-117">If you deployed Teams in a Microsoft 365 Government - GCC environment, see [App permission policies for GCC](#app-permission-policies-for-gcc) to learn more about third-party app settings that are unique to GCC.</span></span>

## <a name="manage-org-wide-app-settings"></a><span data-ttu-id="0b7d0-118">조직 전체 앱 설정 관리</span><span class="sxs-lookup"><span data-stu-id="0b7d0-118">Manage org-wide app settings</span></span>

<span data-ttu-id="0b7d0-119">조직 전체에서 사용할 수 있는 앱을 제어 하려면 org 앱 설정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-119">Use org-wide app settings to control which apps are available across your organization.</span></span> <span data-ttu-id="0b7d0-120">조직 전체 앱 설정은 모든 사용자의 동작을 제어 하 고 사용자에 게 할당 된 다른 앱 사용 권한 정책을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-120">Org-wide app settings govern the behavior for all users and override any other app permission policies assigned to users.</span></span> <span data-ttu-id="0b7d0-121">이를 사용 하 여 악의적 이거나 문제가 있는 앱을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-121">You can use them to control malicious or problematic apps.</span></span>

1. <span data-ttu-id="0b7d0-122">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **팀 앱** > **권한 정책**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-122">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="0b7d0-123">**조직 전체 설정을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-123">Select **Org-wide settings**.</span></span> <span data-ttu-id="0b7d0-124">그런 다음 패널에서 원하는 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-124">You can then configure the settings you want in the panel.</span></span> 
    <span data-ttu-id="0b7d0-125">![조직 전체 앱 설정 스크린샷](media/app-permission-policies-org-wide-settings.png)</span><span class="sxs-lookup"><span data-stu-id="0b7d0-125">![Screenshot of org-wide app settings](media/app-permission-policies-org-wide-settings.png)</span></span>
3. <span data-ttu-id="0b7d0-126">타사 앱에 대 한 액세스를 제어 하기 위해이 설정을 설정 하거나 **해제 합니다.**</span><span class="sxs-lookup"><span data-stu-id="0b7d0-126">Under **Third-party apps**, turn off or turn on these settings to control access to third-party apps:</span></span>

    - <span data-ttu-id="0b7d0-127">**팀에서 제 3 자 허용**:이는 사용자가 타사 앱을 사용할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-127">**Allow third-party in Teams**: This controls whether users can use third-party apps.</span></span>
    - <span data-ttu-id="0b7d0-128">**기본적으로 저장소에 게시 된 새 타사 앱 허용**: 팀 앱 스토어에 게시 되는 새로운 타사 앱을 팀에서 자동으로 사용할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-128">**Allow any new third-party apps published to the store by default**: This controls whether new third-party apps that are published to the Teams app store become automatically available in Teams.</span></span> <span data-ttu-id="0b7d0-129">타사 앱을 허용 하는 경우에만이 옵션을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-129">You can only set this option if you allow third-party apps.</span></span>

4. <span data-ttu-id="0b7d0-130">**사용자 지정 앱**에서 **사용자 지정 앱과의 상호 작용 허용**을 설정 하거나 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-130">Under **Custom apps**, turn off or turn on **Allow interaction with custom apps**.</span></span> <span data-ttu-id="0b7d0-131">이 설정은 사용자가 사용자 지정 (테스트용으로 로드) 앱을 조작할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-131">This setting controls whether users can interact with custom (sideloaded) apps.</span></span> <span data-ttu-id="0b7d0-132">이는 사용자가 사용자 지정 앱을 *업로드* 하는 것을 허용 하는 것과 다르다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-132">Keep in mind that this is different from allowing users to *upload* custom apps.</span></span>
5. <span data-ttu-id="0b7d0-133">**차단 된 앱**에서 조직 내에서 차단 하려는 앱을 검색 하 여 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-133">Under **Blocked apps**, search for and add the apps that you want to block across your organization.</span></span> <span data-ttu-id="0b7d0-134">테 넌 트 앱 카탈로그 또는 팀 앱 스토어에서 앱을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-134">You can choose apps from the tenant app catalog or the Teams app store.</span></span>
6. <span data-ttu-id="0b7d0-135">**저장** 을 클릭 하 여 조직 전체 앱 설정을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-135">Click **Save** for org-wide app settings to take effect.</span></span>

## <a name="create-a-custom-app-permission-policy"></a><span data-ttu-id="0b7d0-136">사용자 지정 앱 권한 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="0b7d0-136">Create a custom app permission policy</span></span>

<span data-ttu-id="0b7d0-137">조직의 다른 사용자 그룹에 대해 사용할 수 있는 앱을 제어 하려는 경우 하나 이상의 사용자 지정 앱 권한 정책을 만들고 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-137">If you want to control the apps that are available for different groups of users in your organization, create and assign one or more custom app permission policies.</span></span> <span data-ttu-id="0b7d0-138">앱이 Microsoft, 타사 또는 조직에 의해 게시 되었는지 여부에 따라 별도의 사용자 지정 정책을 만들고 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-138">You can create and assign separate custom policies based on whether apps are published by Microsoft, third-parties, or your organization.</span></span> <span data-ttu-id="0b7d0-139">사용자 지정 정책을 만든 후에는 조직 전체 설정에서 타사 앱을 사용 하지 않도록 설정한 경우 변경할 수 없다는 것을 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-139">It's important to know that after you create a custom policy, you can't change it if third-party apps are disabled in org-wide settings.</span></span> 

1. <span data-ttu-id="0b7d0-140">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **팀 앱** > **권한 정책**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-140">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="0b7d0-141">**추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-141">Click **Add**.</span></span>
    <span data-ttu-id="0b7d0-142">![새 앱 권한 정책의 스크린샷](media/app-permission-policies-new-policy.png)</span><span class="sxs-lookup"><span data-stu-id="0b7d0-142">![Screenshot of new app permission policy](media/app-permission-policies-new-policy.png)</span></span>
3. <span data-ttu-id="0b7d0-143">정책의 이름 및 설명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-143">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="0b7d0-144">**Microsoft 앱**, 타사 **앱**및 **테 넌 트 앱**에서 다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-144">Under **Microsoft apps**, **Third-party apps**, and **Tenant apps**, select one of the following:</span></span>

    - <span data-ttu-id="0b7d0-145">**모든 앱 허용**</span><span class="sxs-lookup"><span data-stu-id="0b7d0-145">**Allow all apps**</span></span>
    - <span data-ttu-id="0b7d0-146">**특정 앱 허용 및 다른 사용자 모두 차단**</span><span class="sxs-lookup"><span data-stu-id="0b7d0-146">**Allow specific apps and block all others**</span></span>
    - <span data-ttu-id="0b7d0-147">**특정 앱을 차단 하 고 다른 사용자 허용**</span><span class="sxs-lookup"><span data-stu-id="0b7d0-147">**Block specific apps and allow all others**</span></span>
    - <span data-ttu-id="0b7d0-148">**모든 앱 차단**</span><span class="sxs-lookup"><span data-stu-id="0b7d0-148">**Block all apps**</span></span>

5. <span data-ttu-id="0b7d0-149">**특정 앱 허용 및 다른 사용자 차단**을 선택한 경우 허용 하려는 앱을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-149">If you selected **Allow specific apps and block others**, add the apps that you want to allow:</span></span>

    1. <span data-ttu-id="0b7d0-150">**앱 허용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-150">Select **Allow apps**.</span></span>
    1. <span data-ttu-id="0b7d0-151">허용 하려는 앱을 검색 한 다음 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-151">Search for the apps that you want to allow, and then click **Add**.</span></span> <span data-ttu-id="0b7d0-152">검색 결과가 앱 게시자 (**Microsoft 앱**, 타사 **앱**또는 **테 넌 트 앱**)로 필터링 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-152">The search results are filtered to the app publisher (**Microsoft apps**, **Third-party apps**, or **Tenant apps**).</span></span>
    1. <span data-ttu-id="0b7d0-153">앱 목록을 선택 했으면 **허용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-153">When you've chosen the list of apps, click **Allow**.</span></span>

6. <span data-ttu-id="0b7d0-154">마찬가지로 **특정 앱을 차단 하 고 다른 모든 사용자 허용**을 선택한 경우 차단 하려는 앱을 검색 하 여 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-154">Similarly, if you selected **Block specific apps and allow all others**, search for and add the apps that you want to block.</span></span>
7. <span data-ttu-id="0b7d0-155">**저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-155">Click **Save**.</span></span>

## <a name="edit-an-app-permission-policy"></a><span data-ttu-id="0b7d0-156">앱 권한 정책 편집</span><span class="sxs-lookup"><span data-stu-id="0b7d0-156">Edit an app permission policy</span></span>

<span data-ttu-id="0b7d0-157">Microsoft 팀 관리 센터를 사용 하 여 글로벌 정책 및 만든 사용자 지정 정책을 비롯 한 정책을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-157">You can use the Microsoft Teams admin center to edit a policy, including the global policy and custom policies that you create.</span></span>

1. <span data-ttu-id="0b7d0-158">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **팀 앱** > **권한 정책**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-158">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="0b7d0-159">정책 이름 왼쪽을 클릭 하 여 정책을 선택한 다음 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-159">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="0b7d0-160">여기서 원하는 대로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-160">From here, make the changes that you want.</span></span> <span data-ttu-id="0b7d0-161">앱 게시자에 따라 설정을 관리 하 고 허용/차단 설정에 따라 앱을 추가 및 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-161">You can manage settings based on the app publisher and add and remove apps based on the allow/block setting.</span></span>
4. <span data-ttu-id="0b7d0-162">**저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-162">Click **Save**.</span></span>

## <a name="assign-a-custom-app-permission-policy-to-users"></a><span data-ttu-id="0b7d0-163">사용자에 게 사용자 지정 앱 권한 정책 할당</span><span class="sxs-lookup"><span data-stu-id="0b7d0-163">Assign a custom app permission policy to users</span></span>

<span data-ttu-id="0b7d0-164">Microsoft 팀 관리 센터를 사용 하 여 한 명 이상의 사용자 또는 비즈니스용 Skype PowerShell 모듈에 사용자 지정 정책을 할당 하 여 보안 그룹 또는 메일 그룹의 모든 사용자와 같은 사용자 그룹에 사용자 지정 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-164">You can use the Microsoft Teams admin center to assign a custom policy to one or more users or the Skype for Business PowerShell module to assign a custom policy to groups of users, such as all users in a security group or distribution group.</span></span>

### <a name="assign-a-custom-app-permission-policy-to-a-user"></a><span data-ttu-id="0b7d0-165">사용자에 게 사용자 지정 앱 권한 정책 할당</span><span class="sxs-lookup"><span data-stu-id="0b7d0-165">Assign a custom app permission policy to a user</span></span>

1. <span data-ttu-id="0b7d0-166">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **사용자**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-166">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="0b7d0-167">사용자 이름 왼쪽의을 클릭 하 여 사용자를 선택 하 고 **설정 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-167">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="0b7d0-168">**앱 권한 정책**에서 할당할 앱 권한 정책을 선택한 다음 **적용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-168">Under **App permission policy**, select the app permission policy you want to assign, and then click **Apply**.</span></span>

<span data-ttu-id="0b7d0-169">한 번에 여러 사용자에 게 정책을 할당 하려면 [팀 사용자 설정을 일괄적으로 편집](edit-user-settings-in-bulk.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-169">To assign a policy to multiple users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="0b7d0-170">또는 다음을 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-170">Or, you can also do the following:</span></span>

1. <span data-ttu-id="0b7d0-171">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **팀 앱** > **권한 정책**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-171">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="0b7d0-172">정책 이름 왼쪽에 있는을 클릭 하 여 정책을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-172">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="0b7d0-173">**사용자 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-173">Select **Manage users**.</span></span>
4. <span data-ttu-id="0b7d0-174">**사용자 관리** 창에서 표시 이름 또는 사용자 이름을 사용 하 여 사용자를 검색 하 고 이름을 선택한 다음 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-174">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="0b7d0-175">추가 하려는 각 사용자에 대해이 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-175">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="0b7d0-176">사용자 추가를 마쳤으면 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-176">When you're finished adding users, click **Save**.</span></span>

### <a name="assign-a-custom-app-permission-policy-to-users-in-a-group"></a><span data-ttu-id="0b7d0-177">그룹의 사용자에 게 사용자 지정 앱 권한 정책 할당</span><span class="sxs-lookup"><span data-stu-id="0b7d0-177">Assign a custom app permission policy to users in a group</span></span>

<span data-ttu-id="0b7d0-178">이미 식별 한 여러 사용자에 게 사용자 지정 앱 사용 권한 정책을 할당 하려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-178">You may want to assign a custom app permission policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="0b7d0-179">예를 들어 보안 그룹의 모든 사용자에 게 정책을 할당 하려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-179">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="0b7d0-180">그래프 모듈의 Azure Active Directory PowerShell 및 비즈니스용 Skype PowerShell 모듈에 연결 하 여이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-180">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="0b7d0-181">PowerShell을 사용 하 여 팀을 관리 하는 방법에 대 한 자세한 내용은 [팀 Powershell 개요](teams-powershell-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-181">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

<span data-ttu-id="0b7d0-182">이 예제에서는 Contoso 금강 HR 프로젝트 그룹의 모든 사용자에 게 HR 앱 권한 정책 이라는 사용자 지정 앱 권한 정책을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-182">In this example, we assign a custom app permission policy called HR App Permission Policy to all users in the Contoso Pharmaceuticals HR Project group.</span></span>  

> [!NOTE]
> <span data-ttu-id="0b7d0-183">먼저 [단일 Windows powershell 창에서 모든 Office 365 서비스에 연결](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)의 단계를 따라 Graph 모듈 및 비즈니스용 Skype powershell 모듈에 대 한 Azure Active Directory powershell에 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-183">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="0b7d0-184">특정 그룹의 GroupObjectId를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-184">Get the GroupObjectId of the particular group.</span></span>
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Pharmaceuticals HR Project"
```
<span data-ttu-id="0b7d0-185">지정 된 그룹의 구성원을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-185">Get the members of the specified group.</span></span>
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="0b7d0-186">그룹의 모든 사용자를 특정 앱 권한 정책에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-186">Assign all users in the group to a particular app permission policy.</span></span> <span data-ttu-id="0b7d0-187">이 예제에서는 HR 앱 권한 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-187">In this example, it's HR App Permission Policy.</span></span>
```PowerShell
$members | ForEach-Object { Grant-CsTeamsAppPermissionPolicy -PolicyName "HR App Permission Policy" -Identity $_.UserPrincipalName}
``` 
<span data-ttu-id="0b7d0-188">그룹의 구성원 수에 따라이 명령을 실행 하는 데 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-188">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="app-permission-policies-for-gcc"></a><span data-ttu-id="0b7d0-189">GCC 용 앱 권한 정책</span><span class="sxs-lookup"><span data-stu-id="0b7d0-189">App permission policies for GCC</span></span>

<span data-ttu-id="0b7d0-190">팀의 Microsoft 365 정부-GCC 배포에서 GCC에 고유한 제 3 자 앱 설정에 대 한 다음 사항을 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-190">In a Microsoft 365 Government - GCC deployment of Teams, it's important to know the following about third-party app settings, which are unique to GCC.</span></span>

<span data-ttu-id="0b7d0-191">GCC에서는 모든 타사 앱이 기본적으로 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-191">In GCC, all third-party apps are blocked by default.</span></span> <span data-ttu-id="0b7d0-192">또한 Microsoft 팀 관리 센터의 앱 사용 권한 정책 페이지에서 타사 앱을 관리 하는 방법에 대 한 참고 사항을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-192">Additionally, you'll see the following note about managing third-party apps on the app permission policies page in the Microsoft Teams admin center.</span></span>

![GCC의 앱 사용 권한 정책 스크린샷](media/app-permission-policies-gcc.png)

<span data-ttu-id="0b7d0-194">조직의 사용자 또는 사용자 집합에 대해 타사 앱을 사용 하도록 설정 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-194">To enable a third-party app for a user or a set of users in your organization, do the following:</span></span>

1. <span data-ttu-id="0b7d0-195">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **팀 앱** > **권한 정책**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-195">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="0b7d0-196">사용자 집합을 허용 하려는 타사 앱이 조직 수준에서 차단 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-196">Confirm that the third-party app that you want to allow for a set of users is blocked at the org level.</span></span> <span data-ttu-id="0b7d0-197">이렇게 하려면 **조직 전체 설정을**클릭 한 다음 **차단 된 앱**에서 앱이 나열 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-197">To do this, click **Org-wide settings**, and then under **Blocked apps**, check to make sure the app is listed.</span></span>
3. <span data-ttu-id="0b7d0-198">전역 정책을 편집 하 여 타사 앱을 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-198">Edit the global policy to block the third-party app.</span></span> <span data-ttu-id="0b7d0-199">실행할 작업:</span><span class="sxs-lookup"><span data-stu-id="0b7d0-199">To do this:</span></span>
    1. <span data-ttu-id="0b7d0-200">앱 권한 정책 페이지에서 **전역 (조직 전체 기본값)** 을 클릭 한 다음 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-200">On the App permission policies page, click **Global (Org-wide default)**, and then click **Edit**.</span></span>
    2. <span data-ttu-id="0b7d0-201">**타사 앱**에서 **특정 앱 차단을 선택 하 고 다른 모든 사용자를 허용**하 고 앱을 추가한 다음 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-201">Under **Third-party apps**, select **Block specific apps and allow all others**, add the app, and then click **Save**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0b7d0-202">조직 수준에서 앱을 허용 하기 위해 다음 단계로 이동 하기 전에이 작업을 수행 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-202">It's important to do this before you go to the next step to allow the app at the org level.</span></span> <span data-ttu-id="0b7d0-203">이는 타사 앱이 전역 정책에서 차단 되지 않은 경우 전역 정책이 적용 되는 모든 사용자가 조직 수준에서 사용할 때 타사 앱에 액세스할 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-203">This is because if the third-party app isn't blocked in the global policy, all users that the global policy applies to will be able to access the third-party app when you allow it at the org level.</span></span>

4. <span data-ttu-id="0b7d0-204">조직 수준에서 타사 앱을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-204">Allow the third-party app at the org level.</span></span> <span data-ttu-id="0b7d0-205">이렇게 하려면 **조직 전체 설정을**클릭 하 고 **차단 된 앱**에서 목록에서 앱을 제거한 다음 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-205">To do this, click **Org-wide settings**, under **Blocked apps**, remove the app from the list, and then click **Save**.</span></span>
5. <span data-ttu-id="0b7d0-206">앱을 허용 하는 [사용자 지정 앱 권한 정책을 만든](#create-a-custom-app-permission-policy) 다음 정책을 원하는 사용자에 게 [할당](#assign-a-custom-app-permission-policy-to-users) 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-206">[Create a custom app permission policy](#create-a-custom-app-permission-policy) to allow the app, and then [assign the policy](#assign-a-custom-app-permission-policy-to-users) to the users you want.</span></span>

## <a name="faq"></a><span data-ttu-id="0b7d0-207">FAQ</span><span class="sxs-lookup"><span data-stu-id="0b7d0-207">FAQ</span></span>

### <a name="working-with-app-permission-policies"></a><span data-ttu-id="0b7d0-208">앱 권한 정책 사용</span><span class="sxs-lookup"><span data-stu-id="0b7d0-208">Working with app permission policies</span></span>

#### <a name="can-i-control-line-of-business-lob-apps"></a><span data-ttu-id="0b7d0-209">LOB (기간 업무) 앱을 제어할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="0b7d0-209">Can I control line of business (LOB) apps?</span></span>
<span data-ttu-id="0b7d0-210">예, 앱 사용 권한 정책을 사용 하 여 사용자 지정 (LOB) 앱의 출시 및 배포를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-210">Yes, you can use app permission policies to control the rollout and distribution of custom (LOB) apps.</span></span> <span data-ttu-id="0b7d0-211">사용자 지정 정책을 만들거나 전역 정책을 편집 하 여 조직의 요구 사항에 따라 사용자 지정 앱을 허용 하거나 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-211">You can create a custom policy or edit the global policy to allow or block custom apps based on the needs of your organization.</span></span>

#### <a name="how-do-app-permission-policies-relate-to-pinned-apps-and-app-setup-policies"></a><span data-ttu-id="0b7d0-212">앱 권한 정책은 고정 된 앱 및 앱 설정 정책과 어떻게 관련 되나요?</span><span class="sxs-lookup"><span data-stu-id="0b7d0-212">How do app permission policies relate to pinned apps and app setup policies?</span></span>

<span data-ttu-id="0b7d0-213">앱 설치 정책은 앱 권한 정책과 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-213">You can use app setup policies together with app permission policies.</span></span> <span data-ttu-id="0b7d0-214">미리 고정 된 앱은 사용자의 활성화 된 앱 집합에서 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-214">Pre-pinned apps are selected from the set of enabled apps for a user.</span></span> <span data-ttu-id="0b7d0-215">또한 사용자에 게 앱 설정 정책에서 앱을 차단 하는 앱 권한 정책이 있는 경우 해당 앱은 팀에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-215">Additionally, if a user has an app permission policy that blocks an app in their app setup policy, that app won't appear in Teams.</span></span>

#### <a name="can-i-use-app-permission-policies-to-restrict-uploading-custom-apps-also-known-as-sideloading"></a><span data-ttu-id="0b7d0-216">앱 권한 정책을 사용 하 여 사용자 지정 앱 (테스트용 로드 라고도 함) 업로드를 제한할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="0b7d0-216">Can I use app permission policies to restrict uploading custom apps (also known as sideloading)?</span></span>

<span data-ttu-id="0b7d0-217">앱 권한 정책에서 조직 전체 설정을 사용 하 여 조직의 사용자 지정 앱 업로드를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-217">Use org-wide settings in app permission policies to restrict uploading custom apps for your organization.</span></span>  

<span data-ttu-id="0b7d0-218">특정 사용자가 사용자 지정 앱을 업로드 하지 못하도록 제한 하려면 사용자 지정 앱 정책을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-218">To restrict specific users from uploading custom apps, use custom app policies.</span></span> <span data-ttu-id="0b7d0-219">자세히 알아보려면 [팀에서 사용자 지정 앱 정책 및 설정 관리](teams-custom-app-policies-and-settings.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-219">To learn more, see [Manage custom app policies and settings in Teams](teams-custom-app-policies-and-settings.md).</span></span>

#### <a name="does-blocking-an-app-apply-to-teams-mobile-clients"></a><span data-ttu-id="0b7d0-220">앱이 팀 모바일 클라이언트에 적용 되는 것을 차단 합니까?</span><span class="sxs-lookup"><span data-stu-id="0b7d0-220">Does blocking an app apply to Teams mobile clients?</span></span>

<span data-ttu-id="0b7d0-221">예, 앱을 차단 하면 모든 팀 클라이언트에서 앱이 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-221">Yes, when you block an app, that app is blocked across all Teams clients.</span></span>  

### <a name="user-experience"></a><span data-ttu-id="0b7d0-222">사용자 환경</span><span class="sxs-lookup"><span data-stu-id="0b7d0-222">User experience</span></span>

#### <a name="what-does-a-user-experience-when-an-app-is-blocked"></a><span data-ttu-id="0b7d0-223">앱이 차단 되는 경우 사용자 환경</span><span class="sxs-lookup"><span data-stu-id="0b7d0-223">What does a user experience when an app is blocked?</span></span>

<span data-ttu-id="0b7d0-224">사용자는 차단 된 앱 또는 인공 지능, 탭, 메시징 확장과 같은 기능을 조작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-224">Users can't interact with a blocked app or its capabilities, such bots, tabs, and messaging extensions.</span></span> <span data-ttu-id="0b7d0-225">팀 또는 그룹 채팅 같은 공유 컨텍스트에서이는 해당 컨텍스트의 모든 참가자에 게 메시지를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-225">In a shared context, such as a team or group chat, bots can still send messages to all participants of that context.</span></span> <span data-ttu-id="0b7d0-226">앱이 차단 되 면 팀에서 사용자에 게 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-226">Teams indicates to the user when an app is blocked.</span></span>

<span data-ttu-id="0b7d0-227">예를 들어 앱이 차단 되 면 사용자는 다음을 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-227">For example, when an app is blocked, users can't do any of the following:</span></span>

- <span data-ttu-id="0b7d0-228">개인적으로 또는 채팅 또는 팀에 앱 추가</span><span class="sxs-lookup"><span data-stu-id="0b7d0-228">Add the app personally or to a chat or team</span></span>
- <span data-ttu-id="0b7d0-229">앱의 bot에 메시지 보내기</span><span class="sxs-lookup"><span data-stu-id="0b7d0-229">Send messages to the app’s bot</span></span>
- <span data-ttu-id="0b7d0-230">처리 가능한 메시지 등의 정보를 앱으로 다시 보내는 단추 작업 수행</span><span class="sxs-lookup"><span data-stu-id="0b7d0-230">Perform button actions that send information back to the app, such as actionable messages</span></span>  
- <span data-ttu-id="0b7d0-231">앱의 탭 보기</span><span class="sxs-lookup"><span data-stu-id="0b7d0-231">View the app’s tab</span></span>
- <span data-ttu-id="0b7d0-232">알림을 받도록 커넥터 설정</span><span class="sxs-lookup"><span data-stu-id="0b7d0-232">Set up connectors to receive notifications</span></span>
- <span data-ttu-id="0b7d0-233">앱의 메시징 확장 사용</span><span class="sxs-lookup"><span data-stu-id="0b7d0-233">Use the app’s messaging extension</span></span>

<span data-ttu-id="0b7d0-234">레거시 포털은 조직 수준에서 앱을 제어할 수 있으며,이는 앱이 차단 되는 경우 조직의 모든 사용자에 대해 차단 됨을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-234">The legacy portal allowed controlling apps at the organization level, which means when an app is blocked, it's blocked for all users in the organization.</span></span> <span data-ttu-id="0b7d0-235">앱 권한 정책의 조직 전체 앱 설정은 정확히 동일한 방식으로 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-235">The org-wide app setting in app permission policies works exactly the same way.</span></span>

<span data-ttu-id="0b7d0-236">특정 사용자에 게 할당 된 앱 권한 정책의 경우, 봇 또는 커넥터 기능이 있는 앱이 허용 된 후 차단 되며,이 앱이 공유 컨텍스트의 일부 사용자 에게만 허용 되는 경우 해당 앱에 대 한 권한이 없는 그룹 채팅 또는 채널의 구성원  봇 또는 커넥터에 의해 게시 된 메시지 기록 및 메시지를 볼 수 있지만 대화형 작업할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0b7d0-236">For app permission policies assigned to specific users, if an app with bot or connector capability was allowed and then blocked, and if the app is then allowed only for some users in a shared context, members of a group chat or channel that don't have permission to that app can see the message history and messages that were posted by the bot or connector, but can't interact with it.</span></span>

 ## <a name="related-topics"></a><span data-ttu-id="0b7d0-237">관련 항목</span><span class="sxs-lookup"><span data-stu-id="0b7d0-237">Related topics</span></span>
- [<span data-ttu-id="0b7d0-238">Team에서 앱의 관리 설정</span><span class="sxs-lookup"><span data-stu-id="0b7d0-238">Admin settings for apps in Teams</span></span>](admin-settings.md)
