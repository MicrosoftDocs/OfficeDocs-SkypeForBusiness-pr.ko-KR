---
title: 'Lync Server 2013: 음성 정규화 규칙 확인'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Check voice normalization rules
ms:assetid: bf71a218-71cd-4b64-b8e8-b3a98b6e87a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725212(v=OCS.15)
ms:contentKeyID: 63969649
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 487415fccc1e779daa476a4e76aa99a891f6b7fe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981106"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="check-voice-normalization-rules-in-lync-server-2013"></a><span data-ttu-id="a76a7-102">Lync Server 2013에서 음성 표준화 규칙 확인</span><span class="sxs-lookup"><span data-stu-id="a76a7-102">Check voice normalization rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a76a7-103">_**마지막으로 수정한 주제:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="a76a7-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a76a7-104">확인 일정</span><span class="sxs-lookup"><span data-stu-id="a76a7-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="a76a7-105">월간</span><span class="sxs-lookup"><span data-stu-id="a76a7-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a76a7-106">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="a76a7-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="a76a7-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a76a7-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a76a7-108">권한이 필요 함</span><span class="sxs-lookup"><span data-stu-id="a76a7-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="a76a7-109">Lync Server Management Shell을 사용 하 여 로컬에서 실행 되는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a76a7-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="a76a7-110">Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 CsVoiceNormalizationRule cmdlet을 실행 하는 데 필요한 권한이 있는 RBAC 역할을 사용자에 게 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a76a7-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoiceNormalizationRule cmdlet.</span></span> <span data-ttu-id="a76a7-111">이 cmdlet을 사용할 수 있는 모든 RBAC 역할 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a76a7-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceNormalizationRule&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="a76a7-112">설명</span><span class="sxs-lookup"><span data-stu-id="a76a7-112">Description</span></span>

<span data-ttu-id="a76a7-113">음성 표준화 규칙은 사용자가 전화를 거는 전화 번호 (예: 2065551219)를 Lync Server에서 사용 하는 E-164 형식으로 변환 하는 데 사용 됩니다 (+ 12065551219).</span><span class="sxs-lookup"><span data-stu-id="a76a7-113">Voice normalization rules are used to convert a phone number dialed by a user (for example, 2065551219) to the E.164 format that is used by Lync Server (+12065551219).</span></span> <span data-ttu-id="a76a7-114">예를 들어 사용자가 국가 코드나 지역 번호 (예: 5551219)를 포함 하지 않고 전화 번호를 사용 하는 습관을 사용 하는 경우에는 해당 번호를 E-164 형식: + 12065551219로 변환할 수 있는 음성 정규화 규칙이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a76a7-114">For example, if users are in the habit of dialing a phone number without including the country code or the area code (e.g., 5551219) then you must have a voice normalization rule that can convert that number to the E.164 format: +12065551219.</span></span> <span data-ttu-id="a76a7-115">이러한 규칙이 없으면 사용자는 555-1219를 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a76a7-115">Without such a rule, the user won't be able to call 555-1219.</span></span>

<span data-ttu-id="a76a7-116">CsVoiceNormalizationRule cmdlet은 지정 된 음성 표준화 규칙이 지정 된 전화 번호를 성공적으로 변환할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a76a7-116">The Test-CsVoiceNormalizationRule cmdlet verifies that a specified voice normalization rule can successfully convert a specified phone number.</span></span> <span data-ttu-id="a76a7-117">예를 들어이 명령은 전역 정규화 규칙 NoAreaCode에서 다이얼 문자열 5551219을 표준화 하 고 변환할 수 있는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a76a7-117">For example, this command checks whether the global normalization rule NoAreaCode can normalize and convert the dial string 5551219.</span></span>

`Get-CsVoiceNormalizationRule -Identity "global/NoAreaCode" | Test-CsVoiceNormalizationRule -DialedNumber "5551219"`

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="a76a7-118">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="a76a7-118">Running the test</span></span>

