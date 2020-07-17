---
title: Microsoft 팀에서 사용자 지정 앱 관리
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: joglocke
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
description: 개발에서 배포에 이르기까지 사용자 지정 팀 앱을 사용 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 705f5ecf5628dd981a4deb3ded847b3da8e9ea08
ms.sourcegitcommit: 6a4bd155e73ab21944dd5f4f0c776e4cd0508147
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/24/2020
ms.locfileid: "44868515"
---
# <a name="manage-your-custom-apps-in-microsoft-teams"></a><span data-ttu-id="be3e5-103">Microsoft 팀에서 사용자 지정 앱 관리</span><span class="sxs-lookup"><span data-stu-id="be3e5-103">Manage your custom apps in Microsoft Teams</span></span>

<span data-ttu-id="be3e5-104">이 문서에서는 개발에서 배포에 이르기까지 팀 앱을 사용 하는 방법에 대 한 종단 간 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="be3e5-104">This article provides end-to-end guidance for how to take your Teams app from development to deployment.</span></span> <span data-ttu-id="be3e5-105">이 지침은 앱의 팀 측면에 중점을 둔 것 이며 IT 전문가를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="be3e5-105">This guidance focuses on the Teams aspects of the app and is intended for IT pros.</span></span> <span data-ttu-id="be3e5-106">팀 앱을 개발 하는 방법에 대 한 자세한 내용은 <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">여기</a>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="be3e5-106">For more information on developing Teams apps, see <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">here</a>.</span></span>

![개발에서 배포 까지의 앱 개요](media/manage-your-lob-apps.png)

## <a name="getting-started"></a><span data-ttu-id="be3e5-108">시작</span><span class="sxs-lookup"><span data-stu-id="be3e5-108">Getting started</span></span>

<span data-ttu-id="be3e5-109">팀에서 사용자 지정 앱을 만들고 관리 하려면 두 개의 테 넌 트, 개발을 위한 테스트 테 넌 트 및 프로덕션 테 넌 트가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="be3e5-109">To create and manage custom apps in Teams, you'll need two tenants: a test tenant for development and a production tenant.</span></span>

> [!NOTE]
> <span data-ttu-id="be3e5-110">테스트 테 넌 트가 아직 없는 경우에는 신속 하 게 만들고 Office 365 개발자 프로그램을 사용 하 여 테스트 데이터로 채울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be3e5-110">If you don't already have a test tenant, you can quickly create one and populate it with test data using the Office 365 Developer Program.</span></span> <span data-ttu-id="be3e5-111"><a href="https://developer.microsoft.com/office/dev-program" target="_blank">자세한 내용은 여기를 참조</a>하세요.</span><span class="sxs-lookup"><span data-stu-id="be3e5-111"><a href="https://developer.microsoft.com/office/dev-program" target="_blank">Learn more here</a>.</span></span>

## <a name="step-1-develop-and-test"></a><span data-ttu-id="be3e5-112">1 단계: 개발 및 테스트</span><span class="sxs-lookup"><span data-stu-id="be3e5-112">Step 1: Develop and test</span></span>

### <a name="create-test-users"></a><span data-ttu-id="be3e5-113">테스트 사용자 만들기</span><span class="sxs-lookup"><span data-stu-id="be3e5-113">Create test users</span></span>

<span data-ttu-id="be3e5-114">사내 또는 외부에 있든 관계 없이 개발자가 테스트 테 넌 트에 계정이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="be3e5-114">Make sure that your developers, whether in-house or external, have accounts in your test tenant.</span></span> <span data-ttu-id="be3e5-115"><a href="https://docs.microsoft.com/microsoft-365/admin/add-users/add-users" target="_blank">사용자 추가에 대해 자세히 알아보세요</a>.</span><span class="sxs-lookup"><span data-stu-id="be3e5-115"><a href="https://docs.microsoft.com/microsoft-365/admin/add-users/add-users" target="_blank">Learn more about adding users</a>.</span></span>

