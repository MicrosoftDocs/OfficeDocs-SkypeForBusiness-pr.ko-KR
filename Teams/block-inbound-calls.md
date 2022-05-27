---
title: Microsoft Teams 인바운드 호출 차단
ms.author: serdars
author: SerdarSoysal
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
ms.localizationpriority: medium
ms.custom: ''
description: PowerShell을 사용하여 인바운드 호출 차단을 관리하는 방법을 알아봅니다.
ms.openlocfilehash: 25b271cbcf62acd732463e9dd34d4189479d2417
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674390"
---
# <a name="block-inbound-calls"></a>인바운드 호출 차단

Microsoft 통화 플랜, 직접 라우팅 및 운영자 연결 모든 지원은 PSTN(공중 전화망)에서 인바운드 통화를 차단합니다. 이 기능을 사용하면 관리자가 테넌트에 들어오는 모든 PSTN 호출의 호출자 ID를 일치 목록에 대해 확인할 수 있도록 테넌트 전역 수준에서 숫자 패턴 목록을 정의할 수 있습니다. 일치하는 항목이 있으면 들어오는 호출이 거부됩니다.

이 인바운드 호출 차단 기능은 PSTN에서 시작된 인바운드 호출에서만 작동하며 테넌트 전역 수준에서만 작동합니다. 개별 Teams 사용자는 이 목록을 조작할 수 없습니다. Teams 클라이언트는 개별 사용자가 PSTN 호출을 차단할 수 있도록 허용합니다. 최종 사용자가 통화 차단을 구현하는 방법에 대한 자세한 내용은 [Teams 통화 설정 관리를](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f) 참조하세요.

> [!NOTE]
> 차단된 호출자는 차단되었을 때 약간 다른 동작이 발생할 수 있습니다. 이 동작은 차단된 호출자의 통신 사업자가 호출을 성공적으로 완료할 수 없다는 알림을 처리하는 방법을 기반으로 합니다. 전화 걸기로 통화를 완료할 수 없거나 단순히 전화를 끊을 수 없다는 통신 사업자 메시지가 예로 포함될 수 있습니다.

## <a name="call-blocking-admin-controls-and-information"></a>호출 차단 관리자 컨트롤 및 정보

차단 번호에 대한 관리 컨트롤은 PowerShell만 사용하여 제공됩니다. 숫자 블록 패턴은 정규식 패턴으로 정의됩니다. 식의 순서는 중요하지 않습니다. 목록에서 일치하는 첫 번째 패턴은 호출이 차단됩니다. 차단된 호출자 목록에서 추가되거나 제거된 새 번호 또는 패턴은 패턴이 활성화되는 데 최대 24시간이 걸릴 수 있습니다.

## <a name="call-blocking-powershell-commands"></a>통화 차단 PowerShell 명령

New-, **Get-**, **Set**-및 **Remove-CsInboundBlockedNumberPattern** cmdlet을 사용하여 숫자 패턴을 관리합니다. 지정된 패턴의 활성화를 토글하는 기능을 포함하여 이러한 cmdlet을 사용하여 지정된 패턴을 관리할 수 있습니다.

- [Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) 은 이름, 설명, 사용(True/False) 및 각각에 대한 패턴을 포함하여 테넌트 목록에 추가된 모든 차단된 숫자 패턴 목록을 반환합니다.
- [New-CsInboundBlockedNumberPattern](/powershell/module/skype/new-csinboundblockednumberpattern) 은 차단된 숫자 패턴을 테넌트 목록에 추가합니다.
- [Remove-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) 은 테넌트 목록에서 차단된 숫자 패턴을 제거합니다.
- [Set-CsInboundBlockedNumberPattern은](/powershell/module/skype/set-csinboundblockednumberpattern) 테넌트 목록에서 차단된 숫자 패턴의 매개 변수를 하나 이상 수정합니다.

전체 통화 차단 기능 보기 및 활성화는 **Get-** 및 **Set-CsTenantBlockingCallingNumbers** cmdlet을 통해 관리됩니다.

- [Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) 는 전역 차단된 숫자 목록에 대한 인바운드 블록 번호 패턴 및 인바운드 제외 번호 패턴 매개 변수를 반환합니다. 이 cmdlet은 차단이 사용(True 또는 False)인지 여부도 반환합니다. 기능을 켜거나 끄는 것 외에는 수동으로 수정할 수 없는 단일 전역 테넌트 정책이 있습니다.
- [Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) 를 사용하면 테넌트 수준에서 전역 테넌트 차단 호출을 켜고 끌 수 있습니다.

