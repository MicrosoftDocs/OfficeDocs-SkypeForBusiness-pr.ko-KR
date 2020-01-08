---
title: 'Lync Server 2013: 타사 오디오 회의 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing third-party audio conferencing
ms:assetid: 0428eb2f-a5ce-47e5-9ea4-383965dfc1e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727299(v=OCS.15)
ms:contentKeyID: 63969576
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1c23f65015dd34f5efbaafa8472466394caa52c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983607"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-third-party-audio-conferencing-in-lync-server-2013"></a><span data-ttu-id="55060-102">Lync Server 2013에서 타사 오디오 회의 테스트</span><span class="sxs-lookup"><span data-stu-id="55060-102">Testing third-party audio conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="55060-103">_**마지막으로 수정한 주제:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="55060-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="55060-104">확인 일정</span><span class="sxs-lookup"><span data-stu-id="55060-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="55060-105">Daily</span><span class="sxs-lookup"><span data-stu-id="55060-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55060-106">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="55060-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="55060-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="55060-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55060-108">권한이 필요 함</span><span class="sxs-lookup"><span data-stu-id="55060-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="55060-109">Lync Server Management Shell을 사용 하 여 로컬에서 실행 되는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55060-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="55060-110">Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 CsAudioConferencingProvider cmdlet을 실행 하는 데 필요한 권한이 있는 RBAC 역할을 사용자에 게 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55060-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsAudioConferencingProvider cmdlet.</span></span> <span data-ttu-id="55060-111">이 cmdlet을 사용할 수 있는 모든 RBAC 역할 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="55060-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAudioConferencingProvider&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="55060-112">설명</span><span class="sxs-lookup"><span data-stu-id="55060-112">Description</span></span>

<span data-ttu-id="55060-113">오디오 회의 공급자는 조직에서 회의 서비스를 제공 하는 타사 회사입니다.</span><span class="sxs-lookup"><span data-stu-id="55060-113">An audio conferencing provider is a third-party company that provides organizations with conferencing services.</span></span> <span data-ttu-id="55060-114">다른 요인 중에서 오디오 회의 공급자는 사용자를 사이트 외부에 배치 하 고 회사 네트워크나 인터넷에 연결 되지 않은 상태에서 컨퍼런스 또는 모임의 오디오 부분에 참가할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="55060-114">Among other things, audio conferencing providers enable users located off site, and not connected to the corporate network or the Internet, to participate in the audio portion of a conference or meeting.</span></span> <span data-ttu-id="55060-115">오디오 회의 공급자는 live 번역, 기록, 실시간 컨퍼런스 연산자 지원과 같은 고급 서비스를 제공 하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="55060-115">Audio conferencing providers often provide high-end services such as live translation, transcription, and live per-conference operator assistance.</span></span>

<span data-ttu-id="55060-116">**CsAudioConferencingProvider** cmdlet은 사용자가 자신의 오디오 회의 공급자에 연결할 수 있는지 여부를 확인 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55060-116">The **Test-CsAudioConferencingProvider** cmdlet is used to verify that a user is able to make a connection to his or her audio conferencing provider.</span></span> <span data-ttu-id="55060-117">이 cmdlet은 다음 두 가지 방법 중 하나로 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55060-117">Note that this cmdlet can be run in one of two ways.</span></span> <span data-ttu-id="55060-118">대부분의 관리자는 CsHealthMonitoringConfiguration cmdlet을 사용 하 여 각 등록자 풀에 대 한 테스트 사용자를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="55060-118">Many administrators will use the CsHealthMonitoringConfiguration cmdlets to set up test users for each of their Registrar pools.</span></span> <span data-ttu-id="55060-119">이러한 테스트 사용자는 가상 트랜잭션과 함께 사용 하도록 미리 구성한 사용자 계정 쌍을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="55060-119">These test users represent a pair of user accounts that have been preconfigured for use with synthetic transactions.</span></span> <span data-ttu-id="55060-120">일반적으로 이러한 계정은 테스트 계정이 며 실제 사용자에 속하는 계정이 아닙니다. 테스트 사용자가 풀에 대해 구성 되어 있는 경우 관리자는 테스트에 관련 된 사용자 계정에 대 한 id를 지정 (및 자격 증명 제공) 할 필요 없이 해당 풀에 대해 **CsAudioConferencingProvider** cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55060-120">(Typically these are test accounts and not accounts that belong to actual users.) If test users are configured for a pool, administrators can run the **Test-CsAudioConferencingProvider** cmdlet against that pool without having to specify the identity of (and supply the credentials for) the user account involved in the test.</span></span>

