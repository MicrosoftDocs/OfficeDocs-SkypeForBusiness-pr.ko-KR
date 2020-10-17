---
title: 'Lync Server 2013: 익명 웹 앱 액세스 테스트'
description: 'Lync Server 2013: 익명 웹 앱 액세스를 테스트 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test anonymous Web App access
ms:assetid: 92f691cd-e05e-4bab-beb5-251d4b837a19
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767949(v=OCS.15)
ms:contentKeyID: 63969630
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11c33840912fefcaeef069e14773cfefd0834a8b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547474"
---
# <a name="test-anonymous-web-app-access-in-lync-server-2013"></a><span data-ttu-id="43a22-103">Lync Server 2013에서 익명 웹 앱 액세스 테스트</span><span class="sxs-lookup"><span data-stu-id="43a22-103">Test anonymous Web App access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="43a22-104">_**마지막으로 수정 된 항목:** 2014-06-07_</span><span class="sxs-lookup"><span data-stu-id="43a22-104">_**Topic Last Modified:** 2014-06-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="43a22-105">확인 일정</span><span class="sxs-lookup"><span data-stu-id="43a22-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="43a22-106">월간</span><span class="sxs-lookup"><span data-stu-id="43a22-106">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43a22-107">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="43a22-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="43a22-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="43a22-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43a22-109">필요한 권한</span><span class="sxs-lookup"><span data-stu-id="43a22-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="43a22-110">Lync Server 관리 셸을 사용 하 여 로컬로 실행 하는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="43a22-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="43a22-111">Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 사용자에 게 Test-CsWebAppAnonymous cmdlet을 실행 하는 권한이 있는 RBAC 역할을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="43a22-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsWebAppAnonymous cmdlet.</span></span> <span data-ttu-id="43a22-112">이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="43a22-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebAppAnonymous&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="43a22-113">설명</span><span class="sxs-lookup"><span data-stu-id="43a22-113">Description</span></span>

<span data-ttu-id="43a22-114">Test-CsWebAppAnonymous cmdlet은 Lync 웹 앱을 사용 하 여 익명 사용자가 Lync Server 회의에 참가할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="43a22-114">The Test-CsWebAppAnonymous cmdlet verifies that an anonymous user can join Lync Server conferences by using the Lync Web App.</span></span> <span data-ttu-id="43a22-115">Cmdlet을 실행 하면 Test-CsWebAppAnonymous가 웹 티켓 서비스에 연결 하 여 익명 사용자에 대 한 웹 티켓을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="43a22-115">When you run the cmdlet, Test-CsWebAppAnonymous contacts the Web Ticket service to obtain a web ticket for the anonymous user.</span></span> <span data-ttu-id="43a22-116">Cmdlet이이 티켓을 취득 하면 Test-CsWebAppAnonymous Lync Server에 연결 하 고 인스턴트 메시징, 응용 프로그램 공유 및 데이터 공동 작업에 대 한 별도의 전화 회의를 설정 해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="43a22-116">If the cmdlet succeeds in obtaining this ticket, Test-CsWebAppAnonymous will then contact Lync Server and attempt to establish separate conferences for instant messaging, application sharing, and data collaboration.</span></span>

<span data-ttu-id="43a22-117">Test-CsWebAppAnonymous는 이러한 회의를 만드는 데 사용 된 Api 및 연결만 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="43a22-117">Note that Test-CsWebAppAnonymous only verifies the APIs and connections used to create these conferences.</span></span> <span data-ttu-id="43a22-118">이 cmdlet은 실제로 회의를 만들고 수행 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="43a22-118">The cmdlet does not actually create and conduct any conferences.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="43a22-119">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="43a22-119">Running the test</span></span>

