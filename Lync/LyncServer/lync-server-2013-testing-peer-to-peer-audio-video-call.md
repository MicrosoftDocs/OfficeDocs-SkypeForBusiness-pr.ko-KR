---
title: 'Lync Server 2013: 피어-투-피어 오디오/비디오 통화 테스트'
description: 'Lync Server 2013: 피어-투-피어 오디오/비디오 통화를 테스트 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing peer to peer audio/video call
ms:assetid: 95eb3693-b866-4652-bc45-9b75fdb40b49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743835(v=OCS.15)
ms:contentKeyID: 63969627
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03bab69d926a99c091a510ce64b78dbf505d4cbc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556294"
---
# <a name="testing-peer-to-peer-audiovideo-call-in-lync-server-2013"></a><span data-ttu-id="12781-103">Lync Server 2013에서 피어 투 피어 오디오/비디오 통화 테스트</span><span class="sxs-lookup"><span data-stu-id="12781-103">Testing peer to peer audio/video call in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12781-104">_**마지막으로 수정 된 항목:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="12781-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="12781-105">확인 일정</span><span class="sxs-lookup"><span data-stu-id="12781-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="12781-106">매일</span><span class="sxs-lookup"><span data-stu-id="12781-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12781-107">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="12781-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="12781-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="12781-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12781-109">필요한 권한</span><span class="sxs-lookup"><span data-stu-id="12781-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="12781-110">Lync Server 관리 셸을 사용 하 여 로컬로 실행 하는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="12781-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="12781-111">Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 사용자에 게 Test-CsP2PAV cmdlet을 실행 하는 권한이 있는 RBAC 역할을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="12781-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsP2PAV cmdlet.</span></span> <span data-ttu-id="12781-112">이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="12781-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsP2PAV&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="12781-113">설명</span><span class="sxs-lookup"><span data-stu-id="12781-113">Description</span></span>

<span data-ttu-id="12781-114">Test-CsP2PAV은 테스트 사용자 쌍이 피어 투 피어 A/V 대화에 참가할 수 있는지 여부를 확인 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="12781-114">Test-CsP2PAV is used to determine whether a pair of test users can participate in a peer-to-peer A/V conversation.</span></span> <span data-ttu-id="12781-115">이 시나리오를 테스트 하기 위해 두 사용자에 게 Lync Server에 로그온 하 여 cmdlet이 해제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="12781-115">To test this scenario, the cmdlet starts off by logging on the two users to Lync Server.</span></span> <span data-ttu-id="12781-116">두 사용자 모두 로그온에 성공하면 첫 번째 사용자가 두 번째 사용자를 A/V 통화에 참가하도록 초대합니다.</span><span class="sxs-lookup"><span data-stu-id="12781-116">Assuming that the two logons succeed, the first user then invites the second user to join an A/V call.</span></span> <span data-ttu-id="12781-117">두 번째 사용자가 통화를 수락하고, 두 사용자 간에 연결이 테스트되고, 통화가 종료된 후 테스트 사용자가 시스템에서 로그오프됩니다.</span><span class="sxs-lookup"><span data-stu-id="12781-117">The second user accepts the call, the connection between the two users is tested, and then the call is ended and the test users are logged off from the system.</span></span>

<span data-ttu-id="12781-118">Test-CsP2PAV는 실제로 A/V 통화를 수행 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="12781-118">Test-CsP2PAV does not actually conduct an A/V call.</span></span> <span data-ttu-id="12781-119">테스트 사용자 간에는 멀티미디어 정보가 교환 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="12781-119">Multimedia information is not exchanged between the test users.</span></span> <span data-ttu-id="12781-120">대신, cmdlet은 적절 한 연결이 가능 하며 두 사용자가 이러한 통화를 수행할 수 있는지 확인 하기만 합니다.</span><span class="sxs-lookup"><span data-stu-id="12781-120">Instead, the cmdlet merely verifies that the appropriate connections can be made and that the two users can conduct such a call.</span></span>

