---
title: 조직에서 전화 시스템 설정
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: makolomi
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- m365solution-voice
- m365solution-scenario
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-apr2020
description: Microsoft 365 또는 Office 365에서 조직에 대해 전화 시스템(클라우드 PBX)을 설정하는 방법을 자세히 설명하는 단계별 가이드입니다.
ms.openlocfilehash: c00b628716a54adcb19c3dd1f00e8e9e2b6f4c40
ms.sourcegitcommit: 380a96f1ed2cefb429286854f06546bdb28d7d74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701216"
---
# <a name="set-up-phone-system-in-your-organization"></a><span data-ttu-id="91aaa-103">조직에서 전화 시스템 설정</span><span class="sxs-lookup"><span data-stu-id="91aaa-103">Set up Phone System in your organization</span></span>

<span data-ttu-id="91aaa-104">다음은 Microsoft 365 또는 Office 365에서 전화 시스템을 설정하기 위한 단계별 가이드입니다.</span><span class="sxs-lookup"><span data-stu-id="91aaa-104">The following is a step-by-step guide for setting up Phone System in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="91aaa-105">자세한 추가 정보에 대한 링크는 각 단계의 끝에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91aaa-105">Links to additional, detailed information are available at the end of each step.</span></span>

## <a name="step-1-make-sure-that-phone-system-is-available-in-your-country-or-region"></a><span data-ttu-id="91aaa-106">1단계: 전화 시스템을 해당 국가 또는 지역에서 사용할 수 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="91aaa-106">Step 1: Make sure that Phone System is available in your country or region</span></span>

1.    <span data-ttu-id="91aaa-107">먼저 오디오 회의 및 통화 요금제에 대한 국가 및 지역 가용성으로 이동하고 [페이지](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)맨 위에 있는 목록에서 국가 또는 지역을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="91aaa-107">First go to [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md), and select your country or region from the list at the top of the page.</span></span> 
2.    <span data-ttu-id="91aaa-108">전화 **시스템 아래에서** 기능 및 세부 정보 목록을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="91aaa-108">Under **Phone System**, review the list of features and details.</span></span> 
3.    <span data-ttu-id="91aaa-109">전화 시스템을 사용할 수 있는 경우 2단계로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="91aaa-109">If Phone System is available, go to step 2.</span></span> 

## <a name="step-2-buy-and-assign-phone-system-and-calling-plan-licenses"></a><span data-ttu-id="91aaa-110">2단계: 전화 시스템 및 통화 요금제 라이선스 구입 및 할당</span><span class="sxs-lookup"><span data-stu-id="91aaa-110">Step 2: Buy and assign Phone System and Calling Plan licenses</span></span>

<span data-ttu-id="91aaa-111">단일 사용자에게 전화 시스템 및 통화 요금제 라이선스를 할당하는 단계는 Microsoft 365 또는 Office 365 라이선스를 할당하는 단계와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="91aaa-111">To assign a Phone System and Calling Plan license to a single user, the steps are the same as assigning a Microsoft 365 or Office 365 license.</span></span>  <span data-ttu-id="91aaa-112">여러 사용자에게 라이선스를 일괄 할당할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91aaa-112">You can also assign licenses to multiple users in bulk.</span></span> <span data-ttu-id="91aaa-113">자세한 내용은 Microsoft Teams 추가 기능 라이선스 [할당을 참조하세요.](teams-add-on-licensing/assign-teams-add-on-licenses.md)</span><span class="sxs-lookup"><span data-stu-id="91aaa-113">For more information, see [Assign Microsoft Teams add-on licenses](teams-add-on-licensing/assign-teams-add-on-licenses.md).</span></span>

