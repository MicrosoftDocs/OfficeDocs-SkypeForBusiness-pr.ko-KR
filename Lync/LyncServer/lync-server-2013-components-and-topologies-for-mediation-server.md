---
title: 'Lync Server 2013: 중재 서버의 구성 요소 및 토폴로지'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components and topologies for Mediation Server
ms:assetid: 71397168-36c3-4d21-b8ef-db6a751634ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398537(v=OCS.15)
ms:contentKeyID: 48184487
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f9c353dc65f5e943e082df9321a934ea8f14be1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982860"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-mediation-server-in-lync-server-2013"></a><span data-ttu-id="6562e-102">Lync Server 2013의 중재 서버의 구성 요소 및 토폴로지</span><span class="sxs-lookup"><span data-stu-id="6562e-102">Components and topologies for Mediation Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6562e-103">_**마지막으로 수정한 주제:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="6562e-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="6562e-104">이 항목에서는 중재 서버가 종속 되는 구성 요소와 중재 서버가 배포 될 수 있는 토폴로지에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6562e-104">This topic describes the components on which the Mediation Server is dependent and the topologies in which the Mediation Server can be deployed</span></span>

<div>

## <a name="dependencies"></a><span data-ttu-id="6562e-105">항목</span><span class="sxs-lookup"><span data-stu-id="6562e-105">Dependencies</span></span>

<span data-ttu-id="6562e-106">중재 서버에는 다음과 같은 종속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6562e-106">The Mediation Server has the following dependencies:</span></span>

  - <span data-ttu-id="6562e-107">**레지스터.**</span><span class="sxs-lookup"><span data-stu-id="6562e-107">**Registrar.**</span></span> <span data-ttu-id="6562e-108">필수.</span><span class="sxs-lookup"><span data-stu-id="6562e-108">Required.</span></span> <span data-ttu-id="6562e-109">레지스트라는 Lync Server 2013 네트워크와의 중재 서버 조작에서 신호를 보내는 다음 홉입니다.</span><span class="sxs-lookup"><span data-stu-id="6562e-109">The Registrar is the next hop for signaling in the Mediation Server interactions with the Lync Server 2013 network.</span></span> <span data-ttu-id="6562e-110">중재 서버는 collocated와 함께 프런트 엔드 서버에서 사용 될 수 있으며, 중재 서버로만 구성 된 독립 실행형 풀에도 설치 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6562e-110">Note that Mediation Server can be collocated on a Front End Server along with the Registrar, in addition to being installed in a stand-alone pool consisting only of Mediation Servers.</span></span> <span data-ttu-id="6562e-111">레지스트라는 중재 서버와 Survivable Branch 기기에 대 한 PSTN 게이트웨이를 collocated 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6562e-111">The Registrar is collocated with a Mediation Server and PSTN gateway on a Survivable Branch Appliance.</span></span>

  - <span data-ttu-id="6562e-112">**모니터링 서버.**</span><span class="sxs-lookup"><span data-stu-id="6562e-112">**Monitoring Server.**</span></span> <span data-ttu-id="6562e-113">선택 사항 이지만 매우 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6562e-113">Optional but highly recommended.</span></span> <span data-ttu-id="6562e-114">모니터링 서버는 조정 서버에서 해당 미디어 세션과 연결 된 품질 메트릭을 녹화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6562e-114">The Monitoring Server allows the Mediation Server to record quality metrics associated with its media sessions.</span></span>

  - <span data-ttu-id="6562e-115">**Edge 서버.**</span><span class="sxs-lookup"><span data-stu-id="6562e-115">**Edge Server.**</span></span> <span data-ttu-id="6562e-116">외부 사용자 지원에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="6562e-116">Required for external user support.</span></span> <span data-ttu-id="6562e-117">Edge 서버는 조정 서버가 NAT 또는 방화벽 뒤에 있는 사용자와 상호 작용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="6562e-117">The Edge Server allows the Mediation Server to interact with users who are located behind a NAT or firewall.</span></span>

</div>

<div>

## <a name="topologies"></a><span data-ttu-id="6562e-118">토폴로지</span><span class="sxs-lookup"><span data-stu-id="6562e-118">Topologies</span></span>

<span data-ttu-id="6562e-119">Lync Server 2013, 중재 서버는 기본적으로 Standard Edition Server, 프론트 엔드 풀 또는 Survivable Branch 기기의 collocated 인스턴스를 사용 하 여 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6562e-119">The Lync Server 2013, Mediation Server is by default collocated with an instance of the Registrar on a Standard Edition server, a Front End pool, or Survivable Branch Appliance.</span></span> <span data-ttu-id="6562e-120">프런트 엔드 풀의 모든 중재 서버는 동일 하 게 구성 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6562e-120">All Mediation Servers in a Front End pool must be configured identically.</span></span>

