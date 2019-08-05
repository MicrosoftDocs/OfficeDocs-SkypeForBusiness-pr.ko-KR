---
title: SessionCorrelation 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: SessionCorrelation 관계 테이블은 지원 테이블입니다. 각 레코드는 여러 세션을 연결 하는 데 사용 되는 CorrelationID 하나를 나타냅니다.
ms.openlocfilehash: 3c307b9542b9c1f37967a40ae63979d72e0504ae
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196522"
---
# <a name="sessioncorrelation-table"></a><span data-ttu-id="4d1ad-104">SessionCorrelation 테이블</span><span class="sxs-lookup"><span data-stu-id="4d1ad-104">SessionCorrelation table</span></span>
 
<span data-ttu-id="4d1ad-105">SessionCorrelation 관계 테이블은 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="4d1ad-105">The SessionCorrelation table is a supporting table.</span></span> <span data-ttu-id="4d1ad-106">각 레코드는 여러 세션을 연결 하는 데 사용 되는 CorrelationID 하나를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4d1ad-106">Each record represents one CorrelationID which is used to correlate multiple sessions.</span></span> 
  
|<span data-ttu-id="4d1ad-107">**열**</span><span class="sxs-lookup"><span data-stu-id="4d1ad-107">**Column**</span></span>|<span data-ttu-id="4d1ad-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="4d1ad-108">**Data Type**</span></span>|<span data-ttu-id="4d1ad-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="4d1ad-109">**Key/Index**</span></span>|<span data-ttu-id="4d1ad-110">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="4d1ad-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4d1ad-111">**검사**</span><span class="sxs-lookup"><span data-stu-id="4d1ad-111">**Checksum**</span></span> <br/> |<span data-ttu-id="4d1ad-112">int</span><span class="sxs-lookup"><span data-stu-id="4d1ad-112">int</span></span>  <br/> |||
|<span data-ttu-id="4d1ad-113">**CorrelationKey**</span><span class="sxs-lookup"><span data-stu-id="4d1ad-113">**CorrelationKey**</span></span> <br/> |<span data-ttu-id="4d1ad-114">int</span><span class="sxs-lookup"><span data-stu-id="4d1ad-114">int</span></span>  <br/> |<span data-ttu-id="4d1ad-115">주요한</span><span class="sxs-lookup"><span data-stu-id="4d1ad-115">Primary</span></span>  <br/> |<span data-ttu-id="4d1ad-116">이 A/V 회의 서버를 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="4d1ad-116">Unique number identifying this A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="4d1ad-117">**Legredir**</span><span class="sxs-lookup"><span data-stu-id="4d1ad-117">**CorrelationID**</span></span> <br/> |<span data-ttu-id="4d1ad-118">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="4d1ad-118">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="4d1ad-119">독특한</span><span class="sxs-lookup"><span data-stu-id="4d1ad-119">Unique</span></span>  <br/> |<span data-ttu-id="4d1ad-120">상호 관련 된 세션은 동일한 상관 관계 ID를 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="4d1ad-120">Sessions that are correlated will have the same correlation ID.</span></span>  <br/> |
|<span data-ttu-id="4d1ad-121">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="4d1ad-121">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="4d1ad-122">dmtf</span><span class="sxs-lookup"><span data-stu-id="4d1ad-122">datetime</span></span>  <br/> | <br/> |<span data-ttu-id="4d1ad-123">내부용 으로만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d1ad-123">For internal use only.</span></span>  <br/> |
   

