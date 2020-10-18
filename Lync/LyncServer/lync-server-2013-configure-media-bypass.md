---
title: 'Lync Server 2013: 미디어 바이패스 구성'
description: 'Lync Server 2013: 미디어 바이패스를 구성 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure media bypass
ms:assetid: f50a7a13-c6a0-48f1-bee1-e45fa2b2f9b8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413028(v=OCS.15)
ms:contentKeyID: 48185836
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eefe960b9811f16544b7dabdd6aa07960e273806
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577614"
---
# <a name="configure-media-bypass-in-lync-server-2013"></a><span data-ttu-id="4fc5a-103">Lync Server 2013에서 미디어 바이패스 구성</span><span class="sxs-lookup"><span data-stu-id="4fc5a-103">Configure media bypass in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4fc5a-104">_**마지막으로 수정 된 항목:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="4fc5a-104">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="4fc5a-105">이 섹션에서는 하나 이상의 중재 서버를 이미 게시 및 구성 했 고 ( [lync server 2013의 토폴로지 작성기에서 Topology Server 정의](lync-server-2013-define-a-mediation-server-in-topology-builder.md) 를 참조 하 고, lync server 2013에 [토폴로지를 게시](lync-server-2013-publish-the-topology.md)하는 방법에 설명 된 대로 또는 Lync Server [2013에서 프런트 엔드 풀 또는 Standard Edition 서버 정의 및 구성](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) , 그리고 lync [server 2013의 토폴로지는](lync-server-2013-publish-the-topology.md)모든 배포 설명서에 나와 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="4fc5a-105">This section assumes that you have already published and configured either at least one or more Mediation Servers (as described in [Define a Mediation Server in Topology Builder in Lync Server 2013](lync-server-2013-define-a-mediation-server-in-topology-builder.md) and [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md), or in [Define and configure a Front End pool or Standard Edition server in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) and [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md), respectively, all in the Deployment documentation).</span></span>

<span data-ttu-id="4fc5a-106">또한이 섹션에서는 [Lync Server 2013의 토폴로지 작성기에서 게이트웨이 정의](lync-server-2013-define-a-gateway-in-topology-builder.md)에 설명 된 대로 하나 이상의 게이트웨이 피어가 PSTN 연결을 제공 하도록 정의 했다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc5a-106">This section also assumes that you have defined at least one gateway peer to provide PSTN connectivity, as described in [Define a gateway in Topology Builder in Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md).</span></span> <span data-ttu-id="4fc5a-107">연결 하는 피어가 SIP 트렁크 provider의 SBC 인 경우 공급자가 정규화 된 공급자 인지, 그리고 공급자가 미디어 바이패스를 지원 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc5a-107">If the peer you connect to is the SBC of a SIP trunking provider, make sure that the provider is a qualified provider and that the provider supports media bypass.</span></span> <span data-ttu-id="4fc5a-108">예를 들어 대부분의 SIP 트렁크 공급자는 해당 SBC만 중재 서버에서 트래픽을 수신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fc5a-108">For example, many SIP trunking providers will only allow their SBC to receive traffic from the Mediation Server.</span></span> <span data-ttu-id="4fc5a-109">그렇다면 해당 트렁크에 바이패스를 사용 하도록 설정 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc5a-109">If so, then bypass must not be enabled for the trunk in question.</span></span> <span data-ttu-id="4fc5a-110">또한 조직에서 SIP 트렁크 provider에 내부 네트워크 IP 주소를 제공 하는 경우가 아니면 미디어 바이패스를 사용 하도록 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4fc5a-110">Also, you cannot enable media bypass unless your organization reveals its internal network IP addresses to the SIP trunking provider.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4fc5a-111">미디어 바이패스가 모든 PSTN 게이트웨이, IP-PBX 및 SBC에서 작동하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4fc5a-111">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="4fc5a-112">Microsoft는 인증 된 파트너와의 PSTN 게이트웨이 및 국내 집합을 테스트 했으며 Cisco IP-Pbx를 사용 하 여 몇 가지 테스트를 수행 했습니다.</span><span class="sxs-lookup"><span data-stu-id="4fc5a-112">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="4fc5a-113">미디어 바이패스는 통합 커뮤니케이션 오픈 상호 운용성 프로그램-Lync Server에 나열 된 제품 및 버전 에서만 지원 됩니다 <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A> .</span><span class="sxs-lookup"><span data-stu-id="4fc5a-113">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program – Lync Server at <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span></span>



</div>

