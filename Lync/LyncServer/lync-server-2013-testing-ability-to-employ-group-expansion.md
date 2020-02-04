---
title: 'Lync Server 2013: 그룹 확장을 사용 하는 방법 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to employ group expansion
ms:assetid: 9b0fc954-6f9c-411a-ab32-94ebabc42de2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743836(v=OCS.15)
ms:contentKeyID: 63969634
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d79c5432bc2efca0d3a958d3837793eaf227b251
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745978"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-employ-group-expansion-in-lync-server-2013"></a><span data-ttu-id="73e13-102">Lync Server 2013에서 그룹 확장을 사용 하는 테스트 기능</span><span class="sxs-lookup"><span data-stu-id="73e13-102">Testing ability to employ group expansion in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="73e13-103">_**마지막으로 수정한 주제:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="73e13-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="73e13-104">확인 일정</span><span class="sxs-lookup"><span data-stu-id="73e13-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="73e13-105">Daily</span><span class="sxs-lookup"><span data-stu-id="73e13-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73e13-106">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="73e13-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="73e13-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="73e13-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73e13-108">권한이 필요 함</span><span class="sxs-lookup"><span data-stu-id="73e13-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="73e13-109">Lync Server Management Shell을 사용 하 여 로컬에서 실행 되는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73e13-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="73e13-110">Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 테스트-CsGroupExpansion cmdlet을 실행할 권한이 있는 RBAC 역할을 사용자에 게 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73e13-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsGroupExpansion cmdlet.</span></span> <span data-ttu-id="73e13-111">이 cmdlet을 사용할 수 있는 모든 RBAC 역할 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="73e13-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupExpansion&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="73e13-112">설명</span><span class="sxs-lookup"><span data-stu-id="73e13-112">Description</span></span>

<span data-ttu-id="73e13-113">테스트-CsGroupExpansion cmdlet을 사용 하 여 조직 내에서 그룹 확장이 작동 하는지 여부를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73e13-113">The Test-CsGroupExpansion cmdlet lets you determine whether group expansion is working within your organization.</span></span> <span data-ttu-id="73e13-114">그룹 확장을 사용 하도록 설정 하면 사용자가 메일 그룹을 연락처로 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="73e13-114">When group expansion is enabled, users configure distribution groups as a contact.</span></span> <span data-ttu-id="73e13-115">따라서 이러한 사용자는 해당 그룹의 개별 구성원 대신 그룹에 대 한 메시지를 처리 하 여 모든 그룹 구성원에 게 동일한 인스턴트 메시지를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73e13-115">That means that those users can then send the same instant message to all the group members by addressing the message to the group instead of to individual members of that group.</span></span> <span data-ttu-id="73e13-116">그룹 확장을 사용 하면 모든 그룹 구성원과 해당 사용자의 현재 상태를 빠르고 쉽게 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73e13-116">Group expansion enables you to quickly and easily view all the group members and their current status.</span></span>

<span data-ttu-id="73e13-117">테스트-CsGroupExpansion cmdlet을 사용 하 여 그룹의 전자 메일 주소를 사용 하 여 Active Directory 메일 그룹을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="73e13-117">With the Test-CsGroupExpansion cmdlet, you specify an Active Directory distribution group by using the group’s email address.</span></span> <span data-ttu-id="73e13-118">테스트-CsGroupExpansion은 그룹 확장을 사용 하 여 그룹 구성원을 검색 하 고 검색 된 목록을 제공 된 그룹 전자 메일 주소의 구성원으로 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="73e13-118">Test-CsGroupExpansion then uses group expansion to retrieve the group membership and compare the retrieved list to the membership of the group email address that you supplied.</span></span> <span data-ttu-id="73e13-119">두 목록이 일치 하는 경우 그룹 확장이 올바르게 작동 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="73e13-119">If the two lists match, then group expansion is working correctly.</span></span> <span data-ttu-id="73e13-120">서비스 자체를 테스트 하거나 연결 된 웹 서비스를 테스트 하 여 두 가지 방법으로 그룹 확장을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73e13-120">Note that you can test group expansion in two ways: by testing the service itself or by testing the associated web service.</span></span>

