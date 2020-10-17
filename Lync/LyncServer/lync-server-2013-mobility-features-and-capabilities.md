---
title: 'Lync Server 2013: 모바일 기능 및 기능'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mobility features and capabilities
ms:assetid: 12517a88-2531-44a5-bea5-d8884aff53eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh689983(v=OCS.15)
ms:contentKeyID: 48183457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3eecf3d55ba3bb8e8629d41a9a924c65ac7a4c0e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516135"
---
# <a name="mobility-features-and-capabilities-in-lync-server-2013"></a><span data-ttu-id="73d5b-102">Lync Server 2013의 모바일 기능</span><span class="sxs-lookup"><span data-stu-id="73d5b-102">Mobility features and capabilities in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="73d5b-103">_**마지막으로 수정 된 항목:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="73d5b-103">_**Topic Last Modified:** 2013-02-19_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="73d5b-104">Lync Server 2013 용 누적 업데이트에 도입 된 모바일 기능: 2 월 2013은 Lync 2010 Mobile 및 Lync 2013 모바일 클라이언트 기능을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="73d5b-104">The mobility feature introduced in the Cumulative Updates for Lync Server 2013: February 2013 supports Lync 2010 Mobile and Lync 2013 Mobile clients functionality.</span></span> <span data-ttu-id="73d5b-105">Lync Server 2013 Mobility Service를 배포할 때는 사용자가 지원 되는 Apple iOS, Android, Windows Phone 또는 Nokia Symbian 모바일 장치를 사용 하 여 인스턴트 메시지 보내기/받기, 연락처 보기, 현재 상태 보기 등의 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73d5b-105">When you deploy the Lync Server 2013 Mobility Service, users can use supported Apple iOS, Android, and Windows Phone, or Nokia Symbian mobile devices to perform activities such as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="73d5b-106">또한 모바일 장치에서는 클릭하여 회의 참가, 회사번호로 전화, 단일 번호 연결, 음성 메일, 부재 중 통화 등의 일부 Enterprise Voice 기능도 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="73d5b-106">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed calls.</span></span> <span data-ttu-id="73d5b-107">Lync Server 2013 용 누적 업데이트에 도입 된 새로운 기능: 2 월 2013 회의 참석자를 위한 VoIP (Voice over IP) 기능 및 동영상 (.H)을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="73d5b-107">New features introduced in the Cumulative Updates for Lync Server 2013: February 2013 include Voice over IP (VoIP) capability and video (H.264) for meeting attendee.</span></span>