<span data-ttu-id="4fc5a-114">이 섹션에서는 중재 서버에 필요한 처리를 줄이기 위해 미디어 바이패스를 사용 하도록 설정 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc5a-114">This section describes how to enable media bypass to reduce the processing required of the Mediation Server.</span></span> <span data-ttu-id="4fc5a-115">미디어 바이패스를 사용 하도록 설정 하기 전에 계획 설명서의 [Lync Server 2013에서 미디어 바이패스 계획](lync-server-2013-planning-for-media-bypass.md) 에 설명 된 대로, 환경이 미디어 바이패스를 지 원하는 데 필요한 조건을 충족 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc5a-115">Before you enable media bypass, make sure that your environment meets the conditions required to support media bypass, as described in [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in the Planning documentation.</span></span> <span data-ttu-id="4fc5a-116">또한 [Lync server 2013의 미디어 바이패스 계획](lync-server-2013-planning-for-media-bypass.md) 에 설명 된 정보를 사용 하 여 미디어 바이패스 전역 설정을 사용 하 여 항상 중재 서버를 우회 하거나 중재 서버를 건너뛸지 여부를 결정할 때 사이트 및 지역 정보를 사용 하도록 설정할지 여부를 결정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc5a-116">Also make sure that you used the information in [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) to decide whether to enable media bypass global settings to always bypass the Mediation Server or to use site and region information when determining whether to bypass the Mediation Server.</span></span>

<span data-ttu-id="4fc5a-117">선택적으로 CAC (통화 허용 제어) 및 고급 Enterprise Voice 기능을 구성 해야 하는 경우에는 통화 허용 제어에 의해 수행 된 대역폭 예약이 미디어 바이패스를 사용 하는 모든 통화에 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4fc5a-117">If you have already optionally configured call admission control (CAC), another advanced Enterprise Voice feature, note that the bandwidth reservation performed by call admission control does not apply to any calls for which media bypass is employed.</span></span> <span data-ttu-id="4fc5a-118">미디어 바이패스를 사용할 것인지 여부를 확인 하 고, 미디어 바이패스를 사용 하는 경우 통화 허용 제어는 전화를 받지 않습니다. 미디어 바이패스 검사가 실패 한 경우에만 통화 허용 제어에 대 한 확인이 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fc5a-118">The verification of whether to employ media bypass is performed first, and if media bypass is employed, call admission control is not used for the call; only if the media bypass check fails is the check performed for call admission control.</span></span> <span data-ttu-id="4fc5a-119">따라서 PSTN으로 라우팅되는 특정 통화에 대 한 두 가지 기능은 상호 배타적이 지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4fc5a-119">The two features are thus mutually exclusive for any particular call that is routed to the PSTN.</span></span> <span data-ttu-id="4fc5a-120">미디어 바이패스는 통화에 대 한 미디어 끝점 간에 대역폭 제약 조건이 존재 하지 않는다고 가정 하기 때문에 논리입니다. 대역폭이 제한 된 링크에 대해서는 미디어 바이패스를 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4fc5a-120">This is the logic because media bypass assumes that bandwidth constraints do not exist between the media endpoints on a call; media bypass cannot be performed on links with restricted bandwidth.</span></span> <span data-ttu-id="4fc5a-121">따라서 다음 중 하나는 PSTN 통화에 적용 되며 a) 미디어는 중재 서버를 우회 하며 통화 허용 제어는 통화에 대 한 대역폭을 예약 하지 않습니다. 또는 b) 통화 허용 제어는 통화에 대역폭 예약을 적용 하며 통화와 관련 된 중재 서버에서 미디어를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc5a-121">As a result, one of the following will apply to a PSTN call: a) media bypasses the Mediation Server, and call admission control does not reserve bandwidth for the call; or b) call admission control applies bandwidth reservation to the call, and media is processed by the Mediation Server involved in the call.</span></span>

<div>

## <a name="next-steps-enable-media-bypass-on-the-trunk-connection"></a><span data-ttu-id="4fc5a-122">다음 단계: 트렁크 연결에서 미디어 바이패스를 사용 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="4fc5a-122">Next Steps: Enable Media Bypass on the Trunk Connection</span></span>

<span data-ttu-id="4fc5a-123">PSTN 연결에 대 한 초기 설정 (다이얼 플랜, 음성 정책, PSTN 사용 레코드, 아웃 바운드 통화 경로 및 변환 규칙)을 구성한 후에 [는 Lync Server 2013에서 미디어 바이패스](lync-server-2013-configure-a-trunk-with-media-bypass.md)를 사용 하 여 구성 하는 단계를 통해 미디어 바이패스를 사용 하도록 설정 하는 프로세스를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc5a-123">After configuring initial settings for PSTN connectivity (dial plans, voice policies, PSTN usage records, outbound call routes, and translation rules), begin the process of enabling media bypass by using the steps in [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4fc5a-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4fc5a-124">See Also</span></span>


[<span data-ttu-id="4fc5a-125">Lync Server 2013의 미디어 바이패스로 트렁크 구성</span><span class="sxs-lookup"><span data-stu-id="4fc5a-125">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="4fc5a-126">Lync Server 2013에서 미디어 바이패스를 구성 하 여 항상 중재 서버를 바이패스 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="4fc5a-126">Configure media bypass in Lync Server 2013 to always bypass the Mediation Server</span></span>](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md)  
[<span data-ttu-id="4fc5a-127">사이트 및 지역 정보를 사용 하도록 Lync Server 2013에서 미디어 바이패스 전역 설정 구성</span><span class="sxs-lookup"><span data-stu-id="4fc5a-127">Configure media bypass global settings in Lync Server 2013 to use site and region information</span></span>](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md)  


[<span data-ttu-id="4fc5a-128">Lync Server 2013의 글로벌 미디어 바이패스 옵션</span><span class="sxs-lookup"><span data-stu-id="4fc5a-128">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  


[<span data-ttu-id="4fc5a-129">Lync Server 2013의 미디어 바이패스 계획</span><span class="sxs-lookup"><span data-stu-id="4fc5a-129">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

