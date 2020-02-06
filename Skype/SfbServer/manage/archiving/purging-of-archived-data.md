---
title: 비즈니스용 Skype 서버에서 보관 된 데이터 제거 관리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 14c2b4fd-f612-4909-808d-09c655fc9f8a
description: '요약: 비즈니스용 Skype 서버의 보관 된 데이터 제거를 관리 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 7953c6085183e3ace0e395f0c8751897acd49380
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818880"
---
# <a name="manage-purging-of-archived-data-in-skype-for-business-server"></a><span data-ttu-id="941f5-103">비즈니스용 Skype 서버에서 보관 된 데이터 제거 관리</span><span class="sxs-lookup"><span data-stu-id="941f5-103">Manage purging of archived data in Skype for Business Server</span></span>

<span data-ttu-id="941f5-104">**요약:** 비즈니스용 Skype 서버의 보관 된 데이터 제거를 관리 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="941f5-104">**Summary:** Learn how to manage purging of archived data for Skype for Business Server.</span></span>
  
<span data-ttu-id="941f5-105">보관 데이터베이스는 장기 보존을 위한 것이 아니며 비즈니스용 Skype 서버는 보관 된 데이터에 대 한 e-검색 (검색) 솔루션을 제공 하지 않으므로 데이터를 다른 저장소로 옮겨야 합니다.</span><span class="sxs-lookup"><span data-stu-id="941f5-105">The Archiving database is not intended for long-term retention, and Skype for Business Server does not provide an e-discovery (search) solution for archived data, so data needs to be moved to other storage.</span></span> <span data-ttu-id="941f5-106">비즈니스용 Skype Server는 보관 된 데이터를 검색 가능한 내용으로 내보내는 데 사용할 수 있는 세션 내보내기 도구를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="941f5-106">Skype for Business Server provides a session export tool that you can use to export archived data into searchable transcripts.</span></span> <span data-ttu-id="941f5-107">보관 하 고 내보낸 데이터를 지울 시기를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="941f5-107">You need to define when to purge archived and exported data.</span></span> 
  
