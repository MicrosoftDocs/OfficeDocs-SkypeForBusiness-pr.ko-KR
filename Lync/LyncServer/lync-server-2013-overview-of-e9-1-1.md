---
title: 'Lync Server 2013: E9-1-1 개요'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of E9-1-1
ms:assetid: c01e6774-bc9f-4c5b-a60b-478b7317b2b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412936(v=OCS.15)
ms:contentKeyID: 48185290
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 144f189c119653ddb02316193e78b9156fad2278
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984367"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-e9-1-1-in-lync-server-2013"></a><span data-ttu-id="b49fb-102">Lync Server 2013의 E9-1-1 개요</span><span class="sxs-lookup"><span data-stu-id="b49fb-102">Overview of E9-1-1 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b49fb-103">_**마지막으로 수정한 주제:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="b49fb-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="b49fb-104">Microsoft Lync Server 2013는 Lync 클라이언트 및 Lync Phone Edition 장치에서 향상 된 9-1-1 (E9-1) 통화를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="b49fb-104">Microsoft Lync Server 2013 supports Enhanced 9-1-1 (E9-1-1) calling from Lync clients and Lync Phone Edition devices.</span></span> <span data-ttu-id="b49fb-105">E9-1-1 용 Lync Server를 구성 하면 Lync 2013 또는 Lync Phone Edition에서 제공 하는 비상 전화에는 위치 정보 서비스 데이터베이스의 ERL (비상 응답 위치) 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b49fb-105">When you configure Lync Server for E9-1-1, emergency calls placed from Lync 2013 or Lync Phone Edition include Emergency Response Location (ERL) information from the Location Information service database.</span></span> <span data-ttu-id="b49fb-106">ERLs는 사무실 건물과 다른 다중 테 넌 트 시설에서 더 정확한 위치를 식별 하는 데 도움이 되는 도심 (즉, 거리) 주소와 기타 정보로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b49fb-106">ERLs consist of civic (that is, street) addresses and other information that helps to identify a more precise location in office buildings and other multitenant facilities.</span></span> <span data-ttu-id="b49fb-107">사용자가 비상 전화를 걸 때 Lync Server는 E9-1 서비스 공급자에 대 한 중재 서버를 통해 위치 및 콜백 정보와 함께 통화 오디오를 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="b49fb-107">When a user makes an emergency call, Lync Server routes the call audio, along with the location and callback information, through a Mediation Server to an E9-1-1 service provider.</span></span> <span data-ttu-id="b49fb-108">E9-1-1 서비스 공급자는 호출자의 도심 주소를 사용 하 여 호출자의 위치를 제공 하는 PSAP (공개 안전 응답 위치)로 통화를 라우팅하고, PSAP에서 호출자의 ERL를 조회 하는 데 사용 하는 ESQK (응급 서비스 쿼리 키)를 따라 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="b49fb-108">The E9-1-1 service provider uses the civic address of the caller to route the call to the Public Safety Answering Point (PSAP) that serves the caller's location, and sends along an Emergency Service Query Key (ESQK) that the PSAP uses to look up the caller's ERL.</span></span>

<span data-ttu-id="b49fb-109">Lync Server는 E9-1-1 서비스 공급자에 대 한 비상 통화 라우팅 두 가지 방법을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="b49fb-109">Lync Server supports two methods for routing emergency calls to an E9-1-1 service provider:</span></span>

  - <span data-ttu-id="b49fb-110">적격 E9-1-1 서비스 공급자에 대 한 SIP (세션 초기화 프로토콜) 트렁크 연결</span><span class="sxs-lookup"><span data-stu-id="b49fb-110">A Session Initiation Protocol (SIP) trunk connection to a qualified E9-1-1 service provider</span></span>

  - <span data-ttu-id="b49fb-111">PSTN (공개 교환 전화) 기반 E9-1-1 서비스 공급자에 대 한 비상 위치 Id 번호 (ELIN) 게이트웨이</span><span class="sxs-lookup"><span data-stu-id="b49fb-111">An Emergency Location Identification Number (ELIN) gateway to a public switched telephone (PSTN)-based E9-1-1 service provider</span></span>

