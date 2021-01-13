---
title: 비즈니스용 Skype 온-프레미스를 Teams로 업그레이드
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 비즈니스용 Skype-프레미스 배포에서 조직을 Microsoft Teams로 전환하는 방법을 배워보는 것이 좋습니다.
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
ms.openlocfilehash: 90542f680c1d3992f5f318bfedad8a12470d282b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820948"
---
# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a><span data-ttu-id="944a2-103">비즈니스용 Skype-프레미스 배포에서 Teams로 업그레이드</span><span class="sxs-lookup"><span data-stu-id="944a2-103">Upgrade from a Skype for Business on-premises deployment to Teams</span></span>

<span data-ttu-id="944a2-104">![배포 및 구현 단계에 강조를 두는 업그레이드 단계](media/upgrade-banner-deployment.png "배포 및 구현 단계에 강조를 두는 업그레이드 단계")</span><span class="sxs-lookup"><span data-stu-id="944a2-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="944a2-105">이 문서는 업그레이드 여정의 배포 및 구현 단계의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="944a2-105">This article is part of the Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="944a2-106">계속하기 전에 다음 활동을 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="944a2-106">Before proceeding, confirm that you've completed the following activities:</span></span>

- [<span data-ttu-id="944a2-107">프로젝트 이해 관계자에 참여</span><span class="sxs-lookup"><span data-stu-id="944a2-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="944a2-108">프로젝트 범위 정의</span><span class="sxs-lookup"><span data-stu-id="944a2-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="944a2-109">비즈니스용 Skype 및 Teams의 공존성 및 상호 연동성 이해</span><span class="sxs-lookup"><span data-stu-id="944a2-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="944a2-110">업그레이드 여정 선택</span><span class="sxs-lookup"><span data-stu-id="944a2-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="944a2-111">환경 준비</span><span class="sxs-lookup"><span data-stu-id="944a2-111">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="944a2-112">조직 준비</span><span class="sxs-lookup"><span data-stu-id="944a2-112">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="944a2-113">파일럿 수행</span><span class="sxs-lookup"><span data-stu-id="944a2-113">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

<span data-ttu-id="944a2-114">비즈니스용 Skype 또는 Microsoft Lync 온-프레미스를 배포하고 조직에서 여러 공존 모드를 사용하여 선택적으로 또는 모든 기능을 사용하여 Microsoft Teams로 업그레이드하려는 경우 이 문서의 지침을 따르하세요.</span><span class="sxs-lookup"><span data-stu-id="944a2-114">Follow the guidance in this article if you've deployed Skype for Business or Microsoft Lync on-premises and your organization wants to upgrade to Microsoft Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a><span data-ttu-id="944a2-115">1단계: 하이브리드 연결 배포</span><span class="sxs-lookup"><span data-stu-id="944a2-115">Step 1: Deploy hybrid connectivity</span></span>

<span data-ttu-id="944a2-116">사용자를 Teams로 업그레이드하기 위한 주요 구성은 하이브리드 연결을 배포하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="944a2-116">The key prerequisite for upgrading your users to Teams is to deploy hybrid connectivity.</span></span>

<span data-ttu-id="944a2-117">자세한 내용은 비즈니스용 Skype Server와 비즈니스용 Skype Online 간에 하이브리드 연결 [배포를 참조하세요.](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)</span><span class="sxs-lookup"><span data-stu-id="944a2-117">For more information, see [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)</span></span>

## <a name="step-2-implement-your-chosen-upgrade-journey-for-your-organization"></a><span data-ttu-id="944a2-118">2단계: 조직에 대해 선택한 업그레이드 여정 구현</span><span class="sxs-lookup"><span data-stu-id="944a2-118">Step 2: Implement your chosen upgrade journey for your organization</span></span>

<span data-ttu-id="944a2-119">하이브리드 설정을 완료한 후 사용자를 Microsoft 365 또는 Office 365로 이동할 계획입니다.</span><span class="sxs-lookup"><span data-stu-id="944a2-119">After you've completed your hybrid setup, you can plan to move your users to Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="944a2-120">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="944a2-120">For more information, see:</span></span>

- <span data-ttu-id="944a2-121">[TeamsUpgradePolicy: 마이그레이션](upgrade-to-teams-on-prem-tools.md)및 공존 관리.</span><span class="sxs-lookup"><span data-stu-id="944a2-121">[TeamsUpgradePolicy: managing migration and coexistence](upgrade-to-teams-on-prem-tools.md).</span></span>

- <span data-ttu-id="944a2-122">[사용자를 비즈니스용 Skype Online으로 프레미스에서 이동](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)</span><span class="sxs-lookup"><span data-stu-id="944a2-122">[Move users from on premises to Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="944a2-123">전화 시스템 및 Teams 업그레이드</span><span class="sxs-lookup"><span data-stu-id="944a2-123">Phone System and Teams upgrade</span></span>

<span data-ttu-id="944a2-124">전화 시스템 다이렉트 라우팅("직접 라우팅") 또는 Microsoft에서 제공한 Microsoft 365 또는 Office 365 통화 요금제의 장점을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="944a2-124">Transitioning from on-premises phone systems to Teams will allow you to take advantage of Phone System Direct Routing ("Direct Routing") or the Microsoft-provided Calling Plans for Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="944a2-125">통화 계획을 사용하지 않는 경우 Teams로 업그레이드하는 동안 엔터프라이즈 음성 배포를 전화 시스템 직접 라우팅으로 전환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="944a2-125">If you're not using Calling Plans, you need to transition your enterprise voice deployment to Phone System Direct Routing as part of your upgrade to Teams.</span></span>

<span data-ttu-id="944a2-126">자세한 내용은 전화 시스템 직접 라우팅에 대한 추가 [고려 사항을 참조하세요.](https://docs.microsoft.com/MicrosoftTeams/2-envision-make-my-service-decisions-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="944a2-126">For more information, see [additional considerations for Phone System Direct Routing](https://docs.microsoft.com/MicrosoftTeams/2-envision-make-my-service-decisions-direct-routing).</span></span> <span data-ttu-id="944a2-127">통화 요금제 사용을 계획하는 경우 전화 번호를 Teams로 이전하기 위한 지침을 [참조하세요.](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)</span><span class="sxs-lookup"><span data-stu-id="944a2-127">If you are planning to use Calling Plans, please refer to our guidance for [transferring your phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>