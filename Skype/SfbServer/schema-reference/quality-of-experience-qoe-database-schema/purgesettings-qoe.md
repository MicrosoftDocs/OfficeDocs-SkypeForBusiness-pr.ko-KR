---
title: PurgeSettings 테이블(QoE)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
description: PurgeSettings 테이블은 오래된 체감 품질 레코드가 QoE 데이터베이스에서 자동으로 삭제되는지 여부 및 삭제되는 시간을 지정하는 정보를 포함합니다. 다음 명령을 실행하여 비즈니스용 Skype 서버 관리 셸 내에서도 제거 관련 정보를 얻을 수 있습니다.
ms.openlocfilehash: eef723298b04aecf633368d767623488a53ac6ce
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815808"
---
# <a name="purgesettings-table-qoe"></a><span data-ttu-id="f6324-104">PurgeSettings 테이블(QoE)</span><span class="sxs-lookup"><span data-stu-id="f6324-104">PurgeSettings table (QoE)</span></span>
 
<span data-ttu-id="f6324-105">PurgeSettings 테이블은 오래된 체감 품질 레코드가 QoE 데이터베이스에서 자동으로 삭제되는지 여부 및 삭제되는 시간을 지정하는 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="f6324-105">The PurgeSettings table contains information that specifies if (and when) outdated Quality of Experience records will automatically be deleted from the QoE database.</span></span> <span data-ttu-id="f6324-106">다음 명령을 실행하여 비즈니스용 Skype 서버 관리 셸 내에서도 제거 관련 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6324-106">Note that purging-related information can also be obtained from within the Skype for Business Server Management Shell by running the following command:</span></span>
  
```PowerShell
Get-CsQoEConfiguration
```

<span data-ttu-id="f6324-107">이 표는 Microsoft Lync Server 2013에서 도입된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f6324-107">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="f6324-108">**열**</span><span class="sxs-lookup"><span data-stu-id="f6324-108">**Column**</span></span>|<span data-ttu-id="f6324-109">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="f6324-109">**Data Type**</span></span>|<span data-ttu-id="f6324-110">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="f6324-110">**Key/Index**</span></span>|<span data-ttu-id="f6324-111">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="f6324-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f6324-112">**ID**</span><span class="sxs-lookup"><span data-stu-id="f6324-112">**ID**</span></span> <br/> |<span data-ttu-id="f6324-113">int</span><span class="sxs-lookup"><span data-stu-id="f6324-113">int</span></span>  <br/> |<span data-ttu-id="f6324-114">Primary</span><span class="sxs-lookup"><span data-stu-id="f6324-114">Primary</span></span>  <br/> |<span data-ttu-id="f6324-115">QoE 삭제 설정 컬렉션의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="f6324-115">Unique identifier for the collection of QoE purge settings.</span></span>  <br/> |
|<span data-ttu-id="f6324-116">**EnablePurge**</span><span class="sxs-lookup"><span data-stu-id="f6324-116">**EnablePurge**</span></span> <br/> |<span data-ttu-id="f6324-117">bit</span><span class="sxs-lookup"><span data-stu-id="f6324-117">bit</span></span>  <br/> ||<span data-ttu-id="f6324-118">True(1)로 설정하면 Microsoft Lync Server 2013이 QoE 데이터베이스에서 기한이 지난 레코드를 주기적으로 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f6324-118">When set to True (1) Microsoft Lync Server 2013 will periodically purge outdated records from the QoE database.</span></span> <span data-ttu-id="f6324-119">삭제는 매일 PurgeHour 설정으로 지정된 시간에 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6324-119">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="f6324-120">False(0)로 설정하면 레코드가 데이터베이스에서 자동으로 삭제되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f6324-120">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="f6324-121">기본값은 True입니다.</span><span class="sxs-lookup"><span data-stu-id="f6324-121">The default value is True.</span></span>  <br/> |
|<span data-ttu-id="f6324-122">**KeepQoEDataForDays**</span><span class="sxs-lookup"><span data-stu-id="f6324-122">**KeepQoEDataForDays**</span></span> <br/> |<span data-ttu-id="f6324-123">int</span><span class="sxs-lookup"><span data-stu-id="f6324-123">int</span></span>  <br/> ||<span data-ttu-id="f6324-p104">QoE 레코드가 데이터베이스에서 삭제되는 기간(일)을 지정합니다. 삭제가 사용하도록 설정된 경우 이 값보다 오래된 QoE 레코드가 데이터베이스에서 제거됩니다. 기본값은 60일입니다.</span><span class="sxs-lookup"><span data-stu-id="f6324-p104">Specifies the age of QoE records (in days) that will be purged from the database: if purging is enabled, QoE records older than this value will be removed from the database. The default value is 60 days.</span></span>  <br/> |
|<span data-ttu-id="f6324-126">**PurgeHour**</span><span class="sxs-lookup"><span data-stu-id="f6324-126">**PurgeHour**</span></span> <br/> |<span data-ttu-id="f6324-127">int</span><span class="sxs-lookup"><span data-stu-id="f6324-127">int</span></span>  <br/> ||<span data-ttu-id="f6324-p105">데이터베이스 삭제가 수행되는 로컬 시간을 지정합니다. 시간은 24시간제를 사용하여 지정되며 0이 자정(오전 12시)을, 23이 오후 11시를 나타냅니다. 시간 단위만 지정할 수 있습니다. 즉, 오전 10시를 나타내는 10은 값으로 허용되지만 오전 10시 30분을 나타내는 10:30 또는 10.5는 값으로 허용되지 않습니다. 기본값은 1(오전 1시)입니다.</span><span class="sxs-lookup"><span data-stu-id="f6324-p105">Specifies the local time of day when database purging will take place. The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM. Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed. The default value is 1 (1:00 AM). Specifies the local time of day when database purging will take place. The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM. Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed. The default value is 1 (1:00 AM).</span></span>  <br/> |
   

