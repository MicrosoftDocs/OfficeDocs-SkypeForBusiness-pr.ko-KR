---
title: 'Lync Server 2013: 영구 채팅 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing persistent chat
ms:assetid: d351b6f2-bc31-42e0-9e8d-c347713d6b4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727313(v=OCS.15)
ms:contentKeyID: 63969651
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2177e4fce4d32bb2dc6c82e1f3fecae367eb2543
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193961"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-persistent-chat-in-lync-server-2013"></a><span data-ttu-id="c1eaa-102">Lync Server 2013에서 영구 채팅 테스트</span><span class="sxs-lookup"><span data-stu-id="c1eaa-102">Testing persistent chat in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c1eaa-103">_**마지막으로 수정 된 항목:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="c1eaa-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c1eaa-104">확인 일정</span><span class="sxs-lookup"><span data-stu-id="c1eaa-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="c1eaa-105">매일</span><span class="sxs-lookup"><span data-stu-id="c1eaa-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c1eaa-106">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="c1eaa-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="c1eaa-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c1eaa-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c1eaa-108">필요한 권한</span><span class="sxs-lookup"><span data-stu-id="c1eaa-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="c1eaa-109">Lync Server 관리 셸을 사용 하 여 로컬로 실행 하는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1eaa-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="c1eaa-110">Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 <strong>test-cspersistentchatmessage</strong> cmdlet을 실행 하는 권한이 있는 RBAC 역할을 사용자에 게 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1eaa-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsPersistentChatMessage</strong> cmdlet.</span></span> <span data-ttu-id="c1eaa-111">이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1eaa-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPersistentChatMessage&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="c1eaa-112">설명</span><span class="sxs-lookup"><span data-stu-id="c1eaa-112">Description</span></span>

<span data-ttu-id="c1eaa-113">**Test-cspersistentchatmessage** cmdlet은 테스트 사용자 쌍이 영구 채팅 서비스를 사용 하 여 메시지를 교환할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1eaa-113">The **Test-CsPersistentChatMessage** cmdlet verifies that a pair of test users can exchange messages using the Persistent Chat service.</span></span> <span data-ttu-id="c1eaa-114">이 작업을 수행 하기 위해 cmdlet은 두 사용자를 Lync Server 2013에 기록 하 고, 사용자를 영구 채팅방에 연결 하 고, 메시지 쌍을 교환 한 다음 대화방을 종료 하 고 두 사용자를 로그 오프 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1eaa-114">To do this, the cmdlet logs the two users on to Lync Server 2013, connects the users to a persistent Chat room, exchanges a pair of messages, then exits the chat room and logs off the two users.</span></span> <span data-ttu-id="c1eaa-115">대화방을 만들지 않았거나 두 테스트 사용자 계정에 영구 채팅 서비스에 대 한 액세스 권한을 부여 하는 영구 채팅 정책이 할당 되지 않은 경우에는이 cmdlet을 호출 하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1eaa-115">Note that calls to this cmdlet will fail if you have not created any chat rooms or if the two test user accounts are not assigned a Persistent Chat policy that gives them access to the Persistent Chat service.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="c1eaa-116">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="c1eaa-116">Running the test</span></span>

<span data-ttu-id="c1eaa-117">다음 예에 표시 된 명령은 litwareinc\\pilar 및 litwareinc\\kenmyer) 사용자 쌍이 Lync Server 2013에 로그온 한 다음 영구 채팅 서비스를 사용 하 여 메시지를 교환 하는 기능을 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1eaa-117">The commands shown in the following example test the ability of a pair of users (litwareinc\\pilar and litwareinc\\kenmyer) to log on to Lync Server 2013 and then exchange messages using the Persistent Chat service.</span></span> <span data-ttu-id="c1eaa-118">이 작업을 수행 하기 위해이 예제의 첫 번째 명령은 **Get-Credential** cmdlet을 사용 하 여 User Pilar Ackerman의 이름과 암호가 포함 된 Windows PowerShell 명령줄 인터페이스 자격 증명 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c1eaa-118">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credential object that contains the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="c1eaa-119">(로그온 이름, litwareinc\\pilar가 매개 변수로 포함 되었기 때문에 Windows PowerShell 자격 증명 요청 대화 상자에만 관리자가 Pilar Ackerman 계정의 암호를 입력 하면 됩니다.) 그런 다음 결과 credentials 개체가 $cred 1 이라는 변수에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1eaa-119">(Because the logon name, litwareinc\\pilar, was included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credentials object is then stored in a variable named $cred1.</span></span> <span data-ttu-id="c1eaa-120">두 번째 명령도 같은 작업을 수행하지만 이번에는 Ken Myer 계정의 자격 증명 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c1eaa-120">The second command does the same thing, this time returning a credential object for the Ken Myer account.</span></span>

