---
title: 'Lync Server 2013: PSTN 피어 투 피어 통화 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing PSTN peer to peer call
ms:assetid: 7e128eef-9ada-49b4-940f-97d7d13f1e4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690131(v=OCS.15)
ms:contentKeyID: 63969622
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51b74697c7d6d5a037537bb036494d89264c4e75
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983040"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-pstn-peer-to-peer-call-in-lync-server-2013"></a><span data-ttu-id="67242-102">Lync Server 2013에서 PSTN 피어 투 피어 통화 테스트</span><span class="sxs-lookup"><span data-stu-id="67242-102">Testing PSTN peer to peer call in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="67242-103">_**마지막으로 수정한 주제:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="67242-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="67242-104">확인 일정</span><span class="sxs-lookup"><span data-stu-id="67242-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="67242-105">Daily</span><span class="sxs-lookup"><span data-stu-id="67242-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67242-106">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="67242-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="67242-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="67242-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67242-108">권한이 필요 함</span><span class="sxs-lookup"><span data-stu-id="67242-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="67242-109">Lync Server Management Shell을 사용 하 여 로컬에서 실행 되는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="67242-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="67242-110">Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 사용자는 테스트-CsPstnPeerToPeerCall cmdlet을 실행할 권한이 있는 RBAC 역할을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="67242-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsPstnPeerToPeerCall cmdlet.</span></span> <span data-ttu-id="67242-111">이 cmdlet을 사용할 수 있는 모든 RBAC 역할 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="67242-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPstnPeerToPeerCall&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="67242-112">설명</span><span class="sxs-lookup"><span data-stu-id="67242-112">Description</span></span>

<span data-ttu-id="67242-113">테스트-CsPstnPeerToPeerCall cmdlet은 사용자 쌍이 PSTN (공용 전환 통신 네트워크) 게이트웨이에서 피어 투 피어 통화를 수행 해야 하는 기능을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="67242-113">The Test-CsPstnPeerToPeerCall cmdlet verifies the ability a pair of users has to conduct a peer-to-peer call over the public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="67242-114">테스트-CsPstnPeerToPeerCall을 호출 하는 경우 cmdlet은 먼저 두 개의 테스트 사용자를 Lync Server에 로그인 하려고 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="67242-114">When you call Test-CsPstnPeerToPeerCall, the cmdlet will first attempt to log on two test users to Lync Server.</span></span> <span data-ttu-id="67242-115">로그온이 성공한 것으로 가정 하면 cmdlet은 사용자 1이 PSTN 게이트웨이에서 사용자 2를 호출 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="67242-115">Assuming that the logons succeed, the cmdlet will then have user 1 attempt to call user 2 over the PSTN gateway.</span></span> <span data-ttu-id="67242-116">테스트-CsPstnPeerToPeerCall은 다이얼 플랜, 음성 정책, 기타 정책 및 테스트 사용자에 게 할당 된 구성 설정을 사용 하 여이 통화를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="67242-116">Test-CsPstnPeerToPeerCall will make this call using the dial plan, voice policy, and other policy and configuration settings assigned to the test user.</span></span> <span data-ttu-id="67242-117">테스트가 계획 대로 진행 되는 경우 cmdlet은 사용자 2가 전화를 받을 수 있는지 확인 한 다음 시스템에서 두 테스트 계정을 모두 로그 오프 합니다.</span><span class="sxs-lookup"><span data-stu-id="67242-117">If the test goes as planned, the cmdlet will verify that user 2 was able to answer the call, and then log off both test accounts from the system.</span></span>

<span data-ttu-id="67242-118">테스트-CsPstnPeerToPeerCall은 연결을 설정할 수 있는지 확인 하 고 네트워크를 통해 DTMF 코드를 전송 하 여 연결을 통해 미디어를 보낼 수 있는지 여부를 확인 하는 실제 전화를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="67242-118">Test-CsPstnPeerToPeerCall makes an actual phone call, one that verifies that a connection can be made and that also transmits DTMF codes over the network to determine whether media can be sent over the connection.</span></span> <span data-ttu-id="67242-119">이 통화는 cmdlet 자체에 의해 응답 되며, 전화를 수동으로 종료할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="67242-119">The call is answered by the cmdlet itself, and no manual termination of the call is necessary.</span></span> <span data-ttu-id="67242-120">(즉, 아무도 전화를 건 후 통화를 종료 해야 합니다.)</span><span class="sxs-lookup"><span data-stu-id="67242-120">(That is, no one must answer and then hang up the phone that was called.)</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="67242-121">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="67242-121">Running the test</span></span>

