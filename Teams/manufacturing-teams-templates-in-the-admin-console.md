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
description: 관리 콘솔을 사용 하 여 미리 정의 된 설정, 채널 및 사전 설치 앱을 제공 하 여 제조의 요구 사항에 맞게 설계 되는 팀 템플릿을 만드는 방법을 알아봅니다.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 919bfc1bc3e13985ac90484cd203bf93201babd2
ms.sourcegitcommit: af9f96010460f9323db84912fe143aa0750ac798
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/21/2020
ms.locfileid: "48171032"
---
# <a name="use-teams-manufacturing-templates-in-the-admin-console"></a><span data-ttu-id="781b9-103">관리 콘솔에서 팀 제조 템플릿을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="781b9-103">Use Teams manufacturing templates in the admin console</span></span>

[!INCLUDE [template](includes/preview-feature.md)]

<span data-ttu-id="781b9-104">팀 서식 파일을 사용 하면 미리 정의 된 서식 파일 (설정, 채널 및 사전 설치 된 앱)을 제공 하 여 빠르고 쉽게 팀을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="781b9-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="781b9-105">팀 템플릿에는 제조 필요에 따라 디자인 된 팀 구조 정의가 미리 작성 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="781b9-105">Teams templates have pre-built definitions of team structures designed around manufacturing needs.</span></span> <span data-ttu-id="781b9-106">팀 템플릿을 확장 하 여 특정 조직의 요구 사항에 맞게 조정 된 팀을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="781b9-106">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="781b9-107">이 문서에서는 각 팀 서식 파일과이를 사용 하는 방법을 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="781b9-107">In this article, we will introduce each of the Teams templates and how we recommend using them.</span></span>

<span data-ttu-id="781b9-108">이 문서는 제조 조직의 여러 팀을 계획, 배포 및 관리 해야 하는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="781b9-108">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your manufacturing organization.</span></span> <span data-ttu-id="781b9-109">조직에 이미 팀 서비스를 배포 했다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="781b9-109">We assume that you already have deployed Teams service in your organization.</span></span> <span data-ttu-id="781b9-110">아직 팀을 롤아웃하기 않은 경우 먼저 [Microsoft 팀을 배포 하는 방법을](How-to-roll-out-teams.md)읽어 보세요.</span><span class="sxs-lookup"><span data-stu-id="781b9-110">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="781b9-111">일반적으로 팀 서식 파일에 대 한 자세한 내용은 [팀 서식 파일 시작](get-started-with-teams-templates-in-the-admin-console.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="781b9-111">To learn more about team templates in general, please refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="quality-and-safety"></a><span data-ttu-id="781b9-112">품질 및 안전</span><span class="sxs-lookup"><span data-stu-id="781b9-112">Quality and safety</span></span>

<span data-ttu-id="781b9-113">제조 공장 팀으로 의사 소통, 리소스에 대 한 액세스, 플랜트 작업을 중앙 집중화 합니다.</span><span class="sxs-lookup"><span data-stu-id="781b9-113">Centralize communication, access to resources, and plant operations with a Manufacturing Plant team.</span></span> <span data-ttu-id="781b9-114">정책 및 절차 문서, 교육 비디오, 보안 알림, 교대 handover 프로세스를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="781b9-114">Include policy and procedure documents, training videos, safety notices, shift handover processes.</span></span>

| <span data-ttu-id="781b9-115">기본 서식 파일 형식</span><span class="sxs-lookup"><span data-stu-id="781b9-115">Base template type</span></span>|<span data-ttu-id="781b9-116">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="781b9-116">baseTemplateId</span></span> | <span data-ttu-id="781b9-117">이 기본 서식 파일에 포함 된 속성</span><span class="sxs-lookup"><span data-stu-id="781b9-117">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="781b9-118">품질 및 안전</span><span class="sxs-lookup"><span data-stu-id="781b9-118">Quality and safety</span></span>|`com.microsoft.teams.template.QualitySafety` |<span data-ttu-id="781b9-119">채널</span><span class="sxs-lookup"><span data-stu-id="781b9-119">Channels:</span></span> <ul><li><span data-ttu-id="781b9-120">일반</span><span class="sxs-lookup"><span data-stu-id="781b9-120">General</span></span><li><span data-ttu-id="781b9-121">알림에서</span><span class="sxs-lookup"><span data-stu-id="781b9-121">Announcements</span></span></li><li><span data-ttu-id="781b9-122">줄 1</span><span class="sxs-lookup"><span data-stu-id="781b9-122">Line 1</span></span></li><li><span data-ttu-id="781b9-123">선 2</span><span class="sxs-lookup"><span data-stu-id="781b9-123">Line 2</span></span></li><li><span data-ttu-id="781b9-124">선 3</span><span class="sxs-lookup"><span data-stu-id="781b9-124">Line 3</span></span></li><li><span data-ttu-id="781b9-125">안전</span><span class="sxs-lookup"><span data-stu-id="781b9-125">Safety</span></span></li><li><span data-ttu-id="781b9-126">교육</span><span class="sxs-lookup"><span data-stu-id="781b9-126">Training</span></span></li><li><span data-ttu-id="781b9-127">관리할</span><span class="sxs-lookup"><span data-stu-id="781b9-127">Maintenance</span></span></li><li><span data-ttu-id="781b9-128">재미 있는 내용</span><span class="sxs-lookup"><span data-stu-id="781b9-128">Fun stuff</span></span></li></ul> <span data-ttu-id="781b9-129">들</span><span class="sxs-lookup"><span data-stu-id="781b9-129">Apps:</span></span> <ul><li><span data-ttu-id="781b9-130">키</span><span class="sxs-lookup"><span data-stu-id="781b9-130">Wiki</span></span></li></ul>|
||||
