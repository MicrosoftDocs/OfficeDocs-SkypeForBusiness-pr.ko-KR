---
title: 비즈니스용 Skype Online에서 인바운드 통화 차단
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
ms.openlocfilehash: 16a646af3e456bb68a2a582cad7d6b742100c650
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820918"
---
# <a name="block-inbound-calls"></a>인바운드 호출 차단

이제 비즈니스용 Skype Online 통화 요금제는 PSTN(공용 전화망)에서 인바운드 통화 차단을 지원하고 있습니다. 이 기능을 사용하면 테넌트에 들어오는 모든 PSTN 호출의 호출자 ID가 일치하는지 목록에 대해 확인할 수 있도록 테넌트 전역 번호 패턴 목록을 정의할 수 있습니다. 일치하는 경우 들어오는 호출이 거부됩니다.

이 인바운드 호출 차단 기능은 PSTN에서 시작하여 테넌트 전역 기준으로만 작동하는 인바운드 호출에서만 작동합니다. 사용자 기준으로 사용할 수 없습니다.  

이 기능은 아직 직접 라우팅에 사용할 수 없습니다.

>[!NOTE]
> 차단된 호출자는 차단된 경우 약간 다른 동작을 경험할 수 있습니다. 동작은 차단된 발신자 통신 사업자에서 호출이 성공적으로 완료되지 못했다는 알림을 처리하는 방법을 기반으로 합니다. 예를 들어 통화를 전화로 완료할 수 없다고 표시하거나 단순히 통화를 떨어뜨리는 통신사 메시지가 있을 수 있습니다.

## <a name="call-blocking-admin-controls-and-information"></a>통화 차단 관리자 컨트롤 및 정보

숫자 차단에 대한 관리자 컨트롤은 PowerShell만 사용하여 제공됩니다. 숫자 블록 패턴은 정규식 패턴으로 정의됩니다. 식의 순서는 불확실합니다. 목록에서 첫 번째 패턴이 일치하여 호출이 차단됩니다. 차단된 호출자 목록에서 추가되거나 제거된 새 번호 또는 패턴은 패턴이 활성화되는 데 최대 24시간이 걸릴 수 있습니다.

## <a name="call-blocking-powershell-commands"></a>통화 차단 PowerShell 명령

