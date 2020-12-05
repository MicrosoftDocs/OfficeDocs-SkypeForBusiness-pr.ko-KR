---
title: 비즈니스용 Skype-프레미스를 Microsoft Teams로 업그레이드
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 비즈니스용 Skype-프레미스 배포에서 Microsoft Teams로 조직을 업그레이드하는 방법을 배워야 합니다.
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
ms.openlocfilehash: 961ac4f9bcce3c24d62ec1c744d2c9cd15e2ee1b
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578171"
---
# <a name="upgrade-from-skype-for-business-on-premises-to-teams"></a><span data-ttu-id="09745-103">비즈니스용 Skype-프레미스에서 Teams로 업그레이드</span><span class="sxs-lookup"><span data-stu-id="09745-103">Upgrade from Skype for Business on-premises to Teams</span></span>

<span data-ttu-id="09745-104">![배포 및 구현을 강조하는 업그레이드 여정 다이어그램](media/upgrade-banner-deployment.png "배포 및 구현 단계에 강조를 두는 업그레이드 단계")</span><span class="sxs-lookup"><span data-stu-id="09745-104">![Upgrade journey diagram, emphasizing Deployment and Implementation](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="09745-105">이 문서는 업그레이드 여정의 배포 및 구현 단계의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="09745-105">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="09745-106">계속하기 전에 다음 활동을 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09745-106">Before proceeding, confirm that you've completed the following activities:</span></span>

-   [<span data-ttu-id="09745-107">프로젝트 관련자에 참여</span><span class="sxs-lookup"><span data-stu-id="09745-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
-   [<span data-ttu-id="09745-108">프로젝트 범위 정의</span><span class="sxs-lookup"><span data-stu-id="09745-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
-   [<span data-ttu-id="09745-109">비즈니스용 Skype 및 Teams의 공존 및 상호 연동성 이해</span><span class="sxs-lookup"><span data-stu-id="09745-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
-   [<span data-ttu-id="09745-110">업그레이드 여정 선택</span><span class="sxs-lookup"><span data-stu-id="09745-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [<span data-ttu-id="09745-111">환경 준비</span><span class="sxs-lookup"><span data-stu-id="09745-111">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
-   [<span data-ttu-id="09745-112">조직 준비</span><span class="sxs-lookup"><span data-stu-id="09745-112">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
-   [<span data-ttu-id="09745-113">파일럿 수행</span><span class="sxs-lookup"><span data-stu-id="09745-113">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

<span data-ttu-id="09745-114">비즈니스용 Skype Server 또는 Microsoft Lync 온-프레미스를 배포하고 조직에서 Teams로 업그레이드하려는 경우 이 문서의 지침을 따르하세요.</span><span class="sxs-lookup"><span data-stu-id="09745-114">If you've deployed Skype for Business Server or Microsoft Lync on-premises and your organization wants to upgrade to Teams, follow the guidance in this article.</span></span> <span data-ttu-id="09745-115">단계적으로 사용자를 Teams로 이동하는 경우 Microsoft 365 또는 Office 365 조직과 하이브리드 연결을 설정하고 공존 요구 사항을 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09745-115">You need to set up hybrid connectivity with your Microsoft 365 or Office 365 organization, and determine coexistence requirements if you are moving your users to Teams in phases.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="09745-116">비즈니스용 Skype Online은 2021년 7월 31일에 서비스가 종료되며 이후에는 더 이상 액세스할 수 없게 되거나 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09745-116">Skype for Business Online will be retired on July 31, 2021, after which it will no longer be accessible or supported.</span></span> <span data-ttu-id="09745-117">혜택 구현을 극대화하고 조직이 업그레이드를 구현할 수 있는 적절한 시간을 확보하려면 지금 Microsoft Teams로의 여정을 시작하는 것이 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="09745-117">To maximize benefit realization and ensure your organization has proper time to implement your upgrade, we encourage you to begin your journey to Microsoft Teams today.</span></span> <span data-ttu-id="09745-118">성공적인 업그레이드는 기술 및 사용자 준비를 맞추기 때문에 Microsoft Teams로의 여정을 탐색할 때 여기에 설명된 지침을 활용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09745-118">Remember that a successful upgrade aligns technical and user readiness, so be sure to leverage the guidance herein as you navigate your journey to Microsoft Teams.</span></span>

## <a name="step-1-configure-hybrid-connectivity"></a><span data-ttu-id="09745-119">1단계: 하이브리드 연결 구성</span><span class="sxs-lookup"><span data-stu-id="09745-119">Step 1: Configure hybrid connectivity</span></span> 

<span data-ttu-id="09745-120">온라인 프레미스 사용자를 Teams로 업그레이드하기 위한 주요 구성 구성은 비즈니스용 Skype 서버의 온라인 배포에 대한 하이브리드 연결을 구성하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="09745-120">The key prerequisite for upgrading your on-premises users to Teams is to configure hybrid connectivity for your Skype for Business Server on-premises deployment.</span></span> 

<span data-ttu-id="09745-121">하이브리드 연결 [계획부터 시작한](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) 다음 하이브리드 연결 구성에 설명된 [작업을 수행합니다.](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)</span><span class="sxs-lookup"><span data-stu-id="09745-121">Start by reading [Plan hybrid connectivity](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) and then follow the tasks outlined in [Configure hybrid connectivity](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity).</span></span>


## <a name="step-2-set-transitional-coexistence-mode-optional"></a><span data-ttu-id="09745-122">2단계: 전환 공존 모드 설정(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="09745-122">Step 2: Set transitional coexistence mode (optional)</span></span>

<span data-ttu-id="09745-123">비즈니스용 Skype와 Teams 클라이언트와 사용자 간의 공존 및 상호 운영성은 Teams 업그레이드 모드로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="09745-123">Coexistence and interoperability between Skype for Business and Teams clients and users are defined by Teams Upgrade modes.</span></span>  <span data-ttu-id="09745-124">기본적으로 조직은 사용자가 Teams 및 비즈니스용 Skype 클라이언트를 나란히 사용할 수 있도록 하는 제도 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="09745-124">By default, organizations are in Islands mode, which allows users to use both Teams and Skype for Business clients side by side.</span></span>

<span data-ttu-id="09745-125">Teams로 전환하는 조직의 경우 TeamsOnly 모드는 각 사용자의 최종 대상입니다. 하지만 모든 사용자에게 TeamsOnly(또는 다른 모드)를 동시에 할당해야 하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="09745-125">For an organization moving to Teams, TeamsOnly mode is the final destination for each user--though not all users need to be assigned TeamsOnly (or any other mode) at the same time.</span></span>

<span data-ttu-id="09745-126">사용자가 TeamsOnly 모드에 도달하기 전에 조직은 선택적으로 비즈니스용 Skype 공존 모드를 사용하여 TeamsOnly 모드에 있는 사용자와 아직 그렇지 않은 사용자 간에 예측 가능한 통신을 보장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09745-126">Prior to users reaching TeamsOnly mode, organizations can optionally use any of the Skype for Business coexistence modes to ensure predictable communication between users who are in TeamsOnly mode and users who aren't yet.</span></span>  <span data-ttu-id="09745-127">비즈니스용 Skype 공존 모드(SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings)의 목적은 조직이 비즈니스용 Skype에서 Teams로 전환할 때 최종 사용자에게 간단하고 예측 가능한 환경을 제공하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="09745-127">The purpose of the Skype for Business coexistence modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) is to provide a simple, predictable experience for end users as organizations transition from Skype for Business to Teams.</span></span> 

<span data-ttu-id="09745-128">사용자가 비즈니스용 Skype 모드에 있는 경우 들어오는 모든 채팅 및 통화가 사용자의 비즈니스용 Skype 클라이언트로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="09745-128">When a user is in any of the Skype for Business modes, all incoming chats and calls are routed to the user's Skype for Business client.</span></span> <span data-ttu-id="09745-129">최종 사용자 혼동을 방지하고 적절한 라우팅을 보장하기 위해 사용자가 비즈니스용 Skype 모드에 있는 경우 Teams 클라이언트의 통화 및 채팅 기능이 비활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="09745-129">To avoid end-user confusion and ensure proper routing, calling and chat functionality in the Teams client is disabled when a user is in any of the Skype for Business modes.</span></span> <span data-ttu-id="09745-130">마찬가지로 사용자가 SfBOnly 또는 SfBWithTeamsCollab 모드에 있는 경우 Teams의 모임 예정이 명시적으로 비활성화되어 사용자가 SfBWithTeamsCollabAndMeetings 모드에 있는 경우 명시적으로 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="09745-130">Similarly, meeting scheduling in Teams is explicitly disabled when users are in the SfBOnly or SfBWithTeamsCollab modes, and explicitly enabled when a user is in the SfBWithTeamsCollabAndMeetings mode.</span></span>

<span data-ttu-id="09745-131">요구 사항에 따라 조직에서 선택한 업그레이드 경로에 따라 적절한 공존 모드를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09745-131">Depending on your requirements, you can assign the appropriate coexistence mode based on the upgrade path that your organization has chosen.</span></span> <span data-ttu-id="09745-132">자세한 내용은 비즈니스용 Skype와 함께 [Teams를](migration-interop-guidance-for-teams-with-skype.md) 사용하는 조직에 대한 마이그레이션 및 상호 운영성 지침 및 공존 및 업그레이드 설정을 [참조하세요.](https://aka.ms/SkypeToTeams-SetCoexistence)</span><span class="sxs-lookup"><span data-stu-id="09745-132">For more information, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](migration-interop-guidance-for-teams-with-skype.md) and [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence).</span></span>


## <a name="step-3-move-users-from-skype-for-business-on-premises-to-teams-only"></a><span data-ttu-id="09745-133">3단계: 비즈니스용 Skype의 사용자를 비즈니스용 Skype-프레미스에서 Teams로만 이동</span><span class="sxs-lookup"><span data-stu-id="09745-133">Step 3: Move users from Skype for Business on-premises to Teams Only</span></span>

<span data-ttu-id="09745-134">궁극적으로 사용자를 TeamsOnly 모드로 이동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09745-134">Ultimately, you'll want to move your users to TeamsOnly mode.</span></span> <span data-ttu-id="09745-135">여기에는 한 두 단계가 수행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09745-135">This might involve one or two steps depending on your on-premises environment.</span></span>  

<span data-ttu-id="09745-136">자세한 내용은 [사용자를](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud) 프레미스와 클라우드 간에 이동하고 사용자를 프레미스에서 [Teams로 이동을 참조하세요.](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams)</span><span class="sxs-lookup"><span data-stu-id="09745-136">For more information, see [Move users between on-premises and the cloud](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud) and [Move users from on-premises to Teams](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams).</span></span> 

## <a name="step-4-disable-hybrid-to-complete-your-migration-to-the-cloud"></a><span data-ttu-id="09745-137">4단계: 하이브리드를 사용하지 않도록 설정하여 클라우드로 마이그레이션 완료</span><span class="sxs-lookup"><span data-stu-id="09745-137">Step 4: Disable hybrid to complete your migration to the cloud</span></span>

<span data-ttu-id="09745-138">모든 사용자를 프레미스에서 클라우드로 이동한 후, 비즈니스용 Skype 배포를 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09745-138">After you have moved all users from on-premises to the cloud, you can decommission the on-premises Skype for Business deployment.</span></span> <span data-ttu-id="09745-139">자세한 내용은 클라우드로 마이그레이션을 완료하기 위해 하이브리드 사용 안 [을 참조하세요.](https://docs.microsoft.com/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)</span><span class="sxs-lookup"><span data-stu-id="09745-139">For more information, see [Disable hybrid to complete migration to the cloud](https://docs.microsoft.com/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid).</span></span>


## <a name="phone-system-and-pstn-connectivity-options"></a><span data-ttu-id="09745-140">전화 시스템 및 PSTN 연결 옵션</span><span class="sxs-lookup"><span data-stu-id="09745-140">Phone System and PSTN connectivity options</span></span>

<span data-ttu-id="09745-141">Teams가 있는 전화 시스템은 사용자가 TeamsOnly 모드에 있는 후에 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="09745-141">Phone System with Teams is supported after the user is in TeamsOnly mode.</span></span> <span data-ttu-id="09745-142">사용자가 제도 모드인 경우 전화 시스템은 비즈니스용 Skype에서만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="09745-142">(If the user is in Islands mode, Phone System is only supported with Skype for Business.)</span></span> 

### <a name="pstn-connectivity-options"></a><span data-ttu-id="09745-143">PSTN 연결 옵션</span><span class="sxs-lookup"><span data-stu-id="09745-143">PSTN connectivity options</span></span>

<span data-ttu-id="09745-144">PSTN(Public Switched Telephone Network) 연결 옵션을 고려할 때 비즈니스용 Skype에서 프레미스 비즈니스용 Skype에서 TeamsOnly 모드로 전환하는 경우 다음과 같은 두 가지 시나리오가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09745-144">When considering Public Switched Telephone Network (PSTN) connectivity options, there are two possible scenarios when moving from Skype for Business on premises to TeamsOnly mode:</span></span>

- <span data-ttu-id="09745-145">온라인으로 이동하고 Microsoft 통화 요금제로 Enterprise Voice 비즈니스용 Skype의 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="09745-145">A user in Skype for Business on-premises with Enterprise Voice, who will be moving to online and using a Microsoft Calling plan.</span></span> <span data-ttu-id="09745-146">이 사용자를 Teams로 마이그레이션하려면 사용자의 비즈니스용 Skype 계정을 클라우드로 이동하고 A) 사용자의 전화 번호 포트를 Microsoft 통화 요금제로 이동하거나 B) 사용 가능한 지역에서 새 구독자 번호를 할당하도록 조정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09745-146">Migrating this user to Teams requires moving the user’s on-premises Skype for Business account to the cloud, and coordinating that move with either A) the port of that user’s phone number to a Microsoft Calling Plan or B) assigning a new subscriber number from available regions.</span></span>  <span data-ttu-id="09745-147">자세한 내용은 비즈니스용 Skype Server와 함께 Enterprise Voice Microsoft 통화 플랜을 [참조하세요.](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)</span><span class="sxs-lookup"><span data-stu-id="09745-147">For more information, see [From Skype for Business Server on-premises, with Enterprise Voice, to Microsoft Calling Plan](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan).</span></span>

- <span data-ttu-id="09745-148">온라인으로 이동하고 Enterprise Voice PSTN 연결을 유지할 수 있는 비즈니스용 Skype의 Enterprise Voice 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="09745-148">A user in Skype for Business on-premises with Enterprise Voice, who will be moving to online and keeping on-premises PSTN connectivity.</span></span> <span data-ttu-id="09745-149">이 사용자를 Teams로 마이그레이션하려면 사용자의 비즈니스용 Skype 계정을 클라우드로 이동하고 사용자의 마이그레이션과 직접 라우팅을 조정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09745-149">Migrating this user to Teams requires moving the user’s on-premises Skype for Business account to the cloud, and coordinating that move with migration of the user to Direct Routing.</span></span> <span data-ttu-id="09745-150">자세한 내용은 비즈니스용 Skype Server와 함께 Enterprise Voice [라우팅을 참조하세요.](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="09745-150">For more information, see [From Skype for Business Server on-premises, with Enterprise Voice, to Direct Routing](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing).</span></span>
