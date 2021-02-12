---
title: Microsoft Teams에서 앱 설정 정책 관리
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
description: 조직의 사용자에 대해 Microsoft Teams에서 앱 설정 정책을 사용 및 관리하는 방법을 배워야 합니다.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: ffc2f15cdbef49daf36e09ca9676925ebb1ac99e
ms.sourcegitcommit: 27bfa015413bc7742bca4ea227e0324da0c740d7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145925"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a><span data-ttu-id="079b9-103">Microsoft Teams에서 앱 설정 정책 관리</span><span class="sxs-lookup"><span data-stu-id="079b9-103">Manage app setup policies in Microsoft Teams</span></span>

<span data-ttu-id="079b9-104">관리자는 앱 설정 정책을 사용하여 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="079b9-104">As an admin, you can use app setup policies to do the following tasks:</span></span>

- <span data-ttu-id="079b9-105">팀을 사용자 지정하여 사용자에게 가장 중요한 앱을 강조 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="079b9-105">Customize Teams to highlight the apps that are most important for your users.</span></span> <span data-ttu-id="079b9-106">고정할 앱을 선택하고 표시 순서를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="079b9-106">You choose the apps to pin and set the order that they appear.</span></span> <span data-ttu-id="079b9-107">앱을 고정하면 타사 또는 조직의 개발자가 구축한 앱을 포함하여 조직의 사용자가 필요로 하는 앱을 소개할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="079b9-107">Pinning apps lets you showcase apps that users in your organization need, including apps built by third parties or by developers in your organization.</span></span>
- <span data-ttu-id="079b9-108">사용자가 앱을 Teams에 고정할 수 있는지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="079b9-108">Control whether users can pin apps to Teams.</span></span>
- <span data-ttu-id="079b9-109">사용자를 대신하여 앱을 **설치합니다(미리 보기 상태).**</span><span class="sxs-lookup"><span data-stu-id="079b9-109">Install apps on behalf of users **(in preview)**.</span></span> <span data-ttu-id="079b9-110">사용자가 Teams를 시작할 때 기본적으로 설치되는 앱을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="079b9-110">You choose which apps are installed by default for users when they start Teams.</span></span> <span data-ttu-id="079b9-111">할당된 앱 사용 권한 정책이 [](teams-app-permission-policies.md) 허용하는 경우 사용자가 앱을 직접 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="079b9-111">Keep in mind that users can still install apps themselves if the [app permission policy](teams-app-permission-policies.md) that's assigned to them allows it.</span></span>

<span data-ttu-id="079b9-112">앱은 Teams 데스크톱 클라이언트의 측면 및 Teams 모바일 클라이언트(iOS 및 Android) 아래쪽에 있는 표시줄인 앱 바에 고정됩니다.</span><span class="sxs-lookup"><span data-stu-id="079b9-112">Apps are pinned to the app bar, which is the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients (iOS and Android).</span></span>

