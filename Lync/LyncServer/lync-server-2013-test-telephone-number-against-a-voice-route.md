---
title: 'Lync Server 2013: 음성 경로에 대 한 전화 번호 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test telephone number against a voice route
ms:assetid: 9a77ed6d-9394-4bef-9344-3d91b6959b97
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725211(v=OCS.15)
ms:contentKeyID: 63969631
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3fccdcb5dfc0fe52c2c0dcf80f7f6a374e35a39e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "41985073"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-telephone-number-against-a-voice-route-in-lync-server-2013"></a><span data-ttu-id="75eee-102">Lync Server 2013에서 음성 경로에 대 한 전화 번호 테스트</span><span class="sxs-lookup"><span data-stu-id="75eee-102">Test telephone number against a voice route in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="75eee-103">_**마지막으로 수정 된 항목:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="75eee-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="75eee-104">확인 일정</span><span class="sxs-lookup"><span data-stu-id="75eee-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="75eee-105">월간</span><span class="sxs-lookup"><span data-stu-id="75eee-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75eee-106">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="75eee-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="75eee-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="75eee-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75eee-108">필요한 권한</span><span class="sxs-lookup"><span data-stu-id="75eee-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="75eee-109">Lync Server 관리 셸을 사용 하 여 로컬로 실행 하는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75eee-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="75eee-110">Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 Get-csvoiceroute cmdlet을 실행 하는 권한이 있는 RBAC 역할을 사용자에 게 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75eee-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoiceRoute cmdlet.</span></span> <span data-ttu-id="75eee-111">이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="75eee-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceRoute&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="75eee-112">설명</span><span class="sxs-lookup"><span data-stu-id="75eee-112">Description</span></span>

<span data-ttu-id="75eee-113">음성 경로는 회사 음성 통화를 PSTN 네트워크로 라우팅하기 위해 음성 정책과 함께 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="75eee-113">Voice routes work together with voice policies to help route Enterprise Voice calls to the PSTN network.</span></span> <span data-ttu-id="75eee-114">각 음성 경로에는 지정 된 음성 경로를 통해 라우팅되는 전화 번호를 식별 하는 정규식 (숫자 패턴)이 포함 됩니다. 경로는이 정규식과 일치 하는 전화 번호를 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75eee-114">Each voice route includes a regular expression (a number pattern) that identifies the phone numbers that will be routed through a given voice route: the route will be able to handle any phone numbers that match this regular expression.</span></span> <span data-ttu-id="75eee-115">예를 들어 음성 경로에는 10 자리 숫자를 처리할 수 있는 정규식이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75eee-115">For example, a voice route might have a regular expression that enables it to handle any 10-digit number.</span></span> <span data-ttu-id="75eee-116">즉, 경로는 다음과 같은 전화 번호를 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75eee-116">That means the route would be able to handle a phone number such as this:</span></span>

  - <span data-ttu-id="75eee-117">2065551219</span><span class="sxs-lookup"><span data-stu-id="75eee-117">2065551219</span></span>

<span data-ttu-id="75eee-118">경로는 다음 두 숫자 중에서 하나를 처리할 수 없으며 이러한 값은 10 자리 숫자이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="75eee-118">The route would not be able to handle either of the following two numbers, neither of which has 10 digits:</span></span>

  - <span data-ttu-id="75eee-119">5551219</span><span class="sxs-lookup"><span data-stu-id="75eee-119">5551219</span></span>

  - <span data-ttu-id="75eee-120">12065551219</span><span class="sxs-lookup"><span data-stu-id="75eee-120">12065551219</span></span>

<span data-ttu-id="75eee-121">Get-csvoiceroute cmdlet은 지정한 음성 경로에서 지정 된 전화 번호를 라우트할 수 있는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="75eee-121">The Test-CsVoiceRoute cmdlet verifies whether a given voice route can route a specified phone number.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="75eee-122">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="75eee-122">Running the test</span></span>

<span data-ttu-id="75eee-123">음성 경로에서 지정 된 전화 번호를 라우팅하는 기능이 두 단계로 진행 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="75eee-123">Verifying the ability of a voice route to route a specified phone number is a two-step process.</span></span> <span data-ttu-id="75eee-124">먼저 Get-csvoiceroute cmdlet을 사용 하 여 해당 음성 경로의 인스턴스를 반환한 다음 Get-csvoiceroute cmdlet을 사용 하 여 해당 경로의 대상 전화 번호를 처리할 수 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75eee-124">First you have to use the Get-CsVoiceRoute cmdlet to return an instance of that voice route, and then you have to use the Test-CsVoiceRoute cmdlet to verify the ability of that route to handle the target phone number.</span></span> <span data-ttu-id="75eee-125">예를 들어이 명령은 RedmondVoiceRoute 음성 경로에서 전화 번호 2065551219를 라우팅할 수 있는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="75eee-125">For example, this command verifies whether the RedmondVoiceRoute voice route can route the phone number 2065551219:</span></span>

`Get-CsVoiceRoute -Identity "RedmondVoiceRoute" | Test-CsVoiceRoute -TargetNumber "2065551219"`

