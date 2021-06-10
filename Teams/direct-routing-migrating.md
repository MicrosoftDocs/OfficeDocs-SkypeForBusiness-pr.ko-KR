---
title: 직접 라우팅으로 마이그레이션
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 온라인에서 직접 라우팅으로 마이그레이션하는 데 필요한 비즈니스용 Skype 및 구성 Teams 자세히 알아보는 것이 좋습니다.
ms.openlocfilehash: de211dfae9bf2fc20a2cd367687e0fd7c5779a5f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122202"
---
# <a name="migrate-to-direct-routing"></a><span data-ttu-id="fc95b-103">직접 라우팅으로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="fc95b-103">Migrate to Direct Routing</span></span>

<span data-ttu-id="fc95b-104">이 문서에서는 온라인에서 직접 라우팅으로 마이그레이션하는 데 비즈니스용 Skype 구성 관점에서 Microsoft Teams 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fc95b-104">This article describes what is needed to migrate to Direct Routing from a Skype for Business Online and Microsoft Teams configuration perspective.</span></span> <span data-ttu-id="fc95b-105">이 문서에서는 다음에서 마이그레이션하는 데 대해 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc95b-105">This article covers migrating from the following:</span></span> 
 
- <span data-ttu-id="fc95b-106">전화 시스템 계획(Teams 및 비즈니스용 Skype)</span><span class="sxs-lookup"><span data-stu-id="fc95b-106">Phone System with Calling Plans (for Teams and Skype for Business Online)</span></span> 
- <span data-ttu-id="fc95b-107">전화 시스템 PSTN 연결을 통해 비즈니스용 Skype 서버(비즈니스용 Skype 온라인용)</span><span class="sxs-lookup"><span data-stu-id="fc95b-107">Phone System with on-premises PSTN Connectivity in Skype for Business Server (for Skype for Business Online)</span></span>  
- <span data-ttu-id="fc95b-108">전화 시스템 커넥터 버전(온라인용)을 사용하여온-프레미스 PSTN 비즈니스용 Skype 사용</span><span class="sxs-lookup"><span data-stu-id="fc95b-108">Phone System with on-premises PSTN Connectivity by using the Cloud Connector Edition (for Skype for Business Online)</span></span>


<span data-ttu-id="fc95b-109">이러한 구성 단계 외에도 새 경로로 호출을 라우팅하려면 SBC(세션 테두리 컨트롤러)에 구성이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="fc95b-109">In addition to these configuration steps, configuration is also required on the Session Border Controller (SBC) to route the calls to the new route.</span></span> <span data-ttu-id="fc95b-110">이 문서의 범위를 벗어날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc95b-110">That is outside the scope of this document.</span></span> <span data-ttu-id="fc95b-111">자세한 내용은 SBC 공급업체 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fc95b-111">For more information, see your SBC vendor documentation.</span></span>  

## <a name="user-provisioning-end-state-for-various-pstn-connectivity-options"></a><span data-ttu-id="fc95b-112">다양한 PSTN 연결 옵션에 대한 사용자 프로비전 엔드 상태</span><span class="sxs-lookup"><span data-stu-id="fc95b-112">User provisioning end-state for various PSTN connectivity options</span></span> 

<span data-ttu-id="fc95b-113">다음 표에서는 선택한 PSTN 연결 옵션에 대해 프로비전된 사용자의 최종 상태를 전화 시스템.</span><span class="sxs-lookup"><span data-stu-id="fc95b-113">The following table shows the end-state for a user provisioned for the selected PSTN connectivity options with Phone System.</span></span> <span data-ttu-id="fc95b-114">음성과 관련된 특성만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc95b-114">Only attributes relevant for voice are shown.</span></span>

