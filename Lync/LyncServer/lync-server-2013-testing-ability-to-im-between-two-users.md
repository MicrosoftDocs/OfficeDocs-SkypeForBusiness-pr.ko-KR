---
title: 'Lync Server 2013: 두 사용자 간의 IM 기능 테스트'
description: 'Lync Server 2013: 두 사용자 간의 IM 기능을 테스트 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to IM between two users
ms:assetid: a0f3f5c6-f115-4c3f-90ac-5fdc932b417e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743838(v=OCS.15)
ms:contentKeyID: 63969635
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1409cfb58ed435a66dcf61db56660ca760e16422
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560804"
---
# <a name="testing-ability-to-im-between-two-users-in-lync-server-2013"></a><span data-ttu-id="8bc1e-103">Lync Server 2013에서 두 사용자 간의 IM 기능 테스트</span><span class="sxs-lookup"><span data-stu-id="8bc1e-103">Testing ability to IM between two users in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8bc1e-104">_**마지막으로 수정 된 항목:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="8bc1e-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8bc1e-105">확인 일정</span><span class="sxs-lookup"><span data-stu-id="8bc1e-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="8bc1e-106">매일</span><span class="sxs-lookup"><span data-stu-id="8bc1e-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bc1e-107">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="8bc1e-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="8bc1e-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8bc1e-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bc1e-109">필요한 권한</span><span class="sxs-lookup"><span data-stu-id="8bc1e-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="8bc1e-110">Lync Server 관리 셸을 사용 하 여 로컬로 실행 하는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bc1e-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="8bc1e-111">Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 사용자에 게 Test-CsIM cmdlet을 실행 하는 권한이 있는 RBAC 역할을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bc1e-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsIM cmdlet.</span></span> <span data-ttu-id="8bc1e-112">이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bc1e-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="8bc1e-113">설명</span><span class="sxs-lookup"><span data-stu-id="8bc1e-113">Description</span></span>

<span data-ttu-id="8bc1e-114">Test-CsIM cmdlet은 테스트 사용자 쌍이 인스턴트 메시지를 교환할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bc1e-114">The Test-CsIM cmdlet verifies that a pair of test users can exchange instant messages.</span></span> <span data-ttu-id="8bc1e-115">호출 되 면 test users 쌍을 Lync Server에 로그온 하 여 Test-CsIM cmdlet이 시작 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8bc1e-115">When called, the Test-CsIM cmdlet starts off by trying to log on a pair of test users to Lync Server.</span></span> <span data-ttu-id="8bc1e-116">두 로그온이 성공 했다고 가정 하면 cmdlet은 두 테스트 사용자 간에 IM 세션을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bc1e-116">Assuming the two logons are successful, the cmdlet then starts an IM session between the two test users.</span></span> <span data-ttu-id="8bc1e-117">(사용자 1이 IM 세션에 2 사용자를 초대 하 고, 사용자 2가 초대를 수락 합니다.) 두 사용자 간에 메시지를 교환할 수 있는지 확인 한 후에 Test-CsIM는 IM 세션을 종료 하 고 시스템에서 두 사용자를 모두 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bc1e-117">(User 1 invites User 2 to an IM session, and User 2 accepts the invitation.) After verifying that messages can be exchanged between the two users, Test-CsIM then ends the IM session and logs both users off the system.</span></span>

<span data-ttu-id="8bc1e-118">자세한 내용은 [CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) cmdlet에 대 한 도움말 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8bc1e-118">For more information, see the Help documentation for the [Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="8bc1e-119">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="8bc1e-119">Running the Test</span></span>

<span data-ttu-id="8bc1e-120">Test-CsIM cmdlet은 미리 구성 된 테스트 계정 쌍 (Lync Server 테스트 실행을 위한 테스트 계정 설정 참조) 또는 Lync Server를 사용 하도록 설정 된 두 사용자의 계정 중 하나를 사용 하 여 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bc1e-120">The Test-CsIM cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="8bc1e-121">테스트 계정을 사용 하 여이 검사를 실행 하려면 테스트할 Lync Server 풀의 FQDN만 지정 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bc1e-121">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="8bc1e-122">예제:</span><span class="sxs-lookup"><span data-stu-id="8bc1e-122">For example:</span></span>

    Test-CsIM -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="8bc1e-123">실제 사용자 계정을 사용 하 여이 검사를 실행 하려면 각 계정에 대해 두 개의 Windows PowerShell 자격 증명 개체 (계정 이름과 암호가 포함 된 개체)를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bc1e-123">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="8bc1e-124">그런 다음 Test-CsIM을 호출할 때 이러한 자격 증명 개체와 두 계정의 SIP 주소를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bc1e-124">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsIM:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsIm -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="8bc1e-125">자세한 내용은 [CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) cmdlet에 대 한 도움말 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8bc1e-125">For more information, see the Help documentation for the [Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="8bc1e-126">성공 또는 실패 확인</span><span class="sxs-lookup"><span data-stu-id="8bc1e-126">Determining Success or Failure</span></span>

