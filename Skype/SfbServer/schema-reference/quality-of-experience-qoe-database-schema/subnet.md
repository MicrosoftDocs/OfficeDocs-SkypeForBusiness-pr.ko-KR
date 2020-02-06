---
title: Subnet 테이블
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
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: 서브넷 테이블은 지원 테이블입니다. 각 레코드는 네트워크 구성 설정에 정의 된 하나의 서브넷을 나타냅니다.
ms.openlocfilehash: 562684fdb4df9ac90216489c209754309885fa98
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805206"
---
# <a name="subnet-table"></a><span data-ttu-id="fcaa7-104">Subnet 테이블</span><span class="sxs-lookup"><span data-stu-id="fcaa7-104">Subnet table</span></span>
 
<span data-ttu-id="fcaa7-105">서브넷 테이블은 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="fcaa7-105">The Subnet table is a supporting table.</span></span> <span data-ttu-id="fcaa7-106">각 레코드는 네트워크 구성 설정에 정의 된 하나의 서브넷을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fcaa7-106">Each record represents one subnet defined in network configuration setting.</span></span>
  
|<span data-ttu-id="fcaa7-107">**열**</span><span class="sxs-lookup"><span data-stu-id="fcaa7-107">**Column**</span></span>|<span data-ttu-id="fcaa7-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="fcaa7-108">**Data Type**</span></span>|<span data-ttu-id="fcaa7-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="fcaa7-109">**Key/Index**</span></span>|<span data-ttu-id="fcaa7-110">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="fcaa7-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fcaa7-111">**SubnetIP**</span><span class="sxs-lookup"><span data-stu-id="fcaa7-111">**SubnetIP**</span></span> <br/> |<span data-ttu-id="fcaa7-112">int</span><span class="sxs-lookup"><span data-stu-id="fcaa7-112">int</span></span>  <br/> |<span data-ttu-id="fcaa7-113">기본, 외래</span><span class="sxs-lookup"><span data-stu-id="fcaa7-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="fcaa7-114">서브넷 IP에 대 한 정수 표현입니다.</span><span class="sxs-lookup"><span data-stu-id="fcaa7-114">Integer representation for the subnet IP.</span></span>  <br/> |
|<span data-ttu-id="fcaa7-115">**SubnetMask**</span><span class="sxs-lookup"><span data-stu-id="fcaa7-115">**SubnetMask**</span></span> <br/> |<span data-ttu-id="fcaa7-116">int</span><span class="sxs-lookup"><span data-stu-id="fcaa7-116">int</span></span>  <br/> ||<span data-ttu-id="fcaa7-117">서브넷 마스크.</span><span class="sxs-lookup"><span data-stu-id="fcaa7-117">Subnet mask.</span></span>  <br/> |
|<span data-ttu-id="fcaa7-118">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="fcaa7-118">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="fcaa7-119">int</span><span class="sxs-lookup"><span data-stu-id="fcaa7-119">int</span></span>  <br/> |<span data-ttu-id="fcaa7-120">외부</span><span class="sxs-lookup"><span data-stu-id="fcaa7-120">Foreign</span></span>  <br/> |<span data-ttu-id="fcaa7-121">[Usersite 테이블](usersite.md)에서 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcaa7-121">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="fcaa7-122">**SubnetDescription**</span><span class="sxs-lookup"><span data-stu-id="fcaa7-122">**SubnetDescription**</span></span> <br/> |<span data-ttu-id="fcaa7-123">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="fcaa7-123">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="fcaa7-124">서브넷에 대 한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="fcaa7-124">The description for the subnet.</span></span>  <br/> |
   

