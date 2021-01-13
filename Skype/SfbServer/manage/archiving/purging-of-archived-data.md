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
# <a name="manage-purging-of-archived-data-in-skype-for-business-server"></a><span data-ttu-id="70530-103">비즈니스용 Skype 서버에서 보관된 데이터 삭제 관리</span><span class="sxs-lookup"><span data-stu-id="70530-103">Manage purging of archived data in Skype for Business Server</span></span>

<span data-ttu-id="70530-104">**요약:** 비즈니스용 Skype 서버의 보관된 데이터 삭제를 관리하는 방법을 자세히 알아보고,</span><span class="sxs-lookup"><span data-stu-id="70530-104">**Summary:** Learn how to manage purging of archived data for Skype for Business Server.</span></span>
  
<span data-ttu-id="70530-105">보관 데이터베이스는 장기 보존용이 아니며, 비즈니스용 Skype 서버는 보관된 데이터에 대한 전자 검색(검색) 솔루션을 제공하지 않습니다. 따라서 데이터를 다른 저장소로 이동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70530-105">The Archiving database is not intended for long-term retention, and Skype for Business Server does not provide an e-discovery (search) solution for archived data, so data needs to be moved to other storage.</span></span> <span data-ttu-id="70530-106">비즈니스용 Skype 서버는 보관된 데이터를 검색 가능한 기록으로 내보내는 데 사용할 수 있는 세션 내보내기 도구를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="70530-106">Skype for Business Server provides a session export tool that you can use to export archived data into searchable transcripts.</span></span> <span data-ttu-id="70530-107">보관된 데이터와 내보낼 데이터를 삭제하는 경우를 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70530-107">You need to define when to purge archived and exported data.</span></span> 
  
<span data-ttu-id="70530-108">**Export-CsArchivingData** cmdlet을 사용하여 데이터를 내보내는 데 대한 자세한 내용은 비즈니스용 Skype 서버에서 보관된 데이터 내보내기를 [참조하세요.](export-archived-data.md)</span><span class="sxs-lookup"><span data-stu-id="70530-108">For more information about exporting data by using the **Export-CsArchivingData** cmdlet, see [Export archived data in Skype for Business Server](export-archived-data.md).</span></span>
  
## <a name="manage-purging-of-data-by-using-the-control-panel"></a><span data-ttu-id="70530-109">제어판을 사용하여 데이터 제거 관리</span><span class="sxs-lookup"><span data-stu-id="70530-109">Manage purging of data by using the Control Panel</span></span>

<span data-ttu-id="70530-110">제어판을 사용하여 보관된 데이터 삭제를 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="70530-110">To manage purging of archived data by using the Control Panel:</span></span>
  
1. <span data-ttu-id="70530-111">CsArchivingAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="70530-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="70530-112">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="70530-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="70530-113">왼쪽 탐색 모음에서 **모니터링 및 보관** 을 클릭하고 **보관 구성** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="70530-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="70530-114">보관 구성 목록에서 적절한 전역, 사이트 또는 풀 구성의 이름을 클릭하고 **편집** 을 클릭한 후에 **자세한 정보 표시** 를 클릭하고 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="70530-114">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
   - <span data-ttu-id="70530-115">삭제를 사용하도록 설정하려면 **보관 데이터 삭제 사용** 확인란을 선택하고 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="70530-115">To enable purging, select the **Enable purging of archiving data** check box and then do one of the following:</span></span>
    
     - <span data-ttu-id="70530-116">모든 레코드를 삭제하려면 **내보낸 보관 데이터 및 최대 기간(일)이 지난 저장된 보관 데이터 삭제** 를 클릭하고 기간(일)을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="70530-116">To purge all records, click the **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
     - <span data-ttu-id="70530-117">내보낸 데이터만 삭제하려면 **내보낸 보관 데이터만 삭제** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="70530-117">To purge only the data that has been exported, click **Purge exported archiving data only**.</span></span>
    
   - <span data-ttu-id="70530-118">삭제를 사용하지 않도록 설정하려면 **보관 데이터 삭제 사용** 확인란 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="70530-118">To disable purging, clear the **Enable purging of archiving data** check box.</span></span>
    
5. <span data-ttu-id="70530-119">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="70530-119">Click **Commit**.</span></span>
    
