---
title: 공용 영역 전화 설정
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
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
- NOCSH
ms.custom:
- Phone System
description: 배포 단계에 대해 알아보고, 올바른 펌웨어를 다운로드하고, 필요한 경우 업데이트하고, 라이선스를 할당하고, 공용 영역 전화에 대한 설정을 구성합니다.
ms.openlocfilehash: 02cab34b4a1f220e8f28ceeee794470191582704
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220408"
---
# <a name="set-up-common-area-phones"></a><span data-ttu-id="eee3b-103">공통 지역 전화 설정</span><span class="sxs-lookup"><span data-stu-id="eee3b-103">Set up common area phones</span></span>
<span data-ttu-id="eee3b-104">공용 영역 전화(CAP)는 일반적으로 대기실 또는 많은 사람들이 사용할 수 있는 다른 영역에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="eee3b-104">A common area phone (CAP) is typically placed in an area like a lobby or another area that is available to a lot of people.</span></span> <span data-ttu-id="eee3b-105">예를 들어 수신 지역 전화, 문 전화 또는 회의실 전화, CAP는 사용자가 아닌 장치로 설정되고 네트워크에 자동으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="eee3b-105">For example, a reception area phone, door phone or meeting room phone, CAPs are set up as devices rather than users and automatically sign into a network.</span></span> <span data-ttu-id="eee3b-106">아래 단계에서는 조직에 대해 이러한 유형의 휴대폰을 배포할 수 있도록 통화 요금제로 전화 시스템에 대한 계정을 설정하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="eee3b-106">In the steps below, we’ll help you set up an account for Phone System with Calling Plans so you can deploy these types of phones for your organization.</span></span>

## <a name="prerequisites-for-common-area-phones"></a><span data-ttu-id="eee3b-107">공용 지역 전화에 대한 전제적 준비</span><span class="sxs-lookup"><span data-stu-id="eee3b-107">Prerequisites for common area phones</span></span>

<span data-ttu-id="eee3b-108">가장 먼저 해야 할 일은 다음이 있는지 확인하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="eee3b-108">The first thing you need to do is to confirm that you have the following:</span></span>

- <span data-ttu-id="eee3b-109">일반 지역 전화 라이선스 및 통화 플랜을 구매합니다.</span><span class="sxs-lookup"><span data-stu-id="eee3b-109">Purchase Common Area Phone license and a Calling Plan.</span></span>
- <span data-ttu-id="eee3b-110">승인된 휴대폰을 검색하여 구입합니다(여기에서 목록 [보기).](deploying-skype-for-business-online-phones.md)</span><span class="sxs-lookup"><span data-stu-id="eee3b-110">Search for and buy approved phones (view the list [here](deploying-skype-for-business-online-phones.md)).</span></span>
- <span data-ttu-id="eee3b-111">휴대폰에서 펌웨어를 업데이트합니다(이 항목에서 지원되는 펌웨어 [참조).](getting-phones-for-skype-for-business-online.md)</span><span class="sxs-lookup"><span data-stu-id="eee3b-111">Update the firmware on your phones (See supported firmware [in this topic](getting-phones-for-skype-for-business-online.md)).</span></span>  <span data-ttu-id="eee3b-112">다음을 수행하여 휴대폰에서 펌웨어를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eee3b-112">You can check the firmware on you phone by doing this:</span></span>
  - <span data-ttu-id="eee3b-113">**Polycom VVX 휴대폰:** 설정  >  **상태 플랫폼** 애플리케이션  >    >    >  **주로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="eee3b-113">**Polycom VVX phones**: Go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span></span>
  - <span data-ttu-id="eee3b-114">**Yealink 휴대폰:** 주 전화 **화면에서** 상태로 이동</span><span class="sxs-lookup"><span data-stu-id="eee3b-114">**Yealink phones**: Go to **Status** on the main phone screen.</span></span>
  - <span data-ttu-id="eee3b-115">**AudioCodes 휴대폰:** 시작 화면에서 **메뉴** 디바이스 상태  >    >  **펌웨어** 버전으로 이동</span><span class="sxs-lookup"><span data-stu-id="eee3b-115">**AudioCodes phones**: Go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span></span>
  - <span data-ttu-id="eee3b-116">**LPE(Lync Phone Edition)** 전화기: 시작 화면에서 **메뉴**  >   시스템 정보로 이동</span><span class="sxs-lookup"><span data-stu-id="eee3b-116">**Lync Phone Edition (LPE) phones**: Go to **Menu** > **System Information** from the start screen.</span></span>

    <span data-ttu-id="eee3b-117">펌웨어 업데이트는 비즈니스용 Skype 서비스에서 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="eee3b-117">Firmware updates are managed by the Skype for Business Service.</span></span> <span data-ttu-id="eee3b-118">모든 비즈니스용 Skype 인증 휴대폰 펌웨어는 비즈니스용 Skype 업데이트 서버에 업로드됩니다. 장치 업데이트는 기본적으로 모든 휴대폰에서 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="eee3b-118">Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.</span></span>

    <span data-ttu-id="eee3b-119">휴대폰의 비활성 시간 및 폴링 간격에 따라 휴대폰은 자동으로 인증된 최신 빌드를 다운로드하여 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="eee3b-119">Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds.</span></span> <span data-ttu-id="eee3b-120">[Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) cmdlet을 사용하고 *EnableDeviceUpdate* 매개 변수를 으로 설정하여 디바이스 업데이트 설정을 사용하지 않도록 설정할 수 `false` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eee3b-120">You can disable the device update settings by using the  [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) cmdlet and setting the *EnableDeviceUpdate* parameter to `false`.</span></span>

