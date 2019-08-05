---
title: VideoClientEvent 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: 각 레코드에는 비디오 통화의 한 끝점에 대 한 클라이언트 이벤트가 포함 됩니다. 일반적으로 한 통화에는 두 개의 레코드 (호출자 용 1 개와 피호출자 용)가 있습니다.
ms.openlocfilehash: b8e93206ea30622baa82adcec5ee9a80235521c5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196505"
---
# <a name="videoclientevent-table"></a><span data-ttu-id="7b22b-104">VideoClientEvent 테이블</span><span class="sxs-lookup"><span data-stu-id="7b22b-104">VideoClientEvent table</span></span>
 
<span data-ttu-id="7b22b-105">각 레코드에는 비디오 통화의 한 끝점에 대 한 클라이언트 이벤트가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b22b-105">Each record contains client event for one endpoint in a video call.</span></span> <span data-ttu-id="7b22b-106">일반적으로 한 통화에는 두 개의 레코드 (호출자 용 1 개와 피호출자 용)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b22b-106">Usually, one call has two records, one for caller and one for callee.</span></span>
  
|<span data-ttu-id="7b22b-107">**열**</span><span class="sxs-lookup"><span data-stu-id="7b22b-107">**Column**</span></span>|<span data-ttu-id="7b22b-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="7b22b-108">**Data Type**</span></span>|<span data-ttu-id="7b22b-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="7b22b-109">**Key/Index**</span></span>|<span data-ttu-id="7b22b-110">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="7b22b-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7b22b-111">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="7b22b-111">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="7b22b-112">dmtf</span><span class="sxs-lookup"><span data-stu-id="7b22b-112">datetime</span></span>  <br/> |<span data-ttu-id="7b22b-113">주요한</span><span class="sxs-lookup"><span data-stu-id="7b22b-113">Primary</span></span>  <br/> |<span data-ttu-id="7b22b-114">[Medialine 테이블](medialine-0.md)에서 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b22b-114">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="7b22b-115">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="7b22b-115">**SessionSeq**</span></span> <br/> |<span data-ttu-id="7b22b-116">int</span><span class="sxs-lookup"><span data-stu-id="7b22b-116">int</span></span>  <br/> |<span data-ttu-id="7b22b-117">주요한</span><span class="sxs-lookup"><span data-stu-id="7b22b-117">Primary</span></span>  <br/> |<span data-ttu-id="7b22b-118">[Medialine 테이블](medialine-0.md)에서 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b22b-118">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="7b22b-119">**MediaLineLabel**</span><span class="sxs-lookup"><span data-stu-id="7b22b-119">**MediaLineLabel**</span></span> <br/> |<span data-ttu-id="7b22b-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="7b22b-120">tinyint</span></span>  <br/> |<span data-ttu-id="7b22b-121">주요한</span><span class="sxs-lookup"><span data-stu-id="7b22b-121">Primary</span></span>  <br/> |<span data-ttu-id="7b22b-122">[Medialine 테이블](medialine-0.md)에서 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b22b-122">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="7b22b-123">**FromCaller**</span><span class="sxs-lookup"><span data-stu-id="7b22b-123">**FromCaller**</span></span> <br/> |<span data-ttu-id="7b22b-124">다소</span><span class="sxs-lookup"><span data-stu-id="7b22b-124">bit</span></span>  <br/> |<span data-ttu-id="7b22b-125">주요한</span><span class="sxs-lookup"><span data-stu-id="7b22b-125">Primary</span></span>  <br/> |<span data-ttu-id="7b22b-126">0: 피호출자의 데이터</span><span class="sxs-lookup"><span data-stu-id="7b22b-126">0: Callee's data</span></span>  <br/> <span data-ttu-id="7b22b-127">1: 발신자의 데이터</span><span class="sxs-lookup"><span data-stu-id="7b22b-127">1: Caller's data</span></span>  <br/> |
|<span data-ttu-id="7b22b-128">**NetworkBandwidthLowEventRatio**</span><span class="sxs-lookup"><span data-stu-id="7b22b-128">**NetworkBandwidthLowEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="7b22b-129">세션 백분율 \ \ \ \에 대 한 \ \ \ n 대역폭 이벤트가 ' 불량 ' 상태에 대해 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="7b22b-129">Percentage of session the LowBandwidth event was fired for 'Bad' state.</span></span> <span data-ttu-id="7b22b-130">사용할 수 있는 대역폭이 불충분 한 음성 환경에 적합 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7b22b-130">The available bandwidth is insufficient for an acceptable voice experience.</span></span>  <br/> |
|<span data-ttu-id="7b22b-131">**NetworkReceiveQualityEventRatio**</span><span class="sxs-lookup"><span data-stu-id="7b22b-131">**NetworkReceiveQualityEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="7b22b-132">세션 백분율 ReceiveSendQuality 이벤트가 ' 잘못 된 ' 상태에 대해 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="7b22b-132">Percentage of session the ReceiveSendQuality event was fired for 'Bad' state.</span></span>  <br/> <span data-ttu-id="7b22b-133">지터 또는 패킷 손실 측면의 네트워크 품질은 심각 하며 수신 되는 오디오 품질에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7b22b-133">Network quality in terms of jitter or packet loss is severe and impacts the quality of audio being received.</span></span>  <br/> |
   

