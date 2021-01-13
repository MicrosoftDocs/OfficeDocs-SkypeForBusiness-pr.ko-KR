---
title: MonitoredRegionLink 테이블
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
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: MonitoredRegionLink 테이블은 지원 테이블입니다. 각 레코드는 두 국가/지역 간의 한 링크를 나타내며,
ms.openlocfilehash: f30ba249f89a2247e0e03c71fc97f05e69c59bcd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806348"
---
# <a name="monitoredregionlink-table"></a><span data-ttu-id="caea7-104">MonitoredRegionLink 테이블</span><span class="sxs-lookup"><span data-stu-id="caea7-104">MonitoredRegionLink table</span></span>
 
<span data-ttu-id="caea7-105">MonitoredRegionLink 테이블은 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="caea7-105">The MonitoredRegionLink table is a supporting table.</span></span> <span data-ttu-id="caea7-106">각 레코드는 두 국가/지역 간의 한 링크를 나타내며,</span><span class="sxs-lookup"><span data-stu-id="caea7-106">Each record represents one link between two countries/regions.</span></span>
  
|<span data-ttu-id="caea7-107">**열**</span><span class="sxs-lookup"><span data-stu-id="caea7-107">**Column**</span></span>|<span data-ttu-id="caea7-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="caea7-108">**Data Type**</span></span>|<span data-ttu-id="caea7-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="caea7-109">**Key/Index**</span></span>|<span data-ttu-id="caea7-110">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="caea7-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="caea7-111">**Region1Key**</span><span class="sxs-lookup"><span data-stu-id="caea7-111">**Region1Key**</span></span> <br/> |<span data-ttu-id="caea7-112">int</span><span class="sxs-lookup"><span data-stu-id="caea7-112">int</span></span>  <br/> |<span data-ttu-id="caea7-113">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="caea7-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="caea7-114">[Region 테이블에서 참조됩니다.](region.md)</span><span class="sxs-lookup"><span data-stu-id="caea7-114">Referenced from the [Region table](region.md).</span></span>  <br/> |
|<span data-ttu-id="caea7-115">**Region2Key**</span><span class="sxs-lookup"><span data-stu-id="caea7-115">**Region2Key**</span></span> <br/> |<span data-ttu-id="caea7-116">int</span><span class="sxs-lookup"><span data-stu-id="caea7-116">int</span></span>  <br/> |<span data-ttu-id="caea7-117">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="caea7-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="caea7-118">[Region 테이블에서 참조됩니다.](region.md)</span><span class="sxs-lookup"><span data-stu-id="caea7-118">Referenced from the [Region table](region.md).</span></span>  <br/> |
   

