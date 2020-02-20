---
title: 'Lync Server 2013: 모바일 사용자 액세스 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test mobile user access
ms:assetid: 81d97420-428b-41b7-91ef-185d572d3456
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767947(v=OCS.15)
ms:contentKeyID: 63969624
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8afea8450df1533928a0407fb81866351705186e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141674"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-mobile-user-access-in-lync-server-2013"></a><span data-ttu-id="56de2-102">Lync Server 2013에서 모바일 사용자 액세스 테스트</span><span class="sxs-lookup"><span data-stu-id="56de2-102">Test mobile user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="56de2-103">_**마지막으로 수정 된 항목:** 2014-06-07_</span><span class="sxs-lookup"><span data-stu-id="56de2-103">_**Topic Last Modified:** 2014-06-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="56de2-104">확인 일정</span><span class="sxs-lookup"><span data-stu-id="56de2-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="56de2-105">월간</span><span class="sxs-lookup"><span data-stu-id="56de2-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56de2-106">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="56de2-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="56de2-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="56de2-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56de2-108">필요한 권한</span><span class="sxs-lookup"><span data-stu-id="56de2-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="56de2-109">Lync Server 관리 셸을 사용 하 여 로컬로 실행 하는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="56de2-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="56de2-110">Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우, 사용자에 게는 CsMcxConference cmdlet을 실행할 수 있는 권한이 있는 RBAC 역할이 할당 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="56de2-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsMcxConference cmdlet.</span></span> <span data-ttu-id="56de2-111">이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="56de2-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="56de2-112">설명</span><span class="sxs-lookup"><span data-stu-id="56de2-112">Description</span></span>

<span data-ttu-id="56de2-113">모바일 장치 서비스를 사용 하면 다음과 같은 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56de2-113">The Mobility Service enables mobile device users to do such things as:</span></span>

1.  <span data-ttu-id="56de2-114">인스턴트 메시지 및 현재 상태 정보를 교환 합니다.</span><span class="sxs-lookup"><span data-stu-id="56de2-114">Exchange instant messages and presence information.</span></span>

2.  <span data-ttu-id="56de2-115">사용자의 무선 공급자가 아닌 음성 사서함을 내부적으로 저장 하 고 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="56de2-115">Store and retrieve voice mail internally instead of with their wireless provider.</span></span>

3.  <span data-ttu-id="56de2-116">직장 및 전화 접속 회의를 통한 통화와 같은 Lync Server 기능을 활용 합니다.</span><span class="sxs-lookup"><span data-stu-id="56de2-116">Take advantage of Lync Server capabilities such as Call via Work and dial-out conferencing.</span></span> <span data-ttu-id="56de2-117">CsMcxConference cmdlet은 사용자가 모바일 장치를 사용 하 여 Lync Server 회의에 참가 하 고 참가할 수 있는지 확인 하는 빠르고 쉬운 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="56de2-117">The Test-CsMcxConference cmdlet provides a quick and easy way to verify that users can join and participate in Lync Server conferences by using a mobile device.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="56de2-118">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="56de2-118">Running the test</span></span>

<span data-ttu-id="56de2-119">이 검사를 실행 하려면 각 계정에 대해 세 개의 Windows PowerShell 자격 증명 개체 (계정 이름과 암호가 포함 된 개체)를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="56de2-119">To run this check, you must create three Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="56de2-120">그런 다음 다음 예와 같이 Test-CsMcxConference를 호출할 때 이러한 자격 증명 개체와 두 계정의 SIP 주소를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="56de2-120">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsMcxConference as shown in the following example:</span></span>

    $organizerCred = Get-Credential "litwareinc\kenmyer"
    $user1Cred = Get-Credential "litwareinc\packerman"
    $user2Cred = Get-Credential "litwareinc\adelaney"
    
    Test-CsMcxConference -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -OrganizerSipAddress "sip:kenmyer@litwareinc.com" -OrganizerCredential $organizerCred -UserSipAddress "sip:pilar@litwareinc.com" -UserCredential $user1Cred -User2SipAddress "sip:adelaney@litwareinc.com" -User2Credential $user2Cred

<span data-ttu-id="56de2-121">자세한 내용은 [CsMcxConference](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxConference) cmdlet에 대 한 도움말 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="56de2-121">For more information, see the help topic for the [Test-CsMcxConference](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxConference) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="56de2-122">성공 또는 실패 확인</span><span class="sxs-lookup"><span data-stu-id="56de2-122">Determining success or failure</span></span>

<span data-ttu-id="56de2-123">확인에 성공 하면 Test-CsMcxConference는 테스트 결과의 성공 여부를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="56de2-123">If the check succeeds, Test-CsMcxConference will report a test result of Success:</span></span>

