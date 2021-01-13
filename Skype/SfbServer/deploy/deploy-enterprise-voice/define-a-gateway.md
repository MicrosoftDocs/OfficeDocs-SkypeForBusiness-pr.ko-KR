---
title: 비즈니스용 Skype 서버에서 토폴로지 작성기에서 게이트웨이 정의
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 456e5a96-d9f6-42a6-862c-a69464391628
description: '요약: 비즈니스용 Skype 서버의 토폴로지 작성기에서 PSTN 게이트웨이를 정의하는 방법을 설명하는 방법을 제공합니다.'
ms.openlocfilehash: be68c853cdcd530b05ad4b0949f722788e77d0df
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49837028"
---
# <a name="define-a-gateway-in-topology-builder-in-skype-for-business-server"></a><span data-ttu-id="5f332-103">비즈니스용 Skype 서버에서 토폴로지 작성기에서 게이트웨이 정의</span><span class="sxs-lookup"><span data-stu-id="5f332-103">Define a gateway in Topology Builder in Skype for Business Server</span></span>
 
<span data-ttu-id="5f332-104">**요약:** 비즈니스용 Skype 서버에서 토폴로지 작성기에서 PSTN 게이트웨이를 정의하는 방법에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="5f332-104">**Summary:** Learn how to define a PSTN gateway in Topology Builder in Skype for Business Server.</span></span>
  
<span data-ttu-id="5f332-105">토폴로지 작성기에서 다음 단계에 따라 중재 서버를 연결하여 중재 서버가 사용하도록 설정된 사용자에 대해 PSTN(공용 전화망)에 대한 연결을 제공할 수 있는 피어를 Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="5f332-105">Follow these steps to use Topology Builder to define a peer with which you can associate a Mediation Server to provide connectivity to the public switched telephone network (PSTN) for users enabled for Enterprise Voice.</span></span> <span data-ttu-id="5f332-106">중재 서버의 피어는 SIP 트렁크를 구성하여 연결하는 ITSP(인터넷 전화 통신 서비스 공급자)에 대한 PSTN 게이트웨이, IP-PBX 또는 SBC(Session Border Controller)일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f332-106">A peer to the Mediation Server can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP) to which you connect by configuring a SIP trunk.</span></span>
  
### <a name="to-define-a-peer-for-the-mediation-server"></a><span data-ttu-id="5f332-107">중재 서버의 피어를 정의하기 위해</span><span class="sxs-lookup"><span data-stu-id="5f332-107">To define a peer for the Mediation Server</span></span>

1. <span data-ttu-id="5f332-108">토폴로지 작성기 시작: **시작,** 모든 **프로그램,** 비즈니스용 **Skype 서버 2015를** 클릭한 다음 비즈니스용 **Skype 서버 2015Topology Builder를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5f332-108">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="5f332-109">비즈니스용 Skype 서버의 사이트 이름, 공유 구성 요소에서 **PSTN** 게이트웨이 노드를 마우스 오른쪽 단추로 클릭한 다음 **새 PSTN** 게이트웨이를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5f332-109">Under Skype for Business Server, your site name, Shared Components, right-click the **PSTN Gateways** node, and then click **New PSTN Gateway**.</span></span>
3. <span data-ttu-id="5f332-110">**Define New IP/PSTN Gateway** 에서 피어의 FQDN(정규화된 도메인 이름) 또는 IP 주소를 입력하고 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5f332-110">In **Define New IP/PSTN Gateway**, type the fully qualified domain name (FQDN) or IP address of the peer, and click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5f332-111">TLS(전송 계층 보안)를 전송 유형으로 지정하는 경우 중재 서버 피어의 IP 주소 대신 FQDN을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f332-111">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span> 
  
4. <span data-ttu-id="5f332-112">새 PSTN 게이트웨이의 IP 주소에 대한 수신 노드(IPv4 또는 IPv6)를 정의하고 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5f332-112">Define the listening mode (IPv4 or IPv6) of the IP address of your new PSTN gateway, and click **Next**.</span></span>

5. <span data-ttu-id="5f332-113">PSTN 게이트웨이에 대한 루트 트렁크를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5f332-113">Define a root trunk for the PSTN gateway.</span></span> <span data-ttu-id="5f332-114">트렁크는 중재 서버와 튜플로 고유하게 식별되는 게이트웨이 간의 논리적 연결입니다.</span><span class="sxs-lookup"><span data-stu-id="5f332-114">A trunk is a logical connection between a Mediation Server and a gateway uniquely identified by the tuple.</span></span>
    
    <span data-ttu-id="5f332-115">{중재 서버 FQDN, 중재 서버 수신 포트(TLS 또는 TCP) : 게이트웨이 IP 및 FQDN, 게이트웨이 수신 포트}</span><span class="sxs-lookup"><span data-stu-id="5f332-115">{Mediation Server FQDN, Mediation Server listening port (TLS or TCP) : gateway IP and FQDN, gateway listening port}</span></span>
    
     - <span data-ttu-id="5f332-116">토폴로지 작성기에서 PSTN 게이트웨이를 정의할 때 PSTN 게이트웨이를 토폴로지에 성공적으로 추가하려면 루트 트렁크를 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f332-116">When defining a PSTN gateway in Topology Builder, you must define a root trunk to successfully add the PSTN gateway to your topology.</span></span>
    
     - <span data-ttu-id="5f332-117">연결된 PSTN 게이트웨이를 제거할 때까지는 루트 트렁크를 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5f332-117">The root trunk cannot be removed until the associated PSTN gateway is removed.</span></span>
    
