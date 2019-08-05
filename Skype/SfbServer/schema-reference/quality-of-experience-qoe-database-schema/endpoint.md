---
title: Endpoint 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: 끝점 테이블은 데이터베이스에 기록 된 세션에 참가 한 끝점에 대 한 정보를 저장 하는 지원 테이블입니다. 테이블의 각 레코드는 하나의 끝점을 나타냅니다.
ms.openlocfilehash: 7d582d382784d04d4495de972aa20673862284f4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196567"
---
# <a name="endpoint-table"></a><span data-ttu-id="2a459-104">Endpoint 테이블</span><span class="sxs-lookup"><span data-stu-id="2a459-104">Endpoint table</span></span>
 
<span data-ttu-id="2a459-105">끝점 테이블은 데이터베이스에 기록 된 세션에 참가 한 끝점에 대 한 정보를 저장 하는 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="2a459-105">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="2a459-106">테이블의 각 레코드는 하나의 끝점을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2a459-106">Each record in the table represents one endpoint.</span></span>
  
|<span data-ttu-id="2a459-107">**열**</span><span class="sxs-lookup"><span data-stu-id="2a459-107">**Column**</span></span>|<span data-ttu-id="2a459-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="2a459-108">**Data Type**</span></span>|<span data-ttu-id="2a459-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="2a459-109">**Key/Index**</span></span>|<span data-ttu-id="2a459-110">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="2a459-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2a459-111">**EndpointKey**</span><span class="sxs-lookup"><span data-stu-id="2a459-111">**EndpointKey**</span></span> <br/> |<span data-ttu-id="2a459-112">int</span><span class="sxs-lookup"><span data-stu-id="2a459-112">int</span></span>  <br/> |<span data-ttu-id="2a459-113">주요한</span><span class="sxs-lookup"><span data-stu-id="2a459-113">Primary</span></span>  <br/> |<span data-ttu-id="2a459-114">이 끝점을 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="2a459-114">Unique number identifying this endpoint.</span></span>  <br/> |
|<span data-ttu-id="2a459-115">**이름**</span><span class="sxs-lookup"><span data-stu-id="2a459-115">**Name**</span></span> <br/> |<span data-ttu-id="2a459-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2a459-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="2a459-117">독특한</span><span class="sxs-lookup"><span data-stu-id="2a459-117">Unique</span></span>  <br/> |<span data-ttu-id="2a459-118">끝점 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="2a459-118">Endpoint name.</span></span>  <br/> |
|<span data-ttu-id="2a459-119">**변경할**</span><span class="sxs-lookup"><span data-stu-id="2a459-119">**OS**</span></span> <br/> |<span data-ttu-id="2a459-120">name</span><span class="sxs-lookup"><span data-stu-id="2a459-120">nvarchar(128)</span></span>  <br/> | <br/> |<span data-ttu-id="2a459-121">끝점의 OS (운영 체제)입니다.</span><span class="sxs-lookup"><span data-stu-id="2a459-121">Operating system (OS) of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="2a459-122">**CPUName**</span><span class="sxs-lookup"><span data-stu-id="2a459-122">**CPUName**</span></span> <br/> |<span data-ttu-id="2a459-123">name</span><span class="sxs-lookup"><span data-stu-id="2a459-123">nvarchar(128)</span></span>  <br/> ||<span data-ttu-id="2a459-124">끝점의 CPU 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="2a459-124">CPU name of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="2a459-125">**Cpunum Of코어**</span><span class="sxs-lookup"><span data-stu-id="2a459-125">**CPUNumberOfCores**</span></span> <br/> |<span data-ttu-id="2a459-126">smallint</span><span class="sxs-lookup"><span data-stu-id="2a459-126">smallint</span></span>  <br/> ||<span data-ttu-id="2a459-127">끝점의 CPU 코어 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2a459-127">Number of CPU cores of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="2a459-128">**CPUProcessorSpeed**</span><span class="sxs-lookup"><span data-stu-id="2a459-128">**CPUProcessorSpeed**</span></span> <br/> |<span data-ttu-id="2a459-129">int</span><span class="sxs-lookup"><span data-stu-id="2a459-129">int</span></span>  <br/> ||<span data-ttu-id="2a459-130">끝점의 CPU 프로세서 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="2a459-130">CPU processor speed of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="2a459-131">**VirtualizationFlag**</span><span class="sxs-lookup"><span data-stu-id="2a459-131">**VirtualizationFlag**</span></span> <br/> |<span data-ttu-id="2a459-132">tinyint</span><span class="sxs-lookup"><span data-stu-id="2a459-132">tinyint</span></span>  <br/> || <span data-ttu-id="2a459-133">시스템이 가상화 된 환경에서 실행 되 고 있는지를 나타내는 비트 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="2a459-133">Bit flag that indicates if the system is running in a virtualized environment:</span></span> <br/>  <span data-ttu-id="2a459-134">0x0000e-없음</span><span class="sxs-lookup"><span data-stu-id="2a459-134">0x0000 - None</span></span> <br/>  <span data-ttu-id="2a459-135">0x0001-HyperV</span><span class="sxs-lookup"><span data-stu-id="2a459-135">0x0001 - HyperV</span></span> <br/>  <span data-ttu-id="2a459-136">0x0002-VMWare</span><span class="sxs-lookup"><span data-stu-id="2a459-136">0x0002 - VMWare</span></span> <br/>  <span data-ttu-id="2a459-137">0x0004-가상 PC</span><span class="sxs-lookup"><span data-stu-id="2a459-137">0x0004 - Virtual PC</span></span> <br/>  <span data-ttu-id="2a459-138">0x0008-Xen PC</span><span class="sxs-lookup"><span data-stu-id="2a459-138">0x0008 - Xen PC</span></span> <br/> |
   

