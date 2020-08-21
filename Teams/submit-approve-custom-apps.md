---
title: Teams 앱 제출 API를 사용하여 사용자 지정 앱 제출 및 승인
author: lanachin
ms.author: v-lanac
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
description: Microsoft Teams에서 Teams 앱 제출 API를 사용하여 제출된 사용자 지정 앱을 승인하는 방법을 알아봅니다.
ms.openlocfilehash: bdd13dbe4db46110250ea380eebd0ea1d011a322
ms.sourcegitcommit: bb5229c9f7999358dcf0ba185ecfd7c881627a38
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46824919"
---
# <a name="publish-a-custom-app-submitted-through-the-teams-app-submission-api"></a><span data-ttu-id="a7837-103">Teams 앱 제출 API를 통해 제출된 사용자 지정 앱 게시</span><span class="sxs-lookup"><span data-stu-id="a7837-103">Publish a custom app submitted through the Teams App Submission API</span></span>

## <a name="overview"></a><span data-ttu-id="a7837-104">개요</span><span class="sxs-lookup"><span data-stu-id="a7837-104">Overview</span></span>

> [!NOTE]
> <span data-ttu-id="a7837-105">사용자 지정 Teams 앱을 퍼블리싱하면 조직의 앱 스토어에 있는 사용자가 이 앱을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7837-105">When you publish a custom Teams app, it's available to users in your organization's app store.</span></span> <span data-ttu-id="a7837-106">사용자 지정 앱을 게시하는 두 가지 방법과 앱을 사용하는 방법은 그 방법에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7837-106">There are two ways to publish a custom app and the way that you use depends on how you get the app.</span></span> <span data-ttu-id="a7837-107">**이 문서는 개발자가 Teams 앱 제출 API를**통해 제출하는 사용자 지정 앱을 승인하고 게시하는 방법에 대해 집중적으로 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a7837-107">**This article focuses on how to approve and publish a custom app that a developer submits through the Teams App Submission API**.</span></span> <span data-ttu-id="a7837-108">또 다른 방법은 개발자가 앱 패키지를 .zip 형식으로 보낼 때 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7837-108">The other method, uploading a custom app, is used when a developer sends you an app package in .zip format.</span></span> <span data-ttu-id="a7837-109">이 방법에 대한 자세한 내용은 앱 <a href="https://docs.microsoft.com/microsoftteams/upload-custom-apps" target="_blank">패키지를 업로드하여 사용자 지정 앱 게시를 참고하세요.</a></span><span class="sxs-lookup"><span data-stu-id="a7837-109">To learn more about that method, see <a href="https://docs.microsoft.com/microsoftteams/upload-custom-apps" target="_blank">Publish a custom app by uploading an app package</a>.</span></span>
 
<span data-ttu-id="a7837-110">이 문서는 Teams 앱을 개발부터 배포까지 배포까지 이동하는 방법에 대한 종단 간 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a7837-110">This article provides end-to-end guidance for how to take your Teams app from development to deployment to discovery.</span></span> <span data-ttu-id="a7837-111">조직의 앱 스토어에서 사용자 지정 앱을 개발, 배포 및 관리하는 방법을 간소화하기 위해 Teams에서 앱 수명 주기 전체에서 제공하는 연결된 환경을 간단히 살짝 다루게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7837-111">You'll get an overview of the connected experiences that Teams provides across the app lifecycle to streamline how to develop, deploy, and manage custom apps in your organization's app store.</span></span>

<span data-ttu-id="a7837-112">개발자가 Teams 앱 제출 API를 사용하여 사용자 지정 앱을 검토하고 승인할 수 있도록 사용자 지정 앱을 Microsoft Teams 관리 센터에 직접 제출하는 방법, 조직의 사용자에 대한 앱을 관리하기 위한 정책을 설정하는 방법, 사용자가 Teams에서 사용자가 검색하는 방법 등을 비롯해 수명 주기의 각 단계에 대해 다루지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a7837-112">We'll cover each step of the lifecycle, including how developers can use the Teams App Submission API to submit custom apps directly to the Microsoft Teams admin center for you to review and approve, how to set policies to manage apps for users in your organization, and how your users discover them in Teams.</span></span>

