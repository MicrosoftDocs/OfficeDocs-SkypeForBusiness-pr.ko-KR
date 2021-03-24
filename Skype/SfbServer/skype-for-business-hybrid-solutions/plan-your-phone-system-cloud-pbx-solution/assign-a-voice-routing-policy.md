---
title: 음성 라우팅 정책 할당
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: c7f78f23-b74f-402f-bedb-4cc308718f5b
description: '요약: 이 항목을 통해 전화 시스템을 사용하여 사용자에 대해 음성 정책을 할당하는 방법을 배울 수 있습니다.'
ms.openlocfilehash: 43e2b560cc0886bacd6faaec6c113ee1f237eff7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092966"
---
# <a name="assign-a-voice-routing-policy"></a><span data-ttu-id="695c8-103">음성 라우팅 정책 할당</span><span class="sxs-lookup"><span data-stu-id="695c8-103">Assign a Voice Routing Policy</span></span>
 
> [!Important]
> <span data-ttu-id="695c8-104">비즈니스용 Skype Online은 2021년 7월 31에 서비스가 더 이상 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="695c8-104">Skype for Business Online will be retired on July 31, 2021 after which the service will no longer be accessible.</span></span>  <span data-ttu-id="695c8-105">또한 비즈니스용 Skype 서버 또는 클라우드 커넥터 버전과 비즈니스용 Skype Online을 통해 지원되지 않는 모든 사내 환경 간의 PSTN 연결도 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="695c8-105">In addition, PSTN connectivity between your on-premises environment whether through Skype for Business Server or Cloud Connector Edition and Skype for Business Online will no longer be supported.</span></span>  <span data-ttu-id="695c8-106">직접 라우팅을 사용하여 프레미스 전화 통신 네트워크를 Teams에 연결하는 [방법을 학습합니다.](/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="695c8-106">Learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="695c8-107">**요약:** 이 항목을 통해 전화 시스템을 사용하여 사용자에 대해 음성 정책을 할당하는 방법에 대해 자세히 알아보고, PSTN 연결을 통해 음성 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="695c8-107">**Summary:** Read this topic to learn how to assign a voice policy for users using Phone System with on-premises PSTN connectivity.</span></span> 
  
<span data-ttu-id="695c8-108">사용자가 비즈니스용 Skype Online에 있는 경우 전화 시스템을 사용하여온-프레미스 PSTN 연결 시 두 개의 음성 정책이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="695c8-108">Once a user is on Skype for Business Online and using Phone System with on-premises PSTN connectivity, two voice policies will apply to them.</span></span> <span data-ttu-id="695c8-109">하나는 프레미스에서 할당할 사내 음성 라우팅 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="695c8-109">One is an on-premises voice routing policy that you will assign on premises.</span></span> <span data-ttu-id="695c8-110">이 정책은 전역 또는 사용자별일 수 있으며 사용자와 연결된 PSTN 사용 레코드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="695c8-110">This policy can be global or user-specific and defines what PSTN usage records are associated with the user.</span></span> <span data-ttu-id="695c8-111">이 항목에서는 이 정책을 할당하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="695c8-111">This topic explains how to assign this policy.</span></span>
  
<span data-ttu-id="695c8-112">다른 음성 정책은 사용자가 사용할 수 있는 통화 기능을 정의합니다. 이 음성 정책은 Microsoft에서 정의하며, 모든 전화 시스템에 대해 동일하며, 모든 전화 시스템(PSTN 연결 사용자)에 대해 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="695c8-112">The other voice policy defines what calling features are available to the user; this voice policy is defined by Microsoft and is identical for all Phone System with on-premises PSTN connectivity users.</span></span> <span data-ttu-id="695c8-113">이 설정은 전화 시스템 사용자에게 자동으로 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="695c8-113">It is automatically assigned to Phone System users.</span></span>
  
||<span data-ttu-id="695c8-114">**On-premises user**</span><span class="sxs-lookup"><span data-stu-id="695c8-114">**On-premises user**</span></span>|<span data-ttu-id="695c8-115">**전화 시스템(프레미스 PSTN 연결 사용자 사용)**</span><span class="sxs-lookup"><span data-stu-id="695c8-115">**Phone System with on-premises PSTN connectivity user**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="695c8-116">에 정의된 통화 기능</span><span class="sxs-lookup"><span data-stu-id="695c8-116">Calling features defined in</span></span>  <br/> |<span data-ttu-id="695c8-117">음성 정책</span><span class="sxs-lookup"><span data-stu-id="695c8-117">Voice policy</span></span>  <br/> |<span data-ttu-id="695c8-118">사용자가 전화 시스템에 대한 라이선스를 부여할 때 자동으로 할당되는 미리 정의된 음성 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="695c8-118">Pre-defined voice policy, assigned automatically when the user is licensed for Phone System.</span></span>  <br/> |
|<span data-ttu-id="695c8-119">연결된 PSTN 사용 레코드</span><span class="sxs-lookup"><span data-stu-id="695c8-119">PSTN usage records associated with</span></span>  <br/> |<span data-ttu-id="695c8-120">음성 정책</span><span class="sxs-lookup"><span data-stu-id="695c8-120">Voice policy</span></span>  <br/> |<span data-ttu-id="695c8-121">사용자가 여전히 사내에 있는 동안 할당된 음성 라우팅 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="695c8-121">Voice routing policy, assigned while the user is still homed on-premises.</span></span>  <br/> |
   
<span data-ttu-id="695c8-122">사용자가 여전히 On-premises deployment에 있는 동안에는 다음 단계를 수행하여 사내 배포를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="695c8-122">You perform the following steps using your on-premises deployment, while the user is still homed in the on-premises deployment.</span></span>
  
## <a name="using-a-global-voice-routing-policy"></a><span data-ttu-id="695c8-123">전역 음성 라우팅 정책 사용</span><span class="sxs-lookup"><span data-stu-id="695c8-123">Using a global voice routing policy</span></span>

<span data-ttu-id="695c8-124">전화 시스템에 대해 전역 음성 라우팅 정책을 사용하려면 먼저 PSTN 사용 레코드를 정책에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="695c8-124">Before using a global voice routing policy for your Phone System with on-premises PSTN connectivity users, you must add PSTN usage records to the policy.</span></span>
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a><span data-ttu-id="695c8-125">PSTN 사용 레코드를 전역 음성 라우팅 정책에 할당</span><span class="sxs-lookup"><span data-stu-id="695c8-125">To assign PSTN usage records to the global voice routing policy</span></span>

1. <span data-ttu-id="695c8-126">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="695c8-126">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="695c8-127">비즈니스용 Skype 서버 관리 셸 시작: **시작,** 모든 **프로그램,** 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="695c8-127">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="695c8-128">정책에 PSTN 사용 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="695c8-128">Add the PSTN usage records to the policy:</span></span>
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages <PSTNUsagesId> 
   ```

    <span data-ttu-id="695c8-129">예:</span><span class="sxs-lookup"><span data-stu-id="695c8-129">For example:</span></span>
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages "Local", "Long Distance" 
   ```

## <a name="creating-a-new-voice-routing-policy"></a><span data-ttu-id="695c8-130">새 음성 라우팅 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="695c8-130">Creating a new voice routing policy</span></span>

### <a name="to-create-a-new-voice-routing-policy"></a><span data-ttu-id="695c8-131">새 음성 라우팅 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="695c8-131">To create a new voice routing policy</span></span>

1. <span data-ttu-id="695c8-132">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="695c8-132">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="695c8-133">비즈니스용 Skype 서버 관리 셸 시작: **시작,** 모든 **프로그램,** 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="695c8-133">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="695c8-134">새 음성 라우팅 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="695c8-134">Create a new voice routing policy:</span></span>
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity <String> -Name <String> -PSTNUsages <PSTNUsagesId>
   ```

    <span data-ttu-id="695c8-135">예:</span><span class="sxs-lookup"><span data-stu-id="695c8-135">For example:</span></span>
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity HybridVoice -Name Hybrid -PSTNUsages "Local", "Long Distance"
   ```

<span data-ttu-id="695c8-136">이 예에서는 두 개의 PSTN 사용이 연결된 HybridVoice라는 새 음성 라우팅 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="695c8-136">This example creates a new voice routing policy called HybridVoice, which has two PSTN usages associated with it.</span></span>
  
## <a name="assigning-a-voice-routing-policy"></a><span data-ttu-id="695c8-137">음성 라우팅 정책 할당</span><span class="sxs-lookup"><span data-stu-id="695c8-137">Assigning a voice routing policy</span></span>

<span data-ttu-id="695c8-138">전역 음성 라우팅 정책 또는 사용자별 정책에 상관없이 다음 단계를 사용하여 사용자에게 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="695c8-138">No matter whether you use the global voice routing policy, or user-specific ones, use the following steps to assign the policy to a user.</span></span>
  
### <a name="to-assign-the-voice-routing-policy"></a><span data-ttu-id="695c8-139">음성 라우팅 정책을 할당하기 위해</span><span class="sxs-lookup"><span data-stu-id="695c8-139">To assign the voice routing policy</span></span>

1. <span data-ttu-id="695c8-140">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="695c8-140">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="695c8-141">비즈니스용 Skype 서버 관리 셸 시작: **시작,** 모든 **프로그램,** 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="695c8-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="695c8-142">사용자에게 기존 음성 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="695c8-142">Assign an existing voice policy to a user:</span></span>
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    <span data-ttu-id="695c8-143">예:</span><span class="sxs-lookup"><span data-stu-id="695c8-143">For example:</span></span>
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity "Bob Kelly" -PolicyName HybridVoice
   ```

<span data-ttu-id="695c8-144">이 예에서는 표시 이름이 Bob Kelly인 사용자에게 이전에 만든 음성 정책에 HybridVoice가 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="695c8-144">In this example, the user with the display name Bob Kelly is assigned to the previously created voice policy with the name HybridVoice.</span></span>
  
<span data-ttu-id="695c8-145">음성 라우팅 정책에 대한 자세한 내용은 음성 정책 만들기 또는 수정 및 비즈니스용 [Skype 2015에서 PSTN](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md)사용 레코드 구성, [New-CsVoiceRoutingPolicy](/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)및 [Grant-CsVoicePolicy를](/powershell/module/skype/grant-csvoicepolicy?view=skype-ps)참조하세요.</span><span class="sxs-lookup"><span data-stu-id="695c8-145">For more details about voice routing policies, see [Create or modify a voice policy and configure PSTN usage records in Skype for Business 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), [New-CsVoiceRoutingPolicy](/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps), and [Grant-CsVoicePolicy](/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).</span></span>
