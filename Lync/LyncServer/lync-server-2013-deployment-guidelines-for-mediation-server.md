---
title: 'Lync Server 2013: 중재 서버에 대 한 배포 지침'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment guidelines for Mediation Server
ms:assetid: 7cc22b87-18d9-45e6-8402-015abd20f2e5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398622(v=OCS.15)
ms:contentKeyID: 48184606
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: afcbfec56f4cfee3def2a0ef6deb82934534dbb2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213823"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-guidelines-for-mediation-server-in-lync-server-2013"></a><span data-ttu-id="46e4b-102">Lync Server 2013의 중재 서버 배포 지침</span><span class="sxs-lookup"><span data-stu-id="46e4b-102">Deployment guidelines for Mediation Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46e4b-103">_**마지막으로 수정 된 항목:** 2012-10-12_</span><span class="sxs-lookup"><span data-stu-id="46e4b-103">_**Topic Last Modified:** 2012-10-12_</span></span>

<span data-ttu-id="46e4b-104">이 항목에서는 중재 서버 배포에 대 한 계획 지침에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="46e4b-104">This topic describes planning guidelines for Mediation Server deployment.</span></span> <span data-ttu-id="46e4b-105">이러한 지침을 검토 한 후 계획 도구를 사용 하 여 배포를 결정 하는 최종 맞춤형 토폴로지의 모델로 사용할 수 있는 가능한 대체 토폴로지를 만들고 확인 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="46e4b-105">After reviewing these guidelines, we recommend that you use the Planning Tool to create and view possible alternative topologies, which can serve as models for what the final tailored topology that you decide to deploy would look like.</span></span>

<div>

## <a name="collocated-or-stand-alone-mediation-server"></a><span data-ttu-id="46e4b-106">배치 된 또는 독립 실행형 중재 서버</span><span class="sxs-lookup"><span data-stu-id="46e4b-106">Collocated or Stand-alone Mediation Server?</span></span>

<span data-ttu-id="46e4b-107">중재 서버는 기본적으로 중앙 사이트 프런트 엔드 풀의 Standard Edition Server 또는 프런트 엔드 서버에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="46e4b-107">Mediation Server is by default collocated on the Standard Edition server or Front End Server in a Front End pool at central sites.</span></span> <span data-ttu-id="46e4b-108">처리할 수 있는 PSTN (공중 전화망) 통화 수 및 풀에 필요한 컴퓨터 수는 다음에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="46e4b-108">The number of public switched telephone network (PSTN) calls that can be handled and the number of machines required in the pool will depend on the following:</span></span>

  - <span data-ttu-id="46e4b-109">중재 서버 풀에서 제어 하는 게이트웨이 피어 수</span><span class="sxs-lookup"><span data-stu-id="46e4b-109">The number of gateway peers that the Mediation Server pool controls</span></span>

  - <span data-ttu-id="46e4b-110">이러한 게이트웨이를 통한 고용량 트래픽 기간</span><span class="sxs-lookup"><span data-stu-id="46e4b-110">The high-volume traffic periods through those gateways</span></span>

  - <span data-ttu-id="46e4b-111">해당 미디어에서 중재 서버를 바이패스 하는 통화의 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="46e4b-111">The percentage of calls that are calls whose media bypass the Mediation Server</span></span>

<span data-ttu-id="46e4b-112">계획할 때는 PSTN 통화에 대 한 미디어 처리 요구 사항과 미디어 바이패스를 위해 구성 되지 않은 A/V 회의 및 지원 해야 하는 사용량이 많은 시간에 대 한 신호 상호 작용을 처리 하는 데 필요한 처리를 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46e4b-112">When planning, be sure to take into account the media processing requirements for PSTN calls and A/V conferences that are not configured for media bypass, as well as the processing needed to handle signaling interactions for the number of busy-hour calls that need to be supported.</span></span> <span data-ttu-id="46e4b-113">CPU가 충분 하지 않으면 중재 서버의 독립 실행형 풀을 배포 해야 합니다. 및 PSTN 게이트웨이, IP-Pbx 및 자회사는 하나의 풀에 있는 배치 된 중재 서버 및 하나 이상의 독립 실행형 풀에 독립 실행형 중재 서버에 의해 제어 되는 하위 집합으로 분할 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46e4b-113">If there is not enough CPU, then you must deploy a stand-alone pool of Mediation Servers; and PSTN gateways, IP-PBXs, and SBCs will need to be split into subsets that are controlled by the collocated Mediation Servers in one pool and the stand-alone Mediation Servers in one or more stand-alone pools.</span></span>

