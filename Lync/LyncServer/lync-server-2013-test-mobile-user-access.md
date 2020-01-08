---
title: 'Lync Server 2013: 모바일 사용자 액세스 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test mobile user access
ms:assetid: 81d97420-428b-41b7-91ef-185d572d3456
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767947(v=OCS.15)
ms:contentKeyID: 63969624
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eda2ec2d02fe4189c8e34cf700f6f1fd07895ef6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979232"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-mobile-user-access-in-lync-server-2013"></a><span data-ttu-id="4b1f1-102">Lync Server 2013에서 모바일 사용자 액세스 테스트</span><span class="sxs-lookup"><span data-stu-id="4b1f1-102">Test mobile user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4b1f1-103">_**마지막으로 수정한 주제:** 2014-06-07_</span><span class="sxs-lookup"><span data-stu-id="4b1f1-103">_**Topic Last Modified:** 2014-06-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4b1f1-104">확인 일정</span><span class="sxs-lookup"><span data-stu-id="4b1f1-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="4b1f1-105">월간</span><span class="sxs-lookup"><span data-stu-id="4b1f1-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b1f1-106">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="4b1f1-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="4b1f1-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4b1f1-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b1f1-108">권한이 필요 함</span><span class="sxs-lookup"><span data-stu-id="4b1f1-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="4b1f1-109">Lync Server Management Shell을 사용 하 여 로컬에서 실행 되는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b1f1-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="4b1f1-110">Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 사용자에 게 Test-CsMcxConference cmdlet을 실행할 수 있는 권한이 있는 RBAC 역할을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b1f1-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsMcxConference cmdlet.</span></span> <span data-ttu-id="4b1f1-111">이 cmdlet을 사용할 수 있는 모든 RBAC 역할 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b1f1-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="4b1f1-112">설명</span><span class="sxs-lookup"><span data-stu-id="4b1f1-112">Description</span></span>

<span data-ttu-id="4b1f1-113">모바일 장치 사용자는 이동성 서비스를 통해 다음과 같은 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b1f1-113">The Mobility Service enables mobile device users to do such things as:</span></span>

1.  <span data-ttu-id="4b1f1-114">인스턴트 메시지와 현재 상태 정보를 교환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b1f1-114">Exchange instant messages and presence information.</span></span>

2.  <span data-ttu-id="4b1f1-115">무선 공급자가 아닌 내부에서 음성 메일을 저장 하 고 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b1f1-115">Store and retrieve voice mail internally instead of with their wireless provider.</span></span>

3.  <span data-ttu-id="4b1f1-116">업무 및 전화 접속 회의를 통한 통화와 같은 Lync 서버 기능을 활용할 수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b1f1-116">Take advantage of Lync Server capabilities such as Call via Work and dial-out conferencing.</span></span> <span data-ttu-id="4b1f1-117">Test-CsMcxConference cmdlet은 사용자가 모바일 장치를 사용 하 여 Lync Server 회의에 참가 하 고 참여할 수 있는지 확인 하는 빠르고 쉬운 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b1f1-117">The Test-CsMcxConference cmdlet provides a quick and easy way to verify that users can join and participate in Lync Server conferences by using a mobile device.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="4b1f1-118">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="4b1f1-118">Running the test</span></span>

<span data-ttu-id="4b1f1-119">이 검사를 실행 하려면 각 계정에 대해 세 개의 Windows PowerShell 자격 증명 개체 (계정 이름과 암호를 포함 하는 개체)를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b1f1-119">To run this check, you must create three Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="4b1f1-120">그런 다음 다음 예제에 표시 된 대로 Test-CsMcxConference를 호출할 때 두 계정의 해당 자격 증명 개체와 SIP 주소를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b1f1-120">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsMcxConference as shown in the following example:</span></span>

    $organizerCred = Get-Credential "litwareinc\kenmyer"
    $user1Cred = Get-Credential "litwareinc\packerman"
    $user2Cred = Get-Credential "litwareinc\adelaney"
    
    Test-CsMcxConference -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -OrganizerSipAddress "sip:kenmyer@litwareinc.com" -OrganizerCredential $organizerCred -UserSipAddress "sip:pilar@litwareinc.com" -UserCredential $user1Cred -User2SipAddress "sip:adelaney@litwareinc.com" -User2Credential $user2Cred

<span data-ttu-id="4b1f1-121">자세한 내용은 [Test-CsMcxConference](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxConference) cmdlet에 대 한 도움말 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4b1f1-121">For more information, see the help topic for the [Test-CsMcxConference](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxConference) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="4b1f1-122">성공 또는 실패 확인</span><span class="sxs-lookup"><span data-stu-id="4b1f1-122">Determining success or failure</span></span>

