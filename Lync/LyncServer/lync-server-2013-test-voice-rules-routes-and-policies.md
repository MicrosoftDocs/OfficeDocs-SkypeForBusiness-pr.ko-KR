---
title: 'Lync Server 2013: 음성 규칙, 경로 및 정책 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test voice rules, routes, and policies
ms:assetid: ebb9c3fa-6950-4311-87ca-e1ecd9280a43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725213(v=OCS.15)
ms:contentKeyID: 63969661
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bbf04728db30bada37e43f14b33420ede1ce9258
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194361"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-voice-rules-routes-and-policies-in-lync-server-2013"></a><span data-ttu-id="42e31-102">Lync Server 2013에서 음성 규칙, 경로 및 정책 테스트</span><span class="sxs-lookup"><span data-stu-id="42e31-102">Test voice rules, routes, and policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="42e31-103">_**마지막으로 수정 된 항목:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="42e31-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="42e31-104">확인 일정</span><span class="sxs-lookup"><span data-stu-id="42e31-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="42e31-105">월간</span><span class="sxs-lookup"><span data-stu-id="42e31-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42e31-106">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="42e31-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="42e31-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="42e31-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42e31-108">필요한 권한</span><span class="sxs-lookup"><span data-stu-id="42e31-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="42e31-109">Lync Server 관리 셸을 사용 하 여 로컬로 실행 하는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="42e31-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="42e31-110">Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 CsVoiceUser cmdlet을 실행 하는 권한이 있는 RBAC 역할을 사용자에 게 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="42e31-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoiceUser cmdlet.</span></span> <span data-ttu-id="42e31-111">이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="42e31-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceUser&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="42e31-112">설명</span><span class="sxs-lookup"><span data-stu-id="42e31-112">Description</span></span>

<span data-ttu-id="42e31-113">사용자가 전화를 걸 때 통화가 목적지에 도달 하기 위해 수행 하는 경로는 해당 사용자에 게 할당 된 정책 및 다이얼 플랜에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="42e31-113">When a user makes a phone call, the route the call takes to reach its destination depends on both the policies and dial plans assigned to that user.</span></span> <span data-ttu-id="42e31-114">사용자의 SIP 주소와 전화 번호를 지정 하면 CsVoiceUser cmdlet은 해당 번호에 대 한 통화를 완료할 수 있는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="42e31-114">Given a user’s SIP address and a phone number, the Test-CsVoiceUser cmdlet verifies whether the user in question can complete a call to that number.</span></span> <span data-ttu-id="42e31-115">테스트에 성공 하면 CsVoiceUser에서 다음을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="42e31-115">If the test succeeds, Test-CsVoiceUser returns the following:</span></span>

  - <span data-ttu-id="42e31-116">사용자의 다이얼 플랜에 따라 E. 164 형식으로 변환 되는 숫자입니다.</span><span class="sxs-lookup"><span data-stu-id="42e31-116">The number translated to E.164 format (based on the user’s dial plan)</span></span>

  - <span data-ttu-id="42e31-117">해당 변환을 제공한 정규화 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="42e31-117">The normalization rule that supplied that translation</span></span>

  - <span data-ttu-id="42e31-118">경로 우선 순위에 따라 사용 되는 음성 경로</span><span class="sxs-lookup"><span data-stu-id="42e31-118">The voice route used (based on route priority);</span></span>

  - <span data-ttu-id="42e31-119">사용자의 음성 정책을 음성 경로에 연결한 전화 사용입니다.</span><span class="sxs-lookup"><span data-stu-id="42e31-119">The phone usage that linked the user’s voice policy to the voice route.</span></span>

<span data-ttu-id="42e31-120">CsVoiceUser를 사용 하면 특정 전화 번호가 예상 대로 경로 지정 되 고 변환 되는지 여부를 확인 하 고 개별 사용자가 경험 하는 통화 관련 문제를 해결 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42e31-120">Test-CsVoiceUser enables you to determine whether a specific phone number will route and translate as expected, and can help troubleshoot call-related problems that are experienced by individual users.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="42e31-121">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="42e31-121">Running the test</span></span>

<span data-ttu-id="42e31-122">CsVoiceUser cmdlet을 실행 하는 경우 전화를 거는 번호 (DialedNumber) 및 테스트할 사용자 계정의 Id 라는 두 가지 정보를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="42e31-122">When running the Test-CsVoiceUser cmdlet you must supply two pieces of information: the number being dialed (DialedNumber) and the Identity of the user account being tested.</span></span> <span data-ttu-id="42e31-123">예를 들어이 명령은 SIP 주소 sip:kenmyer@litwareinc.com 사용자가 전화 번호 + 1206555-1219에 대 한 호출을 수행 하도록 하는 기능을 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="42e31-123">For example, this command tests the ability of the user who has the SIP address sip:kenmyer@litwareinc.com to make a call to the phone number +1206555-1219:</span></span>

`Test-CsVoiceUser -DialedNumber "12065551219" -SipUri "sip:kenmyer@litwareinc.com"`

