---
title: Microsoft Teams로 업그레이드 구현 개요
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: 현재 비즈니스용 Skype 배포를 기반으로 Microsoft Teams에 대한 최적의 업그레이드 경로를 결정하세요.
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
ms.openlocfilehash: 0db2e752bb163f806c5dcba7aa56fc36bae7c2ef
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578361"
---
# <a name="overview-of-implementing-your-upgrade"></a><span data-ttu-id="a2757-103">업그레이드 구현 개요</span><span class="sxs-lookup"><span data-stu-id="a2757-103">Overview of implementing your upgrade</span></span>

<span data-ttu-id="a2757-104">![배포 및 구현 단계에 강조를 두는 업그레이드 단계](media/upgrade-banner-deployment.png "배포 및 구현 단계에 강조를 두는 업그레이드 단계")</span><span class="sxs-lookup"><span data-stu-id="a2757-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="a2757-105">이 문서는 업그레이드 여정의 배포 및 구현 단계의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="a2757-105">This article is part of the Deployment and Implementation stage of your upgrade journey.</span></span> 



## <a name="prerequisite-planning-activities"></a><span data-ttu-id="a2757-106">전제적 계획 활동</span><span class="sxs-lookup"><span data-stu-id="a2757-106">Prerequisite planning activities</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a2757-107">업그레이드 구현을 계속하기 전에 업그레이드 계획부터 계획 콘텐츠를 읽은 후 모든 전제적 계획 활성화를 완료해야 합니다. [](upgrade-plan-journey.md)</span><span class="sxs-lookup"><span data-stu-id="a2757-107">Before proceeding with your upgrade implementation, confirm that you've read the planning content starting with [Plan your upgrade](upgrade-plan-journey.md) to ensure you've completed all prerequisite planning activites.</span></span>


- [<span data-ttu-id="a2757-108">프로젝트 관련자에 참여</span><span class="sxs-lookup"><span data-stu-id="a2757-108">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="a2757-109">프로젝트 범위 정의</span><span class="sxs-lookup"><span data-stu-id="a2757-109">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="a2757-110">비즈니스용 Skype 및 Teams의 공존 및 상호 연동성 이해</span><span class="sxs-lookup"><span data-stu-id="a2757-110">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="a2757-111">업그레이드 여정 선택</span><span class="sxs-lookup"><span data-stu-id="a2757-111">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="a2757-112">사용자 파일럿 계획</span><span class="sxs-lookup"><span data-stu-id="a2757-112">Planned a user pilot</span></span>](pilot-essentials.md)
- [<span data-ttu-id="a2757-113">환경 준비</span><span class="sxs-lookup"><span data-stu-id="a2757-113">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="a2757-114">조직 준비</span><span class="sxs-lookup"><span data-stu-id="a2757-114">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)

## <a name="choose-your-upgrade-starting-point"></a><span data-ttu-id="a2757-115">업그레이드 시작점 선택</span><span class="sxs-lookup"><span data-stu-id="a2757-115">Choose your upgrade starting point</span></span>

<span data-ttu-id="a2757-116">Teams로 업그레이드하는 단계는 비즈니스용 Skype의 현재 배포에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2757-116">The steps you take to perform your upgrade to Teams depends on your current deployment of Skype for Business:</span></span>

<span data-ttu-id="a2757-117">현재 환경에 따라 시작 지점을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2757-117">Based on your current environment, choose your starting point:</span></span>  

- <span data-ttu-id="a2757-118">**비즈니스용 Skype Online에서 Teams로** 업그레이드하는 경우 비즈니스용 [Skype Online에서](https://aka.ms/SkypeToTeams-UpgradeOnline)Teams로 업그레이드의 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="a2757-118">**If you are upgrading from Skype for Business Online to Teams**, follow the steps in [Upgrade from Skype for Business Online to Teams](https://aka.ms/SkypeToTeams-UpgradeOnline).</span></span>

-  <span data-ttu-id="a2757-119">**비즈니스용 Skype On-프레미스** 환경에서 업그레이드하는 경우 사용자를 Teams로 이동하기 전에 몇 가지 추가 단계를 수행하여 사용자와 온라인 환경 간의 연결을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2757-119">**If you are upgrading from a Skype for Business on-premises environment**, you'll need to perform some extra steps to set up connectivity between your on-premises and online environments before you move your users to Teams.</span></span> <span data-ttu-id="a2757-120">자세한 내용은 비즈니스용 [Skype-프레미스에서 Teams로 업그레이드를 참조하세요.](upgrade-to-teams-execute-SkypeforBusinessHybridOnPrem.md)</span><span class="sxs-lookup"><span data-stu-id="a2757-120">For more information, see [Upgrade Skype for Business on-premises to Teams](upgrade-to-teams-execute-SkypeforBusinessHybridOnPrem.md).</span></span>





> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]