<span data-ttu-id="91aaa-114">해당 국가 또는 지역에서 통화 요금제가 제공되지 않는 경우 직접 라우팅을 사용하여 전화 시스템에 On-프레미스 전화 통신 인프라를 연결하는 것을 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="91aaa-114">If Calling Plans are not available for your country or region, consider using Direct Routing to connect your on-premises telephony infrastructure to Phone System.</span></span>  <span data-ttu-id="91aaa-115">자세한 내용은 전화 시스템 직접 [라우팅을 참조하세요.](direct-routing-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="91aaa-115">For more information, see [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

## <a name="step-3-get-phone-numbers-for-your-users"></a><span data-ttu-id="91aaa-116">3단계: 사용자의 전화 번호 확인</span><span class="sxs-lookup"><span data-stu-id="91aaa-116">Step 3: Get phone numbers for your users</span></span>

<span data-ttu-id="91aaa-117">조직에서 전화를 걸고 받을 사용자를 설정하려면 먼저 해당 사용자의 전화 번호를 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91aaa-117">Before you can set up users in your organization to make and receive phone calls, you must get phone numbers for them.</span></span>

<span data-ttu-id="91aaa-118">다음 세 가지 방법으로 사용자에 대한 번호를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91aaa-118">You have three ways of getting numbers for your users:</span></span>
- <span data-ttu-id="91aaa-119">Teams 관리 센터를 사용하여 새 번호를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="91aaa-119">Get new numbers using the Teams admin center.</span></span>
- <span data-ttu-id="91aaa-120">Teams 관리 센터에서 사용할 수 없는 새 번호를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="91aaa-120">Get new numbers that aren't available in the Teams admin center.</span></span>
- <span data-ttu-id="91aaa-121">현재 서비스 공급자 또는 통신 사업자에서 Microsoft 365 또는 Office 365로 기존 번호를 포터하거나 이전합니다.</span><span class="sxs-lookup"><span data-stu-id="91aaa-121">Port or transfer your existing numbers from your current service provider or phone carrier to Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="91aaa-122">숫자 추가  페이지를 사용하여 해당 번호를 보고, 검색하고, 획득하고, 예약해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91aaa-122">You must use the **Add numbers** page to see, search, acquire, and reserve those numbers.</span></span> <span data-ttu-id="91aaa-123">국가/지역, 주 및 구/시/별로 검색한 다음 사용자에게 필요한 전화 번호 수를 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91aaa-123">You can search by Country/Region, State, and City, and then enter the number of phone numbers you will need for your users.</span></span>

### <a name="get-new-user-phone-numbers-using-the-teams-admin-center"></a><span data-ttu-id="91aaa-124">Teams 관리 센터를 사용하여 새 사용자 전화 번호 얻기</span><span class="sxs-lookup"><span data-stu-id="91aaa-124">Get new user phone numbers using the Teams admin center</span></span>

1. <span data-ttu-id="91aaa-125">직장 또는 학교 계정으로 Microsoft 365에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="91aaa-125">Sign in to Microsoft 365 with your work or school account.</span></span>

2. <span data-ttu-id="91aaa-126">Teams 관리 **센터로 이동**</span><span class="sxs-lookup"><span data-stu-id="91aaa-126">Go to the **Teams admin center**.</span></span>
    
3. <span data-ttu-id="91aaa-127">왼쪽 탐색 모음에서 **음성** 전화 번호로 이동하고 추가를 클릭한 다음  >  프롬프트를 따르습니다. </span><span class="sxs-lookup"><span data-stu-id="91aaa-127">In the left navigation go to **Voice** > **Phone numbers**, click **Add**, and then follow the prompts.</span></span>
    
### <a name="get-new-numbers-that-arent-available-in-the-teams-admin-center"></a><span data-ttu-id="91aaa-128">Teams 관리 센터에서 사용할 수 없는 새 번호 다운로드</span><span class="sxs-lookup"><span data-stu-id="91aaa-128">Get new numbers that aren't available in the Teams admin center</span></span>
  
<span data-ttu-id="91aaa-129">경우에 따라(국가/지역에 따라) Teams 관리 센터를 사용하여 새 번호를 얻을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="91aaa-129">Sometimes (depending on your country/region) you won't be able to get your new numbers using the Teams admin center.</span></span> <span data-ttu-id="91aaa-130">이 경우 양식을 다운로드하여 다시 보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91aaa-130">In this case, you'll need to download a form and send it back to us.</span></span> <span data-ttu-id="91aaa-131">새 사용자 번호를 요청하는 방법에 대한 자세한 내용은 조직의 전화 번호 [관리를 참조합니다.](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)</span><span class="sxs-lookup"><span data-stu-id="91aaa-131">To learn how to request new user numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).</span></span>   
  
### <a name="port-or-transfer-phone-numbers-from-your-service-provider-or-phone-carrier"></a><span data-ttu-id="91aaa-132">서비스 공급자 또는 통신 사업자로부터 전화 번호 포트 또는 이전</span><span class="sxs-lookup"><span data-stu-id="91aaa-132">Port or transfer phone numbers from your service provider or phone carrier</span></span>
  
- <span data-ttu-id="91aaa-133">사용자에게 999개 이하의 전화 번호가 필요한 경우 Teams 관리 센터에서 새 로컬 번호 포트 **주문** 마법사를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91aaa-133">If you need 999 or fewer phone numbers for your users, you can use the **New Local Number Port Order** wizard in the Teams admin center.</span></span> <span data-ttu-id="91aaa-134">전화 번호 전송에 있는 단계를 따라 [Teams로](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) 전화 번호를 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="91aaa-134">Follow the steps found in [Transfer phone numbers to  Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) to transfer your phone numbers.</span></span>
    
- <span data-ttu-id="91aaa-135">999개가 넘게 전화 번호를 포식해야 하는 경우 조직의 전화 번호 관리를 참조하여 포트 주문 서비스 요청 또는 주문을 제출합니다. [](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)</span><span class="sxs-lookup"><span data-stu-id="91aaa-135">If you need to port more than 999 phone numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) to submit a port order service request or order.</span></span> 