<span data-ttu-id="941f5-108">**Export-CsArchivingData** cmdlet을 사용 하 여 데이터를 내보내는 방법에 대 한 자세한 내용은 비즈니스용 [Skype 서버에서 보관 된 데이터 내보내기를](export-archived-data.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="941f5-108">For more information about exporting data by using the **Export-CsArchivingData** cmdlet, see [Export archived data in Skype for Business Server](export-archived-data.md).</span></span>
  
## <a name="manage-purging-of-data-by-using-the-control-panel"></a><span data-ttu-id="941f5-109">제어판을 사용 하 여 데이터 지우기 관리</span><span class="sxs-lookup"><span data-stu-id="941f5-109">Manage purging of data by using the Control Panel</span></span>

<span data-ttu-id="941f5-110">제어판을 사용 하 여 보관 된 데이터의 제거를 관리 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="941f5-110">To manage purging of archived data by using the Control Panel:</span></span>
  
1. <span data-ttu-id="941f5-111">CsArchivingAdministrator 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="941f5-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="941f5-112">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="941f5-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="941f5-113">왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭 한 다음 **구성 보관**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="941f5-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="941f5-114">보관 구성 목록에서 적절 한 전역, 사이트 또는 풀 구성의 이름을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 하 고 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="941f5-114">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
   - <span data-ttu-id="941f5-115">제거를 사용 하도록 설정 하려면 **데이터 보관 제거 사용** 확인란을 선택 하 고 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="941f5-115">To enable purging, select the **Enable purging of archiving data** check box and then do one of the following:</span></span>
    
     - <span data-ttu-id="941f5-116">모든 레코드를 제거 하려면 **내보낸 데이터 보관 및 저장 된 최대 기간 (일)** 을 클릭 한 다음 일 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="941f5-116">To purge all records, click the **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
     - <span data-ttu-id="941f5-117">내보낸 데이터만 제거 하려면 **내보낸 데이터 보관만 삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="941f5-117">To purge only the data that has been exported, click **Purge exported archiving data only**.</span></span>
    
   - <span data-ttu-id="941f5-118">제거를 사용 하지 않도록 설정 하려면 **데이터 보관 제거 사용** 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="941f5-118">To disable purging, clear the **Enable purging of archiving data** check box.</span></span>
    
5. <span data-ttu-id="941f5-119">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="941f5-119">Click **Commit**.</span></span>
    
## <a name="manage-purging-of-data-by-using-windows-powershell"></a><span data-ttu-id="941f5-120">Windows PowerShell을 사용 하 여 데이터 지우기 관리</span><span class="sxs-lookup"><span data-stu-id="941f5-120">Manage purging of data by using Windows PowerShell</span></span>

<span data-ttu-id="941f5-121">다음 Windows PowerShell cmdlet을 사용 하 여 보관 된 데이터 제거를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="941f5-121">You can manage purging of archived data by using the following Windows PowerShell cmdlets:</span></span>
  
- <span data-ttu-id="941f5-122">EnablePurging 매개 변수를 사용 하 여 **CsArchivingConfiguration** cmdlet을 사용 하 여 보관 된 데이터의 제거를 설정 하거나 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="941f5-122">**Set-CsArchivingConfiguration** cmdlet with the EnablePurging parameter lets you enable or disable purging of archived data.</span></span>
    
- <span data-ttu-id="941f5-123">**-CsArchivingDatabasePurge를 호출** 하면 보관 데이터베이스에서 레코드를 수동으로 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="941f5-123">**Invoke-CsArchivingDatabasePurge** lets you manually purge records from the Archiving database.</span></span>
    
<span data-ttu-id="941f5-124">예를 들어 다음 명령을 사용 하 여 아카이브된 모든 데이터를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="941f5-124">For example, the following command enables the purging of all archived data.</span></span> <span data-ttu-id="941f5-125">이 명령을 실행 한 후 비즈니스용 Skype Server는 KeepArchivingDataForDays 매개 변수에 지정 된 값 보다 오래 된 모든 보관 레코드를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="941f5-125">After this command is run, Skype for Business Server will purge all archiving records older than the value specified for the KeepArchivingDataForDays parameter.</span></span> 
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
```

<span data-ttu-id="941f5-126">다음 명령은 **내보내기-CSArchivingData** cmdlet을 사용 하 여 데이터 파일로 내보낸 보관 된 레코드로의 제거를 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="941f5-126">The following command limits purging to archived records that have been exported to a data file (by using the **Export-CSArchivingData** cmdlet).</span></span> <span data-ttu-id="941f5-127">또한 PurgeExportedArchivesOnly 매개 변수를 True ($True)로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="941f5-127">You must also set the PurgeExportedArchivesOnly parameter to True ($True):</span></span>
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
```

<span data-ttu-id="941f5-128">이 명령을 실행 한 후 비즈니스용 Skype 서버는 두 개의 조건을 충족 하는 보관 레코드만을 제거 합니다. 1) KeepArchivingDataForDays 매개 변수에 지정 된 값 보다 오래 된 것입니다. and, 2) **CsArchivingData** cmdlet을 사용 하 여 내보내기를 완료 했습니다.</span><span class="sxs-lookup"><span data-stu-id="941f5-128">After this command is run, Skype for Business Server will only purge archiving records that meet two criteria: 1) they are older than the value specified for the KeepArchivingDataForDays parameter; and, 2) they have been exported by using the **Export-CsArchivingData** cmdlet.</span></span>
  
<span data-ttu-id="941f5-129">기록 보관의 자동 제거를 사용 하지 않도록 설정 하려면 EnablePurging 매개 변수를 False ($False)로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="941f5-129">To disable the automated purging of archiving records, set the EnablePurging parameter to False ($False):</span></span>
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False
```

<span data-ttu-id="941f5-130">다음 예제에서는 **CsArchivingDatabasePurge** cmdlet을 사용 하 여 atl-sql-001.contoso.com의 보관 데이터베이스에서 24 시간 이상 오래 된 레코드를 모두 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="941f5-130">The following example uses the **Invoke-CsArchivingDatabasePurge** cmdlet to purge all the records more than 24 hours old from the archiving database on atl-sql-001.contoso.com.</span></span> <span data-ttu-id="941f5-131">내보내지지 않은 레코드를 포함 하 여 모든 레코드가 삭제 되도록 PurgeExportedArchivesOnly 매개 변수가 False ($False)로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="941f5-131">To ensure that all the records are deleted, including records that have not been exported, the PurgeExportedArchivesOnly parameter is set to False ($False):</span></span>
  
```PowerShell
Invoke-CsArchivingDatabasePurge -Identity "service:ArchivingDatabase:atl-sql-001.contoso.com" -PurgeArchivingDataOlderThanHours 24 -PurgeExportedArchivesOnly $False
```
