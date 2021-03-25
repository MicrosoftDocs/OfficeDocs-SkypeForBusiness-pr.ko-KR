---
title: 관리 센터에서 Teams 제조 템플릿 시작
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
description: 사용하는 방법에 대해 자세히 알아보아야 합니다. 관리 센터를 사용하여 미리 정의된 설정, 채널 및 미리 설치된 앱을 제공하여 제조 요구 사항을 위해 설계된 팀 구조를 만드는 Teams 템플릿입니다.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9f5439cd8fdd053ab8444a1016eac94064638605
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120559"
---
# <a name="use-teams-manufacturing-templates-in-the-admin-center"></a><span data-ttu-id="0659a-104">관리 센터에서 Teams 제조 템플릿 사용</span><span class="sxs-lookup"><span data-stu-id="0659a-104">Use Teams manufacturing templates in the admin center</span></span>

<span data-ttu-id="0659a-105">Teams 서식 파일을 사용하면 미리 정의된 설정, 채널 및 미리 설치된 앱 서식 파일을 제공하여 팀을 쉽고 빠르게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0659a-105">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="0659a-106">Teams 템플릿에는 제조 요구 사항을 중심으로 설계된 팀 구조에 대한 미리 작성된 정의가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0659a-106">Teams templates have pre-built definitions of team structures designed around manufacturing needs.</span></span> <span data-ttu-id="0659a-107">Teams 서식 파일을 확장하여 특정 조직 요구에 맞는 팀을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0659a-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="0659a-108">이 문서에서는 각 Teams 템플릿을 소개하고 사용하는 방법을 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="0659a-108">In this article, we introduce each of the Teams templates and recommend how to use them.</span></span>

<span data-ttu-id="0659a-109">이 문서는 제조 조직 전반에 걸쳐 여러 팀을 계획, 배포 및 관리할 책임이 있는 경우를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0659a-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your manufacturing organization.</span></span> <span data-ttu-id="0659a-110">귀사는 이미 Teams 서비스를 구축했습니다.</span><span class="sxs-lookup"><span data-stu-id="0659a-110">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="0659a-111">Teams를 아직 배포하지 않은 경우 먼저 [Microsoft Teams를 배포하는 방법](./deploy-overview.md)을 읽어보세요.</span><span class="sxs-lookup"><span data-stu-id="0659a-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](./deploy-overview.md).</span></span>

<span data-ttu-id="0659a-112">일반적인 팀 서식 파일에 대한 자세한 내용은 [Teams 서식 파일 시작하기](get-started-with-teams-templates-in-the-admin-console.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0659a-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="quality-and-safety"></a><span data-ttu-id="0659a-113">품질 및 안전</span><span class="sxs-lookup"><span data-stu-id="0659a-113">Quality and safety</span></span>

<span data-ttu-id="0659a-114">Manufacturing Plant 팀을 통해 통신, 리소스에 대한 액세스 및 플랜트 작업을 중앙 집중화합니다.</span><span class="sxs-lookup"><span data-stu-id="0659a-114">Centralize communication, access to resources, and plant operations with a Manufacturing Plant team.</span></span> <span data-ttu-id="0659a-115">정책 및 절차 문서, 교육 비디오, 안전 고지, 교대 근무 프로세스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="0659a-115">Include policy and procedure documents, training videos, safety notices, shift handover processes.</span></span>

| <span data-ttu-id="0659a-116">기본 서식 파일 형식</span><span class="sxs-lookup"><span data-stu-id="0659a-116">Base template type</span></span>|<span data-ttu-id="0659a-117">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="0659a-117">baseTemplateId</span></span>| <span data-ttu-id="0659a-118">이 기본 서식 파일과 함께 사용할 수 있는 속성</span><span class="sxs-lookup"><span data-stu-id="0659a-118">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="0659a-119">품질 및 안전</span><span class="sxs-lookup"><span data-stu-id="0659a-119">Quality and safety</span></span>|`com.microsoft.teams.template.QualitySafety` |<span data-ttu-id="0659a-120">채널</span><span class="sxs-lookup"><span data-stu-id="0659a-120">Channels:</span></span> <ul><li><span data-ttu-id="0659a-121">일반</span><span class="sxs-lookup"><span data-stu-id="0659a-121">General</span></span><li><span data-ttu-id="0659a-122">공지 사항</span><span class="sxs-lookup"><span data-stu-id="0659a-122">Announcements</span></span></li><li><span data-ttu-id="0659a-123">1줄</span><span class="sxs-lookup"><span data-stu-id="0659a-123">Line 1</span></span></li><li><span data-ttu-id="0659a-124">2줄</span><span class="sxs-lookup"><span data-stu-id="0659a-124">Line 2</span></span></li><li><span data-ttu-id="0659a-125">3줄</span><span class="sxs-lookup"><span data-stu-id="0659a-125">Line 3</span></span></li><li><span data-ttu-id="0659a-126">안전</span><span class="sxs-lookup"><span data-stu-id="0659a-126">Safety</span></span></li><li><span data-ttu-id="0659a-127">교육</span><span class="sxs-lookup"><span data-stu-id="0659a-127">Training</span></span></li><li><span data-ttu-id="0659a-128">유지 관리</span><span class="sxs-lookup"><span data-stu-id="0659a-128">Maintenance</span></span></li><li><span data-ttu-id="0659a-129">재미있는 물건</span><span class="sxs-lookup"><span data-stu-id="0659a-129">Fun stuff</span></span></li></ul> <span data-ttu-id="0659a-130">앱:</span><span class="sxs-lookup"><span data-stu-id="0659a-130">Apps:</span></span> <ul><li><span data-ttu-id="0659a-131">Wiki</span><span class="sxs-lookup"><span data-stu-id="0659a-131">Wiki</span></span></li><li><span data-ttu-id="0659a-132">Planner</span><span class="sxs-lookup"><span data-stu-id="0659a-132">Planner</span></span></li></ul>|
||||