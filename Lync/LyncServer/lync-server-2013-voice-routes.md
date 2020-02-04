---
title: 'Lync Server 2013: 음성 경로'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Voice routes
ms:assetid: a2ddf327-2ec4-407b-af0f-276f2b13eefd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412757(v=OCS.15)
ms:contentKeyID: 48185038
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 42aa810f40a6c00c7f2779acdf39caf39d7b2f07
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758590"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voice-routes-in-lync-server-2013"></a><span data-ttu-id="4dca1-102">Lync Server 2013의 음성 경로</span><span class="sxs-lookup"><span data-stu-id="4dca1-102">Voice routes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4dca1-103">_**마지막으로 수정한 주제:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="4dca1-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="4dca1-104">통화 경로는 Lync Server가 엔터프라이즈 음성 사용자가 설정한 아웃 바운드 통화를 처리 하는 방법을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4dca1-104">Call routes specify how Lync Server handles outbound calls placed by Enterprise Voice users.</span></span> <span data-ttu-id="4dca1-105">사용자가 번호로 전화를 걸면 프런트 엔드 서버는 필요한 경우 다이얼 문자열을 E. f a f a i a p i 형식으로 표준화 하 여 SIP URI와 일치 시 키 려 고 합니다.</span><span class="sxs-lookup"><span data-stu-id="4dca1-105">When a user dials a number, the Front End Server normalizes the dial string to E.164 format, if necessary, and attempts to match it to a SIP URI.</span></span> <span data-ttu-id="4dca1-106">서버에서 일치 하는 항목을 만들 수 없는 경우에는 해당 번호를 기반으로 나가는 호출 라우팅 논리를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4dca1-106">If the server cannot make the match, it applies outgoing call routing logic based on the number.</span></span> <span data-ttu-id="4dca1-107">해당 논리를 정의 하는 마지막 단계는 각 다이얼 플랜에 나열 된 각 대상 전화 번호 집합에 대해 별도의 명명 된 호출 경로를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4dca1-107">The final step in defining that logic is to create a separate named call route for each set of destination phone numbers that are listed in each dial plan.</span></span>

<span data-ttu-id="4dca1-108">아웃 바운드 통화 경로를 정의 하기 전에 다음 단계를 완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4dca1-108">Before you define outbound call routes, you should complete the following steps:</span></span>

  - <span data-ttu-id="4dca1-109">하나 이상의 trunks를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="4dca1-109">Deploy one or more trunks.</span></span>

  - <span data-ttu-id="4dca1-110">사이트, 개인 및 연락처 개체에 필요한 경우 다이얼 플랜을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4dca1-110">Create dial plans as needed for sites, individuals, and Contact objects.</span></span>

  - <span data-ttu-id="4dca1-111">PSTN (공개 교환 전화 네트워크) 사용 레코드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4dca1-111">Create public switched telephone network (PSTN) usage records.</span></span>

<span data-ttu-id="4dca1-112">또한 아웃 바운드 통화 라우팅을 사용 하려면 하나 이상의 음성 정책을 만들어 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4dca1-112">Additionally, to enable outbound call routing, you must create and assign one or more voice policies.</span></span> <span data-ttu-id="4dca1-113">아웃 바운드 통화 경로를 정의 하기 전이나 후에이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4dca1-113">You can do this either before or after you define outbound call routes.</span></span>

<span data-ttu-id="4dca1-114">각 경로에 대해 다음을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4dca1-114">For each route, you must specify:</span></span>

  - <span data-ttu-id="4dca1-115">경로를 쉽게 식별할 수 있는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4dca1-115">A name by which the route can be easily identified.</span></span>

  - <span data-ttu-id="4dca1-116">이름 만으로는 경로를 설명 하기에 충분 하지 않을 수 있는 경우에는 선택적 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="4dca1-116">An optional description in cases where the name alone may not be sufficient to describe the route.</span></span>

  - <span data-ttu-id="4dca1-117">경로가 적용 되는 대상 전화 번호를 식별 하는 정규식 일치 패턴으로, 일치 패턴이 적용 되지 않는 예외와 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4dca1-117">The regular expression matching pattern that identifies the destination phone numbers to which the route is applied, along with exceptions to which the matching pattern is not to be applied.</span></span>

  - <span data-ttu-id="4dca1-118">경로에 할당할 하나 이상의 trunks.</span><span class="sxs-lookup"><span data-stu-id="4dca1-118">One or more trunks that you want to assign to the route.</span></span>

  - <span data-ttu-id="4dca1-119">대상 전화 번호 정규식과 일치 하는 숫자를 호출 하기 위해 사용자가 가져야 하는 PSTN 사용 레코드입니다.</span><span class="sxs-lookup"><span data-stu-id="4dca1-119">The PSTN usage records that users must have in order to call numbers matching the destination phone number regular expression.</span></span>

