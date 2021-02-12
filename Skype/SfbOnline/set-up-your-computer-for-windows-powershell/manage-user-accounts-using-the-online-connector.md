---
title: 온라인 커넥터를 사용하여 사용자 계정 관리
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
description: 조직의 Get-CsOnlineUser 비즈니스용 Skype online Windows PowerShell 정보를 얻습니다.
ms.openlocfilehash: 370150de08493507d7b401d7907c90f343802d88
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41692653"
---
# <a name="manage-user-accounts-using-the-online-connector"></a>온라인 커넥터를 사용하여 사용자 계정 관리

## <a name="manage-user-accounts"></a>사용자 계정 관리

이 항목에는 다음 섹션이 포함되어 있습니다.

- [전체 Lync Online 사용자에 대한 정보 반환](manage-user-accounts-using-the-online-connector.md#BKAllUsers)

- [비즈니스용 Skype Online에서 특정 사용자에 대한 정보 반환](manage-user-accounts-using-the-online-connector.md#BKSpecificUser)

- [비즈니스용 Skype Online에서 특정 사용자에 대한 특정 정보 반환](manage-user-accounts-using-the-online-connector.md#BKSpecificUsers)

- [비즈니스용 Skype Online에서 필터링된 사용자 목록 반환](manage-user-accounts-using-the-online-connector.md#BKListofUsers)

> [!NOTE]
> **Set-CsUser** cmdlet은 비즈니스용 Skype Online 관리자가 사용할 수 있는 cmdlet 집합에도 포함되어 있습니다. 그러나 **현재 Set-CsUser는** _AudioVideoDisabled_ 매개 변수를 설정하는 것을 제외하고 비즈니스용 Skype Online을 관리하는 데 사용할 수 없습니다. 다른 매개 변수를 사용하여 cmdlet을 실행하려고 하면 "SipAddress"를 설정할 수 없습니다. 이 매개 변수는 원격 테넌트 PowerShell 내에서 제한됩니다.

### <a name="return-information-about-all-your-skype-for-business-online-users"></a>전체 Lync Online 사용자에 대한 정보 반환
<a name="BKAllUsers"> </a>

비즈니스용 Skype Online을 사용하도록 설정된 모든 사용자에 대한 정보를 반환하기 위해 추가 매개 변수 없이 [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet을 호출합니다.

```PowerShell
Get-CsOnlineUser
```

임의로 선택한 단일 사용자에 대한 정보를 반환하려면(예: 테스트 목적으로 이 계정을 사용하려면) **Get-CsOnlineUser** cmdlet을 호출하고 _ResultSize_ 매개 변수를 1로 설정하세요.

```PowerShell
Get-CsOnlineUser -ResultSize 1
```

이렇게 하면 **Get-CsOnlineUser** cmdlet이 조직에 있는 사용자 수에 관계없이 한 사용자에 대한 정보를 반환합니다. 5명 사용자에 대한 정보를 반환하기 위해 _ResultSize_ 매개 변수 값을 5로 설정하세요.

```PowerShell
Get-CsOnlineUser -ResultSize 5
```

### <a name="return-information-for-a-specific-user-in-skype-for-business-online"></a>비즈니스용 Skype Online에서 특정 사용자에 대한 정보 반환
<a name="BKSpecificUser"> </a>

[Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet을 호출할 때 특정 사용자 계정을 참조하는 여러 가지 방법이 있습니다. 사용자의 AD DS(Active Directory Domain Services) 표시 이름을 사용할 수 있습니다.

```PowerShell
Get-CsOnlineUser -Identity "Ken Myer"
```

사용자의 SIP 주소를 사용할 수 있습니다.

```PowerShell
Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"
```

사용자의 UPN(사용자 계정 이름)을 사용할 수 있습니다.

```PowerShell
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

### <a name="return-specific-information-for-specific-users-in-skype-for-business-online"></a>비즈니스용 Skype Online에서 특정 사용자에 대한 특정 정보 반환
<a name="BKSpecificUsers"> </a>

기본적으로 [Get-CsOnlineUser](https://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) cmdlet은 비즈니스용 Skype Online 사용자 계정에 대해 엄청난 양의 정보를 반환합니다. 해당 정보의 하위 집합에만 관심이 있는 경우 반환된 데이터를 **Select-Object** cmdlet으로 파이프합니다. 예를 들어 이 명령은 Ken Myer 사용자에 대한 모든 데이터를 반환한 다음 **Select-Object** cmdlet을 사용하여 화면에 표시되는 정보를 Ken의 AD DS 표시 이름 및 다이얼 플랜으로 제한합니다.

```PowerShell
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

다음 명령은 모든 사용자의 표시 이름 및 다이얼 플랜을 반환합니다.

```PowerShell
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

비즈니스용 Skype Online 사용자 계정의 속성을 찾으면 다음 명령을 사용하세요.

```PowerShell
Get-CsOnlineUser | Get-Member
```

### <a name="return-a-filtered-list-of-users-in-skype-for-business-online"></a>비즈니스용 Skype Online에서 필터링된 사용자 목록 반환
<a name="BKListofUsers"> </a>

[Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet 및 _LdapFilter_ 또는 _Filter_ 매개 변수를 사용하여 대상 사용자 집합에 대한 정보를 쉽게 반환할 수 있습니다. 예를 들어 이 명령은 재무 부서에서 작업하는 모든 사용자를 반환합니다.

```PowerShell
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## <a name="related-topics"></a>관련 항목
[비즈니스용 Skype 온라인 관리를 위한 컴퓨터를 Windows PowerShell](set-up-your-computer-for-windows-powershell.md)


