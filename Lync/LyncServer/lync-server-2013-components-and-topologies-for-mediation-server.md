---
title: 'Lync Server 2013: 중재 서버에 대 한 구성 요소 및 토폴로지'
description: 'Lync Server 2013: 중재 서버에 대 한 구성 요소 및 토폴로지'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for Mediation Server
ms:assetid: 71397168-36c3-4d21-b8ef-db6a751634ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398537(v=OCS.15)
ms:contentKeyID: 48184487
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: befd244508db9c98d565a76301e150da98708522
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576854"
---
# <a name="components-and-topologies-for-mediation-server-in-lync-server-2013"></a><span data-ttu-id="e6358-103">Lync Server 2013의 중재 서버에 대 한 구성 요소 및 토폴로지</span><span class="sxs-lookup"><span data-stu-id="e6358-103">Components and topologies for Mediation Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e6358-104">_**마지막으로 수정 된 항목:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="e6358-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="e6358-105">이 항목에서는 중재 서버가 종속 된 구성 요소 및 중재 서버를 배포할 수 있는 토폴로지에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6358-105">This topic describes the components on which the Mediation Server is dependent and the topologies in which the Mediation Server can be deployed</span></span>

<div>

## <a name="dependencies"></a><span data-ttu-id="e6358-106">의존</span><span class="sxs-lookup"><span data-stu-id="e6358-106">Dependencies</span></span>

<span data-ttu-id="e6358-107">중재 서버에는 다음과 같은 종속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6358-107">The Mediation Server has the following dependencies:</span></span>

  - <span data-ttu-id="e6358-108">**등록자.**</span><span class="sxs-lookup"><span data-stu-id="e6358-108">**Registrar.**</span></span> <span data-ttu-id="e6358-109">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="e6358-109">Required.</span></span> <span data-ttu-id="e6358-110">등록자는 Lync Server 2013 네트워크와의 중재 서버 상호 작용에서 신호를 보내는 다음 홉입니다.</span><span class="sxs-lookup"><span data-stu-id="e6358-110">The Registrar is the next hop for signaling in the Mediation Server interactions with the Lync Server 2013 network.</span></span> <span data-ttu-id="e6358-111">중재 서버는 배치 된과 함께 프런트 엔드 서버에는 중재 서버로만 구성 된 독립 실행형 풀에 설치 되어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6358-111">Note that Mediation Server can be collocated on a Front End Server along with the Registrar, in addition to being installed in a stand-alone pool consisting only of Mediation Servers.</span></span> <span data-ttu-id="e6358-112">등록자는 Sba (survivable 분기 기기에 중재 서버 및 PSTN 게이트웨이를 사용 하 여 배치 된 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6358-112">The Registrar is collocated with a Mediation Server and PSTN gateway on a Survivable Branch Appliance.</span></span>

  - <span data-ttu-id="e6358-113">**모니터링 서버.**</span><span class="sxs-lookup"><span data-stu-id="e6358-113">**Monitoring Server.**</span></span> <span data-ttu-id="e6358-114">선택 항목이지만 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e6358-114">Optional but highly recommended.</span></span> <span data-ttu-id="e6358-115">모니터링 서버를 사용 하면 중재 서버가 해당 미디어 세션과 관련 된 품질 메트릭을 기록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6358-115">The Monitoring Server allows the Mediation Server to record quality metrics associated with its media sessions.</span></span>

  - <span data-ttu-id="e6358-116">**에지 서버.**</span><span class="sxs-lookup"><span data-stu-id="e6358-116">**Edge Server.**</span></span> <span data-ttu-id="e6358-117">외부 사용자 지원에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e6358-117">Required for external user support.</span></span> <span data-ttu-id="e6358-118">에 지 서버를 사용 하면 NAT 또는 방화벽 뒤에 있는 사용자와 중재 서버가 상호 작용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6358-118">The Edge Server allows the Mediation Server to interact with users who are located behind a NAT or firewall.</span></span>

</div>

<div>

## <a name="topologies"></a><span data-ttu-id="e6358-119">기술</span><span class="sxs-lookup"><span data-stu-id="e6358-119">Topologies</span></span>

