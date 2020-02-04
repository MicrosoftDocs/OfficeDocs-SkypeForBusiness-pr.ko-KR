---
title: 'Lync Server 2013: 중재 서버 배포 지침'
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
ms.openlocfilehash: 3c91ea4368d96e6a558a25eda86d163e4ced4cb8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762676"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-guidelines-for-mediation-server-in-lync-server-2013"></a><span data-ttu-id="81f39-102">Lync Server 2013의 중재 서버 배포 지침</span><span class="sxs-lookup"><span data-stu-id="81f39-102">Deployment guidelines for Mediation Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="81f39-103">_**마지막으로 수정한 주제:** 2012-10-12_</span><span class="sxs-lookup"><span data-stu-id="81f39-103">_**Topic Last Modified:** 2012-10-12_</span></span>

<span data-ttu-id="81f39-104">이 항목에서는 중재 서버 배포에 대 한 계획 지침을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="81f39-104">This topic describes planning guidelines for Mediation Server deployment.</span></span> <span data-ttu-id="81f39-105">이러한 지침을 검토 한 후 계획 도구를 사용 하 여 배포 하기로 결정 하는 최종 맞춤형 토폴로지에 대 한 모델로 사용할 수 있는 대체 토폴로지를 만들고 보는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="81f39-105">After reviewing these guidelines, we recommend that you use the Planning Tool to create and view possible alternative topologies, which can serve as models for what the final tailored topology that you decide to deploy would look like.</span></span>

<div>

## <a name="collocated-or-stand-alone-mediation-server"></a><span data-ttu-id="81f39-106">Collocated 또는 독립 실행형 중재 서버</span><span class="sxs-lookup"><span data-stu-id="81f39-106">Collocated or Stand-alone Mediation Server?</span></span>

<span data-ttu-id="81f39-107">중재 서버는 기본적으로 Standard Edition Server 또는 중앙 사이트의 프런트 엔드 풀에 있는 프런트 엔드 서버에 collocated 됩니다.</span><span class="sxs-lookup"><span data-stu-id="81f39-107">Mediation Server is by default collocated on the Standard Edition server or Front End Server in a Front End pool at central sites.</span></span> <span data-ttu-id="81f39-108">처리할 수 있는 PSTN (공개 통신 네트워크) 및 풀에 필요한 컴퓨터 수는 다음 사항에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="81f39-108">The number of public switched telephone network (PSTN) calls that can be handled and the number of machines required in the pool will depend on the following:</span></span>

  - <span data-ttu-id="81f39-109">중재 서버 풀 컨트롤에서 제어 하는 게이트웨이 피어 수</span><span class="sxs-lookup"><span data-stu-id="81f39-109">The number of gateway peers that the Mediation Server pool controls</span></span>

  - <span data-ttu-id="81f39-110">이러한 게이트웨이를 통한 대용량 트래픽 기간</span><span class="sxs-lookup"><span data-stu-id="81f39-110">The high-volume traffic periods through those gateways</span></span>

  - <span data-ttu-id="81f39-111">미디어에서 중재 서버를 우회 하는 전화 통화의 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="81f39-111">The percentage of calls that are calls whose media bypass the Mediation Server</span></span>

<span data-ttu-id="81f39-112">계획을 수립할 때는 미디어를 우회 하도록 구성 되지 않은 PSTN 통화 및 A/V 회의에 대 한 미디어 처리 요구 사항을 고려 하 고 지원 해야 하는 사용 중인 통화 시간에 대 한 신호 상호 작용을 처리 하는 데 필요한 처리 작업을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81f39-112">When planning, be sure to take into account the media processing requirements for PSTN calls and A/V conferences that are not configured for media bypass, as well as the processing needed to handle signaling interactions for the number of busy-hour calls that need to be supported.</span></span> <span data-ttu-id="81f39-113">CPU가 충분 하지 않으면 중재 서버의 독립 실행형 풀을 배포 해야 합니다. 및 PSTN 게이트웨이, IP-Pbx, SBCs는 하나의 풀에 있는 collocated 중재 서버에 의해 제어 되는 하위 집합으로 분할 되어야 하며 하나 이상의 독립 실행형 풀에 독립 실행형 중재 서버에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81f39-113">If there is not enough CPU, then you must deploy a stand-alone pool of Mediation Servers; and PSTN gateways, IP-PBXs, and SBCs will need to be split into subsets that are controlled by the collocated Mediation Servers in one pool and the stand-alone Mediation Servers in one or more stand-alone pools.</span></span>

