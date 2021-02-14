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
description: 원격 통화 제어는 이전 버전의 Lync Server에서 제공된 기능으로, 사용자가 Lync Server를 사용하여 PBX 전화를 제어할 수 있도록 합니다. 비즈니스용 Skype 서버에서는 이 기능이 직장 전화로 대체됩니다. 비즈니스용 Skype 서버 2015 및 앞으로의 클라이언트 버전에서는 원격 통화 제어를 더 이상 클라이언트에서 구성할 수 없습니다. 이 경우 사용할 수 있도록 제거되었습니다.
ms.openlocfilehash: b48eeed656f5889d08fe892da7d7a6896f8a11c3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813518"
---
# <a name="plan-for-remote-call-control-in-skype-for-business"></a><span data-ttu-id="8f375-105">비즈니스용 Skype의 원격 통화 제어 계획</span><span class="sxs-lookup"><span data-stu-id="8f375-105">Plan for remote call control in Skype for Business</span></span>
 
<span data-ttu-id="8f375-106">원격 통화 제어는 이전 버전의 Lync Server에서 제공된 기능으로, 사용자가 Lync Server를 사용하여 PBX 전화를 제어할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f375-106">Remote call control was a feature in previous versions of Lync Server which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="8f375-107">비즈니스용 Skype 서버에서는 이 기능이 직장 전화로 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f375-107">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span>  <span data-ttu-id="8f375-108">*비즈니스용 Skype 서버 2015 및 앞으로의 클라이언트 버전에서는 원격 통화 제어를 더 이상 클라이언트에서 구성할 수 없습니다. 이 경우 사용할 수 있도록 제거되었습니다.*</span><span class="sxs-lookup"><span data-stu-id="8f375-108">*In the client versions for Skype for Business Server 2015 and going forward, remote call control is no longer available to configure in the client and has been removed for use.*</span></span> 
  
 <span data-ttu-id="8f375-109">Lync Server를 실행하는 프런트 엔드 서버에 있는 조직의 원격 통화 제어 사용자는 비즈니스용 Skype 클라이언트를 사용 중인 경우에도 계속 원격 통화 제어를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f375-109">Remote call control users in your organization who are homed on Front End Servers running Lync Server can continue to use remote call control, even if they are using a Skype for Business client.</span></span> <span data-ttu-id="8f375-110">그러나 비즈니스용 Skype 서버에 있는 사용자의 경우 원격 통화 제어가 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8f375-110">However, for any users homed on Skype for Business Server, remote call control is not supported.</span></span> <span data-ttu-id="8f375-111">서버/클라이언트 조합 및 원격 통화 제어를 지원할 수 있는지 아니면 직장을 통해 전화를 걸 수 있는지에 대한 다음 표를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="8f375-111">See the following table for server/client combinations and whether they can support remote call control or Call via Work.</span></span>
  
