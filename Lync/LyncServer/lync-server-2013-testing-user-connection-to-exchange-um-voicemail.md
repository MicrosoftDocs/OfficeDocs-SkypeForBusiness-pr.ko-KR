---
title: 'Lync Server 2013: Exchange UM 음성 사서함에 대 한 사용자 연결을 테스트 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing user connection to Exchange UM voicemail
ms:assetid: 574da104-8823-4061-9fb6-353639f1884d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727305(v=OCS.15)
ms:contentKeyID: 63969604
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4812f36d19f9645f926eb1aa4f017d70befa47a7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503895"
---
# <a name="testing-user-connection-to-exchange-um-voicemail-in-lync-server-2013"></a><span data-ttu-id="998a2-102">Lync Server 2013에서 Exchange UM 음성 메일에 대 한 사용자 연결 테스트</span><span class="sxs-lookup"><span data-stu-id="998a2-102">Testing user connection to Exchange UM voicemail in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="998a2-103">_**마지막으로 수정 된 항목:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="998a2-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="998a2-104">확인 일정</span><span class="sxs-lookup"><span data-stu-id="998a2-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="998a2-105">매일</span><span class="sxs-lookup"><span data-stu-id="998a2-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="998a2-106">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="998a2-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="998a2-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="998a2-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="998a2-108">필요한 권한</span><span class="sxs-lookup"><span data-stu-id="998a2-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="998a2-109">Lync Server 관리 셸을 사용 하 여 로컬로 실행 하는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="998a2-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="998a2-110">Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우에는 사용자에 게 <strong>테스트-CsExUMVoiceMail</strong> cmdlet을 실행할 수 있는 권한이 있는 RBAC 역할을 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="998a2-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsExUMVoiceMail</strong> cmdlet.</span></span> <span data-ttu-id="998a2-111">이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="998a2-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExUMVoiceMail&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="998a2-112">설명</span><span class="sxs-lookup"><span data-stu-id="998a2-112">Description</span></span>

<span data-ttu-id="998a2-113">**테스트-CsExUMVoiceMail** cmdlet을 사용 하면 관리자가 사용자가 Microsoft Exchange Server 2013 통합 메시징 서비스에 액세스 하 여 사용할 수 있는지를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="998a2-113">The **Test-CsExUMVoiceMail** cmdlet enables administrators to verify that a user can access and use the Microsoft Exchange Server 2013 unified messaging service.</span></span> <span data-ttu-id="998a2-114">이 작업을 수행하기 위해 cmdlet은 통합 메시징 서비스에 연결하여 지정된 사서함에 음성 메일을 남깁니다.</span><span class="sxs-lookup"><span data-stu-id="998a2-114">To do this, the cmdlet connects to the unified messaging service and leaves a voice mail in the specified mailbox.</span></span> <span data-ttu-id="998a2-115">이 메일은 시스템에서 제공한 음성 메일일 수도 있고 직접 녹음한 사용자 지정 .WAV 파일일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="998a2-115">This can be a system-supplied voice mail, or it can be a custom .WAV file that you have recorded yourself.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="998a2-116">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="998a2-116">Running the test</span></span>

<span data-ttu-id="998a2-117">다음 예에서는 atl-cs-001.litwareinc.com 풀에 대 한 Exchange 통합 메시징 음성 메일 연결을 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="998a2-117">The following example tests Exchange Unified Messaging voice mail connectivity for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="998a2-118">이 명령은 atl-cs-001.litwareinc.com 풀에 대해 테스트 사용자가 정의 된 경우에만 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="998a2-118">This command will work only if test users were defined for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="998a2-119">이러한 경우에는 명령에 따라 첫 번째 테스트 사용자가 통합 메시징 음성 메일을 사용할 수 있는지 여부가 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="998a2-119">If they have, then the command will determine whether the first test user can use Unified Messaging voice mail.</span></span> <span data-ttu-id="998a2-120">테스트 사용자가 풀에 대해 구성 되지 않은 경우이 명령은 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="998a2-120">If test users were not configured for the pool then the command will fail.</span></span>

    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" 

