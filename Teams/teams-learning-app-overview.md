---
title: Teams Learning 앱에 대한 사용 권한 설치, 관리 및 할당(비공개 미리 보기)
author: ChuckEdmonson
ms.author: chucked
manager: pamgreenMSFT
ms.date: ''
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ChrisArnoldMSFT, LearningDocs2020
localization_priority: Normal
search.appverid: ''
ms.collection: ''
description: Microsoft Teams Learning 앱을 사용하여 직원이 조직 전체의 콘텐츠 라이브러리에서 공유, 할당 및 학습할 수 있는 중앙 허브를 만들 수 있습니다.
f1.keywords: ''
appliesto:
- Microsoft Teams
ms.custom: ''
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: a8fe0d3b4f86de34accb1519c80a391a9e395fbe
ms.sourcegitcommit: 380a96f1ed2cefb429286854f06546bdb28d7d74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/17/2020
ms.locfileid: "49703459"
---
# <a name="install-manage-and-assign-permissions-for-the-teams-learning-app-private-preview"></a><span data-ttu-id="253c6-103">Teams Learning 앱에 대한 사용 권한 설치, 관리 및 할당(비공개 미리 보기)</span><span class="sxs-lookup"><span data-stu-id="253c6-103">Install, manage, and assign permissions for the Teams Learning app (private preview)</span></span>

<span data-ttu-id="253c6-104">*이 문서에는 비공개 미리 보기 상태인 Teams Learning 앱에 대한 예비 콘텐츠가 포함되어 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="253c6-104">*This article contains preliminary content for the Teams Learning app, which is in private preview.*</span></span>

<span data-ttu-id="253c6-105">Microsoft Teams 학습 앱(비공개 미리 보기)을 통해 조직의 팀과 개인이 하루 중 자연스러운 학습을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="253c6-105">The Microsoft Teams Learning app (private preview) empowers teams and individuals in your organization to make learning a natural part of their day.</span></span> <span data-ttu-id="253c6-106">이 앱은 직원이 조직 전체의 콘텐츠 라이브러리에서 공유, 할당 및 학습할 수 있는 Teams의 중앙 허브를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="253c6-106">The app creates a central hub in Teams where employees can share, assign, and learn from content libraries across your organization.</span></span> <span data-ttu-id="253c6-107">관리자는 사용 권한을 설정하고 앱에 대한 학습 콘텐츠 원본을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="253c6-107">Admins set permissions and allow learning content sources for the app.</span></span> <span data-ttu-id="253c6-108">학습 콘텐츠에는 LinkedIn Learning, Microsoft Learn, Microsoft 365 교육, SharePoint Online에 저장된 조직의 자체 콘텐츠 및 앱에서 지원하는 타사 공급자가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="253c6-108">Learning content can include LinkedIn Learning, Microsoft Learn, Microsoft 365 training, your organization's own content stored in SharePoint online, and third-party providers that are supported by the app.</span></span>

<span data-ttu-id="253c6-109">Teams Learning 앱(비공개 미리 보기)을 설정하려면 다음을 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="253c6-109">To set up the Teams Learning app (private preview), you'll need to involve:</span></span>

-   <span data-ttu-id="253c6-110">Teams 관리 센터 관리자</span><span class="sxs-lookup"><span data-stu-id="253c6-110">Teams admin center admin</span></span>
-   <span data-ttu-id="253c6-111">Microsoft 365 관리 센터 관리자(즉, 전역 관리자)</span><span class="sxs-lookup"><span data-stu-id="253c6-111">Microsoft 365 admin center admin (that is, a global admin)</span></span>
-   <span data-ttu-id="253c6-112">기술 관리자(IT 관리자 또는 Microsoft 365 관리자라고도 하는 전역 관리자)가 조직의 모든 사용자에게 할당할 수 있는 Microsoft 365 관리 센터의 새 역할입니다.</span><span class="sxs-lookup"><span data-stu-id="253c6-112">Knowledge admin (a new role in the Microsoft 365 admin center that a global admin (also known as IT admin or Microsoft 365 admin) can assign to anyone in the organization.</span></span> <span data-ttu-id="253c6-113">이 역할은 Microsoft 365 관리 센터를 통해 조직의 학습 콘텐츠 원본을 관리합니다.)</span><span class="sxs-lookup"><span data-stu-id="253c6-113">This role manages the organization’s learning content sources through the Microsoft 365 admin center.)</span></span> 

