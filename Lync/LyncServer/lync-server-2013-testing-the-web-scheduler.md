---
title: 'Lync Server 2013: 웹 스케줄러 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing the Web scheduler
ms:assetid: 58e34058-1afa-42e3-9096-c4ea1954c237
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727304(v=OCS.15)
ms:contentKeyID: 63969603
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: beb4030a87302c8abaaba9418eaba06b831ed8d6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982276"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-web-scheduler-in-lync-server-2013"></a><span data-ttu-id="7c391-102">Lync Server 2013에서 웹 스케줄러 테스트</span><span class="sxs-lookup"><span data-stu-id="7c391-102">Testing the Web scheduler in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7c391-103">_**마지막으로 수정한 주제:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="7c391-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7c391-104">확인 일정</span><span class="sxs-lookup"><span data-stu-id="7c391-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="7c391-105">Daily</span><span class="sxs-lookup"><span data-stu-id="7c391-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c391-106">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="7c391-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="7c391-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7c391-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c391-108">권한이 필요 함</span><span class="sxs-lookup"><span data-stu-id="7c391-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="7c391-109">Lync Server Management Shell을 사용 하 여 로컬에서 실행 되는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c391-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="7c391-110">Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 사용자에 게 <strong>테스트 CsWebScheduler</strong> cmdlet을 실행할 수 있는 권한이 있는 RBAC 역할을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c391-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsWebScheduler</strong> cmdlet.</span></span> <span data-ttu-id="7c391-111">이 cmdlet을 사용할 수 있는 모든 RBAC 역할 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c391-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebScheduler&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="7c391-112">설명</span><span class="sxs-lookup"><span data-stu-id="7c391-112">Description</span></span>

<span data-ttu-id="7c391-113">**테스트-CsWebScheduler** cmdlet을 사용 하면 특정 사용자가 웹 스케줄러를 사용 하 여 모임을 예약할 수 있는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c391-113">The **Test-CsWebScheduler** cmdlet enables you to determine whether a specific user can schedule a meeting using the Web Scheduler.</span></span> <span data-ttu-id="7c391-114">웹 스케줄러에서는 Outlook을 실행 하지 않는 사용자가 온라인 모임을 예약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c391-114">The Web Scheduler enables users who are not running Outlook to schedule online meetings.</span></span> <span data-ttu-id="7c391-115">그 외에, Microsoft Lync Server 2010 리소스 키트에 포함 된 웹 스케줄러 도구에서 발견 된 기능을 통합 하는이 새로운 기능은 다음과 같은 사용자를 위해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c391-115">Among other things, this new feature (which incorporates the functionality found in the Web Scheduler tool that was included with the Microsoft Lync Server 2010 resource kit) enables users to:</span></span>

  - <span data-ttu-id="7c391-116">새 온라인 모임 예약</span><span class="sxs-lookup"><span data-stu-id="7c391-116">Schedule a new online meeting.</span></span>

  - <span data-ttu-id="7c391-117">자신이 예약한 모든 모임을 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c391-117">List all meetings that he or she has scheduled.</span></span>

  - <span data-ttu-id="7c391-118">기존 모임을 보거나 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c391-118">View/modify an existing meeting.</span></span>

  - <span data-ttu-id="7c391-119">기존 모임을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c391-119">Delete an existing meeting.</span></span>

  - <span data-ttu-id="7c391-120">미리 구성 된 SMTP 메일 서버를 사용 하 여 모임 참가자에 게 전자 메일 초대를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="7c391-120">Send an email invitation to meeting participants by using a preconfigured SMTP mail server.</span></span>

  - <span data-ttu-id="7c391-121">기존 회의에 참가 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c391-121">Join an existing conference.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="7c391-122">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="7c391-122">Running the test</span></span>

