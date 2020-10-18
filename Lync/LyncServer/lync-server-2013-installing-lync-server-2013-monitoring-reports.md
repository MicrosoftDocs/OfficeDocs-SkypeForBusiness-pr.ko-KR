---
title: 'Lync Server 2013: Lync Server 2013 모니터링 보고서 설치'
description: 'Lync Server 2013: Lync Server 2013 모니터링 보고서를 설치 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing Lync Server 2013 Monitoring Reports
ms:assetid: 6f417569-b100-442c-ad48-fdd794626cf7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204989(v=OCS.15)
ms:contentKeyID: 48184445
ms.date: 02/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12405f786cbaf095e97f526fae2e1c2d3cb45c32
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573934"
---
# <a name="installing-lync-server-2013-monitoring-reports"></a><span data-ttu-id="e7269-103">Lync Server 2013 모니터링 보고서 설치</span><span class="sxs-lookup"><span data-stu-id="e7269-103">Installing Lync Server 2013 Monitoring Reports</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e7269-104">_**마지막으로 수정 된 항목:** 2015-02-27_</span><span class="sxs-lookup"><span data-stu-id="e7269-104">_**Topic Last Modified:** 2015-02-27_</span></span>

<span data-ttu-id="e7269-105">Microsoft Lync Server 2013 모니터링 보고서에서는 조직에서 수행 되는 통신 세션의 품질과 양에 대 한 풍부한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7269-105">Microsoft Lync Server 2013 Monitoring Reports provide you with a wealth of information about the quality and quantity of the communication sessions that take place in your organization.</span></span> <span data-ttu-id="e7269-106">그러나 Lync Server 2013을 설치 하면 모니터링 보고서가 자동으로 설치 되지 않습니다. 대신, 컴퓨터에 Lync Server를 설치한 후에만 모니터링 보고서를 별도로 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7269-106">However, Monitoring Reports are not automatically installed when you install Lync Server 2013; instead, you must install Monitoring Reports separately, and only after Lync Server has been installed on the computer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e7269-107">모니터링 데이터베이스를 설치한 컴퓨터에 모니터링 보고서를 설치 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e7269-107">It is recommended that you install Monitoring Reports on the same computer where the monitoring database is installed.</span></span> <span data-ttu-id="e7269-108">이렇게 하면 보고서 액세스 권한을 할당 하는 프로세스가 간단해 집니다. 모니터링 저장소를 호스트 하는 컴퓨터에 모니터링 보고서를 설치 하는 것은 한 컴퓨터의 데이터베이스가 두 번째 컴퓨터에서 실행 되는 Reporting Services와 상호 작용할 수 있도록 하는 권한을 구성 하지 않아도 된다는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7269-108">This simplifies the process of assigning permissions for accessing the reports: installing Monitoring Reports on the computer that hosts the monitoring store means that you will not have to configure permissions that allow a database on one computer to interact with Reporting Services running on a second computer.</span></span>



</div>

