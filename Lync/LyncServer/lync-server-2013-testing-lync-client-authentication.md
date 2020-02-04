---
title: 'Lync Server 2013: Lync 클라이언트 인증 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Lync Client authentication
ms:assetid: e22114cb-4456-4e5f-93ab-51592c4a8209
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689120(v=OCS.15)
ms:contentKeyID: 63969659
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e24f579a4fcaca2651c0225b515241db00ff990
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745708"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-lync-client-authentication-in-lync-server-2013"></a><span data-ttu-id="2d75d-102">Lync Server 2013에서 Lync 클라이언트 인증 테스트</span><span class="sxs-lookup"><span data-stu-id="2d75d-102">Testing Lync Client authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2d75d-103">_**마지막으로 수정한 주제:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="2d75d-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2d75d-104">확인 일정</span><span class="sxs-lookup"><span data-stu-id="2d75d-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="2d75d-105">Daily</span><span class="sxs-lookup"><span data-stu-id="2d75d-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d75d-106">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="2d75d-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="2d75d-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2d75d-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d75d-108">권한이 필요 함</span><span class="sxs-lookup"><span data-stu-id="2d75d-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="2d75d-109">Lync Server Management Shell을 사용 하 여 로컬에서 실행 되는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d75d-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="2d75d-110">Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 사용자에 게는 테스트-CsClientAuth cmdlet을 실행할 권한이 있는 RBAC 역할을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d75d-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsClientAuth cmdlet.</span></span> <span data-ttu-id="2d75d-111">이 cmdlet을 사용할 수 있는 모든 RBAC 역할 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d75d-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsClientAuth&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="2d75d-112">설명</span><span class="sxs-lookup"><span data-stu-id="2d75d-112">Description</span></span>

<span data-ttu-id="2d75d-113">테스트-CsClientAuth cmdlet을 사용 하 여 사용자가 클라이언트 인증서를 사용 하 여 Lync Server에 로그온 할 수 있는지 여부를 확인할 수 있습니다. 테스트-CsClientAuth cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d75d-113">The Test-CsClientAuth cmdlet enables you to determine whether a user can log on to the Lync Server by using a client certificate, you can run the Test-CsClientAuth cmdlet.</span></span> <span data-ttu-id="2d75d-114">테스트-CsClientAuth를 호출한 후 cmdlet은 인증서 프로비저닝 서비스에 연결 하 고 지정 된 사용자에 대 한 클라이언트 인증서의 복사본을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d75d-114">After calling Test-CsClientAuth, the cmdlet will contact the certificate provisioning service and download a copy of any client certificates for the specified user.</span></span> <span data-ttu-id="2d75d-115">클라이언트 인증서를 찾아서 다운로드할 수 있는 경우 테스트-CsClientAuth에서 해당 인증서를 사용 하 여 로그온을 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d75d-115">If a client certificate can be found and downloaded, Test-CsClientAuth will then attempt to log on by using that certificate.</span></span> <span data-ttu-id="2d75d-116">로그온에 성공 하면 테스트-CsClientAuth에서 로그 오프 하 고 테스트에 성공 했음을 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d75d-116">If logon succeeds, Test-CsClientAuth will log off and report that the test succeeded.</span></span> <span data-ttu-id="2d75d-117">인증서를 찾을 수 없거나 다운로드할 수 없는 경우 또는 cmdlet이 해당 인증서를 사용 하 여 로그온 할 수 없는 경우 테스트-CsClientAuth에서 테스트가 실패 한 것으로 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d75d-117">If a certificate cannot be found or downloaded, or if the cmdlet is unable to logon using that certificate, then Test-CsClientAuth will report that the test failed.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="2d75d-118">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="2d75d-118">Running the test</span></span>

