---
title: Microsoft Teams용 오디오 회의 설정하기
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
description: '전화를 사용하여 전화 회의에 참여해야 하는 회사의 사용자를 위해 전화 접속 또는 오디오 회의를 설정하는 방법을 알아봅니다. '
ms.openlocfilehash: e14cf924d039b461df3fc84d7b600d96d515be58
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41838068"
---
# <a name="set-up-audio-conferencing-for-microsoft-teams"></a><span data-ttu-id="ee59f-103">Microsoft Teams용 오디오 회의 설정하기</span><span class="sxs-lookup"><span data-stu-id="ee59f-103">Set up Audio Conferencing for Microsoft Teams</span></span>

<span data-ttu-id="ee59f-104">경우에 따라 조직의 사용자가 전화를 사용하여 모임에 전화해야 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee59f-104">Sometimes people in your organization will need to use a phone to call in to a meeting.</span></span> <span data-ttu-id="ee59f-105">Microsoft Teams에는 이런 상황에 대한 오디오 회의 기능이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee59f-105">Microsoft Teams includes the audio conferencing feature for just this situation!</span></span> <span data-ttu-id="ee59f-106">사용자는 모바일 장치 또는 PC에서 Microsoft Teams 앱을 사용하는 대신 전화를 사용하여 모임에 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee59f-106">People can call in to Teams meetings using a phone, instead of using the Teams app on a mobile device or PC.</span></span> 
  
<span data-ttu-id="ee59f-107">모임 일정을 계획하거나 주도하는 사용자들을 위해 오디오 회의를 설정하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ee59f-107">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings.</span></span> <span data-ttu-id="ee59f-108">전화를 거는 모임 참석자는 자신에게 할당된 라이선스 혹은 그 외 설정이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ee59f-108">Meeting attendees who dial in don't need any licenses assigned to them or other setup.</span></span>
  