<span data-ttu-id="43a22-120">Test-CsWebAppAnonymous cmdlet은 미리 구성 된 테스트 계정 쌍 또는 Lync Server를 사용할 수 있는 두 사용자의 계정 중 하나를 사용 하 여 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="43a22-120">The Test-CsWebAppAnonymous cmdlet can be run using either a pair of preconfigured test accounts or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="43a22-121">테스트 계정을 사용 하 여이 검사를 실행 하려면 테스트할 Lync Server 풀의 정규화 된 도메인 이름을 지정 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="43a22-121">To run this check using test accounts, you just have to specify the fully qualified domain name of the Lync Server pool being tested.</span></span> <span data-ttu-id="43a22-122">예제:</span><span class="sxs-lookup"><span data-stu-id="43a22-122">For example:</span></span>

    Test-CsWebAppAnonymous -TargetFqdn atl-cs-001.litwareinc.com

<span data-ttu-id="43a22-123">실제 사용자 계정을 사용 하 여이 검사를 실행 하려면 각 계정에 대해 두 Lync Server 관리 셸 자격 증명 개체 (계정 이름과 암호가 포함 된 개체)를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="43a22-123">To run this check using actual user accounts, you must create two Lync Server Management Shell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="43a22-124">그런 다음 Test-cswebappanonymous를 호출할 때 이러한 자격 증명 개체와 두 계정의 SIP 주소를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="43a22-124">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsWebAppAnonymous:</span></span>

    $cred1 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsWebApp -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $cred1

<span data-ttu-id="43a22-125">자세한 내용은 Test-CsWebAppAnonymous cmdlet에 대 한 도움말 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="43a22-125">For more information, see the help topic for the Test-CsWebAppAnonymous cmdlet.</span></span> <span data-ttu-id="43a22-126">Test-CsWebAppAnonymous은 Lync Server 2013에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="43a22-126">Note that Test-CsWebAppAnonymous is deprecated for use on Lync Server 2013.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="43a22-127">성공 또는 실패 확인</span><span class="sxs-lookup"><span data-stu-id="43a22-127">Determining success or failure</span></span>

<span data-ttu-id="43a22-128">익명 사용자가 자신의 회의에 참가할 수 Test-CsWebAppAnonymous 경우 cmdlet은 테스트 결과 성공을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="43a22-128">If Test-CsWebAppAnonymous can join the anonymous user to his or her conferences, the cmdlet will return the test result Success:</span></span>

<span data-ttu-id="43a22-129">대상 Fqdn:</span><span class="sxs-lookup"><span data-stu-id="43a22-129">Target Fqdn :</span></span>

<span data-ttu-id="43a22-130">결과: 성공</span><span class="sxs-lookup"><span data-stu-id="43a22-130">Result : Success</span></span>

<span data-ttu-id="43a22-131">대기 시간: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="43a22-131">Latency : 00:00:00</span></span>

<span data-ttu-id="43a22-132">오류 메시지:</span><span class="sxs-lookup"><span data-stu-id="43a22-132">Error Message :</span></span>

<span data-ttu-id="43a22-133">진단을</span><span class="sxs-lookup"><span data-stu-id="43a22-133">Diagnosis :</span></span>

<span data-ttu-id="43a22-134">익명 사용자가 필요한 회의에 참가할 수 없으면 테스트 결과가 실패로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="43a22-134">If the anonymous user can't join the necessary conferences then the test result will be marked as Failure.</span></span> <span data-ttu-id="43a22-135">일반적으로 Test-CsWebAppAnonymous에서는 자세한 오류 메시지와 진단도 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="43a22-135">Typically Test-CsWebAppAnonymous will also report back a detailed error message and diagnosis:</span></span>

<span data-ttu-id="43a22-136">대상 Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="43a22-136">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="43a22-137">결과: 실패</span><span class="sxs-lookup"><span data-stu-id="43a22-137">Result : Failure</span></span>

<span data-ttu-id="43a22-138">대기 시간: 00:00:05.9746266</span><span class="sxs-lookup"><span data-stu-id="43a22-138">Latency : 00:00:05.9746266</span></span>

<span data-ttu-id="43a22-139">오류 메시지: Web-Ticket 서비스에 대 한 응답이 수신 되지 않음</span><span class="sxs-lookup"><span data-stu-id="43a22-139">Error Message : No response received for Web-Ticket service</span></span>

