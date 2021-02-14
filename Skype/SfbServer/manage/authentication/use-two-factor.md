---
title: 비즈니스용 Skype 클라이언트 및 비즈니스용 Skype 서버에서 2단계 인증 사용
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d4136e61-c3ab-4b26-85c8-c1b2c24f5ee3
description: '요약: 비즈니스용 Skype 서버 및 비즈니스용 Skype에서 2단계 인증을 사용하세요.'
ms.openlocfilehash: 72ec3570d632eecefd28ebfd0aa50eb70c54ff99
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806545"
---
# <a name="use-two-factor-authentication-with-skype-for-business-client-and-skype-for-business-server"></a><span data-ttu-id="0a4ea-103">비즈니스용 Skype 클라이언트 및 비즈니스용 Skype 서버에서 2단계 인증 사용</span><span class="sxs-lookup"><span data-stu-id="0a4ea-103">Use two-factor authentication with Skype for Business client and Skype for Business Server</span></span>
 
<span data-ttu-id="0a4ea-104">**요약:** 비즈니스용 Skype 서버 및 비즈니스용 Skype에서 2단계 인증을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="0a4ea-104">**Summary:** Use two-factor authentication with Skype for Business Server and Skype for Business.</span></span>
  
## <a name="sign-in-to-skype-for-business-for-the-first-time"></a><span data-ttu-id="0a4ea-105">처음으로 비즈니스용 Skype에 로그인</span><span class="sxs-lookup"><span data-stu-id="0a4ea-105">Sign in to Skype for Business for the first time</span></span>

<span data-ttu-id="0a4ea-106">사용자의 로그인 정보는 일반적으로 비즈니스용 Skype가 설치될 때 자동으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a4ea-106">Your sign-in information is usually configured automatically when Skype for Business is installed.</span></span> <span data-ttu-id="0a4ea-107">하지만 처음으로 비즈니스용 Skype를 사용할 때 클라이언트를 수동으로 시작해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a4ea-107">But the first time you use Skype for Business, you might have to manually start the client.</span></span>
  
### <a name="to-sign-in-for-the-first-time"></a><span data-ttu-id="0a4ea-108">처음 로그인하는 경우</span><span class="sxs-lookup"><span data-stu-id="0a4ea-108">To sign in for the first time</span></span>

1. <span data-ttu-id="0a4ea-109">조직의 네트워크에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="0a4ea-109">Log on to your organization's network.</span></span>
    
2. <span data-ttu-id="0a4ea-110">모든 **프로그램 시작**  >  **비즈니스용**  >  **Skype를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0a4ea-110">Select **Start** > **All Programs** > **Skype for Business**.</span></span>
    
    <span data-ttu-id="0a4ea-111">로그인 화면이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a4ea-111">You should see the sign-in screen.</span></span>
    
    - <span data-ttu-id="0a4ea-112">로그인 주소 상자가 이미 입력되어 있는 경우 표시된 주소가 올바른지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0a4ea-112">If the sign-in address box is already filled in, confirm that the address shown is correct.</span></span>
    
    - <span data-ttu-id="0a4ea-113">맞지 않는 경우 또는 상자가 비어 있는 경우 로그인 주소를 입력합니다(일반적으로 전자 메일 주소와 동일함).</span><span class="sxs-lookup"><span data-stu-id="0a4ea-113">If it's not correct, or if the box is empty, enter your sign-in address (this is usually the same as your email address).</span></span>
    
    - <span data-ttu-id="0a4ea-114">빈 암호 상자가 표시되면 암호를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0a4ea-114">If an empty password box is displayed, add your password.</span></span>
    
3. <span data-ttu-id="0a4ea-115">로그인을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0a4ea-115">Select **Sign-in**.</span></span>
    
## <a name="sign-out-of-skype-for-business"></a><span data-ttu-id="0a4ea-116">비즈니스용 Skype에서 사인아웃</span><span class="sxs-lookup"><span data-stu-id="0a4ea-116">Sign out of Skype for Business</span></span>