![개발부터 배포로 앱 개요](media/custom-app-lifecycle.png)

<span data-ttu-id="a7837-114">이 지침은 앱의 Teams 통한 정보에 중점을 두고 관리자와 IT 전문가를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a7837-114">This guidance focuses on the Teams aspects of the app and is intended for admins and IT pros.</span></span> <span data-ttu-id="a7837-115">Teams 앱 개발에 관한 자세한 내용은 <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">Teams 개발자 문서를 참조하세요.</a></span><span class="sxs-lookup"><span data-stu-id="a7837-115">For information about developing Teams apps, see the <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">Teams developer documentation</a>.</span></span>

## <a name="develop"></a><span data-ttu-id="a7837-116">개발</span><span class="sxs-lookup"><span data-stu-id="a7837-116">Develop</span></span>

### <a name="create-the-app"></a><span data-ttu-id="a7837-117">앱 만들기</span><span class="sxs-lookup"><span data-stu-id="a7837-117">Create the app</span></span>

<span data-ttu-id="a7837-118">Microsoft Teams 개발자 플랫폼은 개발자가 손쉽게 생산성을 향상하고 결정을 나누고 기존 콘텐츠 및 워크플로 에디션으로 공동 작업을 바인더로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7837-118">The Microsoft Teams developer platform makes it easy for developers to integrate your own apps and services to improve productivity, make decisions faster, and create collaboration around existing content and workflows.</span></span> <span data-ttu-id="a7837-119">Teams 플랫폼으로 구성된 앱은 Teams 클라이언트와 워크플로 간의 시각적 개체로, 공동 작업 플랫폼의 상황에 직접 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7837-119">Apps built on the Teams platform are bridges between the Teams client and your services and workflows, bringing them directly into the context of your collaboration platform.</span></span> <span data-ttu-id="a7837-120">자세한 내용은 <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">Teams 개발자 설명서를 참조하세요.</a></span><span class="sxs-lookup"><span data-stu-id="a7837-120">For more information, go to the <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">Teams developer documentation</a>.</span></span>

### <a name="submit-the-app"></a><span data-ttu-id="a7837-121">앱 제출</span><span class="sxs-lookup"><span data-stu-id="a7837-121">Submit the app</span></span>

<span data-ttu-id="a7837-122">앱이 프로모션에서 사용할 준비가 되면 개발자는 Teams 앱 제출 API를 사용하여 앱을 제출할 수 있습니다. 이러한 앱은 <a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-1.0&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">Graph API,</a>Visual Studio 코드 등의 통합된 개발 환경(IDE), Power Apps 및 Power Rirtual Agents 같은 플랫폼에서 호출될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7837-122">When the app is ready for use in production, the developer can submit the app using the Teams App Submission API, which can be called from <a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-1.0&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">Graph API</a>, an integrated development environment (IDE) such as Visual Studio Code, or a platform such as Power Apps and Power Virtual Agents.</span></span> <span data-ttu-id="a7837-123">이렇게 하면 관리자가 앱을 검토하고 승인할 수 있습니다. <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">Manage apps</a></span><span class="sxs-lookup"><span data-stu-id="a7837-123">Doing this makes the app available on the <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">Manage apps</a> page of the Microsoft Teams admin center, where you, the admin, can review and approve it.this</span></span> 

<span data-ttu-id="a7837-124"><a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-1.0&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">Microsoft Graph를</a>기으로 하는 Teams 앱 제출 API를 사용하면 조직에서 사용자가 선택한 플랫폼에서 개발하고 Teams에서 사용자 지정 앱에 대한 제출 방법을 자동화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7837-124">The Teams App Submission API, <a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-1.0&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">built on Microsoft Graph</a>, allows your organization to develop on the platform of your choice and automates the submission-to-approval process for custom apps on Teams.</span></span>

<span data-ttu-id="a7837-125">이 앱 제출 단계는 코드에 표시된 모양의 Visual Studio 예입니다.</span><span class="sxs-lookup"><span data-stu-id="a7837-125">Here's an example of what this app submission step looks like in Visual Studio Code:</span></span>

![코드에서 앱을 Visual Studio 스크린샷](media/custom-app-lifecycle-submit-app.png)

