---
title: 비즈니스용 Skype 서버에서 위치를 결정하는 데 사용되는 네트워크 요소 정의
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 7538779d-055d-44ed-8dd7-11c45fc1b9f5
description: 비즈니스용 Skype 서버 2013에서 E9-1-1 배포를 위해 발신자 위치를 매핑하는 데 사용할 네트워크 구성 요소를 계획하는 데 Enterprise Voice.
ms.openlocfilehash: 473ef9efc8598b303d6c7a05b902d57e0ad8ffd5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813638"
---
# <a name="define-the-network-elements-used-to-determine-location-in-skype-for-business-server"></a><span data-ttu-id="14909-103">비즈니스용 Skype 서버에서 위치를 결정하는 데 사용되는 네트워크 요소 정의</span><span class="sxs-lookup"><span data-stu-id="14909-103">Define the network elements used to determine location in Skype for Business Server</span></span>
 
<span data-ttu-id="14909-104">비즈니스용 Skype 서버 2013에서 E9-1-1 배포를 위해 발신자 위치를 매핑하는 데 사용할 네트워크 구성 요소를 계획하는 데 Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="14909-104">Decisions necessary for planning which network components you will use to map callers to locations for E9-1-1 deployment in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="14909-105">자동 클라이언트 위치 검색을 지원하기 위해 비즈니스용 Skype 서버 인프라를 설정하는 경우 먼저 발신자 위치를 매핑하는 데 사용할 네트워크 요소를 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14909-105">If you are setting up your Skype for Business Server infrastructure to support automatic client location detection, you first need to decide which network elements you are going to use to map callers to locations.</span></span> <span data-ttu-id="14909-106">비즈니스용 Skype 서버에서는 다음 계층 2 및 계층 3 네트워크 요소를 위치와 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14909-106">In Skype for Business Server, you can associate the following Layer 2 and Layer 3 network elements with locations:</span></span>
  
- <span data-ttu-id="14909-107">WAP(무선 액세스 지점) BSSID(Basic Service Set Identification) 주소(계층 2)</span><span class="sxs-lookup"><span data-stu-id="14909-107">Wireless access point (WAP) Basic Service Set Identification (BSSID) addresses (Layer 2)</span></span>
    
- <span data-ttu-id="14909-108">LLDP 스위치 포트(계층 2)</span><span class="sxs-lookup"><span data-stu-id="14909-108">LLDP switch port (Layer 2)</span></span>
    
- <span data-ttu-id="14909-109">LLDP 스위치 섀시 ID(계층 2)</span><span class="sxs-lookup"><span data-stu-id="14909-109">LLDP switch chassis IDs (Layer 2)</span></span>
    
- <span data-ttu-id="14909-110">IP 서브넷(계층 3)</span><span class="sxs-lookup"><span data-stu-id="14909-110">IP subnets (Layer 3)</span></span>
    
- <span data-ttu-id="14909-111">클라이언트 MAC 주소(계층 2)</span><span class="sxs-lookup"><span data-stu-id="14909-111">Client MAC addresses (Layer 2)</span></span>
    
<span data-ttu-id="14909-112">네트워크 요소는 우선 순위대로 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14909-112">The network elements are listed in order of precedence.</span></span> <span data-ttu-id="14909-113">클라이언트가 두 개 이상의 네트워크 요소를 사용하여 위치할 수 있는 경우 비즈니스용 Skype 서버는 우선 순위를 사용하여 사용할 메커니즘을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="14909-113">If a client can be located by using more than one network element, Skype for Business Server uses the order of precedence to determine which mechanism to use.</span></span> 
  
<span data-ttu-id="14909-114">다음 섹션에서는 각 네트워크 요소 사용에 대해 자세하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="14909-114">The following sections provide more details for using each network element.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="14909-115">네트워크 요소를 사용하여 발신자 위치를 매핑하는 경우 위치 정보 서비스 데이터베이스를 최신으로 유지하는 것이 가장 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="14909-115">When you use network elements to map callers to locations, it is of utmost importance that you keep the Location Information service database up-to-date.</span></span> <span data-ttu-id="14909-116">예를 들어 WAP를 추가하는 등 네트워크 요소를 추가하거나 변경하려면 오래된 항목을 삭제하고 위치 데이터베이스에 새 항목을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14909-116">For example, if you add or change a network element, such as adding a WAP, you must delete the old entry and add the new entry in the location database.</span></span> 
  
## <a name="wireless-access-point"></a><span data-ttu-id="14909-117">무선 액세스 지점</span><span class="sxs-lookup"><span data-stu-id="14909-117">Wireless Access Point</span></span>

