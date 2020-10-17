---
title: 'Lync Server 2013: 사용자가 Lync Server에 로그온 할 수 있는지 테스트'
description: 'Lync Server 2013: 사용자가 Lync Server에 로그온 할 수 있는지 여부를 테스트 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the ability of a user to log on to Lync Server
ms:assetid: d9cd0f9b-6ef2-4050-a4ca-263c5afa93ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743841(v=OCS.15)
ms:contentKeyID: 63969655
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b86ae3e490af0b361799ed5fb3f56ed4de42c82
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556214"
---
# <a name="testing-the-ability-of-a-user-to-log-on-to-lync-server-2013"></a><span data-ttu-id="144d7-103">Lync Server 2013에 로그온 하는 사용자 기능 테스트</span><span class="sxs-lookup"><span data-stu-id="144d7-103">Testing the ability of a user to log on to Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="144d7-104">_**마지막으로 수정 된 항목:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="144d7-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="144d7-105">확인 일정</span><span class="sxs-lookup"><span data-stu-id="144d7-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="144d7-106">매일</span><span class="sxs-lookup"><span data-stu-id="144d7-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="144d7-107">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="144d7-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="144d7-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="144d7-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="144d7-109">필요한 권한</span><span class="sxs-lookup"><span data-stu-id="144d7-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="144d7-110">Lync Server 관리 셸을 사용 하 여 로컬로 실행 하는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="144d7-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="144d7-111">Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 사용자에 게 Test-CsRegistration cmdlet을 실행 하는 권한이 있는 RBAC 역할을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="144d7-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsRegistration cmdlet.</span></span> <span data-ttu-id="144d7-112">이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="144d7-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsRegistration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="144d7-113">설명</span><span class="sxs-lookup"><span data-stu-id="144d7-113">Description</span></span>

<span data-ttu-id="144d7-114">Test-CsRegistration cmdlet을 사용 하 여 조직의 사용자가 Lync Server에 로그온 할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="144d7-114">The Test-CsRegistration cmdlet enables you to verify that users in your organization can log on to Lync Server.</span></span> <span data-ttu-id="144d7-115">테스트-CsRegistration을 실행할 때 cmdlet은 테스트 사용자에 게 Lync Server에 로그인을 시도 하 고 성공한 경우 시스템에서 해당 테스트 사용자의 연결을 끊습니다.</span><span class="sxs-lookup"><span data-stu-id="144d7-115">When you run Test-CsRegistration, the cmdlet attempts to sign in a test user to Lync Server and then, if it is successful, disconnects that test user from the system.</span></span> <span data-ttu-id="144d7-116">이 작업은 모두 사용자 상호 작용 없이, 실제 사용자에게 영향을 미치지 않고 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="144d7-116">All of this happens without any user interaction, and without affecting any actual users.</span></span> <span data-ttu-id="144d7-117">예를 들어 테스트 계정 sip:kenmyer@litwareinc.com 실제 Lync Server 계정을 가진 실제 사용자에 해당 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="144d7-117">For example, suppose that the test account sip:kenmyer@litwareinc.com corresponds to a real user who has a real Lync Server account.</span></span> <span data-ttu-id="144d7-118">이 경우 실제 Ken Myer를 방해하지 않고 테스트가 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="144d7-118">In that case, the test will be conducted without any disruption to the real Ken Myer.</span></span> <span data-ttu-id="144d7-119">Ken Myer 테스트 계정이 시스템에서 로그오프해도 사람 Ken Myer는 계속 로그온 상태로 남아 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="144d7-119">When the Ken Myer test account logs off from the system, Ken Myer the person will remain logged on.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="144d7-120">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="144d7-120">Running the test</span></span>