<span data-ttu-id="8bc1e-127">두 사용자가 인스턴트 메시징 세션을 완료할 수 있으면 결과 속성이 성공으로 표시 된 것과 비슷한 출력을 받게 됩니다 **.**</span><span class="sxs-lookup"><span data-stu-id="8bc1e-127">If the two users can complete an instant messaging session, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="8bc1e-128">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="8bc1e-128">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="8bc1e-129">결과: 성공</span><span class="sxs-lookup"><span data-stu-id="8bc1e-129">Result : Success</span></span>

<span data-ttu-id="8bc1e-130">대기 시간: 00:00:06.6630911</span><span class="sxs-lookup"><span data-stu-id="8bc1e-130">Latency : 00:00:06.6630911</span></span>

<span data-ttu-id="8bc1e-131">오류</span><span class="sxs-lookup"><span data-stu-id="8bc1e-131">Error :</span></span>

<span data-ttu-id="8bc1e-132">진단을</span><span class="sxs-lookup"><span data-stu-id="8bc1e-132">Diagnosis :</span></span>

<span data-ttu-id="8bc1e-133">테스트 사용자가 세션을 완료할 수 없으면 결과가 실패로 표시 되 고 오류 및 진단 속성에 추가 정보가 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bc1e-133">If the test users can't complete the session, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="8bc1e-134">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="8bc1e-134">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="8bc1e-135">결과: 실패</span><span class="sxs-lookup"><span data-stu-id="8bc1e-135">Result : Failure</span></span>

<span data-ttu-id="8bc1e-136">대기 시간: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="8bc1e-136">Latency : 00:00:00</span></span>

<span data-ttu-id="8bc1e-137">오류: 504, 서버 제한 시간</span><span class="sxs-lookup"><span data-stu-id="8bc1e-137">Error : 504, Server time-out</span></span>

<span data-ttu-id="8bc1e-138">진단: ErrorCode = 2, Source = atl-cs-litwareinc, Reason = 참고</span><span class="sxs-lookup"><span data-stu-id="8bc1e-138">Diagnosis : ErrorCode=2, Source=atl-cs-001.litwareinc.com,Reason=See</span></span>

<span data-ttu-id="8bc1e-139">응답 코드 및 이유 구입니다.</span><span class="sxs-lookup"><span data-stu-id="8bc1e-139">response code and reason phrase.</span></span>

<span data-ttu-id="8bc1e-140">Microsoft DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="8bc1e-140">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="8bc1e-141">예를 들어 위의 출력에서는 지정 된 사용자를 찾을 수 없기 때문에 테스트가 실패 했다는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8bc1e-141">For example, the previous output states that the test failed because the specified user couldn't be found.</span></span> <span data-ttu-id="8bc1e-142">다음 명령을 실행 하 여 SIP 주소가 유효한 지 여부와 해당 SIP 주소를 할당 한 사용자가 Lync Server를 사용 하도록 설정 되었는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bc1e-142">You can determine whether a SIP address is valid (and whether the user assigned that SIP address was enabled for Lync Server) by running this command:</span></span>

    Get-CsUser "Ken Myer" | Select-Object SipAddress, Enabled

<span data-ttu-id="8bc1e-143">Test-CsIM 실패 하면 다음 시간에 Verbose 매개 변수를 포함 하 여 테스트를 다시 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bc1e-143">If Test-CsIM fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsIM -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="8bc1e-144">Verbose 매개 변수를 포함 하면 Test-CsIM는 두 테스트 사용자가 IM 세션에 참가 하는 기능을 확인할 때 시도한 각 작업의 단계별 계정을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bc1e-144">When the Verbose parameter is included, Test-CsIM will return a step-by-step account of each action it tried when it checked the ability of the two test users to take part in an IM session.</span></span> <span data-ttu-id="8bc1e-145">예를 들어, 다음은 Test-CsIM에 잘못 된 사용자 자격 증명 집합 (이 경우 잘못 된 암호)을 제공 했을 때 발생 하는 예제 출력입니다.</span><span class="sxs-lookup"><span data-stu-id="8bc1e-145">For example, here’s sample output that occurs when an incorrect set of user credentials (in this case, an incorrect password) is supplied to Test-CsIM:</span></span>

<span data-ttu-id="8bc1e-146">등록 요청을 보내는 중:</span><span class="sxs-lookup"><span data-stu-id="8bc1e-146">Sending Registration request :</span></span>

