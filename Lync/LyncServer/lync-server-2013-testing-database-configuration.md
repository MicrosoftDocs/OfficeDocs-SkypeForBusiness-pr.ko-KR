---
title: 'Lync Server 2013: 데이터베이스 구성 테스트'
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
ms.openlocfilehash: 6fcf6679481d4f35a457eb72960a8ae999b004d3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745828"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-database-configuration-in-lync-server-2013"></a><span data-ttu-id="a62a8-102">Lync Server 2013에서 데이터베이스 구성 테스트</span><span class="sxs-lookup"><span data-stu-id="a62a8-102">Testing database configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a62a8-103">_**마지막으로 수정한 주제:** 2016-07-07_</span><span class="sxs-lookup"><span data-stu-id="a62a8-103">_**Topic Last Modified:** 2016-07-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a62a8-104">확인 일정</span><span class="sxs-lookup"><span data-stu-id="a62a8-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="a62a8-105">Daily</span><span class="sxs-lookup"><span data-stu-id="a62a8-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a62a8-106">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="a62a8-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="a62a8-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a62a8-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a62a8-108">권한이 필요 함</span><span class="sxs-lookup"><span data-stu-id="a62a8-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="a62a8-109">Lync Server Management Shell을 사용 하 여 로컬에서 실행 되는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 하 고 SQL Server에 대 한 관리자 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a62a8-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group, and need to have Administrator privileges on the SQL server.</span></span></p>
<p><span data-ttu-id="a62a8-110">Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 <strong>테스트 CsDatabase</strong> cmdlet을 실행할 권한이 있는 RBAC 역할을 사용자에 게 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a62a8-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsDatabase</strong> cmdlet.</span></span> <span data-ttu-id="a62a8-111">이 cmdlet을 사용할 수 있는 모든 RBAC 역할 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a62a8-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDatabase&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="a62a8-112">설명</span><span class="sxs-lookup"><span data-stu-id="a62a8-112">Description</span></span>

<span data-ttu-id="a62a8-113">**테스트-csdatabase** cmdlet은 하나 이상의 Lync Server 2013 데이터베이스에 대 한 연결을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a62a8-113">The **Test-CsDatabase** cmdlet verifies connectivity to one or more Lync Server 2013 databases.</span></span> <span data-ttu-id="a62a8-114">실행 되 면 **테스트 CsDatabase** Cmdlet이 Lync Server 토폴로지를 읽고 관련 데이터베이스에 연결을 시도한 다음 각 시도의 성공 또는 실패를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="a62a8-114">When run, the **Test-CsDatabase** cmdlet reads the Lync Server topology, attempts to connect to relevant databases, and then reports back the success or failure of each try.</span></span> <span data-ttu-id="a62a8-115">연결을 설정할 수 있는 경우에는 cmdlet에서 데이터베이스 이름, SQL Server 버전 정보, 설치 된 미러 데이터베이스의 위치 등의 정보를 함께 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="a62a8-115">If a connection can be made, the cmdlet will also report back such information as the database name, SQL Server version information, and the location of any installed mirror databases.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="a62a8-116">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="a62a8-116">Running the test</span></span>

<span data-ttu-id="a62a8-117">예제 1에 표시 된 명령은 중앙 관리 데이터베이스의 구성을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a62a8-117">The command shown in Example 1 verifies the configuration of the Central Management database.</span></span>

    Test-CsDatabase -CentralManagementDatabase

<span data-ttu-id="a62a8-118">예제 2는 컴퓨터 atl-sql-001.litwareinc.com에 설치 된 모든 Lync Server 데이터베이스를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a62a8-118">Example 2 verifies all the Lync Server databases installed on the computer atl-sql-001.litwareinc.com.</span></span>

    Test-CsDatabase -ConfiguredDatabases -SqlServerFqdn "atl-sql-001.litwareinc.com"

<span data-ttu-id="a62a8-119">예제 3에서는 컴퓨터 atl-sql-001.litwareinc.com에 설치 된 보관 데이터베이스에 대해서만 확인이 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a62a8-119">In Example 3, verification is performed only for the Archiving database installed on the computer atl-sql-001.litwareinc.com.</span></span> <span data-ttu-id="a62a8-120">SqlInstanceName 매개 변수는 보관 데이터베이스가 있는 Archinst (SQL Server 인스턴스)를 지정 하기 위해 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a62a8-120">Note that the SqlInstanceName parameter is included to specify the SQL Server instance (Archinst) where the Archiving database is located.</span></span>

    Test-CsDatabase -DatabaseType "Archiving" -SqlServerFqdn "atl-sql-001.litwareinc.com" -SqlInstanceName "archinst"