<span data-ttu-id="4b1f1-123">확인에 성공 하면 테스트-CsMcxConference는 성공의 테스트 결과를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b1f1-123">If the check succeeds, Test-CsMcxConference will report a test result of Success:</span></span>

<span data-ttu-id="4b1f1-124">대상 Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="4b1f1-124">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="4b1f1-125">대상 Uri:http://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="4b1f1-125">Target Uri : http://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="4b1f1-126">결과: 성공</span><span class="sxs-lookup"><span data-stu-id="4b1f1-126">Result : Success</span></span>

<span data-ttu-id="4b1f1-127">대기 시간: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="4b1f1-127">Latency : 00:00:00</span></span>

<span data-ttu-id="4b1f1-128">오류 메시지:</span><span class="sxs-lookup"><span data-stu-id="4b1f1-128">Error Message :</span></span>

<span data-ttu-id="4b1f1-129">있게</span><span class="sxs-lookup"><span data-stu-id="4b1f1-129">Diagnosis :</span></span>

<span data-ttu-id="4b1f1-130">검사에 실패 하는 경우-CsMcxConference는 실패의 테스트 결과를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b1f1-130">If the check is unsuccessful Test-CsMcxConference will report a test result of Failure.</span></span> <span data-ttu-id="4b1f1-131">이 테스트 결과는 일반적으로 자세한 오류 메시지 및 진단에 수반 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b1f1-131">This test result will typically be accompanied by a detailed error message and diagnosis.</span></span> <span data-ttu-id="4b1f1-132">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4b1f1-132">For example:</span></span>

<span data-ttu-id="4b1f1-133">대상 Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="4b1f1-133">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="4b1f1-134">대상 Uri:https://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="4b1f1-134">Target Uri : https://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="4b1f1-135">결과: 실패</span><span class="sxs-lookup"><span data-stu-id="4b1f1-135">Result : Failure</span></span>

<span data-ttu-id="4b1f1-136">대기 시간: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="4b1f1-136">Latency : 00:00:00</span></span>

<span data-ttu-id="4b1f1-137">오류 메시지: 웹 티켓 서비스에 대 한 응답을 받지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="4b1f1-137">Error Message : No response received for Web-Ticket service.</span></span>

<span data-ttu-id="4b1f1-138">내부 예외: HHTP 요청이 클라이언트에 게 승인 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="4b1f1-138">Inner Exception:The HHTP request is unauthorized with client</span></span>

<span data-ttu-id="4b1f1-139">협상 구성표 ' Ntlm '.</span><span class="sxs-lookup"><span data-stu-id="4b1f1-139">negotiation scheme 'Ntlm'.</span></span> <span data-ttu-id="4b1f1-140">받은 인증 헤더</span><span class="sxs-lookup"><span data-stu-id="4b1f1-140">The authentication header received</span></span>

<span data-ttu-id="4b1f1-141">서버에서 ' 협상 ' 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4b1f1-141">from the server was 'Negotiate'.</span></span>

<span data-ttu-id="4b1f1-142">내부 예외: 원격 서버에서 오류를 반환 했습니다. (401)</span><span class="sxs-lookup"><span data-stu-id="4b1f1-142">Inner Exception:The remote server returned an error: (401)</span></span>

<span data-ttu-id="4b1f1-143">으로.</span><span class="sxs-lookup"><span data-stu-id="4b1f1-143">Unauthorized.</span></span>

<span data-ttu-id="4b1f1-144">있게</span><span class="sxs-lookup"><span data-stu-id="4b1f1-144">Diagnosis :</span></span>

<span data-ttu-id="4b1f1-145">내부 진단: X-MS-서버-Fqdb: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="4b1f1-145">Inner Diagnosis:X-MS-server-Fqdb : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="4b1f1-146">캐시 제어: 비공개</span><span class="sxs-lookup"><span data-stu-id="4b1f1-146">Cache-Control : private</span></span>

<span data-ttu-id="4b1f1-147">콘텐츠 형식: text/html; charset = u t f-8</span><span class="sxs-lookup"><span data-stu-id="4b1f1-147">Content-Type : text/html; charset=utf-8.</span></span>

<span data-ttu-id="4b1f1-148">서버: Microsoft-IIS/8.5</span><span class="sxs-lookup"><span data-stu-id="4b1f1-148">Server : Microsoft-IIS/8.5</span></span>

<span data-ttu-id="4b1f1-149">WWW-인증: 협상, NTLM</span><span class="sxs-lookup"><span data-stu-id="4b1f1-149">WWW-Authenticate : Negotiate,NTLM</span></span>

<span data-ttu-id="4b1f1-150">X-구동 방법: ASP.NET</span><span class="sxs-lookup"><span data-stu-id="4b1f1-150">X-Powered-By : ASP.NET</span></span>