<span data-ttu-id="4dca1-120">Lync Server 제어판에서 통화 경로를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4dca1-120">You can specify call routes in the Lync Server Control Panel.</span></span> <span data-ttu-id="4dca1-121">이러한 통화 경로는 Lync Server가 PSTN으로 향하는 통화를 라우팅하는 데 사용 하는 서버 라우팅 테이블을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="4dca1-121">These call routes populate the server routing table, which Lync Server uses to route calls that are destined for the PSTN.</span></span>

<div>

## <a name="mn-trunk-support"></a><span data-ttu-id="4dca1-122">M:N 트렁크 지원</span><span class="sxs-lookup"><span data-stu-id="4dca1-122">M:N Trunk Support</span></span>

<span data-ttu-id="4dca1-123">Lync Server는 통화가 PSTN으로 라우팅되는 방법에 유연성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4dca1-123">Lync Server provides flexibility in how calls are routed to the PSTN.</span></span> <span data-ttu-id="4dca1-124">음성 경로는 특정 음성 통화에 사용할 수 있는 PSTN에 대 한 trunks 집합을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4dca1-124">A voice route specifies a set of trunks to the PSTN that can be used for a particular voice call.</span></span> <span data-ttu-id="4dca1-125">트렁크는 중재 서버와 포트 번호를 PSTN 게이트웨이와 수신 포트 번호와 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="4dca1-125">A trunk associates a Mediation Server and a port number with a PSTN gateway and listening port number.</span></span> <span data-ttu-id="4dca1-126">이 논리 연결을 사용 하면 중재 서버를 여러 게이트웨이에 연결 하 고 동일한 게이트웨이에 대해 여러 연결을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4dca1-126">This logical association enables a Mediation Server to be associated with multiple gateways and have multiple connections to the same gateway.</span></span> <span data-ttu-id="4dca1-127">통화 경로를 정의할 때 해당 경로와 연결 된 trunks를 지정 하지만 해당 경로와 연결 되는 중재 서버를 지정 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4dca1-127">When defining a call route, you specify the trunks associated with that route, but you do not specify which Mediation Servers are associated with the route.</span></span> <span data-ttu-id="4dca1-128">중재 서버와 PSTN 게이트웨이, IP-Pbx 및 SBCs (세션 경계 컨트롤러) 간의 관계를 정의 하 여 trunks를 만들려면 토폴로지 작성기를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4dca1-128">To create trunks by defining the relationships between Mediation Servers and PSTN gateways, IP-PBXs, and Session Border Controllers (SBCs), use the Topology Builder.</span></span>

</div>

<div>

## <a name="least-cost-routing"></a><span data-ttu-id="4dca1-129">가장 저렴 한 라우팅</span><span class="sxs-lookup"><span data-stu-id="4dca1-129">Least-Cost Routing</span></span>

<span data-ttu-id="4dca1-130">다양 한 번호를 라우팅할 trunks을 지정 하는 기능을 통해 가장 저렴 한 비용을 초래 하는 경로를 결정 하 고 그에 따라 적절 하 게 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4dca1-130">The ability to specify the trunks to which various numbers are routed enables you to determine which routes incur the lowest costs and implement them accordingly.</span></span> <span data-ttu-id="4dca1-131">Trunks 선택의 일반적인 규칙은 시외 전화 요금을 최소화 하기 위해 대상 번호 위치에 가장 가까운 게이트웨이로 트렁크를 선택 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4dca1-131">The general rule in selecting trunks is to choose the trunk with the closest gateway to the location of the destination number in order to minimize long-distance charges.</span></span> <span data-ttu-id="4dca1-132">예를 들어 뉴욕에 있고 로마에서 숫자를 호출 하는 경우에는 IP 네트워크를 통해 해당 게이트웨이를 사용 하 여 연결 되는 트렁크에 연결 하 고 시내 통화만 충전 합니다.</span><span class="sxs-lookup"><span data-stu-id="4dca1-132">For example, if you are in New York and calling a number in Rome, you would carry the call over the IP network to the trunk with the gateway in your Rome office, thereby incurring a charge only for a local call.</span></span>

