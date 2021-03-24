---
title: 관리 센터에서 Teams 정부 템플릿 사용
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
description: 사용하는 방법에 대해 자세히 알아보아야 합니다. 관리 센터를 사용하여 미리 정의된 설정, 채널 및 미리 설치된 앱을 제공하여 정부 요구에 따라 설계된 팀 구조를 만드는 Teams 템플릿입니다.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: db22de142b9e7f2bead93e607dd01c9dd362ddba
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092216"
---
# <a name="use-teams-government-templates-in-the-admin-center"></a><span data-ttu-id="1e099-104">관리 센터에서 Teams 정부 템플릿 사용</span><span class="sxs-lookup"><span data-stu-id="1e099-104">Use Teams government templates in the admin center</span></span>

<span data-ttu-id="1e099-105">Teams 서식 파일을 사용하면 미리 정의된 설정, 채널 및 미리 설치된 앱 서식 파일을 제공하여 팀을 쉽고 빠르게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e099-105">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="1e099-106">Teams 템플릿에는 정부 요구 사항을 중심으로 디자인된 팀 구조에 대한 미리 작성된 정의가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e099-106">Teams templates have pre-built definitions of team structures designed around governmental needs.</span></span> <span data-ttu-id="1e099-107">Teams 서식 파일을 확장하여 특정 조직 요구에 맞는 팀을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e099-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="1e099-108">이 문서에서는 각 Teams 템플릿을 소개하고 사용하는 방법을 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="1e099-108">In this article, we introduce each of the Teams templates and recommend how to use them.</span></span>

<span data-ttu-id="1e099-109">이 문서는 정부 조직 전체에서 여러 팀을 계획, 배포 및 관리할 책임이 있는 경우를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1e099-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your governmental organization.</span></span> <span data-ttu-id="1e099-110">귀사는 이미 Teams 서비스를 구축했습니다.</span><span class="sxs-lookup"><span data-stu-id="1e099-110">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="1e099-111">Teams를 아직 배포하지 않은 경우 먼저 [Microsoft Teams를 배포하는 방법](./deploy-overview.md)을 읽어보세요.</span><span class="sxs-lookup"><span data-stu-id="1e099-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](./deploy-overview.md).</span></span>

<span data-ttu-id="1e099-112">일반적인 팀 서식 파일에 대한 자세한 내용은 [Teams 서식 파일 시작하기](get-started-with-teams-templates-in-the-admin-console.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1e099-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="coordinate-incident-response"></a><span data-ttu-id="1e099-113">인시던트 응답 조정</span><span class="sxs-lookup"><span data-stu-id="1e099-113">Coordinate incident response</span></span>

<span data-ttu-id="1e099-114">위기 관리 또는 인시던트 대응 팀에 대한 통신 및 중요한 리소스를 중앙 집중화합니다.</span><span class="sxs-lookup"><span data-stu-id="1e099-114">Centralize communication and critical resources for your crisis management or incident response team.</span></span> <span data-ttu-id="1e099-115">이 팀 내에서 다양한 유형의 파일을 포함하여 모든 문서에 대한 중앙 장소를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e099-115">Within this team, you can include many different types of files to help create a central place for all your documents.</span></span> <span data-ttu-id="1e099-116">온라인 모임을 사용하여 정보 흐름 및 상황 인식을 개선합니다.</span><span class="sxs-lookup"><span data-stu-id="1e099-116">Use online meetings to improve information flow and situational awareness.</span></span>

| <span data-ttu-id="1e099-117">기본 서식 파일 형식</span><span class="sxs-lookup"><span data-stu-id="1e099-117">Base template type</span></span> |<span data-ttu-id="1e099-118">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="1e099-118">baseTemplateId</span></span> | <span data-ttu-id="1e099-119">이 기본 서식 파일과 함께 사용할 수 있는 속성</span><span class="sxs-lookup"><span data-stu-id="1e099-119">Properties that come with this base template</span></span> |
|-------------------|-------|---------------------------------------------------------------------------|
|<span data-ttu-id="1e099-120">인시던트 응답 조정</span><span class="sxs-lookup"><span data-stu-id="1e099-120">Coordinate incident response</span></span>|`com.microsoft.teams.template.CoordinateIncidentResponse`|<span data-ttu-id="1e099-121">채널</span><span class="sxs-lookup"><span data-stu-id="1e099-121">Channels:</span></span> <ul><li><span data-ttu-id="1e099-122">일반</span><span class="sxs-lookup"><span data-stu-id="1e099-122">General</span></span><li><span data-ttu-id="1e099-123">공지 사항</span><span class="sxs-lookup"><span data-stu-id="1e099-123">Announcements</span></span></li><li><span data-ttu-id="1e099-124">물류</span><span class="sxs-lookup"><span data-stu-id="1e099-124">Logistics</span></span></li><li><span data-ttu-id="1e099-125">계획</span><span class="sxs-lookup"><span data-stu-id="1e099-125">Planning</span></span></li><li><span data-ttu-id="1e099-126">복구</span><span class="sxs-lookup"><span data-stu-id="1e099-126">Recovery</span></span></li><li><span data-ttu-id="1e099-127">긴급</span><span class="sxs-lookup"><span data-stu-id="1e099-127">Urgent</span></span></li></ul> <span data-ttu-id="1e099-128">앱:</span><span class="sxs-lookup"><span data-stu-id="1e099-128">Apps:</span></span> <ul><li><span data-ttu-id="1e099-129">Wiki</span><span class="sxs-lookup"><span data-stu-id="1e099-129">Wiki</span></span></li><li><span data-ttu-id="1e099-130">Excel</span><span class="sxs-lookup"><span data-stu-id="1e099-130">Excel</span></span></li><li><span data-ttu-id="1e099-131">OneNote</span><span class="sxs-lookup"><span data-stu-id="1e099-131">OneNote</span></span></li><li><span data-ttu-id="1e099-132">SharePoint</span><span class="sxs-lookup"><span data-stu-id="1e099-132">SharePoint</span></span></li><li><span data-ttu-id="1e099-133">Planner</span><span class="sxs-lookup"><span data-stu-id="1e099-133">Planner</span></span></li></ul>|
||||