<span data-ttu-id="73d5b-108">Lync Server 2013 용 누적 업데이트에 도입 된 모바일 기능: 2 월 2013은 Lync 2013 모바일 클라이언트 기능을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="73d5b-108">The mobility feature introduced in the Cumulative Updates for Lync Server 2013: February 2013 supports Lync 2013 Mobile client functionality.</span></span> <span data-ttu-id="73d5b-109">Lync Server 2013 용 누적 업데이트: 2 월 2013 통합 커뮤니케이션 웹 API 또는 c를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="73d5b-109">The Cumulative Updates for Lync Server 2013: February 2013 install Unified Communications Web API, or UCWA.</span></span> <span data-ttu-id="73d5b-110">(C)는 Lync 2013 모바일 클라이언트에 사용 되는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="73d5b-110">UCWA is the component used for Lync 2013 Mobile clients.</span></span> <span data-ttu-id="73d5b-111">Lync Server 2013에서는 Mcx가 Lync 2010 모바일 클라이언트에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73d5b-111">In Lync Server 2013, Mcx is used for Lync 2010 Mobile clients.</span></span> <span data-ttu-id="73d5b-112">Lync Server에 대 한 누적 업데이트 2013:2 월 2013에는 모바일 서비스에 대 한 새 진입점으로 필요한 요소를 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="73d5b-112">Cumulative Updates for Lync Server 2013: February 2013 introduce UCWA as the new entry point for mobility services.</span></span> <span data-ttu-id="73d5b-113">Lync Server 2013는 lync Server 2010 용 누적 업데이트: 11 월 2011 12 일에 도입 된 모바일 서비스 (Mcx)를 동시에 구현 하며 Lync 2010 Mobile에 대 한 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="73d5b-113">Lync Server 2013 concurrently implements the Mobility Service (Mcx), introduced in the Cumulative Updates for Lync Server 2010: November 2011, and provides support for Lync 2010 Mobile.</span></span> <span data-ttu-id="73d5b-114">Lync Server 2013 2013에 대 한 누적 업데이트를 배포 하는 경우 사용자는 다음과 같은 작업을 수행 하기 위해 지원 되는 Apple iOS, Android 및 Windows Phone 모바일 장치를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73d5b-114">When you deploy the Cumulative Updates for Lync Server 2013: February 2013, users can use supported Apple iOS, Android, and Windows Phone mobile devices to perform such activities as:</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="73d5b-115">Lync Server 용 누적 업데이트 2010에서 지원 되는 기능: 11 월 2011은 (Mcx)에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73d5b-115">Features supported by the Mobility Service from the Cumulative Updates for Lync Server 2010: November 2011 are noted with (Mcx).</span></span> <span data-ttu-id="73d5b-116">나열 된 모든 기능은 Lync Server 2013:2 월 2013에 대 한 누적 업데이트에 도입 된 작업을 통해 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73d5b-116">All listed features are supported by the UCWA, introduced in the Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

  - <span data-ttu-id="73d5b-117">인스턴트 메시지 보내기 및 받기 (Mcx)</span><span class="sxs-lookup"><span data-stu-id="73d5b-117">Send and receive instant messages (Mcx)</span></span>

  - <span data-ttu-id="73d5b-118">현재 상태 보기 (Mcx)</span><span class="sxs-lookup"><span data-stu-id="73d5b-118">View presence (Mcx)</span></span>

  - <span data-ttu-id="73d5b-119">대화 상대 보기 (Mcx)</span><span class="sxs-lookup"><span data-stu-id="73d5b-119">View contacts (Mcx)</span></span>

  - <span data-ttu-id="73d5b-120">회의에 참가 하려면 클릭 합니다 (Mcx).</span><span class="sxs-lookup"><span data-stu-id="73d5b-120">Click to join a conference (Mcx)</span></span>

  - <span data-ttu-id="73d5b-121">직장을 통한 통화 (Mcx)</span><span class="sxs-lookup"><span data-stu-id="73d5b-121">Call via work (Mcx)</span></span>

  - <span data-ttu-id="73d5b-122">1 번 도착 (Mcx)</span><span class="sxs-lookup"><span data-stu-id="73d5b-122">Single number reach (Mcx)</span></span>

  - <span data-ttu-id="73d5b-123">음성 메일 (Mcx)</span><span class="sxs-lookup"><span data-stu-id="73d5b-123">Voice mail (Mcx)</span></span>

  - <span data-ttu-id="73d5b-124">부재 중 전화 알림 (Mcx)</span><span class="sxs-lookup"><span data-stu-id="73d5b-124">Missed call notification (Mcx)</span></span>

  - <span data-ttu-id="73d5b-125">VoIP(Voice over IP)</span><span class="sxs-lookup"><span data-stu-id="73d5b-125">Voice over IP (VoIP)</span></span>

  - <span data-ttu-id="73d5b-126">참석자 비디오 (.H. 264)</span><span class="sxs-lookup"><span data-stu-id="73d5b-126">Attendee video (H.264)</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="73d5b-127">Lync 2010 Mobile에서는 Nokia Symbian 장치에 대 한 클라이언트를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="73d5b-127">Lync 2010 Mobile provided a client for Nokia Symbian devices.</span></span> <span data-ttu-id="73d5b-128">Lync 2013 Mobile에는 Nokia Symbian 기반 장치에 대 한 클라이언트가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="73d5b-128">Lync 2013 Mobile will not have a client for Nokia Symbian-based devices.</span></span>



</div>

