---
title: Lync Server 2013 서버 하드웨어 플랫폼
description: Lync Server 2013 서버 하드웨어 플랫폼
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server hardware platforms
ms:assetid: c964c1c0-0153-472b-88ad-a38866e0df0c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398835(v=OCS.15)
ms:contentKeyID: 48185395
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d55deec50994d70cf305b794662a630c16c3af14
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551384"
---
# <a name="server-hardware-platforms-for-lync-server-2013"></a><span data-ttu-id="c4379-103">Lync Server 2013 용 서버 하드웨어 플랫폼</span><span class="sxs-lookup"><span data-stu-id="c4379-103">Server hardware platforms for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c4379-104">_**마지막으로 수정 된 항목:** 2016-07-28_</span><span class="sxs-lookup"><span data-stu-id="c4379-104">_**Topic Last Modified:** 2016-07-28_</span></span>

<span data-ttu-id="c4379-105">Lync server 2013 서버 역할을 실행 하는 경우에는 64 비트 하드웨어가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4379-105">Lync Server 2013 server roles and computers running Lync Server administrative tools require 64-bit hardware.</span></span>

<span data-ttu-id="c4379-106">Lync Server 2013 배포에 사용 되는 특정 하드웨어는 크기 및 사용 요구 사항에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4379-106">The specific hardware used for Lync Server 2013 deployment can vary, depending on size and usage requirements.</span></span> <span data-ttu-id="c4379-107">이 섹션에서는 권장 하드웨어에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c4379-107">This section describes the recommended hardware.</span></span> <span data-ttu-id="c4379-108">이러한 사항은 요구 사항이 아닌 권장 사항이지만 이러한 권장 사항을 충족하지 않는 하드웨어를 사용할 경우 심각한 성능 문제 및 기타 문제가 야기될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4379-108">Although these are recommendations, not requirements, using hardware that does not meet these recommendations may result in significant performance issues and other issues.</span></span>

<div>

## <a name="recommended-hardware-platform"></a><span data-ttu-id="c4379-109">권장 하드웨어 플랫폼</span><span class="sxs-lookup"><span data-stu-id="c4379-109">Recommended Hardware Platform</span></span>

<span data-ttu-id="c4379-110">최적의 성능을 위해 다음 표의 요구 사항을 충족 하는 하드웨어가 포함 된 서버에서 Lync Server를 실행 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c4379-110">For best performance, we recommend that you run Lync Server on servers with hardware that meets the requirements in the following table.</span></span> <span data-ttu-id="c4379-111">덜 강력한 하드웨어를 사용 하는 경우에는 기능에 문제가 있거나 성능이 저하 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4379-111">If you use less powerful hardware, you may experience functionality problems or poor performance.</span></span> <span data-ttu-id="c4379-112">이러한 하드웨어 요구 사항은 주로 Lync Server 2013, 모든 프런트 엔드 서버에서 SQL Server를 실행 하기 때문에 이전 버전의 Lync Server 보다 더 높습니다.</span><span class="sxs-lookup"><span data-stu-id="c4379-112">Note that these hardware requirements are higher than those of previous versions of Lync Server, primarily because in Lync Server 2013, all Front End Servers run SQL Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c4379-113">NIC 팀은 지원 되며 Lync Server에 대해 투명 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4379-113">NIC teaming is supported and should be transparent to Lync Server.</span></span> <span data-ttu-id="c4379-114">자세한 내용은 <A href="https://go.microsoft.com/fwlink/p/?linkid=389910">Communications server Or Lync Server and network adapter 팀 구성을</A>참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c4379-114">For details, see <A href="https://go.microsoft.com/fwlink/p/?linkid=389910">Communications Server or Lync Server and network adapter teaming</A>.</span></span>



</div>

