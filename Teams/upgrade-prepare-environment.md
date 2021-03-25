---
title: Teams로 업그레이드하기 위한 환경 준비
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: 비즈니스용 Skype에서 Teams로 업그레이드를 시작하기 전에 환경 및 네트워크 준비의 유효성을 검사합니다.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f75d899f2b14915e265ce8d36c57daeaf0ce72d2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119057"
---
# <a name="prepare-your-environment-for-upgrading-to-teams"></a><span data-ttu-id="958cf-103">Teams로 업그레이드하기 위한 환경 준비</span><span class="sxs-lookup"><span data-stu-id="958cf-103">Prepare your environment for upgrading to Teams</span></span>

<span data-ttu-id="958cf-104">![기술 준비 단계 강조하는 업그레이드 여정 다이어그램](media/upgrade-banner-tech-readiness.png "기술 준비 단계가 강조된 업그레이드 여정의 단계")</span><span class="sxs-lookup"><span data-stu-id="958cf-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="958cf-105">이 문서는 사용자 준비 단계와 병렬로 완료한 작업인 업그레이드 여정의 기술 준비 단계의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="958cf-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="958cf-106">계속하기 전에 이전 단계에서 이러한 작업을 완료한지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="958cf-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="958cf-107">프로젝트 관계자 인리스트</span><span class="sxs-lookup"><span data-stu-id="958cf-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="958cf-108">프로젝트 범위 정의</span><span class="sxs-lookup"><span data-stu-id="958cf-108">Defined your project scope</span></span>](./upgrade-define-project-scope.md)
- [<span data-ttu-id="958cf-109">비즈니스용 Skype 및 Teams의 공존성 및 상호 연동성 이해</span><span class="sxs-lookup"><span data-stu-id="958cf-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="958cf-110">업그레이드 여정을 선택했습니다.</span><span class="sxs-lookup"><span data-stu-id="958cf-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="958cf-111">조직에서 Teams 업그레이드를 성공적으로 진행하려면 현재 비즈니스용 Skype 환경 및 네트워크 준비의 유효성을 검사하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="958cf-111">To drive a successful Teams upgrade in your organization, it's important that you validate your current Skype for Business environment and your network readiness.</span></span> <span data-ttu-id="958cf-112">현재 환경을 준비하면 Teams의 사용자 환경의 품질을 개선하는 것 외에도 고품질의 사용자 환경을 보장하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="958cf-112">Preparing your current environment will help ensure a high-quality user experience now, in addition to improving the quality of the user experience in Teams.</span></span> <span data-ttu-id="958cf-113">개별 단계를 계획하는 데 시간이 걸린 경우 배포를 가속화하고 중요한 작업 항목을 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="958cf-113">Taking time to plan individual steps can help accelerate your deployment and ensure that you haven't skipped any important action items.</span></span>

<span data-ttu-id="958cf-114">사용자 준비 준비와 병렬로 이러한 작업을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="958cf-114">Complete these activities in parallel with your user readiness preparation:</span></span>

- <span data-ttu-id="958cf-115">[성공적인 업그레이드](upgrade-prepare-IT-pros.md) 여정에 필요한 것을 확보할 수 있도록 IT 직원을 준비합니다.</span><span class="sxs-lookup"><span data-stu-id="958cf-115">[Prepare your IT staff](upgrade-prepare-IT-pros.md) to help ensure they have what they need for a successful upgrade journey.</span></span>
- <span data-ttu-id="958cf-116">환경이 모든 요구 [](upgrade-plan-journey-prerequisites.md)사항을 충족하는지 확인하고 Microsoft 365 또는 Office 365 서비스 및 Teams의 종속성 이해.</span><span class="sxs-lookup"><span data-stu-id="958cf-116">Verify that your environment meets all [prerequisites](upgrade-plan-journey-prerequisites.md), and understand dependencies among Microsoft 365 or Office 365 services and Teams.</span></span>
- <span data-ttu-id="958cf-117">[샘플 설문지에서](upgrade-plan-journey-evaluate-environment.md) 환경 검색을 수행하여 환경을 평가하여 Teams로의 성공적인 업그레이드 여정을 수행할 조직의 준비를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="958cf-117">[Evaluate your environment](upgrade-plan-journey-evaluate-environment.md) by performing environmental discovery by using a sample questionnaire to confirm your organization's readiness to undertake a successful upgrade journey to Teams.</span></span>
- <span data-ttu-id="958cf-118">[Teams 워크로드를](prepare-network.md) 지원하기 위해 네트워크에 필요한 모든 수정 단계를 계획, 준비 및 수행하여 네트워크를 준비합니다.</span><span class="sxs-lookup"><span data-stu-id="958cf-118">[Prepare your network](prepare-network.md) through planning, preparation, and taking any necessary remediation steps for your network to support Teams workloads.</span></span>
- <span data-ttu-id="958cf-119">[온보링](upgrade-prepare-environment-prepare-service.md) 검사 목록을 사용하여 서비스를 준비하여 Teams 구성이 비즈니스용 Skype에서 Teams로 사용자를 마이그레이션할 준비가 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="958cf-119">[Prepare your service](upgrade-prepare-environment-prepare-service.md) for rollout by using onboarding checklists to ensure that your Teams configuration is ready to support migrating your users from Skype for Business to Teams.</span></span>