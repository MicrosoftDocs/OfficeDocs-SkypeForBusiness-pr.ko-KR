---
title: Microsoft Viva Learning에 대한 사용 권한 설치, 관리 및 할당(비공개 미리 보기)
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
description: Microsoft Viva Learning(비공개 미리 보기)을 사용하여 직원이 조직 전체의 콘텐츠 라이브러리에서 공유, 할당 및 학습할 수 있는 학습을 위한 중앙 허브를 만들 수 있습니다.
f1.keywords: ''
appliesto:
- Microsoft Teams
ms.custom: ''
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 3b99cdcd49dc35a558d6217e28bf57bbb8563827
ms.sourcegitcommit: b56727299d7ea47e23807114a4f5881e289c0b6a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/17/2021
ms.locfileid: "51880382"
---
# <a name="install-manage-and-assign-permissions-for-microsoft-viva-learning-private-preview"></a><span data-ttu-id="e628d-103">Microsoft Viva Learning에 대한 사용 권한 설치, 관리 및 할당(비공개 미리 보기)</span><span class="sxs-lookup"><span data-stu-id="e628d-103">Install, manage, and assign permissions for Microsoft Viva Learning (private preview)</span></span>

<span data-ttu-id="e628d-104">*이 문서에는 비공개 미리 보기에 있는 Microsoft Viva Learning의 예비 콘텐츠가 포함되어 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="e628d-104">*This article contains preliminary content for Microsoft Viva Learning, which is in private preview.*</span></span>

<span data-ttu-id="e628d-105">Microsoft Viva Learning(비공개 미리 보기)은 조직의 팀 및 개인이 하루 중 자연스러운 학습을 할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-105">Microsoft Viva Learning (private preview) empowers teams and individuals in your organization to make learning a natural part of their day.</span></span> <span data-ttu-id="e628d-106">앱은 직원들이 조직 전체의 콘텐츠 라이브러리에서 공유, 할당 및 학습할 수 있는 Teams에 중앙 허브를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-106">The app creates a central hub in Teams where employees can share, assign, and learn from content libraries across your organization.</span></span>

<span data-ttu-id="e628d-107">관리자는 권한을 설정하고 Viva Learning(비공개 미리 보기)에 대한 학습 콘텐츠 원본을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-107">Admins set permissions and allow learning content sources for Viva Learning (private preview).</span></span> <span data-ttu-id="e628d-108">학습 콘텐츠에는 LinkedIn Learning, Microsoft Learn, Microsoft 365 교육, SharePoint Online에 저장된 조직의 자체 콘텐츠 및 Viva Learning에서 지원하는 타사 공급자(비공개 미리 보기)가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-108">Learning content can include LinkedIn Learning, Microsoft Learn, Microsoft 365 training, your organization's own content stored in SharePoint online, and third-party providers that are supported by Viva Learning (private preview).</span></span>

## <a name="admin-roles"></a><span data-ttu-id="e628d-109">관리자 역할</span><span class="sxs-lookup"><span data-stu-id="e628d-109">Admin roles</span></span>

<span data-ttu-id="e628d-110">Viva Learning(비공개 미리 보기)을 설정하려면 다음과 같은 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-110">To set up Viva Learning (private preview), you'll need permissions as:</span></span>

- <span data-ttu-id="e628d-111">Microsoft Teams 관리자</span><span class="sxs-lookup"><span data-stu-id="e628d-111">Microsoft Teams admin</span></span>
- <span data-ttu-id="e628d-112">Microsoft 365 전역 관리자 또는 SharePoint 관리자</span><span class="sxs-lookup"><span data-stu-id="e628d-112">Microsoft 365 global administrator or SharePoint administrator</span></span>
- <span data-ttu-id="e628d-113">기술 관리자 - 조직의 모든 사용자에게 할당할 수 있는 Microsoft 365 관리 센터의 새 역할입니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-113">Knowledge admin — This is a new role in the Microsoft 365 admin center that can be assigned to anyone in the organization.</span></span> <span data-ttu-id="e628d-114">이 역할은 Microsoft 365 관리 센터를 통해 조직의 학습 콘텐츠 원본을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-114">This role manages the organization’s learning content sources through the Microsoft 365 admin center.</span></span> 

