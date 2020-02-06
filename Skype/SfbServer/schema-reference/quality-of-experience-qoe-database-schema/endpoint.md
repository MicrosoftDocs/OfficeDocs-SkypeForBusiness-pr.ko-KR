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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: 끝점 테이블은 데이터베이스에 기록 된 세션에 참가 한 끝점에 대 한 정보를 저장 하는 지원 테이블입니다. 테이블의 각 레코드는 하나의 끝점을 나타냅니다.
ms.openlocfilehash: b64b19a3149fa3d490ea8dc957699c0a114f763c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41809556"
---
# <a name="endpoint-table"></a><span data-ttu-id="f54d0-104">Endpoint 테이블</span><span class="sxs-lookup"><span data-stu-id="f54d0-104">Endpoint table</span></span>
 
<span data-ttu-id="f54d0-105">끝점 테이블은 데이터베이스에 기록 된 세션에 참가 한 끝점에 대 한 정보를 저장 하는 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="f54d0-105">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="f54d0-106">테이블의 각 레코드는 하나의 끝점을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f54d0-106">Each record in the table represents one endpoint.</span></span>
  
|<span data-ttu-id="f54d0-107">**열**</span><span class="sxs-lookup"><span data-stu-id="f54d0-107">**Column**</span></span>|<span data-ttu-id="f54d0-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="f54d0-108">**Data Type**</span></span>|<span data-ttu-id="f54d0-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="f54d0-109">**Key/Index**</span></span>|<span data-ttu-id="f54d0-110">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="f54d0-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f54d0-111">**EndpointKey**</span><span class="sxs-lookup"><span data-stu-id="f54d0-111">**EndpointKey**</span></span> <br/> |<span data-ttu-id="f54d0-112">int</span><span class="sxs-lookup"><span data-stu-id="f54d0-112">int</span></span>  <br/> |<span data-ttu-id="f54d0-113">주요한</span><span class="sxs-lookup"><span data-stu-id="f54d0-113">Primary</span></span>  <br/> |<span data-ttu-id="f54d0-114">이 끝점을 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="f54d0-114">Unique number identifying this endpoint.</span></span>  <br/> |
|<span data-ttu-id="f54d0-115">**이름**</span><span class="sxs-lookup"><span data-stu-id="f54d0-115">**Name**</span></span> <br/> |<span data-ttu-id="f54d0-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f54d0-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="f54d0-117">독특한</span><span class="sxs-lookup"><span data-stu-id="f54d0-117">Unique</span></span>  <br/> |<span data-ttu-id="f54d0-118">끝점 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f54d0-118">Endpoint name.</span></span>  <br/> |
|<span data-ttu-id="f54d0-119">**변경할**</span><span class="sxs-lookup"><span data-stu-id="f54d0-119">**OS**</span></span> <br/> |<span data-ttu-id="f54d0-120">name</span><span class="sxs-lookup"><span data-stu-id="f54d0-120">nvarchar(128)</span></span>  <br/> | <br/> |<span data-ttu-id="f54d0-121">끝점의 OS (운영 체제)입니다.</span><span class="sxs-lookup"><span data-stu-id="f54d0-121">Operating system (OS) of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="f54d0-122">**CPUName**</span><span class="sxs-lookup"><span data-stu-id="f54d0-122">**CPUName**</span></span> <br/> |<span data-ttu-id="f54d0-123">name</span><span class="sxs-lookup"><span data-stu-id="f54d0-123">nvarchar(128)</span></span>  <br/> ||<span data-ttu-id="f54d0-124">끝점의 CPU 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f54d0-124">CPU name of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="f54d0-125">**Cpunum Of코어**</span><span class="sxs-lookup"><span data-stu-id="f54d0-125">**CPUNumberOfCores**</span></span> <br/> |<span data-ttu-id="f54d0-126">smallint</span><span class="sxs-lookup"><span data-stu-id="f54d0-126">smallint</span></span>  <br/> ||<span data-ttu-id="f54d0-127">끝점의 CPU 코어 수입니다.</span><span class="sxs-lookup"><span data-stu-id="f54d0-127">Number of CPU cores of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="f54d0-128">**CPUProcessorSpeed**</span><span class="sxs-lookup"><span data-stu-id="f54d0-128">**CPUProcessorSpeed**</span></span> <br/> |<span data-ttu-id="f54d0-129">int</span><span class="sxs-lookup"><span data-stu-id="f54d0-129">int</span></span>  <br/> ||<span data-ttu-id="f54d0-130">끝점의 CPU 프로세서 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="f54d0-130">CPU processor speed of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="f54d0-131">**VirtualizationFlag**</span><span class="sxs-lookup"><span data-stu-id="f54d0-131">**VirtualizationFlag**</span></span> <br/> |<span data-ttu-id="f54d0-132">tinyint</span><span class="sxs-lookup"><span data-stu-id="f54d0-132">tinyint</span></span>  <br/> || <span data-ttu-id="f54d0-133">시스템이 가상화 된 환경에서 실행 되 고 있는지를 나타내는 비트 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="f54d0-133">Bit flag that indicates if the system is running in a virtualized environment:</span></span> <br/>  <span data-ttu-id="f54d0-134">0x0000e-없음</span><span class="sxs-lookup"><span data-stu-id="f54d0-134">0x0000 - None</span></span> <br/>  <span data-ttu-id="f54d0-135">0x0001-HyperV</span><span class="sxs-lookup"><span data-stu-id="f54d0-135">0x0001 - HyperV</span></span> <br/>  <span data-ttu-id="f54d0-136">0x0002-VMWare</span><span class="sxs-lookup"><span data-stu-id="f54d0-136">0x0002 - VMWare</span></span> <br/>  <span data-ttu-id="f54d0-137">0x0004-가상 PC</span><span class="sxs-lookup"><span data-stu-id="f54d0-137">0x0004 - Virtual PC</span></span> <br/>  <span data-ttu-id="f54d0-138">0x0008-Xen PC</span><span class="sxs-lookup"><span data-stu-id="f54d0-138">0x0008 - Xen PC</span></span> <br/> |
   

