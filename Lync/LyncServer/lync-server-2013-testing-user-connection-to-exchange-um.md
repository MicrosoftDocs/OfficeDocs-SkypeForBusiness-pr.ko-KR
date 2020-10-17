---
title: 'Lync Server 2013: Exchange UM에 대 한 사용자 연결을 테스트 합니다.'
description: 'Lync Server 2013: Exchange UM에 대 한 사용자 연결을 테스트 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing user connection to Exchange UM
ms:assetid: 0b83fbf4-e124-4efd-a0a9-202eb849af82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727300(v=OCS.15)
ms:contentKeyID: 63969573
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea6f7d446fe3fd98db67bab4ffee9cc976202689
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556070"
---
# <a name="testing-user-connection-to-exchange-um-in-lync-server-2013"></a><span data-ttu-id="a25d9-103">Lync Server 2013에서 Exchange UM에 대 한 사용자 연결 테스트</span><span class="sxs-lookup"><span data-stu-id="a25d9-103">Testing user connection to Exchange UM in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a25d9-104">_**마지막으로 수정 된 항목:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="a25d9-104">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a25d9-105">확인 일정</span><span class="sxs-lookup"><span data-stu-id="a25d9-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="a25d9-106">매일</span><span class="sxs-lookup"><span data-stu-id="a25d9-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a25d9-107">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="a25d9-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="a25d9-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a25d9-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a25d9-109">필요한 권한</span><span class="sxs-lookup"><span data-stu-id="a25d9-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="a25d9-110">Lync Server 관리 셸을 사용 하 여 로컬로 실행 하는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a25d9-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="a25d9-111">Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 <strong>test-csexumconnectivity</strong> cmdlet을 실행 하는 권한이 있는 RBAC 역할을 사용자에 게 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a25d9-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsExUMConnectivity</strong> cmdlet.</span></span> <span data-ttu-id="a25d9-112">이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a25d9-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExUMConnectivity&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="a25d9-113">설명</span><span class="sxs-lookup"><span data-stu-id="a25d9-113">Description</span></span>

<span data-ttu-id="a25d9-114">**Test-csexumconnectivity** cmdlet은 지정 된 사용자가 Microsoft Exchange Server 2013 통합 메시징 서비스에 연결할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a25d9-114">The **Test-CsExUMConnectivity** cmdlet verifies that the specified user can connect to the Microsoft Exchange Server 2013 unified messaging service.</span></span> <span data-ttu-id="a25d9-115">이 cmdlet은 서비스에 대 한 연결이 가능한 지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a25d9-115">Note that this cmdlet only verifies that a connection can be made to the service.</span></span> <span data-ttu-id="a25d9-116">서비스 자체를 테스트 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a25d9-116">It does not test the service itself.</span></span> <span data-ttu-id="a25d9-117">사용자 사서함에 실제로 음성 메일 메시지를 남기는 가상 트랜잭션 cmdlet을 사용하여 통합 메시징 서비스를 테스트하려면 Test-CsExUMVoiceMail cmdlet을 사용하십시오.</span><span class="sxs-lookup"><span data-stu-id="a25d9-117">To test the unified messaging service (by running a synthetic transaction cmdlet that actually leaves a voice mail message in a user's mailbox) use the Test-CsExUMVoiceMail cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="a25d9-118">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="a25d9-118">Running the test</span></span>

<span data-ttu-id="a25d9-119">다음 예에서는 atl-cs-001.litwareinc.com 풀에 대 한 Exchange 통합 메시징 연결을 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="a25d9-119">The following example tests Exchange Unified Messaging connectivity for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="a25d9-120">이 명령은 atl-cs-001.litwareinc.com 풀에 대해 테스트 사용자가 정의 된 경우에만 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a25d9-120">This command will work only if test users were defined for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="a25d9-121">이러한 경우에는 명령에 따라 첫 번째 테스트 사용자가 통합 메시징에 연결할 수 있는지 여부가 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a25d9-121">If they have, then the command will determine whether the first test user can connect to Unified Messaging.</span></span> <span data-ttu-id="a25d9-122">테스트 사용자가 풀에 대해 구성 되지 않은 경우이 명령은 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="a25d9-122">If test users were not configured for the pool then the command will fail.</span></span>

    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" 

