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
ms.openlocfilehash: 2d83d3c3fe933a4538d9c2508668497af42c3340
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046591"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-dial-in-conferencing-session-in-lync-server-2013"></a><span data-ttu-id="90fc9-102">Lync Server 2013에서 전화 접속 회의 세션 테스트</span><span class="sxs-lookup"><span data-stu-id="90fc9-102">Testing dial-in conferencing session in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="90fc9-103">_**마지막으로 수정 된 항목:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="90fc9-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="90fc9-104">확인 일정</span><span class="sxs-lookup"><span data-stu-id="90fc9-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="90fc9-105">매일</span><span class="sxs-lookup"><span data-stu-id="90fc9-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90fc9-106">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="90fc9-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="90fc9-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="90fc9-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="90fc9-108">필요한 권한</span><span class="sxs-lookup"><span data-stu-id="90fc9-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="90fc9-109">Lync Server 관리 셸을 사용 하 여 로컬로 실행 하는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="90fc9-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="90fc9-110">Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 Test-csdialinconferencing cmdlet을 실행 하는 권한이 있는 RBAC 역할을 사용자에 게 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="90fc9-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsDialInConferencing cmdlet.</span></span> <span data-ttu-id="90fc9-111">이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="90fc9-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDialInConferencing&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="90fc9-112">설명</span><span class="sxs-lookup"><span data-stu-id="90fc9-112">Description</span></span>

<span data-ttu-id="90fc9-113">Test-csdialinconferencing cmdlet은 사용자가 전화 접속 회의에 참가할 수 있는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="90fc9-113">The Test-CsDialInConferencing cmdlet verifies whether a user can participate in a dial-in conference.</span></span> <span data-ttu-id="90fc9-114">테스트 사용자를 시스템에 로그온 하 여 Test-csdialinconferencing 작동을 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="90fc9-114">Test-CsDialInConferencing works by trying to log a test user onto the system.</span></span> <span data-ttu-id="90fc9-115">로그온에 성공 하면 cmdlet은 사용자의 자격 증명과 사용 권한을 사용 하 여 사용 가능한 모든 전화 접속 회의 액세스 번호를 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="90fc9-115">If the logon succeeds, the cmdlet will then use the user’s credentials and permissions to try all of the available dial-in conferencing access numbers.</span></span> <span data-ttu-id="90fc9-116">각 전화 접속 시도의 성공 또는 실패에 대 한 설명이 표시 되 면 테스트 사용자는 Lync Server에서 로그 오프 됩니다. Test-csdialinconferencing 에서만 적절 한 연결을 설정할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="90fc9-116">The success or failure of each dial-in try will be noted, then the test user will be logged off from Lync Server.Test-CsDialInConferencing only verifies that the appropriate connections can be made.</span></span> <span data-ttu-id="90fc9-117">이 cmdlet은 실제로 전화 통화를 수행 하거나 다른 사용자가 참가할 수 있는 전화 접속 회의를 만들지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="90fc9-117">The cmdlet does not actually make any phone calls or create any dial-in conferences that other users can join.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="90fc9-118">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="90fc9-118">Running the test</span></span>

<span data-ttu-id="90fc9-119">Test-csdialinconferencing cmdlet은 미리 구성 된 테스트 계정 (Lync Server 테스트 실행을 위한 테스트 계정 설정 참조) 또는 Lync Server를 사용 하도록 설정 된 사용자의 계정 중 하나를 사용 하 여 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90fc9-119">The Test-CsDialInConferencing cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="90fc9-120">테스트 계정을 사용 하 여이 검사를 실행 하려면 테스트할 Lync Server 풀의 FQDN만 지정 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="90fc9-120">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="90fc9-121">예시는 다음과 같습니다:</span><span class="sxs-lookup"><span data-stu-id="90fc9-121">For example:</span></span>

    Test-CsDialInConferencing -TargetFqdn "atl-cs-001.litwareinc.com" 

