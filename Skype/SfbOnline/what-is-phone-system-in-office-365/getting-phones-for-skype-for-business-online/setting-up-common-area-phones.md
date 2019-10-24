---
title: 공통 지역 전화 설정
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
f1keywords: None
ms.custom:
- Phone System
description: 올바른 펌웨어를 얻고, 필요한 경우 업데이트 하 고, 라이선스를 할당 하 고, 공통 지역 전화에 대 한 설정을 구성 하는 배포 단계를 알아보세요.
ms.openlocfilehash: 9f84b8ebbdd9bfab6b146d3f748715a5e0602047
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/18/2019
ms.locfileid: "37642506"
---
# <a name="set-up-common-area-phones"></a><span data-ttu-id="2b5a9-103">공통 지역 전화 설정</span><span class="sxs-lookup"><span data-stu-id="2b5a9-103">Set up common area phones</span></span>
<span data-ttu-id="2b5a9-104">일반적으로 일반 지역 전화 (CAP)는 일부 사용자가 사용할 수 있는 대기실 또는 다른 영역 등의 영역에 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-104">A common area phone (CAP) is typically placed in an area like a lobby or another area that is available to a lot of people.</span></span> <span data-ttu-id="2b5a9-105">예를 들어 수신 지역 전화, 문 휴대폰 또는 회의실 전화, Cap는 사용자가 아닌 장치로 설정 되며 네트워크에 자동으로 로그인 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-105">For example, a reception area phone, door phone or meeting room phone, CAPs are set up as devices rather than users and automatically sign into a network.</span></span> <span data-ttu-id="2b5a9-106">아래 단계에서는 전화 요금제를 사용 하 여 회사에 대 한 이러한 유형의 전화를 배포할 수 있도록 전화 시스템 계정을 설정 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-106">In the steps below, we’ll help you set up an account for Phone System with Calling Plans so you can deploy these types of phones for your organization.</span></span>

## <a name="prerequisites-for-common-area-phones"></a><span data-ttu-id="2b5a9-107">공통 지역 전화의 전제 조건</span><span class="sxs-lookup"><span data-stu-id="2b5a9-107">Prerequisites for common area phones</span></span>

<span data-ttu-id="2b5a9-108">가장 먼저 할 일은 다음이 있는지 확인 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-108">The first thing you need to do is to confirm that you have the following:</span></span>

- <span data-ttu-id="2b5a9-109">일반적인 지역 전화 라이선스와 통화 요금제를 구입 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-109">Purchase Common Area Phone license and a Calling Plan.</span></span>
- <span data-ttu-id="2b5a9-110">승인 된 전화를 검색 하 고 구입 합니다 ( [여기](deploying-skype-for-business-online-phones.md)에서 목록 보기).</span><span class="sxs-lookup"><span data-stu-id="2b5a9-110">Search for and buy approved phones (view the list [here](deploying-skype-for-business-online-phones.md)).</span></span>
- <span data-ttu-id="2b5a9-111">휴대폰의 펌웨어를 업데이트 합니다 ( [이 항목의](getting-phones-for-skype-for-business-online.md)지원 되는 펌웨어 참조).</span><span class="sxs-lookup"><span data-stu-id="2b5a9-111">Update the firmware on your phones (See supported firmware [in this topic](getting-phones-for-skype-for-business-online.md)).</span></span>  <span data-ttu-id="2b5a9-112">다음과 같은 방법으로 휴대폰에서 펌웨어를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-112">You can check the firmware on you phone by doing this:</span></span>
  - <span data-ttu-id="2b5a9-113">**Polycom vvx 휴대폰**: **설정** > **상태** > **플랫폼** > **응용 프로그램** > **메인**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-113">**Polycom VVX phones**: Go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span></span>
  - <span data-ttu-id="2b5a9-114">**옛 alink 휴대폰**: 메인 전화 화면에서 **상태로** 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-114">**Yealink phones**: Go to **Status** on the main phone screen.</span></span>
  - <span data-ttu-id="2b5a9-115">**오디오 코드 전화**: 시작 화면에서 **메뉴** > **디바이스 상태** > **펌웨어 버전** 으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-115">**AudioCodes phones**: Go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span></span>
  - <span data-ttu-id="2b5a9-116">**Lpe (Lync Phone Edition) 전화**: 시작 화면에서 **메뉴** > **시스템 정보** 로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-116">**Lync Phone Edition (LPE) phones**: Go to **Menu** > **System Information** from the start screen.</span></span>

    <span data-ttu-id="2b5a9-117">펌웨어 업데이트는 비즈니스용 Skype 서비스에서 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-117">Firmware updates are managed by the Skype for Business Service.</span></span> <span data-ttu-id="2b5a9-118">모든 비즈니스용 Skype 인증 휴대폰의 펌웨어가 비즈니스용 Skype 업데이트 서버에 업로드 되며 기본적으로 모든 전화기에서 장치 업데이트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-118">Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.</span></span>

    <span data-ttu-id="2b5a9-119">휴대폰 및 폴링 간격의 비활성 시간에 따라 전화는 자동으로 최신 인증 된 빌드를 다운로드 하 고 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-119">Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds.</span></span> <span data-ttu-id="2b5a9-120">[Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) cmdlet을 사용 하 고 *enabledeviceupdate* 매개 변수를로 `false`설정 하 여 장치 업데이트 설정을 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-120">You can disable the device update settings by using the  [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) cmdlet and setting the *EnableDeviceUpdate* parameter to `false`.</span></span>

