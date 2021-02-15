---
title: 비즈니스용 Skype 서버에서 토폴로지 작성기에서 추가 트렁크 정의
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
ms.assetid: e68b8377-50a2-452a-bf5c-910929e34236
description: '요약: 비즈니스용 Skype 서버의 토폴로지 작성기에서 중재 서버와 게이트웨이 피어 간에 추가 트렁크를 정의하는 방법을 설명하는 방법을 제공합니다.'
ms.openlocfilehash: 3aab744761420ab631f17e6b56391f1fab120ccf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49836998"
---
# <a name="define-additional-trunks-in-topology-builder-in-skype-for-business-server"></a><span data-ttu-id="0078c-103">비즈니스용 Skype 서버에서 토폴로지 작성기에서 추가 트렁크 정의</span><span class="sxs-lookup"><span data-stu-id="0078c-103">Define additional trunks in Topology Builder in Skype for Business Server</span></span>
 
<span data-ttu-id="0078c-104">**요약:** 비즈니스용 Skype 서버의 토폴로지 작성기에서 중재 서버와 게이트웨이 피어 간에 추가 트렁크를 정의하는 방법에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="0078c-104">**Summary:** Learn how to define an additional trunk between a Mediation Server and a gateway peer in Topology Builder in Skype for Business Server.</span></span>
  
<span data-ttu-id="0078c-105">다음 단계에 따라 피어를 중재 서버와 연결하기 위한 추가 트렁크를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0078c-105">Follow these steps to define an additional trunk to which you can associate a peer with a Mediation Server.</span></span> <span data-ttu-id="0078c-106">피어는 PSTN(Enterprise Voice 전화망)에 연결하여 사용자가 사용할 수 있도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0078c-106">A peer provides users enabled for Enterprise Voice with connectivity to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="0078c-107">피어는 ITSP(인터넷 전화 통신 서비스 공급자)에 대한 PSTN 게이트웨이, IP-PBX 또는 SBC(Session Border Controller)일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0078c-107">A peer can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP).</span></span>
  
<span data-ttu-id="0078c-108">트렁크는 중재 서버와 게이트웨이 간의 논리적 연결입니다.</span><span class="sxs-lookup"><span data-stu-id="0078c-108">A trunk is a logical connection between a Mediation Server and a gateway.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0078c-109">이 항목에서는 배포 설명서의 비즈니스용 [Skype](define-a-gateway.md) 서버의 토폴로지 작성기에서 게이트웨이 정의에 설명된 하나 이상의 배치된 중재 서버 또는 독립 실행형 중재 서버 또는 풀을 사용하여 PSTN 게이트웨이 및 루트 트렁크를 설정했다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="0078c-109">This topic assumes that you have setup a PSTN gateway and root trunk with at least one collocated or stand-alone Mediation Server or pool as described in [Define a gateway in Topology Builder in Skype for Business Server](define-a-gateway.md) in the Deployment documentation.</span></span>
  
### <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a><span data-ttu-id="0078c-110">중재 서버와 게이트웨이 피어 간에 추가 트렁크를 정의하기 위해</span><span class="sxs-lookup"><span data-stu-id="0078c-110">To define an additional trunk between a Mediation Server and a gateway peer</span></span>

1. <span data-ttu-id="0078c-111">토폴로지 작성기 시작: **시작,** 모든 **프로그램,** 비즈니스용 **Skype 서버 2015를** 클릭한 다음 비즈니스용 **Skype 서버 2015Topology Builder를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0078c-111">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="0078c-112">비즈니스용 Skype 서버의 사이트 **이름,** 공유 구성 요소에서 **트렁크** 노드를 마우스 오른쪽 단추로 클릭한 다음 **새 트렁크를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0078c-112">Under Skype for Business Server, your site name, **Shared Components**, right-click the **Trunks** node, and then click **New Trunk**.</span></span>
   1. <span data-ttu-id="0078c-113">새 **트렁크 정의에서** 트렁크를 고유하게 식별할 식별 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0078c-113">In **Define New Trunk**, specify a friendly name to uniquely identify the trunk.</span></span> <span data-ttu-id="0078c-114">이름이 같은 트렁크 두 개는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0078c-114">You cannot have two trunks with the same name.</span></span>
    
      > [!NOTE]
      > <span data-ttu-id="0078c-115">TLS(전송 계층 보안)를 전송 유형으로 지정하는 경우 중재 서버 피어의 IP 주소 대신 FQDN을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0078c-115">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span> 
  
