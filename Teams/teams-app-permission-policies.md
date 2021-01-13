---
title: Microsoft Teams에서 앱 사용 권한 정책 관리
author: cichur
ms.author: v-cichur
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
description: Microsoft Teams의 앱 사용 권한 정책 및 이를 사용하여 조직의 사용자가 사용할 수 있는 앱을 제어하는 방법에 대해 자세히 배워야 합니다.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.overview
- ms.teamsadmincenter.appsetuppolicies.addpinnedapp.permissions
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: aa11b21405079ab26bf1fa9572eb203560c4e461
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802498"
---
# <a name="manage-app-permission-policies-in-microsoft-teams"></a><span data-ttu-id="a81cb-103">Microsoft Teams에서 앱 사용 권한 정책 관리</span><span class="sxs-lookup"><span data-stu-id="a81cb-103">Manage app permission policies in Microsoft Teams</span></span>

<span data-ttu-id="a81cb-104">관리자는 앱 권한 정책을 사용하여 조직의 Microsoft Teams 사용자가 사용할 수있는 앱을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a81cb-104">As an admin, you can use app permission policies to control what apps are available to Microsoft Teams users in your organization.</span></span> <span data-ttu-id="a81cb-105">Microsoft, 타사 및 조직에서 게시한 모든 앱 또는 특정 앱을 허용하거나 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a81cb-105">You can allow or block all apps or specific apps published by Microsoft, third-parties, and your organization.</span></span> <span data-ttu-id="a81cb-106">앱을 차단하면 정책이 있는 사용자는 Teams 앱 스토어에서 goekd 앱을 설치할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a81cb-106">When you block an app, users who have the policy are unable to install it from the Teams app store.</span></span> <span data-ttu-id="a81cb-107">이러한 정책을 관리하려면 전역 관리자 또는 Teams 서비스 관리자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a81cb-107">You must be a global admin or Teams service admin to manage these policies.</span></span>

<span data-ttu-id="a81cb-108">Microsoft Teams 관리 센터에서 앱 사용 권한 정책을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="a81cb-108">You manage app permission policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="a81cb-109">전역(전체 기본) 정책을 사용하거나 사용자 지정 정책을 만들고 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a81cb-109">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="a81cb-110">사용자 지정 정책을 만들고 할당하지 않으면 조직의 사용자에게 전역 정책이 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a81cb-110">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="a81cb-111">정책을 편집하거나 할당한 후 변경 내용을 적용하는 데 몇 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a81cb-111">After you edit or assign a policy, it can take a few hours for changes to take effect.</span></span>

![앱 사용 권한 정책 스크린샷](media/app-permission-policies.png)

> [!NOTE]
> <span data-ttu-id="a81cb-113">전체 앱 설정은 사용자가 만들고 사용자에게 할당하는 전역 정책 및 모든 사용자 지정 정책을 다시 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a81cb-113">Org-wide app settings override the global policy and any custom policies that you create and assign to users.</span></span>

<span data-ttu-id="a81cb-114">조직이 이미 Teams에 있는 경우 Microsoft 365 관리 센터의 테넌트 전체 설정에서 구성한 앱 설정이 앱 관리 페이지의 조직 전체 앱 설정에 [반영됩니다.](manage-apps.md) </span><span class="sxs-lookup"><span data-stu-id="a81cb-114">If your organization is already on Teams, the app settings you configured in **Tenant-wide settings** in the Microsoft 365 admin center are reflected in org-wide app settings on the [Manage apps](manage-apps.md) page.</span></span> <span data-ttu-id="a81cb-115">Teams를 시작한 경우 기본적으로 모든 앱이 전역 정책에서 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a81cb-115">If you're new to Teams and just getting started, by default, all apps are allowed in the global policy.</span></span> <span data-ttu-id="a81cb-116">여기에는 Microsoft, 타사 및 조직에서 게시한 앱이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a81cb-116">This includes apps published by Microsoft, third-parties, and your organization.</span></span>