<span data-ttu-id="c1eaa-121">Credential 개체를 사용 하는 경우 세 번째 명령은 영구 채팅을 사용 하 여 이러한 두 사용자가 Lync Server 2013에 로그온 할 수 있는지 여부와 exchange 메시지를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1eaa-121">With the credential objects in hand, the third command determines whether these two users can log on to Lync Server 2013 and exchange messages using Persistent Chat.</span></span> <span data-ttu-id="c1eaa-122">이 작업을 수행 하려면 다음 매개 변수를 사용 하 여 **test-cspersistentchatmessage** cmdlet을 호출 합니다. targetfqdn (등록자 풀의 FQDN) SenderSipAddress (첫 번째 테스트 사용자의 SIP 주소) SenderCredential (이 사용자에 대 한 자격 증명이 포함 된 Windows PowerShell 개체) ReceiverSipAddress (다른 테스트 사용자의 SIP 주소); 및 변수와 (다른 테스트 사용자에 대 한 자격 증명이 포함 된 Windows PowerShell 개체)</span><span class="sxs-lookup"><span data-stu-id="c1eaa-122">To perform this task, the **Test-CsPersistentChatMessage** cmdlet is called using the following parameters: TargetFqdn (the FQDN of the Registrar pool); SenderSipAddress (the SIP address for the first test user); SenderCredential (the Windows PowerShell object that contains the credentials for this same user); ReceiverSipAddress (the SIP address for the other test user); and ReceiverCredential (the Windows PowerShell object that contains the credentials for the other test user).</span></span>

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-persistentchat-001.litwareinc.com -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $cred1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="c1eaa-123">성공 또는 실패 확인</span><span class="sxs-lookup"><span data-stu-id="c1eaa-123">Determining success or failure</span></span>

<span data-ttu-id="c1eaa-124">지정 된 사용자에 게 유효한 위치 정책이 있으면 결과 속성이 **Success**로 표시 된 것과 비슷한 출력을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1eaa-124">If the specified user has a valid location policy, then you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="c1eaa-125">대상 Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="c1eaa-125">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="c1eaa-126">결과: 성공</span><span class="sxs-lookup"><span data-stu-id="c1eaa-126">Result : Success</span></span>

<span data-ttu-id="c1eaa-127">대기 시간: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="c1eaa-127">Latency : 00:00:00</span></span>

<span data-ttu-id="c1eaa-128">오류 메시지:</span><span class="sxs-lookup"><span data-stu-id="c1eaa-128">Error Message :</span></span>

<span data-ttu-id="c1eaa-129">진단을</span><span class="sxs-lookup"><span data-stu-id="c1eaa-129">Diagnosis :</span></span>

<span data-ttu-id="c1eaa-130">지정 된 사용자가 영구 채팅 서비스를 사용 하 여 메시지를 교환할 수 없는 경우 결과가 **실패로**표시 되 고 오류 및 진단 속성에 추가 정보가 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1eaa-130">If the specified users can't exchange messages using the Persistent Chat service, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="c1eaa-131">경고: 지정한 정규화 된 자격에 대 한 등록자 포트 번호를 읽지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="c1eaa-131">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="c1eaa-132">FQDN (도메인 이름)</span><span class="sxs-lookup"><span data-stu-id="c1eaa-132">domain name (FQDN).</span></span> <span data-ttu-id="c1eaa-133">기본 등록자 포트 번호 사용</span><span class="sxs-lookup"><span data-stu-id="c1eaa-133">Using default Registrar port number.</span></span> <span data-ttu-id="c1eaa-134">오류</span><span class="sxs-lookup"><span data-stu-id="c1eaa-134">Exception:</span></span>

