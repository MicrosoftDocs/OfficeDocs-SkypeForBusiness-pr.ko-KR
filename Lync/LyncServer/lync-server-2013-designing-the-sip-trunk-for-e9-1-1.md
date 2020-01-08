---
title: 'Lync Server 2013: E9 용 SIP 트렁크 디자인-1-1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Designing the SIP trunk for E9-1-1
ms:assetid: 4f93b974-b460-45c7-a4a8-6f38e34840f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398323(v=OCS.15)
ms:contentKeyID: 48184096
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2bee3985efd3510b62bfe43b3aa5742f63679093
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981091"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="designing-the-sip-trunk-for-e9-1-1-in-lync-server-2013"></a><span data-ttu-id="b9549-102">Lync Server 2013에서 E9 용 SIP 트렁크 디자인-1-1</span><span class="sxs-lookup"><span data-stu-id="b9549-102">Designing the SIP trunk for E9-1-1 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b9549-103">_**마지막으로 수정한 주제:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="b9549-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="b9549-104">Lync Server는 SIP trunks를 사용 하 여 비상 통화를 E9-1-1 서비스 공급자에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9549-104">Lync Server uses SIP trunks to connect an emergency call to the E9-1-1 service provider.</span></span> <span data-ttu-id="b9549-105">한 중앙 사이트, 여러 중앙 사이트 또는 각 지점 사이트에서 E9-1-1에 대 한 비상 서비스 SIP trunks를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9549-105">You can set up emergency service SIP trunks for E9-1-1 at one central site, at multiple central sites, or at each branch site.</span></span> <span data-ttu-id="b9549-106">그러나 발신자의 사이트와 응급 서비스 SIP 트렁크를 호스트 하는 사이트 간의 WAN 연결을 사용할 수 없는 경우 연결이 끊긴 사이트의 사용자가 전화를 거는 경우 사용자의 음성 정책에서 전화를 라우팅할 수 있는 특별 한 휴대폰 사용 레코드가 필요 합니다. 로컬 PSTN (공개 교환 전화 네트워크) 게이트웨이를 통해 ECRC.</span><span class="sxs-lookup"><span data-stu-id="b9549-106">However, if the WAN link between the caller’s site and the site that hosts the emergency service SIP trunk is unavailable, then a call placed by a user at the disconnected site will need a special phone usage record in the user’s voice policy that will route the call to the ECRC through the local public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="b9549-107">통화 허용 제어 동시 통화 한도가 적용 되는 경우에도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="b9549-107">The same is true if call admission control concurrent call limits are in effect.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b9549-108">Lync 서버 환경에서 SIP 트렁크를 구현 하는 방법에는 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9549-108">There are two ways to implement a SIP trunk in a Lync Server environment:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="b9549-109">외부에 연결 된 공개적으로 라우팅된 인터페이스를 사용 하는 멀티홈 중재 서버를 사용 하 여 SIP 트렁크 공급자와 통신 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9549-109">Use multihomed Mediation Servers that use their outward-facing publicly-routed interfaces to communicate with the SIP trunk provider.</span></span></P>
> <LI>
> <P><span data-ttu-id="b9549-110">SBC (온-프레미스 세션 경계 컨트롤러)를 사용 하 여 중재 서버와 SIP 트렁크 공급자 서비스 간에 안전한 demarcation 지점을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9549-110">Use an on-premises Session Border Controller (SBC) to provide a secure demarcation point between the Mediation Servers and the SIP trunk provider’s services.</span></span></P></LI></UL><span data-ttu-id="b9549-111">후자 방법을 선택 하는 경우 선택 하는 SBC 만들기 및 모델이 인증 되었는지 확인 하 고 SIP 초대의 일부로 현재 상태 정보 데이터 형식 위치 개체 (PIDF-낮음) 위치 데이터를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9549-111">If you choose the latter method, be sure that the SBC make and model that you choose has been certified and supports passing Presence Information Data Format Location Object (PIDF-LO) location data as part of its SIP INVITE.</span></span> <span data-ttu-id="b9549-112">그렇지 않으면 통화는 비상 서비스 서비스 제공 업체에서 해당 위치 정보를 제거할 때에도 도달 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9549-112">Otherwise, the calls will arrive at the emergency services service provider stripped of their location information.</span></span> <span data-ttu-id="b9549-113">인증 된 SBCs에 대 한 자세한 내용은에서 <A href="http://go.microsoft.com/fwlink/p/?linkid=248425">http://go.microsoft.com/fwlink/p/?LinkId=248425</A>"Microsoft Lync에 대 한 인프라 적격"을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b9549-113">For details about certified SBCs, see "Infrastructure Qualified for Microsoft Lync" at <A href="http://go.microsoft.com/fwlink/p/?linkid=248425">http://go.microsoft.com/fwlink/p/?LinkId=248425</A>.</span></span><BR><span data-ttu-id="b9549-114">E9-1-1 서비스 공급자는 중복성을 위해 한 쌍의 SBCs에 대 한 액세스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9549-114">E9-1-1 service providers supply you with access to a pair of SBCs for redundancy.</span></span> <span data-ttu-id="b9549-115">중재 서버 토폴로지와 호출 라우팅 구성과 관련 하 여 몇 가지 사항을 결정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9549-115">You need to make several decisions regarding the Mediation Server topology and call routing configuration.</span></span> <span data-ttu-id="b9549-116">두 개의 SBCs를 모두 동등 피어로 처리 하 고 그 사이의 호출에 라운드 로빈 라우팅을 사용 하 고 있으며 SBC 하나는 기본으로 지정 하 고 나머지는 보조로 지정할 예정</span><span class="sxs-lookup"><span data-stu-id="b9549-116">Will you treat both SBCs as equal peers and use round-robin routing for calls between them, or will you designate one SBC as primary and the other as secondary?</span></span>



