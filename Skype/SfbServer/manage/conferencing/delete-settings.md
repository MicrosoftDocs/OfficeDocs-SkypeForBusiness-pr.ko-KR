---
title: 비즈니스용 Skype 서버에서 모임 구성 설정 삭제
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
ms.assetid: 8ebafb86-13b9-468e-beda-f85f6786da85
description: '요약: 비즈니스용 Skype 서버에서 모임 구성 설정을 삭제하는 방법을 확인합니다.'
ms.openlocfilehash: b0c739f0149b4e28ca23df1437caab0505e1118d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119497"
---
# <a name="delete-meeting-configuration-settings-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 모임 구성 설정 삭제
 
**요약:** 비즈니스용 Skype 서버에서 모임 구성 설정을 삭제하는 방법을 확인합니다.
  
비즈니스용 Skype 서버 제어판 또는 비즈니스용 Skype 서버 관리 셸을 사용하여 모임 구성 설정을 삭제할 수 있습니다.
  
사이트 또는 사용자 구성을 삭제할 수는 있지만 전역 구성은 삭제할 수 없습니다. 전역 구성을 삭제하려고 시도하면 자동으로 기본값으로 다시 설정됩니다.
  
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>비즈니스용 Skype 서버 제어판을 사용하여 모임 구성 설정 삭제

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.
    
2.  비즈니스용 Skype 서버 제어판을 니다.
    
3. 왼쪽 탐색 모음에서 회의 를 클릭한 다음 모임 구성 **을 클릭합니다.**
    
4. 모임 구성 목록에서 삭제할 사이트 또는 풀 구성을 클릭하고 **편집,** 삭제를 **클릭합니다.**
    
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>비즈니스용 Skype 서버 관리 셸을 사용하여 모임 구성 설정 삭제

모임 설정을 삭제하려면 **Remove-CsMeetingConfiguration** cmdlet을 사용합니다.
  
다음 명령은 Redmond 사이트에 적용된 모임 구성 설정을 제거합니다.
  
```PowerShell
Remove-CsMeetingConfiguration -Identity "site:Redmond"
```

다음 명령은 사이트 범위에 적용된 모든 모임 구성 설정을 제거합니다.
  
```PowerShell
Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration
```

전체 매개 변수 목록을 포함하여 자세한 내용은 [Remove-CsMeetingConfiguration을 참조하십시오.](/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps)
