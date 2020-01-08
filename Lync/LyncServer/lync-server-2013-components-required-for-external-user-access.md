---
title: 'Lync Server 2013: 외부 사용자 액세스에 필요한 구성 요소'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components required for external user access
ms:assetid: 2d0f9817-14e7-4109-95dc-62420e3c29e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425779(v=OCS.15)
ms:contentKeyID: 48183711
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 895f2d4837eb465f0eead2b70cf1d603504699ba
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979564"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-required-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="d95af-102">Lync Server 2013의 외부 사용자 액세스에 필요한 구성 요소</span><span class="sxs-lookup"><span data-stu-id="d95af-102">Components required for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d95af-103">_**마지막으로 수정한 주제:** 2014-05-29_</span><span class="sxs-lookup"><span data-stu-id="d95af-103">_**Topic Last Modified:** 2014-05-29_</span></span>

<span data-ttu-id="d95af-104">대부분의 Edge 구성 요소는 경계 네트워크에 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d95af-104">Most Edge components are deployed in a perimeter network.</span></span> <span data-ttu-id="d95af-105">다음 구성 요소는 경계 네트워크의 가장자리 토폴로지를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d95af-105">The following components make up the edge topology of the perimeter network.</span></span> <span data-ttu-id="d95af-106">명시 된 경우를 제외 하 고, 구성 요소는 [Lync Server 2013에서 외부 사용자 액세스에 대 한 시나리오](lync-server-2013-scenarios-for-external-user-access.md) 의 일부 이며 주변 네트워크에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d95af-106">Except where noted, the components are part of the [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) and are in the perimeter network.</span></span> <span data-ttu-id="d95af-107">Edge 구성 요소에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d95af-107">Edge components include the following:</span></span>

  - <span data-ttu-id="d95af-108">Edge 서버</span><span class="sxs-lookup"><span data-stu-id="d95af-108">Edge Servers</span></span>

  - <span data-ttu-id="d95af-109">리버스 프록시</span><span class="sxs-lookup"><span data-stu-id="d95af-109">Reverse proxies</span></span>

  - <span data-ttu-id="d95af-110">들</span><span class="sxs-lookup"><span data-stu-id="d95af-110">Firewalls</span></span>

  - <span data-ttu-id="d95af-111">디렉터 (선택 사항, 논리적으로는 내부 네트워크에 위치)</span><span class="sxs-lookup"><span data-stu-id="d95af-111">Directors (optional, and logically located on the internal network)</span></span>

  - <span data-ttu-id="d95af-112">확장 된 Edge 토폴로지에 대 한 부하 분산 (DNS 부하 분산 또는 하드웨어 부하 분산 장치)</span><span class="sxs-lookup"><span data-stu-id="d95af-112">Load balancing for Scaled Edge Topologies (either DNS load balancing or a hardware load balancer)</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d95af-113">한 인터페이스에서 DNS 부하 분산을 사용 하는 것은 불가능 하지만, 하드웨어 부하 분산이 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d95af-113">Using DNS load balancing on one interface and hardware load balancing on the other is not supported.</span></span> <span data-ttu-id="d95af-114">둘 다에 대해 인터페이스 또는 DNS 부하 분산에 대해 하드웨어 부하 분산을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d95af-114">You must use hardware load balancing for both interfaces or DNS load balancing for both.</span></span>

    
    </div>

<div>

## <a name="edge-servers"></a><span data-ttu-id="d95af-115">Edge 서버</span><span class="sxs-lookup"><span data-stu-id="d95af-115">Edge Servers</span></span>

