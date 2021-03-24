---
title: 관리 센터를 사용하여 Teams 재무 템플릿 시작
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
ms.collection:
- M365-collaboration
localization_priority: Normal
search.appverid: MET150
description: 사용하는 방법에 대해 자세히 알아보아야 합니다. 관리 센터를 사용하여 미리 정의된 설정, 채널 및 미리 설치된 앱을 제공하여 재무 요구에 따라 설계된 팀 구조를 만드는 Teams 템플릿입니다.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0fd7c6fa61f7c929e198440b574b6bb10db7370d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092476"
---
# <a name="use-teams-financial-templates-in-the-admin-center"></a><span data-ttu-id="23dae-104">관리 센터에서 Teams 재무 템플릿 사용</span><span class="sxs-lookup"><span data-stu-id="23dae-104">Use Teams financial templates in the admin center</span></span>

<span data-ttu-id="23dae-105">Teams 서식 파일을 사용하면 미리 정의된 설정, 채널 및 미리 설치된 앱 서식 파일을 제공하여 팀을 쉽고 빠르게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23dae-105">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="23dae-106">Teams 템플릿에는 재정적 요구 사항을 중심으로 설계된 팀 구조에 대한 미리 작성된 정의가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23dae-106">Teams templates have pre-built definitions of team structures designed around financial needs.</span></span> <span data-ttu-id="23dae-107">Teams 서식 파일을 확장하여 특정 조직 요구에 맞는 팀을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23dae-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="23dae-108">이 문서에서는 각 Teams 서식 파일을 소개하고 사용 방법을 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="23dae-108">In this article, we'll introduce each of the Teams templates and recommend how to use them.</span></span>

<span data-ttu-id="23dae-109">이 문서는 재무 조직 전반에 걸쳐 여러 팀을 계획, 배포 및 관리할 책임이 있는 경우를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="23dae-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your financial organization.</span></span> <span data-ttu-id="23dae-110">귀사는 이미 Teams 서비스를 구축했습니다.</span><span class="sxs-lookup"><span data-stu-id="23dae-110">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="23dae-111">Teams를 아직 배포하지 않은 경우 먼저 [Microsoft Teams를 배포하는 방법](./deploy-overview.md)을 읽어보세요.</span><span class="sxs-lookup"><span data-stu-id="23dae-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](./deploy-overview.md).</span></span>

