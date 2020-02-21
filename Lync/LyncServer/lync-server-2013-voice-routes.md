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
ms.openlocfilehash: 434f7cc92fd6a6bc284074cce476f4bc3b2eca01
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211074"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="voice-routes-in-lync-server-2013"></a><span data-ttu-id="237b3-102">Lync Server 2013의 음성 경로</span><span class="sxs-lookup"><span data-stu-id="237b3-102">Voice routes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="237b3-103">_**마지막으로 수정 된 항목:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="237b3-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="237b3-104">Call 경로 Lync Server가 Enterprise Voice 사용자가 설정한 아웃 바운드 호출을 처리 하는 방법을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="237b3-104">Call routes specify how Lync Server handles outbound calls placed by Enterprise Voice users.</span></span> <span data-ttu-id="237b3-105">사용자가 전화를 걸 때 프런트 엔드 서버는 필요한 경우 해당 다이얼 문자열을 E. 164 형식으로 정규화 하 고 SIP URI와 일치 시 키 려 고 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="237b3-105">When a user dials a number, the Front End Server normalizes the dial string to E.164 format, if necessary, and attempts to match it to a SIP URI.</span></span> <span data-ttu-id="237b3-106">일치시킬 수 없는 경우 서버는 해당 번호를 기반으로 발신 전화 라우팅 논리를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="237b3-106">If the server cannot make the match, it applies outgoing call routing logic based on the number.</span></span> <span data-ttu-id="237b3-107">해당 논리를 정의하는 마지막 단계는 각 다이얼 플랜에 나열된 각 대상 전화 번호 집합에 대한 별도의 명명된 통화 경로를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="237b3-107">The final step in defining that logic is to create a separate named call route for each set of destination phone numbers that are listed in each dial plan.</span></span>

<span data-ttu-id="237b3-108">아웃바운드 통화 경로를 정의하기 전에 다음 단계를 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="237b3-108">Before you define outbound call routes, you should complete the following steps:</span></span>

  - <span data-ttu-id="237b3-109">하나 이상의 트렁크를 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="237b3-109">Deploy one or more trunks.</span></span>

  - <span data-ttu-id="237b3-110">사이트, 개인 및 연락처 개체에 필요한 만큼 다이얼 플랜을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="237b3-110">Create dial plans as needed for sites, individuals, and Contact objects.</span></span>

  - <span data-ttu-id="237b3-111">PSTN(공중 전화망) 사용 레코드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="237b3-111">Create public switched telephone network (PSTN) usage records.</span></span>

<span data-ttu-id="237b3-p102">또한 아웃바운드 통화 라우팅을 사용하도록 설정하려면 하나 이상의 음성 정책을 만들고 할당해야 합니다. 이 작업은 아웃바운드 통화 경로를 정의하기 전이나 후에 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="237b3-p102">Additionally, to enable outbound call routing, you must create and assign one or more voice policies. You can do this either before or after you define outbound call routes.</span></span>

<span data-ttu-id="237b3-114">각 경로에 대해 다음을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="237b3-114">For each route, you must specify:</span></span>

  - <span data-ttu-id="237b3-115">경로를 쉽게 식별할 수 있는 이름</span><span class="sxs-lookup"><span data-stu-id="237b3-115">A name by which the route can be easily identified.</span></span>

  - <span data-ttu-id="237b3-116">이름만으로 경로를 설명하기에 충분하지 않은 경우의 선택적 설명</span><span class="sxs-lookup"><span data-stu-id="237b3-116">An optional description in cases where the name alone may not be sufficient to describe the route.</span></span>

  - <span data-ttu-id="237b3-117">경로를 적용할 대상 전화 번호를 식별하는 정규식 일치 패턴과 일치 패턴을 적용하지 않을 예외</span><span class="sxs-lookup"><span data-stu-id="237b3-117">The regular expression matching pattern that identifies the destination phone numbers to which the route is applied, along with exceptions to which the matching pattern is not to be applied.</span></span>

  - <span data-ttu-id="237b3-118">경로를 할당할 하나 이상의 트렁크</span><span class="sxs-lookup"><span data-stu-id="237b3-118">One or more trunks that you want to assign to the route.</span></span>

  - <span data-ttu-id="237b3-119">대상 전화 번호 정규식과 일치하는 번호로 전화를 걸기 위해 사용자에게 필요한 PSTN 사용 레코드</span><span class="sxs-lookup"><span data-stu-id="237b3-119">The PSTN usage records that users must have in order to call numbers matching the destination phone number regular expression.</span></span>