<span data-ttu-id="a62a8-121">예제 4에 나와 있는 명령은 로컬 컴퓨터에 설치 된 데이터베이스를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a62a8-121">The command shown in Example 4 verifies the databases installed on the local computer.</span></span>

    Test-CsDatabase -LocalService

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="a62a8-122">성공 또는 실패 확인</span><span class="sxs-lookup"><span data-stu-id="a62a8-122">Determining success or failure</span></span>

<span data-ttu-id="a62a8-123">데이터베이스 연결이 올바르게 구성 되 면 다음과 비슷한 출력이 표시 되며 성공 속성은 **True**로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a62a8-123">If database connectivity is configured correctly, you'll receive output similar to this, with the Succeed property marked as **True**:</span></span>

<span data-ttu-id="a62a8-124">SqlServerFqdn: atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="a62a8-124">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="a62a8-125">SqlInstanceName: rtc</span><span class="sxs-lookup"><span data-stu-id="a62a8-125">SqlInstanceName : rtc</span></span>

<span data-ttu-id="a62a8-126">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="a62a8-126">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="a62a8-127">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="a62a8-127">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="a62a8-128">DatabaseName: xds</span><span class="sxs-lookup"><span data-stu-id="a62a8-128">DatabaseName : xds</span></span>

<span data-ttu-id="a62a8-129">원본은</span><span class="sxs-lookup"><span data-stu-id="a62a8-129">DataSource :</span></span>

<span data-ttu-id="a62a8-130">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="a62a8-130">SQLServerVersion :</span></span>

<span data-ttu-id="a62a8-131">ExpectedVersion : 10.13.2</span><span class="sxs-lookup"><span data-stu-id="a62a8-131">ExpectedVersion : 10.13.2</span></span>

<span data-ttu-id="a62a8-132">InstalledVersion :</span><span class="sxs-lookup"><span data-stu-id="a62a8-132">InstalledVersion :</span></span>

<span data-ttu-id="a62a8-133">성공: True</span><span class="sxs-lookup"><span data-stu-id="a62a8-133">Succeed : True</span></span>

<span data-ttu-id="a62a8-134">SqlServerFqdn: atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="a62a8-134">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="a62a8-135">SqlInstanceName: rtc</span><span class="sxs-lookup"><span data-stu-id="a62a8-135">SqlInstanceName : rtc</span></span>

<span data-ttu-id="a62a8-136">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="a62a8-136">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="a62a8-137">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="a62a8-137">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="a62a8-138">DatabaseName: lis</span><span class="sxs-lookup"><span data-stu-id="a62a8-138">DatabaseName : lis</span></span>

<span data-ttu-id="a62a8-139">원본은</span><span class="sxs-lookup"><span data-stu-id="a62a8-139">DataSource :</span></span>

<span data-ttu-id="a62a8-140">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="a62a8-140">SQLServerVersion :</span></span>

<span data-ttu-id="a62a8-141">ExpectedVersion : 3.1.1</span><span class="sxs-lookup"><span data-stu-id="a62a8-141">ExpectedVersion : 3.1.1</span></span>

<span data-ttu-id="a62a8-142">InstalledVersion :</span><span class="sxs-lookup"><span data-stu-id="a62a8-142">InstalledVersion :</span></span>

<span data-ttu-id="a62a8-143">성공: True</span><span class="sxs-lookup"><span data-stu-id="a62a8-143">Succeed : True</span></span>

<span data-ttu-id="a62a8-144">데이터베이스가 올바르게 구성 되었지만 계속 사용할 수 있는 경우에는 성공 필드가 **False**로 표시 되 고 추가 경고 및 정보가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a62a8-144">If the database is configured correctly but still available, the Succeed field will be shown as **False**, and additional warnings and information will be provided:</span></span>

<span data-ttu-id="a62a8-145">SqlServerFqdn: atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="a62a8-145">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="a62a8-146">SqlInstanceName: rtc</span><span class="sxs-lookup"><span data-stu-id="a62a8-146">SqlInstanceName : rtc</span></span>

<span data-ttu-id="a62a8-147">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="a62a8-147">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="a62a8-148">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="a62a8-148">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="a62a8-149">DatabaseName: xds</span><span class="sxs-lookup"><span data-stu-id="a62a8-149">DatabaseName : xds</span></span>

<span data-ttu-id="a62a8-150">원본은</span><span class="sxs-lookup"><span data-stu-id="a62a8-150">DataSource :</span></span>

<span data-ttu-id="a62a8-151">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="a62a8-151">SQLServerVersion :</span></span>

<span data-ttu-id="a62a8-152">ExpectedVersion : 10.13.2</span><span class="sxs-lookup"><span data-stu-id="a62a8-152">ExpectedVersion : 10.13.2</span></span>

