---
title: 'Lync Server 2013: PSTN 전화 통화 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing PSTN phone call
ms:assetid: dc7d319d-a627-45b6-a978-6111901251e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690133(v=OCS.15)
ms:contentKeyID: 63969656
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7c9c0b0441ea31e2419101aba188c33b0bbfd70
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193928"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-pstn-phone-call-in-lync-server-2013"></a><span data-ttu-id="f8aa2-102">Lync Server 2013에서 PSTN 전화 통화 테스트</span><span class="sxs-lookup"><span data-stu-id="f8aa2-102">Testing PSTN phone call in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8aa2-103">_**마지막으로 수정 된 항목:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="f8aa2-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f8aa2-104">확인 일정</span><span class="sxs-lookup"><span data-stu-id="f8aa2-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="f8aa2-105">매일</span><span class="sxs-lookup"><span data-stu-id="f8aa2-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8aa2-106">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="f8aa2-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="f8aa2-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f8aa2-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8aa2-108">필요한 권한</span><span class="sxs-lookup"><span data-stu-id="f8aa2-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="f8aa2-109">Lync Server 관리 셸을 사용 하 여 로컬로 실행 하는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8aa2-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="f8aa2-110">Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우, 사용자에 게는 CsRegistration cmdlet을 실행 하는 권한이 있는 RBAC 역할을 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8aa2-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsRegistration cmdlet.</span></span> <span data-ttu-id="f8aa2-111">이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8aa2-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPstnOutboundCall&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="f8aa2-112">설명</span><span class="sxs-lookup"><span data-stu-id="f8aa2-112">Description</span></span>

<span data-ttu-id="f8aa2-113">Test-cspstnoutboundcall cmdlet은 사용자가 PSTN에 있는 전화 번호로 전화를 걸 수 있는지 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8aa2-113">The Test-CsPstnOutboundCall cmdlet tests the ability of a user to make a call to a phone number located on the PSTN.</span></span> <span data-ttu-id="f8aa2-114">Test-cspstnoutboundcall를 실행 하면 cmdlet은 먼저 테스트 사용자를 Lync Server에 로그인 하려고 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8aa2-114">When you run Test-CsPstnOutboundCall, the cmdlet first attempts to log the test user on to Lync Server.</span></span> <span data-ttu-id="f8aa2-115">로그온에 성공 하면 cmdlet은 PSTN 게이트웨이에서 전화 통화를 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8aa2-115">If the logon succeeds, the cmdlet will then try to make a phone call across the PSTN gateway.</span></span> <span data-ttu-id="f8aa2-116">이 통화는 다이얼 플랜, 음성 정책 및 테스트 계정에 할당 된 기타 정책 및 설정을 사용 하 여 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8aa2-116">This phone call will be made using the dial plan, voice policy, and other policies and settings assigned to the test account.</span></span> <span data-ttu-id="f8aa2-117">통화가 응답 하면 cmdlet은 네트워크를 통해 DTMF (이중 톤 주파수) 코드를 보내 미디어 연결을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8aa2-117">When the call is answered, the cmdlet sends dual-tone multi-frequency (DTMF) codes over the network to verify media connectivity.</span></span>

<span data-ttu-id="f8aa2-118">이 테스트를 수행 하는 경우 Test-cspstnoutboundcall는 실제 전화 통화를 수행 합니다. 테스트를 성공적으로 수행 하려면 대상 전화가 울릴 것 이며 응답 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8aa2-118">When conducting its test, Test-CsPstnOutboundCall will make an actual phone call: the target phone will ring and must be answered for the test to succeed.</span></span> <span data-ttu-id="f8aa2-119">또한 관리자가이 통화를 수동으로 종료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8aa2-119">This call must also be manually ended by the administrator.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="f8aa2-120">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="f8aa2-120">Running the test</span></span>

