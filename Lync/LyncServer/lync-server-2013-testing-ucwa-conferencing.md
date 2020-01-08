---
title: 'Lync Server 2013: (와) 회의 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing UCWA conferencing
ms:assetid: 62b3866a-0759-4b1f-99ec-5a68d6a74f00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727306(v=OCS.15)
ms:contentKeyID: 63969610
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b05b67f6f235cdcf3153149c9bd2373c30815d9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978676"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ucwa-conferencing-in-lync-server-2013"></a><span data-ttu-id="d2044-102">Lync Server 2013에서 일부 회의 테스트</span><span class="sxs-lookup"><span data-stu-id="d2044-102">Testing UCWA conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d2044-103">_**마지막으로 수정한 주제:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="d2044-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d2044-104">확인 일정</span><span class="sxs-lookup"><span data-stu-id="d2044-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="d2044-105">Daily</span><span class="sxs-lookup"><span data-stu-id="d2044-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d2044-106">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="d2044-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="d2044-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d2044-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d2044-108">권한이 필요 함</span><span class="sxs-lookup"><span data-stu-id="d2044-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="d2044-109">Lync Server Management Shell을 사용 하 여 로컬에서 실행 되는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2044-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="d2044-110">Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 <strong>CsUcwaConference</strong> cmdlet을 실행 하는 데 필요한 권한이 있는 RBAC 역할을 사용자에 게 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2044-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsUcwaConference</strong> cmdlet.</span></span> <span data-ttu-id="d2044-111">이 cmdlet을 사용할 수 있는 모든 RBAC 역할 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2044-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsUcwaConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="d2044-112">설명</span><span class="sxs-lookup"><span data-stu-id="d2044-112">Description</span></span>

<span data-ttu-id="d2044-113">**CsUcwaConference** cmdlet은 테스트 사용자 쌍이 통합 커뮤니케이션 웹 API (c)를 사용 하 여 예약, 참가, 온라인 회의를 수행할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2044-113">The **Test-CsUcwaConference** cmdlet verifies that a pair of test users can schedule, join, and then conduct an online conference using the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="d2044-114">이렇게 하려면 cmdlet에서 Lync Server web ticket 서비스를 사용 하 여 두 테스트 사용자를 인증 하 고 Lync Server를 사용 하 여 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2044-114">To do this, the cmdlet uses the Lync Server web ticket service to authenticate the two test users and register them with Lync Server.</span></span> <span data-ttu-id="d2044-115">그러면 cmdlet이 이끌이 자격 증명을 사용 하 여 회의를 시작 하 고 참가자에 게 모임에 참가 하도록 초대 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2044-115">The cmdlet then starts a conference using the organizer credentials and invites the participant to join the meeting.</span></span> <span data-ttu-id="d2044-116">모임이 참가 한 후 **CsUcwaConference** cmdlet은 사용자가 exchange 인스턴트 메시지와 같은 작업을 수행 하 고 풀을 수행할 수 있는지 확인 한 다음 회의 연결을 끊고 두 테스트 사용자의 등록을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2044-116">After the meeting is joined, the **Test-CsUcwaConference** cmdlet verifies that the users can do such things as exchange instant message and conduct pools, then disconnects the conference and unregisters the two test users.</span></span> <span data-ttu-id="d2044-117">테스트가 완료 되 면 예약 된 컨퍼런스도 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2044-117">The scheduled conference will also be deleted when the test is finished.</span></span>

<span data-ttu-id="d2044-118">**CsUcwaConference** cmdlet을 사용 하 여 익명 사용자가 온라인 회의에 참가할 수 있는지 여부를 확인할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2044-118">The **Test-CsUcwaConference** cmdlet can also be used to determine whether anonymous users can join online conferences.</span></span>