## <a name="manage-the-teams-learning-app-private-preview-in-the-teams-admin-center"></a><span data-ttu-id="253c6-114">Teams 관리 센터에서 Teams 학습 앱(비공개 미리 보기) 관리</span><span class="sxs-lookup"><span data-stu-id="253c6-114">Manage the Teams Learning app (private preview) in the Teams admin center</span></span>

<span data-ttu-id="253c6-115">Teams 관리자는 앱 스토어에서 Teams 학습 앱(비공개 미리 보기)을 설치하고 Teams 관리 센터를 통해 앱 설정, 관리 및 사용 권한 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="253c6-115">The Teams admin installs the Teams Learning app (private preview) from the app store and applies app setup, manage, and permissions policies through the Teams admin center.</span></span>

### <a name="manage-the-teams-learning-app-private-preview"></a><span data-ttu-id="253c6-116">Teams 학습 앱 관리(비공개 미리 보기)</span><span class="sxs-lookup"><span data-stu-id="253c6-116">Manage the Teams Learning app (private preview)</span></span>

<span data-ttu-id="253c6-117">앱에 대한 설정을 관리하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="253c6-117">To manage settings for app, follow these steps:</span></span>

1. <span data-ttu-id="253c6-118">Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 **Teams 앱 관리**  >  **앱으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="253c6-118">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>

   ![Teams 앱 및 앱 관리 섹션을 보여주는 Teams 관리 센터의 왼쪽 탐색](media/learning-app-teams-manage-apps-nav.png)

2. <span data-ttu-id="253c6-120">앱 관리 **페이지의** 검색 상자에 Teams *학습* 앱(비공개 미리 보기)을 검색하는 학습을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="253c6-120">On the **Manage apps** page, in the search box, type *learning* to search for the Teams Learning app (private preview).</span></span>

   ![검색 상자를 표시하는 Teams 관리 센터의 앱 관리 페이지](media/learning-app-teams-manage-apps-page.png)

3. <span data-ttu-id="253c6-122">학습 **페이지에서:**</span><span class="sxs-lookup"><span data-stu-id="253c6-122">On the **Learning** page:</span></span>
   1. <span data-ttu-id="253c6-123">상태 **아래에서** **앱 켜기** 허용을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="253c6-123">Under **Status**, select **Allowed** to turn on the app.</span></span>
   2. <span data-ttu-id="253c6-124">설정 **탭의** 앱  설정 섹션에서 Microsoft 365 관리 센터로 이동하여 학습 콘텐츠 원본을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="253c6-124">On the **Settings** tab, in the **App settings** section, go to the Microsoft 365 admin center to configure learning content sources.</span></span>

   ![상태 및 앱 설정 섹션을 표시하는 Teams 관리 센터의 학습 페이지](media/learning-app-teams-learning-page.png)

4. <span data-ttu-id="253c6-126">앱 **설정을 관리한**  후 사용 권한 및 설정 정책으로 이동하여 비공개 미리 보기에 참여하는 조직의 일부로 앱에 액세스할 수 있는 직원에게 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="253c6-126">After **Manage app** settings, go to **Permissions and Set-up policies** to grant permission to employees who should have access to the app as part of your organization's participation in the private preview.</span></span>

> [!NOTE]
>  <span data-ttu-id="253c6-127">조직이 Teams TAP100 프로그램의 일부로 링 4.0에 있는 경우 링 3.0에서 승인된 사용자가 Teams 학습 앱(비공개 미리 보기)에 액세스할 수 있도록 다음을 실행해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="253c6-127">If your organization is in Ring 4.0 as part of Teams TAP100 program, you might need to do the following to enable approved users in Ring 3.0 to access the Teams Learning app (private preview).</span></span>

