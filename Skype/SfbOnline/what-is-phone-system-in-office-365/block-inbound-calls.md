---
title: 온라인에서 인바운드 비즈니스용 Skype 차단
ms.author: v-cichur
author: cichur
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
audience: Admin
ms.reviewer: roykuntz
appliesto:
- Skype for Business
localization_priority: Normal
ms.custom: Learn how to use PowerShell to manage inbound call blocking in Skype for Business Online.
ms.openlocfilehash: dae0d585df2f67904712e9220f16213a2f925369
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238034"
---
# <a name="block-inbound-calls"></a><span data-ttu-id="ae3c0-102">인바운드 호출 차단</span><span class="sxs-lookup"><span data-stu-id="ae3c0-102">Block inbound calls</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="ae3c0-103">비즈니스용 Skype 이제 온라인 통화 계획은 공용 PSTN(공용 전화 네트워크)에서 인바운드 호출 차단을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="ae3c0-103">Skype for Business Online Calling Plans now supports blocking of inbound calls from the public switched telephone network (PSTN).</span></span> <span data-ttu-id="ae3c0-104">이 기능을 사용하면 테넌트에 들어오는 모든 PSTN 호출의 발신자 ID를 일치하는 목록에 대해 확인할 수 있도록 테넌트 전역 번호 패턴 목록을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae3c0-104">This feature allows a tenant global list of number patterns to be defined so that the caller ID of every incoming PSTN call to the tenant can be checked against the list for a match.</span></span> <span data-ttu-id="ae3c0-105">일치하는 경우 들어오는 호출이 거부됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae3c0-105">If a match is made, an incoming call is rejected.</span></span>

<span data-ttu-id="ae3c0-106">이 인바운드 호출 차단 기능은 PSTN에서 시작된 인바운드 호출에만 작동하며 테넌트 전역 기준으로만 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="ae3c0-106">This inbound call blocking feature only works on inbound calls that originate from the PSTN and only works on a tenant-global basis.</span></span> <span data-ttu-id="ae3c0-107">사용자당 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ae3c0-107">It's not available on a per-user basis.</span></span>  

<span data-ttu-id="ae3c0-108">이 기능은 아직 직접 라우팅에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ae3c0-108">This feature isn't yet available for Direct Routing.</span></span>

>[!NOTE]
> <span data-ttu-id="ae3c0-109">차단된 호출자는 차단된 경우 약간 다른 동작을 경험할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae3c0-109">Blocked callers may experience slightly different behaviors when they have been blocked.</span></span> <span data-ttu-id="ae3c0-110">동작은 차단된 발신자 통신사가 호출을 성공적으로 완료할 수 없습니다는 알림을 처리하는 방법을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae3c0-110">The behavior is based on how the blocked caller’s carrier handles the notification that the call isn't allowed to be successfully completed.</span></span> <span data-ttu-id="ae3c0-111">예를 들어 전화를 걸 때 통화를 완료할 수 없다거나 단순히 전화를 떨어뜨렸다는 통신사 메시지가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae3c0-111">Examples may include a carrier message stating the call can't be completed as dialed, or simply dropping the call.</span></span>

## <a name="call-blocking-admin-controls-and-information"></a><span data-ttu-id="ae3c0-112">관리자 제어 및 정보 차단 호출</span><span class="sxs-lookup"><span data-stu-id="ae3c0-112">Call blocking admin controls and information</span></span>

<span data-ttu-id="ae3c0-113">차단 번호에 대한 관리자 컨트롤은 PowerShell을 사용하여만 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae3c0-113">Admin controls for blocking numbers are provided using PowerShell only.</span></span> <span data-ttu-id="ae3c0-114">숫자 블록 패턴은 정규식 패턴으로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae3c0-114">Number block patterns are defined as regular expression patterns.</span></span> <span data-ttu-id="ae3c0-115">식의 순서는 무의미합니다. 목록에서 일치하는 첫 번째 패턴은 호출이 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae3c0-115">The order of the expressions is unimportant – the first pattern matched in the list results in the call being blocked.</span></span> <span data-ttu-id="ae3c0-116">차단된 호출자 목록에 추가되거나 제거된 새 번호 또는 패턴은 패턴이 활성화되는 데 최대 24시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae3c0-116">A new number or pattern that's added or removed in the blocked callers list may take up to 24 hours for the pattern to become active.</span></span>