### <a name="examples"></a>예제

#### <a name="block-a-number"></a>숫자 차단

다음 예제에서 테넌트 관리자 숫자 범위 1(312) 555-0000에서 1(312) 555-9999로 오는 모든 호출을 차단하려고 합니다. 숫자 패턴은 + 접두사 + 접두사가 있는 범위의 숫자와 + 접두사 없는 범위의 숫자가 모두 일치되도록 만들어집니다. 시스템이 일치하기 전에 이러한 기호를 제거하기 때문에 전화 번호에 기호 및 ()를 포함할 필요가 없습니다.  숫자 패턴을 켜려면 **Enabled** 매개 변수가 True로 설정됩니다. 이 특정 숫자 패턴을 사용하지 않도록 설정하려면 매개 변수를 False로 설정합니다.

```PowerShell
New-CsInboundBlockedNumberPattern -Name "BlockRange1" -Enabled $True -Description "Block Contoso" -Pattern "^\+?1312555\d{4}$"
```

다음 예제에서 테넌트 관리자 번호 1(412) 555-1234에서 오는 모든 호출을 차단하려고 합니다. 숫자 패턴을 켜려면 **Enabled** 매개 변수가 True로 설정됩니다.

```PowerShell
New-CsInboundBlockedNumberPattern -Name "BlockNumber1" -Enabled $True -Description "Block Fabrikam" -Pattern "^\+?14125551234$"
```

새 패턴을 만들면 기본적으로 사용하도록 설정된 패턴이 추가됩니다. 설명은 추가 정보를 제공하는 선택적 필드입니다.

패턴이 추가된 이유를 쉽게 이해할 수 있도록 의미 있는 이름을 제공하는 것이 좋습니다. 단순히 스팸 번호를 차단하는 경우 일치하는 숫자 패턴과 동일한 규칙 이름을 지정하고 필요에 따라 설명에 추가 정보를 추가하는 것이 좋습니다.

