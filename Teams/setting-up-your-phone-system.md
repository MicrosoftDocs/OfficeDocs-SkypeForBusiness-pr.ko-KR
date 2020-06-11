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
description: Microsoft 365 또는 Office 365에서 조직의 전화 시스템 (클라우드 PBX)을 설정 하는 방법을 설명 하는 단계별 가이드입니다.
ms.openlocfilehash: c1ced5aa9a6fdbfeb5cb02948607c7be7df7fbd8
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691034"
---
# <a name="set-up-phone-system-in-your-organization"></a><span data-ttu-id="5453d-103">조직에서 전화 시스템 설정</span><span class="sxs-lookup"><span data-stu-id="5453d-103">Set up Phone System in your organization</span></span>

<span data-ttu-id="5453d-104">다음은 Microsoft 365 또는 Office 365에서 전화 시스템을 설정 하는 단계별 지침입니다.</span><span class="sxs-lookup"><span data-stu-id="5453d-104">The following is a step-by-step guide for setting up Phone System in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="5453d-105">자세한 정보에 대 한 링크는 각 단계의 마지막에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5453d-105">Links to additional, detailed information are available at the end of each step.</span></span>

## <a name="step-1-make-sure-that-phone-system-is-available-in-your-country-or-region"></a><span data-ttu-id="5453d-106">1 단계: 전화 시스템을 해당 국가 또는 지역에서 사용할 수 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="5453d-106">Step 1: Make sure that Phone System is available in your country or region</span></span>

1.    <span data-ttu-id="5453d-107">먼저 [오디오 회의 및 통화 요금제의 국가 및 지역 사용 가능성](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)으로 이동 하 고 페이지 위쪽에 있는 목록에서 국가 또는 지역을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5453d-107">First go to [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md), and select your country or region from the list at the top of the page.</span></span> 
2.    <span data-ttu-id="5453d-108">**전화 시스템**에서 기능 목록과 세부 정보를 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="5453d-108">Under **Phone System**, review the list of features and details.</span></span> 
3.    <span data-ttu-id="5453d-109">전화 시스템을 사용할 수 있는 경우 2 단계로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="5453d-109">If Phone System is available, go to step 2.</span></span> 

## <a name="step-2-buy-and-assign-phone-system-and-calling-plan-licenses"></a><span data-ttu-id="5453d-110">2 단계: 전화 시스템 및 통화 계획 라이선스 구입 및 할당</span><span class="sxs-lookup"><span data-stu-id="5453d-110">Step 2: Buy and assign Phone System and Calling Plan licenses</span></span>