## <a name="setting-up-a-common-area-phone"></a><span data-ttu-id="eee3b-121">공용 영역 전화 설정</span><span class="sxs-lookup"><span data-stu-id="eee3b-121">Setting up a Common Area Phone</span></span>
<span data-ttu-id="eee3b-122">다음 단계를 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eee3b-122">You will need to follow these steps:</span></span>

### <a name="step-1---buy-the-licenses"></a><span data-ttu-id="eee3b-123">1단계 - 라이선스 구입</span><span class="sxs-lookup"><span data-stu-id="eee3b-123">Step 1 - Buy the licenses</span></span>
1. <span data-ttu-id="eee3b-124">관리 센터에서 청구 구매 서비스로 이동하고  >  다른 계획을 **추가합니다.**</span><span class="sxs-lookup"><span data-stu-id="eee3b-124">In the admin center, go to **Billing** > **Purchase services**, and add **Other plans**.</span></span>

    ![CAP-license.png](../../images/cap-license.png)
2. <span data-ttu-id="eee3b-126">이제 체크 **아웃** 페이지에서 일반 지역 전화 > 클릭하고 지금  >   구입을 **클릭합니다.** </span><span class="sxs-lookup"><span data-stu-id="eee3b-126">Click on **Common Area Phone** > **Buy now** > on the **Checkout** page click on **Buy now**.</span></span>
3. <span data-ttu-id="eee3b-127">추가 기능 **구독을** 확장하려면 클릭한 다음 클릭하여 통화 요금제 구입을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="eee3b-127">Click on to expand **Add-on subscriptions** and then click on to buy a Calling Plan.</span></span> <span data-ttu-id="eee3b-128">국내 통화 요금제 또는 **국내** 및 국제 통화 요금제 중 하나를 **선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="eee3b-128">Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.</span></span>

> [!Note]
> <span data-ttu-id="eee3b-129">전화 시스템 라이선스가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eee3b-129">You don't need a Phone System license.</span></span> <span data-ttu-id="eee3b-130">공용 영역 전화 **라이선스에 포함되어** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eee3b-130">It's included with the **Common Area Phone** license.</span></span>