<span data-ttu-id="d2044-119">해당 풀에 **CsUcwaConference** cmdlet이 설치 되어 있지 않은 경우 Microsoft Lync Server 2010 풀에 대해 테스트를 실행 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2044-119">Note that the **Test-CsUcwaConference** cmdlet should not be run against a Microsoft Lync Server 2010 pool unless UCWA was installed on that pool.</span></span> <span data-ttu-id="d2044-120">A. a i a i a i a i a i \*\*\*\* a i a i a i a i a i a i a i a i a</span><span class="sxs-lookup"><span data-stu-id="d2044-120">If UCWA has not been installed then the call to the **Test-CsUcwaConference** cmdlet will fail.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="d2044-121">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="d2044-121">Running the test</span></span>

<span data-ttu-id="d2044-122">예제 1에 표시 된 명령은 테스트 사용자 쌍이 풀 atl-cs-001.litwareinc.com에서이에 참여할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2044-122">The command shown in Example 1 verifies that a pair of test users can participate in an UCWA conference on the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="d2044-123">Atl-cs-001.litwareinc.com에 대 한 상태 모니터링 구성 테스트 사용자 쌍을 미리 정의 하지 않은 경우에는이 명령이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2044-123">Note that this command will fail if you have not predefined a pair of health monitoring configuration test users for atl-cs-001.litwareinc.com.</span></span>

    Test-CsUcwaConference -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="d2044-124">예제 2에 표시 되는 명령은 litwareinc\\pilar 및 litwareinc\\kenmyer) 사용자 쌍을 테스트 하 여이에 참여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2044-124">The commands shown in Example 2 test the ability of a pair of users (litwareinc\\pilar and litwareinc\\kenmyer) to participate in an UCWA conference.</span></span> <span data-ttu-id="d2044-125">이렇게 하려면이 예제의 첫 번째 명령은 Get-Credential cmdlet을 사용 하 여 사용자 Pilar Ackerman의 이름과 암호를 포함 하는 Windows PowerShell 명령줄 인터페이스 자격 증명 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d2044-125">To do this, the first command in the example uses the Get-Credential cmdlet to create a Windows PowerShell command-line interface credential object that contains the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="d2044-126">(로그온 이름 litwareinc\\pilar는 매개 변수로 포함 되어 있기 때문에 Windows PowerShell 자격 증명 요청 대화 상자에는 관리자만 Pilar Ackerman 계정에 대 한 암호를 입력 해야 합니다.) 그런 다음 결과 자격 증명 개체가 $cred 1 이라는 변수에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2044-126">(Because the logon name, litwareinc\\pilar, was included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credentials object is then stored in a variable named $cred1.</span></span> <span data-ttu-id="d2044-127">두 번째 명령은: 진구 Myer account에 대 한 credential 개체를 반환 하는 것과 동일한 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2044-127">The second command does the same thing, this time returning a credential object for the Ken Myer account.</span></span>

<span data-ttu-id="d2044-128">두 개의 자격 증명 개체를 사용 하는 경우이 예제의 세 번째 명령은 두 사용자가 함께 (a) 회의에 참가할 수 있는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2044-128">With the two credential objects in hand, the third command in the example determines whether the two users can participate in an UCWA conference.</span></span> <span data-ttu-id="d2044-129">이 작업을 실행 하려면 **CsUcwaConference** cmdlet이 다음 매개 변수와 함께 (Targetfqdn (등록자 풀의 fqdn)으로 호출 됩니다. OrganizerSipAddress (모임 이끌이의 SIP 주소). OrganizerCredential (이 사용자에 대 한 자격 증명이 포함 된 Windows PowerShell 개체) ParticipantSipAddress (다른 테스트 사용자의 SIP 주소). 및 ParticipantCredential (다른 사용자의 자격 증명을 포함 하는 Windows PowerShell 명령줄 인터페이스 개체).</span><span class="sxs-lookup"><span data-stu-id="d2044-129">To run this task, the **Test-CsUcwaConference** cmdlet is called, together with the following parameters: TargetFqdn (the FQDN of the Registrar pool); OrganizerSipAddress (the SIP address for the meeting organizer); OrganizerCredential (the Windows PowerShell object that contains the credentials for this same user); ParticipantSipAddress (the SIP address for the other test user); and ParticipantCredential (the Windows PowerShell command-line interface object that contains the credentials for the other user).</span></span>

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    Test-CsUcwaConference -TargetFqdn atl-cs-001.litwareinc.com -OrganizerSipAddress "sip:pilar@litwareinc.com" -OrganizerCredential $cred1 -ParticipantSipAddress "sip:kenmyer@litwareinc.com" -ParticipantCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="d2044-130">성공 또는 실패 확인</span><span class="sxs-lookup"><span data-stu-id="d2044-130">Determining success or failure</span></span>

