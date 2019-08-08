---
title: 비즈니스용 Skype 서버의 토폴로지 작성기에서 게이트웨이 정의
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 456e5a96-d9f6-42a6-862c-a69464391628
description: '요약: 비즈니스용 Skype 서버의 토폴로지 작성기에서 PSTN 게이트웨이를 정의 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 322c526c87c3a354f11fd0c906256b36e6df526e
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233533"
---
# <a name="define-a-gateway-in-topology-builder-in-skype-for-business-server"></a><span data-ttu-id="7106a-103">비즈니스용 Skype 서버의 토폴로지 작성기에서 게이트웨이 정의</span><span class="sxs-lookup"><span data-stu-id="7106a-103">Define a gateway in Topology Builder in Skype for Business Server</span></span>
 
<span data-ttu-id="7106a-104">**요약:** 비즈니스용 Skype 서버의 토폴로지 작성기에서 PSTN 게이트웨이를 정의 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="7106a-104">**Summary:** Learn how to define a PSTN gateway in Topology Builder in Skype for Business Server.</span></span>
  
<span data-ttu-id="7106a-105">다음 단계에 따라 토폴로지 작성기를 사용 하 여 엔터프라이즈 음성에 대해 사용 하도록 설정 된 사용자의 PSTN (공개 교환 전화 네트워크)에 대 한 연결을 제공 하기 위해 중재 서버를 연결할 수 있는 피어를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="7106a-105">Follow these steps to use Topology Builder to define a peer with which you can associate a Mediation Server to provide connectivity to the public switched telephone network (PSTN) for users enabled for Enterprise Voice.</span></span> <span data-ttu-id="7106a-106">중재 서버에 대 한 피어는 PSTN 게이트웨이, IP-PBX 또는 SIP 트렁크를 구성 하 여 연결 하는 인터넷 통신 서비스 공급자 (ITSP)에 대 한 SBC (세션 경계 컨트롤러) 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7106a-106">A peer to the Mediation Server can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP) to which you connect by configuring a SIP trunk.</span></span>
  
### <a name="to-define-a-peer-for-the-mediation-server"></a><span data-ttu-id="7106a-107">중재 서버용 피어를 정의 하려면</span><span class="sxs-lookup"><span data-stu-id="7106a-107">To define a peer for the Mediation Server</span></span>

1. <span data-ttu-id="7106a-108">토폴로지 작성기 시작: **시작**, **모든 프로그램**, **비즈니스용 skype 서버 2015**을 차례로 클릭 한 다음 비즈니스용 **skype server 2015topology Builder**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7106a-108">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="7106a-109">비즈니스용 Skype 서버, 사이트 이름, 공유 구성 요소에서 **PSTN 게이트웨이** 노드를 마우스 오른쪽 단추로 클릭 한 다음 **새 pstn 게이트웨이**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7106a-109">Under Skype for Business Server, your site name, Shared Components, right-click the **PSTN Gateways** node, and then click **New PSTN Gateway**.</span></span>
3. <span data-ttu-id="7106a-110">**새 IP/PSTN 게이트웨이 정의**에서 피어의 FQDN (정규화 된 도메인 이름) 또는 IP 주소를 입력 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7106a-110">In **Define New IP/PSTN Gateway**, type the fully qualified domain name (FQDN) or IP address of the peer, and click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7106a-111">전송 형식으로 TLS (전송 계층 보안)를 지정 하는 경우 중재 서버 피어의 피어 IP 주소 대신 FQDN을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7106a-111">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span> 
  
4. <span data-ttu-id="7106a-112">새 PSTN 게이트웨이의 IP 주소에 대 한 수신 모드 (ipv4 또는 Ipv6)를 정의 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7106a-112">Define the listening mode (IPv4 or IPv6) of the IP address of your new PSTN gateway, and click **Next**.</span></span>

5. <span data-ttu-id="7106a-113">PSTN 게이트웨이에 대 한 루트 트렁크를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="7106a-113">Define a root trunk for the PSTN gateway.</span></span> <span data-ttu-id="7106a-114">트렁크는 중재 서버와 튜플에 의해 고유 하 게 식별 되는 게이트웨이 간의 논리적 연결입니다.</span><span class="sxs-lookup"><span data-stu-id="7106a-114">A trunk is a logical connection between a Mediation Server and a gateway uniquely identified by the tuple.</span></span>
    
    <span data-ttu-id="7106a-115">{중재 서버 FQDN, 중재 서버 수신 포트 (TLS 또는 TCP): 게이트웨이 IP 및 FQDN, 게이트웨이 수신 포트}</span><span class="sxs-lookup"><span data-stu-id="7106a-115">{Mediation Server FQDN, Mediation Server listening port (TLS or TCP) : gateway IP and FQDN, gateway listening port}</span></span>
    
     - <span data-ttu-id="7106a-116">토폴로지 작성기에서 PSTN 게이트웨이를 정의 하는 경우에는 토폴로지에 PSTN 게이트웨이를 성공적으로 추가 하기 위해 루트 트렁크를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7106a-116">When defining a PSTN gateway in Topology Builder, you must define a root trunk to successfully add the PSTN gateway to your topology.</span></span>
    
     - <span data-ttu-id="7106a-117">연결 된 PSTN 게이트웨이를 제거할 때까지 루트 트렁크를 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7106a-117">The root trunk cannot be removed until the associated PSTN gateway is removed.</span></span>
    
