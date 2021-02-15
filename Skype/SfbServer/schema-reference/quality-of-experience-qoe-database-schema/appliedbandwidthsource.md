---
title: AppliedBandwidthSource 테이블
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
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: AppliedBandwidthSource 테이블은 지원 테이블입니다. 각 레코드는 하나의 소스를 나타냅니다.
ms.openlocfilehash: bf7e1be3b98bcd56fea16dbd7aa7171b056a7f3c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831408"
---
# <a name="appliedbandwidthsource-table"></a><span data-ttu-id="6efcd-104">AppliedBandwidthSource 테이블</span><span class="sxs-lookup"><span data-stu-id="6efcd-104">AppliedBandwidthSource table</span></span>
 
<span data-ttu-id="6efcd-105">AppliedBandwidthSource 테이블은 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="6efcd-105">The AppliedBandwidthSource table is a supporting table.</span></span> <span data-ttu-id="6efcd-106">각 레코드는 하나의 소스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6efcd-106">Each record represents one source.</span></span>
  
|<span data-ttu-id="6efcd-107">**열**</span><span class="sxs-lookup"><span data-stu-id="6efcd-107">**Column**</span></span>|<span data-ttu-id="6efcd-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="6efcd-108">**Data Type**</span></span>|<span data-ttu-id="6efcd-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="6efcd-109">**Key/Index**</span></span>|<span data-ttu-id="6efcd-110">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="6efcd-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6efcd-111">**AppliedBandwidthSourceKey**</span><span class="sxs-lookup"><span data-stu-id="6efcd-111">**AppliedBandwidthSourceKey**</span></span> <br/> |<span data-ttu-id="6efcd-112">int</span><span class="sxs-lookup"><span data-stu-id="6efcd-112">int</span></span>  <br/> |<span data-ttu-id="6efcd-113">Primary</span><span class="sxs-lookup"><span data-stu-id="6efcd-113">Primary</span></span>  <br/> |<span data-ttu-id="6efcd-114">원본을 식별하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="6efcd-114">Unique number identifying the source.</span></span>  <br/> |
|<span data-ttu-id="6efcd-115">**AppliedBandwidthSource**</span><span class="sxs-lookup"><span data-stu-id="6efcd-115">**AppliedBandwidthSource**</span></span> <br/> |<span data-ttu-id="6efcd-116">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="6efcd-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="6efcd-117">고유</span><span class="sxs-lookup"><span data-stu-id="6efcd-117">Unique</span></span>  <br/> |<span data-ttu-id="6efcd-118">대역폭 한도가 부과되는 원본입니다.</span><span class="sxs-lookup"><span data-stu-id="6efcd-118">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="6efcd-119">대역폭 제한이 시작되는 위치(예: "정책 서버", "TURN Server" 또는 "Modality")를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6efcd-119">It describes where the bandwidth limit is coming from (for example, "Policy Server", "TURN Server", or "Modality").</span></span>  <br/> |
   

