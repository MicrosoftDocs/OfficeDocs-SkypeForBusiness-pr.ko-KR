---
title: 전화 접속 회의에 대한 PIN 정책 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 459e80bf-5791-49f8-878d-4a5178b3a210
description: '요약: 2013에서 전화 접속 회의에 대한 PIN 정책을 관리하는 비즈니스용 Skype 서버.'
ms.openlocfilehash: 03f18a74045c7ea2af4ec3a80b25e65b3c2c5cb6
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58618844"
---
# <a name="manage-pin-policies-for-dial-in-conferencing-in-skype-for-business-server"></a>전화 접속 회의에 대한 PIN 정책 비즈니스용 Skype 서버
 
**요약:** 사용자 계정에서 전화 접속 회의에 대한 PIN 정책을 관리하는 비즈니스용 Skype 서버.
  
비즈니스용 Skype 서버 AD DS(Active Directory 도메인 서비스) 자격 증명이 있는 사용자는 PIN(개인 식별 번호)을 사용하여 인증된 사용자로 전화 접속 회의에 참가할 수 있습니다. PIN 정책은 전화 접속 회의 PIN의 작동 방식에 대한 규칙을 정의합니다.
  
 전체 조직에 동일한 PIN 정책을 사용하려는 경우 전역 PIN 정책을 사용하여 필요할 때 수정할 수 있습니다. 전역 PIN 정책은 포리스트 수준의 전화 접속 회의 PIN에 대한 규칙을 정의합니다. 전역 PIN 정책을 수정할 수는 있지만 삭제할 수는 없습니다.
  
특정 정책을 사이트 또는 특정 사용자 그룹에 적용하려는 경우 새 PIN 정책을 만들 수 있습니다.
  
PIN 정책은 가장 좁은 범위에서 가장 넓은 범위까지 사용자에게 적용됩니다. 사용자에게 사용자 수준 PIN 정책을 할당하는 경우 해당 설정이 우선합니다. 사용자 정책을 할당하지 않는 경우 사이트 수준 PIN 정책이 적용됩니다(있는 경우). 사용자 또는 사이트 정책이 적용되지 않는다면 전역 PIN 정책이 기본 설정을 제공합니다.
  
## <a name="view-information-about-pin-policies"></a>PIN 정책에 대한 정보 보기

PIN 정책에 대한 정보는 제어판을 비즈니스용 Skype 서버 관리 셸을 사용하여 비즈니스용 Skype 서버 있습니다.
  
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-control-panel"></a>제어판을 사용하여 PIN 정책에 대한 비즈니스용 Skype 서버 보기

1.  RTCUniversalServerAdmins 그룹의 구성원(또는 이와 동등한 사용자 권한)의 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 배포한 네트워크의 컴퓨터에 비즈니스용 Skype 서버.
    
2.  제어판을 비즈니스용 Skype 서버 를 니다.
    
3. 왼쪽 탐색 모음에서 **회의** 를 클릭하고 **PIN 정책** 을 클릭합니다.
    
4. PIN 정책 **페이지에서** 보하려는 PIN 정책을 클릭하고 **편집을** 클릭한 다음 자세한 정보 **표시를 클릭합니다.**
    
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-management-shell"></a>관리 셸을 사용하여 PIN 정책에 대한 비즈니스용 Skype 서버 보기

PIN 정책에 대한 정보를 보기 위해 **Get-CsPinPolicy** cmdlet을 사용하세요. 예를 들어 다음 명령은 ID가 site:Redmond인 단일 PIN 정책에 대한 정보를 반환합니다.
  
```PowerShell
Get-CsPinPolicy -Identity "site:Redmond"
```

전체 구문 설명 및 매개 변수 목록을 포함하여 자세한 내용은 [Get-CsPinPolicy 를 참조하십시오.](/powershell/module/skype/get-cspinpolicy?view=skype-ps)
  
## <a name="modify-the-global-pin-policy"></a>전역 PIN 정책 수정

전역 PIN 정책은 제어판을 사용하거나 관리 비즈니스용 Skype 서버 사용하여 수정할 비즈니스용 Skype 서버 있습니다.
  
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-control-panel"></a>제어판을 사용하여 전역 전화 접속 회의 PIN 비즈니스용 Skype 서버 수정