<span data-ttu-id="6562e-121">성능이 문제가 되는 경우 전용 독립 풀에 하나 이상의 중재 서버를 배포 하는 것이 더 좋을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6562e-121">Where performance is an issue, it may be preferable to deploy one or more Mediation Servers in a dedicated stand-alone pool.</span></span> <span data-ttu-id="6562e-122">또는 SIP 트렁크를 배포 하는 경우에는 독립 실행형 중재 서버 풀을 배포 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6562e-122">Or, if you are deploying SIP trunking, we recommend that you deploy a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="6562e-123">미디어 우회 및 DNS 부하 분산을 지 원하는 정식 PSTN 게이트웨이에 직접 SIP 연결을 배포 하는 경우 독립 실행형 중재 서버 풀은 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6562e-123">If you deploy Direct SIP connections to a qualified PSTN gateway that supports media bypass and DNS load balancing, a stand-alone Mediation Server pool is not necessary.</span></span> <span data-ttu-id="6562e-124">자격 있는 게이트웨이는 중재 서버 풀에 DNS 부하 분산을 사용할 수 있고 풀의 모든 중재 서버에서 트래픽을 수신할 수 있으므로 독립 실행형 중재 서버 풀은 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6562e-124">A stand-alone Mediation Server pool is not necessary because qualified gateways are capable of DNS load balancing to a pool of Mediation Servers and they can receive traffic from any Mediation Server in a pool.</span></span>

<span data-ttu-id="6562e-125">또한 다음 조건 중 하나가 충족 되는 경우 IP Pbx를 배포 하거나 인터넷 전화 통신 서버 공급자의 SBC (세션 경계 컨트롤러)에 연결 된 경우에는 프런트 엔드 풀에 중재 서버를 collocate 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6562e-125">We also recommend that you collocate the Mediation Server on a Front End pool when you have deployed IP-PBXs or connect to an Internet Telephony Server Provider’s Session Border Controller (SBC), as long as any of the following conditions are met:</span></span>

  - <span data-ttu-id="6562e-126">IP-PBX 또는 SBC는 풀의 중재 서버에서 트래픽을 수신 하도록 구성 되며 풀의 모든 중재 서버에 일관 된 트래픽을 라우팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6562e-126">The IP-PBX or SBC is configured to receive traffic from any Mediation Server in the pool and can route traffic uniformly to all Mediation Servers in the pool.</span></span>

  - <span data-ttu-id="6562e-127">IP-PBX는 미디어 바이패스를 지원 하지 않지만 중재 서버를 호스트 하는 프런트 엔드 풀은 미디어 bypass이 적용 되지 않는 호출에 대 한 음성 코드 변환을 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6562e-127">The IP-PBX does not support media bypass, but the Front End pool that is hosting the Mediation Server can handle voice transcoding for calls to which media bypass does not apply.</span></span>