## <a name="setting-up-a-common-area-phone"></a><span data-ttu-id="2b5a9-121">공통 지역 전화 설정</span><span class="sxs-lookup"><span data-stu-id="2b5a9-121">Setting up a Common Area Phone</span></span>
<span data-ttu-id="2b5a9-122">다음 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-122">You will need to follow these steps:</span></span>

### <a name="step-1---buy-the-licenses"></a><span data-ttu-id="2b5a9-123">1 단계-라이선스 구입</span><span class="sxs-lookup"><span data-stu-id="2b5a9-123">Step 1 - Buy the licenses</span></span>
1. <span data-ttu-id="2b5a9-124">관리 센터에서 **청구** > **구매 서비스로**이동 하 고 **다른 요금제**를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-124">In the admin center, go to **Billing** > **Purchase services**, and add **Other plans**.</span></span>

    ![CAP-license](../../images/cap-license.png)
2. <span data-ttu-id="2b5a9-126">**일반 지역 전화** > **구입** 을 클릭 하세요. **체크 아웃** 페이지의 **지금 구입**을 클릭 >.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-126">Click on **Common Area Phone** > **Buy now** > on the **Checkout** page click on **Buy now**.</span></span>
3. <span data-ttu-id="2b5a9-127">**추가 기능 구독** 을 확장 하려면 on을 클릭 한 다음 통화 요금제를 구입 하려면을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-127">Click on to expand **Add-on subscriptions** and then click on to buy a Calling Plan.</span></span> <span data-ttu-id="2b5a9-128">**국내 통화 요금제** 또는 **국내 및 국제 통화 요금제**중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-128">Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.</span></span>

> [!Note]
> <span data-ttu-id="2b5a9-129">전화 시스템 라이선스가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-129">You don't need a Phone System license.</span></span> <span data-ttu-id="2b5a9-130">**일반 지역 전화** 라이선스에 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-130">It's included with the **Common Area Phone** license.</span></span>

