---
title: 'Lync Server 2013: 주소록 액세스 유효성 검사'
description: 'Lync Server 2013: 주소록 액세스 유효성 검사'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating address book access
ms:assetid: 630682c6-9262-46c5-9af1-6193db70374b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720916(v=OCS.15)
ms:contentKeyID: 63969611
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6da08e48be24b3325bc1f415b9baa3c9197717c3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547244"
---
# <a name="validating-address-book-access-in-lync-server-2013"></a><span data-ttu-id="5a72d-103">Lync Server 2013에서 주소록 액세스 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="5a72d-103">Validating address book access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5a72d-104">_**마지막으로 수정 된 항목:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="5a72d-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5a72d-105">확인 일정</span><span class="sxs-lookup"><span data-stu-id="5a72d-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="5a72d-106">매일</span><span class="sxs-lookup"><span data-stu-id="5a72d-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a72d-107">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="5a72d-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="5a72d-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5a72d-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a72d-109">필요한 권한</span><span class="sxs-lookup"><span data-stu-id="5a72d-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="5a72d-110">Lync Server 관리 셸을 사용 하 여 로컬로 실행 하는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a72d-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="5a72d-111">Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 사용자에 게 Test-CsAddressBookService cmdlet을 실행 하는 권한이 있는 RBAC 역할을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a72d-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsAddressBookService cmdlet.</span></span> <span data-ttu-id="5a72d-112">이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a72d-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookService&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="5a72d-113">설명</span><span class="sxs-lookup"><span data-stu-id="5a72d-113">Description</span></span>

<span data-ttu-id="5a72d-114">Test-CsAddressBookService cmdlet은 사용자가 주소록 다운로드 웹 서비스에 연결할 수 있는지 확인 하는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a72d-114">The Test-CsAddressBookService cmdlet provides a way for you to verify that a user can connect to the Address Book Download Web service.</span></span> <span data-ttu-id="5a72d-115">Cmdlet을 실행할 때 Test-CsAddressBookService 지정 된 풀의 주소록 다운로드 웹 서비스에 연결 하 고 주소록 파일의 위치를 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a72d-115">When you run the cmdlet, Test-CsAddressBookService connects to the Address Book Download Web service on the specified pool and requests the location of the Address Book files.</span></span> <span data-ttu-id="5a72d-116">주소록 다운로드 웹 서비스가 해당 위치를 제공 하는 경우 테스트가 성공한 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a72d-116">If the Address Book Download Web service supplies that location, the test is considered successful.</span></span> <span data-ttu-id="5a72d-117">요청이 거부되면 테스트는 실패로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a72d-117">If the request is denied, then the test is considered a failure.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="5a72d-118">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="5a72d-118">Running the test</span></span>

