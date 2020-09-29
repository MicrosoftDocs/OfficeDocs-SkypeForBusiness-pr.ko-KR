---
title: 관리 콘솔을 사용 하 여 팀 재무 템플릿을 시작 하세요.
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
description: 사용 방법에 대해 알아보세요. 관리 콘솔을 사용 하 여 미리 정의 된 설정, 채널 및 사전 설치 앱을 제공 하 여 재무 요구 사항에 맞게 디자인 한 팀 구조를 만들 수 있습니다.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8273e63213b6a0c3d99d6ef66cb778a2541c0327
ms.sourcegitcommit: 340c2f432b78af4e78b21056af56c6421627045d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294414"
---
# <a name="use-teams-financial-templates-in-the-admin-console"></a><span data-ttu-id="c5292-104">관리 콘솔에서 팀 재무 서식 파일 사용</span><span class="sxs-lookup"><span data-stu-id="c5292-104">Use Teams financial templates in the admin console</span></span>

<span data-ttu-id="c5292-105">팀 서식 파일을 사용 하면 미리 정의 된 서식 파일 (설정, 채널 및 사전 설치 된 앱)을 제공 하 여 빠르고 쉽게 팀을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5292-105">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="c5292-106">팀 템플릿에는 재무 요구에 따라 디자인 된 팀 구조 정의가 미리 작성 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5292-106">Teams templates have pre-built definitions of team structures designed around financial needs.</span></span> <span data-ttu-id="c5292-107">팀 템플릿을 확장 하 여 특정 조직의 요구 사항에 맞게 조정 된 팀을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5292-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="c5292-108">이 문서에서는 각 팀 템플릿을 소개 하 고 사용 방법을 추천 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5292-108">In this article, we'll introduce each of the Teams templates and recommend how to use them.</span></span>

