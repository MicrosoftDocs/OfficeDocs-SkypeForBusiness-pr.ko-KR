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
description: 팀 서식 파일을 사용 하 여 관리 콘솔을 사용 하는 미리 정의 된 설정, 채널 및 사전 설치 앱을 제공 하 여 재무 요구 사항에 맞게 설계한 팀 구조를 만드는 방법을 알아봅니다.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 270e03d58a89cf35132f254d2dd1af55d894e8d0
ms.sourcegitcommit: 448606977ee67befbdc91060363cf90dd346a528
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/19/2020
ms.locfileid: "48136113"
---
# <a name="use-teams-financial-templates-in-the-admin-console"></a><span data-ttu-id="25249-103">관리 콘솔에서 팀 재무 서식 파일 사용</span><span class="sxs-lookup"><span data-stu-id="25249-103">Use Teams financial templates in the admin console</span></span>

[!INCLUDE [template](includes/preview-feature.md)]

<span data-ttu-id="25249-104">팀 서식 파일을 사용 하면 미리 정의 된 서식 파일 (설정, 채널 및 사전 설치 된 앱)을 제공 하 여 빠르고 쉽게 팀을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25249-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="25249-105">팀 템플릿에는 재무 요구에 따라 디자인 된 팀 구조 정의가 미리 작성 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25249-105">Teams templates have pre-built definitions of team structures designed around financial needs.</span></span> <span data-ttu-id="25249-106">팀 템플릿을 확장 하 여 특정 조직의 요구 사항에 맞게 조정 된 팀을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25249-106">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="25249-107">이 문서에서는 각 팀 서식 파일과이를 사용 하는 방법을 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="25249-107">In this article, we will introduce each of the Teams templates and how we recommend using them.</span></span>

<span data-ttu-id="25249-108">이 문서에서는 재무 조직에서 여러 팀을 계획, 배포 및 관리 하는 책임이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25249-108">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your financial organization.</span></span> <span data-ttu-id="25249-109">조직에 이미 팀 서비스를 배포 했다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="25249-109">We assume that you already have deployed Teams service in your organization.</span></span> <span data-ttu-id="25249-110">아직 팀을 롤아웃하기 않은 경우 먼저 [Microsoft 팀을 배포 하는 방법을](How-to-roll-out-teams.md)읽어 보세요.</span><span class="sxs-lookup"><span data-stu-id="25249-110">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="25249-111">일반적으로 팀 서식 파일에 대 한 자세한 내용은 [팀 서식 파일 시작](get-started-with-teams-templates-in-the-admin-console.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="25249-111">To learn more about team templates in general, please refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="global-crisis-or-event"></a><span data-ttu-id="25249-112">전역 위기 또는 이벤트</span><span class="sxs-lookup"><span data-stu-id="25249-112">Global crisis or event</span></span>

<span data-ttu-id="25249-113">비즈니스 단위에서 위기 팀을 위한 공동 작업을 수행 하 고, 비즈니스 연속성 계획을 만들고, 원격 작업 팁을 공유 하 고, 고객 통신을 추적 하 고, 모든 사용자에 게 공지 사항 및 뉴스를 유지 하는 데</span><span class="sxs-lookup"><span data-stu-id="25249-113">Centralize collaboration for your crisis team across business units and help create business continuity plans, share remote working tips, track customer communications, and keep everyone in the loop with announcements and news.</span></span>

