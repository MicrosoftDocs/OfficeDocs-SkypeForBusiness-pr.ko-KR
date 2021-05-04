---
title: 경력 코치를 구매, 구성 및 Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: alaina.creager
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 경력 코치를 구매, 구성 및 사용하도록 설정하는 방법을 Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9911f880ba817afff10acb2a347a5c8c776d059c
ms.sourcegitcommit: 49cdcf344c63c805bcb6365804c6f5d1393e926a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2021
ms.locfileid: "52130088"
---
# <a name="purchase-configure-and-enable-career-coach-for-microsoft-teams"></a><span data-ttu-id="6c93f-103">경력 코치를 구매, 구성 및 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6c93f-103">Purchase, configure, and enable Career Coach for Microsoft Teams</span></span>

<span data-ttu-id="6c93f-104">커리어 코치는 Microsoft Teams 진로를 탐색할 수 있도록 고등 교육 학생들이 개인 설정된 지침을 제공하는 LinkedIn에서 제공하는 교육용 앱입니다.</span><span class="sxs-lookup"><span data-stu-id="6c93f-104">Career Coach is a Microsoft Teams for Education app powered by LinkedIn that provides personalized guidance for higher education students to navigate their career journey.</span></span> <span data-ttu-id="6c93f-105">Career Coach는 학생들이 자신의 진로를 검색하고, 실제 기술을 성장하고, 네트워크를 한 자리에 구축할 수 있도록 교육 기관에 통합된 커리어 솔루션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6c93f-105">Career Coach offers educational institutions a unified career solution for students to discover their career path, grow real-world skills, and build their network all in one place.</span></span>

