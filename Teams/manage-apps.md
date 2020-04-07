---
title: Microsoft 팀 관리 센터에서 앱 관리
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: ritikag
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.manageapps.overview
description: Microsoft 팀 관리 센터의 앱 관리 페이지에서 팀 앱을 관리 하는 방법에 대해 알아봅니다.
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 5e261dfd6f23ec298e354a7732a9a1afa9d6b22e
ms.sourcegitcommit: f3390e27bb63b66d1c4fb4f8afbda6b814fbbb5b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/07/2020
ms.locfileid: "43170556"
---
<a name="manage-your-apps-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="0f2ad-103">Microsoft 팀 관리 센터에서 앱 관리</span><span class="sxs-lookup"><span data-stu-id="0f2ad-103">Manage your apps in the Microsoft Teams admin center</span></span>
======================================================

<span data-ttu-id="0f2ad-104">관리자는 Microsoft 팀 관리 센터의 **앱 관리** 페이지에서 조직의 앱 카탈로그에 있는 모든 팀 앱을 보고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f2ad-104">As an admin, the **Manage apps** page in the Microsoft Teams admin center is where you view and manage all Teams apps in your organization's app catalog.</span></span> <span data-ttu-id="0f2ad-105">여기서는 앱의 조직 수준 상태 및 속성을 확인 하 고, 테 넌 트 앱 카탈로그에 새 사용자 지정 앱을 업로드 하 고, 조직 수준의 앱을 차단 하거나 허용 하 고, 조직 전체 앱 설정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f2ad-105">Here, you can see the org-level status and properties of apps, upload new custom apps to your tenant app catalog, block or allow apps at the org level, and manage org-wide app settings.</span></span>

<span data-ttu-id="0f2ad-106">**앱 관리** 페이지는 테 넌 트 카탈로그에서 사용 가능한 모든 앱에 대 한 보기를 제공 하 여 조직 전체에서 허용 하거나 차단 하는 앱을 결정 하는 데 필요한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f2ad-106">The **Manage apps** page gives you a view into all available apps in your tenant catalog, providing you with the information you need to decide which apps to allow or block across your organization.</span></span> <span data-ttu-id="0f2ad-107">그런 다음 [앱 권한 정책](teams-app-permission-policies.md), [앱 설치 정책](teams-app-setup-policies.md), [사용자 지정 앱 정책 및 설정을](teams-custom-app-policies-and-settings.md) 사용 하 여 조직의 특정 사용자에 대 한 앱 환경을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f2ad-107">You can then use [app permission policies](teams-app-permission-policies.md), [app setup policies](teams-app-setup-policies.md), and [custom app policies and settings](teams-custom-app-policies-and-settings.md) to configure the app experience for specific users in your organization.</span></span>

<span data-ttu-id="0f2ad-108">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **팀 앱** > 으로**앱 관리**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f2ad-108">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span> <span data-ttu-id="0f2ad-109">페이지에 액세스 하려면 전역 관리자 또는 팀 서비스 관리자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f2ad-109">You must be a global admin or Teams service admin to access the page.</span></span>

## <a name="view-apps-in-your-tenant-app-catalog"></a><span data-ttu-id="0f2ad-110">테 넌 트 앱 카탈로그에서 앱 보기</span><span class="sxs-lookup"><span data-stu-id="0f2ad-110">View apps in your tenant app catalog</span></span>

<span data-ttu-id="0f2ad-111">각 앱에 대 한 다음 정보를 포함 하 여 테 넌 트 앱 카탈로그의 모든 앱을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f2ad-111">You can view every app in your tenant app catalog including the following information about each app.</span></span>

![관리 되는 앱 페이지의 스크린샷](media/manage-apps.png)

