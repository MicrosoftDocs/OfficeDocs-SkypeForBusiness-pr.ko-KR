---
title: VoIPDetails 보기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: VoIPDetails 보기는 사용자가 한 명 이상 VoIP 사용자 인 피어 투 피어 세션에 대 한 정보를 저장 합니다. 이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.
ms.openlocfilehash: 7f5f1e3cf1540e1a12a9365753e494ff2d8a371e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196665"
---
# <a name="voipdetails-view"></a><span data-ttu-id="756cc-104">VoIPDetails 보기</span><span class="sxs-lookup"><span data-stu-id="756cc-104">VoIPDetails view</span></span>
 
<span data-ttu-id="756cc-105">VoIPDetails 보기는 사용자가 한 명 이상 VoIP 사용자 인 피어 투 피어 세션에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="756cc-105">The VoIPDetails view stores information about peer-to-peer sessions, where at least one user is a VoIP user.</span></span> <span data-ttu-id="756cc-106">이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="756cc-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="756cc-107">VoIPDetails 보기에는 [Sessiondetails 보기](sessiondetails-0.md) 의 모든 열과 아래에 나열 된 열이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="756cc-107">The VoIPDetails view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="756cc-108">**열**</span><span class="sxs-lookup"><span data-stu-id="756cc-108">**Column**</span></span>|<span data-ttu-id="756cc-109">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="756cc-109">**Data Type**</span></span>|<span data-ttu-id="756cc-110">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="756cc-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="756cc-111">**FromPhone**</span><span class="sxs-lookup"><span data-stu-id="756cc-111">**FromPhone**</span></span> <br/> |<span data-ttu-id="756cc-112">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="756cc-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="756cc-113">세션을 시작한 사용자의 전화 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="756cc-113">Phone URI of the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="756cc-114">**ToPhone**</span><span class="sxs-lookup"><span data-stu-id="756cc-114">**ToPhone**</span></span> <br/> |<span data-ttu-id="756cc-115">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="756cc-115">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="756cc-116">세션에 참가 한 사용자의 전화 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="756cc-116">Phone URI of the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="756cc-117">**DisconnectedByUri**</span><span class="sxs-lookup"><span data-stu-id="756cc-117">**DisconnectedByUri**</span></span> <br/> |<span data-ttu-id="756cc-118">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="756cc-118">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="756cc-119">세션을 끊은 사용자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="756cc-119">URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="756cc-120">**DisconnectedByUriType**</span><span class="sxs-lookup"><span data-stu-id="756cc-120">**DisconnectedByUriType**</span></span> <br/> |<span data-ttu-id="756cc-121">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="756cc-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="756cc-122">세션을 끊은 사용자의 URI 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="756cc-122">Type of URI of the user who disconnected the session.</span></span> <span data-ttu-id="756cc-123">자세한 내용은 [UriTypes 테이블](uritypes.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="756cc-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="756cc-124">**DisconnectedByTenant**</span><span class="sxs-lookup"><span data-stu-id="756cc-124">**DisconnectedByTenant**</span></span> <br/> |<span data-ttu-id="756cc-125">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="756cc-125">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="756cc-126">세션을 끊은 사용자의 테 넌 트입니다.</span><span class="sxs-lookup"><span data-stu-id="756cc-126">Tenant of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="756cc-127">**DisconnectedByPhone**</span><span class="sxs-lookup"><span data-stu-id="756cc-127">**DisconnectedByPhone**</span></span> <br/> |<span data-ttu-id="756cc-128">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="756cc-128">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="756cc-129">세션을 끊은 사용자의 전화 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="756cc-129">Phone URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="756cc-130">**FromMediationServer**</span><span class="sxs-lookup"><span data-stu-id="756cc-130">**FromMediationServer**</span></span> <br/> |<span data-ttu-id="756cc-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="756cc-131">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="756cc-132">세션을 시작한 사용자가 사용 하는 중재 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="756cc-132">Mediation Server used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="756cc-133">**ToMediationServer**</span><span class="sxs-lookup"><span data-stu-id="756cc-133">**ToMediationServer**</span></span> <br/> |<span data-ttu-id="756cc-134">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="756cc-134">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="756cc-135">세션에 참가 한 사용자가 사용 하는 중재 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="756cc-135">Mediation Server used by the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="756cc-136">**FromGateway**</span><span class="sxs-lookup"><span data-stu-id="756cc-136">**FromGateway**</span></span> <br/> |<span data-ttu-id="756cc-137">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="756cc-137">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="756cc-138">세션을 시작한 사용자가 사용 하는 게이트웨이</span><span class="sxs-lookup"><span data-stu-id="756cc-138">Gateway used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="756cc-139">**ToGateway**</span><span class="sxs-lookup"><span data-stu-id="756cc-139">**ToGateway**</span></span> <br/> |<span data-ttu-id="756cc-140">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="756cc-140">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="756cc-141">세션에 참가 한 사용자가 사용 하는 게이트웨이</span><span class="sxs-lookup"><span data-stu-id="756cc-141">Gateway used by the user who joined the session.</span></span>  <br/> |
   

