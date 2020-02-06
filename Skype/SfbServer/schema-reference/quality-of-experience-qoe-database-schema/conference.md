---
title: Conference 테이블
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
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: 회의 테이블은 지원 테이블입니다. 각 레코드는 하나의 회의 또는 피어 투 피어 세션을 나타냅니다.
ms.openlocfilehash: 95e08861adaca2e76144f35037626e7b03afd962
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41810306"
---
# <a name="conference-table"></a><span data-ttu-id="753d4-104">Conference 테이블</span><span class="sxs-lookup"><span data-stu-id="753d4-104">Conference table</span></span>
 
<span data-ttu-id="753d4-105">회의 테이블은 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="753d4-105">The Conference table is a supporting table.</span></span> <span data-ttu-id="753d4-106">각 레코드는 하나의 회의 또는 피어 투 피어 세션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="753d4-106">Each record represents one conference or peer-to-peer session.</span></span>
  
|<span data-ttu-id="753d4-107">**열**</span><span class="sxs-lookup"><span data-stu-id="753d4-107">**Column**</span></span>|<span data-ttu-id="753d4-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="753d4-108">**Data Type**</span></span>|<span data-ttu-id="753d4-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="753d4-109">**Key/Index**</span></span>|<span data-ttu-id="753d4-110">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="753d4-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="753d4-111">**ConferenceKey**</span><span class="sxs-lookup"><span data-stu-id="753d4-111">**ConferenceKey**</span></span> <br/> |<span data-ttu-id="753d4-112">int</span><span class="sxs-lookup"><span data-stu-id="753d4-112">int</span></span>  <br/> |<span data-ttu-id="753d4-113">주요한</span><span class="sxs-lookup"><span data-stu-id="753d4-113">Primary</span></span>  <br/> |<span data-ttu-id="753d4-114">이 회의 레코드를 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="753d4-114">Unique number identifying this conference record.</span></span>  <br/> |
|<span data-ttu-id="753d4-115">**ConfURI**</span><span class="sxs-lookup"><span data-stu-id="753d4-115">**ConfURI**</span></span> <br/> |<span data-ttu-id="753d4-116">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="753d4-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="753d4-117">독특한</span><span class="sxs-lookup"><span data-stu-id="753d4-117">unique</span></span>  <br/> |<span data-ttu-id="753d4-118">회의가 면 회의 URI이 고 피어 투 피어 세션 인 경우 DialogID입니다.</span><span class="sxs-lookup"><span data-stu-id="753d4-118">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span>  <br/> |
|<span data-ttu-id="753d4-119">**검사**</span><span class="sxs-lookup"><span data-stu-id="753d4-119">**Checksum**</span></span> <br/> |<span data-ttu-id="753d4-120">int</span><span class="sxs-lookup"><span data-stu-id="753d4-120">int</span></span>  <br/> |<span data-ttu-id="753d4-121">색인</span><span class="sxs-lookup"><span data-stu-id="753d4-121">index</span></span>  <br/> |<span data-ttu-id="753d4-122">회의 URI의 체크섬입니다.</span><span class="sxs-lookup"><span data-stu-id="753d4-122">Checksum of the conference URI.</span></span> <span data-ttu-id="753d4-123">이는 내부적으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="753d4-123">This is used internally.</span></span>  <br/> |
|<span data-ttu-id="753d4-124">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="753d4-124">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="753d4-125">dmtf</span><span class="sxs-lookup"><span data-stu-id="753d4-125">datetime</span></span>  <br/> ||<span data-ttu-id="753d4-126">내부용 으로만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="753d4-126">For internal use only.</span></span>  <br/> |
   

