---
title: 'Lync Server 2013: (c) 회의 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing UCWA conferencing
ms:assetid: 62b3866a-0759-4b1f-99ec-5a68d6a74f00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727306(v=OCS.15)
ms:contentKeyID: 63969610
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5879eaa10b128bedbc1e28fe85cee40aed27dddd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503915"
---
# <a name="testing-ucwa-conferencing-in-lync-server-2013"></a><span data-ttu-id="240e4-102">Lync Server 2013에서 c u c 회의 테스트</span><span class="sxs-lookup"><span data-stu-id="240e4-102">Testing UCWA conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="240e4-103">_**마지막으로 수정 된 항목:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="240e4-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="240e4-104">확인 일정</span><span class="sxs-lookup"><span data-stu-id="240e4-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="240e4-105">매일</span><span class="sxs-lookup"><span data-stu-id="240e4-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="240e4-106">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="240e4-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="240e4-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="240e4-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="240e4-108">필요한 권한</span><span class="sxs-lookup"><span data-stu-id="240e4-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="240e4-109">Lync Server 관리 셸을 사용 하 여 로컬로 실행 하는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="240e4-110">Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 <strong>test-csucwaconference</strong> cmdlet을 실행 하는 권한이 있는 RBAC 역할을 사용자에 게 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsUcwaConference</strong> cmdlet.</span></span> <span data-ttu-id="240e4-111">이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsUcwaConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="240e4-112">설명</span><span class="sxs-lookup"><span data-stu-id="240e4-112">Description</span></span>

<span data-ttu-id="240e4-113">**Test-csucwaconference** cmdlet은 테스트 사용자 쌍이 통합 커뮤니케이션 웹 API (c)를 사용 하 여 온라인 회의를 예약, 가입 하 고 수행할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-113">The **Test-CsUcwaConference** cmdlet verifies that a pair of test users can schedule, join, and then conduct an online conference using the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="240e4-114">이 작업을 수행 하기 위해 cmdlet은 Lync Server web ticket 서비스를 사용 하 여 두 테스트 사용자를 인증 하 고 Lync Server에 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-114">To do this, the cmdlet uses the Lync Server web ticket service to authenticate the two test users and register them with Lync Server.</span></span> <span data-ttu-id="240e4-115">그 다음 cmdlet은 모임 이끌이 자격 증명을 사용하여 회의를 시작하고 참가자를 모임에 초대합니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-115">The cmdlet then starts a conference using the organizer credentials and invites the participant to join the meeting.</span></span> <span data-ttu-id="240e4-116">회의가 완료 되 면 **test-csucwaconference** cmdlet은 사용자가 exchange 인스턴트 메시지와 같은 작업을 수행 하 고 풀을 수행할 수 있는지 확인 한 다음, 회의의 연결을 끊고 두 테스트 사용자의 등록을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-116">After the meeting is joined, the **Test-CsUcwaConference** cmdlet verifies that the users can do such things as exchange instant message and conduct pools, then disconnects the conference and unregisters the two test users.</span></span> <span data-ttu-id="240e4-117">테스트가 완료 되 면 예약 된 전화 회의도 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-117">The scheduled conference will also be deleted when the test is finished.</span></span>

<span data-ttu-id="240e4-118">**Test-csucwaconference** cmdlet을 사용 하 여 익명 사용자가 온라인 회의에 참가할 수 있는지 여부를 확인할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-118">The **Test-CsUcwaConference** cmdlet can also be used to determine whether anonymous users can join online conferences.</span></span>

<span data-ttu-id="240e4-119">해당 풀에 **test-csucwaconference** cmdlet이 설치 되어 있지 않으면 Microsoft Lync Server 2010 풀에 대해 테스트를 실행 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-119">Note that the **Test-CsUcwaConference** cmdlet should not be run against a Microsoft Lync Server 2010 pool unless UCWA was installed on that pool.</span></span> <span data-ttu-id="240e4-120">**Test-csucwaconference** 및 wa가 설치 되지 않은 경우에는 해당 호출이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-120">If UCWA has not been installed then the call to the **Test-CsUcwaConference** cmdlet will fail.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="240e4-121">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="240e4-121">Running the test</span></span>

