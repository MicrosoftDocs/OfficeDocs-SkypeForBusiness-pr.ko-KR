---
title: 'Lync Server 2013: 모바일 기능'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Mobility features and capabilities
ms:assetid: 12517a88-2531-44a5-bea5-d8884aff53eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh689983(v=OCS.15)
ms:contentKeyID: 48183457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e47a37acd45ed577b9ad730de39c79d4113c8f0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979106"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mobility-features-and-capabilities-in-lync-server-2013"></a><span data-ttu-id="9b775-102">Lync Server 2013의 모바일 기능</span><span class="sxs-lookup"><span data-stu-id="9b775-102">Mobility features and capabilities in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9b775-103">_**마지막으로 수정한 주제:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="9b775-103">_**Topic Last Modified:** 2013-02-19_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="9b775-104">Lync Server 2013의 누적 업데이트에 도입 된 이동성 기능: 2 월 2013은 Lync 2010 Mobile 및 Lync 2013 모바일 클라이언트 기능을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b775-104">The mobility feature introduced in the Cumulative Updates for Lync Server 2013: February 2013 supports Lync 2010 Mobile and Lync 2013 Mobile clients functionality.</span></span> <span data-ttu-id="9b775-105">Lync Server 2013 모바일 서비스를 배포 하는 경우 사용자는 지원 되는 Apple iOS, Android, Windows Phone 또는 Nokia Symbian 모바일 장치를 사용 하 여 인스턴트 메시지 보내기 및 받기, 연락처 보기, 현재 상태 보기 등의 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b775-105">When you deploy the Lync Server 2013 Mobility Service, users can use supported Apple iOS, Android, and Windows Phone, or Nokia Symbian mobile devices to perform activities such as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="9b775-106">또한 모바일 장치는 클릭 하 여 회의에 참가 하 고, 회사, 단일 전화 접속, 음성 메일 및 부재 중 통화를 통해 전화를 걸 수 있는 몇 가지 엔터프라이즈 음성 기능을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b775-106">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed calls.</span></span> <span data-ttu-id="9b775-107">Lync Server 용 누적 업데이트에 도입 된 새로운 기능 2013:2 월 2013에는 모임 참석자를 위한 VoIP (Voice over IP) 기능 및 비디오 (.H)가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b775-107">New features introduced in the Cumulative Updates for Lync Server 2013: February 2013 include Voice over IP (VoIP) capability and video (H.264) for meeting attendee.</span></span>