<span data-ttu-id="998a2-121">다음 예에 나와 있는 명령은 사용자 litwareinc kenmyer에 대 한 Exchange 통합 메시징 음성 메일 연결을 테스트 합니다 \\ .</span><span class="sxs-lookup"><span data-stu-id="998a2-121">The commands shown in the next example test Exchange Unified Messaging voice mail connectivity for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="998a2-122">이 작업을 수행 하기 위해 예제의 첫 번째 명령은 **Get-Credential** cmdlet을 사용 하 여 사용자 litwareinc kenmyer에 대 한 Windows PowerShell 명령줄 인터페이스 자격 증명 개체를 만듭니다 \\ .</span><span class="sxs-lookup"><span data-stu-id="998a2-122">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credentials object for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="998a2-123">이 계정의 암호를 입력 하 여 유효한 자격 증명 개체를 만들고, **테스트-CsExUMVoiceMail** cmdlet이 검사를 실행할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="998a2-123">Note that you must supply the password for this account to create a valid credentials object and to ensure that the **Test-CsExUMVoiceMail** cmdlet can run its check.</span></span>

<span data-ttu-id="998a2-124">예제의 두 번째 명령은 제공 된 자격 증명 개체 ($x)와 사용자 litwareinc kenmyer의 SIP 주소 \\ 를 사용 하 여이 사용자가 Exchange 통합 메시징 음성 메일에 연결할 수 있는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="998a2-124">The second command in the example uses the supplied credentials object ($x) and the SIP address of the user litwareinc\\kenmyer to determine whether or this user can connect to Exchange Unified Messaging voice mail.</span></span>

    $credential = Get-Credential "litwareinc\pilar" 
    
    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential 

<span data-ttu-id="998a2-125">다음 예제에 표시 된 명령은 예제 1에 표시 된 명령의 변형입니다. 이 경우에는 OutLoggerVariable 매개 변수를 포함 하 여 **테스트-Ceumcmdlet로** 완료 된 모든 단계의 자세한 로그와 이러한 각 단계의 성공 또는 실패를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="998a2-125">The command shown in the next example is a variation of the command shown in Example 1; in this case, the OutLoggerVariable parameter is included to generate a detailed log of every step done by the **Test-CsExUMVoiceMail** cmdletand the success or failure of each of those steps.</span></span> <span data-ttu-id="998a2-126">이렇게 하려면 OutLoggerVariable 매개 변수가 ExumText 매개 변수 값과 함께 추가 됩니다. 이로 인해 자세한 로깅 정보가 $ExumTest 라는 변수에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="998a2-126">To do this, the OutLoggerVariable parameter is added alongside the parameter value ExumText; that causes detailed logging information to be stored in a variable named $ExumTest.</span></span> <span data-ttu-id="998a2-127">예제의 마지막 명령에서 ToXML () 메서드를 사용 하 여 로그 정보를 XML 형식으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="998a2-127">In the final command in the example, the ToXML() method is used to convert the log information to XML format.</span></span> <span data-ttu-id="998a2-128">이 XML 데이터는 Out-File cmdlet을 사용 하 여 이름이 C: Logs 인 파일에 기록 됩니다 \\ \\VoicemailTest.xml.</span><span class="sxs-lookup"><span data-stu-id="998a2-128">That XML data is then written to a file that is named C:\\Logs\\VoicemailTest.xml by using the Out-File cmdlet.</span></span>

    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -OutLoggerVariable VoicemailTest 
     
    $VoicemailTest.ToXML() | Out-File C:\Logs\VoicemailTest.xml

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="998a2-129">성공 또는 실패 확인</span><span class="sxs-lookup"><span data-stu-id="998a2-129">Determining success or failure</span></span>

<span data-ttu-id="998a2-130">Exchange 통합이 올바르게 구성 되 면 다음과 비슷한 출력을 받게 되며 Result 속성은 **Success**로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="998a2-130">If Exchange integration is correctly configured, you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="998a2-131">대상 Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="998a2-131">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="998a2-132">결과: 성공</span><span class="sxs-lookup"><span data-stu-id="998a2-132">Result : Success</span></span>

<span data-ttu-id="998a2-133">대기 시간: 00:00:02.9911345</span><span class="sxs-lookup"><span data-stu-id="998a2-133">Latency : 00:00:02.9911345</span></span>

<span data-ttu-id="998a2-134">오류 메시지:</span><span class="sxs-lookup"><span data-stu-id="998a2-134">Error Message :</span></span>

<span data-ttu-id="998a2-135">진단을</span><span class="sxs-lookup"><span data-stu-id="998a2-135">Diagnosis :</span></span>

