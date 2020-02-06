---
title: Media 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1e1b427f-59b5-4564-bde5-1002a80439ee
description: 각 레코드는 피어 투 피어 세션에 사용 되는 하나의 미디어 유형을 나타냅니다. 하나 이상의 미디어 유형이 사용 되는 경우 한 세션은 테이블의 여러 레코드로 표시 됩니다.
ms.openlocfilehash: b96f1e9fccf2ac3416e505eb19a54a5e227bb01f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815046"
---
# <a name="media-table"></a><span data-ttu-id="ea844-104">Media 테이블</span><span class="sxs-lookup"><span data-stu-id="ea844-104">Media table</span></span>
 
<span data-ttu-id="ea844-105">각 레코드는 피어 투 피어 세션에 사용 되는 하나의 미디어 유형을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ea844-105">Each record represents one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="ea844-106">하나 이상의 미디어 유형이 사용 되는 경우 한 세션은 테이블의 여러 레코드로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea844-106">One session would be represented by multiple records in the table, if more than one media type is used.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ea844-107">미디어 테이블은 세션의 미디어 기간을 계산 하는 데 사용해 서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea844-107">The Media table should not be used to calculate the media duration for a session.</span></span> <span data-ttu-id="ea844-108">이 표에는 세션의 미디어 교환 신호 세부 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea844-108">This table contains the signaling details of media exchange in a session.</span></span> <span data-ttu-id="ea844-109">미디어 교환은 초대 요청에 의해 수행 되며 StartTime은 초대를 보낸 시간을 나타냅니다. 세션을 수락 하는 경우에만 미디어가 시작 되므로 초대 시간이 반드시 미디어 시작 시간을 의미 하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="ea844-109">Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the sessionee accepts the session.</span></span> <span data-ttu-id="ea844-110">EndTime은 일반적으로이 세션의 종료 시간을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea844-110">The EndTime usually means the end time of this session.</span></span> 
  
|<span data-ttu-id="ea844-111">**열**</span><span class="sxs-lookup"><span data-stu-id="ea844-111">**Column**</span></span>|<span data-ttu-id="ea844-112">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="ea844-112">**Data Type**</span></span>|<span data-ttu-id="ea844-113">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="ea844-113">**Key/Index**</span></span>|<span data-ttu-id="ea844-114">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="ea844-114">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ea844-115">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="ea844-115">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="ea844-116">dmtf</span><span class="sxs-lookup"><span data-stu-id="ea844-116">datetime</span></span>  <br/> |<span data-ttu-id="ea844-117">기본, 외래</span><span class="sxs-lookup"><span data-stu-id="ea844-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="ea844-118">세션 요청 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="ea844-118">Time of session request.</span></span> <span data-ttu-id="ea844-119">세션을 고유 하 게 식별 하는 **Sessionidseq** 와 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea844-119">Used in conjunction with **SessionIdSeq** to uniquely identify a session.</span></span> <span data-ttu-id="ea844-120">자세한 내용은 [비즈니스용 Skype 서버 2015의 대화 상자 표](dialogs.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ea844-120">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="ea844-121">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="ea844-121">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="ea844-122">int</span><span class="sxs-lookup"><span data-stu-id="ea844-122">int</span></span>  <br/> |<span data-ttu-id="ea844-123">기본, 외래</span><span class="sxs-lookup"><span data-stu-id="ea844-123">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="ea844-124">세션을 식별 하는 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="ea844-124">ID number to identify the session.</span></span> <span data-ttu-id="ea844-125">세션을 고유 하 게 식별 하는 **Sessionidtime** 과 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea844-125">Used in conjunction with **SessionIdTime** to uniquely identify a session.</span></span> <span data-ttu-id="ea844-126">자세한 내용은 [비즈니스용 Skype 서버 2015의 대화 상자 표](dialogs.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ea844-126">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="ea844-127">**MediaId**</span><span class="sxs-lookup"><span data-stu-id="ea844-127">**MediaId**</span></span> <br/> |<span data-ttu-id="ea844-128">tinyint</span><span class="sxs-lookup"><span data-stu-id="ea844-128">tinyint</span></span>  <br/> |<span data-ttu-id="ea844-129">기본, 외래</span><span class="sxs-lookup"><span data-stu-id="ea844-129">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="ea844-130">이 미디어 유형을 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="ea844-130">Unique number identifying this media type.</span></span> <span data-ttu-id="ea844-131">자세한 내용은 [Medialist 테이블](medialist.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ea844-131">See the [MediaList table](medialist.md) for more information.</span></span> <br/> |
|<span data-ttu-id="ea844-132">**StartTime**</span><span class="sxs-lookup"><span data-stu-id="ea844-132">**StartTime**</span></span> <br/> |<span data-ttu-id="ea844-133">dmtf</span><span class="sxs-lookup"><span data-stu-id="ea844-133">datetime</span></span>  <br/> |<span data-ttu-id="ea844-134">주요한</span><span class="sxs-lookup"><span data-stu-id="ea844-134">Primary</span></span>  <br/> |<span data-ttu-id="ea844-135">이것은 실제 미디어 시작 시간이 아닌 미디어 요청이 전송 된 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="ea844-135">This is the time that a media request was sent out, not the real media start time.</span></span> <span data-ttu-id="ea844-136">**StartTime** 에는 세션 설정 시간이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea844-136">**StartTime** includes the session setup time.</span></span> <br/> |
|<span data-ttu-id="ea844-137">**EndTime**</span><span class="sxs-lookup"><span data-stu-id="ea844-137">**EndTime**</span></span> <br/> |<span data-ttu-id="ea844-138">dmtf</span><span class="sxs-lookup"><span data-stu-id="ea844-138">datetime</span></span>  <br/> ||<span data-ttu-id="ea844-139">세션 종료 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="ea844-139">This is the end time of the session.</span></span>  <br/> |
   

