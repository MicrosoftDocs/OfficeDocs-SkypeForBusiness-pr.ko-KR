---
title: 통화 정보 기록 및 체감 품질 데이터베이스 수동 제거
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manually purging the call detail recording and Quality of Experience databases
ms:assetid: 3a3a965b-b861-41a4-b9a8-27184d622c17
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204812(v=OCS.15)
ms:contentKeyID: 48183859
ms.date: 07/07/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f14485465e44b089e5002a04d3ed5e5a392ad4d8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "41991863"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manually-purging-the-call-detail-recording-and-quality-of-experience-databases-in-lync-server-2013"></a>Lync Server 2013에서 통화 정보 기록 및 경험 수준 데이터베이스를 수동으로 제거

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-07-07_

관리자는 CDR (통화 정보 기록) 및/또는 QoE (체감 품질) 데이터베이스를 구성 하 여 데이터베이스에서 오래 된 레코드를 자동으로 제거할 수 있습니다. 이는 지정 된 데이터베이스 (CDR 또는 QoE)에 대해 제거가 사용 하도록 설정 되어 있고 데이터베이스에 지정 된 시간 보다 오래 된 레코드가 있는 경우에 발생 합니다. 예를 들어 매일 1:00 AM 관리자가 QoE 데이터베이스에서 이전에 60 일 보다 오래 된 QoE 레코드를 삭제 하도록 시스템을 구성할 수 있습니다.

이러한 자동 삭제 외에도 두 개의 새 cmdlet--Invoke-cscdrdatabasepurge 및 Invoke-CsQoEDatbasePurge가 Microsoft Lync Server 2013에 추가 되었습니다. 이러한 cmdlet을 사용 하면 관리자가 언제 든 지 CDR 및 QoE 데이터베이스에서 레코드를 수동으로 제거할 수 있습니다. 예를 들어 CDR 데이터베이스에서 10 일 보다 오래 된 모든 레코드를 수동으로 제거 하려면 다음과 같은 명령을 사용 하면 됩니다.

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10

위의 예에서는 10일보다 오래된 통화 정보 기록 및 진단 데이터 레코드가 모두 atl-sql-001.litwareinc.com의 모니터링 데이터베이스에서 삭제됩니다. 통화 정보 기록은 사용자/세션 보고서입니다. 진단 데이터 레코드는 Lync 2013와 같은 클라이언트 응용 프로그램에서 업로드 하는 진단 로그입니다.

위에 나와 있는 것처럼, Invoke-CsCdrDatabasePurge cmdlet을 실행할 때는 PurgeCallDetaiDataOlderThanDays 및 PurgeDiagnosticDataOlderThanDays 매개 변수를 둘 다 포함해야 합니다. 그러나 이러한 매개 변수를 같은 값으로 설정할 필요는 없습니다. 예를 들어 10일보다 오래된 통화 정보 기록은 삭제하는 동시에 진단 데이터 레코드는 모두 데이터베이스에 남겨 둘 수 있습니다. 이 작업을 수행 하려면 Purgecalldetaildataolderthandays는을 10으로, PurgeDiagnosticDataOlderThanDays을 0으로 설정 합니다. 예:

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 0

기본적으로 Invoke-CsCdrDatabasePurge를 실행할 때마다 삭제해야 하는 각 데이터베이스 테이블에 대해 다음과 같은 메시지가 표시됩니다.

    Confirm
    Are you sure you want to perform this action?
    Performing operation "Stored procedure: RtcCleanupDiag" on Target "Target SQL Server:atl-sql-001.litwareinc.com\archinst Database: lcscdr".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All [S] Suspend  [?] Help (default is "Y"):

Y(예) 또는 A(모두 예)를 입력해야 데이터베이스 삭제가 실제로 수행됩니다. 이러한 확인 메시지가 표시되지 않도록 하려면 Invoke-CsCdrDatabasePurge 호출 끝부분에 다음 매개 변수를 추가합니다.

    -Confirm:$False

예를 들면 다음과 같습니다.

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False

이렇게 하면 확인 메시지가 표시되지 않으며 데이터베이스 삭제가 즉시 수행됩니다.

QoE 데이터베이스를 삭제하려면 Invoke-CsQoEDatabasePurge cmdlet을 사용하고 삭제할 레코드의 기간을 일 단위로 지정합니다.

    Invoke-CsQoEDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeQoEDataOlderThanDays 10

</div>

<span> </span>

</div>

</div>

</div>

