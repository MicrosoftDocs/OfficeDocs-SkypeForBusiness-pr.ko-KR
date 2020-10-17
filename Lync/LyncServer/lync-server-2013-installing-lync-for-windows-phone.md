---
title: 'Lync Server 2013: Lync for Windows Phone 설치'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing Lync for Windows Phone
ms:assetid: bf502546-ff69-489f-a92e-a78b58803d53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690996(v=OCS.15)
ms:contentKeyID: 51541513
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ac77a8402a62929bcb043ebd165a41605b17351
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514185"
---
# <a name="installing-lync-for-windows-phone-in-lync-server-2013"></a><span data-ttu-id="a8e5d-102">Lync Server 2013에서 Windows Phone 용 Lync 설치</span><span class="sxs-lookup"><span data-stu-id="a8e5d-102">Installing Lync for Windows Phone in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a8e5d-103">_**마지막으로 수정 된 항목:** 2014-02-03_</span><span class="sxs-lookup"><span data-stu-id="a8e5d-103">_**Topic Last Modified:** 2014-02-03_</span></span>

<span data-ttu-id="a8e5d-104">Windows Phone 용 Lync 2013는 Windows Phone 마켓플레이스에 제공 되는 사용자가 설치할 수 있는 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="a8e5d-104">Lync 2013 for Windows Phone is a user-installable application that is available in the Windows Phone Marketplace.</span></span>

<div>

## <a name="installing-lync-for-windows-mobile"></a><span data-ttu-id="a8e5d-105">Lync for Windows Mobile 설치</span><span class="sxs-lookup"><span data-stu-id="a8e5d-105">Installing Lync for Windows Mobile</span></span>

<span data-ttu-id="a8e5d-106">사용자에 게 장치에서 windows Phone 용 Lync 2013을 설치 하도록 지시할 수 있습니다 <https://go.microsoft.com/fwlink/p/?linkid=231901> .</span><span class="sxs-lookup"><span data-stu-id="a8e5d-106">You can instruct your users to install Lync 2013 for Windows Phone on their devices by directing them to the Windows Phone Marketplace at <https://go.microsoft.com/fwlink/p/?linkid=231901>.</span></span>

</div>

<div>

## <a name="if-you-use-a-dns-srv-record-to-publish-exchange-web-services"></a><span data-ttu-id="a8e5d-107">DNS SRV 레코드를 사용 하 여 Exchange 웹 서비스를 게시 하는 경우</span><span class="sxs-lookup"><span data-stu-id="a8e5d-107">If You Use a DNS SRV Record to Publish Exchange Web Services</span></span>