<span data-ttu-id="240e4-p104">예제 1의 명령은 테스트 사용자 한 쌍이 풀 atl-cs-001.litwareinc.com에서 UCWA 회의에 참석할 수 있는지 확인합니다. 이 명령은 atl-cs-001.litwareinc.com에 대해 상태 모니터링 구성 테스트 사용자 쌍을 미리 정의하지 않으면 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-p104">The command shown in Example 1 verifies that a pair of test users can participate in an UCWA conference on the pool atl-cs-001.litwareinc.com. Note that this command will fail if you have not predefined a pair of health monitoring configuration test users for atl-cs-001.litwareinc.com.</span></span>

    Test-CsUcwaConference -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="240e4-124">예제 2에 표시 된 명령은 litwareinc pilar 및 litwareinc kenmyer (사용자 쌍)가 c u 3 \\ \\ 회의에 참가 하는 기능을 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-124">The commands shown in Example 2 test the ability of a pair of users (litwareinc\\pilar and litwareinc\\kenmyer) to participate in an UCWA conference.</span></span> <span data-ttu-id="240e4-125">이 작업을 수행 하기 위해이 예제의 첫 번째 명령은 Get-Credential cmdlet을 사용 하 여 사용자 Pilar Ackerman의 이름과 암호가 포함 된 Windows PowerShell 명령줄 인터페이스 자격 증명 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-125">To do this, the first command in the example uses the Get-Credential cmdlet to create a Windows PowerShell command-line interface credential object that contains the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="240e4-126">(로그온 이름, litwareinc pilar가 \\ 매개 변수로 포함 되었기 때문에 Windows PowerShell 자격 증명 요청 대화 상자에만 관리자가 Pilar Ackerman 계정의 암호를 입력 하면 됩니다.) 그런 다음 결과 credentials 개체가 $cred 1 이라는 변수에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-126">(Because the logon name, litwareinc\\pilar, was included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credentials object is then stored in a variable named $cred1.</span></span> <span data-ttu-id="240e4-127">두 번째 명령도 같은 작업을 수행하지만 이번에는 Ken Myer 계정의 자격 증명 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-127">The second command does the same thing, this time returning a credential object for the Ken Myer account.</span></span>

<span data-ttu-id="240e4-128">두 자격 증명 개체를 함께 사용 하는 경우 예제의 세 번째 명령은 두 사용자가 c-WA 회의에 참가할 수 있는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-128">With the two credential objects in hand, the third command in the example determines whether the two users can participate in an UCWA conference.</span></span> <span data-ttu-id="240e4-129">이 작업을 실행 하기 위해 **test-csucwaconference** Cmdlet은 targetfqdn (등록자 풀의 fqdn)과 함께 다음과 같은 매개 변수를 사용 하 여 호출 됩니다. Organizercredential (모임 이끌이의 SIP 주소) 변수와 (이 사용자에 대 한 자격 증명이 포함 된 Windows PowerShell 개체) ParticipantSipAddress (다른 테스트 사용자의 SIP 주소); 및 ParticipantCredential (다른 사용자의 자격 증명을 포함 하는 Windows PowerShell 명령줄 인터페이스 개체)</span><span class="sxs-lookup"><span data-stu-id="240e4-129">To run this task, the **Test-CsUcwaConference** cmdlet is called, together with the following parameters: TargetFqdn (the FQDN of the Registrar pool); OrganizerSipAddress (the SIP address for the meeting organizer); OrganizerCredential (the Windows PowerShell object that contains the credentials for this same user); ParticipantSipAddress (the SIP address for the other test user); and ParticipantCredential (the Windows PowerShell command-line interface object that contains the credentials for the other user).</span></span>

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    Test-CsUcwaConference -TargetFqdn atl-cs-001.litwareinc.com -OrganizerSipAddress "sip:pilar@litwareinc.com" -OrganizerCredential $cred1 -ParticipantSipAddress "sip:kenmyer@litwareinc.com" -ParticipantCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="240e4-130">성공 또는 실패 확인</span><span class="sxs-lookup"><span data-stu-id="240e4-130">Determining success or failure</span></span>

<span data-ttu-id="240e4-131">회의가 올바르게 구성 되 면 다음과 비슷한 출력을 받게 되며 Result 속성이 Success로 표시 됩니다 **.**</span><span class="sxs-lookup"><span data-stu-id="240e4-131">If conferencing is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="240e4-132">대상 Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="240e4-132">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="240e4-133">대상 Uri: https://Lynctest를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-133">Target Uri : https:// LyncTest-SE.LyncTest.SelfHost.Corp.</span></span>

<span data-ttu-id="240e4-134">Microsoft.com:443/CertProv/CertProvisiongService.svc</span><span class="sxs-lookup"><span data-stu-id="240e4-134">Microsoft.com:443/CertProv/CertProvisiongService.svc</span></span>

<span data-ttu-id="240e4-135">결과: 성공</span><span class="sxs-lookup"><span data-stu-id="240e4-135">Result : Success</span></span>

<span data-ttu-id="240e4-136">대기 시간: 00:00:14.9862716</span><span class="sxs-lookup"><span data-stu-id="240e4-136">Latency : 00:00:14.9862716</span></span>

<span data-ttu-id="240e4-137">오류 메시지:</span><span class="sxs-lookup"><span data-stu-id="240e4-137">Error Message :</span></span>

<span data-ttu-id="240e4-138">진단을</span><span class="sxs-lookup"><span data-stu-id="240e4-138">Diagnosis :</span></span>

<span data-ttu-id="240e4-139">지정 된 사용자가 회의를 사용할 수 없는 경우 결과가 **실패로**표시 되 고 오류 및 진단 속성에 추가 정보가 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-139">If the specified users can't use conferencing, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="240e4-140">경고: 지정한 정규화 된 자격에 대 한 등록자 포트 번호를 읽지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-140">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="240e4-141">FQDN (도메인 이름)</span><span class="sxs-lookup"><span data-stu-id="240e4-141">domain name (FQDN).</span></span> <span data-ttu-id="240e4-142">기본 등록자 포트 번호 사용</span><span class="sxs-lookup"><span data-stu-id="240e4-142">Using default Registrar port number.</span></span> <span data-ttu-id="240e4-143">오류</span><span class="sxs-lookup"><span data-stu-id="240e4-143">Exception:</span></span>

