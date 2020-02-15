---
title: 'Lync Server 2013: smart 전화로 푸시 알림 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test push notifications to smart phones
ms:assetid: 8f5ca7d1-1ccb-4cb0-b417-730559e79b6e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767948(v=OCS.15)
ms:contentKeyID: 63969626
ms.date: 03/15/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 858c1ad3ad5776453a4a48505672c69083de1cc2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42021219"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-push-notifications-to-smart-phones-in-lync-server-2013"></a><span data-ttu-id="aef89-102">Lync Server 2013에서 smart 전화로 푸시 알림 테스트</span><span class="sxs-lookup"><span data-stu-id="aef89-102">Test push notifications to smart phones in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aef89-103">_**마지막으로 수정 된 항목:** 2017-03-15_</span><span class="sxs-lookup"><span data-stu-id="aef89-103">_**Topic Last Modified:** 2017-03-15_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aef89-104">확인 일정</span><span class="sxs-lookup"><span data-stu-id="aef89-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="aef89-105">월간</span><span class="sxs-lookup"><span data-stu-id="aef89-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aef89-106">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="aef89-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="aef89-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="aef89-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aef89-108">필요한 권한</span><span class="sxs-lookup"><span data-stu-id="aef89-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="aef89-109">Lync Server 관리 셸을 사용 하 여 로컬로 실행 하는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aef89-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="aef89-110">Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 사용자에 게는 CsMcxPushNotification cmdlet을 실행할 수 있는 권한이 있는 RBAC 역할이 할당 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aef89-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsMcxPushNotification cmdlet.</span></span> <span data-ttu-id="aef89-111">이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="aef89-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxPushNotification&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="aef89-112">설명</span><span class="sxs-lookup"><span data-stu-id="aef89-112">Description</span></span>

<span data-ttu-id="aef89-113">푸시 알림 서비스 (Apple Push Notification Service 및 Microsoft Push Notification Service)는 Lync 클라이언트를 사용할 경우에도 새 인스턴트 메시지 또는 새 음성 메일과 같은 이벤트에 대 한 알림을 Iphone 및 Windows phone과 같은 모바일 장치에 보낼 수 있습니다. 이러한 장치는 현재 일시 중단 되었거나 백그라운드에서 실행 되 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aef89-113">The push notification service (Apple Push Notification Service and Microsoft Push Notification Service) can send notifications about events such as new instant messages or new voice mail to mobile devices such as iPhones and Windows Phones, even if the Lync client on those devices is currently suspended or running in the background.</span></span> <span data-ttu-id="aef89-114">푸시 알림 서비스는 Microsoft 서버에서 실행 되는 클라우드 기반 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="aef89-114">The push notification service is a cloud-based service that is running on Microsoft servers.</span></span> <span data-ttu-id="aef89-115">푸시 알림을 사용 하려면 푸시 알림 clearinghouse에 연결 하 고 인증을 받을 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aef89-115">In order to take advantage of push notifications, you must be able to connect to, and be authenticated by, the push notification clearinghouse.</span></span> <span data-ttu-id="aef89-116">관리자는 CsMcxPushNotification cmdlet을 사용 하 여 푸시 알림 요청이에 지 서버를 통해 푸시 알림 clearinghouse로 라우팅되도록 할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="aef89-116">The Test-CsMcxPushNotification cmdlet enables administrators to verify that push notification requests can be routed through your Edge server to the push notification clearinghouse.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="aef89-117">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="aef89-117">Running the test</span></span>

<span data-ttu-id="aef89-118">푸시 알림 서비스를 테스트 하려면 Test-CsMcxPushNotification cmdlet을 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="aef89-118">To test the push notification service, call the Test-CsMcxPushNotification cmdlet.</span></span> <span data-ttu-id="aef89-119">에 지 서버의 fqdn (정규화 된 도메인 이름)을 지정 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="aef89-119">Make sure that you specify the fully qualified domain name of your Edge server:</span></span>

    Test-CsMcxPushNotification -AccessEdgeFqdn "atl-edge-001.litwareinc.com"

