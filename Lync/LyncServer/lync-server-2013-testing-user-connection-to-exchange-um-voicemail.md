---
title: 'Lync Server 2013: Exchange UM 보이스 메일에 대 한 사용자 연결 테스트'
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
ms.openlocfilehash: c533781fedc3bf3d6266bae80e5c59cacbec4874
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745388"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-user-connection-to-exchange-um-voicemail-in-lync-server-2013"></a><span data-ttu-id="fc002-102">Lync Server 2013에서 Exchange UM 보이스 메일에 대 한 사용자 연결 테스트</span><span class="sxs-lookup"><span data-stu-id="fc002-102">Testing user connection to Exchange UM voicemail in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fc002-103">_**마지막으로 수정한 주제:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="fc002-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fc002-104">확인 일정</span><span class="sxs-lookup"><span data-stu-id="fc002-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="fc002-105">Daily</span><span class="sxs-lookup"><span data-stu-id="fc002-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc002-106">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="fc002-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="fc002-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fc002-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fc002-108">권한이 필요 함</span><span class="sxs-lookup"><span data-stu-id="fc002-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="fc002-109">Lync Server Management Shell을 사용 하 여 로컬에서 실행 되는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc002-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="fc002-110">Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 사용자에 게 <strong>테스트-CsExUMVoiceMail 메일</strong> cmdlet을 실행할 권한이 있는 RBAC 역할을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc002-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsExUMVoiceMail</strong> cmdlet.</span></span> <span data-ttu-id="fc002-111">이 cmdlet을 사용할 수 있는 모든 RBAC 역할 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc002-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExUMVoiceMail&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="fc002-112">설명</span><span class="sxs-lookup"><span data-stu-id="fc002-112">Description</span></span>

<span data-ttu-id="fc002-113">관리자는 사용자가 Microsoft Exchange Server 2013 통합 메시징 서비스에 액세스 하 여 사용할 수 있는지 여부를 **테스트** 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc002-113">The **Test-CsExUMVoiceMail** cmdlet enables administrators to verify that a user can access and use the Microsoft Exchange Server 2013 unified messaging service.</span></span> <span data-ttu-id="fc002-114">이렇게 하려면 cmdlet이 통합 메시징 서비스에 연결 하 고 지정 된 사서함에 음성 메일을 남겨 둡니다.</span><span class="sxs-lookup"><span data-stu-id="fc002-114">To do this, the cmdlet connects to the unified messaging service and leaves a voice mail in the specified mailbox.</span></span> <span data-ttu-id="fc002-115">시스템에서 제공 하는 음성 메일 또는 사용자 지정이 될 수 있습니다. WAV 파일을 직접 녹음/녹화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc002-115">This can be a system-supplied voice mail, or it can be a custom .WAV file that you have recorded yourself.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="fc002-116">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="fc002-116">Running the test</span></span>

<span data-ttu-id="fc002-117">다음 예에서는 풀 atl-cs-001.litwareinc.com에 대 한 Exchange 통합 메시징 음성 메일 연결을 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc002-117">The following example tests Exchange Unified Messaging voice mail connectivity for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="fc002-118">이 명령은 풀 atl-cs-001.litwareinc.com에 대해 테스트 사용자가 정의 된 경우에만 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc002-118">This command will work only if test users were defined for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="fc002-119">그렇지 않은 경우 명령에서 첫 번째 테스트 사용자가 통합 메시징 음성 메일을 사용할 수 있는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc002-119">If they have, then the command will determine whether the first test user can use Unified Messaging voice mail.</span></span> <span data-ttu-id="fc002-120">테스트 사용자가 풀에 대해 구성 되지 않은 경우에는 명령이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc002-120">If test users were not configured for the pool then the command will fail.</span></span>

    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" 

