---
title: 'Lync Server 2013: 응용 프로그램 공유 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing application sharing
ms:assetid: 8d21db9b-10d1-4b43-b057-0deb1df1c205
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727310(v=OCS.15)
ms:contentKeyID: 63969629
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77a65e2dbea8ca0df01fab37c08f47c8e7d0c5b6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983826"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-application-sharing-in-lync-server-2013"></a><span data-ttu-id="28a7a-102">Lync Server 2013에서 응용 프로그램 공유 테스트</span><span class="sxs-lookup"><span data-stu-id="28a7a-102">Testing application sharing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="28a7a-103">_**마지막으로 수정한 주제:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="28a7a-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="28a7a-104">확인 일정</span><span class="sxs-lookup"><span data-stu-id="28a7a-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="28a7a-105">Daily</span><span class="sxs-lookup"><span data-stu-id="28a7a-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28a7a-106">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="28a7a-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="28a7a-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="28a7a-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="28a7a-108">권한이 필요 함</span><span class="sxs-lookup"><span data-stu-id="28a7a-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="28a7a-109">Lync Server Management Shell을 사용 하 여 로컬에서 실행 되는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="28a7a-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="28a7a-110">Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 사용자에 게 테스트 CsASConference cmdlet을 실행할 수 있는 권한이 있는 RBAC 역할을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="28a7a-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsASConference cmdlet.</span></span> <span data-ttu-id="28a7a-111">이 cmdlet을 사용할 수 있는 모든 RBAC 역할 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="28a7a-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsASConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="28a7a-112">설명</span><span class="sxs-lookup"><span data-stu-id="28a7a-112">Description</span></span>

<span data-ttu-id="28a7a-113">**테스트-CsASConference** cmdlet은 테스트 사용자 쌍이 응용 프로그램 공유를 포함 하는 온라인 회의에 참가할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="28a7a-113">The **Test-CsASConference** cmdlet verifies that a pair of test users can participate in an online conference that includes application sharing.</span></span> <span data-ttu-id="28a7a-114">이를 위해 cmdlet은 두 사용자를 Lync Server 2013에 등록 한 다음 사용자 계정 중 하나를 사용 하 여 응용 프로그램 공유가 포함 된 새 회의를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="28a7a-114">To do this, the cmdlet registers the two users with Lync Server 2013, and then it uses one of the user accounts to create a new conference that includes applications sharing.</span></span> <span data-ttu-id="28a7a-115">그런 다음 cmdlet은 두 번째 사용자가 해당 회의에 참가할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="28a7a-115">The cmdlet then verifies that the second user is able to join that conference.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="28a7a-116">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="28a7a-116">Running the test</span></span>

<span data-ttu-id="28a7a-117">예제 1에 표시 된 명령은 풀 atl-cs-001.litwareinc.com에서 응용 프로그램 공유 회의가 수행 될 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="28a7a-117">The command shown in Example 1 verifies that an Application Sharing conference can be conducted on the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="28a7a-118">이 명령은 지정 된 풀에 대 한 한 쌍의 테스트 사용자를 구성 했다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="28a7a-118">This command assumes that you have configured a pair of test users for the specified pool.</span></span> <span data-ttu-id="28a7a-119">그러한 테스트 사용자가 없는 경우 명령이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="28a7a-119">If no such test users exist, the command will fail.</span></span>

    Test-CsASConference -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="28a7a-120">예제 2에서는 Join 시작 관리자 서비스가 풀 atl-cs-001.litwareinc.com의 응용 프로그램 공유 회의에 참여할 수 있는지 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="28a7a-120">Example 2 tests the ability of the Join Launcher service to participate in an Application Sharing conference on the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="28a7a-121">이 명령은 서비스 자체만을 테스트 합니다. 명령을 실행 하기 위해 모바일 장치가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="28a7a-121">Note that this command tests only the service itself; you do not need any mobile devices in order to run the command.</span></span>

    Test-CsASConference -TargetFqdn "atl-cs-001.litwareinc.com" -TestJoinLauncher 