<span data-ttu-id="81f39-114">다음을 포함 하 여 조정 서버 풀과 상호 작용 하기 위한 올바른 기능을 지원 하지 않는 PSTN 게이트웨이, IP-Pbx 또는 SBCs (세션 경계 컨트롤러)를 배포 하는 경우, 다음과 같이 구성 된 독립 실행형 풀에 연결 해야 합니다. 단일 중재 서버의 경우:</span><span class="sxs-lookup"><span data-stu-id="81f39-114">If you deployed PSTN gateways, IP-PBXs, or Session Border Controllers (SBCs) that do not support the correct capabilities to interact with a pool of Mediation Servers, including the following, then they will need to be associated with a stand-alone pool consisting of a single Mediation Server:</span></span>

  - <span data-ttu-id="81f39-115">풀의 중재 서버에서 네트워크 레이어 DNS (Domain Name System) 로드 균형 조정을 수행 하거나 풀의 모든 중재 서버에 일관 된 트래픽 라우팅</span><span class="sxs-lookup"><span data-stu-id="81f39-115">Perform network layer Domain Name System (DNS) load balancing across Mediation Servers in a pool (or otherwise route traffic uniformly to all Mediation Servers in a pool)</span></span>

  - <span data-ttu-id="81f39-116">풀의 중재 서버에서 트래픽 수락</span><span class="sxs-lookup"><span data-stu-id="81f39-116">Accept traffic from any Mediation Server in a pool</span></span>

<span data-ttu-id="81f39-117">Microsoft Lync Server 2013, 계획 도구를 사용 하 여 collocating가 프런트 엔드 풀을 사용 하는 조정 서버에서 부하를 처리할 수 있는지 여부를 평가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81f39-117">You can use the Microsoft Lync Server 2013, Planning Tool to evaluate whether collocating the Mediation Server with your Front End pool can handle the load.</span></span> <span data-ttu-id="81f39-118">환경이 이러한 요구 사항을 충족 하지 못하는 경우에는 독립 실행형 중재 서버 풀을 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81f39-118">If your environment cannot meet these requirements, then you must deploy a stand-alone Mediation Server pool.</span></span>

</div>

<div>

## <a name="central-site-and-branch-site-considerations"></a><span data-ttu-id="81f39-119">중앙 사이트 및 지점 사이트 고려 사항</span><span class="sxs-lookup"><span data-stu-id="81f39-119">Central Site and Branch Site Considerations</span></span>

<span data-ttu-id="81f39-120">중앙 사이트의 중재 서버를 사용 하 여 지점 사이트에서 IP Pbx 또는 PSTN 게이트웨이에 대 한 통화를 라우팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81f39-120">Mediation Servers at the central site can be used to route calls for IP-PBXs or PSTN gateways at branch sites.</span></span> <span data-ttu-id="81f39-121">그러나 SIP trunks를 배포 하는 경우 각 트렁크가 종료 되는 사이트에 중재 서버를 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81f39-121">If you deploy SIP trunks, however, you must deploy a Mediation Server at the site where each trunk terminates.</span></span> <span data-ttu-id="81f39-122">중앙 사이트에서 지점 사이트의 IP PBX 또는 PSTN 게이트웨이에 대 한 중재 서버를 사용 하는 경우 미디어 바이패스를 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="81f39-122">Having a Mediation Server at the central site route calls for an IP-PBX or PSTN gateway at a branch site does not require the use of media bypass.</span></span> <span data-ttu-id="81f39-123">그러나 미디어 바이패스를 사용 하도록 설정할 수 있는 경우에는 미디어 경로 대기 시간이 줄어들지만, 따라서 더 이상 미디어 경로가 신호 경로를 따르지 않아도 되므로 미디어 품질이 향상 됩니다.</span><span class="sxs-lookup"><span data-stu-id="81f39-123">However, if you can enable media bypass, doing so will reduce media path latency and, consequently, result in improved media quality because the media path is no longer required to follow the signaling path.</span></span> <span data-ttu-id="81f39-124">미디어 바이패스는 또한 풀의 처리 로드를 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="81f39-124">Media bypass will also decrease the processing load on the pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="81f39-125">미디어 바이패스는 모든 PSTN 게이트웨이, IP PBX, SBC와 상호 작용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81f39-125">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="81f39-126">Microsoft는 인증 된 파트너와 함께 PSTN 게이트웨이 및 SBCs 집합을 테스트 했으며 Cisco IP-Pbx를 사용 하 여 테스트를 완료 했습니다.</span><span class="sxs-lookup"><span data-stu-id="81f39-126">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="81f39-127">미디어 바이패스는 통합 커뮤니케이션 오픈 상호 운용성 프로그램 –의 Lync Server에 나열 된 제품 및 버전 에서만 <A href="http://go.microsoft.com/fwlink/p/?linkid=268730">http://go.microsoft.com/fwlink/p/?LinkId=268730</A>지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="81f39-127">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program – Lync Server at <A href="http://go.microsoft.com/fwlink/p/?linkid=268730">http://go.microsoft.com/fwlink/p/?LinkId=268730</A>.</span></span>