<span data-ttu-id="90fc9-122">실제 사용자 계정을 사용 하 여이 검사를 실행 하려면 계정 이름과 암호가 포함 된 Windows PowerShell 자격 증명 개체를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="90fc9-122">To run this check using an actual user account, you must create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="90fc9-123">그런 다음 해당 자격 증명 개체와 계정 SIP 주소를 호출 하는 테스트-Test-csdialinconferencing을 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="90fc9-123">You must then include that credentials object and the account SIP address the calling Test-CsDialInConferencing:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsDialInConferencing -TargetFqdn atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="90fc9-124">자세한 내용은 [test-csdialinconferencing](https://docs.microsoft.com/powershell/module/skype/Test-CsDialInConferencing) cmdlet에 대 한 도움말 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="90fc9-124">For more information, see the Help documentation for the [Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/Test-CsDialInConferencing) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="90fc9-125">성공 또는 실패 확인</span><span class="sxs-lookup"><span data-stu-id="90fc9-125">Determining success or failure</span></span>

<span data-ttu-id="90fc9-126">지정 된 사용자가 Lync Server에 로그온 하 고 사용 가능한 전화 접속 회의 액세스 번호 중 하나를 사용 하 여 연결을 설정할 수 있는 경우 다음과 비슷한 출력을 받게 되며 Result 속성이 Success로 표시 됩니다 **.**</span><span class="sxs-lookup"><span data-stu-id="90fc9-126">If the specified user can log on to Lync Server and then make a connection using one of the available dial-in conferencing access numbers, then you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="90fc9-127">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="90fc9-127">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="90fc9-128">결과: 성공</span><span class="sxs-lookup"><span data-stu-id="90fc9-128">Result : Success</span></span>

<span data-ttu-id="90fc9-129">대기 시간: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="90fc9-129">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="90fc9-130">오류</span><span class="sxs-lookup"><span data-stu-id="90fc9-130">Error :</span></span>

<span data-ttu-id="90fc9-131">진단을</span><span class="sxs-lookup"><span data-stu-id="90fc9-131">Diagnosis :</span></span>

<span data-ttu-id="90fc9-132">지정 된 사용자가이 연결을 설정할 수 없으면 결과가 실패로 표시 되 고 오류 및 진단 속성에 추가 정보가 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="90fc9-132">If the specified user can't make this connection, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="90fc9-133">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="90fc9-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="90fc9-134">결과: 실패</span><span class="sxs-lookup"><span data-stu-id="90fc9-134">Result : Failure</span></span>

<span data-ttu-id="90fc9-135">대기 시간: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="90fc9-135">Latency : 00:00:00</span></span>

<span data-ttu-id="90fc9-136">오류: 로그온이 거부 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="90fc9-136">Error : The log on was denied.</span></span> <span data-ttu-id="90fc9-137">적절 한 자격 증명이 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="90fc9-137">Check that the proper credentials are</span></span>

<span data-ttu-id="90fc9-138">사용 중 이며 계정이 활성 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="90fc9-138">being used and the account is active.</span></span>

<span data-ttu-id="90fc9-139">내부 예외: NegotiateSecurityAssociation 실패, 오류:-</span><span class="sxs-lookup"><span data-stu-id="90fc9-139">Inner Exception:NegotiateSecurityAssociation failed, error: -</span></span>

<span data-ttu-id="90fc9-140">2146893044</span><span class="sxs-lookup"><span data-stu-id="90fc9-140">2146893044</span></span>

<span data-ttu-id="90fc9-141">진단을</span><span class="sxs-lookup"><span data-stu-id="90fc9-141">Diagnosis :</span></span>

<span data-ttu-id="90fc9-142">이전 출력은 테스트 사용자에 게 Lync Server 자체에 대 한 액세스가 거부 되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="90fc9-142">The previous output indicates that the test user was denied access to Lync Server itself.</span></span> <span data-ttu-id="90fc9-143">이는 일반적으로 Test-csdialinconferencing에 전달 된 사용자 자격 증명이 유효 하지 않음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="90fc9-143">This typically means that the user credentials passed to Test-CsDialInConferencing were not valid.</span></span> <span data-ttu-id="90fc9-144">그러면 Windows PowerShell 자격 증명 개체를 다시 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="90fc9-144">In turn, you should re-create the Windows PowerShell credentials object.</span></span> <span data-ttu-id="90fc9-145">사용자 계정에 대 한 암호를 검색할 수는 있지만 다음과 같은 명령을 사용 하 여 SIP 주소를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90fc9-145">Although you can retrieve the password for the user account, you can verify the SIP address by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="90fc9-146">테스트가 실패 한 이유</span><span class="sxs-lookup"><span data-stu-id="90fc9-146">Reasons why the test might have failed</span></span>

<span data-ttu-id="90fc9-147">다음은 Test-csdialinconferencing에서 오류가 발생할 수 있는 몇 가지 일반적인 이유입니다.</span><span class="sxs-lookup"><span data-stu-id="90fc9-147">Here are some common reasons why Test-CsDialInConferencing might fail:</span></span>

  - <span data-ttu-id="90fc9-148">잘못 된 사용자 계정을 지정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="90fc9-148">You specified a user account that is not valid.</span></span> <span data-ttu-id="90fc9-149">다음과 같은 명령을 실행 하 여 사용자 계정이 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90fc9-149">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="90fc9-150">사용자 계정이 올바르지만 해당 계정이 Lync Server에 대해 현재 사용 하도록 설정 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="90fc9-150">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="90fc9-151">사용자 계정이 Lync Server에 대해 사용 하도록 설정 되어 있는지 확인 하려면 다음과 같은 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="90fc9-151">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="90fc9-152">Enabled 속성을 False로 설정 하면 사용자가 현재 Lync Server를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="90fc9-152">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="90fc9-153">전화 접속 회의 액세스 번호가 잘못 되었을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90fc9-153">You might have an incorrect dial-in conferencing access number.</span></span> <span data-ttu-id="90fc9-154">다음 명령을 사용 하 여 현재 구성 된 전화 접속 회의 액세스 번호 목록을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90fc9-154">You can return your currently-configured list of dial-in conferencing access numbers by using this command:</span></span>
    
        Get-CsDialConferencingAccessNumber

</div>

</div>

<span> </span>

</div>

</div>

</div>