<span data-ttu-id="7c391-123">다음 예제에서는 풀 atl-cs-001.litwareinc.com에 대 한 웹 스케줄러를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c391-123">The following example verifies the Web Scheduler for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="7c391-124">이 명령은 풀 atl-cs-001.litwareinc.com에 대해 테스트 사용자가 정의 된 경우에만 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c391-124">This command will work only if test users are defined for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="7c391-125">그렇지 않은 경우이 명령은 첫 번째 테스트 사용자가 웹 스케줄러를 사용 하 여 온라인 모임을 예약할 수 있는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c391-125">If they have, then the command will determine whether the first test user can schedule an online meeting using the Web Scheduler.</span></span>

<span data-ttu-id="7c391-126">테스트 사용자가 정의 되지 않은 경우에는 어떤 사용자로 로그온 해야 하는지 알 수 없기 때문에 명령이 실패 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c391-126">If test users are not defined, then the command will fail because it won't know which user to log on as.</span></span> <span data-ttu-id="7c391-127">풀에 대해 테스트 사용자를 정의 하지 않은 경우에는 UserSipAddress 매개 변수와이 명령을 사용 하 여 로그온 할 때 사용할 사용자의 자격 증명을 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c391-127">If you have not defined test users for a pool, then you must include the UserSipAddress parameter and the credentials of the user the command should use when trying to log on.</span></span>

    Test-CsWebScheduler -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="7c391-128">다음 예제에 표시 된 명령은 특정 사용자 (litwareinc\\kenmeyer)의 기능을 테스트 하 여 웹 스케줄러를 사용 하 여 온라인 모임을 예약 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c391-128">The commands shown in the next example test the ability of a specific user (litwareinc\\kenmeyer) to schedule an online meeting using the Web scheduler.</span></span> <span data-ttu-id="7c391-129">이렇게 하려면이 예제의 첫 번째 명령은 **Get-Credential** cmdlet을 사용 하 여 사용자: 진구 Meyer의 이름 및 암호를 포함 하는 Windows PowerShell 명령줄 인터페이스 자격 증명 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7c391-129">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credential object that contains the name and password of the user Ken Meyer.</span></span> <span data-ttu-id="7c391-130">(로그온 이름 litwareinc\\kenmeyer는 매개 변수로 포함 되어 있기 때문에 Windows PowerShell 자격 증명 요청 대화 상자에는 관리자만: 진구 Meyer 계정에 대 한 암호를 입력 해야 합니다.) 그런 다음 결과 credential 개체는 $cred 1 이라는 변수에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c391-130">(Because the logon name litwareinc\\kenmeyer is included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Ken Meyer account.) The resulting credential object is then stored in a variable named $cred1.</span></span>

<span data-ttu-id="7c391-131">두 번째 명령은이 사용자가 풀 atl-cs-001.litwareinc.com에 로그온 할 수 있는지 여부를 확인 하 고 온라인 모임을 예약 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c391-131">The second command then checks whether this user can log on to the pool atl-cs-001.litwareinc.com and schedule an online meeting.</span></span> <span data-ttu-id="7c391-132">이 작업을 실행 하려면 다음 세 개의 매개 변수 (예: TargetFqdn (등록자 풀의 FQDN)를 사용 하 여 **테스트 CsWebScheduler** cmdlet이 호출 됩니다. UserCredential (Pilar Ackerman의 사용자 자격 증명을 포함 하는 Windows PowerShell 개체)입니다. 및 UserSipAddress (제공 된 사용자 자격 증명에 해당 하는 SIP 주소).</span><span class="sxs-lookup"><span data-stu-id="7c391-132">To run this task, the **Test-CsWebScheduler** cmdlet is called, together with three parameters: TargetFqdn (the FQDN of the Registrar pool); UserCredential (the Windows PowerShell object that contains Pilar Ackerman’s user credentials); and UserSipAddress (the SIP address that corresponds to the supplied user credentials).</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsWebScheduler -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="7c391-133">성공 또는 실패 확인</span><span class="sxs-lookup"><span data-stu-id="7c391-133">Determining success or failure</span></span>

<span data-ttu-id="7c391-134">웹 스케줄러가 올바르게 구성 되어 있는 경우 결과 속성이 **성공**으로 표시 된 것과 비슷한 출력을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c391-134">If the web scheduler is configured correctly , you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="7c391-135">대상 Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="7c391-135">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="7c391-136">대상 Uri: https://atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="7c391-136">Target Uri : https:// atl-cs-001.litwareinc.com.</span></span>