<span data-ttu-id="c1eaa-135">InvalidOperationException: 토폴로지에서 일치 하는 클러스터를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c1eaa-135">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="c1eaa-136">구독자</span><span class="sxs-lookup"><span data-stu-id="c1eaa-136">at</span></span>

<span data-ttu-id="c1eaa-137">SyntheticTransactions SipSyntheticTransaction TryRetri를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1eaa-137">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="c1eaa-138">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="c1eaa-138">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="c1eaa-139">대상 Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="c1eaa-139">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="c1eaa-140">결과: 실패</span><span class="sxs-lookup"><span data-stu-id="c1eaa-140">Result : Failure</span></span>

<span data-ttu-id="c1eaa-141">대기 시간: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="c1eaa-141">Latency : 00:00:00</span></span>

<span data-ttu-id="c1eaa-142">오류 메시지: 10060, 연결 된 파티 때문에 연결 시도가 실패 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c1eaa-142">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="c1eaa-143">일정 시간 후에 올바르게 응답 하지 않았거나</span><span class="sxs-lookup"><span data-stu-id="c1eaa-143">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="c1eaa-144">연결 된 호스트에서 연결이 실패 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c1eaa-144">established connection failed because connected host has</span></span>

<span data-ttu-id="c1eaa-145">2001:4898 \[: e8: f39e: 5c9a: ad83:81b3:9944\]: 5061을 응답 하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="c1eaa-145">failed to respond \[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="c1eaa-146">내부 예외:</span><span class="sxs-lookup"><span data-stu-id="c1eaa-146">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="c1eaa-147">일정 기간 후에 연결 된 파티가 제대로 응답 하지 않음</span><span class="sxs-lookup"><span data-stu-id="c1eaa-147">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="c1eaa-148">연결 된 호스트 때문에 시간이 나 연결에 실패 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c1eaa-148">time, or established connection failed because connected host</span></span>

<span data-ttu-id="c1eaa-149">응답 하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="c1eaa-149">has failed to respond</span></span>

<span data-ttu-id="c1eaa-150">\[2001:4898: e8: f39e: 5c9a: ad83:81b3:9944\]: 5061</span><span class="sxs-lookup"><span data-stu-id="c1eaa-150">\[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="c1eaa-151">진단을</span><span class="sxs-lookup"><span data-stu-id="c1eaa-151">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="c1eaa-152">테스트가 실패 한 이유</span><span class="sxs-lookup"><span data-stu-id="c1eaa-152">Reasons why the test might have failed</span></span>

<span data-ttu-id="c1eaa-153">다음은 **test-cspersistentchatmessage에서** 오류가 발생할 수 있는 몇 가지 일반적인 이유입니다.</span><span class="sxs-lookup"><span data-stu-id="c1eaa-153">Here are some common reasons why **Test-CsPersistentChatMessage** might fail:</span></span>

  - <span data-ttu-id="c1eaa-154">잘못 된 매개 변수 값이 제공 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c1eaa-154">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="c1eaa-155">필요한 테스트 계정이 없거나 올바르게 만들어진 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1eaa-155">The required test accounts may not exist or have been correctly created.</span></span>

  - <span data-ttu-id="c1eaa-156">네트워크 문제가 발생 하 여 테스트 시간이 초과 된 예기치 않은 지연이 발생 했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1eaa-156">There may have been a network issue causing an unexpected delay which timed out the test.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c1eaa-157">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c1eaa-157">See Also</span></span>


[<span data-ttu-id="c1eaa-158">Grant-cspersistentchatpolicy</span><span class="sxs-lookup"><span data-stu-id="c1eaa-158">Grant-CsPersistentChatPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsPersistentChatPolicy)  
[<span data-ttu-id="c1eaa-159">Grant-cspersistentchatpolicy</span><span class="sxs-lookup"><span data-stu-id="c1eaa-159">New-CsPersistentChatPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsPersistentChatPolicy)  
[<span data-ttu-id="c1eaa-160">Grant-cspersistentchatpolicy</span><span class="sxs-lookup"><span data-stu-id="c1eaa-160">Set-CsPersistentChatPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsPersistentChatPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