<span data-ttu-id="9b775-108">Lync Server 2013의 누적 업데이트에 도입 된 이동성 기능: 2 월 2013에서는 Lync 2013 모바일 클라이언트 기능을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b775-108">The mobility feature introduced in the Cumulative Updates for Lync Server 2013: February 2013 supports Lync 2013 Mobile client functionality.</span></span> <span data-ttu-id="9b775-109">Lync Server 2013의 누적 업데이트: 2 월 2013 통합 커뮤니케이션 웹 API 또는 기타를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b775-109">The Cumulative Updates for Lync Server 2013: February 2013 install Unified Communications Web API, or UCWA.</span></span> <span data-ttu-id="9b775-110">일부는 Lync 2013 모바일 클라이언트에 사용 되는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="9b775-110">UCWA is the component used for Lync 2013 Mobile clients.</span></span> <span data-ttu-id="9b775-111">Lync Server 2013에서 Mcx는 Lync 2010 모바일 클라이언트에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b775-111">In Lync Server 2013, Mcx is used for Lync 2010 Mobile clients.</span></span> <span data-ttu-id="9b775-112">Lync Server에 대 한 누적 업데이트 2013:2013 2 월에 모바일 서비스를 위한 새 진입점으로 서의 요소를 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b775-112">Cumulative Updates for Lync Server 2013: February 2013 introduce UCWA as the new entry point for mobility services.</span></span> <span data-ttu-id="9b775-113">Lync Server 2013는 lync Server 2010에 대 한 누적 업데이트 (년 11 2011 월)에 도입 된 모바일 서비스 (Mcx)를 동시에 구현 하 고 Lync 2010 Mobile에 대 한 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b775-113">Lync Server 2013 concurrently implements the Mobility Service (Mcx), introduced in the Cumulative Updates for Lync Server 2010: November 2011, and provides support for Lync 2010 Mobile.</span></span> <span data-ttu-id="9b775-114">Lync Server 2013 2013의 누적 업데이트를 배포 하는 경우 사용자가 지원 되는 Apple iOS, Android 및 Windows Phone 모바일 장치를 사용 하 여 다음과 같은 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b775-114">When you deploy the Cumulative Updates for Lync Server 2013: February 2013, users can use supported Apple iOS, Android, and Windows Phone mobile devices to perform such activities as:</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9b775-115">Lync Server 2010의 누적 업데이트에서 지원 되는 기능: (Mcx)에는 11 월 2011이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b775-115">Features supported by the Mobility Service from the Cumulative Updates for Lync Server 2010: November 2011 are noted with (Mcx).</span></span> <span data-ttu-id="9b775-116">나열 된 모든 기능은 Lync Server 2013의 누적 업데이트에서 도입 된 (예: 2013 년 2 월)에 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b775-116">All listed features are supported by the UCWA, introduced in the Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

  - <span data-ttu-id="9b775-117">인스턴트 메시지 보내기 및 받기 (Mcx)</span><span class="sxs-lookup"><span data-stu-id="9b775-117">Send and receive instant messages (Mcx)</span></span>

  - <span data-ttu-id="9b775-118">현재 상태 보기 (Mcx)</span><span class="sxs-lookup"><span data-stu-id="9b775-118">View presence (Mcx)</span></span>

  - <span data-ttu-id="9b775-119">연락처 보기 (Mcx)</span><span class="sxs-lookup"><span data-stu-id="9b775-119">View contacts (Mcx)</span></span>

  - <span data-ttu-id="9b775-120">회의에 참가 하려면 클릭 하십시오 (Mcx).</span><span class="sxs-lookup"><span data-stu-id="9b775-120">Click to join a conference (Mcx)</span></span>

  - <span data-ttu-id="9b775-121">직장 (Mcx)을 통한 통화</span><span class="sxs-lookup"><span data-stu-id="9b775-121">Call via work (Mcx)</span></span>

  - <span data-ttu-id="9b775-122">단일 숫자에 도달 (Mcx)</span><span class="sxs-lookup"><span data-stu-id="9b775-122">Single number reach (Mcx)</span></span>

  - <span data-ttu-id="9b775-123">음성 메일 (Mcx)</span><span class="sxs-lookup"><span data-stu-id="9b775-123">Voice mail (Mcx)</span></span>

  - <span data-ttu-id="9b775-124">부재 중 통화 알림 (Mcx)</span><span class="sxs-lookup"><span data-stu-id="9b775-124">Missed call notification (Mcx)</span></span>

  - <span data-ttu-id="9b775-125">VoIP (Voice over IP)</span><span class="sxs-lookup"><span data-stu-id="9b775-125">Voice over IP (VoIP)</span></span>

  - <span data-ttu-id="9b775-126">참석자 비디오 (H. 264)</span><span class="sxs-lookup"><span data-stu-id="9b775-126">Attendee video (H.264)</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9b775-127">Lync 2010 Mobile에서 Nokia Symbian 장치에 대 한 클라이언트를 제공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="9b775-127">Lync 2010 Mobile provided a client for Nokia Symbian devices.</span></span> <span data-ttu-id="9b775-128">Lync 2013 Mobile에는 Nokia Symbian 기반 장치에 대 한 클라이언트가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9b775-128">Lync 2013 Mobile will not have a client for Nokia Symbian-based devices.</span></span>



</div>

