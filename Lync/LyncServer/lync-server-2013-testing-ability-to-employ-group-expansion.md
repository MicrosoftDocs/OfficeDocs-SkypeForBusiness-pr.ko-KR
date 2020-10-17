---
title: 'Lync Server 2013: 그룹 확장을 사용 하는 기능 테스트'
description: 'Lync Server 2013: 그룹 확장을 사용 하는 기능을 테스트 합니다.'
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
ms.openlocfilehash: 6267bc2099fc420c5c57e1ef80f4bf4491334938
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560794"
---
# <a name="testing-ability-to-employ-group-expansion-in-lync-server-2013"></a><span data-ttu-id="210ef-103">Lync Server 2013에서 그룹 확장을 사용 하는 기능 테스트</span><span class="sxs-lookup"><span data-stu-id="210ef-103">Testing ability to employ group expansion in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="210ef-104">_**마지막으로 수정 된 항목:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="210ef-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="210ef-105">확인 일정</span><span class="sxs-lookup"><span data-stu-id="210ef-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="210ef-106">매일</span><span class="sxs-lookup"><span data-stu-id="210ef-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="210ef-107">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="210ef-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="210ef-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="210ef-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="210ef-109">필요한 권한</span><span class="sxs-lookup"><span data-stu-id="210ef-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="210ef-110">Lync Server 관리 셸을 사용 하 여 로컬로 실행 하는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="210ef-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="210ef-111">Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 사용자에 게 Test-CsGroupExpansion cmdlet을 실행 하는 권한이 있는 RBAC 역할을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="210ef-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsGroupExpansion cmdlet.</span></span> <span data-ttu-id="210ef-112">이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="210ef-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupExpansion&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="210ef-113">설명</span><span class="sxs-lookup"><span data-stu-id="210ef-113">Description</span></span>

<span data-ttu-id="210ef-114">Test-CsGroupExpansion cmdlet을 사용 하면 조직 내에서 그룹 확장이 작동 하는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="210ef-114">The Test-CsGroupExpansion cmdlet lets you determine whether group expansion is working within your organization.</span></span> <span data-ttu-id="210ef-115">그룹 확장을 사용 하도록 설정 하면 사용자는 메일 그룹을 연락처로 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="210ef-115">When group expansion is enabled, users configure distribution groups as a contact.</span></span> <span data-ttu-id="210ef-116">따라서 이러한 사용자는 해당 그룹의 개별 구성원이 아니라 그룹에 대 한 메시지의 주소를 지정 하 여 모든 그룹 구성원에 게 동일한 인스턴트 메시지를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="210ef-116">That means that those users can then send the same instant message to all the group members by addressing the message to the group instead of to individual members of that group.</span></span> <span data-ttu-id="210ef-117">그룹 확장을 사용하면 모든 그룹 구성원과 이들의 현재 상태를 빠르고 쉽게 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="210ef-117">Group expansion enables you to quickly and easily view all the group members and their current status.</span></span>

<span data-ttu-id="210ef-118">Test-CsGroupExpansion cmdlet에서는 그룹의 전자 메일 주소를 사용 하 여 Active Directory 메일 그룹을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="210ef-118">With the Test-CsGroupExpansion cmdlet, you specify an Active Directory distribution group by using the group’s email address.</span></span> <span data-ttu-id="210ef-119">그런 다음 그룹 확장을 사용 하 여 그룹 구성원을 검색 하 고 검색 된 목록을 제공 된 그룹 전자 메일 주소의 구성원으로 비교 Test-CsGroupExpansion 합니다.</span><span class="sxs-lookup"><span data-stu-id="210ef-119">Test-CsGroupExpansion then uses group expansion to retrieve the group membership and compare the retrieved list to the membership of the group email address that you supplied.</span></span> <span data-ttu-id="210ef-120">두 목록이 일치하면 그룹 확장이 제대로 작동하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="210ef-120">If the two lists match, then group expansion is working correctly.</span></span> <span data-ttu-id="210ef-121">서비스 자체를 테스트 하거나 연결 된 웹 서비스를 테스트 하 여 두 가지 방법으로 그룹 확장을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="210ef-121">Note that you can test group expansion in two ways: by testing the service itself or by testing the associated web service.</span></span>