<span data-ttu-id="a62a8-153">InstalledVersion :</span><span class="sxs-lookup"><span data-stu-id="a62a8-153">InstalledVersion :</span></span>

<span data-ttu-id="a62a8-154">성공: False</span><span class="sxs-lookup"><span data-stu-id="a62a8-154">Succeed : False</span></span>

<span data-ttu-id="a62a8-155">SqlServerFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="a62a8-155">SqlServerFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="a62a8-156">SqlInstanceName: rtc</span><span class="sxs-lookup"><span data-stu-id="a62a8-156">SqlInstanceName : rtc</span></span>

<span data-ttu-id="a62a8-157">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="a62a8-157">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="a62a8-158">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="a62a8-158">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="a62a8-159">DatabaseName: lis</span><span class="sxs-lookup"><span data-stu-id="a62a8-159">DatabaseName : lis</span></span>

<span data-ttu-id="a62a8-160">원본은</span><span class="sxs-lookup"><span data-stu-id="a62a8-160">DataSource :</span></span>

<span data-ttu-id="a62a8-161">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="a62a8-161">SQLServerVersion :</span></span>

<span data-ttu-id="a62a8-162">ExpectedVersion : 3.1.1</span><span class="sxs-lookup"><span data-stu-id="a62a8-162">ExpectedVersion : 3.1.1</span></span>

<span data-ttu-id="a62a8-163">InstalledVersion :</span><span class="sxs-lookup"><span data-stu-id="a62a8-163">InstalledVersion :</span></span>

<span data-ttu-id="a62a8-164">성공: False</span><span class="sxs-lookup"><span data-stu-id="a62a8-164">Succeed : False</span></span>

<span data-ttu-id="a62a8-165">경고: 테스트 CsDatabase에 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="a62a8-165">WARNING: Test-CsDatabase encountered errors.</span></span> <span data-ttu-id="a62a8-166">로그 파일을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a62a8-166">Consult the log file for a</span></span>

<span data-ttu-id="a62a8-167">자세한 분석 및 모든 오류 (2) 및 경고 (0)가 처리 되었는지 확인</span><span class="sxs-lookup"><span data-stu-id="a62a8-167">detailed analysis, and to make sure that all errors (2) and warnings (0) are addressed</span></span>

<span data-ttu-id="a62a8-168">계속 하십시오.</span><span class="sxs-lookup"><span data-stu-id="a62a8-168">before continuing.</span></span>

<span data-ttu-id="a62a8-169">경고: 자세한 결과는 다음에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a62a8-169">WARNING: Detailed results can be found at</span></span>

<span data-ttu-id="a62a8-170">"C:\\AppData\\\\\\Local\\\Temp\\2\\테스트-csdatabase를 테스트 하는 사용자-b18d488a-8044-4679-bbf2-</span><span class="sxs-lookup"><span data-stu-id="a62a8-170">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsDatabase-b18d488a-8044-4679-bbf2-</span></span>

<span data-ttu-id="a62a8-171">04d593cce8e6 ".</span><span class="sxs-lookup"><span data-stu-id="a62a8-171">04d593cce8e6.html".</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="a62a8-172">테스트가 실패할 수 있는 이유</span><span class="sxs-lookup"><span data-stu-id="a62a8-172">Reasons why the test might have failed</span></span>

<span data-ttu-id="a62a8-173">**테스트 CsDatabase에** 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a62a8-173">Here are some common reasons why **Test-CsDatabase** might fail:</span></span>

  - <span data-ttu-id="a62a8-174">잘못 된 매개 변수 값이 제공 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a62a8-174">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="a62a8-175">사용 하는 경우 선택적 매개 변수를 올바르게 구성 하거나 테스트에 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="a62a8-175">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="a62a8-176">선택적 매개 변수 없이 명령을 다시 실행 하 여 성공 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a62a8-176">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="a62a8-177">데이터베이스가 잘못 구성 되었거나 아직 배포 되지 않은 경우에는이 명령이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="a62a8-177">This command will fail if the database is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a62a8-178">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a62a8-178">See Also</span></span>


[<span data-ttu-id="a62a8-179">Get-CsDatabaseMirrorState</span><span class="sxs-lookup"><span data-stu-id="a62a8-179">Get-CsDatabaseMirrorState</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsDatabaseMirrorState)  
[<span data-ttu-id="a62a8-180">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="a62a8-180">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[<span data-ttu-id="a62a8-181">Get-Csuserdatabasedatabasestate</span><span class="sxs-lookup"><span data-stu-id="a62a8-181">Get-CsUserDatabaseState</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserDatabaseState)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