<span data-ttu-id="237b3-120">Lync Server 제어판에서 call 경로를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="237b3-120">You can specify call routes in the Lync Server Control Panel.</span></span> <span data-ttu-id="237b3-121">이러한 호출 경로는 Lync Server가 PSTN으로 향하는 통화를 라우팅하는 데 사용 하는 서버 라우팅 테이블을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="237b3-121">These call routes populate the server routing table, which Lync Server uses to route calls that are destined for the PSTN.</span></span>

<div>

## <a name="mn-trunk-support"></a><span data-ttu-id="237b3-122">M:N 트렁크 지원</span><span class="sxs-lookup"><span data-stu-id="237b3-122">M:N Trunk Support</span></span>

<span data-ttu-id="237b3-123">Lync Server에서는 통화가 PSTN으로 라우팅되는 방식을 유연 하 게 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="237b3-123">Lync Server provides flexibility in how calls are routed to the PSTN.</span></span> <span data-ttu-id="237b3-124">음성 경로는 특정 음성 통화에 사용할 수 있는 PSTN에 대한 트렁크 집합을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="237b3-124">A voice route specifies a set of trunks to the PSTN that can be used for a particular voice call.</span></span> <span data-ttu-id="237b3-125">트렁크는 중재 서버와 포트 번호를 PSTN 게이트웨이와 수신 대기 포트 번호와 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="237b3-125">A trunk associates a Mediation Server and a port number with a PSTN gateway and listening port number.</span></span> <span data-ttu-id="237b3-126">이 논리 연결을 사용 하면 중재 서버를 여러 게이트웨이에 연결 하 고 동일한 게이트웨이에 대해 여러 연결을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="237b3-126">This logical association enables a Mediation Server to be associated with multiple gateways and have multiple connections to the same gateway.</span></span> <span data-ttu-id="237b3-127">통화 경로를 정의 하는 경우 해당 경로와 연결 된 트렁크를 지정 하지만 경로와 연결 된 중재 서버는 지정 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="237b3-127">When defining a call route, you specify the trunks associated with that route, but you do not specify which Mediation Servers are associated with the route.</span></span> <span data-ttu-id="237b3-128">중재 서버와 PSTN 게이트웨이, IP-PBX 및 sbc (Session Border Controller) 간의 관계를 정의 하 여 트렁크을 만들려면 토폴로지 작성기를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="237b3-128">To create trunks by defining the relationships between Mediation Servers and PSTN gateways, IP-PBXs, and Session Border Controllers (SBCs), use the Topology Builder.</span></span>

</div>

<div>

## <a name="least-cost-routing"></a><span data-ttu-id="237b3-129">최소 비용 라우팅</span><span class="sxs-lookup"><span data-stu-id="237b3-129">Least-Cost Routing</span></span>

<span data-ttu-id="237b3-p105">다양한 번호가 라우팅되는 트렁크를 지정하는 기능을 사용하면 가장 적은 비용이 발생하는 경로를 확인하고 이에 따라 경로를 구현할 수 있습니다. 일반적으로 트렁크를 선택할 때는 시외 전화 요금을 최소화하기 위해 대상 번호의 위치와 가장 가까운 게이트웨이를 포함하는 트렁크를 선택합니다. 예를 들어 뉴욕에 있는 사용자가 로마에 전화를 거는 경우 IP 네트워크를 통해 로마 사무실의 게이트웨이를 포함하는 트렁크에 통화를 전달하여 시내 전화 요금만 부과되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="237b3-p105">The ability to specify the trunks to which various numbers are routed enables you to determine which routes incur the lowest costs and implement them accordingly. The general rule in selecting trunks is to choose the trunk with the closest gateway to the location of the destination number in order to minimize long-distance charges. For example, if you are in New York and calling a number in Rome, you would carry the call over the IP network to the trunk with the gateway in your Rome office, thereby incurring a charge only for a local call.</span></span>

