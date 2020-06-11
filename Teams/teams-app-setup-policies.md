---
title: Microsoft 팀에서 앱 설치 정책 관리
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
description: 조직의 사용자를 위해 Microsoft 팀에서 앱 설치 정책을 사용 하 고 관리 하는 방법에 대해 알아봅니다.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: b804916609b121ba02a048d1763c4181fb5d0a63
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691024"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a><span data-ttu-id="5d6ab-103">Microsoft 팀에서 앱 설치 정책 관리</span><span class="sxs-lookup"><span data-stu-id="5d6ab-103">Manage app setup policies in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="5d6ab-104">조직 전체 앱 설정을 사용 하도록 설정한 경우 **사용자 지정 앱과의 상호 작용을 허용**하면 Microsoft 팀 관리 센터에 앱 설정 정책이 아직 표시 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-104">If you enabled the org-wide app setting, **Allow interaction with custom apps**, you may not see app setup policies yet in the Microsoft Teams admin center.</span></span> <span data-ttu-id="5d6ab-105">현재 출시 되 고 있으며 조직에서 곧 사용할 수 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-105">It's currently being rolled out and will be available soon in your organization.</span></span>

<span data-ttu-id="5d6ab-106">관리자는 앱 설정 정책을 사용하여 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-106">As an admin, you can use app setup policies to do the following:</span></span>

- <span data-ttu-id="5d6ab-107">팀을 사용자 지정하여 사용자에게 가장 중요한 앱을 강조 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-107">Customize Teams to highlight the apps that are most important for your users.</span></span> <span data-ttu-id="5d6ab-108">고정할 앱을 선택 하 고 표시 되는 순서를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-108">You choose the apps to pin and set the order that they appear.</span></span> <span data-ttu-id="5d6ab-109">앱 고정을 사용하면 조직의 개발자나 타사에서 빌드한 앱을 비롯하여 조직의 사용자에게 필요한 앱을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-109">Pinning apps lets you showcase apps that users in your organization need, including those built by third parties or by developers in your organization.</span></span>
- <span data-ttu-id="5d6ab-110">사용자가 앱을 Teams에 고정할 수 있는지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-110">Control whether users can pin apps to Teams.</span></span>
- <span data-ttu-id="5d6ab-111">사용자를 대신 하 여 앱을 설치 합니다 **(미리 보기)**.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-111">Install apps on behalf of users **(in preview)**.</span></span> <span data-ttu-id="5d6ab-112">사용자가 팀을 시작할 때 기본적으로 설치 되는 앱을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-112">You choose which apps are installed by default for users when they start Teams.</span></span> <span data-ttu-id="5d6ab-113">할당 된 [앱 권한 정책이](teams-app-permission-policies.md) 허용 하는 경우에도 사용자가 앱을 설치할 수 있다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-113">Keep in mind that users can still install apps themselves if the [app permission policy](teams-app-permission-policies.md) that's assigned to them allows it.</span></span>

<span data-ttu-id="5d6ab-114">앱은 앱 표시줄에 고정됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-114">Apps are pinned to the app bar.</span></span> <span data-ttu-id="5d6ab-115">앱 표시줄 Teams 데스크톱 클라이언트의 측면과 Teams 모바일 클라이언트(iOS 및 Android)의 하단에 있는 표시줄입니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-115">This is the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients (iOS and Android).</span></span>

