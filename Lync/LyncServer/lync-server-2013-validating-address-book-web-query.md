---
title: 'Lync Server 2013: 주소록 웹 쿼리 확인'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating address book web query
ms:assetid: e6ae0a5a-e131-4cfe-9a33-6e611831072d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720925(v=OCS.15)
ms:contentKeyID: 63969662
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31d6a38c0c1d8a67977f9dd66da2a94b51a4f9ab
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763662"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-address-book-web-query-in-lync-server-2013"></a><span data-ttu-id="53a8d-102">Lync Server 2013에서 주소록 웹 쿼리 확인</span><span class="sxs-lookup"><span data-stu-id="53a8d-102">Validating address book web query in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="53a8d-103">_**마지막으로 수정한 주제:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="53a8d-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="53a8d-104">확인 일정</span><span class="sxs-lookup"><span data-stu-id="53a8d-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="53a8d-105">Daily</span><span class="sxs-lookup"><span data-stu-id="53a8d-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a8d-106">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="53a8d-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="53a8d-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="53a8d-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a8d-108">권한이 필요 함</span><span class="sxs-lookup"><span data-stu-id="53a8d-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="53a8d-109">Lync Server Management Shell을 사용 하 여 로컬에서 실행 되는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53a8d-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="53a8d-110">Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 테스트-CsAddressBookWebQuery cmdlet을 실행할 수 있는 권한이 있는 RBAC 역할을 사용자에 게 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53a8d-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsAddressBookWebQuery cmdlet.</span></span> <span data-ttu-id="53a8d-111">이 cmdlet을 사용할 수 있는 모든 RBAC 역할 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="53a8d-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookWebQuery&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="53a8d-112">설명</span><span class="sxs-lookup"><span data-stu-id="53a8d-112">Description</span></span>

<span data-ttu-id="53a8d-113">관리자는 테스트-CsAddressBookWebQuery cmdlet을 통해 사용자가 주소록 웹 쿼리 서비스를 사용 하 여 특정 연락처를 검색할지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53a8d-113">The Test-CsAddressBookWebQuery cmdlet enables administrators to verify that users can use the Address Book Web Query service to search for a specific contact.</span></span> <span data-ttu-id="53a8d-114">Cmdlet을 실행할 때 테스트-CsAddressBookWebQuery는 먼저 인증 받을 웹 티켓 서비스에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="53a8d-114">When you run the cmdlet, Test-CsAddressBookWebQuery will first connect to the Web Ticket service to be authenticated.</span></span> <span data-ttu-id="53a8d-115">인증에 성공 하면 cmdlet이 주소록 웹 쿼리 서비스에 연결 하 고 지정 된 연락처를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="53a8d-115">If authentication is successful, the cmdlet will then connect to the Address Book Web Query service and search for the specified contact.</span></span> <span data-ttu-id="53a8d-116">해당 연락처가 발견 되 면 cmdlet이 해당 정보를 로컬 컴퓨터로 반환 하려고 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="53a8d-116">If that contact is found, the cmdlet will attempt to return that information to the local computer.</span></span> <span data-ttu-id="53a8d-117">해당 단계가 모두 완료 될 수 있는 경우에만 테스트가 성공으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="53a8d-117">The test will be marked a success only if all those steps can be completed.</span></span>