<span data-ttu-id="a7837-127">조직의 앱 스토어에 앱이 아주 게시되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a7837-127">Keep in mind that this doesn't publish the app to your organization's app store yet.</span></span> <span data-ttu-id="a7837-128">이 단계에서는 조직의 앱 스토어에 게시하기 위한 승인된 Microsoft Teams 관리 센터에 앱을 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="a7837-128">This step submits the app to the Microsoft Teams admin center where you can approve it for publishing to your organization's app store.</span></span>

<span data-ttu-id="a7837-129">Graph API를 사용하여 앱 제출에 대한 자세한 내용은 여기를 <a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-1.0&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">참조하세요.</a></span><span class="sxs-lookup"><span data-stu-id="a7837-129">For more information about using the Graph API to submit apps, see <a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-1.0&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">here</a>.</span></span>

## <a name="validate"></a><span data-ttu-id="a7837-130">Validate</span><span class="sxs-lookup"><span data-stu-id="a7837-130">Validate</span></span>

<span data-ttu-id="a7837-131">Microsoft Teams <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">관리</a> 센터의 앱 관리 페이지(왼쪽 탐색 창에서 **Teams**앱  >  **관리**앱로 이동)에서 조직의 모든 Teams 앱을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7837-131">The <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">Manage apps</a> page in the Microsoft Teams admin center (in the left navigation, go to **Teams apps** > **Manage apps**), gives you a view into all Teams apps for your organization.</span></span> <span data-ttu-id="a7837-132">페이지 **맨 위에 있는 승인 보류** 중 위젯을 통해 사용자 지정 앱이 승인을 받기 위한 제출되는 시기를 알려줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7837-132">The **Pending approval** widget at the top of the page lets you know when a custom app is submitted for approval.</span></span>

<span data-ttu-id="a7837-133">표에서 새로 제출된 앱에는 제출된 **게시** 및 차단됨 **상태의** 게시 **상태가** **자동으로 표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="a7837-133">In the table, a newly submitted app automatically shows a **Publishing status** of **Submitted** and **Status** of **Blocked**.</span></span> <span data-ttu-id="a7837-134">게시 상태 열을 **내림차순으로** 정렬하여 앱을 빠르게 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7837-134">You can sort the **Publishing status** column in descending order to quickly find the app.</span></span>

![<span data-ttu-id="a7837-135">보류 요청 및 앱 상태가 표시된 앱 관리 페이지 스크린샷</span><span class="sxs-lookup"><span data-stu-id="a7837-135">Screenshot of Manage apps page showing pending requests and app status</span></span> ](media/custom-app-lifecycle-validate-app.png)

<span data-ttu-id="a7837-136">앱 이름을 클릭하여 앱 세부 정보 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="a7837-136">Click the app name to go to the app details page.</span></span> <span data-ttu-id="a7837-137">정보 **탭에서** 설명, 상태, 제출자 및 앱 ID를 포함하여 앱에 대한 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7837-137">On the **About** tab, you can view details about the app, including description, status, submitter, and app ID.</span></span>

![제출된 앱에 대한 앱 세부 정보 페이지 스크린샷](media/custom-app-lifecycle-app-details.png)

<span data-ttu-id="a7837-139">Graph API를 사용하여 게시 상태를 확인하는 방법에 대한 **자세한 내용은 여기를** <a href="https://docs.microsoft.com/graph/api/teamsapp-list?view=graph-rest-1.0&tabs=http#example-3-list-applications-with-a-given-id-and-return-the-submission-review-state" target="_blank">참조하세요.</a></span><span class="sxs-lookup"><span data-stu-id="a7837-139">For more information about using the Graph API to check the **Publishing status**, see <a href="https://docs.microsoft.com/graph/api/teamsapp-list?view=graph-rest-1.0&tabs=http#example-3-list-applications-with-a-given-id-and-return-the-submission-review-state" target="_blank">here</a>.</span></span>

## <a name="publish"></a><span data-ttu-id="a7837-140">게시</span><span class="sxs-lookup"><span data-stu-id="a7837-140">Publish</span></span>

<span data-ttu-id="a7837-141">사용자가 앱을 사용할 수 있도록 준비가 되면 앱을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="a7837-141">When you're ready to make the app available to users, publish the app.</span></span>

