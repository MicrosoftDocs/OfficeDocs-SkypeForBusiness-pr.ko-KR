---
title: 비즈니스용 Skype 서버에서 모임 구성 설정 수정
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 11d1f9ac-0029-429b-be2b-d7591abfc192
description: '요약: 비즈니스용 Skype 서버에서 모임 구성 설정을 수정하는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: 80ba12266ebc45fdae3256f5238ecf18415734c8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827998"
---
# <a name="modify-meeting-configuration-settings-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 모임 구성 설정 수정
 
**요약:** 비즈니스용 Skype 서버에서 모임 구성 설정을 수정하는 방법을 확인합니다.
  
비즈니스용 Skype 서버 제어판 또는 비즈니스용 Skype 서버 관리 셸을 사용하여 모임 구성 설정을 수정할 수 있습니다.
  
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>비즈니스용 Skype 서버 제어판을 사용하여 모임 구성 설정 수정

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.
    
2.  비즈니스용 Skype 서버 제어판을 니다.
    
3. 왼쪽 탐색 모음에서 회의를 클릭한 다음 모임 **구성을 클릭합니다.**
    
4. 모임 구성 목록에서 변경할 구성을 클릭하고 편집을 **클릭한** 다음 세부 정보 **표시를 클릭합니다.**
    
5. 모임 **구성 편집에서** 수정할 수 없는 구성 이름을 제외하고 구성 설정을 수정합니다.
    
6. **커밋** 을 클릭합니다.
    
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>비즈니스용 Skype 서버 관리 셸을 사용하여 모임 구성 설정 수정

모임 구성 설정을 수정하려면 **Set-CsMeetingConfiguration** cmdlet을 사용합니다.
  
다음 예제에 표시된 명령은 Redmond 사이트(-Identity site:Redmond)에 할당된 모임 구성 설정을 수정합니다. 이 경우 DesignateAsPresenter 속성 값은 Everyone로 설정됩니다.
  
```PowerShell
Set-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

전체 매개 변수 목록을 포함하여 자세한 내용은 [Set-CsMeetingConfiguration을 참조하십시오.](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps)
  

