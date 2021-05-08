---
title: 공용 영역 휴대폰 설정
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
description: 배포 단계에 대해 알아보고, 올바른 펌웨어를 다운로드하고, 필요한 경우 업데이트하고, 라이선스를 할당하고, 공통 영역 휴대폰에 대한 설정을 구성합니다.
ms.openlocfilehash: 4fd45f446d71e581305f7e596c7eacc62f54f8ca
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237354"
---
# <a name="set-up-common-area-phones"></a><span data-ttu-id="9b92d-103">공통 지역 전화 설정</span><span class="sxs-lookup"><span data-stu-id="9b92d-103">Set up common area phones</span></span>

[!INCLUDE [sfbo-retirement](../../../Hub/includes/sfbo-retirement.md)]
<span data-ttu-id="9b92d-104">일반적으로 CAP(공용 영역 전화)는 많은 사람들이 사용할 수 있는 로비 또는 다른 영역과 같은 영역에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b92d-104">A common area phone (CAP) is typically placed in an area like a lobby or another area that is available to a lot of people.</span></span> <span data-ttu-id="9b92d-105">예를 들어 수신 영역 전화, 도어 전화 또는 회의실 전화, CAP는 사용자 대신 디바이스로 설정되고 네트워크에 자동으로 로그인됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b92d-105">For example, a reception area phone, door phone or meeting room phone, CAPs are set up as devices rather than users and automatically sign into a network.</span></span> <span data-ttu-id="9b92d-106">아래 단계에서는 이러한 유형의 휴대폰을 조직에 배포할 수 있도록 전화 시스템 통화 요금제로 계정 설정에 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b92d-106">In the steps below, we’ll help you set up an account for Phone System with Calling Plans so you can deploy these types of phones for your organization.</span></span>

## <a name="prerequisites-for-common-area-phones"></a><span data-ttu-id="9b92d-107">공용 영역 휴대폰에 대한 전제</span><span class="sxs-lookup"><span data-stu-id="9b92d-107">Prerequisites for common area phones</span></span>

<span data-ttu-id="9b92d-108">가장 먼저 해야 할 일은 다음이 있는지 확인하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9b92d-108">The first thing you need to do is to confirm that you have the following:</span></span>

