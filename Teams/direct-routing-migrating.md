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
description: 비즈니스용 Skype Online 및 Teams 구성 관점에서 직접 라우팅으로 마이그레이션하는 데 필요한 내용을 알아보습니다.
ms.openlocfilehash: de211dfae9bf2fc20a2cd367687e0fd7c5779a5f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122202"
---
# <a name="migrate-to-direct-routing"></a><span data-ttu-id="839f9-103">직접 라우팅으로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="839f9-103">Migrate to Direct Routing</span></span>

<span data-ttu-id="839f9-104">이 문서에서는 비즈니스용 Skype Online 및 Microsoft Teams 구성 관점에서 직접 라우팅으로 마이그레이션하는 데 필요한 것을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="839f9-104">This article describes what is needed to migrate to Direct Routing from a Skype for Business Online and Microsoft Teams configuration perspective.</span></span> <span data-ttu-id="839f9-105">이 문서에서는 다음에서 마이그레이션하는 데 대해 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="839f9-105">This article covers migrating from the following:</span></span> 
 
- <span data-ttu-id="839f9-106">통화 계획이 있는 전화 시스템(Teams 및 비즈니스용 Skype Online용)</span><span class="sxs-lookup"><span data-stu-id="839f9-106">Phone System with Calling Plans (for Teams and Skype for Business Online)</span></span> 
- <span data-ttu-id="839f9-107">비즈니스용 Skype Server에서 PSTN 연결이 있는 전화 시스템(비즈니스용 Skype Online용)</span><span class="sxs-lookup"><span data-stu-id="839f9-107">Phone System with on-premises PSTN Connectivity in Skype for Business Server (for Skype for Business Online)</span></span>  
- <span data-ttu-id="839f9-108">클라우드 커넥터 버전(비즈니스용 Skype Online용)을 사용하여온-프레미스 PSTN 연결을 사용하는 전화 시스템</span><span class="sxs-lookup"><span data-stu-id="839f9-108">Phone System with on-premises PSTN Connectivity by using the Cloud Connector Edition (for Skype for Business Online)</span></span>


<span data-ttu-id="839f9-109">이러한 구성 단계 외에도 새 경로로 호출을 라우팅하려면 SBC(세션 테두리 컨트롤러)에 구성이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="839f9-109">In addition to these configuration steps, configuration is also required on the Session Border Controller (SBC) to route the calls to the new route.</span></span> <span data-ttu-id="839f9-110">이 문서의 범위를 벗어날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="839f9-110">That is outside the scope of this document.</span></span> <span data-ttu-id="839f9-111">자세한 내용은 SBC 공급업체 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="839f9-111">For more information, see your SBC vendor documentation.</span></span>  

## <a name="user-provisioning-end-state-for-various-pstn-connectivity-options"></a><span data-ttu-id="839f9-112">다양한 PSTN 연결 옵션에 대한 사용자 프로비전 엔드 상태</span><span class="sxs-lookup"><span data-stu-id="839f9-112">User provisioning end-state for various PSTN connectivity options</span></span> 

<span data-ttu-id="839f9-113">다음 표에서는 Phone System을 사용하여 선택한 PSTN 연결 옵션에 대해 프로비전된 사용자의 최종 상태를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="839f9-113">The following table shows the end-state for a user provisioned for the selected PSTN connectivity options with Phone System.</span></span> <span data-ttu-id="839f9-114">음성과 관련된 특성만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="839f9-114">Only attributes relevant for voice are shown.</span></span>

