---
title: 비즈니스용 Skype 서버에서 전화 접속 회의를 위한 PIN 정책 관리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 459e80bf-5791-49f8-878d-4a5178b3a210
description: '요약: 비즈니스용 Skype 서버에서 전화 접속 회의를 위한 PIN 정책을 관리 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 567d57edc4db5bae87653d8d3e11e44054efc0cd
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818479"
---
# <a name="manage-pin-policies-for-dial-in-conferencing-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 전화 접속 회의를 위한 PIN 정책 관리
 
**요약:** 비즈니스용 Skype 서버에서 전화 접속 회의를 위한 PIN 정책을 관리 하는 방법에 대해 알아봅니다.
  
조직의 AD DS (Active Directory 도메인 서비스) 자격 증명이 있는 비즈니스용 Skype 서버 사용자는 PIN (개인 식별 번호)을 사용 하 여 인증 된 사용자로 전화 접속 회의에 참가할 수 있습니다. 고정 정책 전화 접속 회의 핀이 작동 하는 방법에 대 한 규칙을 정의 합니다.
  
 전체 조직에 동일한 PIN 정책을 사용 하려는 경우 전역 PIN 정책을 사용 하 고 필요에 따라 수정할 수 있습니다. 글로벌 PIN 정책은 포리스트 수준의 전화 접속 회의 핀에 대 한 규칙을 정의 합니다. 글로벌 PIN 정책은 수정할 수 있지만 삭제할 수는 없습니다.
  
특정 정책을 사이트 또는 특정 사용자 그룹에 적용 하려는 경우 새 PIN 정책을 만들 수 있습니다.
  
PIN 정책은 가장 좁은 범위의 사용자에 게 적용 됩니다. 사용자 수준 PIN 정책을 사용자에 게 할당 하면 해당 설정이 우선적으로 적용 됩니다. 사용자 정책을 할당 하지 않으면 사이트 수준 PIN 정책이 있는 경우 적용 됩니다. 사용자 또는 사이트 정책이 적용 되지 않으면 글로벌 PIN 정책이 기본 설정을 제공 합니다.
  
## <a name="view-information-about-pin-policies"></a>고정 정책에 대 한 정보 보기

비즈니스용 Skype Server 제어판을 사용 하거나 비즈니스용 Skype Server Management Shell을 사용 하 여 PIN 정책에 대 한 정보를 볼 수 있습니다.
  
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-control-panel"></a>비즈니스용 Skype Server 제어판을 사용 하 여 PIN 정책에 대 한 정보 보기

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 비즈니스용 Skype 서버를 배포한 네트워크의 컴퓨터에 로그온 합니다. .
    
2.  비즈니스용 Skype Server 제어판을 엽니다.
    
3. 왼쪽 탐색 모음에서 **회의**를 클릭 한 다음 **고정 정책을**클릭 합니다.
    
4. **고정 정책** 페이지에서 보려는 pin 정책을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.
    
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-management-shell"></a>비즈니스용 Skype Server Management Shell을 사용 하 여 PIN 정책에 대 한 정보 보기

핀 정책에 대 한 정보를 보려면 **CsPinPolicy** cmdlet을 사용 합니다. 예를 들어 다음 명령은 Id 사이트: Redmond: 인 단일 PIN 정책에 대 한 정보를 반환 합니다.
  
```PowerShell
Get-CsPinPolicy -Identity "site:Redmond"
```

전체 구문 설명과 매개 변수 목록을 비롯 한 자세한 내용은 [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps)을 참조 하세요.
  
## <a name="modify-the-global-pin-policy"></a>글로벌 PIN 정책 수정

비즈니스용 Skype Server 제어판을 사용 하거나 비즈니스용 Skype Server Management Shell을 사용 하 여 글로벌 PIN 정책을 수정할 수 있습니다.
  
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-control-panel"></a>비즈니스용 Skype Server 제어판을 사용 하 여 글로벌 전화 접속 회의 PIN 정책 수정

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 비즈니스용 Skype 서버를 배포한 네트워크의 컴퓨터에 로그온 합니다. .
    
