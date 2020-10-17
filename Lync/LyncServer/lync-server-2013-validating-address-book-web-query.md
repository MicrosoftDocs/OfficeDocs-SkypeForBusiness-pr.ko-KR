---
title: 'Lync Server 2013: 주소록 웹 쿼리 확인'
description: 'Lync Server 2013: 주소록 웹 쿼리 유효성 검사'
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
ms.openlocfilehash: e73c39fc33f8d1851fc89d277333a94aaa137790
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547254"
---
# <a name="validating-address-book-web-query-in-lync-server-2013"></a><span data-ttu-id="8e2f8-103">Lync Server 2013에서 주소록 웹 쿼리 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="8e2f8-103">Validating address book web query in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8e2f8-104">_**마지막으로 수정 된 항목:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="8e2f8-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8e2f8-105">확인 일정</span><span class="sxs-lookup"><span data-stu-id="8e2f8-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="8e2f8-106">매일</span><span class="sxs-lookup"><span data-stu-id="8e2f8-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e2f8-107">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="8e2f8-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="8e2f8-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8e2f8-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e2f8-109">필요한 권한</span><span class="sxs-lookup"><span data-stu-id="8e2f8-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="8e2f8-110">Lync Server 관리 셸을 사용 하 여 로컬로 실행 하는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e2f8-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="8e2f8-111">Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 사용자에 게 Test-CsAddressBookWebQuery cmdlet을 실행 하는 권한이 있는 RBAC 역할을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e2f8-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsAddressBookWebQuery cmdlet.</span></span> <span data-ttu-id="8e2f8-112">이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e2f8-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookWebQuery&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="8e2f8-113">설명</span><span class="sxs-lookup"><span data-stu-id="8e2f8-113">Description</span></span>

<span data-ttu-id="8e2f8-114">관리자는 Test-CsAddressBookWebQuery cmdlet을 사용 하 여 사용자가 주소록 웹 쿼리 서비스를 사용 하 여 특정 연락처를 검색할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e2f8-114">The Test-CsAddressBookWebQuery cmdlet enables administrators to verify that users can use the Address Book Web Query service to search for a specific contact.</span></span> <span data-ttu-id="8e2f8-115">Cmdlet을 실행할 때 Test-CsAddressBookWebQuery는 먼저 인증을 받기 위해 웹 티켓 서비스에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e2f8-115">When you run the cmdlet, Test-CsAddressBookWebQuery will first connect to the Web Ticket service to be authenticated.</span></span> <span data-ttu-id="8e2f8-116">인증에 성공 하면 cmdlet이 주소록 웹 쿼리 서비스에 연결 하 여 지정 된 연락처를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e2f8-116">If authentication is successful, the cmdlet will then connect to the Address Book Web Query service and search for the specified contact.</span></span> <span data-ttu-id="8e2f8-117">연락처가 발견되면 이 정보를 로컬 컴퓨터로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8e2f8-117">If that contact is found, the cmdlet will attempt to return that information to the local computer.</span></span> <span data-ttu-id="8e2f8-118">이러한 모든 단계를 완료할 수 있는 경우에만 테스트가 성공으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e2f8-118">The test will be marked a success only if all those steps can be completed.</span></span>

<span data-ttu-id="8e2f8-119">자세한 내용은 [테스트-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) cmdlet에 대 한 도움말 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8e2f8-119">For more information, see the Help documentation for the [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="8e2f8-120">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="8e2f8-120">Running the test</span></span>

<span data-ttu-id="8e2f8-121">Test-CsAddressBookWebQuery cmdlet은 미리 구성 된 테스트 계정 (Lync Server 테스트 실행을 위한 테스트 계정 설정 참조) 또는 Lync Server를 사용 하도록 설정 된 사용자의 계정 중 하나를 사용 하 여 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e2f8-121">The Test-CsAddressBookWebQuery cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="8e2f8-122">테스트 계정을 사용 하 여이 검사를 실행 하려면 Lync Server 풀의 FQDN과 검색 대상으로 작동 하는 사용자의 SIP 주소를 지정 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e2f8-122">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool and the SIP address of the user acting as the target of the search.</span></span> <span data-ttu-id="8e2f8-123">예제:</span><span class="sxs-lookup"><span data-stu-id="8e2f8-123">For example:</span></span>

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com"

