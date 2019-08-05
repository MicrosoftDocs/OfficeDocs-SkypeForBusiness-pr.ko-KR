---
title: 비즈니스용 Skype 서버에서 보관 된 데이터 제거 관리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14c2b4fd-f612-4909-808d-09c655fc9f8a
description: '요약: 비즈니스용 Skype 서버의 보관 된 데이터 제거를 관리 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 193e17791290b384552542129d8d89c20296f109
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188211"
---
# <a name="manage-purging-of-archived-data-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 보관 된 데이터 제거 관리

**요약:** 비즈니스용 Skype 서버의 보관 된 데이터 제거를 관리 하는 방법에 대해 알아봅니다.
  
보관 데이터베이스는 장기 보존을 위한 것이 아니며 비즈니스용 Skype 서버는 보관 된 데이터에 대 한 e-검색 (검색) 솔루션을 제공 하지 않으므로 데이터를 다른 저장소로 옮겨야 합니다. 비즈니스용 Skype Server는 보관 된 데이터를 검색 가능한 내용으로 내보내는 데 사용할 수 있는 세션 내보내기 도구를 제공 합니다. 보관 하 고 내보낸 데이터를 지울 시기를 정의 해야 합니다. 
  
**Export-CsArchivingData** cmdlet을 사용 하 여 데이터를 내보내는 방법에 대 한 자세한 내용은 비즈니스용 [Skype 서버에서 보관 된 데이터 내보내기를](export-archived-data.md)참조 하세요.
  
## <a name="manage-purging-of-data-by-using-the-control-panel"></a>제어판을 사용 하 여 데이터 지우기 관리

제어판을 사용 하 여 보관 된 데이터의 제거를 관리 하려면 다음을 실행 합니다.
  
1. CsArchivingAdministrator 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다. 
    
2. 브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다. 
    
3. 왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭 한 다음 **구성 보관**을 클릭 합니다.
    
4. 보관 구성 목록에서 적절 한 전역, 사이트 또는 풀 구성의 이름을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 하 고 다음을 수행 합니다.
    
   - 제거를 사용 하도록 설정 하려면 **데이터 보관 제거 사용** 확인란을 선택 하 고 다음 중 하나를 수행 합니다.
    
     - 모든 레코드를 제거 하려면 **내보낸 데이터 보관 및 저장 된 최대 기간 (일)** 을 클릭 한 다음 일 수를 지정 합니다.
    
     - 내보낸 데이터만 제거 하려면 **내보낸 데이터 보관만 삭제**를 클릭 합니다.
    
   - 제거를 사용 하지 않도록 설정 하려면 **데이터 보관 제거 사용** 확인란의 선택을 취소 합니다.
    
5. **커밋**을 클릭합니다.
    
## <a name="manage-purging-of-data-by-using-windows-powershell"></a>Windows PowerShell을 사용 하 여 데이터 지우기 관리

다음 Windows PowerShell cmdlet을 사용 하 여 보관 된 데이터 제거를 관리할 수 있습니다.
  
- EnablePurging 매개 변수를 사용 하 여 **CsArchivingConfiguration** cmdlet을 사용 하 여 보관 된 데이터의 제거를 설정 하거나 해제할 수 있습니다.
    
- **-CsArchivingDatabasePurge를 호출** 하면 보관 데이터베이스에서 레코드를 수동으로 제거할 수 있습니다.
    
예를 들어 다음 명령을 사용 하 여 아카이브된 모든 데이터를 제거할 수 있습니다. 이 명령을 실행 한 후 비즈니스용 Skype Server는 KeepArchivingDataForDays 매개 변수에 지정 된 값 보다 오래 된 모든 보관 레코드를 제거 합니다. 
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
```

다음 명령은 **내보내기-CSArchivingData** cmdlet을 사용 하 여 데이터 파일로 내보낸 보관 된 레코드로의 제거를 제한 합니다. 또한 PurgeExportedArchivesOnly 매개 변수를 True ($True)로 설정 해야 합니다.
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
```

이 명령을 실행 한 후 비즈니스용 Skype 서버는 두 개의 조건을 충족 하는 보관 레코드만을 제거 합니다. 1) KeepArchivingDataForDays 매개 변수에 지정 된 값 보다 오래 된 것입니다. and, 2) **CsArchivingData** cmdlet을 사용 하 여 내보내기를 완료 했습니다.
  
기록 보관의 자동 제거를 사용 하지 않도록 설정 하려면 EnablePurging 매개 변수를 False ($False)로 설정 합니다.
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False
```

다음 예제에서는 **CsArchivingDatabasePurge** cmdlet을 사용 하 여 atl-sql-001.contoso.com의 보관 데이터베이스에서 24 시간 이상 오래 된 레코드를 모두 제거 합니다. 내보내지지 않은 레코드를 포함 하 여 모든 레코드가 삭제 되도록 PurgeExportedArchivesOnly 매개 변수가 False ($False)로 설정 됩니다.
  
```
Invoke-CsArchivingDatabasePurge -Identity "service:ArchivingDatabase:atl-sql-001.contoso.com" -PurgeArchivingDataOlderThanHours 24 -PurgeExportedArchivesOnly $False
```
