---
title: 비즈니스용 Skype 서버에서 통화 정보 기록 및 경험 품질 데이터베이스를 수동으로 제거
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3a3a965b-b861-41a4-b9a8-27184d622c17
description: '요약: 비즈니스용 Skype 서버에서 사용하는 CDR 및 QoE 데이터베이스에서 레코드를 수동으로 지우는 방법을 설명하는 문서입니다.'
ms.openlocfilehash: 2d36af2d06b6d6951e436ea456d4036478278600
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802148"
---
# <a name="manually-purge-the-call-detail-recording-and-quality-of-experience-databases-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 통화 정보 기록 및 경험 품질 데이터베이스를 수동으로 제거
 
**요약:** 비즈니스용 Skype 서버에서 사용하는 CDR 및 QoE 데이터베이스에서 레코드를 수동으로 지우는 방법을 알아보습니다.
  
CDR 및 QoE 데이터베이스는 레코드를 수동으로 또는 자동으로 삭제할 수 있습니다. 데이터가 부실해지거나 시작 기준에서 보고서를 다시 설정해야 할 때 레코드를 지우는 것이 중요할 수 있습니다.
  
## <a name="manually-purge-records-from-cdr-and-qoe-databases"></a>CDR 및 QoE 데이터베이스에서 레코드 수동 제거

관리자는 CDR(통화 정보 기록) 및/또는 QoE(QoE) 데이터베이스에서 오래된 레코드를 자동으로 제거하도록 구성할 수 있습니다. 이는 지정한 데이터베이스(CDR 또는 QoE)에 대해 삭제를 사용하도록 설정한 경우와 데이터베이스에 지정된 시간보다 긴 레코드가 있는 경우 발생합니다. 예를 들어 매일 오전 1시에 관리자가 60일보다 오래된 QoE 레코드를 QoE 데이터베이스에서 삭제하도록 시스템을 구성할 수 있습니다.
  
자동 삭제 외에도 비즈니스용 Skype 서버에 &#x2014; Invoke-CsCdrDatabasePurge 및 Invoke-CsQoEDatbasePurge &#x2014; 새 cmdlet이 추가되었습니다. 이러한 cmdlet을 통해 관리자는 CDR 및 QoE 데이터베이스에서 레코드를 수동으로 지울 수 있습니다. 예를 들어 CDR 데이터베이스에서 10일보다 오래된 모든 레코드를 수동으로 제거하려면 다음과 같은 명령을 사용할 수 있습니다.
  
```powershell
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10
```

위의 예에서는 10일보다 오래된 통화 정보 기록 및 진단 데이터 레코드가 모두 atl-sql-001.litwareinc.com의 모니터링 데이터베이스에서 삭제됩니다. 통화 정보 기록은 사용자/세션 보고서입니다. 진단 데이터 레코드는 비즈니스용 Skype 서버와 같은 클라이언트 응용 프로그램에서 업로드하는 진단 로그입니다.
  
위에 나와 있는 것처럼, Invoke-CsCdrDatabasePurge cmdlet을 실행할 때는 PurgeCallDetaiDataOlderThanDays 및 PurgeDiagnosticDataOlderThanDays 매개 변수를 둘 다 포함해야 합니다. 그러나 이러한 매개 변수를 같은 값으로 설정할 필요는 없습니다. 예를 들어 10일보다 오래된 통화 정보 기록은 삭제하는 동시에 진단 데이터 레코드는 모두 데이터베이스에 남겨 둘 수 있습니다. 이를 위해 PurgeCallDetailDataOlderThanDays를 10으로 설정하고 PurgeDiagnosticDataOlderThanDays를 0으로 설정합니다. 예를 들면 다음과 같습니다.
  
```powershell
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 0
```

기본적으로 Invoke-CsCdrDatabasePurge를 실행할 때마다 삭제해야 하는 각 데이터베이스 테이블에 대해 다음과 같은 메시지가 표시됩니다.
  
<pre>
Confirm
Are you sure you want to perform this action?
Performing operation "Stored procedure: RtcCleanupDiag" on Target "Target SQL Server:atl-sql-001.litwareinc.com\archinst Database: lcscdr".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All [S] Suspend  [?] Help (default is "Y"):
</pre>

Y(예) 또는 A(모두 예)를 입력해야 데이터베이스 삭제가 실제로 수행됩니다. 이러한 확인 메시지가 표시되지 않도록 하려면 Invoke-CsCdrDatabasePurge 호출 끝부분에 다음 매개 변수를 추가합니다.
  
```powershell
-Confirm:$False
```

예를 들면 다음과 같습니다.
  
```powershell
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False
```

이렇게 하면 확인 메시지가 표시되지 않으며 데이터베이스 삭제가 즉시 수행됩니다.
  
QoE 데이터베이스를 삭제하려면 Invoke-CsQoEDatabasePurge cmdlet을 사용하고 삭제할 레코드의 기간을 일 단위로 지정합니다.
  
```powershell
Invoke-CsQoEDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeQoEDataOlderThanDays 10
```


