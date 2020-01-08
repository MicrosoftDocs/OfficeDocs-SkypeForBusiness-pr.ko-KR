---
title: 'Lync Server 2013: Lync Phone Edition 로그인 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing Lync Phone Edition login
ms:assetid: 1ccde6bf-9a2d-4fcf-b81f-1bc9fee2cfbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690128(v=OCS.15)
ms:contentKeyID: 63969583
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cb2cf0dae748cf82e83e86389abf55c55c8c70e8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985327"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-lync-phone-edition-login-in-lync-server-2013"></a><span data-ttu-id="0b35f-102">Lync Server 2013에서 Lync Phone Edition 로그인 테스트</span><span class="sxs-lookup"><span data-stu-id="0b35f-102">Testing Lync Phone Edition login in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0b35f-103">_**마지막으로 수정한 주제:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="0b35f-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0b35f-104">확인 일정</span><span class="sxs-lookup"><span data-stu-id="0b35f-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="0b35f-105">Daily</span><span class="sxs-lookup"><span data-stu-id="0b35f-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b35f-106">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="0b35f-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="0b35f-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0b35f-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b35f-108">권한이 필요 함</span><span class="sxs-lookup"><span data-stu-id="0b35f-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="0b35f-109">Lync Server Management Shell을 사용 하 여 로컬에서 실행 되는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b35f-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="0b35f-110">Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 CsPhoneBootstrap cmdlet을 실행 하는 데 필요한 권한이 있는 RBAC 역할을 사용자에 게 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b35f-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsPhoneBootstrap cmdlet.</span></span> <span data-ttu-id="0b35f-111">이 cmdlet을 사용할 수 있는 모든 RBAC 역할 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b35f-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPhoneBootstrap&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="0b35f-112">설명</span><span class="sxs-lookup"><span data-stu-id="0b35f-112">Description</span></span>

<span data-ttu-id="0b35f-113">관리자는 CsPhoneBootstrap cmdlet을 사용 하 여 지정 된 사용자 (자신에 게 할당 된 전화 번호 및 PIN을 사용 하 여 Lync 2013 Phone Edition 호환 가능 장치에서 시스템에 로그온 할 수 있음)을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b35f-113">The Test-CsPhoneBootstrap cmdlet enables administrators to verify that a given user—using the phone number and PIN assigned to him or her—can log on to the system from a Lync 2013 Phone Edition-compatible device.</span></span> <span data-ttu-id="0b35f-114">(테스트를 실행 하는 데 실제로 장치가 필요 하지 않습니다.)</span><span class="sxs-lookup"><span data-stu-id="0b35f-114">(No device is actually needed to run the test.)</span></span>

<span data-ttu-id="0b35f-115">테스트-CsPhoneBootstrap 검사를 수행 하려면 테스트 중인 사용자 계정을 호스트 하는 등록자 풀이 DHCP를 사용 하 여 검색 가능 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b35f-115">In order for Test-CsPhoneBootstrap to make its check, the Registrar pool that hosts the user account being tested must be discoverable using DHCP.</span></span> <span data-ttu-id="0b35f-116">이 방법으로 등록자를 검색할 수 있는지 여부를 확인 하려면 cmdlet CsRegistrarConfiguration를 사용 하 여 EnableDHCPServer 속성 값을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b35f-116">To determine whether a Registrar is discoverable in this manner, use the cmdlet Get-CsRegistrarConfiguration and check the value of the EnableDHCPServer property.</span></span> <span data-ttu-id="0b35f-117">이 속성이 False로 설정 되어 있으면 Set-CsRegistrarConfiguration를 사용 하 여 속성 값을 True로 설정 하 고 등록자를 DHCP를 사용 하 여 검색 가능 하 게 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b35f-117">If this property is set to False, you must use Set-CsRegistrarConfiguration to set the property value to True and make the Registrar discoverable using DHCP.</span></span> <span data-ttu-id="0b35f-118">엔터프라이즈 DHCP 서버를 사용 하 고 Lync Server 관련 옵션을 구성 하는 방법으로도이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b35f-118">This can also be done by using Enterprise DHCP Server and configuring the Lync Server-specific options.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="0b35f-119">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="0b35f-119">Running the test</span></span>

<span data-ttu-id="0b35f-120">CsPhoneBootstrap cmdlet을 실행 하려면 최소한 올바른 Lync Server 사용자에 대 한 전화 번호 및 클라이언트 PIN (개인 식별 번호)을 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b35f-120">To run the Test-CsPhoneBootstrap cmdlet, you must, at a minimum, supply the phone number and client personal identification number (PIN) for a valid Lync Server user.</span></span> <span data-ttu-id="0b35f-121">예를 들어이 명령은 전화 번호 12065551219와 PIN 0712이 있는 사용자의 로그온 기능을 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b35f-121">For example, this command tests the logon ability for the user who has the phone number 12065551219 and the PIN 0712:</span></span>

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712"

