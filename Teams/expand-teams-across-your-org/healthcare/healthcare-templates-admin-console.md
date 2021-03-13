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
description: 관리 센터 또는 Microsoft Graph에서 Microsoft Teams 서식 파일을 사용하여 설정, 채널 및 앱의 미리 정의된 서식 파일을 제공함으로써 팀을 쉽고 빠르게 만들 수 있습니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b45c949b70aa2a299f2aafe54d81cdd8a1a6c0b5
ms.sourcegitcommit: 774c2fdc71df430674493c33b609523af3cbda4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/16/2021
ms.locfileid: "50260310"
---
# <a name="create-a-team-using-teams-healthcare-templates"></a><span data-ttu-id="a3c39-103">Teams 의료 서식 파일을 사용하여 팀 만들기</span><span class="sxs-lookup"><span data-stu-id="a3c39-103">Create a team using Teams healthcare templates</span></span>

<span data-ttu-id="a3c39-104">Microsoft Teams 서식 파일을 사용하면 미리 정의된 설정, 채널 및 미리 설치된 앱 서식 파일을 제공하여 팀을 쉽고 빠르게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3c39-104">Microsoft Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="a3c39-105">서식 파일은 사용자가 Teams를 효과적으로 사용하는 방법을 통해 방향을 정할 수 있는 구조를 제공하기 때문에 특히 강력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3c39-105">For healthcare organizations, templates can be especially powerful, as they provide structure for users to become oriented with how to effectively use Teams.</span></span> <span data-ttu-id="a3c39-106">또한 관리자는 서식 파일을 사용하여 조직 전체에 일관된 팀을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3c39-106">Templates also allow administrators to deploy consistent teams across their organizations.</span></span> <span data-ttu-id="a3c39-107">이 문서는 의료 조직 전반에서 여러 팀을 계획, 배포 및 관리할 책임이 있는 경우 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3c39-107">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your healthcare organization.</span></span>

<span data-ttu-id="a3c39-108">다음과 같은 Teams 의료 서식 파일을 사용하여 팀을 만드는 방법을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a3c39-108">Choose a method for creating teams with the Teams healthcare templates:</span></span>

