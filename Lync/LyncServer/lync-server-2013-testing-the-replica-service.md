---
title: 'Lync Server 2013: 복제본 서비스 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the replica service
ms:assetid: 4ff2cc91-0036-4c5a-9792-7bf43d8ce18d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727303(v=OCS.15)
ms:contentKeyID: 63969600
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2784796d0eaca5d37aa841ee3db351a841c3c397
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141274"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-the-replica-service-in-lync-server-2013"></a><span data-ttu-id="c4a19-102">Lync Server 2013에서 복제본 서비스 테스트</span><span class="sxs-lookup"><span data-stu-id="c4a19-102">Testing the replica service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c4a19-103">_**마지막으로 수정 된 항목:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="c4a19-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c4a19-104">확인 일정</span><span class="sxs-lookup"><span data-stu-id="c4a19-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="c4a19-105">매일</span><span class="sxs-lookup"><span data-stu-id="c4a19-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4a19-106">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="c4a19-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="c4a19-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c4a19-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4a19-108">필요한 권한</span><span class="sxs-lookup"><span data-stu-id="c4a19-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="c4a19-109">Lync Server 관리 셸을 사용 하 여 로컬로 실행 하는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4a19-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="c4a19-110">Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우, 사용자에 게는 <strong>CsReplica</strong> cmdlet을 실행 하는 권한이 있는 RBAC 역할이 할당 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4a19-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsReplica</strong> cmdlet.</span></span> <span data-ttu-id="c4a19-111">이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4a19-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsReplica&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="c4a19-112">설명</span><span class="sxs-lookup"><span data-stu-id="c4a19-112">Description</span></span>

<span data-ttu-id="c4a19-113">**테스트-csreplica** cmdlet은 로컬 컴퓨터에서 Lync Server 2013 복제본 서비스가 실행 되 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4a19-113">The **Test-CsReplica** cmdlet verifies that the Lync Server 2013 replica service is running on the local computer.</span></span> <span data-ttu-id="c4a19-114">**테스트-CsReplica** cmdlet은 다음과 같은 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4a19-114">The **Test-CsReplica** cmdlet performs such tasks as:</span></span>

  - <span data-ttu-id="c4a19-115">복제기 에이전트 및 중앙 로깅 에이전트 서비스의 상태 확인</span><span class="sxs-lookup"><span data-stu-id="c4a19-115">checking the status of the Replicator Agent and Centralized Logging Agent services</span></span>

  - <span data-ttu-id="c4a19-116">Windows 방화벽에서 필요한 포트가 열려 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="c4a19-116">verifying that the required ports were opened in the Windows Firewall</span></span>

  - <span data-ttu-id="c4a19-117">필요한 Active Directory 및 로컬 컴퓨터 보안 그룹이 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="c4a19-117">making sure that the necessary Active Directory and local computer security groups exist.</span></span>

<span data-ttu-id="c4a19-118">이 cmdlet은 로컬로 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4a19-118">Note that this cmdlet must be run locally.</span></span> <span data-ttu-id="c4a19-119">즉, 복제 서비스가 실행 되 고 있는 동일한 컴퓨터에서 실행 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4a19-119">That is, it must be run on the same computer where the replica service is running.</span></span> <span data-ttu-id="c4a19-120">원격 서버에 대해 **CsReplica** cmdlet을 실행 하기 위한 옵션은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c4a19-120">There are no options for running the **Test-CsReplica** cmdlet against a remote server.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="c4a19-121">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="c4a19-121">Running the test</span></span>

<span data-ttu-id="c4a19-122">예제 1에 표시 된 명령은 로컬 컴퓨터에서 Lync Server 2013 복제본 서비스를 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4a19-122">The command shown in Example 1 tests the Lync Server 2013 replica service on the local computer.</span></span> <span data-ttu-id="c4a19-123">이 예제에서는 Verbose 매개 변수를 사용 하 여 테스트에 대 한 성공 또는 실패를 비롯 하 여 테스트를 통해 생성 된 보고서의 위치와 화면에 표시 되는 결과를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4a19-123">In this example the Verbose parameter is used to guarantee that information about the test – including the eventual failure or success of the test and the location of the report generated by the test – is displayed on screen.</span></span>

    Test-CsReplica -Verbose

