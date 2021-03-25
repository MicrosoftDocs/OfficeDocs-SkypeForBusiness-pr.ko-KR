---
title: Teams App Submit API를 사용하여 사용자 지정 앱을 제출하고 승인합니다.
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: joglocke, vaibhava
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams의 Teams 앱 제출 API를 사용하여 제출된 사용자 지정 앱을 승인하는 방법에 대해 자세히 알아보습니다.
ms.openlocfilehash: 8c12d93a0b4420fd248064c69308e8049dc6326f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116976"
---
# <a name="publish-a-custom-app-submitted-through-the-teams-app-submission-api"></a><span data-ttu-id="79020-103">Teams 앱 제출 API를 통해 제출된 사용자 지정 앱 게시</span><span class="sxs-lookup"><span data-stu-id="79020-103">Publish a custom app submitted through the Teams App Submission API</span></span>

## <a name="overview"></a><span data-ttu-id="79020-104">개요</span><span class="sxs-lookup"><span data-stu-id="79020-104">Overview</span></span>

> [!NOTE]
> <span data-ttu-id="79020-105">사용자 지정 Teams 앱을 게시할 때 조직의 앱 스토어의 사용자가 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79020-105">When you publish a custom Teams app, it's available to users in your organization's app store.</span></span> <span data-ttu-id="79020-106">사용자 지정 앱을 게시하는 방법에는 두 가지가 있으며, 사용하는 방식은 앱을 다운로드하는 방법에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79020-106">There are two ways to publish a custom app and the way that you use depends on how you get the app.</span></span> <span data-ttu-id="79020-107">이 문서에서는 개발자가 Teams App Submit API 를 통해 제출하는 사용자 지정 앱을 승인하고 게시하는 방법에 **대해 중점적으로 다를 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="79020-107">**This article focuses on how to approve and publish a custom app that a developer submits through the Teams App Submission API**.</span></span> <span data-ttu-id="79020-108">사용자 지정 앱을 업로드하는 다른 방법은 개발자가 .zip 형식으로 앱 패키지를 보낼 때 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="79020-108">The other method, uploading a custom app, is used when a developer sends you an app package in .zip format.</span></span> <span data-ttu-id="79020-109">해당 방법에 대한 자세한 내용은 앱 패키지를 업로드하여 사용자 지정 <a href="/microsoftteams/upload-custom-apps" target="_blank">앱 게시를 참조하세요.</a></span><span class="sxs-lookup"><span data-stu-id="79020-109">To learn more about that method, see <a href="/microsoftteams/upload-custom-apps" target="_blank">Publish a custom app by uploading an app package</a>.</span></span> <span data-ttu-id="79020-110">승인 앱 위젯은 GCC 테넌트에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="79020-110">The approve app widget isn't available in GCC tenants.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="79020-111">이 메서드는 현재 GCC 환경에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="79020-111">This method is not currently available for GCC environments.</span></span> <span data-ttu-id="79020-112">사용자 지정 앱 업로드 *방법을 사용해야* 합니다.</span><span class="sxs-lookup"><span data-stu-id="79020-112">You must use the *uploading a custom app* method.</span></span>

<span data-ttu-id="79020-113">이 문서에서는 Teams 앱을 개발에서 배포로 검색하는 방법에 대한 종단-종단 지침이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="79020-113">This article provides end-to-end guidance for how to take your Teams app from development to deployment to discovery.</span></span> <span data-ttu-id="79020-114">Teams가 앱 수명 주기 전반에 걸쳐 제공하는 연결된 환경의 개요를 통해 조직의 앱 스토어에서 사용자 지정 앱을 개발, 배포 및 관리하는 방법을 간소화합니다.</span><span class="sxs-lookup"><span data-stu-id="79020-114">You'll get an overview of the connected experiences that Teams provides across the app lifecycle to streamline how to develop, deploy, and manage custom apps in your organization's app store.</span></span>

