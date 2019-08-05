---
title: 비즈니스용 Skype에서 원격 통화 제어 계획
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
description: 원격 통화 제어는 Lync server를 사용 하 여 사용자가 PBX 전화를 제어할 수 있도록 하는 이전 버전의 Lync Server의 기능입니다. 비즈니스용 Skype Server에서이 기능은 업무에의 한 통화를 통해 대체 되었습니다. 비즈니스용 Skype Server 2015의 클라이언트 버전에서 원격 통화 제어는 더 이상 클라이언트에서 구성할 수 없으며 사용을 위해 제거 되었습니다.
ms.openlocfilehash: e98bcbd7e1feb91b31994d2ece2770c911547882
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187575"
---
# <a name="plan-for-remote-call-control-in-skype-for-business"></a><span data-ttu-id="ba683-105">비즈니스용 Skype에서 원격 통화 제어 계획</span><span class="sxs-lookup"><span data-stu-id="ba683-105">Plan for remote call control in Skype for Business</span></span>
 
<span data-ttu-id="ba683-106">원격 통화 제어는 Lync server를 사용 하 여 사용자가 PBX 전화를 제어할 수 있도록 하는 이전 버전의 Lync Server의 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="ba683-106">Remote call control was a feature in previous versions of Lync Server which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="ba683-107">비즈니스용 Skype Server에서이 기능은 업무에의 한 통화를 통해 대체 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ba683-107">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span>  <span data-ttu-id="ba683-108">*비즈니스용 Skype Server 2015의 클라이언트 버전에서 원격 통화 제어는 더 이상 클라이언트에서 구성할 수 없으며 사용을 위해 제거 되었습니다.*</span><span class="sxs-lookup"><span data-stu-id="ba683-108">*In the client versions for Skype for Business Server 2015 and going forward, remote call control is no longer available to configure in the client and has been removed for use.*</span></span> 
  
 <span data-ttu-id="ba683-109">원격 통화 제어 Lync Server를 실행 하는 프런트 엔드 서버에 속한 조직의 사용자는 비즈니스용 Skype 클라이언트를 사용 하는 경우에도 원격 통화 제어를 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba683-109">Remote call control users in your organization who are homed on Front End Servers running Lync Server can continue to use remote call control, even if they are using a Skype for Business client.</span></span> <span data-ttu-id="ba683-110">그러나 비즈니스용 Skype Server에 속한 사용자는 원격 통화 제어가 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ba683-110">However, for any users homed on Skype for Business Server, remote call control is not supported.</span></span> <span data-ttu-id="ba683-111">다음 표에서는 서버/클라이언트 조합의 경우와 원격 통화 제어를 지원 하거나 작업을 통해 통화할 수 있는지 여부를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ba683-111">See the following table for server/client combinations and whether they can support remote call control or Call via Work.</span></span>
  
