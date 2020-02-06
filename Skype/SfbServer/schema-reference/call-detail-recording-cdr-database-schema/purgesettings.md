---
title: PurgeSettings 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9ff2c8fc-4ae8-4f22-96a8-1f4d5eecbf2d
description: PurgeSettings 테이블에는 CDR 데이터베이스에서 오래 된 통화 정보 레코드가 자동으로 삭제 되는지 여부를 지정 하는 정보가 포함 되어 있습니다. 다음 명령을 실행 하 여 비즈니스용 Skype 서버 2015 내에서 제거 관련 정보를 얻을 수도 있습니다.
ms.openlocfilehash: 81e702a4d62b4c85fb849a768c97428719ddc391
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814966"
---
# <a name="purgesettings-table"></a><span data-ttu-id="d7a6f-104">PurgeSettings 테이블</span><span class="sxs-lookup"><span data-stu-id="d7a6f-104">PurgeSettings table</span></span>
 
<span data-ttu-id="d7a6f-105">PurgeSettings 테이블에는 CDR 데이터베이스에서 오래 된 통화 정보 레코드가 자동으로 삭제 되는지 여부를 지정 하는 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7a6f-105">The PurgeSettings table contains information that specifies if (and when) outdated call detail records will automatically be deleted from the CDR database.</span></span> <span data-ttu-id="d7a6f-106">다음 명령을 실행 하 여 비즈니스용 Skype 서버 2015 내에서 제거 관련 정보를 얻을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7a6f-106">Note that purging-related information can also be obtained from within the Skype for Business Server 2015 by running the following command:</span></span>
  
```PowerShell
Get-CsCdrConfiguration
```

<span data-ttu-id="d7a6f-107">관리자는 PurgeSettings 테이블을 읽기 전용으로 처리 해야 합니다. 통화 정보 제거 설정의 변경 사항은 [새로운-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) 또는 [CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet을 사용해 서만 이루어져야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a6f-107">Administrators should treat the PurgeSettings table as read-only: changes to the call detail purge settings should only be made using the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) or [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlets.</span></span>
  
<span data-ttu-id="d7a6f-108">이 표는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d7a6f-108">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="d7a6f-109">**열**</span><span class="sxs-lookup"><span data-stu-id="d7a6f-109">**Column**</span></span>|<span data-ttu-id="d7a6f-110">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="d7a6f-110">**Data Type**</span></span>|<span data-ttu-id="d7a6f-111">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="d7a6f-111">**Key/Index**</span></span>|<span data-ttu-id="d7a6f-112">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="d7a6f-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d7a6f-113">**I**</span><span class="sxs-lookup"><span data-stu-id="d7a6f-113">**Id**</span></span> <br/> |<span data-ttu-id="d7a6f-114">int</span><span class="sxs-lookup"><span data-stu-id="d7a6f-114">int</span></span>  <br/> |<span data-ttu-id="d7a6f-115">주요한</span><span class="sxs-lookup"><span data-stu-id="d7a6f-115">Primary</span></span>  <br/> |<span data-ttu-id="d7a6f-116">CDR 제거 설정 컬렉션의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a6f-116">Unique identifier for the collection of CDR purge settings.</span></span>  <br/> |
|<span data-ttu-id="d7a6f-117">**EnablePurge**</span><span class="sxs-lookup"><span data-stu-id="d7a6f-117">**EnablePurge**</span></span> <br/> |<span data-ttu-id="d7a6f-118">다소</span><span class="sxs-lookup"><span data-stu-id="d7a6f-118">bit</span></span>  <br/> ||<span data-ttu-id="d7a6f-119">True (1)로 설정 된 경우 비즈니스용 Skype Server 2015는 CDR 데이터베이스에서 오래 된 레코드를 주기적으로 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a6f-119">When set to True (1) Skype for Business Server 2015 will periodically purge outdated records from the CDR database.</span></span> <span data-ttu-id="d7a6f-120">제거는 PurgeHour 설정으로 지정 된 상투메 매일 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7a6f-120">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="d7a6f-121">False로 설정 된 경우 레코드가 데이터베이스에서 자동으로 제거 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d7a6f-121">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="d7a6f-122">기본값은 True입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a6f-122">The default value is True.</span></span>  <br/> |
|<span data-ttu-id="d7a6f-123">**KeepCallDetailForDays**</span><span class="sxs-lookup"><span data-stu-id="d7a6f-123">**KeepCallDetailForDays**</span></span> <br/> |<span data-ttu-id="d7a6f-124">int</span><span class="sxs-lookup"><span data-stu-id="d7a6f-124">int</span></span>  <br/> ||<span data-ttu-id="d7a6f-125">데이터베이스에서 제거 되는 CDR 레코드의 보존 기간 (일)을 지정 합니다. 제거를 사용 하는 경우이 값 보다 오래 된 CDR 레코드가 데이터베이스에서 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7a6f-125">Specifies the age of CDR records (in days) that will be purged from the database: if purging is enabled, CDR records older than this value will be removed from the database.</span></span> <span data-ttu-id="d7a6f-126">기본값은 60 일입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a6f-126">The default value is 60 days.</span></span>  <br/> |
|<span data-ttu-id="d7a6f-127">**KeepErrorReportForDays**</span><span class="sxs-lookup"><span data-stu-id="d7a6f-127">**KeepErrorReportForDays**</span></span> <br/> |<span data-ttu-id="d7a6f-128">int</span><span class="sxs-lookup"><span data-stu-id="d7a6f-128">int</span></span>  <br/> ||<span data-ttu-id="d7a6f-129">데이터베이스에서 삭제 되는 오류 보고서 레코드의 기간 (일)을 지정 합니다. 제거를 사용 하는 경우이 값 보다 오래 된 오류 보고서 레코드가 데이터베이스에서 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7a6f-129">Specifies the age of error report records (in days) that will be purged from the database: if purging is enabled, error report records older than this value will be removed from the database.</span></span> <span data-ttu-id="d7a6f-130">기본값은 60 일입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a6f-130">The default value is 60 days.</span></span>  <br/> |
|<span data-ttu-id="d7a6f-131">**PurgeHour**</span><span class="sxs-lookup"><span data-stu-id="d7a6f-131">**PurgeHour**</span></span> <br/> |<span data-ttu-id="d7a6f-132">int</span><span class="sxs-lookup"><span data-stu-id="d7a6f-132">int</span></span>  <br/> ||<span data-ttu-id="d7a6f-133">데이터베이스 제거를 수행할 현지 시간을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a6f-133">Specifies the local time of day when database purging will take place.</span></span> <span data-ttu-id="d7a6f-134">시간은 24시간제를 사용하여 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a6f-134">The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM.</span></span> <span data-ttu-id="d7a6f-135">일의 시간만 지정할 수 있음: 값 10 (10:00 AM)은 허용 되지만 10.5의 10:30의 값 (10:30 AM을 나타냄)은 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d7a6f-135">Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed.</span></span> <span data-ttu-id="d7a6f-136">기본값은 2(오전 2:00)입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a6f-136">The default value is 2 (2:00 AM).</span></span>  <br/> |
   

