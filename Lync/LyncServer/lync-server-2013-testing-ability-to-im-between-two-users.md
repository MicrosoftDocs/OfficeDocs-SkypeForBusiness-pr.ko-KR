---
title: 'Lync Server 2013: 두 사용자 간의 IM 기능 테스트'
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
ms.openlocfilehash: 201aceceadeba3c6c97530925273097fe039bc08
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745898"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-im-between-two-users-in-lync-server-2013"></a><span data-ttu-id="69aa2-102">Lync Server 2013에서 두 사용자 간의 IM 기능 테스트</span><span class="sxs-lookup"><span data-stu-id="69aa2-102">Testing ability to IM between two users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="69aa2-103">_**마지막으로 수정한 주제:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="69aa2-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="69aa2-104">확인 일정</span><span class="sxs-lookup"><span data-stu-id="69aa2-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="69aa2-105">Daily</span><span class="sxs-lookup"><span data-stu-id="69aa2-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69aa2-106">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="69aa2-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="69aa2-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="69aa2-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69aa2-108">권한이 필요 함</span><span class="sxs-lookup"><span data-stu-id="69aa2-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="69aa2-109">Lync Server Management Shell을 사용 하 여 로컬에서 실행 되는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="69aa2-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="69aa2-110">Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 사용자에 게 Test-CsIM cmdlet을 실행할 권한이 있는 RBAC 역할을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="69aa2-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsIM cmdlet.</span></span> <span data-ttu-id="69aa2-111">이 cmdlet을 사용할 수 있는 모든 RBAC 역할 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="69aa2-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="69aa2-112">설명</span><span class="sxs-lookup"><span data-stu-id="69aa2-112">Description</span></span>

<span data-ttu-id="69aa2-113">Test-CsIM cmdlet은 테스트 사용자 쌍이 인스턴트 메시지를 교환할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="69aa2-113">The Test-CsIM cmdlet verifies that a pair of test users can exchange instant messages.</span></span> <span data-ttu-id="69aa2-114">호출 되 면 Lync Server에 한 쌍의 테스트 사용자를 기록 하려고 하 여 Test-CsIM cmdlet이 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="69aa2-114">When called, the Test-CsIM cmdlet starts off by trying to log on a pair of test users to Lync Server.</span></span> <span data-ttu-id="69aa2-115">두 번의 로그온이 성공한 것으로 가정 하면 cmdlet은 두 테스트 사용자 간에 IM 세션을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="69aa2-115">Assuming the two logons are successful, the cmdlet then starts an IM session between the two test users.</span></span> <span data-ttu-id="69aa2-116">(사용자 1이 IM 세션에 2 사용자를 초대 하 고 사용자 2가 초대를 수락 합니다.) 두 사용자 간에 메시지를 교환할 수 있는지 확인 한 후에는 Test-CsIM이 IM 세션을 종료 하 고 두 사용자를 모두 시스템에서 로그 합니다.</span><span class="sxs-lookup"><span data-stu-id="69aa2-116">(User 1 invites User 2 to an IM session, and User 2 accepts the invitation.) After verifying that messages can be exchanged between the two users, Test-CsIM then ends the IM session and logs both users off the system.</span></span>