||<span data-ttu-id="8f375-112">**Skype UI가 사용하도록 설정된 비즈니스용 Skype 클라이언트**</span><span class="sxs-lookup"><span data-stu-id="8f375-112">**Skype for Business Client With Skype UI enabled**</span></span>|<span data-ttu-id="8f375-113">**Lync UI가 사용하도록 설정된 비즈니스용 Skype 클라이언트**</span><span class="sxs-lookup"><span data-stu-id="8f375-113">**Skype for Business Client With Lync UI enabled**</span></span>|<span data-ttu-id="8f375-114">**비즈니스용 Skype 2016 클라이언트**</span><span class="sxs-lookup"><span data-stu-id="8f375-114">**Skype for Business 2016 Client**</span></span>|<span data-ttu-id="8f375-115">**Lync 2013 클라이언트**</span><span class="sxs-lookup"><span data-stu-id="8f375-115">**Lync 2013 Client**</span></span>|<span data-ttu-id="8f375-116">**Lync 2010 클라이언트**</span><span class="sxs-lookup"><span data-stu-id="8f375-116">**Lync 2010 Client**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
| <span data-ttu-id="8f375-117">비즈니스용 Skype 서버</span><span class="sxs-lookup"><span data-stu-id="8f375-117">Skype for Business Server</span></span> <br/> |<span data-ttu-id="8f375-118">직장을 통한 통화</span><span class="sxs-lookup"><span data-stu-id="8f375-118">Call via Work</span></span>  <br/> |<span data-ttu-id="8f375-119">1 </span><span class="sxs-lookup"><span data-stu-id="8f375-119">1</span></span> <br/> |<span data-ttu-id="8f375-120">직장을 통한 통화</span><span class="sxs-lookup"><span data-stu-id="8f375-120">Call via Work</span></span>  <br/> |<span data-ttu-id="8f375-121">1 </span><span class="sxs-lookup"><span data-stu-id="8f375-121">1</span></span> <br/> |<span data-ttu-id="8f375-122">1 </span><span class="sxs-lookup"><span data-stu-id="8f375-122">1</span></span> <br/> |
| <span data-ttu-id="8f375-123">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f375-123">Lync Server 2013</span></span> <br/> |<span data-ttu-id="8f375-124">원격 통화 제어</span><span class="sxs-lookup"><span data-stu-id="8f375-124">Remote Call Control</span></span>  <br/> |<span data-ttu-id="8f375-125">원격 통화 제어</span><span class="sxs-lookup"><span data-stu-id="8f375-125">Remote Call Control</span></span>  <br/> |<span data-ttu-id="8f375-126">1 </span><span class="sxs-lookup"><span data-stu-id="8f375-126">1</span></span> <br/> |<span data-ttu-id="8f375-127">원격 통화 제어</span><span class="sxs-lookup"><span data-stu-id="8f375-127">Remote Call Control</span></span>  <br/> |<span data-ttu-id="8f375-128">원격 통화 제어</span><span class="sxs-lookup"><span data-stu-id="8f375-128">Remote Call Control</span></span>  <br/> |
| <span data-ttu-id="8f375-129">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="8f375-129">Lync Server 2010</span></span> <br/> |<span data-ttu-id="8f375-130">원격 통화 제어</span><span class="sxs-lookup"><span data-stu-id="8f375-130">Remote Call Control</span></span>  <br/> |<span data-ttu-id="8f375-131">원격 통화 제어</span><span class="sxs-lookup"><span data-stu-id="8f375-131">Remote Call Control</span></span>  <br/> |<span data-ttu-id="8f375-132">1 </span><span class="sxs-lookup"><span data-stu-id="8f375-132">1</span></span> <br/> |<span data-ttu-id="8f375-133">원격 통화 제어</span><span class="sxs-lookup"><span data-stu-id="8f375-133">Remote Call Control</span></span>  <br/> |<span data-ttu-id="8f375-134">원격 통화 제어</span><span class="sxs-lookup"><span data-stu-id="8f375-134">Remote Call Control</span></span>  <br/> |
   
1. <span data-ttu-id="8f375-135">두 기능 모두 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8f375-135">Neither feature is supported.</span></span>
  
<span data-ttu-id="8f375-136">자세한 내용은 Lync Server 2013 설명서의 원격 통화 제어를 참조하십시오. [](https://go.microsoft.com/fwlink/p/?LinkId=530208)</span><span class="sxs-lookup"><span data-stu-id="8f375-136">For more information, see [Remote Call Control](https://go.microsoft.com/fwlink/p/?LinkId=530208) in the Lync Server 2013 documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8f375-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8f375-137">See also</span></span>

[<span data-ttu-id="8f375-138">비즈니스용 Skype 서버의 직장 전화 계획</span><span class="sxs-lookup"><span data-stu-id="8f375-138">Plan for Call Via Work in Skype for Business Server</span></span>](call-via-work.md)
  
[<span data-ttu-id="8f375-139">비즈니스용 Skype에 대한 데스크톱 클라이언트 기능 비교</span><span class="sxs-lookup"><span data-stu-id="8f375-139">Desktop client feature comparison for Skype for Business</span></span>](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[<span data-ttu-id="8f375-140">비즈니스용 Skype 통화를 하지만 오디오에 PBX 책상 전화 사용</span><span class="sxs-lookup"><span data-stu-id="8f375-140">Make a Skype for Business call but use your PBX desk phone for audio</span></span>](https://support.office.com/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)

