---
title: 'Lync Server 2013: 위치 정책 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing location policy
ms:assetid: 23d06fd3-31ee-4480-ba1e-d179a55b8b14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690127(v=OCS.15)
ms:contentKeyID: 63969591
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e034be609bfe773a15935d7f0875e0155b57df75
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982894"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-location-policy-in-lync-server-2013"></a><span data-ttu-id="e09f8-102">Lync Server 2013의 테스트 위치 정책</span><span class="sxs-lookup"><span data-stu-id="e09f8-102">Testing location policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e09f8-103">_**마지막으로 수정한 주제:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="e09f8-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e09f8-104">확인 일정</span><span class="sxs-lookup"><span data-stu-id="e09f8-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="e09f8-105">Daily</span><span class="sxs-lookup"><span data-stu-id="e09f8-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e09f8-106">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="e09f8-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="e09f8-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e09f8-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e09f8-108">권한이 필요 함</span><span class="sxs-lookup"><span data-stu-id="e09f8-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="e09f8-109">Lync Server Management Shell을 사용 하 여 로컬에서 실행 되는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e09f8-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="e09f8-110">Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 사용자에 게는 테스트-CsLocationPolicy cmdlet을 실행할 권한이 있는 RBAC 역할을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e09f8-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsLocationPolicy cmdlet.</span></span> <span data-ttu-id="e09f8-111">이 cmdlet을 사용할 수 있는 모든 RBAC 역할 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e09f8-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLocationPolicy&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="e09f8-112">설명</span><span class="sxs-lookup"><span data-stu-id="e09f8-112">Description</span></span>

<span data-ttu-id="e09f8-113">테스트-CsLocationPolicy cmdlet은 위치 정책이 사용자에 게 할당 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e09f8-113">The Test-CsLocationPolicy cmdlet verifies that a location policy is assigned to a user.</span></span> <span data-ttu-id="e09f8-114">위치 정책은 E9-1-1 기능 및 클라이언트 위치와 관련 된 설정을 적용 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e09f8-114">The location policy is used to apply settings that relate to E9-1-1 functionality and client location.</span></span> <span data-ttu-id="e09f8-115">위치 정책은 사용자가 E9-1-1을 사용할 수 있는지 여부를 결정 하 고, 대답이 "예" 인 경우 비상 전화의 동작을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e09f8-115">The location policy determines whether a user is enabled for E9-1-1, and, if the answer is "yes,", what the behavior is of an emergency call.</span></span> <span data-ttu-id="e09f8-116">예를 들어 위치 정책을 사용 하 여 전화를 걸 번호를 정의할 수 있습니다 (미국에서는 911), 회사 보안에서 자동으로 알림을 받을 지 여부, 통화를 라우팅하는 방법을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="e09f8-116">For example, you can use the location policy to define what number makes up an emergency call (911 in the United States), whether corporate security should be automatically notified, and how the call should be routed.</span></span>

<span data-ttu-id="e09f8-117">사용자 또는 네트워크 서브넷에 대 한 위치 정책을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e09f8-117">You can test location policies on users or on network subnets.</span></span> <span data-ttu-id="e09f8-118">서브넷 매개 변수에 대 한 값을 지정 하 여 서브넷에 대해 테스트를 실행 하는 경우 cmdlet은 해당 서브넷에 대 한 위치 정책 확인을 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="e09f8-118">If you run the test against a subnet (by specifying a value for the Subnet parameter), the cmdlet will attempt to resolve the location policy for that subnet.</span></span> <span data-ttu-id="e09f8-119">서브넷에 지정 된 위치 정책이 없는 경우, 구성 된 사용자에 대 한 위치 정책이 검색 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e09f8-119">If no location policy is assigned to the subnet, the location policy for the configured user will be retrieved.</span></span> <span data-ttu-id="e09f8-120">서브넷 정책을 성공적으로 검색 하는 경우 LocationPolicyTagID에서 tagid로 시작 하는 값이 출력에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e09f8-120">If the subnet policy is retrieved successfully, the output will include a LocationPolicyTagID value that begins with subnet-tagid.</span></span> <span data-ttu-id="e09f8-121">서브넷에 대 한 위치 정책을 찾지 못한 경우 LocationPolicyTagID는 사용자-tagid으로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e09f8-121">If a location policy for the subnet was not found, the LocationPolicyTagID will begin with user-tagid.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="e09f8-122">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="e09f8-122">Running the test</span></span>