<span data-ttu-id="2d75d-119">테스트-CsClientAuth cmdlet은 Lync Server에 대해 사용 하도록 설정 된 모든 사용자의 계정을 사용 하 여 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d75d-119">The Test-CsClientAuth cmdlet is run by using the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="2d75d-120">실제 사용자 계정을 사용 하 여이 검사를 실행 하려면 먼저 계정 이름과 암호를 포함 하는 Windows PowerShell 자격 증명 개체를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d75d-120">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="2d75d-121">그런 다음 시스템에서 테스트 CsClientAuth를 호출할 때 계정에 할당 된 해당 자격 증명 개체와 SIP 주소를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d75d-121">You must then include that credentials object and the SIP address assigned to the account when the system calls Test-CsClientAuth:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsClientAuth -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="2d75d-122">자세한 내용은 [CsClientAuth](http://technet.microsoft.com/en-us/library/gg398712\(v=ocs.14\).aspx) cmdlet에 대 한 도움말 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2d75d-122">For more information, see the Help documentation for the [Test-CsClientAuth](http://technet.microsoft.com/en-us/library/gg398712\(v=ocs.14\).aspx) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="2d75d-123">성공 또는 실패 확인</span><span class="sxs-lookup"><span data-stu-id="2d75d-123">Determining success or failure</span></span>

<span data-ttu-id="2d75d-124">지정 된 사용자가 클라이언트 인증서를 사용 하 여 Lync Server에 로그온 할 수 있는 경우 다음과 유사한 출력이 표시 되며 결과 속성이 성공으로 표시 됩니다 **.**</span><span class="sxs-lookup"><span data-stu-id="2d75d-124">If the specified user can log on to Lync Server by using a client certificate, you will receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="2d75d-125">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="2d75d-125">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="2d75d-126">결과: 성공</span><span class="sxs-lookup"><span data-stu-id="2d75d-126">Result : Success</span></span>

<span data-ttu-id="2d75d-127">대기 시간: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="2d75d-127">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="2d75d-128">오류</span><span class="sxs-lookup"><span data-stu-id="2d75d-128">Error :</span></span>

<span data-ttu-id="2d75d-129">있게</span><span class="sxs-lookup"><span data-stu-id="2d75d-129">Diagnosis :</span></span>

<span data-ttu-id="2d75d-130">지정 된 사용자가 로그온 할 수 없는 경우 결과가 실패로 표시 되 고 오류 및 진단 속성에 추가 정보가 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d75d-130">If the specified user can not log on, the Result will be shown as Failure and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="2d75d-131">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="2d75d-131">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="2d75d-132">결과: 실패</span><span class="sxs-lookup"><span data-stu-id="2d75d-132">Result : Failure</span></span>

<span data-ttu-id="2d75d-133">대기 시간: 00:00:03.3645259</span><span class="sxs-lookup"><span data-stu-id="2d75d-133">Latency : 00:00:03.3645259</span></span>

<span data-ttu-id="2d75d-134">오류: 지정 된 사용자에 대 한 CS 인증서를 다운로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2d75d-134">Error : Could not download a CS Certificate for the given user.</span></span> <span data-ttu-id="2d75d-135">여부 확인</span><span class="sxs-lookup"><span data-stu-id="2d75d-135">Check if</span></span>

<span data-ttu-id="2d75d-136">제공 된 uri 및 자격 증명이 올바릅니다.</span><span class="sxs-lookup"><span data-stu-id="2d75d-136">provided uri and credentials are correct.</span></span>

<span data-ttu-id="2d75d-137">있게</span><span class="sxs-lookup"><span data-stu-id="2d75d-137">Diagnosis :</span></span>

<span data-ttu-id="2d75d-138">예를 들어 이전 출력은 지정 된 사용자에 대 한 유효한 클라이언트 인증서를 찾을 수 없기 때문에 테스트가 실패 했다는 것을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d75d-138">For example, the previous output states that the test failed because a valid client certificate couldn't be located for the specified user.</span></span> <span data-ttu-id="2d75d-139">다음과 같이 명령을 실행 하 여 사용자에 게 발급 된 클라이언트 인증서의 목록을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d75d-139">You can return a list of the client certificates issued to a user by running a command as follows:</span></span>

    Get-CsClientCertificate -Identity "sip:kenmyer@litwareinc.com"

<span data-ttu-id="2d75d-140">테스트-CsClientAuth에 실패 하는 경우 다음과 같이 Verbose 매개 변수를 포함 하 여 테스트를 다시 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d75d-140">If Test-CsClientAuth fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsClientAuth -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential -Verbose

<span data-ttu-id="2d75d-141">Verbose 매개 변수가 포함 된 경우 테스트-CsClientAuth에서는 지정 된 사용자가 Lync Server에 로그온 하는 기능을 검사 한 경우 시도한 각 작업의 단계별 계정을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d75d-141">When the Verbose parameter is included, Test-CsClientAuth will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="2d75d-142">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2d75d-142">For example:</span></span>

<span data-ttu-id="2d75d-143">사용자에 대 한 CS 인증서를 다운로드 하는 중: kenmyer@litwareinc.com endpoint: Stid</span><span class="sxs-lookup"><span data-stu-id="2d75d-143">Trying to download a CS certificate for User : kenmyer@litwareinc.com endpoint : STEpid</span></span>

<span data-ttu-id="2d75d-144">웹 서비스 url:https://atl-cs-001.litwareinc.com:443/CertProv/CertprovisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="2d75d-144">Web Service url : https://atl-cs-001.litwareinc.com:443/CertProv/CertprovisioningService.svc</span></span>

<span data-ttu-id="2d75d-145">웹 서비스에서 CS 인증서를 다운로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2d75d-145">Could not download a CS certificate from web service.</span></span>

<span data-ttu-id="2d75d-146">검사가</span><span class="sxs-lookup"><span data-stu-id="2d75d-146">CHECK:</span></span>

<span data-ttu-id="2d75d-147">\-웹 서비스 url이 올바르며 웹 서비스가 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d75d-147">\- Web service url is valid and the web services are functional</span></span>

<span data-ttu-id="2d75d-148">\-PhoneNo\\\\Pin을 사용 하 여 인증 하는 경우 사용자 uri와 일치 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d75d-148">\- If using PhoneNo\\\\Pin to authenticate, make sure they match the user uri</span></span>

<span data-ttu-id="2d75d-149">\-NTLM\\Kerberos 인증을 사용 하는 경우 유효한 자격 증명을 제공 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d75d-149">\- If using NTLM\\Kerberos auth, make sure you provided valid credentials</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="2d75d-150">테스트가 실패할 수 있는 이유</span><span class="sxs-lookup"><span data-stu-id="2d75d-150">Reasons why the test might have failed</span></span>

<span data-ttu-id="2d75d-151">테스트-CsClientAuth에 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2d75d-151">Here are some common reasons why Test-CsClientAuth might fail:</span></span>

  - <span data-ttu-id="2d75d-152">잘못 된 사용자 계정을 지정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="2d75d-152">You specified a user account that was not valid.</span></span> <span data-ttu-id="2d75d-153">다음과 같은 명령을 실행 하 여 사용자 계정이 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d75d-153">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="2d75d-154">사용자 계정이 올바르지만 현재 Lync Server에서 계정을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2d75d-154">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="2d75d-155">Lync Server에 대해 사용자 계정이 설정 되어 있는지 확인 하려면 다음과 같은 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d75d-155">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="2d75d-156">Enabled 속성이 False로 설정 된 경우 사용자가 현재 Lync Server에 대해 사용 하도록 설정 되어 있지 않음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d75d-156">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="2d75d-157">테스트 사용자에 게 유효한 클라이언트 인증서가 없을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d75d-157">The test user might not have a valid client certificate.</span></span> <span data-ttu-id="2d75d-158">다음과 같은 명령을 사용 하 여 사용자에 게 할당 된 클라이언트 인증서에 대 한 정보를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d75d-158">You can return information about the client certificates assigned to a user by using a command similar to this:</span></span>
    
        Get-CsClientCertificate -Identity "sip:kenmyer@litwareinc.com"

</div>

</div>

<span> </span>

</div>

</div>

</div>