<span data-ttu-id="a25d9-123">다음 예에 나와 있는 명령은 사용자 litwareinc kenmyer에 대 한 Exchange 통합 메시징 연결을 테스트 합니다 \\ .</span><span class="sxs-lookup"><span data-stu-id="a25d9-123">The commands shown in the following example test Exchange Unified Messaging connectivity for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="a25d9-124">이 작업을 수행 하기 위해 예제의 첫 번째 명령은 **Get-Credential** cmdlet을 사용 하 여 사용자 litwareinc kenmyer에 대 한 Windows PowerShell 명령줄 인터페이스 자격 증명 개체를 만듭니다 \\ .</span><span class="sxs-lookup"><span data-stu-id="a25d9-124">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credentials object for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="a25d9-125">유효한 자격 증명 개체를 만들 수 있도록이 계정의 암호를 입력 하 고 **test-csexumconnectivity** cmdlet이 검사를 실행 하도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a25d9-125">Note that you must supply the password for this account to create a valid credentials object and to ensure that the **Test-CsExUMConnectivity** cmdlet can run its check.</span></span>

<span data-ttu-id="a25d9-126">예제의 두 번째 명령은 제공 된 자격 증명 개체 ($x)와 사용자 litwareinc kenmyer의 SIP 주소 \\ 를 사용 하 여이 사용자가 Exchange 통합 메시징에 연결할 수 있는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a25d9-126">The second command in the example uses the supplied credentials object ($x) and the SIP address of the user litwareinc\\kenmyer to determine whether or this user can connect to Exchange Unified Messaging.</span></span>

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="a25d9-127">다음 예제에 표시 된 명령은 방금 표시 된 명령의 변형입니다.</span><span class="sxs-lookup"><span data-stu-id="a25d9-127">The command shown in the next example is a variation of the command just shown.</span></span> <span data-ttu-id="a25d9-128">이 경우에는 OutLoggerVariable 매개 변수를 포함 하 여 **test-csexumconnectivity** cmdletand 수행한 모든 단계의 자세한 로그와 이러한 각 단계의 성공 또는 실패를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="a25d9-128">In this case, the OutLoggerVariable parameter is included to generate a detailed log of every step done by the **Test-CsExUMConnectivity** cmdletand the success or failure of each of those steps.</span></span> <span data-ttu-id="a25d9-129">이렇게 하려면 OutLoggerVariable 매개 변수 값이 ExumText와 함께 추가 됩니다. 이로 인해 자세한 로깅 정보가 $ExumTest 라는 변수에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a25d9-129">To do this, the OutLoggerVariable parameter is added together with the parameter value ExumText; that causes detailed logging information to be stored in a variable named $ExumTest.</span></span> <span data-ttu-id="a25d9-130">예제의 마지막 명령에서 ToXML () 메서드를 사용 하 여 로그 정보를 XML 형식으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a25d9-130">In the final command in the example, the ToXML() method is used to convert the log information to XML format.</span></span> <span data-ttu-id="a25d9-131">이 XML 데이터는 Out-File cmdlet을 사용 하 여 이름이 C: Logs 인 파일에 기록 됩니다 \\ \\ExumTest.xml.</span><span class="sxs-lookup"><span data-stu-id="a25d9-131">That XML data is then written to a file that is named C:\\Logs\\ExumTest.xml by using the Out-File cmdlet.</span></span>

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential -OutLoggerVariable ExumTest 
    $ExumTest.ToXML() | Out-File C:\Logs\ExumTest.xml 

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="a25d9-132">성공 또는 실패 확인</span><span class="sxs-lookup"><span data-stu-id="a25d9-132">Determining success or failure</span></span>

<span data-ttu-id="a25d9-133">Exchange 통합이 올바르게 구성 되 면 다음과 비슷한 출력을 받게 되며 Result 속성은 **Success**로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a25d9-133">If Exchange integration is correctly configured, you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="a25d9-134">대상 Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="a25d9-134">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="a25d9-135">결과: 성공</span><span class="sxs-lookup"><span data-stu-id="a25d9-135">Result : Success</span></span>