</div>

<span data-ttu-id="81f39-128">지점 사이트의 복원성이 필요한 경우 Survivable Branch 기기 또는 프런트 엔드 서버, 중재 서버 및 게이트웨이의 조합이 지점 사이트에 배포 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81f39-128">If branch site resiliency is required, a Survivable Branch Appliance or combination of a Front End Server, a Mediation Server, and a gateway must be deployed at the branch site.</span></span> <span data-ttu-id="81f39-129">지점 사이트 복원에 대 한 전제 하에는 현재 상태와 회의가 사이트에 탄력적으로 포함 되어 있지 않습니다. 음성에 대 한 지점 사이트 계획에 대 한 지침은 [Lync Server 2013의 지점 사이트 음성 복원 계획](lync-server-2013-planning-for-branch-site-voice-resiliency.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="81f39-129">(The assumption with branch site resiliency is that presence and conferencing are not resilient at the site.) For guidance on branch site planning for voice, see [Planning for branch-site voice resiliency in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).</span></span>

<span data-ttu-id="81f39-130">Ip pbx와의 상호 작용을 위해 IP-PBX가 여러 초기 대화 및 RFC 3960 상호 작용을 통해 초기 미디어 조작을 올바르게 지원 하지 않는 경우에는 IP PBX에서 Lync 끝점으로 들어오는 통화에 대 한 인사말의 처음 몇 단어를 클리핑 하 게 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81f39-130">For interactions with an IP-PBX, if the IP-PBX does not correctly support early media interactions with multiple early dialogs and RFC 3960 interactions, there can be clipping of the first few words of the greeting for incoming calls from the IP-PBX to Lync endpoints.</span></span> <span data-ttu-id="81f39-131">중앙 사이트의 중재 서버가 지점 사이트에서 경로가 종료 되는 IP PBX에 대 한 라우팅 호출을 수행 하는 경우, 알림을 보내는 데 시간이 더 필요 하기 때문에 더욱 심각한 문제가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81f39-131">This behavior can be more severe if a Mediation Server at a central site is routing calls for an IP-PBX where the route terminates at a branch site, because more time is needed for signaling to complete.</span></span> <span data-ttu-id="81f39-132">이 동작이 발생 하는 경우 분기 사이트에서 중재 서버를 배포 하는 것이 처음 몇 단어의 클리핑을 줄이는 유일한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="81f39-132">If you experience this behavior, deploying a Mediation Server at the branch site is the only way to reduce clipping of the first few words.</span></span>

<span data-ttu-id="81f39-133">마지막으로, 중앙 사이트에 TDM PBX가 있거나 IP PBX가 PSTN 게이트웨이를 필요로 하지 않는 경우에는 중재 서버와 PBX를 연결 하는 call 경로에 게이트웨이를 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81f39-133">Finally, if your central site has a TDM PBX, or if your IP-PBX does not eliminate the need for a PSTN gateway, then you must deploy a gateway on the call route connecting Mediation Server and the PBX.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="81f39-134">독립 실행형 중재 서버의 미디어 성능을 향상 시키려면 이러한 서버의 네트워크 어댑터에서 수신측 배율 (RSS)을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81f39-134">To improve the media performance of standalone Mediation Server, you should enable receive-side scaling (RSS) on the network adapters on these servers.</span></span> <span data-ttu-id="81f39-135">RSS를 사용 하면 서버의 여러 프로세서가 들어오는 패킷을 병렬로 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81f39-135">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="81f39-136">자세한 내용은에서 <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?LinkId=268731</A>"Windows Server의 수신측 스케일링 개선 사항"을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="81f39-136">For details, see "Receive-Side Scaling Enhancements in Windows Server" at <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?LinkId=268731</A>.</span></span> <span data-ttu-id="81f39-137">RSS를 사용 하도록 설정 하는 방법에 대 한 자세한 내용은 네트워크 어댑터 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="81f39-137">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