### <a name="allow-custom-apps-in-the-test-tenant"></a><span data-ttu-id="be3e5-116">테스트 테 넌 트에서 사용자 지정 앱 허용</span><span class="sxs-lookup"><span data-stu-id="be3e5-116">Allow custom apps in the test tenant</span></span>

<span data-ttu-id="be3e5-117">개발자에 게 테스트에 필요한 액세스 권한을 부여 하려면 테스트 테 넌 트의 모든 사용자가 사용자 지정 앱 (테스트용 로드 라고도 함)을 업로드 하도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="be3e5-117">To give developers the access they need for testing, allow all users in the test tenant to upload custom apps (also known as sideloading).</span></span> <span data-ttu-id="be3e5-118">이를 통해 개발자는 팀 앱 스토어에 앱을 제출할 필요 없이 개인적으로 사용 하거나 테스트 테 넌 트를 통해 사용자 지정 앱을 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be3e5-118">This lets developers upload a custom app to be used personally or across the test tenant without having to submit the app to the Teams apps store.</span></span> <span data-ttu-id="be3e5-119">사용자 지정 앱을 업로드 하면 개발자가 앱을 테스트 한 후 보다 광범위 하 게 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be3e5-119">Uploading a custom app lets developers test an app before you distribute it more widely.</span></span>

<span data-ttu-id="be3e5-120">사용자가 사용자 지정 앱을 업로드 하도록 허용 하려면 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="be3e5-120">To allow users to upload custom apps, follow these steps:</span></span>

1. <span data-ttu-id="be3e5-121">**사용자 지정 앱과 상호 작용 허용** 조직 전체 앱 설정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="be3e5-121">Turn on the **Allow interaction with custom apps** org-wide app setting.</span></span> <span data-ttu-id="be3e5-122">실행할 작업:</span><span class="sxs-lookup"><span data-stu-id="be3e5-122">To do this:</span></span>
    1. <span data-ttu-id="be3e5-123"><a href="https://admin.teams.microsoft.com/" target="_blank">Microsoft 팀 관리 센터</a>의 왼쪽 탐색 창에서 **팀 앱**으로 이동 하 여  >  **앱을 관리**하 고 **조직 전체 앱 설정을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="be3e5-123">In the left navigation of the <a href="https://admin.teams.microsoft.com/" target="_blank">Microsoft Teams admin center</a>, go to **Teams apps** > **Manage apps**, and then click **Org-wide app settings**.</span></span>
    2. <span data-ttu-id="be3e5-124">**사용자 지정 앱**에서 **사용자 지정 앱과의 상호 작용 허용**을 켠 다음 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="be3e5-124">Under **Custom apps**, turn on **Allow interaction with custom apps**, and then click **Save**.</span></span>

    !["사용자 지정 앱과 상호 작용 허용" 조직 전체 앱 설정의 스크린샷](media/manage-your-lob-apps-org-wide-custom-apps.png)

2. <span data-ttu-id="be3e5-126">전역 앱 설정 정책에서 **사용자 지정 앱 업로드** 설정을 켭니다.</span><span class="sxs-lookup"><span data-stu-id="be3e5-126">Turn on the **Upload custom apps** setting in the global app setup policy.</span></span> <span data-ttu-id="be3e5-127">실행할 작업:</span><span class="sxs-lookup"><span data-stu-id="be3e5-127">To do this:</span></span>
    1. <span data-ttu-id="be3e5-128"><a href="https://admin.teams.microsoft.com/" target="_blank">Microsoft 팀 관리 센터</a>의 왼쪽 탐색 창에서 **팀 앱**  >  **설정 정책**으로 이동한 다음 **전역 (조직 전체 기본값)** 정책을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="be3e5-128">In the left navigation of the <a href="https://admin.teams.microsoft.com/" target="_blank">Microsoft Teams admin center</a>, go to **Teams apps** > **Setup policies**, and then click the **Global (Org-wide default)** policy.</span></span>
    2. <span data-ttu-id="be3e5-129">**사용자 지정 앱 업로드**를 켠 다음 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="be3e5-129">Turn on **Upload custom apps**, and then click **Save**.</span></span>

    !["사용자 지정 앱 업로드" 앱 설치 정책 설정의 스크린샷](media/manage-your-lob-apps-app-setup-custom-apps.png)

