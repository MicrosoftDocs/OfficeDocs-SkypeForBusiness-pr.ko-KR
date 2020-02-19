---
title: 'Lync Server 2013: 음성 구성 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test voice configuration
ms:assetid: 574794a3-cb30-4762-bb62-3a68574f05e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725208(v=OCS.15)
ms:contentKeyID: 63969605
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f0d5c8aef7c3cca22a41f591a208413cc453898
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141574"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-voice-configuration-in-lync-server-2013"></a><span data-ttu-id="43774-102">Lync Server 2013에서 음성 구성 테스트</span><span class="sxs-lookup"><span data-stu-id="43774-102">Test voice configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="43774-103">_**마지막으로 수정 된 항목:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="43774-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="43774-104">확인 일정</span><span class="sxs-lookup"><span data-stu-id="43774-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="43774-105">월간</span><span class="sxs-lookup"><span data-stu-id="43774-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43774-106">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="43774-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="43774-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="43774-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43774-108">필요한 권한</span><span class="sxs-lookup"><span data-stu-id="43774-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="43774-109">Lync Server 관리 셸을 사용 하 여 로컬로 실행 하는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="43774-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="43774-110">Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 수정한 구성은 test-csvoicetestconfiguration cmdlet을 실행 하는 권한이 있는 RBAC 역할을 사용자에 게 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="43774-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoiceTestConfiguration cmdlet.</span></span> <span data-ttu-id="43774-111">이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="43774-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceTestConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="43774-112">설명</span><span class="sxs-lookup"><span data-stu-id="43774-112">Description</span></span>

<span data-ttu-id="43774-113">Lync Server에는 다양 한 Windows PowerShell cmdlet (예: Get-csvoiceroute 및 Set-csvoicepolicy, Get-cstrunkconfiguration)이 포함 되어 있으므로 엔터프라이즈 음성 인프라의 개별 부분이 있는지 확인할 수 있습니다.-음성 경로, 음성 정책, SIP 트렁크-정상적으로 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="43774-113">Lync Server includes several Windows PowerShell cmdlets (such as Test-CsVoiceRoute and Test-CsVoicePolicy, Test-CsTrunkConfiguration) that enable you to verify that the individual pieces of your Enterprise Voice infrastructure – voice routes, voice policies, SIP trunks – are working as expected.</span></span>

<span data-ttu-id="43774-114">Enterprise Voice에서는 모든 개별 작업을 수행 하는 것이 중요 하지만, 유효한 음성 경로, 유효한 음성 정책 및 유효한 SIP 트렁크를 사용할 수 있지만 사용자는 여전히 전화를 걸거나 받을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="43774-114">While it’s important with Enterprise Voice that all the individual pieces work: it’s possible to have a valid voice route, a valid voice policy, and a valid SIP trunk, but still have users unable to make or receive phone calls.</span></span> <span data-ttu-id="43774-115">따라서 Lync Server는 음성 테스트 구성을 만들 수 있는 기능도 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="43774-115">Because of that, Lync Server also provides the ability to create voice test configurations.</span></span> <span data-ttu-id="43774-116">음성 테스트 구성은 일반적인 Enterprise Voice 시나리오를 나타내며, 음성 경로, 음성 정책, 다이얼 플랜 등을 지정 하 고 해당 개별 항목이 함께 작동 하 여 전화 서비스를 제공할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="43774-116">Voice test configurations represent common Enterprise Voice scenarios: you can specify such things as a voice route, a voice policy, and a dial plan, and then verify that those individual items are work able to work together to provide phone service.</span></span> <span data-ttu-id="43774-117">또한 지정 된 시나리오에서 기대치를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43774-117">In addition, you can validate your expectations in a given scenario.</span></span> <span data-ttu-id="43774-118">예를 들어 다이얼 플랜 A와 음성 정책 B의 조합이 음성 경로 C를 통해 호출 될 것으로 예상 한다고 가정 합니다. 음성 경로 C를 ExpectedRoute으로 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43774-118">For example, suppose that you expect that the combination of dial plan A and voice policy B would result in calls being routed over voice route C. You can enter voice route C as the ExpectedRoute.</span></span> <span data-ttu-id="43774-119">테스트를 실행할 때 voice route C를 적용 하지 않으면 테스트가 실패 한 것으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="43774-119">When you run the test, if voice route C is not employed then the test will be marked as having failed.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="43774-120">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="43774-120">Running the test</span></span>