<span data-ttu-id="75eee-126">사용자가 전화를 걸 수 있는 것으로 예상 되는 전화 번호를 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75eee-126">Note that the phone number should be typed as you expect users to dial that number.</span></span> <span data-ttu-id="75eee-127">예를 들어 전화를 걸 때 국가 코드와 지역 번호를 포함 하지 않을 것으로 예상 되 면 다음과 같은 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="75eee-127">For example, if you do not expect users to include the country code and area code when dialing, then use syntax similar to this:</span></span>

`-TargetNumber "5551219"`

<span data-ttu-id="75eee-128">이 경우 대상 번호에 국가 코드와 지역 코드가 모두 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="75eee-128">In this case, the target number leaves out both the country code and the area code.</span></span>

<span data-ttu-id="75eee-129">단일 명령을 사용 하 여 지정 된 대상 번호에 대 한 모든 음성 경로를 테스트 하려면 다음과 같은 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="75eee-129">To use a single command to test all the voice routes against a specified target number, use syntax such as the following:</span></span>

`Get-CsVoiceRoute | Test-CsVoiceRoute -TargetNumber "2065551219"`

<span data-ttu-id="75eee-130">자세한 내용은 Get-csvoiceroute cmdlet에 대 한 도움말 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="75eee-130">For more information, see the Help documentation for the Test-CsVoiceRoute cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="75eee-131">성공 또는 실패 확인</span><span class="sxs-lookup"><span data-stu-id="75eee-131">Determining success or failure</span></span>

<span data-ttu-id="75eee-132">음성 경로에서 대상 전화 번호를 라우팅할 수 있는 경우 Get-csvoiceroute cmdlet은 True 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="75eee-132">If the voice route can route the target phone number the Test-CsVoiceRoute cmdlet just returns the value True:</span></span>

<span data-ttu-id="75eee-133">MatchesPattern</span><span class="sxs-lookup"><span data-stu-id="75eee-133">MatchesPattern</span></span>

\--------------

<span data-ttu-id="75eee-134">참</span><span class="sxs-lookup"><span data-stu-id="75eee-134">True</span></span>

<span data-ttu-id="75eee-135">즉, 경로는 대상 번호와 비슷한 숫자를 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75eee-135">That means that route can handle numbers similar to the target number.</span></span> <span data-ttu-id="75eee-136">음성 경로에서 대상 번호를 처리할 수 없는 경우 Get-csvoiceroute는 False 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="75eee-136">If the voice route is can't handle the target number then Test-CsVoiceRoute returns the value False:</span></span>

<span data-ttu-id="75eee-137">MatchesPattern</span><span class="sxs-lookup"><span data-stu-id="75eee-137">MatchesPattern</span></span>

\--------------

<span data-ttu-id="75eee-138">False</span><span class="sxs-lookup"><span data-stu-id="75eee-138">False</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="75eee-139">테스트가 실패 한 이유</span><span class="sxs-lookup"><span data-stu-id="75eee-139">Reasons why the test might have failed</span></span>

<span data-ttu-id="75eee-140">음성 경로를 테스트할 때는 "실패"가 상대 용어입니다.</span><span class="sxs-lookup"><span data-stu-id="75eee-140">When testing voice routes, “failure” is a relative term.</span></span> <span data-ttu-id="75eee-141">이 경우에는 경로가 "끊어짐;" 이라는 의미는 아니므로 경로에서 대상 번호를 처리할 수 없다는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="75eee-141">In this case, it doesn’t mean that the route is somehow “broken;” instead, it just means that the route can't handle the target number.</span></span> <span data-ttu-id="75eee-142">음성 경로가 잘못 구성 되었기 때문일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75eee-142">That could be because the voice route was configured incorrectly.</span></span> <span data-ttu-id="75eee-143">또한 경로는이 패턴을 사용 하 여 숫자를 처리 하도록 의도 된 것이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="75eee-143">It could also mean that the route was never intended to handle numbers using this pattern.</span></span> <span data-ttu-id="75eee-144">예를 들어 국가 코드를 포함 하는 모든 전화 번호를 거부 하도록 경로 지정 된 경로를 통해 다른 국가에 대 한 통화를 라우팅 하지 않으려는 경우</span><span class="sxs-lookup"><span data-stu-id="75eee-144">For example, if you do not want to route calls to other countries over a given route that route might be configured to reject all phone numbers that include a country code.</span></span> <span data-ttu-id="75eee-145">Get-csvoiceroute가 True를 반환 하는 경우 False가 반환 되 면 대상 번호를 올바르게 입력 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="75eee-145">If Test-CsVoiceRoute returns False when you expected it to return True, verify that you typed the target number in correctly.</span></span> <span data-ttu-id="75eee-146">이 경우에는 다음과 같은 명령을 사용 하 여 경로에 대해 구성 된 번호 패턴을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="75eee-146">If you did, then use a command similar to this one to view the NumberPattern configured for the route:</span></span>

`Get-CsVoiceRoute -Identity "RedmondVoiceRoute" | Select-Object NumberPattern`

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="75eee-147">참고 항목</span><span class="sxs-lookup"><span data-stu-id="75eee-147">See Also</span></span>


[<span data-ttu-id="75eee-148">Get-csvoiceroute</span><span class="sxs-lookup"><span data-stu-id="75eee-148">Test-CsVoiceRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceRoute)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

