---
title: 'Lync Server 2013: 토폴로지 작성기에서 게이트웨이 정의'
description: 'Lync Server 2013: 토폴로지 작성기에서 게이트웨이를 정의 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a gateway in Topology Builder
ms:assetid: 456e5a96-d9f6-42a6-862c-a69464391628
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425945(v=OCS.15)
ms:contentKeyID: 48184036
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f8bf09f06f54d8988c8c9a9e385ef251a960bd6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567804"
---
# <a name="define-a-gateway-in-topology-builder-in-lync-server-2013"></a><span data-ttu-id="b2a5b-103">Lync Server 2013의 토폴로지 작성기에서 게이트웨이 정의</span><span class="sxs-lookup"><span data-stu-id="b2a5b-103">Define a gateway in Topology Builder in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b2a5b-104">_**마지막으로 수정 된 항목:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="b2a5b-104">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="b2a5b-105">다음 단계에 따라 토폴로지 작성기를 사용 하 여 Enterprise Voice를 사용할 수 있도록 설정 된 사용자에 대해 중재 서버를 연결 하 여 공중 전화망 (PSTN)에 대 한 연결을 제공 하는 *피어* 를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2a5b-105">Follow these steps to use Topology Builder to define a *peer* with which you can associate a Mediation Server to provide connectivity to the public switched telephone network (PSTN) for users enabled for Enterprise Voice.</span></span> <span data-ttu-id="b2a5b-106">중재 서버에 대 한 피어는 SIP 트렁크를 구성 하 여 연결 하는 ITSP (인터넷 전화 통신 서비스 공급자)에 대 한 PSTN 게이트웨이, IP PBX 또는 SBC (Session Border Controller) 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2a5b-106">A peer to the Mediation Server can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP) to which you connect by configuring a SIP trunk.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b2a5b-107">이 항목에서는 배포 설명서의 lync server <A href="lync-server-2013-publish-the-topology.md">2013</A> <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">2013에서 프런트 엔드 풀 또는 Standard edition server 정의 및 구성</A> 에 설명 된 대로 하나 이상의 내부 프런트 엔드 풀 또는 standard edition server를 배치 된 또는 독립 실행형 중재 서버를 사용 하 여 한 개 이상 중앙 사이트에 설정 했다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2a5b-107">This topic assumes that you have set up at least one internal Front End pool or Standard Edition server in at least one central site with a collocated or stand-alone Mediation Server, as described in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</A> and <A href="lync-server-2013-publish-the-topology.md">Publish the topology in Lync Server 2013</A> in the Deployment documentation.</span></span> <span data-ttu-id="b2a5b-108">이 항목에서는 인프라에서 lync server <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">2013의 Enterprise voice 용 소프트웨어 필수 구성</A> 요소에 설명 된 필수 구성 요소와 <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">lync Server 2013의 enterprise voice에 대 한 보안 및 구성 필수 구성 요소</A>를 참조 하는 것을 확인 한 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2a5b-108">This topic also assumes that you have verified that your infrastructure meets the prerequisites described in <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">Software prerequisites for Enterprise Voice in Lync Server 2013</A> and <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">Security and configuration prerequisites for Enterprise Voice in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-define-a-peer-for-the-mediation-server"></a><span data-ttu-id="b2a5b-109">중재 서버의 피어를 정의하려면</span><span class="sxs-lookup"><span data-stu-id="b2a5b-109">To Define a Peer for the Mediation Server</span></span>

1.  <span data-ttu-id="b2a5b-110">토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2a5b-110">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="b2a5b-111">Lync Server 2013, 사이트 이름, 공유 구성 요소에서 **PSTN 게이트웨이** 노드를 마우스 오른쪽 단추로 클릭 한 다음 **새 PSTN 게이트웨이**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2a5b-111">Under Lync Server 2013, your site name, Shared Components, right-click the **PSTN Gateways** node, and then click **New PSTN Gateway**.</span></span>
    
    <span data-ttu-id="b2a5b-112">![d898c3c1-8798-4b74-8f02-b994ef3db4c1](images/Gg425945.d898c3c1-8798-4b74-8f02-b994ef3db4c1(OCS.15).png "d898c3c1-8798-4b74-8f02-b994ef3db4c1")</span><span class="sxs-lookup"><span data-stu-id="b2a5b-112">![d898c3c1-8798-4b74-8f02-b994ef3db4c1](images/Gg425945.d898c3c1-8798-4b74-8f02-b994ef3db4c1(OCS.15).png "d898c3c1-8798-4b74-8f02-b994ef3db4c1")</span></span>