<span data-ttu-id="c4a19-124">예제 2는 예제 1에 표시된 명령의 변형입니다.</span><span class="sxs-lookup"><span data-stu-id="c4a19-124">Example 2 is a variation of the command shown in Example 1.</span></span> <span data-ttu-id="c4a19-125">이 경우 Report 매개 변수는 테스트에서 생성 된 보고서의 폴더 경로와 이름을 지정 하는 데 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4a19-125">In this case, the Report parameter is included to specify a folder path and name for the report generated by the test.</span></span> <span data-ttu-id="c4a19-126">보고서 경로를 지정 하지 않으면 보고서에 다음과 유사한 자동 생성 이름이 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4a19-126">If you do not specify a report path the report will be given an auto-generated name similar to this:</span></span>

<span data-ttu-id="c4a19-127">C:\\사용자\\관리자. Litwareinc\\AppData\\Local\\Temp\\1\\Test-.cs-3db40ee0-4b5d-4f58-8d3d-b1e61253129e .html</span><span class="sxs-lookup"><span data-stu-id="c4a19-127">C:\\Users\\Administrator.Litwareinc\\AppData\\Local\\Temp\\1\\Test-Cs-Replica-3db40ee0-4b5d-4f58-8d3d-b1e61253129e.html</span></span>

    Test-CsReplica -Verbose -Report C:\Logs\ReplicaTest.html

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="c4a19-128">성공 또는 실패 확인</span><span class="sxs-lookup"><span data-stu-id="c4a19-128">Determining success or failure</span></span>

<span data-ttu-id="c4a19-129">여기에 섹션 본문을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="c4a19-129">Insert section body here.</span></span>

<span data-ttu-id="c4a19-130">VERBOSE: 새 로그 파일 만들기 "C:\\사용자\\테스트\\AppData\\Local\\Temp\\테스트-csreplica-3cb066b3-dd23-411a-8932-99f01c0f940c" .xml "을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c4a19-130">VERBOSE: Creating new log file "C:\\Users\\Testing\\AppData\\Local\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".</span></span>

<span data-ttu-id="c4a19-131">VERBOSE: 새 로그 파일 만들기 "C:\\사용자\\테스트\\AppData\\Local\\Temp\\테스트-csreplica-3cb066b3-dd23-411a-8932-99f01c0f940c" .xml "을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c4a19-131">VERBOSE: Creating new log file "C:\\Users\\Testing\\AppData\\Local\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".</span></span>

<span data-ttu-id="c4a19-132">VERBOSE: "테스트-CsReplica" 처리가 완료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c4a19-132">VERBOSE: "Test-CsReplica" processing has completed successfully.</span></span>

<span data-ttu-id="c4a19-133">VERBOSE: 자세한 결과는 "C\\: 사용자\\테스트\\AppData\\Local\\Temp\\Test-csreplica-3cb066b3-dd23-411a-8932-99f01c0f940c)에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4a19-133">VERBOSE: Detailed results can be found at "C:\\Users\\Testing\\AppData\\Local\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".</span></span>

<span data-ttu-id="c4a19-134">VERBOSE: 새 로그 파일 만들기</span><span class="sxs-lookup"><span data-stu-id="c4a19-134">VERBOSE: Creating new log file</span></span>

<span data-ttu-id="c4a19-135">"C:\\사용자\\테스트\\AppData\\로컬\\온도\\2\\테스트-csreplica-29fddb35-f56e-4e3c-8f4c-e</span><span class="sxs-lookup"><span data-stu-id="c4a19-135">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span></span>

<span data-ttu-id="c4a19-136">d3bd0e4a083 ".</span><span class="sxs-lookup"><span data-stu-id="c4a19-136">d3bd0e4a083.xml".</span></span>

<span data-ttu-id="c4a19-137">VERBOSE: 새 로그 파일 만들기</span><span class="sxs-lookup"><span data-stu-id="c4a19-137">VERBOSE: Creating new log file</span></span>

