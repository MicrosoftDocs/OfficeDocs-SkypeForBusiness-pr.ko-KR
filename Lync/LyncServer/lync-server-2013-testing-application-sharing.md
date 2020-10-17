---
title: 'Lync Server 2013: 응용 프로그램 공유 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing application sharing
ms:assetid: 8d21db9b-10d1-4b43-b057-0deb1df1c205
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727310(v=OCS.15)
ms:contentKeyID: 63969629
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11130c1882fd6d12784cf6c25559a4249453f5d3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530535"
---
# <a name="testing-application-sharing-in-lync-server-2013"></a><span data-ttu-id="27a1c-102">Lync Server 2013에서 응용 프로그램 공유 테스트</span><span class="sxs-lookup"><span data-stu-id="27a1c-102">Testing application sharing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="27a1c-103">_**마지막으로 수정 된 항목:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="27a1c-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="27a1c-104">확인 일정</span><span class="sxs-lookup"><span data-stu-id="27a1c-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="27a1c-105">매일</span><span class="sxs-lookup"><span data-stu-id="27a1c-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27a1c-106">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="27a1c-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="27a1c-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="27a1c-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27a1c-108">필요한 권한</span><span class="sxs-lookup"><span data-stu-id="27a1c-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="27a1c-109">Lync Server 관리 셸을 사용 하 여 로컬로 실행 하는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="27a1c-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="27a1c-110">Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 사용자에 게 Test-CsASConference cmdlet을 실행 하는 권한이 있는 RBAC 역할을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="27a1c-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsASConference cmdlet.</span></span> <span data-ttu-id="27a1c-111">이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="27a1c-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsASConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="27a1c-112">설명</span><span class="sxs-lookup"><span data-stu-id="27a1c-112">Description</span></span>

<span data-ttu-id="27a1c-113">**테스트-CsASConference** cmdlet은 테스트 사용자 쌍이 응용 프로그램 공유를 포함 하는 온라인 회의에 참가할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="27a1c-113">The **Test-CsASConference** cmdlet verifies that a pair of test users can participate in an online conference that includes application sharing.</span></span> <span data-ttu-id="27a1c-114">이를 위해 cmdlet은 Lync Server 2013를 사용 하 여 두 사용자를 등록 한 다음 사용자 계정 중 하나를 사용 하 여 응용 프로그램 공유를 포함 하는 새 전화 회의를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="27a1c-114">To do this, the cmdlet registers the two users with Lync Server 2013, and then it uses one of the user accounts to create a new conference that includes applications sharing.</span></span> <span data-ttu-id="27a1c-115">그런 후에 두 번째 사용자가 해당 회의에 참가할 수 있는지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="27a1c-115">The cmdlet then verifies that the second user is able to join that conference.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="27a1c-116">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="27a1c-116">Running the test</span></span>

<span data-ttu-id="27a1c-p103">예제 1에 표시된 명령은 atl-cs-001.litwareinc.com 풀에서 응용 프로그램 공유 회의를 진행할 수 있는지 확인합니다. 이 명령은 지정된 풀에 대해 테스트 사용자 한 쌍이 구성되었다고 가정합니다. 테스트 사용자가 없으면 명령은 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="27a1c-p103">The command shown in Example 1 verifies that an Application Sharing conference can be conducted on the pool atl-cs-001.litwareinc.com. This command assumes that you have configured a pair of test users for the specified pool. If no such test users exist, the command will fail.</span></span>

    Test-CsASConference -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="27a1c-p104">예제 2에서는 참가 시작 관리자 서비스를 사용하여 atl-cs-001.litwareinc.com 풀에서 응용 프로그램 공유 회의에 참가할 수 있는지 테스트합니다. 이 명령은 서비스 자체만 테스트하며 모바일 장치가 없어도 명령을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27a1c-p104">Example 2 tests the ability of the Join Launcher service to participate in an Application Sharing conference on the pool atl-cs-001.litwareinc.com. Note that this command tests only the service itself; you do not need any mobile devices in order to run the command.</span></span>

    Test-CsASConference -TargetFqdn "atl-cs-001.litwareinc.com" -TestJoinLauncher 