<span data-ttu-id="9b775-129">Apple iPad 사용자는 향상 된 기능에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b775-129">Apple iPad users will have access to enhanced capabilities.</span></span> <span data-ttu-id="9b775-130">오디오 통화를 사용 하 여 모임에 참가 한 후에는 iPad 사용자가 모임 내에서 업로드 된 Microsoft PowerPoint 프레젠테이션을 보고, 응용 프로그램 및 데스크톱을 공유 하 고, 모임 참가자 목록을 보고, 다른 콘텐츠 형식의 알림을 받을 수 있습니다. 모임 내에서 공유 되 고 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9b775-130">After joining a meeting by using audio call back, an iPad user will be able to view uploaded Microsoft PowerPoint presentations within a meeting, share applications and desktops, view the meeting participant list, and receive notifications of other content types that are being shared within the meeting.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="9b775-131">단일 번호에 도달 하면 사용자가 회사 번호로 전화를 건 휴대 전화에서 전화를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="9b775-131">With single number reach, a user receives calls on a mobile phone that were dialed to the work number.</span></span> <span data-ttu-id="9b775-132">작업을 통한 통화를 통해 사용자는 휴대 전화 번호 대신 회사 전화 번호를 사용 하 여 Lync 모바일 클라이언트에서 아웃 바운드 통화를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="9b775-132">With Call via Work, the user places an outbound call from the Lync Mobile client by using a work phone number instead of the mobile phone number.</span></span> <span data-ttu-id="9b775-133">전화 걸기를 사용 하면 클라이언트는 Lync Mobile 버전을 기반으로 하는 Mcx 또는 a에 대 한 요청을 보내 해당 사용자에 게 전화를 겁니다.</span><span class="sxs-lookup"><span data-stu-id="9b775-133">With dial-out, the client sends a request to Mcx or UCWA (based on the Lync Mobile version) to make the call for them.</span></span> <span data-ttu-id="9b775-134">서버가 전화를 시작 하 고 휴대폰에서 사용자에 게 다시 전화 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b775-134">The server initiates the call and then calls the user back on the mobile phone.</span></span> <span data-ttu-id="9b775-135">사용자가 응답 하면 서버는 상대방에 게 전화를 걸어 통화를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b775-135">When the user answers, the server completes the call by dialing the other party.</span></span> <span data-ttu-id="9b775-136">작업을 통한 통화를 사용 하 여 사용자는 통화 중에 작업 id를 유지할 수 있으며,이는 통화 수신자에 게 발신자의 휴대폰 번호가 표시 되지 않으며 발신자가 아웃 바운드 통화 요금을 방지 한다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="9b775-136">By using Call via Work, users can maintain their work identity during a call, which means that the call recipient does not see the caller's mobile number, and the caller avoids incurring outbound calling charges.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="9b775-137">모든 모바일 장치에서 모든 기능이 정확히 동일 하 게 작동 하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="9b775-137">Not all features work exactly the same on all mobile devices.</span></span> <span data-ttu-id="9b775-138">모바일 장치에서 지원 되는 기능에 대 한 자세한 내용은 모바일 클라이언트 비교 표 <A href="http://go.microsoft.com/fwlink/p/?linkid=234777">http://go.microsoft.com/fwlink/p/?LinkId=234777</A>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9b775-138">For details about features supported on mobile devices, see the Mobile Client Comparison Tables at <A href="http://go.microsoft.com/fwlink/p/?linkid=234777">http://go.microsoft.com/fwlink/p/?LinkId=234777</A>.</span></span> <span data-ttu-id="9b775-139">지원 되는 장치 및 운영 체제에 대 한 자세한 내용은 <A href="lync-server-2013-planning-for-mobile-clients.md">Lync Server 2013의 모바일 클라이언트 계획</A>에서 요구 사항 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9b775-139">For details about supported devices and operating systems, see the requirements topics under <A href="lync-server-2013-planning-for-mobile-clients.md">Planning for mobile clients in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="9b775-140">Lync Server 2013 자동 검색 기능을 사용 하는 경우 모바일 응용 프로그램은 사용자가 수동으로 해당 장치 설정에 Url을 입력할 필요 없이 Lync Server 2013 웹 서비스를 자동으로 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b775-140">When you use the Lync Server 2013 Autodiscover feature, mobile applications can automatically locate Lync Server 2013 Web Services without requiring users to manually enter the URLs in their device settings.</span></span> <span data-ttu-id="9b775-141">모바일 장치 설정에서 수동으로 Url을 입력 하는 것도 주로 문제 해결을 위해 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b775-141">Manually entering URLs in mobile device settings is also supported, primarily for troubleshooting purposes.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9b775-142">Mcx 및 2013 2010/또는 a i h a i a i a h a i a i a i a i a i a i a i a i a i a i a</span><span class="sxs-lookup"><span data-stu-id="9b775-142">The Mcx and UCWA are complimentary services and both are deployed to support Lync 2010 Mobile and Lync 2013 Mobile clients.</span></span> <span data-ttu-id="9b775-143">Lync 2013 Mobile에서 Lync Server 2010 배포에 로그인 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9b775-143">Lync 2013 Mobile will not be able to sign in to Lync Server 2010 deployments.</span></span> <span data-ttu-id="9b775-144">Lync 2010 모바일 및 Lync 2013 Mobile은 lync server 2013 배포를 사용할 수 있습니다.: 2 월 2013 적용 됨 2013이 업데이트 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9b775-144">Lync 2010 Mobile and Lync 2013 Mobile will be able to use a Lync Server 2013 deployment with the Cumulative Updates for Lync Server 2013: February 2013 applied.</span></span>



</div>

<span data-ttu-id="9b775-145">또한 모바일 기능은 백그라운드에서 실행 되는 응용 프로그램을 지원 하지 않는 모바일 장치에 대 한 *푸시 알림을* 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b775-145">The mobility feature also supports *push notifications* for mobile devices that do not support applications running in the background.</span></span> <span data-ttu-id="9b775-146">푸시 알림은 모바일 응용 프로그램이 비활성 상태일 때 발생 하는 이벤트에 대 한 모바일 장치에 전송 되는 알림입니다.</span><span class="sxs-lookup"><span data-stu-id="9b775-146">A push notification is a notification that is sent to a mobile device about an event that occurs while a mobile application is inactive.</span></span> <span data-ttu-id="9b775-147">예를 들어 부재 중 메신저 대화 초대를 통해 푸시 알림을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b775-147">For example, a missed instant messaging (IM) invitation can result in a push notification.</span></span>

<span data-ttu-id="9b775-148">Mcx, 함께, 자동 검색 서비스, 푸시 알림 지원은 Lync Server 2013에서 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b775-148">Mcx, UCWA, Autodiscover Service, and support for push notifications are provided in Lync Server 2013.</span></span> <span data-ttu-id="9b775-149">모바일 진입점에 대 한 업데이트 된 클라이언트 기능, 기능 및 사용은 Lync Server 2013:2013 2 월에 대 한 누적 업데이트에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9b775-149">Updated client features, capabilities, and the use of UCWA as the mobility entry point are introduced in the Cumulative Updates for Lync Server 2013: February 2013.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