<span data-ttu-id="46e4b-114">다음을 포함 하 여 중재 서버 풀과 상호 작용 하기 위한 올바른 기능을 지원 하지 않는 PSTN 게이트웨이, IP-PBX 또는 sbc (Session Border Controller)를 배포한 경우에는이를 구성 하는 독립 실행형 풀에 연결 해야 합니다. 단일 중재 서버의 경우:</span><span class="sxs-lookup"><span data-stu-id="46e4b-114">If you deployed PSTN gateways, IP-PBXs, or Session Border Controllers (SBCs) that do not support the correct capabilities to interact with a pool of Mediation Servers, including the following, then they will need to be associated with a stand-alone pool consisting of a single Mediation Server:</span></span>

  - <span data-ttu-id="46e4b-115">풀의 중재 서버 간에 네트워크 계층 DNS (Domain Name System) 부하 분산을 수행 합니다 (또는 풀의 모든 중재 서버에 트래픽을 균일 하 게 라우팅하는 경우).</span><span class="sxs-lookup"><span data-stu-id="46e4b-115">Perform network layer Domain Name System (DNS) load balancing across Mediation Servers in a pool (or otherwise route traffic uniformly to all Mediation Servers in a pool)</span></span>

  - <span data-ttu-id="46e4b-116">풀에 있는 중재 서버의 트래픽 허용</span><span class="sxs-lookup"><span data-stu-id="46e4b-116">Accept traffic from any Mediation Server in a pool</span></span>

<span data-ttu-id="46e4b-117">Microsoft Lync Server 2013, 계획 도구를 사용 하 여 배치 중재 서버가 프런트 엔드 풀과의 부하를 처리할 수 있는지 여부를 평가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46e4b-117">You can use the Microsoft Lync Server 2013, Planning Tool to evaluate whether collocating the Mediation Server with your Front End pool can handle the load.</span></span> <span data-ttu-id="46e4b-118">사용자 환경에서 이러한 요구 사항을 충족할 수 없는 경우 독립 실행형 중재 서버 풀을 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46e4b-118">If your environment cannot meet these requirements, then you must deploy a stand-alone Mediation Server pool.</span></span>

</div>

<div>

## <a name="central-site-and-branch-site-considerations"></a><span data-ttu-id="46e4b-119">중앙 사이트 및 분기 사이트 고려 사항</span><span class="sxs-lookup"><span data-stu-id="46e4b-119">Central Site and Branch Site Considerations</span></span>

<span data-ttu-id="46e4b-p105">중앙 사이트의 중재 서버는 분기 사이트의 IP-PBX 또는 PSTN 게이트웨이에 대한 통화를 라우팅하는 데 사용될 수 있습니다. 그러나 SIP 트렁크를 배포한 경우에는 각 트렁크가 종료되는 사이트에 중재 서버를 배포해야 합니다. 분기 사이트의 IP-PBX 또는 PSTN 게이트웨이에 대한 통화를 라우팅하는 중재 서버를 중앙 사이트에 배포한 경우에는 미디어 바이패스를 사용할 필요가 없습니다. 하지만 미디어 바이패스를 사용하도록 설정할 수 있는 경우 미디어 바이패스를 사용하면 미디어 경로가 더 이상 신호 경로를 따를 필요가 없어 미디어 경로 대기 시간이 줄어들므로 미디어 품질이 향상됩니다. 미디어 바이패스는 풀의 처리 부하도 감소시킵니다.</span><span class="sxs-lookup"><span data-stu-id="46e4b-p105">Mediation Servers at the central site can be used to route calls for IP-PBXs or PSTN gateways at branch sites. If you deploy SIP trunks, however, you must deploy a Mediation Server at the site where each trunk terminates. Having a Mediation Server at the central site route calls for an IP-PBX or PSTN gateway at a branch site does not require the use of media bypass. However, if you can enable media bypass, doing so will reduce media path latency and, consequently, result in improved media quality because the media path is no longer required to follow the signaling path. Media bypass will also decrease the processing load on the pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="46e4b-125">미디어 바이패스가 모든 PSTN 게이트웨이, IP-PBX 및 SBC에서 작동하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="46e4b-125">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="46e4b-126">Microsoft는 인증 된 파트너와의 PSTN 게이트웨이 및 국내 집합을 테스트 했으며 Cisco IP-Pbx를 사용 하 여 몇 가지 테스트를 수행 했습니다.</span><span class="sxs-lookup"><span data-stu-id="46e4b-126">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="46e4b-127">미디어 바이패스는 통합 커뮤니케이션 오픈 상호 운용성 프로그램-Lync Server에 <A href="https://go.microsoft.com/fwlink/p/?linkid=268730">https://go.microsoft.com/fwlink/p/?LinkId=268730</A>나열 된 제품 및 버전 에서만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46e4b-127">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program – Lync Server at <A href="https://go.microsoft.com/fwlink/p/?linkid=268730">https://go.microsoft.com/fwlink/p/?LinkId=268730</A>.</span></span>