<span data-ttu-id="c4a19-138">"C:\\사용자\\테스트\\AppData\\로컬\\온도\\2\\테스트-csreplica-29fddb35-f56e-4e3c-8f4c-e</span><span class="sxs-lookup"><span data-stu-id="c4a19-138">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span></span>

<span data-ttu-id="c4a19-139">d3bd0e4a083 "</span><span class="sxs-lookup"><span data-stu-id="c4a19-139">d3bd0e4a083.html".</span></span>

<span data-ttu-id="c4a19-140">경고: 테스트-CsReplica에 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c4a19-140">WARNING: Test-CsReplica failed.</span></span>

<span data-ttu-id="c4a19-141">경고: 자세한 결과는 다음 위치에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4a19-141">WARNING: Detailed results can be found at</span></span>

<span data-ttu-id="c4a19-142">"C:\\사용자\\테스트\\AppData\\로컬\\온도\\2\\테스트-csreplica-29fddb35-f56e-4e3c-8f4c-e</span><span class="sxs-lookup"><span data-stu-id="c4a19-142">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span></span>

<span data-ttu-id="c4a19-143">d3bd0e4a083 "</span><span class="sxs-lookup"><span data-stu-id="c4a19-143">d3bd0e4a083.html".</span></span>

<span data-ttu-id="c4a19-144">테스트-CsReplica: 명령 실행 실패: 요청 된 레지스트리 액세스 권한 없음</span><span class="sxs-lookup"><span data-stu-id="c4a19-144">Test-CsReplica : Command execution failed: Requested registry access is not</span></span>

<span data-ttu-id="c4a19-145">있도록.</span><span class="sxs-lookup"><span data-stu-id="c4a19-145">allowed.</span></span>

<span data-ttu-id="c4a19-146">줄: 1 문자: 1</span><span class="sxs-lookup"><span data-stu-id="c4a19-146">At line:1 char:1</span></span>

<span data-ttu-id="c4a19-147">\+테스트-CsReplica-자세한 정보 표시</span><span class="sxs-lookup"><span data-stu-id="c4a19-147">\+ Test-CsReplica -Verbose</span></span>

\+ ~~~~~~~~~~~~~~~~~~~~~~~

<span data-ttu-id="c4a19-148">\+CategoryInfo: InvalidOperation: (:) \[테스트-csreplica\], Security</span><span class="sxs-lookup"><span data-stu-id="c4a19-148">\+ CategoryInfo : InvalidOperation: (:) \[Test-CsReplica\], Security</span></span>

<span data-ttu-id="c4a19-149">오류</span><span class="sxs-lookup"><span data-stu-id="c4a19-149">Exception</span></span>

<span data-ttu-id="c4a19-150">\+FullyQualifiedErrorId: ProcessingFailed, Microsoft. .Deploy</span><span class="sxs-lookup"><span data-stu-id="c4a19-150">\+ FullyQualifiedErrorId : ProcessingFailed,Microsoft.Rtc.Management.Deploy</span></span>

<span data-ttu-id="c4a19-151">주석. TestReplicaCmdlet</span><span class="sxs-lookup"><span data-stu-id="c4a19-151">ment.TestReplicaCmdlet</span></span>

<span data-ttu-id="c4a19-152">PS C:\\사용자\\테스트\></span><span class="sxs-lookup"><span data-stu-id="c4a19-152">PS C:\\Users\\Testing\></span></span>

<span data-ttu-id="c4a19-153">PS C:\\Test-csucwaconference\\-\> Targetfqdn "lynctest"를 테스트 하는 사용자</span><span class="sxs-lookup"><span data-stu-id="c4a19-153">PS C:\\Users\\Testing\> Test-CsUcwaConference -TargetFqdn "LyncTest.SelfHost.Corp.M</span></span>

<span data-ttu-id="c4a19-154">icrosoft.com "</span><span class="sxs-lookup"><span data-stu-id="c4a19-154">icrosoft.com"</span></span>

