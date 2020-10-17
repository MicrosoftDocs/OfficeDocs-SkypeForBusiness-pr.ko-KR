---
title: 'Lync Server 2013: PSTN 연결 구성 요소'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN connectivity components
ms:assetid: 6b2a3f7d-760f-4f09-8432-312c98a7e6b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398504(v=OCS.15)
ms:contentKeyID: 48184408
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fa82336ed96c61315da4c25a0152ba75d15d7b6e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531745"
---
# <a name="pstn-connectivity-components-in-lync-server-2013"></a><span data-ttu-id="aab1a-102">Lync Server 2013의 PSTN 연결 구성 요소</span><span class="sxs-lookup"><span data-stu-id="aab1a-102">PSTN connectivity components in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aab1a-103">_**마지막으로 수정 된 항목:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="aab1a-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="aab1a-104">엔터프라이즈급 VoIP 솔루션은 QoS (서비스 품질)를 제외 하 고는 PSTN (공중 전화망)에 대 한 통화를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aab1a-104">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS).</span></span> <span data-ttu-id="aab1a-105">또한 사용자는 전화를 걸고 받을 때 기본 기술을 모르고 서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aab1a-105">In addition, users should not be aware of the underlying technology when they place and receive calls.</span></span> <span data-ttu-id="aab1a-106">사용자의 관점에서 보면 엔터프라이즈 음성 인프라와 PSTN 간의 통화는 다른 SIP 세션 처럼 보일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab1a-106">From the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another SIP session.</span></span>

<span data-ttu-id="aab1a-107">PSTN 연결의 경우 SIP 트렁크 또는 PSTN 게이트웨이 (PBX, 직접 SIP 링크 라고도 함 또는 PBX가 없는 경우)를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab1a-107">For PSTN connections, you can either deploy a SIP trunk or a PSTN gateway (with a PBX, also known as a Direct SIP link, or without a PBX).</span></span>

<div>

## <a name="sip-trunking"></a><span data-ttu-id="aab1a-108">SIP 트렁크</span><span class="sxs-lookup"><span data-stu-id="aab1a-108">SIP Trunking</span></span>

<span data-ttu-id="aab1a-109">PSTN 게이트웨이를 사용 하는 대신 SIP 트렁크를 사용 하 여 Enterprise Voice 솔루션을 PSTN에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab1a-109">As an alternative to using PSTN gateways, you can connect your Enterprise Voice solution to the PSTN by using SIP trunking.</span></span> <span data-ttu-id="aab1a-110">SIP 트렁크에서는 다음과 같은 시나리오를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab1a-110">SIP trunking enables the following scenarios:</span></span>

  - <span data-ttu-id="aab1a-111">회사 방화벽 내부 또는 외부의 엔터프라이즈 사용자는 해당 서비스 공급자의 서비스로 PSTN에서 종료 되는 전자 164 규격 번호로 지정 된 시내 또는 시외 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab1a-111">An enterprise user inside or outside the corporate firewall can make a local or long-distance call specified by an E.164-compliant number that is terminated on the PSTN as a service of the corresponding service provider.</span></span>

  - <span data-ttu-id="aab1a-112">모든 PSTN 구독자는 해당 엔터프라이즈 사용자와 연결 된 직접 안쪽 전화 걸기 (온) 번호에 전화를 걸어 회사 방화벽 내부 또는 외부의 엔터프라이즈 사용자에 게 연락할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab1a-112">Any PSTN subscriber can contact an enterprise user inside or outside the corporate firewall by dialing a Direct Inward Dialing (DID) number associated with that enterprise user.</span></span>

<span data-ttu-id="aab1a-113">이 배포 솔루션을 사용 하려면 SIP 트렁크 서비스 공급자가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="aab1a-113">The use of this deployment solution requires a SIP trunking service provider.</span></span>

</div>

<div>

## <a name="pstn-gateways"></a><span data-ttu-id="aab1a-114">PSTN 게이트웨이</span><span class="sxs-lookup"><span data-stu-id="aab1a-114">PSTN gateways</span></span>

