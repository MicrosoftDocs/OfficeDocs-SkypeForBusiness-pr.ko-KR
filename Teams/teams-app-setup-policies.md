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
description: 조직의 사용자를 위해 Microsoft Teams에서 앱 설치 정책을 사용 및 관리하는 방법에 대해 자세히 알아보고 있습니다.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: ee50af6dec780480b8efdbf39dabb8e52ff03f3a
ms.sourcegitcommit: cfef9dd41cac0df83bd02b35036d8f8f1b472feb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51697713"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a><span data-ttu-id="c0e26-103">Microsoft Teams에서 앱 설정 정책 관리</span><span class="sxs-lookup"><span data-stu-id="c0e26-103">Manage app setup policies in Microsoft Teams</span></span>

<span data-ttu-id="c0e26-104">관리자는 앱 설정 정책을 사용하여 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0e26-104">As an admin, you can use app setup policies to do the following tasks:</span></span>

- <span data-ttu-id="c0e26-105">팀을 사용자 지정하여 사용자에게 가장 중요한 앱을 강조 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="c0e26-105">Customize Teams to highlight the apps that are most important for your users.</span></span> <span data-ttu-id="c0e26-106">앱을 선택하고 표시하는 순서를 고정하고 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0e26-106">You choose the apps to pin and set the order that they appear.</span></span> <span data-ttu-id="c0e26-107">앱을 고정하면 타사 또는 조직의 개발자가 구축한 앱을 포함하여 조직의 사용자가 필요로 하는 앱을 선보일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0e26-107">Pinning apps lets you showcase apps that users in your organization need, including apps built by third parties or by developers in your organization.</span></span>
- <span data-ttu-id="c0e26-108">사용자가 앱을 Teams에 고정할 수 있는지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="c0e26-108">Control whether users can pin apps to Teams.</span></span>
- <span data-ttu-id="c0e26-109">사용자를 대신하여 앱을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="c0e26-109">Install apps on behalf of users.</span></span> <span data-ttu-id="c0e26-110">Teams를 시작할 때 기본적으로 사용자에게 설치되는 앱을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0e26-110">You choose which apps are installed by default for users when they start Teams.</span></span> <span data-ttu-id="c0e26-111">사용자에게 할당된 앱 사용 권한 정책이 허용하는 경우 사용자가 앱을 직접 설치할 수 있습니다. [](teams-app-permission-policies.md)</span><span class="sxs-lookup"><span data-stu-id="c0e26-111">Keep in mind that users can still install apps themselves if the [app permission policy](teams-app-permission-policies.md) that's assigned to them allows it.</span></span>

> [!Note]
> <span data-ttu-id="c0e26-112">관리자가 설치한 앱의 경우 사용자는 해당 앱을 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c0e26-112">For apps installed by admins, users can't uninstall those apps.</span></span>

<span data-ttu-id="c0e26-113">앱이 앱 표시줄에 고정됩니다. 이 막대는 Teams 데스크톱 클라이언트의 측면과 Teams 모바일 클라이언트(iOS 및 Android)의 아래쪽에 있는 막대입니다.</span><span class="sxs-lookup"><span data-stu-id="c0e26-113">Apps are pinned to the app bar, which is the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients (iOS and Android).</span></span>

