---
title: 비즈니스용 Skype 서버에서 위치 정책 만들기
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 이 항목을 통해 비즈니스용 Skype 서버 2013에서 E9-1-1(Enhanced Emergency Service) 위치 정책을 구성하는 방법을 Enterprise Voice.
ms.openlocfilehash: cee02204a9c5b3708a83e9433f6a88c70230fd64
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093146"
---
# <a name="create-location-policies-in-skype-for-business-server"></a><span data-ttu-id="93fbe-103">비즈니스용 Skype 서버에서 위치 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="93fbe-103">Create location policies in Skype for Business Server</span></span>

<span data-ttu-id="93fbe-104">이 항목을 통해 비즈니스용 Skype 서버 2013에서 E9-1-1(Enhanced Emergency Service) 위치 정책을 구성하는 방법을 Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="93fbe-104">Read this topic to learn how to configure enhanced emergency service (E9-1-1) location policies in Skype for Business Server Enterprise Voice.</span></span> 

<span data-ttu-id="93fbe-105">비즈니스용 Skype 서버는 위치 정책을 사용하여 클라이언트 등록 중에 E9-1-1에 대해 비즈니스용 Skype 클라이언트를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="93fbe-105">Skype for Business Server uses a location policy to enable Skype for Business clients for E9-1-1 during client registration.</span></span> <span data-ttu-id="93fbe-106">위치 정책에는 E9-1-1을 구현하는 방법을 정의하는 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93fbe-106">A location policy contains the settings that define how E9-1-1 will be implemented.</span></span> <span data-ttu-id="93fbe-107">자세한 내용은 [Plan location policies for Skype for Business Server을 참조하십시오.](../../plan-your-deployment/enterprise-voice-solution/location-policies.md)</span><span class="sxs-lookup"><span data-stu-id="93fbe-107">For more information, see [Plan location policies for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/location-policies.md).</span></span>

<span data-ttu-id="93fbe-108">비즈니스용 Skype 제어판 또는 [New-CsLocationPolicy](/powershell/module/skype/new-cslocationpolicy?view=skype-ps) cmdlet을 사용하여 위치 정책을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="93fbe-108">You define location policies by using the Skype for Business Control Panel or by using the [New-CsLocationPolicy](/powershell/module/skype/new-cslocationpolicy?view=skype-ps) cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="93fbe-109">비즈니스용 Skype 서버는 이제 클라이언트에 대해 여러 긴급 번호의 구성을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="93fbe-109">Skype for Business Server now supports the configuration of multiple emergency numbers for a client.</span></span> <span data-ttu-id="93fbe-110">여러 긴급 번호를 구성하려면 비즈니스용 Skype 서버에서 여러 긴급 번호 계획 및 비즈니스용 [Skype에서](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md) 여러 긴급 번호 구성의 정보를 [따라야 합니다.](configure-multiple-emergency-numbers.md)</span><span class="sxs-lookup"><span data-stu-id="93fbe-110">If you want to configure multiple emergency numbers, you must follow the information in [Plan for multiple emergency numbers in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md) and [Configure multiple emergency numbers in Skype for Business](configure-multiple-emergency-numbers.md).</span></span> 

<span data-ttu-id="93fbe-111">전역 위치 정책을 편집하고 태그가 지정한 새 위치 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93fbe-111">You can edit the global location policy and create new tagged location policies.</span></span> <span data-ttu-id="93fbe-112">클라이언트는 연결된 위치 정책이 있는 서브넷 내에 있지 않은 경우 또는 클라이언트에 위치 정책이 직접 할당되지 않은 경우 전역 정책을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="93fbe-112">A client obtains a global policy when it is not located within a subnet with an associated location policy, or when the client has not been directly assigned a location policy.</span></span> <span data-ttu-id="93fbe-113">태그가 지정된 정책은 서브넷 또는 사용자에게 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="93fbe-113">Tagged policies are assigned to subnets or users.</span></span> 

<span data-ttu-id="93fbe-114">위치 정책을 만들하려면 RTCUniversalServerAdmins 그룹의 구성원 또는 CsVoiceAdministrator 관리 역할의 구성원 또는 동등한 관리자 권한 및 사용 권한이 있는 계정을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93fbe-114">To create a location policy, you must use an account that is a member of the RTCUniversalServerAdmins group, or is a member of the CsVoiceAdministrator administrative role, or has equivalent administrator rights and permissions.</span></span>

