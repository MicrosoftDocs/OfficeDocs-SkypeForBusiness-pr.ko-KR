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
# <a name="block-inbound-calls"></a>들어오는 통화 차단

전화 시스템 다이렉트 라우팅 및 통화 계획은 PSTN (공개 전환 전화 네트워크)에서 인바운드 호출을 차단 하는 기능을 지원 합니다. 이 기능을 사용 하면 수신 되는 모든 PSTN 호출의 발신자 ID를 해당 목록에 대해 테 넌 트에 대해 확인할 수 있습니다. 일치 하는 항목이 있으면 수신 통화가 거부 됩니다.

이 인바운드 통화 차단 기능은 PSTN에서 시작 되는 인바운드 통화에만 작동 하며 테 넌 트 전역 으로만 작동 합니다. 사용자 기준으로 사용할 수 없습니다.  

>[!NOTE]
> 차단 된 호출자는 차단 되 면 약간 다른 동작이 발생할 수 있습니다. 동작은 차단 된 호출자의 반송파가 통화가 성공적으로 완료 될 수 없다는 알림을 처리 하는 방법을 기반으로 합니다. 예에는 전화를 걸 수 없거나 통화를 삭제 하는 등 통화를 완료할 수 없음을 나타내는 통신 회사 메시지가 포함 될 수 있습니다.

## <a name="call-blocking-admin-controls-and-information"></a>통화 차단 관리 컨트롤 및 정보

차단 번호에 대 한 관리 컨트롤은 PowerShell을 사용 하는 경우에만 제공 됩니다. 숫자 블록 패턴은 정규식 패턴으로 정의 됩니다. 식의 순서는 중요 하지 않으며 목록에서 일치 하는 첫 번째 패턴은 호출이 차단 됨을 반환 합니다. 차단 된 호출자 목록에서 추가 하거나 제거 하는 새 숫자나 패턴은 패턴이 활성 상태가 되는 데 최대 24 시간까지 걸릴 수 있습니다.

## <a name="call-blocking-powershell-commands"></a>호출 차단 PowerShell 명령

**새**, **Get**, **Set**, **Remove**  - **CsInboundBlockedNumberPattern** cmdlet을 사용 하 여 번호 패턴을 관리 합니다. 지정 된 패턴의 활성화를 전환 하는 기능을 포함 하 여 지정 된 패턴을 이러한 cmdlet을 사용 하 여 관리할 수 있습니다.

