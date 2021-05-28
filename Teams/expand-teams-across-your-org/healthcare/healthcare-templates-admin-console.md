---
title: 의료 템플릿을 사용하여 팀 만들기
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: 관리 센터 또는 Microsoft와 함께 팀 템플릿을 사용하여 Graph, 채널 및 앱의 미리 정의된 템플릿을 제공하여 빠르고 쉽게 팀을 만듭니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f90ddfa9682c7000c4698977c51a39c9631ff9b1
ms.sourcegitcommit: 36924dc54fe7b09607b07d7543fe7e39eb4d2483
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684355"
---
# <a name="use-a-healthcare-team-templates"></a><span data-ttu-id="59403-103">의료 팀 템플릿 사용</span><span class="sxs-lookup"><span data-stu-id="59403-103">Use a healthcare team templates</span></span>

<span data-ttu-id="59403-104">템플릿을 사용하면 미리 정의된 설정, 채널 및 미리 설치된 앱의 템플릿을 제공하여 빠르고 쉽게 팀을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59403-104">Templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="59403-105">헬스케어 조직의 경우 템플릿이 특히 강력할 수 있습니다. 이러한 템플릿은 사용자가 조직을 효과적으로 사용하는 방법을 지향할 수 있도록 Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="59403-105">For healthcare organizations, templates can be especially powerful, as they provide structure for users to become oriented with how to effectively use Microsoft Teams.</span></span> <span data-ttu-id="59403-106">또한 관리자는 서식 파일을 사용하여 조직 전체에 일관된 팀을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59403-106">Templates also allow administrators to deploy consistent teams across their organizations.</span></span> <span data-ttu-id="59403-107">이 문서는 의료 조직 전반에서 여러 팀을 계획, 배포 및 관리할 책임이 있는 경우 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59403-107">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your healthcare organization.</span></span>

<span data-ttu-id="59403-108">팀 헬스케어 템플릿을 사용하여 팀을 만드는 방법을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="59403-108">Choose a method for creating teams with the team healthcare templates:</span></span>