<span data-ttu-id="55060-121">또는 관리자가 실제 사용자 계정을 사용 하 여 **CsAudioConferencingProvider** cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55060-121">Alternatively, administrators can run the **Test-CsAudioConferencingProvider** cmdlet using an actual user account.</span></span> <span data-ttu-id="55060-122">실제 사용자 계정을 사용 하 여 테스트를 수행 하기로 결정 한 경우 해당 계정에 대 한 로그온 이름과 암호를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55060-122">If you decide to conduct the test using an actual user account you will need to supply the logon name and password for that account.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="55060-123">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="55060-123">Running the test</span></span>

<span data-ttu-id="55060-124">예제 1에서는 풀 atl-cs-001.litwareinc.com에 대해 정의 된 테스트 사용자가 자신의 오디오 회의 공급자에 연결할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="55060-124">Example 1 checks to see if a test user defined for the pool atl-cs-001.litwareinc.com is able to connect to his or her audio conferencing provider.</span></span> <span data-ttu-id="55060-125">이 명령을 사용 하려면 풀에 대해 하나 이상의 테스트 사용자를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55060-125">This command requires that at least one test user be defined for the pool.</span></span> <span data-ttu-id="55060-126">Atl-cs-001.litwareinc.com에 대해 정의 된 테스트 사용자가 없는 경우 명령이 실패 합니다. 이는 테스트에서 **CsAudioConferencingProvider** cmdlet이 테스트에 어떤 사용자를 사용 해야 하는지 알 수 없기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="55060-126">If no test users have been defined for atl-cs-001.litwareinc.com, then the command will fail; that's because the **Test-CsAudioConferencingProvider** cmdlet will not know which user to employ in the test.</span></span> <span data-ttu-id="55060-127">풀에 대 한 테스트 사용자를 정의 하지 않은 경우 오디오 회의 공급자와의 연결을 확인할 때 명령에 사용할 사용자 계정의 자격 증명과 UserSipAddress 매개 변수를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55060-127">If you have not defined test users for a pool, then you must include the UserSipAddress parameter and the credentials of the user account that the command should employ when verifying the connection with an audio conferencing provider.</span></span>

    Test-CsAudioConferencingProvider -TargetFqdn atl-cs-001.litwareinc.com 

<span data-ttu-id="55060-128">예제 2에 표시 된 명령은 특정 사용자 (litwareinc\\kenmyer)가 자신의 오디오 회의 공급자에 연결 하는 기능을 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="55060-128">The commands shown in Example 2 test the ability of a specific user (litwareinc\\kenmyer) to connect to his audio conferencing provider.</span></span> <span data-ttu-id="55060-129">이렇게 하려면이 예제의 첫 번째 명령은 Get-Credential cmdlet을 사용 하 여 사용자: 진구 Myer의 이름 및 암호를 포함 하는 Windows PowerShell 명령줄 인터페이스 자격 증명 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="55060-129">To do this, the first command in the example uses the Get-Credential cmdlet to create a Windows PowerShell command-line interface credentials object containing the name and password of the user Ken Myer.</span></span> <span data-ttu-id="55060-130">(로그온 이름 litwareinc\\kenmyer 매개 변수로 포함 되어 있기 때문에 Windows PowerShell 자격 증명 요청 대화 상자에는 관리자만: 진구 Myer 계정에 대 한 암호를 입력 해야 합니다.) 결과 자격 증명 개체는 $credential 라는 변수에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55060-130">(Because the logon name litwareinc\\kenmyer has been included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Ken Myer account.) The resulting credentials object is stored in a variable named $credential.</span></span>

