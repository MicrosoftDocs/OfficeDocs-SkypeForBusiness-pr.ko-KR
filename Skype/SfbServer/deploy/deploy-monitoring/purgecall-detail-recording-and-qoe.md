---
title: 비즈니스용 Skype 서버에서 통화 정보 기록 및 경력 데이터베이스의 품질을 수동으로 제거
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3a3a965b-b861-41a4-b9a8-27184d622c17
description: '요약: CDR 및 비즈니스용 Skype 서버에서 사용 하는 체감 품질 데이터베이스의 레코드를 수동으로 제거 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: c995611704c2fed04461da0b311e8a4141fc4908
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189468"
---
# <a name="manually-purge-the-call-detail-recording-and-quality-of-experience-databases-in-skype-for-business-server"></a><span data-ttu-id="54260-103">비즈니스용 Skype 서버에서 통화 정보 기록 및 경력 데이터베이스의 품질을 수동으로 제거</span><span class="sxs-lookup"><span data-stu-id="54260-103">Manually purge the call detail recording and Quality of Experience databases in Skype for Business Server</span></span>
 
<span data-ttu-id="54260-104">**요약:** 비즈니스용 Skype 서버에서 사용 하는 체감 품질 데이터베이스와 CDR의 레코드를 수동으로 제거 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="54260-104">**Summary:** Learn how to manually purge records from the CDR and the QoE databases used by Skype for Business Server.</span></span>
  
<span data-ttu-id="54260-105">CDR 및 체감 품질 데이터베이스는 수동으로 또는 레코드를 자동으로 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54260-105">The CDR and QoE databases can be manually or automatically purged of records.</span></span> <span data-ttu-id="54260-106">레코드 제거는 데이터가 쓸모 없게 되거나 시작 기준선에서 보고서를 다시 설정 해야 하는 경우에 중요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54260-106">Purging records can be important so that data doesn't become stale or when needing to reset reports from a starting baseline.</span></span>
  
## <a name="manually-purge-records-from-cdr-and-qoe-databases"></a><span data-ttu-id="54260-107">CDR 및 체감 품질 데이터베이스에서 수동으로 레코드 제거</span><span class="sxs-lookup"><span data-stu-id="54260-107">Manually purge records from CDR and QoE databases</span></span>

<span data-ttu-id="54260-108">관리자는 데이터베이스에서 오래 된 레코드를 자동으로 제거 하도록 체감 품질 (통화 정보 기록) 및/또는 환경 (경력 품질) 데이터베이스를 구성할 수 있습니다. 지정 된 데이터베이스 (CDR 또는 체감 품질)에 대 한 제거가 설정 되어 있고 데이터베이스에 지정 된 시간 보다 오래 된 레코드가 있는 경우이 문제가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="54260-108">Administrators can configure the Call Detail Recording (CDR) and/or the Quality of Experience (QoE) databases to automatically purge old records from the database; this occurs if purging has been enabled for the specified database (CDR or QoE) and if there are any records that have been in the database longer than the specified amount of time.</span></span> <span data-ttu-id="54260-109">예를 들어 매일 1:00 AM 관리자는 60 일이 지난 체감 품질 레코드가 체감 품질 데이터베이스에서 삭제 되도록 시스템을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54260-109">For example, every day at 1:00 AM administrators might configure the system so that QoE records more than 60 days old will be deleted from the QoE database.</span></span>
  
<span data-ttu-id="54260-110">이러한 자동 제거 외에도 CsCdrDatabasePurge 및 Invoke를 호출 하는 두 개의 새로운 &#x2014; cmdlet 인-CsQoEDatbasePurge &#x2014; 비즈니스용 Skype 서버에 추가 되었습니다. 관리자는 이러한 cmdlet을 사용 하 여 언제 든 지 CDR 및 체감 품질 데이터베이스에서 레코드를 수동으로 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54260-110">In addition to that automatic purging, two new cmdlets &#x2014; Invoke-CsCdrDatabasePurge and Invoke-CsQoEDatbasePurge &#x2014; have been added to Skype for Business Server; these cmdlets allow administrators to manually purge records from the CDR and the QoE databases at any time.</span></span> <span data-ttu-id="54260-111">예를 들어, CDR 데이터베이스에서 10 일 이상 지난 모든 레코드를 수동으로 제거 하려면 다음과 같은 명령을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54260-111">For example, to manually purge all the records more than 10 days old from the CDR database you can use a command similar to this:</span></span>
  
```
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10
```

