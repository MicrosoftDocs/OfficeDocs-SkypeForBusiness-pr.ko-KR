---
title: 전화 접속 회의를 사용하도록 설정하거나 사용하지 않도록 비즈니스용 Skype 서버
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: c1f7cf91-8434-42ec-b09d-7d9d01e0b357
description: '요약: 제어판 또는 관리 셸을 사용하여 제어판에서 전화 접속 회의를 사용하도록 설정하거나 사용하지 않도록 설정하는 비즈니스용 Skype 서버.'
---

# <a name="enable-or-disable-dial-in-conferencing-in-skype-for-business-server"></a>전화 접속 회의를 사용하도록 설정하거나 사용하지 않도록 비즈니스용 Skype 서버
 
**요약:** 제어판 또는 관리 셸을 사용하여 제어판에서 전화 접속 회의를 사용하도록 설정하거나 사용하지 않도록 설정하는 비즈니스용 Skype 서버.
  
비즈니스용 Skype 서버 관리 셸을 사용하여 전화 접속 회의를 사용하도록 설정할 비즈니스용 Skype 서버 있습니다.
  
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a>제어판을 사용하여 전화 접속 회의를 비즈니스용 Skype 서버 사용

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.
    
2.  제어판을 비즈니스용 Skype 서버 를 니다.
    
3. 왼쪽 탐색 모음에서 회의를 **클릭한** 다음 회의 정책을 **클릭합니다**.
    
4. 회의 정책 목록에서 전화 접속 회의를 사용하도록 설정하려는 정책을 선택하고 **편집** 을 클릭한 다음 **세부 정보 표시** 를 클릭합니다. 
    
5. 사용자가 전화 접속을 사용해서 모임에 참가할 수 있도록 허용하려면 **PSTN 전화 접속 회의 사용** 확인란을 선택합니다. 기본적으로 사용자는 PSTN(공중 전화망)을 사용하여 모임에 전화 접속할 수 있습니다.
    
6. **커밋** 을 클릭합니다. 
    
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a>관리 셸을 사용하여 전화 접속 회의를 비즈니스용 Skype 서버 사용 안 하도록 설정

전화 접속 회의를 사용하도록 설정하거나 사용하지 않도록 설정하려면 **다음과 같이 EnableDialInConferencing 매개 변수와 함께 Set-CsConferencingPolicy** cmdlet을 사용합니다.
  
```PowerShell
Set-CsConferencingPolicy  [-EnableDialInConferencing <$true | $false>] 
```

자세한 내용은 [Set-CsConferencingPolicy를 참조하십시오](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
