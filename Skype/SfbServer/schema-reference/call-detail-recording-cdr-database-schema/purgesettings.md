---
title: PurgeSettings 테이블
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9ff2c8fc-4ae8-4f22-96a8-1f4d5eecbf2d
description: PurgeSettings 테이블에는 오래된 통화 정보 기록을 CDR 데이터베이스에서 자동으로 삭제할지 여부 및 시기를 지정하는 정보가 포함됩니다. 다음 명령을 실행하여 비즈니스용 Skype 서버 2015 내에서도 제거 관련 정보를 얻을 수 있습니다.
ms.openlocfilehash: c90c36dc91eaaac6fe38c6eea8e2a5617264e200
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823168"
---
# <a name="purgesettings-table"></a><span data-ttu-id="bc821-104">PurgeSettings 테이블</span><span class="sxs-lookup"><span data-stu-id="bc821-104">PurgeSettings table</span></span>
 
<span data-ttu-id="bc821-105">PurgeSettings 테이블에는 오래된 통화 정보 기록을 CDR 데이터베이스에서 자동으로 삭제할지 여부 및 시기를 지정하는 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc821-105">The PurgeSettings table contains information that specifies if (and when) outdated call detail records will automatically be deleted from the CDR database.</span></span> <span data-ttu-id="bc821-106">다음 명령을 실행하여 비즈니스용 Skype 서버 2015 내에서도 제거 관련 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc821-106">Note that purging-related information can also be obtained from within the Skype for Business Server 2015 by running the following command:</span></span>
  
```PowerShell
Get-CsCdrConfiguration
```

<span data-ttu-id="bc821-107">관리자는 PurgeSettings 테이블을 읽기 전용으로 처리해야 합니다. 통화 정보 삭제 설정은 [New-CsCdrConfiguration 또는 Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) cmdlet을 사용하여만 변경해야 합니다. [](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="bc821-107">Administrators should treat the PurgeSettings table as read-only: changes to the call detail purge settings should only be made using the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) or [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlets.</span></span>
  
<span data-ttu-id="bc821-108">이 표는 Microsoft Lync Server 2013에서 도입된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bc821-108">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="bc821-109">**열**</span><span class="sxs-lookup"><span data-stu-id="bc821-109">**Column**</span></span>|<span data-ttu-id="bc821-110">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="bc821-110">**Data Type**</span></span>|<span data-ttu-id="bc821-111">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="bc821-111">**Key/Index**</span></span>|<span data-ttu-id="bc821-112">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="bc821-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bc821-113">**Id**</span><span class="sxs-lookup"><span data-stu-id="bc821-113">**Id**</span></span> <br/> |<span data-ttu-id="bc821-114">int</span><span class="sxs-lookup"><span data-stu-id="bc821-114">int</span></span>  <br/> |<span data-ttu-id="bc821-115">Primary</span><span class="sxs-lookup"><span data-stu-id="bc821-115">Primary</span></span>  <br/> |<span data-ttu-id="bc821-116">CDR 삭제 설정 컬렉션에 대한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="bc821-116">Unique identifier for the collection of CDR purge settings.</span></span>  <br/> |
|<span data-ttu-id="bc821-117">**EnablePurge**</span><span class="sxs-lookup"><span data-stu-id="bc821-117">**EnablePurge**</span></span> <br/> |<span data-ttu-id="bc821-118">bit</span><span class="sxs-lookup"><span data-stu-id="bc821-118">bit</span></span>  <br/> ||<span data-ttu-id="bc821-119">True(1)로 설정하면 비즈니스용 Skype 서버 2015가 CDR 데이터베이스에서 기한이 지난 레코드를 주기적으로 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="bc821-119">When set to True (1) Skype for Business Server 2015 will periodically purge outdated records from the CDR database.</span></span> <span data-ttu-id="bc821-120">삭제는 매일 PurgeHour 설정으로 지정된 시간에 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc821-120">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="bc821-121">False(0)로 설정하면 레코드가 데이터베이스에서 자동으로 삭제되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bc821-121">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="bc821-122">기본값은 True입니다.</span><span class="sxs-lookup"><span data-stu-id="bc821-122">The default value is True.</span></span>  <br/> |
|<span data-ttu-id="bc821-123">**KeepCallDetailForDays**</span><span class="sxs-lookup"><span data-stu-id="bc821-123">**KeepCallDetailForDays**</span></span> <br/> |<span data-ttu-id="bc821-124">int</span><span class="sxs-lookup"><span data-stu-id="bc821-124">int</span></span>  <br/> ||<span data-ttu-id="bc821-p104">데이터베이스에서 삭제할 CDR 레코드의 기간(일)을 지정합니다. 삭제를 사용하도록 설정한 경우 이 값보다 오래된 CDR 레코드가 데이터베이스에서 삭제됩니다. 기본값은 60일입니다.</span><span class="sxs-lookup"><span data-stu-id="bc821-p104">Specifies the age of CDR records (in days) that will be purged from the database: if purging is enabled, CDR records older than this value will be removed from the database. The default value is 60 days.</span></span>  <br/> |
|<span data-ttu-id="bc821-127">**KeepErrorReportForDays**</span><span class="sxs-lookup"><span data-stu-id="bc821-127">**KeepErrorReportForDays**</span></span> <br/> |<span data-ttu-id="bc821-128">int</span><span class="sxs-lookup"><span data-stu-id="bc821-128">int</span></span>  <br/> ||<span data-ttu-id="bc821-p105">데이터베이스에서 삭제할 오류 보고서 레코드의 기간(일)을 지정합니다. 삭제를 사용하도록 설정한 경우 이 값보다 오래된 오류 보고서 레코드가 데이터베이스에서 삭제됩니다. 기본값은 60일입니다.</span><span class="sxs-lookup"><span data-stu-id="bc821-p105">Specifies the age of error report records (in days) that will be purged from the database: if purging is enabled, error report records older than this value will be removed from the database. The default value is 60 days.</span></span>  <br/> |
|<span data-ttu-id="bc821-131">**PurgeHour**</span><span class="sxs-lookup"><span data-stu-id="bc821-131">**PurgeHour**</span></span> <br/> |<span data-ttu-id="bc821-132">int</span><span class="sxs-lookup"><span data-stu-id="bc821-132">int</span></span>  <br/> ||<span data-ttu-id="bc821-p106">데이터베이스 삭제가 수행되는 현지 시간을 지정합니다. 시간은 24시간제를 사용하여 지정합니다. 0은 자정(오전 12:00)을 나타내고 23은 오후 11:00를 나타냅니다. 시간만 지정할 수 있습니다. 즉, 값으로 10(오전 10:00)은 사용할 수는 있지만, 10:30 또는 10.5(오전 10:30)는 사용할 수 없습니다. 기본값은 2(오전 2:00)입니다.</span><span class="sxs-lookup"><span data-stu-id="bc821-p106">Specifies the local time of day when database purging will take place. The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM. Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed. The default value is 2 (2:00 AM).</span></span>  <br/> |
   

