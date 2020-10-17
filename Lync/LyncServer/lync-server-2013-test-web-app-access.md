---
title: 'Lync Server 2013: 웹 앱 액세스 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test Web App access
ms:assetid: 17d67ea3-f74d-4952-ac2b-92c0dacc8014
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767944(v=OCS.15)
ms:contentKeyID: 63969584
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2cdf0c4d974732b75a7ff83022c6bfbf1c4d8e80
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532935"
---
# <a name="test-web-app-access-in-lync-server-2013"></a><span data-ttu-id="62233-102">Lync Server 2013에서 웹 앱 액세스 테스트</span><span class="sxs-lookup"><span data-stu-id="62233-102">Test Web App access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="62233-103">_**마지막으로 수정 된 항목:** 2014-06-07_</span><span class="sxs-lookup"><span data-stu-id="62233-103">_**Topic Last Modified:** 2014-06-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="62233-104">확인 일정</span><span class="sxs-lookup"><span data-stu-id="62233-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="62233-105">월간</span><span class="sxs-lookup"><span data-stu-id="62233-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62233-106">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="62233-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="62233-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="62233-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62233-108">필요한 권한</span><span class="sxs-lookup"><span data-stu-id="62233-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="62233-109">Lync Server 관리 셸을 사용 하 여 로컬로 실행 하는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="62233-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="62233-110">Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 사용자에 게 Test-CsWebApp cmdlet을 실행 하는 권한이 있는 RBAC 역할을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="62233-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsWebApp cmdlet.</span></span> <span data-ttu-id="62233-111">이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="62233-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebApp&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="62233-112">설명</span><span class="sxs-lookup"><span data-stu-id="62233-112">Description</span></span>

<span data-ttu-id="62233-113">Test-CsWebApp cmdlet은 인증 된 사용자가 Lync 웹 앱을 사용 하 여 Lync Server 회의에 참가할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="62233-113">The Test-CsWebApp cmdlet verifies that authenticated users can join Lync Server conferences by using the Lync Web App.</span></span> <span data-ttu-id="62233-114">Cmdlet을 실행 하면 Test-CsWebApp가 웹 티켓 서비스에 연결 하 여 지정 된 사용자에 대 한 웹 티켓을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="62233-114">When you run the cmdlet, Test-CsWebApp contacts the Web Ticket service to obtain web tickets for the specified users.</span></span> <span data-ttu-id="62233-115">이러한 티켓은 Lync Server 회의에 효과적으로 ' 허용 티켓 '으로 작용 합니다.</span><span class="sxs-lookup"><span data-stu-id="62233-115">These tickets effectively act as ‘admission tickets” to the Lync Server conference.</span></span> <span data-ttu-id="62233-116">티켓을 검색할 수 있고 사용자를 인증할 수 있는 경우에는 Lync Server에 연락 하 여 인스턴트 메시징, 응용 프로그램 공유 및 데이터 공동 작업에 대 한 별도의 회의를 설정 해 Test-CsWebApp 합니다.</span><span class="sxs-lookup"><span data-stu-id="62233-116">If the tickets can be retrieved, and if the users can be authenticated, Test-CsWebApp will then contact Lync Server and attempt to establish separate conferences for instant messaging, application sharing, and data collaboration.</span></span>

<span data-ttu-id="62233-117">Test-CsWebApp에서는 이러한 회의를 만드는 데 사용 되는 Api 및 연결만 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="62233-117">Note that Test-CsWebApp just verifies the APIs and connections used to create these conferences.</span></span> <span data-ttu-id="62233-118">이 cmdlet은 Lync Web App을 사용 하 여 회의를 만들고 참가할 수 있는지 확인 하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="62233-118">The cmdlet is designed to verify that Lync Web App could be used to create and join conferences.</span></span> <span data-ttu-id="62233-119">그러나 실제로 회의를 만들고 수행 하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="62233-119">However,, it does not actually create and conduct a conference.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="62233-120">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="62233-120">Running the test</span></span>

<span data-ttu-id="62233-121">Test-CsWebApp cmdlet은 미리 구성 된 테스트 계정 쌍 또는 Lync Server를 사용할 수 있는 두 사용자의 계정 중 하나를 사용 하 여 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="62233-121">The Test-CsWebApp cmdlet can be run using either a pair of preconfigured test accounts or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="62233-122">테스트 계정을 사용 하 여이 검사를 실행 하려면 테스트할 Lync Server 풀의 정규화 된 도메인 이름을 지정 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="62233-122">To run this check using test accounts, you just have to specify the fully qualified domain name of the Lync Server pool being tested.</span></span> <span data-ttu-id="62233-123">예제:</span><span class="sxs-lookup"><span data-stu-id="62233-123">For example:</span></span>

    Test-CsWebApp -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="62233-124">실제 사용자 계정을 사용 하 여이 검사를 실행 하려면 각 계정에 대해 두 개의 Windows PowerShell 자격 증명 개체 (계정 이름과 암호가 포함 된 개체)를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="62233-124">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="62233-125">그런 다음 Test-cswebapp를 호출할 때 이러한 자격 증명 개체와 두 계정의 SIP 주소를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="62233-125">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsWebApp:</span></span>

    $cred1 = Get-Credential "litwareinc\kenmyer"
    $cred2 = Get-Credential "litwareinc\pilar"
    
    Test-CsWebApp -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $cred1 -User2SipAddress "sip:pilar@litwareinc.com" -User2Credential $cred2

