---
title: Teams 의료 서식 파일을 사용하여 팀 만들기
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
description: 관리 센터 또는 Microsoft Graph에서 Microsoft Teams 서식 파일을 사용하여 설정, 채널 및 앱의 미리 정의된 서식 파일을 제공하여 빠르고 쉽게 팀을 만들 수 있습니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b45c949b70aa2a299f2aafe54d81cdd8a1a6c0b5
ms.sourcegitcommit: 774c2fdc71df430674493c33b609523af3cbda4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/16/2021
ms.locfileid: "50260310"
---
# <a name="create-a-team-using-teams-healthcare-templates"></a><span data-ttu-id="e9f47-103">Teams 의료 서식 파일을 사용하여 팀 만들기</span><span class="sxs-lookup"><span data-stu-id="e9f47-103">Create a team using Teams healthcare templates</span></span>

<span data-ttu-id="e9f47-104">Microsoft Teams 서식 파일을 사용하면 설정, 채널 및 미리 설치된 앱의 미리 정의된 서식 파일을 제공하여 빠르고 쉽게 팀을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9f47-104">Microsoft Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="e9f47-105">의료 조직의 경우 템플릿은 사용자가 Teams를 효과적으로 사용하는 방법을 주도할 수 있는 구조를 제공하기에 특히 강력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9f47-105">For healthcare organizations, templates can be especially powerful, as they provide structure for users to become oriented with how to effectively use Teams.</span></span> <span data-ttu-id="e9f47-106">또한 템플릿을 사용하면 관리자가 조직 전체에 일관된 팀을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9f47-106">Templates also allow administrators to deploy consistent teams across their organizations.</span></span> <span data-ttu-id="e9f47-107">이 문서는 의료 조직 전체에서 여러 팀을 계획, 배포 및 관리할 책임이 있는 경우를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e9f47-107">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your healthcare organization.</span></span>

<span data-ttu-id="e9f47-108">Teams 의료 서식 파일을 사용하여 팀을 만드는 방법을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="e9f47-108">Choose a method for creating teams with the Teams healthcare templates:</span></span>

