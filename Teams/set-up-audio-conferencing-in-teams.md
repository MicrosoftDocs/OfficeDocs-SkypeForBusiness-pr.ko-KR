---
title: Microsoft 팀을 위한 오디오 회의 설정
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d01954f1-4f37-4cf5-a636-20039e5c59e9
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- LIL_Placement
description: '휴대폰을 사용 하 여 전화 회의에 참가 해야 하는 사용자에 대해 전화 접속 또는 오디오 회의를 설정 하는 방법에 대해 알아봅니다. '
ms.openlocfilehash: e14cf924d039b461df3fc84d7b600d96d515be58
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41838068"
---
# <a name="set-up-audio-conferencing-for-microsoft-teams"></a><span data-ttu-id="6abfe-103">Microsoft 팀을 위한 오디오 회의 설정</span><span class="sxs-lookup"><span data-stu-id="6abfe-103">Set up Audio Conferencing for Microsoft Teams</span></span>

<span data-ttu-id="6abfe-104">조직의 사용자가 모임에 전화를 걸 때 휴대폰을 사용 해야 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6abfe-104">Sometimes people in your organization will need to use a phone to call in to a meeting.</span></span> <span data-ttu-id="6abfe-105">Microsoft 팀에는 이러한 상황에 대 한 오디오 회의 기능이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6abfe-105">Microsoft Teams includes the audio conferencing feature for just this situation!</span></span> <span data-ttu-id="6abfe-106">사용자는 모바일 장치 또는 PC에서 팀 앱을 사용 하는 대신 휴대폰을 사용 하 여 팀 회의에 통화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6abfe-106">People can call in to Teams meetings using a phone, instead of using the Teams app on a mobile device or PC.</span></span> 
  
<span data-ttu-id="6abfe-107">모임 일정을 계획하거나 주도하는 사용자들을 위해 오디오 회의를 설정하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6abfe-107">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings.</span></span> <span data-ttu-id="6abfe-108">전화를 걸 수 있는 모임 참석자는 해당 사용자 또는 다른 설정에 할당 된 라이선스가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6abfe-108">Meeting attendees who dial in don't need any licenses assigned to them or other setup.</span></span>
  
