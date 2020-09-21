---
title: 비즈니스용 Skype 온-프레미스 배포에서 팀으로 업그레이드-Microsoft 팀
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/20
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 비즈니스용 Skype에서 팀으로 업그레이드 음성 고려 사항
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4a709f747d448b8a820cdd3d6fc3d1b732cc4a2a
ms.sourcegitcommit: b37632ffa22e3a6045b476c95d46889e9193a15b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47955891"
---
# <a name="pstn-considerations-when-upgrading-to-teams-mdash-for-it-administrators"></a><span data-ttu-id="4a1af-103">IT 관리자를 위해 팀으로 업그레이드할 때 PSTN 고려 사항 &mdash;</span><span class="sxs-lookup"><span data-stu-id="4a1af-103">PSTN considerations when upgrading to Teams &mdash; for IT administrators</span></span>

<span data-ttu-id="4a1af-104">이 문서에서는 팀으로 업그레이드할 때의 PSTN (공개 통신 네트워크) 고려 사항에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-104">This article describes Public Switched Telephone Network (PSTN) considerations when upgrading to Teams.</span></span> <span data-ttu-id="4a1af-105">이 문서는 IT 관리자의 업그레이드 개념 및 구현에 대해 설명 하는 몇 가지 항목 중 여섯 번째입니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-105">This article is the sixth of several that describe upgrade concepts and implementation for IT administrators.</span></span>  

- [<span data-ttu-id="4a1af-106">개요</span><span class="sxs-lookup"><span data-stu-id="4a1af-106">Overview</span></span>](upgrade-to-teams-on-prem-overview.md)
- [<span data-ttu-id="4a1af-107">업그레이드 방법</span><span class="sxs-lookup"><span data-stu-id="4a1af-107">Upgrade methods</span></span>](upgrade-to-teams-on-prem-upgrade-methods.md)
- [<span data-ttu-id="4a1af-108">업그레이드 관리 도구</span><span class="sxs-lookup"><span data-stu-id="4a1af-108">Tools for managing your upgrade</span></span>](upgrade-to-teams-on-prem-tools.md)
- [<span data-ttu-id="4a1af-109">비즈니스용 Skype 온-프레미스를 사용 하는 조직에 대 한 추가 고려 사항</span><span class="sxs-lookup"><span data-stu-id="4a1af-109">Additional considerations for organizations with Skype for Business on-premises</span></span>](upgrade-to-teams-on-prem-considerations.md)
- [<span data-ttu-id="4a1af-110">업그레이드 수행</span><span class="sxs-lookup"><span data-stu-id="4a1af-110">Implement your upgrade</span></span>](upgrade-to-teams-on-prem-implement.md)
- <span data-ttu-id="4a1af-111">**PSTN (공개 통신 네트워크) 고려 사항** (이 문서)</span><span class="sxs-lookup"><span data-stu-id="4a1af-111">**Public Switched Telephone Network (PSTN) considerations** (this article)</span></span>

<span data-ttu-id="4a1af-112">또한 다음 문서에서는 중요 한 업그레이드 개념 및 공존 동작에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-112">In addition, the following articles describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="4a1af-113">팀과 비즈니스용 Skype의 공존</span><span class="sxs-lookup"><span data-stu-id="4a1af-113">Coexistence of Teams and Skype for Business</span></span>](upgrade-to-teams-on-prem-coexistence.md)
- [<span data-ttu-id="4a1af-114">공존 모드-참조</span><span class="sxs-lookup"><span data-stu-id="4a1af-114">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="4a1af-115">Teams 클라이언트 환경 및 공존 모드 준수</span><span class="sxs-lookup"><span data-stu-id="4a1af-115">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)


 > [!NOTE]
 > <span data-ttu-id="4a1af-116">팀과 함께 전화 시스템을 사용 하는 것은 사용자가 TeamsOnly 모드에 있는 경우에만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-116">Using Phone System with Teams is only supported when the user is in TeamsOnly mode.</span></span>  <span data-ttu-id="4a1af-117">사용자가 군도 모드에 있는 경우, 전화 시스템은 비즈니스용 Skype 에서만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-117">If the user is in Islands mode, Phone System is only supported with Skype for Business.</span></span> 


## <a name="pstn-calling-scenarios"></a><span data-ttu-id="4a1af-118">PSTN 통화 시나리오</span><span class="sxs-lookup"><span data-stu-id="4a1af-118">PSTN calling scenarios</span></span>