<span data-ttu-id="fc002-121">다음 예제에 나와 있는 명령은 사용자 litwareinc\\kenmyer에 대 한 Exchange 통합 메시징 음성 메일 연결을 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc002-121">The commands shown in the next example test Exchange Unified Messaging voice mail connectivity for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="fc002-122">이렇게 하려면 예제의 첫 번째 명령은 **Get-Credential** cmdlet을 사용 하 여 사용자 litwareinc\\Kenmyer에 대 한 Windows PowerShell 명령줄 인터페이스 자격 증명 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fc002-122">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credentials object for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="fc002-123">유효한 자격 증명 개체를 만들기 위해이 계정에 대 한 암호를 제공 하 고 **테스트-CsExUMVoiceMail 메일** cmdlet이 검사를 실행할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc002-123">Note that you must supply the password for this account to create a valid credentials object and to ensure that the **Test-CsExUMVoiceMail** cmdlet can run its check.</span></span>

<span data-ttu-id="fc002-124">이 예제의 두 번째 명령은 제공 된 자격 증명 개체 ($x)와 사용자 litwareinc\\KENMYER의 SIP 주소를 사용 하 여이 사용자가 Exchange 통합 메시징 음성 메일에 연결할 수 있는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc002-124">The second command in the example uses the supplied credentials object ($x) and the SIP address of the user litwareinc\\kenmyer to determine whether or this user can connect to Exchange Unified Messaging voice mail.</span></span>

    $credential = Get-Credential "litwareinc\pilar" 
    
    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential 

<span data-ttu-id="fc002-125">다음 예제에 표시 되는 명령은 예제 1에 표시 된 명령의 변형입니다. 이 경우 OutLoggerVariable 매개 변수는 **테스트-c** ...의 모든 단계에 대 한 자세한 로그를 생성 하는 데 포함 되며, 이러한 각 단계의 성공 또는 실패입니다.</span><span class="sxs-lookup"><span data-stu-id="fc002-125">The command shown in the next example is a variation of the command shown in Example 1; in this case, the OutLoggerVariable parameter is included to generate a detailed log of every step done by the **Test-CsExUMVoiceMail** cmdletand the success or failure of each of those steps.</span></span> <span data-ttu-id="fc002-126">이렇게 하려면 OutLoggerVariable 매개 변수를 매개 변수 값으로 ExumText와 함께 추가 합니다. 이렇게 하면 자세한 로깅 정보가 $ExumTest 라는 변수에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc002-126">To do this, the OutLoggerVariable parameter is added alongside the parameter value ExumText; that causes detailed logging information to be stored in a variable named $ExumTest.</span></span> <span data-ttu-id="fc002-127">예제의 마지막 명령에서 ToXML () 메서드를 사용 하 여 로그 정보를 XML 형식으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc002-127">In the final command in the example, the ToXML() method is used to convert the log information to XML format.</span></span> <span data-ttu-id="fc002-128">그런 다음 VoicemailTest cmdlet을 사용 하 여 XML 데이터를 C:\\Logs\\라는 파일에 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc002-128">That XML data is then written to a file that is named C:\\Logs\\VoicemailTest.xml by using the Out-File cmdlet.</span></span>

    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -OutLoggerVariable VoicemailTest 
     
    $VoicemailTest.ToXML() | Out-File C:\Logs\VoicemailTest.xml

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="fc002-129">성공 또는 실패 확인</span><span class="sxs-lookup"><span data-stu-id="fc002-129">Determining success or failure</span></span>

<span data-ttu-id="fc002-130">Exchange 통합이 올바르게 구성 되 면 다음과 비슷한 출력이 표시 되 고 결과 속성이 **성공**으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc002-130">If Exchange integration is correctly configured, you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="fc002-131">대상 Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="fc002-131">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="fc002-132">결과: 성공</span><span class="sxs-lookup"><span data-stu-id="fc002-132">Result : Success</span></span>

<span data-ttu-id="fc002-133">대기 시간: 00:00:02.9911345</span><span class="sxs-lookup"><span data-stu-id="fc002-133">Latency : 00:00:02.9911345</span></span>

<span data-ttu-id="fc002-134">오류 메시지:</span><span class="sxs-lookup"><span data-stu-id="fc002-134">Error Message :</span></span>

<span data-ttu-id="fc002-135">있게</span><span class="sxs-lookup"><span data-stu-id="fc002-135">Diagnosis :</span></span>