<span data-ttu-id="5a72d-119">Test-CsAddressBookService cmdlet은 미리 구성 된 테스트 계정 (Lync Server 테스트 실행을 위한 테스트 계정 설정 참조) 또는 Lync Server를 사용 하도록 설정 된 사용자의 계정 중 하나를 사용 하 여 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a72d-119">The Test-CsAddressBookService cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who has been enabled for Lync Server.</span></span> <span data-ttu-id="5a72d-120">테스트 계정을 사용 하 여이 검사를 실행 하려면 테스트 중인 Lync Server 풀의 FQDN (정규화 된 도메인 이름)을 지정 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a72d-120">To run this check using a test account, all you need to do is specify the fully qualified domain name (FQDN) of the Lync Server pool being tested.</span></span> <span data-ttu-id="5a72d-121">예제:</span><span class="sxs-lookup"><span data-stu-id="5a72d-121">For example:</span></span>

    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="5a72d-122">실제 사용자 계정을 사용 하 여이 검사를 실행 하려면 먼저 계정 이름과 암호가 포함 된 Windows PowerShell 자격 증명 개체를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a72d-122">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="5a72d-123">그런 다음 테스트-CsAddressBookService를 호출할 때 해당 자격 증명 개체 및 해당 계정에 할당 된 SIP 주소를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a72d-123">You must then include that credentials object and the SIP address assigned to the account when calling Test-CsAddressBookService:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="5a72d-124">자세한 내용은 [CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService) cmdlet에 대 한 도움말 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="5a72d-124">For more information, see the Help documentation for the [Test-CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="5a72d-125">성공 또는 실패 확인</span><span class="sxs-lookup"><span data-stu-id="5a72d-125">Determining success or failure</span></span>

<span data-ttu-id="5a72d-126">지정 된 사용자가 주소록 서비스에 연결할 수 있으면 Result 속성이 **Success**로 표시 된 것과 비슷한 출력이 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a72d-126">If the specified user is able to connect to the Address Book Service you will get back output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="5a72d-127">TargetUri https://lync-se.fabrikam.com:443/abs/handler</span><span class="sxs-lookup"><span data-stu-id="5a72d-127">TargetUri : https://lync-se.fabrikam.com:443/abs/handler</span></span>

<span data-ttu-id="5a72d-128">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="5a72d-128">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="5a72d-129">결과: 성공</span><span class="sxs-lookup"><span data-stu-id="5a72d-129">Result : Success</span></span>

<span data-ttu-id="5a72d-130">대기 시간: 00:00:06.2260399</span><span class="sxs-lookup"><span data-stu-id="5a72d-130">Latency : 00:00:06.2260399</span></span>

<span data-ttu-id="5a72d-131">오류</span><span class="sxs-lookup"><span data-stu-id="5a72d-131">Error :</span></span>

<span data-ttu-id="5a72d-132">진단을</span><span class="sxs-lookup"><span data-stu-id="5a72d-132">Diagnosis :</span></span>

<span data-ttu-id="5a72d-133">지정 된 사용자가이 연결을 설정할 수 없으면 결과가 실패로 표시 되 고 오류 및 진단 속성에 추가 정보가 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a72d-133">If the specified user is not able to make this connection, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="5a72d-134">TargetUri</span><span class="sxs-lookup"><span data-stu-id="5a72d-134">TargetUri :</span></span>

<span data-ttu-id="5a72d-135">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="5a72d-135">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="5a72d-136">결과: 실패</span><span class="sxs-lookup"><span data-stu-id="5a72d-136">Result : Failure</span></span>

<span data-ttu-id="5a72d-137">대기 시간: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="5a72d-137">Latency : 00:00:00</span></span>

<span data-ttu-id="5a72d-138">진단: ErrorCode = 4005, Source = atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="5a72d-138">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="5a72d-139">이유 = 대상 URI가 SIP에 대해 사용 하도록 설정 되지 않았거나 지원 되지 않음</span><span class="sxs-lookup"><span data-stu-id="5a72d-139">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="5a72d-140">가.</span><span class="sxs-lookup"><span data-stu-id="5a72d-140">exist.</span></span>

<span data-ttu-id="5a72d-141">Microsoft DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="5a72d-141">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="5a72d-142">예를 들어 위의 출력에서는 지정 된 사용자 ("대상 URI")가 존재 하지 않거나 Lync Server에 대해 사용 하도록 설정 되지 않아 테스트가 실패 했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5a72d-142">For example, the preceding output states that the test failed because the specified user (that is, the “Destination URI”) either does not exist or has not been enabled for Lync Server.</span></span> <span data-ttu-id="5a72d-143">사용자 계정이 유효한 지 여부를 확인 하 고, 다음과 같은 명령을 실행 하 여 올바른 SIP 주소를 제공 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a72d-143">You can verify whether or not a user account is valid, and verify that you supplied the correct SIP address, by running a command like this one:</span></span>

<span data-ttu-id="5a72d-144">Get-CsUser-Id "sip:kenmyer@litwareinc.com" | Select-Object Nm-server-w15-short, Enabled</span><span class="sxs-lookup"><span data-stu-id="5a72d-144">Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled</span></span>

<span data-ttu-id="5a72d-145">Test-CsAddressBookService 실패 하면 다음 시간에 Verbose 매개 변수를 포함 하 여 테스트를 다시 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a72d-145">If Test-CsAddressBookService fails then you might want to rerun the test, this time including the Verbose parameter:</span></span>

<span data-ttu-id="5a72d-146">Test-CsAddressBookService-TargetFqdn "atl-cs-001.litwareinc.com"-Verbose</span><span class="sxs-lookup"><span data-stu-id="5a72d-146">Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose</span></span>

<span data-ttu-id="5a72d-147">Verbose 매개 변수를 포함 하면 Test-CsAddressBookService는 지정 된 사용자가 Lync Server에 로그온 할 수 있는지 확인할 때 시도한 각 작업의 단계별 계정을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a72d-147">When the Verbose parameter is included Test-CsAddressBookService will return a step-by-step account of each action it attempted when checking the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="5a72d-148">예를 들어 다음은이 예제에 나와 있는 테스트-CsAddressBookService가 주소록 파일을 다운로드할 수 있다는 것을 보여 주는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="5a72d-148">For example, this sample output shows that Test-CsAddressBookService, at least in this example, was able to download the Address Book file:</span></span>

<span data-ttu-id="5a72d-149">Http GET 요청을 보내는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="5a72d-149">Sending Http GET Request.</span></span>

<span data-ttu-id="5a72d-150">파일 경로 = https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span><span class="sxs-lookup"><span data-stu-id="5a72d-150">File Path = https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span></span>

<span data-ttu-id="5a72d-151">시도 번호 = 1</span><span class="sxs-lookup"><span data-stu-id="5a72d-151">Attempt Number = 1</span></span>

<span data-ttu-id="5a72d-152">시간 제한 (밀리초) = 6만</span><span class="sxs-lookup"><span data-stu-id="5a72d-152">TimeOut (msec) = 60000</span></span>

<span data-ttu-id="5a72d-153">ABS 파일을 성공적으로 다운로드 함 https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span><span class="sxs-lookup"><span data-stu-id="5a72d-153">Successfully Downloaded the ABS file https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="5a72d-154">테스트가 실패 한 이유</span><span class="sxs-lookup"><span data-stu-id="5a72d-154">Reasons why the test might have failed</span></span>

<span data-ttu-id="5a72d-155">Test-CsAddressBookService 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5a72d-155">Here are some common reasons why Test-CsAddressBookService might fail:</span></span>

  - <span data-ttu-id="5a72d-156">잘못 된 사용자 계정을 지정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="5a72d-156">You specified an invalid user account.</span></span> <span data-ttu-id="5a72d-157">다음과 같은 명령을 실행 하 여 사용자 계정이 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a72d-157">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="5a72d-158">사용자 계정이 올바르지만 현재 Lync Server에 대해 계정이 사용 하도록 설정 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5a72d-158">The user account is valid, but the account is not currently enabled for Lync Server.</span></span> <span data-ttu-id="5a72d-159">사용자 계정이 Lync Server에 대해 사용 하도록 설정 되었는지 확인 하려면 다음과 같은 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a72d-159">To verify that a user account has been enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="5a72d-160">Enabled 속성을 False로 설정 하면 사용자가 현재 Lync Server를 사용 하도록 설정 되지 않은 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5a72d-160">If the Enabled property is set to False that means that the user is not currently enabled for Lync Server.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5a72d-161">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5a72d-161">See Also</span></span>


[<span data-ttu-id="5a72d-162">테스트-CsAddressBookService</span><span class="sxs-lookup"><span data-stu-id="5a72d-162">Test-CsAddressBookService</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