> [!NOTE]
> <span data-ttu-id="be3e5-131">팀 수준의 업로드 사용자 지정 앱 설정도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be3e5-131">There's also an upload custom app setting at the team level.</span></span> <span data-ttu-id="be3e5-132">기본적으로이 설정은 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be3e5-132">By default this setting is on.</span></span> <span data-ttu-id="be3e5-133">그러나 개발자가 팀에 사용자 지정 앱을 업로드할 수 없는 경우에는 다음 단계를 따라 설정을 <a href="https://docs.microsoft.com/microsoftteams/teams-custom-app-policies-and-settings#configure-the-team-custom-app-setting" target="_blank">확인 합니다.</a></span><span class="sxs-lookup"><span data-stu-id="be3e5-133">However, if developers are unable to upload a custom app to a team, check the setting by following the steps <a href="https://docs.microsoft.com/microsoftteams/teams-custom-app-policies-and-settings#configure-the-team-custom-app-setting" target="_blank">here</a>.</span></span>

### <a name="create-your-app"></a><span data-ttu-id="be3e5-134">앱 만들기</span><span class="sxs-lookup"><span data-stu-id="be3e5-134">Create your app</span></span>

<span data-ttu-id="be3e5-135">이제 개발자에 게 앱을 만드는 데 필요한 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be3e5-135">Developers should now have what they need to create your app.</span></span> <span data-ttu-id="be3e5-136">여기에 대 한 지침을 보려면 <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">여기</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="be3e5-136">See <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">here</a> for guidance on that.</span></span>

## <a name="step-2-validate-in-production"></a><span data-ttu-id="be3e5-137">2 단계: 프로덕션에서 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="be3e5-137">Step 2: Validate in production</span></span>

### <a name="get-the-app-package"></a><span data-ttu-id="be3e5-138">앱 패키지 다운로드</span><span class="sxs-lookup"><span data-stu-id="be3e5-138">Get the app package</span></span>

<span data-ttu-id="be3e5-139">앱을 프로덕션에 사용할 준비가 되 면 개발자는 앱 패키지를 생성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="be3e5-139">When the app is ready for use in production, the developer should produce an app package.</span></span> <span data-ttu-id="be3e5-140">이를 위해 <a href="https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio" target="_blank">앱 Studio</a> 를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be3e5-140">They can use <a href="https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio" target="_blank">App Studio</a> for that.</span></span> <span data-ttu-id="be3e5-141">.Zip 형식으로 파일을 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="be3e5-141">They'll send you the file in .zip format.</span></span>

<span data-ttu-id="be3e5-142">Microsoft는 <a href="https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-approval" target="_blank">이러한 지침</a> 을 사용 하 여 앱이 전역 팀 앱 스토어의 품질 및 보안 표준을 준수 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="be3e5-142">Microsoft uses <a href="https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-approval" target="_blank">these guidelines</a> to ensure apps comply with the quality and security standards of the global Teams apps store.</span></span>

### <a name="allow-trusted-users-to-upload-custom-apps-in-the-production-tenant"></a><span data-ttu-id="be3e5-143">신뢰할 수 있는 사용자가 프로덕션 테 넌 트에서 사용자 지정 앱을 업로드 하도록 허용</span><span class="sxs-lookup"><span data-stu-id="be3e5-143">Allow trusted users to upload custom apps in the production tenant</span></span>

