---
title: 'Lync Server 2013: SIP 트렁크 배포 검사 목록'
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
ms.openlocfilehash: ef670fc4ae9e8a9acba3277a00fc0daf6ff766b3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764494"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sip-trunk-deployment-checklist-for-lync-server-2013"></a><span data-ttu-id="f3afc-102">Lync Server 2013에 대한 SIP 트렁크 배포 검사 목록</span><span class="sxs-lookup"><span data-stu-id="f3afc-102">SIP trunk deployment checklist for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f3afc-103">_**마지막으로 수정한 주제:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="f3afc-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="f3afc-104">SIP 트렁크를 배포 하기 전에, 귀하와 서비스 제공 업체는 해당 SIP 트렁크 끝점에 대 한 몇 가지 기본 연결 정보를 교환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3afc-104">Before you can deploy a SIP trunk, you and your service provider must exchange some basic connection information about your respective SIP trunk endpoints.</span></span>

<span data-ttu-id="f3afc-105">연결할 각 ITSP 게이트웨이에 대해 다음 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f3afc-105">Get the following information for each ITSP gateway that you will connect to:</span></span>

  - <span data-ttu-id="f3afc-106">IP 주소</span><span class="sxs-lookup"><span data-stu-id="f3afc-106">IP address</span></span>

  - <span data-ttu-id="f3afc-107">FQDN (정규화 된 도메인 이름)</span><span class="sxs-lookup"><span data-stu-id="f3afc-107">Fully qualified domain name (FQDN)</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f3afc-108">서비스 공급자가 두 개 이상의 ITSP 게이트웨이에 연결 하도록 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3afc-108">The service provider may ask you to connect to more than one ITSP gateway.</span></span> <span data-ttu-id="f3afc-109">이 경우 각 ITSP 게이트웨이와 풀의 각 중재 서버 간에 연결을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3afc-109">In that case, you must configure a connection between each ITSP gateway and each Mediation Server in your pool.</span></span>



</div>

<span data-ttu-id="f3afc-110">서비스 공급자에 게 제공 하는 정보는 사용자의 SIP 트렁크 연결 형식에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="f3afc-110">The information you give to your service provider depends on your SIP trunk connection type:</span></span>

  - <span data-ttu-id="f3afc-111">MPLS (멀티 프로토콜 레이블 전환) 또는 개인 네트워크 연결의 경우 경계 네트워크 (DMZ, 완충 영역 및 스크린 된 서브넷이 라고도 함)에서 라우터의 공용 라우팅 가능 IP 주소를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3afc-111">For Multiprotocol Label Switching (MPLS) or private network connections, give the ITSP the publicly routable IP Address of the router in your perimeter network (also known as DMZ, demilitarized zone, and screened subnet).</span></span> <span data-ttu-id="f3afc-112">ITSP의 SBC (게이트웨이 또는 세션 경계 컨트롤러)가이 주소에 도달할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3afc-112">Verify that the gateway or Session Border Controller (SBC) at the ITSP can reach this address.</span></span> <span data-ttu-id="f3afc-113">또한, ITSP에 게 중재 서버의 FQDN을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3afc-113">Also give the ITSP the FQDN of your Mediation Server.</span></span>

  - <span data-ttu-id="f3afc-114">VPN (가상 사설망) 연결의 경우 VPN 서버의 IP 주소를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3afc-114">For virtual private network (VPN) connections, give the ITSP the IP address of your VPN server.</span></span>

<div>

## <a name="certificate-considerations"></a><span data-ttu-id="f3afc-115">인증서 고려 사항</span><span class="sxs-lookup"><span data-stu-id="f3afc-115">Certificate Considerations</span></span>

<span data-ttu-id="f3afc-116">SIP 트렁크 인증서가 필요한 지 여부를 결정 하려면 프로토콜 지원에 대 한 ITSP에 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="f3afc-116">To determine whether you need a certificate for SIP trunking, check with your ITSP about protocol support:</span></span>

1.  <span data-ttu-id="f3afc-117">ITSP가 TCP (전송 제어 프로토콜)만 지 원하는 경우 인증서가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f3afc-117">If your ITSP supports Transmission Control Protocol (TCP) only, you do not need a certificate.</span></span>

2.  <span data-ttu-id="f3afc-118">ITSP가 TLS (전송 계층 보안)를 지 원하는 경우 ITSP는 인증서를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3afc-118">If your ITSP supports Transport Layer Security (TLS), the ITSP must provide you with a certificate.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f3afc-119">SIP는 SRTP (실시간 전송 프로토콜) 또는 VoIP (Voice over 인터넷 프로토콜) 통화에서 실제 음성 데이터를 관리 하는 프로토콜인 안전한 실시간 전송 프로토콜 ()과 함께 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3afc-119">SIP works in conjunction with real-time transport protocol (RTP) or secure real-time transport protocol (SRTP), the protocols that manage the actual voice data in Voice over Internet Protocol (VoIP) calls.</span></span>



</div>

</div>

<div>

## <a name="deployment-process"></a><span data-ttu-id="f3afc-120">배포 프로세스</span><span class="sxs-lookup"><span data-stu-id="f3afc-120">Deployment Process</span></span>

<span data-ttu-id="f3afc-121">SIP 트렁크 연결의 Lync Server 쪽을 구현 하려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="f3afc-121">To implement the Lync Server side of the SIP trunk connection, follow these steps:</span></span>

1.  <span data-ttu-id="f3afc-122">Lync Server 토폴로지 작성기를 사용 하 여 SIP 도메인 토폴로지를 만들고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3afc-122">Using the Lync Server Topology Builder, create and configure the SIP domain topology.</span></span> <span data-ttu-id="f3afc-123">자세한 내용은 배포 설명서의 [Lync Server 2013에 대 한 토폴로지 작성기에서 토폴로지 정의 및 구성을](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f3afc-123">For details, see [Define and configure a topology in Topology Builder for Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md) in the Deployment documentation.</span></span>

2.  <span data-ttu-id="f3afc-124">Lync Server 제어판을 사용 하 여 새 SIP 도메인에 대 한 음성 라우팅을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3afc-124">Using the Lync Server Control Panel, configure voice routing for the new SIP domain.</span></span> <span data-ttu-id="f3afc-125">자세한 내용은 배포 설명서의 [Lync Server 2013에서 Trunks 구성을](lync-server-2013-configuring-trunks.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f3afc-125">For details, see [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md) in the Deployment documentation.</span></span>

3.  <span data-ttu-id="f3afc-126">**테스트 CsPstnOutboundCall** cmdlet을 사용 하 여 연결을 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3afc-126">Test connectivity by using the **Test-CsPstnOutboundCall** cmdlet.</span></span> <span data-ttu-id="f3afc-127">자세한 내용은 lync Server 관리 셸 설명서 또는 Lync Server Management Shell에 대 한 도움말을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f3afc-127">For details, see the Lync Server Management Shell documentation or Help for Lync Server Management Shell.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

