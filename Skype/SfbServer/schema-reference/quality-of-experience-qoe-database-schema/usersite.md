---
title: UserSite 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: UserSite 테이블은 지원 테이블입니다. 각 레코드는 네트워크 구성 설정에 정의 된 사용자 사이트 하나를 나타냅니다.
ms.openlocfilehash: 21f60afdb1690024f85dc74e11f856642413e6a8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196508"
---
# <a name="usersite-table"></a><span data-ttu-id="887e3-104">UserSite 테이블</span><span class="sxs-lookup"><span data-stu-id="887e3-104">UserSite table</span></span>
 
<span data-ttu-id="887e3-105">UserSite 테이블은 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="887e3-105">The UserSite table is a supporting table.</span></span> <span data-ttu-id="887e3-106">각 레코드는 네트워크 구성 설정에 정의 된 사용자 사이트 하나를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="887e3-106">Each record represents one user site defined in network configuration setting.</span></span>
  
|<span data-ttu-id="887e3-107">**열**</span><span class="sxs-lookup"><span data-stu-id="887e3-107">**Column**</span></span>|<span data-ttu-id="887e3-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="887e3-108">**Data Type**</span></span>|<span data-ttu-id="887e3-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="887e3-109">**Key/Index**</span></span>|<span data-ttu-id="887e3-110">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="887e3-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="887e3-111">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="887e3-111">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="887e3-112">int</span><span class="sxs-lookup"><span data-stu-id="887e3-112">int</span></span>  <br/> |<span data-ttu-id="887e3-113">주요한</span><span class="sxs-lookup"><span data-stu-id="887e3-113">Primary</span></span>  <br/> |<span data-ttu-id="887e3-114">사용자 사이트를 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="887e3-114">Unique number identifying the user site.</span></span>  <br/> |
|<span data-ttu-id="887e3-115">**UserSiteName**</span><span class="sxs-lookup"><span data-stu-id="887e3-115">**UserSiteName**</span></span> <br/> |<span data-ttu-id="887e3-116">name</span><span class="sxs-lookup"><span data-stu-id="887e3-116">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="887e3-117">독특한</span><span class="sxs-lookup"><span data-stu-id="887e3-117">Unique</span></span>  <br/> |<span data-ttu-id="887e3-118">사용자 사이트의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="887e3-118">User site's name.</span></span>  <br/> |
|<span data-ttu-id="887e3-119">**국가 키**</span><span class="sxs-lookup"><span data-stu-id="887e3-119">**RegionKey**</span></span> <br/> |<span data-ttu-id="887e3-120">int</span><span class="sxs-lookup"><span data-stu-id="887e3-120">int</span></span>  <br/> |<span data-ttu-id="887e3-121">외부</span><span class="sxs-lookup"><span data-stu-id="887e3-121">Foreign</span></span>  <br/> |<span data-ttu-id="887e3-122">[지역 테이블](region.md)에서 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="887e3-122">Referenced from [Region table](region.md).</span></span>  <br/> |
   