<span data-ttu-id="4b1f1-151">X-콘텐츠 형식-옵션: nosniff 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b1f1-151">X-Content-Type-Options : nosniff</span></span>

<span data-ttu-id="4b1f1-152">날짜: 수요일, 28 월 2014 19:22:19 GMT</span><span class="sxs-lookup"><span data-stu-id="4b1f1-152">Date : Wed, 28 May 2014 19:22:19 GMT</span></span>

<span data-ttu-id="4b1f1-153">콘텐츠 길이: 6305</span><span class="sxs-lookup"><span data-stu-id="4b1f1-153">Content-Length : 6305</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="4b1f1-154">테스트가 실패할 수 있는 이유</span><span class="sxs-lookup"><span data-stu-id="4b1f1-154">Reasons why the test might have failed</span></span>

<span data-ttu-id="4b1f1-155">테스트-CsMcxConference가 실패 하는 경우 모바일 서비스를 실행 하 고 액세스할 수 있는지 확인 하는 것으로 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b1f1-155">If Test-CsMcxConference fails you should begin by verifying that the mobility service is running and can be accessed.</span></span> <span data-ttu-id="4b1f1-156">이 작업은 웹 브라우저를 사용 하 여 Lync Server 풀의 모바일 서비스 URL에 액세스할 수 있는지 확인 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b1f1-156">That can be done by using a web browser to verify that the mobility service URL for your Lync Server pool can be accessed.</span></span> <span data-ttu-id="4b1f1-157">예를 들어이 명령은 풀 atl-cs-001.litwareinc.com에 대 한 URL을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b1f1-157">For example, this command verifies the URL for the pool atl-cs-001.litwareinc.com:</span></span>

`https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc`

<span data-ttu-id="4b1f1-158">모바일 서비스에 액세스할 수 있는 경우에는 테스트 사용자에 게 유효한 Lync Server 계정이 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b1f1-158">If the mobility service can be accessed you should then verify that your test users have valid Lync Server accounts.</span></span> <span data-ttu-id="4b1f1-159">다음과 같은 명령을 사용 하 여 계정 정보를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b1f1-159">You can retrieve account information by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

<span data-ttu-id="4b1f1-160">Enabled 속성이 True가 아니거나 명령이 실패 한 경우에는 사용자에 게 유효한 Lync Server 계정이 없음을 의미 합니다. 또한 각 사용자 계정이 이동성을 사용할 수 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b1f1-160">If the Enabled property is not equal to True or if the command fails, that means that the user does not have a valid Lync Server account.You should also verify that each user account is enabled for mobility.</span></span> <span data-ttu-id="4b1f1-161">이렇게 하려면 먼저 계정에 할당 된 이동성 정책을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b1f1-161">To do that, first determine the mobility policy that is assigned to the account:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

<span data-ttu-id="4b1f1-162">정책 이름을 알고 나면 CsMobilityPolicy cmdlet을 사용 하 여 문제의 정책 (예: RedmondMobilityPolicy)에 EnableMobility 속성이 True로 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b1f1-162">After you know the policy name, use the Get-CsMobilityPolicy cmdlet to verify that the policy in question (for example, RedmondMobilityPolicy) has the EnableMobility property set to True:</span></span>

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

<span data-ttu-id="4b1f1-163">유효한 사용자 계정을 지정 하지 않은 것을 의미 하는 테스트-CsMcxConference를 실행할 때 "인증 헤더" 오류 메시지가 표시 되는 경우 사용자 이름 및 암호를 확인 한 다음 테스트를 다시 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b1f1-163">If you receive an “authentication header” error message when you run Test-CsMcxConference that often means that you have not specified a valid user account, Verify the user name and password and then try the test again.</span></span> <span data-ttu-id="4b1f1-164">사용자 계정이 유효한 것으로 확신 하는 경우 CsWebServiceConfiguration cmdlet을 사용 하 여 UseWindowsAuth 속성 값을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b1f1-164">If you are convinced that the user account is valid, then use the Get-CsWebServiceConfiguration cmdlet and check the value of the UseWindowsAuth property.</span></span> <span data-ttu-id="4b1f1-165">이렇게 하면 조직에서 사용할 수 있는 인증 방법을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b1f1-165">That will tell you which authentication methods are enabled in your organization.</span></span>

<span data-ttu-id="4b1f1-166">모바일 서비스 문제를 해결 하는 방법에 대 한 자세한 팁은 블로그 게시물 [문제 해결 외부 Lync 모바일 연결 문제를 단계별로](http://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4b1f1-166">For more tips about how to troubleshoot the mobility service, see the blog post [Troubleshooting External Lync Mobility Connectivity Issues Step-by-Step](http://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

