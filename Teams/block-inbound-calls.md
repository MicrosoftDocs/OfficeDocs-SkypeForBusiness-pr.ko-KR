---
title: Microsoft 팀에서 인바운드 전화 차단
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: 3bb1222f0662228e5c0de7b2253cbac162571b1e
ms.sourcegitcommit: a36514c7c8ea47bde4edb09c11ff99061b1f74c0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2020
ms.locfileid: "45094684"
---
# <a name="block-inbound-calls"></a><span data-ttu-id="4ce29-102">들어오는 통화 차단</span><span class="sxs-lookup"><span data-stu-id="4ce29-102">Block inbound calls</span></span>

<span data-ttu-id="4ce29-103">전화 시스템 다이렉트 라우팅 및 통화 계획은 PSTN (공개 전환 전화 네트워크)에서 인바운드 호출을 차단 하는 기능을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ce29-103">Phone System Direct Routing and Calling Plans support blocking inbound calls from the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="4ce29-104">이 기능을 사용 하면 수신 되는 모든 PSTN 호출의 발신자 ID를 해당 목록에 대해 테 넌 트에 대해 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ce29-104">This feature allows a tenant global list of number patterns to be defined so that the caller ID of every incoming PSTN call to the tenant can be checked against the list for a match.</span></span> <span data-ttu-id="4ce29-105">일치 하는 항목이 있으면 수신 통화가 거부 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ce29-105">If a match is made, an incoming call is rejected.</span></span>

<span data-ttu-id="4ce29-106">이 인바운드 통화 차단 기능은 PSTN에서 시작 되는 인바운드 통화에만 작동 하며 테 넌 트 전역 으로만 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ce29-106">This inbound call blocking feature only works on inbound calls that originate from the PSTN and only works on a tenant-global basis.</span></span> <span data-ttu-id="4ce29-107">사용자 기준으로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4ce29-107">It's not available on a per-user basis.</span></span>  

>[!NOTE]
> <span data-ttu-id="4ce29-108">차단 된 호출자는 차단 되 면 약간 다른 동작이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ce29-108">Blocked callers may experience slightly different behaviors when they've been blocked.</span></span> <span data-ttu-id="4ce29-109">동작은 차단 된 호출자의 반송파가 통화가 성공적으로 완료 될 수 없다는 알림을 처리 하는 방법을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ce29-109">The behavior is based on how the blocked caller’s carrier handles the notification that the call isn't allowed to be successfully completed.</span></span> <span data-ttu-id="4ce29-110">예에는 전화를 걸 수 없거나 통화를 삭제 하는 등 통화를 완료할 수 없음을 나타내는 통신 회사 메시지가 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ce29-110">Examples may include a carrier message stating the call can't be completed as dialed, or simply dropping the call.</span></span>

## <a name="call-blocking-admin-controls-and-information"></a><span data-ttu-id="4ce29-111">통화 차단 관리 컨트롤 및 정보</span><span class="sxs-lookup"><span data-stu-id="4ce29-111">Call blocking admin controls and information</span></span>

<span data-ttu-id="4ce29-112">차단 번호에 대 한 관리 컨트롤은 PowerShell을 사용 하는 경우에만 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ce29-112">Admin controls for blocking numbers are provided using PowerShell only.</span></span> <span data-ttu-id="4ce29-113">숫자 블록 패턴은 정규식 패턴으로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ce29-113">Number block patterns are defined as regular expression patterns.</span></span> <span data-ttu-id="4ce29-114">식의 순서는 중요 하지 않으며 목록에서 일치 하는 첫 번째 패턴은 호출이 차단 됨을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ce29-114">The order of the expressions is unimportant – the first pattern matched in the list results in the call being blocked.</span></span> <span data-ttu-id="4ce29-115">차단 된 호출자 목록에서 추가 하거나 제거 하는 새 숫자나 패턴은 패턴이 활성 상태가 되는 데 최대 24 시간까지 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ce29-115">A new number or pattern that's added or removed in the blocked callers list may take up to 24 hours for the pattern to become active.</span></span>

## <a name="call-blocking-powershell-commands"></a><span data-ttu-id="4ce29-116">호출 차단 PowerShell 명령</span><span class="sxs-lookup"><span data-stu-id="4ce29-116">Call blocking PowerShell commands</span></span>

