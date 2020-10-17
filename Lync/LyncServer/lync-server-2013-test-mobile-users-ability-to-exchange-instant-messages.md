---
title: 'Lync Server 2013: 인스턴트 메시지를 교환 하는 모바일 사용자 기능 테스트'
description: 'Lync Server 2013: 모바일 사용자가 인스턴트 메시지를 교환 하는 기능을 테스트 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test mobile users' ability to exchange instant messages
ms:assetid: a78a048f-d413-4bee-8626-d62b8b74f811
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767950(v=OCS.15)
ms:contentKeyID: 63969638
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 675bbeff93fed374d950b2efbdf15b4ea246f861
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558294"
---
# <a name="test-mobile-users-ability-to-exchange-instant-messages-in-lync-server-2013"></a><span data-ttu-id="92bff-103">Lync Server 2013에서 모바일 사용자의 인스턴트 메시지 교환 기능 테스트</span><span class="sxs-lookup"><span data-stu-id="92bff-103">Test mobile users' ability to exchange instant messages in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="92bff-104">_**마지막으로 수정 된 항목:** 2014-06-07_</span><span class="sxs-lookup"><span data-stu-id="92bff-104">_**Topic Last Modified:** 2014-06-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="92bff-105">확인 일정</span><span class="sxs-lookup"><span data-stu-id="92bff-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="92bff-106">월간</span><span class="sxs-lookup"><span data-stu-id="92bff-106">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92bff-107">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="92bff-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="92bff-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="92bff-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="92bff-109">필요한 권한</span><span class="sxs-lookup"><span data-stu-id="92bff-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="92bff-110">Lync Server 관리 셸을 사용 하 여 로컬로 실행 하는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="92bff-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="92bff-111">Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 사용자에 게 Test-CsMcxP2PIM cmdlet을 실행 하는 권한이 있는 RBAC 역할을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="92bff-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsMcxP2PIM cmdlet.</span></span> <span data-ttu-id="92bff-112">이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="92bff-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxP2PIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="92bff-113">설명</span><span class="sxs-lookup"><span data-stu-id="92bff-113">Description</span></span>

<span data-ttu-id="92bff-114">모바일 장치 서비스를 사용 하면 다음과 같은 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92bff-114">The Mobility Service enables mobile device users to do such things as:</span></span>

1.  <span data-ttu-id="92bff-115">인스턴트 메시지 및 현재 상태 정보를 교환 합니다.</span><span class="sxs-lookup"><span data-stu-id="92bff-115">Exchange instant messages and presence information.</span></span>

2.  <span data-ttu-id="92bff-116">사용자의 무선 공급자가 아닌 음성 사서함을 내부적으로 저장 하 고 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="92bff-116">Store and retrieve voice mail internally instead of with their wireless provider.</span></span>

3.  <span data-ttu-id="92bff-117">직장 및 전화 접속 회의를 통한 통화와 같은 Lync Server 기능을 활용 합니다.</span><span class="sxs-lookup"><span data-stu-id="92bff-117">Take advantage of Lync Server capabilities such as Call via Work and dial-out conferencing.</span></span>

<span data-ttu-id="92bff-118">Test-CsMxcP2PIM cmdlet은 사용자가 모바일 서비스를 사용 하 여 인스턴트 메시지를 교환할 수 있는지 확인 하는 빠르고 쉬운 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="92bff-118">The Test-CsMxcP2PIM cmdlet provides a quick and easy way to verify that users can use the Mobility Service to exchange instant messages.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="92bff-119">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="92bff-119">Running the test</span></span>

<span data-ttu-id="92bff-120">이 테스트를 실행 하려면 각 계정에 대해 두 개의 Windows PowerShell 자격 증명 개체 (계정 이름과 암호가 포함 된 개체)를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="92bff-120">To run this test, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="92bff-121">그런 다음 Test-csmcxp2pim를 호출할 때 이러한 자격 증명 개체와 두 계정의 SIP 주소를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="92bff-121">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsMcxP2PIM:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\pilar"
    
    Test-CsMcxP2PIM -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -SenderSipAddres "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:packerman@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="92bff-122">자세한 내용은 [test-csmcxp2pim](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM) cmdlet에 대 한 도움말 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="92bff-122">For more information, see the help topic for the [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="92bff-123">성공 또는 실패 확인</span><span class="sxs-lookup"><span data-stu-id="92bff-123">Determining success or failure</span></span>

<span data-ttu-id="92bff-124">두 테스트 사용자가 모바일 서비스를 사용 하 여 인스턴트 메시지를 교환할 수 있으면 Test-CsMcxP2PIM에서는 테스트 결과 성공을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="92bff-124">If the two test users can exchange instant messages by using the mobility service then Test-CsMcxP2PIM will return test result Success:</span></span>