<span data-ttu-id="42e31-124">전화 번호를 지정 하는 방법에 맞는 형식으로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="42e31-124">The phone number should be formatted in the way that you expect it to be dialed.</span></span> <span data-ttu-id="42e31-125">예를 들어 사용자가 시외 전화를 걸기 전에 1을 전화를 걸지 않으면 다음 형식을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="42e31-125">For example, if users typically do not dial the 1 before placing a long distance call then you should use this format:</span></span>

`-DialedNumber "2065551219"`

<span data-ttu-id="42e31-126">물론이 경우 숫자 2065551219을 Lync Server에서 사용 되는 E. 164 전화 형식으로 올바르게 변환할 수 있는 정규화 규칙이 없는 경우에는 테스트가 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="42e31-126">Of course, in that case, the test will fail if you do not have a normalization rule that can correctly translate the number 2065551219 into the E.164 telephone format that is used by Lync Server.</span></span> <span data-ttu-id="42e31-127">자세한 내용은 Get-csvoicenormalizationrule cmdlet에 대 한 도움말 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="42e31-127">For more information, see the help topic New-CsVoiceNormalizationRule cmdlet.</span></span>

<span data-ttu-id="42e31-128">각 사용자 계정에 대해 이와 동일한 테스트를 실행 하려는 경우에는 다음과 같은 명령을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42e31-128">If you want to run this same test against each of your user accounts, you can use a command similar to the following:</span></span>

`Get-CsUser | ForEach-Object {$_.DisplayName; Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri $_.SipAddress} | Format-List`

<span data-ttu-id="42e31-129">자세한 내용은 CsVoiceUser cmdlet에 대 한 도움말 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="42e31-129">For more information, see the Help documentation for the Test-CsVoiceUser cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="42e31-130">성공 또는 실패 확인</span><span class="sxs-lookup"><span data-stu-id="42e31-130">Determining success or failure</span></span>

<span data-ttu-id="42e31-131">테스트가 성공적으로 완료 되 면 (즉, 사용자가 지정 된 번호로 전화를 걸 수 있는 경우) 출력에는 변환 된 전화 번호와 일치 하는 정규화 규칙 및 음성 경로와 같은 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="42e31-131">If the test is completed successfully (that is, if the user can make a phone call to the specified number), the output will show information like the translated phone number and the matching normalization rule and voice route:</span></span>

<span data-ttu-id="42e31-132">TranslatedNumber    MatchingRule    FirstMatchingRoute    MatchingUsage</span><span class="sxs-lookup"><span data-stu-id="42e31-132">TranslatedNumber    MatchingRule    FirstMatchingRoute    MatchingUsage</span></span>

<span data-ttu-id="42e31-133">\----------------    ------------    ------------------    -------------</span><span class="sxs-lookup"><span data-stu-id="42e31-133">\----------------    ------------    ------------------    -------------</span></span>

<span data-ttu-id="42e31-134">\+12065551219 Descripti    LocalRoute 로컬</span><span class="sxs-lookup"><span data-stu-id="42e31-134">\+12065551219        Descripti...    LocalRoute            Local</span></span>

<span data-ttu-id="42e31-135">Windows PowerShell 화면의 제한 사항으로 인해 적어도 일부 반환 된 정보 (일치 하는 정규화 규칙에 대 한 전체 설명)가 화면에 표시 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42e31-135">Because of the limitations of the Windows PowerShell screen, at least some returned information (most notably the full description of the matching normalization rule) might not appear on-screen.</span></span> <span data-ttu-id="42e31-136">테스트의 성공 또는 실패에만 관심이 있는 경우에는 문제가 없는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="42e31-136">If you are only interested in the success or failure of the test, then this might not matter.</span></span> <span data-ttu-id="42e31-137">반환 된 데이터에 대 한 자세한 내용을 보려면 테스트를 실행할 때 Format cmdlet에 출력을 파이프 합니다.</span><span class="sxs-lookup"><span data-stu-id="42e31-137">If you would prefer to see the full details of the returned data then pipe the output to the Format-List cmdlet when running the test:</span></span>

`Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri "sip:kenmyer@litwareinc.com" -Verbose | Format-List`

<span data-ttu-id="42e31-138">그러면 다음과 같은 읽기 쉬운 형식으로 출력을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42e31-138">That will display the output in a more reader-friendly format:</span></span>

<span data-ttu-id="42e31-139">TranslatedNumber: + 12065551219</span><span class="sxs-lookup"><span data-stu-id="42e31-139">TranslatedNumber : +12065551219</span></span>

<span data-ttu-id="42e31-140">MatchingRule: Description =; Pattern = ^ (\\d{11}) $; 번역 = + $1,</span><span class="sxs-lookup"><span data-stu-id="42e31-140">MatchingRule : Description=;Pattern=^(\\d{11})$;Translation=+$1;</span></span>

