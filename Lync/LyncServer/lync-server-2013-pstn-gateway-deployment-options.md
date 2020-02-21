---
title: 'Lync Server 2013: PSTN 게이트웨이 배포 옵션'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN gateway deployment options
ms:assetid: d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398899(v=OCS.15)
ms:contentKeyID: 48185445
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be67190fc4c6a124cd7c7f44082d9cddf0290bc1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183521"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="pstn-gateway-deployment-options-in-lync-server-2013"></a><span data-ttu-id="fddda-102">Lync Server 2013의 PSTN 게이트웨이 배포 옵션</span><span class="sxs-lookup"><span data-stu-id="fddda-102">PSTN gateway deployment options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fddda-103">_**마지막으로 수정 된 항목:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="fddda-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<div>

## <a name="pstn-gateways"></a><span data-ttu-id="fddda-104">PSTN 게이트웨이</span><span class="sxs-lookup"><span data-stu-id="fddda-104">PSTN Gateways</span></span>

<span data-ttu-id="fddda-105">PSTN (공중 전화망) 게이트웨이는 직접 또는 SIP 트렁크 연결을 통해 기업 음성 인프라와 PSTN 간에 신호 및 미디어를 변환 하는 타사 하드웨어 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="fddda-105">Public switched telephone network (PSTN) gateways are third-party hardware components that translate signaling and media between the Enterprise Voice infrastructure and the PSTN, either directly or through connection to SIP trunks.</span></span> <span data-ttu-id="fddda-106">어느 토폴로지에서 든 게이트웨이는 PSTN을 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="fddda-106">In either topology, the gateway terminates the PSTN.</span></span> <span data-ttu-id="fddda-107">게이트웨이는 자체 서브넷으로 격리 되며 중재 서버를 통해 엔터프라이즈 네트워크에 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fddda-107">The gateway is isolated in its own subnet and is connected to the enterprise network through the Mediation Server.</span></span>

