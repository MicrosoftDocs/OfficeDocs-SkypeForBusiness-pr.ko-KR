---
title: 관리 센터에서 Teams 정부 서식 파일 사용
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
description: 사용 방법을 배워야 합니다. 관리 센터를 사용하여 미리 정의한 설정, 채널 및 미리 설치된 앱을 제공하여 정부 요구를 위해 설계된 팀 구조를 만드는 Teams 템플릿입니다.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: db0d8fa4a2744f0f3c3591918230e3f569727ae7
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662203"
---
# <a name="use-teams-government-templates-in-the-admin-center"></a><span data-ttu-id="b74ce-104">관리 센터에서 Teams 정부 서식 파일 사용</span><span class="sxs-lookup"><span data-stu-id="b74ce-104">Use Teams government templates in the admin center</span></span>

<span data-ttu-id="b74ce-105">Teams 서식 파일을 사용하면 설정, 채널 및 미리 설치된 앱의 미리 정의된 서식 파일을 제공하여 빠르고 쉽게 팀을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b74ce-105">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="b74ce-106">Teams 템플릿에는 정부 요구 사항을 중심으로 설계된 팀 구조에 대한 미리 작성된 정의가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b74ce-106">Teams templates have pre-built definitions of team structures designed around governmental needs.</span></span> <span data-ttu-id="b74ce-107">Teams 서식 파일을 확장하여 특정 조직 요구에 맞는 팀을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b74ce-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="b74ce-108">이 문서에서는 각 Teams 서식 파일을 소개하고 이를 사용하는 방법을 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="b74ce-108">In this article, we introduce each of the Teams templates and recommend how to use them.</span></span>

<span data-ttu-id="b74ce-109">이 문서는 정부 조직에서 여러 팀을 계획, 배포 및 관리할 책임이 있는 경우를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b74ce-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your governmental organization.</span></span> <span data-ttu-id="b74ce-110">조직에 Teams 서비스를 이미 배포했습니다.</span><span class="sxs-lookup"><span data-stu-id="b74ce-110">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="b74ce-111">아직 Teams를 롤아웃하지 않은 경우 먼저 Microsoft Teams를 롤아웃하는 [방법을 읽어 읽습니다.](How-to-roll-out-teams.md)</span><span class="sxs-lookup"><span data-stu-id="b74ce-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="b74ce-112">일반적으로 팀 서식 파일에 대한 자세한 내용은 Teams 서식 파일 [시작을 참조합니다.](get-started-with-teams-templates-in-the-admin-console.md)</span><span class="sxs-lookup"><span data-stu-id="b74ce-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="coordinate-incident-response"></a><span data-ttu-id="b74ce-113">인시던트 대응 조정</span><span class="sxs-lookup"><span data-stu-id="b74ce-113">Coordinate incident response</span></span>

<span data-ttu-id="b74ce-114">위기 관리 또는 인시던트 대응 팀을 위한 통신 및 중요한 리소스를 중앙 집중화합니다.</span><span class="sxs-lookup"><span data-stu-id="b74ce-114">Centralize communication and critical resources for your crisis management or incident response team.</span></span> <span data-ttu-id="b74ce-115">이 팀 내에서 다양한 유형의 파일을 포함하면 모든 문서에 대한 중앙 장소를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b74ce-115">Within this team, you can include many different types of files to help create a central place for all your documents.</span></span> <span data-ttu-id="b74ce-116">온라인 모임을 사용하여 정보 흐름 및 상황 인식을 개선할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b74ce-116">Use online meetings to improve information flow and situational awareness.</span></span>

| <span data-ttu-id="b74ce-117">기본 템플릿 형식</span><span class="sxs-lookup"><span data-stu-id="b74ce-117">Base template type</span></span> |<span data-ttu-id="b74ce-118">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="b74ce-118">baseTemplateId</span></span> | <span data-ttu-id="b74ce-119">이 기본 템플릿과 함께 사용할 속성</span><span class="sxs-lookup"><span data-stu-id="b74ce-119">Properties that come with this base template</span></span> |
|-------------------|-------|---------------------------------------------------------------------------|
|<span data-ttu-id="b74ce-120">인시던트 대응 조정</span><span class="sxs-lookup"><span data-stu-id="b74ce-120">Coordinate incident response</span></span>|`com.microsoft.teams.template.CoordinateIncidentResponse`|<span data-ttu-id="b74ce-121">채널:</span><span class="sxs-lookup"><span data-stu-id="b74ce-121">Channels:</span></span> <ul><li><span data-ttu-id="b74ce-122">일반</span><span class="sxs-lookup"><span data-stu-id="b74ce-122">General</span></span><li><span data-ttu-id="b74ce-123">공지</span><span class="sxs-lookup"><span data-stu-id="b74ce-123">Announcements</span></span></li><li><span data-ttu-id="b74ce-124">물류</span><span class="sxs-lookup"><span data-stu-id="b74ce-124">Logistics</span></span></li><li><span data-ttu-id="b74ce-125">계획</span><span class="sxs-lookup"><span data-stu-id="b74ce-125">Planning</span></span></li><li><span data-ttu-id="b74ce-126">복구</span><span class="sxs-lookup"><span data-stu-id="b74ce-126">Recovery</span></span></li><li><span data-ttu-id="b74ce-127">긴급</span><span class="sxs-lookup"><span data-stu-id="b74ce-127">Urgent</span></span></li></ul> <span data-ttu-id="b74ce-128">앱:</span><span class="sxs-lookup"><span data-stu-id="b74ce-128">Apps:</span></span> <ul><li><span data-ttu-id="b74ce-129">Wiki</span><span class="sxs-lookup"><span data-stu-id="b74ce-129">Wiki</span></span></li><li><span data-ttu-id="b74ce-130">Excel</span><span class="sxs-lookup"><span data-stu-id="b74ce-130">Excel</span></span></li><li><span data-ttu-id="b74ce-131">OneNote</span><span class="sxs-lookup"><span data-stu-id="b74ce-131">OneNote</span></span></li><li><span data-ttu-id="b74ce-132">SharePoint</span><span class="sxs-lookup"><span data-stu-id="b74ce-132">SharePoint</span></span></li><li><span data-ttu-id="b74ce-133">Planner</span><span class="sxs-lookup"><span data-stu-id="b74ce-133">Planner</span></span></li></ul>|
||||