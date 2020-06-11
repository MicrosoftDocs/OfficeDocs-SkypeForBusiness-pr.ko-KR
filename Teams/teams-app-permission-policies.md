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
ms.openlocfilehash: b54a4263adc8e697a19f997ac34018e1e2b2c302
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691014"
---
# <a name="manage-app-permission-policies-in-microsoft-teams"></a><span data-ttu-id="fcba4-103">Microsoft 팀에서 앱 권한 정책 관리</span><span class="sxs-lookup"><span data-stu-id="fcba4-103">Manage app permission policies in Microsoft Teams</span></span>

<span data-ttu-id="fcba4-104">관리자는 앱 권한 정책을 사용하여 조직의 Microsoft Teams 사용자가 사용할 수있는 앱을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-104">As an admin, you can use app permission policies to control what apps are available to Microsoft Teams users in your organization.</span></span> <span data-ttu-id="fcba4-105">Microsoft, 타사, 조직에서 게시 한 앱 또는 특정 앱을 모두 허용 하거나 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-105">You can allow or block all apps or specific apps published by Microsoft, third-parties, and your organization.</span></span> <span data-ttu-id="fcba4-106">앱을 차단하면 정책이 있는 사용자는 Teams 앱 스토어에서 goekd 앱을 설치할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-106">When you block an app, users who have the policy are unable to install it from the Teams app store.</span></span> <span data-ttu-id="fcba4-107">이러한 정책을 관리하려면 전역 관리자 또는 Teams 서비스 관리자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-107">You must be a global admin or Teams service admin to manage these policies.</span></span>

<span data-ttu-id="fcba4-108">Microsoft 팀 관리 센터에서 앱 권한 정책을 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-108">You manage app permission policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="fcba4-109">전역 (조직 차원의 기본) 정책을 사용 하거나 개별 사용자 또는 그룹의 사용자에 게 사용자 지정 정책을 만들어 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-109">You can use the global (Org-wide default) policy or create and assign custom policies to individual users or users in a group.</span></span>  

![앱 사용 권한 정책의 스크린샷](media/app-permission-policies.png)

> [!NOTE]
> <span data-ttu-id="fcba4-111">사용자 지정 정책을 만들고 할당하지 않으면 조직의 사용자에게 전역 정책이 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-111">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="fcba4-112">조직 전체 앱 설정은 전역 정책 및 사용자가 만들고 할당 하는 사용자 지정 정책을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-112">Org-wide app settings override the global policy and any custom policies that you create and assign to users.</span></span>

<span data-ttu-id="fcba4-113">조직이 이미 팀에 있는 경우 Microsoft 365 관리 센터의 **테 넌 트 전체 설정** 에서 구성한 앱 설정은 [앱 관리](manage-apps.md) 페이지의 조직 전체 앱 설정에 반영 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-113">If your organization is already on Teams, the app settings you configured in **Tenant-wide settings** in the Microsoft 365 admin center are reflected in org-wide app settings on the [Manage apps](manage-apps.md) page.</span></span> <span data-ttu-id="fcba4-114">팀을 처음 접하는 경우에는 기본적으로 모든 앱을 전역 정책에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-114">If you're new to Teams and just getting started, by default, all apps are allowed in the global policy.</span></span> <span data-ttu-id="fcba4-115">여기에는 Microsoft, 타사, 조직에서 게시 한 앱이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-115">This includes apps published by Microsoft, third-parties, and your organization.</span></span>

<span data-ttu-id="fcba4-116">예를 들어 모든 타사 앱을 차단 하 고 조직의 HR 팀에 대해 Microsoft의 특정 앱을 허용 하려는 경우를 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-116">Say, for example, you want to block all third-party apps and allow specific apps from Microsoft for the HR team in your organization.</span></span> <span data-ttu-id="fcba4-117">먼저 [앱 관리](manage-apps.md) 페이지로 이동 하 여 HR 팀에 허용 하려는 앱이 조직 수준에서 허용 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-117">First, you would go to the [Manage apps](manage-apps.md) page and make sure that the apps that you want to allow for the HR team are allowed at the org level.</span></span> <span data-ttu-id="fcba4-118">그런 다음 HR 앱 권한 정책 이라는 사용자 지정 정책을 만들고, 원하는 앱을 차단 하 고 허용 하도록 설정한 다음 HR 팀에서 사용자에 게 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-118">Then, create a custom policy named HR App Permission Policy, set it to block and allow the apps that you want, and assign it to users on the HR team.</span></span>