2.  비즈니스용 Skype Server 제어판을 엽니다.
    
3. 왼쪽 탐색 모음에서 **회의**를 클릭 한 다음 **고정 정책을**클릭 합니다.
    
4. **고정 정책** 페이지에서 **전역** 정책을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.
    
5. **Pin 편집 정책**에서 **최소 pin 길이**에 허용 하려는 최소 pin 길이를 입력 하거나 선택 합니다. 기본 최소 길이는 다섯 자리입니다.
    
6. 사용자가 잠길 때까지 허용 되는 최대 로그온 시도 횟수를 지정할 수 있으려면 **최대 로그온 시도 수 지정** 확인란을 선택 합니다. 이 옵션을 선택 하지 않으면 허용 되는 최대 시도 수는 PIN 길이에 따라 자동으로 결정 됩니다. 기본적으로 최대 시도 횟수는 자동으로 결정 됩니다.
    
7. 최대 로그온 시도 **횟수 지정** 확인란을 선택한 경우 **최대 로그온 시도**에서 허용 하려는 최대 로그온 시도 횟수를 입력 하거나 선택 합니다.
    
8. 핀이 만료 되 게 하려면 **PIN 만료 사용** 확인란을 선택 합니다. 이 옵션을 선택 하지 않으면 Pin이 만료 되지 않습니다. 기본적으로 Pin은 만료 되지 않습니다.
    
9. **Pin 만료 사용** 확인란을 선택한 경우 **pin이 (일) 후에 만료**되는 경우 해당 pin이 만료 되는 일 수를 입력 하거나 선택 합니다.
    
10. **Pin 기록 개수**에 사용자가 PIN을 다시 사용할 수 있으려면 먼저 사용자가 만들어야 하는 pin의 수를 입력 합니다. 기본적으로 사용자는 Pin을 다시 사용할 수 있습니다.
    
11. 일련 번호와 반복 되는 숫자 집합 등의 일반 숫자 패턴을 허용 하려면 **일반 패턴 허용** 확인란을 선택 합니다. 이 옵션을 선택 하지 않으면 복잡 한 자릿수의 숫자만 사용할 수 있습니다. 기본적으로 복잡 한 자릿수 패턴만 사용할 수 있습니다.
    
    > [!IMPORTANT]
    > 보안상의 이유로, Microsoft에서는 일반적인 패턴을 허용 하지 않는 것이 좋습니다. 
  
12. **커밋**을 클릭합니다.
    
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-management-shell"></a>비즈니스용 Skype Server Management Shell을 사용 하 여 전역 전화 접속 회의 PIN 정책 수정

전역 전화 접속 회의 PIN 정책을 수정 하려면 **CsPinPolicy** cmdlet을 사용 합니다.
  
다음 명령은 조직에서 사용 하도록 구성 된 모든 PIN 정책에 대 한 MinPasswordLength 값을 변경 합니다. 이렇게 하려면 명령은 먼저 모든 기존 PIN 정책의 컬렉션을 검색 하기 위해 매개 변수 없이 **CsPinPolicy** cmdlet을 호출 합니다. 그런 다음 해당 컬렉션은 컬렉션의 각 정책에 대 한 MinPasswordLength 속성 값을 수정 하는 **Set CsPinPolicy** cmdlet으로 파이프 됩니다.
  
```PowerShell
Get-CsPinPolicy | Set-CsPinPolicy -MinPasswordLength 10
```

전체 구문 설명과 매개 변수 목록을 비롯 한 자세한 내용은 [Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps)를 참조 하세요.
  
## <a name="create-a-user-or-site-pin-policy"></a>사용자 또는 사이트 PIN 정책 만들기

비즈니스용 Skype Server 제어판을 사용 하거나 비즈니스용 Skype Server Management Shell을 사용 하 여 사용자 또는 사이트 PIN 정책을 만들 수 있습니다.
  
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a>비즈니스용 Skype Server 제어판을 사용 하 여 사용자 또는 사이트 PIN 정책 만들기

1. RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 비즈니스용 Skype 서버를 배포한 네트워크의 컴퓨터에 로그온 합니다. .
    
2.  비즈니스용 Skype Server 제어판을 엽니다.
    
3. 왼쪽 탐색 모음에서 **회의**를 클릭 한 다음 **고정 정책을**클릭 합니다.
    
4. **고정 정책** 페이지에서 **새로 만들기**를 클릭 하 고 다음 중 하나를 수행 합니다.
    
   - 사용자 수준 정책을 만들려면 **사용자 정책을**클릭 합니다. **새 PIN 정책의** **이름**에 정책을 설명 하는 이름을 입력 합니다.
    
   - 사이트 수준 정책을 만들려면 **사이트 정책을**클릭 합니다. 사이트 검색 **선택** 필드에 정책을 만들려는 사이트 이름의 전부 또는 일부를 입력 합니다. 사이트 목록에서 원하는 사이트를 클릭 한 다음 **확인**을 클릭 합니다.
    
5. **설명** 필드에 고정 정책에 대 한 설명을 입력 합니다.
    
6. **최소 pin 길이** 필드에 허용 하려는 최소 pin 길이를 입력 하거나 선택 합니다. 기본 최소 길이는 다섯 자리입니다.
    
7. 사용자가 잠길 때까지 허용 되는 최대 로그온 시도 횟수를 지정할 수 있으려면 **최대 로그온 시도 수 지정** 확인란을 선택 합니다. 이 옵션을 선택 하지 않으면 허용 되는 최대 시도 수는 PIN 길이에 따라 자동으로 결정 됩니다. 기본적으로 최대 시도 횟수는 자동으로 결정 됩니다.
    
8. 최대 로그온 시도 **횟수 지정** 확인란을 선택한 경우 **최대 로그온 시도**에서 허용 하려는 최대 로그온 시도 횟수를 입력 하거나 선택 합니다.
    
9. 핀이 만료 되 게 하려면 **PIN 만료 사용** 확인란을 선택 합니다. 이 옵션을 선택 하지 않으면 Pin이 만료 되지 않습니다. 기본적으로 Pin은 만료 되지 않습니다.
    
10. **Pin 만료 사용** 확인란을 선택한 경우 **pin이 (일) 후에 만료**되는 경우 해당 pin이 만료 되는 일 수를 입력 하거나 선택 합니다.
    
11. **Pin 기록 개수**에 사용자가 PIN을 다시 사용할 수 있으려면 먼저 사용자가 만들어야 하는 pin의 수를 입력 합니다. 기본적으로 사용자는 Pin을 다시 사용할 수 있습니다.
    
12. 일련 번호와 반복 되는 숫자 집합 등의 일반 숫자 패턴을 허용 하려면 **일반 패턴 허용** 확인란을 선택 합니다. 이 옵션을 선택 하지 않으면 복잡 한 자릿수의 숫자만 사용할 수 있습니다. 기본적으로 복잡 한 자릿수 패턴만 사용할 수 있습니다.
    
    > [!IMPORTANT]
    > 보안상의 이유로, Microsoft에서는 일반적인 패턴을 허용 하지 않는 것이 좋습니다. 
  
13. **커밋**을 클릭합니다.
    
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a>비즈니스용 Skype Server Management Shell을 사용 하 여 사용자 또는 사이트 PIN 정책 만들기

사용자 또는 사이트 PIN 정책을 만들려면 **새 CsPinPolicy** cmdlet을 사용 합니다.
  
다음 명령은 Id 사이트: Redmond를 사용 하 여 새 PIN 정책을 만듭니다. 이 명령에는 MinPasswordLength 속성을 7로 설정 하는 데 사용 되는 선택적 매개 변수인 MinPasswordLength가 포함 되어 있습니다. 나머지 모든 정책 속성은 기본 값을 사용 하 여 구성 됩니다.
  