<span data-ttu-id="aab1a-115">PSTN 게이트웨이는 엔터프라이즈 음성 인프라와 PSTN 또는 PBX 간에 신호 및 미디어를 변환 하는 타사 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="aab1a-115">PSTN gateways are third-party devices that translate signaling and media between the Enterprise Voice infrastructure and a PSTN or a PBX.</span></span> <span data-ttu-id="aab1a-116">PSTN 게이트웨이는 중재 서버와 함께 엔터프라이즈 음성 클라이언트에 PSTN 또는 PBX 통화를 제공 하는 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="aab1a-116">PSTN gateways work with the Mediation Server to present a PSTN or PBX call to an Enterprise Voice client.</span></span> <span data-ttu-id="aab1a-117">중재 서버는 PSTN 또는 PBX로 라우팅하기 위해 Enterprise Voice 클라이언트에서 PSTN 게이트웨이로의 통화도 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="aab1a-117">The Mediation Server also presents calls from Enterprise Voice clients to the PSTN gateway for routing to the PSTN or PBX.</span></span> <span data-ttu-id="aab1a-118">Microsoft와 협력 하 여 Lync Server에서 작동 하는 장치를 제공 하는 파트너 목록은의 Microsoft 통합 커뮤니케이션 파트너 웹 사이트를 참조 하세요 [https://go.microsoft.com/fwlink/p/?linkId=202836](https://go.microsoft.com/fwlink/p/?linkid=202836) .</span><span class="sxs-lookup"><span data-stu-id="aab1a-118">For a list of partners who work with Microsoft to provide devices that work with Lync Server, see the Microsoft Unified Communications Partners website at [https://go.microsoft.com/fwlink/p/?linkId=202836](https://go.microsoft.com/fwlink/p/?linkid=202836).</span></span>

</div>

<div>

## <a name="private-branch-exchanges"></a><span data-ttu-id="aab1a-119">Private Branch 교환</span><span class="sxs-lookup"><span data-stu-id="aab1a-119">Private Branch Exchanges</span></span>

<span data-ttu-id="aab1a-120">PBX (private branch exchange)를 사용 하는 기존 음성 인프라가 있는 경우 Lync Server Enterprise Voice를 사용 하 여 PBX를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab1a-120">If you have an existing voice infrastructure that uses a private branch exchange (PBX), you can use your PBX with Lync Server Enterprise Voice.</span></span>

<span data-ttu-id="aab1a-121">지원 되는 Enterprise Voice PBX 통합 시나리오는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="aab1a-121">The supported Enterprise Voice-PBX integration scenarios are as follows:</span></span>

  - <span data-ttu-id="aab1a-122">중재 서버를 사용 하 여 미디어 바이패스를 지 원하는 ip-pbx</span><span class="sxs-lookup"><span data-stu-id="aab1a-122">IP-PBX that supports media bypass, with a Mediation Server.</span></span>

  - <span data-ttu-id="aab1a-123">독립 실행형 PSTN 게이트웨이가 필요한 ip-pbx</span><span class="sxs-lookup"><span data-stu-id="aab1a-123">IP-PBX that requires a stand-alone PSTN gateway.</span></span>

  - <span data-ttu-id="aab1a-124">독립 실행형 PSTN 게이트웨이를 사용 하는 TDM (시간 구분 멀티플렉싱) PBX</span><span class="sxs-lookup"><span data-stu-id="aab1a-124">Time division multiplexing (TDM) PBX, with a stand-alone PSTN gateway.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="aab1a-125">미디어 바이패스가 모든 PSTN 게이트웨이, IP-PBX 및 SBC에서 작동하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aab1a-125">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="aab1a-126">Microsoft는 인증 된 파트너와의 PSTN 게이트웨이 및 국내 집합을 테스트 했으며 Cisco IP-Pbx를 사용 하 여 몇 가지 테스트를 수행 했습니다.</span><span class="sxs-lookup"><span data-stu-id="aab1a-126">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="aab1a-127">미디어 바이패스는 통합 커뮤니케이션 오픈 상호 운용성 프로그램-Lync Server에 나열 된 제품 및 버전 에서만 지원 됩니다 <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A> .</span><span class="sxs-lookup"><span data-stu-id="aab1a-127">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program – Lync Server at <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span></span>



</div>

<span data-ttu-id="aab1a-128">Enterprise Voice 솔루션을 제공 하는 파트너에 대 한 자세한 내용은의 Microsoft 통합 커뮤니케이션 파트너 웹 사이트를 참조 하세요 [https://go.microsoft.com/fwlink/p/?linkId=202836](https://go.microsoft.com/fwlink/p/?linkid=202836) .</span><span class="sxs-lookup"><span data-stu-id="aab1a-128">For details about partners who offer Enterprise Voice solutions, see the Microsoft Unified Communications Partners website at [https://go.microsoft.com/fwlink/p/?linkId=202836](https://go.microsoft.com/fwlink/p/?linkid=202836).</span></span>

<span data-ttu-id="aab1a-129">PSTN 게이트웨이를 포함 하 여 Enterprise Voice 하드웨어 솔루션을 제공 하는 파트너에 대 한 자세한 내용은 Microsoft 통합 커뮤니케이션 파트너 웹 사이트를 참조 하십시오 [https://go.microsoft.com/fwlink/p/?linkId=202836](https://go.microsoft.com/fwlink/p/?linkid=202836) .</span><span class="sxs-lookup"><span data-stu-id="aab1a-129">For details about partners who offer Enterprise Voice hardware solutions, including PSTN gateways, see the Microsoft Unified Communications Partners website [https://go.microsoft.com/fwlink/p/?linkId=202836](https://go.microsoft.com/fwlink/p/?linkid=202836).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

