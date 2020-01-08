---
title: 'Lync Server 2013: 회의에서 공유 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing sharing in conferences
ms:assetid: e6021d70-6ed9-414d-954c-06eef397dc1a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727314(v=OCS.15)
ms:contentKeyID: 63969660
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce4cd1a45d1eddf8875d85ff28886b0c04c29cfe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979164"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-sharing-in-conferences-in-lync-server-2013"></a><span data-ttu-id="ed5e1-102">Lync Server 2013에서 회의 공유 테스트</span><span class="sxs-lookup"><span data-stu-id="ed5e1-102">Testing sharing in conferences in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed5e1-103">_**마지막으로 수정한 주제:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="ed5e1-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ed5e1-104">확인 일정</span><span class="sxs-lookup"><span data-stu-id="ed5e1-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="ed5e1-105">Daily</span><span class="sxs-lookup"><span data-stu-id="ed5e1-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed5e1-106">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="ed5e1-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="ed5e1-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ed5e1-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed5e1-108">권한이 필요 함</span><span class="sxs-lookup"><span data-stu-id="ed5e1-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="ed5e1-109">Lync Server Management Shell을 사용 하 여 로컬에서 실행 되는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed5e1-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="ed5e1-110">Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 <strong>CsDataConference</strong> cmdlet을 실행 하는 데 필요한 권한이 있는 RBAC 역할을 사용자에 게 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed5e1-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsDataConference</strong> cmdlet.</span></span> <span data-ttu-id="ed5e1-111">이 cmdlet을 사용할 수 있는 모든 RBAC 역할 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed5e1-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDataConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="ed5e1-112">설명</span><span class="sxs-lookup"><span data-stu-id="ed5e1-112">Description</span></span>

<span data-ttu-id="ed5e1-113">Lync Server 2013에서 데이터 회의는 whiteboarding 또는 주석과 같은 협업 작업을 사용 하는 모든 회의입니다.</span><span class="sxs-lookup"><span data-stu-id="ed5e1-113">In Lync Server 2013, a data conference is any conference where collaborative activities such as whiteboarding or annotations are used.</span></span> <span data-ttu-id="ed5e1-114">**CsDataConference** cmdlet을 사용 하 여 사용자 쌍이 데이터 컨퍼런스에 참여할 수 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed5e1-114">The **Test-CsDataConference** cmdlet enables you to verify that a pair of users are able to take part in a data conference.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="ed5e1-115">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="ed5e1-115">Running the test</span></span>

<span data-ttu-id="ed5e1-116">예제 1에 표시 된 명령은 데이터 회의가 풀 atl-cs-001.litwareinc.com에서 수행 될 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed5e1-116">The command shown in Example 1 verifies that a data conference can be conducted on the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="ed5e1-117">이 명령은 지정 된 풀에 대 한 한 쌍의 테스트 사용자를 구성 했다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed5e1-117">This command assumes that you have configured a pair of test users for the specified pool.</span></span> <span data-ttu-id="ed5e1-118">그러한 테스트 사용자가 없는 경우 명령이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed5e1-118">If no such test users exist, the command will fail.</span></span>

    Test-CsDataConference -TargetFqdn "atl-cs-001.litwareinc.com" 

