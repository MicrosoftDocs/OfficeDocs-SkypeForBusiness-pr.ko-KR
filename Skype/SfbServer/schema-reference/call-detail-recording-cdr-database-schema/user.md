---
title: 사용자 보기
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
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: 사용자 보기에는 데이터베이스의 레코드를 포함하는 통화 또는 세션에 포함된 사용자에 대한 정보가 저장됩니다. 이 보기는 Microsoft Lync Server 2013에서 도입했습니다.
ms.openlocfilehash: 03af849f9185d90d1c7888c1946b47ee2ef38db4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831698"
---
# <a name="user-view"></a><span data-ttu-id="41575-104">사용자 보기</span><span class="sxs-lookup"><span data-stu-id="41575-104">User view</span></span>
 
<span data-ttu-id="41575-105">사용자 보기에는 데이터베이스의 레코드를 포함하는 통화 또는 세션에 포함된 사용자에 대한 정보가 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="41575-105">The User view stores information about users who have been involved in calls or sessions that have records in the database.</span></span> <span data-ttu-id="41575-106">이 보기는 Microsoft Lync Server 2013에서 도입했습니다.</span><span class="sxs-lookup"><span data-stu-id="41575-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="41575-107">**열**</span><span class="sxs-lookup"><span data-stu-id="41575-107">**Column**</span></span>|<span data-ttu-id="41575-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="41575-108">**Data Type**</span></span>|<span data-ttu-id="41575-109">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="41575-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="41575-110">UserId</span><span class="sxs-lookup"><span data-stu-id="41575-110">UserId</span></span>  <br/> |<span data-ttu-id="41575-111">int</span><span class="sxs-lookup"><span data-stu-id="41575-111">int</span></span>  <br/> |<span data-ttu-id="41575-112">이 사용자를 식별하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="41575-112">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="41575-113">UserUri</span><span class="sxs-lookup"><span data-stu-id="41575-113">UserUri</span></span>  <br/> |<span data-ttu-id="41575-114">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="41575-114">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="41575-115">사용자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="41575-115">Uri of the user.</span></span>  <br/> |
|<span data-ttu-id="41575-116">TenantKey</span><span class="sxs-lookup"><span data-stu-id="41575-116">TenantKey</span></span>  <br/> |<span data-ttu-id="41575-117">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="41575-117">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="41575-118">사용자의 테넌트입니다.</span><span class="sxs-lookup"><span data-stu-id="41575-118">Tenant of user.</span></span> <span data-ttu-id="41575-119">자세한 내용은 [Tenants 테이블을](tenants.md) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="41575-119">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="41575-120">UriType</span><span class="sxs-lookup"><span data-stu-id="41575-120">UriType</span></span>  <br/> |<span data-ttu-id="41575-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="41575-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="41575-122">사용자 URI의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="41575-122">Type of user URI.</span></span> <span data-ttu-id="41575-123">자세한 내용은 [UriTypes 테이블을](uritypes.md) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="41575-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

