---
title: 'Lync Server 2013: 고급 엔터프라이즈 음성 기능에 대 한 네트워크 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Network settings for the advanced Enterprise Voice features
ms:assetid: 7f6de9e4-c8a4-44e4-8d14-21fe8c45283a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398637(v=OCS.15)
ms:contentKeyID: 48184632
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1ce4983f7744158c9c9ff56cdfdde818fdc8e14
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765879"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="network-settings-for-the-advanced-enterprise-voice-features-in-lync-server-2013"></a><span data-ttu-id="8b3ff-102">Lync Server 2013의 고급 엔터프라이즈 음성 기능에 대 한 네트워크 설정</span><span class="sxs-lookup"><span data-stu-id="8b3ff-102">Network settings for the advanced Enterprise Voice features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b3ff-103">_**마지막으로 수정한 주제:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="8b3ff-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="8b3ff-104">Lync Server에는 세 가지 고급 엔터프라이즈 음성 기능 (call 허용 제어 (CAC), 응급 서비스 (E9-1-1), 미디어 바이패스)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b3ff-104">Lync Server has three advanced Enterprise Voice features: call admission control (CAC), emergency services (E9-1-1), and media bypass.</span></span> <span data-ttu-id="8b3ff-105">이러한 기능은 네트워크 지역, 네트워크 사이트에 대 한 특정 구성 요구 사항과 네트워크 사이트를 사용 하 여 Lync Server 토폴로지의 각 서브넷에 대 한 연결을 공유 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b3ff-105">These features share certain configuration requirements for network regions, network sites, and association of each subnet in the Lync Server topology with a network site.</span></span> <span data-ttu-id="8b3ff-106">이러한 기능 배포를 계획 하는 방법에 대 한 자세한 내용은 다음을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8b3ff-106">For details about planning for deployment of these features, see:</span></span>

  - [<span data-ttu-id="8b3ff-107">Lync Server 2013의 통화 허용 제어 서비스 계획</span><span class="sxs-lookup"><span data-stu-id="8b3ff-107">Planning for call admission control in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-admission-control.md)

  - [<span data-ttu-id="8b3ff-108">Lync Server 2013의 응급 서비스 계획(E9-1-1)</span><span class="sxs-lookup"><span data-stu-id="8b3ff-108">Planning for emergency services (E9-1-1) in Lync Server 2013</span></span>](lync-server-2013-planning-for-emergency-services-e9-1-1.md)

  - [<span data-ttu-id="8b3ff-109">Lync Server 2013의 미디어 바이패스 계획</span><span class="sxs-lookup"><span data-stu-id="8b3ff-109">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)

