---
title: 비즈니스용 Skype에서 팀으로 업그레이드 하기 위한 환경 준비
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: 비즈니스용 Skype에서 팀으로 업그레이드를 시작 하기 전에 환경 및 네트워크 준비 상태를 확인 합니다.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3b1777aaadb1a4a141ec3c80936fa147cd44353d
ms.sourcegitcommit: 75b2cd0d2d39c50dc1e1513860841e2ae3f84324
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/28/2019
ms.locfileid: "36183758"
---
<span data-ttu-id="05b86-103">![여행 다이어그램 업그레이드, 기술 준비 단계 강조] (media/upgrade-banner-tech-readiness.png "기술 준비 단계에 중점을 두어 업그레이드 여행 단계")</span><span class="sxs-lookup"><span data-stu-id="05b86-103">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="05b86-104">이 문서는 사용자 준비 단계와 병행 하 여 완료 한 활동 인 업그레이드 여행에 대 한 기술 준비 단계의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="05b86-104">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="05b86-105">계속 하기 전에 이전 단계에서 다음 활동을 완료 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b86-105">Before proceeding, confirm that you’ve completed these activities from previous stages:</span></span>

- [<span data-ttu-id="05b86-106">프로젝트 이해 관계자 참여</span><span class="sxs-lookup"><span data-stu-id="05b86-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="05b86-107">프로젝트 범위 정의</span><span class="sxs-lookup"><span data-stu-id="05b86-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="05b86-108">비즈니스용 Skype 및 팀의 공존 성과 상호 운영성 이해</span><span class="sxs-lookup"><span data-stu-id="05b86-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="05b86-109">업그레이드 여행 선택</span><span class="sxs-lookup"><span data-stu-id="05b86-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

# <a name="prepare-your-environment-for-upgrading-to-teams"></a><span data-ttu-id="05b86-110">팀으로 업그레이드 하기 위한 환경 준비</span><span class="sxs-lookup"><span data-stu-id="05b86-110">Prepare your environment for upgrading to Teams</span></span>

<span data-ttu-id="05b86-111">조직에서 팀을 업그레이드 하는 데 성공한 경우 현재 비즈니스용 Skype 환경과 네트워크 준비 상태를 확인 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b86-111">To drive a successful Teams upgrade in your organization, it’s important that you validate your current Skype for Business environment and your network readiness.</span></span> <span data-ttu-id="05b86-112">현재 환경을 준비 하면 이제 팀에서 사용자 환경의 품질을 개선 하는 것 외에도 고품질 사용자 환경을 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05b86-112">Preparing your current environment will help ensure a high-quality user experience now, in addition to improving the quality of the user experience in Teams.</span></span> <span data-ttu-id="05b86-113">개별 단계를 계획 하는 데 시간이 걸리는 경우 배포를 가속화 하 고 중요 한 작업 항목을 건너뛰지 않도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05b86-113">Taking time to plan individual steps can help accelerate your deployment and ensure that you haven’t skipped any important action items.</span></span>

<span data-ttu-id="05b86-114">사용자의 준비 준비를 통해 이러한 활동을 병렬로 완료 하세요.</span><span class="sxs-lookup"><span data-stu-id="05b86-114">Complete these activities in parallel with your user readiness preparation:</span></span>

- <span data-ttu-id="05b86-115">성공적인 업그레이드 여행에 필요한 사항을 확인 하는 데 도움이 되도록 [IT 직원을 준비](upgrade-prepare-IT-pros.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b86-115">[Prepare your IT staff](upgrade-prepare-IT-pros.md) to help ensure they have what they need for a successful upgrade journey.</span></span>
- <span data-ttu-id="05b86-116">환경이 모든 [필수 구성 요소](upgrade-plan-journey-prerequisites.md)를 충족 하는지 확인 하 고 Office 365 서비스와 팀 간의 종속성을 이해 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b86-116">Verify that your environment meets all [prerequisites](upgrade-plan-journey-prerequisites.md), and understand dependencies among Office 365 services and Teams.</span></span>
- <span data-ttu-id="05b86-117">팀으로 업그레이드를 성공적으로 진행 하기 위해 조직의 준비 상태를 확인 하는 예제 질문을 사용 하 여 [환경 평가](upgrade-plan-journey-evaluate-environment.md) 를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b86-117">[Evaluate your environment](upgrade-plan-journey-evaluate-environment.md) by performing environmental discovery by using a sample questionnaire to confirm your organization’s readiness to undertake a successful upgrade journey to Teams.</span></span>
- <span data-ttu-id="05b86-118">팀 작업을 지원 하기 위해 네트워크에 대 한 계획, 준비, 필요한 수정 단계 수행을 통해 [네트워크를 준비](upgrade-prepare-environment-prepare-network.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b86-118">[Prepare your network](upgrade-prepare-environment-prepare-network.md) through planning, preparation, and taking any necessary remediation steps for your network to support Teams workloads.</span></span>
- <span data-ttu-id="05b86-119">온 보 딩 검사를 사용 하 여 사용자의 팀 구성이 비즈니스용 Skype에서 팀으로 마이그레이션을 지원할 준비가 되었는지 확인 하기 위해 출시를 위해 [서비스를 준비할](upgrade-prepare-environment-prepare-service.md) 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05b86-119">[Prepare your service](upgrade-prepare-environment-prepare-service.md) for rollout by using onboarding checklists to ensure that your Teams configuration is ready to support migrating your users from Skype for Business to Teams.</span></span>