<span data-ttu-id="92bff-125">대상 Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="92bff-125">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="92bff-126">대상 Uri: http://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="92bff-126">Target Uri : http://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="92bff-127">결과: 성공</span><span class="sxs-lookup"><span data-stu-id="92bff-127">Result : Success</span></span>

<span data-ttu-id="92bff-128">대기 시간: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="92bff-128">Latency : 00:00:00</span></span>

<span data-ttu-id="92bff-129">오류 메시지:</span><span class="sxs-lookup"><span data-stu-id="92bff-129">Error Message :</span></span>

<span data-ttu-id="92bff-130">진단을</span><span class="sxs-lookup"><span data-stu-id="92bff-130">Diagnosis :</span></span>

<span data-ttu-id="92bff-131">테스트가 실패 하면 결과가 실패로 설정 되 고 자세한 오류 메시지와 진단이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="92bff-131">If the test fails then the Result will be set to Failure and a detailed error message and diagnosis will be displayed:</span></span>

<span data-ttu-id="92bff-132">대상 Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="92bff-132">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="92bff-133">대상 Uri: https://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="92bff-133">Target Uri : https://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="92bff-134">결과: 실패</span><span class="sxs-lookup"><span data-stu-id="92bff-134">Result : Failure</span></span>

<span data-ttu-id="92bff-135">대기 시간: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="92bff-135">Latency : 00:00:00</span></span>

<span data-ttu-id="92bff-136">오류 메시지: Web-Ticket 서비스에 대 한 응답이 수신 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="92bff-136">Error Message : No response received for Web-Ticket service.</span></span>

<span data-ttu-id="92bff-137">내부 예외: HHTP 요청에 대해 권한이 부여 되지 않음</span><span class="sxs-lookup"><span data-stu-id="92bff-137">Inner Exception:The HHTP request is unauthorized with</span></span>

<span data-ttu-id="92bff-138">클라이언트 협상 구성표 ' Ntlm '.</span><span class="sxs-lookup"><span data-stu-id="92bff-138">client negotiation scheme 'Ntlm'.</span></span> <span data-ttu-id="92bff-139">인증</span><span class="sxs-lookup"><span data-stu-id="92bff-139">The authentication</span></span>

<span data-ttu-id="92bff-140">서버에서 받은 헤더가 ' 협상, NTLM ' 이었습니다.</span><span class="sxs-lookup"><span data-stu-id="92bff-140">header received from the server was 'Negotiate,NTLM'.</span></span>

<span data-ttu-id="92bff-141">내부 예외: 원격 서버에서 오류를 반환 했습니다.</span><span class="sxs-lookup"><span data-stu-id="92bff-141">Inner Exception:The remote server returned an error:</span></span>

<span data-ttu-id="92bff-142">(401) 인증 되지 않음</span><span class="sxs-lookup"><span data-stu-id="92bff-142">(401) Unauthorized.</span></span>

<span data-ttu-id="92bff-143">진단을</span><span class="sxs-lookup"><span data-stu-id="92bff-143">Diagnosis :</span></span>

<span data-ttu-id="92bff-144">내부 진단: X-Fqdb: atl-cs-</span><span class="sxs-lookup"><span data-stu-id="92bff-144">Inner Diagnosis:X-MS-server-Fqdb : atl-cs-</span></span>

<span data-ttu-id="92bff-145">001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="92bff-145">001.litwareinc.com</span></span>

<span data-ttu-id="92bff-146">Cache-Control: private</span><span class="sxs-lookup"><span data-stu-id="92bff-146">Cache-Control : private</span></span>

<span data-ttu-id="92bff-147">Content-Type: text/html; charset = u t f-8</span><span class="sxs-lookup"><span data-stu-id="92bff-147">Content-Type : text/html; charset=utf-8.</span></span>

<span data-ttu-id="92bff-148">서버: Microsoft-IIS/8.5</span><span class="sxs-lookup"><span data-stu-id="92bff-148">Server : Microsoft-IIS/8.5</span></span>

<span data-ttu-id="92bff-149">WWW-Authenticate: 협상, NTLM</span><span class="sxs-lookup"><span data-stu-id="92bff-149">WWW-Authenticate : Negotiate,NTLM</span></span>

<span data-ttu-id="92bff-150">X-전원 공급: ASP.NET</span><span class="sxs-lookup"><span data-stu-id="92bff-150">X-Powered-By : ASP.NET</span></span>

<span data-ttu-id="92bff-151">X-콘텐츠 형식-옵션: noexpression</span><span class="sxs-lookup"><span data-stu-id="92bff-151">X-Content-Type-Options : nosniff</span></span>