<span data-ttu-id="237b3-133">순위가 가장 낮은 라우팅을 사용 하는 방법의 예는 다음 사항을 고려 하십시오. Fabrikam은 영어 트렁크를 사용 하 여 독일어 사용자가 미국 번호를 전화 접속할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="237b3-133">For an example of how least-cost routing might be used, consider the following: Fabrikam decides to enable German users to dial U.S. numbers by using the U.S. trunk.</span></span> <span data-ttu-id="237b3-134">또한 Fabrikam은 미국 Lync Server 사용자에서 독일 및 인접 한 국가/지역으로의 모든 통화가 독일에서 게이트웨이가 종료 되도록 시스템을 구성 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="237b3-134">Fabrikam also wants to configure the system so that all calls from U.S. Lync Server users to Germany and adjacent countries/regions terminate on the trunk with the gateway in Germany.</span></span> <span data-ttu-id="237b3-135">예를 들어 독일에서 오스트리아로 전화를 거는 통화는 미국에서 오스트리아 까지의 통화 보다 저렴 하기 때문에이 라우팅에서 비용을 절약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="237b3-135">This routing will save money, because a call from Germany to Austria, for example, is less expensive than a call from the U.S. to Austria.</span></span>

</div>

<div>

## <a name="translating-outbound-dial-strings"></a><span data-ttu-id="237b3-136">아웃바운드 전화 걸기 문자열 변환</span><span class="sxs-lookup"><span data-stu-id="237b3-136">Translating Outbound Dial Strings</span></span>

<span data-ttu-id="237b3-137">Lync Server 2013를 바로 실행 하는 경우에는 RNL (역방향 번호 조회)를 수행할 목적으로 모든 다이얼 문자열을 E. 164 형식으로 정규화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="237b3-137">Lync Server 2013, like its immediate predecessors, requires all dial strings to be normalized to E.164 format for the purpose of performing reverse number lookup (RNL).</span></span> <span data-ttu-id="237b3-138">게이트웨이 또는 Pbx (private branch exchange)가 로컬 전화 걸기 형식으로 변환 되어야 하는 트렁크 경우 Lync Server 2013를 사용 하 여 호출 된 번호 (예: 요청 URI)를 처리 하는 데 도움이 되는 하나 이상의 규칙을 만든 다음 트렁크.</span><span class="sxs-lookup"><span data-stu-id="237b3-138">For trunks with gateways or private branch exchanges (PBXs) that require numbers translated in local dialing formats, Lync Server 2013 enables you to create one or more rules that assist in manipulating the called number (i.e. Request URI) prior to routing it to the trunk.</span></span> <span data-ttu-id="237b3-139">예를 들어 전화 걸기 문자열의 시작 부분에서 +44를 제거하고 대신 0144를 넣는 규칙을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="237b3-139">For example, you could write a rule to remove +44 from the head of a dial string and replace it with 0144.</span></span>

<span data-ttu-id="237b3-140">Lync Server 2013를 사용 하 여 트렁크로 라우팅하기 전에 호출 번호를 조작 하는 데 도움이 되는 하나 이상의 규칙을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="237b3-140">With Lync Server 2013, it is possible to create one or more rules that assist in manipulating the calling number prior to routing it to the trunk.</span></span>

<span data-ttu-id="237b3-141">중재 서버: 포트 쌍과 함께 게이트웨이를 연결 하는 트렁크를 계획 하는 경우, 유사한 로컬 전화 걸기 요구 사항을 가진 트렁크을 그룹화 하 여 필요한 변환 규칙 수와이를 작성 하는 데 걸리는 시간을 줄이는 것이 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="237b3-141">In planning your trunks that associate gateways:port pairs with Mediation Server:port pairs, it may be useful to group trunks with similar local dialing requirements, and therefore reduce the number of required translation rules and the time it takes to write them.</span></span>

</div>

<div>

## <a name="configuring-caller-id"></a><span data-ttu-id="237b3-142">발신자 번호 구성</span><span class="sxs-lookup"><span data-stu-id="237b3-142">Configuring Caller ID</span></span>