```PowerShell
New-CsPinPolicy -Identity "site:Redmond" -MinPasswordLength 7
```

 전체 구문 설명과 매개 변수 목록을 비롯 한 자세한 내용은 [New-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps)를 참조 하세요.
  
## <a name="modify-a-user-or-site-pin-policy"></a>사용자 또는 사이트 PIN 정책 수정

비즈니스용 Skype Server 제어판을 사용 하거나 비즈니스용 Skype Server Management Shell을 사용 하 여 사용자 또는 사이트 PIN 정책을 수정할 수 있습니다.
  
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a>비즈니스용 Skype Server 제어판을 사용 하 여 사용자 또는 사이트 PIN 정책 수정

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 비즈니스용 Skype 서버를 배포한 네트워크의 컴퓨터에 로그온 합니다. .
    
2.  비즈니스용 Skype Server 제어판을 엽니다.
    
3. 왼쪽 탐색 모음에서 **회의**를 클릭 한 다음 **고정 정책을**클릭 합니다.
    
4. **고정 정책** 페이지에서 변경 하려는 pin 정책을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.
    
5. **PIN 정책 편집**에서 정책 설정을 수정 합니다 (수정할 수 없는 정책 이름을 제외한).
    
6. **커밋**을 클릭합니다.
    
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a>비즈니스용 Skype Server Management Shell을 사용 하 여 사용자 또는 사이트 PIN 정책 수정

전화 접속 회의 PIN 정책을 수정 하려면 **Set-CsPinPolicy** cmdlet을 사용 합니다.
  
다음 명령은 Redmond 사이트에 할당 된 PIN 정책을 수정 합니다. 이 경우 명령은 MinPasswordLength 속성 값을 10으로 변경 합니다. 즉, 새 Pin에는 최소 10 자리 숫자를 포함 해야 합니다.
  
```PowerShell
Set-CsPinPolicy -Identity site:Redmond -MinPasswordLength 10
```

전체 구문 설명과 매개 변수 목록을 비롯 한 자세한 내용은 [Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps)를 참조 하세요.
  
## <a name="delete-a-user-or-site-pin-policy"></a>사용자 또는 사이트 PIN 정책 삭제

비즈니스용 Skype Server 제어판을 사용 하거나 비즈니스용 Skype Server Management Shell을 사용 하 여 사용자 또는 사이트 PIN 정책을 삭제할 수 있습니다.
  
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a>비즈니스용 Skype Server 제어판을 사용 하 여 사용자 또는 사이트 PIN 정책 삭제

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 비즈니스용 Skype 서버를 배포한 네트워크의 컴퓨터에 로그온 합니다. .
    
2.  비즈니스용 Skype Server 제어판을 엽니다.
    
3. 왼쪽 탐색 모음에서 **회의**를 클릭 한 다음 **고정 정책을**클릭 합니다.
    
4. **고정 정책** 페이지에서 변경 하려는 pin 정책을 클릭 하 고 **편집**을 클릭 한 다음 **삭제**를 클릭 합니다.
    
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a>비즈니스용 Skype Server Management Shell을 사용 하 여 사용자 또는 사이트 PIN 정책 삭제

사용자 또는 사이트 PIN 정책을 삭제 하려면 **CsPinPolicy** cmdlet을 사용 합니다.
  
다음 명령을 사용 하 여 사이트 범위에서 구성 된 PIN 정책을 모두 제거 합니다. 이렇게 하려면 Filter 매개 변수와 함께 **CsPinPolicy** cmdlet을 사용 하 여 id가 "site:" 문자로 시작 하는 모든 정책의 컬렉션을 반환 합니다. 그런 다음이 컬렉션은 컬렉션의 각 정책을 삭제 하는 **CsPinPolicy** cmdlet으로 파이프 됩니다.
  
```PowerShell
Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
```

전체 구문 설명과 매개 변수 목록을 비롯 한 자세한 내용은 [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps)를 참조 하세요.
  

