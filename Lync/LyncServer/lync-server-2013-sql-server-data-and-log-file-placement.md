---
title: 'Lync Server 2013: SQL Server 데이터 및 로그 파일 배치'
description: 'Lync Server 2013: SQL Server 데이터 및 로그 파일 배치'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SQL Server data and log file placement
ms:assetid: 67aa525b-8aa3-474f-827e-8e1d4697f30f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398479(v=OCS.15)
ms:contentKeyID: 48184395
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a127254fec41a734136df9b63fc6cc8929745df7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558284"
---
# <a name="sql-server-data-and-log-file-placement-for-lync-server-2013"></a><span data-ttu-id="9e04d-103">Lync Server 2013에 대 한 SQL Server 데이터 및 로그 파일 배치</span><span class="sxs-lookup"><span data-stu-id="9e04d-103">SQL Server data and log file placement for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9e04d-104">_**마지막으로 수정 된 항목:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="9e04d-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="9e04d-105">Lync Server 2013 프런트 엔드 풀에 대 한 Microsoft SQL Server 2012 또는 Microsoft SQL Server 2008 R2 s p 1을 계획 하 고 배포 하는 동안 성능에 맞게 데이터 및 로그 파일을 실제 하드 디스크에 배치 하는 것이 중요 한 고려 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="9e04d-105">During the planning and deployment of Microsoft SQL Server 2012 or Microsoft SQL Server 2008 R2 SP1 for your Lync Server 2013 Front End pool, an important consideration is the placement of data and log files onto physical hard disks for performance.</span></span> <span data-ttu-id="9e04d-106">권장 되는 디스크 구성은 6 스핀 들을 사용 하 여 1 + 0 RAID 집합을 구현 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9e04d-106">The recommended disk configuration is to implement a 1+0 RAID set using 6 spindles.</span></span> <span data-ttu-id="9e04d-107">Lync Server 배포 마법사를 사용 하 여 프런트 엔드 풀 및 연결 된 서버 역할 및 서비스 (즉, 보관 및 모니터링 서버, Lync Server Response 그룹 서비스, Lync Server 통화 대기 서비스)에 사용 되는 모든 데이터베이스 및 로그 파일을 RAID 드라이브 집합에 저장 하면 적절 한 성능으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e04d-107">Placing all database and log files that are used by the Front End pool and associated server roles and services (that is, Archiving and Monitoring Server, Lync Server Response Group service, Lync Server Call Park service) onto the RAID drive set using the Lync Server Deployment Wizard will result in a configuration that has been tested for good performance.</span></span> <span data-ttu-id="9e04d-108">다음 표에는 데이터베이스 파일과 각 파일의 역할이 자세히 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e04d-108">The database files and what they are responsible for is detailed in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9e04d-109">정책 및 SQL Server 구성에 보다 전문화 된 설치가 필요한 경우 Lync Server 관리 셸을 사용 하 여 데이터베이스 및 로그 파일을 미리 정의 된 위치에 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e04d-109">If your policies and SQL Server configurations require a more specialized installation, the database and log files can be installed to any pre-defined location using the Lync Server Management Shell.</span></span> <span data-ttu-id="9e04d-110">자세한 내용은 <A href="lync-server-2013-database-installation-using-lync-server-management-shell.md">Lync server 2013에서 Lync Server 관리 셸을 사용 하 여 데이터베이스 설치를</A> 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9e04d-110">See <A href="lync-server-2013-database-installation-using-lync-server-management-shell.md">Database installation using Lync Server Management Shell in Lync Server 2013</A> for more details.</span></span>



</div>