1. <span data-ttu-id="a7837-142">Microsoft Teams 관리 센터의 왼쪽 탐색에서 Teams 앱 관리 **앱으로**  >  **이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="a7837-142">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="a7837-143">앱 이름을 클릭하여 앱 세부 정보 페이지로 이동한 다음 게시 상태 **상자에서 게시를** **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="a7837-143">Click the app name to go to the app details page, and then in the **Publishing status** box, select **Publish**.</span></span>

    <span data-ttu-id="a7837-144">앱을 게시하면 게시 상태가 **게시됨으로** **변경되며** **상태가 자동으로 허용됨으로** **변경됩니다.**</span><span class="sxs-lookup"><span data-stu-id="a7837-144">After you publish the app, the **Publishing status** changes to **Published** and the **Status** automatically changes to **Allowed**.</span></span>

## <a name="set-up-and-manage"></a><span data-ttu-id="a7837-145">설정 및 관리</span><span class="sxs-lookup"><span data-stu-id="a7837-145">Set up and manage</span></span>

### <a name="control-access-to-the-app"></a><span data-ttu-id="a7837-146">앱에 대한 액세스 제어</span><span class="sxs-lookup"><span data-stu-id="a7837-146">Control access to the app</span></span>

<span data-ttu-id="a7837-147">기본적으로 조직의 모든 사용자는 조직의 앱 스토어에 있는 앱에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7837-147">By default, all users in your organization can access the app in your organization's app store.</span></span> <span data-ttu-id="a7837-148">앱을 사용할 권한이 있는 사용자를 제한하고 제어하려면 앱 사용 권한 정책을 만들어 할당하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7837-148">To restrict and control who has permission to use the app, you can create and assign an app permission policy.</span></span> <span data-ttu-id="a7837-149">자세히 알아보려면 <a href="https://docs.microsoft.com/microsoftteams/teams-app-permission-policies" target="_blank">Teams에서 앱 사용 권한 정책 관리를 참조하세요.</a></span><span class="sxs-lookup"><span data-stu-id="a7837-149">To learn more, see <a href="https://docs.microsoft.com/microsoftteams/teams-app-permission-policies" target="_blank">Manage app permission policies in Teams</a>.</span></span>

### <a name="pin-and-install-the-app-for-users-to-discover"></a><span data-ttu-id="a7837-150">사용자가 검색할 앱을 고정 및 설치</span><span class="sxs-lookup"><span data-stu-id="a7837-150">Pin and install the app for users to discover</span></span>

<span data-ttu-id="a7837-151">기본적으로 사용자는 조직의 앱 스토어로 이동하여 검색하거나 검색해야 하는 앱을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7837-151">By default, for users to find the app they have to go to your organization's app store and browse or search for it.</span></span> <span data-ttu-id="a7837-152">사용자가 쉽게 앱에 액세스할 수 있도록 앱을 Teams의 앱 바에 고정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7837-152">To make it easy for users to get to the app, you can pin the app to the app bar in Teams.</span></span> <span data-ttu-id="a7837-153">이렇게 하려면 앱 설정 정책을 만들어 사용자에게 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="a7837-153">To do this, create an app setup policy and assign it to users.</span></span> <span data-ttu-id="a7837-154">자세히 알아보려면 <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">Teams에서 앱 설치 정책 관리를 참조하세요.</a></span><span class="sxs-lookup"><span data-stu-id="a7837-154">To learn more, see <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">Manage app setup policies in Teams</a>.</span></span>

### <a name="search-the-audit-log-for-teams-app-events"></a><span data-ttu-id="a7837-155">Teams 앱 이벤트에 대한 감사 로그 검색</span><span class="sxs-lookup"><span data-stu-id="a7837-155">Search the audit log for Teams app events</span></span>

