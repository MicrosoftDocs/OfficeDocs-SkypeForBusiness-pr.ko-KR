---
title: 'Lync Server 2013: E9-1-1에 대 한 SIP 트렁크 디자인'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Designing the SIP trunk for E9-1-1
ms:assetid: 4f93b974-b460-45c7-a4a8-6f38e34840f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398323(v=OCS.15)
ms:contentKeyID: 48184096
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 35efd8571a30b3d0dd067cbfc27f292985b6ee14
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498955"
---
# <a name="designing-the-sip-trunk-for-e9-1-1-in-lync-server-2013"></a><span data-ttu-id="191d4-102">Lync Server 2013에서 E9-1-1에 대 한 SIP 트렁크 디자인</span><span class="sxs-lookup"><span data-stu-id="191d4-102">Designing the SIP trunk for E9-1-1 in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="191d4-103">_**마지막으로 수정 된 항목:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="191d4-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="191d4-104">Lync Server에서는 SIP 트렁크을 사용 하 여 E9-1-1 서비스 공급자에 대 한 긴급 통화를 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="191d4-104">Lync Server uses SIP trunks to connect an emergency call to the E9-1-1 service provider.</span></span> <span data-ttu-id="191d4-105">하나의 중앙 사이트, 여러 중앙 사이트 또는 각 분기 사이트에서 E9-1-1에 대한 긴급 서비스 SIP 트렁크를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="191d4-105">You can set up emergency service SIP trunks for E9-1-1 at one central site, at multiple central sites, or at each branch site.</span></span> <span data-ttu-id="191d4-106">하지만 발신자 사이트와 긴급 서비스 SIP 트렁크를 호스팅하는 사이트 간의 WAN 링크를 사용할 수 없는 경우 연결이 끊긴 사이트에서 사용자가 건 통화에는 로컬 PSTN(공중 전화망) 게이트웨이를 통해 ECRC로 통화를 라우팅하는 특별한 전화 사용 레코드가 사용자의 음성 정책에 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="191d4-106">However, if the WAN link between the caller’s site and the site that hosts the emergency service SIP trunk is unavailable, then a call placed by a user at the disconnected site will need a special phone usage record in the user’s voice policy that will route the call to the ECRC through the local public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="191d4-107">통화 허용 제어 동시 통화 제한이 적용되는 경우에도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="191d4-107">The same is true if call admission control concurrent call limits are in effect.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="191d4-108">Lync Server 환경에서 SIP 트렁크를 구현 하는 방법에는 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="191d4-108">There are two ways to implement a SIP trunk in a Lync Server environment:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="191d4-109">외부에 연결 되는 공용 경로 인터페이스를 사용 하 여 SIP 트렁크 공급자와 통신 하는 멀티홈 중재 서버를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="191d4-109">Use multihomed Mediation Servers that use their outward-facing publicly-routed interfaces to communicate with the SIP trunk provider.</span></span></P>
> <LI>
> <P><span data-ttu-id="191d4-110">온-프레미스 세션 경계 컨트롤러 (SBC)를 사용 하 여 중재 서버와 SIP 트렁크 공급자 서비스 간의 안전한 구분 점을 지점을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="191d4-110">Use an on-premises Session Border Controller (SBC) to provide a secure demarcation point between the Mediation Servers and the SIP trunk provider’s services.</span></span></P></LI></UL><span data-ttu-id="191d4-111">두 번째 방법을 사용할 경우 선택한 SBC 작성 및 모델이 인증되었는지 확인하고 PIDF-LO(Presence Information Data Format Location Object) 위치 데이터를 SIP INVITE의 일부로 전달하도록 지원하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="191d4-111">If you choose the latter method, be sure that the SBC make and model that you choose has been certified and supports passing Presence Information Data Format Location Object (PIDF-LO) location data as part of its SIP INVITE.</span></span> <span data-ttu-id="191d4-112">그렇지 않으면 해당 위치 정보가 제거된 상태로 통화가 긴급 서비스 제공자에게 도착합니다.</span><span class="sxs-lookup"><span data-stu-id="191d4-112">Otherwise, the calls will arrive at the emergency services service provider stripped of their location information.</span></span> <span data-ttu-id="191d4-113">인증 된 SBCs에 대 한 자세한 내용은의 "Microsoft Lync의 인프라 자격 확인"을 참조 <A href="https://go.microsoft.com/fwlink/p/?linkid=248425">https://go.microsoft.com/fwlink/p/?LinkId=248425</A> 하세요.</span><span class="sxs-lookup"><span data-stu-id="191d4-113">For details about certified SBCs, see "Infrastructure Qualified for Microsoft Lync" at <A href="https://go.microsoft.com/fwlink/p/?linkid=248425">https://go.microsoft.com/fwlink/p/?LinkId=248425</A>.</span></span><BR><span data-ttu-id="191d4-114">E9-1-1 서비스 공급자는 중복성을 위해 한 쌍의 SBCs 액세스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="191d4-114">E9-1-1 service providers supply you with access to a pair of SBCs for redundancy.</span></span> <span data-ttu-id="191d4-115">중재 서버 토폴로지 및 통화 라우팅 구성과 관련 하 여 몇 가지 사항을 결정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="191d4-115">You need to make several decisions regarding the Mediation Server topology and call routing configuration.</span></span> <span data-ttu-id="191d4-116">두 개의 모든 사용자를 동일한 피어로 처리 하 고 이러한 통화 간 호출에 라운드 로빈 라우팅을 사용 하 시겠습니까?</span><span class="sxs-lookup"><span data-stu-id="191d4-116">Will you treat both SBCs as equal peers and use round-robin routing for calls between them, or will you designate one SBC as primary and the other as secondary?</span></span>