<span data-ttu-id="92bff-152">날짜: 수요일, 28 년 5 월 2014 19:16:05 GMT</span><span class="sxs-lookup"><span data-stu-id="92bff-152">Date : Wed, 28 May 2014 19:16:05 GMT</span></span>

<span data-ttu-id="92bff-153">콘텐츠 길이: 6305</span><span class="sxs-lookup"><span data-stu-id="92bff-153">Content-Length : 6305</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="92bff-154">테스트가 실패 한 이유</span><span class="sxs-lookup"><span data-stu-id="92bff-154">Reasons why the test might have failed</span></span>

<span data-ttu-id="92bff-155">Test-CsMcxP2PIM에 오류가 발생 하는 경우 첫 번째 단계는 mobility service가 작동 하 고 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="92bff-155">If Test-CsMcxP2PIM fails your first step should be to verify that the mobility service is up and running.</span></span> <span data-ttu-id="92bff-156">이 작업은 웹 브라우저를 사용 하 여 Lync Server 풀의 모바일 서비스 URL에 액세스할 수 있는지를 확인 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92bff-156">That can be done by using a web browser to verify that the mobility service URL for your Lync Server pool can be accessed.</span></span> <span data-ttu-id="92bff-157">예를 들어 다음 명령은 atl-cs-001.litwareinc.com 풀에 대 한 URL을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="92bff-157">For example, this command verifies the URL for the pool atl-cs-001.litwareinc.com:</span></span>

    https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc

<span data-ttu-id="92bff-158">모바일 서비스가 실행 되 고 있는 것 처럼 보이면 두 테스트 사용자의 Lync Server 계정이 유효한 지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="92bff-158">If the mobility service seems to be running then verify that your two test users have valid Lync Server accounts.</span></span> <span data-ttu-id="92bff-159">다음과 같은 명령을 사용 하 여 계정 정보를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92bff-159">You can retrieve account information by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

<span data-ttu-id="92bff-160">Enabled 속성이 True가 아니거나 명령이 실패 하는 경우에는 사용자에 게 유효한 Lync Server 계정이 없음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="92bff-160">If the Enabled property is not equal to True or if the command fails, that means that the user does not have a valid Lync Server account.</span></span>

<span data-ttu-id="92bff-161">또한 사용자가 모바일 기능을 사용할 수 있도록 설정 되어 있는지도 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="92bff-161">You should also verify that the user is enabled for mobility.</span></span> <span data-ttu-id="92bff-162">이 작업을 수행 하려면 먼저 계정에 할당 된 모바일 정책을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="92bff-162">To do that, first determine the mobility policy that is assigned to the account:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

<span data-ttu-id="92bff-163">정책 이름을 확인 한 후에 Get-CsMobilityPolicy cmdlet을 사용 하 여 문제의 정책 (예: RedmondMobilityPolicy)이 EnableMobility 속성을 True로 설정 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="92bff-163">After you know the policy name, use the Get-CsMobilityPolicy cmdlet to verify that the policy in question (for example, RedmondMobilityPolicy) has the EnableMobility property set to True:</span></span>

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

<span data-ttu-id="92bff-164">인증 헤더와 함께 오류 메시지가 표시 되는 경우에는 종종 유효한 사용자 계정을 지정 하지 않은 것입니다.</span><span class="sxs-lookup"><span data-stu-id="92bff-164">If you receive an error message with authentication headers, that often means that you have not specified a valid user account.</span></span> <span data-ttu-id="92bff-165">사용자 이름 및 암호를 확인 한 후 테스트를 다시 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="92bff-165">Verify the user name and password and then try the test again.</span></span> <span data-ttu-id="92bff-166">사용자 계정이 유효한 것으로 확신 하면 Get-CsWebServiceConfiguration cmdlet을 사용 하 여 UseWindowsAuth 속성의 값을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="92bff-166">If you are convinced that the user account is valid, then use the Get-CsWebServiceConfiguration cmdlet and check the value of the UseWindowsAuth property.</span></span> <span data-ttu-id="92bff-167">그러면 조직에서 사용 하도록 설정 된 인증 방법을 확인할 수 있습니다. 모바일 서비스 문제를 해결 하는 방법에 대 한 자세한 내용은 블로그 게시물 [문제 해결 외부 Lync Mobility Connectivity 문제 단계별](https://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx)설명을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="92bff-167">That will tell you which authentication methods are enabled in your organization.For more tips about how to troubleshoot the mobility service, see the blog post [Troubleshooting External Lync Mobility Connectivity Issues Step-by-Step](https://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

