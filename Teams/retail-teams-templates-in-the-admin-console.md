---
title: 관리 콘솔에서 팀 소매 서식 파일 사용
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
description: 관리자 콘솔을 사용 하 여 미리 정의 된 설정, 채널 및 사전 설치 앱을 제공 하 여 소매점의 요구 사항에 맞게 설계한 팀 구조를 만드는 방법에 대해 알아봅니다.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 77411e734ebbcfaea4d3e2a0454f48e43a8b8a7d
ms.sourcegitcommit: 45064a0020a1231e17967c74f082106c68213ea0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/30/2020
ms.locfileid: "48308331"
---
# <a name="use-teams-retail-templates-in-the-admin-console"></a><span data-ttu-id="819d0-103">관리 콘솔에서 팀 소매 서식 파일 사용</span><span class="sxs-lookup"><span data-stu-id="819d0-103">Use Teams retail templates in the admin console</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="819d0-104">팀 서식 파일을 사용 하면 미리 정의 된 서식 파일 (설정, 채널 및 사전 설치 된 앱)을 제공 하 여 빠르고 쉽게 팀을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="819d0-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="819d0-105">팀 템플릿에는 소매점의 요구 사항에 따라 디자인 된 팀 구조의 정의가 미리 작성 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="819d0-105">Teams templates have pre-built definitions of team structures designed around retailer needs.</span></span> <span data-ttu-id="819d0-106">팀 서식 파일을 사용 하 여 소매 업체에 잘 맞는 팀 유형을 신속 하 게 만들고 조직 내에서 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="819d0-106">You can use Teams templates to quickly create the types of teams that work well for retailers and deploy them across your organization.</span></span> <span data-ttu-id="819d0-107">팀 템플릿을 확장 하 여 특정 조직의 요구 사항에 맞게 조정 된 팀을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="819d0-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="819d0-108">이 문서에서는 각 팀 서식 파일과이를 사용 하는 방법을 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="819d0-108">In this article, we will introduce each of the Teams templates and how we recommend using them.</span></span>