1.  RTCUniversalServerAdmins 그룹의 구성원(또는 이와 동등한 사용자 권한)의 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 배포한 네트워크의 컴퓨터에 비즈니스용 Skype 서버.
    
2.  제어판을 비즈니스용 Skype 서버 를 니다.
    
3. 왼쪽 탐색 모음에서 **회의** 를 클릭하고 **PIN 정책** 을 클릭합니다.
    
4. **PIN 정책** 페이지에서 **전역** 정책을 클릭하고 **편집** 을 클릭한 후에 **자세한 정보 표시** 를 클릭합니다.
    
5. **PIN 정책 편집** 의 **최소 PIN 길이** 에서 허용할 최소 PIN 길이를 입력하거나 선택합니다. 기본 최소 길이는 5자리입니다.
    
6. 사용자가 잠길 때까지의 최대 로그온 시도 횟수를 지정하려면 **최대 로그온 시도 횟수 지정** 확인란을 선택합니다. 이 옵션을 선택하지 않으면 PIN 길이에 따라 최대 로그온 시도 횟수가 자동으로 결정됩니다. 기본적으로 최대 시도 횟수는 자동으로 결정됩니다.
    
7. **최대 로그온 시도 횟수 지정** 확인란을 선택한 경우 **최대 로그온 시도 횟수** 에 허용할 최대 로그온 시도 횟수를 입력하거나 선택합니다.
    
8. PIN이 만료되도록 하려면 **PIN 만료 사용** 확인란을 선택합니다. 이 옵션을 선택하지 않으면 PIN이 만료되지 않습니다. 기본적으로 PIN은 만료되지 않습니다.
    
9. **PIN 만료 사용** 확인란을 선택한 경우 **다음 이후 PIN 만료(일)** 에 PIN이 만료될 때까지의 기간(일)을 입력하거나 선택합니다.
    
10. **PIN 기록 카운트** 에 사용자가 PIN을 다시 사용할 수 있을 때까지 만들어야 하는 PIN의 개수를 입력합니다. 기본적으로 사용자는 PIN을 다시 사용할 수 있습니다.
    
11. PIN에서 연속하는 숫자, 반복되는 숫자 집합 등의 공통 숫자 패턴을 허용하려면 **공통 패턴 허용** 확인란을 선택합니다. 이 옵션을 선택하지 않으면 복잡한 숫자 패턴만 허용됩니다. 기본적으로는 복잡한 숫자 패턴만 허용됩니다.
    
    > [!IMPORTANT]
    > 보안상의 이유로 공통 패턴을 허용하지 않는 것이 좋습니다. 
  
12. **커밋** 을 클릭합니다.
    
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-management-shell"></a>관리 셸을 사용하여 전역 전화 접속 회의 PIN 비즈니스용 Skype 서버 수정

전역 전화 접속 회의 PIN 정책을 수정하려면 **Set-CsPinPolicy** cmdlet을 사용 합니다.
  
다음 명령은 조직에서 사용하도록 구성된 모든 PIN 정책에 대한 MinPasswordLength 값을 변경합니다. 이 작업을 위해 명령은 먼저 매개 변수 없이 **Get-CsPinPolicy** cmdlet을 호출하여 모든 기존 PIN 정책의 컬렉션을 검색합니다. 이 컬렉션은 컬렉션의 각 정책에 대한 MinPasswordLength 속성 값을 수정하는 **Set-CsPinPolicy** cmdlet에 파이프됩니다.
  
```PowerShell
Get-CsPinPolicy | Set-CsPinPolicy -MinPasswordLength 10
```

전체 구문 설명 및 매개 변수 목록을 포함하여 자세한 내용은 [Set-CsPinPolicy를 참조하십시오.](/powershell/module/skype/set-cspinpolicy?view=skype-ps)
  
## <a name="create-a-user-or-site-pin-policy"></a>사용자 또는 사이트 PIN 정책 만들기

