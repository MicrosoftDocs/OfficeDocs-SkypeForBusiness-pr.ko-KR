---
title: 'Lync Server 2013: 토폴로지 작성기에서 게이트웨이 정의'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define a gateway in Topology Builder
ms:assetid: 456e5a96-d9f6-42a6-862c-a69464391628
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425945(v=OCS.15)
ms:contentKeyID: 48184036
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c9e57ad4e3d8c1692731bcfd4a56dc5c3d05bda
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979742"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-gateway-in-topology-builder-in-lync-server-2013"></a><span data-ttu-id="4ef2a-102">Lync Server 2013의 토폴로지 작성기에서 게이트웨이 정의</span><span class="sxs-lookup"><span data-stu-id="4ef2a-102">Define a gateway in Topology Builder in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4ef2a-103">_**마지막으로 수정한 주제:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="4ef2a-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="4ef2a-104">다음 단계에 따라 토폴로지 작성기를 사용 하 여 엔터프라이즈 음성에 대해 사용 하도록 설정 된 사용자의 PSTN (공개 교환 전화 네트워크)에 대 한 연결을 제공 하기 위해 중재 서버를 연결할 수 있는 *피어* 를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ef2a-104">Follow these steps to use Topology Builder to define a *peer* with which you can associate a Mediation Server to provide connectivity to the public switched telephone network (PSTN) for users enabled for Enterprise Voice.</span></span> <span data-ttu-id="4ef2a-105">중재 서버에 대 한 피어는 PSTN 게이트웨이, IP-PBX 또는 SIP 트렁크를 구성 하 여 연결 하는 인터넷 통신 서비스 공급자 (ITSP)에 대 한 SBC (세션 경계 컨트롤러) 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ef2a-105">A peer to the Mediation Server can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP) to which you connect by configuring a SIP trunk.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4ef2a-106">이 항목에서는 <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Lync server 2013의 프런트 엔드 풀 또는 Standard edition Server 정의 및 구성</A> 에서 설명한 대로 하나 이상의 내부 프런트 엔드 풀 또는 standard edition server를 collocated 또는 독립 실행형 중재 서버로 설정 했다고 가정 하 고 배포 설명서의 <A href="lync-server-2013-publish-the-topology.md">lync server 2013에서 토폴로지를 게시</A> 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ef2a-106">This topic assumes that you have set up at least one internal Front End pool or Standard Edition server in at least one central site with a collocated or stand-alone Mediation Server, as described in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</A> and <A href="lync-server-2013-publish-the-topology.md">Publish the topology in Lync Server 2013</A> in the Deployment documentation.</span></span> <span data-ttu-id="4ef2a-107">이 항목에서는 사용자가 인프라에서 <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">Lync server 2013의 Enterprise voice 용 소프트웨어 필수 구성</A> 요소에 설명 된 필수 구성 요소와 <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">lync Server 2013의 enterprise voice에 대 한 보안 및 구성 선행</A>조건을 충족 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ef2a-107">This topic also assumes that you have verified that your infrastructure meets the prerequisites described in <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">Software prerequisites for Enterprise Voice in Lync Server 2013</A> and <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">Security and configuration prerequisites for Enterprise Voice in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-define-a-peer-for-the-mediation-server"></a><span data-ttu-id="4ef2a-108">중재 서버용 피어를 정의 하려면</span><span class="sxs-lookup"><span data-stu-id="4ef2a-108">To Define a Peer for the Mediation Server</span></span>

1.  <span data-ttu-id="4ef2a-109">토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ef2a-109">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="4ef2a-110">Lync Server 2013, 사이트 이름, 공유 구성 요소에서 **PSTN 게이트웨이** 노드를 마우스 오른쪽 단추로 클릭 한 다음 **새 pstn 게이트웨이**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ef2a-110">Under Lync Server 2013, your site name, Shared Components, right-click the **PSTN Gateways** node, and then click **New PSTN Gateway**.</span></span>
    
    <span data-ttu-id="4ef2a-111">![d898c3c1-8798-4b74-8f02-b994ef3db4c1](images/Gg425945.d898c3c1-8798-4b74-8f02-b994ef3db4c1(OCS.15).png "d898c3c1-8798-4b74-8f02-b994ef3db4c1")</span><span class="sxs-lookup"><span data-stu-id="4ef2a-111">![d898c3c1-8798-4b74-8f02-b994ef3db4c1](images/Gg425945.d898c3c1-8798-4b74-8f02-b994ef3db4c1(OCS.15).png "d898c3c1-8798-4b74-8f02-b994ef3db4c1")</span></span>

