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
ms.openlocfilehash: 4d506ed0115fd5346048ff8870763a7ffc888a69
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745298"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-user-presence-publishing-and-subscribing-in-lync-server-2013"></a><span data-ttu-id="d5eef-102">Lync Server 2013에서 사용자 현재 상태 게시 및 구독 테스트</span><span class="sxs-lookup"><span data-stu-id="d5eef-102">Testing user presence publishing and subscribing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5eef-103">_**마지막으로 수정한 주제:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="d5eef-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d5eef-104">확인 일정</span><span class="sxs-lookup"><span data-stu-id="d5eef-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="d5eef-105">Daily</span><span class="sxs-lookup"><span data-stu-id="d5eef-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5eef-106">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="d5eef-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="d5eef-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d5eef-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5eef-108">권한이 필요 함</span><span class="sxs-lookup"><span data-stu-id="d5eef-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="d5eef-109">Lync Server Management Shell을 사용 하 여 로컬에서 실행 되는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5eef-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="d5eef-110">Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 테스트-CsPresence을 실행할 권한이 있는 RBAC 역할을 사용자에 게 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5eef-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsPresence cmdlet.</span></span> <span data-ttu-id="d5eef-111">이 cmdlet을 사용할 수 있는 모든 RBAC 역할 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5eef-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPresence&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="d5eef-112">설명</span><span class="sxs-lookup"><span data-stu-id="d5eef-112">Description</span></span>

<span data-ttu-id="d5eef-113">테스트-CsPresence 테스트 사용자 쌍이 Lync Server에 로그온 할 수 있는지 여부와 exchange 현재 상태 정보를 확인 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5eef-113">Test-CsPresence is used to determine whether a pair of test users can log on to Lync Server and then exchange presence information.</span></span> <span data-ttu-id="d5eef-114">이를 위해 cmdlet은 먼저 두 사용자를 시스템에 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5eef-114">To do this, the cmdlet first logs the two users on to the system.</span></span> <span data-ttu-id="d5eef-115">두 로그온이 모두 성공한 경우 첫 번째 테스트 사용자는 두 번째 사용자에 게 현재 상태 정보를 수신 하도록 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5eef-115">If both logons succeed, the first test user then asks to receive presence information from the second user.</span></span> <span data-ttu-id="d5eef-116">두 번째 사용자는이 정보를 게시 하 고 테스트-CsPresence 정보가 첫 번째 사용자에 게 성공적으로 전송 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5eef-116">The second user publishes this information, and Test-CsPresence verifies that the information was successfully transmitted to the first user.</span></span> <span data-ttu-id="d5eef-117">현재 상태 정보를 교환 한 후에는 Lync Server에서 두 테스트 사용자가 로그 오프 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5eef-117">After the exchange of presence information, the two test users are then logged off from Lync Server.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="d5eef-118">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="d5eef-118">Running the test</span></span>

<span data-ttu-id="d5eef-119">테스트-CsPresence cmdlet은 한 쌍의 미리 구성 된 테스트 계정 (Lync Server 테스트 실행을 위한 테스트 계정 설정 참조) 또는 Lync Server에 대해 사용 하도록 설정 된 두 사용자의 계정 중 하나를 사용 하 여 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5eef-119">The Test-CsPresence cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="d5eef-120">테스트 계정을 사용 하 여이 검사를 실행 하려면 테스트 중인 Lync Server 풀의 FQDN만 지정 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5eef-120">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="d5eef-121">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d5eef-121">For example:</span></span>

    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="d5eef-122">실제 사용자 계정을 사용 하 여이 검사를 실행 하려면 각 계정에 대해 두 개의 Windows PowerShell 자격 증명 개체 (계정 이름과 암호를 포함 하는 개체)를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5eef-122">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="d5eef-123">그런 다음 테스트를 호출할 때 다음과 같은 자격 증명 개체와 두 계정의 SIP 주소를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5eef-123">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsPresence:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com" -PublisherSipAddress "sip:kenmyer@litwareinc.com" -PublisherCredential $credential1 -SubscriberSipAddress "sip:davidlongmire@litwareinc.com" -SubscriberCredential $credential2