<span data-ttu-id="a25d9-136">대기 시간: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="a25d9-136">Latency : 00:00:00</span></span>

<span data-ttu-id="a25d9-137">오류 메시지:</span><span class="sxs-lookup"><span data-stu-id="a25d9-137">Error Message :</span></span>

<span data-ttu-id="a25d9-138">진단을</span><span class="sxs-lookup"><span data-stu-id="a25d9-138">Diagnosis :</span></span>

<span data-ttu-id="a25d9-139">지정 된 사용자가 알림을 받을 수 없는 경우 결과가 **실패로**표시 되 고 오류 및 진단 속성에 추가 정보가 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a25d9-139">If the specified user can't receive notifications, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="a25d9-140">대상 Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="a25d9-140">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="a25d9-141">결과: 실패</span><span class="sxs-lookup"><span data-stu-id="a25d9-141">Result : Failure</span></span>

<span data-ttu-id="a25d9-142">대기 시간: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="a25d9-142">Latency : 00:00:00</span></span>

<span data-ttu-id="a25d9-143">오류 메시지: 10060, 연결 된 파티 때문에 연결 시도가 실패 했습니다.</span><span class="sxs-lookup"><span data-stu-id="a25d9-143">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="a25d9-144">일정 시간 후에 올바르게 응답 하지 않았거나</span><span class="sxs-lookup"><span data-stu-id="a25d9-144">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="a25d9-145">연결 된 호스트에서 연결이 실패 했습니다.</span><span class="sxs-lookup"><span data-stu-id="a25d9-145">established connection failed because connected host has</span></span>

<span data-ttu-id="a25d9-146">10.188.116.96에 응답 하지 못했습니다. 5061</span><span class="sxs-lookup"><span data-stu-id="a25d9-146">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="a25d9-147">내부 예외:</span><span class="sxs-lookup"><span data-stu-id="a25d9-147">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="a25d9-148">일정 기간 후에 연결 된 파티가 제대로 응답 하지 않음</span><span class="sxs-lookup"><span data-stu-id="a25d9-148">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="a25d9-149">연결 된 호스트 때문에 시간이 나 연결에 실패 했습니다.</span><span class="sxs-lookup"><span data-stu-id="a25d9-149">time, or established connection failed because connected host</span></span>

<span data-ttu-id="a25d9-150">에서 10.188.116.96에 응답 하지 못했습니다. 5061</span><span class="sxs-lookup"><span data-stu-id="a25d9-150">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="a25d9-151">진단을</span><span class="sxs-lookup"><span data-stu-id="a25d9-151">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="a25d9-152">테스트가 실패 한 이유</span><span class="sxs-lookup"><span data-stu-id="a25d9-152">Reasons why the test might have failed</span></span>

<span data-ttu-id="a25d9-153">다음은 **test-csexumconnectivity에서** 오류가 발생할 수 있는 몇 가지 일반적인 이유입니다.</span><span class="sxs-lookup"><span data-stu-id="a25d9-153">Here are some common reasons why **Test-CsExUMConnectivity** might fail:</span></span>

  - <span data-ttu-id="a25d9-154">잘못 된 매개 변수 값이 제공 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a25d9-154">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="a25d9-155">사용 하는 경우 선택적 매개 변수를 올바르게 구성 해야 하며 그렇지 않으면 테스트가 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="a25d9-155">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="a25d9-156">선택적 매개 변수 없이 명령을 다시 실행 하 여 성공 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a25d9-156">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="a25d9-157">Exchange 서버가 잘못 구성 되었거나 아직 배포 되지 않은 경우에는이 명령이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="a25d9-157">This command will fail if the Exchange Server is misconfigured or not yet deployed.</span></span>

  - <span data-ttu-id="a25d9-158">네트워크를 통해 Exchange 서버에 연결할 수 없으면이 명령은 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="a25d9-158">This command will fail if the Exchange Server is not reachable over your network.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a25d9-159">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a25d9-159">See Also</span></span>


[<span data-ttu-id="a25d9-160">테스트-CsExUMVoiceMail 메일</span><span class="sxs-lookup"><span data-stu-id="a25d9-160">Test-CsExUMVoiceMail</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

