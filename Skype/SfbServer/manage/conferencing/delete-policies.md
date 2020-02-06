---
title: 비즈니스용 Skype 서버에서 회의 정책 삭제
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
ms.assetid: 497e6ca0-7a49-4f3e-9804-14414cf87b57
description: '요약: 비즈니스용 Skype 서버에서 회의 정책을 삭제 하는 방법에 대해 알아보세요.'
ms.openlocfilehash: 3fe5b8c2bb12f48cb6e904df2fe43c6c8a01e3f6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818599"
---
# <a name="delete-conferencing-policies-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 회의 정책 삭제
 
**요약:** 비즈니스용 Skype 서버에서 회의 정책을 삭제 하는 방법에 대해 알아봅니다.
  
Skype for Business Server 제어판을 사용 하거나 비즈니스용 Skype 서버 관리 셸을 사용 하 여 회의 정책을 삭제할 수 있습니다.
  
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>비즈니스용 Skype 서버 제어판을 사용 하 여 회의 정책 삭제

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.
    
2.  비즈니스용 Skype Server 제어판을 엽니다.
    
3. 왼쪽 탐색 모음에서 **회의**를 클릭 한 다음 **회의 정책을**클릭 합니다.
    
4. 회의 정책 목록에서 삭제 하려는 사이트 또는 사용자 정책을 클릭 하 고 **편집**을 클릭 한 다음 **삭제**를 클릭 합니다.
    
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>비즈니스용 Skype Server Management Shell을 사용 하 여 회의 정책 삭제

회의 정책을 삭제 하려면 **Remove-CsConferencingPolicy** cmdlet을 사용 합니다.
  
다음 명령은 Id RedmondConferencingPolicy를 사용 하 여 회의 정책을 제거 합니다.
  
```PowerShell
Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"
```

다음 명령은 외부 사용자가 회의를 녹화할 수 있도록 하는 회의 정책을 삭제 합니다.
  
```PowerShell
Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy
```

전체 구문 및 매개 변수 목록을 비롯 한 자세한 내용은 [Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps)를 참조 하세요.
  