<span data-ttu-id="69aa2-117">자세한 내용은 [Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) cmdlet에 대 한 도움말 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="69aa2-117">For more information, see the Help documentation for the [Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="69aa2-118">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="69aa2-118">Running the Test</span></span>

<span data-ttu-id="69aa2-119">테스트 계정 (Lync Server 테스트 실행을 위한 테스트 계정 설정 참조) 또는 Lync Server에 대해 사용 하도록 설정 된 두 명의 사용자 계정 중 하나를 사용 하 여 Test-CsIM cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69aa2-119">The Test-CsIM cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="69aa2-120">테스트 계정을 사용 하 여이 검사를 실행 하려면 테스트 중인 Lync Server 풀의 FQDN만 지정 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="69aa2-120">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="69aa2-121">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="69aa2-121">For example:</span></span>

    Test-CsIM -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="69aa2-122">실제 사용자 계정을 사용 하 여이 검사를 실행 하려면 각 계정에 대해 두 개의 Windows PowerShell 자격 증명 개체 (계정 이름과 암호를 포함 하는 개체)를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="69aa2-122">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="69aa2-123">그런 다음 Test-CsIM을 호출할 때 다음과 같은 두 계정의 SIP 주소와 이러한 자격 증명 개체를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="69aa2-123">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsIM:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsIm -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="69aa2-124">자세한 내용은 [Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) cmdlet에 대 한 도움말 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="69aa2-124">For more information, see the Help documentation for the [Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="69aa2-125">성공 또는 실패 확인</span><span class="sxs-lookup"><span data-stu-id="69aa2-125">Determining Success or Failure</span></span>

<span data-ttu-id="69aa2-126">두 사용자가 인스턴트 메시지 세션을 완료할 수 있는 경우 다음과 유사한 출력을 받고 결과 속성이 성공으로 표시 됩니다 **.**</span><span class="sxs-lookup"><span data-stu-id="69aa2-126">If the two users can complete an instant messaging session, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="69aa2-127">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="69aa2-127">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="69aa2-128">결과: 성공</span><span class="sxs-lookup"><span data-stu-id="69aa2-128">Result : Success</span></span>

<span data-ttu-id="69aa2-129">대기 시간: 00:00:06.6630911</span><span class="sxs-lookup"><span data-stu-id="69aa2-129">Latency : 00:00:06.6630911</span></span>

<span data-ttu-id="69aa2-130">오류</span><span class="sxs-lookup"><span data-stu-id="69aa2-130">Error :</span></span>

<span data-ttu-id="69aa2-131">있게</span><span class="sxs-lookup"><span data-stu-id="69aa2-131">Diagnosis :</span></span>

<span data-ttu-id="69aa2-132">테스트 사용자가 세션을 완료할 수 없는 경우 결과가 실패로 표시 되 고 오류 및 진단 속성에 추가 정보가 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="69aa2-132">If the test users can't complete the session, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="69aa2-133">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="69aa2-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="69aa2-134">결과: 실패</span><span class="sxs-lookup"><span data-stu-id="69aa2-134">Result : Failure</span></span>

<span data-ttu-id="69aa2-135">대기 시간: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="69aa2-135">Latency : 00:00:00</span></span>

<span data-ttu-id="69aa2-136">오류: 504, 서버 시간 초과</span><span class="sxs-lookup"><span data-stu-id="69aa2-136">Error : 504, Server time-out</span></span>

<span data-ttu-id="69aa2-137">진단: ErrorCode = 2, 원본 = atl-cs-001. litwareinc, Reason = 참조</span><span class="sxs-lookup"><span data-stu-id="69aa2-137">Diagnosis : ErrorCode=2, Source=atl-cs-001.litwareinc.com,Reason=See</span></span>

<span data-ttu-id="69aa2-138">응답 코드 및 이유 구.</span><span class="sxs-lookup"><span data-stu-id="69aa2-138">response code and reason phrase.</span></span>

<span data-ttu-id="69aa2-139">Microsoft DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="69aa2-139">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="69aa2-140">예를 들어 이전 출력은 지정 된 사용자를 찾을 수 없기 때문에 테스트가 실패 했다는 것을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="69aa2-140">For example, the previous output states that the test failed because the specified user couldn't be found.</span></span> <span data-ttu-id="69aa2-141">이 명령을 실행 하 여 SIP 주소가 유효한 지 (그리고 SIP 주소를 사용 하도록 설정 된 사용자에 게 있는지 여부)를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69aa2-141">You can determine whether a SIP address is valid (and whether the user assigned that SIP address was enabled for Lync Server) by running this command:</span></span>

    Get-CsUser "Ken Myer" | Select-Object SipAddress, Enabled

<span data-ttu-id="69aa2-142">Test-CsIM이 실패 하는 경우 다음과 같이 Verbose 매개 변수를 포함 하 여 테스트를 다시 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69aa2-142">If Test-CsIM fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsIM -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="69aa2-143">Verbose 매개 변수가 포함 된 경우 테스트-CsIM은 두 테스트 사용자가 IM 세션에 참여 하는 기능을 검사할 때 시도한 각 작업의 단계별 계정을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="69aa2-143">When the Verbose parameter is included, Test-CsIM will return a step-by-step account of each action it tried when it checked the ability of the two test users to take part in an IM session.</span></span> <span data-ttu-id="69aa2-144">예를 들어 다음은 잘못 된 사용자 자격 증명 집합 (이 경우 잘못 된 암호)이 테스트-CsIM에 제공 될 때 발생 하는 예제 출력입니다.</span><span class="sxs-lookup"><span data-stu-id="69aa2-144">For example, here’s sample output that occurs when an incorrect set of user credentials (in this case, an incorrect password) is supplied to Test-CsIM:</span></span>

<span data-ttu-id="69aa2-145">등록 요청 전송 중:</span><span class="sxs-lookup"><span data-stu-id="69aa2-145">Sending Registration request :</span></span>

<span data-ttu-id="69aa2-146">대상 Fqdn = atl-cs-011.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="69aa2-146">Target Fqdn = atl-cs-011.litwareinc.com</span></span>

<span data-ttu-id="69aa2-147">사용자 Sip 주소 = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="69aa2-147">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="69aa2-148">등록자 포트 = 5061</span><span class="sxs-lookup"><span data-stu-id="69aa2-148">Registrar Port = 5061</span></span>

<span data-ttu-id="69aa2-149">' IWA ' 인증 유형이 선택 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="69aa2-149">Auth Type 'IWA' is selected.</span></span>

<span data-ttu-id="69aa2-150">Sip/atl에 대 한 등록 적중률-cs-001 litwareinc .com</span><span class="sxs-lookup"><span data-stu-id="69aa2-150">Registration hit against sip/atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="69aa2-151">' 등록 ' 활동이 완료 되었습니다 (' 0.0601795 ' 초).</span><span class="sxs-lookup"><span data-stu-id="69aa2-151">'Register' activity completed in '0.0601795' secs.</span></span>

<span data-ttu-id="69aa2-152">' 로그온이 거부 되었습니다. ' 라는 예외가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="69aa2-152">An exception 'The log on was denied.</span></span> <span data-ttu-id="69aa2-153">올바른 자격 증명을 사용 하 고 있으며 계정이 활성 상태 인지 확인 합니다. '</span><span class="sxs-lookup"><span data-stu-id="69aa2-153">Check that the correct credentials are being used and the account is active.'</span></span> <span data-ttu-id="69aa2-154">워크플로를 진행 하는 동안 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="69aa2-154">occurred during the Workflow.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="69aa2-155">테스트가 실패할 수 있는 이유</span><span class="sxs-lookup"><span data-stu-id="69aa2-155">Reasons Why the Test Might Have Failed</span></span>

<span data-ttu-id="69aa2-156">테스트-CsIM이 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="69aa2-156">Here are some common reasons why Test-CsIM might fail:</span></span>

  - <span data-ttu-id="69aa2-157">유효 하지 않은 사용자 계정을 지정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="69aa2-157">You specified a user account that is not valid.</span></span> <span data-ttu-id="69aa2-158">다음과 같은 명령을 실행 하 여 사용자 계정이 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69aa2-158">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="69aa2-159">사용자 계정이 올바르지만 현재 Lync Server에서 계정을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="69aa2-159">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="69aa2-160">Lync Server에 대해 사용자 계정이 설정 되어 있는지 확인 하려면 다음과 같은 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="69aa2-160">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="69aa2-161">Enabled 속성이 False로 설정 된 경우 사용자가 현재 Lync Server에 대해 사용 하도록 설정 되어 있지 않음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="69aa2-161">If the Enabled property is set to False that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="69aa2-162">메신저 서비스를 사용 하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69aa2-162">The instant messaging service might not be available.</span></span> <span data-ttu-id="69aa2-163">Lync Server를 사용 하 여 보관 데이터베이스에 액세스할 수 없는 경우 메신저를 사용할 수 없도록 시스템을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69aa2-163">With Lync Server, you can configure the system so that IM is not available if the archiving database cannot be accessed.</span></span> <span data-ttu-id="69aa2-164">다음과 같은 명령을 실행 하 여 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69aa2-164">You can verify that by running a command similar to the following:</span></span>
    
        Get-CsArchivingConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object BlockOnArchiveFailure
    
    <span data-ttu-id="69aa2-165">BlockOnArchiveFailure가 True로 설정 된 경우 보관 데이터베이스를 사용할 수 있는지 여부를 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="69aa2-165">If BlockOnArchiveFailure is set to True, then you should determine whether or not the archiving database is available.</span></span> <span data-ttu-id="69aa2-166">다음 명령을 사용 하 여 보관 데이터베이스의 위치를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69aa2-166">You can return the locations of your archiving databases by using the following command:</span></span>
    
        Get-CsService -ArchivingDatabase

  - <span data-ttu-id="69aa2-167">보관 서버를 사용할 수 없는 경우일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69aa2-167">The Archiving server might not be available.</span></span> <span data-ttu-id="69aa2-168">다음 명령을 사용 하 여 보관 서버의 FQDN을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69aa2-168">You can retrieve the FQDN of your Archiving servers by using this command:</span></span>
    
        Get-CsService -ArchivingServer
    
    <span data-ttu-id="69aa2-169">그런 다음 적절 한 서버에 ping을 사용 하 여 사용할 수 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69aa2-169">You can then ping the appropriate server to verify that it is available.</span></span> <span data-ttu-id="69aa2-170">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="69aa2-170">For example:</span></span>
    
        ping atl-archiving-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