- <span data-ttu-id="0f2ad-113">**Name**: 앱 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="0f2ad-113">**Name**: The app name.</span></span> <span data-ttu-id="0f2ad-114">앱에 대 한 자세한 정보를 보려면 앱 이름을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f2ad-114">Click the app name to see more information about the app.</span></span> <span data-ttu-id="0f2ad-115">여기에는 앱에 대 한 설명, 허용 또는 차단 여부, 버전, 앱에 적용 되는 범주, 인증 상태, 지원 되는 기능, 앱 ID가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f2ad-115">This includes a description of the app, whether it's allowed or blocked, version, categories that apply to the app, certification status, supported capabilities, and app ID.</span></span> <span data-ttu-id="0f2ad-116">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0f2ad-116">Here's an example:</span></span><br><span data-ttu-id="0f2ad-117"> 
![앱에 대 한 앱 세부 정보 페이지 스크린샷](media/manage-apps-app-details.png)</span><span class="sxs-lookup"><span data-stu-id="0f2ad-117"> 
![Screenshot of the apps details page for an app](media/manage-apps-app-details.png)</span></span>
- <span data-ttu-id="0f2ad-118">**인증**: 앱이 인증을 통과 하 게 되 면 **Microsoft 365 인증** 된 또는 **게시자 증명**중 하나가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f2ad-118">**Certification**: If the app has gone through certification, you'll see either **Microsoft 365 certified** or **Publisher attestation**.</span></span> <span data-ttu-id="0f2ad-119">링크를 클릭 하 여 앱에 대 한 인증 세부 정보를 봅니다.</span><span class="sxs-lookup"><span data-stu-id="0f2ad-119">Click the link to view certification details for the app.</span></span> <span data-ttu-id="0f2ad-120">"**--**"가 표시 되 면 앱에 대 한 인증 정보가 없는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0f2ad-120">If you see "**--**", we don't have certification information for the app.</span></span> <span data-ttu-id="0f2ad-121">팀의 인증 된 앱에 대 한 자세한 내용을 보려면 [Microsoft 365 앱 인증 프로그램](https://docs.microsoft.com/teams-app-certification/all-apps)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0f2ad-121">To learn more about certified apps in Teams, read [Microsoft 365 App Certification program](https://docs.microsoft.com/teams-app-certification/all-apps).</span></span>  
- <span data-ttu-id="0f2ad-122">**범주**: 앱에 적용 되는 범주입니다.</span><span class="sxs-lookup"><span data-stu-id="0f2ad-122">**Categories**: Categories that apply to the app.</span></span>
- <span data-ttu-id="0f2ad-123">**앱 상태**: 조직 수준의 앱 상태 이며 다음 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f2ad-123">**App status**: Status of the app at the org level, which can be one of the following:</span></span>
    - <span data-ttu-id="0f2ad-124">**허용 됨**: 조직의 모든 사용자가 앱을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f2ad-124">**Allowed**: The app is available for all users in your organization.</span></span>
    - <span data-ttu-id="0f2ad-125">**차단**됨: 앱이 차단 되어 조직의 모든 사용자가 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0f2ad-125">**Blocked**: The app is blocked and not available for any users in your organization.</span></span><br>
<span data-ttu-id="0f2ad-126">이 열은 이전에 **조직 전체 설정** 창에 있는 앱의 허용 및 차단 상태를 나타내는 것을 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f2ad-126">It's important to know that this column represents the allowed and blocked status of apps that were formerly on the **Org-wide settings** pane.</span></span> <span data-ttu-id="0f2ad-127">이제 **앱 관리** 페이지에서 조직 전체에 앱을 표시 하 고, 차단 하 고, 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f2ad-127">You now view, block, and allow apps at the org-wide on the **Manage apps** page.</span></span> 
- <span data-ttu-id="0f2ad-128">**버전**: 앱 버전.</span><span class="sxs-lookup"><span data-stu-id="0f2ad-128">**Version**: App version.</span></span>

<span data-ttu-id="0f2ad-129">표에 원하는 정보를 표시 하려면 오른쪽 위 모서리에서 **열 편집** 을 클릭 하 여 표에 열을 추가 하거나 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f2ad-129">To see the information that you want in the table, click **Edit Column** in the upper-right corner to add or remove columns to the table.</span></span>