<span data-ttu-id="43774-121">Windows PowerShell을 사용 하 여 음성 구성 모음을 테스트 하기 전에 먼저 수정한 구성은 test-csvoicetestconfiguration cmdlet을 사용 하 여 이러한 구성 설정의 인스턴스를 검색 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="43774-121">Before testing Voice configuration collections using Windows PowerShell, you must first use the Get-CsVoiceTestConfiguration cmdlet to retrieve an instance of these configuration settings.</span></span> <span data-ttu-id="43774-122">그런 다음 해당 인스턴스를 수정한 구성은 test-csvoicetestconfiguration으로 파이프 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="43774-122">That instance must then be piped to the Test-CsVoiceTestConfiguration.</span></span> <span data-ttu-id="43774-123">예:</span><span class="sxs-lookup"><span data-stu-id="43774-123">For example:</span></span>

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration" | Test-CsVoiceTestConfiguration`

<span data-ttu-id="43774-124">모든 음성 테스트 구성 설정을 동시에 검사 하려면 다음 명령을 대신 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="43774-124">To validate all the voice test configuration settings at the same time, use this command instead:</span></span>

`Get-CsVoiceTestConfiguration | Test-CsVoiceTestConfiguration`

<span data-ttu-id="43774-125">자세한 내용은 수정한 구성은 test-csvoicetestconfiguration cmdlet에 대 한 도움말 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="43774-125">For more information, see the Help documentation for the Test-CsVoiceTestConfiguration cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="43774-126">성공 또는 실패 확인</span><span class="sxs-lookup"><span data-stu-id="43774-126">Determining success or failure</span></span>

<span data-ttu-id="43774-127">수정한 구성은 test-csvoicetestconfiguration cmdlet은 테스트가 실패 했는지 여부를 보고 하 고, 작업을 완료 하는 데 사용 되는 변환 규칙, 음성 경로 및 PSTN 사용과 같은 성공적인 테스트에 대 한 추가 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="43774-127">The Test-CsVoiceTestConfiguration cmdlet reports whether a test failed or succeeded, and provides additional information about each successful test, such as the translation rule, voice route, and PSTN usage used to complete the task:</span></span>

<span data-ttu-id="43774-128">결과: 성공</span><span class="sxs-lookup"><span data-stu-id="43774-128">Result:             Success</span></span>

<span data-ttu-id="43774-129">TranslatedNumber: + 15551234</span><span class="sxs-lookup"><span data-stu-id="43774-129">TranslatedNumber:   +15551234</span></span>

<span data-ttu-id="43774-130">MatchingRule: Description =; Pattern = ^ (\\d{4}) $; 번역 = + 1\\d; Name = Test; IsInternalExtension = False</span><span class="sxs-lookup"><span data-stu-id="43774-130">MatchingRule:       Description=;Pattern=^(\\d{4})$;Translation=+1\\d;Name=Test;IsInternalExtension=False</span></span>

<span data-ttu-id="43774-131">FirstMatchingRoute: 사이트: Redmond</span><span class="sxs-lookup"><span data-stu-id="43774-131">FirstMatchingRoute: site:Redmond</span></span>

<span data-ttu-id="43774-132">MatchingUsage: Local</span><span class="sxs-lookup"><span data-stu-id="43774-132">MatchingUsage:      Local</span></span>

<span data-ttu-id="43774-133">테스트가 실패 하면 결과가 실패로 보고 됩니다.</span><span class="sxs-lookup"><span data-stu-id="43774-133">If the test fails then the result is reported as Fail:</span></span>

<span data-ttu-id="43774-134">결과: 실패</span><span class="sxs-lookup"><span data-stu-id="43774-134">Result:             Fail</span></span>

<span data-ttu-id="43774-135">TranslatedNumber:</span><span class="sxs-lookup"><span data-stu-id="43774-135">TranslatedNumber:</span></span>   

<span data-ttu-id="43774-136">FirstMatchingRoute:</span><span class="sxs-lookup"><span data-stu-id="43774-136">FirstMatchingRoute:</span></span>

<span data-ttu-id="43774-137">MatchingUsage:</span><span class="sxs-lookup"><span data-stu-id="43774-137">MatchingUsage:</span></span>      

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="43774-138">테스트가 실패 한 이유</span><span class="sxs-lookup"><span data-stu-id="43774-138">Reasons why the test might have failed</span></span>

