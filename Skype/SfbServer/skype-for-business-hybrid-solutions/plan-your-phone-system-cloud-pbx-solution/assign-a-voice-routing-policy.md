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
description: '요약: 온-프레미스 PSTN 연결과 함께 전화 시스템을 사용 하는 사용자에 게 음성 정책을 할당 하는 방법에 대해 알아보려면이 항목을 읽어 보십시오.'
ms.openlocfilehash: 141d3cca560201df921fb4195db55ac60103a3d6
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221862"
---
# <a name="assign-a-voice-routing-policy"></a><span data-ttu-id="e3b54-103">음성 라우팅 정책 할당</span><span class="sxs-lookup"><span data-stu-id="e3b54-103">Assign a Voice Routing Policy</span></span>
 
<span data-ttu-id="e3b54-104">**요약:** 온-프레미스 PSTN 연결과 함께 전화 시스템을 사용 하는 사용자에 게 음성 정책을 할당 하는 방법에 대 한 자세한 내용은이 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e3b54-104">**Summary:** Read this topic to learn how to assign a voice policy for users using Phone System with on-premises PSTN connectivity.</span></span> 
  
<span data-ttu-id="e3b54-105">사용자가 비즈니스용 Skype 온라인에 있고 온-프레미스 PSTN 연결을 통해 전화 시스템을 사용 하는 경우 두 가지 음성 정책이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3b54-105">Once a user is on Skype for Business Online and using Phone System with on-premises PSTN connectivity, two voice policies will apply to them.</span></span> <span data-ttu-id="e3b54-106">하나는 온-프레미스 음성 라우팅 정책 (온-프레미스에 할당)입니다.</span><span class="sxs-lookup"><span data-stu-id="e3b54-106">One is an on-premises voice routing policy that you will assign on premises.</span></span> <span data-ttu-id="e3b54-107">이 정책은 전역 또는 사용자별 일 수 있으며 사용자와 연결 된 PSTN 사용 레코드를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3b54-107">This policy can be global or user-specific and defines what PSTN usage records are associated with the user.</span></span> <span data-ttu-id="e3b54-108">이 항목에서는이 정책을 할당 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3b54-108">This topic explains how to assign this policy.</span></span>
  
<span data-ttu-id="e3b54-109">다른 음성 정책은 사용자가 사용할 수 있는 호출 기능을 정의 합니다. 이 음성 정책은 Microsoft에서 정의 되며 온-프레미스 PSTN 연결 사용자가 있는 모든 전화 시스템에서 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3b54-109">The other voice policy defines what calling features are available to the user; this voice policy is defined by Microsoft and is identical for all Phone System with on-premises PSTN connectivity users.</span></span> <span data-ttu-id="e3b54-110">전화 시스템 사용자에 게 자동으로 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3b54-110">It is automatically assigned to Phone System users.</span></span>
  
||<span data-ttu-id="e3b54-111">**온-프레미스 사용자**</span><span class="sxs-lookup"><span data-stu-id="e3b54-111">**On-premises user**</span></span>|<span data-ttu-id="e3b54-112">**온-프레미스 PSTN 연결 사용자가 있는 전화 시스템**</span><span class="sxs-lookup"><span data-stu-id="e3b54-112">**Phone System with on-premises PSTN connectivity user**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e3b54-113">통화 기능 정의</span><span class="sxs-lookup"><span data-stu-id="e3b54-113">Calling features defined in</span></span>  <br/> |<span data-ttu-id="e3b54-114">음성 정책</span><span class="sxs-lookup"><span data-stu-id="e3b54-114">Voice policy</span></span>  <br/> |<span data-ttu-id="e3b54-115">사용자가 전화 시스템에 대해 사용이 허가 될 때 자동으로 할당 되는 미리 정의 된 음성 정책</span><span class="sxs-lookup"><span data-stu-id="e3b54-115">Pre-defined voice policy, assigned automatically when the user is licensed for Phone System.</span></span>  <br/> |
|<span data-ttu-id="e3b54-116">연결 된 PSTN 사용 레코드</span><span class="sxs-lookup"><span data-stu-id="e3b54-116">PSTN usage records associated with</span></span>  <br/> |<span data-ttu-id="e3b54-117">음성 정책</span><span class="sxs-lookup"><span data-stu-id="e3b54-117">Voice policy</span></span>  <br/> |<span data-ttu-id="e3b54-118">사용자가 계속 온-프레미스에 있는 동안 지정 된 음성 라우팅 정책</span><span class="sxs-lookup"><span data-stu-id="e3b54-118">Voice routing policy, assigned while the user is still homed on-premises.</span></span>  <br/> |
   
<span data-ttu-id="e3b54-119">온-프레미스 배포를 사용 하 여 다음 단계를 수행 하는 동안 사용자는 여전히 온-프레미스 배포에 속해 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3b54-119">You perform the following steps using your on-premises deployment, while the user is still homed in the on-premises deployment.</span></span>
  
