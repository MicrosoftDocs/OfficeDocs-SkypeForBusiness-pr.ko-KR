---
title: Microsoft 팀 업그레이드 | 환경 평가, 검색 질문
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 이 지침을 사용 하 여 팀으로 업그레이드 하기 위한 현재 환경을 적절 하 게 평가 하는 요구 사항에 대해 알아보세요.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 799d348f05c8fece6684d01768934faedcb7603f
ms.sourcegitcommit: f7f86744c6dbf0db87e1408fd1f4b770fda07ff9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/17/2020
ms.locfileid: "45158746"
---
# <a name="evaluate-your-environment-before-upgrading-to-teams"></a><span data-ttu-id="d6d08-103">팀으로 업그레이드 하기 전에 환경 평가</span><span class="sxs-lookup"><span data-stu-id="d6d08-103">Evaluate your environment before upgrading to Teams</span></span>

<span data-ttu-id="d6d08-104">![여행 다이어그램 업그레이드, 기술 준비 단계 강조](media/upgrade-banner-tech-readiness.png "기술 준비 단계에 중점을 두어 업그레이드 여행 단계")</span><span class="sxs-lookup"><span data-stu-id="d6d08-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="d6d08-105">이 문서는 사용자 준비 단계와 병행 하 여 완료 한 활동 인 업그레이드 여행에 대 한 기술 준비 단계의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="d6d08-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="d6d08-106">계속 하기 전에 이전 단계에서 다음 활동을 완료 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d08-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="d6d08-107">프로젝트 이해 관계자 참여</span><span class="sxs-lookup"><span data-stu-id="d6d08-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="d6d08-108">프로젝트 범위 정의</span><span class="sxs-lookup"><span data-stu-id="d6d08-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="d6d08-109">비즈니스용 Skype 및 팀의 공존 성과 상호 운영성 이해</span><span class="sxs-lookup"><span data-stu-id="d6d08-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="d6d08-110">업그레이드 여행 선택</span><span class="sxs-lookup"><span data-stu-id="d6d08-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="d6d08-111">이 문서에서는 운영 팀의 현재 환경을 적절 하 게 평가 하기 위한 요구 사항을 간략하게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d08-111">This article gives an overview of the requirements for properly evaluating your current environment for operating Teams.</span></span> <span data-ttu-id="d6d08-112">환경을 평가 하 여 전체 배포에 영향을 주는 위험 및 요구 사항을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d08-112">By evaluating your environment, you identify risks and requirements that will influence your overall deployment.</span></span> <span data-ttu-id="d6d08-113">이러한 항목을 미리 확인 하 여 성공에 대 한 계획을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d08-113">By identifying these items beforehand, you can adjust your planning to drive success.</span></span>

## <a name="introduction-to-the-discovery-questionnaire"></a><span data-ttu-id="d6d08-114">검색 질문에 대 한 소개</span><span class="sxs-lookup"><span data-stu-id="d6d08-114">Introduction to the Discovery Questionnaire</span></span>

<span data-ttu-id="d6d08-115">목표 키 결과 (OKRs)를 달성 하기 위해 이전에는 키 서비스 결정을 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d08-115">To achieve your objective key results (OKRs), you previously made key service decisions.</span></span> <span data-ttu-id="d6d08-116">다음 단계는 환경 검색을 수행 하 여 IT 인프라, 네트워킹 및 작업 관련 모든 측면을 평가 하 여 조직이 솔루션을 구현할 준비가 되었는지 확인 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d6d08-116">The next step is to perform environmental discovery to evaluate all aspects relating to your IT infrastructure, networking, and operations to confirm that your organization is ready to implement the solution.</span></span> <span data-ttu-id="d6d08-117">검색은 팀에 대 한 여행 계획을 수립할 때 가장 먼저 수행 하는 주요 단계 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="d6d08-117">Discovery is one of the very first, key steps that you take when planning for your journey to Teams.</span></span> <span data-ttu-id="d6d08-118">환경 검색에는 네트워크가 팀으로 업그레이드를 지원할 수 있도록 네트워크 준비 평가가 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d08-118">Environmental discovery must include a network readiness assessment to ensure your network can support upgrading to Teams.</span></span> <span data-ttu-id="d6d08-119">자신의 환경에 대 한 상세한 검색을 수행 하 여 현재 상태를 파악 하 고, 문제가 있거나 팀의 출시에 대 한 가능한 차단 가능성을 더욱 중요 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d08-119">You perform a detailed discovery of your environment to better understand its current state and to reveal any difficulties or—even more important—possible blockers to the execution of your Teams rollout.</span></span>

<span data-ttu-id="d6d08-120">환경 평가 및 채택 준비 평가의 일부로 기술 위험을 식별 하 고 식별 된 각 위험에 대 한 완화 계획을 개발 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d08-120">You identify technical risks as part of an environmental assessment and adoption readiness evaluation, and develop a mitigation plan for each identified risk.</span></span> <span data-ttu-id="d6d08-121">이 정보는 위험 등록기에 통합 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d08-121">You should incorporate this information in the risk register.</span></span>

