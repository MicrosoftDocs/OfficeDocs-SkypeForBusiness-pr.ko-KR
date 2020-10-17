---
title: 'Lync Server 2013: Lync 클라이언트에서 2 단계 인증 사용'
description: 'Lync Server 2013: Lync 클라이언트에서 2 단계 인증을 사용 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using two-factor authentication with Lync client
ms:assetid: d4136e61-c3ab-4b26-85c8-c1b2c24f5ee3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn338071(v=OCS.15)
ms:contentKeyID: 55115593
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbfde1d04d4e641c8fbe4817ffce214df891b565
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547284"
---
# <a name="using-two-factor-authentication-with-lync-client-and-lync-server-2013"></a><span data-ttu-id="86c63-103">Lync 클라이언트 및 Lync Server 2013에서 2 단계 인증 사용</span><span class="sxs-lookup"><span data-stu-id="86c63-103">Using two-factor authentication with Lync client and Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="86c63-104">_**마지막으로 수정 된 항목:** 2013-07-11_</span><span class="sxs-lookup"><span data-stu-id="86c63-104">_**Topic Last Modified:** 2013-07-11_</span></span>

<span data-ttu-id="86c63-105">이 항목에서는 Lync 2013 클라이언트에서 2 단계 인증을 활용 하는 방법에 대해 설명 했습니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-105">This topic described how to take advantage of two-factor authentication with Lync 2013 client.</span></span>

<div>

## <a name="sign-in-to-lync-2013-for-the-first-time"></a><span data-ttu-id="86c63-106">처음으로 Lync 2013에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-106">Sign in to Lync 2013 for the first time</span></span>

<span data-ttu-id="86c63-107">Lync 로그인 정보는 대개 Lync 2013이 설치 될 때 자동으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-107">Your Lync sign-in information is usually configured automatically when Lync 2013 is installed.</span></span> <span data-ttu-id="86c63-108">하지만 Lync를 처음 사용 하는 경우에는 클라이언트를 수동으로 시작 해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-108">But the first time you use Lync, you might have to manually start the client.</span></span>

<span data-ttu-id="86c63-109">**처음으로 Lync에 로그인 하려면**</span><span class="sxs-lookup"><span data-stu-id="86c63-109">**To sign in to Lync for the first time**</span></span>

1.  <span data-ttu-id="86c63-110">조직의 네트워크에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-110">Log on to your organization’s network.</span></span>

2.  <span data-ttu-id="86c63-111">**Start** \> **모든 프로그램** 시작 \> **Microsoft Lync \> Lync 2013**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-111">Select **Start** \> **All Programs** \> **Microsoft Lync \> Lync 2013**.</span></span>
    
    <span data-ttu-id="86c63-112">Lync 로그인 화면이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-112">You should see the Lync sign-in screen.</span></span>
    
      - <span data-ttu-id="86c63-113">로그인 주소 상자에 이미 입력 되어 있는 경우 표시 된 주소가 올바른지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-113">If the sign-in address box is already filled in, confirm that the address shown is correct.</span></span>
    
      - <span data-ttu-id="86c63-114">올바르지 않거나 상자가 비어 있으면 Lync 로그인 주소 (일반적으로 사용자의 전자 메일 주소와 같음)를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-114">If it’s not correct, or if the box is empty, enter your Lync sign-in address (this is usually the same as your email address).</span></span>
    
      - <span data-ttu-id="86c63-115">빈 암호 상자가 표시 되 면 암호를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-115">If an empty password box is displayed, add your password.</span></span>

3.  <span data-ttu-id="86c63-116">**로그인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-116">Select **Sign-in**.</span></span>

</div>

<div>

## <a name="sign-out-of-lync"></a><span data-ttu-id="86c63-117">Lync에서 로그 아웃</span><span class="sxs-lookup"><span data-stu-id="86c63-117">Sign out of Lync</span></span>

