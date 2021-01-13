---
title: 서브넷 테이블
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
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: Subnet 테이블은 지원 테이블입니다. 각 레코드는 네트워크 구성 설정에 정의된 하나의 서브넷을 나타냅니다.
ms.openlocfilehash: b4683c654d5d188d2f5096dd7ec9da124001f68b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831338"
---
# <a name="subnet-table"></a><span data-ttu-id="9e185-104">서브넷 테이블</span><span class="sxs-lookup"><span data-stu-id="9e185-104">Subnet table</span></span>
 
<span data-ttu-id="9e185-p102">Subnet 테이블은 지원 테이블입니다. 각 레코드는 네트워크 구성 설정에 정의된 하나의 서브넷을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9e185-p102">The Subnet table is a supporting table. Each record represents one subnet defined in network configuration setting.</span></span>
  
|<span data-ttu-id="9e185-107">**열**</span><span class="sxs-lookup"><span data-stu-id="9e185-107">**Column**</span></span>|<span data-ttu-id="9e185-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="9e185-108">**Data Type**</span></span>|<span data-ttu-id="9e185-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="9e185-109">**Key/Index**</span></span>|<span data-ttu-id="9e185-110">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="9e185-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9e185-111">**SubnetIP**</span><span class="sxs-lookup"><span data-stu-id="9e185-111">**SubnetIP**</span></span> <br/> |<span data-ttu-id="9e185-112">int</span><span class="sxs-lookup"><span data-stu-id="9e185-112">int</span></span>  <br/> |<span data-ttu-id="9e185-113">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="9e185-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="9e185-114">정수로 표시된 서브넷 IP입니다.</span><span class="sxs-lookup"><span data-stu-id="9e185-114">Integer representation for the subnet IP.</span></span>  <br/> |
|<span data-ttu-id="9e185-115">**SubnetMask**</span><span class="sxs-lookup"><span data-stu-id="9e185-115">**SubnetMask**</span></span> <br/> |<span data-ttu-id="9e185-116">int</span><span class="sxs-lookup"><span data-stu-id="9e185-116">int</span></span>  <br/> ||<span data-ttu-id="9e185-117">서브넷 마스크입니다.</span><span class="sxs-lookup"><span data-stu-id="9e185-117">Subnet mask.</span></span>  <br/> |
|<span data-ttu-id="9e185-118">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="9e185-118">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="9e185-119">int</span><span class="sxs-lookup"><span data-stu-id="9e185-119">int</span></span>  <br/> |<span data-ttu-id="9e185-120">외계인</span><span class="sxs-lookup"><span data-stu-id="9e185-120">Foreign</span></span>  <br/> |<span data-ttu-id="9e185-121">[UserSite 테이블에서 참조됩니다.](usersite.md)</span><span class="sxs-lookup"><span data-stu-id="9e185-121">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="9e185-122">**SubnetDescription**</span><span class="sxs-lookup"><span data-stu-id="9e185-122">**SubnetDescription**</span></span> <br/> |<span data-ttu-id="9e185-123">nvarchar(512)</span><span class="sxs-lookup"><span data-stu-id="9e185-123">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="9e185-124">서브넷에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="9e185-124">The description for the subnet.</span></span>  <br/> |
   