> [!TIP]
> <span data-ttu-id="e628d-115">기술 관리자는 적당히 기술해야 합니다. 기존 SharePoint 관리자 자격 증명이 있는 것이 바람직하며, 조직의 교육, 학습, 교육 또는 직원 경험에 정교한 사람이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-115">The knowledge admin should be moderately technical and have existing SharePoint admin credentials, preferably someone who is well-versed in the education, learning, training, or employee experience part of the organization.</span></span>
 
## <a name="manage-viva-learning-private-preview-in-the-teams-admin-center"></a><span data-ttu-id="e628d-116">Teams 관리 센터에서 Viva Learning 관리(비공개 미리 보기)</span><span class="sxs-lookup"><span data-stu-id="e628d-116">Manage Viva Learning (private preview) in the Teams admin center</span></span>

<span data-ttu-id="e628d-117">Teams 관리자는 앱 스토어에서 Viva Learning(비공개 미리 보기)을 설치한 다음 Teams 관리 센터를 통해 설정, 관리 및 사용 권한 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-117">The Teams admin installs Viva Learning (private preview) from the app store, and then applies setup, manage, and permission policies through the Teams admin center.</span></span>

### <a name="manage-settings-for-viva-learning-private-preview"></a><span data-ttu-id="e628d-118">Viva Learning에 대한 설정 관리(비공개 미리 보기)</span><span class="sxs-lookup"><span data-stu-id="e628d-118">Manage settings for Viva Learning (private preview)</span></span>

<span data-ttu-id="e628d-119">이러한 작업을 수행하려면 Teams 관리 센터의 관리자가 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-119">You must be an administrator in the Teams admin center to perform these tasks.</span></span>

<span data-ttu-id="e628d-120">Viva Learning에 대한 설정을 관리하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-120">To manage settings for Viva Learning, follow these steps:</span></span>

1. <span data-ttu-id="e628d-121">Teams 관리 센터의 왼쪽 탐색에서 **Teams apps**  >  **관리 앱으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="e628d-121">In the left navigation of the Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>

   ![Teams 앱 및 앱 관리 섹션을 보여주는 Teams 관리 센터의 왼쪽 탐색](media/learning-app-teams-manage-apps-nav.png)

2. <span data-ttu-id="e628d-123">앱 **관리** 페이지에서 검색 상자에 Teams  Learning 앱(비공개 미리 보기)을 검색하는 학습을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-123">On the **Manage apps** page, in the search box, type *learning* to search for the Teams Learning app (private preview).</span></span>

   ![검색 상자를 보여주는 Teams 관리 센터의 앱 페이지 관리](media/learning-app-teams-manage-apps-page.png)

3. <span data-ttu-id="e628d-125">학습 **페이지에서:**</span><span class="sxs-lookup"><span data-stu-id="e628d-125">On the **Learning** page:</span></span>
   1. <span data-ttu-id="e628d-126">**상태에서** 앱을 **켜기** 허용을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-126">Under **Status**, select **Allowed** to turn on the app.</span></span>
   2. <span data-ttu-id="e628d-127">설정 **탭의** 앱  설정 섹션에서 Microsoft 365 관리 센터로 이동하여 학습 콘텐츠 원본을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-127">On the **Settings** tab, in the **App settings** section, go to the Microsoft 365 admin center to configure learning content sources.</span></span>

   ![상태 및 앱 설정 섹션을 보여주는 Teams 관리 센터의 학습 페이지](media/learning-app-teams-learning-page.png)

4. <span data-ttu-id="e628d-129">앱 **설정 관리** 후  권한 및 설정 정책으로 이동하여 조직의 비공개 미리 보기 참여의 일부로 앱에 액세스할 수 있는 직원에게 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-129">After **Manage app** settings, go to **Permissions and Set-up policies** to grant permission to employees who should have access to the app as part of your organization's participation in the private preview.</span></span>