<span data-ttu-id="c4a19-155">경고: 지정한 정규화 된 자격에 대 한 등록자 포트 번호를 읽지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="c4a19-155">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="c4a19-156">FQDN (도메인 이름)</span><span class="sxs-lookup"><span data-stu-id="c4a19-156">domain name (FQDN).</span></span> <span data-ttu-id="c4a19-157">기본 등록자 포트 번호 사용</span><span class="sxs-lookup"><span data-stu-id="c4a19-157">Using default Registrar port number.</span></span> <span data-ttu-id="c4a19-158">오류</span><span class="sxs-lookup"><span data-stu-id="c4a19-158">Exception:</span></span>

<span data-ttu-id="c4a19-159">InvalidOperationException: 토폴로지에서 일치 하는 클러스터를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c4a19-159">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="c4a19-160">구독자</span><span class="sxs-lookup"><span data-stu-id="c4a19-160">at</span></span>

<span data-ttu-id="c4a19-161">SyntheticTransactions SipSyntheticTransaction TryRetri를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4a19-161">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="c4a19-162">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="c4a19-162">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="c4a19-163">Test-csucwaconference: 할당 된 테스트 사용자가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c4a19-163">Test-CsUcwaConference : There is no test user assigned for</span></span>

<span data-ttu-id="c4a19-164">\[LyncTest.SelfHost.Corp.Microsoft.com\]</span><span class="sxs-lookup"><span data-stu-id="c4a19-164">\[LyncTest.SelfHost.Corp.Microsoft.com\].</span></span> <span data-ttu-id="c4a19-165">테스트 사용자 구성을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4a19-165">Verify test user configuration.</span></span>

<span data-ttu-id="c4a19-166">줄: 1 문자: 1</span><span class="sxs-lookup"><span data-stu-id="c4a19-166">At line:1 char:1</span></span>

<span data-ttu-id="c4a19-167">\+Test-csucwaconference-TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"</span><span class="sxs-lookup"><span data-stu-id="c4a19-167">\+ Test-CsUcwaConference -TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"</span></span>

\+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

<span data-ttu-id="c4a19-168">\+CategoryInfo: ResourceUnavailable 사용할 수 없음: (:) \[Test-csucwaconference\]</span><span class="sxs-lookup"><span data-stu-id="c4a19-168">\+ CategoryInfo : ResourceUnavailable: (:) \[Test-CsUcwaConference\]</span></span>

<span data-ttu-id="c4a19-169">, InvalidOperationException</span><span class="sxs-lookup"><span data-stu-id="c4a19-169">, InvalidOperationException</span></span>

<span data-ttu-id="c4a19-170">\+FullyQualifiedErrorId: NotFoundTestUsers, Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c4a19-170">\+ FullyQualifiedErrorId : NotFoundTestUsers,Microsoft.Rtc.Management.Synth</span></span>

<span data-ttu-id="c4a19-171">eticTransactions</span><span class="sxs-lookup"><span data-stu-id="c4a19-171">eticTransactions.TestUcwaConferenceCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="c4a19-172">테스트가 실패 한 이유</span><span class="sxs-lookup"><span data-stu-id="c4a19-172">Reasons why the test might have failed</span></span>

<span data-ttu-id="c4a19-173">**테스트-CsReplica** 가 실패할 수 있는 일반적인 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c4a19-173">Here are some common reasons why **Test-CsReplica** might fail:</span></span>

  - <span data-ttu-id="c4a19-174">복제기 에이전트 및 중앙 로깅 에이전트 서비스에 더 이상 문제가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4a19-174">There may be a larger problem with the Replicator Agent and Centralized Logging Agent services</span></span>

  - <span data-ttu-id="c4a19-175">필요한 포트가 Windows 방화벽에서 열리지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4a19-175">The required ports may not be open in the Windows Firewall</span></span>

  - <span data-ttu-id="c4a19-176">필요한 Active Directory 및 로컬 컴퓨터 보안 그룹이 존재 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4a19-176">The necessary Active Directory and local computer security groups may not exist</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