### <a name="recommended-hardware-for-front-end-servers-back-end-servers-standard-edition-servers-persistent-chat-servers-and-persistent-chat-store-and-persistent-chat-compliance-store-back-end-server-roles-for-persistent-chat-server"></a><span data-ttu-id="c4379-115">프런트 엔드 서버, 백 엔드 서버, Standard Edition Server, 영구 채팅 서버 및 영구 채팅 준수 저장소 (영구 채팅 서버에 대 한 백 엔드 서버 역할)에 대 한 권장 하드웨어</span><span class="sxs-lookup"><span data-stu-id="c4379-115">Recommended Hardware for Front End Servers, Back End Servers, Standard Edition Servers, Persistent Chat Servers, and Persistent Chat Store and Persistent Chat Compliance Store (Back End Server Roles for Persistent Chat Server)</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c4379-116">하드웨어 구성 요소</span><span class="sxs-lookup"><span data-stu-id="c4379-116">Hardware component</span></span></th>
<th><span data-ttu-id="c4379-117">권장</span><span class="sxs-lookup"><span data-stu-id="c4379-117">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c4379-118">CPU</span><span class="sxs-lookup"><span data-stu-id="c4379-118">CPU</span></span></p></td>
<td><p><span data-ttu-id="c4379-119">64 비트 이중 프로세서, 16 진수 코어, 2.26 ghz 이상</span><span class="sxs-lookup"><span data-stu-id="c4379-119">64-bit dual processor, hex-core, 2.26 gigahertz (GHz) or higher.</span></span></p>
<p><span data-ttu-id="c4379-120">Lync Server 서버 역할에는 Intel Itanium 프로세서가 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c4379-120">Intel Itanium processors are not supported for Lync Server server roles.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4379-121">메모리</span><span class="sxs-lookup"><span data-stu-id="c4379-121">Memory</span></span></p></td>
<td><p><span data-ttu-id="c4379-122">32 기가바이트 (GB)입니다.</span><span class="sxs-lookup"><span data-stu-id="c4379-122">32 gigabytes (GB).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4379-123">공간이</span><span class="sxs-lookup"><span data-stu-id="c4379-123">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c4379-124">72GB 이상의 사용 가능한 디스크 공간이 있는 10,000 RPM 하드 디스크 드라이브 8개 이상</span><span class="sxs-lookup"><span data-stu-id="c4379-124">8 or more 10,000 RPM hard disk drives with at least 72 GB free disk space.</span></span></p>
<p><span data-ttu-id="c4379-125">이 중 두 개는 RAID 1을 사용하고 6개는 RAID 10을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c4379-125">Two of the disks should use RAID 1, and six should use RAID 10.</span></span></p>
<p><span data-ttu-id="c4379-126">- 사용자나</span><span class="sxs-lookup"><span data-stu-id="c4379-126">- OR -</span></span></p></li>
<li><p><span data-ttu-id="c4379-127">8개의 10,000 RPM 기계식 디스크 드라이브와 유사한 성능을 제공하는 SDD(반도체 드라이브)</span><span class="sxs-lookup"><span data-stu-id="c4379-127">Solid state drives (SSDs) which provide performance similar to 8 10,000-RPM mechanical disk drives.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4379-128">네트워크</span><span class="sxs-lookup"><span data-stu-id="c4379-128">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c4379-129">1 개의 이중 포트 네트워크 어댑터, 1Gbps 이상 (2 개 권장, 단일 MAC 주소와 단일 IP 주소를 사용 하는 팀이 필요 함)</span><span class="sxs-lookup"><span data-stu-id="c4379-129">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address).</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="c4379-130">프런트 엔드 서버, 백 엔드 서버, Standard Edition 서버 및 영구 채팅 서버에는 이중 또는 멀티홈 구성이 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c4379-130">Dual or multi-homed configurations are not supported for Front End Servers, Back End Servers, Standard Edition servers, and Persistent Chat Servers.</span></span><BR><span data-ttu-id="c4379-131">ILO/DRAC/기타. 운영 체제에 표시 되지 않고 서버 하드웨어를 모니터링 하 고 관리 하는 데 사용 되는 연결은 멀티홈 서버를 구성 하지 않으므로 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4379-131">ILO/DRAC/etc. connections not exposed to the Operating System and used to monitor and manage the server hardware do not constitute a multi-homed server and thus are supported.</span></span>


</div></li>
</ul></td>
</tr>
</tbody>
</table>