- <span data-ttu-id="9b92d-109">공용 지역 전화 라이선스 및 통화 계획을 구입합니다.</span><span class="sxs-lookup"><span data-stu-id="9b92d-109">Purchase Common Area Phone license and a Calling Plan.</span></span>
- <span data-ttu-id="9b92d-110">승인된 휴대폰을 검색하고 구입합니다(목록 [보기).](deploying-skype-for-business-online-phones.md)</span><span class="sxs-lookup"><span data-stu-id="9b92d-110">Search for and buy approved phones (view the list [here](deploying-skype-for-business-online-phones.md)).</span></span>
- <span data-ttu-id="9b92d-111">휴대폰에서 펌웨어를 업데이트합니다(이 항목에서 지원되는 펌웨어 [참조).](getting-phones-for-skype-for-business-online.md)</span><span class="sxs-lookup"><span data-stu-id="9b92d-111">Update the firmware on your phones (See supported firmware [in this topic](getting-phones-for-skype-for-business-online.md)).</span></span>  <span data-ttu-id="9b92d-112">다음을 수행하여 휴대폰에서 펌웨어를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b92d-112">You can check the firmware on you phone by doing this:</span></span>
  - <span data-ttu-id="9b92d-113">**Polycom VVX 휴대폰**: 설정 플랫폼 애플리케이션  >    >    >    >  **메인으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="9b92d-113">**Polycom VVX phones**: Go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span></span>
  - <span data-ttu-id="9b92d-114">**Yealink 휴대폰**: 기본 전화 화면에서 **상태로** 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="9b92d-114">**Yealink phones**: Go to **Status** on the main phone screen.</span></span>
  - <span data-ttu-id="9b92d-115">**AudioCodes 휴대폰**: 시작 화면에서 **메뉴**  >  **디바이스 상태** 펌웨어  >  **버전으로** 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="9b92d-115">**AudioCodes phones**: Go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span></span>
  - <span data-ttu-id="9b92d-116">**Lync 전화 버전(LPE)** 휴대폰: 시작 화면에서 메뉴 시스템 정보 메뉴로  >   이동하세요.</span><span class="sxs-lookup"><span data-stu-id="9b92d-116">**Lync Phone Edition (LPE) phones**: Go to **Menu** > **System Information** from the start screen.</span></span>

    <span data-ttu-id="9b92d-117">펌웨어 업데이트는 서비스에서 비즈니스용 Skype 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b92d-117">Firmware updates are managed by the Skype for Business Service.</span></span> <span data-ttu-id="9b92d-118">모든 비즈니스용 Skype 인증된 휴대폰의 펌웨어는 업데이트 비즈니스용 Skype 업데이트 서버에 업로드하고 기본적으로 모든 휴대폰에서 디바이스 업데이트를 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b92d-118">Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.</span></span>

    <span data-ttu-id="9b92d-119">휴대폰의 비활성 시간 및 폴링 간격에 따라 휴대폰이 자동으로 최신 인증된 빌드를 다운로드하고 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="9b92d-119">Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds.</span></span> <span data-ttu-id="9b92d-120">[Set-CsIPPhonePolicy](/powershell/module/skype/set-csipphonepolicy) cmdlet을 사용하고 *EnableDeviceUpdate* 매개 변수를 로 설정하여 디바이스 업데이트 설정을 사용하지 않도록 설정할 수 `false` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b92d-120">You can disable the device update settings by using the  [Set-CsIPPhonePolicy](/powershell/module/skype/set-csipphonepolicy) cmdlet and setting the *EnableDeviceUpdate* parameter to `false`.</span></span>

## <a name="setting-up-a-common-area-phone"></a><span data-ttu-id="9b92d-121">공용 영역 설정 전화</span><span class="sxs-lookup"><span data-stu-id="9b92d-121">Setting up a Common Area Phone</span></span>
<span data-ttu-id="9b92d-122">다음 단계를 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b92d-122">You will need to follow these steps:</span></span>

### <a name="step-1---buy-the-licenses"></a><span data-ttu-id="9b92d-123">1단계 - 라이선스 구매</span><span class="sxs-lookup"><span data-stu-id="9b92d-123">Step 1 - Buy the licenses</span></span>
1. <span data-ttu-id="9b92d-124">관리 센터에서 청구 구매 서비스로  >  **이동하고** 다른 요금제 **를 추가합니다.**</span><span class="sxs-lookup"><span data-stu-id="9b92d-124">In the admin center, go to **Billing** > **Purchase services**, and add **Other plans**.</span></span>

    ![공용 영역 라이선스의 전화 스크린샷](../../images/cap-license.png)
2. <span data-ttu-id="9b92d-126">체크 아웃 **페이지에서** 지금 전화 구입을 클릭하고 지금 >  >   **구매를 클릭합니다.** </span><span class="sxs-lookup"><span data-stu-id="9b92d-126">Click on **Common Area Phone** > **Buy now** > on the **Checkout** page click on **Buy now**.</span></span>
3. <span data-ttu-id="9b92d-127">클릭을 클릭하여 **추가 기능 구독을 확장한** 다음 클릭하여 통화 요금제 구입을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9b92d-127">Click on to expand **Add-on subscriptions** and then click on to buy a Calling Plan.</span></span> <span data-ttu-id="9b92d-128">국내 통화  계획 또는 국내 및 국제 통화 계획 **중 하나를 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="9b92d-128">Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.</span></span>

> [!Note]
> <span data-ttu-id="9b92d-129">라이선스가 필요 전화 시스템 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9b92d-129">You don't need a Phone System license.</span></span> <span data-ttu-id="9b92d-130">공용 영역 라이선스에 전화 **포함되어** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b92d-130">It's included with the **Common Area Phone** license.</span></span>

