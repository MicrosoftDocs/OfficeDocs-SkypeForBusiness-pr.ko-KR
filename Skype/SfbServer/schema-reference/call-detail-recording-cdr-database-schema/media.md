---
title: Media 테이블
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1e1b427f-59b5-4564-bde5-1002a80439ee
description: 각 레코드는 피어-투-피어 세션에 사용된 하나의 미디어 유형을 나타냅니다. 둘 이상의 미디어 유형이 사용된 경우 하나의 세션이 테이블에 여러 레코드로 표시됩니다.
ms.openlocfilehash: ce5b5a2b312307e608367279e4e871ed03063860
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800108"
---
# <a name="media-table"></a><span data-ttu-id="08c9e-104">Media 테이블</span><span class="sxs-lookup"><span data-stu-id="08c9e-104">Media table</span></span>
 
<span data-ttu-id="08c9e-p102">각 레코드는 피어-투-피어 세션에 사용된 하나의 미디어 유형을 나타냅니다. 둘 이상의 미디어 유형이 사용된 경우 하나의 세션이 테이블에 여러 레코드로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="08c9e-p102">Each record represents one media type used in a peer-to-peer session. One session would be represented by multiple records in the table, if more than one media type is used.</span></span>
  
> [!NOTE]
> <span data-ttu-id="08c9e-p103">Media 테이블을 사용하여 세션의 미디어 기간을 계산해서는 안 됩니다. 이 테이블에는 세션에 포함된 미디어 교환의 신호 세부 정보가 포함됩니다. 미디어 교환은 INVITE 요청에 의해 수행되며 StartTime은 INVITE가 전송된 시간을 나타냅니다. 미디어는 세션 참가자가 세션을 수락한 후에만 시작되므로 초대 시간이 반드시 미디어 시작 시간인 것은 아닙니다. EndTime은 일반적으로 이 세션의 종료 시간을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="08c9e-p103">The Media table should not be used to calculate the media duration for a session. This table contains the signaling details of media exchange in a session. Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the sessionee accepts the session. The EndTime usually means the end time of this session.</span></span> 
  
|<span data-ttu-id="08c9e-111">**열**</span><span class="sxs-lookup"><span data-stu-id="08c9e-111">**Column**</span></span>|<span data-ttu-id="08c9e-112">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="08c9e-112">**Data Type**</span></span>|<span data-ttu-id="08c9e-113">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="08c9e-113">**Key/Index**</span></span>|<span data-ttu-id="08c9e-114">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="08c9e-114">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="08c9e-115">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="08c9e-115">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="08c9e-116">datetime</span><span class="sxs-lookup"><span data-stu-id="08c9e-116">datetime</span></span>  <br/> |<span data-ttu-id="08c9e-117">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="08c9e-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="08c9e-118">세션 요청 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="08c9e-118">Time of session request.</span></span> <span data-ttu-id="08c9e-119">**SessionIdSeq** 와 함께 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="08c9e-119">Used in conjunction with **SessionIdSeq** to uniquely identify a session.</span></span> <span data-ttu-id="08c9e-120">자세한 내용은 [비즈니스용 Skype 서버 2015의 Dialogs](dialogs.md) 테이블을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="08c9e-120">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="08c9e-121">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="08c9e-121">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="08c9e-122">int</span><span class="sxs-lookup"><span data-stu-id="08c9e-122">int</span></span>  <br/> |<span data-ttu-id="08c9e-123">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="08c9e-123">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="08c9e-124">세션을 식별하기 위한 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="08c9e-124">ID number to identify the session.</span></span> <span data-ttu-id="08c9e-125">**SessionIdTime** 과 함께 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="08c9e-125">Used in conjunction with **SessionIdTime** to uniquely identify a session.</span></span> <span data-ttu-id="08c9e-126">자세한 내용은 [비즈니스용 Skype 서버 2015의 Dialogs](dialogs.md) 테이블을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="08c9e-126">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="08c9e-127">**MediaId**</span><span class="sxs-lookup"><span data-stu-id="08c9e-127">**MediaId**</span></span> <br/> |<span data-ttu-id="08c9e-128">tinyint</span><span class="sxs-lookup"><span data-stu-id="08c9e-128">tinyint</span></span>  <br/> |<span data-ttu-id="08c9e-129">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="08c9e-129">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="08c9e-130">이 미디어 유형을 식별하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="08c9e-130">Unique number identifying this media type.</span></span> <span data-ttu-id="08c9e-131">자세한 내용은 [MediaList 테이블을](medialist.md) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="08c9e-131">See the [MediaList table](medialist.md) for more information.</span></span> <br/> |
|<span data-ttu-id="08c9e-132">**StartTime**</span><span class="sxs-lookup"><span data-stu-id="08c9e-132">**StartTime**</span></span> <br/> |<span data-ttu-id="08c9e-133">datetime</span><span class="sxs-lookup"><span data-stu-id="08c9e-133">datetime</span></span>  <br/> |<span data-ttu-id="08c9e-134">Primary</span><span class="sxs-lookup"><span data-stu-id="08c9e-134">Primary</span></span>  <br/> |<span data-ttu-id="08c9e-p107">실제 미디어 시작 시간이 아니라 미디어 요청이 전송된 시간입니다. **StartTime** 에는 세션 설정 시간이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="08c9e-p107">This is the time that a media request was sent out, not the real media start time. **StartTime** includes the session setup time. </span></span><br/> |
|<span data-ttu-id="08c9e-137">**EndTime**</span><span class="sxs-lookup"><span data-stu-id="08c9e-137">**EndTime**</span></span> <br/> |<span data-ttu-id="08c9e-138">datetime</span><span class="sxs-lookup"><span data-stu-id="08c9e-138">datetime</span></span>  <br/> ||<span data-ttu-id="08c9e-139">세션의 종료 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="08c9e-139">This is the end time of the session.</span></span>  <br/> |
   