<span data-ttu-id="93fbe-115">자세한 내용은 [Plan location policies for Skype for Business Server을 참조하십시오.](../../plan-your-deployment/enterprise-voice-solution/location-policies.md)</span><span class="sxs-lookup"><span data-stu-id="93fbe-115">For more information, see [Plan location policies for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/location-policies.md).</span></span> <span data-ttu-id="93fbe-116">이 절차의 cmdlet은 다음 값을 사용하여 정의된 위치 정책을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="93fbe-116">Cmdlets in this procedure use a location policy defined using the following values.</span></span> <span data-ttu-id="93fbe-117">cmdlet 매개 변수 및 값에 대한 자세한 내용은 [New-CsLocationPolicy를 참조하세요.](/powershell/module/skype/new-cslocationpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="93fbe-117">For a complete description of cmdlet parameters and values, see [New-CsLocationPolicy](/powershell/module/skype/new-cslocationpolicy?view=skype-ps).</span></span>


| <span data-ttu-id="93fbe-118">**요소**</span><span class="sxs-lookup"><span data-stu-id="93fbe-118">**Element**</span></span>                               | <span data-ttu-id="93fbe-119">**값**</span><span class="sxs-lookup"><span data-stu-id="93fbe-119">**Value**</span></span>                                                                                                                                                                          |
|:------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="93fbe-120">EnhancedEmergencyServicesEnabled</span><span class="sxs-lookup"><span data-stu-id="93fbe-120">EnhancedEmergencyServicesEnabled</span></span>  <br/>   | <span data-ttu-id="93fbe-121">**True**</span><span class="sxs-lookup"><span data-stu-id="93fbe-121">**True**</span></span> <br/>                                                                                                                                                                     |
| <span data-ttu-id="93fbe-122">LocationRequired</span><span class="sxs-lookup"><span data-stu-id="93fbe-122">LocationRequired</span></span>  <br/>                   | <span data-ttu-id="93fbe-123">**고지 사항**</span><span class="sxs-lookup"><span data-stu-id="93fbe-123">**Disclaimer**</span></span> <br/>                                                                                                                                                               |
| <span data-ttu-id="93fbe-124">EnhancedEmergencyServiceDisclaimer</span><span class="sxs-lookup"><span data-stu-id="93fbe-124">EnhancedEmergencyServiceDisclaimer</span></span>  <br/> | <span data-ttu-id="93fbe-125">회사 정책을 사용하려면 위치를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93fbe-125">Your company policy requires you to set a location.</span></span> <span data-ttu-id="93fbe-126">위치를 설정하지 않은 경우 응급 서비스가 긴급 상황 시 위치를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="93fbe-126">If you do not set a location, emergency services will not be able to locate you in an emergency.</span></span> <span data-ttu-id="93fbe-127">위치를 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="93fbe-127">Please set a location.</span></span>  <br/> |
| <span data-ttu-id="93fbe-128">UseLocationForE911Only</span><span class="sxs-lookup"><span data-stu-id="93fbe-128">UseLocationForE911Only</span></span>  <br/>             | <span data-ttu-id="93fbe-129">**False**</span><span class="sxs-lookup"><span data-stu-id="93fbe-129">**False**</span></span> <br/>                                                                                                                                                                    |
| <span data-ttu-id="93fbe-130">PstnUsage</span><span class="sxs-lookup"><span data-stu-id="93fbe-130">PstnUsage</span></span>  <br/>                          | <span data-ttu-id="93fbe-131">**EmergencyUsage**</span><span class="sxs-lookup"><span data-stu-id="93fbe-131">**EmergencyUsage**</span></span> <br/>                                                                                                                                                           |
| <span data-ttu-id="93fbe-132">EmergencyDialString</span><span class="sxs-lookup"><span data-stu-id="93fbe-132">EmergencyDialString</span></span>  <br/>                | <span data-ttu-id="93fbe-133">**911**</span><span class="sxs-lookup"><span data-stu-id="93fbe-133">**911**</span></span> <br/>                                                                                                                                                                      |
| <span data-ttu-id="93fbe-134">EmergencyDialMask</span><span class="sxs-lookup"><span data-stu-id="93fbe-134">EmergencyDialMask</span></span>  <br/>                  | <span data-ttu-id="93fbe-135">**112**</span><span class="sxs-lookup"><span data-stu-id="93fbe-135">**112**</span></span> <br/>                                                                                                                                                                      |
| <span data-ttu-id="93fbe-136">NotificationUri</span><span class="sxs-lookup"><span data-stu-id="93fbe-136">NotificationUri</span></span>  <br/>                    | <span data-ttu-id="93fbe-137"><strong>sip:security@litwareinc.com</strong></span><span class="sxs-lookup"><span data-stu-id="93fbe-137"><strong>sip:security@litwareinc.com</strong></span></span> <br/>                                                                                                                                 |
| <span data-ttu-id="93fbe-138">ConferenceUri</span><span class="sxs-lookup"><span data-stu-id="93fbe-138">ConferenceUri</span></span>  <br/>                      | <span data-ttu-id="93fbe-139"><strong>sip:+14255550123@litwareinc.com</strong></span><span class="sxs-lookup"><span data-stu-id="93fbe-139"><strong>sip:+14255550123@litwareinc.com</strong></span></span> <br/>                                                                                                                             |
| <span data-ttu-id="93fbe-140">ConferenceMode</span><span class="sxs-lookup"><span data-stu-id="93fbe-140">ConferenceMode</span></span>  <br/>                     | <span data-ttu-id="93fbe-141">**twoway**</span><span class="sxs-lookup"><span data-stu-id="93fbe-141">**twoway**</span></span> <br/>                                                                                                                                                                   |
| <span data-ttu-id="93fbe-142">LocationRefreshInterval</span><span class="sxs-lookup"><span data-stu-id="93fbe-142">LocationRefreshInterval</span></span>  <br/>            | <span data-ttu-id="93fbe-143">**2**</span><span class="sxs-lookup"><span data-stu-id="93fbe-143">**2**</span></span> <br/>                                                                                                                                                                        |

### <a name="to-create-location-policies"></a><span data-ttu-id="93fbe-144">위치 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93fbe-144">To create location policies</span></span>

1. <span data-ttu-id="93fbe-145">비즈니스용 Skype 서버 관리 셸 시작: **시작,** 모든 **프로그램,** 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="93fbe-145">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="93fbe-146">**PstnUsage의 설정이 PstnUsages의** 전역 목록에 없는 경우 CsLocationPolicy가 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="93fbe-146">CsLocationPolicy will fail if the setting for **PstnUsage** is not already in the Global list of PstnUsages.</span></span>

2. <span data-ttu-id="93fbe-147">선택적으로 다음 cmdlet을 실행하여 전역 위치 정책을 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="93fbe-147">Optionally, run the following cmdlet to edit the global Location Policy:</span></span>

   ```powershell
   Set-CsLocationPolicy -Identity Global -EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -PstnUsage "emergencyUsage" -EmergencyDialString "911" -ConferenceMode "twoway" -ConferenceUri "sip:+14255550123@litwareinc.com" -EmergencyDialMask "112" NotificationUri "sip:security@litwareinc.com" -UseLocationForE911Only $true -LocationRefreshInterval 2
   ```

3. <span data-ttu-id="93fbe-148">다음을 실행하여 태그가 지정된 위치 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93fbe-148">Run the following to create a tagged Location Policy.</span></span>

   ```powershell
   New-CsLocationPolicy -Identity Tag:Redmond - EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -UseLocationForE911Only $false -PstnUsage "EmergencyUsage" -EmergencyDialString "911" -EmergencyDialMask "112" -NotificationUri "sip:security@litwareinc.com" -ConferenceUri "sip:+14255550123@litwareinc.com" -ConferenceMode "twoway" -LocationRefreshInterval 2
   ```

4. <span data-ttu-id="93fbe-149">다음 cmdlet을 실행하여 3단계에서 만든 태그가 지정한 위치 정책을 사용자 정책에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="93fbe-149">Run the following cmdlet to apply the tagged Location Policy created in step 3 to a user policy.</span></span>

   ```powershell
   (Get-CsUser | where { $_.Name -match "UserName" }) | Grant-CsLocationPolicy -PolicyName Redmond
   ```