<span data-ttu-id="9b92d-131">라이선스에 대한 자세한 내용은 추가 비즈니스용 Skype 및 Microsoft Teams [를 참조하세요.](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="9b92d-131">For more info on licenses, see [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

### <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a><span data-ttu-id="9b92d-132">2단계 - 휴대폰에 대한 새 사용자 계정 만들기 및 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="9b92d-132">Step 2 - Create a new user account for the phone and assign the licenses</span></span>
1. <span data-ttu-id="9b92d-133">관리 센터에서 사용자 활성 사용자 추가 으로  >    >  **이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="9b92d-133">In the admin center, go to **Users** > **Active Users** > **Add a user**.</span></span>
2. <span data-ttu-id="9b92d-134">이름의  "Main"과 같은 사용자 이름과 두 번째 이름의 "수신"을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9b92d-134">Put in a **User name** like “Main" for the first name and "Reception” for the second name.</span></span>
3. <span data-ttu-id="9b92d-135">"Main  Reception"처럼 자동으로 자생하지 않는 경우 표시 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9b92d-135">Put in a **Display name** if it doesn't autogenerate one like "Main Reception".</span></span>
4. <span data-ttu-id="9b92d-136">"MainReception" 또는 "Mainlobby"같은 사용자 이름을 입력합니다. </span><span class="sxs-lookup"><span data-stu-id="9b92d-136">Put in a **User name** like "MainReception" or "Mainlobby".</span></span>
5. <span data-ttu-id="9b92d-137">공통 영역 휴대폰의 경우 암호를 수동으로 설정하거나 모든 공통 영역 휴대폰에 대해 동일한 암호를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b92d-137">For common area phones, you might want to set a password manually or have the same password for all of you common area phones.</span></span> <span data-ttu-id="9b92d-138">또한 이 사용자가 처음 로그인할 때 암호를 변경하도록 선택을 선택하지 않는 **것으로 생각할 수도 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="9b92d-138">Also, you might think about unselecting **Make this user change their password when they first sign in**.</span></span>
6. <span data-ttu-id="9b92d-139">여전히 있는 경우 이 사용자에게 라이선스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="9b92d-139">If you are still there, assign the licenses to this user.</span></span> <span data-ttu-id="9b92d-140">동일한 페이지에서 제품 **라이선스를 확장하려면 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="9b92d-140">On the same page, click to expand **Product licenses**.</span></span> <span data-ttu-id="9b92d-141">다음을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9b92d-141">Turn on the following:</span></span>
   - <span data-ttu-id="9b92d-142">공용 영역 전화</span><span class="sxs-lookup"><span data-stu-id="9b92d-142">Common Area Phone</span></span>
   - <span data-ttu-id="9b92d-143">그런 다음 국내 통화  계획 또는 국내 및 국제 통화 계획을 **선택해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="9b92d-143">Then you need to pick either a **Domestic Calling Plan** or a Domestic and **International Calling Plan**.</span></span>

     <span data-ttu-id="9b92d-144">라이선스 할당은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9b92d-144">Assigning the licenses will look like:</span></span>

     ![TurnOnCapLicense.png](../../images/cap-license-turn-on.png)

     > [!Note]
     > <span data-ttu-id="9b92d-146">알다시 비즈니스용 Skype 계획 2는 공용 영역 라이선스에 전화 **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="9b92d-146">Just so you know, Skype for Business Plan 2 is included with the **Common Area Phone** license.</span></span>

<span data-ttu-id="9b92d-147">자세한 내용은 사용자 추가 [를 참조합니다.](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec)</span><span class="sxs-lookup"><span data-stu-id="9b92d-147">For more details, see [Add a user](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span>

### <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a><span data-ttu-id="9b92d-148">3단계 - 공용 영역 사용자 계정에 전화 전화 할당</span><span class="sxs-lookup"><span data-stu-id="9b92d-148">Step 3 - Assign a phone number to the Common Area Phone user account</span></span>

<span data-ttu-id="9b92d-149">![관리 센터를 사용하여 사용자에게 비즈니스용 Skype 로고를 표시하는 아이콘 비즈니스용 Skype ](../../images/sfb-logo-30x30.png) **지정**</span><span class="sxs-lookup"><span data-stu-id="9b92d-149">![An icon showing the Skype for Business logo](../../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>

1. <span data-ttu-id="9b92d-150">관리 센터에서 > **관리 센터에서**  >  비즈니스용 Skype.</span><span class="sxs-lookup"><span data-stu-id="9b92d-150">In the admin center > **Admin centers** > **Skype for Business**.</span></span>
2. <span data-ttu-id="9b92d-151">관리 **비즈니스용 Skype 음성 전화**  >     >  **번호입니다.**</span><span class="sxs-lookup"><span data-stu-id="9b92d-151">In the **Skype for Business admin center** >  **Voice** > **Phone numbers**.</span></span>
3. <span data-ttu-id="9b92d-152">전화 번호 목록에서 숫자를 선택하고 **할당을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="9b92d-152">Select a number from the list of phone numbers and click **Assign**.</span></span>
4. <span data-ttu-id="9b92d-153">할당 **페이지에서** **음성** 사용자 상자에 휴대폰에 사용되는 사용자의 이름을 입력한 다음 음성 사용자  선택 드롭다운에서 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9b92d-153">On the **Assign** page, in the **Voice user** box enter the name of the user that is used for the phone then select the user in the **Select a voice user** drop down.</span></span>
5. <span data-ttu-id="9b92d-154">이 경우 긴급 주소를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b92d-154">While you're there you will need to add an emergency address.</span></span> <span data-ttu-id="9b92d-155">검색하면 긴급 주소  선택 아래에서 적합한 주소를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9b92d-155">Once you search, look under the **Select emergency address** to pick the right one for you.</span></span>
6. <span data-ttu-id="9b92d-156">**저장을** 클릭하고 사용자는 다음과 같이 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b92d-156">Click **Save** and your user should look like this:</span></span>

    ![사용자 전화 번호 스크린샷](../../images/cap-user-number.png)

   > [!Note]
   > <span data-ttu-id="9b92d-158">라이선스가 적용된 전화 시스템 사용자에게만 표시됩니다. </span><span class="sxs-lookup"><span data-stu-id="9b92d-158">Users will only show up if they have a **Phone System** licence applied.</span></span> <span data-ttu-id="9b92d-159">방금 이 경우 사용자가 목록에 표시하는 데 약간의 시간이 걸리는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b92d-159">If you just did this, then sometimes it takes a bit for the user to show up in the list.</span></span>

<span data-ttu-id="9b92d-160">자세한 내용은 [사용자에 대한 전화 번호 보기를 참조합니다.](/microsoftteams/getting-phone-numbers-for-your-users)</span><span class="sxs-lookup"><span data-stu-id="9b92d-160">For more stuff, see [Getting phone numbers for your users](/microsoftteams/getting-phone-numbers-for-your-users).</span></span>

<span data-ttu-id="9b92d-161">궁금한 경우 다른 통신사 및 "포트"에 있는 휴대폰번호를 찍거나 해당 휴대폰을 Microsoft 365 또는 Office 365.</span><span class="sxs-lookup"><span data-stu-id="9b92d-161">If you're wondering, you can also take your phone number that you have with another carrier and "*port*" or transfer them over to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="9b92d-162">를 [참조하여 전화 번호를](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams)Teams.</span><span class="sxs-lookup"><span data-stu-id="9b92d-162">See, [Transfer phone numbers to Teams](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams).</span></span>

### <a name="step-4---setting-up-your-phone"></a><span data-ttu-id="9b92d-163">4단계 - 휴대폰 설정</span><span class="sxs-lookup"><span data-stu-id="9b92d-163">Step 4 - Setting up your phone</span></span>

<span data-ttu-id="9b92d-164">**휴대폰에서 모드 설정**</span><span class="sxs-lookup"><span data-stu-id="9b92d-164">**Setting the mode on a phone**</span></span>

<span data-ttu-id="9b92d-165">공용 영역 모드가 켜져 있어야 전화 **전화** 또는 휴대폰입니다.</span><span class="sxs-lookup"><span data-stu-id="9b92d-165">The phone or phones you have must have the **Common Area Phone mode** turned on.</span></span> <span data-ttu-id="9b92d-166">해당 작업을 확인하여 해당 작업을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b92d-166">You might want to check on that to make sure they do.</span></span>

<span data-ttu-id="9b92d-167">**Polycom VVX 휴대폰을 설정하는 방법에 대한 예제는 다음과 같습니다.**</span><span class="sxs-lookup"><span data-stu-id="9b92d-167">**Here's an example for how to set up a Polycom VVX phone**</span></span>

- <span data-ttu-id="9b92d-168">다음 전화 다음 단계를 수행하여 Polycom VVX에 공통 영역 설정 모드를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9b92d-168">Enable Common Area Phone mode for the Polycom VVX by following these steps:</span></span>
    1. <span data-ttu-id="9b92d-169">브라우저에서 CAP 모드를 사용하도록 설정할 수 있도록 웹 인터페이스에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="9b92d-169">In your browser, connect to the web interface so that you can enable CAP mode.</span></span>
    2. <span data-ttu-id="9b92d-170">그런 다음  설정으로 **이동하여** 비즈니스용 Skype 설정 옵션에서 공통 영역 **전화.**</span><span class="sxs-lookup"><span data-stu-id="9b92d-170">Then go to **Setting**  and in the **Skype for Business Setting** option, select **Common Area Phone**.</span></span>
    3. <span data-ttu-id="9b92d-171">예를 **클릭하여** 설정을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="9b92d-171">Click **Yes** to save your settings.</span></span>

- <span data-ttu-id="9b92d-172">이제 CAP 모드를 사용하도록 설정하고 휴대폰의 디스플레이를 사용하여 휴대폰을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9b92d-172">Now that CAP mode is enabled, set up the phone using the phone's display.</span></span> <span data-ttu-id="9b92d-173">표시에는 **CaAP가 사용하도록 설정되어 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="9b92d-173">The display should show **CaAP is enabled**.</span></span> <span data-ttu-id="9b92d-174">그런 다음 다음을 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b92d-174">Then do the following:</span></span>

    1. <span data-ttu-id="9b92d-175">를 **설정** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9b92d-175">Click **Settings**.</span></span>
    2. <span data-ttu-id="9b92d-176">고급 **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9b92d-176">Select **Advanced**.</span></span>
    3. <span data-ttu-id="9b92d-177">암호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9b92d-177">Enter the password.</span></span>
    4. <span data-ttu-id="9b92d-178">관리 **설정에서** **공통** 영역 전화 설정.</span><span class="sxs-lookup"><span data-stu-id="9b92d-178">In **Administration settings**, select **Common Area Phone Settings**.</span></span>
    5. <span data-ttu-id="9b92d-179">**CAP 및** CAP 관리 모드를 **사용하도록 설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="9b92d-179">Enable **CAP** and **CAP Admin Mode**.</span></span>
    6. <span data-ttu-id="9b92d-180">구성 **저장 을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="9b92d-180">Click **Save Config**.</span></span>

- <span data-ttu-id="9b92d-181">이제 휴대폰이 준비되어 있으므로 홈 화면에 로그인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b92d-181">Ok, now your phone is ready so you can sign in on the home screen.</span></span>

    1. <span data-ttu-id="9b92d-182">기능 설정   >  **선택하여 로그인**  >  **비즈니스용 Skype.**</span><span class="sxs-lookup"><span data-stu-id="9b92d-182">Sign in by selecting **Settings** > **Features** > **Skype for Business.**</span></span>
    2. <span data-ttu-id="9b92d-183">사용자 **자격 증명을** 선택하고 **CAP(웹 로그인)를** 선택하여 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="9b92d-183">Select **User Credentials**, and select **web sign-in (CAP)** to generate a code.</span></span>
    3. <span data-ttu-id="9b92d-184">[프로비전 포털로 이동하고](https://aka.ms/skypecap)관리자로 **로그인합니다.**</span><span class="sxs-lookup"><span data-stu-id="9b92d-184">Go to the [provisioning portal](https://aka.ms/skypecap), and sign in as **admin**.</span></span>
    4. <span data-ttu-id="9b92d-185">표시 이름(예: Main Reception)을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9b92d-185">Enter the display name (for example, Main Reception).</span></span>

       > [!Note]
       > <span data-ttu-id="9b92d-186">공용 **영역** 휴대폰 검색만 선택된 경우 확인란을 선택 취소하고 다시 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="9b92d-186">If **Search for Common Area Phones only** is checked, clear the checkbox and search again.</span></span>

    5. <span data-ttu-id="9b92d-187">페어링 코드 창에서 휴대폰에 표시된 코드를 입력하고 프로비전 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="9b92d-187">In the pairing code window, enter the code displayed on the phone and click **Provision**.</span></span>

        <span data-ttu-id="9b92d-188">이 마지막 단계에 따라 휴대폰이 자동으로 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b92d-188">Following this last step, the phone should sign in automatically.</span></span>


> [!NOTE]
> <span data-ttu-id="9b92d-189">CAP 프로비전 사이트는 CAP 계정의 암호를 임의 암호로 재설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9b92d-189">The CAP provisioning site states it will reset the CAP account's password to a random password.</span></span> <span data-ttu-id="9b92d-190">CAP가 참조하는 계정은 AAD(Azure Active Directory) 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="9b92d-190">Take note that the account the CAP is referring is the Azure Active Directory (AAD) account.</span></span> <span data-ttu-id="9b92d-191">AAD에서만 계정을 만든 경우 프로세스가 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="9b92d-191">If you created the account in AAD only then the process is straightforward.</span></span> <span data-ttu-id="9b92d-192">AAD에 On-Premises Active Directory를 동기화하고 타사 IDP 또는 ADFS를 사용하는 경우 CAP 프로비전이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="9b92d-192">If you have synced an on premises Active Directory to AAD and you use a third-party IDP or ADFS, CAP provisioning will fail.</span></span> <span data-ttu-id="9b92d-193">이 경우 CAP 프로비전이 작동하려면 Microsoft 365 Office 365/Azure Active Directory 계정(예: onmicrosoft.com 도메인이 있는 **계정)만** 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b92d-193">In this case, you need to use a Microsoft 365 or Office 365/Azure Active Directory account only (for example, an account with **onmicrosoft.com** domain) for CAP provisioning to work.</span></span>


### <a name="related-topics"></a><span data-ttu-id="9b92d-194">관련 주제</span><span class="sxs-lookup"><span data-stu-id="9b92d-194">Related topics</span></span>

- <span data-ttu-id="9b92d-195">온라인 휴대폰 배포에서 사용 가능한 [비즈니스용 Skype 자세히 알아보기](deploying-skype-for-business-online-phones.md)</span><span class="sxs-lookup"><span data-stu-id="9b92d-195">Learn more about available phones at [Deploying Skype for Business Online phones](deploying-skype-for-business-online-phones.md).</span></span>
- [<span data-ttu-id="9b92d-196">비즈니스용 Skype Online 휴대폰 받기</span><span class="sxs-lookup"><span data-stu-id="9b92d-196">Getting phones for Skype for Business Online</span></span>](getting-phones-for-skype-for-business-online.md)
