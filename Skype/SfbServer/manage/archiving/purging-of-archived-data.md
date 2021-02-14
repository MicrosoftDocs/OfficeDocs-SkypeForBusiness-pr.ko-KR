---
title: 비즈니스용 Skype 서버에서 보관된 데이터 삭제 관리
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
ms.assetid: 14c2b4fd-f612-4909-808d-09c655fc9f8a
description: '요약: 비즈니스용 Skype 서버의 보관된 데이터 삭제를 관리하는 방법을 설명하는 문서입니다.'
ms.openlocfilehash: aecc78f84b3cd4b745a96e534535c98c1739c156
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828538"
---
# <a name="manage-purging-of-archived-data-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 보관된 데이터 삭제 관리

**요약:** 비즈니스용 Skype 서버의 보관된 데이터 삭제를 관리하는 방법에 대해 자세히 알아보습니다.
  
보관 데이터베이스는 장기 보존용이 아니며, 비즈니스용 Skype 서버는 보관된 데이터에 대한 전자 검색(검색) 솔루션을 제공하지 않습니다. 따라서 데이터를 다른 저장소로 이동해야 합니다. 비즈니스용 Skype 서버는 보관된 데이터를 검색 가능한 기록으로 내보내는 데 사용할 수 있는 세션 내보내기 도구를 제공합니다. 보관된 데이터와 내보낼 데이터를 삭제하는 경우를 정의해야 합니다. 
  
**Export-CsArchivingData** cmdlet을 사용하여 데이터를 내보내는 데 대한 자세한 내용은 비즈니스용 Skype 서버에서 보관된 데이터 내보내기를 [참조하세요.](export-archived-data.md)
  
## <a name="manage-purging-of-data-by-using-the-control-panel"></a>제어판을 사용하여 데이터 제거 관리

제어판을 사용하여 보관된 데이터 삭제를 관리합니다.
  
1. CsArchivingAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다. 
    
2. 브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다. 
    
3. 왼쪽 탐색 모음에서 **모니터링 및 보관** 을 클릭하고 **보관 구성** 을 클릭합니다.
    
4. 보관 구성 목록에서 적절한 전역, 사이트 또는 풀 구성의 이름을 클릭하고 **편집** 을 클릭한 후에 **자세한 정보 표시** 를 클릭하고 다음을 수행합니다.
    
   - 삭제를 사용하도록 설정하려면 **보관 데이터 삭제 사용** 확인란을 선택하고 다음 중 하나를 수행합니다.
    
     - 모든 레코드를 삭제하려면 **내보낸 보관 데이터 및 최대 기간(일)이 지난 저장된 보관 데이터 삭제** 를 클릭하고 기간(일)을 지정합니다.
    
     - 내보낸 데이터만 삭제하려면 **내보낸 보관 데이터만 삭제** 를 클릭합니다.
    
   - 삭제를 사용하지 않도록 설정하려면 **보관 데이터 삭제 사용** 확인란 선택을 취소합니다.
    
5. **커밋** 을 클릭합니다.
    
## <a name="manage-purging-of-data-by-using-windows-powershell"></a>데이터를 사용하여 데이터 Windows PowerShell

다음 cmdlet을 사용하여 보관된 데이터 삭제를 관리할 Windows PowerShell 있습니다.
  
- EnablePurging 매개 변수가 있는 **Set-CsArchivingConfiguration** cmdlet을 사용하면 보관된 데이터 삭제를 활성화하거나 사용하지 않도록 설정할 수 있습니다.
    
- **Invoke-CsArchivingDatabasePurge를** 사용하면 보관 데이터베이스에서 레코드를 수동으로 지우는 데 사용됩니다.
    
예를 들어 다음 명령은 보관된 모든 데이터를 지우는 데 사용할 수 있습니다. 이 명령을 실행하면 비즈니스용 Skype 서버는 KeepArchivingDataForDays 매개 변수에 지정된 값보다 오래된 모든 보관 레코드를 제거합니다. 
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
```

다음 명령은 **Export-CSArchivingData** cmdlet을 사용하여 데이터 파일로 내보냈던 보관된 레코드의 삭제를 제한합니다. PurgeExportedArchivesOnly 매개 변수도 True($True).
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
```

이 명령을 실행하면 비즈니스용 Skype 서버는 두 가지 조건, 즉 1) KeepArchivingDataForDays 매개 변수에 지정된 값보다 오래된 보관 레코드만 제거합니다. 2) **Export-CsArchivingData** cmdlet을 사용하여 내보낼 수 있습니다.
  
보관 레코드의 자동 제거를 사용하지 않도록 설정하려면 EnablePurging 매개 변수를 False($False).
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False
```

다음 예제에서는 **Invoke-CsArchivingDatabasePurge** cmdlet을 사용하여 24시간보다 오래된 모든 레코드를 보관 데이터베이스에서 atl-sql-001.contoso.com. 내보내지 않은 레코드를 포함하여 모든 레코드가 삭제되도록 PurgeExportedArchivesOnly 매개 변수는 False($False).
  
```PowerShell
Invoke-CsArchivingDatabasePurge -Identity "service:ArchivingDatabase:atl-sql-001.contoso.com" -PurgeArchivingDataOlderThanHours 24 -PurgeExportedArchivesOnly $False
```
