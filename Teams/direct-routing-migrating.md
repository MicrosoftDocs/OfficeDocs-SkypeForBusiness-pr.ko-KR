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
description: 비즈니스용 Skype Online 및 팀 구성 관점에서 직접 라우팅하기 위해 마이그레이션하는 데 필요한 사항에 대해 알아보세요.
ms.openlocfilehash: 11bf4ffe7e5e0f1c2fb177531c2eba36d081bf47
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359424"
---
# <a name="migrate-to-direct-routing"></a><span data-ttu-id="dbcbd-103">직접 라우팅으로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="dbcbd-103">Migrate to Direct Routing</span></span>

<span data-ttu-id="dbcbd-104">이 문서에서는 비즈니스용 Skype Online 및 Microsoft 팀 구성 관점에서 직접 라우팅하기 위해 마이그레이션하는 데 필요한 사항에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbcbd-104">This article describes what is needed to migrate to Direct Routing from a Skype for Business Online and Microsoft Teams configuration perspective.</span></span> <span data-ttu-id="dbcbd-105">이 문서에서는 다음에서 마이그레이션하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbcbd-105">This article covers migrating from the following:</span></span> 
 
- <span data-ttu-id="dbcbd-106">통화 요금제가 포함 되어 있는 전화 시스템 (팀 및 비즈니스용 Skype Online)</span><span class="sxs-lookup"><span data-stu-id="dbcbd-106">Phone System with Calling Plans (for Teams and Skype for Business Online)</span></span> 
- <span data-ttu-id="dbcbd-107">비즈니스용 skype Online에서 온-프레미스 PSTN 연결을 사용 하는 전화 시스템 (비즈니스용 Skype Online)</span><span class="sxs-lookup"><span data-stu-id="dbcbd-107">Phone System with on-premises PSTN Connectivity in Skype for Business Server (for Skype for Business Online)</span></span>  
- <span data-ttu-id="dbcbd-108">클라우드 커넥터 에디션을 사용 하 여 온-프레미스 PSTN 연결을 사용한 전화 시스템 (비즈니스용 Skype Online)</span><span class="sxs-lookup"><span data-stu-id="dbcbd-108">Phone System with on-premises PSTN Connectivity by using the Cloud Connector Edition (for Skype for Business Online)</span></span>


<span data-ttu-id="dbcbd-109">이러한 구성 단계 외에도 SBC (세션 경계 컨트롤러)에서 호출을 새 경로로 라우팅하는 데 구성이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbcbd-109">In addition to these configuration steps, configuration is also required on the Session Border Controller (SBC) to route the calls to the new route.</span></span> <span data-ttu-id="dbcbd-110">이 문서에서는 다루지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dbcbd-110">That is outside the scope of this document.</span></span> <span data-ttu-id="dbcbd-111">자세한 내용은 SBC 공급 업체 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dbcbd-111">For more information, see your SBC vendor documentation.</span></span>  

## <a name="user-provisioning-end-state-for-various-pstn-connectivity-options"></a><span data-ttu-id="dbcbd-112">다양 한 PSTN 연결 옵션의 사용자 프로비저닝 종료 상태</span><span class="sxs-lookup"><span data-stu-id="dbcbd-112">User provisioning end-state for various PSTN connectivity options</span></span> 

<span data-ttu-id="dbcbd-113">다음 표에는 전화 시스템에서 선택한 PSTN 연결 옵션에 대해 프로 비전 된 사용자의 종료 상태가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbcbd-113">The following table shows the end-state for a user provisioned for the selected PSTN connectivity options with Phone System.</span></span> <span data-ttu-id="dbcbd-114">음성과 관련 된 특성만 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbcbd-114">Only attributes relevant for voice are shown.</span></span>

