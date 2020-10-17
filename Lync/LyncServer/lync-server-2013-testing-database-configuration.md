---
title: 'Lync Server 2013: 데이터베이스 구성 테스트'
description: 'Lync Server 2013: 데이터베이스 구성을 테스트 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing database configuration
ms:assetid: 60f7fcd2-5efe-4791-b159-b0f9bf39a41b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727307(v=OCS.15)
ms:contentKeyID: 63969606
ms.date: 07/07/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b9f88eee99c4a2d523cc84df401dcc1d7b9fe59
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560684"
---
# <a name="testing-database-configuration-in-lync-server-2013"></a><span data-ttu-id="bc2d0-103">Lync Server 2013의 데이터베이스 구성 테스트</span><span class="sxs-lookup"><span data-stu-id="bc2d0-103">Testing database configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bc2d0-104">_**마지막으로 수정 된 항목:** 2016-07-07_</span><span class="sxs-lookup"><span data-stu-id="bc2d0-104">_**Topic Last Modified:** 2016-07-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bc2d0-105">확인 일정</span><span class="sxs-lookup"><span data-stu-id="bc2d0-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="bc2d0-106">매일</span><span class="sxs-lookup"><span data-stu-id="bc2d0-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc2d0-107">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="bc2d0-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="bc2d0-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bc2d0-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc2d0-109">필요한 권한</span><span class="sxs-lookup"><span data-stu-id="bc2d0-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="bc2d0-110">Lync Server 관리 셸을 사용 하 여 로컬로 실행 하는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 하며 SQL Server에 대 한 관리자 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc2d0-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group, and need to have Administrator privileges on the SQL server.</span></span></p>
<p><span data-ttu-id="bc2d0-111">Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우, 사용자에 게는 <strong>CsDatabase</strong> cmdlet을 실행 하는 권한이 있는 RBAC 역할을 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc2d0-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsDatabase</strong> cmdlet.</span></span> <span data-ttu-id="bc2d0-112">이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc2d0-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDatabase&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="bc2d0-113">설명</span><span class="sxs-lookup"><span data-stu-id="bc2d0-113">Description</span></span>

<span data-ttu-id="bc2d0-114">**테스트-CsDatabase** cmdlet은 하나 이상의 Lync Server 2013 데이터베이스에 대 한 연결을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc2d0-114">The **Test-CsDatabase** cmdlet verifies connectivity to one or more Lync Server 2013 databases.</span></span> <span data-ttu-id="bc2d0-115">실행 하는 경우, **테스트-CsDatabase** Cmdlet은 Lync Server 토폴로지를 읽고 관련 데이터베이스에 대 한 연결을 시도한 다음 각 시도의 성공 또는 실패를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc2d0-115">When run, the **Test-CsDatabase** cmdlet reads the Lync Server topology, attempts to connect to relevant databases, and then reports back the success or failure of each try.</span></span> <span data-ttu-id="bc2d0-116">연결이 가능한 경우 이 cmdlet은 데이터베이스 이름, SQL Server 버전 정보 및 설치된 미러 데이터베이스의 위치와 같은 정보도 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="bc2d0-116">If a connection can be made, the cmdlet will also report back such information as the database name, SQL Server version information, and the location of any installed mirror databases.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="bc2d0-117">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="bc2d0-117">Running the test</span></span>

<span data-ttu-id="bc2d0-118">예제 1에 표시된 명령은 중앙 관리 데이터베이스의 구성을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="bc2d0-118">The command shown in Example 1 verifies the configuration of the Central Management database.</span></span>

    Test-CsDatabase -CentralManagementDatabase

<span data-ttu-id="bc2d0-119">예제 2에서는 atl-sql-001.litwareinc.com 컴퓨터에 설치 된 모든 Lync Server 데이터베이스를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc2d0-119">Example 2 verifies all the Lync Server databases installed on the computer atl-sql-001.litwareinc.com.</span></span>

    Test-CsDatabase -ConfiguredDatabases -SqlServerFqdn "atl-sql-001.litwareinc.com"

<span data-ttu-id="bc2d0-p103">예제 3에서는 atl-sql-001.litwareinc.com 컴퓨터에 설치된 보관 데이터베이스에 대해서만 확인을 수행합니다. 보관 데이터베이스가 있는 SQL Server 인스턴스(Archinst)를 지정하기 위해 SqlInstanceName 매개 변수가 포함되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bc2d0-p103">In Example 3, verification is performed only for the Archiving database installed on the computer atl-sql-001.litwareinc.com. Note that the SqlInstanceName parameter is included to specify the SQL Server instance (Archinst) where the Archiving database is located.</span></span>

    Test-CsDatabase -DatabaseType "Archiving" -SqlServerFqdn "atl-sql-001.litwareinc.com" -SqlInstanceName "archinst"

