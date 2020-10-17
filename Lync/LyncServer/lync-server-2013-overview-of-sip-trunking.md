---
title: 'Lync Server 2013: SIP 트렁크 개요'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of SIP trunking
ms:assetid: 204f2c21-436f-4b2d-93ea-d6db98fa2952
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398285(v=OCS.15)
ms:contentKeyID: 48183601
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 81690d4f006b5c1df3ed001369cbe5c4b1f560b8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520855"
---
# <a name="overview-of-sip-trunking-in-lync-server-2013"></a><span data-ttu-id="f5fac-102">Lync Server 2013의 SIP 트렁크 개요</span><span class="sxs-lookup"><span data-stu-id="f5fac-102">Overview of SIP trunking in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5fac-103">_**마지막으로 수정 된 항목:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="f5fac-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="f5fac-104">SIP 트렁크 구축은 조직의 통신을 단순화 하 고 실시간 통신에 대 한 최신 향상을 준비 하기 위한 커다란 단계가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5fac-104">Deploying SIP trunking can be a big step toward simplifying your organization’s telecommunications and preparing for up-to-date enhancements to real-time communications.</span></span> <span data-ttu-id="f5fac-105">SIP 트렁크의 주요 이점 중 하나는 일반적으로 각 분기 사이트에서 별도의 트렁크를 필요로 하는 선행, 시간 구분 멀티플렉싱 (TDM) 트렁크와 반대로 중앙 사이트에서 조직의 연결을 PSTN (공중 전화망)으로 통합할 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f5fac-105">One of the primary advantages of SIP trunking is that you can consolidate your organization’s connections to the public switched telephone network (PSTN) at a central site, as opposed to its predecessor, time division multiplexing (TDM) trunking, which typically requires a separate trunk from each branch site.</span></span>

<div>

## <a name="sip-trunking-in-lync-server"></a><span data-ttu-id="f5fac-106">Lync Server의 SIP 트렁크</span><span class="sxs-lookup"><span data-stu-id="f5fac-106">SIP Trunking in Lync Server</span></span>

<span data-ttu-id="f5fac-107">Lync Server 2013 SIP 트렁크 기능을 사용 하면 다음을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5fac-107">The Lync Server 2013 SIP trunking capabilities enable the following:</span></span>

  - <span data-ttu-id="f5fac-108">회사 방화벽 내부 또는 외부에 있는 enterprise 사용자는 해당 서비스 공급자의 서비스로 PSTN에서 종료 되는 E. 164 규격 번호로 지정 된 시내 전화 또는 시외 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5fac-108">An enterprise user, whether inside or outside the corporate firewall, can make a local call or a long-distance call that is specified by an E.164-compliant number that is terminated on the PSTN as a service of the corresponding service provider.</span></span>

  - <span data-ttu-id="f5fac-109">모든 PSTN 구독자는 해당 enterprise 사용자와 연결 된 직접 안쪽 전화 걸기 (즉) 번호를 사용 하 여 회사 방화벽 내부 또는 외부의 엔터프라이즈 사용자에 게 연락할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5fac-109">Any PSTN subscriber can contact an enterprise user inside or outside the corporate firewall by dialing a Direct Inward Dialing (DID) number that is associated with that enterprise user.</span></span>

</div>

<div>

## <a name="cost-savings"></a><span data-ttu-id="f5fac-110">비용 절감</span><span class="sxs-lookup"><span data-stu-id="f5fac-110">Cost Savings</span></span>

