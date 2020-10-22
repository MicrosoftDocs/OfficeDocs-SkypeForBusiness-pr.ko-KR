---
title: 관리 센터에서 팀 정부 서식 파일 사용
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
description: 사용 방법에 대해 알아보세요. 관리 센터를 사용 하 여 미리 정의 된 설정, 채널 및 사전 설치 앱을 제공 하 여 정부용 팀 구조를 개발 하기 위해 팀 서식 파일을 만들 수 있습니다.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 993cabc7139edeb971f60f1cdf44428fb4083db9
ms.sourcegitcommit: 0a9c5c01b37a93eecc369ca0ed49ae18f6a5065b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2020
ms.locfileid: "48655515"
---
# <a name="use-teams-government-templates-in-the-admin-center"></a><span data-ttu-id="41fa1-104">관리 센터에서 팀 정부 서식 파일 사용</span><span class="sxs-lookup"><span data-stu-id="41fa1-104">Use Teams government templates in the admin center</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="41fa1-105">팀 서식 파일을 사용 하면 미리 정의 된 서식 파일 (설정, 채널 및 사전 설치 된 앱)을 제공 하 여 빠르고 쉽게 팀을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41fa1-105">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="41fa1-106">팀 템플릿에는 정부 요구에 따라 디자인 된 팀 구조의 정의가 미리 작성 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41fa1-106">Teams templates have pre-built definitions of team structures designed around governmental needs.</span></span> <span data-ttu-id="41fa1-107">팀 템플릿을 확장 하 여 특정 조직의 요구 사항에 맞게 조정 된 팀을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41fa1-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="41fa1-108">이 문서에서는 각 팀 템플릿을 소개 하 고 사용 방법을 추천 합니다.</span><span class="sxs-lookup"><span data-stu-id="41fa1-108">In this article, we introduce each of the Teams templates and recommend how to use them.</span></span>

<span data-ttu-id="41fa1-109">본 문서는 정부 기관에서 여러 팀을 계획, 배포 및 관리 하는 책임이 있는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="41fa1-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your governmental organization.</span></span> <span data-ttu-id="41fa1-110">조직에 이미 팀 서비스를 배포 했습니다.</span><span class="sxs-lookup"><span data-stu-id="41fa1-110">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="41fa1-111">아직 팀을 롤아웃하기 않은 경우 먼저 [Microsoft 팀을 배포 하는 방법을](How-to-roll-out-teams.md)읽어 보세요.</span><span class="sxs-lookup"><span data-stu-id="41fa1-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="41fa1-112">일반적으로 팀 서식 파일에 대 한 자세한 내용은 [팀 서식 파일 시작](get-started-with-teams-templates-in-the-admin-console.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="41fa1-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="coordinate-incident-response"></a><span data-ttu-id="41fa1-113">조정 사고 대응</span><span class="sxs-lookup"><span data-stu-id="41fa1-113">Coordinate incident response</span></span>

<span data-ttu-id="41fa1-114">위기 관리 또는 사고 대응 팀에 대 한 커뮤니케이션 및 중요 리소스를 중앙 집중화 합니다.</span><span class="sxs-lookup"><span data-stu-id="41fa1-114">Centralize communication and critical resources for your crisis management or incident response team.</span></span> <span data-ttu-id="41fa1-115">이 팀 내에는 모든 문서에 대 한 중앙 위치를 만드는 데 도움이 되는 다양 한 형식의 파일을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41fa1-115">Within this team, you can include many different types of files to help create a central place for all your documents.</span></span> <span data-ttu-id="41fa1-116">온라인 모임을 사용 하 여 정보 흐름 및 따른 단기 인식을 개선 하세요.</span><span class="sxs-lookup"><span data-stu-id="41fa1-116">Use online meetings to improve information flow and situational awareness.</span></span>

| <span data-ttu-id="41fa1-117">기본 서식 파일 형식</span><span class="sxs-lookup"><span data-stu-id="41fa1-117">Base template type</span></span> |<span data-ttu-id="41fa1-118">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="41fa1-118">baseTemplateId</span></span> | <span data-ttu-id="41fa1-119">이 기본 서식 파일에 포함 된 속성</span><span class="sxs-lookup"><span data-stu-id="41fa1-119">Properties that come with this base template</span></span> |
|-------------------|-------|---------------------------------------------------------------------------|
|<span data-ttu-id="41fa1-120">조정 사고 대응</span><span class="sxs-lookup"><span data-stu-id="41fa1-120">Coordinate incident response</span></span>|`com.microsoft.teams.template.CoordinateIncidentResponse` |<span data-ttu-id="41fa1-121">채널</span><span class="sxs-lookup"><span data-stu-id="41fa1-121">Channels:</span></span> <ul><li><span data-ttu-id="41fa1-122">일반</span><span class="sxs-lookup"><span data-stu-id="41fa1-122">General</span></span><li><span data-ttu-id="41fa1-123">알림에서</span><span class="sxs-lookup"><span data-stu-id="41fa1-123">Announcements</span></span></li><li><span data-ttu-id="41fa1-124">물류</span><span class="sxs-lookup"><span data-stu-id="41fa1-124">Logistics</span></span></li><li><span data-ttu-id="41fa1-125">계획</span><span class="sxs-lookup"><span data-stu-id="41fa1-125">Planning</span></span></li><li><span data-ttu-id="41fa1-126">복구</span><span class="sxs-lookup"><span data-stu-id="41fa1-126">Recovery</span></span></li><li><span data-ttu-id="41fa1-127">받기</span><span class="sxs-lookup"><span data-stu-id="41fa1-127">Urgent</span></span></li></ul> <span data-ttu-id="41fa1-128">들</span><span class="sxs-lookup"><span data-stu-id="41fa1-128">Apps:</span></span> <ul><li><span data-ttu-id="41fa1-129">키</span><span class="sxs-lookup"><span data-stu-id="41fa1-129">Wiki</span></span></li><li><span data-ttu-id="41fa1-130">0:excel}</span><span class="sxs-lookup"><span data-stu-id="41fa1-130">Excel</span></span></li><li><span data-ttu-id="41fa1-131">만들어졌으므로</span><span class="sxs-lookup"><span data-stu-id="41fa1-131">OneNote</span></span></li><li><span data-ttu-id="41fa1-132">SharePoint</span><span class="sxs-lookup"><span data-stu-id="41fa1-132">SharePoint</span></span></li><li><span data-ttu-id="41fa1-133">Planner</span><span class="sxs-lookup"><span data-stu-id="41fa1-133">Planner</span></span></li></ul>|
||||