| <span data-ttu-id="59403-109">Who</span><span class="sxs-lookup"><span data-stu-id="59403-109">Who</span></span> | <span data-ttu-id="59403-110">사용 방법:</span><span class="sxs-lookup"><span data-stu-id="59403-110">Method to use:</span></span> |
| ---- | --------- |
| <span data-ttu-id="59403-111">관리자 및 IT 전문가</span><span class="sxs-lookup"><span data-stu-id="59403-111">Admins and IT Professionals</span></span> | <span data-ttu-id="59403-112">[관리 Teams](#use-the-team-templates-in-the-admin-center) 관리 센터를 사용하여 의료 팀 템플릿을 기반으로 팀을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="59403-112">[Use the Teams admin center](#use-the-team-templates-in-the-admin-center) to create teams based on the healthcare team templates.</span></span>|
| <span data-ttu-id="59403-113">개발자 및 시스템 통합자</span><span class="sxs-lookup"><span data-stu-id="59403-113">Developers and systems integrators</span></span> | <span data-ttu-id="59403-114">[Microsoft Graph](#use-the-team-templates-with-the-microsoft-graph) 사용하여 의료 팀 템플릿을 기반으로 팀을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="59403-114">[Use the Microsoft Graph](#use-the-team-templates-with-the-microsoft-graph) to create a team based on the healthcare team templates.</span></span> |

## <a name="use-the-team-templates-in-the-admin-center"></a><span data-ttu-id="59403-115">관리 센터에서 팀 템플릿 사용</span><span class="sxs-lookup"><span data-stu-id="59403-115">Use the team templates in the admin center</span></span>

<span data-ttu-id="59403-116">Microsoft Teams 관리자는 관리자 Teams 관리 센터를 사용하여 팀 템플릿을 사용하여 팀을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59403-116">Microsoft Teams admins can use the Teams admin center to create teams with the team templates.</span></span> <span data-ttu-id="59403-117">Microsoft는 현재 다양한 상황에서 사용할 수 있는 두 가지 일선 의료 서식 파일을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="59403-117">We currently offer two first-party healthcare templates that you can use for a variety of situations.</span></span> <span data-ttu-id="59403-118">일반적으로 팀 템플릿에 대한 자세한 내용은 관리 센터에서 팀 템플릿 시작 [을 참조하세요.](../../get-started-with-teams-templates-in-the-admin-console.md)</span><span class="sxs-lookup"><span data-stu-id="59403-118">To learn more about team templates in general, see [Get started with team templates in the admin center](../../get-started-with-teams-templates-in-the-admin-console.md).</span></span>

### <a name="collaborate-on-patient-care"></a><span data-ttu-id="59403-119">환자 관리 공동 작업</span><span class="sxs-lookup"><span data-stu-id="59403-119">Collaborate on patient care</span></span>

 <span data-ttu-id="59403-120">병동, 병실 또는 부서 내에서 의료 커뮤니케이션 및 공동 작업을 간소화합니다.</span><span class="sxs-lookup"><span data-stu-id="59403-120">Streamline healthcare communication and collaboration within a ward, pod, or department.</span></span> <span data-ttu-id="59403-121">이 서식 파일을 사용하여 병동의 환자 관리 및 운영 요구 사항을 용이하게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59403-121">The template can be used to facilitate patient management and operational needs of a ward.</span></span>

| <span data-ttu-id="59403-122">기본 서식 파일 형식</span><span class="sxs-lookup"><span data-stu-id="59403-122">Base template type</span></span> |<span data-ttu-id="59403-123">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="59403-123">baseTemplateId</span></span>| <span data-ttu-id="59403-124">이 기본 서식 파일과 함께 사용할 수 있는 속성</span><span class="sxs-lookup"><span data-stu-id="59403-124">Properties that come with this base template</span></span> |
| ------------------ |---|----------------------------------------------------- |
| <span data-ttu-id="59403-125">환자 관리 공동 작업</span><span class="sxs-lookup"><span data-stu-id="59403-125">Collaborate on patient care</span></span> |`healthcareWard` | <span data-ttu-id="59403-126">채널</span><span class="sxs-lookup"><span data-stu-id="59403-126">Channels:</span></span><ul><li><span data-ttu-id="59403-127">일반</span><span class="sxs-lookup"><span data-stu-id="59403-127">General</span></span></li><li><span data-ttu-id="59403-128">공지 사항</span><span class="sxs-lookup"><span data-stu-id="59403-128">Announcements</span></span></li><li><span data-ttu-id="59403-129">장애 요소</span><span class="sxs-lookup"><span data-stu-id="59403-129">Huddles</span></span></li><li><span data-ttu-id="59403-130">라운드</span><span class="sxs-lookup"><span data-stu-id="59403-130">Rounds</span></span></li><li><span data-ttu-id="59403-131">직원</span><span class="sxs-lookup"><span data-stu-id="59403-131">Staffing</span></span></li><li><span data-ttu-id="59403-132">교육</span><span class="sxs-lookup"><span data-stu-id="59403-132">Training</span></span></li></ul> <span data-ttu-id="59403-133">앱:</span><span class="sxs-lookup"><span data-stu-id="59403-133">Apps:</span></span> <ul><li><span data-ttu-id="59403-134">Wiki</span><span class="sxs-lookup"><span data-stu-id="59403-134">Wiki</span></span></li><li><span data-ttu-id="59403-135">목록</span><span class="sxs-lookup"><span data-stu-id="59403-135">Lists</span></span></li></ul>|
||||

### <a name="hospital"></a><span data-ttu-id="59403-136">병원</span><span class="sxs-lookup"><span data-stu-id="59403-136">Hospital</span></span>

<span data-ttu-id="59403-137">병원 내에서 여러 병동, 병실, 부서 간 의사소통과 공동 작업을 간소화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59403-137">Streamline communication and collaboration between multiple wards, pods, and departments within a hospital.</span></span> <span data-ttu-id="59403-138">이 템플릿은 병원 운영을 위한 기본 채널 집합을 포함하며, 자체 확장을 통해 관계, 특별 업무를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59403-138">This template includes a set of base channels for hospital operations, and can be self-extended to include specialties, ad-hoc.</span></span>

| <span data-ttu-id="59403-139">기본 서식 파일 형식</span><span class="sxs-lookup"><span data-stu-id="59403-139">Base template type</span></span> |<span data-ttu-id="59403-140">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="59403-140">baseTemplateId</span></span> | <span data-ttu-id="59403-141">이 기본 서식 파일과 함께 사용할 수 있는 속성</span><span class="sxs-lookup"><span data-stu-id="59403-141">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="59403-142">병원</span><span class="sxs-lookup"><span data-stu-id="59403-142">Hospital</span></span>|`healthcareHospital`|<span data-ttu-id="59403-143">채널</span><span class="sxs-lookup"><span data-stu-id="59403-143">Channels:</span></span> <ul><li><span data-ttu-id="59403-144">일반</span><span class="sxs-lookup"><span data-stu-id="59403-144">General</span></span></li><li><span data-ttu-id="59403-145">공지 사항</span><span class="sxs-lookup"><span data-stu-id="59403-145">Announcements</span></span></li><li><span data-ttu-id="59403-146">규정 준수</span><span class="sxs-lookup"><span data-stu-id="59403-146">Compliance</span></span></li><li><span data-ttu-id="59403-147">보호</span><span class="sxs-lookup"><span data-stu-id="59403-147">Custodial</span></span></li><li><span data-ttu-id="59403-148">인적 리소스</span><span class="sxs-lookup"><span data-stu-id="59403-148">Human resources</span></span></li><li><span data-ttu-id="59403-149">약국</span><span class="sxs-lookup"><span data-stu-id="59403-149">Pharmacy</span></span></li></ul> <span data-ttu-id="59403-150">앱:</span><span class="sxs-lookup"><span data-stu-id="59403-150">Apps:</span></span> <ul><li><span data-ttu-id="59403-151">Wiki</span><span class="sxs-lookup"><span data-stu-id="59403-151">Wiki</span></span></li><li><span data-ttu-id="59403-152">목록</span><span class="sxs-lookup"><span data-stu-id="59403-152">Lists</span></span> </li></ul>|
||||


## <a name="use-the-team-templates-with-the-microsoft-graph"></a><span data-ttu-id="59403-153">Microsoft 사용자와 함께 팀 템플릿을 Graph</span><span class="sxs-lookup"><span data-stu-id="59403-153">Use the team templates with the Microsoft Graph</span></span>

<span data-ttu-id="59403-154">개발자는 Microsoft Graph 템플릿을 사용하여 팀을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59403-154">Developers can use the Microsoft Graph to create teams with the team templates.</span></span> <span data-ttu-id="59403-155">Microsoft는 현재 다양한 상황에서 사용할 수 있는 두 가지 일선 의료 서식 파일을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="59403-155">We currently offer two first-party healthcare templates that you can use for a variety of situations.</span></span> <span data-ttu-id="59403-156">일반적으로 팀 템플릿에 대한 자세한 내용은 팀 템플릿 시작 을 [참조합니다.](../../get-started-with-teams-templates.md)</span><span class="sxs-lookup"><span data-stu-id="59403-156">To learn more about team templates in general, see [Get started with team templates](../../get-started-with-teams-templates.md).</span></span> <span data-ttu-id="59403-157">팀 템플릿 및 Microsoft Graph 대한 자세한 내용은 api [Microsoft Teams](/graph/teams-concept-overview?view=graph-rest-1.0) 및 [teamsTemplate](/graph/api/resources/teamstemplate?view=graph-rest-1.0)리소스 유형 을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="59403-157">And for information about team templates and the Microsoft Graph, see [Microsoft Teams API overview](/graph/teams-concept-overview?view=graph-rest-1.0) and [teamsTemplate resource type](/graph/api/resources/teamstemplate?view=graph-rest-1.0).</span></span>

### <a name="ward-template"></a><span data-ttu-id="59403-158">병동 서식 파일</span><span class="sxs-lookup"><span data-stu-id="59403-158">Ward template</span></span>

<span data-ttu-id="59403-159">병동 서식 파일은 병동, 병실 또는 부서 내에서 의사소통과 공동 작업을 하기 위한 서식 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="59403-159">The ward template is meant for communication and collaboration within a ward, pod, or department.</span></span> <span data-ttu-id="59403-160">이 서식 파일을 사용하여 병동의 환자 관리 및 운영 요구 사항을 용이하게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59403-160">The template can be used to facilitate patient management, as well as the operational needs of a ward.</span></span> <span data-ttu-id="59403-161">예를 들어, 병동 공지 사항을 *공지 사항* 채널에서 게시하고 *직원* 에서 교대 근무를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59403-161">For example, ward announcements can be posted in the *Announcements* channel and shifts can be managed in *Staffing*.</span></span> <span data-ttu-id="59403-162">병동 작업을 간소화하고자 하는 경우, 이 서식 파일이 매우 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="59403-162">If you're looking to streamline your ward operations, then this template is for you.</span></span>

|<span data-ttu-id="59403-163">기본 서식 파일 형식</span><span class="sxs-lookup"><span data-stu-id="59403-163">Base Template Type</span></span> |<span data-ttu-id="59403-164">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="59403-164">baseTemplateId</span></span> |<span data-ttu-id="59403-165">기준 서식 파일 채널</span><span class="sxs-lookup"><span data-stu-id="59403-165">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="59403-166">의료 - 병동</span><span class="sxs-lookup"><span data-stu-id="59403-166">Healthcare - Ward</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | <span data-ttu-id="59403-167">공지 사항\*</span><span class="sxs-lookup"><span data-stu-id="59403-167">Announcements\*</span></span> <br> <span data-ttu-id="59403-168">장애 요소\*</span><span class="sxs-lookup"><span data-stu-id="59403-168">Huddles\*</span></span> <br> <span data-ttu-id="59403-169">라운드\*</span><span class="sxs-lookup"><span data-stu-id="59403-169">Rounds\*</span></span> <br> <span data-ttu-id="59403-170">직원\*</span><span class="sxs-lookup"><span data-stu-id="59403-170">Staffing\*</span></span> <br> <span data-ttu-id="59403-171">교육\*</span><span class="sxs-lookup"><span data-stu-id="59403-171">Training\*</span></span> |
|     | |         |

<span data-ttu-id="59403-172">\*자동 즐겨찾기 지정</span><span class="sxs-lookup"><span data-stu-id="59403-172">\* Auto-favorited</span></span>

### <a name="hospital-template"></a><span data-ttu-id="59403-173">병원 서식 파일</span><span class="sxs-lookup"><span data-stu-id="59403-173">Hospital template</span></span>

<span data-ttu-id="59403-174">이 병원 서식 파일은 병원 내에서 여러 병동, 병실, 부서 간 의사소통과 공동 작업을 수행하기 위해 제작되었습니다.</span><span class="sxs-lookup"><span data-stu-id="59403-174">The hospital template is meant for communication and collaboration between multiple wards, pods, and departments within a hospital.</span></span> <span data-ttu-id="59403-175">이 서식 파일에는 *공지 사항*, *보호* 및 *약국* 을 비롯한 여러 운영 채널이 포함되어 있지만, 또한 원하는 대로 추가, 삭제 또는 편집할 수 있는 다양한 추가 부서 또는 전문 중심 채널로 템플릿을 확장하는 아래의 스크립트도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="59403-175">Included in this template are several operational channels including *Announcements*, *Custodial*, and *Pharmacy*, but we also provide a script below which extends the template with a variety of additional department or specialty-centric channels that you can add to, delete from, or edit to your liking.</span></span> <span data-ttu-id="59403-176">예를 들어, *내분비학과* 가 있지만 *안과* 용 채널은 필요하지 않은 경우 스크립트를 조정하여 *내분비학과* 채널을 포함하고 *안과* 채널을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59403-176">For example, if you have an *Endocrinology* department, but don't need a channel for *Ophthalmology*, then the script can be adapted to include an *Endocrinology* channel and remove the *Ophthalmology* channel.</span></span> <span data-ttu-id="59403-177">알림 포화 상태를 방지하기 위해 이러한 특수 또는 병동 모델의 채널은 자동 즐겨찾기하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="59403-177">We recommend that these specialty or ward-modeled channels not be auto-favorited to avoid notification saturation.</span></span> <span data-ttu-id="59403-178">사용자는 일반적으로 관련이 있는 모든 채널을 즐겨찾습니다.</span><span class="sxs-lookup"><span data-stu-id="59403-178">Users generally favorite any channels that they find relevant.</span></span>

|<span data-ttu-id="59403-179">기본 서식 파일 형식</span><span class="sxs-lookup"><span data-stu-id="59403-179">Base Template Type</span></span> |<span data-ttu-id="59403-180">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="59403-180">baseTemplateId</span></span> |<span data-ttu-id="59403-181">기준 서식 파일 채널</span><span class="sxs-lookup"><span data-stu-id="59403-181">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="59403-182">의료 - 병원</span><span class="sxs-lookup"><span data-stu-id="59403-182">Healthcare - Hospital</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | <span data-ttu-id="59403-183">공지 사항\*</span><span class="sxs-lookup"><span data-stu-id="59403-183">Announcements\*</span></span> <br> <span data-ttu-id="59403-184">규정 준수\*</span><span class="sxs-lookup"><span data-stu-id="59403-184">Compliance\*</span></span> <br> <span data-ttu-id="59403-185">보호</span><span class="sxs-lookup"><span data-stu-id="59403-185">Custodial</span></span> <br> <span data-ttu-id="59403-186">인적 리소스</span><span class="sxs-lookup"><span data-stu-id="59403-186">Human Resources</span></span> <br> <span data-ttu-id="59403-187">약국</span><span class="sxs-lookup"><span data-stu-id="59403-187">Pharmacy</span></span> |
| | |  |

<span data-ttu-id="59403-188">\*자동 즐겨찾기 지정</span><span class="sxs-lookup"><span data-stu-id="59403-188">\* Auto-favorited</span></span> 

### <a name="how-to-use-first-party-templates"></a><span data-ttu-id="59403-189">기본 서식 파일을 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="59403-189">How to use first-party templates</span></span>

<span data-ttu-id="59403-190">이러한 서식 파일을 사용하려면 요청 본문의 'template@odata.bind' 속성을 '표준'에서 위의 TemplateID로 변경하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="59403-190">To use these templates, simply change the 'template@odata.bind' property in the request body from 'standard' to the TemplateIDs above.</span></span>  <span data-ttu-id="59403-191">팀 템플릿을 배포하는 방법에 대한 자세한 내용은 팀을 만드는 Graph Microsoft Graph [문서를 참조하세요.](/graph/api/team-post?view=graph-rest-beta)</span><span class="sxs-lookup"><span data-stu-id="59403-191">For more information on how to deploy team templates, see the Microsoft Graph article on how to [create a Team](/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="59403-192">서식 파일에서 채널은 일반 탭 아래에 자동으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="59403-192">The channels in the template will automatically be created under the General Tab.</span></span>

#### <a name="example-hospital-template-extension-script"></a><span data-ttu-id="59403-193">예: 병원 서식 파일 확장 스크립트</span><span class="sxs-lookup"><span data-stu-id="59403-193">Example: Hospital template extension script</span></span>

``` Powershell
{ 
          "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('healthcareHospital')",
          "DisplayName": "Contoso Hospital",
          "Description": "Team for all staff in Contoso Hospital",
          "Channels": [
            {
              "displayName": "Ambulatory",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Anesthesiology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Cardiology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "CCU",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Ear, Nose, and Throat",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Emergency Care",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Family Medicine",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Gynecology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "ICU",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Mother-Baby",
              "IsFavoriteByDefault": false
            }, 
            {
              "displayName": "Neonatal",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Neurology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Oncology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Ophthalmology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "PACU",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Psychiatric",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Radiology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Rehabilitation",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Surgical",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Urology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Women's Health",
              "IsFavoriteByDefault": false
            }
          ],
          "Apps": [
            {
              "Id": "1542629c-01b3-4a6d-8f76-1938b779e48d"
            }
          ]
          }

```

### <a name="related-topics"></a><span data-ttu-id="59403-194">관련 주제</span><span class="sxs-lookup"><span data-stu-id="59403-194">Related topics</span></span>

[<span data-ttu-id="59403-195">팀 템플릿 시작</span><span class="sxs-lookup"><span data-stu-id="59403-195">Get started with team templates</span></span>](../../get-started-with-teams-templates.md)

[<span data-ttu-id="59403-196">의료 조직을 위한 팀 시작</span><span class="sxs-lookup"><span data-stu-id="59403-196">Get started with team for Healthcare organizations</span></span>](teams-in-hc.md)