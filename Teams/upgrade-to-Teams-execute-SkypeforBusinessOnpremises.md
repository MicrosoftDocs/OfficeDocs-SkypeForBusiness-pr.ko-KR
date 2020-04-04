---
title: 비즈니스용 Skype 온-프레미스를 Teams로 업그레이드
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: 비즈니스용 Skype 또는 Microsoft Lync 온-프레미스 배포에서 팀으로 업그레이드 하기 위한 고려 사항
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
ms.openlocfilehash: 8f4e5dc3d7ed2aa215997f6f83e09fa71b3ff6df
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43139617"
---
# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a><span data-ttu-id="9d3e7-103">비즈니스용 Skype 온-프레미스 배포에서 팀으로 업그레이드</span><span class="sxs-lookup"><span data-stu-id="9d3e7-103">Upgrade from a Skype for Business on-premises deployment to Teams</span></span>

<span data-ttu-id="9d3e7-104">![배포 및 구현 단계에 주안점을 두어 업그레이드 여행 단계](media/upgrade-banner-deployment.png "배포 및 구현 단계에 주안점을 두어 업그레이드 여행 단계")</span><span class="sxs-lookup"><span data-stu-id="9d3e7-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="9d3e7-105">이 문서는 업그레이드 여행 배포 및 구현 단계의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="9d3e7-105">This article is part of the Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="9d3e7-106">계속 하기 전에 다음 활동을 완료 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d3e7-106">Before proceeding, confirm that you've completed the following activities:</span></span>

- [<span data-ttu-id="9d3e7-107">프로젝트 이해 관계자 참여</span><span class="sxs-lookup"><span data-stu-id="9d3e7-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="9d3e7-108">프로젝트 범위 정의</span><span class="sxs-lookup"><span data-stu-id="9d3e7-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="9d3e7-109">비즈니스용 Skype 및 팀의 공존 성과 상호 운영성 이해</span><span class="sxs-lookup"><span data-stu-id="9d3e7-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="9d3e7-110">업그레이드 여행 선택</span><span class="sxs-lookup"><span data-stu-id="9d3e7-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="9d3e7-111">환경 준비</span><span class="sxs-lookup"><span data-stu-id="9d3e7-111">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="9d3e7-112">조직 준비</span><span class="sxs-lookup"><span data-stu-id="9d3e7-112">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="9d3e7-113">파일럿 수행</span><span class="sxs-lookup"><span data-stu-id="9d3e7-113">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

<span data-ttu-id="9d3e7-114">비즈니스용 Skype 또는 Microsoft Lync 온-프레미스를 배포 하 고 조직에서 Microsoft 팀으로 업그레이드 하려는 사용자가 여러 공존 모드를 사용 하거나 모두 하는 경우에는이 문서의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="9d3e7-114">Follow the guidance in this article if you've deployed Skype for Business or Microsoft Lync on-premises and your organization wants to upgrade to Microsoft Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a><span data-ttu-id="9d3e7-115">1 단계: 하이브리드 연결 배포</span><span class="sxs-lookup"><span data-stu-id="9d3e7-115">Step 1: Deploy hybrid connectivity</span></span>

<span data-ttu-id="9d3e7-116">사용자를 팀으로 업그레이드 하기 위한 주요 전제 조건은 하이브리드 연결을 배포 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9d3e7-116">The key prerequisite for upgrading your users to Teams is to deploy hybrid connectivity.</span></span>

<span data-ttu-id="9d3e7-117">자세한 내용은 비즈니스용 [Skype 서버 간 하이브리드 연결 배포 및 비즈니스용 Skype Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9d3e7-117">For more information, see [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)</span></span>

## <a name="step-2-implement-your-chosen-upgrade-journey-for-your-organization"></a><span data-ttu-id="9d3e7-118">2 단계: 조직에 대해 선택한 업그레이드 여행 구현</span><span class="sxs-lookup"><span data-stu-id="9d3e7-118">Step 2: Implement your chosen upgrade journey for your organization</span></span>

<span data-ttu-id="9d3e7-119">하이브리드 설정을 완료 한 후 사용자를 Office 365으로 이동 하도록 계획할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d3e7-119">After you've completed your hybrid setup, you can plan to move your users to Office 365.</span></span>

<span data-ttu-id="9d3e7-120">자세한 내용은 다음을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9d3e7-120">For more information, see:</span></span>

- <span data-ttu-id="9d3e7-121">[TeamsUpgradePolicy: 마이그레이션 및 공존 관리](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span><span class="sxs-lookup"><span data-stu-id="9d3e7-121">[TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

- <span data-ttu-id="9d3e7-122">[온-프레미스에서 비즈니스용 Skype Online으로 사용자를 이동](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)합니다.</span><span class="sxs-lookup"><span data-stu-id="9d3e7-122">[Move users from on premises to Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="9d3e7-123">전화 시스템 및 팀 업그레이드</span><span class="sxs-lookup"><span data-stu-id="9d3e7-123">Phone System and Teams upgrade</span></span>

<span data-ttu-id="9d3e7-124">온-프레미스 전화 시스템에서 팀으로 전환 하면 전화 시스템 다이렉트 라우팅 ("직접 라우팅") 또는 Office 365에 대 한 Microsoft 제공 전화 요금제를 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d3e7-124">Transitioning from on-premises phone systems to Teams will allow you to take advantage of Phone System Direct Routing ("Direct Routing") or the Microsoft-provided Calling Plans for Office 365.</span></span>

<span data-ttu-id="9d3e7-125">Office 365에서 통화 요금제를 사용 하 고 있지 않은 경우에는 팀으로 업그레이드 하는 과정의 일부로 서 엔터프라이즈 음성 배포를 전화 시스템 다이렉트 라우팅으로 전환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d3e7-125">If you're not using Calling Plans in Office 365, you need to transition your enterprise voice deployment to Phone System Direct Routing as part of your upgrade to Teams.</span></span>

<span data-ttu-id="9d3e7-126">자세한 내용은 [전화 시스템 다이렉트 라우팅에 대 한 추가 고려 사항을](https://docs.microsoft.com/MicrosoftTeams/2-envision-make-my-service-decisions-direct-routing)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9d3e7-126">For more information, see [additional considerations for Phone System Direct Routing](https://docs.microsoft.com/MicrosoftTeams/2-envision-make-my-service-decisions-direct-routing).</span></span> <span data-ttu-id="9d3e7-127">Office 365에서 통화 계획을 사용할 계획 이라면 [팀에 전화 번호를 전송](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)하는 지침을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9d3e7-127">If you are planning to use Calling Plans in Office 365, please refer to our guidance for [transferring your phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>