<span data-ttu-id="0a4ea-117">비즈니스용 Skype 사용을 마치면 파일 메뉴에서 디스플레이를 닫거나 세션에서 로그인하거나 프로그램에서 종료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a4ea-117">When you're finished using Skype for Business, you can close the display, sign out of your session, or exit from the program, all from the File menu.</span></span> <span data-ttu-id="0a4ea-118">다음 표에서는 옵션의 차이점을 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a4ea-118">The following table explains the differences in the options.</span></span>
  
|<span data-ttu-id="0a4ea-119">**옵션**</span><span class="sxs-lookup"><span data-stu-id="0a4ea-119">**Option**</span></span>|<span data-ttu-id="0a4ea-120">**속성 기능**</span><span class="sxs-lookup"><span data-stu-id="0a4ea-120">**What it does**</span></span>|<span data-ttu-id="0a4ea-121">**이 작업을 수행하는 방법**</span><span class="sxs-lookup"><span data-stu-id="0a4ea-121">**How to perform it**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0a4ea-122">닫기</span><span class="sxs-lookup"><span data-stu-id="0a4ea-122">Close</span></span>  <br/> |<span data-ttu-id="0a4ea-123">디스플레이를 닫지만 사용자 ID로 식별된 비즈니스용 Skype 세션이 계속 실행될 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a4ea-123">Closes your display but lets the Skype for Business session identified with your user ID continue to run.</span></span> <span data-ttu-id="0a4ea-124">이렇게 하여 계속해서 알림을 받고 다른 사용자와 상호 작용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a4ea-124">This is so you can continue to get notifications and interact with others.</span></span> <br/> <br/> <span data-ttu-id="0a4ea-125">작업 표시줄 또는 화면 아래쪽의 알림 영역에 있는 비즈니스용 Skype 아이콘을 클릭하여 디스플레이를 다시 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a4ea-125">You can get the display back at any time by clicking the Skype for Business icon on the taskbar or the notification area at the bottom of your screen.</span></span>  <br/> | <span data-ttu-id="0a4ea-126">비즈니스용 Skype 주 창에서 다음 중 하나를 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a4ea-126">On the Skype for Business main window, do one of the following:</span></span> <br/> <span data-ttu-id="0a4ea-127">1. 옵션 **단추를** 선택한 다음 파일 **닫기를**  >  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0a4ea-127">1. Select the **Options** button, then select **File** > **Close**.</span></span>  <br/> <span data-ttu-id="0a4ea-128">2. **창의** 오른쪽 위 모서리에 있는 닫기 단추(X)를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0a4ea-128">2. Click the **Close** button (X) in the upper-right corner of the window.</span></span> <br/> |
|<span data-ttu-id="0a4ea-129">Sign out</span><span class="sxs-lookup"><span data-stu-id="0a4ea-129">Sign out</span></span>  <br/> |<span data-ttu-id="0a4ea-130">사용자 ID와 연결된 세션을 종료하지만 비즈니스용 Skype는 백그라운드에서 계속 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a4ea-130">Ends the session associated with your user ID, but Skype for Business continues to run in the background.</span></span> <span data-ttu-id="0a4ea-131">로그인하면 로그인 창이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="0a4ea-131">When you sign out, the sign-in window will appear.</span></span>  <br/> <span data-ttu-id="0a4ea-132">**팁:** 로그온 **ID** 및 암호의 레코드를 컴퓨터에서 제거하려면 로그아웃할 때 내 로그인 정보 삭제를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0a4ea-132">**Tip:** Select **Delete my sign-in information** when you sign out to remove the record of your logon ID and password from the computer.</span></span> <span data-ttu-id="0a4ea-133">이렇게 하면 지원 사람들이 로그인 문제를 쉽게 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a4ea-133">Doing this might make it easier for support people to troubleshoot sign-in issues.</span></span> <span data-ttu-id="0a4ea-134">또한 권한이 없는 사용자가 자격 증명으로 로그온하기 어렵게 하여 로그인 정보를 보다 안전하게 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a4ea-134">It can also help ensure your sign-in information is more secure by making it difficult for unauthorized users to log on with your credentials.</span></span> <br/> |<span data-ttu-id="0a4ea-135">비즈니스용 Skype 주 창에서  옵션 단추를 선택한 다음 파일   >  **로그인을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0a4ea-135">On the Skype for Business main window, select the **Options** button, then select **File** > **Sign Out**.</span></span>  <br/> |
|<span data-ttu-id="0a4ea-136">Exit</span><span class="sxs-lookup"><span data-stu-id="0a4ea-136">Exit</span></span>  <br/> |<span data-ttu-id="0a4ea-137">비즈니스용 Skype 세션을 종료하고 컴퓨터에서 비즈니스용 Skype를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="0a4ea-137">Ends your Skype for Business session and shuts down Skype for Business on your computer.</span></span> <span data-ttu-id="0a4ea-138">종료한 후 다시 시작하려면 비즈니스용   >   Skype에서 모든 > 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0a4ea-138">After exiting, if you want to restart, select **Start** > **All Programs** > Skype for Business.</span></span> <br/> |<span data-ttu-id="0a4ea-139">비즈니스용 Skype 주 창에서  옵션 단추를 선택한 다음 파일 **종료를**  >  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0a4ea-139">On the Skype for Business main window, select the **Options** button, then select **File** > **Exit**.</span></span>  <br/> |
   