|<span data-ttu-id="839f9-115">사용자 개체 특성</span><span class="sxs-lookup"><span data-stu-id="839f9-115">User object attributes</span></span> |<span data-ttu-id="839f9-116">통화 플랜을 사용하는 전화 시스템</span><span class="sxs-lookup"><span data-stu-id="839f9-116">Phone System with Calling Plans</span></span>|<span data-ttu-id="839f9-117">비즈니스용 Skype 서버를 통해 PSTN에 연결되는 전화 시스템</span><span class="sxs-lookup"><span data-stu-id="839f9-117">Phone System with on-premises PSTN connectivity via Skype for Business Server</span></span>|<span data-ttu-id="839f9-118">Cloud Connector를 통한 PSTN 연결로 전화 시스템</span><span class="sxs-lookup"><span data-stu-id="839f9-118">Phone System with on-premises PSTN connectivity via Cloud Connector</span></span>|<span data-ttu-id="839f9-119">직접 라우팅을 통해 프레미스 PSTN 연결이 있는 전화 시스템</span><span class="sxs-lookup"><span data-stu-id="839f9-119">Phone System with on-premises PSTN connectivity via Direct Routing</span></span>|
|---|---|---|---|---|
|<span data-ttu-id="839f9-120">클라이언트</span><span class="sxs-lookup"><span data-stu-id="839f9-120">Client</span></span>|<span data-ttu-id="839f9-121">비즈니스용 Skype 또는 Teams</span><span class="sxs-lookup"><span data-stu-id="839f9-121">Skype for Business or Teams</span></span> |<span data-ttu-id="839f9-122">비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="839f9-122">Skype for Business</span></span> |<span data-ttu-id="839f9-123">비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="839f9-123">Skype for Business</span></span> |<span data-ttu-id="839f9-124">Teams</span><span class="sxs-lookup"><span data-stu-id="839f9-124">Teams</span></span>|
|<span data-ttu-id="839f9-125">라이선스</span><span class="sxs-lookup"><span data-stu-id="839f9-125">Licenses</span></span>|<span data-ttu-id="839f9-126">Skype Business Online</span><span class="sxs-lookup"><span data-stu-id="839f9-126">Skype Business Online</span></span></br><span data-ttu-id="839f9-127">계획 2</span><span class="sxs-lookup"><span data-stu-id="839f9-127">Plan 2</span></span></br></br><span data-ttu-id="839f9-128">MCOProfessional 또는 MCOSTANDARD)</span><span class="sxs-lookup"><span data-stu-id="839f9-128">MCOProfessional or MCOSTANDARD)</span></span></br></br></br><span data-ttu-id="839f9-129">전화 시스템(MCOEV)</span><span class="sxs-lookup"><span data-stu-id="839f9-129">Phone System (MCOEV)</span></span></br></br></br><span data-ttu-id="839f9-130">통화 플랜</span><span class="sxs-lookup"><span data-stu-id="839f9-130">Calling Plans</span></span></br><span data-ttu-id="839f9-131">Teams</span><span class="sxs-lookup"><span data-stu-id="839f9-131">Teams</span></span>|<span data-ttu-id="839f9-132">Skype Business Online 계획 2(MCOProfessional 또는 MCOSTANDARD)</span><span class="sxs-lookup"><span data-stu-id="839f9-132">Skype Business Online Plan 2 (MCOProfessional or MCOSTANDARD)</span></span></br></br></br><span data-ttu-id="839f9-133">전화 시스템(MCOEV)</span><span class="sxs-lookup"><span data-stu-id="839f9-133">Phone System (MCOEV)</span></span>|<span data-ttu-id="839f9-134">Skype Business Online 계획 2(MCOProfessional 또는 MCOSTANDARD)</span><span class="sxs-lookup"><span data-stu-id="839f9-134">Skype Business Online Plan 2 (MCOProfessional or MCOSTANDARD)</span></span></br></br></br><span data-ttu-id="839f9-135">전화 시스템(MCOEV)</span><span class="sxs-lookup"><span data-stu-id="839f9-135">Phone System (MCOEV)</span></span>|<span data-ttu-id="839f9-136">Skype Business Online 계획 2(MCOProfessional 또는 MCOSTANDARD)</span><span class="sxs-lookup"><span data-stu-id="839f9-136">Skype Business Online Plan 2 (MCOProfessional or MCOSTANDARD</span></span></br></br></br><span data-ttu-id="839f9-137">전화 시스템(MCOEV)</span><span class="sxs-lookup"><span data-stu-id="839f9-137">Phone System (MCOEV)</span></span></br></br><span data-ttu-id="839f9-138">Teams</span><span class="sxs-lookup"><span data-stu-id="839f9-138">Teams</span></span>|
<span data-ttu-id="839f9-139">OnPremLineURI</span><span class="sxs-lookup"><span data-stu-id="839f9-139">OnPremLineURI</span></span> |<span data-ttu-id="839f9-140">해당 없음</span><span class="sxs-lookup"><span data-stu-id="839f9-140">N/A</span></span>|<span data-ttu-id="839f9-141">전화 번호는 프레미스 AD에서 동기화되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="839f9-141">The phone number  must be synced from the on-premises AD.</span></span> |<span data-ttu-id="839f9-142">전화 번호는 프레미스 Active Directory 또는 Azure Active Directory에서 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="839f9-142">The phone number can be managed either in on-premises Active Directory or in Azure Active Directory.</span></span>|<span data-ttu-id="839f9-143">전화 번호는 프레미스 Active Directory 또는 Azure Active Directory에서 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="839f9-143">The phone number can be managed either in on-premises Active Directory or in Azure Active Directory.</span></span> <span data-ttu-id="839f9-144">그러나 조직에 비즈니스용 Skype가 있는 경우 이 수를 On-프레미스 Active Directory에서 동기화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="839f9-144">However, if the organization has on-premises Skype for Business, the number must be synced from the on-premises Active Directory.</span></span>|
|<span data-ttu-id="839f9-145">LineURI</span><span class="sxs-lookup"><span data-stu-id="839f9-145">LineURI</span></span>|<span data-ttu-id="839f9-146">PSTN 통화 전화 번호</span><span class="sxs-lookup"><span data-stu-id="839f9-146">PSTN Calling phone number</span></span>|<span data-ttu-id="839f9-147">OnPremLineURI 매개 변수에서 자동으로 설정</span><span class="sxs-lookup"><span data-stu-id="839f9-147">Set automatically from the OnPremLineURI parameter</span></span>|<span data-ttu-id="839f9-148">OnPremLineURI 매개 변수에서 자동으로 설정</span><span class="sxs-lookup"><span data-stu-id="839f9-148">Set automatically from the OnPremLineURI parameter</span></span>|<span data-ttu-id="839f9-149">OnPremLineURI 매개 변수에서 자동으로 설정</span><span class="sxs-lookup"><span data-stu-id="839f9-149">Set automatically from the OnPremLineURI parameter</span></span>|
|<span data-ttu-id="839f9-150">EnterpriseVoiceEnabled</span><span class="sxs-lookup"><span data-stu-id="839f9-150">EnterpriseVoiceEnabled</span></span>|<span data-ttu-id="839f9-151">True</span><span class="sxs-lookup"><span data-stu-id="839f9-151">True</span></span>|<span data-ttu-id="839f9-152">True</span><span class="sxs-lookup"><span data-stu-id="839f9-152">True</span></span>|<span data-ttu-id="839f9-153">True</span><span class="sxs-lookup"><span data-stu-id="839f9-153">True</span></span>|<span data-ttu-id="839f9-154">True</span><span class="sxs-lookup"><span data-stu-id="839f9-154">True</span></span>|
|<span data-ttu-id="839f9-155">HostedVoiceMail</span><span class="sxs-lookup"><span data-stu-id="839f9-155">HostedVoiceMail</span></span> |<span data-ttu-id="839f9-156">True</span><span class="sxs-lookup"><span data-stu-id="839f9-156">True</span></span>|<span data-ttu-id="839f9-157">True</span><span class="sxs-lookup"><span data-stu-id="839f9-157">True</span></span>|<span data-ttu-id="839f9-158">True</span><span class="sxs-lookup"><span data-stu-id="839f9-158">True</span></span>|<span data-ttu-id="839f9-159">True</span><span class="sxs-lookup"><span data-stu-id="839f9-159">True</span></span>|
|<span data-ttu-id="839f9-160">VoicePolicy</span><span class="sxs-lookup"><span data-stu-id="839f9-160">VoicePolicy</span></span>|<span data-ttu-id="839f9-161">BusinessVoice</span><span class="sxs-lookup"><span data-stu-id="839f9-161">BusinessVoice</span></span>|<span data-ttu-id="839f9-162">HybridVoice</span><span class="sxs-lookup"><span data-stu-id="839f9-162">HybridVoice</span></span>|<span data-ttu-id="839f9-163">HybridVoice</span><span class="sxs-lookup"><span data-stu-id="839f9-163">HybridVoice</span></span>|<span data-ttu-id="839f9-164">HybridVoice</span><span class="sxs-lookup"><span data-stu-id="839f9-164">HybridVoice</span></span>|
|<span data-ttu-id="839f9-165">HostedVoiceMailPolicy</span><span class="sxs-lookup"><span data-stu-id="839f9-165">HostedVoiceMailPolicy</span></span> |<span data-ttu-id="839f9-166">BusinessVoice</span><span class="sxs-lookup"><span data-stu-id="839f9-166">BusinessVoice</span></span>|<span data-ttu-id="839f9-167">BusinessVoice</span><span class="sxs-lookup"><span data-stu-id="839f9-167">BusinessVoice</span></span>|<span data-ttu-id="839f9-168">BusinessVoice</span><span class="sxs-lookup"><span data-stu-id="839f9-168">BusinessVoice</span></span>|<span data-ttu-id="839f9-169">BusinessVoice</span><span class="sxs-lookup"><span data-stu-id="839f9-169">BusinessVoice</span></span>|
|<span data-ttu-id="839f9-170">VoiceRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="839f9-170">VoiceRoutingPolicy</span></span>|<span data-ttu-id="839f9-171">값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="839f9-171">Has a value</span></span>|<span data-ttu-id="839f9-172">값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="839f9-172">Has a value</span></span>|<span data-ttu-id="839f9-173">값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="839f9-173">Has a value</span></span>|<span data-ttu-id="839f9-174">해당 없음</span><span class="sxs-lookup"><span data-stu-id="839f9-174">N/A</span></span>|
|<span data-ttu-id="839f9-175">OnlineVoiceRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="839f9-175">OnlineVoiceRoutingPolicy</span></span>|<span data-ttu-id="839f9-176">$Null</span><span class="sxs-lookup"><span data-stu-id="839f9-176">$Null</span></span>|<span data-ttu-id="839f9-177">$Null</span><span class="sxs-lookup"><span data-stu-id="839f9-177">$Null</span></span>|<span data-ttu-id="839f9-178">$Null</span><span class="sxs-lookup"><span data-stu-id="839f9-178">$Null</span></span>|<span data-ttu-id="839f9-179">값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="839f9-179">Has a value</span></span>|
|<span data-ttu-id="839f9-180">TeamsUpgradePolicy<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="839f9-180">TeamsUpgradePolicy<sup>1</sup></span></span>|<span data-ttu-id="839f9-181">TeamsOnly, SfBOnly</span><span class="sxs-lookup"><span data-stu-id="839f9-181">TeamsOnly, SfBOnly</span></span>|<span data-ttu-id="839f9-182">$Null</span><span class="sxs-lookup"><span data-stu-id="839f9-182">$Null</span></span>|<span data-ttu-id="839f9-183">$Null</span><span class="sxs-lookup"><span data-stu-id="839f9-183">$Null</span></span>|<span data-ttu-id="839f9-184">TeamsOnly</span><span class="sxs-lookup"><span data-stu-id="839f9-184">TeamsOnly</span></span>|
|<span data-ttu-id="839f9-185">TeamsCallingPolicy</span><span class="sxs-lookup"><span data-stu-id="839f9-185">TeamsCallingPolicy</span></span></br><span data-ttu-id="839f9-186">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="839f9-186">AllowPrivateCalling</span></span>|<span data-ttu-id="839f9-187">True</span><span class="sxs-lookup"><span data-stu-id="839f9-187">True</span></span>|<span data-ttu-id="839f9-188">해당 없음</span><span class="sxs-lookup"><span data-stu-id="839f9-188">N/A</span></span>|<span data-ttu-id="839f9-189">해당 없음</span><span class="sxs-lookup"><span data-stu-id="839f9-189">N/A</span></span>|<span data-ttu-id="839f9-190">True</span><span class="sxs-lookup"><span data-stu-id="839f9-190">True</span></span>|
|<span data-ttu-id="839f9-191">TeamsCallingPolicy</span><span class="sxs-lookup"><span data-stu-id="839f9-191">TeamsCallingPolicy</span></span></br><span data-ttu-id="839f9-192">AllowGroupCalling</span><span class="sxs-lookup"><span data-stu-id="839f9-192">AllowGroupCalling</span></span>|<span data-ttu-id="839f9-193">True</span><span class="sxs-lookup"><span data-stu-id="839f9-193">True</span></span>|<span data-ttu-id="839f9-194">해당 없음</span><span class="sxs-lookup"><span data-stu-id="839f9-194">N/A</span></span>|<span data-ttu-id="839f9-195">해당 없음</span><span class="sxs-lookup"><span data-stu-id="839f9-195">N/A</span></span>|<span data-ttu-id="839f9-196">True</span><span class="sxs-lookup"><span data-stu-id="839f9-196">True</span></span>|
||||||

<span data-ttu-id="839f9-197"><sup>1</sup> TeamsUpgradePolicy의 올바른 모드 선택은 시나리오에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="839f9-197"><sup>1</sup> Choosing the right mode of the TeamsUpgradePolicy depends on the scenario.</span></span> <span data-ttu-id="839f9-198">비즈니스용 Skype와 함께 Teams를 사용하는 조직에 대한 마이그레이션 및 상호 연동성 지침의 다양한 모드에서 음성 환경에 [대해 읽어 주세요.](migration-interop-guidance-for-teams-with-skype.md)</span><span class="sxs-lookup"><span data-stu-id="839f9-198">Please read about the voice experience in different modes in [Migration and interoperability Guidance for organizations using Teams together with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span>

<span data-ttu-id="839f9-199">이러한 노력의 일환으로 Microsoft는 최근 공존 모드를 기반으로 하는 새 관리 모델을 반영하기 위해 "Microsoft Teams 관리 센터"(모던 포털라고도도 하는)를 업데이트했습니다.</span><span class="sxs-lookup"><span data-stu-id="839f9-199">As part of this effort, Microsoft recently updated the “Microsoft Teams admin center” (also known as Modern Portal) to reflect the new management model based on coexistence modes.</span></span> <span data-ttu-id="839f9-200">현대 포털에서 TeamsUpgradePolicy를 구성하면 TeamsInteropPolicy도 자동으로 일관된 값으로 설정되어 TeamsInteropPolicy가 사용자 인터페이스에 더 이상 노출되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="839f9-200">In Modern Portal, configuring TeamsUpgradePolicy will now automatically also set TeamsInteropPolicy to consistent value, so TeamsInteropPolicy is no longer exposed in the user interface.</span></span> <span data-ttu-id="839f9-201">그러나 PowerShell을 사용하는 관리자는 적절한 라우팅을 보장하기 위해 TeamsUpgradePolicy와 TeamsInteropPolicy를 함께 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="839f9-201">However, admins using PowerShell must still set both TeamsUpgradePolicy and TeamsInteropPolicy together to ensure proper routing.</span></span> <span data-ttu-id="839f9-202">TeamsUpgradePolicy로 전환이 완료되면 TeamsInteropPolicy도 더 이상 설정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="839f9-202">After the transition to TeamsUpgradePolicy is complete, it will no longer be necessary to also set TeamsInteropPolicy.</span></span>

<span data-ttu-id="839f9-203">자세한 내용은 비즈니스용 Skype와 함께 Teams를 사용하는 조직에 대한 마이그레이션 및 상호 연동성 지침을 [참조하세요.](migration-interop-guidance-for-teams-with-skype.md)</span><span class="sxs-lookup"><span data-stu-id="839f9-203">For more information, please refer to [Migration and interoperability Guidance for organizations using Teams together with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span>

## <a name="migrating-from-calling-plans"></a><span data-ttu-id="839f9-204">통화 계획에서 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="839f9-204">Migrating from Calling Plans</span></span>

<span data-ttu-id="839f9-205">통화 계획에서 마이그레이션하는 데 대한 자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="839f9-205">For more information about migrating from Calling Plans, see:</span></span>

- [<span data-ttu-id="839f9-206">통화 플랜 설정</span><span class="sxs-lookup"><span data-stu-id="839f9-206">Set up Calling Plans</span></span>](/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)
- [<span data-ttu-id="839f9-207">Set-CsOnlineVoice 사용자</span><span class="sxs-lookup"><span data-stu-id="839f9-207">Set-CsOnlineVoice User</span></span>](/powershell/module/skype/Set-CsOnlineVoiceUser?view=skype-ps)
- [<span data-ttu-id="839f9-208">Get-CsOnlineLisLocation</span><span class="sxs-lookup"><span data-stu-id="839f9-208">Get-CsOnlineLisLocation</span></span>](/powershell/module/skype/get-csonlinelislocation?view=skype-ps)  
 
 
<span data-ttu-id="839f9-209">다음과 같이 이전에 구성된 라이선스 계획 정보를 제거하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="839f9-209">It is recommended that you remove previously configured licensing plan information as follows:</span></span>
 
```powershell
$companyname = “contoso” 
$lic1 = $companyname + “:MCOPSTN1” 
$lic2 = $companyname + “:MCOPSTN2” 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic1 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic2 
```
## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a><span data-ttu-id="839f9-210">비즈니스용 Skype 서버에서온-프레미스 PSTN 연결로 Office 365 Phone System에서 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="839f9-210">Migrating from Office 365 Phone System with on-premises PSTN connectivity in Skype for Business Server</span></span>

<span data-ttu-id="839f9-211">비즈니스용 Skype Server의온-프레미스 PSTN 연결을 사용하여 Phone System에서 마이그레이션하는 자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="839f9-211">For more information about migrating from Phone System with on-premises PSTN connectivity in Skype for Business Server, see the following:</span></span>

- [<span data-ttu-id="839f9-212">계획</span><span class="sxs-lookup"><span data-stu-id="839f9-212">Planning</span></span>](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)
- [<span data-ttu-id="839f9-213">배포</span><span class="sxs-lookup"><span data-stu-id="839f9-213">Deploying</span></span>](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system) 

<span data-ttu-id="839f9-214">다음과 같이 이전에 구성된 음성 라우팅 정보를 제거하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="839f9-214">It is recommended that you remove previously configured voice routing information as follows:</span></span>

```PowerShell
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
```
> [!NOTE]
> <span data-ttu-id="839f9-215">전역 CsVoiceRoutingPolicy가 구성된 경우 이 전역 정책과 연결된 모든 PSTN 사용량을 제거하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="839f9-215">If a global CsVoiceRoutingPolicy is configured, it is recommended that you remove any PSTN usages associated with this global policy.</span></span> 

## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-via-cloud-connector-edition"></a><span data-ttu-id="839f9-216">Cloud Connector Edition을 통해온-프레미스 PSTN 연결로 Office 365 Phone System에서 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="839f9-216">Migrating from Office 365 Phone System with on-premises PSTN connectivity via Cloud Connector Edition</span></span> 

> [!Important]
> <span data-ttu-id="839f9-217">Cloud Connector Edition은 비즈니스용 Skype Online과 함께 2021년 7월 31일을 사용 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="839f9-217">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="839f9-218">조직이 Teams로 업그레이드된 후 직접 라우팅을 사용하여 프레미스 전화 통신 네트워크를 Teams에 연결하는 [방법에 대해 자세히 알아보습니다.](direct-routing-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="839f9-218">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](direct-routing-landing-page.md).</span></span>

<span data-ttu-id="839f9-219">Cloud Connector를 통해온-프레미스 PSTN 연결을 사용하여 Phone System에서 마이그레이션하는 데 대한 자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="839f9-219">For more information about migrating from Phone System with on-premises PSTN connectivity via Cloud Connector, see the following:</span></span>

- [<span data-ttu-id="839f9-220">계획</span><span class="sxs-lookup"><span data-stu-id="839f9-220">Planning</span></span>](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition)  
- [<span data-ttu-id="839f9-221">배포</span><span class="sxs-lookup"><span data-stu-id="839f9-221">Deploying</span></span>](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system)
- [<span data-ttu-id="839f9-222">사용자 구성</span><span class="sxs-lookup"><span data-stu-id="839f9-222">User configuration</span></span>](/powershell/module/skype/set-csuserpstnsettings?view=skype-ps) 

<span data-ttu-id="839f9-223">다음과 같이 이전에 구성된 음성 라우팅 정보를 제거하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="839f9-223">It is recommended that you remove previously configured voice routing information as follows:</span></span>
 
```PowerShell
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
Set-CsUserPstnSettings -Identity <UPN> -AllowInternationalCalls $false -HybridPSTNSite $null 
```


## <a name="related-links"></a><span data-ttu-id="839f9-224">관련 링크</span><span class="sxs-lookup"><span data-stu-id="839f9-224">Related links</span></span>

[<span data-ttu-id="839f9-225">비즈니스용 Skype와 함께 Teams를 사용하는 조직에 대한 마이그레이션 및 상호 연동성 지침</span><span class="sxs-lookup"><span data-stu-id="839f9-225">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md)

[<span data-ttu-id="839f9-226">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="839f9-226">Grant-CsTeamsUpgradePolicy</span></span>](/powershell/module/skype/grant-csteamsupgradepolicy)

[<span data-ttu-id="839f9-227">Get-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="839f9-227">Get-CsTeamsUpgradePolicy</span></span>](/powershell/module/skype/Get-CsTeamsUpgradePolicy)

[<span data-ttu-id="839f9-228">New-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="839f9-228">New-CsTeamsUpgradePolicy</span></span>](/powershell/module/skype/New-CsTeamsUpgradePolicy)

[<span data-ttu-id="839f9-229">Remove-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="839f9-229">Remove-CsTeamsUpgradePolicy</span></span>](/powershell/module/skype/Remove-CsTeamsUpgradePolicy)

[<span data-ttu-id="839f9-230">Set-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="839f9-230">Set-CsTeamsUpgradePolicy</span></span>](/powershell/module/skype/Set-CsTeamsUpgradePolicy)

[<span data-ttu-id="839f9-231">Get-CsTeamsUpgradeConfiguration</span><span class="sxs-lookup"><span data-stu-id="839f9-231">Get-CsTeamsUpgradeConfiguration</span></span>](/powershell/module/skype/Get-CsTeamsUpgradeConfiguration)

[<span data-ttu-id="839f9-232">Set-CsTeamsUpgradeConfiguration</span><span class="sxs-lookup"><span data-stu-id="839f9-232">Set-CsTeamsUpgradeConfiguration</span></span>](/powershell/module/skype/Set-CsTeamsUpgradeConfiguration)