---
title: 관리 콘솔에서 팀 제조 템플릿을 시작 하세요.
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
description: 사용 방법에 대해 알아보세요. 관리자 콘솔을 사용 하 여 미리 정의 된 설정, 채널, 사전 설치 되어 있는 앱을 제공 하 여 제조할 목적으로 설계 되는 팀 구조를 만들 수 있습니다.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3ebbf765373699d07f96d11fff66e9677213bdb8
ms.sourcegitcommit: 340c2f432b78af4e78b21056af56c6421627045d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294441"
---
# <a name="use-teams-manufacturing-templates-in-the-admin-console"></a><span data-ttu-id="3bbac-104">관리 콘솔에서 팀 제조 템플릿을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3bbac-104">Use Teams manufacturing templates in the admin console</span></span>

<span data-ttu-id="3bbac-105">팀 서식 파일을 사용 하면 미리 정의 된 서식 파일 (설정, 채널 및 사전 설치 된 앱)을 제공 하 여 빠르고 쉽게 팀을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bbac-105">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="3bbac-106">팀 템플릿에는 제조 필요에 따라 디자인 된 팀 구조 정의가 미리 작성 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bbac-106">Teams templates have pre-built definitions of team structures designed around manufacturing needs.</span></span> <span data-ttu-id="3bbac-107">팀 템플릿을 확장 하 여 특정 조직의 요구 사항에 맞게 조정 된 팀을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bbac-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="3bbac-108">이 문서에서는 각 팀 템플릿을 소개 하 고 사용 방법을 추천 합니다.</span><span class="sxs-lookup"><span data-stu-id="3bbac-108">In this article, we introduce each of the Teams templates and recommend how to use them.</span></span>

<span data-ttu-id="3bbac-109">이 문서는 제조 조직의 여러 팀을 계획, 배포 및 관리 해야 하는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3bbac-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your manufacturing organization.</span></span> <span data-ttu-id="3bbac-110">조직에 이미 팀 서비스를 배포 했습니다.</span><span class="sxs-lookup"><span data-stu-id="3bbac-110">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="3bbac-111">아직 팀을 롤아웃하기 않은 경우 먼저 [Microsoft 팀을 배포 하는 방법을](How-to-roll-out-teams.md)읽어 보세요.</span><span class="sxs-lookup"><span data-stu-id="3bbac-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="3bbac-112">일반적으로 팀 서식 파일에 대 한 자세한 내용은 [팀 서식 파일 시작](get-started-with-teams-templates-in-the-admin-console.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3bbac-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="quality-and-safety"></a><span data-ttu-id="3bbac-113">품질 및 안전</span><span class="sxs-lookup"><span data-stu-id="3bbac-113">Quality and safety</span></span>

<span data-ttu-id="3bbac-114">제조 공장 팀으로 의사 소통, 리소스에 대 한 액세스, 플랜트 작업을 중앙 집중화 합니다.</span><span class="sxs-lookup"><span data-stu-id="3bbac-114">Centralize communication, access to resources, and plant operations with a Manufacturing Plant team.</span></span> <span data-ttu-id="3bbac-115">정책 및 절차 문서, 교육 비디오, 보안 알림, 교대 handover 프로세스를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="3bbac-115">Include policy and procedure documents, training videos, safety notices, shift handover processes.</span></span>

| <span data-ttu-id="3bbac-116">기본 서식 파일 형식</span><span class="sxs-lookup"><span data-stu-id="3bbac-116">Base template type</span></span>|<span data-ttu-id="3bbac-117">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="3bbac-117">baseTemplateId</span></span> | <span data-ttu-id="3bbac-118">이 기본 서식 파일에 포함 된 속성</span><span class="sxs-lookup"><span data-stu-id="3bbac-118">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="3bbac-119">품질 및 안전</span><span class="sxs-lookup"><span data-stu-id="3bbac-119">Quality and safety</span></span>|`com.microsoft.teams.template.QualitySafety` |<span data-ttu-id="3bbac-120">채널</span><span class="sxs-lookup"><span data-stu-id="3bbac-120">Channels:</span></span> <ul><li><span data-ttu-id="3bbac-121">일반</span><span class="sxs-lookup"><span data-stu-id="3bbac-121">General</span></span><li><span data-ttu-id="3bbac-122">알림에서</span><span class="sxs-lookup"><span data-stu-id="3bbac-122">Announcements</span></span></li><li><span data-ttu-id="3bbac-123">줄 1</span><span class="sxs-lookup"><span data-stu-id="3bbac-123">Line 1</span></span></li><li><span data-ttu-id="3bbac-124">선 2</span><span class="sxs-lookup"><span data-stu-id="3bbac-124">Line 2</span></span></li><li><span data-ttu-id="3bbac-125">선 3</span><span class="sxs-lookup"><span data-stu-id="3bbac-125">Line 3</span></span></li><li><span data-ttu-id="3bbac-126">안전</span><span class="sxs-lookup"><span data-stu-id="3bbac-126">Safety</span></span></li><li><span data-ttu-id="3bbac-127">교육</span><span class="sxs-lookup"><span data-stu-id="3bbac-127">Training</span></span></li><li><span data-ttu-id="3bbac-128">관리할</span><span class="sxs-lookup"><span data-stu-id="3bbac-128">Maintenance</span></span></li><li><span data-ttu-id="3bbac-129">재미 있는 내용</span><span class="sxs-lookup"><span data-stu-id="3bbac-129">Fun stuff</span></span></li></ul> <span data-ttu-id="3bbac-130">들</span><span class="sxs-lookup"><span data-stu-id="3bbac-130">Apps:</span></span> <ul><li><span data-ttu-id="3bbac-131">키</span><span class="sxs-lookup"><span data-stu-id="3bbac-131">Wiki</span></span></li></ul>|
||||
