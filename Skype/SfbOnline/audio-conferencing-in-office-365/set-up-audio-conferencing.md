---
title: 오디오 회의 설정 비즈니스용 Skype
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d01954f1-4f37-4cf5-a636-20039e5c59e9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- LIL_Placement
- O365P_DialInConfDesc
description: '전화를 사용하여 전화 회의에 참여해야 하는 회사의 사용자를 위해 전화 접속 또는 오디오 회의를 설정하는 방법을 알아봅니다. '
ms.openlocfilehash: ce5d80b8be0fe2e6983229be8185bcdf02e06ab6
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237644"
---
# <a name="set-up-audio-conferencing-for-skype-for-business"></a><span data-ttu-id="874b3-103">오디오 회의 설정 비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="874b3-103">Set up Audio Conferencing for Skype for Business</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="874b3-104">경우에 따라 조직의 사용자가 전화를 사용하여 모임에 전화해야 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="874b3-104">Sometimes people in your organization will need to use a phone to call in to a meeting.</span></span> <span data-ttu-id="874b3-105">비즈니스용 Skype 상황에 대한 오디오 회의 기능이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="874b3-105">Skype for Business includes the audio conferencing feature for just this situation!</span></span> <span data-ttu-id="874b3-106">모바일 디바이스 또는 PC에서 비즈니스용 Skype 앱을 사용하는 대신 휴대폰을 사용하여 비즈니스용 Skype 모임에 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="874b3-106">People can call in to Skype for Business meetings using a phone, instead of using the Skype for Business app on a mobile device or PC.</span></span> 
  
<span data-ttu-id="874b3-107">모임 일정을 계획하거나 주도하는 사용자들을 위해 오디오 회의를 설정하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="874b3-107">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings.</span></span> <span data-ttu-id="874b3-108">전화를 거는 모임 참석자는 자신에게 할당된 라이선스 혹은 그 외 설정이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="874b3-108">Meeting attendees who dial in don't need any licenses assigned to them or other setup.</span></span>
  
<span data-ttu-id="874b3-109">오디오 회의에 대한 질문과 대답을 확인하려면 [오디오 회의에 대한 일반적인 질문](/MicrosoftTeams/audio-conferencing-common-questions)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="874b3-109">For frequently asked questions about Audio Conferencing, see [Audio Conferencing common questions](/MicrosoftTeams/audio-conferencing-common-questions).</span></span>

## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a><span data-ttu-id="874b3-110">1단계: 사용자의 국가/지역에서 오디오 회의를 사용할 수 있는지 확인하기</span><span class="sxs-lookup"><span data-stu-id="874b3-110">Step 1: Find out if Audio Conferencing is available in your country/region</span></span>
<span data-ttu-id="874b3-111"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="874b3-111"><a name="__top"> </a></span></span>

<span data-ttu-id="874b3-112">[오디오 회의 및 통화 플랜의 국가 및 지역 가용성](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)으로 이동하고 해당 국가나 지역을 선택하여 전화 시스템, 통화 플랜, 유료 및 무료 전화번호, 통신 크레딧에 대한 정보뿐만 아니라 오디오 회의에 대한 가용성 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="874b3-112">Go to [Country and region availability for Audio Conferencing and Calling Plans](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans) and select your country or region to get availability information about Audio Conferencing, as well as information about Phone System, Calling Plans, toll and toll-free numbers, and Communications Credits.</span></span> 
 
## <a name="step-2-get-and-assign-licenses"></a><span data-ttu-id="874b3-113">2단계: 라이선스 받기 및 할당하기</span><span class="sxs-lookup"><span data-stu-id="874b3-113">Step 2: Get and assign licenses</span></span>
 