> [!NOTE]
>  <span data-ttu-id="e628d-130">조직이 Teams TAP100 프로그램의 일부로 링 4.0에 있는 경우 링 3.0에서 승인된 사용자가 Viva Learning(비공개 미리 보기)에 액세스하도록 설정하려면 다음을 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-130">If your organization is in Ring 4.0 as part of Teams TAP100 program, you might need to do the following to enable approved users in Ring 3.0 to access Viva Learning (private preview).</span></span>

<span data-ttu-id="e628d-131">비공개 미리 보기의 일부로 Viva Learning(비공개 미리 보기)은 Ring 3.0에서 릴리스됩니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-131">As part of private preview, Viva Learning (private preview) is released in Ring 3.0.</span></span> <span data-ttu-id="e628d-132">조직이 Ring 4.0에 있는 경우 앱 스토어에 앱이 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-132">If your organization is in Ring 4.0, you won’t see the app in the app store.</span></span> <span data-ttu-id="e628d-133">앱을 테스트하려면 사용자 지정 앱 사용 권한 정책을 만들고, 모든 앱 허용으로 **설정하고,** 링 3.0 승인된 사용자에게 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-133">To test the app, you need to create a custom apps permission policy, set it to **Allow all apps**, and assign it to Ring 3.0 approved users.</span></span>

   ![TAP-AppsPermission-Plcy 페이지가 선택한 모든 앱 허용](media/learning-app-tap-appspermission-plcy.png)

## <a name="configure-learning-content-sources-in-the-microsoft-365-admin-center"></a><span data-ttu-id="e628d-135">Microsoft 365 관리 센터에서 학습 콘텐츠 원본 구성</span><span class="sxs-lookup"><span data-stu-id="e628d-135">Configure learning content sources in the Microsoft 365 admin center</span></span>

<span data-ttu-id="e628d-136">Microsoft 365 관리 센터의 관리자는 조직에서 선택한 개인에게 기술 관리자 역할을 할당하여 Viva Learning(비공개 미리 보기)과 관련된 설정을 관리할 수 있으며 학습 콘텐츠 원본을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-136">The administrators for the Microsoft 365 admin center—either by themselves or by assigning the knowledge admin role to selected individuals in your organization—can manage settings related to Viva Learning (private preview) and can configure the learning content sources.</span></span>

<span data-ttu-id="e628d-137">관리자는 Viva Learning(비공개 미리 보기)의 사용자가 사용할 수 있는 추가 학습 콘텐츠 원본(예: SharePoint 또는 지원되는 타사 콘텐츠 공급자 원본)을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-137">The administrator selects which additional learning content sources (for example, SharePoint or supported third-party content provider sources) will be available to users of Viva Learning (private preview).</span></span> <span data-ttu-id="e628d-138">그런 다음 관리자는 해당 원본을 구성하여 콘텐츠를 검색 및 검색에 사용할 수 있으며 Viva Learning(비공개 미리 보기)을 사용하는 직원이 검색할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-138">The admin then configures those sources to make sure the content is available for search and discovery and can be browsed by the employees who use Viva Learning (private preview).</span></span>

> [!NOTE]
>  <span data-ttu-id="e628d-139">사용자는 브라우저 또는 포함된 뷰어에서 비 Microsoft 및 LinkedIn Learning Pro 학습에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-139">Users sign in to non-Microsoft and LinkedIn Learning Pro learnings in a browser or embedded viewer.</span></span> <span data-ttu-id="e628d-140">이 구성된 학습은 Viva Learning(비공개 미리 보기) 용어가 아닌 조직과 타사 간에 별도의 라이선스, 개인 정보 및 서비스 약관의 적용을 하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-140">This configured learning is subject to the separate license, privacy and service terms between your organization and the third party, and not the Viva Learning (private preview) terms.</span></span> <span data-ttu-id="e628d-141">이러한 유형의 학습을 선택하기 전에 조직 및 사용자에 대한 계약이 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-141">Before selecting this type of learning, verify you have an agreement in place for your organization and users.</span></span>

### <a name="assign-the-knowledge-admin-role-optional"></a><span data-ttu-id="e628d-142">기술 관리자 역할 할당 [선택 사항]</span><span class="sxs-lookup"><span data-stu-id="e628d-142">Assign the knowledge admin role [Optional]</span></span>

