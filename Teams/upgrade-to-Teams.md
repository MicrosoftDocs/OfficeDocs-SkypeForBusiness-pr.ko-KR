---
title: Microsoft Teams로 업그레이드 구현 개요
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: 현재 비즈니스용 Skype 배포를 기반으로 Microsoft Teams에 대한 최적의 업그레이드 경로를 결정합니다.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3eb6c65d414217810c795aa72701a8e546f30643
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096032"
---
# <a name="overview-of-implementing-your-upgrade"></a><span data-ttu-id="c8fa9-103">업그레이드 구현 개요</span><span class="sxs-lookup"><span data-stu-id="c8fa9-103">Overview of implementing your upgrade</span></span>

<span data-ttu-id="c8fa9-104">![배포 및 구현 단계에 주안점 있는 업그레이드 여정의 단계](media/upgrade-banner-deployment.png "배포 및 구현 단계에 주안점 있는 업그레이드 여정의 단계")</span><span class="sxs-lookup"><span data-stu-id="c8fa9-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="c8fa9-105">이 문서는 업그레이드 여정의 배포 및 구현 단계의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="c8fa9-105">This article is part of the Deployment and Implementation stage of your upgrade journey.</span></span> 



## <a name="prerequisite-planning-activities"></a><span data-ttu-id="c8fa9-106">전제적 계획 활동</span><span class="sxs-lookup"><span data-stu-id="c8fa9-106">Prerequisite planning activities</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c8fa9-107">업그레이드 구현을 진행하기 전에 업그레이드 계획부터 계획 내용을 읽은 후 모든 전제적 계획 활동이 완료되도록 합니다. [](upgrade-plan-journey.md)</span><span class="sxs-lookup"><span data-stu-id="c8fa9-107">Before proceeding with your upgrade implementation, confirm that you've read the planning content starting with [Plan your upgrade](upgrade-plan-journey.md) to ensure you've completed all prerequisite planning activites.</span></span>


- [<span data-ttu-id="c8fa9-108">프로젝트 관계자 인리스트</span><span class="sxs-lookup"><span data-stu-id="c8fa9-108">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="c8fa9-109">프로젝트 범위 정의</span><span class="sxs-lookup"><span data-stu-id="c8fa9-109">Defined your project scope</span></span>](./upgrade-define-project-scope.md)
- [<span data-ttu-id="c8fa9-110">비즈니스용 Skype 및 Teams의 공존성 및 상호 연동성 이해</span><span class="sxs-lookup"><span data-stu-id="c8fa9-110">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="c8fa9-111">업그레이드 여정을 선택했습니다.</span><span class="sxs-lookup"><span data-stu-id="c8fa9-111">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="c8fa9-112">사용자 파일럿 계획</span><span class="sxs-lookup"><span data-stu-id="c8fa9-112">Planned a user pilot</span></span>](pilot-essentials.md)
- [<span data-ttu-id="c8fa9-113">환경 준비</span><span class="sxs-lookup"><span data-stu-id="c8fa9-113">Prepared your environment</span></span>](./upgrade-prepare-environment.md)
- [<span data-ttu-id="c8fa9-114">조직 준비</span><span class="sxs-lookup"><span data-stu-id="c8fa9-114">Prepared your organization</span></span>](./upgrade-prepare-organization.md)

## <a name="choose-your-upgrade-starting-point"></a><span data-ttu-id="c8fa9-115">업그레이드 시작 지점 선택</span><span class="sxs-lookup"><span data-stu-id="c8fa9-115">Choose your upgrade starting point</span></span>

<span data-ttu-id="c8fa9-116">Teams로 업그레이드를 수행하는 단계는 비즈니스용 Skype의 현재 배포에 따라 달라 니다.</span><span class="sxs-lookup"><span data-stu-id="c8fa9-116">The steps you take to perform your upgrade to Teams depends on your current deployment of Skype for Business:</span></span>

<span data-ttu-id="c8fa9-117">현재 환경에 따라 시작 지점을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="c8fa9-117">Based on your current environment, choose your starting point:</span></span>  

- <span data-ttu-id="c8fa9-118">**비즈니스용 Skype Online에서 Teams로** 업그레이드하는 경우 비즈니스용 [Skype Online에서 Teams로 업그레이드의](./upgrade-to-teams-execute-skypeforbusinessonline.md)단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="c8fa9-118">**If you are upgrading from Skype for Business Online to Teams**, follow the steps in [Upgrade from Skype for Business Online to Teams](./upgrade-to-teams-execute-skypeforbusinessonline.md).</span></span>

-  <span data-ttu-id="c8fa9-119">**비즈니스용 Skype온-프레미스** 환경에서 업그레이드하는 경우 사용자를 Teams로 이동하기 전에 프레미스와 온라인 환경 간에 연결을 설정하기 위해 몇 가지 추가 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8fa9-119">**If you are upgrading from a Skype for Business on-premises environment**, you'll need to perform some extra steps to set up connectivity between your on-premises and online environments before you move your users to Teams.</span></span> <span data-ttu-id="c8fa9-120">자세한 내용은 비즈니스용 [Skype On-Premises에서 Teams로 업그레이드를 참조하세요.](upgrade-to-teams-execute-SkypeforBusinessHybridOnPrem.md)</span><span class="sxs-lookup"><span data-stu-id="c8fa9-120">For more information, see [Upgrade Skype for Business on-premises to Teams](upgrade-to-teams-execute-SkypeforBusinessHybridOnPrem.md).</span></span>





> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]