<span data-ttu-id="253c6-128">비공개 미리 보기의 일부로 Teams 학습 앱(비공개 미리 보기)은 링 3.0에서 릴리스됩니다.</span><span class="sxs-lookup"><span data-stu-id="253c6-128">As part of private preview, the Teams Learning app (private preview) is released in Ring 3.0.</span></span> <span data-ttu-id="253c6-129">조직이 링 4.0에 있는 경우 앱 스토어에 앱이 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="253c6-129">If your organization is in Ring 4.0, you won’t see the app in the app store.</span></span> <span data-ttu-id="253c6-130">앱을 테스트하려면 사용자 지정 앱 사용 권한 정책을 만들고, 모든 앱을 허용하도록 **설정하고,** 링 3.0 승인된 사용자에게 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="253c6-130">To test the app, you need to create a custom apps permission policy, set it to **Allow all apps**, and assign it to Ring 3.0 approved users.</span></span>

   ![모든 앱 허용이 선택된 TAP-AppsPermission-Plcy 페이지](media/learning-app-tap-appspermission-plcy.png)

## <a name="configure-learning-content-sources-in-the-microsoft-365-admin-center"></a><span data-ttu-id="253c6-132">Microsoft 365 관리 센터에서 학습 콘텐츠 원본 구성</span><span class="sxs-lookup"><span data-stu-id="253c6-132">Configure learning content sources in the Microsoft 365 admin center</span></span>

<span data-ttu-id="253c6-133">Microsoft 365 관리 센터의 관리자는 직접 또는 조직에서 선택한 개인에게 기술 관리자 역할을 할당하여 Teams 학습 앱(비공개 미리 보기)과 관련된 설정을 관리하고 학습 콘텐츠 원본을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="253c6-133">The admins for the Microsoft 365 admin center—either by themselves or by assigning the Knowledge admin role to selected individuals in your organization—can manage settings related to the Teams Learning app (private preview) and can configure the learning content sources.</span></span>

> [!TIP]
> <span data-ttu-id="253c6-134">기술 관리자는 보통 기술자 및 기존 SharePoint 관리자 자격 증명을 가급적이면 조직의 교육, 학습, 교육 또는 직원 경험에 잘 알고 있는 사람입니다.</span><span class="sxs-lookup"><span data-stu-id="253c6-134">The Knowledge admin should be moderately technical and have existing SharePoint admin credentials, preferably someone who is well-versed in the education, learning, training, or employee experience part of the organization.</span></span>
 
<span data-ttu-id="253c6-135">관리자는 앱에서 사용할 수 있는 학습 콘텐츠 원본(예: LinkedIn Learning 또는 SharePoint)을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="253c6-135">The admin selects which learning content sources (such as LinkedIn Learning or SharePoint) will be available in the app.</span></span> <span data-ttu-id="253c6-136">그런 다음 관리자는 콘텐츠를 검색 및 검색에 사용할 수 있으며 앱을 사용하는 직원이 검색할 수 있도록 해당 원본을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="253c6-136">The admin then configures those sources to make sure the content is available for search and discovery and can be browsed by the employees who use the app.</span></span>

### <a name="assign-the-knowledge-admin-role-optional"></a><span data-ttu-id="253c6-137">기술 관리자 역할 할당 [선택 사항]</span><span class="sxs-lookup"><span data-stu-id="253c6-137">Assign the Knowledge admin role [Optional]</span></span>

<span data-ttu-id="253c6-138">이러한 단계는 Microsoft 365 관리 센터의 관리자가 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="253c6-138">These steps are to be performed by the admin for the Microsoft 365 admin center.</span></span>

1.  <span data-ttu-id="253c6-139">Microsoft 365 관리 센터의 왼쪽 탐색 모음에서 **역할로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="253c6-139">In the left navigation of the Microsoft 365 admin center, go to **Roles**.</span></span>

2.  <span data-ttu-id="253c6-140">역할 **페이지의** **Azure AD** 탭에서 기술 **관리자를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="253c6-140">On the **Roles** page, on the **Azure AD** tab, select **Knowledge admin**.</span></span>
 
3.  <span data-ttu-id="253c6-141">기술 관리 **페이지의** 할당된  관리자 섹션에서 추가를 선택한 다음 역할에 대해 선택한 사람을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="253c6-141">On the **Knowledge admin** page, in the **Assigned Admins** section, select **Add**, and then add the person you choose for the role.</span></span>