<span data-ttu-id="73d5b-129">Apple iPad 사용자는 향상된 기능에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73d5b-129">Apple iPad users will have access to enhanced capabilities.</span></span> <span data-ttu-id="73d5b-130">오디오 통화를 사용 하 여 모임에 참가 한 후에는 iPad 사용자가 모임 내에서 업로드 된 Microsoft PowerPoint 프레젠테이션을 보고, 응용 프로그램 및 데스크톱을 공유 하 고, 모임 참가자 목록을 보고, 모임 내에서 공유 되는 다른 콘텐츠 형식에 대 한 알림을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73d5b-130">After joining a meeting by using audio call back, an iPad user will be able to view uploaded Microsoft PowerPoint presentations within a meeting, share applications and desktops, view the meeting participant list, and receive notifications of other content types that are being shared within the meeting.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="73d5b-131">단일 번호 연결을 사용하는 경우 회사 번호로 걸려온 전화를 휴대폰에서 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73d5b-131">With single number reach, a user receives calls on a mobile phone that were dialed to the work number.</span></span> <span data-ttu-id="73d5b-132">직장에서 작업을 수행 하는 경우 사용자는 휴대폰 번호 대신 회사 전화 번호를 사용 하 여 Lync 모바일 클라이언트에서 아웃 바운드 호출을 합니다.</span><span class="sxs-lookup"><span data-stu-id="73d5b-132">With Call via Work, the user places an outbound call from the Lync Mobile client by using a work phone number instead of the mobile phone number.</span></span> <span data-ttu-id="73d5b-133">전화 걸기를 사용 하는 경우 클라이언트는 Lync Mobile 버전을 기반으로 Mcx 또는 WA 인천에 요청을 보내 통화를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="73d5b-133">With dial-out, the client sends a request to Mcx or UCWA (based on the Lync Mobile version) to make the call for them.</span></span> <span data-ttu-id="73d5b-134">그러면 서버에서는 통화를 시작한 다음 사용자의 휴대폰으로 다시 전화를 겁니다.</span><span class="sxs-lookup"><span data-stu-id="73d5b-134">The server initiates the call and then calls the user back on the mobile phone.</span></span> <span data-ttu-id="73d5b-135">사용자가 전화를 받으면 서버에서 상대방에 전화를 걸어 통화를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="73d5b-135">When the user answers, the server completes the call by dialing the other party.</span></span> <span data-ttu-id="73d5b-136">회사번호로 전화 기능을 사용하면 통화 중에 회사 번호가 표시되도록 할 수 있으므로 통화 수신자가 발신자의 휴대폰 번호를 볼 수 없으며, 발신자에게 발신 통화 요금이 부과되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="73d5b-136">By using Call via Work, users can maintain their work identity during a call, which means that the call recipient does not see the caller's mobile number, and the caller avoids incurring outbound calling charges.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="73d5b-137">모든 기능이 모든 모바일 장치에서 정확히 동일하게 작동하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="73d5b-137">Not all features work exactly the same on all mobile devices.</span></span> <span data-ttu-id="73d5b-138">모바일 장치에서 지원 되는 기능에 대 한 자세한 내용은 모바일 클라이언트 비교 표를 참조 하세요 <A href="https://go.microsoft.com/fwlink/p/?linkid=234777">https://go.microsoft.com/fwlink/p/?LinkId=234777</A> .</span><span class="sxs-lookup"><span data-stu-id="73d5b-138">For details about features supported on mobile devices, see the Mobile Client Comparison Tables at <A href="https://go.microsoft.com/fwlink/p/?linkid=234777">https://go.microsoft.com/fwlink/p/?LinkId=234777</A>.</span></span> <span data-ttu-id="73d5b-139">지원 되는 장치 및 운영 체제에 대 한 자세한 내용은 <A href="lync-server-2013-planning-for-mobile-clients.md">Lync Server 2013의 모바일 클라이언트 계획</A>에서 요구 사항 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="73d5b-139">For details about supported devices and operating systems, see the requirements topics under <A href="lync-server-2013-planning-for-mobile-clients.md">Planning for mobile clients in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="73d5b-140">Lync Server 2013 자동 검색 기능을 사용할 때 모바일 응용 프로그램은 사용자가 자신의 장치 설정에 Url을 수동으로 입력할 필요 없이 Lync Server 2013 웹 서비스를 자동으로 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73d5b-140">When you use the Lync Server 2013 Autodiscover feature, mobile applications can automatically locate Lync Server 2013 Web Services without requiring users to manually enter the URLs in their device settings.</span></span> <span data-ttu-id="73d5b-141">그러나 모바일 장치 설정에서 URL을 수동으로 입력할 수도 있으며, 이 기능은 주로 문제 해결을 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="73d5b-141">Manually entering URLs in mobile device settings is also supported, primarily for troubleshooting purposes.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="73d5b-142">Mcx 및 WA는 무료 서비스이 고 둘 다 Lync 2010 모바일 및 Lync 2013 모바일 클라이언트를 지원 하기 위해 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73d5b-142">The Mcx and UCWA are complimentary services and both are deployed to support Lync 2010 Mobile and Lync 2013 Mobile clients.</span></span> <span data-ttu-id="73d5b-143">Lync 2013 Mobile은 Lync Server 2010 배포에 로그인 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="73d5b-143">Lync 2013 Mobile will not be able to sign in to Lync Server 2010 deployments.</span></span> <span data-ttu-id="73d5b-144">Lync 2010 모바일 및 Lync 2013 Mobile에서는 lync Server 2013:2 2013 월 적용 된 lync server 2013 배포를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73d5b-144">Lync 2010 Mobile and Lync 2013 Mobile will be able to use a Lync Server 2013 deployment with the Cumulative Updates for Lync Server 2013: February 2013 applied.</span></span>



</div>

<span data-ttu-id="73d5b-145">모바일 기능에는 또한 백그라운드에서 실행 중인 응용 프로그램을 지원하지 않는 모바일 장치를 위한 *푸시 알림*도 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="73d5b-145">The mobility feature also supports *push notifications* for mobile devices that do not support applications running in the background.</span></span> <span data-ttu-id="73d5b-146">푸시 알림은 해당 모바일 응용 프로그램이 비활성 상태일 때 발생한 이벤트에 대해 모바일 장치에 전송되는 알림입니다.</span><span class="sxs-lookup"><span data-stu-id="73d5b-146">A push notification is a notification that is sent to a mobile device about an event that occurs while a mobile application is inactive.</span></span> <span data-ttu-id="73d5b-147">예를 들어 부재 중 IM (인스턴트 메시징) 초대로 인해 푸시 알림이 생성 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73d5b-147">For example, a missed instant messaging (IM) invitation can result in a push notification.</span></span>

<span data-ttu-id="73d5b-148">Mcx, COWA, 자동 검색 서비스 및 푸시 알림 지원은 Lync Server 2013에 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73d5b-148">Mcx, UCWA, Autodiscover Service, and support for push notifications are provided in Lync Server 2013.</span></span> <span data-ttu-id="73d5b-149">업데이트 된 클라이언트 기능, 기능 및 이동성 진입점을 사용 하는 경우 Lync Server 2013:2 월 2013에 대 한 누적 업데이트에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="73d5b-149">Updated client features, capabilities, and the use of UCWA as the mobility entry point are introduced in the Cumulative Updates for Lync Server 2013: February 2013.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