<span data-ttu-id="42e31-141">Name = All 접두사, IsInternalExtension = False</span><span class="sxs-lookup"><span data-stu-id="42e31-141">Name=Prefix All;IsInternalExtension=False</span></span>

<span data-ttu-id="42e31-142">FirsMatchingRoute: LocalRoute</span><span class="sxs-lookup"><span data-stu-id="42e31-142">FirsMatchingRoute : LocalRoute</span></span>

<span data-ttu-id="42e31-143">MatchingUsage: Local</span><span class="sxs-lookup"><span data-stu-id="42e31-143">MatchingUsage : Local</span></span>

<span data-ttu-id="42e31-144">테스트가 실패 하면 CsVoiceUser에서 빈 속성 값 집합을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="42e31-144">If the test fails, Test-CsVoiceUser will return an empty set of property values:</span></span>

<span data-ttu-id="42e31-145">TranslatedNumber MatchingRule FirstMatchingRoute MatchingUsage</span><span class="sxs-lookup"><span data-stu-id="42e31-145">TranslatedNumber MatchingRule FirstMatchingRoute MatchingUsage</span></span>

<span data-ttu-id="42e31-146">\---------------- ------------ ------------------ -------------</span><span class="sxs-lookup"><span data-stu-id="42e31-146">\---------------- ------------ ------------------ -------------</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="42e31-147">테스트가 실패 한 이유</span><span class="sxs-lookup"><span data-stu-id="42e31-147">Reasons why the test might have failed</span></span>

<span data-ttu-id="42e31-148">CsVoiceUser cmdlet이 실패 하는 이유에는 여러 가지가 있습니다. 제공 된 전화 번호를 변환할 수 있는 정규화 규칙이 없을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42e31-148">There are any number of reasons why the Test-CsVoiceUser cmdlet might fail: there might not be a normalization rule that can translate the provided phone number.</span></span> <span data-ttu-id="42e31-149">음성 경로에 문제가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42e31-149">There could be problems with the voice route.</span></span> <span data-ttu-id="42e31-150">해당 사용자에 게 할당 된 다이얼 플랜에 대 한 구성 문제가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42e31-150">There could be a configuration issue with the dial plan assigned to the user in question.</span></span> <span data-ttu-id="42e31-151">따라서 CsVoiceUser cmdlet을 실행 하는 경우 Verbose 매개 변수를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42e31-151">Because of that, you might want to include the Verbose parameter when you are running the Test-CsVoiceUser cmdlet:</span></span>

`Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri "sip:kenmyer@litwareinc.com" -Verbose`

<span data-ttu-id="42e31-152">자세한 정보 표시 cmdlet이 포함 된 경우 CsVoiceUser에서는 검사를 수행할 때 수행 되는 모든 단계의 자세한 계정을 발급 합니다.</span><span class="sxs-lookup"><span data-stu-id="42e31-152">When the Verbose cmdlet is included, Test-CsVoiceUser will issue a detailed account of all the steps in takes when conducting its checks.</span></span> <span data-ttu-id="42e31-153">예를 들어 다음과 같은 단계를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42e31-153">For example, you might see steps similar to these:</span></span> 

<span data-ttu-id="42e31-154">VERBOSE: id가 "sip:kenmyer@litwareinc.com" 인 사용자 찾기</span><span class="sxs-lookup"><span data-stu-id="42e31-154">VERBOSE: Locating user with identity "sip:kenmyer@litwareinc.com"</span></span>

<span data-ttu-id="42e31-155">VERBOSE: 다이얼 플랜 로드: "RedmondDialPlan"</span><span class="sxs-lookup"><span data-stu-id="42e31-155">VERBOSE: Loading dial plan: "RedmondDialPlan"</span></span>

<span data-ttu-id="42e31-156">이 추가 정보는 오류의 원인을 정확 하 게 파악 하기 위해 수행할 수 있는 단계에 대 한 힌트를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42e31-156">This additional information can provide hints as to the steps that you can take to pinpoint the cause of the failure.</span></span> <span data-ttu-id="42e31-157">예를 들어 여기에 표시 된 자세한 정보 출력은 테스트 중인 사용자에 게 다이얼 플랜 RedmondDialPlan이 할당 되었음을 알려 줍니다.</span><span class="sxs-lookup"><span data-stu-id="42e31-157">For example, the verbose output shown here tells us that the user being tested was assigned the dial plan RedmondDialPlan.</span></span> <span data-ttu-id="42e31-158">테스트가 실패 한 후에는 RedmondDialPlan에서 제공 된 전화 번호를 변환할 수 있는지 확인 하는 논리적 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="42e31-158">If the test has failed, one logical next step would be to verify that RedmondDialPlan can translate the supplied phone number.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="42e31-159">참고 항목</span><span class="sxs-lookup"><span data-stu-id="42e31-159">See Also</span></span>


[<span data-ttu-id="42e31-160">CsVoiceUser</span><span class="sxs-lookup"><span data-stu-id="42e31-160">Test-CsVoiceUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceUser)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

