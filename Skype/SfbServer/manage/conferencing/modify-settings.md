---
title: 모임 구성 설정 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 11d1f9ac-0029-429b-be2b-d7591abfc192
description: '요약: 이 문서에서 모임 구성 설정을 수정하는 비즈니스용 Skype 서버.'
ms.openlocfilehash: c3da96738e4902be94ed1efc3b5037b105c0771f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58587074"
---
# <a name="modify-meeting-configuration-settings-in-skype-for-business-server"></a>모임 구성 설정 비즈니스용 Skype 서버
 
**요약:** 모임 구성 설정을 수정하는 방법을 비즈니스용 Skype 서버.
  
모임 구성 설정은 제어판을 사용하거나 비즈니스용 Skype 서버 관리 셸을 사용하여 수정할 비즈니스용 Skype 서버 있습니다.
  
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>제어판을 사용하여 모임 구성 비즈니스용 Skype 서버 수정

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.
    
2.  제어판을 비즈니스용 Skype 서버 를 니다.
    
3. 왼쪽 탐색 모음에서 회의 를 클릭한 다음 모임 구성 **을 클릭합니다.**
    
4. 모임 구성 목록에서 변경할 구성을 클릭하고 편집을 **클릭한** 다음 자세한 정보 **표시를 클릭합니다.**
    
5. 모임 **구성 편집에서** 수정할 수 없는 구성 이름을 제외하고 모든 구성 설정을 수정합니다.
    
6. **커밋** 을 클릭합니다.
    
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>관리 셸을 사용하여 모임 구성 비즈니스용 Skype 서버 수정

모임 구성 설정을 수정하려면 **Set-CsMeetingConfiguration** cmdlet을 사용합니다.
  
다음 예제에 표시된 명령은 Redmond 사이트(-Identity site:Redmond)에 할당된 모임 구성 설정을 수정합니다. 이 경우 DesignateAsPresenter 속성 값은 Everyone로 설정됩니다.
  
```PowerShell
Set-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

전체 매개 변수 목록을 포함하여 자세한 내용은 [Set-CsMeetingConfiguration을 참조하십시오.](/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps)