<span data-ttu-id="6c93f-106">커리어 [코치에 대해 자세히 알아보자.](https://aka.ms/career-coach)</span><span class="sxs-lookup"><span data-stu-id="6c93f-106">Learn more about [Career Coach](https://aka.ms/career-coach).</span></span>

> [!NOTE]
> <span data-ttu-id="6c93f-107">이 가이드의 모범 사례 및 유용한 팁을 사용하여 학생, 교직원 및 교직원을 위한 커리어 코치의 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c93f-107">Use the best practices and helpful tips in this guide to enable the capabilities of Career Coach for students, faculty, and staff.</span></span> <span data-ttu-id="6c93f-108">빠른 계획 [가이드 문서를 참조하세요.](https://support.microsoft.com/office/c5d0b934-bfcf-4fe7-8a85-ba7bbb1b6ad4)</span><span class="sxs-lookup"><span data-stu-id="6c93f-108">See the [Quick planning guide](https://support.microsoft.com/office/c5d0b934-bfcf-4fe7-8a85-ba7bbb1b6ad4) article.</span></span>

## <a name="review-the-requirements"></a><span data-ttu-id="6c93f-109">요구 사항 검토</span><span class="sxs-lookup"><span data-stu-id="6c93f-109">Review the requirements</span></span>

<span data-ttu-id="6c93f-110">교육 기관에 경력 코치를 사용하도록 설정하려면 앱을 설치하고 실행하는 데 필요한 기능을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="6c93f-110">To enable Career Coach for your educational institution, review what you need to get the app up and running.</span></span>

<span data-ttu-id="6c93f-111">**기술 요구 사항**</span><span class="sxs-lookup"><span data-stu-id="6c93f-111">**Technical requirements**</span></span>

  - <span data-ttu-id="6c93f-112">Office 365 있는 Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="6c93f-112">Office 365 tenant with Azure Active Directory</span></span>

  - <span data-ttu-id="6c93f-113">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6c93f-113">Microsoft Teams</span></span>

  - <span data-ttu-id="6c93f-114">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="6c93f-114">LinkedIn account connections in Azure Active Directory</span></span>

<span data-ttu-id="6c93f-115">**라이선스**</span><span class="sxs-lookup"><span data-stu-id="6c93f-115">**Licenses**</span></span>

  - <span data-ttu-id="6c93f-116">교직원</span><span class="sxs-lookup"><span data-stu-id="6c93f-116">Faculty</span></span> 

  - <span data-ttu-id="6c93f-117">학생</span><span class="sxs-lookup"><span data-stu-id="6c93f-117">Students</span></span>

> [!NOTE]
> <span data-ttu-id="6c93f-118">커리어 코치 교직원 라이선스는 구성을 완료하는 IT 관리자에게 할당되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c93f-118">A Career Coach Faculty license must be assigned to the IT admin completing the configuration.</span></span>

<span data-ttu-id="6c93f-119">**교육 기관의 데이터 및 파일**</span><span class="sxs-lookup"><span data-stu-id="6c93f-119">**Data and files from your educational institution**</span></span>

  - <span data-ttu-id="6c93f-120">과정 카탈로그 데이터</span><span class="sxs-lookup"><span data-stu-id="6c93f-120">Course catalog data</span></span>

  - <span data-ttu-id="6c93f-121">제공되는 연구 분야</span><span class="sxs-lookup"><span data-stu-id="6c93f-121">Fields of study offered</span></span>

  - <span data-ttu-id="6c93f-122">교육 기관의 LinkedIn 페이지</span><span class="sxs-lookup"><span data-stu-id="6c93f-122">Educational institution’s LinkedIn page</span></span>

  - <span data-ttu-id="6c93f-123">LinkedIn Learning 캠퍼스 구독(기본 설정)</span><span class="sxs-lookup"><span data-stu-id="6c93f-123">LinkedIn Learning campus subscription (preferred)</span></span>

## <a name="purchase-the-career-coach-licenses"></a><span data-ttu-id="6c93f-124">경력 코치 라이선스 구입</span><span class="sxs-lookup"><span data-stu-id="6c93f-124">Purchase the Career Coach licenses</span></span>

<span data-ttu-id="6c93f-125">경력 코치는 EES(교육용 등록 솔루션), CSP(클라우드 서비스 공급자) 및 Microsoft 365 관리 센터(웹 직접)를 통해 자격을 갖춘 고등 교육 기관에 대해 전 세계(중국 및 러시아 제외)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c93f-125">Career Coach is available worldwide (except China and Russia) for qualified higher education institutions through Enrollment for Education Solutions (EES), Cloud Service Providers (CSP), and Microsoft 365 admin center (web direct).</span></span> <span data-ttu-id="6c93f-126">앱의 Microsoft Teams A3/A5 또는 Microsoft 365/A3/A5 Office 365 A1 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c93f-126">As a Microsoft Teams app, customers must have Microsoft 365 A3/A5 or Office 365 A1/A3/A5.</span></span>

### <a name="assign-app-licenses-to-users"></a><span data-ttu-id="6c93f-127">사용자에게 앱 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="6c93f-127">Assign app licenses to users</span></span>

<span data-ttu-id="6c93f-128">단계별 지침은 사용자에게 라이선스 [할당을 참조하세요.](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)</span><span class="sxs-lookup"><span data-stu-id="6c93f-128">For step-by-step instructions, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

### <a name="turn-on-linkedin-account-connections"></a><span data-ttu-id="6c93f-129">LinkedIn 계정 연결 설정</span><span class="sxs-lookup"><span data-stu-id="6c93f-129">Turn on LinkedIn account connections</span></span>

<span data-ttu-id="6c93f-130">경력 **코치는 교육** 기관의 사용자가 커리어 코치 내에서 촉진되는 linkedIn 계정에 Microsoft 365 계정을 연결할 수 있도록 요구합니다.</span><span class="sxs-lookup"><span data-stu-id="6c93f-130">Career Coach **requires** your educational institution’s users to have the ability to connect their Microsoft 365 account to their LinkedIn account that is facilitated within Career Coach</span></span>

1. <span data-ttu-id="6c93f-131">[Azure AD](https://aad.portal.azure.com/) 조직의 전역 관리자 계정으로 Azure AD 관리 센터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="6c93f-131">Sign in to the [Azure AD admin center](https://aad.portal.azure.com/) with an account that's a global admin for the Azure AD organization.</span></span>

2. <span data-ttu-id="6c93f-132">사용자를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6c93f-132">Select **Users**.</span></span>

3. <span data-ttu-id="6c93f-133">사용자 **페이지에서** 사용자 **설정을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6c93f-133">On the **Users** page, select **User settings**.</span></span>

4. <span data-ttu-id="6c93f-134">**LinkedIn 계정 연결에서** 사용자가 자신의 계정을 연결하여 일부 Microsoft 앱 내에서 LinkedIn 연결에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c93f-134">Under **LinkedIn account connections**, allow users to connect their accounts to access their LinkedIn connections within some Microsoft apps.</span></span> <span data-ttu-id="6c93f-135">사용자가 자신의 계정을 연결하는 데 동의할 때까지는 데이터가 공유됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c93f-135">No data is shared until users consent to connect their accounts.</span></span>

   - <span data-ttu-id="6c93f-136">**예를** 선택하여 교육 기관의 모든 사용자에 대해 서비스를 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="6c93f-136">Select **Yes** to enable the service for all users in your educational institution</span></span>

   - <span data-ttu-id="6c93f-137">선택한 **그룹을** 선택하여 교육 기관에서 선택한 사용자 그룹에만 서비스를 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="6c93f-137">Select **Selected group** to enable the service for only a group of selected users in your educational institution</span></span>

   - <span data-ttu-id="6c93f-138">**아니요를** 선택하여 교육 기관의 모든 사용자의 동의를 철회합니다.</span><span class="sxs-lookup"><span data-stu-id="6c93f-138">Select **No** to withdraw consent from all users in your educational institution</span></span>

<span data-ttu-id="6c93f-139">LinkedIn 계정 연결을 통합하는 [방법을 Azure Active Directory](/azure/active-directory/enterprise-users/linkedin-integration)</span><span class="sxs-lookup"><span data-stu-id="6c93f-139">Learn how to [Integrate LinkedIn account connections in Azure Active Directory](/azure/active-directory/enterprise-users/linkedin-integration)</span></span>

## <a name="configure-career-coach-in-the-teams-admin-center"></a><span data-ttu-id="6c93f-140">관리 센터에서 경력 Teams 구성</span><span class="sxs-lookup"><span data-stu-id="6c93f-140">Configure Career Coach in the Teams admin center</span></span>

<span data-ttu-id="6c93f-141">관리 센터의 관리자 설정을 Microsoft Teams 교육 기관에 대한 경력 코치를 구성하고 사용자에 대해 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c93f-141">Using the admin settings in the Microsoft Teams admin center, you can configure Career Coach for your educational institution and enable it for users.</span></span>

## <a name="access-the-career-coach-app-settings"></a><span data-ttu-id="6c93f-142">경력 코치 앱 설정에 액세스</span><span class="sxs-lookup"><span data-stu-id="6c93f-142">Access the Career Coach app settings</span></span>

<span data-ttu-id="6c93f-143">앱 [관리](/microsoftteams/manage-apps) 페이지를 사용하여 Teams 앱 카탈로그에서 앱을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c93f-143">Use the [Manage apps page](/microsoftteams/manage-apps) to view the Teams apps in your educational institution’s app catalog.</span></span>

1. <span data-ttu-id="6c93f-144">관리 **센터에 Teams 로그인합니다.**</span><span class="sxs-lookup"><span data-stu-id="6c93f-144">Sign in to the **Teams admin center**.</span></span>

2. <span data-ttu-id="6c93f-145">왼쪽 탐색에서 앱 **관리 Teams**  >  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6c93f-145">In the left navigation, select **Teams apps** > **Manage apps**.</span></span>  

    > [!NOTE]
    > <span data-ttu-id="6c93f-146">페이지에 액세스하려면 전역 관리자 또는 Teams 관리자 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c93f-146">You must be a global admin or Teams service admin to access the page.</span></span>

3. <span data-ttu-id="6c93f-147">커리어 코치를 **검색하거나 검색합니다.**</span><span class="sxs-lookup"><span data-stu-id="6c93f-147">Search or browse for **Career Coach**.</span></span>  

4. <span data-ttu-id="6c93f-148">경력 **코치** 를 선택한 다음, **설정.**</span><span class="sxs-lookup"><span data-stu-id="6c93f-148">Select **Career Coach**, and then select **Settings.**</span></span>  

    ![커리어 코치 앱을 표시하는 설정 표시됩니다.](media/app-settings.png)

### <a name="configure-the-career-coach-app-settings"></a><span data-ttu-id="6c93f-150">경력 코치 앱 설정 구성</span><span class="sxs-lookup"><span data-stu-id="6c93f-150">Configure the Career Coach app settings</span></span>

<span data-ttu-id="6c93f-151">커리어 코치는 5가지 구성 범주가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c93f-151">Career Coach has five configuration categories:</span></span>

- [<span data-ttu-id="6c93f-152">브랜드 및 기본 설정</span><span class="sxs-lookup"><span data-stu-id="6c93f-152">Brand and preferences</span></span>](#brand-and-preferences)

- [<span data-ttu-id="6c93f-153">LinkedIn 구성</span><span class="sxs-lookup"><span data-stu-id="6c93f-153">LinkedIn configuration</span></span>](#linkedin-configuration)

- [<span data-ttu-id="6c93f-154">과정 카탈로그</span><span class="sxs-lookup"><span data-stu-id="6c93f-154">Course catalog</span></span>](#course-catalog)

- [<span data-ttu-id="6c93f-155">연구 분야</span><span class="sxs-lookup"><span data-stu-id="6c93f-155">Fields of study</span></span>](#fields-of-study)

- [<span data-ttu-id="6c93f-156">사용자 지정</span><span class="sxs-lookup"><span data-stu-id="6c93f-156">Customization</span></span>](#customization)

> [!NOTE]
> <span data-ttu-id="6c93f-157">학생, 교직원 및 교직원을 위해 앱을  효과적으로 사용하도록 설정하려면 브랜드 및 기본 설정, LinkedIn 구성, 과정 카탈로그 및 학습 필드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6c93f-157">Brand and preferences, LinkedIn configuration, Course catalog, and Fields of study are **required** to effectively enable the app for students, faculty, and staff.</span></span>

#### <a name="brand-and-preferences"></a><span data-ttu-id="6c93f-158">브랜드 및 기본 설정</span><span class="sxs-lookup"><span data-stu-id="6c93f-158">Brand and preferences</span></span>

<span data-ttu-id="6c93f-159">브랜드 및 기본 설정 설정 페이지에서 교육 기관의 이름, 로고 및 기본 언어를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6c93f-159">Set your educational institution’s name, logo, and default language on the brand and preferences settings page.</span></span>

![관리 센터의 경력 코치 브랜디드 섹션](media/brand-preferences.png)

##### <a name="educational-institution-icon"></a><span data-ttu-id="6c93f-161">교육 기관 아이콘</span><span class="sxs-lookup"><span data-stu-id="6c93f-161">Educational institution icon</span></span>

<span data-ttu-id="6c93f-162">교육 기관 아이콘은 커리어 코치 전체에서 교육 기관 고유의 콘텐츠를 식별하고, 앱 전체에 걸쳐 카탈로그 리소스, 대시보드의 실제 환경 섹션에서 식별하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c93f-162">The educational institution icon is used throughout Career Coach to identify content unique to your educational institution, course catalog resources throughout the app, and on the real-world experiences section of the dashboard.</span></span> <span data-ttu-id="6c93f-163">아이콘은 다음으로 서식이 가장 잘 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c93f-163">The icon is best formatted as:</span></span>

 - <span data-ttu-id="6c93f-164">투명한 PNG</span><span class="sxs-lookup"><span data-stu-id="6c93f-164">A transparent PNG</span></span>
 - <span data-ttu-id="6c93f-165">1:1의 화면 비율</span><span class="sxs-lookup"><span data-stu-id="6c93f-165">Aspect ratio of 1:1</span></span>
 - <span data-ttu-id="6c93f-166">최대 크기는 64 px x 64 px입니다.</span><span class="sxs-lookup"><span data-stu-id="6c93f-166">Maximum size of 64 px x 64 px.</span></span>

##### <a name="educational-institution-thumbnail"></a><span data-ttu-id="6c93f-167">교육 기관 축소판 그림</span><span class="sxs-lookup"><span data-stu-id="6c93f-167">Educational institution thumbnail</span></span>

<span data-ttu-id="6c93f-168">교육 기관 아이콘은 특정 이미지를 코스에 사용할 수 없는 경우 앱 전체의 코스 카탈로그 리소스에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c93f-168">The educational institution icon will be used for course catalog resources throughout the app when a specific image isn't available for a course.</span></span> <span data-ttu-id="6c93f-169">아이콘은 다음으로 서식이 가장 잘 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c93f-169">The icon is best formatted as:</span></span>

- <span data-ttu-id="6c93f-170">A PNG</span><span class="sxs-lookup"><span data-stu-id="6c93f-170">A PNG</span></span>
- <span data-ttu-id="6c93f-171">16:9의 화면 비율</span><span class="sxs-lookup"><span data-stu-id="6c93f-171">Aspect ratio of 16:9</span></span>
- <span data-ttu-id="6c93f-172">최대 크기는 360 px x 200 px입니다.</span><span class="sxs-lookup"><span data-stu-id="6c93f-172">Maximum size of 360 px x 200 px.</span></span>

#### <a name="linkedin-configuration"></a><span data-ttu-id="6c93f-173">LinkedIn 구성</span><span class="sxs-lookup"><span data-stu-id="6c93f-173">LinkedIn configuration</span></span>

<span data-ttu-id="6c93f-174">LinkedIn 구성은 LinkedIn의 공개 동문 데이터와 경력 코치를 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="6c93f-174">The LinkedIn configuration connects Career Coach with public alumni data from LinkedIn.</span></span>

> [!NOTE]
> <span data-ttu-id="6c93f-175">LinkedIn 페이지 연결이 확인되지 않으면 커리어 코치를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6c93f-175">Career Coach can't be enabled without the LinkedIn page connection verified.</span></span>

##### <a name="add-and-confirm-the-linkedin-page"></a><span data-ttu-id="6c93f-176">LinkedIn 페이지 추가 및 확인</span><span class="sxs-lookup"><span data-stu-id="6c93f-176">Add and confirm the LinkedIn page</span></span>

<span data-ttu-id="6c93f-177">교육 기관의 LinkedIn 페이지를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6c93f-177">Determine the educational institution's LinkedIn page.</span></span> <span data-ttu-id="6c93f-178">LinkedIn에서 검색하거나 경력 서비스 직원과 연결하여 사용할 올바른 페이지를 확인하여 LinkedIn 페이지를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c93f-178">Find the LinkedIn page by searching on LinkedIn or connecting with a career services staff member to determine the correct page to use.</span></span>  
  
1. <span data-ttu-id="6c93f-179">관리 **센터에 Teams 로그인합니다.**</span><span class="sxs-lookup"><span data-stu-id="6c93f-179">Sign in to the **Teams admin center**.</span></span>

1. <span data-ttu-id="6c93f-180">앱 **Teams**  >    >  **커리어 코치** LinkedIn 연결 관리  >  **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6c93f-180">Select **Teams apps** > **Manage apps** > **Career Coach** > **LinkedIn connection**.</span></span>

2. <span data-ttu-id="6c93f-181">교육 기관의 LinkedIn 페이지 URL을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="6c93f-181">Enter your educational institution's LinkedIn page URL.</span></span>  

3. <span data-ttu-id="6c93f-182">적용 **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6c93f-182">Select **Apply**.</span></span>

4. <span data-ttu-id="6c93f-183">확인 URL을 복사하여 교육 기관의 LinkedIn 페이지 관리자 LinkedIn 페이지 관리자 설명서와 [공유합니다.](https://www.linkedin.com/help/linkedin/answer/4783/linkedin-page-admins-overview?lang=en)</span><span class="sxs-lookup"><span data-stu-id="6c93f-183">Copy the verification URL and share it with your educational institution’s LinkedIn page admin [LinkedIn page admin documentation](https://www.linkedin.com/help/linkedin/answer/4783/linkedin-page-admins-overview?lang=en).</span></span> <span data-ttu-id="6c93f-184">확인 링크는 30일 후에 만료됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c93f-184">The verification link expires after 30 days.</span></span>  

   ![커리어 코치에 대한 linkedin 설정](media/linkedin.png)  

#### <a name="course-catalog"></a><span data-ttu-id="6c93f-186">과정 카탈로그</span><span class="sxs-lookup"><span data-stu-id="6c93f-186">Course catalog</span></span>

<span data-ttu-id="6c93f-187">코스 카탈로그는 교육 기관에서 학생들에게 제공하는 과정 및 수업을 나타내고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c93f-187">The course catalog represents the courses and classes offered to students by your educational institution.</span></span> <span data-ttu-id="6c93f-188">이러한 과정은 다음 두 영역에서 앱 내에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c93f-188">These courses are used within the app in two areas:</span></span>

- <span data-ttu-id="6c93f-189">교육 과정은 학습 리소스의 일부로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c93f-189">Courses are returned as part of learning resources.</span></span>  

- <span data-ttu-id="6c93f-190">설명과 같은 코스 및 코스 메타 데이터는 학생들이 성적 증명서를 업로드할 때 자신의 기술을 식별하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c93f-190">Courses and course meta data, like descriptions, are used to help students identify their skills when they upload a transcript.</span></span>  

<span data-ttu-id="6c93f-191">과정 카탈로그를 만들하려면 교육 기관에서 학습한 모든 과정 목록을 함께 작성하고 CSV 파일로 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="6c93f-191">To create the course catalog, put together a list of all courses taught at your educational institution and upload it as a CSV file.</span></span> <span data-ttu-id="6c93f-192">앱은 코스 카탈로그에서 학생의 기술을 자신의 성적표에서 식별하고 수강할 강좌를 제안합니다.</span><span class="sxs-lookup"><span data-stu-id="6c93f-192">The app draws from the course catalog to identify a student’s skills from their transcript and to suggest courses to take.</span></span> 

> [!NOTE]
> <span data-ttu-id="6c93f-193">학생 [정보](location-of-data-in-teams.md) 보호에 대한 Teams [](security-compliance-overview.md) 및 보안 및 규정 준수를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6c93f-193">See [Location of data in Teams](location-of-data-in-teams.md) and [Security and compliance](security-compliance-overview.md) for information about protecting of student information.</span></span> 

##### <a name="course-catalog-documents-formatting-and-schema"></a><span data-ttu-id="6c93f-194">코스 카탈로그 문서 서식 및 스위마</span><span class="sxs-lookup"><span data-stu-id="6c93f-194">Course catalog documents formatting and schema</span></span>

<span data-ttu-id="6c93f-195">문서는 최대 크기가 18MB인 CSV 형식으로 작성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c93f-195">The document needs to be in CSV format with a maximum size of 18 MB.</span></span> <span data-ttu-id="6c93f-196">문서에는 필수 필드 코스 **제목,** 코스 **ID** 및 **과정 URL이 포함되어 있어야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="6c93f-196">The document must contain the required fields **course title**, **course ID**, and **course URL**.</span></span> <span data-ttu-id="6c93f-197">권장 필드를 포함하면 더 나은 검색 결과 및 기술 식별을 반환하여 학생들의 환경을 개선할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c93f-197">Including the recommended fields improves the experience for students by returning better search results and skill identification.</span></span>

> [!NOTE]
> <span data-ttu-id="6c93f-198">시작을 [위해 샘플]( https://aka.ms/career-coach/docs/it-admins/sample-catalog) 과정 카탈로그 문서로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="6c93f-198">Start with the [sample course catalog]( https://aka.ms/career-coach/docs/it-admins/sample-catalog) document to get started.</span></span>

##### <a name="sample-csv-file"></a><span data-ttu-id="6c93f-199">샘플 .CSV 파일</span><span class="sxs-lookup"><span data-stu-id="6c93f-199">Sample .CSV file</span></span>

```
courseId,title,sourceLink,description,language,format,thumbnailLink,thumbnailAltText,educationLevel,topics
"AA-501","Analytics Foundations","https://example.com/course-id","This course equips the student with the knowledge and skills needed to conduct and present large-scale studies based on advanced analytics.","en-us","In-person","https://via.placeholder.com/360x200","Undergraduate","Alt text for the thumbnail","analytics, data science, data analysis, linear regression"
```

<span data-ttu-id="6c93f-200">다음 표에서는 코스 카탈로그에 포함할 항목을 보여 주었다.</span><span class="sxs-lookup"><span data-stu-id="6c93f-200">The following table shows the items to include in the course catalog:</span></span>


| <span data-ttu-id="6c93f-201">이름</span><span class="sxs-lookup"><span data-stu-id="6c93f-201">Name</span></span>             | <span data-ttu-id="6c93f-202">상태</span><span class="sxs-lookup"><span data-stu-id="6c93f-202">Status</span></span>      | <span data-ttu-id="6c93f-203">유형</span><span class="sxs-lookup"><span data-stu-id="6c93f-203">Type</span></span>   | <span data-ttu-id="6c93f-204">설명</span><span class="sxs-lookup"><span data-stu-id="6c93f-204">Description</span></span>                                                                    |
|------------------|-------------|--------|--------------------------------------------------------------------------------|
| <span data-ttu-id="6c93f-205">courseId</span><span class="sxs-lookup"><span data-stu-id="6c93f-205">courseId</span></span>         | <span data-ttu-id="6c93f-206">필수</span><span class="sxs-lookup"><span data-stu-id="6c93f-206">Required</span></span>    | <span data-ttu-id="6c93f-207">string</span><span class="sxs-lookup"><span data-stu-id="6c93f-207">string</span></span> | <span data-ttu-id="6c93f-208">일반적으로 코스 ID(일반적으로 성적 스크립트에서 생성된 것)에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c93f-208">Usually the course id (Typically maps to what is generated in the transcript).</span></span> |
| <span data-ttu-id="6c93f-209">타이틀</span><span class="sxs-lookup"><span data-stu-id="6c93f-209">title</span></span>            | <span data-ttu-id="6c93f-210">필수</span><span class="sxs-lookup"><span data-stu-id="6c93f-210">Required</span></span>    | <span data-ttu-id="6c93f-211">string</span><span class="sxs-lookup"><span data-stu-id="6c93f-211">string</span></span> | <span data-ttu-id="6c93f-212">일반적으로 코스 제목입니다.</span><span class="sxs-lookup"><span data-stu-id="6c93f-212">Usually the course title.</span></span>                                                      |
| <span data-ttu-id="6c93f-213">sourceLink</span><span class="sxs-lookup"><span data-stu-id="6c93f-213">sourceLink</span></span>       | <span data-ttu-id="6c93f-214">필수</span><span class="sxs-lookup"><span data-stu-id="6c93f-214">Required</span></span>    | <span data-ttu-id="6c93f-215">URL</span><span class="sxs-lookup"><span data-stu-id="6c93f-215">URL</span></span>    | <span data-ttu-id="6c93f-216">코스 페이지에 대한 웹 사이트 링크입니다.</span><span class="sxs-lookup"><span data-stu-id="6c93f-216">Website link to the course page.</span></span>                                               |
| <span data-ttu-id="6c93f-217">설명</span><span class="sxs-lookup"><span data-stu-id="6c93f-217">description</span></span>      | <span data-ttu-id="6c93f-218">권장</span><span class="sxs-lookup"><span data-stu-id="6c93f-218">Recommended</span></span> | <span data-ttu-id="6c93f-219">string</span><span class="sxs-lookup"><span data-stu-id="6c93f-219">string</span></span> | <span data-ttu-id="6c93f-220">과정에 대한 소개 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="6c93f-220">Introduction text for the course.</span></span>                                              |
| <span data-ttu-id="6c93f-221">언어</span><span class="sxs-lookup"><span data-stu-id="6c93f-221">language</span></span>         | <span data-ttu-id="6c93f-222">권장</span><span class="sxs-lookup"><span data-stu-id="6c93f-222">Recommended</span></span> | <span data-ttu-id="6c93f-223">string</span><span class="sxs-lookup"><span data-stu-id="6c93f-223">string</span></span> | <span data-ttu-id="6c93f-224">과정의 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="6c93f-224">Language of the course.</span></span> <span data-ttu-id="6c93f-225">표준 언어 코드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c93f-225">Use standard language codes.</span></span>                           |
| <span data-ttu-id="6c93f-226">형식</span><span class="sxs-lookup"><span data-stu-id="6c93f-226">format</span></span>           | <span data-ttu-id="6c93f-227">권장</span><span class="sxs-lookup"><span data-stu-id="6c93f-227">Recommended</span></span> | <span data-ttu-id="6c93f-228">string</span><span class="sxs-lookup"><span data-stu-id="6c93f-228">string</span></span> | <span data-ttu-id="6c93f-229">교육 모드(예: 온라인, 비디오, 대면)</span><span class="sxs-lookup"><span data-stu-id="6c93f-229">Mode of teaching, e.g., online, video, in-person.</span></span>                              |
| <span data-ttu-id="6c93f-230">축소판 그림링크</span><span class="sxs-lookup"><span data-stu-id="6c93f-230">thumbnailLink</span></span>    | <span data-ttu-id="6c93f-231">권장</span><span class="sxs-lookup"><span data-stu-id="6c93f-231">Recommended</span></span> | <span data-ttu-id="6c93f-232">URL</span><span class="sxs-lookup"><span data-stu-id="6c93f-232">URL</span></span>    | <span data-ttu-id="6c93f-233">과정 이미지에 대한 축소판 그림 링크입니다.</span><span class="sxs-lookup"><span data-stu-id="6c93f-233">Thumbnail link to the course image.</span></span>                                            |
| <span data-ttu-id="6c93f-234">축소판 그림AltText</span><span class="sxs-lookup"><span data-stu-id="6c93f-234">thumbnailAltText</span></span> | <span data-ttu-id="6c93f-235">권장</span><span class="sxs-lookup"><span data-stu-id="6c93f-235">Recommended</span></span> | <span data-ttu-id="6c93f-236">string</span><span class="sxs-lookup"><span data-stu-id="6c93f-236">string</span></span> | <span data-ttu-id="6c93f-237">이미지에 대한 접근성 alt 텍스트</span><span class="sxs-lookup"><span data-stu-id="6c93f-237">Accessibility alt text for the image</span></span>                                           |
| <span data-ttu-id="6c93f-238">educationLevel</span><span class="sxs-lookup"><span data-stu-id="6c93f-238">educationLevel</span></span>   | <span data-ttu-id="6c93f-239">권장</span><span class="sxs-lookup"><span data-stu-id="6c93f-239">Recommended</span></span> | <span data-ttu-id="6c93f-240">string</span><span class="sxs-lookup"><span data-stu-id="6c93f-240">string</span></span> | <span data-ttu-id="6c93f-241">학습 수준, 예.</span><span class="sxs-lookup"><span data-stu-id="6c93f-241">Study level, ex.</span></span> <span data-ttu-id="6c93f-242">학부/졸업생.</span><span class="sxs-lookup"><span data-stu-id="6c93f-242">Undergraduate/Graduate.</span></span>                                       |
| <span data-ttu-id="6c93f-243">토픽</span><span class="sxs-lookup"><span data-stu-id="6c93f-243">topics</span></span>           | <span data-ttu-id="6c93f-244">권장</span><span class="sxs-lookup"><span data-stu-id="6c93f-244">Recommended</span></span> | <span data-ttu-id="6c93f-245">string</span><span class="sxs-lookup"><span data-stu-id="6c93f-245">string</span></span> | <span data-ttu-id="6c93f-246">강의가 가르치는 기술과 관련된 토픽 또는 태그입니다.</span><span class="sxs-lookup"><span data-stu-id="6c93f-246">Topics or tags that are associated with the skills the courses teach.</span></span>          |

##### <a name="add-the-course-catalog"></a><span data-ttu-id="6c93f-247">과정 카탈로그 추가</span><span class="sxs-lookup"><span data-stu-id="6c93f-247">Add the course catalog</span></span>

1. <span data-ttu-id="6c93f-248">관리 **센터에 Teams 로그인합니다.**</span><span class="sxs-lookup"><span data-stu-id="6c93f-248">Sign in to the **Teams admin center**.</span></span>

1. <span data-ttu-id="6c93f-249">앱 **Teams** &gt; **커리어 코치** 설정 &gt;  &gt;  &gt; **카탈로그를 선택합니다.**  </span><span class="sxs-lookup"><span data-stu-id="6c93f-249">Select **Teams apps** &gt; **Manage apps** &gt; **Career Coach** &gt; **Settings** &gt;  **Course catalog**.</span></span>

2. <span data-ttu-id="6c93f-250">업로드 CSV 형식으로 교육 과정을 수강합니다.</span><span class="sxs-lookup"><span data-stu-id="6c93f-250">Upload courses in CSV format.</span></span>

4. <span data-ttu-id="6c93f-251">적용 **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6c93f-251">Select **Apply**.</span></span>

   ![경력 코치 앱의 과정 카탈로그 섹션](media/course-catalog.png)

#### <a name="fields-of-study"></a><span data-ttu-id="6c93f-253">연구 분야</span><span class="sxs-lookup"><span data-stu-id="6c93f-253">Fields of study</span></span>

<span data-ttu-id="6c93f-254">연구 분야는 주요 관심 분야, 학업 전공 및 학위와 동의어입니다.</span><span class="sxs-lookup"><span data-stu-id="6c93f-254">The fields of study are synonymous with major areas of interest, academic major, and degree.</span></span> <span data-ttu-id="6c93f-255">이러한 타이틀은 앱을 사용하여 개인 설정된 프로필을 설정하기 시작할 때 학생들이 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="6c93f-255">These titles are referenced by students when they start using the app and begin setting up their personalized profile.</span></span>

<span data-ttu-id="6c93f-256">공학, 영어, 비즈니스 등 학생들에게 사용할 수 있는 모든 학습 필드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6c93f-256">Add all fields of study available to students such as Engineering, English, Business, and so on.</span></span> <span data-ttu-id="6c93f-257">필드 목록을 통해 학생들이 관심 있는 학습 영역을 검색하고 자신의 프로필에 포커스 영역을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c93f-257">The list of fields lets students discover fields of study that may interest them and add their area of focus to their profile.</span></span>

> [!NOTE]
> <span data-ttu-id="6c93f-258">스터디 [문서의 샘플 필드로 시작합니다.](https://aka.ms/career-coach/docs/it-admins/sample-fieldsofstudy)</span><span class="sxs-lookup"><span data-stu-id="6c93f-258">Start with the [sample field of study](https://aka.ms/career-coach/docs/it-admins/sample-fieldsofstudy) document.</span></span>
##### <a name="add-the-fields-of-study"></a><span data-ttu-id="6c93f-259">연구 필드 추가</span><span class="sxs-lookup"><span data-stu-id="6c93f-259">Add the fields of study</span></span>

1. <span data-ttu-id="6c93f-260">관리 **센터에 Teams 로그인합니다.**</span><span class="sxs-lookup"><span data-stu-id="6c93f-260">Sign in to the **Teams admin center**.</span></span>
1. <span data-ttu-id="6c93f-261">앱 **Teams** 커리어 코치 설정 &gt;  &gt;  &gt;  &gt; **앱을 선택합니다.**  </span><span class="sxs-lookup"><span data-stu-id="6c93f-261">Select **Teams apps** &gt; **Manage apps** &gt; **Career Coach** &gt; **Settings** &gt;  **Fields of study**.</span></span>

2. <span data-ttu-id="6c93f-262">업로드 형식의 학습 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="6c93f-262">Upload field of study in CSV format.</span></span>

3. <span data-ttu-id="6c93f-263">적용 **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6c93f-263">Select **Apply**.</span></span>

#### <a name="customization"></a><span data-ttu-id="6c93f-264">사용자 지정</span><span class="sxs-lookup"><span data-stu-id="6c93f-264">Customization</span></span>

<span data-ttu-id="6c93f-265">커리어 코치는 교육 기관에 고유하도록 사용자 지정될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c93f-265">Career Coach can be customized to be unique to your educational institution.</span></span> <span data-ttu-id="6c93f-266">사용자 지정은 대시보드에 환경 추가를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="6c93f-266">The customization supports adding experiences to the dashboard.</span></span> <span data-ttu-id="6c93f-267">학생이 실제 경험을 쌓는 데 도움이 되는 작업 보드, 이벤트, 경력 서비스 사무실, 경력 관련 이벤트, 학생 클럽 및 기타 리소스에 대한 링크를 추가하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6c93f-267">It's recommended to add links to job boards, events, career services office, career-related events, student clubs, and any other resources that help students gain real-world experience.</span></span>

##### <a name="add-customized-experiences"></a><span data-ttu-id="6c93f-268">사용자 지정 환경 추가</span><span class="sxs-lookup"><span data-stu-id="6c93f-268">Add customized experiences</span></span>

1. <span data-ttu-id="6c93f-269">관리 **센터에 Teams 로그인합니다.**</span><span class="sxs-lookup"><span data-stu-id="6c93f-269">Sign in to the **Teams admin center**.</span></span>

1. <span data-ttu-id="6c93f-270">앱 **Teams** &gt; **관리 커리어** 코치 설정 사용자 지정 &gt;   >   &gt; **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6c93f-270">Select **Teams apps** &gt; **Manage apps** &gt; **Career Coach** > **Settings** &gt; **Customization**.</span></span>

2. <span data-ttu-id="6c93f-271">각 URL, 제목 및 간략한 설명을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6c93f-271">Add each URL, a title, and short description.</span></span>  
  
3. <span data-ttu-id="6c93f-272">적용 **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6c93f-272">Select **Apply**.</span></span>

### <a name="enable-the-app"></a><span data-ttu-id="6c93f-273">앱 사용</span><span class="sxs-lookup"><span data-stu-id="6c93f-273">Enable the app</span></span>

<span data-ttu-id="6c93f-274">구성을 완료한 후 학생 및 라이선스가 부여된 사용자를 위해 앱을 사용하도록 설정하여 커리어 코치에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c93f-274">After you complete the configuration, enable the app for students and licensed users so they'll have access to Career Coach.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6c93f-275">전역 또는 관리자 Teams 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c93f-275">You must have Global or Teams admin role permissions.</span></span>

1. <span data-ttu-id="6c93f-276">관리 **센터에 Teams 로그인합니다.**</span><span class="sxs-lookup"><span data-stu-id="6c93f-276">Sign in to the **Teams admin center**.</span></span>

1. <span data-ttu-id="6c93f-277">앱 **Teams** &gt; **커리어 코치 관리 를** &gt; **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6c93f-277">Select **Teams apps** &gt; **Manage apps** &gt; **Career Coach**.</span></span>

2. <span data-ttu-id="6c93f-278">상태 토글을 허용 **으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="6c93f-278">Move the Status toggle to **Allowed**.</span></span>  

  > [!NOTE]
  > <span data-ttu-id="6c93f-279">허용되는 것은 교육 기관의 사용자가 앱을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c93f-279">Allowed means that the app is available for users in your educational institution.</span></span> <span data-ttu-id="6c93f-280">차단된 것은 학생이 앱을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6c93f-280">Blocked means that the app isn't available to students.</span></span>

#### <a name="pin-the-app"></a><span data-ttu-id="6c93f-281">앱 고정</span><span class="sxs-lookup"><span data-stu-id="6c93f-281">Pin the app</span></span>

<span data-ttu-id="6c93f-282">경력 코치를 고정하면 학생들이 앱을 더 쉽게 접근하고 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c93f-282">Pinning Career Coach will make the app more accessible and visible for students.</span></span>

1. <span data-ttu-id="6c93f-283">관리 **센터에 Teams 로그인합니다.**</span><span class="sxs-lookup"><span data-stu-id="6c93f-283">Sign in to the **Teams admin center**.</span></span>

1. <span data-ttu-id="6c93f-284">앱 **Teams 정책** 설정 &gt; **정책을** &gt; *선택합니다.*</span><span class="sxs-lookup"><span data-stu-id="6c93f-284">Select **Teams apps** &gt;**Setup policies** &gt; *Your policy*.</span></span> 

2. <span data-ttu-id="6c93f-285">고정된 **앱 아래에서** 앱 **추가를 선택하세요.**</span><span class="sxs-lookup"><span data-stu-id="6c93f-285">Under **Pinned apps**, choose **Add apps**.</span></span>

1. <span data-ttu-id="6c93f-286">경력 코치를 **검색한** 다음 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6c93f-286">Search for **Career Coach**, and then select **Add**.</span></span>

1. <span data-ttu-id="6c93f-287">앱이 나타날 순서를 선택하고 저장을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6c93f-287">Choose the order for the app to appear and select **Save**.</span></span>

   <span data-ttu-id="6c93f-288">학생은 커리어 코치가 고정된 Microsoft Teams 알림을 하게 될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6c93f-288">Students will be notified in Microsoft Teams that Career Coach has been pinned.</span></span>  

## <a name="resources"></a><span data-ttu-id="6c93f-289">리소스</span><span class="sxs-lookup"><span data-stu-id="6c93f-289">Resources</span></span>

<span data-ttu-id="6c93f-290">다음 리소스는 커리어 코치 앱을 계획하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c93f-290">The following resources will help you plan your Career Coach app.</span></span>

- [<span data-ttu-id="6c93f-291">Microsoft Teams에 오신 것을 환영합니다.</span><span class="sxs-lookup"><span data-stu-id="6c93f-291">Welcome to Microsoft Teams</span></span>](Teams-overview.md)

- [<span data-ttu-id="6c93f-292">Teams를 배포하는 방법</span><span class="sxs-lookup"><span data-stu-id="6c93f-292">How to roll out Teams</span></span>](get-started-with-teams-resources-for-org-wide-rollout.md?tabs=SmallBusiness)

- [<span data-ttu-id="6c93f-293">Microsoft Teams의 Teams 및 채널 개요</span><span class="sxs-lookup"><span data-stu-id="6c93f-293">Overview of teams and channels in Microsoft Teams</span></span>](teams-channels-overview.md)

- [<span data-ttu-id="6c93f-294">관리 센터에서 앱 Microsoft Teams 관리</span><span class="sxs-lookup"><span data-stu-id="6c93f-294">Managing apps in Microsoft Teams Admin Center</span></span>](manage-apps.md)

- [<span data-ttu-id="6c93f-295">보안, 개인 정보 보호 및 규정 준수를 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6c93f-295">Security, privacy, and compliance in Microsoft Teams</span></span>](security-compliance-overview.md)

- [<span data-ttu-id="6c93f-296">온라인 가상 방향 키트</span><span class="sxs-lookup"><span data-stu-id="6c93f-296">Online Virtual Orientation Kit</span></span>](https://www.microsoft.com/education/remote-learning/virtual-orientation) 

- [<span data-ttu-id="6c93f-297">채널의 제한 및 Teams 사양</span><span class="sxs-lookup"><span data-stu-id="6c93f-297">Limits and specification of Teams channels</span></span>](limits-specifications-teams.md)

- [<span data-ttu-id="6c93f-298">Microsoft Teams의 데이터 위치</span><span class="sxs-lookup"><span data-stu-id="6c93f-298">Location of data in Microsoft Teams</span></span>](location-of-data-in-teams.md)

- [<span data-ttu-id="6c93f-299">관리자 교육을 시작하기 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6c93f-299">Getting started with admin training for Microsoft Teams</span></span>](ITAdmin-readiness.md)

- [<span data-ttu-id="6c93f-300">Teams 문제 해결</span><span class="sxs-lookup"><span data-stu-id="6c93f-300">Teams troubleshooting</span></span>](/microsoftteams/troubleshoot/teams-welcome)

- [<span data-ttu-id="6c93f-301">Microsoft Teams에서 앱 사용 권한 정책 관리</span><span class="sxs-lookup"><span data-stu-id="6c93f-301">Manage app permission policies in Microsoft Teams</span></span>](teams-app-permission-policies.md)