## <a name="call-blocking-powershell-commands"></a><span data-ttu-id="ae3c0-117">PowerShell 명령 차단 호출</span><span class="sxs-lookup"><span data-stu-id="ae3c0-117">Call blocking PowerShell commands</span></span>

<span data-ttu-id="ae3c0-118">숫자 패턴은 명령, , 및 를 통해 ```CsInboundBlockedNumberPattern``` ```New``` ```Get``` ```Set``` ```Remove``` 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae3c0-118">Number patterns are managed through the ```CsInboundBlockedNumberPattern``` commands ```New```, ```Get```, ```Set```, and ```Remove```.</span></span> <span data-ttu-id="ae3c0-119">특정 패턴의 활성화를 전환하는 기능을 포함하여 이러한 cmdlet을 사용하여 주어진 패턴을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae3c0-119">You can manage a given pattern by using these cmdlets, including the ability to toggle the activation of a given pattern.</span></span>
- <span data-ttu-id="ae3c0-120">[Get-CsInboundBlockedNumberPattern은](/powershell/module/skype/get-csinboundblockednumberpattern) 각각에 대한 이름, 설명, 사용 가능(True/False) 및 패턴을 포함하여 테넌트 목록에 추가된 모든 차단된 숫자 패턴의 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ae3c0-120">[Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) returns a list of all blocked number patterns added to the tenant list including Name, Description, Enabled (True/False), and Pattern for each.</span></span>
- <span data-ttu-id="ae3c0-121">[New-CsInboundBlockedNumberPattern은](/powershell/module/skype/new-csinboundblockednumberpattern) 테넌트 목록에 차단된 숫자 패턴을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ae3c0-121">[New-CsInboundBlockedNumberPattern](/powershell/module/skype/new-csinboundblockednumberpattern) adds a blocked number pattern to the tenant list.</span></span>
- <span data-ttu-id="ae3c0-122">[Remove-CsInboundBlockedNumberPattern은](/powershell/module/skype/remove-csinboundblockednumberpattern) 테넌트 목록에서 차단된 숫자 패턴을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="ae3c0-122">[Remove-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) removes a blocked number pattern from the tenant list.</span></span>
- <span data-ttu-id="ae3c0-123">[Set-CsInboundBlockedNumberPattern은](/powershell/module/skype/set-csinboundblockednumberpattern) 테넌트 목록에서 차단된 숫자 패턴의 하나 이상의 매개 변수를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="ae3c0-123">[Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) modifies one or more parameters of a blocked number pattern in the tenant list.</span></span>

<span data-ttu-id="ae3c0-124">전체 호출 차단 기능을 보고 활성화하는 것은 명령 및 를 통해 ```CsTenantBlockingCallingNumbers``` ```Get``` ```Set``` 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae3c0-124">Viewing and activating the entire call blocking feature is managed through the ```CsTenantBlockingCallingNumbers``` commands ```Get``` and ```Set```.</span></span>

- <span data-ttu-id="ae3c0-125">[Get-CsTenantBlockedCallingNumbers는](/powershell/module/skype/get-cstenantblockedcallingnumbers) 사용(True/False)을 포함하여 전역 차단된 번호 목록에 대한 매개 변수를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ae3c0-125">[Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) returns the parameters for the global blocked number list including Enabled (True/False).</span></span> <span data-ttu-id="ae3c0-126">기능을 켜거나 끄는 것 이외에 수동으로 수정할 수 없는 단일 전역 테넌트 정책이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae3c0-126">There's a single global tenant policy that can't be modified manually other than to turn the feature on or off.</span></span>
- <span data-ttu-id="ae3c0-127">[Set-CsTenantBlockedCallingNumbers를](/powershell/module/skype/set-cstenantblockedcallingnumbers) 사용하면 테넌트 수준에서 전역 테넌트 차단된 호출을 설정 및 해제하도록 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae3c0-127">[Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) allows modifying the global tenant blocked calls to be turned on and off at the tenant level.</span></span>

