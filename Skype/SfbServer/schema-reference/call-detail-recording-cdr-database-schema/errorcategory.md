---
title: 비즈니스용 Skype 서버의 ErrorCategory 테이블
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: ErrorCategory 테이블에는 각 비즈니스용 Skype 서버 2015 진단 분류의 이름이 포함되어 있습니다. 기본적으로 비즈니스용 Skype 서버 2015는 다음 분류를 사용 합니다.
ms.openlocfilehash: ca3719f6d284cf715be1a87b1c7a5dc04ae84b04
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813148"
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a><span data-ttu-id="5d84a-104">비즈니스용 Skype 서버의 ErrorCategory 테이블</span><span class="sxs-lookup"><span data-stu-id="5d84a-104">ErrorCategory table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="5d84a-105">ErrorCategory 테이블에는 각 비즈니스용 Skype 서버 2015 진단 분류의 이름이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-105">The ErrorCategory table contains the friendly name for each Skype for Business Server 2015 diagnostic classification.</span></span> <span data-ttu-id="5d84a-106">기본적으로 비즈니스용 Skype 서버 2015는 다음 분류를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-106">By default, Skype for Business Server 2015 uses the following classifications:</span></span>
  
- <span data-ttu-id="5d84a-107">0 -- 성공</span><span class="sxs-lookup"><span data-stu-id="5d84a-107">0 -- Success</span></span>
    
- <span data-ttu-id="5d84a-108">1 -- 예상 오류</span><span class="sxs-lookup"><span data-stu-id="5d84a-108">1 -- Expected failure</span></span>
    
- <span data-ttu-id="5d84a-109">2 - 예기치 않은 오류</span><span class="sxs-lookup"><span data-stu-id="5d84a-109">2 - Unexpected failure</span></span>
    
<span data-ttu-id="5d84a-110">이 표는 Microsoft Lync Server 2013에서 도입된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-110">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="5d84a-111">**열**</span><span class="sxs-lookup"><span data-stu-id="5d84a-111">**Column**</span></span>|<span data-ttu-id="5d84a-112">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="5d84a-112">**Data Type**</span></span>|<span data-ttu-id="5d84a-113">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="5d84a-113">**Key/Index**</span></span>|<span data-ttu-id="5d84a-114">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="5d84a-114">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5d84a-115">**CategoryId**</span><span class="sxs-lookup"><span data-stu-id="5d84a-115">**CategoryId**</span></span> <br/> |<span data-ttu-id="5d84a-116">tinyint</span><span class="sxs-lookup"><span data-stu-id="5d84a-116">tinyint</span></span>  <br/> |<span data-ttu-id="5d84a-117">Primary</span><span class="sxs-lookup"><span data-stu-id="5d84a-117">Primary</span></span>  <br/> |<span data-ttu-id="5d84a-118">분류의 고유한 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-118">Unique identifier for the classification.</span></span>  <br/> |
|<span data-ttu-id="5d84a-119">**이름**</span><span class="sxs-lookup"><span data-stu-id="5d84a-119">**Name**</span></span> <br/> |<span data-ttu-id="5d84a-120">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="5d84a-120">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="5d84a-p103">분류에 할당된 값과 이름입니다. 허용되는 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-p103">Value and friendly name assigned to the classification. Allowed values are:</span></span> <br/>  <span data-ttu-id="5d84a-123">0 -- 성공</span><span class="sxs-lookup"><span data-stu-id="5d84a-123">0 -- Success</span></span> <br/>  <span data-ttu-id="5d84a-124">1 -- 예상 오류</span><span class="sxs-lookup"><span data-stu-id="5d84a-124">1 -- Expected failure</span></span> <br/>  <span data-ttu-id="5d84a-125">2 - 예기치 않은 오류</span><span class="sxs-lookup"><span data-stu-id="5d84a-125">2 - Unexpected failure</span></span> <br/> |
   

