---
title: VideoClientEvent 테이블
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
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: 각 레코드에는 비디오 통화의 한 끝점에 대한 클라이언트 이벤트가 포함되어 있습니다. 일반적으로 한 통화에는 발신자용과 발신자용 레코드가 1개씩 두 개 있습니다.
ms.openlocfilehash: bb4a9feca562bed7bdb0080e7f9181003952f5d4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821398"
---
# <a name="videoclientevent-table"></a><span data-ttu-id="4e422-104">VideoClientEvent 테이블</span><span class="sxs-lookup"><span data-stu-id="4e422-104">VideoClientEvent table</span></span>
 
<span data-ttu-id="4e422-105">각 레코드에는 비디오 통화의 한 끝점에 대한 클라이언트 이벤트가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e422-105">Each record contains client event for one endpoint in a video call.</span></span> <span data-ttu-id="4e422-106">일반적으로 한 통화에는 발신자용과 발신자용 레코드가 1개씩 두 개 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e422-106">Usually, one call has two records, one for caller and one for callee.</span></span>
  
|<span data-ttu-id="4e422-107">**열**</span><span class="sxs-lookup"><span data-stu-id="4e422-107">**Column**</span></span>|<span data-ttu-id="4e422-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="4e422-108">**Data Type**</span></span>|<span data-ttu-id="4e422-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="4e422-109">**Key/Index**</span></span>|<span data-ttu-id="4e422-110">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="4e422-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4e422-111">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="4e422-111">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="4e422-112">datetime</span><span class="sxs-lookup"><span data-stu-id="4e422-112">datetime</span></span>  <br/> |<span data-ttu-id="4e422-113">Primary</span><span class="sxs-lookup"><span data-stu-id="4e422-113">Primary</span></span>  <br/> |<span data-ttu-id="4e422-114">[MediaLine 테이블에서 참조됩니다.](medialine-0.md)</span><span class="sxs-lookup"><span data-stu-id="4e422-114">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="4e422-115">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="4e422-115">**SessionSeq**</span></span> <br/> |<span data-ttu-id="4e422-116">int</span><span class="sxs-lookup"><span data-stu-id="4e422-116">int</span></span>  <br/> |<span data-ttu-id="4e422-117">Primary</span><span class="sxs-lookup"><span data-stu-id="4e422-117">Primary</span></span>  <br/> |<span data-ttu-id="4e422-118">[MediaLine 테이블에서 참조됩니다.](medialine-0.md)</span><span class="sxs-lookup"><span data-stu-id="4e422-118">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="4e422-119">**MediaLineLabel**</span><span class="sxs-lookup"><span data-stu-id="4e422-119">**MediaLineLabel**</span></span> <br/> |<span data-ttu-id="4e422-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="4e422-120">tinyint</span></span>  <br/> |<span data-ttu-id="4e422-121">Primary</span><span class="sxs-lookup"><span data-stu-id="4e422-121">Primary</span></span>  <br/> |<span data-ttu-id="4e422-122">[MediaLine 테이블에서 참조됩니다.](medialine-0.md)</span><span class="sxs-lookup"><span data-stu-id="4e422-122">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="4e422-123">**FromCaller**</span><span class="sxs-lookup"><span data-stu-id="4e422-123">**FromCaller**</span></span> <br/> |<span data-ttu-id="4e422-124">bit</span><span class="sxs-lookup"><span data-stu-id="4e422-124">bit</span></span>  <br/> |<span data-ttu-id="4e422-125">Primary</span><span class="sxs-lookup"><span data-stu-id="4e422-125">Primary</span></span>  <br/> |<span data-ttu-id="4e422-126">0: 발신자 데이터</span><span class="sxs-lookup"><span data-stu-id="4e422-126">0: Callee's data</span></span>  <br/> <span data-ttu-id="4e422-127">1: 발신자 데이터</span><span class="sxs-lookup"><span data-stu-id="4e422-127">1: Caller's data</span></span>  <br/> |
|<span data-ttu-id="4e422-128">**NetworkBandwidthLowEventRatio**</span><span class="sxs-lookup"><span data-stu-id="4e422-128">**NetworkBandwidthLowEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="4e422-129">LowBandwidth 이벤트가 '나쁜' 상태로 발생된 세션의 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="4e422-129">Percentage of session the LowBandwidth event was fired for 'Bad' state.</span></span> <span data-ttu-id="4e422-130">사용 가능한 대역폭이 허용되는 음성 환경으로 충분하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4e422-130">The available bandwidth is insufficient for an acceptable voice experience.</span></span>  <br/> |
|<span data-ttu-id="4e422-131">**NetworkReceiveQualityEventRatio**</span><span class="sxs-lookup"><span data-stu-id="4e422-131">**NetworkReceiveQualityEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="4e422-132">ReceiveSendQuality 이벤트가 '나쁜' 상태로 발생된 세션의 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="4e422-132">Percentage of session the ReceiveSendQuality event was fired for 'Bad' state.</span></span>  <br/> <span data-ttu-id="4e422-133">지터나 패킷 손실 측면에서 네트워크 품질은 심각하며 수신되는 오디오 품질에 영향을 미치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e422-133">Network quality in terms of jitter or packet loss is severe and impacts the quality of audio being received.</span></span>  <br/> |
   