<span data-ttu-id="f5fac-111">SIP 트렁크과 관련 된 비용 절감 금액은 상당히 크게 증가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5fac-111">The cost savings associated with SIP trunking can be substantial:</span></span>

  - <span data-ttu-id="f5fac-112">일반적으로 SIP 트렁크를 통한 장거리 통화 비용이 많이 듭니다.</span><span class="sxs-lookup"><span data-stu-id="f5fac-112">Long distance calls typically cost much less through a SIP trunk.</span></span>

  - <span data-ttu-id="f5fac-113">관리 효율성 비용을 절감 하 고 배포의 복잡성을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5fac-113">You can cut manageability costs and reduce the complexity of deployment.</span></span>

  - <span data-ttu-id="f5fac-114">SIP 트렁크를 ITSP에 직접 연결 하면 BRI (기본 속도 인터페이스) 및 PRI (기본 속도 인터페이스) 수수료를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5fac-114">Basic rate interface (BRI) and primary rate interface (PRI) fees can be eliminated if you connect a SIP trunk directly to your ITSP at significantly lower cost.</span></span> <span data-ttu-id="f5fac-115">TDM 트렁크에서는 서비스 공급자가 1 분 동안 통화를 충전 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5fac-115">In TDM trunking, service providers charge for calls by the minute.</span></span> <span data-ttu-id="f5fac-116">SIP 트렁크 비용은 비교적 작고 경제적으로 구입할 수 있는 대역폭 사용량을 기반으로 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5fac-116">The cost of SIP trunking may be based on bandwidth usage, which you can buy in smaller, more economical increments.</span></span> <span data-ttu-id="f5fac-117">실제 비용은 선택한 ITSP의 서비스 모델에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="f5fac-117">(The actual cost depends on the service model of the ITSP you choose.)</span></span>

<div>

## <a name="sip-trunking-vs-hosting-a-pstn-gateway-or-ip-pbx"></a><span data-ttu-id="f5fac-118">SIP 트렁크 및 PSTN 게이트웨이 또는 IP-PBX 호스팅</span><span class="sxs-lookup"><span data-stu-id="f5fac-118">SIP Trunking vs. Hosting a PSTN Gateway or IP-PBX</span></span>

<span data-ttu-id="f5fac-119">SIP 트렁크가 서비스 공급자에 직접 연결 하기 때문에 PSTN 게이트웨이 및 해당 관리 비용 및 복잡도를 없앨 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5fac-119">Because SIP trunks connect directly to your service provider, you can eliminate your PSTN gateways and their management cost and complexity.</span></span> <span data-ttu-id="f5fac-120">SIP 트렁크를 사용 하면 유지 관리 및 관리가 줄어들어 비용 절감 효과를 크게 절감할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5fac-120">Using a SIP trunk can lead to substantial cost savings through reduced maintenance and administration.</span></span>

</div>

</div>

<div>

## <a name="expanded-voip-services"></a><span data-ttu-id="f5fac-121">확장 된 VoIP 서비스</span><span class="sxs-lookup"><span data-stu-id="f5fac-121">Expanded VoIP Services</span></span>

<span data-ttu-id="f5fac-122">음성 기능은 종종 SIP 트렁크 배포의 주요 동기 이지만 음성 지원은 첫 번째 단계에 불과합니다.</span><span class="sxs-lookup"><span data-stu-id="f5fac-122">Voice features are often the primary motivation for deploying SIP trunking, but voice support is just the first step.</span></span> <span data-ttu-id="f5fac-123">SIP 트렁크를 사용 하 여 VoIP 기능을 확장 하 고 Lync Server 2013을 사용 하 여 보다 다양 한 서비스 집합을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5fac-123">With SIP trunking, you can extend VoIP capabilities and enable Lync Server 2013 to deliver a richer set of services.</span></span> <span data-ttu-id="f5fac-124">예제:</span><span class="sxs-lookup"><span data-stu-id="f5fac-124">For example:</span></span>

  - <span data-ttu-id="f5fac-125">향상 된 현재 상태 검색 (Lync Server 2013을 실행 하지 않는 장치)을 사용 하면 휴대폰을 보다 효율적으로 통합 하 여 사용자가 휴대폰 통화 상태 인지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5fac-125">Enhanced presence detection for devices that are not running Lync Server 2013 can provide better integration with mobile phones, enabling you to see when a user is on a mobile phone call.</span></span>

  - <span data-ttu-id="f5fac-126">E9-1-1 긴급 통화를 통해 911 통화에 응답 하 여 전화 번호에서 발신자의 위치를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5fac-126">E9-1-1 emergency calling enables the authorities who answer 911 calls to determine the caller’s location from his or her telephone number.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f5fac-127">사용자가 지원 하 고 조직에 대해 사용 하도록 설정할 수 있는 서비스 목록은 ITSP에 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="f5fac-127">Contact your ITSP for a list of services that they support and can enable for your organization.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