### <a name="data-and-log-files-for-central-management-store"></a><span data-ttu-id="9e04d-111">중앙 관리 저장소의 데이터 및 로그 파일</span><span class="sxs-lookup"><span data-stu-id="9e04d-111">Data and Log Files for Central Management Store</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9e04d-112">중앙 관리 저장소 데이터베이스 파일</span><span class="sxs-lookup"><span data-stu-id="9e04d-112">Central Management store database files</span></span></th>
<th><span data-ttu-id="9e04d-113">데이터 파일 또는 로그 용도</span><span class="sxs-lookup"><span data-stu-id="9e04d-113">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9e04d-114">Xds</span><span class="sxs-lookup"><span data-stu-id="9e04d-114">Xds.ldf</span></span></p></td>
<td><p><span data-ttu-id="9e04d-115">중앙 관리 저장소에 대 한 트랜잭션 로그 파일</span><span class="sxs-lookup"><span data-stu-id="9e04d-115">Transaction log file for the Central Management store</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e04d-116">Xds .mdf</span><span class="sxs-lookup"><span data-stu-id="9e04d-116">Xds.mdf</span></span></p></td>
<td><p><span data-ttu-id="9e04d-117">토폴로지 작성기에서 정의 하 고 게시 한 대로 현재 Lync Server 2013 토폴로지의 구성을 유지 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e04d-117">Maintains the configuration of the current Lync Server 2013 topology, as defined and published by Topology Builder</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e04d-118">Lis</span><span class="sxs-lookup"><span data-stu-id="9e04d-118">Lis.mdf</span></span></p></td>
<td><p><span data-ttu-id="9e04d-119">위치 정보 서비스 데이터 파일</span><span class="sxs-lookup"><span data-stu-id="9e04d-119">Location Information service data file</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e04d-120">Lis</span><span class="sxs-lookup"><span data-stu-id="9e04d-120">Lis.ldf</span></span></p></td>
<td><p><span data-ttu-id="9e04d-121">위치 정보 서비스 데이터 파일에 대 한 트랜잭션 로그</span><span class="sxs-lookup"><span data-stu-id="9e04d-121">Transaction log for the Location Information service data file</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-user-conferencing-and-address-book"></a><span data-ttu-id="9e04d-122">사용자, 회의 및 주소록에 대한 데이터 및 로그 파일</span><span class="sxs-lookup"><span data-stu-id="9e04d-122">Data and Log files for User, Conferencing, and Address Book</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9e04d-123">핵심 Lync Server 2013 데이터베이스 파일</span><span class="sxs-lookup"><span data-stu-id="9e04d-123">Core Lync Server 2013 database files</span></span></th>
<th><span data-ttu-id="9e04d-124">데이터 파일 또는 로그 용도</span><span class="sxs-lookup"><span data-stu-id="9e04d-124">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9e04d-125">Rtc .mdf</span><span class="sxs-lookup"><span data-stu-id="9e04d-125">Rtc.mdf</span></span></p></td>
<td><p><span data-ttu-id="9e04d-126">영구 사용자 데이터 (예: Acl (액세스 제어 목록), 연락처, 예약 된 회의)</span><span class="sxs-lookup"><span data-stu-id="9e04d-126">Persistent user data (for example, access control lists (ACLs), contacts, scheduled conferences)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e04d-127">Rtc</span><span class="sxs-lookup"><span data-stu-id="9e04d-127">Rtc.ldf</span></span></p></td>
<td><p><span data-ttu-id="9e04d-128">Rtc 데이터에 대 한 트랜잭션 로그</span><span class="sxs-lookup"><span data-stu-id="9e04d-128">Transaction log for Rtc data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e04d-129">Rtcdyn. .mdf</span><span class="sxs-lookup"><span data-stu-id="9e04d-129">Rtcdyn.mdf</span></span></p></td>
<td><p><span data-ttu-id="9e04d-130">임시 사용자 데이터 (현재 상태 데이터)를 유지 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e04d-130">Maintains transient user data (presence runtime data)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e04d-131">Rtcdyn</span><span class="sxs-lookup"><span data-stu-id="9e04d-131">Rtcdyn.ldf</span></span></p></td>
<td><p><span data-ttu-id="9e04d-132">Rtcdyn 데이터에 대 한 트랜잭션 로그</span><span class="sxs-lookup"><span data-stu-id="9e04d-132">Transaction log for Rtcdyn data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e04d-133">Rtcab .mdf</span><span class="sxs-lookup"><span data-stu-id="9e04d-133">Rtcab.mdf</span></span></p></td>
<td><p><span data-ttu-id="9e04d-134">RTC(Real-Time Communications) 주소록 데이터베이스는 주소록 서비스 정보가 저장되는 SQL Server 리포지토리임</span><span class="sxs-lookup"><span data-stu-id="9e04d-134">Real-time communications (RTC) address book database is the SQL Server repository where Address Book service information is stored</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e04d-135">Rtcab. .ldf</span><span class="sxs-lookup"><span data-stu-id="9e04d-135">Rtcab.ldf</span></span></p></td>
<td><p><span data-ttu-id="9e04d-136">주소록 서비스에 대한 트랜잭션 로그</span><span class="sxs-lookup"><span data-stu-id="9e04d-136">Transaction log for Address Book Service</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e04d-137">Rtclocal .mdb</span><span class="sxs-lookup"><span data-stu-id="9e04d-137">Rtclocal.mdb</span></span></p></td>
<td><p><span data-ttu-id="9e04d-138">회의 디렉터리를 호스팅합니다.</span><span class="sxs-lookup"><span data-stu-id="9e04d-138">Hosts the conference directory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e04d-139">Rtcxds. .mdf</span><span class="sxs-lookup"><span data-stu-id="9e04d-139">Rtcxds.mdf</span></span></p></td>
<td><p><span data-ttu-id="9e04d-140">사용자 데이터에 대 한 백업을 유지 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e04d-140">Maintains the backup for user data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e04d-141">Rtcxds</span><span class="sxs-lookup"><span data-stu-id="9e04d-141">Rtcxds.ldf</span></span></p></td>
<td><p><span data-ttu-id="9e04d-142">Rtcxds 데이터에 대 한 트랜잭션 로그</span><span class="sxs-lookup"><span data-stu-id="9e04d-142">Transaction log for Rtcxds data</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-call-park-and-response-group"></a><span data-ttu-id="9e04d-143">통화 대기 및 응답 그룹에 대한 데이터 및 로그 파일</span><span class="sxs-lookup"><span data-stu-id="9e04d-143">Data and Log Files for Call Park and Response Group</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9e04d-144">응용 프로그램 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="9e04d-144">Application database</span></span></th>
<th><span data-ttu-id="9e04d-145">데이터 파일 또는 로그 용도</span><span class="sxs-lookup"><span data-stu-id="9e04d-145">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9e04d-146">Cpsdyn.mdf. .mdf</span><span class="sxs-lookup"><span data-stu-id="9e04d-146">Cpsdyn.mdf</span></span></p></td>
<td><p><span data-ttu-id="9e04d-147">통화 대기 응용 프로그램에 대 한 동적 정보 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="9e04d-147">Dynamic information database for the Call Park application</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e04d-148">Cpsdyn.mdf</span><span class="sxs-lookup"><span data-stu-id="9e04d-148">Cpsdyn.ldf</span></span></p></td>
<td><p><span data-ttu-id="9e04d-149">통화 대기 응용 프로그램 데이터 파일에 대 한 트랜잭션 로그</span><span class="sxs-lookup"><span data-stu-id="9e04d-149">Transaction log for Call Park application data file</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e04d-150">Rgsconfig. .mdf</span><span class="sxs-lookup"><span data-stu-id="9e04d-150">Rgsconfig.mdf</span></span></p></td>
<td><p><span data-ttu-id="9e04d-151">서비스 구성에 대한 Lync Server 응답 그룹 서비스 데이터 파일</span><span class="sxs-lookup"><span data-stu-id="9e04d-151">Lync Server Response Group service data file for the configuration of the services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e04d-152">Rgsconfig</span><span class="sxs-lookup"><span data-stu-id="9e04d-152">Rgsconfig.ldf</span></span></p></td>
<td><p><span data-ttu-id="9e04d-153">응답 그룹 응용 프로그램 구성에 대 한 트랜잭션 로그 파일</span><span class="sxs-lookup"><span data-stu-id="9e04d-153">Transaction log file for the Response Group application configuration</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e04d-154">Rgsdyn.mdf. .mdf</span><span class="sxs-lookup"><span data-stu-id="9e04d-154">Rgsdyn.mdf</span></span></p></td>
<td><p><span data-ttu-id="9e04d-155">런타임 작업에 대한 응답 그룹 서비스 데이터 파일</span><span class="sxs-lookup"><span data-stu-id="9e04d-155">Response Group service data file for runtime operations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e04d-156">Rgsdyn.mdf</span><span class="sxs-lookup"><span data-stu-id="9e04d-156">Rgsdyn.ldf</span></span></p></td>
<td><p><span data-ttu-id="9e04d-157">응답 그룹 서비스 런타임 데이터 파일에 대한 트랜잭션 로그</span><span class="sxs-lookup"><span data-stu-id="9e04d-157">Transaction log for the Response Group service runtime data file</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-archiving-and-monitoring-server"></a><span data-ttu-id="9e04d-158">보관 및 모니터링 서버에 대한 데이터 및 로그 파일</span><span class="sxs-lookup"><span data-stu-id="9e04d-158">Data and Log Files for Archiving and Monitoring Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9e04d-159">보관 및 모니터링 데이터베이스 파일</span><span class="sxs-lookup"><span data-stu-id="9e04d-159">Archiving and Monitoring database files</span></span></th>
<th><span data-ttu-id="9e04d-160">데이터 파일 또는 로그 용도</span><span class="sxs-lookup"><span data-stu-id="9e04d-160">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9e04d-161">LcsCdr. .mdf</span><span class="sxs-lookup"><span data-stu-id="9e04d-161">LcsCdr.mdf</span></span></p></td>
<td><p><span data-ttu-id="9e04d-162">모니터링 서버의 CDR (통화 정보 기록) 프로세스에 대 한 데이터 저장소</span><span class="sxs-lookup"><span data-stu-id="9e04d-162">Data store for the call detail recording (CDR) process of the Monitoring Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e04d-163">LcsCdr</span><span class="sxs-lookup"><span data-stu-id="9e04d-163">LcsCdr.ldf</span></span></p></td>
<td><p><span data-ttu-id="9e04d-164">CDR(통화 정보 기록) 데이터에 대한 트랜잭션 로그</span><span class="sxs-lookup"><span data-stu-id="9e04d-164">Transaction log for call detail recording (CDR) data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e04d-165">QoEMetrics. .mdf</span><span class="sxs-lookup"><span data-stu-id="9e04d-165">QoEMetrics.mdf</span></span></p></td>
<td><p><span data-ttu-id="9e04d-166">모니터링 서버에서 저장 된 품질 데이터 파일</span><span class="sxs-lookup"><span data-stu-id="9e04d-166">Quality of Experience data file stored from the Monitoring Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e04d-167">QoEMetrics</span><span class="sxs-lookup"><span data-stu-id="9e04d-167">QoEMetrics.ldf</span></span></p></td>
<td><p><span data-ttu-id="9e04d-168">모니터링 데이터에 대한 트랜잭션 로그</span><span class="sxs-lookup"><span data-stu-id="9e04d-168">Transaction log for Monitoring data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e04d-169">Lcslog</span><span class="sxs-lookup"><span data-stu-id="9e04d-169">Lcslog.mdf</span></span></p></td>
<td><p><span data-ttu-id="9e04d-170">인스턴트 메시징 및 회의 데이터를 보관 서버에 보존 하기 위한 데이터 파일</span><span class="sxs-lookup"><span data-stu-id="9e04d-170">Data file for the retention of instant messaging and conferencing data on an Archiving Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e04d-171">Lcslog. .ldf</span><span class="sxs-lookup"><span data-stu-id="9e04d-171">Lcslog.ldf</span></span></p></td>
<td><p><span data-ttu-id="9e04d-172">보관 데이터에 대한 트랜잭션 로그</span><span class="sxs-lookup"><span data-stu-id="9e04d-172">Transaction log for Archiving data</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="9e04d-p103">이 항목에서는 디스크 및 RAID 세트를 기준으로 합니다. SQL Server 리소스 구성에서 디스크란 단일 하드웨어 장치를 의미합니다. 각각 로그 파일과 데이터 파일을 유지하는 두 개의 파티션이 있는 하드 디스크 드라이브는 각각 로그 또는 데이터 파일에 전용되는 두 개의 디스크와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="9e04d-p103">In this topic, references are made to disk and to RAID set. Note that in the configuration of SQL Server resources, referring to a disk means a single hardware device. A hard disk drive with two partitions, one holding log files and the other partition holding data files, is not the same as two disks, each dedicated to either log or data files.</span></span>