<span data-ttu-id="e7269-109">Lync Server 모니터링 보고서에는 회의, 피어 투 피어 IM 세션, 사용자 등록, 응답 그룹 응용 프로그램 등에 대 한 세부 정보를 제공 하도록 설계 된 30 개 이상의 보고서가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7269-109">Lync Server Monitoring Reports include over 30 reports designed to provide detailed information about conferences, peer-to-peer IM sessions, user registrations, the Response Group application, and much more.</span></span> <span data-ttu-id="e7269-110">2013 버전의 경우 Lync Server 모니터링 보고서에는 다음과 같은 다양 한 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7269-110">For the 2013 version, Lync Server Monitoring Reports include a number of enhancements:</span></span>

  - <span data-ttu-id="e7269-111">**새로운 음성 품질 보고서**</span><span class="sxs-lookup"><span data-stu-id="e7269-111">**New voice quality reports**.</span></span> <span data-ttu-id="e7269-112">이러한 새 보고서에는 여러 통화 유형 간의 품질을 비교 하는 [Lync Server 2013의 미디어 품질 비교 보고서](lync-server-2013-media-quality-comparison-report.md)(예: 유선 통화와 무선 통화 간)가 포함 됩니다. [Lync Server 2013의 회의 참가 시간 보고서](lync-server-2013-conference-join-time-report.md)에서는 사용자가 회의에 참가 하는 데 필요한 시간에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7269-112">These new reports include the [Media Quality Comparison Report in Lync Server 2013](lync-server-2013-media-quality-comparison-report.md), which compares quality between different types of calls (for example, between wired calls and wireless calls); and the [Conference Join Time Report in Lync Server 2013](lync-server-2013-conference-join-time-report.md), which provides information regarding the amount of time requires for users to join a conference.</span></span>

  - <span data-ttu-id="e7269-113">**비디오 및 응용 프로그램 공유 세션의 분석 및 문제 해결을 위한 향상 된 보고서**</span><span class="sxs-lookup"><span data-stu-id="e7269-113">**Improved reports for analyzing and troubleshooting both video and application sharing sessions.**</span></span> <span data-ttu-id="e7269-114">[Lync server 2013의 미디어 품질 요약 보고서](lync-server-2013-media-quality-summary-report.md) 를 통해 비디오 및 응용 프로그램 공유 통화를 분석할 수 있는 반면 [lync Server 2013의 서버 성능 보고서](lync-server-2013-server-performance-report.md) 는 이러한 통화를 생성 하는 서버의 성능에 대해 자세히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7269-114">The [Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md) provides a way to analyze video and application sharing calls, while the [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) details the performance of servers generating these calls.</span></span> <span data-ttu-id="e7269-115">비디오 및 응용 프로그램 공유 메트릭은 이제 [Lync server 2013의 피어 투 피어 세션 정보 보고서](lync-server-2013-peer-to-peer-session-detail-report.md) 와 [lync Server 2013의 전화 회의 정보 보고서](lync-server-2013-conference-detail-report.md)에 의해 보고 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7269-115">Video and application sharing metrics are also now reported by the [Peer-to-Peer Session Detail Report in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) and the [Conference Detail Report in Lync Server 2013](lync-server-2013-conference-detail-report.md).</span></span>

  - <span data-ttu-id="e7269-116">**향상 된 보고서 성능**</span><span class="sxs-lookup"><span data-stu-id="e7269-116">**Improved report performance**.</span></span> <span data-ttu-id="e7269-117">여기에는 보다 빠른 응답 및 데이터 검색 시간이 포함 되며 보고서를 보다 빠르고 쉽게 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7269-117">This includes faster response and data retrieval time, as well as faster and easier navigation through the reports.</span></span>

<span data-ttu-id="e7269-118">개별 보고서에 대 한 자세한 내용은 모니터링 보고서 설명서에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7269-118">More information on the individual reports can be found in the Monitoring Reports documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e7269-119">Lync Server 2013에는 또 다른 새 보고서-QoE Call Detail 하위 보고서가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7269-119">There is another new report – QoE Call Detail Subreport – included in Lync Server 2013.</span></span> <span data-ttu-id="e7269-120">그러나이 보고서는 기본적으로 내부용 이며 직접 액세스 하기 위한 것이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="e7269-120">However, this report is primarily for internal use, and is not intended to be directly accessed.</span></span>



</div>