<span data-ttu-id="62233-126">자세한 내용은 [test-cswebapp](https://docs.microsoft.com/powershell/module/skype/Test-CsWebApp) cmdlet에 대 한 도움말 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="62233-126">For more information, see the help topic for the [Test-CsWebApp](https://docs.microsoft.com/powershell/module/skype/Test-CsWebApp) cmdlet.</span></span> <span data-ttu-id="62233-127">Test-CsWebApp은 Lync Server 2013에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="62233-127">Note that Test-CsWebApp was deprecated for use on Lync Server 2013.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="62233-128">성공 또는 실패 확인</span><span class="sxs-lookup"><span data-stu-id="62233-128">Determining success or failure</span></span>

<span data-ttu-id="62233-129">사용자가 전화 회의에 참가할 수 Test-CsWebApp 경우 cmdlet은 테스트 결과 성공을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="62233-129">If Test-CsWebApp can join the users to their conferences, the cmdlet will return the test result Success:</span></span>

<span data-ttu-id="62233-130">대상 Fqdn:</span><span class="sxs-lookup"><span data-stu-id="62233-130">Target Fqdn :</span></span>

<span data-ttu-id="62233-131">결과: 성공</span><span class="sxs-lookup"><span data-stu-id="62233-131">Result : Success</span></span>

<span data-ttu-id="62233-132">대기 시간: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="62233-132">Latency : 00:00:00</span></span>

<span data-ttu-id="62233-133">오류 메시지:</span><span class="sxs-lookup"><span data-stu-id="62233-133">Error Message :</span></span>

<span data-ttu-id="62233-134">진단을</span><span class="sxs-lookup"><span data-stu-id="62233-134">Diagnosis :</span></span>

<span data-ttu-id="62233-135">사용자가 필요한 회의에 참가할 수 없으면 테스트 결과가 실패로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="62233-135">If the users cannot join the necessary conferences then the test result will be marked as Failure.</span></span> <span data-ttu-id="62233-136">일반적으로 Test-CsWebApp에서는 자세한 오류 메시지와 진단도 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="62233-136">Typically Test-CsWebApp will also report back a detailed error message and diagnosis:</span></span>

<span data-ttu-id="62233-137">대상 Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="62233-137">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="62233-138">결과: 실패</span><span class="sxs-lookup"><span data-stu-id="62233-138">Result : Failure</span></span>

<span data-ttu-id="62233-139">대기 시간: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="62233-139">Latency : 00:00:00</span></span>

<span data-ttu-id="62233-140">오류 메시지: Web-Ticket 서비스에 대 한 응답이 수신 되지 않음</span><span class="sxs-lookup"><span data-stu-id="62233-140">Error Message : No response received for Web-Ticket service</span></span>

<span data-ttu-id="62233-141">진단: HTTP 요청이 클라이언트와 함께 인증 되지 않음</span><span class="sxs-lookup"><span data-stu-id="62233-141">Diagnosis : The HTTP request is unauthorized with client</span></span>

<span data-ttu-id="62233-142">' Ntlm ' 인증 체계</span><span class="sxs-lookup"><span data-stu-id="62233-142">authentication scheme 'Ntlm'.</span></span> <span data-ttu-id="62233-143">인증</span><span class="sxs-lookup"><span data-stu-id="62233-143">The authentication</span></span>

<span data-ttu-id="62233-144">서버에서 받은 헤더가 ' 협상, NTLM ' 이었습니다.</span><span class="sxs-lookup"><span data-stu-id="62233-144">header received from the server was 'Negotiate,NTLM'.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="62233-145">테스트가 실패 한 이유</span><span class="sxs-lookup"><span data-stu-id="62233-145">Reasons why the test might have failed</span></span>

<span data-ttu-id="62233-146">Test-CsWebApp 실패에는 일반적으로 사용자 인증 오류가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="62233-146">Test-CsWebApp failures typically involve user authentication errors.</span></span> <span data-ttu-id="62233-147">Test-CsWebApp 실패 하면 먼저 지정한 사용자에 게 유효한 사용자 계정이 있고 Lync Server에 대해 사용 하도록 설정 되어 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="62233-147">If Test-CsWebApp fails, you should first verify that the specified users have valid user accounts and are enabled for Lync Server.</span></span> <span data-ttu-id="62233-148">다음과 같은 명령을 사용 하 여 계정 정보를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62233-148">You can retrieve account information by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

<span data-ttu-id="62233-149">Enabled 속성이 True가 아니거나 명령이 실패 하는 경우에는 사용자에 게 유효한 Lync Server 계정이 없음을 의미 합니다. 또한 cmdlet에 제공한 암호가 유효한 지도 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="62233-149">If the Enabled property is not equal to True or if the command fails, that means that the user does not have a valid Lync Server account.You should also verify that the passwords that you supplied to the cmdlet are valid.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