## <a name="sign-in-to-skype-for-business-with-a-smart-card"></a><span data-ttu-id="0a4ea-140">스마트 카드로 비즈니스용 Skype에 로그인</span><span class="sxs-lookup"><span data-stu-id="0a4ea-140">Sign in to Skype for Business with a Smart Card</span></span>

<span data-ttu-id="0a4ea-141">일부 조직에서는 이제 2단계 인증이라는 다단계 로그인 프로세스를 사용하여 사용자의 보안을 강화합니다.</span><span class="sxs-lookup"><span data-stu-id="0a4ea-141">Some organizations now use a multi-step sign-in process, called two-factor authentication, to increase security for their users.</span></span> <span data-ttu-id="0a4ea-142">이 옵션을 사용할 것으로 예상되는 경우 비즈니스용 Skype에 로그인하는 "스마트 카드"가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0a4ea-142">If you're expected to use this option, you'll need a "smart card" to sign in to Skype for Business.</span></span> <span data-ttu-id="0a4ea-143">스마트 카드는 물리적 또는 가상 카드일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a4ea-143">Smart cards can be either physical or virtual:</span></span>
  
- <span data-ttu-id="0a4ea-144">**물리적** 신용 카드의 크기</span><span class="sxs-lookup"><span data-stu-id="0a4ea-144">**Physical** About the size of a credit card.</span></span> <span data-ttu-id="0a4ea-145">로그인할 때 스마트 카드 판독기에 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="0a4ea-145">You insert it into a smart card reader when you log in.</span></span>
    
- <span data-ttu-id="0a4ea-146">**가상** 물리적 개체가 아니라 컴퓨터의 특수 칩에 기록되는 전자 식별자입니다. 이 식별자는 기본적으로 스마트 카드를 컴퓨터에 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="0a4ea-146">**Virtual** Not a physical object, but an electronic identifier that gets written to a special chip on your computer, which in essence builds the smart card into your computer.</span></span> <span data-ttu-id="0a4ea-147">TPM(신뢰할 수 있는 플랫폼 모듈) 칩이 포함된 Windows 8 컴퓨터에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a4ea-147">Available only for use with Windows 8 computers that contain the TPM (Trusted Platform Module) chip.</span></span>
    
### <a name="enroll-your-smart-card"></a><span data-ttu-id="0a4ea-148">스마트 카드 등록</span><span class="sxs-lookup"><span data-stu-id="0a4ea-148">Enroll your smart card</span></span>

