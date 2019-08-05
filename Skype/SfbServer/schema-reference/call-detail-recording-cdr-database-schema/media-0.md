---
title: 미디어 보기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
description: 미디어 보기는 피어 투 피어 세션에 사용 되는 미디어 형식에 대 한 정보를 저장 합니다. 하나 이상의 미디어 유형이 사용 되는 경우 한 세션은 테이블의 여러 레코드로 표시 됩니다. 이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.
ms.openlocfilehash: 044a31381d4e1e48c465f7ee6de89acab10ab54e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196718"
---
# <a name="media-view"></a><span data-ttu-id="1459a-105">미디어 보기</span><span class="sxs-lookup"><span data-stu-id="1459a-105">Media view</span></span>
 
<span data-ttu-id="1459a-106">미디어 보기는 피어 투 피어 세션에 사용 되는 미디어 형식에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="1459a-106">The Media view stores information about one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="1459a-107">하나 이상의 미디어 유형이 사용 되는 경우 한 세션은 테이블의 여러 레코드로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1459a-107">One session would be represented by multiple records in the table, if more than one media type is used.</span></span> <span data-ttu-id="1459a-108">이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1459a-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1459a-109">미디어 보기는 세션의 미디어 기간을 계산 하는 데 사용해 서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1459a-109">The Media view should not be used to calculate the media duration for a session.</span></span> <span data-ttu-id="1459a-110">이 보기에는 세션의 미디어 교환에 대 한 신호 세부 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1459a-110">This view contains the signaling details of media exchange in a session.</span></span> <span data-ttu-id="1459a-111">미디어 교환은 초대 요청에 의해 수행 되며 StartTime은 초대를 보낸 시간을 나타냅니다. 세션이 허용 된 후에만 미디어가 시작 되므로 초대 시간이 반드시 미디어 시작 시간을 의미 하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="1459a-111">Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the session is accepted.</span></span> 
  
<span data-ttu-id="1459a-112">미디어 보기에는 [Sessiondetails 보기](sessiondetails-0.md) 의 모든 열이 포함 되어 있으며 아래 목록에 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1459a-112">The Media view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the ones listed below.</span></span>
  
|<span data-ttu-id="1459a-113">**열**</span><span class="sxs-lookup"><span data-stu-id="1459a-113">**Column**</span></span>|<span data-ttu-id="1459a-114">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="1459a-114">**Data Type**</span></span>|<span data-ttu-id="1459a-115">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="1459a-115">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1459a-116">**미디어**</span><span class="sxs-lookup"><span data-stu-id="1459a-116">**Media**</span></span> <br/> |<span data-ttu-id="1459a-117">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1459a-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="1459a-118">미디어 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="1459a-118">Media type.</span></span> <span data-ttu-id="1459a-119">자세한 내용은 [Medialist 테이블](medialist.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1459a-119">See the [MediaList table](medialist.md) for more information.</span></span> <br/> |
|<span data-ttu-id="1459a-120">**MediaStartTime**</span><span class="sxs-lookup"><span data-stu-id="1459a-120">**MediaStartTime**</span></span> <br/> |<span data-ttu-id="1459a-121">dmtf</span><span class="sxs-lookup"><span data-stu-id="1459a-121">datetime</span></span>  <br/> |<span data-ttu-id="1459a-122">미디어 요청이 전송 된 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="1459a-122">Time that a media request was sent out.</span></span>  <br/> |
|<span data-ttu-id="1459a-123">**MediaEndTime**</span><span class="sxs-lookup"><span data-stu-id="1459a-123">**MediaEndTime**</span></span> <br/> |<span data-ttu-id="1459a-124">dmtf</span><span class="sxs-lookup"><span data-stu-id="1459a-124">datetime</span></span>  <br/> |<span data-ttu-id="1459a-125">세션 종료 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="1459a-125">End time of the session.</span></span>  <br/> |
   

