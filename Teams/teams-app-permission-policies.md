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
ms.openlocfilehash: 83a06357402b44c5c15932211e562e488c2a2d5a
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938477"
---
# <a name="manage-app-permission-policies-in-microsoft-teams"></a><span data-ttu-id="e71b7-103">Microsoft 팀에서 앱 권한 정책 관리</span><span class="sxs-lookup"><span data-stu-id="e71b7-103">Manage app permission policies in Microsoft Teams</span></span>

<span data-ttu-id="e71b7-104">관리자는 앱 권한 정책을 사용하여 조직의 Microsoft Teams 사용자가 사용할 수있는 앱을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e71b7-104">As an admin, you can use app permission policies to control what apps are available to Microsoft Teams users in your organization.</span></span> <span data-ttu-id="e71b7-105">Microsoft, 타사, 조직에서 게시 한 앱 또는 특정 앱을 모두 허용 하거나 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e71b7-105">You can allow or block all apps or specific apps published by Microsoft, third-parties, and your organization.</span></span> <span data-ttu-id="e71b7-106">앱을 차단하면 정책이 있는 사용자는 Teams 앱 스토어에서 goekd 앱을 설치할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e71b7-106">When you block an app, users who have the policy are unable to install it from the Teams app store.</span></span> <span data-ttu-id="e71b7-107">이러한 정책을 관리하려면 전역 관리자 또는 Teams 서비스 관리자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e71b7-107">You must be a global admin or Teams service admin to manage these policies.</span></span>

<span data-ttu-id="e71b7-108">Microsoft 팀 관리 센터에서 앱 권한 정책을 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="e71b7-108">You manage app permission policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="e71b7-109">전역 (조직 차원의 기본) 정책을 사용 하거나 사용자 지정 정책을 만들고 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e71b7-109">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="e71b7-110">사용자 지정 정책을 만들고 할당하지 않으면 조직의 사용자에게 전역 정책이 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e71b7-110">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="e71b7-111">정책을 편집 하거나 할당 한 후 변경 내용을 적용 하는 데 몇 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e71b7-111">After you edit or assign a policy, it can take a few hours for changes to take effect.</span></span>

![앱 사용 권한 정책의 스크린샷](media/app-permission-policies.png)

> [!NOTE]
> <span data-ttu-id="e71b7-113">조직 전체 앱 설정은 전역 정책 및 사용자가 만들고 할당 하는 사용자 지정 정책을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="e71b7-113">Org-wide app settings override the global policy and any custom policies that you create and assign to users.</span></span>

<span data-ttu-id="e71b7-114">조직이 이미 팀에 있는 경우 Microsoft 365 관리 센터의 **테 넌 트 전체 설정** 에서 구성한 앱 설정은 [앱 관리](manage-apps.md) 페이지의 조직 전체 앱 설정에 반영 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e71b7-114">If your organization is already on Teams, the app settings you configured in **Tenant-wide settings** in the Microsoft 365 admin center are reflected in org-wide app settings on the [Manage apps](manage-apps.md) page.</span></span> <span data-ttu-id="e71b7-115">팀을 처음 접하는 경우에는 기본적으로 모든 앱을 전역 정책에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e71b7-115">If you're new to Teams and just getting started, by default, all apps are allowed in the global policy.</span></span> <span data-ttu-id="e71b7-116">여기에는 Microsoft, 타사, 조직에서 게시 한 앱이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e71b7-116">This includes apps published by Microsoft, third-parties, and your organization.</span></span>

<span data-ttu-id="e71b7-117">예를 들어 모든 타사 앱을 차단 하 고 조직의 HR 팀에 대해 Microsoft의 특정 앱을 허용 하려는 경우를 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="e71b7-117">Say, for example, you want to block all third-party apps and allow specific apps from Microsoft for the HR team in your organization.</span></span> <span data-ttu-id="e71b7-118">먼저 [앱 관리](manage-apps.md) 페이지로 이동 하 여 HR 팀에 허용 하려는 앱이 조직 수준에서 허용 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e71b7-118">First, you would go to the [Manage apps](manage-apps.md) page and make sure that the apps that you want to allow for the HR team are allowed at the org level.</span></span> <span data-ttu-id="e71b7-119">그런 다음 HR 앱 권한 정책 이라는 사용자 지정 정책을 만들고, 원하는 앱을 차단 하 고 허용 하도록 설정한 다음 HR 팀에서 사용자에 게 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="e71b7-119">Then, create a custom policy named HR App Permission Policy, set it to block and allow the apps that you want, and assign it to users on the HR team.</span></span>