<span data-ttu-id="91aaa-136">새 전화 번호를 옮기거나 기존 번호를 이전하는 자세한 내용은 조직의 전화 번호 관리를 [참조하세요.](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)</span><span class="sxs-lookup"><span data-stu-id="91aaa-136">For detailed information about getting new phone numbers or transferring existing numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).</span></span>

## <a name="step-4-get-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a><span data-ttu-id="91aaa-137">4단계: 서비스 전화 번호(오디오 회의, 통화 큐, 자동 전화 회의)</span><span class="sxs-lookup"><span data-stu-id="91aaa-137">Step 4: Get service phone numbers (audio conferencing, call queues, auto attendants)</span></span>

<span data-ttu-id="91aaa-138">Microsoft 365 또는 Office 365에서 사용자의 전화 번호를 확보하는 것 외에도 오디오 회의(전화 회의용), 자동 전화 회의 및 통화 큐와 같은 서비스에 대한 무료 전화 번호를 검색하고 획득할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91aaa-138">In addition to getting phone numbers for your users from Microsoft 365 or Office 365, you can search and acquire toll or toll-free phone numbers for services such as audio conferencing (for conference bridges), auto attendants, and call queues.</span></span> <span data-ttu-id="91aaa-139">서비스 전화 번호는 사용자 또는 구독자 전화 번호보다 더 높은 동시 통화 용량을 습니다.</span><span class="sxs-lookup"><span data-stu-id="91aaa-139">Service phone numbers have a higher concurrent calling capacity than user or subscriber phone numbers.</span></span> <span data-ttu-id="91aaa-140">예를 들어 서비스 번호는 수백 개의 호출을 동시에 처리할 수 있는 반면, 사용자의 전화 번호는 동시에 몇 개의 호출만 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91aaa-140">For example, a service number can handle hundreds of calls simultaneously, whereas a user's phone number can only handle a few calls simultaneously.</span></span>

### <a name="get-new-service-numbers-using-the-teams-admin-center"></a><span data-ttu-id="91aaa-141">Teams 관리 센터를 사용하여 새 서비스 번호 얻기</span><span class="sxs-lookup"><span data-stu-id="91aaa-141">Get new service numbers using the Teams admin center</span></span>