<span data-ttu-id="e7269-121">Lync server 모니터링 보고서는 다음과 같은 두 가지 방법으로 설치할 수 있습니다. Lync server 배포 마법사를 사용 하거나 Lync Server 2013 설치 파일에 포함 된 Windows PowerShell 스크립트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7269-121">There are two ways to install Lync Server Monitoring Reports: you can use the Lync Server Deployment Wizard or you can use a Windows PowerShell script included with the Lync Server 2013 installation files.</span></span> <span data-ttu-id="e7269-122">보고서를 설치 하는 데 사용 하는 방법에 관계 없이 먼저 다음 사항을 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7269-122">Regardless of the method you use to install the reports you must first make sure that you:</span></span>

  - <span data-ttu-id="e7269-123">모니터링 데이터베이스의 사용자 계정에 데이터베이스 역할을 추가할 수 있는 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7269-123">Have the right to add a database role to a user account in the monitoring database.</span></span>

  - <span data-ttu-id="e7269-124">SQL Server Reporting Services에서 콘텐츠 관리자 역할을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7269-124">Hold the Content Manager role in SQL Server Reporting Services.</span></span> <span data-ttu-id="e7269-125">이 역할은 SQL Server Reporting Services에 보고서를 배포할 수 있는 권한을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7269-125">This role gives you the right to deploy reports to SQL Server Reporting Services.</span></span>

<span data-ttu-id="e7269-126">배포 마법사를 사용 하 여 모니터링 보고서를 설치 하려면 다음 단계를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7269-126">To install the Monitoring Reports by using the Deployment Wizard, complete the following steps:</span></span>

1.  <span data-ttu-id="e7269-127">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013**, **Lync server 배포 마법사**를 차례로 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7269-127">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="e7269-128">배포 마법사에서 **모니터링 보고서 배포** 를 클릭 하 여 모니터링 보고서 배포 마법사를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7269-128">In the Deployment Wizard, click **Deploy Monitoring Reports** in order to start the Deploy Monitoring Reports wizard.</span></span>

3.  <span data-ttu-id="e7269-129">모니터링 보고서 배포 마법사의 **모니터링 데이터베이스 지정** 페이지에서 모니터링 저장소를 호스트 하는 컴퓨터의 정규화 된 도메인 이름이 **모니터링 데이터베이스** 드롭다운 목록에 표시 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7269-129">In the Deploy Monitoring Reports wizard, on the **Specify Monitoring Database** page, make sure that the fully qualified domain name of the computer hosting your monitoring store appears in the **Monitoring database** dropdown list.</span></span> <span data-ttu-id="e7269-130">모니터링 저장소가 여러 개인 경우에는 드롭다운 목록에서 적절 한 서버를 선택 해야 합니다. **Sql Server Reporting Services (SSRS) 인스턴스** 상자에 올바른 SQL Server 인스턴스가 나타나는지 확인 하 고 (예: **atl-sql-001.litwareinc.com/archinst**) **Next (다음**)를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7269-130">(If you have multiple monitoring stores you will need to select the appropriate server from the dropdown list.) Verify that the correct SQL Server instance appears in the **SQL Server Reporting Services (SSRS) instance** box (for example, **atl-sql-001.litwareinc.com/archinst**) and then click **Next**.</span></span>

4.  <span data-ttu-id="e7269-131">**자격 증명 지정** 페이지의 **사용자 이름** 상자에 모니터링 보고서에 액세스할 때 사용할 계정의 도메인 이름과 사용자 이름을 입력 합니다 (예: **litwareinc \\ kenmyer**).</span><span class="sxs-lookup"><span data-stu-id="e7269-131">On the **Specify Credentials** page, in the **User name** box, type the domain name and user name of the account to be used when accessing the Monitoring Reports (for example, **litwareinc\\kenmyer**).</span></span> <span data-ttu-id="e7269-132">이 형식 (도메인 사용자 이름)을 사용 하지 않는 경우에 \\ 는 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7269-132">If you do not use this format (domain\\user name) an error will occur.</span></span>
    
    <span data-ttu-id="e7269-133">**암호** 상자에 사용자 계정 암호를 입력 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7269-133">Type the user account password in the **Password** box, and then click **Next**.</span></span> <span data-ttu-id="e7269-134">이 계정에는 특별 한 권한이 필요 하지 않음을 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="e7269-134">Note that no special rights are required for this account.</span></span> <span data-ttu-id="e7269-135">설치가 완료 되 면 계정에 필요한 로그온 및 데이터베이스 권한이 자동으로 부여 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7269-135">The account will automatically be granted the required logon and database permissions when setup completes.</span></span>