|<span data-ttu-id="079b9-113">Teams 데스크톱 클라이언트</span><span class="sxs-lookup"><span data-stu-id="079b9-113">Teams desktop client</span></span>  |<span data-ttu-id="079b9-114">Teams 모바일 클라이언트</span><span class="sxs-lookup"><span data-stu-id="079b9-114">Teams mobile client</span></span> |
|---------|---------|
|![Teams 데스크톱 클라이언트](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![Teams 모바일 클라이언트](media/mobile-app-ui.png)      |

<span data-ttu-id="079b9-117">미리 설치된 앱을 표시하려면 앱 표시줄에서 ...를 **선택합니다.** Teams 데스크톱 및 웹 클라이언트에 더 많은 앱이 있으며 모바일 클라이언트에서 위를 스와이프합니다.</span><span class="sxs-lookup"><span data-stu-id="079b9-117">To see their pre-installed apps, in the app bar, users select **... More apps** in the Teams desktop and web clients and swipe up in the mobile clients.</span></span>

<span data-ttu-id="079b9-118">Microsoft Teams 관리 센터에서 앱 설정 정책을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="079b9-118">You manage app setup policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="079b9-119">전역(전체 기본) 정책을 사용하거나 사용자 지정 정책을 만들고 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="079b9-119">Use the global (Org-wide default) policy or create and assign custom policies.</span></span>  <span data-ttu-id="079b9-120">사용자 지정 정책을 만들고 할당하지 않으면 조직의 사용자에게 전역 정책이 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="079b9-120">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="079b9-121">이러한 정책을 관리하려면 전역 관리자 또는 Teams 서비스 관리자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="079b9-121">You must be a global admin or Teams service admin to manage these policies.</span></span>

<span data-ttu-id="079b9-122">원하는 앱을 포함하려면 전역 정책에서 설정을 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="079b9-122">You edit the settings in the global policy to include the apps that you want.</span></span> <span data-ttu-id="079b9-123">조직의 여러 사용자 그룹에 대해 Teams를 사용자 지정하기 위해 하나 이상의 사용자 지정 정책을 만들고 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="079b9-123">To customize Teams for different groups of users in your organization, create and assign one or more custom policies.</span></span>

![앱 설정 정책 페이지](media/app-setup-policies.png)

> [!NOTE]
> <span data-ttu-id="079b9-125">교육용 Teams가 있는 경우 과제 앱이 기본적으로 전역 정책에 고정되어 있는 경우에도 전역 정책에 나열되어 있는 것은 아는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="079b9-125">If you have Teams for Education, it's important to know that the Assignments app is pinned by default in the global policy even though currently, you don't see it listed in the global policy.</span></span> <span data-ttu-id="079b9-126">Teams 클라이언트의 고정된 앱 목록에 있는 네 번째 앱입니다.</span><span class="sxs-lookup"><span data-stu-id="079b9-126">It will be the fourth app in the list of pinned apps on Teams clients.</span></span>

## <a name="create-a-custom-app-setup-policy"></a><span data-ttu-id="079b9-127">사용자 지정 앱 설정 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="079b9-127">Create a custom app setup policy</span></span>

<span data-ttu-id="079b9-128">Microsoft Teams 관리 센터를 사용하여 사용자 지정 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="079b9-128">You can use the Microsoft Teams admin center to create a custom policy.</span></span>

1. <span data-ttu-id="079b9-129">Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 **Teams** 앱 설정  >  **정책으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="079b9-129">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>

2. <span data-ttu-id="079b9-130">**추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="079b9-130">Select **Add**.</span></span>

   ![앱 설정 정책 추가 페이지](media/app-setup-policies-add.png)
    
3. <span data-ttu-id="079b9-132">정책의 이름과 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="079b9-132">Enter a name and description for the policy.</span></span>

4. <span data-ttu-id="079b9-133">사용자가 Teams에 사용자 지정 앱을 업로드할지 여부에 따라 사용자 지정 앱 업로드를 설정하거나 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="079b9-133">Turn on or turn off **Upload custom apps**, depending on whether you want to let users upload custom apps to Teams.</span></span> <span data-ttu-id="079b9-134">타사 앱 허용이 전체  앱 설정에서 해제되어 있는 경우 이 설정을 변경할 [수 없습니다.](manage-apps.md#manage-org-wide-app-settings)</span><span class="sxs-lookup"><span data-stu-id="079b9-134">You can't change this setting if **Allow third-party apps** is turned off in [org-wide app settings](manage-apps.md#manage-org-wide-app-settings).</span></span>

5. <span data-ttu-id="079b9-135">사용자가 앱을 고정하여 앱 바를 개인 설정하도록 할지 여부에 따라 사용자 고정 허용을 설정하거나 해제합니다. </span><span class="sxs-lookup"><span data-stu-id="079b9-135">Turn on or turn off **Allow user pinning**, depending on whether you want to let users personalize their app bar by pinning apps to it.</span></span>

   > [!NOTE]
   > <span data-ttu-id="079b9-136">사용자 **고정** 허용 설정은 Microsoft 365 GCC(Government Community Cloud) 환경(GCC, GCC High 및 DoD)의 Teams 관리 센터에서 사용할 수 있지만 현재는 효과가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="079b9-136">The **Allow user pinning** setting is available in the Teams admin center in Microsoft 365 Government Community Cloud (GCC) environments (GCC, GCC High and DoD), but currently it has no effect.</span></span>

6. <span data-ttu-id="079b9-137">사용자용 앱(미리 **보기)을 설치하려면** 다음 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="079b9-137">To install apps for users **(in preview)**, do the following tasks:</span></span>

    1. <span data-ttu-id="079b9-138">설치된 **앱 아래에서** 앱 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="079b9-138">Under **Installed apps**, select **Add apps**.</span></span>
    
    2. <span data-ttu-id="079b9-139">설치된 앱 **추가** 창에서 Teams를 시작할 때 사용자를 위해 자동으로 설치하려는 앱을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="079b9-139">In the **Add installed apps** pane, search for the apps you want to automatically install for users when they start Teams.</span></span> <span data-ttu-id="079b9-140">앱 사용 권한 정책에 따라 앱을 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="079b9-140">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="079b9-141">앱 목록을 선택한 경우 추가를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="079b9-141">When you've chosen your list of apps, select **Add**.</span></span>

       ![설치된 앱 추가 창](media/app-setup-policies-add-installed-apps.png)

7. <span data-ttu-id="079b9-143">앱을 고정하기 위해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="079b9-143">To pin apps, do the following:</span></span>

    1. <span data-ttu-id="079b9-144">고정된 **앱에서** 앱 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="079b9-144">Under **Pinned apps**, select **Add apps**.</span></span>
    
    2. <span data-ttu-id="079b9-145">고정된  앱 추가 창에서 추가할 앱을 검색한 다음 추가를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="079b9-145">In the **Add pinned apps** pane, search for the apps you want to add, and then select **Add**.</span></span> <span data-ttu-id="079b9-146">앱 사용 권한 정책에 따라 앱을 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="079b9-146">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="079b9-147">고정할 앱 목록을 선택한 경우 추가를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="079b9-147">When you've chosen your list of apps to pin, select **Add**.</span></span>

       ![고정된 앱 추가 창](media/app-setup-policies-add-apps.png)

    3. <span data-ttu-id="079b9-149">앱을 Teams에 표시하려는 순서대로 정렬한 다음 저장을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="079b9-149">Arrange the apps in the order that you want them to appear in Teams, and then select **Save**.</span></span>

       ![고정된 앱 섹션](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a><span data-ttu-id="079b9-151">앱 설정 정책 편집</span><span class="sxs-lookup"><span data-stu-id="079b9-151">Edit an app setup policy</span></span>

<span data-ttu-id="079b9-152">Microsoft Teams 관리 센터를 사용하여 만든 전역(전체 기본) 정책 및 사용자 지정 정책을 포함하여 정책을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="079b9-152">You can use the Microsoft Teams admin center to edit a policy, including the global (Org-wide default) policy and custom policies that you create.</span></span>

1. <span data-ttu-id="079b9-153">Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 **Teams** 앱 설정  >  **정책으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="079b9-153">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>

2. <span data-ttu-id="079b9-154">정책 이름 왼쪽을 클릭하여 정책을 선택한 다음 편집을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="079b9-154">Select the policy by clicking to the left of the policy name, and then select **Edit**.</span></span>

3. <span data-ttu-id="079b9-155">여기서 원하는 내용을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="079b9-155">From here, make the changes that you want.</span></span>

4. <span data-ttu-id="079b9-156">저장을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="079b9-156">Select **Save**.</span></span>

## <a name="assign-a-custom-app-setup-policy-to-users"></a><span data-ttu-id="079b9-157">사용자에게 사용자 지정 앱 설정 정책 할당</span><span class="sxs-lookup"><span data-stu-id="079b9-157">Assign a custom app setup policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="faq"></a><span data-ttu-id="079b9-158">FAQ</span><span class="sxs-lookup"><span data-stu-id="079b9-158">FAQ</span></span>

### <a name="working-with-app-setup-policies"></a><span data-ttu-id="079b9-159">앱 설정 정책 작업</span><span class="sxs-lookup"><span data-stu-id="079b9-159">Working with app setup policies</span></span>

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="079b9-160">Microsoft Teams 관리 센터에 포함된 기본 제공 앱 설정 정책</span><span class="sxs-lookup"><span data-stu-id="079b9-160">What built-in app setup policies are included in the Microsoft Teams admin center</span></span>

- <span data-ttu-id="079b9-161">**전역(조직** 전체 기본값) : 이 기본 정책은 다른 정책을 할당하지 않는 한 조직의 모든 사용자에게 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="079b9-161">**Global (Org-wide default)**: This default policy applies to all users in your organization unless you assign another policy.</span></span> <span data-ttu-id="079b9-162">사용자에게 가장 중요한 앱을 고정하려면 전역 정책을 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="079b9-162">Edit the global policy to pin apps that are most important for your users.</span></span>

- <span data-ttu-id="079b9-163">**FrontlineWorker:** 이 정책은 Frontline Workers에 대한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="079b9-163">**FrontlineWorker**: This policy is for Frontline Workers.</span></span> <span data-ttu-id="079b9-164">조직의 일선 작업자에게 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="079b9-164">You can assign it to Frontline Workers in your organization.</span></span> <span data-ttu-id="079b9-165">만드는 사용자 지정 정책과 마찬가지로 설정이 활성화될 수 있도록 사용자에게 정책을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="079b9-165">It's important to know that like custom policies that you create, you have to assign the policy to users for the settings to be active.</span></span> <span data-ttu-id="079b9-166">자세한 내용은 이 문서의 사용자에 대한 사용자 지정 앱 설정 정책 할당 섹션으로 이동하세요. [](#assign-a-custom-app-setup-policy-to-users)</span><span class="sxs-lookup"><span data-stu-id="079b9-166">For more information, go to the [Assign a custom app setup policy to users](#assign-a-custom-app-setup-policy-to-users) section of this article.</span></span>

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a><span data-ttu-id="079b9-167">고정된 앱 추가 창에서 앱을 찾을 수 없는 이유</span><span class="sxs-lookup"><span data-stu-id="079b9-167">Why can't I find an app in the Add pinned apps pane</span></span>

<span data-ttu-id="079b9-168">일부 앱은 앱 설정 정책을 통해 Teams에 고정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="079b9-168">Not all apps can be pinned to Teams through an app setup policy.</span></span> <span data-ttu-id="079b9-169">일부 앱은 이 기능을 지원하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="079b9-169">Some apps may not support this functionality.</span></span> <span data-ttu-id="079b9-170">고정할 수 있는 앱을 찾으면 고정된 앱 추가 창에서 앱을 **검색합니다.**</span><span class="sxs-lookup"><span data-stu-id="079b9-170">To find apps that can be pinned, search for the app in the **Add pinned apps** pane.</span></span> <span data-ttu-id="079b9-171">개인 범위(정적 탭)와 봇이 있는 탭은 Teams 데스크톱 클라이언트에 고정할 수 있으며 이러한 앱은 고정된 앱 추가 창에서 사용할 **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="079b9-171">Tabs that have a personal scope (static tabs) and bots can be pinned to the Teams desktop client and these apps are available in the **Add pinned apps** pane.</span></span>

<span data-ttu-id="079b9-172">Teams 앱 스토어에는 모든 Teams 앱이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="079b9-172">Keep in mind that the Teams app store lists all Teams apps.</span></span> <span data-ttu-id="079b9-173">고정된 **앱 추가** 창에는 정책을 통해 Teams에 고정할 수 있는 앱만 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="079b9-173">The **Add pinned apps** pane includes only apps that can be pinned to Teams through a policy.</span></span>

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a><span data-ttu-id="079b9-174">저는 교육용 Teams 관리자입니다. 교육용 Teams의 앱 설정 정책에 대해 알아야 할 정보</span><span class="sxs-lookup"><span data-stu-id="079b9-174">I'm a Teams for Education admin. What do I need to know about app setup policies in Teams for Education</span></span>

<span data-ttu-id="079b9-175">교육용 Teams에서 통화 앱을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="079b9-175">The Calling app isn't available in Teams for Education.</span></span> <span data-ttu-id="079b9-176">새 사용자 지정 앱 설정 정책을 만들면 호출 앱이 앱 목록에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="079b9-176">When you create a new custom app setup policy, the Calling app is displayed in the list of apps.</span></span> <span data-ttu-id="079b9-177">그러나 앱이 Teams 클라이언트에 고정되지 않은 경우 교육용 Teams 사용자는 Teams에서 통화 앱을 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="079b9-177">However, the app isn't pinned to Teams clients and Teams for Education users won't see the Calls app in Teams.</span></span>

#### <a name="how-many-pinned-apps-can-be-added-to-a-policy"></a><span data-ttu-id="079b9-178">정책에 추가할 수 있는 고정된 앱 수</span><span class="sxs-lookup"><span data-stu-id="079b9-178">How many pinned apps can be added to a policy</span></span>

<span data-ttu-id="079b9-179">Teams 모바일 클라이언트(iOS 및 Android)에 최소 두 개의 앱을 고정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="079b9-179">A minimum of two apps must be pinned to the Teams mobile clients (iOS and Android).</span></span> <span data-ttu-id="079b9-180">정책에 두 개 미만의 앱이 있는 경우 모바일 클라이언트는 정책 설정을 반영하지 않고 기존 구성을 계속 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="079b9-180">If a policy has fewer than two apps, the mobile clients won't reflect the policy settings and instead will continue to use the existing configuration.</span></span>

<span data-ttu-id="079b9-181">정책에 추가할 수 있는 고정된 앱 수에는 제한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="079b9-181">There's no limit on the number of pinned apps you can add to a policy.</span></span>

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a><span data-ttu-id="079b9-182">정책 변경 내용을 적용하는 데 시간이 얼마나 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="079b9-182">How long does it take for policy changes to take effect</span></span>

<span data-ttu-id="079b9-183">정책을 편집하거나 할당한 후 변경 내용을 적용하는 데 몇 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="079b9-183">After you edit or assign a policy, it can take a few hours for changes to take effect.</span></span>

### <a name="user-experience"></a><span data-ttu-id="079b9-184">사용자 환경</span><span class="sxs-lookup"><span data-stu-id="079b9-184">User experience</span></span>

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a><span data-ttu-id="079b9-185">사용자가 Teams에서 고정된 모든 앱을 보는 방법</span><span class="sxs-lookup"><span data-stu-id="079b9-185">How can users see all their pinned apps in Teams</span></span>

<span data-ttu-id="079b9-186">사용자에 대해 고정된 모든 앱을 보기 위해 사용자는 설치된 앱 수 및 Teams 클라이언트 창의 크기에 따라 다음을 실행해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="079b9-186">To view all apps that are pinned for a user, users might have to do the following depending on the number of installed apps and the size of their Teams client window.</span></span>

|<span data-ttu-id="079b9-187">Teams 데스크톱 클라이언트</span><span class="sxs-lookup"><span data-stu-id="079b9-187">Teams desktop client</span></span> |<span data-ttu-id="079b9-188">Teams 모바일 클라이언트</span><span class="sxs-lookup"><span data-stu-id="079b9-188">Teams mobile client</span></span> |
|---------|---------|
|<span data-ttu-id="079b9-189">Teams 측면의 앱 바에서 ... **더 많은 앱.**</span><span class="sxs-lookup"><span data-stu-id="079b9-189">In the app bar on the side of Teams, select **... More apps**.</span></span>| <span data-ttu-id="079b9-190">Teams 아래쪽에 있는 앱 바에서 위쪽으로 손가락을 다.</span><span class="sxs-lookup"><span data-stu-id="079b9-190">In the app bar near the bottom of Teams, swipe up.</span></span>|
|![Teams 데스크톱 클라이언트의 추가 앱](media/app-setup-policies-desktop-more-apps.png)<br>   |![Teams 모바일 클라이언트에서 더 많은 앱](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a><span data-ttu-id="079b9-193">Teams 모바일 경험에 대해 알아야 할 것</span><span class="sxs-lookup"><span data-stu-id="079b9-193">What do I need to know about the Teams mobile experience</span></span>

<span data-ttu-id="079b9-194">Teams 모바일 클라이언트(iOS 및 Android)는 현재 정적 탭이 있는 개인 앱을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="079b9-194">The Teams mobile clients (iOS and Android) currently don't support personal apps with static tabs.</span></span> <span data-ttu-id="079b9-195">정책에 설정된 앱에 따라 Teams 데스크톱 클라이언트에 고정된 앱이 Teams 모바일 클라이언트에 나타나지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="079b9-195">Depending on the apps set in the policy, apps pinned to the Teams desktop client might not appear in the Teams mobile clients.</span></span> <span data-ttu-id="079b9-196">개인 봇은 모바일 클라이언트의 채팅에 계속 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="079b9-196">Personal bots will still appear in Chat on mobile clients.</span></span>

<span data-ttu-id="079b9-197">Teams 모바일 클라이언트를 사용하면 사용자는 활동, 채팅, Teams와 같은 핵심 Teams 앱을 볼 수 있으며 Shifts와 같은 Microsoft의 일부 파티 앱을 고정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="079b9-197">With the Teams mobile clients, users will see core Teams apps such as Activity, Chat, and Teams, and you can pin some first-party apps from Microsoft, such as Shifts.</span></span>

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a><span data-ttu-id="079b9-198">사용자가 정책을 통해 고정된 앱의 순서를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="079b9-198">Can users change the order of apps pinned through a policy</span></span>

<span data-ttu-id="079b9-199">사용자 고정 허용 옵션이 켜져 있는 경우 Teams 데스크톱  및 모바일 클라이언트에서 고정된 앱의 순서를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="079b9-199">Users can change the order of their pinned apps on Teams desktop and mobile clients if the **Allow user pinning** option is turned on.</span></span> <span data-ttu-id="079b9-200">사용자는 Teams 웹 클라이언트에서 고정된 앱의 순서를 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="079b9-200">Users can't change the order of their pinned apps on Teams web clients.</span></span>

#### <a name="does-user-pinning-take-precedence"></a><span data-ttu-id="079b9-201">사용자 고정이 우선적으로 적용</span><span class="sxs-lookup"><span data-stu-id="079b9-201">Does user pinning take precedence</span></span>

<span data-ttu-id="079b9-202">사용자에게 할당된 앱 설정 정책이 사용자 앱 고정을 차단하도록 변경된 경우 Teams는 앱 바에 고정된 모든 앱을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="079b9-202">If the app setup policy assigned to the user is changed to block user app pinning, Teams removes any apps pinned to the app bar.</span></span> <span data-ttu-id="079b9-203">정책이 사용자 앱 고정을 허용하도록 변경된 경우 사용자는 이전에 고정된 앱을 다시 고정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="079b9-203">If the policy is then changed to allow user app pinning, users must re-pin their previously pinned apps.</span></span>

### <a name="custom-teams-apps"></a><span data-ttu-id="079b9-204">사용자 지정 Teams 앱</span><span class="sxs-lookup"><span data-stu-id="079b9-204">Custom Teams apps</span></span>

#### <a name="my-organization-built-a-custom-teams-app-and-published-it-either-to-appsource-or-the-tenant-app-catalog-but-the-app-icon-isnt-displayed-as-expected-when-the-app-is-pinned-to-the-app-bar-in-teams-how-do-i-fix-it"></a><span data-ttu-id="079b9-205">조직에서 사용자 지정 Teams 앱을 구축하여 AppSource 또는 테넌트 앱 카탈로그에 게시했지만 앱이 Teams의 앱 바에 고정되어 있는 경우 앱 아이콘이 예상대로 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="079b9-205">My organization built a custom Teams app and published it, either to AppSource or the tenant app catalog, but the app icon isn't displayed as expected when the app is pinned to the app bar in Teams.</span></span> <span data-ttu-id="079b9-206">해결 방법</span><span class="sxs-lookup"><span data-stu-id="079b9-206">How do I fix it</span></span>

<span data-ttu-id="079b9-207">앱을 제출하기 전에 로고 지침을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="079b9-207">Make sure that you follow the logo guidelines before you submit the app.</span></span> <span data-ttu-id="079b9-208">자세한 내용은 판매자 대시보드 [제출에 대한 검사 목록을 참조하세요.](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview)</span><span class="sxs-lookup"><span data-stu-id="079b9-208">To learn more, see [Checklist for Seller Dashboard submission](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview).</span></span>

## <a name="related-topics"></a><span data-ttu-id="079b9-209">관련 항목</span><span class="sxs-lookup"><span data-stu-id="079b9-209">Related topics</span></span>

[<span data-ttu-id="079b9-210">Teams의 앱에 대한 관리 설정</span><span class="sxs-lookup"><span data-stu-id="079b9-210">Admin settings for apps in Teams</span></span>](admin-settings.md)

[<span data-ttu-id="079b9-211">Teams에서 사용자에게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="079b9-211">Assign policies to your users in Teams</span></span>](assign-policies.md)