<span data-ttu-id="79020-115">개발자가 Teams App Submit API를 사용하여 사용자 지정 앱을 제출하여 검토하고 승인할 수 있도록 Microsoft Teams 관리 센터에 직접 제출하는 방법, 조직의 사용자에 대한 앱을 관리하기 위한 정책을 설정하는 방법, 사용자가 Teams에서 앱을 검색하는 방법을 포함하여 수명 주기의 각 단계를 다 덮습니다.</span><span class="sxs-lookup"><span data-stu-id="79020-115">We'll cover each step of the lifecycle, including how developers can use the Teams App Submission API to submit custom apps directly to the Microsoft Teams admin center for you to review and approve, how to set policies to manage apps for users in your organization, and how your users discover them in Teams.</span></span>

![개발에서 배포까지 앱 개요](media/custom-app-lifecycle.png)

<span data-ttu-id="79020-117">이 지침은 앱의 Teams 측면에 중점을 두며 관리자 및 IT 프로를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="79020-117">This guidance focuses on the Teams aspects of the app and is intended for admins and IT pros.</span></span> <span data-ttu-id="79020-118">Teams 앱 개발에 대한 자세한 내용은 Teams 개발자 설명서 <a href="/microsoftteams/platform" target="_blank">를 참조하세요.</a></span><span class="sxs-lookup"><span data-stu-id="79020-118">For information about developing Teams apps, see the <a href="/microsoftteams/platform" target="_blank">Teams developer documentation</a>.</span></span>

## <a name="develop"></a><span data-ttu-id="79020-119">개발</span><span class="sxs-lookup"><span data-stu-id="79020-119">Develop</span></span>

### <a name="create-the-app"></a><span data-ttu-id="79020-120">앱 만들기</span><span class="sxs-lookup"><span data-stu-id="79020-120">Create the app</span></span>

<span data-ttu-id="79020-121">Microsoft Teams 개발자 플랫폼을 사용하면 개발자가 사용자만의 앱 및 서비스를 통합하여 생산성을 향상하고, 의사 결정을 빠르게 내릴 수 있으며, 기존 콘텐츠 및 워크플로에 대한 공동 작업을 쉽게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79020-121">The Microsoft Teams developer platform makes it easy for developers to integrate your own apps and services to improve productivity, make decisions faster, and create collaboration around existing content and workflows.</span></span> <span data-ttu-id="79020-122">Teams 플랫폼에 구축된 앱은 Teams 클라이언트와 서비스 및 워크플로 간의 브리지로, 공동 작업 플랫폼의 컨텍스트로 바로 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="79020-122">Apps built on the Teams platform are bridges between the Teams client and your services and workflows, bringing them directly into the context of your collaboration platform.</span></span> <span data-ttu-id="79020-123">자세한 내용은 Teams 개발자 설명서 <a href="/microsoftteams/platform" target="_blank">를 참조하세요.</a></span><span class="sxs-lookup"><span data-stu-id="79020-123">For more information, go to the <a href="/microsoftteams/platform" target="_blank">Teams developer documentation</a>.</span></span>

### <a name="submit-the-app"></a><span data-ttu-id="79020-124">앱 제출</span><span class="sxs-lookup"><span data-stu-id="79020-124">Submit the app</span></span>

<span data-ttu-id="79020-125">앱이 프로덕션 환경에서 사용할 준비가 된 경우 개발자는 <a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-beta&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank" target="_blank">Graph API,</a>IDE(통합 개발 환경(예: IDE Visual Studio) 또는 Power Apps 및 Power Virtual Agents와 같은 플랫폼에서 호출할 수 있는 Teams App Submit API를 사용하여 앱을 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79020-125">When the app is ready for use in production, the developer can submit the app using the Teams App Submission API, which can be called from <a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-beta&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank" target="_blank">Graph API</a>, an integrated development environment (IDE) such as Visual Studio Code, or a platform such as Power Apps and Power Virtual Agents.</span></span> <span data-ttu-id="79020-126">이렇게 하면 Microsoft Teams <a href="/microsoftteams/manage-apps" target="_blank"></a> 관리 센터의 앱 관리 페이지에서 앱을 사용할 수 있으며, 여기서 관리자인 사용자가 앱을 검토하고 승인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79020-126">Doing this makes the app available on the <a href="/microsoftteams/manage-apps" target="_blank">Manage apps</a> page of the Microsoft Teams admin center, where you, the admin, can review and approve it.this</span></span>