<span data-ttu-id="e628d-143">이러한 작업을 수행하려면 Microsoft 365 전역 관리자가 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-143">You must be a Microsoft 365 global administrator to perform these tasks.</span></span>

<span data-ttu-id="e628d-144">Viva Learning에 대한 기술 관리자를 할당하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-144">To assign a knowledge admin for Viva Learning, follow these steps:</span></span>

1.  <span data-ttu-id="e628d-145">Microsoft 365 관리 센터의 왼쪽 탐색에서 **역할 으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="e628d-145">In the left navigation of the Microsoft 365 admin center, go to **Roles**.</span></span>

2.  <span data-ttu-id="e628d-146">역할 **페이지에서** **Azure AD** 탭에서 기술 **관리자를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e628d-146">On the **Roles** page, on the **Azure AD** tab, select **Knowledge admin**.</span></span>
 
3.  <span data-ttu-id="e628d-147">기술 관리자 **페이지에서** 할당된  관리자 섹션에서 **추가를** 선택한 다음 역할에 대해 선택한 사람을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-147">On the **Knowledge admin** page, in the **Assigned Admins** section, select **Add**, and then add the person you choose for the role.</span></span>

### <a name="configure-settings-for-the-learning-content-sources-for-viva-learning-private-preview"></a><span data-ttu-id="e628d-148">Viva Learning용 학습 콘텐츠 원본에 대한 설정 구성(비공개 미리 보기)</span><span class="sxs-lookup"><span data-stu-id="e628d-148">Configure settings for the learning content sources for Viva Learning (private preview)</span></span>

<span data-ttu-id="e628d-149">이러한 작업을 수행하려면 Microsoft 365 전역 관리자 또는 지식 관리자가 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-149">You must be a Microsoft 365 global administrator or knowledge admin to perform these tasks.</span></span>

<span data-ttu-id="e628d-150">Viva Learning에서 콘텐츠 원본 학습에 대한 설정을 구성하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-150">To configure settings for learning content sources in Viva Learning, follow these steps:</span></span>

1.  <span data-ttu-id="e628d-151">Microsoft 365 관리 센터의 왼쪽 탐색에서 설정  >  **Org 설정으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="e628d-151">In the left navigation of the Microsoft 365 admin center, go to **Settings** > **Org settings**.</span></span>

2.  <span data-ttu-id="e628d-152">Org **설정** 페이지에서 **서비스** 탭에서 학습 **앱(미리 보기)을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e628d-152">On the **Org settings** page, on the **Services** tab, select **Learning app (Preview)**.</span></span>

     ![나열된 학습 앱을 보여주는 Microsoft 365 관리 센터의 설정 페이지](media/learning-sharepoint-configure1.png)

3.  <span data-ttu-id="e628d-154">학습 **앱(미리 보기)** 패널에서 조직에 대해 구성할 학습 콘텐츠 원본을 선택한 다음 저장을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e628d-154">On the **Learning app (Preview)** panel, select the learning content sources you want to configure for the organization, and then select **Save**.</span></span>

     ![콘텐츠 원본 옵션을 보여주는 Microsoft 365 관리 센터의 학습 패널](media/learning-sharepoint-configure2.png)

<span data-ttu-id="e628d-156">존재하는 모든 학습 원본 중 일부는 기본적으로 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-156">Among all the learning sources that exist, some will be enabled by default.</span></span> <span data-ttu-id="e628d-157">여기에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-157">These include:</span></span>

- <span data-ttu-id="e628d-158">LinkedIn Learning(무료 콘텐츠)</span><span class="sxs-lookup"><span data-stu-id="e628d-158">LinkedIn Learning (free content)</span></span>
- <span data-ttu-id="e628d-159">Microsoft Learn</span><span class="sxs-lookup"><span data-stu-id="e628d-159">Microsoft Learn</span></span>
- <span data-ttu-id="e628d-160">Microsoft 365 교육</span><span class="sxs-lookup"><span data-stu-id="e628d-160">Microsoft 365 Training</span></span>

