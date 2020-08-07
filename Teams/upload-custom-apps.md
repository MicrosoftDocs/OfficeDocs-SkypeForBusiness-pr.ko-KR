---
title: Microsoft 팀 관리 센터에서 사용자 지정 앱 업로드
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
description: Microsoft 팀 관리 센터에서 조직의 앱 스토어에 사용자 지정 앱을 업로드 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: d43b19f4ada3ce6f0424a324cdea6f194575325b
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583647"
---
# <a name="publish-a-custom-app-by-uploading-an-app-package"></a><span data-ttu-id="b1d80-103">앱 패키지를 업로드 하 여 사용자 지정 앱 게시</span><span class="sxs-lookup"><span data-stu-id="b1d80-103">Publish a custom app by uploading an app package</span></span>

> [!NOTE]
> <span data-ttu-id="b1d80-104">사용자 지정 팀 앱을 게시 하면 조직의 앱 스토어에 있는 사용자가 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1d80-104">When you publish a custom Teams app, it's available to users in your organization's app store.</span></span> <span data-ttu-id="b1d80-105">두 가지 방법으로 사용자 지정 앱을 게시할 수 있으며, 사용 하는 방법은 앱을 가져오는 방법에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="b1d80-105">There are two ways to publish a custom app and the way that you use depends on how you get the app.</span></span> <span data-ttu-id="b1d80-106">**이 문서에서는 개발자가 사용자에 게 전송 하는 앱 패키지 (.zip 형식)를 업로드 하 여 사용자 지정 앱을 게시 하는 방법에 대해 설명**합니다.</span><span class="sxs-lookup"><span data-stu-id="b1d80-106">**This article focuses on how to publish a custom app by uploading an app package (in .zip format) that a developer sends you**.</span></span> <span data-ttu-id="b1d80-107">개발자가 팀 앱 제출 API를 통해 앱 <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">관리</a> 페이지에 직접 앱을 제출 하는 경우 사용자 지정 앱을 승인 하는 다른 방법이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1d80-107">The other method, approving a custom app, is used when a developer submits an app directly to the <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">Manage apps</a> page through the Teams App Submission API.</span></span> <span data-ttu-id="b1d80-108">해당 방법에 대해 자세히 알아보려면 <a href="https://docs.microsoft.com/microsoftteams/submit-approve-custom-apps" target="_blank">팀 앱 제출 API를 통해 제출 된 사용자 지정 앱 게시</a>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b1d80-108">To learn more about that method, see <a href="https://docs.microsoft.com/microsoftteams/submit-approve-custom-apps" target="_blank">Publish a custom app submitted through the Teams App Submission API</a>.</span></span>

<span data-ttu-id="b1d80-109">이 문서에서는 팀 앱을 개발에서 배포로 가져오는 방법에 대 한 종단 간 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1d80-109">This article provides end-to-end guidance for how to take your Teams app from development to deployment to discovery.</span></span> <span data-ttu-id="b1d80-110">이 가이드는 앱의 팀 측면에 중점을 둔 것 이며 관리자 및 IT 전문가를 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1d80-110">This guidance focuses on the Teams aspects of the app and is intended for admins and IT pros.</span></span> <span data-ttu-id="b1d80-111">팀 앱을 개발 하는 방법에 대 한 자세한 내용은 <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">팀 개발자 설명서</a>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b1d80-111">For more information about developing Teams apps, see the <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">Teams developer documentation</a>.</span></span>

![개발에서 배포 까지의 앱 개요](media/upload-custom-apps.png)

## <a name="develop"></a><span data-ttu-id="b1d80-113">개발</span><span class="sxs-lookup"><span data-stu-id="b1d80-113">Develop</span></span>

### <a name="create-your-app"></a><span data-ttu-id="b1d80-114">앱 만들기</span><span class="sxs-lookup"><span data-stu-id="b1d80-114">Create your app</span></span>

