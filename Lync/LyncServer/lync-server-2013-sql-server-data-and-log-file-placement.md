---
title: 'Lync Server 2013: SQL Server 데이터 및 로그 파일 배치'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: SQL Server data and log file placement
ms:assetid: 67aa525b-8aa3-474f-827e-8e1d4697f30f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398479(v=OCS.15)
ms:contentKeyID: 48184395
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a528ba7a348ebb5c8f865a795f8b1f1c1bc30cb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979736"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sql-server-data-and-log-file-placement-for-lync-server-2013"></a><span data-ttu-id="f7603-102">Lync Server 2013에 대한 SQL Server 데이터 및 로그 파일 배치</span><span class="sxs-lookup"><span data-stu-id="f7603-102">SQL Server data and log file placement for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f7603-103">_**마지막으로 수정한 주제:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="f7603-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="f7603-104">Lync Server 2013 프런트 엔드 풀에 대 한 Microsoft SQL Server 2012 또는 Microsoft SQL Server 2008 R2 SP1을 계획 하 고 배포 하는 동안 성능에 대 한 데이터 및 로그 파일을 실제 하드 디스크에 배치 하는 것이 중요 한 고려 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="f7603-104">During the planning and deployment of Microsoft SQL Server 2012 or Microsoft SQL Server 2008 R2 SP1 for your Lync Server 2013 Front End pool, an important consideration is the placement of data and log files onto physical hard disks for performance.</span></span> <span data-ttu-id="f7603-105">권장 되는 디스크 구성은 6 개 스핀 들을 사용 하 여 1 + 0 RAID 집합을 구현 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f7603-105">The recommended disk configuration is to implement a 1+0 RAID set using 6 spindles.</span></span> <span data-ttu-id="f7603-106">Lync Server를 사용 하 여 RAID 드라이브 집합에 대 한 프런트 엔드 풀 및 연결 된 서버 역할 및 서비스 (즉, 보관 및 모니터링 서버, Lync Server 응답 그룹 서비스, Lync Server 통화 공원 서비스)에 사용 되는 모든 데이터베이스 및 로그 파일을 배치할 수 있습니다. 배포 마법사는 좋은 성능을 위해 테스트 된 구성을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7603-106">Placing all database and log files that are used by the Front End pool and associated server roles and services (that is, Archiving and Monitoring Server, Lync Server Response Group service, Lync Server Call Park service) onto the RAID drive set using the Lync Server Deployment Wizard will result in a configuration that has been tested for good performance.</span></span> <span data-ttu-id="f7603-107">데이터베이스 파일과 이러한 파일의 역할은 다음 표에 자세히 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7603-107">The database files and what they are responsible for is detailed in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f7603-108">정책 및 SQL Server 구성에 더 특별 한 설치가 필요한 경우 Lync Server Management Shell을 사용 하 여 데이터베이스 및 로그 파일을 미리 정의 된 위치에 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7603-108">If your policies and SQL Server configurations require a more specialized installation, the database and log files can be installed to any pre-defined location using the Lync Server Management Shell.</span></span> <span data-ttu-id="f7603-109">자세한 내용은 <A href="lync-server-2013-database-installation-using-lync-server-management-shell.md">Lync server 2013에서 Lync Server Management Shell을 사용 하 여 데이터베이스 설치</A> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f7603-109">See <A href="lync-server-2013-database-installation-using-lync-server-management-shell.md">Database installation using Lync Server Management Shell in Lync Server 2013</A> for more details.</span></span>



</div>

