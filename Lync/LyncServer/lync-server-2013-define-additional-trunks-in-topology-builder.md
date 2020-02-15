---
title: 'Lync Server 2013: 토폴로지 작성기에서 추가 트렁크 정의'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define additional trunks in Topology Builder
ms:assetid: e68b8377-50a2-452a-bf5c-910929e34236
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721915(v=OCS.15)
ms:contentKeyID: 49733849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f88a292b11e617d1ae0d20f603ad53b2b2847e7f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038140"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-additional-trunks-in-topology-builder-in-lync-server-2013"></a><span data-ttu-id="da993-102">Lync Server 2013의 토폴로지 작성기에서 추가 트렁크 정의</span><span class="sxs-lookup"><span data-stu-id="da993-102">Define additional trunks in Topology Builder in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="da993-103">_**마지막으로 수정 된 항목:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="da993-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="da993-104">다음 단계에 따라 토폴로지 작성기를 사용 하 여 *피어* 를 중재 서버에 연결할 수 있는 추가 트렁크를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="da993-104">Follow these steps to use Topology Builder to define an additional trunk to which you can associate a *peer* with a Mediation Server.</span></span> <span data-ttu-id="da993-105">피어는 공중 전화망 (PSTN)에 대 한 연결을 사용 하 여 Enterprise Voice를 사용할 수 있도록 하는 사용자를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="da993-105">A peer provides users enabled for Enterprise Voice with connectivity to the public switched telephone network (PSTN).</span></span> <span data-ttu-id="da993-106">피어는 ITSP (인터넷 전화 통신 서비스 공급자)에 대 한 PSTN 게이트웨이, IP PBX 또는 SBC (Session Border Controller) 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da993-106">A peer can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP).</span></span> <span data-ttu-id="da993-107">트렁크는 중재 서버와 피어 간에이 연결을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="da993-107">The trunk defines this connection between the Mediation Server and peer.</span></span> <span data-ttu-id="da993-108">중재 서버 마다 여러 트렁크를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da993-108">Multiple trunks can be defined per Mediation Server.</span></span> <span data-ttu-id="da993-109">중재 서버는 여러 피어와 연결 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da993-109">A Mediation Server can be associated with multiple peers.</span></span>

<span data-ttu-id="da993-110">트렁크는 중재 서버와 튜플에 의해 고유 하 게 식별 되는 게이트웨이 간의 논리적 연결입니다.</span><span class="sxs-lookup"><span data-stu-id="da993-110">A trunk is a logical connection between a Mediation Server and a gateway uniquely identified by the tuple:</span></span>

<span data-ttu-id="da993-111">{중재 서버 FQDN, 중재 서버 수신 대기 포트 (TLS 또는 TCP): 게이트웨이 IP 및 FQDN, 게이트웨이 수신 대기 포트}</span><span class="sxs-lookup"><span data-stu-id="da993-111">{Mediation Server FQDN, Mediation Server listening port (TLS or TCP) : gateway IP and FQDN, gateway listening port}</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="da993-112">이 항목에서는 배포 설명서에서 <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">Lync Server 2013의 토폴로지 작성기</A> 에서 기술 정의에 설명 된 대로 하나 이상의 배치 된 또는 독립 실행형 중재 서버 또는 풀을 사용 하 여 PSTN 게이트웨이 및 루트 트렁크를 설정 했다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="da993-112">This topic assumes that you have setup a PSTN gateway and root trunk with at least one collocated or stand-alone Mediation Server or pool as described in <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">Define a gateway in Topology Builder in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="da993-113">이 항목에서는 배포 설명서의 lync server <A href="lync-server-2013-publish-the-topology.md">2013</A> <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">2013에서 프런트 엔드 풀 또는 Standard edition server 정의 및 구성</A> 에 설명 된 대로 하나 이상의 프런트 엔드 풀 또는 standard edition 서버를 적어도 하나의 중앙 사이트에 설정 했다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="da993-113">This topic assumes that you have set up at least one Front End pool or Standard Edition server in at least one central site, as described in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</A> and <A href="lync-server-2013-publish-the-topology.md">Publish the topology in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a><span data-ttu-id="da993-114">중재 서버와 게이트웨이 피어 사이에 추가 트렁크를 정의 하려면</span><span class="sxs-lookup"><span data-stu-id="da993-114">To Define an additional Trunk between a Mediation Server and a Gateway Peer</span></span>

1.  <span data-ttu-id="da993-115">토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="da993-115">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="da993-116">Lync Server 2013, 사이트 이름, **공유 구성 요소**에서 **트렁크** 노드를 마우스 오른쪽 단추로 클릭 한 다음 **새 트렁크**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="da993-116">Under Lync Server 2013, your site name, **Shared Components**, right-click the **Trunks** node, and then click **New Trunk**.</span></span>
    
    <span data-ttu-id="da993-117">![Lync Server 토폴로지 작성기 파일 구조 화면](images/JJ721915.90d5b349-aa1e-407a-87ed-fa112f478560(OCS.15).png "Lync Server 토폴로지 작성기 파일 구조 화면")</span><span class="sxs-lookup"><span data-stu-id="da993-117">![Lync Server Topology Builder file structure screen](images/JJ721915.90d5b349-aa1e-407a-87ed-fa112f478560(OCS.15).png "Lync Server Topology Builder file structure screen")</span></span>

