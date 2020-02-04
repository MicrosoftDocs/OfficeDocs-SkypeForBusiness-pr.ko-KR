---
title: 'Lync Server 2013: 다이얼 플랜 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the dial plan
ms:assetid: 70eec03c-aca3-4106-86a7-77ae96b53779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690130(v=OCS.15)
ms:contentKeyID: 63969616
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8e0e39b88d7b6c90a55d236038d03cc4cc717319
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745458"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-dial-plan-in-lync-server-2013"></a><span data-ttu-id="e3286-102">Lync Server 2013에서 다이얼 플랜 테스트</span><span class="sxs-lookup"><span data-stu-id="e3286-102">Testing the dial plan in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3286-103">_**마지막으로 수정한 주제:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="e3286-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e3286-104">확인 일정</span><span class="sxs-lookup"><span data-stu-id="e3286-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="e3286-105">Daily</span><span class="sxs-lookup"><span data-stu-id="e3286-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3286-106">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="e3286-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="e3286-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e3286-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3286-108">권한이 필요 함</span><span class="sxs-lookup"><span data-stu-id="e3286-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="e3286-109">Lync Server Management Shell을 사용 하 여 로컬에서 실행 되는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3286-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="e3286-110">Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 테스트-CsDialPlan 플랜 cmdlet을 실행할 권한이 있는 RBAC 역할을 사용자에 게 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3286-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsDialPlan cmdlet.</span></span> <span data-ttu-id="e3286-111">이 cmdlet을 사용할 수 있는 모든 RBAC 역할 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3286-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDialPlan&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="e3286-112">설명</span><span class="sxs-lookup"><span data-stu-id="e3286-112">Description</span></span>

<span data-ttu-id="e3286-113">테스트-CsDialPlan cmdlet을 사용 하면 지정 된 전화 번호에 다이얼 플랜을 적용 한 결과를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3286-113">The Test-CsDialPlan cmdlet enables you to see the results of applying a dial plan to a given telephone number.</span></span> <span data-ttu-id="e3286-114">다이얼 플랜은 표준화 규칙이 적용 되는 방법과 같이 Enterprise Voice 사용자가 전화를 걸 수 있도록 하는 데 필요한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3286-114">Dial plans provide information, such as how normalization rules are applied, required to enable Enterprise Voice users to make telephone calls.</span></span> <span data-ttu-id="e3286-115">전화 거는 번호와 다이얼 플랜이 지정 된 경우이 cmdlet은 다이얼 플랜에서 적용 되는 정규화 규칙과 번역 된 번호를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3286-115">Given a dialed number and a dial plan, this cmdlet will verify which normalization rule within the dial plan will be applied and what the translated number will be.</span></span>

<span data-ttu-id="e3286-116">이 cmdlet을 사용 하 여 숫자 번역 관련 문제를 해결 하거나 특정 번호에 대 한 규칙을 적용 하는 방법을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3286-116">You can use this cmdlet for troubleshooting issues with number translations, or for verifying how to apply rules against certain numbers.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="e3286-117">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="e3286-117">Running the test</span></span>

<span data-ttu-id="e3286-118">테스트-CsDialPlan 플랜 cmdlet을 사용 하려면 두 가지 작업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3286-118">The Test-CsDialPlan cmdlet requires you to do two things.</span></span> <span data-ttu-id="e3286-119">먼저 테스트 중인 다이얼 플랜의 인스턴스를 가져와야 합니다. 이 작업은 Get-CsDialPlan 플랜 cmdlet을 사용 하 여 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3286-119">First, you must obtain an instance of the dial plan being tested; that can be done by using the Get-CsDialPlan cmdlet.</span></span> <span data-ttu-id="e3286-120">둘째로, 정규화 할 전화 번호를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3286-120">Second, you must specify the phone number that has to be normalized.</span></span> <span data-ttu-id="e3286-121">전화 번호에 사용 되는 형식은 사용자가 전화를 걸어 입력 하는 번호와 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3286-121">The format that is used for the phone number should match the number as dialed/entered by a user.</span></span> <span data-ttu-id="e3286-122">예를 들어이 명령은 다이얼 플랜의 인스턴스를 검색 하 고 RedmondDialPlan 전화 번호 12065551219을 표준화할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3286-122">For example, this command retrieves an instance of the dial plan, RedmondDialPlan, and checks whether the phone number 12065551219 can be normalized:</span></span>

    Get-CsDialPlan -Identity "RedmondDialPlan" | Test-CsDialPlan -DialedNumber "12065551219" | Format-List

<span data-ttu-id="e3286-123">국가 코드 (이 예에서는 1) 및 지역 번호 (206)를 자동으로 추가 하는 정규화 규칙을 사용 하는 경우 다음과 같이 전화 번호 5551219을 확인 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3286-123">If you have a normalization rule that automatically adds the country code (in this example, 1) and the area code (206), then you might want to check the phone number 5551219, as follows:</span></span>

    Get-CsDialPlan -Identity "RedmondDialPlan" | Test-CsDialPlan -DialedNumber "5551219" | Format-List