<span data-ttu-id="55060-131">두 번째 명령은이 사용자가 오디오 회의 공급자에 연결할 수 있는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="55060-131">The second command then checks to see if this user can connect to his audio conferencing provider.</span></span> <span data-ttu-id="55060-132">이 작업을 수행 하기 위해 CsAudioConferencingProvider cmdlet이 세 가지 매개 변수 (TargetFqdn (등록자 풀의 FQDN)와 함께 호출 됩니다. UserCredential (: 진구 Myer의 사용자 자격 증명을 포함 하는 Windows PowerShell 개체) 및 UserSipAddress (제공 된 사용자 자격 증명에 해당 하는 SIP 주소).</span><span class="sxs-lookup"><span data-stu-id="55060-132">To carry out this task, the Test-CsAudioConferencingProvider cmdlet is called, along with three parameters: TargetFqdn (the FQDN of the Registrar pool); UserCredential (the Windows PowerShell object containing Ken Myer's user credentials); and UserSipAddress (the SIP address corresponding to the supplied user credentials).</span></span>

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsAudioConferencingProvider -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="55060-133">성공 또는 실패 확인</span><span class="sxs-lookup"><span data-stu-id="55060-133">Determining success or failure</span></span>

<span data-ttu-id="55060-134">오디오 회의 공급자가 올바르게 구성 되 면 다음과 비슷한 출력이 표시 되 고 결과 속성이 성공으로 표시 됩니다 **.**</span><span class="sxs-lookup"><span data-stu-id="55060-134">If the audio conferencing provider is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="55060-135">대상 Fqdn: atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="55060-135">Target Fqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="55060-136">결과: 성공</span><span class="sxs-lookup"><span data-stu-id="55060-136">Result : Success</span></span>

<span data-ttu-id="55060-137">대기 시간: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="55060-137">Latency : 00:00:00</span></span>

<span data-ttu-id="55060-138">오류 메시지:</span><span class="sxs-lookup"><span data-stu-id="55060-138">Error Message :</span></span>

<span data-ttu-id="55060-139">있게</span><span class="sxs-lookup"><span data-stu-id="55060-139">Diagnosis :</span></span>

<span data-ttu-id="55060-140">지정 된 사용자가 로그온 하거나 로그 오프할 수 없는 경우에는 결과가 **오류로**표시 되 고 다음과 같은 오류 및 진단 속성에 추가 정보가 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55060-140">If the specified user can't log on or log off, the Result will be shown as a **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="55060-141">대상 Fqdn: atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="55060-141">Target Fqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="55060-142">결과: 실패</span><span class="sxs-lookup"><span data-stu-id="55060-142">Result : Failure</span></span>

<span data-ttu-id="55060-143">대기 시간: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="55060-143">Latency : 00:00:00</span></span>

<span data-ttu-id="55060-144">오류 메시지: 10060, 연결 된 파티 때문에 연결 시도가 실패 했습니다.</span><span class="sxs-lookup"><span data-stu-id="55060-144">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="55060-145">일정 시간 후에 제대로 응답 하지 않았거나</span><span class="sxs-lookup"><span data-stu-id="55060-145">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="55060-146">연결 된 호스트가 다음 연결에 실패 하 여 성립</span><span class="sxs-lookup"><span data-stu-id="55060-146">established connection failed because connected host has</span></span>

<span data-ttu-id="55060-147">2001:4898 \[: e8: f39e: 5c9a: ad83:81b3:9944\]: 5061에 응답 하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="55060-147">failed to respond \[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="55060-148">내부 예외: 다음 이유로 인해 연결 시도가 실패 했습니다.</span><span class="sxs-lookup"><span data-stu-id="55060-148">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="55060-149">연결 된 상대방이 일정 기간 후에 적절 하 게 응답 하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="55060-149">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="55060-150">연결 된 호스트 때문에 시간이 나 연결에 실패 했습니다.</span><span class="sxs-lookup"><span data-stu-id="55060-150">time, or established connection failed because connected host</span></span>

<span data-ttu-id="55060-151">님이 응답 하지 못했습니다</span><span class="sxs-lookup"><span data-stu-id="55060-151">has failed to respond</span></span>

<span data-ttu-id="55060-152">\[2001:4898: e8: f39e: 5c9a: ad83:81b3:9944\]: 5061</span><span class="sxs-lookup"><span data-stu-id="55060-152">\[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="55060-153">있게</span><span class="sxs-lookup"><span data-stu-id="55060-153">Diagnosis :</span></span>

<span data-ttu-id="55060-154">예를 들어 이전 출력에는 일반적으로 Edge 서버에 문제가 있음을 나타내는 "연결 된 파티가 제대로 응답 하지 않았습니다." 메모가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55060-154">For example, the previous output includes the note “the connected party did not properly respond” That typically indicates a problem with the Edge Server.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="55060-155">테스트가 실패할 수 있는 이유</span><span class="sxs-lookup"><span data-stu-id="55060-155">Reasons why the test might have failed</span></span>

<span data-ttu-id="55060-156">**테스트 CsAudioConferencingProvider** 가 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="55060-156">Here are some common reasons why **Test-CsAudioConferencingProvider** might fail:</span></span>

  - <span data-ttu-id="55060-157">잘못 된 매개 변수 값이 제공 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="55060-157">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="55060-158">앞의 예제에서와 같이 선택적 매개 변수를 올바르게 구성 하거나 테스트에 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="55060-158">As shown in the previous example, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="55060-159">선택적 매개 변수 없이 명령을 다시 실행 하 여 성공 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="55060-159">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="55060-160">CsAudioConferencingProvider cmdlet이 **사용** 하는 사용자에 게 오디오 회의 공급자가 지정 되지 않은 경우 테스트에 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="55060-160">Note that the test will fail if the user employed by the **Test-CsAudioConferencingProvider** cmdlet has not been assigned an audio conferencing provider.</span></span>

  - <span data-ttu-id="55060-161">Edge 서버가 잘못 구성 되었거나 아직 배포 되지 않은 경우에는이 명령이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="55060-161">This command will fail if the Edge Server is misconfigured or not yet deployed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

