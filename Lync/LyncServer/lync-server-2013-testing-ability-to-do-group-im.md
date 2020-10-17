---
title: 'Lync Server 2013: 그룹 IM을 수행 하는 기능 테스트'
description: 'Lync Server 2013: 그룹 IM을 수행 하는 기능을 테스트 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to do group IM
ms:assetid: ca5545bc-51ac-490f-b96b-917bb742ad04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743839(v=OCS.15)
ms:contentKeyID: 63969652
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f6988a0c1a7ba569f7b4da098ae741beab5e14fa
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560814"
---
# <a name="testing-ability-to-do-group-im-in-lync-server-2013"></a><span data-ttu-id="462f5-103">Lync Server 2013에서 그룹 IM을 수행 하는 기능 테스트</span><span class="sxs-lookup"><span data-stu-id="462f5-103">Testing ability to do group IM in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="462f5-104">_**마지막으로 수정 된 항목:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="462f5-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="462f5-105">확인 일정</span><span class="sxs-lookup"><span data-stu-id="462f5-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="462f5-106">매일</span><span class="sxs-lookup"><span data-stu-id="462f5-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="462f5-107">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="462f5-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="462f5-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="462f5-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="462f5-109">필요한 권한</span><span class="sxs-lookup"><span data-stu-id="462f5-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="462f5-110">Lync Server 관리 셸을 사용 하 여 로컬로 실행 하는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="462f5-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="462f5-111">Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 사용자에 게 Test-CsGroupIM cmdlet을 실행 하는 권한이 있는 RBAC 역할을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="462f5-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsGroupIM cmdlet.</span></span> <span data-ttu-id="462f5-112">이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="462f5-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="462f5-113">설명</span><span class="sxs-lookup"><span data-stu-id="462f5-113">Description</span></span>

<span data-ttu-id="462f5-114">Test-CsGroupIM cmdlet은 조직의 사용자가 그룹 인스턴트 메시징 세션을 수행할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="462f5-114">The Test-CsGroupIM cmdlet verifies that users in your organization can conduct group instant messaging sessions.</span></span> <span data-ttu-id="462f5-115">테스트-CsGroupIM을 실행 하면 cmdlet이 테스트 사용자 쌍에 Lync Server로 로그인을 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="462f5-115">When you run Test-CsGroupIM, the cmdlet attempts to sign in a pair of test users to Lync Server.</span></span> <span data-ttu-id="462f5-116">성공하면 Test-CsGroupIM에서 첫 번째 테스트 사용자를 사용하여 새 전화 회의를 만든 다음 두 번째 사용자를 전화 회의에 참가하도록 초대합니다.</span><span class="sxs-lookup"><span data-stu-id="462f5-116">If successful, Test-CsGroupIM creates a new conference using the first test user, then invites the second user to join the conference.</span></span> <span data-ttu-id="462f5-117">메시지를 교환한 후 두 사용자의 시스템 연결이 모두 끊어집니다.</span><span class="sxs-lookup"><span data-stu-id="462f5-117">After an exchange of messages, both users are then disconnected from the system.</span></span> <span data-ttu-id="462f5-118">이러한 모든 작업은 실제 사용자에 게 영향을 주지 않고 사용자 상호 작용 없이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="462f5-118">Note that all of this happens without any user interaction, and without affecting any actual users.</span></span> <span data-ttu-id="462f5-119">예를 들어 테스트 계정 sip:kenmyer@litwareinc.com 실제 Lync Server 계정을 가진 실제 사용자에 해당 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="462f5-119">For example, suppose that the test account sip:kenmyer@litwareinc.com corresponds to a real user who has a real Lync Server account.</span></span> <span data-ttu-id="462f5-120">이 경우 실제 Ken Myer를 방해하지 않고 테스트가 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="462f5-120">In that case, the test will be conducted without any disruption to the real Ken Myer.</span></span> <span data-ttu-id="462f5-121">예를 들어 Ken Myer 테스트 계정이 시스템에서 로그오프된 경우에도 실제 Ken Myer는 계속 로그온되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="462f5-121">For example, even when the Ken Myer test account logs off from the system, Ken Myer the person will remain logged on.</span></span> <span data-ttu-id="462f5-122">마찬가지로 실제 Ken Myer는 전화 회의 참가 초대를 받을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="462f5-122">Likewise, the real Ken Myer won't receive an invitation to join the conference.</span></span> <span data-ttu-id="462f5-123">이 초대는 테스트 계정에 전송되고 해당 계정에 의해 수락됩니다.</span><span class="sxs-lookup"><span data-stu-id="462f5-123">That invitation will be sent to, and accepted by, the test account.</span></span>