<span data-ttu-id="0a4ea-149">스마트 카드로 로그인하려면 먼저 카드를 "등록"해야 합니다. 즉, 사용자 자격 증명을 카드로 식별해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a4ea-149">Before you can sign in with a smart card, the card must be "enrolled"—that is, your user credentials have to be identified with the card.</span></span> <span data-ttu-id="0a4ea-150">카드가 실제 카드인지 가상 카드인지에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="0a4ea-150">This is the case whether the card is physical or virtual.</span></span> <span data-ttu-id="0a4ea-151">이 프로세스는 비즈니스용 Skype 서버 관리자가 이미 수행한 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a4ea-151">This process may already been carried out by your Skype for Business Server administrator.</span></span> <span data-ttu-id="0a4ea-152">완료 여부가 확실하지 않은 경우 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="0a4ea-152">Check with them if you're not sure whether that has been done.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0a4ea-153">각 가상 스마트 카드는 설치된 디바이스에만 연결하기 때문에 사용하는 각 Windows 8 컴퓨터에 대해 별도의 카드를 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a4ea-153">Since each virtual smart card is associated only with the device it's installed on, a separate card will need to be enrolled for each Windows 8 computer you use.</span></span> 
  
### <a name="to-manually-enroll-your-smart-card"></a><span data-ttu-id="0a4ea-154">스마트 카드를 수동으로 등록하려면</span><span class="sxs-lookup"><span data-stu-id="0a4ea-154">To manually enroll your smart card</span></span>

1. <span data-ttu-id="0a4ea-155">비즈니스용 Skype를 실행 중인 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="0a4ea-155">Log on to the computer you'll be running Skype for Business on.</span></span>
    
2. <span data-ttu-id="0a4ea-156">이 Internet Explorer 사용하여 조직의 인증 기관 웹 등록 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="0a4ea-156">Using Internet Explorer, browse to your organization's Certificate Authority Web Enrollment page.</span></span> 
    
    <span data-ttu-id="0a4ea-157">비즈니스용 Skype 서버 관리자에게 이 리소스의 웹 주소가 없는 경우 요청하세요.</span><span class="sxs-lookup"><span data-stu-id="0a4ea-157">Ask your Skype for Business Server administrator for the web address of this resource if you don't already have it.</span></span> <span data-ttu-id="0a4ea-158">URL은 다음과 https://MyCA 같습니다. .[ yourcompanyname].com/certsrv.</span><span class="sxs-lookup"><span data-stu-id="0a4ea-158">The URL will look something like this: https://MyCA.[yourcompanyname].com/certsrv.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0a4ea-159">Internet Explorer 10을 사용하는 경우 호환성 모드에서 이 웹 사이트를 보아야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a4ea-159">If you're using Internet Explorer 10, you may need to view this website in Compatibility Mode.</span></span> 
  
3. <span data-ttu-id="0a4ea-160">인증 페이지에 로그온하라는 메시지가 표시될 때 컴퓨터의 관리자 대신 도메인 계정을 사용하여 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="0a4ea-160">When you're prompted to log on to the certification page, log on using your domain account (rather than as administrator of your computer).</span></span>
    
4. <span data-ttu-id="0a4ea-161">웹 사이트 시작 페이지에서 인증서 **요청을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0a4ea-161">On the website Welcome Page, select **Request a certificate**.</span></span>
    
5. <span data-ttu-id="0a4ea-162">고급 **요청을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0a4ea-162">Select **Advanced Request**.</span></span>
    
6. <span data-ttu-id="0a4ea-163">이 **CA에 요청** 만들기 및 제출을 선택하고 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0a4ea-163">Select **Create and submit a request to this CA**, then click **Next**.</span></span>
    