### <a name="data-and-log-files-for-central-management-store"></a><span data-ttu-id="f7603-110">중앙 관리 저장소에 대 한 데이터 및 로그 파일</span><span class="sxs-lookup"><span data-stu-id="f7603-110">Data and Log Files for Central Management Store</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f7603-111">중앙 관리 저장소 데이터베이스 파일</span><span class="sxs-lookup"><span data-stu-id="f7603-111">Central Management store database files</span></span></th>
<th><span data-ttu-id="f7603-112">데이터 파일 또는 로그 용도</span><span class="sxs-lookup"><span data-stu-id="f7603-112">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f7603-113">Xds</span><span class="sxs-lookup"><span data-stu-id="f7603-113">Xds.ldf</span></span></p></td>
<td><p><span data-ttu-id="f7603-114">중앙 관리 저장소의 트랜잭션 로그 파일</span><span class="sxs-lookup"><span data-stu-id="f7603-114">Transaction log file for the Central Management store</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7603-115">Xds .mdf</span><span class="sxs-lookup"><span data-stu-id="f7603-115">Xds.mdf</span></span></p></td>
<td><p><span data-ttu-id="f7603-116">토폴로지 작성기에서 정의 하 고 게시 한 현재 Lync Server 2013 토폴로지의 구성을 유지 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7603-116">Maintains the configuration of the current Lync Server 2013 topology, as defined and published by Topology Builder</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f7603-117">Lis. .mdf</span><span class="sxs-lookup"><span data-stu-id="f7603-117">Lis.mdf</span></span></p></td>
<td><p><span data-ttu-id="f7603-118">위치 정보 서비스 데이터 파일</span><span class="sxs-lookup"><span data-stu-id="f7603-118">Location Information service data file</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7603-119">Lis</span><span class="sxs-lookup"><span data-stu-id="f7603-119">Lis.ldf</span></span></p></td>
<td><p><span data-ttu-id="f7603-120">위치 정보 서비스 데이터 파일에 대 한 트랜잭션 로그</span><span class="sxs-lookup"><span data-stu-id="f7603-120">Transaction log for the Location Information service data file</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-user-conferencing-and-address-book"></a><span data-ttu-id="f7603-121">사용자, 회의 및 주소록에 대 한 데이터 및 로그 파일</span><span class="sxs-lookup"><span data-stu-id="f7603-121">Data and Log files for User, Conferencing, and Address Book</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f7603-122">핵심 Lync Server 2013 데이터베이스 파일</span><span class="sxs-lookup"><span data-stu-id="f7603-122">Core Lync Server 2013 database files</span></span></th>
<th><span data-ttu-id="f7603-123">데이터 파일 또는 로그 용도</span><span class="sxs-lookup"><span data-stu-id="f7603-123">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f7603-124">Rtc</span><span class="sxs-lookup"><span data-stu-id="f7603-124">Rtc.mdf</span></span></p></td>
<td><p><span data-ttu-id="f7603-125">영구 사용자 데이터 (예: Acl (액세스 제어 목록), 연락처, 예약 된 회의)</span><span class="sxs-lookup"><span data-stu-id="f7603-125">Persistent user data (for example, access control lists (ACLs), contacts, scheduled conferences)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7603-126">Rtc</span><span class="sxs-lookup"><span data-stu-id="f7603-126">Rtc.ldf</span></span></p></td>
<td><p><span data-ttu-id="f7603-127">Rtc 데이터에 대 한 트랜잭션 로그</span><span class="sxs-lookup"><span data-stu-id="f7603-127">Transaction log for Rtc data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f7603-128">Rtcdyn</span><span class="sxs-lookup"><span data-stu-id="f7603-128">Rtcdyn.mdf</span></span></p></td>
<td><p><span data-ttu-id="f7603-129">임시 사용자 데이터 (현재 상태 런타임 데이터)를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7603-129">Maintains transient user data (presence runtime data)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7603-130">Rtcdyn</span><span class="sxs-lookup"><span data-stu-id="f7603-130">Rtcdyn.ldf</span></span></p></td>
<td><p><span data-ttu-id="f7603-131">Rtcdyn 데이터에 대 한 트랜잭션 로그</span><span class="sxs-lookup"><span data-stu-id="f7603-131">Transaction log for Rtcdyn data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f7603-132">Rtcab .mdf</span><span class="sxs-lookup"><span data-stu-id="f7603-132">Rtcab.mdf</span></span></p></td>
<td><p><span data-ttu-id="f7603-133">RTC (실시간 통신) 주소록 데이터베이스는 주소록 서비스 정보가 저장 되는 SQL Server 리포지토리입니다.</span><span class="sxs-lookup"><span data-stu-id="f7603-133">Real-time communications (RTC) address book database is the SQL Server repository where Address Book service information is stored</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7603-134">Rtcab. i a .ldf</span><span class="sxs-lookup"><span data-stu-id="f7603-134">Rtcab.ldf</span></span></p></td>
<td><p><span data-ttu-id="f7603-135">주소록 서비스에 대 한 트랜잭션 로그</span><span class="sxs-lookup"><span data-stu-id="f7603-135">Transaction log for Address Book Service</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f7603-136">Rtclocal</span><span class="sxs-lookup"><span data-stu-id="f7603-136">Rtclocal.mdb</span></span></p></td>
<td><p><span data-ttu-id="f7603-137">회의 디렉터리를 호스팅합니다.</span><span class="sxs-lookup"><span data-stu-id="f7603-137">Hosts the conference directory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7603-138">Rtcxds</span><span class="sxs-lookup"><span data-stu-id="f7603-138">Rtcxds.mdf</span></span></p></td>
<td><p><span data-ttu-id="f7603-139">사용자 데이터에 대 한 백업 유지 관리</span><span class="sxs-lookup"><span data-stu-id="f7603-139">Maintains the backup for user data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f7603-140">Rtcxds</span><span class="sxs-lookup"><span data-stu-id="f7603-140">Rtcxds.ldf</span></span></p></td>
<td><p><span data-ttu-id="f7603-141">Rtcxds 데이터에 대 한 트랜잭션 로그</span><span class="sxs-lookup"><span data-stu-id="f7603-141">Transaction log for Rtcxds data</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-call-park-and-response-group"></a><span data-ttu-id="f7603-142">통화 공원 및 응답 그룹에 대 한 데이터 및 로그 파일</span><span class="sxs-lookup"><span data-stu-id="f7603-142">Data and Log Files for Call Park and Response Group</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f7603-143">응용 프로그램 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="f7603-143">Application database</span></span></th>
<th><span data-ttu-id="f7603-144">데이터 파일 또는 로그 용도</span><span class="sxs-lookup"><span data-stu-id="f7603-144">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f7603-145">Cpsdyn</span><span class="sxs-lookup"><span data-stu-id="f7603-145">Cpsdyn.mdf</span></span></p></td>
<td><p><span data-ttu-id="f7603-146">통화 공원 응용 프로그램에 대 한 동적 정보 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="f7603-146">Dynamic information database for the Call Park application</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7603-147">Cpsdyn</span><span class="sxs-lookup"><span data-stu-id="f7603-147">Cpsdyn.ldf</span></span></p></td>
<td><p><span data-ttu-id="f7603-148">통화 공원 응용 프로그램 데이터 파일에 대 한 트랜잭션 로그</span><span class="sxs-lookup"><span data-stu-id="f7603-148">Transaction log for Call Park application data file</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f7603-149">Rgsconfig</span><span class="sxs-lookup"><span data-stu-id="f7603-149">Rgsconfig.mdf</span></span></p></td>
<td><p><span data-ttu-id="f7603-150">서비스 구성에 대 한 Lync Server 응답 그룹 서비스 데이터 파일</span><span class="sxs-lookup"><span data-stu-id="f7603-150">Lync Server Response Group service data file for the configuration of the services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7603-151">Rgsconfig</span><span class="sxs-lookup"><span data-stu-id="f7603-151">Rgsconfig.ldf</span></span></p></td>
<td><p><span data-ttu-id="f7603-152">응답 그룹 응용 프로그램 구성에 대 한 트랜잭션 로그 파일</span><span class="sxs-lookup"><span data-stu-id="f7603-152">Transaction log file for the Response Group application configuration</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f7603-153">Rgsdyn</span><span class="sxs-lookup"><span data-stu-id="f7603-153">Rgsdyn.mdf</span></span></p></td>
<td><p><span data-ttu-id="f7603-154">런타임 작업에 대 한 응답 그룹 서비스 데이터 파일</span><span class="sxs-lookup"><span data-stu-id="f7603-154">Response Group service data file for runtime operations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7603-155">Rgsdyn</span><span class="sxs-lookup"><span data-stu-id="f7603-155">Rgsdyn.ldf</span></span></p></td>
<td><p><span data-ttu-id="f7603-156">응답 그룹 서비스 런타임 데이터 파일에 대 한 트랜잭션 로그</span><span class="sxs-lookup"><span data-stu-id="f7603-156">Transaction log for the Response Group service runtime data file</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-archiving-and-monitoring-server"></a><span data-ttu-id="f7603-157">보관 및 모니터링 서버에 대 한 데이터 및 로그 파일</span><span class="sxs-lookup"><span data-stu-id="f7603-157">Data and Log Files for Archiving and Monitoring Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f7603-158">데이터베이스 파일 보관 및 모니터링</span><span class="sxs-lookup"><span data-stu-id="f7603-158">Archiving and Monitoring database files</span></span></th>
<th><span data-ttu-id="f7603-159">데이터 파일 또는 로그 용도</span><span class="sxs-lookup"><span data-stu-id="f7603-159">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f7603-160">LcsCdr</span><span class="sxs-lookup"><span data-stu-id="f7603-160">LcsCdr.mdf</span></span></p></td>
<td><p><span data-ttu-id="f7603-161">모니터링 서버의 CDR (통화 정보 기록) 프로세스에 대 한 데이터 저장소</span><span class="sxs-lookup"><span data-stu-id="f7603-161">Data store for the call detail recording (CDR) process of the Monitoring Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7603-162">LcsCdr</span><span class="sxs-lookup"><span data-stu-id="f7603-162">LcsCdr.ldf</span></span></p></td>
<td><p><span data-ttu-id="f7603-163">CDR (통화 정보 기록) 데이터에 대 한 트랜잭션 로그</span><span class="sxs-lookup"><span data-stu-id="f7603-163">Transaction log for call detail recording (CDR) data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f7603-164">QoEMetrics</span><span class="sxs-lookup"><span data-stu-id="f7603-164">QoEMetrics.mdf</span></span></p></td>
<td><p><span data-ttu-id="f7603-165">모니터링 서버에서 저장 된 환경 데이터 파일의 품질</span><span class="sxs-lookup"><span data-stu-id="f7603-165">Quality of Experience data file stored from the Monitoring Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7603-166">QoEMetrics</span><span class="sxs-lookup"><span data-stu-id="f7603-166">QoEMetrics.ldf</span></span></p></td>
<td><p><span data-ttu-id="f7603-167">데이터 모니터링에 대 한 트랜잭션 로그</span><span class="sxs-lookup"><span data-stu-id="f7603-167">Transaction log for Monitoring data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f7603-168">Lcslog .mdf</span><span class="sxs-lookup"><span data-stu-id="f7603-168">Lcslog.mdf</span></span></p></td>
<td><p><span data-ttu-id="f7603-169">보관 서버에서 인스턴트 메시지 및 회의 데이터 보존을 위한 데이터 파일</span><span class="sxs-lookup"><span data-stu-id="f7603-169">Data file for the retention of instant messaging and conferencing data on an Archiving Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7603-170">Lcslog. .ldf</span><span class="sxs-lookup"><span data-stu-id="f7603-170">Lcslog.ldf</span></span></p></td>
<td><p><span data-ttu-id="f7603-171">데이터 보관을 위한 트랜잭션 로그</span><span class="sxs-lookup"><span data-stu-id="f7603-171">Transaction log for Archiving data</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f7603-172">이 항목에서는 디스크와 RAID 집합에 대 한 참조를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7603-172">In this topic, references are made to disk and to RAID set.</span></span> <span data-ttu-id="f7603-173">SQL Server 리소스의 구성에서 디스크를 참조 하는 것은 단일 하드웨어 장치를 의미 한다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="f7603-173">Note that in the configuration of SQL Server resources, referring to a disk means a single hardware device.</span></span> <span data-ttu-id="f7603-174">두 개의 파티션, 그리고 데이터 파일을 보유 하 고 있는 다른 파티션이 포함 된 하드 디스크 드라이브는 두 개의 디스크와 동일 하지 않으며, 각각 로그 또는 데이터 파일에 대 한 전용 복사본입니다.</span><span class="sxs-lookup"><span data-stu-id="f7603-174">A hard disk drive with two partitions, one holding log files and the other partition holding data files, is not the same as two disks, each dedicated to either log or data files.</span></span>

