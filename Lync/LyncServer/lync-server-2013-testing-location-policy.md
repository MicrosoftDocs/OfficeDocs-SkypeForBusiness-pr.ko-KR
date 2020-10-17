---
title: 'Lync Server 2013: 테스트 위치 정책'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing location policy
ms:assetid: 23d06fd3-31ee-4480-ba1e-d179a55b8b14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690127(v=OCS.15)
ms:contentKeyID: 63969591
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d5cd477b02aa261b762f728ca15d296f49dfbac1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535995"
---
# <a name="testing-location-policy-in-lync-server-2013"></a><span data-ttu-id="377af-102">Lync Server 2013의 테스트 위치 정책</span><span class="sxs-lookup"><span data-stu-id="377af-102">Testing location policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="377af-103">_**마지막으로 수정 된 항목:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="377af-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="377af-104">확인 일정</span><span class="sxs-lookup"><span data-stu-id="377af-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="377af-105">매일</span><span class="sxs-lookup"><span data-stu-id="377af-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="377af-106">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="377af-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="377af-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="377af-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="377af-108">필요한 권한</span><span class="sxs-lookup"><span data-stu-id="377af-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="377af-109">Lync Server 관리 셸을 사용 하 여 로컬로 실행 하는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="377af-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="377af-110">Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 사용자에 게 Test-CsLocationPolicy cmdlet을 실행 하는 권한이 있는 RBAC 역할을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="377af-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsLocationPolicy cmdlet.</span></span> <span data-ttu-id="377af-111">이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="377af-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLocationPolicy&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="377af-112">설명</span><span class="sxs-lookup"><span data-stu-id="377af-112">Description</span></span>

<span data-ttu-id="377af-113">Test-CsLocationPolicy cmdlet은 위치 정책이 사용자에 게 할당 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="377af-113">The Test-CsLocationPolicy cmdlet verifies that a location policy is assigned to a user.</span></span> <span data-ttu-id="377af-114">위치 정책은 E9-1-1 기능 및 클라이언트 위치와 관련된 설정을 적용하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="377af-114">The location policy is used to apply settings that relate to E9-1-1 functionality and client location.</span></span> <span data-ttu-id="377af-115">위치 정책은 사용자가 E9-1-1을 사용할 수 있는지 여부를 결정 하 고, 대답이 "예" 인 경우 긴급 통화의 동작을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="377af-115">The location policy determines whether a user is enabled for E9-1-1, and, if the answer is "yes,", what the behavior is of an emergency call.</span></span> <span data-ttu-id="377af-116">예를 들어 위치 정책을 사용 하 여 긴급 통화를 구성 하는 번호 (미국에서는 911), 회사 보안에 자동으로 알릴지 여부 및 통화를 라우팅하는 방법을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="377af-116">For example, you can use the location policy to define what number makes up an emergency call (911 in the United States), whether corporate security should be automatically notified, and how the call should be routed.</span></span>

<span data-ttu-id="377af-117">사용자나 네트워크 서브넷에 대해 위치 정책을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="377af-117">You can test location policies on users or on network subnets.</span></span> <span data-ttu-id="377af-118">Subnet 매개 변수의 값을 지정하여 서브넷에 대해 테스트를 실행하는 경우 이 cmdlet은 해당 서브넷에 대한 위치 정책을 확인하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="377af-118">If you run the test against a subnet (by specifying a value for the Subnet parameter), the cmdlet will attempt to resolve the location policy for that subnet.</span></span> <span data-ttu-id="377af-119">서브넷에 위치 정책이 할당되어 있지 않으면 구성된 사용자에 대한 위치 정책이 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="377af-119">If no location policy is assigned to the subnet, the location policy for the configured user will be retrieved.</span></span> <span data-ttu-id="377af-120">서브넷 정책을 성공적으로 검색 하면 LocationPolicyTagID 값이 서브넷-tagid로 시작 하는 출력에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="377af-120">If the subnet policy is retrieved successfully, the output will include a LocationPolicyTagID value that begins with subnet-tagid.</span></span> <span data-ttu-id="377af-121">서브넷에 대한 위치 정책을 찾을 수 없는 경우 LocationPolicyTagID가 user-tagid로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="377af-121">If a location policy for the subnet was not found, the LocationPolicyTagID will begin with user-tagid.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="377af-122">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="377af-122">Running the test</span></span>

