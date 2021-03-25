---
title: 비즈니스용 Skype에서 Teams로 업그레이드할 때 PSTN 고려 사항
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 비즈니스용 Skype에서 Teams로 업그레이드하기 위한 음성 고려 사항
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 72a12cf1dbcb69af7b71bf259568e4a53d1a3a33
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51115546"
---
# <a name="pstn-considerations-for-upgrading-to-teams-from-skype-for-business-on-premises"></a><span data-ttu-id="865d2-103">비즈니스용 Skype에서 Teams로 업그레이드하기 위한 PSTN 고려 사항</span><span class="sxs-lookup"><span data-stu-id="865d2-103">PSTN considerations for upgrading to Teams from Skype for Business on-premises</span></span>

<span data-ttu-id="865d2-104">이 문서에서는 Teams로 업그레이드할 때 PSTN(공용 전환 전화 네트워크) 고려 사항을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-104">This article describes Public Switched Telephone Network (PSTN) considerations when upgrading to Teams.</span></span>   


<span data-ttu-id="865d2-105">또한 다음 문서에서는 중요한 업그레이드 개념 및 공존 동작을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-105">In addition, the following articles describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="865d2-106">Teams 및 비즈니스용 Skype의 공존</span><span class="sxs-lookup"><span data-stu-id="865d2-106">Coexistence of Teams and Skype for Business</span></span>](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="865d2-107">공존 모드 - 참조</span><span class="sxs-lookup"><span data-stu-id="865d2-107">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="865d2-108">Teams 클라이언트 환경 및 공존 모드 준수</span><span class="sxs-lookup"><span data-stu-id="865d2-108">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)


 > [!NOTE]
 > - <span data-ttu-id="865d2-109">Teams와 전화 시스템 사용은 사용자가 TeamsOnly 모드일 때만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-109">Using Phone System with Teams is only supported when the user is in TeamsOnly mode.</span></span>  <span data-ttu-id="865d2-110">사용자가 제도 모드인 경우 전화 시스템은 비즈니스용 Skype에서만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-110">If the user is in Islands mode, Phone System is only supported with Skype for Business.</span></span> 
 > - <span data-ttu-id="865d2-111">비즈니스용 Skype의 모든 통화 전달, 팀 호출 그룹 및 위임 설정은 마이그레이션되지 않습니다. Teams에 대해 다시 다시 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-111">Any call forwarding, team-call group, and delegation settings from Skype for Business are not migrated and will need to be re-recreated for Teams.</span></span>
 > - <span data-ttu-id="865d2-112">Microsoft Teams 클라우드 음성 기능에 대한 일반 개요 및 조직에 적합한 Microsoft 음성 솔루션 결정에 대한 자세한 내용은 Teams 음성 솔루션 계획 [을 참조하세요.](cloud-voice-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="865d2-112">For a general overview of Microsoft Teams cloud voice features, and help deciding which Microsoft voice solution is right for your organization, see [Plan your Teams voice solution](cloud-voice-landing-page.md).</span></span>


## <a name="pstn-calling-scenarios"></a><span data-ttu-id="865d2-113">PSTN 호출 시나리오</span><span class="sxs-lookup"><span data-stu-id="865d2-113">PSTN calling scenarios</span></span>

<span data-ttu-id="865d2-114">TeamsOnly 모드로 이동하는 경우 네 가지 가능한 호출 시나리오가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-114">There are four possible calling scenarios when moving to TeamsOnly mode:</span></span>

- <span data-ttu-id="865d2-115">Microsoft 통화 계획이 있는 [비즈니스용 Skype Online의 사용자입니다.](#from-skype-for-business-online-with-microsoft-calling-plans)</span><span class="sxs-lookup"><span data-stu-id="865d2-115">[A user in Skype for Business Online, with a Microsoft Calling Plan](#from-skype-for-business-online-with-microsoft-calling-plans).</span></span> <span data-ttu-id="865d2-116">업그레이드 시 이 사용자는 Microsoft 통화 계획을 계속 하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-116">Upon upgrade, this user will continue to have a Microsoft Calling plan.</span></span>

- <span data-ttu-id="865d2-117">[비즈니스용 Skype Online의](#from-skype-for-business-online-with-on-premises-voice) 사용자는 비즈니스용 Skype-프레미스 또는 클라우드 커넥터 에디션을 통해 프레미스 음성 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-117">[A user in Skype for Business Online, with on-premises voice functionality](#from-skype-for-business-online-with-on-premises-voice) through Skype for Business on-premises or Cloud Connector Edition.</span></span> <span data-ttu-id="865d2-118">Teams로의 사용자의 업그레이드는 TeamsOnly 사용자에게 PSTN 기능을 보장하기 위해 사용자를 직접 라우팅으로 마이그레이션하는 방법을 조정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-118">The user’s upgrade to Teams needs to be coordinated with migration of the user to Direct Routing to ensure the TeamsOnly user has PSTN functionality.</span></span>

- <span data-ttu-id="865d2-119">[비즈니스용 Skype온-프레미스에서](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)Enterprise Voice 온라인으로 이동하고온-프레미스 PSTN 연결을 유지할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-119">[A user in Skype for Business on-premises with Enterprise Voice](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing), who will be moving to online and keeping on-premises PSTN connectivity.</span></span>  <span data-ttu-id="865d2-120">이 사용자를 Teams로 마이그레이션하려면 사용자의 비즈니스용 Skype 계정을 클라우드로 이동하고, 사용자의 마이그레이션을 통해 직접 라우팅으로 이동하는 조정이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-120">Migrating this user to Teams requires moving the user’s on-premises Skype for Business account to the cloud, and coordinating that move with migration of the user to Direct Routing.</span></span> 

- <span data-ttu-id="865d2-121">[비즈니스용 Skype온-프레미스에서](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)Enterprise Voice 온라인으로 이동하고 Microsoft 통화 계획을 사용하는 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-121">[A user in Skype for Business on-premises with Enterprise Voice](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan), who will be moving to online and using a Microsoft Calling plan.</span></span>  <span data-ttu-id="865d2-122">이 사용자를 Teams로 마이그레이션하려면 사용자의 비즈니스용 Skype 계정을 클라우드로 이동하고 A) 해당 사용자의 전화 번호 포트를 Microsoft 통화 계획 또는 B로 이동하도록 조정해야 합니다. 사용 가능한 지역에서 새 구독자 번호를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-122">Migrating this user to Teams requires moving the user’s on-premises Skype for Business account to the cloud, and coordinating that move with either A) the port of that user’s phone number to a Microsoft Calling Plan or B) assigning a new subscriber number from available regions.</span></span>

<span data-ttu-id="865d2-123">이 문서에서는 고급 개요만 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-123">This article provides a high-level overview only.</span></span> <span data-ttu-id="865d2-124">자세한 내용은 전화 시스템 [직접](direct-routing-landing-page.md) 라우팅 및 통화 [계획 을 참조하세요.](calling-plan-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="865d2-124">For more information, see [Phone System Direct Routing](direct-routing-landing-page.md) and [Calling Plans](calling-plan-landing-page.md).</span></span> 

## <a name="from-skype-for-business-online-with-microsoft-calling-plans"></a><span data-ttu-id="865d2-125">Microsoft 통화 계획을 통해 비즈니스용 Skype Online에서</span><span class="sxs-lookup"><span data-stu-id="865d2-125">From Skype for Business Online with Microsoft Calling Plans</span></span> 

<span data-ttu-id="865d2-126">음성과 관련된 가장 간단한 업그레이드 시나리오입니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-126">This is the simplest upgrade scenario involving voice.</span></span> 

1. <span data-ttu-id="865d2-127">사용자에게 Teams 라이선스가 할당되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-127">Make sure users have been assigned a Teams license.</span></span> <span data-ttu-id="865d2-128">기본적으로 Microsoft 365 또는 Office 365 라이선스를 할당할 때 Teams가 사용하도록 설정되어 있으므로 이전에 Teams 라이선스를 사용하지 않도록 설정한 경우 작업이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-128">By default, when you assign a Microsoft 365 or Office 365 license, Teams is enabled, so unless you previously disabled the Teams license, no action should be necessary.</span></span>

2.  <span data-ttu-id="865d2-129">사용자가 이미 전화 번호가 있는 Microsoft 통화 요금제가 있는 경우 TeamsUpgradePolicy에서 사용자 TeamsOnly 모드를 할당하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-129">If users already have a Microsoft Calling Plan with a phone number, the only required change is to assign the user TeamsOnly mode in TeamsUpgradePolicy.</span></span>  <span data-ttu-id="865d2-130">TeamsOnly 모드를 할당하기 전에 들어오는 PSTN 호출이 사용자의 비즈니스용 Skype 클라이언트에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-130">Prior to assigning TeamsOnly mode, incoming PSTN calls will land in the user’s Skype for Business client.</span></span> <span data-ttu-id="865d2-131">TeamsOnly 모드로 업그레이드한 후 들어오는 PSTN 호출이 사용자의 Teams 클라이언트에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-131">After the upgrade to TeamsOnly mode, incoming PSTN calls will land in the user’s Teams client.</span></span>  

## <a name="from-skype-for-business-online-with-on-premises-voice"></a><span data-ttu-id="865d2-132">비즈니스용 Skype Online에서온-프레미스 음성으로</span><span class="sxs-lookup"><span data-stu-id="865d2-132">From Skype for Business Online with on-premises voice</span></span>

<span data-ttu-id="865d2-133">이 시나리오에서는 사용자가 비즈니스용 Skype Online에 이미 있지만 해당 PSTN 연결은 하이브리드 모드 또는 Cloud Connector Edition에서 비즈니스용 Skype Server를 사용하는 프레미스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-133">In this scenario, the user is already in Skype for Business Online, but their PSTN connectivity is on-premises, either using Skype for Business Server in hybrid mode or Cloud Connector Edition.</span></span> <span data-ttu-id="865d2-134">PSTN 기능을 사용하여 이러한 사용자를 TeamsOnly 모드로 마이그레이션하는 것은 PSTN 트렁크가 SBC(On-Premises Session Border Controller)를 통해 클라우드의 직접 라우팅 서비스에 직접 연결하는 직접 라우팅을 사용하도록 설정하는 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-134">Migrating these users to TeamsOnly mode with PSTN functionality means enabling them for Direct Routing, in which PSTN trunks connect directly to the Direct Routing service in the cloud, via your on-premises Session Border Controller (SBC).</span></span>

<span data-ttu-id="865d2-135">기본 단계는 아래에 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-135">The basic steps are listed below.</span></span>  <span data-ttu-id="865d2-136">1-4단계는 제안된 순서대로 나열되지만 순서대로 수행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-136">Steps 1-4 are listed in the suggested sequence, but they can be done in any order.</span></span> <span data-ttu-id="865d2-137">이 모든 작업을 5단계 전에 완료해야 한다는 것이 핵심입니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-137">The key is that all of these should be completed before Step 5.</span></span>

1. <span data-ttu-id="865d2-138">테넌트 전체 정책을 비즈니스용 Skype 모드 중 하나로 설정하는 경우 이전에 설명한 바와 같이 섬 모드를 명시적으로 할당하여 기존 아일랜드 사용자를 할아버지 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-138">If you are setting the tenant-wide policy to one of the Skype for Business modes, be sure to grandfather any existing Islands users by explicitly assigning them Islands mode, as previously described.</span></span>

2. <span data-ttu-id="865d2-139">직접 라우팅에 대한 테넌트 구성</span><span class="sxs-lookup"><span data-stu-id="865d2-139">Configure your tenant for Direct Routing.</span></span> <span data-ttu-id="865d2-140">직접 라우팅의 테넌트당 구성 [요약을 참조합니다.](#summary-of-per-tenant-configuration-of-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="865d2-140">See [Summary of per-tenant configuration of Direct Routing](#summary-of-per-tenant-configuration-of-direct-routing).</span></span>

3. <span data-ttu-id="865d2-141">원하는 경우 이러한 사용자에 대한 다양한 Teams 정책(예: TeamsMessagingPolicy, TeamsMeetingPolicy 등)을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-141">If desired, configure various Teams policies for these users (for example, TeamsMessagingPolicy, TeamsMeetingPolicy, etc.).</span></span> <span data-ttu-id="865d2-142">이 작업을 언제든 할 수 있지만 업그레이드할 때 사용자가 올바른 구성을 하도록 보장하려면 사용자가 TeamsOnly 모드로 업그레이드되기 전에 이 작업을 하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-142">This can be done at any time, but if you want to ensure that users have the correct configuration when they are upgraded, it’s best to do this before the user is upgraded to TeamsOnly mode.</span></span>

4. <span data-ttu-id="865d2-143">음성 마이그레이션을 위해 선택 사용자를 준비합니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-143">Prepare select users for voice migration:</span></span> 
   - <span data-ttu-id="865d2-144">필요한 경우 Teams 라이선스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-144">If necessary, assign the Teams license.</span></span>  <span data-ttu-id="865d2-145">사용자가 비즈니스용 Skype Online온-프레미스 음성에서 이미 작동하고 있는 경우 사용자는 이미 비즈니스용 Skype 요금제 2와 Microsoft Phone System을 갖추고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-145">Assuming the user is already functional in Skype for Business Online on-premises voice, the user already has Skype for Business Plan 2 as well as Microsoft Phone System.</span></span> <span data-ttu-id="865d2-146">비즈니스용 Skype Online 계획 2 라이선스를 포함하여 이러한 계획을 모두 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-146">Leave both those plans enabled, including the Skype for Business Online Plan 2 license.</span></span>  
   - <span data-ttu-id="865d2-147">원하는 OnlineVoiceRoutingPolicy를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-147">Assign the desired OnlineVoiceRoutingPolicy.</span></span> 

5. <span data-ttu-id="865d2-148">사용자 업그레이드: 이러한 단계를 조정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-148">Upgrade the user: These steps should be coordinated.</span></span> 

   - <span data-ttu-id="865d2-149">Microsoft 365 또는 Office 365에서 사용자를 TeamsOnly 모드(Grant-CsTeamsUpgradePolicy)로 업그레이드합니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-149">In Microsoft 365 or Office 365, upgrade the user to TeamsOnly mode (Grant-CsTeamsUpgradePolicy).</span></span>
   - <span data-ttu-id="865d2-150">SBC에서 음성 라우팅을 구성하여 들어오는 통화를 활성화하기 위해 프레미스 중재 서버 대신 직접 라우팅에 대한 호출을 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-150">On the SBC, configure voice routing to enable incoming calls by sending calls to Direct Routing instead of to the on-premises Mediation Server.</span></span>


## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing"></a><span data-ttu-id="865d2-151">비즈니스용 Skype 서버의 온라인 Enterprise Voice 라우팅</span><span class="sxs-lookup"><span data-stu-id="865d2-151">From Skype for Business Server on-premises, with Enterprise Voice, to Direct Routing</span></span>

<span data-ttu-id="865d2-152">이 시나리오에서는 사용자가 여전히 비즈니스용 Skype On-프레미스에 있으며 해당 PSTN 연결도 프레미스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-152">In this scenario, the user is still homed in Skype for Business on-premises, and their PSTN connectivity is also on-premises.</span></span> <span data-ttu-id="865d2-153">PSTN 기능을 사용하여 이러한 사용자를 TeamsOnly 모드로 마이그레이션하는 것은 직접 라우팅을 사용하도록 설정한 다음 사용자를 클라우드로 이동하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-153">Migrating these users to TeamsOnly mode with PSTN functionality means enabling them for Direct Routing and then moving the user to the cloud.</span></span> 
 
<span data-ttu-id="865d2-154">기본 단계는 아래에 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-154">The basic steps are listed below.</span></span>  <span data-ttu-id="865d2-155">1-5단계는 제안된 순서대로 나열되지만 순서대로 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-155">Steps 1-5 are listed in the suggested sequence, but they can be done in any order.</span></span> <span data-ttu-id="865d2-156">이 모든 작업을 6단계 전에 완료해야 한다는 것이 핵심입니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-156">The key is that all of these should be completed before Step 6.</span></span>

1. <span data-ttu-id="865d2-157">테넌트 전체 정책을 비즈니스용 Skype 모드 중 하나로 설정하는 경우 이전에 설명한 바와 같이 아일랜드 모드를 명시적으로 할당하여 기존 아일랜드 사용자를 할아버지 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-157">If you will be setting the tenant-wide policy to one of the Skype for Business modes, be sure to grandfather existing Islands users by explicitly assigning them Islands mode, as previously described.</span></span>

2. <span data-ttu-id="865d2-158">아직 수행하지 않은 경우 [비즈니스용 Skype 하이브리드 조직을 구성합니다.](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)</span><span class="sxs-lookup"><span data-stu-id="865d2-158">If you haven’t already done so, [configure the organization for Skype for Business hybrid](/SkypeForBusiness/hybrid/configure-hybrid-connectivity).</span></span>

3. <span data-ttu-id="865d2-159">직접 라우팅에 대한 테넌트 구성</span><span class="sxs-lookup"><span data-stu-id="865d2-159">Configure your tenant for Direct Routing.</span></span> <span data-ttu-id="865d2-160">직접 라우팅의 테넌트당 구성 [요약을 참조합니다.](#summary-of-per-tenant-configuration-of-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="865d2-160">See [Summary of per-tenant configuration of Direct Routing](#summary-of-per-tenant-configuration-of-direct-routing).</span></span>

4. <span data-ttu-id="865d2-161">원하는 경우 이러한 사용자에 대한 다양한 Teams 정책(예: TeamsMessagingPolicy, TeamsMeetingPolicy 등)을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-161">If desired, configure various Teams policies for these users (e.g. TeamsMessagingPolicy, TeamsMeetingPolicy, etc.).</span></span> <span data-ttu-id="865d2-162">이 작업을 언제든 할 수 있지만 사용자가 업그레이드할 때 올바른 구성을 하도록 보장하려면 사용자가 TeamsOnly로 업그레이드하기 전에 이 작업을 하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-162">This can be done at any time, but if you want to ensure that users have the correct configuration when they are upgraded, it’s best to do this before the user is upgraded to TeamsOnly.</span></span>

5. <span data-ttu-id="865d2-163">필요한 경우 Microsoft 365 또는 Office 365 라이선스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-163">Assign the Microsoft 365 or Office 365 licenses if necessary.</span></span>  <span data-ttu-id="865d2-164">사용자에게는 전화 시스템뿐만 아니라 Teams 및 비즈니스용 Skype Online 계획 2가 모두 있습니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-164">The user should have both Teams and Skype for Business Online Plan 2, as well as Phone System.</span></span> <span data-ttu-id="865d2-165">비즈니스용 Skype Online 계획 2를 사용하지 않도록 설정한 경우 다시 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-165">If the Skype for Business Online Plan 2 is disabled, re-enable it.</span></span>  

6. <span data-ttu-id="865d2-166">사용자 업그레이드: 이러한 단계를 조정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-166">Upgrade the user: These steps should be coordinated.</span></span> 

   - <span data-ttu-id="865d2-167">비즈니스용 Skype 도구를 사용하여 -MoveToTeams 스위치로 Move-CsUser 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-167">Using the on-premises Skype for Business tools, run Move-CsUser with -MoveToTeams switch.</span></span> <span data-ttu-id="865d2-168">-MoveToTeams 스위치를 지원하지 않는 비즈니스용 Skype 서버 버전을 사용하는 경우 먼저 실행을 Move-CsUser 테넌트 원격 PowerShell 또는 Teams 관리 콘솔에서 TeamsOnly 모드를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-168">If you are using a version of Skype for Business Server that does not support the -MoveToTeams switch, first run Move-CsUser and then assign TeamsOnly mode in tenant remote PowerShell or Teams Admin Console.</span></span>

   - <span data-ttu-id="865d2-169">SBC에서 음성 라우팅을 구성하여 들어오는 통화를 활성화하기 위해 프레미스 중재 서버 대신 직접 라우팅에 대한 호출을 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-169">On the SBC, configure voice routing to enable incoming calls by sending calls to Direct Routing instead of to the on-premises Mediation Server.</span></span> 

   - <span data-ttu-id="865d2-170">Microsoft 365 또는 Office 365: 관련 OnlineVoiceRoutingPolicy를 할당하여 통화를 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-170">In Microsoft 365 or Office 365: Assign the relevant OnlineVoiceRoutingPolicy to enable outgoing calls.</span></span> 


## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan"></a><span data-ttu-id="865d2-171">비즈니스용 Skype 서버의 모든 기능을 Enterprise Voice Microsoft 통화 계획으로</span><span class="sxs-lookup"><span data-stu-id="865d2-171">From Skype for Business Server on-premises, with Enterprise Voice, to Microsoft Calling Plan</span></span>

<span data-ttu-id="865d2-172">이 시나리오에서는 사용자가 여전히 비즈니스용 Skype On-프레미스에 있으며 해당 PSTN 연결도 프레미스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-172">In this scenario, the user is still homed in Skype for Business on-premises, and their PSTN connectivity is also on-premises.</span></span> <span data-ttu-id="865d2-173">PSTN 기능을 사용하여 이러한 사용자를 TeamsOnly 모드로 마이그레이션하는 것은 사용자를 클라우드로 이동하고 이전 통신 사업자에서 Microsoft 통화 계획으로 번호를 이식하거나 사용자에게 새 번호를 할당하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-173">Migrating these users to TeamsOnly mode with PSTN functionality means moving the user to the cloud and either porting their number from the old carrier to a Microsoft Calling plan or assigning the user a new number.</span></span> 

<span data-ttu-id="865d2-174">기본 단계는 아래에 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-174">The basic steps are listed below.</span></span><span data-ttu-id="865d2-175">1-5단계는 제안된 순서대로 나열되지만 순서대로 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-175">  Steps 1-5 are listed in the suggested sequence, but they can be done in any order.</span></span> <span data-ttu-id="865d2-176">이 모든 작업을 6단계 전에 완료해야 한다는 것이 핵심입니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-176">The key is that all of these should be completed before Step 6.</span></span> 

1. <span data-ttu-id="865d2-177">테넌트 전체 정책을 비즈니스용 Skype 모드 중 하나로 설정하는 경우 이전에 설명한 바와 같이 아일랜드 모드를 명시적으로 할당하여 기존 아일랜드 사용자를 할아버지 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-177">If you will be setting the tenant-wide policy to one of the Skype for Business modes, be sure to grandfather existing Islands users by explicitly assigning them Islands mode, as previously described.</span></span> 

2. <span data-ttu-id="865d2-178">아직 수행하지 않은 경우 [비즈니스용 Skype 하이브리드 조직을 구성합니다.](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)</span><span class="sxs-lookup"><span data-stu-id="865d2-178">If you haven’t already done so, [configure the organization for Skype for Business hybrid](/SkypeForBusiness/hybrid/configure-hybrid-connectivity).</span></span> 

3. <span data-ttu-id="865d2-179">원하는 경우 이러한 사용자에 대한 다양한 Teams 정책(예: TeamsMessagingPolicy, TeamsMeetingPolicy 등)을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-179">If desired, configure various Teams policies for these users (for example, TeamsMessagingPolicy, TeamsMeetingPolicy, etc.).</span></span> <span data-ttu-id="865d2-180">이 작업을 언제든 할 수 있지만 사용자가 업그레이드할 때 올바른 구성을 하도록 보장하려면 사용자가 TeamsOnly로 업그레이드하기 전에 이 작업을 하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-180">This can be done at any time, but if you want to ensure that users have the correct configuration when they are upgraded, it’s best to do this before the user is upgraded to TeamsOnly.</span></span> 

4. <span data-ttu-id="865d2-181">필요한 경우 Microsoft 365 또는 Office 365 라이선스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-181">Assign the Microsoft 365 or Office 365 licenses if necessary.</span></span><span data-ttu-id="865d2-182">사용자에게는 전화 시스템뿐만 아니라 Teams 및 비즈니스용 Skype Online 계획 2가 모두 있습니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-182">  The user should have both Teams and Skype for Business Online Plan 2, as well as Phone System.</span></span> <span data-ttu-id="865d2-183">비즈니스용 Skype Online 계획 2를 사용하지 않도록 설정한 경우 다시 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-183">If the Skype for Business Online Plan 2 is disabled, re-enable it.</span></span>  

5. <span data-ttu-id="865d2-184">사용자에 대한 전화 번호를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-184">Get phone numbers for your users.</span></span> <span data-ttu-id="865d2-185">(자세한 내용은 조직의 [전화 번호 관리를 참조합니다.](./manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)</span><span class="sxs-lookup"><span data-stu-id="865d2-185">(For details see [Manage phone numbers for your organization](./manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).)</span></span>

   - <span data-ttu-id="865d2-186">번호를 다시 사용하는 경우 이동통신사에 이식 요청을 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-186">If you will be re-using the numbers, submit a porting request to your carrier.</span></span>  
   - <span data-ttu-id="865d2-187">또는 Microsoft에서 직접 새 번호를 획득할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-187">Alternatively, you can acquire new numbers directly from Microsoft.</span></span> 

6. <span data-ttu-id="865d2-188">사용자를 업그레이드하고 필요한 경우 LineUri를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-188">Upgrade the user and if needed assign LineUri.</span></span> <span data-ttu-id="865d2-189">비즈니스용 Skype 도구를 사용하여 -MoveToTeams Move-CsUser 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-189">Using the on-premises Skype for Business tools, run Move-CsUser with the -MoveToTeams switch.</span></span>  

    - <span data-ttu-id="865d2-190">Microsoft에 번호를 포터링하는 경우 포트가 발생할 때 이 작업의 타이밍을 조정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-190">If you are porting numbers to Microsoft, you should coordinate the timing of this operation to occur when the port occurs.</span></span> 

    - <span data-ttu-id="865d2-191">Microsoft에서 새 번호를 사용하는 경우 사용자에 대한 LineUri를 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-191">If you are using new numbers from Microsoft, you’ll need to change the LineUri for the user.</span></span> <span data-ttu-id="865d2-192">Set-CsOnlineVoiceUser를 사용하여 사용자가 온라인으로 이동한 후 이 방법을 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-192">This must be done after the user is moved online using Set-CsOnlineVoiceUser.</span></span>  

## <a name="summary-of-per-tenant-configuration-of-direct-routing"></a><span data-ttu-id="865d2-193">직접 라우팅의 테넌트당 구성 요약</span><span class="sxs-lookup"><span data-stu-id="865d2-193">Summary of per-tenant configuration of Direct Routing</span></span> 

1. <span data-ttu-id="865d2-194">이 목록을 검토하여 SBC(세션 테두리 컨트롤러)가 직접 라우팅에서 [지원되는지 확인](direct-routing-border-controllers.md)</span><span class="sxs-lookup"><span data-stu-id="865d2-194">Ensure that your Session Border Controller (SBC) is supported with Direct Routing by reviewing [this list](direct-routing-border-controllers.md).</span></span> <span data-ttu-id="865d2-195">또한 올바른 버전의 펌웨어가 있는지도 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-195">You must also ensure that you have correct version of firmware.</span></span>  

2. <span data-ttu-id="865d2-196">팀 다이렉트 라우팅 서비스와 프레미스 SBC를 페어링합니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-196">Pair your on-premises SBC with the Teams Direct Routing service.</span></span> <span data-ttu-id="865d2-197">자세한 내용은 전화 시스템의 직접 라우팅 서비스에 [SBC 쌍을 참조합니다.](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="865d2-197">For details, see [Pair the SBC to the Direct Routing service of Phone System](direct-routing-configure.md).</span></span> 

3. <span data-ttu-id="865d2-198">이 구성은 기본적으로 프레미스 구성의 미러입니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-198">This configuration is essentially a mirror of the on-premises configuration.</span></span> <span data-ttu-id="865d2-199">온라인 구성은 다음으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-199">The online configuration consists of:</span></span> 
   - <span data-ttu-id="865d2-200">OnlineVoiceRoutingPolicy(비즈니스용 Skype Online에서 사용자를 마이그레이션하는 경우 On-프레미스 VoiceRoutingPolicy에 기반하고, 사용자가 프레미스에서 마이그레이션하는 경우 VoicePolicy를 기반으로 Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="865d2-200">OnlineVoiceRoutingPolicy (based on the on-premises VoiceRoutingPolicy if migrating users from Skype for Business   Online, and based on VoicePolicy if migrating users from on-premises with Enterprise Voice).</span></span>
   - <span data-ttu-id="865d2-201">OnlinePSTNUsage 개체(온-프레미스 PSTN 사용량에 따라)</span><span class="sxs-lookup"><span data-stu-id="865d2-201">OnlinePSTNUsage objects (based on on-premises PSTN usage).</span></span> 
   - <span data-ttu-id="865d2-202">OnlineVoiceRoute 개체(On-Premises VoiceRoute 기반).</span><span class="sxs-lookup"><span data-stu-id="865d2-202">OnlineVoiceRoute objects (based on-premises VoiceRoute).</span></span> 

<span data-ttu-id="865d2-203">자세한 내용은 직접 라우팅 [구성을 참조하세요.](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="865d2-203">For more information, see [Configure Direct Routing](direct-routing-configure.md).</span></span> 

## <a name="manage-enterprisevoiceenabled-property-during-migration"></a><span data-ttu-id="865d2-204">마이그레이션하는 동안 EnterpriseVoiceEnabled 속성 관리</span><span class="sxs-lookup"><span data-stu-id="865d2-204">Manage EnterpriseVoiceEnabled property during migration</span></span> 

<span data-ttu-id="865d2-205">직접 라우팅 또는 Microsoft 통화 요금제 사용 여부에 따라 사용자가 PSTN 기능을 사용하려면 Azure AD에 EnterpriseVoiceEnabled=true가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-205">Whether using Direct Routing or a Microsoft Calling plan, a user must have EnterpriseVoiceEnabled=true in Azure AD for the user to have PSTN functionality.</span></span>  <span data-ttu-id="865d2-206">EnterpriseVoiceEnabled("EV 사용")는 프레미스 디렉터리와 클라우드 모두에 있는 속성(정책이 아 아우름)입니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-206">EnterpriseVoiceEnabled (“EV-enabled”) is a property (not a policy) that exists in both an on-premises directory and in the cloud.</span></span> <span data-ttu-id="865d2-207">클라우드의 값은 Teams에 중요한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-207">The value in the cloud is what matters for Teams.</span></span>  <span data-ttu-id="865d2-208">EV를 사용하도록 설정하는 방법에 대한 정확한 논리는 다음 시나리오에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-208">The exact logic for how EV-enabled gets set to true depends on the following scenario:</span></span> 

- <span data-ttu-id="865d2-209">사용자가 비즈니스용 Skype 서버에서 EV를 사용하도록 설정하고 이동 CsUser를 통해 사용자를 클라우드로 이동하기 전에 사용자에게 전화 시스템 라이선스가 할당된 경우 온라인 사용자는 EV-enabled=true로 프로비전됩니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-209">If the user is EV-enabled in on-premises Skype for Business Server and a Phone System license is assigned to the user prior to moving the user to the cloud with Move-CsUser, the online user will be provisioned with EV-enabled=true.</span></span> 

- <span data-ttu-id="865d2-210">기존 TeamsOnly 또는 비즈니스용 Skype Online 사용자에게 전화 시스템 라이선스가 할당된 경우 EV 사용은 기본적으로 true로 설정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-210">If an existing TeamsOnly or Skype for Business Online user is assigned a Phone System license, EV-enabled is not set to true by default.</span></span>  <span data-ttu-id="865d2-211">이는 전화 시스템 라이선스를 할당하기 전에 프레미스 사용자가 클라우드로 이동하는 경우에도 해당됩니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-211">This also is the case if an on-premises user is moved to the cloud prior to assigning the Phone System license.</span></span> <span data-ttu-id="865d2-212">두 경우 모두 관리자는 다음 cmdlet을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="865d2-212">In either case, the admin must specify the following cmdlet:</span></span> 

  ```PowerShell
  Set-CsUser -EnterpriseVoiceEnabled $True 
  ```

## <a name="related-links"></a><span data-ttu-id="865d2-213">관련 링크</span><span class="sxs-lookup"><span data-stu-id="865d2-213">Related links</span></span>

[<span data-ttu-id="865d2-214">Teams 음성 솔루션 계획</span><span class="sxs-lookup"><span data-stu-id="865d2-214">Plan your Teams voice solution</span></span>](cloud-voice-landing-page.md)

[<span data-ttu-id="865d2-215">비즈니스용 Skype와 함께 Teams를 사용하는 조직에 대한 마이그레이션 및 상호 연동성 지침</span><span class="sxs-lookup"><span data-stu-id="865d2-215">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="865d2-216">비즈니스용 Skype 서버와 Microsoft 365 또는 Office 365 간에 하이브리드 연결 구성</span><span class="sxs-lookup"><span data-stu-id="865d2-216">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="865d2-217">온-프레미스와 클라우드 간에 사용자 이동</span><span class="sxs-lookup"><span data-stu-id="865d2-217">Move users between on-premises and cloud</span></span>](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="865d2-218">공존 및 업그레이드 설정 설정</span><span class="sxs-lookup"><span data-stu-id="865d2-218">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="865d2-219">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="865d2-219">Grant-CsTeamsUpgradePolicy</span></span>](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="865d2-220">MMS(모임 마이그레이션 서비스) 사용</span><span class="sxs-lookup"><span data-stu-id="865d2-220">Using the Meeting Migration Service (MMS)</span></span>](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)