<span data-ttu-id="a7837-156">감사 로그를 검색하여 조직에서 Teams 앱 활동을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7837-156">You can search the audit log to view Teams apps activity in your organization.</span></span> <span data-ttu-id="a7837-157">감사 로그를 검색하고 감사 로그에 기록된 Teams 활동 목록을 보는 방법에 대한 자세한 내용은 Teams에서 이벤트에 대한 감사 <a href="https://docs.microsoft.com/microsoftteams/audit-log-events" target="_blank">로그 검색을 참조하세요.</a></span><span class="sxs-lookup"><span data-stu-id="a7837-157">To learn more about how to search the audit log and to see a list of Teams activities that are logged in the audit log, see <a href="https://docs.microsoft.com/microsoftteams/audit-log-events" target="_blank">Search the audit log for events in Teams</a>.</span></span>

<span data-ttu-id="a7837-158">감사 로그를 검색하려면 먼저 보안 기능 및 준수 <a href="https://protection.office.com" target="_blank">센터에서 감사를 & 켜야 합니다.</a></span><span class="sxs-lookup"><span data-stu-id="a7837-158">Before you can search the audit log, you have to first turn on auditing in the <a href="https://protection.office.com" target="_blank">Security & Compliance Center</a>.</span></span> <span data-ttu-id="a7837-159">자세한 내용은 <a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">감사 로그 검색 켜기 또는 끄기를 참조하세요.</a></span><span class="sxs-lookup"><span data-stu-id="a7837-159">To learn more, see <a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">Turn audit log search on or off</a>.</span></span> <span data-ttu-id="a7837-160">감사 데이터는 감사를 설정한 지점부터만 사용할 수 있다는 점에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="a7837-160">Keep in mind that audit data is only available from the point at which you turned on auditing.</span></span>

## <a name="discover-and-adopt"></a><span data-ttu-id="a7837-161">검색 및 실행</span><span class="sxs-lookup"><span data-stu-id="a7837-161">Discover and adopt</span></span>

<span data-ttu-id="a7837-162">앱에 대한 권한이 있는 사용자는 조직의 앱 스토어에서 해당 앱을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7837-162">Users who have permissions to the app can find it in your organization's app store.</span></span> <span data-ttu-id="a7837-163">앱 \*\*페이지에 대한 기본 *제공로 이동하여* \*\* 조직의 사용자 지정 앱을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="a7837-163">Go to **Built for *Your Organization Name*** on the Apps page to find your organization's custom apps.</span></span>

![<span data-ttu-id="a7837-164">게시된 앱을 보여 주는 앱 페이지 스크린샷</span><span class="sxs-lookup"><span data-stu-id="a7837-164">Screenshot of Apps page showing published app</span></span> ](media/custom-app-lifecycle-discovery.png)

<span data-ttu-id="a7837-165">앱 설정 정책을 만들고 할당한 경우 앱이 Teams의 앱 바에 고정되어 정책이 할당된 사용자가 쉽게 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7837-165">If you created and assigned an app setup policy, the app is pinned to the app bar in Teams for easy access for those users who were assigned the policy.</span></span>

## <a name="update"></a><span data-ttu-id="a7837-166">업데이트</span><span class="sxs-lookup"><span data-stu-id="a7837-166">Update</span></span>