<span data-ttu-id="56de2-124">대상 Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="56de2-124">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="56de2-125">대상 Uri:http://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="56de2-125">Target Uri : http://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="56de2-126">결과: 성공</span><span class="sxs-lookup"><span data-stu-id="56de2-126">Result : Success</span></span>

<span data-ttu-id="56de2-127">대기 시간: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="56de2-127">Latency : 00:00:00</span></span>

<span data-ttu-id="56de2-128">오류 메시지:</span><span class="sxs-lookup"><span data-stu-id="56de2-128">Error Message :</span></span>

<span data-ttu-id="56de2-129">진단을</span><span class="sxs-lookup"><span data-stu-id="56de2-129">Diagnosis :</span></span>

<span data-ttu-id="56de2-130">확인이 실패 하면 Test-CsMcxConference는 실패의 테스트 결과를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="56de2-130">If the check is unsuccessful Test-CsMcxConference will report a test result of Failure.</span></span> <span data-ttu-id="56de2-131">이 테스트 결과에는 일반적으로 자세한 오류 메시지와 진단이 수반 됩니다.</span><span class="sxs-lookup"><span data-stu-id="56de2-131">This test result will typically be accompanied by a detailed error message and diagnosis.</span></span> <span data-ttu-id="56de2-132">예:</span><span class="sxs-lookup"><span data-stu-id="56de2-132">For example:</span></span>

<span data-ttu-id="56de2-133">대상 Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="56de2-133">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="56de2-134">대상 Uri:https://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="56de2-134">Target Uri : https://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="56de2-135">결과: 실패</span><span class="sxs-lookup"><span data-stu-id="56de2-135">Result : Failure</span></span>

<span data-ttu-id="56de2-136">대기 시간: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="56de2-136">Latency : 00:00:00</span></span>

<span data-ttu-id="56de2-137">오류 메시지: 웹 티켓 서비스에 대 한 응답이 수신 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="56de2-137">Error Message : No response received for Web-Ticket service.</span></span>

<span data-ttu-id="56de2-138">내부 예외: 클라이언트를 사용 하 여 HHTP 요청에 대 한 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="56de2-138">Inner Exception:The HHTP request is unauthorized with client</span></span>

<span data-ttu-id="56de2-139">협상 구성표 ' Ntlm '.</span><span class="sxs-lookup"><span data-stu-id="56de2-139">negotiation scheme 'Ntlm'.</span></span> <span data-ttu-id="56de2-140">수신 된 인증 헤더</span><span class="sxs-lookup"><span data-stu-id="56de2-140">The authentication header received</span></span>

<span data-ttu-id="56de2-141">서버에서 ' 협상 ' 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="56de2-141">from the server was 'Negotiate'.</span></span>

<span data-ttu-id="56de2-142">내부 예외: 원격 서버에서 오류를 반환 했습니다. (401)</span><span class="sxs-lookup"><span data-stu-id="56de2-142">Inner Exception:The remote server returned an error: (401)</span></span>

<span data-ttu-id="56de2-143">권한.</span><span class="sxs-lookup"><span data-stu-id="56de2-143">Unauthorized.</span></span>

<span data-ttu-id="56de2-144">진단을</span><span class="sxs-lookup"><span data-stu-id="56de2-144">Diagnosis :</span></span>

<span data-ttu-id="56de2-145">내부 진단: X-Fqdb: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="56de2-145">Inner Diagnosis:X-MS-server-Fqdb : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="56de2-146">Cache-컨트롤: private</span><span class="sxs-lookup"><span data-stu-id="56de2-146">Cache-Control : private</span></span>

<span data-ttu-id="56de2-147">Content-Type: text/html; charset = u t f-8</span><span class="sxs-lookup"><span data-stu-id="56de2-147">Content-Type : text/html; charset=utf-8.</span></span>

<span data-ttu-id="56de2-148">서버: Microsoft-IIS/8.5</span><span class="sxs-lookup"><span data-stu-id="56de2-148">Server : Microsoft-IIS/8.5</span></span>

<span data-ttu-id="56de2-149">WWW-인증: 협상, NTLM</span><span class="sxs-lookup"><span data-stu-id="56de2-149">WWW-Authenticate : Negotiate,NTLM</span></span>

<span data-ttu-id="56de2-150">X-전원 공급: ASP.NET</span><span class="sxs-lookup"><span data-stu-id="56de2-150">X-Powered-By : ASP.NET</span></span>

