---
title: 정품에서 팀 서식 파일 시작
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/11/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
localization_priority: Normal
search.appverid: MET150
description: 팀 서식 파일을 사용 하 여 소매업 자의 요구 사항에 맞게 디자인 된 팀 구조를 만드는 방법을 알아봅니다.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: e463061dca0633480124bbe91fb2e8e6f9f926f6
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "36181643"
---
# <a name="get-started-with-teams-templates-in-retail"></a><span data-ttu-id="4243a-103">정품에서 팀 서식 파일 시작</span><span class="sxs-lookup"><span data-stu-id="4243a-103">Get started with Teams templates in retail</span></span> 

<span data-ttu-id="4243a-104">팀 서식 파일을 사용 하면 미리 정의 된 서식 파일 (설정, 채널 및 사전 설치 된 앱)을 제공 하 여 빠르고 쉽게 팀을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4243a-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="4243a-105">팀 템플릿에는 소매점의 요구 사항에 따라 디자인 된 팀 구조의 정의가 미리 작성 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4243a-105">Teams templates have pre-built definitions of team structures designed around retailer needs.</span></span> <span data-ttu-id="4243a-106">팀 서식 파일을 사용 하 여 소매 업체에 잘 맞는 팀 유형을 신속 하 게 만들고 조직 내에서 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4243a-106">You can use Teams templates to quickly create the types of teams that work well for retailers and deploy them across your organization.</span></span> <span data-ttu-id="4243a-107">팀 템플릿을 확장 하 여 특정 조직의 요구 사항에 맞게 조정 된 팀을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4243a-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="4243a-108">이 문서에서는 각 팀 서식 파일과이를 사용 하는 방법을 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="4243a-108">In this article, we will introduce each of the Teams templates and how we recommend using them.</span></span>

<span data-ttu-id="4243a-109">본 문서는 소매점에서 여러 팀을 계획, 배포 및 관리 해야 하는 경우에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="4243a-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your retail organization.</span></span>

