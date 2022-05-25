---
title: 비즈니스용 Skype Online에서 인바운드 호출 차단
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
audience: Admin
ms.reviewer: roykuntz
appliesto:
- Skype for Business
ms.localizationpriority: medium
ms.custom: Learn how to use PowerShell to manage inbound call blocking in Skype for Business Online.
description: 관리자는 비즈니스용 Skype Online에서 인바운드 통화를 차단하는 방법을 알아볼 수 있습니다.
ms.openlocfilehash: 40b43f669ededf7ac334c25c79b5af09140c075d
ms.sourcegitcommit: c53c22069b1babce7a2364de631057ff501ca1c0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65671654"
---
# <a name="block-inbound-calls"></a>인바운드 호출 차단

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

비즈니스용 Skype 온라인 통화 플랜은 이제 PSTN(공중 전화망)에서 인바운드 통화 차단을 지원합니다. 이 기능을 사용하면 테넌트에 들어오는 모든 PSTN 호출의 호출자 ID를 일치 목록에 대해 확인할 수 있도록 테넌트 전역 번호 패턴 목록을 정의할 수 있습니다. 일치하는 항목이 있으면 들어오는 호출이 거부됩니다.

이 인바운드 호출 차단 기능은 PSTN에서 시작된 인바운드 호출에서만 작동하며 테넌트 전역에서만 작동합니다. 사용자별로 사용할 수 없습니다.

이 기능은 아직 직접 라우팅에 사용할 수 없습니다.

>[!NOTE]
> 차단된 호출자는 차단되었을 때 약간 다른 동작이 발생할 수 있습니다. 이 동작은 차단된 호출자의 통신 사업자가 호출을 성공적으로 완료할 수 없다는 알림을 처리하는 방법을 기반으로 합니다. 전화 걸기로 통화를 완료할 수 없거나 단순히 전화를 끊을 수 없다는 통신 사업자 메시지가 예로 포함될 수 있습니다.

## <a name="call-blocking-admin-controls-and-information"></a>호출 차단 관리자 컨트롤 및 정보

차단 번호에 대한 관리 컨트롤은 PowerShell만 사용하여 제공됩니다. 숫자 블록 패턴은 정규식 패턴으로 정의됩니다. 식의 순서는 중요하지 않습니다. 목록에서 일치하는 첫 번째 패턴은 호출이 차단됩니다. 차단된 호출자 목록에서 추가되거나 제거된 새 번호 또는 패턴은 패턴이 활성화되는 데 최대 24시간이 걸릴 수 있습니다.

## <a name="call-blocking-powershell-commands"></a>통화 차단 PowerShell 명령

숫자 패턴은 명령, ```Get```및 .를 통해 ```CsInboundBlockedNumberPattern``` 관리됩니다```New```.```Remove``````Set``` 지정된 패턴의 활성화를 토글하는 기능을 포함하여 이러한 cmdlet을 사용하여 지정된 패턴을 관리할 수 있습니다.
- [Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) 은 이름, 설명, 사용(True/False) 및 각각에 대한 패턴을 포함하여 테넌트 목록에 추가된 모든 차단된 숫자 패턴 목록을 반환합니다.
- [New-CsInboundBlockedNumberPattern](/powershell/module/skype/new-csinboundblockednumberpattern) 은 차단된 숫자 패턴을 테넌트 목록에 추가합니다.
- [Remove-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) 은 테넌트 목록에서 차단된 숫자 패턴을 제거합니다.
- [Set-CsInboundBlockedNumberPattern은](/powershell/module/skype/set-csinboundblockednumberpattern) 테넌트 목록에서 차단된 숫자 패턴의 매개 변수를 하나 이상 수정합니다.

전체 통화 차단 기능 보기 및 활성화는 명령 및 ```Set```을 ```CsTenantBlockingCallingNumbers``` 통해 관리됩니다```Get```.

- [Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) 는 Enabled(True/False)를 포함하여 전역 차단된 숫자 목록에 대한 매개 변수를 반환합니다. 기능을 켜거나 끄는 것 외에는 수동으로 수정할 수 없는 단일 전역 테넌트 정책이 있습니다.
- [Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) 를 사용하면 테넌트 수준에서 전역 테넌트 차단 호출을 켜고 끌 수 있습니다.

### <a name="examples"></a>예제

#### <a name="block-a-number"></a>숫자 차단

이 예제에서 ```-Enabled``` 매개 변수 및 ```-Description``` 매개 변수는 선택 사항입니다.

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

새 패턴을 만들면 기본적으로 사용하도록 설정된 패턴이 추가됩니다. 설명은 추가 정보를 제공하는 선택적 필드입니다.

패턴이 추가된 이유를 쉽게 이해할 수 있도록 의미 있는 이름을 제공하는 것이 좋습니다. 단순히 스팸 번호를 차단하는 경우 일치하는 숫자 패턴과 동일한 규칙 이름을 지정하고 필요에 따라 설명에 추가 정보를 추가하는 것이 좋습니다.

패턴은 정규식(Regex)을 사용하여 일치합니다.
테스트하고 유효성을 검사하기 전에 복제 시간을 허용합니다.

#### <a name="allow-a-number"></a>숫자 허용

