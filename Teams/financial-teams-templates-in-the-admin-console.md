---
title: 관리 센터를 사용하여 재무 팀 템플릿 시작
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
description: 관리 센터를 사용하여 Teams 미리 정의된 설정, 채널 및 미리 설치된 앱을 제공하여 재무 요구에 따라 설계된 팀 구조를 만드는 방법에 대해 알아보습니다.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 34e1140fe1551c0e0bc52449735755fc6d6428ca
ms.sourcegitcommit: 36924dc54fe7b09607b07d7543fe7e39eb4d2483
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684445"
---
# <a name="use-financial-team-templates-in-the-admin-center"></a><span data-ttu-id="20f10-103">관리 센터에서 재무 팀 템플릿 사용</span><span class="sxs-lookup"><span data-stu-id="20f10-103">Use financial team templates in the admin center</span></span>

<span data-ttu-id="20f10-104">팀 템플릿을 사용하면 설정, 채널 및 미리 설치된 앱의 미리 정의된 템플릿을 제공하여 빠르고 쉽게 팀을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20f10-104">Team templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="20f10-105">팀 템플릿에는 재정적 요구 사항을 중심으로 설계된 팀 구조에 대한 미리 작성된 정의가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20f10-105">Team templates have pre-built definitions of team structures designed around financial needs.</span></span> <span data-ttu-id="20f10-106">팀 템플릿을 확장하여 특정 조직 요구에 맞게 팀을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20f10-106">You can also extend the team templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="20f10-107">이 문서에서는 각 팀 템플릿을 소개하고 이를 사용하는 방법을 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="20f10-107">In this article, we'll introduce each of the team templates and recommend how to use them.</span></span>

<span data-ttu-id="20f10-108">이 문서는 재무 조직 전반에 걸쳐 여러 팀을 계획, 배포 및 관리할 책임이 있는 경우를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="20f10-108">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your financial organization.</span></span> <span data-ttu-id="20f10-109">귀사는 이미 Teams 서비스를 구축했습니다.</span><span class="sxs-lookup"><span data-stu-id="20f10-109">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="20f10-110">Teams를 아직 배포하지 않은 경우 먼저 [Microsoft Teams를 배포하는 방법](./deploy-overview.md)을 읽어보세요.</span><span class="sxs-lookup"><span data-stu-id="20f10-110">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](./deploy-overview.md).</span></span>

