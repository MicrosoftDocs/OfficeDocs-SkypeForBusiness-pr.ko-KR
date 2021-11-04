---
title: 2013에서 회의 정책 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 497e6ca0-7a49-4f3e-9804-14414cf87b57
description: '요약: 2013에서 회의 정책을 삭제하는 비즈니스용 Skype 서버.'
ms.openlocfilehash: d77910cb5fe39dcb47564b1b456a314ae03584a5
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60773698"
---
# <a name="delete-conferencing-policies-in-skype-for-business-server"></a>2013에서 회의 정책 비즈니스용 Skype 서버
 
**요약:** 2013에서 회의 정책을 삭제하는 비즈니스용 Skype 서버.
  
회의 정책은 제어판 또는 비즈니스용 Skype 서버 관리 셸을 사용하여 삭제할 비즈니스용 Skype 서버 있습니다.
  
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>제어판을 사용하여 회의 비즈니스용 Skype 서버 삭제

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.
    
2.  제어판을 비즈니스용 Skype 서버 를 니다.
    
3. 왼쪽 탐색 모음에서 회의 를 클릭한 다음 회의 정책을 **클릭합니다.**
    
4. 회의 정책 목록에서 삭제할 사이트 또는 사용자 정책을 클릭하고 편집, 삭제를 **클릭합니다.** 
    
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>비즈니스용 Skype 서버 관리 셸을 사용하여 회의 정책 삭제

회의 정책을 삭제하려면 **Remove-CsConferencingPolicy** cmdlet을 사용 합니다.
  
다음 명령은 ID RedmondConferencingPolicy가 포함된 회의 정책을 제거합니다.
  
```PowerShell
Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"
```

다음 명령은 외부 사용자가 회의를 기록할 수 있도록 허용하는 모든 회의 정책을 삭제합니다.
  
```PowerShell
Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy
```

전체 구문과 매개 변수 목록을 비롯한 자세한 내용은 [Remove-CsConferencingPolicy 를 참조하십시오.](/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps)