<span data-ttu-id="b49fb-112">SIP 트렁크 E9-1-1 서비스 공급자를 사용 하는 경우 위치 정보 서비스 데이터베이스에 ERLs를 추가 하 고 E9-1-1 서비스 공급자가 유지 관리 하는 MSAG (마스터 주소 가이드)에 대해 위치 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="b49fb-112">When you use a SIP trunk E9-1-1 service provider, you add ERLs to the Location Information service database, and then validate the locations against a Master Street Address Guide (MSAG) that is maintained by the E9-1-1 service provider.</span></span> <span data-ttu-id="b49fb-113">E9-1 서비스 공급자가 위치 정보가 없거나 MSAG에 대해 유효성을 검사 하지 않은 전화를 받은 경우 E9-1 서비스 공급자는 국가/지역 긴급 통화 응답 센터 (ECRC)에 게 전화를 라우팅하고, 가능한 경우 호출자의 위치를 구두로 하 고 적절 한 PSAP에 대 한 통화를 수동으로 라우팅하는 특정 교육을 받고 있는 직원을 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="b49fb-113">If an E9-1-1 service provider receives a call that doesn’t have location information or has a location that has not been validated against the MSAG, the E9-1-1 service provider routes the call to a national/regional Emergency Call Response Center (ECRC), which is staffed with specially trained personnel who verbally obtain the caller’s location, if possible, and manually route the call to the appropriate PSAP.</span></span> <span data-ttu-id="b49fb-114">(일부 SIP 트렁크 E9-1-1 서비스 공급자는 고객에 게 PSTN 직접 내부 전화 걸기 (9-1-1) 번호를 제공 하 여 SIP 트렁크가 어떠한 이유로 든 실패 하는 경우이를 라우팅 하는 대체 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b49fb-114">(Some SIP trunk E9-1-1 service providers also provide customers with a PSTN direct inward dialing (DID) number to the ECRC, which provides an alternate means of routing 9-1-1 calls, if the SIP trunk fails for any reason.)</span></span>

<span data-ttu-id="b49fb-115">고정 위치가 있는 시간 구분 멀티플렉싱 (TDM) 및 IP 기반 개인 분기 교환 (PBX) 전화와는 달리 Lync 끝점은 매우 모바일 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b49fb-115">Unlike time division multiplexing (TDM) and IP-based private branch exchange (PBX) phones, which have fixed locations, a Lync endpoint can be very mobile.</span></span> <span data-ttu-id="b49fb-116">E9 기능을 배포 하는 경우 Lync Server는 호출자의 위치에 관계 없이 긴급 전화를 사용 하 여 호출자의 위치를 제공 하는 PSAP로 라우팅할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b49fb-116">When you deploy the E9-1-1 feature, Lync Server helps to ensure that no matter where a caller is located, the emergency call can be routed to the PSAP that serves the caller’s location.</span></span> <span data-ttu-id="b49fb-117">예를 들어 사용자의 기본 office가 Redmond, 인천에 있지만, Wichita의 지사에 있는 컴퓨터에서 비상 전화를 사용 하는 경우 SIP 트렁크 또는 PSTN 기반 E9-1-1 서비스 공급자가 통화를 Wichita의 PSAP에 라우팅합니다. Kansas , Redmond의 PSAP에는 해당 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b49fb-117">For example, if a user’s main office is located in Redmond, Washington, but the user places an emergency call from a computer in a branch office in Wichita, Kansas, the SIP trunk or PSTN-based E9-1-1 service provider will route the call to the PSAP in Wichita, not to the PSAP in Redmond.</span></span>

<span data-ttu-id="b49fb-118">게이트웨이에서 ELIN을 사용 하는 경우 위치 정보 서비스 데이터베이스에 ERLs도 추가 되지만 각 위치에 ELIN 번호를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="b49fb-118">When you use an ELIN gateway, you also add ERLs to the Location Information service database, but you include also an ELIN number for each location.</span></span> <span data-ttu-id="b49fb-119">비상 전화를 걸 때의 ELIN 번호는 비상 전화 번호가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b49fb-119">The ELIN number becomes the emergency calling number during the emergency call.</span></span> <span data-ttu-id="b49fb-120">그런 다음 PSTN 반송파가 ELINs을 자동 위치 확인 (ALI) 데이터베이스로 업로드 하는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b49fb-120">You must then make sure that your PSTN carrier uploads the ELINs to the Automatic Location Identification (ALI) database.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b49fb-121">Lync에 연결 된 아날로그 장치는 위치 정보 서비스에서 위치 정보를 받을 수 없으며, E9-1-1 서비스 공급자에 위치를 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="b49fb-121">Lync-connected analog devices cannot receive location information from the Location Information service or transmit location to the E9-1-1 service provider.</span></span> <span data-ttu-id="b49fb-122">SIP 트렁크 E9-1-1 서비스 공급자 옵션을 사용 하 고 아날로그 전화기에서 E9-1-1을 지원 해야 하는 경우 다음 두 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b49fb-122">If you use the SIP trunk E9-1-1 service provider option and need to support E9-1-1 from analog phones, you have two options:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="b49fb-123"><STRONG>전통적인 PS-ALI 옵션</STRONG>&nbsp;&nbsp;&nbsp;아날로그 전화가 배포 되는 각 사이트에 로컬 PSTN 게이트웨이가 있고 각 아날로그 전화기가 있는 경우 개인 스위치/자동 위치 식별 (PS-ALI) 서비스 공급자를 사용 하 여 아날로그 디바이스의 위치를 직접 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b49fb-123"><STRONG>Traditional PS-ALI option</STRONG>&nbsp;&nbsp;&nbsp;If you have local PSTN gateways at each site where analog phones are deployed and each analog phone has a DID, you can provision the analog device’s location directly with a Private Switch/Automatic Location Identification (PS-ALI) service provider.</span></span> <span data-ttu-id="b49fb-124">이 경우 특수 하 게 조작 된 Lync 음성 정책을 구성 하 고 아날로그 디바이스 연락처 개체에 할당 하 여 해당 전화에서 E9-1-1로 직접 전화를 걸어 사이트를 서비스 하는 PSTN 공급자에 게 로컬 게이트웨이를 라우팅 하는 대신 E9-1-1 서비스 공급자에 대 한 통화 SIP 트렁크).</span><span class="sxs-lookup"><span data-stu-id="b49fb-124">In this case, you configure specially-crafted Lync voice policies and assign them to the analog device contact objects so that E9-1-1 calls from those phones route directly through the local gateway to the PSTN provider that services the site (instead of routing the call to an E9-1-1 service provider SIP trunk).</span></span> <span data-ttu-id="b49fb-125">비상 통화가 시작 되 면 PSTN 트렁크와 연결 된 PS ALI 공급자의 데이터베이스가 각 아날로그 전화기를 실제 위치로 매핑하고이 위치를 PSAP에 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b49fb-125">When an emergency call is placed, a database at a PS-ALI provider that is associated with the PSTN trunk maps the DID of each analog phone to a physical location and provides this location to the PSAP.</span></span> <span data-ttu-id="b49fb-126">이러한 레코드는 휴대폰을 다른 ERLs로 이동할 때마다 PS-ALI 서비스 공급자로 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b49fb-126">These records must be updated with the PS-ALI service provider every time phones are moved to different ERLs.</span></span></P>
> <LI>
> <P><span data-ttu-id="b49fb-127"><STRONG>E9-1-1 서비스 공급자 옵션</STRONG>&nbsp;&nbsp;&nbsp;E9-1-1 서비스 공급자에서 지원 되는 경우, E9-1-1 서비스 공급자에 아날로그 휴대폰 dids 및 해당 erls를 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b49fb-127"><STRONG>E9-1-1 service provider option</STRONG>&nbsp;&nbsp;&nbsp;You can register the analog phone DIDs and their corresponding ERLs with the E9-1-1 service provider, if this is supported by the E9-1-1 service provider.</span></span> <span data-ttu-id="b49fb-128">공급자가 PIDF-대/소문자 데이터를 포함 하지 않는 Lync Server에서 전화를 받으면 공급자는 전화 파티의 번호와 일치 하는 데이터베이스가 있는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b49fb-128">If the provider receives a call from Lync Server that doesn’t include PIDF-LO data, the provider can see if there is a database match on the calling party’s DID number.</span></span> <span data-ttu-id="b49fb-129">공급자는 해당 데이터베이스에서 검색 된 ERL를 사용 하 여 올바른 PSAP로 긴급 통화를 자동으로 라우트할 수 있으며, PSAP는 발송자가 발신자의 위치를 조회할 수 있도록 하는 아날로그 디바이스와 ESQK 레코드를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="b49fb-129">By using the ERL retrieved from its database, the provider can automatically route the emergency call to the correct PSAP, and the PSAP will receive the DID of the analog device and an ESQK record that allows the dispatcher to lookup the caller’s location.</span></span></P></LI></UL><span data-ttu-id="b49fb-130">ELIN gateway 옵션을 사용 하 고 아날로그 전화기에서 E9-1-1을 지원 해야 하는 경우 위의 첫 번째 옵션에서 설명한 대로 PS-ALI 서비스 공급자를 사용 하 여 아날로그 디바이스의 위치를 직접 프로 비전 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b49fb-130">If you use the ELIN gateway option and need to support E9-1-1 from analog phones, you can provision the analog device's location directly with the PS-ALI service provider, as described in the first option above.</span></span>



</div>

<span data-ttu-id="b49fb-131">Lync Server 관점에서 E9-1 프로세스는 다음 두 단계로 나눌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b49fb-131">From a Lync Server perspective, the E9-1-1 process can be separated into two stages:</span></span>

  - <span data-ttu-id="b49fb-132">1 단계: 위치 가져오기</span><span class="sxs-lookup"><span data-stu-id="b49fb-132">Stage 1: Acquiring a location</span></span>

  - <span data-ttu-id="b49fb-133">2 단계: E9-1-1 서비스 공급자에 대 한 비상 통화 라우팅</span><span class="sxs-lookup"><span data-stu-id="b49fb-133">Stage 2: Routing the emergency call to an E9-1-1 service provider</span></span>

<span data-ttu-id="b49fb-134">이 섹션에서는 이러한 단계의 작동 방식에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="b49fb-134">This section describes how these stages work.</span></span>

<span data-ttu-id="b49fb-135">클라이언트 위치를 자동으로 검색 하도록 인프라를 구성 하려는 경우 먼저 호출자를 위치로 매핑하는 데 사용할 네트워크 요소를 결정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b49fb-135">If you plan to configure your infrastructure to automatically detect client location, first you need to decide which network elements you will use to map callers to locations.</span></span> <span data-ttu-id="b49fb-136">사용할 수 있는 옵션에 대 한 자세한 내용은 [Lync Server 2013의 위치를 확인 하는 데 사용 되는 네트워크 요소 정의](lync-server-2013-defining-the-network-elements-used-to-determine-location.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b49fb-136">For details about the possible options, see [Defining the network elements used to determine location in Lync Server 2013](lync-server-2013-defining-the-network-elements-used-to-determine-location.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b49fb-137">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="b49fb-137">In This Section</span></span>

  - [<span data-ttu-id="b49fb-138">Lync Server 2013에서 위치 얻기</span><span class="sxs-lookup"><span data-stu-id="b49fb-138">Acquiring a location in Lync Server 2013</span></span>](lync-server-2013-acquiring-a-location.md)

  - [<span data-ttu-id="b49fb-139">Lync Server 2013에서 SIP 트렁크를 사용하여 E9-1-1 통화 라우팅</span><span class="sxs-lookup"><span data-stu-id="b49fb-139">Routing E9-1-1 calls by using a SIP trunk in Lync Server 2013</span></span>](lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md)

  - [<span data-ttu-id="b49fb-140">Lync Server 2013에서 ELIN 게이트웨이를 사용하여 E9-1-1 전화 라우팅</span><span class="sxs-lookup"><span data-stu-id="b49fb-140">Routing E9-1-1 calls by using an ELIN gateway in Lync Server 2013</span></span>](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