<span data-ttu-id="8e2f8-124">실제 사용자 계정을 사용 하 여이 검사를 실행 하려면 유효한 사용자 이름과 암호를 포함 하는 Windows PowerShell 자격 증명 개체를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e2f8-124">To run this check using an actual user account, you must create a Windows PowerShell credentials object that contains a valid user name and password.</span></span> <span data-ttu-id="8e2f8-125">그런 다음 코드에서 Test-CsAddressBookWebQuery를 호출 하면 해당 자격 증명 개체와 해당 계정에 할당 된 SIP 주소를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e2f8-125">You must then include that credentials object and the SIP address assigned to the account when the code calls Test-CsAddressBookWebQuery:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="8e2f8-126">자세한 내용은 [테스트-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) cmdlet에 대 한 도움말 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8e2f8-126">For more information, see the Help documentation for the [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="8e2f8-127">성공 또는 실패 확인</span><span class="sxs-lookup"><span data-stu-id="8e2f8-127">Determining success or failure</span></span>

<span data-ttu-id="8e2f8-128">지정 된 사용자가 주소록 서비스에 연결 하 여 대상 사용자 주소를 검색할 수 있는 경우 Result 속성이 Success로 표시 된 것과 비슷한 출력을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e2f8-128">If the specified user can connect to the Address Book Service and retrieve the targeted user address, you'll return output similar to this with the Result property marked as Success:</span></span>

<span data-ttu-id="8e2f8-129">TargetUri https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="8e2f8-129">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="8e2f8-130">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="8e2f8-130">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="8e2f8-131">결과: 성공</span><span class="sxs-lookup"><span data-stu-id="8e2f8-131">Result : Success</span></span>

<span data-ttu-id="8e2f8-132">대기 시간: 00:00:06.2611356</span><span class="sxs-lookup"><span data-stu-id="8e2f8-132">Latency : 00:00:06.2611356</span></span>

<span data-ttu-id="8e2f8-133">오류</span><span class="sxs-lookup"><span data-stu-id="8e2f8-133">Error :</span></span>

<span data-ttu-id="8e2f8-134">진단을</span><span class="sxs-lookup"><span data-stu-id="8e2f8-134">Diagnosis :</span></span>

<span data-ttu-id="8e2f8-135">지정한 사용자가 연결할 수 없거나 대상 사용자 주소를 검색할 수 없는 경우 결과가 실패로 표시 되 고 오류 및 진단 속성에 추가 정보가 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e2f8-135">If the specified user can't connect or if the target user address cannot be retrieved, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="8e2f8-136">TargetUri https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="8e2f8-136">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="8e2f8-137">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="8e2f8-137">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="8e2f8-138">결과: 실패</span><span class="sxs-lookup"><span data-stu-id="8e2f8-138">Result : Failure</span></span>

<span data-ttu-id="8e2f8-139">대기 시간: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="8e2f8-139">Latency : 00:00:00</span></span>

<span data-ttu-id="8e2f8-140">오류: 응답 코드와 함께 주소록 웹 서비스 요청이 실패 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8e2f8-140">Error : Address Book Web service request has failed with response code</span></span>

<span data-ttu-id="8e2f8-141">NoEntryFound 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e2f8-141">NoEntryFound.</span></span>

<span data-ttu-id="8e2f8-142">진단을</span><span class="sxs-lookup"><span data-stu-id="8e2f8-142">Diagnosis :</span></span>

