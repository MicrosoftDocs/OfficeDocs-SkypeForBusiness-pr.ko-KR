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
ms.openlocfilehash: ecc03ff6a6baf1333028b949b590f3018d66e393
ms.sourcegitcommit: ab094058e3ffa974527fce8a331dad609ac19609
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/04/2020
ms.locfileid: "46552321"
---
<a name="manage-your-apps-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="f200c-103">Microsoft 팀 관리 센터에서 앱 관리</span><span class="sxs-lookup"><span data-stu-id="f200c-103">Manage your apps in the Microsoft Teams admin center</span></span>
======================================================

<span data-ttu-id="f200c-104">관리자는 Microsoft 팀 관리 센터의 앱 관리 페이지에서 조직의 모든 팀 앱을 보고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f200c-104">As an admin, the Manage apps page in the Microsoft Teams admin center is where you view and manage all Teams apps for your organization.</span></span> <span data-ttu-id="f200c-105">여기에서 앱의 조직 수준 상태 및 속성을 확인 하 고, 조직의 앱 스토어에 새 사용자 지정 앱을 승인 또는 업로드 하 고, 조직 수준의 앱을 차단 하거나 허용 하 고, 조직 전체 앱 설정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f200c-105">Here, you can see the org-level status and properties of apps, approve or upload new custom apps to your organization's app store, block or allow apps at the org level, and manage org-wide app settings.</span></span>

<span data-ttu-id="f200c-106">앱 관리 페이지에서는 사용 가능한 모든 앱에 대 한 보기가 제공 되며, 조직 전체에서 허용 하거나 차단 하는 앱을 결정 하는 데 필요한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f200c-106">The Manage apps page gives you a view into all available apps, providing you with the information you need to decide which apps to allow or block across your organization.</span></span> <span data-ttu-id="f200c-107">그런 다음 [앱 권한 정책](teams-app-permission-policies.md), [앱 설치 정책](teams-app-setup-policies.md), [사용자 지정 앱 정책 및 설정을](teams-custom-app-policies-and-settings.md) 사용 하 여 조직의 특정 사용자에 대 한 앱 환경을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f200c-107">You can then use [app permission policies](teams-app-permission-policies.md), [app setup policies](teams-app-setup-policies.md), and [custom app policies and settings](teams-custom-app-policies-and-settings.md) to configure the app experience for specific users in your organization.</span></span>

<span data-ttu-id="f200c-108">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **팀 앱**으로  >  **앱 관리**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="f200c-108">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span> <span data-ttu-id="f200c-109">페이지에 액세스 하려면 전역 관리자 또는 팀 서비스 관리자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f200c-109">You must be a global admin or Teams service admin to access the page.</span></span>

> [!NOTE]
> <span data-ttu-id="f200c-110">팀의 GCC (Microsoft 365 정부 커뮤니티 클라우드) 배포에서 앱 관리 페이지를 아직 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f200c-110">The Manage apps page isn't available yet in Microsoft 365 Government Community Cloud (GCC) deployments of Teams.</span></span>

## <a name="view-apps"></a><span data-ttu-id="f200c-111">앱 보기</span><span class="sxs-lookup"><span data-stu-id="f200c-111">View apps</span></span>

<span data-ttu-id="f200c-112">각 앱에 대 한 다음 정보를 포함 하 여 모든 앱을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f200c-112">You can view every app including the following information about each app.</span></span>

![관리 되는 앱 페이지의 스크린샷](media/manage-apps.png)

- <span data-ttu-id="f200c-114">**Name**: 앱 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f200c-114">**Name**: The app name.</span></span> <span data-ttu-id="f200c-115">앱에 대 한 자세한 정보를 보려면 앱 이름을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f200c-115">Click the app name to see more information about the app.</span></span> <span data-ttu-id="f200c-116">여기에는 앱에 대 한 설명, 허용 또는 차단 여부, 버전, 앱에 적용 되는 범주, 인증 상태, 지원 되는 기능, 앱 ID가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f200c-116">This includes a description of the app, whether it's allowed or blocked, version, categories that apply to the app, certification status, supported capabilities, and app ID.</span></span> <span data-ttu-id="f200c-117">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f200c-117">Here's an example:</span></span>

  ![앱에 대 한 앱 세부 정보 페이지 스크린샷](media/manage-apps-app-details.png)
  