6. <span data-ttu-id="7106a-118">**IP/PSTN 게이트웨이의 수신 대기 포트**에서 게이트웨이, PBX 또는 SBC가 PSTN 게이트웨이의 루트 트렁크와 연결 되는 조정 서버의 SIP 메시지에 사용할 수신 대기 포트를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="7106a-118">Under **Listening Port for IP/PSTN Gateway**, type the listening port that the gateway, PBX, or SBC will use for SIP messages from the Mediation Server that will be associated with the root trunk of the PSTN gateway.</span></span> <span data-ttu-id="7106a-119">(기본적으로 포트는 TCP (전송 제어 프로토콜) 용 5066 이며 PSTN 게이트웨이, PBX 또는 SBC의 TLS (전송 계층 보안) 용 5067입니다.</span><span class="sxs-lookup"><span data-stu-id="7106a-119">(By default, the ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS) on a PSTN gateway, PBX or SBC.</span></span> <span data-ttu-id="7106a-120">지사 사이트의 Survivable Branch 기기에서 기본 포트는 TCP 용 5081이 고 TLS의 경우 5082입니다.</span><span class="sxs-lookup"><span data-stu-id="7106a-120">On a Survivable Branch Appliance at a branch site, the default ports are 5081 for TCP and 5082 for TLS.)</span></span>
    
7. <span data-ttu-id="7106a-121">**SIP 전송 프로토콜**에서 피어가 사용 하는 전송 유형을 클릭 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7106a-121">Under **SIP Transport Protocol**, click the transport type that the peer uses, and then click **OK**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7106a-122">보안상의 이유로 TLS를 사용할 수 있는 중재 서버에 피어를 배포 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7106a-122">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span> 
  
8. <span data-ttu-id="7106a-123">**연결 된 중재 서버**에서이 PSTN 게이트웨이의 루트 트렁크와 연결할 중재 서버 풀을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7106a-123">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this PSTN Gateway.</span></span>
    
9. <span data-ttu-id="7106a-124">**연결 된 중재 서버 포트**에 중재 서버가 게이트웨이에서 SIP 메시지에 사용할 수신 대기 포트를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="7106a-124">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will use for SIP messages from the gateway.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7106a-125">비즈니스용 Skype Server의 여러 트렁크 지원 기능을 사용 하면 여러 PSTN 게이트웨이와 통신 하기 위해 중재 서버에서 여러 SIP 신호 포트를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7106a-125">With multiple trunk support in Skype for Business Server, you can define multiple SIP signaling ports on the Mediation Server for communication with multiple PSTN gateways.</span></span> <span data-ttu-id="7106a-126">트렁크를 정의할 때 **연결 된 중재 서버 포트** 는 중재 서버에서 허용 하는 각 프로토콜의 수신 대기 포트 범위 내에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7106a-126">When defining a trunk, the **Associated Mediation Server port** must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="7106a-127">이 포트 범위는 비즈니스용 Skype 서버 및 중재 풀에 정의 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7106a-127">This port range is defined under Skype for Business Server and Mediation Pools.</span></span> <span data-ttu-id="7106a-128">관심 있는 중재 서버 풀을 마우스 오른쪽 단추로 클릭 하 고 **속성 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7106a-128">Right-click the Mediation Server pool of interest, and select **Edit Properties**.</span></span> <span data-ttu-id="7106a-129">**수신 대기 포트** 필드에 포트 범위를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7106a-129">Specify the port range in the **Listening ports** field.</span></span>
  
10. <span data-ttu-id="7106a-130">정의한 피어가 실행 중이 고 지정한 FQDN 또는 IP 주소를 사용 하 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="7106a-130">Be sure that the peer you defined is running and using the FQDN or IP address that you specified.</span></span> <span data-ttu-id="7106a-131">그런 다음 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7106a-131">Then click **Finish**.</span></span>
    
11. <span data-ttu-id="7106a-132">**비즈니스용 Skype 서버** 노드를 마우스 오른쪽 단추로 클릭 한 다음 **토폴로지 게시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7106a-132">Right-click the **Skype for Business Server** node, and then click **Publish Topology**.</span></span>
    

