---
title: PurgeSettings 테이블 (체감 품질)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
description: PurgeSettings 테이블에는 체감 품질 데이터베이스에서 오래 된 경력 품질 레코드가 자동으로 삭제 되는지 여부를 지정 하는 정보가 포함 되어 있습니다. 다음 명령을 실행 하 여 비즈니스용 Skype 서버 관리 셸에서 제거 관련 정보를 얻을 수도 있습니다.
ms.openlocfilehash: dab1b2ffeab5882d0e459d7957b2817e780fc3a4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807336"
---
# <a name="purgesettings-table-qoe"></a><span data-ttu-id="b816f-104">PurgeSettings 테이블 (체감 품질)</span><span class="sxs-lookup"><span data-stu-id="b816f-104">PurgeSettings table (QoE)</span></span>
 
<span data-ttu-id="b816f-105">PurgeSettings 테이블에는 체감 품질 데이터베이스에서 오래 된 경력 품질 레코드가 자동으로 삭제 되는지 여부를 지정 하는 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b816f-105">The PurgeSettings table contains information that specifies if (and when) outdated Quality of Experience records will automatically be deleted from the QoE database.</span></span> <span data-ttu-id="b816f-106">다음 명령을 실행 하 여 비즈니스용 Skype 서버 관리 셸에서 제거 관련 정보를 얻을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b816f-106">Note that purging-related information can also be obtained from within the Skype for Business Server Management Shell by running the following command:</span></span>
  
```PowerShell
Get-CsQoEConfiguration
```

<span data-ttu-id="b816f-107">이 표는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b816f-107">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="b816f-108">**열**</span><span class="sxs-lookup"><span data-stu-id="b816f-108">**Column**</span></span>|<span data-ttu-id="b816f-109">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="b816f-109">**Data Type**</span></span>|<span data-ttu-id="b816f-110">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="b816f-110">**Key/Index**</span></span>|<span data-ttu-id="b816f-111">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="b816f-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b816f-112">**I**</span><span class="sxs-lookup"><span data-stu-id="b816f-112">**ID**</span></span> <br/> |<span data-ttu-id="b816f-113">int</span><span class="sxs-lookup"><span data-stu-id="b816f-113">int</span></span>  <br/> |<span data-ttu-id="b816f-114">주요한</span><span class="sxs-lookup"><span data-stu-id="b816f-114">Primary</span></span>  <br/> |<span data-ttu-id="b816f-115">체감 품질 purge 설정 컬렉션의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="b816f-115">Unique identifier for the collection of QoE purge settings.</span></span>  <br/> |
|<span data-ttu-id="b816f-116">**EnablePurge**</span><span class="sxs-lookup"><span data-stu-id="b816f-116">**EnablePurge**</span></span> <br/> |<span data-ttu-id="b816f-117">다소</span><span class="sxs-lookup"><span data-stu-id="b816f-117">bit</span></span>  <br/> ||<span data-ttu-id="b816f-118">True (1)로 설정 하면 Microsoft Lync Server 2013 체감 품질 데이터베이스에서 오래 된 레코드가 주기적으로 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b816f-118">When set to True (1) Microsoft Lync Server 2013 will periodically purge outdated records from the QoE database.</span></span> <span data-ttu-id="b816f-119">제거는 PurgeHour 설정으로 지정 된 상투메 매일 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b816f-119">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="b816f-120">False로 설정 된 경우 레코드가 데이터베이스에서 자동으로 제거 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b816f-120">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="b816f-121">기본값은 True입니다.</span><span class="sxs-lookup"><span data-stu-id="b816f-121">The default value is True.</span></span>  <br/> |
|<span data-ttu-id="b816f-122">**KeepQoEDataForDays**</span><span class="sxs-lookup"><span data-stu-id="b816f-122">**KeepQoEDataForDays**</span></span> <br/> |<span data-ttu-id="b816f-123">int</span><span class="sxs-lookup"><span data-stu-id="b816f-123">int</span></span>  <br/> ||<span data-ttu-id="b816f-124">데이터베이스에서 삭제 되는 체감 품질 레코드의 기간 (일)을 지정 합니다. 제거를 사용 하는 경우이 값 보다 오래 된 체감 품질 레코드는 데이터베이스에서 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b816f-124">Specifies the age of QoE records (in days) that will be purged from the database: if purging is enabled, QoE records older than this value will be removed from the database.</span></span> <span data-ttu-id="b816f-125">기본값은 60 일입니다.</span><span class="sxs-lookup"><span data-stu-id="b816f-125">The default value is 60 days.</span></span>  <br/> |
|<span data-ttu-id="b816f-126">**PurgeHour**</span><span class="sxs-lookup"><span data-stu-id="b816f-126">**PurgeHour**</span></span> <br/> |<span data-ttu-id="b816f-127">int</span><span class="sxs-lookup"><span data-stu-id="b816f-127">int</span></span>  <br/> ||<span data-ttu-id="b816f-128">데이터베이스 제거를 수행할 현지 시간을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b816f-128">Specifies the local time of day when database purging will take place.</span></span> <span data-ttu-id="b816f-129">시간은 24시간제를 사용하여 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b816f-129">The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM.</span></span> <span data-ttu-id="b816f-130">일의 시간만 지정할 수 있음: 값 10 (10:00 AM)은 허용 되지만 10.5의 10:30의 값 (10:30 AM을 나타냄)은 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b816f-130">Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed.</span></span> <span data-ttu-id="b816f-131">기본값은 1 (1:00 AM)입니다.</span><span class="sxs-lookup"><span data-stu-id="b816f-131">The default value is 1 (1:00 AM).</span></span> <span data-ttu-id="b816f-132">데이터베이스 제거를 수행할 현지 시간을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b816f-132">Specifies the local time of day when database purging will take place.</span></span> <span data-ttu-id="b816f-133">시간은 24시간제를 사용하여 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b816f-133">The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM.</span></span> <span data-ttu-id="b816f-134">일의 시간만 지정할 수 있음: 값 10 (10:00 AM)은 허용 되지만 10.5의 10:30의 값 (10:30 AM을 나타냄)은 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b816f-134">Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed.</span></span> <span data-ttu-id="b816f-135">기본값은 1 (1:00 AM)입니다.</span><span class="sxs-lookup"><span data-stu-id="b816f-135">The default value is 1 (1:00 AM).</span></span>  <br/> |
   