<span data-ttu-id="14909-118">클라이언트가 네트워크에 무선으로 연결하면 위치 요청이 WAP의 BSSID 주소를 사용하여 해당 위치를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="14909-118">When a client connects to the network wirelessly, the location request uses the BSSID address of the WAP to determine its location.</span></span> <span data-ttu-id="14909-119">클라이언트가 로밍하는 경우 표시된 WAP가 가장 가까운 WAP가 아니며, 건물의 다른 층에 있는 WAP를 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14909-119">If the client is roaming, the WAP indicated may not be the closest one, and it's even possible to pick up a WAP that is on a different floor of the building.</span></span> <span data-ttu-id="14909-120">위치가 근사값을 나타내기 위해 위치 값을 **[Near] 또는 [Closeto]** 설명자에 추가하면 됩니다. </span><span class="sxs-lookup"><span data-stu-id="14909-120">To indicate that the location is approximate, you can prepend the location value with a **[Near]** or **[Closeto]** descriptor.</span></span>
  
<span data-ttu-id="14909-121">이 위치 방식은 각 WAP의 BSSID가 정적인 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="14909-121">This location method assumes that the BSSID of each WAP is static.</span></span> <span data-ttu-id="14909-122">그러나 WAP 공급업체에서 동적으로 할당된 BSSID를 사용하는 경우 WAP에서 얻은 BSSID가 변경될 수 있으며(WAP 구성 변경 후 이 문제가 발생), 무선 클라이언트가 위치를 받지 못하게 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14909-122">However, if your WAP vendor uses dynamically-assigned BSSIDs, the BSSID that is obtained from a WAP could change (this can happen following a WAP configuration change), and wireless clients could be left in a situation where they don't receive a location.</span></span> <span data-ttu-id="14909-123">이러한 문제를 방지하려면 각 WAP에서 사용할 수 있는 모든 BSSID 주소에 대한 ERL로 위치 정보 서비스 데이터베이스를 채워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14909-123">To prevent this possibility, you need to populate the Location Information service database with ERLs for all possible BSSID addresses used by each WAP.</span></span> 
  
## <a name="lldp-ports-and-switches"></a><span data-ttu-id="14909-124">LLDP 포트 및 스위치</span><span class="sxs-lookup"><span data-stu-id="14909-124">LLDP Ports and Switches</span></span>

<span data-ttu-id="14909-p106">LLDP-MED(Link Layer Discovery Protocol-Media Endpoint Discover)를 지원하는 관리되는 이더넷 스위치는 자신의 ID 및 포트 정보를 LLDP-MED 호환 클라이언트에 광고할 수 있으며, 위치 데이터베이스에 대해 이를 쿼리하여 장치 위치를 제공할 수 있습니다. 스위치 섀시 ID에서만 ERL을 연결하거나 이를 포트 수준으로 매핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14909-p106">Managed Ethernet switches that support Link Layer Discovery Protocol-Media Endpoint Discover (LLDP-MED) can advertise their identity and port information to LLDP-MED compatible clients, which then can be queried against the location database to provide the location of the device. You can associate ERLs solely on the switch chassis ID, or you can map them down to the port level.</span></span>
  
> [!NOTE]
> <span data-ttu-id="14909-127">비즈니스용 Skype 서버는 WINDOWS 8에서 실행되는 Lync Phone Edition 장치 및 비즈니스용 Skype 클라이언트의 위치만 결정하는 데 LLDP-MED를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14909-127">Skype for Business Server supports using LLDP-MED for determining locations only of Lync Phone Edition devices and Skype for Business clients running on Windows 8.</span></span> <span data-ttu-id="14909-128">스위치 수준 계층 2 데이터를 사용하여 다른 유선 PC 기반 비즈니스용 Skype 서버 클라이언트의 위치를 결정해야 하는 경우 클라이언트 MAC 주소 방법을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14909-128">If you need to use switch-level Layer 2 data to determine the location of other wired PC-based Skype for Business Server clients, you need to use the client MAC address method.</span></span> 
  
## <a name="subnet"></a><span data-ttu-id="14909-129">서브넷</span><span class="sxs-lookup"><span data-stu-id="14909-129">Subnet</span></span>

<span data-ttu-id="14909-130">계층 3 IP 서브넷은 클라이언트 위치를 자동으로 검색하는 데 사용할 수 있는 모든 비즈니스용 Skype 서버 클라이언트에서 지원하는 메커니즘을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="14909-130">Layer 3 IP subnets provide a mechanism supported by all Skype for Business Server clients that can be used to automatically detect client location.</span></span> <span data-ttu-id="14909-131">유선 클라이언트를 구성 및 관리하는 데에는 IP 서브넷을 사용하는 것이 가장 간편한 위치 방식입니다.</span><span class="sxs-lookup"><span data-stu-id="14909-131">Using IP subnets is the easiest location method to configure and manage wired clients.</span></span> <span data-ttu-id="14909-132">하지만 서브넷을 사용하도록 결정하기 전에 다음과 같은 질문을 고려해서 서브넷의 위치 특성이 클라이언트를 정확하게 찾는 데 충분히 적합한지 여부를 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="14909-132">Before you decide to use subnets, however, use the following questions to help determine if the location specificity of the subnet is sufficiently fine to accurately locate a client:</span></span>
  
- <span data-ttu-id="14909-133">한 개 또는 그 이상의 클라이언트 서브넷으로 여러 층이 지원됩니까?</span><span class="sxs-lookup"><span data-stu-id="14909-133">Do one or more client subnets cover multiple floors?</span></span>
    
