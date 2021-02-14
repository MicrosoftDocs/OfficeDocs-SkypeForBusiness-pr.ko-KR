---
title: Server 테이블
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
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: Server 테이블은 지원 테이블입니다. 각 레코드는 하나의 서버를 나타냅니다.
ms.openlocfilehash: 7f26ed9053c65acb8cfd2e586edbd77fdfa7472b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802708"
---
# <a name="server-table"></a><span data-ttu-id="61a6d-104">Server 테이블</span><span class="sxs-lookup"><span data-stu-id="61a6d-104">Server table</span></span>
 
<span data-ttu-id="61a6d-p102">Server 테이블은 지원 테이블입니다. 각 레코드는 하나의 서버를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="61a6d-p102">The Server table is a supporting table. Each record represents one server.</span></span> 
  
|<span data-ttu-id="61a6d-107">**열**</span><span class="sxs-lookup"><span data-stu-id="61a6d-107">**Column**</span></span>|<span data-ttu-id="61a6d-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="61a6d-108">**Data Type**</span></span>|<span data-ttu-id="61a6d-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="61a6d-109">**Key/Index**</span></span>|<span data-ttu-id="61a6d-110">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="61a6d-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="61a6d-111">**ServerKey**</span><span class="sxs-lookup"><span data-stu-id="61a6d-111">**ServerKey**</span></span> <br/> |<span data-ttu-id="61a6d-112">int</span><span class="sxs-lookup"><span data-stu-id="61a6d-112">int</span></span>  <br/> |<span data-ttu-id="61a6d-113">Primary</span><span class="sxs-lookup"><span data-stu-id="61a6d-113">Primary</span></span>  <br/> |<span data-ttu-id="61a6d-114">이 서버를 식별하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="61a6d-114">Unique number identifying the server.</span></span>  <br/> |
|<span data-ttu-id="61a6d-115">**FQDNOrIP**</span><span class="sxs-lookup"><span data-stu-id="61a6d-115">**FQDNOrIP**</span></span> <br/> |<span data-ttu-id="61a6d-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="61a6d-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="61a6d-117">index</span><span class="sxs-lookup"><span data-stu-id="61a6d-117">index</span></span>  <br/> |<span data-ttu-id="61a6d-118">MAC 주소 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="61a6d-118">MAC address string.</span></span>  <br/> |
|<span data-ttu-id="61a6d-119">**ServerType**</span><span class="sxs-lookup"><span data-stu-id="61a6d-119">**ServerType**</span></span> <br/> |<span data-ttu-id="61a6d-120">int</span><span class="sxs-lookup"><span data-stu-id="61a6d-120">int</span></span>  <br/> |<span data-ttu-id="61a6d-121">외계인</span><span class="sxs-lookup"><span data-stu-id="61a6d-121">Foreign</span></span>  <br/> |<span data-ttu-id="61a6d-122">1: 중재 서버</span><span class="sxs-lookup"><span data-stu-id="61a6d-122">1: Mediation Server</span></span>  <br/> <span data-ttu-id="61a6d-123">2: A/V 회의 서버 16394: A/V 에지 서버 32769: 게이트웨이</span><span class="sxs-lookup"><span data-stu-id="61a6d-123">2: A/V Conferencing Server16394: A/V Edge service32769: Gateway</span></span>  <br/> |
|<span data-ttu-id="61a6d-124">**PoolName**</span><span class="sxs-lookup"><span data-stu-id="61a6d-124">**PoolName**</span></span> <br/> |<span data-ttu-id="61a6d-125">nvarchar(512)</span><span class="sxs-lookup"><span data-stu-id="61a6d-125">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="61a6d-p103">서버가 속하는 풀입니다. A/V 회의 서버에만 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61a6d-p103">Pool the server belongs to. Only applicable for the A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="61a6d-128">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="61a6d-128">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="61a6d-129">datetime</span><span class="sxs-lookup"><span data-stu-id="61a6d-129">datetime</span></span>  <br/> ||<span data-ttu-id="61a6d-130">내부 용도로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="61a6d-130">For internal use only.</span></span>  <br/> |
   