### <a name="examples"></a><span data-ttu-id="ae3c0-128">예제</span><span class="sxs-lookup"><span data-stu-id="ae3c0-128">Examples</span></span>

#### <a name="block-a-number"></a><span data-ttu-id="ae3c0-129">숫자 차단</span><span class="sxs-lookup"><span data-stu-id="ae3c0-129">Block a number</span></span>

<span data-ttu-id="ae3c0-130">이 예제에서는 ```-Enabled``` 및 매개 ```-Description``` 변수는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="ae3c0-130">In this example, the ```-Enabled``` and ```-Description``` parameters are optional:</span></span>

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

<span data-ttu-id="ae3c0-131">새 패턴을 만들면 기본적으로 사용하도록 설정된 패턴을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ae3c0-131">Creating a new pattern adds the pattern as enabled by default.</span></span> <span data-ttu-id="ae3c0-132">설명은 자세한 정보를 제공하는 선택적 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="ae3c0-132">The description is an optional field to provide more information.</span></span>

<span data-ttu-id="ae3c0-133">패턴을 추가한 이유를 쉽게 이해할 수 있도록 의미 있는 이름을 제공하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ae3c0-133">We recommend that you provide a meaningful name to easily understand why the pattern was added.</span></span> <span data-ttu-id="ae3c0-134">스팸 번호를 차단하는 경우 규칙의 이름을 일치되는 숫자 패턴과 동일하게 이름을 매기고 필요한 경우 설명에 추가 정보를 추가하는 것이 고려됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae3c0-134">In the case of simply blocking spam numbers, consider naming the rule the same as the number pattern that's being matched and add additional information in the description as required.</span></span>

<span data-ttu-id="ae3c0-135">패턴은 정규식(Regex)을 사용하여 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="ae3c0-135">Patterns are matched using Regular Expressions (Regex).</span></span> <span data-ttu-id="ae3c0-136">테스트하고 유효성을 검사하기 전에 복제 시간을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="ae3c0-136">Allow time for replication before you test and validate.</span></span>

#### <a name="allow-a-number"></a><span data-ttu-id="ae3c0-137">숫자 허용</span><span class="sxs-lookup"><span data-stu-id="ae3c0-137">Allow a number</span></span>