### <a name="configure-settings-for-the-learning-content-sources-for-the-app"></a><span data-ttu-id="253c6-142">앱에 대한 학습 콘텐츠 원본에 대한 설정 구성</span><span class="sxs-lookup"><span data-stu-id="253c6-142">Configure settings for the learning content sources for the app</span></span>

<span data-ttu-id="253c6-143">이러한 단계는 Microsoft 365 관리자 또는 기술 관리자가 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="253c6-143">These steps are to be performed by the Microsoft 365 admin or the Knowledge admin.</span></span>

1.  <span data-ttu-id="253c6-144">Microsoft 365 관리 센터의 왼쪽 탐색 모음에서 설정  >  **구성 설정으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="253c6-144">In the left navigation of the Microsoft 365 admin center, go to **Settings** > **Org settings**.</span></span>

2.  <span data-ttu-id="253c6-145">설정 **페이지의** 서비스 & **추가 기능** 탭에서 학습 앱을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="253c6-145">On the **Settings** page, on the **Services & add-ins** tab, select **Learning app**.</span></span>

   ![나열된 학습 앱을 표시하는 Microsoft 365 관리 센터의 설정 페이지](media/learning-app-365-settings-page.png)

3.  <span data-ttu-id="253c6-147">학습 앱 **패널에서** 조직에 대해 구성하려는 학습 콘텐츠 원본을 선택한 다음 저장을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="253c6-147">On the **Learning app** panel, select the learning content sources you want to configure for the organization, and then select **Save**.</span></span>

   ![콘텐츠 원본 옵션을 표시하는 Microsoft 365 관리 센터의 학습 앱 패널](media/learning-app-365-settings-learning-app-panel.png)

<span data-ttu-id="253c6-149">존재하는 모든 학습 원본 중 일부는 기본적으로 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="253c6-149">Among all the learning sources that exist, some will be enabled by default.</span></span> <span data-ttu-id="253c6-150">여기에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="253c6-150">These include:</span></span>

- <span data-ttu-id="253c6-151">LinkedIn Learning(무료 콘텐츠)</span><span class="sxs-lookup"><span data-stu-id="253c6-151">LinkedIn Learning (free content)</span></span>
- <span data-ttu-id="253c6-152">Microsoft Learn</span><span class="sxs-lookup"><span data-stu-id="253c6-152">Microsoft Learn</span></span>
- <span data-ttu-id="253c6-153">Microsoft 365 교육</span><span class="sxs-lookup"><span data-stu-id="253c6-153">Microsoft 365 Training</span></span>

> [!NOTE]
> <span data-ttu-id="253c6-154">조직에 LinkedIn Learning 표준 또는 Pro 구독이 있는 경우 조직의 직원에 대한 콘텐츠 리포지토리가 잠금 해제됩니다.</span><span class="sxs-lookup"><span data-stu-id="253c6-154">If your organization has a LinkedIn Learning Standard or Pro subscription, the content repository will be unlocked for the employees in your organization.</span></span> <span data-ttu-id="253c6-155">권한이 있는 직원만 전체 콘텐츠 리포지토리를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="253c6-155">Only those employees who have permission will be able to use the entire content repository.</span></span>

<span data-ttu-id="253c6-156">다른 원본을 사용하도록 설정하거나 수동으로 구성해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="253c6-156">Other sources might need to be enabled or configured manually.</span></span> <span data-ttu-id="253c6-157">Microsoft가 아닌 학습 원본은 조직과 타사 간에 별도로 사용이 허가됩니다.</span><span class="sxs-lookup"><span data-stu-id="253c6-157">Learning sources that are not from Microsoft are separately licensed between your organization and the third party.</span></span> <span data-ttu-id="253c6-158">사용자 및 사용자를 위해 학습에 등록한지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="253c6-158">You’ll need to verify you’ve signed up for their learning for you and your users.</span></span>