<span data-ttu-id="eee3b-131">라이선스에 대한 자세한 내용은 비즈니스용 Skype 및 Microsoft Teams 추가 기능 라이선스를 [참조하세요.](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="eee3b-131">For more info on licenses, see [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

### <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a><span data-ttu-id="eee3b-132">2단계 - 휴대폰에 대한 새 사용자 계정 만들기 및 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="eee3b-132">Step 2 - Create a new user account for the phone and assign the licenses</span></span>
1. <span data-ttu-id="eee3b-133">관리 센터에서 사용자   >  **활성 사용자**  >  **추가로 이동하여 사용자를 추가합니다.**</span><span class="sxs-lookup"><span data-stu-id="eee3b-133">In the admin center, go to **Users** > **Active Users** > **Add a user**.</span></span>
2. <span data-ttu-id="eee3b-134">이름의  경우 "Main"과 같은 사용자 이름을 입력하고 두 번째 이름은 "수신"을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="eee3b-134">Put in a **User name** like “Main" for the first name and "Reception” for the second name.</span></span>
3. <span data-ttu-id="eee3b-135">"주  수신"처럼 자동으로 표시되지 않는 경우 표시 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="eee3b-135">Put in a **Display name** if it doesn't autogenerate one like "Main Reception".</span></span>
4. <span data-ttu-id="eee3b-136">"MainReception" 또는 "Mainlobby"처럼 사용자 이름을 입력합니다. </span><span class="sxs-lookup"><span data-stu-id="eee3b-136">Put in a **User name** like "MainReception" or "Mainlobby".</span></span>
5. <span data-ttu-id="eee3b-137">일반 지역 전화의 경우 암호를 수동으로 설정하거나 일반 지역 전화에 대해 동일한 암호를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="eee3b-137">For common area phones, you might want to set a password manually or have the same password for all of you common area phones.</span></span> <span data-ttu-id="eee3b-138">또한 이 사용자가 처음 로그인할 때 암호를 변경하도록 **선택하지 않는 것이 생각할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="eee3b-138">Also, you might think about unselecting **Make this user change their password when they first sign in**.</span></span>
6. <span data-ttu-id="eee3b-139">그래도 이 사용자에게 라이선스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="eee3b-139">If you are still there, assign the licenses to this user.</span></span> <span data-ttu-id="eee3b-140">같은 페이지에서 제품 라이선스를 **확장하려면 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="eee3b-140">On the same page, click to expand **Product licenses**.</span></span> <span data-ttu-id="eee3b-141">다음을 켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eee3b-141">Turn on the following:</span></span>
   - <span data-ttu-id="eee3b-142">공용 지역 전화</span><span class="sxs-lookup"><span data-stu-id="eee3b-142">Common Area Phone</span></span>
   - <span data-ttu-id="eee3b-143">그런 다음 국내 통화  요금제 또는 국내 및 국제 통화 요금제 중 하나를 **선택해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="eee3b-143">Then you need to pick either a **Domestic Calling Plan** or a Domestic and **International Calling Plan**.</span></span>

     <span data-ttu-id="eee3b-144">라이선스 할당은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="eee3b-144">Assigning the licenses will look like:</span></span>

     ![TurnOnCapLicense.png](../../images/cap-license-turn-on.png)

     > [!Note]
     > <span data-ttu-id="eee3b-146">비즈니스용 Skype 요금제 2는 일반 지역 전화 **라이선스에 포함되어** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eee3b-146">Just so you know, Skype for Business Plan 2 is included with the **Common Area Phone** license.</span></span>

<span data-ttu-id="eee3b-147">자세한 내용은 사용자 [추가를 참조합니다.](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec)</span><span class="sxs-lookup"><span data-stu-id="eee3b-147">For more details, see [Add a user](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span>

### <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a><span data-ttu-id="eee3b-148">3단계 - 일반 지역 전화 사용자 계정에 전화 번호 할당</span><span class="sxs-lookup"><span data-stu-id="eee3b-148">Step 3 - Assign a phone number to the Common Area Phone user account</span></span>

<span data-ttu-id="eee3b-149">![비즈니스용 Skype 관리 센터를 사용하여 사용자에게 비즈니스용 Skype 로고를 표시하는 아이콘 ](../../images/sfb-logo-30x30.png) </span><span class="sxs-lookup"><span data-stu-id="eee3b-149">![An icon showing the Skype for Business logo](../../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>

1. <span data-ttu-id="eee3b-150">관리 센터에서 >   >  **비즈니스용 Skype를 관리합니다.**</span><span class="sxs-lookup"><span data-stu-id="eee3b-150">In the admin center > **Admin centers** > **Skype for Business**.</span></span>
2. <span data-ttu-id="eee3b-151">비즈니스용 **Skype 관리**  >   **센터의 음성** 전화  >  **번호.**</span><span class="sxs-lookup"><span data-stu-id="eee3b-151">In the **Skype for Business admin center** >  **Voice** > **Phone numbers**.</span></span>
3. <span data-ttu-id="eee3b-152">전화 번호 목록에서 번호를 선택하고 할당을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="eee3b-152">Select a number from the list of phone numbers and click **Assign**.</span></span>
4. <span data-ttu-id="eee3b-153">할당 **페이지의** **음성** 사용자 상자에 전화에 사용되는 사용자의 이름을 입력한 다음 음성 사용자  선택 드롭다운에서 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eee3b-153">On the **Assign** page, in the **Voice user** box enter the name of the user that is used for the phone then select the user in the **Select a voice user** drop down.</span></span>
5. <span data-ttu-id="eee3b-154">여기에 있는 동안 긴급 주소를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eee3b-154">While you're there you will need to add an emergency address.</span></span> <span data-ttu-id="eee3b-155">검색한 후 긴급  주소 선택 아래에서 적합한 주소를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eee3b-155">Once you search, look under the **Select emergency address** to pick the right one for you.</span></span>
6. <span data-ttu-id="eee3b-156">**저장을** 클릭하면 사용자가 다음과 같이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eee3b-156">Click **Save** and your user should look like this:</span></span>

    ![cap-user-number.png](../../images/cap-user-number.png)

   > [!Note]
   > <span data-ttu-id="eee3b-158">사용자는 전화 시스템 라이선스가  적용된 경우만 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eee3b-158">Users will only show up if they have a **Phone System** licence applied.</span></span> <span data-ttu-id="eee3b-159">방금 이 경우 사용자가 목록에 표시하는 데 약간의 시간이 걸리는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eee3b-159">If you just did this, then sometimes it takes a bit for the user to show up in the list.</span></span>

<span data-ttu-id="eee3b-160">자세한 내용은 사용자의 전화 번호 [보기를 참조합니다.](/microsoftteams/getting-phone-numbers-for-your-users)</span><span class="sxs-lookup"><span data-stu-id="eee3b-160">For more stuff, see [Getting phone numbers for your users](/microsoftteams/getting-phone-numbers-for-your-users).</span></span>

<span data-ttu-id="eee3b-161">궁금한 경우 다른 통신 사업자 및 "포트"에 있는전화 번호를 옮기거나 Microsoft 365 또는 Office 365로 이전할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eee3b-161">If you're wondering, you can also take your phone number that you have with another carrier and "*port*" or transfer them over to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="eee3b-162">Teams로 [전화 번호 이전을 참조합니다.](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams)</span><span class="sxs-lookup"><span data-stu-id="eee3b-162">See, [Transfer phone numbers to Teams](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams).</span></span>

### <a name="step-4---setting-up-your-phone"></a><span data-ttu-id="eee3b-163">4단계 - 휴대폰 설정</span><span class="sxs-lookup"><span data-stu-id="eee3b-163">Step 4 - Setting up your phone</span></span>

<span data-ttu-id="eee3b-164">**휴대폰에서 모드 설정**</span><span class="sxs-lookup"><span data-stu-id="eee3b-164">**Setting the mode on a phone**</span></span>

<span data-ttu-id="eee3b-165">일반 지역 전화 모드가 켜져 있어야 하는 전화 또는  전화기입니다.</span><span class="sxs-lookup"><span data-stu-id="eee3b-165">The phone or phones you have must have the **Common Area Phone mode** turned on.</span></span> <span data-ttu-id="eee3b-166">해당 작업을 확인하여 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eee3b-166">You might want to check on that to make sure they do.</span></span>

<span data-ttu-id="eee3b-167">**Polycom VVX 휴대폰을 설정하는 방법에 대한 예제는 다음과 같습니다.**</span><span class="sxs-lookup"><span data-stu-id="eee3b-167">**Here's an example for how to set up a Polycom VVX phone**</span></span>

- <span data-ttu-id="eee3b-168">다음 단계를 수행하여 Polycom VVX에 공통 영역 전화 모드를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="eee3b-168">Enable Common Area Phone mode for the Polycom VVX by following these steps:</span></span>
    1. <span data-ttu-id="eee3b-169">브라우저에서 CAP 모드를 사용하도록 설정할 수 있도록 웹 인터페이스에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="eee3b-169">In your browser, connect to the web interface so that you can enable CAP mode.</span></span>
    2. <span data-ttu-id="eee3b-170">그런 다음 설정으로 **이동하여** 비즈니스용 **Skype** 설정 옵션에서 일반 지역 **전화(Common Area Phone)를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="eee3b-170">Then go to **Setting**  and in the **Skype for Business Setting** option, select **Common Area Phone**.</span></span>
    3. <span data-ttu-id="eee3b-171">예를 **클릭하여** 설정을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="eee3b-171">Click **Yes** to save your settings.</span></span>

- <span data-ttu-id="eee3b-172">이제 CAP 모드를 사용하도록 설정하고 휴대폰의 디스플레이를 사용하여 휴대폰을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="eee3b-172">Now that CAP mode is enabled, set up the phone using the phone's display.</span></span> <span data-ttu-id="eee3b-173">표시에는 **CaAP가 사용하도록 설정되어 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="eee3b-173">The display should show **CaAP is enabled**.</span></span> <span data-ttu-id="eee3b-174">그런 다음, 다음을 합니다.</span><span class="sxs-lookup"><span data-stu-id="eee3b-174">Then do the following:</span></span>

    1. <span data-ttu-id="eee3b-175">설정을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="eee3b-175">Click **Settings**.</span></span>
    2. <span data-ttu-id="eee3b-176">고급을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="eee3b-176">Select **Advanced**.</span></span>
    3. <span data-ttu-id="eee3b-177">암호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="eee3b-177">Enter the password.</span></span>
    4. <span data-ttu-id="eee3b-178">관리 **설정에서** **일반 영역 전화 설정을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="eee3b-178">In **Administration settings**, select **Common Area Phone Settings**.</span></span>
    5. <span data-ttu-id="eee3b-179">**CAP 및** CAP 관리자 모드를 **사용하도록 설정**</span><span class="sxs-lookup"><span data-stu-id="eee3b-179">Enable **CAP** and **CAP Admin Mode**.</span></span>
    6. <span data-ttu-id="eee3b-180">[구성 **저장]을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="eee3b-180">Click **Save Config**.</span></span>

- <span data-ttu-id="eee3b-181">이제 휴대폰이 준비되어 홈 화면에서 로그인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eee3b-181">Ok, now your phone is ready so you can sign in on the home screen.</span></span>

    1. <span data-ttu-id="eee3b-182">비즈니스용 Skype의 설정  >  **기능을 선택하여**  >  **로그인합니다.**</span><span class="sxs-lookup"><span data-stu-id="eee3b-182">Sign in by selecting **Settings** > **Features** > **Skype for Business.**</span></span>
    2. <span data-ttu-id="eee3b-183">사용자 **자격 증명을 선택하고** **CAP(웹** 로그인)를 선택하여 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="eee3b-183">Select **User Credentials**, and select **web sign-in (CAP)** to generate a code.</span></span>
    3. <span data-ttu-id="eee3b-184">[프로비전 포털로 이동하고](https://aka.ms/skypecap)관리자로 **로그인합니다.**</span><span class="sxs-lookup"><span data-stu-id="eee3b-184">Go to the [provisioning portal](https://aka.ms/skypecap), and sign in as **admin**.</span></span>
    4. <span data-ttu-id="eee3b-185">표시 이름(예: 주 수신)을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="eee3b-185">Enter the display name (for example, Main Reception).</span></span>

       > [!Note]
       > <span data-ttu-id="eee3b-186">공용 **영역 전화 검색만** 선택된 경우 확인란의 선택을 취소하고 다시 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="eee3b-186">If **Search for Common Area Phones only** is checked, clear the checkbox and search again.</span></span>

    5. <span data-ttu-id="eee3b-187">페어링 코드 창에서 휴대폰에 표시된 코드를 입력하고 프로비전을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="eee3b-187">In the pairing code window, enter the code displayed on the phone and click **Provision**.</span></span>

        <span data-ttu-id="eee3b-188">이 마지막 단계를 수행하면 휴대폰이 자동으로 로그인됩니다.</span><span class="sxs-lookup"><span data-stu-id="eee3b-188">Following this last step, the phone should sign in automatically.</span></span>


> [!NOTE]
> <span data-ttu-id="eee3b-189">CAP 프로비전 사이트는 CAP 계정의 암호를 임의 암호로 다시 설정하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eee3b-189">The CAP provisioning site states it will reset the CAP account's password to a random password.</span></span> <span data-ttu-id="eee3b-190">CAP가 참조하는 계정은 AAD(Azure Active Directory) 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="eee3b-190">Take note that the account the CAP is referring is the Azure Active Directory (AAD) account.</span></span> <span data-ttu-id="eee3b-191">AAD에서만 계정을 만든 경우 프로세스는 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="eee3b-191">If you created the account in AAD only then the process is straightforward.</span></span> <span data-ttu-id="eee3b-192">AAD에 On-Premises Active Directory를 동기화하고 타사 IDP 또는 ADFS를 사용하는 경우 CAP 프로비전이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="eee3b-192">If you have synced an on premises Active Directory to AAD and you use a third-party IDP or ADFS, CAP provisioning will fail.</span></span> <span data-ttu-id="eee3b-193">이 경우 CAP 프로비전이 작동하려면 Microsoft 365 또는 Office 365/Azure Active Directory 계정(예: onmicrosoft.com 도메인이 있는 **계정)만** 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eee3b-193">In this case, you need to use a Microsoft 365 or Office 365/Azure Active Directory account only (for example, an account with **onmicrosoft.com** domain) for CAP provisioning to work.</span></span>


### <a name="related-topics"></a><span data-ttu-id="eee3b-194">관련 항목</span><span class="sxs-lookup"><span data-stu-id="eee3b-194">Related topics</span></span>

- <span data-ttu-id="eee3b-195">비즈니스용 Skype Online 휴대폰 배포에서 사용 가능한 전화에 [대해 자세히 알아보면 됩니다.](deploying-skype-for-business-online-phones.md)</span><span class="sxs-lookup"><span data-stu-id="eee3b-195">Learn more about available phones at [Deploying Skype for Business Online phones](deploying-skype-for-business-online-phones.md).</span></span>
- [<span data-ttu-id="eee3b-196">비즈니스용 Skype Online 휴대폰 받기</span><span class="sxs-lookup"><span data-stu-id="eee3b-196">Getting phones for Skype for Business Online</span></span>](getting-phones-for-skype-for-business-online.md)


