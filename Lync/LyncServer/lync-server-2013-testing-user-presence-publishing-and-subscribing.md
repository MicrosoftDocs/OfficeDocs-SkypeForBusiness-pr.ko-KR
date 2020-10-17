---
title: 'Lync Server 2013: 사용자 현재 상태 게시 및 구독 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing user presence publishing and subscribing
ms:assetid: 27694c71-8e63-4aa4-b49f-fa06ccb81949
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743832(v=OCS.15)
ms:contentKeyID: 63969587
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 335ad014595f855c1ccefab363f3cf34ad7c282b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503855"
---
# <a name="testing-user-presence-publishing-and-subscribing-in-lync-server-2013"></a><span data-ttu-id="ec872-102">Lync Server 2013에서 사용자 현재 상태 게시 및 구독 테스트</span><span class="sxs-lookup"><span data-stu-id="ec872-102">Testing user presence publishing and subscribing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ec872-103">_**마지막으로 수정 된 항목:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="ec872-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ec872-104">확인 일정</span><span class="sxs-lookup"><span data-stu-id="ec872-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="ec872-105">매일</span><span class="sxs-lookup"><span data-stu-id="ec872-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec872-106">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="ec872-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="ec872-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ec872-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec872-108">필요한 권한</span><span class="sxs-lookup"><span data-stu-id="ec872-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="ec872-109">Lync Server 관리 셸을 사용 하 여 로컬로 실행 하는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec872-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="ec872-110">Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 사용자에 게 Test-CsPresence cmdlet을 실행 하는 권한이 있는 RBAC 역할을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec872-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsPresence cmdlet.</span></span> <span data-ttu-id="ec872-111">이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec872-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPresence&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="ec872-112">설명</span><span class="sxs-lookup"><span data-stu-id="ec872-112">Description</span></span>

<span data-ttu-id="ec872-113">Test-CsPresence를 사용 하 여 테스트 사용자 쌍이 Lync Server에 로그온 하 고 현재 상태 정보를 교환할 수 있는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec872-113">Test-CsPresence is used to determine whether a pair of test users can log on to Lync Server and then exchange presence information.</span></span> <span data-ttu-id="ec872-114">이 작업을 위해 cmdlet은 먼저 두 사용자를 시스템에 로그온시킵니다.</span><span class="sxs-lookup"><span data-stu-id="ec872-114">To do this, the cmdlet first logs the two users on to the system.</span></span> <span data-ttu-id="ec872-115">두 로그온이 모두 성공하면 첫 번째 테스트 사용자가 두 번째 사용자로부터 현재 상태 정보를 받기 위해 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="ec872-115">If both logons succeed, the first test user then asks to receive presence information from the second user.</span></span> <span data-ttu-id="ec872-116">두 번째 사용자가 이 정보를 게시한 다음 Test-CsPresence는 정보가 첫 번째 사용자에게 성공적으로 전송되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ec872-116">The second user publishes this information, and Test-CsPresence verifies that the information was successfully transmitted to the first user.</span></span> <span data-ttu-id="ec872-117">현재 상태 정보를 교환 한 후에는 두 테스트 사용자가 Lync Server에서 로그 오프 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec872-117">After the exchange of presence information, the two test users are then logged off from Lync Server.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="ec872-118">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="ec872-118">Running the test</span></span>

<span data-ttu-id="ec872-119">Test-CsPresence cmdlet은 미리 구성 된 테스트 계정 쌍 (Lync Server 테스트 실행을 위한 테스트 계정 설정 참조) 또는 Lync Server를 사용 하도록 설정 된 두 사용자의 계정 중 하나를 사용 하 여 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec872-119">The Test-CsPresence cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="ec872-120">테스트 계정을 사용 하 여이 검사를 실행 하려면 테스트할 Lync Server 풀의 FQDN만 지정 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec872-120">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="ec872-121">예제:</span><span class="sxs-lookup"><span data-stu-id="ec872-121">For example:</span></span>

    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="ec872-122">실제 사용자 계정을 사용 하 여이 검사를 실행 하려면 각 계정에 대해 두 개의 Windows PowerShell 자격 증명 개체 (계정 이름과 암호가 포함 된 개체)를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec872-122">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="ec872-123">그런 다음 테스트-CsPresence 호출할 때 이러한 자격 증명 개체와 두 계정의 SIP 주소를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec872-123">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsPresence:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com" -PublisherSipAddress "sip:kenmyer@litwareinc.com" -PublisherCredential $credential1 -SubscriberSipAddress "sip:davidlongmire@litwareinc.com" -SubscriberCredential $credential2