<span data-ttu-id="253c6-159">학습 콘텐츠 원본을 사용 또는 사용하지 않도록 설정하려면 원본 옆에 있는 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="253c6-159">To enable or disable a learning content source, select the check box next to the source.</span></span> <span data-ttu-id="253c6-160">원본을 사용하도록 설정하면 확인 표시가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="253c6-160">If a source is enabled, a check mark will be visible.</span></span>

## <a name="configure-sharepoint-as-a-learning-content-source"></a><span data-ttu-id="253c6-161">SharePoint를 학습 콘텐츠 원본으로 구성</span><span class="sxs-lookup"><span data-stu-id="253c6-161">Configure SharePoint as a learning content source</span></span>

<span data-ttu-id="253c6-162">Microsoft 365 관리 센터에서 Teams Learning 앱(비공개 미리 보기)에 대한 학습 콘텐츠 원본으로 SharePoint를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="253c6-162">You configure SharePoint as a learning content source for the Teams Learning app (private preview) in the Microsoft 365 admin center.</span></span>

### <a name="overview"></a><span data-ttu-id="253c6-163">개요</span><span class="sxs-lookup"><span data-stu-id="253c6-163">Overview</span></span>

<span data-ttu-id="253c6-164">기술 관리자는 학습 서비스가 구조화된 SharePoint 목록 형태로 빈 중앙 집중식 학습 콘텐츠 리포지토리를 만들 수 있는 사이트 URL을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="253c6-164">The Knowledge admin provides a site URL to where the Learning Service can create an empty centralized learning content repository in the form of a structured SharePoint list.</span></span> <span data-ttu-id="253c6-165">이 목록은 조직에서 학습 콘텐츠를 포함하는 회사 간 SharePoint 폴더에 대한 링크를 저장하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="253c6-165">This list can be used by the organization to house links to cross-company SharePoint folders that contain learning content.</span></span> <span data-ttu-id="253c6-166">관리자는 폴더에 대한 URL 목록을 수집하고 큐링할 책임이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="253c6-166">Admins are responsible for collecting and curating a list of URLs for folders.</span></span> <span data-ttu-id="253c6-167">이러한 폴더에는 Teams 학습 앱(비공개 미리 보기)에서 사용할 수 있는 콘텐츠만 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="253c6-167">These folders should only include content that can be made available in the Teams Learning app (private preview).</span></span>

### <a name="permissions"></a><span data-ttu-id="253c6-168">사용 권한</span><span class="sxs-lookup"><span data-stu-id="253c6-168">Permissions</span></span>

<span data-ttu-id="253c6-169">폴더 URL은 조직의 모든 SharePoint 사이트에서 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="253c6-169">Folder URLs can be collected from any SharePoint site in the organization.</span></span> <span data-ttu-id="253c6-170">이러한 폴더 내의 모든 콘텐츠는 검색할 수 있지만 개별 직원에게 사용 권한이 있는 콘텐츠만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="253c6-170">Any content within these folders will be searchable, but only content to which the individual employee has permissions can be used.</span></span>
 
### <a name="learning-service"></a><span data-ttu-id="253c6-171">학습 서비스</span><span class="sxs-lookup"><span data-stu-id="253c6-171">Learning Service</span></span>

<span data-ttu-id="253c6-172">Learning Service는 제공된 폴더 URL을 사용하여 해당 폴더에 저장된 모든 콘텐츠에서 메타데이터를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="253c6-172">The Learning Service uses the provided folder URLs to get metadata from all content stored in those folders.</span></span> <span data-ttu-id="253c6-173">직원은 중앙 집중식 리포지토리에 폴더 URL을 제공한 후 24시간 이내에 앱 내에서 회사의 콘텐츠를 검색하고 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="253c6-173">Within 24 hours of supplying the folder URL in the centralized repository, employees can search for and use the company’s content within the app.</span></span> <span data-ttu-id="253c6-174">리포지토리의 콘텐츠 삭제는 현재 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="253c6-174">Content deletion from the repository isn't supported at this point.</span></span> <span data-ttu-id="253c6-175">의도치 않은 콘텐츠는 Microsoft 365 관리 센터에서 새 SharePoint 사이트 URL을 제공해야만 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="253c6-175">Unintentionally surfaced content can only be removed by supplying a new SharePoint site URL in the Microsoft 365 admin center.</span></span>