<span data-ttu-id="a8e5d-108">Lync 클라이언트에 대해 Exchange 통합을 사용 하도록 설정 하기 위해 일부 조직에서는 DNS SRV 레코드를 사용 하 여 Exchange 웹 서비스 URL을 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8e5d-108">To enable Exchange integration for Lync clients, some organizations publish the Exchange Web Services URL by using a DNS SRV record.</span></span> <span data-ttu-id="a8e5d-109">Microsoft 다운로드 센터에서 제공 하는 "Exchange 통합 이해 및 문제 해결" 문서에서 [https://go.microsoft.com/fwlink/?LinkID=391095](https://go.microsoft.com/fwlink/?linkid=391095) 이 작업이 필요할 수 있는 시나리오에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8e5d-109">The document "Understanding and Troubleshooting Exchange Integration," available in the Microsoft Download Center at [https://go.microsoft.com/fwlink/?LinkID=391095](https://go.microsoft.com/fwlink/?linkid=391095), describes scenarios in which this might be necessary.</span></span> <span data-ttu-id="a8e5d-110">그러나 Windows Phone 플랫폼은 SRV 조회를 지원 하지 않으므로이 시나리오에서는 Windows Phone 사용자에 대 한 Exchange 통합이 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a8e5d-110">However, Exchange integration for Windows Phone users will not work in this scenario, because the Windows Phone platform does not support SRV lookups.</span></span> <span data-ttu-id="a8e5d-111">전화를 통해 서버를 자동으로 검색 하도록 허용 하는 대신 Windows Phone 사용자에 게 Exchange 웹 서비스 URL을 지정 하도록 지시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8e5d-111">You will need to instruct Windows Phone users to specify the Exchange Web Services URL instead of allowing the phone to automatically detect the server.</span></span>

<span data-ttu-id="a8e5d-112">사용자가 다음과 같이 Windows phone에서 Lync 설정을 구성 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8e5d-112">Instruct your users to configure the Lync settings on their Windows Phones as follows:</span></span>

1.  <span data-ttu-id="a8e5d-113">Windows Phone의 Lync 설정에서 **Exchange** 화면을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8e5d-113">In Windows Phone, in the Lync settings, select the **Exchange** screen.</span></span>

2.  <span data-ttu-id="a8e5d-114">**자동 검색 서버** 를 **해제**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8e5d-114">Move **Auto-Detect Server** to **Off**.</span></span>

3.  <span data-ttu-id="a8e5d-115">빈 필드를 탭 하 고 Exchange 웹 서비스의 FQDN (정규화 된 도메인 이름) 또는 URL을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8e5d-115">Tap the empty field and enter the fully qualified domain name (FQDN) or URL for Exchange Web Services.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a8e5d-116">Exchange 웹 서비스 서버의 FQDN (정규화 된 도메인 이름) 또는 전체 URL을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8e5d-116">You can specify either the fully qualified domain name (FQDN) or the full URL of your Exchange Web Services server.</span></span> <span data-ttu-id="a8e5d-117">FQDN을 지정 하면 프로토콜 (https://)과 Exchange 웹 서비스 경로 (/ews/exchange.asmx)가 자동으로 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8e5d-117">If you specify the FQDN, the protocol (https://) and the Exchange Web Services path (/ews/exchange.asmx) are added automatically.</span></span> <span data-ttu-id="a8e5d-118">Exchange 웹 서비스 경로가 다르면 전체 URL을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8e5d-118">If your Exchange Web Services path is different, you can specify the full URL.</span></span>

    
    </div>

4.  <span data-ttu-id="a8e5d-119">화면을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="a8e5d-119">Close the screen.</span></span>

</div>

<div>

## <a name="verifying-mobile-client-installation"></a><span data-ttu-id="a8e5d-120">모바일 클라이언트 설치 확인</span><span class="sxs-lookup"><span data-stu-id="a8e5d-120">Verifying Mobile Client Installation</span></span>

<span data-ttu-id="a8e5d-121">클라이언트를 구성 하 고 성공적으로 로그인 한 후에는 다음 테스트를 사용 하 여 Lync 2013 설치가 모바일 장치에서 올바르게 작동 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8e5d-121">After you configure the client and sign in successfully, use the following tests to verify that your installation of Lync 2013 is working correctly on your mobile device.</span></span>

<span data-ttu-id="a8e5d-122">**회사 디렉터리에서 대화 상대 검색**</span><span class="sxs-lookup"><span data-stu-id="a8e5d-122">**Search for a contact in the corporate directory**</span></span>

1.  <span data-ttu-id="a8e5d-123">대화 상대 목록에서 아래쪽의 **검색**을 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="a8e5d-123">In the Contacts list, tap **Search** at the bottom.</span></span>

2.  <span data-ttu-id="a8e5d-124">전체 주소 목록에만 있는 대화 상대를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="a8e5d-124">Search for a contact that exists only in the global address list.</span></span>

3.  <span data-ttu-id="a8e5d-125">대화 상대 이름이 검색 결과에 나타나는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a8e5d-125">Verify that the contact name appears in the search results.</span></span>

<span data-ttu-id="a8e5d-126">**인스턴트 메시징 및 현재 상태 테스트**</span><span class="sxs-lookup"><span data-stu-id="a8e5d-126">**Test instant messaging and presence**</span></span>

1.  <span data-ttu-id="a8e5d-127">대화 상대 목록에서 대화 상대를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="a8e5d-127">In the Contacts list, tap a contact.</span></span>

2.  <span data-ttu-id="a8e5d-128">대화 상대 카드에서 **IM** 아이콘을 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="a8e5d-128">In the contact card, tap the **IM** icon.</span></span>

3.  <span data-ttu-id="a8e5d-129">Im (인스턴트 메시징) 창이 나타나고 IM을 입력 하 고 보낼 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8e5d-129">Verify that an instant messaging (IM) window appears and that you can type and send an IM.</span></span>

<span data-ttu-id="a8e5d-130">**전화 접속 회의 테스트**</span><span class="sxs-lookup"><span data-stu-id="a8e5d-130">**Test dial-out conferencing**</span></span>

1.  <span data-ttu-id="a8e5d-131">Outlook에서 Lync 모임을 예약합니다.</span><span class="sxs-lookup"><span data-stu-id="a8e5d-131">In Outlook, schedule a Lync meeting.</span></span>

2.  <span data-ttu-id="a8e5d-132">모바일 장치에서 모임 초대를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a8e5d-132">On the mobile device, open the meeting invitation.</span></span>

3.  <span data-ttu-id="a8e5d-133">참가할 모임의 링크를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a8e5d-133">Click the link in the meeting to join.</span></span>

4.  <span data-ttu-id="a8e5d-134">회의 서비스에서 걸려 오는 전화를 받아 모임 오디오에 연결되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a8e5d-134">Answer the call from the conference service and verify that you are connected to meeting audio.</span></span>

<span data-ttu-id="a8e5d-135">**푸시 알림 테스트**</span><span class="sxs-lookup"><span data-stu-id="a8e5d-135">**Test push notifications**</span></span>

1.  <span data-ttu-id="a8e5d-136">사용자 A의 모바일 장치에서 사용자 A의 계정으로 Lync에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="a8e5d-136">On user A’s mobile device, sign in to Lync with user A’s account.</span></span>

2.  <span data-ttu-id="a8e5d-137">모바일 장치에서 다른 응용 프로그램을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a8e5d-137">Open another application on the mobile device.</span></span>

3.  <span data-ttu-id="a8e5d-138">다른 클라이언트에서 사용자 B의 계정으로 Lync에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="a8e5d-138">On a different client, sign in to Lync with user B’s account.</span></span>

4.  <span data-ttu-id="a8e5d-139">사용자 B로부터 사용자 A에게 IM을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="a8e5d-139">Send an IM from user B to user A.</span></span>

5.  <span data-ttu-id="a8e5d-140">IM 알림이 사용자 A의 모바일 장치에 나타나는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a8e5d-140">Verify that the IM notification appears on user A’s mobile device.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

