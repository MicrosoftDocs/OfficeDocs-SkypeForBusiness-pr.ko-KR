---
title: 비즈니스용 Skype 서버에서 회의 정책 삭제
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
ms.assetid: 497e6ca0-7a49-4f3e-9804-14414cf87b57
description: '요약: 비즈니스용 Skype 서버에서 회의 정책을 삭제하는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: eedb0b3676f0cc046e6096dca2cb1ec5ced5d6ec
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828198"
---
# <a name="delete-conferencing-policies-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 회의 정책 삭제
 
**요약:** 비즈니스용 Skype 서버에서 회의 정책을 삭제하는 방법에 대해 자세히 알아보습니다.
  
비즈니스용 Skype 서버 제어판 또는 비즈니스용 Skype 서버 관리 셸을 사용하여 회의 정책을 삭제할 수 있습니다.
  
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>비즈니스용 Skype 서버 제어판을 사용하여 회의 정책 삭제

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.
    
2.  비즈니스용 Skype 서버 제어판을 니다.
    
3. 왼쪽 탐색 모음에서 회의를 클릭한 다음 회의 **정책을 클릭합니다.**
    
4. 회의 정책 목록에서 삭제할 사이트 또는 사용자 정책을 클릭하고 **편집을** 클릭한 다음 삭제를 **클릭합니다.**
    
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>비즈니스용 Skype 서버 관리 셸을 사용하여 회의 정책 삭제

회의 정책을 삭제하려면 **Remove-CsConferencingPolicy** cmdlet을 사용 합니다.
  
다음 명령은 ID RedmondConferencingPolicy가 포함된 회의 정책을 제거합니다.
  
```PowerShell
Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"
```

다음 명령은 외부 사용자가 회의를 녹음/녹화할 수 있도록 허용하는 모든 회의 정책을 삭제합니다.
  
```PowerShell
Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy
```

전체 구문과 매개 변수 목록을 비롯한 자세한 내용은 [Remove-CsConferencingPolicy를 참조하십시오.](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps)
  

