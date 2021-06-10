---
title: 업로드 관리 센터에서 사용자 Microsoft Teams 앱 관리
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
description: 사용자 지정 앱을 관리 센터의 조직의 앱 스토어에 업로드하는 Microsoft Teams 대해 자세히 알아보습니다.
ms.openlocfilehash: 9473c8e2fc4284c4ca205666152ef183b0210841
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51115526"
---
# <a name="publish-a-custom-app-by-uploading-an-app-package"></a><span data-ttu-id="89215-103">앱 패키지를 업로드하여 사용자 지정 앱 게시</span><span class="sxs-lookup"><span data-stu-id="89215-103">Publish a custom app by uploading an app package</span></span>

> [!NOTE]
> <span data-ttu-id="89215-104">사용자 지정 Teams 게시할 때 조직의 앱 스토어의 사용자가 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89215-104">When you publish a custom Teams app, it's available to users in your organization's app store.</span></span> <span data-ttu-id="89215-105">사용자 지정 앱을 게시하는 방법에는 두 가지가 있으며, 사용하는 방식은 앱을 다운로드하는 방법에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89215-105">There are two ways to publish a custom app and the way that you use depends on how you get the app.</span></span> <span data-ttu-id="89215-106">이 문서에서는 개발자가 를 보내는 앱 패키지(.zip 형식)를 업로드하여 사용자 지정 앱을 게시하는 **방법에 대해 중점적으로 다를 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="89215-106">**This article focuses on how to publish a custom app by uploading an app package (in .zip format) that a developer sends you**.</span></span> <span data-ttu-id="89215-107">사용자 지정 앱을 사용하는 다른 방법은 개발자가 앱 제출 API를 통해 <a href="/microsoftteams/manage-apps" target="_blank"></a> 앱 관리 페이지에 직접 앱을 제출할 Teams 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="89215-107">The other method, approving a custom app, is used when a developer submits an app directly to the <a href="/microsoftteams/manage-apps" target="_blank">Manage apps</a> page through the Teams App Submission API.</span></span> <span data-ttu-id="89215-108">해당 방법에 대한 자세한 내용은 앱 제출 API 를 통해 제출된 사용자 지정 앱 <a href="/microsoftteams/submit-approve-custom-apps" target="_blank">게시를 Teams 참조하세요.</a></span><span class="sxs-lookup"><span data-stu-id="89215-108">To learn more about that method, see <a href="/microsoftteams/submit-approve-custom-apps" target="_blank">Publish a custom app submitted through the Teams App Submission API</a>.</span></span>

<span data-ttu-id="89215-109">이 문서에서는 개발에서 배포로 배포에 Teams 앱으로 데려오는 방법에 대한 종단 Teams 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="89215-109">This article provides end-to-end guidance for how to take your Teams app from development to deployment to discovery.</span></span> <span data-ttu-id="89215-110">이 지침은 앱의 Teams 측면에 중점을 두며 관리자 및 IT 프로를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="89215-110">This guidance focuses on the Teams aspects of the app and is intended for admins and IT pros.</span></span> <span data-ttu-id="89215-111">앱 개발에 대한 Teams 자세한 내용은 개발자 Teams <a href="/microsoftteams/platform" target="_blank">참조하세요.</a></span><span class="sxs-lookup"><span data-stu-id="89215-111">For more information about developing Teams apps, see the <a href="/microsoftteams/platform" target="_blank">Teams developer documentation</a>.</span></span>

![개발에서 배포까지 앱 개요](media/upload-custom-apps.png)

## <a name="develop"></a><span data-ttu-id="89215-113">개발</span><span class="sxs-lookup"><span data-stu-id="89215-113">Develop</span></span>

### <a name="create-your-app"></a><span data-ttu-id="89215-114">앱 만들기</span><span class="sxs-lookup"><span data-stu-id="89215-114">Create your app</span></span>

