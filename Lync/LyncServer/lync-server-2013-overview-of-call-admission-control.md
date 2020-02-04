---
title: 'Lync Server 2013: 통화 허용 제어 개요'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of call admission control
ms:assetid: 6fda0195-4c89-4dea-82e8-624f03e3d062
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398529(v=OCS.15)
ms:contentKeyID: 48184474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5b38fbb1ae1e209e5b5332e896d806d1ca24975
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755622"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="47d95-102">Lync Server 2013의 통화 허용 제어 개요</span><span class="sxs-lookup"><span data-stu-id="47d95-102">Overview of call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="47d95-103">_**마지막으로 수정한 주제:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="47d95-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="47d95-104">실시간 통신은 혼잡 네트워크에서 발생할 수 있는 대기 시간 및 패킷 손실률을 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="47d95-104">Real-time communications are sensitive to the latency and packet loss that can occur on congested networks.</span></span> <span data-ttu-id="47d95-105">CAC (호출 허용 제어)는 음성 또는 영상 통화 등의 실시간 통신 세션을 설정할 수 있는 사용 가능한 네트워크 대역폭을 기준으로 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47d95-105">Call admission control (CAC) determines, based on available network bandwidth, whether to allow real-time communications sessions such as voice or video calls to be established.</span></span> <span data-ttu-id="47d95-106">Lync Server 2013의 CAC 디자인은 네 가지 주요 특성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="47d95-106">The CAC design in Lync Server 2013 offers four main attributes:</span></span>

  - <span data-ttu-id="47d95-107">특별 하 게 구성 된 라우터 등 추가 장비 없이도 간편 하 게 배포 하 고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47d95-107">It is simple to deploy and manage without requiring additional equipment, such as specially configured routers.</span></span>

  - <span data-ttu-id="47d95-108">로밍 사용자, 여러 지점 현재 상태 등의 중요 한 통합 커뮤니케이션 사용 사례를 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="47d95-108">It addresses critical unified communications use cases, such as roaming users and multiple points of presence.</span></span> <span data-ttu-id="47d95-109">CAC 정책은 끝점이 위치한 위치에 따라 적용 되며 사용자가 홈 위치에 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="47d95-109">CAC policies are enforced according to where the endpoint is located, not where the user is homed.</span></span>

  - <span data-ttu-id="47d95-110">음성 통화 외에 영상 통화, 오디오/비디오 회의 세션 등의 다른 트래픽에도 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47d95-110">In addition to voice calls, it can be applied to other traffic, such as video calls and audio/video conferencing sessions.</span></span>

  - <span data-ttu-id="47d95-111">다양 한 종류의 네트워크 토폴로지 표현을 사용할 수 있는 유연성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="47d95-111">Provides the flexibility to enable representation of various kinds of network topologies.</span></span> <span data-ttu-id="47d95-112">예를 들어 [Lync Server 2013에서 CAC에 대 한 구성 요소 및 토폴로지](lync-server-2013-components-and-topologies-for-cac.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="47d95-112">For examples, see [Components and topologies for CAC in Lync Server 2013](lync-server-2013-components-and-topologies-for-cac.md).</span></span>

<span data-ttu-id="47d95-113">새 음성 또는 비디오 세션이 WAN 링크에 설정한 대역폭 제한을 초과 하는 경우 해당 세션은 차단 되거나 (전화 통화 전용) PSTN으로 다시 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="47d95-113">If a new voice or video session exceeds the bandwidth limits that you have set on a WAN link, the session is either blocked or (for phone calls only) rerouted to the PSTN.</span></span>

<span data-ttu-id="47d95-114">CAC는 음성 및 비디오만을 위한 실시간 소통을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="47d95-114">CAC controls real-time traffic for voice and video only.</span></span> <span data-ttu-id="47d95-115">데이터 트래픽을 제어 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="47d95-115">It does not control data traffic.</span></span>

<span data-ttu-id="47d95-116">관리자는 모든 프런트 엔드 풀과 함께 설치 되는 대역폭 정책 서비스에 의해 적용 되는 CAC 정책을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="47d95-116">Administrators define CAC policies, which are enforced by the Bandwidth Policy Service that is installed with every Front End pool.</span></span> <span data-ttu-id="47d95-117">CAC 설정은 네트워크의 모든 Lync Server 프런트 엔드 서버에 자동으로 전파 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47d95-117">CAC settings are automatically propagated to all Lync Server Front End Servers in your network.</span></span>

<span data-ttu-id="47d95-118">CAC 정책 때문에 실패 하는 통화의 경우 통화를 다시 라우팅 하는 데 사용할 수 있는 우선 순위는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="47d95-118">For calls that fail because of CAC policies, the order of precedence for rerouting the call is as follows:</span></span>

1.  <span data-ttu-id="47d95-119">인터넷</span><span class="sxs-lookup"><span data-stu-id="47d95-119">Internet</span></span>

2.  <span data-ttu-id="47d95-120">PSTN</span><span class="sxs-lookup"><span data-stu-id="47d95-120">PSTN</span></span>

3.  <span data-ttu-id="47d95-121">음성 메일</span><span class="sxs-lookup"><span data-stu-id="47d95-121">Voice mail</span></span>

<span data-ttu-id="47d95-122">CDR (통화 정보 기록)는 PSTN 또는 음성 메일로 경로를 전환 하는 통화에 대 한 정보를 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="47d95-122">Call detail recording (CDR) captures information about calls that are rerouted to the PSTN or to voice mail.</span></span> <span data-ttu-id="47d95-123">CDR는 인터넷이 보조 옵션이 아닌 대체 경로로 처리 되므로 인터넷으로 경로 전환 되는 호출에 대 한 정보를 수집 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="47d95-123">CDR does not capture information about calls that are rerouted to the Internet, because the Internet is treated as an alternate path rather than a secondary option.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="47d95-124">음성 메일 저축과는 대역폭 제약 조건 때문에 거부 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="47d95-124">Voice mail deposits will not be denied because of bandwidth constraints.</span></span>



</div>

<span data-ttu-id="47d95-125">대역폭 정책 서비스는 쉼표로 구분 된 값 (CSV) 형식으로 두 가지 유형의 로그 파일을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="47d95-125">The Bandwidth Policy Service generates two types of log files in comma separated values (CSV) format.</span></span> <span data-ttu-id="47d95-126">대역폭 요청이 거부 되 면 **오류 검사** 로그 파일에서 정보를 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="47d95-126">The **check failures** log file captures information when bandwidth requests are denied.</span></span> <span data-ttu-id="47d95-127">**링크 사용률** 로그 파일은 네트워크 토폴로지의 스냅샷과 WAN 링크 대역폭 사용률을 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="47d95-127">The **link utilization** log file captures a snapshot of the network topology and the WAN link bandwidth utilization.</span></span> <span data-ttu-id="47d95-128">두 로그 파일은 모두 사용률을 기준으로 CAC 정책을 미세 조정 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47d95-128">Both of these log files can assist you in fine-tuning your CAC policies based on utilization.</span></span>

<div>

## <a name="call-admission-control-considerations"></a><span data-ttu-id="47d95-129">통화 허용 제어 고려 사항</span><span class="sxs-lookup"><span data-stu-id="47d95-129">Call Admission Control Considerations</span></span>

<span data-ttu-id="47d95-130">관리자가 중앙 사이트에 구성 된 첫 번째 풀에 대역폭 정책 서비스를 설치 하도록 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="47d95-130">The administrator selects to install the Bandwidth Policy Service on the first pool configured in the central site.</span></span> <span data-ttu-id="47d95-131">각 네트워크 지역에 단일 중앙 사이트가 있으므로 해당 지역에 대 한 대역폭 정책, 연결 된 사이트 및 해당 사이트에 대 한 링크를 관리 하는 네트워크 지역 마다 하나의 대역폭 정책 서비스만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47d95-131">Since there is a single central site per network region, there is only one Bandwidth Policy Service per network region, which manages bandwidth policy for that region, its associated sites and the links to those sites.</span></span> <span data-ttu-id="47d95-132">대역폭 정책 서비스는 프런트 엔드 서버의 일부로 실행 되므로 고가용성이 해당 풀 내에 기본 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47d95-132">The Bandwidth Policy Service runs as part of the Front End Servers, and therefore high availability is built-in within that pool.</span></span> <span data-ttu-id="47d95-133">각 프런트 엔드 서버에서 실행 되는 대역폭 정책 서비스는 15 초 마다 동기화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47d95-133">The Bandwidth Policy Service running on each Front End Server synchronizes every 15 seconds.</span></span> <span data-ttu-id="47d95-134">프런트 엔드 풀에 오류가 발생 하면 프런트 엔드 풀까지 해당 사이트에 CAC 정책이 더 이상 적용 되지 않으며 결과적으로 대역폭 정책 서비스가 다시 작동할 수 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47d95-134">If the Front End pool fails, CAC policies are no longer enforced for that site until the Front End pool and consequently the Bandwidth Policy Service becomes operational again.</span></span> <span data-ttu-id="47d95-135">이는 모든 통화가 대역폭 정책 서비스가 서비스를 종료 한 기간 동안 진행 됨을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="47d95-135">This implies that all calls will go through for the duration the Bandwidth Policy Service is out of service.</span></span> <span data-ttu-id="47d95-136">따라서이 기간 동안에는 링크의 대역폭 초과로 인해 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47d95-136">Therefore there is the possibility of bandwidth oversubscription of your links during this period</span></span>

<span data-ttu-id="47d95-137">대역폭 정책 서비스는 프런트 엔드 풀 내에서 높은 가용성을 제공 합니다. 그러나 프런트 엔드 풀에서 중복성을 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="47d95-137">The Bandwidth Policy Service provides high availability within a Front End pool; however, it does not provide redundancy across Front End pools.</span></span> <span data-ttu-id="47d95-138">대역폭 정책 서비스는 프런트 엔드 풀 간에 장애 조치 (failover)를 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="47d95-138">The Bandwidth Policy Service cannot failover from one Front End pool to another.</span></span> <span data-ttu-id="47d95-139">프런트 엔드 풀에 대 한 서비스가 복원 되 면 대역폭 정책 서비스가 다시 시작 되 고 대역폭 정책 확인을 다시 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47d95-139">Once service to the Front End pool is restored, the Bandwidth Policy Service is resumed and can enforce bandwidth policy checks again.</span></span>

<div>

## <a name="network-considerations"></a><span data-ttu-id="47d95-140">네트워크 고려 사항</span><span class="sxs-lookup"><span data-stu-id="47d95-140">Network Considerations</span></span>

<span data-ttu-id="47d95-141">오디오 및 비디오에 대 한 대역폭 제한은 Lync Server 2013의 대역폭 정책 서비스에 의해 적용 되지만 네트워크 라우터에서 (계층 2 및 3)에는 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="47d95-141">Although bandwidth restriction for audio and video is enforced by the Bandwidth Policy Service in Lync Server 2013, this restriction is not enforced at the network router (layer 2 and 3).</span></span> <span data-ttu-id="47d95-142">Lync Server 2010 CAC는 데이터 응용 프로그램 (예: CAC 정책에서 오디오 및 비디오용으로 예약 된 대역폭)을 포함 하 여 WAN 링크에서 전체 네트워크 대역폭을 소모 하는 것을 방지할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="47d95-142">Lync Server 2010 CAC cannot prevent a data application, for example, from consuming the entire network bandwidth on a WAN link, including the bandwidth that is reserved for audio and video by your CAC policy.</span></span> <span data-ttu-id="47d95-143">네트워크에서 필요한 대역폭을 보호 하기 위해, DiffServ (차별화 서비스)와 같은 QoS (서비스 품질) 프로토콜을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47d95-143">To protect the necessary bandwidth on your network, you can deploy a Quality of Service (QoS) protocol such as Differentiated Services (DiffServ).</span></span> <span data-ttu-id="47d95-144">따라서 가장 좋은 방법은 배포할 수 있는 모든 QoS 설정을 사용 하 여 정의 하는 CAC 대역폭 정책을 조정 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="47d95-144">Therefore, a best practice is to coordinate the CAC bandwidth policies you define with any QoS settings that you might deploy.</span></span>

</div>

<div>

## <a name="media-and-signaling-paths-over-vpn"></a><span data-ttu-id="47d95-145">VPN을 통한 미디어 및 신호 경로</span><span class="sxs-lookup"><span data-stu-id="47d95-145">Media and Signaling Paths over VPN</span></span>

<span data-ttu-id="47d95-146">엔터프라이즈에서 VPN을 통해 미디어를 지 원하는 경우 미디어 스트림과 신호 스트림이 VPN을 통과 하거나 모두 인터넷을 통해 라우팅되도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47d95-146">If your enterprise supports media through VPN, ensure that either both the media stream and the signaling stream go through the VPN or both are routed through the internet.</span></span> <span data-ttu-id="47d95-147">기본적으로 미디어 및 신호 스트림은 VPN 터널을 통해 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="47d95-147">By default, the media and signaling streams go through the VPN tunnel.</span></span>

</div>

<div>

## <a name="call-admission-control-of-outside-users"></a><span data-ttu-id="47d95-148">외부 사용자의 통화 허용 제어</span><span class="sxs-lookup"><span data-stu-id="47d95-148">Call Admission Control of Outside Users</span></span>

<span data-ttu-id="47d95-149">네트워크 트래픽이 인터넷을 통해 흐르는 원격 사용자에 게는 통화 허용 제어가 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="47d95-149">Call admission control is not enforced for remote users where the network traffic flows through the Internet.</span></span> <span data-ttu-id="47d95-150">미디어 트래픽이 Lync Server로 관리 되지 않는 인터넷을 탐색 하 고 있기 때문에 CAC를 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="47d95-150">Because the media traffic is traversing the Internet, which is not managed by Lync Server, CAC cannot be applied.</span></span> <span data-ttu-id="47d95-151">그러나 엔터프라이즈 네트워크를 통해 전달 되는 통화의 일부에 CAC 확인이 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47d95-151">CAC checks will be performed, however, on the portion of the call that flows through the enterprise network.</span></span>

</div>

<div>

## <a name="call-admission-control-of-pstn-connections"></a><span data-ttu-id="47d95-152">PSTN 연결의 통화 허용 제어</span><span class="sxs-lookup"><span data-stu-id="47d95-152">Call Admission Control of PSTN Connections</span></span>

<span data-ttu-id="47d95-153">통화 허용 제어는 IP/PBX, PSTN 게이트웨이 또는 SIP 트렁크에 연결 되어 있는지 여부에 관계 없이 중재 서버에 enforceable 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47d95-153">Call admission control is enforceable on the Mediation Server regardless of whether it is connected to an IP/PBX, a PSTN gateway, or a SIP trunk.</span></span> <span data-ttu-id="47d95-154">중재 서버는 B2BUA (연속 사용자 에이전트) 이므로 미디어를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="47d95-154">Because the Mediation Server is a back-to-back user agent (B2BUA), it terminates media.</span></span> <span data-ttu-id="47d95-155">이 연결에는 Lync Server에 연결 된 쪽과 PSTN 게이트웨이, IP/Pbx 또는 SIP trunks에 연결 되는 게이트웨이 쪽 두 개가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47d95-155">It has two connection sides: a side that is connected to Lync Server and a gateway side, which is connected to PSTN gateways, IP/PBXs, or SIP trunks.</span></span> <span data-ttu-id="47d95-156">PSTN 연결에 대 한 자세한 내용은 [Lync Server 2013의 PSTN 연결 계획](lync-server-2013-planning-for-pstn-connectivity.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="47d95-156">For details about PSTN connections, see [Planning for PSTN connectivity in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md).</span></span>

<span data-ttu-id="47d95-157">미디어 바이패스를 사용 하도록 설정 하지 않는 한 중재 서버의 양쪽에 CAC를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47d95-157">CAC can be enforced on both sides of the Mediation Server unless media bypass is enabled.</span></span> <span data-ttu-id="47d95-158">미디어 바이패스를 사용 하도록 설정 하면 미디어 트래픽이 중재 서버를 통과 하지 않고 대신 Lync 클라이언트와 게이트웨이 사이에 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47d95-158">If media bypass is enabled, the media traffic doesn’t traverse the Mediation Server but instead flows directly between the Lync client and the gateway.</span></span> <span data-ttu-id="47d95-159">이 경우에는 CAC가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="47d95-159">In this case, CAC is not needed.</span></span> <span data-ttu-id="47d95-160">자세한 내용은 [Lync Server 2013의 미디어 바이패스 계획](lync-server-2013-planning-for-media-bypass.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="47d95-160">For details, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md).</span></span>

<span data-ttu-id="47d95-161">다음 그림은 미디어 바이패스를 사용 하는 경우와 사용 하지 않고 PSTN 연결에 CAC를 적용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="47d95-161">The following figure illustrates how CAC is enforced on PSTN connections with and without media bypass enabled.</span></span>

<span data-ttu-id="47d95-162">**PSTN 연결에 대 한 통화 허용 제어 적용**</span><span class="sxs-lookup"><span data-stu-id="47d95-162">**Call admission control enforcement on connections to the PSTN**</span></span>

<span data-ttu-id="47d95-163">![음성 CAC 미디어 바이패스 연결 적용](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "음성 CAC 미디어 바이패스 연결 적용")</span><span class="sxs-lookup"><span data-stu-id="47d95-163">![Voice CAC Media Bypass Connection Enforcement](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Voice CAC Media Bypass Connection Enforcement")</span></span>

</div>

<div>

## <a name="compatibility-of-call-admission-control-with-earlier-versions-of-office-communications-server"></a><span data-ttu-id="47d95-164">이전 버전의 Office Communications Server와의 통화 허용 제어 호환성</span><span class="sxs-lookup"><span data-stu-id="47d95-164">Compatibility of Call Admission Control with Earlier Versions of Office Communications Server</span></span>

<span data-ttu-id="47d95-165">통화 허용 제어는 Lync Server 2010 이상에서 사용 하도록 설정 된 끝점 에서만 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47d95-165">Call admission control can be enabled only on endpoints that are enabled for Lync Server 2010 and later.</span></span>

<span data-ttu-id="47d95-166">Office Communicator 2007 R2이 하 버전을 실행 하는 끝점에서는 통화 허용 제어를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="47d95-166">Call admission control cannot be enabled on endpoints running Office Communicator 2007 R2 or earlier.</span></span>

<span data-ttu-id="47d95-167">**다른 Lync Server 버전에서 CAC 적용**</span><span class="sxs-lookup"><span data-stu-id="47d95-167">**Application of CAC on different Lync Server versions**</span></span>

<span data-ttu-id="47d95-168">![음성 CAC 버전 비교 다이어그램](images/Gg398529.fdbfee7e-15fc-445b-949d-8d61e61ac350(OCS.15).jpg "음성 CAC 버전 비교 다이어그램")</span><span class="sxs-lookup"><span data-stu-id="47d95-168">![Voice CAC Version Comparison diagram](images/Gg398529.fdbfee7e-15fc-445b-949d-8d61e61ac350(OCS.15).jpg "Voice CAC Version Comparison diagram")</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

