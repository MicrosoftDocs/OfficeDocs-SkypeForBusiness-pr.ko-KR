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
ms.localizationpriority: medium
ms.custom: Learn how to use PowerShell to manage inbound call blocking.
ms.openlocfilehash: 6388c65e5f2c8600c263153b1a943bf485670fe4
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58631432"
---
# <a name="block-inbound-calls"></a>인바운드 호출 차단

Microsoft 통화 계획, 직접 라우팅 및 운영자는 PSTN(공용 커넥트 전화 네트워크)에서 인바운드 호출을 차단하는 모든 지원을 제공합니다. 이 기능을 사용하면 관리자가 테넌트 전역 수준에서 번호 패턴 목록을 정의하여 테넌트에 들어오는 모든 PSTN 호출의 호출자 ID를 매치 목록에 대해 확인할 수 있습니다. 일치하는 경우 들어오는 호출이 거부됩니다.

이 인바운드 호출 차단 기능은 PSTN에서 시작된 인바운드 호출에만 작동하며 테넌트 전역 수준에서만 작동합니다. 개별 Teams 사용자가 이 목록을 조작할 수 없습니다. Teams 클라이언트는 개별 사용자가 PSTN 호출을 차단할 수 있도록 허용합니다. 최종 사용자가 통화 차단을 구현하는 방법에 대한 자세한 내용은 에서 호출 [설정 관리를 Teams.](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)

>[!NOTE]
> 차단된 호출자는 차단된 경우 약간 다른 동작을 경험할 수 있습니다. 동작은 차단된 발신자 통신사가 호출을 성공적으로 완료할 수 없습니다는 알림을 처리하는 방법을 기반으로 합니다. 예를 들어 전화를 걸 때 통화를 완료할 수 없다거나 단순히 전화를 떨어뜨렸다는 통신사 메시지가 있을 수 있습니다.

## <a name="call-blocking-admin-controls-and-information"></a>관리자 제어 및 정보 차단 호출

차단 번호에 대한 관리자 컨트롤은 PowerShell을 사용하여만 제공됩니다. 숫자 블록 패턴은 정규식 패턴으로 정의됩니다. 식의 순서는 무의미합니다. 목록에서 일치하는 첫 번째 패턴은 호출이 차단됩니다. 차단된 호출자 목록에 추가되거나 제거된 새 번호 또는 패턴은 패턴이 활성화되는 데 최대 24시간이 걸릴 수 있습니다.

## <a name="call-blocking-powershell-commands"></a>PowerShell 명령 차단 호출

**New-**, **Get-**, **Set-** 및 **Remove-CsInboundBlockedNumberPattern** cmdlet을 사용하여 숫자 패턴을 관리합니다. 특정 패턴의 활성화를 전환하는 기능을 포함하여 이러한 cmdlet을 사용하여 주어진 패턴을 관리할 수 있습니다.

- [Get-CsInboundBlockedNumberPattern은](/powershell/module/skype/get-csinboundblockednumberpattern) 각각에 대한 이름, 설명, 사용 가능(True/False) 및 패턴을 포함하여 테넌트 목록에 추가된 모든 차단된 숫자 패턴의 목록을 반환합니다.
- [New-CsInboundBlockedNumberPattern은](/powershell/module/skype/new-csinboundblockednumberpattern) 테넌트 목록에 차단된 숫자 패턴을 추가합니다.
- [Remove-CsInboundBlockedNumberPattern은](/powershell/module/skype/remove-csinboundblockednumberpattern) 테넌트 목록에서 차단된 숫자 패턴을 제거합니다.
- [Set-CsInboundBlockedNumberPattern은](/powershell/module/skype/set-csinboundblockednumberpattern) 테넌트 목록에서 차단된 숫자 패턴의 하나 이상의 매개 변수를 수정합니다.

전체 호출 차단 기능을 보고 활성화하는 것은 **Get-and** **Set-CsTenantBlockingCallingNumbers** cmdlet을 통해 관리됩니다.

- [Get-CsTenantBlockedCallingNumbers는](/powershell/module/skype/get-cstenantblockedcallingnumbers) 전역 차단 번호 목록에 대한 인바운드 블록 번호 패턴 및 인바운드 면제 번호 패턴 매개 변수를 반환합니다. 이 cmdlet은 차단이 활성화되어 있는지(True 또는 False)를 반환합니다. 기능을 켜거나 끄는 것 이외에 수동으로 수정할 수 없는 단일 전역 테넌트 정책이 있습니다.
- [Set-CsTenantBlockedCallingNumbers를](/powershell/module/skype/set-cstenantblockedcallingnumbers) 사용하면 테넌트 수준에서 전역 테넌트 차단된 호출을 설정 및 해제하도록 수정할 수 있습니다.