6. <span data-ttu-id="5f332-118">**IP/PSTN** 게이트웨이용 수신 포트 아래에 게이트웨이, PBX 또는 SBC가 PSTN 게이트웨이의 루트 트렁크와 연결될 중재 서버의 SIP 메시지에 사용할 수신 포트를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="5f332-118">Under **Listening Port for IP/PSTN Gateway**, type the listening port that the gateway, PBX, or SBC will use for SIP messages from the Mediation Server that will be associated with the root trunk of the PSTN gateway.</span></span> <span data-ttu-id="5f332-119">기본적으로 TCP(Transmission Control Protocol)의 경우 포트 5066, PSTN 게이트웨이, PBX 또는 SBC의 TLS(전송 계층 보안)의 경우 포트 5067이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f332-119">(By default, the ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS) on a PSTN gateway, PBX or SBC.</span></span> <span data-ttu-id="5f332-120">분기 사이트의 Survivable Branch Appliance에서 기본 포트는 TCP의 경우 5081, TLS의 경우 5082입니다.</span><span class="sxs-lookup"><span data-stu-id="5f332-120">On a Survivable Branch Appliance at a branch site, the default ports are 5081 for TCP and 5082 for TLS.)</span></span>
    
7. <span data-ttu-id="5f332-121">**SIP 전송 프로토콜** 에서 피어가 사용하는 전송 유형을 클릭하고 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5f332-121">Under **SIP Transport Protocol**, click the transport type that the peer uses, and then click **OK**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5f332-122">보안상의 이유로 TLS를 사용할 수 있는 중재 서버에 피어를 배포하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5f332-122">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span> 
  
8. <span data-ttu-id="5f332-123">연결된 **중재** 서버에서 이 PSTN 게이트웨이의 루트 트렁크와 연결하기 위해 중재 서버 풀을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5f332-123">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this PSTN Gateway.</span></span>
    
9. <span data-ttu-id="5f332-124">연결된 중재 서버 **포트에서** 중재 서버가 게이트웨이의 SIP 메시지에 사용할 수신 포트를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="5f332-124">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will use for SIP messages from the gateway.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5f332-125">비즈니스용 Skype 서버에서 여러 트렁크를 지원하면 중재 서버에서 여러 PSTN 게이트웨이와의 통신을 위해 여러 SIP 신호 포트를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f332-125">With multiple trunk support in Skype for Business Server, you can define multiple SIP signaling ports on the Mediation Server for communication with multiple PSTN gateways.</span></span> <span data-ttu-id="5f332-126">트렁크를 정의할 때  연결된 중재 서버 포트는 중재 서버에서 허용하는 각 프로토콜에 대한 수신 포트 범위 내에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f332-126">When defining a trunk, the **Associated Mediation Server port** must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="5f332-127">이 포트 범위는 비즈니스용 Skype 서버 및 중재 풀에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f332-127">This port range is defined under Skype for Business Server and Mediation Pools.</span></span> <span data-ttu-id="5f332-128">원하는 중재 서버 풀을 마우스 오른쪽 단추로 클릭하고 속성 **편집을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5f332-128">Right-click the Mediation Server pool of interest, and select **Edit Properties**.</span></span> <span data-ttu-id="5f332-129">**수신 대기 포트** 필드에서 포트 범위를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5f332-129">Specify the port range in the **Listening ports** field.</span></span>
  
10. <span data-ttu-id="5f332-130">정의한 피어가 실행 중이고 지정한 FQDN 또는 IP 주소를 사용하는지 확인</span><span class="sxs-lookup"><span data-stu-id="5f332-130">Be sure that the peer you defined is running and using the FQDN or IP address that you specified.</span></span> <span data-ttu-id="5f332-131">그런 다음 **마쳤습니다.**</span><span class="sxs-lookup"><span data-stu-id="5f332-131">Then click **Finish**.</span></span>
    
11. <span data-ttu-id="5f332-132">비즈니스용 Skype 서버 노드를 마우스 오른쪽 **단추로** 클릭한 다음 토폴로지 **게시를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5f332-132">Right-click the **Skype for Business Server** node, and then click **Publish Topology**.</span></span>
    