3. <span data-ttu-id="0078c-116">연결된 **PSTN** 게이트웨이에서 이 트렁크와 연결되는 PSTN 게이트웨이 피어를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0078c-116">Under **Associated PSTN gateway**, select the PSTN gateway peer to associate with this trunk.</span></span>
    5. <span data-ttu-id="0078c-117">**PSTN** 게이트웨이용 수신 포트 아래에 피어(PSTN 게이트웨이, IP-PBX 또는 SBC)가 이 트렁크와 연결될 중재 서버에서 SIP 메시지를 받을 수신 포트를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0078c-117">Under **Listening Port for PSTN gateway**, type the listening port that the peer (PSTN gateway, IP-PBX, or SBC) will receive SIP messages from the Mediation Server that is to be associated with this trunk.</span></span> <span data-ttu-id="0078c-118">기본 피어 포트는 TCP(Transmission Control Protocol)의 경우 5066, TLS(전송 계층 보안)의 경우 5067입니다.</span><span class="sxs-lookup"><span data-stu-id="0078c-118">The default peer ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS).</span></span> <span data-ttu-id="0078c-119">기본 Survivable Branch Appliance 포트는 TCP의 경우 5081, TLS의 경우 5082입니다.</span><span class="sxs-lookup"><span data-stu-id="0078c-119">The default Survivable Branch Appliance ports are 5081 for TCP and 5082 for TLS.</span></span>
    
4. <span data-ttu-id="0078c-120">**SIP 전송 프로토콜 아래에서** 피어가 사용하는 전송 유형을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0078c-120">Under **SIP Transport Protocol**, click the transport type that the peer uses.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0078c-121">보안상의 이유로 TLS를 사용할 수 있는 중재 서버에 피어를 배포하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0078c-121">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span> 
  
5. <span data-ttu-id="0078c-122">연결된 **중재** 서버에서 이 피어의 루트 트렁크와 연결하기 위해 중재 서버 풀을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0078c-122">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this peer</span></span>
    
6. <span data-ttu-id="0078c-123">연결된 중재 서버 **포트에서** 중재 서버가 피어로부터 SIP 메시지를 받을 수신 포트를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0078c-123">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will receive SIP messages from the peer.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0078c-124">비즈니스용 Skype 서버에서 여러 트렁크가 지원되는 경우 서로 다른 트렁크 이름을 사용하는  두 트렁크를 **IP/PSTN** 게이트웨이에 대한 동일한 연결된 중재 서버 포트 및 수신 포트로 구성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0078c-124">With multiple trunk support in Skype for Business Server, two trunks with different trunk names cannot be configured with the same **Associated Mediation Server port** and **Listening Port for IP/PSTN gateway**</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="0078c-125">비즈니스용 Skype 서버에서 여러 트렁크를 지원하면 중재 서버에서 여러 피어와의 통신을 위해 여러 SIP 신호 포트를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0078c-125">With multiple trunk support in Skype for Business Server, multiple SIP signaling ports can be defined on the Mediation Server for communication with multiple peers.</span></span> <span data-ttu-id="0078c-126">트렁크를 정의할 때  연결된 중재 서버 포트 번호는 중재 서버에서 허용하는 각 프로토콜에 대한 수신 포트 범위 내에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0078c-126">When defining a trunk, the **Associated Mediation Server port** number must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="0078c-127">이 포트 범위는 비즈니스용 Skype 서버 및 중재 서버 풀에서 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="0078c-127">This port range is defined under Skype for Business Server and Mediation Server pools.</span></span> <span data-ttu-id="0078c-128">관련 중재 서버 풀을 마우스 오른쪽 단추로 클릭하고 속성 **편집을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0078c-128">Right-click the relevant Mediation Server pool, and select **Edit Properties**.</span></span> <span data-ttu-id="0078c-129">**수신 대기 포트** 필드에서 포트 범위를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0078c-129">Specify the port range in the **Listening ports** field.</span></span>
  
7. <span data-ttu-id="0078c-130">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0078c-130">Click **OK**.</span></span> 
    