<span data-ttu-id="79020-127">Microsoft Graph에 기반한 <a href="/graph/api/teamsapp-publish?tabs=http&view=graph-rest-beta#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">Teams</a>App 제출 API를 사용하면 조직에서 선택한 플랫폼에서 개발할 수 있으며 Teams의 사용자 지정 앱에 대한 제출-승인 프로세스를 자동화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79020-127">The Teams App Submission API, <a href="/graph/api/teamsapp-publish?tabs=http&view=graph-rest-beta#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">built on Microsoft Graph</a>, allows your organization to develop on the platform of your choice and automates the submission-to-approval process for custom apps on Teams.</span></span>

<span data-ttu-id="79020-128">다음은 코드에서 이 앱 제출 단계의 모양을 Visual Studio 예입니다.</span><span class="sxs-lookup"><span data-stu-id="79020-128">Here's an example of what this app submission step looks like in Visual Studio Code:</span></span>

![코드에서 앱 Visual Studio 제출](media/custom-app-lifecycle-submit-app.png)

<span data-ttu-id="79020-130">아직 조직의 앱 스토어에 앱을 게시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="79020-130">Keep in mind that this doesn't publish the app to your organization's app store yet.</span></span> <span data-ttu-id="79020-131">이 단계에서는 조직의 앱 스토어에 게시하기 위해 승인할 수 있는 Microsoft Teams 관리 센터에 앱을 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="79020-131">This step submits the app to the Microsoft Teams admin center where you can approve it for publishing to your organization's app store.</span></span>

<span data-ttu-id="79020-132">Graph API를 사용하여 앱을 제출하는 데 대한 자세한 내용은 여기를 <a href="/graph/api/teamsapp-publish?tabs=http&view=graph-rest-beta#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">참조하세요.</a></span><span class="sxs-lookup"><span data-stu-id="79020-132">For more information about using the Graph API to submit apps, see <a href="/graph/api/teamsapp-publish?tabs=http&view=graph-rest-beta#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">here</a>.</span></span>

## <a name="validate"></a><span data-ttu-id="79020-133">유효성 검사</span><span class="sxs-lookup"><span data-stu-id="79020-133">Validate</span></span>

<span data-ttu-id="79020-134">Microsoft <a href="/microsoftteams/manage-apps" target="_blank">Teams</a> 관리 센터의 앱 관리 페이지(왼쪽 탐색에서 **Teams Apps** 관리 앱으로 이동) 조직의 모든 Teams 앱에 대한 보기를  >  제공합니다.</span><span class="sxs-lookup"><span data-stu-id="79020-134">The <a href="/microsoftteams/manage-apps" target="_blank">Manage apps</a> page in the Microsoft Teams admin center (in the left navigation, go to **Teams apps** > **Manage apps**), gives you a view into all Teams apps for your organization.</span></span> <span data-ttu-id="79020-135">페이지 **맨** 위에 있는 보류 중인 승인 위젯을 통해 사용자 지정 앱이 승인을 위해 제출된 경우를 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79020-135">The **Pending approval** widget at the top of the page lets you know when a custom app is submitted for approval.</span></span>

<span data-ttu-id="79020-136">표에서 새로 제출된 앱은 자동으로  제출 및 차단  상태의 게시 상태를 **보여 집니다.** </span><span class="sxs-lookup"><span data-stu-id="79020-136">In the table, a newly submitted app automatically shows a **Publishing status** of **Submitted** and **Status** of **Blocked**.</span></span> <span data-ttu-id="79020-137">게시 상태  열을 내선 순서로 정렬하여 앱을 빠르게 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79020-137">You can sort the **Publishing status** column in descending order to quickly find the app.</span></span>

![<span data-ttu-id="79020-138">게시 상태</span><span class="sxs-lookup"><span data-stu-id="79020-138">publishing status</span></span> ](media/custom-app-lifecycle-validate-app.png)

<span data-ttu-id="79020-139">앱 이름을 클릭하여 앱 세부 정보 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="79020-139">Click the app name to go to the app details page.</span></span> <span data-ttu-id="79020-140">정보 **탭에서** 설명, 상태, 제출자 및 앱 ID를 포함하여 앱에 대한 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79020-140">On the **About** tab, you can view details about the app, including description, status, submitter, and app ID.</span></span>