<span data-ttu-id="819d0-109">본 문서는 소매점에서 여러 팀을 계획, 배포 및 관리 해야 하는 경우에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="819d0-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your retail organization.</span></span> <span data-ttu-id="819d0-110">조직에 이미 팀 서비스를 배포 했다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="819d0-110">We assume that you already have deployed Teams service in your organization.</span></span> <span data-ttu-id="819d0-111">아직 팀을 롤아웃하기 않은 경우 먼저 [Microsoft 팀을 배포 하는 방법을](How-to-roll-out-teams.md)읽어 보세요.</span><span class="sxs-lookup"><span data-stu-id="819d0-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="819d0-112">일반적으로 팀 서식 파일에 대 한 자세한 내용은 [팀 서식 파일 시작](get-started-with-teams-templates-in-the-admin-console.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="819d0-112">To learn more about team templates in general, please refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="organize-a-store"></a><span data-ttu-id="819d0-113">스토어 구성</span><span class="sxs-lookup"><span data-stu-id="819d0-113">Organize a store</span></span>

<span data-ttu-id="819d0-114">소매 직원을 하나의 중앙 환경에서 함께 가져와 작업을 관리 하 고 문서를 공유 하 고 고객 문제를 해결 하세요.</span><span class="sxs-lookup"><span data-stu-id="819d0-114">Bring your retail employees together in one central experience to manage tasks, share documents and resolve customer issues.</span></span> <span data-ttu-id="819d0-115">추가 응용 프로그램을 통합 하 여 이동 시작 & 프로세스를 간소화 합니다.</span><span class="sxs-lookup"><span data-stu-id="819d0-115">Integrate additional applications to streamline shift start & end processes.</span></span>

| <span data-ttu-id="819d0-116">기본 서식 파일 형식</span><span class="sxs-lookup"><span data-stu-id="819d0-116">Base template type</span></span> |<span data-ttu-id="819d0-117">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="819d0-117">baseTemplateId</span></span> | <span data-ttu-id="819d0-118">이 기본 서식 파일에 포함 된 속성</span><span class="sxs-lookup"><span data-stu-id="819d0-118">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="819d0-119">스토어 구성</span><span class="sxs-lookup"><span data-stu-id="819d0-119">Organize a store</span></span>| `retailStore`|<span data-ttu-id="819d0-120">채널</span><span class="sxs-lookup"><span data-stu-id="819d0-120">Channels:</span></span> <ul><li><span data-ttu-id="819d0-121">일반</span><span class="sxs-lookup"><span data-stu-id="819d0-121">General</span></span><li><span data-ttu-id="819d0-122">교대 이송</span><span class="sxs-lookup"><span data-stu-id="819d0-122">Shift handoff</span></span></li><li><span data-ttu-id="819d0-123">배웁니다</span><span class="sxs-lookup"><span data-stu-id="819d0-123">Learning</span></span></li></ul> <span data-ttu-id="819d0-124">들</span><span class="sxs-lookup"><span data-stu-id="819d0-124">Apps:</span></span> <ul><li><span data-ttu-id="819d0-125">키</span><span class="sxs-lookup"><span data-stu-id="819d0-125">Wiki</span></span></li></ul>|
||||

## <a name="manager-collaboration"></a><span data-ttu-id="819d0-126">관리자 공동 작업</span><span class="sxs-lookup"><span data-stu-id="819d0-126">Manager Collaboration</span></span>

<span data-ttu-id="819d0-127">관리자 공동 작업 템플릿은 저장소/지역에서 공동 작업 하는 관리자 집합을 위한 팀을 만드는 데 적합 합니다. 예를 들어 조직에 지역이 있는 경우 캘리포니아 지역에 대 한 관리자 공동 작업 팀을 만들고 해당 지역의 모든 스토어 관리자와 해당 지역의 지역 관리자를 함께 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="819d0-127">The Manager Collaboration template is ideal for creating a team for a set of managers to collaborate across stores/regions, etc. For example, if your organization has regions, you might create a Manager Collaboration team for the California Region and include all the store managers in that region, as well as the regional manager for that region.</span></span>

| <span data-ttu-id="819d0-128">기본 서식 파일 형식</span><span class="sxs-lookup"><span data-stu-id="819d0-128">Base template type</span></span>| <span data-ttu-id="819d0-129">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="819d0-129">baseTemplateId</span></span> | <span data-ttu-id="819d0-130">이 기본 서식 파일에 포함 된 속성</span><span class="sxs-lookup"><span data-stu-id="819d0-130">Properties that come with this base template</span></span> |
| ------------------|- |----------------------------------------------------- |
|<span data-ttu-id="819d0-131">소매 관리자 공동 작업</span><span class="sxs-lookup"><span data-stu-id="819d0-131">Retail - manager collaboration</span></span>|`retailManagerCollaboration` |<span data-ttu-id="819d0-132">채널</span><span class="sxs-lookup"><span data-stu-id="819d0-132">Channels:</span></span> <ul><li><span data-ttu-id="819d0-133">일반</span><span class="sxs-lookup"><span data-stu-id="819d0-133">General</span></span><li><span data-ttu-id="819d0-134">운영</span><span class="sxs-lookup"><span data-stu-id="819d0-134">Operations</span></span></li><li><span data-ttu-id="819d0-135">배웁니다</span><span class="sxs-lookup"><span data-stu-id="819d0-135">Learning</span></span></li></ul> <span data-ttu-id="819d0-136">들</span><span class="sxs-lookup"><span data-stu-id="819d0-136">Apps:</span></span> <ul><li><span data-ttu-id="819d0-137">키</span><span class="sxs-lookup"><span data-stu-id="819d0-137">Wiki</span></span></li></ul>|
||||
