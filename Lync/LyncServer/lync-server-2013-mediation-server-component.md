---
title: 'Lync Server 2013: 중재 서버 구성 요소'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mediation Server component
ms:assetid: 5b19edef-4a54-43c9-aa12-5643b8108355
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398399(v=OCS.15)
ms:contentKeyID: 48184239
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b78a7903cb46ada3231d1d604ced2f8536699776
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149718"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="mediation-server-component-in-lync-server-2013"></a><span data-ttu-id="7925a-102">Lync Server 2013의 중재 서버 구성 요소</span><span class="sxs-lookup"><span data-stu-id="7925a-102">Mediation Server component in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7925a-103">_**마지막으로 수정 된 항목:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="7925a-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="7925a-104">Enterprise Voice 작업을 배포 하는 경우에는 Lync Server 2013, 중재 서버를 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7925a-104">You must deploy Lync Server 2013, Mediation Server if you deploy the Enterprise Voice workload.</span></span> <span data-ttu-id="7925a-105">이 섹션에서는 기본 기능, 종속성, 기본 토폴로지 및 계획 지침을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7925a-105">This section describes basic functionality, dependencies, basic topologies, and planning guidelines.</span></span>

<span data-ttu-id="7925a-106">중재 서버는 신호를 변환 하 고, 일부 구성의 경우 내부 Lync Server 2013, Enterprise Voice infrastructure 및 공중 전화망 (PSTN) 게이트웨이 또는 SIP (Session 착수 프로토콜) 트렁크 간의 미디어를 번역 합니다.</span><span class="sxs-lookup"><span data-stu-id="7925a-106">The Mediation Server translates signaling and, in some configurations, media between your internal Lync Server 2013, Enterprise Voice infrastructure and a public switched telephone network (PSTN) gateway or a Session Initiation Protocol (SIP) trunk.</span></span> <span data-ttu-id="7925a-107">Lync Server 2013 쪽에서는 중재 서버가 단일 상호 TLS (MTLS) 전송 주소에서 수신 대기 합니다.</span><span class="sxs-lookup"><span data-stu-id="7925a-107">On the Lync Server 2013 side, Mediation Server listens on a single mutual TLS (MTLS) transport address.</span></span> <span data-ttu-id="7925a-108">게이트웨이 쪽에서 중재 서버는 토폴로지 문서에 정의된 트렁크와 연결된 모든 연관된 수신 대기 포트에서 수신 대기합니다.</span><span class="sxs-lookup"><span data-stu-id="7925a-108">On the gateway side, Mediation Server listens on all associated listening ports associated with trunks defined in the Topology document.</span></span> <span data-ttu-id="7925a-109">해당하는 모든 게이트웨이는 TLS를 지원해야 하지만, TCP도 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7925a-109">All qualified gateways must support TLS, but can enable TCP as well.</span></span> <span data-ttu-id="7925a-110">TLS를 지원하지 않는 게이트웨이의 경우 TCP가 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="7925a-110">TCP is supported for gateways that do not support TLS.</span></span>

<span data-ttu-id="7925a-111">환경에 기존 PBX (공용 분기 교환)도 있으면 중재 서버가 Enterprise Voice 사용자와 PBX 간의 통화를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="7925a-111">If you also have an existing Public Branch Exchange (PBX) in your environment, Mediation Server handles calls between Enterprise Voice users and the PBX.</span></span> <span data-ttu-id="7925a-112">PBX가 ip-pbx 인 경우 PBX와 중재 서버 간에 직접 SIP 연결을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7925a-112">If your PBX is an IP-PBX, you can create a direct SIP connection between the PBX and Mediation Server.</span></span> <span data-ttu-id="7925a-113">PBX가 TDM (Time 디비전 Multiplex) PBX 인 경우 중재 서버와 PBX 간에 PSTN 게이트웨이를 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7925a-113">If your PBX is a Time Division Multiplex (TDM) PBX, you must also deploy a PSTN gateway between Mediation Server and the PBX.</span></span>

<span data-ttu-id="7925a-114">중재 서버는 기본적으로 프런트 엔드 서버와 배치 된 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7925a-114">The Mediation Server is collocated with the Front End Server by default.</span></span> <span data-ttu-id="7925a-115">또한 성능상의 이유로 독립 실행형 풀에 중재 서버를 배포 하거나, 독립 실행형 풀을 사용 하는 것이 트렁크 SIP를 배포 하는 경우에도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7925a-115">The Mediation Server can also be deployed in a stand-alone pool for performance reasons, or if you deploy SIP trunking, in which case the stand-alone pool is strongly recommended.</span></span>