> [!NOTE]
> <span data-ttu-id="e71b7-120">Microsoft 365 정부-GCC 환경에서 팀을 배포한 경우 gcc에 고유한 타사 앱 설정에 대 한 자세한 내용은 [gcc 용 앱 권한 정책을](#app-permission-policies-for-gcc) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e71b7-120">If you deployed Teams in a Microsoft 365 Government - GCC environment, see [App permission policies for GCC](#app-permission-policies-for-gcc) to learn more about third-party app settings that are unique to GCC.</span></span>

## <a name="create-a-custom-app-permission-policy"></a><span data-ttu-id="e71b7-121">사용자 지정 앱 권한 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="e71b7-121">Create a custom app permission policy</span></span>

<span data-ttu-id="e71b7-122">조직의 다른 사용자 그룹에 대해 사용할 수 있는 앱을 제어 하려는 경우 하나 이상의 사용자 지정 앱 권한 정책을 만들고 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="e71b7-122">If you want to control the apps that are available for different groups of users in your organization, create and assign one or more custom app permission policies.</span></span> <span data-ttu-id="e71b7-123">앱이 Microsoft, 타사 또는 조직에 의해 게시 되었는지 여부에 따라 별도의 사용자 지정 정책을 만들고 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e71b7-123">You can create and assign separate custom policies based on whether apps are published by Microsoft, third-parties, or your organization.</span></span> <span data-ttu-id="e71b7-124">사용자 지정 정책을 만든 후에는 조직 전체 앱 설정에서 타사 앱을 사용 하지 않도록 설정한 경우 변경할 수 없다는 것을 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e71b7-124">It's important to know that after you create a custom policy, you can't change it if third-party apps are disabled in org-wide app settings.</span></span>

1. <span data-ttu-id="e71b7-125">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **팀 앱**  >  **권한 정책**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e71b7-125">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="e71b7-126">**추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e71b7-126">Click **Add**.</span></span> <br>
    <span data-ttu-id="e71b7-127">![새 앱 권한 정책의 스크린샷](media/app-permission-policies-new-policy.png)</span><span class="sxs-lookup"><span data-stu-id="e71b7-127">![Screenshot of new app permission policy](media/app-permission-policies-new-policy.png)</span></span>
3. <span data-ttu-id="e71b7-128">정책의 이름과 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="e71b7-128">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="e71b7-129">**Microsoft 앱**, 타사 **앱**및 **사용자 지정 앱**에서 다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e71b7-129">Under **Microsoft apps**, **Third-party apps**, and **Custom apps**, select one of the following:</span></span>

    - <span data-ttu-id="e71b7-130">**모든 앱 허용**</span><span class="sxs-lookup"><span data-stu-id="e71b7-130">**Allow all apps**</span></span>
    - <span data-ttu-id="e71b7-131">**특정 앱 허용 및 다른 사용자 모두 차단**</span><span class="sxs-lookup"><span data-stu-id="e71b7-131">**Allow specific apps and block all others**</span></span>
    - <span data-ttu-id="e71b7-132">**특정 앱을 차단 하 고 다른 사용자 허용**</span><span class="sxs-lookup"><span data-stu-id="e71b7-132">**Block specific apps and allow all others**</span></span>
    - <span data-ttu-id="e71b7-133">**모든 앱 차단**</span><span class="sxs-lookup"><span data-stu-id="e71b7-133">**Block all apps**</span></span>

5. <span data-ttu-id="e71b7-134">**특정 앱 허용 및 다른 사용자 차단**을 선택한 경우 허용 하려는 앱을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="e71b7-134">If you selected **Allow specific apps and block others**, add the apps that you want to allow:</span></span>

    1. <span data-ttu-id="e71b7-135">**앱 허용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e71b7-135">Select **Allow apps**.</span></span>
    1. <span data-ttu-id="e71b7-136">허용 하려는 앱을 검색 한 다음 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e71b7-136">Search for the apps that you want to allow, and then click **Add**.</span></span> <span data-ttu-id="e71b7-137">검색 결과가 앱 게시자 (**Microsoft 앱**, 타사 **앱**또는 **사용자 지정 앱**)로 필터링 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e71b7-137">The search results are filtered to the app publisher (**Microsoft apps**, **Third-party apps**, or **Custom apps**).</span></span>
    1. <span data-ttu-id="e71b7-138">앱 목록을 선택 했으면 **허용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e71b7-138">When you've chosen the list of apps, click **Allow**.</span></span> 

6. <span data-ttu-id="e71b7-139">마찬가지로 **특정 앱을 차단 하 고 다른 모든 사용자 허용**을 선택한 경우 차단 하려는 앱을 검색 하 여 추가한 다음 **차단을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e71b7-139">Similarly, if you selected **Block specific apps and allow all others**, search for and add the apps that you want to block, and then click **Block**.</span></span>
7. <span data-ttu-id="e71b7-140">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e71b7-140">Click **Save**.</span></span>

## <a name="edit-an-app-permission-policy"></a><span data-ttu-id="e71b7-141">앱 권한 정책 편집</span><span class="sxs-lookup"><span data-stu-id="e71b7-141">Edit an app permission policy</span></span>

<span data-ttu-id="e71b7-142">Microsoft 팀 관리 센터를 사용 하 여 글로벌 정책 및 만든 사용자 지정 정책을 비롯 한 정책을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e71b7-142">You can use the Microsoft Teams admin center to edit a policy, including the global policy and custom policies that you create.</span></span>

1. <span data-ttu-id="e71b7-143">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **팀 앱**  >  **권한 정책**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e71b7-143">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="e71b7-144">정책 이름 왼쪽을 클릭 하 여 정책을 선택한 다음 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e71b7-144">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="e71b7-145">여기서 원하는 대로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="e71b7-145">From here, make the changes that you want.</span></span> <span data-ttu-id="e71b7-146">앱 게시자에 따라 설정을 관리 하 고 허용/차단 설정에 따라 앱을 추가 및 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e71b7-146">You can manage settings based on the app publisher and add and remove apps based on the allow/block setting.</span></span>
4. <span data-ttu-id="e71b7-147">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e71b7-147">Click **Save**.</span></span>

## <a name="assign-a-custom-app-permission-policy-to-users"></a><span data-ttu-id="e71b7-148">사용자에 게 사용자 지정 앱 권한 정책 할당</span><span class="sxs-lookup"><span data-stu-id="e71b7-148">Assign a custom app permission policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="app-permission-policies-for-gcc"></a><span data-ttu-id="e71b7-149">GCC 용 앱 권한 정책</span><span class="sxs-lookup"><span data-stu-id="e71b7-149">App permission policies for GCC</span></span>

<span data-ttu-id="e71b7-150">팀의 Microsoft 365 정부-GCC 배포에서 GCC에 고유한 제 3 자 앱 설정에 대 한 다음 사항을 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e71b7-150">In a Microsoft 365 Government - GCC deployment of Teams, it's important to know the following about third-party app settings, which are unique to GCC.</span></span>

<span data-ttu-id="e71b7-151">GCC에서는 모든 타사 앱이 기본적으로 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e71b7-151">In GCC, all third-party apps are blocked by default.</span></span> <span data-ttu-id="e71b7-152">또한 Microsoft 팀 관리 센터의 앱 사용 권한 정책 페이지에서 타사 앱을 관리 하는 방법에 대 한 참고 사항을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e71b7-152">Additionally, you'll see the following note about managing third-party apps on the app permission policies page in the Microsoft Teams admin center.</span></span>

![GCC의 앱 사용 권한 정책 스크린샷](media/app-permission-policies-gcc.png)

<span data-ttu-id="e71b7-154">조직의 사용자 또는 사용자 집합에 대해 타사 앱을 사용 하도록 설정 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e71b7-154">To enable a third-party app for a user or a set of users in your organization, do the following:</span></span>

1. <span data-ttu-id="e71b7-155">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **팀 앱**으로 이동 하  >  **Manage apps**고 앱 목록에서 사용자 집합을 허용 하려는 타사 앱이 조직 수준에서 **차단** 되도록 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e71b7-155">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**, and then in the list of apps, confirm that the third-party app that you want to allow for a set of users is set to **Blocked** at the org level.</span></span>

2. <span data-ttu-id="e71b7-156">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **팀 앱**  >  **권한 정책**으로 이동한 다음, 전역 정책을 편집 하 여 타사 앱을 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="e71b7-156">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**, and then edit the global policy to block the third-party app.</span></span> <span data-ttu-id="e71b7-157">실행할 작업:</span><span class="sxs-lookup"><span data-stu-id="e71b7-157">To do this:</span></span>
    1. <span data-ttu-id="e71b7-158">앱 권한 정책 페이지에서 **전역 (조직 전체 기본값)** 을 클릭 한 다음 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e71b7-158">On the App permission policies page, click **Global (Org-wide default)**, and then click **Edit**.</span></span>
    2. <span data-ttu-id="e71b7-159">**타사 앱**에서 **특정 앱 차단을 선택 하 고 다른 모든 사용자를 허용**하 고 앱을 추가한 다음 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e71b7-159">Under **Third-party apps**, select **Block specific apps and allow all others**, add the app, and then click **Save**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e71b7-160">조직 수준에서 앱을 허용 하기 위해 다음 단계로 이동 하기 전에이 작업을 수행 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e71b7-160">It's important to do this before you go to the next step to allow the app at the org level.</span></span> <span data-ttu-id="e71b7-161">이는 타사 앱이 전역 앱 권한 정책에서 차단 되지 않은 경우 전역 정책이 적용 되는 모든 사용자가 조직 수준에서 허용 하는 경우 타사 앱에 액세스할 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="e71b7-161">This is because if the third-party app isn't blocked in the global app permission policy, all users that the global policy applies to will be able to access the third-party app when you allow it at the org level.</span></span>

3. <span data-ttu-id="e71b7-162">조직 수준에서 타사 앱을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e71b7-162">Allow the third-party app at the org level.</span></span> <span data-ttu-id="e71b7-163">이렇게 하려면 왼쪽 탐색 창에서 **팀 앱**앱  >  **관리**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e71b7-163">To do this, in the left navigation, go to **Teams apps** > **Manage apps**.</span></span> <span data-ttu-id="e71b7-164">앱 목록에서 앱 이름 왼쪽에 있는을 클릭 하 여 앱을 선택한 다음 **허용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e71b7-164">In the list of apps, click to the left of the app name to select the app, and then select **Allow**.</span></span>
4. <span data-ttu-id="e71b7-165">앱을 허용 하는 [사용자 지정 앱 권한 정책을 만든](#create-a-custom-app-permission-policy) 다음 정책을 원하는 사용자에 게 [할당](#assign-a-custom-app-permission-policy-to-users) 합니다.</span><span class="sxs-lookup"><span data-stu-id="e71b7-165">[Create a custom app permission policy](#create-a-custom-app-permission-policy) to allow the app, and then [assign the policy](#assign-a-custom-app-permission-policy-to-users) to the users you want.</span></span>

## <a name="faq"></a><span data-ttu-id="e71b7-166">FAQ</span><span class="sxs-lookup"><span data-stu-id="e71b7-166">FAQ</span></span>

### <a name="working-with-app-permission-policies"></a><span data-ttu-id="e71b7-167">앱 권한 정책 사용</span><span class="sxs-lookup"><span data-stu-id="e71b7-167">Working with app permission policies</span></span>

#### <a name="what-app-interactions-do-permission-policies-affect"></a><span data-ttu-id="e71b7-168">권한 정책의 영향을 받는 앱 조작</span><span class="sxs-lookup"><span data-stu-id="e71b7-168">What app interactions do permission policies affect?</span></span>
<span data-ttu-id="e71b7-169">권한 정책은 최종 사용자의 설치, 검색, 조작 등을 제어 하 여 앱 사용을 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="e71b7-169">Permission policies govern app usage by controlling installation, discovery, and interaction for end users.</span></span> <span data-ttu-id="e71b7-170">관리자는 할당 된 권한 정책에 관계 없이 Microsoft 팀 관리 센터에서 앱을 계속 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e71b7-170">Admins can still manage apps in the Microsoft Teams admin center regardless of the permission policies assigned to them.</span></span>

#### <a name="can-i-control-line-of-business-lob-apps"></a><span data-ttu-id="e71b7-171">LOB (기간 업무) 앱을 제어할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="e71b7-171">Can I control line of business (LOB) apps?</span></span>
<span data-ttu-id="e71b7-172">예, 앱 사용 권한 정책을 사용 하 여 사용자 지정 (LOB) 앱의 출시 및 배포를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e71b7-172">Yes, you can use app permission policies to control the rollout and distribution of custom (LOB) apps.</span></span> <span data-ttu-id="e71b7-173">사용자 지정 정책을 만들거나 전역 정책을 편집 하 여 조직의 요구 사항에 따라 사용자 지정 앱을 허용 하거나 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e71b7-173">You can create a custom policy or edit the global policy to allow or block custom apps based on the needs of your organization.</span></span>

#### <a name="how-do-app-permission-policies-relate-to-pinned-apps-and-app-setup-policies"></a><span data-ttu-id="e71b7-174">앱 권한 정책은 고정 된 앱 및 앱 설정 정책과 어떻게 관련 되나요?</span><span class="sxs-lookup"><span data-stu-id="e71b7-174">How do app permission policies relate to pinned apps and app setup policies?</span></span>

<span data-ttu-id="e71b7-175">앱 설치 정책은 앱 권한 정책과 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e71b7-175">You can use app setup policies together with app permission policies.</span></span> <span data-ttu-id="e71b7-176">미리 고정 된 앱은 사용자의 활성화 된 앱 집합에서 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e71b7-176">Pre-pinned apps are selected from the set of enabled apps for a user.</span></span> <span data-ttu-id="e71b7-177">또한 사용자에 게 앱 설정 정책에서 앱을 차단 하는 앱 권한 정책이 있는 경우 해당 앱은 팀에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e71b7-177">Additionally, if a user has an app permission policy that blocks an app in their app setup policy, that app won't appear in Teams.</span></span>

#### <a name="can-i-use-app-permission-policies-to-restrict-uploading-custom-apps"></a><span data-ttu-id="e71b7-178">앱 권한 정책을 사용 하 여 사용자 지정 앱 업로드를 제한할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="e71b7-178">Can I use app permission policies to restrict uploading custom apps?</span></span>

<span data-ttu-id="e71b7-179">**앱 관리** 페이지 또는 앱 설정 정책에서 조직 전체 설정을 사용 하 여 조직의 사용자 지정 앱 업로드를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e71b7-179">You can use org-wide settings on the **Manage apps** page, or app setup policies to restrict uploading custom apps for your organization.</span></span>  

<span data-ttu-id="e71b7-180">특정 사용자가 사용자 지정 앱을 업로드 하지 못하도록 제한 하려면 사용자 지정 앱 정책을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e71b7-180">To restrict specific users from uploading custom apps, use custom app policies.</span></span> <span data-ttu-id="e71b7-181">자세히 알아보려면 [팀에서 사용자 지정 앱 정책 및 설정 관리](teams-custom-app-policies-and-settings.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e71b7-181">To learn more, see [Manage custom app policies and settings in Teams](teams-custom-app-policies-and-settings.md).</span></span>

#### <a name="does-blocking-an-app-apply-to-teams-mobile-clients"></a><span data-ttu-id="e71b7-182">앱이 팀 모바일 클라이언트에 적용 되는 것을 차단 합니까?</span><span class="sxs-lookup"><span data-stu-id="e71b7-182">Does blocking an app apply to Teams mobile clients?</span></span>

<span data-ttu-id="e71b7-183">예, 앱을 차단 하면 모든 팀 클라이언트에서 앱이 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e71b7-183">Yes, when you block an app, that app is blocked across all Teams clients.</span></span>  

### <a name="user-experience"></a><span data-ttu-id="e71b7-184">사용자 환경</span><span class="sxs-lookup"><span data-stu-id="e71b7-184">User experience</span></span>

#### <a name="what-does-a-user-experience-when-an-app-is-blocked"></a><span data-ttu-id="e71b7-185">앱이 차단 되는 경우 사용자 환경</span><span class="sxs-lookup"><span data-stu-id="e71b7-185">What does a user experience when an app is blocked?</span></span>

<span data-ttu-id="e71b7-186">사용자는 차단 된 앱 또는 인공 지능, 탭, 메시징 확장과 같은 기능을 조작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e71b7-186">Users can't interact with a blocked app or its capabilities, such bots, tabs, and messaging extensions.</span></span> <span data-ttu-id="e71b7-187">팀 또는 그룹 채팅 같은 공유 컨텍스트에서이는 해당 컨텍스트의 모든 참가자에 게 메시지를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e71b7-187">In a shared context, such as a team or group chat, bots can still send messages to all participants of that context.</span></span> <span data-ttu-id="e71b7-188">앱이 차단 되 면 팀에서 사용자에 게 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e71b7-188">Teams indicates to the user when an app is blocked.</span></span>

<span data-ttu-id="e71b7-189">예를 들어 앱이 차단 되 면 사용자는 다음을 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e71b7-189">For example, when an app is blocked, users can't do any of the following:</span></span>

- <span data-ttu-id="e71b7-190">개인적으로 또는 채팅 또는 팀에 앱 추가</span><span class="sxs-lookup"><span data-stu-id="e71b7-190">Add the app personally or to a chat or team</span></span>
- <span data-ttu-id="e71b7-191">앱의 bot에 메시지 보내기</span><span class="sxs-lookup"><span data-stu-id="e71b7-191">Send messages to the app’s bot</span></span>
- <span data-ttu-id="e71b7-192">처리 가능한 메시지 등의 정보를 앱으로 다시 보내는 단추 작업 수행</span><span class="sxs-lookup"><span data-stu-id="e71b7-192">Perform button actions that send information back to the app, such as actionable messages</span></span>  
- <span data-ttu-id="e71b7-193">앱의 탭 보기</span><span class="sxs-lookup"><span data-stu-id="e71b7-193">View the app’s tab</span></span>
- <span data-ttu-id="e71b7-194">알림을 받도록 커넥터 설정</span><span class="sxs-lookup"><span data-stu-id="e71b7-194">Set up connectors to receive notifications</span></span>
- <span data-ttu-id="e71b7-195">앱의 메시징 확장 사용</span><span class="sxs-lookup"><span data-stu-id="e71b7-195">Use the app’s messaging extension</span></span>

<span data-ttu-id="e71b7-196">레거시 포털은 조직 수준에서 앱을 제어할 수 있으며,이는 앱이 차단 되는 경우 조직의 모든 사용자에 대해 차단 됨을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="e71b7-196">The legacy portal allowed controlling apps at the organization level, which means when an app is blocked, it's blocked for all users in the organization.</span></span> <span data-ttu-id="e71b7-197">[앱 관리](manage-apps.md) 페이지에서 앱을 차단 하는 방법은 동일 하 게 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e71b7-197">Blocking an app on the [Manage apps](manage-apps.md) page works exactly the same way.</span></span>

<span data-ttu-id="e71b7-198">특정 사용자에 게 할당 된 앱 권한 정책의 경우, 봇 또는 커넥터 기능이 있는 앱이 허용 된 후 차단 되며,이 앱이 공유 컨텍스트의 일부 사용자 에게만 허용 되는 경우 해당 앱에 대 한 권한이 없는 그룹 채팅 또는 채널의 구성원은 봇 또는 커넥터에 의해 게시 된 메시지 기록 및 메시지를 볼 수 있습니다. 있지만 대화형 작업을 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e71b7-198">For app permission policies assigned to specific users, if an app with bot or connector capability was allowed and then blocked, and if the app is then allowed only for some users in a shared context, members of a group chat or channel that don't have permission to that app can see the message history and messages that were posted by the bot or connector, but can't interact with it.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e71b7-199">관련 항목</span><span class="sxs-lookup"><span data-stu-id="e71b7-199">Related topics</span></span>

[<span data-ttu-id="e71b7-200">Team에서 앱의 관리 설정</span><span class="sxs-lookup"><span data-stu-id="e71b7-200">Admin settings for apps in Teams</span></span>](admin-settings.md)

[<span data-ttu-id="e71b7-201">팀에서 사용자에 게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="e71b7-201">Assign policies to your users in Teams</span></span>](assign-policies.md)