<span data-ttu-id="d5eef-124">자세한 내용은 [테스트-CsPresence](https://docs.microsoft.com/powershell/module/skype/Test-CsPresence) cmdlet에 대 한 도움말 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d5eef-124">For more information, see the Help documentation for the [Test-CsPresence](https://docs.microsoft.com/powershell/module/skype/Test-CsPresence) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="d5eef-125">성공 또는 실패 확인</span><span class="sxs-lookup"><span data-stu-id="d5eef-125">Determining success or failure</span></span>

<span data-ttu-id="d5eef-126">지정 된 사용자가 현재 상태 정보를 교환할 수 있는 경우 다음과 유사한 출력을 받고 결과 속성이 성공으로 표시 됨 **:**</span><span class="sxs-lookup"><span data-stu-id="d5eef-126">If the specified users can exchange presence information, then you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="d5eef-127">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="d5eef-127">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="d5eef-128">결과: 성공</span><span class="sxs-lookup"><span data-stu-id="d5eef-128">Result : Success</span></span>

<span data-ttu-id="d5eef-129">대기 시간: 00:00:06.3280315</span><span class="sxs-lookup"><span data-stu-id="d5eef-129">Latency : 00:00:06.3280315</span></span>

<span data-ttu-id="d5eef-130">오류</span><span class="sxs-lookup"><span data-stu-id="d5eef-130">Error :</span></span>

<span data-ttu-id="d5eef-131">있게</span><span class="sxs-lookup"><span data-stu-id="d5eef-131">Diagnosis :</span></span>

<span data-ttu-id="d5eef-132">두 명의 사용자가 현재 상태 정보를 교환할 수 없으면 결과가 실패로 표시 되 고 오류 및 진단 속성에 추가 정보가 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5eef-132">If the two users can't exchange presence information, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="d5eef-133">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="d5eef-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="d5eef-134">결과: 실패</span><span class="sxs-lookup"><span data-stu-id="d5eef-134">Result : Failure</span></span>

<span data-ttu-id="d5eef-135">대기 시간: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="d5eef-135">Latency : 00:00:00</span></span>

<span data-ttu-id="d5eef-136">오류: 404, 찾을 수 없음</span><span class="sxs-lookup"><span data-stu-id="d5eef-136">Error : 404, Not Found</span></span>

<span data-ttu-id="d5eef-137">진단: ErrorCode = 4005, Source = atl-cs-001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="d5eef-137">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="d5eef-138">이유 = 대상 URI가 SIP에 대해 사용 하도록 설정 되지 않았거나 지원 되지 않음</span><span class="sxs-lookup"><span data-stu-id="d5eef-138">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="d5eef-139">존재.</span><span class="sxs-lookup"><span data-stu-id="d5eef-139">exist.</span></span>

<span data-ttu-id="d5eef-140">Microsoft DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="d5eef-140">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="d5eef-141">예를 들어 이전 출력은 두 사용자 계정 중 적어도 하나가 유효 하지 않기 때문에 테스트가 실패 했음을 의미 합니다. 계정이 없거나 Lync Server에 대해 사용 하도록 설정 되지 않은 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="d5eef-141">For example, the previous output states that the test failed because at least one of the two user accounts is not valid: either the account does not exist or it has not been enabled for Lync Server.</span></span> <span data-ttu-id="d5eef-142">계정이 있는지 확인 하 고 다음과 같은 명령을 실행 하 여 Lync Server에 대해 사용 하도록 설정 했는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5eef-142">You can verify that the accounts exist, and determine whether they are enabled for Lync Server, by running a command similar to this:</span></span>

    "sip:kenmyer@litwareinc.com", "sip:davidlongmire@litwareinc.com" | Get-CsUser | Select-Object SipAddress, Enabled

<span data-ttu-id="d5eef-143">테스트-CsPresence이 실패할 경우 다음과 같이 Verbose 매개 변수를 포함 하 여 테스트를 다시 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5eef-143">If Test-CsPresence fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="d5eef-144">Verbose 매개 변수가 포함 된 경우 테스트-CsPresence 지정 된 사용자가 Lync Server에 로그온 하는 기능을 확인할 때 시도한 각 작업에 대 한 단계별 계정을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5eef-144">When the Verbose parameter is included, Test-CsPresence will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="d5eef-145">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d5eef-145">For example:</span></span>

<span data-ttu-id="d5eef-146">등록 요청이 알 수 없는 것으로 적중 됨</span><span class="sxs-lookup"><span data-stu-id="d5eef-146">Registration Request hit against Unknown</span></span>

<span data-ttu-id="d5eef-147">' 등록 ' 활동이 완료 되었습니다 (' 0.0345791 ' 초).</span><span class="sxs-lookup"><span data-stu-id="d5eef-147">'Register' activity completed in '0.0345791' secs.</span></span>

<span data-ttu-id="d5eef-148">' SelfSubscribeActivity ' 활동이 시작 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d5eef-148">'SelfSubscribeActivity' activity started.</span></span>

<span data-ttu-id="d5eef-149">' SelfSubscribeActivity ' 활동이 ' 0.0041174 ' 초 후에 완료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d5eef-149">'SelfSubscribeActivity' activity completed in '0.0041174' secs.</span></span>

<span data-ttu-id="d5eef-150">' SubscribePresence ' 활동이 시작 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d5eef-150">'SubscribePresence' activity started.</span></span>

<span data-ttu-id="d5eef-151">' SubscribePresence ' 활동이 ' 0.0038764 ' 초 후에 완료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d5eef-151">'SubscribePresence' activity completed in '0.0038764' secs.</span></span>

<span data-ttu-id="d5eef-152">' 없음 현재 상태 ' 활동이 시작 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d5eef-152">'PublishPresence' activity started.</span></span>

<span data-ttu-id="d5eef-153">예외 ' 현재 알림 '은 25 초 내에 수신 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d5eef-153">An exception 'Presence notification is not received within 25 secs.'</span></span> <span data-ttu-id="d5eef-154">워크플로 Microsoft SyntheticTransactions. STPresenceWorkflow 실행이 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d5eef-154">occurred ruing Workflow Microsoft.Rtc.SyntheticTransactions.Workflows.STPresenceWorkflow execution.</span></span>

<span data-ttu-id="d5eef-155">현재 상태 알림이 25 초 내에 수신 되지 않은 경우 네트워크 문제로 인해 정보가 교환 되지 않는 것을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5eef-155">The fact that the presence notification was not received within 25 seconds might indicate that network issues are preventing information from being exchanged.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="d5eef-156">테스트가 실패할 수 있는 이유</span><span class="sxs-lookup"><span data-stu-id="d5eef-156">Reasons why the test might have failed</span></span>

<span data-ttu-id="d5eef-157">테스트 CsPresence 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d5eef-157">Here are some common reasons why Test-CsPresence might fail:</span></span>

  - <span data-ttu-id="d5eef-158">잘못 된 사용자 계정을 지정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d5eef-158">You specified an incorrect user account.</span></span> <span data-ttu-id="d5eef-159">다음과 같은 명령을 실행 하 여 사용자 계정이 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5eef-159">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="d5eef-160">사용자 계정이 올바르지만 현재 Lync Server에서 계정을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d5eef-160">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="d5eef-161">Lync Server에 대해 사용자 계정이 설정 되어 있는지 확인 하려면 다음과 같은 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5eef-161">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="d5eef-162">Enabled 속성이 False로 설정 된 경우 사용자가 현재 Lync Server에 대해 사용 하도록 설정 되어 있지 않음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5eef-162">If the Enabled property is set to False that means that the user is currently not enabled for Lync Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

