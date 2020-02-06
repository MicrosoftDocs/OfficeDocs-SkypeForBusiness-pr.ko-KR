---
title: TraceRoute 테이블
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
ms.assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
description: TraceRoute 테이블에는 통화의 라우팅 정보가 포함 됩니다. 이 표는 Microsoft Lync Server 2013에서 도입 되었습니다.
ms.openlocfilehash: e257bf6d89d04cd0f4784e62e7ac2876b6ede7e5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805116"
---
# <a name="traceroute-table"></a><span data-ttu-id="4635f-104">TraceRoute 테이블</span><span class="sxs-lookup"><span data-stu-id="4635f-104">TraceRoute table</span></span>
 
<span data-ttu-id="4635f-105">TraceRoute 테이블에는 통화의 라우팅 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4635f-105">The TraceRoute table contains routing information from calls.</span></span> <span data-ttu-id="4635f-106">이 표는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4635f-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="4635f-107">**열**</span><span class="sxs-lookup"><span data-stu-id="4635f-107">**Column**</span></span>|<span data-ttu-id="4635f-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="4635f-108">**Data Type**</span></span>|<span data-ttu-id="4635f-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="4635f-109">**Key/Index**</span></span>|<span data-ttu-id="4635f-110">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="4635f-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4635f-111">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="4635f-111">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="4635f-112">dmtf</span><span class="sxs-lookup"><span data-stu-id="4635f-112">datetime</span></span>  <br/> |<span data-ttu-id="4635f-113">기본, 외래</span><span class="sxs-lookup"><span data-stu-id="4635f-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="4635f-114">통화가 시작 된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="4635f-114">Date and time that the call began.</span></span>  <br/> |
|<span data-ttu-id="4635f-115">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="4635f-115">**SessionSeq**</span></span> <br/> |<span data-ttu-id="4635f-116">int</span><span class="sxs-lookup"><span data-stu-id="4635f-116">int</span></span>  <br/> |<span data-ttu-id="4635f-117">기본, 외래</span><span class="sxs-lookup"><span data-stu-id="4635f-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="4635f-118">같은 날짜와 동시에 시작 했을 수 있는 여러 통화를 구분 하는 데 사용 되는 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="4635f-118">Unique identifier used to distinguish between multiple calls that might have begun on the same date and at the same time.</span></span>  <br/> |
|<span data-ttu-id="4635f-119">**MediaLineLabel**</span><span class="sxs-lookup"><span data-stu-id="4635f-119">**MediaLineLabel**</span></span> <br/> |<span data-ttu-id="4635f-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="4635f-120">tinyint</span></span>  <br/> |<span data-ttu-id="4635f-121">기본, 외래</span><span class="sxs-lookup"><span data-stu-id="4635f-121">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="4635f-122">통화에 사용 되는 영상 회선 유형을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4635f-122">Represents the type of video line used in the call.</span></span> <span data-ttu-id="4635f-123">사용 가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4635f-123">Allowed values are:</span></span>  <br/> <span data-ttu-id="4635f-124">0-오디오</span><span class="sxs-lookup"><span data-stu-id="4635f-124">0 - Audio</span></span>  <br/> <span data-ttu-id="4635f-125">1-영상 통화</span><span class="sxs-lookup"><span data-stu-id="4635f-125">1 - Video</span></span>  <br/> <span data-ttu-id="4635f-126">2-파노라마 비디오</span><span class="sxs-lookup"><span data-stu-id="4635f-126">2 - Panoramic video</span></span>  <br/> <span data-ttu-id="4635f-127">3-애플리케이션/데스크톱 공유</span><span class="sxs-lookup"><span data-stu-id="4635f-127">3 - Application/Desktop sharing</span></span>  <br/> |
|<span data-ttu-id="4635f-128">**FromCaller**</span><span class="sxs-lookup"><span data-stu-id="4635f-128">**FromCaller**</span></span> <br/> |<span data-ttu-id="4635f-129">다소</span><span class="sxs-lookup"><span data-stu-id="4635f-129">bit</span></span>  <br/> |<span data-ttu-id="4635f-130">주요한</span><span class="sxs-lookup"><span data-stu-id="4635f-130">Primary</span></span>  <br/> |<span data-ttu-id="4635f-131">호출을 배치한 끝점입니다.</span><span class="sxs-lookup"><span data-stu-id="4635f-131">Endpoint that placed the call.</span></span>  <br/> |
|<span data-ttu-id="4635f-132">**홉당**</span><span class="sxs-lookup"><span data-stu-id="4635f-132">**Hop**</span></span> <br/> |<span data-ttu-id="4635f-133">int</span><span class="sxs-lookup"><span data-stu-id="4635f-133">int</span></span>  <br/> ||<span data-ttu-id="4635f-134">네트워크 홉/</span><span class="sxs-lookup"><span data-stu-id="4635f-134">Network hop/</span></span>  <br/> |
|<span data-ttu-id="4635f-135">**IPAddressKey**</span><span class="sxs-lookup"><span data-stu-id="4635f-135">**IPAddressKey**</span></span> <br/> |<span data-ttu-id="4635f-136">int</span><span class="sxs-lookup"><span data-stu-id="4635f-136">int</span></span>  <br/> |<span data-ttu-id="4635f-137">외부</span><span class="sxs-lookup"><span data-stu-id="4635f-137">Foreign</span></span>  <br/> |<span data-ttu-id="4635f-138">IP 주소에 대 한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="4635f-138">Unique identifier for the IP address.</span></span> <span data-ttu-id="4635f-139">IP 주소 정보는 [IPAddress 테이블](ipaddress.md)에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4635f-139">IP address information is stored in the [IPAddress table](ipaddress.md).</span></span>  <br/> |
|<span data-ttu-id="4635f-140">**RTT**</span><span class="sxs-lookup"><span data-stu-id="4635f-140">**RTT**</span></span> <br/> |<span data-ttu-id="4635f-141">int</span><span class="sxs-lookup"><span data-stu-id="4635f-141">int</span></span>  <br/> ||<span data-ttu-id="4635f-142">왕복 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="4635f-142">Roundtrip time.</span></span> <span data-ttu-id="4635f-143">왕복 시간은 음성 패킷이 목적지에 도달 하는 데 걸리는 시간을 측정 한 다음 받은 알림을 다시 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="4635f-143">The roundtrip time measures the amount of time it takes for a voice packet to reach its destination and then send back notification that it was received.</span></span>  <br/> |
   

