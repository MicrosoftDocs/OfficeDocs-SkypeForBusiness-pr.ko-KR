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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: UserSite 테이블은 지원 테이블입니다. 각 레코드는 네트워크 구성 설정에 정의 된 사용자 사이트 하나를 나타냅니다.
ms.openlocfilehash: e1d6c4ddc3a756f2e5df0713d6abe1cb7b61295f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805006"
---
# <a name="usersite-table"></a><span data-ttu-id="a302d-104">UserSite 테이블</span><span class="sxs-lookup"><span data-stu-id="a302d-104">UserSite table</span></span>
 
<span data-ttu-id="a302d-105">UserSite 테이블은 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="a302d-105">The UserSite table is a supporting table.</span></span> <span data-ttu-id="a302d-106">각 레코드는 네트워크 구성 설정에 정의 된 사용자 사이트 하나를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a302d-106">Each record represents one user site defined in network configuration setting.</span></span>
  
|<span data-ttu-id="a302d-107">**열**</span><span class="sxs-lookup"><span data-stu-id="a302d-107">**Column**</span></span>|<span data-ttu-id="a302d-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="a302d-108">**Data Type**</span></span>|<span data-ttu-id="a302d-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="a302d-109">**Key/Index**</span></span>|<span data-ttu-id="a302d-110">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="a302d-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a302d-111">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="a302d-111">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="a302d-112">int</span><span class="sxs-lookup"><span data-stu-id="a302d-112">int</span></span>  <br/> |<span data-ttu-id="a302d-113">주요한</span><span class="sxs-lookup"><span data-stu-id="a302d-113">Primary</span></span>  <br/> |<span data-ttu-id="a302d-114">사용자 사이트를 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="a302d-114">Unique number identifying the user site.</span></span>  <br/> |
|<span data-ttu-id="a302d-115">**UserSiteName**</span><span class="sxs-lookup"><span data-stu-id="a302d-115">**UserSiteName**</span></span> <br/> |<span data-ttu-id="a302d-116">name</span><span class="sxs-lookup"><span data-stu-id="a302d-116">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="a302d-117">독특한</span><span class="sxs-lookup"><span data-stu-id="a302d-117">Unique</span></span>  <br/> |<span data-ttu-id="a302d-118">사용자 사이트의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="a302d-118">User site's name.</span></span>  <br/> |
|<span data-ttu-id="a302d-119">**국가 키**</span><span class="sxs-lookup"><span data-stu-id="a302d-119">**RegionKey**</span></span> <br/> |<span data-ttu-id="a302d-120">int</span><span class="sxs-lookup"><span data-stu-id="a302d-120">int</span></span>  <br/> |<span data-ttu-id="a302d-121">외부</span><span class="sxs-lookup"><span data-stu-id="a302d-121">Foreign</span></span>  <br/> |<span data-ttu-id="a302d-122">[지역 테이블](region.md)에서 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="a302d-122">Referenced from [Region table](region.md).</span></span>  <br/> |
   