<span data-ttu-id="23dae-112">일반적인 팀 서식 파일에 대한 자세한 내용은 [Teams 서식 파일 시작하기](get-started-with-teams-templates-in-the-admin-console.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="23dae-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="global-crisis-or-event"></a><span data-ttu-id="23dae-113">글로벌 위기 또는 이벤트</span><span class="sxs-lookup"><span data-stu-id="23dae-113">Global crisis or event</span></span>

<span data-ttu-id="23dae-114">비즈니스 단위에서 위기 팀에 대한 공동 작업을 중앙 집중화하고 비즈니스 연속성 계획을 만들고, 원격 작업 팁을 공유하고, 고객 통신을 추적하고, 공지 및 뉴스를 사용하여 모든 사람을 루프에 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23dae-114">Centralize collaboration for your crisis team across business units and help create business continuity plans, share remote working tips, track customer communications, and keep everyone in the loop with announcements and news.</span></span>

| <span data-ttu-id="23dae-115">기본 서식 파일 형식</span><span class="sxs-lookup"><span data-stu-id="23dae-115">Base template type</span></span>|<span data-ttu-id="23dae-116">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="23dae-116">baseTemplateId</span></span> | <span data-ttu-id="23dae-117">이 기본 서식 파일과 함께 사용할 수 있는 속성</span><span class="sxs-lookup"><span data-stu-id="23dae-117">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
| <span data-ttu-id="23dae-118">글로벌 위기 또는 이벤트에 대한 공동 작업</span><span class="sxs-lookup"><span data-stu-id="23dae-118">Collaborate on global crisis or event</span></span>|`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent` |<span data-ttu-id="23dae-119">채널</span><span class="sxs-lookup"><span data-stu-id="23dae-119">Channels:</span></span> <ul><li><span data-ttu-id="23dae-120">일반</span><span class="sxs-lookup"><span data-stu-id="23dae-120">General</span></span><li><span data-ttu-id="23dae-121">공지 사항</span><span class="sxs-lookup"><span data-stu-id="23dae-121">Announcements</span></span></li><li><span data-ttu-id="23dae-122">세계 뉴스</span><span class="sxs-lookup"><span data-stu-id="23dae-122">World news</span></span></li><li><span data-ttu-id="23dae-123">비즈니스 연속성</span><span class="sxs-lookup"><span data-stu-id="23dae-123">Business continuity</span></span></li><li><span data-ttu-id="23dae-124">원격 작업</span><span class="sxs-lookup"><span data-stu-id="23dae-124">Remote working</span></span></li><li><span data-ttu-id="23dae-125">내부 커미스</span><span class="sxs-lookup"><span data-stu-id="23dae-125">Internal comms</span></span></li><li><span data-ttu-id="23dae-126">외부 커미스</span><span class="sxs-lookup"><span data-stu-id="23dae-126">External comms</span></span></li><li><span data-ttu-id="23dae-127">승인 요청</span><span class="sxs-lookup"><span data-stu-id="23dae-127">Approvals request</span></span></li><li><span data-ttu-id="23dae-128">고객 불만</span><span class="sxs-lookup"><span data-stu-id="23dae-128">Customer complaints</span></span></li><li><span data-ttu-id="23dae-129">Kudos</span><span class="sxs-lookup"><span data-stu-id="23dae-129">Kudos</span></span></li><li><span data-ttu-id="23dae-130">임원 업데이트</span><span class="sxs-lookup"><span data-stu-id="23dae-130">Executive update</span></span></li></ul><span data-ttu-id="23dae-131">앱:</span><span class="sxs-lookup"><span data-stu-id="23dae-131">Apps:</span></span> <ul><li><span data-ttu-id="23dae-132">찬양</span><span class="sxs-lookup"><span data-stu-id="23dae-132">Praise</span></span></li><li><span data-ttu-id="23dae-133">Wiki</span><span class="sxs-lookup"><span data-stu-id="23dae-133">Wiki</span></span></li><li><span data-ttu-id="23dae-134">웹 사이트</span><span class="sxs-lookup"><span data-stu-id="23dae-134">Website</span></span></li><li><span data-ttu-id="23dae-135">Planner</span><span class="sxs-lookup"><span data-stu-id="23dae-135">Planner</span></span></li></ul>|
||||

## <a name="collaborate-within-a-bank-branch"></a><span data-ttu-id="23dae-136">은행 지점 내에서 공동 작업</span><span class="sxs-lookup"><span data-stu-id="23dae-136">Collaborate within a bank branch</span></span>

<span data-ttu-id="23dae-137">Huddles, 고객 모임, 모기지 공동 작업과 같은 비즈니스 프로세스에서 은행 지점 직원에 대한 공동 작업을 중앙 집중화하고 공지사항 및 Kudos를 사용하여 모든 사람을 루프에 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="23dae-137">Centralize collaboration for your bank branch employees across Huddles, Customer Meetings, Business Processes such as Mortgage Collaboration, and keep everyone in the loop with Announcements and Kudos.</span></span>

| <span data-ttu-id="23dae-138">기본 서식 파일 형식</span><span class="sxs-lookup"><span data-stu-id="23dae-138">Base template type</span></span> |<span data-ttu-id="23dae-139">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="23dae-139">baseTemplateId</span></span>| <span data-ttu-id="23dae-140">이 기본 서식 파일과 함께 사용할 수 있는 속성</span><span class="sxs-lookup"><span data-stu-id="23dae-140">Properties that come with this base template</span></span> |
| ------------------ |--|----------------------------------------------------- |
|<span data-ttu-id="23dae-141">은행 지점 내에서 공동 작업</span><span class="sxs-lookup"><span data-stu-id="23dae-141">Collaborate within a bank branch</span></span>|`com.microsoft.teams.template.CollaborateWithinABankBranch` |<span data-ttu-id="23dae-142">채널</span><span class="sxs-lookup"><span data-stu-id="23dae-142">Channels:</span></span> <ul><li><span data-ttu-id="23dae-143">일반</span><span class="sxs-lookup"><span data-stu-id="23dae-143">General</span></span><li><span data-ttu-id="23dae-144">공지 사항</span><span class="sxs-lookup"><span data-stu-id="23dae-144">Announcements</span></span></li><li><span data-ttu-id="23dae-145">장애 요소</span><span class="sxs-lookup"><span data-stu-id="23dae-145">Huddles</span></span></li><li><span data-ttu-id="23dae-146">고객 모임</span><span class="sxs-lookup"><span data-stu-id="23dae-146">Customer meetings</span></span></li><li><span data-ttu-id="23dae-147">승인 요청</span><span class="sxs-lookup"><span data-stu-id="23dae-147">Approvals Request</span></span></li><li><span data-ttu-id="23dae-148">코칭</span><span class="sxs-lookup"><span data-stu-id="23dae-148">Coaching</span></span></li><li><span data-ttu-id="23dae-149">기술 개발</span><span class="sxs-lookup"><span data-stu-id="23dae-149">Skills development</span></span></li><li><span data-ttu-id="23dae-150">대출 처리</span><span class="sxs-lookup"><span data-stu-id="23dae-150">Loan processing</span></span></li><li><span data-ttu-id="23dae-151">고객 불만</span><span class="sxs-lookup"><span data-stu-id="23dae-151">Customer complaints</span></span></li><li><span data-ttu-id="23dae-152">Kudos</span><span class="sxs-lookup"><span data-stu-id="23dae-152">Kudos</span></span></li><li><span data-ttu-id="23dae-153">재미있는 물건</span><span class="sxs-lookup"><span data-stu-id="23dae-153">Fun stuff</span></span></li><li><span data-ttu-id="23dae-154">규정 준수</span><span class="sxs-lookup"><span data-stu-id="23dae-154">Compliance</span></span></li></ul><span data-ttu-id="23dae-155">앱:</span><span class="sxs-lookup"><span data-stu-id="23dae-155">Apps:</span></span><ul><li><span data-ttu-id="23dae-156">찬양</span><span class="sxs-lookup"><span data-stu-id="23dae-156">Praise</span></span></li></ul>|
||||