![제출된 앱에 대한 앱 세부 정보 페이지](media/custom-app-lifecycle-app-details.png)

<span data-ttu-id="79020-142">Graph API를 사용하여 게시 상태를 확인한 자세한 내용은 **여기를** <a href="/graph/api/appcatalogs-list-teamsapps?tabs=http&view=graph-rest-beta#example-3-find-application-based-on-the-teams-app-manifest-id" target="_blank">참조하세요.</a></span><span class="sxs-lookup"><span data-stu-id="79020-142">For more information about using the Graph API to check the **Publishing status**, see <a href="/graph/api/appcatalogs-list-teamsapps?tabs=http&view=graph-rest-beta#example-3-find-application-based-on-the-teams-app-manifest-id" target="_blank">here</a>.</span></span>

## <a name="publish"></a><span data-ttu-id="79020-143">게시</span><span class="sxs-lookup"><span data-stu-id="79020-143">Publish</span></span>

<span data-ttu-id="79020-144">사용자가 앱을 사용할 수 있도록 만들 준비가 되면 앱을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="79020-144">When you're ready to make the app available to users, publish the app.</span></span>

1. <span data-ttu-id="79020-145">Microsoft Teams 관리 센터의 왼쪽 탐색 창에서 **Teams 앱** > **앱 관리** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="79020-145">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="79020-146">앱 이름을 클릭하여 앱 세부 정보 페이지로 이동한 다음 게시 상태 **상자에서** 게시를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="79020-146">Click the app name to go to the app details page, and then in the **Publishing status** box, select **Publish**.</span></span>

    <span data-ttu-id="79020-147">앱을 게시한 후  게시 상태가 **게시로** 변경되고  상태가 자동으로 허용 으로 **변경됩니다.**</span><span class="sxs-lookup"><span data-stu-id="79020-147">After you publish the app, the **Publishing status** changes to **Published** and the **Status** automatically changes to **Allowed**.</span></span>

## <a name="set-up-and-manage"></a><span data-ttu-id="79020-148">설정 및 관리</span><span class="sxs-lookup"><span data-stu-id="79020-148">Set up and manage</span></span>

### <a name="control-access-to-the-app"></a><span data-ttu-id="79020-149">앱에 대한 액세스 제어</span><span class="sxs-lookup"><span data-stu-id="79020-149">Control access to the app</span></span>

<span data-ttu-id="79020-150">기본적으로 조직의 모든 사용자는 조직의 앱 스토어에서 앱에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79020-150">By default, all users in your organization can access the app in your organization's app store.</span></span> <span data-ttu-id="79020-151">앱을 사용할 권한이 있는 사용자에 대한 제한 및 제어를 위해 앱 사용 권한 정책을 만들고 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79020-151">To restrict and control who has permission to use the app, you can create and assign an app permission policy.</span></span> <span data-ttu-id="79020-152">자세한 내용은 Teams 에서 <a href="/microsoftteams/teams-app-permission-policies" target="_blank">앱 사용 권한 정책 관리</a>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="79020-152">To learn more, see <a href="/microsoftteams/teams-app-permission-policies" target="_blank">Manage app permission policies in Teams</a>.</span></span>

### <a name="pin-and-install-the-app-for-users-to-discover"></a><span data-ttu-id="79020-153">사용자가 검색할 앱 고정 및 설치</span><span class="sxs-lookup"><span data-stu-id="79020-153">Pin and install the app for users to discover</span></span>

<span data-ttu-id="79020-154">기본적으로 사용자가 조직의 앱 스토어로 이동하여 찾아보거나 검색해야 하는 앱을 찾으면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="79020-154">By default, for users to find the app they have to go to your organization's app store and browse or search for it.</span></span> <span data-ttu-id="79020-155">사용자가 앱에 쉽게 도착할 수 있도록 Teams의 앱 표시줄에 앱을 고정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79020-155">To make it easy for users to get to the app, you can pin the app to the app bar in Teams.</span></span> <span data-ttu-id="79020-156">이렇게하려면 앱 설정 정책을 만들고 사용자에게 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="79020-156">To do this, create an app setup policy and assign it to users.</span></span> <span data-ttu-id="79020-157">자세한 내용은 <a href="/microsoftteams/teams-app-setup-policies" target="_blank">Teams에서 앱 설정 정책 관리</a>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="79020-157">To learn more, see <a href="/microsoftteams/teams-app-setup-policies" target="_blank">Manage app setup policies in Teams</a>.</span></span>

