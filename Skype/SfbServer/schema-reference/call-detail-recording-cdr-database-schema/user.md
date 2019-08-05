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
localization_priority: Normal
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: 사용자 보기에는 통화와 관련 된 사용자에 대 한 정보 또는 데이터베이스에 레코드가 있는 세션이 저장 됩니다. 이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.
ms.openlocfilehash: 2fe0ba4748a776a8f17065a3c5db21d34bd6340d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196676"
---
# <a name="user-view"></a><span data-ttu-id="566ac-104">사용자 보기</span><span class="sxs-lookup"><span data-stu-id="566ac-104">User view</span></span>
 
<span data-ttu-id="566ac-105">사용자 보기에는 통화와 관련 된 사용자에 대 한 정보 또는 데이터베이스에 레코드가 있는 세션이 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="566ac-105">The User view stores information about users who have been involved in calls or sessions that have records in the database.</span></span> <span data-ttu-id="566ac-106">이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="566ac-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="566ac-107">**열**</span><span class="sxs-lookup"><span data-stu-id="566ac-107">**Column**</span></span>|<span data-ttu-id="566ac-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="566ac-108">**Data Type**</span></span>|<span data-ttu-id="566ac-109">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="566ac-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="566ac-110">UserId</span><span class="sxs-lookup"><span data-stu-id="566ac-110">UserId</span></span>  <br/> |<span data-ttu-id="566ac-111">int</span><span class="sxs-lookup"><span data-stu-id="566ac-111">int</span></span>  <br/> |<span data-ttu-id="566ac-112">이 사용자를 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="566ac-112">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="566ac-113">UserUri</span><span class="sxs-lookup"><span data-stu-id="566ac-113">UserUri</span></span>  <br/> |<span data-ttu-id="566ac-114">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="566ac-114">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="566ac-115">사용자의 Uri입니다.</span><span class="sxs-lookup"><span data-stu-id="566ac-115">Uri of the user.</span></span>  <br/> |
|<span data-ttu-id="566ac-116">TenantKey</span><span class="sxs-lookup"><span data-stu-id="566ac-116">TenantKey</span></span>  <br/> |<span data-ttu-id="566ac-117">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="566ac-117">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="566ac-118">사용자의 테 넌 트입니다.</span><span class="sxs-lookup"><span data-stu-id="566ac-118">Tenant of user.</span></span> <span data-ttu-id="566ac-119">자세한 내용은 [테 넌 트 테이블](tenants.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="566ac-119">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="566ac-120">UriType</span><span class="sxs-lookup"><span data-stu-id="566ac-120">UriType</span></span>  <br/> |<span data-ttu-id="566ac-121">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="566ac-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="566ac-122">사용자 URI의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="566ac-122">Type of user URI.</span></span> <span data-ttu-id="566ac-123">자세한 내용은 [UriTypes 테이블](uritypes.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="566ac-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

