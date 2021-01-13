---
title: Users 테이블
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: Users 테이블은 지원 테이블입니다. 테이블의 각 레코드에는 데이터베이스에 레코드가 있는 통화 또는 세션에 관련된 한 사용자에 대한 정보가 저장됩니다.
ms.openlocfilehash: 1905efa9b87b0b94c55e3a72e8be86e9ab191661
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831618"
---
# <a name="users-table"></a><span data-ttu-id="96779-104">Users 테이블</span><span class="sxs-lookup"><span data-stu-id="96779-104">Users table</span></span>
 
<span data-ttu-id="96779-105">Users 테이블은 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="96779-105">The Users table is a supporting table.</span></span> <span data-ttu-id="96779-106">테이블의 각 레코드에는 데이터베이스에 레코드가 있는 통화 또는 세션에 관련된 한 사용자에 대한 정보가 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="96779-106">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>
  
|<span data-ttu-id="96779-107">**열**</span><span class="sxs-lookup"><span data-stu-id="96779-107">**Column**</span></span>|<span data-ttu-id="96779-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="96779-108">**Data Type**</span></span>|<span data-ttu-id="96779-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="96779-109">**Key/Index**</span></span>|<span data-ttu-id="96779-110">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="96779-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="96779-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="96779-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="96779-112">datetime</span><span class="sxs-lookup"><span data-stu-id="96779-112">datetime</span></span>  <br/> ||<span data-ttu-id="96779-113">내부용 타임스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="96779-113">Time stamp for internal use.</span></span>  <br/> |
|<span data-ttu-id="96779-114">**UserId**</span><span class="sxs-lookup"><span data-stu-id="96779-114">**UserId**</span></span> <br/> |<span data-ttu-id="96779-115">int</span><span class="sxs-lookup"><span data-stu-id="96779-115">int</span></span>  <br/> |<span data-ttu-id="96779-116">Primary</span><span class="sxs-lookup"><span data-stu-id="96779-116">Primary</span></span>  <br/> |<span data-ttu-id="96779-117">이 사용자를 식별하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="96779-117">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="96779-118">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="96779-118">**UserUri**</span></span> <br/> |<span data-ttu-id="96779-119">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="96779-119">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="96779-120">사용자 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="96779-120">User URI.</span></span>  <br/> |
|<span data-ttu-id="96779-121">**TenantId**</span><span class="sxs-lookup"><span data-stu-id="96779-121">**TenantId**</span></span> <br/> |<span data-ttu-id="96779-122">int</span><span class="sxs-lookup"><span data-stu-id="96779-122">int</span></span>  <br/> |<span data-ttu-id="96779-123">외계인</span><span class="sxs-lookup"><span data-stu-id="96779-123">Foreign</span></span>  <br/> |<span data-ttu-id="96779-124">이 사용자의 테넌트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="96779-124">This user's Tenant ID.</span></span> <span data-ttu-id="96779-125">자세한 내용은 [Tenants 테이블을](tenants.md) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="96779-125">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="96779-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="96779-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="96779-127">int</span><span class="sxs-lookup"><span data-stu-id="96779-127">int</span></span>  <br/> |<span data-ttu-id="96779-128">외계인</span><span class="sxs-lookup"><span data-stu-id="96779-128">Foreign</span></span>  <br/> |<span data-ttu-id="96779-129">이 사용자의 URI 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="96779-129">This user's URI type.</span></span> <span data-ttu-id="96779-130">자세한 내용은 [UriTypes 테이블을](uritypes.md) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="96779-130">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

