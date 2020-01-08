---
title: Lync Server 2013 서버 하드웨어 플랫폼
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Server hardware platforms
ms:assetid: c964c1c0-0153-472b-88ad-a38866e0df0c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398835(v=OCS.15)
ms:contentKeyID: 48185395
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2682d0d8636c024dee4151842a143e65b11d48c5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984582"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-hardware-platforms-for-lync-server-2013"></a><span data-ttu-id="4ff9d-102">Lync Server 2013의 서버 하드웨어 플랫폼</span><span class="sxs-lookup"><span data-stu-id="4ff9d-102">Server hardware platforms for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4ff9d-103">_**마지막으로 수정한 주제:** 2016-07-28_</span><span class="sxs-lookup"><span data-stu-id="4ff9d-103">_**Topic Last Modified:** 2016-07-28_</span></span>

<span data-ttu-id="4ff9d-104">Lync server 2013 서버 역할 및 Lync Server 관리 도구를 실행 하는 컴퓨터에는 64 비트 하드웨어가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ff9d-104">Lync Server 2013 server roles and computers running Lync Server administrative tools require 64-bit hardware.</span></span>

<span data-ttu-id="4ff9d-105">Lync Server 2013 배포에 사용 되는 특정 하드웨어는 크기 및 사용 요구 사항에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ff9d-105">The specific hardware used for Lync Server 2013 deployment can vary, depending on size and usage requirements.</span></span> <span data-ttu-id="4ff9d-106">이 섹션에서는 권장 하드웨어에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ff9d-106">This section describes the recommended hardware.</span></span> <span data-ttu-id="4ff9d-107">이는 권장 사항은 아니지만 이러한 권장 사항을 충족 하지 않는 하드웨어를 사용 하는 경우 중대 한 성능 문제 및 기타 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ff9d-107">Although these are recommendations, not requirements, using hardware that does not meet these recommendations may result in significant performance issues and other issues.</span></span>

<div>

## <a name="recommended-hardware-platform"></a><span data-ttu-id="4ff9d-108">권장 하드웨어 플랫폼</span><span class="sxs-lookup"><span data-stu-id="4ff9d-108">Recommended Hardware Platform</span></span>

<span data-ttu-id="4ff9d-109">최상의 성능을 위해서는 다음 표의 요구 사항에 맞는 하드웨어를 사용 하 여 서버에서 Lync Server를 실행 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4ff9d-109">For best performance, we recommend that you run Lync Server on servers with hardware that meets the requirements in the following table.</span></span> <span data-ttu-id="4ff9d-110">덜 강력한 하드웨어를 사용 하는 경우 기능에 문제가 있거나 성능이 저하 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ff9d-110">If you use less powerful hardware, you may experience functionality problems or poor performance.</span></span> <span data-ttu-id="4ff9d-111">이러한 하드웨어 요구 사항은 주로 Lync Server 2013, 모든 프런트 엔드 서버에서 SQL Server를 실행 하기 때문에 이전 버전의 Lync Server 보다 더 높습니다.</span><span class="sxs-lookup"><span data-stu-id="4ff9d-111">Note that these hardware requirements are higher than those of previous versions of Lync Server, primarily because in Lync Server 2013, all Front End Servers run SQL Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4ff9d-112">NIC 팀은 지원 되며 Lync Server에 투명 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ff9d-112">NIC teaming is supported and should be transparent to Lync Server.</span></span> <span data-ttu-id="4ff9d-113">자세한 내용은 <A href="http://go.microsoft.com/fwlink/p/?linkid=389910">통신 서버 또는 Lync 서버 및 네트워크 어댑터 팀 구성을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4ff9d-113">For details, see <A href="http://go.microsoft.com/fwlink/p/?linkid=389910">Communications Server or Lync Server and network adapter teaming</A>.</span></span>



</div>

