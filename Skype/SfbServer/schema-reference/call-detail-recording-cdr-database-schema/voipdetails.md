---
title: VoIPDetails 보기
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
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: VoIPDetails 보기에는 한 명 이상의 사용자가 VoIP 사용자인 피어 투 피어 세션에 대한 정보가 저장됩니다. 이 보기는 Microsoft Lync Server 2013에서 도입했습니다.
ms.openlocfilehash: b42fecc7a0f43f86dba2439a373c7013c605a5e0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813078"
---
# <a name="voipdetails-view"></a><span data-ttu-id="3a6e1-104">VoIPDetails 보기</span><span class="sxs-lookup"><span data-stu-id="3a6e1-104">VoIPDetails view</span></span>
 
<span data-ttu-id="3a6e1-105">VoIPDetails 보기에는 한 명 이상의 사용자가 VoIP 사용자인 피어 투 피어 세션에 대한 정보가 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a6e1-105">The VoIPDetails view stores information about peer-to-peer sessions, where at least one user is a VoIP user.</span></span> <span data-ttu-id="3a6e1-106">이 보기는 Microsoft Lync Server 2013에서 도입했습니다.</span><span class="sxs-lookup"><span data-stu-id="3a6e1-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3a6e1-107">VoIPDetails 보기에는 [SessionDetails](sessiondetails-0.md) 보기의 모든 열과 아래에 나열된 열이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a6e1-107">The VoIPDetails view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="3a6e1-108">**열**</span><span class="sxs-lookup"><span data-stu-id="3a6e1-108">**Column**</span></span>|<span data-ttu-id="3a6e1-109">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="3a6e1-109">**Data Type**</span></span>|<span data-ttu-id="3a6e1-110">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="3a6e1-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3a6e1-111">**FromPhone**</span><span class="sxs-lookup"><span data-stu-id="3a6e1-111">**FromPhone**</span></span> <br/> |<span data-ttu-id="3a6e1-112">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="3a6e1-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="3a6e1-113">세션을 시작한 사용자의 전화 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="3a6e1-113">Phone URI of the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="3a6e1-114">**ToPhone**</span><span class="sxs-lookup"><span data-stu-id="3a6e1-114">**ToPhone**</span></span> <br/> |<span data-ttu-id="3a6e1-115">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="3a6e1-115">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="3a6e1-116">세션에 참가한 사용자의 전화 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="3a6e1-116">Phone URI of the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="3a6e1-117">**DisconnectedByUri**</span><span class="sxs-lookup"><span data-stu-id="3a6e1-117">**DisconnectedByUri**</span></span> <br/> |<span data-ttu-id="3a6e1-118">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="3a6e1-118">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="3a6e1-119">세션 연결을 끊은 사용자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="3a6e1-119">URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="3a6e1-120">**DisconnectedByUriType**</span><span class="sxs-lookup"><span data-stu-id="3a6e1-120">**DisconnectedByUriType**</span></span> <br/> |<span data-ttu-id="3a6e1-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="3a6e1-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="3a6e1-122">세션 연결을 끊은 사용자의 URI 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="3a6e1-122">Type of URI of the user who disconnected the session.</span></span> <span data-ttu-id="3a6e1-123">자세한 내용은 [UriTypes 테이블을](uritypes.md) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3a6e1-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="3a6e1-124">**DisconnectedByTenant**</span><span class="sxs-lookup"><span data-stu-id="3a6e1-124">**DisconnectedByTenant**</span></span> <br/> |<span data-ttu-id="3a6e1-125">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="3a6e1-125">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="3a6e1-126">세션 연결을 끊은 사용자의 테넌트입니다.</span><span class="sxs-lookup"><span data-stu-id="3a6e1-126">Tenant of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="3a6e1-127">**DisconnectedByPhone**</span><span class="sxs-lookup"><span data-stu-id="3a6e1-127">**DisconnectedByPhone**</span></span> <br/> |<span data-ttu-id="3a6e1-128">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="3a6e1-128">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="3a6e1-129">세션 연결을 끊은 사용자의 전화 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="3a6e1-129">Phone URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="3a6e1-130">**FromMediationServer**</span><span class="sxs-lookup"><span data-stu-id="3a6e1-130">**FromMediationServer**</span></span> <br/> |<span data-ttu-id="3a6e1-131">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="3a6e1-131">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="3a6e1-132">세션을 시작한 사용자가 사용하는 중재 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="3a6e1-132">Mediation Server used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="3a6e1-133">**ToMediationServer**</span><span class="sxs-lookup"><span data-stu-id="3a6e1-133">**ToMediationServer**</span></span> <br/> |<span data-ttu-id="3a6e1-134">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="3a6e1-134">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="3a6e1-135">세션에 참가한 사용자가 사용하는 중재 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="3a6e1-135">Mediation Server used by the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="3a6e1-136">**FromGateway**</span><span class="sxs-lookup"><span data-stu-id="3a6e1-136">**FromGateway**</span></span> <br/> |<span data-ttu-id="3a6e1-137">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="3a6e1-137">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="3a6e1-138">세션을 시작한 사용자가 사용하는 게이트웨이입니다.</span><span class="sxs-lookup"><span data-stu-id="3a6e1-138">Gateway used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="3a6e1-139">**ToGateway**</span><span class="sxs-lookup"><span data-stu-id="3a6e1-139">**ToGateway**</span></span> <br/> |<span data-ttu-id="3a6e1-140">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="3a6e1-140">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="3a6e1-141">세션에 참가한 사용자가 사용하는 게이트웨이입니다.</span><span class="sxs-lookup"><span data-stu-id="3a6e1-141">Gateway used by the user who joined the session.</span></span>  <br/> |
   

