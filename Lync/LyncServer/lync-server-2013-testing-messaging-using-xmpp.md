---
title: 'Lync Server 2013: XMPP를 사용 하 여 메시징 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing messaging using XMPP
ms:assetid: ae5305ba-e5fc-4ca0-a805-872b4ebaf981
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727312(v=OCS.15)
ms:contentKeyID: 63969641
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d5a1840e344ee19114cca424822fa1df14028495
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745648"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-messaging-using-xmpp-in-lync-server-2013"></a><span data-ttu-id="85d75-102">Lync Server 2013에서 XMPP를 사용 하 여 메시징 테스트</span><span class="sxs-lookup"><span data-stu-id="85d75-102">Testing messaging using XMPP in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="85d75-103">_**마지막으로 수정한 주제:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="85d75-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="85d75-104">확인 일정</span><span class="sxs-lookup"><span data-stu-id="85d75-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="85d75-105">Daily</span><span class="sxs-lookup"><span data-stu-id="85d75-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85d75-106">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="85d75-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="85d75-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="85d75-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85d75-108">권한이 필요 함</span><span class="sxs-lookup"><span data-stu-id="85d75-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="85d75-109">Lync Server Management Shell을 사용 하 여 로컬에서 실행 되는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85d75-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="85d75-110">Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 사용자에 게는 <strong>테스트-CsXmppIM</strong> cmdlet을 실행할 권한이 있는 RBAC 역할을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85d75-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsXmppIM</strong> cmdlet.</span></span> <span data-ttu-id="85d75-111">이 cmdlet을 사용할 수 있는 모든 RBAC 역할 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="85d75-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsXmppIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="85d75-112">설명</span><span class="sxs-lookup"><span data-stu-id="85d75-112">Description</span></span>

<span data-ttu-id="85d75-113">XMPP (확장할 수 있는 메시징 및 현재 상태 프로토콜)는 인터넷을 통해 메시지를 보내는 데 사용 되는 표준 통신 프로토콜 (XML 기반)입니다.</span><span class="sxs-lookup"><span data-stu-id="85d75-113">The Extensible Messaging and Presence Protocol (XMPP) is a standard communications protocol (based on XML) used for sending messages across the Internet.</span></span> <span data-ttu-id="85d75-114">XMPP는 원래 Jabber으로 명명 되었으며, 여러 인터넷 메시징 및 통신 응용 프로그램 (예: Google 대화 및 Facebook 채팅)에서 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="85d75-114">XMPP was originally named Jabber, and is supported by several Internet messaging and communication applications, such as Google Talk and Facebook Chat.</span></span> <span data-ttu-id="85d75-115">**테스트-CsXmppIM** cmdlet은 사용자가 xmpp 네트워크의 사용자와 인스턴트 메시지를 교환할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="85d75-115">The **Test-CsXmppIM** cmdlet verifies that a user can exchange instant messages with a user on an XMPP network.</span></span> <span data-ttu-id="85d75-116">이 테스트를 성공적으로 수행 하려면 XMPP 사용자에 대 한 유효한 SIP 주소가 있어야 하 고 해당 SIP 주소가 허용 되는 XMPP 파트너로 구성 된 네트워크에 있어야 한다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="85d75-116">Note that, for this test to succeed, you must have a valid SIP address for the XMPP user, and that SIP address must be on a network that was configured as an allowed XMPP partner.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="85d75-117">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="85d75-117">Running the test</span></span>

<span data-ttu-id="85d75-118">다음 예에서는 풀 atl-cs-001.litwareinc.com의 XMPP 인스턴트 메시지 기능을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="85d75-118">The following example verifies the XMPP instant messaging capabilities for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="85d75-119">이 명령은 풀 atl-cs-001.litwareinc.com에 대해 테스트 사용자가 정의 된 경우에만 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="85d75-119">This command will work only if test users are defined for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="85d75-120">이 경우 명령에서 첫 번째 테스트 사용자가 SIP 주소 adelaney@contoso.com를 가진 사용자에 게 XMPP 인스턴트 메시지를 보낼 수 있는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="85d75-120">If they have, then the command will determine whether the first test user can send an XMPP instant message to a user who has the SIP address adelaney@contoso.com.</span></span>

