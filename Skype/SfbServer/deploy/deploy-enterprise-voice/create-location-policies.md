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
description: 이 항목을 읽고 비즈니스용 Skype 서버 2016에서 E9-1-1(고급 응급 서비스) 위치 정책을 구성하는 Enterprise Voice.
ms.openlocfilehash: 4230d6ac1a820cb9612d58b21a2e5b6ae36d8f77
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822548"
---
# <a name="create-location-policies-in-skype-for-business-server"></a><span data-ttu-id="f41be-103">비즈니스용 Skype 서버에서 위치 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="f41be-103">Create location policies in Skype for Business Server</span></span>

<span data-ttu-id="f41be-104">이 항목을 읽고 비즈니스용 Skype 서버 2016에서 E9-1-1(고급 응급 서비스) 위치 정책을 구성하는 Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="f41be-104">Read this topic to learn how to configure enhanced emergency service (E9-1-1) location policies in Skype for Business Server Enterprise Voice.</span></span> 

<span data-ttu-id="f41be-105">비즈니스용 Skype 서버는 클라이언트 등록 중에 위치 정책을 사용하여 비즈니스용 Skype 클라이언트가 E9-1-1을 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f41be-105">Skype for Business Server uses a location policy to enable Skype for Business clients for E9-1-1 during client registration.</span></span> <span data-ttu-id="f41be-106">위치 정책에는 E9-1-1 구현 방법을 정의하는 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f41be-106">A location policy contains the settings that define how E9-1-1 will be implemented.</span></span> <span data-ttu-id="f41be-107">자세한 내용은 비즈니스용 Skype 서버의 [위치 정책 계획을 참조하세요.](../../plan-your-deployment/enterprise-voice-solution/location-policies.md)</span><span class="sxs-lookup"><span data-stu-id="f41be-107">For more information, see [Plan location policies for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/location-policies.md).</span></span>

<span data-ttu-id="f41be-108">비즈니스용 Skype 제어판 또는 [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) cmdlet을 사용하여 위치 정책을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f41be-108">You define location policies by using the Skype for Business Control Panel or by using the [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="f41be-109">비즈니스용 Skype 서버는 이제 클라이언트에 대해 여러 긴급 번호 구성을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="f41be-109">Skype for Business Server now supports the configuration of multiple emergency numbers for a client.</span></span> <span data-ttu-id="f41be-110">여러 긴급 번호를 구성하려면 비즈니스용 [Skype](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md) 서버에서 여러 긴급 번호 계획의 정보를 따르고 비즈니스용 Skype에서 여러 긴급 번호를 [구성해야 합니다.](configure-multiple-emergency-numbers.md)</span><span class="sxs-lookup"><span data-stu-id="f41be-110">If you want to configure multiple emergency numbers, you must follow the information in [Plan for multiple emergency numbers in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md) and [Configure multiple emergency numbers in Skype for Business](configure-multiple-emergency-numbers.md).</span></span> 

<span data-ttu-id="f41be-111">전역 위치 정책을 편집하고 태그가 있는 새 위치 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f41be-111">You can edit the global location policy and create new tagged location policies.</span></span> <span data-ttu-id="f41be-112">클라이언트는 연결된 위치 정책이 있는 서브넷 내에 있지 않은 경우 또는 클라이언트에 위치 정책이 직접 할당되지 않은 경우 전역 정책을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="f41be-112">A client obtains a global policy when it is not located within a subnet with an associated location policy, or when the client has not been directly assigned a location policy.</span></span> <span data-ttu-id="f41be-113">태그가 지정된 정책은 서브넷 또는 사용자에게 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="f41be-113">Tagged policies are assigned to subnets or users.</span></span> 

<span data-ttu-id="f41be-114">위치 정책을 만들하려면 RTCUniversalServerAdmins 그룹의 구성원인 계정 또는 CsVoiceAdministrator 관리 역할의 구성원 또는 동등한 관리자 권한이 있는 계정을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f41be-114">To create a location policy, you must use an account that is a member of the RTCUniversalServerAdmins group, or is a member of the CsVoiceAdministrator administrative role, or has equivalent administrator rights and permissions.</span></span>

