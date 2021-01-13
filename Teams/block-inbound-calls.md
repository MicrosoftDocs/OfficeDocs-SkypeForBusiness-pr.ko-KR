---
title: Microsoft Teams에서 인바운드 통화 차단
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
ms.openlocfilehash: ca2f8de5962572a08ab2a0ae7127446d14334c83
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799908"
---
# <a name="block-inbound-calls"></a><span data-ttu-id="67a1a-102">인바운드 호출 차단</span><span class="sxs-lookup"><span data-stu-id="67a1a-102">Block inbound calls</span></span>

<span data-ttu-id="67a1a-103">전화 시스템 직접 라우팅 및 통화 요금제는 PSTN(공용 전환 전화 네트워크)의 인바운드 통화 차단을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="67a1a-103">Phone System Direct Routing and Calling Plans support blocking inbound calls from the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="67a1a-104">이 기능을 사용하면 테넌트에 들어오는 모든 PSTN 호출의 호출자 ID가 일치하는지 목록에 대해 확인할 수 있도록 테넌트 전역 번호 패턴 목록을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67a1a-104">This feature allows a tenant global list of number patterns to be defined so that the caller ID of every incoming PSTN call to the tenant can be checked against the list for a match.</span></span> <span data-ttu-id="67a1a-105">일치하는 경우 들어오는 호출이 거부됩니다.</span><span class="sxs-lookup"><span data-stu-id="67a1a-105">If a match is made, an incoming call is rejected.</span></span>

<span data-ttu-id="67a1a-106">이 인바운드 호출 차단 기능은 PSTN에서 시작하여 테넌트 전역 기준으로만 작동하는 인바운드 호출에서만 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="67a1a-106">This inbound call blocking feature only works on inbound calls that originate from the PSTN and only works on a tenant-global basis.</span></span> <span data-ttu-id="67a1a-107">사용자 기준으로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="67a1a-107">It's not available on a per-user basis.</span></span>  

>[!NOTE]
> <span data-ttu-id="67a1a-108">차단된 호출자는 차단된 경우 약간 다른 동작을 경험할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67a1a-108">Blocked callers may experience slightly different behaviors when they've been blocked.</span></span> <span data-ttu-id="67a1a-109">동작은 차단된 발신자 통신 사업자에서 호출이 성공적으로 완료되지 못했다는 알림을 처리하는 방법을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="67a1a-109">The behavior is based on how the blocked caller’s carrier handles the notification that the call isn't allowed to be successfully completed.</span></span> <span data-ttu-id="67a1a-110">예를 들어 통화를 전화로 완료할 수 없다고 말하는 통신사 메시지 또는 단순히 통화를 떨어뜨리는 메시지가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67a1a-110">Examples may include a carrier message stating the call can't be completed as dialed, or simply dropping the call.</span></span>

## <a name="call-blocking-admin-controls-and-information"></a><span data-ttu-id="67a1a-111">통화 차단 관리자 컨트롤 및 정보</span><span class="sxs-lookup"><span data-stu-id="67a1a-111">Call blocking admin controls and information</span></span>

<span data-ttu-id="67a1a-112">숫자 차단에 대한 관리자 컨트롤은 PowerShell만 사용하여 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="67a1a-112">Admin controls for blocking numbers are provided using PowerShell only.</span></span> <span data-ttu-id="67a1a-113">숫자 블록 패턴은 정규식 패턴으로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="67a1a-113">Number block patterns are defined as regular expression patterns.</span></span> <span data-ttu-id="67a1a-114">식의 순서는 불확실합니다. 목록에서 첫 번째 패턴이 일치하여 호출이 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="67a1a-114">The order of the expressions is unimportant – the first pattern matched in the list results in the call being blocked.</span></span> <span data-ttu-id="67a1a-115">차단된 호출자 목록에서 추가 또는 제거된 새 번호 또는 패턴은 패턴이 활성화되는 데 최대 24시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67a1a-115">A new number or pattern that's added or removed in the blocked callers list may take up to 24 hours for the pattern to become active.</span></span>

## <a name="call-blocking-powershell-commands"></a><span data-ttu-id="67a1a-116">통화 차단 PowerShell 명령</span><span class="sxs-lookup"><span data-stu-id="67a1a-116">Call blocking PowerShell commands</span></span>