<span data-ttu-id="462f5-124">자세한 내용은 [CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) cmdlet에 대 한 도움말 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="462f5-124">For more information, see the Help documentation for the [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="462f5-125">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="462f5-125">Running the test</span></span>

<span data-ttu-id="462f5-126">Test-CsGroupIM cmdlet은 미리 구성 된 테스트 계정 쌍 (Lync Server 테스트 실행을 위한 테스트 계정 설정 참조) 또는 Lync Server를 사용 하도록 설정 된 두 사용자의 계정 중 하나를 사용 하 여 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="462f5-126">The Test-CsGroupIM cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="462f5-127">테스트 계정을 사용 하 여이 검사를 실행 하려면 테스트할 Lync Server 풀의 FQDN만 지정 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="462f5-127">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="462f5-128">예제:</span><span class="sxs-lookup"><span data-stu-id="462f5-128">For example:</span></span>

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="462f5-129">실제 사용자 계정을 사용 하 여이 검사를 실행 하려면 각 계정에 대해 두 Lync Server 관리 셸 자격 증명 개체 (계정 이름과 암호가 포함 된 개체)를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="462f5-129">To run this check using actual user accounts, you must create two Lync Server Management Shell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="462f5-130">그런 다음 테스트-CsGroupIM을 호출할 때 이러한 자격 증명 개체와 두 계정의 SIP 주소를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="462f5-130">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsGroupIM:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsGroupIm -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="462f5-131">자세한 내용은 [CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) cmdlet에 대 한 도움말 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="462f5-131">For more information, see the Help documentation for the [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="462f5-132">성공 또는 실패 확인</span><span class="sxs-lookup"><span data-stu-id="462f5-132">Determining Success or Failure</span></span>

<span data-ttu-id="462f5-133">두 사용자가 그룹 인스턴트 메시징 세션을 완료할 수 있는 경우 Result 속성이 Success로 표시 된 것과 비슷한 출력을 받게 됩니다 **.**</span><span class="sxs-lookup"><span data-stu-id="462f5-133">If the two users can complete a group instant messaging session, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="462f5-134">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="462f5-134">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="462f5-135">결과: 성공</span><span class="sxs-lookup"><span data-stu-id="462f5-135">Result : Success</span></span>

<span data-ttu-id="462f5-136">대기 시간: 00:00:06.3812203</span><span class="sxs-lookup"><span data-stu-id="462f5-136">Latency : 00:00:06.3812203</span></span>

<span data-ttu-id="462f5-137">오류</span><span class="sxs-lookup"><span data-stu-id="462f5-137">Error :</span></span>

<span data-ttu-id="462f5-138">진단을</span><span class="sxs-lookup"><span data-stu-id="462f5-138">Diagnosis :</span></span>

<span data-ttu-id="462f5-139">두 사용자가 인스턴트 메시징 세션을 완료할 수 없으면 결과가 실패로 표시 되 고 오류 및 진단 속성에 추가 정보가 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="462f5-139">If the two users can't able to complete the instant messaging session, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="462f5-140">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="462f5-140">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="462f5-141">결과: 실패</span><span class="sxs-lookup"><span data-stu-id="462f5-141">Result : Failure</span></span>

<span data-ttu-id="462f5-142">대기 시간: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="462f5-142">Latency : 00:00:00</span></span>

<span data-ttu-id="462f5-143">오류: 404, 찾을 수 없음</span><span class="sxs-lookup"><span data-stu-id="462f5-143">Error : 404, Not Found</span></span>

<span data-ttu-id="462f5-144">진단: ErrorCode = 4005, Source = atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="462f5-144">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="462f5-145">이유 = 대상 URI가 SIP에 대해 사용 하도록 설정 되지 않았거나 지원 되지 않음</span><span class="sxs-lookup"><span data-stu-id="462f5-145">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="462f5-146">가.</span><span class="sxs-lookup"><span data-stu-id="462f5-146">exist.</span></span>

<span data-ttu-id="462f5-147">Microsoft DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="462f5-147">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="462f5-148">이전 출력에서는 계정이 없거나 사용자가 Lync Server에 대해 사용 하도록 설정 되지 않았으므로 테스트 계정 중 하나 이상이 올바르지 않아 테스트가 실패 했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="462f5-148">The previous output states that the test failed because at least one of the test accounts was not valid, either because the account does not exist or because the user has not been enabled for Lync Server.</span></span> <span data-ttu-id="462f5-149">이 계정이 있는지와 이와 유사한 명령을 실행 하 여 계정이 nm-14-3에 대해 사용 하도록 설정 되었는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="462f5-149">You can verify the account exists, and whether or not the account has been enabled for nm-ocs-14-3rd by running a command similar to this:</span></span>

    "Ken Myer", "David Longmire" | Get-CsUser | Select-Object SipAddress, Enabled

<span data-ttu-id="462f5-150">Test-CsGroupIM 실패 하면 다음 시간에 Verbose 매개 변수를 포함 하 여 테스트를 다시 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="462f5-150">If Test-CsGroupIM fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="462f5-151">Verbose 매개 변수를 포함 하면 Test-CsGroupIM는 지정 된 사용자가 그룹 인스턴트 메시징 세션에 참가할 수 있는지 확인할 때 시도한 각 작업의 단계별 계정을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="462f5-151">When the Verbose parameter is included, Test-CsGroupIM will return a step-by-step account of each action it tried when it checked the ability of the specified users to participate in a group instant messaging sessions.</span></span> <span data-ttu-id="462f5-152">예를 들어 테스트가 실패 하 여 하나 이상의 사용자 계정이 올바르지 않은 것으로 확인 되 면 Verbose 매개 변수를 사용 하 여 테스트를 다시 실행 하 고 어떤 사용자 계정이 유효한 지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="462f5-152">For example, if your test fails and you are told that one or more of the user accounts is not valid, you can rerun the test using the Verbose parameter and determine which user account is not valid:</span></span>

<span data-ttu-id="462f5-153">등록 요청을 보내는 중:</span><span class="sxs-lookup"><span data-stu-id="462f5-153">Sending Registration request:</span></span>

 <span data-ttu-id="462f5-154">대상 Fqdn = atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="462f5-154">Target Fqdn      = atl-cs-001.litwareinc.com</span></span>

 <span data-ttu-id="462f5-155">사용자 SIP 주소 = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="462f5-155">User SIP Address = sip:kenmyer@litwareinc.com</span></span>

 <span data-ttu-id="462f5-156">포트 등록 = 5061</span><span class="sxs-lookup"><span data-stu-id="462f5-156">Register Port    = 5061</span></span>

<span data-ttu-id="462f5-157">인증 유형 ' IWA '이 선택 됩니다.</span><span class="sxs-lookup"><span data-stu-id="462f5-157">Auth type 'IWA' is selected.</span></span>

<span data-ttu-id="462f5-158">' 로그온이 거부 되었습니다. ' 라는 예외가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="462f5-158">An exception 'The log on was denied.</span></span> <span data-ttu-id="462f5-159">올바른 자격 증명을 사용 하 고 있는지와 계정이 활성 상태 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="462f5-159">Check that the correct credentials are being used and the account is active'</span></span>

<span data-ttu-id="462f5-160">여기에서 볼 수 있듯이이 예에서는 SIP 주소 sip:kenmyer@litwareinc.com을 가진 사용자가 로그온 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="462f5-160">As you can see, in this example the user who has the SIP address sip:kenmyer@litwareinc.com was not able to log on.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="462f5-161">테스트가 실패 한 이유</span><span class="sxs-lookup"><span data-stu-id="462f5-161">Reasons why the test might have failed</span></span>

<span data-ttu-id="462f5-162">Test-CsGroupIM 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="462f5-162">Here are some common reasons why Test-CsGroupIM might fail:</span></span>

  - <span data-ttu-id="462f5-163">잘못 된 사용자 계정을 지정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="462f5-163">You specified an incorrect user account.</span></span> <span data-ttu-id="462f5-164">다음과 같은 명령을 실행 하 여 사용자 계정이 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="462f5-164">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="462f5-165">사용자 계정이 올바르지만 해당 계정이 Lync Server에 대해 현재 사용 하도록 설정 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="462f5-165">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="462f5-166">사용자 계정이 Lync Server에 대해 사용 하도록 설정 되었는지 확인 하려면 다음과 같은 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="462f5-166">To verify that a user account was enabled for Lync Server, run a command similar to the following:</span></span>
    
    <span data-ttu-id="462f5-167">Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object 사용</span><span class="sxs-lookup"><span data-stu-id="462f5-167">Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled</span></span>
    
    <span data-ttu-id="462f5-168">Enabled 속성을 False로 설정 하면 사용자가 현재 Lync Server를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="462f5-168">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="462f5-169">인스턴트 메시징 서비스를 사용 하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="462f5-169">The instant messaging service might not be available.</span></span> <span data-ttu-id="462f5-170">Lync Server에서는 보관 데이터베이스에 액세스할 수 없는 경우 인스턴트 메시징을 사용할 수 없도록 시스템을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="462f5-170">With Lync Server, you can configure the system so that instant messaging is not available if the archiving database cannot be accessed.</span></span> <span data-ttu-id="462f5-171">다음과 같은 명령을 실행 하 여이를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="462f5-171">You can verify that by running a command similar to the following:</span></span>
    
        Get-CsArchivingConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object BlockOnArchiveFailure
    
    <span data-ttu-id="462f5-172">BlockOnArchiveFailure이 True로 설정 된 경우 보관 데이터베이스를 사용할 수 있는지 여부를 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="462f5-172">If BlockOnArchiveFailure is set to True, then you should determine whether or not the archiving database is available.</span></span> <span data-ttu-id="462f5-173">다음 명령을 사용 하 여 보관 데이터베이스의 위치를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="462f5-173">You can return the locations of your archiving databases by using the following command:</span></span>
    
        Get-CsService -ArchivingDatabase

  - <span data-ttu-id="462f5-174">보관 서버를 사용 하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="462f5-174">The Archiving Server might not be available.</span></span> <span data-ttu-id="462f5-175">다음 명령을 사용 하 여 보관 서버의 FQDN을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="462f5-175">You can retrieve the FQDN of your Archiving Servers by using this command:</span></span>
    
        Get-CsService -ArchivingServer
    
    <span data-ttu-id="462f5-176">그런 다음 적절 한 서버에 ping을 수행 하 여 해당 서버가 사용 가능한 지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="462f5-176">You can then ping the appropriate server to verify that it is available.</span></span> <span data-ttu-id="462f5-177">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="462f5-177">For example:</span></span>
    
        ping atl-archiving-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

