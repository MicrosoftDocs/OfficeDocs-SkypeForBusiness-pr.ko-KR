---
title: 'Lync Server 2013: 미디어 바이패스 구성'
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
ms.openlocfilehash: 8be022e5b1b16bff432873e27ddda5f388db02f1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758432"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-in-lync-server-2013"></a><span data-ttu-id="bcfa5-102">Lync Server 2013에서 미디어 바이패스 구성</span><span class="sxs-lookup"><span data-stu-id="bcfa5-102">Configure media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bcfa5-103">_**마지막으로 수정한 주제:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="bcfa5-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="bcfa5-104">이 섹션에서는 적어도 하나 이상의 중재 서버를 이미 게시 하 고 구성 했습니다 ( [Lync server 2013의 토폴로지 작성기에서 조정 서버 정의](lync-server-2013-define-a-mediation-server-in-topology-builder.md) 및 [lync server 2013의 토폴로지 게시](lync-server-2013-publish-the-topology.md)또는 Lync Server [2013에서 프런트 엔드 풀 또는 Standard Edition Server 정의 및 구성](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) 및 lync server 2013에서 각각 배포 설명서의 [토폴로지 게시](lync-server-2013-publish-the-topology.md)에 설명 되어 있는 것으로 가정 합니다.)</span><span class="sxs-lookup"><span data-stu-id="bcfa5-104">This section assumes that you have already published and configured either at least one or more Mediation Servers (as described in [Define a Mediation Server in Topology Builder in Lync Server 2013](lync-server-2013-define-a-mediation-server-in-topology-builder.md) and [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md), or in [Define and configure a Front End pool or Standard Edition server in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) and [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md), respectively, all in the Deployment documentation).</span></span>

<span data-ttu-id="bcfa5-105">또한이 섹션에서는 [Lync Server 2013의 토폴로지 작성기에서 게이트웨이 정의](lync-server-2013-define-a-gateway-in-topology-builder.md)에 설명 된 대로 하나 이상의 게이트웨이 피어가 PSTN 연결을 제공 하도록 정의 되었다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcfa5-105">This section also assumes that you have defined at least one gateway peer to provide PSTN connectivity, as described in [Define a gateway in Topology Builder in Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md).</span></span> <span data-ttu-id="bcfa5-106">연결 하는 피어가 SIP 트렁크 공급자의 SBC 인 경우 공급자가 정규화 된 공급자이 고 공급자가 미디어 바이패스를 지원 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcfa5-106">If the peer you connect to is the SBC of a SIP trunking provider, make sure that the provider is a qualified provider and that the provider supports media bypass.</span></span> <span data-ttu-id="bcfa5-107">예를 들어 많은 SIP 트렁크 공급자는 해당 SBC만 중재 서버에서 트래픽을 수신할 수 있도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcfa5-107">For example, many SIP trunking providers will only allow their SBC to receive traffic from the Mediation Server.</span></span> <span data-ttu-id="bcfa5-108">그런 경우에는 해당 트렁크에 대해 bypass을 사용 하도록 설정 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcfa5-108">If so, then bypass must not be enabled for the trunk in question.</span></span> <span data-ttu-id="bcfa5-109">또한 조직에서 SIP 트렁크 공급자에 대 한 내부 네트워크 IP 주소를 표시 하지 않는 한 미디어 바이패스를 사용 하도록 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bcfa5-109">Also, you cannot enable media bypass unless your organization reveals its internal network IP addresses to the SIP trunking provider.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bcfa5-110">미디어 바이패스는 모든 PSTN 게이트웨이, IP PBX, SBC와 상호 작용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bcfa5-110">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="bcfa5-111">Microsoft는 인증 된 파트너와 함께 PSTN 게이트웨이 및 SBCs 집합을 테스트 했으며 Cisco IP-Pbx를 사용 하 여 테스트를 완료 했습니다.</span><span class="sxs-lookup"><span data-stu-id="bcfa5-111">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="bcfa5-112">미디어 바이패스는 통합 커뮤니케이션 오픈 상호 운용성 프로그램 –의 Lync Server에 나열 된 제품 및 버전 에서만 <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bcfa5-112">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program – Lync Server at <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span></span>



</div>