<span data-ttu-id="fddda-108">일반적으로 사이트가 여러 개인 기업에서는 각 사이트에 하나 이상의 게이트웨이를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="fddda-108">An enterprise with multiple sites would typically deploy one or more gateways at each site.</span></span> <span data-ttu-id="fddda-109">분기 사이트는 게이트웨이를 통해 또는 단일 상자에 게이트웨이와 서버를 결합 하는 Sba (survivable Branch 기기를 통해 PSTN에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fddda-109">Branch sites can connect to the PSTN either through a gateway, or through a Survivable Branch Appliance, which combines gateway and servers in a single box.</span></span> <span data-ttu-id="fddda-110">분기 사이트에서 게이트웨이를 사용 하는 경우 WAN 링크를 복원 하지 않으면 사이트에 등록자 및 중재 서버가 모두 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="fddda-110">If branch sites use a gateway, both a Registrar and Mediation Server are required on site, unless the WAN link is resilient.</span></span> <span data-ttu-id="fddda-111">프런트 엔드 서버에서 배치 된 되는 하나 이상의 중재 서버는 각 사이트에서 하나 이상의 게이트웨이에 대 한 통화를 라우팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fddda-111">One or more Mediation Servers, which are collocated on Front End Servers, can route calls for the one or more gateways at each site.</span></span> <span data-ttu-id="fddda-112">사이트에 필요한 등록자, 중재 서버 및 게이트웨이는 Sba (survivable Branch 기기로 배포 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fddda-112">We recommend that the Registrar, Mediation Server, and gateway required on site are deployed as a Survivable Branch Appliance.</span></span>

<span data-ttu-id="fddda-113">PSTN 게이트웨이의 수, 크기 및 위치를 결정 하는 것은 엔터프라이즈 음성 인프라를 계획할 때 결정 해야 하는 가장 중요 한 비용 및 비용이 많이 드는 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="fddda-113">Determining the number, size, and location of PSTN gateways is perhaps the most important and expensive decision you must make when planning your Enterprise Voice infrastructure.</span></span>

<span data-ttu-id="fddda-114">다음은 고려해 야 할 주요 질문입니다.</span><span class="sxs-lookup"><span data-stu-id="fddda-114">Here are the main questions to consider.</span></span> <span data-ttu-id="fddda-115">이러한 질문에 대 한 대답은 모두 상호 의존적인 것으로 생각 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fddda-115">Keep in mind that the answers to these questions are all interdependent</span></span>

  - <span data-ttu-id="fddda-116">필요한 PSTN 게이트웨이 수</span><span class="sxs-lookup"><span data-stu-id="fddda-116">How many PSTN gateways are needed?</span></span> <span data-ttu-id="fddda-117">답은 사용자 수, 예상 되는 동시 통화 수 (트래픽 부하) 및 사이트 수 (각 사이트 마다 하나씩)에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="fddda-117">The answer depends on the number of users, the anticipated number of simultaneous calls (traffic load), and the number of sites (each site needs one).</span></span>

  - <span data-ttu-id="fddda-118">게이트웨이 크기는 어떻게 됩니까?</span><span class="sxs-lookup"><span data-stu-id="fddda-118">What size should the gateways be?</span></span> <span data-ttu-id="fddda-119">해답은 사이트의 사용자 수와 트래픽 부하에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="fddda-119">The answer depends on the number of users at the site and on the traffic load.</span></span>

  - <span data-ttu-id="fddda-120">게이트웨이 위치</span><span class="sxs-lookup"><span data-stu-id="fddda-120">Where should the gateways be located?</span></span> <span data-ttu-id="fddda-121">이에 대 한 답은 토폴로지와 조직의 지리적 배포에 포함 되는 부분에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="fddda-121">The answer depends in part on the topology and in part on the geographic distribution of your organization.</span></span>

<span data-ttu-id="fddda-122">또한 게이트웨이 토폴로지 옵션을 고려해 야 합니다 (이 항목의 뒷부분에 나오는 게이트웨이 토폴로지 참조).</span><span class="sxs-lookup"><span data-stu-id="fddda-122">You should also consider your gateway topology options (for details, see Gateway Topologies later in this topic).</span></span>

<div>

## <a name="mn-trunk-support"></a><span data-ttu-id="fddda-123">M:N 트렁크 지원</span><span class="sxs-lookup"><span data-stu-id="fddda-123">M:N Trunk Support</span></span>

<span data-ttu-id="fddda-124">중재 서버는 여러 게이트웨이, 인터넷 전화 통신 서비스 공급자가 제공 하는 다중 및 sbc (세션 경계 컨트롤러)를 통해 통화를 라우팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fddda-124">The Mediation Servers can route calls through multiple gateways, Session Border Controllers (SBCs) provided by Internet telephony service providers, or a combination of the two.</span></span> <span data-ttu-id="fddda-125">또한 풀의 여러 중재 서버가 여러 게이트웨이와 상호 작용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fddda-125">Additionally, multiple Mediation Servers in the pool can interact with multiple gateways.</span></span> <span data-ttu-id="fddda-126">중재 서버와 게이트웨이 간에 정의 된 논리 경로를 *트렁크*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="fddda-126">The logical route defined between a Mediation Server and gateway is called a *trunk*.</span></span> <span data-ttu-id="fddda-127">내부 사용자가 PSTN 전화를 걸 때 프런트 엔드 풀의 아웃 바운드 라우팅 논리는 특정 통화를 라우팅하는 데 사용할 수 있는 모든 가능한 조합으로 경로를 지정할 트렁크를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fddda-127">When an internal user places a PSTN call, outbound routing logic on the Front End pool chooses which trunk to route over out of all possible combinations that may be available for routing that particular call.</span></span> <span data-ttu-id="fddda-128">DNS 부하 분산을 사용 하 여 풀의 특정 중재 서버에 문제가 발생 하 여 게이트웨이에 연결 하는 데 실패 하는 경우 해당 통화는 풀의 대체 중재 서버로 다시 시도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fddda-128">With DNS load balancing, if a call fails to reach a gateway due to an issue with a particular Mediation Server in the pool, the call will be retried to an alternate Mediation Server in the pool.</span></span>

<span data-ttu-id="fddda-129">여러 게이트웨이를 계획 하는 방법에 대 한 자세한 내용은 [Lync Server 2013의 M:n 트렁크](lync-server-2013-m-n-trunk.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fddda-129">For details about planning for multiple gateways, see [M:N trunk in Lync Server 2013](lync-server-2013-m-n-trunk.md).</span></span>

<span data-ttu-id="fddda-130">다른 아웃 바운드 라우팅 향상 기능에 대 한 자세한 내용은 [Lync Server 2013의 음성 경로](lync-server-2013-voice-routes.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="fddda-130">For details about other outbound routing enhancements, see [Voice routes in Lync Server 2013](lync-server-2013-voice-routes.md).</span></span>

</div>

<div>

## <a name="gateway-topologies"></a><span data-ttu-id="fddda-131">게이트웨이 토폴로지</span><span class="sxs-lookup"><span data-stu-id="fddda-131">Gateway Topologies</span></span>

<span data-ttu-id="fddda-132">게이트웨이 배포의 기본적인 사항을 고려 하는 경우 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="fddda-132">When you consider the fundamental questions of gateway deployment, follow these steps:</span></span>

1.  <span data-ttu-id="fddda-133">Enterprise Voice를 사용 하 여 PSTN 연결을 제공 하려는 사이트의 개수를 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="fddda-133">Count the sites at which you want to provide PSTN connectivity by using Enterprise Voice.</span></span>

2.  <span data-ttu-id="fddda-134">각 사이트의 트래픽 (사용자 수 및 사용자별 시간당 평균 통화 횟수)을 예측 합니다.</span><span class="sxs-lookup"><span data-stu-id="fddda-134">Estimate the traffic at each site (number of users and average number of calls per hour per user).</span></span>

3.  <span data-ttu-id="fddda-135">각 사이트에 예상 되는 트래픽을 처리 하기 위한 게이트웨이를 하나 이상 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="fddda-135">Deploy one or more gateways at each site to handle the anticipated traffic.</span></span>

<span data-ttu-id="fddda-136">결과로 생성 되는 분산 게이트웨이 토폴로지는 다음 그림에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fddda-136">The resulting distributed gateway topology is shown in the following figure.</span></span>

<span data-ttu-id="fddda-137">**분산 게이트웨이 토폴로지**</span><span class="sxs-lookup"><span data-stu-id="fddda-137">**Distributed gateway topology**</span></span>

<span data-ttu-id="fddda-138">![분산 게이트웨이 토폴로지 다이어그램](images/Gg398899.f0f65a0b-a462-491a-878b-4d4bf0a96f6d(OCS.15).jpg "분산 게이트웨이 토폴로지 다이어그램")</span><span class="sxs-lookup"><span data-stu-id="fddda-138">![Distributed Gateway Topology diagram](images/Gg398899.f0f65a0b-a462-491a-878b-4d4bf0a96f6d(OCS.15).jpg "Distributed Gateway Topology diagram")</span></span>

<span data-ttu-id="fddda-139">이 토폴로지를 사용 하는 경우 각 사이트 및 사이트 간 통화 간의 통화가 인트라넷을 통해 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="fddda-139">With this topology, calls among workers at each site and between sites are all routed over your intranet.</span></span> <span data-ttu-id="fddda-140">PSTN 통화는 기업 IP 네트워크를 통해 대상 번호의 위치에 가장 가까운 게이트웨이로 라우팅됩니다. 하지만 조직에서 하나 이상의 대륙에 걸쳐 있는 수십 ~ 수백 또는 수천 대의 사이트를 지 원하는 경우에는 많은 금융 기관 및 기타 대규모 기업이 어떤 작업을 수행 하나요?</span><span class="sxs-lookup"><span data-stu-id="fddda-140">Calls to the PSTN are routed over the enterprise IP network to the gateways that are closest to the location of the destination numbers.But what if your organization supports dozens or hundreds or even thousands of sites spread across one or more continents, as many financial institutions and other large enterprises do?</span></span> <span data-ttu-id="fddda-141">이러한 경우 각 사이트에 별도의 게이트웨이를 배포 하는 것은 실용적이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="fddda-141">In such cases, deploying a separate gateway at each site is not practical.</span></span>

<span data-ttu-id="fddda-142">이 문제를 해결 하기 위해 많은 대규모 회사에서는 다음 그림에 나와 있는 것 처럼 하나 또는 몇 개의 대규모 전화 통신 중앙 사이트를 배포 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fddda-142">To address this issue, many large companies prefer to deploy one or a few large telephony central sites, as shown in the following figure.</span></span>

<span data-ttu-id="fddda-143">**전화 통신 중앙 사이트 토폴로지**</span><span class="sxs-lookup"><span data-stu-id="fddda-143">**Telephony central site topology**</span></span>

<span data-ttu-id="fddda-144">![데이터 센터 게이트웨이 토폴로지](images/Gg398899.927f4808-bf74-405a-be20-2cd9cd87af6d(OCS.15).jpg "데이터 센터 게이트웨이 토폴로지")</span><span class="sxs-lookup"><span data-stu-id="fddda-144">![Data center gateway topology](images/Gg398899.927f4808-bf74-405a-be20-2cd9cd87af6d(OCS.15).jpg "Data center gateway topology")</span></span>

<span data-ttu-id="fddda-145">이 토폴로지에서는 예상 사용자 부하를 수용할 수 있는 여러 대규모 게이트웨이가 각 중앙 사이트에 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fddda-145">In this topology, several large gateways sufficient to accommodate the anticipated user load are deployed at each central site.</span></span> <span data-ttu-id="fddda-146">기업의 사용자에 대 한 모든 통화는 회사 전화 서비스 공급자가 중앙 사이트에 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="fddda-146">All calls to users in the enterprise are forwarded by the company's telephone service provider to a central site.</span></span> <span data-ttu-id="fddda-147">중앙 사이트의 라우팅 논리는 통화를 인트라넷 이나 PSTN으로 라우팅해야 하는지를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fddda-147">Routing logic at the central site determines whether the call should be routed over the intranet or to the PSTN.</span></span>

</div>

<div>

## <a name="gateway-location"></a><span data-ttu-id="fddda-148">게이트웨이 위치</span><span class="sxs-lookup"><span data-stu-id="fddda-148">Gateway Location</span></span>

<span data-ttu-id="fddda-149">게이트웨이 위치에 따라 선택한 게이트웨이 유형 및 구성 방법이 결정 될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fddda-149">Gateway location may also determine the types of gateways that you choose and how they are configured.</span></span> <span data-ttu-id="fddda-150">PSTN 프로토콜이 수십 개 있는데, 이러한 프로토콜은 전세계 표준에 해당 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fddda-150">There are dozens of PSTN protocols, none of which is a worldwide standard.</span></span> <span data-ttu-id="fddda-151">모든 게이트웨이가 단일 국가/지역에 있는 경우에는 문제가 되지 않지만 여러 국가/지역에서 게이트웨이를 찾는 경우 각 국가/지역의 PSTN 표준에 따라 각 게이트웨이를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fddda-151">If all your gateways are located in a single country/region, this is not an issue, but if you locate gateways in several countries/regions, each must be configured according to the PSTN standards of that country/region.</span></span> <span data-ttu-id="fddda-152">또한 캐나다와 같은 작업을 위해 인증 된 게이트웨이는 인도, 브라질 또는 유럽 연합에서 인증 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fddda-152">Moreover, gateways that are certified for operation in, for example, Canada, may not be certified in India, Brazil, or the European Union.</span></span>

</div>

<div>

## <a name="gateway-size-and-number"></a><span data-ttu-id="fddda-153">게이트웨이 크기 및 번호</span><span class="sxs-lookup"><span data-stu-id="fddda-153">Gateway Size and Number</span></span>

<span data-ttu-id="fddda-154">대부분의 조직이 배포 하는 PSTN 게이트웨이 크기는 2에서 960 까지의 포트까지 고려 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fddda-154">The PSTN gateways that most organizations will consider deploying range in size from 2 to as many as 960 ports.</span></span> <span data-ttu-id="fddda-155">(게이트웨이는 훨씬 크지만 전화 서비스 공급자가 주로 사용 합니다.) 조직에 필요한 포트 수를 예상할 때 다음 지침을 따르십시오.</span><span class="sxs-lookup"><span data-stu-id="fddda-155">(There are even larger gateways, but these are used mainly by telephone service providers.) When estimating the number of ports your organization requires, use the following guidelines:</span></span>

  - <span data-ttu-id="fddda-156">가벼운 전화 통신 사용량이 많은 조직 (시간당 사용자 당 PSTN 통화 1 개)은 15 명의 사용자 마다 하나의 포트를 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fddda-156">Organizations with light telephony usage (one PSTN call per user per hour) should allocate one port for every 15 users.</span></span> <span data-ttu-id="fddda-157">예를 들어 사용자가 20 명인 경우 두 개의 포트가 있는 게이트웨이가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="fddda-157">For example, if you have 20 users, you will require a gateway with two ports.</span></span>

  - <span data-ttu-id="fddda-158">일반 전화 통신 사용량이 있는 조직 (시간당 사용자 당 PSTN 호출 두 개)은 10 명의 사용자 마다 하나의 포트를 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fddda-158">Organizations with moderate telephony usage (two PSTN calls per user per hour) should allocate one port for every 10 users.</span></span> <span data-ttu-id="fddda-159">예를 들어 100 명의 사용자가 있는 경우 하나 이상의 게이트웨이에서 할당 된 포트가 총 10 개 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="fddda-159">For example, if you have 100 users, you will require a total of 10 ports allocated among one or more gateways.</span></span>

  - <span data-ttu-id="fddda-160">전화 통신 사용량이 많은 조직 (시간당 사용자 당 3 명 이상의 PSTN 통화)은 5 명의 사용자 마다 포트를 하나씩 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fddda-160">Organizations with heavy telephony usage (three or more PSTN calls per user per hour) should allocate one port for every five users.</span></span> <span data-ttu-id="fddda-161">예를 들어 47000 명의 사용자가 있는 경우 10 개 이상의 게이트웨이 간에 총 9400 포트가 할당 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fddda-161">For example, if you have 47,000 users, you will require a total of 9,400 ports allocated among at least 10 large gateways.</span></span>

  - <span data-ttu-id="fddda-162">조직의 사용자 수 나 트래픽 양이 증가 함에 따라 추가 포트를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fddda-162">Additional ports can be acquired as the number of users or amount of traffic in your organization increases.</span></span>

<span data-ttu-id="fddda-163">지원 해야 하는 모든 사용자에 대해 더 적은 수의 게이트웨이를 배포 하는 것을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fddda-163">For any given number of users you must support, you have the choice of deploying fewer, larger gateways, or smaller ones.</span></span> <span data-ttu-id="fddda-164">한 가지 게이트웨이가 작동 하지 않는 경우에는 조직에 대해 최소 두 개의 게이트웨이를 사용 하 여 가용성을 유지 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fddda-164">As a rule, a minimum of two gateways for an organization is recommended to maintain availability if one gateway fails.</span></span>

<span data-ttu-id="fddda-165">배포 하는 각 PSTN 게이트웨이에는 해당 중재 서버가 하나 이상 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fddda-165">Each PSTN gateway that you deploy must have at least one corresponding Mediation Server.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