<span data-ttu-id="4dca1-133">저렴 한 라우팅 사용 방법에 대 한 예는 다음을 고려 하세요. Fabrikam은 미국 트렁크를 사용 하 여 미국 번호를 전화 걸 수 있도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4dca1-133">For an example of how least-cost routing might be used, consider the following: Fabrikam decides to enable German users to dial U.S. numbers by using the U.S. trunk.</span></span> <span data-ttu-id="4dca1-134">또한 Fabrikam은 미국 Lync Server 사용자에서 독일 및 인접 한 국가/지역으로의 모든 통화가 독일의 게이트웨이가 있는 트렁크에서 종료 되도록 시스템을 구성 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="4dca1-134">Fabrikam also wants to configure the system so that all calls from U.S. Lync Server users to Germany and adjacent countries/regions terminate on the trunk with the gateway in Germany.</span></span> <span data-ttu-id="4dca1-135">예를 들어 독일에서 오스트리아로 거는 통화가 미국에서 오스트리아로 거는 통화 보다 저렴 하기 때문에이 라우팅이 비용 절약을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4dca1-135">This routing will save money, because a call from Germany to Austria, for example, is less expensive than a call from the U.S. to Austria.</span></span>

</div>

<div>

## <a name="translating-outbound-dial-strings"></a><span data-ttu-id="4dca1-136">아웃 바운드 다이얼 문자열 번역</span><span class="sxs-lookup"><span data-stu-id="4dca1-136">Translating Outbound Dial Strings</span></span>

<span data-ttu-id="4dca1-137">바로 선행 작업 등의 Lync Server 2013에서는 역 번호 조회 (RNL)를 수행 하기 위해 모든 다이얼 문자열이 E 164 형식으로 정규화 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4dca1-137">Lync Server 2013, like its immediate predecessors, requires all dial strings to be normalized to E.164 format for the purpose of performing reverse number lookup (RNL).</span></span> <span data-ttu-id="4dca1-138">지역 전화 걸기 형식으로 번역 된 숫자가 필요한 게이트웨이 또는 개인 분기 교환 (Pbx)이 있는 trunks 경우 Lync Server 2013에서는 호출 되는 번호 (예: 요청 URI)를 조작 하는 데 도움이 되는 하나 이상의 규칙을 만들 수 있습니다. 트렁크.</span><span class="sxs-lookup"><span data-stu-id="4dca1-138">For trunks with gateways or private branch exchanges (PBXs) that require numbers translated in local dialing formats, Lync Server 2013 enables you to create one or more rules that assist in manipulating the called number (i.e. Request URI) prior to routing it to the trunk.</span></span> <span data-ttu-id="4dca1-139">예를 들어 다이얼 문자열의 머리에서 + 44을 제거 하 고 0144으로 대체 하는 규칙을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4dca1-139">For example, you could write a rule to remove +44 from the head of a dial string and replace it with 0144.</span></span>

<span data-ttu-id="4dca1-140">Lync Server 2013를 사용 하 여, 트렁크에 라우팅 하기 전에 전화 번호를 조작 하는 데 도움이 되는 하나 이상의 규칙을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4dca1-140">With Lync Server 2013, it is possible to create one or more rules that assist in manipulating the calling number prior to routing it to the trunk.</span></span>

<span data-ttu-id="4dca1-141">Trunks에 게이트웨이를 연결 하는 포트 쌍을 조정 서버: 포트 쌍으로 사용 하는 경우, 유사한 지역 전화 접속 요구 사항이 있는 trunks를 그룹화 하는 것이 유용할 수 있으며 따라서 필요한 번역 규칙의 수와 기록 하는 데 걸리는 시간이 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="4dca1-141">In planning your trunks that associate gateways:port pairs with Mediation Server:port pairs, it may be useful to group trunks with similar local dialing requirements, and therefore reduce the number of required translation rules and the time it takes to write them.</span></span>

</div>

<div>

## <a name="configuring-caller-id"></a><span data-ttu-id="4dca1-142">발신자 ID 구성</span><span class="sxs-lookup"><span data-stu-id="4dca1-142">Configuring Caller ID</span></span>