<span data-ttu-id="4a1af-119">팀 전용 모드로 전환할 때는 다음과 같은 네 가지 호출 시나리오가 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-119">There are four possible calling scenarios when moving to TeamsOnly mode:</span></span>

- <span data-ttu-id="4a1af-120">[Microsoft 전화 요금제를 사용 하 여 비즈니스용 Skype Online의 사용자](#from-skype-for-business-online-with-microsoft-calling-plans)입니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-120">[A user in Skype for Business Online, with a Microsoft Calling Plan](#from-skype-for-business-online-with-microsoft-calling-plans).</span></span> <span data-ttu-id="4a1af-121">업그레이드 되 면이 사용자는 계속 Microsoft 통화 요금제를 보유 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-121">Upon upgrade, this user will continue to have a Microsoft Calling plan.</span></span>

- <span data-ttu-id="4a1af-122">비즈니스용 skype Online의 Skype for Business for 온 [-프레미스 음성 기능을 사용 하는 사용자](#from-skype-for-business-online-with-on-premises-voice)</span><span class="sxs-lookup"><span data-stu-id="4a1af-122">[A user in Skype for Business Online, with on-premises voice functionality](#from-skype-for-business-online-with-on-premises-voice) through Skype for Business on-premises or Cloud Connector Edition.</span></span> <span data-ttu-id="4a1af-123">팀으로의 사용자 업그레이드는 사용자가 자신에 게 PSTN 기능을가지고 있는지를 확인 하기 위해 자신을 마이그레이션하도록 조정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-123">The user’s upgrade to Teams needs to be coordinated with migration of the user to Direct Routing to ensure the TeamsOnly user has PSTN functionality.</span></span>

- <span data-ttu-id="4a1af-124">[비즈니스용 Skype 온-프레미스에서 엔터프라이즈 음성을 사용 하 여](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)온라인으로 전환 하 고 온-프레미스 PSTN 연결을 유지 하는 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-124">[A user in Skype for Business on-premises with Enterprise Voice](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing), who will be moving to online and keeping on-premises PSTN connectivity.</span></span>  <span data-ttu-id="4a1af-125">이 사용자를 팀으로 마이그레이션하면 사용자의 온-프레미스 비즈니스용 Skype 계정을 클라우드로 이동 하 고 사용자의 직접 라우팅에 맞게 이동 하도록 조정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-125">Migrating this user to Teams requires moving the user’s on-premises Skype for Business account to the cloud, and coordinating that move with migration of the user to Direct Routing.</span></span> 

- <span data-ttu-id="4a1af-126">Enterprise Voice를 사용 하는 [비즈니스용 Skype 온-프레미스 사용자](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)로 서, 온라인으로 이동 하 고 Microsoft의 통화 요금제를 사용 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-126">[A user in Skype for Business on-premises with Enterprise Voice](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan), who will be moving to online and using a Microsoft Calling plan.</span></span>  <span data-ttu-id="4a1af-127">이 사용자를 팀으로 마이그레이션하면 사용자의 온-프레미스 비즈니스용 Skype 계정을 클라우드로 이동 하 고 해당 사용자의 전화 번호를 Microsoft 통화 요금제 또는 B로 이동 하 여 사용 가능한 지역에서 새 구독자 번호를 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-127">Migrating this user to Teams requires moving the user’s on-premises Skype for Business account to the cloud, and coordinating that move with either A) the port of that user’s phone number to a Microsoft Calling Plan or B) assigning a new subscriber number from available regions.</span></span>

<span data-ttu-id="4a1af-128">이 문서에서는 상위 수준의 개요만 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-128">This article provides a high-level overview only.</span></span> <span data-ttu-id="4a1af-129">자세한 내용은 [전화 시스템 다이렉트 라우팅](direct-routing-landing-page.md) 및 [통화 계획](calling-plan-landing-page.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4a1af-129">For more information, see [Phone System Direct Routing](direct-routing-landing-page.md) and [Calling Plans](calling-plan-landing-page.md).</span></span> 

## <a name="from-skype-for-business-online-with-microsoft-calling-plans"></a><span data-ttu-id="4a1af-130">Microsoft 통화 요금제를 사용 하 여 비즈니스용 Skype Online에서</span><span class="sxs-lookup"><span data-stu-id="4a1af-130">From Skype for Business Online with Microsoft Calling Plans</span></span> 

<span data-ttu-id="4a1af-131">이는 음성 관련 가장 간단한 업그레이드 시나리오입니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-131">This is the simplest upgrade scenario involving voice.</span></span> 