<span data-ttu-id="6562e-128">Microsoft Lync Server 2013, 계획 도구를 사용 하 여 중재 서버를 collocate 프런트 엔드 풀에서 부하를 처리할 수 있는지 여부를 평가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6562e-128">You can use the Microsoft Lync Server 2013, Planning Tool to evaluate whether the Front End pool where you want to collocate the Mediation Server can handle the load.</span></span> <span data-ttu-id="6562e-129">환경이 이러한 요구 사항을 충족 하지 못하는 경우에는 독립 실행형 중재 서버 풀을 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6562e-129">If your environment cannot meet these requirements, then you must deploy a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="6562e-130">배포할 토폴로지에 대 한 자세한 내용은 [Lync server 2013의 중재 서버 배포 지침](lync-server-2013-deployment-guidelines-for-mediation-server.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6562e-130">For details about which topology to deploy, see [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).</span></span>

<span data-ttu-id="6562e-131">다음 그림에는 WAN 링크로 연결 된 두 개의 사이트로 구성 된 간단한 토폴로지가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6562e-131">The following figure shows a simple topology consisting of two sites connected by a WAN link.</span></span> <span data-ttu-id="6562e-132">중재 서버는 사이트 1의 프런트 엔드 풀에 있는 레지스트라를 사용 하 여 collocated 합니다.</span><span class="sxs-lookup"><span data-stu-id="6562e-132">Mediation Server is collocated with the Registrar on a Front End pool at Site 1.</span></span> <span data-ttu-id="6562e-133">사이트 1의 중재 서버는 사이트 1의 PSTN 게이트웨이와 사이트 2의 게이트웨이를 모두 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="6562e-133">The Mediation Servers at Site 1 controls both the PSTN gateway at Site 1 and the gateway at Site 2.</span></span> <span data-ttu-id="6562e-134">이 토폴로지에서는 media bypass이 사이트 및 지역 정보를 사용 하도록 전역적으로 사용 하도록 설정 되어 있으며, 각 PSTN 게이트웨이 (GW1 및 GW2)에 대 한 trunks 사용 하지 않도록 설정 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6562e-134">In this topology, media bypass is enabled globally to use site and region information, and the trunks to each PSTN gateway (GW1 and GW2) have bypass enabled.</span></span>

<span data-ttu-id="6562e-135">**사이트 1의 중재 서버와 사이트 2의 PSTN 게이트웨이를 사용 하 여 WAN 링크로 연결 된 사이트의 예**</span><span class="sxs-lookup"><span data-stu-id="6562e-135">**Example of sites connected by a WAN link with a Mediation Server at Site 1 and a PSTN gateway at Site 2**</span></span>

<span data-ttu-id="6562e-136">(images/Gg398537.67872e61-1444-447b-918c-abe89abc3004(OCS.15).jpg "중재 서버 Wan 게이트웨이를 사용 하는") ![중재 서버 Wan 게이트웨이 음성 토폴로지가 있는 음성 토폴로지]</span><span class="sxs-lookup"><span data-stu-id="6562e-136">![Voice Topology with Mediation Server WAN Gateway](images/Gg398537.67872e61-1444-447b-918c-abe89abc3004(OCS.15).jpg "Voice Topology with Mediation Server WAN Gateway")</span></span>

<span data-ttu-id="6562e-137">다음 그림은 중재 서버가 사이트 1의 프런트 엔드 풀에 있는 레지스트라로 collocated 하 고 사이트 1의 ip-pbx (IP-PBX)에 대 한 직접 SIP 연결을 사용 하는 간단한 토폴로지를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6562e-137">The next figure shows a simple topology where the Mediation Server is collocated with the Registrar on Front End pool at Site 1 and has a Direct SIP connection to the IP-PBX at Site 1.</span></span> <span data-ttu-id="6562e-138">이 그림에서 중재 서버는 사이트 2 에서도 PSTN 게이트웨이를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="6562e-138">In this figure, the Mediation Server also controls a PSTN gateway at Site 2.</span></span> <span data-ttu-id="6562e-139">Lync 사용자가 사이트 1 및 2에 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6562e-139">Assume that Lync users exist at both Sites 1 and 2.</span></span> <span data-ttu-id="6562e-140">또한 ip PBX에는 IP pbx가 제어 하는 미디어 끝점에 전송 하기 전에 Lync 끝점에서 생성 된 모든 미디어에서 통과 해야 하는 관련 미디어 프로세서가 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6562e-140">Also assume that the IP-PBX has an associated media processor that must be traversed by all media originating from Lync endpoints before being sent to media endpoints controlled by the IP-PBX.</span></span> <span data-ttu-id="6562e-141">이 토폴로지에서는 미디어 바이패스를 사이트 및 지역 정보를 사용 하도록 전체적으로 설정 하 고, PBX 및 PSTN 게이트웨이에 대 한 trunks는 미디어 바이패스를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6562e-141">In this topology, media bypass is enabled globally to use site and region information, and the trunks to the PBX and PSTN gateway have media bypass enabled.</span></span>

<span data-ttu-id="6562e-142">**사이트 1의 중재 서버와 사이트 2에 있는 PBX를 사용 하 여 WAN 링크로 연결 된 사이트의 예**</span><span class="sxs-lookup"><span data-stu-id="6562e-142">**Example of sites connected by a WAN link with a Mediation Server at Site 1 and a PBX at Site 2**</span></span>

<span data-ttu-id="6562e-143">![음성 토폴로지 중재 서버 WAN pbx](images/Gg398537.df6c8a5b-8431-4187-907d-ff5ca26eeeec(OCS.15).jpg "음성 토폴로지 중재 서버 wan pbx")</span><span class="sxs-lookup"><span data-stu-id="6562e-143">![Voice Topology Mediation Server WAN PBX](images/Gg398537.df6c8a5b-8431-4187-907d-ff5ca26eeeec(OCS.15).jpg "Voice Topology Mediation Server WAN PBX")</span></span>

<span data-ttu-id="6562e-144">PBX 토폴로지 계획에 대 한 자세한 내용은 lync server 2013의 중재 서버와 [Lync server 2013의 직접 SIP 배포 옵션](lync-server-2013-direct-sip-deployment-options.md) [에 대 한 배포 지침](lync-server-2013-deployment-guidelines-for-mediation-server.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6562e-144">For details about planning for PBX topologies, see [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) and [Direct SIP deployment options in Lync Server 2013](lync-server-2013-direct-sip-deployment-options.md).</span></span>

<span data-ttu-id="6562e-145">이 항목의 마지막 그림에서는 중재 서버가 인터넷 전화 통신 서비스 공급자의 SBC에 연결 된 토폴로지를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6562e-145">The last figure in this topic shows a topology where the Mediation Server is connected to the SBC of an Internet Telephony Service Provider.</span></span> <span data-ttu-id="6562e-146">SIP 트렁크 토폴로지에 대 한 자세한 내용은 [Lync Server 2013의 sip 트렁크](lync-server-2013-sip-trunking.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6562e-146">For details about SIP trunk topologies, see [SIP trunking in Lync Server 2013](lync-server-2013-sip-trunking.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

