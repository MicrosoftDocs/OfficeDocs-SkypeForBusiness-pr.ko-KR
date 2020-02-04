---
title: 'Lync Server 2013: 위치를 결정 하는 데 사용 되는 네트워크 요소 정의'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining the network elements used to determine location
ms:assetid: 7538779d-055d-44ed-8dd7-11c45fc1b9f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398567(v=OCS.15)
ms:contentKeyID: 48184508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d71d222fd6784c32ecf0228fff2f33188d2afae
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728338"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-the-network-elements-used-to-determine-location-in-lync-server-2013"></a><span data-ttu-id="353bb-102">Lync Server 2013에서 위치를 확인 하는 데 사용 되는 네트워크 요소 정의</span><span class="sxs-lookup"><span data-stu-id="353bb-102">Defining the network elements used to determine location in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="353bb-103">_**마지막으로 수정한 주제:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="353bb-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="353bb-104">자동 클라이언트 위치 검색을 지원 하도록 Lync Server 인프라를 설정 하는 경우 먼저 호출자를 위치로 매핑하는 데 사용할 네트워크 요소를 결정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="353bb-104">If you are setting up your Lync Server infrastructure to support automatic client location detection, you first need to decide which network elements you are going to use to map callers to locations.</span></span> <span data-ttu-id="353bb-105">Lync Server 2013에서 다음 계층 2 및 계층 3 네트워크 요소를 위치와 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="353bb-105">In Lync Server 2013, you can associate the following Layer 2 and Layer 3 network elements with locations:</span></span>

  - <span data-ttu-id="353bb-106">무선 액세스 지점간 (WAP) 기본 서비스 집합 식별 Id (BSSID) 주소 (계층 2)</span><span class="sxs-lookup"><span data-stu-id="353bb-106">Wireless access point (WAP) Basic Service Set Identification (BSSID) addresses (Layer 2)</span></span>

  - <span data-ttu-id="353bb-107">LLDP 스위치 포트 (레이어 2)</span><span class="sxs-lookup"><span data-stu-id="353bb-107">LLDP switch port (Layer 2)</span></span>

  - <span data-ttu-id="353bb-108">LLDP 스위치 섀시 Id (계층 2)</span><span class="sxs-lookup"><span data-stu-id="353bb-108">LLDP switch chassis IDs (Layer 2)</span></span>

  - <span data-ttu-id="353bb-109">IP 서브넷 (계층 3)</span><span class="sxs-lookup"><span data-stu-id="353bb-109">IP subnets (Layer 3)</span></span>

  - <span data-ttu-id="353bb-110">클라이언트 MAC 주소 (계층 2)</span><span class="sxs-lookup"><span data-stu-id="353bb-110">Client MAC addresses (Layer 2)</span></span>

<span data-ttu-id="353bb-111">네트워크 요소는 우선 순위 순서 대로 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="353bb-111">The network elements are listed in order of precedence.</span></span> <span data-ttu-id="353bb-112">두 개 이상의 네트워크 요소를 사용 하 여 클라이언트를 찾을 수 있는 경우 Lync Server는 우선 순위를 사용 하 여 사용할 메커니즘을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="353bb-112">If a client can be located by using more than one network element, Lync Server uses the order of precedence to determine which mechanism to use.</span></span>

<span data-ttu-id="353bb-113">다음 섹션에서는 각 네트워크 요소를 사용 하는 방법에 대 한 자세한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="353bb-113">The following sections provide more details for using each network element.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="353bb-114">네트워크 요소를 사용 하 여 호출자를 위치로 매핑하는 경우 위치 정보 서비스 데이터베이스를 최신 상태로 유지 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="353bb-114">When you use network elements to map callers to locations, it is of utmost importance that you keep the Location Information service database up-to-date.</span></span> <span data-ttu-id="353bb-115">예를 들어 WAP 추가와 같은 네트워크 요소를 추가 하거나 변경 하는 경우 이전 항목을 삭제 하 고 위치 데이터베이스에 새 항목을 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="353bb-115">For example, if you add or change a network element, such as adding a WAP, you must delete the old entry and add the new entry in the location database.</span></span>



</div>

<div>

## <a name="wireless-access-point"></a><span data-ttu-id="353bb-116">무선 액세스 지점의</span><span class="sxs-lookup"><span data-stu-id="353bb-116">Wireless Access Point</span></span>

<span data-ttu-id="353bb-117">클라이언트가 네트워크에 무선으로 연결할 때 위치 요청은 WAP의 BSSID 주소를 사용 하 여 해당 위치를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="353bb-117">When a client connects to the network wirelessly, the location request uses the BSSID address of the WAP to determine its location.</span></span> <span data-ttu-id="353bb-118">클라이언트가 로밍 중인 경우 표시 되는 WAP이 가장 가까이 있지 않을 수 있으며 건물의 다른 밑면에 있는 WAP을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="353bb-118">If the client is roaming, the WAP indicated may not be the closest one, and it’s even possible to pick up a WAP that is on a different floor of the building.</span></span> <span data-ttu-id="353bb-119">위치에 근사값을 표시 하려면 위치 값 앞에 가까운 또는 위쪽을 설명자에 가깝게 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="353bb-119">To indicate that the location is approximate, you can prepend the location value with a Near or Close to descriptor.</span></span>