<span data-ttu-id="27a1c-122">예제 2에 표시 된 명령은 litwareinc \\ pilar 및 litwareinc \\ kenmyer)에서 Lync Server 2013에 로그온 한 후 응용 프로그램 공유 회의를 수행 하는 기능을 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="27a1c-122">The commands shown in Example 2 test the ability of a pair of users (litwareinc\\pilar and litwareinc\\kenmyer) to log on to Lync Server 2013 and then conduct an Application Sharing conference.</span></span> <span data-ttu-id="27a1c-123">이 작업을 수행 하기 위해이 예제의 첫 번째 명령은 Get-Credential cmdlet을 사용 하 여 사용자 Pilar Ackerman의 이름과 암호가 포함 된 Windows PowerShell 명령줄 인터페이스 자격 증명 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="27a1c-123">To do this, the first command in the example uses the Get-Credential cmdlet to create a Windows PowerShell command-line interface credential object containing the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="27a1c-124">(로그온 이름, litwareinc pilar가 \\ 매개 변수로 포함 되었기 때문에 Windows PowerShell 자격 증명 요청 대화 상자에만 관리자가 Pilar Ackerman 계정의 암호를 입력 하면 됩니다.) 그런 다음 결과 credential 개체는 $cred 1 이라는 변수에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="27a1c-124">(Because the logon name, litwareinc\\pilar, has been included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credential object is then stored in a variable named $cred1.</span></span> <span data-ttu-id="27a1c-125">두 번째 명령도 같은 작업을 수행하지만 이번에는 Ken Myer 계정의 자격 증명 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="27a1c-125">The second command does the same thing, this time returning a credential object for the Ken Myer account.</span></span>

<span data-ttu-id="27a1c-126">자격 증명 개체를 사용 하는 경우 세 번째 명령은 이러한 두 사용자가 Lync Server 2013에 로그온 하 고 응용 프로그램 공유 전화 회의를 수행할 수 있는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="27a1c-126">With the credential objects in hand, the third command determines whether or not these two users can log on to Lync Server 2013 and conduct an Application Sharing conference.</span></span> <span data-ttu-id="27a1c-127">이 작업을 수행 하기 위해 **테스트-CsASConference** Cmdlet은 targetfqdn (등록자 풀의 fqdn)과 함께 다음 매개 변수와 함께 호출 됩니다. SenderSipAddress (첫 번째 테스트 사용자의 SIP 주소) SenderCredential (이 사용자에 대 한 자격 증명이 포함 된 Windows PowerShell 개체) ReceiverSipAddress (다른 테스트 사용자의 SIP 주소); 및 변수와 (다른 테스트 사용자에 대 한 자격 증명이 포함 된 Windows PowerShell 개체)</span><span class="sxs-lookup"><span data-stu-id="27a1c-127">To carry out this task, the **Test-CsASConference** cmdlet is called, along with the following parameters: TargetFqdn (the FQDN of the Registrar pool); SenderSipAddress (the SIP address for the first test user); SenderCredential (the Windows PowerShell object containing the credentials for this same user); ReceiverSipAddress (the SIP address for the other test user); and ReceiverCredential (the Windows PowerShell object containing the credentials for the other test user).</span></span>

    $cred1 = Get-Credential "litwareinc\pilar" 
    $cred2 = Get-Credential "litwareinc\kenmyer" 
    Test-CsASConference -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $cred1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="27a1c-128">성공 또는 실패 확인</span><span class="sxs-lookup"><span data-stu-id="27a1c-128">Determining success or failure</span></span>

<span data-ttu-id="27a1c-129">응용 프로그램 공유가 올바르게 구성 되 면 다음과 비슷한 출력을 받게 되며 Result 속성은 Success로 표시 됩니다 **.**</span><span class="sxs-lookup"><span data-stu-id="27a1c-129">If application sharing is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="27a1c-130">대상 Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="27a1c-130">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="27a1c-131">결과: 성공</span><span class="sxs-lookup"><span data-stu-id="27a1c-131">Result : Success</span></span>

<span data-ttu-id="27a1c-132">대기 시간: 00:00:01</span><span class="sxs-lookup"><span data-stu-id="27a1c-132">Latency : 00:00:01</span></span>

<span data-ttu-id="27a1c-133">오류 메시지:</span><span class="sxs-lookup"><span data-stu-id="27a1c-133">Error Message :</span></span>

<span data-ttu-id="27a1c-134">진단을</span><span class="sxs-lookup"><span data-stu-id="27a1c-134">Diagnosis :</span></span>

<span data-ttu-id="27a1c-135">지정 된 사용자가 응용 프로그램을 공유할 수 없는 경우 결과가 실패로 표시 되 고 오류 및 진단 속성에 추가 정보가 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="27a1c-135">If the specified users can't share applications, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="27a1c-136">대상 Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="27a1c-136">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="27a1c-137">결과: 실패</span><span class="sxs-lookup"><span data-stu-id="27a1c-137">Result : Failure</span></span>

<span data-ttu-id="27a1c-138">대기 시간: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="27a1c-138">Latency : 00:00:00</span></span>

<span data-ttu-id="27a1c-139">오류 메시지: 10060, 연결 된 파티 때문에 연결 시도가 실패 했습니다.</span><span class="sxs-lookup"><span data-stu-id="27a1c-139">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="27a1c-140">일정 시간 후에 올바르게 응답 하지 않았거나</span><span class="sxs-lookup"><span data-stu-id="27a1c-140">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="27a1c-141">연결 된 호스트에서 연결이 실패 했습니다.</span><span class="sxs-lookup"><span data-stu-id="27a1c-141">established connection failed because connected host has</span></span>

<span data-ttu-id="27a1c-142">10.188.116.96에 응답 하지 못했습니다. 5061</span><span class="sxs-lookup"><span data-stu-id="27a1c-142">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="27a1c-143">내부 예외:</span><span class="sxs-lookup"><span data-stu-id="27a1c-143">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="27a1c-144">일정 기간 후에 연결 된 파티가 제대로 응답 하지 않음</span><span class="sxs-lookup"><span data-stu-id="27a1c-144">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="27a1c-145">연결 된 호스트 때문에 시간이 나 연결에 실패 했습니다.</span><span class="sxs-lookup"><span data-stu-id="27a1c-145">time, or established connection failed because connected host</span></span>

<span data-ttu-id="27a1c-146">에서 10.188.116.96에 응답 하지 못했습니다. 5061</span><span class="sxs-lookup"><span data-stu-id="27a1c-146">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="27a1c-147">진단을</span><span class="sxs-lookup"><span data-stu-id="27a1c-147">Diagnosis :</span></span>

<span data-ttu-id="27a1c-148">예를 들어 이전 출력에는 일반적으로에 지 서버에 문제가 있음을 나타내는 "연결 된 당사자가 제대로 응답 하지 않았습니다." 라는 노트가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="27a1c-148">For example, the previous output includes the note “the connected party did not properly respond” That typically indicates a problem with the Edge Server.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="27a1c-149">테스트가 실패 한 이유</span><span class="sxs-lookup"><span data-stu-id="27a1c-149">Reasons why the test might have failed</span></span>

<span data-ttu-id="27a1c-150">**테스트-CsASConference** 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="27a1c-150">Here are some common reasons why **Test-CsASConference** might fail:</span></span>

  - <span data-ttu-id="27a1c-151">잘못 된 매개 변수 값이 제공 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="27a1c-151">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="27a1c-152">사용 하는 경우 선택적 매개 변수를 올바르게 구성 해야 하며 그렇지 않으면 테스트가 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="27a1c-152">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="27a1c-153">선택적 매개 변수 없이 명령을 다시 실행 하 여 성공 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="27a1c-153">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="27a1c-154">테스트 사용자에 게 응용 프로그램 공유 사용을 금지 하는 회의 정책이 할당 된 경우에는이 명령이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="27a1c-154">This command will fail if the test users were assigned a conferencing policy that prevents them from using application sharing.</span></span>

  - <span data-ttu-id="27a1c-155">에 지 서버가 잘못 구성 되었거나 아직 배포 되지 않은 경우에는이 명령이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="27a1c-155">This command will fail if the Edge Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="27a1c-156">참고 항목</span><span class="sxs-lookup"><span data-stu-id="27a1c-156">See Also</span></span>


[<span data-ttu-id="27a1c-157">Get-csconferencingpolicy</span><span class="sxs-lookup"><span data-stu-id="27a1c-157">Get-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsConferencingPolicy)  
[<span data-ttu-id="27a1c-158">Test-csdataconference</span><span class="sxs-lookup"><span data-stu-id="27a1c-158">Test-CsDataConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsDataConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

