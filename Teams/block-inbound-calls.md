---
title: 인바운드 호출을 차단합니다Microsoft Teams
ms.author: v-cichur
author: cichur
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
audience: Admin
ms.reviewer: roykuntz
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.custom: Learn how to use PowerShell to manage inbound call blocking.
ms.openlocfilehash: e584e9f0c16ef77424121c37ce87c6d63afb4b92
ms.sourcegitcommit: 17e34d2de3d10f1d04929a695e301127db7014bd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689766"
---
# <a name="block-inbound-calls"></a><span data-ttu-id="25084-102">인바운드 호출 차단</span><span class="sxs-lookup"><span data-stu-id="25084-102">Block inbound calls</span></span>

<span data-ttu-id="25084-103">Microsoft 통화 계획, 직접 라우팅 및 운영자는 PSTN(공용 커넥트 전화 네트워크)에서 인바운드 호출을 차단하는 모든 지원을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="25084-103">Microsoft Calling Plans, Direct Routing, and Operator Connect all support blocking inbound calls from the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="25084-104">이 기능을 사용하면 관리자가 테넌트 전역 수준에서 번호 패턴 목록을 정의하여 테넌트에 들어오는 모든 PSTN 호출의 호출자 ID를 매치 목록에 대해 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25084-104">This feature allows an administrator to define a  list of number patterns at the tenant global level so that the caller ID of every incoming PSTN call to the tenant can be checked against the list for a match.</span></span> <span data-ttu-id="25084-105">일치하는 경우 들어오는 호출이 거부됩니다.</span><span class="sxs-lookup"><span data-stu-id="25084-105">If a match is made, an incoming call is rejected.</span></span>

<span data-ttu-id="25084-106">이 인바운드 호출 차단 기능은 PSTN에서 시작된 인바운드 호출에만 작동하며 테넌트 전역 수준에서만 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="25084-106">This inbound call blocking feature only works on inbound calls that originate from the PSTN and only works on a tenant global level.</span></span> <span data-ttu-id="25084-107">개별 Teams 사용자가 이 목록을 조작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="25084-107">Individual Teams users can’t manipulate this list.</span></span> <span data-ttu-id="25084-108">Teams 클라이언트는 개별 사용자가 PSTN 호출을 차단할 수 있도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="25084-108">The Teams client does allow individual users to block PSTN calls.</span></span> <span data-ttu-id="25084-109">최종 사용자가 통화 차단을 구현하는 방법에 대한 자세한 내용은 에서 호출 [설정 관리를 Teams.](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)</span><span class="sxs-lookup"><span data-stu-id="25084-109">For information about how your end users can implement call blocking, see [Manage call settings in Teams](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f).</span></span>

>[!NOTE]
> <span data-ttu-id="25084-110">차단된 호출자는 차단된 경우 약간 다른 동작을 경험할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25084-110">Blocked callers may experience slightly different behaviors when they've been blocked.</span></span> <span data-ttu-id="25084-111">동작은 차단된 발신자 통신사가 호출을 성공적으로 완료할 수 없습니다는 알림을 처리하는 방법을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="25084-111">The behavior is based on how the blocked caller’s carrier handles the notification that the call isn't allowed to be successfully completed.</span></span> <span data-ttu-id="25084-112">예를 들어 전화를 걸 때 통화를 완료할 수 없다거나 단순히 전화를 떨어뜨렸다는 통신사 메시지가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25084-112">Examples may include a carrier message stating the call can't be completed as dialed, or simply dropping the call.</span></span>

## <a name="call-blocking-admin-controls-and-information"></a><span data-ttu-id="25084-113">관리자 제어 및 정보 차단 호출</span><span class="sxs-lookup"><span data-stu-id="25084-113">Call blocking admin controls and information</span></span>

<span data-ttu-id="25084-114">차단 번호에 대한 관리자 컨트롤은 PowerShell을 사용하여만 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="25084-114">Admin controls for blocking numbers are provided using PowerShell only.</span></span> <span data-ttu-id="25084-115">숫자 블록 패턴은 정규식 패턴으로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="25084-115">Number block patterns are defined as regular expression patterns.</span></span> <span data-ttu-id="25084-116">식의 순서는 무의미합니다. 목록에서 일치하는 첫 번째 패턴은 호출이 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="25084-116">The order of the expressions is unimportant – the first pattern matched in the list results in the call being blocked.</span></span> <span data-ttu-id="25084-117">차단된 호출자 목록에 추가되거나 제거된 새 번호 또는 패턴은 패턴이 활성화되는 데 최대 24시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25084-117">A new number or pattern that's added or removed in the blocked callers list may take up to 24 hours for the pattern to become active.</span></span>