<span data-ttu-id="a76a7-119">CsVoiceNormalizationRule cmdlet을 실행 하려면 먼저 Get-CsVoiceNormalizationRule cmdlet을 사용 하 여 테스트할 규칙의 인스턴스를 검색 한 다음 해당 인스턴스를 테스트-CsVoiceNormalizationRule에 파이프 합니다.</span><span class="sxs-lookup"><span data-stu-id="a76a7-119">To run the Test-CsVoiceNormalizationRule cmdlet, you must first use the Get-CsVoiceNormalizationRule cmdlet to retrieve an instance of the rule being tested, and then pipe that instance to Test-CsVoiceNormalizationRule.</span></span> <span data-ttu-id="a76a7-120">다음과 같은 구문은 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a76a7-120">Syntax similar to this won't work:</span></span>

<span data-ttu-id="a76a7-121">테스트-CsVoiceNormalizationRule-DialedNumber "12065551219"-NormalizationRule "global/Prefix All"</span><span class="sxs-lookup"><span data-stu-id="a76a7-121">Test-CsVoiceNormalizationRule -DialedNumber "12065551219" –NormalizationRule "global/Prefix All"</span></span>

<span data-ttu-id="a76a7-122">대신 CsVoiceNormalizationRule 및 Test-CsVoiceNormalizationRule cmdlet을 모두 결합 하는 다음과 같은 구문을 사용 하세요.</span><span class="sxs-lookup"><span data-stu-id="a76a7-122">Instead, use syntax such as the following, which combines both the Get-CsVoiceNormalizationRule and the Test-CsVoiceNormalizationRule cmdlets:</span></span>

<span data-ttu-id="a76a7-123">Get-CsVoiceNormalizationRule-Id "global/Prefix All" | 테스트-CsVoiceNormalizationRule-DialedNumber "12065551219"</span><span class="sxs-lookup"><span data-stu-id="a76a7-123">Get-CsVoiceNormalizationRule -Identity "global/Prefix All" | Test-CsVoiceNormalizationRule -DialedNumber "12065551219"</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a76a7-124">.</span><span class="sxs-lookup"><span data-stu-id="a76a7-124"></span></span> <span data-ttu-id="a76a7-125">또는이 방법을 사용 하 여 규칙의 인스턴스를 검색 한 다음 지정 된 전화 번호에 대해 해당 규칙을 테스트할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a76a7-125">Or, you can also use this approach to retrieve an instance of a rule and then test that rule against a specified phone number:</span></span>



</div>

`$x = Get-CsVoiceNormalizationRule -Identity "global/Prefix All"`

`Test-CsVoiceNormalizationRule -DialedNumber "12065551219" -NormalizationRule $x`

<span data-ttu-id="a76a7-126">DialedNumber 매개 변수에 대 한 값을 정확 하 게 입력 하 여 원하는 번호로 전화를 겁니다.</span><span class="sxs-lookup"><span data-stu-id="a76a7-126">Enter the value for the DialedNumber parameter exactly as you expect that number to be dialed.</span></span> <span data-ttu-id="a76a7-127">예를 들어 지정 된 음성 정규화 규칙에서 국가 코드 (값 12065551219의 초기 1)를 자동으로 추가 해야 하는 경우 국가 코드를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="a76a7-127">For example, if the specified voice normalization rule is supposed to automatically add the country code (the initial 1 in the value 12065551219) then you should leave off the country code:</span></span>

`-DialedNumber "2065551219"`

<span data-ttu-id="a76a7-128">규칙이 올바르게 구성 되 면 Lync Server에서 사용 하는 해당 번호를 E-164 형식으로 변환할 때 국가 코드가 자동으로 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a76a7-128">If the rule is configured correctly, it will automatically add the country code when translating the number to the E.164 format that is used by Lync Server.</span></span>

<span data-ttu-id="a76a7-129">자세한 내용은 테스트 CsVoiceNormalizationRule cmdlet에 대 한 도움말 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a76a7-129">For more information, see the Help documentation for the Test-CsVoiceNormalizationRule cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="a76a7-130">성공 또는 실패 확인</span><span class="sxs-lookup"><span data-stu-id="a76a7-130">Determining success or failure</span></span>

