---
title: 'Lync Server 2013: 네트워크 성능 모니터링'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring network performance
ms:assetid: bc3a01da-91eb-4c0c-9598-35e5e46b00f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720923(v=OCS.15)
ms:contentKeyID: 63969647
ms.date: 04/27/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2fa3c2685b4da32d5f2e3f123a938920b5ce9f7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982874"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-network-performance-in-lync-server-2013"></a><span data-ttu-id="308e1-102">Lync Server 2013의 네트워크 성능 모니터링</span><span class="sxs-lookup"><span data-stu-id="308e1-102">Monitoring network performance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="308e1-103">_**마지막으로 수정한 주제:** 2016-04-27_</span><span class="sxs-lookup"><span data-stu-id="308e1-103">_**Topic Last Modified:** 2016-04-27_</span></span>

<span data-ttu-id="308e1-104">Lync Server 2013는 IM (인스턴트 메시징), 음성 통화 또는 비디오 통신을 통해 사용자 간의 통신을 가능 하 게 하는 실시간 통신 기술로, 네트워크에 크게 의존 합니다.</span><span class="sxs-lookup"><span data-stu-id="308e1-104">Lync Server 2013 is a real-time communications technology that relies heavily on the network to enable communication between users—either through instant messaging (IM), voice calls, or video communication.</span></span> <span data-ttu-id="308e1-105">따라서 사용자가 선택한 통신 모달을 최대한 활용할 수 있도록 네트워크 성능을 지속적으로 모니터링 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="308e1-105">It is therefore important to monitor the network performance continuously to help guarantee that a user’s chosen communication modality provides the best possible experience.</span></span>

<span data-ttu-id="308e1-106">네트워크 성능은 다음 두 가지 수준으로 측정 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="308e1-106">Network performance can be measured at two levels:</span></span>

  - <span data-ttu-id="308e1-107">**전체 네트워크 성능**   이 수준의 성능 측정은 조직에서 네트워크의 "대규모 그림" 보기를 만들 수 있도록 하 고, 일반적으로 타사 네트워크 모니터링 시스템을 통해 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="308e1-107">**Overall network performance**   This level of performance measurement will allow an organization to create a "big-picture" view of their network and is usually implemented through third-party network monitoring systems.</span></span> <span data-ttu-id="308e1-108">이러한 시스템은 라우터 등의 원격 네트워크 장치에서 성능 및 용량 데이터를 수신 하 고, 관리자가 언제 든 지 지정 된 네트워크 구성 요소의 상태를 확인할 수 있도록 네트워크 전체에서 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="308e1-108">These systems will receive performance and capacity data from remote network devices such as routers and switched throughout the network to allow administrators to determine the health of any given network component at any time of day.</span></span>

  - <span data-ttu-id="308e1-109">**개별 서버 성능**   이 수준의 성능 측정은 특정 서버로 제한 되며, 관리자가 특정 성능 문제를 해결 하는 데 도움이 되거나 특정 기간에 대 한 각 서버의 성능을 용량 계획 프로세스의 일부로 평가할 수 있도록 해당 서버의 네트워크 성능을 측정 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="308e1-109">**Individual server performance**   This level of performance measurement is limited to a specific server and will help administrators with gauging the network performance of a specific server to either help with troubleshooting a specific performance issue or to gauge the respective server’s performance over a given period as part of a capacity planning process.</span></span>

<span data-ttu-id="308e1-110">다음 섹션에서 설명 하는 도구를 사용 하 여 네트워크를 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="308e1-110">You can monitor the network by using the tools described in the following sections.</span></span>

<div>

## <a name="tools-for-overall-network-performance-monitoring"></a><span data-ttu-id="308e1-111">전체 네트워크 성능 모니터링 도구</span><span class="sxs-lookup"><span data-stu-id="308e1-111">Tools for Overall Network Performance Monitoring</span></span>

<div>

## <a name="system-center-operations-manager-2012"></a><span data-ttu-id="308e1-112">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="308e1-112">System Center Operations Manager 2012</span></span>