<span data-ttu-id="a81cb-117">예를 들어 모든 타사 앱을 차단하고 조직의 HR 팀에 대해 Microsoft의 특정 앱을 허용하려는 경우를 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a81cb-117">Say, for example, you want to block all third-party apps and allow specific apps from Microsoft for the HR team in your organization.</span></span> <span data-ttu-id="a81cb-118">먼저 앱 관리 페이지로 이동하여 HR 팀에 허용하려는 앱이 구성 수준에서 허용되는지 확인하게 됩니다. [](manage-apps.md)</span><span class="sxs-lookup"><span data-stu-id="a81cb-118">First, you would go to the [Manage apps](manage-apps.md) page and make sure that the apps that you want to allow for the HR team are allowed at the org level.</span></span> <span data-ttu-id="a81cb-119">그런 다음, HR 앱 사용 권한 정책이라는 사용자 지정 정책을 만들고, 원하는 앱을 차단 및 허용하도록 설정하고, HR 팀의 사용자에게 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="a81cb-119">Then, create a custom policy named HR App Permission Policy, set it to block and allow the apps that you want, and assign it to users on the HR team.</span></span>

> [!NOTE]
> <span data-ttu-id="a81cb-120">Microsoft 365 GCC(Government Community Cloud) 환경에 Teams를 배포한 경우 GCC에 고유한 타사 앱 설정에 대한 자세한 내용은 [Microsoft 365 Government의](#manage-org-wide-app-settings-for-microsoft-365-government) 전체 앱 설정 관리를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a81cb-120">If you deployed Teams in a Microsoft 365 Government Community Cloud (GCC) environment, see [Manage org-wide app settings for Microsoft 365 Government](#manage-org-wide-app-settings-for-microsoft-365-government) to learn more about third-party app settings that are unique to GCC.</span></span>

## <a name="create-a-custom-app-permission-policy"></a><span data-ttu-id="a81cb-121">사용자 지정 앱 사용 권한 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="a81cb-121">Create a custom app permission policy</span></span>

<span data-ttu-id="a81cb-122">조직의 다른 사용자 그룹에 사용할 수 있는 앱을 제어하려면 하나 이상의 사용자 지정 앱 사용 권한 정책을 만들고 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="a81cb-122">If you want to control the apps that are available for different groups of users in your organization, create and assign one or more custom app permission policies.</span></span> <span data-ttu-id="a81cb-123">Microsoft, 타사 또는 조직에서 앱을 게시하는지 여부에 따라 별도의 사용자 지정 정책을 만들고 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a81cb-123">You can create and assign separate custom policies based on whether apps are published by Microsoft, third-parties, or your organization.</span></span> <span data-ttu-id="a81cb-124">사용자 지정 정책을 만든 후 전체 앱 설정에서 타사 앱을 사용하지 않도록 설정한 경우 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a81cb-124">It's important to know that after you create a custom policy, you can't change it if third-party apps are disabled in org-wide app settings.</span></span>

1. <span data-ttu-id="a81cb-125">Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 Teams 앱 사용 **권한**  >  **정책으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="a81cb-125">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="a81cb-126">추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="a81cb-126">Click **Add**.</span></span> <br>
    <span data-ttu-id="a81cb-127">![새 앱 사용 권한 정책의 스크린샷](media/app-permission-policies-new-policy.png)</span><span class="sxs-lookup"><span data-stu-id="a81cb-127">![Screenshot of new app permission policy](media/app-permission-policies-new-policy.png)</span></span>
3. <span data-ttu-id="a81cb-128">정책의 이름과 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a81cb-128">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="a81cb-129">**Microsoft 앱,** **타사** 앱 및 사용자 지정 **앱 아래에서** 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a81cb-129">Under **Microsoft apps**, **Third-party apps**, and **Custom apps**, select one of the following:</span></span>

    - <span data-ttu-id="a81cb-130">**모든 앱 허용**</span><span class="sxs-lookup"><span data-stu-id="a81cb-130">**Allow all apps**</span></span>
    - <span data-ttu-id="a81cb-131">**특정 앱 허용 및 다른 모든 앱 차단**</span><span class="sxs-lookup"><span data-stu-id="a81cb-131">**Allow specific apps and block all others**</span></span>
    - <span data-ttu-id="a81cb-132">**특정 앱 차단 및 다른 모든 앱 허용**</span><span class="sxs-lookup"><span data-stu-id="a81cb-132">**Block specific apps and allow all others**</span></span>
    - <span data-ttu-id="a81cb-133">**모든 앱 차단**</span><span class="sxs-lookup"><span data-stu-id="a81cb-133">**Block all apps**</span></span>

5. <span data-ttu-id="a81cb-134">특정 앱 **허용을 선택한 경우** 다른 앱을 차단한 경우 허용하려는 앱을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a81cb-134">If you selected **Allow specific apps and block others**, add the apps that you want to allow:</span></span>

    1. <span data-ttu-id="a81cb-135">앱 **허용을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="a81cb-135">Select **Allow apps**.</span></span>
    1. <span data-ttu-id="a81cb-136">허용할 앱을 검색한 다음 추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="a81cb-136">Search for the apps that you want to allow, and then click **Add**.</span></span> <span data-ttu-id="a81cb-137">검색 결과는 앱 게시자(Microsoft **앱,** 타사 앱 또는 사용자 지정 앱)로 **필터링됩니다.**</span><span class="sxs-lookup"><span data-stu-id="a81cb-137">The search results are filtered to the app publisher (**Microsoft apps**, **Third-party apps**, or **Custom apps**).</span></span>
    1. <span data-ttu-id="a81cb-138">앱 목록을 선택한 경우 허용을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="a81cb-138">When you've chosen the list of apps, click **Allow**.</span></span> 

6. <span data-ttu-id="a81cb-139">마찬가지로 특정 앱 차단을 선택한 경우 다른 모든 앱을 허용한 경우 차단할 앱을 검색하여 추가한 다음 차단을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="a81cb-139">Similarly, if you selected **Block specific apps and allow all others**, search for and add the apps that you want to block, and then click **Block**.</span></span>
7. <span data-ttu-id="a81cb-140">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a81cb-140">Click **Save**.</span></span>

## <a name="edit-an-app-permission-policy"></a><span data-ttu-id="a81cb-141">앱 사용 권한 정책 편집</span><span class="sxs-lookup"><span data-stu-id="a81cb-141">Edit an app permission policy</span></span>

<span data-ttu-id="a81cb-142">Microsoft Teams 관리 센터를 사용하여 만든 전역 정책 및 사용자 지정 정책을 포함하여 정책을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a81cb-142">You can use the Microsoft Teams admin center to edit a policy, including the global policy and custom policies that you create.</span></span>

1. <span data-ttu-id="a81cb-143">Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 Teams 앱 사용 **권한**  >  **정책으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="a81cb-143">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="a81cb-144">정책 이름 왼쪽을 클릭하여 정책을 선택한 다음 편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="a81cb-144">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="a81cb-145">여기에서 원하는 내용을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="a81cb-145">From here, make the changes that you want.</span></span> <span data-ttu-id="a81cb-146">앱 게시자를 기반으로 설정을 관리하고 허용/차단 설정에 따라 앱을 추가 및 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a81cb-146">You can manage settings based on the app publisher and add and remove apps based on the allow/block setting.</span></span>
4. <span data-ttu-id="a81cb-147">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a81cb-147">Click **Save**.</span></span>

## <a name="assign-a-custom-app-permission-policy-to-users"></a><span data-ttu-id="a81cb-148">사용자에게 사용자 지정 앱 사용 권한 정책 할당</span><span class="sxs-lookup"><span data-stu-id="a81cb-148">Assign a custom app permission policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="manage-org-wide-app-settings-for-microsoft-365-government"></a><span data-ttu-id="a81cb-149">Microsoft 365 Government에 대한 전체 앱 설정 관리</span><span class="sxs-lookup"><span data-stu-id="a81cb-149">Manage org-wide app settings for Microsoft 365 Government</span></span>  

<span data-ttu-id="a81cb-150">Microsoft 365 Government - Teams의 GCC 배포에서는 GCC에 고유한 타사 앱 설정에 대해 다음을 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a81cb-150">In a Microsoft 365 Government - GCC deployment of Teams, it's important to know the following about third-party app settings, which are unique to GCC.</span></span>

<span data-ttu-id="a81cb-151">GCC에서 모든 타사 앱은 기본적으로 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="a81cb-151">In GCC, all third-party apps are blocked by default.</span></span> <span data-ttu-id="a81cb-152">또한 Microsoft Teams 관리 센터의 앱 사용 권한 정책 페이지에서 타사 앱 관리에 대한 다음 메모가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a81cb-152">Additionally, you'll see the following note about managing third-party apps on the app permission policies page in the Microsoft Teams admin center.</span></span>

![GCC의 앱 사용 권한 정책 스크린샷](media/app-permission-policies-gcc.png)

<span data-ttu-id="a81cb-154">전체 앱 설정을 사용하여 사용자가 타사 앱을 설치할 수 있는지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="a81cb-154">Use org-wide app settings to control whether users can install third-party apps.</span></span> <span data-ttu-id="a81cb-155">전체 앱 설정은 모든 사용자에 대한 동작을 관리하고 사용자에게 할당된 다른 모든 앱 사용 권한 정책을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="a81cb-155">Org-wide app settings govern the behavior for all users and override any other app permission policies assigned to users.</span></span> <span data-ttu-id="a81cb-156">악의적 또는 문제가 있는 앱을 제어하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a81cb-156">You can use them to control malicious or problematic apps.</span></span>

1. <span data-ttu-id="a81cb-157">사용 권한 **정책 페이지에서** 전체 앱 설정을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="a81cb-157">On the **Permission policies** page, select **Org-wide app settings**.</span></span> <span data-ttu-id="a81cb-158">그런 다음 패널에서 원하는 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a81cb-158">You can then configure the settings you want in the panel.</span></span>

    ![전체 앱 설정 스크린샷](media/app-permission-policies-gcc-org-wide.png)
    
2. <span data-ttu-id="a81cb-160">타사 **앱에서** 다음 설정을 끄거나 켜 타사 앱에 대한 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="a81cb-160">Under **Third-party apps**, turn off or turn on these settings to control access to third-party apps:</span></span>

    - <span data-ttu-id="a81cb-161">**타사 앱 허용:** 사용자가 타사 앱을 사용할 수 있는지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="a81cb-161">**Allow third-party apps**: This controls whether users can use third-party apps.</span></span> <span data-ttu-id="a81cb-162">이 설정을 해제하면 사용자가 타사 앱을 설치하거나 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a81cb-162">If you turn off this setting, your users won't be able to install or use any third-party apps.</span></span> <span data-ttu-id="a81cb-163">Teams의 Microsoft 365 Government - GCC 배포에서 이 설정은 기본적으로 해제되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a81cb-163">In a Microsoft 365 Government - GCC deployment of Teams, this setting is off by default.</span></span>
    - <span data-ttu-id="a81cb-164">**기본적으로** 스토어에 게시된 새 타사 앱을 허용합니다. Teams 앱 스토어에 게시된 새 타사 앱을 Teams에서 자동으로 사용할 수 있는지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="a81cb-164">**Allow any new third-party apps published to the store by default**: This controls whether new third-party apps that are published to the Teams app store become automatically available in Teams.</span></span> <span data-ttu-id="a81cb-165">타사 앱을 허용하는 경우 이 옵션을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a81cb-165">You can only set this option if you allow third-party apps.</span></span>

3. <span data-ttu-id="a81cb-166">차단된 **앱 아래에서** 조직 전체에서 차단하려는 앱을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a81cb-166">Under **Blocked apps**, add the apps you want to block across your organization.</span></span> <span data-ttu-id="a81cb-167">Microsoft 365 Government - Teams의 GCC 배포에서는 기본적으로 모든 타사 앱이 이 목록에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="a81cb-167">In a Microsoft 365 Government - GCC deployment of Teams, all third-party apps are added to this list by default.</span></span> <span data-ttu-id="a81cb-168">조직에서 허용하려는 타사 앱의 경우 차단된 앱 목록에서 앱을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="a81cb-168">For any third-party app you want to allow in your organization, remove the app from this blocked apps list.</span></span> <span data-ttu-id="a81cb-169">앱 전체를 차단하면 앱 사용 권한 정책에 허용되는지 여부에 관계없이 모든 사용자에 대해 앱이 자동으로 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="a81cb-169">When you block an app org-wide, the app is automatically blocked for all your users, regardless of whether it's allowed in any app permission policies</span></span>
4. <span data-ttu-id="a81cb-170">전체 **앱** 설정에 대해 저장을 클릭하여 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="a81cb-170">Click **Save** for org-wide app settings to take effect.</span></span>

<span data-ttu-id="a81cb-171">앞에서 설명한 대로 타사 앱을 허용하기 위해 전역(전체 기본) 정책을 편집 및 사용하거나 사용자 지정 정책을 만들고 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a81cb-171">As mentioned earlier, to allow third-party apps, you can either edit and use the global (Org-wide default) policy or create and assign custom policies.</span></span>

## <a name="faq"></a><span data-ttu-id="a81cb-172">FAQ</span><span class="sxs-lookup"><span data-stu-id="a81cb-172">FAQ</span></span>

### <a name="working-with-app-permission-policies"></a><span data-ttu-id="a81cb-173">앱 사용 권한 정책 작업</span><span class="sxs-lookup"><span data-stu-id="a81cb-173">Working with app permission policies</span></span>

#### <a name="what-app-interactions-do-permission-policies-affect"></a><span data-ttu-id="a81cb-174">권한 정책은 어떤 앱 상호 작용에 영향을 주나요?</span><span class="sxs-lookup"><span data-stu-id="a81cb-174">What app interactions do permission policies affect?</span></span>
<span data-ttu-id="a81cb-175">사용 권한 정책은 최종 사용자에 대한 설치, 검색 및 상호 작용을 제어하여 앱 사용량을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="a81cb-175">Permission policies govern app usage by controlling installation, discovery, and interaction for end users.</span></span> <span data-ttu-id="a81cb-176">관리자는 할당된 사용 권한 정책에 관계없이 Microsoft Teams 관리 센터에서 앱을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a81cb-176">Admins can still manage apps in the Microsoft Teams admin center regardless of the permission policies assigned to them.</span></span>

#### <a name="can-i-control-line-of-business-lob-apps"></a><span data-ttu-id="a81cb-177">LOB(사업부) 앱을 제어할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="a81cb-177">Can I control line of business (LOB) apps?</span></span>
<span data-ttu-id="a81cb-178">예, 앱 사용 권한 정책을 사용하여 사용자 지정(LOB) 앱의 롤아웃 및 배포를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a81cb-178">Yes, you can use app permission policies to control the rollout and distribution of custom (LOB) apps.</span></span> <span data-ttu-id="a81cb-179">조직의 요구에 따라 사용자 지정 앱을 허용하거나 차단하도록 사용자 지정 정책을 만들거나 전역 정책을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a81cb-179">You can create a custom policy or edit the global policy to allow or block custom apps based on the needs of your organization.</span></span>

#### <a name="how-do-app-permission-policies-relate-to-pinned-apps-and-app-setup-policies"></a><span data-ttu-id="a81cb-180">앱 사용 권한 정책은 고정된 앱 및 앱 설정 정책과 어떻게 관련이 있나요?</span><span class="sxs-lookup"><span data-stu-id="a81cb-180">How do app permission policies relate to pinned apps and app setup policies?</span></span>

<span data-ttu-id="a81cb-181">앱 사용 권한 정책과 함께 앱 설정 정책을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a81cb-181">You can use app setup policies together with app permission policies.</span></span> <span data-ttu-id="a81cb-182">미리 고정된 앱은 사용자에 대해 활성화된 앱 집합에서 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="a81cb-182">Pre-pinned apps are selected from the set of enabled apps for a user.</span></span> <span data-ttu-id="a81cb-183">또한 사용자에게 앱 설정 정책에서 앱을 차단하는 앱 사용 권한 정책이 있는 경우 해당 앱이 Teams에 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a81cb-183">Additionally, if a user has an app permission policy that blocks an app in their app setup policy, that app won't appear in Teams.</span></span>

#### <a name="can-i-use-app-permission-policies-to-restrict-uploading-custom-apps"></a><span data-ttu-id="a81cb-184">앱 사용 권한 정책을 사용하여 사용자 지정 앱 업로드를 제한할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="a81cb-184">Can I use app permission policies to restrict uploading custom apps?</span></span>

<span data-ttu-id="a81cb-185">앱 관리 페이지에서 조직 전체 설정을 사용할 수 **있습니다.** 또는 앱 설정 정책을 사용하여 조직에 대한 사용자 지정 앱 업로드를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a81cb-185">You can use org-wide settings on the **Manage apps** page, or app setup policies to restrict uploading custom apps for your organization.</span></span>  

<span data-ttu-id="a81cb-186">특정 사용자를 사용자 지정 앱 업로드를 제한하려면 사용자 지정 앱 정책을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="a81cb-186">To restrict specific users from uploading custom apps, use custom app policies.</span></span> <span data-ttu-id="a81cb-187">자세한 내용은 Teams에서 사용자 [지정 앱 정책 및 설정 관리를 참조하세요.](teams-custom-app-policies-and-settings.md)</span><span class="sxs-lookup"><span data-stu-id="a81cb-187">To learn more, see [Manage custom app policies and settings in Teams](teams-custom-app-policies-and-settings.md).</span></span>

#### <a name="does-blocking-an-app-apply-to-teams-mobile-clients"></a><span data-ttu-id="a81cb-188">앱 차단이 Teams 모바일 클라이언트에 적용하나요?</span><span class="sxs-lookup"><span data-stu-id="a81cb-188">Does blocking an app apply to Teams mobile clients?</span></span>

<span data-ttu-id="a81cb-189">예, 앱을 차단하면 모든 Teams 클라이언트에서 해당 앱이 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="a81cb-189">Yes, when you block an app, that app is blocked across all Teams clients.</span></span>  

### <a name="user-experience"></a><span data-ttu-id="a81cb-190">사용자 환경</span><span class="sxs-lookup"><span data-stu-id="a81cb-190">User experience</span></span>

#### <a name="what-does-a-user-experience-when-an-app-is-blocked"></a><span data-ttu-id="a81cb-191">앱이 차단된 경우 사용자 환경은 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="a81cb-191">What does a user experience when an app is blocked?</span></span>

<span data-ttu-id="a81cb-192">사용자는 차단된 앱 또는 해당 기능(예: 봇, 탭 및 메시징 확장)과 상호 작용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a81cb-192">Users can't interact with a blocked app or its capabilities, such bots, tabs, and messaging extensions.</span></span> <span data-ttu-id="a81cb-193">팀 또는 그룹 채팅과 같은 공유 컨텍스트에서 봇은 해당 컨텍스트의 모든 참가자에게 메시지를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a81cb-193">In a shared context, such as a team or group chat, bots can still send messages to all participants of that context.</span></span> <span data-ttu-id="a81cb-194">앱이 차단되면 Teams가 사용자에게 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a81cb-194">Teams indicates to the user when an app is blocked.</span></span>

<span data-ttu-id="a81cb-195">예를 들어 앱이 차단된 경우 사용자는 다음 중 어떤 작업을 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a81cb-195">For example, when an app is blocked, users can't do any of the following:</span></span>

- <span data-ttu-id="a81cb-196">개인적으로 또는 채팅 또는 팀에 앱 추가</span><span class="sxs-lookup"><span data-stu-id="a81cb-196">Add the app personally or to a chat or team</span></span>
- <span data-ttu-id="a81cb-197">앱의 봇에 메시지 보내기</span><span class="sxs-lookup"><span data-stu-id="a81cb-197">Send messages to the app’s bot</span></span>
- <span data-ttu-id="a81cb-198">실행 가능한 메시지와 같은 정보를 앱으로 다시 보내는 단추 작업 수행</span><span class="sxs-lookup"><span data-stu-id="a81cb-198">Perform button actions that send information back to the app, such as actionable messages</span></span>  
- <span data-ttu-id="a81cb-199">앱의 탭 보기</span><span class="sxs-lookup"><span data-stu-id="a81cb-199">View the app’s tab</span></span>
- <span data-ttu-id="a81cb-200">알림을 받기 위해 커넥터 설정</span><span class="sxs-lookup"><span data-stu-id="a81cb-200">Set up connectors to receive notifications</span></span>
- <span data-ttu-id="a81cb-201">앱의 메시징 확장 사용</span><span class="sxs-lookup"><span data-stu-id="a81cb-201">Use the app’s messaging extension</span></span>

<span data-ttu-id="a81cb-202">레거시 포털은 조직 수준에서 앱을 제어하도록 허용했습니다. 즉, 앱이 차단된 경우 조직의 모든 사용자에 대해 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="a81cb-202">The legacy portal allowed controlling apps at the organization level, which means when an app is blocked, it's blocked for all users in the organization.</span></span> <span data-ttu-id="a81cb-203">앱 관리 페이지에서 [](manage-apps.md) 앱을 차단하는 것은 정확히 동일한 방식으로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="a81cb-203">Blocking an app on the [Manage apps](manage-apps.md) page works exactly the same way.</span></span>

<span data-ttu-id="a81cb-204">특정 사용자에게 할당된 앱 사용 권한 정책의 경우, 봇 또는 커넥터 기능이 있는 앱이 허용된 다음 차단된 경우, 앱이 공유 컨텍스트의 일부 사용자에 대해만 허용되는 경우 해당 앱에 대한 권한이 없는 그룹 채팅 또는 채널의 구성원은 봇 또는 커넥터에 의해 게시된 메시지 기록 및 메시지를 볼 수 있습니다. 으로는 상호 작용할 수 없는 경우</span><span class="sxs-lookup"><span data-stu-id="a81cb-204">For app permission policies assigned to specific users, if an app with bot or connector capability was allowed and then blocked, and if the app is then allowed only for some users in a shared context, members of a group chat or channel that don't have permission to that app can see the message history and messages that were posted by the bot or connector, but can't interact with it.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a81cb-205">관련 항목</span><span class="sxs-lookup"><span data-stu-id="a81cb-205">Related topics</span></span>

[<span data-ttu-id="a81cb-206">Team에서 앱의 관리 설정</span><span class="sxs-lookup"><span data-stu-id="a81cb-206">Admin settings for apps in Teams</span></span>](admin-settings.md)

[<span data-ttu-id="a81cb-207">Teams에서 사용자에게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="a81cb-207">Assign policies to your users in Teams</span></span>](assign-policies.md)
