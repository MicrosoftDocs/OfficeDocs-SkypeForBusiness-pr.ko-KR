---
title: 'Lync Server 2013: iPhone 및 iPad 용 Lync 설치'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing Lync for iPhone and iPad
ms:assetid: 88d1c149-5842-4ecf-a15e-fcda0330325b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690987(v=OCS.15)
ms:contentKeyID: 51541496
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 91d8f26e0ae1b0777823380ca4888cad4c13ee90
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197021"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-lync-for-iphone-and-ipad-in-lync-server-2013"></a><span data-ttu-id="b9f9b-102">Lync Server 2013에서 iPhone 및 iPad 용 Lync 설치</span><span class="sxs-lookup"><span data-stu-id="b9f9b-102">Installing Lync for iPhone and iPad in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b9f9b-103">_**마지막으로 수정 된 항목:** 2014-03-10_</span><span class="sxs-lookup"><span data-stu-id="b9f9b-103">_**Topic Last Modified:** 2014-03-10_</span></span>

<span data-ttu-id="b9f9b-104">IPhone 용 lync 2013 for iPad 및 Lync 2013은 Apple App 스토어에서 사용할 수 있는 사용자 설치 가능 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="b9f9b-104">Lync 2013 for iPhone and Lync 2013 for iPad are user-installable applications that are available in the Apple App Store.</span></span>

<div>

## <a name="installing-lync-for-iphone-and-lync-for-ipad"></a><span data-ttu-id="b9f9b-105">Lync for iPhone 및 Lync for iPad 설치</span><span class="sxs-lookup"><span data-stu-id="b9f9b-105">Installing Lync for iPhone and Lync for iPad</span></span>