> [!NOTE]
> <span data-ttu-id="e628d-161">조직에 LinkedIn Learning 표준 또는 Pro 구독이 있는 경우 조직의 직원에 대한 콘텐츠 리포지토리가 잠금 해제됩니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-161">If your organization has a LinkedIn Learning Standard or Pro subscription, the content repository will be unlocked for the employees in your organization.</span></span> <span data-ttu-id="e628d-162">권한이 있는 직원만 전체 콘텐츠 리포지토리를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-162">Only those employees who have permission will be able to use the entire content repository.</span></span> <br><span data-ttu-id="e628d-163">다른 원본을 사용하도록 설정하거나 수동으로 구성해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-163">Other sources might need to be enabled or configured manually.</span></span> <span data-ttu-id="e628d-164">Microsoft가 아닌 학습 원본은 조직과 타사 간에 별도로 라이선스가 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-164">Learning sources that are not from Microsoft are separately licensed between your organization and the third party.</span></span> <span data-ttu-id="e628d-165">사용자 및 사용자에 대한 학습에 등록한지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-165">You’ll need to verify you’ve signed up for their learning for you and your users.</span></span>

<span data-ttu-id="e628d-166">학습 콘텐츠 원본을 사용하도록 설정하거나 사용하지 않도록 설정하려면 원본 옆에 있는 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-166">To enable or disable a learning content source, select the check box next to the source.</span></span> <span data-ttu-id="e628d-167">원본을 사용하도록 설정하면 확인 표시가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-167">If a source is enabled, a check mark will be visible.</span></span>

## <a name="configure-sharepoint-as-a-learning-content-source"></a><span data-ttu-id="e628d-168">SharePoint를 학습 콘텐츠 원본으로 구성</span><span class="sxs-lookup"><span data-stu-id="e628d-168">Configure SharePoint as a learning content source</span></span>

<span data-ttu-id="e628d-169">Viva Learning(비공개 미리 보기)에서 조직의 자체 콘텐츠를 사용할 수 있도록 SharePoint를 학습 콘텐츠 원본으로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-169">You can configure SharePoint as a learning content source to make your organization's own content available in Viva Learning (private preview).</span></span>

### <a name="overview"></a><span data-ttu-id="e628d-170">개요</span><span class="sxs-lookup"><span data-stu-id="e628d-170">Overview</span></span>

<span data-ttu-id="e628d-171">기술 관리자(또는 전역 관리자)는 학습 서비스가 구조화된 SharePoint 목록의 형태로 빈 중앙 집중식 위치인 학습 앱 콘텐츠 리포지토리를 만들 수 있는 사이트 URL을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-171">The knowledge admin (or global administrator) provides a site URL to where the Learning Service can create an empty centralized location—the Learning App Content Repository—in the form of a structured SharePoint list.</span></span> <span data-ttu-id="e628d-172">이 목록은 조직에서 학습 콘텐츠를 포함하는 회사 간 SharePoint 폴더에 대한 링크를 저장하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-172">This list can be used by your organization to house links to cross-company SharePoint folders that contain learning content.</span></span> <span data-ttu-id="e628d-173">관리자는 폴더에 대한 URL 목록을 수집하고 큐레이터할 책임이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-173">Admins are responsible for collecting and curating a list of URLs for folders.</span></span> <span data-ttu-id="e628d-174">이러한 폴더에는 Viva Learning(비공개 미리 보기)에서 사용할 수 있는 콘텐츠만 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-174">These folders should only include content that can be made available in Viva Learning (private preview).</span></span>

<span data-ttu-id="e628d-175">Viva Learning(비공개 미리 보기)은 다음 문서 형식을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-175">Viva Learning (private preview) supports the following document types:</span></span>

- <span data-ttu-id="e628d-176">Word, PowerPoint, Excel, PDF</span><span class="sxs-lookup"><span data-stu-id="e628d-176">Word, PowerPoint, Excel, PDF</span></span>
- <span data-ttu-id="e628d-177">오디오(.m4a)</span><span class="sxs-lookup"><span data-stu-id="e628d-177">Audio (.m4a)</span></span>
- <span data-ttu-id="e628d-178">비디오(.mov, .mp4, .avi)</span><span class="sxs-lookup"><span data-stu-id="e628d-178">Video (.mov, .mp4, .avi)</span></span>