<span data-ttu-id="73e13-121">자세한 내용은 [테스트-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) cmdlet에 대 한 도움말 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="73e13-121">For more information, see the Help documentation for the [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="73e13-122">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="73e13-122">Running the test</span></span>

<span data-ttu-id="73e13-123">테스트-CsGroupExpansion cmdlet은 미리 구성 된 테스트 계정 (Lync Server 테스트 실행을 위한 테스트 계정 설정 참조) 또는 Lync Server에 대해 사용 하도록 설정 된 모든 사용자의 계정을 사용 하 여 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73e13-123">The Test-CsGroupExpansion cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who was enabled for Lync Server.</span></span> <span data-ttu-id="73e13-124">테스트 계정을 사용 하 여이 검사를 실행 하려면 테스트 중인 Lync Server 풀의 FQDN과 올바른 메일 그룹의 전자 메일 주소를 지정 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73e13-124">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested and the email address for a valid distribution group.</span></span> <span data-ttu-id="73e13-125">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="73e13-125">For example:</span></span>

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com"

<span data-ttu-id="73e13-126">실제 사용자 계정을 사용 하 여이 검사를 실행 하려면 먼저 계정 이름과 암호를 포함 하는 Lync Server 자격 증명 개체를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73e13-126">To run this check using an actual user account, you must first create a Lync Server credentials object that contains the account name and password.</span></span> <span data-ttu-id="73e13-127">그런 다음 시스템에서 테스트-CsGroupExpansion을 호출할 때 계정에 할당 된 해당 자격 증명 개체와 SIP 주소를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73e13-127">You must then include that credentials object and the SIP address assigned to the account when the system calls Test-CsGroupExpansion:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="73e13-128">자세한 내용은 [테스트-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) cmdlet에 대 한 도움말 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="73e13-128">For more information, see the Help documentation for the [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="73e13-129">성공 또는 실패 확인</span><span class="sxs-lookup"><span data-stu-id="73e13-129">Determining success or failure</span></span>

<span data-ttu-id="73e13-130">지정 된 사용자가 그룹 확장을 사용할 수 있는 경우 결과 속성이 성공으로 표시 된 것과 비슷한 출력을 받게 됩니다 **.**</span><span class="sxs-lookup"><span data-stu-id="73e13-130">If the specified user can use group expansion, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="73e13-131">TargetUri :https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="73e13-131">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="73e13-132">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="73e13-132">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="73e13-133">결과: 성공</span><span class="sxs-lookup"><span data-stu-id="73e13-133">Result : Success</span></span>

<span data-ttu-id="73e13-134">대기 시간: 00:00:01.1234976</span><span class="sxs-lookup"><span data-stu-id="73e13-134">Latency : 00:00:01.1234976</span></span>

<span data-ttu-id="73e13-135">오류</span><span class="sxs-lookup"><span data-stu-id="73e13-135">Error :</span></span>

<span data-ttu-id="73e13-136">있게</span><span class="sxs-lookup"><span data-stu-id="73e13-136">Diagnosis :</span></span>

<span data-ttu-id="73e13-137">지정 된 사용자가 그룹 확장을 사용할 수 없는 경우 결과가 실패로 표시 되 고 오류 및 진단 속성에 추가 정보가 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73e13-137">If the specified user can't use group expansion, then the Result will be shown as Failure and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="73e13-138">TargetUri :https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="73e13-138">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="73e13-139">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="73e13-139">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="73e13-140">결과: 실패</span><span class="sxs-lookup"><span data-stu-id="73e13-140">Result : Failure</span></span>

<span data-ttu-id="73e13-141">대기 시간: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="73e13-141">Latency : 00:00:00</span></span>

<span data-ttu-id="73e13-142">오류</span><span class="sxs-lookup"><span data-stu-id="73e13-142">Error :</span></span>

<span data-ttu-id="73e13-143">있게</span><span class="sxs-lookup"><span data-stu-id="73e13-143">Diagnosis :</span></span>

<span data-ttu-id="73e13-144">테스트-CsGroupExpansion: 끝점을 등록할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="73e13-144">Test-CsGroupExpansion : The endpoint was unable to register.</span></span> <span data-ttu-id="73e13-145">오류 코드는 특정 이유를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="73e13-145">See the ErrorCode for specific reason.</span></span>

<span data-ttu-id="73e13-146">이전 출력에서는 지정 된 사용자가 Lync Server에 등록할 수 없기 때문에 테스트가 실패 했다는 것을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="73e13-146">The previous output states that the test failed because the specified user was unable to register with Lync Server.</span></span> <span data-ttu-id="73e13-147">일반적으로이 문제는 테스트 계정이 없거나 Lync Server에 대해 사용 하도록 설정 되지 않은 경우 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="73e13-147">This will typically occur if the test account does not exist or has not enabled for Lync Server.</span></span> <span data-ttu-id="73e13-148">계정이 있는지 확인 하 고 다음 예와 비슷한 명령을 실행 하 여 해당 계정이 nm-ocs-14-3에 대해 사용 하도록 설정 되었는지 여부를 확인 하는 방법을 알아 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73e13-148">You can verify that the account exists, and determine whether or not the account has been enabled for nm-ocs-14-3rd by running a command similar to the following:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

<span data-ttu-id="73e13-149">테스트-CsGroupExpansion에 실패 하는 경우 자세한 정보 매개 변수를 포함 하 여 테스트를 다시 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73e13-149">If Test-CsGroupExpansion fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -Verbose

<span data-ttu-id="73e13-150">Verbose 매개 변수를 포함 하는 경우 테스트-CsGroupExpansion에서 지정 된 사용자가 Lync Server에 로그온 하는 기능을 검사 한 경우 시도한 각 작업의 단계별 계정을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="73e13-150">When the Verbose parameter is included Test-CsGroupExpansion will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="73e13-151">예를 들어 다음 출력은 지정 된 메일 그룹을 찾을 수 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="73e13-151">For example, this output indicates that the specified distribution group couldn't be found:</span></span>

<span data-ttu-id="73e13-152">웹 티켓을 가져오려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="73e13-152">Trying to get web ticket.</span></span>

<span data-ttu-id="73e13-153">웹 서비스 url:https://atl-cs-001.litwareinc.com:443/WebTicket/WebTicketService.svc</span><span class="sxs-lookup"><span data-stu-id="73e13-153">Web Service url : https://atl-cs-001.litwareinc.com:443/WebTicket/WebTicketService.svc</span></span>

<span data-ttu-id="73e13-154">NTLM/Kerb 인증을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="73e13-154">Using NTLM/Kerb auth.</span></span>

<span data-ttu-id="73e13-155">GetWebTicketActivity 완료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="73e13-155">GetWebTicketActivity completed.</span></span>

<span data-ttu-id="73e13-156">' VerifyDistributionList ' 활동이 시작 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="73e13-156">'VerifyDistributionList' activity started.</span></span>

<span data-ttu-id="73e13-157">DLX 웹 서비스 응답 상태가 NotFound입니다.</span><span class="sxs-lookup"><span data-stu-id="73e13-157">DLX Web Service Response Status is: NotFound.</span></span>

<span data-ttu-id="73e13-158">' VerifyDistributionList ' 활동이 ' 0.2597923 ' 초 후에 완료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="73e13-158">'VerifyDistributionList' activity completed in '0.2597923' secs.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="73e13-159">테스트가 실패할 수 있는 이유</span><span class="sxs-lookup"><span data-stu-id="73e13-159">Reasons why the test might have failed</span></span>

<span data-ttu-id="73e13-160">테스트-CsGroupExpansion 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="73e13-160">Here are some common reasons why Test-CsGroupExpansion might fail:</span></span>

  - <span data-ttu-id="73e13-161">잘못 된 사용자 계정을 지정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="73e13-161">You specified an invalid user account.</span></span> <span data-ttu-id="73e13-162">다음과 같은 명령을 실행 하 여 사용자 계정이 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73e13-162">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="73e13-163">사용자 계정이 올바르지만 현재 Lync Server에서 계정을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="73e13-163">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="73e13-164">사용자 계정이 Lync Server에 대해 사용 하도록 설정 되어 있는지 확인 하려면 다음과 같은 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="73e13-164">To verify that a user account was enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="73e13-165">Enabled 속성이 False로 설정 된 경우 사용자가 현재 Lync Server에 대해 사용 하도록 설정 되어 있지 않음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="73e13-165">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="73e13-166">그룹 확장을 사용 하지 않도록 설정 했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73e13-166">Group expansion might be disabled.</span></span> <span data-ttu-id="73e13-167">그룹 확장을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73e13-167">It is possible to turn off group expansion.</span></span> <span data-ttu-id="73e13-168">그룹 확장을 사용 하지 않도록 설정한 경우 테스트-CsGroupExpansion cmdlet이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="73e13-168">If group expansion was disabled then the Test-CsGroupExpansion cmdlet will fail.</span></span> <span data-ttu-id="73e13-169">그룹 확장을 사용할 수 있는지 여부를 확인 하려면 다음과 같은 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="73e13-169">To determine whether group expansion is enabled, use a command similar to this:</span></span>
    
        Get-CsWebServiceConfiguration | Select-Object Identity, EnableGroupExpansion

</div>

</div>

<span> </span>

</div>

</div>

</div>