<span data-ttu-id="d6d08-122">기존 공동 작업 인프라와 Microsoft 365 또는 Office 365 조 직, 네트워킹, 끝점, 운영, 채택 및 준비와 관련 된 모든 문제가 환경 검색 질문의 일부로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6d08-122">All matters related to your existing collaboration infrastructure and Microsoft 365 or Office 365 organization, networking, endpoints, operations, and adoption and readiness are included as part of the environmental discovery questionnaire.</span></span> <span data-ttu-id="d6d08-123">프로젝트 팀과 협력 하 여 필요한 정보를 최대한 자세하게 제공 하 여 계획 활동을 촉진 하세요.</span><span class="sxs-lookup"><span data-stu-id="d6d08-123">Work with your project team to provide the requested information with as much detail as possible to facilitate your planning activities.</span></span>

<span data-ttu-id="d6d08-124">이 [질문](upgrade-plan-journey-discovery-questionnaire.md) 서에는 다음 섹션으로 나뉘어 조직에서 팀의 여러 주요 영역에 대 한 준비가 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d08-124">[The questionnaire](upgrade-plan-journey-discovery-questionnaire.md) is divided into the following sections to confirm your organization's readiness for your Teams deployment in several major areas:</span></span>

- <span data-ttu-id="d6d08-125">Microsoft 365 또는 Office 365 조직 세부 정보</span><span class="sxs-lookup"><span data-stu-id="d6d08-125">Microsoft 365 or Office 365 organization details</span></span>
- <span data-ttu-id="d6d08-126">기존 공동 작업 플랫폼 요약</span><span class="sxs-lookup"><span data-stu-id="d6d08-126">Existing collaboration platform summary</span></span>
- <span data-ttu-id="d6d08-127">공동 작업 플랫폼 배포 세부 정보</span><span class="sxs-lookup"><span data-stu-id="d6d08-127">Collaboration platform deployment details</span></span>
- <span data-ttu-id="d6d08-128">네트워킹 및 Microsoft 365 또는 Office 365 서비스에 대 한 액세스</span><span class="sxs-lookup"><span data-stu-id="d6d08-128">Networking and access to Microsoft 365 or Office 365 services</span></span>
- <span data-ttu-id="d6d08-129">끝점</span><span class="sxs-lookup"><span data-stu-id="d6d08-129">Endpoints</span></span>
- <span data-ttu-id="d6d08-130">운영</span><span class="sxs-lookup"><span data-stu-id="d6d08-130">Operations</span></span>
- <span data-ttu-id="d6d08-131">채택 및 준비</span><span class="sxs-lookup"><span data-stu-id="d6d08-131">Adoption and readiness</span></span>

> [!TIP]
> <span data-ttu-id="d6d08-132">Microsoft Word 문서로 질문을 복사 하 여 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d08-132">You can start by copying the questionnaire into a Microsoft Word document.</span></span> <span data-ttu-id="d6d08-133">모든 질문에 답을 하 고 이동할 때 모든 세부 정보를 수집 해 보세요.</span><span class="sxs-lookup"><span data-stu-id="d6d08-133">Try to answer all questions and capture all details as you move through.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/><span data-ttu-id="d6d08-134">판단 요점</span><span class="sxs-lookup"><span data-stu-id="d6d08-134">Decision point</span></span></td><td><ul><li><span data-ttu-id="d6d08-135">환경 평가를 완료 해야 하는 사람은 누구 인가요?</span><span class="sxs-lookup"><span data-stu-id="d6d08-135">Who will be responsible for completing an environment assessment?</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next step"/><br/><span data-ttu-id="d6d08-136">다음 단계</span><span class="sxs-lookup"><span data-stu-id="d6d08-136">Next step</span></span></td><td><ul><li><span data-ttu-id="d6d08-137">환경 평가의 결과를 문서화 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d08-137">Document the results of the environment assessment.</span></span></li></ul></td></tr>
</table>


## <a name="project-team"></a><span data-ttu-id="d6d08-138">프로젝트 팀</span><span class="sxs-lookup"><span data-stu-id="d6d08-138">Project team</span></span>

<span data-ttu-id="d6d08-139">프로젝트 팀에 게 적합 한 사람을 참여 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d08-139">Ensure that you've engaged the right people for your project team.</span></span> <span data-ttu-id="d6d08-140">[프로젝트 이해 관계자 참여](upgrade-enlist-stakeholders.md)에서 완료 한 단계를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d08-140">Verify the steps you completed in [Enlist your project stakeholders](upgrade-enlist-stakeholders.md).</span></span>

<span data-ttu-id="d6d08-141">환경을 평가한 후에는 다음 단계를 진행 하세요 ( [서비스 준비](upgrade-prepare-environment-prepare-service.md)).</span><span class="sxs-lookup"><span data-stu-id="d6d08-141">After you evaluate your environment, proceed to the next step: [Prepare your service](upgrade-prepare-environment-prepare-service.md).</span></span>