<span data-ttu-id="d95af-116">Edge 서버는 외부 사용자의 내부 배포에서 제공 하는 서비스에 대 한 네트워크 트래픽을 주고 받습니다.</span><span class="sxs-lookup"><span data-stu-id="d95af-116">The Edge Servers send and receive network traffic for the services offered by internal deployment by external users.</span></span> <span data-ttu-id="d95af-117">Edge 서버는 다음 서비스를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d95af-117">The Edge Server runs the following services:</span></span>

  - <span data-ttu-id="d95af-118">**액세스에 지 서비스**   액세스에 지 서비스는 아웃 바운드 및 인바운드 세션 초기화 프로토콜 (SIP) 트래픽 모두에 대해 신뢰할 수 있는 단일 연결 지점을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d95af-118">**Access Edge service**   The Access Edge service provides a single, trusted connection point for both outbound and inbound Session Initiation Protocol (SIP) traffic.</span></span>

  - <span data-ttu-id="d95af-119">**웹 회의에 지 서비스**   웹 회의에 지 서비스를 통해 외부 사용자가 내부 Lync Server 2013 배포에 호스트 된 모임에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d95af-119">**Web Conferencing Edge service**   The Web Conferencing Edge service enables external users to join meetings that are hosted on your internal Lync Server 2013 deployment.</span></span>

  - <span data-ttu-id="d95af-120">**A/v edge 서비스**   a/v edge 서비스는 오디오, 비디오, 응용 프로그램 공유 및 외부 사용자가 파일 전송을 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d95af-120">**A/V Edge service**   The A/V Edge service makes audio, video, application sharing, and file transfer available to external users.</span></span> <span data-ttu-id="d95af-121">사용자는 외부 참가자가 포함 된 모임에 오디오 및 비디오를 추가할 수 있으며, 지점간 세션에서 외부 사용자와 직접 오디오 및 비디오를 사용 하 여 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d95af-121">Your users can add audio and video to meetings that include external participants, and they can communicate using audio and/or video directly with an external user in point-to-point sessions.</span></span> <span data-ttu-id="d95af-122">또한 A/V Edge 서비스는 데스크톱 공유 및 파일 전송에 대 한 지원도 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d95af-122">The A/V Edge service also provides support for desktop sharing and file transfer.</span></span>

  - <span data-ttu-id="d95af-123">\*\*\*\*   Xmpp 프록시 서비스 xmpp 프록시 서비스는 확장할 수 있는 메시징 및 현재 상태 프로토콜 (xmpp) 메시지를 구성 된 xmpp 페더레이션 파트너와 주고 받습니다.</span><span class="sxs-lookup"><span data-stu-id="d95af-123">**XMPP Proxy service**   The XMPP Proxy service accepts and sends extensible messaging and presence protocol (XMPP) messages to and from configured XMPP Federated partners.</span></span>

<span data-ttu-id="d95af-124">권한이 부여 된 외부 사용자는 내부 Lync Server 2013 배포에 연결 하기 위해 Edge 서버에 액세스할 수 있지만, Edge 서버는 내부 네트워크에 대 한 다른 액세스를 위한 수단을 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d95af-124">Authorized external users can access the Edge Servers in order to connect to your internal Lync Server 2013 deployment, but the Edge Servers do not provide a means for any other access to the internal network.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d95af-125">Edge 서버는 활성화 된 Lync 클라이언트 및 기타 Microsoft Edge 서버에 대 한 연결을 제공 하기 위해 배포 됩니다 (페더레이션 시나리오의 경우).</span><span class="sxs-lookup"><span data-stu-id="d95af-125">Edge servers are deployed to provide connections for enabled Lync clients and other Microsoft Edge servers (as in federation scenarios).</span></span> <span data-ttu-id="d95af-126">다른 끝점 클라이언트나 서버 유형에 대 한 연결을 허용 하도록 설계 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="d95af-126">They are not designed to allow connections from other end point client or server types.</span></span> <span data-ttu-id="d95af-127">XMPP 게이트웨이 서버는 구성 된 XMPP 파트너와의 연결을 허용 하도록 배포 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d95af-127">The XMPP Gateway server can be deployed to allow connections with configured XMPP partners.</span></span> <span data-ttu-id="d95af-128">Edge 서버 및 XMPP 게이트웨이는 이러한 클라이언트 및 페더레이션 유형의 끝점 연결만 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d95af-128">The Edge server and XMPP Gateway can only support end point connections from these client and federation types.</span></span>



</div>

</div>

<div>

## <a name="reverse-proxy"></a><span data-ttu-id="d95af-129">역방향 프록시</span><span class="sxs-lookup"><span data-stu-id="d95af-129">Reverse Proxy</span></span>

