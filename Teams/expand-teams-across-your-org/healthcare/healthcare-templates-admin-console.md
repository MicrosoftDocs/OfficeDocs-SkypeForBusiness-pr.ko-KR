---
title: 관리 콘솔에서 팀 의료 템플릿 사용
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: 관리 콘솔에서 Microsoft 팀 서식 파일을 사용 하 여 미리 정의 된 서식 파일, 채널 및 앱 템플릿을 제공 하 여 팀을 빠르고 쉽게 만들 수 있습니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ff093ecb0ffec0fdc58d724c4a75fdea1810fd6d
ms.sourcegitcommit: 340c2f432b78af4e78b21056af56c6421627045d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294584"
---
# <a name="use-teams-healthcare-templates-in-the-admin-console"></a><span data-ttu-id="c8537-103">관리 콘솔에서 팀 의료 템플릿 사용</span><span class="sxs-lookup"><span data-stu-id="c8537-103">Use Teams healthcare templates in the admin console</span></span>

<span data-ttu-id="c8537-104">Microsoft 팀 서식 파일을 사용 하면 미리 정의 된 서식 파일 (설정, 채널 및 사전 설치 된 앱)을 제공 하 여 빠르고 쉽게 팀을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8537-104">Microsoft Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="c8537-105">건강 보험 조직의 경우, 사용자가 팀을 효과적으로 활용 하는 방법에 대 한 구조를 제공 하는 것 처럼 서식 파일을 사용 하는 것이 특히 좋을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8537-105">For healthcare organizations, templates can be especially powerful, as they provide structure for users to become oriented with how to best leverage Teams effectively.</span></span> <span data-ttu-id="c8537-106">또한 서식 파일을 사용 하면 관리자가 조직 간에 일관 된 팀을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8537-106">Templates also allow administrators to deploy consistent teams across their organizations.</span></span> <span data-ttu-id="c8537-107">이 문서는 의료 기관에서 여러 팀을 계획, 배포 및 관리 해야 하는 경우에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8537-107">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your Healthcare organization.</span></span>

