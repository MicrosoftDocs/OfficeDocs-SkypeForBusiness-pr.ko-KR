---
title: 조직에 사용할 통신 크레딧 설정
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: mikedav
ms.topic: article
ms.assetid: bb9f2a8d-f5be-41ed-9d19-25dea5ca9f52
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Licensing
- seo-marvel-apr2020
description: '사용자 및 조직의 통신 크레딧(PSTN 소비) 청구 라이선스를 설정하는 방법에 대해 자세히 알아보고 '
ms.openlocfilehash: 98591d7603cdf63a76bef3478834f37504d8ff6c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117106"
---
# <a name="set-up-communications-credits-for-your-organization"></a><span data-ttu-id="e9c12-103">조직에 사용할 통신 크레딧 설정</span><span class="sxs-lookup"><span data-stu-id="e9c12-103">Set up Communications Credits for your organization</span></span>

<span data-ttu-id="e9c12-104">무료 번호와 무료 번호를 사용하려면 통신 크레딧을 설정해야 비즈니스용 Skype Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e9c12-104">You will need to set up Communications Credits if you would like to use toll-free numbers with Skype for Business and Microsoft Teams.</span></span> <span data-ttu-id="e9c12-105">또한 통화 계획(국내 또는 국제) 및 모든 대상에 전화를 걸 수 있는 능력이 필요한 오디오 회의 사용자에 대한 통신 크레딧을 설정하는 **것이 좋습니다.**</span><span class="sxs-lookup"><span data-stu-id="e9c12-105">Also, we recommend that you set up Communications Credits for your Calling Plans (Domestic or International) and Audio Conferencing users who need the ability to dial out to **any destination**.</span></span> <span data-ttu-id="e9c12-106">많은 국가/지역이 포함되어 있지만 일부 대상은 통화 계획 또는 오디오 회의 구독에 포함되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9c12-106">Many countries/regions are included, but some destinations may not be included in your Calling Plan or Audio Conferencing subscriptions.</span></span> <span data-ttu-id="e9c12-107">통신 크레딧 청구를 설정하고 사용자에게 통신 크레딧  라이선스를 할당하지 않은 경우 조직에 대한 분(국가/지역의 통화 계획 또는 오디오 회의 계획에 따라 다를 경우) 해당 사용자는 오디오 회의 모임에서 전화를 걸거나 전화를 걸 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e9c12-107">If you don't set up Communications Credits billing and assign a **Communications Credits** license to your users and you run out minutes for your organization (depending on your Calling Plan or Audio Conferencing plan in your country/region), those users won't be able to make calls or dial out from Audio Conferencing meetings.</span></span> <span data-ttu-id="e9c12-108">권장되는 자금을 포함하여 자세한 정보를 얻을 수 있습니다. 통신 [크레딧이란?](what-are-communications-credits.md)</span><span class="sxs-lookup"><span data-stu-id="e9c12-108">You can get more information, including recommended funding amounts, by reading [What are Communications Credits?](what-are-communications-credits.md)</span></span>
  
