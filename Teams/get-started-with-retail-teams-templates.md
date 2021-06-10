---
title: 소매에서 팀 템플릿 시작
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
ms.collection:
- M365-collaboration
localization_priority: Normal
search.appverid: MET150
description: 팀 템플릿을 사용하여 미리 정의된 설정, 채널 및 미리 설치된 앱을 제공하여 소매업체 요구에 따라 디자인된 팀 구조를 만드는 방법을 알아보습니다.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: edc3b646af4577199b13a5803837625b8a9ea354
ms.sourcegitcommit: 36924dc54fe7b09607b07d7543fe7e39eb4d2483
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684556"
---
# <a name="create-a-team-using-retail-team-templates"></a><span data-ttu-id="44bfc-103">소매 팀 템플릿을 사용하여 팀 만들기</span><span class="sxs-lookup"><span data-stu-id="44bfc-103">Create a team using retail team templates</span></span>

<span data-ttu-id="44bfc-104">Microsoft 팀 템플릿을 사용하면 설정, 채널 및 미리 설치된 앱의 미리 정의된 템플릿을 제공하여 빠르고 쉽게 팀을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44bfc-104">Microsoft team templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="44bfc-105">팀 템플릿에는 소매업체 요구 사항을 중심으로 디자인된 팀 구조에 대한 미리 작성된 정의가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44bfc-105">Team templates have pre-built definitions of team structures designed around retailer needs.</span></span> <span data-ttu-id="44bfc-106">팀 템플릿을 사용하여 소매업체에 잘 작동하고 조직 전체에 배포하는 팀 유형을 빠르게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44bfc-106">You can use team templates to quickly create the types of teams that work well for retailers and deploy them across your organization.</span></span> <span data-ttu-id="44bfc-107">팀 템플릿을 확장하여 특정 조직 요구에 맞게 팀을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44bfc-107">You can also extend the team templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="44bfc-108">이 문서에서는 각 팀 템플릿을 소개하고 이를 사용하는 방법을 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="44bfc-108">In this article, we'll introduce each of the team templates and recommend how to use them.</span></span>

<span data-ttu-id="44bfc-109">이 문서는 판매점 조직 전체에 걸쳐 여러 Teams를 계획, 배포 및 관리하는 업무를 담당하는 사용자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="44bfc-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your retail organization.</span></span> <span data-ttu-id="44bfc-110">귀사는 이미 Teams 서비스를 구축했습니다.</span><span class="sxs-lookup"><span data-stu-id="44bfc-110">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="44bfc-111">Teams를 아직 배포하지 않은 경우 먼저 [Microsoft Teams를 배포하는 방법](./deploy-overview.md)을 읽어보세요.</span><span class="sxs-lookup"><span data-stu-id="44bfc-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](./deploy-overview.md).</span></span>

<span data-ttu-id="44bfc-112">일반적으로 팀 템플릿에 대한 자세한 내용은 팀 템플릿 시작 을 [참조합니다.](get-started-with-teams-templates.md)</span><span class="sxs-lookup"><span data-stu-id="44bfc-112">To learn more about team templates in general, refer to [Get started with team templates](get-started-with-teams-templates.md).</span></span>