<span data-ttu-id="ee59f-109">오디오 회의에 대한 질문과 대답을 확인하려면 [오디오 회의에 대한 일반적인 질문](audio-conferencing-common-questions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ee59f-109">For frequently asked questions about Audio Conferencing, see [Audio Conferencing common questions](audio-conferencing-common-questions.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a><span data-ttu-id="ee59f-110">1단계: 사용자의 국가/지역에서 오디오 회의를 사용할 수 있는지 확인하기</span><span class="sxs-lookup"><span data-stu-id="ee59f-110">Step 1: Find out if Audio Conferencing is available in your country/region</span></span>
<span data-ttu-id="ee59f-111"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="ee59f-111"><a name="__top"> </a></span></span>

<span data-ttu-id="ee59f-112">[오디오 회의 및 통화 플랜의 국가 및 지역 가용성](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)으로 이동하고 해당 국가나 지역을 선택하여 전화 시스템, 통화 플랜, 유료 및 무료 전화번호, 통신 크레딧에 대한 정보뿐만 아니라 오디오 회의에 대한 가용성 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee59f-112">Go to [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) and select your country or region to get availability information about Audio Conferencing, as well as information about Phone System, Calling Plans, toll and toll-free numbers, and Communications Credits.</span></span> 
 
## <a name="step-2-get-and-assign-licenses"></a><span data-ttu-id="ee59f-113">2단계: 라이선스 받기 및 할당하기</span><span class="sxs-lookup"><span data-stu-id="ee59f-113">Step 2: Get and assign licenses</span></span>
 
1. <span data-ttu-id="ee59f-114">오디오 회의를 위해서는 전화 접속 모임을 설정할 각 사용자에 대한 라이선스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ee59f-114">For Audio Conferencing, you need a license for each user who will set up dial-in meetings.</span></span> <span data-ttu-id="ee59f-115">오디오 회의를 위해 구입해야 하는 라이선스와 비용에 대한 자세한 내용은 [Microsoft Teams 추가 기능 라이선스](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ee59f-115">To learn which licenses you need to buy for Audio Conferencing and how much they will cost, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

    >[!NOTE] 
    > <span data-ttu-id="ee59f-116">오디오 회의는 Office 365 Enterprise E5 라이선스에 추가 기능으로 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee59f-116">Audio Conferencing is included in Office 365 Enterprise E5 licenses and as an add-on.</span></span>
        
2. <span data-ttu-id="ee59f-117">오디오 회의 라이선스를 구입한 후에는 모임을 예약하거나 진행할 조직의 사용자에게 라이선스를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee59f-117">After you buy the Audio Conferencing licenses, you will need to assign them to those people in your organization who are going to schedule or lead meetings.</span></span> <span data-ttu-id="ee59f-118">구매한 라이선스를 모임을 예약하거나 진행할 조직의 사용자에게 할당하려면 [비즈니스용 Office 365에서 사용자에게 라이선스 할당하기](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ee59f-118">See [Assign licenses to users in Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) you purchased to the people in your organization who are going to schedule or lead meetings.</span></span>
    
3. <span data-ttu-id="ee59f-119">또한 이전 단계에서 라이선스를 할당한 동일한 사용자에게 통신 크레딧 라이선스(비용 없음)를 할당하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ee59f-119">We also recommend that you assign Communications Credits licenses (they don’t cost anything) to the same people you assigned licenses to in the previous step.</span></span> <span data-ttu-id="ee59f-120">통신 크레딧을 설정하는 방법을 확인하려면 [조직에 대한 통신 크레딧 설정하기](set-up-communications-credits-for-your-organization.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ee59f-120">To learn how to set up Communications Credits, see [Set up Communications Credits for your organization](set-up-communications-credits-for-your-organization.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="ee59f-121">[오디오 회의(분 단위 요금)](audio-conferencing-pay-per-minute.md)를 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee59f-121">You can also set up [pay-per-minute Audio Conferencing](audio-conferencing-pay-per-minute.md).</span></span>

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a><span data-ttu-id="ee59f-122">3단계: 회의 브리지에 대한 서비스 전화번호 받기</span><span class="sxs-lookup"><span data-stu-id="ee59f-122">Step 3: Get service numbers for your conferencing bridges</span></span>
<span data-ttu-id="ee59f-123"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="ee59f-123"><a name="__top"> </a></span></span>

<span data-ttu-id="ee59f-124">오디오 회의의 경우 사용자의 전화번호를 사용할 수 없습니다. 서비스 전화번호를 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee59f-124">For Audio Conferencing, you can’t use phone numbers for users; you will need to get service numbers.</span></span> <span data-ttu-id="ee59f-125">회의 브리지에 대한 유료 또는 무료 서비스 전화번호를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee59f-125">You can get either toll or toll-free service numbers for your conferencing bridges.</span></span> <span data-ttu-id="ee59f-126">유료 및 무료 서비스 전화번호를 받는 방법에는 세 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee59f-126">There are three ways to get toll and toll-free service numbers:</span></span> 
  
- <span data-ttu-id="ee59f-127">**Microsoft Teams 관리 센터 사용하기**</span><span class="sxs-lookup"><span data-stu-id="ee59f-127">**Use the Microsoft Teams admin center**.</span></span> <span data-ttu-id="ee59f-128">일부 국가/지역의 경우 Microsoft Teams 관리 센터를 사용하여 회의 브리지의 서비스 전화번호를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee59f-128">For some countries/regions, you can get service numbers for your conferencing bridges using the Microsoft Teams admin center.</span></span> <span data-ttu-id="ee59f-129">[서비스 전화번호 받기](/microsoftteams/getting-service-phone-numbers)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ee59f-129">See [Getting service phone numbers](/microsoftteams/getting-service-phone-numbers).</span></span>
    
- <span data-ttu-id="ee59f-130">**기존 서비스 전화번호 포팅하기**</span><span class="sxs-lookup"><span data-stu-id="ee59f-130">**Port your existing service numbers**.</span></span> <span data-ttu-id="ee59f-131">기존 전화번호를 현재 서비스 공급자 또는 전화 캐리어에서 Office 365로 포팅하거나 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="ee59f-131">To port or transfer existing numbers from your current service provider or phone carrier to Office 365.</span></span> <span data-ttu-id="ee59f-132">이 작업을 수행 하는 데 도움이 되는 자세한 내용은 [Teams로 전화번호 전송](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) 또는 [조직에 대한 전화번호 관리하기](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ee59f-132">You can see [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) or [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) for more information to help you do this.</span></span>  
  
- <span data-ttu-id="ee59f-133">**새 전화 번호를 위한 요청 양식 사용하기**</span><span class="sxs-lookup"><span data-stu-id="ee59f-133">**Use a request form for new numbers**.</span></span> <span data-ttu-id="ee59f-134">경우에 따라(국가/지역에 따라) Microsoft Teams 관리 센터를 사용하여 새 서비스 전화번호를 받을 수 없거나 특정 전화번호 또는 지역 코드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ee59f-134">Sometimes (depending on your country/region) you won't be able to get your new service numbers using the Microsoft Teams admin center, or you will need specific phone numbers or area codes.</span></span> <span data-ttu-id="ee59f-135">그럴 경우 양식을 다운로드하여 다시 보내주세요.</span><span class="sxs-lookup"><span data-stu-id="ee59f-135">If so, you will need to download a form and send it back to us.</span></span> <span data-ttu-id="ee59f-136">자세한 내용은 [조직에서 전화번호 관리하기](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ee59f-136">See [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) for more information.</span></span> 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a><span data-ttu-id="ee59f-137">4단계: 회의 브리지에 서비스 전화번호 할당하기</span><span class="sxs-lookup"><span data-stu-id="ee59f-137">Step 4: Assign a service number to the conferencing bridge</span></span>
<span data-ttu-id="ee59f-138"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="ee59f-138"><a name="__top"> </a></span></span>

<span data-ttu-id="ee59f-139">회의 브리지에 대한 유료 및/또는 무료 전화번호를 받으면 모임 초대에 사용할 수 있도록 번호를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee59f-139">Once you get your toll and/or toll-free phone numbers for your conferencing bridge, you need to assign the numbers so they can be used on meeting invitations.</span></span>  

<span data-ttu-id="ee59f-140">다음 단계에 따라 오디오 회의 브리지에 새 전화번호를 할당하세요.</span><span class="sxs-lookup"><span data-stu-id="ee59f-140">Follow these steps to assign a new phone number to your audio conferencing bridge.</span></span>

<span data-ttu-id="ee59f-141">![비즈니스용 skype 로고를 나타내는 아이콘](media/sfb-logo-30x30.png) **비즈니스용 Skype 관리 센터 사용:**</span><span class="sxs-lookup"><span data-stu-id="ee59f-141">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

 1. <span data-ttu-id="ee59f-142">**Microsoft 365 관리 센터** > **관리 센터** > **Teams** > **레거시 포털**로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="ee59f-142">Go to the **Microsoft 365 admin center** > **Admin centers** > **Teams** > **Legacy portal**.</span></span>
 2. <span data-ttu-id="ee59f-143">**음성** > **전화번호**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ee59f-143">Select **Voice** > **Phone numbers**.</span></span>
 3. <span data-ttu-id="ee59f-144">전화번호를 선택하고, **할당**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ee59f-144">Select the phone number, and click **Assign**.</span></span>

<span data-ttu-id="ee59f-145">자세한 내용은 [오디오 회의 브리지에서 전화번호 변경하기](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ee59f-145">For more details, see [Change the phone numbers on your Audio Conferencing bridge](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span></span>

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a><span data-ttu-id="ee59f-146">5단계: 회의 브리지의 기본 및 대체 언어 설정하기</span><span class="sxs-lookup"><span data-stu-id="ee59f-146">Step 5: Set the default and alternate languages for a conferencing bridge</span></span>
<span data-ttu-id="ee59f-147"><a name="__top"> </a> 다음으로, [Microsoft Teams에서 오디오 회의에 대한 자동 전화 교환 언어를 설정](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)하려고 합니다. 이는 회의 자동 전화 교환에서 오디오 회의를 위해 전화번호로 전화를 걸 때 발신자에게 인사하는 데 사용하는 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="ee59f-147"><a name="__top"> </a> Next, you want to [Set auto attendant languages for Audio Conferencing in Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md) that the conferencing auto attendant uses to greet callers when they dial in to a phone number for Audio Conferencing.</span></span> 

<span data-ttu-id="ee59f-148">![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**:</span><span class="sxs-lookup"><span data-stu-id="ee59f-148">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="ee59f-149">대시보드에서 **모임** > **회의 브리지**로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="ee59f-149">From the Dashboard, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="ee59f-150">회의 브리지 전화번호를 선택하고 **편집**을 클릭한 다음 기본 언어를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ee59f-150">Select the conferencing bridge phone number, click **Edit**, and then choose the default language.</span></span>

## <a name="step-6-set-your-conferencing-bridge-settings"></a><span data-ttu-id="ee59f-151">6단계: 회의 브리지 설정 확인하기</span><span class="sxs-lookup"><span data-stu-id="ee59f-151">Step 6: Set your conferencing bridge settings</span></span>
<span data-ttu-id="ee59f-152"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="ee59f-152"><a name="__top"> </a></span></span>
    
<span data-ttu-id="ee59f-153">회의 브리지를 설정한 후에는 입력/종료 알림과 PIN 길이와 같은 기본 설정이 사용하려는 설정인지 확인합니다. 사용하려는 설정이 아니라면 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee59f-153">After setting up your conferencing bridge, verify that the default settings such as entry/exit notifications and PIN length are the ones you want to use; if they're not, you can change them.</span></span> 

<span data-ttu-id="ee59f-154">![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**:</span><span class="sxs-lookup"><span data-stu-id="ee59f-154">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="ee59f-155">대시보드에서 **모임** > **회의 브리지**로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="ee59f-155">From the Dashboard, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="ee59f-156">**브리지 설정**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ee59f-156">Select **Bridge settings**.</span></span> <span data-ttu-id="ee59f-157">그러면 **브리지 설정** 창이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="ee59f-157">This will open the **Bridge settings** pane.</span></span> 

<span data-ttu-id="ee59f-158">자세한 내용은 [오디오 회의 브리지의 설정 변경하기](change-the-settings-for-an-audio-conferencing-bridge.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ee59f-158">For more details, see [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a><span data-ttu-id="ee59f-159">7단계: 모임을 진행하는 사용자에게 전화 접속 번호 할당하기</span><span class="sxs-lookup"><span data-stu-id="ee59f-159">Step 7: Assign dial-in phone numbers for users who lead meetings</span></span>

<span data-ttu-id="ee59f-160">오디오 회의 브리지를 만든 후에는 사용자를 위해 유료 및 무료 전화번호를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee59f-160">After you have created an Audio Conferencing bridge, you need to set the toll and toll-free numbers for your users.</span></span>

<span data-ttu-id="ee59f-161">모임을 진행하거나 예약하는 조직의 모든 사용자를 위해 이 작업을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee59f-161">You will need to do this for all of the people in your organization who lead or schedule meetings.</span></span> 

<span data-ttu-id="ee59f-162">![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**:</span><span class="sxs-lookup"><span data-stu-id="ee59f-162">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="ee59f-163">대시보드에서 **사용자**를 클릭하고 목록에서 사용자를 선택한 다음 **편집**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ee59f-163">From the Dashboard, click **Users**, select the user from the list, and select **Edit**.</span></span>
2. <span data-ttu-id="ee59f-164">**오디오 회의** 옆의 **편집**을 선택한 다음 **오디오 회의** 창에서 **유료 전화번호** 및 **무료** 전화번호 목록에서 번호를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ee59f-164">Select **Edit** next to **Audio Conferencing**, and then in the **Audio Conferencing** pane, choose a number in the **Toll number** and **Toll-free** number lists.</span></span>

<span data-ttu-id="ee59f-165">자세한 내용은 [Microsoft를 오디오 회의 공급자로 지정하기](/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ee59f-165">If you need more details, see [Assign Microsoft as the audio conferencing provider](/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span></span>


## <a name="step-8-set-up-meeting-invitations-optional"></a><span data-ttu-id="ee59f-166">8단계: 모임 초대 설정하기(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="ee59f-166">Step 8: Set up meeting invitations (optional)</span></span>
<span data-ttu-id="ee59f-167"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="ee59f-167"><a name="__top"> </a></span></span>
 
<span data-ttu-id="ee59f-168">사용자에게 설정되는 전화 접속 번호는 모임 참석자에게 보내지는 모임 초대에 자동으로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="ee59f-168">The dial-in numbers that are set for the user will be automatically added to the meeting invitations that are sent to meeting attendees.</span></span> <span data-ttu-id="ee59f-169">그러나 원하는 경우 자체 도움말 및 법적인 링크, 문자 메시지 및 작은 회사 그래픽을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee59f-169">However, you can add your own help and legal links, a text message, and small company graphic if you want.</span></span> <span data-ttu-id="ee59f-170">[모임 초대 사용자 지정하기](meeting-settings-in-teams.md#customize-meeting-invitations)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ee59f-170">See [Customize meeting invitations](meeting-settings-in-teams.md#customize-meeting-invitations).</span></span>
   
## <a name="related-topics"></a><span data-ttu-id="ee59f-171">관련 항목</span><span class="sxs-lookup"><span data-stu-id="ee59f-171">Related topics</span></span>

[<span data-ttu-id="ee59f-172">오디오 회의 일반적인 질문</span><span class="sxs-lookup"><span data-stu-id="ee59f-172">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
  
[<span data-ttu-id="ee59f-173">Microsoft Teams에서 오디오 회의를 위한 전화번호</span><span class="sxs-lookup"><span data-stu-id="ee59f-173">Phone numbers for Audio Conferencing in Microsoft Teams</span></span>](phone-numbers-for-audio-conferencing-in-teams.md)
  
[<span data-ttu-id="ee59f-174">온라인 모임 및 전화 회의에 대한 옵션 설정하기</span><span class="sxs-lookup"><span data-stu-id="ee59f-174">Set options for online meetings and conference calls</span></span>](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
