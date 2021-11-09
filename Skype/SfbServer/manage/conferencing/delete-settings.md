---
title: 모임 구성 설정 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 8ebafb86-13b9-468e-beda-f85f6786da85
description: '요약: 사용자 계정에서 모임 구성 설정을 삭제하는 비즈니스용 Skype 서버.'
ms.openlocfilehash: 95eda4da393f1eb677fc331ffb824e6222e35113
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60830902"
---
# <a name="delete-meeting-configuration-settings-in-skype-for-business-server"></a>모임 구성 설정 비즈니스용 Skype 서버
 
**요약:** 사용자 계정에서 모임 구성 설정을 삭제하는 비즈니스용 Skype 서버.
  
모임 구성 설정은 비즈니스용 Skype 서버 관리 셸을 사용하여 삭제할 비즈니스용 Skype 서버 있습니다.
  
사이트 또는 사용자 구성을 삭제할 수는 있지만 전역 구성은 삭제할 수 없습니다. 전역 구성을 삭제하려고 시도하면 자동으로 기본값으로 다시 설정됩니다.
  
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>제어판을 사용하여 모임 구성 비즈니스용 Skype 서버 삭제

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.
    
2.  제어판을 비즈니스용 Skype 서버 를 니다.
    
3. 왼쪽 탐색 모음에서 회의 를 클릭한 다음 모임 구성 **을 클릭합니다.**
    
4. 모임 구성 목록에서 삭제할 사이트 또는 풀 구성을 클릭하고 **편집,** 삭제를 **클릭합니다.**
    
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>관리 셸을 사용하여 모임 비즈니스용 Skype 서버 삭제

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