<span data-ttu-id="be3e5-144">프로덕션 테 넌 트에서 앱이 올바르게 작동 하는지 확인 하려면 조직에서 자신 및/또는 신뢰할 수 있는 사용자가 사용자 지정 앱을 업로드 하도록 허용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="be3e5-144">To validate that the app is working correctly in your production tenant, you need to allow yourself and/or trusted users in your organization to upload custom apps.</span></span>  <span data-ttu-id="be3e5-145">앞의 <a href="https://docs.microsoft.com/microsoftteams/manage-your-lob-apps#allow-custom-apps-in-the-test-tenant" target="_blank">단계</a>에서와 같이이 작업을 수행 하는 데 앱 설치 정책을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="be3e5-145">Much like in the earlier <a href="https://docs.microsoft.com/microsoftteams/manage-your-lob-apps#allow-custom-apps-in-the-test-tenant" target="_blank">step</a>, you use app setup policies to do this.</span></span>

> [!NOTE]
> <span data-ttu-id="be3e5-146">유효성 검사를 위해 앱을 프로덕션 테 넌 트에 업로드 하는 것이 불편 하거나 신뢰 하는 사용자 라도이 단계를 건너뛰고 3-4 단계를 수행 하 여 unvalidated 앱을 테 넌 트 앱 스토어에 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be3e5-146">If you're uncomfortable with uploading the app to your production tenant for validation, even for yourself or trusted users, you can skip this step and follow steps 3 and 4 to upload the unvalidated app to your tenant app store.</span></span> <span data-ttu-id="be3e5-147">그런 다음 자신 및 신뢰 하는 사용자만 해당 앱에 대 한 액세스를 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="be3e5-147">Then, restrict access to that app to only yourself and users you trust.</span></span> <span data-ttu-id="be3e5-148">그러면 이러한 사용자가 테 넌 트 앱 스토어에서 앱을 다운로드 하 여 유효성 검사를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be3e5-148">These users can then get the app from the tenant app store to perform validation.</span></span> <span data-ttu-id="be3e5-149">앱의 유효성을 검사 한 후에는 동일한 권한 정책을 사용 하 여 access를 열고 앱을 프로덕션에 사용할 수 있도록 롤포워드합니다.</span><span class="sxs-lookup"><span data-stu-id="be3e5-149">After the app is validated, use the same permission policies to open access and roll the app out for production use.</span></span>

<span data-ttu-id="be3e5-150">신뢰할 수 있는 사용자가 사용자 지정 앱을 업로드 하도록 허용 하려면 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="be3e5-150">To allow trusted users to upload custom apps, follow these steps:</span></span>

1. <span data-ttu-id="be3e5-151">**사용자 지정 앱과 상호 작용 허용** 조직 전체 앱 설정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="be3e5-151">Turn on the **Allow interaction with custom apps** org-wide app setting.</span></span> <span data-ttu-id="be3e5-152">실행할 작업:</span><span class="sxs-lookup"><span data-stu-id="be3e5-152">To do this:</span></span>
    1. <span data-ttu-id="be3e5-153"><a href="https://admin.teams.microsoft.com/" target="_blank">Microsoft 팀 관리 센터</a>의 왼쪽 탐색 창에서 **팀 앱**으로 이동 하 여  >  **앱을 관리**하 고 **조직 전체 앱 설정을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="be3e5-153">In the left navigation of the <a href="https://admin.teams.microsoft.com/" target="_blank">Microsoft Teams admin center</a>, go to **Teams apps** > **Manage apps**, and then click **Org-wide app settings**.</span></span>
    2. <span data-ttu-id="be3e5-154">**사용자 지정 앱**에서 **사용자 지정 앱과의 상호 작용 허용**을 켠 다음 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="be3e5-154">Under **Custom apps**, turn on **Allow interaction with custom apps**, and then click **Save**.</span></span>
