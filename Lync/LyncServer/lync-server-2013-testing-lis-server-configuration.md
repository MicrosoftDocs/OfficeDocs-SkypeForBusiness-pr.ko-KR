---
title: 'Lync Server 2013: LIS Server 구성 테스트'
description: 'Lync Server 2013: LIS 서버 구성을 테스트 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing LIS server configuration
ms:assetid: 6b06e7ab-522f-41a2-878b-e89cd4e3c6da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690129(v=OCS.15)
ms:contentKeyID: 63969614
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba4d16d2ce48e3e5bb89e863f02902d05ce77bd7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560614"
---
# <a name="testing-lis-server-configuration-in-lync-server-2013"></a><span data-ttu-id="ba0e4-103">Lync Server 2013에서 LIS 서버 구성 테스트</span><span class="sxs-lookup"><span data-stu-id="ba0e4-103">Testing LIS server configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ba0e4-104">_**마지막으로 수정 된 항목:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="ba0e4-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba0e4-105">확인 일정</span><span class="sxs-lookup"><span data-stu-id="ba0e4-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="ba0e4-106">매일</span><span class="sxs-lookup"><span data-stu-id="ba0e4-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba0e4-107">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="ba0e4-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="ba0e4-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ba0e4-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba0e4-109">필요한 권한</span><span class="sxs-lookup"><span data-stu-id="ba0e4-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="ba0e4-110">Lync Server 관리 셸을 사용 하 여 로컬로 실행 하는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba0e4-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="ba0e4-111">Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 사용자에 게 Test-CsLisConfiguration cmdlet을 실행 하는 권한이 있는 RBAC 역할을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba0e4-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsLisConfiguration cmdlet.</span></span> <span data-ttu-id="ba0e4-112">이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba0e4-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLisConfiguration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="ba0e4-113">설명</span><span class="sxs-lookup"><span data-stu-id="ba0e4-113">Description</span></span>

<span data-ttu-id="ba0e4-114">Test-CsLisConfiguration cmdlet은 LIS 웹 서비스에 연결할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba0e4-114">The Test-CsLisConfiguration cmdlet verifies your ability to contact the LIS web service.</span></span> <span data-ttu-id="ba0e4-115">웹 서비스에 연결할 수 있으면 특정 위치를 찾을 수 있는지 여부에 관계 없이 테스트가 성공으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba0e4-115">If the web service can be contacted, then the test will be considered a success, regardless of whether any specific locations can be found.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="ba0e4-116">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="ba0e4-116">Running the test</span></span>

<span data-ttu-id="ba0e4-117">Test-CsLisConfguration cmdlet은 미리 구성 된 테스트 계정 (Lync Server 테스트 실행을 위한 테스트 계정 설정 참조) 또는 Lync Server를 사용 하도록 설정 된 사용자의 계정 중 하나를 사용 하 여 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba0e4-117">The Test-CsLisConfguration cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="ba0e4-118">테스트 계정을 사용 하 여이 검사를 실행 하려면 테스트할 Lync Server 풀의 FQDN만 지정 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba0e4-118">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="ba0e4-119">예제:</span><span class="sxs-lookup"><span data-stu-id="ba0e4-119">For example:</span></span>

    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="ba0e4-120">실제 사용자 계정을 사용 하 여이 검사를 실행 하려면 먼저 계정 이름과 암호가 포함 된 Windows PowerShell 자격 증명 개체를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba0e4-120">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="ba0e4-121">그런 다음 Export-cslisconfiguration를 호출 하면 해당 자격 증명 개체 및 해당 계정에 할당 된 SIP 주소를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba0e4-121">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsLisConfiguration:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="ba0e4-122">자세한 내용은 [export-cslisconfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsLisConfiguration) cmdlet에 대 한 도움말 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ba0e4-122">For more information, see the Help documentation for the [Test-CsLisConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsLisConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="ba0e4-123">성공 또는 실패 확인</span><span class="sxs-lookup"><span data-stu-id="ba0e4-123">Determining success or failure</span></span>