## <a name="upload-a-new-app"></a><span data-ttu-id="0f2ad-130">새 앱 업로드</span><span class="sxs-lookup"><span data-stu-id="0f2ad-130">Upload a new app</span></span>

<span data-ttu-id="0f2ad-131">앱 카탈로그를 사용 하 여 조직에 맞게 특별히 작성 된 lob (기간 업무) 응용 프로그램을 테스트 하 고 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f2ad-131">You can use your app catalog to test and distribute line-of-business applications that are built specifically for your organization.</span></span> <span data-ttu-id="0f2ad-132">팀 앱 패키지는 [팀 앱 Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)를 사용 하 여 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0f2ad-132">A Teams app package is created by using [Teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio).</span></span> <span data-ttu-id="0f2ad-133">앱 패키지를 사용 하는 경우 앱 카탈로그에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f2ad-133">When you have the app package, you can add it to the your app catalog.</span></span> <span data-ttu-id="0f2ad-134">조직의 모든 사용자가 앱 카탈로그를 볼 수 있지만, 전역 관리자 및 팀 서비스 관리자만이를 게시 하 고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f2ad-134">While all users in your organization can view the app catalog, only global admins and Teams service admins can publish and manage it.</span></span>

<span data-ttu-id="0f2ad-135">테 넌 트 앱 카탈로그에 새 사용자 지정 앱을 업로드 하려면 **새 앱 업로드** 를 클릭 하 여 앱 패키지를 .zip 형식으로 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f2ad-135">To upload a new custom app to your tenant app catalog, click **Upload new app** to upload your app package in .zip format.</span></span> <span data-ttu-id="0f2ad-136">앱이 업로드 된 후 강조 표시 되지 않으므로 앱 카탈로그를 검색 하 여 찾을 필요가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f2ad-136">The app isn't highlighted after it's uploaded so you'll need to search your app catalog to find it.</span></span>

<span data-ttu-id="0f2ad-137">앱을 업로드 한 후 업데이트 하려면 **앱 관리** 페이지의 앱 목록에서 앱 이름을 클릭 한 다음 **업데이트**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f2ad-137">To update an app after it's uploaded, in the list of apps on the **Manage apps** page, click the app name, and then click **Update**.</span></span> <span data-ttu-id="0f2ad-138">이렇게 하면 앱 카탈로그의 기존 앱이 바뀌고, 모든 앱 사용 권한 정책 및 앱 설정 정책은 업데이트 된 앱에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f2ad-138">Doing this replaces the existing app in your app catalog and all app permission policies and app setup policies remain enforced for the updated app.</span></span>

