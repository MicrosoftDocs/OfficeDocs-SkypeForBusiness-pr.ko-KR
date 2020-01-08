---
title: 'Lync Server 2013: 음성 정책에 대해 전화 번호 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test telephone number against a voice policy
ms:assetid: 30c51700-17c6-4c57-891a-8d5ec30b50ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725207(v=OCS.15)
ms:contentKeyID: 63969596
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a7a1e24a07a0f6e1e985c9fc42f7468838074d3a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984098"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-telephone-number-against-a-voice-policy-in-lync-server-2013"></a><span data-ttu-id="7a712-102">Lync Server 2013에서 음성 정책에 대해 전화 번호 테스트</span><span class="sxs-lookup"><span data-stu-id="7a712-102">Test telephone number against a voice policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7a712-103">_**마지막으로 수정한 주제:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="7a712-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7a712-104">확인 일정</span><span class="sxs-lookup"><span data-stu-id="7a712-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="7a712-105">월간</span><span class="sxs-lookup"><span data-stu-id="7a712-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a712-106">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="7a712-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="7a712-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7a712-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a712-108">권한이 필요 함</span><span class="sxs-lookup"><span data-stu-id="7a712-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="7a712-109">Lync Server Management Shell을 사용 하 여 로컬에서 실행 되는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a712-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="7a712-110">Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 CsVoicePolicy cmdlet을 실행 하는 데 필요한 권한이 있는 RBAC 역할을 사용자에 게 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a712-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoicePolicy cmdlet.</span></span> <span data-ttu-id="7a712-111">이 cmdlet을 사용할 수 있는 모든 RBAC 역할 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a712-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoicePolicy&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="7a712-112">설명</span><span class="sxs-lookup"><span data-stu-id="7a712-112">Description</span></span>

<span data-ttu-id="7a712-113">기업 음성 사용자는 다음 세 가지 사항에 따라 대규모의 PSTN (공개 통신 네트워크) 힌지 (hinge)를 통해 나가는 전화 통화를 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a712-113">The ability of Enterprise Voice users to make outgoing phone calls over the Public Switched Telephone network (PSTN) hinges, in large part, on three things:</span></span>

  - <span data-ttu-id="7a712-114">사용자에 게 할당 된 음성 정책.</span><span class="sxs-lookup"><span data-stu-id="7a712-114">The voice policy assigned to the user.</span></span>

  - <span data-ttu-id="7a712-115">Lync Server에서 PSTN 네트워크로 통화를 라우팅하는 데 사용 되는 음성 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="7a712-115">The voice routes used to route calls from Lync Server to the PSTN network.</span></span>

  - <span data-ttu-id="7a712-116">PSTN 사용으로 음성 경로를 음성에 연결 하는 Lync Server 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="7a712-116">The PSTN usage, a Lync Server property that connects a voice policy to a voice route.</span></span>

<span data-ttu-id="7a712-117">PSTN 사용은 특히 중요 한 음성 정책에 음성 경로를 연결 하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="7a712-117">The PSTN usage is especially important: it’s the property that connects a voice policy to a voice route.</span></span> <span data-ttu-id="7a712-118">(음성 정책 및 음성 경로는 하나 이상의 PSTN 사용량이 공통으로 있는 경우 연결 되었다고 말합니다.) 음성 정책은 PSTN 사용을 지정 하지 않고 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a712-118">(A voice policy and a voice route are said to be connected if they have at least one PSTN usage in common.) Voice policies can be configured without specifying a PSTN usage.</span></span> <span data-ttu-id="7a712-119">이 경우 해당 정책을 할당 받은 사용자는 PSTN 네트워크를 통해 발신 전화를 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7a712-119">In that case, users who were assigned that policy won't be able to make outgoing calls over the PSTN network.</span></span> <span data-ttu-id="7a712-120">마찬가지로, 하나 이상의 지정 된 PSTN 사용이 없는 음성 경로는 PSTN 네트워크로 전화를 라우팅할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7a712-120">Likewise, voice routes that do not have at least one specified PSTN usage will be unable to route calls to the PSTN network.</span></span>

<span data-ttu-id="7a712-121">CsVoicePolicy cmdlet은 지정 된 음성 정책에 PSTN 사용이 있는지 확인 하 고 하나 이상의 음성 경로에 따라 사용이 공유 되는지 여부를 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a712-121">The Test-CsVoicePolicy cmdlet verifies that a given voice policy has a PSTN usage and that the usage is shared by at least one voice route.</span></span> <span data-ttu-id="7a712-122">테스트를 CsVoicePolicy에서 실행 하는 경우 cmdlet은 발견 한 첫 번째 유효한 음성 경로의 이름을 보고 하 고 정책을 경로에 연결 하는 PSTN 사용의 이름을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a712-122">If the verification run by Test-CsVoicePolicy succeeds, the cmdlet will report back the name of the first valid voice route it finds, and also the name of the PSTN usage that connects the policy to the route.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="7a712-123">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="7a712-123">Running the test</span></span>

<span data-ttu-id="7a712-124">테스트 CsVoicePolicy cmdlet을 실행 하려면 먼저 Get-CsVoicePolicy cmdlet을 사용 하 여 테스트할 음성 정책의 인스턴스를 검색 해야 합니다. 그런 다음 해당 인스턴스를 테스트-CsVoicePolicy로 파이프라인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a712-124">To run the Test-CsVoicePolicy cmdlet you must first use the Get-CsVoicePolicy cmdlet retrieve an instance of the voice policy to be tested; that instance must then be piped to Test-CsVoicePolicy.</span></span> <span data-ttu-id="7a712-125">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7a712-125">For example:</span></span>