|<span data-ttu-id="fc95b-115">사용자 개체 특성</span><span class="sxs-lookup"><span data-stu-id="fc95b-115">User object attributes</span></span> |<span data-ttu-id="fc95b-116">통화 플랜을 사용하는 전화 시스템</span><span class="sxs-lookup"><span data-stu-id="fc95b-116">Phone System with Calling Plans</span></span>|<span data-ttu-id="fc95b-117">전화 시스템 PSTN 연결을 통해 비즈니스용 Skype 서버</span><span class="sxs-lookup"><span data-stu-id="fc95b-117">Phone System with on-premises PSTN connectivity via Skype for Business Server</span></span>|<span data-ttu-id="fc95b-118">전화 시스템 커넥터를 통해 PSTN 연결과 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc95b-118">Phone System with on-premises PSTN connectivity via Cloud Connector</span></span>|<span data-ttu-id="fc95b-119">전화 시스템 라우팅을 통해 프레미스 PSTN 연결로 연결</span><span class="sxs-lookup"><span data-stu-id="fc95b-119">Phone System with on-premises PSTN connectivity via Direct Routing</span></span>|
|---|---|---|---|---|
|<span data-ttu-id="fc95b-120">클라이언트</span><span class="sxs-lookup"><span data-stu-id="fc95b-120">Client</span></span>|<span data-ttu-id="fc95b-121">비즈니스용 Skype 또는 Teams</span><span class="sxs-lookup"><span data-stu-id="fc95b-121">Skype for Business or Teams</span></span> |<span data-ttu-id="fc95b-122">비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="fc95b-122">Skype for Business</span></span> |<span data-ttu-id="fc95b-123">비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="fc95b-123">Skype for Business</span></span> |<span data-ttu-id="fc95b-124">Teams</span><span class="sxs-lookup"><span data-stu-id="fc95b-124">Teams</span></span>|
|<span data-ttu-id="fc95b-125">라이선스</span><span class="sxs-lookup"><span data-stu-id="fc95b-125">Licenses</span></span>|<span data-ttu-id="fc95b-126">Skype Business Online</span><span class="sxs-lookup"><span data-stu-id="fc95b-126">Skype Business Online</span></span></br><span data-ttu-id="fc95b-127">계획 2</span><span class="sxs-lookup"><span data-stu-id="fc95b-127">Plan 2</span></span></br></br><span data-ttu-id="fc95b-128">MCOProfessional 또는 MCOSTANDARD)</span><span class="sxs-lookup"><span data-stu-id="fc95b-128">MCOProfessional or MCOSTANDARD)</span></span></br></br></br><span data-ttu-id="fc95b-129">전화 시스템(MCOEV)</span><span class="sxs-lookup"><span data-stu-id="fc95b-129">Phone System (MCOEV)</span></span></br></br></br><span data-ttu-id="fc95b-130">통화 플랜</span><span class="sxs-lookup"><span data-stu-id="fc95b-130">Calling Plans</span></span></br><span data-ttu-id="fc95b-131">Teams</span><span class="sxs-lookup"><span data-stu-id="fc95b-131">Teams</span></span>|<span data-ttu-id="fc95b-132">Skype Business Online 계획 2(MCOProfessional 또는 MCOSTANDARD)</span><span class="sxs-lookup"><span data-stu-id="fc95b-132">Skype Business Online Plan 2 (MCOProfessional or MCOSTANDARD)</span></span></br></br></br><span data-ttu-id="fc95b-133">전화 시스템(MCOEV)</span><span class="sxs-lookup"><span data-stu-id="fc95b-133">Phone System (MCOEV)</span></span>|<span data-ttu-id="fc95b-134">Skype Business Online 계획 2(MCOProfessional 또는 MCOSTANDARD)</span><span class="sxs-lookup"><span data-stu-id="fc95b-134">Skype Business Online Plan 2 (MCOProfessional or MCOSTANDARD)</span></span></br></br></br><span data-ttu-id="fc95b-135">전화 시스템(MCOEV)</span><span class="sxs-lookup"><span data-stu-id="fc95b-135">Phone System (MCOEV)</span></span>|<span data-ttu-id="fc95b-136">Skype Business Online 계획 2(MCOProfessional 또는 MCOSTANDARD)</span><span class="sxs-lookup"><span data-stu-id="fc95b-136">Skype Business Online Plan 2 (MCOProfessional or MCOSTANDARD</span></span></br></br></br><span data-ttu-id="fc95b-137">전화 시스템(MCOEV)</span><span class="sxs-lookup"><span data-stu-id="fc95b-137">Phone System (MCOEV)</span></span></br></br><span data-ttu-id="fc95b-138">Teams</span><span class="sxs-lookup"><span data-stu-id="fc95b-138">Teams</span></span>|
<span data-ttu-id="fc95b-139">OnPremLineURI</span><span class="sxs-lookup"><span data-stu-id="fc95b-139">OnPremLineURI</span></span> |<span data-ttu-id="fc95b-140">해당 없음</span><span class="sxs-lookup"><span data-stu-id="fc95b-140">N/A</span></span>|<span data-ttu-id="fc95b-141">전화 번호는 프레미스 AD에서 동기화되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc95b-141">The phone number  must be synced from the on-premises AD.</span></span> |<span data-ttu-id="fc95b-142">전화 번호는 프레미스 Active Directory 또는 프레미스에서 관리할 수 Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="fc95b-142">The phone number can be managed either in on-premises Active Directory or in Azure Active Directory.</span></span>|<span data-ttu-id="fc95b-143">전화 번호는 프레미스 Active Directory 또는 프레미스에서 관리할 수 Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="fc95b-143">The phone number can be managed either in on-premises Active Directory or in Azure Active Directory.</span></span> <span data-ttu-id="fc95b-144">그러나 조직에 프레미스가 있는 비즈니스용 Skype 수를 On-프레미스 Active Directory에서 동기화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc95b-144">However, if the organization has on-premises Skype for Business, the number must be synced from the on-premises Active Directory.</span></span>|
|<span data-ttu-id="fc95b-145">LineURI</span><span class="sxs-lookup"><span data-stu-id="fc95b-145">LineURI</span></span>|<span data-ttu-id="fc95b-146">PSTN 통화 전화 번호</span><span class="sxs-lookup"><span data-stu-id="fc95b-146">PSTN Calling phone number</span></span>|<span data-ttu-id="fc95b-147">OnPremLineURI 매개 변수에서 자동으로 설정</span><span class="sxs-lookup"><span data-stu-id="fc95b-147">Set automatically from the OnPremLineURI parameter</span></span>|<span data-ttu-id="fc95b-148">OnPremLineURI 매개 변수에서 자동으로 설정</span><span class="sxs-lookup"><span data-stu-id="fc95b-148">Set automatically from the OnPremLineURI parameter</span></span>|<span data-ttu-id="fc95b-149">OnPremLineURI 매개 변수에서 자동으로 설정</span><span class="sxs-lookup"><span data-stu-id="fc95b-149">Set automatically from the OnPremLineURI parameter</span></span>|
|<span data-ttu-id="fc95b-150">EnterpriseVoiceEnabled</span><span class="sxs-lookup"><span data-stu-id="fc95b-150">EnterpriseVoiceEnabled</span></span>|<span data-ttu-id="fc95b-151">True</span><span class="sxs-lookup"><span data-stu-id="fc95b-151">True</span></span>|<span data-ttu-id="fc95b-152">True</span><span class="sxs-lookup"><span data-stu-id="fc95b-152">True</span></span>|<span data-ttu-id="fc95b-153">True</span><span class="sxs-lookup"><span data-stu-id="fc95b-153">True</span></span>|<span data-ttu-id="fc95b-154">True</span><span class="sxs-lookup"><span data-stu-id="fc95b-154">True</span></span>|
|<span data-ttu-id="fc95b-155">HostedVoiceMail</span><span class="sxs-lookup"><span data-stu-id="fc95b-155">HostedVoiceMail</span></span> |<span data-ttu-id="fc95b-156">True</span><span class="sxs-lookup"><span data-stu-id="fc95b-156">True</span></span>|<span data-ttu-id="fc95b-157">True</span><span class="sxs-lookup"><span data-stu-id="fc95b-157">True</span></span>|<span data-ttu-id="fc95b-158">True</span><span class="sxs-lookup"><span data-stu-id="fc95b-158">True</span></span>|<span data-ttu-id="fc95b-159">True</span><span class="sxs-lookup"><span data-stu-id="fc95b-159">True</span></span>|
|<span data-ttu-id="fc95b-160">VoicePolicy</span><span class="sxs-lookup"><span data-stu-id="fc95b-160">VoicePolicy</span></span>|<span data-ttu-id="fc95b-161">BusinessVoice</span><span class="sxs-lookup"><span data-stu-id="fc95b-161">BusinessVoice</span></span>|<span data-ttu-id="fc95b-162">HybridVoice</span><span class="sxs-lookup"><span data-stu-id="fc95b-162">HybridVoice</span></span>|<span data-ttu-id="fc95b-163">HybridVoice</span><span class="sxs-lookup"><span data-stu-id="fc95b-163">HybridVoice</span></span>|<span data-ttu-id="fc95b-164">HybridVoice</span><span class="sxs-lookup"><span data-stu-id="fc95b-164">HybridVoice</span></span>|
|<span data-ttu-id="fc95b-165">HostedVoiceMailPolicy</span><span class="sxs-lookup"><span data-stu-id="fc95b-165">HostedVoiceMailPolicy</span></span> |<span data-ttu-id="fc95b-166">BusinessVoice</span><span class="sxs-lookup"><span data-stu-id="fc95b-166">BusinessVoice</span></span>|<span data-ttu-id="fc95b-167">BusinessVoice</span><span class="sxs-lookup"><span data-stu-id="fc95b-167">BusinessVoice</span></span>|<span data-ttu-id="fc95b-168">BusinessVoice</span><span class="sxs-lookup"><span data-stu-id="fc95b-168">BusinessVoice</span></span>|<span data-ttu-id="fc95b-169">BusinessVoice</span><span class="sxs-lookup"><span data-stu-id="fc95b-169">BusinessVoice</span></span>|
|<span data-ttu-id="fc95b-170">VoiceRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="fc95b-170">VoiceRoutingPolicy</span></span>|<span data-ttu-id="fc95b-171">값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc95b-171">Has a value</span></span>|<span data-ttu-id="fc95b-172">값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc95b-172">Has a value</span></span>|<span data-ttu-id="fc95b-173">값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc95b-173">Has a value</span></span>|<span data-ttu-id="fc95b-174">해당 없음</span><span class="sxs-lookup"><span data-stu-id="fc95b-174">N/A</span></span>|
|<span data-ttu-id="fc95b-175">OnlineVoiceRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="fc95b-175">OnlineVoiceRoutingPolicy</span></span>|<span data-ttu-id="fc95b-176">$Null</span><span class="sxs-lookup"><span data-stu-id="fc95b-176">$Null</span></span>|<span data-ttu-id="fc95b-177">$Null</span><span class="sxs-lookup"><span data-stu-id="fc95b-177">$Null</span></span>|<span data-ttu-id="fc95b-178">$Null</span><span class="sxs-lookup"><span data-stu-id="fc95b-178">$Null</span></span>|<span data-ttu-id="fc95b-179">값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc95b-179">Has a value</span></span>|
|<span data-ttu-id="fc95b-180">TeamsUpgradePolicy<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="fc95b-180">TeamsUpgradePolicy<sup>1</sup></span></span>|<span data-ttu-id="fc95b-181">TeamsOnly, SfBOnly</span><span class="sxs-lookup"><span data-stu-id="fc95b-181">TeamsOnly, SfBOnly</span></span>|<span data-ttu-id="fc95b-182">$Null</span><span class="sxs-lookup"><span data-stu-id="fc95b-182">$Null</span></span>|<span data-ttu-id="fc95b-183">$Null</span><span class="sxs-lookup"><span data-stu-id="fc95b-183">$Null</span></span>|<span data-ttu-id="fc95b-184">TeamsOnly</span><span class="sxs-lookup"><span data-stu-id="fc95b-184">TeamsOnly</span></span>|
|<span data-ttu-id="fc95b-185">TeamsCallingPolicy</span><span class="sxs-lookup"><span data-stu-id="fc95b-185">TeamsCallingPolicy</span></span></br><span data-ttu-id="fc95b-186">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="fc95b-186">AllowPrivateCalling</span></span>|<span data-ttu-id="fc95b-187">True</span><span class="sxs-lookup"><span data-stu-id="fc95b-187">True</span></span>|<span data-ttu-id="fc95b-188">해당 없음</span><span class="sxs-lookup"><span data-stu-id="fc95b-188">N/A</span></span>|<span data-ttu-id="fc95b-189">해당 없음</span><span class="sxs-lookup"><span data-stu-id="fc95b-189">N/A</span></span>|<span data-ttu-id="fc95b-190">True</span><span class="sxs-lookup"><span data-stu-id="fc95b-190">True</span></span>|
|<span data-ttu-id="fc95b-191">TeamsCallingPolicy</span><span class="sxs-lookup"><span data-stu-id="fc95b-191">TeamsCallingPolicy</span></span></br><span data-ttu-id="fc95b-192">AllowGroupCalling</span><span class="sxs-lookup"><span data-stu-id="fc95b-192">AllowGroupCalling</span></span>|<span data-ttu-id="fc95b-193">True</span><span class="sxs-lookup"><span data-stu-id="fc95b-193">True</span></span>|<span data-ttu-id="fc95b-194">해당 없음</span><span class="sxs-lookup"><span data-stu-id="fc95b-194">N/A</span></span>|<span data-ttu-id="fc95b-195">해당 없음</span><span class="sxs-lookup"><span data-stu-id="fc95b-195">N/A</span></span>|<span data-ttu-id="fc95b-196">True</span><span class="sxs-lookup"><span data-stu-id="fc95b-196">True</span></span>|
||||||

<span data-ttu-id="fc95b-197"><sup>1</sup> TeamsUpgradePolicy의 올바른 모드 선택은 시나리오에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="fc95b-197"><sup>1</sup> Choosing the right mode of the TeamsUpgradePolicy depends on the scenario.</span></span> <span data-ttu-id="fc95b-198">마이그레이션 및 상호운용성 지침에서 다른 모드에서 음성 환경과 함께 Teams [를](migration-interop-guidance-for-teams-with-skype.md)비즈니스용 Skype.</span><span class="sxs-lookup"><span data-stu-id="fc95b-198">Please read about the voice experience in different modes in [Migration and interoperability Guidance for organizations using Teams together with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span>

<span data-ttu-id="fc95b-199">이러한 노력의 일환으로 Microsoft는 최근 공존 모드를 기반으로 새 관리 모델을 반영하기 위해 "Microsoft Teams 관리 센터"(현대 포털라고도 합니다)를 업데이트했습니다.</span><span class="sxs-lookup"><span data-stu-id="fc95b-199">As part of this effort, Microsoft recently updated the “Microsoft Teams admin center” (also known as Modern Portal) to reflect the new management model based on coexistence modes.</span></span> <span data-ttu-id="fc95b-200">현대 포털에서 TeamsUpgradePolicy를 구성하면 TeamsInteropPolicy도 자동으로 일관된 값으로 설정되어 TeamsInteropPolicy가 사용자 인터페이스에 더 이상 노출되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fc95b-200">In Modern Portal, configuring TeamsUpgradePolicy will now automatically also set TeamsInteropPolicy to consistent value, so TeamsInteropPolicy is no longer exposed in the user interface.</span></span> <span data-ttu-id="fc95b-201">그러나 PowerShell을 사용하는 관리자는 적절한 라우팅을 보장하기 위해 TeamsUpgradePolicy와 TeamsInteropPolicy를 함께 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc95b-201">However, admins using PowerShell must still set both TeamsUpgradePolicy and TeamsInteropPolicy together to ensure proper routing.</span></span> <span data-ttu-id="fc95b-202">TeamsUpgradePolicy로 전환이 완료되면 TeamsInteropPolicy도 더 이상 설정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fc95b-202">After the transition to TeamsUpgradePolicy is complete, it will no longer be necessary to also set TeamsInteropPolicy.</span></span>

<span data-ttu-id="fc95b-203">자세한 내용은 와 함께 Teams 조직에 대한 마이그레이션 [및](migration-interop-guidance-for-teams-with-skype.md)상호 비즈니스용 Skype.</span><span class="sxs-lookup"><span data-stu-id="fc95b-203">For more information, please refer to [Migration and interoperability Guidance for organizations using Teams together with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span>

## <a name="migrating-from-calling-plans"></a><span data-ttu-id="fc95b-204">통화 계획에서 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="fc95b-204">Migrating from Calling Plans</span></span>

<span data-ttu-id="fc95b-205">통화 계획에서 마이그레이션하는 데 대한 자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fc95b-205">For more information about migrating from Calling Plans, see:</span></span>

- [<span data-ttu-id="fc95b-206">통화 플랜 설정</span><span class="sxs-lookup"><span data-stu-id="fc95b-206">Set up Calling Plans</span></span>](/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)
- [<span data-ttu-id="fc95b-207">Set-CsOnlineVoice 사용자</span><span class="sxs-lookup"><span data-stu-id="fc95b-207">Set-CsOnlineVoice User</span></span>](/powershell/module/skype/Set-CsOnlineVoiceUser?view=skype-ps)
- [<span data-ttu-id="fc95b-208">Get-CsOnlineLisLocation</span><span class="sxs-lookup"><span data-stu-id="fc95b-208">Get-CsOnlineLisLocation</span></span>](/powershell/module/skype/get-csonlinelislocation?view=skype-ps)  
 
 
<span data-ttu-id="fc95b-209">다음과 같이 이전에 구성된 라이선스 계획 정보를 제거하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fc95b-209">It is recommended that you remove previously configured licensing plan information as follows:</span></span>
 
```powershell
$companyname = “contoso” 
$lic1 = $companyname + “:MCOPSTN1” 
$lic2 = $companyname + “:MCOPSTN2” 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic1 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic2 
```
## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a><span data-ttu-id="fc95b-210">Office 365 전화 시스템 PSTN 연결로 비즈니스용 Skype 서버</span><span class="sxs-lookup"><span data-stu-id="fc95b-210">Migrating from Office 365 Phone System with on-premises PSTN connectivity in Skype for Business Server</span></span>

<span data-ttu-id="fc95b-211">전화 시스템 PSTN 연결로 마이그레이션하는 비즈니스용 Skype 서버 자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fc95b-211">For more information about migrating from Phone System with on-premises PSTN connectivity in Skype for Business Server, see the following:</span></span>

- [<span data-ttu-id="fc95b-212">계획</span><span class="sxs-lookup"><span data-stu-id="fc95b-212">Planning</span></span>](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)
- [<span data-ttu-id="fc95b-213">배포</span><span class="sxs-lookup"><span data-stu-id="fc95b-213">Deploying</span></span>](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system) 

<span data-ttu-id="fc95b-214">다음과 같이 이전에 구성된 음성 라우팅 정보를 제거하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fc95b-214">It is recommended that you remove previously configured voice routing information as follows:</span></span>

```PowerShell
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
```
> [!NOTE]
> <span data-ttu-id="fc95b-215">전역 CsVoiceRoutingPolicy가 구성된 경우 이 전역 정책과 연결된 모든 PSTN 사용량을 제거하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fc95b-215">If a global CsVoiceRoutingPolicy is configured, it is recommended that you remove any PSTN usages associated with this global policy.</span></span> 

## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-via-cloud-connector-edition"></a><span data-ttu-id="fc95b-216">클라우드 커넥터 Office 365 전화 시스템 통해 프레미스 PSTN 연결로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="fc95b-216">Migrating from Office 365 Phone System with on-premises PSTN connectivity via Cloud Connector Edition</span></span> 

> [!Important]
> <span data-ttu-id="fc95b-217">Cloud Connector Edition은 온라인과 함께 2021년 7월 31일 비즈니스용 Skype 사용 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc95b-217">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="fc95b-218">조직이 로 업그레이드된 Teams 직접 라우팅을 사용하여 프레미스 전화 통신 네트워크를 Teams [방법을 알아보습니다.](direct-routing-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="fc95b-218">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](direct-routing-landing-page.md).</span></span>

<span data-ttu-id="fc95b-219">Cloud Connector를 통한 전화 시스템 PSTN 연결로 마이그레이션에 대한 자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fc95b-219">For more information about migrating from Phone System with on-premises PSTN connectivity via Cloud Connector, see the following:</span></span>

- [<span data-ttu-id="fc95b-220">계획</span><span class="sxs-lookup"><span data-stu-id="fc95b-220">Planning</span></span>](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition)  
- [<span data-ttu-id="fc95b-221">배포</span><span class="sxs-lookup"><span data-stu-id="fc95b-221">Deploying</span></span>](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system)
- [<span data-ttu-id="fc95b-222">사용자 구성</span><span class="sxs-lookup"><span data-stu-id="fc95b-222">User configuration</span></span>](/powershell/module/skype/set-csuserpstnsettings?view=skype-ps) 

<span data-ttu-id="fc95b-223">다음과 같이 이전에 구성된 음성 라우팅 정보를 제거하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fc95b-223">It is recommended that you remove previously configured voice routing information as follows:</span></span>
 
```PowerShell
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
Set-CsUserPstnSettings -Identity <UPN> -AllowInternationalCalls $false -HybridPSTNSite $null 
```


## <a name="related-links"></a><span data-ttu-id="fc95b-224">관련 링크</span><span class="sxs-lookup"><span data-stu-id="fc95b-224">Related links</span></span>

[<span data-ttu-id="fc95b-225">조직과 함께 Teams 조직에 대한 마이그레이션 및 상호 비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="fc95b-225">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md)

[<span data-ttu-id="fc95b-226">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="fc95b-226">Grant-CsTeamsUpgradePolicy</span></span>](/powershell/module/skype/grant-csteamsupgradepolicy)

[<span data-ttu-id="fc95b-227">Get-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="fc95b-227">Get-CsTeamsUpgradePolicy</span></span>](/powershell/module/skype/Get-CsTeamsUpgradePolicy)

[<span data-ttu-id="fc95b-228">New-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="fc95b-228">New-CsTeamsUpgradePolicy</span></span>](/powershell/module/skype/New-CsTeamsUpgradePolicy)

[<span data-ttu-id="fc95b-229">Remove-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="fc95b-229">Remove-CsTeamsUpgradePolicy</span></span>](/powershell/module/skype/Remove-CsTeamsUpgradePolicy)

[<span data-ttu-id="fc95b-230">Set-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="fc95b-230">Set-CsTeamsUpgradePolicy</span></span>](/powershell/module/skype/Set-CsTeamsUpgradePolicy)

[<span data-ttu-id="fc95b-231">Get-CsTeamsUpgradeConfiguration</span><span class="sxs-lookup"><span data-stu-id="fc95b-231">Get-CsTeamsUpgradeConfiguration</span></span>](/powershell/module/skype/Get-CsTeamsUpgradeConfiguration)

[<span data-ttu-id="fc95b-232">Set-CsTeamsUpgradeConfiguration</span><span class="sxs-lookup"><span data-stu-id="fc95b-232">Set-CsTeamsUpgradeConfiguration</span></span>](/powershell/module/skype/Set-CsTeamsUpgradeConfiguration)