> [!NOTE]
> <span data-ttu-id="fcba4-119">Microsoft 365 정부-GCC 환경에서 팀을 배포한 경우 gcc에 고유한 타사 앱 설정에 대 한 자세한 내용은 [gcc 용 앱 권한 정책을](#app-permission-policies-for-gcc) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fcba4-119">If you deployed Teams in a Microsoft 365 Government - GCC environment, see [App permission policies for GCC](#app-permission-policies-for-gcc) to learn more about third-party app settings that are unique to GCC.</span></span>

## <a name="create-a-custom-app-permission-policy"></a><span data-ttu-id="fcba4-120">사용자 지정 앱 권한 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="fcba4-120">Create a custom app permission policy</span></span>

<span data-ttu-id="fcba4-121">조직의 다른 사용자 그룹에 대해 사용할 수 있는 앱을 제어 하려는 경우 하나 이상의 사용자 지정 앱 권한 정책을 만들고 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-121">If you want to control the apps that are available for different groups of users in your organization, create and assign one or more custom app permission policies.</span></span> <span data-ttu-id="fcba4-122">앱이 Microsoft, 타사 또는 조직에 의해 게시 되었는지 여부에 따라 별도의 사용자 지정 정책을 만들고 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-122">You can create and assign separate custom policies based on whether apps are published by Microsoft, third-parties, or your organization.</span></span> <span data-ttu-id="fcba4-123">사용자 지정 정책을 만든 후에는 조직 전체 앱 설정에서 타사 앱을 사용 하지 않도록 설정한 경우 변경할 수 없다는 것을 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-123">It's important to know that after you create a custom policy, you can't change it if third-party apps are disabled in org-wide app settings.</span></span>

1. <span data-ttu-id="fcba4-124">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **팀 앱**  >  **권한 정책**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-124">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="fcba4-125">**추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-125">Click **Add**.</span></span> <br>
    <span data-ttu-id="fcba4-126">![새 앱 권한 정책의 스크린샷](media/app-permission-policies-new-policy.png)</span><span class="sxs-lookup"><span data-stu-id="fcba4-126">![Screenshot of new app permission policy](media/app-permission-policies-new-policy.png)</span></span>
3. <span data-ttu-id="fcba4-127">정책의 이름과 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-127">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="fcba4-128">**Microsoft 앱**, 타사 **앱**및 **사용자 지정 앱**에서 다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-128">Under **Microsoft apps**, **Third-party apps**, and **Custom apps**, select one of the following:</span></span>

    - <span data-ttu-id="fcba4-129">**모든 앱 허용**</span><span class="sxs-lookup"><span data-stu-id="fcba4-129">**Allow all apps**</span></span>
    - <span data-ttu-id="fcba4-130">**특정 앱 허용 및 다른 사용자 모두 차단**</span><span class="sxs-lookup"><span data-stu-id="fcba4-130">**Allow specific apps and block all others**</span></span>
    - <span data-ttu-id="fcba4-131">**특정 앱을 차단 하 고 다른 사용자 허용**</span><span class="sxs-lookup"><span data-stu-id="fcba4-131">**Block specific apps and allow all others**</span></span>
    - <span data-ttu-id="fcba4-132">**모든 앱 차단**</span><span class="sxs-lookup"><span data-stu-id="fcba4-132">**Block all apps**</span></span>

5. <span data-ttu-id="fcba4-133">**특정 앱 허용 및 다른 사용자 차단**을 선택한 경우 허용 하려는 앱을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-133">If you selected **Allow specific apps and block others**, add the apps that you want to allow:</span></span>

    1. <span data-ttu-id="fcba4-134">**앱 허용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-134">Select **Allow apps**.</span></span>
    1. <span data-ttu-id="fcba4-135">허용 하려는 앱을 검색 한 다음 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-135">Search for the apps that you want to allow, and then click **Add**.</span></span> <span data-ttu-id="fcba4-136">검색 결과가 앱 게시자 (**Microsoft 앱**, 타사 **앱**또는 **사용자 지정 앱**)로 필터링 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-136">The search results are filtered to the app publisher (**Microsoft apps**, **Third-party apps**, or **Custom apps**).</span></span>
    1. <span data-ttu-id="fcba4-137">앱 목록을 선택 했으면 **허용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-137">When you've chosen the list of apps, click **Allow**.</span></span> 

6. <span data-ttu-id="fcba4-138">마찬가지로 **특정 앱을 차단 하 고 다른 모든 사용자 허용**을 선택한 경우 차단 하려는 앱을 검색 하 여 추가한 다음 **차단을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-138">Similarly, if you selected **Block specific apps and allow all others**, search for and add the apps that you want to block, and then click **Block**.</span></span>
7. <span data-ttu-id="fcba4-139">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-139">Click **Save**.</span></span>

## <a name="edit-an-app-permission-policy"></a><span data-ttu-id="fcba4-140">앱 권한 정책 편집</span><span class="sxs-lookup"><span data-stu-id="fcba4-140">Edit an app permission policy</span></span>

<span data-ttu-id="fcba4-141">Microsoft 팀 관리 센터를 사용 하 여 글로벌 정책 및 만든 사용자 지정 정책을 비롯 한 정책을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-141">You can use the Microsoft Teams admin center to edit a policy, including the global policy and custom policies that you create.</span></span>

1. <span data-ttu-id="fcba4-142">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **팀 앱**  >  **권한 정책**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-142">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="fcba4-143">정책 이름 왼쪽을 클릭 하 여 정책을 선택한 다음 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-143">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="fcba4-144">여기서 원하는 대로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-144">From here, make the changes that you want.</span></span> <span data-ttu-id="fcba4-145">앱 게시자에 따라 설정을 관리 하 고 허용/차단 설정에 따라 앱을 추가 및 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-145">You can manage settings based on the app publisher and add and remove apps based on the allow/block setting.</span></span>
4. <span data-ttu-id="fcba4-146">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-146">Click **Save**.</span></span>

## <a name="assign-a-custom-app-permission-policy-to-users"></a><span data-ttu-id="fcba4-147">사용자에 게 사용자 지정 앱 권한 정책 할당</span><span class="sxs-lookup"><span data-stu-id="fcba4-147">Assign a custom app permission policy to users</span></span>

<span data-ttu-id="fcba4-148">Microsoft 팀 관리 센터를 사용 하 여 하나 이상의 사용자 또는 비즈니스용 Skype PowerShell 모듈에 사용자 지정 정책을 할당 하 여 보안 그룹 또는 메일 그룹의 모든 사용자와 같은 그룹의 사용자에 게 사용자 지정 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-148">You can use the Microsoft Teams admin center to assign a custom policy to one or more users or the Skype for Business PowerShell module to assign a custom policy to users in a group, such as all users in a security group or distribution group.</span></span>

### <a name="assign-a-custom-app-permission-policy-to-users"></a><span data-ttu-id="fcba4-149">사용자에 게 사용자 지정 앱 권한 정책 할당</span><span class="sxs-lookup"><span data-stu-id="fcba4-149">Assign a custom app permission policy to users</span></span>

<span data-ttu-id="fcba4-150">한 사용자에 게 정책을 할당 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-150">To assign a policy to one user:</span></span>

1. <span data-ttu-id="fcba4-151">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **사용자**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-151">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="fcba4-152">사용자 이름의 왼쪽을 클릭하여 사용자를 선택한 후 **설정 편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-152">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="fcba4-153">**앱 권한 정책**에서 할당할 앱 권한 정책을 선택한 다음 **적용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-153">Under **App permission policy**, select the app permission policy you want to assign, and then click **Apply**.</span></span>

<span data-ttu-id="fcba4-154">한 번에 여러 사용자에게 정책을 할당하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-154">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="fcba4-155">Microsoft Teams 관리 센터의 왼쪽 탐색에서 **사용자**로 이동한 다음, 사용자를 검색하거나 보기를 필터링하여 원하는 사용자를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-155">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="fcba4-156">**&#x2713;**(확인 표시) 열에서 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-156">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="fcba4-157">모든 사용자를 선택하려면 표 맨 위에서 &#x2713;(확인 표시)를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-157">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="fcba4-158">**설정 편집**을 클릭하고 원하는 대로 변경한 다음, **적용**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-158">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>  

<span data-ttu-id="fcba4-159">또는 다음을 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-159">Or, you can also do the following:</span></span>

1. <span data-ttu-id="fcba4-160">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **팀 앱**  >  **권한 정책**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-160">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="fcba4-161">정책 이름의 왼쪽을 클릭하여 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-161">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="fcba4-162">**사용자 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-162">Select **Manage users**.</span></span>
4. <span data-ttu-id="fcba4-163">**사용자 관리** 창에서 표시 이름 또는 사용자 이름으로 사용자를 검색하고 이름을 선택한 후 **추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-163">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="fcba4-164">추가할 각 사용자에 대해 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-164">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="fcba4-165">사용자 추가를 마쳤으면 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-165">When you're finished adding users, click **Save**.</span></span>

### <a name="assign-a-custom-app-permission-policy-to-users-in-a-group"></a><span data-ttu-id="fcba4-166">그룹의 사용자에 게 사용자 지정 앱 권한 정책 할당</span><span class="sxs-lookup"><span data-stu-id="fcba4-166">Assign a custom app permission policy to users in a group</span></span>

<span data-ttu-id="fcba4-167">이미 식별 한 여러 사용자에 게 사용자 지정 앱 사용 권한 정책을 할당 하려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-167">You may want to assign a custom app permission policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="fcba4-168">예를 들어 보안 그룹의 모든 사용자에 게 정책을 할당 하려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-168">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="fcba4-169">그래프 모듈의 Azure Active Directory PowerShell 및 비즈니스용 Skype PowerShell 모듈에 연결 하 여이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-169">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="fcba4-170">PowerShell을 사용 하 여 팀을 관리 하는 방법에 대 한 자세한 내용은 [팀 Powershell 개요](teams-powershell-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fcba4-170">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

<span data-ttu-id="fcba4-171">이 예제에서는 Contoso 금강 HR 프로젝트 그룹의 모든 사용자에 게 HR 앱 권한 정책 이라는 사용자 지정 앱 권한 정책을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-171">In this example, we assign a custom app permission policy called HR App Permission Policy to all users in the Contoso Pharmaceuticals HR Project group.</span></span>  

> [!NOTE]
> <span data-ttu-id="fcba4-172">먼저 [모든 Microsoft 365 또는 Office 365 서비스에 연결의 단계를 단일 Windows powershell 창에](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)따라 Graph 모듈 및 비즈니스용 Skype powershell 모듈에 대 한 Azure Active Directory powershell에 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-172">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="fcba4-173">특정 그룹의 GroupObjectId를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-173">Get the GroupObjectId of the particular group.</span></span>
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Pharmaceuticals HR Project"
```
<span data-ttu-id="fcba4-174">지정 된 그룹의 구성원을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-174">Get the members of the specified group.</span></span>
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="fcba4-175">그룹의 모든 사용자를 특정 앱 권한 정책에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-175">Assign all users in the group to a particular app permission policy.</span></span> <span data-ttu-id="fcba4-176">이 예제에서는 HR 앱 권한 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-176">In this example, it's HR App Permission Policy.</span></span>
```PowerShell
$members | ForEach-Object { Grant-CsTeamsAppPermissionPolicy -PolicyName "HR App Permission Policy" -Identity $_.UserPrincipalName}
``` 
<span data-ttu-id="fcba4-177">그룹의 구성원 수에 따라이 명령을 실행 하는 데 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-177">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="app-permission-policies-for-gcc"></a><span data-ttu-id="fcba4-178">GCC 용 앱 권한 정책</span><span class="sxs-lookup"><span data-stu-id="fcba4-178">App permission policies for GCC</span></span>

<span data-ttu-id="fcba4-179">팀의 Microsoft 365 정부-GCC 배포에서 GCC에 고유한 제 3 자 앱 설정에 대 한 다음 사항을 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-179">In a Microsoft 365 Government - GCC deployment of Teams, it's important to know the following about third-party app settings, which are unique to GCC.</span></span>

<span data-ttu-id="fcba4-180">GCC에서는 모든 타사 앱이 기본적으로 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-180">In GCC, all third-party apps are blocked by default.</span></span> <span data-ttu-id="fcba4-181">또한 Microsoft 팀 관리 센터의 앱 사용 권한 정책 페이지에서 타사 앱을 관리 하는 방법에 대 한 참고 사항을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-181">Additionally, you'll see the following note about managing third-party apps on the app permission policies page in the Microsoft Teams admin center.</span></span>

![GCC의 앱 사용 권한 정책 스크린샷](media/app-permission-policies-gcc.png)

<span data-ttu-id="fcba4-183">조직의 사용자 또는 사용자 집합에 대해 타사 앱을 사용 하도록 설정 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-183">To enable a third-party app for a user or a set of users in your organization, do the following:</span></span>

1. <span data-ttu-id="fcba4-184">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **팀 앱**으로 이동 하  >  **Manage apps**고 앱 목록에서 사용자 집합을 허용 하려는 타사 앱이 조직 수준에서 **차단** 되도록 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-184">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**, and then in the list of apps, confirm that the third-party app that you want to allow for a set of users is set to **Blocked** at the org level.</span></span>

2. <span data-ttu-id="fcba4-185">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **팀 앱**  >  **권한 정책**으로 이동한 다음, 전역 정책을 편집 하 여 타사 앱을 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-185">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**, and then edit the global policy to block the third-party app.</span></span> <span data-ttu-id="fcba4-186">실행할 작업:</span><span class="sxs-lookup"><span data-stu-id="fcba4-186">To do this:</span></span>
    1. <span data-ttu-id="fcba4-187">앱 권한 정책 페이지에서 **전역 (조직 전체 기본값)** 을 클릭 한 다음 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-187">On the App permission policies page, click **Global (Org-wide default)**, and then click **Edit**.</span></span>
    2. <span data-ttu-id="fcba4-188">**타사 앱**에서 **특정 앱 차단을 선택 하 고 다른 모든 사용자를 허용**하 고 앱을 추가한 다음 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-188">Under **Third-party apps**, select **Block specific apps and allow all others**, add the app, and then click **Save**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="fcba4-189">조직 수준에서 앱을 허용 하기 위해 다음 단계로 이동 하기 전에이 작업을 수행 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-189">It's important to do this before you go to the next step to allow the app at the org level.</span></span> <span data-ttu-id="fcba4-190">이는 타사 앱이 전역 앱 권한 정책에서 차단 되지 않은 경우 전역 정책이 적용 되는 모든 사용자가 조직 수준에서 허용 하는 경우 타사 앱에 액세스할 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-190">This is because if the third-party app isn't blocked in the global app permission policy, all users that the global policy applies to will be able to access the third-party app when you allow it at the org level.</span></span>

3. <span data-ttu-id="fcba4-191">조직 수준에서 타사 앱을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-191">Allow the third-party app at the org level.</span></span> <span data-ttu-id="fcba4-192">이렇게 하려면 왼쪽 탐색 창에서 **팀 앱**앱  >  **관리**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-192">To do this, in the left navigation, go to **Teams apps** > **Manage apps**.</span></span> <span data-ttu-id="fcba4-193">앱 목록에서 앱 이름 왼쪽에 있는을 클릭 하 여 앱을 선택한 다음 **허용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-193">In the list of apps, click to the left of the app name to select the app, and then select **Allow**.</span></span>
4. <span data-ttu-id="fcba4-194">앱을 허용 하는 [사용자 지정 앱 권한 정책을 만든](#create-a-custom-app-permission-policy) 다음 정책을 원하는 사용자에 게 [할당](#assign-a-custom-app-permission-policy-to-users) 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-194">[Create a custom app permission policy](#create-a-custom-app-permission-policy) to allow the app, and then [assign the policy](#assign-a-custom-app-permission-policy-to-users) to the users you want.</span></span>

## <a name="faq"></a><span data-ttu-id="fcba4-195">FAQ</span><span class="sxs-lookup"><span data-stu-id="fcba4-195">FAQ</span></span>

### <a name="working-with-app-permission-policies"></a><span data-ttu-id="fcba4-196">앱 권한 정책 사용</span><span class="sxs-lookup"><span data-stu-id="fcba4-196">Working with app permission policies</span></span>

#### <a name="what-app-interactions-do-permission-policies-affect"></a><span data-ttu-id="fcba4-197">권한 정책의 영향을 받는 앱 조작</span><span class="sxs-lookup"><span data-stu-id="fcba4-197">What app interactions do permission policies affect?</span></span>
<span data-ttu-id="fcba4-198">권한 정책은 최종 사용자의 설치, 검색, 조작 등을 제어 하 여 앱 사용을 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-198">Permission policies govern app usage by controlling installation, discovery, and interaction for end users.</span></span> <span data-ttu-id="fcba4-199">관리자는 할당 된 권한 정책에 관계 없이 Microsoft 팀 관리 센터에서 앱을 계속 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-199">Admins can still manage apps in the Microsoft Teams admin center regardless of the permission policies assigned to them.</span></span>

#### <a name="can-i-control-line-of-business-lob-apps"></a><span data-ttu-id="fcba4-200">LOB (기간 업무) 앱을 제어할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="fcba4-200">Can I control line of business (LOB) apps?</span></span>
<span data-ttu-id="fcba4-201">예, 앱 사용 권한 정책을 사용 하 여 사용자 지정 (LOB) 앱의 출시 및 배포를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-201">Yes, you can use app permission policies to control the rollout and distribution of custom (LOB) apps.</span></span> <span data-ttu-id="fcba4-202">사용자 지정 정책을 만들거나 전역 정책을 편집 하 여 조직의 요구 사항에 따라 사용자 지정 앱을 허용 하거나 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-202">You can create a custom policy or edit the global policy to allow or block custom apps based on the needs of your organization.</span></span>

#### <a name="how-do-app-permission-policies-relate-to-pinned-apps-and-app-setup-policies"></a><span data-ttu-id="fcba4-203">앱 권한 정책은 고정 된 앱 및 앱 설정 정책과 어떻게 관련 되나요?</span><span class="sxs-lookup"><span data-stu-id="fcba4-203">How do app permission policies relate to pinned apps and app setup policies?</span></span>

<span data-ttu-id="fcba4-204">앱 설치 정책은 앱 권한 정책과 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-204">You can use app setup policies together with app permission policies.</span></span> <span data-ttu-id="fcba4-205">미리 고정 된 앱은 사용자의 활성화 된 앱 집합에서 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-205">Pre-pinned apps are selected from the set of enabled apps for a user.</span></span> <span data-ttu-id="fcba4-206">또한 사용자에 게 앱 설정 정책에서 앱을 차단 하는 앱 권한 정책이 있는 경우 해당 앱은 팀에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-206">Additionally, if a user has an app permission policy that blocks an app in their app setup policy, that app won't appear in Teams.</span></span>

#### <a name="can-i-use-app-permission-policies-to-restrict-uploading-custom-apps"></a><span data-ttu-id="fcba4-207">앱 권한 정책을 사용 하 여 사용자 지정 앱 업로드를 제한할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="fcba4-207">Can I use app permission policies to restrict uploading custom apps?</span></span>

<span data-ttu-id="fcba4-208">**앱 관리** 페이지 또는 앱 설정 정책에서 조직 전체 설정을 사용 하 여 조직의 사용자 지정 앱 업로드를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-208">You can use org-wide settings on the **Manage apps** page, or app setup policies to restrict uploading custom apps for your organization.</span></span>  

<span data-ttu-id="fcba4-209">특정 사용자가 사용자 지정 앱을 업로드 하지 못하도록 제한 하려면 사용자 지정 앱 정책을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-209">To restrict specific users from uploading custom apps, use custom app policies.</span></span> <span data-ttu-id="fcba4-210">자세히 알아보려면 [팀에서 사용자 지정 앱 정책 및 설정 관리](teams-custom-app-policies-and-settings.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fcba4-210">To learn more, see [Manage custom app policies and settings in Teams](teams-custom-app-policies-and-settings.md).</span></span>

#### <a name="does-blocking-an-app-apply-to-teams-mobile-clients"></a><span data-ttu-id="fcba4-211">앱이 팀 모바일 클라이언트에 적용 되는 것을 차단 합니까?</span><span class="sxs-lookup"><span data-stu-id="fcba4-211">Does blocking an app apply to Teams mobile clients?</span></span>

<span data-ttu-id="fcba4-212">예, 앱을 차단 하면 모든 팀 클라이언트에서 앱이 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-212">Yes, when you block an app, that app is blocked across all Teams clients.</span></span>  

### <a name="user-experience"></a><span data-ttu-id="fcba4-213">사용자 환경</span><span class="sxs-lookup"><span data-stu-id="fcba4-213">User experience</span></span>

#### <a name="what-does-a-user-experience-when-an-app-is-blocked"></a><span data-ttu-id="fcba4-214">앱이 차단 되는 경우 사용자 환경</span><span class="sxs-lookup"><span data-stu-id="fcba4-214">What does a user experience when an app is blocked?</span></span>

<span data-ttu-id="fcba4-215">사용자는 차단 된 앱 또는 인공 지능, 탭, 메시징 확장과 같은 기능을 조작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-215">Users can't interact with a blocked app or its capabilities, such bots, tabs, and messaging extensions.</span></span> <span data-ttu-id="fcba4-216">팀 또는 그룹 채팅 같은 공유 컨텍스트에서이는 해당 컨텍스트의 모든 참가자에 게 메시지를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-216">In a shared context, such as a team or group chat, bots can still send messages to all participants of that context.</span></span> <span data-ttu-id="fcba4-217">앱이 차단 되 면 팀에서 사용자에 게 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-217">Teams indicates to the user when an app is blocked.</span></span>

<span data-ttu-id="fcba4-218">예를 들어 앱이 차단 되 면 사용자는 다음을 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-218">For example, when an app is blocked, users can't do any of the following:</span></span>

- <span data-ttu-id="fcba4-219">개인적으로 또는 채팅 또는 팀에 앱 추가</span><span class="sxs-lookup"><span data-stu-id="fcba4-219">Add the app personally or to a chat or team</span></span>
- <span data-ttu-id="fcba4-220">앱의 bot에 메시지 보내기</span><span class="sxs-lookup"><span data-stu-id="fcba4-220">Send messages to the app’s bot</span></span>
- <span data-ttu-id="fcba4-221">처리 가능한 메시지 등의 정보를 앱으로 다시 보내는 단추 작업 수행</span><span class="sxs-lookup"><span data-stu-id="fcba4-221">Perform button actions that send information back to the app, such as actionable messages</span></span>  
- <span data-ttu-id="fcba4-222">앱의 탭 보기</span><span class="sxs-lookup"><span data-stu-id="fcba4-222">View the app’s tab</span></span>
- <span data-ttu-id="fcba4-223">알림을 받도록 커넥터 설정</span><span class="sxs-lookup"><span data-stu-id="fcba4-223">Set up connectors to receive notifications</span></span>
- <span data-ttu-id="fcba4-224">앱의 메시징 확장 사용</span><span class="sxs-lookup"><span data-stu-id="fcba4-224">Use the app’s messaging extension</span></span>

<span data-ttu-id="fcba4-225">레거시 포털은 조직 수준에서 앱을 제어할 수 있으며,이는 앱이 차단 되는 경우 조직의 모든 사용자에 대해 차단 됨을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-225">The legacy portal allowed controlling apps at the organization level, which means when an app is blocked, it's blocked for all users in the organization.</span></span> <span data-ttu-id="fcba4-226">[앱 관리](manage-apps.md) 페이지에서 앱을 차단 하는 방법은 동일 하 게 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-226">Blocking an app on the [Manage apps](manage-apps.md) page works exactly the same way.</span></span>

<span data-ttu-id="fcba4-227">특정 사용자에 게 할당 된 앱 권한 정책의 경우, 봇 또는 커넥터 기능이 있는 앱이 허용 된 후 차단 되며,이 앱이 공유 컨텍스트의 일부 사용자 에게만 허용 되는 경우 해당 앱에 대 한 권한이 없는 그룹 채팅 또는 채널의 구성원은 봇 또는 커넥터에 의해 게시 된 메시지 기록 및 메시지를 볼 수 있습니다. 있지만 대화형 작업을 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fcba4-227">For app permission policies assigned to specific users, if an app with bot or connector capability was allowed and then blocked, and if the app is then allowed only for some users in a shared context, members of a group chat or channel that don't have permission to that app can see the message history and messages that were posted by the bot or connector, but can't interact with it.</span></span>

## <a name="related-topics"></a><span data-ttu-id="fcba4-228">관련 항목</span><span class="sxs-lookup"><span data-stu-id="fcba4-228">Related topics</span></span>

- [<span data-ttu-id="fcba4-229">Team에서 앱의 관리 설정</span><span class="sxs-lookup"><span data-stu-id="fcba4-229">Admin settings for apps in Teams</span></span>](admin-settings.md)
- [<span data-ttu-id="fcba4-230">팀에서 사용자에 게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="fcba4-230">Assign policies to your users in Teams</span></span>](assign-policies.md)