<span data-ttu-id="2b5a9-131">라이선스에 대 한 자세한 내용은 [비즈니스용 Skype 및 Microsoft 팀 추가 기능 라이선스](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-131">For more info on licenses, see [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

### <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a><span data-ttu-id="2b5a9-132">2 단계-휴대폰에 대 한 새 사용자 계정 만들기 및 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="2b5a9-132">Step 2 - Create a new user account for the phone and assign the licenses</span></span>
1. <span data-ttu-id="2b5a9-133">관리 센터에서 사용자**활성 사용자** > 를**추가할** **사용자로** > 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-133">In the admin center, go to **Users** > **Active Users** > **Add a user**.</span></span>
2. <span data-ttu-id="2b5a9-134">이름에 "Main"과 같은 **사용자 이름을** 사용 하 고 두 번째 이름에는 "수신"을 붙여 넣으십시오.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-134">Put in a **User name** like “Main" for the first name and "Reception” for the second name.</span></span>
3. <span data-ttu-id="2b5a9-135">"주요 수신"과 같이 자동으로 생성 되지 않는 경우 **표시 이름을** 둡니다.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-135">Put in a **Display name** if it doesn't autogenerate one like "Main Reception".</span></span>
4. <span data-ttu-id="2b5a9-136">"MainReception" 또는 "Mainreception"와 같은 **사용자 이름을** 넣으십시오.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-136">Put in a **User name** like "MainReception" or "Mainlobby".</span></span>
5. <span data-ttu-id="2b5a9-137">일반적인 지역 전화의 경우 암호를 수동으로 설정 하거나 모든 공통 지역 전화에 대해 같은 암호를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-137">For common area phones, you might want to set a password manually or have the same password for all of you common area phones.</span></span> <span data-ttu-id="2b5a9-138">또한 선택을 취소 하는 **경우이 사용자가 처음 로그인 할 때 암호를 변경**하는 것을 고려해 야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-138">Also, you might think about unselecting **Make this user change their password when they first sign in**.</span></span>
6. <span data-ttu-id="2b5a9-139">아직도 있으면이 사용자에 게 라이선스를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-139">If you are still there, assign the licenses to this user.</span></span> <span data-ttu-id="2b5a9-140">동일한 페이지에서 **제품 라이선스**를 클릭 하 여 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-140">On the same page, click to expand **Product licenses**.</span></span> <span data-ttu-id="2b5a9-141">다음을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-141">Turn on the following:</span></span>
   - <span data-ttu-id="2b5a9-142">공통 지역 전화</span><span class="sxs-lookup"><span data-stu-id="2b5a9-142">Common Area Phone</span></span>
   - <span data-ttu-id="2b5a9-143">그런 다음 **국내 통화 요금제** 나 국내 및 **국제 통화 요금제**중 하나를 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-143">Then you need to pick either a **Domestic Calling Plan** or a Domestic and **International Calling Plan**.</span></span>

     <span data-ttu-id="2b5a9-144">라이선스 할당에는 다음과 같은 모양이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-144">Assigning the licenses will look like:</span></span>

     ![TurnOnCapLicense](../../images/cap-license-turn-on.png)

     > [!Note]
     > <span data-ttu-id="2b5a9-146">이에 대 한 자세한 내용은 비즈니스용 Skype 요금제 2가 **일반 지역 전화** 라이선스에 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-146">Just so you know, Skype for Business Plan 2 is included with the **Common Area Phone** license.</span></span>

<span data-ttu-id="2b5a9-147">자세한 내용은 [사용자 추가](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-147">For more details, see [Add a user](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span>

### <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a><span data-ttu-id="2b5a9-148">3 단계-일반 지역 전화 사용자 계정에 전화 번호 지정</span><span class="sxs-lookup"><span data-stu-id="2b5a9-148">Step 3 - Assign a phone number to the Common Area Phone user account</span></span>

<span data-ttu-id="2b5a9-149">![비즈니스용 skype 로고](../../images/sfb-logo-30x30.png) 를 표시 하는 아이콘은 비즈니스용 **skype 관리 센터** 를 사용 하 여 사용자에 게 전화 번호를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-149">![An icon showing the Skype for Business logo](../../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>

1. <span data-ttu-id="2b5a9-150">관리 센터 > **관리** > 센터에서**비즈니스용 Skype를 사용할**경우</span><span class="sxs-lookup"><span data-stu-id="2b5a9-150">In the admin center > **Admin centers** > **Skype for Business**.</span></span>
2. <span data-ttu-id="2b5a9-151">**비즈니스용 Skype 관리 센터** >  의**음성** > **전화 번호**.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-151">In the **Skype for Business admin center** >  **Voice** > **Phone numbers**.</span></span>
3. <span data-ttu-id="2b5a9-152">전화 번호 목록에서 번호를 선택 하 고 **할당**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-152">Select a number from the list of phone numbers and click **Assign**.</span></span>
4. <span data-ttu-id="2b5a9-153">**지정** 페이지의 **음성 사용자** 상자에 휴대폰에 사용 되는 사용자의 이름을 입력 한 다음 **음성 사용자 선택** 드롭다운에서 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-153">On the **Assign** page, in the **Voice user** box enter the name of the user that is used for the phone then select the user in the **Select a voice user** drop down.</span></span>
5. <span data-ttu-id="2b5a9-154">여기서 긴급 주소를 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-154">While you're there you will need to add an emergency address.</span></span> <span data-ttu-id="2b5a9-155">검색을 마치면 **긴급 주소 선택** 아래에서 원하는 항목을 바로 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-155">Once you search, look under the **Select emergency address** to pick the right one for you.</span></span>
6. <span data-ttu-id="2b5a9-156">**저장** 을 클릭 하면 사용자에 게 다음과 같은 모양이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-156">Click **Save** and your user should look like this:</span></span>

    ![cap-user-number](../../images/cap-user-number.png)

   > [!Note]
   > <span data-ttu-id="2b5a9-158">사용자에 게 **전화 시스템** 라이선스가 적용 된 경우에만 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-158">Users will only show up if they have a **Phone System** licence applied.</span></span> <span data-ttu-id="2b5a9-159">방금이 작업을 수행한 경우 사용자가 목록에 표시 되는 데 약간의 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-159">If you just did this, then sometimes it takes a bit for the user to show up in the list.</span></span>

<span data-ttu-id="2b5a9-160">자세한 내용은 [사용자의 전화 번호 가져오기를](/microsoftteams/getting-phone-numbers-for-your-users)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-160">For more stuff, see [Getting phone numbers for your users](/microsoftteams/getting-phone-numbers-for-your-users).</span></span>

<span data-ttu-id="2b5a9-161">다른 통신 회사와 "*포트*"를 사용 하 여 전화 번호를 받아 Office 365으로 전송할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-161">If you're wondering, you can also take your phone number that you have with another carrier and "*port*" or transfer them over to Office 365.</span></span> <span data-ttu-id="2b5a9-162">[Office 365에 전화 번호를 전송](/microsoftteams/transfer-phone-numbers-to-office-365)하세요.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-162">See, [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).</span></span>

### <a name="step-4---setting-up-your-phone"></a><span data-ttu-id="2b5a9-163">4 단계-휴대폰 설정</span><span class="sxs-lookup"><span data-stu-id="2b5a9-163">Step 4 - Setting up your phone</span></span>

<span data-ttu-id="2b5a9-164">**휴대폰에서 모드 설정**</span><span class="sxs-lookup"><span data-stu-id="2b5a9-164">**Setting the mode on a phone**</span></span>

<span data-ttu-id="2b5a9-165">휴대폰 이나 전화기에는 **공통 영역 전화 모드가** 켜져 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-165">The phone or phones you have must have the **Common Area Phone mode** turned on.</span></span> <span data-ttu-id="2b5a9-166">이 작업을 수행할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-166">You might want to check on that to make sure they do.</span></span>

<span data-ttu-id="2b5a9-167">**다음은 Polycom VVX 휴대폰을 설정 하는 방법의 예입니다.**</span><span class="sxs-lookup"><span data-stu-id="2b5a9-167">**Here's an example for how to set up a Polycom VVX phone**</span></span>

- <span data-ttu-id="2b5a9-168">다음 단계에 따라 Polycom VVX에 대해 공통 영역 전화 모드를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-168">Enable Common Area Phone mode for the Polycom VVX by following these steps:</span></span>
    1. <span data-ttu-id="2b5a9-169">브라우저에서 CAP 모드를 사용할 수 있도록 웹 인터페이스에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-169">In your browser, connect to the web interface so that you can enable CAP mode.</span></span>
    2. <span data-ttu-id="2b5a9-170">그런 다음, **설정** 으로 이동 하 여 **비즈니스용 Skype 설정** 옵션에서 **일반 지역 전화**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-170">Then go to **Setting**  and in the **Skype for Business Setting** option, select **Common Area Phone**.</span></span>
    3. <span data-ttu-id="2b5a9-171">**예** 를 클릭 하 여 설정을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-171">Click **Yes** to save your settings.</span></span>

- <span data-ttu-id="2b5a9-172">이제 CAP 모드가 활성화 되 면 휴대폰 디스플레이를 사용 하 여 전화를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-172">Now that CAP mode is enabled, set up the phone using the phone's display.</span></span> <span data-ttu-id="2b5a9-173">표시에는 **Caap가 사용 하도록 설정 되어**표시 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-173">The display should show **CaAP is enabled**.</span></span> <span data-ttu-id="2b5a9-174">그런 후 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-174">Then do the following:</span></span>

    1. <span data-ttu-id="2b5a9-175">**설정을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-175">Click **Settings**.</span></span>
    2. <span data-ttu-id="2b5a9-176">**고급**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-176">Select **Advanced**.</span></span>
    3. <span data-ttu-id="2b5a9-177">비밀 번호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-177">Enter the password.</span></span>
    4. <span data-ttu-id="2b5a9-178">**관리 설정**에서 **일반 영역 전화 설정을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-178">In **Administration settings**, select **Common Area Phone Settings**.</span></span>
    5. <span data-ttu-id="2b5a9-179">**Cap** 및 **cap 관리 모드**를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-179">Enable **CAP** and **CAP Admin Mode**.</span></span>
    6. <span data-ttu-id="2b5a9-180">**구성 저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-180">Click **Save Config**.</span></span>

- <span data-ttu-id="2b5a9-181">이제 휴대폰을 사용할 준비가 되어 홈 화면에서 로그인 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-181">Ok, now your phone is ready so you can sign in on the home screen.</span></span>

    1. <span data-ttu-id="2b5a9-182">**비즈니스용 Skype의** **설정** > **기능** > 을 선택 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-182">Sign in by selecting **Settings** > **Features** > **Skype for Business.**</span></span>
    2. <span data-ttu-id="2b5a9-183">**사용자 자격 증명**을 선택 하 고 **웹 로그인 (CAP)** 을 선택 하 여 코드를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-183">Select **User Credentials**, and select **web sign-in (CAP)** to generate a code.</span></span>
    3. <span data-ttu-id="2b5a9-184">[프로 비전 포털로](https://aka.ms/skypecap)이동 하 고 **관리자로**로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-184">Go to the [provisioning portal](https://aka.ms/skypecap), and sign in as **admin**.</span></span>
    4. <span data-ttu-id="2b5a9-185">표시 이름 (예: 메인 수신)을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-185">Enter the display name (for example, Main Reception).</span></span>

       > [!Note]
       > <span data-ttu-id="2b5a9-186">**공용 지역 전화만 검색** 을 선택 하는 경우 확인란을 선택 취소 하 고 다시 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-186">If **Search for Common Area Phones only** is checked, clear the checkbox and search again.</span></span>

    5. <span data-ttu-id="2b5a9-187">페어링 코드 창에서 휴대폰에 표시 되는 코드를 입력 하 고 **프로 비전**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-187">In the pairing code window, enter the code displayed on the phone and click **Provision**.</span></span>

        <span data-ttu-id="2b5a9-188">이 마지막 단계를 따라 휴대폰에서 자동으로 로그인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-188">Following this last step, the phone should sign in automatically.</span></span>


> [!NOTE]
> <span data-ttu-id="2b5a9-189">CAP 프로비저닝 사이트 상태에서는 CAP 계정의 암호가 임의 암호로 재설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-189">The CAP provisioning site states it will reset the CAP account's password to a random password.</span></span> <span data-ttu-id="2b5a9-190">CAP가 참조 하는 계정이 Azure Active Directory (AAD) 계정이 된다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-190">Take note that the account the CAP is referring is the Azure Active Directory (AAD) account.</span></span> <span data-ttu-id="2b5a9-191">AAD 에서만 계정을 만든 경우 프로세스는 간단 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-191">If you created the account in AAD only then the process is straightforward.</span></span> <span data-ttu-id="2b5a9-192">온-프레미스 Active Directory를 AAD에 동기화 하 고 타사 IDP 또는 ADFS를 사용 하는 경우 CAP 프로비저닝이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-192">If you have synced an on premises Active Directory to AAD and you use a third-party IDP or ADFS, CAP provisioning will fail.</span></span> <span data-ttu-id="2b5a9-193">이 경우 CAP 프로비저닝 작업을 수행 하려면 Office 365/Azure Active Directory 계정 (예: **onmicrosoft.com** 도메인을 사용 하는 계정)만 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-193">In this case, you need to use an Office 365/Azure Active Directory account only (for example, an account with **onmicrosoft.com** domain) for CAP provisioning to work.</span></span>


### <a name="related-topics"></a><span data-ttu-id="2b5a9-194">관련 항목</span><span class="sxs-lookup"><span data-stu-id="2b5a9-194">Related topics</span></span>

- <span data-ttu-id="2b5a9-195">[비즈니스용 Skype Online 휴대폰을 구축할](deploying-skype-for-business-online-phones.md)때 사용 가능한 전화에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-195">Learn more about available phones at [Deploying Skype for Business Online phones](deploying-skype-for-business-online-phones.md).</span></span>
- [<span data-ttu-id="2b5a9-196">비즈니스용 Skype Online에서 전화 받기</span><span class="sxs-lookup"><span data-stu-id="2b5a9-196">Getting phones for Skype for Business Online</span></span>](getting-phones-for-skype-for-business-online.md)


