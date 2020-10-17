---
title: 'Lync Server 2013: SIP 트렁크 배포 검사 목록'
description: 'Lync Server 2013: SIP 트렁크 배포 검사 목록'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIP trunk deployment checklist
ms:assetid: 94f4f03e-19d5-4198-92be-e4076dbb959a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398755(v=OCS.15)
ms:contentKeyID: 48184891
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbab9647a7146b2478317ab6c020969506f9c0ef
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559044"
---
# <a name="sip-trunk-deployment-checklist-for-lync-server-2013"></a><span data-ttu-id="988b3-103">Lync Server 2013에 대 한 SIP 트렁크 배포 검사 목록</span><span class="sxs-lookup"><span data-stu-id="988b3-103">SIP trunk deployment checklist for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="988b3-104">_**마지막으로 수정 된 항목:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="988b3-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="988b3-105">SIP 트렁크를 배포하기 전에 사용자와 사용자의 서비스 공급자는 각 SIP 트렁크 끝점에 대한 기본 연결 정보를 교환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="988b3-105">Before you can deploy a SIP trunk, you and your service provider must exchange some basic connection information about your respective SIP trunk endpoints.</span></span>

<span data-ttu-id="988b3-106">연결할 각 ITSP 게이트웨이에 대한 다음 정보를 얻도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="988b3-106">Get the following information for each ITSP gateway that you will connect to:</span></span>

  - <span data-ttu-id="988b3-107">IP 주소</span><span class="sxs-lookup"><span data-stu-id="988b3-107">IP address</span></span>

  - <span data-ttu-id="988b3-108">FQDN(정규화된 도메인 이름)</span><span class="sxs-lookup"><span data-stu-id="988b3-108">Fully qualified domain name (FQDN)</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="988b3-109">서비스 공급자가 둘 이상의 ITSP 게이트웨이에 연결하도록 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="988b3-109">The service provider may ask you to connect to more than one ITSP gateway.</span></span> <span data-ttu-id="988b3-110">이 경우 각 ITSP 게이트웨이와 풀의 각 중재 서버 사이에 연결을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="988b3-110">In that case, you must configure a connection between each ITSP gateway and each Mediation Server in your pool.</span></span>



</div>

<span data-ttu-id="988b3-111">서비스 공급자에게 제공하는 정보는 SIP 트렁크 연결 유형에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="988b3-111">The information you give to your service provider depends on your SIP trunk connection type:</span></span>

  - <span data-ttu-id="988b3-112">MPLS(Multiprotocol Label Switching) 또는 사설망 연결의 경우 ITSP에 경계 네트워크(DMZ, 완충 지역 및 스크린된 서브넷이라고도 함)에 있는 라우터의 공개적으로 라우팅 가능한 IP 주소를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="988b3-112">For Multiprotocol Label Switching (MPLS) or private network connections, give the ITSP the publicly routable IP Address of the router in your perimeter network (also known as DMZ, demilitarized zone, and screened subnet).</span></span> <span data-ttu-id="988b3-113">ITSP의 게이트웨이나 SBC(세션 경계 컨트롤러)가 이 주소에 연결할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="988b3-113">Verify that the gateway or Session Border Controller (SBC) at the ITSP can reach this address.</span></span> <span data-ttu-id="988b3-114">또한 ITSP에 중재 서버의 FQDN을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="988b3-114">Also give the ITSP the FQDN of your Mediation Server.</span></span>

  - <span data-ttu-id="988b3-115">VPN(가상 사설망) 연결의 경우 ITSP에 VPN 서버의 IP 주소를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="988b3-115">For virtual private network (VPN) connections, give the ITSP the IP address of your VPN server.</span></span>

<div>

## <a name="certificate-considerations"></a><span data-ttu-id="988b3-116">인증서 고려 사항</span><span class="sxs-lookup"><span data-stu-id="988b3-116">Certificate Considerations</span></span>

<span data-ttu-id="988b3-117">SIP 트렁크에 인증서가 필요한지를 확인하려면 ITSP에 프로토콜 지원에 대해 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="988b3-117">To determine whether you need a certificate for SIP trunking, check with your ITSP about protocol support:</span></span>

1.  <span data-ttu-id="988b3-118">ITSP가 TCP(Transmission Control Protocol)만 지원하는 경우 인증서가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="988b3-118">If your ITSP supports Transmission Control Protocol (TCP) only, you do not need a certificate.</span></span>

2.  <span data-ttu-id="988b3-119">ITSP가 TLS(전송 계층 보안)를 지원하는 경우 ITSP가 사용자에게 인증서를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="988b3-119">If your ITSP supports Transport Layer Security (TLS), the ITSP must provide you with a certificate.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="988b3-120">SIP는 VoIP(Voice over Internet Protocol) 통화에서 실제 음성 데이터를 관리하는 프로토콜인 RTP(Real-Time Transport Protocol) 또는 SRTP(Secure Real-time Transport Protocol)와 함께 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="988b3-120">SIP works in conjunction with real-time transport protocol (RTP) or secure real-time transport protocol (SRTP), the protocols that manage the actual voice data in Voice over Internet Protocol (VoIP) calls.</span></span>



</div>

</div>

<div>

## <a name="deployment-process"></a><span data-ttu-id="988b3-121">배포 프로세스</span><span class="sxs-lookup"><span data-stu-id="988b3-121">Deployment Process</span></span>

<span data-ttu-id="988b3-122">SIP 트렁크 연결의 Lync Server 쪽을 구현 하려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="988b3-122">To implement the Lync Server side of the SIP trunk connection, follow these steps:</span></span>

1.  <span data-ttu-id="988b3-123">Lync Server 토폴로지 작성기를 사용 하 여 SIP 도메인 토폴로지를 만들고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="988b3-123">Using the Lync Server Topology Builder, create and configure the SIP domain topology.</span></span> <span data-ttu-id="988b3-124">자세한 내용은 배포 설명서에서 " [Lync Server 2013에 대 한 토폴로지 작성기에서 토폴로지 정의 및 구성](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md) "을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="988b3-124">For details, see [Define and configure a topology in Topology Builder for Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md) in the Deployment documentation.</span></span>

2.  <span data-ttu-id="988b3-125">Lync Server 제어판을 사용 하 여 새 SIP 도메인에 대 한 음성 라우팅을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="988b3-125">Using the Lync Server Control Panel, configure voice routing for the new SIP domain.</span></span> <span data-ttu-id="988b3-126">자세한 내용은 배포 설명서에서 [Lync Server 2013의 트렁크 구성을](lync-server-2013-configuring-trunks.md) 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="988b3-126">For details, see [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md) in the Deployment documentation.</span></span>

3.  <span data-ttu-id="988b3-127">**Test-CsPstnOutboundCall** cmdlet을 사용하여 연결을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="988b3-127">Test connectivity by using the **Test-CsPstnOutboundCall** cmdlet.</span></span> <span data-ttu-id="988b3-128">자세한 내용은 lync server 관리 셸 설명서 또는 Lync Server Management Shell에 대 한 도움말을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="988b3-128">For details, see the Lync Server Management Shell documentation or Help for Lync Server Management Shell.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