<span data-ttu-id="c8537-108">현재 다양 한 상황에 활용할 수 있는 제 1 자 건강 보험 템플릿을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8537-108">We currently offer two first-party healthcare templates that you can leverage for a variety of situations.</span></span> <span data-ttu-id="c8537-109">팀 서식 파일에 대 한 일반적인 내용은 [관리 콘솔에서 팀 서식 파일 시작](../../get-started-with-teams-templates-in-the-admin-console.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c8537-109">To learn more about team templates in general, see [Get started with Teams templates in the admin console](../../get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="collaborate-on-patient-care"></a><span data-ttu-id="c8537-110">환자 관리에 대 한 공동 작업</span><span class="sxs-lookup"><span data-stu-id="c8537-110">Collaborate on patient care</span></span>

 <span data-ttu-id="c8537-111">통합, pod 또는 부서 내에서 건강 보험 통신과 공동 작업을 합리화 하세요.</span><span class="sxs-lookup"><span data-stu-id="c8537-111">Streamline healthcare communication and collaboration within a ward, pod, or department.</span></span> <span data-ttu-id="c8537-112">서식 파일을 사용 하 여 환자 관리 및 운영 요구를 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8537-112">The template can be used to facilitate patient management and operational needs of a ward.</span></span>

| <span data-ttu-id="c8537-113">기본 서식 파일 형식</span><span class="sxs-lookup"><span data-stu-id="c8537-113">Base template type</span></span> |<span data-ttu-id="c8537-114">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="c8537-114">baseTemplateId</span></span>| <span data-ttu-id="c8537-115">이 기본 서식 파일에 포함 된 속성</span><span class="sxs-lookup"><span data-stu-id="c8537-115">Properties that come with this base template</span></span> |
| ------------------ |---|----------------------------------------------------- |
| <span data-ttu-id="c8537-116">환자 관리에 대 한 공동 작업</span><span class="sxs-lookup"><span data-stu-id="c8537-116">Collaborate on patient care</span></span> |`healthcareWard` | <span data-ttu-id="c8537-117">채널</span><span class="sxs-lookup"><span data-stu-id="c8537-117">Channels:</span></span><ul><li><span data-ttu-id="c8537-118">일반</span><span class="sxs-lookup"><span data-stu-id="c8537-118">General</span></span></li><li><span data-ttu-id="c8537-119">알림에서</span><span class="sxs-lookup"><span data-stu-id="c8537-119">Announcements</span></span></li><li><span data-ttu-id="c8537-120">Huddles</span><span class="sxs-lookup"><span data-stu-id="c8537-120">Huddles</span></span></li><li><span data-ttu-id="c8537-121">소수</span><span class="sxs-lookup"><span data-stu-id="c8537-121">Rounds</span></span></li><li><span data-ttu-id="c8537-122">자원</span><span class="sxs-lookup"><span data-stu-id="c8537-122">Staffing</span></span></li><li><span data-ttu-id="c8537-123">교육</span><span class="sxs-lookup"><span data-stu-id="c8537-123">Training</span></span></li></ul> <span data-ttu-id="c8537-124">들</span><span class="sxs-lookup"><span data-stu-id="c8537-124">Apps:</span></span> <ul><li><span data-ttu-id="c8537-125">키</span><span class="sxs-lookup"><span data-stu-id="c8537-125">Wiki</span></span></li>|
||||

## <a name="hospital"></a><span data-ttu-id="c8537-126">병원</span><span class="sxs-lookup"><span data-stu-id="c8537-126">Hospital</span></span>

<span data-ttu-id="c8537-127">병원에서 여러 wards, pods, 부서 간의 의사 소통 및 공동 작업을 간소화 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8537-127">Streamline communication and collaboration between multiple wards, pods, and departments within a hospital.</span></span> <span data-ttu-id="c8537-128">이 서식 파일에는 병원 작업을 위한 기본 채널 집합이 포함 되며, 자격증, ad-hoc을 포함 하도록 자체 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8537-128">This template includes a set of base channels for hospital operations, and can be self-extended to include specialties, ad-hoc.</span></span>

| <span data-ttu-id="c8537-129">기본 서식 파일 형식</span><span class="sxs-lookup"><span data-stu-id="c8537-129">Base template type</span></span> |<span data-ttu-id="c8537-130">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="c8537-130">baseTemplateId</span></span> | <span data-ttu-id="c8537-131">이 기본 서식 파일에 포함 된 속성</span><span class="sxs-lookup"><span data-stu-id="c8537-131">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="c8537-132">병원</span><span class="sxs-lookup"><span data-stu-id="c8537-132">Hospital</span></span>|`healthcareHospital`|<span data-ttu-id="c8537-133">채널</span><span class="sxs-lookup"><span data-stu-id="c8537-133">Channels:</span></span> <ul><li><span data-ttu-id="c8537-134">일반</span><span class="sxs-lookup"><span data-stu-id="c8537-134">General</span></span><li><span data-ttu-id="c8537-135">알림에서</span><span class="sxs-lookup"><span data-stu-id="c8537-135">Announcements</span></span></li><li><span data-ttu-id="c8537-136">규정 준수</span><span class="sxs-lookup"><span data-stu-id="c8537-136">Compliance</span></span></li><li><span data-ttu-id="c8537-137">Custodial</span><span class="sxs-lookup"><span data-stu-id="c8537-137">Custodial</span></span></li><li><span data-ttu-id="c8537-138">인적 자원</span><span class="sxs-lookup"><span data-stu-id="c8537-138">Human resources</span></span></li><li><span data-ttu-id="c8537-139">Pharmacy</span><span class="sxs-lookup"><span data-stu-id="c8537-139">Pharmacy</span></span></li></ul> <span data-ttu-id="c8537-140">들</span><span class="sxs-lookup"><span data-stu-id="c8537-140">Apps:</span></span> <ul><li><span data-ttu-id="c8537-141">키</span><span class="sxs-lookup"><span data-stu-id="c8537-141">Wiki</span></span></li></ul>|
||||

## <a name="related-topics"></a><span data-ttu-id="c8537-142">관련 항목</span><span class="sxs-lookup"><span data-stu-id="c8537-142">Related topics</span></span>

[<span data-ttu-id="c8537-143">Teams 서식 파일 시작</span><span class="sxs-lookup"><span data-stu-id="c8537-143">Get started with Teams templates</span></span>](../../get-started-with-teams-templates-in-the-admin-console.md)
