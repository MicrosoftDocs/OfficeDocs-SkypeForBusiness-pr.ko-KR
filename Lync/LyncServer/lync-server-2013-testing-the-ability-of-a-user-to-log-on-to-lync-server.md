---
title: 'Lync Server 2013: 사용자가 Lync Server에 로그온 하는 기능 테스트'
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
ms.openlocfilehash: 4fb1d0af8a5191c7e0af1ffe3319c426c116b586
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745468"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-ability-of-a-user-to-log-on-to-lync-server-2013"></a><span data-ttu-id="d7bad-102">사용자의 Lync Server 2013 로그온 기능 테스트</span><span class="sxs-lookup"><span data-stu-id="d7bad-102">Testing the ability of a user to log on to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d7bad-103">_**마지막으로 수정한 주제:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="d7bad-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d7bad-104">확인 일정</span><span class="sxs-lookup"><span data-stu-id="d7bad-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="d7bad-105">Daily</span><span class="sxs-lookup"><span data-stu-id="d7bad-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7bad-106">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="d7bad-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="d7bad-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d7bad-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7bad-108">권한이 필요 함</span><span class="sxs-lookup"><span data-stu-id="d7bad-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="d7bad-109">Lync Server Management Shell을 사용 하 여 로컬에서 실행 되는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7bad-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="d7bad-110">Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 사용자에 게는 테스트 CsRegistration cmdlet을 실행할 권한이 있는 RBAC 역할을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7bad-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsRegistration cmdlet.</span></span> <span data-ttu-id="d7bad-111">이 cmdlet을 사용할 수 있는 모든 RBAC 역할 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7bad-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsRegistration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="d7bad-112">설명</span><span class="sxs-lookup"><span data-stu-id="d7bad-112">Description</span></span>

<span data-ttu-id="d7bad-113">테스트-CsRegistration cmdlet을 사용 하 여 조직의 사용자가 Lync Server에 로그온 할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7bad-113">The Test-CsRegistration cmdlet enables you to verify that users in your organization can log on to Lync Server.</span></span> <span data-ttu-id="d7bad-114">테스트-CsRegistration을 실행할 때 cmdlet이 테스트 사용자에 게 Lync Server에 로그인 한 다음 성공한 경우 시스템에서 해당 테스트 사용자의 연결을 끊습니다.</span><span class="sxs-lookup"><span data-stu-id="d7bad-114">When you run Test-CsRegistration, the cmdlet attempts to sign in a test user to Lync Server and then, if it is successful, disconnects that test user from the system.</span></span> <span data-ttu-id="d7bad-115">이러한 모든 작업은 사용자 개입 없이, 실제 사용자에 게는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d7bad-115">All of this happens without any user interaction, and without affecting any actual users.</span></span> <span data-ttu-id="d7bad-116">예를 들어 테스트 계정 sip:kenmyer@litwareinc.com 실제 Lync Server 계정이 있는 실제 사용자에 해당 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7bad-116">For example, suppose that the test account sip:kenmyer@litwareinc.com corresponds to a real user who has a real Lync Server account.</span></span> <span data-ttu-id="d7bad-117">이 경우 실제: 진구 Myer에 대 한 장애 없이 테스트를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7bad-117">In that case, the test will be conducted without any disruption to the real Ken Myer.</span></span> <span data-ttu-id="d7bad-118">: 진구 Myer 테스트 계정이 시스템에서 로그 오프할 때: 진구 Myer 해당 사용자는 로그온 된 상태로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7bad-118">When the Ken Myer test account logs off from the system, Ken Myer the person will remain logged on.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="d7bad-119">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="d7bad-119">Running the test</span></span>