<span data-ttu-id="d2044-131">회의가 올바르게 구성 되 면 다음과 비슷한 출력이 표시 되 고 결과 속성이 성공으로 표시 됩니다 **.**</span><span class="sxs-lookup"><span data-stu-id="d2044-131">If conferencing is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="d2044-132">대상 Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="d2044-132">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="d2044-133">대상 Uri: https://L Ctest-SE SelfHost.</span><span class="sxs-lookup"><span data-stu-id="d2044-133">Target Uri : https:// LyncTest-SE.LyncTest.SelfHost.Corp.</span></span>

<span data-ttu-id="d2044-134">Microsoft.com:443/CertProv/CertProvisiongService.svc</span><span class="sxs-lookup"><span data-stu-id="d2044-134">Microsoft.com:443/CertProv/CertProvisiongService.svc</span></span>

<span data-ttu-id="d2044-135">결과: 성공</span><span class="sxs-lookup"><span data-stu-id="d2044-135">Result : Success</span></span>

<span data-ttu-id="d2044-136">대기 시간: 00:00:14.9862716</span><span class="sxs-lookup"><span data-stu-id="d2044-136">Latency : 00:00:14.9862716</span></span>

<span data-ttu-id="d2044-137">오류 메시지:</span><span class="sxs-lookup"><span data-stu-id="d2044-137">Error Message :</span></span>

<span data-ttu-id="d2044-138">있게</span><span class="sxs-lookup"><span data-stu-id="d2044-138">Diagnosis :</span></span>

<span data-ttu-id="d2044-139">지정 된 사용자가 회의를 사용할 수 없는 경우에는 결과가 **실패로**표시 되 고 오류 및 진단 속성에 추가 정보가 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2044-139">If the specified users can't use conferencing, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="d2044-140">경고: 정규화 된 정식 #b0에 대 한 등록자 포트 번호를 읽지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="d2044-140">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="d2044-141">도메인 이름 (FQDN).</span><span class="sxs-lookup"><span data-stu-id="d2044-141">domain name (FQDN).</span></span> <span data-ttu-id="d2044-142">기본 등록자 포트 번호를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2044-142">Using default Registrar port number.</span></span> <span data-ttu-id="d2044-143">발생</span><span class="sxs-lookup"><span data-stu-id="d2044-143">Exception:</span></span>

<span data-ttu-id="d2044-144">InvalidOperationException: 토폴로지에서 일치 하는 클러스터를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2044-144">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="d2044-145">배포자</span><span class="sxs-lookup"><span data-stu-id="d2044-145">at</span></span>

<span data-ttu-id="d2044-146">SyntheticTransactions. SipSyntheticTransaction. TryRetri</span><span class="sxs-lookup"><span data-stu-id="d2044-146">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="d2044-147">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="d2044-147">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="d2044-148">CsUcwaConference: 지정 된 테스트 사용자가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2044-148">Test-CsUcwaConference : There is no test user assigned for</span></span>

<span data-ttu-id="d2044-149">\[LyncTest.SelfHost.Corp.Microsoft.com\].</span><span class="sxs-lookup"><span data-stu-id="d2044-149">\[LyncTest.SelfHost.Corp.Microsoft.com\].</span></span> <span data-ttu-id="d2044-150">테스트 사용자 구성을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2044-150">Verify test user configuration.</span></span>