3.  <span data-ttu-id="b2a5b-113">**Define New IP/PSTN Gateway**에서 피어의 FQDN(정규화된 도메인 이름) 또는 IP 주소를 입력하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b2a5b-113">In **Define New IP/PSTN Gateway**, type the fully qualified domain name (FQDN) or IP address of the peer, and click **Next**.</span></span>
    
    <span data-ttu-id="b2a5b-114">![8017ba5e-41bc-48d4-97d9-fd306cd322b8](images/Gg425945.8017ba5e-41bc-48d4-97d9-fd306cd322b8(OCS.15).png "8017ba5e-41bc-48d4-97d9-fd306cd322b8")</span><span class="sxs-lookup"><span data-stu-id="b2a5b-114">![8017ba5e-41bc-48d4-97d9-fd306cd322b8](images/Gg425945.8017ba5e-41bc-48d4-97d9-fd306cd322b8(OCS.15).png "8017ba5e-41bc-48d4-97d9-fd306cd322b8")</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b2a5b-115">TLS (전송 계층 보안)를 전송 유형으로 지정 하는 경우 중재 서버 피어의 IP 주소 대신 FQDN을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2a5b-115">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span>

    
    </div>

4.  <span data-ttu-id="b2a5b-116">새 PSTN 게이트웨이의 IP 주소에 대한 수신 노드(IPv4 또는 IPv6)를 정의하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b2a5b-116">Define the listening mode (IPv4 or IPv6) of the IP address of your new PSTN gateway, and click **Next**.</span></span>
    
    <span data-ttu-id="b2a5b-117">![c7fc0d12-adc8-45a7-aca1-b376e1d2fcec](images/Gg425945.c7fc0d12-adc8-45a7-aca1-b376e1d2fcec(OCS.15).png "c7fc0d12-adc8-45a7-aca1-b376e1d2fcec")</span><span class="sxs-lookup"><span data-stu-id="b2a5b-117">![c7fc0d12-adc8-45a7-aca1-b376e1d2fcec](images/Gg425945.c7fc0d12-adc8-45a7-aca1-b376e1d2fcec(OCS.15).png "c7fc0d12-adc8-45a7-aca1-b376e1d2fcec")</span></span>

5.  <span data-ttu-id="b2a5b-118">PSTN 게이트웨이에 대한 *루트 트렁크*를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b2a5b-118">Define a *root trunk* for the PSTN gateway.</span></span> <span data-ttu-id="b2a5b-119">트렁크는 중재 서버와 튜플에 의해 고유 하 게 식별 되는 게이트웨이 간의 논리적 연결입니다.</span><span class="sxs-lookup"><span data-stu-id="b2a5b-119">A trunk is a logical connection between a Mediation Server and a gateway uniquely identified by the tuple.</span></span>
    
    <span data-ttu-id="b2a5b-120">{중재 서버 FQDN, 중재 서버 수신 대기 포트 (TLS 또는 TCP): 게이트웨이 IP 및 FQDN, 게이트웨이 수신 대기 포트}</span><span class="sxs-lookup"><span data-stu-id="b2a5b-120">{Mediation Server FQDN, Mediation Server listening port (TLS or TCP) : gateway IP and FQDN, gateway listening port}</span></span>
    
      - <span data-ttu-id="b2a5b-121">토폴로지 작성기에서 PSTN 게이트웨이를 정의할 때 토폴로지에 PSTN 게이트웨이를 성공적으로 추가 하려면 루트 트렁크를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2a5b-121">When defining a PSTN gateway in Topology Builder, you must define a root trunk to successfully add the PSTN gateway to your topology.</span></span>
    
      - <span data-ttu-id="b2a5b-122">연결된 PSTN 게이트웨이를 제거할 때까지는 루트 트렁크를 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b2a5b-122">The root trunk cannot be removed until the associated PSTN gateway is removed.</span></span>
    
    <span data-ttu-id="b2a5b-123">![3b030757-eb35-4616-bb6b-74ee67507e3d](images/Gg425945.3b030757-eb35-4616-bb6b-74ee67507e3d(OCS.15).png "3b030757-eb35-4616-bb6b-74ee67507e3d")</span><span class="sxs-lookup"><span data-stu-id="b2a5b-123">![3b030757-eb35-4616-bb6b-74ee67507e3d](images/Gg425945.3b030757-eb35-4616-bb6b-74ee67507e3d(OCS.15).png "3b030757-eb35-4616-bb6b-74ee67507e3d")</span></span>