| <span data-ttu-id="44bfc-113">Who</span><span class="sxs-lookup"><span data-stu-id="44bfc-113">Who</span></span> | <span data-ttu-id="44bfc-114">사용 방법:</span><span class="sxs-lookup"><span data-stu-id="44bfc-114">Method to use:</span></span> |
| ---- | --------- |
| <span data-ttu-id="44bfc-115">관리자 및 IT 전문가</span><span class="sxs-lookup"><span data-stu-id="44bfc-115">Admins and IT Professionals</span></span> | <span data-ttu-id="44bfc-116">[관리 Teams](#use-the-team-templates-in-the-teams-admin-center) 관리 센터를 사용하여 소매 팀 템플릿을 기반으로 팀을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="44bfc-116">[Use the Teams admin center](#use-the-team-templates-in-the-teams-admin-center) to create teams based on the retail team templates.</span></span>|
| <span data-ttu-id="44bfc-117">개발자 및 시스템 통합자</span><span class="sxs-lookup"><span data-stu-id="44bfc-117">Developers and systems integrators</span></span> | <span data-ttu-id="44bfc-118">[Microsoft Graph](#use-the-team-templates-with-the-microsoft-graph) 팀 템플릿을 기반으로 팀을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="44bfc-118">[Use the Microsoft Graph](#use-the-team-templates-with-the-microsoft-graph) to create teams based on the retail team templates.</span></span> |

## <a name="use-the-team-templates-in-the-teams-admin-center"></a><span data-ttu-id="44bfc-119">관리 센터에서 팀 Teams 사용</span><span class="sxs-lookup"><span data-stu-id="44bfc-119">Use the team templates in the Teams admin center</span></span>

### <a name="organize-a-store"></a><span data-ttu-id="44bfc-120">스토어 구성</span><span class="sxs-lookup"><span data-stu-id="44bfc-120">Organize a store</span></span>

<span data-ttu-id="44bfc-121">하나의 중앙 집중식 경험을 통해 판매점 직원들을 하나로 묶어 작업을 관리하고, 문서를 공유하며, 고객 문제를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="44bfc-121">Bring your retail employees together in one central experience to manage tasks, share documents and resolve customer issues.</span></span> <span data-ttu-id="44bfc-122">추가 애플리케이션을 통합하여 교대 근무 시작 및 종료 프로세스를 효율화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44bfc-122">Integrate additional applications to streamline shift start & end processes.</span></span>

| <span data-ttu-id="44bfc-123">기본 서식 파일 형식</span><span class="sxs-lookup"><span data-stu-id="44bfc-123">Base template type</span></span> |<span data-ttu-id="44bfc-124">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="44bfc-124">baseTemplateId</span></span> | <span data-ttu-id="44bfc-125">이 기본 서식 파일과 함께 사용할 수 있는 속성</span><span class="sxs-lookup"><span data-stu-id="44bfc-125">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="44bfc-126">스토어 구성</span><span class="sxs-lookup"><span data-stu-id="44bfc-126">Organize a store</span></span>|`retailStore`|<span data-ttu-id="44bfc-127">채널</span><span class="sxs-lookup"><span data-stu-id="44bfc-127">Channels:</span></span> <ul><li><span data-ttu-id="44bfc-128">일반</span><span class="sxs-lookup"><span data-stu-id="44bfc-128">General</span></span><li><span data-ttu-id="44bfc-129">교대 근무 전달</span><span class="sxs-lookup"><span data-stu-id="44bfc-129">Shift handoff</span></span></li><li><span data-ttu-id="44bfc-130">학습</span><span class="sxs-lookup"><span data-stu-id="44bfc-130">Learning</span></span></li></ul> <span data-ttu-id="44bfc-131">앱:</span><span class="sxs-lookup"><span data-stu-id="44bfc-131">Apps:</span></span> <ul><li><span data-ttu-id="44bfc-132">Wiki</span><span class="sxs-lookup"><span data-stu-id="44bfc-132">Wiki</span></span></li></ul>|
||||

### <a name="manager-collaboration"></a><span data-ttu-id="44bfc-133">관리자 공동 작업</span><span class="sxs-lookup"><span data-stu-id="44bfc-133">Manager Collaboration</span></span>

<span data-ttu-id="44bfc-134">관리자 공동 작업 템플릿은 관리자 집합이 상점/지역 등에서 공동 작업할 수 있는 팀을 만드는 데 이상적입니다. 예를 들어 조직에 지역이 있는 경우 캘리포니아 지역에 대한 관리자 공동 작업 팀을 만들고 해당 지역에 대한 지역 관리자와 함께 해당 지역에 있는 모든 저장소 관리자를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44bfc-134">The Manager Collaboration template is ideal for creating a team for a set of managers to collaborate across stores/regions, etc. For example, if your organization has regions, you might create a Manager Collaboration team for the California Region and include all the store managers in that region, along with the regional manager for that region.</span></span>

| <span data-ttu-id="44bfc-135">기본 서식 파일 형식</span><span class="sxs-lookup"><span data-stu-id="44bfc-135">Base template type</span></span>| <span data-ttu-id="44bfc-136">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="44bfc-136">baseTemplateId</span></span> | <span data-ttu-id="44bfc-137">이 기본 서식 파일과 함께 사용할 수 있는 속성</span><span class="sxs-lookup"><span data-stu-id="44bfc-137">Properties that come with this base template</span></span> |
| ------------------|- |----------------------------------------------------- |
|<span data-ttu-id="44bfc-138">소매 - 관리자 공동 작업</span><span class="sxs-lookup"><span data-stu-id="44bfc-138">Retail - manager collaboration</span></span>|`retailManagerCollaboration` |<span data-ttu-id="44bfc-139">채널</span><span class="sxs-lookup"><span data-stu-id="44bfc-139">Channels:</span></span> <ul><li><span data-ttu-id="44bfc-140">일반</span><span class="sxs-lookup"><span data-stu-id="44bfc-140">General</span></span><li><span data-ttu-id="44bfc-141">작업</span><span class="sxs-lookup"><span data-stu-id="44bfc-141">Operations</span></span></li><li><span data-ttu-id="44bfc-142">학습</span><span class="sxs-lookup"><span data-stu-id="44bfc-142">Learning</span></span></li></ul> <span data-ttu-id="44bfc-143">앱:</span><span class="sxs-lookup"><span data-stu-id="44bfc-143">Apps:</span></span> <ul><li><span data-ttu-id="44bfc-144">Wiki</span><span class="sxs-lookup"><span data-stu-id="44bfc-144">Wiki</span></span></li></ul>|
||||

## <a name="use-the-team-templates-with-the-microsoft-graph"></a><span data-ttu-id="44bfc-145">Microsoft 사용자와 함께 팀 템플릿을 Graph</span><span class="sxs-lookup"><span data-stu-id="44bfc-145">Use the team templates with the Microsoft Graph</span></span>

### <a name="store-template"></a><span data-ttu-id="44bfc-146">Store 서식 파일</span><span class="sxs-lookup"><span data-stu-id="44bfc-146">Store template</span></span>

<span data-ttu-id="44bfc-147">Store 서식 파일은 개별 판매점 위치를 대표하기 위해 팀을 만드는 경우에 이상적입니다.</span><span class="sxs-lookup"><span data-stu-id="44bfc-147">The Store template is ideal for creating a team to represent an individual retail store location.</span></span> <span data-ttu-id="44bfc-148">Store 서식 파일을 사용하여 조직의 각 판매점 위치별로 팀을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44bfc-148">Using the Store template, you can create a team for each retail store location in your organization.</span></span>

| <span data-ttu-id="44bfc-149">기본 서식 파일 형식</span><span class="sxs-lookup"><span data-stu-id="44bfc-149">Base template type</span></span> | <span data-ttu-id="44bfc-150">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="44bfc-150">baseTemplateId</span></span> | <span data-ttu-id="44bfc-151">이 기본 서식 파일과 함께 사용할 수 있는 속성</span><span class="sxs-lookup"><span data-stu-id="44bfc-151">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="44bfc-152">소매 -</span><span class="sxs-lookup"><span data-stu-id="44bfc-152">Retail -</span></span> <br><span data-ttu-id="44bfc-153">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="44bfc-153">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| <span data-ttu-id="44bfc-154">채널</span><span class="sxs-lookup"><span data-stu-id="44bfc-154">Channels</span></span> <ul><li><span data-ttu-id="44bfc-155">교대 근무 전달\*</span><span class="sxs-lookup"><span data-stu-id="44bfc-155">Shifts handoff\*</span></span></li><li><span data-ttu-id="44bfc-156">Learning\*</span><span class="sxs-lookup"><span data-stu-id="44bfc-156">Learning\*</span></span></li></ul><span data-ttu-id="44bfc-157">\*자동 즐겨찾기 채널</span><span class="sxs-lookup"><span data-stu-id="44bfc-157">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="44bfc-158">팀 속성</span><span class="sxs-lookup"><span data-stu-id="44bfc-158">Team properties</span></span> <ul><li><span data-ttu-id="44bfc-159">팀 표시 유형이 공개로 설정됨</span><span class="sxs-lookup"><span data-stu-id="44bfc-159">Team visibility set to Public</span></span></li></ul> <br><span data-ttu-id="44bfc-160">구성원 권한</span><span class="sxs-lookup"><span data-stu-id="44bfc-160">Member permissions</span></span> <ul><li><span data-ttu-id="44bfc-161">채널을 생성/업데이트/삭제할 수 없음</span><span class="sxs-lookup"><span data-stu-id="44bfc-161">Can't create/update/delete channels</span></span> </li><li><span data-ttu-id="44bfc-162">앱을 추가/제거할 수 없음</span><span class="sxs-lookup"><span data-stu-id="44bfc-162">Can't add/remove apps</span></span> </li><li><span data-ttu-id="44bfc-163">탭을 생성/업데이트/제거할 수 없음</span><span class="sxs-lookup"><span data-stu-id="44bfc-163">Can't create/update/remove tabs</span></span></li><li><span data-ttu-id="44bfc-164">커넥터를 생성/업데이트/제거할 수 없음</span><span class="sxs-lookup"><span data-stu-id="44bfc-164">Can't create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="44bfc-165">조직에 맞게 Store 서식 파일을 사용자 지정하기 위한 권장 방법:</span><span class="sxs-lookup"><span data-stu-id="44bfc-165">Recommended ways to customize the Store template for your organization:</span></span>

- <span data-ttu-id="44bfc-166">조직의 각 매장 내에 부서가 있는 경우 각 부서에 대해 채널을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="44bfc-166">If your organization has departments within each store, add a channel for each department.</span></span> <span data-ttu-id="44bfc-167">채널을 추가하면 부서 내에서 의사소통과 공동 작업을 용이하게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44bfc-167">Adding a channel facilitates communication and collaboration within the department.</span></span>

- <span data-ttu-id="44bfc-168">조직에 내부 웹 사이트(예: SharePoint 사이트)가 있는 경우 해당 웹 사이트를 관련 팀 채널의 탭으로 고정해 보세요.</span><span class="sxs-lookup"><span data-stu-id="44bfc-168">If your organization has any internal websites (for example, a SharePoint site), consider pinning them as tabs in the relevant team channel.</span></span> <span data-ttu-id="44bfc-169">지침은 팀 [템플릿](get-started-with-teams-templates.md) 시작을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="44bfc-169">Refer to [Get started with team templates](get-started-with-teams-templates.md) for instructions.</span></span>

### <a name="manager-collaboration-template"></a><span data-ttu-id="44bfc-170">관리자 공동 작업 서식 파일</span><span class="sxs-lookup"><span data-stu-id="44bfc-170">Manager Collaboration template</span></span>

<span data-ttu-id="44bfc-171">Manager 공동 작업 템플릿은 소매업체 요구 사항을 중심으로 디자인된 팀 템플릿 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="44bfc-171">The Manager Collaboration template is another one of the team templates designed around retailer needs.</span></span> <span data-ttu-id="44bfc-172">관리자 공동 작업 서식 파일은 매장/지역 등에서 공동 작업할 관리자 집합을 위한 팀을 만드는 데 이상적입니다.</span><span class="sxs-lookup"><span data-stu-id="44bfc-172">The Manager Collaboration template is ideal for creating a team for a set of managers to collaborate across stores/regions, and more.</span></span> <span data-ttu-id="44bfc-173">예를 들어 조직에 지역이 있는 경우 캘리포니아 지역에 대한 관리자 공동 작업 팀을 생성하고 해당 지역의 모든 스토어 매니저와 해당 지역의 지역 관리자를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44bfc-173">For example, if your organization has regions, you might create a Manager Collaboration team for the California Region and include all the store managers in that region, as well as the regional manager for that region.</span></span>

| <span data-ttu-id="44bfc-174">기본 서식 파일 형식</span><span class="sxs-lookup"><span data-stu-id="44bfc-174">Base template type</span></span> | <span data-ttu-id="44bfc-175">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="44bfc-175">baseTemplateId</span></span> | <span data-ttu-id="44bfc-176">이 기본 서식 파일과 함께 사용할 수 있는 속성</span><span class="sxs-lookup"><span data-stu-id="44bfc-176">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="44bfc-177">소매 -</span><span class="sxs-lookup"><span data-stu-id="44bfc-177">Retail -</span></span> <br><span data-ttu-id="44bfc-178">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="44bfc-178">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| <span data-ttu-id="44bfc-179">채널</span><span class="sxs-lookup"><span data-stu-id="44bfc-179">Channels</span></span> <ul><li><span data-ttu-id="44bfc-180">작업\*</span><span class="sxs-lookup"><span data-stu-id="44bfc-180">Operations\*</span></span></li><li><span data-ttu-id="44bfc-181">Learning\*</span><span class="sxs-lookup"><span data-stu-id="44bfc-181">Learning\*</span></span></li></ul><span data-ttu-id="44bfc-182">\*자동 즐겨찾기 채널</span><span class="sxs-lookup"><span data-stu-id="44bfc-182">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="44bfc-183">팀 속성</span><span class="sxs-lookup"><span data-stu-id="44bfc-183">Team properties</span></span> <ul><li><span data-ttu-id="44bfc-184">비공개로 설정된 팀 표시 유형</span><span class="sxs-lookup"><span data-stu-id="44bfc-184">Team visibility set to Private</span></span></li></ul> <br><span data-ttu-id="44bfc-185">구성원 권한</span><span class="sxs-lookup"><span data-stu-id="44bfc-185">Member permissions</span></span> <ul><li><span data-ttu-id="44bfc-186">채널을 생성/업데이트/삭제할 수 없음</span><span class="sxs-lookup"><span data-stu-id="44bfc-186">Can create/update/delete channels</span></span> </li><li><span data-ttu-id="44bfc-187">앱을 추가/제거할 수 있음</span><span class="sxs-lookup"><span data-stu-id="44bfc-187">Can add/remove apps</span></span> </li><li><span data-ttu-id="44bfc-188">탭을 생성/업데이트/제거</span><span class="sxs-lookup"><span data-stu-id="44bfc-188">Can create/update/remove tabs</span></span></li><li><span data-ttu-id="44bfc-189">커넥터 생성/업데이트/제거</span><span class="sxs-lookup"><span data-stu-id="44bfc-189">Can create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="44bfc-190">조직에 맞게 관리자 공동 작업 서식 파일을 사용자 지정하기 위한 권장 방법:</span><span class="sxs-lookup"><span data-stu-id="44bfc-190">Recommended ways to customize the Manager Collaboration template for your organization:</span></span>

- <span data-ttu-id="44bfc-191">조직에 관리자와 관련된 SharePoint 사이트와 같은 내부 웹 사이트가 있는 경우 해당 웹 사이트를 관련 팀 채널의 탭으로 고정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="44bfc-191">If your organization has any internal websites, such as a SharePoint site, that are relevant for managers, consider pinning them as tabs in a relevant team channel.</span></span> <span data-ttu-id="44bfc-192">지침은 Microsoft 팀 템플릿 설명서를 [살펴](get-started-with-teams-templates.md) 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44bfc-192">You can take a look at the [Microsoft team Template documentation](get-started-with-teams-templates.md) for instructions.</span></span>

## <a name="how-to-use-first-party-templates"></a><span data-ttu-id="44bfc-193">기본 서식 파일을 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="44bfc-193">How to use first-party templates</span></span>

<span data-ttu-id="44bfc-194">이러한 서식 파일을 사용하려면 요청 본문의 'template@odata.bind' 속성을 '표준'에서 위의 TemplateID로 변경하세요.</span><span class="sxs-lookup"><span data-stu-id="44bfc-194">To use these templates, change the 'template@odata.bind' property in the request body from 'standard' to the TemplateIDs above.</span></span>  <span data-ttu-id="44bfc-195">팀 템플릿을 배포하는 방법에 대한 자세한 내용은 팀을 만드는 Graph Microsoft Graph [문서를 참조하세요.](/graph/api/team-post?view=graph-rest-beta)</span><span class="sxs-lookup"><span data-stu-id="44bfc-195">For more information on how to deploy team templates, see the Microsoft Graph article on how to [create a Team](/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="44bfc-196">서식 파일에서 채널은 일반 탭 아래에 자동으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="44bfc-196">The channels in the template will automatically be created under the General Tab.</span></span>

### <a name="example-store-template-extension-script"></a><span data-ttu-id="44bfc-197">예: Store 서식 파일 확장 스크립트</span><span class="sxs-lookup"><span data-stu-id="44bfc-197">Example: Store template extension script</span></span>

``` PowerShell
{
  "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('retailStore')",
  "DisplayName": "Contoso Store",
  "Description": "Team for all staff in Contoso Store",
  "Channels": [
    {
      "displayName": "Additional store channel",
      "IsFavoriteByDefault": false
    }
  ]
}
```
