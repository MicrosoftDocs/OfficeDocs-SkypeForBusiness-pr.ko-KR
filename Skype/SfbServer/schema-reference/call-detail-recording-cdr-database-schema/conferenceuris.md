---
title: 비즈니스용 Skype 서버 2015의 ConferenceUris 테이블
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
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: ConfereneUris 테이블은 데이터베이스에 기록 된 회의 세션에 참가 한 다양 한 회의 Uri 목록을 저장 하는 지원 테이블입니다. 테이블의 각 레코드는 하나의 회의 URI를 나타냅니다.
ms.openlocfilehash: f1e95cce4fedf26477973a4fba6a9d3a32288f92
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815316"
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a><span data-ttu-id="e5657-104">비즈니스용 Skype 서버 2015의 ConferenceUris 테이블</span><span class="sxs-lookup"><span data-stu-id="e5657-104">ConferenceUris table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="e5657-105">ConfereneUris 테이블은 데이터베이스에 기록 된 회의 세션에 참가 한 다양 한 회의 Uri 목록을 저장 하는 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="e5657-105">The ConfereneUris table is a supporting table that stores a list of the various conference URIs that have participated in conference sessions recorded in the database.</span></span> <span data-ttu-id="e5657-106">테이블의 각 레코드는 하나의 회의 URI를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e5657-106">Each record in the table represents one conference URI.</span></span>
  
|<span data-ttu-id="e5657-107">**열**</span><span class="sxs-lookup"><span data-stu-id="e5657-107">**Column**</span></span>|<span data-ttu-id="e5657-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="e5657-108">**Data Type**</span></span>|<span data-ttu-id="e5657-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="e5657-109">**Key/Index**</span></span>|<span data-ttu-id="e5657-110">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="e5657-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e5657-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="e5657-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="e5657-112">dmtf</span><span class="sxs-lookup"><span data-stu-id="e5657-112">datetime</span></span>  <br/> |<span data-ttu-id="e5657-113">주요한</span><span class="sxs-lookup"><span data-stu-id="e5657-113">Primary</span></span>  <br/> |<span data-ttu-id="e5657-114">내부에 사용 되는 타임 스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="e5657-114">Time stamp, Internal used.</span></span>  <br/> |
|<span data-ttu-id="e5657-115">**ConferenceUriId**</span><span class="sxs-lookup"><span data-stu-id="e5657-115">**ConferenceUriId**</span></span> <br/> |<span data-ttu-id="e5657-116">int</span><span class="sxs-lookup"><span data-stu-id="e5657-116">int</span></span>  <br/> |<span data-ttu-id="e5657-117">주요한</span><span class="sxs-lookup"><span data-stu-id="e5657-117">Primary</span></span>  <br/> |<span data-ttu-id="e5657-118">이 회의 URI를 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="e5657-118">Unique number identifying this conference URI.</span></span>  <br/> |
|<span data-ttu-id="e5657-119">**ConferenceUri**</span><span class="sxs-lookup"><span data-stu-id="e5657-119">**ConferenceUri**</span></span> <br/> |<span data-ttu-id="e5657-120">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="e5657-120">nvarchar(450)</span></span>  <br/> ||<span data-ttu-id="e5657-121">회의 URI.</span><span class="sxs-lookup"><span data-stu-id="e5657-121">Conference URI.</span></span>  <br/> |
|<span data-ttu-id="e5657-122">**검사**</span><span class="sxs-lookup"><span data-stu-id="e5657-122">**Checksum**</span></span> <br/> |<span data-ttu-id="e5657-123">int</span><span class="sxs-lookup"><span data-stu-id="e5657-123">int</span></span>  <br/> ||<span data-ttu-id="e5657-124">ConferenceUri의 검사 값입니다.</span><span class="sxs-lookup"><span data-stu-id="e5657-124">Checksum of ConferenceUri.</span></span> <span data-ttu-id="e5657-125">데이터베이스 검색 속도를 향상 시키는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5657-125">Used to increases the speed of database searches.</span></span>  <br/> |
|<span data-ttu-id="e5657-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="e5657-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="e5657-127">int</span><span class="sxs-lookup"><span data-stu-id="e5657-127">int</span></span>  <br/> |<span data-ttu-id="e5657-128">외부</span><span class="sxs-lookup"><span data-stu-id="e5657-128">Foreign</span></span>  <br/> |<span data-ttu-id="e5657-129">회의: IM 회의에 대 한 채팅 또는 컨퍼런스: 오디오/비디오 회의를 위한 오디오-영상 통화 등의 URI 형식</span><span class="sxs-lookup"><span data-stu-id="e5657-129">URI type, such as conf:chat for IM conference, or conf:audio-video for audio/video conference.</span></span> <span data-ttu-id="e5657-130">자세한 내용은 [UriTypes 표](uritypes.md) 표를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e5657-130">See the [UriTypes table](uritypes.md) table for more information.</span></span> <br/> |
   