<span data-ttu-id="bc2d0-122">예제 4에 표시된 명령은 로컬 컴퓨터에 설치된 데이터베이스를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="bc2d0-122">The command shown in Example 4 verifies the databases installed on the local computer.</span></span>

    Test-CsDatabase -LocalService

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="bc2d0-123">성공 또는 실패 확인</span><span class="sxs-lookup"><span data-stu-id="bc2d0-123">Determining success or failure</span></span>

<span data-ttu-id="bc2d0-124">데이터베이스 연결이 올바르게 구성 되 면 다음과 비슷한 출력이 표시 되며 성공 속성은 **True**로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc2d0-124">If database connectivity is configured correctly, you'll receive output similar to this, with the Succeed property marked as **True**:</span></span>

<span data-ttu-id="bc2d0-125">변수와 sqlserverfqdn: atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="bc2d0-125">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="bc2d0-126">SqlInstanceName: rtc</span><span class="sxs-lookup"><span data-stu-id="bc2d0-126">SqlInstanceName : rtc</span></span>

<span data-ttu-id="bc2d0-127">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="bc2d0-127">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="bc2d0-128">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="bc2d0-128">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="bc2d0-129">DatabaseName: xds</span><span class="sxs-lookup"><span data-stu-id="bc2d0-129">DatabaseName : xds</span></span>

<span data-ttu-id="bc2d0-130">아닙니다</span><span class="sxs-lookup"><span data-stu-id="bc2d0-130">DataSource :</span></span>

<span data-ttu-id="bc2d0-131">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="bc2d0-131">SQLServerVersion :</span></span>

<span data-ttu-id="bc2d0-132">ExpectedVersion : 10.13.2</span><span class="sxs-lookup"><span data-stu-id="bc2d0-132">ExpectedVersion : 10.13.2</span></span>

<span data-ttu-id="bc2d0-133">InstalledVersion :</span><span class="sxs-lookup"><span data-stu-id="bc2d0-133">InstalledVersion :</span></span>

<span data-ttu-id="bc2d0-134">성공: True</span><span class="sxs-lookup"><span data-stu-id="bc2d0-134">Succeed : True</span></span>

<span data-ttu-id="bc2d0-135">변수와 sqlserverfqdn: atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="bc2d0-135">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="bc2d0-136">SqlInstanceName: rtc</span><span class="sxs-lookup"><span data-stu-id="bc2d0-136">SqlInstanceName : rtc</span></span>

<span data-ttu-id="bc2d0-137">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="bc2d0-137">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="bc2d0-138">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="bc2d0-138">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="bc2d0-139">DatabaseName: lis</span><span class="sxs-lookup"><span data-stu-id="bc2d0-139">DatabaseName : lis</span></span>

<span data-ttu-id="bc2d0-140">아닙니다</span><span class="sxs-lookup"><span data-stu-id="bc2d0-140">DataSource :</span></span>

<span data-ttu-id="bc2d0-141">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="bc2d0-141">SQLServerVersion :</span></span>

<span data-ttu-id="bc2d0-142">ExpectedVersion : 3.1.1</span><span class="sxs-lookup"><span data-stu-id="bc2d0-142">ExpectedVersion : 3.1.1</span></span>

<span data-ttu-id="bc2d0-143">InstalledVersion :</span><span class="sxs-lookup"><span data-stu-id="bc2d0-143">InstalledVersion :</span></span>

<span data-ttu-id="bc2d0-144">성공: True</span><span class="sxs-lookup"><span data-stu-id="bc2d0-144">Succeed : True</span></span>

<span data-ttu-id="bc2d0-145">데이터베이스가 올바르게 구성 되었지만 계속 사용할 수 있는 경우 성공 필드는 **False**로 표시 되 고 다음과 같은 추가 경고 및 정보가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc2d0-145">If the database is configured correctly but still available, the Succeed field will be shown as **False**, and additional warnings and information will be provided:</span></span>

<span data-ttu-id="bc2d0-146">변수와 sqlserverfqdn: atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="bc2d0-146">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="bc2d0-147">SqlInstanceName: rtc</span><span class="sxs-lookup"><span data-stu-id="bc2d0-147">SqlInstanceName : rtc</span></span>

<span data-ttu-id="bc2d0-148">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="bc2d0-148">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="bc2d0-149">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="bc2d0-149">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="bc2d0-150">DatabaseName: xds</span><span class="sxs-lookup"><span data-stu-id="bc2d0-150">DatabaseName : xds</span></span>

<span data-ttu-id="bc2d0-151">아닙니다</span><span class="sxs-lookup"><span data-stu-id="bc2d0-151">DataSource :</span></span>

<span data-ttu-id="bc2d0-152">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="bc2d0-152">SQLServerVersion :</span></span>

<span data-ttu-id="bc2d0-153">ExpectedVersion : 10.13.2</span><span class="sxs-lookup"><span data-stu-id="bc2d0-153">ExpectedVersion : 10.13.2</span></span>