### <a name="examples"></a>예제

#### <a name="block-a-number"></a>숫자 차단

다음 예제에서 테넌트 관리자는 숫자 범위 1(312) 555-0000에서 1(312) 555-9999까지 오는 모든 호출을 차단하려는 경우 숫자 패턴은 +가 있는 범위의 숫자와 + 도두사 없는 범위의 숫자가 모두 일치하게 만들어 졌습니다. 시스템이 일치하기 전에 이러한 기호를 스트립하기 때문에 전화 번호에 기호 및 ()를 포함할 필요가 없습니다.  숫자 패턴을 켜기 위해 **사용** 가능 매개 변수가 True로 설정됩니다. 이 특정 숫자 패턴을 사용하지 않도록 설정하기 위해 매개 변수를 False로 설정합니다.

```PowerShell
New-CsInboundBlockedNumberPattern -Name "BlockRange1" -Enabled $True -Description "Block Contoso" -Pattern "^\+?1312555\d{4}$"
```

다음 예제에서 테넌트 관리자는 숫자 1(412) 555-1234에서 오는 모든 호출을 차단합니다. 숫자 패턴을 켜기 위해 **사용** 가능 매개 변수가 True로 설정됩니다.

```PowerShell
New-CsInboundBlockedNumberPattern -Name "BlockNumber1" -Enabled $True -Description "Block Fabrikam" -Pattern "^\+?14125551234$"
```

새 패턴을 만들면 기본적으로 사용하도록 설정된 패턴을 추가합니다. 설명은 자세한 정보를 제공하는 선택적 필드입니다.

패턴을 추가한 이유를 쉽게 이해할 수 있도록 의미 있는 이름을 제공하는 것이 좋습니다. 스팸 번호를 차단하는 경우 규칙의 이름을 일치되는 숫자 패턴과 동일하게 이름을 매기고 필요한 경우 설명에 추가 정보를 추가하는 것이 고려됩니다.