<span data-ttu-id="377af-123">Test-CsLocationPolicy cmdlet은 미리 구성 된 테스트 계정 (Lync Server 테스트 실행을 위한 테스트 계정 설정 참조) 또는 Lync Server를 사용 하도록 설정 된 사용자의 계정 중 하나를 사용 하 여 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="377af-123">The Test-CsLocationPolicy cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="377af-124">테스트 계정을 사용 하 여이 검사를 실행 하려면 테스트할 Lync Server 풀의 FQDN만 지정 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="377af-124">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="377af-125">예제:</span><span class="sxs-lookup"><span data-stu-id="377af-125">For example:</span></span>

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="377af-126">실제 사용자 계정을 사용 하 여이 검사를 실행 하려면 먼저 계정 이름과 암호가 포함 된 Windows PowerShell 자격 증명 개체를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="377af-126">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="377af-127">그런 다음 테스트-CsLocationPolicy를 호출할 때 해당 계정에 할당 된 자격 증명 개체 및 SIP 주소를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="377af-127">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsLocationPolicy:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="377af-128">자세한 내용은 [CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Test-CsLocationPolicy) cmdlet에 대 한 도움말 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="377af-128">For more information, see the Help documentation for the [Test-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Test-CsLocationPolicy) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="377af-129">성공 또는 실패 확인</span><span class="sxs-lookup"><span data-stu-id="377af-129">Determining success or failure</span></span>

<span data-ttu-id="377af-130">지정 된 사용자에 게 유효한 위치 정책이 있으면 결과 속성이 Success로 표시 된 것과 비슷한 출력을 받게 됩니다 **.**</span><span class="sxs-lookup"><span data-stu-id="377af-130">If the specified user has a valid location policy, then you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="377af-131">EnhancedEmergencyServicesEnabled: true</span><span class="sxs-lookup"><span data-stu-id="377af-131">EnhancedEmergencyServicesEnabled : true</span></span>

<span data-ttu-id="377af-132">LocationPolicyTagID: 사용자-tagid</span><span class="sxs-lookup"><span data-stu-id="377af-132">LocationPolicyTagID : user-tagid</span></span>

<span data-ttu-id="377af-133">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="377af-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="377af-134">결과: 성공</span><span class="sxs-lookup"><span data-stu-id="377af-134">Result : Success</span></span>

<span data-ttu-id="377af-135">대기 시간: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="377af-135">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="377af-136">오류</span><span class="sxs-lookup"><span data-stu-id="377af-136">Error :</span></span>

<span data-ttu-id="377af-137">진단을</span><span class="sxs-lookup"><span data-stu-id="377af-137">Diagnosis :</span></span>

<span data-ttu-id="377af-138">지정 된 사용자에 대해 유효한 위치 정책을 찾을 수 없는 경우 결과가 실패로 표시 되 고 오류 및 진단 속성에 추가 정보가 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="377af-138">If a valid location policy cannot be found for the specified user, then Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="377af-139">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="377af-139">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="377af-140">결과: 실패</span><span class="sxs-lookup"><span data-stu-id="377af-140">Result : Failure</span></span>

<span data-ttu-id="377af-141">대기 시간: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="377af-141">Latency : 00:00:00</span></span>

<span data-ttu-id="377af-142">오류: 404, 찾을 수 없음</span><span class="sxs-lookup"><span data-stu-id="377af-142">Error : 404, Not Found</span></span>

<span data-ttu-id="377af-143">진단: ErrorCode = 4005, Source = atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="377af-143">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="377af-144">이유 = 대상 URI가 SIP에 대해 사용 하도록 설정 되지 않았거나 지원 되지 않음</span><span class="sxs-lookup"><span data-stu-id="377af-144">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="377af-145">가.</span><span class="sxs-lookup"><span data-stu-id="377af-145">exist.</span></span>