1. <span data-ttu-id="91aaa-142">직장 또는 학교 계정으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="91aaa-142">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="91aaa-143">Teams 관리 **센터로 이동**</span><span class="sxs-lookup"><span data-stu-id="91aaa-143">Go to the **Teams admin center**.</span></span>

3. <span data-ttu-id="91aaa-144">왼쪽 탐색 창에서 음성 **전화** 번호 추가 새 번호로 이동한 다음 새 서비스  >    >   **번호를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="91aaa-144">In the left navigation pane go to **Voice** > **Phone numbers** > **Add new number**, and then click **New service numbers**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="91aaa-145">Teams 관리 센터의 왼쪽 탐색 창에서 음성 옵션을 표시하려면 먼저 하나 이상의 **Enterprise E5**  라이선스, 전화 시스템 추가  기능 라이선스 하나 또는 오디오 회의 추가 기능 라이선스 1개 이상을 구입해야 합니다. </span><span class="sxs-lookup"><span data-stu-id="91aaa-145">For you to see the **Voice** option in the left navigation pane in the Teams admin center, you must first buy at least one **Enterprise E5 license**, one **Phone System** add-on license, or one **Audio Conferencing** add-on license.</span></span>

### <a name="get-new-numbers-that-arent-available-in-the-teams-admin-center"></a><span data-ttu-id="91aaa-146">Teams 관리 센터에서 사용할 수 없는 새 번호 다운로드</span><span class="sxs-lookup"><span data-stu-id="91aaa-146">Get new numbers that aren't available in the Teams admin center</span></span>
  
<span data-ttu-id="91aaa-147">경우에 따라(국가/지역에 따라) Teams 관리 센터를 사용하여 새 번호를 얻을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="91aaa-147">Sometimes (depending on your country/region) you won't be able to get your new numbers using the Teams admin center.</span></span> <span data-ttu-id="91aaa-148">이 경우 양식을 다운로드하여 다시 보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91aaa-148">In this case, you will need to download a form and send it back to us.</span></span> <span data-ttu-id="91aaa-149">새 번호를 요청하는 방법에 대한 자세한 내용은 조직의 전화 번호 [관리를 참조합니다.](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)</span><span class="sxs-lookup"><span data-stu-id="91aaa-149">To learn how to request new numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).</span></span> 

### <a name="port-or-transfer-existing-service-numbers"></a><span data-ttu-id="91aaa-150">기존 서비스 번호 포트 또는 전송</span><span class="sxs-lookup"><span data-stu-id="91aaa-150">Port or transfer existing service numbers</span></span>

<span data-ttu-id="91aaa-151">현재 서비스 공급자 또는 통신 사업자로부터 서비스 번호를 전송하려는 경우 포트 주문을 Microsoft에 수동으로 제출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91aaa-151">If you want to transfer service numbers from your current service provider or carrier, you need to manually submit a port order to Microsoft.</span></span> <span data-ttu-id="91aaa-152">LOA(승인 서신)를 사용하여 전송할 각 서비스 번호 유형(무료 및 무료)에 대해 별도의 포트 주문을 제출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91aaa-152">You need to submit separate port orders for each type of service number (toll vs. toll-free) that you will be transferring using a Letter of Authorization (LOA).</span></span> <span data-ttu-id="91aaa-153">LOA(승인 서신)에서 올바른 서비스 번호를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91aaa-153">In the Letter of Authorization (LOA), you must select the correct type of service number.</span></span> <span data-ttu-id="91aaa-154">Microsoft 지원에 문의할 때 서비스 번호(사용자또는 구독자 번호가 아닌)를 전송하도록 지정하거나, 동시 호출 용량이 호출 볼륨을 처리하기에 충분하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91aaa-154">When contacting Microsoft support, specify that you are transferring a service number (*and not a user or subscriber number*), or the concurrent calling capacity may not be enough to handle call volumes.</span></span> <span data-ttu-id="91aaa-155">전화 번호를 이전하거나 전화 번호로 다른 작업을 하려는 경우 조직의 전화 번호 관리를 [참조합니다.](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)</span><span class="sxs-lookup"><span data-stu-id="91aaa-155">If you want to transfer phone numbers or do other things with your phone numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).</span></span>

