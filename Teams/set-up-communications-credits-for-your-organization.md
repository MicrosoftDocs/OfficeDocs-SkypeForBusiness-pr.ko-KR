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
description: '사용자 및 조직에 대해 통신 크레딧 (PSTN 소비) 청구 라이선스를 설정 하는 방법에 대해 알아봅니다. '
ms.openlocfilehash: f124cd09c0baa604b09345394d9a53ae254bbb6f
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691244"
---
# <a name="set-up-communications-credits-for-your-organization"></a><span data-ttu-id="09419-103">조직에 사용할 통신 크레딧 설정</span><span class="sxs-lookup"><span data-stu-id="09419-103">Set up Communications Credits for your organization</span></span>

<span data-ttu-id="09419-104">비즈니스용 Skype 및 Microsoft 팀에 무료 전화 번호를 사용 하려는 경우에는 통신 크레딧을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09419-104">You will need to set up Communications Credits if you would like to use toll-free numbers with Skype for Business and Microsoft Teams.</span></span> <span data-ttu-id="09419-105">또한 통화 요금제 (국내 또는 국제) 및 오디오 회의 사용자에 게 통신 크레딧을 설정 하 고 **목적지**로 전화를 걸 수 있는 기능이 필요한 경우이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="09419-105">Also, we recommend that you set up Communications Credits for your Calling Plans (Domestic or International) and Audio Conferencing users who need the ability to dial out to **any destination**.</span></span> <span data-ttu-id="09419-106">여러 국가/지역이 포함 되어 있지만 일부 대상은 통화 요금제 또는 오디오 회의 구독에 포함 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09419-106">Many countries/regions are included, but some destinations may not be included in your Calling Plan or Audio Conferencing subscriptions.</span></span> <span data-ttu-id="09419-107">통신 크레딧 청구를 설정 하지 않고 사용자에 게 **통신 크레딧** 라이선스를 할당 하지 않으면 해당 국가/지역의 통화 요금제 또는 오디오 회의 요금제에 따라 해당 사용자가 오디오 회의 모임에서 통화 하거나 전화를 걸 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="09419-107">If you don't set up Communications Credits billing and assign a **Communications Credits** license to your users and you run out minutes for your organization (depending on your Calling Plan or Audio Conferencing plan in your country/region), those users won't be able to make calls or dial out from Audio Conferencing meetings.</span></span> <span data-ttu-id="09419-108">[통신 크레딧을 확인](what-are-communications-credits.md) 하 여 권장 자금을 포함 하 여 더 많은 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09419-108">You can get more information, including recommended funding amounts, by reading [What are Communications Credits?](what-are-communications-credits.md)</span></span>
  
