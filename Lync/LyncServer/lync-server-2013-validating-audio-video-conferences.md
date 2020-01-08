---
title: 'Lync Server 2013: 오디오/비디오 회의의 유효성 검사'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Validating audio/video conferences
ms:assetid: 6c8c422a-d501-42cb-820b-b002f9b2250b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720915(v=OCS.15)
ms:contentKeyID: 63969615
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b0e608f0c765c4dd552645320ec947c7e8a54ac4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979180"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-audiovideo-conferences-in-lync-server-2013"></a><span data-ttu-id="79390-102">Lync Server 2013에서 오디오/비디오 회의의 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="79390-102">Validating audio/video conferences in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="79390-103">_**마지막으로 수정한 주제:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="79390-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79390-104">확인 일정</span><span class="sxs-lookup"><span data-stu-id="79390-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="79390-105">Daily</span><span class="sxs-lookup"><span data-stu-id="79390-105">Daily</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79390-106">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="79390-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="79390-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="79390-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79390-108">권한이 필요 함</span><span class="sxs-lookup"><span data-stu-id="79390-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="79390-109">Lync Server Management Shell을 사용 하 여 로컬에서 실행 되는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="79390-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="79390-110">Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 사용자는 테스트-CsAVConference cmdlet을 실행할 권한이 있는 RBAC 역할을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="79390-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsAVConference cmdlet.</span></span> <span data-ttu-id="79390-111">이 cmdlet을 사용할 수 있는 모든 RBAC 역할 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="79390-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAVConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="79390-112">설명</span><span class="sxs-lookup"><span data-stu-id="79390-112">Description</span></span>

<span data-ttu-id="79390-113">테스트-CsAVConference cmdlet은 두 테스트 사용자가 오디오/비디오 (A/V) 회의에 참가할 수 있는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="79390-113">The Test-CsAVConference cmdlet checks whether two test users can participate in an audio/video (A/V) conference.</span></span> <span data-ttu-id="79390-114">Cmdlet이 실행 되 면 두 사용자가 시스템에 로그온 됩니다.</span><span class="sxs-lookup"><span data-stu-id="79390-114">When the cmdlet runs, the two users are logged on to the system.</span></span> <span data-ttu-id="79390-115">성공적으로 로그인 한 후에는 첫 번째 사용자가 A/V 회의를 만든 다음 두 번째 사용자가 해당 회의에 참가할 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="79390-115">After they face successfully logged on, the first user creates an A/V conference, and then waits for the second user to join that conference.</span></span> <span data-ttu-id="79390-116">간단한 데이터 교환 후 회의가 삭제 되 고 두 테스트 사용자가 로그 오프 됩니다.</span><span class="sxs-lookup"><span data-stu-id="79390-116">After a brief exchange of data, the conference is deleted and the two tests users are logged off.</span></span>

<span data-ttu-id="79390-117">테스트-CsAVConference는 두 테스트 사용자 간의 실제 A/V 회의를 수행 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="79390-117">Note that Test-CsAVConference does not conduct an actual A/V conference between the two test users.</span></span> <span data-ttu-id="79390-118">대신, cmdlet은 두 사용자가 이러한 회의를 수행 하는 데 필요한 모든 연결을 수행할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="79390-118">Instead, the cmdlet verifies that the two users can make all the connections necessary to conduct such a conference.</span></span>

<span data-ttu-id="79390-119">이 명령에 대 한 추가 예제는 [테스트-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference)에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79390-119">Further examples for this command can be found at [Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference).</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="79390-120">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="79390-120">Running the test</span></span>

