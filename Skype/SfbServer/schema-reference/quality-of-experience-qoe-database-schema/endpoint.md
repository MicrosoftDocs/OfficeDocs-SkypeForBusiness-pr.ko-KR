---
title: 끝점 테이블
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
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: Endpoint 테이블은 데이터베이스에 기록된 세션에 참여한 끝점에 대한 정보를 저장하는 지원 테이블입니다. 테이블의 각 레코드는 끝점을 하나씩 나타났습니다.
ms.openlocfilehash: 9caa0571e562a84c1678208f0e70c27317deda3c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823068"
---
# <a name="endpoint-table"></a><span data-ttu-id="9aefe-104">끝점 테이블</span><span class="sxs-lookup"><span data-stu-id="9aefe-104">Endpoint table</span></span>
 
<span data-ttu-id="9aefe-105">Endpoint 테이블은 데이터베이스에 기록된 세션에 참여한 끝점에 대한 정보를 저장하는 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="9aefe-105">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="9aefe-106">테이블의 각 레코드는 하나의 끝점을 나타났습니다.</span><span class="sxs-lookup"><span data-stu-id="9aefe-106">Each record in the table represents one endpoint.</span></span>
  
|<span data-ttu-id="9aefe-107">**열**</span><span class="sxs-lookup"><span data-stu-id="9aefe-107">**Column**</span></span>|<span data-ttu-id="9aefe-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="9aefe-108">**Data Type**</span></span>|<span data-ttu-id="9aefe-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="9aefe-109">**Key/Index**</span></span>|<span data-ttu-id="9aefe-110">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="9aefe-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9aefe-111">**EndpointKey**</span><span class="sxs-lookup"><span data-stu-id="9aefe-111">**EndpointKey**</span></span> <br/> |<span data-ttu-id="9aefe-112">int</span><span class="sxs-lookup"><span data-stu-id="9aefe-112">int</span></span>  <br/> |<span data-ttu-id="9aefe-113">Primary</span><span class="sxs-lookup"><span data-stu-id="9aefe-113">Primary</span></span>  <br/> |<span data-ttu-id="9aefe-114">이 끝점을 식별하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="9aefe-114">Unique number identifying this endpoint.</span></span>  <br/> |
|<span data-ttu-id="9aefe-115">**이름**</span><span class="sxs-lookup"><span data-stu-id="9aefe-115">**Name**</span></span> <br/> |<span data-ttu-id="9aefe-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9aefe-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="9aefe-117">고유</span><span class="sxs-lookup"><span data-stu-id="9aefe-117">Unique</span></span>  <br/> |<span data-ttu-id="9aefe-118">끝점 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9aefe-118">Endpoint name.</span></span>  <br/> |
|<span data-ttu-id="9aefe-119">**OS**</span><span class="sxs-lookup"><span data-stu-id="9aefe-119">**OS**</span></span> <br/> |<span data-ttu-id="9aefe-120">nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="9aefe-120">nvarchar(128)</span></span>  <br/> | <br/> |<span data-ttu-id="9aefe-121">끝점의 운영 체제(OS)입니다.</span><span class="sxs-lookup"><span data-stu-id="9aefe-121">Operating system (OS) of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="9aefe-122">**CPUName**</span><span class="sxs-lookup"><span data-stu-id="9aefe-122">**CPUName**</span></span> <br/> |<span data-ttu-id="9aefe-123">nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="9aefe-123">nvarchar(128)</span></span>  <br/> ||<span data-ttu-id="9aefe-124">끝점의 CPU 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9aefe-124">CPU name of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="9aefe-125">**CPUNumberOfCores**</span><span class="sxs-lookup"><span data-stu-id="9aefe-125">**CPUNumberOfCores**</span></span> <br/> |<span data-ttu-id="9aefe-126">smallint</span><span class="sxs-lookup"><span data-stu-id="9aefe-126">smallint</span></span>  <br/> ||<span data-ttu-id="9aefe-127">끝점의 CPU 코어 수입니다.</span><span class="sxs-lookup"><span data-stu-id="9aefe-127">Number of CPU cores of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="9aefe-128">**CPUProcessorSpeed**</span><span class="sxs-lookup"><span data-stu-id="9aefe-128">**CPUProcessorSpeed**</span></span> <br/> |<span data-ttu-id="9aefe-129">int</span><span class="sxs-lookup"><span data-stu-id="9aefe-129">int</span></span>  <br/> ||<span data-ttu-id="9aefe-130">끝점의 CPU 프로세서 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="9aefe-130">CPU processor speed of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="9aefe-131">**VirtualizationFlag**</span><span class="sxs-lookup"><span data-stu-id="9aefe-131">**VirtualizationFlag**</span></span> <br/> |<span data-ttu-id="9aefe-132">tinyint</span><span class="sxs-lookup"><span data-stu-id="9aefe-132">tinyint</span></span>  <br/> || <span data-ttu-id="9aefe-133">시스템이 가상화된 환경에서 실행 중인지 나타내는 비트 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="9aefe-133">Bit flag that indicates if the system is running in a virtualized environment:</span></span> <br/>  <span data-ttu-id="9aefe-134">0x0000 - 없음</span><span class="sxs-lookup"><span data-stu-id="9aefe-134">0x0000 - None</span></span> <br/>  <span data-ttu-id="9aefe-135">0x0001 - HyperV</span><span class="sxs-lookup"><span data-stu-id="9aefe-135">0x0001 - HyperV</span></span> <br/>  <span data-ttu-id="9aefe-136">0x0002 - VMWare</span><span class="sxs-lookup"><span data-stu-id="9aefe-136">0x0002 - VMWare</span></span> <br/>  <span data-ttu-id="9aefe-137">0x0004 - 가상 PC</span><span class="sxs-lookup"><span data-stu-id="9aefe-137">0x0004 - Virtual PC</span></span> <br/>  <span data-ttu-id="9aefe-138">0x0008 - Xen PC</span><span class="sxs-lookup"><span data-stu-id="9aefe-138">0x0008 - Xen PC</span></span> <br/> |
   