## <a name="step-5-if-you-want-to-set-up-calling-plans"></a><span data-ttu-id="91aaa-156">5단계: 통화 요금제 설정</span><span class="sxs-lookup"><span data-stu-id="91aaa-156">Step 5: If you want to set up Calling Plans</span></span>

<span data-ttu-id="91aaa-157">위의 단계를 수행한 경우 이미 전화 시스템 및 라이선스 및 통화 요금제(2단계)를 구입하여 할당하고 사용자에 대한 전화 번호를 획득(3단계)했기 때문에 통화 계획이 부분적으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="91aaa-157">If you have been following the steps above, you have already bought and assigned Phone System and licenses and a Calling Plan (step 2) and acquired phone numbers for your users (step 3), so your calling plan is partially set up.</span></span> <span data-ttu-id="91aaa-158">통화 요금제 설정 절차를 완료하기 위해 통화 요금제 설정을 [참조합니다.](set-up-calling-plans.md)</span><span class="sxs-lookup"><span data-stu-id="91aaa-158">To complete the procedures for setting up Calling Plan, see [Set up Calling Plans](set-up-calling-plans.md).</span></span>


## <a name="step-6-if-you-want-to-set-up-audio-conferencing"></a><span data-ttu-id="91aaa-159">6단계: 오디오 회의를 설정하려는 경우</span><span class="sxs-lookup"><span data-stu-id="91aaa-159">Step 6: If you want to set up Audio Conferencing</span></span>