</div>

<span data-ttu-id="46e4b-128">분기 사이트 복구가 필요한 경우에는 SBA(Survivable Branch Appliance) 또는 프런트 엔드 서버, 중재 서버 및 게이트웨이의 조합을 분기 사이트에 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46e4b-128">If branch site resiliency is required, a Survivable Branch Appliance or combination of a Front End Server, a Mediation Server, and a gateway must be deployed at the branch site.</span></span> <span data-ttu-id="46e4b-129">분기 사이트 복구에 대 한 가정에는 현재 상태 및 회의가 사이트에서 탄력적으로 발생 하지 않는다는 것입니다. 음성에 대 한 분기 사이트 계획에 대 한 지침은 [Lync Server 2013에서 분기 사이트 음성 복구 계획](lync-server-2013-planning-for-branch-site-voice-resiliency.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="46e4b-129">(The assumption with branch site resiliency is that presence and conferencing are not resilient at the site.) For guidance on branch site planning for voice, see [Planning for branch-site voice resiliency in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).</span></span>

<span data-ttu-id="46e4b-130">Ip-https와 상호 작용 하는 경우, IP-PBX가 여러 초기 대화 및 RFC 3960 상호 작용과 함께 초기 미디어 상호 작용을 올바르게 지원 하지 않으면 IP-PBX에서 Lync 끝점으로 들어오는 호출에 대해 인사말의 처음 몇 단어를 클리핑 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46e4b-130">For interactions with an IP-PBX, if the IP-PBX does not correctly support early media interactions with multiple early dialogs and RFC 3960 interactions, there can be clipping of the first few words of the greeting for incoming calls from the IP-PBX to Lync endpoints.</span></span> <span data-ttu-id="46e4b-131">중앙 사이트의 중재 서버가 지점 사이트에서 경로가 종료 되는 IP PBX에 대 한 호출을 라우팅하는 경우, 신호가 완료 되는 데 더 많은 시간이 필요 하기 때문에이 동작이 더 심각 해질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46e4b-131">This behavior can be more severe if a Mediation Server at a central site is routing calls for an IP-PBX where the route terminates at a branch site, because more time is needed for signaling to complete.</span></span> <span data-ttu-id="46e4b-132">이 문제가 발생 하는 경우 분기 사이트에 중재 서버를 배포 하는 것은 처음 몇 단어의 클리핑을 줄이는 유일한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="46e4b-132">If you experience this behavior, deploying a Mediation Server at the branch site is the only way to reduce clipping of the first few words.</span></span>

<span data-ttu-id="46e4b-133">끝으로, 중앙 사이트에 TDM PBX가 있거나, IP-PBX가 PSTN 게이트웨이의 필요성을 해소하지 못한 경우 통화 경로에 중재 서버와 PBX를 연결하는 게이트웨이를 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46e4b-133">Finally, if your central site has a TDM PBX, or if your IP-PBX does not eliminate the need for a PSTN gateway, then you must deploy a gateway on the call route connecting Mediation Server and the PBX.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="46e4b-134">독립 실행형 중재 서버의 미디어 성능을 향상 시키려면 이러한 서버의 네트워크 어댑터에 대해 수신측 확장 (RSS)을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46e4b-134">To improve the media performance of standalone Mediation Server, you should enable receive-side scaling (RSS) on the network adapters on these servers.</span></span> <span data-ttu-id="46e4b-135">RSS를 사용 하면 서버의 여러 프로세서에서 들어오는 패킷을 병렬로 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46e4b-135">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="46e4b-136">자세한 내용은 Windows Server의 "수신측 확장 향상 기능"을 참조 <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?LinkId=268731</A>하세요.</span><span class="sxs-lookup"><span data-stu-id="46e4b-136">For details, see "Receive-Side Scaling Enhancements in Windows Server" at <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?LinkId=268731</A>.</span></span> <span data-ttu-id="46e4b-137">RSS를 사용 하도록 설정 하는 방법에 대 한 자세한 내용은 네트워크 어댑터 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="46e4b-137">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