<span data-ttu-id="144d7-121">Test-CsRegistration cmdlet은 미리 구성 된 테스트 계정 (Lync Server 테스트 실행을 위한 테스트 계정 설정 참조) 또는 Lync Server를 사용 하도록 설정 된 사용자의 계정 중 하나를 사용 하 여 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="144d7-121">The Test-CsRegistration cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="144d7-122">테스트 계정을 사용 하 여이 검사를 실행 하려면 테스트할 Lync Server 등록자 풀의 FQDN만 지정 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="144d7-122">To run this check using a test account, you just have to specify the FQDN of the Lync Server Registrar pool being tested.</span></span> <span data-ttu-id="144d7-123">예제:</span><span class="sxs-lookup"><span data-stu-id="144d7-123">For example:</span></span>

    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="144d7-124">실제 사용자 계정을 사용 하 여이 검사를 실행 하려면 먼저 계정 이름과 암호가 포함 된 Windows PowerShell 자격 증명 개체를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="144d7-124">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="144d7-125">그런 다음 테스트-CsRegistration을 호출할 때 해당 자격 증명 개체와 해당 계정에 할당 된 SIP 주소를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="144d7-125">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsRegistration:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="144d7-126">자세한 내용은 [테스트-CsRegistration](https://docs.microsoft.com/powershell/module/skype/Test-CsRegistration) cmdlet에 대 한 도움말 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="144d7-126">For more information, see the Help documentation for the [Test-CsRegistration](https://docs.microsoft.com/powershell/module/skype/Test-CsRegistration) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="144d7-127">성공 또는 실패 확인</span><span class="sxs-lookup"><span data-stu-id="144d7-127">Determining success or failure</span></span>

<span data-ttu-id="144d7-128">지정 된 사용자가 Lync Server에 로그온 한 다음 로그 오프할 수 있는 경우 Result 속성이 Success로 표시 된 것과 비슷한 출력을 받게 됩니다 **.**</span><span class="sxs-lookup"><span data-stu-id="144d7-128">If the specified user can log on to (and then log off from) Lync Server, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="144d7-129">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="144d7-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="144d7-130">결과: 성공</span><span class="sxs-lookup"><span data-stu-id="144d7-130">Result : Success</span></span>

<span data-ttu-id="144d7-131">대기 시간: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="144d7-131">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="144d7-132">오류</span><span class="sxs-lookup"><span data-stu-id="144d7-132">Error :</span></span>

<span data-ttu-id="144d7-133">진단을</span><span class="sxs-lookup"><span data-stu-id="144d7-133">Diagnosis :</span></span>

<span data-ttu-id="144d7-134">지정 된 사용자가 로그인 하거나 로그 아웃할 수 없으면 결과가 실패로 표시 되 고 오류 및 진단 속성에 추가 정보가 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="144d7-134">If the specified user can't log in or log out, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="144d7-135">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="144d7-135">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="144d7-136">결과: 실패</span><span class="sxs-lookup"><span data-stu-id="144d7-136">Result : Failure</span></span>

<span data-ttu-id="144d7-137">대기 시간: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="144d7-137">Latency : 00:00:00</span></span>

<span data-ttu-id="144d7-138">오류: 404, 찾을 수 없음</span><span class="sxs-lookup"><span data-stu-id="144d7-138">Error : 404, Not Found</span></span>

<span data-ttu-id="144d7-139">진단: ErrorCode = 1003, source = atl-cs-litwareinc, 이유 = 사용자가 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="144d7-139">Diagnosis : ErrorCode=1003,source=atl-cs-001.litwareinc.com,Reason=User does</span></span>

<span data-ttu-id="144d7-140">존재 하지 않음</span><span class="sxs-lookup"><span data-stu-id="144d7-140">not exist</span></span>

<span data-ttu-id="144d7-141">Microsoft DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="144d7-141">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="144d7-142">예를 들어 위의 출력에서는 지정 된 사용자를 찾을 수 없기 때문에 테스트가 실패 했다는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="144d7-142">For example, the previous output states that the test failed because the specified user couldn't be found.</span></span> <span data-ttu-id="144d7-143">다음 명령을 실행 하 여 SIP 주소가 유효한 지 여부와 해당 SIP 주소를 할당 한 사용자가 Lync Server에 대해 사용 되는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="144d7-143">You can determine whether or not a SIP address is valid (and whether the user assigned that SIP address is enabled for Lync Server) by running this command:</span></span>

    Get-CsUser "sip:kenmyer@litwareinc.com"

<span data-ttu-id="144d7-144">Test-CsRegistration 실패 하면 다음 시간에 Verbose 매개 변수를 포함 하 여 테스트를 다시 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="144d7-144">If Test-CsRegistration fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsRegistration -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="144d7-145">Verbose 매개 변수를 포함 하면 Test-CsRegistration는 지정 된 사용자가 Lync Server에 로그온 할 수 있는지 확인할 때 시도한 각 작업의 단계별 계정을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="144d7-145">When the Verbose parameter is included, Test-CsRegistration will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="144d7-146">예제:</span><span class="sxs-lookup"><span data-stu-id="144d7-146">For example:</span></span>

<span data-ttu-id="144d7-147">VERBOSE: ' 등록 ' 활동이 시작 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="144d7-147">VERBOSE: 'Register' activity started.</span></span>

<span data-ttu-id="144d7-148">등록 요청을 보내는 중:</span><span class="sxs-lookup"><span data-stu-id="144d7-148">Sending Registration request:</span></span>

<span data-ttu-id="144d7-149">대상 Fqdn = atl-cs-011.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="144d7-149">Target Fqdn = atl-cs-011.litwareinc.com</span></span>

<span data-ttu-id="144d7-150">사용자 Sip 주소 = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="144d7-150">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="144d7-151">등록자 포트 = 5061.</span><span class="sxs-lookup"><span data-stu-id="144d7-151">Registrar Port = 5061.</span></span>

<span data-ttu-id="144d7-152">' 신뢰할 수 있음 ' 인증 유형을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="144d7-152">Auth Type 'Trusted' is selected.</span></span>

<span data-ttu-id="144d7-153">' 끝점이 등록할 수 없습니다. ' 예외가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="144d7-153">An exception 'The endpoint is unable to register.</span></span> <span data-ttu-id="144d7-154">SyntheticTransactions 실행 중에 특정 이유로 인해 발생 한 오류에 대 한 ErrorCode를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="144d7-154">See the ErrorCode for specific reason' occurred during Workflow Microsoft.Rtc.SyntheticTransactions.Workflow.STRegistrerWorkflow execution.</span></span>

<span data-ttu-id="144d7-155">예외 호출 스택: SipAsyncResult'1에서 ThrowIfFailed ()</span><span class="sxs-lookup"><span data-stu-id="144d7-155">Exception Call Stack: at Microsoft.Rtc.Signaling.SipAsyncResult'1.ThrowIfFailed()</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="144d7-156">테스트가 실패 한 이유</span><span class="sxs-lookup"><span data-stu-id="144d7-156">Reasons why the test might have failed</span></span>

<span data-ttu-id="144d7-157">Test-CsRegistration 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="144d7-157">Here are some common reasons why Test-CsRegistration might fail:</span></span>

  - <span data-ttu-id="144d7-158">잘못 된 사용자 계정을 지정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="144d7-158">You specified an incorrect user account.</span></span> <span data-ttu-id="144d7-159">다음과 같은 명령을 실행 하 여 사용자 계정이 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="144d7-159">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="144d7-160">사용자 계정이 올바르지만 해당 계정이 Lync Server에 대해 현재 사용 하도록 설정 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="144d7-160">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="144d7-161">사용자 계정이 Lync Server에 대해 사용 하도록 설정 되어 있는지 확인 하려면 다음과 같은 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="144d7-161">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="144d7-162">Enabled 속성을 False로 설정 하면 사용자가 현재 Lync Server를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="144d7-162">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="144d7-163">잘못 된 등록자 풀을 지정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="144d7-163">You specified an incorrect Registrar pool.</span></span> <span data-ttu-id="144d7-164">다음 명령을 사용 하 여 등록자 풀의 Fqdn을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="144d7-164">You can return the FQDNs of your Registrar pools by using this command:</span></span>
    
        Get-CsService -Registrar | Select-Object PoolFqdn

  - <span data-ttu-id="144d7-165">등록자 풀은 현재 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="144d7-165">The Registrar pool is currently not available.</span></span> <span data-ttu-id="144d7-166">풀에 ping을 사용해 서 응답 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="144d7-166">Try pinging the pool to see whether it responds:</span></span>
    
        ping atl-cs-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