<span data-ttu-id="4dca1-143">Lync Server는 아웃 바운드 통화에 대 한 발신자 ID를 조작 하는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4dca1-143">Lync Server provides a way to manipulate the caller ID for outbound calls.</span></span> <span data-ttu-id="4dca1-144">예를 들어 조직에서 직원의 직접 전화 걸기 확장을 마스크 하 고 일반 회사 또는 부서별 번호로 바꾸는 경우 관리자는 Lync Server 제어판을 사용 하 여 발신자 ID를 표시 하지 않고 지정 된 대체 발신자 ID.</span><span class="sxs-lookup"><span data-stu-id="4dca1-144">For example, if an organization wants to mask employees’ direct-dial extensions and replace them with the generic corporate or departmental number, an administrator can do that by using Lync Server Control Panel to suppress the caller ID and replace it with a specified alternative caller ID.</span></span> <span data-ttu-id="4dca1-145">라우팅 논리를 계획 하는 경우, 심지어 모든 직원에 대해이 옵션을 사용할 수 있는 개인, 그룹, 사이트 등을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4dca1-145">In planning your routing logic, consider which individuals, groups, sites you’ll want this option for—perhaps, even, for all employees.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4dca1-146">PSTN을 통해 경로를 전환 하는 경우 원래 발신자 ID 대신 일반 발신자 ID가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4dca1-146">For calls that are rerouted over the PSTN, the generic caller ID will be presented instead of the original caller ID.</span></span> <span data-ttu-id="4dca1-147">이로 인해 호출이 호출에서 방해 금지 또는 피호출자가 구성한 개인 정보 설정이 무시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4dca1-147">This can cause the call to bypass Do Not Disturb or privacy settings that the callee may have configured.</span></span>



</div>

</div>

<div>

## <a name="additional-routing-logic"></a><span data-ttu-id="4dca1-148">추가 라우팅 논리</span><span class="sxs-lookup"><span data-stu-id="4dca1-148">Additional Routing Logic</span></span>

<span data-ttu-id="4dca1-149">아웃 바운드 통화 경로를 만들 때 라우팅 논리에 영향을 줄 수 있는 다음 요소에 유의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4dca1-149">In creating outbound call routes, you should be aware of the following factors that can affect routing logic:</span></span>

  - <span data-ttu-id="4dca1-150">페더레이션 경계를 통해 호출이 설정 되 면 URI의 도메인 부분을 사용 하 여 아웃 바운드 라우팅 논리 적용을 담당 하는 엔터프라이즈에 대 한 통화를 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="4dca1-150">Where a call is established over a federated boundary, the domain portion of the URI is used to route the call over to the enterprise that is responsible for applying the outbound routing logic.</span></span>

  - <span data-ttu-id="4dca1-151">요청 URI의 도메인 부분에 엔터프라이즈에 대해 지원 되는 도메인이 포함 되어 있지 않은 경우 서버의 아웃 바운드 라우팅 구성 요소는 통화를 처리 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4dca1-151">If the domain portion of the request URI does not contain a supported domain for the enterprise, the outbound routing component on the server does not process the call.</span></span>

  - <span data-ttu-id="4dca1-152">사용자가 엔터프라이즈 음성을 사용할 수 없는 경우 서버는 적절 하 게 다른 라우팅 논리를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4dca1-152">If a user is not enabled for Enterprise Voice, the server applies other routing logic, as appropriate.</span></span>

  - <span data-ttu-id="4dca1-153">통화가 완전히 점유 된 게이트웨이 (모든 트렁크 회선을 사용 중인 경우)로 라우팅된 경우 게이트웨이는 전화를 거부 하 고 아웃 바운드 라우팅 논리는 통화를 다음 최소 순위의 경로로 리디렉션합니다.</span><span class="sxs-lookup"><span data-stu-id="4dca1-153">If a call is routed to a gateway that is fully occupied (all trunk lines are busy), the gateway rejects the call and the outbound routing logic redirects the call to the next-least-cost route.</span></span> <span data-ttu-id="4dca1-154">소규모 사무실 해외 (예: Zurich)에 대 한 게이트웨이가 실제로 스위스에 대 한 국제 전화를 위해 매우 많은 양의 비로컬 트래픽을 가질 수 있기 때문에이 주의를 기울여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4dca1-154">Give this careful consideration, because a gateway sized for a small office overseas (for example, Zurich) may actually carry a significant amount of nonlocal traffic for international calls to Switzerland.</span></span> <span data-ttu-id="4dca1-155">이 추가 트래픽에 대해 게이트웨이가 적절 한 크기를 지정 하지 않으면 스위스에 대 한 호출이 독일의 게이트웨이를 통해 라우팅될 수 있으며, 결과적으로 유료 요금이 더 커집니다.</span><span class="sxs-lookup"><span data-stu-id="4dca1-155">If the gateway is not correctly sized for this additional traffic, calls to Switzerland may be routed by way of a gateway in Germany, resulting in larger toll charges.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

