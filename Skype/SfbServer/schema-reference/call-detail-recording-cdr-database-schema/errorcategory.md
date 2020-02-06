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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: ErrorCategory 테이블에는 각 비즈니스용 Skype Server 2015 진단 분류에 대 한 친근 한 이름이 있습니다. 기본적으로 비즈니스용 Skype 서버 2015에는 다음 분류가 사용 됩니다.
ms.openlocfilehash: f3ad3f86a382b900d53c5e86140a46d7f32ca1c1
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815256"
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a><span data-ttu-id="92516-104">비즈니스용 Skype 서버 2015의 ErrorCategory 테이블</span><span class="sxs-lookup"><span data-stu-id="92516-104">ErrorCategory table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="92516-105">ErrorCategory 테이블에는 각 비즈니스용 Skype Server 2015 진단 분류에 대 한 친근 한 이름이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92516-105">The ErrorCategory table contains the friendly name for each Skype for Business Server 2015 diagnostic classification.</span></span> <span data-ttu-id="92516-106">기본적으로 비즈니스용 Skype 서버 2015에는 다음 분류가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="92516-106">By default, Skype for Business Server 2015 uses the following classifications:</span></span>
  
- <span data-ttu-id="92516-107">0--성공</span><span class="sxs-lookup"><span data-stu-id="92516-107">0 -- Success</span></span>
    
- <span data-ttu-id="92516-108">1--실패 예상</span><span class="sxs-lookup"><span data-stu-id="92516-108">1 -- Expected failure</span></span>
    
- <span data-ttu-id="92516-109">2-예기치 않은 오류</span><span class="sxs-lookup"><span data-stu-id="92516-109">2 - Unexpected failure</span></span>
    
<span data-ttu-id="92516-110">이 표는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="92516-110">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="92516-111">**열**</span><span class="sxs-lookup"><span data-stu-id="92516-111">**Column**</span></span>|<span data-ttu-id="92516-112">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="92516-112">**Data Type**</span></span>|<span data-ttu-id="92516-113">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="92516-113">**Key/Index**</span></span>|<span data-ttu-id="92516-114">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="92516-114">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="92516-115">**CategoryId**</span><span class="sxs-lookup"><span data-stu-id="92516-115">**CategoryId**</span></span> <br/> |<span data-ttu-id="92516-116">tinyint</span><span class="sxs-lookup"><span data-stu-id="92516-116">tinyint</span></span>  <br/> |<span data-ttu-id="92516-117">주요한</span><span class="sxs-lookup"><span data-stu-id="92516-117">Primary</span></span>  <br/> |<span data-ttu-id="92516-118">분류의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="92516-118">Unique identifier for the classification.</span></span>  <br/> |
|<span data-ttu-id="92516-119">**이름**</span><span class="sxs-lookup"><span data-stu-id="92516-119">**Name**</span></span> <br/> |<span data-ttu-id="92516-120">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="92516-120">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="92516-121">분류에 할당 된 값 및 식별 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="92516-121">Value and friendly name assigned to the classification.</span></span> <span data-ttu-id="92516-122">사용 가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="92516-122">Allowed values are:</span></span> <br/>  <span data-ttu-id="92516-123">0--성공</span><span class="sxs-lookup"><span data-stu-id="92516-123">0 -- Success</span></span> <br/>  <span data-ttu-id="92516-124">1--실패 예상</span><span class="sxs-lookup"><span data-stu-id="92516-124">1 -- Expected failure</span></span> <br/>  <span data-ttu-id="92516-125">2-예기치 않은 오류</span><span class="sxs-lookup"><span data-stu-id="92516-125">2 - Unexpected failure</span></span> <br/> |
   