<span data-ttu-id="353bb-120">이 위치 메서드는 각 WAP의 BSSID가 정적 이라고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="353bb-120">This location method assumes that the BSSID of each WAP is static.</span></span> <span data-ttu-id="353bb-121">그러나 WAP 공급 업체가 동적으로 할당 된 BSSIDs를 사용 하는 경우 WAP에서 가져온 BSSID가 변경 될 수 있으며,이는 WAP 구성 변경 후에 발생 하며, 무선 클라이언트는 위치를 받지 못하는 상황에 남아 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="353bb-121">However, if your WAP vendor uses dynamically-assigned BSSIDs, the BSSID that is obtained from a WAP could change (this can happen following a WAP configuration change), and wireless clients could be left in a situation where they don’t receive a location.</span></span> <span data-ttu-id="353bb-122">이러한 가능성을 방지 하려면 각 WAP에서 사용 가능한 모든 BSSID 주소에 대 한 ERLs로 위치 정보 서비스 데이터베이스를 채워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="353bb-122">To prevent this possibility, you need to populate the Location Information service database with ERLs for all possible BSSID addresses used by each WAP.</span></span>

</div>

<div>

## <a name="lldp-ports-and-switches"></a><span data-ttu-id="353bb-123">LLDP 포트 및 스위치</span><span class="sxs-lookup"><span data-stu-id="353bb-123">LLDP Ports and Switches</span></span>

<span data-ttu-id="353bb-124">연결 계층 검색 프로토콜을 지 원하는 관리 되는 이더넷 스위치-LLDP (미디어 끝점 검색)는 LLDP 호환 클라이언트에 대 한 id 및 포트 정보를 광고 하 고 다음을 제공 하기 위해 위치 데이터베이스에 대해 쿼리할 수 있습니다. 디바이스의 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="353bb-124">Managed Ethernet switches that support Link Layer Discovery Protocol-Media Endpoint Discover (LLDP-MED) can advertise their identity and port information to LLDP-MED compatible clients, which then can be queried against the location database to provide the location of the device.</span></span> <span data-ttu-id="353bb-125">스위치 섀시 ID에는 단독으로 ERLs를 연결 하거나 포트 수준에 매핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="353bb-125">You can associate ERLs solely on the switch chassis ID, or you can map them down to the port level.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="353bb-126">Lync Server 2013는 Windows 8에서 실행 되는 lync Phone Edition 장치 및 Lync 2013의 위치만 확인 하기 위해 LLDP 사용을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="353bb-126">Lync Server 2013 supports using LLDP-MED for determining locations only of Lync Phone Edition devices and Lync 2013 running on Windows 8.</span></span> <span data-ttu-id="353bb-127">다른 유선 PC 기반 Lync 클라이언트의 위치를 확인 하는 데 스위치 수준 계층 2 데이터를 사용 해야 하는 경우에는 클라이언트 MAC 주소 메서드를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="353bb-127">If you need to use switch-level Layer 2 data to determine the location of other wired PC-based Lync clients, you need to use the client MAC address method.</span></span>



</div>

</div>

<div>

## <a name="subnet"></a><span data-ttu-id="353bb-128">서브넷</span><span class="sxs-lookup"><span data-stu-id="353bb-128">Subnet</span></span>

<span data-ttu-id="353bb-129">계층 3 IP 서브넷은 클라이언트 위치를 자동으로 검색 하는 데 사용할 수 있는 모든 Lync Server 클라이언트에서 지원 되는 메커니즘을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="353bb-129">Layer 3 IP subnets provide a mechanism supported by all Lync Server clients that can be used to automatically detect client location.</span></span> <span data-ttu-id="353bb-130">유선 클라이언트를 구성 하 고 관리 하는 가장 쉬운 위치 방법은 IP 서브넷을 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="353bb-130">Using IP subnets is the easiest location method to configure and manage wired clients.</span></span> <span data-ttu-id="353bb-131">그러나 서브넷을 사용 하기로 결정 하기 전에 다음 질문을 사용 하 여 서브넷의 위치가 클라이언트를 정확 하 게 찾는 데 충분 한지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="353bb-131">Before you decide to use subnets, however, use the following questions to help determine if the location specificity of the subnet is sufficiently fine to accurately locate a client:</span></span>

  - <span data-ttu-id="353bb-132">하나 이상의 클라이언트 서브넷에 여러 층이 포함 되나요?</span><span class="sxs-lookup"><span data-stu-id="353bb-132">Do one or more client subnets cover multiple floors?</span></span>

  - <span data-ttu-id="353bb-133">하나 이상의 서브넷이 두 개 이상의 건물을 차지 하 고 있나요?</span><span class="sxs-lookup"><span data-stu-id="353bb-133">Do one or more subnets cover more than one building?</span></span>

  - <span data-ttu-id="353bb-134">각 클라이언트 서브넷에 포함 되는 바닥 공간은 얼마나 되나요?</span><span class="sxs-lookup"><span data-stu-id="353bb-134">How much floor space is covered by each client subnet?</span></span>