<span data-ttu-id="4243a-110">일반적으로 팀 서식 파일에 대 한 자세한 내용은 [팀 서식 파일 시작](get-started-with-teams-templates.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4243a-110">To learn more about team templates in general, please refer to [Get started with Teams templates](get-started-with-teams-templates.md).</span></span>

## <a name="store-template"></a><span data-ttu-id="4243a-111">스토어 서식 파일</span><span class="sxs-lookup"><span data-stu-id="4243a-111">Store template</span></span>

<span data-ttu-id="4243a-112">스토어 서식 파일은 개별 소매 상점 위치를 나타내는 팀을 만드는 데 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="4243a-112">The Store template is ideal for creating a team to represent an individual retail store location.</span></span> <span data-ttu-id="4243a-113">스토어 서식 파일을 사용 하 여 조직의 각 소매점 위치에 대 한 팀을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4243a-113">Using the Store template, you can create a team for each retail store location in your organization.</span></span>

| <span data-ttu-id="4243a-114">기본 서식 파일 형식</span><span class="sxs-lookup"><span data-stu-id="4243a-114">Base template type</span></span> | <span data-ttu-id="4243a-115">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="4243a-115">baseTemplateId</span></span> | <span data-ttu-id="4243a-116">이 기본 서식 파일에 포함 된 속성</span><span class="sxs-lookup"><span data-stu-id="4243a-116">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="4243a-117">Retail</span><span class="sxs-lookup"><span data-stu-id="4243a-117">Retail -</span></span> <br><span data-ttu-id="4243a-118">스토어</span><span class="sxs-lookup"><span data-stu-id="4243a-118">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| <span data-ttu-id="4243a-119">채널</span><span class="sxs-lookup"><span data-stu-id="4243a-119">Channels</span></span> <ul><li><span data-ttu-id="4243a-120">이송 이동\*</span><span class="sxs-lookup"><span data-stu-id="4243a-120">Shifts handoff\*</span></span></li><li><span data-ttu-id="4243a-121">배웁니다\*</span><span class="sxs-lookup"><span data-stu-id="4243a-121">Learning\*</span></span></li></ul><span data-ttu-id="4243a-122">\*자동 즐겨찾기에 채널</span><span class="sxs-lookup"><span data-stu-id="4243a-122">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="4243a-123">팀 속성</span><span class="sxs-lookup"><span data-stu-id="4243a-123">Team properties</span></span> <ul><li><span data-ttu-id="4243a-124">팀 가시성을 공개로 설정</span><span class="sxs-lookup"><span data-stu-id="4243a-124">Team visibility set to Public</span></span></li></ul> <br><span data-ttu-id="4243a-125">회원 사용 권한</span><span class="sxs-lookup"><span data-stu-id="4243a-125">Member permissions</span></span> <ul><li><span data-ttu-id="4243a-126">채널을 만들거나 업데이트 하거나 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4243a-126">Cannot create/update/delete channels</span></span> </li><li><span data-ttu-id="4243a-127">앱을 추가/제거할 수 없음</span><span class="sxs-lookup"><span data-stu-id="4243a-127">Cannot add/remove apps</span></span> </li><li><span data-ttu-id="4243a-128">탭을 만들거나 업데이트 하거나 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4243a-128">Cannot create/update/remove tabs</span></span></li><li><span data-ttu-id="4243a-129">커넥터를 만들거나 업데이트 하거나 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4243a-129">Cannot create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="4243a-130">조직의 스토어 서식 파일을 사용자 지정 하는 권장 방법:</span><span class="sxs-lookup"><span data-stu-id="4243a-130">Recommended ways to customize the Store template for your organization:</span></span>

- <span data-ttu-id="4243a-131">조직의 부서가 각 매장 내에 있는 경우 각 부서에 대 한 채널을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="4243a-131">If your organization has departments within each store, add a channel for each department.</span></span> <span data-ttu-id="4243a-132">이렇게 하면 부서 내에서 커뮤니케이션 및 공동 작업이 용이해 집니다.</span><span class="sxs-lookup"><span data-stu-id="4243a-132">This will facilitate communication and collaboration within the department.</span></span>

- <span data-ttu-id="4243a-133">조직에 내부 웹 사이트 (예: SharePoint 사이트)가 있는 경우 관련 팀 채널에서 탭으로 고정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4243a-133">If your organization has any internal websites (for example, a SharePoint site), consider pinning them as tabs in the relevant team channel.</span></span> <span data-ttu-id="4243a-134">자세한 내용은 [팀 템플릿 시작](get-started-with-teams-templates.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4243a-134">Refer to [Get started with Teams templates](get-started-with-teams-templates.md) for instructions.</span></span>

## <a name="manager-collaboration-template"></a><span data-ttu-id="4243a-135">관리자 공동 작업 서식 파일</span><span class="sxs-lookup"><span data-stu-id="4243a-135">Manager Collaboration template</span></span>

<span data-ttu-id="4243a-136">관리자 공동 작업 서식 파일은 소매점 필요에 따라 디자인 된 팀 템플릿 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="4243a-136">The Manager Collaboration template is another one of the Teams templates designed around retailer needs.</span></span> <span data-ttu-id="4243a-137">관리자 공동 작업 템플릿은 저장소/지역에서 공동 작업 하는 관리자 집합을 위한 팀을 만드는 데 적합 합니다. 예를 들어 조직에 지역이 있는 경우 캘리포니아 지역에 대 한 관리자 공동 작업 팀을 만들고 해당 지역의 모든 스토어 관리자와 해당 지역의 지역 관리자를 함께 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4243a-137">The Manager Collaboration template is ideal for creating a team for a set of managers to collaborate across stores/regions, etc. For example, if your organization has regions, you might create a Manager Collaboration team for the California Region and include all the store managers in that region, as well as the regional manager for that region.</span></span>

| <span data-ttu-id="4243a-138">기본 서식 파일 형식</span><span class="sxs-lookup"><span data-stu-id="4243a-138">Base template type</span></span> | <span data-ttu-id="4243a-139">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="4243a-139">baseTemplateId</span></span> | <span data-ttu-id="4243a-140">이 기본 서식 파일에 포함 된 속성</span><span class="sxs-lookup"><span data-stu-id="4243a-140">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="4243a-141">Retail</span><span class="sxs-lookup"><span data-stu-id="4243a-141">Retail -</span></span> <br><span data-ttu-id="4243a-142">스토어</span><span class="sxs-lookup"><span data-stu-id="4243a-142">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| <span data-ttu-id="4243a-143">채널</span><span class="sxs-lookup"><span data-stu-id="4243a-143">Channels</span></span> <ul><li><span data-ttu-id="4243a-144">작업\*</span><span class="sxs-lookup"><span data-stu-id="4243a-144">Operations\*</span></span></li><li><span data-ttu-id="4243a-145">배웁니다\*</span><span class="sxs-lookup"><span data-stu-id="4243a-145">Learning\*</span></span></li></ul><span data-ttu-id="4243a-146">\*자동 즐겨찾기에 채널</span><span class="sxs-lookup"><span data-stu-id="4243a-146">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="4243a-147">팀 속성</span><span class="sxs-lookup"><span data-stu-id="4243a-147">Team properties</span></span> <ul><li><span data-ttu-id="4243a-148">팀 표시 유형을 비공개로 설정</span><span class="sxs-lookup"><span data-stu-id="4243a-148">Team visibility set to Private</span></span></li></ul> <br><span data-ttu-id="4243a-149">회원 사용 권한</span><span class="sxs-lookup"><span data-stu-id="4243a-149">Member permissions</span></span> <ul><li><span data-ttu-id="4243a-150">채널을 만들거나 업데이트 하거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4243a-150">Can create/update/delete channels</span></span> </li><li><span data-ttu-id="4243a-151">앱을 추가/제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4243a-151">Can add/remove apps</span></span> </li><li><span data-ttu-id="4243a-152">탭을 만들거나 업데이트/제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4243a-152">Can create/update/remove tabs</span></span></li><li><span data-ttu-id="4243a-153">커넥터를 만들거나 업데이트 하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4243a-153">Can create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="4243a-154">조직의 관리자 공동 작업 서식 파일을 사용자 지정 하는 권장 방법:</span><span class="sxs-lookup"><span data-stu-id="4243a-154">Recommended ways to customize the Manager Collaboration template for your organization:</span></span>

- <span data-ttu-id="4243a-155">조직에 관리자와 관련 된 내부 웹 사이트 (예: SharePoint 사이트)가 있는 경우 관련 팀 채널에서 탭으로 고정 하는 것이 좋습니다 (지침에 대 한 [](get-started-with-teams-templates.md) 설명서 참조).</span><span class="sxs-lookup"><span data-stu-id="4243a-155">If your organization has any internal websites (for example, a SharePoint site) that are relevant for managers, consider pinning them as tabs in a relevant team channel (refer to documentation [here](get-started-with-teams-templates.md) for instructions).</span></span>