<span data-ttu-id="89215-115">개발자 Microsoft Teams 플랫폼을 사용하면 개발자가 사용자 자신의 앱 및 서비스를 통합하여 생산성을 향상하고, 더 빠르게 의사 결정을 내릴 수 있으며, 기존 콘텐츠 및 워크플로에 대한 공동 작업을 쉽게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89215-115">The Microsoft Teams developer platform makes it easy for developers to integrate your own apps and services to improve productivity, make decisions faster, and create collaboration around existing content and workflows.</span></span> <span data-ttu-id="89215-116">Teams 플랫폼에 구축된 앱은 Teams 클라이언트와 서비스 및 워크플로 간의 브리지로, 공동 작업 플랫폼의 컨텍스트로 바로 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="89215-116">Apps built on the Teams platform are bridges between the Teams client and your services and workflows, bringing them directly into the context of your collaboration platform.</span></span> <span data-ttu-id="89215-117">자세한 내용은 개발자 Teams <a href="/microsoftteams/platform" target="_blank">로 이동하세요.</a></span><span class="sxs-lookup"><span data-stu-id="89215-117">For more information, go to the <a href="/microsoftteams/platform" target="_blank">Teams developer documentation</a>.</span></span>

## <a name="validate"></a><span data-ttu-id="89215-118">유효성 검사</span><span class="sxs-lookup"><span data-stu-id="89215-118">Validate</span></span>

### <a name="get-the-app-package"></a><span data-ttu-id="89215-119">앱 패키지 다운로드</span><span class="sxs-lookup"><span data-stu-id="89215-119">Get the app package</span></span>

<span data-ttu-id="89215-120">앱이 프로덕션에서 사용할 준비가 된 경우 개발자는 앱 패키지를 생성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89215-120">When the app is ready for use in production, the developer should produce an app package.</span></span> <span data-ttu-id="89215-121">이 경우 <a href="/microsoftteams/platform/get-started/get-started-app-studio" target="_blank">App Studio를 사용할</a> 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89215-121">They can use <a href="/microsoftteams/platform/get-started/get-started-app-studio" target="_blank">App Studio</a> for that.</span></span> <span data-ttu-id="89215-122">파일 형식에 따라 .zip 합니다.</span><span class="sxs-lookup"><span data-stu-id="89215-122">They'll send you the file in .zip format.</span></span>

<span data-ttu-id="89215-123">Microsoft는 이러한 <a href="/microsoftteams/platform/publishing/office-store-approval" target="_blank">지침을</a> 사용하여 앱이 글로벌 앱 스토어의 품질 및 보안 Teams 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="89215-123">Microsoft uses <a href="/microsoftteams/platform/publishing/office-store-approval" target="_blank">these guidelines</a> to ensure apps comply with the quality and security standards of the global Teams apps store.</span></span>

### <a name="allow-trusted-users-to-upload-custom-apps"></a><span data-ttu-id="89215-124">신뢰할 수 있는 사용자가 사용자 지정 앱을 업로드하도록 허용</span><span class="sxs-lookup"><span data-stu-id="89215-124">Allow trusted users to upload custom apps</span></span>

<span data-ttu-id="89215-125">앱이 프로덕션 테넌트에서 올바르게 작동하고 있는지 확인하려면 자신 및/또는 신뢰할 수 있는 사용자가 프로덕션 테넌트에서 사용자 지정 앱을 업로드하도록 허용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89215-125">To validate that the app is working correctly in your production tenant, you need to allow yourself and/or trusted users to upload custom apps in the production tenant.</span></span> <span data-ttu-id="89215-126">앱 설정 <a href="/microsoftteams/teams-app-setup-policies" target="_blank">정책을 사용하여</a> 이 작업을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="89215-126">You use <a href="/microsoftteams/teams-app-setup-policies" target="_blank">app setup policies</a> to do this.</span></span>