|<span data-ttu-id="c0e26-114">Teams 데스크톱 클라이언트</span><span class="sxs-lookup"><span data-stu-id="c0e26-114">Teams desktop client</span></span>  |<span data-ttu-id="c0e26-115">Teams 모바일 클라이언트</span><span class="sxs-lookup"><span data-stu-id="c0e26-115">Teams mobile client</span></span> |
|---------|---------|
|![Teams 데스크톱 클라이언트](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![Teams 모바일 클라이언트](media/mobile-app-ui.png)      |

<span data-ttu-id="c0e26-118">관리자가 설치한 앱을 표시하려면 앱 표시줄에서 ...를 **선택합니다.** Teams 데스크톱 및 웹 클라이언트의 더 많은 앱과 모바일 클라이언트에서 스 와이프합니다.</span><span class="sxs-lookup"><span data-stu-id="c0e26-118">To see the apps installed by admins, in the app bar, users select **... More apps** in the Teams desktop and web clients and swipe up in the mobile clients.</span></span>

<span data-ttu-id="c0e26-119">Microsoft Teams 관리 센터에서 앱 설정 정책을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="c0e26-119">You manage app setup policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="c0e26-120">전역(Org-wide 기본값) 정책을 사용하거나 사용자 지정 정책을 만들고 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="c0e26-120">Use the global (Org-wide default) policy or create and assign custom policies.</span></span>  <span data-ttu-id="c0e26-121">사용자 지정 정책을 만들고 할당하지 않으면 조직의 사용자에게 전역 정책이 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0e26-121">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="c0e26-122">이러한 정책을 관리하려면 전역 관리자 또는 Teams 서비스 관리자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0e26-122">You must be a global admin or Teams service admin to manage these policies.</span></span>

<span data-ttu-id="c0e26-123">전역 정책의 설정을 편집하여 원하는 앱을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="c0e26-123">You edit the settings in the global policy to include the apps that you want.</span></span> <span data-ttu-id="c0e26-124">조직의 다른 사용자 그룹에 대해 Teams를 사용자 지정하기 위해 하나 이상의 사용자 지정 정책을 만들고 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="c0e26-124">To customize Teams for different groups of users in your organization, create and assign one or more custom policies.</span></span>

![앱 설정 정책 페이지](media/app-setup-policies.png)

> [!NOTE]
> <span data-ttu-id="c0e26-126">교육용 Teams가 있는 경우 할당 앱이 현재 글로벌 정책에 기본적으로 고정되어 있는 경우 전역 정책에 나열되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c0e26-126">If you have Teams for Education, it's important to know that the Assignments app is pinned by default in the global policy even though currently, you don't see it listed in the global policy.</span></span> <span data-ttu-id="c0e26-127">Teams 클라이언트의 고정된 앱 목록에 있는 네 번째 앱입니다.</span><span class="sxs-lookup"><span data-stu-id="c0e26-127">It will be the fourth app in the list of pinned apps on Teams clients.</span></span>

## <a name="create-a-custom-app-setup-policy"></a><span data-ttu-id="c0e26-128">사용자 지정 앱 설정 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="c0e26-128">Create a custom app setup policy</span></span>

<span data-ttu-id="c0e26-129">Microsoft Teams 관리 센터를 사용하여 사용자 지정 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0e26-129">You can use the Microsoft Teams admin center to create a custom policy.</span></span>

1. <span data-ttu-id="c0e26-130">Microsoft Teams 관리 센터의 왼쪽 탐색에서 **Teams 앱** 설치 정책  >  **으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="c0e26-130">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>

2. <span data-ttu-id="c0e26-131">**추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c0e26-131">Select **Add**.</span></span>

   ![앱 설정 정책 추가 페이지](media/app-setup-policies-add.png)

3. <span data-ttu-id="c0e26-133">정책의 이름과 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c0e26-133">Enter a name and description for the policy.</span></span>

4. <span data-ttu-id="c0e26-134">사용자가 Teams에 사용자 지정 앱을 업로드할지 여부에 따라 사용자 지정 앱 업로드를 설정하거나 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="c0e26-134">Turn on or turn off **Upload custom apps**, depending on whether you want to let users upload custom apps to Teams.</span></span> <span data-ttu-id="c0e26-135">타사 앱 허용이 [org-wide](manage-apps.md#manage-org-wide-app-settings)앱 설정에서 해제된 경우 이 설정을 변경할 수 없습니다. </span><span class="sxs-lookup"><span data-stu-id="c0e26-135">You can't change this setting if **Allow third-party apps** is turned off in [org-wide app settings](manage-apps.md#manage-org-wide-app-settings).</span></span>

5. <span data-ttu-id="c0e26-136">앱에 앱을 고정하여 사용자가 앱 표시줄을 개인 설정하도록 할지 여부에 따라 사용자 고정 허용을 설정하거나 끄습니다.</span><span class="sxs-lookup"><span data-stu-id="c0e26-136">Turn on or turn off **Allow user pinning**, depending on whether you want to let users personalize their app bar by pinning apps to it.</span></span>

   > [!NOTE]
   > <span data-ttu-id="c0e26-137">사용자 **고정** 허용 설정은 Microsoft 365 GCC(정부 커뮤니티 클라우드) 환경(GCC, GCC High 및 DoD)의 Teams 관리 센터에서 사용할 수 있지만 현재는 효과가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c0e26-137">The **Allow user pinning** setting is available in the Teams admin center in Microsoft 365 Government Community Cloud (GCC) environments (GCC, GCC High and DoD), but currently it has no effect.</span></span>

6. <span data-ttu-id="c0e26-138">사용자를 위한 앱을 설치하려면 다음 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c0e26-138">To install apps for users, do the following tasks:</span></span>

    1. <span data-ttu-id="c0e26-139">설치된 **앱에서** 앱 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c0e26-139">Under **Installed apps**, select **Add apps**.</span></span>

    2. <span data-ttu-id="c0e26-140">설치된 **앱** 추가 창에서 Teams를 시작할 때 자동으로 설치하려는 앱을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="c0e26-140">In the **Add installed apps** pane, search for the apps you want to automatically install for users when they start Teams.</span></span> <span data-ttu-id="c0e26-141">앱 사용 권한 정책에 따라 앱을 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0e26-141">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="c0e26-142">앱 목록을 선택한 경우 추가를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c0e26-142">When you've chosen your list of apps, select **Add**.</span></span>

       ![설치된 앱 추가 창](media/app-setup-policies-add-installed-apps.png)

7. <span data-ttu-id="c0e26-144">앱을 고정하기 위해 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c0e26-144">To pin apps, do the following steps:</span></span>

    1. <span data-ttu-id="c0e26-145">고정된 **앱 아래에서** 앱 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c0e26-145">Under **Pinned apps**, select **Add apps**.</span></span>

    2. <span data-ttu-id="c0e26-146">고정된  앱 추가 창에서 추가할 앱을 검색한 다음 추가를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c0e26-146">In the **Add pinned apps** pane, search for the apps you want to add, and then select **Add**.</span></span> <span data-ttu-id="c0e26-147">앱 사용 권한 정책에 따라 앱을 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0e26-147">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="c0e26-148">고정할 앱 목록을 선택한 경우 추가를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c0e26-148">When you've chosen your list of apps to pin, select **Add**.</span></span>

       ![고정된 앱 추가 창](media/app-setup-policies-add-apps.png)

    3. <span data-ttu-id="c0e26-150">앱을 Teams에 표시하려는 순서대로 정렬한 다음 저장을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c0e26-150">Arrange the apps in the order that you want them to appear in Teams, and then select **Save**.</span></span>

       ![고정된 앱 섹션](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a><span data-ttu-id="c0e26-152">앱 설정 정책 편집</span><span class="sxs-lookup"><span data-stu-id="c0e26-152">Edit an app setup policy</span></span>

<span data-ttu-id="c0e26-153">Microsoft Teams 관리 센터를 사용하여 만든 전역(Org-wide default) 정책 및 사용자 지정 정책을 포함하여 정책을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0e26-153">You can use the Microsoft Teams admin center to edit a policy, including the global (Org-wide default) policy and custom policies that you create.</span></span>

1. <span data-ttu-id="c0e26-154">Microsoft Teams 관리 센터의 왼쪽 탐색에서 **Teams 앱** 설치 정책  >  **으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="c0e26-154">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>

2. <span data-ttu-id="c0e26-155">정책 이름 왼쪽을 클릭하여 정책을 선택한 다음 **편집** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c0e26-155">Select the policy by clicking to the left of the policy name, and then select **Edit**.</span></span>

3. <span data-ttu-id="c0e26-156">여기서 원하는 대로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="c0e26-156">From here, make the changes that you want.</span></span>

4. <span data-ttu-id="c0e26-157">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c0e26-157">Select **Save**.</span></span>

## <a name="assign-a-custom-app-setup-policy-to-users"></a><span data-ttu-id="c0e26-158">사용자에게 사용자 지정 앱 설정 정책 할당</span><span class="sxs-lookup"><span data-stu-id="c0e26-158">Assign a custom app setup policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="faq"></a><span data-ttu-id="c0e26-159">FAQ</span><span class="sxs-lookup"><span data-stu-id="c0e26-159">FAQ</span></span>

### <a name="working-with-app-setup-policies"></a><span data-ttu-id="c0e26-160">앱 설정 정책 작업</span><span class="sxs-lookup"><span data-stu-id="c0e26-160">Working with app setup policies</span></span>

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="c0e26-161">Microsoft Teams 관리 센터에 포함된 기본 제공 앱 설정 정책</span><span class="sxs-lookup"><span data-stu-id="c0e26-161">What built-in app setup policies are included in the Microsoft Teams admin center</span></span>

- <span data-ttu-id="c0e26-162">**전역(조직** 전체 기본값) : 이 기본 정책은 다른 정책을 할당하지 않는 한 조직의 모든 사용자에게 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0e26-162">**Global (Org-wide default)**: This default policy applies to all users in your organization unless you assign another policy.</span></span> <span data-ttu-id="c0e26-163">전역 정책을 편집하여 사용자에게 가장 중요한 앱을 고정합니다.</span><span class="sxs-lookup"><span data-stu-id="c0e26-163">Edit the global policy to pin apps that are most important for your users.</span></span>

- <span data-ttu-id="c0e26-164">**FrontlineWorker**: 이 정책은 Frontline Workers에 대한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c0e26-164">**FrontlineWorker**: This policy is for Frontline Workers.</span></span> <span data-ttu-id="c0e26-165">조직의 Frontline Workers에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0e26-165">You can assign it to Frontline Workers in your organization.</span></span> <span data-ttu-id="c0e26-166">만드는 사용자 지정 정책과 마찬가지로 설정이 활성화될 수 있도록 사용자에게 정책을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0e26-166">It's important to know that like custom policies that you create, you have to assign the policy to users for the settings to be active.</span></span> <span data-ttu-id="c0e26-167">자세한 내용은 이 문서의 사용자에게 사용자 지정 앱 설정 정책 할당 섹션으로 이동하세요. [](#assign-a-custom-app-setup-policy-to-users)</span><span class="sxs-lookup"><span data-stu-id="c0e26-167">For more information, go to the [Assign a custom app setup policy to users](#assign-a-custom-app-setup-policy-to-users) section of this article.</span></span>

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a><span data-ttu-id="c0e26-168">고정된 앱 추가 창에서 앱을 찾을 수 없는 이유</span><span class="sxs-lookup"><span data-stu-id="c0e26-168">Why can't I find an app in the Add pinned apps pane</span></span>

<span data-ttu-id="c0e26-169">앱 설정 정책을 통해 모든 앱을 Teams에 고정할 수 있는 것은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c0e26-169">Not all apps can be pinned to Teams through an app setup policy.</span></span> <span data-ttu-id="c0e26-170">일부 앱은 이 기능을 지원하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0e26-170">Some apps may not support this functionality.</span></span> <span data-ttu-id="c0e26-171">고정할 수 있는 앱을 찾으면 고정된 앱 추가 창에서 앱을 **검색합니다.**</span><span class="sxs-lookup"><span data-stu-id="c0e26-171">To find apps that can be pinned, search for the app in the **Add pinned apps** pane.</span></span> <span data-ttu-id="c0e26-172">개인 범위(고정 탭)와 봇이 있는 탭은 Teams 데스크톱 클라이언트에 고정할 수 있으며 이러한 앱은 고정된 앱 추가 창에서 **사용할 수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0e26-172">Tabs that have a personal scope (static tabs) and bots can be pinned to the Teams desktop client and these apps are available in the **Add pinned apps** pane.</span></span>

<span data-ttu-id="c0e26-173">Teams 앱 스토어에는 모든 Teams 앱이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0e26-173">Keep in mind that the Teams app store lists all Teams apps.</span></span> <span data-ttu-id="c0e26-174">고정된 **앱** 추가 창에는 정책을 통해 Teams에 고정할 수 있는 앱만 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0e26-174">The **Add pinned apps** pane includes only apps that can be pinned to Teams through a policy.</span></span>

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a><span data-ttu-id="c0e26-175">저는 교육용 Teams 관리자입니다. Teams for Education의 앱 설정 정책에 대해 알아야 할 일</span><span class="sxs-lookup"><span data-stu-id="c0e26-175">I'm a Teams for Education admin. What do I need to know about app setup policies in Teams for Education</span></span>

<span data-ttu-id="c0e26-176">전화 걸기 앱은 교육용 Teams에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c0e26-176">The Calling app isn't available in Teams for Education.</span></span> <span data-ttu-id="c0e26-177">새 사용자 지정 앱 설정 정책을 만들 때 호출 앱이 앱 목록에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0e26-177">When you create a new custom app setup policy, the Calling app is displayed in the list of apps.</span></span> <span data-ttu-id="c0e26-178">그러나 앱이 Teams 클라이언트에 고정되지 않습니다. 교육용 Teams 사용자는 Teams에서 호출 앱이 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c0e26-178">However, the app isn't pinned to Teams clients and Teams for Education users won't see the Calls app in Teams.</span></span>

#### <a name="how-many-pinned-apps-can-be-added-to-a-policy"></a><span data-ttu-id="c0e26-179">정책에 추가할 수 있는 고정된 앱 수</span><span class="sxs-lookup"><span data-stu-id="c0e26-179">How many pinned apps can be added to a policy</span></span>

<span data-ttu-id="c0e26-180">Teams 모바일 클라이언트(iOS 및 Android)에 최소 2개의 앱을 고정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0e26-180">A minimum of two apps must be pinned to the Teams mobile clients (iOS and Android).</span></span> <span data-ttu-id="c0e26-181">정책에 앱이 두 개 미만인 경우 모바일 클라이언트는 정책 설정을 반영하지 않고 기존 구성을 계속 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c0e26-181">If a policy has fewer than two apps, the mobile clients won't reflect the policy settings and instead will continue to use the existing configuration.</span></span>

<span data-ttu-id="c0e26-182">정책에 추가할 수 있는 고정된 앱 수에는 제한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c0e26-182">There's no limit on the number of pinned apps you can add to a policy.</span></span>

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a><span data-ttu-id="c0e26-183">정책 변경이 적용하는 데 얼마나 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0e26-183">How long does it take for policy changes to take effect</span></span>

<span data-ttu-id="c0e26-184">정책을 편집하거나 할당한 후 변경 내용을 적용하는 데 몇 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0e26-184">After you edit or assign a policy, it can take a few hours for changes to take effect.</span></span>

### <a name="user-experience"></a><span data-ttu-id="c0e26-185">사용자 환경</span><span class="sxs-lookup"><span data-stu-id="c0e26-185">User experience</span></span>

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a><span data-ttu-id="c0e26-186">사용자가 Teams에서 고정된 모든 앱을 볼 수 있는 방법</span><span class="sxs-lookup"><span data-stu-id="c0e26-186">How can users see all their pinned apps in Teams</span></span>

<span data-ttu-id="c0e26-187">사용자에 대해 고정된 모든 앱을 표시하기 위해 사용자는 설치된 앱 수와 Teams 클라이언트 창의 크기에 따라 다음을 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0e26-187">To view all apps that are pinned for a user, users might have to do the following depending on the number of installed apps and the size of their Teams client window.</span></span>

|<span data-ttu-id="c0e26-188">Teams 데스크톱 클라이언트</span><span class="sxs-lookup"><span data-stu-id="c0e26-188">Teams desktop client</span></span> |<span data-ttu-id="c0e26-189">Teams 모바일 클라이언트</span><span class="sxs-lookup"><span data-stu-id="c0e26-189">Teams mobile client</span></span> |
|---------|---------|
|<span data-ttu-id="c0e26-190">Teams 쪽의 앱 표시줄에서 ...를 **선택합니다. 더 많은 앱**.</span><span class="sxs-lookup"><span data-stu-id="c0e26-190">In the app bar on the side of Teams, select **... More apps**.</span></span>| <span data-ttu-id="c0e26-191">Teams의 아래쪽에 있는 앱 표시줄에서 위쪽으로 으로 아</span><span class="sxs-lookup"><span data-stu-id="c0e26-191">In the app bar near the bottom of Teams, swipe up.</span></span>|
|![Teams 데스크톱 클라이언트의 더 많은 앱](media/app-setup-policies-desktop-more-apps.png)<br>   |![Teams 모바일 클라이언트에서 더 많은 앱](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a><span data-ttu-id="c0e26-194">Teams 모바일 경험에 대해 알아야 할 일</span><span class="sxs-lookup"><span data-stu-id="c0e26-194">What do I need to know about the Teams mobile experience</span></span>

<span data-ttu-id="c0e26-195">현재 Teams 모바일 클라이언트(iOS 및 Android)는 정적 탭이 있는 개인 앱을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c0e26-195">The Teams mobile clients (iOS and Android) currently don't support personal apps with static tabs.</span></span> <span data-ttu-id="c0e26-196">정책에 설정된 앱에 따라 Teams 데스크톱 클라이언트에 고정된 앱이 Teams 모바일 클라이언트에 나타나지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0e26-196">Depending on the apps set in the policy, apps pinned to the Teams desktop client might not appear in the Teams mobile clients.</span></span> <span data-ttu-id="c0e26-197">모바일 클라이언트의 채팅에 개인 봇이 계속 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0e26-197">Personal bots will still appear in Chat on mobile clients.</span></span>

<span data-ttu-id="c0e26-198">Teams 모바일 클라이언트를 사용하면 사용자는 활동, 채팅, Teams와 같은 핵심 Teams 앱을 볼 수 있으며 Shifts와 같은 Microsoft의 일부 파티 앱을 고정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0e26-198">With the Teams mobile clients, users will see core Teams apps such as Activity, Chat, and Teams, and you can pin some first-party apps from Microsoft, such as Shifts.</span></span>

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a><span data-ttu-id="c0e26-199">사용자가 정책을 통해 고정된 앱의 순서를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0e26-199">Can users change the order of apps pinned through a policy</span></span>

<span data-ttu-id="c0e26-200">사용자 고정 허용 옵션이 켜져 있는 경우 Teams 데스크톱  및 모바일 클라이언트에서 고정된 앱의 순서를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0e26-200">Users can change the order of their pinned apps on Teams desktop and mobile clients if the **Allow user pinning** option is turned on.</span></span> <span data-ttu-id="c0e26-201">사용자는 Teams 웹 클라이언트에서 고정된 앱의 순서를 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c0e26-201">Users can't change the order of their pinned apps on Teams web clients.</span></span>

#### <a name="does-user-pinning-take-precedence"></a><span data-ttu-id="c0e26-202">사용자 고정이 우선 순위를 적용하는가</span><span class="sxs-lookup"><span data-stu-id="c0e26-202">Does user pinning take precedence</span></span>

<span data-ttu-id="c0e26-203">관리자 핀은 항상 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="c0e26-203">Admin pins always take precedence.</span></span> <span data-ttu-id="c0e26-204">사용자 **고정** 허용 옵션이 켜져 있는 경우 사용자는 고정된 앱을 관리자 고정 앱 아래에 유지하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0e26-204">If the **Allow user pinning** option is turned on, then users will retain their pinned apps below admin pinned apps.</span></span> <span data-ttu-id="c0e26-205">사용자 **고정** 허용 옵션이 해제된 경우 사용자가 기존 핀을 잃고 관리자 고정된 앱만 앱 표시줄에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0e26-205">If the **Allow user pinning** option is turned off, then users will lose their pre-existing pins, and only admin-pinned apps will be present in the app bar.</span></span>

### <a name="custom-teams-apps"></a><span data-ttu-id="c0e26-206">사용자 지정 Teams 앱</span><span class="sxs-lookup"><span data-stu-id="c0e26-206">Custom Teams apps</span></span>

<span data-ttu-id="c0e26-207">내 조직은 사용자 지정 Teams 앱을 만들어 AppSource 또는 테넌트 앱 카탈로그에 게시했지만 앱이 Teams의 앱 표시줄에 고정될 때 앱 아이콘이 예상대로 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c0e26-207">My organization built a custom Teams app and published it, either to AppSource or the tenant app catalog, but the app icon isn't displayed as expected when the app is pinned to the app bar in Teams.</span></span> <span data-ttu-id="c0e26-208">해결 방법</span><span class="sxs-lookup"><span data-stu-id="c0e26-208">How do I fix it</span></span>

<span data-ttu-id="c0e26-209">앱을 제출하기 전에 로고 지침을 준수해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0e26-209">Make sure that you follow the logo guidelines before you submit the app.</span></span> <span data-ttu-id="c0e26-210">자세한 내용은 판매자 대시보드 제출 [확인 목록을 참조하세요.](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview)</span><span class="sxs-lookup"><span data-stu-id="c0e26-210">To learn more, see [Checklist for Seller Dashboard submission](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview).</span></span>

## <a name="related-topics"></a><span data-ttu-id="c0e26-211">관련 항목</span><span class="sxs-lookup"><span data-stu-id="c0e26-211">Related topics</span></span>

[<span data-ttu-id="c0e26-212">Teams의 앱에 대한 관리 설정</span><span class="sxs-lookup"><span data-stu-id="c0e26-212">Admin settings for apps in Teams</span></span>](admin-settings.md)

[<span data-ttu-id="c0e26-213">Teams에서 사용자에게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="c0e26-213">Assign policies to your users in Teams</span></span>](assign-policies.md)