제어판 또는 관리 셸을 사용하여 사용자 또는 비즈니스용 Skype 서버 PIN 정책을 만들 비즈니스용 Skype 서버 있습니다.
  
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a>제어판을 사용하여 사용자 또는 사이트 PIN 비즈니스용 Skype 서버 만들기

1. RTCUniversalServerAdmins 그룹의 구성원(또는 이와 동등한 사용자 권한)의 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 배포한 네트워크의 컴퓨터에 비즈니스용 Skype 서버.
    
2.  제어판을 비즈니스용 Skype 서버 를 니다.
    
3. 왼쪽 탐색 모음에서 **회의** 를 클릭하고 **PIN 정책** 을 클릭합니다.
    
4. **PIN 정책** 페이지에서 **새로 만들기** 를 클릭한 다음, 다음 중 하나를 수행합니다.
    
   - 사용자 수준 정책을 만들려면 **사용자 정책** 을 클릭합니다. **새 PIN 정책** 의 **이름** 에 정책에 대해 설명하는 이름을 입력합니다.
    
   - 사이트 수준 정책을 만들려면 **사이트 정책** 을 클릭합니다. **사이트 선택** 검색 필드에 정책을 만들 사이트의 이름 전부 또는 일부를 입력합니다. 사이트 목록에서 원하는 사이트를 클릭한 다음 **확인** 을 클릭합니다.
    
5. **설명** 필드에 PIN 정책에 대한 설명을 입력합니다.
    
6. **최소 PIN 길이** 필드에서 허용할 최소 PIN 길이를 입력하거나 선택합니다. 기본 최소 길이는 5자리입니다.
    
7. 사용자가 잠길 때까지의 최대 로그온 시도 횟수를 지정하려면 **최대 로그온 시도 횟수 지정** 확인란을 선택합니다. 이 옵션을 선택하지 않으면 PIN 길이에 따라 최대 로그온 시도 횟수가 자동으로 결정됩니다. 기본적으로 최대 시도 횟수는 자동으로 결정됩니다.
    
8. **최대 로그온 시도 횟수 지정** 확인란을 선택한 경우 **최대 로그온 시도 횟수** 에 허용할 최대 로그온 시도 횟수를 입력하거나 선택합니다.
    
9. PIN이 만료되도록 하려면 **PIN 만료 사용** 확인란을 선택합니다. 이 옵션을 선택하지 않으면 PIN이 만료되지 않습니다. 기본적으로 PIN은 만료되지 않습니다.
    
10. **PIN 만료 사용** 확인란을 선택한 경우 **다음 이후 PIN 만료(일)** 에 PIN이 만료될 때까지의 기간(일)을 입력하거나 선택합니다.
    
11. **PIN 기록 카운트** 에 사용자가 PIN을 다시 사용할 수 있을 때까지 만들어야 하는 PIN의 개수를 입력합니다. 기본적으로 사용자는 PIN을 다시 사용할 수 있습니다.
    
12. PIN에서 연속하는 숫자, 반복되는 숫자 집합 등의 공통 숫자 패턴을 허용하려면 **공통 패턴 허용** 확인란을 선택합니다. 이 옵션을 선택하지 않으면 복잡한 숫자 패턴만 허용됩니다. 기본적으로는 복잡한 숫자 패턴만 허용됩니다.
    
    > [!IMPORTANT]
    > 보안상의 이유로 공통 패턴을 허용하지 않는 것이 좋습니다. 
  
13. **커밋** 을 클릭합니다.
    
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a>관리 셸을 사용하여 사용자 또는 사이트 PIN 비즈니스용 Skype 서버 만들기

사용자 또는 사이트 PIN 정책을 만들 경우 **New-CsPinPolicy** cmdlet을 사용하세요.
  
다음 명령은 ID가 site:Redmond인 새 PIN 정책을 만듭니다. 이 명령에는 MinPasswordLength 속성을 7로 설정하는 데 사용되는 하나의 선택적 매개 변수인 MinPasswordLength만 포함됩니다. 나머지 모든 정책 속성은 기본값을 사용하여 구성됩니다.
  
```PowerShell
New-CsPinPolicy -Identity "site:Redmond" -MinPasswordLength 7
```

 전체 구문 설명 및 매개 변수 목록을 포함하여 자세한 내용은 [New-CsPinPolicy 를 참조하십시오.](/powershell/module/skype/new-cspinpolicy?view=skype-ps)
  