<span data-ttu-id="20f10-111">일반적으로 팀 템플릿에 대한 자세한 내용은 팀 템플릿 시작 을 [참조합니다.](get-started-with-teams-templates-in-the-admin-console.md)</span><span class="sxs-lookup"><span data-stu-id="20f10-111">To learn more about team templates in general, refer to [Get started with team templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="global-crisis-or-event"></a><span data-ttu-id="20f10-112">글로벌 위기 또는 이벤트</span><span class="sxs-lookup"><span data-stu-id="20f10-112">Global crisis or event</span></span>

<span data-ttu-id="20f10-113">비즈니스 단위에서 위기 팀에 대한 공동 작업을 중앙 집중화하고 비즈니스 연속성 계획을 만들고, 원격 작업 팁을 공유하고, 고객 통신을 추적하고, 공지 및 뉴스를 사용하여 모든 사람을 루프에 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20f10-113">Centralize collaboration for your crisis team across business units and help create business continuity plans, share remote working tips, track customer communications, and keep everyone in the loop with announcements and news.</span></span>

| <span data-ttu-id="20f10-114">기본 서식 파일 형식</span><span class="sxs-lookup"><span data-stu-id="20f10-114">Base template type</span></span>|<span data-ttu-id="20f10-115">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="20f10-115">baseTemplateId</span></span> | <span data-ttu-id="20f10-116">이 기본 서식 파일과 함께 사용할 수 있는 속성</span><span class="sxs-lookup"><span data-stu-id="20f10-116">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
| <span data-ttu-id="20f10-117">글로벌 위기 또는 이벤트에 대한 공동 작업</span><span class="sxs-lookup"><span data-stu-id="20f10-117">Collaborate on global crisis or event</span></span>|`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent` |<span data-ttu-id="20f10-118">채널</span><span class="sxs-lookup"><span data-stu-id="20f10-118">Channels:</span></span> <ul><li><span data-ttu-id="20f10-119">일반</span><span class="sxs-lookup"><span data-stu-id="20f10-119">General</span></span><li><span data-ttu-id="20f10-120">공지 사항</span><span class="sxs-lookup"><span data-stu-id="20f10-120">Announcements</span></span></li><li><span data-ttu-id="20f10-121">세계 뉴스</span><span class="sxs-lookup"><span data-stu-id="20f10-121">World news</span></span></li><li><span data-ttu-id="20f10-122">비즈니스 연속성</span><span class="sxs-lookup"><span data-stu-id="20f10-122">Business continuity</span></span></li><li><span data-ttu-id="20f10-123">원격 작업</span><span class="sxs-lookup"><span data-stu-id="20f10-123">Remote working</span></span></li><li><span data-ttu-id="20f10-124">내부 커미스</span><span class="sxs-lookup"><span data-stu-id="20f10-124">Internal comms</span></span></li><li><span data-ttu-id="20f10-125">외부 커미스</span><span class="sxs-lookup"><span data-stu-id="20f10-125">External comms</span></span></li><li><span data-ttu-id="20f10-126">승인 요청</span><span class="sxs-lookup"><span data-stu-id="20f10-126">Approvals request</span></span></li><li><span data-ttu-id="20f10-127">고객 불만</span><span class="sxs-lookup"><span data-stu-id="20f10-127">Customer complaints</span></span></li><li><span data-ttu-id="20f10-128">Kudos</span><span class="sxs-lookup"><span data-stu-id="20f10-128">Kudos</span></span></li><li><span data-ttu-id="20f10-129">임원 업데이트</span><span class="sxs-lookup"><span data-stu-id="20f10-129">Executive update</span></span></li></ul><span data-ttu-id="20f10-130">앱:</span><span class="sxs-lookup"><span data-stu-id="20f10-130">Apps:</span></span> <ul><li><span data-ttu-id="20f10-131">칭찬하기</span><span class="sxs-lookup"><span data-stu-id="20f10-131">Praise</span></span></li><li><span data-ttu-id="20f10-132">Wiki</span><span class="sxs-lookup"><span data-stu-id="20f10-132">Wiki</span></span></li><li><span data-ttu-id="20f10-133">웹 사이트</span><span class="sxs-lookup"><span data-stu-id="20f10-133">Website</span></span></li><li><span data-ttu-id="20f10-134">Planner</span><span class="sxs-lookup"><span data-stu-id="20f10-134">Planner</span></span></li></ul>|
||||

## <a name="collaborate-within-a-bank-branch"></a><span data-ttu-id="20f10-135">은행 지점 내에서 공동 작업</span><span class="sxs-lookup"><span data-stu-id="20f10-135">Collaborate within a bank branch</span></span>

<span data-ttu-id="20f10-136">Huddles, 고객 모임, 모기지 공동 작업과 같은 비즈니스 프로세스에서 은행 지점 직원에 대한 공동 작업을 중앙 집중화하고 공지사항 및 Kudos를 사용하여 모든 사람을 루프에 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="20f10-136">Centralize collaboration for your bank branch employees across Huddles, Customer Meetings, Business Processes such as Mortgage Collaboration, and keep everyone in the loop with Announcements and Kudos.</span></span>

| <span data-ttu-id="20f10-137">기본 서식 파일 형식</span><span class="sxs-lookup"><span data-stu-id="20f10-137">Base template type</span></span> |<span data-ttu-id="20f10-138">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="20f10-138">baseTemplateId</span></span>| <span data-ttu-id="20f10-139">이 기본 서식 파일과 함께 사용할 수 있는 속성</span><span class="sxs-lookup"><span data-stu-id="20f10-139">Properties that come with this base template</span></span> |
| ------------------ |--|----------------------------------------------------- |
|<span data-ttu-id="20f10-140">은행 지점 내에서 공동 작업</span><span class="sxs-lookup"><span data-stu-id="20f10-140">Collaborate within a bank branch</span></span>|`com.microsoft.teams.template.CollaborateWithinABankBranch` |<span data-ttu-id="20f10-141">채널</span><span class="sxs-lookup"><span data-stu-id="20f10-141">Channels:</span></span> <ul><li><span data-ttu-id="20f10-142">일반</span><span class="sxs-lookup"><span data-stu-id="20f10-142">General</span></span><li><span data-ttu-id="20f10-143">공지 사항</span><span class="sxs-lookup"><span data-stu-id="20f10-143">Announcements</span></span></li><li><span data-ttu-id="20f10-144">장애 요소</span><span class="sxs-lookup"><span data-stu-id="20f10-144">Huddles</span></span></li><li><span data-ttu-id="20f10-145">고객 모임</span><span class="sxs-lookup"><span data-stu-id="20f10-145">Customer meetings</span></span></li><li><span data-ttu-id="20f10-146">승인 요청</span><span class="sxs-lookup"><span data-stu-id="20f10-146">Approvals Request</span></span></li><li><span data-ttu-id="20f10-147">코칭</span><span class="sxs-lookup"><span data-stu-id="20f10-147">Coaching</span></span></li><li><span data-ttu-id="20f10-148">기술 개발</span><span class="sxs-lookup"><span data-stu-id="20f10-148">Skills development</span></span></li><li><span data-ttu-id="20f10-149">대출 처리</span><span class="sxs-lookup"><span data-stu-id="20f10-149">Loan processing</span></span></li><li><span data-ttu-id="20f10-150">고객 불만</span><span class="sxs-lookup"><span data-stu-id="20f10-150">Customer complaints</span></span></li><li><span data-ttu-id="20f10-151">Kudos</span><span class="sxs-lookup"><span data-stu-id="20f10-151">Kudos</span></span></li><li><span data-ttu-id="20f10-152">재미있는 물건</span><span class="sxs-lookup"><span data-stu-id="20f10-152">Fun stuff</span></span></li><li><span data-ttu-id="20f10-153">규정 준수</span><span class="sxs-lookup"><span data-stu-id="20f10-153">Compliance</span></span></li></ul><span data-ttu-id="20f10-154">앱:</span><span class="sxs-lookup"><span data-stu-id="20f10-154">Apps:</span></span><ul><li><span data-ttu-id="20f10-155">칭찬하기</span><span class="sxs-lookup"><span data-stu-id="20f10-155">Praise</span></span></li></ul>|
||||