<span data-ttu-id="85d75-121">테스트 사용자가 정의 되지 않은 경우에는 어떤 사용자로 로그온 해야 하는지 알 수 없기 때문에 명령이 실패 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="85d75-121">If test users are not defined, then the command will fail because it won't know which user to log on as.</span></span> <span data-ttu-id="85d75-122">풀에 대해 테스트 사용자를 정의 하지 않은 경우에는 UserSipAddress 매개 변수와이 명령을 사용 하 여 로그온 할 때 사용할 사용자의 자격 증명을 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85d75-122">If you have not defined test users for a pool, then you must include the UserSipAddress parameter and the credentials of the user who the command should use when trying to log on.</span></span>

    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com"

<span data-ttu-id="85d75-123">다음 예제에 표시 된 명령은 특정 사용자 (litwareinc\\pilar)가 로그온 할 수 있는 기능을 테스트 하 여 사용자 adelaney@contoso.com에 xmpp 인스턴트 메시지를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="85d75-123">The commands shown in the next example test the ability of a specific user (litwareinc\\pilar) to log on to send an XMPP instant message to the user adelaney@contoso.com.</span></span> <span data-ttu-id="85d75-124">이렇게 하려면이 예제의 첫 번째 명령은 Get-Credential cmdlet을 사용 하 여 사용자 Pilar Ackerman의 이름과 암호를 포함 하는 Windows PowerShell 명령줄 인터페이스 자격 증명 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="85d75-124">To do this, the first command in the example uses the Get-Credential cmdlet to create a Windows PowerShell command-line interface credential object that contains the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="85d75-125">(로그온 이름 litwareinc\\pilar는 매개 변수로 포함 되어 있기 때문에 Windows PowerShell 자격 증명 요청 대화 상자에서는 관리자만 Pilar Ackerman 계정에 대 한 암호를 입력 해야 합니다.) 그런 다음 결과 credential 개체는 $cred 1 이라는 변수에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="85d75-125">(Because the logon name litwareinc\\pilar was included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credential object is then stored in a variable named $cred1.</span></span>

<span data-ttu-id="85d75-126">그런 다음 두 번째 명령은이 사용자가 풀 atl-cs-001.litwareinc.com에 로그온 할 수 있는지 여부를 확인 하 고 XMPP 인스턴트 메시지를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="85d75-126">The second command then checks whether this user can log on to the pool atl-cs-001.litwareinc.com and send the XMPP instant message.</span></span> <span data-ttu-id="85d75-127">이 작업을 실행 하려면 4 개의 매개 변수 (예: TargetFqdn (등록자 풀의 FQDN))와 함께 **테스트 CsXmppIm** cmdlet이 호출 됩니다. 받는 사람 (메시지를 보내는 사용자의 SIP 주소) UserCredential (Pilar Ackerman의 사용자 자격 증명을 포함 하는 Windows PowerShell 개체)입니다. 및 UserSipAddress (제공 된 사용자 자격 증명에 해당 하는 SIP 주소).</span><span class="sxs-lookup"><span data-stu-id="85d75-127">To run this task, the **Test-CsXmppIm** cmdlet is called, together with four parameters: TargetFqdn (the FQDN of the Registrar pool); Receiver (the SIP address of the user the message is being addressed to); UserCredential (the Windows PowerShell object that contains Pilar Ackerman’s user credentials); and UserSipAddress (the SIP address that corresponds to the supplied user credentials).</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="85d75-128">성공 또는 실패 확인</span><span class="sxs-lookup"><span data-stu-id="85d75-128">Determining success or failure</span></span>

<span data-ttu-id="85d75-129">XMPP 인스턴트 메시지가 올바르게 구성 되 면 다음과 비슷한 출력이 표시 되 고 결과 속성이 성공으로 표시 됩니다 **.**</span><span class="sxs-lookup"><span data-stu-id="85d75-129">If XMPP instant messaging is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="85d75-130">대상 Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="85d75-130">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="85d75-131">결과: 성공</span><span class="sxs-lookup"><span data-stu-id="85d75-131">Result : Success</span></span>

<span data-ttu-id="85d75-132">대기 시간: 00:00:02.5361946</span><span class="sxs-lookup"><span data-stu-id="85d75-132">Latency : 00:00:02.5361946</span></span>

<span data-ttu-id="85d75-133">오류 메시지:</span><span class="sxs-lookup"><span data-stu-id="85d75-133">Error Message :</span></span>

<span data-ttu-id="85d75-134">있게</span><span class="sxs-lookup"><span data-stu-id="85d75-134">Diagnosis :</span></span>

<span data-ttu-id="85d75-135">지정 된 사용자가 XMPP 인스턴트 메시지를 사용할 수 없는 경우에는 결과가 **실패로**표시 되 고 오류 및 진단 속성에 추가 정보가 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="85d75-135">If the specified users can't use XMPP instant messaging, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="85d75-136">경고: 정규화 된 정식 #b0에 대 한 등록자 포트 번호를 읽지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="85d75-136">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="85d75-137">도메인 이름 (FQDN).</span><span class="sxs-lookup"><span data-stu-id="85d75-137">domain name (FQDN).</span></span> <span data-ttu-id="85d75-138">기본 등록자 포트 번호를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="85d75-138">Using default Registrar port number.</span></span> <span data-ttu-id="85d75-139">발생</span><span class="sxs-lookup"><span data-stu-id="85d75-139">Exception:</span></span>

<span data-ttu-id="85d75-140">InvalidOperationException: 토폴로지에서 일치 하는 클러스터를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="85d75-140">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="85d75-141">배포자</span><span class="sxs-lookup"><span data-stu-id="85d75-141">at</span></span>

<span data-ttu-id="85d75-142">SyntheticTransactions. SipSyntheticTransaction. TryRetri</span><span class="sxs-lookup"><span data-stu-id="85d75-142">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="85d75-143">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="85d75-143">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="85d75-144">대상 Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="85d75-144">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="85d75-145">결과: 실패</span><span class="sxs-lookup"><span data-stu-id="85d75-145">Result : Failure</span></span>

<span data-ttu-id="85d75-146">대기 시간: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="85d75-146">Latency : 00:00:00</span></span>

<span data-ttu-id="85d75-147">오류 메시지: 10060, 연결 된 파티 때문에 연결 시도가 실패 했습니다.</span><span class="sxs-lookup"><span data-stu-id="85d75-147">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="85d75-148">일정 시간 후에 제대로 응답 하지 않았거나</span><span class="sxs-lookup"><span data-stu-id="85d75-148">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="85d75-149">연결 된 호스트가 다음 연결에 실패 하 여 성립</span><span class="sxs-lookup"><span data-stu-id="85d75-149">established connection failed because connected host has</span></span>

<span data-ttu-id="85d75-150">10.188.116.96에 응답 하지 못했습니다: 5061</span><span class="sxs-lookup"><span data-stu-id="85d75-150">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="85d75-151">내부 예외: 다음 이유로 인해 연결 시도가 실패 했습니다.</span><span class="sxs-lookup"><span data-stu-id="85d75-151">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="85d75-152">연결 된 상대방이 일정 기간 후에 적절 하 게 응답 하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="85d75-152">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="85d75-153">연결 된 호스트 때문에 시간이 나 연결에 실패 했습니다.</span><span class="sxs-lookup"><span data-stu-id="85d75-153">time, or established connection failed because connected host</span></span>

<span data-ttu-id="85d75-154">님이 10.188.116.96에 응답 하지 못했습니다: 5061</span><span class="sxs-lookup"><span data-stu-id="85d75-154">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="85d75-155">있게</span><span class="sxs-lookup"><span data-stu-id="85d75-155">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="85d75-156">테스트가 실패할 수 있는 이유</span><span class="sxs-lookup"><span data-stu-id="85d75-156">Reasons why the test might have failed</span></span>

<span data-ttu-id="85d75-157">**테스트-CsXmppIM** 이 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="85d75-157">Here are some common reasons why **Test-CsXmppIM** might fail:</span></span>

  - <span data-ttu-id="85d75-158">잘못 된 매개 변수 값이 제공 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="85d75-158">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="85d75-159">사용 하는 경우 선택적 매개 변수를 올바르게 구성 하거나 테스트에 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="85d75-159">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="85d75-160">선택적 매개 변수 없이 명령을 다시 실행 하 여 성공 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="85d75-160">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="85d75-161">XMPP 게이트웨이 구성이 잘못 구성 되었거나 아직 배포 되지 않은 경우이 명령은 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="85d75-161">This command will fail if XMPP gateway configuration is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="85d75-162">참고 항목</span><span class="sxs-lookup"><span data-stu-id="85d75-162">See Also</span></span>


[<span data-ttu-id="85d75-163">Set-Csxmpp게이트웨이 구성</span><span class="sxs-lookup"><span data-stu-id="85d75-163">Set-CsXmppGatewayConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsXmppGatewayConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

