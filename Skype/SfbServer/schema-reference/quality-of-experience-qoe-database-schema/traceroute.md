---
title: TraceRoute 테이블
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
ms.assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
description: TraceRoute 테이블에는 통화의 라우팅 정보가 포함되어 있습니다. 이 표는 Microsoft Lync Server 2013에서 도입된 것입니다.
ms.openlocfilehash: 7ecad93cca80a9b7cea73f64158b3c0008a1d6e7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831328"
---
# <a name="traceroute-table"></a><span data-ttu-id="44a47-104">TraceRoute 테이블</span><span class="sxs-lookup"><span data-stu-id="44a47-104">TraceRoute table</span></span>
 
<span data-ttu-id="44a47-105">TraceRoute 테이블에는 통화의 라우팅 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44a47-105">The TraceRoute table contains routing information from calls.</span></span> <span data-ttu-id="44a47-106">이 표는 Microsoft Lync Server 2013에서 도입된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="44a47-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="44a47-107">**열**</span><span class="sxs-lookup"><span data-stu-id="44a47-107">**Column**</span></span>|<span data-ttu-id="44a47-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="44a47-108">**Data Type**</span></span>|<span data-ttu-id="44a47-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="44a47-109">**Key/Index**</span></span>|<span data-ttu-id="44a47-110">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="44a47-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="44a47-111">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="44a47-111">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="44a47-112">datetime</span><span class="sxs-lookup"><span data-stu-id="44a47-112">datetime</span></span>  <br/> |<span data-ttu-id="44a47-113">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="44a47-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="44a47-114">통화가 시작된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="44a47-114">Date and time that the call began.</span></span>  <br/> |
|<span data-ttu-id="44a47-115">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="44a47-115">**SessionSeq**</span></span> <br/> |<span data-ttu-id="44a47-116">int</span><span class="sxs-lookup"><span data-stu-id="44a47-116">int</span></span>  <br/> |<span data-ttu-id="44a47-117">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="44a47-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="44a47-118">같은 날짜와 동시에 시작될 수 있는 여러 호출을 구분하는 데 사용되는 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="44a47-118">Unique identifier used to distinguish between multiple calls that might have begun on the same date and at the same time.</span></span>  <br/> |
|<span data-ttu-id="44a47-119">**MediaLineLabel**</span><span class="sxs-lookup"><span data-stu-id="44a47-119">**MediaLineLabel**</span></span> <br/> |<span data-ttu-id="44a47-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="44a47-120">tinyint</span></span>  <br/> |<span data-ttu-id="44a47-121">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="44a47-121">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="44a47-p103">통화에서 사용되는 비디오 라인의 유형을 나타냅니다. 허용되는 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="44a47-p103">Represents the type of video line used in the call. Allowed values are:</span></span>  <br/> <span data-ttu-id="44a47-124">0 - 오디오</span><span class="sxs-lookup"><span data-stu-id="44a47-124">0 - Audio</span></span>  <br/> <span data-ttu-id="44a47-125">1 - 비디오</span><span class="sxs-lookup"><span data-stu-id="44a47-125">1 - Video</span></span>  <br/> <span data-ttu-id="44a47-126">2 - 파노라마 비디오</span><span class="sxs-lookup"><span data-stu-id="44a47-126">2 - Panoramic video</span></span>  <br/> <span data-ttu-id="44a47-127">3 - 응용 프로그램/데스크톱 공유</span><span class="sxs-lookup"><span data-stu-id="44a47-127">3 - Application/Desktop sharing</span></span>  <br/> |
|<span data-ttu-id="44a47-128">**FromCaller**</span><span class="sxs-lookup"><span data-stu-id="44a47-128">**FromCaller**</span></span> <br/> |<span data-ttu-id="44a47-129">bit</span><span class="sxs-lookup"><span data-stu-id="44a47-129">bit</span></span>  <br/> |<span data-ttu-id="44a47-130">Primary</span><span class="sxs-lookup"><span data-stu-id="44a47-130">Primary</span></span>  <br/> |<span data-ttu-id="44a47-131">통화를 시작한 끝점입니다.</span><span class="sxs-lookup"><span data-stu-id="44a47-131">Endpoint that placed the call.</span></span>  <br/> |
|<span data-ttu-id="44a47-132">**홉**</span><span class="sxs-lookup"><span data-stu-id="44a47-132">**Hop**</span></span> <br/> |<span data-ttu-id="44a47-133">int</span><span class="sxs-lookup"><span data-stu-id="44a47-133">int</span></span>  <br/> ||<span data-ttu-id="44a47-134">네트워크 홉/</span><span class="sxs-lookup"><span data-stu-id="44a47-134">Network hop/</span></span>  <br/> |
|<span data-ttu-id="44a47-135">**IPAddressKey**</span><span class="sxs-lookup"><span data-stu-id="44a47-135">**IPAddressKey**</span></span> <br/> |<span data-ttu-id="44a47-136">int</span><span class="sxs-lookup"><span data-stu-id="44a47-136">int</span></span>  <br/> |<span data-ttu-id="44a47-137">외계인</span><span class="sxs-lookup"><span data-stu-id="44a47-137">Foreign</span></span>  <br/> |<span data-ttu-id="44a47-138">IP 주소의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="44a47-138">Unique identifier for the IP address.</span></span> <span data-ttu-id="44a47-139">IP 주소 정보는 [IPAddress 테이블에 저장됩니다.](ipaddress.md)</span><span class="sxs-lookup"><span data-stu-id="44a47-139">IP address information is stored in the [IPAddress table](ipaddress.md).</span></span>  <br/> |
|<span data-ttu-id="44a47-140">**RTT**</span><span class="sxs-lookup"><span data-stu-id="44a47-140">**RTT**</span></span> <br/> |<span data-ttu-id="44a47-141">int</span><span class="sxs-lookup"><span data-stu-id="44a47-141">int</span></span>  <br/> ||<span data-ttu-id="44a47-142">왕복 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="44a47-142">Roundtrip time.</span></span> <span data-ttu-id="44a47-143">왕복 시간은 음성 패킷이 대상에 도달한 다음 수신된 알림을 다시 보내는 데 걸리는 시간을 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="44a47-143">The roundtrip time measures the amount of time it takes for a voice packet to reach its destination and then send back notification that it was received.</span></span>  <br/> |
   