<span data-ttu-id="aef89-120">자세한 내용은 [Test-CsMcxPushNotification](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification) cmdlet에 대 한 도움말 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="aef89-120">For more information, see the help topic for the [Test-CsMcxPushNotification](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="aef89-121">성공 또는 실패 확인</span><span class="sxs-lookup"><span data-stu-id="aef89-121">Determining success or failure</span></span>

<span data-ttu-id="aef89-122">Test-CsMcxPushNotification가 성공한 경우 cmdlet은 테스트 결과 성공을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="aef89-122">If Test-CsMcxPushNotification succeeds the cmdlet will return the test result Success:</span></span>

<span data-ttu-id="aef89-123">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="aef89-123">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="aef89-124">결과: 성공</span><span class="sxs-lookup"><span data-stu-id="aef89-124">Result : Success</span></span>

<span data-ttu-id="aef89-125">대기 시간: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="aef89-125">Latency : 00:00:00</span></span>

<span data-ttu-id="aef89-126">오류</span><span class="sxs-lookup"><span data-stu-id="aef89-126">Error :</span></span>

<span data-ttu-id="aef89-127">진단을</span><span class="sxs-lookup"><span data-stu-id="aef89-127">Diagnosis :</span></span>

<span data-ttu-id="aef89-128">Test-CsMcxPushNotification이 푸시 알림 clearinghouse에 연결할 수 없는 경우 cmdlet은 일반적으로 실패의 테스트 결과를 반환 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aef89-128">If Test-CsMcxPushNotification is unable to connect to the push notification clearinghouse the cmdlet will typically not return a test result of Failure.</span></span> <span data-ttu-id="aef89-129">대신 명령이 완전히 실패 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aef89-129">Instead the command will usually fail completely.</span></span> <span data-ttu-id="aef89-130">예:</span><span class="sxs-lookup"><span data-stu-id="aef89-130">For example:</span></span>

<span data-ttu-id="aef89-131">Test-CsMcxPushNotification: 네트워크에서 504 (서버 시간 초과) 응답이 수신 되었으며 작업이 실패 했습니다.</span><span class="sxs-lookup"><span data-stu-id="aef89-131">Test-CsMcxPushNotification : A 504 (Server time-out) response was received from the network and the operation failed.</span></span> <span data-ttu-id="aef89-132">자세한 내용은 예외 정보를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="aef89-132">See the exception details for more information.</span></span>

<span data-ttu-id="aef89-133">줄: 1 문자: 27</span><span class="sxs-lookup"><span data-stu-id="aef89-133">At line:1 char:27</span></span>

<span data-ttu-id="aef89-134">\+Test-csmcxpushnotification \< \< \< \< -AccessEdgeFqdn lyncedge.mydomain.com</span><span class="sxs-lookup"><span data-stu-id="aef89-134">\+ Test-CsMcxPushNotification \<\<\<\< -AccessEdgeFqdn lyncedge.mydomain.com</span></span>

<span data-ttu-id="aef89-135">\+CategoryInfo: OperationStopped 됨: (:) \[Test-CsMcxPushNotification\], FailureResponseException</span><span class="sxs-lookup"><span data-stu-id="aef89-135">\+ CategoryInfo : OperationStopped: (:) \[Test-CsMcxPushNotification\], FailureResponseException</span></span>

<span data-ttu-id="aef89-136">\+FullyQualifiedErrorId: WorkflowNotCompleted, Microsoft. SyntheticTransactions. TestMcxPushNotificationCmdlet</span><span class="sxs-lookup"><span data-stu-id="aef89-136">\+ FullyQualifiedErrorId : WorkflowNotCompleted,Microsoft.Rtc.Management.SyntheticTransactions.TestMcxPushNotificationCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="aef89-137">테스트가 실패 한 이유</span><span class="sxs-lookup"><span data-stu-id="aef89-137">Reasons why the test might have failed</span></span>

<span data-ttu-id="aef89-138">에 지 서버와 통신 하는 데 문제가 있거나 푸시 알림 클리어 링 하우스와 통신 하는 데 문제가 있는 경우 푸시 알림 서비스에서 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="aef89-138">If the push notification service fails that usually indicates either problems communicating with your Edge server, or problems communicating with the Push Notification Clearing House.</span></span> <span data-ttu-id="aef89-139">Test-CsMcxPushNotification를 실행할 때 문제가 발생 하는 경우에는에 지 서버가 올바르게 작동 하는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aef89-139">If you encounter problems when you run Test-CsMcxPushNotification, the first thing that you should do is verify that your Edge server is working correctly.</span></span> <span data-ttu-id="aef89-140">이 작업을 수행 하는 한 가지 방법은 Test-csavedgeconnectivity cmdlet을 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="aef89-140">One way to do that is to use the Test-CsAVEdgeConnectivity cmdlet:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsAVEdgeConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="aef89-141">이 검사는 지정 된 사용자가에 지 서버에 연결할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="aef89-141">This check verifies that a specified user can connect to the Edge server.</span></span>

<span data-ttu-id="aef89-142">에 지 서버가 정상적으로 작동 하는 것 처럼 보이면 대개 푸시 알림 clearinghouse에 연결할 수 없다는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="aef89-142">If the Edge server seems to be working correctly, that often means that you are unable to connect to the push notification clearinghouse.</span></span> <span data-ttu-id="aef89-143">이는 일반적으로 clearinghouse URI를 올바르게 구성 하지 않았거나이 URL을 가리키는 DNS SRV 레코드가 없는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="aef89-143">In turn, that typically means that you either have not configured the clearinghouse URI correctly or that you do not have a DNS SRV record that points to this URL.</span></span> <span data-ttu-id="aef89-144">다음 명령을 실행 하 여 URI가 올바른 값 (sip:push@push.lync.com)으로 설정 되어 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aef89-144">You can verify that the URI is set to the correct value (sip:push@push.lync.com) by running this command:</span></span>

    Get-CsMcxConfiguration

<span data-ttu-id="aef89-145">PushNotificationProxyUri 속성이 sip:push@push.lync.com 이외의 다른 값으로 설정 된 경우에는 집합-McxConfiguration cmdlet을 사용 하 여 해당 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aef89-145">If the PushNotificationProxyUri property is set to anything other than sip:push@push.lync.com then you can correct that problem by using the Set-McxConfiguration cmdlet.</span></span> <span data-ttu-id="aef89-146">예를 들어이 명령은 조직 전체에서 URI를 올바르게 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="aef89-146">For example, this command correctly sets the URI throughout your organization:</span></span>

    Get-CsMcxConfiguration | Set-CsMcxConfiguration -PushNotificationProxyUri "sip:push@push.lync.com"

<span data-ttu-id="aef89-147">자세한 내용은 [CsMcxConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsMcxConfiguration) cmdlet에 대 한 도움말 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="aef89-147">For more information, see the help topic for the [Set-CsMcxConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsMcxConfiguration) cmdlet.</span></span>

<span data-ttu-id="aef89-148">URI가 올바르게 구성 된 경우 다음 단계는 SIP 도메인 및에 지 서버로 확인 되는 DNS SRV 레코드가 있는지 확인 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="aef89-148">If the URI is configured correctly, your next step should be to verify that you have a DNS SRV record that resolves to your SIP domain and your Edge server.</span></span> <span data-ttu-id="aef89-149">이러한 레코드를 구성 하는 방법에 대 한 자세한 내용은 모바일 기능에 대 한 DNS 요구 사항 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="aef89-149">For more information about how to configure these records, see the help topic DNS Requirements for Mobility.</span></span> <span data-ttu-id="aef89-150">일반적으로 다음 오류 메시지는 DNS 레코드에 문제가 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="aef89-150">Note that the following error message usually indicates a problem with DNS records:</span></span>

<span data-ttu-id="aef89-151">네트워크에서 504 (서버 시간 초과) 응답이 수신 되었으며 작업에 실패 했습니다.</span><span class="sxs-lookup"><span data-stu-id="aef89-151">A 504 (Server time-out) response was received from the network and the operation failed.</span></span> <span data-ttu-id="aef89-152">자세한 내용은 예외 정보를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="aef89-152">See the exception details for more information.</span></span>

<span data-ttu-id="aef89-153">또한이 오류 메시지와 함께 CsMcxConfiguration이 실패할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aef89-153">It’s also possible that Test-CsMcxConfiguration will fail with this error message:</span></span>

<span data-ttu-id="aef89-154">Test-CsMcxPushNotification: 푸시 알림 요청이 거부 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="aef89-154">Test-CsMcxPushNotification : Push Notification request was rejected.</span></span>

<span data-ttu-id="aef89-155">줄: 1 문자: 27</span><span class="sxs-lookup"><span data-stu-id="aef89-155">At line:1 char:27</span></span>

<span data-ttu-id="aef89-156">\+Test-CsMcxPushNotification\<\<\<\<</span><span class="sxs-lookup"><span data-stu-id="aef89-156">\+ Test-CsMcxPushNotification \<\<\<\<</span></span>

<span data-ttu-id="aef89-157">\+CategoryInfo: OperationStopped 됨: (:) \[Test-CsMcxPushNotification\], SyntheticTransactionException</span><span class="sxs-lookup"><span data-stu-id="aef89-157">\+ CategoryInfo : OperationStopped: (:) \[Test-CsMcxPushNotification\], SyntheticTransactionException</span></span>

<span data-ttu-id="aef89-158">\+FullyQualifiedErrorId: WorkflowNotCompleted, Microsoft. SyntheticTransactions. TestMcxPushNotificationCmdlet</span><span class="sxs-lookup"><span data-stu-id="aef89-158">\+ FullyQualifiedErrorId : WorkflowNotCompleted,Microsoft.Rtc.Management.SyntheticTransactions.TestMcxPushNotificationCmdlet</span></span>

<span data-ttu-id="aef89-159">"푸시 알림 요청이 거부 되었습니다." 메시지는 일반적으로 URL 필터링을 사용 하도록 설정 하 고 http: 및 https: 접두사를 차단 하는 경우에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="aef89-159">The “Push notification request was rejected” message typically occurs if you have enabled URL filtering and are blocking the http: and https: prefixes.</span></span> <span data-ttu-id="aef89-160">다음과 같은 명령을 사용 하 여 차단 되는 접두사를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aef89-160">You can determine which prefixes are being blocked by using a command similar to the following:</span></span>

```PowerShell 
 (Get-CsImFilterConfiguration -Identity Global).Prefixes
```

<span data-ttu-id="aef89-161">Http: 또는 https:가 결과에 표시 되는 경우 푸시 알림이 작동 하려면 차단 된 접두사 목록에서 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aef89-161">If http: or https: appear in the results, you must remove them from the blocked prefix list for push notifications to work.</span></span> <span data-ttu-id="aef89-162">다음과 같은 명령을 사용 하 여이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aef89-162">That can be done by using commands similar to these:</span></span>

    Set-CsImFilterConfiguration -Identity site:Redmond -Prefixes @{remove="http:"}
    Set-CsImFilterConfiguration -Identity site:Redmond -Prefixes @{remove="https:"}

<span data-ttu-id="aef89-163">자세한 내용은 [CsImFilterConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsImFilterConfiguration)cmdlet에 대 한 도움말 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="aef89-163">For more information, see the help topic for the [Set-CsImFilterConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsImFilterConfiguration)cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