- [CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/get-csinboundblockednumberpattern) 는 이름, 설명, Enabled (True/False), 각각의 패턴을 비롯 하 여 테 넌 트 목록에 추가 된 모든 차단 된 번호 패턴의 목록을 반환 합니다.
- [New-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/new-csinboundblockednumberpattern) 차단 된 번호 패턴을 테 넌 트 목록에 추가 합니다.
- [CsInboundBlockedNumberPattern 제거-](https://docs.microsoft.com/powershell/module/skype/remove-csinboundblockednumberpattern) 테 넌 트 목록에서 차단 된 번호 패턴을 제거 합니다.
- [Set-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/set-csinboundblockednumberpattern) 는 테 넌 트 목록에서 차단 된 번호 패턴의 매개 변수를 하나 이상 수정 합니다.

전체 통화 차단 기능 보기 및 활성화는 **Get**, **Set**  - **CsTenantBlockingCallingNumbers** cmdlet을 통해 관리 됩니다.

- [CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockedcallingnumbers) 는 허용 (True/False)을 포함 하 여 전체 차단 된 번호 목록의 매개 변수를 반환 합니다. 기능을 설정 하거나 해제 하는 것 외에는 수동으로 수정할 수 없는 단일 전역 테 넌 트 정책이 있습니다.
- [Set-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockedcallingnumbers) 를 사용 하면 테 넌 트 차단 된 통화를 수신 대기 수준에서 켜거나 끄도록 수정할 수 있습니다.

### <a name="examples"></a>예제

#### <a name="block-a-number"></a>숫자 차단

이 예제에서 **Enabled** 및 **Description** 매개 변수는 선택 사항입니다.

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

새 패턴을 만들면 기본적으로 사용 하도록 설정 된 패턴이 추가 됩니다. 설명은 추가 정보를 제공 하는 선택적 필드입니다.

패턴이 추가 된 이유를 쉽게 이해할 수 있도록 의미 있는 이름을 제공 하는 것이 좋습니다. 단순히 스팸 번호를 차단 하는 경우, 일치 하는 번호 패턴과 같은 규칙 이름을 지정 하 고 필요에 따라 설명에 추가 정보를 추가 하는 것이 좋습니다.

패턴은 정규식 (Regex)을 사용 하 여 일치 합니다. 테스트 하 고 유효성을 검사 하기 전에 복제 시간을 허용 합니다.

#### <a name="allow-a-number"></a>숫자 허용

이 예제에서는 **id** 매개 변수가 필요 합니다.

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```
 
Id가 알려지지 않은 경우 **CsInboundBlockedNumberPattern** cmdlet을 사용 하 여 먼저 올바른 패턴을 찾고 id를 확인 합니다. 그런 다음 **Remove-CsTenantBlockedNumberPattern** cmdlet을 실행 하 고 적절 한 id 값을 전달 합니다.

테스트 하 고 유효성을 검사 하기 전에 복제 시간을 허용 합니다.

#### <a name="view-all-number-patterns"></a>모든 숫자 패턴 보기

이 cmdlet을 실행 하면 테 넌 트에 대해 입력 한 모든 차단 된 번호 목록이 반환 됩니다.

```powershell
Get-CsInboundBlockedNumberPattern
```

기본 제공 PowerShell 필터링 기능을 사용 하 여 반환 된 값을 필요에 따라 구문 분석 합니다.

## <a name="add-number-exceptions"></a>숫자 예외 추가

**New**, **Get**, **Set** **,**  - **csten앤틸리스 블록 번호 exceptionpattern** cmdlet을 사용 하 여 차단 된 번호 패턴에 예외를 추가할 수 있습니다.

- [CsTenantBlockedNumberExceptionPattern 새](https://docs.microsoft.com/powershell/module/skype/new-cstenantblockednumberexceptionpattern) 테 넌 트 목록에 숫자 예외 패턴을 추가 합니다. 
- [Get-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockednumberexceptionpattern) 는 테 넌 트 목록에 추가 된 모든 숫자 예외 패턴의 목록을 반환 합니다.
- [Set-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockednumberexceptionpattern) 는 하나 이상의 매개 변수를 테 넌 트 목록의 숫자 예외 패턴으로 수정 합니다.
- [CsTenantBlockedNumberExceptionPattern 제거-](https://docs.microsoft.com/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) 테 넌 트 목록에서 번호 예외 패턴을 제거 합니다.

### <a name="examples"></a>예제

#### <a name="add-a-number-exception"></a>숫자 예외 추가

이 예제에서는 새 숫자 예외 패턴이 만들어지고 기본적으로 패턴을 enabled로 추가 합니다. **Enabled** 및 **Description** 매개 변수는 선택 사항입니다.

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"  
```

#### <a name="view-all-number-exceptions"></a>모든 숫자 예외 보기

이 예제에서 **Identity** 매개 변수는 선택 사항입니다. **Id** 매개 변수를 지정 하지 않으면이 cmdlet은 테 넌 트에 대해 입력 된 모든 숫자 예외 패턴 목록을 반환 합니다.
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a>숫자 예외 수정

이 예제에서 **Identity** 매개 변수는 필수입니다. **CsTenantBlockedNumberExceptionPattern** cmdlet을 사용 하면 지정 된 번호 패턴 id에 대 한 하나 이상의 매개 변수를 수정할 수 있습니다.
 
```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$" 
```

#### <a name="remove-a-number-exception"></a>숫자 예외 제거

이 예제에서는 **id** 매개 변수가 필요 합니다. 이 cmdlet은 테 넌 트 목록에서 지정 된 번호 패턴을 제거 합니다.  Id가 알려지지 않은 경우 **CsInboundBlockedNumberPattern** cmdlet을 사용 하 여 먼저 올바른 패턴을 찾고 id를 확인 합니다. 그런 다음 **Remove-CsTenantBlockedNumberExceptionPattern** cmdlet을 실행 하 고 적절 한 id 값을 전달 합니다.테스트 하 고 유효성을 검사 하기 전에 복제 시간을 허용 합니다.  

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a>숫자가 차단 되었는지 테스트

**CsInboundBlockedNumberPattern** cmdlet을 사용 하 여 해당 숫자가 테 넌 트에서 차단 되었는지 여부를 확인 합니다.
 
이 예제에서는 **PhoneNumber** 및 **테 넌 트** 매개 변수가 필요 합니다. **PhoneNumber** 매개 변수는 + 또는-등의 추가 문자 없이 숫자 문자열 이어야 합니다. TRPS에서 **테 넌 트 매개 변수** 는 선택 사항입니다. 결과 **Is번호 차단** 된 매개 변수는 해당 숫자가 테 넌 트에서 차단 되는 경우 True 값을 반환 하 고, 차단 되지 않으면 False입니다.

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 4255550101
```

|httpResponseCode  |Is번호 차단 됨   |errorMessage |
|---------|---------|---------|
|200    | False        |         |

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 6045550188
```

|httpResponseCode  |Is번호 차단 됨   |errorMessage |
|---------|---------|---------|
|200    | 해제        |         |

## <a name="a-note-about-regex"></a>Regex에 대 한 참고 사항

앞에서 설명한 대로 호출자 차단에 대 한 패턴 일치는 Regex를 사용 하 여 수행 됩니다. Regex 패턴 일치의 유효성을 검사 하는 데 도움이 되는 여러 도구를 온라인에서 사용할 수 있습니다. Regex 패턴에 익숙하지 않은 경우 기본 사항에 익숙해지는 데 약간의 시간이 소요 되는 것이 좋습니다. 예상 되는 결과를 얻으려면 새 차단 된 번호 일치 항목을 테 넌 트에 추가 하기 전에 패턴 일치의 유효성을 검사 하기 위한 도구를 사용 하세요.