<span data-ttu-id="8e2f8-143">이전 출력에서는 대상 사용자를 찾을 수 없기 때문에 테스트가 실패 했다는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8e2f8-143">The previous output states that the test failed because the target user couldn't be found.</span></span> <span data-ttu-id="8e2f8-144">다음과 같은 명령을 실행 하 여 Test-CsAddressBookWebQuery에 유효한 SIP 주소가 전달 되었는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e2f8-144">You can determine whether or not a valid SIP address was passed to Test-CsAddressBookWebQuery by running a command similar to the following:</span></span>

    Get-CsUser | Where-Object {$_.SipAddress -eq "sip:davidlongmire@litwareinc.com"

<span data-ttu-id="8e2f8-145">Test-CsAddressBookWebQuery 실패 하면 다음 시간에 Verbose 매개 변수를 포함 하 여 테스트를 다시 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e2f8-145">If Test-CsAddressBookWebQuery fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -Verbose

<span data-ttu-id="8e2f8-146">Verbose 매개 변수를 포함 하면 Test-CsAddressBookWebQuery는 지정 된 사용자가 Lync Server에 로그온 할 수 있는지 확인 하는 동안 시도한 각 작업의 단계별 계정을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e2f8-146">When the Verbose parameter is included, Test-CsAddressBookWebQuery will return a step-by-step account of each action it tried while checking the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="8e2f8-147">예를 들어이 출력은 Test-CsAddressBookWebQuery가 주소록 서비스에 연결할 수 있지만 대상 SIP 주소를 찾을 수 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8e2f8-147">For example, this output indicates that Test-CsAddressBookWebQuery was able to connect to the Address Book Service, but was not able to locate the target SIP address:</span></span>

<span data-ttu-id="8e2f8-148">' QueryAddressBookWebService ' 활동이 시작 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8e2f8-148">'QueryAddressBookWebService' activity started.</span></span>

<span data-ttu-id="8e2f8-149">전화 주소록 웹 쿼리 서비스를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e2f8-149">Calling Address Book Web Query Service.</span></span> <span data-ttu-id="8e2f8-150">ABWS URL =</span><span class="sxs-lookup"><span data-stu-id="8e2f8-150">ABWS URL =</span></span>

https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

<span data-ttu-id="8e2f8-151">주소록 쿼리 예외: 응답 코드 NoEntryFound 발견 되어 주소록 웹 서비스 요청이 실패 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8e2f8-151">Address book query exception : Address Book Web service request has failed with response code NoEntryFound.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="8e2f8-152">테스트가 실패 한 이유</span><span class="sxs-lookup"><span data-stu-id="8e2f8-152">Reasons Why the Test Might Have Failed</span></span>

<span data-ttu-id="8e2f8-153">Test-CsAddressBookWebQuery 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8e2f8-153">Here are some common reasons why Test-CsAddressBookWebQuery might fail:</span></span>

  - <span data-ttu-id="8e2f8-154">잘못 된 사용자 계정을 지정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8e2f8-154">You specified an invalid user account.</span></span> <span data-ttu-id="8e2f8-155">다음과 같은 명령을 실행 하 여 사용자 계정이 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e2f8-155">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="8e2f8-156">사용자 계정이 올바르지만 현재 Lync Server에 대해 계정이 사용 하도록 설정 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e2f8-156">The user account is valid, but the account is not currently enabled for Lync Server.</span></span> <span data-ttu-id="8e2f8-157">사용자 계정이 Lync Server에 대해 사용 하도록 설정 되었는지 확인 하려면 다음과 같은 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e2f8-157">To verify that a user account has been enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="8e2f8-158">Enabled 속성을 False로 설정 하면 사용자가 현재 Lync Server를 사용 하도록 설정 되지 않은 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8e2f8-158">If the Enabled property is set to False that means that the user is not currently enabled for Lync Server.</span></span>

  - <span data-ttu-id="8e2f8-159">대상 사용자가 주소록에 없을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e2f8-159">The target user might not be in the Address Book.</span></span>

  - <span data-ttu-id="8e2f8-160">주소록이 완전히 업데이트 및 복제 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e2f8-160">The Address Book might not have fully updated and replicated.</span></span> <span data-ttu-id="8e2f8-161">다음 명령을 실행 하 여 조직의 모든 주소록 서버를 강제로 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e2f8-161">You can force an update of all the Address Book Servers in your organization by running the following command:</span></span>
    
        Update-CsAddressBook

</div>

</div>

<span> </span>

</div>

</div>

</div>