### <a name="search-the-audit-log-for-teams-app-events"></a><span data-ttu-id="79020-158">Teams 앱 이벤트에 대한 감사 로그 검색</span><span class="sxs-lookup"><span data-stu-id="79020-158">Search the audit log for Teams app events</span></span>

<span data-ttu-id="79020-159">감사 로그를 검색하여 조직의 Teams 앱 활동을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79020-159">You can search the audit log to view Teams apps activity in your organization.</span></span> <span data-ttu-id="79020-160">감사 로그를 검색하고 감사 로그에 기록된 Teams 활동 목록을 보는 방법에 대한 자세한 내용은 Teams의 이벤트에 대한 감사 로그 검색을 <a href="/microsoftteams/audit-log-events" target="_blank">참조하세요.</a></span><span class="sxs-lookup"><span data-stu-id="79020-160">To learn more about how to search the audit log and to see a list of Teams activities that are logged in the audit log, see <a href="/microsoftteams/audit-log-events" target="_blank">Search the audit log for events in Teams</a>.</span></span>

<span data-ttu-id="79020-161">감사 로그를 검색하려면 먼저 <a href="https://protection.office.com" target="_blank">보안 및 준수 센터</a>에서 감사를 켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="79020-161">Before you can search the audit log, you have to first turn on auditing in the <a href="https://protection.office.com" target="_blank">Security & Compliance Center</a>.</span></span> <span data-ttu-id="79020-162">자세한 내용은 <a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">감사 로그 검색 설정 및 해제</a>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="79020-162">To learn more, see <a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">Turn audit log search on or off</a>.</span></span> <span data-ttu-id="79020-163">감사 데이터는 감사가 켜진 시점부터만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79020-163">Keep in mind that audit data is only available from the point at which you turned on auditing.</span></span>

## <a name="discover-and-adopt"></a><span data-ttu-id="79020-164">검색 및 채택</span><span class="sxs-lookup"><span data-stu-id="79020-164">Discover and adopt</span></span>

<span data-ttu-id="79020-165">앱에 대한 권한이 있는 사용자는 조직의 앱 스토어에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79020-165">Users who have permissions to the app can find it in your organization's app store.</span></span> <span data-ttu-id="79020-166">앱 **페이지에서** 조직 이름에 대한 기본 제공 페이지로 이동하여 조직의 사용자 지정 앱을 찾으십시오.</span><span class="sxs-lookup"><span data-stu-id="79020-166">Go to **Built for *Your Organization Name*** on the Apps page to find your organization's custom apps.</span></span>

![<span data-ttu-id="79020-167">게시된 앱을 보여주는 앱 페이지</span><span class="sxs-lookup"><span data-stu-id="79020-167">Apps page showing published app</span></span> ](media/custom-app-lifecycle-discovery.png)

<span data-ttu-id="79020-168">앱 설치 정책을 만들어 할당한 경우 앱이 Teams의 앱 표시줄에 고정되어 정책을 할당한 사용자에게 쉽게 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79020-168">If you created and assigned an app setup policy, the app is pinned to the app bar in Teams for easy access for those users who were assigned the policy.</span></span>

## <a name="update"></a><span data-ttu-id="79020-169">업데이트</span><span class="sxs-lookup"><span data-stu-id="79020-169">Update</span></span>