<span data-ttu-id="f41be-115">자세한 내용은 비즈니스용 Skype 서버의 [위치 정책 계획을 참조하세요.](../../plan-your-deployment/enterprise-voice-solution/location-policies.md)</span><span class="sxs-lookup"><span data-stu-id="f41be-115">For more information, see [Plan location policies for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/location-policies.md).</span></span> <span data-ttu-id="f41be-116">이 절차의 cmdlet은 다음 값을 사용하여 정의된 위치 정책을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f41be-116">Cmdlets in this procedure use a location policy defined using the following values.</span></span> <span data-ttu-id="f41be-117">cmdlet 매개 변수 및 값에 대한 자세한 내용은 [New-CsLocationPolicy를 참조하세요.](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="f41be-117">For a complete description of cmdlet parameters and values, see [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps).</span></span>


| <span data-ttu-id="f41be-118">**요소**</span><span class="sxs-lookup"><span data-stu-id="f41be-118">**Element**</span></span>                               | <span data-ttu-id="f41be-119">**값**</span><span class="sxs-lookup"><span data-stu-id="f41be-119">**Value**</span></span>                                                                                                                                                                          |
|:------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="f41be-120">EnhancedEmergencyServicesEnabled</span><span class="sxs-lookup"><span data-stu-id="f41be-120">EnhancedEmergencyServicesEnabled</span></span>  <br/>   | <span data-ttu-id="f41be-121">**True**</span><span class="sxs-lookup"><span data-stu-id="f41be-121">**True**</span></span> <br/>                                                                                                                                                                     |
| <span data-ttu-id="f41be-122">LocationRequired</span><span class="sxs-lookup"><span data-stu-id="f41be-122">LocationRequired</span></span>  <br/>                   | <span data-ttu-id="f41be-123">**고지 사항**</span><span class="sxs-lookup"><span data-stu-id="f41be-123">**Disclaimer**</span></span> <br/>                                                                                                                                                               |
| <span data-ttu-id="f41be-124">EnhancedEmergencyServiceDisclaimer</span><span class="sxs-lookup"><span data-stu-id="f41be-124">EnhancedEmergencyServiceDisclaimer</span></span>  <br/> | <span data-ttu-id="f41be-125">회사 정책에 따라 위치를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f41be-125">Your company policy requires you to set a location.</span></span> <span data-ttu-id="f41be-126">위치를 설정하지 않은 경우 응급 서비스에서 응급 서비스를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f41be-126">If you do not set a location, emergency services will not be able to locate you in an emergency.</span></span> <span data-ttu-id="f41be-127">위치를 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="f41be-127">Please set a location.</span></span>  <br/> |
| <span data-ttu-id="f41be-128">UseLocationForE911Only</span><span class="sxs-lookup"><span data-stu-id="f41be-128">UseLocationForE911Only</span></span>  <br/>             | <span data-ttu-id="f41be-129">**거짓**</span><span class="sxs-lookup"><span data-stu-id="f41be-129">**False**</span></span> <br/>                                                                                                                                                                    |
| <span data-ttu-id="f41be-130">PstnUsage</span><span class="sxs-lookup"><span data-stu-id="f41be-130">PstnUsage</span></span>  <br/>                          | <span data-ttu-id="f41be-131">**EmergencyUsage**</span><span class="sxs-lookup"><span data-stu-id="f41be-131">**EmergencyUsage**</span></span> <br/>                                                                                                                                                           |
| <span data-ttu-id="f41be-132">EmergencyDialString</span><span class="sxs-lookup"><span data-stu-id="f41be-132">EmergencyDialString</span></span>  <br/>                | <span data-ttu-id="f41be-133">**911**</span><span class="sxs-lookup"><span data-stu-id="f41be-133">**911**</span></span> <br/>                                                                                                                                                                      |
| <span data-ttu-id="f41be-134">EmergencyDialMask</span><span class="sxs-lookup"><span data-stu-id="f41be-134">EmergencyDialMask</span></span>  <br/>                  | <span data-ttu-id="f41be-135">**112**</span><span class="sxs-lookup"><span data-stu-id="f41be-135">**112**</span></span> <br/>                                                                                                                                                                      |
| <span data-ttu-id="f41be-136">NotificationUri</span><span class="sxs-lookup"><span data-stu-id="f41be-136">NotificationUri</span></span>  <br/>                    | <span data-ttu-id="f41be-137"><strong>sip:security@litwareinc.com</strong></span><span class="sxs-lookup"><span data-stu-id="f41be-137"><strong>sip:security@litwareinc.com</strong></span></span> <br/>                                                                                                                                 |
| <span data-ttu-id="f41be-138">ConferenceUri</span><span class="sxs-lookup"><span data-stu-id="f41be-138">ConferenceUri</span></span>  <br/>                      | <span data-ttu-id="f41be-139"><strong>sip:+14255550123@litwareinc.com</strong></span><span class="sxs-lookup"><span data-stu-id="f41be-139"><strong>sip:+14255550123@litwareinc.com</strong></span></span> <br/>                                                                                                                             |
| <span data-ttu-id="f41be-140">ConferenceMode</span><span class="sxs-lookup"><span data-stu-id="f41be-140">ConferenceMode</span></span>  <br/>                     | <span data-ttu-id="f41be-141">**twoway**</span><span class="sxs-lookup"><span data-stu-id="f41be-141">**twoway**</span></span> <br/>                                                                                                                                                                   |
| <span data-ttu-id="f41be-142">LocationRefreshInterval</span><span class="sxs-lookup"><span data-stu-id="f41be-142">LocationRefreshInterval</span></span>  <br/>            | <span data-ttu-id="f41be-143">**2**</span><span class="sxs-lookup"><span data-stu-id="f41be-143">**2**</span></span> <br/>                                                                                                                                                                        |

