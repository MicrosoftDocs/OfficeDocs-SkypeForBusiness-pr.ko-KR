---
title: 비즈니스용 Skype의 원격 통화 제어 계획
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
description: 원격 통화 제어는 사용자가 Lync Server를 사용하여 PBX 전화를 제어할 수 있는 이전 버전의 Lync Server의 기능입니다. 비즈니스용 Skype 서버에서는 이 기능이 업무를 통해 전화로 대체됩니다. 비즈니스용 Skype 서버 2015 및 앞으로의 클라이언트 버전에서는 원격 통화 제어를 더 이상 클라이언트에서 구성할 수 없습니다. 사용이 제거되었습니다.
ms.openlocfilehash: 1ec6bb59b34505f17451be72baa44cdcc466c0d3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114614"
---
# <a name="plan-for-remote-call-control-in-skype-for-business"></a><span data-ttu-id="3d7e6-105">비즈니스용 Skype의 원격 통화 제어 계획</span><span class="sxs-lookup"><span data-stu-id="3d7e6-105">Plan for remote call control in Skype for Business</span></span>
 
<span data-ttu-id="3d7e6-106">원격 통화 제어는 사용자가 Lync Server를 사용하여 PBX 전화를 제어할 수 있는 이전 버전의 Lync Server의 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="3d7e6-106">Remote call control was a feature in previous versions of Lync Server which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="3d7e6-107">비즈니스용 Skype 서버에서는 이 기능이 업무를 통해 전화로 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d7e6-107">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span>  <span data-ttu-id="3d7e6-108">*비즈니스용 Skype 서버 2015 및 앞으로의 클라이언트 버전에서는 원격 통화 제어를 더 이상 클라이언트에서 구성할 수 없습니다. 사용이 제거되었습니다.*</span><span class="sxs-lookup"><span data-stu-id="3d7e6-108">*In the client versions for Skype for Business Server 2015 and going forward, remote call control is no longer available to configure in the client and has been removed for use.*</span></span> 
  
 <span data-ttu-id="3d7e6-109">Lync Server를 실행하는 프런트 엔드 서버에 있는 조직의 원격 통화 제어 사용자는 비즈니스용 Skype 클라이언트를 사용 중인 경우에도 원격 통화 제어를 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d7e6-109">Remote call control users in your organization who are homed on Front End Servers running Lync Server can continue to use remote call control, even if they are using a Skype for Business client.</span></span> <span data-ttu-id="3d7e6-110">그러나 비즈니스용 Skype 서버에 있는 사용자의 경우 원격 통화 제어가 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3d7e6-110">However, for any users homed on Skype for Business Server, remote call control is not supported.</span></span> <span data-ttu-id="3d7e6-111">서버/클라이언트 조합 및 원격 통화 제어를 지원할 수 있는지 또는 직장을 통한 통화를 지원할 수 있는지에 대한 다음 표를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="3d7e6-111">See the following table for server/client combinations and whether they can support remote call control or Call via Work.</span></span>
  