<span data-ttu-id="43774-139">음성 테스트 구성 테스트에서는 음성 정책, 다이얼 플랜, 음성 경로 등 다양 한 항목을 테스트 하기 때문에 테스트에 실패 하는 몇 가지 요인이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43774-139">Because voice test configuration testing tests several different items – including voice policies, dial plans, voice routes, and so on – there are several different factors that could result in a failed test.</span></span> <span data-ttu-id="43774-140">테스트가 실패 하는 경우 첫 번째 단계는 수정한 구성은 test-csvoicetestconfiguration cmdlet을 사용 하 여 구성 설정 자체를 검토 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="43774-140">If a test fails, your first step should be to review the configuration settings themselves by using the Get-CsVoiceTestConfiguration cmdlet:</span></span>

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration"`

<span data-ttu-id="43774-141">설정이 올바르게 구성 된 것 처럼 보이는 경우 Verbose 매개 변수를 포함 하 여 테스트를 다시 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="43774-141">If the settings seem to be configured correctly, re-run the test while including the Verbose parameter:</span></span>

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration" | Test-CsVoiceTestConfiguration`

<span data-ttu-id="43774-142">Verbose 매개 변수는 다음 예에서와 같이 수정한 구성은 test-csvoicetestconfiguration에서 수행 하는 각 작업의 단계별 계정을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="43774-142">The Verbose parameter will provide a step-by-step account of each action taken by Test-CsVoiceTestConfiguration as shown in this example:</span></span>

<span data-ttu-id="43774-143">자세한 정보 표시: 다이얼 플랜 로드: "Global"</span><span class="sxs-lookup"><span data-stu-id="43774-143">VERBOSE: Loading dial plan: "Global"</span></span>

<span data-ttu-id="43774-144">VERBOSE: "RedmondDialPlan" 라는 음성 정책을 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="43774-144">VERBOSE: Loading voice policy: "RedmondDialPlan"</span></span>

<span data-ttu-id="43774-145">이 단계별 계정은 테스트가 실제로 실패 한 위치에 대 한 유용한 단서를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43774-145">This step-by-step account might provide a useful clue as to where the test actually failed.</span></span> <span data-ttu-id="43774-146">그렇지 않은 경우에는 다른 Windows PowerShell cmdlet (예: Set-csvoicepolicy)을 사용 하 고, 체계적으로 시작 하 여 음성 테스트 구성 설정에 포함 된 개별 구성 요소를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43774-146">If not, you can then use other Windows PowerShell cmdlets (such as Test-CsVoicePolicy) and methodically begin to verify the individual components that are included in the voice test configuration settings.</span></span>

<span data-ttu-id="43774-147">이 외에도 테스트에서 전화를 라우팅하고 여전히 실패로 표시 되는 것을 알 수 있습니다. ExpectedRoute, ExpectedTranslatedNumber 및 ExpectedUsage에 대 한 값을 입력 하 고 이러한 기대치가 충족 되지 않는 경우에 발생할 수 있는 문제입니다.</span><span class="sxs-lookup"><span data-stu-id="43774-147">In addition to that, be aware that it’s possible for a test to be able to route a call and yet still be marked as a failure; that can occur if you enter values for ExpectedRoute, ExpectedTranslatedNumber, and ExpectedUsage, and any of those expectations are not met.</span></span> <span data-ttu-id="43774-148">예를 들어 음성 경로 C를 예상 음성 경로로 입력 한다고 가정 하면 테스트에서 음성 경로 D를 사용 하 여 통화를 실제로 완료 합니다. 이 경우 예상 되는 음성 경로를 사용 하지 않았으므로 테스트가 실패로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="43774-148">For example, suppose that you enter voice route C as your expected voice route, but the test actually completes the call using voice route D. In that case the test will be marked as Failed because the expected voice route was not used.</span></span> <span data-ttu-id="43774-149">테스트가 실패 하면 ExpectedRoute, ExpectedTranslatedNumber 및 ExpectedUsage에 대 한 값을 제거한 다음 테스트를 다시 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43774-149">If a test fails, you might remove the values for ExpectedRoute, ExpectedTranslatedNumber, and ExpectedUsage and then re-run the test.</span></span> <span data-ttu-id="43774-150">이를 통해 통화를 완료할 수 없거나, 한 가지 작업을 실제로 수신 하는 것으로 예상 했을 때 오류가 발생 했는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43774-150">That will help you determine whether the failure was because the call couldn't be completed, or because you expect one thing and actually received another.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="43774-151">참고 항목</span><span class="sxs-lookup"><span data-stu-id="43774-151">See Also</span></span>


[<span data-ttu-id="43774-152">수정한 구성은 test-csvoicetestconfiguration</span><span class="sxs-lookup"><span data-stu-id="43774-152">Test-CsVoiceTestConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceTestConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

