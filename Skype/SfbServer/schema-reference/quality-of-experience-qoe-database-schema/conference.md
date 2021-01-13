---
title: Conference 테이블
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
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: Conference 테이블은 지원 테이블입니다. 각 레코드는 하나의 회의 또는 피어-투-피어 세션을 나타냅니다.
ms.openlocfilehash: 3840ad9bb4f9b0ff0aea5068c73d307d5bd0cf5e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802788"
---
# <a name="conference-table"></a><span data-ttu-id="75e64-104">Conference 테이블</span><span class="sxs-lookup"><span data-stu-id="75e64-104">Conference table</span></span>
 
<span data-ttu-id="75e64-p102">Conference 테이블은 지원 테이블입니다. 각 레코드는 하나의 회의 또는 피어-투-피어 세션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="75e64-p102">The Conference table is a supporting table. Each record represents one conference or peer-to-peer session.</span></span>
  
|<span data-ttu-id="75e64-107">**열**</span><span class="sxs-lookup"><span data-stu-id="75e64-107">**Column**</span></span>|<span data-ttu-id="75e64-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="75e64-108">**Data Type**</span></span>|<span data-ttu-id="75e64-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="75e64-109">**Key/Index**</span></span>|<span data-ttu-id="75e64-110">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="75e64-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="75e64-111">**ConferenceKey**</span><span class="sxs-lookup"><span data-stu-id="75e64-111">**ConferenceKey**</span></span> <br/> |<span data-ttu-id="75e64-112">int</span><span class="sxs-lookup"><span data-stu-id="75e64-112">int</span></span>  <br/> |<span data-ttu-id="75e64-113">Primary</span><span class="sxs-lookup"><span data-stu-id="75e64-113">Primary</span></span>  <br/> |<span data-ttu-id="75e64-114">이 회의 레코드를 식별하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="75e64-114">Unique number identifying this conference record.</span></span>  <br/> |
|<span data-ttu-id="75e64-115">**ConfURI**</span><span class="sxs-lookup"><span data-stu-id="75e64-115">**ConfURI**</span></span> <br/> |<span data-ttu-id="75e64-116">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="75e64-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="75e64-117">unique</span><span class="sxs-lookup"><span data-stu-id="75e64-117">unique</span></span>  <br/> |<span data-ttu-id="75e64-118">항목이 회의인 경우 회의 URI이고 피어 투 피어 세션인 경우에는 DialogID입니다.</span><span class="sxs-lookup"><span data-stu-id="75e64-118">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span>  <br/> |
|<span data-ttu-id="75e64-119">**체크 um**</span><span class="sxs-lookup"><span data-stu-id="75e64-119">**Checksum**</span></span> <br/> |<span data-ttu-id="75e64-120">int</span><span class="sxs-lookup"><span data-stu-id="75e64-120">int</span></span>  <br/> |<span data-ttu-id="75e64-121">index</span><span class="sxs-lookup"><span data-stu-id="75e64-121">index</span></span>  <br/> |<span data-ttu-id="75e64-p103">회의 URI의 체크섬입니다. 내부적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="75e64-p103">Checksum of the conference URI. This is used internally.</span></span>  <br/> |
|<span data-ttu-id="75e64-124">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="75e64-124">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="75e64-125">datetime</span><span class="sxs-lookup"><span data-stu-id="75e64-125">datetime</span></span>  <br/> ||<span data-ttu-id="75e64-126">내부 용도로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="75e64-126">For internal use only.</span></span>  <br/> |
   