||<span data-ttu-id="3d7e6-112">**Skype UI가 사용하도록 설정된 비즈니스용 Skype 클라이언트**</span><span class="sxs-lookup"><span data-stu-id="3d7e6-112">**Skype for Business Client With Skype UI enabled**</span></span>|<span data-ttu-id="3d7e6-113">**Lync UI가 사용하도록 설정된 비즈니스용 Skype 클라이언트**</span><span class="sxs-lookup"><span data-stu-id="3d7e6-113">**Skype for Business Client With Lync UI enabled**</span></span>|<span data-ttu-id="3d7e6-114">**비즈니스용 Skype 2016 클라이언트**</span><span class="sxs-lookup"><span data-stu-id="3d7e6-114">**Skype for Business 2016 Client**</span></span>|<span data-ttu-id="3d7e6-115">**Lync 2013 클라이언트**</span><span class="sxs-lookup"><span data-stu-id="3d7e6-115">**Lync 2013 Client**</span></span>|<span data-ttu-id="3d7e6-116">**Lync 2010 클라이언트**</span><span class="sxs-lookup"><span data-stu-id="3d7e6-116">**Lync 2010 Client**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
| <span data-ttu-id="3d7e6-117">비즈니스용 Skype 서버</span><span class="sxs-lookup"><span data-stu-id="3d7e6-117">Skype for Business Server</span></span> <br/> |<span data-ttu-id="3d7e6-118">업무를 통해 전화</span><span class="sxs-lookup"><span data-stu-id="3d7e6-118">Call via Work</span></span>  <br/> |<span data-ttu-id="3d7e6-119">1</span><span class="sxs-lookup"><span data-stu-id="3d7e6-119">1</span></span> <br/> |<span data-ttu-id="3d7e6-120">업무를 통해 전화</span><span class="sxs-lookup"><span data-stu-id="3d7e6-120">Call via Work</span></span>  <br/> |<span data-ttu-id="3d7e6-121">1</span><span class="sxs-lookup"><span data-stu-id="3d7e6-121">1</span></span> <br/> |<span data-ttu-id="3d7e6-122">1</span><span class="sxs-lookup"><span data-stu-id="3d7e6-122">1</span></span> <br/> |
| <span data-ttu-id="3d7e6-123">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d7e6-123">Lync Server 2013</span></span> <br/> |<span data-ttu-id="3d7e6-124">원격 통화 제어</span><span class="sxs-lookup"><span data-stu-id="3d7e6-124">Remote Call Control</span></span>  <br/> |<span data-ttu-id="3d7e6-125">원격 통화 제어</span><span class="sxs-lookup"><span data-stu-id="3d7e6-125">Remote Call Control</span></span>  <br/> |<span data-ttu-id="3d7e6-126">1</span><span class="sxs-lookup"><span data-stu-id="3d7e6-126">1</span></span> <br/> |<span data-ttu-id="3d7e6-127">원격 통화 제어</span><span class="sxs-lookup"><span data-stu-id="3d7e6-127">Remote Call Control</span></span>  <br/> |<span data-ttu-id="3d7e6-128">원격 통화 제어</span><span class="sxs-lookup"><span data-stu-id="3d7e6-128">Remote Call Control</span></span>  <br/> |
| <span data-ttu-id="3d7e6-129">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="3d7e6-129">Lync Server 2010</span></span> <br/> |<span data-ttu-id="3d7e6-130">원격 통화 제어</span><span class="sxs-lookup"><span data-stu-id="3d7e6-130">Remote Call Control</span></span>  <br/> |<span data-ttu-id="3d7e6-131">원격 통화 제어</span><span class="sxs-lookup"><span data-stu-id="3d7e6-131">Remote Call Control</span></span>  <br/> |<span data-ttu-id="3d7e6-132">1</span><span class="sxs-lookup"><span data-stu-id="3d7e6-132">1</span></span> <br/> |<span data-ttu-id="3d7e6-133">원격 통화 제어</span><span class="sxs-lookup"><span data-stu-id="3d7e6-133">Remote Call Control</span></span>  <br/> |<span data-ttu-id="3d7e6-134">원격 통화 제어</span><span class="sxs-lookup"><span data-stu-id="3d7e6-134">Remote Call Control</span></span>  <br/> |
   
1. <span data-ttu-id="3d7e6-135">두 기능 모두 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3d7e6-135">Neither feature is supported.</span></span>
  
<span data-ttu-id="3d7e6-136">자세한 내용은 Lync Server 2013 설명서의 원격 통화 제어를 참조하십시오. [](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-remote-call-control)</span><span class="sxs-lookup"><span data-stu-id="3d7e6-136">For more information, see [Remote Call Control](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-remote-call-control) in the Lync Server 2013 documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3d7e6-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3d7e6-137">See also</span></span>

[<span data-ttu-id="3d7e6-138">비즈니스용 Skype 서버에서 직장을 통한 통화 계획</span><span class="sxs-lookup"><span data-stu-id="3d7e6-138">Plan for Call Via Work in Skype for Business Server</span></span>](call-via-work.md)
  
[<span data-ttu-id="3d7e6-139">비즈니스용 Skype에 대한 데스크톱 클라이언트 기능 비교</span><span class="sxs-lookup"><span data-stu-id="3d7e6-139">Desktop client feature comparison for Skype for Business</span></span>](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[<span data-ttu-id="3d7e6-140">비즈니스용 Skype 통화를 하지만 오디오에 PBX 책상 전화 사용</span><span class="sxs-lookup"><span data-stu-id="3d7e6-140">Make a Skype for Business call but use your PBX desk phone for audio</span></span>](https://support.office.com/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)