5.  <span data-ttu-id="e7269-136">**Read-Only 그룹 지정** 페이지에서 사용자 그룹 상자의 SQL Server Reporting Services에 대 한 읽기 전용 액세스 권한이 부여 될 보안 그룹의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7269-136">On the **Specify Read-Only Group** page enter the name of a security group that will be granted read-only access to the SQL Server Reporting Services in the User group box.</span></span> <span data-ttu-id="e7269-137">예를 들어 읽기 전용 관리자에 게 보고서에 대 한 액세스 권한을 부여 하려면 **RTCUniversalReadOnlyAdmins**를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7269-137">For example, to give read-only administrators access to the reports enter **RTCUniversalReadOnlyAdmins**.</span></span> <span data-ttu-id="e7269-138">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e7269-138">Click **Next**.</span></span>

6.  <span data-ttu-id="e7269-139">**명령 실행** 페이지에서 **마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e7269-139">On the **Executing Commands** page, click **Finish**.</span></span>

<span data-ttu-id="e7269-140">스크립트 DeployReports.ps1를 실행 하 여 Lync Server 관리 셸에서 모니터링 보고서를 설치할 수도 있습니다. 이 Windows PowerShell 스크립트는 \\ 설치 ReportingSetup 폴더의 Lync Server 설치 미디어에서 찾을 수 있습니다 \\ .</span><span class="sxs-lookup"><span data-stu-id="e7269-140">Monitoring Reports can also be installed from the Lync Server Management Shell by running the script DeployReports.ps1; this Windows PowerShell script can be found on the Lync Server installation media in the \\Setup\\ReportingSetup folder.</span></span> <span data-ttu-id="e7269-141">DeployReports.ps1를 사용 하 여 모니터링 보고서를 설치 하려면 관리 셸 프롬프트에 다음과 같은 명령을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7269-141">To install Monitoring Reports using DeployReports.ps1, type a command similar to the following at the Management Shell prompt:</span></span>

    C:\Program Files\Microsoft Lync Server 2013\Deployment\Setup\DeployReports.ps1 -storedUserName "litwareinc\kenmyer" -storedPassword "p@ssw0rd" -readOnlyGroupName "RTCUniversalReadOnlyAdmins" -reportServerSqlInstance "atl-sql-001.litwareinc.com" -monitoringDatabaseId "MonitoringDatabase:atl-sql-001.litwareinc.com"