<span data-ttu-id="67242-122">테스트-CsPstnPeerToPeerCall cmdlet은 미리 구성 된 테스트 계정 (Lync Server 테스트 실행을 위한 테스트 계정 설정 참조) 또는 Lync Server에 대해 사용 하도록 설정 된 두 사용자의 계정 중 하나를 사용 하 여 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67242-122">The Test-CsPstnPeerToPeerCall cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="67242-123">테스트 계정을 사용 하 여이 검사를 실행 하려면 테스트 중인 Lync Server 풀의 FQDN만 지정 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="67242-123">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="67242-124">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="67242-124">For example:</span></span>

`Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com"`

<span data-ttu-id="67242-125">실제 사용자 계정을 사용 하 여이 검사를 실행 하려면 각 계정에 대해 두 개의 Windows PowerShell 자격 증명 개체 (계정 이름과 암호를 포함 하는 개체)를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="67242-125">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="67242-126">그런 다음 테스트-CsPstnPeerToPeerCall을 호출할 때 다음과 같은 두 계정의 SIP 주소와 이러한 자격 증명 개체를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="67242-126">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsPstnPeerToPeerCall:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="67242-127">자세한 내용은 [테스트-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) cmdlet에 대 한 도움말 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="67242-127">For more information, see the Help documentation for the [Test-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="67242-128">성공 또는 실패 확인</span><span class="sxs-lookup"><span data-stu-id="67242-128">Determining success or failure</span></span>

<span data-ttu-id="67242-129">지정 된 사용자가 피어 투 피어 통화를 완료할 수 있는 경우 다음과 비슷한 출력을 받고 결과 속성이 성공으로 표시 됩니다 **.**</span><span class="sxs-lookup"><span data-stu-id="67242-129">If the specified users can complete a peer-to-peer call, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="67242-130">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="67242-130">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="67242-131">결과: 성공</span><span class="sxs-lookup"><span data-stu-id="67242-131">Result : Success</span></span>

<span data-ttu-id="67242-132">대기 시간: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="67242-132">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="67242-133">오류</span><span class="sxs-lookup"><span data-stu-id="67242-133">Error :</span></span>

<span data-ttu-id="67242-134">있게</span><span class="sxs-lookup"><span data-stu-id="67242-134">Diagnosis :</span></span>

<span data-ttu-id="67242-135">지정 된 사용자가 피어 투 피어 통화를 완료할 수 없는 경우 결과가 실패로 표시 되 고 오류 및 진단 속성에 추가 정보가 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="67242-135">If the specified users can't complete a peer-to-peer call, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="67242-136">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="67242-136">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="67242-137">결과: 실패</span><span class="sxs-lookup"><span data-stu-id="67242-137">Result : Failure</span></span>

<span data-ttu-id="67242-138">대기 시간: 00:00:0182361</span><span class="sxs-lookup"><span data-stu-id="67242-138">Latency : 00:00:0182361</span></span>

<span data-ttu-id="67242-139">오류: 403, 금지</span><span class="sxs-lookup"><span data-stu-id="67242-139">Error : 403, Forbidden</span></span>

<span data-ttu-id="67242-140">진단: ErrorCode = 12001, Source = atl-cs-001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="67242-140">Diagnosis : ErrorCode=12001,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="67242-141">이유 = 사용자 정책에 전화 경로 사용이 포함 되어 있지 않음</span><span class="sxs-lookup"><span data-stu-id="67242-141">Reason=User Policy does not contain phone route usage</span></span>

<span data-ttu-id="67242-142">이전 출력에서는 지정 된 사용자 중 한 명 이상에 게 할당 된 음성 정책에 전화 사용이 포함 되지 않아 테스트가 실패 했다는 것을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="67242-142">The previous output states that the test failed because the voice policy assigned to at least one of the specified users does not include a phone usage.</span></span> <span data-ttu-id="67242-143">(전화 사용은 음성 경로에 음성 정책을 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="67242-143">(Phone usages tie voice policies to voice routes.</span></span> <span data-ttu-id="67242-144">음성 정책 및 해당 하는 음성 경로를 모두 사용 하지 않으면 PSTN을 통해 전화를 걸 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="67242-144">Without both a voice policy and a corresponding voice route, you can't make calls over the PSTN.)</span></span>

<span data-ttu-id="67242-145">테스트-CsPstnPeerToPeerCall이 실패 하는 경우 다음과 같이 Verbose 매개 변수를 포함 하 여 테스트를 다시 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67242-145">If Test-CsPstnPeerToPeerCall fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="67242-146">Verbose 매개 변수가 포함 된 경우 테스트-CsPstnPeerToPeerCall은 지정 된 사용자가 Lync Server에 로그온 하는 기능을 확인할 때 시도한 각 작업에 대 한 단계별 계정을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="67242-146">When the Verbose parameter is included, Test-CsPstnPeerToPeerCall will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="67242-147">예를 들어 다음 출력은 네트워크 문제로 인해 PSTN과 연결 되지 않았음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="67242-147">For example, this output indicates that network problems are preventing a connection with the PSTN:</span></span>

<span data-ttu-id="67242-148">' Sip: + 12065551219@litwareinc .com, user = 휴대폰 '으로 오디오 영상 통화를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="67242-148">Establishing Audio Video call to 'sip:+12065551219@litwareinc.com;user=phone'.</span></span>

<span data-ttu-id="67242-149">네트워크에서 ' A 404 (찾을 수 없음) 응답이 수신 되어 작업이 실패 했습니다.</span><span class="sxs-lookup"><span data-stu-id="67242-149">An exception 'A 404 (Not Found) response was received from the network and the operation failed.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="67242-150">테스트가 실패할 수 있는 이유</span><span class="sxs-lookup"><span data-stu-id="67242-150">Reasons why the test might have failed</span></span>

<span data-ttu-id="67242-151">테스트-CsPstnPeerToPeerCall이 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="67242-151">Here are some common reasons why Test-CsPstnPeerToPeerCall might fail:</span></span>

  - <span data-ttu-id="67242-152">유효 하지 않은 사용자 계정을 지정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="67242-152">You specified a user account that is not valid.</span></span> <span data-ttu-id="67242-153">다음과 같은 명령을 실행 하 여 사용자 계정이 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67242-153">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="67242-154">사용자 계정이 올바르지만 현재 Lync Server에서 계정을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="67242-154">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="67242-155">Lync Server에 대해 사용자 계정이 설정 되어 있는지 확인 하려면 다음과 같은 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="67242-155">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="67242-156">Enabled 속성이 False로 설정 된 경우 사용자가 현재 Lync Server에 대해 사용 하도록 설정 되어 있지 않음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="67242-156">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="67242-157">지정 된 사용자에 게 할당 된 음성 정책에 유효한 PSTN 사용이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="67242-157">The voice policy assigned to the specified user does not have a valid PSTN usage.</span></span> <span data-ttu-id="67242-158">다음과 유사한 명령을 사용 하 여 사용자에 게 할당 된 음성 정책을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67242-158">You can determine the voice policy that is assigned to a user by using a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object VoicePolicy
    
    <span data-ttu-id="67242-159">그런 다음 사용자 단위 음성 정책 RedmondVoicePolicy에 대 한 정보를 검색 하는 다음과 유사한 명령을 사용 하 여 해당 정책에 할당 된 PSTN 사용 (있는 경우)을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67242-159">And then you can determine the PSTN usages (if any) that are assigned to that policy by using a command similar to the following, which retrieves information about the per-user voice policy RedmondVoicePolicy:</span></span>
    
        Get-CsVoicePolicy -Identity "RedmondVoicePolicy"

</div>

</div>

<span> </span>

</div>

</div>

</div>

