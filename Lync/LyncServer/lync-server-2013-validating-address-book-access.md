---
title: 'Lync Server 2013: 주소록 액세스 확인'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Validating address book access
ms:assetid: 630682c6-9262-46c5-9af1-6193db70374b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720916(v=OCS.15)
ms:contentKeyID: 63969611
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 233ad9804ea0f9ddd1075ea01bf7a4c8f35da819
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983153"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-address-book-access-in-lync-server-2013"></a><span data-ttu-id="61a47-102">Lync Server 2013에서 주소록 액세스 확인</span><span class="sxs-lookup"><span data-stu-id="61a47-102">Validating address book access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="61a47-103">_**마지막으로 수정한 주제:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="61a47-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="61a47-104">확인 일정</span><span class="sxs-lookup"><span data-stu-id="61a47-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="61a47-105">Daily</span><span class="sxs-lookup"><span data-stu-id="61a47-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61a47-106">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="61a47-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="61a47-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="61a47-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61a47-108">권한이 필요 함</span><span class="sxs-lookup"><span data-stu-id="61a47-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="61a47-109">Lync Server Management Shell을 사용 하 여 로컬에서 실행 되는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61a47-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="61a47-110">Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 사용자는 테스트-CsAddressBookService cmdlet을 실행할 권한이 있는 RBAC 역할을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61a47-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsAddressBookService cmdlet.</span></span> <span data-ttu-id="61a47-111">이 cmdlet을 사용할 수 있는 모든 RBAC 역할 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="61a47-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookService&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="61a47-112">설명</span><span class="sxs-lookup"><span data-stu-id="61a47-112">Description</span></span>

<span data-ttu-id="61a47-113">테스트-CsAddressBookService cmdlet은 사용자가 주소록 다운로드 웹 서비스에 연결할 수 있는지 확인 하는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="61a47-113">The Test-CsAddressBookService cmdlet provides a way for you to verify that a user can connect to the Address Book Download Web service.</span></span> <span data-ttu-id="61a47-114">Cmdlet을 실행 하면 테스트-CsAddressBookService가 지정 된 풀의 주소록 다운로드 웹 서비스에 연결 하 고 주소록 파일의 위치를 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="61a47-114">When you run the cmdlet, Test-CsAddressBookService connects to the Address Book Download Web service on the specified pool and requests the location of the Address Book files.</span></span> <span data-ttu-id="61a47-115">주소록 다운로드 웹 서비스에서 해당 위치를 제공 하는 경우 테스트가 성공한 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61a47-115">If the Address Book Download Web service supplies that location, the test is considered successful.</span></span> <span data-ttu-id="61a47-116">요청이 거부 되 면 테스트를 실패로 간주 합니다.</span><span class="sxs-lookup"><span data-stu-id="61a47-116">If the request is denied, then the test is considered a failure.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="61a47-117">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="61a47-117">Running the test</span></span>