<span data-ttu-id="308e1-113">System Center Operations Manager는 IT 환경의 서비스 수준을 개선 하기 위해 쉽게 사용자 지정 하 고 확장할 수 있는 종단 간 서비스 관리를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="308e1-113">System Center Operations Manager provides end-to-end service management that is easy to customize and extend for improved service levels across an IT environment.</span></span> <span data-ttu-id="308e1-114">이렇게 하면 작업 및 IT 관리 팀이 분산 IT 서비스의 상태에 영향을 주는 문제를 식별 하 고 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="308e1-114">This enables Operations and IT Management teams to identify, and resolve issues affecting the health of distributed IT services.</span></span> <span data-ttu-id="308e1-115">엔드 투 엔드 서비스 관리는 Microsoft 기반 환경으로 제한 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="308e1-115">End-to-end service management is not restricted to Microsoft-based environments.</span></span> <span data-ttu-id="308e1-116">관리 (WS-MANAGEMENT)에 대 한 웹 서비스 지원, SNMP (단순 네트워크 관리 프로토콜), 파트너 솔루션을 통해 Microsoft 운영 체제 및 하드웨어를 실행 하지 않는 시스템에서 시스템 센터 내 서비스 모니터링에 포함할 수 있습니다. Operations Manager 2012.</span><span class="sxs-lookup"><span data-stu-id="308e1-116">Support for Web Services for Management (WS-Management), Simple Network Management Protocol (SNMP), and partner solutions allow for systems that do not run Microsoft operating systems and hardware to be included in service monitoring within System Center Operations Manager 2012.</span></span>

</div>

<div>

## <a name="system-center-operations-manager-2012-and-third-party-network-management-solutions"></a><span data-ttu-id="308e1-117">System Center Operations Manager 2012 및 타사 네트워크 관리 솔루션</span><span class="sxs-lookup"><span data-stu-id="308e1-117">System Center Operations Manager 2012 and Third-Party Network Management Solutions</span></span>

<span data-ttu-id="308e1-118">**Emc Smarts**   emc Operations Manager 솔루션에 대 한 해결 방법은 전체 서비스 수준에 영향을 주는 문제를 빠르게 해결할 수 있도록 도와줍니다.</span><span class="sxs-lookup"><span data-stu-id="308e1-118">**EMC Smarts**   EMC Solutions for Operations Manager help you quickly resolve issues affecting service levels throughout.</span></span> <span data-ttu-id="308e1-119">Operations Manager에 EMC 솔루션을 사용 하 여 통합 된 자동화 솔루션 하나로 전체 IT 서비스 체인을 관리 및 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="308e1-119">By using EMC Solutions for Operations Manager, you can manage and monitor your whole IT service chain with one integrated, automated solution.</span></span> <span data-ttu-id="308e1-120">성능 및 사용 가능성 문제의 근본 원인을 쉽게 식별 하 고 효과와 비용을 줄일 수 있도록 신속 하 게 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="308e1-120">You'll easily identify the root causes of performance and availability issues, and resolve them faster which reduces effects and costs.</span></span> <span data-ttu-id="308e1-121">주요 이점에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="308e1-121">Key benefits include the following:</span></span>

  - <span data-ttu-id="308e1-122">더욱 간편한 고급 관리는 혼란 스러운 알림을 수동으로 정렬 하 고 필터링 하는 대신 전략적 비즈니스 가치를 제공 하는 데 초점을 맞춘 것입니다.</span><span class="sxs-lookup"><span data-stu-id="308e1-122">Advanced, easy-to-use management   Focus on delivering strategic business value instead of manually sorting and filtering confusing alerts.</span></span>

  - <span data-ttu-id="308e1-123">**더 빠른 해상도**   를 통해 IT의 문제를 해결 하 고 비즈니스 요구에 대 한 대처 속도를 줄이고 효과와 비용을 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="308e1-123">**Faster resolution**   Solve IT issues and respond to business needs faster, reducing effect and cost.</span></span>

  - <span data-ttu-id="308e1-124">**효율적인 작업**   을 사용 하면 여러 관리 도구, 응용 프로그램 및 터미널을 결합 하 여 복잡성을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="308e1-124">**Streamlined operations**   Avoid IT complexity by combining multiple management tools, applications, and terminals.</span></span>

<span data-ttu-id="308e1-125">자세한 내용은 다음을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="308e1-125">More information can be found here:</span></span>