<span data-ttu-id="ed5e1-119">예제 2에 나와 있는 명령은 사용자 쌍 (litwareinc\\pilar 및 litwareinc\\kenmyer)의 기능을 테스트 하 여 Lync Server 2013에 로그온 한 다음 데이터 회의를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed5e1-119">The commands shown in Example 2 test the ability of a pair of users (litwareinc\\pilar and litwareinc\\kenmyer) to log on to Lync Server 2013 and then conduct a data conference.</span></span> <span data-ttu-id="ed5e1-120">이렇게 하려면이 예제의 첫 번째 명령은 **Get-Credential** cmdlet을 사용 하 여 사용자 Pilar Ackerman의 이름과 암호를 포함 하는 Windows PowerShell 명령줄 인터페이스 자격 증명 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ed5e1-120">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credential object containing the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="ed5e1-121">(로그온 이름 litwareinc\\pilar는 매개 변수로 포함 되어 있기 때문에 Windows PowerShell 자격 증명 요청 대화 상자에서는 관리자만 Pilar Ackerman 계정에 대 한 암호를 입력 해야 합니다.) 그런 다음 결과 credential 개체는 $cred 1 이라는 변수에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed5e1-121">(Because the logon name, litwareinc\\pilar, has been included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credential object is then stored in a variable named $cred1.</span></span> <span data-ttu-id="ed5e1-122">두 번째 명령은: 진구 Myer account에 대 한 credential 개체를 반환 하는 것과 동일한 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed5e1-122">The second command does the same thing, this time returning a credential object for the Ken Myer account.</span></span>

<span data-ttu-id="ed5e1-123">자격 증명 개체를 사용 하는 경우 세 번째 명령은 이러한 두 사용자가 Lync Server 2013에 로그온 하 여 데이터 회의를 수행할 수 있는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed5e1-123">With the credential objects in hand, the third command determines whether or not these two users can log on to Lync Server 2013 and conduct a data conference.</span></span> <span data-ttu-id="ed5e1-124">이 작업을 수행 하려면 **CsDataConference** cmdlet이 다음과 같은 매개 변수와 함께 (targetfqdn (등록자 풀의 fqdn)으로 호출 됩니다. SenderSipAddress (첫 번째 테스트 사용자의 SIP 주소). SenderCredential (같은 사용자에 대 한 자격 증명을 포함 하는 Windows PowerShell 개체) ReceiverSipAddress (다른 테스트 사용자의 SIP 주소). 및 ReceiverCredential (다른 테스트 사용자에 대 한 자격 증명을 포함 하는 Windows PowerShell 개체).</span><span class="sxs-lookup"><span data-stu-id="ed5e1-124">To carry out this task, the **Test-CsDataConference** cmdlet is called, along with the following parameters: TargetFqdn (the FQDN of the Registrar pool); SenderSipAddress (the SIP address for the first test user); SenderCredential (the Windows PowerShell object containing the credentials for this same user); ReceiverSipAddress (the SIP address for the other test user); and ReceiverCredential (the Windows PowerShell object containing the credentials for the other test user).</span></span>

    $credential1 = Get-Credential "litwareinc\pilar" 
    $credential2 = Get-Credential "litwareinc\kenmyer" 
    Test-CsDataConference -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $credential2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="ed5e1-125">성공 또는 실패 확인</span><span class="sxs-lookup"><span data-stu-id="ed5e1-125">Determining success or failure</span></span>

<span data-ttu-id="ed5e1-126">데이터 회의가 올바르게 구성 되어 있는 경우 결과 속성이 성공으로 표시 된 것과 비슷한 출력을 받게 됩니다 **.**</span><span class="sxs-lookup"><span data-stu-id="ed5e1-126">If data conferencing is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="ed5e1-127">대상 Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ed5e1-127">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="ed5e1-128">결과: 성공</span><span class="sxs-lookup"><span data-stu-id="ed5e1-128">Result : Success</span></span>

<span data-ttu-id="ed5e1-129">대기 시간: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="ed5e1-129">Latency : 00:00:00</span></span>

<span data-ttu-id="ed5e1-130">오류 메시지:</span><span class="sxs-lookup"><span data-stu-id="ed5e1-130">Error Message :</span></span>

<span data-ttu-id="ed5e1-131">있게</span><span class="sxs-lookup"><span data-stu-id="ed5e1-131">Diagnosis :</span></span>

<span data-ttu-id="ed5e1-132">지정 된 사용자가 데이터 공유를 사용할 수 없는 경우 결과가 **실패로**표시 되 고 오류 및 진단 속성에 추가 정보가 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed5e1-132">If the specified users can't use data sharing, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="ed5e1-133">대상 Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ed5e1-133">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="ed5e1-134">결과: 실패</span><span class="sxs-lookup"><span data-stu-id="ed5e1-134">Result : Failure</span></span>