</div>

<span data-ttu-id="191d4-117">Lync Server에서 SIP 트렁크를 배포 하는 방법에 대 한 자세한 내용은 [How To 어떻게 sip 트렁크을 구현 합니까? Lync server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="191d4-117">For details about deploying a SIP trunk in Lync Server, see [How do I implement SIP trunking in Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).</span></span> <span data-ttu-id="191d4-118">다음 질문은 E9-1-1을 위한 SP 트렁크 배포 방법을 결정하는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="191d4-118">The following questions will help you decide how to deploy the SIP trunks for E9-1-1.</span></span>

  - <span data-ttu-id="191d4-119">**SIP 트렁크를 배포할 때 사용할 연결(전용 임대 연결 또는 공유 인터넷 연결)**</span><span class="sxs-lookup"><span data-stu-id="191d4-119">**Should you deploy the SIP trunk over a dedicated leased or a shared internet connection?**</span></span>  
    <span data-ttu-id="191d4-p105">긴급 통화는 항상 연결되어야 합니다. 따라서 전용선을 사용하면 연결이 네트워크의 다른 트래픽에 의해 선취되지 않으며, QoS(서비스 품질)를 구현할 수 있습니다. 공용 인터넷을 통해 긴급 서비스 제공자에 연결할 경우 긴급 통화의 기밀성을 보장해야 하며 IPSec 암호화가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="191d4-p105">It is important that emergency calls always connect. A dedicated line provides a connection that will not be preempted by other traffic on the network, and gives you the ability to implement Quality of Service (QoS). Remember that if you are connecting to emergency services service providers over the public Internet and you need to guarantee the confidentiality of emergency calls, IPSec encryption is required.</span></span>

<!-- end list -->

  - <span data-ttu-id="191d4-123">**E9-1-1 배포가 재해 내결함성을 위해 설계 되었습니까?**</span><span class="sxs-lookup"><span data-stu-id="191d4-123">**Is your E9-1-1 deployment designed for disaster tolerance?**</span></span>  
    <span data-ttu-id="191d4-124">이 배포는 긴급 솔루션이므로 복구가 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="191d4-124">Because this is an emergency solution, resiliency is important.</span></span> <span data-ttu-id="191d4-125">재해 허용 위치에 기본 및 보조 중재 서버 및 SIP 트렁크를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="191d4-125">Deploy your primary and secondary Mediation Servers and SIP trunks in disaster tolerant locations.</span></span> <span data-ttu-id="191d4-126">지원 되는 사용자에 게 가장 가까운 기본 중재 서버를 배포 하 고 다른 지리적 위치에 있는 보조 중재 서버를 통해 장애 조치 (failover) 호출을 라우팅하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="191d4-126">It is a good idea to deploy your primary Mediation Server closest to the users that it is supporting, and route failover calls through the secondary Mediation Server (located in a different geographic location).</span></span>

<!-- end list -->

  - <span data-ttu-id="191d4-127">**각 지점에 대해 별도의 SIP 트렁크를 배포할지 여부**</span><span class="sxs-lookup"><span data-stu-id="191d4-127">**Should you deploy a separate SIP trunk for each branch office?**</span></span>  
    <span data-ttu-id="191d4-128">Lync Server에서는 복구 가능한 데이터 네트워크를 포함 하거나, 각 분기에서 SIP 트렁크를 배포 하거나, 중단 시 로컬 게이트웨이로 호출을 실행 하는 등의 방법으로 분기 사무실에서 음성 복구를 처리 하기 위한 몇 가지 전략을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="191d4-128">Lync Server provides several strategies for handling voice resiliency in branch offices, including: having resilient data networks, deploying a SIP trunk at each branch, or pushing calls out to the local gateway during outages.</span></span> <span data-ttu-id="191d4-129">자세한 내용은 [Branch SITE SIP 트렁크 In Lync Server 2013](lync-server-2013-branch-site-sip-trunking.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="191d4-129">For details, see [Branch site SIP trunking in Lync Server 2013](lync-server-2013-branch-site-sip-trunking.md).</span></span>

<!-- end list -->

  - <span data-ttu-id="191d4-130">**CAC(통화 허용 제어)가 사용하도록 설정되는지 여부**</span><span class="sxs-lookup"><span data-stu-id="191d4-130">**Is call admission control (CAC) enabled?**</span></span>  
    <span data-ttu-id="191d4-131">Lync Server에서는 일반 통화와는 다른 긴급 통화를 처리 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="191d4-131">Lync Server does not handle emergency calls any differently than an ordinary call.</span></span> <span data-ttu-id="191d4-132">따라서 대역폭 관리 또는 CAC(통화 허용 제어)가 E9-1-1 구성에 좋지 않은 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="191d4-132">For this reason, bandwidth management, or call admission control (CAC), can have a negative impact on an E9-1-1 configuration.</span></span> <span data-ttu-id="191d4-133">CAC가 사용하도록 설정되어 있으며 긴급 통화를 라우팅하는 링크에서 구성된 제한을 초과한 경우, 긴급 통화가 차단되거나 로컬 PSTN 게이트웨이로 라우팅될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="191d4-133">Emergency calls will be blocked or routed to the local PSTN gateway if a CAC is enabled and the configured limit is exceeded on a link where emergency calls are being routed.</span></span> <span data-ttu-id="191d4-134">이 항목의 앞 부분에 표시된 것처럼 이러한 통화는 위치 데이터를 포함하지 않으며 수동으로 ECRC로 라우팅해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="191d4-134">As indicated earlier in this topic, such calls will not have location data and must be manually routed to the ECRC.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

