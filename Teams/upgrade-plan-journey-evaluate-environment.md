---
title: Teams로 업그레이드하기 전에 환경 평가
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Teams로 업그레이드하기 위한 현재 환경을 제대로 평가하기 위한 요구 사항에 대해 자세히 배워야 합니다.
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
ms.openlocfilehash: c783934128e2c1d3f971948c41e3481839ff0aa1
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578241"
---
# <a name="evaluate-your-environment-before-upgrading-to-teams"></a><span data-ttu-id="5c376-103">Teams로 업그레이드하기 전에 환경 평가</span><span class="sxs-lookup"><span data-stu-id="5c376-103">Evaluate your environment before upgrading to Teams</span></span>

<span data-ttu-id="5c376-104">![기술 준비 단계 강조를 표시하는 업그레이드 여정 다이어그램](media/upgrade-banner-tech-readiness.png "기술 준비 단계에 강조를 두는 업그레이드 단계")</span><span class="sxs-lookup"><span data-stu-id="5c376-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="5c376-105">이 문서는 사용자 준비 단계와 병렬로 완료하는 작업인 업그레이드 여정의 기술 준비 단계의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="5c376-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="5c376-106">계속하기 전에 이전 단계에서 이러한 활동을 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c376-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="5c376-107">프로젝트 관련자에 참여</span><span class="sxs-lookup"><span data-stu-id="5c376-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="5c376-108">프로젝트 범위 정의</span><span class="sxs-lookup"><span data-stu-id="5c376-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="5c376-109">비즈니스용 Skype 및 Teams의 공존 및 상호 연동성 이해</span><span class="sxs-lookup"><span data-stu-id="5c376-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="5c376-110">업그레이드 여정 선택</span><span class="sxs-lookup"><span data-stu-id="5c376-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="5c376-111">이 문서에서는 Teams 운영을 위해 현재 환경을 제대로 평가하기 위한 요구 사항에 대해 간략하게 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="5c376-111">This article gives an overview of the requirements for properly evaluating your current environment for operating Teams.</span></span> <span data-ttu-id="5c376-112">환경을 평가하여 전체 배포에 영향을 주는 위험 및 요구 사항을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="5c376-112">By evaluating your environment, you identify risks and requirements that will influence your overall deployment.</span></span> <span data-ttu-id="5c376-113">이러한 항목을 먼저 식별하여 계획을 조정하여 성공을 주도할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c376-113">By identifying these items beforehand, you can adjust your planning to drive success.</span></span>

## <a name="introduction-to-the-discovery-questionnaire"></a><span data-ttu-id="5c376-114">검색 설문지 소개</span><span class="sxs-lookup"><span data-stu-id="5c376-114">Introduction to the Discovery Questionnaire</span></span>

<span data-ttu-id="5c376-115">목표 주요 결과(OKRS)를 달성하기 위해 이전에 주요 서비스 결정을 내렸다.</span><span class="sxs-lookup"><span data-stu-id="5c376-115">To achieve your objective key results (OKRs), you previously made key service decisions.</span></span> <span data-ttu-id="5c376-116">다음 단계는 환경 검색을 수행하여 IT 인프라, 네트워킹 및 운영과 관련된 모든 측면을 평가하여 조직이 솔루션을 구현할 준비가 됐는지 확인하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5c376-116">The next step is to perform environmental discovery to evaluate all aspects relating to your IT infrastructure, networking, and operations to confirm that your organization is ready to implement the solution.</span></span> <span data-ttu-id="5c376-117">검색은 Teams로의 여정을 계획할 때 취하는 첫 번째 주요 단계 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="5c376-117">Discovery is one of the very first, key steps that you take when planning for your journey to Teams.</span></span> <span data-ttu-id="5c376-118">환경 검색에는 네트워크가 Teams로 업그레이드를 지원할 수 있도록 네트워크 준비 평가가 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c376-118">Environmental discovery must include a network readiness assessment to ensure your network can support upgrading to Teams.</span></span> <span data-ttu-id="5c376-119">환경의 세부 검색을 수행하여 현재 상태를 더 잘 이해하고, Teams 롤아웃 실행을 차단할 수 있는 모든 어려움 또는 더 중요한 것을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c376-119">You perform a detailed discovery of your environment to better understand its current state and to reveal any difficulties or—even more important—possible blockers to the execution of your Teams rollout.</span></span>

<span data-ttu-id="5c376-120">환경 평가 및 채택 준비 평가의 일부로 기술 위험을 식별하고 식별된 각 위험에 대한 완화 계획을 개발합니다.</span><span class="sxs-lookup"><span data-stu-id="5c376-120">You identify technical risks as part of an environmental assessment and adoption readiness evaluation, and develop a mitigation plan for each identified risk.</span></span> <span data-ttu-id="5c376-121">이 정보를 위험 레지스터에 통합해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c376-121">You should incorporate this information in the risk register.</span></span>