| <span data-ttu-id="e9f47-109">Who</span><span class="sxs-lookup"><span data-stu-id="e9f47-109">Who</span></span> | <span data-ttu-id="e9f47-110">사용하는 방법:</span><span class="sxs-lookup"><span data-stu-id="e9f47-110">Method to use:</span></span> |
| ---- | --------- |
| <span data-ttu-id="e9f47-111">관리자 및 IT 전문가</span><span class="sxs-lookup"><span data-stu-id="e9f47-111">Admins and IT Professionals</span></span> | <span data-ttu-id="e9f47-112">[Teams 관리 센터를 사용하여](#use-the-teams-templates-in-the-teams-admin-center) 의료 팀 서식 파일을 기반으로 팀을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e9f47-112">[Use the Teams admin center](#use-the-teams-templates-in-the-teams-admin-center) to create teams based on the healthcare Teams templates.</span></span>|
| <span data-ttu-id="e9f47-113">개발자 및 시스템 통합자</span><span class="sxs-lookup"><span data-stu-id="e9f47-113">Developers and systems integrators</span></span> | <span data-ttu-id="e9f47-114">[Microsoft Graph를](#use-the-teams-templates-with-the-microsoft-graph) 사용하여 의료 팀 템플릿을 기반으로 팀을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e9f47-114">[Use the Microsoft Graph](#use-the-teams-templates-with-the-microsoft-graph) to create teams based on the healthcare Teams templates.</span></span> |

## <a name="use-the-teams-templates-in-the-teams-admin-center"></a><span data-ttu-id="e9f47-115">Teams 관리 센터에서 Teams 서식 파일 사용</span><span class="sxs-lookup"><span data-stu-id="e9f47-115">Use the Teams templates in the Teams admin center</span></span>

<span data-ttu-id="e9f47-116">Microsoft Teams 관리자는 Teams 관리 센터를 사용하여 Teams 서식 파일을 사용하여 팀을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9f47-116">Microsoft Teams admins can use the Teams admin center to create teams with the Teams templates.</span></span> <span data-ttu-id="e9f47-117">현재 다양한 상황에 사용할 수 있는 두 개의 첫 번째 의료 템플릿을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e9f47-117">We currently offer two first-party healthcare templates that you can use for a variety of situations.</span></span> <span data-ttu-id="e9f47-118">일반적으로 팀 서식 파일에 대한 자세한 내용은 관리 센터에서 Teams 서식 [파일 시작을 참조하세요.](../../get-started-with-teams-templates-in-the-admin-console.md)</span><span class="sxs-lookup"><span data-stu-id="e9f47-118">To learn more about team templates in general, see [Get started with Teams templates in the admin center](../../get-started-with-teams-templates-in-the-admin-console.md).</span></span>

### <a name="collaborate-on-patient-care"></a><span data-ttu-id="e9f47-119">환자 관리에 대한 공동 작업</span><span class="sxs-lookup"><span data-stu-id="e9f47-119">Collaborate on patient care</span></span>

 <span data-ttu-id="e9f47-120">구, Pod 또는 부서 내에서 의료 통신 및 공동 작업을 간소화합니다.</span><span class="sxs-lookup"><span data-stu-id="e9f47-120">Streamline healthcare communication and collaboration within a ward, pod, or department.</span></span> <span data-ttu-id="e9f47-121">이 템플릿은 환자 관리 및 구의 운영 요구를 용이하게 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9f47-121">The template can be used to facilitate patient management and operational needs of a ward.</span></span>

| <span data-ttu-id="e9f47-122">기본 템플릿 형식</span><span class="sxs-lookup"><span data-stu-id="e9f47-122">Base template type</span></span> |<span data-ttu-id="e9f47-123">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="e9f47-123">baseTemplateId</span></span>| <span data-ttu-id="e9f47-124">이 기본 템플릿과 함께 사용할 속성</span><span class="sxs-lookup"><span data-stu-id="e9f47-124">Properties that come with this base template</span></span> |
| ------------------ |---|----------------------------------------------------- |
| <span data-ttu-id="e9f47-125">환자 관리에 대한 공동 작업</span><span class="sxs-lookup"><span data-stu-id="e9f47-125">Collaborate on patient care</span></span> |`healthcareWard` | <span data-ttu-id="e9f47-126">채널:</span><span class="sxs-lookup"><span data-stu-id="e9f47-126">Channels:</span></span><ul><li><span data-ttu-id="e9f47-127">일반</span><span class="sxs-lookup"><span data-stu-id="e9f47-127">General</span></span></li><li><span data-ttu-id="e9f47-128">공지</span><span class="sxs-lookup"><span data-stu-id="e9f47-128">Announcements</span></span></li><li><span data-ttu-id="e9f47-129">Huddles</span><span class="sxs-lookup"><span data-stu-id="e9f47-129">Huddles</span></span></li><li><span data-ttu-id="e9f47-130">라운드</span><span class="sxs-lookup"><span data-stu-id="e9f47-130">Rounds</span></span></li><li><span data-ttu-id="e9f47-131">직원 직원</span><span class="sxs-lookup"><span data-stu-id="e9f47-131">Staffing</span></span></li><li><span data-ttu-id="e9f47-132">교육</span><span class="sxs-lookup"><span data-stu-id="e9f47-132">Training</span></span></li></ul> <span data-ttu-id="e9f47-133">앱:</span><span class="sxs-lookup"><span data-stu-id="e9f47-133">Apps:</span></span> <ul><li><span data-ttu-id="e9f47-134">Wiki</span><span class="sxs-lookup"><span data-stu-id="e9f47-134">Wiki</span></span></li><li><span data-ttu-id="e9f47-135">목록</span><span class="sxs-lookup"><span data-stu-id="e9f47-135">Lists</span></span></li></ul>|
||||

### <a name="hospital"></a><span data-ttu-id="e9f47-136">병원</span><span class="sxs-lookup"><span data-stu-id="e9f47-136">Hospital</span></span>

<span data-ttu-id="e9f47-137">여러 구, Pod 및 병원 내의 부서 간의 통신 및 공동 작업을 간소화합니다.</span><span class="sxs-lookup"><span data-stu-id="e9f47-137">Streamline communication and collaboration between multiple wards, pods, and departments within a hospital.</span></span> <span data-ttu-id="e9f47-138">이 템플릿은 병원 운영을 위한 기본 채널 집합을 포함하며, 전문성, 애드워크를 포함하기 위해 자체 확장될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9f47-138">This template includes a set of base channels for hospital operations, and can be self-extended to include specialties, ad-hoc.</span></span>

| <span data-ttu-id="e9f47-139">기본 템플릿 형식</span><span class="sxs-lookup"><span data-stu-id="e9f47-139">Base template type</span></span> |<span data-ttu-id="e9f47-140">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="e9f47-140">baseTemplateId</span></span> | <span data-ttu-id="e9f47-141">이 기본 템플릿과 함께 사용할 속성</span><span class="sxs-lookup"><span data-stu-id="e9f47-141">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="e9f47-142">병원</span><span class="sxs-lookup"><span data-stu-id="e9f47-142">Hospital</span></span>|`healthcareHospital`|<span data-ttu-id="e9f47-143">채널:</span><span class="sxs-lookup"><span data-stu-id="e9f47-143">Channels:</span></span> <ul><li><span data-ttu-id="e9f47-144">일반</span><span class="sxs-lookup"><span data-stu-id="e9f47-144">General</span></span></li><li><span data-ttu-id="e9f47-145">공지</span><span class="sxs-lookup"><span data-stu-id="e9f47-145">Announcements</span></span></li><li><span data-ttu-id="e9f47-146">규정 준수</span><span class="sxs-lookup"><span data-stu-id="e9f47-146">Compliance</span></span></li><li><span data-ttu-id="e9f47-147">Custodial</span><span class="sxs-lookup"><span data-stu-id="e9f47-147">Custodial</span></span></li><li><span data-ttu-id="e9f47-148">인적 자원</span><span class="sxs-lookup"><span data-stu-id="e9f47-148">Human resources</span></span></li><li><span data-ttu-id="e9f47-149">약국</span><span class="sxs-lookup"><span data-stu-id="e9f47-149">Pharmacy</span></span></li></ul> <span data-ttu-id="e9f47-150">앱:</span><span class="sxs-lookup"><span data-stu-id="e9f47-150">Apps:</span></span> <ul><li><span data-ttu-id="e9f47-151">Wiki</span><span class="sxs-lookup"><span data-stu-id="e9f47-151">Wiki</span></span></li><li><span data-ttu-id="e9f47-152">목록</span><span class="sxs-lookup"><span data-stu-id="e9f47-152">Lists</span></span> </li></ul>|
||||


## <a name="use-the-teams-templates-with-the-microsoft-graph"></a><span data-ttu-id="e9f47-153">Microsoft Graph에서 Teams 서식 파일 사용</span><span class="sxs-lookup"><span data-stu-id="e9f47-153">Use the Teams templates with the Microsoft Graph</span></span>

<span data-ttu-id="e9f47-154">개발자는 Microsoft Graph를 사용하여 Teams 서식 파일로 팀을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9f47-154">Developers can use the Microsoft Graph to create teams with the Teams templates.</span></span> <span data-ttu-id="e9f47-155">현재 다양한 상황에 사용할 수 있는 두 개의 첫 번째 의료 템플릿을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e9f47-155">We currently offer two first-party healthcare templates that you can use for a variety of situations.</span></span> <span data-ttu-id="e9f47-156">일반적으로 팀 서식 파일에 대한 자세한 내용은 Teams 서식 [파일 시작을 참조합니다.](../../get-started-with-teams-templates.md)</span><span class="sxs-lookup"><span data-stu-id="e9f47-156">To learn more about team templates in general, see [Get started with Teams templates](../../get-started-with-teams-templates.md).</span></span> <span data-ttu-id="e9f47-157">Teams 템플릿 및 Microsoft Graph에 대한 자세한 내용은 [Microsoft Teams API 개요](https://docs.microsoft.com/graph/teams-concept-overview?view=graph-rest-1.0) 및 [teamsTemplate 리소스 종류를 참조하세요.](https://docs.microsoft.com/graph/api/resources/teamstemplate?view=graph-rest-1.0)</span><span class="sxs-lookup"><span data-stu-id="e9f47-157">And for information about Teams templates and the Microsoft Graph, see [Microsoft Teams API overview](https://docs.microsoft.com/graph/teams-concept-overview?view=graph-rest-1.0) and [teamsTemplate resource type](https://docs.microsoft.com/graph/api/resources/teamstemplate?view=graph-rest-1.0).</span></span>

### <a name="ward-template"></a><span data-ttu-id="e9f47-158">Ward 서식 파일</span><span class="sxs-lookup"><span data-stu-id="e9f47-158">Ward template</span></span>

<span data-ttu-id="e9f47-159">와드 서식 파일은 구, Pod 또는 부서 내에서 통신 및 공동 작업을 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e9f47-159">The ward template is meant for communication and collaboration within a ward, pod, or department.</span></span> <span data-ttu-id="e9f47-160">이 템플릿은 환자 관리뿐만 아니라 구의 운영 요구를 용이하게 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9f47-160">The template can be used to facilitate patient management, as well as the operational needs of a ward.</span></span> <span data-ttu-id="e9f47-161">예를 들어, 공지사항 채널에 와드  공지 사항을 게시할 수 있으며 교대 근무는 직원 관리에서 관리할 *수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="e9f47-161">For example, ward announcements can be posted in the *Announcements* channel and shifts can be managed in *Staffing*.</span></span> <span data-ttu-id="e9f47-162">구 작업을 간소화하고자 하는 경우 이 템플릿을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9f47-162">If you're looking to streamline your ward operations, then this template is for you.</span></span>

|<span data-ttu-id="e9f47-163">기본 템플릿 유형</span><span class="sxs-lookup"><span data-stu-id="e9f47-163">Base Template Type</span></span> |<span data-ttu-id="e9f47-164">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="e9f47-164">baseTemplateId</span></span> |<span data-ttu-id="e9f47-165">기준 템플릿 채널</span><span class="sxs-lookup"><span data-stu-id="e9f47-165">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="e9f47-166">의료 - Ward</span><span class="sxs-lookup"><span data-stu-id="e9f47-166">Healthcare - Ward</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | <span data-ttu-id="e9f47-167">공지\*</span><span class="sxs-lookup"><span data-stu-id="e9f47-167">Announcements\*</span></span> <br> <span data-ttu-id="e9f47-168">Huddles\*</span><span class="sxs-lookup"><span data-stu-id="e9f47-168">Huddles\*</span></span> <br> <span data-ttu-id="e9f47-169">라운드\*</span><span class="sxs-lookup"><span data-stu-id="e9f47-169">Rounds\*</span></span> <br> <span data-ttu-id="e9f47-170">직원 직원\*</span><span class="sxs-lookup"><span data-stu-id="e9f47-170">Staffing\*</span></span> <br> <span data-ttu-id="e9f47-171">교육\*</span><span class="sxs-lookup"><span data-stu-id="e9f47-171">Training\*</span></span> |
|     | |         |

<span data-ttu-id="e9f47-172">\* 자동 즐겨찾기</span><span class="sxs-lookup"><span data-stu-id="e9f47-172">\* Auto-favorited</span></span>

### <a name="hospital-template"></a><span data-ttu-id="e9f47-173">병원 서식 파일</span><span class="sxs-lookup"><span data-stu-id="e9f47-173">Hospital template</span></span>

<span data-ttu-id="e9f47-174">병원 템플릿은 여러 구, Pod 및 병원 내의 부서 간의 통신 및 공동 작업을 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e9f47-174">The hospital template is meant for communication and collaboration between multiple wards, pods, and departments within a hospital.</span></span> <span data-ttu-id="e9f47-175">이 템플릿에는 공지, 관리 및  *약국을* 비롯한 여러 운영 채널이 포함되어 있지만, 아래에는 원하는 채널에 추가, 삭제 또는 편집할 수 있는 다양한 부서 또는 특수 중심 채널로 템플릿을 확장하는 스크립트가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9f47-175">Included in this template are several operational channels including *Announcements*, *Custodial*, and *Pharmacy*, but we also provide a script below which extends the template with a variety of additional department or specialty-centric channels that you can add to, delete from, or edit to your liking.</span></span> <span data-ttu-id="e9f47-176">예를 들어, 내분비학 부서가 있지만 *Ophthalmology에* 대한 채널이 필요하지 않은 경우 스크립트를 조정하여 내분비 채널을 포함하고 *Ophthalmology* 채널을 제거할 수 있습니다.  </span><span class="sxs-lookup"><span data-stu-id="e9f47-176">For example, if you have an *Endocrinology* department, but don't need a channel for *Ophthalmology*, then the script can be adapted to include an *Endocrinology* channel and remove the *Ophthalmology* channel.</span></span> <span data-ttu-id="e9f47-177">알림 포화 방지를 위해 이러한 전문 채널 또는 구 모델링 채널을 자동으로 즐겨찾기하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e9f47-177">We recommend that these specialty or ward-modeled channels not be auto-favorited to avoid notification saturation.</span></span> <span data-ttu-id="e9f47-178">사용자는 일반적으로 관련성이 있는 채널을 즐겨찾기합니다.</span><span class="sxs-lookup"><span data-stu-id="e9f47-178">Users generally favorite any channels that they find relevant.</span></span>

|<span data-ttu-id="e9f47-179">기본 템플릿 유형</span><span class="sxs-lookup"><span data-stu-id="e9f47-179">Base Template Type</span></span> |<span data-ttu-id="e9f47-180">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="e9f47-180">baseTemplateId</span></span> |<span data-ttu-id="e9f47-181">기준 템플릿 채널</span><span class="sxs-lookup"><span data-stu-id="e9f47-181">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="e9f47-182">의료 - 병원</span><span class="sxs-lookup"><span data-stu-id="e9f47-182">Healthcare - Hospital</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | <span data-ttu-id="e9f47-183">공지\*</span><span class="sxs-lookup"><span data-stu-id="e9f47-183">Announcements\*</span></span> <br> <span data-ttu-id="e9f47-184">규정 준수\*</span><span class="sxs-lookup"><span data-stu-id="e9f47-184">Compliance\*</span></span> <br> <span data-ttu-id="e9f47-185">Custodial</span><span class="sxs-lookup"><span data-stu-id="e9f47-185">Custodial</span></span> <br> <span data-ttu-id="e9f47-186">인적 자원</span><span class="sxs-lookup"><span data-stu-id="e9f47-186">Human Resources</span></span> <br> <span data-ttu-id="e9f47-187">약국</span><span class="sxs-lookup"><span data-stu-id="e9f47-187">Pharmacy</span></span> |
| | |  |

<span data-ttu-id="e9f47-188">\* 자동 즐겨찾기</span><span class="sxs-lookup"><span data-stu-id="e9f47-188">\* Auto-favorited</span></span> 

### <a name="how-to-use-first-party-templates"></a><span data-ttu-id="e9f47-189">첫 번째 파티 템플릿을 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="e9f47-189">How to use first-party templates</span></span>

<span data-ttu-id="e9f47-190">이러한 템플릿을 사용하기 위해 요청 본문의 'template@odata.bind' 속성을 'standard'에서 위의 TemplateID로 변경하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9f47-190">To use these templates, simply change the 'template@odata.bind' property in the request body from 'standard' to the TemplateIDs above.</span></span>  <span data-ttu-id="e9f47-191">Teams 템플릿을 배포하는 방법에 대한 자세한 내용은 팀을 만드는 방법에 대한 Microsoft Graph [문서를 참조하세요.](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)</span><span class="sxs-lookup"><span data-stu-id="e9f47-191">For more information on how to deploy Teams templates, see the Microsoft Graph article on how to [create a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="e9f47-192">템플릿의 채널은 일반 탭 아래에 자동으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="e9f47-192">The channels in the template will automatically be created under the General Tab.</span></span>

#### <a name="example-hospital-template-extension-script"></a><span data-ttu-id="e9f47-193">예: 병원 템플릿 확장 스크립트</span><span class="sxs-lookup"><span data-stu-id="e9f47-193">Example: Hospital template extension script</span></span>

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

### <a name="related-topics"></a><span data-ttu-id="e9f47-194">관련 항목</span><span class="sxs-lookup"><span data-stu-id="e9f47-194">Related topics</span></span>

[<span data-ttu-id="e9f47-195">Teams 서식 파일 시작</span><span class="sxs-lookup"><span data-stu-id="e9f47-195">Get started with Teams templates</span></span>](../../get-started-with-teams-templates.md)

[<span data-ttu-id="e9f47-196">의료 조직을 위한 Teams 시작</span><span class="sxs-lookup"><span data-stu-id="e9f47-196">Get started with Teams for Healthcare organizations</span></span>](teams-in-hc.md)
