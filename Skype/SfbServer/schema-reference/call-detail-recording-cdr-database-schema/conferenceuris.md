---
title: 비즈니스용 Skype 서버의 ConferenceUris 테이블
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
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: ConfereneUris 테이블은 데이터베이스에 기록된 회의 세션에 참가한 다양한 회의 URI 목록을 저장하는 지원 테이블입니다. 테이블의 각 레코드는 하나의 회의 URI를 나타 내는 것입니다.
ms.openlocfilehash: f439c828460f06067105f8f2da493616c223ed85
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816138"
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a><span data-ttu-id="de067-104">비즈니스용 Skype 서버의 ConferenceUris 테이블</span><span class="sxs-lookup"><span data-stu-id="de067-104">ConferenceUris table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="de067-105">ConfereneUris 테이블은 데이터베이스에 기록된 회의 세션에 참가한 다양한 회의 URI 목록을 저장하는 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="de067-105">The ConfereneUris table is a supporting table that stores a list of the various conference URIs that have participated in conference sessions recorded in the database.</span></span> <span data-ttu-id="de067-106">테이블의 각 레코드는 하나의 회의 URI를 나타 내는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="de067-106">Each record in the table represents one conference URI.</span></span>
  
|<span data-ttu-id="de067-107">**열**</span><span class="sxs-lookup"><span data-stu-id="de067-107">**Column**</span></span>|<span data-ttu-id="de067-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="de067-108">**Data Type**</span></span>|<span data-ttu-id="de067-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="de067-109">**Key/Index**</span></span>|<span data-ttu-id="de067-110">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="de067-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="de067-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="de067-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="de067-112">datetime</span><span class="sxs-lookup"><span data-stu-id="de067-112">datetime</span></span>  <br/> |<span data-ttu-id="de067-113">Primary</span><span class="sxs-lookup"><span data-stu-id="de067-113">Primary</span></span>  <br/> |<span data-ttu-id="de067-114">타임스탬프, 내부 사용</span><span class="sxs-lookup"><span data-stu-id="de067-114">Time stamp, Internal used.</span></span>  <br/> |
|<span data-ttu-id="de067-115">**ConferenceUriId**</span><span class="sxs-lookup"><span data-stu-id="de067-115">**ConferenceUriId**</span></span> <br/> |<span data-ttu-id="de067-116">int</span><span class="sxs-lookup"><span data-stu-id="de067-116">int</span></span>  <br/> |<span data-ttu-id="de067-117">Primary</span><span class="sxs-lookup"><span data-stu-id="de067-117">Primary</span></span>  <br/> |<span data-ttu-id="de067-118">이 전화 회의 URI를 식별하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="de067-118">Unique number identifying this conference URI.</span></span>  <br/> |
|<span data-ttu-id="de067-119">**ConferenceUri**</span><span class="sxs-lookup"><span data-stu-id="de067-119">**ConferenceUri**</span></span> <br/> |<span data-ttu-id="de067-120">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="de067-120">nvarchar(450)</span></span>  <br/> ||<span data-ttu-id="de067-121">회의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="de067-121">Conference URI.</span></span>  <br/> |
|<span data-ttu-id="de067-122">**체크 um**</span><span class="sxs-lookup"><span data-stu-id="de067-122">**Checksum**</span></span> <br/> |<span data-ttu-id="de067-123">int</span><span class="sxs-lookup"><span data-stu-id="de067-123">int</span></span>  <br/> ||<span data-ttu-id="de067-124">ConferenceUri의 체크um입니다.</span><span class="sxs-lookup"><span data-stu-id="de067-124">Checksum of ConferenceUri.</span></span> <span data-ttu-id="de067-125">데이터베이스 검색 속도를 향상하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="de067-125">Used to increases the speed of database searches.</span></span>  <br/> |
|<span data-ttu-id="de067-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="de067-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="de067-127">int</span><span class="sxs-lookup"><span data-stu-id="de067-127">int</span></span>  <br/> |<span data-ttu-id="de067-128">외계인</span><span class="sxs-lookup"><span data-stu-id="de067-128">Foreign</span></span>  <br/> |<span data-ttu-id="de067-129">URI 유형(예: IM 회의용 conf:chat 또는 오디오/비디오 회의의 경우 conf:audio-video)</span><span class="sxs-lookup"><span data-stu-id="de067-129">URI type, such as conf:chat for IM conference, or conf:audio-video for audio/video conference.</span></span> <span data-ttu-id="de067-130">자세한 내용은 [UriTypes 테이블을](uritypes.md) 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="de067-130">See the [UriTypes table](uritypes.md) table for more information.</span></span> <br/> |
   