<span data-ttu-id="56de2-151">X-콘텐츠 형식-옵션: noexpression</span><span class="sxs-lookup"><span data-stu-id="56de2-151">X-Content-Type-Options : nosniff</span></span>

<span data-ttu-id="56de2-152">날짜: 수요일, 28 년 5 월 2014 19:22:19 GMT</span><span class="sxs-lookup"><span data-stu-id="56de2-152">Date : Wed, 28 May 2014 19:22:19 GMT</span></span>

<span data-ttu-id="56de2-153">콘텐츠 길이: 6305</span><span class="sxs-lookup"><span data-stu-id="56de2-153">Content-Length : 6305</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="56de2-154">테스트가 실패 한 이유</span><span class="sxs-lookup"><span data-stu-id="56de2-154">Reasons why the test might have failed</span></span>

<span data-ttu-id="56de2-155">Test-CsMcxConference 실패 하면 모바일 서비스가 실행 중이 고 액세스할 수 있는지 확인 하는 것으로 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="56de2-155">If Test-CsMcxConference fails you should begin by verifying that the mobility service is running and can be accessed.</span></span> <span data-ttu-id="56de2-156">이 작업은 웹 브라우저를 사용 하 여 Lync Server 풀의 모바일 서비스 URL에 액세스할 수 있는지를 확인 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56de2-156">That can be done by using a web browser to verify that the mobility service URL for your Lync Server pool can be accessed.</span></span> <span data-ttu-id="56de2-157">예를 들어 다음 명령은 atl-cs-001.litwareinc.com 풀에 대 한 URL을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="56de2-157">For example, this command verifies the URL for the pool atl-cs-001.litwareinc.com:</span></span>

`https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc`

<span data-ttu-id="56de2-158">모바일 서비스에 액세스할 수 있는 경우 테스트 사용자에 게 유효한 Lync Server 계정이 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="56de2-158">If the mobility service can be accessed you should then verify that your test users have valid Lync Server accounts.</span></span> <span data-ttu-id="56de2-159">다음과 같은 명령을 사용 하 여 계정 정보를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56de2-159">You can retrieve account information by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

<span data-ttu-id="56de2-160">Enabled 속성이 True가 아니거나 명령이 실패 하는 경우에는 사용자에 게 유효한 Lync Server 계정이 없음을 의미 합니다. 또한 각 사용자 계정이 모바일 기능을 사용할 수 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="56de2-160">If the Enabled property is not equal to True or if the command fails, that means that the user does not have a valid Lync Server account.You should also verify that each user account is enabled for mobility.</span></span> <span data-ttu-id="56de2-161">이 작업을 수행 하려면 먼저 계정에 할당 된 모바일 정책을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="56de2-161">To do that, first determine the mobility policy that is assigned to the account:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

<span data-ttu-id="56de2-162">정책 이름을 확인 한 후 Get-csmobilitypolicy cmdlet을 사용 하 여 문제의 정책 (예: RedmondMobilityPolicy)에 EnableMobility 속성이 True로 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="56de2-162">After you know the policy name, use the Get-CsMobilityPolicy cmdlet to verify that the policy in question (for example, RedmondMobilityPolicy) has the EnableMobility property set to True:</span></span>

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

<span data-ttu-id="56de2-163">유효한 사용자 계정을 지정 하지 않은 것을 의미 하는 테스트-CsMcxConference를 실행할 때 "인증 헤더" 오류 메시지가 표시 되 면 사용자 이름 및 암호를 확인 한 후 테스트를 다시 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="56de2-163">If you receive an “authentication header” error message when you run Test-CsMcxConference that often means that you have not specified a valid user account, Verify the user name and password and then try the test again.</span></span> <span data-ttu-id="56de2-164">사용자 계정이 유효한 것으로 확신 하는 경우 Set-cswebserviceconfiguration cmdlet을 사용 하 여 UseWindowsAuth 속성의 값을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="56de2-164">If you are convinced that the user account is valid, then use the Get-CsWebServiceConfiguration cmdlet and check the value of the UseWindowsAuth property.</span></span> <span data-ttu-id="56de2-165">그러면 조직에서 사용 하도록 설정 된 인증 방법을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56de2-165">That will tell you which authentication methods are enabled in your organization.</span></span>

<span data-ttu-id="56de2-166">모바일 서비스 문제를 해결 하는 방법에 대 한 자세한 내용은 블로그 게시물 [문제 해결 외부 Lync Mobility Connectivity 문제 단계별](https://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx)설명을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="56de2-166">For more tips about how to troubleshoot the mobility service, see the blog post [Troubleshooting External Lync Mobility Connectivity Issues Step-by-Step](https://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