| <span data-ttu-id="a3c39-109">Who</span><span class="sxs-lookup"><span data-stu-id="a3c39-109">Who</span></span> | <span data-ttu-id="a3c39-110">사용 방법:</span><span class="sxs-lookup"><span data-stu-id="a3c39-110">Method to use:</span></span> |
| ---- | --------- |
| <span data-ttu-id="a3c39-111">관리자 및 IT 전문가</span><span class="sxs-lookup"><span data-stu-id="a3c39-111">Admins and IT Professionals</span></span> | <span data-ttu-id="a3c39-112">[Teams 관리 센터를 사용](#use-the-teams-templates-in-the-teams-admin-center)하여 의료 팀 서식 파일을 기반으로 팀을 만드세요.</span><span class="sxs-lookup"><span data-stu-id="a3c39-112">[Use the Teams admin center](#use-the-teams-templates-in-the-teams-admin-center) to create teams based on the healthcare Teams templates.</span></span>|
| <span data-ttu-id="a3c39-113">개발자 및 시스템 통합자</span><span class="sxs-lookup"><span data-stu-id="a3c39-113">Developers and systems integrators</span></span> | <span data-ttu-id="a3c39-114">[Microsoft Graph를 사용](#use-the-teams-templates-with-the-microsoft-graph)하여 의료 팀 서식 파일을 기반으로 팀을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3c39-114">[Use the Microsoft Graph](#use-the-teams-templates-with-the-microsoft-graph) to create teams based on the healthcare Teams templates.</span></span> |

## <a name="use-the-teams-templates-in-the-teams-admin-center"></a><span data-ttu-id="a3c39-115">Teams 관리 센터에서 Teams 서식 파일 사용</span><span class="sxs-lookup"><span data-stu-id="a3c39-115">Use the Teams templates in the Teams admin center</span></span>

<span data-ttu-id="a3c39-116">Microsoft Teams 관리자는 Teams 서식 파일이 있는 Teams 관리 센터를 사용하여 팀을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3c39-116">Microsoft Teams admins can use the Teams admin center to create teams with the Teams templates.</span></span> <span data-ttu-id="a3c39-117">Microsoft는 현재 다양한 상황에서 사용할 수 있는 두 가지 일선 의료 서식 파일을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a3c39-117">We currently offer two first-party healthcare templates that you can use for a variety of situations.</span></span> <span data-ttu-id="a3c39-118">일반적인 팀 서식 파일에 대한 자세한 내용은 [관리 센터에서 Teams 서식 파일 시작하기](../../get-started-with-teams-templates-in-the-admin-console.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a3c39-118">To learn more about team templates in general, see [Get started with Teams templates in the admin center](../../get-started-with-teams-templates-in-the-admin-console.md).</span></span>

### <a name="collaborate-on-patient-care"></a><span data-ttu-id="a3c39-119">환자 관리 공동 작업</span><span class="sxs-lookup"><span data-stu-id="a3c39-119">Collaborate on patient care</span></span>

 <span data-ttu-id="a3c39-120">병동, 병실 또는 부서 내에서 의료 커뮤니케이션 및 공동 작업을 간소화합니다.</span><span class="sxs-lookup"><span data-stu-id="a3c39-120">Streamline healthcare communication and collaboration within a ward, pod, or department.</span></span> <span data-ttu-id="a3c39-121">이 서식 파일을 사용하여 병동의 환자 관리 및 운영 요구 사항을 용이하게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3c39-121">The template can be used to facilitate patient management and operational needs of a ward.</span></span>

| <span data-ttu-id="a3c39-122">기본 서식 파일 형식</span><span class="sxs-lookup"><span data-stu-id="a3c39-122">Base template type</span></span> |<span data-ttu-id="a3c39-123">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="a3c39-123">baseTemplateId</span></span>| <span data-ttu-id="a3c39-124">이 기본 서식 파일과 함께 사용할 수 있는 속성</span><span class="sxs-lookup"><span data-stu-id="a3c39-124">Properties that come with this base template</span></span> |
| ------------------ |---|----------------------------------------------------- |
| <span data-ttu-id="a3c39-125">환자 관리 공동 작업</span><span class="sxs-lookup"><span data-stu-id="a3c39-125">Collaborate on patient care</span></span> |`healthcareWard` | <span data-ttu-id="a3c39-126">채널</span><span class="sxs-lookup"><span data-stu-id="a3c39-126">Channels:</span></span><ul><li><span data-ttu-id="a3c39-127">일반</span><span class="sxs-lookup"><span data-stu-id="a3c39-127">General</span></span></li><li><span data-ttu-id="a3c39-128">공지 사항</span><span class="sxs-lookup"><span data-stu-id="a3c39-128">Announcements</span></span></li><li><span data-ttu-id="a3c39-129">장애 요소</span><span class="sxs-lookup"><span data-stu-id="a3c39-129">Huddles</span></span></li><li><span data-ttu-id="a3c39-130">라운드</span><span class="sxs-lookup"><span data-stu-id="a3c39-130">Rounds</span></span></li><li><span data-ttu-id="a3c39-131">직원</span><span class="sxs-lookup"><span data-stu-id="a3c39-131">Staffing</span></span></li><li><span data-ttu-id="a3c39-132">교육</span><span class="sxs-lookup"><span data-stu-id="a3c39-132">Training</span></span></li></ul> <span data-ttu-id="a3c39-133">앱:</span><span class="sxs-lookup"><span data-stu-id="a3c39-133">Apps:</span></span> <ul><li><span data-ttu-id="a3c39-134">Wiki</span><span class="sxs-lookup"><span data-stu-id="a3c39-134">Wiki</span></span></li><li><span data-ttu-id="a3c39-135">목록</span><span class="sxs-lookup"><span data-stu-id="a3c39-135">Lists</span></span></li></ul>|
||||

### <a name="hospital"></a><span data-ttu-id="a3c39-136">병원</span><span class="sxs-lookup"><span data-stu-id="a3c39-136">Hospital</span></span>

<span data-ttu-id="a3c39-137">병원 내에서 여러 병동, 병실, 부서 간 의사소통과 공동 작업을 간소화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3c39-137">Streamline communication and collaboration between multiple wards, pods, and departments within a hospital.</span></span> <span data-ttu-id="a3c39-138">이 템플릿은 병원 운영을 위한 기본 채널 집합을 포함하며, 자체 확장을 통해 관계, 특별 업무를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3c39-138">This template includes a set of base channels for hospital operations, and can be self-extended to include specialties, ad-hoc.</span></span>

| <span data-ttu-id="a3c39-139">기본 서식 파일 형식</span><span class="sxs-lookup"><span data-stu-id="a3c39-139">Base template type</span></span> |<span data-ttu-id="a3c39-140">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="a3c39-140">baseTemplateId</span></span> | <span data-ttu-id="a3c39-141">이 기본 서식 파일과 함께 사용할 수 있는 속성</span><span class="sxs-lookup"><span data-stu-id="a3c39-141">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="a3c39-142">병원</span><span class="sxs-lookup"><span data-stu-id="a3c39-142">Hospital</span></span>|`healthcareHospital`|<span data-ttu-id="a3c39-143">채널</span><span class="sxs-lookup"><span data-stu-id="a3c39-143">Channels:</span></span> <ul><li><span data-ttu-id="a3c39-144">일반</span><span class="sxs-lookup"><span data-stu-id="a3c39-144">General</span></span></li><li><span data-ttu-id="a3c39-145">공지 사항</span><span class="sxs-lookup"><span data-stu-id="a3c39-145">Announcements</span></span></li><li><span data-ttu-id="a3c39-146">규정 준수</span><span class="sxs-lookup"><span data-stu-id="a3c39-146">Compliance</span></span></li><li><span data-ttu-id="a3c39-147">보호</span><span class="sxs-lookup"><span data-stu-id="a3c39-147">Custodial</span></span></li><li><span data-ttu-id="a3c39-148">인적 리소스</span><span class="sxs-lookup"><span data-stu-id="a3c39-148">Human resources</span></span></li><li><span data-ttu-id="a3c39-149">약국</span><span class="sxs-lookup"><span data-stu-id="a3c39-149">Pharmacy</span></span></li></ul> <span data-ttu-id="a3c39-150">앱:</span><span class="sxs-lookup"><span data-stu-id="a3c39-150">Apps:</span></span> <ul><li><span data-ttu-id="a3c39-151">Wiki</span><span class="sxs-lookup"><span data-stu-id="a3c39-151">Wiki</span></span></li><li><span data-ttu-id="a3c39-152">목록</span><span class="sxs-lookup"><span data-stu-id="a3c39-152">Lists</span></span> </li></ul>|
||||


## <a name="use-the-teams-templates-with-the-microsoft-graph"></a><span data-ttu-id="a3c39-153">Microsoft Graph에서 Teams 서식 파일 사용</span><span class="sxs-lookup"><span data-stu-id="a3c39-153">Use the Teams templates with the Microsoft Graph</span></span>

<span data-ttu-id="a3c39-154">개발자는 Teams 서식 파일가 포함된 Microsoft Graph를 사용하여 팀을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3c39-154">Developers can use the Microsoft Graph to create teams with the Teams templates.</span></span> <span data-ttu-id="a3c39-155">Microsoft는 현재 다양한 상황에서 사용할 수 있는 두 가지 일선 의료 서식 파일을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a3c39-155">We currently offer two first-party healthcare templates that you can use for a variety of situations.</span></span> <span data-ttu-id="a3c39-156">일반적인 팀 서식 파일에 대한 자세한 내용은 [Teams 서식 파일 시작하기](../../get-started-with-teams-templates.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a3c39-156">To learn more about team templates in general, see [Get started with Teams templates](../../get-started-with-teams-templates.md).</span></span> <span data-ttu-id="a3c39-157">Teams 서식 파일과 Microsoft Graph에 대한 자세한 내용은 [Microsoft Teams API 개요](https://docs.microsoft.com/graph/teams-concept-overview?view=graph-rest-1.0) 및 [Teams 서식 파일 리소스 유형](https://docs.microsoft.com/graph/api/resources/teamstemplate?view=graph-rest-1.0)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a3c39-157">And for information about Teams templates and the Microsoft Graph, see [Microsoft Teams API overview](https://docs.microsoft.com/graph/teams-concept-overview?view=graph-rest-1.0) and [teamsTemplate resource type](https://docs.microsoft.com/graph/api/resources/teamstemplate?view=graph-rest-1.0).</span></span>

### <a name="ward-template"></a><span data-ttu-id="a3c39-158">병동 서식 파일</span><span class="sxs-lookup"><span data-stu-id="a3c39-158">Ward template</span></span>

<span data-ttu-id="a3c39-159">병동 서식 파일은 병동, 병실 또는 부서 내에서 의사소통과 공동 작업을 하기 위한 서식 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="a3c39-159">The ward template is meant for communication and collaboration within a ward, pod, or department.</span></span> <span data-ttu-id="a3c39-160">이 서식 파일을 사용하여 병동의 환자 관리 및 운영 요구 사항을 용이하게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3c39-160">The template can be used to facilitate patient management, as well as the operational needs of a ward.</span></span> <span data-ttu-id="a3c39-161">예를 들어, 병동 공지 사항을 *공지 사항* 채널에서 게시하고 *직원* 에서 교대 근무를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3c39-161">For example, ward announcements can be posted in the *Announcements* channel and shifts can be managed in *Staffing*.</span></span> <span data-ttu-id="a3c39-162">병동 작업을 간소화하고자 하는 경우, 이 서식 파일이 매우 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="a3c39-162">If you're looking to streamline your ward operations, then this template is for you.</span></span>

|<span data-ttu-id="a3c39-163">기본 서식 파일 형식</span><span class="sxs-lookup"><span data-stu-id="a3c39-163">Base Template Type</span></span> |<span data-ttu-id="a3c39-164">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="a3c39-164">baseTemplateId</span></span> |<span data-ttu-id="a3c39-165">기준 서식 파일 채널</span><span class="sxs-lookup"><span data-stu-id="a3c39-165">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="a3c39-166">의료 - 병동</span><span class="sxs-lookup"><span data-stu-id="a3c39-166">Healthcare - Ward</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | <span data-ttu-id="a3c39-167">공지 사항\*</span><span class="sxs-lookup"><span data-stu-id="a3c39-167">Announcements\*</span></span> <br> <span data-ttu-id="a3c39-168">장애 요소\*</span><span class="sxs-lookup"><span data-stu-id="a3c39-168">Huddles\*</span></span> <br> <span data-ttu-id="a3c39-169">라운드\*</span><span class="sxs-lookup"><span data-stu-id="a3c39-169">Rounds\*</span></span> <br> <span data-ttu-id="a3c39-170">직원\*</span><span class="sxs-lookup"><span data-stu-id="a3c39-170">Staffing\*</span></span> <br> <span data-ttu-id="a3c39-171">교육\*</span><span class="sxs-lookup"><span data-stu-id="a3c39-171">Training\*</span></span> |
|     | |         |

<span data-ttu-id="a3c39-172">\*자동 즐겨찾기 지정</span><span class="sxs-lookup"><span data-stu-id="a3c39-172">\* Auto-favorited</span></span>

### <a name="hospital-template"></a><span data-ttu-id="a3c39-173">병원 서식 파일</span><span class="sxs-lookup"><span data-stu-id="a3c39-173">Hospital template</span></span>

<span data-ttu-id="a3c39-174">이 병원 서식 파일은 병원 내에서 여러 병동, 병실, 부서 간 의사소통과 공동 작업을 수행하기 위해 제작되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a3c39-174">The hospital template is meant for communication and collaboration between multiple wards, pods, and departments within a hospital.</span></span> <span data-ttu-id="a3c39-175">이 서식 파일에는 *공지 사항*, *보호* 및 *약국* 을 비롯한 여러 운영 채널이 포함되어 있지만, 또한 원하는 대로 추가, 삭제 또는 편집할 수 있는 다양한 추가 부서 또는 전문 중심 채널로 템플릿을 확장하는 아래의 스크립트도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a3c39-175">Included in this template are several operational channels including *Announcements*, *Custodial*, and *Pharmacy*, but we also provide a script below which extends the template with a variety of additional department or specialty-centric channels that you can add to, delete from, or edit to your liking.</span></span> <span data-ttu-id="a3c39-176">예를 들어, *내분비학과* 가 있지만 *안과* 용 채널은 필요하지 않은 경우 스크립트를 조정하여 *내분비학과* 채널을 포함하고 *안과* 채널을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3c39-176">For example, if you have an *Endocrinology* department, but don't need a channel for *Ophthalmology*, then the script can be adapted to include an *Endocrinology* channel and remove the *Ophthalmology* channel.</span></span> <span data-ttu-id="a3c39-177">알림 포화 상태를 방지하기 위해 이러한 특수 또는 병동 모델의 채널은 자동 즐겨찾기하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a3c39-177">We recommend that these specialty or ward-modeled channels not be auto-favorited to avoid notification saturation.</span></span> <span data-ttu-id="a3c39-178">사용자는 일반적으로 관련이 있는 모든 채널을 즐겨찾습니다.</span><span class="sxs-lookup"><span data-stu-id="a3c39-178">Users generally favorite any channels that they find relevant.</span></span>

|<span data-ttu-id="a3c39-179">기본 서식 파일 형식</span><span class="sxs-lookup"><span data-stu-id="a3c39-179">Base Template Type</span></span> |<span data-ttu-id="a3c39-180">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="a3c39-180">baseTemplateId</span></span> |<span data-ttu-id="a3c39-181">기준 서식 파일 채널</span><span class="sxs-lookup"><span data-stu-id="a3c39-181">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="a3c39-182">의료 - 병원</span><span class="sxs-lookup"><span data-stu-id="a3c39-182">Healthcare - Hospital</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | <span data-ttu-id="a3c39-183">공지 사항\*</span><span class="sxs-lookup"><span data-stu-id="a3c39-183">Announcements\*</span></span> <br> <span data-ttu-id="a3c39-184">규정 준수\*</span><span class="sxs-lookup"><span data-stu-id="a3c39-184">Compliance\*</span></span> <br> <span data-ttu-id="a3c39-185">보호</span><span class="sxs-lookup"><span data-stu-id="a3c39-185">Custodial</span></span> <br> <span data-ttu-id="a3c39-186">인적 리소스</span><span class="sxs-lookup"><span data-stu-id="a3c39-186">Human Resources</span></span> <br> <span data-ttu-id="a3c39-187">약국</span><span class="sxs-lookup"><span data-stu-id="a3c39-187">Pharmacy</span></span> |
| | |  |

<span data-ttu-id="a3c39-188">\*자동 즐겨찾기 지정</span><span class="sxs-lookup"><span data-stu-id="a3c39-188">\* Auto-favorited</span></span> 

### <a name="how-to-use-first-party-templates"></a><span data-ttu-id="a3c39-189">기본 서식 파일을 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="a3c39-189">How to use first-party templates</span></span>

<span data-ttu-id="a3c39-190">이러한 서식 파일을 사용하려면 요청 본문의 'template@odata.bind' 속성을 '표준'에서 위의 TemplateID로 변경하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3c39-190">To use these templates, simply change the 'template@odata.bind' property in the request body from 'standard' to the TemplateIDs above.</span></span>  <span data-ttu-id="a3c39-191">Teams 서식 파일을 배포하는 방법에 대한 자세한 내용은 [팀을 만드는](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) 방법에 대한 Microsoft Graph 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a3c39-191">For more information on how to deploy Teams templates, see the Microsoft Graph article on how to [create a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="a3c39-192">서식 파일에서 채널은 일반 탭 아래에 자동으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="a3c39-192">The channels in the template will automatically be created under the General Tab.</span></span>

#### <a name="example-hospital-template-extension-script"></a><span data-ttu-id="a3c39-193">예: 병원 서식 파일 확장 스크립트</span><span class="sxs-lookup"><span data-stu-id="a3c39-193">Example: Hospital template extension script</span></span>

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

### <a name="related-topics"></a><span data-ttu-id="a3c39-194">관련 주제</span><span class="sxs-lookup"><span data-stu-id="a3c39-194">Related topics</span></span>

[<span data-ttu-id="a3c39-195">Teams 서식 파일 시작</span><span class="sxs-lookup"><span data-stu-id="a3c39-195">Get started with Teams templates</span></span>](../../get-started-with-teams-templates.md)

[<span data-ttu-id="a3c39-196">의료 조직을 위한 Teams 시작</span><span class="sxs-lookup"><span data-stu-id="a3c39-196">Get started with Teams for Healthcare organizations</span></span>](teams-in-hc.md)
