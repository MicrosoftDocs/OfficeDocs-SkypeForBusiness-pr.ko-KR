---
title: 미디어 보기
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
ms.assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
description: Media 보기에는 피어 투 피어 세션에 사용되는 단일 미디어 유형에 대한 정보가 저장됩니다. 둘 이상의 미디어 유형이 사용된 경우 하나의 세션이 테이블에 여러 레코드로 표시됩니다. 이 보기는 Microsoft Lync Server 2013에서 도입했습니다.
ms.openlocfilehash: 77c22246056a28cdb41a007ac0d7e2617fa00ad9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831793"
---
# <a name="media-view"></a><span data-ttu-id="9e677-105">미디어 보기</span><span class="sxs-lookup"><span data-stu-id="9e677-105">Media view</span></span>
 
<span data-ttu-id="9e677-106">Media 보기에는 피어 투 피어 세션에 사용되는 단일 미디어 유형에 대한 정보가 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e677-106">The Media view stores information about one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="9e677-107">둘 이상의 미디어 유형이 사용된 경우 하나의 세션이 테이블에 여러 레코드로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e677-107">One session would be represented by multiple records in the table, if more than one media type is used.</span></span> <span data-ttu-id="9e677-108">이 보기는 Microsoft Lync Server 2013에서 도입했습니다.</span><span class="sxs-lookup"><span data-stu-id="9e677-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9e677-p103">Media 보기를 사용하여 세션의 미디어 기간을 계산해서는 안 됩니다. 이 보기에는 세션에 포함된 미디어 교환의 신호 세부 정보가 포함됩니다. 미디어 교환은 INVITE 요청에 의해 수행되며 StartTime은 INVITE가 전송된 시간을 나타냅니다. 미디어는 세션이 수락된 후에만 시작되므로 초대 시간이 반드시 미디어 시작 시간인 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="9e677-p103">The Media view should not be used to calculate the media duration for a session. This view contains the signaling details of media exchange in a session. Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the session is accepted.</span></span> 
  
<span data-ttu-id="9e677-112">미디어 보기에는 [SessionDetails](sessiondetails-0.md) 보기의 모든 열과 아래에 나열된 열이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e677-112">The Media view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the ones listed below.</span></span>
  
|<span data-ttu-id="9e677-113">**열**</span><span class="sxs-lookup"><span data-stu-id="9e677-113">**Column**</span></span>|<span data-ttu-id="9e677-114">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="9e677-114">**Data Type**</span></span>|<span data-ttu-id="9e677-115">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="9e677-115">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9e677-116">**미디어**</span><span class="sxs-lookup"><span data-stu-id="9e677-116">**Media**</span></span> <br/> |<span data-ttu-id="9e677-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9e677-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="9e677-118">미디어 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="9e677-118">Media type.</span></span> <span data-ttu-id="9e677-119">자세한 내용은 [MediaList 테이블을](medialist.md) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9e677-119">See the [MediaList table](medialist.md) for more information.</span></span> <br/> |
|<span data-ttu-id="9e677-120">**MediaStartTime**</span><span class="sxs-lookup"><span data-stu-id="9e677-120">**MediaStartTime**</span></span> <br/> |<span data-ttu-id="9e677-121">datetime</span><span class="sxs-lookup"><span data-stu-id="9e677-121">datetime</span></span>  <br/> |<span data-ttu-id="9e677-122">미디어 요청을 보낸 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="9e677-122">Time that a media request was sent out.</span></span>  <br/> |
|<span data-ttu-id="9e677-123">**MediaEndTime**</span><span class="sxs-lookup"><span data-stu-id="9e677-123">**MediaEndTime**</span></span> <br/> |<span data-ttu-id="9e677-124">datetime</span><span class="sxs-lookup"><span data-stu-id="9e677-124">datetime</span></span>  <br/> |<span data-ttu-id="9e677-125">세션 종료 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="9e677-125">End time of the session.</span></span>  <br/> |
   