- <span data-ttu-id="f200c-119">**인증**: 앱이 인증을 통과 하 게 되 면 **Microsoft 365 인증** 된 또는 **게시자 증명**중 하나가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f200c-119">**Certification**: If the app has gone through certification, you'll see either **Microsoft 365 certified** or **Publisher attestation**.</span></span> <span data-ttu-id="f200c-120">링크를 클릭 하 여 앱에 대 한 인증 세부 정보를 봅니다.</span><span class="sxs-lookup"><span data-stu-id="f200c-120">Click the link to view certification details for the app.</span></span> <span data-ttu-id="f200c-121">" **--** "가 표시 되 면 앱에 대 한 인증 정보가 없는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f200c-121">If you see "**--**", we don't have certification information for the app.</span></span> <span data-ttu-id="f200c-122">팀의 인증 된 앱에 대 한 자세한 내용을 보려면 [Microsoft 365 앱 인증 프로그램](https://docs.microsoft.com/teams-app-certification/all-apps)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f200c-122">To learn more about certified apps in Teams, read [Microsoft 365 App Certification program](https://docs.microsoft.com/teams-app-certification/all-apps).</span></span>  

- <span data-ttu-id="f200c-123">**Publisher**: 게시자의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f200c-123">**Publisher**: Name of the publisher.</span></span>
- <span data-ttu-id="f200c-124">**게시 상태**: 사용자 지정 앱의 게시 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="f200c-124">**Publishing status**: Publishing status of custom apps.</span></span>
- <span data-ttu-id="f200c-125">**상태**: 조직 수준의 앱 상태 이며 다음 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f200c-125">**Status**: Status of the app at the org level, which can be one of the following:</span></span>

    - <span data-ttu-id="f200c-126">**허용 됨**: 조직의 모든 사용자가 앱을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f200c-126">**Allowed**: The app is available for all users in your organization.</span></span>
    
    - <span data-ttu-id="f200c-127">**차단**됨: 앱이 차단 되어 조직의 모든 사용자가 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f200c-127">**Blocked**: The app is blocked and not available for any users in your organization.</span></span>
    
    - <span data-ttu-id="f200c-128">**차단 됨**: 조직 전체 앱 설정에서 앱이 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f200c-128">**Blocked org-wide**: The app is blocked in org-wide app settings.</span></span>
    
      <span data-ttu-id="f200c-129">이 열은 이전에 **조직 전체 설정** 창에 있는 앱의 허용 및 차단 상태를 나타내는 것을 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f200c-129">It's important to know that this column represents the allowed and blocked status of apps that were formerly on the **Org-wide settings** pane.</span></span> <span data-ttu-id="f200c-130">이제 앱 관리 페이지에서 조직 전체에 앱을 표시 하 고, 차단 하 고, 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f200c-130">You now view, block, and allow apps at the org-wide on the Manage apps page.</span></span>

- <span data-ttu-id="f200c-131">**사용자 지정 앱**: 앱이 사용자 지정 앱 인지 여부</span><span class="sxs-lookup"><span data-stu-id="f200c-131">**Custom app**: Whether the app is a custom app.</span></span>

- <span data-ttu-id="f200c-132">**범주**: 앱에 적용 되는 범주입니다.</span><span class="sxs-lookup"><span data-stu-id="f200c-132">**Categories**: Categories that apply to the app.</span></span>

- <span data-ttu-id="f200c-133">**버전**: 앱 버전.</span><span class="sxs-lookup"><span data-stu-id="f200c-133">**Version**: App version.</span></span>

<span data-ttu-id="f200c-134">표에 원하는 정보를 표시 하려면 오른쪽 위 모서리에서 **열 편집** 을 클릭 하 여 표에 열을 추가 하거나 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="f200c-134">To see the information that you want in the table, click **Edit Column** in the upper-right corner to add or remove columns to the table.</span></span>