<span data-ttu-id="61a47-118">테스트-CsAddressBookService cmdlet은 미리 구성 된 테스트 계정 (Lync Server 테스트 실행을 위한 테스트 계정 설정 참조) 또는 Lync Server에 대해 사용 하도록 설정 된 모든 사용자의 계정을 사용 하 여 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61a47-118">The Test-CsAddressBookService cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who has been enabled for Lync Server.</span></span> <span data-ttu-id="61a47-119">테스트 계정을 사용 하 여이 검사를 실행 하려면 테스트 중인 Lync Server 풀의 FQDN (정규화 된 도메인 이름)을 지정 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61a47-119">To run this check using a test account, all you need to do is specify the fully qualified domain name (FQDN) of the Lync Server pool being tested.</span></span> <span data-ttu-id="61a47-120">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="61a47-120">For example:</span></span>

    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="61a47-121">실제 사용자 계정을 사용 하 여이 검사를 실행 하려면 먼저 계정 이름과 암호를 포함 하는 Windows PowerShell 자격 증명 개체를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61a47-121">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="61a47-122">그런 다음 테스트-CsAddressBookService를 호출할 때 해당 자격 증명 개체와 해당 계정에 할당 된 SIP 주소를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61a47-122">You must then include that credentials object and the SIP address assigned to the account when calling Test-CsAddressBookService:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="61a47-123">자세한 내용은 [CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService) cmdlet에 대 한 도움말 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="61a47-123">For more information, see the Help documentation for the [Test-CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="61a47-124">성공 또는 실패 확인</span><span class="sxs-lookup"><span data-stu-id="61a47-124">Determining success or failure</span></span>

<span data-ttu-id="61a47-125">지정 된 사용자가 주소록 서비스에 연결할 수 있으면 결과 속성이 **성공**으로 표시 된 것과 비슷한 출력이 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61a47-125">If the specified user is able to connect to the Address Book Service you will get back output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="61a47-126">TargetUri :https://lync-se.fabrikam.com:443/abs/handler</span><span class="sxs-lookup"><span data-stu-id="61a47-126">TargetUri : https://lync-se.fabrikam.com:443/abs/handler</span></span>

<span data-ttu-id="61a47-127">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="61a47-127">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="61a47-128">결과: 성공</span><span class="sxs-lookup"><span data-stu-id="61a47-128">Result : Success</span></span>

<span data-ttu-id="61a47-129">대기 시간: 00:00:06.2260399</span><span class="sxs-lookup"><span data-stu-id="61a47-129">Latency : 00:00:06.2260399</span></span>

<span data-ttu-id="61a47-130">오류</span><span class="sxs-lookup"><span data-stu-id="61a47-130">Error :</span></span>

<span data-ttu-id="61a47-131">있게</span><span class="sxs-lookup"><span data-stu-id="61a47-131">Diagnosis :</span></span>

<span data-ttu-id="61a47-132">지정 된 사용자가이 연결을 할 수 없으면 결과가 실패로 표시 되 고 오류 및 진단 속성에 추가 정보가 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61a47-132">If the specified user is not able to make this connection, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="61a47-133">TargetUri :</span><span class="sxs-lookup"><span data-stu-id="61a47-133">TargetUri :</span></span>

<span data-ttu-id="61a47-134">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="61a47-134">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="61a47-135">결과: 실패</span><span class="sxs-lookup"><span data-stu-id="61a47-135">Result : Failure</span></span>

<span data-ttu-id="61a47-136">대기 시간: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="61a47-136">Latency : 00:00:00</span></span>

<span data-ttu-id="61a47-137">진단: ErrorCode = 4005, Source = atl-cs-001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="61a47-137">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="61a47-138">이유 = 대상 URI가 SIP에 대해 사용 하도록 설정 되지 않았거나 지원 되지 않음</span><span class="sxs-lookup"><span data-stu-id="61a47-138">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="61a47-139">존재.</span><span class="sxs-lookup"><span data-stu-id="61a47-139">exist.</span></span>

<span data-ttu-id="61a47-140">Microsoft DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="61a47-140">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="61a47-141">예를 들어 앞의 출력에는 지정 된 사용자 (즉, "대상 URI")가 없거나 Lync Server에 대해 사용 하도록 설정 되어 있지 않아 테스트가 실패 했음을 알리는 메시지가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61a47-141">For example, the preceding output states that the test failed because the specified user (that is, the “Destination URI”) either does not exist or has not been enabled for Lync Server.</span></span> <span data-ttu-id="61a47-142">사용자 계정이 유효한 지 여부를 확인 하 고, 다음과 같은 명령을 실행 하 여 올바른 SIP 주소를 입력 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="61a47-142">You can verify whether or not a user account is valid, and verify that you supplied the correct SIP address, by running a command like this one:</span></span>

<span data-ttu-id="61a47-143">Get-CsUser-Id "sip:kenmyer@litwareinc.com" | 선택-개체 SipAddress, 사용</span><span class="sxs-lookup"><span data-stu-id="61a47-143">Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled</span></span>

<span data-ttu-id="61a47-144">테스트-CsAddressBookService가 실패 하는 경우 다음 시간에 Verbose 매개 변수를 포함 하 여 테스트를 다시 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61a47-144">If Test-CsAddressBookService fails then you might want to rerun the test, this time including the Verbose parameter:</span></span>

<span data-ttu-id="61a47-145">테스트-CsAddressBookService-TargetFqdn "atl-cs-001.litwareinc.com"-Verbose</span><span class="sxs-lookup"><span data-stu-id="61a47-145">Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose</span></span>

<span data-ttu-id="61a47-146">Verbose 매개 변수를 포함 하는 경우 테스트-CsAddressBookService는 지정 된 사용자가 Lync Server에 로그온 하는 기능을 확인할 때 시도한 각 작업의 단계별 계정을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="61a47-146">When the Verbose parameter is included Test-CsAddressBookService will return a step-by-step account of each action it attempted when checking the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="61a47-147">예를 들어 다음은이 예제에 있는 테스트 CsAddressBookService가 주소록 파일을 다운로드할 수 있다는 것을 보여 주는 예제 출력입니다.</span><span class="sxs-lookup"><span data-stu-id="61a47-147">For example, this sample output shows that Test-CsAddressBookService, at least in this example, was able to download the Address Book file:</span></span>

<span data-ttu-id="61a47-148">Http GET 요청을 보내는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="61a47-148">Sending Http GET Request.</span></span>

<span data-ttu-id="61a47-149">파일 경로 =https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span><span class="sxs-lookup"><span data-stu-id="61a47-149">File Path = https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span></span>

<span data-ttu-id="61a47-150">시도 번호 = 1</span><span class="sxs-lookup"><span data-stu-id="61a47-150">Attempt Number = 1</span></span>

<span data-ttu-id="61a47-151">TimeOut (msec) = 6만</span><span class="sxs-lookup"><span data-stu-id="61a47-151">TimeOut (msec) = 60000</span></span>

<span data-ttu-id="61a47-152">ABS 파일을 다운로드 했습니다.https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span><span class="sxs-lookup"><span data-stu-id="61a47-152">Successfully Downloaded the ABS file https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="61a47-153">테스트가 실패할 수 있는 이유</span><span class="sxs-lookup"><span data-stu-id="61a47-153">Reasons why the test might have failed</span></span>

<span data-ttu-id="61a47-154">테스트-CsAddressBookService 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="61a47-154">Here are some common reasons why Test-CsAddressBookService might fail:</span></span>

  - <span data-ttu-id="61a47-155">잘못 된 사용자 계정을 지정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="61a47-155">You specified an invalid user account.</span></span> <span data-ttu-id="61a47-156">다음과 같은 명령을 실행 하 여 사용자 계정이 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61a47-156">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="61a47-157">사용자 계정이 올바르지만 현재 Lync Server에 계정이 설정 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="61a47-157">The user account is valid, but the account is not currently enabled for Lync Server.</span></span> <span data-ttu-id="61a47-158">Lync Server에 대해 사용자 계정이 사용 하도록 설정 되어 있는지 확인 하려면 다음과 같은 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="61a47-158">To verify that a user account has been enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="61a47-159">Enabled 속성이 False로 설정 된 경우 사용자가 현재 Lync Server에 대해 사용 하도록 설정 되어 있지 않음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="61a47-159">If the Enabled property is set to False that means that the user is not currently enabled for Lync Server.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="61a47-160">참고 항목</span><span class="sxs-lookup"><span data-stu-id="61a47-160">See Also</span></span>


[<span data-ttu-id="61a47-161">Test-CsAddressBookService</span><span class="sxs-lookup"><span data-stu-id="61a47-161">Test-CsAddressBookService</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

