---
title: 클라이언트에서 스마트 연락처 비즈니스용 Skype 구성
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 4eecb5f7-3ef7-4582-a6cb-9f4aa068338d
description: '요약: 클라이언트에서 스마트 연락처 목록 기능을 켜는 비즈니스용 Skype 있습니다.'
ms.openlocfilehash: d7e2957b6b8622ea8c3ce3dc2974e7dbb7ff51d4
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58580002"
---
# <a name="configure-smart-contacts-list-in-skype-for-business-clients"></a>클라이언트에서 스마트 연락처 비즈니스용 Skype 구성

**요약:** 클라이언트에서 스마트 연락처 목록 기능을 켜는 방법을 비즈니스용 Skype 합니다.

스마트 연락처 목록 기능을 사용하면 최종 사용자의 연락처 목록을 자동으로 사용할 수 있습니다. 사용자를 처음 비즈니스용 Skype 경우 사용자는 자신의 관리자와 팀의 다른 사용자를 자동으로 볼 수 있습니다. 이 기능은 Microsoft 365 Office 365 사용자에 대해 기본적으로 설정되지만 클라이언트 정책 설정을 구성하여 이 기능을 명시적으로 사용하도록 설정해야 합니다.

이 기능을 구성할 때 다음에 유의하십시오.

- 최대 13명인 사용자는 다음 순서로 스마트 연락처 목록에 자동으로 추가됩니다.

  1. Manager

  2. 지시문(사전순)

  3. 피어(사전순)

- 사용자가 처음 로그인하면 My Group이라는 새 그룹이 만들어집니다. 그룹은 관리자 필드에 채워진 사용자 별칭에 따라 사용자의 AD 그룹 관계에 있는 사용자로 자동으로 채워집니다. AD 그룹 구성원 자격을 변경하면 처음 채워진 후 내 그룹이 업데이트되지는 않습니다. 사용자가 연락처나 그룹을 삭제하면 연락처와 그룹이 모두 다시 만들어지지 않습니다. 

- 자동 태그 지정이 설정되어 있는 경우 목록의 연락처에 현재 상태 변경에 대한 태그가 지정됩니다. 자동 태그 지정은 기본적으로 설정되어 있지만 해제할 수 있습니다. 

- 그룹의 모든 새 사용자는 연락처 목록에 추가된 것으로 표시됩니다. 사용자는 자신의 내 그룹 또는 선택한 다른 그룹에 새 구성원을 수동으로 추가할 수 있습니다.

- 이 기능은 처음 로그인하는 사용자에게만 작동합니다. 사용자가 이전에 모바일 장치 또는 Mac을 비롯한 모든 장치에서 로그인한 경우 해당 사용자에 대해 이 기능을 사용할 수 없습니다.

## <a name="configure-smart-contacts-list"></a>스마트 연락처 목록 구성

사용자에 대해 스마트 연락처 목록 기능을 사용하도록 설정하려면 다음 단계를 수행해야 합니다. 

- 새 CsClientPolicy 항목을 만들어 전역 클라이언트 정책에 추가합니다. 

- 주소부 검색이 웹 검색 전용으로 구성되어 있는지 확인

### <a name="create-a-policy-entry-to-enable-smart-contacts-list"></a>스마트 연락처 목록을 사용하도록 설정하는 정책 항목 만들기

스마트 연락처 목록 기능을 사용하도록 설정하는 정책 항목을 만들하려면 다음과 같이 EnableClientAutoPopulateWithTeam 옵션과 함께 [New-CsClientPolicyEntry](/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) cmdlet을 사용합니다.

```powershell
$x=New-CsClientPolicyEntry -Name EnableClientAutoPopulateWithTeam -Value $True
```

다음으로 [Set-CsClientPolicy](/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet을 사용하여 글로벌 정책에 다음과 같이 변경 내용을 기록합니다.

```powershell
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

선택적으로 다음과 같이 자동 태그 지정을 해제하는 정책을 만들 수 있습니다.

```powershell
$x=New-CsClientPolicyEntry -Name TagContactsInClientAutoPopulatedGroup -Value $False
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

또한 해당 정책에 대한 AddressBookAvailability 매개 변수를 WebSearchOnly로 설정해야 합니다. 자세한 내용은 [Set-CsClientPolicy를 참조하세요.](/powershell/module/skype/set-csclientpolicy?view=skype-ps) 

### <a name="troubleshoot"></a>문제 해결

스마트 연락처 목록이 예상대로 작동하지 않는 경우 다음을 검사합니다.

- 구성의 유효성을 검사합니다. 

- AD 조직 정보가 채워지는지 확인

- 추가 비즈니스용 Skype 위해 새 사용자에 대한 클라이언트 로그를 수집합니다.

- 주소 비즈니스용 Skype 연결할 수 없다는 메시지가 클라이언트 UI에 표시되지 않는지 확인 주소장 연결을 확인하기 위해 클라이언트 검색 비즈니스용 Skype 검색합니다.

- AD DS 복제 문제로 인해 사용자가 처음 로그인할 때 연락처가 해결되지 비즈니스용 Skype.