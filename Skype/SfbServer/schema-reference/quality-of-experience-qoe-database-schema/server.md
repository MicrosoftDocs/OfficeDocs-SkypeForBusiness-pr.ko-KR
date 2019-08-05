---
title: Server 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: 서버 테이블은 지원 테이블입니다. 각 레코드는 하나의 서버를 나타냅니다.
ms.openlocfilehash: 93ba62c262b95b46b76cd445be04a0bc53c5a960
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196527"
---
# <a name="server-table"></a><span data-ttu-id="b0af0-104">Server 테이블</span><span class="sxs-lookup"><span data-stu-id="b0af0-104">Server table</span></span>
 
<span data-ttu-id="b0af0-105">서버 테이블은 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="b0af0-105">The Server table is a supporting table.</span></span> <span data-ttu-id="b0af0-106">각 레코드는 하나의 서버를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b0af0-106">Each record represents one server.</span></span> 
  
|<span data-ttu-id="b0af0-107">**열**</span><span class="sxs-lookup"><span data-stu-id="b0af0-107">**Column**</span></span>|<span data-ttu-id="b0af0-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="b0af0-108">**Data Type**</span></span>|<span data-ttu-id="b0af0-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="b0af0-109">**Key/Index**</span></span>|<span data-ttu-id="b0af0-110">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="b0af0-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b0af0-111">**ServerKey**</span><span class="sxs-lookup"><span data-stu-id="b0af0-111">**ServerKey**</span></span> <br/> |<span data-ttu-id="b0af0-112">int</span><span class="sxs-lookup"><span data-stu-id="b0af0-112">int</span></span>  <br/> |<span data-ttu-id="b0af0-113">주요한</span><span class="sxs-lookup"><span data-stu-id="b0af0-113">Primary</span></span>  <br/> |<span data-ttu-id="b0af0-114">서버를 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="b0af0-114">Unique number identifying the server.</span></span>  <br/> |
|<span data-ttu-id="b0af0-115">**FQDNOrIP**</span><span class="sxs-lookup"><span data-stu-id="b0af0-115">**FQDNOrIP**</span></span> <br/> |<span data-ttu-id="b0af0-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b0af0-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="b0af0-117">색인</span><span class="sxs-lookup"><span data-stu-id="b0af0-117">index</span></span>  <br/> |<span data-ttu-id="b0af0-118">MAC 주소 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="b0af0-118">MAC address string.</span></span>  <br/> |
|<span data-ttu-id="b0af0-119">**ServerType**</span><span class="sxs-lookup"><span data-stu-id="b0af0-119">**ServerType**</span></span> <br/> |<span data-ttu-id="b0af0-120">int</span><span class="sxs-lookup"><span data-stu-id="b0af0-120">int</span></span>  <br/> |<span data-ttu-id="b0af0-121">외부</span><span class="sxs-lookup"><span data-stu-id="b0af0-121">Foreign</span></span>  <br/> |<span data-ttu-id="b0af0-122">1: 중재 서버</span><span class="sxs-lookup"><span data-stu-id="b0af0-122">1: Mediation Server</span></span>  <br/> <span data-ttu-id="b0af0-123">2: a/V 회의 Server16394: A/v Edge service32769: Gateway</span><span class="sxs-lookup"><span data-stu-id="b0af0-123">2: A/V Conferencing Server16394: A/V Edge service32769: Gateway</span></span>  <br/> |
|<span data-ttu-id="b0af0-124">**PoolName**</span><span class="sxs-lookup"><span data-stu-id="b0af0-124">**PoolName**</span></span> <br/> |<span data-ttu-id="b0af0-125">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="b0af0-125">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="b0af0-126">서버가 속한 풀.</span><span class="sxs-lookup"><span data-stu-id="b0af0-126">Pool the server belongs to.</span></span> <span data-ttu-id="b0af0-127">A/V 회의 서버에만 해당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0af0-127">Only applicable for the A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="b0af0-128">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="b0af0-128">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="b0af0-129">dmtf</span><span class="sxs-lookup"><span data-stu-id="b0af0-129">datetime</span></span>  <br/> ||<span data-ttu-id="b0af0-130">내부용 으로만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0af0-130">For internal use only.</span></span>  <br/> |
   