|<span data-ttu-id="5d6ab-116">팀 데스크톱 클라이언트</span><span class="sxs-lookup"><span data-stu-id="5d6ab-116">Teams desktop client</span></span>  |<span data-ttu-id="5d6ab-117">팀 모바일 클라이언트</span><span class="sxs-lookup"><span data-stu-id="5d6ab-117">Teams mobile client</span></span> |
|---------|---------|
|![팀 데스크톱 클라이언트를 보여 주는 스크린샷](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![팀 모바일 클라이언트를 보여 주는 스크린샷](media/app-setup-policies-mobile-app-bar.png)      |

<span data-ttu-id="5d6ab-120">사전 설치 된 앱을 보려면 앱 표시줄에서 사용자 \*\*를 클릭 합니다. \*\*팀 데스크톱 및 웹 클라이언트의 앱을 더 추가 하 고 모바일 클라이언트에서 위로 살짝 밉니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-120">To see their pre-installed apps, in the app bar, users click **... More apps** in the Teams desktop and web clients and swipe up in the mobile clients.</span></span>

<span data-ttu-id="5d6ab-121">Microsoft 팀 관리 센터에서 앱 설치 정책을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-121">You manage app setup policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="5d6ab-122">전역(조직 전체 기본값) 정책을 사용하거나 사용자 지정 정책을 만들어 사용자에게 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-122">You can use the global (Org-wide default) policy or create custom policies and assign them to users.</span></span> <span data-ttu-id="5d6ab-123">사용자 지정 정책을 만들고 할당하지 않으면 조직의 사용자에게 전역 정책이 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-123">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="5d6ab-124">이러한 정책을 관리하려면 전역 관리자 또는 Teams 서비스 관리자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-124">You must be a global admin or Teams service admin to manage these policies.</span></span>

<span data-ttu-id="5d6ab-125">전역 정책의 설정을 편집 하 여 원하는 앱을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-125">You can edit the settings in the global policy to include the apps that you want.</span></span> <span data-ttu-id="5d6ab-126">조직의 다른 사용자 그룹에 대해 팀을 사용자 지정 하려면 하나 이상의 사용자 지정 정책을 만들고 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-126">If you want to customize Teams for different groups of users in your organization, create and assign one or more custom policies.</span></span> <span data-ttu-id="5d6ab-127">사용자가 사용자 지정 정책을 할당 한 경우 해당 정책이 사용자에 게 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-127">If a user is assigned a custom policy, that policy applies to the user.</span></span> <span data-ttu-id="5d6ab-128">사용자가 사용자 지정 정책을 할당 하지 않으면 전역 정책이 사용자에 게 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-128">If a user isn't assigned a custom policy, the global policy applies to the user.</span></span>

![앱 설정 정책 페이지를 보여 주는 스크린샷](media/app-setup-policies.png)

> [!NOTE]
> <span data-ttu-id="5d6ab-130">교육 팀이 있는 경우 현재 글로벌 정책에는 할당 앱이 기본적으로 고정 되어 있지만,이는 전역 정책에 나열 되지 않은 경우에도 확인 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-130">If you have Teams for Education, it's important to know that the Assignments app is pinned by default in the global policy even though currently, you don't see it listed in the global policy.</span></span> <span data-ttu-id="5d6ab-131">팀 클라이언트의 고정 된 앱 목록에서 네 번째 앱이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-131">It will be the fourth app in the list of pinned apps on Teams clients.</span></span>

## <a name="create-a-custom-app-setup-policy"></a><span data-ttu-id="5d6ab-132">사용자 지정 앱 설정 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="5d6ab-132">Create a custom app setup policy</span></span>

<span data-ttu-id="5d6ab-133">Microsoft 팀 관리 센터를 사용 하 여 사용자 지정 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-133">You can use the Microsoft Teams admin center to create a custom policy.</span></span>

1. <span data-ttu-id="5d6ab-134">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **팀 앱**  >  **설정 정책**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-134">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>
2. <span data-ttu-id="5d6ab-135">**추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-135">Click **Add**.</span></span>
    <span data-ttu-id="5d6ab-136">![앱 설정 정책 추가 페이지를 보여 주는 스크린샷](media/app-setup-policies-add.png)</span><span class="sxs-lookup"><span data-stu-id="5d6ab-136">![Screenshot showing the Add app setup policies page](media/app-setup-policies-add.png)</span></span>
3. <span data-ttu-id="5d6ab-137">정책의 이름과 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-137">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="5d6ab-138">사용자 지정 앱을 팀에 업로드 하도록 허용할지 여부에 따라 **사용자 지정 앱 업로드**를 설정 하거나 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-138">Turn on or turn off **Upload custom apps**, depending on whether you want to let users upload custom apps to Teams.</span></span> <span data-ttu-id="5d6ab-139">[조직 전체 앱 설정](manage-apps.md#manage-org-wide-app-settings)에서 타사 **앱 허용** 이 해제 되어 있는 경우에는이 설정을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-139">You won't be able to change this setting if **Allow third-party apps** is turned off in [org-wide app settings](manage-apps.md#manage-org-wide-app-settings).</span></span>
5. <span data-ttu-id="5d6ab-140">사용자에 게 앱을 고정 하 여 앱 표시줄을 개인 설정할 수 있도록 할지 여부에 따라 **사용자 고정 허용**을 설정 하거나 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-140">Turn on or turn off **Allow user pinning**, depending on whether you want to let users personalize their app bar by pinning apps to it.</span></span>
6. <span data-ttu-id="5d6ab-141">사용자를 위해 앱을 설치 하려면 **(미리 보기에서)** 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-141">To install apps for users **(in preview)**, do the following:</span></span>

    1. <span data-ttu-id="5d6ab-142">**설치 된 앱**에서 **앱 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-142">Under **Installed apps**, click **Add apps**.</span></span>
    2. <span data-ttu-id="5d6ab-143">**설치 된 앱 추가** 창에서 팀을 시작할 때 자동으로 설치 하려는 앱을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-143">In the **Add installed apps** pane, search for the apps you want to automatically install for users when they start Teams.</span></span> <span data-ttu-id="5d6ab-144">앱 사용 권한 정책을 기준으로 앱을 필터링 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-144">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="5d6ab-145">앱 목록을 선택한 후 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-145">When you've chosen your list of apps, click **Add**.</span></span>

        ![설치 된 앱 추가 창을 보여 주는 스크린샷](media/app-setup-policies-add-installed-apps.png)

7. <span data-ttu-id="5d6ab-147">앱을 고정 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-147">To pin apps, do the following:</span></span>

    1. <span data-ttu-id="5d6ab-148">**고정 된 앱**에서 **앱 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-148">Under **Pinned apps**, click **Add apps**.</span></span>
    2. <span data-ttu-id="5d6ab-149">고정 된 **앱 추가** 창에서 추가 하려는 앱을 검색 한 다음 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-149">In the **Add pinned apps** pane, search for the apps you want to add, and then click **Add**.</span></span> <span data-ttu-id="5d6ab-150">앱 사용 권한 정책을 기준으로 앱을 필터링 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-150">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="5d6ab-151">고정할 앱 목록을 선택 했으면 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-151">When you've chosen your list of apps to pin, click **Add**.</span></span>

         ![고정 된 앱 추가 창을 보여 주는 스크린샷](media/app-setup-policies-add-apps.png)

    3. <span data-ttu-id="5d6ab-153">팀에 표시할 순서 대로 앱을 정렬 한 다음 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-153">Arrange the apps in the order that you want them to appear in Teams, and then click **Save**.</span></span>

        ![고정 된 앱 섹션을 보여 주는 스크린샷](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a><span data-ttu-id="5d6ab-155">앱 설치 정책 편집</span><span class="sxs-lookup"><span data-stu-id="5d6ab-155">Edit an app setup policy</span></span>

<span data-ttu-id="5d6ab-156">Microsoft 팀 관리 센터를 사용 하 여 전역 (조직 전체 기본값) 정책 및 직접 만든 사용자 지정 정책을 비롯 한 정책을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-156">You can use the Microsoft Teams admin center to edit a policy, including the global (Org-wide default) policy and custom policies that you create.</span></span>

1. <span data-ttu-id="5d6ab-157">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **팀 앱**  >  **설정 정책**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-157">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>
2. <span data-ttu-id="5d6ab-158">정책 이름 왼쪽을 클릭 하 여 정책을 선택한 다음 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-158">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="5d6ab-159">여기서 원하는 대로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-159">From here, make the changes that you want.</span></span>
4. <span data-ttu-id="5d6ab-160">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-160">Click **Save**.</span></span>

## <a name="assign-a-custom-app-setup-policy-to-users"></a><span data-ttu-id="5d6ab-161">사용자에 게 사용자 지정 앱 설정 정책 할당</span><span class="sxs-lookup"><span data-stu-id="5d6ab-161">Assign a custom app setup policy to users</span></span>

<span data-ttu-id="5d6ab-162">Microsoft 팀 관리 센터를 사용 하 여 개인 사용자 또는 비즈니스용 Skype PowerShell 모듈에 사용자 지정 정책을 할당 하 여 그룹의 사용자에 게 보안 그룹 또는 메일 그룹과 같은 사용자 지정 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-162">You can use the Microsoft Teams admin center to assign a custom policy to individual users or the Skype for Business PowerShell module  to assign a custom policy to users in a group, such as a security group or distribution group.</span></span>

### <a name="assign-a-custom-app-setup-policy-to-users"></a><span data-ttu-id="5d6ab-163">사용자에 게 사용자 지정 앱 설정 정책 할당</span><span class="sxs-lookup"><span data-stu-id="5d6ab-163">Assign a custom app setup policy to users</span></span>

<span data-ttu-id="5d6ab-164">한 사용자에 게 정책을 할당 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-164">To assign a policy to one user:</span></span>

1. <span data-ttu-id="5d6ab-165">Microsoft Teams 관리 센터의 왼쪽 탐색 창에서 **사용자**로 이동한 후 해당 사용자를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-165">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="5d6ab-166">사용자 이름의 왼쪽을 클릭하여 사용자를 선택한 후 **설정 편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-166">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="5d6ab-167">**앱 설정 정책**에서 할당 하려는 앱 설정 정책을 선택한 다음 **적용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-167">Under **App setup policy**, select the app setup policy you want to assign, and then click **Apply**.</span></span>

<span data-ttu-id="5d6ab-168">한 번에 여러 사용자에게 정책을 할당하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-168">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="5d6ab-169">Microsoft Teams 관리 센터의 왼쪽 탐색에서 **사용자**로 이동한 다음, 사용자를 검색하거나 보기를 필터링하여 원하는 사용자를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-169">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="5d6ab-170">**&#x2713;**(확인 표시) 열에서 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-170">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="5d6ab-171">모든 사용자를 선택하려면 표 맨 위에서 &#x2713;(확인 표시)를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-171">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="5d6ab-172">**설정 편집**을 클릭하고 원하는 대로 변경한 다음, **적용**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-172">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>  

<span data-ttu-id="5d6ab-173">또는 다음을 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-173">Or, you can also do the following:</span></span>

1. <span data-ttu-id="5d6ab-174">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **팀 앱**  >  **설정 정책**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-174">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>
2. <span data-ttu-id="5d6ab-175">정책 이름의 왼쪽을 클릭하여 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-175">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="5d6ab-176">**사용자 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-176">Select **Manage users**.</span></span>
4. <span data-ttu-id="5d6ab-177">**사용자 관리** 창에서 표시 이름 또는 사용자 이름으로 사용자를 검색하고 이름을 선택한 다음, **추가**를 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-177">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="5d6ab-178">추가할 각 사용자에 대해 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-178">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="5d6ab-179">사용자 추가를 마쳤으면 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-179">After you finish adding users, select **Save**.</span></span>

### <a name="assign-a-custom-app-setup-policy-to-users-in-a-group"></a><span data-ttu-id="5d6ab-180">그룹의 사용자에 게 사용자 지정 앱 설정 정책 할당</span><span class="sxs-lookup"><span data-stu-id="5d6ab-180">Assign a custom app setup policy to users in a group</span></span>

<span data-ttu-id="5d6ab-181">이미 식별 한 여러 사용자에 게 사용자 지정 앱 설정 정책을 할당 하려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-181">You may want to assign a custom app setup policy to multiple users that you've already identified.</span></span> <span data-ttu-id="5d6ab-182">예를 들어 보안 그룹의 모든 사용자에 게 정책을 할당 하려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-182">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="5d6ab-183">그래프 모듈의 Azure Active Directory PowerShell 및 비즈니스용 Skype PowerShell 모듈에 연결 하 여이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-183">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="5d6ab-184">PowerShell을 사용 하 여 팀을 관리 하는 방법에 대 한 자세한 내용은 [팀 Powershell 개요](teams-powershell-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-184">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

<span data-ttu-id="5d6ab-185">이 예제에서는 Contoso 금강 HR 프로젝트 그룹의 모든 사용자에 게 HR 앱 설정 정책 이라는 사용자 지정 앱 설정 정책을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-185">In this example, we assign a custom app setup policy called HR App Setup Policy to all users in the Contoso Pharmaceuticals HR Project group.</span></span>  

> [!NOTE]
> <span data-ttu-id="5d6ab-186">먼저 [모든 Microsoft 365 또는 Office 365 서비스에 연결의 단계를 단일 Windows powershell 창에](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)따라 Graph 모듈 및 비즈니스용 Skype powershell 모듈에 대 한 Azure Active Directory powershell에 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-186">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="5d6ab-187">특정 그룹의 GroupObjectId를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-187">Get the GroupObjectId of the particular group.</span></span>
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Pharmaceuticals HR Project"
```
<span data-ttu-id="5d6ab-188">지정 된 그룹의 구성원을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-188">Get the members of the specified group.</span></span>
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="5d6ab-189">그룹의 모든 사용자를 특정 앱 설정 정책에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-189">Assign all users in the group to a particular app setup policy.</span></span> <span data-ttu-id="5d6ab-190">이 예제에서는 HR 앱 설정 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-190">In this example, it's HR App Setup Policy.</span></span>
```PowerShell
$members | ForEach-Object { Grant-CsTeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $_.UserPrincipalName}
``` 
<span data-ttu-id="5d6ab-191">그룹의 구성원 수에 따라이 명령을 실행 하는 데 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-191">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="faq"></a><span data-ttu-id="5d6ab-192">FAQ</span><span class="sxs-lookup"><span data-stu-id="5d6ab-192">FAQ</span></span>

### <a name="working-with-app-setup-policies"></a><span data-ttu-id="5d6ab-193">앱 설정 정책 사용</span><span class="sxs-lookup"><span data-stu-id="5d6ab-193">Working with app setup policies</span></span>

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="5d6ab-194">Microsoft 팀 관리 센터에 포함 된 기본 제공 앱 설정 정책은 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="5d6ab-194">What built-in app setup policies are included in the Microsoft Teams admin center?</span></span>

- <span data-ttu-id="5d6ab-195">**전역 (조직 전체 기본값)**: 다른 정책을 할당 하지 않는 한이 기본 정책은 조직의 모든 사용자에 게 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-195">**Global (Org-wide default)**: This default policy applies to all users in your organization unless you assign another policy.</span></span> <span data-ttu-id="5d6ab-196">전역 정책을 편집 하 여 사용자에 게 가장 중요 한 앱을 고정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-196">Edit the global policy to pin apps that are most important for your users.</span></span>
- <span data-ttu-id="5d6ab-197">**Firstlineworker**:이 정책은 firstline worker 용입니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-197">**FirstLineWorker**: This policy is for Firstline Workers.</span></span> <span data-ttu-id="5d6ab-198">조직의 Firstline Worker에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-198">You can assign it to Firstline Workers in your organization.</span></span> <span data-ttu-id="5d6ab-199">사용자 지정 정책과 마찬가지로, 설정이 활성화 되도록 사용자에 게 정책을 할당 해야 한다는 것을 이해 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-199">It's important to know that like custom policies that you create, you have to assign the policy to users for the settings to be active.</span></span> <span data-ttu-id="5d6ab-200">자세한 내용은이 문서의 [사용자에 게 사용자 지정 앱 설정 정책](#assign-a-custom-app-setup-policy-to-users) 지정 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-200">For more information, go to the [Assign a custom app setup policy to users](#assign-a-custom-app-setup-policy-to-users) section of this article.</span></span>

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a><span data-ttu-id="5d6ab-201">고정 된 앱 추가 창에서 앱을 찾을 수 없는 이유는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="5d6ab-201">Why can't I find an app in the Add pinned apps pane?</span></span>

<span data-ttu-id="5d6ab-202">앱 설치 정책을 통해 일부 앱을 팀에 고정 시킬 수 있는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-202">Not all apps can be pinned to Teams through an app setup policy.</span></span> <span data-ttu-id="5d6ab-203">일부 앱은이 기능을 지원 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-203">Some apps may not support this functionality.</span></span> <span data-ttu-id="5d6ab-204">고정 될 수 있는 앱을 찾으려면 **고정 된 앱 추가** 창에서 앱을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-204">To find apps that can be pinned, search for the app in the **Add pinned apps** pane.</span></span> <span data-ttu-id="5d6ab-205">개인 범위 (정적 탭) 및 bot이 있는 탭은 팀 데스크톱 클라이언트에 고정 될 수 있으며, 이러한 앱은 **고정 된 앱 추가** 창에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-205">Tabs that have a personal scope (static tabs) and bots can be pinned to the Teams desktop client and these apps are available in the **Add pinned apps** pane.</span></span>

<span data-ttu-id="5d6ab-206">팀 앱 스토어에는 모든 팀 앱이 나열 되는 반면, **고정 된 앱 추가** 창에는 정책을 통해 팀에 고정 될 수 있는 앱만 포함 된다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-206">Keep in mind that the Teams app store lists all Teams apps whereas the **Add pinned apps** pane includes only apps that can be pinned to Teams through a policy.</span></span> 

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a><span data-ttu-id="5d6ab-207">저는 교육 관리자를 위한 팀입니다. 교육용 팀에서 앱 설정 정책에 대해 알아야 할 사항</span><span class="sxs-lookup"><span data-stu-id="5d6ab-207">I'm a Teams for Education admin. What do I need to know about app setup policies in Teams for Education?</span></span>

<span data-ttu-id="5d6ab-208">교육 팀에서는 호출 앱을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-208">The Calling app isn't available in Teams for Education.</span></span> <span data-ttu-id="5d6ab-209">새 사용자 지정 앱 설치 정책을 만들면 앱 목록에 호출 앱이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-209">When you create a new custom app setup policy, the Calling app is displayed in the list of apps.</span></span> <span data-ttu-id="5d6ab-210">그러나 앱이 팀에 고정 되어 있지 않으며 교육용 사용자 용 팀에 팀의 통화 앱이 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-210">However, the app isn't pinned to Teams clients and Teams for Education users won't see the Calls app in Teams.</span></span>

#### <a name="how-many-pinned-apps-can-be-added-to-a-policy"></a><span data-ttu-id="5d6ab-211">정책에 추가할 수 있는 고정 된 앱은 몇 개입니까?</span><span class="sxs-lookup"><span data-stu-id="5d6ab-211">How many pinned apps can be added to a policy?</span></span>

<span data-ttu-id="5d6ab-212">최소 두 개의 앱을 팀 모바일 클라이언트 (iOS 및 Android)에 고정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-212">A minimum of two apps must be pinned to the Teams mobile clients (iOS and Android).</span></span> <span data-ttu-id="5d6ab-213">정책에 두 개 미만의 앱이 있는 경우 모바일 클라이언트에는 정책 설정이 반영 되지 않으며 대신 기존 구성을 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-213">If a policy has less than two apps, the mobile clients won't reflect the policy settings and instead will continue to use the existing configuration.</span></span>

<span data-ttu-id="5d6ab-214">정책에 추가할 수 있는 고정 된 앱의 수에는 제한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-214">There's no limit on the number of pinned apps you can add to a policy.</span></span>

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a><span data-ttu-id="5d6ab-215">정책 변경 내용이 적용 되는 데 걸리는 시간</span><span class="sxs-lookup"><span data-stu-id="5d6ab-215">How long does it take for policy changes to take effect?</span></span>

<span data-ttu-id="5d6ab-216">전역 정책을 편집 하거나 정책을 할당 한 후 변경 내용을 적용 하는 데 몇 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-216">After you edit the global policy or assign a policy, it can take a few hours for changes to take effect.</span></span>

### <a name="user-experience"></a><span data-ttu-id="5d6ab-217">사용자 환경</span><span class="sxs-lookup"><span data-stu-id="5d6ab-217">User experience</span></span>

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a><span data-ttu-id="5d6ab-218">사용자가 팀에서 모든 고정 된 앱을 볼 수 있는 방법</span><span class="sxs-lookup"><span data-stu-id="5d6ab-218">How can users see all their pinned apps in Teams?</span></span>

<span data-ttu-id="5d6ab-219">사용자에 대해 고정 된 모든 앱을 보려면 설치 된 앱 수와 팀 클라이언트 창의 크기에 따라 사용자가 다음을 수행 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-219">To view all apps that are pinned for a user, users may have to do the following depending on the number of installed apps and the size of their Teams client window.</span></span>

|<span data-ttu-id="5d6ab-220">팀 데스크톱 클라이언트</span><span class="sxs-lookup"><span data-stu-id="5d6ab-220">Teams desktop client</span></span> |<span data-ttu-id="5d6ab-221">팀 모바일 클라이언트</span><span class="sxs-lookup"><span data-stu-id="5d6ab-221">Teams mobile client</span></span> |
|---------|---------|
|<span data-ttu-id="5d6ab-222">팀 측면의 앱 바에서을 클릭 **합니다. 앱이 더**있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-222">In the app bar on the side of Teams, click **... More apps**.</span></span>| <span data-ttu-id="5d6ab-223">팀 아래쪽 근처에 있는 앱 바에서 위로 살짝 밉니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-223">In the app bar near the bottom of Teams, swipe up.</span></span>|
|![팀 데스크톱 클라이언트의 더 많은 앱을 보여 주는 스크린샷](media/app-setup-policies-desktop-more-apps.png)<br>   |![팀 모바일 클라이언트의 더 많은 앱을 보여 주는 스크린샷](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a><span data-ttu-id="5d6ab-226">팀 모바일 환경에 대해 알아야 할 사항</span><span class="sxs-lookup"><span data-stu-id="5d6ab-226">What do I need to know about the Teams mobile experience?</span></span>

<span data-ttu-id="5d6ab-227">팀 모바일 클라이언트 (iOS 및 Android)는 현재 정적 탭이 있는 개인 앱을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-227">The Teams mobile clients (iOS and Android) currently don't support personal apps with static tabs.</span></span> <span data-ttu-id="5d6ab-228">정책에 설정 된 앱에 따라 팀 데스크톱 클라이언트에 고정 된 앱이 팀 모바일 클라이언트에 표시 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-228">Depending on the apps set in the policy, apps pinned to the Teams desktop client might not appear in the Teams mobile clients.</span></span> <span data-ttu-id="5d6ab-229">개인 봇이 모바일 클라이언트의 채팅에 계속 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-229">Personal bots will still appear in Chat on mobile clients.</span></span>

<span data-ttu-id="5d6ab-230">팀 모바일 클라이언트를 사용 하는 경우 사용자에 게 활동, 채팅, 팀 등의 핵심 팀 앱이 표시 되며, Microsoft에서 일부 자사 앱 (예: 이동)을 고정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-230">With the Teams mobile clients, users will see core Teams apps such as Activity, Chat, and Teams, and you can pin some first-party apps from Microsoft, such as Shifts.</span></span>

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a><span data-ttu-id="5d6ab-231">사용자가 정책을 통해 고정 된 앱의 순서를 변경할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="5d6ab-231">Can users change the order of apps pinned through a policy?</span></span>

<span data-ttu-id="5d6ab-232">**사용자 고정 허용** 옵션이 설정 되어 있는 경우 사용자는 팀 데스크톱 및 모바일 클라이언트에서 고정 된 앱의 순서를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-232">Users can change the order of their pinned apps on Teams desktop and mobile clients if the **Allow user pinning** option is turned on.</span></span> <span data-ttu-id="5d6ab-233">사용자는 팀 웹 클라이언트에서 고정 된 앱의 순서를 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-233">Users can't change the order of their pinned apps on Teams web clients.</span></span>

#### <a name="does-user-pinning-take-precedence"></a><span data-ttu-id="5d6ab-234">사용자 고정이 우선적으로 적용 되나요?</span><span class="sxs-lookup"><span data-stu-id="5d6ab-234">Does user pinning take precedence?</span></span>

<span data-ttu-id="5d6ab-235">사용자에 게 할당 된 앱 설정 정책이 사용자 앱 고정을 차단 하도록 변경 되는 경우 팀은 앱 표시줄에 고정 된 앱을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-235">If the app setup policy assigned to the user is changed to block user app pinning, Teams removes any apps pinned to the app bar.</span></span> <span data-ttu-id="5d6ab-236">그런 다음 사용자 앱 고정을 허용 하도록 정책이 변경 되는 경우 사용자는 이전에 고정 된 앱을 다시 고정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-236">If the policy is then changed to allow user app pinning, users must re-pin their previously pinned apps.</span></span>

### <a name="custom-teams-apps"></a><span data-ttu-id="5d6ab-237">사용자 지정 팀 앱</span><span class="sxs-lookup"><span data-stu-id="5d6ab-237">Custom Teams apps</span></span>

#### <a name="my-organization-built-a-custom-teams-app-and-published-it-either-to-appsource-or-the-tenant-app-catalog-but-the-app-icon-isnt-displayed-as-expected-when-the-app-is-pinned-to-the-app-bar-in-teams-how-do-i-fix-it"></a><span data-ttu-id="5d6ab-238">조직에서 사용자 지정 팀 앱을 작성 하 고 AppSource 또는 테 넌 트 앱 카탈로그에 게시 했지만 앱이 팀의 앱 표시줄에 고정 되어 있는 경우 앱 아이콘이 예상 대로 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-238">My organization built a custom Teams app and published it, either to AppSource or the tenant app catalog, but the app icon isn't displayed as expected when the app is pinned to the app bar in Teams.</span></span> <span data-ttu-id="5d6ab-239">이 문제를 해결 하려면 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="5d6ab-239">How do I fix it?</span></span>

<span data-ttu-id="5d6ab-240">앱을 제출 하기 전에 로고 지침을 따르고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-240">Make sure that you follow the logo guidelines before you submit the app.</span></span> <span data-ttu-id="5d6ab-241">자세한 내용은 [판매자 대시보드 제출에 대 한 검사 목록](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5d6ab-241">To learn more, see [Checklist for Seller Dashboard submission](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview).</span></span> 

 ## <a name="related-topics"></a><span data-ttu-id="5d6ab-242">관련 항목</span><span class="sxs-lookup"><span data-stu-id="5d6ab-242">Related topics</span></span>

- [<span data-ttu-id="5d6ab-243">Team에서 앱의 관리 설정</span><span class="sxs-lookup"><span data-stu-id="5d6ab-243">Admin settings for apps in Teams</span></span>](admin-settings.md)
- [<span data-ttu-id="5d6ab-244">팀에서 사용자에 게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="5d6ab-244">Assign policies to your users in Teams</span></span>](assign-policies.md)