<span data-ttu-id="7925a-116">미디어 바이패스 및 DNS 부하 분산을 지원하는 적격한 PSTN 게이트웨이에 직접 SIP 연결을 배포한 경우 독립 실행형 중재 서버 풀이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7925a-116">If you deploy Direct SIP connections to a qualified PSTN gateway that supports media bypass and DNS load balancing, a stand-alone Mediation Server pool is not necessary.</span></span> <span data-ttu-id="7925a-117">정규 게이트웨이는 중재 서버 풀에 대 한 DNS 부하 분산을 가능 하 게 하 고 풀의 중재 서버에서 트래픽을 수신할 수 있으므로 독립 실행형 중재 서버 풀은 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7925a-117">A stand-alone Mediation Server pool is not necessary because qualified gateways are capable of DNS load balancing to a pool of Mediation Servers and they can receive traffic from any Mediation Server in a pool.</span></span>

<span data-ttu-id="7925a-118">또한 다음 조건 중 하나라도 충족 되 면 IP-Pbx를 배포 하거나 인터넷 전화 통신 서버 공급자의 세션 경계 컨트롤러 (SBC)에 연결 하는 경우에도 프런트 엔드 풀에 중재 서버를 함께 배치할 것을 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="7925a-118">We also recommend that you collocate the Mediation Server on a Front End pool when you have deployed IP-PBXs or connect to an Internet Telephony Server Provider’s Session Border Controller (SBC), as long as any of the following conditions are met:</span></span>

  - <span data-ttu-id="7925a-119">IP-PBX 또는 SBC가 풀의 중재 서버에서 트래픽을 수신하도록 구성되었고 풀의 모든 중재 서버에 트래픽을 단일 방식으로 라우팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7925a-119">The IP-PBX or SBC is configured to receive traffic from any Mediation Server in the pool and can route traffic uniformly to all Mediation Servers in the pool.</span></span>

  - <span data-ttu-id="7925a-120">IP-PBX는 미디어 바이패스를 지원 하지 않지만 중재 서버를 호스트 하는 프런트 엔드 풀은 미디어 바이패스가 적용 되지 않는 통화에 대 한 음성 트랜스 변환을 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7925a-120">The IP-PBX does not support media bypass, but the Front End pool that is hosting the Mediation Server can handle voice transcoding for calls to which media bypass does not apply.</span></span>

<span data-ttu-id="7925a-121">Microsoft Lync Server 2013, 계획 도구를 사용 하 여 중재 서버를 함께 배치할 프런트 엔드 풀에서 부하를 처리할 수 있는지 여부를 평가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7925a-121">You can use the Microsoft Lync Server 2013, Planning Tool to evaluate whether the Front End pool where you want to collocate the Mediation Server can handle the load.</span></span> <span data-ttu-id="7925a-122">사용자 환경에서 이러한 요구 사항을 충족할 수 없는 경우 독립 실행형 중재 서버 풀을 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7925a-122">If your environment cannot meet these requirements, then you must deploy a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="7925a-123">중재 서버의 주요 기능은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7925a-123">The main functions of the Mediation Server are as follows:</span></span>

  - <span data-ttu-id="7925a-124">Lync Server 쪽에서 SRTP 암호화 및 암호 해독</span><span class="sxs-lookup"><span data-stu-id="7925a-124">Encrypting and decrypting SRTP on the Lync Server side</span></span>

  - <span data-ttu-id="7925a-125">TCP(TLS를 지원하지 않는 게이트웨이의 경우)를 통한 SIP를 Mutual TLS를 통한 SIP로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="7925a-125">Translating SIP over TCP (for gateways that do not support TLS) to SIP over mutual TLS</span></span>

  - <span data-ttu-id="7925a-126">Lync Server와 중재 서버의 게이트웨이 피어 사이에 미디어 스트림 변환</span><span class="sxs-lookup"><span data-stu-id="7925a-126">Translating media streams between Lync Server and the gateway peer of the Mediation Server</span></span>

  - <span data-ttu-id="7925a-127">미디어가 NAT 및 방화벽을 통과할 수 있도록 네트워크 외부에 있는 클라이언트를 내부 ICE 구성 요소에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="7925a-127">Connecting clients that are outside the network to internal ICE components, which enable media traversal of NAT and firewalls</span></span>

  - <span data-ttu-id="7925a-128">기업 음성 클라이언트의 원격 작업자 로부터의 전화와 같이 게이트웨이가 지원 하지 않는 통화 흐름에 대 한 중개 역할 수행</span><span class="sxs-lookup"><span data-stu-id="7925a-128">Acting as an intermediary for call flows that a gateway does not support, such as calls from remote workers on an Enterprise Voice client</span></span>

  - <span data-ttu-id="7925a-129">SIP 트렁크가 포함된 배포에서 SIP 트렁크 서비스 공급자와 함께 PSTN 지원을 제공하므로 PSTN 게이트웨이를 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7925a-129">In deployments that include SIP trunking, working with the SIP trunking service provider to provide PSTN support, which eliminates the need for a PSTN gateway</span></span>