<span data-ttu-id="d95af-130">리버스 프록시는 다음에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d95af-130">The reverse proxy is required for the following:</span></span>

  - <span data-ttu-id="d95af-131">사용자가 간단한 Url을 사용 하 여 모임 또는 전화 접속 회의에 연결할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="d95af-131">To allow users to connect to meetings or dial-in conferences using simple URLs</span></span>

  - <span data-ttu-id="d95af-132">외부 사용자가 모임 콘텐츠를 다운로드할 수 있도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="d95af-132">To enable external users to download meeting content</span></span>

  - <span data-ttu-id="d95af-133">외부 사용자가 메일 그룹을 확장할 수 있도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="d95af-133">To enable external users to expand distribution groups</span></span>

  - <span data-ttu-id="d95af-134">사용자가 클라이언트 인증서 기반 인증을 위해 사용자 기반 인증서를 얻을 수 있도록 허용 하려면</span><span class="sxs-lookup"><span data-stu-id="d95af-134">To allow the user to obtain a user-based certificate for client certificate based authentication</span></span>

  - <span data-ttu-id="d95af-135">원격 사용자가 주소록 서버에서 파일을 다운로드 하거나 주소록 웹 쿼리 서비스에 쿼리를 제출할 수 있도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="d95af-135">To enable remote users to download files from the Address Book Server or to submit queries to the Address Book Web Query service</span></span>

  - <span data-ttu-id="d95af-136">원격 사용자가 클라이언트 및 장치 소프트웨어에 대 한 업데이트를 얻을 수 있도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="d95af-136">To enable remote users to obtain updates to client and device software</span></span>

  - <span data-ttu-id="d95af-137">모바일 장치에서 이동성 서비스를 제공 하는 프런트 엔드 서버를 자동으로 검색 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="d95af-137">To enable mobile devices to automatically discover Front End Servers offering mobility services</span></span>

  - <span data-ttu-id="d95af-138">Office 365 또는 Apple push notification services에서 모바일 장치에 대 한 푸시 알림을 사용 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="d95af-138">To enable push notifications to mobile devices from the Office 365 or Apple push notification services</span></span>

<span data-ttu-id="d95af-139">리버스 프록시와 충족 해야 하는 요구 사항에 대 한 추가 정보는 [Lync Server 2013의 리버스 프록시에 대 한 구성 요구 사항](lync-server-2013-configuration-requirements-for-reverse-proxy.md)정보를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d95af-139">For additional information related to reverse proxies and the requirements that reverse proxies must meet, see the details in [Configuration requirements for reverse proxy in Lync Server 2013](lync-server-2013-configuration-requirements-for-reverse-proxy.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d95af-140">외부 사용자는 Lync Server 2013를 사용 하 여 통신에 참가 하기 위해 조직에 대 한 VPN (가상 사설망) 연결이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d95af-140">External users do not need a virtual private network (VPN) connection to your organization in order to participate in communications using Lync Server 2013.</span></span> <span data-ttu-id="d95af-141">조직에서 VPN 기술을 구현 하 고 사용자가 Lync 용 VPN을 사용 하는 경우 미디어 트래픽 (예: 비디오 회의)이 악영향을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d95af-141">If you have implemented VPN technology in your organization and your users use the VPN for Lync, media traffic (such as video conferencing) can be adversely affected.</span></span> <span data-ttu-id="d95af-142">미디어 트래픽이 AV Edge 서비스에 직접 연결 하 고 VPN을 우회 하는 방법을 제공 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d95af-142">You should consider providing a means for media traffic to connect to the AV Edge service directly and bypass the VPN.</span></span> <span data-ttu-id="d95af-143">자세한 내용은 NextHop 블로그 문서, Lync 미디어에서 VPN 터널 우회 기능 사용 "을 참조 하세요 <A href="http://go.microsoft.com/fwlink/p/?linkid=256532">http://go.microsoft.com/fwlink/p/?LinkId=256532</A>.</span><span class="sxs-lookup"><span data-stu-id="d95af-143">For details, see the NextHop Blog article, “Enabling Lync Media to Bypass a VPN Tunnel,” at <A href="http://go.microsoft.com/fwlink/p/?linkid=256532">http://go.microsoft.com/fwlink/p/?LinkId=256532</A>.</span></span>