3.  <span data-ttu-id="4ef2a-112">**새 IP/PSTN 게이트웨이 정의**에서 피어의 FQDN (정규화 된 도메인 이름) 또는 IP 주소를 입력 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ef2a-112">In **Define New IP/PSTN Gateway**, type the fully qualified domain name (FQDN) or IP address of the peer, and click **Next**.</span></span>
    
    <span data-ttu-id="4ef2a-113">![8017ba5e-41bc-48d4-97d9-fd306cd322b8](images/Gg425945.8017ba5e-41bc-48d4-97d9-fd306cd322b8(OCS.15).png "8017ba5e-41bc-48d4-97d9-fd306cd322b8")</span><span class="sxs-lookup"><span data-stu-id="4ef2a-113">![8017ba5e-41bc-48d4-97d9-fd306cd322b8](images/Gg425945.8017ba5e-41bc-48d4-97d9-fd306cd322b8(OCS.15).png "8017ba5e-41bc-48d4-97d9-fd306cd322b8")</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4ef2a-114">전송 형식으로 TLS (전송 계층 보안)를 지정 하는 경우 중재 서버 피어의 피어 IP 주소 대신 FQDN을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ef2a-114">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span>

    
    </div>

4.  <span data-ttu-id="4ef2a-115">새 PSTN 게이트웨이의 IP 주소에 대 한 수신 모드 (ipv4 또는 Ipv6)를 정의 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ef2a-115">Define the listening mode (IPv4 or IPv6) of the IP address of your new PSTN gateway, and click **Next**.</span></span>
    
    <span data-ttu-id="4ef2a-116">![c7fc0d12-adc8-45a7-aca1-b376e1d2fcec](images/Gg425945.c7fc0d12-adc8-45a7-aca1-b376e1d2fcec(OCS.15).png "c7fc0d12-adc8-45a7-aca1-b376e1d2fcec")</span><span class="sxs-lookup"><span data-stu-id="4ef2a-116">![c7fc0d12-adc8-45a7-aca1-b376e1d2fcec](images/Gg425945.c7fc0d12-adc8-45a7-aca1-b376e1d2fcec(OCS.15).png "c7fc0d12-adc8-45a7-aca1-b376e1d2fcec")</span></span>

5.  <span data-ttu-id="4ef2a-117">PSTN 게이트웨이에 대 한 *루트 트렁크* 를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ef2a-117">Define a *root trunk* for the PSTN gateway.</span></span> <span data-ttu-id="4ef2a-118">트렁크는 중재 서버와 튜플에 의해 고유 하 게 식별 되는 게이트웨이 간의 논리적 연결입니다.</span><span class="sxs-lookup"><span data-stu-id="4ef2a-118">A trunk is a logical connection between a Mediation Server and a gateway uniquely identified by the tuple.</span></span>
    
    <span data-ttu-id="4ef2a-119">{중재 서버 FQDN, 중재 서버 수신 포트 (TLS 또는 TCP): 게이트웨이 IP 및 FQDN, 게이트웨이 수신 포트}</span><span class="sxs-lookup"><span data-stu-id="4ef2a-119">{Mediation Server FQDN, Mediation Server listening port (TLS or TCP) : gateway IP and FQDN, gateway listening port}</span></span>
    
      - <span data-ttu-id="4ef2a-120">토폴로지 작성기에서 PSTN 게이트웨이를 정의 하는 경우에는 토폴로지에 PSTN 게이트웨이를 성공적으로 추가 하기 위해 루트 트렁크를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ef2a-120">When defining a PSTN gateway in Topology Builder, you must define a root trunk to successfully add the PSTN gateway to your topology.</span></span>
    
      - <span data-ttu-id="4ef2a-121">연결 된 PSTN 게이트웨이를 제거할 때까지 루트 트렁크를 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4ef2a-121">The root trunk cannot be removed until the associated PSTN gateway is removed.</span></span>
    
    <span data-ttu-id="4ef2a-122">![3b030757-eb35-4616-bb6b-74ee67507e3d](images/Gg425945.3b030757-eb35-4616-bb6b-74ee67507e3d(OCS.15).png "3b030757-eb35-4616-bb6b-74ee6e3d")</span><span class="sxs-lookup"><span data-stu-id="4ef2a-122">![3b030757-eb35-4616-bb6b-74ee67507e3d](images/Gg425945.3b030757-eb35-4616-bb6b-74ee67507e3d(OCS.15).png "3b030757-eb35-4616-bb6b-74ee67507e3d")</span></span>

