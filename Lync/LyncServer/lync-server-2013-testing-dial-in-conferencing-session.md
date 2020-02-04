---
title: 'Lync Server 2013: 전화 접속 회의 세션 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing dial-in conferencing session
ms:assetid: 6c505be5-5af7-450c-b3ca-10d9122bee5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743834(v=OCS.15)
ms:contentKeyID: 63969613
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1afb4ee2e1a500b08c3481f71994f585298bc8c2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745838"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-dial-in-conferencing-session-in-lync-server-2013"></a><span data-ttu-id="20d7d-102">Lync Server 2013에서 전화 접속 회의 세션 테스트</span><span class="sxs-lookup"><span data-stu-id="20d7d-102">Testing dial-in conferencing session in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="20d7d-103">_**마지막으로 수정한 주제:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="20d7d-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="20d7d-104">확인 일정</span><span class="sxs-lookup"><span data-stu-id="20d7d-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="20d7d-105">Daily</span><span class="sxs-lookup"><span data-stu-id="20d7d-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20d7d-106">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="20d7d-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="20d7d-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="20d7d-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20d7d-108">권한이 필요 함</span><span class="sxs-lookup"><span data-stu-id="20d7d-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="20d7d-109">Lync Server Management Shell을 사용 하 여 로컬에서 실행 되는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="20d7d-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="20d7d-110">Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 CsDialInConferencing cmdlet을 실행 하는 데 필요한 권한이 있는 RBAC 역할을 사용자에 게 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="20d7d-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsDialInConferencing cmdlet.</span></span> <span data-ttu-id="20d7d-111">이 cmdlet을 사용할 수 있는 모든 RBAC 역할 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="20d7d-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDialInConferencing&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="20d7d-112">설명</span><span class="sxs-lookup"><span data-stu-id="20d7d-112">Description</span></span>

<span data-ttu-id="20d7d-113">테스트 CsDialInConferencing cmdlet은 사용자가 전화 접속 회의에 참가할 수 있는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="20d7d-113">The Test-CsDialInConferencing cmdlet verifies whether a user can participate in a dial-in conference.</span></span> <span data-ttu-id="20d7d-114">테스트 사용자는 시스템에 로그인 하 여 CsDialInConferencing 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="20d7d-114">Test-CsDialInConferencing works by trying to log a test user onto the system.</span></span> <span data-ttu-id="20d7d-115">로그온에 성공 하면 cmdlet은 사용자의 자격 증명과 사용 권한을 사용 하 여 사용 가능한 모든 전화 접속 회의 액세스 번호를 사용해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="20d7d-115">If the logon succeeds, the cmdlet will then use the user’s credentials and permissions to try all of the available dial-in conferencing access numbers.</span></span> <span data-ttu-id="20d7d-116">각 전화 접속 시도의 성공 또는 실패에 대 한 설명이 표시 되 면 테스트 사용자는 Lync Server에서 로그 오프 됩니다. CsDialInConferencing는 적절 한 연결을 설정할 수 있는지만 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="20d7d-116">The success or failure of each dial-in try will be noted, then the test user will be logged off from Lync Server.Test-CsDialInConferencing only verifies that the appropriate connections can be made.</span></span> <span data-ttu-id="20d7d-117">Cmdlet은 실제로 전화를 걸거나 다른 사용자가 참가할 수 있는 전화 접속 회의를 만들지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="20d7d-117">The cmdlet does not actually make any phone calls or create any dial-in conferences that other users can join.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="20d7d-118">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="20d7d-118">Running the test</span></span>

<span data-ttu-id="20d7d-119">테스트 CsDialInConferencing cmdlet은 미리 구성 된 테스트 계정 (Lync Server 테스트 실행을 위한 테스트 계정 설정 참조) 또는 Lync Server에 대해 사용 하도록 설정 된 모든 사용자의 계정을 사용 하 여 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20d7d-119">The Test-CsDialInConferencing cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="20d7d-120">테스트 계정을 사용 하 여이 검사를 실행 하려면 테스트 중인 Lync Server 풀의 FQDN만 지정 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="20d7d-120">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="20d7d-121">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="20d7d-121">For example:</span></span>

    Test-CsDialInConferencing -TargetFqdn "atl-cs-001.litwareinc.com" 

<span data-ttu-id="20d7d-122">실제 사용자 계정을 사용 하 여이 검사를 실행 하려면 계정 이름과 암호를 포함 하는 Windows PowerShell 자격 증명 개체를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="20d7d-122">To run this check using an actual user account, you must create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="20d7d-123">그런 다음 해당 자격 증명 개체를 포함 하 고 계정 SIP는 호출 테스트-CsDialInConferencing에 대해 다음을 처리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="20d7d-123">You must then include that credentials object and the account SIP address the calling Test-CsDialInConferencing:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsDialInConferencing -TargetFqdn atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="20d7d-124">자세한 내용은 [테스트 CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/Test-CsDialInConferencing) cmdlet에 대 한 도움말 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="20d7d-124">For more information, see the Help documentation for the [Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/Test-CsDialInConferencing) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="20d7d-125">성공 또는 실패 확인</span><span class="sxs-lookup"><span data-stu-id="20d7d-125">Determining success or failure</span></span>