<span data-ttu-id="b1d80-115">Microsoft 팀 개발자 플랫폼을 사용 하면 개발자가 자신의 앱과 서비스를 쉽게 통합 하 여 생산성을 개선 하 고, 의사 결정을 더 빠르게 하 고, 기존 콘텐츠 및 워크플로를 통해 공동 작업을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1d80-115">The Microsoft Teams developer platform makes it easy for developers to integrate your own apps and services to improve productivity, make decisions faster, and create collaboration around existing content and workflows.</span></span> <span data-ttu-id="b1d80-116">팀 플랫폼에 빌드된 앱은 팀 클라이언트와 서비스 및 워크플로 간의 브리지로 공동 작업 플랫폼의 컨텍스트로 직접 전환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1d80-116">Apps built on the Teams platform are bridges between the Teams client and your services and workflows, bringing them directly into the context of your collaboration platform.</span></span> <span data-ttu-id="b1d80-117">자세한 내용은 <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">팀 개발자 설명서</a>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b1d80-117">For more information, go to the <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">Teams developer documentation</a>.</span></span>

## <a name="validate"></a><span data-ttu-id="b1d80-118">Validate</span><span class="sxs-lookup"><span data-stu-id="b1d80-118">Validate</span></span>

### <a name="get-the-app-package"></a><span data-ttu-id="b1d80-119">앱 패키지 다운로드</span><span class="sxs-lookup"><span data-stu-id="b1d80-119">Get the app package</span></span>

<span data-ttu-id="b1d80-120">앱을 프로덕션에 사용할 준비가 되 면 개발자는 앱 패키지를 생성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1d80-120">When the app is ready for use in production, the developer should produce an app package.</span></span> <span data-ttu-id="b1d80-121">이를 위해 <a href="https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio" target="_blank">앱 Studio</a> 를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1d80-121">They can use <a href="https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio" target="_blank">App Studio</a> for that.</span></span> <span data-ttu-id="b1d80-122">.Zip 형식으로 파일을 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1d80-122">They'll send you the file in .zip format.</span></span>

<span data-ttu-id="b1d80-123">Microsoft는 <a href="https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-approval" target="_blank">이러한 지침</a> 을 사용 하 여 앱이 전역 팀 앱 스토어의 품질 및 보안 표준을 준수 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1d80-123">Microsoft uses <a href="https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-approval" target="_blank">these guidelines</a> to ensure apps comply with the quality and security standards of the global Teams apps store.</span></span>

### <a name="allow-trusted-users-to-upload-custom-apps"></a><span data-ttu-id="b1d80-124">신뢰할 수 있는 사용자가 사용자 지정 앱을 업로드 하도록 허용</span><span class="sxs-lookup"><span data-stu-id="b1d80-124">Allow trusted users to upload custom apps</span></span>

<span data-ttu-id="b1d80-125">프로덕션 테 넌 트에서 앱이 올바르게 작동 하는지 확인 하려면 자신 및 신뢰 하는 사용자가 프로덕션 테 넌 트에서 사용자 지정 앱을 업로드 하도록 허용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1d80-125">To validate that the app is working correctly in your production tenant, you need to allow yourself and/or trusted users to upload custom apps in the production tenant.</span></span> <span data-ttu-id="b1d80-126"><a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">앱 설치 정책을</a> 사용 하 여이 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1d80-126">You use <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">app setup policies</a> to do this.</span></span>