이 예제에서는 매개 변수가 ```-Identity``` 필요합니다.

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```

ID를 알 수 없는 경우 cmdlet을 ```Get-CsInboundBlockedNumberPattern``` 사용하여 먼저 적절한 패턴을 찾고 ID를 기록해 둡다. 그런 다음 cmdlet을 ```Remove-CsTenantBlockedNumberPattern``` 실행하고 적절한 ID 값을 전달합니다.

테스트하고 유효성을 검사하기 전에 복제 시간을 허용합니다.

#### <a name="view-all-number-patterns"></a>모든 숫자 패턴 보기

이 cmdlet을 실행하면 테넌트에 대해 입력된 모든 차단된 숫자 목록이 반환됩니다.

```powershell
Get-CsInboundBlockedNumberPattern
```

기본 제공 PowerShell 필터링 기능을 사용하여 필요에 따라 반환된 값을 구문 분석합니다.

## <a name="add-number-exceptions"></a>숫자 예외 추가

명령, ```New```, ```Set``````Get```및 ```Remove```명령을 통해 차단된 숫자 패턴에 ```CsTenantBlockNumberExceptionPattern``` 예외를 추가할 수 있습니다.

- [New-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/new-cstenantblockednumberexceptionpattern) 은 테넌트 목록에 숫자 예외 패턴을 추가합니다.
- [Get-CsTenantBlockedNumberExceptionPattern은](/powershell/module/skype/get-cstenantblockednumberexceptionpattern) 테넌트 목록에 추가된 모든 숫자 예외 패턴의 목록을 반환합니다.
- [Set-CsTenantBlockedNumberExceptionPattern은](/powershell/module/skype/set-cstenantblockednumberexceptionpattern) 하나 이상의 매개 변수를 테넌트 목록의 숫자 예외 패턴으로 수정합니다.
- [Remove-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) 은 테넌트 목록에서 숫자 예외 패턴을 제거합니다.

### <a name="examples"></a>예제

#### <a name="add-a-number-exception"></a>숫자 예외 추가

이 예제에서는 새 숫자 예외 패턴이 만들어지고 기본적으로 사용으로 패턴을 추가합니다. 및 ```-Description``` 매개 변수는 ```-Enabled``` 선택 사항입니다.

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"
```

#### <a name="view-all-number-exceptions"></a>모든 숫자 예외 보기

이 예제에서 -Identity 매개 변수는 선택 사항입니다. 매개 변수를 ```-Identity``` 지정하지 않으면 이 cmdlet은 테넌트에 대해 입력된 모든 숫자 예외 패턴의 목록을 반환합니다.

```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a>숫자 예외 수정

이 예제에서는 -Identity 매개 변수가 필수입니다. cmdlet을 ```Set-CsTenantBlockedNumberExceptionPattern``` 사용하면 지정된 숫자 패턴 ID에 대해 하나 이상의 매개 변수를 수정할 수 있습니다.

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string>
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$"
```

#### <a name="remove-a-number-exception"></a>숫자 예외 제거

이 예제에서는 매개 변수가 ```-Identity``` 필요합니다. 이 cmdlet은 테넌트 목록에서 지정된 숫자 패턴을 제거합니다.  ID를 알 수 없는 경우 cmdlet을 ```Get-CsInboundBlockedNumberPattern``` 사용하여 먼저 적절한 패턴을 찾고 ID를 기록해 둡다. 그런 다음 cmdlet을 ```Remove-CsTenantBlockedNumberExceptionPattern``` 실행하고 적절한 ID 값을 전달합니다. 테스트하고 유효성을 검사하기 전에 복제 시간을 허용합니다.

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a>숫자가 차단되었는지 테스트

cmdlet을 ```Test-CsInboundBlockedNumberPattern``` 사용하여 테넌트에서 숫자가 차단되었는지 확인합니다.

이 예제에서는 ```-Phonenumber``` 매개 변수와 ```-Tenant``` 매개 변수가 필요합니다. 매개 변수는 ```-PhoneNumber``` + 또는 -와 같은 추가 문자가 없는 숫자 문자열이어야 합니다. TRPS에서 선택 ```-Tenant parameter``` 사항입니다. 결과 ```isNumberBlocked``` 매개 변수는 숫자가 테넌트에서 차단된 경우 True, 차단되지 않은 경우 False 값을 반환합니다.

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 4255550101
```

|httpResponseCode  |isNumberBlocked   |errorMessage |
|---------|---------|---------|
|200    | 사실        |         |

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 6045550188
```

|httpResponseCode  |isNumberBlocked   |errorMessage |
|---------|---------|---------|
|200    | False        |         |

## <a name="a-note-about-regex"></a>Regex에 대한 참고 사항

앞에서 설명한 대로 차단 호출자에 대한 패턴 일치는 Regex를 사용하여 수행됩니다. Regex 패턴 일치의 유효성을 검사하는 데 도움이 되는 여러 도구를 온라인으로 사용할 수 있습니다. Regex 패턴에 익숙하지 않은 경우 잠시 시간을 내어 기본 사항을 숙지하는 것이 좋습니다. 예상된 결과를 얻으려면 테넌트에 차단된 숫자 일치를 새로 추가하기 전에 패턴 일치의 유효성을 검사하는 도구를 사용합니다.

## <a name="related-topics"></a>관련 항목

- [Windows PowerShell 사용하여 비즈니스용 Skype Online을 관리하도록 컴퓨터 설정](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
