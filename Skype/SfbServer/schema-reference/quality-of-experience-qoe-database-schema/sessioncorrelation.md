---
title: SessionCorrelation 테이블
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
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: SessionCorrelation 테이블은 지원 테이블입니다. 각 레코드는 여러 세션을 상호 관련하는 데 사용되는 하나의 CorrelationID를 나타내며,
ms.openlocfilehash: 36b617517f3642a2150c72369db858eee62a4a87
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802658"
---
# <a name="sessioncorrelation-table"></a><span data-ttu-id="7429d-104">SessionCorrelation 테이블</span><span class="sxs-lookup"><span data-stu-id="7429d-104">SessionCorrelation table</span></span>
 
<span data-ttu-id="7429d-105">SessionCorrelation 테이블은 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="7429d-105">The SessionCorrelation table is a supporting table.</span></span> <span data-ttu-id="7429d-106">각 레코드는 여러 세션을 상호 관련하는 데 사용되는 하나의 CorrelationID를 나타내며,</span><span class="sxs-lookup"><span data-stu-id="7429d-106">Each record represents one CorrelationID which is used to correlate multiple sessions.</span></span> 
  
|<span data-ttu-id="7429d-107">**열**</span><span class="sxs-lookup"><span data-stu-id="7429d-107">**Column**</span></span>|<span data-ttu-id="7429d-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="7429d-108">**Data Type**</span></span>|<span data-ttu-id="7429d-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="7429d-109">**Key/Index**</span></span>|<span data-ttu-id="7429d-110">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="7429d-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7429d-111">**체크 um**</span><span class="sxs-lookup"><span data-stu-id="7429d-111">**Checksum**</span></span> <br/> |<span data-ttu-id="7429d-112">int</span><span class="sxs-lookup"><span data-stu-id="7429d-112">int</span></span>  <br/> |||
|<span data-ttu-id="7429d-113">**CorrelationKey**</span><span class="sxs-lookup"><span data-stu-id="7429d-113">**CorrelationKey**</span></span> <br/> |<span data-ttu-id="7429d-114">int</span><span class="sxs-lookup"><span data-stu-id="7429d-114">int</span></span>  <br/> |<span data-ttu-id="7429d-115">Primary</span><span class="sxs-lookup"><span data-stu-id="7429d-115">Primary</span></span>  <br/> |<span data-ttu-id="7429d-116">이 A/V 회의 서버를 식별하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="7429d-116">Unique number identifying this A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="7429d-117">**CorrelationID**</span><span class="sxs-lookup"><span data-stu-id="7429d-117">**CorrelationID**</span></span> <br/> |<span data-ttu-id="7429d-118">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7429d-118">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="7429d-119">고유</span><span class="sxs-lookup"><span data-stu-id="7429d-119">Unique</span></span>  <br/> |<span data-ttu-id="7429d-120">상관 관계가 있는 세션의 상관 관계 ID는 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="7429d-120">Sessions that are correlated will have the same correlation ID.</span></span>  <br/> |
|<span data-ttu-id="7429d-121">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="7429d-121">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="7429d-122">datetime</span><span class="sxs-lookup"><span data-stu-id="7429d-122">datetime</span></span>  <br/> | <br/> |<span data-ttu-id="7429d-123">내부 용도로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7429d-123">For internal use only.</span></span>  <br/> |
   