<span data-ttu-id="9e04d-176">RAID 세트의 경우 여러 공급업체의 다양한 RAID 기술이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e04d-176">In reference to RAID sets, there are a number of different RAID technologies from various vendors.</span></span> <span data-ttu-id="9e04d-177">또한 SAN(저장 영역 네트워크)의 증가로 인해 단일 시스템에 전용되는 RAID 세트가 드문 것이 현실입니다.</span><span class="sxs-lookup"><span data-stu-id="9e04d-177">And, with the proliferation of storage area networks (SAN), RAID sets dedicated to a single system are rarer.</span></span> <span data-ttu-id="9e04d-178">Lync Server 2013을 사용 하 여 SQL Server 성능을 구성할 때 RAID 또는 SAN 공급 업체에 문의 하 여 디스크 레이아웃에 가장 적합 한 구성을 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e04d-178">You should consult with your RAID or SAN vendor to determine what the best configuration is for your disk layout when configuring for SQL Server performance with Lync Server 2013.</span></span>

<span data-ttu-id="9e04d-179">또한 모든 디스크 드라이브가 동일하게 만들어지는 것이 아니며 그 중 성능이 나은 것이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e04d-179">Note also that not all disk drives are created equally; some perform better than others.</span></span> <span data-ttu-id="9e04d-180">같은 제조업체의 드라이브도 회전 속도, 하드웨어 캐시 크기 및 기타 요인으로 인해 성능이 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e04d-180">Even drives from the same manufacturer can vary in performance because of rotational speed, hardware cache size, and other factors.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