<span data-ttu-id="12781-121">자세한 내용은 [test-csp2pav](https://docs.microsoft.com/powershell/module/skype/Test-CsP2PAV) cmdlet에 대 한 도움말 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="12781-121">For more information, see the Help documentation for the [Test-CsP2PAV](https://docs.microsoft.com/powershell/module/skype/Test-CsP2PAV) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="12781-122">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="12781-122">Running the test</span></span>

<span data-ttu-id="12781-123">Test-CsP2PAV cmdlet은 미리 구성 된 테스트 계정 쌍 (Lync Server 테스트 실행을 위한 테스트 계정 설정 참조) 또는 Lync Server를 사용 하도록 설정 된 두 사용자의 계정 중 하나를 사용 하 여 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12781-123">The Test-CsP2PAV cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="12781-124">테스트 계정을 사용 하 여이 검사를 실행 하려면 테스트할 Lync Server 풀의 FQDN만 지정 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="12781-124">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="12781-125">예제:</span><span class="sxs-lookup"><span data-stu-id="12781-125">For example:</span></span>

    Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="12781-126">실제 사용자 계정을 사용 하 여이 검사를 실행 하려면 각 계정에 대해 두 Lync Server 자격 증명 개체 (계정 이름과 암호가 포함 된 개체)를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="12781-126">To run this check using actual user accounts, you must create two Lync Server credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="12781-127">그런 다음 Test-csp2pav를 호출할 때 이러한 자격 증명 개체와 두 계정의 SIP 주소를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="12781-127">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsP2PAV:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="12781-128">성공 또는 실패 확인</span><span class="sxs-lookup"><span data-stu-id="12781-128">Determining success or failure</span></span>

<span data-ttu-id="12781-129">두 테스트 사용자가 피어 투 피어 A/V 통화를 완료할 수 있으면 Result 속성이 Success로 표시 된 것과 비슷한 출력을 받게 됩니다 **.**</span><span class="sxs-lookup"><span data-stu-id="12781-129">If the two test users can complete a peer-to-peer A/V call, then you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="12781-130">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="12781-130">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="12781-131">결과: 성공</span><span class="sxs-lookup"><span data-stu-id="12781-131">Result : Success</span></span>

<span data-ttu-id="12781-132">대기 시간: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="12781-132">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="12781-133">오류</span><span class="sxs-lookup"><span data-stu-id="12781-133">Error :</span></span>

<span data-ttu-id="12781-134">진단을</span><span class="sxs-lookup"><span data-stu-id="12781-134">Diagnosis :</span></span>

<span data-ttu-id="12781-135">테스트 사용자가 통화를 완료할 수 없는 경우 결과가 실패로 표시 되 고 오류 및 진단 속성에 추가 정보가 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="12781-135">If the test users can't complete the call, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="12781-136">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="12781-136">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="12781-137">결과: 실패</span><span class="sxs-lookup"><span data-stu-id="12781-137">Result : Failure</span></span>

<span data-ttu-id="12781-138">대기 시간: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="12781-138">Latency : 00:00:00</span></span>

<span data-ttu-id="12781-139">오류: 480, 일시적으로 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="12781-139">Error : 480, Temporarily Unavailable</span></span>

<span data-ttu-id="12781-140">진단: ErrorCode = 15030, Source = atl-cs-001. litwareinc, 이유 = 실패</span><span class="sxs-lookup"><span data-stu-id="12781-140">Diagnosis : ErrorCode=15030,Source=atl-cs-001.litwareinc.com,Reason=Failed</span></span>

<span data-ttu-id="12781-141">Exchange Server로 경로를 조정 하려면</span><span class="sxs-lookup"><span data-stu-id="12781-141">to route to Exchange Server</span></span>

<span data-ttu-id="12781-142">Microsoft DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="12781-142">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="12781-143">예를 들어 위의 출력에서는 Microsoft Exchange 서버에 연결할 수 없기 때문에 테스트가 실패 했다는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="12781-143">For example, the previous output states that the test failed because the Microsoft Exchange Server couldn't be contacted.</span></span> <span data-ttu-id="12781-144">이 오류 메시지는 일반적으로 Exchange 통합 메시징의 구성에 문제가 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="12781-144">This error message typically indicates a problem the configuration of Exchange Unified Messaging.</span></span>

<span data-ttu-id="12781-145">Test-CsP2PAV 실패 하면 다음 시간에 Verbose 매개 변수를 포함 하 여 테스트를 다시 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12781-145">If Test-CsP2PAV fails then you might want to rerun the test, this time including the Verbose parameter:</span></span>

<span data-ttu-id="12781-146">Test-CsP2PAV-TargetFqdn "atl-cs-001.litwareinc.com"-Verbose</span><span class="sxs-lookup"><span data-stu-id="12781-146">Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose</span></span>

<span data-ttu-id="12781-147">Verbose 매개 변수를 포함 하면 Test-CsP2PAV에서 지정 된 사용자가 Lync Server에 로그온 할 수 있는지 확인 한 각 작업의 단계별 계정을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="12781-147">When the Verbose parameter is included, Test-CsP2PAV will return a step-by-step account of each action it tried as it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="12781-148">예를 들어 다음과 같은 진단으로 테스트가 실패 했다고 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="12781-148">For example, suppose that your test failed with the following Diagnosis:</span></span>

<span data-ttu-id="12781-149">ErrorCode = 6003, Source = atl-cs-litwareinc, Reason = dialog 요청이 지원 되지 않음</span><span class="sxs-lookup"><span data-stu-id="12781-149">ErrorCode=6003,Source=atl-cs-001.litwareinc.com,Reason=Unsupported out of dialog request</span></span>

<span data-ttu-id="12781-150">Test-CsP2PAV를 다시 실행 하 고 Verbose 매개 변수를 포함 하면 다음과 같은 출력을 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="12781-150">If you rerun Test-CsP2PAV and include the Verbose parameter, you'll get output similar to this:</span></span>

<span data-ttu-id="12781-151">VERBOSE: ' 등록 ' 활동이 시작 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="12781-151">VERBOSE: 'Register' activity started.</span></span>

<span data-ttu-id="12781-152">등록 요청을 보내는 중:</span><span class="sxs-lookup"><span data-stu-id="12781-152">Sending Registration request:</span></span>

<span data-ttu-id="12781-153">대상 Fqdn = atl-cs-011.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="12781-153">Target Fqdn = atl-cs-011.litwareinc.com</span></span>

<span data-ttu-id="12781-154">사용자 Sip 주소 = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="12781-154">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="12781-155">등록자 포트 = 5062.</span><span class="sxs-lookup"><span data-stu-id="12781-155">Registrar Port = 5062.</span></span>

<span data-ttu-id="12781-156">인증 유형 ' IWA '이 선택 됩니다.</span><span class="sxs-lookup"><span data-stu-id="12781-156">Auth Type 'IWA' is selected.</span></span>

<span data-ttu-id="12781-157">' 끝점을 등록할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="12781-157">An exception 'The endpoint was unable to register.</span></span> <span data-ttu-id="12781-158">구체적인 이유로 ErrorCode를 참조 하세요. '</span><span class="sxs-lookup"><span data-stu-id="12781-158">See the ErrorCode for specific reason.'</span></span> <span data-ttu-id="12781-159">SyntheticTransactions을 STP2PAVWorkflow 실행 하는 동안 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="12781-159">occurred during workflow Microsoft.Rtc.SyntheticTransactions.Workflows.STP2PAVWorkflow execution.</span></span>

<span data-ttu-id="12781-160">즉시 확인 하지 못할 수도 있지만 출력을 주의 깊게 살펴보면 잘못 된 등록자 포트 (포트 5062)가 지정 되었음을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12781-160">Although it might not be immediately obvious, if you examine the output carefully you’ll see that an incorrect Registrar port (port 5062) was specified.</span></span> <span data-ttu-id="12781-161">이로 인해 테스트가 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="12781-161">In turn, that caused the test to fail.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="12781-162">테스트가 실패 한 이유</span><span class="sxs-lookup"><span data-stu-id="12781-162">Reasons why the test might have failed</span></span>

<span data-ttu-id="12781-163">Test-CsP2PAV 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="12781-163">Here are some common reasons why Test-CsP2PAV might fail:</span></span>

  - <span data-ttu-id="12781-164">잘못 된 사용자 계정을 지정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="12781-164">You specified a user account that is not valid.</span></span> <span data-ttu-id="12781-165">다음과 같은 명령을 실행 하 여 사용자 계정이 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12781-165">You can verify that a user account exists by running a command similar to this:</span></span>
    
    <span data-ttu-id="12781-166">Get-CsUser "sip:kenmyer@litwareinc.com"</span><span class="sxs-lookup"><span data-stu-id="12781-166">Get-CsUser "sip:kenmyer@litwareinc.com"</span></span>

  - <span data-ttu-id="12781-167">사용자 계정이 올바르지만 해당 계정이 Lync Server에 대해 현재 사용 하도록 설정 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="12781-167">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="12781-168">사용자 계정이 Lync Server에 대해 사용 하도록 설정 되어 있는지 확인 하려면 다음과 같은 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="12781-168">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="12781-169">Enabled 속성을 False로 설정 하면 사용자가 현재 Lync Server를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="12781-169">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