패턴은 정규식(Regex)을 사용하여 일치합니다. 자세한 내용은 [Regex 사용을](#using-regex) 참조하세요.

테스트하고 유효성을 검사하기 전에 복제 시간을 허용합니다.

#### <a name="allow-a-number"></a>숫자 허용

차단된 숫자 패턴을 제거하여 번호를 호출하도록 허용할 수 있습니다. 다음 예제에서 테넌트 관리자 1(412) 555-1234가 다시 호출되도록 허용하려고 합니다.

```PowerShell
Remove-CsInboundBlockedNumberPattern -Identity "BlockNumber1"
```

ID를 알 수 없는 경우 **Get-CsInboundBlockedNumberPattern** cmdlet을 사용하여 먼저 적절한 패턴을 찾고 ID를 기록해 둡니다. 그런 다음 **Remove-CsInboundBlockedNumberPattern** cmdlet을 실행하고 적절한 ID 값을 전달합니다.

테스트하고 유효성을 검사하기 전에 복제 시간을 허용합니다.

#### <a name="view-all-number-patterns"></a>모든 숫자 패턴 보기

이 cmdlet을 실행하면 테넌트에 대해 입력된 모든 차단된 숫자 목록이 반환됩니다.

```powershell
Get-CsInboundBlockedNumberPattern
```

기본 제공 PowerShell 필터링 기능을 사용하여 필요에 따라 반환된 값을 구문 분석합니다.

## <a name="add-number-exceptions"></a>숫자 예외 추가

New-, **Get**-, **Set**-및 **Remove-CsInboundExemptNumberPattern** cmdlet을 사용하여 차단된 숫자 패턴에 예외를 추가할 수 있습니다.

- [New-CsInboundExemptNumberPattern](/powershell/module/skype/New-CsInboundExemptNumberPattern) 은 테넌트 목록에 숫자 예외 패턴을 추가합니다.
- [Get-CsInboundExemptNumberPattern](/powershell/module/skype/Get-CsInboundExemptNumberPattern) 은 테넌트 목록에 추가된 모든 숫자 예외 패턴의 목록을 반환합니다.
- [Set-CsInboundExemptNumberPattern은](/powershell/module/skype/Set-CsInboundExemptNumberPattern) 하나 이상의 매개 변수를 테넌트 목록의 숫자 예외 패턴으로 수정합니다.
- [Remove-CsInboundExemptNumberPattern](/powershell/module/skype/Remove-CsInboundExemptNumberPattern) 은 테넌트 목록에서 숫자 예외 패턴을 제거합니다.

### <a name="examples"></a>예제

#### <a name="add-a-number-exception"></a>숫자 예외 추가

다음 예제에서 테넌트 관리자 위의 예제에서 차단된 범위에 두 전화 번호가 있더라도 전화 번호 1(312) 555-8882 및 1(312) 555-8883으로 테넌트에 전화를 걸 수 있도록 허용하려고 합니다. 이를 사용하도록 설정하려면 다음과 같이 새 숫자 예외 패턴이 만들어집니다.

```PowerShell
New-CsInboundExemptNumberPattern  -Identity "AllowContoso1" -Pattern "^\+?1312555888[2|3]$" -Description "Allow Contoso helpdesk" -Enabled $True
```

숫자 패턴을 켜려면 **Enabled** 매개 변수가 True로 설정됩니다. 이 특정 숫자 패턴을 사용하지 않도록 설정하려면 매개 변수를 False로 설정합니다.

#### <a name="view-all-number-exceptions"></a>모든 숫자 예외 보기

이 예제에서 **Identity** 매개 변수는 선택 사항입니다. **Identity** 매개 변수를 지정하지 않으면 이 cmdlet은 테넌트에 대해 입력된 모든 숫자 예외 패턴의 목록을 반환합니다.

```powershell
Get-CsInboundExemptNumberPattern -Identity <String>
```

```powershell
Get-CsInboundExemptNumberPattern
```

#### <a name="modify-a-number-exception"></a>숫자 예외 수정

**Set-CsInboundExemptNumberPattern** cmdlet을 사용하면 지정된 숫자 패턴 ID에 대해 하나 이상의 매개 변수를 수정할 수 있습니다. 이 예제에서는 **Identity** 매개 변수가 필요합니다.

```powershell
Set-CsInboundExemptNumberPattern -Identity <String> -Enabled <bool> -Description <string> -Pattern <string>
```

```powershell
Set-CsInboundExemptNumberPattern -Identity "AllowContoso1" -Enabled $False
```

#### <a name="remove-a-number-exception"></a>숫자 예외 제거

**Remove-CsInboundExemptNumberPattern** cmdlet은 테넌트 목록에서 지정된 숫자 패턴을 제거합니다. 이 예제에서는 **Identity** 매개 변수가 필요합니다.

ID를 알 수 없는 경우 **Get-CsInboundExemptNumberPattern** cmdlet을 사용하여 먼저 적절한 패턴을 찾고 ID를 기록해 둡니다. 그런 다음 **Remove-CsInboundExemptNumberPattern** cmdlet을 실행하고 적절한 ID 값을 전달합니다. 테스트하고 유효성을 검사하기 전에 복제 시간을 허용합니다.

```powershell
Remove-CsInboundExemptNumberPattern -Identity <String>
```

```powershell
Remove-CsInboundExemptNumberPattern -Identity "AllowContoso1"
```

## <a name="test-whether-a-number-is-blocked"></a>숫자가 차단되었는지 테스트

**Test-CsInboundBlockedNumberPattern** cmdlet을 사용하여 테넌트에서 숫자가 차단되었는지 여부를 확인합니다.

**PhoneNumber** 매개 변수는 필수이며 +, 또는 ()와 같은 추가 문자가 없는 숫자 문자열이어야 합니다. 결과 **IsNumberBlocked** 매개 변수는 숫자가 테넌트에서 차단된 경우 True 값을 반환합니다. 매개 변수가 차단되지 않은 경우 False를 반환합니다.

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

### <a name="examples"></a>예제

이 예제에서는 전화 번호 1(312) 555-8884가 위의 차단된 범위에 있기 때문에 차단된 반면, 전화 번호 1(312) 555-8883은 위에서 만든 예외에 따라 호출할 수 있습니다.

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

## <a name="using-regex"></a>Regex 사용

차단 호출자에 대한 패턴 일치는 Regex를 사용하여 수행됩니다. Regex 패턴 일치의 유효성을 검사하는 데 도움이 되는 여러 도구를 온라인으로 사용할 수 있습니다. Regex 패턴에 익숙하지 않은 경우 잠시 시간을 내어 기본 사항을 숙지하는 것이 좋습니다. 예상된 결과를 얻으려면 테넌트에 차단된 숫자 일치를 새로 추가하기 전에 패턴 일치의 유효성을 검사하는 도구를 사용합니다.
