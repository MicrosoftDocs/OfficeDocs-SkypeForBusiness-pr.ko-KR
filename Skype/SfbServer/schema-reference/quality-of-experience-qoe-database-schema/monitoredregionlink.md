---
title: MonitoredRegionLink 테이블
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
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: Monitored국가 링크 테이블은 지원 테이블입니다. 각 레코드는 두 국가/지역 간의 하나의 링크를 나타냅니다.
ms.openlocfilehash: a6b92460e2b097460681023f7d6877f02c046bdc
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807816"
---
# <a name="monitoredregionlink-table"></a><span data-ttu-id="18d6f-104">MonitoredRegionLink 테이블</span><span class="sxs-lookup"><span data-stu-id="18d6f-104">MonitoredRegionLink table</span></span>
 
<span data-ttu-id="18d6f-105">Monitored국가 링크 테이블은 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="18d6f-105">The MonitoredRegionLink table is a supporting table.</span></span> <span data-ttu-id="18d6f-106">각 레코드는 두 국가/지역 간의 하나의 링크를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="18d6f-106">Each record represents one link between two countries/regions.</span></span>
  
|<span data-ttu-id="18d6f-107">**열**</span><span class="sxs-lookup"><span data-stu-id="18d6f-107">**Column**</span></span>|<span data-ttu-id="18d6f-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="18d6f-108">**Data Type**</span></span>|<span data-ttu-id="18d6f-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="18d6f-109">**Key/Index**</span></span>|<span data-ttu-id="18d6f-110">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="18d6f-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="18d6f-111">**Region1Key**</span><span class="sxs-lookup"><span data-stu-id="18d6f-111">**Region1Key**</span></span> <br/> |<span data-ttu-id="18d6f-112">int</span><span class="sxs-lookup"><span data-stu-id="18d6f-112">int</span></span>  <br/> |<span data-ttu-id="18d6f-113">기본, 외래</span><span class="sxs-lookup"><span data-stu-id="18d6f-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="18d6f-114">[지역 테이블](region.md)에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="18d6f-114">Referenced from the [Region table](region.md).</span></span>  <br/> |
|<span data-ttu-id="18d6f-115">**Region2Key**</span><span class="sxs-lookup"><span data-stu-id="18d6f-115">**Region2Key**</span></span> <br/> |<span data-ttu-id="18d6f-116">int</span><span class="sxs-lookup"><span data-stu-id="18d6f-116">int</span></span>  <br/> |<span data-ttu-id="18d6f-117">기본, 외래</span><span class="sxs-lookup"><span data-stu-id="18d6f-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="18d6f-118">[지역 테이블](region.md)에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="18d6f-118">Referenced from the [Region table](region.md).</span></span>  <br/> |
   

