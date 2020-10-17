---
title: 'Lync Server 2013: 음성 정책에 대해 전화 번호 테스트'
description: 'Lync Server 2013: 음성 정책에 대해 전화 번호를 테스트 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test telephone number against a voice policy
ms:assetid: 30c51700-17c6-4c57-891a-8d5ec30b50ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725207(v=OCS.15)
ms:contentKeyID: 63969596
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a6523e7657bd4c30c23909bb02e2569b6067298
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548034"
---
# <a name="test-telephone-number-against-a-voice-policy-in-lync-server-2013"></a><span data-ttu-id="94c10-103">Lync Server 2013의 음성 정책에 대해 전화 번호 테스트</span><span class="sxs-lookup"><span data-stu-id="94c10-103">Test telephone number against a voice policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="94c10-104">_**마지막으로 수정 된 항목:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="94c10-104">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="94c10-105">확인 일정</span><span class="sxs-lookup"><span data-stu-id="94c10-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="94c10-106">월간</span><span class="sxs-lookup"><span data-stu-id="94c10-106">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94c10-107">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="94c10-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="94c10-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="94c10-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="94c10-109">필요한 권한</span><span class="sxs-lookup"><span data-stu-id="94c10-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="94c10-110">Lync Server 관리 셸을 사용 하 여 로컬로 실행 하는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="94c10-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="94c10-111">Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 사용자에 게 Test-CsVoicePolicy cmdlet을 실행 하는 권한이 있는 RBAC 역할을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="94c10-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoicePolicy cmdlet.</span></span> <span data-ttu-id="94c10-112">이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="94c10-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoicePolicy&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="94c10-113">설명</span><span class="sxs-lookup"><span data-stu-id="94c10-113">Description</span></span>

<span data-ttu-id="94c10-114">Enterprise Voice 사용자가 다음 세 가지 작업을 통해 대규모의 PSTN (공중 전화망) 힌지를 통해 나가는 전화 통화를 수행할 수 있는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="94c10-114">The ability of Enterprise Voice users to make outgoing phone calls over the Public Switched Telephone network (PSTN) hinges, in large part, on three things:</span></span>

  - <span data-ttu-id="94c10-115">사용자에 게 할당 된 음성 정책</span><span class="sxs-lookup"><span data-stu-id="94c10-115">The voice policy assigned to the user.</span></span>

  - <span data-ttu-id="94c10-116">Lync Server에서 PSTN 네트워크로 통화를 라우팅하는 데 사용 되는 음성 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="94c10-116">The voice routes used to route calls from Lync Server to the PSTN network.</span></span>

  - <span data-ttu-id="94c10-117">PSTN 사용 (음성 정책을 음성 경로에 연결 하는 Lync Server 속성)입니다.</span><span class="sxs-lookup"><span data-stu-id="94c10-117">The PSTN usage, a Lync Server property that connects a voice policy to a voice route.</span></span>

<span data-ttu-id="94c10-118">PSTN 사용은 특히 중요 한 음성 정책을 음성 경로에 연결 하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="94c10-118">The PSTN usage is especially important: it’s the property that connects a voice policy to a voice route.</span></span> <span data-ttu-id="94c10-119">(음성 정책 및 음성 경로는 하나 이상의 PSTN 사용량이 공통으로 있는 경우 연결 되었다고 말합니다.) 음성 정책은 PSTN 사용을 지정 하지 않고 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94c10-119">(A voice policy and a voice route are said to be connected if they have at least one PSTN usage in common.) Voice policies can be configured without specifying a PSTN usage.</span></span> <span data-ttu-id="94c10-120">이 경우 해당 정책이 할당 된 사용자가 PSTN 네트워크를 통해 발신 전화를 걸 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="94c10-120">In that case, users who were assigned that policy won't be able to make outgoing calls over the PSTN network.</span></span> <span data-ttu-id="94c10-121">마찬가지로 지정 된 PSTN 사용량이 하나 이상 없는 음성 경로는 통화를 PSTN 네트워크로 라우팅할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="94c10-121">Likewise, voice routes that do not have at least one specified PSTN usage will be unable to route calls to the PSTN network.</span></span>

<span data-ttu-id="94c10-122">Test-CsVoicePolicy cmdlet은 지정 된 음성 정책에 PSTN 사용이 있는지와 사용 현황이 하나 이상의 음성 경로를 통해 공유 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="94c10-122">The Test-CsVoicePolicy cmdlet verifies that a given voice policy has a PSTN usage and that the usage is shared by at least one voice route.</span></span> <span data-ttu-id="94c10-123">Test-CsVoicePolicy에서 실행 하는 확인이 성공 하면 cmdlet은 찾은 첫 번째 유효한 음성 경로의 이름과 정책을 연결 하는 PSTN 사용의 이름을 해당 경로에 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="94c10-123">If the verification run by Test-CsVoicePolicy succeeds, the cmdlet will report back the name of the first valid voice route it finds, and also the name of the PSTN usage that connects the policy to the route.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="94c10-124">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="94c10-124">Running the test</span></span>

<span data-ttu-id="94c10-125">Test-CsVoicePolicy cmdlet을 실행 하려면 먼저 Get-CsVoicePolicy cmdlet을 사용 하 여 테스트할 음성 정책의 인스턴스를 검색 해야 합니다. 그런 다음 해당 인스턴스를 Set-csvoicepolicy으로 파이프 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="94c10-125">To run the Test-CsVoicePolicy cmdlet you must first use the Get-CsVoicePolicy cmdlet retrieve an instance of the voice policy to be tested; that instance must then be piped to Test-CsVoicePolicy.</span></span> <span data-ttu-id="94c10-126">예제:</span><span class="sxs-lookup"><span data-stu-id="94c10-126">For example:</span></span>