<span data-ttu-id="20d7d-126">지정 된 사용자가 Lync Server에 로그온 한 다음 사용 가능한 전화 접속 회의 액세스 번호 중 하나를 사용 하 여 연결할 수 있는 경우 다음과 유사한 출력을 받고 결과 속성이 성공으로 표시 됩니다 **.**</span><span class="sxs-lookup"><span data-stu-id="20d7d-126">If the specified user can log on to Lync Server and then make a connection using one of the available dial-in conferencing access numbers, then you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="20d7d-127">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="20d7d-127">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="20d7d-128">결과: 성공</span><span class="sxs-lookup"><span data-stu-id="20d7d-128">Result : Success</span></span>

<span data-ttu-id="20d7d-129">대기 시간: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="20d7d-129">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="20d7d-130">오류</span><span class="sxs-lookup"><span data-stu-id="20d7d-130">Error :</span></span>

<span data-ttu-id="20d7d-131">있게</span><span class="sxs-lookup"><span data-stu-id="20d7d-131">Diagnosis :</span></span>

<span data-ttu-id="20d7d-132">지정 된 사용자가이 연결을 설정할 수 없는 경우에는 결과가 실패로 표시 되 고 다음과 같은 오류 및 진단 속성에 추가 정보가 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="20d7d-132">If the specified user can't make this connection, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="20d7d-133">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="20d7d-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="20d7d-134">결과: 실패</span><span class="sxs-lookup"><span data-stu-id="20d7d-134">Result : Failure</span></span>

<span data-ttu-id="20d7d-135">대기 시간: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="20d7d-135">Latency : 00:00:00</span></span>

<span data-ttu-id="20d7d-136">오류: 로그온이 거부 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="20d7d-136">Error : The log on was denied.</span></span> <span data-ttu-id="20d7d-137">적절 한 자격 증명이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="20d7d-137">Check that the proper credentials are</span></span>

<span data-ttu-id="20d7d-138">사용 중이 고 계정이 활성 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="20d7d-138">being used and the account is active.</span></span>

<span data-ttu-id="20d7d-139">내부 예외: NegotiateSecurityAssociation 실패, 오류:-</span><span class="sxs-lookup"><span data-stu-id="20d7d-139">Inner Exception:NegotiateSecurityAssociation failed, error: -</span></span>

<span data-ttu-id="20d7d-140">2146893044</span><span class="sxs-lookup"><span data-stu-id="20d7d-140">2146893044</span></span>

<span data-ttu-id="20d7d-141">있게</span><span class="sxs-lookup"><span data-stu-id="20d7d-141">Diagnosis :</span></span>

<span data-ttu-id="20d7d-142">이전 출력은 테스트 사용자에 게 Lync Server 자체에 대 한 액세스가 거부 되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="20d7d-142">The previous output indicates that the test user was denied access to Lync Server itself.</span></span> <span data-ttu-id="20d7d-143">이는 일반적으로 Test-CsDialInConferencing에 전달 된 사용자 자격 증명이 유효 하지 않음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="20d7d-143">This typically means that the user credentials passed to Test-CsDialInConferencing were not valid.</span></span> <span data-ttu-id="20d7d-144">그런 다음 Windows PowerShell 자격 증명 개체를 다시 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="20d7d-144">In turn, you should re-create the Windows PowerShell credentials object.</span></span> <span data-ttu-id="20d7d-145">사용자 계정에 대 한 암호를 검색할 수 있지만 다음과 같은 명령을 사용 하 여 SIP 주소를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20d7d-145">Although you can retrieve the password for the user account, you can verify the SIP address by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="20d7d-146">테스트가 실패할 수 있는 이유</span><span class="sxs-lookup"><span data-stu-id="20d7d-146">Reasons why the test might have failed</span></span>

<span data-ttu-id="20d7d-147">테스트 CsDialInConferencing가 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="20d7d-147">Here are some common reasons why Test-CsDialInConferencing might fail:</span></span>

  - <span data-ttu-id="20d7d-148">유효 하지 않은 사용자 계정을 지정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="20d7d-148">You specified a user account that is not valid.</span></span> <span data-ttu-id="20d7d-149">다음과 같은 명령을 실행 하 여 사용자 계정이 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20d7d-149">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="20d7d-150">사용자 계정이 올바르지만 현재 Lync Server에서 계정을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="20d7d-150">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="20d7d-151">Lync Server에 대해 사용자 계정이 설정 되어 있는지 확인 하려면 다음과 같은 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="20d7d-151">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="20d7d-152">Enabled 속성이 False로 설정 된 경우 사용자가 현재 Lync Server에 대해 사용 하도록 설정 되어 있지 않음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="20d7d-152">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="20d7d-153">전화 접속 회의 액세스 번호가 올바르지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20d7d-153">You might have an incorrect dial-in conferencing access number.</span></span> <span data-ttu-id="20d7d-154">다음 명령을 사용 하 여 현재 구성 된 전화 접속 회의 액세스 번호 목록을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20d7d-154">You can return your currently-configured list of dial-in conferencing access numbers by using this command:</span></span>
    
        Get-CsDialConferencingAccessNumber

</div>

</div>

<span> </span>

</div>

</div>

</div>

