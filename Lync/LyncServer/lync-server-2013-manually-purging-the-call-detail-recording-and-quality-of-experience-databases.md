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

# <a name="manually-purging-the-call-detail-recording-and-quality-of-experience-databases-in-lync-server-2013"></a><span data-ttu-id="926c5-102">Lync Server 2013에서 통화 정보 기록 및 경력 데이터베이스의 품질을 수동으로 제거</span><span class="sxs-lookup"><span data-stu-id="926c5-102">Manually purging the call detail recording and Quality of Experience databases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="926c5-103">_**마지막으로 수정한 주제:** 2014-07-07_</span><span class="sxs-lookup"><span data-stu-id="926c5-103">_**Topic Last Modified:** 2014-07-07_</span></span>

<span data-ttu-id="926c5-104">관리자는 데이터베이스에서 오래 된 레코드를 자동으로 제거 하도록 체감 품질 (통화 정보 기록) 및/또는 환경 (경력 품질) 데이터베이스를 구성할 수 있습니다. 지정 된 데이터베이스 (CDR 또는 체감 품질)에 대 한 제거가 설정 되어 있고 데이터베이스에 지정 된 시간 보다 오래 된 레코드가 있는 경우이 문제가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="926c5-104">Administrators can configure the Call Detail Recording (CDR) and/or the Quality of Experience (QoE) databases to automatically purge old records from the database; this occurs if purging has been enabled for the specified database (CDR or QoE) and if there are any records that have been in the database longer than the specified amount of time.</span></span> <span data-ttu-id="926c5-105">예를 들어 매일 1:00 AM 관리자는 60 일이 지난 체감 품질 레코드가 체감 품질 데이터베이스에서 삭제 되도록 시스템을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="926c5-105">For example, every day at 1:00 AM administrators might configure the system so that QoE records more than 60 days old will be deleted from the QoE database.</span></span>

<span data-ttu-id="926c5-106">이러한 자동 제거 외에도 CsCdrDatabasePurge 및 Invoke-CsQoEDatbasePurge의 두 가지 새로운 cmdlet이 Microsoft Lync Server 2013에 추가 되었습니다. 관리자는 이러한 cmdlet을 사용 하 여 언제 든 지 CDR 및 체감 품질 데이터베이스에서 레코드를 수동으로 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="926c5-106">In addition to that automatic purging, two new cmdlets -- Invoke-CsCdrDatabasePurge and Invoke-CsQoEDatbasePurge -- have been added to Microsoft Lync Server 2013; these cmdlets allow administrators to manually purge records from the CDR and the QoE databases at any time.</span></span> <span data-ttu-id="926c5-107">예를 들어, CDR 데이터베이스에서 10 일 이상 지난 모든 레코드를 수동으로 제거 하려면 다음과 같은 명령을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="926c5-107">For example, to manually purge all the records more than 10 days old from the CDR database you can use a command similar to this:</span></span>

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10

<span data-ttu-id="926c5-108">앞의 명령에서 10 일 보다 오래 된 통화 정보 레코드 및 진단 데이터 레코드는 모두 atl-sql-001.litwareinc.com의 모니터링 데이터베이스에서 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="926c5-108">In the preceding command both call detail records and diagnostic data records older than 10 days are deleted from the monitoring database on atl-sql-001.litwareinc.com.</span></span> <span data-ttu-id="926c5-109">(통화 정보 레코드는 사용자/세션 보고서입니다.</span><span class="sxs-lookup"><span data-stu-id="926c5-109">(Call detail records are user/session reports.</span></span> <span data-ttu-id="926c5-110">진단 데이터 레코드는 Lync 2013 등의 클라이언트 응용 프로그램에서 업로드 한 진단 로그입니다.</span><span class="sxs-lookup"><span data-stu-id="926c5-110">Diagnostic data records are diagnostic logs uploaded by client applications such as Lync 2013.)</span></span>

<span data-ttu-id="926c5-111">위의 그림과 같이 CsCdrDatabasePurge cmdlet을 실행 하는 경우에는 PurgeCallDetaiDataOlderThanDays 및 PurgeDiagnosticDataOlderThanDays 매개 변수를 둘 다 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="926c5-111">As shown above, when you run the Invoke-CsCdrDatabasePurge cmdlet you must include both the PurgeCallDetaiDataOlderThanDays and the PurgeDiagnosticDataOlderThanDays parameters.</span></span> <span data-ttu-id="926c5-112">그러나 이러한 매개 변수를 같은 값으로 설정할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="926c5-112">However, these parameters do not have to be set to the same value.</span></span> <span data-ttu-id="926c5-113">예를 들어 10 일 이상 지난 통화 정보 레코드를 제거 하 고 동시에 모든 진단 데이터 레코드를 데이터베이스에 남길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="926c5-113">For example, it's possible to purge call detail records more than 10 days old and yet, at the same time, leave all the diagnostic data records in the database.</span></span> <span data-ttu-id="926c5-114">이 작업을 수행 하려면 PurgeCallDetailDataOlderThanDays를 10으로, PurgeDiagnosticDataOlderThanDays를 0으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="926c5-114">To do that, set PurgeCallDetailDataOlderThanDays to 10 and PurgeDiagnosticDataOlderThanDays to 0.</span></span> <span data-ttu-id="926c5-115">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="926c5-115">For example:</span></span>

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 0

<span data-ttu-id="926c5-116">기본적으로 CsCdrDatabasePurge를 실행할 때마다 제거 해야 하는 각 데이터베이스 테이블에 대해 다음과 비슷한 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="926c5-116">By default, any time you run Invoke-CsCdrDatabasePurge you will see a prompt similar to this one for each database table that must be purged:</span></span>

    Confirm
    Are you sure you want to perform this action?
    Performing operation "Stored procedure: RtcCleanupDiag" on Target "Target SQL Server:atl-sql-001.litwareinc.com\archinst Database: lcscdr".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All [S] Suspend  [?] Help (default is "Y"):

<span data-ttu-id="926c5-117">데이터베이스 제거를 실제로 수행 하기 전에 Y (Yes) 또는 A (Yes에 대해)를 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="926c5-117">You must type either Y (for Yes) or A (for Yes to All) before the database purging will actually take place.</span></span> <span data-ttu-id="926c5-118">이러한 확인 메시지를 표시 하지 않으려면 CsCdrDatabasePurge 호출에 대 한 통화 종료에 다음 매개 변수를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="926c5-118">If you would prefer to suppress these confirmation prompts, add the following parameter to the end of your call to Invoke-CsCdrDatabasePurge:</span></span>

    -Confirm:$False

<span data-ttu-id="926c5-119">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="926c5-119">For example:</span></span>

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False

<span data-ttu-id="926c5-120">이렇게 하면 확인 메시지가 표시 되지 않으며 데이터베이스 제거가 즉시 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="926c5-120">If you do that, confirmation prompts will not be displayed, and database purging will immediately be performed.</span></span>

<span data-ttu-id="926c5-121">체감 품질 데이터베이스를 제거 하려면 Invoke-CsQoEDatabasePurge cmdlet을 사용 하 고 삭제할 레코드의 보존 기간 (일)을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="926c5-121">To purge the QoE database, use the Invoke-CsQoEDatabasePurge cmdlet and specify the age (in days) of the records to be deleted:</span></span>

    Invoke-CsQoEDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeQoEDataOlderThanDays 10

</div>

<span> </span>

</div>

</div>

</div>