## <a name="modify-a-user-or-site-pin-policy"></a>사용자 또는 사이트 PIN 정책 수정

제어판을 사용하거나 관리 셸을 사용하여 사용자 또는 비즈니스용 Skype 서버 PIN 정책을 수정할 비즈니스용 Skype 서버 있습니다.
  
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a>제어판을 사용하여 사용자 또는 사이트 PIN 비즈니스용 Skype 서버 수정

1.  RTCUniversalServerAdmins 그룹의 구성원(또는 이와 동등한 사용자 권한)의 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 배포한 네트워크의 컴퓨터에 비즈니스용 Skype 서버.
    
2.  제어판을 비즈니스용 Skype 서버 를 니다.
    
3. 왼쪽 탐색 모음에서 **회의** 를 클릭하고 **PIN 정책** 을 클릭합니다.
    
4. **PIN 정책** 페이지에서 변경할 PIN 정책을 클릭한 다음 **편집**, **자세한 정보 표시** 를 차례로 클릭합니다.
    
5. **PIN 정책 편집** 에서 원하는 정책 설정을 수정합니다(이름은 수정할 수 없음).
    
6. **커밋** 을 클릭합니다.
    
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a>관리 셸을 사용하여 사용자 또는 사이트 PIN 비즈니스용 Skype 서버 수정

전화 접속 회의 PIN 정책을 수정하려면 **Set-CsPinPolicy** cmdlet을 사용 합니다.
  
다음 명령은 Redmond 사이트에 할당된 PIN 정책을 수정합니다. 이 경우 명령은 MinPasswordLength 속성 값을 10으로 변경합니다. 즉, 새 PI에는 10자리 이상의 숫자가 포함되어야 합니다.
  
```PowerShell
Set-CsPinPolicy -Identity site:Redmond -MinPasswordLength 10
```

전체 구문 설명 및 매개 변수 목록을 포함하여 자세한 내용은 [Set-CsPinPolicy를 참조하십시오.](/powershell/module/skype/set-cspinpolicy?view=skype-ps)
  
## <a name="delete-a-user-or-site-pin-policy"></a>사용자 또는 사이트 PIN 정책 삭제

사용자 또는 사이트 PIN 정책은 제어판을 비즈니스용 Skype 서버 관리 셸을 사용하여 삭제할 비즈니스용 Skype 서버 있습니다.
  
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a>제어판을 사용하여 사용자 또는 사이트 PIN 비즈니스용 Skype 서버 삭제

1.  RTCUniversalServerAdmins 그룹의 구성원(또는 이와 동등한 사용자 권한)의 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 배포한 네트워크의 컴퓨터에 비즈니스용 Skype 서버.
    
2.  제어판을 비즈니스용 Skype 서버 를 니다.
    
3. 왼쪽 탐색 모음에서 **회의** 를 클릭하고 **PIN 정책** 을 클릭합니다.
    
4. **PIN** 정책 페이지에서 변경할 PIN 정책을 클릭하고 **편집,** 삭제를 **클릭합니다.**
    
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a>관리 셸을 사용하여 사용자 또는 사이트 PIN 비즈니스용 Skype 서버 삭제

사용자 또는 사이트 PIN 정책을 삭제하려면 **Remove-CsPinPolicy** cmdlet을 사용하세요.
  
다음 명령은 사이트 범위에서 구성된 모든 PIN 정책을 제거합니다. 이 작업을 위해 **Get-CsPinPolicy** cmdlet과 Filter 매개 변수를 함께 사용하여 ID가 "site:" 문자로 시작하는 모든 정책 컬렉션을 반환합니다. 이 컬렉션은 컬렉션의 각 정책을 삭제하는 **Remove-CsPinPolicy** cmdlet에 파이프됩니다.
  
```PowerShell
Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
```

전체 구문 설명 및 매개 변수 목록을 포함하여 자세한 내용은 [Remove-CsPinPolicy를 참조하십시오.](/powershell/module/skype/remove-cspinpolicy?view=skype-ps)
