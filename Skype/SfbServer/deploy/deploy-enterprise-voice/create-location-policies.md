---
title: 비즈니스용 Skype 서버에서 위치 정책 만들기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f1878194-c756-4794-8fa1-15dd2118b4b3
description: 비즈니스용 Skype Server Enterprise Voice에서 향상 된 응급 서비스 (E9-1-1) 위치 정책을 구성 하는 방법에 대 한 자세한 내용은이 항목을 참조 하세요.
ms.openlocfilehash: d06e22850b1556e4c7d9143b49176aff23bb6640
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767941"
---
# <a name="create-location-policies-in-skype-for-business-server"></a><span data-ttu-id="30744-103">비즈니스용 Skype 서버에서 위치 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="30744-103">Create location policies in Skype for Business Server</span></span>

<span data-ttu-id="30744-104">비즈니스용 Skype Server Enterprise Voice에서 향상 된 응급 서비스 (E9-1-1) 위치 정책을 구성 하는 방법에 대 한 자세한 내용은이 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="30744-104">Read this topic to learn how to configure enhanced emergency service (E9-1-1) location policies in Skype for Business Server Enterprise Voice.</span></span> 

<span data-ttu-id="30744-105">비즈니스용 skype Server는 위치 정책을 사용 하 여 E9에서 비즈니스용 Skype 클라이언트를 사용 하도록 설정 합니다 (클라이언트 등록 중-1-1).</span><span class="sxs-lookup"><span data-stu-id="30744-105">Skype for Business Server uses a location policy to enable Skype for Business clients for E9-1-1 during client registration.</span></span> <span data-ttu-id="30744-106">위치 정책에는 E9-1-1이 구현 되는 방법을 정의 하는 설정이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30744-106">A location policy contains the settings that define how E9-1-1 will be implemented.</span></span> <span data-ttu-id="30744-107">자세한 내용은 [비즈니스용 Skype 서버용 계획 위치 정책을](../../plan-your-deployment/enterprise-voice-solution/location-policies.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="30744-107">For more information, see [Plan location policies for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/location-policies.md).</span></span>