### <a name="configure-sharepoint-as-a-source"></a><span data-ttu-id="253c6-176">SharePoint를 원본으로 구성</span><span class="sxs-lookup"><span data-stu-id="253c6-176">Configure SharePoint as a source</span></span>

<span data-ttu-id="253c6-177">이러한 단계는 Microsoft 365 관리자 또는 기술 관리자가 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="253c6-177">These steps are to be performed by Microsoft 365 admin or the Knowledge admin.</span></span>

1.  <span data-ttu-id="253c6-178">Microsoft 365 관리 센터의 왼쪽 탐색 모음에서 설정으로 **이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="253c6-178">In the left navigation of the Microsoft 365 admin center, go to **Settings**.</span></span>
 
2.  <span data-ttu-id="253c6-179">설정 **페이지의** 서비스 & **추가 기능** 탭에서 학습 앱을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="253c6-179">On the **Settings** page, on the **Services & add-ins** tab, select **Learning app**.</span></span>

   ![나열된 학습 앱을 표시하는 Microsoft 365 관리 센터의 설정 페이지](media/learning-app-365-settings-page.png)

3.  <span data-ttu-id="253c6-181">학습 앱 **패널에서** 앱이 중앙 집중식 리포지토리를 만들 SharePoint 사이트에 사이트 URL을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="253c6-181">On the **Learning app** panel, provide the site URL to the SharePoint site where you want the app to create a centralized repository.</span></span>

   ![선택한 SharePoint를 표시하는 Microsoft 365 관리 센터의 학습 앱 패널](media/learning-app-365-panel-sharepoint-selected.png)

4.  <span data-ttu-id="253c6-183">SharePoint 목록은 제공된 조직의 SharePoint 사이트 내에서 자동으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="253c6-183">A SharePoint list is created automatically within the provided organization’s SharePoint site.</span></span> <span data-ttu-id="253c6-184">SharePoint 사이트의 왼쪽 탐색에서 앱 콘텐츠 리포지토리 **학습을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="253c6-184">In the left navigation of the SharePoint site, select **Learning App Content Repository**.</span></span> 

   ![학습 앱 콘텐츠 리포지토리 섹션을 보여주는 SharePoint의 왼쪽 탐색](media/learning-app-content-repository-nav.png)

 
5. <span data-ttu-id="253c6-186">학습 앱 **콘텐츠** 리포지토리 페이지에서 학습 콘텐츠 폴더에 대한 URL로 SharePoint 목록을 채우습니다.</span><span class="sxs-lookup"><span data-stu-id="253c6-186">On the **Learning App Content Repository** page, populate the SharePoint list with URLs to the learning content folders.</span></span>

   1.   <span data-ttu-id="253c6-187">새로 **보기를** 선택하여 새 항목 **패널을** 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="253c6-187">Select **New** to view the **New item** panel.</span></span> 

   ![새 옵션을 표시하는 SharePoint의 앱 콘텐츠 리포지토리 학습 페이지](media/learning-app-content-repository-new.png)
 
   2.   <span data-ttu-id="253c6-189">새 항목 **패널의** **제목** 필드에서 원하는 디렉터리 이름을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="253c6-189">On the **New item** panel, in the **Title** field, add a directory name of your choice.</span></span> <span data-ttu-id="253c6-190">폴더 **URL 필드에서** 학습 콘텐츠 폴더에 URL을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="253c6-190">In the **Folder URL** field, add the URL to the learning content folder.</span></span> <span data-ttu-id="253c6-191">저장을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="253c6-191">Select **Save**.</span></span>

   ![제목 및 폴더 URL 필드를 표시하는 SharePoint의 새 항목 패널](media/learning-app-new-item-panel.png)

   3. <span data-ttu-id="253c6-193">학습 앱 콘텐츠 리포지토리 페이지가 새 학습 콘텐츠로 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="253c6-193">The Learning App Content Repository page is updated with the new learning content.</span></span>

   ![업데이트된 정보를 표시하는 SharePoint의 앱 콘텐츠 리포지토리 학습 페이지](media/learning-app-content-repository-populated.png)


 