|<span data-ttu-id="dbcbd-115">사용자 개체 특성</span><span class="sxs-lookup"><span data-stu-id="dbcbd-115">User object attributes</span></span> |<span data-ttu-id="dbcbd-116">통화 요금제가 포함 되어 있는 전화 시스템</span><span class="sxs-lookup"><span data-stu-id="dbcbd-116">Phone System with Calling Plans</span></span>|<span data-ttu-id="dbcbd-117">비즈니스용 Skype 서버를 통해 온-프레미스 PSTN 연결을 사용 하는 전화 시스템</span><span class="sxs-lookup"><span data-stu-id="dbcbd-117">Phone System with on-premises PSTN connectivity via Skype for Business Server</span></span>|<span data-ttu-id="dbcbd-118">클라우드 커넥터를 통해 온-프레미스 PSTN 연결을 사용 하는 전화 시스템</span><span class="sxs-lookup"><span data-stu-id="dbcbd-118">Phone System with on-premises PSTN connectivity via Cloud Connector</span></span>|<span data-ttu-id="dbcbd-119">직접 라우팅을 통한 온-프레미스 PSTN 연결을 사용 하는 전화 시스템</span><span class="sxs-lookup"><span data-stu-id="dbcbd-119">Phone System with on-premises PSTN connectivity via Direct Routing</span></span>|
|---|---|---|---|---|
|<span data-ttu-id="dbcbd-120">클라이언트</span><span class="sxs-lookup"><span data-stu-id="dbcbd-120">Client</span></span>|<span data-ttu-id="dbcbd-121">비즈니스용 Skype 또는 팀</span><span class="sxs-lookup"><span data-stu-id="dbcbd-121">Skype for Business or Teams</span></span> |<span data-ttu-id="dbcbd-122">비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="dbcbd-122">Skype for Business</span></span> |<span data-ttu-id="dbcbd-123">비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="dbcbd-123">Skype for Business</span></span> |<span data-ttu-id="dbcbd-124">Teams</span><span class="sxs-lookup"><span data-stu-id="dbcbd-124">Teams</span></span>|
|<span data-ttu-id="dbcbd-125">라이센스</span><span class="sxs-lookup"><span data-stu-id="dbcbd-125">Licenses</span></span>|<span data-ttu-id="dbcbd-126">Skype Business Online</span><span class="sxs-lookup"><span data-stu-id="dbcbd-126">Skype Business Online</span></span></br><span data-ttu-id="dbcbd-127">계획 2</span><span class="sxs-lookup"><span data-stu-id="dbcbd-127">Plan 2</span></span></br></br><span data-ttu-id="dbcbd-128">MCOProfessional 또는 MCOPROFESSIONAL)</span><span class="sxs-lookup"><span data-stu-id="dbcbd-128">MCOProfessional or MCOSTANDARD)</span></span></br></br></br><span data-ttu-id="dbcbd-129">휴대폰 시스템 (MCOEV)</span><span class="sxs-lookup"><span data-stu-id="dbcbd-129">Phone System (MCOEV)</span></span></br></br></br><span data-ttu-id="dbcbd-130">통화 플랜</span><span class="sxs-lookup"><span data-stu-id="dbcbd-130">Calling Plans</span></span></br><span data-ttu-id="dbcbd-131">Teams</span><span class="sxs-lookup"><span data-stu-id="dbcbd-131">Teams</span></span>|<span data-ttu-id="dbcbd-132">Skype Business Online 계획 2 (MCOProfessional 또는 MCOPROFESSIONAL)</span><span class="sxs-lookup"><span data-stu-id="dbcbd-132">Skype Business Online Plan 2 (MCOProfessional or MCOSTANDARD)</span></span></br></br></br><span data-ttu-id="dbcbd-133">휴대폰 시스템 (MCOEV)</span><span class="sxs-lookup"><span data-stu-id="dbcbd-133">Phone System (MCOEV)</span></span>|<span data-ttu-id="dbcbd-134">Skype Business Online 계획 2 (MCOProfessional 또는 MCOPROFESSIONAL)</span><span class="sxs-lookup"><span data-stu-id="dbcbd-134">Skype Business Online Plan 2 (MCOProfessional or MCOSTANDARD)</span></span></br></br></br><span data-ttu-id="dbcbd-135">휴대폰 시스템 (MCOEV)</span><span class="sxs-lookup"><span data-stu-id="dbcbd-135">Phone System (MCOEV)</span></span>|<span data-ttu-id="dbcbd-136">Skype Business Online 요금제 2 (MCOProfessional 또는 MCOPROFESSIONAL</span><span class="sxs-lookup"><span data-stu-id="dbcbd-136">Skype Business Online Plan 2 (MCOProfessional or MCOSTANDARD</span></span></br></br></br><span data-ttu-id="dbcbd-137">휴대폰 시스템 (MCOEV)</span><span class="sxs-lookup"><span data-stu-id="dbcbd-137">Phone System (MCOEV)</span></span></br></br><span data-ttu-id="dbcbd-138">Teams</span><span class="sxs-lookup"><span data-stu-id="dbcbd-138">Teams</span></span>|
<span data-ttu-id="dbcbd-139">OnPremLineURI</span><span class="sxs-lookup"><span data-stu-id="dbcbd-139">OnPremLineURI</span></span> |<span data-ttu-id="dbcbd-140">해당 없음</span><span class="sxs-lookup"><span data-stu-id="dbcbd-140">N/A</span></span>|<span data-ttu-id="dbcbd-141">전화 번호는 온-프레미스 광고와 동기화 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbcbd-141">The phone number  must be synced from the on-premises AD.</span></span> |<span data-ttu-id="dbcbd-142">전화 번호는 온-프레미스 Active Directory 또는 Azure Active Directory에서 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbcbd-142">The phone number can be managed either in on-premises Active Directory or in Azure Active Directory.</span></span>|<span data-ttu-id="dbcbd-143">전화 번호는 온-프레미스 Active Directory 또는 Azure Active Directory에서 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbcbd-143">The phone number can be managed either in on-premises Active Directory or in Azure Active Directory.</span></span> <span data-ttu-id="dbcbd-144">그러나 조직에 비즈니스용 Skype가 있는 경우에는 온-프레미스 Active Directory에서 번호를 동기화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbcbd-144">However, if the organization has on-premises Skype for Business, the number must be synced from the on-premises Active Directory.</span></span>|
|<span data-ttu-id="dbcbd-145">LineURI</span><span class="sxs-lookup"><span data-stu-id="dbcbd-145">LineURI</span></span>|<span data-ttu-id="dbcbd-146">PSTN 통화 전화 번호</span><span class="sxs-lookup"><span data-stu-id="dbcbd-146">PSTN Calling phone number</span></span>|<span data-ttu-id="dbcbd-147">OnPremLineURI 매개 변수에서 자동으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbcbd-147">Set automatically from the OnPremLineURI parameter</span></span>|<span data-ttu-id="dbcbd-148">OnPremLineURI 매개 변수에서 자동으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbcbd-148">Set automatically from the OnPremLineURI parameter</span></span>|<span data-ttu-id="dbcbd-149">OnPremLineURI 매개 변수에서 자동으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbcbd-149">Set automatically from the OnPremLineURI parameter</span></span>|
|<span data-ttu-id="dbcbd-150">EnterpriseVoiceEnabled</span><span class="sxs-lookup"><span data-stu-id="dbcbd-150">EnterpriseVoiceEnabled</span></span>|<span data-ttu-id="dbcbd-151">False</span><span class="sxs-lookup"><span data-stu-id="dbcbd-151">True</span></span>|<span data-ttu-id="dbcbd-152">False</span><span class="sxs-lookup"><span data-stu-id="dbcbd-152">True</span></span>|<span data-ttu-id="dbcbd-153">False</span><span class="sxs-lookup"><span data-stu-id="dbcbd-153">True</span></span>|<span data-ttu-id="dbcbd-154">False</span><span class="sxs-lookup"><span data-stu-id="dbcbd-154">True</span></span>|
|<span data-ttu-id="dbcbd-155">HostedVoiceMail</span><span class="sxs-lookup"><span data-stu-id="dbcbd-155">HostedVoiceMail</span></span> |<span data-ttu-id="dbcbd-156">False</span><span class="sxs-lookup"><span data-stu-id="dbcbd-156">True</span></span>|<span data-ttu-id="dbcbd-157">False</span><span class="sxs-lookup"><span data-stu-id="dbcbd-157">True</span></span>|<span data-ttu-id="dbcbd-158">False</span><span class="sxs-lookup"><span data-stu-id="dbcbd-158">True</span></span>|<span data-ttu-id="dbcbd-159">False</span><span class="sxs-lookup"><span data-stu-id="dbcbd-159">True</span></span>|
|<span data-ttu-id="dbcbd-160">VoicePolicy</span><span class="sxs-lookup"><span data-stu-id="dbcbd-160">VoicePolicy</span></span>|<span data-ttu-id="dbcbd-161">BusinessVoice</span><span class="sxs-lookup"><span data-stu-id="dbcbd-161">BusinessVoice</span></span>|<span data-ttu-id="dbcbd-162">HybridVoice</span><span class="sxs-lookup"><span data-stu-id="dbcbd-162">HybridVoice</span></span>|<span data-ttu-id="dbcbd-163">HybridVoice</span><span class="sxs-lookup"><span data-stu-id="dbcbd-163">HybridVoice</span></span>|<span data-ttu-id="dbcbd-164">HybridVoice</span><span class="sxs-lookup"><span data-stu-id="dbcbd-164">HybridVoice</span></span>|
|<span data-ttu-id="dbcbd-165">HostedVoiceMailPolicy</span><span class="sxs-lookup"><span data-stu-id="dbcbd-165">HostedVoiceMailPolicy</span></span> |<span data-ttu-id="dbcbd-166">BusinessVoice</span><span class="sxs-lookup"><span data-stu-id="dbcbd-166">BusinessVoice</span></span>|<span data-ttu-id="dbcbd-167">BusinessVoice</span><span class="sxs-lookup"><span data-stu-id="dbcbd-167">BusinessVoice</span></span>|<span data-ttu-id="dbcbd-168">BusinessVoice</span><span class="sxs-lookup"><span data-stu-id="dbcbd-168">BusinessVoice</span></span>|<span data-ttu-id="dbcbd-169">BusinessVoice</span><span class="sxs-lookup"><span data-stu-id="dbcbd-169">BusinessVoice</span></span>|
|<span data-ttu-id="dbcbd-170">VoiceRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="dbcbd-170">VoiceRoutingPolicy</span></span>|<span data-ttu-id="dbcbd-171">값이 있음</span><span class="sxs-lookup"><span data-stu-id="dbcbd-171">Has a value</span></span>|<span data-ttu-id="dbcbd-172">값이 있음</span><span class="sxs-lookup"><span data-stu-id="dbcbd-172">Has a value</span></span>|<span data-ttu-id="dbcbd-173">값이 있음</span><span class="sxs-lookup"><span data-stu-id="dbcbd-173">Has a value</span></span>|<span data-ttu-id="dbcbd-174">해당 없음</span><span class="sxs-lookup"><span data-stu-id="dbcbd-174">N/A</span></span>|
|<span data-ttu-id="dbcbd-175">OnlineVoiceRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="dbcbd-175">OnlineVoiceRoutingPolicy</span></span>|<span data-ttu-id="dbcbd-176">$Null</span><span class="sxs-lookup"><span data-stu-id="dbcbd-176">$Null</span></span>|<span data-ttu-id="dbcbd-177">$Null</span><span class="sxs-lookup"><span data-stu-id="dbcbd-177">$Null</span></span>|<span data-ttu-id="dbcbd-178">$Null</span><span class="sxs-lookup"><span data-stu-id="dbcbd-178">$Null</span></span>|<span data-ttu-id="dbcbd-179">값이 있음</span><span class="sxs-lookup"><span data-stu-id="dbcbd-179">Has a value</span></span>|
|<span data-ttu-id="dbcbd-180">TeamsUpgradePolicy<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="dbcbd-180">TeamsUpgradePolicy<sup>1</sup></span></span>|<span data-ttu-id="dbcbd-181">TeamsOnly, SfBOnly</span><span class="sxs-lookup"><span data-stu-id="dbcbd-181">TeamsOnly, SfBOnly</span></span>|<span data-ttu-id="dbcbd-182">$Null</span><span class="sxs-lookup"><span data-stu-id="dbcbd-182">$Null</span></span>|<span data-ttu-id="dbcbd-183">$Null</span><span class="sxs-lookup"><span data-stu-id="dbcbd-183">$Null</span></span>|<span data-ttu-id="dbcbd-184">TeamsOnly</span><span class="sxs-lookup"><span data-stu-id="dbcbd-184">TeamsOnly</span></span>|
|<span data-ttu-id="dbcbd-185">TeamsCallingPolicy</span><span class="sxs-lookup"><span data-stu-id="dbcbd-185">TeamsCallingPolicy</span></span></br><span data-ttu-id="dbcbd-186">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="dbcbd-186">AllowPrivateCalling</span></span>|<span data-ttu-id="dbcbd-187">False</span><span class="sxs-lookup"><span data-stu-id="dbcbd-187">True</span></span>|<span data-ttu-id="dbcbd-188">해당 없음</span><span class="sxs-lookup"><span data-stu-id="dbcbd-188">N/A</span></span>|<span data-ttu-id="dbcbd-189">해당 없음</span><span class="sxs-lookup"><span data-stu-id="dbcbd-189">N/A</span></span>|<span data-ttu-id="dbcbd-190">False</span><span class="sxs-lookup"><span data-stu-id="dbcbd-190">True</span></span>|
|<span data-ttu-id="dbcbd-191">TeamsCallingPolicy</span><span class="sxs-lookup"><span data-stu-id="dbcbd-191">TeamsCallingPolicy</span></span></br><span data-ttu-id="dbcbd-192">AllowGroupCalling</span><span class="sxs-lookup"><span data-stu-id="dbcbd-192">AllowGroupCalling</span></span>|<span data-ttu-id="dbcbd-193">False</span><span class="sxs-lookup"><span data-stu-id="dbcbd-193">True</span></span>|<span data-ttu-id="dbcbd-194">해당 없음</span><span class="sxs-lookup"><span data-stu-id="dbcbd-194">N/A</span></span>|<span data-ttu-id="dbcbd-195">해당 없음</span><span class="sxs-lookup"><span data-stu-id="dbcbd-195">N/A</span></span>|<span data-ttu-id="dbcbd-196">False</span><span class="sxs-lookup"><span data-stu-id="dbcbd-196">True</span></span>|
||||||

<span data-ttu-id="dbcbd-197"><sup>1</sup> TeamsUpgradePolicy의 오른쪽 모드 선택 시나리오에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="dbcbd-197"><sup>1</sup> Choosing the right mode of the TeamsUpgradePolicy depends on the scenario.</span></span> <span data-ttu-id="dbcbd-198">[비즈니스용 Skype와 함께 팀을 사용 하는 조직에 대 한 마이그레이션 및 상호 운용성 지침](migration-interop-guidance-for-teams-with-skype.md)에서 서로 다른 모드의 음성 환경에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="dbcbd-198">Please read about the voice experience in different modes in [Migration and interoperability Guidance for organizations using Teams together with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span>

<span data-ttu-id="dbcbd-199">이 작업의 일환으로 Microsoft는 최근에 "Microsoft 팀 관리 센터" (최신 포털이 라고도 함)를 업데이트 하 여 공존 모드에 따라 새로운 관리 모델을 반영 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbcbd-199">As part of this effort, Microsoft recently updated the “Microsoft Teams admin center” (also known as Modern Portal) to reflect the new management model based on coexistence modes.</span></span> <span data-ttu-id="dbcbd-200">최신 포털에서 이제 TeamsUpgradePolicy를 구성 하면 TeamsInteropPolicy 일관성 있는 값으로 설정 되므로 TeamsInteropPolicy는 더 이상 사용자 인터페이스에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dbcbd-200">In Modern Portal, configuring TeamsUpgradePolicy will now automatically also set TeamsInteropPolicy to consistent value, so TeamsInteropPolicy is no longer exposed in the user interface.</span></span> <span data-ttu-id="dbcbd-201">그러나 PowerShell을 사용 하는 관리자는 적절 한 라우팅이 가능 하도록 TeamsUpgradePolicy 및 TeamsInteropPolicy를 함께 함께 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbcbd-201">However, admins using PowerShell must still set both TeamsUpgradePolicy and TeamsInteropPolicy together to ensure proper routing.</span></span> <span data-ttu-id="dbcbd-202">TeamsUpgradePolicy에 대 한 전환이 완료 된 후에는 TeamsInteropPolicy도 설정 하는 데 더 이상 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dbcbd-202">After the transition to TeamsUpgradePolicy is complete, it will no longer be necessary to also set TeamsInteropPolicy.</span></span>

<span data-ttu-id="dbcbd-203">자세한 내용은 [비즈니스용 Skype로 함께 팀을 사용 하는 조직의 마이그레이션 및 상호 운용성 지침](migration-interop-guidance-for-teams-with-skype.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dbcbd-203">For more information, please refer to [Migration and interoperability Guidance for organizations using Teams together with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span>

## <a name="migrating-from-calling-plans"></a><span data-ttu-id="dbcbd-204">통화 요금제에서 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="dbcbd-204">Migrating from Calling Plans</span></span>

<span data-ttu-id="dbcbd-205">통화 계획에서 마이그레이션하는 방법에 대 한 자세한 내용은 다음을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dbcbd-205">For more information about migrating from Calling Plans, see:</span></span>

- [<span data-ttu-id="dbcbd-206">통화 플랜 설정</span><span class="sxs-lookup"><span data-stu-id="dbcbd-206">Set up Calling Plans</span></span>](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)
- [<span data-ttu-id="dbcbd-207">Set-CsOnlineVoice 사용자</span><span class="sxs-lookup"><span data-stu-id="dbcbd-207">Set-CsOnlineVoice User</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsOnlineVoiceUser?view=skype-ps)
- [<span data-ttu-id="dbcbd-208">Get-CsOnlineLisLocation</span><span class="sxs-lookup"><span data-stu-id="dbcbd-208">Get-CsOnlineLisLocation</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csonlinelislocation?view=skype-ps)  
 
 
<span data-ttu-id="dbcbd-209">다음과 같이 이전에 구성한 라이선스 계획 정보를 제거 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="dbcbd-209">It is recommended that you remove previously configured licensing plan information as follows:</span></span>
 
```powershell
$companyname = “contoso” 
$lic1 = $companyname + “:MCOPSTN1” 
$lic2 = $companyname + “:MCOPSTN2” 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic1 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic2 
```
## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a><span data-ttu-id="dbcbd-210">비즈니스용 Skype 서버에서 온-프레미스 PSTN 연결을 사용 하 여 Office 365 전화 시스템 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="dbcbd-210">Migrating from Office 365 Phone System with on-premises PSTN connectivity in Skype for Business Server</span></span>

<span data-ttu-id="dbcbd-211">비즈니스용 Skype 서버에서 온-프레미스 PSTN 연결을 사용 하 여 전화 시스템을 마이그레이션하는 방법에 대 한 자세한 내용은 다음을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dbcbd-211">For more information about migrating from Phone System with on-premises PSTN connectivity in Skype for Business Server, see the following:</span></span>

- [<span data-ttu-id="dbcbd-212">계획</span><span class="sxs-lookup"><span data-stu-id="dbcbd-212">Planning</span></span>](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)
- [<span data-ttu-id="dbcbd-213">구축</span><span class="sxs-lookup"><span data-stu-id="dbcbd-213">Deploying</span></span>](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system) 

<span data-ttu-id="dbcbd-214">다음과 같이 이전에 구성한 음성 라우팅 정보를 제거 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="dbcbd-214">It is recommended that you remove previously configured voice routing information as follows:</span></span>

```PowerShell
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
```
> [!NOTE]
> <span data-ttu-id="dbcbd-215">전역 CsVoiceRoutingPolicy 구성 된 경우이 글로벌 정책과 연결 된 PSTN 사용량을 제거 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="dbcbd-215">If a global CsVoiceRoutingPolicy is configured, it is recommended that you remove any PSTN usages associated with this global policy.</span></span> 

## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-via-cloud-connector-edition"></a><span data-ttu-id="dbcbd-216">클라우드 커넥터 에디션을 통해 온-프레미스 PSTN 연결을 사용 하 여 Office 365 전화 시스템에서 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="dbcbd-216">Migrating from Office 365 Phone System with on-premises PSTN connectivity via Cloud Connector Edition</span></span> 

> [!Important]
> <span data-ttu-id="dbcbd-217">클라우드 커넥터 버전이 비즈니스용 Skype Online과 함께 2021 년 7 월 31 일에 사용 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbcbd-217">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="dbcbd-218">조직이 팀으로 업그레이드 되 면 [직접 라우팅을](direct-routing-landing-page.md)사용 하 여 팀에 온-프레미스 전화 접속 네트워크를 연결 하는 방법을 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="dbcbd-218">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](direct-routing-landing-page.md).</span></span>

<span data-ttu-id="dbcbd-219">클라우드 커넥터를 통해 온-프레미스 PSTN 연결을 사용 하 여 전화 시스템을 마이그레이션하는 방법에 대 한 자세한 내용은 다음을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dbcbd-219">For more information about migrating from Phone System with on-premises PSTN connectivity via Cloud Connector, see the following:</span></span>

- [<span data-ttu-id="dbcbd-220">계획</span><span class="sxs-lookup"><span data-stu-id="dbcbd-220">Planning</span></span>](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition)  
- [<span data-ttu-id="dbcbd-221">구축</span><span class="sxs-lookup"><span data-stu-id="dbcbd-221">Deploying</span></span>](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system)
- [<span data-ttu-id="dbcbd-222">사용자 구성</span><span class="sxs-lookup"><span data-stu-id="dbcbd-222">User configuration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csuserpstnsettings?view=skype-ps) 

<span data-ttu-id="dbcbd-223">다음과 같이 이전에 구성한 음성 라우팅 정보를 제거 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="dbcbd-223">It is recommended that you remove previously configured voice routing information as follows:</span></span>
 
```PowerShell
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
Set-CsUserPstnSettings -Identity <UPN> -AllowInternationalCalls $false -HybridPSTNSite $null 
```


## <a name="related-links"></a><span data-ttu-id="dbcbd-224">관련 링크</span><span class="sxs-lookup"><span data-stu-id="dbcbd-224">Related links</span></span>

[<span data-ttu-id="dbcbd-225">비즈니스용 Skype로 팀을 함께 사용 하는 조직에 대 한 마이그레이션 및 상호 운용성 지침</span><span class="sxs-lookup"><span data-stu-id="dbcbd-225">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md)

[<span data-ttu-id="dbcbd-226">부여-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="dbcbd-226">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy)

[<span data-ttu-id="dbcbd-227">Get-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="dbcbd-227">Get-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsTeamsUpgradePolicy)

[<span data-ttu-id="dbcbd-228">새로운 CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="dbcbd-228">New-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsUpgradePolicy)

[<span data-ttu-id="dbcbd-229">제거-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="dbcbd-229">Remove-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsTeamsUpgradePolicy)

[<span data-ttu-id="dbcbd-230">Set-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="dbcbd-230">Set-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsUpgradePolicy)

[<span data-ttu-id="dbcbd-231">Get-CsTeamsUpgradeConfiguration</span><span class="sxs-lookup"><span data-stu-id="dbcbd-231">Get-CsTeamsUpgradeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsTeamsUpgradeConfiguration)

[<span data-ttu-id="dbcbd-232">Set-CsTeamsUpgradeConfiguration</span><span class="sxs-lookup"><span data-stu-id="dbcbd-232">Set-CsTeamsUpgradeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsUpgradeConfiguration)

