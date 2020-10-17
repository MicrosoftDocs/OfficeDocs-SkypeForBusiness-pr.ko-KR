---
title: 'Lync Server 2013: 다이얼 플랜 테스트'
description: 'Lync Server 2013: 다이얼 플랜을 테스트 합니다.'
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
ms.openlocfilehash: a0ef2e3fce9d1fbbb0186b1b7aef608834145d3e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556174"
---
# <a name="testing-the-dial-plan-in-lync-server-2013"></a><span data-ttu-id="4983b-103">Lync Server 2013에서 다이얼 플랜 테스트</span><span class="sxs-lookup"><span data-stu-id="4983b-103">Testing the dial plan in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4983b-104">_**마지막으로 수정 된 항목:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="4983b-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4983b-105">확인 일정</span><span class="sxs-lookup"><span data-stu-id="4983b-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="4983b-106">매일</span><span class="sxs-lookup"><span data-stu-id="4983b-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4983b-107">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="4983b-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="4983b-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4983b-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4983b-109">필요한 권한</span><span class="sxs-lookup"><span data-stu-id="4983b-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="4983b-110">Lync Server 관리 셸을 사용 하 여 로컬로 실행 하는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4983b-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="4983b-111">Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 사용자에 게 Test-CsDialPlan cmdlet을 실행 하는 권한이 있는 RBAC 역할을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4983b-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsDialPlan cmdlet.</span></span> <span data-ttu-id="4983b-112">이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4983b-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDialPlan&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="4983b-113">설명</span><span class="sxs-lookup"><span data-stu-id="4983b-113">Description</span></span>

<span data-ttu-id="4983b-114">Test-CsDialPlan cmdlet을 사용 하면 지정 된 전화 번호에 다이얼 플랜을 적용 한 결과를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4983b-114">The Test-CsDialPlan cmdlet enables you to see the results of applying a dial plan to a given telephone number.</span></span> <span data-ttu-id="4983b-115">다이얼 플랜은 Enterprise Voice 사용자가 전화를 걸 수 있도록 하는 데 필요한 정규화 규칙 적용 방법 등의 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4983b-115">Dial plans provide information, such as how normalization rules are applied, required to enable Enterprise Voice users to make telephone calls.</span></span> <span data-ttu-id="4983b-116">전화 건 번호와 다이얼 플랜이 제공 되 면이 cmdlet은 다이얼 플랜 내에서 적용 되는 정규화 규칙 및 변환 된 번호를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4983b-116">Given a dialed number and a dial plan, this cmdlet will verify which normalization rule within the dial plan will be applied and what the translated number will be.</span></span>

<span data-ttu-id="4983b-117">이 cmdlet을 사용 하 여 번호 변환과 관련 된 문제를 해결 하거나 특정 번호에 대해 규칙을 적용 하는 방법을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4983b-117">You can use this cmdlet for troubleshooting issues with number translations, or for verifying how to apply rules against certain numbers.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="4983b-118">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="4983b-118">Running the test</span></span>

<span data-ttu-id="4983b-119">Test-CsDialPlan cmdlet을 사용 하려면 두 가지 작업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4983b-119">The Test-CsDialPlan cmdlet requires you to do two things.</span></span> <span data-ttu-id="4983b-120">먼저 테스트할 다이얼 플랜의 인스턴스를 가져와야 합니다. 이 작업은 Get-CsDialPlan cmdlet을 사용 하 여 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4983b-120">First, you must obtain an instance of the dial plan being tested; that can be done by using the Get-CsDialPlan cmdlet.</span></span> <span data-ttu-id="4983b-121">두 번째로, 정규화 해야 하는 전화 번호를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4983b-121">Second, you must specify the phone number that has to be normalized.</span></span> <span data-ttu-id="4983b-122">전화 번호에 사용 되는 형식은 사용자가 전화를 걸고 입력 한 번호와 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4983b-122">The format that is used for the phone number should match the number as dialed/entered by a user.</span></span> <span data-ttu-id="4983b-123">예를 들어이 명령은 다이얼 플랜의 인스턴스를 검색 하 여 RedmondDialPlan를 확인 하 고 전화 번호 12065551219 정규화 가능 여부를 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="4983b-123">For example, this command retrieves an instance of the dial plan, RedmondDialPlan, and checks whether the phone number 12065551219 can be normalized:</span></span>

    Get-CsDialPlan -Identity "RedmondDialPlan" | Test-CsDialPlan -DialedNumber "12065551219" | Format-List

<span data-ttu-id="4983b-124">국가 코드 (이 예에서 1)와 지역 번호 (206)를 자동으로 추가 하는 정규화 규칙이 있는 경우 다음과 같이 전화 번호 5551219를 확인 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4983b-124">If you have a normalization rule that automatically adds the country code (in this example, 1) and the area code (206), then you might want to check the phone number 5551219, as follows:</span></span>

    Get-CsDialPlan -Identity "RedmondDialPlan" | Test-CsDialPlan -DialedNumber "5551219" | Format-List

