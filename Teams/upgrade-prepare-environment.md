---
title: 업그레이드할 환경 준비를 Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: 업그레이드를 시작하기 전에 환경 및 네트워크 준비 비즈니스용 Skype Teams.
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
ms.openlocfilehash: e154dc5844c4b8f3994c8c7bc00865c494a4c8c6
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282145"
---
# <a name="prepare-your-environment-for-upgrading-to-teams"></a><span data-ttu-id="8691e-103">업그레이드할 환경 준비를 Teams</span><span class="sxs-lookup"><span data-stu-id="8691e-103">Prepare your environment for upgrading to Teams</span></span>

<span data-ttu-id="8691e-104">![기술 준비 단계 강조하는 업그레이드 여정 다이어그램](media/upgrade-banner-tech-readiness.png "기술 준비 단계가 강조된 업그레이드 여정의 단계")</span><span class="sxs-lookup"><span data-stu-id="8691e-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="8691e-105">이 문서는 사용자 준비 단계와 병렬로 완료한 작업인 업그레이드 여정의 기술 준비 단계의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="8691e-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="8691e-106">계속하기 전에 이전 단계에서 이러한 작업을 완료한지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8691e-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="8691e-107">프로젝트 관계자 인리스트</span><span class="sxs-lookup"><span data-stu-id="8691e-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="8691e-108">프로젝트 범위 정의</span><span class="sxs-lookup"><span data-stu-id="8691e-108">Defined your project scope</span></span>](./upgrade-define-project-scope.md)
- [<span data-ttu-id="8691e-109">비즈니스용 Skype 및 상호운용성을 Teams</span><span class="sxs-lookup"><span data-stu-id="8691e-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="8691e-110">업그레이드 여정을 선택했습니다.</span><span class="sxs-lookup"><span data-stu-id="8691e-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="8691e-111">조직에서 성공적인 Teams 업그레이드하려면 현재 환경 및 네트워크 비즈니스용 Skype 유효성을 검사하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="8691e-111">To drive a successful Teams upgrade in your organization, it's important that you validate your current Skype for Business environment and your network readiness.</span></span> <span data-ttu-id="8691e-112">현재 환경을 준비하면 이제 사용자 환경의 품질을 개선하는 것 외에도 고품질의 사용자 환경을 보장하는 데 Teams.</span><span class="sxs-lookup"><span data-stu-id="8691e-112">Preparing your current environment will help ensure a high-quality user experience now, in addition to improving the quality of the user experience in Teams.</span></span> <span data-ttu-id="8691e-113">개별 단계를 계획하는 데 시간이 걸린 경우 배포를 가속화하고 중요한 작업 항목을 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="8691e-113">Taking time to plan individual steps can help accelerate your deployment and ensure that you haven't skipped any important action items.</span></span>

<span data-ttu-id="8691e-114">사용자 준비 준비와 병렬로 이러한 작업을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="8691e-114">Complete these activities in parallel with your user readiness preparation:</span></span>

- <span data-ttu-id="8691e-115">[성공적인 업그레이드](upgrade-prepare-IT-pros.md) 여정에 필요한 것을 확보할 수 있도록 IT 직원을 준비합니다.</span><span class="sxs-lookup"><span data-stu-id="8691e-115">[Prepare your IT staff](upgrade-prepare-IT-pros.md) to help ensure they have what they need for a successful upgrade journey.</span></span>
- <span data-ttu-id="8691e-116">환경이 모든 요구 [](upgrade-plan-journey-prerequisites.md)사항을 충족하는지 확인하고 서비스 및 Microsoft 365 서비스 및 Office 365 종속성 Teams.</span><span class="sxs-lookup"><span data-stu-id="8691e-116">Verify that your environment meets all [prerequisites](upgrade-plan-journey-prerequisites.md), and understand dependencies among Microsoft 365 or Office 365 services and Teams.</span></span>
- <span data-ttu-id="8691e-117">[샘플 설문](upgrade-plan-journey-evaluate-environment.md) 조사를 사용하여 환경 검색을 수행하여 환경 검색을 수행하여 조직의 성공적인 업그레이드 여정을 수행하기 위한 준비를 Teams.</span><span class="sxs-lookup"><span data-stu-id="8691e-117">[Evaluate your environment](upgrade-plan-journey-evaluate-environment.md) by performing environmental discovery by using a sample questionnaire to confirm your organization's readiness to undertake a successful upgrade journey to Teams.</span></span>
- <span data-ttu-id="8691e-118">[네트워크에서](prepare-network.md) 워크로드를 지원하기 위해 필요한 모든 수정 단계를 계획, 준비 및 Teams 준비합니다.</span><span class="sxs-lookup"><span data-stu-id="8691e-118">[Prepare your network](prepare-network.md) through planning, preparation, and taking any necessary remediation steps for your network to support Teams workloads.</span></span>
- <span data-ttu-id="8691e-119">[온보더링](upgrade-prepare-environment-prepare-service.md) 검사 목록을 사용하여 서비스를 준비하여 Teams 구성에서 사용자 마이그레이션을 지원할 준비가 비즈니스용 Skype Teams.</span><span class="sxs-lookup"><span data-stu-id="8691e-119">[Prepare your service](upgrade-prepare-environment-prepare-service.md) for rollout by using onboarding checklists to ensure that your Teams configuration is ready to support migrating your users from Skype for Business to Teams.</span></span>