7. <span data-ttu-id="0a4ea-164">이제 스마트 카드 등록 스테이션이라는 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a4ea-164">Now you'll see a page called Smart Card Enrollment Station.</span></span> <span data-ttu-id="0a4ea-165">ActiveX 설치 요청을 승인하고 다음과 같이 고급 인증서 요청 양식을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="0a4ea-165">Approve the request to install the ActiveX control, and then complete the Advanced Certificate Request form as follows:</span></span>
    
    <span data-ttu-id="0a4ea-166">a.</span><span class="sxs-lookup"><span data-stu-id="0a4ea-166">a.</span></span> <span data-ttu-id="0a4ea-167">인증서 **템플릿 드롭다운** 목록에서 스마트 카드 **사용자를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0a4ea-167">Select **Smartcard user** from the **Certificate Template** dropdown list.</span></span>
    
    <span data-ttu-id="0a4ea-168">b.</span><span class="sxs-lookup"><span data-stu-id="0a4ea-168">b.</span></span> <span data-ttu-id="0a4ea-169">새 **키 집합 만들기를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0a4ea-169">Select **Create new key set**.</span></span>
    
    <span data-ttu-id="0a4ea-170">c.</span><span class="sxs-lookup"><span data-stu-id="0a4ea-170">c.</span></span> <span data-ttu-id="0a4ea-171">스마트 카드 레이블에 대한 제조업체 정보를 찾아 **CSP** 드롭다운 목록에서 해당 제조업체를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0a4ea-171">Find the manufacturer information on the label of your smart card and select that manufacturer from the **CSP** dropdown list.</span></span>
    
    <span data-ttu-id="0a4ea-172">d.</span><span class="sxs-lookup"><span data-stu-id="0a4ea-172">d.</span></span> <span data-ttu-id="0a4ea-173">아직 선택하지 않은 경우 요청 형식으로 **CSP를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0a4ea-173">Select **CSP** as the Request Format, if it's not already selected.</span></span>
    
    <span data-ttu-id="0a4ea-174">e.</span><span class="sxs-lookup"><span data-stu-id="0a4ea-174">e.</span></span> <span data-ttu-id="0a4ea-175">아직 선택되지 않은 경우 해시 알고리즘 드롭다운 목록에서 **sha1을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0a4ea-175">Select **sha1** from the Hash Algorithm dropdown list, if it's not already selected.</span></span>
    
    <span data-ttu-id="0a4ea-176">f.</span><span class="sxs-lookup"><span data-stu-id="0a4ea-176">f.</span></span> <span data-ttu-id="0a4ea-177">인증서에 인식할 수 있는 이름을 지정하고 제출을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0a4ea-177">Give your certificate a name you'll recognize, and click **Submit**.</span></span>
    
8. <span data-ttu-id="0a4ea-178">이제 등록 스테이션에 연결된 카드 판독기에 빈 스마트 카드를 삽입하고 등록을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0a4ea-178">Now insert your blank smart card into the card reader attached to the enrollment station and click **Enroll**.</span></span>
    
9. <span data-ttu-id="0a4ea-179">메시지가 표시될 때 PIN(개인 식별 번호)을 입력한 다음 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0a4ea-179">When prompted, enter your personal identification number (PIN), and then click **OK**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0a4ea-180">기술 지원 팀에서 스마트 카드를 등록하는 데 사용할 특수 PIN을 지정하지 않은 경우 기본 스마트 카드 PIN 값(12345678)을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a4ea-180">If your technical support person has not given you a special PIN to use to enroll your smart card, use the default smart card PIN value, which is 12345678.</span></span> 
  
10. <span data-ttu-id="0a4ea-181">스마트 카드를 처음 사용할 때 사용자(사용자)가 PIN을 강제로 변경하도록 하는 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0a4ea-181">Select the option to force the user (you) to change the PIN the first time the smart card is used.</span></span>
    
11. <span data-ttu-id="0a4ea-182">이제 등록 스테이션에 연결된 카드 판독기에 빈 스마트 카드를 삽입하고 등록을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0a4ea-182">Now insert your blank smart card into the card reader attached to the enrollment station and click **Enroll**.</span></span>
    
12. <span data-ttu-id="0a4ea-183">메시지가 표시될 때 PIN(개인 식별 번호)을 입력한 다음 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0a4ea-183">When prompted, enter your personal identification number (PIN), and then click **OK**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0a4ea-184">기술 지원 팀에서 스마트 카드를 등록하는 데 사용할 특수 PIN을 지정하지 않은 경우 기본 스마트 카드 PIN 값(12345678)을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a4ea-184">If your technical support person has not given you a special PIN to use to enroll your smart card, use the default smart card PIN value, which is 12345678.</span></span> 
  
13. <span data-ttu-id="0a4ea-185">스마트 카드를 처음 사용할 때 사용자(사용자)가 PIN을 강제로 변경하도록 하는 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0a4ea-185">Select the option to force the user (you) to change the PIN the first time the smart card is used.</span></span>
    