<span data-ttu-id="e628d-179">자세한 내용은 [SharePoint Online 설명서 를 참조하세요.](https://docs.microsoft.com/sharepoint/introductionlink)</span><span class="sxs-lookup"><span data-stu-id="e628d-179">For more information, see the [SharePoint Online documentation](https://docs.microsoft.com/sharepoint/introductionlink).</span></span> 

### <a name="permissions"></a><span data-ttu-id="e628d-180">사용 권한</span><span class="sxs-lookup"><span data-stu-id="e628d-180">Permissions</span></span>

<span data-ttu-id="e628d-181">문서 라이브러리 폴더 URL은 조직의 SharePoint 사이트에서 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-181">Document library folder URLs can be collected from any SharePoint site in the organization.</span></span> <span data-ttu-id="e628d-182">Viva Learning(비공개 미리 보기)은 모든 기존 콘텐츠 권한을 따르고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-182">Viva Learning (private preview) follows all existing content permissions.</span></span> <span data-ttu-id="e628d-183">따라서 사용자가 액세스할 수 있는 권한이 있는 콘텐츠만 Viva Learning(비공개 미리 보기) 내에서 검색 가능하고 비자블입니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-183">Therefore, only content for which a user has permission to access is searchable and visable within Viva Learning (private preview).</span></span> <span data-ttu-id="e628d-184">이러한 폴더 내의 모든 콘텐츠는 검색할 수 있지만 개별 직원이 사용 권한이 있는 콘텐츠만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-184">Any content within these folders will be searchable, but only content to which the individual employee has permissions can be used.</span></span>

<span data-ttu-id="e628d-185">조직의 리포지토리에서 콘텐츠 삭제는 현재 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-185">Content deletion from your organization’s repository is not currently supported.</span></span>

<span data-ttu-id="e628d-186">의도하지 않은 표면 콘텐츠를 제거하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-186">To remove unintentionally surfaced content, follow these steps:</span></span>

1.  <span data-ttu-id="e628d-187">문서 라이브러리의 액세스를 제한하려면  작업 표시 옵션을 선택한 다음, 액세스 **관리 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e628d-187">To restrict access on the document library, select the **Show actions** option, and then select **Manage access**.</span></span>
     
     ![Access 관리가 높게 설정되어 있는 작업 표시 옵션을 보여주는 SharePoint의 문서 라이브러리 페이지입니다.](media/learning-sharepoint-permissions2.png)

2.  <span data-ttu-id="e628d-189">문서 라이브러리 내에서 원본 문서를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-189">Delete the original document within the document library.</span></span>

<span data-ttu-id="e628d-190">자세한 내용은 SharePoint 최신 환경의 공유 및 사용 권한을 [참조하세요.](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions)</span><span class="sxs-lookup"><span data-stu-id="e628d-190">For more information, see [Sharing and permissions in the SharePoint modern experience](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions).</span></span> 

### <a name="learning-service"></a><span data-ttu-id="e628d-191">학습 서비스</span><span class="sxs-lookup"><span data-stu-id="e628d-191">Learning Service</span></span>

<span data-ttu-id="e628d-192">Learning Service는 제공된 폴더 URL을 사용하여 해당 폴더에 저장된 모든 콘텐츠에서 메타데이터를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-192">The Learning Service uses the provided folder URLs to get metadata from all content stored in those folders.</span></span> <span data-ttu-id="e628d-193">중앙 집중식 리포지토리에 폴더 URL을 제공한 후 24시간 이내에 직원들은 Viva Learning(비공개 미리 보기) 내에서 조직의 콘텐츠를 검색하고 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-193">Within 24 hours of supplying the folder URL in the centralized repository, employees can search for and use your organization’s content within Viva Learning (private preview).</span></span> <span data-ttu-id="e628d-194">업데이트된 메타데이터 및 사용 권한을 포함하여 콘텐츠에 대한 모든 변경 내용은 24시간 이내에 Learning Service에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-194">All changes to content, including updated metadata and permissions, will also be applied in the Learning Service within 24 hours.</span></span>

### <a name="configure-sharepoint-as-a-source"></a><span data-ttu-id="e628d-195">SharePoint를 원본으로 구성</span><span class="sxs-lookup"><span data-stu-id="e628d-195">Configure SharePoint as a source</span></span>

<span data-ttu-id="e628d-196">이러한 작업을 수행하려면 Microsoft 365 전역 관리자, SharePoint 관리자 또는 기술 관리자가 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-196">You must be a Microsoft 365 global administrator, SharePoint administrator, or knowledge admin to perform these tasks.</span></span>

<span data-ttu-id="e628d-197">Viva Learning(비공개 미리 보기)에서 SharePoint를 학습 콘텐츠 원본으로 구성하기 위해 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-197">To configure SharePoint as a learning content sources in for Viva Learning (private preview), follow these steps:</span></span>

1.  <span data-ttu-id="e628d-198">Microsoft 365 관리 센터의 왼쪽 탐색에서 설정  >  **Org 설정으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="e628d-198">In the left navigation of the Microsoft 365 admin center, go to **Settings** > **Org settings**.</span></span>
 
2.  <span data-ttu-id="e628d-199">Org **설정** 페이지에서 **서비스** 탭에서 학습 **앱(미리 보기)을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e628d-199">On the **Org settings** page, on the **Services** tab, select **Learning app (Preview)**.</span></span>

     ![나열된 Viva Learning을 보여주는 Microsoft 365 관리 센터의 설정 페이지입니다.](media/learning-sharepoint-configure1.png)

3.  <span data-ttu-id="e628d-201">학습 **앱(미리 보기)** 패널의 **SharePoint에서** Viva Learning이 중앙 집중식 리포지토리를 만들 수 있는 SharePoint 사이트에 사이트 URL을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-201">On the **Learning app (Preview)** panel, under **SharePoint**, provide the site URL to the SharePoint site where you want Viva Learning to create a centralized repository.</span></span>

     ![SharePoint가 선택한 Microsoft 365 관리 센터의 학습 패널입니다.](media/learning-sharepoint-configure2.png)

4.  <span data-ttu-id="e628d-203">SharePoint 목록은 제공된 SharePoint 사이트 내에서 자동으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-203">A SharePoint list is created automatically within the provided SharePoint site.</span></span>

     ![SharePoint 사이트 내에서 새로 만든 SharePoint 목록입니다.](media/learning-sharepoint-configure3.png)

     <span data-ttu-id="e628d-205">SharePoint 사이트의 왼쪽 탐색에서 **사이트 콘텐츠** 학습 앱 콘텐츠 리포지토리  >  **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e628d-205">In the left navigation of the SharePoint site, select **Site contents** > **Learning App Content Repository**.</span></span> 

     ![사이트 콘텐츠 탐색 및 학습 앱 콘텐츠 리포지토리 섹션을 보여주는 SharePoint 목록입니다.](media/learning-sharepoint-configure4.png) 

5. <span data-ttu-id="e628d-207">학습 앱 콘텐츠 리포지토리 **페이지에서** SharePoint 목록을 학습 콘텐츠 폴더에 URL로 채우습니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-207">On the **Learning App Content Repository** page, populate the SharePoint list with URLs to the learning content folders.</span></span>

   1. <span data-ttu-id="e628d-208">새로 **고를** 선택하여 새 항목 **패널을** 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-208">Select **New** to view the **New item** panel.</span></span> 

       ![새 옵션을 보여주는 SharePoint의 콘텐츠 리포지토리 학습 페이지.](media/learning-sharepoint-configure5.png)
 
   2. <span data-ttu-id="e628d-210">새 항목 **패널의** **제목** 필드에서 원하는 디렉터리 이름을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-210">On the **New item** panel, in the **Title** field, add a directory name of your choice.</span></span> <span data-ttu-id="e628d-211">폴더 **URL 필드에서** 학습 콘텐츠 폴더에 URL을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-211">In the **Folder URL** field, add the URL to the learning content folder.</span></span> <span data-ttu-id="e628d-212">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-212">Select **Save**.</span></span>

       ![제목 및 폴더 URL 필드를 보여주는 SharePoint의 새 항목 패널입니다.](media/learning-sharepoint-configure6.png)

   3. <span data-ttu-id="e628d-214">학습 **앱 콘텐츠 리포지토리 페이지는** 새 학습 콘텐츠로 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-214">The **Learning App Content Repository** page is updated with the new learning content.</span></span>

       ![업데이트된 정보를 보여주는 SharePoint의 콘텐츠 리포지토리 학습 페이지.](media/learning-sharepoint-configure7.png)

> [!NOTE]
> <span data-ttu-id="e628d-216">학습 앱 콘텐츠 리포지토리에 대한 광범위한 액세스를 허용하기 위해 사용자가 액세스를 요청하고 궁극적으로 목록을 채우는 데 도움이 되는 Viva Learning(비공개 미리 보기) 인터페이스에서 목록에 대한 링크를 곧 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-216">To allow for broader access to the Learning App Content Repository, a link to the list soon will be available in the Viva Learning (private preview) interface where users can request access and ultimately help populate the list.</span></span> <span data-ttu-id="e628d-217">사이트 소유자 및 전역 관리자는 목록에 대한 액세스 권한을 부여해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-217">Site owners and global administrators will be required to grant access to the list.</span></span> <span data-ttu-id="e628d-218">액세스는 목록에만 해당하며 목록이 저장되는 사이트에는 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-218">Access is specific to the list only and does not apply to the site where the list is stored.</span></span>

### <a name="folder-url-document-library-curation"></a><span data-ttu-id="e628d-219">폴더 URL 문서 라이브러리 큐레이터</span><span class="sxs-lookup"><span data-stu-id="e628d-219">Folder URL document library curation</span></span>

<span data-ttu-id="e628d-220">기본 메타데이터(예: 수정된 날짜, 문서 이름, 콘텐츠 유형 및 조직 이름)는 Microsoft Graph API에서 Viva Learning(비공개 미리 보기)으로 자동으로 끌어오게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-220">Default metadata (such as modified date, created by, document name, content type, and organization name) is automatically pulled into Viva Learning (private preview) by the Microsoft Graph API.</span></span>
 
<span data-ttu-id="e628d-221">콘텐츠의 전체 검색 및 검색 관련성을 개선하기 위해 설명 열을 **추가하는 것이** 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-221">To improve overall discovery and search relevance of the content, we recommend adding a **Description** column.</span></span>

<span data-ttu-id="e628d-222">문서 라이브러리 페이지에 **설명** 열을 추가하는 경우 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-222">To add a **Description** column to the document library page, follow these steps:</span></span>

1.  <span data-ttu-id="e628d-223">문서 **페이지에서** 열 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e628d-223">On the **Documents** page, select **Add column**.</span></span>

2. <span data-ttu-id="e628d-224">작업 표시 **옵션을** 선택한 다음 한 줄의 **텍스트 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e628d-224">Select the **Show actions** option, and then select **Single line of text**.</span></span>

     ![텍스트 줄이 강조 표시된 작업 표시 옵션을 보여주는 SharePoint의 문서 페이지입니다.](media/learning-sharepoint-curation1.png)

3. <span data-ttu-id="e628d-226">열 만들기 **패널의** **이름** 필드에 열에 대한 설명 이름을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-226">On the **Create a column** panel, in the **Name** field, add a descriptive name for the column.</span></span> <span data-ttu-id="e628d-227">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-227">Select **Save**.</span></span>

     ![이름 및 기타 필드를 보여 주어 SharePoint에서 열 패널을 생성합니다.](media/learning-sharepoint-curation2.png)
 
4. <span data-ttu-id="e628d-229">문서 **페이지의** 설명 열에서  각 항목에 대한 사용자 지정 설명을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-229">On the **Documents** page, in the **Description** column, add custom descriptions for each item.</span></span> <span data-ttu-id="e628d-230">설명이 제공되지 않습니다. Viva Learning(비공개 미리 보기)은 콘텐츠를 자신의 SharePoint 라이브러리에서 제공한 것으로 강조 표시하는 기본 메시지를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e628d-230">If no description is supplied, Viva Learning (private preview) will provide a default message that highlights the content as being from your own SharePoint library.</span></span> 

     ![설명 열에 설명을 표시하는 SharePoint의 문서 페이지입니다.](media/learning-sharepoint-curation3.png)
 