## <a name="call-blocking-powershell-commands"></a><span data-ttu-id="25084-118">PowerShell 명령 차단 호출</span><span class="sxs-lookup"><span data-stu-id="25084-118">Call blocking PowerShell commands</span></span>

<span data-ttu-id="25084-119">**New-**, **Get-**, **Set-** 및 **Remove-CsInboundBlockedNumberPattern** cmdlet을 사용하여 숫자 패턴을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="25084-119">You manage number patterns by using the **New-**, **Get-**, **Set-**, and **Remove-CsInboundBlockedNumberPattern** cmdlets.</span></span> <span data-ttu-id="25084-120">특정 패턴의 활성화를 전환하는 기능을 포함하여 이러한 cmdlet을 사용하여 주어진 패턴을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25084-120">You can manage a given pattern by using these cmdlets, including the ability to toggle the activation of a given pattern.</span></span>

- <span data-ttu-id="25084-121">[Get-CsInboundBlockedNumberPattern은](/powershell/module/skype/get-csinboundblockednumberpattern) 각각에 대한 이름, 설명, 사용 가능(True/False) 및 패턴을 포함하여 테넌트 목록에 추가된 모든 차단된 숫자 패턴의 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="25084-121">[Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) returns a list of all blocked number patterns added to the tenant list including Name, Description, Enabled (True/False), and Pattern for each.</span></span>
- <span data-ttu-id="25084-122">[New-CsInboundBlockedNumberPattern은](/powershell/module/skype/new-csinboundblockednumberpattern) 테넌트 목록에 차단된 숫자 패턴을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="25084-122">[New-CsInboundBlockedNumberPattern](/powershell/module/skype/new-csinboundblockednumberpattern) adds a blocked number pattern to the tenant list.</span></span>
- <span data-ttu-id="25084-123">[Remove-CsInboundBlockedNumberPattern은](/powershell/module/skype/remove-csinboundblockednumberpattern) 테넌트 목록에서 차단된 숫자 패턴을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="25084-123">[Remove-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) removes a blocked number pattern from the tenant list.</span></span>
- <span data-ttu-id="25084-124">[Set-CsInboundBlockedNumberPattern은](/powershell/module/skype/set-csinboundblockednumberpattern) 테넌트 목록에서 차단된 숫자 패턴의 하나 이상의 매개 변수를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="25084-124">[Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) modifies one or more parameters of a blocked number pattern in the tenant list.</span></span>

<span data-ttu-id="25084-125">전체 호출 차단 기능을 보고 활성화하는 것은 **Get-and** **Set-CsTenantBlockingCallingNumbers** cmdlet을 통해 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="25084-125">Viewing and activating the entire call blocking feature is managed through the **Get-** and **Set-CsTenantBlockingCallingNumbers** cmdlets.</span></span>

- <span data-ttu-id="25084-126">[Get-CsTenantBlockedCallingNumbers는](/powershell/module/skype/get-cstenantblockedcallingnumbers) 전역 차단 번호 목록에 대한 인바운드 블록 번호 패턴 및 인바운드 면제 번호 패턴 매개 변수를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="25084-126">[Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) returns the inbound block number patterns and the inbound exempt number patterns parameters for the global blocked number list.</span></span> <span data-ttu-id="25084-127">이 cmdlet은 차단이 활성화되어 있는지(True 또는 False)를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="25084-127">This cmdlet also returns whether blocking has been Enabled (True or False).</span></span> <span data-ttu-id="25084-128">기능을 켜거나 끄는 것 이외에 수동으로 수정할 수 없는 단일 전역 테넌트 정책이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25084-128">There's a single global tenant policy that can't be modified manually other than to turn the feature on or off.</span></span>
- <span data-ttu-id="25084-129">[Set-CsTenantBlockedCallingNumbers를](/powershell/module/skype/set-cstenantblockedcallingnumbers) 사용하면 테넌트 수준에서 전역 테넌트 차단된 호출을 설정 및 해제하도록 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25084-129">[Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) allows modifying the global tenant blocked calls to be turned on and off at the tenant level.</span></span>