<span data-ttu-id="e7269-142">위 명령에 사용 된 매개 변수는 다음 표에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7269-142">The parameters used in the preceding command are described in the following table:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e7269-143">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="e7269-143">Parameter Name</span></span></th>
<th><span data-ttu-id="e7269-144">필수</span><span class="sxs-lookup"><span data-stu-id="e7269-144">Required</span></span></th>
<th><span data-ttu-id="e7269-145">설명</span><span class="sxs-lookup"><span data-stu-id="e7269-145">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e7269-146">storedUserName</span><span class="sxs-lookup"><span data-stu-id="e7269-146">storedUserName</span></span></p></td>
<td><p><span data-ttu-id="e7269-147">예</span><span class="sxs-lookup"><span data-stu-id="e7269-147">Yes</span></span></p></td>
<td><p><span data-ttu-id="e7269-148">모니터링 저장소에 액세스 하는 데 사용 되는 도메인 \ 사용자 계정 형식입니다. 예를 들어:</span><span class="sxs-lookup"><span data-stu-id="e7269-148">User account (in the format domain\username) used to access the monitoring store; for example:</span></span></p>
<pre><code>-storedUserName &quot;litwareinc\kenmyer&quot;</code></pre>
<p><span data-ttu-id="e7269-149">이 계정에는 이전에 지정 된 SQL Server 및 SQL Server Reporting Services 권한이 있어야 하며, 그렇지 않으면 스크립트가 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7269-149">This account must have the previously-specified SQL Server and SQL Server Reporting Services permissions or the script will fail.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7269-150">storedPassword</span><span class="sxs-lookup"><span data-stu-id="e7269-150">storedPassword</span></span></p></td>
<td><p><span data-ttu-id="e7269-151">예</span><span class="sxs-lookup"><span data-stu-id="e7269-151">Yes</span></span></p></td>
<td><p><span data-ttu-id="e7269-152">모니터링 저장소에 액세스 하는 데 사용 되는 사용자 계정의 암호입니다.</span><span class="sxs-lookup"><span data-stu-id="e7269-152">Password for the user account used to access the monitoring store.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7269-153">readOnlyGroupName</span><span class="sxs-lookup"><span data-stu-id="e7269-153">readOnlyGroupName</span></span></p></td>
<td><p><span data-ttu-id="e7269-154">아니요</span><span class="sxs-lookup"><span data-stu-id="e7269-154">No</span></span></p></td>
<td><p><span data-ttu-id="e7269-155">해당 구성원에 게 모니터링 보고서에 대 한 읽기 전용 액세스 권한이 부여 되는 도메인 또는 로컬 보안 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="e7269-155">Domain or local security group whose members will be granted read-only access to the Monitoring Reports.</span></span> <span data-ttu-id="e7269-156">지정한 그룹이 없으면 스크립트를 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e7269-156">Note that the script will fail if the specified group does not exist.</span></span> <span data-ttu-id="e7269-157">나중에 이러한 사용 권한을 해지 하거나 다른 사용자나 다른 그룹에 게 권한을 부여 하기로 결정 한 경우 SQL Service Reporting Services 보고서 관리자를 사용 하 여이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7269-157">If you later decide to revoke these permissions, or if you decide to grant other users or other groups access permissions, you can do so using the SQL Service Reporting Services Report Manager.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7269-158">reportSqlServerInstance</span><span class="sxs-lookup"><span data-stu-id="e7269-158">reportSqlServerInstance</span></span></p></td>
<td><p><span data-ttu-id="e7269-159">아니요</span><span class="sxs-lookup"><span data-stu-id="e7269-159">No</span></span></p></td>
<td><p><span data-ttu-id="e7269-160">Reporting Service를 호스트 하는 SQL Server 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="e7269-160">SQL Server instance that hosts the Reporting Service.</span></span> <span data-ttu-id="e7269-161">보고서 서버의 정규화 된 도메인 이름을 사용 하 여 보고 인스턴스를 지정 해야 합니다. 예를 들어:</span><span class="sxs-lookup"><span data-stu-id="e7269-161">The Reporting instance must be specified using the fully qualified domain name of the Report Server; for example:</span></span></p>
<pre><code>-reportServerSqlInstance atl-sql-001.litwareinc.com</code></pre>
<p><span data-ttu-id="e7269-162">이 매개 변수를 포함 하지 않을 경우 스크립트는 모니터링 데이터베이스를 호스팅하는 동일한 SQL Server 인스턴스에서 reporting services를 호스트 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7269-162">If this parameter is not included the script will assume that the reporting services are hosted by the same SQL Server instance that hosts the monitoring database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7269-163">monitoringDatabaseId</span><span class="sxs-lookup"><span data-stu-id="e7269-163">monitoringDatabaseId</span></span></p></td>
<td><p><span data-ttu-id="e7269-164">아니요</span><span class="sxs-lookup"><span data-stu-id="e7269-164">No</span></span></p></td>
<td><p><span data-ttu-id="e7269-165">모니터링 데이터베이스의 서비스 Id입니다.</span><span class="sxs-lookup"><span data-stu-id="e7269-165">Service Identity for the monitoring database.</span></span> <span data-ttu-id="e7269-166">다음 명령을 실행 하 여 모니터링 데이터베이스에 대 한 Id를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7269-166">You can return the Identities for your monitoring databases by running this command:</span></span></p>
<pre><code>Get-CsService -MonitoringDatabase</code></pre></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e7269-167">모니터링 보고서를 설치한 후에는 Set-CsReportingConfiguration cmdlet을 사용 하 여 이러한 보고서에 액세스 하는 데 사용 되는 URL을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7269-167">After the Monitoring Reports have been installed you must then use the Set-CsReportingConfiguration cmdlet to configure the URL used to access these reports.</span></span> <span data-ttu-id="e7269-168">이 작업은 다음 Windows PowerShell 명령을 실행 하 여 Lync Server 관리 셸에서 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7269-168">This task can be carried out from the Lync Server Management Shell by running the following Windows PowerShell command.</span></span> <span data-ttu-id="e7269-169">보고 URL을 구성 하는 경우 HTTPS 프로토콜을 사용 하는 것이 좋지만 반드시 필요한 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="e7269-169">Note that it is recommended, but not required, that you use the HTTPS protocol when configuring the reporting URL:</span></span>

    Set-CsReportingConfiguration -Identity "MonitoringDatabase:atl-sql-001.litwareinc.com" -ReportingURL "https://atl-sql-001.litwareinc.com:443/Reports_ARCHINST"

