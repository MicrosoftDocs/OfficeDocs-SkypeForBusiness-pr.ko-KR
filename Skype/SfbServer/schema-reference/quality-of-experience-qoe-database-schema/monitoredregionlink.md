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
localization_priority: Normal
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: Monitored국가 링크 테이블은 지원 테이블입니다. 각 레코드는 두 국가/지역 간의 하나의 링크를 나타냅니다.
ms.openlocfilehash: fdace97e0a7c9685f59471074cca64ede4fcc63d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196554"
---
# <a name="monitoredregionlink-table"></a><span data-ttu-id="7a805-104">MonitoredRegionLink 테이블</span><span class="sxs-lookup"><span data-stu-id="7a805-104">MonitoredRegionLink table</span></span>
 
<span data-ttu-id="7a805-105">Monitored국가 링크 테이블은 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="7a805-105">The MonitoredRegionLink table is a supporting table.</span></span> <span data-ttu-id="7a805-106">각 레코드는 두 국가/지역 간의 하나의 링크를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7a805-106">Each record represents one link between two countries/regions.</span></span>
  
|<span data-ttu-id="7a805-107">**열**</span><span class="sxs-lookup"><span data-stu-id="7a805-107">**Column**</span></span>|<span data-ttu-id="7a805-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="7a805-108">**Data Type**</span></span>|<span data-ttu-id="7a805-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="7a805-109">**Key/Index**</span></span>|<span data-ttu-id="7a805-110">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="7a805-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7a805-111">**Region1Key**</span><span class="sxs-lookup"><span data-stu-id="7a805-111">**Region1Key**</span></span> <br/> |<span data-ttu-id="7a805-112">int</span><span class="sxs-lookup"><span data-stu-id="7a805-112">int</span></span>  <br/> |<span data-ttu-id="7a805-113">기본, 외래</span><span class="sxs-lookup"><span data-stu-id="7a805-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="7a805-114">[지역 테이블](region.md)에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a805-114">Referenced from the [Region table](region.md).</span></span>  <br/> |
|<span data-ttu-id="7a805-115">**Region2Key**</span><span class="sxs-lookup"><span data-stu-id="7a805-115">**Region2Key**</span></span> <br/> |<span data-ttu-id="7a805-116">int</span><span class="sxs-lookup"><span data-stu-id="7a805-116">int</span></span>  <br/> |<span data-ttu-id="7a805-117">기본, 외래</span><span class="sxs-lookup"><span data-stu-id="7a805-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="7a805-118">[지역 테이블](region.md)에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a805-118">Referenced from the [Region table](region.md).</span></span>  <br/> |
   