[<span data-ttu-id="308e1-126">Microsoft System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="308e1-126">Microsoft System Center Operations Manager</span></span>](http://go.microsoft.com/fwlink/p/?linkid=243651)

[<span data-ttu-id="308e1-127">Microsoft System Center Operations Manager 솔루션</span><span class="sxs-lookup"><span data-stu-id="308e1-127">Solutions for Microsoft System Center Operations Manager</span></span>](http://www.emc.com/collateral/software/data-sheet/h6135-server-manager-ds.pdf)

</div>

<div>

## <a name="third-party-solutions"></a><span data-ttu-id="308e1-128">타사 솔루션</span><span class="sxs-lookup"><span data-stu-id="308e1-128">Third-Party Solutions</span></span>

<span data-ttu-id="308e1-129">Hp **네트워크 관리 센터 (이전의 Hp OpenView)**   [Hp 네트워크 관리 센터](http://www8.hp.com/us/en/software-solutions/network-management/index.html?%26zn=bto%26cp=1-11-15-119_4000_100__) 는 네트워크 가용성 및 성능을 향상 시키기 위해 통합 된 오류 및 성능 관리를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="308e1-129">**HP Network Management Center (previously known as HP OpenView)**   [HP Network Management Center](http://www8.hp.com/us/en/software-solutions/network-management/index.html?%26zn=bto%26cp=1-11-15-119_4000_100__) provides integrated fault and performance management to improve network availability and performance.</span></span> <span data-ttu-id="308e1-130">네트워크 관리 센터는 결함, 성능, 구성, 변경 관리를 통합 하는 HP 자동화 네트워크 관리 솔루션의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="308e1-130">Network Management Center is part of the HP automated network management solution that unifies fault, performance, configuration, and change management.</span></span>

<span data-ttu-id="308e1-131">**엔터프라이즈 용 cisco 네트워크 관리 및 자동화 제품**   cisco에는 운영 효율성을 높이고 네트워크 중단 시간을 줄일 수 있도록 CiscoWorks LAN 관리 솔루션과 cisco 네트워크 분석 모듈을 포함 하 여 다양 한 관리 제품이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="308e1-131">**Cisco Network Management and Automation products**   For the Enterprise, Cisco has several management products available including CiscoWorks LAN Management Solution and Cisco Network Analysis Module, to help improve operational efficiency and reduce network downtime.</span></span> <span data-ttu-id="308e1-132">이러한 제품에 대 한 추가 정보는의 Cisco 웹 사이트를 [http://www.cisco.com/en/US/products/sw/netmgtsw/index.html](http://www.cisco.com/en/us/products/sw/netmgtsw/index.html)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="308e1-132">For additional data on these products, refer to the Cisco website at [http://www.cisco.com/en/US/products/sw/netmgtsw/index.html](http://www.cisco.com/en/us/products/sw/netmgtsw/index.html).</span></span>

<span data-ttu-id="308e1-133">SNMP (단순 네트워크 관리 프로토콜) SNMP (단순 네트워크 관리 프로토콜)는 TCP/IP 네트워크를 관리 하는 전략을 정의 하는 네트워크 관리 표준입니다.</span><span class="sxs-lookup"><span data-stu-id="308e1-133">Simple Network Management Protocol (SNMP)   Simple Network Management Protocol (SNMP) is a network management standard that defines a strategy for managing TCP/IP networks.</span></span> <span data-ttu-id="308e1-134">SNMP를 사용 하 여 네트워크에 대 한 구성 및 상태 정보를 캡처하여 이벤트 모니터링을 위해 지정 된 컴퓨터에 정보를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="308e1-134">SNMP enables you to capture configuration and status information about the network, and send the information to a designated computer for event monitoring.</span></span> <span data-ttu-id="308e1-135">이 표준 기반 네트워크 관리 프로토콜은 다음을 포함 하는 분산 아키텍처를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="308e1-135">This standards based network management protocol uses a distributed architecture that includes the following:</span></span>

  - <span data-ttu-id="308e1-136">각각 관리 계측에 대 한 원격 액세스를 제공 하는 에이전트 라는 SNMP 엔터티를 포함 하는 여러 관리 되는 노드입니다.</span><span class="sxs-lookup"><span data-stu-id="308e1-136">Multiple managed nodes, each with an SNMP entity called an agent which provides remote access to management instrumentation.</span></span>

  - <span data-ttu-id="308e1-137">관리 응용 프로그램을 실행 하 여 관리 요소를 모니터링 하 고 제어 하는 관리자 라고 하는 하나 이상의 SNMP 엔터티.</span><span class="sxs-lookup"><span data-stu-id="308e1-137">At least one SNMP entity known as a manager which runs management applications to monitor and control managed elements.</span></span> <span data-ttu-id="308e1-138">관리 요소는 호스트, 라우터 등의 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="308e1-138">Managed elements are devices such as hosts, routers, and so on.</span></span> <span data-ttu-id="308e1-139">관리 정보에 액세스 하 여 모니터링 및 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="308e1-139">They are monitored and controlled by accessing their management information.</span></span>

  - <span data-ttu-id="308e1-140">관리 프로토콜인 SNMP는 관리 스테이션과 에이전트 간에 관리 정보를 전달 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="308e1-140">A management protocol, SNMP, is used to communicate management information between the management stations and agents.</span></span> <span data-ttu-id="308e1-141">관리 정보는 관리 정보 데이터베이스 (MIB) 라는 가상 정보 저장소에 상주 하는 관리 되는 개체의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="308e1-141">Management information refers to a collection of managed objects that live in a virtual information store called a Management Information Base (MIB).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="308e1-142">타사 네트워크 모니터링 솔루션의 예는 위에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="308e1-142">Examples of third-party network monitoring solutions are provided above.</span></span> <span data-ttu-id="308e1-143">이 목록은 결정적인 것이 아니므로 Microsoft는 특정 공급 업체 솔루션을 선호 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="308e1-143">This list is not definitive and Microsoft does not favor any specific vendor solution.</span></span> <span data-ttu-id="308e1-144">네트워크 서비스 공급자 또는 해당 기술 공급자에 게 문의 하 여 조직에 가장 적합 한 네트워크 모니터링 솔루션을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="308e1-144">Consult with a network service provider and or your respective technology provider to determine the best network monitoring solution for your organization.</span></span>



</div>

</div>

</div>

<div>

## <a name="tools-for-monitoring-individual-server-network-performance"></a><span data-ttu-id="308e1-145">개별 서버 네트워크 성능 모니터링 도구</span><span class="sxs-lookup"><span data-stu-id="308e1-145">Tools for Monitoring Individual Server Network Performance</span></span>

<div>

## <a name="system-center-operations-manager-2012"></a><span data-ttu-id="308e1-146">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="308e1-146">System Center Operations Manager 2012</span></span>

<span data-ttu-id="308e1-147">System Center Operations Manager 2012에서 관리자는 Windows Server 2012 관리 팩을 통해 개별 서버의 네트워크 성능을 볼 수 있습니다. Windows Server 운영 체제 관리 팩에는 "성능" 관리 팩이 포함 되어 있습니다. 이렇게 하면 관리자가 네트워크 어댑터 성능 및 어댑터 상태를 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="308e1-147">System Center Operations Manager 2012 would allow administrators to view network performance of individual servers through the Windows Server 2012 Management Pack: The Windows Server operating system management pack includes a "Performance" management pack that would allow administrators to monitor Network Adapter performance and adapter health.</span></span>

</div>

<div>

## <a name="windows-network-monitor"></a><span data-ttu-id="308e1-148">Windows 네트워크 모니터</span><span class="sxs-lookup"><span data-stu-id="308e1-148">Windows Network Monitor</span></span>

<span data-ttu-id="308e1-149">서버의 리소스 사용을 수집, 표시, 분석 하 고 네트워크 트래픽을 측정 합니다.</span><span class="sxs-lookup"><span data-stu-id="308e1-149">Collects, displays, analyzes resource usage on a server, and measures network traffic.</span></span> <span data-ttu-id="308e1-150">네트워크 모니터는 네트워크 활동을 독점적으로 모니터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="308e1-150">Network Monitor exclusively monitors network activity.</span></span> <span data-ttu-id="308e1-151">네트워크 데이터를 캡처 및 분석 하 고 성능 로그에이 데이터를 사용 하 여 네트워크 사용량을 확인 하 고 네트워크 문제를 식별 하 고 향후 네트워크 요구를 예측할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="308e1-151">By capturing and analyzing network data, and using this data with performance logs, you can determine the network usage, identify network issues, and forecast future network needs.</span></span>

<span data-ttu-id="308e1-152">네트워크 모니터 3.4에 대 한 자세한 내용과 네트워크 모니터를 설치 및 구성 하 고 데이터를 캡처 및 분석 하는 방법에 대 한 자세한 내용은이 세션을 검토 하세요. 네트워크 모니터 3.3 개요.</span><span class="sxs-lookup"><span data-stu-id="308e1-152">For more information about Network Monitor 3.4, and to learn how to install and configure Network Monitor and capture and analyze data, review this session: Network Monitor 3.3 Overview.</span></span> <span data-ttu-id="308e1-153">또한 [네트워크 모니터 블로그](http://blogs.technet.com/b/netmon/)를 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="308e1-153">Also, review the [Network Monitor blog](http://blogs.technet.com/b/netmon/).</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