<span data-ttu-id="54260-112">앞의 명령에서 10 일 보다 오래 된 통화 정보 레코드 및 진단 데이터 레코드는 모두 atl-sql-001.litwareinc.com의 모니터링 데이터베이스에서 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54260-112">In the preceding command both call detail records and diagnostic data records older than 10 days are deleted from the monitoring database on atl-sql-001.litwareinc.com.</span></span> <span data-ttu-id="54260-113">(통화 정보 레코드는 사용자/세션 보고서입니다.</span><span class="sxs-lookup"><span data-stu-id="54260-113">(Call detail records are user/session reports.</span></span> <span data-ttu-id="54260-114">진단 데이터 레코드는 비즈니스용 Skype 서버와 같은 클라이언트 응용 프로그램에서 업로드 한 진단 로그입니다.</span><span class="sxs-lookup"><span data-stu-id="54260-114">Diagnostic data records are diagnostic logs uploaded by client applications such as Skype for Business Server.)</span></span>
  
<span data-ttu-id="54260-115">위의 그림과 같이 CsCdrDatabasePurge cmdlet을 실행 하는 경우에는 PurgeCallDetaiDataOlderThanDays 및 PurgeDiagnosticDataOlderThanDays 매개 변수를 둘 다 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="54260-115">As shown above, when you run the Invoke-CsCdrDatabasePurge cmdlet you must include both the PurgeCallDetaiDataOlderThanDays and the PurgeDiagnosticDataOlderThanDays parameters.</span></span> <span data-ttu-id="54260-116">그러나 이러한 매개 변수를 같은 값으로 설정할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="54260-116">However, these parameters do not have to be set to the same value.</span></span> <span data-ttu-id="54260-117">예를 들어 10 일 이상 지난 통화 정보 레코드를 제거 하 고 동시에 모든 진단 데이터 레코드를 데이터베이스에 남길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54260-117">For example, it's possible to purge call detail records more than 10 days old and yet, at the same time, leave all the diagnostic data records in the database.</span></span> <span data-ttu-id="54260-118">이 작업을 수행 하려면 PurgeCallDetailDataOlderThanDays를 10으로, PurgeDiagnosticDataOlderThanDays를 0으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="54260-118">To do that, set PurgeCallDetailDataOlderThanDays to 10 and PurgeDiagnosticDataOlderThanDays to 0.</span></span> <span data-ttu-id="54260-119">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="54260-119">For example:</span></span>
  
```
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 0
```

<span data-ttu-id="54260-120">기본적으로 CsCdrDatabasePurge를 실행할 때마다 제거 해야 하는 각 데이터베이스 테이블에 대해 다음과 비슷한 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54260-120">By default, any time you run Invoke-CsCdrDatabasePurge you will see a prompt similar to this one for each database table that must be purged:</span></span>
  
<pre>
Confirm
Are you sure you want to perform this action?
Performing operation "Stored procedure: RtcCleanupDiag" on Target "Target SQL Server:atl-sql-001.litwareinc.com\archinst Database: lcscdr".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All [S] Suspend  [?] Help (default is "Y"):
</pre>

<span data-ttu-id="54260-121">데이터베이스 제거를 실제로 수행 하기 전에 Y (Yes) 또는 A (Yes에 대해)를 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="54260-121">You must type either Y (for Yes) or A (for Yes to All) before the database purging will actually take place.</span></span> <span data-ttu-id="54260-122">이러한 확인 메시지를 표시 하지 않으려면 CsCdrDatabasePurge 호출에 대 한 통화 종료에 다음 매개 변수를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="54260-122">If you would prefer to suppress these confirmation prompts, add the following parameter to the end of your call to Invoke-CsCdrDatabasePurge:</span></span>
  
```
-Confirm:$False
```

<span data-ttu-id="54260-123">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="54260-123">For example:</span></span>
  
```
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False
```

<span data-ttu-id="54260-124">이렇게 하면 확인 메시지가 표시 되지 않으며 데이터베이스 제거가 즉시 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54260-124">If you do that, confirmation prompts will not be displayed, and database purging will immediately be performed.</span></span>
  
<span data-ttu-id="54260-125">체감 품질 데이터베이스를 제거 하려면 Invoke-CsQoEDatabasePurge cmdlet을 사용 하 고 삭제할 레코드의 보존 기간 (일)을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="54260-125">To purge the QoE database, use the Invoke-CsQoEDatabasePurge cmdlet and specify the age (in days) of the records to be deleted:</span></span>
  
```
Invoke-CsQoEDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeQoEDataOlderThanDays 10
```