### <a name="recommended-hardware-for-front-end-servers-back-end-servers-standard-edition-servers-persistent-chat-servers-and-persistent-chat-store-and-persistent-chat-compliance-store-back-end-server-roles-for-persistent-chat-server"></a><span data-ttu-id="4ff9d-114">프론트 엔드 서버용 권장 하드웨어, 백 엔드 서버, 스탠더드 버전 서버, 영구 채팅 서버, 영구 채팅 및 영구 채팅 준수 저장소 (영구 채팅 서버용 백 엔드 서버 역할)</span><span class="sxs-lookup"><span data-stu-id="4ff9d-114">Recommended Hardware for Front End Servers, Back End Servers, Standard Edition Servers, Persistent Chat Servers, and Persistent Chat Store and Persistent Chat Compliance Store (Back End Server Roles for Persistent Chat Server)</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4ff9d-115">하드웨어 구성 요소</span><span class="sxs-lookup"><span data-stu-id="4ff9d-115">Hardware component</span></span></th>
<th><span data-ttu-id="4ff9d-116">권장</span><span class="sxs-lookup"><span data-stu-id="4ff9d-116">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4ff9d-117">%</span><span class="sxs-lookup"><span data-stu-id="4ff9d-117">CPU</span></span></p></td>
<td><p><span data-ttu-id="4ff9d-118">64 비트 듀얼 프로세서, 16 진수 코어, 2.26 ghz 이상.</span><span class="sxs-lookup"><span data-stu-id="4ff9d-118">64-bit dual processor, hex-core, 2.26 gigahertz (GHz) or higher.</span></span></p>
<p><span data-ttu-id="4ff9d-119">인텔 아이테니엄 프로세서는 Lync Server 서버 역할에 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4ff9d-119">Intel Itanium processors are not supported for Lync Server server roles.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ff9d-120">Memory</span><span class="sxs-lookup"><span data-stu-id="4ff9d-120">Memory</span></span></p></td>
<td><p><span data-ttu-id="4ff9d-121">32 기가바이트 (GB).</span><span class="sxs-lookup"><span data-stu-id="4ff9d-121">32 gigabytes (GB).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ff9d-122">공간</span><span class="sxs-lookup"><span data-stu-id="4ff9d-122">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="4ff9d-123">최소 72 GB의 사용 가능한 디스크 공간을 갖춘 8 개 이상의 1만 RPM 하드 디스크 드라이브.</span><span class="sxs-lookup"><span data-stu-id="4ff9d-123">8 or more 10,000 RPM hard disk drives with at least 72 GB free disk space.</span></span></p>
<p><span data-ttu-id="4ff9d-124">두 개의 디스크에서 RAID 1을 사용 하 고 6 개는 RAID 10을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ff9d-124">Two of the disks should use RAID 1, and six should use RAID 10.</span></span></p>
<p><span data-ttu-id="4ff9d-125">-또는</span><span class="sxs-lookup"><span data-stu-id="4ff9d-125">- OR -</span></span></p></li>
<li><p><span data-ttu-id="4ff9d-126">8 1만-RPM 기계 디스크 드라이브와 유사한 성능을 제공 하는 Ssd (고체 스테이트 드라이브).</span><span class="sxs-lookup"><span data-stu-id="4ff9d-126">Solid state drives (SSDs) which provide performance similar to 8 10,000-RPM mechanical disk drives.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ff9d-127">네트워크</span><span class="sxs-lookup"><span data-stu-id="4ff9d-127">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="4ff9d-128">1 개의 듀얼 포트 네트워크 어댑터, 1Gbps 이상 (2 권장, 단일 MAC 주소 및 단일 IP 주소를 사용 하는 팀이 필요 함)</span><span class="sxs-lookup"><span data-stu-id="4ff9d-128">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address).</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="4ff9d-129">프런트 엔드 서버, 백 엔드 서버, Standard Edition 서버 및 영구 채팅 서버에서는 듀얼 또는 멀티홈 구성이 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4ff9d-129">Dual or multi-homed configurations are not supported for Front End Servers, Back End Servers, Standard Edition servers, and Persistent Chat Servers.</span></span><BR><span data-ttu-id="4ff9d-130">ILO/DRAC/기타. 운영 체제에 표시 되지 않고 서버 하드웨어를 모니터링 하 고 관리 하는 데 사용 되는 연결은 멀티홈 서버를 구성 하지 않으므로 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ff9d-130">ILO/DRAC/etc. connections not exposed to the Operating System and used to monitor and manage the server hardware do not constitute a multi-homed server and thus are supported.</span></span>


</div></li>
</ul></td>
</tr>
</tbody>
</table>