<span data-ttu-id="f7603-175">RAID 집합에 대 한 참조에는 다양 한 공급 업체의 여러 가지 RAID 기술이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7603-175">In reference to RAID sets, there are a number of different RAID technologies from various vendors.</span></span> <span data-ttu-id="f7603-176">그리고 SAN (storage area networks)의 확산으로 단일 시스템 전용 RAID 집합은 rarer입니다.</span><span class="sxs-lookup"><span data-stu-id="f7603-176">And, with the proliferation of storage area networks (SAN), RAID sets dedicated to a single system are rarer.</span></span> <span data-ttu-id="f7603-177">Lync Server 2013를 사용 하 여 SQL Server 성능을 구성할 때 디스크 레이아웃에 적합 한 구성을 확인 하려면 RAID 또는 SAN 공급 업체에 문의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7603-177">You should consult with your RAID or SAN vendor to determine what the best configuration is for your disk layout when configuring for SQL Server performance with Lync Server 2013.</span></span>

<span data-ttu-id="f7603-178">또한 모든 디스크 드라이브가 동등 하 게 만들어지지 않은 것을 참고 하십시오. 일부는 다른 방법 보다 성능이 더 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f7603-178">Note also that not all disk drives are created equally; some perform better than others.</span></span> <span data-ttu-id="f7603-179">동일한 제조업체의 드라이브 조차도 회전 속도, 하드웨어 캐시 크기 및 기타 요인 때문에 성능이 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7603-179">Even drives from the same manufacturer can vary in performance because of rotational speed, hardware cache size, and other factors.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

