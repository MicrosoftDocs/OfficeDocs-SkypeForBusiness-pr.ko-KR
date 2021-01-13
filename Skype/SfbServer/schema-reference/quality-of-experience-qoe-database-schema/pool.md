---
title: Pool 테이블
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
ms.assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
description: Pool 테이블은 여러 프런트 엔드 풀에 대한 정보를 저장하는 지원 테이블입니다. 테이블의 각 레코드는 하나의 풀을 나타냅니다.
ms.openlocfilehash: e90b9b2a34a184e1d8cdb23dc3d33b1c41367584
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815818"
---
# <a name="pool-table"></a><span data-ttu-id="e00fe-104">Pool 테이블</span><span class="sxs-lookup"><span data-stu-id="e00fe-104">Pool table</span></span>
 
<span data-ttu-id="e00fe-p102">Pool 테이블은 여러 프런트 엔드 풀에 대한 정보를 저장하는 지원 테이블입니다. 테이블의 각 레코드는 하나의 풀을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e00fe-p102">The Pool table is a supporting table that stores information about the various Front End pools. Each record in the table represents one pool.</span></span>
  
|<span data-ttu-id="e00fe-107">**열**</span><span class="sxs-lookup"><span data-stu-id="e00fe-107">**Column**</span></span>|<span data-ttu-id="e00fe-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="e00fe-108">**Data Type**</span></span>|<span data-ttu-id="e00fe-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="e00fe-109">**Key/Index**</span></span>|<span data-ttu-id="e00fe-110">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="e00fe-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e00fe-111">**PoolKey**</span><span class="sxs-lookup"><span data-stu-id="e00fe-111">**PoolKey**</span></span> <br/> |<span data-ttu-id="e00fe-112">int</span><span class="sxs-lookup"><span data-stu-id="e00fe-112">int</span></span>  <br/> |<span data-ttu-id="e00fe-113">Primary</span><span class="sxs-lookup"><span data-stu-id="e00fe-113">Primary</span></span>  <br/> |<span data-ttu-id="e00fe-114">이 풀을 식별하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="e00fe-114">Unique number identifying this pool.</span></span>  <br/> |
|<span data-ttu-id="e00fe-115">**PoolName**</span><span class="sxs-lookup"><span data-stu-id="e00fe-115">**PoolName**</span></span> <br/> |<span data-ttu-id="e00fe-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e00fe-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="e00fe-117">고유</span><span class="sxs-lookup"><span data-stu-id="e00fe-117">Unique</span></span>  <br/> |<span data-ttu-id="e00fe-118">풀 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="e00fe-118">Pool FQDN.</span></span>  <br/> |
   