<span data-ttu-id="210ef-122">자세한 내용은 [테스트-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) cmdlet에 대 한 도움말 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="210ef-122">For more information, see the Help documentation for the [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="210ef-123">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="210ef-123">Running the test</span></span>

<span data-ttu-id="210ef-124">Test-CsGroupExpansion cmdlet은 미리 구성 된 테스트 계정 (Lync Server 테스트 실행을 위한 테스트 계정 설정 참조) 또는 Lync Server를 사용 하도록 설정 된 사용자의 계정 중 하나를 사용 하 여 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="210ef-124">The Test-CsGroupExpansion cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who was enabled for Lync Server.</span></span> <span data-ttu-id="210ef-125">테스트 계정을 사용 하 여이 검사를 실행 하려면 테스트할 Lync Server 풀의 FQDN과 유효한 메일 그룹의 전자 메일 주소를 지정 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="210ef-125">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested and the email address for a valid distribution group.</span></span> <span data-ttu-id="210ef-126">예제:</span><span class="sxs-lookup"><span data-stu-id="210ef-126">For example:</span></span>

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com"

<span data-ttu-id="210ef-127">실제 사용자 계정을 사용 하 여이 검사를 실행 하려면 먼저 계정 이름과 암호가 포함 된 Lync Server credentials 개체를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="210ef-127">To run this check using an actual user account, you must first create a Lync Server credentials object that contains the account name and password.</span></span> <span data-ttu-id="210ef-128">그런 다음 시스템에서 테스트-CsGroupExpansion을 호출할 때 해당 계정에 할당 된 자격 증명 개체 및 SIP 주소를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="210ef-128">You must then include that credentials object and the SIP address assigned to the account when the system calls Test-CsGroupExpansion:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="210ef-129">자세한 내용은 [테스트-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) cmdlet에 대 한 도움말 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="210ef-129">For more information, see the Help documentation for the [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="210ef-130">성공 또는 실패 확인</span><span class="sxs-lookup"><span data-stu-id="210ef-130">Determining success or failure</span></span>

<span data-ttu-id="210ef-131">지정 된 사용자가 그룹 확장을 사용할 수 있는 경우 Result 속성이 Success로 표시 된 것과 비슷한 출력을 받게 됩니다 **.**</span><span class="sxs-lookup"><span data-stu-id="210ef-131">If the specified user can use group expansion, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="210ef-132">TargetUri https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="210ef-132">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="210ef-133">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="210ef-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="210ef-134">결과: 성공</span><span class="sxs-lookup"><span data-stu-id="210ef-134">Result : Success</span></span>

<span data-ttu-id="210ef-135">대기 시간: 00:00:01.1234976</span><span class="sxs-lookup"><span data-stu-id="210ef-135">Latency : 00:00:01.1234976</span></span>

<span data-ttu-id="210ef-136">오류</span><span class="sxs-lookup"><span data-stu-id="210ef-136">Error :</span></span>

<span data-ttu-id="210ef-137">진단을</span><span class="sxs-lookup"><span data-stu-id="210ef-137">Diagnosis :</span></span>

<span data-ttu-id="210ef-138">지정한 사용자가 그룹 확장을 사용할 수 없는 경우 결과가 실패로 표시 되 고 오류 및 진단 속성에 추가 정보가 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="210ef-138">If the specified user can't use group expansion, then the Result will be shown as Failure and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="210ef-139">TargetUri https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="210ef-139">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="210ef-140">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="210ef-140">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="210ef-141">결과: 실패</span><span class="sxs-lookup"><span data-stu-id="210ef-141">Result : Failure</span></span>

<span data-ttu-id="210ef-142">대기 시간: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="210ef-142">Latency : 00:00:00</span></span>

<span data-ttu-id="210ef-143">오류</span><span class="sxs-lookup"><span data-stu-id="210ef-143">Error :</span></span>

<span data-ttu-id="210ef-144">진단을</span><span class="sxs-lookup"><span data-stu-id="210ef-144">Diagnosis :</span></span>

<span data-ttu-id="210ef-145">Test-CsGroupExpansion: 끝점을 등록할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="210ef-145">Test-CsGroupExpansion : The endpoint was unable to register.</span></span> <span data-ttu-id="210ef-146">특정 이유를 확인 하려면 ErrorCode를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="210ef-146">See the ErrorCode for specific reason.</span></span>

<span data-ttu-id="210ef-147">이전 출력에서는 지정 된 사용자가 Lync Server에 등록할 수 없기 때문에 테스트가 실패 했다는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="210ef-147">The previous output states that the test failed because the specified user was unable to register with Lync Server.</span></span> <span data-ttu-id="210ef-148">이 오류는 일반적으로 테스트 계정이 없거나 Lync Server에 대해 사용 하도록 설정 되지 않은 경우에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="210ef-148">This will typically occur if the test account does not exist or has not enabled for Lync Server.</span></span> <span data-ttu-id="210ef-149">계정이 존재 하는지 확인 하 고 다음과 같은 명령을 실행 하 여 계정이 nm-14-3에 대해 사용 하도록 설정 되었는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="210ef-149">You can verify that the account exists, and determine whether or not the account has been enabled for nm-ocs-14-3rd by running a command similar to the following:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

<span data-ttu-id="210ef-150">Test-CsGroupExpansion 실패 하면 다음 시간에 Verbose 매개 변수를 포함 하 여 테스트를 다시 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="210ef-150">If Test-CsGroupExpansion fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -Verbose

<span data-ttu-id="210ef-151">Verbose 매개 변수를 포함 하면 Test-CsGroupExpansion는 지정 된 사용자가 Lync Server에 로그온 할 수 있는지 확인할 때 시도한 각 작업의 단계별 계정을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="210ef-151">When the Verbose parameter is included Test-CsGroupExpansion will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="210ef-152">예를 들어 다음 출력은 지정 된 메일 그룹을 찾을 수 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="210ef-152">For example, this output indicates that the specified distribution group couldn't be found:</span></span>

<span data-ttu-id="210ef-153">웹 티켓을 가져오려고 했습니다.</span><span class="sxs-lookup"><span data-stu-id="210ef-153">Trying to get web ticket.</span></span>

<span data-ttu-id="210ef-154">웹 서비스 url: https://atl-cs-001.litwareinc.com:443/WebTicket/WebTicketService.svc</span><span class="sxs-lookup"><span data-stu-id="210ef-154">Web Service url : https://atl-cs-001.litwareinc.com:443/WebTicket/WebTicketService.svc</span></span>

<span data-ttu-id="210ef-155">NTLM/Kerb 인증 사용</span><span class="sxs-lookup"><span data-stu-id="210ef-155">Using NTLM/Kerb auth.</span></span>

<span data-ttu-id="210ef-156">GetWebTicketActivity 완료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="210ef-156">GetWebTicketActivity completed.</span></span>

<span data-ttu-id="210ef-157">' VerifyDistributionList ' 활동이 시작 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="210ef-157">'VerifyDistributionList' activity started.</span></span>

<span data-ttu-id="210ef-158">DLX Web Service 응답 상태가 NotFound입니다.</span><span class="sxs-lookup"><span data-stu-id="210ef-158">DLX Web Service Response Status is: NotFound.</span></span>

<span data-ttu-id="210ef-159">' VerifyDistributionList ' 작업이 ' 0.2597923 ' 초에 완료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="210ef-159">'VerifyDistributionList' activity completed in '0.2597923' secs.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="210ef-160">테스트가 실패 한 이유</span><span class="sxs-lookup"><span data-stu-id="210ef-160">Reasons why the test might have failed</span></span>

<span data-ttu-id="210ef-161">Test-CsGroupExpansion 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="210ef-161">Here are some common reasons why Test-CsGroupExpansion might fail:</span></span>

  - <span data-ttu-id="210ef-162">잘못 된 사용자 계정을 지정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="210ef-162">You specified an invalid user account.</span></span> <span data-ttu-id="210ef-163">다음과 같은 명령을 실행 하 여 사용자 계정이 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="210ef-163">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="210ef-164">사용자 계정이 올바르지만 해당 계정이 Lync Server에 대해 현재 사용 하도록 설정 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="210ef-164">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="210ef-165">사용자 계정이 Lync Server에 대해 사용 하도록 설정 되었는지 확인 하려면 다음과 같은 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="210ef-165">To verify that a user account was enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="210ef-166">Enabled 속성을 False로 설정 하면 사용자가 현재 Lync Server를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="210ef-166">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="210ef-167">그룹 확장을 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="210ef-167">Group expansion might be disabled.</span></span> <span data-ttu-id="210ef-168">그룹 확장을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="210ef-168">It is possible to turn off group expansion.</span></span> <span data-ttu-id="210ef-169">그룹 확장을 사용 하지 않도록 설정한 경우에는 Test-CsGroupExpansion cmdlet이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="210ef-169">If group expansion was disabled then the Test-CsGroupExpansion cmdlet will fail.</span></span> <span data-ttu-id="210ef-170">그룹 확장을 사용할 수 있는지 여부를 확인 하려면 다음과 같은 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="210ef-170">To determine whether group expansion is enabled, use a command similar to this:</span></span>
    
        Get-CsWebServiceConfiguration | Select-Object Identity, EnableGroupExpansion

</div>

</div>

<span> </span>

</div>

</div>

</div>