<span data-ttu-id="6abfe-109">오디오 회의에 대 한 질문과 대답은 [오디오 회의 일반적인 질문](audio-conferencing-common-questions.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6abfe-109">For frequently asked questions about Audio Conferencing, see [Audio Conferencing common questions](audio-conferencing-common-questions.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a><span data-ttu-id="6abfe-110">1 단계: 자신의 국가/지역에서 음성 회의를 사용할 수 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="6abfe-110">Step 1: Find out if Audio Conferencing is available in your country/region</span></span>
<span data-ttu-id="6abfe-111"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="6abfe-111"><a name="__top"> </a></span></span>

<span data-ttu-id="6abfe-112">오디오 회의 [및 통화 요금제에 대 한 국가 및 지역](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) 으로 이동 하 고, 전화 시스템, 통화 요금제, 유료 및 무료 번호, 통신 크레딧에 대 한 정보를 비롯 하 여 오디오 회의에 대 한 가용성 정보를 얻을 국가 또는 지역을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6abfe-112">Go to [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) and select your country or region to get availability information about Audio Conferencing, as well as information about Phone System, Calling Plans, toll and toll-free numbers, and Communications Credits.</span></span> 
 
## <a name="step-2-get-and-assign-licenses"></a><span data-ttu-id="6abfe-113">2 단계: 라이선스 가져오기 및 할당</span><span class="sxs-lookup"><span data-stu-id="6abfe-113">Step 2: Get and assign licenses</span></span>
 
1. <span data-ttu-id="6abfe-114">오디오 회의의 경우 전화 접속 모임을 설정 하는 각 사용자에 대 한 라이선스가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="6abfe-114">For Audio Conferencing, you need a license for each user who will set up dial-in meetings.</span></span> <span data-ttu-id="6abfe-115">오디오 회의를 위해 구입 해야 하는 라이선스에 대해 알아보고 비용을 얼마나 사용할 수 있는지 알아보려면 [Microsoft 팀 추가 기능 라이선스](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6abfe-115">To learn which licenses you need to buy for Audio Conferencing and how much they will cost, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

    >[!NOTE] 
    > <span data-ttu-id="6abfe-116">오디오 회의는 Office 365 Enterprise E5 라이선스에 포함 되어 있으며 추가 기능으로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6abfe-116">Audio Conferencing is included in Office 365 Enterprise E5 licenses and as an add-on.</span></span>
        
2. <span data-ttu-id="6abfe-117">오디오 회의 라이선스를 구입한 후에는 모임을 예약 하거나 진행 하는 조직의 사용자에 게 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6abfe-117">After you buy the Audio Conferencing licenses, you will need to assign them to those people in your organization who are going to schedule or lead meetings.</span></span> <span data-ttu-id="6abfe-118">조직의 사용자에 게 예약 또는 잠재 고객 모임이 있는 사용자에 게 구입한 [비즈니스용 Office 365에서 라이선스 할당](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6abfe-118">See [Assign licenses to users in Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) you purchased to the people in your organization who are going to schedule or lead meetings.</span></span>
    
3. <span data-ttu-id="6abfe-119">또한 이전 단계에서 라이선스를 할당 한 동일한 사람에 게 통신 크레딧 라이선스 (아무런 비용 없음)를 할당 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6abfe-119">We also recommend that you assign Communications Credits licenses (they don’t cost anything) to the same people you assigned licenses to in the previous step.</span></span> <span data-ttu-id="6abfe-120">통신 크레딧을 설정 하는 방법에 [대 한 자세한 내용은 조직의 통신 크레딧 설정을](set-up-communications-credits-for-your-organization.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6abfe-120">To learn how to set up Communications Credits, see [Set up Communications Credits for your organization](set-up-communications-credits-for-your-organization.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="6abfe-121">[분당 유료 오디오 회의](audio-conferencing-pay-per-minute.md)를 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6abfe-121">You can also set up [pay-per-minute Audio Conferencing](audio-conferencing-pay-per-minute.md).</span></span>

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a><span data-ttu-id="6abfe-122">3 단계: 회의 브리지에 대 한 서비스 번호 가져오기</span><span class="sxs-lookup"><span data-stu-id="6abfe-122">Step 3: Get service numbers for your conferencing bridges</span></span>
<span data-ttu-id="6abfe-123"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="6abfe-123"><a name="__top"> </a></span></span>

<span data-ttu-id="6abfe-124">오디오 회의의 경우 사용자에 게 전화 번호를 사용할 수 없습니다. 서비스 번호를 구해야 할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6abfe-124">For Audio Conferencing, you can’t use phone numbers for users; you will need to get service numbers.</span></span> <span data-ttu-id="6abfe-125">회의 브리지에 대해 유료 또는 무료 서비스 번호를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6abfe-125">You can get either toll or toll-free service numbers for your conferencing bridges.</span></span> <span data-ttu-id="6abfe-126">다음과 같은 세 가지 방법으로 유료 및 무료 서비스 번호를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6abfe-126">There are three ways to get toll and toll-free service numbers:</span></span> 
  
- <span data-ttu-id="6abfe-127">**Microsoft 팀 관리 센터를 사용**합니다.</span><span class="sxs-lookup"><span data-stu-id="6abfe-127">**Use the Microsoft Teams admin center**.</span></span> <span data-ttu-id="6abfe-128">일부 국가/지역의 경우 Microsoft 팀 관리 센터를 사용 하 여 회의 브리지의 서비스 번호를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6abfe-128">For some countries/regions, you can get service numbers for your conferencing bridges using the Microsoft Teams admin center.</span></span> <span data-ttu-id="6abfe-129">[서비스 전화 번호 가져오기를](/microsoftteams/getting-service-phone-numbers)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6abfe-129">See [Getting service phone numbers](/microsoftteams/getting-service-phone-numbers).</span></span>
    
- <span data-ttu-id="6abfe-130">**기존 서비스 번호를 이식**합니다.</span><span class="sxs-lookup"><span data-stu-id="6abfe-130">**Port your existing service numbers**.</span></span> <span data-ttu-id="6abfe-131">현재 서비스 공급자 또는 전화 통신 회사의 기존 번호를 Office 365으로 이식 하거나 이전 합니다.</span><span class="sxs-lookup"><span data-stu-id="6abfe-131">To port or transfer existing numbers from your current service provider or phone carrier to Office 365.</span></span> <span data-ttu-id="6abfe-132">이 작업을 수행 하는 데 도움이 되는 자세한 내용은 [팀에 전화 번호 전송](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) 또는 [조직에 대 한 전화 번호 관리](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 를 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="6abfe-132">You can see [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) or [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) for more information to help you do this.</span></span>  
  
- <span data-ttu-id="6abfe-133">**새 번호에 요청 양식을 사용**합니다.</span><span class="sxs-lookup"><span data-stu-id="6abfe-133">**Use a request form for new numbers**.</span></span> <span data-ttu-id="6abfe-134">때로는 (국가/지역에 따라) Microsoft 팀 관리 센터를 사용 하 여 새 서비스 번호를 받을 수 없으며, 특정 전화 번호 또는 지역 코드도 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="6abfe-134">Sometimes (depending on your country/region) you won't be able to get your new service numbers using the Microsoft Teams admin center, or you will need specific phone numbers or area codes.</span></span> <span data-ttu-id="6abfe-135">그렇다면 양식을 다운로드 하 여 다시 전송 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6abfe-135">If so, you will need to download a form and send it back to us.</span></span> <span data-ttu-id="6abfe-136">자세한 내용은 [조직의 전화 번호 관리](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6abfe-136">See [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) for more information.</span></span> 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a><span data-ttu-id="6abfe-137">4 단계: 회의 브리지에 서비스 번호 할당</span><span class="sxs-lookup"><span data-stu-id="6abfe-137">Step 4: Assign a service number to the conferencing bridge</span></span>
<span data-ttu-id="6abfe-138"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="6abfe-138"><a name="__top"> </a></span></span>

<span data-ttu-id="6abfe-139">회의 브리지에 대해 유료 및/또는 무료 전화 번호를 받은 후에는 모임 초대에 사용할 수 있도록 번호를 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6abfe-139">Once you get your toll and/or toll-free phone numbers for your conferencing bridge, you need to assign the numbers so they can be used on meeting invitations.</span></span>  

<span data-ttu-id="6abfe-140">오디오 회의 브리지에 새 전화 번호를 지정 하려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="6abfe-140">Follow these steps to assign a new phone number to your audio conferencing bridge.</span></span>

<span data-ttu-id="6abfe-141">![비즈니스용 skype](media/sfb-logo-30x30.png) **관리 센터를 사용 하 여** 비즈니스용 skype 로고를 표시 하는 아이콘:</span><span class="sxs-lookup"><span data-stu-id="6abfe-141">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

 1. <span data-ttu-id="6abfe-142">**Microsoft 365 관리 센터** > **관리** > 센터**팀** > **레거시 포털로**이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="6abfe-142">Go to the **Microsoft 365 admin center** > **Admin centers** > **Teams** > **Legacy portal**.</span></span>
 2. <span data-ttu-id="6abfe-143">**Voice** > **전화번호**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6abfe-143">Select **Voice** > **Phone numbers**.</span></span>
 3. <span data-ttu-id="6abfe-144">전화 번호를 선택 하 고 **할당**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6abfe-144">Select the phone number, and click **Assign**.</span></span>

<span data-ttu-id="6abfe-145">자세한 내용은 [오디오 회의 브리지에서 전화 번호 변경을](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6abfe-145">For more details, see [Change the phone numbers on your Audio Conferencing bridge](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span></span>

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a><span data-ttu-id="6abfe-146">5 단계: 회의 브리지의 기본 및 대체 언어 설정</span><span class="sxs-lookup"><span data-stu-id="6abfe-146">Step 5: Set the default and alternate languages for a conferencing bridge</span></span>
<span data-ttu-id="6abfe-147"><a name="__top"></a> 다음으로, 회의 자동 전화 교환에서 오디오 회의에 대 한 전화 번호로 전화를 걸 때 발신자를 위해 사용 하는 [Microsoft 팀에서 오디오 회의에 대 한 자동 전화 교환 언어를 설정](set-auto-attendant-languages-for-audio-conferencing-in-teams.md) 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="6abfe-147"><a name="__top"> </a> Next, you want to [Set auto attendant languages for Audio Conferencing in Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md) that the conferencing auto attendant uses to greet callers when they dial in to a phone number for Audio Conferencing.</span></span> 

<span data-ttu-id="6abfe-148">![Microsoft](media/teams-logo-30x30.png) **팀 관리 센터를 사용 하 여**microsoft 팀 로고를 표시 하는 아이콘:</span><span class="sxs-lookup"><span data-stu-id="6abfe-148">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="6abfe-149">대시보드에서 **모임** > **회의 브리지로**이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="6abfe-149">From the Dashboard, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="6abfe-150">회의 브리지 전화 번호를 선택 하 고 **편집**을 클릭 한 다음 기본 언어를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6abfe-150">Select the conferencing bridge phone number, click **Edit**, and then choose the default language.</span></span>

## <a name="step-6-set-your-conferencing-bridge-settings"></a><span data-ttu-id="6abfe-151">6 단계: 회의 브리지 설정 설정</span><span class="sxs-lookup"><span data-stu-id="6abfe-151">Step 6: Set your conferencing bridge settings</span></span>
<span data-ttu-id="6abfe-152"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="6abfe-152"><a name="__top"> </a></span></span>
    
<span data-ttu-id="6abfe-153">회의 브리지를 설정한 후에는 입력/종료 알림과 PIN 길이 등의 기본 설정이 사용할 것인지 확인 합니다. 그렇지 않은 경우 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6abfe-153">After setting up your conferencing bridge, verify that the default settings such as entry/exit notifications and PIN length are the ones you want to use; if they're not, you can change them.</span></span> 

<span data-ttu-id="6abfe-154">![Microsoft](media/teams-logo-30x30.png) **팀 관리 센터를 사용 하 여**microsoft 팀 로고를 표시 하는 아이콘:</span><span class="sxs-lookup"><span data-stu-id="6abfe-154">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="6abfe-155">대시보드에서 **모임** > **회의 브리지로**이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="6abfe-155">From the Dashboard, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="6abfe-156">**브리지 설정을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6abfe-156">Select **Bridge settings**.</span></span> <span data-ttu-id="6abfe-157">이렇게 하면 **브리지 설정** 창이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="6abfe-157">This will open the **Bridge settings** pane.</span></span> 

<span data-ttu-id="6abfe-158">자세한 내용은 [오디오 회의 브리지에 대 한 설정 변경을](change-the-settings-for-an-audio-conferencing-bridge.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6abfe-158">For more details, see [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a><span data-ttu-id="6abfe-159">7 단계: 모임 리더 사용자를 위한 전화 접속 전화 번호 지정</span><span class="sxs-lookup"><span data-stu-id="6abfe-159">Step 7: Assign dial-in phone numbers for users who lead meetings</span></span>

<span data-ttu-id="6abfe-160">오디오 회의 브리지를 만든 후에는 사용자의 유료 및 무료 전화 번호를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6abfe-160">After you have created an Audio Conferencing bridge, you need to set the toll and toll-free numbers for your users.</span></span>

<span data-ttu-id="6abfe-161">모임에 참가 하거나 일정을 예약 하는 조직의 모든 사용자에 대해이 작업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6abfe-161">You will need to do this for all of the people in your organization who lead or schedule meetings.</span></span> 

<span data-ttu-id="6abfe-162">![Microsoft](media/teams-logo-30x30.png) **팀 관리 센터를 사용 하 여**microsoft 팀 로고를 표시 하는 아이콘:</span><span class="sxs-lookup"><span data-stu-id="6abfe-162">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="6abfe-163">대시보드에서 **사용자**를 클릭 하 고 목록에서 사용자를 선택한 다음 **편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6abfe-163">From the Dashboard, click **Users**, select the user from the list, and select **Edit**.</span></span>
2. <span data-ttu-id="6abfe-164">**오디오 회의**옆에 있는 **편집** 을 선택 하 고 **오디오 회의** 창의 **유료 번호** 및 무료 번호 목록 **에서 번호를** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6abfe-164">Select **Edit** next to **Audio Conferencing**, and then in the **Audio Conferencing** pane, choose a number in the **Toll number** and **Toll-free** number lists.</span></span>

<span data-ttu-id="6abfe-165">자세한 내용은 [Microsoft를 오디오 회의 공급자로 지정](/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6abfe-165">If you need more details, see [Assign Microsoft as the audio conferencing provider](/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span></span>


## <a name="step-8-set-up-meeting-invitations-optional"></a><span data-ttu-id="6abfe-166">8 단계: 모임 초대 설정 (선택 사항)</span><span class="sxs-lookup"><span data-stu-id="6abfe-166">Step 8: Set up meeting invitations (optional)</span></span>
<span data-ttu-id="6abfe-167"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="6abfe-167"><a name="__top"> </a></span></span>
 
<span data-ttu-id="6abfe-168">사용자에 대해 설정 된 전화 접속 번호가 모임 참석자에 게 전송 되는 모임 초대에 자동으로 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6abfe-168">The dial-in numbers that are set for the user will be automatically added to the meeting invitations that are sent to meeting attendees.</span></span> <span data-ttu-id="6abfe-169">그러나 원하는 경우 자신만의 도움말 및 법률 링크, 문자 메시지, 작은 회사 그래픽을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6abfe-169">However, you can add your own help and legal links, a text message, and small company graphic if you want.</span></span> <span data-ttu-id="6abfe-170">[모임 초대 사용자 지정](meeting-settings-in-teams.md#customize-meeting-invitations)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6abfe-170">See [Customize meeting invitations](meeting-settings-in-teams.md#customize-meeting-invitations).</span></span>
   
## <a name="related-topics"></a><span data-ttu-id="6abfe-171">관련 항목</span><span class="sxs-lookup"><span data-stu-id="6abfe-171">Related topics</span></span>

[<span data-ttu-id="6abfe-172">오디오 회의 일반적인 질문</span><span class="sxs-lookup"><span data-stu-id="6abfe-172">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
  
[<span data-ttu-id="6abfe-173">Microsoft 팀에서 오디오 회의를 위한 전화 번호</span><span class="sxs-lookup"><span data-stu-id="6abfe-173">Phone numbers for Audio Conferencing in Microsoft Teams</span></span>](phone-numbers-for-audio-conferencing-in-teams.md)
  
[<span data-ttu-id="6abfe-174">온라인 모임 및 컨퍼런스 통화에 대 한 옵션 설정</span><span class="sxs-lookup"><span data-stu-id="6abfe-174">Set options for online meetings and conference calls</span></span>](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