<span data-ttu-id="ed5e1-135">대기 시간: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="ed5e1-135">Latency : 00:00:00</span></span>

<span data-ttu-id="ed5e1-136">오류 메시지: 10060, 연결 된 파티 때문에 연결 시도가 실패 했습니다.</span><span class="sxs-lookup"><span data-stu-id="ed5e1-136">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="ed5e1-137">일정 시간 후에 제대로 응답 하지 않았거나</span><span class="sxs-lookup"><span data-stu-id="ed5e1-137">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="ed5e1-138">연결 된 호스트가 다음 연결에 실패 하 여 성립</span><span class="sxs-lookup"><span data-stu-id="ed5e1-138">established connection failed because connected host has</span></span>

<span data-ttu-id="ed5e1-139">2001:4898 \[: e8: f39e: 5c9a: ad83:81b3:9944\]: 5061에 응답 하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="ed5e1-139">failed to respond \[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="ed5e1-140">내부 예외: 다음 이유로 인해 연결 시도가 실패 했습니다.</span><span class="sxs-lookup"><span data-stu-id="ed5e1-140">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="ed5e1-141">연결 된 상대방이 일정 기간 후에 적절 하 게 응답 하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="ed5e1-141">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="ed5e1-142">연결 된 호스트 때문에 시간이 나 연결에 실패 했습니다.</span><span class="sxs-lookup"><span data-stu-id="ed5e1-142">time, or established connection failed because connected host</span></span>

<span data-ttu-id="ed5e1-143">님이 응답 하지 못했습니다</span><span class="sxs-lookup"><span data-stu-id="ed5e1-143">has failed to respond</span></span>

<span data-ttu-id="ed5e1-144">\[2001:4898: e8: f39e: 5c9a: ad83:81b3:9944\]: 5061</span><span class="sxs-lookup"><span data-stu-id="ed5e1-144">\[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="ed5e1-145">있게</span><span class="sxs-lookup"><span data-stu-id="ed5e1-145">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="ed5e1-146">테스트가 실패할 수 있는 이유</span><span class="sxs-lookup"><span data-stu-id="ed5e1-146">Reasons why the test might have failed</span></span>

<span data-ttu-id="ed5e1-147">**테스트 CsDataConference** 가 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ed5e1-147">Here are some common reasons why **Test-CsDataConference** might fail:</span></span>

  - <span data-ttu-id="ed5e1-148">잘못 된 매개 변수 값이 제공 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ed5e1-148">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="ed5e1-149">사용 하는 경우 선택적 매개 변수를 올바르게 구성 하거나 테스트에 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed5e1-149">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="ed5e1-150">선택적 매개 변수 없이 명령을 다시 실행 하 여 성공 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed5e1-150">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="ed5e1-151">데이터 회의를 수행 하는 기능은 회의를 이끄는 사용자에 게 할당 된 회의 정책 ( **CsDataConference** cmdlet의 경우 "sender")에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="ed5e1-151">The ability to conduct a data conference depends on the conferencing policy that has been assigned to the user who organized the conference (in the case of the **Test-CsDataConference** cmdlet, that is the "sender").</span></span> <span data-ttu-id="ed5e1-152">이끌이는 자신의 모임에 공동 작업을 포함할 수 없는 경우 (예: 해당 회의 정책에 EnableDataCollaboration 속성이 False로 설정 된 경우)에는 **테스트-CsDataConference** cmdlet이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed5e1-152">If the organizer is not allowed to include collaborative activities in his or her meeting (for example, if his or her conferencing policy has the EnableDataCollaboration property set to False) then the **Test-CsDataConference** cmdlet will fail.</span></span>

  - <span data-ttu-id="ed5e1-153">Edge 서버가 잘못 구성 되었거나 아직 배포 되지 않은 경우에는이 명령이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed5e1-153">This command will fail if the Edge Server is misconfigured or not yet deployed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