14. <span data-ttu-id="0a4ea-186">**확인을** 클릭하여 표시된 인증서에 대한 정보가 표시되는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a4ea-186">Click **OK** to confirm that the certificate displayed has your information on it.</span></span>
    
15. <span data-ttu-id="0a4ea-187">인증서가 발급된 알림이 표시되고 나면  이 인증서 설치를 클릭하여 등록 프로세스를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="0a4ea-187">Once you see the notice that the certificate has been issued, click **Install this certificate** to complete the enrollment process.</span></span>
    
### <a name="sign-in-to-skype-for-business-with-your-smart-card-credentials"></a><span data-ttu-id="0a4ea-188">스마트 카드 자격 증명을 사용하여 비즈니스용 Skype에 로그인</span><span class="sxs-lookup"><span data-stu-id="0a4ea-188">Sign in to Skype for Business with your smart card credentials</span></span>

<span data-ttu-id="0a4ea-189">스마트 카드를 처음으로 사용하기 전에 비즈니스용 Skype 로그인 페이지에서  내 로그인 정보 삭제를 클릭하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0a4ea-189">Before you use your smart card for the first time, it's recommended that you click **Delete my sign-in info** on the Skype for Business sign-in page.</span></span> <span data-ttu-id="0a4ea-190">이렇게 하면 컴퓨터에 저장된 모든 로그인 자격 증명이 지워지며 가능한 오류 원본이 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a4ea-190">Doing this clears any sign-in credentials stored on your computer, and eliminates a possible source of error.</span></span>
  
### <a name="to-sign-in-to-skype-for-business-with-your-smart-card-credentials"></a><span data-ttu-id="0a4ea-191">스마트 카드 자격 증명을 사용하여 비즈니스용 Skype에 로그인</span><span class="sxs-lookup"><span data-stu-id="0a4ea-191">To sign in to Skype for Business with your smart card credentials</span></span>

1. <span data-ttu-id="0a4ea-192">비즈니스용 Skype 클라이언트를 시작하세요.</span><span class="sxs-lookup"><span data-stu-id="0a4ea-192">Start the Skype for Business client.</span></span>
    
2. <span data-ttu-id="0a4ea-193">로그인 화면에서 로그인 주소 상자에 로그인 사용자  계정 이름을 입력한 다음 **로그인을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0a4ea-193">On the Sign in screen, type your sign in user account name in the **Sign-in address** box, and then click **Sign In**.</span></span>
    
3. <span data-ttu-id="0a4ea-194">가상 스마트 카드를 사용하는 경우 이 단계를 건너뜁니 다.</span><span class="sxs-lookup"><span data-stu-id="0a4ea-194">If you are using a virtual smart card, skip this step.</span></span>
    
    <span data-ttu-id="0a4ea-195">실제 스마트 카드를 사용하는 경우 스마트 카드 판독기에 스마트 카드를 삽입하고 이를 확인하라는 메시지가 표시되면 카드가 감지되면 **확인을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0a4ea-195">If you are using a physical smart card, insert the smart card into your smart card reader and prompted to do so, and then click **OK** when the card is detected.</span></span>
    
4. <span data-ttu-id="0a4ea-196">스마트 카드에 사용할 PIN 번호를 입력하고 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0a4ea-196">Type in the PIN number you for your smart card and then click **OK**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0a4ea-197">지원 담당자가 스마트 카드 PIN 번호를 할당하지 않은 경우 기본값인 12345678을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a4ea-197">If you were not assigned a smart card PIN number by your support person, use the default value, which is 12345678.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="0a4ea-198">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0a4ea-198">See also</span></span>

[<span data-ttu-id="0a4ea-199">비즈니스용 Skype 서버에서 2단계 인증 관리</span><span class="sxs-lookup"><span data-stu-id="0a4ea-199">Manage two-factor authentication in Skype for Business Server</span></span>](two-factor-authentication.md)
  
[<span data-ttu-id="0a4ea-200">비즈니스용 Skype 서버에서 2단계 인증 구성</span><span class="sxs-lookup"><span data-stu-id="0a4ea-200">Configure two-factor authentication in Skype for Business Server</span></span>](configure-two-factor.md)