<span data-ttu-id="a76a7-131">지정 된 음성 표준화 규칙에서 제공 된 숫자를 변환할 수 있는 경우 번역 된 번호가 화면에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a76a7-131">If the specified voice normalization rule can translate the supplied number then the translated number will be displayed on-screen:</span></span>

<span data-ttu-id="a76a7-132">TranslatedNumber</span><span class="sxs-lookup"><span data-stu-id="a76a7-132">TranslatedNumber</span></span>

\----------------

<span data-ttu-id="a76a7-133">\+12065551219</span><span class="sxs-lookup"><span data-stu-id="a76a7-133">\+12065551219</span></span>

<span data-ttu-id="a76a7-134">테스트에 실패 하면 빈 번역 번호가 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a76a7-134">If the test fails then a blank translated number will be returned:</span></span>

<span data-ttu-id="a76a7-135">TranslatedNumber</span><span class="sxs-lookup"><span data-stu-id="a76a7-135">TranslatedNumber</span></span>

\----------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="a76a7-136">테스트가 실패할 수 있는 이유</span><span class="sxs-lookup"><span data-stu-id="a76a7-136">Reasons why the test might have failed</span></span>

<span data-ttu-id="a76a7-137">테스트-CsVoiceNormalizationRule가 번역 된 숫자를 반환 하는 경우 지정 된 음성 표준화 규칙에서 제공 된 전화 번호를 Lync Server에서 사용 하는 전자 164 형식으로 변환할 수 없음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="a76a7-137">If the Test-CsVoiceNormalizationRule does return a translated number that means that the specified voice normalization rule was unable to translate the supplied telephone number into the E.164 format that is used by Lync Server.</span></span> <span data-ttu-id="a76a7-138">이를 확인 하려면 먼저 전화 번호를 올바르게 입력 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a76a7-138">To verify that, first make sure that you typed the telephone number in correctly.</span></span> <span data-ttu-id="a76a7-139">예를 들어 음성 표준화 규칙에 다음과 같은 번호를 번역 하는 데 문제가 있는 것으로 예상 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a76a7-139">For example, you would expect your voice normalization rule to have problems translating a number similar to this:</span></span>

`-DialedNumber "1"`

<span data-ttu-id="a76a7-140">숫자가 올바르게 입력 되었다고 가정 하 고 다음 단계는 지정 된 정규화 규칙이 해당 전화 번호를 처리 하도록 디자인 되었는지 확인 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a76a7-140">Assuming the number was entered correctly, your next step should be to verify that the specified normalization rule is designed to handle that phone number.</span></span> <span data-ttu-id="a76a7-141">예를 들어 12065551219 형식을 처리 하도록 한 정규화 규칙을 디자인할 수 있지만 두 번째 규칙은 숫자 2065551219을 처리 하도록 디자인 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a76a7-141">For example, one normalization rule might be designed to handle the format 12065551219, but a second rule might be designed to handle the number 2065551219.</span></span> <span data-ttu-id="a76a7-142">(맨 앞에 국가 코드 1을 제외한 전화 번호입니다.) 음성 정규화 규칙에 대 한 자세한 정보를 반환 하려면 다음과 같은 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a76a7-142">(That’s the same phone number, minus the country code 1 at the very beginning.) To return detailed information about a voice normalization rule, run a command similar to this:</span></span>

`Get-CsVoiceNormalizationRule -Identity "global/Prefix All" | Format-List`

<span data-ttu-id="a76a7-143">모든 음성 정규화 규칙에 대 한 자세한 정보를 반환 하려면 대신이 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a76a7-143">To return detailed information about all the voice normalization rules, run this command instead:</span></span>

`Get-CsVoiceNormalizationRule | Format-List`

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a76a7-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a76a7-144">See Also</span></span>


[<span data-ttu-id="a76a7-145">테스트-CsVoiceNormalizationRule</span><span class="sxs-lookup"><span data-stu-id="a76a7-145">Test-CsVoiceNormalizationRule</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceNormalizationRule)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