<span data-ttu-id="e7269-170">위 명령에서 ReportingUrl 속성은 SQL Server 2008 R2 Reporting Services에서 사용 하는 보고서 관리자 URL로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7269-170">In the preceding command, the ReportingUrl property should be set to the Report Manager URL used by SQL Server 2008 R2 Reporting Services.</span></span> <span data-ttu-id="e7269-171">SQL Server Reporting Services가 설치 된 컴퓨터에서 다음 단계를 완료 하 여 보고서 관리자 URL을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7269-171">You can determine the Report Manager URL by completing the following steps on the computer where SQL Server Reporting Services has been installed:</span></span>

1.  <span data-ttu-id="e7269-172">시작, 모든 프로그램, Microsoft SQL Server 2008 R2, 구성 도구를 차례로 클릭 한 후 Reporting Services 구성 관리자를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7269-172">Click Start, click All Programs, click Microsoft SQL Server 2008 R2, click Configuration Tools, and then click Reporting Services Configuration Manager.</span></span>

2.  <span data-ttu-id="e7269-173">Reporting Services 구성 연결 대화 상자에서 서버 이름 상자에 Reporting Services 컴퓨터의 이름을 표시 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7269-173">In the Reporting Services Configuration Connection dialog box, make sure that the name of the Reporting Services computer appears in the Server Name box.</span></span> <span data-ttu-id="e7269-174">보고서 서버 인스턴스 드롭다운 목록에서 SQL Server 인스턴스를 선택 하 고 연결을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7269-174">Select the SQL Server instance from the Report Server Instance dropdown list and then click Connect.</span></span>

3.  <span data-ttu-id="e7269-175">Reporting Services 구성 관리자에서 보고서 관리자 URL을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7269-175">In Reporting Services Configuration Manager, click Report Manager URL.</span></span> <span data-ttu-id="e7269-176">하나 이상의 Url이 보고서 관리자 URL 창에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7269-176">One or more URLs should appear in the Report Manager URL pane.</span></span> <span data-ttu-id="e7269-177">이러한 Url을 보고 URL로 사용할 수 있지만 다시 말하지만, ReportingUrl에서 HTTPS 프로토콜을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e7269-177">Any of these URLs can be used as the Reporting URL although, again, it is recommended that the ReportingUrl use the HTTPS protocol.</span></span>

<span data-ttu-id="e7269-178">모니터링 데이터베이스에 대 한 미러 데이터베이스를 설정한 경우에는 모니터링 보고서를 미러 데이터베이스에도 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7269-178">If you have set up a mirror database for your monitoring database then you must also associate the Monitoring Reports with the mirror database.</span></span> <span data-ttu-id="e7269-179">자세한 내용은 [Lync Server 2013에서 모니터링 보고서를 미러 데이터베이스에 연결](lync-server-2013-associating-monitoring-reports-with-a-mirror-database.md) 문서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e7269-179">See the article [Associating Monitoring Reports with a mirror database in Lync Server 2013](lync-server-2013-associating-monitoring-reports-with-a-mirror-database.md) for details.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

