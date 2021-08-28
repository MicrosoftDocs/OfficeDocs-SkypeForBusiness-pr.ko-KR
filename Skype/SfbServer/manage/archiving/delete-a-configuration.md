---
title: 보관 구성을 비즈니스용 Skype 서버
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
ms.assetid: fed12cb5-2c80-476a-af3b-d55b450c5fbc
description: '요약: 보관 구성을 삭제하는 방법을 비즈니스용 Skype 서버.'
ms.openlocfilehash: 046bd2c1fc5e54189ac038bdf769a711b3c9a774
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58621144"
---
# <a name="delete-an-archiving-configuration-in-skype-for-business-server"></a>보관 구성을 비즈니스용 Skype 서버

**요약:** 보관 구성을 삭제하는 방법을 비즈니스용 Skype 서버.
  
사이트 구성 또는 풀 구성을 삭제할 수는 있지만 전역 구성은 삭제할 수 없습니다. 전역 구성을 삭제하는 경우 자동으로 구성이 기본값으로 다시 설정됩니다.
  
## <a name="delete-an-archiving-configuration-by-using-the-control-panel"></a>제어판을 사용하여 보관 구성 삭제

제어판을 사용하여 보관 구성을 삭제하려면
  
1. CsArchivingAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다. 
    
2. 브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버 열 수 있습니다. 
    
3. 왼쪽 탐색 모음에서 **모니터링 및 보관** 을 클릭하고 **보관 구성** 을 클릭합니다.
    
4. 보관 구성 목록에서 삭제할 사이트 또는 풀 구성을 클릭하고 **편집** 을 클릭한 다음 **삭제** 를 클릭합니다.
    
    > [!NOTE]
    > 전역 구성을 클릭할 수도 있지만 전역 구성을 기본값으로 다시 설정하려는 경우 이 옵션을 선택합니다. 
  
5. **커밋** 을 클릭합니다.
    
## <a name="delete-an-archiving-configuration-by-using-windows-powershell"></a>보관 구성을 사용하여 Windows PowerShell

**Remove-CsArchivingConfiguration** cmdlet을 사용하여 보관 구성을 삭제할 수도 있습니다.
  
예를 들어 다음 명령은 Redmond 사이트에 적용된 보관 구성 설정을 제거합니다. 사이트 범위에서 구성된 정책이 삭제되면 이전에 사이트 정책에 의해 관리된 사용자는 자동으로 전역 보관 정책에 의해 관리됩니다.
  
```PowerShell
Remove-CsArchivingConfiguration -Identity "site:Redmond"
```

다음 명령은 서비스 범위에 적용된 모든 보관 구성 설정을 제거합니다.
  
```PowerShell
Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration
```

다음 명령은 보관을 사용하지 않도록 Exchange 모든 보관 구성 설정을 제거합니다.
  
```PowerShell
Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration
```

**Remove-CsArchivingConfiguration** cmdlet을 사용하여 전역 설정을 기본값으로 다시 설정할 수도 있습니다. 예를 들어 IM 세션 보관을 전역 수준에서 사용하도록 설정했다고 가정해 보겠습니다. 다음 명령은 값을 기본값 None으로 다시 설정하여 전역 수준에서 보관을 사용하지 않도록 설정합니다.
  
```PowerShell
Remove-CsArchivingConfiguration -Identity global
```

자세한 내용은 [Remove-CsArchivingConfiguration](/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps) cmdlet에 대한 도움말 항목을 참조하십시오.