### <a name="examples"></a><span data-ttu-id="25084-130">예제</span><span class="sxs-lookup"><span data-stu-id="25084-130">Examples</span></span>

#### <a name="block-a-number"></a><span data-ttu-id="25084-131">숫자 차단</span><span class="sxs-lookup"><span data-stu-id="25084-131">Block a number</span></span>

<span data-ttu-id="25084-132">다음 예제에서 테넌트 관리자는 숫자 범위 1(312) 555-0000에서 1(312) 555-9999까지 오는 모든 호출을 차단하려는 경우</span><span class="sxs-lookup"><span data-stu-id="25084-132">In the following example, the tenant administrator wants to block all calls coming from the number range 1 (312) 555-0000 to 1 (312) 555-9999.</span></span> <span data-ttu-id="25084-133">숫자 패턴은 +가 있는 범위의 숫자와 + 도두사 없는 범위의 숫자가 모두 일치하게 만들어 졌습니다.</span><span class="sxs-lookup"><span data-stu-id="25084-133">The number pattern is created so that both numbers in range with + prefixed and numbers in the range without + prefixed are matched.</span></span> <span data-ttu-id="25084-134">시스템이 일치하기 전에 이러한 기호를 스트립하기 때문에 전화 번호에 기호 및 ()를 포함할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="25084-134">You don’t need to include the symbols – and () in the phone numbers because the system strips these symbols before matching.</span></span>  <span data-ttu-id="25084-135">숫자 패턴을 켜기 위해 **사용** 가능 매개 변수가 True로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="25084-135">To turn on the number pattern, the **Enabled** parameter is set to True.</span></span> <span data-ttu-id="25084-136">이 특정 숫자 패턴을 사용하지 않도록 설정하기 위해 매개 변수를 False로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="25084-136">To disable this specific number pattern, set the parameter to False.</span></span>

```PowerShell
New-CsInboundBlockedNumberPattern -Name "BlockRange1" -Enabled $True -Description "Block Contoso" -Pattern "^\+?1312555\d{4}$"
```

<span data-ttu-id="25084-137">다음 예제에서 테넌트 관리자는 숫자 1(412) 555-1234에서 오는 모든 호출을 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="25084-137">In the next example, the tenant administrator wants to block all calls coming from the number 1 (412) 555-1234.</span></span> <span data-ttu-id="25084-138">숫자 패턴을 켜기 위해 **사용** 가능 매개 변수가 True로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="25084-138">To turn on the number pattern, the **Enabled** parameter is set to True.</span></span>

```PowerShell
New-CsInboundBlockedNumberPattern -Name "BlockNumber1" -Enabled $True -Description "Block Fabrikam" -Pattern "^\+?14125551234$"
```

<span data-ttu-id="25084-139">새 패턴을 만들면 기본적으로 사용하도록 설정된 패턴을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="25084-139">Creating a new pattern adds the pattern as enabled by default.</span></span> <span data-ttu-id="25084-140">설명은 자세한 정보를 제공하는 선택적 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="25084-140">The description is an optional field to provide more information.</span></span>

<span data-ttu-id="25084-141">패턴을 추가한 이유를 쉽게 이해할 수 있도록 의미 있는 이름을 제공하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="25084-141">We recommend that you provide a meaningful name to easily understand why the pattern was added.</span></span> <span data-ttu-id="25084-142">스팸 번호를 차단하는 경우 규칙의 이름을 일치되는 숫자 패턴과 동일하게 이름을 매기고 필요한 경우 설명에 추가 정보를 추가하는 것이 고려됩니다.</span><span class="sxs-lookup"><span data-stu-id="25084-142">In the case of simply blocking spam numbers, consider naming the rule the same as the number pattern that's being matched and add additional information in the description as required.</span></span>