<span data-ttu-id="53a8d-118">자세한 내용은 [테스트-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) cmdlet에 대 한 도움말 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="53a8d-118">For more information, see the Help documentation for the [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="53a8d-119">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="53a8d-119">Running the test</span></span>

<span data-ttu-id="53a8d-120">테스트-CsAddressBookWebQuery cmdlet은 미리 구성 된 테스트 계정 (Lync Server 테스트 실행을 위한 테스트 계정 설정 참조) 또는 Lync Server에 대해 사용 하도록 설정 된 모든 사용자의 계정을 사용 하 여 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53a8d-120">The Test-CsAddressBookWebQuery cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="53a8d-121">테스트 계정을 사용 하 여이 검사를 실행 하려면 Lync Server 풀의 FQDN과 검색 대상으로 작동 하는 사용자의 SIP 주소를 지정 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="53a8d-121">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool and the SIP address of the user acting as the target of the search.</span></span> <span data-ttu-id="53a8d-122">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="53a8d-122">For example:</span></span>

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com"

<span data-ttu-id="53a8d-123">실제 사용자 계정을 사용 하 여이 검사를 실행 하려면 유효한 사용자 이름 및 암호를 포함 하는 Windows PowerShell 자격 증명 개체를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53a8d-123">To run this check using an actual user account, you must create a Windows PowerShell credentials object that contains a valid user name and password.</span></span> <span data-ttu-id="53a8d-124">그런 다음 코드에서 테스트-CsAddressBookWebQuery를 호출할 때 계정에 할당 된 해당 자격 증명 개체와 SIP 주소를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53a8d-124">You must then include that credentials object and the SIP address assigned to the account when the code calls Test-CsAddressBookWebQuery:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="53a8d-125">자세한 내용은 [테스트-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) cmdlet에 대 한 도움말 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="53a8d-125">For more information, see the Help documentation for the [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="53a8d-126">성공 또는 실패 확인</span><span class="sxs-lookup"><span data-stu-id="53a8d-126">Determining success or failure</span></span>

<span data-ttu-id="53a8d-127">지정 된 사용자가 주소록 서비스에 연결 하 고 대상 사용자 주소를 검색할 수 있는 경우 결과 속성이 성공으로 표시 된 것과 비슷한 출력을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="53a8d-127">If the specified user can connect to the Address Book Service and retrieve the targeted user address, you'll return output similar to this with the Result property marked as Success:</span></span>

<span data-ttu-id="53a8d-128">TargetUri :https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="53a8d-128">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="53a8d-129">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="53a8d-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="53a8d-130">결과: 성공</span><span class="sxs-lookup"><span data-stu-id="53a8d-130">Result : Success</span></span>

<span data-ttu-id="53a8d-131">대기 시간: 00:00:06.2611356</span><span class="sxs-lookup"><span data-stu-id="53a8d-131">Latency : 00:00:06.2611356</span></span>

<span data-ttu-id="53a8d-132">오류</span><span class="sxs-lookup"><span data-stu-id="53a8d-132">Error :</span></span>

<span data-ttu-id="53a8d-133">있게</span><span class="sxs-lookup"><span data-stu-id="53a8d-133">Diagnosis :</span></span>

<span data-ttu-id="53a8d-134">지정 된 사용자가 연결할 수 없거나 대상 사용자 주소를 검색할 수 없는 경우에는 결과가 실패로 표시 되 고 오류 및 진단 속성에 추가 정보가 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="53a8d-134">If the specified user can't connect or if the target user address cannot be retrieved, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="53a8d-135">TargetUri :https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="53a8d-135">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="53a8d-136">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="53a8d-136">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="53a8d-137">결과: 실패</span><span class="sxs-lookup"><span data-stu-id="53a8d-137">Result : Failure</span></span>

<span data-ttu-id="53a8d-138">대기 시간: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="53a8d-138">Latency : 00:00:00</span></span>

<span data-ttu-id="53a8d-139">오류: 응답 코드와 함께 주소록 웹 서비스 요청이 실패 했습니다.</span><span class="sxs-lookup"><span data-stu-id="53a8d-139">Error : Address Book Web service request has failed with response code</span></span>

<span data-ttu-id="53a8d-140">NoEntryFound.</span><span class="sxs-lookup"><span data-stu-id="53a8d-140">NoEntryFound.</span></span>

<span data-ttu-id="53a8d-141">있게</span><span class="sxs-lookup"><span data-stu-id="53a8d-141">Diagnosis :</span></span>

<span data-ttu-id="53a8d-142">이전 출력에서는 대상 사용자를 찾을 수 없기 때문에 테스트가 실패 했다는 것을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="53a8d-142">The previous output states that the test failed because the target user couldn't be found.</span></span> <span data-ttu-id="53a8d-143">다음과 같은 명령을 실행 하 여 유효한 SIP 주소가 테스트-CsAddressBookWebQuery에 전달 되었는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53a8d-143">You can determine whether or not a valid SIP address was passed to Test-CsAddressBookWebQuery by running a command similar to the following:</span></span>

    Get-CsUser | Where-Object {$_.SipAddress -eq "sip:davidlongmire@litwareinc.com"

<span data-ttu-id="53a8d-144">테스트-CsAddressBookWebQuery가 실패 하는 경우 다음과 같이 Verbose 매개 변수를 포함 하 여 테스트를 다시 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53a8d-144">If Test-CsAddressBookWebQuery fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -Verbose

<span data-ttu-id="53a8d-145">Verbose 매개 변수가 포함 된 경우 테스트-CsAddressBookWebQuery는 지정 된 사용자가 Lync Server에 로그온 하는 기능을 확인 하는 동안 시도한 각 작업의 단계별 계정을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="53a8d-145">When the Verbose parameter is included, Test-CsAddressBookWebQuery will return a step-by-step account of each action it tried while checking the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="53a8d-146">예를 들어이 출력은 테스트-CsAddressBookWebQuery가 주소록 서비스에 연결할 수 있었지만 대상 SIP 주소를 찾을 수 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="53a8d-146">For example, this output indicates that Test-CsAddressBookWebQuery was able to connect to the Address Book Service, but was not able to locate the target SIP address:</span></span>

<span data-ttu-id="53a8d-147">' QueryAddressBookWebService ' 활동이 시작 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="53a8d-147">'QueryAddressBookWebService' activity started.</span></span>

<span data-ttu-id="53a8d-148">호출 주소록 웹 쿼리 서비스</span><span class="sxs-lookup"><span data-stu-id="53a8d-148">Calling Address Book Web Query Service.</span></span> <span data-ttu-id="53a8d-149">ABWS URL =</span><span class="sxs-lookup"><span data-stu-id="53a8d-149">ABWS URL =</span></span>

https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

<span data-ttu-id="53a8d-150">주소록 쿼리 예외: 응답 코드 NoEntryFound 발견 하 여 주소록 웹 서비스 요청이 실패 했습니다.</span><span class="sxs-lookup"><span data-stu-id="53a8d-150">Address book query exception : Address Book Web service request has failed with response code NoEntryFound.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="53a8d-151">테스트가 실패할 수 있는 이유</span><span class="sxs-lookup"><span data-stu-id="53a8d-151">Reasons Why the Test Might Have Failed</span></span>

<span data-ttu-id="53a8d-152">테스트-CsAddressBookWebQuery가 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="53a8d-152">Here are some common reasons why Test-CsAddressBookWebQuery might fail:</span></span>

  - <span data-ttu-id="53a8d-153">잘못 된 사용자 계정을 지정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="53a8d-153">You specified an invalid user account.</span></span> <span data-ttu-id="53a8d-154">다음과 같은 명령을 실행 하 여 사용자 계정이 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53a8d-154">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="53a8d-155">사용자 계정이 올바르지만 현재 Lync Server에 계정이 설정 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="53a8d-155">The user account is valid, but the account is not currently enabled for Lync Server.</span></span> <span data-ttu-id="53a8d-156">Lync Server에 대해 사용자 계정이 사용 하도록 설정 되어 있는지 확인 하려면 다음과 같은 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="53a8d-156">To verify that a user account has been enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="53a8d-157">Enabled 속성이 False로 설정 된 경우 사용자가 현재 Lync Server에 대해 사용 하도록 설정 되어 있지 않음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="53a8d-157">If the Enabled property is set to False that means that the user is not currently enabled for Lync Server.</span></span>

  - <span data-ttu-id="53a8d-158">대상 사용자가 주소록에 없을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53a8d-158">The target user might not be in the Address Book.</span></span>

  - <span data-ttu-id="53a8d-159">주소록이 완전히 업데이트 및 복제 되지 않았을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53a8d-159">The Address Book might not have fully updated and replicated.</span></span> <span data-ttu-id="53a8d-160">다음 명령을 실행 하 여 조직의 모든 주소록 서버를 강제로 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53a8d-160">You can force an update of all the Address Book Servers in your organization by running the following command:</span></span>
    
        Update-CsAddressBook

</div>

</div>

<span> </span>

</div>

</div>

</div>