<span data-ttu-id="d2044-151">줄: 1 char: 1</span><span class="sxs-lookup"><span data-stu-id="d2044-151">At line:1 char:1</span></span>

<span data-ttu-id="d2044-152">\+테스트-CsUcwaConference-TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"</span><span class="sxs-lookup"><span data-stu-id="d2044-152">\+ Test-CsUcwaConference -TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"</span></span>

\+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

<span data-ttu-id="d2044-153">\+CategoryInfo: ResourceUnavailable 사용할 수 없음: (:) \[테스트-CsUcwaConference\]</span><span class="sxs-lookup"><span data-stu-id="d2044-153">\+ CategoryInfo : ResourceUnavailable: (:) \[Test-CsUcwaConference\]</span></span>

<span data-ttu-id="d2044-154">, InvalidOperationException</span><span class="sxs-lookup"><span data-stu-id="d2044-154">, InvalidOperationException</span></span>

<span data-ttu-id="d2044-155">\+FullyQualifiedErrorId: NotFoundTestUsers, Microsoft. m m/. 신시사이저</span><span class="sxs-lookup"><span data-stu-id="d2044-155">\+ FullyQualifiedErrorId : NotFoundTestUsers,Microsoft.Rtc.Management.Synth</span></span>

<span data-ttu-id="d2044-156">eticTransactions</span><span class="sxs-lookup"><span data-stu-id="d2044-156">eticTransactions.TestUcwaConferenceCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="d2044-157">테스트가 실패할 수 있는 이유</span><span class="sxs-lookup"><span data-stu-id="d2044-157">Reasons why the test might have failed</span></span>

<span data-ttu-id="d2044-158">**테스트 CsUcwaConference** 가 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d2044-158">Here are some common reasons why **Test-CsUcwaConference** might fail:</span></span>

  - <span data-ttu-id="d2044-159">잘못 된 매개 변수 값이 제공 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d2044-159">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="d2044-160">사용 하는 경우 선택적 매개 변수를 올바르게 구성 하거나 테스트에 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2044-160">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="d2044-161">선택적 매개 변수 없이 명령을 다시 실행 하 여 성공 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2044-161">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="d2044-162">회의를 진행 하는 기능은 회의를 이끄는 사용자에 게 할당 된 회의 정책 ( **CsUcwaConference** cmdlet의 경우 "sender")에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="d2044-162">The ability to conduct a conference depends on the conferencing policy that has been assigned to the user who organized the conference (in the case of the **Test-CsUcwaConference** cmdlet, that is the "sender").</span></span> <span data-ttu-id="d2044-163">이끌이는 자신의 모임에 공동 작업을 포함할 수 없는 경우 (예: 해당 회의 정책에 EnableDataCollaboration 속성이 False로 설정 된 경우)에는 **테스트-CsUcwaConference** cmdlet이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2044-163">If the organizer is not allowed to include collaborative activities in his or her meeting (for example, if his or her conferencing policy has the EnableDataCollaboration property set to False) then the **Test-CsUcwaConference** cmdlet will fail.</span></span>

  - <span data-ttu-id="d2044-164">Edge 서버가 잘못 구성 되었거나 아직 배포 되지 않은 경우에는이 명령이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2044-164">This command will fail if the Edge Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d2044-165">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d2044-165">See Also</span></span>


[<span data-ttu-id="d2044-166">Test-CsASConference</span><span class="sxs-lookup"><span data-stu-id="d2044-166">Test-CsASConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsASConference)  
[<span data-ttu-id="d2044-167">Test-CsDataConference</span><span class="sxs-lookup"><span data-stu-id="d2044-167">Test-CsDataConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsDataConference)  
[<span data-ttu-id="d2044-168">Test-CsAVConference</span><span class="sxs-lookup"><span data-stu-id="d2044-168">Test-CsAVConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

