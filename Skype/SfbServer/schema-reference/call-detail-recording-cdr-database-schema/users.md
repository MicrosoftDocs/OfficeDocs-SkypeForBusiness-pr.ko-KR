---
title: Users 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: 사용자 테이블은 지원 테이블입니다. 테이블의 각 레코드에는 데이터베이스의 레코드를 포함 하는 호출 또는 세션과 관련 된 한 사용자에 대 한 정보가 저장 됩니다.
ms.openlocfilehash: 0dcc2fda73305be2bbe6a7a5c546dac0b05f8273
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196671"
---
# <a name="users-table"></a><span data-ttu-id="553c8-104">Users 테이블</span><span class="sxs-lookup"><span data-stu-id="553c8-104">Users table</span></span>
 
<span data-ttu-id="553c8-105">사용자 테이블은 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="553c8-105">The Users table is a supporting table.</span></span> <span data-ttu-id="553c8-106">테이블의 각 레코드에는 데이터베이스의 레코드를 포함 하는 호출 또는 세션과 관련 된 한 사용자에 대 한 정보가 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="553c8-106">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>
  
|<span data-ttu-id="553c8-107">**열**</span><span class="sxs-lookup"><span data-stu-id="553c8-107">**Column**</span></span>|<span data-ttu-id="553c8-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="553c8-108">**Data Type**</span></span>|<span data-ttu-id="553c8-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="553c8-109">**Key/Index**</span></span>|<span data-ttu-id="553c8-110">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="553c8-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="553c8-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="553c8-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="553c8-112">dmtf</span><span class="sxs-lookup"><span data-stu-id="553c8-112">datetime</span></span>  <br/> ||<span data-ttu-id="553c8-113">내부 사용을 위한 타임 스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="553c8-113">Time stamp for internal use.</span></span>  <br/> |
|<span data-ttu-id="553c8-114">**UserId**</span><span class="sxs-lookup"><span data-stu-id="553c8-114">**UserId**</span></span> <br/> |<span data-ttu-id="553c8-115">int</span><span class="sxs-lookup"><span data-stu-id="553c8-115">int</span></span>  <br/> |<span data-ttu-id="553c8-116">주요한</span><span class="sxs-lookup"><span data-stu-id="553c8-116">Primary</span></span>  <br/> |<span data-ttu-id="553c8-117">이 사용자를 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="553c8-117">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="553c8-118">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="553c8-118">**UserUri**</span></span> <br/> |<span data-ttu-id="553c8-119">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="553c8-119">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="553c8-120">사용자 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="553c8-120">User URI.</span></span>  <br/> |
|<span data-ttu-id="553c8-121">**TenantId**</span><span class="sxs-lookup"><span data-stu-id="553c8-121">**TenantId**</span></span> <br/> |<span data-ttu-id="553c8-122">int</span><span class="sxs-lookup"><span data-stu-id="553c8-122">int</span></span>  <br/> |<span data-ttu-id="553c8-123">외부</span><span class="sxs-lookup"><span data-stu-id="553c8-123">Foreign</span></span>  <br/> |<span data-ttu-id="553c8-124">이 사용자의 테 넌 트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="553c8-124">This user's Tenant ID.</span></span> <span data-ttu-id="553c8-125">자세한 내용은 [테 넌 트 테이블](tenants.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="553c8-125">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="553c8-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="553c8-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="553c8-127">int</span><span class="sxs-lookup"><span data-stu-id="553c8-127">int</span></span>  <br/> |<span data-ttu-id="553c8-128">외부</span><span class="sxs-lookup"><span data-stu-id="553c8-128">Foreign</span></span>  <br/> |<span data-ttu-id="553c8-129">이 사용자의 URI 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="553c8-129">This user's URI type.</span></span> <span data-ttu-id="553c8-130">자세한 내용은 [UriTypes 테이블](uritypes.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="553c8-130">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