> [!NOTE]
> <span data-ttu-id="b1d80-127">유효성 검사를 위해 앱을 프로덕션 테 넌 트에 업로드 하는 것이 불편 하거나 신뢰 하는 사용자 에게도 문제가 되지 않는 경우이 단계를 건너뛰고 [업로드](#upload) 및 [설정 및 관리](#set-up-and-manage) 섹션의 단계를 수행 하 여 unvalidated 앱을 조직의 앱 스토어에 게시 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1d80-127">If you're uncomfortable with uploading the app to your production tenant for validation, even for yourself or trusted users, you can skip this step and follow the steps in the [Upload](#upload) and [Set up and manage](#set-up-and-manage) sections to publish the unvalidated app to your organization's app store.</span></span> <span data-ttu-id="b1d80-128">그런 다음 자신 및 신뢰 하는 사용자만 해당 앱에 대 한 액세스를 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1d80-128">Then, restrict access to that app to only yourself and users you trust.</span></span> <span data-ttu-id="b1d80-129">그러면 이러한 사용자가 조직의 app store에서 앱을 다운로드 하 여 유효성 검사를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1d80-129">These users can then get the app from your organization's app store to perform validation.</span></span> <span data-ttu-id="b1d80-130">앱의 유효성을 검사 한 후에는 동일한 권한 정책을 사용 하 여 access를 열고 앱을 프로덕션에 사용할 수 있도록 롤포워드합니다.</span><span class="sxs-lookup"><span data-stu-id="b1d80-130">After the app is validated, use the same permission policies to open access and roll the app out for production use.</span></span>

<span data-ttu-id="b1d80-131">신뢰할 수 있는 사용자가 사용자 지정 앱을 업로드 하도록 허용 하려면 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="b1d80-131">To allow trusted users to upload custom apps, follow these steps:</span></span>

1. <span data-ttu-id="b1d80-132">**사용자 지정 앱과 상호 작용 허용** 조직 전체 앱 설정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1d80-132">Turn on the **Allow interaction with custom apps** org-wide app setting.</span></span> <span data-ttu-id="b1d80-133">실행할 작업:</span><span class="sxs-lookup"><span data-stu-id="b1d80-133">To do this:</span></span>
    1. <span data-ttu-id="b1d80-134">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **팀 앱**으로 이동 하 여  >  **앱을 관리**하 고 **조직 전체 앱 설정을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1d80-134">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**, and then click **Org-wide app settings**.</span></span>
    2. <span data-ttu-id="b1d80-135">**사용자 지정 앱**에서 **사용자 지정 앱과의 상호 작용 허용**을 켠 다음 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1d80-135">Under **Custom apps**, turn on **Allow interaction with custom apps**, and then click **Save**.</span></span>
2. <span data-ttu-id="b1d80-136">전역 앱 설정 정책에서 **사용자 지정 앱 업로드** 설정을 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1d80-136">Turn off the **Upload custom apps** setting in the global app setup policy.</span></span> <span data-ttu-id="b1d80-137">실행할 작업:</span><span class="sxs-lookup"><span data-stu-id="b1d80-137">To do this:</span></span>
    1. <span data-ttu-id="b1d80-138">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **팀 앱**  >  **설정 정책**으로 이동한 다음 **전역 (조직 전체 기본값)** 정책을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1d80-138">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**, and then click the **Global (Org-wide default)** policy.</span></span>
    2. <span data-ttu-id="b1d80-139">**사용자 지정 앱 업로드**를 해제 한 다음 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1d80-139">Turn off **Upload custom apps**, and then click **Save**.</span></span>
3. <span data-ttu-id="b1d80-140">사용자 지정 앱을 업로드 하 고 신뢰할 수 있는 사용자 집합에 할당할 수 있는 새 앱 설정 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b1d80-140">Create a new app setup policy that allows uploading custom apps and assign it to your set of trusted users.</span></span> <span data-ttu-id="b1d80-141">실행할 작업:</span><span class="sxs-lookup"><span data-stu-id="b1d80-141">To do this:</span></span>
    1. <span data-ttu-id="b1d80-142">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **팀 앱**  >  **설치 정책**으로 이동한 다음 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1d80-142">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**, and then click the **Add**.</span></span> <span data-ttu-id="b1d80-143">새 정책에 이름 및 설명을 지정 하 고, **사용자 지정 앱 업로드**를 설정한 다음 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1d80-143">Give the new policy a name and description, turn on **Upload custom apps**, and then click **Save**.</span></span>
    2. <span data-ttu-id="b1d80-144">만든 새 정책을 선택한 다음 **사용자 관리**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1d80-144">Select the new policy you created, and then click **Manage users**.</span></span> <span data-ttu-id="b1d80-145">사용자를 검색 하 고 **추가**를 클릭 한 다음 **적용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1d80-145">Search for a user, click **Add**, and then click **Apply**.</span></span> <span data-ttu-id="b1d80-146">이 단계를 반복 하 여 모든 신뢰할 수 있는 사용자에 게 정책을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1d80-146">Repeat this step to assign the policy to all your trusted users.</span></span>

        !["앱 설치 정책 추가" 페이지의 스크린샷](media/manage-your-lob-apps-new-app-setup-policy.png)

    <span data-ttu-id="b1d80-148">이러한 사용자는 이제 앱 매니페스트를 업로드 하 여 앱이 프로덕션 테 넌 트에서 올바르게 작동 하는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1d80-148">These users can now upload the app manifest to validate that the app is working correctly in the production tenant.</span></span>

## <a name="upload"></a><span data-ttu-id="b1d80-149">업로드가</span><span class="sxs-lookup"><span data-stu-id="b1d80-149">Upload</span></span>

<span data-ttu-id="b1d80-150">조직의 app store 사용자가 앱을 사용할 수 있도록 하려면 앱을 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1d80-150">To make the app available to users in your organization's app store, upload the app.</span></span> <span data-ttu-id="b1d80-151">Microsoft 팀 관리 센터의 <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">앱 관리</a> 페이지에서이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1d80-151">You can do this on the <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">Manage apps</a> page of the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="b1d80-152">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **팀 앱**으로  >  **앱 관리**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1d80-152">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="b1d80-153">**업로드**를 클릭 하 고 **파일 선택을**클릭 한 다음 개발자 로부터 받은 앱 패키지를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1d80-153">Click **Upload**, click **Select a file**, and then select the app package that you received from the developer.</span></span>

   ![관리 센터에서 앱을 업로드 하는 스크린샷](media/manage-your-lob-apps-upload-new-app.png) 

## <a name="set-up-and-manage"></a><span data-ttu-id="b1d80-155">설정 및 관리</span><span class="sxs-lookup"><span data-stu-id="b1d80-155">Set up and manage</span></span>

### <a name="control-access-to-the-app"></a><span data-ttu-id="b1d80-156">앱에 대 한 액세스 제어</span><span class="sxs-lookup"><span data-stu-id="b1d80-156">Control access to the app</span></span>

<span data-ttu-id="b1d80-157">기본적으로 조직의 모든 사용자가 조직의 app store에서 앱에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1d80-157">By default, all users in your organization can access the app in your organization's app store.</span></span> <span data-ttu-id="b1d80-158">앱을 사용할 권한이 있는 사용자를 제한 하 고 제어 하기 위해 앱 사용 권한 정책을 만들고 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1d80-158">To restrict and control who has permission to use the app, you can create and assign an app permission policy.</span></span> <span data-ttu-id="b1d80-159">자세히 알아보려면 <a href="https://docs.microsoft.com/microsoftteams/teams-app-permission-policies" target="_blank">팀에서 앱 권한 정책 관리</a>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b1d80-159">To learn more, see <a href="https://docs.microsoft.com/microsoftteams/teams-app-permission-policies" target="_blank">Manage app permission policies in Teams</a>.</span></span>

### <a name="pin-and-install-the-app-for-users-to-discover"></a><span data-ttu-id="b1d80-160">사용자가 검색할 수 있도록 앱을 고정 하 고 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1d80-160">Pin and install the app for users to discover</span></span>

<span data-ttu-id="b1d80-161">기본적으로 사용자는 조직의 app store로 이동 하 여 해당 앱을 찾거나 검색 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1d80-161">By default, for users to find the app they have to go to your organization's app store and browse or search for it.</span></span> <span data-ttu-id="b1d80-162">사용자가 앱에 쉽게 액세스할 수 있도록 하려면 팀의 앱 표시줄에 앱을 고정 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1d80-162">To make it easy for users to get to the app, you can pin the app to the app bar in Teams.</span></span> <span data-ttu-id="b1d80-163">이렇게 하려면 앱 설치 정책을 만들어 사용자에 게 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1d80-163">To do this, create an app setup policy and assign it to users.</span></span> <span data-ttu-id="b1d80-164">자세히 알아보려면 <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">팀에서 앱 설정 정책 관리</a>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b1d80-164">To learn more, see <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">Manage app setup policies in Teams</a>.</span></span>

### <a name="search-the-audit-log-for-teams-app-events"></a><span data-ttu-id="b1d80-165">팀에 대 한 감사 로그 앱 이벤트 검색</span><span class="sxs-lookup"><span data-stu-id="b1d80-165">Search the audit log for Teams app events</span></span>

<span data-ttu-id="b1d80-166">감사 로그를 검색 하 여 조직의 팀 앱 활동을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1d80-166">You can search the audit log to view Teams apps activity in your organization.</span></span> <span data-ttu-id="b1d80-167">감사 로그를 검색 하 고 감사 로그에 기록 된 팀 활동 목록을 확인 하는 방법에 대 한 자세한 내용은 <a href="https://docs.microsoft.com/microsoftteams/audit-log-events" target="_blank">팀에서 이벤트 감사 로그 검색</a>을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b1d80-167">To learn more about how to search the audit log and to see a list of Teams activities that are logged in the audit log, see <a href="https://docs.microsoft.com/microsoftteams/audit-log-events" target="_blank">Search the audit log for events in Teams</a>.</span></span>

<span data-ttu-id="b1d80-168">감사 로그를 검색 하려면 먼저 <a href="https://protection.office.com" target="_blank">보안 & 준수 센터</a>에서 감사를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1d80-168">Before you can search the audit log, you have to first turn on auditing in the <a href="https://protection.office.com" target="_blank">Security & Compliance Center</a>.</span></span> <span data-ttu-id="b1d80-169">자세히 알아보려면 <a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">감사 로그 검색 설정 또는 해제</a>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b1d80-169">To learn more, see <a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">Turn audit log search on or off</a>.</span></span> <span data-ttu-id="b1d80-170">감사 데이터는 감사를 설정한 지점 에서만 사용할 수 있다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="b1d80-170">Keep in mind that audit data is only available from the point at which you turned on auditing.</span></span>

## <a name="discover-and-adopt"></a><span data-ttu-id="b1d80-171">검색 및 채택</span><span class="sxs-lookup"><span data-stu-id="b1d80-171">Discover and adopt</span></span>

<span data-ttu-id="b1d80-172">앱에 대 한 사용 권한이 있는 사용자는 조직의 앱 스토어에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1d80-172">Users who have permissions to the app can find it in your organization's app store.</span></span> <span data-ttu-id="b1d80-173">조직의 사용자 지정 앱을 찾을 수 있도록 앱 페이지에서 \*\* *조직 이름* 으로 기본\*\* 설정으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1d80-173">Go to **Built for *Your Organization Name*** on the Apps page to find your organization's custom apps.</span></span>

![<span data-ttu-id="b1d80-174">게시 된 앱을 보여 주는 앱 페이지 스크린샷</span><span class="sxs-lookup"><span data-stu-id="b1d80-174">Screenshot of Apps page showing published app</span></span> ](media/custom-app-lifecycle-discovery.png)

<span data-ttu-id="b1d80-175">앱 설치 정책을 만들고 할당 한 경우 앱은 정책에 할당 된 사용자에 게 쉽게 액세스할 수 있도록 팀의 앱 표시줄에 고정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1d80-175">If you created and assigned an app setup policy, the app is pinned to the app bar in Teams for easy access for those users who were assigned the policy.</span></span>

## <a name="update"></a><span data-ttu-id="b1d80-176">Update</span><span class="sxs-lookup"><span data-stu-id="b1d80-176">Update</span></span>

<span data-ttu-id="b1d80-177">앱을 업데이트 하려면 개발자가 계속 해 서 [개발](#develop) 및 [유효성 검사](#validate) 섹션의 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="b1d80-177">To update an app, developers should continue to follow the steps in the [Develop](#develop) and [Validate](#validate) sections.</span></span>

<span data-ttu-id="b1d80-178">Microsoft 팀 관리 센터의 앱 관리 페이지에서 앱을 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1d80-178">You can update the app on the Manage apps page in the Microsoft Teams admin center.</span></span> <span data-ttu-id="b1d80-179">이렇게 하려면 Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **팀 앱**앱으로 이동  >  **Manage apps**합니다.</span><span class="sxs-lookup"><span data-stu-id="b1d80-179">To do this, in the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span> <span data-ttu-id="b1d80-180">앱 이름을 클릭 한 다음 **업데이트**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1d80-180">Click the app name, and then click **Update**.</span></span> <span data-ttu-id="b1d80-181">이렇게 하면 기존 앱이 바뀌며, 모든 앱 사용 권한 정책 및 앱 설치 정책은 업데이트 된 앱에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1d80-181">Doing this replaces the existing app, and all app permission policies and app setup policies remain enforced for the updated app.</span></span>

### <a name="end-user-update-experience"></a><span data-ttu-id="b1d80-182">최종 사용자 업데이트 환경</span><span class="sxs-lookup"><span data-stu-id="b1d80-182">End user update experience</span></span>

<span data-ttu-id="b1d80-183">대부분의 경우 앱 업데이트를 완료 하면 최종 사용자에 게 새 버전이 자동으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1d80-183">In most cases, after you complete an app update the new version automatically appears for end users.</span></span> <span data-ttu-id="b1d80-184">그러나 사용자에 게 완료 해야 하는 <a href="https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft 팀 매니페스트에</a> 대 한 몇 가지 업데이트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1d80-184">However, there are some updates to the <a href="https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft Teams manifest</a> that require user acceptance to complete:</span></span>

* <span data-ttu-id="b1d80-185">봇이 추가 되거나 제거 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b1d80-185">A bot was added or removed</span></span>
* <span data-ttu-id="b1d80-186">기존 봇의 "botId" 속성이 변경 됨</span><span class="sxs-lookup"><span data-stu-id="b1d80-186">An existing bot's "botId" property changed</span></span>
* <span data-ttu-id="b1d80-187">기존 봇의 "isNotificationOnly" 속성이 변경 됨</span><span class="sxs-lookup"><span data-stu-id="b1d80-187">An existing bot's "isNotificationOnly" property changed</span></span>
* <span data-ttu-id="b1d80-188">Bot "supportsFiles" 속성이 변경 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b1d80-188">The bot's "supportsFiles" property changed</span></span>
* <span data-ttu-id="b1d80-189">메시징 확장이 추가 또는 제거 됨</span><span class="sxs-lookup"><span data-stu-id="b1d80-189">A Messaging extension was added or removed</span></span>
* <span data-ttu-id="b1d80-190">새 커넥터가 추가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b1d80-190">A new connector was added</span></span>
* <span data-ttu-id="b1d80-191">새 정적 탭이 추가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b1d80-191">A new static tab was added</span></span>
* <span data-ttu-id="b1d80-192">구성 가능한 새 탭이 추가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b1d80-192">A new configurable tab was added</span></span>
* <span data-ttu-id="b1d80-193">"WebApplicationInfo" 내의 속성 변경 됨</span><span class="sxs-lookup"><span data-stu-id="b1d80-193">Properties inside "webApplicationInfo" changed</span></span>

![새 버전을 사용할 수 있는 앱을 표시 하는 앱 목록 스크린샷](media/manage-your-custom-apps-update1.png)

![앱의 업그레이드 옵션 스크린샷](media/manage-your-custom-apps-update2.png)

## <a name="related-topics"></a><span data-ttu-id="b1d80-196">관련 항목</span><span class="sxs-lookup"><span data-stu-id="b1d80-196">Related topics</span></span>

- [<span data-ttu-id="b1d80-197">팀 앱 제출 API를 통해 제출 된 사용자 지정 앱 게시</span><span class="sxs-lookup"><span data-stu-id="b1d80-197">Publish a custom app submitted through the Teams App Submission API</span></span>](submit-approve-custom-apps.md)
- [<span data-ttu-id="b1d80-198">Microsoft 팀 관리 센터에서 앱 관리</span><span class="sxs-lookup"><span data-stu-id="b1d80-198">Manage your apps in the Microsoft Teams admin center</span></span>](manage-apps.md)
- [<span data-ttu-id="b1d80-199">Teams에서 사용자 지정 앱 정책 및 설정 관리</span><span class="sxs-lookup"><span data-stu-id="b1d80-199">Manage custom app policies and settings in Teams</span></span>](teams-custom-app-policies-and-settings.md)
- [<span data-ttu-id="b1d80-200">Teams에서 앱 사용 권한 정책 관리</span><span class="sxs-lookup"><span data-stu-id="b1d80-200">Manage app permission policies in Teams</span></span>](teams-app-permission-policies.md)
- [<span data-ttu-id="b1d80-201">Teams에서 앱 설정 정책 관리</span><span class="sxs-lookup"><span data-stu-id="b1d80-201">Manage app setup policies in Teams</span></span>](teams-app-setup-policies.md)