<span data-ttu-id="4983b-125">자세한 내용은 [테스트-CsDialPlan 플랜](https://docs.microsoft.com/powershell/module/skype/Test-CsDialPlan) cmdlet에 대 한 도움말 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="4983b-125">For more information, see the Help documentation for the [Test-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/Test-CsDialPlan) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="4983b-126">성공 또는 실패 확인</span><span class="sxs-lookup"><span data-stu-id="4983b-126">Determining success or failure</span></span>

<span data-ttu-id="4983b-127">Test-CsDialPlan 대부분의 Lync Server 테스트 cmdlet은 테스트가 성공 했는지 아니면 실패 하는지를 간접적으로 표시 하기 때문에 이와는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="4983b-127">Test-CsDialPlan differs from many of the Lync Server test cmdlets because it only indirectly indicates whether a test succeeded or failed.</span></span> <span data-ttu-id="4983b-128">Test-CsDialPlan 사용 하는 경우 다음과 유사한 출력이 표시 되 고 결과에 분명 하 게 레이블이 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4983b-128">When using Test-CsDialPlan you do not receive back output similar to this with the Result clearly labeled:</span></span>

<span data-ttu-id="4983b-129">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="4983b-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="4983b-130">결과: 성공</span><span class="sxs-lookup"><span data-stu-id="4983b-130">Result : Success</span></span>

<span data-ttu-id="4983b-131">대기 시간: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="4983b-131">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="4983b-132">오류</span><span class="sxs-lookup"><span data-stu-id="4983b-132">Error :</span></span>

<span data-ttu-id="4983b-133">진단을</span><span class="sxs-lookup"><span data-stu-id="4983b-133">Diagnosis :</span></span>

<span data-ttu-id="4983b-134">대신, Test-CsDialPlan에 성공 하면 지정 된 전화 번호를 성공적으로 변환 하 고 사용할 수 있는 정규화 규칙에 대 한 정보를 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4983b-134">Instead, if Test-CsDialPlan succeeds, then you'll receive information about the normalization rule that was able to successfully translate and use the specified phone number:</span></span>

<span data-ttu-id="4983b-135">TranslatedNumber: + 12065551219</span><span class="sxs-lookup"><span data-stu-id="4983b-135">TranslatedNumber : +12065551219</span></span>

<span data-ttu-id="4983b-136">MatchingRule: Description =; Pattern = ^ ( \\ d (11)) $; 번역 = + $1,</span><span class="sxs-lookup"><span data-stu-id="4983b-136">MatchingRule : Description=;Pattern=^(\\d(11))$;Translation=+$1;</span></span>

<span data-ttu-id="4983b-137">Name = All 접두사; IsInternalExtension = False</span><span class="sxs-lookup"><span data-stu-id="4983b-137">Name=Prefix All; IsInternalExtension=False</span></span>

<span data-ttu-id="4983b-138">Test-CsDialPlan이 실패 하는 경우 (즉, 다이얼 플랜에 지정 된 전화 번호를 변환할 수 있는 정규화 규칙이 없는 경우) 다음과 같이 "빈" 출력을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4983b-138">If Test-CsDialPlan fails (that is, if the dial plan does not have a normalization rule that can translate the specified phone number), you'll just receive “empty” output as follows:</span></span>

<span data-ttu-id="4983b-139">TranslatedNumber :</span><span class="sxs-lookup"><span data-stu-id="4983b-139">TranslatedNumber :</span></span>

<span data-ttu-id="4983b-140">MatchingRule :</span><span class="sxs-lookup"><span data-stu-id="4983b-140">MatchingRule :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="4983b-141">테스트가 실패 한 이유</span><span class="sxs-lookup"><span data-stu-id="4983b-141">Reasons why the test might have failed</span></span>

<span data-ttu-id="4983b-142">Test-CsDialPlan 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4983b-142">Here are some common reasons why Test-CsDialPlan might fail:</span></span>

  - <span data-ttu-id="4983b-143">전화 번호를 지정할 때 잘못 된 형식을 사용 했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4983b-143">You might have used an incorrect format when specifying the phone number.</span></span> <span data-ttu-id="4983b-144">다이얼 플랜에는 Lync Server에서 사용자가 전화를 걸고 입력 한 번호를 번역할 수 있도록 하는 정규화 규칙이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4983b-144">Dial plans include normalization rules that enable Lync Server to translate the phone numbers dialed or entered by a user.</span></span> <span data-ttu-id="4983b-145">따라서 다이얼 플랜은 사용자가 전화를 걸 가능성이 있는 번호와 일치 하는 정규화 규칙을 가져야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4983b-145">Therefore, your dial plan should have normalization rules that match the numbers users are likely to dial.</span></span> <span data-ttu-id="4983b-146">예를 들어 사용자가 국가 코드, 지역 번호 및 전화 번호로 전화를 걸 수 있는 경우이는 다이얼 플랜에 다음과 같은 전화 번호를 처리 하기 위한 정규화 규칙이 있어야 함을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="4983b-146">For example, if users might dial the country code, area code, and then the phone number itself, that means that your dial plan should have a normalization rule to handle phone numbers such as this:</span></span>
    
    <span data-ttu-id="4983b-147">12065551219</span><span class="sxs-lookup"><span data-stu-id="4983b-147">12065551219</span></span>
    
    <span data-ttu-id="4983b-148">그러나 마지막 숫자를 제외 하 고 잘못 된 전화 번호를 입력 한 경우에는 Test-CsDialPlan가 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="4983b-148">However, if you enter an incorrect phone number (for example, leaving off the final digit), then Test-CsDialPlan will fail.</span></span> <span data-ttu-id="4983b-149">다이얼 플랜에 문제가 있지만 해석할 수 없는 것 보다 전화 번호를 입력 했기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="4983b-149">That’s not because the dial plan is faulty but because you have entered a phone number than can’t be interpreted.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

