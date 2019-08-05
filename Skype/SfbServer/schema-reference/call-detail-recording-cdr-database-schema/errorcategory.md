---
title: 비즈니스용 Skype 서버 2015의 ErrorCategory 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: ErrorCategory 테이블에는 각 비즈니스용 Skype Server 2015 진단 분류에 대 한 친근 한 이름이 있습니다. 기본적으로 비즈니스용 Skype 서버 2015에는 다음 분류가 사용 됩니다.
ms.openlocfilehash: bafeb75ee9e6ae0f96b08e26909828f1b36f7e7b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196757"
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a><span data-ttu-id="fb54a-104">비즈니스용 Skype 서버 2015의 ErrorCategory 테이블</span><span class="sxs-lookup"><span data-stu-id="fb54a-104">ErrorCategory table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="fb54a-105">ErrorCategory 테이블에는 각 비즈니스용 Skype Server 2015 진단 분류에 대 한 친근 한 이름이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb54a-105">The ErrorCategory table contains the friendly name for each Skype for Business Server 2015 diagnostic classification.</span></span> <span data-ttu-id="fb54a-106">기본적으로 비즈니스용 Skype 서버 2015에는 다음 분류가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb54a-106">By default, Skype for Business Server 2015 uses the following classifications:</span></span>
  
- <span data-ttu-id="fb54a-107">0--성공</span><span class="sxs-lookup"><span data-stu-id="fb54a-107">0 -- Success</span></span>
    
- <span data-ttu-id="fb54a-108">1--실패 예상</span><span class="sxs-lookup"><span data-stu-id="fb54a-108">1 -- Expected failure</span></span>
    
- <span data-ttu-id="fb54a-109">2-예기치 않은 오류</span><span class="sxs-lookup"><span data-stu-id="fb54a-109">2 - Unexpected failure</span></span>
    
<span data-ttu-id="fb54a-110">이 표는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fb54a-110">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="fb54a-111">**열**</span><span class="sxs-lookup"><span data-stu-id="fb54a-111">**Column**</span></span>|<span data-ttu-id="fb54a-112">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="fb54a-112">**Data Type**</span></span>|<span data-ttu-id="fb54a-113">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="fb54a-113">**Key/Index**</span></span>|<span data-ttu-id="fb54a-114">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="fb54a-114">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fb54a-115">**CategoryId**</span><span class="sxs-lookup"><span data-stu-id="fb54a-115">**CategoryId**</span></span> <br/> |<span data-ttu-id="fb54a-116">tinyint</span><span class="sxs-lookup"><span data-stu-id="fb54a-116">tinyint</span></span>  <br/> |<span data-ttu-id="fb54a-117">주요한</span><span class="sxs-lookup"><span data-stu-id="fb54a-117">Primary</span></span>  <br/> |<span data-ttu-id="fb54a-118">분류의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="fb54a-118">Unique identifier for the classification.</span></span>  <br/> |
|<span data-ttu-id="fb54a-119">**이름**</span><span class="sxs-lookup"><span data-stu-id="fb54a-119">**Name**</span></span> <br/> |<span data-ttu-id="fb54a-120">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="fb54a-120">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="fb54a-121">분류에 할당 된 값 및 식별 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="fb54a-121">Value and friendly name assigned to the classification.</span></span> <span data-ttu-id="fb54a-122">사용 가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fb54a-122">Allowed values are:</span></span> <br/>  <span data-ttu-id="fb54a-123">0--성공</span><span class="sxs-lookup"><span data-stu-id="fb54a-123">0 -- Success</span></span> <br/>  <span data-ttu-id="fb54a-124">1--실패 예상</span><span class="sxs-lookup"><span data-stu-id="fb54a-124">1 -- Expected failure</span></span> <br/>  <span data-ttu-id="fb54a-125">2-예기치 않은 오류</span><span class="sxs-lookup"><span data-stu-id="fb54a-125">2 - Unexpected failure</span></span> <br/> |
   