<span data-ttu-id="998a2-136">지정 된 사용자가 음성 메일에 연결할 수 없으면 결과가 **실패로**표시 되 고 오류 및 진단 속성에 추가 정보가 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="998a2-136">If the specified user can't connect to voicemail, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="998a2-137">경고: 지정한 정규화 된 자격에 대 한 등록자 포트 번호를 읽지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="998a2-137">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="998a2-138">FQDN (도메인 이름)</span><span class="sxs-lookup"><span data-stu-id="998a2-138">domain name (FQDN).</span></span> <span data-ttu-id="998a2-139">기본 등록자 포트 번호 사용</span><span class="sxs-lookup"><span data-stu-id="998a2-139">Using default Registrar port number.</span></span> <span data-ttu-id="998a2-140">오류</span><span class="sxs-lookup"><span data-stu-id="998a2-140">Exception:</span></span>

<span data-ttu-id="998a2-141">InvalidOperationException: 토폴로지에서 일치 하는 클러스터를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="998a2-141">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="998a2-142">구독자</span><span class="sxs-lookup"><span data-stu-id="998a2-142">at</span></span>

<span data-ttu-id="998a2-143">SyntheticTransactions SipSyntheticTransaction TryRetri를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="998a2-143">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="998a2-144">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="998a2-144">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="998a2-145">대상 Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="998a2-145">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="998a2-146">결과: 실패</span><span class="sxs-lookup"><span data-stu-id="998a2-146">Result : Failure</span></span>

<span data-ttu-id="998a2-147">대기 시간: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="998a2-147">Latency : 00:00:00</span></span>

<span data-ttu-id="998a2-148">오류 메시지: 10060, 연결 된 파티 때문에 연결 시도가 실패 했습니다.</span><span class="sxs-lookup"><span data-stu-id="998a2-148">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="998a2-149">일정 시간 후에 올바르게 응답 하지 않았거나</span><span class="sxs-lookup"><span data-stu-id="998a2-149">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="998a2-150">연결 된 호스트에서 연결이 실패 했습니다.</span><span class="sxs-lookup"><span data-stu-id="998a2-150">established connection failed because connected host has</span></span>

<span data-ttu-id="998a2-151">10.188.116.96에 응답 하지 못했습니다. 5061</span><span class="sxs-lookup"><span data-stu-id="998a2-151">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="998a2-152">내부 예외:</span><span class="sxs-lookup"><span data-stu-id="998a2-152">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="998a2-153">일정 기간 후에 연결 된 파티가 제대로 응답 하지 않음</span><span class="sxs-lookup"><span data-stu-id="998a2-153">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="998a2-154">연결 된 호스트 때문에 시간이 나 연결에 실패 했습니다.</span><span class="sxs-lookup"><span data-stu-id="998a2-154">time, or established connection failed because connected host</span></span>

<span data-ttu-id="998a2-155">에서 10.188.116.96에 응답 하지 못했습니다. 5061</span><span class="sxs-lookup"><span data-stu-id="998a2-155">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="998a2-156">진단을</span><span class="sxs-lookup"><span data-stu-id="998a2-156">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="998a2-157">테스트가 실패 한 이유</span><span class="sxs-lookup"><span data-stu-id="998a2-157">Reasons why the test might have failed</span></span>

<span data-ttu-id="998a2-158">**Test-CsExUMVoiceMail에서** 오류가 발생할 수 있는 일반적인 몇 가지 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="998a2-158">Here are some common reasons why **Test-CsExUMVoiceMail** might fail:</span></span>

  - <span data-ttu-id="998a2-159">잘못 된 매개 변수 값이 제공 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="998a2-159">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="998a2-160">사용 하는 경우 선택적 매개 변수를 올바르게 구성 해야 하며 그렇지 않으면 테스트가 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="998a2-160">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="998a2-161">선택적 매개 변수 없이 명령을 다시 실행 하 여 성공 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="998a2-161">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="998a2-162">Exchange 서버가 잘못 구성 되었거나 아직 배포 되지 않은 경우에는이 명령이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="998a2-162">This command will fail if the Exchange Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="998a2-163">참고 항목</span><span class="sxs-lookup"><span data-stu-id="998a2-163">See Also</span></span>


[<span data-ttu-id="998a2-164">Test-csexumconnectivity</span><span class="sxs-lookup"><span data-stu-id="998a2-164">Test-CsExUMConnectivity</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMConnectivity)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