<span data-ttu-id="f8aa2-121">Test-cspstnoutboundcall cmdlet은 미리 구성 된 테스트 계정 (Lync Server 테스트 실행을 위한 테스트 계정 설정 참조) 또는 Lync Server를 사용 하도록 설정 된 사용자의 계정 중 하나를 사용 하 여 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8aa2-121">The Test-CsPstnOutboundCall cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="f8aa2-122">테스트 계정을 사용 하 여이 검사를 실행 하려면 테스트할 Lync Server 풀의 FQDN과 호출 되는 PSTN 전화 번호를 지정 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8aa2-122">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested and the PSTN phone number being called.</span></span> <span data-ttu-id="f8aa2-123">예:</span><span class="sxs-lookup"><span data-stu-id="f8aa2-123">For example:</span></span>

    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219"

<span data-ttu-id="f8aa2-124">실제 사용자 계정을 사용 하 여이 검사를 실행 하려면 먼저 계정 이름과 암호가 포함 된 Windows PowerShell 자격 증명 개체를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8aa2-124">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="f8aa2-125">그런 다음 Test-cspstnoutboundcall를 호출 하면 해당 자격 증명 개체 및 해당 계정에 할당 된 SIP 주소를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8aa2-125">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsPstnOutboundCall:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="f8aa2-126">자세한 내용은 [test-cspstnoutboundcall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall) cmdlet에 대 한 도움말 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="f8aa2-126">For more information, see the Help documentation for the [Test-CsPstnOutboundCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="f8aa2-127">성공 또는 실패 확인</span><span class="sxs-lookup"><span data-stu-id="f8aa2-127">Determining success or failure</span></span>

<span data-ttu-id="f8aa2-128">지정 된 사용자가 전화를 걸 수 있고 통화에 응답 하는 경우 결과 속성이 Success로 표시 된 것과 비슷한 출력을 받게 됩니다 **.**</span><span class="sxs-lookup"><span data-stu-id="f8aa2-128">If the specified user can make the call, and if the call is answered, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="f8aa2-129">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f8aa2-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="f8aa2-130">결과: 성공</span><span class="sxs-lookup"><span data-stu-id="f8aa2-130">Result : Success</span></span>

<span data-ttu-id="f8aa2-131">대기 시간: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="f8aa2-131">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="f8aa2-132">오류</span><span class="sxs-lookup"><span data-stu-id="f8aa2-132">Error :</span></span>

<span data-ttu-id="f8aa2-133">진단을</span><span class="sxs-lookup"><span data-stu-id="f8aa2-133">Diagnosis :</span></span>

<span data-ttu-id="f8aa2-134">지정 된 사용자가 전화를 걸 수 없거나 호출에 응답 하지 않으면 결과가 실패로 표시 되 고 오류 및 진단 속성에 추가 정보가 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8aa2-134">If the specified user can't make the call or if the call is not answered, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="f8aa2-135">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f8aa2-135">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="f8aa2-136">결과: 실패</span><span class="sxs-lookup"><span data-stu-id="f8aa2-136">Result : Failure</span></span>

<span data-ttu-id="f8aa2-137">대기 시간: 00:00:0987365</span><span class="sxs-lookup"><span data-stu-id="f8aa2-137">Latency : 00:00:0987365</span></span>

<span data-ttu-id="f8aa2-138">오류: 403, 금지 됨</span><span class="sxs-lookup"><span data-stu-id="f8aa2-138">Error : 403, Forbidden</span></span>

<span data-ttu-id="f8aa2-139">진단: ErrorCode = 12001, Source = atl-cs-001-litwareinc, Reason = User</span><span class="sxs-lookup"><span data-stu-id="f8aa2-139">Diagnosis : ErrorCode=12001,Source=atl-cs-001.litwareinc.com,Reason=User</span></span>

<span data-ttu-id="f8aa2-140">정책에 전화 경로 사용이 포함 되지 않음</span><span class="sxs-lookup"><span data-stu-id="f8aa2-140">Policy does not contain phone route usage</span></span>

<span data-ttu-id="f8aa2-141">위 출력에서는 지정 된 사용자에 게 할당 된 음성 정책에 전화 사용이 포함 되지 않아 테스트가 실패 했다는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f8aa2-141">The previous output states that the test failed because the voice policy assigned to the specified user does not include a phone usage.</span></span> <span data-ttu-id="f8aa2-142">전화 용도가 음성 경로에 음성 정책을 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8aa2-142">(Phone usages tie voice policies to voice routes.</span></span> <span data-ttu-id="f8aa2-143">음성 정책 및 해당 하는 음성 경로가 둘 다 없으면 PSTN을 통해 전화를 걸 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f8aa2-143">Without both a voice policy and a corresponding voice route you can't make calls over the PSTN.)</span></span>

<span data-ttu-id="f8aa2-144">Test-cspstnoutboundcall에 오류가 발생 한 경우에는 다음 시간에 Verbose 매개 변수를 포함 하 여 테스트를 다시 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8aa2-144">If Test-CsPstnOutboundCall fails then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219" -Verbose

<span data-ttu-id="f8aa2-145">Verbose 매개 변수가 포함 된 경우 Test-cspstnoutboundcall는 지정 된 사용자가 Lync Server에 로그온 할 수 있는지 확인할 때 시도한 각 작업의 단계별 계정을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8aa2-145">When the Verbose parameter is included, Test-CsPstnOutboundCall will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="f8aa2-146">예를 들어 다음 출력은 네트워크 문제로 인해 PSTN과의 연결이 차단 됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f8aa2-146">For example, this output indicates that network problems are preventing a connection with the PSTN:</span></span>

<span data-ttu-id="f8aa2-147">오디오 화상 통화를 ' sip: + 12065551219@litwareinc .com, user = phone '으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8aa2-147">Establishing Audio Video call to 'sip:+12065551219@litwareinc.com;user=phone'.</span></span>

<span data-ttu-id="f8aa2-148">네트워크에서 404 (찾을 수 없음) 응답이 수신 되었으며 작업에 실패 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f8aa2-148">An exception 'A 404 (Not Found) response was received from the network and the operation failed.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="f8aa2-149">테스트가 실패 한 이유</span><span class="sxs-lookup"><span data-stu-id="f8aa2-149">Reasons why the test might have failed</span></span>

<span data-ttu-id="f8aa2-150">다음은 Test-cspstnoutboundcall에서 오류가 발생할 수 있는 몇 가지 일반적인 이유입니다.</span><span class="sxs-lookup"><span data-stu-id="f8aa2-150">Here are some common reasons why Test-CsPstnOutboundCall might fail:</span></span>

  - <span data-ttu-id="f8aa2-151">잘못 된 사용자 계정을 지정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f8aa2-151">You specified an invalid user account.</span></span> <span data-ttu-id="f8aa2-152">다음과 같은 명령을 실행 하 여 사용자 계정이 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8aa2-152">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="f8aa2-153">사용자 계정이 올바르지만 해당 계정이 Lync Server에 대해 현재 사용 하도록 설정 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f8aa2-153">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="f8aa2-154">사용자 계정이 Lync Server에 대해 사용 하도록 설정 되어 있는지 확인 하려면 다음과 같은 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8aa2-154">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="f8aa2-155">Enabled 속성을 False로 설정 하면 사용자가 현재 Lync Server를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f8aa2-155">If the Enabled property is set to False that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="f8aa2-156">지정 된 사용자에 게 할당 된 음성 정책에 유효한 PSTN 사용이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f8aa2-156">The voice policy assigned to the specified user does not have a valid PSTN usage.</span></span> <span data-ttu-id="f8aa2-157">다음과 같은 명령을 사용 하 여 사용자에 게 할당 된 음성 정책을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8aa2-157">You can determine the voice policy that is assigned to a user by using a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object VoicePolicy
    
    <span data-ttu-id="f8aa2-158">그런 다음 사용자별 음성 정책 RedmondVoicePolicy에 대 한 정보를 검색 하는 다음과 같은 명령을 사용 하 여 해당 정책에 할당 된 PSTN 사용 (있는 경우)을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8aa2-158">And then you can determine the PSTN usages (if any) that are assigned to that policy by using a command similar to the following, which retrieves information about the per-user voice policy RedmondVoicePolicy:</span></span>
    
        Get-CsVoicePolicy -Identity "RedmondVoicePolicy"

</div>

</div>

<span> </span>

</div>

</div>

</div>