<span data-ttu-id="5453d-111">전화 시스템 및 통화 계획 라이선스를 단일 사용자에 게 할당 하려면 Microsoft 365 또는 Office 365 라이선스를 할당 하는 것과 같은 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5453d-111">To assign a Phone System and Calling Plan license to a single user, the steps are the same as assigning a Microsoft 365 or Office 365 license.</span></span>  <span data-ttu-id="5453d-112">라이선스를 여러 사용자에 게 대량으로 배정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5453d-112">You can also assign licenses to multiple users in bulk.</span></span> <span data-ttu-id="5453d-113">자세한 내용은 [Microsoft 팀 추가 기능 라이선스 할당](teams-add-on-licensing/assign-teams-add-on-licenses.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5453d-113">For more information, see [Assign Microsoft Teams add-on licenses](teams-add-on-licensing/assign-teams-add-on-licenses.md).</span></span>

<span data-ttu-id="5453d-114">해당 국가나 지역에 대 한 통화 요금제를 사용할 수 없는 경우 직접 라우팅 기능을 사용 하 여 온-프레미스 전화 통신 인프라를 전화 시스템에 연결 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5453d-114">If Calling Plans are not available for your country or region, consider using Direct Routing to connect your on-premises telephony infrastructure to Phone System.</span></span>  <span data-ttu-id="5453d-115">자세한 내용은 [전화 시스템 직접 라우팅을](direct-routing-landing-page.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5453d-115">For more information, see [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

## <a name="step-3-get-phone-numbers-for-your-users"></a><span data-ttu-id="5453d-116">3 단계: 사용자의 전화 번호 가져오기</span><span class="sxs-lookup"><span data-stu-id="5453d-116">Step 3: Get phone numbers for your users</span></span>

<span data-ttu-id="5453d-117">전화를 걸고 받을 수 있도록 조직에 사용자를 설정 하려면 먼저 전화 번호를 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5453d-117">Before you can set up users in your organization to make and receive phone calls, you must get phone numbers for them.</span></span>

<span data-ttu-id="5453d-118">다음과 같은 세 가지 방법으로 사용자에 대 한 번호를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5453d-118">You have three ways of getting numbers for your users:</span></span>
- <span data-ttu-id="5453d-119">팀 관리 센터를 사용 하 여 새 번호를 받으세요.</span><span class="sxs-lookup"><span data-stu-id="5453d-119">Get new numbers using the Teams admin center.</span></span>
- <span data-ttu-id="5453d-120">팀 관리 센터에서 사용할 수 없는 새 번호를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5453d-120">Get new numbers that aren't available in the Teams admin center.</span></span>
- <span data-ttu-id="5453d-121">현재 서비스 공급자 또는 전화 통신 회사에서 Microsoft 365 또는 Office 365으로 기존 번호를 이식 하거나 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="5453d-121">Port or transfer your existing numbers from your current service provider or phone carrier to Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="5453d-122">이러한 번호를 보고, 검색 하 고, 가져오고, 예약 하려면 **숫자 추가** 페이지를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5453d-122">You must use the **Add numbers** page to see, search, acquire, and reserve those numbers.</span></span> <span data-ttu-id="5453d-123">국가/지역, 시/도, 시/도를 기준으로 검색할 수 있으며, 사용자에 게 필요한 전화 번호 수를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="5453d-123">You can search by Country/Region, State, and City, and then enter the number of phone numbers you will need for your users.</span></span>

### <a name="get-new-user-phone-numbers-using-the-teams-admin-center"></a><span data-ttu-id="5453d-124">팀 관리 센터를 사용 하 여 새 사용자 전화 번호 받기</span><span class="sxs-lookup"><span data-stu-id="5453d-124">Get new user phone numbers using the Teams admin center</span></span>

1. <span data-ttu-id="5453d-125">회사 또는 학교 계정으로 Microsoft 365에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5453d-125">Sign in to Microsoft 365 with your work or school account.</span></span>

2. <span data-ttu-id="5453d-126">**팀 관리 센터로**이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="5453d-126">Go to the **Teams admin center**.</span></span>
    
3. <span data-ttu-id="5453d-127">왼쪽 탐색 창에서 **음성**  >  **전화 번호로**이동한 다음 **추가**를 클릭 하 고 화면의 지시를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="5453d-127">In the left navigation go to **Voice** > **Phone numbers**, click **Add**, and then follow the prompts.</span></span>
    
### <a name="get-new-numbers-that-arent-available-in-the-teams-admin-center"></a><span data-ttu-id="5453d-128">팀 관리 센터에서 사용할 수 없는 새 번호 가져오기</span><span class="sxs-lookup"><span data-stu-id="5453d-128">Get new numbers that aren't available in the Teams admin center</span></span>
  
<span data-ttu-id="5453d-129">때로는 (국가/지역에 따라) 팀 관리 센터를 사용 하 여 새 번호를 받을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5453d-129">Sometimes (depending on your country/region) you won't be able to get your new numbers using the Teams admin center.</span></span> <span data-ttu-id="5453d-130">이 경우 양식을 다운로드 하 여 다시 전송 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5453d-130">In this case, you'll need to download a form and send it back to us.</span></span> <span data-ttu-id="5453d-131">새 사용자 번호를 요청 하는 방법을 알아보려면 [조직의 전화 번호 관리](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5453d-131">To learn how to request new user numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).</span></span>   
  
### <a name="port-or-transfer-phone-numbers-from-your-service-provider-or-phone-carrier"></a><span data-ttu-id="5453d-132">서비스 공급자 또는 전화 통신 회사의 전화 번호를 이식 하거나 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="5453d-132">Port or transfer phone numbers from your service provider or phone carrier</span></span>
  
- <span data-ttu-id="5453d-133">사용자에 게 999 이하의 전화 번호가 필요한 경우 팀 관리 센터에서 **새 로컬 번호 포트 주문** 마법사를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5453d-133">If you need 999 or fewer phone numbers for your users, you can use the **New Local Number Port Order** wizard in the Teams admin center.</span></span> <span data-ttu-id="5453d-134">전화 [번호를 팀에 게 전송](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) 에 나와 있는 단계를 따라 전화 번호를 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="5453d-134">Follow the steps found in [Transfer phone numbers to  Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) to transfer your phone numbers.</span></span>
    
- <span data-ttu-id="5453d-135">999 개 이상의 전화 번호를 이식 해야 하는 경우 [조직의 전화 번호 관리](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 를 참조 하 여 포트 주문 서비스 요청 또는 주문을 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5453d-135">If you need to port more than 999 phone numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) to submit a port order service request or order.</span></span> 

<span data-ttu-id="5453d-136">새 전화 번호를 받고 있거나 기존 번호를 전송 하는 방법에 대 한 자세한 내용은 [조직의 전화 번호 관리](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5453d-136">For detailed information about getting new phone numbers or transferring existing numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).</span></span>

## <a name="step-4-get-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a><span data-ttu-id="5453d-137">4 단계: 서비스 전화 번호 가져오기 (오디오 회의, 통화 대기열, 자동 전화 교환)</span><span class="sxs-lookup"><span data-stu-id="5453d-137">Step 4: Get service phone numbers (audio conferencing, call queues, auto attendants)</span></span>

<span data-ttu-id="5453d-138">Microsoft 365 또는 Office 365에서 사용자의 전화 번호를 가져올 수 있을 뿐만 아니라 오디오 회의 (컨퍼런스), 자동 전화 교환, 통화 대기열 등의 서비스에 대 한 유료 또는 무료 전화 번호를 검색 하 고 가져올 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5453d-138">In addition to getting phone numbers for your users from Microsoft 365 or Office 365, you can search and acquire toll or toll-free phone numbers for services such as audio conferencing (for conference bridges), auto attendants, and call queues.</span></span> <span data-ttu-id="5453d-139">서비스 전화 번호는 사용자 또는 구독자 전화 번호 보다 높은 동시 통화 용량을가지고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5453d-139">Service phone numbers have a higher concurrent calling capacity than user or subscriber phone numbers.</span></span> <span data-ttu-id="5453d-140">예를 들어 서비스 번호는 여러 개의 통화를 동시에 처리할 수 있지만, 사용자의 전화 번호는 일부 통화를 동시에 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5453d-140">For example, a service number can handle hundreds of calls simultaneously, whereas a user's phone number can only handle a few calls simultaneously.</span></span>

### <a name="get-new-service-numbers-using-the-teams-admin-center"></a><span data-ttu-id="5453d-141">팀 관리 센터를 사용 하 여 새 서비스 번호 받기</span><span class="sxs-lookup"><span data-stu-id="5453d-141">Get new service numbers using the Teams admin center</span></span>


1. <span data-ttu-id="5453d-142">회사 또는 학교 계정으로 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5453d-142">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="5453d-143">**팀 관리 센터로**이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="5453d-143">Go to the **Teams admin center**.</span></span>

3. <span data-ttu-id="5453d-144">왼쪽 탐색 창에서 **음성**  >  **전화 번호로**이동한  >  다음**새 번호를 추가**하 고 **새 서비스 번호**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5453d-144">In the left navigation pane go to **Voice** > **Phone numbers** > **Add new number**, and then click **New service numbers**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="5453d-145">팀 관리 센터의 왼쪽 탐색 창에서 **음성** 옵션을 보려면 먼저 하나 이상의 **Enterprise E5 라이선스**, 하나의 **전화 시스템** 추가 기능 라이선스 또는 하나의 **오디오 회의** 추가 기능 라이선스를 구입 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5453d-145">For you to see the **Voice** option in the left navigation pane in the Teams admin center, you must first buy at least one **Enterprise E5 license**, one **Phone System** add-on license, or one **Audio Conferencing** add-on license.</span></span>

### <a name="get-new-numbers-that-arent-available-in-the-teams-admin-center"></a><span data-ttu-id="5453d-146">팀 관리 센터에서 사용할 수 없는 새 번호 가져오기</span><span class="sxs-lookup"><span data-stu-id="5453d-146">Get new numbers that aren't available in the Teams admin center</span></span>
  
<span data-ttu-id="5453d-147">때로는 (국가/지역에 따라) 팀 관리 센터를 사용 하 여 새 번호를 받을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5453d-147">Sometimes (depending on your country/region) you won't be able to get your new numbers using the Teams admin center.</span></span> <span data-ttu-id="5453d-148">이 경우 양식을 다운로드 하 여 다시 전송 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5453d-148">In this case, you will need to download a form and send it back to us.</span></span> <span data-ttu-id="5453d-149">새 번호를 요청 하는 방법을 알아보려면 [조직의 전화 번호 관리](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5453d-149">To learn how to request new numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).</span></span> 

### <a name="port-or-transfer-existing-service-numbers"></a><span data-ttu-id="5453d-150">기존 서비스 번호 포트 또는 전송</span><span class="sxs-lookup"><span data-stu-id="5453d-150">Port or transfer existing service numbers</span></span>

<span data-ttu-id="5453d-151">현재 서비스 공급자 또는 통신 회사에서 서비스 번호를 전송 하려면 Microsoft에 수동으로 포트 순서를 제출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5453d-151">If you want to transfer service numbers from your current service provider or carrier, you need to manually submit a port order to Microsoft.</span></span> <span data-ttu-id="5453d-152">각 서비스 번호 유형 (유료 및 무료)에 대해 별도의 포트 주문을 제출 하 여 승인 문자 (LOA)를 사용 하 여 전송 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5453d-152">You need to submit separate port orders for each type of service number (toll vs. toll-free) that you will be transferring using a Letter of Authorization (LOA).</span></span> <span data-ttu-id="5453d-153">인증 문자 (LOA)에서 올바른 서비스 번호 유형을 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5453d-153">In the Letter of Authorization (LOA), you must select the correct type of service number.</span></span> <span data-ttu-id="5453d-154">Microsoft 지원에 문의 하는 경우*사용자 또는 구독자 번호가 아닌*서비스 번호를 전송 하도록 지정 하거나 동시 통화 용량이 통화 볼륨을 처리 하는 데 충분 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5453d-154">When contacting Microsoft support, specify that you are transferring a service number (*and not a user or subscriber number*), or the concurrent calling capacity may not be enough to handle call volumes.</span></span> <span data-ttu-id="5453d-155">전화 번호를 전송 하거나 전화 번호를 사용 하 여 다른 작업을 수행 하려는 경우 [조직의 전화 번호 관리](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5453d-155">If you want to transfer phone numbers or do other things with your phone numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).</span></span>

## <a name="step-5-if-you-want-to-set-up-calling-plans"></a><span data-ttu-id="5453d-156">5 단계: 통화 계획을 설정 하려는 경우</span><span class="sxs-lookup"><span data-stu-id="5453d-156">Step 5: If you want to set up Calling Plans</span></span>

<span data-ttu-id="5453d-157">위의 단계를 수행한 후에는 이미 전화 시스템 및 라이선스와 통화 요금제 (2 단계)를 구입 하 고 할당 하 고 사용자에 게 확보 한 전화 번호 (3 단계)를 사용 하 여 통화 계획이 부분적으로 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5453d-157">If you have been following the steps above, you have already bought and assigned Phone System and licenses and a Calling Plan (step 2) and acquired phone numbers for your users (step 3), so your calling plan is partially set up.</span></span> <span data-ttu-id="5453d-158">통화 계획을 설정 하는 절차를 완료 하려면 [통화 계획](set-up-calling-plans.md)설정을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5453d-158">To complete the procedures for setting up Calling Plan, see [Set up Calling Plans](set-up-calling-plans.md).</span></span>


## <a name="step-6-if-you-want-to-set-up-audio-conferencing"></a><span data-ttu-id="5453d-159">6 단계: 오디오 회의를 설정 하려는 경우</span><span class="sxs-lookup"><span data-stu-id="5453d-159">Step 6: If you want to set up Audio Conferencing</span></span>

<span data-ttu-id="5453d-160">경우에 따라 조직의 사용자가 전화를 사용하여 모임에 전화해야 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5453d-160">Sometimes people in your organization will need to use a phone to call in to a meeting.</span></span> <span data-ttu-id="5453d-161">Microsoft 팀에는 이러한 상황에 대 한 오디오 회의 기능도 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5453d-161">Microsoft Teams includes the Audio Conferencing feature for just this situation.</span></span> <span data-ttu-id="5453d-162">사용자는 모바일 장치 또는 PC에서 팀 앱을 사용 하는 대신 휴대폰을 사용 하 여 팀 회의에 통화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5453d-162">People can call in to  Teams meetings using a phone, instead of using the Teams app on a mobile device or PC.</span></span>
<span data-ttu-id="5453d-163">오디오 회의를 설정 하는 방법에 대 한 자세한 내용은 [팀에 대 한 오디오 회의 설정을](set-up-audio-conferencing-in-teams.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5453d-163">For information about how to set up Audio Conferencing, see [Set up Audio Conferencing for Teams](set-up-audio-conferencing-in-teams.md).</span></span>

## <a name="step-7-if-you-want-to-set-up-a-cloud-call-queue"></a><span data-ttu-id="5453d-164">7 단계: 클라우드 통화 큐를 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="5453d-164">Step 7: If you want to set up a Cloud call queue</span></span>

<span data-ttu-id="5453d-165">클라우드 통화 큐에는 사용자가 조직의 전화 번호를 호출할 때 사용 되는 인사말, 통화를 자동으로 대기 하는 기능, 전화를 걸고 있는 사용자가 대기 중인 음악을 수신 대기 하는 동안 사용 가능한 다음 통화 에이전트를 검색 하 여 통화를 처리 하는 기능이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5453d-165">Cloud call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="5453d-166">조직에 대 한 단일 또는 복수 통화 대기열을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5453d-166">You can create single or multiple call queues for your organization.</span></span>

<span data-ttu-id="5453d-167">통화 대기열에 대 한 자세한 내용은 [클라우드 통화 대기열 만들기](create-a-phone-system-call-queue.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5453d-167">For more information about call queues, see [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>

## <a name="step-8-if-you-want-to-set-up-a-cloud-auto-attendant"></a><span data-ttu-id="5453d-168">8 단계: 클라우드 자동 전화 교환을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="5453d-168">Step 8: If you want to set up a Cloud auto attendant</span></span>

<span data-ttu-id="5453d-169">자동 전화 교환을 통해 조직에 전화를 걸고 메뉴 시스템을 탐색 하 여 올바른 부서, 통화 대기열, 사람, 교환원에 게 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5453d-169">Auto attendants let people that call in to your organization and navigate a menu system to get them to the right department, call queue, person, or the operator.</span></span> <span data-ttu-id="5453d-170">팀 관리 센터를 사용 하 여 조직에 대 한 자동 전화 교환을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5453d-170">You can create an auto attendant for your organization by using the Teams admin center.</span></span>

<span data-ttu-id="5453d-171">클라우드 자동 전화 교환 설정에 대 한 자세한 내용은 [클라우드 자동 전화 교환을 설정](create-a-phone-system-auto-attendant.md)attendendant을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5453d-171">For information about setting up a Cloud auto attendendant, see [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span>


## <a name="step-9-assign-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a><span data-ttu-id="5453d-172">9 단계: 서비스 전화 번호 지정 (오디오 회의, 통화 대기열, 자동 전화 교환)</span><span class="sxs-lookup"><span data-stu-id="5453d-172">Step 9: Assign service phone numbers (audio conferencing, call queues, auto attendants)</span></span>

<span data-ttu-id="5453d-173">**위의 4 단계**에서 서비스 번호를 찾았으면 원하는 각 서비스 유형에 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5453d-173">Once you have your service numbers from **Step 4 above**, you need to assign them to each type of service that you want.</span></span> <span data-ttu-id="5453d-174">예를 들어 유료 또는 무료 서비스 전화 번호를 원할 경우 회의 브리지에 해당 번호를 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5453d-174">For example, if you want a dedicated service phone number (toll or toll-free), you'll need to assign the number to the conferencing bridge.</span></span>

- <span data-ttu-id="5453d-175">오디오 회의의 경우 **팀 관리 센터**  >  **모임**발송 브리지로 연결 하  >  고 화면의 지시에 따라**전화** 회의 브리지에 전용 번호를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5453d-175">For Audio Conferencing, you can assign a dedicated number to a conferencing bridge by going to **Teams admin center** > **Meetings** > **Conference bridges** and follow the prompts.</span></span>  <span data-ttu-id="5453d-176">자세한 내용은 [오디오 회의 브리지의 유료 또는 무료 전화 번호 변경을](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5453d-176">For more information, see  [Change the toll or toll-free numbers on your Audio Conferencing bridge](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span></span>

- <span data-ttu-id="5453d-177">자동 전화 교환의 경우 **팀 관리 센터**  >  **음성**  >  **자동 전화 교환** 으로 이동 하 여 메시지에 따라 전용 번호를 자동 전화 교환에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5453d-177">For Auto Attendants, you can assign a dedicated number to an auto attendant by going to  **Teams admin center** > **Voice** > **Auto attendants** and follow the prompts.</span></span>  <span data-ttu-id="5453d-178">자세한 내용은 [클라우드 자동 전화 교환 설정을](create-a-phone-system-auto-attendant.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5453d-178">For more information, see [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span>

- <span data-ttu-id="5453d-179">통화 대기열의 경우 **팀 관리 센터**  >  **음성**  >  **통화 전담팀** 으로 이동 하 여 메시지에 따라 전용 번호를 통화 대기열에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5453d-179">For Call Queues, you can assign a dedicated number to a call queue by going to **Teams admin center** > **Voice** > **Call queues** and follow the prompts.</span></span> <span data-ttu-id="5453d-180">자세한 내용은 [클라우드 통화 대기열 만들기](create-a-phone-system-call-queue.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5453d-180">For more information, see [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>

<span data-ttu-id="5453d-181">새 서비스 번호를 받고 기존 서비스 번호를 포팅 하는 방법에 대 한 자세한 내용은 [서비스 전화 번호 가져오기를](getting-service-phone-numbers.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5453d-181">For detailed information about getting new service numbers and porting existing service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md).</span></span>

## <a name="step-10-set-up-communications-credits-for-your-organization"></a><span data-ttu-id="5453d-182">10 단계: 조직의 통신 크레딧을 설정</span><span class="sxs-lookup"><span data-stu-id="5453d-182">Step 10: Set up Communications Credits for your organization</span></span>

<span data-ttu-id="5453d-183">Microsoft 팀에 무료 전화 번호를 사용 하려면 통신 크레딧을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5453d-183">If you would like to use toll-free numbers with Microsoft Teams, You'll need to set up Communications Credits.</span></span> <span data-ttu-id="5453d-184">통화 요금제 (국내 또는 국제) 및 오디오 회의 사용자에 게 통신 크레딧을 설정 하 고 대상에 게 전화를 걸 수 있는 기능이 필요한 경우에 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="5453d-184">Microsoft recommends that you set up Communications Credits for your Calling Plans (Domestic or International) and Audio Conferencing users who need the ability to dial out to any destination.</span></span> <span data-ttu-id="5453d-185">여러 국가/지역이 포함 되어 있지만 일부 대상은 통화 요금제 또는 오디오 회의 구독에 포함 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5453d-185">Many countries/regions are included, but some destinations may not be included in your Calling Plan or Audio Conferencing subscriptions.</span></span> 

<span data-ttu-id="5453d-186">통신 크레딧 청구를 설정 하지 않고 사용자에 게 **통신 크레딧** 라이선스를 할당 하지 않으면 해당 국가/지역의 통화 요금제 또는 오디오 회의 요금제에 따라 해당 사용자가 오디오 회의 모임에서 통화 하거나 전화를 걸 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5453d-186">If you don't set up Communications Credits billing and assign a **Communications Credits** license to your users and you run out minutes for your organization (depending on your Calling Plan or Audio Conferencing plan in your country/region), those users won't be able to make calls or dial out from Audio Conferencing meetings.</span></span> <span data-ttu-id="5453d-187">권장 자금 액수를 포함 하 여 자세한 내용은 [통신 크레딧을 소개](what-are-communications-credits.md) 하 고 [조직의 통신 크레딧을 설정](set-up-communications-credits-for-your-organization.md)하세요.</span><span class="sxs-lookup"><span data-stu-id="5453d-187">For more information, including recommended funding amounts, see [What are Communications Credits?](what-are-communications-credits.md) and [Set up Communications Credits for your organization](set-up-communications-credits-for-your-organization.md).</span></span>
  

## <a name="related-topics"></a><span data-ttu-id="5453d-188">관련 항목</span><span class="sxs-lookup"><span data-stu-id="5453d-188">Related topics</span></span>
[<span data-ttu-id="5453d-189">Microsoft 365 또는 Office 365에서 전화 시스템을 사용 하 여 얻을 수 있는 기능</span><span class="sxs-lookup"><span data-stu-id="5453d-189">Here's what you get with Phone System in Microsoft 365 or Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="5453d-190">조직의 전화 번호 관리</span><span class="sxs-lookup"><span data-stu-id="5453d-190">Manage phone numbers for your organization</span></span>](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[<span data-ttu-id="5453d-191">비즈니스용 Skype 및 Microsoft Teams의 서비스 전화 번호 받기</span><span class="sxs-lookup"><span data-stu-id="5453d-191">Getting service phone numbers for Skype for Business and Microsoft Teams</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="5453d-192">오디오 회의 및 통화 플랜의 국가 및 지역 가용성</span><span class="sxs-lookup"><span data-stu-id="5453d-192">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
    
  
 