2. <span data-ttu-id="be3e5-155">전역 앱 설정 정책에서 **사용자 지정 앱 업로드** 설정을 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="be3e5-155">Turn off the **Upload custom apps** setting in the global app setup policy.</span></span> <span data-ttu-id="be3e5-156">실행할 작업:</span><span class="sxs-lookup"><span data-stu-id="be3e5-156">To do this:</span></span>
    1. <span data-ttu-id="be3e5-157"><a href="https://admin.teams.microsoft.com/" target="_blank">Microsoft 팀 관리 센터</a>의 왼쪽 탐색 창에서 **팀 앱**  >  **설정 정책**으로 이동한 다음 **전역 (조직 전체 기본값)** 정책을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="be3e5-157">In the left navigation of the <a href="https://admin.teams.microsoft.com/" target="_blank">Microsoft Teams admin center</a>, go to **Teams apps** > **Setup policies**, and then click the **Global (Org-wide default)** policy.</span></span>
    2. <span data-ttu-id="be3e5-158">**사용자 지정 앱 업로드**를 해제 한 다음 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="be3e5-158">Turn off **Upload custom apps**, and then click **Save**.</span></span>
3. <span data-ttu-id="be3e5-159">사용자 지정 앱을 업로드 하 고 신뢰할 수 있는 사용자 집합에 할당할 수 있는 새 앱 설정 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="be3e5-159">Create a new app setup policy that allows uploading custom apps and assign it to your set of trusted users.</span></span> <span data-ttu-id="be3e5-160">실행할 작업:</span><span class="sxs-lookup"><span data-stu-id="be3e5-160">To do this:</span></span>
    1. <span data-ttu-id="be3e5-161"><a href="https://admin.teams.microsoft.com/" target="_blank">Microsoft 팀 관리 센터</a>의 왼쪽 탐색 창에서 **팀 앱**  >  **설치 정책**으로 이동한 다음 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="be3e5-161">In the left navigation of the <a href="https://admin.teams.microsoft.com/" target="_blank">Microsoft Teams admin center</a>, go to **Teams apps** > **Setup policies**, and then click the **Add**.</span></span> <span data-ttu-id="be3e5-162">새 정책에 이름 및 설명을 지정 하 고, **사용자 지정 앱 업로드**를 설정한 다음 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="be3e5-162">Give the new policy a name and description, turn on **Upload custom apps**, and then click **Save**.</span></span>
    2. <span data-ttu-id="be3e5-163">만든 새 정책을 선택한 다음 **사용자 관리**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="be3e5-163">Select the new policy you created, and then click **Manage users**.</span></span> <span data-ttu-id="be3e5-164">사용자를 검색 하 고 **추가**를 클릭 한 다음 **적용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="be3e5-164">Search for a user, click **Add**, and then click **Apply**.</span></span> <span data-ttu-id="be3e5-165">이 단계를 반복 하 여 모든 신뢰할 수 있는 사용자에 게 정책을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="be3e5-165">Repeat this step to assign the policy to all your trusted users.</span></span>

        !["앱 설치 정책 추가" 페이지의 스크린샷](media/manage-your-lob-apps-new-app-setup-policy.png)

    <span data-ttu-id="be3e5-167">이러한 사용자는 이제 앱 매니페스트를 업로드 하 여 앱이 프로덕션 테 넌 트에서 올바르게 작동 하는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be3e5-167">These users can now upload the app manifest to validate that the app is working correctly in the production tenant.</span></span>

## <a name="step-3-upload-to-the-tenant-app-catalog"></a><span data-ttu-id="be3e5-168">3 단계: 테 넌 트 앱 카탈로그에 업로드</span><span class="sxs-lookup"><span data-stu-id="be3e5-168">Step 3: Upload to the tenant app catalog</span></span>

<span data-ttu-id="be3e5-169">테 넌 트 앱 스토어의 사용자가 앱을 사용할 수 있도록 하려면 앱을 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="be3e5-169">To make the app available to users in the tenant app store, upload the app.</span></span> <span data-ttu-id="be3e5-170">Microsoft 팀 관리 센터의 [앱 관리](manage-apps.md) 페이지에서이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be3e5-170">You can do this on the [Manage apps](manage-apps.md) page of the Microsoft Teams admin center.</span></span>