<span data-ttu-id="bcfa5-113">이 섹션에서는 미디어 우회를 사용 하 여 중재 서버에 필요한 처리를 줄이는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcfa5-113">This section describes how to enable media bypass to reduce the processing required of the Mediation Server.</span></span> <span data-ttu-id="bcfa5-114">미디어 바이패스를 사용 하도록 설정 하기 전에 계획 설명서의 [Lync Server 2013에서 미디어 바이패스 계획](lync-server-2013-planning-for-media-bypass.md) 에 설명 된 대로, 환경이 미디어 바이패스를 지 원하는 데 필요한 조건을 충족 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcfa5-114">Before you enable media bypass, make sure that your environment meets the conditions required to support media bypass, as described in [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in the Planning documentation.</span></span> <span data-ttu-id="bcfa5-115">또한 [Lync server 2013에서 미디어](lync-server-2013-planning-for-media-bypass.md) 바이패스를 사용 하도록 설정 하 여 미디어 무시 전역 설정이 항상 중재 서버를 우회 하거나 중재 서버를 우회할 지 여부를 결정할 때 사이트 및 지역 정보를 사용 하는지 여부를 결정할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcfa5-115">Also make sure that you used the information in [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) to decide whether to enable media bypass global settings to always bypass the Mediation Server or to use site and region information when determining whether to bypass the Mediation Server.</span></span>

<span data-ttu-id="bcfa5-116">선택적으로 CAC (call 허용 제어)에 대 한 다른 고급 엔터프라이즈 음성 기능을 구성한 경우에는 호출 허용 제어에 의해 수행 되는 대역폭 예약이 미디어 바이패스를 사용 하는 모든 통화에 적용 되지 않는다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="bcfa5-116">If you have already optionally configured call admission control (CAC), another advanced Enterprise Voice feature, note that the bandwidth reservation performed by call admission control does not apply to any calls for which media bypass is employed.</span></span> <span data-ttu-id="bcfa5-117">미디어 바이패스를 사용할 것인지 여부를 확인 하 고 미디어 바이패스를 사용 하는 경우 통화 허용 제어는 통화에 사용할 수 없습니다. 미디어 바이패스 검사에 실패 하는 경우에만 호출 허용 제어에 대 한 검사를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcfa5-117">The verification of whether to employ media bypass is performed first, and if media bypass is employed, call admission control is not used for the call; only if the media bypass check fails is the check performed for call admission control.</span></span> <span data-ttu-id="bcfa5-118">이러한 두 기능은 PSTN으로 라우팅되는 특정 통화에 대해 상호 배타적이 지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bcfa5-118">The two features are thus mutually exclusive for any particular call that is routed to the PSTN.</span></span> <span data-ttu-id="bcfa5-119">미디어 바이패스는 통화의 미디어 끝점 사이에 대역폭 제약 조건이 없는 것으로 간주 되므로이 논리를 사용 합니다. 제한 된 대역폭의 링크에서는 미디어 바이패스를 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bcfa5-119">This is the logic because media bypass assumes that bandwidth constraints do not exist between the media endpoints on a call; media bypass cannot be performed on links with restricted bandwidth.</span></span> <span data-ttu-id="bcfa5-120">따라서 다음 중 하나가 PSTN 통화에 적용 됩니다. a) 미디어는 중재 서버를 우회 하 고 통화 허용 제어는 통화에 대 한 대역폭을 예약 하지 않습니다. 또는 b) 통화 허용 제어는 통화에 대역폭 예약을 적용 하 고, 통화와 관련 된 중재 서버에서 미디어를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcfa5-120">As a result, one of the following will apply to a PSTN call: a) media bypasses the Mediation Server, and call admission control does not reserve bandwidth for the call; or b) call admission control applies bandwidth reservation to the call, and media is processed by the Mediation Server involved in the call.</span></span>

<div>

## <a name="next-steps-enable-media-bypass-on-the-trunk-connection"></a><span data-ttu-id="bcfa5-121">다음 단계: 트렁크 연결에서 미디어 바이패스 사용</span><span class="sxs-lookup"><span data-stu-id="bcfa5-121">Next Steps: Enable Media Bypass on the Trunk Connection</span></span>

<span data-ttu-id="bcfa5-122">PSTN 연결 (다이얼 플랜, 음성 정책, PSTN 사용 레코드, 아웃 바운드 통화 경로 및 번역 규칙)에 대 한 초기 설정을 구성한 후에는 [Lync Server 2013에서 미디어 바이패스](lync-server-2013-configure-a-trunk-with-media-bypass.md)를 사용 하 여 트렁크 구성 단계를 사용 하 여 미디어 바이패스를 사용 하도록 설정 하는 프로세스를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcfa5-122">After configuring initial settings for PSTN connectivity (dial plans, voice policies, PSTN usage records, outbound call routes, and translation rules), begin the process of enabling media bypass by using the steps in [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bcfa5-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bcfa5-123">See Also</span></span>


[<span data-ttu-id="bcfa5-124">Lync Server 2013에서 미디어 바이패스를 사용 하 여 트렁크 구성</span><span class="sxs-lookup"><span data-stu-id="bcfa5-124">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="bcfa5-125">Lync Server 2013에서 미디어 바이패스를 구성 하 여 항상 중재 서버를 우회 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="bcfa5-125">Configure media bypass in Lync Server 2013 to always bypass the Mediation Server</span></span>](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md)  
[<span data-ttu-id="bcfa5-126">미디어 구성 Lync Server 2013에서 사이트 및 지역 정보를 사용 하 여 전역 설정을 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcfa5-126">Configure media bypass global settings in Lync Server 2013 to use site and region information</span></span>](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md)  


[<span data-ttu-id="bcfa5-127">Lync Server 2013의 글로벌 미디어 우회 옵션</span><span class="sxs-lookup"><span data-stu-id="bcfa5-127">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  


[<span data-ttu-id="bcfa5-128">Lync Server 2013의 미디어 바이패스 계획</span><span class="sxs-lookup"><span data-stu-id="bcfa5-128">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

