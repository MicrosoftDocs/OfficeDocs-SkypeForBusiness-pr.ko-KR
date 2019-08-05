---
title: 비즈니스용 Skype 서버의 토폴로지 작성기에 추가 trunks 정의
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e68b8377-50a2-452a-bf5c-910929e34236
description: '요약: 비즈니스용 Skype 서버의 토폴로지 작성기에서 중재 서버와 게이트웨이 피어 간의 추가 트렁크를 정의 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: de6cfd45c9e5f8440fcbcf6b6098a82edda752f0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197429"
---
# <a name="define-additional-trunks-in-topology-builder-in-skype-for-business-server"></a><span data-ttu-id="059e5-103">비즈니스용 Skype 서버의 토폴로지 작성기에 추가 trunks 정의</span><span class="sxs-lookup"><span data-stu-id="059e5-103">Define additional trunks in Topology Builder in Skype for Business Server</span></span>
 
<span data-ttu-id="059e5-104">**요약:** 비즈니스용 Skype 서버의 토폴로지 작성기에서 중재 서버와 게이트웨이 피어 간의 추가 트렁크를 정의 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="059e5-104">**Summary:** Learn how to define an additional trunk between a Mediation Server and a gateway peer in Topology Builder in Skype for Business Server.</span></span>
  
<span data-ttu-id="059e5-105">이 단계에 따라 피어를 중재 서버와 연결할 수 있는 추가 트렁크를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="059e5-105">Follow these steps to define an additional trunk to which you can associate a peer with a Mediation Server.</span></span> <span data-ttu-id="059e5-106">피어는 PSTN (공개 통신 네트워크) 연결을 통해 엔터프라이즈 음성을 사용할 수 있는 사용자를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="059e5-106">A peer provides users enabled for Enterprise Voice with connectivity to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="059e5-107">피어는 ITSP (인터넷 통신 서비스 공급자)에 대 한 PSTN 게이트웨이, IP PBX 또는 SBC (세션 경계 컨트롤러) 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="059e5-107">A peer can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP).</span></span>
  
<span data-ttu-id="059e5-108">트렁크는 중재 서버와 게이트웨이 간의 논리적 연결입니다.</span><span class="sxs-lookup"><span data-stu-id="059e5-108">A trunk is a logical connection between a Mediation Server and a gateway.</span></span>
  
> [!NOTE]
> <span data-ttu-id="059e5-109">이 항목에서는 배포 설명서의 [비즈니스용 Skype 서버에서 토폴로지 작성기의 게이트웨이 정의](define-a-gateway.md) 에서 설명한 대로 하나 이상의 collocated 또는 독립 실행형 중재 서버 또는 풀을 사용 하 여 PSTN 게이트웨이 및 루트 트렁크를 설정 하는 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="059e5-109">This topic assumes that you have setup a PSTN gateway and root trunk with at least one collocated or stand-alone Mediation Server or pool as described in [Define a gateway in Topology Builder in Skype for Business Server](define-a-gateway.md) in the Deployment documentation.</span></span>
  
### <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a><span data-ttu-id="059e5-110">중재 서버와 게이트웨이 피어 간의 추가 트렁크를 정의 하려면</span><span class="sxs-lookup"><span data-stu-id="059e5-110">To define an additional trunk between a Mediation Server and a gateway peer</span></span>

1. <span data-ttu-id="059e5-111">토폴로지 작성기 시작: **시작**, **모든 프로그램**, **비즈니스용 skype 서버 2015**을 차례로 클릭 한 다음 비즈니스용 **skype server 2015topology Builder**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="059e5-111">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="059e5-112">비즈니스용 Skype 서버, 사이트 이름, **공유 구성 요소**에서 **Trunks** 노드를 마우스 오른쪽 단추로 클릭 한 다음 **새 트렁크**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="059e5-112">Under Skype for Business Server, your site name, **Shared Components**, right-click the **Trunks** node, and then click **New Trunk**.</span></span>
   1. <span data-ttu-id="059e5-113">**새 트렁크 정의**에서 트렁크를 고유 하 게 식별 하는 대화명을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="059e5-113">In **Define New Trunk**, specify a friendly name to uniquely identify the trunk.</span></span> <span data-ttu-id="059e5-114">두 개의 trunks 같은 이름을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="059e5-114">You cannot have two trunks with the same name.</span></span>
    
      > [!NOTE]
      > <span data-ttu-id="059e5-115">전송 형식으로 TLS (전송 계층 보안)를 지정 하는 경우 중재 서버 피어의 피어 IP 주소 대신 FQDN을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="059e5-115">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span> 
  