> [!NOTE]
> <span data-ttu-id="e9c12-109">비용은 여기를 [참조하세요.](https://go.microsoft.com/fwlink/p/?LinkId=799523 )</span><span class="sxs-lookup"><span data-stu-id="e9c12-109">To find out how much it costs, [see the rates here](https://go.microsoft.com/fwlink/p/?LinkId=799523 ).</span></span> 
  
## <a name="step-1-assign-an-audio-conferencing-or-calling-plan-license-to-your-users"></a><span data-ttu-id="e9c12-110">1단계: 사용자에게 오디오 회의 또는 통화 계획 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="e9c12-110">Step 1: Assign an Audio Conferencing or Calling Plan license to your users</span></span>

<span data-ttu-id="e9c12-111">등록할 때 국가/지역에 따라 일정한 수의 분을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="e9c12-111">When you sign up, you get a certain number of minutes depending on your country/region.</span></span> <span data-ttu-id="e9c12-112">국가 또는 지역 가용성 목록에서 [](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md#select-your-country-or-region-to-see-whats-available-for-your-organization) 오디오 회의 및 통화 계획에 대한 국가 또는 지역을 검색하여 얻을 수 있는 분 수를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9c12-112">You can search for your country or region in the [Country or region availability list for Audio Conferencing and Calling Plans](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md#select-your-country-or-region-to-see-whats-available-for-your-organization) to see the number of minutes you will get.</span></span> <span data-ttu-id="e9c12-113">해당 분을 사용하면 통화 연결이 끊어집니다.</span><span class="sxs-lookup"><span data-stu-id="e9c12-113">After you use those minutes, calls will be disconnected.</span></span> <span data-ttu-id="e9c12-114">이 문제를 방지하려면 통신 크레딧을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9c12-114">To prevent this from happening, you need to set up Communications Credits.</span></span>
  
<span data-ttu-id="e9c12-115">이렇게하려면 사용자에게 오디오 회의 또는 전화 시스템 **할당해야** 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9c12-115">To do so, **you need to assign an Audio Conferencing or Phone System license** to your users.</span></span>
  
- <span data-ttu-id="e9c12-116">사용자에게 **오디오** 회의 라이선스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="e9c12-116">Assign an **Audio Conferencing** license to your users.</span></span> <span data-ttu-id="e9c12-117">추가 [Microsoft Teams 라이선스 할당을 참조합니다.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="e9c12-117">See [Assign Microsoft Teams add-on licenses](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
    <span data-ttu-id="e9c12-118">이 라이선스를 할당한 후 오디오 회의를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9c12-118">After you assign this license, you will need to set up audio conferencing.</span></span> <span data-ttu-id="e9c12-119">단계별 지침은 에서 오디오 회의 시도 또는 구매를 Microsoft 365 또는 [Office 365.](try-or-purchase-audio-conferencing-in-office-365-for-teams.md)</span><span class="sxs-lookup"><span data-stu-id="e9c12-119">For step-by-step instructions, see [Try or purchase Audio Conferencing in Microsoft 365 or Office 365](try-or-purchase-audio-conferencing-in-office-365-for-teams.md).</span></span>
    
- <span data-ttu-id="e9c12-120">사용자에게  전화 시스템 및  국내 및 국제 통화 계획 라이선스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="e9c12-120">Assign **Phone System** and a **Domestic or Domestic and International** Calling Plan license to your users.</span></span> <span data-ttu-id="e9c12-121">추가 [Microsoft Teams 라이선스 할당을 참조합니다.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="e9c12-121">See [Assign Microsoft Teams add-on licenses](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e9c12-122">통신 크레딧에는 필요하지는 않습니다. 국내 통화 요금제 또는  국내 및 국제 통화 요금제 라이선스도 **할당해야** 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9c12-122">Although it's not required for Communications Credits, you still need to also assign a **Domestic Calling Plan** or a **Domestic and International Calling Plan** license.</span></span>
  
    <span data-ttu-id="e9c12-123">이러한 라이선스를 할당한 후 조직의 전화 번호를 받은 다음 해당 번호를 조직의 사용자에게 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9c12-123">After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="e9c12-124">단계별 지침은 통화 계획 설정 [을 참조하세요.](set-up-calling-plans.md)</span><span class="sxs-lookup"><span data-stu-id="e9c12-124">For step-by-step instructions, see [Set up Calling Plans](set-up-calling-plans.md).</span></span>
    
<span data-ttu-id="e9c12-125">자세한 내용은 추가 [Microsoft Teams 라이선스를 참조하세요.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="e9c12-125">For more information, see [Microsoft Teams add-on licensing](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span></span>
  
## <a name="step-2-set-up-communications-credits-for-your-organization"></a><span data-ttu-id="e9c12-126">2단계: 조직에 대한 통신 크레딧 설정</span><span class="sxs-lookup"><span data-stu-id="e9c12-126">Step 2: Set up Communications Credits for your organization</span></span>

1. <span data-ttu-id="e9c12-127">직장 또는 [학교 계정으로](https://portal.office.com/Adminportal) Microsoft 365 관리 센터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="e9c12-127">Sign in to the [Microsoft 365 admin center](https://portal.office.com/Adminportal) with your work or school account.</span></span>
    
2. <span data-ttu-id="e9c12-128">관리 센터의 왼쪽 Microsoft 365 청구 구매   >  **서비스로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="e9c12-128">In the left navigation of the Microsoft 365 admin center, go to **Billing** > **Purchase Services**.</span></span> <span data-ttu-id="e9c12-129">아래로 스크롤하고 **추가 기능 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e9c12-129">Scroll down and select **Add-Ons**.</span></span>

3. <span data-ttu-id="e9c12-130">통신 **크레딧을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e9c12-130">Select **Communications Credits**.</span></span>
    
4. <span data-ttu-id="e9c12-131">**Communications Credits 구독** 페이지에서 정보를 입력한 다음 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="e9c12-131">On the **Communications Credits** subscription page, fill in your information, and then click **Next**:</span></span>
    
   - <span data-ttu-id="e9c12-132">**자금 추가** 계정에 추가할 금액을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="e9c12-132">**Add funds** Enter the amount that you want to add to your account.</span></span> <span data-ttu-id="e9c12-133">자동 충전을 사용하도록 설정하지 않은 경우 이러한 자금이 고갈되면 통신 크레딧을 사용하여 사용하도록 설정된 호출 기능이 중단됩니다(예: 인바운드 무료 서비스).</span><span class="sxs-lookup"><span data-stu-id="e9c12-133">If you don't enable auto-recharge, once these funds are depleted, calling capabilities that are enabled using Communications Credits will be disrupted (such as inbound toll-free service).</span></span> <span data-ttu-id="e9c12-134">잔액이 0(0)에 도달할 때마다 통신 크레딧 잔액을 수동으로 보충하지 않도록하려면 자동 충전 기능을 사용하도록 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e9c12-134">To avoid having to manually replenish your Communications Credits balance each time your balance reaches 0 (zero), we recommend you enable the auto-recharge feature.</span></span>
    
   - <span data-ttu-id="e9c12-135">**자동 충전** 자동 충전을 사용하도록 설정하면 잔액이 설정한 임계값보다 낮아질 때 계정이 자동으로 다시 충전됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9c12-135">**Auto-recharge** Enabling auto-recharge will automatically refill your account when the balance falls below the threshold that you set.</span></span>
    
     <span data-ttu-id="e9c12-136">Communications Credits 잔액이 0(0)에 도달할 경우 자동 충전 설정을 사용하여 서비스 중단을 방지하는 것이 좋습니다. </span><span class="sxs-lookup"><span data-stu-id="e9c12-136">It's recommended that you use the **Auto-recharge** setting to avoid any disruption of service should your Communications Credits balance reach 0 (zero).</span></span> <span data-ttu-id="e9c12-137">재충전이 성공하고, 재충전이 실패하는 경우(예: 만료된 신용 카드) 통신 크레딧 잔액이 0(0)에 도달하면 전자 메일이 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9c12-137">You will be sent an email when recharge transactions succeed, when recharge transactions fail (such as an expired credit card), and when your Communications Credits balance reaches 0 (zero).</span></span>
    
   - <span data-ttu-id="e9c12-138">**충전 금액** 아래 트리거 금액에 도달하면 계정에 추가할 재충전 상자에 금액을 입력합니다. </span><span class="sxs-lookup"><span data-stu-id="e9c12-138">**Recharge amount** Enter the amount in the **Recharge with** box that you want added to your account once it reaches the trigger amount below.</span></span>
    
   - <span data-ttu-id="e9c12-139">**트리거 금액** 잔액이  '트리거' 자동 충전에 사용되는 상자  아래에 떨어지면 금액을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="e9c12-139">**Trigger amount** Enter the amount in **When the balance falls below** box that will be used to ' *trigger*  ' the auto-recharge.</span></span> <span data-ttu-id="e9c12-140">잔액이 이 금액보다 떨어질 경우 충전 금액이 계정에 자동으로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9c12-140">Once your balance falls below this amount, the recharge amount will be added automatically to your account.</span></span>

      > [!NOTE]
     > <span data-ttu-id="e9c12-141">자금은 서비스를 사용할 때 Microsoft 게시 요금에서 Communications 크레딧에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9c12-141">Funds will be applied only to Communications Credits at Microsoft published rates when the services are used.</span></span> <span data-ttu-id="e9c12-142">구매일 12개월 이내에 사용되지 않은 모든 자금은 만료되고 소진됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9c12-142">Any funds not used within 12 months of the purchase date will expire and be forfeited.</span></span> 
     > 
     > <span data-ttu-id="e9c12-143">통신 크레딧에 대한 월별 청구는 배정된 펀드가 사용된 경우만 적용됩니다. 월별 사용량을 검사하는 방법에 대해 알아보고 [PSTN](/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report) 사용 비즈니스용 Skype 읽기</span><span class="sxs-lookup"><span data-stu-id="e9c12-143">Monthly billing for Communication Credits will only be applied if the alloted fund has been used, to learn how to check your monthly usage, read [Skype for Business PSTN usage report](/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report)</span></span>
    
5. <span data-ttu-id="e9c12-144">결제 정보를 입력하고 주문 **장소를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="e9c12-144">Enter your payment information and click **Place order**.</span></span>
    >[!IMPORTANT]
    ><span data-ttu-id="e9c12-145">볼륨 라이선스 고객인 경우 결제를 위해 엔터프라이즈 계약 번호를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9c12-145">If you are a volume licensing customer, you may choose your enterprise agreement number for payment.</span></span> <span data-ttu-id="e9c12-146">엔터프라이즈 계약 번호가 여러 개 있는 경우 결제에 사용할 엔터프라이즈 계약을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9c12-146">If you have multiple enterprise agreement numbers, you will be able to select which enterprise agreement you would like to use for payment.</span></span> <span data-ttu-id="e9c12-147">또한 기업 계약 번호와 연결될 구매 주문 번호를 지정할 수 있는 기회도 부여됩니다(해당하는 경우).</span><span class="sxs-lookup"><span data-stu-id="e9c12-147">You will also be given an opportunity to specify a purchase order number to associate with the enterprise agreement number (if applicable).</span></span>
    
<span data-ttu-id="e9c12-148">각 조직은 고려할 통화 요금제 볼륨 및 요금의 사용 현황이 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="e9c12-148">Each organization will have a different usage of Calling Plan volume and rates to consider.</span></span> <span data-ttu-id="e9c12-149">현재 서비스 공급자에서 이러한 유형의 사용 데이터를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9c12-149">You will need to get this type of usage data from your current service provider.</span></span> <span data-ttu-id="e9c12-150">이미 비즈니스용 Skype Online을 서비스 공급자로 사용하는 조직은 관리 센터 보고서 PSTN 사용 세부 정보 **보고서에서** 검토하여 Microsoft Teams 데이터를 얻을  >    >  **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9c12-150">Organizations already using Skype for Business Online already as their service provider can get usage data by reviewing it in the **Microsoft Teams admin center** > **Reports** > **PSTN usage details** report.</span></span>
  
<span data-ttu-id="e9c12-151">Communications Credits를 설정하는 경우 필요한 금액을 결정하기 위해 조직의 통화 사용량을 조사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9c12-151">When you are setting up Communications Credits, you will need to investigate call usage for your organization to determine the amounts you need.</span></span> <span data-ttu-id="e9c12-152">**PSTN** 사용 세부 정보 보고서를 검토하여 통화 사용 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9c12-152">You can get call usage information by reviewing the **PSTN usage details** report.</span></span> <span data-ttu-id="e9c12-153">이 보고서를 사용하면 데이터를 저장하거나 사용자 지정 보고서를 만들어야 Excel 호출 데이터 레코드를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9c12-153">This report lets you export the call data records to Excel if you need to store the data or create custom reports.</span></span> <span data-ttu-id="e9c12-154">사용량을 보는 방법을 알아보고자 하는 경우 [PSTN 사용 현황 보고서를 참조합니다.](/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report)</span><span class="sxs-lookup"><span data-stu-id="e9c12-154">To learn how to see usage, read [PSTN usage report](/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report).</span></span>
  
## <a name="step-3-assign-a-communications-credits-license-to-users"></a><span data-ttu-id="e9c12-155">3단계: 사용자에게 통신 크레딧 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="e9c12-155">Step 3: Assign a Communications Credits license to users</span></span>

1. <span data-ttu-id="e9c12-156">직장 또는 [학교 계정으로](https://portal.office.com/Adminportal) Microsoft 365 관리 센터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="e9c12-156">Sign in to the [Microsoft 365 admin center](https://portal.office.com/Adminportal) with your work or school account.</span></span>
    
2. <span data-ttu-id="e9c12-157">관리 센터의 왼쪽 탐색에서 Microsoft 365 활성 사용자로 이동한 다음 목록에서   >  사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e9c12-157">In the left navigation of the Microsoft 365 admin center, go to **Users** > **Active users**, and then select a user from the list.</span></span>
    
3. <span data-ttu-id="e9c12-158">라이선스 **및 앱을 선택하세요.**</span><span class="sxs-lookup"><span data-stu-id="e9c12-158">Choose **Licenses and Apps**.</span></span>
    
4. <span data-ttu-id="e9c12-159">통신 **크레딧을** **On으로** 전환하여 이 라이선스를 할당한 다음 저장을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="e9c12-159">Toggle **Communications Credits** to **On** to assign this license, and then select **Save**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e9c12-160">E5 라이선스에 할당된  사용자가 Enterprise 경우에도 이 작업을 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e9c12-160">Even if you have users who are assigned an **Enterprise E5** license, it's still recommended that you do this.</span></span>

    > [!TIP]
    > <span data-ttu-id="e9c12-161">[Powershell을](/powershell/module/skype/?view=skype-ps) 사용하여 하나의 명령으로 여러 사용자에게 라이선스 및 앱을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9c12-161">You can use [Powershell](/powershell/module/skype/?view=skype-ps) to assign licenses and apps to multiple users with one command.</span></span>
  
## <a name="want-to-know-about-plans-and-pricing"></a><span data-ttu-id="e9c12-162">계획 및 가격 책정에 대해 알고 싶습니까?</span><span class="sxs-lookup"><span data-stu-id="e9c12-162">Want to know about plans and pricing?</span></span>

<span data-ttu-id="e9c12-163">다음 링크 중 하나를 방문하여 요금제 및 가격 책정을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9c12-163">You can see the plans and pricing by visiting one of the following links:</span></span>
  
- [<span data-ttu-id="e9c12-164">통화 플랜</span><span class="sxs-lookup"><span data-stu-id="e9c12-164">Calling Plans</span></span>](https://go.microsoft.com/fwlink/?LinkId=799761 )
    
- [<span data-ttu-id="e9c12-165">오디오 회의 계획</span><span class="sxs-lookup"><span data-stu-id="e9c12-165">Audio Conferencing Plans</span></span>](https://go.microsoft.com/fwlink/?LinkId=799762 )
    
- [<span data-ttu-id="e9c12-166">전화 시스템 계획</span><span class="sxs-lookup"><span data-stu-id="e9c12-166">Phone System Plans</span></span>](https://go.microsoft.com/fwlink/?LinkId=799763)
    
<span data-ttu-id="e9c12-167">또한 관리 센터에 로그인하고 구독 [Microsoft 365](https://portal.office.com/adminportal/home?add=sub&amp;adminportal=1#/catalog) 청구 구독으로 가면 정보를 볼  >    >  **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="e9c12-167">You can also see information by [signing in to the Microsoft 365 admin center](https://portal.office.com/adminportal/home?add=sub&amp;adminportal=1#/catalog) and going to **Billing** > **Subscriptions** > **Add subscriptions**.</span></span>
  
<span data-ttu-id="e9c12-168">각 기능에 필요한 라이선스 또는 라이선스가 있는 표를 표시하려면 추가 Microsoft Teams [라이선스 를 참조합니다.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="e9c12-168">To see a table with the license or licenses you will need for each feature, see [Microsoft Teams add-on licensing](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="e9c12-169">관련 항목</span><span class="sxs-lookup"><span data-stu-id="e9c12-169">Related topics</span></span>

- [<span data-ttu-id="e9c12-170">비즈니스용 Skype 온라인 설정</span><span class="sxs-lookup"><span data-stu-id="e9c12-170">Set up Skype for Business Online</span></span>](/SkypeForBusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)
    
- [<span data-ttu-id="e9c12-171">클라우드 음성 메일 설정 - 관리자 도움말</span><span class="sxs-lookup"><span data-stu-id="e9c12-171">Set up Cloud Voicemail - Admin help</span></span>](set-up-phone-system-voicemail.md)
    
- <span data-ttu-id="e9c12-172">[통화 계획](set-up-calling-plans.md) 및 [](calling-plans-for-office-365.md) 통화 계획 Microsoft 365 또는 Office 365</span><span class="sxs-lookup"><span data-stu-id="e9c12-172">[Set up Calling Plans](set-up-calling-plans.md) and [Calling Plans for Microsoft 365 or Office 365](calling-plans-for-office-365.md)</span></span>
    
- [<span data-ttu-id="e9c12-173">자금 추가 및 커뮤니케이션 크레딧 관리</span><span class="sxs-lookup"><span data-stu-id="e9c12-173">Add funds and manage Communications Credits</span></span>](add-funds-and-manage-communications-credits.md)
    
  