<span data-ttu-id="86c63-118">Lync 사용을 마친 후에는 파일 메뉴에서 디스플레이를 닫거나, 세션을 로그 아웃 하거나, 프로그램을 끝낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-118">When you’re finished using Lync, you can close the display, sign out of your session, or exit from the program, all from the File menu.</span></span> <span data-ttu-id="86c63-119">다음 표에서는 옵션의 차이점에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-119">The following table explains the differences in the options.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="86c63-120">옵션</span><span class="sxs-lookup"><span data-stu-id="86c63-120">Option</span></span></th>
<th><span data-ttu-id="86c63-121">속성 기능</span><span class="sxs-lookup"><span data-stu-id="86c63-121">What it does</span></span></th>
<th><span data-ttu-id="86c63-122">수행 방법</span><span class="sxs-lookup"><span data-stu-id="86c63-122">How to perform it</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="86c63-123">닫지</span><span class="sxs-lookup"><span data-stu-id="86c63-123">Close</span></span></p></td>
<td><p><span data-ttu-id="86c63-124">Lync 화면을 닫지만 사용자 ID로 식별 된 Lync 세션을 계속 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-124">Closes your Lync display but lets the Lync session identified with your user ID continue to run.</span></span> <span data-ttu-id="86c63-125">따라서 계속 해 서 알림을 받고 다른 사람들과 상호 작용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-125">This is so you can continue to get notifications and interact with others.</span></span></p>
<p><span data-ttu-id="86c63-126">작업 표시줄의 Lync 아이콘 또는 화면 아래쪽에 있는 알림 영역을 클릭 하 여 언제 든 지 다시 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-126">You can get the display back at any time by clicking the Lync icon on the taskbar or the notification area at the bottom of your screen.</span></span></p></td>
<td><p><span data-ttu-id="86c63-127">Lync 주 창에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-127">On the Lync main window, do one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="86c63-128"><strong>옵션</strong> 단추를 선택한 다음 <strong>파일</strong> &gt; <strong>닫기를</strong>선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-128">Select the <strong>Options</strong> button, then select <strong>File</strong> &gt; <strong>Close</strong>.</span></span></p></li>
<li><p><span data-ttu-id="86c63-129">창의 오른쪽 위 모서리에 있는 <strong>닫기</strong> 단추 (X)를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-129">Click the <strong>Close</strong> button (X) in the upper-right corner of the window.</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86c63-130">로그 아웃</span><span class="sxs-lookup"><span data-stu-id="86c63-130">Sign out</span></span></p></td>
<td><p><span data-ttu-id="86c63-131">사용자 ID와 연결 된 Lync 세션을 종료 하지만 Lync는 백그라운드에서 계속 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-131">Ends the Lync session associated with your user ID, but Lync continues to run in the background.</span></span> <span data-ttu-id="86c63-132">로그 아웃 하면 로그인 창이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-132">When you sign out, the sign-in window will appear.</span></span></p>
<div>

> [!TIP]  
> <span data-ttu-id="86c63-133">컴퓨터에서 로그온 ID 및 암호 기록을 제거 하려면 로그 아웃할 때 <STRONG>내 로그인 정보 삭제</STRONG> 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-133">Select <STRONG>Delete my sign-in information</STRONG> when you sign out to remove the record of your logon ID and password from the computer.</span></span> <span data-ttu-id="86c63-134">이렇게 하면 사용자가 로그인 문제를 보다 쉽게 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-134">Doing this might make it easier for support people to troubleshoot sign-in issues.</span></span> <span data-ttu-id="86c63-135">또한 인증 되지 않은 사용자가 자격 증명을 사용 하 여 로그온 하는 것을 어렵게 하 여 로그인 정보를 보다 안전 하 게 유지 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-135">It can also help ensure your sign-in information is more secure by making it difficult for unauthorized users to log on with your credentials.</span></span>


</div></td>
<td><p><span data-ttu-id="86c63-136">Lync 주 창에서 <strong>옵션</strong> 단추를 선택한 다음 <strong>파일</strong> &gt; <strong>로그 아웃</strong>을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-136">On the Lync main window, select the <strong>Options</strong> button, then select <strong>File</strong> &gt; <strong>Sign Out</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86c63-137">마침</span><span class="sxs-lookup"><span data-stu-id="86c63-137">Exit</span></span></p></td>
<td><p><span data-ttu-id="86c63-138">Lync 세션을 종료 하 고 컴퓨터에서 Lync를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-138">Ends your Lync session and shuts down Lync on your computer.</span></span> <span data-ttu-id="86c63-139">종료 후 Lync를 다시 시작 하려면 <strong>Start</strong> &gt; <strong>All Programs</strong> &gt; <strong>Microsoft Lync</strong> &gt; <strong>Lync 2013</strong>모든 프로그램 시작을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-139">After exiting, if you want to restart Lync, select <strong>Start</strong> &gt; <strong>All Programs</strong> &gt; <strong>Microsoft Lync</strong> &gt; <strong>Lync 2013</strong>.</span></span></p></td>
<td><p><span data-ttu-id="86c63-140">Lync 주 창에서 <strong>옵션</strong> 단추를 선택 하 고 <strong>파일</strong> &gt; <strong>종료</strong>를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-140">On the Lync main window, select the <strong>Options</strong> button, then select <strong>File</strong> &gt; <strong>Exit</strong>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="sign-in-to-lync-with-a-smart-card"></a><span data-ttu-id="86c63-141">스마트 카드를 사용 하 여 Lync에 로그인</span><span class="sxs-lookup"><span data-stu-id="86c63-141">Sign in to Lync with a Smart Card</span></span>