<span data-ttu-id="237b3-143">Lync Server는 아웃 바운드 호출에 대 한 발신자 ID를 조작할 수 있는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="237b3-143">Lync Server provides a way to manipulate the caller ID for outbound calls.</span></span> <span data-ttu-id="237b3-144">예를 들어 조직에서 직원의 직접 전화 걸기 내선 번호를 마스크 하 고 일반 회사 또는 부서 번호로 교체 하려는 경우 관리자는 Lync Server 제어판을 사용 하 여 발신자 ID를 억제 하 고 지정한 대체 발신자 ID</span><span class="sxs-lookup"><span data-stu-id="237b3-144">For example, if an organization wants to mask employees’ direct-dial extensions and replace them with the generic corporate or departmental number, an administrator can do that by using Lync Server Control Panel to suppress the caller ID and replace it with a specified alternative caller ID.</span></span> <span data-ttu-id="237b3-145">라우팅 논리를 계획할 때는 개인, 그룹, 사이트 또는 모든 직원 중 어떤 대상에 대해 발신자 번호를 대체할지 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="237b3-145">In planning your routing logic, consider which individuals, groups, sites you’ll want this option for—perhaps, even, for all employees.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="237b3-p109">PSTN을 통해 다시 라우팅된 통화의 경우 원래 발신자 번호 대신 일반 발신자 번호가 표시됩니다. 따라서 수신자가 방해 금지 또는 개인 정보 보호 설정을 구성한 경우 통화가 이러한 설정을 바이패스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="237b3-p109">For calls that are rerouted over the PSTN, the generic caller ID will be presented instead of the original caller ID. This can cause the call to bypass Do Not Disturb or privacy settings that the callee may have configured.</span></span>



</div>

</div>

<div>

## <a name="additional-routing-logic"></a><span data-ttu-id="237b3-148">추가 라우팅 논리</span><span class="sxs-lookup"><span data-stu-id="237b3-148">Additional Routing Logic</span></span>

<span data-ttu-id="237b3-149">아웃바운드 통화 경로를 만드는 경우 라우팅 논리에 영향을 주는 다음 요소에 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="237b3-149">In creating outbound call routes, you should be aware of the following factors that can affect routing logic:</span></span>

  - <span data-ttu-id="237b3-150">요청 URI의 도메인 부분에 지원되는 엔터프라이즈 도메인이 포함되어 있지 않으면 해당 서버의 아웃바운드 라우팅 구성 요소에서 통화를 처리하지 않습니다. 예를 들어 페더레이션 경계를 넘어 통화가 설정되는 특정 시나리오에서 URI의 도메인 부분은 아웃바운드 라우팅 논리를 적용할 책임이 있는 엔터프라이즈로 통화를 라우팅하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="237b3-150">Where a call is established over a federated boundary, the domain portion of the URI is used to route the call over to the enterprise that is responsible for applying the outbound routing logic.</span></span>

  - <span data-ttu-id="237b3-151">요청 URI의 도메인 부분에 지원되는 엔터프라이즈 도메인이 포함되어 있지 않으면 해당 서버의 아웃바운드 라우팅 구성 요소에서 통화를 처리하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="237b3-151">If the domain portion of the request URI does not contain a supported domain for the enterprise, the outbound routing component on the server does not process the call.</span></span>

  - <span data-ttu-id="237b3-152">사용자가 Enterprise Voice를 사용할 수 있도록 설정 되지 않은 경우 서버에서 다른 라우팅 논리를 적절 하 게 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="237b3-152">If a user is not enabled for Enterprise Voice, the server applies other routing logic, as appropriate.</span></span>

  - <span data-ttu-id="237b3-p110">통화가 모두 사용 중인(모든 트렁크 회선이 통화 중) 게이트웨이로 라우팅되면 게이트웨이에서 통화를 거부하며 아웃바운드 라우팅 논리가 통화를 다음 최소 비용 경로로 리디렉션합니다. 소규모 해외 지사(예: 취리히)용 크기의 게이트웨이에서 실제로 스위스 국제 전화를 위한 시내가 아닌 많은 트래픽을 전송할 수 있으므로 이를 신중하게 고려해야 합니다. 이 추가 트래픽과 관련해서 게이트웨이 크기가 올바르게 지정되지 않은 경우 스위스에 대한 통화가 독일의 게이트웨이를 통해 라우팅되어 전화 요금이 훨씬 늘어날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="237b3-p110">If a call is routed to a gateway that is fully occupied (all trunk lines are busy), the gateway rejects the call and the outbound routing logic redirects the call to the next-least-cost route. Give this careful consideration, because a gateway sized for a small office overseas (for example, Zurich) may actually carry a significant amount of nonlocal traffic for international calls to Switzerland. If the gateway is not correctly sized for this additional traffic, calls to Switzerland may be routed by way of a gateway in Germany, resulting in larger toll charges.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