<span data-ttu-id="bc2d0-154">InstalledVersion :</span><span class="sxs-lookup"><span data-stu-id="bc2d0-154">InstalledVersion :</span></span>

<span data-ttu-id="bc2d0-155">성공: False</span><span class="sxs-lookup"><span data-stu-id="bc2d0-155">Succeed : False</span></span>

<span data-ttu-id="bc2d0-156">변수와 sqlserverfqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="bc2d0-156">SqlServerFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="bc2d0-157">SqlInstanceName: rtc</span><span class="sxs-lookup"><span data-stu-id="bc2d0-157">SqlInstanceName : rtc</span></span>

<span data-ttu-id="bc2d0-158">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="bc2d0-158">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="bc2d0-159">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="bc2d0-159">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="bc2d0-160">DatabaseName: lis</span><span class="sxs-lookup"><span data-stu-id="bc2d0-160">DatabaseName : lis</span></span>

<span data-ttu-id="bc2d0-161">아닙니다</span><span class="sxs-lookup"><span data-stu-id="bc2d0-161">DataSource :</span></span>

<span data-ttu-id="bc2d0-162">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="bc2d0-162">SQLServerVersion :</span></span>

<span data-ttu-id="bc2d0-163">ExpectedVersion : 3.1.1</span><span class="sxs-lookup"><span data-stu-id="bc2d0-163">ExpectedVersion : 3.1.1</span></span>

<span data-ttu-id="bc2d0-164">InstalledVersion :</span><span class="sxs-lookup"><span data-stu-id="bc2d0-164">InstalledVersion :</span></span>

<span data-ttu-id="bc2d0-165">성공: False</span><span class="sxs-lookup"><span data-stu-id="bc2d0-165">Succeed : False</span></span>

<span data-ttu-id="bc2d0-166">경고: Test-CsDatabase에서 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="bc2d0-166">WARNING: Test-CsDatabase encountered errors.</span></span> <span data-ttu-id="bc2d0-167">자세한 내용은 로그 파일을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="bc2d0-167">Consult the log file for a</span></span>

<span data-ttu-id="bc2d0-168">자세한 분석 및 모든 오류 (2) 및 경고 (0)가 처리 되는지 확인</span><span class="sxs-lookup"><span data-stu-id="bc2d0-168">detailed analysis, and to make sure that all errors (2) and warnings (0) are addressed</span></span>

<span data-ttu-id="bc2d0-169">를 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc2d0-169">before continuing.</span></span>

<span data-ttu-id="bc2d0-170">경고: 자세한 결과는 다음 위치에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc2d0-170">WARNING: Detailed results can be found at</span></span>

<span data-ttu-id="bc2d0-171">"C: \\ 사용자 \\ 테스트 \\ AppData \\ 로컬 \\ 온도 \\ 2 \\ 테스트-csdatabase-b18d488a-8044-4679-bbf2-</span><span class="sxs-lookup"><span data-stu-id="bc2d0-171">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsDatabase-b18d488a-8044-4679-bbf2-</span></span>

<span data-ttu-id="bc2d0-172">04d593cce8e6.html ")</span><span class="sxs-lookup"><span data-stu-id="bc2d0-172">04d593cce8e6.html".</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="bc2d0-173">테스트가 실패 한 이유</span><span class="sxs-lookup"><span data-stu-id="bc2d0-173">Reasons why the test might have failed</span></span>

<span data-ttu-id="bc2d0-174">**테스트 CsDatabase에** 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bc2d0-174">Here are some common reasons why **Test-CsDatabase** might fail:</span></span>

  - <span data-ttu-id="bc2d0-175">잘못 된 매개 변수 값이 제공 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bc2d0-175">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="bc2d0-176">사용 하는 경우 선택적 매개 변수를 올바르게 구성 해야 하며 그렇지 않으면 테스트가 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc2d0-176">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="bc2d0-177">선택적 매개 변수 없이 명령을 다시 실행 하 여 성공 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc2d0-177">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="bc2d0-178">데이터베이스가 잘못 구성 되었거나 아직 배포 되지 않은 경우에는이 명령이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc2d0-178">This command will fail if the database is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bc2d0-179">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bc2d0-179">See Also</span></span>


[<span data-ttu-id="bc2d0-180">Get-csdatabasemirrorstate</span><span class="sxs-lookup"><span data-stu-id="bc2d0-180">Get-CsDatabaseMirrorState</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsDatabaseMirrorState)  
[<span data-ttu-id="bc2d0-181">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="bc2d0-181">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[<span data-ttu-id="bc2d0-182">Get-CsUserDatabaseState</span><span class="sxs-lookup"><span data-stu-id="bc2d0-182">Get-CsUserDatabaseState</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserDatabaseState)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

