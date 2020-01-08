---
title: 통화 정보 기록 및 경력 데이터베이스 품질 수동 제거
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Manually purging the call detail recording and Quality of Experience databases
ms:assetid: 3a3a965b-b861-41a4-b9a8-27184d622c17
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204812(v=OCS.15)
ms:contentKeyID: 48183859
ms.date: 07/07/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 979f05441bfb62c8b79c604127e23fe7b7b4909f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983115"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manually-purging-the-call-detail-recording-and-quality-of-experience-databases-in-lync-server-2013"></a>Lync Server 2013에서 통화 정보 기록 및 경력 데이터베이스의 품질을 수동으로 제거

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-07-07_

관리자는 데이터베이스에서 오래 된 레코드를 자동으로 제거 하도록 체감 품질 (통화 정보 기록) 및/또는 환경 (경력 품질) 데이터베이스를 구성할 수 있습니다. 지정 된 데이터베이스 (CDR 또는 체감 품질)에 대 한 제거가 설정 되어 있고 데이터베이스에 지정 된 시간 보다 오래 된 레코드가 있는 경우이 문제가 발생 합니다. 예를 들어 매일 1:00 AM 관리자는 60 일이 지난 체감 품질 레코드가 체감 품질 데이터베이스에서 삭제 되도록 시스템을 구성할 수 있습니다.

이러한 자동 제거 외에도 CsCdrDatabasePurge 및 Invoke-CsQoEDatbasePurge의 두 가지 새로운 cmdlet이 Microsoft Lync Server 2013에 추가 되었습니다. 관리자는 이러한 cmdlet을 사용 하 여 언제 든 지 CDR 및 체감 품질 데이터베이스에서 레코드를 수동으로 제거할 수 있습니다. 예를 들어, CDR 데이터베이스에서 10 일 이상 지난 모든 레코드를 수동으로 제거 하려면 다음과 같은 명령을 사용할 수 있습니다.

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10

앞의 명령에서 10 일 보다 오래 된 통화 정보 레코드 및 진단 데이터 레코드는 모두 atl-sql-001.litwareinc.com의 모니터링 데이터베이스에서 삭제 됩니다. (통화 정보 레코드는 사용자/세션 보고서입니다. 진단 데이터 레코드는 Lync 2013 등의 클라이언트 응용 프로그램에서 업로드 한 진단 로그입니다.

위의 그림과 같이 CsCdrDatabasePurge cmdlet을 실행 하는 경우에는 PurgeCallDetaiDataOlderThanDays 및 PurgeDiagnosticDataOlderThanDays 매개 변수를 둘 다 포함 해야 합니다. 그러나 이러한 매개 변수를 같은 값으로 설정할 필요는 없습니다. 예를 들어 10 일 이상 지난 통화 정보 레코드를 제거 하 고 동시에 모든 진단 데이터 레코드를 데이터베이스에 남길 수 있습니다. 이 작업을 수행 하려면 PurgeCallDetailDataOlderThanDays를 10으로, PurgeDiagnosticDataOlderThanDays를 0으로 설정 합니다. 예를 들면 다음과 같습니다.

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 0

기본적으로 CsCdrDatabasePurge를 실행할 때마다 제거 해야 하는 각 데이터베이스 테이블에 대해 다음과 비슷한 메시지가 표시 됩니다.

    Confirm
    Are you sure you want to perform this action?
    Performing operation "Stored procedure: RtcCleanupDiag" on Target "Target SQL Server:atl-sql-001.litwareinc.com\archinst Database: lcscdr".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All [S] Suspend  [?] Help (default is "Y"):

데이터베이스 제거를 실제로 수행 하기 전에 Y (Yes) 또는 A (Yes에 대해)를 입력 해야 합니다. 이러한 확인 메시지를 표시 하지 않으려면 CsCdrDatabasePurge 호출에 대 한 통화 종료에 다음 매개 변수를 추가 합니다.

    -Confirm:$False

예를 들면 다음과 같습니다.

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False

이렇게 하면 확인 메시지가 표시 되지 않으며 데이터베이스 제거가 즉시 수행 됩니다.

체감 품질 데이터베이스를 제거 하려면 Invoke-CsQoEDatabasePurge cmdlet을 사용 하 고 삭제할 레코드의 보존 기간 (일)을 지정 합니다.

    Invoke-CsQoEDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeQoEDataOlderThanDays 10

</div>

<span> </span>

</div>

</div>

</div>

