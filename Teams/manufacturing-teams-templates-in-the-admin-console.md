---
title: 관리 센터에서 팀 제조 템플릿을 시작 하세요.
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
description: 사용 방법에 대해 알아보세요. 관리 센터를 사용 하 여 미리 정의 된 설정, 채널 및 사전 설치 앱을 제공 하 여 제조의 요구 사항에 맞게 설계한 팀 구조를 만들기 위해 팀 템플릿을 만듭니다.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9013bda2f83a63776dfbf9110a0863dcf68c0ddb
ms.sourcegitcommit: bc471f18e40e37456edc9696e11b175581847617
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/29/2020
ms.locfileid: "48800601"
---
# <a name="use-teams-manufacturing-templates-in-the-admin-center"></a><span data-ttu-id="6bb14-104">관리 센터에서 팀 제조 서식 파일 사용</span><span class="sxs-lookup"><span data-stu-id="6bb14-104">Use Teams manufacturing templates in the admin center</span></span>

<span data-ttu-id="6bb14-105">팀 서식 파일을 사용 하면 미리 정의 된 서식 파일 (설정, 채널 및 사전 설치 된 앱)을 제공 하 여 빠르고 쉽게 팀을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bb14-105">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="6bb14-106">팀 템플릿에는 제조 필요에 따라 디자인 된 팀 구조 정의가 미리 작성 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bb14-106">Teams templates have pre-built definitions of team structures designed around manufacturing needs.</span></span> <span data-ttu-id="6bb14-107">팀 템플릿을 확장 하 여 특정 조직의 요구 사항에 맞게 조정 된 팀을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bb14-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="6bb14-108">이 문서에서는 각 팀 템플릿을 소개 하 고 사용 방법을 추천 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bb14-108">In this article, we introduce each of the Teams templates and recommend how to use them.</span></span>

<span data-ttu-id="6bb14-109">이 문서는 제조 조직의 여러 팀을 계획, 배포 및 관리 해야 하는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bb14-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your manufacturing organization.</span></span> <span data-ttu-id="6bb14-110">조직에 이미 팀 서비스를 배포 했습니다.</span><span class="sxs-lookup"><span data-stu-id="6bb14-110">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="6bb14-111">아직 팀을 롤아웃하기 않은 경우 먼저 [Microsoft 팀을 배포 하는 방법을](How-to-roll-out-teams.md)읽어 보세요.</span><span class="sxs-lookup"><span data-stu-id="6bb14-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="6bb14-112">일반적으로 팀 서식 파일에 대 한 자세한 내용은 [팀 서식 파일 시작](get-started-with-teams-templates-in-the-admin-console.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6bb14-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="quality-and-safety"></a><span data-ttu-id="6bb14-113">품질 및 안전</span><span class="sxs-lookup"><span data-stu-id="6bb14-113">Quality and safety</span></span>

<span data-ttu-id="6bb14-114">제조 공장 팀으로 의사 소통, 리소스에 대 한 액세스, 플랜트 작업을 중앙 집중화 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bb14-114">Centralize communication, access to resources, and plant operations with a Manufacturing Plant team.</span></span> <span data-ttu-id="6bb14-115">정책 및 절차 문서, 교육 비디오, 보안 알림, 교대 handover 프로세스를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bb14-115">Include policy and procedure documents, training videos, safety notices, shift handover processes.</span></span>

| <span data-ttu-id="6bb14-116">기본 서식 파일 형식</span><span class="sxs-lookup"><span data-stu-id="6bb14-116">Base template type</span></span>|<span data-ttu-id="6bb14-117">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="6bb14-117">baseTemplateId</span></span> | <span data-ttu-id="6bb14-118">이 기본 서식 파일에 포함 된 속성</span><span class="sxs-lookup"><span data-stu-id="6bb14-118">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="6bb14-119">품질 및 안전</span><span class="sxs-lookup"><span data-stu-id="6bb14-119">Quality and safety</span></span>|`com.microsoft.teams.template.QualitySafety` |<span data-ttu-id="6bb14-120">채널</span><span class="sxs-lookup"><span data-stu-id="6bb14-120">Channels:</span></span> <ul><li><span data-ttu-id="6bb14-121">일반</span><span class="sxs-lookup"><span data-stu-id="6bb14-121">General</span></span><li><span data-ttu-id="6bb14-122">알림에서</span><span class="sxs-lookup"><span data-stu-id="6bb14-122">Announcements</span></span></li><li><span data-ttu-id="6bb14-123">줄 1</span><span class="sxs-lookup"><span data-stu-id="6bb14-123">Line 1</span></span></li><li><span data-ttu-id="6bb14-124">선 2</span><span class="sxs-lookup"><span data-stu-id="6bb14-124">Line 2</span></span></li><li><span data-ttu-id="6bb14-125">선 3</span><span class="sxs-lookup"><span data-stu-id="6bb14-125">Line 3</span></span></li><li><span data-ttu-id="6bb14-126">안전</span><span class="sxs-lookup"><span data-stu-id="6bb14-126">Safety</span></span></li><li><span data-ttu-id="6bb14-127">교육</span><span class="sxs-lookup"><span data-stu-id="6bb14-127">Training</span></span></li><li><span data-ttu-id="6bb14-128">관리할</span><span class="sxs-lookup"><span data-stu-id="6bb14-128">Maintenance</span></span></li><li><span data-ttu-id="6bb14-129">재미 있는 내용</span><span class="sxs-lookup"><span data-stu-id="6bb14-129">Fun stuff</span></span></li></ul> <span data-ttu-id="6bb14-130">들</span><span class="sxs-lookup"><span data-stu-id="6bb14-130">Apps:</span></span> <ul><li><span data-ttu-id="6bb14-131">키</span><span class="sxs-lookup"><span data-stu-id="6bb14-131">Wiki</span></span></li></ul>|
||||
