---
title: 비즈니스용 Skype 서버에서 모임 구성 설정 삭제
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ebafb86-13b9-468e-beda-f85f6786da85
description: '요약: 비즈니스용 Skype 서버에서 모임 구성 설정을 삭제 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: a728f1c1de3470cf505163c5cb25996c190e9026
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197718"
---
# <a name="delete-meeting-configuration-settings-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 모임 구성 설정 삭제
 
**요약:** 비즈니스용 Skype 서버에서 모임 구성 설정을 삭제 하는 방법에 대해 알아봅니다.
  
Skype for Business Server 제어판을 사용 하거나 비즈니스용 Skype Server Management Shell을 사용 하 여 모임 구성 설정을 삭제할 수 있습니다.
  
사이트 또는 사용자 구성을 삭제할 수 있지만 전역 구성은 삭제할 수 없습니다. 전역 구성을 삭제 하려고 하면 자동으로 기본 값으로 다시 설정 됩니다.
  
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>비즈니스용 Skype 서버 제어판을 사용 하 여 모임 구성 설정 삭제

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.
    
2.  비즈니스용 Skype Server 제어판을 엽니다.
    
3. 왼쪽 탐색 모음에서 **회의**를 클릭 한 다음 **모임 구성을**클릭 합니다.
    
4. 모임 구성 목록에서 삭제 하려는 사이트 또는 풀 구성을 클릭 하 고 **편집**을 클릭 한 다음 **삭제**를 클릭 합니다.
    
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>비즈니스용 Skype Server Management Shell을 사용 하 여 모임 구성 설정 삭제

모임 설정을 삭제 하려면 **Remove-CsMeetingConfiguration** cmdlet을 사용 합니다.
  
다음 명령은 Redmond 사이트에 적용 된 모임 구성 설정을 제거 합니다.
  
```
Remove-CsMeetingConfiguration -Identity "site:Redmond"
```

다음 명령을 실행 하면 사이트 범위에 적용 된 모든 모임 구성 설정이 제거 됩니다.
  
```
Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration
```

전체 매개 변수 목록을 비롯 한 자세한 내용은 [제거-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps)를 참조 하세요.
  