<span data-ttu-id="c5292-109">이 문서에서는 재무 조직에서 여러 팀을 계획, 배포 및 관리 하는 책임이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5292-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your financial organization.</span></span> <span data-ttu-id="c5292-110">조직에 이미 팀 서비스를 배포 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c5292-110">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="c5292-111">아직 팀을 롤아웃하기 않은 경우 먼저 [Microsoft 팀을 배포 하는 방법을](How-to-roll-out-teams.md)읽어 보세요.</span><span class="sxs-lookup"><span data-stu-id="c5292-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="c5292-112">일반적으로 팀 서식 파일에 대 한 자세한 내용은 [팀 서식 파일 시작](get-started-with-teams-templates-in-the-admin-console.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c5292-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="global-crisis-or-event"></a><span data-ttu-id="c5292-113">전역 위기 또는 이벤트</span><span class="sxs-lookup"><span data-stu-id="c5292-113">Global crisis or event</span></span>

<span data-ttu-id="c5292-114">비즈니스 단위에서 위기 팀을 위한 공동 작업을 수행 하 고, 비즈니스 연속성 계획을 만들고, 원격 작업 팁을 공유 하 고, 고객 통신을 추적 하 고, 모든 사용자에 게 공지 사항 및 뉴스를 유지 하는 데</span><span class="sxs-lookup"><span data-stu-id="c5292-114">Centralize collaboration for your crisis team across business units and help create business continuity plans, share remote working tips, track customer communications, and keep everyone in the loop with announcements and news.</span></span>

| <span data-ttu-id="c5292-115">기본 서식 파일 형식</span><span class="sxs-lookup"><span data-stu-id="c5292-115">Base template type</span></span>|<span data-ttu-id="c5292-116">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="c5292-116">baseTemplateId</span></span> | <span data-ttu-id="c5292-117">이 기본 서식 파일에 포함 된 속성</span><span class="sxs-lookup"><span data-stu-id="c5292-117">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
| <span data-ttu-id="c5292-118">전역 위기 또는 이벤트에 대 한 공동 작업</span><span class="sxs-lookup"><span data-stu-id="c5292-118">Collaborate on global crisis or event</span></span>|`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent` |<span data-ttu-id="c5292-119">채널</span><span class="sxs-lookup"><span data-stu-id="c5292-119">Channels:</span></span> <ul><li><span data-ttu-id="c5292-120">일반</span><span class="sxs-lookup"><span data-stu-id="c5292-120">General</span></span><li><span data-ttu-id="c5292-121">알림에서</span><span class="sxs-lookup"><span data-stu-id="c5292-121">Announcements</span></span></li><li><span data-ttu-id="c5292-122">월드 뉴스</span><span class="sxs-lookup"><span data-stu-id="c5292-122">World news</span></span></li><li><span data-ttu-id="c5292-123">비즈니스 연속성</span><span class="sxs-lookup"><span data-stu-id="c5292-123">Business continuity</span></span></li><li><span data-ttu-id="c5292-124">원격 작업</span><span class="sxs-lookup"><span data-stu-id="c5292-124">Remote working</span></span></li><li><span data-ttu-id="c5292-125">내부 주석 s</span><span class="sxs-lookup"><span data-stu-id="c5292-125">Internal comms</span></span></li><li><span data-ttu-id="c5292-126">외부 대화 s</span><span class="sxs-lookup"><span data-stu-id="c5292-126">External comms</span></span></li><li><span data-ttu-id="c5292-127">고객 불만</span><span class="sxs-lookup"><span data-stu-id="c5292-127">Customer complaints</span></span></li><li><span data-ttu-id="c5292-128">보너스</span><span class="sxs-lookup"><span data-stu-id="c5292-128">Kudos</span></span></li><li><span data-ttu-id="c5292-129">임원 업데이트</span><span class="sxs-lookup"><span data-stu-id="c5292-129">Executive update</span></span></li></ul><span data-ttu-id="c5292-130">들</span><span class="sxs-lookup"><span data-stu-id="c5292-130">Apps:</span></span> <ul><li><span data-ttu-id="c5292-131">칭찬</span><span class="sxs-lookup"><span data-stu-id="c5292-131">Praise</span></span></li><li><span data-ttu-id="c5292-132">키</span><span class="sxs-lookup"><span data-stu-id="c5292-132">Wiki</span></span></li><li><span data-ttu-id="c5292-133">웹 사이트</span><span class="sxs-lookup"><span data-stu-id="c5292-133">Website</span></span></li></ul>|
||||

## <a name="collaborate-within-a-bank-branch"></a><span data-ttu-id="c5292-134">은행 지사 내에서 공동 작업</span><span class="sxs-lookup"><span data-stu-id="c5292-134">Collaborate within a bank branch</span></span>

<span data-ttu-id="c5292-135">은행에 대 한 공동 작업은 Huddles, 고객 모임, 담보 대출 공동 작업 등의 비즈니스 프로세스를 통해 직원 들에 게 집중 하 고 모든 사용자에 게 공지 및 Kudos를 포함 하도록 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5292-135">Centralize collaboration for your bank branch employees across Huddles, Customer Meetings, Business Processes such as Mortgage Collaboration, and keep everyone in the loop with Announcements and Kudos.</span></span>

| <span data-ttu-id="c5292-136">기본 서식 파일 형식</span><span class="sxs-lookup"><span data-stu-id="c5292-136">Base template type</span></span> |<span data-ttu-id="c5292-137">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="c5292-137">baseTemplateId</span></span>| <span data-ttu-id="c5292-138">이 기본 서식 파일에 포함 된 속성</span><span class="sxs-lookup"><span data-stu-id="c5292-138">Properties that come with this base template</span></span> |
| ------------------ |--|----------------------------------------------------- |
|<span data-ttu-id="c5292-139">은행 지사 내에서 공동 작업</span><span class="sxs-lookup"><span data-stu-id="c5292-139">Collaborate within a bank branch</span></span>|`com.microsoft.teams.template.CollaborateWithinABankBranch` |<span data-ttu-id="c5292-140">채널</span><span class="sxs-lookup"><span data-stu-id="c5292-140">Channels:</span></span> <ul><li><span data-ttu-id="c5292-141">일반</span><span class="sxs-lookup"><span data-stu-id="c5292-141">General</span></span><li><span data-ttu-id="c5292-142">알림에서</span><span class="sxs-lookup"><span data-stu-id="c5292-142">Announcements</span></span></li><li><span data-ttu-id="c5292-143">Huddles</span><span class="sxs-lookup"><span data-stu-id="c5292-143">Huddles</span></span></li><li><span data-ttu-id="c5292-144">고객 모임</span><span class="sxs-lookup"><span data-stu-id="c5292-144">Customer meetings</span></span></li><li><span data-ttu-id="c5292-145">코칭</span><span class="sxs-lookup"><span data-stu-id="c5292-145">Coaching</span></span></li><li><span data-ttu-id="c5292-146">기술 개발</span><span class="sxs-lookup"><span data-stu-id="c5292-146">Skills development</span></span></li><li><span data-ttu-id="c5292-147">대출 처리</span><span class="sxs-lookup"><span data-stu-id="c5292-147">Loan processing</span></span></li><li><span data-ttu-id="c5292-148">고객 불만</span><span class="sxs-lookup"><span data-stu-id="c5292-148">Customer complaints</span></span></li><li><span data-ttu-id="c5292-149">보너스</span><span class="sxs-lookup"><span data-stu-id="c5292-149">Kudos</span></span></li><li><span data-ttu-id="c5292-150">재미 있는 내용</span><span class="sxs-lookup"><span data-stu-id="c5292-150">Fun stuff</span></span></li><li><span data-ttu-id="c5292-151">규정 준수</span><span class="sxs-lookup"><span data-stu-id="c5292-151">Compliance</span></span></li></ul>|
||||