||<span data-ttu-id="ba683-112">**Skype UI를 사용 하는 비즈니스용 skype 클라이언트**</span><span class="sxs-lookup"><span data-stu-id="ba683-112">**Skype for Business Client With Skype UI enabled**</span></span>|<span data-ttu-id="ba683-113">**Lync UI가 설정 된 비즈니스용 Skype 클라이언트**</span><span class="sxs-lookup"><span data-stu-id="ba683-113">**Skype for Business Client With Lync UI enabled**</span></span>|<span data-ttu-id="ba683-114">**비즈니스용 Skype 2016 클라이언트**</span><span class="sxs-lookup"><span data-stu-id="ba683-114">**Skype for Business 2016 Client**</span></span>|<span data-ttu-id="ba683-115">**Lync 2013 클라이언트**</span><span class="sxs-lookup"><span data-stu-id="ba683-115">**Lync 2013 Client**</span></span>|<span data-ttu-id="ba683-116">**Lync 2010 클라이언트**</span><span class="sxs-lookup"><span data-stu-id="ba683-116">**Lync 2010 Client**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
| <span data-ttu-id="ba683-117">비즈니스용 Skype 서버</span><span class="sxs-lookup"><span data-stu-id="ba683-117">Skype for Business Server</span></span> <br/> |<span data-ttu-id="ba683-118">직장을 통한 통화</span><span class="sxs-lookup"><span data-stu-id="ba683-118">Call via Work</span></span>  <br/> |<span data-ttu-id="ba683-119">raid-1</span><span class="sxs-lookup"><span data-stu-id="ba683-119">1</span></span> <br/> |<span data-ttu-id="ba683-120">직장을 통한 통화</span><span class="sxs-lookup"><span data-stu-id="ba683-120">Call via Work</span></span>  <br/> |<span data-ttu-id="ba683-121">raid-1</span><span class="sxs-lookup"><span data-stu-id="ba683-121">1</span></span> <br/> |<span data-ttu-id="ba683-122">raid-1</span><span class="sxs-lookup"><span data-stu-id="ba683-122">1</span></span> <br/> |
| <span data-ttu-id="ba683-123">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba683-123">Lync Server 2013</span></span> <br/> |<span data-ttu-id="ba683-124">원격 통화 제어</span><span class="sxs-lookup"><span data-stu-id="ba683-124">Remote Call Control</span></span>  <br/> |<span data-ttu-id="ba683-125">원격 통화 제어</span><span class="sxs-lookup"><span data-stu-id="ba683-125">Remote Call Control</span></span>  <br/> |<span data-ttu-id="ba683-126">raid-1</span><span class="sxs-lookup"><span data-stu-id="ba683-126">1</span></span> <br/> |<span data-ttu-id="ba683-127">원격 통화 제어</span><span class="sxs-lookup"><span data-stu-id="ba683-127">Remote Call Control</span></span>  <br/> |<span data-ttu-id="ba683-128">원격 통화 제어</span><span class="sxs-lookup"><span data-stu-id="ba683-128">Remote Call Control</span></span>  <br/> |
| <span data-ttu-id="ba683-129">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="ba683-129">Lync Server 2010</span></span> <br/> |<span data-ttu-id="ba683-130">원격 통화 제어</span><span class="sxs-lookup"><span data-stu-id="ba683-130">Remote Call Control</span></span>  <br/> |<span data-ttu-id="ba683-131">원격 통화 제어</span><span class="sxs-lookup"><span data-stu-id="ba683-131">Remote Call Control</span></span>  <br/> |<span data-ttu-id="ba683-132">raid-1</span><span class="sxs-lookup"><span data-stu-id="ba683-132">1</span></span> <br/> |<span data-ttu-id="ba683-133">원격 통화 제어</span><span class="sxs-lookup"><span data-stu-id="ba683-133">Remote Call Control</span></span>  <br/> |<span data-ttu-id="ba683-134">원격 통화 제어</span><span class="sxs-lookup"><span data-stu-id="ba683-134">Remote Call Control</span></span>  <br/> |
   
1. <span data-ttu-id="ba683-135">두 기능은 모두 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ba683-135">Neither feature is supported.</span></span>
  
<span data-ttu-id="ba683-136">자세한 내용은 Lync Server 2013 설명서의 [원격 통화 제어](https://go.microsoft.com/fwlink/p/?LinkId=530208) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ba683-136">For more information, see [Remote Call Control](https://go.microsoft.com/fwlink/p/?LinkId=530208) in the Lync Server 2013 documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ba683-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ba683-137">See also</span></span>

[<span data-ttu-id="ba683-138">비즈니스용 Skype 서버의 작업을 통한 통화 계획</span><span class="sxs-lookup"><span data-stu-id="ba683-138">Plan for Call Via Work in Skype for Business Server</span></span>](call-via-work.md)
  
[<span data-ttu-id="ba683-139">비즈니스용 Skype에 대 한 데스크톱 클라이언트 기능 비교</span><span class="sxs-lookup"><span data-stu-id="ba683-139">Desktop client feature comparison for Skype for Business</span></span>](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[<span data-ttu-id="ba683-140">비즈니스용 Skype 통화를 설정 하지만 오디오에 PBX 일반 전화기를 사용 하세요.</span><span class="sxs-lookup"><span data-stu-id="ba683-140">Make a Skype for Business call but use your PBX desk phone for audio</span></span>](https://support.office.com/en-us/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)