<span data-ttu-id="8bc1e-147">대상 Fqdn = atl-cs-011.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="8bc1e-147">Target Fqdn = atl-cs-011.litwareinc.com</span></span>

<span data-ttu-id="8bc1e-148">사용자 Sip 주소 = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="8bc1e-148">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="8bc1e-149">등록자 포트 = 5061</span><span class="sxs-lookup"><span data-stu-id="8bc1e-149">Registrar Port = 5061</span></span>

<span data-ttu-id="8bc1e-150">인증 유형 ' IWA '이 선택 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bc1e-150">Auth Type 'IWA' is selected.</span></span>

<span data-ttu-id="8bc1e-151">Sip/atl-litwareinc에 대 한 등록 적중</span><span class="sxs-lookup"><span data-stu-id="8bc1e-151">Registration hit against sip/atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="8bc1e-152">' 등록 ' 활동이 완료 되었습니다 (' 0.0601795 ' 초).</span><span class="sxs-lookup"><span data-stu-id="8bc1e-152">'Register' activity completed in '0.0601795' secs.</span></span>

<span data-ttu-id="8bc1e-153">' 로그온이 거부 되었습니다. ' 라는 예외가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8bc1e-153">An exception 'The log on was denied.</span></span> <span data-ttu-id="8bc1e-154">올바른 자격 증명을 사용 하 고 있으며 계정이 활성 상태 인지 확인 합니다. '</span><span class="sxs-lookup"><span data-stu-id="8bc1e-154">Check that the correct credentials are being used and the account is active.'</span></span> <span data-ttu-id="8bc1e-155">워크플로 중에 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8bc1e-155">occurred during the Workflow.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="8bc1e-156">테스트가 실패 한 이유</span><span class="sxs-lookup"><span data-stu-id="8bc1e-156">Reasons Why the Test Might Have Failed</span></span>

<span data-ttu-id="8bc1e-157">Test-CsIM 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8bc1e-157">Here are some common reasons why Test-CsIM might fail:</span></span>

  - <span data-ttu-id="8bc1e-158">잘못 된 사용자 계정을 지정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8bc1e-158">You specified a user account that is not valid.</span></span> <span data-ttu-id="8bc1e-159">다음과 같은 명령을 실행 하 여 사용자 계정이 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bc1e-159">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="8bc1e-160">사용자 계정이 올바르지만 해당 계정이 Lync Server에 대해 현재 사용 하도록 설정 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8bc1e-160">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="8bc1e-161">사용자 계정이 Lync Server에 대해 사용 하도록 설정 되어 있는지 확인 하려면 다음과 같은 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bc1e-161">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="8bc1e-162">Enabled 속성을 False로 설정 하면 사용자가 현재 Lync Server를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8bc1e-162">If the Enabled property is set to False that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="8bc1e-163">인스턴트 메시징 서비스를 사용 하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bc1e-163">The instant messaging service might not be available.</span></span> <span data-ttu-id="8bc1e-164">Lync Server에서는 보관 데이터베이스에 액세스할 수 없는 경우 IM을 사용할 수 없도록 시스템을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bc1e-164">With Lync Server, you can configure the system so that IM is not available if the archiving database cannot be accessed.</span></span> <span data-ttu-id="8bc1e-165">다음과 같은 명령을 실행 하 여이를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bc1e-165">You can verify that by running a command similar to the following:</span></span>
    
        Get-CsArchivingConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object BlockOnArchiveFailure
    
    <span data-ttu-id="8bc1e-166">BlockOnArchiveFailure이 True로 설정 된 경우 보관 데이터베이스를 사용할 수 있는지 여부를 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bc1e-166">If BlockOnArchiveFailure is set to True, then you should determine whether or not the archiving database is available.</span></span> <span data-ttu-id="8bc1e-167">다음 명령을 사용 하 여 보관 데이터베이스의 위치를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bc1e-167">You can return the locations of your archiving databases by using the following command:</span></span>
    
        Get-CsService -ArchivingDatabase

  - <span data-ttu-id="8bc1e-168">보관 서버를 사용 하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bc1e-168">The Archiving server might not be available.</span></span> <span data-ttu-id="8bc1e-169">다음 명령을 사용 하 여 보관 서버의 FQDN을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bc1e-169">You can retrieve the FQDN of your Archiving servers by using this command:</span></span>
    
        Get-CsService -ArchivingServer
    
    <span data-ttu-id="8bc1e-170">그런 다음 적절 한 서버에 ping을 수행 하 여 해당 서버가 사용 가능한 지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bc1e-170">You can then ping the appropriate server to verify that it is available.</span></span> <span data-ttu-id="8bc1e-171">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8bc1e-171">For example:</span></span>
    
        ping atl-archiving-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

