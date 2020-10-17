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
ms.openlocfilehash: 0b34b3a0dd79651ef288740243313d58482959e4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524785"
---
# <a name="manually-purging-the-call-detail-recording-and-quality-of-experience-databases-in-lync-server-2013"></a><span data-ttu-id="66954-102">Lync Server 2013에서 통화 정보 기록 및 경험 수준 데이터베이스를 수동으로 제거</span><span class="sxs-lookup"><span data-stu-id="66954-102">Manually purging the call detail recording and Quality of Experience databases in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="66954-103">_**마지막으로 수정 된 항목:** 2014-07-07_</span><span class="sxs-lookup"><span data-stu-id="66954-103">_**Topic Last Modified:** 2014-07-07_</span></span>

<span data-ttu-id="66954-104">관리자는 CDR (통화 정보 기록) 및/또는 QoE (체감 품질) 데이터베이스를 구성 하 여 데이터베이스에서 오래 된 레코드를 자동으로 제거할 수 있습니다. 이는 지정 된 데이터베이스 (CDR 또는 QoE)에 대해 제거가 사용 하도록 설정 되어 있고 데이터베이스에 지정 된 시간 보다 오래 된 레코드가 있는 경우에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="66954-104">Administrators can configure the Call Detail Recording (CDR) and/or the Quality of Experience (QoE) databases to automatically purge old records from the database; this occurs if purging has been enabled for the specified database (CDR or QoE) and if there are any records that have been in the database longer than the specified amount of time.</span></span> <span data-ttu-id="66954-105">예를 들어 매일 1:00 AM 관리자가 QoE 데이터베이스에서 이전에 60 일 보다 오래 된 QoE 레코드를 삭제 하도록 시스템을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66954-105">For example, every day at 1:00 AM administrators might configure the system so that QoE records more than 60 days old will be deleted from the QoE database.</span></span>

<span data-ttu-id="66954-106">자동 삭제 외에도 두 개의 새 cmdlet--Invoke-CsCdrDatabasePurge 및 Invoke-CsQoEDatbasePurge가 Microsoft Lync Server 2013에 추가 되었습니다. 이러한 cmdlet을 사용 하면 관리자가 언제 든 지 CDR 및 QoE 데이터베이스에서 레코드를 수동으로 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66954-106">In addition to that automatic purging, two new cmdlets -- Invoke-CsCdrDatabasePurge and Invoke-CsQoEDatbasePurge -- have been added to Microsoft Lync Server 2013; these cmdlets allow administrators to manually purge records from the CDR and the QoE databases at any time.</span></span> <span data-ttu-id="66954-107">예를 들어 CDR 데이터베이스에서 10 일 보다 오래 된 모든 레코드를 수동으로 제거 하려면 다음과 같은 명령을 사용 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="66954-107">For example, to manually purge all the records more than 10 days old from the CDR database you can use a command similar to this:</span></span>

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10

<span data-ttu-id="66954-108">위의 예에서는 10일보다 오래된 통화 정보 기록 및 진단 데이터 레코드가 모두 atl-sql-001.litwareinc.com의 모니터링 데이터베이스에서 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="66954-108">In the preceding command both call detail records and diagnostic data records older than 10 days are deleted from the monitoring database on atl-sql-001.litwareinc.com.</span></span> <span data-ttu-id="66954-109">통화 정보 기록은 사용자/세션 보고서입니다.</span><span class="sxs-lookup"><span data-stu-id="66954-109">(Call detail records are user/session reports.</span></span> <span data-ttu-id="66954-110">진단 데이터 레코드는 Lync 2013와 같은 클라이언트 응용 프로그램에서 업로드 하는 진단 로그입니다.</span><span class="sxs-lookup"><span data-stu-id="66954-110">Diagnostic data records are diagnostic logs uploaded by client applications such as Lync 2013.)</span></span>

<span data-ttu-id="66954-111">위에 나와 있는 것처럼, Invoke-CsCdrDatabasePurge cmdlet을 실행할 때는 PurgeCallDetaiDataOlderThanDays 및 PurgeDiagnosticDataOlderThanDays 매개 변수를 둘 다 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66954-111">As shown above, when you run the Invoke-CsCdrDatabasePurge cmdlet you must include both the PurgeCallDetaiDataOlderThanDays and the PurgeDiagnosticDataOlderThanDays parameters.</span></span> <span data-ttu-id="66954-112">그러나 이러한 매개 변수를 같은 값으로 설정할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="66954-112">However, these parameters do not have to be set to the same value.</span></span> <span data-ttu-id="66954-113">예를 들어 10일보다 오래된 통화 정보 기록은 삭제하는 동시에 진단 데이터 레코드는 모두 데이터베이스에 남겨 둘 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66954-113">For example, it's possible to purge call detail records more than 10 days old and yet, at the same time, leave all the diagnostic data records in the database.</span></span> <span data-ttu-id="66954-114">이 작업을 수행 하려면 Purgecalldetaildataolderthandays는을 10으로, PurgeDiagnosticDataOlderThanDays을 0으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="66954-114">To do that, set PurgeCallDetailDataOlderThanDays to 10 and PurgeDiagnosticDataOlderThanDays to 0.</span></span> <span data-ttu-id="66954-115">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="66954-115">For example:</span></span>

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 0

<span data-ttu-id="66954-116">기본적으로 Invoke-CsCdrDatabasePurge를 실행할 때마다 삭제해야 하는 각 데이터베이스 테이블에 대해 다음과 같은 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="66954-116">By default, any time you run Invoke-CsCdrDatabasePurge you will see a prompt similar to this one for each database table that must be purged:</span></span>

    Confirm
    Are you sure you want to perform this action?
    Performing operation "Stored procedure: RtcCleanupDiag" on Target "Target SQL Server:atl-sql-001.litwareinc.com\archinst Database: lcscdr".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All [S] Suspend  [?] Help (default is "Y"):

<span data-ttu-id="66954-p105">Y(예) 또는 A(모두 예)를 입력해야 데이터베이스 삭제가 실제로 수행됩니다. 이러한 확인 메시지가 표시되지 않도록 하려면 Invoke-CsCdrDatabasePurge 호출 끝부분에 다음 매개 변수를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="66954-p105">You must type either Y (for Yes) or A (for Yes to All) before the database purging will actually take place. If you would prefer to suppress these confirmation prompts, add the following parameter to the end of your call to Invoke-CsCdrDatabasePurge:</span></span>

    -Confirm:$False

<span data-ttu-id="66954-119">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="66954-119">For example:</span></span>

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False

<span data-ttu-id="66954-120">이렇게 하면 확인 메시지가 표시되지 않으며 데이터베이스 삭제가 즉시 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="66954-120">If you do that, confirmation prompts will not be displayed, and database purging will immediately be performed.</span></span>

<span data-ttu-id="66954-121">QoE 데이터베이스를 삭제하려면 Invoke-CsQoEDatabasePurge cmdlet을 사용하고 삭제할 레코드의 기간을 일 단위로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="66954-121">To purge the QoE database, use the Invoke-CsQoEDatabasePurge cmdlet and specify the age (in days) of the records to be deleted:</span></span>

    Invoke-CsQoEDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeQoEDataOlderThanDays 10

</div>

<span> </span>

</div>

</div>

</div>