## <a name="manage-purging-of-data-by-using-windows-powershell"></a><span data-ttu-id="70530-120">데이터를 사용하여 데이터 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="70530-120">Manage purging of data by using Windows PowerShell</span></span>

<span data-ttu-id="70530-121">다음 cmdlet을 사용하여 보관된 데이터 삭제를 관리할 Windows PowerShell 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70530-121">You can manage purging of archived data by using the following Windows PowerShell cmdlets:</span></span>
  
- <span data-ttu-id="70530-122">EnablePurging 매개 변수가 있는 **Set-CsArchivingConfiguration** cmdlet을 사용하면 보관된 데이터 삭제를 활성화하거나 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70530-122">**Set-CsArchivingConfiguration** cmdlet with the EnablePurging parameter lets you enable or disable purging of archived data.</span></span>
    
- <span data-ttu-id="70530-123">**Invoke-CsArchivingDatabasePurge를** 사용하면 보관 데이터베이스에서 레코드를 수동으로 지우는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="70530-123">**Invoke-CsArchivingDatabasePurge** lets you manually purge records from the Archiving database.</span></span>
    
<span data-ttu-id="70530-124">예를 들어 다음 명령은 보관된 모든 데이터를 지우는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70530-124">For example, the following command enables the purging of all archived data.</span></span> <span data-ttu-id="70530-125">이 명령을 실행하면 비즈니스용 Skype 서버는 KeepArchivingDataForDays 매개 변수에 지정된 값보다 오래된 모든 보관 레코드를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="70530-125">After this command is run, Skype for Business Server will purge all archiving records older than the value specified for the KeepArchivingDataForDays parameter.</span></span> 
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
```

<span data-ttu-id="70530-126">다음 명령은 **Export-CSArchivingData** cmdlet을 사용하여 데이터 파일로 내보냈던 보관된 레코드의 삭제를 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="70530-126">The following command limits purging to archived records that have been exported to a data file (by using the **Export-CSArchivingData** cmdlet).</span></span> <span data-ttu-id="70530-127">PurgeExportedArchivesOnly 매개 변수도 True($True).</span><span class="sxs-lookup"><span data-stu-id="70530-127">You must also set the PurgeExportedArchivesOnly parameter to True ($True):</span></span>
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
```

<span data-ttu-id="70530-128">이 명령을 실행하면 비즈니스용 Skype 서버는 두 가지 조건, 즉 1) KeepArchivingDataForDays 매개 변수에 지정된 값보다 오래된 보관 레코드만 제거합니다. 2) **Export-CsArchivingData** cmdlet을 사용하여 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70530-128">After this command is run, Skype for Business Server will only purge archiving records that meet two criteria: 1) they are older than the value specified for the KeepArchivingDataForDays parameter; and, 2) they have been exported by using the **Export-CsArchivingData** cmdlet.</span></span>
  
<span data-ttu-id="70530-129">보관 레코드의 자동 제거를 사용하지 않도록 설정하려면 EnablePurging 매개 변수를 False($False).</span><span class="sxs-lookup"><span data-stu-id="70530-129">To disable the automated purging of archiving records, set the EnablePurging parameter to False ($False):</span></span>
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False
```

<span data-ttu-id="70530-130">다음 예제에서는 **Invoke-CsArchivingDatabasePurge** cmdlet을 사용하여 24시간보다 오래된 모든 레코드를 보관 데이터베이스에서 atl-sql-001.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="70530-130">The following example uses the **Invoke-CsArchivingDatabasePurge** cmdlet to purge all the records more than 24 hours old from the archiving database on atl-sql-001.contoso.com.</span></span> <span data-ttu-id="70530-131">내보낼 수 없는 레코드를 포함하여 모든 레코드가 삭제되도록 PurgeExportedArchivesOnly 매개 변수는 False($False).</span><span class="sxs-lookup"><span data-stu-id="70530-131">To ensure that all the records are deleted, including records that have not been exported, the PurgeExportedArchivesOnly parameter is set to False ($False):</span></span>
  
```PowerShell
Invoke-CsArchivingDatabasePurge -Identity "service:ArchivingDatabase:atl-sql-001.contoso.com" -PurgeArchivingDataOlderThanHours 24 -PurgeExportedArchivesOnly $False
```
