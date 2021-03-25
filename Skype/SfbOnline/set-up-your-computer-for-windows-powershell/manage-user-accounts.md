---
title: 사용자 계정 관리
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: a226b0d4-6359-42b8-808d-4b8ab3736d3b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: 조직의 Get-CsOnlineUser 비즈니스용 Skype Windows PowerShell 정보를 얻습니다.
ms.openlocfilehash: a4675bdb438dd81f9c72aa743134f9a444f0d1f9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113154"
---
# <a name="manage-user-accounts"></a>사용자 계정 관리

## <a name="manage-user-accounts"></a>사용자 계정 관리

이 항목에는 다음 섹션이 포함되어 있습니다.

- [전체 Lync Online 사용자에 대한 정보 반환](manage-user-accounts.md#BKMKReturnInfoAboutAllUsers)

- [비즈니스용 Skype Online에서 특정 사용자에 대한 정보 반환](manage-user-accounts.md#BKMKReturnInfoSpecificUser)

- [비즈니스용 Skype Online의 특정 사용자에 대한 특정 정보 반환](manage-user-accounts.md#BKMKReturninfoSpecificUsers)

- [비즈니스용 Skype Online에서 필터링된 사용자 목록 반환](manage-user-accounts.md#BKMKReturnFilteredListofUsers)

> [!NOTE]
> **Set-CsUser** cmdlet은 비즈니스용 Skype Online 관리자에게 사용할 수 있는 cmdlet 집합에도 포함되어 있습니다. 그러나 **Set-CsUser는** _AudioVideoDisabled_ 매개 변수를 설정하는 경우를 제외하고 비즈니스용 Skype Online을 관리하는 데 사용할 수 없습니다. 다른 매개 변수로 cmdlet을 실행하려고 하면 "SipAddress"를 설정할 수 없습니다. 이와 유사한 오류 메시지로 실패합니다. 이 매개 변수는 원격 테넌트 PowerShell 내에서 제한됩니다.

### <a name="return-information-about-all-your-skype-for-business-online-users"></a>전체 Lync Online 사용자에 대한 정보 반환
<a name="BKMKReturnInfoAboutAllUsers"> </a>

비즈니스용 Skype Online에 사용하도록 설정된 모든 사용자에 대한 정보를 반환하기 위해 추가 매개 변수 없이 [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) cmdlet을 호출합니다.

```PowerShell
Get-CsOnlineUser
```

임의로 선택한 단일 사용자에 대한 정보를 반환하려면(예: 이 계정을 테스트 목적으로 사용하려면 **Get-CsOnlineUser** cmdlet)를 호출하고 _ResultSize_ 매개 변수를 1로 설정합니다.

```PowerShell
Get-CsOnlineUser -ResultSize 1
```

그러면 조직의 사용자 수에 관계없이 **Get-CsOnlineUser** cmdlet이 한 사용자에 대한 정보를 반환합니다. 5명 사용자에 대한 정보를 반환하기 위해 _ResultSize_ 매개 변수의 값을 5로 설정합니다.

```PowerShell
Get-CsOnlineUser -ResultSize 5
```

### <a name="return-information-for-a-specific-user-in-skype-for-business-online"></a>비즈니스용 Skype Online에서 특정 사용자에 대한 정보 반환
<a name="BKMKReturnInfoSpecificUser"> </a>

[Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) cmdlet을 호출할 때 특정 사용자 계정을 참조하는 여러 가지 방법이 있습니다. 사용자의 AD DS(Active Directory Domain Services) 표시 이름을 사용할 수 있습니다.

```PowerShell
Get-CsOnlineUser -Identity "Ken Myer"
```

사용자의 SIP 주소를 사용할 수 있습니다.

```PowerShell
Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"
```

사용자의 사용자 주체 이름(UPN)을 사용할 수 있습니다.

```PowerShell
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

### <a name="return-specific-information-for-specific-users-in-skype-for-business-online"></a>비즈니스용 Skype Online의 특정 사용자에 대한 특정 정보 반환
<a name="BKMKReturninfoSpecificUsers"> </a>

기본적으로 [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) cmdlet은 비즈니스용 Skype Online 사용자 계정에 대해 엄청난 양의 정보를 반환합니다. 해당 정보의 하위 집합에만 관심이 있는 경우 반환된 데이터를 **Select-Object** cmdlet에 파이프합니다. 예를 들어 이 명령은 사용자 Ken Myer에 대한 모든 데이터를 반환한 다음 **Select-Object** cmdlet을 사용하여 화면에 표시되는 정보를 Ken의 AD DS 표시 이름 및 다이얼 플랜으로 제한합니다.

```PowerShell
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

다음 명령은 모든 사용자의 표시 이름 및 다이얼 플랜을 반환합니다.

```PowerShell
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

비즈니스용 Skype Online 사용자 계정의 속성을 찾으하려면 다음 명령을 사용하세요.

```PowerShell
Get-CsOnlineUser | Get-Member
```

### <a name="return-a-filtered-list-of-users-in-skype-for-business-online"></a>비즈니스용 Skype Online에서 필터링된 사용자 목록 반환
<a name="BKMKReturnFilteredListofUsers"> </a>

[Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) cmdlet 및 _LdapFilter_ 또는 _Filter_ 매개 변수를 사용하여 대상 사용자 집합에 대한 정보를 쉽게 반환할 수 있습니다. 예를 들어 이 명령은 재무 부서에서 작업하는 모든 사용자를 반환합니다.

```PowerShell
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## <a name="related-topics"></a>관련 항목
[비즈니스용 Skype 온라인 관리용 컴퓨터를 Windows PowerShell](set-up-your-computer-for-windows-powershell.md)