<span data-ttu-id="240e4-144">InvalidOperationException: 토폴로지에서 일치 하는 클러스터를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-144">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="240e4-145">구독자</span><span class="sxs-lookup"><span data-stu-id="240e4-145">at</span></span>

<span data-ttu-id="240e4-146">SyntheticTransactions SipSyntheticTransaction TryRetri를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-146">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="240e4-147">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="240e4-147">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="240e4-148">Test-CsUcwaConference: 할당 된 테스트 사용자가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-148">Test-CsUcwaConference : There is no test user assigned for</span></span>

<span data-ttu-id="240e4-149">\[LyncTest.SelfHost.Corp.Microsoft.com \]</span><span class="sxs-lookup"><span data-stu-id="240e4-149">\[LyncTest.SelfHost.Corp.Microsoft.com\].</span></span> <span data-ttu-id="240e4-150">테스트 사용자 구성을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-150">Verify test user configuration.</span></span>

<span data-ttu-id="240e4-151">줄: 1 문자: 1</span><span class="sxs-lookup"><span data-stu-id="240e4-151">At line:1 char:1</span></span>

<span data-ttu-id="240e4-152">\+ Test-CsUcwaConference-TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"</span><span class="sxs-lookup"><span data-stu-id="240e4-152">\+ Test-CsUcwaConference -TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"</span></span>

\+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

<span data-ttu-id="240e4-153">\+ CategoryInfo: ResourceUnavailable 사용할 수 없음: (:) \[ Test-csucwaconference\]</span><span class="sxs-lookup"><span data-stu-id="240e4-153">\+ CategoryInfo : ResourceUnavailable: (:) \[Test-CsUcwaConference\]</span></span>

<span data-ttu-id="240e4-154">, InvalidOperationException</span><span class="sxs-lookup"><span data-stu-id="240e4-154">, InvalidOperationException</span></span>

<span data-ttu-id="240e4-155">\+ FullyQualifiedErrorId: NotFoundTestUsers, Microsoft.</span><span class="sxs-lookup"><span data-stu-id="240e4-155">\+ FullyQualifiedErrorId : NotFoundTestUsers,Microsoft.Rtc.Management.Synth</span></span>

<span data-ttu-id="240e4-156">eticTransactions</span><span class="sxs-lookup"><span data-stu-id="240e4-156">eticTransactions.TestUcwaConferenceCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="240e4-157">테스트가 실패 한 이유</span><span class="sxs-lookup"><span data-stu-id="240e4-157">Reasons why the test might have failed</span></span>

<span data-ttu-id="240e4-158">다음은 **test-csucwaconference에서** 오류가 발생할 수 있는 몇 가지 일반적인 이유입니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-158">Here are some common reasons why **Test-CsUcwaConference** might fail:</span></span>

  - <span data-ttu-id="240e4-159">잘못 된 매개 변수 값이 제공 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-159">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="240e4-160">사용 하는 경우 선택적 매개 변수를 올바르게 구성 해야 하며 그렇지 않으면 테스트가 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-160">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="240e4-161">선택적 매개 변수 없이 명령을 다시 실행 하 여 성공 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-161">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="240e4-162">회의를 수행 하는 기능은 회의를 이끄는 사용자에 게 할당 된 회의 정책 ( **test-csucwaconference** cmdlet의 경우 "sender")에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-162">The ability to conduct a conference depends on the conferencing policy that has been assigned to the user who organized the conference (in the case of the **Test-CsUcwaConference** cmdlet, that is the "sender").</span></span> <span data-ttu-id="240e4-163">이끌이가 자신의 모임에 공동 작업을 포함할 수 없는 경우 (예: 해당 회의 정책에서 EnableDataCollaboration 속성을 False로 설정한 경우) **test-csucwaconference** cmdlet이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-163">If the organizer is not allowed to include collaborative activities in his or her meeting (for example, if his or her conferencing policy has the EnableDataCollaboration property set to False) then the **Test-CsUcwaConference** cmdlet will fail.</span></span>

  - <span data-ttu-id="240e4-164">에 지 서버가 잘못 구성 되었거나 아직 배포 되지 않은 경우에는이 명령이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="240e4-164">This command will fail if the Edge Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="240e4-165">참고 항목</span><span class="sxs-lookup"><span data-stu-id="240e4-165">See Also</span></span>


[<span data-ttu-id="240e4-166">테스트-CsASConference</span><span class="sxs-lookup"><span data-stu-id="240e4-166">Test-CsASConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsASConference)  
[<span data-ttu-id="240e4-167">Test-csdataconference</span><span class="sxs-lookup"><span data-stu-id="240e4-167">Test-CsDataConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsDataConference)  
[<span data-ttu-id="240e4-168">CsAVConference 테스트</span><span class="sxs-lookup"><span data-stu-id="240e4-168">Test-CsAVConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