<span data-ttu-id="0b35f-122">더 포괄적인 검사를 위해 사용자의 SIP 주소도 포함할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b35f-122">For a more comprehensive check, you can also include the user’s SIP address.</span></span> <span data-ttu-id="0b35f-123">이 경우 테스트에 성공 하려면 전화 번호, 클라이언트 PIN 및 SIP 주소가 모두 유효 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b35f-123">In that case, the phone number, client PIN, and SIP address must all be valid for the test to succeed:</span></span>

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712" -UserSipAddress "sip:kenmyer@litwareinc.com"

<span data-ttu-id="0b35f-124">자세한 내용은 [테스트 CsPhoneBootstrap](https://docs.microsoft.com/powershell/module/skype/Test-CsPhoneBootstrap) cmdlet에 대 한 도움말 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0b35f-124">For more information, see the Help documentation for the [Test-CsPhoneBootstrap](https://docs.microsoft.com/powershell/module/skype/Test-CsPhoneBootstrap) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="0b35f-125">성공 또는 실패 확인</span><span class="sxs-lookup"><span data-stu-id="0b35f-125">Determining success or failure</span></span>

<span data-ttu-id="0b35f-126">지정 된 사용자가 Lync Server에 연결할 수 있는 경우 결과 속성이 성공으로 표시 된 것과 비슷한 출력을 받게 됩니다 **.**</span><span class="sxs-lookup"><span data-stu-id="0b35f-126">If the specified user was able to connect to Lync Server, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="0b35f-127">TargetUri :https://atl-cs-001.litwareinc.com:443/CertProv/</span><span class="sxs-lookup"><span data-stu-id="0b35f-127">TargetUri : https://atl-cs-001.litwareinc.com:443/CertProv/</span></span>

<span data-ttu-id="0b35f-128">CertProvisioningService</span><span class="sxs-lookup"><span data-stu-id="0b35f-128">CertProvisioningService.svc</span></span>

<span data-ttu-id="0b35f-129">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="0b35f-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="0b35f-130">결과: 성공</span><span class="sxs-lookup"><span data-stu-id="0b35f-130">Result : Success</span></span>

<span data-ttu-id="0b35f-131">대기 시간: 00:00:06.3981276</span><span class="sxs-lookup"><span data-stu-id="0b35f-131">Latency : 00:00:06.3981276</span></span>

<span data-ttu-id="0b35f-132">오류</span><span class="sxs-lookup"><span data-stu-id="0b35f-132">Error :</span></span>

<span data-ttu-id="0b35f-133">있게</span><span class="sxs-lookup"><span data-stu-id="0b35f-133">Diagnosis :</span></span>

<span data-ttu-id="0b35f-134">지정 된 사용자가 연결을 설정할 수 없는 경우 결과가 실패로 표시 되 고 오류 및 진단 속성에 추가 정보가 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b35f-134">If the specified user was not able to make a connection, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="0b35f-135">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="0b35f-135">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="0b35f-136">결과: 실패</span><span class="sxs-lookup"><span data-stu-id="0b35f-136">Result : Failure</span></span>

<span data-ttu-id="0b35f-137">대기 시간: 00:00:04.1993845</span><span class="sxs-lookup"><span data-stu-id="0b35f-137">Latency : 00:00:04.1993845</span></span>

<span data-ttu-id="0b35f-138">오류: 오류-웹 티켓 서비스에 대 한 응답을 받지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="0b35f-138">Error : ERROR - No response received for Web-Ticket service.</span></span>

<span data-ttu-id="0b35f-139">있게</span><span class="sxs-lookup"><span data-stu-id="0b35f-139">Diagnosis :</span></span>

<span data-ttu-id="0b35f-140">이전 출력에서는 웹 티켓 서비스가 응답 하지 않아 테스트가 실패 했다는 것을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b35f-140">The previous output states that the test failed because the Web Ticket service did not respond.</span></span> <span data-ttu-id="0b35f-141">이것은 서비스 자체의 문제 때문일 수도 있고, 테스트-CsPhoneBootstrap에 전달 된 SIP 주소, 전화 번호 또는 클라이언트 PIN으로 인해 발생할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b35f-141">This could be due to a problem with the service itself, or it might be due to the SIP address, phone number, or client PIN passed to Test-CsPhoneBootstrap.</span></span> <span data-ttu-id="0b35f-142">이 예와 유사한 명령을 사용 하 여 사용자의 SIP 주소 및 전화 번호를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b35f-142">You can verify the user’s SIP address and phone number by using a command similar to this one:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, LineUri

<span data-ttu-id="0b35f-143">그리고 다음과 같이 명령을 사용 하 여 사용자에 게 유효한 PIN이 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b35f-143">And you can verify that the user has a valid PIN by using a command as follows:</span></span>

    Get-CsClientPinInfo -Identity "sip:kenmyer@litwareinc.com" 

<span data-ttu-id="0b35f-144">테스트-CsPhoneBootstrap 실패 하는 경우 다음과 같이 Verbose 매개 변수를 포함 하 여 테스트를 다시 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b35f-144">If Test-CsPhoneBootstrap fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712" -Verbose

<span data-ttu-id="0b35f-145">Verbose 매개 변수가 포함 된 경우 테스트-CsPhoneBootstrap는 지정 된 사용자가 Lync Server에 로그온 하는 기능을 검사 한 경우 시도한 각 작업의 단계별 계정을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b35f-145">When the Verbose parameter is included, Test-CsPhoneBootstrap will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="0b35f-146">예를 들어 다음은 잘못 된 PIN이 포함 된 세션 인 실패 한 로그온에 대 한 출력의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="0b35f-146">For example, here is a portion of the output for an unsuccessful logon, a session in which an incorrect PIN was included:</span></span>

<span data-ttu-id="0b35f-147">휴대폰\\EXT와 pin 인증 사용: 12065551219 PIN: 0712</span><span class="sxs-lookup"><span data-stu-id="0b35f-147">Using PIN auth with Phone\\Ext : 12065551219 Pin : 0712</span></span>

<span data-ttu-id="0b35f-148">웹 티켓을 가져올 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0b35f-148">Could not get web ticket</span></span>

<span data-ttu-id="0b35f-149">검사가</span><span class="sxs-lookup"><span data-stu-id="0b35f-149">CHECK :</span></span>

<span data-ttu-id="0b35f-150">\-웹 서비스 url이 올바르며 웹 서비스가 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b35f-150">\- Web service url is valid and the web services are functional</span></span>

<span data-ttu-id="0b35f-151">\-PhoneNo\\PIN을 사용 하 여 인증 하는 경우 사용자 uri와 일치 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b35f-151">\- If using PhoneNo\\PIN to authenticate, make sure they match the user uri</span></span>

<span data-ttu-id="0b35f-152">\-NTLM\\Kerberos 인증을 사용 하는 경우 유효한 자격 증명을 제공 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b35f-152">\- If using NTLM\\Kerberos auth, make sure you provided valid credentials</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="0b35f-153">테스트가 실패할 수 있는 이유</span><span class="sxs-lookup"><span data-stu-id="0b35f-153">Reasons why the test might have failed</span></span>

<span data-ttu-id="0b35f-154">테스트 CsPhoneBootstrap가 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0b35f-154">Here are some common reasons why Test-CsPhoneBootstrap might fail:</span></span>

  - <span data-ttu-id="0b35f-155">유효 하지 않은 SIP 주소를 지정 했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b35f-155">You might have specified a SIP address that is not valid.</span></span> <span data-ttu-id="0b35f-156">다음과 같은 명령을 사용 하 여 SIP 주소가 올바른지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b35f-156">You can verify that a SIP address is correct by using a command such as this one:</span></span>
    
        Get-CsUser -Identity "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="0b35f-157">유효 하지 않은 PIN을 지정 했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b35f-157">You might have specified a PIN that is not valid.</span></span> <span data-ttu-id="0b35f-158">사용자의 PIN 번호를 검색할 수는 없지만 다음과 같은 명령을 사용 하 여 사용자에 게 PIN 번호가 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b35f-158">Although you can't retrieve the user’s PIN number, you can verify that the user at least has a PIN number by using a command similar to this:</span></span>
    
        Get-CsClientPinInfo -Identity "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="0b35f-159">유효 하지 않은 전화 번호를 지정 했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b35f-159">You might have specified a phone number that is not valid.</span></span> <span data-ttu-id="0b35f-160">다음과 같은 명령을 사용 하 여 사용자의 전화를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b35f-160">You can verify a user’s phone by using a command similar to the following:</span></span>
    
        Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object LineUri

  - <span data-ttu-id="0b35f-161">등록자 풀이 DHCP를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0b35f-161">The Registrar pool is not DHCP-enabled.</span></span> <span data-ttu-id="0b35f-162">등록자 풀이 DHCP에 대해 사용 하도록 설정 되어 있는지 확인 하려면 CsRegistrarConfiguration cmdlet을 실행 하 고 EnableDHCPServer 속성의 값을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b35f-162">To determine whether your Registrar pool is enabled for DHCP, run the Get-CsRegistrarConfiguration cmdlet and check the value of the EnableDHCPServer property.</span></span> <span data-ttu-id="0b35f-163">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0b35f-163">For example:</span></span>
    
        Get-CsRegistrarConfiguration -Identity "global"

</div>

</div>

<span> </span>

</div>

</div>

</div>