<span data-ttu-id="ba0e4-124">LIS가 올바르게 구성 된 경우 결과 속성이 Success로 표시 된 것과 비슷한 출력을 받게 됩니다 **.**</span><span class="sxs-lookup"><span data-stu-id="ba0e4-124">If the LIS is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="ba0e4-125">TargetUri https://atl-cs-001.litwareinc.com:443/locationinformation/</span><span class="sxs-lookup"><span data-stu-id="ba0e4-125">TargetUri : https://atl-cs-001.litwareinc.com:443/locationinformation/</span></span>

<span data-ttu-id="ba0e4-126">liservice .svc</span><span class="sxs-lookup"><span data-stu-id="ba0e4-126">liservice.svc</span></span>

<span data-ttu-id="ba0e4-127">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ba0e4-127">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="ba0e4-128">결과: 성공</span><span class="sxs-lookup"><span data-stu-id="ba0e4-128">Result : Success</span></span>

<span data-ttu-id="ba0e4-129">대기 시간: 00:00:06.1616913</span><span class="sxs-lookup"><span data-stu-id="ba0e4-129">Latency : 00:00:06.1616913</span></span>

<span data-ttu-id="ba0e4-130">오류</span><span class="sxs-lookup"><span data-stu-id="ba0e4-130">Error :</span></span>

<span data-ttu-id="ba0e4-131">진단을</span><span class="sxs-lookup"><span data-stu-id="ba0e4-131">Diagnosis :</span></span>

<span data-ttu-id="ba0e4-132">지정 된 사용자가 로그온 하거나 로그 오프할 수 없으면 결과가 실패로 표시 되 고 오류 및 진단 속성에 추가 정보가 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba0e4-132">If the specified user can't log on or log off, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="ba0e4-133">TargetUri</span><span class="sxs-lookup"><span data-stu-id="ba0e4-133">TargetUri :</span></span>

<span data-ttu-id="ba0e4-134">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ba0e4-134">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="ba0e4-135">결과: 실패</span><span class="sxs-lookup"><span data-stu-id="ba0e4-135">Result : Failure</span></span>

<span data-ttu-id="ba0e4-136">대기 시간: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="ba0e4-136">Latency : 00:00:00</span></span>

<span data-ttu-id="ba0e4-137">오류: 11004, 요청한 이름이 올바르지만 요청 된 데이터가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ba0e4-137">Error : 11004, The requested name is valid but no data of the requested</span></span>

<span data-ttu-id="ba0e4-138">형식이 발견 됨</span><span class="sxs-lookup"><span data-stu-id="ba0e4-138">type was found</span></span>

<span data-ttu-id="ba0e4-139">진단을</span><span class="sxs-lookup"><span data-stu-id="ba0e4-139">Diagnosis :</span></span>

<span data-ttu-id="ba0e4-140">Test-CsLisConfiguration: 토폴로지에서 일치 하는 클러스터를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ba0e4-140">Test-CsLisConfiguration : No matching cluster found in topology.</span></span>

<span data-ttu-id="ba0e4-141">예를 들어 위의 출력에는 "토폴로지에 일치 하는 클러스터가 없습니다." 라는 노트가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba0e4-141">For example, the previous output includes the note “No matching cluster found in topology.”</span></span> <span data-ttu-id="ba0e4-142">일반적으로에 지 서버에 문제가 있음을 나타내는 경우:에 지 서버를 사용 하 여 서비스 공급자에 연결 하 고 주소를 확인 하는 LIS입니다.</span><span class="sxs-lookup"><span data-stu-id="ba0e4-142">That typically indicates a problem with the Edge Server: the LIS using the Edge Server to connect to the service provider and validate addresses.</span></span>

<span data-ttu-id="ba0e4-143">Test-CsLisConfiguration 실패 하면 다음 시간에 Verbose 매개 변수를 포함 하 여 테스트를 다시 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba0e4-143">If Test-CsLisConfiguration fails then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="ba0e4-144">Verbose 매개 변수를 포함 하면 Test-CsLisConfiguration는 지정 된 사용자가 Lync Server에 로그온 할 수 있는지 확인할 때 시도한 각 작업의 단계별 계정을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba0e4-144">When the Verbose parameter is included, Test-CsLisConfiguration will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="ba0e4-145">예제:</span><span class="sxs-lookup"><span data-stu-id="ba0e4-145">For example:</span></span>