<span data-ttu-id="79390-121">테스트 (Lync Server 테스트 실행을 위한 테스트 계정 설정 참조) 또는 Lync Server에 대해 사용 하도록 설정 된 두 명의 사용자 계정 중 하나를 사용 하 여 CsAVConference cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79390-121">The Test-CsAVConference cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="79390-122">테스트 계정을 사용 하 여이 검사를 실행 하려면 테스트 중인 Lync Server 풀의 FQDN만 지정 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="79390-122">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="79390-123">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="79390-123">For example:</span></span>

    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="79390-124">실제 사용자 계정을 사용 하 여이 검사를 실행 하려면 각 계정에 대해 두 개의 Windows PowerShell 자격 증명 개체 (계정 이름과 암호를 포함 하는 개체)를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="79390-124">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="79390-125">그런 다음 해당 자격 증명 개체와 두 계정의 SIP 주소를 테스트-CsAVConference를 호출할 때 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="79390-125">You must then include those credentials objects and the SIP addresses of the two accounts when they call Test-CsAVConference:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="79390-126">자세한 내용은 [CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference) cmdlet에 대 한 도움말 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="79390-126">For more information, see the Help documentation for the [Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="79390-127">성공 또는 실패 확인</span><span class="sxs-lookup"><span data-stu-id="79390-127">Determining Success or Failure</span></span>

<span data-ttu-id="79390-128">지정 된 사용자가 A/V 회의를 성공적으로 완료할 수 있는 경우 다음과 비슷한 출력이 표시 되 고 결과 속성이 성공으로 표시 됩니다 **.**</span><span class="sxs-lookup"><span data-stu-id="79390-128">If the specified users can successfully complete an A/V conference, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="79390-129">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="79390-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="79390-130">결과: 성공</span><span class="sxs-lookup"><span data-stu-id="79390-130">Result : Success</span></span>

<span data-ttu-id="79390-131">대기 시간: 00:00:02.6841765</span><span class="sxs-lookup"><span data-stu-id="79390-131">Latency : 00:00:02.6841765</span></span>

<span data-ttu-id="79390-132">오류</span><span class="sxs-lookup"><span data-stu-id="79390-132">Error :</span></span>

<span data-ttu-id="79390-133">있게</span><span class="sxs-lookup"><span data-stu-id="79390-133">Diagnosis :</span></span>

<span data-ttu-id="79390-134">사용자가 회의를 완료할 수 없는 경우에는 결과가 실패로 표시 되 고 오류 및 진단 속성에 추가 정보가 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="79390-134">If the users can not complete the conference, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="79390-135">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="79390-135">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="79390-136">결과: 실패</span><span class="sxs-lookup"><span data-stu-id="79390-136">Result : Failure</span></span>

<span data-ttu-id="79390-137">대기 시간: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="79390-137">Latency : 00:00:00</span></span>

<span data-ttu-id="79390-138">오류: 404, 찾을 수 없음</span><span class="sxs-lookup"><span data-stu-id="79390-138">Error : 404, Not Found</span></span>

<span data-ttu-id="79390-139">진단: ErrorCode = 4005, Source = atl-cs-001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="79390-139">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="79390-140">이유 = 대상 URI가 SIP에 대해 사용 하도록 설정 되지 않았거나 지원 되지 않음</span><span class="sxs-lookup"><span data-stu-id="79390-140">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="79390-141">존재.</span><span class="sxs-lookup"><span data-stu-id="79390-141">exist.</span></span>

<span data-ttu-id="79390-142">Microsoft DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="79390-142">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="79390-143">예를 들어 이전 출력에서는 두 사용자 계정 중 적어도 하나가 유효 하지 않기 때문에 (계정이 없거나 해당 계정이 Lync Server에 대해 사용 하도록 설정 되지 않았기 때문에) 테스트가 실패 했음을 명시 합니다.</span><span class="sxs-lookup"><span data-stu-id="79390-143">For example, the previous output states that the test failed because at least one of the two user accounts was not valid, either because the account does not exist or because the account has not been enabled for Lync Server.</span></span> <span data-ttu-id="79390-144">다음과 같은 명령을 실행 하 여 두 개의 테스트 계정이 있는지, Lync Server에 대해 사용 하도록 설정 되었는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79390-144">You can verify the existence of the two test accounts, and whether they were enabled for Lync Server, by running a command similar to the following:</span></span>

    "sip:kenmyer@litwareinc.com","sip:davidlongmire@litwareinc.com" | Get-CsUser | Select-Object SipAddress, enabled

<span data-ttu-id="79390-145">테스트-CsAVConference에 오류가 발생 하면 다음과 같이 Verbose 매개 변수를 포함 하 여 테스트를 다시 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79390-145">If Test-CsAVConference fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="79390-146">Verbose 매개 변수를 포함 하는 경우 테스트-CsAVConference는 지정 된 사용자가 AV 회의에 참여 하는 기능을 확인할 때 시도한 각 작업의 단계별 계정을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="79390-146">When the Verbose parameter is included Test-CsAVConference will return a step-by-step account of each action it tried when it checked the ability of the specified users to participate in an AV conference.</span></span> <span data-ttu-id="79390-147">예를 들어 테스트에 실패 하 고 다음 진단이 표시 된다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="79390-147">For example, suppose that your test fails and you receive the following Diagnosis:</span></span>

<span data-ttu-id="79390-148">ErrorCode = 1008, Source = accessproxy. litwareinc, Reason = DNS SRV 레코드를 확인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="79390-148">ErrorCode=1008,Source=accessproxy.litwareinc.com,Reason=Unable to resolve DNS SRV record</span></span>

<span data-ttu-id="79390-149">Verbose 매개 변수를 사용 하 여 테스트를 다시 실행 하는 경우 반환 되는 단계별 정보에는 다음과 같은 출력이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="79390-149">If you rerun the test using the Verbose parameter, the step-by-step information returned will include output similar to this:</span></span>

<span data-ttu-id="79390-150">자세한 정보: ' Register ' 활동을 시작 했습니다.</span><span class="sxs-lookup"><span data-stu-id="79390-150">VERBOSE: 'Register' activity started.</span></span>

<span data-ttu-id="79390-151">등록 요청 전송 중:</span><span class="sxs-lookup"><span data-stu-id="79390-151">Sending Registration request:</span></span>

<span data-ttu-id="79390-152">대상 Fqdn = atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="79390-152">Target Fqdn = atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="79390-153">사용자 Sip 주소 = sip:davidlongmire@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="79390-153">User Sip Address = sip:davidlongmire@litwareinc.com</span></span>

<span data-ttu-id="79390-154">등록자 포트 = 5061.</span><span class="sxs-lookup"><span data-stu-id="79390-154">Registrar Port = 5061.</span></span>

<span data-ttu-id="79390-155">인증 유형 ' 신뢰 됨 '이 선택 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="79390-155">Auth Type 'Trusted' is selected.</span></span>

<span data-ttu-id="79390-156">' 등록 ' 활동이 시작 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="79390-156">'Register' activity started.</span></span>

<span data-ttu-id="79390-157">등록 요청 전송 중:</span><span class="sxs-lookup"><span data-stu-id="79390-157">Sending Registration request:</span></span>

<span data-ttu-id="79390-158">대상 Fqdn = atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="79390-158">Target Fqdn = atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="79390-159">사용자 Sip 주소 = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="79390-159">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="79390-160">등록자 포트 = 5061.</span><span class="sxs-lookup"><span data-stu-id="79390-160">Registrar Port = 5061.</span></span>

<span data-ttu-id="79390-161">인증 유형 ' 신뢰 됨 '이 선택 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="79390-161">Auth Type 'Trusted' is selected.</span></span>

<span data-ttu-id="79390-162">' 끝점을 등록할 수 없는 ' 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="79390-162">An exception 'The endpoint was unable to register.</span></span> <span data-ttu-id="79390-163">특정 이유는 ErrorCode를 참조 하세요. '</span><span class="sxs-lookup"><span data-stu-id="79390-163">See the ErrorCode for specific reason.'</span></span> <span data-ttu-id="79390-164">워크플로 중 발생</span><span class="sxs-lookup"><span data-stu-id="79390-164">occurred during Workflow</span></span>

<span data-ttu-id="79390-165">해당 출력의 마지막 줄은 사용자 sip:kenmyer@litwareinc.com Lync Server를 사용 하 여 등록할 수 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="79390-165">The last line in that output indicates that the user sip:kenmyer@litwareinc.com was unable to register with Lync Server.</span></span> <span data-ttu-id="79390-166">즉, SIP 주소 sip:kenmyer@litwareinc.com이 유효한 지, 그리고 연결 된 사용자가 Lync Server에 대해 설정 되어 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="79390-166">That means that you should verify that the SIP address sip:kenmyer@litwareinc.com is valid, and that the associated user is enabled for Lync Server.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="79390-167">테스트가 실패할 수 있는 이유</span><span class="sxs-lookup"><span data-stu-id="79390-167">Reasons why the test might have failed</span></span>

<span data-ttu-id="79390-168">테스트-CsAVConference가 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="79390-168">Here are some common reasons why Test-CsAVConference might fail:</span></span>

  - <span data-ttu-id="79390-169">유효 하지 않은 사용자 계정을 지정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="79390-169">You specified a user account that is not valid.</span></span> <span data-ttu-id="79390-170">다음과 같은 명령을 실행 하 여 사용자 계정이 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79390-170">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="79390-171">사용자 계정이 올바르지만 현재 Lync Server에서 계정을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="79390-171">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="79390-172">Lync Server에 대해 사용자 계정이 설정 되어 있는지 확인 하려면 다음과 같은 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="79390-172">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="79390-173">Enabled 속성이 False로 설정 된 경우 사용자가 현재 Lync Server에 대해 사용 하도록 설정 되어 있지 않음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="79390-173">If the Enabled property is set to False that means that the user is currently not enabled for Lync Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