`Get-CsVoicePolicy -Identity "Global" | Test-CsVoicePolicy -TargetNumber "+12065551219"`

<span data-ttu-id="94c10-127">음성 정책 인스턴스를 검색 하는 데 Get-CsVoicePolicy를 사용 하지 않는이 명령은 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="94c10-127">Note that this command, which does not use Get-CsVoicePolicy to retrieve a voice policy instance, will fail:</span></span>

`Test-CsVoicePolicy -TargetNumber "+12065551219" -VoicePolicy "Global"`

<span data-ttu-id="94c10-128">지정 된 전화 번호에 대해 모든 음성 정책을 확인 하려면 다음과 같은 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="94c10-128">If you want to check all the voice policies against a specified phone number then use a command similar to this:</span></span>

`Get-CsVoicePolicy | Test-CsVoicePolicy -TargetNumber "+12065551219"`

<span data-ttu-id="94c10-129">TargetNumber는 E. 164 형식을 사용 하 여 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="94c10-129">Note that the TargetNumber must be specified by using the E.164 format.</span></span> <span data-ttu-id="94c10-130">Test-CsVoicePolicy는 전화 번호를 전자 164 형식으로 정규화 하거나 변환 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="94c10-130">Test-CsVoicePolicy won't attempt to normalize or translate phone numbers into the E.164 format.</span></span>

<span data-ttu-id="94c10-131">자세한 내용은 Test-CsVoicePolicy cmdlet에 대 한 도움말 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="94c10-131">For more information, see the Help documentation for the Test-CsVoicePolicy cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="94c10-132">성공 또는 실패 확인</span><span class="sxs-lookup"><span data-stu-id="94c10-132">Determining success or failure</span></span>

<span data-ttu-id="94c10-133">음성 정책이 일치 하는 음성 경로 및 일치 하는 PSTN 사용을 찾을 수 있으면 경로와 사용 현황이 모두 화면에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="94c10-133">If the voice policy can find both a matching voice route and a matching PSTN usage, then both the route and the usage will be displayed on-screen:</span></span>

<span data-ttu-id="94c10-134">FirstMatchingRoute MatchingUsage</span><span class="sxs-lookup"><span data-stu-id="94c10-134">FirstMatchingRoute MatchingUsage</span></span>

<span data-ttu-id="94c10-135">\------------------ -------------</span><span class="sxs-lookup"><span data-stu-id="94c10-135">\------------------ -------------</span></span>

<span data-ttu-id="94c10-136">RedmondVoiceRoute RedmondPstnUsage</span><span class="sxs-lookup"><span data-stu-id="94c10-136">RedmondVoiceRoute RedmondPstnUsage</span></span>

<span data-ttu-id="94c10-137">적절 한 음성 경로 또는 적절 한 PSTN 사용을 찾을 수 없는 경우 빈 속성 값이 화면에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="94c10-137">If either an appropriate voice route or an appropriate PSTN usage cannot be found then blank property values will be displayed on-screen:</span></span>

<span data-ttu-id="94c10-138">FirstMatchingRoute MatchingUsage</span><span class="sxs-lookup"><span data-stu-id="94c10-138">FirstMatchingRoute MatchingUsage</span></span>

<span data-ttu-id="94c10-139">\------------------ -------------</span><span class="sxs-lookup"><span data-stu-id="94c10-139">\------------------ -------------</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="94c10-140">테스트가 실패 한 이유</span><span class="sxs-lookup"><span data-stu-id="94c10-140">Reasons why the test might have failed</span></span>

<span data-ttu-id="94c10-141">Test-CsVoicePolicy에 대해 음성 정책이 음성 경로와 함께 PSTN 사용을 공유 하지 않을 것 이라는 것을 의미 하는 일치 항목을 반환 하지 않는 경우</span><span class="sxs-lookup"><span data-stu-id="94c10-141">If Test-CsVoicePolicy does not return a match that could mean that the voice policy does not share a PSTN usage with a voice route.</span></span> <span data-ttu-id="94c10-142">이를 확인 하려면 다음과 같은 cmdlet을 사용 하 여 음성 정책에 할당 된 PSTN 사용법을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="94c10-142">To verify that, use a cmdlet similar to the following to verify that PSTN usages assigned to the voice policy:</span></span>

`Get-CsVoicePolicy -Identity "Global" | Select-Object PstnUsages | Format-List`

<span data-ttu-id="94c10-143">다음으로, 다음 명령을 실행 하 여 각 음성 경로에 대 한 PSTN 사용 할당을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="94c10-143">Next, run this command to determine the PSTN usages assign to each of your voice routes:</span></span>

`Get-CsVoiceRoute | Select-Object Identity, PstnUsages`

<span data-ttu-id="94c10-144">일치 하는 항목이 표시 되는 경우 즉, 음성 정책을 사용 하 여 하나 이상의 음성 경로를 공유 하는 경우에는 Test-CsVoiceRoute cmdlet을 실행 하 여 음성 경로에서 제공 된 전화 번호로 전화를 걸 수 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="94c10-144">If you see any matches (that is, if you see one or more voice routes that share at least one PSTN usage with your voice policy), you should then run the Test-CsVoiceRoute cmdlet to verify that the voice route can dial the supplied phone number.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="94c10-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="94c10-145">See Also</span></span>


[<span data-ttu-id="94c10-146">Set-csvoicepolicy</span><span class="sxs-lookup"><span data-stu-id="94c10-146">Test-CsVoicePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoicePolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