<span data-ttu-id="fc002-136">지정 된 사용자가 보이스 메일에 연결할 수 없는 경우 결과가 **실패로**표시 되 고 오류 및 진단 속성에 추가 정보가 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc002-136">If the specified user can't connect to voicemail, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="fc002-137">경고: 정규화 된 정식 #b0에 대 한 등록자 포트 번호를 읽지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="fc002-137">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="fc002-138">도메인 이름 (FQDN).</span><span class="sxs-lookup"><span data-stu-id="fc002-138">domain name (FQDN).</span></span> <span data-ttu-id="fc002-139">기본 등록자 포트 번호를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc002-139">Using default Registrar port number.</span></span> <span data-ttu-id="fc002-140">발생</span><span class="sxs-lookup"><span data-stu-id="fc002-140">Exception:</span></span>

<span data-ttu-id="fc002-141">InvalidOperationException: 토폴로지에서 일치 하는 클러스터를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fc002-141">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="fc002-142">배포자</span><span class="sxs-lookup"><span data-stu-id="fc002-142">at</span></span>

<span data-ttu-id="fc002-143">SyntheticTransactions. SipSyntheticTransaction. TryRetri</span><span class="sxs-lookup"><span data-stu-id="fc002-143">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="fc002-144">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="fc002-144">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="fc002-145">대상 Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="fc002-145">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="fc002-146">결과: 실패</span><span class="sxs-lookup"><span data-stu-id="fc002-146">Result : Failure</span></span>

<span data-ttu-id="fc002-147">대기 시간: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="fc002-147">Latency : 00:00:00</span></span>

<span data-ttu-id="fc002-148">오류 메시지: 10060, 연결 된 파티 때문에 연결 시도가 실패 했습니다.</span><span class="sxs-lookup"><span data-stu-id="fc002-148">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="fc002-149">일정 시간 후에 제대로 응답 하지 않았거나</span><span class="sxs-lookup"><span data-stu-id="fc002-149">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="fc002-150">연결 된 호스트가 다음 연결에 실패 하 여 성립</span><span class="sxs-lookup"><span data-stu-id="fc002-150">established connection failed because connected host has</span></span>

<span data-ttu-id="fc002-151">10.188.116.96에 응답 하지 못했습니다: 5061</span><span class="sxs-lookup"><span data-stu-id="fc002-151">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="fc002-152">내부 예외: 다음 이유로 인해 연결 시도가 실패 했습니다.</span><span class="sxs-lookup"><span data-stu-id="fc002-152">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="fc002-153">연결 된 상대방이 일정 기간 후에 적절 하 게 응답 하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="fc002-153">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="fc002-154">연결 된 호스트 때문에 시간이 나 연결에 실패 했습니다.</span><span class="sxs-lookup"><span data-stu-id="fc002-154">time, or established connection failed because connected host</span></span>

<span data-ttu-id="fc002-155">님이 10.188.116.96에 응답 하지 못했습니다: 5061</span><span class="sxs-lookup"><span data-stu-id="fc002-155">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="fc002-156">있게</span><span class="sxs-lookup"><span data-stu-id="fc002-156">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="fc002-157">테스트가 실패할 수 있는 이유</span><span class="sxs-lookup"><span data-stu-id="fc002-157">Reasons why the test might have failed</span></span>

<span data-ttu-id="fc002-158">다음은 **테스트-CsExUMVoiceMail 메일이** 실패할 수 있는 몇 가지 일반적인 이유입니다.</span><span class="sxs-lookup"><span data-stu-id="fc002-158">Here are some common reasons why **Test-CsExUMVoiceMail** might fail:</span></span>

  - <span data-ttu-id="fc002-159">잘못 된 매개 변수 값이 제공 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fc002-159">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="fc002-160">사용 하는 경우 선택적 매개 변수를 올바르게 구성 하거나 테스트에 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc002-160">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="fc002-161">선택적 매개 변수 없이 명령을 다시 실행 하 여 성공 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc002-161">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="fc002-162">Exchange 서버가 잘못 구성 되었거나 아직 배포 되지 않은 경우에는이 명령이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc002-162">This command will fail if the Exchange Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fc002-163">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fc002-163">See Also</span></span>


[<span data-ttu-id="fc002-164">Test-CsExUMConnectivity</span><span class="sxs-lookup"><span data-stu-id="fc002-164">Test-CsExUMConnectivity</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMConnectivity)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