<span data-ttu-id="e09f8-123">테스트-CsLocationPolicy cmdlet은 미리 구성 된 테스트 계정 (Lync Server 테스트 실행을 위한 테스트 계정 설정 참조) 또는 Lync Server에 대해 사용 하도록 설정 된 모든 사용자의 계정을 사용 하 여 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e09f8-123">The Test-CsLocationPolicy cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="e09f8-124">테스트 계정을 사용 하 여이 검사를 실행 하려면 테스트 중인 Lync Server 풀의 FQDN만 지정 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e09f8-124">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="e09f8-125">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e09f8-125">For example:</span></span>

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="e09f8-126">실제 사용자 계정을 사용 하 여이 검사를 실행 하려면 먼저 계정 이름과 암호를 포함 하는 Windows PowerShell 자격 증명 개체를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e09f8-126">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="e09f8-127">그런 다음 테스트-CsLocationPolicy를 호출할 때 해당 자격 증명 개체와 해당 계정에 할당 된 SIP 주소를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e09f8-127">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsLocationPolicy:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="e09f8-128">자세한 내용은 [CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Test-CsLocationPolicy) cmdlet에 대 한 도움말 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e09f8-128">For more information, see the Help documentation for the [Test-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Test-CsLocationPolicy) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="e09f8-129">성공 또는 실패 확인</span><span class="sxs-lookup"><span data-stu-id="e09f8-129">Determining success or failure</span></span>

<span data-ttu-id="e09f8-130">지정 된 사용자에 게 유효한 위치 정책이 있는 경우 다음과 유사한 출력을 받고 결과 속성이 성공으로 표시 됨 **:**</span><span class="sxs-lookup"><span data-stu-id="e09f8-130">If the specified user has a valid location policy, then you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="e09f8-131">EnhancedEmergencyServicesEnabled: true</span><span class="sxs-lookup"><span data-stu-id="e09f8-131">EnhancedEmergencyServicesEnabled : true</span></span>

<span data-ttu-id="e09f8-132">LocationPolicyTagID: 사용자-tagid</span><span class="sxs-lookup"><span data-stu-id="e09f8-132">LocationPolicyTagID : user-tagid</span></span>

<span data-ttu-id="e09f8-133">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e09f8-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="e09f8-134">결과: 성공</span><span class="sxs-lookup"><span data-stu-id="e09f8-134">Result : Success</span></span>

<span data-ttu-id="e09f8-135">대기 시간: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="e09f8-135">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="e09f8-136">오류</span><span class="sxs-lookup"><span data-stu-id="e09f8-136">Error :</span></span>

<span data-ttu-id="e09f8-137">있게</span><span class="sxs-lookup"><span data-stu-id="e09f8-137">Diagnosis :</span></span>

<span data-ttu-id="e09f8-138">지정 된 사용자에 대 한 유효한 위치 정책을 찾을 수 없으면 결과가 실패로 표시 되 고 오류 및 진단 속성에 추가 정보가 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e09f8-138">If a valid location policy cannot be found for the specified user, then Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="e09f8-139">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e09f8-139">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="e09f8-140">결과: 실패</span><span class="sxs-lookup"><span data-stu-id="e09f8-140">Result : Failure</span></span>

<span data-ttu-id="e09f8-141">대기 시간: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="e09f8-141">Latency : 00:00:00</span></span>

<span data-ttu-id="e09f8-142">오류: 404, 찾을 수 없음</span><span class="sxs-lookup"><span data-stu-id="e09f8-142">Error : 404, Not Found</span></span>

<span data-ttu-id="e09f8-143">진단: ErrorCode = 4005, Source = atl-cs-001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="e09f8-143">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="e09f8-144">이유 = 대상 URI가 SIP에 대해 사용 하도록 설정 되지 않았거나 지원 되지 않음</span><span class="sxs-lookup"><span data-stu-id="e09f8-144">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="e09f8-145">존재.</span><span class="sxs-lookup"><span data-stu-id="e09f8-145">exist.</span></span>