<span data-ttu-id="ae3c0-138">이 예제에서는 ```-Identity``` 매개 변수가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ae3c0-138">In this example, the ```-Identity``` parameter is required:</span></span>

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```
 
<span data-ttu-id="ae3c0-139">ID를 알 수 없는 경우 cmdlet을 사용하여 먼저 적절한 패턴을 찾고 ```Get-CsInboundBlockedNumberPattern``` ID를 적어 냅니다.</span><span class="sxs-lookup"><span data-stu-id="ae3c0-139">If the identity isn't known, use the ```Get-CsInboundBlockedNumberPattern``` cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="ae3c0-140">그런 다음 ```Remove-CsTenantBlockedNumberPattern``` cmdlet을 실행하고 적절한 ID 값을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="ae3c0-140">Then, run the ```Remove-CsTenantBlockedNumberPattern``` cmdlet and pass the appropriate identity value.</span></span>

<span data-ttu-id="ae3c0-141">테스트하고 유효성을 검사하기 전에 복제 시간을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="ae3c0-141">Allow time for replication before you test and validate.</span></span>

#### <a name="view-all-number-patterns"></a><span data-ttu-id="ae3c0-142">모든 숫자 패턴 보기</span><span class="sxs-lookup"><span data-stu-id="ae3c0-142">View all number patterns</span></span>

<span data-ttu-id="ae3c0-143">이 cmdlet을 실행하여 테넌트에 입력된 모든 차단된 숫자 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ae3c0-143">Running this cmdlet returns a list of all blocked numbers that are entered for a tenant:</span></span>

```powershell
Get-CsInboundBlockedNumberPattern
```

<span data-ttu-id="ae3c0-144">기본 제공 PowerShell 필터링 기능을 사용하여 반환된 값을 필요한 경우 구문 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="ae3c0-144">Use built-in PowerShell filtering abilities to parse the returned values as required.</span></span>

## <a name="add-number-exceptions"></a><span data-ttu-id="ae3c0-145">숫자 예외 추가</span><span class="sxs-lookup"><span data-stu-id="ae3c0-145">Add number exceptions</span></span>

<span data-ttu-id="ae3c0-146">명령을 통해 차단된 숫자 패턴에 예외를 추가할 수 ```CsTenantBlockNumberExceptionPattern``` ```New``` ```Get``` ```Set``` ```Remove``` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae3c0-146">You can add exceptions to blocked number patterns through the ```CsTenantBlockNumberExceptionPattern``` commands, ```New```, ```Get```, ```Set```, and ```Remove```.</span></span>

- <span data-ttu-id="ae3c0-147">[New-CsTenantBlockedNumberExceptionPattern은](/powershell/module/skype/new-cstenantblockednumberexceptionpattern) 테넌트 목록에 숫자 예외 패턴을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ae3c0-147">[New-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/new-cstenantblockednumberexceptionpattern) adds a number exception pattern to the tenant list.</span></span> 
- <span data-ttu-id="ae3c0-148">[Get-CsTenantBlockedNumberExceptionPattern은](/powershell/module/skype/get-cstenantblockednumberexceptionpattern) 테넌트 목록에 추가된 모든 숫자 예외 패턴 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ae3c0-148">[Get-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/get-cstenantblockednumberexceptionpattern) returns a list of all number exception patterns added to the tenant list.</span></span>
- <span data-ttu-id="ae3c0-149">[Set-CsTenantBlockedNumberExceptionPattern은](/powershell/module/skype/set-cstenantblockednumberexceptionpattern) 테넌트 목록의 숫자 예외 패턴에 하나 이상의 매개 변수를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="ae3c0-149">[Set-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/set-cstenantblockednumberexceptionpattern) modifies one or more parameters to a number exception pattern in the tenant list.</span></span>
- <span data-ttu-id="ae3c0-150">[Remove-CsTenantBlockedNumberExceptionPattern은](/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) 테넌트 목록에서 숫자 예외 패턴을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="ae3c0-150">[Remove-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) removes a number exception pattern from the tenant list.</span></span>

### <a name="examples"></a><span data-ttu-id="ae3c0-151">예제</span><span class="sxs-lookup"><span data-stu-id="ae3c0-151">Examples</span></span>

#### <a name="add-a-number-exception"></a><span data-ttu-id="ae3c0-152">숫자 예외 추가</span><span class="sxs-lookup"><span data-stu-id="ae3c0-152">Add a number exception</span></span>

<span data-ttu-id="ae3c0-153">이 예제에서는 새 숫자 예외 패턴이 만들어지며 기본적으로 사용 가능한 패턴을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ae3c0-153">In this example, a new number exception pattern is created and will by default add the pattern as enabled.</span></span> <span data-ttu-id="ae3c0-154">및 ```-Enabled``` ```-Description``` 매개 변수는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="ae3c0-154">The ```-Enabled``` and ```-Description``` parameters are optional.</span></span>

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"  
```

#### <a name="view-all-number-exceptions"></a><span data-ttu-id="ae3c0-155">모든 숫자 예외 보기</span><span class="sxs-lookup"><span data-stu-id="ae3c0-155">View all number exceptions</span></span>