<span data-ttu-id="7c391-137">litwareinc.com:443/Scheduler</span><span class="sxs-lookup"><span data-stu-id="7c391-137">litwareinc.com:443/Scheduler</span></span>

<span data-ttu-id="7c391-138">결과: 성공</span><span class="sxs-lookup"><span data-stu-id="7c391-138">Result : Success</span></span>

<span data-ttu-id="7c391-139">대기 시간: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="7c391-139">Latency : 00:00:00</span></span>

<span data-ttu-id="7c391-140">오류 메시지:</span><span class="sxs-lookup"><span data-stu-id="7c391-140">Error Message :</span></span>

<span data-ttu-id="7c391-141">있게</span><span class="sxs-lookup"><span data-stu-id="7c391-141">Diagnosis :</span></span>

<span data-ttu-id="7c391-142">웹 스케줄러가 올바르게 구성 되어 있지 않으면 결과가 **실패로**표시 되 고 다음과 같은 오류 및 진단 속성에 추가 정보가 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c391-142">If the web scheduler is not configured correctly, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="7c391-143">경고: 정규화 된 정식 #b0에 대 한 등록자 포트 번호를 읽지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="7c391-143">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="7c391-144">도메인 이름 (FQDN).</span><span class="sxs-lookup"><span data-stu-id="7c391-144">domain name (FQDN).</span></span> <span data-ttu-id="7c391-145">기본 등록자 포트 번호를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c391-145">Using default Registrar port number.</span></span> <span data-ttu-id="7c391-146">발생</span><span class="sxs-lookup"><span data-stu-id="7c391-146">Exception:</span></span>

<span data-ttu-id="7c391-147">InvalidOperationException: 토폴로지에서 일치 하는 클러스터를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7c391-147">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="7c391-148">배포자</span><span class="sxs-lookup"><span data-stu-id="7c391-148">at</span></span>

<span data-ttu-id="7c391-149">SyntheticTransactions. SipSyntheticTransaction. TryRetri</span><span class="sxs-lookup"><span data-stu-id="7c391-149">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="7c391-150">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="7c391-150">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="7c391-151">대상 Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="7c391-151">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="7c391-152">대상 Uri:</span><span class="sxs-lookup"><span data-stu-id="7c391-152">Target Uri :</span></span>

<span data-ttu-id="7c391-153">결과: 실패</span><span class="sxs-lookup"><span data-stu-id="7c391-153">Result : Failure</span></span>

<span data-ttu-id="7c391-154">대기 시간: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="7c391-154">Latency : 00:00:00</span></span>

<span data-ttu-id="7c391-155">오류 메시지: 토폴로지에서 일치 하는 클러스터를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7c391-155">Error Message : No matching cluster found in topology.</span></span>

<span data-ttu-id="7c391-156">있게</span><span class="sxs-lookup"><span data-stu-id="7c391-156">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="7c391-157">테스트가 실패할 수 있는 이유</span><span class="sxs-lookup"><span data-stu-id="7c391-157">Reasons why the test might have failed</span></span>

<span data-ttu-id="7c391-158">**테스트-CsWebScheduler에서** 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7c391-158">Here are some common reasons why **Test-CsWebScheduler** might fail:</span></span>

  - <span data-ttu-id="7c391-159">잘못 된 매개 변수 값이 제공 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7c391-159">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="7c391-160">사용 하는 경우 선택적 매개 변수를 올바르게 구성 하거나 테스트에 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c391-160">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="7c391-161">선택적 매개 변수 없이 명령을 다시 실행 하 여 성공 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c391-161">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="7c391-162">웹 스케줄러가 잘못 구성 되었거나 아직 배포 되지 않은 경우에는이 명령이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c391-162">This command will fail if the Web Scheduler is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7c391-163">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7c391-163">See Also</span></span>


[<span data-ttu-id="7c391-164">Set-CsWebServer</span><span class="sxs-lookup"><span data-stu-id="7c391-164">Set-CsWebServer</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServer)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