## <a name="using-a-global-voice-routing-policy"></a><span data-ttu-id="e3b54-120">전역 음성 라우팅 정책 사용</span><span class="sxs-lookup"><span data-stu-id="e3b54-120">Using a global voice routing policy</span></span>

<span data-ttu-id="e3b54-121">온-프레미스 PSTN 연결 사용자와 전화 시스템에 대해 전역 음성 라우팅 정책을 사용 하기 전에 정책에 PSTN 사용 레코드를 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3b54-121">Before using a global voice routing policy for your Phone System with on-premises PSTN connectivity users, you must add PSTN usage records to the policy.</span></span>
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a><span data-ttu-id="e3b54-122">전역 음성 라우팅 정책에 PSTN 사용 레코드를 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="e3b54-122">To assign PSTN usage records to the global voice routing policy</span></span>

1. <span data-ttu-id="e3b54-123">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="e3b54-123">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="e3b54-124">비즈니스용 Skype 서버 관리 셸 시작: **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 **비즈니스용 skype 서버 관리 셸을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3b54-124">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="e3b54-125">정책에 PSTN 사용 레코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3b54-125">Add the PSTN usage records to the policy:</span></span>
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages <PSTNUsagesId> 
   ```

    <span data-ttu-id="e3b54-126">예시는 다음과 같습니다:</span><span class="sxs-lookup"><span data-stu-id="e3b54-126">For example:</span></span>
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages "Local", "Long Distance" 
   ```

## <a name="creating-a-new-voice-routing-policy"></a><span data-ttu-id="e3b54-127">새 음성 라우팅 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="e3b54-127">Creating a new voice routing policy</span></span>

### <a name="to-create-a-new-voice-routing-policy"></a><span data-ttu-id="e3b54-128">새 음성 라우팅 정책을 만들려면</span><span class="sxs-lookup"><span data-stu-id="e3b54-128">To create a new voice routing policy</span></span>

1. <span data-ttu-id="e3b54-129">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="e3b54-129">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="e3b54-130">비즈니스용 Skype 서버 관리 셸 시작: **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 **비즈니스용 skype 서버 관리 셸을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3b54-130">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="e3b54-131">새 음성 라우팅 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e3b54-131">Create a new voice routing policy:</span></span>
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity <String> -Name <String> -PSTNUsages <PSTNUsagesId>
   ```

    <span data-ttu-id="e3b54-132">예시는 다음과 같습니다:</span><span class="sxs-lookup"><span data-stu-id="e3b54-132">For example:</span></span>
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity HybridVoice -Name Hybrid -PSTNUsages "Local", "Long Distance"
   ```

<span data-ttu-id="e3b54-133">이 예에서는 PSTN을 두 번 사용 하 여 연결 된 HybridVoice 라는 새 음성 라우팅 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e3b54-133">This example creates a new voice routing policy called HybridVoice, which has two PSTN usages associated with it.</span></span>
  
## <a name="assigning-a-voice-routing-policy"></a><span data-ttu-id="e3b54-134">음성 라우팅 정책 지정</span><span class="sxs-lookup"><span data-stu-id="e3b54-134">Assigning a voice routing policy</span></span>

<span data-ttu-id="e3b54-135">전역 음성 라우팅 정책이 사용 되는지, 아니면 사용자에 게 어떤 관련이 있는지에 관계 없이 다음 단계를 수행 하 여 사용자에 게 정책을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3b54-135">No matter whether you use the global voice routing policy, or user-specific ones, use the following steps to assign the policy to a user.</span></span>
  
### <a name="to-assign-the-voice-routing-policy"></a><span data-ttu-id="e3b54-136">음성 라우팅 정책을 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="e3b54-136">To assign the voice routing policy</span></span>

1. <span data-ttu-id="e3b54-137">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="e3b54-137">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="e3b54-138">비즈니스용 Skype 서버 관리 셸 시작: **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 **비즈니스용 skype 서버 관리 셸을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3b54-138">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="e3b54-139">기존 음성 정책을 사용자에 게 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3b54-139">Assign an existing voice policy to a user:</span></span>
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    <span data-ttu-id="e3b54-140">예시는 다음과 같습니다:</span><span class="sxs-lookup"><span data-stu-id="e3b54-140">For example:</span></span>
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity "Bob Kelly" -PolicyName HybridVoice
   ```

<span data-ttu-id="e3b54-141">이 예에서 표시 이름이 Bob 최소라 인 사용자는 이름이 HybridVoice 인 이전에 만든 음성 정책에 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3b54-141">In this example, the user with the display name Bob Kelly is assigned to the previously created voice policy with the name HybridVoice.</span></span>
  
<span data-ttu-id="e3b54-142">음성 라우팅 정책에 대 한 자세한 내용은 [Create or modify a voice policy And 비즈니스용 Skype 2015, get-csvoiceroutingpolicy 및 set-csvoicepolicy에 대 한 PSTN 사용 레코드 구성을](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md)참조 하십시오 [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps). [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="e3b54-142">For more details about voice routing policies, see [Create or modify a voice policy and configure PSTN usage records in Skype for Business 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps), and [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).</span></span>
  