| <span data-ttu-id="25249-114">기본 서식 파일 형식</span><span class="sxs-lookup"><span data-stu-id="25249-114">Base template type</span></span>|<span data-ttu-id="25249-115">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="25249-115">baseTemplateId</span></span> | <span data-ttu-id="25249-116">이 기본 서식 파일에 포함 된 속성</span><span class="sxs-lookup"><span data-stu-id="25249-116">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
| <span data-ttu-id="25249-117">전역 위기 또는 이벤트에 대 한 공동 작업</span><span class="sxs-lookup"><span data-stu-id="25249-117">Collaborate on global crisis or event</span></span>|`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent` |<span data-ttu-id="25249-118">채널</span><span class="sxs-lookup"><span data-stu-id="25249-118">Channels:</span></span> <ul><li><span data-ttu-id="25249-119">일반</span><span class="sxs-lookup"><span data-stu-id="25249-119">General</span></span><li><span data-ttu-id="25249-120">알림에서</span><span class="sxs-lookup"><span data-stu-id="25249-120">Announcements</span></span></li><li><span data-ttu-id="25249-121">월드 뉴스</span><span class="sxs-lookup"><span data-stu-id="25249-121">World news</span></span></li><li><span data-ttu-id="25249-122">비즈니스 연속성</span><span class="sxs-lookup"><span data-stu-id="25249-122">Business continuity</span></span></li><li><span data-ttu-id="25249-123">원격 작업</span><span class="sxs-lookup"><span data-stu-id="25249-123">Remote working</span></span></li><li><span data-ttu-id="25249-124">내부 주석 s</span><span class="sxs-lookup"><span data-stu-id="25249-124">Internal comms</span></span></li><li><span data-ttu-id="25249-125">외부 대화 s</span><span class="sxs-lookup"><span data-stu-id="25249-125">External comms</span></span></li><li><span data-ttu-id="25249-126">고객 불만</span><span class="sxs-lookup"><span data-stu-id="25249-126">Customer complaints</span></span></li><li><span data-ttu-id="25249-127">보너스</span><span class="sxs-lookup"><span data-stu-id="25249-127">Kudos</span></span></li><li><span data-ttu-id="25249-128">임원 업데이트</span><span class="sxs-lookup"><span data-stu-id="25249-128">Executive update</span></span></li></ul><span data-ttu-id="25249-129">들</span><span class="sxs-lookup"><span data-stu-id="25249-129">Apps:</span></span> <ul><li><span data-ttu-id="25249-130">칭찬</span><span class="sxs-lookup"><span data-stu-id="25249-130">Praise</span></span></li><li><span data-ttu-id="25249-131">키</span><span class="sxs-lookup"><span data-stu-id="25249-131">Wiki</span></span></li><li><span data-ttu-id="25249-132">웹 사이트</span><span class="sxs-lookup"><span data-stu-id="25249-132">Website</span></span></li></ul>|
||||

## <a name="collaborate-within-a-bank-branch"></a><span data-ttu-id="25249-133">은행 지사 내에서 공동 작업</span><span class="sxs-lookup"><span data-stu-id="25249-133">Collaborate within a bank branch</span></span>

<span data-ttu-id="25249-134">은행에 대 한 공동 작업은 Huddles, 고객 모임, 담보 대출 공동 작업 등의 비즈니스 프로세스를 통해 직원 들에 게 집중 하 고 모든 사용자에 게 공지 및 Kudos를 포함 하도록 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="25249-134">Centralize collaboration for your bank branch employees across Huddles, Customer Meetings, Business Processes such as Mortgage Collaboration, and keep everyone in the loop with Announcements and Kudos.</span></span>

| <span data-ttu-id="25249-135">기본 서식 파일 형식</span><span class="sxs-lookup"><span data-stu-id="25249-135">Base template type</span></span> |<span data-ttu-id="25249-136">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="25249-136">baseTemplateId</span></span>| <span data-ttu-id="25249-137">이 기본 서식 파일에 포함 된 속성</span><span class="sxs-lookup"><span data-stu-id="25249-137">Properties that come with this base template</span></span> |
| ------------------ |--|----------------------------------------------------- |
|<span data-ttu-id="25249-138">은행 지사 내에서 공동 작업</span><span class="sxs-lookup"><span data-stu-id="25249-138">Collaborate within a bank branch</span></span>|`com.microsoft.teams.template.CollaborateWithinABankBranch` |<span data-ttu-id="25249-139">채널</span><span class="sxs-lookup"><span data-stu-id="25249-139">Channels:</span></span> <ul><li><span data-ttu-id="25249-140">일반</span><span class="sxs-lookup"><span data-stu-id="25249-140">General</span></span><li><span data-ttu-id="25249-141">알림에서</span><span class="sxs-lookup"><span data-stu-id="25249-141">Announcements</span></span></li><li><span data-ttu-id="25249-142">Huddles</span><span class="sxs-lookup"><span data-stu-id="25249-142">Huddles</span></span></li><li><span data-ttu-id="25249-143">고객 모임</span><span class="sxs-lookup"><span data-stu-id="25249-143">Customer meetings</span></span></li><li><span data-ttu-id="25249-144">코칭</span><span class="sxs-lookup"><span data-stu-id="25249-144">Coaching</span></span></li><li><span data-ttu-id="25249-145">기술 개발</span><span class="sxs-lookup"><span data-stu-id="25249-145">Skills development</span></span></li><li><span data-ttu-id="25249-146">대출 처리</span><span class="sxs-lookup"><span data-stu-id="25249-146">Loan processing</span></span></li><li><span data-ttu-id="25249-147">고객 불만</span><span class="sxs-lookup"><span data-stu-id="25249-147">Customer complaints</span></span></li><li><span data-ttu-id="25249-148">보너스</span><span class="sxs-lookup"><span data-stu-id="25249-148">Kudos</span></span></li><li><span data-ttu-id="25249-149">재미 있는 내용</span><span class="sxs-lookup"><span data-stu-id="25249-149">Fun stuff</span></span></li><li><span data-ttu-id="25249-150">규정 준수</span><span class="sxs-lookup"><span data-stu-id="25249-150">Compliance</span></span></li></ul>|
||||

