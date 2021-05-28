---
title: 관리 센터에서 제조 팀 템플릿 시작
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
description: 팀 템플릿을 사용하여 관리 센터를 사용하여 미리 정의된 설정, 채널 및 미리 설치된 앱을 제공하여 제조 요구 사항을 위해 디자인된 팀 구조를 만드는 방법을 알아보습니다.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: ec27cba4336d86f51a32582440d5d7902ffca2b9
ms.sourcegitcommit: 36924dc54fe7b09607b07d7543fe7e39eb4d2483
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684485"
---
# <a name="use-manufacturing-team-templates-in-the-admin-center"></a><span data-ttu-id="8cdb2-103">관리 센터에서 제조 팀 템플릿 사용</span><span class="sxs-lookup"><span data-stu-id="8cdb2-103">Use manufacturing team templates in the admin center</span></span>

<span data-ttu-id="8cdb2-104">팀 템플릿을 사용하면 설정, 채널 및 미리 설치된 앱의 미리 정의된 템플릿을 제공하여 빠르고 쉽게 팀을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cdb2-104">Team templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="8cdb2-105">팀 템플릿에는 제조 요구 사항을 중심으로 설계된 팀 구조에 대한 미리 작성된 정의가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cdb2-105">Team templates have pre-built definitions of team structures designed around manufacturing needs.</span></span> <span data-ttu-id="8cdb2-106">팀 템플릿을 확장하여 특정 조직 요구에 맞게 팀을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cdb2-106">You can also extend the team templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="8cdb2-107">이 문서에서는 각 팀 템플릿을 소개하고 이를 사용하는 방법을 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="8cdb2-107">In this article, we introduce each of the team templates and recommend how to use them.</span></span>

<span data-ttu-id="8cdb2-108">이 문서는 제조 조직 전반에 걸쳐 여러 팀을 계획, 배포 및 관리할 책임이 있는 경우를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8cdb2-108">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your manufacturing organization.</span></span> <span data-ttu-id="8cdb2-109">귀사는 이미 Teams 서비스를 구축했습니다.</span><span class="sxs-lookup"><span data-stu-id="8cdb2-109">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="8cdb2-110">Teams를 아직 배포하지 않은 경우 먼저 [Microsoft Teams를 배포하는 방법](./deploy-overview.md)을 읽어보세요.</span><span class="sxs-lookup"><span data-stu-id="8cdb2-110">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](./deploy-overview.md).</span></span>

<span data-ttu-id="8cdb2-111">일반적으로 팀 템플릿에 대한 자세한 내용은 팀 템플릿 시작 을 [참조합니다.](get-started-with-teams-templates-in-the-admin-console.md)</span><span class="sxs-lookup"><span data-stu-id="8cdb2-111">To learn more about team templates in general, refer to [Get started with team templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="quality-and-safety"></a><span data-ttu-id="8cdb2-112">품질 및 안전</span><span class="sxs-lookup"><span data-stu-id="8cdb2-112">Quality and safety</span></span>

<span data-ttu-id="8cdb2-113">Manufacturing Plant 팀을 통해 통신, 리소스에 대한 액세스 및 플랜트 작업을 중앙 집중화합니다.</span><span class="sxs-lookup"><span data-stu-id="8cdb2-113">Centralize communication, access to resources, and plant operations with a Manufacturing Plant team.</span></span> <span data-ttu-id="8cdb2-114">정책 및 절차 문서, 교육 비디오, 안전 고지, 교대 근무 프로세스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="8cdb2-114">Include policy and procedure documents, training videos, safety notices, shift handover processes.</span></span>

| <span data-ttu-id="8cdb2-115">기본 서식 파일 형식</span><span class="sxs-lookup"><span data-stu-id="8cdb2-115">Base template type</span></span>|<span data-ttu-id="8cdb2-116">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="8cdb2-116">baseTemplateId</span></span>| <span data-ttu-id="8cdb2-117">이 기본 서식 파일과 함께 사용할 수 있는 속성</span><span class="sxs-lookup"><span data-stu-id="8cdb2-117">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="8cdb2-118">품질 및 안전</span><span class="sxs-lookup"><span data-stu-id="8cdb2-118">Quality and safety</span></span>|`com.microsoft.teams.template.QualitySafety` |<span data-ttu-id="8cdb2-119">채널</span><span class="sxs-lookup"><span data-stu-id="8cdb2-119">Channels:</span></span> <ul><li><span data-ttu-id="8cdb2-120">일반</span><span class="sxs-lookup"><span data-stu-id="8cdb2-120">General</span></span><li><span data-ttu-id="8cdb2-121">공지 사항</span><span class="sxs-lookup"><span data-stu-id="8cdb2-121">Announcements</span></span></li><li><span data-ttu-id="8cdb2-122">1줄</span><span class="sxs-lookup"><span data-stu-id="8cdb2-122">Line 1</span></span></li><li><span data-ttu-id="8cdb2-123">2줄</span><span class="sxs-lookup"><span data-stu-id="8cdb2-123">Line 2</span></span></li><li><span data-ttu-id="8cdb2-124">3줄</span><span class="sxs-lookup"><span data-stu-id="8cdb2-124">Line 3</span></span></li><li><span data-ttu-id="8cdb2-125">안전</span><span class="sxs-lookup"><span data-stu-id="8cdb2-125">Safety</span></span></li><li><span data-ttu-id="8cdb2-126">교육</span><span class="sxs-lookup"><span data-stu-id="8cdb2-126">Training</span></span></li><li><span data-ttu-id="8cdb2-127">유지 관리</span><span class="sxs-lookup"><span data-stu-id="8cdb2-127">Maintenance</span></span></li><li><span data-ttu-id="8cdb2-128">재미있는 물건</span><span class="sxs-lookup"><span data-stu-id="8cdb2-128">Fun stuff</span></span></li></ul> <span data-ttu-id="8cdb2-129">앱:</span><span class="sxs-lookup"><span data-stu-id="8cdb2-129">Apps:</span></span> <ul><li><span data-ttu-id="8cdb2-130">Wiki</span><span class="sxs-lookup"><span data-stu-id="8cdb2-130">Wiki</span></span></li><li><span data-ttu-id="8cdb2-131">Planner</span><span class="sxs-lookup"><span data-stu-id="8cdb2-131">Planner</span></span></li></ul>|
||||