<span data-ttu-id="8b3ff-110">이러한 각 기능을 배포 하는 방법에 대 한 자세한 내용은 배포 설명서에서 [Lync Server 2013의 고급 엔터프라이즈 음성 기능 배포](lync-server-2013-deploying-advanced-enterprise-voice-features.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8b3ff-110">For details about deploying each of these features, see [Deploying advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md) in the Deployment documentation.</span></span>

<span data-ttu-id="8b3ff-111">이 항목에서는 세 가지 고급 엔터프라이즈 음성 기능에 공통적인 구성 요구 사항에 대 한 개요를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b3ff-111">This topic provides an overview of the configuration requirements that are common to all three advanced Enterprise Voice features.</span></span>

<div>

## <a name="network-regions"></a><span data-ttu-id="8b3ff-112">네트워크 지역</span><span class="sxs-lookup"><span data-stu-id="8b3ff-112">Network Regions</span></span>

<span data-ttu-id="8b3ff-113">네트워크 지역은 호출 허용 제어 (CAC), E9-1-1 및 미디어 바이패스 구성에만 사용 되는 네트워크 허브나 네트워크 백본입니다.</span><span class="sxs-lookup"><span data-stu-id="8b3ff-113">A network region is a network hub or network backbone used only in the configuration of call admission control (CAC), E9-1-1, and media bypass.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8b3ff-114">네트워크 지역은 Lync Server 전화 접속 회의 영역과 동일 하지 않으며, 전화 접속 회의 액세스 번호를 하나 이상의 Lync Server 다이얼 플랜에 연결 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b3ff-114">Network regions are not the same as Lync Server dial-in conferencing regions, which are required to associate dial-in conferencing access numbers with one or more Lync Server dial plans.</span></span> <span data-ttu-id="8b3ff-115">전화 접속 회의 지역에 대 한 자세한 내용은 계획 설명서의 <A href="lync-server-2013-dial-in-conferencing-requirements.md">Lync Server 2013에서 전화 접속 회의 요구 사항을</A> 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8b3ff-115">For details about dial-in conferencing regions, see <A href="lync-server-2013-dial-in-conferencing-requirements.md">Dial-in conferencing requirements in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<span data-ttu-id="8b3ff-116">CAC는 모든 네트워크 영역에 지역 내의 미디어 트래픽을 관리 하는 연결 된 Lync Server 중앙 사이트 (즉, 사용자가 구성한 정책에 기반 하 여 실시간 오디오 또는 비디오 세션을 할 수 있는지 여부에 대 한 결정을 내리는 데 사용 됩니다. 설정).</span><span class="sxs-lookup"><span data-stu-id="8b3ff-116">CAC requires that every network region have an associated Lync Server central site, which manages media traffic within the region (that is, it makes decisions based on policies that you have configured, regarding whether or not a real-time audio or video session can be established).</span></span> <span data-ttu-id="8b3ff-117">Lync Server 중앙 사이트는 지리적 위치를 나타내지 않고 풀 또는 풀 집합으로 구성 된 서버의 논리 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="8b3ff-117">Lync Server central sites do not represent geographical locations, but rather logical groups of servers that are configured as a pool or a set of pools.</span></span> <span data-ttu-id="8b3ff-118">중앙 사이트에 대 한 자세한 내용은 계획 설명서의 [Lync Server 2013에서 참조 토폴로지](lync-server-2013-reference-topologies.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8b3ff-118">For details about central sites, see [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md) in the Planning documentation.</span></span> <span data-ttu-id="8b3ff-119">또한 지원 가능성 문서에는 [Lync Server 2013에서 지원 되는 토폴로지가](lync-server-2013-supported-topologies.md) 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b3ff-119">Also see [Supported topologies in Lync Server 2013](lync-server-2013-supported-topologies.md) in the Supportability documentation.</span></span>

<span data-ttu-id="8b3ff-120">네트워크 지역을 구성 하려면 Lync Server 제어판의 **네트워크 구성** 섹션에 있는 **지역** 탭을 사용 하거나, **새-CsNetworkRegion** 또는 **Set csnetworkregion** Lync Server 관리 셸 cmdlet을 실행 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b3ff-120">To configure a network region, you can either use the **Regions** tab on the **Network Configuration** section of Lync Server Control Panel, or run the **New-CsNetworkRegion** or **Set-CsNetworkRegion** Lync Server Management Shell cmdlets.</span></span> <span data-ttu-id="8b3ff-121">지침은 배포 설명서의 [Lync Server 2013에서 네트워크 영역 만들기 또는 수정을](lync-server-2013-create-or-modify-a-network-region.md) 참조 하거나 Lync Server 관리 셸 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8b3ff-121">For instructions, see [Create or modify a network region in Lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md) in the Deployment documentation, or refer to the Lync Server Management Shell documentation.</span></span>

<span data-ttu-id="8b3ff-122">동일한 네트워크 지역 정의는 세 가지 고급 엔터프라이즈 음성 기능 모두에 의해 공유 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b3ff-122">The same network region definitions are shared by all three advanced Enterprise Voice features.</span></span> <span data-ttu-id="8b3ff-123">이미 하나의 기능에 대 한 네트워크 지역을 만든 경우에는 다른 기능에 대해 새 네트워크 지역을 만들 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8b3ff-123">If you have already created network regions for one feature, you do not need to create new network regions for the other features.</span></span> <span data-ttu-id="8b3ff-124">그러나 기능별 설정을 적용 하려면 기존 네트워크 지역 정의를 수정 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b3ff-124">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="8b3ff-125">예를 들어 E9 (연결 된 중앙 사이트 필요 없음)에 대 한 네트워크 지역을 만든 경우, 나중에 통화 허용 제어를 배포 하는 경우 각 네트워크 영역 정의를 수정 하 여 중앙 사이트를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b3ff-125">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and, later, you deploy call admission control, you must modify each of the network region definitions to specify a central site.</span></span>

<span data-ttu-id="8b3ff-126">Lync Server 중앙 사이트를 네트워크 지역에 연결 하려면 Lync Server 제어판의 **네트워크 구성** 섹션을 사용 하거나, **새** 사이트 이름을 지정 하거나 Csnetworkregion 또는 **Set Csnetworkregion** Lync Server Management Shell cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b3ff-126">To associate a Lync Server central site with a network region, you specify the central site name, either by using the **Network Configuration** section of Lync Server Control Panel, or by running the **New-CsNetworkRegion** or **Set-CsNetworkRegion** Lync Server Management Shell cmdlets.</span></span> <span data-ttu-id="8b3ff-127">지침은 배포 설명서의 [Lync Server 2013에서 네트워크 영역 만들기 또는 수정을](lync-server-2013-create-or-modify-a-network-region.md) 참조 하거나 Lync Server 관리 셸 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8b3ff-127">For instructions, see [Create or modify a network region in Lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md) in the Deployment documentation, or refer to the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="network-sites"></a><span data-ttu-id="8b3ff-128">네트워크 사이트</span><span class="sxs-lookup"><span data-stu-id="8b3ff-128">Network Sites</span></span>

<span data-ttu-id="8b3ff-129">네트워크 사이트는 지사, 지역 사무소 또는 기본 사무실 등의 지리적 위치를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8b3ff-129">A network site represents a geographical location, such as a branch office, a regional office, or a main office.</span></span> <span data-ttu-id="8b3ff-130">각 네트워크 사이트는 특정 네트워크 지역에 연결 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b3ff-130">Each network site must be associated with a specific network region.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8b3ff-131">네트워크 사이트는 고급 엔터프라이즈 음성 기능 으로만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b3ff-131">Network sites are used only by the advanced Enterprise Voice features.</span></span> <span data-ttu-id="8b3ff-132">이는 Lync Server 토폴로지에서 구성한 분기 사이트와 동일 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8b3ff-132">They are not the same as the branch sites that you configure in your Lync Server topology.</span></span> <span data-ttu-id="8b3ff-133">지점 사이트에 대 한 자세한 내용은 계획 설명서의 <A href="lync-server-2013-reference-topologies.md">Lync Server 2013에서 참조 토폴로지</A> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8b3ff-133">For details about branch sites, see <A href="lync-server-2013-reference-topologies.md">Reference topologies in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="8b3ff-134">또한 지원 가능성 문서에는 <A href="lync-server-2013-supported-topologies.md">Lync Server 2013에서 지원 되는 토폴로지가</A> 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b3ff-134">Also see <A href="lync-server-2013-supported-topologies.md">Supported topologies in Lync Server 2013</A> in the Supportability documentation.</span></span>



</div>

<span data-ttu-id="8b3ff-135">네트워크 사이트를 구성 하 고 네트워크 지역에 연결 하려면 Lync Server 제어판의 **네트워크 구성** 섹션을 사용 하거나 Lync Server 관리 셸 **새 csnetworksite** 또는 **Set csnetworksite** cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b3ff-135">To configure a network site and associate it with a network region, you can either use the **Network Configuration** section of Lync Server Control Panel, or run the Lync Server Management Shell **New-CsNetworkSite** or **Set-CsNetworkSite** cmdlets.</span></span> <span data-ttu-id="8b3ff-136">자세한 내용은 배포 설명서의 [Lync server 2013에서 네트워크 사이트 만들기 또는 수정을](lync-server-2013-create-or-modify-a-network-site.md) 참조 하거나 Lync Server 관리 셸 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8b3ff-136">For details, see [Create or modify a network site in Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md) in the Deployment documentation, or refer to the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="identify-ip-subnets"></a><span data-ttu-id="8b3ff-137">IP 서브넷 확인</span><span class="sxs-lookup"><span data-stu-id="8b3ff-137">Identify IP Subnets</span></span>

<span data-ttu-id="8b3ff-138">각 네트워크 사이트에 대해 네트워크 관리자와 협력 하 여 각 네트워크 사이트에 할당 되는 IP 서브넷을 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b3ff-138">For each network site, you will need to work with your network administrator to determine which IP subnets are assigned to each network site.</span></span> <span data-ttu-id="8b3ff-139">네트워크 관리자가 이미 네트워크 지역 및 네트워크 사이트로 IP 서브넷을 구성한 경우에는 작업이 대폭 간소화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b3ff-139">If your network administrator has already organized the IP subnets into network regions and network sites, then your work is significantly simplified.</span></span>

<span data-ttu-id="8b3ff-140">예를 들어 북미 지역의 뉴욕 사이트에는 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24의 IP 서브넷이 할당 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b3ff-140">For example, the New York site in the North America region can be assigned the following IP subnets: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24.</span></span> <span data-ttu-id="8b3ff-141">일반적으로 디트로이트에서 작동 하는 사용자의 경우, 교육을 위해 뉴욕 사무실로 이동 하 고, 컴퓨터를 설정 하 여 네트워크에 연결 하면 컴퓨터는 뉴욕에 대해 할당 된 4 개의 범위 (예: 172.29.80.103) 중 하나에 IP 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8b3ff-141">If Bob, who usually works in Detroit, travels to the New York office for training, turns on his computer and connects to the network, his computer will get an IP address in one of the four ranges that are allocated for New York—for example, 172.29.80.103.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="8b3ff-142">서버에서 네트워크 구성 중에 지정 된 IP 서브넷은 미디어 바이패스에 사용 하기 위해 클라이언트 컴퓨터가 제공 하는 형식과 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b3ff-142">The IP subnets specified during network configuration on the server must match the format that is provided by client computers in order to be properly used for media bypass.</span></span> <span data-ttu-id="8b3ff-143">Lync 클라이언트는 해당 로컬 IP 주소를 사용 하 고 연결 된 서브넷 마스크를 사용 하 여 IP 주소를 마스크 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b3ff-143">A Lync client takes its local IP address and masks the IP address with the associated subnet mask.</span></span> <span data-ttu-id="8b3ff-144">각 클라이언트와 연결 된 우회 ID를 결정할 때, 레지스트라는 각 네트워크 사이트와 연결 된 IP 서브넷 목록을 클라이언트에서 제공 하는 서브넷과 정확히 일치 하도록 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b3ff-144">When determining the bypass ID associated with each client, the Registrar will compare the list of IP subnets associated with each network site against the subnet that is provided by the client for an exact match.</span></span> <span data-ttu-id="8b3ff-145">이러한 이유로, 서버에서 네트워크를 구성 하는 동안 입력 된 서브넷이 가상 서브넷 대신 실제 서브넷이 되는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b3ff-145">For this reason, it is important that subnets entered during network configuration on the server are actual subnets instead of virtual subnets.</span></span> <span data-ttu-id="8b3ff-146">(통화 허용 제어를 배포 하지만 미디어 바이패스는 아닌 경우 가상 서브넷을 구성한 경우에도 통화 허용 제어가 올바르게 작동 합니다.)</span><span class="sxs-lookup"><span data-stu-id="8b3ff-146">(If you deploy call admission control, but not media bypass, call admission control will function properly even if you configure virtual subnets.)</span></span><BR><span data-ttu-id="8b3ff-147">예를 들어 Lync 클라이언트가 IP 주소 서브넷이 255.255.255.0 인 컴퓨터에 로그인 하면 서브넷 172.29.81.0와 연결 된 우회 ID를 요청 하 게 됩니다. 172.29.81.57.</span><span class="sxs-lookup"><span data-stu-id="8b3ff-147">For example, if a Lync client signs in on a computer with an IP address of 172.29.81.57 with an IP subnet mask of 255.255.255.0, it will request the bypass ID that is associated with subnet 172.29.81.0.</span></span> <span data-ttu-id="8b3ff-148">서브넷이 172.29.0.0/16으로 정의 된 경우에는 클라이언트가 가상 서브넷에 속해 있지만, 레지스트라는 특별히 서브넷 172.29.81.0를 찾고 있기 때문에이에 대 한 일치가 고려 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8b3ff-148">If the subnet is defined as 172.29.0.0/16, although the client belongs to the virtual subnet, the Registrar will not consider this a match because the Registrar is specifically looking for subnet 172.29.81.0.</span></span> <span data-ttu-id="8b3ff-149">따라서 관리자는 네트워크 구성 중에 서브넷이 정적으로 또는 동적 호스트 구성 프로토콜 (DHCP)에 따라 프로 비전 되는 Lync 클라이언트에서 제공 하는 대로 서브넷을 정확 하 게 입력 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b3ff-149">Therefore, it is important that the administrator enters subnets exactly as provided by Lync clients (which are provisioned with subnets during network configuration, either statically or by Dynamic Host Configuration Protocol (DHCP).)</span></span>



</div>

</div>

<div>

## <a name="associating-subnets-with-network-sites"></a><span data-ttu-id="8b3ff-150">네트워크 사이트와 서브넷 연결</span><span class="sxs-lookup"><span data-stu-id="8b3ff-150">Associating Subnets with Network Sites</span></span>

<span data-ttu-id="8b3ff-151">엔터프라이즈 네트워크의 모든 서브넷은 네트워크 사이트와 연결 되어야 하며 (즉, 모든 서브넷은 지리적 위치와 연결 되어야 합니다.)</span><span class="sxs-lookup"><span data-stu-id="8b3ff-151">Every subnet in the enterprise network must be associated with a network site (that is, every subnet needs to be associated with a geographic location).</span></span> <span data-ttu-id="8b3ff-152">이러한 서브넷 연결을 통해 고급 엔터프라이즈 음성 기능을 통해 끝점을 지리적으로 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b3ff-152">This association of subnets enables the advanced Enterprise Voice features to locate the endpoints geographically.</span></span> <span data-ttu-id="8b3ff-153">예를 들어 끝점을 찾으면 CAC는 네트워크 사이트와 주고 받는 실시간 오디오 및 비디오 데이터의 흐름을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b3ff-153">For example, locating the endpoints enables CAC to regulate the flow of real-time audio and video data going to and from the network site.</span></span>

<span data-ttu-id="8b3ff-154">서브넷을 네트워크 사이트와 연결 하려면 Lync Server 제어판의 **네트워크 구성** 섹션을 사용 하거나 Lync Server 관리 셸을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b3ff-154">To associate subnets with network sites, you can either use the **Network Configuration** section of Lync Server Control Panel, or you can use the Lync Server Management Shell.</span></span> <span data-ttu-id="8b3ff-155">지침은 배포 설명서의 [Lync server 2013에서 서브넷을 네트워크 사이트에 연결](lync-server-2013-associate-a-subnet-with-a-network-site.md) 또는 Lync Server 관리 셸 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8b3ff-155">For instructions, see [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md) in the Deployment documentation, or refer to the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8b3ff-156">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8b3ff-156">See Also</span></span>


[<span data-ttu-id="8b3ff-157">Lync Server 2013의 통화 허용 제어 서비스 계획</span><span class="sxs-lookup"><span data-stu-id="8b3ff-157">Planning for call admission control in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-admission-control.md)  
[<span data-ttu-id="8b3ff-158">Lync Server 2013의 응급 서비스 계획(E9-1-1)</span><span class="sxs-lookup"><span data-stu-id="8b3ff-158">Planning for emergency services (E9-1-1) in Lync Server 2013</span></span>](lync-server-2013-planning-for-emergency-services-e9-1-1.md)  
[<span data-ttu-id="8b3ff-159">Lync Server 2013의 미디어 바이패스 계획</span><span class="sxs-lookup"><span data-stu-id="8b3ff-159">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

