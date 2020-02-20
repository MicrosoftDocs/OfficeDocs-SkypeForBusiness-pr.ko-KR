---
title: 'Lync Server 2013: SIP 트렁크에 대 한 구성 요소 및 토폴로지'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for SIP trunking
ms:assetid: 8ed9a9d0-517e-4f36-a131-22cdafa257fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398720(v=OCS.15)
ms:contentKeyID: 48184775
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b81768fe055c28fb8643a267b74de4cc99bc0ff3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147331"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-sip-trunking-in-lync-server-2013"></a><span data-ttu-id="372c8-102">Lync Server 2013의 SIP 트렁크에 대 한 구성 요소 및 토폴로지</span><span class="sxs-lookup"><span data-stu-id="372c8-102">Components and topologies for SIP trunking in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="372c8-103">_**마지막으로 수정 된 항목:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="372c8-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="372c8-104">다음 그림에서는 Lync Server의 SIP 트렁크 토폴로지를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="372c8-104">The following figure depicts the SIP trunking topology in Lync Server.</span></span>

<span data-ttu-id="372c8-105">**SIP 트렁크 토폴로지**</span><span class="sxs-lookup"><span data-stu-id="372c8-105">**SIP trunking topology**</span></span>

<span data-ttu-id="372c8-106">![SIP 트렁크 토폴로지](images/Gg398720.669fb55d-7c81-4e21-9421-fabc43d6e064(OCS.15).jpg "SIP 트렁크 토폴로지")</span><span class="sxs-lookup"><span data-stu-id="372c8-106">![SIP Trunking Topology](images/Gg398720.669fb55d-7c81-4e21-9421-fabc43d6e064(OCS.15).jpg "SIP Trunking Topology")</span></span>

<span data-ttu-id="372c8-p101">다이어그램에 나온 것처럼 엔터프라이즈 네트워크 및 PSTN(공중 전화망) 서비스 공급자 간의 연결에 IP VPN(가상 사설망)이 사용됩니다. 이 사설망의 목적은 IP 연결을 제공하고 보안을 향상시키며 선택적으로 QoS(서비스 품질) 보증을 얻는 것입니다. VPN의 특성으로 인해 SIP 신호 트래픽을 위한 TLS(Transport Layer Security)나 미디어 트래픽을 위한 SRTP(실시간 전송 프로토콜)를 사용할 필요가 없습니다. 따라서 엔터프라이즈와 서비스 공급자 간의 연결은 SIP를 위한 일반 TCP 연결 및 IP VPN을 통해 터널링되는 미디어를 위한 UDP를 통한 일반 RTP(실시간 전송 프로토콜)로 구성됩니다. 이때 VPN 라우터 간 모든 방화벽에서는 VPN 라우터가 통신할 수 있도록 포트를 열어 놓아야 하고 VPN 라우터의 외부 에지에 대한 IP 주소는 공개적으로 라우팅 가능한 주소여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="372c8-p101">As shown in the diagram, an IP virtual private network (VPN) is used for connectivity between the enterprise network and the public switched telephone network (PSTN) service provider. The purpose of this private network is to provide IP connectivity, enhance security, and (optionally) obtain Quality of Service (QoS) guarantees. Because of the nature of a VPN, you do not need to use Transport Layer Security (TLS) for SIP signaling traffic or secure real-time transport protocol (SRTP) for the media traffic. Connections between the enterprise and the service provider therefore consist of plain TCP connections for SIP and plain real-time transport protocol (RTP) (over UDP) for media tunneled through an IP VPN. Ensure that all firewalls between the VPN routers have ports open to allow the VPN routers to communicate, and that the IP addresses on the external edges of the VPN routers are publicly routable.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="372c8-112">서비스 공급자에 게 문의 하 여 장애 조치 (failover)를 포함 하 여 고가용성에 대 한 지원을 제공 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="372c8-112">Contact your service provider to determine whether it provides support for high availability, including failover.</span></span> <span data-ttu-id="372c8-113">해당 하는 경우 설정 절차를 결정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="372c8-113">If so, you will need to determine the procedures for setting it up.</span></span> <span data-ttu-id="372c8-114">예를 들어 각 중재 서버에 하나의 IP 주소와 하나의 SIP 트렁크를 구성 해야 합니까, 아니면 각 중재 서버에서 여러 SIP 트렁크를 구성 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="372c8-114">For example, do you need to configure only one IP address and one SIP trunk on each Mediation Server, or do you need to configure multiple SIP trunks on each Mediation Server?</span></span><BR><span data-ttu-id="372c8-115">중앙 사이트가 여러 개인 경우 서비스 공급자가 다른 중앙 사이트에 대 한 연결을 설정 하는 기능을 사용할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="372c8-115">If you have multiple central sites, also ask whether the service provider has the ability to enable connections to and from another central site.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="372c8-116">SIP 트렁크의 경우 독립 실행형 중재 서버를 배포 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="372c8-116">For SIP trunking, we strongly recommend that you deploy stand-alone Mediation Servers.</span></span> <span data-ttu-id="372c8-117">자세한 내용은 배포 설명서에서 <A href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">중재 서버 배포 및 Lync Server 2013의 피어 정의</A> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="372c8-117">For details, see <A href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">Deploying Mediation Servers and defining peers in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="securing-the-mediation-server-for-sip-trunking"></a><span data-ttu-id="372c8-118">SIP 트렁크에 대해 중재 서버 보호</span><span class="sxs-lookup"><span data-stu-id="372c8-118">Securing the Mediation Server for SIP Trunking</span></span>