<span data-ttu-id="377af-146">Microsoft DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="377af-146">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="377af-147">이전 출력에서는 지정 된 사용자가 유효 하지 않거나 사용자가 Lync Server에 대해 사용 하도록 설정 되지 않아 테스트가 실패 했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="377af-147">The previous output states that the test failed because the specified user is not valid: either the account does not exist or the user has not been enabled for Lync Server.</span></span> <span data-ttu-id="377af-148">계정의 유효성을 확인 하 고 다음과 같은 명령을 실행 하 여 해당 계정이 nm-14-3 세 번째에 사용 하도록 설정 되었는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="377af-148">You can verify the validity of an account, and determine whether or not that account has been enabled for nm-ocs-14-3rd, by running a command similar to this:</span></span>

    Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

<span data-ttu-id="377af-149">Test-CsLocationPolicy 실패 하면 다음 시간에 Verbose 매개 변수를 포함 하 여 테스트를 다시 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="377af-149">If Test-CsLocationPolicy fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="377af-150">Verbose 매개 변수를 포함 하면 Test-CsLocationPolicy는 위치 정책을 확인할 때 시도한 각 작업의 단계별 계정을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="377af-150">When the Verbose parameter is included, Test-CsLocationPolicy will return a step-by-step account of each action it tried when verifying the location policy.</span></span> <span data-ttu-id="377af-151">예를 들어 다음과 같은 출력은 잘못 된 암호가 제공 되었기 때문일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="377af-151">For example, this output indicates that Lync Server couldn't log on the test user, probably because an invalid password was supplied:</span></span>

<span data-ttu-id="377af-152">등록 요청을 보내는 중:</span><span class="sxs-lookup"><span data-stu-id="377af-152">Sending Registration request :</span></span>

<span data-ttu-id="377af-153">대상 Fqdn = atl-cs-011.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="377af-153">Target Fqdn = atl-cs-011.litwareinc.com</span></span>

<span data-ttu-id="377af-154">사용자 Sip 주소 = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="377af-154">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="377af-155">등록자 포트 = 5061</span><span class="sxs-lookup"><span data-stu-id="377af-155">Registrar Port = 5061</span></span>

<span data-ttu-id="377af-156">인증 유형 ' IWA '이 선택 됩니다.</span><span class="sxs-lookup"><span data-stu-id="377af-156">Auth Type 'IWA' is selected.</span></span>

<span data-ttu-id="377af-157">Sip/atl-litwareinc에 대 한 등록 적중</span><span class="sxs-lookup"><span data-stu-id="377af-157">Registration hit against sip/atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="377af-158">' 등록 ' 활동이 완료 되었습니다 (' 0.0601795 ' 초).</span><span class="sxs-lookup"><span data-stu-id="377af-158">'Register' activity completed in '0.0601795' secs.</span></span>

<span data-ttu-id="377af-159">' 로그온이 거부 되었습니다. ' 라는 예외가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="377af-159">An exception 'The log on was denied.</span></span> <span data-ttu-id="377af-160">올바른 자격 증명을 사용 하 고 있으며 계정이 활성 상태 인지 확인 합니다. '</span><span class="sxs-lookup"><span data-stu-id="377af-160">Check that the correct credentials are being used and the account is active.'</span></span> <span data-ttu-id="377af-161">워크플로 중에 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="377af-161">occurred during the Workflow.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="377af-162">테스트가 실패 한 이유</span><span class="sxs-lookup"><span data-stu-id="377af-162">Reasons why the test might have failed</span></span>

<span data-ttu-id="377af-163">Test-CsLocationPolicy 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="377af-163">Here are some common reasons why Test-CsLocationPolicy might fail:</span></span>

  - <span data-ttu-id="377af-164">잘못 된 사용자 계정을 지정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="377af-164">You specified a user account that is not valid.</span></span> <span data-ttu-id="377af-165">다음과 같은 명령을 실행 하 여 사용자 계정이 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="377af-165">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="377af-166">사용자 계정이 올바르지만 해당 계정이 Lync Server에 대해 현재 사용 하도록 설정 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="377af-166">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="377af-167">사용자 계정이 Lync Server에 대해 사용 하도록 설정 되어 있는지 확인 하려면 다음과 같은 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="377af-167">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="377af-168">Enabled 속성을 False로 설정 하면 사용자가 현재 Lync Server를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="377af-168">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