<span data-ttu-id="ae3c0-156">이 예제에서는 -Identity 매개 변수가 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="ae3c0-156">In this example, the -Identity parameter is optional.</span></span> <span data-ttu-id="ae3c0-157">매개 변수를 지정하지 않으면 이 cmdlet은 테넌트에 입력된 모든 숫자 예외 패턴 목록을 ```-Identity``` 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ae3c0-157">If the ```-Identity``` parameter isn't specified, this cmdlet returns a list of all number exception patterns entered for a tenant.</span></span>
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a><span data-ttu-id="ae3c0-158">숫자 예외 수정</span><span class="sxs-lookup"><span data-stu-id="ae3c0-158">Modify a number exception</span></span>

<span data-ttu-id="ae3c0-159">이 예제에서는 -Identity 매개 변수가 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="ae3c0-159">In this example, the -Identity parameter is mandatory.</span></span> <span data-ttu-id="ae3c0-160">cmdlet을 사용하면 주어진 숫자 패턴 ID에 대해 하나 이상의 매개 ```Set-CsTenantBlockedNumberExceptionPattern``` 변수를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae3c0-160">The ```Set-CsTenantBlockedNumberExceptionPattern``` cmdlet lets you modify one or more parameters for a given number pattern identity.</span></span>
 
```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$" 
```

#### <a name="remove-a-number-exception"></a><span data-ttu-id="ae3c0-161">숫자 예외 제거</span><span class="sxs-lookup"><span data-stu-id="ae3c0-161">Remove a number exception</span></span>

<span data-ttu-id="ae3c0-162">이 예제에서는 매개 ```-Identity``` 변수가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ae3c0-162">In this example, the ```-Identity``` parameter is required.</span></span> <span data-ttu-id="ae3c0-163">이 cmdlet은 테넌트 목록에서 주어진 숫자 패턴을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="ae3c0-163">This cmdlet will remove the given number pattern from the tenant list.</span></span>  <span data-ttu-id="ae3c0-164">ID를 알 수 없는 경우 cmdlet을 사용하여 먼저 적절한 패턴을 찾고 ```Get-CsInboundBlockedNumberPattern``` ID를 적어 냅니다.</span><span class="sxs-lookup"><span data-stu-id="ae3c0-164">If the identity isn't known, use the ```Get-CsInboundBlockedNumberPattern``` cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="ae3c0-165">그런 다음 ```Remove-CsTenantBlockedNumberExceptionPattern``` cmdlet을 실행하고 적절한 ID 값을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="ae3c0-165">Then, run the ```Remove-CsTenantBlockedNumberExceptionPattern``` cmdlet and pass the appropriate identity value.</span></span><span data-ttu-id="ae3c0-166">테스트하고 유효성을 검사하기 전에 복제 시간을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="ae3c0-166"> Allow time for replication before you test and validate.</span></span>  

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a><span data-ttu-id="ae3c0-167">숫자가 차단된지 여부를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="ae3c0-167">Test whether a number is blocked</span></span>

<span data-ttu-id="ae3c0-168">cmdlet을 사용하여 테넌트에서 숫자가 차단되는지 ```Test-CsInboundBlockedNumberPattern``` 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae3c0-168">Use the ```Test-CsInboundBlockedNumberPattern``` cmdlet to verify whether a number is blocked in the tenant.</span></span>
 