<span data-ttu-id="e09f8-146">Microsoft DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="e09f8-146">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="e09f8-147">이전 출력에서는 지정 된 사용자가 유효 하지 않기 때문에 테스트 실패 됨: 계정이 없거나 사용자에 게 Lync Server에 대 한 사용이 설정 되어 있지 않은 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="e09f8-147">The previous output states that the test failed because the specified user is not valid: either the account does not exist or the user has not been enabled for Lync Server.</span></span> <span data-ttu-id="e09f8-148">계정의 유효성을 확인 하 고 다음과 같은 명령을 실행 하 여 해당 계정이 nm-ocs-14-3에 대해 사용 하도록 설정 되었는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e09f8-148">You can verify the validity of an account, and determine whether or not that account has been enabled for nm-ocs-14-3rd, by running a command similar to this:</span></span>

    Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

<span data-ttu-id="e09f8-149">테스트-CsLocationPolicy에 실패 하는 경우 다음과 같이 Verbose 매개 변수를 포함 하 여 테스트를 다시 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e09f8-149">If Test-CsLocationPolicy fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="e09f8-150">Verbose 매개 변수가 포함 된 경우 테스트-CsLocationPolicy는 위치 정책을 확인 하는 동안 시도한 각 작업의 단계별 계정을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e09f8-150">When the Verbose parameter is included, Test-CsLocationPolicy will return a step-by-step account of each action it tried when verifying the location policy.</span></span> <span data-ttu-id="e09f8-151">예를 들어 다음 출력은 잘못 된 비밀 번호를 제공 하 여 Lync Server에서 테스트 사용자에 게 로그온 할 수 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e09f8-151">For example, this output indicates that Lync Server couldn't log on the test user, probably because an invalid password was supplied:</span></span>

<span data-ttu-id="e09f8-152">등록 요청 전송 중:</span><span class="sxs-lookup"><span data-stu-id="e09f8-152">Sending Registration request :</span></span>

<span data-ttu-id="e09f8-153">대상 Fqdn = atl-cs-011.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e09f8-153">Target Fqdn = atl-cs-011.litwareinc.com</span></span>

<span data-ttu-id="e09f8-154">사용자 Sip 주소 = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e09f8-154">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="e09f8-155">등록자 포트 = 5061</span><span class="sxs-lookup"><span data-stu-id="e09f8-155">Registrar Port = 5061</span></span>

<span data-ttu-id="e09f8-156">' IWA ' 인증 유형이 선택 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e09f8-156">Auth Type 'IWA' is selected.</span></span>

<span data-ttu-id="e09f8-157">Sip/atl에 대 한 등록 적중률-cs-001 litwareinc .com</span><span class="sxs-lookup"><span data-stu-id="e09f8-157">Registration hit against sip/atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="e09f8-158">' 등록 ' 활동이 완료 되었습니다 (' 0.0601795 ' 초).</span><span class="sxs-lookup"><span data-stu-id="e09f8-158">'Register' activity completed in '0.0601795' secs.</span></span>

<span data-ttu-id="e09f8-159">' 로그온이 거부 되었습니다. ' 라는 예외가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="e09f8-159">An exception 'The log on was denied.</span></span> <span data-ttu-id="e09f8-160">올바른 자격 증명을 사용 하 고 있으며 계정이 활성 상태 인지 확인 합니다. '</span><span class="sxs-lookup"><span data-stu-id="e09f8-160">Check that the correct credentials are being used and the account is active.'</span></span> <span data-ttu-id="e09f8-161">워크플로를 진행 하는 동안 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="e09f8-161">occurred during the Workflow.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="e09f8-162">테스트가 실패할 수 있는 이유</span><span class="sxs-lookup"><span data-stu-id="e09f8-162">Reasons why the test might have failed</span></span>

<span data-ttu-id="e09f8-163">테스트-CsLocationPolicy에서 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e09f8-163">Here are some common reasons why Test-CsLocationPolicy might fail:</span></span>

  - <span data-ttu-id="e09f8-164">유효 하지 않은 사용자 계정을 지정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="e09f8-164">You specified a user account that is not valid.</span></span> <span data-ttu-id="e09f8-165">다음과 같은 명령을 실행 하 여 사용자 계정이 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e09f8-165">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="e09f8-166">사용자 계정이 올바르지만 현재 Lync Server에서 계정을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e09f8-166">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="e09f8-167">Lync Server에 대해 사용자 계정이 설정 되어 있는지 확인 하려면 다음과 같은 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e09f8-167">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="e09f8-168">Enabled 속성이 False로 설정 된 경우 사용자가 현재 Lync Server에 대해 사용 하도록 설정 되어 있지 않음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="e09f8-168">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

