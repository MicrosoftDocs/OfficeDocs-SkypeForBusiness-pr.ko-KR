---
title: 비즈니스용 Skype 서버에서 통화 정보 기록 및 경력 데이터베이스의 품질을 수동으로 제거
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3a3a965b-b861-41a4-b9a8-27184d622c17
description: '요약: CDR 및 비즈니스용 Skype 서버에서 사용 하는 체감 품질 데이터베이스의 레코드를 수동으로 제거 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: ba87e05dd72e5da22cfe4e01cd68be1a9fac6242
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239879"
---
# <a name="manually-purge-the-call-detail-recording-and-quality-of-experience-databases-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 통화 정보 기록 및 경력 데이터베이스의 품질을 수동으로 제거
 
**요약:** 비즈니스용 Skype 서버에서 사용 하는 체감 품질 데이터베이스와 CDR의 레코드를 수동으로 제거 하는 방법에 대해 알아봅니다.
  
CDR 및 체감 품질 데이터베이스는 수동으로 또는 레코드를 자동으로 제거할 수 있습니다. 레코드 제거는 데이터가 쓸모 없게 되거나 시작 기준선에서 보고서를 다시 설정 해야 하는 경우에 중요할 수 있습니다.
  
## <a name="manually-purge-records-from-cdr-and-qoe-databases"></a>CDR 및 체감 품질 데이터베이스에서 수동으로 레코드 제거

관리자는 데이터베이스에서 오래 된 레코드를 자동으로 제거 하도록 체감 품질 (통화 정보 기록) 및/또는 환경 (경력 품질) 데이터베이스를 구성할 수 있습니다. 지정 된 데이터베이스 (CDR 또는 체감 품질)에 대 한 제거가 설정 되어 있고 데이터베이스에 지정 된 시간 보다 오래 된 레코드가 있는 경우이 문제가 발생 합니다. 예를 들어 매일 1:00 AM 관리자는 60 일이 지난 체감 품질 레코드가 체감 품질 데이터베이스에서 삭제 되도록 시스템을 구성할 수 있습니다.
  
이러한 자동 제거 외에도 CsCdrDatabasePurge 및 Invoke를 호출 하는 두 개의 새로운 &#x2014; cmdlet 인-CsQoEDatbasePurge &#x2014; 비즈니스용 Skype 서버에 추가 되었습니다. 관리자는 이러한 cmdlet을 사용 하 여 언제 든 지 CDR 및 체감 품질 데이터베이스에서 레코드를 수동으로 제거할 수 있습니다. 예를 들어, CDR 데이터베이스에서 10 일 이상 지난 모든 레코드를 수동으로 제거 하려면 다음과 같은 명령을 사용할 수 있습니다.
  
```
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10
```

앞의 명령에서 10 일 보다 오래 된 통화 정보 레코드 및 진단 데이터 레코드는 모두 atl-sql-001.litwareinc.com의 모니터링 데이터베이스에서 삭제 됩니다. (통화 정보 레코드는 사용자/세션 보고서입니다. 진단 데이터 레코드는 비즈니스용 Skype 서버와 같은 클라이언트 응용 프로그램에서 업로드 한 진단 로그입니다.
  
위의 그림과 같이 CsCdrDatabasePurge cmdlet을 실행 하는 경우에는 PurgeCallDetaiDataOlderThanDays 및 PurgeDiagnosticDataOlderThanDays 매개 변수를 둘 다 포함 해야 합니다. 그러나 이러한 매개 변수를 같은 값으로 설정할 필요는 없습니다. 예를 들어 10 일 이상 지난 통화 정보 레코드를 제거 하 고 동시에 모든 진단 데이터 레코드를 데이터베이스에 남길 수 있습니다. 이 작업을 수행 하려면 PurgeCallDetailDataOlderThanDays를 10으로, PurgeDiagnosticDataOlderThanDays를 0으로 설정 합니다. 예를 들면 다음과 같습니다.
  
```
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 0
```

기본적으로 CsCdrDatabasePurge를 실행할 때마다 제거 해야 하는 각 데이터베이스 테이블에 대해 다음과 비슷한 메시지가 표시 됩니다.
  
<pre>
Confirm
Are you sure you want to perform this action?
Performing operation "Stored procedure: RtcCleanupDiag" on Target "Target SQL Server:atl-sql-001.litwareinc.com\archinst Database: lcscdr".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All [S] Suspend  [?] Help (default is "Y"):
</pre>

데이터베이스 제거를 실제로 수행 하기 전에 Y (Yes) 또는 A (Yes에 대해)를 입력 해야 합니다. 이러한 확인 메시지를 표시 하지 않으려면 CsCdrDatabasePurge 호출에 대 한 통화 종료에 다음 매개 변수를 추가 합니다.
  
```
-Confirm:$False
```

예를 들면 다음과 같습니다.
  
```
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False
```

이렇게 하면 확인 메시지가 표시 되지 않으며 데이터베이스 제거가 즉시 수행 됩니다.
  
체감 품질 데이터베이스를 제거 하려면 Invoke-CsQoEDatabasePurge cmdlet을 사용 하 고 삭제할 레코드의 보존 기간 (일)을 지정 합니다.
  
```
Invoke-CsQoEDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeQoEDataOlderThanDays 10
```