<span data-ttu-id="353bb-135">서브넷이 너무 광범위 한 영역을 포함 하는 경우에는 다른 메커니즘을 사용 하 여 클라이언트를 찾아야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="353bb-135">If the subnet covers too broad an area, you may need to use another mechanism to locate clients.</span></span> <span data-ttu-id="353bb-136">그러나 실질적으로는 타사 SNMP 기반 솔루션의 비용과 복잡성을 준수 하는 대신 ERL 위치 specificity 요구 사항에 맞게 고객의 IP 서브넷을 재구성 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="353bb-136">However, if at all practical, we recommend that customers reorganize their IP subnetting to meet the ERL location specificity requirements rather than incurring the cost and complexity of third-party SNMP-based solutions.</span></span>

</div>

<div>

## <a name="client-mac-address"></a><span data-ttu-id="353bb-137">클라이언트 MAC 주소</span><span class="sxs-lookup"><span data-stu-id="353bb-137">Client MAC Address</span></span>

<span data-ttu-id="353bb-138">클라이언트 컴퓨터의 MAC 주소를 사용 하 여 발신자를 찾으려면 관리 되는 이더넷 스위치가 필요 하며, 해당 스위치에 연결 된 Lync 클라이언트의 MAC 주소를 검색할 수 있는 타사 SNMP 솔루션을 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="353bb-138">To use a client computer's MAC address to locate a caller, you need managed Ethernet switches, and you must deploy a third-party SNMP solution that can discover the MAC addresses of Lync clients connected to (or through) those switches.</span></span> <span data-ttu-id="353bb-139">SNMP 솔루션은 계속 해 서 관리 스위치를 폴링하여 각 포트에 연결 된 끝점 MAC 주소의 현재 매핑을 가져와 해당 포트 Id를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="353bb-139">The SNMP solution continually polls the managed switches to get the current mappings of the endpoint MAC addresses connected to each port and obtains the corresponding port IDs.</span></span> <span data-ttu-id="353bb-140">발신자 클라이언트가 위치 정보 서비스에 대 한 요청을 하는 동안 위치 정보 서비스는 클라이언트의 MAC 주소를 사용 하 여 타사 응용 프로그램을 쿼리 한 다음 일치 하는 스위치 IP 주소와 포트 Id를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="353bb-140">During a Lync client’s request to the Location Information service, the Location Information service queries the third-party application by using the client’s MAC address, and then returns any matching switch IP addresses and port IDs.</span></span> <span data-ttu-id="353bb-141">위치 정보 서비스는이 정보를 사용 하 여 일치 하는 레코드에 대해 게시 된 계층 2 wiremap 매핑 쿼리를 쿼리하고 클라이언트로의 위치를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="353bb-141">The Location Information service uses this information to query its published Layer 2 wiremap for a matching record and returns the location to the client.</span></span> <span data-ttu-id="353bb-142">이 옵션을 사용 하는 경우 SNMP 응용 프로그램과 게시 된 위치 데이터베이스 레코드 간에 스위치 포트 식별자가 일관 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="353bb-142">If you use this option, make sure that the switch port identifiers are consistent between the SNMP application and the published location database records.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="353bb-143">일부 타사 SNMP 솔루션은 관리 되지 않는 액세스 전환을 지원할 수 있습니다. Lync 클라이언트를 서비스 하는 스위치가 관리 되지 않지만 관리 되는 배포 스위치로 업링크를가지고 있는 경우 관리 되는 스위치는 액세스 스위치에 연결 된 클라이언트의 MAC 주소를 SNMP 응용 프로그램으로 다시 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="353bb-143">Some third-party SNMP solutions can support unmanaged access switches; if the switch that services the Lync client is unmanaged but has an uplink to a managed distribution switch, the managed switch can report back to the SNMP application the MAC addresses of the clients connected to the access switch.</span></span> <span data-ttu-id="353bb-144">이 정보는 위치 정보 서비스에서 사용자의 위치를 식별 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="353bb-144">This information enables the Location Information service to identify the location of the user.</span></span> <span data-ttu-id="353bb-145">그러나 관리 되지 않는 스위치의 모든 포트에 단일 ERL 할당할 수 있으므로 위치 specificity는 포트 수준이 아닌 액세스 스위치의 섀시 수준 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="353bb-145">However, it is possible to assign only a single ERL to all ports on the unmanaged switch, so the location specificity is available only at the chassis level of the access switch, not the port level.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