<span data-ttu-id="a7837-167">앱을 업데이트하려면 개발자가 개발 섹션의 단계를 계속 따를 [수](#develop) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7837-167">To update an app, developers should continue to follow the steps in the [Develop](#develop) section.</span></span>

<span data-ttu-id="a7837-168">개발자가 게시된 사용자 지정 앱에 업데이트를 제출하면 앱 관리 페이지의 **승인** 위젯에 <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">알림이 표시됩니다.</a></span><span class="sxs-lookup"><span data-stu-id="a7837-168">When the developer submits an update to a published custom app, you'll get notified in the **Pending approval** widget of the <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">Manage apps</a> page.</span></span> <span data-ttu-id="a7837-169">표에서 **앱의 게시 상태가** 제출됨으로 **설정됩니다.**</span><span class="sxs-lookup"><span data-stu-id="a7837-169">In the table, the **Publishing status** of the app will be set to **Update submitted**.</span></span>

![<span data-ttu-id="a7837-170">보류 요청 및 앱 상태가 표시된 앱 관리 페이지 스크린샷</span><span class="sxs-lookup"><span data-stu-id="a7837-170">Screenshot of Manage apps page showing pending requests and app status</span></span> ](media/custom-app-lifecycle-update-submitted.png)

<span data-ttu-id="a7837-171">앱 업데이트를 검토하고 게시하려면:</span><span class="sxs-lookup"><span data-stu-id="a7837-171">To review and publish an app update:</span></span>

1. <span data-ttu-id="a7837-172">Microsoft Teams 관리 센터의 왼쪽 탐색에서 Teams 앱 관리 **앱으로**  >  **이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="a7837-172">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="a7837-173">앱 이름을 클릭하여 앱 세부 정보 페이지로 이동한 다음 업데이트 **사용 가능을** 선택하여 업데이트 세부 사항을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="a7837-173">Click the app name to go to the app details page, and then select **Update available** to review details of the update.</span></span>

    ![<span data-ttu-id="a7837-174">보류 요청 및 앱 상태가 표시된 앱 관리 페이지 스크린샷</span><span class="sxs-lookup"><span data-stu-id="a7837-174">Screenshot of Manage apps page showing pending requests and app status</span></span> ](media/custom-app-lifecycle-update-app.png)
3. <span data-ttu-id="a7837-175">준비가 되면 게시를 선택하여 **업데이트를** 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="a7837-175">When you're ready, select **Publish** to publish the update.</span></span> <span data-ttu-id="a7837-176">이렇게 하면 기존 앱이 대체되어 버전 번호가 업데이트되며 게시 **상태가 게시됨으로** **변경됩니다.**</span><span class="sxs-lookup"><span data-stu-id="a7837-176">Doing this replaces the existing app, updates the version number, and changes the **Publishing status** to **Published**.</span></span> <span data-ttu-id="a7837-177">업데이트된 앱에 대해 모든 앱 사용 권한 정책 및 앱 설정 정책이 그대로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7837-177">All app permission policies and app setup policies remain enforced for the updated app.</span></span>

    <span data-ttu-id="a7837-178">업데이트를 거절하는 경우 이전 버전의 앱은 게시된 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7837-178">If you reject the update, the earlier version of the app remains published.</span></span>

<span data-ttu-id="a7837-179">다음 사항에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="a7837-179">Keep in mind the following:</span></span>

- <span data-ttu-id="a7837-180">앱이 승인되면 다른 사람은 모든 사용자가 앱에 대한 업데이트를 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7837-180">When an app is approved, any one can submit an update to the app.</span></span> <span data-ttu-id="a7837-181">즉, 원래 앱을 제출한 개발자를 포함한 다른 개발자가 앱에 대한 업데이트를 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7837-181">This means other developers, including the developer who originally submitted the app, can submit an update to the app.</span></span>
- <span data-ttu-id="a7837-182">개발자가 앱을 제출하고 요청이 보류 중이면 동일한 개발자만 앱에 대한 업데이트를 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7837-182">When a developer submits an app and the request is pending, only that same developer can submit an update to the app.</span></span> <span data-ttu-id="a7837-183">다른 개발자는 앱이 승인된 후에만 업데이트를 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7837-183">Other developers can submit an update only after the app is approved.</span></span>

<span data-ttu-id="a7837-184">Graph API를 사용하여 앱을 업데이트하는 방법에 대한 자세한 내용은 여기를 <a href="https://docs.microsoft.com/graph/api/teamsapp-update?view=graph-rest-1.0#example-2-update-a-previously-reviewed-and-published-application-to-the-teams-app-catalog" target="_blank">참조하세요.</a></span><span class="sxs-lookup"><span data-stu-id="a7837-184">For more information about using the Graph API to update apps, see <a href="https://docs.microsoft.com/graph/api/teamsapp-update?view=graph-rest-1.0#example-2-update-a-previously-reviewed-and-published-application-to-the-teams-app-catalog" target="_blank">here</a>.</span></span>

### <a name="update-experience-for-users"></a><span data-ttu-id="a7837-185">사용자를 위한 업데이트 환경</span><span class="sxs-lookup"><span data-stu-id="a7837-185">Update experience for users</span></span>

<span data-ttu-id="a7837-186">대부분의 경우 앱 업데이트를 퍼블리싱하고 나면 사용자에게 새 버전이 자동으로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="a7837-186">In most cases, after you publish an app update, the new version automatically appears for users.</span></span> <span data-ttu-id="a7837-187">그러나 사용자가 수락을 완료해야 <a href="https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">하는 Microsoft Teams</a> 매니페스트에 몇 가지 업데이트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7837-187">However, there are some updates to the <a href="https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft Teams manifest</a> that require user acceptance to complete:</span></span>

* <span data-ttu-id="a7837-188">부품이 추가 또는 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a7837-188">A bot was added or removed</span></span>
* <span data-ttu-id="a7837-189">기존 의 "botId" 속성이 변경된 경우</span><span class="sxs-lookup"><span data-stu-id="a7837-189">An existing bot's "botId" property changed</span></span>
* <span data-ttu-id="a7837-190">기존 의 "isNotificationOnly" 속성이 변경된 경우</span><span class="sxs-lookup"><span data-stu-id="a7837-190">An existing bot's "isNotificationOnly" property changed</span></span>
* <span data-ttu-id="a7837-191">부트의 "supportsFiles" 속성이 변경됨</span><span class="sxs-lookup"><span data-stu-id="a7837-191">The bot's "supportsFiles" property changed</span></span>
* <span data-ttu-id="a7837-192">메시지 확장 기능이 추가 또는 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a7837-192">A messaging extension was added or removed</span></span>
* <span data-ttu-id="a7837-193">새 커넥터가 추가됨</span><span class="sxs-lookup"><span data-stu-id="a7837-193">A new connector was added</span></span>
* <span data-ttu-id="a7837-194">새 정적 탭이 추가됨</span><span class="sxs-lookup"><span data-stu-id="a7837-194">A new static tab was added</span></span>
* <span data-ttu-id="a7837-195">새 구성 할 수 있는 탭이 추가됨</span><span class="sxs-lookup"><span data-stu-id="a7837-195">A new configurable tab was added</span></span>
* <span data-ttu-id="a7837-196">"webApplicationInfo" 내의 속성이 변경됨</span><span class="sxs-lookup"><span data-stu-id="a7837-196">Properties inside "webApplicationInfo" changed</span></span>

![사용할 수 있는 새 버전이 있는 앱을 보여 주는 스크린샷](media/manage-your-custom-apps-update1.png)

![앱 업그레이드 옵션 스크린샷](media/manage-your-custom-apps-update2.png)

## <a name="related-topics"></a><span data-ttu-id="a7837-199">관련 항목</span><span class="sxs-lookup"><span data-stu-id="a7837-199">Related topics</span></span>

- [<span data-ttu-id="a7837-200">앱 패키지를 업로드하여 사용자 지정 앱 게시</span><span class="sxs-lookup"><span data-stu-id="a7837-200">Publish a custom app by uploading an app package</span></span>](upload-custom-apps.md)
- [<span data-ttu-id="a7837-201">Microsoft Teams 관리 센터에서 앱 관리</span><span class="sxs-lookup"><span data-stu-id="a7837-201">Manage your apps in the Microsoft Teams admin center</span></span>](manage-apps.md)
- [<span data-ttu-id="a7837-202">Teams에서 사용자 지정 앱 정책 및 설정 관리</span><span class="sxs-lookup"><span data-stu-id="a7837-202">Manage custom app policies and settings in Teams</span></span>](teams-custom-app-policies-and-settings.md)
- [<span data-ttu-id="a7837-203">Teams에서 앱 사용 권한 정책 관리</span><span class="sxs-lookup"><span data-stu-id="a7837-203">Manage app permission policies in Teams</span></span>](teams-app-permission-policies.md)
- [<span data-ttu-id="a7837-204">Teams에서 앱 설정 정책 관리</span><span class="sxs-lookup"><span data-stu-id="a7837-204">Manage app setup policies in Teams</span></span>](teams-app-setup-policies.md)
- <span data-ttu-id="a7837-205"><a href="https://docs.microsoft.com/graph/api/resources/teamsapp?view=graph-rest-1.0" target="_blank">Teams 앱용 Microsoft Graph API</a></span><span class="sxs-lookup"><span data-stu-id="a7837-205"><a href="https://docs.microsoft.com/graph/api/resources/teamsapp?view=graph-rest-1.0" target="_blank">Microsoft Graph API for Teams apps</a></span></span>