### <a name="recommended-hardware-for-edge-servers-standalone-mediation-servers-and-directors"></a><span data-ttu-id="c4379-132">에지 서버, 독립 실행형 중재 서버 및 디렉터를 위한 권장 하드웨어</span><span class="sxs-lookup"><span data-stu-id="c4379-132">Recommended Hardware for Edge Servers, Standalone Mediation Servers, and Directors</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c4379-133">하드웨어 구성 요소</span><span class="sxs-lookup"><span data-stu-id="c4379-133">Hardware component</span></span></th>
<th><span data-ttu-id="c4379-134">권장</span><span class="sxs-lookup"><span data-stu-id="c4379-134">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c4379-135">CPU</span><span class="sxs-lookup"><span data-stu-id="c4379-135">CPU</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c4379-136">64 비트 이중 프로세서, 쿼드 코어, 2.0 ghz 이상</span><span class="sxs-lookup"><span data-stu-id="c4379-136">64-bit dual processor, quad-core, 2.0 gigahertz (GHz) or higher.</span></span></p>
<p><span data-ttu-id="c4379-137">- 사용자나</span><span class="sxs-lookup"><span data-stu-id="c4379-137">- OR -</span></span></p></li>
<li><p><span data-ttu-id="c4379-138">64 비트 4 방향 프로세서, 듀얼 코어, 2.0 GHz 이상</span><span class="sxs-lookup"><span data-stu-id="c4379-138">64-bit 4-way processor, dual-core, 2.0 GHz or higher.</span></span></p></li>
</ul>
<p><span data-ttu-id="c4379-139">Lync Server 서버 역할에는 Intel Itanium 프로세서가 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c4379-139">Intel Itanium processors are not supported for Lync Server server roles.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4379-140">메모리</span><span class="sxs-lookup"><span data-stu-id="c4379-140">Memory</span></span></p></td>
<td><p><span data-ttu-id="c4379-141">162gb</span><span class="sxs-lookup"><span data-stu-id="c4379-141">16 gigabytes (GB).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4379-142">공간이</span><span class="sxs-lookup"><span data-stu-id="c4379-142">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c4379-143">72 GB 이상의 사용 가능한 디스크 공간이 있는 1만 RPM 하드 디스크 드라이브 4 개 이상</span><span class="sxs-lookup"><span data-stu-id="c4379-143">4 or more 10,000 RPM hard disk drives with at least 72 GB free disk space.</span></span></p>
<p><span data-ttu-id="c4379-144">디스크는 2 배의 RAID 1 구성에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4379-144">The disks should be in a 2x RAID 1 configuration.</span></span></p>
<p><span data-ttu-id="c4379-145">- 사용자나</span><span class="sxs-lookup"><span data-stu-id="c4379-145">- OR -</span></span></p></li>
<li><p><span data-ttu-id="c4379-146">4개의 10,000 RPM 기계식 디스크 드라이브와 유사한 성능을 제공하는 SDD(반도체 드라이브)</span><span class="sxs-lookup"><span data-stu-id="c4379-146">Solid state drives (SSDs) which provide performance similar to 4 10,000-RPM mechanical disk drives.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4379-147">네트워크</span><span class="sxs-lookup"><span data-stu-id="c4379-147">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c4379-148">1 개의 이중 포트 네트워크 어댑터, 1Gbps 이상 (2 개 권장, 단일 MAC 주소와 단일 IP 주소를 사용 하는 팀이 필요 함)</span><span class="sxs-lookup"><span data-stu-id="c4379-148">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address).</span></span> <span data-ttu-id="c4379-149">2 네트워크 인터페이스는에 지 서버에 필요 하며 독립 실행형 중재 서버에서 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4379-149">2 network interfaces are required on Edge Servers, and are supported on standalone Mediation Servers.</span></span></p></li>
</ul>
<div>

> [!NOTE]  
> <span data-ttu-id="c4379-150">이중 또는 멀티홈 구성은 디렉터에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c4379-150">Dual or multi-homed configurations are not supported for Directors.</span></span><BR><span data-ttu-id="c4379-151">ILO/DRAC/기타. 운영 체제에 표시 되지 않고 서버 하드웨어를 모니터링 하 고 관리 하는 데 사용 되는 연결은 멀티홈 서버를 구성 하지 않으므로 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4379-151">ILO/DRAC/etc. connections not exposed to the Operating System and used to monitor and manage the server hardware do not constitute a multi-homed server and thus are supported.</span></span>


</div>
<p><span data-ttu-id="c4379-152">에 지 서버에는 이중 포트 네트워크 어댑터, 1Gbps 이상 (두 개의 연결 된 네트워크 어댑터, 총 4 개, 단일 MAC 주소와 단일 IP 주소를 사용 하 여 각 쌍을 그룹화 하 고 총 두 쌍에 대해 연결 된 두 개의 네트워크 어댑터가 필요 합니다.)</span><span class="sxs-lookup"><span data-stu-id="c4379-152">Edge Servers will require two network interfaces that are dual-port network adapters, 1 Gbps or higher (or two paired network adapters, for a total of four, each pair being teamed with a single MAC address and a single IP address, for a total of two pairs).</span></span></p>
<p><span data-ttu-id="c4379-153">독립 실행형 중재 서버에서 특정 PSTN IP 주소 구성을 허용 하기 위해 추가 Nic (네트워크 인터페이스 카드)를 설치 하는 것이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4379-153">Installation of additional network interface cards (NICs) to allow the configuration of a specific PSTN IP address is supported on standalone Mediation Servers.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

