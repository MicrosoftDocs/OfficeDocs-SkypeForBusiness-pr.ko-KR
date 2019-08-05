---
title: 음성 라우팅 정책 지정
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: c7f78f23-b74f-402f-bedb-4cc308718f5b
description: 요약:이 항목에서는 Office 365에서 온-프레미스 PSTN 연결을 사용 하는 사용자를 위해 음성 정책을 할당 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 0d310378b77c09b427836f0d9bceb60a14982071
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196494"
---
# <a name="assign-a-voice-routing-policy"></a><span data-ttu-id="3d8e9-103">음성 라우팅 정책 지정</span><span class="sxs-lookup"><span data-stu-id="3d8e9-103">Assign a Voice Routing Policy</span></span>
 
<span data-ttu-id="3d8e9-104">**요약:** 이 항목에서는 Office 365에서 온-프레미스 PSTN 연결을 사용 하는 사용자를 위해 음성 정책을 할당 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e9-104">**Summary:** Read this topic to learn how to assign a voice policy for users using Phone System in Office 365 with on-premises PSTN connectivity.</span></span> 
  
<span data-ttu-id="3d8e9-105">사용자가 비즈니스용 Skype Online을 사용 하 고 있고 온-프레미스 PSTN 연결을 사용 하는 Office 365에서 전화 시스템을 사용할 경우 두 가지 음성 정책이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e9-105">Once a user is on Skype for Business Online and using Phone System in Office 365 with on-premises PSTN connectivity, two voice policies will apply to them.</span></span> <span data-ttu-id="3d8e9-106">하나는 온-프레미스 음성 라우팅 정책으로 서, 구내에 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e9-106">One is an on-premises voice routing policy that you will assign on premises.</span></span> <span data-ttu-id="3d8e9-107">이 정책은 전역 또는 사용자에 따라 가능 하며 사용자와 연결 되는 PSTN 사용 레코드를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e9-107">This policy can be global or user-specific and defines what PSTN usage records are associated with the user.</span></span> <span data-ttu-id="3d8e9-108">이 항목에서는이 정책을 할당 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e9-108">This topic explains how to assign this policy.</span></span>
  
<span data-ttu-id="3d8e9-109">다른 음성 정책은 사용자에 게 제공 되는 통화 기능을 정의 합니다. 이 음성 정책은 Microsoft에서 정의 하며 온-프레미스 PSTN 연결 사용자와 Office 365의 모든 전화 시스템에 대해 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e9-109">The other voice policy defines what calling features are available to the user; this voice policy is defined by Microsoft and is identical for all Phone System in Office 365 with on-premises PSTN connectivity users.</span></span> <span data-ttu-id="3d8e9-110">Office 365 사용자의 전화 시스템에 자동으로 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e9-110">It is automatically assigned to Phone System in Office 365 users.</span></span>
  
||<span data-ttu-id="3d8e9-111">**온-프레미스 사용자**</span><span class="sxs-lookup"><span data-stu-id="3d8e9-111">**On-premises user**</span></span>|<span data-ttu-id="3d8e9-112">**온-프레미스 PSTN 연결 사용자와 Office 365의 전화 시스템**</span><span class="sxs-lookup"><span data-stu-id="3d8e9-112">**Phone System in Office 365 with on-premises PSTN connectivity user**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3d8e9-113">에 정의 된 통화 기능</span><span class="sxs-lookup"><span data-stu-id="3d8e9-113">Calling features defined in</span></span>  <br/> |<span data-ttu-id="3d8e9-114">음성 정책</span><span class="sxs-lookup"><span data-stu-id="3d8e9-114">Voice policy</span></span>  <br/> |<span data-ttu-id="3d8e9-115">사전 정의 된 음성 정책은 사용자가 Office 365에서 전화 시스템을 사용 하도록 허가 받은 경우 자동으로 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e9-115">Pre-defined voice policy, assigned automatically when the user is licensed for Phone System in Office 365.</span></span>  <br/> |
|<span data-ttu-id="3d8e9-116">와 연결 된 PSTN 사용 레코드</span><span class="sxs-lookup"><span data-stu-id="3d8e9-116">PSTN usage records associated with</span></span>  <br/> |<span data-ttu-id="3d8e9-117">음성 정책</span><span class="sxs-lookup"><span data-stu-id="3d8e9-117">Voice policy</span></span>  <br/> |<span data-ttu-id="3d8e9-118">사용자가 온-프레미스 상태에서 지정 된 음성 라우팅 정책</span><span class="sxs-lookup"><span data-stu-id="3d8e9-118">Voice routing policy, assigned while the user is still homed on-premises.</span></span>  <br/> |
   
<span data-ttu-id="3d8e9-119">온-프레미스 배포를 사용 하 여 다음 단계를 수행 하는 반면 사용자는 온-프레미스 배포에 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e9-119">You perform the following steps using your on-premises deployment, while the user is still homed in the on-premises deployment.</span></span>
  