<span data-ttu-id="28a7a-122">예제 2에 나와 있는 명령은 사용자 쌍 (litwareinc\\pilar 및 litwareinc\\kenmyer)의 기능을 테스트 하 여 Lync Server 2013에 로그온 한 다음 응용 프로그램 공유 회의를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="28a7a-122">The commands shown in Example 2 test the ability of a pair of users (litwareinc\\pilar and litwareinc\\kenmyer) to log on to Lync Server 2013 and then conduct an Application Sharing conference.</span></span> <span data-ttu-id="28a7a-123">이렇게 하려면이 예제의 첫 번째 명령은 Get-Credential cmdlet을 사용 하 여 사용자 Pilar Ackerman의 이름과 암호를 포함 하는 Windows PowerShell 명령줄 인터페이스 자격 증명 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="28a7a-123">To do this, the first command in the example uses the Get-Credential cmdlet to create a Windows PowerShell command-line interface credential object containing the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="28a7a-124">(로그온 이름 litwareinc\\pilar는 매개 변수로 포함 되어 있기 때문에 Windows PowerShell 자격 증명 요청 대화 상자에서는 관리자만 Pilar Ackerman 계정에 대 한 암호를 입력 해야 합니다.) 그런 다음 결과 credential 개체는 $cred 1 이라는 변수에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="28a7a-124">(Because the logon name, litwareinc\\pilar, has been included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credential object is then stored in a variable named $cred1.</span></span> <span data-ttu-id="28a7a-125">두 번째 명령은: 진구 Myer account에 대 한 credential 개체를 반환 하는 것과 동일한 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="28a7a-125">The second command does the same thing, this time returning a credential object for the Ken Myer account.</span></span>

<span data-ttu-id="28a7a-126">자격 증명 개체를 사용 하는 경우 세 번째 명령은 이러한 두 사용자가 Lync Server 2013에 로그온 하 고 응용 프로그램 공유 회의를 수행할 수 있는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="28a7a-126">With the credential objects in hand, the third command determines whether or not these two users can log on to Lync Server 2013 and conduct an Application Sharing conference.</span></span> <span data-ttu-id="28a7a-127">이 작업을 수행 하기 위해 **테스트 CsASConference** cmdlet이 다음 매개 변수와 함께 (targetfqdn (등록자 풀의 fqdn)으로 호출 됩니다. SenderSipAddress (첫 번째 테스트 사용자의 SIP 주소). SenderCredential (같은 사용자에 대 한 자격 증명을 포함 하는 Windows PowerShell 개체) ReceiverSipAddress (다른 테스트 사용자의 SIP 주소). 및 ReceiverCredential (다른 테스트 사용자에 대 한 자격 증명을 포함 하는 Windows PowerShell 개체).</span><span class="sxs-lookup"><span data-stu-id="28a7a-127">To carry out this task, the **Test-CsASConference** cmdlet is called, along with the following parameters: TargetFqdn (the FQDN of the Registrar pool); SenderSipAddress (the SIP address for the first test user); SenderCredential (the Windows PowerShell object containing the credentials for this same user); ReceiverSipAddress (the SIP address for the other test user); and ReceiverCredential (the Windows PowerShell object containing the credentials for the other test user).</span></span>

    $cred1 = Get-Credential "litwareinc\pilar" 
    $cred2 = Get-Credential "litwareinc\kenmyer" 
    Test-CsASConference -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $cred1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="28a7a-128">성공 또는 실패 확인</span><span class="sxs-lookup"><span data-stu-id="28a7a-128">Determining success or failure</span></span>

<span data-ttu-id="28a7a-129">응용 프로그램 공유가 올바르게 구성 되 면 다음과 비슷한 출력이 표시 되 고 결과 속성이 성공으로 표시 됩니다 **.**</span><span class="sxs-lookup"><span data-stu-id="28a7a-129">If application sharing is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="28a7a-130">대상 Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="28a7a-130">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="28a7a-131">결과: 성공</span><span class="sxs-lookup"><span data-stu-id="28a7a-131">Result : Success</span></span>

<span data-ttu-id="28a7a-132">대기 시간: 00:00:01</span><span class="sxs-lookup"><span data-stu-id="28a7a-132">Latency : 00:00:01</span></span>

<span data-ttu-id="28a7a-133">오류 메시지:</span><span class="sxs-lookup"><span data-stu-id="28a7a-133">Error Message :</span></span>

<span data-ttu-id="28a7a-134">있게</span><span class="sxs-lookup"><span data-stu-id="28a7a-134">Diagnosis :</span></span>

<span data-ttu-id="28a7a-135">지정 된 사용자가 응용 프로그램을 공유할 수 없는 경우 결과가 실패로 표시 되 고 오류 및 진단 속성에 추가 정보가 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="28a7a-135">If the specified users can't share applications, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="28a7a-136">대상 Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="28a7a-136">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="28a7a-137">결과: 실패</span><span class="sxs-lookup"><span data-stu-id="28a7a-137">Result : Failure</span></span>

<span data-ttu-id="28a7a-138">대기 시간: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="28a7a-138">Latency : 00:00:00</span></span>

<span data-ttu-id="28a7a-139">오류 메시지: 10060, 연결 된 파티 때문에 연결 시도가 실패 했습니다.</span><span class="sxs-lookup"><span data-stu-id="28a7a-139">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="28a7a-140">일정 시간 후에 제대로 응답 하지 않았거나</span><span class="sxs-lookup"><span data-stu-id="28a7a-140">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="28a7a-141">연결 된 호스트가 다음 연결에 실패 하 여 성립</span><span class="sxs-lookup"><span data-stu-id="28a7a-141">established connection failed because connected host has</span></span>

<span data-ttu-id="28a7a-142">10.188.116.96에 응답 하지 못했습니다: 5061</span><span class="sxs-lookup"><span data-stu-id="28a7a-142">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="28a7a-143">내부 예외: 다음 이유로 인해 연결 시도가 실패 했습니다.</span><span class="sxs-lookup"><span data-stu-id="28a7a-143">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="28a7a-144">연결 된 상대방이 일정 기간 후에 적절 하 게 응답 하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="28a7a-144">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="28a7a-145">연결 된 호스트 때문에 시간이 나 연결에 실패 했습니다.</span><span class="sxs-lookup"><span data-stu-id="28a7a-145">time, or established connection failed because connected host</span></span>

<span data-ttu-id="28a7a-146">님이 10.188.116.96에 응답 하지 못했습니다: 5061</span><span class="sxs-lookup"><span data-stu-id="28a7a-146">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="28a7a-147">있게</span><span class="sxs-lookup"><span data-stu-id="28a7a-147">Diagnosis :</span></span>

<span data-ttu-id="28a7a-148">예를 들어 이전 출력에는 일반적으로 Edge 서버에 문제가 있음을 나타내는 "연결 된 파티가 제대로 응답 하지 않았습니다." 메모가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="28a7a-148">For example, the previous output includes the note “the connected party did not properly respond” That typically indicates a problem with the Edge Server.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="28a7a-149">테스트가 실패할 수 있는 이유</span><span class="sxs-lookup"><span data-stu-id="28a7a-149">Reasons why the test might have failed</span></span>

<span data-ttu-id="28a7a-150">다음은 **테스트-CsASConference** 가 실패할 수 있는 몇 가지 일반적인 이유입니다.</span><span class="sxs-lookup"><span data-stu-id="28a7a-150">Here are some common reasons why **Test-CsASConference** might fail:</span></span>

  - <span data-ttu-id="28a7a-151">잘못 된 매개 변수 값이 제공 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="28a7a-151">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="28a7a-152">사용 하는 경우 선택적 매개 변수를 올바르게 구성 하거나 테스트에 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="28a7a-152">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="28a7a-153">선택적 매개 변수 없이 명령을 다시 실행 하 여 성공 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="28a7a-153">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="28a7a-154">테스트 사용자가 응용 프로그램 공유를 사용 하지 못하도록 하는 회의 정책을 할당 한 경우이 명령은 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="28a7a-154">This command will fail if the test users were assigned a conferencing policy that prevents them from using application sharing.</span></span>

  - <span data-ttu-id="28a7a-155">Edge 서버가 잘못 구성 되었거나 아직 배포 되지 않은 경우에는이 명령이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="28a7a-155">This command will fail if the Edge Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="28a7a-156">참고 항목</span><span class="sxs-lookup"><span data-stu-id="28a7a-156">See Also</span></span>


[<span data-ttu-id="28a7a-157">Get-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="28a7a-157">Get-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsConferencingPolicy)  
[<span data-ttu-id="28a7a-158">Test-CsDataConference</span><span class="sxs-lookup"><span data-stu-id="28a7a-158">Test-CsDataConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsDataConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