3.  <span data-ttu-id="da993-118">**새 트렁크 정의**에서 트렁크를 고유 하 게 식별 하는 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="da993-118">In **Define New Trunk**, specify a friendly name to uniquely identify the trunk.</span></span> <span data-ttu-id="da993-119">이름이 같은 두 트렁크를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="da993-119">You cannot have two trunks with the same name.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="da993-120">TLS (전송 계층 보안)를 전송 유형으로 지정 하는 경우 중재 서버 피어의 IP 주소 대신 FQDN을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da993-120">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span>

    
    </div>

4.  <span data-ttu-id="da993-121">**연결 된 pstn 게이트웨이에서**이 트렁크와 연결할 PSTN 게이트웨이 피어를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="da993-121">Under **Associated PSTN gateway**, select the PSTN gateway peer to associate with this trunk.</span></span>
    
    <span data-ttu-id="da993-122">![트렁크에 대 한 PSTN 게이트웨이 피어에 대 한 속성 설정](images/JJ721915.7c3fe8ee-8f4c-4413-8462-8347228e61bb(OCS.15).png "트렁크에 대 한 PSTN 게이트웨이 피어에 대 한 속성 설정")</span><span class="sxs-lookup"><span data-stu-id="da993-122">![Property settings for PSTN gateway peer for trunk](images/JJ721915.7c3fe8ee-8f4c-4413-8462-8347228e61bb(OCS.15).png "Property settings for PSTN gateway peer for trunk")</span></span>

5.  <span data-ttu-id="da993-123">**Pstn 게이트웨이의 수신 대기 포트**에서 피어 (pstn 게이트웨이, IP-PBX 또는 SBC)가이 트렁크와 연결할 중재 서버 로부터 SIP 메시지를 받을 수신 대기 포트를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="da993-123">Under **Listening Port for PSTN gateway**, type the listening port that the peer (PSTN gateway, IP-PBX, or SBC) will receive SIP messages from the Mediation Server that is to be associated with this trunk.</span></span> <span data-ttu-id="da993-124">기본 피어 포트는 TCP (전송 제어 프로토콜)의 경우 5066이 고 TLS (전송 계층 보안)의 경우 5067입니다.</span><span class="sxs-lookup"><span data-stu-id="da993-124">The default peer ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS).</span></span> <span data-ttu-id="da993-125">기본 Sba (survivable Branch 기기 포트는 TCP의 경우 5081이 고 TLS의 경우 5082입니다.</span><span class="sxs-lookup"><span data-stu-id="da993-125">The default Survivable Branch Appliance ports are 5081 for TCP and 5082 for TLS.</span></span>

6.  <span data-ttu-id="da993-126">**SIP 전송 프로토콜**에서 피어가 사용 하는 전송 유형을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="da993-126">Under **SIP Transport Protocol**, click the transport type that the peer uses.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="da993-127">보안상의 이유로 TLS를 사용할 수 있는 중재 서버에 피어를 배포 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="da993-127">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span>

    
    </div>

7.  <span data-ttu-id="da993-128">**연결 된 중재 서버**에서이 피어의 루트 트렁크와 연결할 중재 서버 풀을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="da993-128">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this peer</span></span>

8.  <span data-ttu-id="da993-129">**연결 된 중재 서버 포트**에 중재 서버가 피어에서 SIP 메시지를 받을 수신 대기 포트를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="da993-129">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will receive SIP messages from the peer.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="da993-130">Lync Server 2013에서 여러 트렁크 지원을 사용 하는 경우 서로 다른 트렁크 이름을 사용 하는 두 개의 트렁크를 <STRONG>IP/PSTN 게이트웨이와</STRONG> 동일한 <STRONG>연결 된 중재 서버 포트</STRONG> 및 수신 대기 포트로 구성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="da993-130">With multiple trunk support in Lync Server 2013, two trunks with different trunk names cannot be configured with the same <STRONG>Associated Mediation Server port</STRONG> and <STRONG>Listening Port for IP/PSTN gateway</STRONG></span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="da993-131">Lync Server 2013의 트렁크 지원을 여러 개 사용 하는 경우 여러 피어와 통신 하기 위해 중재 서버에서 여러 SIP 신호 포트를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da993-131">With multiple trunk support in Lync Server 2013, multiple SIP signaling ports can be defined on the Mediation Server for communication with multiple peers.</span></span> <span data-ttu-id="da993-132">트렁크를 정의할 때 <STRONG>연결 된 중재 서버 포트</STRONG> 번호는 중재 서버에서 허용 하는 해당 프로토콜의 수신 대기 포트 범위 내에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da993-132">When defining a trunk, the <STRONG>Associated Mediation Server port</STRONG> number must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="da993-133">이 포트 범위는 Lync Server 2013 및 중재 서버 풀에 정의 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da993-133">This port range is defined under Lync Server 2013 and Mediation Server pools.</span></span> <span data-ttu-id="da993-134">관련 중재 서버 풀을 마우스 오른쪽 단추로 클릭 하 고 <STRONG>속성 편집</STRONG>을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="da993-134">Right-click the relevant Mediation Server pool, and select <STRONG>Edit Properties</STRONG>.</span></span> <span data-ttu-id="da993-135"><STRONG>수신 대기 포트</STRONG> 필드에서 포트 범위를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="da993-135">Specify the port range in the <STRONG>Listening ports</STRONG> field.</span></span>

    
    </div>

9.  <span data-ttu-id="da993-136">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="da993-136">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="da993-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="da993-137">See Also</span></span>


[<span data-ttu-id="da993-138">Lync Server 2013의 토폴로지 작성기에서 트렁크 수정</span><span class="sxs-lookup"><span data-stu-id="da993-138">Modify a trunk in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-modify-a-trunk-in-topology-builder.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