<span data-ttu-id="4ce29-117">**새**, **Get**, **Set**, **Remove**  - **CsInboundBlockedNumberPattern** cmdlet을 사용 하 여 번호 패턴을 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ce29-117">You manage number patterns by using the **New**, **Get**, **Set**, **Remove** -**CsInboundBlockedNumberPattern** cmdlets.</span></span> <span data-ttu-id="4ce29-118">지정 된 패턴의 활성화를 전환 하는 기능을 포함 하 여 지정 된 패턴을 이러한 cmdlet을 사용 하 여 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ce29-118">You can manage a given pattern by using these cmdlets, including the ability to toggle the activation of a given pattern.</span></span>

- <span data-ttu-id="4ce29-119">[CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/get-csinboundblockednumberpattern) 는 이름, 설명, Enabled (True/False), 각각의 패턴을 비롯 하 여 테 넌 트 목록에 추가 된 모든 차단 된 번호 패턴의 목록을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ce29-119">[Get-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/get-csinboundblockednumberpattern) returns a list of all blocked number patterns added to the tenant list including Name, Description, Enabled (True/False), and Pattern for each.</span></span>
- <span data-ttu-id="4ce29-120">[New-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/new-csinboundblockednumberpattern) 차단 된 번호 패턴을 테 넌 트 목록에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ce29-120">[New-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/new-csinboundblockednumberpattern) adds a blocked number pattern to the tenant list.</span></span>
- <span data-ttu-id="4ce29-121">[CsInboundBlockedNumberPattern 제거-](https://docs.microsoft.com/powershell/module/skype/remove-csinboundblockednumberpattern) 테 넌 트 목록에서 차단 된 번호 패턴을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ce29-121">[Remove-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/remove-csinboundblockednumberpattern) removes a blocked number pattern from the tenant list.</span></span>
- <span data-ttu-id="4ce29-122">[Set-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/set-csinboundblockednumberpattern) 는 테 넌 트 목록에서 차단 된 번호 패턴의 매개 변수를 하나 이상 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ce29-122">[Set-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/set-csinboundblockednumberpattern) modifies one or more parameters of a blocked number pattern in the tenant list.</span></span>

<span data-ttu-id="4ce29-123">전체 통화 차단 기능 보기 및 활성화는 **Get**, **Set**  - **CsTenantBlockingCallingNumbers** cmdlet을 통해 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ce29-123">Viewing and activating the entire call blocking feature is managed through the **Get**, **Set** -**CsTenantBlockingCallingNumbers** cmdlets.</span></span>

- <span data-ttu-id="4ce29-124">[CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockedcallingnumbers) 는 허용 (True/False)을 포함 하 여 전체 차단 된 번호 목록의 매개 변수를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ce29-124">[Get-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockedcallingnumbers) returns the parameters for the global blocked number list including Enabled (True/False).</span></span> <span data-ttu-id="4ce29-125">기능을 설정 하거나 해제 하는 것 외에는 수동으로 수정할 수 없는 단일 전역 테 넌 트 정책이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ce29-125">There's a single global tenant policy that can't be modified manually other than to turn the feature on or off.</span></span>
- <span data-ttu-id="4ce29-126">[Set-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockedcallingnumbers) 를 사용 하면 테 넌 트 차단 된 통화를 수신 대기 수준에서 켜거나 끄도록 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ce29-126">[Set-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockedcallingnumbers) allows modifying the global tenant blocked calls to be turned on and off at the tenant level.</span></span>

### <a name="examples"></a><span data-ttu-id="4ce29-127">예제</span><span class="sxs-lookup"><span data-stu-id="4ce29-127">Examples</span></span>

#### <a name="block-a-number"></a><span data-ttu-id="4ce29-128">숫자 차단</span><span class="sxs-lookup"><span data-stu-id="4ce29-128">Block a number</span></span>

<span data-ttu-id="4ce29-129">이 예제에서 **Enabled** 및 **Description** 매개 변수는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="4ce29-129">In this example, the **Enabled** and **Description** parameters are optional.</span></span>

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

<span data-ttu-id="4ce29-130">새 패턴을 만들면 기본적으로 사용 하도록 설정 된 패턴이 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ce29-130">Creating a new pattern adds the pattern as enabled by default.</span></span> <span data-ttu-id="4ce29-131">설명은 추가 정보를 제공 하는 선택적 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="4ce29-131">The description is an optional field to provide more information.</span></span>

<span data-ttu-id="4ce29-132">패턴이 추가 된 이유를 쉽게 이해할 수 있도록 의미 있는 이름을 제공 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4ce29-132">We recommend that you provide a meaningful name to easily understand why the pattern was added.</span></span> <span data-ttu-id="4ce29-133">단순히 스팸 번호를 차단 하는 경우, 일치 하는 번호 패턴과 같은 규칙 이름을 지정 하 고 필요에 따라 설명에 추가 정보를 추가 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4ce29-133">In the case of simply blocking spam numbers, consider naming the rule the same as the number pattern that's being matched and add additional information in the description as required.</span></span>

<span data-ttu-id="4ce29-134">패턴은 정규식 (Regex)을 사용 하 여 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ce29-134">Patterns are matched using Regular Expressions (Regex).</span></span> <span data-ttu-id="4ce29-135">테스트 하 고 유효성을 검사 하기 전에 복제 시간을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ce29-135">Allow time for replication before you test and validate.</span></span>

#### <a name="allow-a-number"></a><span data-ttu-id="4ce29-136">숫자 허용</span><span class="sxs-lookup"><span data-stu-id="4ce29-136">Allow a number</span></span>

<span data-ttu-id="4ce29-137">이 예제에서는 **id** 매개 변수가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ce29-137">In this example, the **Identity** parameter is required.</span></span>

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```
 
<span data-ttu-id="4ce29-138">Id가 알려지지 않은 경우 **CsInboundBlockedNumberPattern** cmdlet을 사용 하 여 먼저 올바른 패턴을 찾고 id를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ce29-138">If the identity isn't known, use the **Get-CsInboundBlockedNumberPattern** cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="4ce29-139">그런 다음 **Remove-CsTenantBlockedNumberPattern** cmdlet을 실행 하 고 적절 한 id 값을 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ce29-139">Then, run the **Remove-CsTenantBlockedNumberPattern** cmdlet and pass the appropriate identity value.</span></span>

<span data-ttu-id="4ce29-140">테스트 하 고 유효성을 검사 하기 전에 복제 시간을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ce29-140">Allow time for replication before you test and validate.</span></span>

#### <a name="view-all-number-patterns"></a><span data-ttu-id="4ce29-141">모든 숫자 패턴 보기</span><span class="sxs-lookup"><span data-stu-id="4ce29-141">View all number patterns</span></span>

<span data-ttu-id="4ce29-142">이 cmdlet을 실행 하면 테 넌 트에 대해 입력 한 모든 차단 된 번호 목록이 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ce29-142">Running this cmdlet returns a list of all blocked numbers that are entered for a tenant:</span></span>

```powershell
Get-CsInboundBlockedNumberPattern
```

<span data-ttu-id="4ce29-143">기본 제공 PowerShell 필터링 기능을 사용 하 여 반환 된 값을 필요에 따라 구문 분석 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ce29-143">Use built-in PowerShell filtering abilities to parse the returned values as required.</span></span>

## <a name="add-number-exceptions"></a><span data-ttu-id="4ce29-144">숫자 예외 추가</span><span class="sxs-lookup"><span data-stu-id="4ce29-144">Add number exceptions</span></span>

<span data-ttu-id="4ce29-145">**New**, **Get**, **Set** **,**  - **csten앤틸리스 블록 번호 exceptionpattern** cmdlet을 사용 하 여 차단 된 번호 패턴에 예외를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ce29-145">You can add exceptions to blocked number patterns by using the **New**, **Get**, **Set**, **Remove** -**CsTenantBlockNumberExceptionPattern** cmdlets.</span></span>

- <span data-ttu-id="4ce29-146">[CsTenantBlockedNumberExceptionPattern 새](https://docs.microsoft.com/powershell/module/skype/new-cstenantblockednumberexceptionpattern) 테 넌 트 목록에 숫자 예외 패턴을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ce29-146">[New-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/new-cstenantblockednumberexceptionpattern) adds a number exception pattern to the tenant list.</span></span> 
- <span data-ttu-id="4ce29-147">[Get-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockednumberexceptionpattern) 는 테 넌 트 목록에 추가 된 모든 숫자 예외 패턴의 목록을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ce29-147">[Get-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockednumberexceptionpattern) returns a list of all number exception patterns added to the tenant list.</span></span>
- <span data-ttu-id="4ce29-148">[Set-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockednumberexceptionpattern) 는 하나 이상의 매개 변수를 테 넌 트 목록의 숫자 예외 패턴으로 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ce29-148">[Set-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockednumberexceptionpattern) modifies one or more parameters to a number exception pattern in the tenant list.</span></span>
- <span data-ttu-id="4ce29-149">[CsTenantBlockedNumberExceptionPattern 제거-](https://docs.microsoft.com/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) 테 넌 트 목록에서 번호 예외 패턴을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ce29-149">[Remove-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) removes a number exception pattern from the tenant list.</span></span>

### <a name="examples"></a><span data-ttu-id="4ce29-150">예제</span><span class="sxs-lookup"><span data-stu-id="4ce29-150">Examples</span></span>

#### <a name="add-a-number-exception"></a><span data-ttu-id="4ce29-151">숫자 예외 추가</span><span class="sxs-lookup"><span data-stu-id="4ce29-151">Add a number exception</span></span>

<span data-ttu-id="4ce29-152">이 예제에서는 새 숫자 예외 패턴이 만들어지고 기본적으로 패턴을 enabled로 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ce29-152">In this example, a new number exception pattern is created and will by default add the pattern as enabled.</span></span> <span data-ttu-id="4ce29-153">**Enabled** 및 **Description** 매개 변수는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="4ce29-153">The **Enabled** and **Description** parameters are optional.</span></span>

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"  
```

#### <a name="view-all-number-exceptions"></a><span data-ttu-id="4ce29-154">모든 숫자 예외 보기</span><span class="sxs-lookup"><span data-stu-id="4ce29-154">View all number exceptions</span></span>

<span data-ttu-id="4ce29-155">이 예제에서 **Identity** 매개 변수는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="4ce29-155">In this example, the **Identity** parameter is optional.</span></span> <span data-ttu-id="4ce29-156">**Id** 매개 변수를 지정 하지 않으면이 cmdlet은 테 넌 트에 대해 입력 된 모든 숫자 예외 패턴 목록을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ce29-156">If the **Identity** parameter isn't specified, this cmdlet returns a list of all number exception patterns entered for a tenant.</span></span>
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a><span data-ttu-id="4ce29-157">숫자 예외 수정</span><span class="sxs-lookup"><span data-stu-id="4ce29-157">Modify a number exception</span></span>

<span data-ttu-id="4ce29-158">이 예제에서 **Identity** 매개 변수는 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="4ce29-158">In this example, the **Identity** parameter is mandatory.</span></span> <span data-ttu-id="4ce29-159">**CsTenantBlockedNumberExceptionPattern** cmdlet을 사용 하면 지정 된 번호 패턴 id에 대 한 하나 이상의 매개 변수를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ce29-159">The **Set-CsTenantBlockedNumberExceptionPattern** cmdlet lets you modify one or more parameters for a given number pattern identity.</span></span>
 
```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$" 
```

#### <a name="remove-a-number-exception"></a><span data-ttu-id="4ce29-160">숫자 예외 제거</span><span class="sxs-lookup"><span data-stu-id="4ce29-160">Remove a number exception</span></span>

<span data-ttu-id="4ce29-161">이 예제에서는 **id** 매개 변수가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ce29-161">In this example, the **Identity** parameter is required.</span></span> <span data-ttu-id="4ce29-162">이 cmdlet은 테 넌 트 목록에서 지정 된 번호 패턴을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ce29-162">This cmdlet will remove the given number pattern from the tenant list.</span></span>  <span data-ttu-id="4ce29-163">Id가 알려지지 않은 경우 **CsInboundBlockedNumberPattern** cmdlet을 사용 하 여 먼저 올바른 패턴을 찾고 id를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ce29-163">If the identity isn't known, use the **Get-CsInboundBlockedNumberPattern** cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="4ce29-164">그런 다음 **Remove-CsTenantBlockedNumberExceptionPattern** cmdlet을 실행 하 고 적절 한 id 값을 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ce29-164">Then, run the **Remove-CsTenantBlockedNumberExceptionPattern** cmdlet and pass the appropriate identity value.</span></span><span data-ttu-id="4ce29-165">테스트 하 고 유효성을 검사 하기 전에 복제 시간을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ce29-165"> Allow time for replication before you test and validate.</span></span>  

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a><span data-ttu-id="4ce29-166">숫자가 차단 되었는지 테스트</span><span class="sxs-lookup"><span data-stu-id="4ce29-166">Test whether a number is blocked</span></span>

<span data-ttu-id="4ce29-167">**CsInboundBlockedNumberPattern** cmdlet을 사용 하 여 해당 숫자가 테 넌 트에서 차단 되었는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ce29-167">Use the **Test-CsInboundBlockedNumberPattern** cmdlet to verify whether a number is blocked in the tenant.</span></span>
 
<span data-ttu-id="4ce29-168">이 예제에서는 **PhoneNumber** 및 **테 넌 트** 매개 변수가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ce29-168">In this example, the **PhoneNumber** and **Tenant** parameters are required.</span></span> <span data-ttu-id="4ce29-169">**PhoneNumber** 매개 변수는 + 또는-등의 추가 문자 없이 숫자 문자열 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ce29-169">The **PhoneNumber** parameter should be a numeric string without any additional characters such as + or -.</span></span> <span data-ttu-id="4ce29-170">TRPS에서 **테 넌 트 매개 변수** 는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="4ce29-170">In TRPS, the **Tenant parameter** is optional.</span></span> <span data-ttu-id="4ce29-171">결과 **Is번호 차단** 된 매개 변수는 해당 숫자가 테 넌 트에서 차단 되는 경우 True 값을 반환 하 고, 차단 되지 않으면 False입니다.</span><span class="sxs-lookup"><span data-stu-id="4ce29-171">The resulting **isNumberBlocked** parameter returns a value of True if the number is blocked in the tenant and False if it's not blocked.</span></span>

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 4255550101
```

|<span data-ttu-id="4ce29-172">httpResponseCode</span><span class="sxs-lookup"><span data-stu-id="4ce29-172">httpResponseCode</span></span>  |<span data-ttu-id="4ce29-173">Is번호 차단 됨</span><span class="sxs-lookup"><span data-stu-id="4ce29-173">isNumberBlocked</span></span>   |<span data-ttu-id="4ce29-174">errorMessage</span><span class="sxs-lookup"><span data-stu-id="4ce29-174">errorMessage</span></span> |
|---------|---------|---------|
|<span data-ttu-id="4ce29-175">200</span><span class="sxs-lookup"><span data-stu-id="4ce29-175">200</span></span>    | <span data-ttu-id="4ce29-176">False</span><span class="sxs-lookup"><span data-stu-id="4ce29-176">True</span></span>        |         |

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 6045550188
```

|<span data-ttu-id="4ce29-177">httpResponseCode</span><span class="sxs-lookup"><span data-stu-id="4ce29-177">httpResponseCode</span></span>  |<span data-ttu-id="4ce29-178">Is번호 차단 됨</span><span class="sxs-lookup"><span data-stu-id="4ce29-178">isNumberBlocked</span></span>   |<span data-ttu-id="4ce29-179">errorMessage</span><span class="sxs-lookup"><span data-stu-id="4ce29-179">errorMessage</span></span> |
|---------|---------|---------|
|<span data-ttu-id="4ce29-180">200</span><span class="sxs-lookup"><span data-stu-id="4ce29-180">200</span></span>    | <span data-ttu-id="4ce29-181">해제</span><span class="sxs-lookup"><span data-stu-id="4ce29-181">False</span></span>        |         |

## <a name="a-note-about-regex"></a><span data-ttu-id="4ce29-182">Regex에 대 한 참고 사항</span><span class="sxs-lookup"><span data-stu-id="4ce29-182">A note about Regex</span></span>

<span data-ttu-id="4ce29-183">앞에서 설명한 대로 호출자 차단에 대 한 패턴 일치는 Regex를 사용 하 여 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ce29-183">As stated earlier, the pattern matching for blocking callers is done by using Regex.</span></span> <span data-ttu-id="4ce29-184">Regex 패턴 일치의 유효성을 검사 하는 데 도움이 되는 여러 도구를 온라인에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ce29-184">Multiple tools are available online to help validate a Regex pattern match.</span></span> <span data-ttu-id="4ce29-185">Regex 패턴에 익숙하지 않은 경우 기본 사항에 익숙해지는 데 약간의 시간이 소요 되는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4ce29-185">If you aren't familiar with Regex patterns, we recommend that you take some time to familiarize yourself with the basics.</span></span> <span data-ttu-id="4ce29-186">예상 되는 결과를 얻으려면 새 차단 된 번호 일치 항목을 테 넌 트에 추가 하기 전에 패턴 일치의 유효성을 검사 하기 위한 도구를 사용 하세요.</span><span class="sxs-lookup"><span data-stu-id="4ce29-186">To make sure you get expected results, use a tool for validating pattern matches before you add new blocked number matches to your tenant.</span></span>