<span data-ttu-id="0f2ad-139">자세한 내용은 [팀에서 lob (기간 업무) 앱 관리](manage-your-lob-apps.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0f2ad-139">To learn more, see [Manage your line-of-business apps in Teams](manage-your-lob-apps.md).</span></span>

## <a name="allow-and-block-apps"></a><span data-ttu-id="0f2ad-140">앱 허용 및 차단</span><span class="sxs-lookup"><span data-stu-id="0f2ad-140">Allow and block apps</span></span>

<span data-ttu-id="0f2ad-141">**앱 관리** 페이지는 조직 수준에서 개별 앱을 허용 하거나 차단 하는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="0f2ad-141">The **Manage apps** page is where you allow or block individual apps at the org level.</span></span> <span data-ttu-id="0f2ad-142">여기에는 사용 가능한 모든 앱과 현재 조직 수준의 앱 상태가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f2ad-142">It shows every available app and its current org-level app status.</span></span> <span data-ttu-id="0f2ad-143">(조직 수준에서 앱을 차단 하 고 허용 하는 것이 **조직 전체 앱 설정** 창에서 여기로 이동 했습니다.)</span><span class="sxs-lookup"><span data-stu-id="0f2ad-143">(Blocking and allowing apps at the org level has moved from the **Org-wide app settings** pane to here.)</span></span>

<span data-ttu-id="0f2ad-144">앱을 허용 하거나 차단 하려면이를 선택한 다음 **허용** 또는 **차단을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f2ad-144">To allow or block an app, select it, and then click **Allow** or **Block**.</span></span> <span data-ttu-id="0f2ad-145">앱을 차단 하면 해당 앱과의 모든 조작이 비활성화 되 고 조직의 모든 사용자에 대 한 팀에 앱이 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0f2ad-145">When you block an app, all interactions with that app are disabled and the app doesn't appear in Teams for any users in your organization.</span></span>

<span data-ttu-id="0f2ad-146">앱 **관리** 페이지에서 앱을 차단 하거나 허용 하면 해당 앱이 차단 되거나 조직의 모든 사용자에 게 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f2ad-146">When you block or allow an app on the **Manage apps** page, that app is blocked or allowed for all users in your organization.</span></span>  <span data-ttu-id="0f2ad-147">팀 앱 권한 정책에서 앱을 차단 하거나 허용 하면 해당 정책이 할당 된 사용자가 차단 되거나 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f2ad-147">When you block or allow an app in a Teams app permission policy, it's blocked or allowed for users who are assigned that policy.</span></span> <span data-ttu-id="0f2ad-148">사용자가 앱을 설치 하 고 상호 작용할 수 있으려면 **앱 관리** 페이지의 조직 수준에서 앱을 허용 하 고 사용자에 게 할당 된 앱 권한 정책에서 해당 앱을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f2ad-148">For a user to be able to install and interact with any app, you must allow the app at the org level on the **Manage apps** page and in the app permission policy that's assigned to the user.</span></span>

 > [!NOTE]
 > <span data-ttu-id="0f2ad-149">앱을 제거 하려면 앱을 마우스 오른쪽 단추로 클릭 한 다음 **제거** 를 클릭 하거나 왼쪽 측의 **다른 앱** 메뉴를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f2ad-149">To uninstall an app, right-click on the app and then click **Uninstall** or use the **More apps** menu on the lefthand side.</span></span> 

## <a name="manage-org-wide-app-settings"></a><span data-ttu-id="0f2ad-150">조직 전체 앱 설정 관리</span><span class="sxs-lookup"><span data-stu-id="0f2ad-150">Manage org-wide app settings</span></span>

<span data-ttu-id="0f2ad-151">조직 전체 앱 설정을 사용 하 여 사용자가 타사 앱을 설치할 수 있는지 여부와 사용자가 조직의 사용자 지정 앱을 업로드 하거나 대화형 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f2ad-151">Use org-wide app settings to control whether users can install third-party apps and whether users can upload or interact with custom  apps in your organization.</span></span> <span data-ttu-id="0f2ad-152">조직 전체 앱 설정은 모든 사용자의 동작을 제어 하 고 사용자에 게 할당 된 다른 앱 사용 권한 정책을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f2ad-152">Org-wide app settings govern the behavior for all users and override any other app permission policies assigned to users.</span></span> <span data-ttu-id="0f2ad-153">이를 사용 하 여 악의적 이거나 문제가 있는 앱을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f2ad-153">You can use them to control malicious or problematic apps.</span></span>

1. <span data-ttu-id="0f2ad-154">**앱 관리** 페이지에서 **조직 전체 앱 설정을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f2ad-154">On the **Manage apps** page, select **Org-wide app settings**.</span></span> <span data-ttu-id="0f2ad-155">그런 다음 패널에서 원하는 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f2ad-155">You can then configure the settings you want in the panel.</span></span>

    ![조직 전체 앱 설정 스크린샷](media/manage-apps-org-wide-app-settings.png)
    
2. <span data-ttu-id="0f2ad-157">타사 앱에 대 한 액세스를 제어 하기 위해이 설정을 설정 하거나 **해제 합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f2ad-157">Under **Third-party apps**, turn off or turn on these settings to control access to third-party apps:</span></span>

    - <span data-ttu-id="0f2ad-158">**팀에서 타사 앱 허용**:이는 사용자가 타사 앱을 사용할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f2ad-158">**Allow third-party apps in Teams**: This controls whether users can use third-party apps.</span></span> <span data-ttu-id="0f2ad-159">이 설정을 해제 하는 경우 사용자는 타사 앱을 설치 하거나 사용할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f2ad-159">If you turn off this setting, your users won't be able to install or use any third-party apps.</span></span> <span data-ttu-id="0f2ad-160">허용 되는 앱의 경우 상태는 허용 됨으로 표시 **되지만 조직 전체에서 사용할 수 없도록 설정**됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f2ad-160">For apps that you allowed, the status shows as **Allowed but disabled org-wide**.</span></span>              

        > [!NOTE]
        > <span data-ttu-id="0f2ad-161">팀의 Microsoft 365 정부-GCC 배포에서 **팀에서 타사 앱 허용** 설정이 기본적으로 해제 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f2ad-161">In a Microsoft 365 Government - GCC deployment of Teams, the **Allow third-party apps in Teams** setting is off by default.</span></span>

        <span data-ttu-id="0f2ad-162">**팀에서 타사 앱 허용** 이 해제 되어 있는 경우 [보내는 webhooks](https://docs.microsoft.com/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) 는 사용 하지 않도록 설정 되며,이는 사용자가 만들 수 없음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f2ad-162">When **Allow third-party apps in Teams** is off, [outgoing webhooks](https://docs.microsoft.com/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) are disabled, which means that users can't create them.</span></span> <span data-ttu-id="0f2ad-163">이 설정을 사용 하면 사용자의 앱 권한 정책에서 설정이 설정 되어 있는지 여부에 관계 없이 모든 사용자가 보내는 webhooks를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f2ad-163">When this setting is on, outgoing webhooks are enabled for all users regardless of whether the setting is on or off in the users' app permission policy.</span></span>
    - <span data-ttu-id="0f2ad-164">**기본적으로 저장소에 게시 된 새 타사 앱 허용**: 팀 앱 스토어에 게시 되는 새로운 타사 앱을 팀에서 자동으로 사용할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f2ad-164">**Allow any new third-party apps published to the store by default**: This controls whether new third-party apps that are published to the Teams app store become automatically available in Teams.</span></span> <span data-ttu-id="0f2ad-165">타사 앱을 허용 하는 경우에만이 옵션을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f2ad-165">You can only set this option if you allow third-party apps.</span></span>

3. <span data-ttu-id="0f2ad-166">**사용자 지정 앱**에서 **사용자 지정 앱과의 상호 작용 허용**을 설정 하거나 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f2ad-166">Under **Custom apps**, turn off or turn on **Allow interaction with custom apps**.</span></span> <span data-ttu-id="0f2ad-167">이 설정은 사용자가 사용자 지정 앱을 조작할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f2ad-167">This setting controls whether users can interact with custom apps.</span></span> <span data-ttu-id="0f2ad-168">자세히 알아보려면 [팀에서 사용자 지정 앱 정책 및 설정 관리](teams-custom-app-policies-and-settings.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0f2ad-168">To learn more, see [Manage custom app policies and settings in Teams](teams-custom-app-policies-and-settings.md).</span></span>
4. <span data-ttu-id="0f2ad-169">**저장** 을 클릭 하 여 조직 전체 앱 설정을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f2ad-169">Click **Save** for org-wide app settings to take effect.</span></span>

## <a name="related-topics"></a><span data-ttu-id="0f2ad-170">관련 항목</span><span class="sxs-lookup"><span data-stu-id="0f2ad-170">Related topics</span></span>

- [<span data-ttu-id="0f2ad-171">Team에서 앱의 관리 설정</span><span class="sxs-lookup"><span data-stu-id="0f2ad-171">Admin settings for apps in Teams</span></span>](admin-settings.md)