## <a name="using-a-global-voice-routing-policy"></a><span data-ttu-id="3d8e9-120">전역 음성 라우팅 정책 사용</span><span class="sxs-lookup"><span data-stu-id="3d8e9-120">Using a global voice routing policy</span></span>

<span data-ttu-id="3d8e9-121">Office 365에서 온-프레미스 PSTN 연결 사용자와 함께 전화 시스템에 대 한 전역 음성 라우팅 정책을 사용 하기 전에 정책에 PSTN 사용 레코드를 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e9-121">Before using a global voice routing policy for your Phone System in Office 365 with on-premises PSTN connectivity users, you must add PSTN usage records to the policy.</span></span>
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a><span data-ttu-id="3d8e9-122">전역 음성 라우팅 정책에 PSTN 사용 레코드 할당</span><span class="sxs-lookup"><span data-stu-id="3d8e9-122">To assign PSTN usage records to the global voice routing policy</span></span>

1. <span data-ttu-id="3d8e9-123">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e9-123">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="3d8e9-124">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e9-124">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="3d8e9-125">정책에 PSTN 사용 레코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e9-125">Add the PSTN usage records to the policy:</span></span>
    
   ```
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages <PSTNUsagesId> 
   ```

    <span data-ttu-id="3d8e9-126">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e9-126">For example:</span></span>
    
   ```
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages "Local", "Long Distance" 
   ```

## <a name="creating-a-new-voice-routing-policy"></a><span data-ttu-id="3d8e9-127">새 음성 라우팅 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="3d8e9-127">Creating a new voice routing policy</span></span>

### <a name="to-create-a-new-voice-routing-policy"></a><span data-ttu-id="3d8e9-128">새 음성 라우팅 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="3d8e9-128">To create a new voice routing policy</span></span>

1. <span data-ttu-id="3d8e9-129">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e9-129">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="3d8e9-130">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e9-130">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="3d8e9-131">새 음성 라우팅 정책 만들기:</span><span class="sxs-lookup"><span data-stu-id="3d8e9-131">Create a new voice routing policy:</span></span>
    
   ```
   New-CSVoiceRoutingPolicy -Identity <String> -Name <String> -PSTNUsages <PSTNUsagesId>
   ```

    <span data-ttu-id="3d8e9-132">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e9-132">For example:</span></span>
    
   ```
   New-CSVoiceRoutingPolicy -Identity HybridVoice -Name Hybrid -PSTNUsages "Local", "Long Distance"
   ```

<span data-ttu-id="3d8e9-133">이 예제에서는 두 개의 PSTN 용도와 연결 된 HybridVoice 이라는 새 음성 라우팅 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e9-133">This example creates a new voice routing policy called HybridVoice, which has two PSTN usages associated with it.</span></span>
  
## <a name="assigning-a-voice-routing-policy"></a><span data-ttu-id="3d8e9-134">음성 라우팅 정책 지정</span><span class="sxs-lookup"><span data-stu-id="3d8e9-134">Assigning a voice routing policy</span></span>

<span data-ttu-id="3d8e9-135">전역 음성 라우팅 정책 (사용자 관련)을 사용 하는지 여부에 관계 없이 다음 단계를 사용 하 여 정책을 사용자에 게 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e9-135">No matter whether you use the global voice routing policy, or user-specific ones, use the following steps to assign the policy to a user.</span></span>
  
### <a name="to-assign-the-voice-routing-policy"></a><span data-ttu-id="3d8e9-136">음성 라우팅 정책을 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="3d8e9-136">To assign the voice routing policy</span></span>

1. <span data-ttu-id="3d8e9-137">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e9-137">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="3d8e9-138">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e9-138">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="3d8e9-139">기존 음성 정책을 사용자에 게 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e9-139">Assign an existing voice policy to a user:</span></span>
    
   ```
   Grant-CsVoiceRoutingPolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    <span data-ttu-id="3d8e9-140">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e9-140">For example:</span></span>
    
   ```
   Grant-CsVoiceRoutingPolicy -Identity "Bob Kelly" -PolicyName HybridVoice
   ```

<span data-ttu-id="3d8e9-141">이 예제에서 표시 이름이 Bob 최소라 인 사용자는 이전에 만든 이름 HybridVoice를 사용 하는 음성 정책에 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d8e9-141">In this example, the user with the display name Bob Kelly is assigned to the previously created voice policy with the name HybridVoice.</span></span>
  
<span data-ttu-id="3d8e9-142">음성 라우팅 정책에 대 한 자세한 내용은 [음성 정책 만들기 또는 수정 및 비즈니스용 Skype 2015, CsVoiceRoutingPolicy 및 CsVoicePolicy에 대 한 PSTN 사용 레코드 구성을](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md)참조 하세요. [](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps) [](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="3d8e9-142">For more details about voice routing policies, see [Create or modify a voice policy and configure PSTN usage records in Skype for Business 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps), and [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).</span></span>
  