![관리 센터의 앱 관리 페이지 스크린샷](media/manage-your-lob-apps-upload-new-app.png)

## <a name="step-4-configure-and-assign-permissions"></a><span data-ttu-id="be3e5-172">4 단계: 사용 권한 구성 및 할당</span><span class="sxs-lookup"><span data-stu-id="be3e5-172">Step 4: Configure and assign permissions</span></span>

### <a name="control-access-to-the-app"></a><span data-ttu-id="be3e5-173">앱에 대 한 액세스 제어</span><span class="sxs-lookup"><span data-stu-id="be3e5-173">Control access to the app</span></span>

<span data-ttu-id="be3e5-174">기본적으로 모든 사용자는 팀 앱 스토어에서이 앱에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be3e5-174">By default, all users have access to this app in the the Teams apps store.</span></span> <span data-ttu-id="be3e5-175">앱을 사용할 권한이 있는 사용자를 제한 하 고 제어 하려면 새 앱 사용 권한 정책을 만들고 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be3e5-175">To restrict and control who has permission to use the app, you can create and assign a new app permission policy.</span></span> <span data-ttu-id="be3e5-176">단계 <a href="https://docs.microsoft.com/microsoftteams/teams-app-permission-policies#create-a-custom-app-permission-policy" target="_blank">를 따르세요.</a></span><span class="sxs-lookup"><span data-stu-id="be3e5-176">Follow the steps <a href="https://docs.microsoft.com/microsoftteams/teams-app-permission-policies#create-a-custom-app-permission-policy" target="_blank">here</a>.</span></span>

!["앱 권한 정책 추가" 페이지의 스크린샷](media/manage-your-lob-apps-new-app-permission-policy.png)

### <a name="pin-the-app-for-users-to-discover"></a><span data-ttu-id="be3e5-178">사용자가 검색할 수 있도록 앱 고정</span><span class="sxs-lookup"><span data-stu-id="be3e5-178">Pin the app for users to discover</span></span>

<span data-ttu-id="be3e5-179">기본적으로 사용자가이 앱을 찾으려면 팀 앱으로 이동 하 여 저장 하 고 찾아보거나 검색 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="be3e5-179">By default, for users to find this app they would have to go to Teams apps store and browse or search for it.</span></span> <span data-ttu-id="be3e5-180">사용자가 앱에 쉽게 액세스할 수 있도록 하려면 팀의 앱 표시줄에 앱을 고정 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="be3e5-180">To make it easy for users to get to the app, you can pin the app to the app bar in Teams.</span></span> <span data-ttu-id="be3e5-181">이렇게 하려면 새 앱 설치 정책을 만들어 사용자에 게 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="be3e5-181">To do this, create a new app setup policy and assign it to users.</span></span> <span data-ttu-id="be3e5-182">단계 <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies#create-a-custom-app-setup-policy" target="_blank">를 따르세요.</a></span><span class="sxs-lookup"><span data-stu-id="be3e5-182">Follow the steps  <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies#create-a-custom-app-setup-policy" target="_blank">here</a>.</span></span>

!["고정 된 앱 추가" 창의 스크린샷](media/manage-your-lob-apps-pinned-apps.png)

## <a name="step-5-update-the-app"></a><span data-ttu-id="be3e5-184">5 단계: 앱 업데이트</span><span class="sxs-lookup"><span data-stu-id="be3e5-184">Step 5: Update the app</span></span>

![개발에서 배포 까지의 앱 개요](media/manage-your-lob-apps-update.png)

