---
title: 비즈니스용 Skype 온-프레미스를 Teams로 업그레이드
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/09/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 비즈니스용 Skype 온-프레미스 배포에서 조직을 Microsoft 팀으로 업그레이드 하는 방법에 대해 알아봅니다.
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
ms.openlocfilehash: 17420c93c883054d36c4ae2e1b323be9e589a2c2
ms.sourcegitcommit: f7f86744c6dbf0db87e1408fd1f4b770fda07ff9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/17/2020
ms.locfileid: "45158676"
---
# <a name="upgrade-from-skype-for-business-on-premises-to-teams"></a><span data-ttu-id="88225-103">비즈니스용 Skype 온-프레미스에서 팀으로 업그레이드</span><span class="sxs-lookup"><span data-stu-id="88225-103">Upgrade from Skype for Business on-premises to Teams</span></span>

<span data-ttu-id="88225-104">![여행 다이어그램 업그레이드, 배포 및 구현 강조](media/upgrade-banner-deployment.png "배포 및 구현 단계에 주안점을 두어 업그레이드 여행 단계")</span><span class="sxs-lookup"><span data-stu-id="88225-104">![Upgrade journey diagram, emphasizing Deployment and Implementation](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="88225-105">이 문서는 업그레이드 여행 배포 및 구현 단계의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="88225-105">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="88225-106">계속 하기 전에 다음 활동을 완료 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="88225-106">Before proceeding, confirm that you've completed the following activities:</span></span>

-   [<span data-ttu-id="88225-107">프로젝트 이해 관계자 참여</span><span class="sxs-lookup"><span data-stu-id="88225-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
-   [<span data-ttu-id="88225-108">프로젝트 범위 정의</span><span class="sxs-lookup"><span data-stu-id="88225-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
-   [<span data-ttu-id="88225-109">비즈니스용 Skype 및 팀의 공존 성과 상호 운영성 이해</span><span class="sxs-lookup"><span data-stu-id="88225-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
-   [<span data-ttu-id="88225-110">업그레이드 여행 선택</span><span class="sxs-lookup"><span data-stu-id="88225-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [<span data-ttu-id="88225-111">환경 준비</span><span class="sxs-lookup"><span data-stu-id="88225-111">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
-   [<span data-ttu-id="88225-112">조직 준비</span><span class="sxs-lookup"><span data-stu-id="88225-112">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
-   [<span data-ttu-id="88225-113">파일럿 수행</span><span class="sxs-lookup"><span data-stu-id="88225-113">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

<span data-ttu-id="88225-114">비즈니스용 Skype 서버 또는 Microsoft Lync 온-프레미스를 배포 하 고 조직에서 팀으로 업그레이드 하려는 경우이 문서의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="88225-114">If you've deployed Skype for Business Server or Microsoft Lync on-premises and your organization wants to upgrade to Teams, follow the guidance in this article.</span></span> <span data-ttu-id="88225-115">Microsoft 365 또는 Office 365 조직과 하이브리드 연결을 설정 하 고 사용자를 단계별로 팀으로 이동 하는 경우 공존 요구 사항을 결정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="88225-115">You need to set up hybrid connectivity with your Microsoft 365 or Office 365 organization, and determine coexistence requirements if you are moving your users to Teams in phases.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="88225-116">비즈니스용 Skype Online은 2021년 7월 31일에 서비스가 종료되며 이후에는 더 이상 액세스할 수 없게 되거나 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="88225-116">Skype for Business Online will be retired on July 31, 2021, after which it will no longer be accessible or supported.</span></span> <span data-ttu-id="88225-117">조직의 혜택 실현을 최대화 하 고 업그레이드를 구현 하는 데 적절 한 시간을 확보 하려면 지금 Microsoft 팀으로 여행을 시작 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="88225-117">To maximize benefit realization and ensure your organization has proper time to implement your upgrade, we encourage you to begin your journey to Microsoft Teams today.</span></span> <span data-ttu-id="88225-118">성공적으로 업그레이드 하면 기술 및 사용자의 준비가 정렬 되므로 Microsoft 팀으로 여행을 이동할 때이 가이드의 지침을 활용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="88225-118">Remember that a successful upgrade aligns technical and user readiness, so be sure to leverage the guidance herein as you navigate your journey to Microsoft Teams.</span></span>

## <a name="step-1-configure-hybrid-connectivity"></a><span data-ttu-id="88225-119">1 단계: 하이브리드 연결 구성</span><span class="sxs-lookup"><span data-stu-id="88225-119">Step 1: Configure hybrid connectivity</span></span> 

<span data-ttu-id="88225-120">온-프레미스 사용자를 팀으로 업그레이드 하기 위한 주요 전제 조건은 비즈니스용 Skype Server 온-프레미스 배포에 하이브리드 연결을 구성 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="88225-120">The key prerequisite for upgrading your on-premises users to Teams is to configure hybrid connectivity for your Skype for Business Server on-premises deployment.</span></span> 

<span data-ttu-id="88225-121">먼저 [하이브리드 연결 계획](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) 을 읽고 [하이브리드 연결 구성](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)에 설명 된 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="88225-121">Start by reading [Plan hybrid connectivity](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) and then follow the tasks outlined in [Configure hybrid connectivity](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity).</span></span>


## <a name="step-2-set-transitional-coexistence-mode-optional"></a><span data-ttu-id="88225-122">2 단계: 전환 공존 모드 설정 (선택 사항)</span><span class="sxs-lookup"><span data-stu-id="88225-122">Step 2: Set transitional coexistence mode (optional)</span></span>

<span data-ttu-id="88225-123">비즈니스용 Skype 및 팀 간 공존 및 상호 운용성 클라이언트와 사용자는 팀 업그레이드 모드에서 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="88225-123">Coexistence and interoperability between Skype for Business and Teams clients and users are defined by Teams Upgrade modes.</span></span>  <span data-ttu-id="88225-124">기본적으로 조직은 사용자가 팀과 비즈니스용 Skype 클라이언트를 나란히 사용할 수 있도록 하는 군도 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="88225-124">By default, organizations are in Islands mode, which allows users to use both Teams and Skype for Business clients side by side.</span></span>

<span data-ttu-id="88225-125">팀으로 이동 하는 조직의 경우 각 사용자에 대 한 최종 대상, 즉 모든 사용자가 동시에 Teamonly (또는 다른 모드)를 할당 해야 하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="88225-125">For an organization moving to Teams, TeamsOnly mode is the final destination for each user--though not all users need to be assigned TeamsOnly (or any other mode) at the same time.</span></span>

<span data-ttu-id="88225-126">사용자가 팀의 유일한 모드에 도달 하기 전에, 조직에서 비즈니스용 Skype 공존 모드를 사용 하 여 필요한 경우 팀 전용 모드의 사용자와 아직 없는 사용자 간에 예측 가능한 의사 소통을 보장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88225-126">Prior to users reaching TeamsOnly mode, organizations can optionally use any of the Skype for Business coexistence modes to ensure predictable communication between users who are in TeamsOnly mode and users who aren't yet.</span></span>  <span data-ttu-id="88225-127">비즈니스용 skype 공존 모드 (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings)는 조직의 비즈니스용 Skype에서 팀으로 전환 하는 등 최종 사용자에 게 예측 가능한 간단한 환경을 제공 하는 데 목적이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88225-127">The purpose of the Skype for Business coexistence modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) is to provide a simple, predictable experience for end users as organizations transition from Skype for Business to Teams.</span></span> 

<span data-ttu-id="88225-128">사용자가 비즈니스용 Skype 모드에 있는 경우 모든 수신 채팅 및 통화는 사용자의 비즈니스용 Skype 클라이언트로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="88225-128">When a user is in any of the Skype for Business modes, all incoming chats and calls are routed to the user's Skype for Business client.</span></span> <span data-ttu-id="88225-129">사용자가 비즈니스용 Skype 모드에 있는 경우 최종 사용자의 혼란을 방지 하 고 적절 한 라우팅이 가능 하도록 팀 클라이언트의 통화 및 채팅 기능을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="88225-129">To avoid end-user confusion and ensure proper routing, calling and chat functionality in the Teams client is disabled when a user is in any of the Skype for Business modes.</span></span> <span data-ttu-id="88225-130">마찬가지로 사용자가 SfBOnly 또는 SfBWithTeamsCollab 모드에 있고 사용자가 SfBWithTeamsCollabAndMeetings 모드일 때 명시적으로 사용 하도록 설정 되어 있는 경우 팀에서 모임 예약을 명시적으로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="88225-130">Similarly, meeting scheduling in Teams is explicitly disabled when users are in the SfBOnly or SfBWithTeamsCollab modes, and explicitly enabled when a user is in the SfBWithTeamsCollabAndMeetings mode.</span></span>

<span data-ttu-id="88225-131">요구 사항에 따라 조직에서 선택한 업그레이드 경로에 따라 적절 한 공존 모드를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88225-131">Depending on your requirements, you can assign the appropriate coexistence mode based on the upgrade path that your organization has chosen.</span></span> <span data-ttu-id="88225-132">자세한 내용은 비즈니스용 [Skype로 팀을 사용 하는 조직에 대 한 마이그레이션 및 상호 운용성 지침](migration-interop-guidance-for-teams-with-skype.md) 을 참조 하 고 [공존 및 업그레이드 설정을 설정](https://aka.ms/SkypeToTeams-SetCoexistence)합니다.</span><span class="sxs-lookup"><span data-stu-id="88225-132">For more information, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](migration-interop-guidance-for-teams-with-skype.md) and [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence).</span></span>


## <a name="step-3-move-users-from-skype-for-business-on-premises-to-teams-only"></a><span data-ttu-id="88225-133">3 단계: 비즈니스용 Skype 온-프레미스에서 팀 으로만 사용자 이동</span><span class="sxs-lookup"><span data-stu-id="88225-133">Step 3: Move users from Skype for Business on-premises to Teams Only</span></span>

<span data-ttu-id="88225-134">궁극적으로 사용자를 팀 전용 모드로 이동 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="88225-134">Ultimately, you'll want to move your users to TeamsOnly mode.</span></span> <span data-ttu-id="88225-135">이 작업에는 온-프레미스 환경에 따라 하나 또는 두 단계가 포함 될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="88225-135">This might involve one or two steps depending on your on-premises environment.</span></span>  

<span data-ttu-id="88225-136">자세한 내용은 온 [-프레미스와 클라우드 간에 사용자 이동을](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud) 참조 하 고 온 [-프레미스에서 팀으로 사용자를 이동](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams)합니다.</span><span class="sxs-lookup"><span data-stu-id="88225-136">For more information, see [Move users between on-premises and the cloud](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud) and [Move users from on-premises to Teams](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams).</span></span> 

## <a name="step-4-disable-hybrid-to-complete-your-migration-to-the-cloud"></a><span data-ttu-id="88225-137">4 단계: 하이브리드를 사용 하지 않도록 설정 하 여 클라우드로 마이그레이션 완료</span><span class="sxs-lookup"><span data-stu-id="88225-137">Step 4: Disable hybrid to complete your migration to the cloud</span></span>

<span data-ttu-id="88225-138">모든 사용자를 온-프레미스에서 클라우드로 이동한 후에는 온-프레미스 Skype 비즈니스 배포를 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88225-138">After you have moved all users from on-premises to the cloud, you can decommission the on-premises Skype for Business deployment.</span></span> <span data-ttu-id="88225-139">자세한 내용은 [클라우드로 마이그레이션을 완료 하기 위해 하이브리드 사용 안 함을](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="88225-139">For more information, see [Disable hybrid to complete migration to the cloud](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md).</span></span>


## <a name="phone-system-and-pstn-connectivity-options"></a><span data-ttu-id="88225-140">전화 시스템 및 PSTN 연결 옵션</span><span class="sxs-lookup"><span data-stu-id="88225-140">Phone System and PSTN connectivity options</span></span>

<span data-ttu-id="88225-141">사용자가 TeamsOnly 모드에 있는 경우 팀이 포함 된 전화 시스템이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="88225-141">Phone System with Teams is supported after the user is in TeamsOnly mode.</span></span> <span data-ttu-id="88225-142">(사용자가 군도 모드에 있는 경우, 전화 시스템은 비즈니스용 Skype 에서만 지원 됩니다.)</span><span class="sxs-lookup"><span data-stu-id="88225-142">(If the user is in Islands mode, Phone System is only supported with Skype for Business.)</span></span> 

### <a name="pstn-connectivity-options"></a><span data-ttu-id="88225-143">PSTN 연결 옵션</span><span class="sxs-lookup"><span data-stu-id="88225-143">PSTN connectivity options</span></span>

<span data-ttu-id="88225-144">PSTN (공용 전환 전화 네트워크) 연결 옵션을 고려할 때 비즈니스용 Skype에서 팀 전용 모드로 전환할 때 다음과 같은 두 가지 시나리오가 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="88225-144">When considering Public Switched Telephone Network (PSTN) connectivity options, there are two possible scenarios when moving from Skype for Business on premises to TeamsOnly mode:</span></span>

- <span data-ttu-id="88225-145">Enterprise Voice를 사용 하는 비즈니스용 Skype 온-프레미스 사용자로 서, 온라인으로 이동 하 고 Microsoft의 통화 요금제를 사용 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="88225-145">A user in Skype for Business on-premises with Enterprise Voice, who will be moving to online and using a Microsoft Calling plan.</span></span> <span data-ttu-id="88225-146">이 사용자를 팀으로 마이그레이션하면 사용자의 온-프레미스 비즈니스용 Skype 계정을 클라우드로 이동 하 고 해당 사용자의 전화 번호를 Microsoft 통화 요금제 또는 B로 이동 하 여 사용 가능한 지역에서 새 구독자 번호를 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="88225-146">Migrating this user to Teams requires moving the user’s on-premises Skype for Business account to the cloud, and coordinating that move with either A) the port of that user’s phone number to a Microsoft Calling Plan or B) assigning a new subscriber number from available regions.</span></span>  <span data-ttu-id="88225-147">자세한 내용은 [비즈니스용 Skype Server 온-프레미스에서 엔터프라이즈 음성을 사용 하 여 Microsoft 전화 요금제를](upgrade-to-teams-on-prem-overview.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="88225-147">For more information, see [From Skype for Business Server on-premises, with Enterprise Voice, to Microsoft Calling Plan](upgrade-to-teams-on-prem-overview.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan).</span></span>

- <span data-ttu-id="88225-148">비즈니스용 Skype 온-프레미스에서 엔터프라이즈 음성을 사용 하 여 온라인으로 전환 하 고 온-프레미스 PSTN 연결을 유지 하는 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="88225-148">A user in Skype for Business on-premises with Enterprise Voice, who will be moving to online and keeping on-premises PSTN connectivity.</span></span> <span data-ttu-id="88225-149">이 사용자를 팀으로 마이그레이션하면 사용자의 온-프레미스 비즈니스용 Skype 계정을 클라우드로 이동 하 고 사용자의 직접 라우팅에 맞게 이동 하도록 조정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="88225-149">Migrating this user to Teams requires moving the user’s on-premises Skype for Business account to the cloud, and coordinating that move with migration of the user to Direct Routing.</span></span> <span data-ttu-id="88225-150">자세한 내용은 [비즈니스용 Skype Server 온-프레미스에서 엔터프라이즈 음성을 사용 하 여 직접 라우팅](upgrade-to-teams-on-prem-overview.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="88225-150">For more information, see [From Skype for Business Server on-premises, with Enterprise Voice, to Direct Routing](upgrade-to-teams-on-prem-overview.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing).</span></span>