<span data-ttu-id="86c63-142">일부 조직에서는 이제 2 단계 인증 이라는 다단계 로그인 프로세스를 사용 하 여 Lync 2013 사용자의 보안을 강화 합니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-142">Some organizations now use a multi-step sign-in process, called two-factor authentication, to increase security for their Lync 2013 users.</span></span> <span data-ttu-id="86c63-143">이 옵션을 사용할 것으로 예상 되 면 Lync에 로그인 하기 위한 "스마트 카드"가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-143">If you’re expected to use this option, you’ll need a “smart card” to sign in to Lync.</span></span> <span data-ttu-id="86c63-144">스마트 카드는 실제 및 가상의 두 가지 형태로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-144">Smart cards come in two varieties, physical and virtual:</span></span>

  - <span data-ttu-id="86c63-145">**실제**     신용 카드의 크기 정보</span><span class="sxs-lookup"><span data-stu-id="86c63-145">**Physical**   About the size of a credit card.</span></span> <span data-ttu-id="86c63-146">로그인 할 때 스마트 카드 판독기에 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-146">You insert it into a smart card reader when you log in.</span></span>

  - <span data-ttu-id="86c63-147">**가상**     실제 개체는 아니지만 컴퓨터의 특수 칩에 기록 되는 전자 식별자 이며, 기본적으로 컴퓨터에 스마트 카드를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-147">**Virtual**   Not a physical object, but an electronic identifier that gets written to a special chip on your computer, which in essence builds the smart card into your computer.</span></span> <span data-ttu-id="86c63-148">TPM (신뢰할 수 있는 플랫폼 모듈) 칩이 포함 된 Windows 8 컴퓨터 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-148">Available only for use with Windows 8 computers that contain the TPM (Trusted Platform Module) chip.</span></span>

<div>

## <a name="enroll-your-smart-card"></a><span data-ttu-id="86c63-149">스마트 카드 등록</span><span class="sxs-lookup"><span data-stu-id="86c63-149">Enroll your smart card</span></span>

<span data-ttu-id="86c63-150">스마트 카드를 사용 하 여 로그인 하려면 카드를 "등록" 해야 하며, 즉 사용자 자격 증명을 해당 카드와 함께 식별할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-150">Before you can sign in with a smart card, the card must be “enrolled”—that is, your user credentials have to be identified with the card.</span></span> <span data-ttu-id="86c63-151">이는 명함이 실제 또는 가상 인지 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-151">This is the case whether the card is physical or virtual.</span></span> <span data-ttu-id="86c63-152">이 프로세스는 Lync Server 관리자가 이미 수행 했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-152">This process may already been carried out by your Lync Server administrator.</span></span> <span data-ttu-id="86c63-153">완료 되었는지 여부를 확인 하지 않은 경우 해당 내용을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="86c63-153">Check with them if you’re not sure whether that has been done.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="86c63-154">각 가상 스마트 카드는 설치 된 장치에만 연결 되므로 사용 하는 각 Windows 8 컴퓨터에 대해 별도의 카드를 등록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-154">Since each virtual smart card is associated only with the device it’s installed on, a separate card will need to be enrolled for each Windows 8 computer you use.</span></span>



</div>

<span data-ttu-id="86c63-155">**스마트 카드를 수동으로 등록 하려면**</span><span class="sxs-lookup"><span data-stu-id="86c63-155">**To manually enroll your smart card**</span></span>

1.  <span data-ttu-id="86c63-156">Lync를 실행할 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-156">Log on to the computer you’ll be running Lync on.</span></span>