<span data-ttu-id="be3e5-186">앱을 업데이트 하려면 개발자가 [1 단계](#step-1-develop-and-test) 와 [2 단계](#step-2-validate-in-production)를 계속 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="be3e5-186">To update an app, developers should continue to follow [step 1](#step-1-develop-and-test) and [step 2](#step-2-validate-in-production).</span></span>

<span data-ttu-id="be3e5-187">테 넌 트 앱 카탈로그를 통해 앱을 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be3e5-187">You can update the app through the tenant app catalog.</span></span> <span data-ttu-id="be3e5-188">이렇게 하려면 Microsoft 팀 관리 센터에서 **팀 앱**앱  >  **관리**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="be3e5-188">To do this, in the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span> <span data-ttu-id="be3e5-189">앱 목록에서 앱 이름을 클릭 한 다음 **업데이트**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="be3e5-189">In the list of apps, click the app name, and then click **Update**.</span></span> <span data-ttu-id="be3e5-190">이렇게 하면 테 넌 트 앱 카탈로그의 기존 앱이 바뀌고, 모든 앱 권한 정책 및 앱 설정 정책은 업데이트 된 앱에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="be3e5-190">Doing this replaces the existing app in the tenant app catalog, and all app permission policies and app setup policies remain enforced for the updated app.</span></span>

### <a name="end-user-update-experience"></a><span data-ttu-id="be3e5-191">최종 사용자 업데이트 환경</span><span class="sxs-lookup"><span data-stu-id="be3e5-191">End user update experience</span></span>

<span data-ttu-id="be3e5-192">대부분의 경우 앱 업데이트를 완료 하면 최종 사용자에 게 새 버전이 자동으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="be3e5-192">In most cases, after you complete an app update the new version will automatically appear for end users.</span></span> <span data-ttu-id="be3e5-193">그러나 사용자에 게 완료 해야 하는 <a href="https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft 팀 매니페스트에</a> 대 한 몇 가지 업데이트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be3e5-193">However, there are some updates to the <a href="https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft Teams manifest</a> that require user acceptance to complete:</span></span>

* <span data-ttu-id="be3e5-194">봇이 추가 되거나 제거 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="be3e5-194">A bot was added or removed</span></span>
* <span data-ttu-id="be3e5-195">기존 봇의 "botId" 속성이 변경 됨</span><span class="sxs-lookup"><span data-stu-id="be3e5-195">An existing bot's "botId" property changed</span></span>
* <span data-ttu-id="be3e5-196">기존 봇의 "isNotificationOnly" 속성이 변경 됨</span><span class="sxs-lookup"><span data-stu-id="be3e5-196">An existing bot's "isNotificationOnly" property changed</span></span>
* <span data-ttu-id="be3e5-197">Bot "supportsFiles" 속성이 변경 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="be3e5-197">The bot's "supportsFiles" property changed</span></span>
* <span data-ttu-id="be3e5-198">메시징 확장이 추가 또는 제거 됨</span><span class="sxs-lookup"><span data-stu-id="be3e5-198">A Messaging extension was added or removed</span></span>
* <span data-ttu-id="be3e5-199">새 커넥터가 추가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="be3e5-199">A new connector was added</span></span>
* <span data-ttu-id="be3e5-200">새 정적 탭이 추가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="be3e5-200">A new static tab was added</span></span>
* <span data-ttu-id="be3e5-201">구성 가능한 새 탭이 추가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="be3e5-201">A new configurable tab was added</span></span>
* <span data-ttu-id="be3e5-202">"WebApplicationInfo" 내의 속성 변경 됨</span><span class="sxs-lookup"><span data-stu-id="be3e5-202">Properties inside "webApplicationInfo" changed</span></span>

![새 버전을 사용할 수 있는 앱을 표시 하는 앱 목록 스크린샷](media/manage-your-custom-apps-update1.png)

![앱의 업그레이드 옵션 스크린샷](media/manage-your-custom-apps-update2.png)

## <a name="related-apps"></a><span data-ttu-id="be3e5-205">관련 앱</span><span class="sxs-lookup"><span data-stu-id="be3e5-205">Related apps</span></span>

- [<span data-ttu-id="be3e5-206">Microsoft 팀 관리 센터에서 앱 관리</span><span class="sxs-lookup"><span data-stu-id="be3e5-206">Manage your apps in the Microsoft Teams admin center</span></span>](manage-apps.md)