`Get-CsVoicePolicy -Identity "Global" | Test-CsVoicePolicy -TargetNumber "+12065551219"`

<span data-ttu-id="7a712-126">이 명령은 CsVoicePolicy를 사용 하 여 음성 정책 인스턴스를 검색 하지 않으므로 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a712-126">Note that this command, which does not use Get-CsVoicePolicy to retrieve a voice policy instance, will fail:</span></span>

`Test-CsVoicePolicy -TargetNumber "+12065551219" -VoicePolicy "Global"`

<span data-ttu-id="7a712-127">지정 된 전화 번호에 대 한 모든 음성 정책을 확인 하려면 다음과 같은 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a712-127">If you want to check all the voice policies against a specified phone number then use a command similar to this:</span></span>

`Get-CsVoicePolicy | Test-CsVoicePolicy -TargetNumber "+12065551219"`

<span data-ttu-id="7a712-128">TargetNumber는 E 164 형식을 사용 하 여 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a712-128">Note that the TargetNumber must be specified by using the E.164 format.</span></span> <span data-ttu-id="7a712-129">CsVoicePolicy 형식으로 전화 번호를 정규화 하거나 번역 하는 것은 테스트를 시도 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7a712-129">Test-CsVoicePolicy won't attempt to normalize or translate phone numbers into the E.164 format.</span></span>

<span data-ttu-id="7a712-130">자세한 내용은 테스트 CsVoicePolicy cmdlet에 대 한 도움말 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7a712-130">For more information, see the Help documentation for the Test-CsVoicePolicy cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="7a712-131">성공 또는 실패 확인</span><span class="sxs-lookup"><span data-stu-id="7a712-131">Determining success or failure</span></span>

<span data-ttu-id="7a712-132">음성 정책에서 일치 하는 음성 경로와 일치 하는 PSTN 사용을 찾을 수 있는 경우 경로와 사용이 모두 화면에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a712-132">If the voice policy can find both a matching voice route and a matching PSTN usage, then both the route and the usage will be displayed on-screen:</span></span>

<span data-ttu-id="7a712-133">FirstMatchingRoute MatchingUsage</span><span class="sxs-lookup"><span data-stu-id="7a712-133">FirstMatchingRoute MatchingUsage</span></span>

<span data-ttu-id="7a712-134">\------------------ -------------</span><span class="sxs-lookup"><span data-stu-id="7a712-134"></span></span>

<span data-ttu-id="7a712-135">RedmondVoiceRoute RedmondPstnUsage</span><span class="sxs-lookup"><span data-stu-id="7a712-135">RedmondVoiceRoute RedmondPstnUsage</span></span>

<span data-ttu-id="7a712-136">적절 한 음성 경로 또는 적절 한 PSTN 사용을 찾을 수 없는 경우 빈 속성 값이 화면에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a712-136">If either an appropriate voice route or an appropriate PSTN usage cannot be found then blank property values will be displayed on-screen:</span></span>

<span data-ttu-id="7a712-137">FirstMatchingRoute MatchingUsage</span><span class="sxs-lookup"><span data-stu-id="7a712-137">FirstMatchingRoute MatchingUsage</span></span>

<span data-ttu-id="7a712-138">\------------------ -------------</span><span class="sxs-lookup"><span data-stu-id="7a712-138"></span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="7a712-139">테스트가 실패할 수 있는 이유</span><span class="sxs-lookup"><span data-stu-id="7a712-139">Reasons why the test might have failed</span></span>

<span data-ttu-id="7a712-140">테스트-CsVoicePolicy가 일치 하는 항목을 반환 하지 않으면 음성 정책에서 음성 경로를 사용 하 여 PSTN 사용을 공유 하지 않는다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="7a712-140">If Test-CsVoicePolicy does not return a match that could mean that the voice policy does not share a PSTN usage with a voice route.</span></span> <span data-ttu-id="7a712-141">이를 확인 하려면 다음과 같은 cmdlet을 사용 하 여 음성 정책에 할당 된 PSTN 사용량을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a712-141">To verify that, use a cmdlet similar to the following to verify that PSTN usages assigned to the voice policy:</span></span>

`Get-CsVoicePolicy -Identity "Global" | Select-Object PstnUsages | Format-List`

<span data-ttu-id="7a712-142">다음으로이 명령을 실행 하 여 각 음성 경로에 대 한 PSTN 용도 할당을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a712-142">Next, run this command to determine the PSTN usages assign to each of your voice routes:</span></span>

`Get-CsVoiceRoute | Select-Object Identity, PstnUsages`

<span data-ttu-id="7a712-143">일치 하는 항목이 표시 되는 경우 (즉, 음성 경로에 하나 이상의 PSTN 사용량을 공유 하는 하나 이상의 음성 경로가 표시 되는 경우) CsVoiceRoute cmdlet을 실행 하 여 음성 경로가 제공 된 전화 번호로 전화를 걸 수 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a712-143">If you see any matches (that is, if you see one or more voice routes that share at least one PSTN usage with your voice policy), you should then run the Test-CsVoiceRoute cmdlet to verify that the voice route can dial the supplied phone number.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7a712-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7a712-144">See Also</span></span>


[<span data-ttu-id="7a712-145">테스트-CsVoicePolicy</span><span class="sxs-lookup"><span data-stu-id="7a712-145">Test-CsVoicePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoicePolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

