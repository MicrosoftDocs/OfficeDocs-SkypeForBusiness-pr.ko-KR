---
title: 사용자 보기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: 사용자 보기에는 통화와 관련 된 사용자에 대 한 정보 또는 데이터베이스에 레코드가 있는 세션이 저장 됩니다. 이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.
ms.openlocfilehash: 1d170b558dbf77cd8ebeff09a914826830d5621d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814836"
---
# <a name="user-view"></a><span data-ttu-id="69d02-104">사용자 보기</span><span class="sxs-lookup"><span data-stu-id="69d02-104">User view</span></span>
 
<span data-ttu-id="69d02-105">사용자 보기에는 통화와 관련 된 사용자에 대 한 정보 또는 데이터베이스에 레코드가 있는 세션이 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="69d02-105">The User view stores information about users who have been involved in calls or sessions that have records in the database.</span></span> <span data-ttu-id="69d02-106">이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="69d02-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="69d02-107">**열**</span><span class="sxs-lookup"><span data-stu-id="69d02-107">**Column**</span></span>|<span data-ttu-id="69d02-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="69d02-108">**Data Type**</span></span>|<span data-ttu-id="69d02-109">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="69d02-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="69d02-110">UserId</span><span class="sxs-lookup"><span data-stu-id="69d02-110">UserId</span></span>  <br/> |<span data-ttu-id="69d02-111">int</span><span class="sxs-lookup"><span data-stu-id="69d02-111">int</span></span>  <br/> |<span data-ttu-id="69d02-112">이 사용자를 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="69d02-112">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="69d02-113">UserUri</span><span class="sxs-lookup"><span data-stu-id="69d02-113">UserUri</span></span>  <br/> |<span data-ttu-id="69d02-114">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="69d02-114">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="69d02-115">사용자의 Uri입니다.</span><span class="sxs-lookup"><span data-stu-id="69d02-115">Uri of the user.</span></span>  <br/> |
|<span data-ttu-id="69d02-116">TenantKey</span><span class="sxs-lookup"><span data-stu-id="69d02-116">TenantKey</span></span>  <br/> |<span data-ttu-id="69d02-117">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="69d02-117">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="69d02-118">사용자의 테 넌 트입니다.</span><span class="sxs-lookup"><span data-stu-id="69d02-118">Tenant of user.</span></span> <span data-ttu-id="69d02-119">자세한 내용은 [테 넌 트 테이블](tenants.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="69d02-119">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="69d02-120">UriType</span><span class="sxs-lookup"><span data-stu-id="69d02-120">UriType</span></span>  <br/> |<span data-ttu-id="69d02-121">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="69d02-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="69d02-122">사용자 URI의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="69d02-122">Type of user URI.</span></span> <span data-ttu-id="69d02-123">자세한 내용은 [UriTypes 테이블](uritypes.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="69d02-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