## <a name="publish-a-custom-app-to-your-organizations-app-store"></a><span data-ttu-id="f200c-135">조직의 앱 스토어에 사용자 지정 앱 게시</span><span class="sxs-lookup"><span data-stu-id="f200c-135">Publish a custom app to your organization's app store</span></span>

<span data-ttu-id="f200c-136">앱 관리 페이지를 사용 하 여 조직에 맞게 빌드된 앱을 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f200c-136">Use the Manage apps page to publish apps that are built specifically for your organization.</span></span> <span data-ttu-id="f200c-137">사용자 지정 앱을 게시 한 후 조직의 앱 스토어에 있는 사용자가 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f200c-137">After you publish a custom app, it's available to users in your organization's app store.</span></span> <span data-ttu-id="f200c-138">사용자 지정 앱을 조직의 앱 스토어에 게시 하는 방법에는 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f200c-138">There are two ways to publish a custom app to your organization's app store.</span></span> <span data-ttu-id="f200c-139">사용 하는 방법은 앱을 가져오는 방법에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="f200c-139">The way that you use depends on how you get the app.</span></span>

- <span data-ttu-id="f200c-140">[사용자 지정 앱 승인](#approve-a-custom-app): 개발자가 팀 앱 제출 API를 사용 하 여 앱을 앱 관리 페이지로 직접 제출 하는 경우이 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f200c-140">[Approve a custom app](#approve-a-custom-app): Use this method if the developer submits the app directly to the Manage apps page using the Teams App Submission API.</span></span> <span data-ttu-id="f200c-141">그런 다음 앱 세부 정보 페이지에서 앱을 검토 하 고 직접 게시 하거나 거부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f200c-141">You can then review and publish (or reject) the app directly from the app details page.</span></span>
- <span data-ttu-id="f200c-142">[앱 패키지 업로드](#upload-an-app-package): 개발자가 .zip 형식으로 앱 패키지를 보내는 경우이 방법을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f200c-142">[Upload an app package](#upload-an-app-package): Use this method if the developer sends you the app package in .zip format.</span></span> <span data-ttu-id="f200c-143">앱 패키지를 업로드 하 여 앱을 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="f200c-143">You publish the app by uploading the app package.</span></span>

###  <a name="approve-a-custom-app"></a><span data-ttu-id="f200c-144">사용자 지정 앱 승인</span><span class="sxs-lookup"><span data-stu-id="f200c-144">Approve a custom app</span></span>

<span data-ttu-id="f200c-145">앱 관리 페이지의 **보류 중인 승인** 위젯은 개발자가 팀 앱 제출 API를 사용 하 여 앱을 제출할 때 알림을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="f200c-145">The **Pending approvals** widget on the Manage apps page notifies you when a developer submits an app by using the Teams App Submission API.</span></span> <span data-ttu-id="f200c-146">새로 제출 된 앱이 **제출** 됨의 **게시 상태** 와 **차단 됨** **상태가** 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f200c-146">A newly submitted app is listed with a **Publishing status** of **Submitted** and an **Status** of **Blocked**.</span></span> <span data-ttu-id="f200c-147">앱 세부 정보 페이지로 이동 하 여 앱에 대 한 자세한 정보를 확인 한 다음 게시 하 고 게시 **상태** 를 **게시**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f200c-147">Go to the app details page to see more information about the app, and then to publish it, set **Publishing status** to **Publish**.</span></span>

<span data-ttu-id="f200c-148">개발자가 사용자 지정 앱에 대 한 업데이트를 제출 하는 경우에도 알림을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="f200c-148">You're also notified when a developer submits an update to a custom app.</span></span> <span data-ttu-id="f200c-149">그런 다음 앱 세부 정보 페이지에서 업데이트를 검토 하 고 게시 (또는 거부) 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f200c-149">You can then review and publish (or reject) the update on the app details page.</span></span> <span data-ttu-id="f200c-150">모든 앱 사용 권한 정책 및 앱 설치 정책은 업데이트 된 앱에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f200c-150">All app permission policies and app setup policies remain enforced for the updated app.</span></span>

<span data-ttu-id="f200c-151">자세히 알아보려면 [팀 앱 제출 API를 통해 제출 된 사용자 지정 앱 게시](submit-approve-custom-apps.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f200c-151">To learn more, see [Publish a custom app submitted through the Teams App Submission API](submit-approve-custom-apps.md).</span></span>

### <a name="upload-an-app-package"></a><span data-ttu-id="f200c-152">앱 패키지 업로드</span><span class="sxs-lookup"><span data-stu-id="f200c-152">Upload an app package</span></span>

<span data-ttu-id="f200c-153">개발자는 [팀 앱 Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)를 사용 하 여 팀 앱 패키지를 만든 다음이를 .zip 형식으로 사용자에 게 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="f200c-153">The developer creates a Teams app package using [Teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio), and then sends it to you in .zip format.</span></span> <span data-ttu-id="f200c-154">앱 패키지를 사용 하는 경우 조직의 앱 스토어에 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f200c-154">When you have the app package, you can upload it to your organization's app store.</span></span>

<span data-ttu-id="f200c-155">새 사용자 지정 앱을 업로드 하려면 **업로드** 를 선택 하 여 앱 패키지를 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="f200c-155">To upload a new custom app, select **Upload** to upload the app package.</span></span> <span data-ttu-id="f200c-156">앱이 업로드 된 후 강조 표시 되지 않으므로 앱 관리 페이지에서 앱 목록을 검색 하 여 파일을 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f200c-156">The app isn't highlighted after it's uploaded so you'll need to search the list of apps on the Manage apps page to find it.</span></span>

<span data-ttu-id="f200c-157">앱을 업로드 한 후 업데이트 하려면 앱 관리 페이지의 앱 목록에서 앱 이름을 클릭 한 다음 **업데이트**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f200c-157">To update an app after it's uploaded, in the list of apps on the Manage apps page, click the app name, and then click **Update**.</span></span> <span data-ttu-id="f200c-158">이렇게 하면 기존 앱과 앱 권한 정책 및 앱 설정 정책이 업데이트 된 앱에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f200c-158">Doing this replaces the existing app and all app permission policies and app setup policies remain enforced for the updated app.</span></span>

<span data-ttu-id="f200c-159">자세히 알아보려면 [앱 패키지를 업로드 하 여 사용자 지정 앱 게시](upload-custom-apps.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f200c-159">To learn more, see [Publish a custom app by uploading an app package](upload-custom-apps.md).</span></span>

## <a name="allow-and-block-apps"></a><span data-ttu-id="f200c-160">앱 허용 및 차단</span><span class="sxs-lookup"><span data-stu-id="f200c-160">Allow and block apps</span></span>

<span data-ttu-id="f200c-161">앱 관리 페이지는 조직 수준에서 개별 앱을 허용 하거나 차단 하는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="f200c-161">The Manage apps page is where you allow or block individual apps at the org level.</span></span> <span data-ttu-id="f200c-162">여기에는 사용 가능한 모든 앱과 현재 조직 수준의 앱 상태가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f200c-162">It shows every available app and its current org-level app status.</span></span> <span data-ttu-id="f200c-163">(조직 수준에서 앱을 차단 하 고 허용 하는 것이 **조직 전체 앱 설정** 창에서 여기로 이동 했습니다.)</span><span class="sxs-lookup"><span data-stu-id="f200c-163">(Blocking and allowing apps at the org level has moved from the **Org-wide app settings** pane to here.)</span></span>

<span data-ttu-id="f200c-164">앱을 허용 하거나 차단 하려면이를 선택한 다음 **허용** 또는 **차단을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f200c-164">To allow or block an app, select it, and then click **Allow** or **Block**.</span></span> <span data-ttu-id="f200c-165">앱을 차단 하면 해당 앱과의 모든 조작이 비활성화 되 고 조직의 모든 사용자에 대 한 팀에 앱이 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f200c-165">When you block an app, all interactions with that app are disabled and the app doesn't appear in Teams for any users in your organization.</span></span>

<span data-ttu-id="f200c-166">앱 관리 페이지에서 앱을 차단 하거나 허용 하면 해당 앱이 차단 되거나 조직의 모든 사용자에 게 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f200c-166">When you block or allow an app on the Manage apps page, that app is blocked or allowed for all users in your organization.</span></span>  <span data-ttu-id="f200c-167">팀 앱 권한 정책에서 앱을 차단 하거나 허용 하면 해당 정책이 할당 된 사용자가 차단 되거나 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f200c-167">When you block or allow an app in a Teams app permission policy, it's blocked or allowed for users who are assigned that policy.</span></span> <span data-ttu-id="f200c-168">사용자가 앱을 설치 하 고 상호 작용할 수 있으려면 앱 관리 페이지의 조직 수준에서 앱을 허용 하 고 사용자에 게 할당 된 앱 권한 정책에서 해당 앱을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f200c-168">For a user to be able to install and interact with any app, you must allow the app at the org level on the Manage apps page and in the app permission policy that's assigned to the user.</span></span>

 > [!NOTE]
 > <span data-ttu-id="f200c-169">앱을 제거 하려면 앱을 마우스 오른쪽 단추로 클릭 한 다음 **제거** 를 클릭 하거나 왼쪽에 있는 **다른 앱** 메뉴를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f200c-169">To uninstall an app, right-click the app, and then click **Uninstall** or use the **More apps** menu on the left side.</span></span> 

## <a name="manage-org-wide-app-settings"></a><span data-ttu-id="f200c-170">조직 전체 앱 설정 관리</span><span class="sxs-lookup"><span data-stu-id="f200c-170">Manage org-wide app settings</span></span>

<span data-ttu-id="f200c-171">조직 전체 앱 설정을 사용 하 여 사용자가 타사 앱을 설치할 수 있는지 여부와 사용자가 조직의 사용자 지정 앱을 업로드 하거나 대화형 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f200c-171">Use org-wide app settings to control whether users can install third-party apps and whether users can upload or interact with custom  apps in your organization.</span></span> <span data-ttu-id="f200c-172">조직 전체 앱 설정은 모든 사용자의 동작을 제어 하 고 사용자에 게 할당 된 다른 앱 사용 권한 정책을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="f200c-172">Org-wide app settings govern the behavior for all users and override any other app permission policies assigned to users.</span></span> <span data-ttu-id="f200c-173">이를 사용 하 여 악의적 이거나 문제가 있는 앱을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f200c-173">You can use them to control malicious or problematic apps.</span></span>

> [!NOTE]
> <span data-ttu-id="f200c-174">Microsoft 365 정부의 GCC 팀 배포에서 조직 전체 앱 설정을 사용 하는 방법에 대 한 자세한 내용은 [팀에서 앱 권한 정책 관리](teams-app-permission-policies.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f200c-174">To learn how to use org-wide app settings in Microsoft 365 Government - GCC deployments of Teams, see [Manage app permission policies in Teams](teams-app-permission-policies.md).</span></span>

1. <span data-ttu-id="f200c-175">앱 관리 페이지에서 **조직 전체 앱 설정을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f200c-175">On the Manage apps page, select **Org-wide app settings**.</span></span> <span data-ttu-id="f200c-176">그런 다음 패널에서 원하는 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f200c-176">You can then configure the settings you want in the panel.</span></span>

    ![조직 전체 앱 설정 스크린샷](media/manage-apps-org-wide-app-settings.png)
    
2. <span data-ttu-id="f200c-178">타사 앱에 대 한 액세스를 제어 하기 위해이 설정을 설정 하거나 **해제 합니다.**</span><span class="sxs-lookup"><span data-stu-id="f200c-178">Under **Third-party apps**, turn off or turn on these settings to control access to third-party apps:</span></span>

    - <span data-ttu-id="f200c-179">타사 **앱 허용**:이는 사용자가 타사 앱을 사용할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="f200c-179">**Allow third-party apps**: This controls whether users can use third-party apps.</span></span> <span data-ttu-id="f200c-180">이 설정을 해제 하면 사용자가 타사 앱을 설치 하거나 사용할 수 없게 되며 이러한 앱의 앱 상태는 테이블에서 **조직 전체로 차단** 된 것으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f200c-180">If you turn off this setting, your users won't be able to install or use any third-party apps and the app status of these apps is displayed as **Blocked org-wide** in the table.</span></span>

        > [!NOTE]
        > <span data-ttu-id="f200c-181">타사 **앱 허용** 이 해제 된 경우 [보내는 webhooks](https://docs.microsoft.com/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) 를 사용할 수 없으며,이는 사용자가 만들 수 없음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="f200c-181">When **Allow third-party apps** is off, [outgoing webhooks](https://docs.microsoft.com/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) are disabled, which means that users can't create them.</span></span> <span data-ttu-id="f200c-182">이 설정이 켜져 있으면 보내는 webhooks는 모든 사용자에 대해 사용 하도록 설정 되며, [앱 권한 정책을](teams-app-permission-policies.md)통해 보내는 Webhook 앱을 허용 하거나 차단 하 여 사용자 수준에서 제어 하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f200c-182">When this setting is on, outgoing webhooks are enabled for all users and you can control them at the user level by allowing or blocking the Outgoing Webhook app through [app permission policies](teams-app-permission-policies.md).</span></span> <br><br><span data-ttu-id="f200c-183">**특정 앱 허용 및 다른 모든 항목 차단** 설정을 사용 하는 **Microsoft 앱** 에 대 한 기존 [앱 권한 정책이](teams-app-permission-policies.md) 있고 사용자에 게 보내는 webhooks를 사용 하도록 설정 하려는 경우에는 보내는 Webhook 앱을 목록에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="f200c-183">Note that if you have existing [app permission policies](teams-app-permission-policies.md) for **Microsoft apps** that use the **Allow specific apps and block all others** setting, and you want to enable outgoing webhooks for users, add the Outgoing Webhook app to the list.</span></span>
    - <span data-ttu-id="f200c-184">**기본적으로 저장소에 게시 된 새 타사 앱 허용**: 팀 앱 스토어에 게시 되는 새로운 타사 앱을 팀에서 자동으로 사용할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="f200c-184">**Allow any new third-party apps published to the store by default**: This controls whether new third-party apps that are published to the Teams app store become automatically available in Teams.</span></span> <span data-ttu-id="f200c-185">타사 앱을 허용 하는 경우에만이 옵션을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f200c-185">You can only set this option if you allow third-party apps.</span></span>

3. <span data-ttu-id="f200c-186">**사용자 지정 앱**에서 **사용자 지정 앱과의 상호 작용 허용**을 설정 하거나 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="f200c-186">Under **Custom apps**, turn off or turn on **Allow interaction with custom apps**.</span></span> <span data-ttu-id="f200c-187">이 설정은 사용자가 사용자 지정 앱을 조작할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="f200c-187">This setting controls whether users can interact with custom apps.</span></span> <span data-ttu-id="f200c-188">자세히 알아보려면 [팀에서 사용자 지정 앱 정책 및 설정 관리](teams-custom-app-policies-and-settings.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f200c-188">To learn more, see [Manage custom app policies and settings in Teams](teams-custom-app-policies-and-settings.md).</span></span>
4. <span data-ttu-id="f200c-189">**저장** 을 클릭 하 여 조직 전체 앱 설정을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f200c-189">Click **Save** for org-wide app settings to take effect.</span></span>

## <a name="related-topics"></a><span data-ttu-id="f200c-190">관련 항목</span><span class="sxs-lookup"><span data-stu-id="f200c-190">Related topics</span></span>

- [<span data-ttu-id="f200c-191">Team에서 앱의 관리 설정</span><span class="sxs-lookup"><span data-stu-id="f200c-191">Admin settings for apps in Teams</span></span>](admin-settings.md)