<span data-ttu-id="79020-170">앱을 업데이트하기 위해 개발자는 개발 섹션의 단계를 계속 [따라야](#develop) 합니다.</span><span class="sxs-lookup"><span data-stu-id="79020-170">To update an app, developers should continue to follow the steps in the [Develop](#develop) section.</span></span>

<span data-ttu-id="79020-171">개발자가 게시된 사용자 지정 앱에 대한 업데이트를 제출하면 앱  관리 페이지의 승인 보류 중 위젯에서 <a href="/microsoftteams/manage-apps" target="_blank">알림을 받을 수</a> 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79020-171">When the developer submits an update to a published custom app, you'll get notified in the **Pending approval** widget of the <a href="/microsoftteams/manage-apps" target="_blank">Manage apps</a> page.</span></span> <span data-ttu-id="79020-172">표에서 앱의  게시 상태는 제출된 **업데이트로 설정됩니다.**</span><span class="sxs-lookup"><span data-stu-id="79020-172">In the table, the **Publishing status** of the app will be set to **Update submitted**.</span></span>

![<span data-ttu-id="79020-173">보류 중인 요청 및 앱 상태를 표시하는 앱 페이지 관리</span><span class="sxs-lookup"><span data-stu-id="79020-173">Manage apps page showing pending requests and app status</span></span> ](media/custom-app-lifecycle-update-submitted.png)

<span data-ttu-id="79020-174">앱 업데이트를 검토하고 게시하는 경우:</span><span class="sxs-lookup"><span data-stu-id="79020-174">To review and publish an app update:</span></span>

1. <span data-ttu-id="79020-175">Microsoft Teams 관리 센터의 왼쪽 탐색 창에서 **Teams 앱** > **앱 관리** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="79020-175">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="79020-176">앱 이름을 클릭하여 앱 세부 정보 페이지로 이동한 다음 사용 가능한 업데이트를 선택하여 업데이트 세부 정보를 검토합니다. </span><span class="sxs-lookup"><span data-stu-id="79020-176">Click the app name to go to the app details page, and then select **Update available** to review details of the update.</span></span>

    ![앱 세부 정보 페이지](media/custom-app-lifecycle-update-app.png)
3. <span data-ttu-id="79020-178">준비가되면 게시를 **선택하여** 업데이트를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="79020-178">When you're ready, select **Publish** to publish the update.</span></span> <span data-ttu-id="79020-179">이렇게 하면 기존 앱이 바뀌고 버전 번호를 업데이트하고 게시 상태를 게시 **으로** **변경합니다.**</span><span class="sxs-lookup"><span data-stu-id="79020-179">Doing this replaces the existing app, updates the version number, and changes the **Publishing status** to **Published**.</span></span> <span data-ttu-id="79020-180">모든 앱 사용 권한 정책 및 앱 설정 정책은 업데이트된 앱에 대해 계속 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="79020-180">All app permission policies and app setup policies remain enforced for the updated app.</span></span>

    <span data-ttu-id="79020-181">업데이트를 거부하면 이전 버전의 앱이 게시된 상태로 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79020-181">If you reject the update, the earlier version of the app remains published.</span></span>

<span data-ttu-id="79020-182">다음을 염두에 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="79020-182">Keep in mind the following:</span></span>

- <span data-ttu-id="79020-183">앱이 승인되면 모든 사용자가 앱에 업데이트를 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79020-183">When an app is approved, any one can submit an update to the app.</span></span> <span data-ttu-id="79020-184">즉, 앱을 처음 제출한 개발자를 포함하여 다른 개발자가 앱에 업데이트를 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79020-184">This means other developers, including the developer who originally submitted the app, can submit an update to the app.</span></span>
- <span data-ttu-id="79020-185">개발자가 앱을 제출하고 요청이 보류 중인 경우 동일한 개발자만 앱에 업데이트를 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79020-185">When a developer submits an app and the request is pending, only that same developer can submit an update to the app.</span></span> <span data-ttu-id="79020-186">다른 개발자는 앱이 승인된 후에만 업데이트를 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79020-186">Other developers can submit an update only after the app is approved.</span></span>

<span data-ttu-id="79020-187">Graph API를 사용하여 앱을 업데이트하는 데 대한 자세한 내용은 여기를 <a href="/graph/api/teamsapp-update?view=graph-rest-beta#example-2-update-a-previously-reviewed-and-published-application-to-the-teams-app-catalog" target="_blank">참조하세요.</a></span><span class="sxs-lookup"><span data-stu-id="79020-187">For more information about using the Graph API to update apps, see <a href="/graph/api/teamsapp-update?view=graph-rest-beta#example-2-update-a-previously-reviewed-and-published-application-to-the-teams-app-catalog" target="_blank">here</a>.</span></span>

### <a name="update-experience-for-users"></a><span data-ttu-id="79020-188">사용자에 대한 환경 업데이트</span><span class="sxs-lookup"><span data-stu-id="79020-188">Update experience for users</span></span>

<span data-ttu-id="79020-189">대부분의 경우 앱 업데이트를 게시한 후 사용자에게 새 버전이 자동으로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="79020-189">In most cases, after you publish an app update, the new version automatically appears for users.</span></span> <span data-ttu-id="79020-190">그러나 사용자 동의를 완료해야 하는 <a href="/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft Teams</a> 매니페스트에 대한 몇 가지 업데이트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79020-190">However, there are some updates to the <a href="/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft Teams manifest</a> that require user acceptance to complete:</span></span>

* <span data-ttu-id="79020-191">봇이 추가되거나 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="79020-191">A bot was added or removed</span></span>
* <span data-ttu-id="79020-192">기존 봇의 "botId" 속성이 변경된 경우</span><span class="sxs-lookup"><span data-stu-id="79020-192">An existing bot's "botId" property changed</span></span>
* <span data-ttu-id="79020-193">기존 봇의 "isNotificationOnly" 속성이 변경된 경우</span><span class="sxs-lookup"><span data-stu-id="79020-193">An existing bot's "isNotificationOnly" property changed</span></span>
* <span data-ttu-id="79020-194">봇의 "supportsFiles" 속성이 변경된 경우</span><span class="sxs-lookup"><span data-stu-id="79020-194">The bot's "supportsFiles" property changed</span></span>
* <span data-ttu-id="79020-195">메시징 확장이 추가되거나 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="79020-195">A messaging extension was added or removed</span></span>
* <span data-ttu-id="79020-196">새 커넥터가 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="79020-196">A new connector was added</span></span>
* <span data-ttu-id="79020-197">새 정적 탭이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="79020-197">A new static tab was added</span></span>
* <span data-ttu-id="79020-198">새 구성 가능한 탭이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="79020-198">A new configurable tab was added</span></span>
* <span data-ttu-id="79020-199">"webApplicationInfo" 내부 속성이 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="79020-199">Properties inside "webApplicationInfo" changed</span></span>

![새 버전 사용 가능](media/manage-your-custom-apps-update1.png)

![앱의 업그레이드 옵션](media/manage-your-custom-apps-update2.png)

## <a name="related-topics"></a><span data-ttu-id="79020-202">관련 항목</span><span class="sxs-lookup"><span data-stu-id="79020-202">Related topics</span></span>

- [<span data-ttu-id="79020-203">앱 패키지를 업로드하여 사용자 지정 앱 게시</span><span class="sxs-lookup"><span data-stu-id="79020-203">Publish a custom app by uploading an app package</span></span>](upload-custom-apps.md)
- [<span data-ttu-id="79020-204">Microsoft Teams 관리 센터에서 앱 관리</span><span class="sxs-lookup"><span data-stu-id="79020-204">Manage your apps in the Microsoft Teams admin center</span></span>](manage-apps.md)
- [<span data-ttu-id="79020-205">Teams에서 사용자 지정 앱 정책 및 설정 관리</span><span class="sxs-lookup"><span data-stu-id="79020-205">Manage custom app policies and settings in Teams</span></span>](teams-custom-app-policies-and-settings.md)
- [<span data-ttu-id="79020-206">Teams에서 앱 사용 권한 정책 관리</span><span class="sxs-lookup"><span data-stu-id="79020-206">Manage app permission policies in Teams</span></span>](teams-app-permission-policies.md)
- [<span data-ttu-id="79020-207">Teams에서 앱 설정 정책 관리</span><span class="sxs-lookup"><span data-stu-id="79020-207">Manage app setup policies in Teams</span></span>](teams-app-setup-policies.md)
- <span data-ttu-id="79020-208"><a href="/graph/api/resources/teamsapp?view=graph-rest-beta" target="_blank">Teams용 Microsoft Graph API 앱</a></span><span class="sxs-lookup"><span data-stu-id="79020-208"><a href="/graph/api/resources/teamsapp?view=graph-rest-beta" target="_blank">Microsoft Graph API for Teams apps</a></span></span>