2.  <span data-ttu-id="86c63-157">Internet Explorer를 사용 하 여 조직의 인증 기관 웹 등록 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-157">Using Internet Explorer, browse to your organization’s Certificate Authority Web Enrollment page.</span></span>
    
    <span data-ttu-id="86c63-158">이 리소스가 없으면 Lync Server 관리자에 게 해당 리소스의 웹 주소를 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="86c63-158">Ask your Lync Server administrator for the web address of this resource if you don’t already have it.</span></span> <span data-ttu-id="86c63-159">URL은 https://MyCA.\ [이란 companyname \] . .com/certsrv와 같이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-159">The URL will look something like this: https://MyCA.\[yourcompanyname\].com/certsrv.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="86c63-160">Internet Explorer 10을 사용 중인 경우 호환 모드에서이 웹 사이트를 확인 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-160">If you’re using Internet Explorer 10, you may need to view this website in Compatibility Mode.</span></span>

    
    </div>

3.  <span data-ttu-id="86c63-161">인증 페이지에 로그온 하 라는 메시지가 표시 되 면 사용자 컴퓨터의 관리자가 아닌 도메인 계정을 사용 하 여 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-161">When you’re prompted to log on to the certification page, log on using your domain account (rather than as administrator of your computer).</span></span>

4.  <span data-ttu-id="86c63-162">웹 사이트 시작 페이지에서 **인증서 요청**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-162">On the website Welcome Page, select **Request a certificate**.</span></span>

5.  <span data-ttu-id="86c63-163">**고급 요청**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-163">Select **Advanced Request**.</span></span>

6.  <span data-ttu-id="86c63-164">**이 CA에 요청 만들기 및 제출을**선택 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-164">Select **Create and submit a request to this CA**, then click **Next**.</span></span>

7.  <span data-ttu-id="86c63-165">이제 스마트 카드 등록 스테이션 이라는 페이지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-165">Now you’ll see a page called Smart Card Enrollment Station.</span></span> <span data-ttu-id="86c63-166">ActiveX 컨트롤 설치 요청을 승인 하 고 다음과 같이 고급 인증서 요청 양식을 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-166">Approve the request to install the ActiveX control, and then complete the Advanced Certificate Request form as follows:</span></span>
    
    1.  <span data-ttu-id="86c63-167">**인증서 템플릿** 드롭다운 목록에서 **스마트 카드 사용자** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-167">Select **Smartcard user** from the **Certificate Template** dropdown list.</span></span>
    
    2.  <span data-ttu-id="86c63-168">**새 키 집합 만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-168">Select **Create new key set**.</span></span>
    
    3.  <span data-ttu-id="86c63-169">스마트 카드 레이블에서 제조업체 정보를 확인 하 고 **CSP** 드롭다운 목록에서 해당 제조업체를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-169">Find the manufacturer information on the label of your smart card and select that manufacturer from the **CSP** dropdown list.</span></span>
    
    4.  <span data-ttu-id="86c63-170">요청 형식이 아직 선택 되지 않은 경우 **CSP** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-170">Select **CSP** as the Request Format, if it’s not already selected.</span></span>
    
    5.  <span data-ttu-id="86c63-171">해시 알고리즘 드롭다운 목록에서 **sha1** 을 선택 합니다 (아직 선택 되어 있지 않은 경우).</span><span class="sxs-lookup"><span data-stu-id="86c63-171">Select **sha1** from the Hash Algorithm dropdown list, if it’s not already selected.</span></span>
    
    6.  <span data-ttu-id="86c63-172">사용자에 게 인식할 수 있는 이름을 인증서에 제공 하 고 **제출을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-172">Give your certificate a name you’ll recognize, and click **Submit**.</span></span>

8.  <span data-ttu-id="86c63-173">이제 등록 스테이션에 연결 된 카드 판독기에 빈 스마트 카드를 삽입 하 고 **등록**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-173">Now insert your blank smart card into the card reader attached to the enrollment station and click **Enroll**.</span></span>

9.  <span data-ttu-id="86c63-174">메시지가 표시 되 면 PIN (개인 id 번호)을 입력 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-174">When prompted, enter your personal identification number (PIN), and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="86c63-175">기술 지원 담당자가 스마트 카드를 등록 하는 데 사용할 특수 PIN을 제공 하지 않은 경우 기본 스마트 카드 PIN 값 (12345678)을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-175">If your technical support person has not given you a special PIN to use to enroll your smart card, use the default smart card PIN value, which is 12345678.</span></span>

    
    </div>