</div>

</div>

<div>

## <a name="firewall"></a><span data-ttu-id="d95af-144">방화벽</span><span class="sxs-lookup"><span data-stu-id="d95af-144">Firewall</span></span>

<span data-ttu-id="d95af-145">외부 방화벽 또는 외부 및 내부 방화벽과 모두 함께 edge 토폴로지를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d95af-145">You can deploy your edge topology with only an external firewall or both external and internal firewalls.</span></span> <span data-ttu-id="d95af-146">시나리오 아키텍처에는 두 개의 방화벽이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d95af-146">The scenario architectures include two firewalls.</span></span> <span data-ttu-id="d95af-147">두 개의 방화벽을 사용 하는 것이 권장 되는 방법으로, 네트워크 경계 간에 엄격한 라우팅이 보장 되 고 두 가지 수준의 방화벽으로 내부 배포를 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="d95af-147">Using two firewalls is the recommended approach because it ensures strict routing from one network edge to the other, and it protects your internal deployment behind two levels of firewall.</span></span>

</div>

<div>

## <a name="director"></a><span data-ttu-id="d95af-148">Director</span><span class="sxs-lookup"><span data-stu-id="d95af-148">Director</span></span>

<span data-ttu-id="d95af-149">디렉터는 가정용 사용자 계정이 아니거나 현재 상태 또는 회의 서비스를 제공 하는 Lync Server 2013의 별도의 선택적 서버 역할입니다.</span><span class="sxs-lookup"><span data-stu-id="d95af-149">A Director is a separate, optional server role in Lync Server 2013 that does not home user accounts, or provide presence or conferencing services.</span></span> <span data-ttu-id="d95af-150">이 서비스는 Edge 서버가 내부 서버를 대상으로 하는 인바운드 SIP 트래픽을 라우팅하는 내부 다음 홉 서버로 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="d95af-150">It serves as an internal next hop server to which an Edge Server routes inbound SIP traffic destined for internal servers.</span></span> <span data-ttu-id="d95af-151">디렉터는 인바운드 요청을 사전 인증 하 고 사용자의 홈 풀이나 서버로 리디렉션합니다.</span><span class="sxs-lookup"><span data-stu-id="d95af-151">The Director preauthenticates inbound requests and redirects them to the user’s home pool or server.</span></span> <span data-ttu-id="d95af-152">디렉터에서 사전 인증을 통해 배포에 알려지지 않은 사용자 계정의 요청을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d95af-152">By preauthenticating at the Director, you can drop requests from user accounts that are unknown to the deployment.</span></span>

<span data-ttu-id="d95af-153">디렉터는 DoS (서비스 거부) 공격과 같은 악의적인 트래픽에 대 한 엔터프라이즈 에디션 프런트 엔드 풀의 표준 버전 서버와 프런트 엔드 서버를 보장 합니다.</span><span class="sxs-lookup"><span data-stu-id="d95af-153">A Director helps insulate Standard Edition servers and Front End Servers in Enterprise Edition Front End pools from malicious traffic such as denial-of-service (DoS) attacks.</span></span> <span data-ttu-id="d95af-154">이러한 공격에서 유효 하지 않은 외부 트래픽으로 네트워크에 장애가 발생 하는 경우에는 해당 트래픽이 디렉터에서 끝납니다.</span><span class="sxs-lookup"><span data-stu-id="d95af-154">If the network is flooded with invalid external traffic in such an attack, the traffic ends at the Director.</span></span> <span data-ttu-id="d95af-155">디렉터 사용에 대 한 자세한 내용은 [Lync Server 2013의 디렉터에 대 한 시나리오](lync-server-2013-scenarios-for-the-director.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d95af-155">For details about the use of Directors, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d95af-156">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d95af-156">See Also</span></span>


[<span data-ttu-id="d95af-157">Lync Server 2013에 대한 하드웨어 부하 분산 장치 요구 사항</span><span class="sxs-lookup"><span data-stu-id="d95af-157">Hardware load balancer requirements for Lync Server 2013</span></span>](lync-server-2013-hardware-load-balancer-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