> [!NOTE]
> <span data-ttu-id="89215-127">직접 또는 신뢰할 수 있는 사용자에 대해 프로덕션 테넌트에 앱을 업로드하는 것이 불편한 경우 이 단계를 건너뛰고 업로드 [](#set-up-and-manage) 섹션을 설정하고 관리하여 평가되지 않은 앱을 조직의 앱 스토어에 게시할 수 있습니다. [](#upload)</span><span class="sxs-lookup"><span data-stu-id="89215-127">If you're uncomfortable with uploading the app to your production tenant for validation, even for yourself or trusted users, you can skip this step and follow the steps in the [Upload](#upload) and [Set up and manage](#set-up-and-manage) sections to publish the unvalidated app to your organization's app store.</span></span> <span data-ttu-id="89215-128">그런 다음, 자신과 신뢰하는 사용자만 해당 앱에 대한 액세스를 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="89215-128">Then, restrict access to that app to only yourself and users you trust.</span></span> <span data-ttu-id="89215-129">그런 다음 이러한 사용자는 조직의 앱 스토어에서 앱을 다운로드하여 유효성 검사를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89215-129">These users can then get the app from your organization's app store to perform validation.</span></span> <span data-ttu-id="89215-130">앱이 유효성을 검사한 후 동일한 권한 정책을 사용하여 액세스를 열고 프로덕션 사용을 위해 앱을 롤아웃합니다.</span><span class="sxs-lookup"><span data-stu-id="89215-130">After the app is validated, use the same permission policies to open access and roll the app out for production use.</span></span>

<span data-ttu-id="89215-131">신뢰할 수 있는 사용자가 사용자 지정 앱을 업로드할 수 있도록 허용하려면 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="89215-131">To allow trusted users to upload custom apps, follow these steps:</span></span>

1. <span data-ttu-id="89215-132">사용자 지정 앱 또는 전체 **앱** 설정과의 상호 작용 허용을 켜습니다.</span><span class="sxs-lookup"><span data-stu-id="89215-132">Turn on the **Allow interaction with custom apps** org-wide app setting.</span></span> <span data-ttu-id="89215-133">이 작업을 위해:</span><span class="sxs-lookup"><span data-stu-id="89215-133">To do this:</span></span>
    1. <span data-ttu-id="89215-134">관리 센터의 왼쪽 탐색 Microsoft Teams 앱 관리 Teams 앱 관리로 이동한 다음,  >   **Org-wide 앱** 설정을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="89215-134">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**, and then click **Org-wide app settings**.</span></span>
    2. <span data-ttu-id="89215-135">사용자 **지정 앱에서** 사용자 지정 **앱과의 상호 작용 허용을 켜고** 저장을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="89215-135">Under **Custom apps**, turn on **Allow interaction with custom apps**, and then click **Save**.</span></span>
2. <span data-ttu-id="89215-136">전역 앱 **업로드 설정에서** 사용자 지정 앱 설정을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="89215-136">Turn off the **Upload custom apps** setting in the global app setup policy.</span></span> <span data-ttu-id="89215-137">이 작업을 위해:</span><span class="sxs-lookup"><span data-stu-id="89215-137">To do this:</span></span>
    1. <span data-ttu-id="89215-138">관리 센터의 왼쪽 탐색에서 Microsoft Teams 앱 Teams 설정 정책으로 이동한 다음  >   **전역(org-wide default)** 정책을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="89215-138">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**, and then click the **Global (Org-wide default)** policy.</span></span>
    2. <span data-ttu-id="89215-139">사용자 **업로드 앱을 끄고** 저장을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="89215-139">Turn off **Upload custom apps**, and then click **Save**.</span></span>
3. <span data-ttu-id="89215-140">사용자 지정 앱을 업로드하고 신뢰할 수 있는 사용자 집합에 할당할 수 있는 새 앱 설정 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89215-140">Create a new app setup policy that allows uploading custom apps and assign it to your set of trusted users.</span></span> <span data-ttu-id="89215-141">이 작업을 위해:</span><span class="sxs-lookup"><span data-stu-id="89215-141">To do this:</span></span>
    1. <span data-ttu-id="89215-142">관리 센터의 왼쪽 탐색에서 Microsoft Teams 앱 설치 정책으로 Teams 이동한 다음 추가를  >   **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="89215-142">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**, and then click the **Add**.</span></span> <span data-ttu-id="89215-143">새 정책에 이름과 설명을 지정하고 사용자 **업로드** 설정한 다음 저장을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="89215-143">Give the new policy a name and description, turn on **Upload custom apps**, and then click **Save**.</span></span>
    2. <span data-ttu-id="89215-144">만든 새 정책을 선택한 다음 사용자 **관리를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="89215-144">Select the new policy you created, and then click **Manage users**.</span></span> <span data-ttu-id="89215-145">사용자를 검색하고 **추가를** 클릭한 다음 적용을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="89215-145">Search for a user, click **Add**, and then click **Apply**.</span></span> <span data-ttu-id="89215-146">이 단계를 반복하여 신뢰할 수 있는 모든 사용자에게 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="89215-146">Repeat this step to assign the policy to all your trusted users.</span></span>

        !["앱 설정 정책 추가" 페이지의 스크린샷](media/manage-your-lob-apps-new-app-setup-policy.png)

    <span data-ttu-id="89215-148">이제 이러한 사용자는 앱 매니페스트를 업로드하여 앱이 프로덕션 테넌트에서 올바르게 작동하고 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89215-148">These users can now upload the app manifest to validate that the app is working correctly in the production tenant.</span></span>

## <a name="upload"></a><span data-ttu-id="89215-149">업로드</span><span class="sxs-lookup"><span data-stu-id="89215-149">Upload</span></span>

<span data-ttu-id="89215-150">조직의 앱 스토어의 사용자가 앱을 사용할 수 있도록하려면 앱을 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="89215-150">To make the app available to users in your organization's app store, upload the app.</span></span> <span data-ttu-id="89215-151">관리 센터의 앱 <a href="/microsoftteams/manage-apps" target="_blank"></a> 관리 페이지에서 Microsoft Teams 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89215-151">You can do this on the <a href="/microsoftteams/manage-apps" target="_blank">Manage apps</a> page of the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="89215-152">Microsoft Teams 관리 센터의 왼쪽 탐색 창에서 **Teams 앱** > **앱 관리** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="89215-152">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="89215-153">업로드 클릭하고 파일 선택을 **클릭한** 다음 개발자로부터 받은 앱 패키지를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="89215-153">Click **Upload**, click **Select a file**, and then select the app package that you received from the developer.</span></span>

   ![관리 센터에서 앱 업로드 스크린샷](media/manage-your-lob-apps-upload-new-app.png) 

## <a name="set-up-and-manage"></a><span data-ttu-id="89215-155">설정 및 관리</span><span class="sxs-lookup"><span data-stu-id="89215-155">Set up and manage</span></span>

### <a name="control-access-to-the-app"></a><span data-ttu-id="89215-156">앱에 대한 액세스 제어</span><span class="sxs-lookup"><span data-stu-id="89215-156">Control access to the app</span></span>

<span data-ttu-id="89215-157">기본적으로 조직의 모든 사용자는 조직의 앱 스토어에서 앱에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89215-157">By default, all users in your organization can access the app in your organization's app store.</span></span> <span data-ttu-id="89215-158">앱을 사용할 권한이 있는 사용자에 대한 제한 및 제어를 위해 앱 사용 권한 정책을 만들고 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89215-158">To restrict and control who has permission to use the app, you can create and assign an app permission policy.</span></span> <span data-ttu-id="89215-159">자세한 내용은 <a href="/microsoftteams/teams-app-permission-policies" target="_blank">Teams에서 앱 권한 정책 관리</a>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="89215-159">To learn more, see <a href="/microsoftteams/teams-app-permission-policies" target="_blank">Manage app permission policies in Teams</a>.</span></span>

### <a name="pin-and-install-the-app-for-users-to-discover"></a><span data-ttu-id="89215-160">사용자가 검색할 앱 고정 및 설치</span><span class="sxs-lookup"><span data-stu-id="89215-160">Pin and install the app for users to discover</span></span>

<span data-ttu-id="89215-161">기본적으로 사용자가 조직의 앱 스토어로 이동하여 찾아보거나 검색해야 하는 앱을 찾으면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89215-161">By default, for users to find the app they have to go to your organization's app store and browse or search for it.</span></span> <span data-ttu-id="89215-162">사용자가 앱에 쉽게 도착할 수 있도록 앱 표시줄에 앱을 고정할 수 Teams.</span><span class="sxs-lookup"><span data-stu-id="89215-162">To make it easy for users to get to the app, you can pin the app to the app bar in Teams.</span></span> <span data-ttu-id="89215-163">이렇게하려면 앱 설정 정책을 만들고 사용자에게 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="89215-163">To do this, create an app setup policy and assign it to users.</span></span> <span data-ttu-id="89215-164">자세한 내용은 <a href="/microsoftteams/teams-app-setup-policies" target="_blank">Teams에서 앱 설정 정책 관리</a>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="89215-164">To learn more, see <a href="/microsoftteams/teams-app-setup-policies" target="_blank">Manage app setup policies in Teams</a>.</span></span>

### <a name="search-the-audit-log-for-teams-app-events"></a><span data-ttu-id="89215-165">앱 이벤트에 대한 감사 Teams 검색</span><span class="sxs-lookup"><span data-stu-id="89215-165">Search the audit log for Teams app events</span></span>

<span data-ttu-id="89215-166">감사 로그를 검색하여 조직의 앱 Teams 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89215-166">You can search the audit log to view Teams apps activity in your organization.</span></span> <span data-ttu-id="89215-167">감사 로그를 검색하고 감사 로그에 Teams 활동 목록을 보는 방법에 대한 자세한 내용은 감사 로그에서 이벤트에 대한 감사 <a href="/microsoftteams/audit-log-events" target="_blank">로그 검색을 Teams.</a></span><span class="sxs-lookup"><span data-stu-id="89215-167">To learn more about how to search the audit log and to see a list of Teams activities that are logged in the audit log, see <a href="/microsoftteams/audit-log-events" target="_blank">Search the audit log for events in Teams</a>.</span></span>

<span data-ttu-id="89215-168">감사 로그를 검색하려면 먼저 <a href="https://protection.office.com" target="_blank">보안 및 준수 센터</a>에서 감사를 켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89215-168">Before you can search the audit log, you have to first turn on auditing in the <a href="https://protection.office.com" target="_blank">Security & Compliance Center</a>.</span></span> <span data-ttu-id="89215-169">자세한 내용은 <a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">감사 로그 검색 설정 및 해제</a>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="89215-169">To learn more, see <a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">Turn audit log search on or off</a>.</span></span> <span data-ttu-id="89215-170">감사 데이터는 감사가 켜진 시점부터만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89215-170">Keep in mind that audit data is only available from the point at which you turned on auditing.</span></span>

## <a name="discover-and-adopt"></a><span data-ttu-id="89215-171">검색 및 채택</span><span class="sxs-lookup"><span data-stu-id="89215-171">Discover and adopt</span></span>

<span data-ttu-id="89215-172">앱에 대한 권한이 있는 사용자는 조직의 앱 스토어에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89215-172">Users who have permissions to the app can find it in your organization's app store.</span></span> <span data-ttu-id="89215-173">앱 **페이지에서** 조직 이름에 대한 기본 제공 페이지로 이동하여 조직의 사용자 지정 앱을 찾으십시오.</span><span class="sxs-lookup"><span data-stu-id="89215-173">Go to **Built for *Your Organization Name*** on the Apps page to find your organization's custom apps.</span></span>

![<span data-ttu-id="89215-174">게시된 앱을 보여주는 앱 페이지의 스크린샷</span><span class="sxs-lookup"><span data-stu-id="89215-174">Screenshot of Apps page showing published app</span></span> ](media/custom-app-lifecycle-discovery.png)

<span data-ttu-id="89215-175">앱 설치 정책을 만들어 할당한 경우 앱이 정책에 할당된 사용자에 Teams 앱 표시줄에 고정됩니다.</span><span class="sxs-lookup"><span data-stu-id="89215-175">If you created and assigned an app setup policy, the app is pinned to the app bar in Teams for easy access for those users who were assigned the policy.</span></span>

## <a name="update"></a><span data-ttu-id="89215-176">업데이트</span><span class="sxs-lookup"><span data-stu-id="89215-176">Update</span></span>

<span data-ttu-id="89215-177">앱을 업데이트하기 위해 개발자는 개발 및 [](#develop) 유효성 검사 섹션의 단계를 계속 [따라야](#validate) 합니다.</span><span class="sxs-lookup"><span data-stu-id="89215-177">To update an app, developers should continue to follow the steps in the [Develop](#develop) and [Validate](#validate) sections.</span></span>

<span data-ttu-id="89215-178">관리 센터의 앱 관리 페이지에서 앱을 Microsoft Teams 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89215-178">You can update the app on the Manage apps page in the Microsoft Teams admin center.</span></span> <span data-ttu-id="89215-179">이렇게하려면 관리 센터의 왼쪽 Microsoft Teams 앱 관리 **Teams**  >  **로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="89215-179">To do this, in the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span> <span data-ttu-id="89215-180">앱 이름을 클릭한 다음 업데이트를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="89215-180">Click the app name, and then click **Update**.</span></span> <span data-ttu-id="89215-181">이렇게 하면 기존 앱이 대체되어 업데이트된 앱에 대한 모든 앱 사용 권한 정책 및 앱 설정 정책이 계속 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="89215-181">Doing this replaces the existing app, and all app permission policies and app setup policies remain enforced for the updated app.</span></span>

### <a name="end-user-update-experience"></a><span data-ttu-id="89215-182">최종 사용자 업데이트 환경</span><span class="sxs-lookup"><span data-stu-id="89215-182">End user update experience</span></span>

<span data-ttu-id="89215-183">대부분의 경우 앱 업데이트를 완료한 후 최종 사용자에게 새 버전이 자동으로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="89215-183">In most cases, after you complete an app update the new version automatically appears for end users.</span></span> <span data-ttu-id="89215-184">그러나 사용자 수락을 <a href="/microsoftteams/platform/resources/schema/manifest-schema" target="_blank"></a> 완료해야 하는 Microsoft Teams 매니페스트에 대한 몇 가지 업데이트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89215-184">However, there are some updates to the <a href="/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft Teams manifest</a> that require user acceptance to complete:</span></span>

* <span data-ttu-id="89215-185">봇이 추가되거나 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="89215-185">A bot was added or removed</span></span>
* <span data-ttu-id="89215-186">기존 봇의 "botId" 속성이 변경된 경우</span><span class="sxs-lookup"><span data-stu-id="89215-186">An existing bot's "botId" property changed</span></span>
* <span data-ttu-id="89215-187">기존 봇의 "isNotificationOnly" 속성이 변경된 경우</span><span class="sxs-lookup"><span data-stu-id="89215-187">An existing bot's "isNotificationOnly" property changed</span></span>
* <span data-ttu-id="89215-188">봇의 "supportsFiles" 속성이 변경된 경우</span><span class="sxs-lookup"><span data-stu-id="89215-188">The bot's "supportsFiles" property changed</span></span>
* <span data-ttu-id="89215-189">메시징 확장이 추가되거나 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="89215-189">A Messaging extension was added or removed</span></span>
* <span data-ttu-id="89215-190">새 커넥터가 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="89215-190">A new connector was added</span></span>
* <span data-ttu-id="89215-191">새 정적 탭이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="89215-191">A new static tab was added</span></span>
* <span data-ttu-id="89215-192">새 구성 가능한 탭이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="89215-192">A new configurable tab was added</span></span>
* <span data-ttu-id="89215-193">"webApplicationInfo" 내부 속성이 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="89215-193">Properties inside "webApplicationInfo" changed</span></span>

![새 버전을 사용할 수 있는 앱을 보여 주며 앱 목록의 스크린샷](media/manage-your-custom-apps-update1.png)

![앱에 대한 업그레이드 옵션 스크린샷](media/manage-your-custom-apps-update2.png)

## <a name="related-topics"></a><span data-ttu-id="89215-196">관련 항목</span><span class="sxs-lookup"><span data-stu-id="89215-196">Related topics</span></span>

- [<span data-ttu-id="89215-197">앱 제출 API를 통해 제출된 사용자 Teams 게시</span><span class="sxs-lookup"><span data-stu-id="89215-197">Publish a custom app submitted through the Teams App Submission API</span></span>](submit-approve-custom-apps.md)
- [<span data-ttu-id="89215-198">관리 센터에서 앱 Microsoft Teams 관리</span><span class="sxs-lookup"><span data-stu-id="89215-198">Manage your apps in the Microsoft Teams admin center</span></span>](manage-apps.md)
- [<span data-ttu-id="89215-199">Teams에서 사용자 지정 앱 정책 및 설정 관리</span><span class="sxs-lookup"><span data-stu-id="89215-199">Manage custom app policies and settings in Teams</span></span>](teams-custom-app-policies-and-settings.md)
- [<span data-ttu-id="89215-200">Teams에서 앱 사용 권한 정책 관리</span><span class="sxs-lookup"><span data-stu-id="89215-200">Manage app permission policies in Teams</span></span>](teams-app-permission-policies.md)
- [<span data-ttu-id="89215-201">Teams에서 앱 설정 정책 관리</span><span class="sxs-lookup"><span data-stu-id="89215-201">Manage app setup policies in Teams</span></span>](teams-app-setup-policies.md)