---
title: Microsoft 팀으로 업그레이드 | 비즈니스용 Skype 팀 로드맵
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
audience: admin
description: 현재 비즈니스용 Skype 배포에 따라 Microsoft 팀에 대 한 업그레이드 경로를 선택 합니다.
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
ms.openlocfilehash: 8038b1d04c3deda955465d6262982d0e216e8f23
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836300"
---
<span data-ttu-id="9fd88-103">![배포 및 구현 단계에 주안점을 두어 업그레이드 여행 단계](media/upgrade-banner-deployment.png "배포 및 구현 단계에 주안점을 두어 업그레이드 여행 단계")</span><span class="sxs-lookup"><span data-stu-id="9fd88-103">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="9fd88-104">이 문서는 업그레이드 여행 배포 및 구현 단계의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="9fd88-104">This article is part of the Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="9fd88-105">계속 하기 전에 다음 활동을 완료 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fd88-105">Before proceeding, confirm that you’ve completed the following activities:</span></span>

- [<span data-ttu-id="9fd88-106">프로젝트 이해 관계자 참여</span><span class="sxs-lookup"><span data-stu-id="9fd88-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="9fd88-107">프로젝트 범위 정의</span><span class="sxs-lookup"><span data-stu-id="9fd88-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="9fd88-108">비즈니스용 Skype 및 팀의 공존 성과 상호 운영성 이해</span><span class="sxs-lookup"><span data-stu-id="9fd88-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="9fd88-109">업그레이드 여행 선택</span><span class="sxs-lookup"><span data-stu-id="9fd88-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="9fd88-110">환경 준비</span><span class="sxs-lookup"><span data-stu-id="9fd88-110">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="9fd88-111">조직 준비</span><span class="sxs-lookup"><span data-stu-id="9fd88-111">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)




# <a name="overview"></a><span data-ttu-id="9fd88-112">개요</span><span class="sxs-lookup"><span data-stu-id="9fd88-112">Overview</span></span>

<span data-ttu-id="9fd88-113">팀으로 업그레이드 하기 위해 수행 하는 단계는 비즈니스용 Skype의 현재 배포에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="9fd88-113">The steps you take to perform your upgrade to Teams depends on your current deployment of Skype for Business:</span></span>

1. <span data-ttu-id="9fd88-114">업그레이드를 시작 하기 전에 먼저 [사용자 파일럿을 수행](pilot-essentials.md)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fd88-114">Before beginning your upgrade, be sure you [conduct a user pilot](pilot-essentials.md).</span></span>

2.  <span data-ttu-id="9fd88-115">다음으로 현재 환경에 따라 시작점을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fd88-115">Next, based on your current environment, choose your starting point:</span></span>  

    - <span data-ttu-id="9fd88-116">비즈니스용 **Skype online에서 팀으로 업그레이드 하는 경우**비즈니스용 [Skype online에서 팀으로 업그레이드](https://aka.ms/SkypeToTeams-UpgradeOnline)의 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="9fd88-116">**If you are upgrading from Skype for Business Online to Teams**, follow the steps in [Upgrade from Skype for Business Online to Teams](https://aka.ms/SkypeToTeams-UpgradeOnline).</span></span>

    -  <span data-ttu-id="9fd88-117">**비즈니스용 Skype 온-프레미스 환경에서 업그레이드 하는 경우**사용자를 팀으로 이동 하기 전에 온-프레미스 및 온라인 환경 간에 연결을 설정 하기 위해 몇 가지 추가 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fd88-117">**If you are upgrading from a Skype for Business on-premises environment**, you'll need to perform some extra steps to set up connectivity between your on-premises and online environments before you move your users to Teams.</span></span> <span data-ttu-id="9fd88-118">자세한 내용은 [비즈니스용 Skype 온-프레미스를 팀으로 업그레이드](upgrade-to-teams-execute-SkypeforBusinessHybridOnPrem.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9fd88-118">For more information, see [Upgrade Skype for Business on-premises to Teams](upgrade-to-teams-execute-SkypeforBusinessHybridOnPrem.md).</span></span>





> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]
