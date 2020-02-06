---
title: AppliedBandwidthSource 테이블
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
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: AppliedBandwidthSource 테이블은 지원 테이블입니다. 각 레코드는 하나의 원본을 나타냅니다.
ms.openlocfilehash: 875f6d105a2fef0bf710e57ec389bee4f2613c66
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41811446"
---
# <a name="appliedbandwidthsource-table"></a><span data-ttu-id="04e1f-104">AppliedBandwidthSource 테이블</span><span class="sxs-lookup"><span data-stu-id="04e1f-104">AppliedBandwidthSource table</span></span>
 
<span data-ttu-id="04e1f-105">AppliedBandwidthSource 테이블은 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="04e1f-105">The AppliedBandwidthSource table is a supporting table.</span></span> <span data-ttu-id="04e1f-106">각 레코드는 하나의 원본을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="04e1f-106">Each record represents one source.</span></span>
  
|<span data-ttu-id="04e1f-107">**열**</span><span class="sxs-lookup"><span data-stu-id="04e1f-107">**Column**</span></span>|<span data-ttu-id="04e1f-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="04e1f-108">**Data Type**</span></span>|<span data-ttu-id="04e1f-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="04e1f-109">**Key/Index**</span></span>|<span data-ttu-id="04e1f-110">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="04e1f-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="04e1f-111">**AppliedBandwidthSourceKey**</span><span class="sxs-lookup"><span data-stu-id="04e1f-111">**AppliedBandwidthSourceKey**</span></span> <br/> |<span data-ttu-id="04e1f-112">int</span><span class="sxs-lookup"><span data-stu-id="04e1f-112">int</span></span>  <br/> |<span data-ttu-id="04e1f-113">주요한</span><span class="sxs-lookup"><span data-stu-id="04e1f-113">Primary</span></span>  <br/> |<span data-ttu-id="04e1f-114">출처를 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="04e1f-114">Unique number identifying the source.</span></span>  <br/> |
|<span data-ttu-id="04e1f-115">**AppliedBandwidthSource**</span><span class="sxs-lookup"><span data-stu-id="04e1f-115">**AppliedBandwidthSource**</span></span> <br/> |<span data-ttu-id="04e1f-116">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="04e1f-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="04e1f-117">독특한</span><span class="sxs-lookup"><span data-stu-id="04e1f-117">Unique</span></span>  <br/> |<span data-ttu-id="04e1f-118">적용 되는 대역폭 cap의 원본입니다.</span><span class="sxs-lookup"><span data-stu-id="04e1f-118">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="04e1f-119">대역폭 한도가 시작 되는 위치를 설명 합니다 (예: "정책 서버", "서버 설정" 또는 "모달").</span><span class="sxs-lookup"><span data-stu-id="04e1f-119">It describes where the bandwidth limit is coming from (for example, "Policy Server", "TURN Server", or "Modality").</span></span>  <br/> |
   