<span data-ttu-id="e6358-120">Lync Server 2013, 중재 서버는 기본적으로 Standard Edition Server, 프런트 엔드 풀 또는 Sba (survivable 분기 기기의 등록자 인스턴스를 사용 하 여 배치 된 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6358-120">The Lync Server 2013, Mediation Server is by default collocated with an instance of the Registrar on a Standard Edition server, a Front End pool, or Survivable Branch Appliance.</span></span> <span data-ttu-id="e6358-121">프런트 엔드 풀의 모든 중재 서버는 동일 하 게 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6358-121">All Mediation Servers in a Front End pool must be configured identically.</span></span>

<span data-ttu-id="e6358-122">성능에 문제가 있는 경우 전용 독립 실행형 풀에 하나 이상의 중재 서버를 배포 하는 것이 좋을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6358-122">Where performance is an issue, it may be preferable to deploy one or more Mediation Servers in a dedicated stand-alone pool.</span></span> <span data-ttu-id="e6358-123">또는 SIP 트렁크를 배포 하는 경우 독립 실행형 중재 서버 풀을 배포 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e6358-123">Or, if you are deploying SIP trunking, we recommend that you deploy a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="e6358-124">미디어 바이패스 및 DNS 부하 분산을 지원하는 적격한 PSTN 게이트웨이에 직접 SIP 연결을 배포한 경우 독립 실행형 중재 서버 풀이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e6358-124">If you deploy Direct SIP connections to a qualified PSTN gateway that supports media bypass and DNS load balancing, a stand-alone Mediation Server pool is not necessary.</span></span> <span data-ttu-id="e6358-125">정규 게이트웨이는 중재 서버 풀에 대 한 DNS 부하 분산을 가능 하 게 하 고 풀의 중재 서버에서 트래픽을 수신할 수 있으므로 독립 실행형 중재 서버 풀은 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e6358-125">A stand-alone Mediation Server pool is not necessary because qualified gateways are capable of DNS load balancing to a pool of Mediation Servers and they can receive traffic from any Mediation Server in a pool.</span></span>

<span data-ttu-id="e6358-126">또한 다음 조건 중 하나에 해당 하는 경우 IP-PBXs를 배포 하거나 인터넷 전화 통신 서버 공급자의 SBC (세션 경계 컨트롤러)에 연결 하는 경우에도 프런트 엔드 풀에 중재 서버를 함께 배치할 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e6358-126">We also recommend that you collocate the Mediation Server on a Front End pool when you have deployed IP-PBXs or connect to an Internet Telephony Server Provider’s Session Border Controller (SBC), as long as any of the following conditions are met:</span></span>

  - <span data-ttu-id="e6358-127">IP-PBX 또는 SBC가 풀의 중재 서버에서 트래픽을 수신하도록 구성되었고 풀의 모든 중재 서버에 트래픽을 단일 방식으로 라우팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6358-127">The IP-PBX or SBC is configured to receive traffic from any Mediation Server in the pool and can route traffic uniformly to all Mediation Servers in the pool.</span></span>

  - <span data-ttu-id="e6358-128">IP-PBX는 미디어 바이패스를 지원 하지 않지만 중재 서버를 호스트 하는 프런트 엔드 풀은 미디어 바이패스가 적용 되지 않는 통화에 대 한 음성 트랜스 변환을 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6358-128">The IP-PBX does not support media bypass, but the Front End pool that is hosting the Mediation Server can handle voice transcoding for calls to which media bypass does not apply.</span></span>

<span data-ttu-id="e6358-129">Microsoft Lync Server 2013, 계획 도구를 사용 하 여 중재 서버를 함께 배치할 프런트 엔드 풀에서 부하를 처리할 수 있는지 여부를 평가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6358-129">You can use the Microsoft Lync Server 2013, Planning Tool to evaluate whether the Front End pool where you want to collocate the Mediation Server can handle the load.</span></span> <span data-ttu-id="e6358-130">사용자 환경에서 이러한 요구 사항을 충족할 수 없는 경우 독립 실행형 중재 서버 풀을 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6358-130">If your environment cannot meet these requirements, then you must deploy a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="e6358-131">배포할 토폴로지에 대 한 자세한 내용은 [Lync server 2013의 중재 서버에 대 한 배포 지침](lync-server-2013-deployment-guidelines-for-mediation-server.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e6358-131">For details about which topology to deploy, see [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).</span></span>

<span data-ttu-id="e6358-132">다음 그림에서는 WAN 링크로 연결된 두 사이트로 구성된 단순한 토폴로지를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e6358-132">The following figure shows a simple topology consisting of two sites connected by a WAN link.</span></span> <span data-ttu-id="e6358-133">중재 서버는 배치 된이 사이트 1의 프런트 엔드 풀에 있는 등록자와 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6358-133">Mediation Server is collocated with the Registrar on a Front End pool at Site 1.</span></span> <span data-ttu-id="e6358-134">사이트 1의 중재 서버는 사이트 1의 PSTN 게이트웨이와 사이트 2의 게이트웨이를 모두 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6358-134">The Mediation Servers at Site 1 controls both the PSTN gateway at Site 1 and the gateway at Site 2.</span></span> <span data-ttu-id="e6358-135">이 토폴로지에서는 사이트 및 지역 정보를 사용하도록 미디어 바이패스가 전역적으로 설정되어 있으며 각 PSTN 게이트웨이의 트렁크(GW1 및 GW2)에 바이패스가 사용되도록 설정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e6358-135">In this topology, media bypass is enabled globally to use site and region information, and the trunks to each PSTN gateway (GW1 and GW2) have bypass enabled.</span></span>

<span data-ttu-id="e6358-136">**사이트 1의 중재 서버 및 사이트 2의 PSTN 게이트웨이를 사용하여 WAN 링크로 연결된 사이트의 예**</span><span class="sxs-lookup"><span data-stu-id="e6358-136">**Example of sites connected by a WAN link with a Mediation Server at Site 1 and a PSTN gateway at Site 2**</span></span>

<span data-ttu-id="e6358-137">![중재 서버 WAN 게이트웨이를 사용 하는 음성 토폴로지](images/Gg398537.67872e61-1444-447b-918c-abe89abc3004(OCS.15).jpg "중재 서버 WAN 게이트웨이를 사용 하는 음성 토폴로지")</span><span class="sxs-lookup"><span data-stu-id="e6358-137">![Voice Topology with Mediation Server WAN Gateway](images/Gg398537.67872e61-1444-447b-918c-abe89abc3004(OCS.15).jpg "Voice Topology with Mediation Server WAN Gateway")</span></span>

<span data-ttu-id="e6358-138">다음 그림에서는 중재 서버가 사이트 1의 프런트 엔드 풀에 있는 등록자와 배치 된 하 고 사이트 1의 IP-PBX에 직접 SIP 연결 되는 간단한 토폴로지를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e6358-138">The next figure shows a simple topology where the Mediation Server is collocated with the Registrar on Front End pool at Site 1 and has a Direct SIP connection to the IP-PBX at Site 1.</span></span> <span data-ttu-id="e6358-139">이 그림에서 중재 서버는 사이트 2의 PSTN 게이트웨이도 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6358-139">In this figure, the Mediation Server also controls a PSTN gateway at Site 2.</span></span> <span data-ttu-id="e6358-140">사이트 1과 2에 모두 Lync 사용자가 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6358-140">Assume that Lync users exist at both Sites 1 and 2.</span></span> <span data-ttu-id="e6358-141">또한 ip-pbx가 IP-PBX에서 제어 하는 미디어 끝점에 전송 되기 전에 Lync 끝점에서 시작 되는 모든 미디어에서 통과 해야 하는 관련 미디어 프로세서가 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6358-141">Also assume that the IP-PBX has an associated media processor that must be traversed by all media originating from Lync endpoints before being sent to media endpoints controlled by the IP-PBX.</span></span> <span data-ttu-id="e6358-142">이 토폴로지에는 사이트 및 지역 정보를 사용하도록 미디어 바이패스가 전역적으로 설정되어 있으며 PBX 및 PSTN 게이트웨이의 트렁크에 바이패스가 사용되도록 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6358-142">In this topology, media bypass is enabled globally to use site and region information, and the trunks to the PBX and PSTN gateway have media bypass enabled.</span></span>

<span data-ttu-id="e6358-143">**사이트 1의 중재 서버 및 사이트 2의 PBX를 사용하여 WAN 링크로 연결된 사이트의 예**</span><span class="sxs-lookup"><span data-stu-id="e6358-143">**Example of sites connected by a WAN link with a Mediation Server at Site 1 and a PBX at Site 2**</span></span>

<span data-ttu-id="e6358-144">![음성 토폴로지 중재 서버 WAN PBX](images/Gg398537.df6c8a5b-8431-4187-907d-ff5ca26eeeec(OCS.15).jpg "음성 토폴로지 중재 서버 WAN PBX")</span><span class="sxs-lookup"><span data-stu-id="e6358-144">![Voice Topology Mediation Server WAN PBX](images/Gg398537.df6c8a5b-8431-4187-907d-ff5ca26eeeec(OCS.15).jpg "Voice Topology Mediation Server WAN PBX")</span></span>

<span data-ttu-id="e6358-145">PBX 토폴로지를 계획 하는 방법에 대 한 자세한 내용은 [lync server 2013의 중재 서버에 대 한 배포 지침](lync-server-2013-deployment-guidelines-for-mediation-server.md) 및 [lync Server 2013의 Direct SIP 배포 옵션](lync-server-2013-direct-sip-deployment-options.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e6358-145">For details about planning for PBX topologies, see [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) and [Direct SIP deployment options in Lync Server 2013](lync-server-2013-direct-sip-deployment-options.md).</span></span>

<span data-ttu-id="e6358-146">이 항목의 마지막 그림에서는 중재 서버가 인터넷 전화 통신 서비스 공급자의 SBC에 연결 되는 토폴로지를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e6358-146">The last figure in this topic shows a topology where the Mediation Server is connected to the SBC of an Internet Telephony Service Provider.</span></span> <span data-ttu-id="e6358-147">SIP 트렁크 토폴로지에 대 한 자세한 내용은 [sip 트렁크 In Lync Server 2013](lync-server-2013-sip-trunking.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e6358-147">For details about SIP trunk topologies, see [SIP trunking in Lync Server 2013](lync-server-2013-sip-trunking.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