3. <span data-ttu-id="059e5-116">**연결 된 PSTN 게이트웨이에서**이 트렁크와 연결할 pstn 게이트웨이 피어를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="059e5-116">Under **Associated PSTN gateway**, select the PSTN gateway peer to associate with this trunk.</span></span>
    5. <span data-ttu-id="059e5-117">**Pstn 게이트웨이의 수신 대기 포트**에서 피어 (pstn 게이트웨이, IP-PBX 또는 SBC)가이 트렁크와 연결할 중재 서버에서 SIP 메시지를 수신 하는 수신 대기 포트를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="059e5-117">Under **Listening Port for PSTN gateway**, type the listening port that the peer (PSTN gateway, IP-PBX, or SBC) will receive SIP messages from the Mediation Server that is to be associated with this trunk.</span></span> <span data-ttu-id="059e5-118">기본 피어 포트는 TCP (전송 제어 프로토콜) 및 TLS (전송 계층 보안) 용 5067의 5066입니다.</span><span class="sxs-lookup"><span data-stu-id="059e5-118">The default peer ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS).</span></span> <span data-ttu-id="059e5-119">기본 Survivable Branch 기기 포트는 TCP 및 TLS 용 5082의 5081입니다.</span><span class="sxs-lookup"><span data-stu-id="059e5-119">The default Survivable Branch Appliance ports are 5081 for TCP and 5082 for TLS.</span></span>
    
4. <span data-ttu-id="059e5-120">**SIP 전송 프로토콜**에서 피어가 사용 하는 전송 유형을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="059e5-120">Under **SIP Transport Protocol**, click the transport type that the peer uses.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="059e5-121">보안상의 이유로 TLS를 사용할 수 있는 중재 서버에 피어를 배포 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="059e5-121">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span> 
  
5. <span data-ttu-id="059e5-122">**연결 된 중재 서버**에서이 피어의 루트 트렁크에 연결할 중재 서버 풀을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="059e5-122">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this peer</span></span>
    
6. <span data-ttu-id="059e5-123">**연결 된 중재 서버 포트**에서 중재 서버가 피어에서 SIP 메시지를 수신할 수신 대기 포트를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="059e5-123">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will receive SIP messages from the peer.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="059e5-124">비즈니스용 Skype 서버에서 여러 트렁크 지원 기능을 사용 하는 경우 두 개의 trunks 같은 **연결 된 중재 서버 포트** 와 **수신 대기 포트 (IP/PSTN 게이트웨이** )를 사용 하 여 다른 트렁크 이름을 구성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="059e5-124">With multiple trunk support in Skype for Business Server, two trunks with different trunk names cannot be configured with the same **Associated Mediation Server port** and **Listening Port for IP/PSTN gateway**</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="059e5-125">비즈니스용 Skype Server의 여러 트렁크 지원 기능을 사용 하면 여러 피어와 통신 하기 위해 중재 서버에서 여러 개의 SIP 신호 포트를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="059e5-125">With multiple trunk support in Skype for Business Server, multiple SIP signaling ports can be defined on the Mediation Server for communication with multiple peers.</span></span> <span data-ttu-id="059e5-126">트렁크를 정의할 때 **연결 된 중재 서버 포트** 번호는 중재 서버에서 허용 하는 해당 프로토콜에 대 한 수신 대기 포트 범위 내에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="059e5-126">When defining a trunk, the **Associated Mediation Server port** number must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="059e5-127">이 포트 범위는 비즈니스용 Skype 서버 및 중재 서버 풀에 정의 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="059e5-127">This port range is defined under Skype for Business Server and Mediation Server pools.</span></span> <span data-ttu-id="059e5-128">관련 중재 서버 풀을 마우스 오른쪽 단추로 클릭 하 고 **속성 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="059e5-128">Right-click the relevant Mediation Server pool, and select **Edit Properties**.</span></span> <span data-ttu-id="059e5-129">**수신 대기 포트** 필드에 포트 범위를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="059e5-129">Specify the port range in the **Listening ports** field.</span></span>
  
7. <span data-ttu-id="059e5-130">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="059e5-130">Click **OK**.</span></span> 
    

