---
title: 보관 정책에서 기존 보관 정책을 비즈니스용 Skype 서버
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
ms.assetid: 8b88bed9-2b37-4caf-b119-48688076e06a
description: '요약: 보관 정책에 대한 보관 정책을 삭제하는 비즈니스용 Skype 서버.'
ms.openlocfilehash: acc4f0b5a1576b1e46989f5717754e700de0a86d
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58632942"
---
# <a name="delete-an-existing-archiving-policy-in-skype-for-business-server"></a>보관 정책에서 기존 보관 정책을 비즈니스용 Skype 서버

**요약:** 보관 정책에 대한 보관 정책을 삭제하는 비즈니스용 Skype 서버.
  
사용자 정책 또는 사이트 정책은 삭제할 수 있지만 글로벌 정책은 삭제할 수 없습니다. 전역 정책을 삭제하면 비즈니스용 Skype 서버 기본값으로 자동으로 다시 설정됩니다.
  
## <a name="delete-a-policy-by-using-the-control-panel"></a>제어판을 사용하여 정책 삭제

1. CsArchivingAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다. 
    
2. 브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버 열 수 있습니다. 
    
3. 왼쪽 탐색 모음에서 **모니터링 및 보관** 을 클릭하고 **보관 정책** 을 클릭합니다.
    
4. 보관 정책 목록에서 삭제하려는 사용자 또는 사이트 정책을 클릭하고, **편집** 을 클릭한 후 **삭제** 를 클릭합니다.
    
5. **커밋** 을 클릭합니다.
    
## <a name="delete-a-policy-by-using-windows-powershell"></a>정책을 사용하여 정책 Windows PowerShell

**Remove-CsArchivingPolicy** cmdlet을 사용하여 보관 정책을 삭제할 수도 있습니다.
  
예를 들어 다음 명령은 ID가 site:Redmond인 정책을 삭제합니다. 사이트 수준에서 구성된 정책이 삭제되면 이전에 사이트 정책에 의해 관리된 사용자는 자동으로 전역 보관 정책에 의해 관리됩니다.
  
```PowerShell
Remove-CsArchivingPolicy -Identity site:Redmond
```

이 명령은 사용자 수준에 적용된 모든 보관 정책을 제거합니다.
  
```PowerShell
Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy
```

이 명령은 내부 보관이 해제된 모든 보관 정책을 제거합니다.
  
```PowerShell
Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy
```

자세한 내용은 [Remove-CsArchivingPolicy](/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps) cmdlet에 대한 도움말 항목을 참조하십시오.