6.  <span data-ttu-id="b2a5b-124">**IP/PSTN 게이트웨이의 수신 대기 포트**에서 게이트웨이, PBX 또는 SBC가 PSTN 게이트웨이의 루트 트렁크와 연결 될 중재 서버의 SIP 메시지에 대해 사용할 수신 대기 포트를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2a5b-124">Under **Listening Port for IP/PSTN Gateway**, type the listening port that the gateway, PBX, or SBC will use for SIP messages from the Mediation Server that will be associated with the root trunk of the PSTN gateway.</span></span> <span data-ttu-id="b2a5b-125">기본적으로 TCP(Transmission Control Protocol)의 경우 포트 5066, PSTN 게이트웨이, PBX 또는 SBC의 TLS(전송 계층 보안)의 경우 포트 5067이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2a5b-125">(By default, the ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS) on a PSTN gateway, PBX or SBC.</span></span> <span data-ttu-id="b2a5b-126">분기 사이트의 Sba (survivable 분기 기기에서 기본 포트는 TCP의 경우 5081이 고 TLS의 경우 5082입니다.</span><span class="sxs-lookup"><span data-stu-id="b2a5b-126">On a Survivable Branch Appliance at a branch site, the default ports are 5081 for TCP and 5082 for TLS.)</span></span>

7.  <span data-ttu-id="b2a5b-127">**SIP 전송 프로토콜**에서 피어가 사용하는 전송 유형을 클릭하고 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b2a5b-127">Under **SIP Transport Protocol**, click the transport type that the peer uses, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b2a5b-128">보안상의 이유로 TLS를 사용할 수 있는 중재 서버에 피어를 배포 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b2a5b-128">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span>

    
    </div>

8.  <span data-ttu-id="b2a5b-129">**연결 된 중재 서버**에서이 PSTN 게이트웨이의 루트 트렁크와 연결할 중재 서버 풀을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2a5b-129">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this PSTN Gateway.</span></span>

9.  <span data-ttu-id="b2a5b-130">**연결 된 중재 서버 포트**에 중재 서버가 게이트웨이에서 SIP 메시지에 사용할 수신 대기 포트를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2a5b-130">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will use for SIP messages from the gateway.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b2a5b-131">Lync Server 2013의 트렁크 지원을 여러 개 사용 하는 경우 여러 PSTN 게이트웨이와 통신 하는 데 사용할 중재 서버에서 여러 SIP 신호 포트를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2a5b-131">With multiple trunk support in Lync Server 2013, multiple SIP signaling ports can be defined on the Mediation Server to be used for communication with multiple PSTN gateways.</span></span> <span data-ttu-id="b2a5b-132">트렁크를 정의할 때 연결 된 <STRONG>중재 서버 포트</STRONG> 는 중재 서버에서 허용 하는 해당 프로토콜의 수신 대기 포트 범위 내에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2a5b-132">When defining a trunk, the <STRONG>Associated Mediation Server port</STRONG> must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="b2a5b-133">이 포트 범위는 Lync Server 2013 및 중재 풀에 정의 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2a5b-133">This port range is defined under Lync Server 2013 and Mediation Pools.</span></span> <span data-ttu-id="b2a5b-134">관심 있는 중재 서버 풀을 마우스 오른쪽 단추로 클릭 하 고 <STRONG>속성 편집</STRONG>을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2a5b-134">Right-click the Mediation Server pool of interest, and select <STRONG>Edit Properties</STRONG>.</span></span> <span data-ttu-id="b2a5b-135"><STRONG>수신 대기 포트</STRONG> 필드에서 포트 범위를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b2a5b-135">Specify the port range in the <STRONG>Listening ports</STRONG> field.</span></span>

    
    </div>

10. <span data-ttu-id="b2a5b-136">**마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b2a5b-136">Click **Finish**.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b2a5b-137">이 단계를 마치기 전에 정의한 피어가 실행 중이고 사용자가 지정한 FQDN 또는 IP 주소를 사용 중인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b2a5b-137">Before you finish this step, be sure that the peer that you defined is running and using the FQDN or IP address that you specified.</span></span>



</div>

<span data-ttu-id="b2a5b-138">다음으로, 토폴로지에 피어를 추가 하려면 배포 설명서에서 [Lync Server 2013의 토폴로지 게시](lync-server-2013-publish-the-topology.md) 에 나와 있는 절차를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2a5b-138">Next, to add the peer to the topology, follow the procedures in [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md) in the Deployment documentation.</span></span> <span data-ttu-id="b2a5b-139">Lync Server를 실행 하는 서버에 대 한 파일을 설치 하는 데 데이터를 사용할 수 있도록 토폴로지 작성기를 사용 하 여 토폴로지를 작성 하거나 수정할 때마다 토폴로지를 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2a5b-139">You must publish your topology each time that you use Topology Builder to build or modify your topology, so that the data can be used to install the files for servers that are running Lync Server.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b2a5b-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b2a5b-140">See Also</span></span>


[<span data-ttu-id="b2a5b-141">Lync Server 2013의 토폴로지 작성기에서 트렁크 수정</span><span class="sxs-lookup"><span data-stu-id="b2a5b-141">Modify a trunk in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-modify-a-trunk-in-topology-builder.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