<span data-ttu-id="67a1a-117">새로 고치기, Get,  **Set,**   - **CsInboundBlockedNumberPattern** cmdlet을 사용하여 숫자 패턴을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="67a1a-117">You manage number patterns by using the **New**, **Get**, **Set**, **Remove** -**CsInboundBlockedNumberPattern** cmdlets.</span></span> <span data-ttu-id="67a1a-118">특정 패턴의 활성화를 전환하는 기능을 포함하여 이러한 cmdlet을 사용하여 주어진 패턴을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67a1a-118">You can manage a given pattern by using these cmdlets, including the ability to toggle the activation of a given pattern.</span></span>

- <span data-ttu-id="67a1a-119">[Get-CsInboundBlockedNumberPattern은](https://docs.microsoft.com/powershell/module/skype/get-csinboundblockednumberpattern) 각각에 대한 이름, 설명, 사용(True/False) 및 패턴을 포함하여 테넌트 목록에 추가된 모든 차단된 번호 패턴 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="67a1a-119">[Get-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/get-csinboundblockednumberpattern) returns a list of all blocked number patterns added to the tenant list including Name, Description, Enabled (True/False), and Pattern for each.</span></span>
- <span data-ttu-id="67a1a-120">[New-CsInboundBlockedNumberPattern은](https://docs.microsoft.com/powershell/module/skype/new-csinboundblockednumberpattern) 차단된 숫자 패턴을 테넌트 목록에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="67a1a-120">[New-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/new-csinboundblockednumberpattern) adds a blocked number pattern to the tenant list.</span></span>
- <span data-ttu-id="67a1a-121">[Remove-CsInboundBlockedNumberPattern은](https://docs.microsoft.com/powershell/module/skype/remove-csinboundblockednumberpattern) 테넌트 목록에서 차단된 숫자 패턴을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="67a1a-121">[Remove-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/remove-csinboundblockednumberpattern) removes a blocked number pattern from the tenant list.</span></span>
- <span data-ttu-id="67a1a-122">[Set-CsInboundBlockedNumberPattern은](https://docs.microsoft.com/powershell/module/skype/set-csinboundblockednumberpattern) 테넌트 목록에서 차단된 숫자 패턴의 매개 변수를 하나 이상 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="67a1a-122">[Set-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/set-csinboundblockednumberpattern) modifies one or more parameters of a blocked number pattern in the tenant list.</span></span>

<span data-ttu-id="67a1a-123">전체 호출 차단 기능 보기 및 활성화는 **Get,** **Set**  - **CsTenantBlockingCallingNumbers** cmdlet을 통해 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="67a1a-123">Viewing and activating the entire call blocking feature is managed through the **Get**, **Set** -**CsTenantBlockingCallingNumbers** cmdlets.</span></span>

- <span data-ttu-id="67a1a-124">[Get-CsTenantBlockedCallingNumbers는](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockedcallingnumbers) Enabled(True/False)를 포함하여 전역 차단된 번호 목록에 대한 매개 변수를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="67a1a-124">[Get-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockedcallingnumbers) returns the parameters for the global blocked number list including Enabled (True/False).</span></span> <span data-ttu-id="67a1a-125">기능을 켜거나 끄는 것 이외에는 수동으로 수정할 수 없는 단일 전역 테넌트 정책이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67a1a-125">There's a single global tenant policy that can't be modified manually other than to turn the feature on or off.</span></span>
- <span data-ttu-id="67a1a-126">[Set-CsTenantBlockedCallingNumbers를](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockedcallingnumbers) 사용하면 테넌트 수준에서 전역 테넌트 차단 호출을 설정 및 해제하도록 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67a1a-126">[Set-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockedcallingnumbers) allows modifying the global tenant blocked calls to be turned on and off at the tenant level.</span></span>

### <a name="examples"></a><span data-ttu-id="67a1a-127">예제</span><span class="sxs-lookup"><span data-stu-id="67a1a-127">Examples</span></span>

#### <a name="block-a-number"></a><span data-ttu-id="67a1a-128">숫자 차단</span><span class="sxs-lookup"><span data-stu-id="67a1a-128">Block a number</span></span>

<span data-ttu-id="67a1a-129">이 예제에서 **Enabled** 및 **Description** 매개 변수는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="67a1a-129">In this example, the **Enabled** and **Description** parameters are optional.</span></span>

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

<span data-ttu-id="67a1a-130">새 패턴을 만들면 패턴이 기본적으로 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="67a1a-130">Creating a new pattern adds the pattern as enabled by default.</span></span> <span data-ttu-id="67a1a-131">설명은 자세한 정보를 제공하는 선택적 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="67a1a-131">The description is an optional field to provide more information.</span></span>

<span data-ttu-id="67a1a-132">패턴이 추가된 이유를 쉽게 이해할 수 있도록 의미 있는 이름을 제공하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="67a1a-132">We recommend that you provide a meaningful name to easily understand why the pattern was added.</span></span> <span data-ttu-id="67a1a-133">스팸 번호를 차단하는 경우 규칙의 이름을 일치되는 숫자 패턴과 동일하게 이름을 정하고 필요한 경우 설명에 추가 정보를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="67a1a-133">In the case of simply blocking spam numbers, consider naming the rule the same as the number pattern that's being matched and add additional information in the description as required.</span></span>

<span data-ttu-id="67a1a-134">패턴은 정규식(Regex)을 사용하여 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="67a1a-134">Patterns are matched using Regular Expressions (Regex).</span></span> <span data-ttu-id="67a1a-135">복제를 테스트하고 유효성을 검사하기 전에 시간을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="67a1a-135">Allow time for replication before you test and validate.</span></span>

#### <a name="allow-a-number"></a><span data-ttu-id="67a1a-136">숫자 허용</span><span class="sxs-lookup"><span data-stu-id="67a1a-136">Allow a number</span></span>

<span data-ttu-id="67a1a-137">이 예제에서는 ID 매개 **변수가** 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="67a1a-137">In this example, the **Identity** parameter is required.</span></span>

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```
 
<span data-ttu-id="67a1a-138">ID를 알 수 없는 경우 **Get-CsInboundBlockedNumberPattern** cmdlet을 사용하여 먼저 적절한 패턴을 찾고 ID를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="67a1a-138">If the identity isn't known, use the **Get-CsInboundBlockedNumberPattern** cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="67a1a-139">그런 다음 **Remove-CsTenantBlockedNumberPattern** cmdlet을 실행하고 적절한 ID 값을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="67a1a-139">Then, run the **Remove-CsTenantBlockedNumberPattern** cmdlet and pass the appropriate identity value.</span></span>

<span data-ttu-id="67a1a-140">복제를 테스트하고 유효성을 검사하기 전에 시간을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="67a1a-140">Allow time for replication before you test and validate.</span></span>

#### <a name="view-all-number-patterns"></a><span data-ttu-id="67a1a-141">모든 숫자 패턴 보기</span><span class="sxs-lookup"><span data-stu-id="67a1a-141">View all number patterns</span></span>

<span data-ttu-id="67a1a-142">이 cmdlet을 실행하여 테넌트에 입력된 모든 차단된 번호 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="67a1a-142">Running this cmdlet returns a list of all blocked numbers that are entered for a tenant:</span></span>

```powershell
Get-CsInboundBlockedNumberPattern
```

<span data-ttu-id="67a1a-143">기본 제공 PowerShell 필터링 기능을 사용하여 필요한 경우 반환된 값을 구문 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="67a1a-143">Use built-in PowerShell filtering abilities to parse the returned values as required.</span></span>

## <a name="add-number-exceptions"></a><span data-ttu-id="67a1a-144">숫자 예외 추가</span><span class="sxs-lookup"><span data-stu-id="67a1a-144">Add number exceptions</span></span>

<span data-ttu-id="67a1a-145">New,  **Get,** **Set,** **Remove**  - **CsTenantBlockNumberExceptionPattern** cmdlet을 사용하여 차단된 숫자 패턴에 예외를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67a1a-145">You can add exceptions to blocked number patterns by using the **New**, **Get**, **Set**, **Remove** -**CsTenantBlockNumberExceptionPattern** cmdlets.</span></span>

- <span data-ttu-id="67a1a-146">[New-CsTenantBlockedNumberExceptionPattern은](https://docs.microsoft.com/powershell/module/skype/new-cstenantblockednumberexceptionpattern) 테넌트 목록에 숫자 예외 패턴을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="67a1a-146">[New-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/new-cstenantblockednumberexceptionpattern) adds a number exception pattern to the tenant list.</span></span> 
- <span data-ttu-id="67a1a-147">[Get-CsTenantBlockedNumberExceptionPattern은](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockednumberexceptionpattern) 테넌트 목록에 추가된 모든 숫자 예외 패턴 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="67a1a-147">[Get-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockednumberexceptionpattern) returns a list of all number exception patterns added to the tenant list.</span></span>
- <span data-ttu-id="67a1a-148">[Set-CsTenantBlockedNumberExceptionPattern은](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockednumberexceptionpattern) 하나 이상의 매개 변수를 테넌트 목록의 숫자 예외 패턴으로 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="67a1a-148">[Set-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockednumberexceptionpattern) modifies one or more parameters to a number exception pattern in the tenant list.</span></span>
- <span data-ttu-id="67a1a-149">[Remove-CsTenantBlockedNumberExceptionPattern은](https://docs.microsoft.com/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) 테넌트 목록에서 숫자 예외 패턴을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="67a1a-149">[Remove-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) removes a number exception pattern from the tenant list.</span></span>

### <a name="examples"></a><span data-ttu-id="67a1a-150">예제</span><span class="sxs-lookup"><span data-stu-id="67a1a-150">Examples</span></span>

#### <a name="add-a-number-exception"></a><span data-ttu-id="67a1a-151">숫자 예외 추가</span><span class="sxs-lookup"><span data-stu-id="67a1a-151">Add a number exception</span></span>

<span data-ttu-id="67a1a-152">이 예제에서는 새 숫자 예외 패턴이 만들어지며 기본적으로 패턴을 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="67a1a-152">In this example, a new number exception pattern is created and will by default add the pattern as enabled.</span></span> <span data-ttu-id="67a1a-153">Enabled **및** Description 매개 **변수는** 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="67a1a-153">The **Enabled** and **Description** parameters are optional.</span></span>

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"  
```

#### <a name="view-all-number-exceptions"></a><span data-ttu-id="67a1a-154">모든 숫자 예외 보기</span><span class="sxs-lookup"><span data-stu-id="67a1a-154">View all number exceptions</span></span>

<span data-ttu-id="67a1a-155">이 예제에서 ID 매개 **변수는** 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="67a1a-155">In this example, the **Identity** parameter is optional.</span></span> <span data-ttu-id="67a1a-156">ID **매개** 변수를 지정하지 않으면 이 cmdlet은 테넌트에 대해 입력된 모든 숫자 예외 패턴 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="67a1a-156">If the **Identity** parameter isn't specified, this cmdlet returns a list of all number exception patterns entered for a tenant.</span></span>
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a><span data-ttu-id="67a1a-157">숫자 예외 수정</span><span class="sxs-lookup"><span data-stu-id="67a1a-157">Modify a number exception</span></span>

<span data-ttu-id="67a1a-158">이 예제에서는 ID 매개 **변수가** 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="67a1a-158">In this example, the **Identity** parameter is mandatory.</span></span> <span data-ttu-id="67a1a-159">**Set-CsTenantBlockedNumberExceptionPattern** cmdlet을 사용하면 주어진 숫자 패턴 ID에 대해 하나 이상의 매개 변수를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67a1a-159">The **Set-CsTenantBlockedNumberExceptionPattern** cmdlet lets you modify one or more parameters for a given number pattern identity.</span></span>
 
```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$" 
```

#### <a name="remove-a-number-exception"></a><span data-ttu-id="67a1a-160">숫자 예외 제거</span><span class="sxs-lookup"><span data-stu-id="67a1a-160">Remove a number exception</span></span>

<span data-ttu-id="67a1a-161">이 예제에서는 ID 매개 **변수가** 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="67a1a-161">In this example, the **Identity** parameter is required.</span></span> <span data-ttu-id="67a1a-162">이 cmdlet은 테넌트 목록에서 주어진 숫자 패턴을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="67a1a-162">This cmdlet will remove the given number pattern from the tenant list.</span></span>  <span data-ttu-id="67a1a-163">ID를 알 수 없는 경우 **Get-CsInboundBlockedNumberPattern** cmdlet을 사용하여 먼저 적절한 패턴을 찾고 ID를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="67a1a-163">If the identity isn't known, use the **Get-CsInboundBlockedNumberPattern** cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="67a1a-164">그런 다음 **Remove-CsTenantBlockedNumberExceptionPattern** cmdlet을 실행하고 적절한 ID 값을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="67a1a-164">Then, run the **Remove-CsTenantBlockedNumberExceptionPattern** cmdlet and pass the appropriate identity value.</span></span><span data-ttu-id="67a1a-165">복제를 테스트하고 유효성을 검사하기 전에 시간을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="67a1a-165"> Allow time for replication before you test and validate.</span></span>  

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a><span data-ttu-id="67a1a-166">숫자가 차단되는지 테스트</span><span class="sxs-lookup"><span data-stu-id="67a1a-166">Test whether a number is blocked</span></span>

<span data-ttu-id="67a1a-167">**Test-CsInboundBlockedNumberPattern** cmdlet을 사용하여 테넌트에서 숫자가 차단되는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67a1a-167">Use the **Test-CsInboundBlockedNumberPattern** cmdlet to verify whether a number is blocked in the tenant.</span></span>
 
<span data-ttu-id="67a1a-168">이 예제에서는 **PhoneNumber** 및 **테넌트** 매개 변수가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="67a1a-168">In this example, the **PhoneNumber** and **Tenant** parameters are required.</span></span> <span data-ttu-id="67a1a-169">**PhoneNumber** 매개 변수는 + 또는 -와 같은 추가 문자가 없는 숫자 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="67a1a-169">The **PhoneNumber** parameter should be a numeric string without any additional characters such as + or -.</span></span> <span data-ttu-id="67a1a-170">TRPS에서 **테넌트** 매개 변수는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="67a1a-170">In TRPS, the **Tenant parameter** is optional.</span></span> <span data-ttu-id="67a1a-171">결과 **isNumberBlocked** 매개 변수는 테넌트에서 숫자가 차단된 경우 True 값을 반환하고, 차단되지 않은 경우 False를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="67a1a-171">The resulting **isNumberBlocked** parameter returns a value of True if the number is blocked in the tenant and False if it's not blocked.</span></span>

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 4255550101
```

|<span data-ttu-id="67a1a-172">httpResponseCode</span><span class="sxs-lookup"><span data-stu-id="67a1a-172">httpResponseCode</span></span>  |<span data-ttu-id="67a1a-173">isNumberBlocked</span><span class="sxs-lookup"><span data-stu-id="67a1a-173">isNumberBlocked</span></span>   |<span data-ttu-id="67a1a-174">errorMessage</span><span class="sxs-lookup"><span data-stu-id="67a1a-174">errorMessage</span></span> |
|---------|---------|---------|
|<span data-ttu-id="67a1a-175">200</span><span class="sxs-lookup"><span data-stu-id="67a1a-175">200</span></span>    | <span data-ttu-id="67a1a-176">True</span><span class="sxs-lookup"><span data-stu-id="67a1a-176">True</span></span>        |         |

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 6045550188
```

|<span data-ttu-id="67a1a-177">httpResponseCode</span><span class="sxs-lookup"><span data-stu-id="67a1a-177">httpResponseCode</span></span>  |<span data-ttu-id="67a1a-178">isNumberBlocked</span><span class="sxs-lookup"><span data-stu-id="67a1a-178">isNumberBlocked</span></span>   |<span data-ttu-id="67a1a-179">errorMessage</span><span class="sxs-lookup"><span data-stu-id="67a1a-179">errorMessage</span></span> |
|---------|---------|---------|
|<span data-ttu-id="67a1a-180">200</span><span class="sxs-lookup"><span data-stu-id="67a1a-180">200</span></span>    | <span data-ttu-id="67a1a-181">False</span><span class="sxs-lookup"><span data-stu-id="67a1a-181">False</span></span>        |         |

## <a name="a-note-about-regex"></a><span data-ttu-id="67a1a-182">Regex에 대한 참고 사항</span><span class="sxs-lookup"><span data-stu-id="67a1a-182">A note about Regex</span></span>

<span data-ttu-id="67a1a-183">앞에서 설명한 대로 호출자 차단에 대한 패턴 일치는 Regex를 사용하여 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="67a1a-183">As stated earlier, the pattern matching for blocking callers is done by using Regex.</span></span> <span data-ttu-id="67a1a-184">여러 도구를 온라인으로 사용하여 Regex 패턴 일치의 유효성을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67a1a-184">Multiple tools are available online to help validate a Regex pattern match.</span></span> <span data-ttu-id="67a1a-185">Regex 패턴에 익숙하지 않은 경우 기본에 익숙해지기 위해 다소 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67a1a-185">If you aren't familiar with Regex patterns, we recommend that you take some time to familiarize yourself with the basics.</span></span> <span data-ttu-id="67a1a-186">예상된 결과를 얻습니다. 테넌트에 차단된 숫자 일치를 새로 추가하기 전에 패턴 일치의 유효성을 검사하는 도구를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="67a1a-186">To make sure you get expected results, use a tool for validating pattern matches before you add new blocked number matches to your tenant.</span></span>