1. <span data-ttu-id="4a1af-132">사용자에 게 팀 라이선스가 할당 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-132">Make sure users have been assigned a Teams license.</span></span> <span data-ttu-id="4a1af-133">기본적으로 Microsoft 365 또는 Office 365 라이선스를 할당 하는 경우 팀을 사용할 수 있으므로 이전에 팀 라이선스를 사용 하지 않도록 설정 하지 않은 경우에는 아무런 작업도 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-133">By default, when you assign a Microsoft 365 or Office 365 license, Teams is enabled, so unless you previously disabled the Teams license, no action should be necessary.</span></span>

2.  <span data-ttu-id="4a1af-134">사용자가 이미 전화 번호를 사용 하는 Microsoft 호출 계획이 있는 경우, TeamsUpgradePolicy에 사용자 팀 전용 모드를 할당 하는 것 으로만 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-134">If users already have a Microsoft Calling Plan with a phone number, the only required change is to assign the user TeamsOnly mode in TeamsUpgradePolicy.</span></span>  <span data-ttu-id="4a1af-135">팀 전용 모드를 할당 하기 전에 들어오는 PSTN 통화가 사용자의 비즈니스용 Skype 클라이언트에 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-135">Prior to assigning TeamsOnly mode, incoming PSTN calls will land in the user’s Skype for Business client.</span></span> <span data-ttu-id="4a1af-136">팀 전용 모드로 업그레이드 한 후에는 들어오는 PSTN 통화가 사용자의 팀 클라이언트에 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-136">After the upgrade to TeamsOnly mode, incoming PSTN calls will land in the user’s Teams client.</span></span>  

## <a name="from-skype-for-business-online-with-on-premises-voice"></a><span data-ttu-id="4a1af-137">온-프레미스 음성으로 비즈니스용 Skype Online에서</span><span class="sxs-lookup"><span data-stu-id="4a1af-137">From Skype for Business Online with on-premises voice</span></span>

<span data-ttu-id="4a1af-138">이 시나리오에서는 사용자가 이미 비즈니스용 Skype Online에 있지만, 하이브리드 모드 또는 클라우드 커넥터 에디션에 비즈니스용 Skype Server를 사용 하 여 PSTN 연결이 온-프레미스입니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-138">In this scenario, the user is already in Skype for Business Online, but their PSTN connectivity is on-premises, either using Skype for Business Server in hybrid mode or Cloud Connector Edition.</span></span> <span data-ttu-id="4a1af-139">PSTN 기능을 사용 하 여이 사용자를 팀 전용 모드로 마이그레이션하면 PSTN trunks가 클라우드의 직접 라우팅 서비스에 직접 연결 하 여 온-프레미스 세션 경계 컨트롤러 (SBC)를 통해 직접 라우팅에 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-139">Migrating these users to TeamsOnly mode with PSTN functionality means enabling them for Direct Routing, in which PSTN trunks connect directly to the Direct Routing service in the cloud, via your on-premises Session Border Controller (SBC).</span></span>

<span data-ttu-id="4a1af-140">기본 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-140">The basic steps are listed below.</span></span>  <span data-ttu-id="4a1af-141">1-4 단계는 제안 된 순서 대로 나열 되지만 순서에 관계 없이 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-141">Steps 1-4 are listed in the suggested sequence, but they can be done in any order.</span></span> <span data-ttu-id="4a1af-142">중요 한 것은 5 단계 이전에 모두 완료 되어야 한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-142">The key is that all of these should be completed before Step 5.</span></span>

1. <span data-ttu-id="4a1af-143">테 넌 트 전체 정책을 비즈니스용 Skype 모드 중 하나로 설정 하는 경우 앞에서 설명한 대로 해당 아일랜드 모드를 명시적으로 할당 하 여 기존 아일랜드 사용자에 게 grandfather 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-143">If you are setting the tenant-wide policy to one of the Skype for Business modes, be sure to grandfather any existing Islands users by explicitly assigning them Islands mode, as previously described.</span></span>