<span data-ttu-id="b9f9b-106">사용자에 게 장치에서 앱 스토어로 지시 하 여 iPhone 및 Lync 2013 용 Lync 2013을 설치 하도록 지시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9f9b-106">You can instruct your users to install Lync 2013 for iPhone and Lync 2013 for iPad by directing them to the App Store from their devices.</span></span> <span data-ttu-id="b9f9b-107">각 장치에서 액세스할 수 있는 App Store는 온라인에서도 사용 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="b9f9b-107">The App Store for each device is also available online.</span></span>

  - <span data-ttu-id="b9f9b-108">Lync for iPhone은 앱 스토어 ( \< h<span></span>ttp://www.apple.com/iphone/from-the-app-store/>)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9f9b-108">Lync for iPhone is available in the App Store at \< h<span></span>ttp://www.apple.com/iphone/from-the-app-store/></span></span>

  - <span data-ttu-id="b9f9b-109">Lync for iPad는 \< Ht<span></span>tp://www.apple.com/ipad/from-the-app-store/앱 스토어에서 사용할 수 있습니다 ></span><span class="sxs-lookup"><span data-stu-id="b9f9b-109">Lync for iPad is available in the App Store at \< ht<span></span>tp://www.apple.com/ipad/from-the-app-store/></span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b9f9b-110">iPhone Lync 2013 앱을 설치 하지 않고 모임 초대 로부터 Lync 모임에 참가 하려는 사용자는 참가 시작 관리자 페이지로 리디렉션됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9f9b-110">iPhone users who have not installed the Lync 2013 app and who try to join a Lync meeting from a meeting invitation will be redirected to a Join Launcher page.</span></span> <span data-ttu-id="b9f9b-111">이 페이지에는 Lync 2013 앱을 설치 하기 위한 링크가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9f9b-111">This page contains a link for installing the Lync 2013 app.</span></span> <span data-ttu-id="b9f9b-112">그러나 사용자를 앱 저장소로 전달 하는 대신이 링크를 사용 하면 빈 Safari 브라우저 페이지가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="b9f9b-112">However, instead of directing the user to the App Store, this link opens a blank Safari browser page.</span></span> <span data-ttu-id="b9f9b-113">사용자는 다음 두 가지 방법 중 하나를 수행 하 여이 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9f9b-113">The user can do one of two things to work around this issue:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="b9f9b-114"><STRONG>홈</STRONG> 단추를 사용 하 여 safari 페이지를 백그라운드로 보낸 다음 safari를 다시 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b9f9b-114">Use the <STRONG>Home</STRONG> button to send the Safari page to the background, and then reopen Safari.</span></span> <span data-ttu-id="b9f9b-115">"앱 스토어에서이 페이지 열기" 알림이 표시 되 면 앱 스토어에서 <STRONG>Open</STRONG> 을 탭 하 여 Lync 2013 다운로드로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9f9b-115">When the notification “Open this page in App Store” appears, tap <STRONG>Open</STRONG> to be directed to Lync 2013 download in the App Store.</span></span></P>
> <LI>
> <P><span data-ttu-id="b9f9b-116">앱 스토어를 수동으로 열고 "Lync 2013"을 검색 한 후 앱을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9f9b-116">Manually open the App Store, search for "Lync 2013," and download the app.</span></span></P></LI></UL>



</div>

</div>

<div>

## <a name="verifying-mobile-client-installation"></a><span data-ttu-id="b9f9b-117">모바일 클라이언트 설치 확인</span><span class="sxs-lookup"><span data-stu-id="b9f9b-117">Verifying Mobile Client Installation</span></span>

<span data-ttu-id="b9f9b-118">정상적으로 클라이언트를 구성하여 로그인한 후에는 다음 테스트를 통해 설치한 Lync가 모바일 장치에서 올바르게 작동하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b9f9b-118">After you configure the client and sign in successfully, use the following tests to verify that your Lync installation is working correctly on your mobile device.</span></span>

<span data-ttu-id="b9f9b-119">**회사 디렉터리에서 대화 상대 검색**</span><span class="sxs-lookup"><span data-stu-id="b9f9b-119">**Search for a contact in the corporate directory**</span></span>

1.  <span data-ttu-id="b9f9b-120">대화 상대 목록에서 위쪽의 검색 창 안을 누르고 GAL(전체 주소 목록)에만 있는 대화 상대의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b9f9b-120">In the Contacts list, tap inside the search bar at the top, and begin typing the name of a contact that exists only in the global address list (GAL).</span></span>

2.  <span data-ttu-id="b9f9b-121">대화 상대 이름이 검색 결과에 나타나는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b9f9b-121">Verify that the contact name appears in the search results.</span></span>

<span data-ttu-id="b9f9b-122">**인스턴트 메시징 및 현재 상태 테스트**</span><span class="sxs-lookup"><span data-stu-id="b9f9b-122">**Test instant messaging and presence**</span></span>

1.  <span data-ttu-id="b9f9b-123">대화 상대 목록에서 대화 상대를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="b9f9b-123">In the Contacts list, tap a contact.</span></span>

2.  <span data-ttu-id="b9f9b-124">대화 상대 카드에서 **IM** 아이콘을 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="b9f9b-124">In the contact card, tap the **IM** icon.</span></span>

3.  <span data-ttu-id="b9f9b-125">Im (인스턴트 메시징) 창이 나타나고 IM을 입력 하 고 보낼 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9f9b-125">Verify that an instant messaging (IM) window appears and that you can type and send an IM.</span></span>

<span data-ttu-id="b9f9b-126">**전화 접속 회의 테스트**</span><span class="sxs-lookup"><span data-stu-id="b9f9b-126">**Test dial-out conferencing**</span></span>

1.  <span data-ttu-id="b9f9b-127">Outlook에서 Lync 모임을 예약합니다.</span><span class="sxs-lookup"><span data-stu-id="b9f9b-127">In Outlook, schedule a Lync meeting.</span></span>

2.  <span data-ttu-id="b9f9b-128">모바일 장치에서 모임 초대를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b9f9b-128">On the mobile device, open the meeting invitation.</span></span>

3.  <span data-ttu-id="b9f9b-129">참가할 모임의 링크를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b9f9b-129">Click the link in the meeting to join.</span></span>

4.  <span data-ttu-id="b9f9b-130">회의 서비스에서 걸려 오는 전화를 받아 모임 오디오에 연결되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b9f9b-130">Answer the call from the conference service and verify that you are connected to the meeting audio.</span></span>

<span data-ttu-id="b9f9b-131">**푸시 알림 테스트**</span><span class="sxs-lookup"><span data-stu-id="b9f9b-131">**Test push notifications**</span></span>

1.  <span data-ttu-id="b9f9b-132">사용자 A의 모바일 장치에서 사용자 A의 계정으로 Lync에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="b9f9b-132">On user A’s mobile device, sign in to Lync with user A’s account.</span></span>

2.  <span data-ttu-id="b9f9b-133">모바일 장치에서 다른 응용 프로그램을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b9f9b-133">Open another application on the mobile device.</span></span>

3.  <span data-ttu-id="b9f9b-134">다른 클라이언트에서 사용자 B의 계정으로 Lync에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="b9f9b-134">On a different client, sign in to Lync with user B’s account.</span></span>

4.  <span data-ttu-id="b9f9b-135">사용자 B로부터 사용자 A에게 IM을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="b9f9b-135">Send an IM from user B to user A.</span></span>

5.  <span data-ttu-id="b9f9b-136">IM 알림이 사용자 A의 모바일 장치에 나타나는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b9f9b-136">Verify that the IM notification appears on user A’s mobile device.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