### <a name="recommended-hardware-for-edge-servers-standalone-mediation-servers-and-directors"></a><span data-ttu-id="4ff9d-131">Edge 서버, 독립 실행형 중재 서버 및 디렉터에 권장 되는 하드웨어</span><span class="sxs-lookup"><span data-stu-id="4ff9d-131">Recommended Hardware for Edge Servers, Standalone Mediation Servers, and Directors</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4ff9d-132">하드웨어 구성 요소</span><span class="sxs-lookup"><span data-stu-id="4ff9d-132">Hardware component</span></span></th>
<th><span data-ttu-id="4ff9d-133">권장</span><span class="sxs-lookup"><span data-stu-id="4ff9d-133">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4ff9d-134">%</span><span class="sxs-lookup"><span data-stu-id="4ff9d-134">CPU</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="4ff9d-135">64 비트 듀얼 프로세서, 쿼드 코어, 2.0 ghz 이상</span><span class="sxs-lookup"><span data-stu-id="4ff9d-135">64-bit dual processor, quad-core, 2.0 gigahertz (GHz) or higher.</span></span></p>
<p><span data-ttu-id="4ff9d-136">-또는</span><span class="sxs-lookup"><span data-stu-id="4ff9d-136">- OR -</span></span></p></li>
<li><p><span data-ttu-id="4ff9d-137">64 비트 4 방향 프로세서, 듀얼 코어, 2.0 GHz 이상.</span><span class="sxs-lookup"><span data-stu-id="4ff9d-137">64-bit 4-way processor, dual-core, 2.0 GHz or higher.</span></span></p></li>
</ul>
<p><span data-ttu-id="4ff9d-138">인텔 아이테니엄 프로세서는 Lync Server 서버 역할에 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4ff9d-138">Intel Itanium processors are not supported for Lync Server server roles.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ff9d-139">Memory</span><span class="sxs-lookup"><span data-stu-id="4ff9d-139">Memory</span></span></p></td>
<td><p><span data-ttu-id="4ff9d-140">16gb (GB).</span><span class="sxs-lookup"><span data-stu-id="4ff9d-140">16 gigabytes (GB).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ff9d-141">공간</span><span class="sxs-lookup"><span data-stu-id="4ff9d-141">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="4ff9d-142">최소 72 GB의 사용 가능한 디스크 공간을 제공 하는 4 개 이상의 1만 RPM 하드 디스크 드라이브.</span><span class="sxs-lookup"><span data-stu-id="4ff9d-142">4 or more 10,000 RPM hard disk drives with at least 72 GB free disk space.</span></span></p>
<p><span data-ttu-id="4ff9d-143">디스크는 2 배로 RAID 1에 구성 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ff9d-143">The disks should be in a 2x RAID 1 configuration.</span></span></p>
<p><span data-ttu-id="4ff9d-144">-또는</span><span class="sxs-lookup"><span data-stu-id="4ff9d-144">- OR -</span></span></p></li>
<li><p><span data-ttu-id="4ff9d-145">4 1만-RPM 기계 디스크 드라이브와 유사한 성능을 제공 하는 Ssd (고체 스테이트 드라이브).</span><span class="sxs-lookup"><span data-stu-id="4ff9d-145">Solid state drives (SSDs) which provide performance similar to 4 10,000-RPM mechanical disk drives.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ff9d-146">네트워크</span><span class="sxs-lookup"><span data-stu-id="4ff9d-146">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="4ff9d-147">1 개의 듀얼 포트 네트워크 어댑터, 1Gbps 이상 (2 권장, 단일 MAC 주소 및 단일 IP 주소를 사용 하는 팀이 필요 함)</span><span class="sxs-lookup"><span data-stu-id="4ff9d-147">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address).</span></span> <span data-ttu-id="4ff9d-148">2 네트워크 인터페이스는 Edge 서버에 필요 하며 독립 실행형 중재 서버에서 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ff9d-148">2 network interfaces are required on Edge Servers, and are supported on standalone Mediation Servers.</span></span></p></li>
</ul>
<div>

> [!NOTE]  
> <span data-ttu-id="4ff9d-149">이중 또는 멀티홈 구성은 디렉터에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4ff9d-149">Dual or multi-homed configurations are not supported for Directors.</span></span><BR><span data-ttu-id="4ff9d-150">ILO/DRAC/기타. 운영 체제에 표시 되지 않고 서버 하드웨어를 모니터링 하 고 관리 하는 데 사용 되는 연결은 멀티홈 서버를 구성 하지 않으므로 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ff9d-150">ILO/DRAC/etc. connections not exposed to the Operating System and used to monitor and manage the server hardware do not constitute a multi-homed server and thus are supported.</span></span>


</div>
<p><span data-ttu-id="4ff9d-151">Edge 서버에는 이중 포트 네트워크 어댑터용 1 Gbps 이상 (또는 두 개의 연결 된 네트워크 어댑터와 총 4 개, 단일 MAC 주소와 단일 IP 주소로 그룹화 된 각 쌍 중 총 2 쌍) 인 2 개의 네트워크 인터페이스가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ff9d-151">Edge Servers will require two network interfaces that are dual-port network adapters, 1 Gbps or higher (or two paired network adapters, for a total of four, each pair being teamed with a single MAC address and a single IP address, for a total of two pairs).</span></span></p>
<p><span data-ttu-id="4ff9d-152">독립 실행형 중재 서버에서 특정 PSTN IP 주소 구성을 허용 하는 추가 Nic (네트워크 인터페이스 카드)를 설치 하는 것이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ff9d-152">Installation of additional network interface cards (NICs) to allow the configuration of a specific PSTN IP address is supported on standalone Mediation Servers.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