<span data-ttu-id="25084-143">패턴은 정규식(Regex)을 사용하여 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="25084-143">Patterns are matched using Regular Expressions (Regex).</span></span> <span data-ttu-id="25084-144">자세한 내용은 Regex 사용을 [참조하세요.](#using-regex)</span><span class="sxs-lookup"><span data-stu-id="25084-144">For more information, see [Using Regex](#using-regex).</span></span>

<span data-ttu-id="25084-145">테스트하고 유효성을 검사하기 전에 복제 시간을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="25084-145">Allow time for replication before you test and validate.</span></span> 

#### <a name="allow-a-number"></a><span data-ttu-id="25084-146">숫자 허용</span><span class="sxs-lookup"><span data-stu-id="25084-146">Allow a number</span></span>

<span data-ttu-id="25084-147">차단된 번호 패턴을 제거하여 번호를 호출하도록 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25084-147">You can allow a number to call by removing the blocked number pattern.</span></span> <span data-ttu-id="25084-148">다음 예제에서 테넌트 관리자는 1(412) 555-1234에서 다시 전화를 걸 수 있도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="25084-148">In the following example, the tenant administrator wants to allow 1 (412) 555-1234 to make calls again.</span></span>

```PowerShell
Remove-CsInboundBlockedNumberPattern -Identity "BlockNumber1"
```
 
<span data-ttu-id="25084-149">ID를 알 수 없는 경우 **Get-CsInboundBlockedNumberPattern** cmdlet을 사용하여 먼저 적절한 패턴을 찾고 ID를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="25084-149">If the identity isn't known, use the **Get-CsInboundBlockedNumberPattern** cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="25084-150">그런 다음 **Remove-CsInboundBlockedNumberPattern** cmdlet을 실행하고 적절한 ID 값을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="25084-150">Then, run the **Remove-CsInboundBlockedNumberPattern** cmdlet and pass the appropriate identity value.</span></span>

<span data-ttu-id="25084-151">테스트하고 유효성을 검사하기 전에 복제 시간을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="25084-151">Allow time for replication before you test and validate.</span></span>

#### <a name="view-all-number-patterns"></a><span data-ttu-id="25084-152">모든 숫자 패턴 보기</span><span class="sxs-lookup"><span data-stu-id="25084-152">View all number patterns</span></span>

<span data-ttu-id="25084-153">이 cmdlet을 실행하여 테넌트에 입력된 모든 차단된 숫자 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="25084-153">Running this cmdlet returns a list of all blocked numbers that are entered for a tenant:</span></span>

```powershell
Get-CsInboundBlockedNumberPattern
```

<span data-ttu-id="25084-154">기본 제공 PowerShell 필터링 기능을 사용하여 반환된 값을 필요한 경우 구문 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="25084-154">Use built-in PowerShell filtering abilities to parse the returned values as required.</span></span>

## <a name="add-number-exceptions"></a><span data-ttu-id="25084-155">숫자 예외 추가</span><span class="sxs-lookup"><span data-stu-id="25084-155">Add number exceptions</span></span>

<span data-ttu-id="25084-156">**New-**, **Get-**, **Set-** 및 **Remove-CsInboundExemptNumberPattern** cmdlet을 사용하여 차단된 숫자 패턴에 예외를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25084-156">You can add exceptions to blocked number patterns by using the **New-**, **Get-**, **Set-**, and **Remove-CsInboundExemptNumberPattern** cmdlets.</span></span>

- <span data-ttu-id="25084-157">[New-CsInboundExemptNumberPattern은](/powershell/module/skype/New-CsInboundExemptNumberPattern) 테넌트 목록에 숫자 예외 패턴을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="25084-157">[New-CsInboundExemptNumberPattern](/powershell/module/skype/New-CsInboundExemptNumberPattern) adds a number exception pattern to the tenant list.</span></span> 
- <span data-ttu-id="25084-158">[Get-CsInboundExemptNumberPattern은](/powershell/module/skype/Get-CsInboundExemptNumberPattern) 테넌트 목록에 추가된 모든 숫자 예외 패턴 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="25084-158">[Get-CsInboundExemptNumberPattern](/powershell/module/skype/Get-CsInboundExemptNumberPattern) returns a list of all number exception patterns added to the tenant list.</span></span>
- <span data-ttu-id="25084-159">[Set-CsInboundExemptNumberPattern은](/powershell/module/skype/Set-CsInboundExemptNumberPattern) 테넌트 목록의 숫자 예외 패턴에 하나 이상의 매개 변수를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="25084-159">[Set-CsInboundExemptNumberPattern](/powershell/module/skype/Set-CsInboundExemptNumberPattern) modifies one or more parameters to a number exception pattern in the tenant list.</span></span>
- <span data-ttu-id="25084-160">[Remove-CsInboundExemptNumberPattern은](/powershell/module/skype/Remove-CsInboundExemptNumberPattern) 테넌트 목록에서 숫자 예외 패턴을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="25084-160">[Remove-CsInboundExemptNumberPattern](/powershell/module/skype/Remove-CsInboundExemptNumberPattern) removes a number exception pattern from the tenant list.</span></span>

### <a name="examples"></a><span data-ttu-id="25084-161">예제</span><span class="sxs-lookup"><span data-stu-id="25084-161">Examples</span></span>

#### <a name="add-a-number-exception"></a><span data-ttu-id="25084-162">숫자 예외 추가</span><span class="sxs-lookup"><span data-stu-id="25084-162">Add a number exception</span></span>

<span data-ttu-id="25084-163">다음 예제에서 테넌트 관리자는 위의 예제에서 차단된 범위에 있는 경우에도 전화 번호 1(312) 555-8882 및 1(312) 555-8883으로 테넌트에 전화를 걸 수 있도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="25084-163">In the following example, the tenant administrator wants to allow the phone numbers 1 (312) 555-8882 and 1 (312) 555-8883 to make calls to the tenant, even if these two phone numbers are in the range that has been blocked in the example above.</span></span> <span data-ttu-id="25084-164">이를 사용하도록 설정하려면 다음과 같이 새 숫자 예외 패턴이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="25084-164">To enable this, a new number exception pattern is created as follows:</span></span>

```PowerShell
New-CsInboundExemptNumberPattern  -Identity "AllowContoso1" -Pattern "^\+?1312555888[2|3]$" -Description "Allow Contoso helpdesk" -Enabled $True
```

<span data-ttu-id="25084-165">숫자 패턴을 켜기 위해 **사용** 가능 매개 변수가 True로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="25084-165">To turn on the number pattern, the **Enabled** parameter is set to True.</span></span> <span data-ttu-id="25084-166">이 특정 숫자 패턴을 사용하지 않도록 설정하기 위해 매개 변수를 False로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="25084-166">To disable this specific number pattern, set the parameter to False.</span></span>


#### <a name="view-all-number-exceptions"></a><span data-ttu-id="25084-167">모든 숫자 예외 보기</span><span class="sxs-lookup"><span data-stu-id="25084-167">View all number exceptions</span></span>

<span data-ttu-id="25084-168">이 예제에서는 **ID** 매개 변수가 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="25084-168">In this example, the **Identity** parameter is optional.</span></span> <span data-ttu-id="25084-169">ID **매개** 변수를 지정하지 않으면 이 cmdlet은 테넌트에 입력된 모든 숫자 예외 패턴 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="25084-169">If the **Identity** parameter isn't specified, this cmdlet returns a list of all number exception patterns entered for a tenant.</span></span>
 
```powershell
Get-CsInboundExemptNumberPattern -Identity <String>
```
 
```powershell
Get-CsInboundExemptNumberPattern 
```

#### <a name="modify-a-number-exception"></a><span data-ttu-id="25084-170">숫자 예외 수정</span><span class="sxs-lookup"><span data-stu-id="25084-170">Modify a number exception</span></span>

<span data-ttu-id="25084-171">**Set-CsInboundExemptNumberPattern** cmdlet을 사용하면 주어진 숫자 패턴 ID에 대한 하나 이상의 매개 변수를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25084-171">The **Set-CsInboundExemptNumberPattern** cmdlet lets you modify one or more parameters for a given number pattern identity.</span></span> <span data-ttu-id="25084-172">이 예제에서는 **ID 매개 변수가** 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="25084-172">In this example, the **Identity** parameter is required.</span></span>
 
```powershell
Set-CsInboundExemptNumberPattern -Identity <String> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsInboundExemptNumberPattern -Identity "AllowContoso1" -Enabled $False
```

#### <a name="remove-a-number-exception"></a><span data-ttu-id="25084-173">숫자 예외 제거</span><span class="sxs-lookup"><span data-stu-id="25084-173">Remove a number exception</span></span>

<span data-ttu-id="25084-174">**Remove-CsInboundExemptNumberPattern** cmdlet은 테넌트 목록에서 주어진 숫자 패턴을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="25084-174">The **Remove-CsInboundExemptNumberPattern** cmdlet will remove the given number pattern from the tenant list.</span></span> <span data-ttu-id="25084-175">이 예제에서는 **ID 매개 변수가** 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="25084-175">In this example, the **Identity** parameter is required.</span></span> 

<span data-ttu-id="25084-176">ID를 알 수 없는 경우 **Get-CsInboundExemptNumberPattern** cmdlet을 사용하여 먼저 적절한 패턴을 찾고 ID를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="25084-176">If the identity isn't known, use the **Get-CsInboundExemptNumberPattern** cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="25084-177">그런 다음 **Remove-CsInboundExemptNumberPattern** cmdlet을 실행하고 적절한 ID 값을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="25084-177">Then, run the **Remove-CsInboundExemptNumberPattern** cmdlet and pass the appropriate identity value.</span></span><span data-ttu-id="25084-178">테스트하고 유효성을 검사하기 전에 복제 시간을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="25084-178"> Allow time for replication before you test and validate.</span></span>  

```powershell
Remove-CsInboundExemptNumberPattern -Identity <String>
```

```powershell
Remove-CsInboundExemptNumberPattern -Identity "AllowContoso1"
```

## <a name="test-whether-a-number-is-blocked"></a><span data-ttu-id="25084-179">숫자가 차단된지 여부를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="25084-179">Test whether a number is blocked</span></span>

<span data-ttu-id="25084-180">**Test-CsInboundBlockedNumberPattern** cmdlet을 사용하여 테넌트에서 숫자가 차단되는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25084-180">Use the **Test-CsInboundBlockedNumberPattern** cmdlet to verify whether a number is blocked in the tenant.</span></span>
 
<span data-ttu-id="25084-181">**PhoneNumber** 매개 변수가 필요하며 +, 또는 ()과 같은 추가 문자가 없는 숫자 문자열이 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="25084-181">The **PhoneNumber** parameter is required, and should be a numeric string without any additional characters, such as +, - or ().</span></span> <span data-ttu-id="25084-182">결과 **IsNumberBlocked 매개** 변수는 테넌트에서 숫자가 차단된 경우 True 값을 반환합니다. 매개 변수가 차단되지 않은 경우 False를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="25084-182">The resulting **IsNumberBlocked** parameter returns a value of True if the number is blocked in the tenant; the parameter returns False if it's not blocked.</span></span>

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

### <a name="examples"></a><span data-ttu-id="25084-183">예제</span><span class="sxs-lookup"><span data-stu-id="25084-183">Examples</span></span>

<span data-ttu-id="25084-184">이 예제에서는 전화 번호 1(312) 555-8884가 위에서 만든 면제에 따라 호출할 수 있는 반면, 전화 번호 1(312) 555-8883은 위에서 만든 면제에 따라 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25084-184">In these examples you can see that the phone number 1 (312) 555-8884 is blocked as it should be due to it being in the blocked range above, while the phone number 1 (312) 555-8883 is allowed to call as it should be based on the exemption created above.</span></span>

```PowerShell
Test-CsInboundBlockedNumberPattern -PhoneNumber 13125558884

RunspaceId      : 09537e45-6f0c-4001-8b85-a79002707b0c
httpStatusCode  : NoContent
IsNumberBlocked : True
errorMessage    :

Test-CsInboundBlockedNumberPattern -PhoneNumber 13125558883

RunspaceId      : 09537e45-6f0c-4001-8b85-a79002707b0c
httpStatusCode  : NoContent
IsNumberBlocked : False
errorMessage    :
```

## <a name="using-regex"></a><span data-ttu-id="25084-185">Regex 사용</span><span class="sxs-lookup"><span data-stu-id="25084-185">Using Regex</span></span>

<span data-ttu-id="25084-186">호출자 차단에 대한 패턴 일치는 Regex를 사용하여 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="25084-186">The pattern matching for blocking callers is done by using Regex.</span></span> <span data-ttu-id="25084-187">여러 도구를 온라인으로 사용하여 Regex 패턴 일치의 유효성을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25084-187">Multiple tools are available online to help validate a Regex pattern match.</span></span> <span data-ttu-id="25084-188">Regex 패턴에 익숙하지 않은 경우 기본에 익숙해지기 위해 시간이 걸릴 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="25084-188">If you aren't familiar with Regex patterns, we recommend that you take some time to familiarize yourself with the basics.</span></span> <span data-ttu-id="25084-189">예상 결과를 얻지 못하게하려면 테넌트에 새 차단된 번호 일치를 추가하기 전에 패턴 일치를 유효성 검사하기 위해 도구를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="25084-189">To make sure you get expected results, use a tool for validating pattern matches before you add new blocked number matches to your tenant.</span></span>