<span data-ttu-id="5c376-122">기존 공동 작업 인프라 및 Microsoft 365 또는 Office 365 조직, 네트워킹, 엔드포인트, 운영 및 채택 및 준비와 관련된 모든 문제는 환경 검색 설문지의 일부로 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c376-122">All matters related to your existing collaboration infrastructure and Microsoft 365 or Office 365 organization, networking, endpoints, operations, and adoption and readiness are included as part of the environmental discovery questionnaire.</span></span> <span data-ttu-id="5c376-123">프로젝트 팀과 의하면 요청된 정보를 최대한 세부 정보로 제공하여 계획 활동을 용이하게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c376-123">Work with your project team to provide the requested information with as much detail as possible to facilitate your planning activities.</span></span>

<span data-ttu-id="5c376-124">[설문지가](upgrade-plan-journey-discovery-questionnaire.md) 다음 섹션으로 나뉘어 여러 주요 영역에서 Teams 배포에 대한 조직의 준비를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c376-124">[The questionnaire](upgrade-plan-journey-discovery-questionnaire.md) is divided into the following sections to confirm your organization's readiness for your Teams deployment in several major areas:</span></span>

- <span data-ttu-id="5c376-125">Microsoft 365 또는 Office 365 조직 세부 정보</span><span class="sxs-lookup"><span data-stu-id="5c376-125">Microsoft 365 or Office 365 organization details</span></span>
- <span data-ttu-id="5c376-126">기존 공동 작업 플랫폼 요약</span><span class="sxs-lookup"><span data-stu-id="5c376-126">Existing collaboration platform summary</span></span>
- <span data-ttu-id="5c376-127">공동 작업 플랫폼 배포 세부 정보</span><span class="sxs-lookup"><span data-stu-id="5c376-127">Collaboration platform deployment details</span></span>
- <span data-ttu-id="5c376-128">Microsoft 365 또는 Office 365 서비스에 대한 네트워킹 및 액세스</span><span class="sxs-lookup"><span data-stu-id="5c376-128">Networking and access to Microsoft 365 or Office 365 services</span></span>
- <span data-ttu-id="5c376-129">엔드포인트</span><span class="sxs-lookup"><span data-stu-id="5c376-129">Endpoints</span></span>
- <span data-ttu-id="5c376-130">운영</span><span class="sxs-lookup"><span data-stu-id="5c376-130">Operations</span></span>
- <span data-ttu-id="5c376-131">채택 및 준비</span><span class="sxs-lookup"><span data-stu-id="5c376-131">Adoption and readiness</span></span>

> [!TIP]
> <span data-ttu-id="5c376-132">먼저 Microsoft Word 문서에 설문지 복사를 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c376-132">You can start by copying the questionnaire into a Microsoft Word document.</span></span> <span data-ttu-id="5c376-133">모든 질문에 답변하고 이동할 때 모든 세부 정보를 캡처해 하세요.</span><span class="sxs-lookup"><span data-stu-id="5c376-133">Try to answer all questions and capture all details as you move through.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/><span data-ttu-id="5c376-134">의사 결정 지점</span><span class="sxs-lookup"><span data-stu-id="5c376-134">Decision point</span></span></td><td><ul><li><span data-ttu-id="5c376-135">환경 평가를 완료할 책임이 있는 사람이 누구인가요?</span><span class="sxs-lookup"><span data-stu-id="5c376-135">Who will be responsible for completing an environment assessment?</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next step"/><br/><span data-ttu-id="5c376-136">다음 단계</span><span class="sxs-lookup"><span data-stu-id="5c376-136">Next step</span></span></td><td><ul><li><span data-ttu-id="5c376-137">환경 평가 결과를 문서화합니다.</span><span class="sxs-lookup"><span data-stu-id="5c376-137">Document the results of the environment assessment.</span></span></li></ul></td></tr>
</table>


## <a name="project-team"></a><span data-ttu-id="5c376-138">프로젝트 팀</span><span class="sxs-lookup"><span data-stu-id="5c376-138">Project team</span></span>

<span data-ttu-id="5c376-139">프로젝트 팀에 적합한 인원이 참여하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c376-139">Ensure that you've engaged the right people for your project team.</span></span> <span data-ttu-id="5c376-140">프로젝트 관련자에 대한 참여에서 [완료한 단계를 확인 합니다.](upgrade-enlist-stakeholders.md)</span><span class="sxs-lookup"><span data-stu-id="5c376-140">Verify the steps you completed in [Enlist your project stakeholders](upgrade-enlist-stakeholders.md).</span></span>

<span data-ttu-id="5c376-141">환경을 평가한 후 다음 단계인 서비스 [준비를 진행합니다.](upgrade-prepare-environment-prepare-service.md)</span><span class="sxs-lookup"><span data-stu-id="5c376-141">After you evaluate your environment, proceed to the next step: [Prepare your service](upgrade-prepare-environment-prepare-service.md).</span></span>