<span data-ttu-id="372c8-p104">보안을 위해 두 VPN 라우터 간의 각 연결에 대해 VLAN(가상 LAN)을 설치해야 합니다. VLAN의 실제 설치 프로세스는 라우터 제조업체별로 다릅니다. 자세한 내용은 라우터 공급업체에 문의하십시오.</span><span class="sxs-lookup"><span data-stu-id="372c8-p104">For security purposes, you should set up a virtual LAN (VLAN) for each connection between the two VPN routers. The actual process for setting up a VLAN varies from one router manufacturer to another. For details, contact your router vendor.</span></span>

<span data-ttu-id="372c8-122">다음 지침을 따르는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="372c8-122">We recommend that you follow these guidelines:</span></span>

  - <span data-ttu-id="372c8-123">중재 서버와 경계 네트워크 (DMZ, 완충 영역 및 스크린 된 서브넷이 라고도 함)의 VPN 라우터 간에 VLAN (가상 LAN)을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="372c8-123">Set up a virtual LAN (VLAN) between the Mediation Server and the VPN router in the perimeter network (also known as DMZ, demilitarized zone, and screened subnet).</span></span>

  - <span data-ttu-id="372c8-124">라우터에서 VLAN으로 브로드캐스트나 멀티캐스트 패킷이 전송되는 것을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="372c8-124">Do not allow broadcast or multicast packets to be transferred from the router to the VLAN.</span></span>

  - <span data-ttu-id="372c8-125">라우터에서 중재 서버를 제외한 모든 사람에 게 트래픽을 라우팅하는 모든 라우팅 규칙을 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="372c8-125">Block any routing rules that route traffic from the router to anywhere but the Mediation Server.</span></span>

<span data-ttu-id="372c8-126">VPN 서버를 사용하는 경우 다음 지침을 따르는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="372c8-126">If you use a VPN server, we recommend that you follow these guidelines:</span></span>

  - <span data-ttu-id="372c8-127">VPN 서버와 중재 서버 간에 VLAN을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="372c8-127">Set up a VLAN between the VPN server and the Mediation Server.</span></span>

  - <span data-ttu-id="372c8-128">VPN 서버에서 VLAN으로 브로드캐스트나 멀티캐스트 패킷이 전송되는 것을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="372c8-128">Do not allow broadcast or multicast packets to be transmitted from the VPN server to the VLAN.</span></span>

  - <span data-ttu-id="372c8-129">VPN 서버 트래픽을 사용 하지 않고 중재 서버로 라우팅하는 모든 라우팅 규칙을 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="372c8-129">Block any routing rule that routes VPN server traffic to anywhere but the Mediation Server.</span></span>

  - <span data-ttu-id="372c8-130">GRE(Generic Routing Encapsulation)를 사용하여 VPN의 데이터를 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="372c8-130">Encrypt data on the VPN by using generic routing encapsulation (GRE).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