> [!NOTE]
> <span data-ttu-id="09419-109">비용을 확인 하려면 [여기에서 요금](https://go.microsoft.com/fwlink/p/?LinkId=799523 )을 보세요.</span><span class="sxs-lookup"><span data-stu-id="09419-109">To find out how much it costs, [see the rates here](https://go.microsoft.com/fwlink/p/?LinkId=799523 ).</span></span> 
  
## <a name="step-1-assign-an-audio-conferencing-or-calling-plan-license-to-your-users"></a><span data-ttu-id="09419-110">1 단계: 오디오 회의 또는 통화 계획 라이선스를 사용자에 게 할당</span><span class="sxs-lookup"><span data-stu-id="09419-110">Step 1: Assign an Audio Conferencing or Calling Plan license to your users</span></span>

<span data-ttu-id="09419-111">등록할 때 국가/지역에 따라 특정 수의 분이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="09419-111">When you sign up, you get a certain number of minutes depending on your country/region.</span></span> <span data-ttu-id="09419-112">[오디오 회의 및 통화 요금제](https://docs.microsoft.com/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans#select-your-country-or-region-to-see-whats-available-for-your-organization) 에서 국가 또는 지역을 검색 하 여 받을 수 있는 시간 (분)을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09419-112">You can search for your country or region in the [Country or region availability list for Audio Conferencing and Calling Plans](https://docs.microsoft.com/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans#select-your-country-or-region-to-see-whats-available-for-your-organization) to see the number of minutes you will get.</span></span> <span data-ttu-id="09419-113">해당 분을 사용한 후에는 통화가 끊깁니다.</span><span class="sxs-lookup"><span data-stu-id="09419-113">After you use those minutes, calls will be disconnected.</span></span> <span data-ttu-id="09419-114">이러한 상황이 발생 하지 않도록 하려면 통신 크레딧을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09419-114">To prevent this from happening, you need to set up Communications Credits.</span></span>
  
<span data-ttu-id="09419-115">이렇게 하려면 **오디오 회의 또는 전화 시스템 라이선스** 를 사용자에 게 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09419-115">To do so, **you need to assign an Audio Conferencing or Phone System license** to your users.</span></span>
  
- <span data-ttu-id="09419-116">사용자에 게 **오디오 회의** 라이선스를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="09419-116">Assign an **Audio Conferencing** license to your users.</span></span> <span data-ttu-id="09419-117">[Microsoft 팀 추가 기능 라이선스 할당](teams-add-on-licensing/assign-teams-add-on-licenses.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="09419-117">See [Assign Microsoft Teams add-on licenses](teams-add-on-licensing/assign-teams-add-on-licenses.md).</span></span>
    
    <span data-ttu-id="09419-118">이 라이선스를 할당 한 후에는 오디오 회의를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09419-118">After you assign this license, you will need to set up audio conferencing.</span></span> <span data-ttu-id="09419-119">단계별 지침은 [Microsoft 365 또는 Office 365에서 오디오 회의 체험 또는 구입](try-or-purchase-audio-conferencing-in-office-365-for-teams.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="09419-119">For step-by-step instructions, see [Try or purchase Audio Conferencing in Microsoft 365 or Office 365](try-or-purchase-audio-conferencing-in-office-365-for-teams.md).</span></span>
    
- <span data-ttu-id="09419-120">**전화 시스템** 및 **국내 또는 국내 및 국제** 통화 요금제 라이선스를 사용자에 게 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="09419-120">Assign **Phone System** and a **Domestic or Domestic and International** Calling Plan license to your users.</span></span> <span data-ttu-id="09419-121">[Microsoft 팀 추가 기능 라이선스 할당](teams-add-on-licensing/assign-teams-add-on-licenses.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="09419-121">See [Assign Microsoft Teams add-on licenses](teams-add-on-licensing/assign-teams-add-on-licenses.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="09419-122">통신 크레딧에는 필요 하지 않지만 **국내 통화 요금제** 또는 **국내 및 국제 통화 요금제** 라이선스도 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09419-122">Although it's not required for Communications Credits, you still need to also assign a **Domestic Calling Plan** or a **Domestic and International Calling Plan** license.</span></span>
  
    <span data-ttu-id="09419-123">이러한 라이선스를 할당 한 후에는 조직의 전화 번호를 얻은 다음 조직의 사용자에 게 해당 번호를 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09419-123">After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="09419-124">단계별 지침은 [통화 계획 설정을](set-up-calling-plans.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="09419-124">For step-by-step instructions, see [Set up Calling Plans](set-up-calling-plans.md).</span></span>
    
<span data-ttu-id="09419-125">자세한 내용은 [Microsoft 팀 추가 기능 라이선스](teams-add-on-licensing/microsoft-teams-add-on-licensing.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="09419-125">For more information, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span></span>
  
## <a name="step-2-set-up-communications-credits-for-your-organization"></a><span data-ttu-id="09419-126">2 단계: 조직의 통신 크레딧을 설정</span><span class="sxs-lookup"><span data-stu-id="09419-126">Step 2: Set up Communications Credits for your organization</span></span>

1. <span data-ttu-id="09419-127">회사 또는 학교 계정으로 [Microsoft 365 관리 센터](https://portal.office.com/Adminportal) 에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="09419-127">Sign in to the [Microsoft 365 admin center](https://portal.office.com/Adminportal) with your work or school account.</span></span>
    
2. <span data-ttu-id="09419-128">Microsoft 365 관리 센터의 왼쪽 탐색 모음에서 **청구**  >  **구입 서비스로**이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="09419-128">In the left navigation of the Microsoft 365 admin center, go to **Billing** > **Purchase Services**.</span></span> <span data-ttu-id="09419-129">아래로 스크롤하여 **추가 기능**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="09419-129">Scroll down and select **Add-Ons**.</span></span>

3. <span data-ttu-id="09419-130">**통신 크레딧을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="09419-130">Select **Communications Credits**.</span></span>
    
4. <span data-ttu-id="09419-131">**커뮤니케이션 크레딧** 신청 페이지에서 정보를 입력 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="09419-131">On the **Communications Credits** subscription page, fill in your information, and then click **Next**:</span></span>
    
   - <span data-ttu-id="09419-132">**자금 추가** 계정에 추가 하려는 금액을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="09419-132">**Add funds** Enter the amount that you want to add to your account.</span></span> <span data-ttu-id="09419-133">자동 충전을 사용 하지 않는 경우, 이러한 자금을 고갈 한 후에는 통신 크레딧을 사용 하 여 사용 하도록 설정 된 통화 기능이 중단 됩니다 (예: 인바운드 무료 무료 서비스).</span><span class="sxs-lookup"><span data-stu-id="09419-133">If you don't enable auto-recharge, once these funds are depleted, calling capabilities that are enabled using Communications Credits will be disrupted (such as inbound toll-free service).</span></span> <span data-ttu-id="09419-134">잔액이 0 (영)에 도달할 때마다 통신 크레딧을 수동으로 보충할 하지 않도록 하려면 자동 충전 기능을 사용 하도록 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="09419-134">To avoid having to manually replenish your Communications Credits balance each time your balance reaches 0 (zero), we recommend you enable the auto-recharge feature.</span></span>
    
   - <span data-ttu-id="09419-135">**자동 충전** 자동 충전을 사용 하도록 설정 하면 잔액이 설정한 임계값 아래로 떨어질 때 자동으로 계정이 다시 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="09419-135">**Auto-recharge** Enabling auto-recharge will automatically refill your account when the balance falls below the threshold that you set.</span></span>
    
     <span data-ttu-id="09419-136">통신 크레딧 잔액이 0 (영)에 도달 해야 하는 경우에는 **자동 충전** 설정을 사용 하 여 서비스 중단을 방지 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="09419-136">It's recommended that you use the **Auto-recharge** setting to avoid any disruption of service should your Communications Credits balance reach 0 (zero).</span></span> <span data-ttu-id="09419-137">충전이 거래에 성공 하는 경우 (예: 만료 된 신용 카드)와 통신 크레딧 잔액이 0 (영)에 도달 하면 전자 메일을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="09419-137">You will be sent an email when recharge transactions succeed, when recharge transactions fail (such as an expired credit card), and when your Communications Credits balance reaches 0 (zero).</span></span>
    
   - <span data-ttu-id="09419-138">**충전 금액** 아래의 트리거 금액에 도달 하면 계정에 추가 하려는 **충전** 기준 상자에 금액을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="09419-138">**Recharge amount** Enter the amount in the **Recharge with** box that you want added to your account once it reaches the trigger amount below.</span></span>
    
   - <span data-ttu-id="09419-139">**트리거 금액** 자동 충전을 ' *시작* ' 하는 데 사용 되는 **잔액이 아래 상자 아래로 떨어질 때** 의 크기를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="09419-139">**Trigger amount** Enter the amount in **When the balance falls below** box that will be used to ' *trigger*  ' the auto-recharge.</span></span> <span data-ttu-id="09419-140">잔액이이 금액 미만으로 떨어지면 사용자의 계정에 충전 금액이 자동으로 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="09419-140">Once your balance falls below this amount, the recharge amount will be added automatically to your account.</span></span>

      > [!NOTE]
     > <span data-ttu-id="09419-141">결제는 서비스를 사용 하는 경우 Microsoft에서 게시 한 요금으로 통신 크레딧에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="09419-141">Funds will be applied only to Communications Credits at Microsoft published rates when the services are used.</span></span> <span data-ttu-id="09419-142">12 개월 내에 사용 되지 않은 자금은 모두 만료 되 고 forfeited 됩니다.</span><span class="sxs-lookup"><span data-stu-id="09419-142">Any funds not used within 12 months of the purchase date will expire and be forfeited.</span></span> 
     > 
     > <span data-ttu-id="09419-143">커뮤니케이션 크레딧에 대 한 월간 청구는 alloted 펀드를 사용 하는 경우에만 적용 되며, 월간 사용량을 확인 하는 방법에 대 한 자세한 내용은 비즈니스용 [SKYPE PSTN 사용 보고서](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="09419-143">Monthly billing for Communication Credits will only be applied if the alloted fund has been used, to learn how to check your monthly usage, read [Skype for Business PSTN usage report](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report)</span></span>
    
5. <span data-ttu-id="09419-144">결제 정보를 입력 하 고 **주문을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="09419-144">Enter your payment information and click **Place order**.</span></span>
    >[!IMPORTANT]
    ><span data-ttu-id="09419-145">볼륨 라이선스 고객 인 경우 결제를 위해 엔터프라이즈 계약 번호를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09419-145">If you are a volume licensing customer, you may choose your enterprise agreement number for payment.</span></span> <span data-ttu-id="09419-146">여러 엔터프라이즈 계약 번호를 사용 하는 경우 결제에 사용할 엔터프라이즈 계약을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09419-146">If you have multiple enterprise agreement numbers, you will be able to select which enterprise agreement you would like to use for payment.</span></span> <span data-ttu-id="09419-147">또한 회사 계약 번호와 연결할 구매 주문 번호를 지정할 기회가 주어 집니다 (해당 하는 경우).</span><span class="sxs-lookup"><span data-stu-id="09419-147">You will also be given an opportunity to specify a purchase order number to associate with the enterprise agreement number (if applicable).</span></span>
    
<span data-ttu-id="09419-148">각 조직은 서로 다른 통화 계획 볼륨 및 고려 요금을 사용 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="09419-148">Each organization will have a different usage of Calling Plan volume and rates to consider.</span></span> <span data-ttu-id="09419-149">현재 서비스 공급자 로부터이 유형의 사용 데이터를 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09419-149">You will need to get this type of usage data from your current service provider.</span></span> <span data-ttu-id="09419-150">이미 비즈니스용 Skype Online을 해당 서비스 공급자로 사용 하는 조직은 **Microsoft 팀 관리 센터**의  >  **Reports**  >  **PSTN 사용 정보** 보고서에서 사용 현황 데이터를 검토 하 여 이용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09419-150">Organizations already using Skype for Business Online already as their service provider can get usage data by reviewing it in the **Microsoft Teams admin center** > **Reports** > **PSTN usage details** report.</span></span>
  
<span data-ttu-id="09419-151">통신 크레딧을 설정 하는 경우 조직의 통화 사용량을 조사 하 여 필요한 금액을 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09419-151">When you are setting up Communications Credits, you will need to investigate call usage for your organization to determine the amounts you need.</span></span> <span data-ttu-id="09419-152">**PSTN 사용** 정보 보고서를 검토 하 여 통화 사용 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09419-152">You can get call usage information by reviewing the **PSTN usage details** report.</span></span> <span data-ttu-id="09419-153">이 보고서를 사용 하면 데이터를 저장 하거나 사용자 지정 보고서를 만들어야 할 경우 Excel로 통화 데이터 레코드를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09419-153">This report lets you export the call data records to Excel if you need to store the data or create custom reports.</span></span> <span data-ttu-id="09419-154">사용 현황을 확인 하는 방법에 대해 알아보려면 [PSTN 사용 현황 보고서](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report)를 읽어보십시오.</span><span class="sxs-lookup"><span data-stu-id="09419-154">To learn how to see usage, read [PSTN usage report](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report).</span></span>
  
## <a name="step-3-assign-a-communications-credits-license-to-users"></a><span data-ttu-id="09419-155">3 단계: 사용자에 게 통신 크레딧 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="09419-155">Step 3: Assign a Communications Credits license to users</span></span>

1. <span data-ttu-id="09419-156">회사 또는 학교 계정으로 [Microsoft 365 관리 센터](https://portal.office.com/Adminportal) 에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="09419-156">Sign in to the [Microsoft 365 admin center](https://portal.office.com/Adminportal) with your work or school account.</span></span>
    
2. <span data-ttu-id="09419-157">Microsoft 365 관리 센터의 왼쪽 탐색 창에서 **사용자**  >  **활성 사용자**로 이동한 다음 목록에서 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="09419-157">In the left navigation of the Microsoft 365 admin center, go to **Users** > **Active users**, and then select a user from the list.</span></span>
    
3. <span data-ttu-id="09419-158">**라이선스 및 앱**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="09419-158">Choose **Licenses and Apps**.</span></span>
    
4. <span data-ttu-id="09419-159">이 라이선스를 할당 하려면 **통신 크레딧을** **설정으로 전환** 하 고 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="09419-159">Toggle **Communications Credits** to **On** to assign this license, and then select **Save**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="09419-160">**Enterprise E5** 라이선스를 할당 받은 사용자가 있는 경우에도이 작업을 수행 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="09419-160">Even if you have users who are assigned an **Enterprise E5** license, it's still recommended that you do this.</span></span>

    > [!TIP]
    > <span data-ttu-id="09419-161">[Powershell](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps) 을 사용 하 여 한 명령으로 여러 사용자에 게 라이선스와 앱을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09419-161">You can use [Powershell](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps) to assign licenses and apps to multiple users with one command.</span></span>
  
## <a name="want-to-know-about-plans-and-pricing"></a><span data-ttu-id="09419-162">요금제 및 가격에 대해 알고 싶으세요?</span><span class="sxs-lookup"><span data-stu-id="09419-162">Want to know about plans and pricing?</span></span>

<span data-ttu-id="09419-163">다음 링크 중 하나를 방문 하 여 요금제 및 가격을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09419-163">You can see the plans and pricing by visiting one of the following links:</span></span>
  
- [<span data-ttu-id="09419-164">통화 플랜</span><span class="sxs-lookup"><span data-stu-id="09419-164">Calling Plans</span></span>](https://go.microsoft.com/fwlink/?LinkId=799761 )
    
- [<span data-ttu-id="09419-165">오디오 회의 계획</span><span class="sxs-lookup"><span data-stu-id="09419-165">Audio Conferencing Plans</span></span>](https://go.microsoft.com/fwlink/?LinkId=799762 )
    
- [<span data-ttu-id="09419-166">전화 시스템 요금제</span><span class="sxs-lookup"><span data-stu-id="09419-166">Phone System Plans</span></span>](https://go.microsoft.com/fwlink/?LinkId=799763)
    
<span data-ttu-id="09419-167">[Microsoft 365 관리 센터에 로그인](https://portal.office.com/adminportal/home?add=sub&amp;adminportal=1#/catalog) 하 여 정보를 볼 수 있으며, **결제**플랜으로 진행 하 여  >  **Subscriptions**  >  **구독을 추가할**수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09419-167">You can also see information by [signing in to the Microsoft 365 admin center](https://portal.office.com/adminportal/home?add=sub&amp;adminportal=1#/catalog) and going to **Billing** > **Subscriptions** > **Add subscriptions**.</span></span>
  
<span data-ttu-id="09419-168">각 기능에 필요한 라이선스가 나 라이선스가 포함 된 테이블을 보려면 [Microsoft 팀 추가 기능 라이선스](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="09419-168">To see a table with the license or licenses you will need for each feature, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="09419-169">관련 항목</span><span class="sxs-lookup"><span data-stu-id="09419-169">Related topics</span></span>

- [<span data-ttu-id="09419-170">비즈니스용 Skype 온라인 설정</span><span class="sxs-lookup"><span data-stu-id="09419-170">Set up Skype for Business Online</span></span>](/SkypeForBusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)
    
- [<span data-ttu-id="09419-171">클라우드 음성 메일 설정 - 관리자 도움말</span><span class="sxs-lookup"><span data-stu-id="09419-171">Set up Cloud Voicemail - Admin help</span></span>](set-up-phone-system-voicemail.md)
    
- <span data-ttu-id="09419-172">[Microsoft 365 또는 Office 365에 대 한](calling-plans-for-office-365.md) [통화 계획](set-up-calling-plans.md) 및 통화 계획 설정</span><span class="sxs-lookup"><span data-stu-id="09419-172">[Set up Calling Plans](set-up-calling-plans.md) and [Calling Plans for Microsoft 365 or Office 365](calling-plans-for-office-365.md)</span></span>
    
- [<span data-ttu-id="09419-173">자금 추가 및 커뮤니케이션 크레딧 관리</span><span class="sxs-lookup"><span data-stu-id="09419-173">Add funds and manage Communications Credits</span></span>](add-funds-and-manage-communications-credits.md)
    
  
 