<span data-ttu-id="ec872-124">자세한 내용은 [테스트-CsPresence](https://docs.microsoft.com/powershell/module/skype/Test-CsPresence) 에 대 한 도움말 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ec872-124">For more information, see the Help documentation for the [Test-CsPresence](https://docs.microsoft.com/powershell/module/skype/Test-CsPresence) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="ec872-125">성공 또는 실패 확인</span><span class="sxs-lookup"><span data-stu-id="ec872-125">Determining success or failure</span></span>

<span data-ttu-id="ec872-126">지정 된 사용자가 현재 상태 정보를 교환할 수 있으면 Result 속성이 Success로 표시 된 것과 비슷한 출력을 받게 됩니다 **.**</span><span class="sxs-lookup"><span data-stu-id="ec872-126">If the specified users can exchange presence information, then you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="ec872-127">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ec872-127">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="ec872-128">결과: 성공</span><span class="sxs-lookup"><span data-stu-id="ec872-128">Result : Success</span></span>

<span data-ttu-id="ec872-129">대기 시간: 00:00:06.3280315</span><span class="sxs-lookup"><span data-stu-id="ec872-129">Latency : 00:00:06.3280315</span></span>

<span data-ttu-id="ec872-130">오류</span><span class="sxs-lookup"><span data-stu-id="ec872-130">Error :</span></span>

<span data-ttu-id="ec872-131">진단을</span><span class="sxs-lookup"><span data-stu-id="ec872-131">Diagnosis :</span></span>

<span data-ttu-id="ec872-132">두 사용자가 현재 상태 정보를 교환할 수 없으면 결과가 실패로 표시 되 고 오류 및 진단 속성에 추가 정보가 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec872-132">If the two users can't exchange presence information, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="ec872-133">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ec872-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="ec872-134">결과: 실패</span><span class="sxs-lookup"><span data-stu-id="ec872-134">Result : Failure</span></span>

<span data-ttu-id="ec872-135">대기 시간: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="ec872-135">Latency : 00:00:00</span></span>

<span data-ttu-id="ec872-136">오류: 404, 찾을 수 없음</span><span class="sxs-lookup"><span data-stu-id="ec872-136">Error : 404, Not Found</span></span>

<span data-ttu-id="ec872-137">진단: ErrorCode = 4005, Source = atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ec872-137">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="ec872-138">이유 = 대상 URI가 SIP에 대해 사용 하도록 설정 되지 않았거나 지원 되지 않음</span><span class="sxs-lookup"><span data-stu-id="ec872-138">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="ec872-139">가.</span><span class="sxs-lookup"><span data-stu-id="ec872-139">exist.</span></span>

<span data-ttu-id="ec872-140">Microsoft DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="ec872-140">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="ec872-141">예를 들어 위의 출력에서는 두 사용자 계정 중 하나 이상이 올바르지 않아 테스트가 실패 했음을 나타냅니다. 계정이 없거나 Lync Server에 대해 사용 하도록 설정 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="ec872-141">For example, the previous output states that the test failed because at least one of the two user accounts is not valid: either the account does not exist or it has not been enabled for Lync Server.</span></span> <span data-ttu-id="ec872-142">다음과 같은 명령을 실행 하 여 해당 계정이 있는지 확인 하 고 Lync Server에 대해 사용 하도록 설정 되었는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec872-142">You can verify that the accounts exist, and determine whether they are enabled for Lync Server, by running a command similar to this:</span></span>

    "sip:kenmyer@litwareinc.com", "sip:davidlongmire@litwareinc.com" | Get-CsUser | Select-Object SipAddress, Enabled

<span data-ttu-id="ec872-143">Test-CsPresence 실패 하면 다음 시간에 Verbose 매개 변수를 포함 하 여 테스트를 다시 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec872-143">If Test-CsPresence fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="ec872-144">Verbose 매개 변수를 포함 하면 Test-CsPresence는 지정 된 사용자가 Lync Server에 로그온 할 수 있는지 확인할 때 시도한 각 작업의 단계별 계정을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec872-144">When the Verbose parameter is included, Test-CsPresence will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="ec872-145">예제:</span><span class="sxs-lookup"><span data-stu-id="ec872-145">For example:</span></span>

<span data-ttu-id="ec872-146">알 수 없는 등록 요청 적중률</span><span class="sxs-lookup"><span data-stu-id="ec872-146">Registration Request hit against Unknown</span></span>

<span data-ttu-id="ec872-147">' 등록 ' 활동이 완료 되었습니다 (' 0.0345791 ' 초).</span><span class="sxs-lookup"><span data-stu-id="ec872-147">'Register' activity completed in '0.0345791' secs.</span></span>

<span data-ttu-id="ec872-148">' SelfSubscribeActivity ' 활동이 시작 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ec872-148">'SelfSubscribeActivity' activity started.</span></span>

<span data-ttu-id="ec872-149">' SelfSubscribeActivity ' 작업이 ' 0.0041174 ' 초에 완료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ec872-149">'SelfSubscribeActivity' activity completed in '0.0041174' secs.</span></span>

<span data-ttu-id="ec872-150">' SubscribePresence ' 활동이 시작 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ec872-150">'SubscribePresence' activity started.</span></span>

<span data-ttu-id="ec872-151">' SubscribePresence ' 작업이 ' 0.0038764 ' 초에 완료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ec872-151">'SubscribePresence' activity completed in '0.0038764' secs.</span></span>

<span data-ttu-id="ec872-152">' 임-현재 상태 ' 활동이 시작 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ec872-152">'PublishPresence' activity started.</span></span>

<span data-ttu-id="ec872-153">예외 ' 현재 알림 '은 25 초 이내에 수신 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ec872-153">An exception 'Presence notification is not received within 25 secs.'</span></span> <span data-ttu-id="ec872-154">SyntheticTransactions에서 STPresenceWorkflow 실행을 수행 했습니다.</span><span class="sxs-lookup"><span data-stu-id="ec872-154">occurred ruing Workflow Microsoft.Rtc.SyntheticTransactions.Workflows.STPresenceWorkflow execution.</span></span>

<span data-ttu-id="ec872-155">현재 상태 알림이 25 초 이내에 수신 되지 않았다는 사실은 네트워크 문제로 인해 정보 교환이 차단 되는 것을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec872-155">The fact that the presence notification was not received within 25 seconds might indicate that network issues are preventing information from being exchanged.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="ec872-156">테스트가 실패 한 이유</span><span class="sxs-lookup"><span data-stu-id="ec872-156">Reasons why the test might have failed</span></span>

<span data-ttu-id="ec872-157">Test-CsPresence 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ec872-157">Here are some common reasons why Test-CsPresence might fail:</span></span>

  - <span data-ttu-id="ec872-158">잘못 된 사용자 계정을 지정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="ec872-158">You specified an incorrect user account.</span></span> <span data-ttu-id="ec872-159">다음과 같은 명령을 실행 하 여 사용자 계정이 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec872-159">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="ec872-160">사용자 계정이 올바르지만 해당 계정이 Lync Server에 대해 현재 사용 하도록 설정 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ec872-160">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="ec872-161">사용자 계정이 Lync Server에 대해 사용 하도록 설정 되어 있는지 확인 하려면 다음과 같은 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec872-161">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="ec872-162">Enabled 속성을 False로 설정 하면 사용자가 현재 Lync Server를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ec872-162">If the Enabled property is set to False that means that the user is currently not enabled for Lync Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

