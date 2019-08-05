---
title: 비즈니스용 Skype 서버에서 모임 구성 설정 수정
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11d1f9ac-0029-429b-be2b-d7591abfc192
description: '요약: 비즈니스용 Skype 서버에서 모임 구성 설정을 수정 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 6e2566a5bc48e081c1912753586aef2213e1c727
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188949"
---
# <a name="modify-meeting-configuration-settings-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 모임 구성 설정 수정
 
**요약:** 비즈니스용 Skype 서버에서 모임 구성 설정을 수정 하는 방법에 대해 알아봅니다.
  
비즈니스용 Skype Server 제어판을 사용 하거나 비즈니스용 Skype Server Management Shell을 사용 하 여 모임 구성 설정을 수정할 수 있습니다.
  
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>비즈니스용 Skype Server 제어판을 사용 하 여 모임 구성 설정 수정

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.
    
2.  비즈니스용 Skype Server 제어판을 엽니다.
    
3. 왼쪽 탐색 모음에서 **회의**를 클릭 한 다음 **모임 구성을**클릭 합니다.
    
4. 모임 구성 목록에서 변경 하려는 구성을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.
    
5. **모임 구성 편집**에서 수정할 수 없는 구성 이름을 제외한 모든 구성 설정을 수정 합니다.
    
6. **커밋**을 클릭합니다.
    
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>비즈니스용 Skype Server Management Shell을 사용 하 여 모임 구성 설정 수정

모임 구성 설정을 수정 하려면 **Set-CsMeetingConfiguration** cmdlet을 사용 합니다.
  
다음 예제에 표시 된 명령은 Redmond 사이트 (-Id 사이트: Redmond)에 할당 된 모임 구성 설정을 수정 합니다. 이 경우 DesignateAsPresenter 속성의 값은 모든 사용자로 설정 됩니다.
  
```
Set-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

전체 매개 변수 목록을 비롯 한 자세한 내용은 [Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps)를 참조 하세요.
  