<span data-ttu-id="ae3c0-169">이 예제에서는 ```-Phonenumber``` 및 매개 ```-Tenant``` 변수가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ae3c0-169">In this example, the ```-Phonenumber``` and ```-Tenant``` parameters are required.</span></span> <span data-ttu-id="ae3c0-170">매개 변수는 + 또는 -와 같은 추가 문자가 없는 숫자 ```-PhoneNumber``` 문자열이 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae3c0-170">The ```-PhoneNumber``` parameter should be a numeric string without any additional characters such as + or -.</span></span> <span data-ttu-id="ae3c0-171">TRPS에서 ```-Tenant parameter``` 는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="ae3c0-171">In TRPS, the ```-Tenant parameter``` is optional.</span></span> <span data-ttu-id="ae3c0-172">결과 매개 변수는 테넌트에서 숫자가 차단된 경우 True 값을 반환하고, 차단되지 않은 경우 ```isNumberBlocked``` False를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ae3c0-172">The resulting ```isNumberBlocked``` parameter returns a value of True if the number is blocked in the tenant and False if it's not blocked.</span></span>

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 4255550101
```

|<span data-ttu-id="ae3c0-173">httpResponseCode</span><span class="sxs-lookup"><span data-stu-id="ae3c0-173">httpResponseCode</span></span>  |<span data-ttu-id="ae3c0-174">isNumberBlocked</span><span class="sxs-lookup"><span data-stu-id="ae3c0-174">isNumberBlocked</span></span>   |<span data-ttu-id="ae3c0-175">errorMessage</span><span class="sxs-lookup"><span data-stu-id="ae3c0-175">errorMessage</span></span> |
|---------|---------|---------|
|<span data-ttu-id="ae3c0-176">200</span><span class="sxs-lookup"><span data-stu-id="ae3c0-176">200</span></span>    | <span data-ttu-id="ae3c0-177">True</span><span class="sxs-lookup"><span data-stu-id="ae3c0-177">True</span></span>        |         |

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 6045550188
```

|<span data-ttu-id="ae3c0-178">httpResponseCode</span><span class="sxs-lookup"><span data-stu-id="ae3c0-178">httpResponseCode</span></span>  |<span data-ttu-id="ae3c0-179">isNumberBlocked</span><span class="sxs-lookup"><span data-stu-id="ae3c0-179">isNumberBlocked</span></span>   |<span data-ttu-id="ae3c0-180">errorMessage</span><span class="sxs-lookup"><span data-stu-id="ae3c0-180">errorMessage</span></span> |
|---------|---------|---------|
|<span data-ttu-id="ae3c0-181">200</span><span class="sxs-lookup"><span data-stu-id="ae3c0-181">200</span></span>    | <span data-ttu-id="ae3c0-182">False</span><span class="sxs-lookup"><span data-stu-id="ae3c0-182">False</span></span>        |         |

## <a name="a-note-about-regex"></a><span data-ttu-id="ae3c0-183">Regex에 대한 참고 사항</span><span class="sxs-lookup"><span data-stu-id="ae3c0-183">A note about Regex</span></span>

<span data-ttu-id="ae3c0-184">앞에서 설명한 대로 호출자 차단에 대한 패턴 일치는 Regex를 사용하여 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae3c0-184">As stated earlier, the pattern matching for blocking callers is done by using Regex.</span></span> <span data-ttu-id="ae3c0-185">여러 도구를 온라인으로 사용하여 Regex 패턴 일치의 유효성을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae3c0-185">Multiple tools are available online to help validate a Regex pattern match.</span></span> <span data-ttu-id="ae3c0-186">Regex 패턴에 익숙하지 않은 경우 기본에 익숙해지기 위해 시간이 걸릴 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ae3c0-186">If you aren't familiar with Regex patterns, we recommend that you take some time to familiarize yourself with the basics.</span></span> <span data-ttu-id="ae3c0-187">예상 결과를 얻지 못하게하려면 테넌트에 새 차단된 번호 일치를 추가하기 전에 패턴 일치를 유효성 검사하기 위해 도구를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ae3c0-187">To make sure you get expected results, use a tool for validating pattern matches before you add new blocked number matches to your tenant.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="ae3c0-188">관련 주제</span><span class="sxs-lookup"><span data-stu-id="ae3c0-188">Related topics</span></span>

- [<span data-ttu-id="ae3c0-189">컴퓨터를 설정하여 비즈니스용 Skype 온라인을 관리합니다Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ae3c0-189">Set up your computer to manage Skype for Business Online by using Windows PowerShell</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