### <a name="to-create-location-policies"></a><span data-ttu-id="f41be-144">위치 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f41be-144">To create location policies</span></span>

1. <span data-ttu-id="f41be-145">비즈니스용 Skype 서버 관리 셸 시작: **시작,** **모든** 프로그램, 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f41be-145">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f41be-146">**PstnUsage 설정이 PstnUsages의** 전역 목록에 아직 없는 경우 CsLocationPolicy가 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="f41be-146">CsLocationPolicy will fail if the setting for **PstnUsage** is not already in the Global list of PstnUsages.</span></span>

2. <span data-ttu-id="f41be-147">선택적으로 다음 cmdlet을 실행하여 전역 위치 정책을 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="f41be-147">Optionally, run the following cmdlet to edit the global Location Policy:</span></span>

   ```powershell
   Set-CsLocationPolicy -Identity Global -EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -PstnUsage "emergencyUsage" -EmergencyDialString "911" -ConferenceMode "twoway" -ConferenceUri "sip:+14255550123@litwareinc.com" -EmergencyDialMask "112" NotificationUri "sip:security@litwareinc.com" -UseLocationForE911Only $true -LocationRefreshInterval 2
   ```

3. <span data-ttu-id="f41be-148">다음을 실행하여 태그가 지정된 위치 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f41be-148">Run the following to create a tagged Location Policy.</span></span>

   ```powershell
   New-CsLocationPolicy -Identity Tag:Redmond - EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -UseLocationForE911Only $false -PstnUsage "EmergencyUsage" -EmergencyDialString "911" -EmergencyDialMask "112" -NotificationUri "sip:security@litwareinc.com" -ConferenceUri "sip:+14255550123@litwareinc.com" -ConferenceMode "twoway" -LocationRefreshInterval 2
   ```

4. <span data-ttu-id="f41be-149">다음 cmdlet을 실행하여 3단계에서 만든 태그가 지정한 위치 정책을 사용자 정책에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="f41be-149">Run the following cmdlet to apply the tagged Location Policy created in step 3 to a user policy.</span></span>

   ```powershell
   (Get-CsUser | where { $_.Name -match "UserName" }) | Grant-CsLocationPolicy -PolicyName Redmond
   ```