</div>

<span data-ttu-id="b9549-117">Lync Server에서 SIP 트렁크를 배포 하는 방법에 대 한 자세한 내용은 [Lync server 2013에서 sip 트렁크을 구현 하는 방법은 무엇 인가요?](lync-server-2013-how-do-i-implement-sip-trunking.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b9549-117">For details about deploying a SIP trunk in Lync Server, see [How do I implement SIP trunking in Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).</span></span> <span data-ttu-id="b9549-118">다음 질문은 E9-1-1에 대 한 SIP trunks를 배포 하는 방법을 결정 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9549-118">The following questions will help you decide how to deploy the SIP trunks for E9-1-1.</span></span>

  - <span data-ttu-id="b9549-119">**전용 임대 또는 공유 인터넷 연결을 통해 SIP 트렁크를 배포 해야 하나요?**</span><span class="sxs-lookup"><span data-stu-id="b9549-119">**Should you deploy the SIP trunk over a dedicated leased or a shared internet connection?**</span></span>  
    <span data-ttu-id="b9549-120">비상 전화는 항상 연결 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9549-120">It is important that emergency calls always connect.</span></span> <span data-ttu-id="b9549-121">전용 회선은 네트워크의 다른 트래픽에 의해 선점 되지 않는 연결을 제공 하 고 서비스 품질 (QoS)을 구현 하는 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9549-121">A dedicated line provides a connection that will not be preempted by other traffic on the network, and gives you the ability to implement Quality of Service (QoS).</span></span> <span data-ttu-id="b9549-122">일반 인터넷을 통해 응급 서비스 서비스 공급자에 연결 하는 경우 긴급 전화의 기밀성을 보장 해야 한다는 점에 유의 하 여 IPSec 암호화가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9549-122">Remember that if you are connecting to emergency services service providers over the public Internet and you need to guarantee the confidentiality of emergency calls, IPSec encryption is required.</span></span>

<!-- end list -->

  - <span data-ttu-id="b9549-123">**재해 허용에 맞게 설계 된 E9-1 배포**</span><span class="sxs-lookup"><span data-stu-id="b9549-123">**Is your E9-1-1 deployment designed for disaster tolerance?**</span></span>  
    <span data-ttu-id="b9549-124">이것은 긴급 해결 방법 이므로 탄력성이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9549-124">Because this is an emergency solution, resiliency is important.</span></span> <span data-ttu-id="b9549-125">주 및 보조 중재 서버와 SIP trunks를 재해 허용 위치에 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9549-125">Deploy your primary and secondary Mediation Servers and SIP trunks in disaster tolerant locations.</span></span> <span data-ttu-id="b9549-126">지원 되는 사용자에 게 가장 가까운 기본 중재 서버를 배포 하 고 보조 중재 서버 (다른 지리적 위치에 있는)로 장애 조치 (failover) 호출을 라우팅하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b9549-126">It is a good idea to deploy your primary Mediation Server closest to the users that it is supporting, and route failover calls through the secondary Mediation Server (located in a different geographic location).</span></span>

<!-- end list -->

  - <span data-ttu-id="b9549-127">**각 지점에 대 한 별도의 SIP 트렁크를 배포 해야 하나요?**</span><span class="sxs-lookup"><span data-stu-id="b9549-127">**Should you deploy a separate SIP trunk for each branch office?**</span></span>  
    <span data-ttu-id="b9549-128">Lync Server는 복구 데이터 네트워크를 보유 하거나, 각 지점에서 SIP 트렁크를 배포 하거나, 중단 하는 동안 로컬 게이트웨이로 호출을 비롯 하 여 지사에서 음성 복원을 처리 하기 위한 몇 가지 전략을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9549-128">Lync Server provides several strategies for handling voice resiliency in branch offices, including: having resilient data networks, deploying a SIP trunk at each branch, or pushing calls out to the local gateway during outages.</span></span> <span data-ttu-id="b9549-129">자세한 내용은 [Lync Server 2013에서 지사 사이트 SIP 트렁크](lync-server-2013-branch-site-sip-trunking.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b9549-129">For details, see [Branch site SIP trunking in Lync Server 2013](lync-server-2013-branch-site-sip-trunking.md).</span></span>

<!-- end list -->

  - <span data-ttu-id="b9549-130">**호출 허용 제어 (CAC)를 사용할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="b9549-130">**Is call admission control (CAC) enabled?**</span></span>  
    <span data-ttu-id="b9549-131">Lync Server는 일반 통화와는 다른 비상 전화를 처리 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b9549-131">Lync Server does not handle emergency calls any differently than an ordinary call.</span></span> <span data-ttu-id="b9549-132">이러한 이유로 대역폭 관리 또는 CAC (통화 허용 제어)가 E9-1-1 구성에 부정적인 영향을 미칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9549-132">For this reason, bandwidth management, or call admission control (CAC), can have a negative impact on an E9-1-1 configuration.</span></span> <span data-ttu-id="b9549-133">CAC가 사용 하도록 설정 되어 있고 긴급 호출이 라우팅되는 링크에서 구성 된 한도가 초과 되는 경우 긴급 전화는 로컬 PSTN 게이트웨이로 차단 되거나 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9549-133">Emergency calls will be blocked or routed to the local PSTN gateway if a CAC is enabled and the configured limit is exceeded on a link where emergency calls are being routed.</span></span> <span data-ttu-id="b9549-134">이 항목의 앞부분에서 설명한 대로 이러한 호출에는 위치 데이터가 없으며 수동으로 ECRC에 라우팅해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9549-134">As indicated earlier in this topic, such calls will not have location data and must be manually routed to the ECRC.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