<span data-ttu-id="91aaa-160">경우에 따라 조직의 사용자가 전화를 사용하여 모임에 전화해야 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91aaa-160">Sometimes people in your organization will need to use a phone to call in to a meeting.</span></span> <span data-ttu-id="91aaa-161">Microsoft Teams에는 이 상황에 대한 오디오 회의 기능이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91aaa-161">Microsoft Teams includes the Audio Conferencing feature for just this situation.</span></span> <span data-ttu-id="91aaa-162">모바일 장치나 PC에서 Teams 앱을 사용하는 대신 전화를 사용하여 Teams 모임에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91aaa-162">People can call in to  Teams meetings using a phone, instead of using the Teams app on a mobile device or PC.</span></span>
<span data-ttu-id="91aaa-163">오디오 회의를 설정하는 방법에 대한 자세한 내용은 Teams에 대한 오디오 회의 [설정을 참조하세요.](set-up-audio-conferencing-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="91aaa-163">For information about how to set up Audio Conferencing, see [Set up Audio Conferencing for Teams](set-up-audio-conferencing-in-teams.md).</span></span>

## <a name="step-7-if-you-want-to-set-up-a-cloud-call-queue"></a><span data-ttu-id="91aaa-164">7단계: 클라우드 호출 큐를 설정하려는 경우</span><span class="sxs-lookup"><span data-stu-id="91aaa-164">Step 7: If you want to set up a Cloud call queue</span></span>

<span data-ttu-id="91aaa-165">클라우드 통화 큐에는 누군가 조직의 전화 번호로 전화를 걸 때 사용되는 인사말, 자동으로 통화를 보류할 수 있는 능력, 통화 중인 사람이 대기 중인 동안 통화를 처리하기 위해 사용 가능한 다음 통화 에이전트를 검색하는 기능을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="91aaa-165">Cloud call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="91aaa-166">조직에 대한 단일 또는 여러 호출 큐를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91aaa-166">You can create single or multiple call queues for your organization.</span></span>

<span data-ttu-id="91aaa-167">호출 큐에 대한 자세한 내용은 클라우드 호출 큐 [만들기를 참조하세요.](create-a-phone-system-call-queue.md)</span><span class="sxs-lookup"><span data-stu-id="91aaa-167">For more information about call queues, see [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>

## <a name="step-8-if-you-want-to-set-up-a-cloud-auto-attendant"></a><span data-ttu-id="91aaa-168">8단계: 클라우드 자동 Attendant를 설정하려는 경우</span><span class="sxs-lookup"><span data-stu-id="91aaa-168">Step 8: If you want to set up a Cloud auto attendant</span></span>

<span data-ttu-id="91aaa-169">자동 전화 회의를 통해 조직에 전화를 걸고 메뉴 시스템을 탐색하여 올바른 부서, 통화 큐, 사람 또는 운영자에게 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91aaa-169">Auto attendants let people that call in to your organization and navigate a menu system to get them to the right department, call queue, person, or the operator.</span></span> <span data-ttu-id="91aaa-170">Teams 관리 센터를 사용하여 조직에 대한 자동 문의를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91aaa-170">You can create an auto attendant for your organization by using the Teams admin center.</span></span>

<span data-ttu-id="91aaa-171">클라우드 자동 참석자 설정에 대한 자세한 내용은 클라우드 자동 참석자 [설정을 참조하세요.](create-a-phone-system-auto-attendant.md)</span><span class="sxs-lookup"><span data-stu-id="91aaa-171">For information about setting up a Cloud auto attendendant, see [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span>


## <a name="step-9-assign-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a><span data-ttu-id="91aaa-172">9단계: 서비스 전화 번호 할당(오디오 회의, 통화 큐, 자동 전화 회의)</span><span class="sxs-lookup"><span data-stu-id="91aaa-172">Step 9: Assign service phone numbers (audio conferencing, call queues, auto attendants)</span></span>

<span data-ttu-id="91aaa-173">위의 **4단계에서** 서비스 번호를 지정한 후 원하는 각 서비스 유형에 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91aaa-173">Once you have your service numbers from **Step 4 above**, you need to assign them to each type of service that you want.</span></span> <span data-ttu-id="91aaa-174">예를 들어 전용 서비스 전화 번호(무료 또는 무료)를 원하는 경우 회의 브리지에 번호를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91aaa-174">For example, if you want a dedicated service phone number (toll or toll-free), you'll need to assign the number to the conferencing bridge.</span></span>

- <span data-ttu-id="91aaa-175">오디오 회의의 경우 **Teams** 관리 센터 모임 회의 브리지로 연결하여 회의 브리지에 전용 번호를 할당하고 프롬프트를 따를  >    >   수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91aaa-175">For Audio Conferencing, you can assign a dedicated number to a conferencing bridge by going to **Teams admin center** > **Meetings** > **Conference bridges** and follow the prompts.</span></span>  <span data-ttu-id="91aaa-176">자세한 내용은 오디오 회의 브리지에서 무료 또는 무료 번호 변경을 [참조하세요.](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)</span><span class="sxs-lookup"><span data-stu-id="91aaa-176">For more information, see  [Change the toll or toll-free numbers on your Audio Conferencing bridge](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span></span>

- <span data-ttu-id="91aaa-177">자동 전화 회의의 경우 **Teams** 관리 센터 음성 자동 전화 회의로 가고 지시에 따라 자동 전화 회의에 전용 번호를  >    >   할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91aaa-177">For Auto Attendants, you can assign a dedicated number to an auto attendant by going to  **Teams admin center** > **Voice** > **Auto attendants** and follow the prompts.</span></span>  <span data-ttu-id="91aaa-178">자세한 내용은 클라우드 자동 [참석자 설정을 참조하세요.](create-a-phone-system-auto-attendant.md)</span><span class="sxs-lookup"><span data-stu-id="91aaa-178">For more information, see [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span>

- <span data-ttu-id="91aaa-179">통화 큐의 경우 **Teams** 관리 센터 음성 통화 큐로 가고 프롬프트를 따라 통화 큐에 전용 번호를 할당할  >    >   수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91aaa-179">For Call Queues, you can assign a dedicated number to a call queue by going to **Teams admin center** > **Voice** > **Call queues** and follow the prompts.</span></span> <span data-ttu-id="91aaa-180">자세한 내용은 클라우드 호출 [큐 만들기를 참조하세요.](create-a-phone-system-call-queue.md)</span><span class="sxs-lookup"><span data-stu-id="91aaa-180">For more information, see [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>

<span data-ttu-id="91aaa-181">새 서비스 번호를 받고 기존 서비스 번호를 포식하는 자세한 내용은 서비스 전화 번호 [확인을 참조하세요.](getting-service-phone-numbers.md)</span><span class="sxs-lookup"><span data-stu-id="91aaa-181">For detailed information about getting new service numbers and porting existing service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md).</span></span>

## <a name="step-10-set-up-communications-credits-for-your-organization"></a><span data-ttu-id="91aaa-182">10단계: 조직에 대한 통신 크레딧 설정</span><span class="sxs-lookup"><span data-stu-id="91aaa-182">Step 10: Set up Communications Credits for your organization</span></span>

<span data-ttu-id="91aaa-183">Microsoft Teams에서 무료 번호를 사용하려면 통신 크레딧을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91aaa-183">If you would like to use toll-free numbers with Microsoft Teams, You'll need to set up Communications Credits.</span></span> <span data-ttu-id="91aaa-184">모든 대상에 전화를 걸 수 있는 능력이 필요한 통화 요금제(국내 또는 국제) 및 오디오 회의 사용자에 대한 통신 크레딧을 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="91aaa-184">Microsoft recommends that you set up Communications Credits for your Calling Plans (Domestic or International) and Audio Conferencing users who need the ability to dial out to any destination.</span></span> <span data-ttu-id="91aaa-185">많은 국가/지역이 포함되지만 일부 목적지는 통화 요금제 또는 오디오 회의 구독에 포함되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91aaa-185">Many countries/regions are included, but some destinations may not be included in your Calling Plan or Audio Conferencing subscriptions.</span></span> 

<span data-ttu-id="91aaa-186">통신 크레딧 청구를 설정하고 사용자에게 통신 크레딧  라이선스를 할당하지 않은 경우 조직에 대해 몇 분이 소요되는 경우(해당 국가/지역의 통화 요금제 또는 오디오 회의 계획에 따라) 해당 사용자는 오디오 회의 모임에서 전화를 걸거나 전화를 걸 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="91aaa-186">If you don't set up Communications Credits billing and assign a **Communications Credits** license to your users and you run out minutes for your organization (depending on your Calling Plan or Audio Conferencing plan in your country/region), those users won't be able to make calls or dial out from Audio Conferencing meetings.</span></span> <span data-ttu-id="91aaa-187">권장 금액을 포함한 자세한 내용은 통신 [크레딧이란?](what-are-communications-credits.md) 및 조직에 대한 통신 크레딧을 설정하는 방법을 [참조하세요.](set-up-communications-credits-for-your-organization.md)</span><span class="sxs-lookup"><span data-stu-id="91aaa-187">For more information, including recommended funding amounts, see [What are Communications Credits?](what-are-communications-credits.md) and [Set up Communications Credits for your organization](set-up-communications-credits-for-your-organization.md).</span></span>
  

## <a name="related-topics"></a><span data-ttu-id="91aaa-188">관련 항목</span><span class="sxs-lookup"><span data-stu-id="91aaa-188">Related topics</span></span>
[<span data-ttu-id="91aaa-189">Microsoft 365 또는 Office 365에서 전화 시스템을 사용할 수 있는 제품</span><span class="sxs-lookup"><span data-stu-id="91aaa-189">Here's what you get with Phone System in Microsoft 365 or Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="91aaa-190">조직의 전화 번호 관리</span><span class="sxs-lookup"><span data-stu-id="91aaa-190">Manage phone numbers for your organization</span></span>](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[<span data-ttu-id="91aaa-191">비즈니스용 Skype 및 Microsoft Teams의 서비스 전화 번호 받기</span><span class="sxs-lookup"><span data-stu-id="91aaa-191">Getting service phone numbers for Skype for Business and Microsoft Teams</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="91aaa-192">오디오 회의 및 통화 플랜의 국가 및 지역 가용성</span><span class="sxs-lookup"><span data-stu-id="91aaa-192">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
    
  
 