10. <span data-ttu-id="86c63-176">사용자가 스마트 카드를 처음 사용할 때 PIN을 강제로 변경 하도록 하려면이 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-176">Select the option to force the user (you) to change the PIN the first time the smart card is used.</span></span>

11. <span data-ttu-id="86c63-177">이제 등록 스테이션에 연결 된 카드 판독기에 빈 스마트 카드를 삽입 하 고 **등록**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-177">Now insert your blank smart card into the card reader attached to the enrollment station and click **Enroll**.</span></span>

12. <span data-ttu-id="86c63-178">메시지가 표시 되 면 PIN (개인 id 번호)을 입력 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-178">When prompted, enter your personal identification number (PIN), and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="86c63-179">기술 지원 담당자가 스마트 카드를 등록 하는 데 사용할 특수 PIN을 제공 하지 않은 경우 기본 스마트 카드 PIN 값 (12345678)을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-179">If your technical support person has not given you a special PIN to use to enroll your smart card, use the default smart card PIN value, which is 12345678.</span></span>

    
    </div>

13. <span data-ttu-id="86c63-180">사용자가 스마트 카드를 처음 사용할 때 PIN을 강제로 변경 하도록 하려면이 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-180">Select the option to force the user (you) to change the PIN the first time the smart card is used.</span></span>

14. <span data-ttu-id="86c63-181">**확인** 을 클릭 하 여 표시 된 인증서에 정보가 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-181">Click **OK** to confirm that the certificate displayed has your information on it.</span></span>

15. <span data-ttu-id="86c63-182">인증서가 발급 되었음을 알리는 메시지가 표시 되 면 **이 인증서 설치** 를 클릭 하 여 등록 프로세스를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-182">Once you see the notice that the certificate has been issued, click **Install this certificate** to complete the enrollment process.</span></span>

</div>

<div>

## <a name="sign-in-to-lync-with-your-smart-card-credentials"></a><span data-ttu-id="86c63-183">스마트 카드 자격 증명을 사용 하 여 Lync에 로그인</span><span class="sxs-lookup"><span data-stu-id="86c63-183">Sign in to Lync with your smart card credentials</span></span>

<span data-ttu-id="86c63-184">스마트 카드를 처음 사용 하기 전에 Lync 로그인 페이지에서 **내 로그인 정보 삭제** 를 클릭 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-184">Before you use your smart card for the first time, it’s recommended that you click **Delete my sign-in info** on the Lync sign-in page.</span></span> <span data-ttu-id="86c63-185">이렇게 하면 컴퓨터에 저장 된 모든 로그인 자격 증명이 지워지고 오류가 발생할 수 있는 원인이 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-185">Doing this clears any sign-in credentials stored on your computer, and eliminates a possible source of error.</span></span>

<span data-ttu-id="86c63-186">**스마트 카드 자격 증명을 사용 하 여 Lync에 로그인 하려면**</span><span class="sxs-lookup"><span data-stu-id="86c63-186">**To sign in to Lync with your smart card credentials**</span></span>

1.  <span data-ttu-id="86c63-187">Lync 클라이언트를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-187">Start the Lync client.</span></span>

2.  <span data-ttu-id="86c63-188">로그인 화면에서 **로그인 주소** 상자에 로그인 사용자 계정 이름을 입력 하 고 **로그인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-188">On the Sign in screen, type your sign in user account name in the **Sign-in address** box, and then click **Sign In**.</span></span>

3.  <span data-ttu-id="86c63-189">가상 스마트 카드를 사용 하는 경우에는이 단계를 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-189">If you are using a virtual smart card, skip this step.</span></span>
    
    <span data-ttu-id="86c63-190">실제 스마트 카드를 사용 하는 경우 스마트 카드 판독기에 스마트 카드를 삽입 하 고, 카드를 넣으라는 메시지가 표시 되 면 **확인** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-190">If you are using a physical smart card, insert the smart card into your smart card reader and prompted to do so, and then click **OK** when the card is detected.</span></span>

4.  <span data-ttu-id="86c63-191">PIN 번호를 스마트 카드에 입력 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-191">Type in the PIN number you for your smart card and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="86c63-192">지원 담당자가 스마트 카드 PIN 번호를 할당 하지 않은 경우 기본값 (12345678)을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="86c63-192">If you were not assigned a smart card PIN number by your support person, use the default value, which is 12345678.</span></span>

    
    </div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