<span data-ttu-id="30744-108">Skype for 비즈니스용 제어판을 사용 하거나 [새-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) cmdlet을 사용 하 여 위치 정책을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="30744-108">You define location policies by using the Skype for Business Control Panel or by using the [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="30744-109">비즈니스용 Skype 서버는 이제 클라이언트에 대 한 여러 응급 번호 구성을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="30744-109">Skype for Business Server now supports the configuration of multiple emergency numbers for a client.</span></span> <span data-ttu-id="30744-110">여러 비상 번호를 구성 하려는 경우 비즈니스용 [Skype 서버에서 여러 응급 번호 계획](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md) 의 정보를 따르고 [비즈니스용 skype에서 여러 응급 번호를 구성](configure-multiple-emergency-numbers.md)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="30744-110">If you want to configure multiple emergency numbers, you must follow the information in [Plan for multiple emergency numbers in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md) and [Configure multiple emergency numbers in Skype for Business](configure-multiple-emergency-numbers.md).</span></span> 

<span data-ttu-id="30744-111">전역 위치 정책을 편집 하 고 태그가 지정 된 새 위치 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30744-111">You can edit the global location policy and create new tagged location policies.</span></span> <span data-ttu-id="30744-112">클라이언트는 연결 된 위치 정책을 사용 하 여 서브넷 내에 있지 않거나 클라이언트에 위치 정책이 직접 할당 되지 않은 경우 전역 정책을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="30744-112">A client obtains a global policy when it is not located within a subnet with an associated location policy, or when the client has not been directly assigned a location policy.</span></span> <span data-ttu-id="30744-113">태그가 지정 된 정책은 서브넷 또는 사용자에 게 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="30744-113">Tagged policies are assigned to subnets or users.</span></span> 

<span data-ttu-id="30744-114">위치 정책을 만들려면 RTCUniversalServerAdmins 그룹의 구성원 이거나 CsVoiceAdministrator 관리 역할의 구성원 이거나 해당 관리자 권한 및 사용 권한이 있는 계정을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="30744-114">To create a location policy, you must use an account that is a member of the RTCUniversalServerAdmins group, or is a member of the CsVoiceAdministrator administrative role, or has equivalent administrator rights and permissions.</span></span>

<span data-ttu-id="30744-115">자세한 내용은 [비즈니스용 Skype 서버용 계획 위치 정책을](../../plan-your-deployment/enterprise-voice-solution/location-policies.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="30744-115">For more information, see [Plan location policies for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/location-policies.md).</span></span> <span data-ttu-id="30744-116">이 절차의 cmdlet에서는 다음 값을 사용 하 여 정의 된 위치 정책을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="30744-116">Cmdlets in this procedure use a location policy defined using the following values.</span></span> <span data-ttu-id="30744-117">Cmdlet 매개 변수 및 값에 대 한 자세한 내용은 [신규-CsLocationPolicy 정책을](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="30744-117">For a complete description of cmdlet parameters and values, see [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps).</span></span>


| <span data-ttu-id="30744-118">**요소**</span><span class="sxs-lookup"><span data-stu-id="30744-118">**Element**</span></span>                               | <span data-ttu-id="30744-119">**값**</span><span class="sxs-lookup"><span data-stu-id="30744-119">**Value**</span></span>                                                                                                                                                                          |
|:------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="30744-120">EnhancedEmergencyServicesEnabled</span><span class="sxs-lookup"><span data-stu-id="30744-120">EnhancedEmergencyServicesEnabled</span></span>  <br/>   | <span data-ttu-id="30744-121">**False**</span><span class="sxs-lookup"><span data-stu-id="30744-121">**True**</span></span> <br/>                                                                                                                                                                     |
| <span data-ttu-id="30744-122">LocationRequired</span><span class="sxs-lookup"><span data-stu-id="30744-122">LocationRequired</span></span>  <br/>                   | <span data-ttu-id="30744-123">**고 지 사항**</span><span class="sxs-lookup"><span data-stu-id="30744-123">**Disclaimer**</span></span> <br/>                                                                                                                                                               |
| <span data-ttu-id="30744-124">EnhancedEmergencyServiceDisclaimer</span><span class="sxs-lookup"><span data-stu-id="30744-124">EnhancedEmergencyServiceDisclaimer</span></span>  <br/> | <span data-ttu-id="30744-125">회사 정책에 따라 위치를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="30744-125">Your company policy requires you to set a location.</span></span> <span data-ttu-id="30744-126">위치를 설정 하지 않으면 비상 서비스는 비상 시 사용자를 찾을 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="30744-126">If you do not set a location, emergency services will not be able to locate you in an emergency.</span></span> <span data-ttu-id="30744-127">위치를 설정 하십시오.</span><span class="sxs-lookup"><span data-stu-id="30744-127">Please set a location.</span></span>  <br/> |
| <span data-ttu-id="30744-128">UseLocationForE911Only</span><span class="sxs-lookup"><span data-stu-id="30744-128">UseLocationForE911Only</span></span>  <br/>             | <span data-ttu-id="30744-129">**해제**</span><span class="sxs-lookup"><span data-stu-id="30744-129">**False**</span></span> <br/>                                                                                                                                                                    |
| <span data-ttu-id="30744-130">PstnUsage</span><span class="sxs-lookup"><span data-stu-id="30744-130">PstnUsage</span></span>  <br/>                          | <span data-ttu-id="30744-131">**EmergencyUsage**</span><span class="sxs-lookup"><span data-stu-id="30744-131">**EmergencyUsage**</span></span> <br/>                                                                                                                                                           |
| <span data-ttu-id="30744-132">EmergencyDialString</span><span class="sxs-lookup"><span data-stu-id="30744-132">EmergencyDialString</span></span>  <br/>                | <span data-ttu-id="30744-133">**911**</span><span class="sxs-lookup"><span data-stu-id="30744-133">**911**</span></span> <br/>                                                                                                                                                                      |
| <span data-ttu-id="30744-134">EmergencyDialMask</span><span class="sxs-lookup"><span data-stu-id="30744-134">EmergencyDialMask</span></span>  <br/>                  | <span data-ttu-id="30744-135">**112**</span><span class="sxs-lookup"><span data-stu-id="30744-135">**112**</span></span> <br/>                                                                                                                                                                      |
| <span data-ttu-id="30744-136">NotificationUri</span><span class="sxs-lookup"><span data-stu-id="30744-136">NotificationUri</span></span>  <br/>                    | <span data-ttu-id="30744-137"><strong>sip:security@litwareinc.com</strong></span><span class="sxs-lookup"><span data-stu-id="30744-137"><strong>sip:security@litwareinc.com</strong></span></span> <br/>                                                                                                                                 |
| <span data-ttu-id="30744-138">ConferenceUri</span><span class="sxs-lookup"><span data-stu-id="30744-138">ConferenceUri</span></span>  <br/>                      | <span data-ttu-id="30744-139"><strong>sip:+14255550123@litwareinc.com</strong></span><span class="sxs-lookup"><span data-stu-id="30744-139"><strong>sip:+14255550123@litwareinc.com</strong></span></span> <br/>                                                                                                                             |
| <span data-ttu-id="30744-140">ConferenceMode</span><span class="sxs-lookup"><span data-stu-id="30744-140">ConferenceMode</span></span>  <br/>                     | <span data-ttu-id="30744-141">**twoway**</span><span class="sxs-lookup"><span data-stu-id="30744-141">**twoway**</span></span> <br/>                                                                                                                                                                   |
| <span data-ttu-id="30744-142">LocationRefreshInterval</span><span class="sxs-lookup"><span data-stu-id="30744-142">LocationRefreshInterval</span></span>  <br/>            | <span data-ttu-id="30744-143">**2**</span><span class="sxs-lookup"><span data-stu-id="30744-143">**2**</span></span> <br/>                                                                                                                                                                        |

### <a name="to-create-location-policies"></a><span data-ttu-id="30744-144">위치 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="30744-144">To create location policies</span></span>

1. <span data-ttu-id="30744-145">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="30744-145">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="30744-146">**PstnUsage** 에 대 한 설정이 PstnUsages의 전역 목록에 없으면 CsLocationPolicy가 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="30744-146">CsLocationPolicy will fail if the setting for **PstnUsage** is not already in the Global list of PstnUsages.</span></span>

2. <span data-ttu-id="30744-147">필요에 따라 다음 cmdlet을 실행 하 여 전역 위치 정책을 편집 합니다.</span><span class="sxs-lookup"><span data-stu-id="30744-147">Optionally, run the following cmdlet to edit the global Location Policy:</span></span>

   ```powershell
   Set-CsLocationPolicy -Identity Global -EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -PstnUsage "emergencyUsage" -EmergencyDialString "911" -ConferenceMode "twoway" -ConferenceUri "sip:+14255550123@litwareinc.com" -EmergencyDialMask "112" NotificationUri "sip:security@litwareinc.com" -UseLocationForE911Only $true -LocationRefreshInterval 2
   ```

3. <span data-ttu-id="30744-148">다음을 실행 하 여 태그가 지정 된 위치 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="30744-148">Run the following to create a tagged Location Policy.</span></span>

   ```powershell
   New-CsLocationPolicy -Identity Tag:Redmond - EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -UseLocationForE911Only $false -PstnUsage "EmergencyUsage" -EmergencyDialString "911" -EmergencyDialMask "112" -NotificationUri "sip:security@litwareinc.com" -ConferenceUri "sip:+14255550123@litwareinc.com" -ConferenceMode "twoway" -LocationRefreshInterval 2
   ```

4. <span data-ttu-id="30744-149">3 단계에서 만든 태그가 지정 된 위치 정책을 사용자 정책에 적용 하려면 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="30744-149">Run the following cmdlet to apply the tagged Location Policy created in step 3 to a user policy.</span></span>

   ```powershell
   (Get-CsUser | where { $_.Name -match "UserName" }) | Grant-CsLocationPolicy -PolicyName Redmond
   ```