<span data-ttu-id="43a22-140">진단: HTTP 요청이 클라이언트와 함께 인증 되지 않음</span><span class="sxs-lookup"><span data-stu-id="43a22-140">Diagnosis : The HTTP request is unauthorized with client</span></span>

<span data-ttu-id="43a22-141">' Ntlm ' 인증 체계</span><span class="sxs-lookup"><span data-stu-id="43a22-141">authentication scheme 'Ntlm'.</span></span> <span data-ttu-id="43a22-142">인증</span><span class="sxs-lookup"><span data-stu-id="43a22-142">The authentication</span></span>

<span data-ttu-id="43a22-143">서버에서 받은 헤더가 ' 협상, NTLM ' 이었습니다.</span><span class="sxs-lookup"><span data-stu-id="43a22-143">header received from the server was 'Negotiate,NTLM'.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="43a22-144">테스트가 실패 한 이유</span><span class="sxs-lookup"><span data-stu-id="43a22-144">Reasons why the test might have failed</span></span>

<span data-ttu-id="43a22-145">Test-CsWebAppAnonymous 오류는 대개 사용자 인증 오류가 발생 하는 것을 중심으로 합니다. cmdlet이 Lync Server에 연결 하는 익명 사용자의 기능을 검사 하는 경우에도 유효한 사용자 계정을 사용 하 여 테스트를 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="43a22-145">Test-CsWebAppAnonymous failures usually revolve around user authentication errors: you must run the test using a valid user account even though the cmdlet is checking the ability of an anonymous user to connect to Lync Server.</span></span> <span data-ttu-id="43a22-146">Test-CsWebAppAnonymous 실패 하면 지정한 사용자에 게 유효한 Lync Server 사용자 계정이 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="43a22-146">If Test-CsWebAppAnonymous fails, you should verify that the specified user has valid a Lync Server user account.</span></span> <span data-ttu-id="43a22-147">다음과 같은 명령을 사용 하 여 Lync Server 계정 정보를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43a22-147">You can retrieve Lync Server account information by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

<span data-ttu-id="43a22-148">Enabled 속성이 True가 아니거나 명령이 실패 하는 경우에는 사용자에 게 유효한 Lync Server 계정이 없음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="43a22-148">If the Enabled property is not equal to True or if the command fails, that means that the user does not have a valid Lync Server account.</span></span>

<span data-ttu-id="43a22-149">또한 cmdlet을 실행할 때 제공한 암호가 유효한 암호 인지도 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="43a22-149">You should also verify that the password that you supplied when you run the cmdlet is a valid password.</span></span>

<span data-ttu-id="43a22-150">Office Web Apps 서버의 구성 문제로 인해 Test-CsWebAppAnonymous 실패할 수도 있습니다. 이는 종종 다음과 같은 진단을 받는 경우에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="43a22-150">Configuration problems with Office Web Apps Server can also cause Test-CsWebAppAnonymous to fail; that will often be the case if you receive the following diagnosis:</span></span>

<span data-ttu-id="43a22-151">HTTP 요청이 클라이언트 인증 체계 ' Ntlm '을 사용 하 여 인증 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="43a22-151">The HTTP request is unauthorized with client authentication scheme 'Ntlm'.</span></span> <span data-ttu-id="43a22-152">서버에서 받은 인증 헤더가 ' 협상, NTLM '입니다.</span><span class="sxs-lookup"><span data-stu-id="43a22-152">The authentication header received from the server was 'Negotiate,NTLM'.</span></span>

<span data-ttu-id="43a22-153">Office Web Apps 서버 문제를 진단 하 고 해결 하는 방법에 대 한 자세한 내용은 블로그 게시물 [Office Web Apps 서버 2013-시스템이 항상 비정상으로 보고 됨](http://www.wictorwilen.se/office-web-apps-server-2013---machines-are-always-reported-as-unhealthy)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="43a22-153">For more information on diagnosing and resolving Office Web Apps Server problems see the blog post [Office Web Apps Server 2013 - machines are always reported as Unhealthy](http://www.wictorwilen.se/office-web-apps-server-2013---machines-are-always-reported-as-unhealthy).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

