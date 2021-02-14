---
title: UserSite 테이블
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
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: UserSite 테이블은 지원 테이블입니다. 각 레코드는 네트워크 구성 설정에 정의된 하나의 사용자 사이트를 나타냅니다.
ms.openlocfilehash: 88df08875ea3254ee355a96aa3b12d3ee7f5ccaf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799918"
---
# <a name="usersite-table"></a><span data-ttu-id="922b0-104">UserSite 테이블</span><span class="sxs-lookup"><span data-stu-id="922b0-104">UserSite table</span></span>
 
<span data-ttu-id="922b0-p102">UserSite 테이블은 지원 테이블입니다. 각 레코드는 네트워크 구성 설정에 정의된 하나의 사용자 사이트를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="922b0-p102">The UserSite table is a supporting table. Each record represents one user site defined in network configuration setting.</span></span>
  
|<span data-ttu-id="922b0-107">**열**</span><span class="sxs-lookup"><span data-stu-id="922b0-107">**Column**</span></span>|<span data-ttu-id="922b0-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="922b0-108">**Data Type**</span></span>|<span data-ttu-id="922b0-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="922b0-109">**Key/Index**</span></span>|<span data-ttu-id="922b0-110">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="922b0-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="922b0-111">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="922b0-111">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="922b0-112">int</span><span class="sxs-lookup"><span data-stu-id="922b0-112">int</span></span>  <br/> |<span data-ttu-id="922b0-113">Primary</span><span class="sxs-lookup"><span data-stu-id="922b0-113">Primary</span></span>  <br/> |<span data-ttu-id="922b0-114">사용자 사이트를 식별하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="922b0-114">Unique number identifying the user site.</span></span>  <br/> |
|<span data-ttu-id="922b0-115">**UserSiteName**</span><span class="sxs-lookup"><span data-stu-id="922b0-115">**UserSiteName**</span></span> <br/> |<span data-ttu-id="922b0-116">nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="922b0-116">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="922b0-117">고유</span><span class="sxs-lookup"><span data-stu-id="922b0-117">Unique</span></span>  <br/> |<span data-ttu-id="922b0-118">사용자 사이트의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="922b0-118">User site's name.</span></span>  <br/> |
|<span data-ttu-id="922b0-119">**RegionKey**</span><span class="sxs-lookup"><span data-stu-id="922b0-119">**RegionKey**</span></span> <br/> |<span data-ttu-id="922b0-120">int</span><span class="sxs-lookup"><span data-stu-id="922b0-120">int</span></span>  <br/> |<span data-ttu-id="922b0-121">외계인</span><span class="sxs-lookup"><span data-stu-id="922b0-121">Foreign</span></span>  <br/> |<span data-ttu-id="922b0-122">[Region 테이블에서 참조됩니다.](region.md)</span><span class="sxs-lookup"><span data-stu-id="922b0-122">Referenced from [Region table](region.md).</span></span>  <br/> |
   