<span data-ttu-id="ba0e4-146">통화 위치 정보 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="ba0e4-146">Calling Location Information Service.</span></span>

<span data-ttu-id="ba0e4-147">서비스 경로 = https://atl-cs-001.litwareinc.com:443/locationinformation/liservice.svc</span><span class="sxs-lookup"><span data-stu-id="ba0e4-147">Service Path = https://atl-cs-001.litwareinc.com:443/locationinformation/liservice.svc</span></span>

<span data-ttu-id="ba0e4-148">Subnet =</span><span class="sxs-lookup"><span data-stu-id="ba0e4-148">Subnet =</span></span>

<span data-ttu-id="ba0e4-149">BssId = 5</span><span class="sxs-lookup"><span data-stu-id="ba0e4-149">BssId = 5</span></span>

<span data-ttu-id="ba0e4-150">ChassisId =</span><span class="sxs-lookup"><span data-stu-id="ba0e4-150">ChassisId =</span></span>

<span data-ttu-id="ba0e4-151">PortId =</span><span class="sxs-lookup"><span data-stu-id="ba0e4-151">PortId =</span></span>

<span data-ttu-id="ba0e4-152">PortIdSubType = 정의 되지 않은 형식</span><span class="sxs-lookup"><span data-stu-id="ba0e4-152">PortIdSubType = Undefined Type</span></span>

<span data-ttu-id="ba0e4-153">Mac</span><span class="sxs-lookup"><span data-stu-id="ba0e4-153">Mac</span></span>

<span data-ttu-id="ba0e4-154">응답 코드 Item400를 사용 하 여 예외 ' 위치 정보 웹 서비스 요청이 실패 했습니다.</span><span class="sxs-lookup"><span data-stu-id="ba0e4-154">An exception 'Location Information Web Service request has failed with a response code Item400.'</span></span> <span data-ttu-id="ba0e4-155">워크플로 SyntheticTrsnactions가 실행 되는 동안 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba0e4-155">occurred during Workflow Microsoft.Rtc.SyntheticTrsnactions.Workflows.STLisConfigurationWorkflow execution.</span></span>

<span data-ttu-id="ba0e4-156">이전 출력을 자세히 살펴보면 cmdlet이 위치 정보 서비스에 대 한 호출을 시도 하면 실패 한 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba0e4-156">If you examine the previous output closely, you’ll see that the cmdlet failed after it tried to call the Location Information Service.</span></span> <span data-ttu-id="ba0e4-157">이 통화에서 사용 된 매개 변수 중 하나는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ba0e4-157">One of the parameters that were used in that call was this:</span></span>

<span data-ttu-id="ba0e4-158">BssId = 5</span><span class="sxs-lookup"><span data-stu-id="ba0e4-158">BssId = 5</span></span>

<span data-ttu-id="ba0e4-159">이 값은 기본 BssID (서비스 집합 Id)에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ba0e4-159">That’s not a valid value for the Basic Service Set Identifier (BssID).</span></span> <span data-ttu-id="ba0e4-160">대신 BssID는 다음과 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba0e4-160">Instead, a BssID should resemble this:</span></span>

<span data-ttu-id="ba0e4-161">12-34-56-78-90-ab</span><span class="sxs-lookup"><span data-stu-id="ba0e4-161">12-34-56-78-90-ab</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="ba0e4-162">테스트가 실패 한 이유</span><span class="sxs-lookup"><span data-stu-id="ba0e4-162">Reasons why the test might have failed</span></span>

<span data-ttu-id="ba0e4-163">Test-CsLisConfiguration 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ba0e4-163">Here are some common reasons why Test-CsLisConfiguration might fail:</span></span>

  - <span data-ttu-id="ba0e4-164">잘못 된 매개 변수 값이 제공 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ba0e4-164">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="ba0e4-165">앞의 예제에 나와 있는 것 처럼 선택적 매개 변수를 올바르게 구성 해야 하며 그렇지 않으면 테스트가 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba0e4-165">As shown in the previous example, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="ba0e4-166">선택적 매개 변수 없이 명령을 다시 실행 하 여 성공 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba0e4-166">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

