---
title: 온라인 커넥터를 사용 하 여 사용자 계정 관리
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
f1keywords: None
ms.custom:
- PowerShell
description: Windows PowerShell의 CsOnlineUser cmdlet을 사용 하 여 조직의 비즈니스용 Skype Online 사용자에 대 한 정보를 얻을 수 있습니다.
ms.openlocfilehash: 143f7934564caf4e2c00b5b4a40bc6f2e597950d
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40990993"
---
# <a name="manage-user-accounts-using-the-online-connector"></a>온라인 커넥터를 사용 하 여 사용자 계정 관리

## <a name="manage-user-accounts"></a>사용자 계정 관리

이 항목에서는 다음 섹션을 다룹니다.

- [전체 Lync Online 사용자에 대한 정보 반환](manage-user-accounts-using-the-online-connector.md#BKAllUsers)

- [비즈니스용 Skype Online에서 특정 사용자에 대 한 정보 반환](manage-user-accounts-using-the-online-connector.md#BKSpecificUser)

- [비즈니스용 Skype Online에서 특정 사용자에 대 한 특정 정보 반환](manage-user-accounts-using-the-online-connector.md#BKSpecificUsers)

- [비즈니스용 Skype Online에서 필터링 된 사용자 목록 반환](manage-user-accounts-using-the-online-connector.md#BKListofUsers)

> [!NOTE]
> **집합-CsUser** Cmdlet은 비즈니스용 Skype Online 관리자가 사용할 수 있는 cmdlet 집합에도 포함 되어 있습니다. 그러나, **사용자** 는 현재 비즈니스용 Skype Online을 관리 하는 데 사용할 수 없습니다 (예를 들어, _오디오 videodisabled_ 매개 변수를 설정 하는 경우 제외). 다른 매개 변수를 사용 하 여 cmdlet을 실행 하려고 하면 다음과 같은 오류 메시지가 표시 되지 않습니다. "SipAddress"을 설정할 수 없습니다. 이 매개 변수는 원격 테 넌 트 PowerShell 내에서 제한 됩니다.

### <a name="return-information-about-all-your-skype-for-business-online-users"></a>전체 Lync Online 사용자에 대한 정보 반환
<a name="BKAllUsers"> </a>

비즈니스용 Skype Online을 사용 하도록 설정 된 모든 사용자에 대 한 정보를 반환 하려면 추가 매개 변수 없이 [CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet을 호출 합니다.

```PowerShell
Get-CsOnlineUser
```

무작위로 선택한 단일 사용자 (예: 테스트 목적으로이 계정을 사용 하는 경우)에 대 한 정보를 반환 하려면 **Get-CsOnlineUser** cmdlet을 호출 하 고 _resultsize_ 매개 변수를 1로 설정 합니다.

```PowerShell
Get-CsOnlineUser -ResultSize 1
```

이렇게 하면 조직에서 사용 하는 사용자 수에 관계 없이 **CsOnlineUser** cmdlet이 한 명의 사용자에 대 한 정보를 반환 합니다. 5 명의 사용자에 대 한 정보를 반환 하려면 _Resultsize_ 매개 변수 값을 5로 설정 합니다.

```PowerShell
Get-CsOnlineUser -ResultSize 5
```

### <a name="return-information-for-a-specific-user-in-skype-for-business-online"></a>비즈니스용 Skype Online에서 특정 사용자에 대 한 정보 반환
<a name="BKSpecificUser"> </a>

[CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet을 호출할 때 특정 사용자 계정을 참조 하는 방법에는 여러 가지가 있습니다. 사용자의 AD DS (Active Directory 도메인 서비스) 표시 이름을 사용할 수 있습니다.

```PowerShell
Get-CsOnlineUser -Identity "Ken Myer"
```

사용자의 SIP 주소를 사용할 수 있습니다.

```PowerShell
Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"
```

사용자의 UPN (사용자 계정 이름)을 사용할 수 있습니다.

```PowerShell
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

### <a name="return-specific-information-for-specific-users-in-skype-for-business-online"></a>비즈니스용 Skype Online에서 특정 사용자에 대 한 특정 정보 반환
<a name="BKSpecificUsers"> </a>

기본적으로 [CsOnlineUser](https://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) cmdlet은 각 비즈니스용 Skype Online 사용자 계정에 대 한 방대한 양의 정보를 반환 합니다. 해당 정보의 하위 집합에만 관심이 있는 경우 반환 된 데이터를 **개체 선택** cmdlet에 파이프 합니다. 예를 들어이 명령은 사용자: 진구 Myer에 대 한 모든 데이터를 반환 하 고 **개체 선택** cmdlet을 사용 하 여 화면에 표시 되는 정보를: 진구의 AD DS 표시 이름 및 다이얼 플랜으로 제한 합니다.

```PowerShell
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

다음 명령은 모든 사용자의 표시 이름 및 다이얼 플랜을 반환 합니다.

```PowerShell
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

비즈니스용 Skype Online 사용자 계정의 속성을 찾으려면 다음 명령을 사용 합니다.

```PowerShell
Get-CsOnlineUser | Get-Member
```

### <a name="return-a-filtered-list-of-users-in-skype-for-business-online"></a>비즈니스용 Skype Online에서 필터링 된 사용자 목록 반환
<a name="BKListofUsers"> </a>

[CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) Cmdlet 및 _Ldapfilter_ 또는 _Filter_ 매개 변수를 사용 하 여 대상 사용자 집합에 대 한 정보를 쉽게 반환할 수 있습니다. 예를 들어이 명령은 재무 부서에서 근무 하는 모든 사용자를 반환 합니다.

```PowerShell
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## <a name="related-topics"></a>관련 항목
[Windows PowerShell을 사용 하 여 비즈니스용 skype online 관리를 위한 컴퓨터 설정](set-up-your-computer-for-windows-powershell.md)