<span data-ttu-id="e3286-124">자세한 내용은 [CsDialPlan 플랜](https://docs.microsoft.com/powershell/module/skype/Test-CsDialPlan) cmdlet에 대 한 도움말 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e3286-124">For more information, see the Help documentation for the [Test-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/Test-CsDialPlan) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="e3286-125">성공 또는 실패 확인</span><span class="sxs-lookup"><span data-stu-id="e3286-125">Determining success or failure</span></span>

<span data-ttu-id="e3286-126">테스트 성공 또는 실패 여부는 간접적 으로만 표시 되기 때문에 테스트 CsDialPlan 플랜은 많은 Lync Server 테스트 cmdlet과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="e3286-126">Test-CsDialPlan differs from many of the Lync Server test cmdlets because it only indirectly indicates whether a test succeeded or failed.</span></span> <span data-ttu-id="e3286-127">테스트-CsDialPlan 플랜을 사용 하는 경우 다음과 비슷한 출력이 표시 되며 결과는 명확 하 게 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3286-127">When using Test-CsDialPlan you do not receive back output similar to this with the Result clearly labeled:</span></span>

<span data-ttu-id="e3286-128">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e3286-128">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="e3286-129">결과: 성공</span><span class="sxs-lookup"><span data-stu-id="e3286-129">Result : Success</span></span>

<span data-ttu-id="e3286-130">대기 시간: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="e3286-130">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="e3286-131">오류</span><span class="sxs-lookup"><span data-stu-id="e3286-131">Error :</span></span>

<span data-ttu-id="e3286-132">있게</span><span class="sxs-lookup"><span data-stu-id="e3286-132">Diagnosis :</span></span>

<span data-ttu-id="e3286-133">대신 테스트-CsDialPlan 플랜에 성공한 경우 지정 된 전화 번호를 성공적으로 번역 하 여 사용할 수 있었던 정규화 규칙에 대 한 정보를 수신 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3286-133">Instead, if Test-CsDialPlan succeeds, then you'll receive information about the normalization rule that was able to successfully translate and use the specified phone number:</span></span>

<span data-ttu-id="e3286-134">TranslatedNumber: + 12065551219</span><span class="sxs-lookup"><span data-stu-id="e3286-134">TranslatedNumber : +12065551219</span></span>

<span data-ttu-id="e3286-135">MatchingRule: Description =; Pattern = ^ (\\d (11)) $; 번역 = + $1,</span><span class="sxs-lookup"><span data-stu-id="e3286-135">MatchingRule : Description=;Pattern=^(\\d(11))$;Translation=+$1;</span></span>

<span data-ttu-id="e3286-136">Name = All 접두사 IsInternalExtension = False</span><span class="sxs-lookup"><span data-stu-id="e3286-136">Name=Prefix All; IsInternalExtension=False</span></span>

<span data-ttu-id="e3286-137">테스트-CsDialPlan 다이얼 플랜에 실패 한 경우 (즉, 다이얼 플랜에 지정 된 전화번호를 번역할 수 있는 정규화 규칙이 없으면) 다음과 같이 "빈" 출력만 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3286-137">If Test-CsDialPlan fails (that is, if the dial plan does not have a normalization rule that can translate the specified phone number), you'll just receive “empty” output as follows:</span></span>

<span data-ttu-id="e3286-138">TranslatedNumber :</span><span class="sxs-lookup"><span data-stu-id="e3286-138">TranslatedNumber :</span></span>

<span data-ttu-id="e3286-139">MatchingRule :</span><span class="sxs-lookup"><span data-stu-id="e3286-139">MatchingRule :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="e3286-140">테스트가 실패할 수 있는 이유</span><span class="sxs-lookup"><span data-stu-id="e3286-140">Reasons why the test might have failed</span></span>

<span data-ttu-id="e3286-141">테스트 CsDialPlan 플랜에 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e3286-141">Here are some common reasons why Test-CsDialPlan might fail:</span></span>

  - <span data-ttu-id="e3286-142">전화 번호를 지정할 때 잘못 된 형식을 사용 했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3286-142">You might have used an incorrect format when specifying the phone number.</span></span> <span data-ttu-id="e3286-143">다이얼 플랜에는 Lync Server에서 전화를 걸어 사용자가 입력 한 전화번호를 번역할 수 있는 정규화 규칙이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3286-143">Dial plans include normalization rules that enable Lync Server to translate the phone numbers dialed or entered by a user.</span></span> <span data-ttu-id="e3286-144">따라서 다이얼 플랜에는 사용자가 자주 접속 하는 번호와 일치 하는 정규화 규칙이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3286-144">Therefore, your dial plan should have normalization rules that match the numbers users are likely to dial.</span></span> <span data-ttu-id="e3286-145">예를 들어 사용자가 국가 코드, 지역 번호, 전화 번호 자체에 전화를 걸 경우 다이얼 플랜에 다음과 같은 전화 번호를 처리 하는 정규화 규칙이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3286-145">For example, if users might dial the country code, area code, and then the phone number itself, that means that your dial plan should have a normalization rule to handle phone numbers such as this:</span></span>
    
    <span data-ttu-id="e3286-146">12065551219</span><span class="sxs-lookup"><span data-stu-id="e3286-146">12065551219</span></span>
    
    <span data-ttu-id="e3286-147">그러나 마지막 자릿수를 해제 하는 등 잘못 된 전화 번호를 입력 하는 경우 테스트-CsDialPlan 플랜에 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3286-147">However, if you enter an incorrect phone number (for example, leaving off the final digit), then Test-CsDialPlan will fail.</span></span> <span data-ttu-id="e3286-148">다이얼 플랜에 문제가 있지만 해석할 수 없는 전화 번호를 입력 했기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="e3286-148">That’s not because the dial plan is faulty but because you have entered a phone number than can’t be interpreted.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