2. <span data-ttu-id="4a1af-144">직접 라우팅을 위해 테 넌 트를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-144">Configure your tenant for Direct Routing.</span></span> <span data-ttu-id="4a1af-145">[직접 라우팅의 테 넌 트 단위 구성 요약을](#summary-of-per-tenant-configuration-of-direct-routing)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4a1af-145">See [Summary of per-tenant configuration of Direct Routing](#summary-of-per-tenant-configuration-of-direct-routing).</span></span>

3. <span data-ttu-id="4a1af-146">필요한 경우 이러한 사용자에 대 한 다양 한 팀 정책을 구성 합니다 (예: TeamsMessagingPolicy, TeamsMeetingPolicy 등).</span><span class="sxs-lookup"><span data-stu-id="4a1af-146">If desired, configure various Teams policies for these users (for example, TeamsMessagingPolicy, TeamsMeetingPolicy, etc.).</span></span> <span data-ttu-id="4a1af-147">언제 든 지이 작업을 수행할 수 있지만, 사용자를 업그레이드할 때 올바른 구성을 유지 하려면 사용자가 TeamsOnly 모드로 업그레이드 하기 전에이 작업을 수행 하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-147">This can be done at any time, but if you want to ensure that users have the correct configuration when they are upgraded, it’s best to do this before the user is upgraded to TeamsOnly mode.</span></span>

4. <span data-ttu-id="4a1af-148">음성 마이그레이션을 위해 사용자 선택 준비:</span><span class="sxs-lookup"><span data-stu-id="4a1af-148">Prepare select users for voice migration:</span></span> 
   - <span data-ttu-id="4a1af-149">필요한 경우 팀 라이선스를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-149">If necessary, assign the Teams license.</span></span>  <span data-ttu-id="4a1af-150">비즈니스용 Skype Online 온-프레미스 음성에서 사용자가 이미 기능을 사용 하 고 있는 경우, 사용자는 이미 비즈니스용 Skype 요금제 2와 Microsoft 전화 시스템을 보유 하 고 있는 것으로 간주 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-150">Assuming the user is already functional in Skype for Business Online on-premises voice, the user already has Skype for Business Plan 2 as well as Microsoft Phone System.</span></span> <span data-ttu-id="4a1af-151">비즈니스용 Skype Online 요금제 2 라이선스를 포함 하 여 사용 하도록 설정 된 계획을 모두 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-151">Leave both those plans enabled, including the Skype for Business Online Plan 2 license.</span></span>  
   - <span data-ttu-id="4a1af-152">원하는 OnlineVoiceRoutingPolicy를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-152">Assign the desired OnlineVoiceRoutingPolicy.</span></span> 

5. <span data-ttu-id="4a1af-153">사용자 업그레이드: 이러한 단계는 조정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-153">Upgrade the user: These steps should be coordinated.</span></span> 

   - <span data-ttu-id="4a1af-154">Microsoft 365 또는 Office 365에서 사용자를 TeamsOnly 모드 (CsTeamsUpgradePolicy)로 업그레이드 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-154">In Microsoft 365 or Office 365, upgrade the user to TeamsOnly mode (Grant-CsTeamsUpgradePolicy).</span></span>
   - <span data-ttu-id="4a1af-155">SBC에서 온-프레미스 중재 서버 대신 다이렉트 라우팅에 대 한 통화를 보내 들어오는 전화를 사용할 수 있도록 음성 라우팅을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-155">On the SBC, configure voice routing to enable incoming calls by sending calls to Direct Routing instead of to the on-premises Mediation Server.</span></span>


## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing"></a><span data-ttu-id="4a1af-156">비즈니스용 Skype Server 온-프레미스에서 엔터프라이즈 음성을 사용 하 여 직접 라우팅</span><span class="sxs-lookup"><span data-stu-id="4a1af-156">From Skype for Business Server on-premises, with Enterprise Voice, to Direct Routing</span></span>

<span data-ttu-id="4a1af-157">이 시나리오에서는 사용자가 계속 비즈니스용 Skype 온-프레미스에 있고, PSTN 연결도 온-프레미스입니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-157">In this scenario, the user is still homed in Skype for Business on-premises, and their PSTN connectivity is also on-premises.</span></span> <span data-ttu-id="4a1af-158">PSTN 기능을 사용 하 여이 사용자를 팀 전용 모드로 마이그레이션하는 것은 직접 라우팅에 대해 사용 하도록 설정한 다음 사용자를 클라우드로 이동 하는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-158">Migrating these users to TeamsOnly mode with PSTN functionality means enabling them for Direct Routing and then moving the user to the cloud.</span></span> 
 
<span data-ttu-id="4a1af-159">기본 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-159">The basic steps are listed below.</span></span>  <span data-ttu-id="4a1af-160">1-5 단계는 제안 된 순서 대로 나열 되지만 순서에 관계 없이 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-160">Steps 1-5 are listed in the suggested sequence, but they can be done in any order.</span></span> <span data-ttu-id="4a1af-161">중요 한 것은 6 단계 이전에 모두 완료 되어야 한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-161">The key is that all of these should be completed before Step 6.</span></span>

1. <span data-ttu-id="4a1af-162">테 넌 트 전체 정책을 비즈니스용 Skype 모드 중 하나로 설정 하는 경우 앞에서 설명한 대로 해당 아일랜드 모드를 명시적으로 할당 하 여 기존 아일랜드 사용자를 grandfather 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-162">If you will be setting the tenant-wide policy to one of the Skype for Business modes, be sure to grandfather existing Islands users by explicitly assigning them Islands mode, as previously described.</span></span>

2. <span data-ttu-id="4a1af-163">아직 수행 하지 않은 경우 [비즈니스용 Skype 하이브리드에 맞게 조직을 구성](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)합니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-163">If you haven’t already done so, [configure the organization for Skype for Business hybrid](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity).</span></span>

3. <span data-ttu-id="4a1af-164">직접 라우팅을 위해 테 넌 트를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-164">Configure your tenant for Direct Routing.</span></span> <span data-ttu-id="4a1af-165">[직접 라우팅의 테 넌 트 단위 구성 요약을](#summary-of-per-tenant-configuration-of-direct-routing)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4a1af-165">See [Summary of per-tenant configuration of Direct Routing](#summary-of-per-tenant-configuration-of-direct-routing).</span></span>

4. <span data-ttu-id="4a1af-166">필요한 경우, 이러한 사용자에 대해 다양 한 팀 정책을 구성 합니다 (예: TeamsMessagingPolicy, TeamsMeetingPolicy 등).</span><span class="sxs-lookup"><span data-stu-id="4a1af-166">If desired, configure various Teams policies for these users (e.g. TeamsMessagingPolicy, TeamsMeetingPolicy, etc.).</span></span> <span data-ttu-id="4a1af-167">언제 든 지이 작업을 수행할 수 있지만, 업그레이드 시 사용자가 올바른 구성을 보유 하 고 있는지 확인 하려면 사용자가 TeamsOnly으로 업그레이드 하기 전에이 작업을 수행 하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-167">This can be done at any time, but if you want to ensure that users have the correct configuration when they are upgraded, it’s best to do this before the user is upgraded to TeamsOnly.</span></span>

5. <span data-ttu-id="4a1af-168">필요한 경우 Microsoft 365 또는 Office 365 라이선스를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-168">Assign the Microsoft 365 or Office 365 licenses if necessary.</span></span>  <span data-ttu-id="4a1af-169">사용자는 휴대폰 시스템과 함께 팀과 비즈니스용 Skype Online 요금제 2를 보유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-169">The user should have both Teams and Skype for Business Online Plan 2, as well as Phone System.</span></span> <span data-ttu-id="4a1af-170">비즈니스용 Skype Online 요금제 2를 사용할 수 없는 경우 다시 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-170">If the Skype for Business Online Plan 2 is disabled, re-enable it.</span></span>  

6. <span data-ttu-id="4a1af-171">사용자 업그레이드: 이러한 단계는 조정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-171">Upgrade the user: These steps should be coordinated.</span></span> 

   - <span data-ttu-id="4a1af-172">온-프레미스 비즈니스용 Skype 도구를 사용 하 여-MoveToTeams 스위치를 사용 하 여 CsUser Move 사용자를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-172">Using the on-premises Skype for Business tools, run Move-CsUser with -MoveToTeams switch.</span></span> <span data-ttu-id="4a1af-173">-MoveToTeams 스위치를 지원 하지 않는 비즈니스용 Skype Server 버전을 사용 하는 경우 먼저 이동-CsUser를 실행 한 다음 테 넌 트 원격 PowerShell 또는 팀 관리 콘솔에서 TeamsOnly 모드를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-173">If you are using a version of Skype for Business Server that does not support the -MoveToTeams switch, first run Move-CsUser and then assign TeamsOnly mode in tenant remote PowerShell or Teams Admin Console.</span></span>

   - <span data-ttu-id="4a1af-174">SBC에서 온-프레미스 중재 서버 대신 다이렉트 라우팅에 대 한 통화를 보내 들어오는 전화를 사용할 수 있도록 음성 라우팅을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-174">On the SBC, configure voice routing to enable incoming calls by sending calls to Direct Routing instead of to the on-premises Mediation Server.</span></span> 

   - <span data-ttu-id="4a1af-175">Microsoft 365 또는 Office 365: 나가는 통화를 사용할 수 있도록 관련 OnlineVoiceRoutingPolicy를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-175">In Microsoft 365 or Office 365: Assign the relevant OnlineVoiceRoutingPolicy to enable outgoing calls.</span></span> 


## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan"></a><span data-ttu-id="4a1af-176">비즈니스용 Skype Server 온-프레미스에서 Enterprise Voice를 사용 하 여 Microsoft 통화 요금제로</span><span class="sxs-lookup"><span data-stu-id="4a1af-176">From Skype for Business Server on-premises, with Enterprise Voice, to Microsoft Calling Plan</span></span>

<span data-ttu-id="4a1af-177">이 시나리오에서는 사용자가 계속 비즈니스용 Skype 온-프레미스에 있고, PSTN 연결도 온-프레미스입니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-177">In this scenario, the user is still homed in Skype for Business on-premises, and their PSTN connectivity is also on-premises.</span></span> <span data-ttu-id="4a1af-178">PSTN 기능을 사용 하 여 이러한 사용자를 팀 전용 모드로 마이그레이션하면 사용자를 클라우드로 이동 하 고 이전 캐리어에서 Microsoft 호출 계획으로 해당 번호를 이식 하거나 사용자에 게 새 번호를 할당 하는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-178">Migrating these users to TeamsOnly mode with PSTN functionality means moving the user to the cloud and either porting their number from the old carrier to a Microsoft Calling plan or assigning the user a new number.</span></span> 

<span data-ttu-id="4a1af-179">기본 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-179">The basic steps are listed below.</span></span><span data-ttu-id="4a1af-180">1-5 단계는 제안 된 순서 대로 나열 되지만 순서에 관계 없이 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-180">  Steps 1-5 are listed in the suggested sequence, but they can be done in any order.</span></span> <span data-ttu-id="4a1af-181">중요 한 것은 6 단계 이전에 모두 완료 되어야 한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-181">The key is that all of these should be completed before Step 6.</span></span> 

1. <span data-ttu-id="4a1af-182">테 넌 트 전체 정책을 비즈니스용 Skype 모드 중 하나로 설정 하는 경우 앞에서 설명한 대로 해당 아일랜드 모드를 명시적으로 할당 하 여 기존 아일랜드 사용자를 grandfather 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-182">If you will be setting the tenant-wide policy to one of the Skype for Business modes, be sure to grandfather existing Islands users by explicitly assigning them Islands mode, as previously described.</span></span> 

2. <span data-ttu-id="4a1af-183">아직 수행 하지 않은 경우 [비즈니스용 Skype 하이브리드에 맞게 조직을 구성](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)합니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-183">If you haven’t already done so, [configure the organization for Skype for Business hybrid](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity).</span></span> 

3. <span data-ttu-id="4a1af-184">필요한 경우 이러한 사용자에 대 한 다양 한 팀 정책을 구성 합니다 (예: TeamsMessagingPolicy, TeamsMeetingPolicy 등).</span><span class="sxs-lookup"><span data-stu-id="4a1af-184">If desired, configure various Teams policies for these users (for example, TeamsMessagingPolicy, TeamsMeetingPolicy, etc.).</span></span> <span data-ttu-id="4a1af-185">언제 든 지이 작업을 수행할 수 있지만, 업그레이드 시 사용자가 올바른 구성을 보유 하 고 있는지 확인 하려면 사용자가 TeamsOnly으로 업그레이드 하기 전에이 작업을 수행 하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-185">This can be done at any time, but if you want to ensure that users have the correct configuration when they are upgraded, it’s best to do this before the user is upgraded to TeamsOnly.</span></span> 

4. <span data-ttu-id="4a1af-186">필요한 경우 Microsoft 365 또는 Office 365 라이선스를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-186">Assign the Microsoft 365 or Office 365 licenses if necessary.</span></span><span data-ttu-id="4a1af-187">사용자는 휴대폰 시스템과 함께 팀과 비즈니스용 Skype Online 요금제 2를 보유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-187">  The user should have both Teams and Skype for Business Online Plan 2, as well as Phone System.</span></span> <span data-ttu-id="4a1af-188">비즈니스용 Skype Online 요금제 2를 사용할 수 없는 경우 다시 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-188">If the Skype for Business Online Plan 2 is disabled, re-enable it.</span></span>  

5. <span data-ttu-id="4a1af-189">사용자의 전화 번호를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-189">Get phone numbers for your users.</span></span> <span data-ttu-id="4a1af-190">(자세한 내용은 [조직의 전화 번호 관리](https://docs.microsoft.com/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)를 참조 하세요.)</span><span class="sxs-lookup"><span data-stu-id="4a1af-190">(For details see [Manage phone numbers for your organization](https://docs.microsoft.com/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization).)</span></span>

   - <span data-ttu-id="4a1af-191">번호를 다시 사용 하는 경우에는 해당 통신 업체에 포팅 요청을 제출 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-191">If you will be re-using the numbers, submit a porting request to your carrier.</span></span>  
   - <span data-ttu-id="4a1af-192">또는 Microsoft에서 직접 새 번호를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-192">Alternatively, you can acquire new numbers directly from Microsoft.</span></span> 

6. <span data-ttu-id="4a1af-193">사용자를 업그레이드 하 고 필요한 경우 LineUri를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-193">Upgrade the user and if needed assign LineUri.</span></span> <span data-ttu-id="4a1af-194">온-프레미스 비즈니스용 Skype 도구를 사용 하 여-MoveToTeams 스위치와 함께 CsUser Move를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-194">Using the on-premises Skype for Business tools, run Move-CsUser with the -MoveToTeams switch.</span></span>  

    - <span data-ttu-id="4a1af-195">Microsoft로 번호를 포팅 하는 경우 포트가 발생할 때이 작업이 발생 하는 시기를 조정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-195">If you are porting numbers to Microsoft, you should coordinate the timing of this operation to occur when the port occurs.</span></span> 

    - <span data-ttu-id="4a1af-196">Microsoft에서 새 번호를 사용 하는 경우 사용자의 LineUri를 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-196">If you are using new numbers from Microsoft, you’ll need to change the LineUri for the user.</span></span> <span data-ttu-id="4a1af-197">사용자가 CsOnlineVoiceUser를 사용 하 여 온라인으로 이동한 후에이 작업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-197">This must be done after the user is moved online using Set-CsOnlineVoiceUser.</span></span>  

## <a name="summary-of-per-tenant-configuration-of-direct-routing"></a><span data-ttu-id="4a1af-198">직접 라우팅의 테 넌 트 단위 구성 요약</span><span class="sxs-lookup"><span data-stu-id="4a1af-198">Summary of per-tenant configuration of Direct Routing</span></span> 

1. <span data-ttu-id="4a1af-199">[이 목록을](direct-routing-border-controllers.md)검토 하 여 SBC (세션 경계 컨트롤러)가 직접 라우팅이 지원 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-199">Ensure that your Session Border Controller (SBC) is supported with Direct Routing by reviewing [this list](direct-routing-border-controllers.md).</span></span> <span data-ttu-id="4a1af-200">또한 올바른 펌웨어 버전이 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-200">You must also ensure that you have correct version of firmware.</span></span>  

2. <span data-ttu-id="4a1af-201">온-프레미스 SBC를 팀 다이렉트 라우팅 서비스와 쌍으로 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-201">Pair your on-premises SBC with the Teams Direct Routing service.</span></span> <span data-ttu-id="4a1af-202">자세한 내용은 [전화 시스템의 다이렉트 라우팅 서비스에 SBC 페어링](direct-routing-configure.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4a1af-202">For details, see [Pair the SBC to the Direct Routing service of Phone System](direct-routing-configure.md).</span></span> 

3. <span data-ttu-id="4a1af-203">이 구성은 본질적으로 온-프레미스 구성의 미러입니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-203">This configuration is essentially a mirror of the on-premises configuration.</span></span> <span data-ttu-id="4a1af-204">온라인 구성은 다음으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-204">The online configuration consists of:</span></span> 
   - <span data-ttu-id="4a1af-205">OnlineVoiceRoutingPolicy (비즈니스용 Skype Online에서 사용자를 마이그레이션하는 경우 온-프레미스 VoiceRoutingPolicy를 기반으로 하며, 사용자를 Enterprise Voice를 통해 온-프레미스에서 마이그레이션하는 경우 VoicePolicy에 기반을 둔 경우).</span><span class="sxs-lookup"><span data-stu-id="4a1af-205">OnlineVoiceRoutingPolicy (based on the on-premises VoiceRoutingPolicy if migrating users from Skype for Business   Online, and based on VoicePolicy if migrating users from on-premises with Enterprise Voice).</span></span>
   - <span data-ttu-id="4a1af-206">OnlinePSTNUsage 개체 (온-프레미스 PSTN 사용 기준).</span><span class="sxs-lookup"><span data-stu-id="4a1af-206">OnlinePSTNUsage objects (based on on-premises PSTN usage).</span></span> 
   - <span data-ttu-id="4a1af-207">OnlineVoiceRoute 개체 (기반 온-프레미스 VoiceRoute).</span><span class="sxs-lookup"><span data-stu-id="4a1af-207">OnlineVoiceRoute objects (based on-premises VoiceRoute).</span></span> 

<span data-ttu-id="4a1af-208">자세한 내용은 [직접 라우팅 구성을](direct-routing-configure.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4a1af-208">For more information, see [Configure Direct Routing](direct-routing-configure.md).</span></span> 

## <a name="manage-enterprisevoiceenabled-property-during-migration"></a><span data-ttu-id="4a1af-209">마이그레이션 중 EnterpriseVoiceEnabled 속성 관리</span><span class="sxs-lookup"><span data-stu-id="4a1af-209">Manage EnterpriseVoiceEnabled property during migration</span></span> 

<span data-ttu-id="4a1af-210">직접 라우팅 또는 Microsoft 호출 계획을 사용 하는 경우 사용자는 사용자가 PSTN 기능을 사용할 수 있도록 Azure AD에서 EnterpriseVoiceEnabled = true를 가져야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-210">Whether using Direct Routing or a Microsoft Calling plan, a user must have EnterpriseVoiceEnabled=true in Azure AD for the user to have PSTN functionality.</span></span>  <span data-ttu-id="4a1af-211">EnterpriseVoiceEnabled ("EV 사용")는 온-프레미스 디렉터리와 클라우드에 모두 존재 하는 속성 (정책 아님)입니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-211">EnterpriseVoiceEnabled (“EV-enabled”) is a property (not a policy) that exists in both an on-premises directory and in the cloud.</span></span> <span data-ttu-id="4a1af-212">클라우드의 가치는 팀에 중요 한 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-212">The value in the cloud is what matters for Teams.</span></span>  <span data-ttu-id="4a1af-213">EV 사용이 true로 설정 되는 방법에 대 한 정확한 논리는 다음 시나리오에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-213">The exact logic for how EV-enabled gets set to true depends on the following scenario:</span></span> 

- <span data-ttu-id="4a1af-214">사용자가 온-프레미스 비즈니스용 Skype 서버에서 EV를 사용 하도록 설정 되어 있고 사용자를 이동-CsUser와 함께 클라우드로 이동 하기 전에 사용자에 게 할당 된 전화 시스템 라이선스가 있는 경우, 온라인 사용자는 EV 사용 = true를 사용 하 여 프로 비전 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-214">If the user is EV-enabled in on-premises Skype for Business Server and a Phone System license is assigned to the user prior to moving the user to the cloud with Move-CsUser, the online user will be provisioned with EV-enabled=true.</span></span> 

- <span data-ttu-id="4a1af-215">기존 팀 또는 비즈니스용 Skype Online 사용자에 게 전화 시스템 라이선스가 할당 되 면 기본적으로 EV 사용이 true로 설정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-215">If an existing TeamsOnly or Skype for Business Online user is assigned a Phone System license, EV-enabled is not set to true by default.</span></span>  <span data-ttu-id="4a1af-216">이는 전화 시스템 라이선스를 할당 하기 전에 온-프레미스 사용자가 클라우드로 이동 하는 경우에도 해당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-216">This also is the case if an on-premises user is moved to the cloud prior to assigning the Phone System license.</span></span> <span data-ttu-id="4a1af-217">두 경우 모두 관리자는 다음 cmdlet을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a1af-217">In either case, the admin must specify the following cmdlet:</span></span> 

  ```PowerShell
  Set-CsUser -EnterpriseVoiceEnabled $True 
  ```

## <a name="related-links"></a><span data-ttu-id="4a1af-218">관련 링크</span><span class="sxs-lookup"><span data-stu-id="4a1af-218">Related links</span></span>

[<span data-ttu-id="4a1af-219">비즈니스용 Skype로 팀을 함께 사용 하는 조직에 대 한 마이그레이션 및 상호 운용성 지침</span><span class="sxs-lookup"><span data-stu-id="4a1af-219">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="4a1af-220">비즈니스용 Skype 서버와 Microsoft 365 또는 Office 365 간 하이브리드 연결 구성</span><span class="sxs-lookup"><span data-stu-id="4a1af-220">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="4a1af-221">온-프레미스와 클라우드 간에 사용자 이동</span><span class="sxs-lookup"><span data-stu-id="4a1af-221">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="4a1af-222">공존 및 업그레이드 설정 설정</span><span class="sxs-lookup"><span data-stu-id="4a1af-222">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="4a1af-223">부여-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="4a1af-223">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="4a1af-224">MMS (모임 마이그레이션 서비스) 사용</span><span class="sxs-lookup"><span data-stu-id="4a1af-224">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