6.  <span data-ttu-id="4ef2a-123">**IP/PSTN 게이트웨이의 수신 대기 포트**에서 게이트웨이, PBX 또는 SBC가 PSTN 게이트웨이의 루트 트렁크와 연결 되는 조정 서버의 SIP 메시지에 사용할 수신 대기 포트를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ef2a-123">Under **Listening Port for IP/PSTN Gateway**, type the listening port that the gateway, PBX, or SBC will use for SIP messages from the Mediation Server that will be associated with the root trunk of the PSTN gateway.</span></span> <span data-ttu-id="4ef2a-124">(기본적으로 포트는 TCP (전송 제어 프로토콜) 용 5066 이며 PSTN 게이트웨이, PBX 또는 SBC의 TLS (전송 계층 보안) 용 5067입니다.</span><span class="sxs-lookup"><span data-stu-id="4ef2a-124">(By default, the ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS) on a PSTN gateway, PBX or SBC.</span></span> <span data-ttu-id="4ef2a-125">지사 사이트의 Survivable Branch 기기에서 기본 포트는 TCP 용 5081이 고 TLS의 경우 5082입니다.</span><span class="sxs-lookup"><span data-stu-id="4ef2a-125">On a Survivable Branch Appliance at a branch site, the default ports are 5081 for TCP and 5082 for TLS.)</span></span>

7.  <span data-ttu-id="4ef2a-126">**SIP 전송 프로토콜**에서 피어가 사용 하는 전송 유형을 클릭 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ef2a-126">Under **SIP Transport Protocol**, click the transport type that the peer uses, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4ef2a-127">보안상의 이유로 TLS를 사용할 수 있는 중재 서버에 피어를 배포 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4ef2a-127">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span>

    
    </div>

8.  <span data-ttu-id="4ef2a-128">**연결 된 중재 서버**에서이 PSTN 게이트웨이의 루트 트렁크와 연결할 중재 서버 풀을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ef2a-128">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this PSTN Gateway.</span></span>

9.  <span data-ttu-id="4ef2a-129">**연결 된 중재 서버 포트**에 중재 서버가 게이트웨이에서 SIP 메시지에 사용할 수신 대기 포트를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ef2a-129">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will use for SIP messages from the gateway.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4ef2a-130">Lync Server 2013의 여러 트렁크 지원 기능을 사용 하면 여러 PSTN 게이트웨이와 통신 하는 데 사용할 중재 서버에서 여러 개의 SIP 신호 포트를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ef2a-130">With multiple trunk support in Lync Server 2013, multiple SIP signaling ports can be defined on the Mediation Server to be used for communication with multiple PSTN gateways.</span></span> <span data-ttu-id="4ef2a-131">트렁크를 정의할 때 <STRONG>연결 된 중재 서버 포트</STRONG> 는 중재 서버에서 허용 하는 각 프로토콜의 수신 대기 포트 범위 내에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ef2a-131">When defining a trunk, the <STRONG>Associated Mediation Server port</STRONG> must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="4ef2a-132">이 포트 범위는 Lync Server 2013 및 중재 풀 아래에 정의 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ef2a-132">This port range is defined under Lync Server 2013 and Mediation Pools.</span></span> <span data-ttu-id="4ef2a-133">관심 있는 중재 서버 풀을 마우스 오른쪽 단추로 클릭 하 고 <STRONG>속성 편집</STRONG>을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ef2a-133">Right-click the Mediation Server pool of interest, and select <STRONG>Edit Properties</STRONG>.</span></span> <span data-ttu-id="4ef2a-134"><STRONG>수신 대기 포트</STRONG> 필드에 포트 범위를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ef2a-134">Specify the port range in the <STRONG>Listening ports</STRONG> field.</span></span>

    
    </div>

10. <span data-ttu-id="4ef2a-135">**마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4ef2a-135">Click **Finish**.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4ef2a-136">이 단계를 마치기 전에 정의한 피어가 실행 중이 고 지정한 FQDN 또는 IP 주소를 사용 하 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ef2a-136">Before you finish this step, be sure that the peer that you defined is running and using the FQDN or IP address that you specified.</span></span>



</div>

<span data-ttu-id="4ef2a-137">다음으로,이 피어를 토폴로지에 추가 하려면 배포 설명서의 [Lync Server 2013에서 토폴로지 게시](lync-server-2013-publish-the-topology.md) 의 절차를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="4ef2a-137">Next, to add the peer to the topology, follow the procedures in [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md) in the Deployment documentation.</span></span> <span data-ttu-id="4ef2a-138">Lync Server를 실행 하는 서버에 대 한 파일을 설치 하는 데 데이터를 사용할 수 있도록 토폴로지 작성기를 사용 하 여 토폴로지를 빌드하거나 수정할 때마다 토폴로지를 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ef2a-138">You must publish your topology each time that you use Topology Builder to build or modify your topology, so that the data can be used to install the files for servers that are running Lync Server.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4ef2a-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4ef2a-139">See Also</span></span>


[<span data-ttu-id="4ef2a-140">Lync Server 2013의 토폴로지 작성기에서 트렁크 수정</span><span class="sxs-lookup"><span data-stu-id="4ef2a-140">Modify a trunk in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-modify-a-trunk-in-topology-builder.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