패턴은 정규식(Regex)을 사용하여 일치합니다. 자세한 내용은 Regex 사용을 [참조하세요.](#using-regex)

테스트하고 유효성을 검사하기 전에 복제 시간을 허용합니다. 

#### <a name="allow-a-number"></a>숫자 허용

차단된 번호 패턴을 제거하여 번호를 호출하도록 허용할 수 있습니다. 다음 예제에서 테넌트 관리자는 1(412) 555-1234에서 다시 전화를 걸 수 있도록 허용합니다.

```PowerShell
Remove-CsInboundBlockedNumberPattern -Identity "BlockNumber1"
```
 
ID를 알 수 없는 경우 **Get-CsInboundBlockedNumberPattern** cmdlet을 사용하여 먼저 적절한 패턴을 찾고 ID를 기록합니다. 그런 다음 **Remove-CsInboundBlockedNumberPattern** cmdlet을 실행하고 적절한 ID 값을 전달합니다.

테스트하고 유효성을 검사하기 전에 복제 시간을 허용합니다.

#### <a name="view-all-number-patterns"></a>모든 숫자 패턴 보기

이 cmdlet을 실행하여 테넌트에 입력된 모든 차단된 숫자 목록을 반환합니다.

```powershell
Get-CsInboundBlockedNumberPattern
```

기본 제공 PowerShell 필터링 기능을 사용하여 반환된 값을 필요한 경우 구문 분석합니다.

## <a name="add-number-exceptions"></a>숫자 예외 추가

**New-**, **Get-**, **Set-** 및 **Remove-CsInboundExemptNumberPattern** cmdlet을 사용하여 차단된 숫자 패턴에 예외를 추가할 수 있습니다.

- [New-CsInboundExemptNumberPattern은](/powershell/module/skype/New-CsInboundExemptNumberPattern) 테넌트 목록에 숫자 예외 패턴을 추가합니다. 
- [Get-CsInboundExemptNumberPattern은](/powershell/module/skype/Get-CsInboundExemptNumberPattern) 테넌트 목록에 추가된 모든 숫자 예외 패턴 목록을 반환합니다.
- [Set-CsInboundExemptNumberPattern은](/powershell/module/skype/Set-CsInboundExemptNumberPattern) 테넌트 목록의 숫자 예외 패턴에 하나 이상의 매개 변수를 수정합니다.
- [Remove-CsInboundExemptNumberPattern은](/powershell/module/skype/Remove-CsInboundExemptNumberPattern) 테넌트 목록에서 숫자 예외 패턴을 제거합니다.

### <a name="examples"></a>예제

#### <a name="add-a-number-exception"></a>숫자 예외 추가

다음 예제에서 테넌트 관리자는 위의 예제에서 차단된 범위에 있는 경우에도 전화 번호 1(312) 555-8882 및 1(312) 555-8883으로 테넌트에 전화를 걸 수 있도록 허용합니다. 이를 사용하도록 설정하려면 다음과 같이 새 숫자 예외 패턴이 만들어집니다.

```PowerShell
New-CsInboundExemptNumberPattern  -Identity "AllowContoso1" -Pattern "^\+?1312555888[2|3]$" -Description "Allow Contoso helpdesk" -Enabled $True
```

숫자 패턴을 켜기 위해 **사용** 가능 매개 변수가 True로 설정됩니다. 이 특정 숫자 패턴을 사용하지 않도록 설정하기 위해 매개 변수를 False로 설정합니다.


#### <a name="view-all-number-exceptions"></a>모든 숫자 예외 보기

이 예제에서는 **ID** 매개 변수가 선택 사항입니다. ID **매개** 변수를 지정하지 않으면 이 cmdlet은 테넌트에 입력된 모든 숫자 예외 패턴 목록을 반환합니다.
 
```powershell
Get-CsInboundExemptNumberPattern -Identity <String>
```
 
```powershell
Get-CsInboundExemptNumberPattern 
```

#### <a name="modify-a-number-exception"></a>숫자 예외 수정

**Set-CsInboundExemptNumberPattern** cmdlet을 사용하면 주어진 숫자 패턴 ID에 대한 하나 이상의 매개 변수를 수정할 수 있습니다. 이 예제에서는 **ID 매개 변수가** 필요합니다.
 
```powershell
Set-CsInboundExemptNumberPattern -Identity <String> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsInboundExemptNumberPattern -Identity "AllowContoso1" -Enabled $False
```

#### <a name="remove-a-number-exception"></a>숫자 예외 제거

**Remove-CsInboundExemptNumberPattern** cmdlet은 테넌트 목록에서 주어진 숫자 패턴을 제거합니다. 이 예제에서는 **ID 매개 변수가** 필요합니다. 

ID를 알 수 없는 경우 **Get-CsInboundExemptNumberPattern** cmdlet을 사용하여 먼저 적절한 패턴을 찾고 ID를 기록합니다. 그런 다음 **Remove-CsInboundExemptNumberPattern** cmdlet을 실행하고 적절한 ID 값을 전달합니다.테스트하고 유효성을 검사하기 전에 복제 시간을 허용합니다.  

```powershell
Remove-CsInboundExemptNumberPattern -Identity <String>
```

```powershell
Remove-CsInboundExemptNumberPattern -Identity "AllowContoso1"
```

## <a name="test-whether-a-number-is-blocked"></a>숫자가 차단된지 여부를 테스트합니다.

**Test-CsInboundBlockedNumberPattern** cmdlet을 사용하여 테넌트에서 숫자가 차단되는지 여부를 확인할 수 있습니다.
 
**PhoneNumber** 매개 변수가 필요하며 +, 또는 ()과 같은 추가 문자가 없는 숫자 문자열이 해야 합니다. 결과 **IsNumberBlocked 매개** 변수는 테넌트에서 숫자가 차단된 경우 True 값을 반환합니다. 매개 변수가 차단되지 않은 경우 False를 반환합니다.

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

### <a name="examples"></a>예제

이 예제에서는 전화 번호 1(312) 555-8884가 위에서 만든 면제에 따라 호출할 수 있는 반면, 전화 번호 1(312) 555-8883은 위에서 만든 면제에 따라 호출할 수 있습니다.

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

호출자 차단에 대한 패턴 일치는 Regex를 사용하여 수행됩니다. 여러 도구를 온라인으로 사용하여 Regex 패턴 일치의 유효성을 검사할 수 있습니다. Regex 패턴에 익숙하지 않은 경우 기본에 익숙해지기 위해 시간이 걸릴 것이 좋습니다. 예상 결과를 얻지 못하게하려면 테넌트에 새 차단된 번호 일치를 추가하기 전에 패턴 일치를 유효성 검사하기 위해 도구를 사용합니다.