- <span data-ttu-id="14909-134">한 개 또는 그 이상의 서브넷으로 건물 외부까지 지원됩니까?</span><span class="sxs-lookup"><span data-stu-id="14909-134">Do one or more subnets cover more than one building?</span></span>
    
- <span data-ttu-id="14909-135">각 클라이언트 서브넷으로 몇 층까지 지원됩니까?</span><span class="sxs-lookup"><span data-stu-id="14909-135">How much floor space is covered by each client subnet?</span></span>
    
<span data-ttu-id="14909-p109">서브넷이 너무 넓은 영역을 지원할 경우, 클라이언트 위치를 찾기 위한 다른 메커니즘을 사용해야 할 수 있습니다. 하지만 실용성을 높이기 위해서는 타사 SNMP 기반 솔루션으로 비용 및 복잡성을 늘리는 대신 ERL 위치 특성 요구 사항을 충족시킬 수 있도록 IP 서브넷 설정을 재구성하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="14909-p109">If the subnet covers too broad an area, you may need to use another mechanism to locate clients. However, if at all practical, we recommend that customers reorganize their IP subnetting to meet the ERL location specificity requirements rather than incurring the cost and complexity of third-party SNMP-based solutions.</span></span>
  
## <a name="client-mac-address"></a><span data-ttu-id="14909-138">클라이언트 MAC 주소</span><span class="sxs-lookup"><span data-stu-id="14909-138">Client MAC Address</span></span>

<span data-ttu-id="14909-139">클라이언트 컴퓨터의 MAC 주소를 사용하여 발신자 찾기를 위해 관리되는 이더넷 스위치가 필요하며, 해당 스위치에 연결된(또는 통해) 비즈니스용 Skype 클라이언트의 MAC 주소를 검색할 수 있는 타사 SNMP 솔루션을 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14909-139">To use a client computer's MAC address to locate a caller, you need managed Ethernet switches, and you must deploy a third-party SNMP solution that can discover the MAC addresses of Skype for Business clients connected to (or through) those switches.</span></span> <span data-ttu-id="14909-140">SNMP 솔루션은 관리되는 스위치를 지속적으로 폴링하여 각 포트에 연결된 끝점 MAC 주소의 현재 매핑을 가져오고 해당 포트 ID를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="14909-140">The SNMP solution continually polls the managed switches to get the current mappings of the endpoint MAC addresses connected to each port and obtains the corresponding port IDs.</span></span> <span data-ttu-id="14909-141">비즈니스용 Skype 클라이언트가 위치 정보 서비스에 요청하는 동안 위치 정보 서비스는 클라이언트의 MAC 주소를 사용하여 타사 응용 프로그램을 쿼리한 다음 일치하는 스위치 IP 주소와 포트 ID를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="14909-141">During a Skype for Business client's request to the Location Information service, the Location Information service queries the third-party application by using the client's MAC address, and then returns any matching switch IP addresses and port IDs.</span></span> <span data-ttu-id="14909-142">위치 정보 서비스는 이 정보를 사용하여 게시된 계층 2 와이어맵에서 일치하는 레코드를 쿼리하고 위치를 클라이언트에 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="14909-142">The Location Information service uses this information to query its published Layer 2 wiremap for a matching record and returns the location to the client.</span></span> <span data-ttu-id="14909-143">이 옵션을 사용할 경우 스위치 포트 식별자가 SNMP 응용 프로그램 및 게시된 위치 데이터베이스 레코드 사이에 일관적인지 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="14909-143">If you use this option, make sure that the switch port identifiers are consistent between the SNMP application and the published location database records.</span></span>
  
> [!NOTE]
> <span data-ttu-id="14909-144">일부 타사 SNMP 솔루션은 관리되지 않는 액세스 스위치를 지원할 수 있습니다. 비즈니스용 Skype 클라이언트에 서비스를 제공하는 스위치가 관리되지 않지만 관리되는 배포 스위치에 대한 업링크가 있는 경우 관리 스위치는 액세스 스위치에 연결된 클라이언트의 MAC 주소를 SNMP 응용 프로그램에 다시 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14909-144">Some third-party SNMP solutions can support unmanaged access switches; if the switch that services the Skype for Business client is unmanaged but has an uplink to a managed distribution switch, the managed switch can report back to the SNMP application the MAC addresses of the clients connected to the access switch.</span></span> <span data-ttu-id="14909-145">이 정보를 통해 위치 정보 서비스는 사용자의 위치를 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14909-145">This information enables the Location Information service to identify the location of the user.</span></span> <span data-ttu-id="14909-146">그러나 관리되지 않는 스위치의 모든 포트에 단일 ERL만 할당할 수 있으므로 위치 특정성은 포트 수준이 아닌 액세스 스위치의 섀시 수준에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14909-146">However, it is possible to assign only a single ERL to all ports on the unmanaged switch, so the location specificity is available only at the chassis level of the access switch, not the port level.</span></span> 
  