<span data-ttu-id="d7bad-120">테스트-CsRegistration cmdlet은 미리 구성 된 테스트 계정 (Lync Server 테스트 실행을 위한 테스트 계정 설정 참조) 또는 Lync Server에 대해 사용 하도록 설정 된 모든 사용자의 계정을 사용 하 여 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7bad-120">The Test-CsRegistration cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="d7bad-121">테스트 계정을 사용 하 여이 검사를 실행 하려면 테스트 중인 Lync Server 등록자 풀의 FQDN만 지정 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7bad-121">To run this check using a test account, you just have to specify the FQDN of the Lync Server Registrar pool being tested.</span></span> <span data-ttu-id="d7bad-122">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d7bad-122">For example:</span></span>

    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="d7bad-123">실제 사용자 계정을 사용 하 여이 검사를 실행 하려면 먼저 계정 이름과 암호를 포함 하는 Windows PowerShell 자격 증명 개체를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7bad-123">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="d7bad-124">그런 다음 테스트-CsRegistration을 호출할 때 해당 자격 증명 개체와 해당 계정에 할당 된 SIP 주소를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7bad-124">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsRegistration:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="d7bad-125">자세한 내용은 [테스트 CsRegistration](https://docs.microsoft.com/powershell/module/skype/Test-CsRegistration) cmdlet에 대 한 도움말 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d7bad-125">For more information, see the Help documentation for the [Test-CsRegistration](https://docs.microsoft.com/powershell/module/skype/Test-CsRegistration) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="d7bad-126">성공 또는 실패 확인</span><span class="sxs-lookup"><span data-stu-id="d7bad-126">Determining success or failure</span></span>

<span data-ttu-id="d7bad-127">지정 된 사용자가 Lync Server에 로그온 한 다음 로그 오프할 수 있는 경우 결과 속성이 성공으로 표시 된 것과 비슷한 출력을 받게 됩니다 **.**</span><span class="sxs-lookup"><span data-stu-id="d7bad-127">If the specified user can log on to (and then log off from) Lync Server, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="d7bad-128">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="d7bad-128">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="d7bad-129">결과: 성공</span><span class="sxs-lookup"><span data-stu-id="d7bad-129">Result : Success</span></span>

<span data-ttu-id="d7bad-130">대기 시간: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="d7bad-130">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="d7bad-131">오류</span><span class="sxs-lookup"><span data-stu-id="d7bad-131">Error :</span></span>

<span data-ttu-id="d7bad-132">있게</span><span class="sxs-lookup"><span data-stu-id="d7bad-132">Diagnosis :</span></span>

<span data-ttu-id="d7bad-133">지정 된 사용자가 로그인 하거나 로그 아웃할 수 없는 경우에는 결과가 실패로 표시 되 고 오류 및 진단 속성에 추가 정보가 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7bad-133">If the specified user can't log in or log out, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="d7bad-134">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="d7bad-134">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="d7bad-135">결과: 실패</span><span class="sxs-lookup"><span data-stu-id="d7bad-135">Result : Failure</span></span>

<span data-ttu-id="d7bad-136">대기 시간: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="d7bad-136">Latency : 00:00:00</span></span>

<span data-ttu-id="d7bad-137">오류: 404, 찾을 수 없음</span><span class="sxs-lookup"><span data-stu-id="d7bad-137">Error : 404, Not Found</span></span>

<span data-ttu-id="d7bad-138">진단: ErrorCode = 1003, source = atl-cs-001. litwareinc, 이유 = 사용자가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d7bad-138">Diagnosis : ErrorCode=1003,source=atl-cs-001.litwareinc.com,Reason=User does</span></span>

<span data-ttu-id="d7bad-139">없음</span><span class="sxs-lookup"><span data-stu-id="d7bad-139">not exist</span></span>

<span data-ttu-id="d7bad-140">Microsoft DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="d7bad-140">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="d7bad-141">예를 들어 이전 출력은 지정 된 사용자를 찾을 수 없기 때문에 테스트가 실패 했다는 것을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d7bad-141">For example, the previous output states that the test failed because the specified user couldn't be found.</span></span> <span data-ttu-id="d7bad-142">이 명령을 실행 하 여 SIP 주소가 유효한 지 (그리고 sip 주소를 사용 하도록 설정 된 사용자에 게 있는지 여부)를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7bad-142">You can determine whether or not a SIP address is valid (and whether the user assigned that SIP address is enabled for Lync Server) by running this command:</span></span>

    Get-CsUser "sip:kenmyer@litwareinc.com"

<span data-ttu-id="d7bad-143">테스트-CsRegistration이 실패 하는 경우 다음과 같이 Verbose 매개 변수를 포함 하 여 테스트를 다시 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7bad-143">If Test-CsRegistration fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsRegistration -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="d7bad-144">Verbose 매개 변수를 포함 하는 경우 테스트-CsRegistration은 지정 된 사용자가 Lync Server에 로그온 하는 기능을 확인할 때 시도한 각 작업의 단계별 계정을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7bad-144">When the Verbose parameter is included, Test-CsRegistration will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="d7bad-145">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d7bad-145">For example:</span></span>

<span data-ttu-id="d7bad-146">자세한 정보: ' Register ' 활동을 시작 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d7bad-146">VERBOSE: 'Register' activity started.</span></span>

<span data-ttu-id="d7bad-147">등록 요청 전송 중:</span><span class="sxs-lookup"><span data-stu-id="d7bad-147">Sending Registration request:</span></span>

<span data-ttu-id="d7bad-148">대상 Fqdn = atl-cs-011.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="d7bad-148">Target Fqdn = atl-cs-011.litwareinc.com</span></span>

<span data-ttu-id="d7bad-149">사용자 Sip 주소 = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="d7bad-149">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="d7bad-150">등록자 포트 = 5061.</span><span class="sxs-lookup"><span data-stu-id="d7bad-150">Registrar Port = 5061.</span></span>

<span data-ttu-id="d7bad-151">인증 유형 ' 신뢰 됨 '이 선택 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d7bad-151">Auth Type 'Trusted' is selected.</span></span>

<span data-ttu-id="d7bad-152">' 종점이 등록할 수 없는 ' 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="d7bad-152">An exception 'The endpoint is unable to register.</span></span> <span data-ttu-id="d7bad-153">워크플로 SyntheticTransactions가 실행 되는 동안 특정 이유로 인해 ErrorCode에 대 한 오류 발생을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="d7bad-153">See the ErrorCode for specific reason' occurred during Workflow Microsoft.Rtc.SyntheticTransactions.Workflow.STRegistrerWorkflow execution.</span></span>

<span data-ttu-id="d7bad-154">예외 호출 스택: Microsoft SipAsyncResult'1. ThrowIfFailed ()</span><span class="sxs-lookup"><span data-stu-id="d7bad-154">Exception Call Stack: at Microsoft.Rtc.Signaling.SipAsyncResult'1.ThrowIfFailed()</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="d7bad-155">테스트가 실패할 수 있는 이유</span><span class="sxs-lookup"><span data-stu-id="d7bad-155">Reasons why the test might have failed</span></span>

<span data-ttu-id="d7bad-156">테스트-CsRegistration이 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d7bad-156">Here are some common reasons why Test-CsRegistration might fail:</span></span>

  - <span data-ttu-id="d7bad-157">잘못 된 사용자 계정을 지정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d7bad-157">You specified an incorrect user account.</span></span> <span data-ttu-id="d7bad-158">다음과 같은 명령을 실행 하 여 사용자 계정이 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7bad-158">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="d7bad-159">사용자 계정이 올바르지만 현재 Lync Server에서 계정을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d7bad-159">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="d7bad-160">Lync Server에 대해 사용자 계정이 설정 되어 있는지 확인 하려면 다음과 같은 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7bad-160">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="d7bad-161">Enabled 속성이 False로 설정 된 경우 사용자가 현재 Lync Server에 대해 사용 하도록 설정 되어 있지 않음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7bad-161">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="d7bad-162">잘못 된 등록자 풀을 지정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d7bad-162">You specified an incorrect Registrar pool.</span></span> <span data-ttu-id="d7bad-163">다음 명령을 사용 하 여 등록자 풀의 Fqdn을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7bad-163">You can return the FQDNs of your Registrar pools by using this command:</span></span>
    
        Get-CsService -Registrar | Select-Object PoolFqdn

  - <span data-ttu-id="d7bad-164">현재 등록자 풀을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d7bad-164">The Registrar pool is currently not available.</span></span> <span data-ttu-id="d7bad-165">풀을 ping 하 여 응답 여부를 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="d7bad-165">Try pinging the pool to see whether it responds:</span></span>
    
        ping atl-cs-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