1. <span data-ttu-id="874b3-114">오디오 회의를 위해서는 전화 접속 모임을 설정할 각 사용자에 대한 라이선스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="874b3-114">For Audio Conferencing, you need a license for each user who will set up dial-in meetings.</span></span> <span data-ttu-id="874b3-115">오디오 회의를 위해 구입해야 하는 라이선스와 비용에 대한 자세한 내용은 추가 비즈니스용 Skype 라이선스 를 [참조합니다.](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="874b3-115">To learn which licenses you need to buy for Audio Conferencing and how much they will cost, see [Skype for Business add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

    >[!NOTE] 
    > <span data-ttu-id="874b3-116">오디오 회의는 Office 365 Enterprise E5 라이선스에 추가 기능으로 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="874b3-116">Audio Conferencing is included in Office 365 Enterprise E5 licenses and as an add-on.</span></span>
        
2. <span data-ttu-id="874b3-117">오디오 회의 라이선스를 구입한 후에는 모임을 예약하거나 진행할 조직의 사용자에게 라이선스를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="874b3-117">After you buy the Audio Conferencing licenses, you will need to assign them to those people in your organization who are going to schedule or lead meetings.</span></span> <span data-ttu-id="874b3-118">[모임을](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) 예약하거나 이끌 조직의 비즈니스용 Microsoft 365 앱 사용자에 대한 라이선스 할당 또는 제거를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="874b3-118">See [Assign or remove licenses for Microsoft 365 Apps for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) you purchased to the people in your organization who are going to schedule or lead meetings.</span></span>
    
3. <span data-ttu-id="874b3-119">또한 이전 단계에서 라이선스를 할당한 동일한 사용자에게 통신 크레딧 라이선스(비용 없음)를 할당하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="874b3-119">We also recommend that you assign Communications Credits licenses (they don’t cost anything) to the same people you assigned licenses to in the previous step.</span></span> <span data-ttu-id="874b3-120">통신 크레딧을 설정하는 방법을 확인하려면 [조직에 대한 통신 크레딧 설정하기](/microsoftteams/set-up-communications-credits-for-your-organization)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="874b3-120">To learn how to set up Communications Credits, see [Set up Communications Credits for your organization](/microsoftteams/set-up-communications-credits-for-your-organization).</span></span>
    
> [!NOTE]
> <span data-ttu-id="874b3-121">[오디오 회의(분 단위 요금)](/microsoftteams/audio-conferencing-pay-per-minute)를 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="874b3-121">You can also set up [pay-per-minute Audio Conferencing](/microsoftteams/audio-conferencing-pay-per-minute).</span></span>

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a><span data-ttu-id="874b3-122">3단계: 회의 브리지에 대한 서비스 전화번호 받기</span><span class="sxs-lookup"><span data-stu-id="874b3-122">Step 3: Get service numbers for your conferencing bridges</span></span>
<span data-ttu-id="874b3-123"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="874b3-123"><a name="__top"> </a></span></span>

<span data-ttu-id="874b3-124">오디오 회의의 경우 사용자의 전화번호를 사용할 수 없습니다. 서비스 전화번호를 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="874b3-124">For Audio Conferencing, you can’t use phone numbers for users; you will need to get service numbers.</span></span> <span data-ttu-id="874b3-125">회의 브리지에 대한 유료 또는 무료 서비스 전화번호를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="874b3-125">You can get either toll or toll-free service numbers for your conferencing bridges.</span></span> <span data-ttu-id="874b3-126">유료 및 무료 서비스 전화번호를 받는 방법에는 세 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="874b3-126">There are three ways to get toll and toll-free service numbers:</span></span> 
  
- <span data-ttu-id="874b3-127">**관리 비즈니스용 Skype 을 사용하세요.**</span><span class="sxs-lookup"><span data-stu-id="874b3-127">**Use the Skype for Business admin center**.</span></span> <span data-ttu-id="874b3-128">일부 국가/지역의 경우 관리 센터를 사용하여 회의 브리지에 대한 서비스 비즈니스용 Skype 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="874b3-128">For some countries/regions, you can get service numbers for your conferencing bridges using the Skype for Business admin center.</span></span> <span data-ttu-id="874b3-129">[서비스 전화번호 받기](/microsoftteams/getting-service-phone-numbers)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="874b3-129">See [Getting service phone numbers](/microsoftteams/getting-service-phone-numbers).</span></span>
    
- <span data-ttu-id="874b3-130">**기존 서비스 전화번호 포팅하기**</span><span class="sxs-lookup"><span data-stu-id="874b3-130">**Port your existing service numbers**.</span></span> <span data-ttu-id="874b3-131">현재 서비스 공급자 또는 휴대폰 통신사에서 기존 번호를 Microsoft 365 또는 Office 365.</span><span class="sxs-lookup"><span data-stu-id="874b3-131">To port or transfer existing numbers from your current service provider or phone carrier to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="874b3-132">이 작업을 수행 하는 데 도움이 되는 자세한 내용은 [Teams로 전화번호 전송](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) 또는 [조직에 대한 전화번호 관리하기](/microsoftteams/manage-phone-numbers-for-your-organization)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="874b3-132">You can see [Transfer phone numbers to Teams](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) or [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information to help you do this.</span></span>  
  
- <span data-ttu-id="874b3-133">**새 전화 번호를 위한 요청 양식 사용하기**</span><span class="sxs-lookup"><span data-stu-id="874b3-133">**Use a request form for new numbers**.</span></span> <span data-ttu-id="874b3-134">경우에 따라(국가/지역에 따라) 관리 센터를 사용하여 새 서비스 번호를 비즈니스용 Skype 수 없습니다. 또는 특정 전화 번호 또는 지역 코드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="874b3-134">Sometimes (depending on your country/region) you won't be able to get your new service numbers using the Skype for Business admin center, or you will need specific phone numbers or area codes.</span></span> <span data-ttu-id="874b3-135">그럴 경우 양식을 다운로드하여 다시 보내주세요.</span><span class="sxs-lookup"><span data-stu-id="874b3-135">If so, you will need to download a form and send it back to us.</span></span> <span data-ttu-id="874b3-136">자세한 내용은 [조직에서 전화번호 관리하기](/microsoftteams/manage-phone-numbers-for-your-organization)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="874b3-136">See [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information.</span></span> 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a><span data-ttu-id="874b3-137">4단계: 회의 브리지에 서비스 전화번호 할당하기</span><span class="sxs-lookup"><span data-stu-id="874b3-137">Step 4: Assign a service number to the conferencing bridge</span></span>
<span data-ttu-id="874b3-138"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="874b3-138"><a name="__top"> </a></span></span>

<span data-ttu-id="874b3-139">회의 브리지에 대한 유료 및/또는 무료 전화번호를 받으면 모임 초대에 사용할 수 있도록 번호를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="874b3-139">Once you get your toll and/or toll-free phone numbers for your conferencing bridge, you need to assign the numbers so they can be used on meeting invitations.</span></span>  

<span data-ttu-id="874b3-140">오디오 회의 브리지에 새 전화 번호를 할당하는 경우:</span><span class="sxs-lookup"><span data-stu-id="874b3-140">To assign a new phone number to your audio conferencing bridge:</span></span>

<span data-ttu-id="874b3-141">![비즈니스용 skype 로고를 나타내는 아이콘](../images/sfb-logo-30x30.png) **비즈니스용 Skype 관리 센터 사용:**</span><span class="sxs-lookup"><span data-stu-id="874b3-141">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

 1. <span data-ttu-id="874b3-142">**Microsoft 365 관리 센터** > **관리 센터** > **Teams** > **레거시 포털** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="874b3-142">Go to the **Microsoft 365 admin center** > **Admin centers** > **Teams** > **Legacy portal**.</span></span>
 2. <span data-ttu-id="874b3-143">**음성** > **전화번호** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="874b3-143">Select **Voice** > **Phone numbers**.</span></span>
 3. <span data-ttu-id="874b3-144">전화번호를 선택하고, **할당** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="874b3-144">Select the phone number, and click **Assign**.</span></span>

<span data-ttu-id="874b3-145">자세한 내용은 오디오 회의 브리지의 전화 번호 [변경을 참조합니다.](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge)</span><span class="sxs-lookup"><span data-stu-id="874b3-145">For more details, see [Change the phone numbers on your audio conferencing bridge](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).</span></span>

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a><span data-ttu-id="874b3-146">5단계: 회의 브리지의 기본 및 대체 언어 설정하기</span><span class="sxs-lookup"><span data-stu-id="874b3-146">Step 5: Set the default and alternate languages for a conferencing bridge</span></span>
<span data-ttu-id="874b3-147"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="874b3-147"><a name="__top"> </a></span></span>

<span data-ttu-id="874b3-148">다음으로, 회의 [](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md) 자동 참석자가 오디오 회의를 위해 전화 번호로 전화 접속할 때 전화를 걸 때 회의 자동 참석자가 사용하는 자동 참석 언어를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="874b3-148">Next, you want to [Set auto attendant languages for Audio Conferencing](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md) that the conferencing auto attendant uses to greet callers when they dial in to a phone number for Audio Conferencing.</span></span> 

<span data-ttu-id="874b3-149">![Microsoft Teams 로고를 나타내는 아이콘](../images/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**:</span><span class="sxs-lookup"><span data-stu-id="874b3-149">![An icon showing the Microsoft Teams logo](../images/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="874b3-150">대시보드에서 **모임** > **회의 브리지** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="874b3-150">From the Dashboard, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="874b3-151">회의 브리지 전화번호를 선택하고 **편집** 을 클릭한 다음 기본 언어를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="874b3-151">Select the conferencing bridge phone number, click **Edit**, and then choose the default language.</span></span>

<span data-ttu-id="874b3-152">![관리 센터를 사용하여 비즈니스용 Skype ](../images/sfb-logo-30x30.png) **로고를 비즈니스용 Skype 아이콘:**</span><span class="sxs-lookup"><span data-stu-id="874b3-152">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**:</span></span>

1. <span data-ttu-id="874b3-153">관리 센터 > **관리** 센터 Teams  >    >  **로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="874b3-153">Go to the admin center > **Admin centers** > **Teams** > **Legacy portal**.</span></span>
2. <span data-ttu-id="874b3-154">오디오 회의 Microsoft   >  **브리지를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="874b3-154">Select **Audio conferencing** > **Microsoft bridge**.</span></span> 
3. <span data-ttu-id="874b3-155">회의 브리지 전화 번호를 선택하고 언어 설정을 **선택한** 다음 기본 언어를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="874b3-155">Select the conferencing bridge phone number, select **Set languages**, and then choose the default language.</span></span>

## <a name="step-6-set-your-conferencing-bridge-settings"></a><span data-ttu-id="874b3-156">6단계: 회의 브리지 설정 확인하기</span><span class="sxs-lookup"><span data-stu-id="874b3-156">Step 6: Set your conferencing bridge settings</span></span>
<span data-ttu-id="874b3-157"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="874b3-157"><a name="__top"> </a></span></span>
    
<span data-ttu-id="874b3-158">회의 브리지를 설정한 후에는 입력/종료 알림과 PIN 길이와 같은 기본 설정이 사용하려는 설정인지 확인합니다. 사용하려는 설정이 아니라면 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="874b3-158">After setting up your conferencing bridge, verify that the default settings such as entry/exit notifications and PIN length are the ones you want to use; if they're not, you can change them.</span></span> 

<span data-ttu-id="874b3-159">![Microsoft Teams 로고를 나타내는 아이콘](../images/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**:</span><span class="sxs-lookup"><span data-stu-id="874b3-159">![An icon showing the Microsoft Teams logo](../images/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="874b3-160">대시보드에서 **모임** > **회의 브리지** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="874b3-160">From the Dashboard, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="874b3-161">**브리지 설정** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="874b3-161">Select **Bridge settings**.</span></span> <span data-ttu-id="874b3-162">그러면 **브리지 설정** 창이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="874b3-162">This will open the **Bridge settings** pane.</span></span> 

<span data-ttu-id="874b3-163">자세한 내용은 [오디오 회의 브리지의 설정 변경하기](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="874b3-163">For more details, see [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>

<span data-ttu-id="874b3-164">![비즈니스용 skype 로고를 나타내는 아이콘](../images/sfb-logo-30x30.png) **비즈니스용 Skype 관리 센터 사용:**</span><span class="sxs-lookup"><span data-stu-id="874b3-164">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

1. <span data-ttu-id="874b3-165">**Microsoft 365 관리 센터** > **관리 센터** > **Teams** > **레거시 포털** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="874b3-165">Go to the **Microsoft 365 admin center** > **Admin centers** > **Teams** > **Legacy portal**.</span></span>
2. <span data-ttu-id="874b3-166">오디오 **회의** Microsoft 브리지 설정을  >  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="874b3-166">Select **Audio conferencing** > **Microsoft bridge settings**.</span></span> <span data-ttu-id="874b3-167">그러면 Microsoft 브리지 **설정 페이지가 열립니다.**</span><span class="sxs-lookup"><span data-stu-id="874b3-167">This will open the **Microsoft bridge settings** page.</span></span> 

<span data-ttu-id="874b3-168">자세한 내용은 [오디오 회의 브리지의 설정 변경하기](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="874b3-168">For more details, see [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a><span data-ttu-id="874b3-169">7단계: 모임을 진행하는 사용자에게 전화 접속 번호 할당하기</span><span class="sxs-lookup"><span data-stu-id="874b3-169">Step 7: Assign dial-in phone numbers for users who lead meetings</span></span>

<span data-ttu-id="874b3-170">오디오 회의 브리지를 만든 후에는 사용자를 위해 유료 및 무료 전화번호를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="874b3-170">After you have created an Audio Conferencing bridge, you need to set the toll and toll-free numbers for your users.</span></span>

<span data-ttu-id="874b3-171">모임을 진행하거나 예약하는 조직의 모든 사용자를 위해 이 작업을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="874b3-171">You will need to do this for all of the people in your organization who lead or schedule meetings.</span></span> 

<span data-ttu-id="874b3-172">![Microsoft Teams 로고를 나타내는 아이콘](../images/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**:</span><span class="sxs-lookup"><span data-stu-id="874b3-172">![An icon showing the Microsoft Teams logo](../images/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="874b3-173">대시보드에서 **사용자** 를 클릭하고 목록에서 사용자를 선택한 다음 **편집** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="874b3-173">From the Dashboard, click **Users**, select the user from the list, and select **Edit**.</span></span>
2. <span data-ttu-id="874b3-174">**오디오 회의** 옆의 **편집** 을 선택한 다음 **오디오 회의** 창에서 **유료 전화번호** 및 **무료** 전화번호 목록에서 번호를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="874b3-174">Select **Edit** next to **Audio Conferencing**, and then in the **Audio Conferencing** pane, choose a number in the **Toll number** and **Toll-free** number lists.</span></span>

<span data-ttu-id="874b3-175">![비즈니스용 skype 로고를 나타내는 아이콘](../images/sfb-logo-30x30.png) **비즈니스용 Skype 관리 센터 사용:**</span><span class="sxs-lookup"><span data-stu-id="874b3-175">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

1. <span data-ttu-id="874b3-176">레거시 **Microsoft 365 관리 센터**  >  **Teams** 로  >  **이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="874b3-176">Go to the **Microsoft 365 admin center** > **Teams** > **Legacy portal**.</span></span>
2. <span data-ttu-id="874b3-177">오디오 **회의** 사용자를 선택한 다음 목록에서 사용자를 선택하고  >   **편집을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="874b3-177">Select **Audio conferencing** > **Users**, and then select the user from the list and click **Edit**.</span></span> 

<span data-ttu-id="874b3-178">자세한 내용은 [Microsoft를 오디오 회의 공급자로 지정하기](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="874b3-178">If you need more details, see [Assign Microsoft as the audio conferencing provider](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md).</span></span>


## <a name="step-8-set-up-meeting-invitations-optional"></a><span data-ttu-id="874b3-179">8단계: 모임 초대 설정하기(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="874b3-179">Step 8: Set up meeting invitations (optional)</span></span>
<span data-ttu-id="874b3-180"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="874b3-180"><a name="__top"> </a></span></span>
 
<span data-ttu-id="874b3-181">사용자에게 설정되는 전화 접속 번호는 모임 참석자에게 보내지는 모임 초대에 자동으로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="874b3-181">The dial-in numbers that are set for the user will be automatically added to the meeting invitations that are sent to meeting attendees.</span></span> <span data-ttu-id="874b3-182">그러나 원하는 경우 자체 도움말 및 법적인 링크, 문자 메시지 및 작은 회사 그래픽을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="874b3-182">However, you can add your own help and legal links, a text message, and small company graphic if you want.</span></span> <span data-ttu-id="874b3-183">[모임 초대 사용자 지정하기](../set-up-skype-for-business-online/customize-meeting-invitations.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="874b3-183">See [Customize meeting invitations](../set-up-skype-for-business-online/customize-meeting-invitations.md).</span></span>
   
## <a name="related-topics"></a><span data-ttu-id="874b3-184">관련 항목</span><span class="sxs-lookup"><span data-stu-id="874b3-184">Related topics</span></span>

[<span data-ttu-id="874b3-185">오디오 회의 일반적인 질문</span><span class="sxs-lookup"><span data-stu-id="874b3-185">Audio Conferencing common questions</span></span>](/MicrosoftTeams/audio-conferencing-common-questions)
  
[<span data-ttu-id="874b3-186">비즈니스용 Skype 온라인 설정</span><span class="sxs-lookup"><span data-stu-id="874b3-186">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[<span data-ttu-id="874b3-187">오디오 회의의 전화 번호</span><span class="sxs-lookup"><span data-stu-id="874b3-187">Phone numbers for Audio Conferencing</span></span>](phone-numbers-for-audio-conferencing.md)
  
[<span data-ttu-id="874b3-188">온라인 모임 및 전화 회의에 대한 옵션 설정하기</span><span class="sxs-lookup"><span data-stu-id="874b3-188">Set options for online meetings and conference calls</span></span>](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