숫자 패턴은 명령, 및 를 통해 ```CsInboundBlockedNumberPattern``` ```New``` ```Get``` ```Set``` ```Remove``` 관리됩니다. 특정 패턴의 활성화를 전환하는 기능을 포함하여 이러한 cmdlet을 사용하여 주어진 패턴을 관리할 수 있습니다.
- [Get-CsInboundBlockedNumberPattern은](https://docs.microsoft.com/powershell/module/skype/get-csinboundblockednumberpattern) 각각에 대한 이름, 설명, 사용(True/False) 및 패턴을 포함하여 테넌트 목록에 추가된 모든 차단된 번호 패턴 목록을 반환합니다.
- [New-CsInboundBlockedNumberPattern은](https://docs.microsoft.com/powershell/module/skype/new-csinboundblockednumberpattern) 차단된 숫자 패턴을 테넌트 목록에 추가합니다.
- [Remove-CsInboundBlockedNumberPattern은](https://docs.microsoft.com/powershell/module/skype/remove-csinboundblockednumberpattern) 테넌트 목록에서 차단된 숫자 패턴을 제거합니다.
- [Set-CsInboundBlockedNumberPattern은](https://docs.microsoft.com/powershell/module/skype/set-csinboundblockednumberpattern) 테넌트 목록에서 차단된 숫자 패턴의 매개 변수를 하나 이상 수정합니다.

전체 호출 차단 기능을 보고 활성화하는 것은 명령 및 를 통해 ```CsTenantBlockingCallingNumbers``` ```Get``` ```Set``` 관리됩니다.

- [Get-CsTenantBlockedCallingNumbers는](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockedcallingnumbers) Enabled(True/False)를 포함하여 전역 차단된 번호 목록에 대한 매개 변수를 반환합니다. 기능을 켜거나 끄는 것 이외에는 수동으로 수정할 수 없는 단일 전역 테넌트 정책이 있습니다.
- [Set-CsTenantBlockedCallingNumbers를](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockedcallingnumbers) 사용하면 테넌트 수준에서 전역 테넌트 차단 호출을 설정 및 해제하도록 수정할 수 있습니다.

### <a name="examples"></a>예제

#### <a name="block-a-number"></a>숫자 차단

이 예제에서 매개 ```-Enabled``` 변수는 ```-Description``` 선택 사항입니다.

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

새 패턴을 만들면 패턴이 기본적으로 사용하도록 설정됩니다. 설명은 자세한 정보를 제공하는 선택적 필드입니다.

패턴이 추가된 이유를 쉽게 이해할 수 있도록 의미 있는 이름을 제공하는 것이 좋습니다. 스팸 번호를 차단하는 경우 규칙의 이름을 일치되는 숫자 패턴과 동일하게 이름을 정하고 필요한 경우 설명에 추가 정보를 추가합니다.

패턴은 정규식(정규식)을 사용하여 일치합니다. 복제를 테스트하고 유효성을 검사하기 전에 시간을 허용합니다.

#### <a name="allow-a-number"></a>숫자 허용

이 예제에서는 매개 ```-Identity``` 변수가 필요합니다.

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```
 
ID를 알 수 없는 경우 cmdlet을 사용하여 먼저 적절한 패턴을 찾고 ```Get-CsInboundBlockedNumberPattern``` ID를 적어 냅니다. 그런 다음 ```Remove-CsTenantBlockedNumberPattern``` cmdlet을 실행하고 적절한 ID 값을 전달합니다.

복제를 테스트하고 유효성을 검사하기 전에 시간을 허용합니다.

#### <a name="view-all-number-patterns"></a>모든 숫자 패턴 보기

이 cmdlet을 실행하여 테넌트에 입력된 모든 차단된 번호 목록을 반환합니다.

```powershell
Get-CsInboundBlockedNumberPattern
```

기본 제공 PowerShell 필터링 기능을 사용하여 필요한 경우 반환된 값을 구문 분석합니다.

## <a name="add-number-exceptions"></a>숫자 예외 추가

명령, , 및 를 통해 차단된 숫자 패턴에 예외를 ```CsTenantBlockNumberExceptionPattern``` ```New``` 추가할 수 ```Get``` ```Set``` ```Remove``` 있습니다.

- [New-CsTenantBlockedNumberExceptionPattern은](https://docs.microsoft.com/powershell/module/skype/new-cstenantblockednumberexceptionpattern) 테넌트 목록에 숫자 예외 패턴을 추가합니다. 
- [Get-CsTenantBlockedNumberExceptionPattern은](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockednumberexceptionpattern) 테넌트 목록에 추가된 모든 숫자 예외 패턴 목록을 반환합니다.
- [Set-CsTenantBlockedNumberExceptionPattern은](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockednumberexceptionpattern) 하나 이상의 매개 변수를 테넌트 목록의 숫자 예외 패턴으로 수정합니다.
- [Remove-CsTenantBlockedNumberExceptionPattern은](https://docs.microsoft.com/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) 테넌트 목록에서 숫자 예외 패턴을 제거합니다.

### <a name="examples"></a>예제

#### <a name="add-a-number-exception"></a>숫자 예외 추가

이 예제에서는 새 숫자 예외 패턴이 만들어지며 기본적으로 패턴을 사용하도록 설정됩니다. 및 ```-Enabled``` ```-Description``` 매개 변수는 선택 사항입니다.

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"  
```

#### <a name="view-all-number-exceptions"></a>모든 숫자 예외 보기

이 예제에서 -Identity 매개 변수는 선택 사항입니다. 매개 변수를 지정하지 않으면 이 cmdlet은 테넌트에 입력된 모든 숫자 예외 패턴 목록을 ```-Identity``` 반환합니다.
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a>숫자 예외 수정

이 예제에서는 -Identity 매개 변수가 필수입니다. cmdlet을 사용하면 주어진 숫자 패턴 ID에 대해 하나 ```Set-CsTenantBlockedNumberExceptionPattern``` 이상의 매개 변수를 수정할 수 있습니다.
 
```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$" 
```

#### <a name="remove-a-number-exception"></a>숫자 예외 제거

이 예제에서는 매개 ```-Identity``` 변수가 필요합니다. 이 cmdlet은 테넌트 목록에서 주어진 숫자 패턴을 제거합니다.  ID를 알 수 없는 경우 cmdlet을 사용하여 먼저 적절한 패턴을 찾고 ```Get-CsInboundBlockedNumberPattern``` ID를 적어 냅니다. 그런 다음 ```Remove-CsTenantBlockedNumberExceptionPattern``` cmdlet을 실행하고 적절한 ID 값을 전달합니다.복제를 테스트하고 유효성을 검사하기 전에 시간을 허용합니다.  

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a>숫자가 차단되는지 테스트

cmdlet을 사용하여 테넌트에서 숫자가 ```Test-CsInboundBlockedNumberPattern``` 차단되는지 여부를 확인할 수 있습니다.
 
이 예제에서는 매개 ```-Phonenumber``` 변수가 ```-Tenant``` 필요합니다. 매개 변수는 + 또는 -와 같은 추가 문자가 없는 ```-PhoneNumber``` 숫자 문자열입니다. TRPS에서는 선택 ```-Tenant parameter``` 사항입니다. 결과 매개 변수는 숫자가 테넌트에서 차단된 경우 True 값을 반환하고 차단되지 않은 경우 False 값을 ```isNumberBlocked``` 반환합니다.

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 4255550101
```

|httpResponseCode  |isNumberBlocked   |errorMessage |
|---------|---------|---------|
|200    | True        |         |

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 6045550188
```

|httpResponseCode  |isNumberBlocked   |errorMessage |
|---------|---------|---------|
|200    | False        |         |

## <a name="a-note-about-regex"></a>Regex에 대한 참고 사항

앞에서 설명한 대로 호출자 차단에 대한 패턴 일치는 Regex를 사용하여 수행됩니다. 여러 도구를 온라인으로 사용하여 Regex 패턴 일치의 유효성을 검사할 수 있습니다. Regex 패턴에 익숙하지 않은 경우 기본에 익숙해지기 위해 다소 시간이 걸릴 수 있습니다. 예상된 결과를 얻습니다. 테넌트에 차단된 숫자 일치를 새로 추가하기 전에 패턴 일치의 유효성을 검사하는 도구를 사용합니다. 

## <a name="related-topics"></a>관련 항목

- [다음을 사용하여 비즈니스용 Skype Online을 관리하기 위해 Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