<span data-ttu-id="7925a-130">다음 그림에서는 기본 PSTN 게이트웨이와 엔터프라이즈 음성 인프라와 통신할 때 중재 서버에서 사용 하는 신호 및 미디어 프로토콜을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7925a-130">The following figure shows the signaling and media protocols that are used by the Mediation Server when communicating with a basic PSTN gateway and the Enterprise Voice infrastructure.</span></span>

<span data-ttu-id="7925a-131">**중재 서버에서 사용되는 신호 및 미디어 프로토콜**</span><span class="sxs-lookup"><span data-stu-id="7925a-131">**Signaling and media protocols used by the Mediation Server**</span></span>

<span data-ttu-id="7925a-132">![중재 서버 프로토콜 다이어그램](images/Gg398399.c3d39ba0-e323-4a58-8f07-4e80d3278af2(OCS.15).jpg "중재 서버 프로토콜 다이어그램")</span><span class="sxs-lookup"><span data-stu-id="7925a-132">![Mediation Server Protocols diagram](images/Gg398399.c3d39ba0-e323-4a58-8f07-4e80d3278af2(OCS.15).jpg "Mediation Server Protocols diagram")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7925a-133">PSTN 게이트웨이와 중재 서버 간의 네트워크에서 SRTP 또는 SRTCP 대신 TCP 또는 RTP/RTCP를 사용 하는 경우에는 네트워크의 보안 및 개인 정보를 보호 하는 데 도움이 되는 조치를 취하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7925a-133">If you are using TCP or RTP/RTCP (instead of SRTP or SRTCP) on the network between the PSTN gateway and the Mediation Server, we recommend that you take measures to help ensure the security and privacy of the network.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7925a-134">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="7925a-134">In This Section</span></span>

  - [<span data-ttu-id="7925a-135">Lync Server 2013의 M:N 트렁크</span><span class="sxs-lookup"><span data-stu-id="7925a-135">M:N trunk in Lync Server 2013</span></span>](lync-server-2013-m-n-trunk.md)

  - [<span data-ttu-id="7925a-136">Lync Server 2013의 통화 허용 제어 및 중재 서버</span><span class="sxs-lookup"><span data-stu-id="7925a-136">Call admission control and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-call-admission-control-and-mediation-server.md)

  - [<span data-ttu-id="7925a-137">Lync Server 2013의 향상 된 9-1-1 (E9-1-1) 및 중재 서버</span><span class="sxs-lookup"><span data-stu-id="7925a-137">Enhanced 9-1-1 (E9-1-1) and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md)

  - [<span data-ttu-id="7925a-138">Lync Server 2013의 미디어 바이패스 및 중재 서버</span><span class="sxs-lookup"><span data-stu-id="7925a-138">Media bypass and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-mediation-server.md)

  - [<span data-ttu-id="7925a-139">Lync Server 2013의 중재 서버에 대 한 구성 요소 및 토폴로지</span><span class="sxs-lookup"><span data-stu-id="7925a-139">Components and topologies for Mediation Server in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-mediation-server.md)

  - [<span data-ttu-id="7925a-140">Lync Server 2013의 중재 서버 배포 지침</span><span class="sxs-lookup"><span data-stu-id="7925a-140">Deployment guidelines for Mediation Server in Lync Server 2013</span></span>](lync-server-2013-deployment-guidelines-for-mediation-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

