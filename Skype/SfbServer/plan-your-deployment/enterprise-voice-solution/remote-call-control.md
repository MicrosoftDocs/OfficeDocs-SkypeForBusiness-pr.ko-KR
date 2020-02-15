---
title: 비즈니스용 Skype에서 원격 통화 제어 계획
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 원격 통화 제어는 Lync Server를 사용 하 여 사용자가 PBX 전화를 제어할 수 있도록 하는 이전 버전 Lync Server의 기능 이었습니다. 비즈니스용 Skype 서버에서이 기능은 직장을 통해 통화로 바뀌었습니다. 비즈니스용 Skype 서버 2015의 클라이언트 버전에서 원격 통화 제어를 더 이상 클라이언트에서 구성할 수 없으며 사용 하기 위해 제거 되었습니다.
ms.openlocfilehash: 788939c392b1d86d14590232c19979e664fa0c09
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "41982803"
---
# <a name="plan-for-remote-call-control-in-skype-for-business"></a><span data-ttu-id="f84ac-105">비즈니스용 Skype에서 원격 통화 제어 계획</span><span class="sxs-lookup"><span data-stu-id="f84ac-105">Plan for remote call control in Skype for Business</span></span>
 
<span data-ttu-id="f84ac-106">원격 통화 제어는 Lync Server를 사용 하 여 사용자가 PBX 전화를 제어할 수 있도록 하는 이전 버전 Lync Server의 기능 이었습니다.</span><span class="sxs-lookup"><span data-stu-id="f84ac-106">Remote call control was a feature in previous versions of Lync Server which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="f84ac-107">비즈니스용 Skype 서버에서이 기능은 직장을 통해 통화로 바뀌었습니다.</span><span class="sxs-lookup"><span data-stu-id="f84ac-107">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span>  <span data-ttu-id="f84ac-108">*비즈니스용 Skype 서버 2015의 클라이언트 버전에서 원격 통화 제어를 더 이상 클라이언트에서 구성할 수 없으며 사용 하기 위해 제거 되었습니다.*</span><span class="sxs-lookup"><span data-stu-id="f84ac-108">*In the client versions for Skype for Business Server 2015 and going forward, remote call control is no longer available to configure in the client and has been removed for use.*</span></span> 
  
 <span data-ttu-id="f84ac-109">원격 통화 제어 Lync Server를 실행 하는 프런트 엔드 서버를 사용 하는 조직의 사용자는 비즈니스용 Skype 클라이언트를 사용 하는 경우에도 원격 통화 제어를 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f84ac-109">Remote call control users in your organization who are homed on Front End Servers running Lync Server can continue to use remote call control, even if they are using a Skype for Business client.</span></span> <span data-ttu-id="f84ac-110">하지만 비즈니스용 Skype 서버에 있는 모든 사용자의 경우 원격 통화 제어는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f84ac-110">However, for any users homed on Skype for Business Server, remote call control is not supported.</span></span> <span data-ttu-id="f84ac-111">서버/클라이언트 조합과 원격 통화 제어를 지원 하거나 직장을 통해 전화를 걸 수 있는지 여부에 대해서는 다음 표를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f84ac-111">See the following table for server/client combinations and whether they can support remote call control or Call via Work.</span></span>
  
||<span data-ttu-id="f84ac-112">**Skype UI가 사용 하도록 설정 된 비즈니스용 skype 클라이언트**</span><span class="sxs-lookup"><span data-stu-id="f84ac-112">**Skype for Business Client With Skype UI enabled**</span></span>|<span data-ttu-id="f84ac-113">**Lync UI가 사용 하도록 설정 된 비즈니스용 Skype 클라이언트**</span><span class="sxs-lookup"><span data-stu-id="f84ac-113">**Skype for Business Client With Lync UI enabled**</span></span>|<span data-ttu-id="f84ac-114">**비즈니스용 Skype 2016 클라이언트**</span><span class="sxs-lookup"><span data-stu-id="f84ac-114">**Skype for Business 2016 Client**</span></span>|<span data-ttu-id="f84ac-115">**Lync 2013 클라이언트**</span><span class="sxs-lookup"><span data-stu-id="f84ac-115">**Lync 2013 Client**</span></span>|<span data-ttu-id="f84ac-116">**Lync 2010 클라이언트**</span><span class="sxs-lookup"><span data-stu-id="f84ac-116">**Lync 2010 Client**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
| <span data-ttu-id="f84ac-117">비즈니스용 Skype 서버</span><span class="sxs-lookup"><span data-stu-id="f84ac-117">Skype for Business Server</span></span> <br/> |<span data-ttu-id="f84ac-118">회사 번호로 전화</span><span class="sxs-lookup"><span data-stu-id="f84ac-118">Call via Work</span></span>  <br/> |<span data-ttu-id="f84ac-119">1 </span><span class="sxs-lookup"><span data-stu-id="f84ac-119">1</span></span> <br/> |<span data-ttu-id="f84ac-120">회사 번호로 전화</span><span class="sxs-lookup"><span data-stu-id="f84ac-120">Call via Work</span></span>  <br/> |<span data-ttu-id="f84ac-121">1 </span><span class="sxs-lookup"><span data-stu-id="f84ac-121">1</span></span> <br/> |<span data-ttu-id="f84ac-122">1 </span><span class="sxs-lookup"><span data-stu-id="f84ac-122">1</span></span> <br/> |
| <span data-ttu-id="f84ac-123">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f84ac-123">Lync Server 2013</span></span> <br/> |<span data-ttu-id="f84ac-124">원격 통화 제어</span><span class="sxs-lookup"><span data-stu-id="f84ac-124">Remote Call Control</span></span>  <br/> |<span data-ttu-id="f84ac-125">원격 통화 제어</span><span class="sxs-lookup"><span data-stu-id="f84ac-125">Remote Call Control</span></span>  <br/> |<span data-ttu-id="f84ac-126">1 </span><span class="sxs-lookup"><span data-stu-id="f84ac-126">1</span></span> <br/> |<span data-ttu-id="f84ac-127">원격 통화 제어</span><span class="sxs-lookup"><span data-stu-id="f84ac-127">Remote Call Control</span></span>  <br/> |<span data-ttu-id="f84ac-128">원격 통화 제어</span><span class="sxs-lookup"><span data-stu-id="f84ac-128">Remote Call Control</span></span>  <br/> |
| <span data-ttu-id="f84ac-129">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="f84ac-129">Lync Server 2010</span></span> <br/> |<span data-ttu-id="f84ac-130">원격 통화 제어</span><span class="sxs-lookup"><span data-stu-id="f84ac-130">Remote Call Control</span></span>  <br/> |<span data-ttu-id="f84ac-131">원격 통화 제어</span><span class="sxs-lookup"><span data-stu-id="f84ac-131">Remote Call Control</span></span>  <br/> |<span data-ttu-id="f84ac-132">1 </span><span class="sxs-lookup"><span data-stu-id="f84ac-132">1</span></span> <br/> |<span data-ttu-id="f84ac-133">원격 통화 제어</span><span class="sxs-lookup"><span data-stu-id="f84ac-133">Remote Call Control</span></span>  <br/> |<span data-ttu-id="f84ac-134">원격 통화 제어</span><span class="sxs-lookup"><span data-stu-id="f84ac-134">Remote Call Control</span></span>  <br/> |
   
1. <span data-ttu-id="f84ac-135">두 기능 모두 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f84ac-135">Neither feature is supported.</span></span>
  
<span data-ttu-id="f84ac-136">자세한 내용은 Lync Server 2013 설명서의 [원격 통화 제어](https://go.microsoft.com/fwlink/p/?LinkId=530208) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="f84ac-136">For more information, see [Remote Call Control](https://go.microsoft.com/fwlink/p/?LinkId=530208) in the Lync Server 2013 documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f84ac-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f84ac-137">See also</span></span>

[<span data-ttu-id="f84ac-138">비즈니스용 Skype 서버의 직장을 통한 통화 계획</span><span class="sxs-lookup"><span data-stu-id="f84ac-138">Plan for Call Via Work in Skype for Business Server</span></span>](call-via-work.md)
  
[<span data-ttu-id="f84ac-139">비즈니스용 Skype에 대 한 데스크톱 클라이언트 기능 비교</span><span class="sxs-lookup"><span data-stu-id="f84ac-139">Desktop client feature comparison for Skype for Business</span></span>](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[<span data-ttu-id="f84ac-140">비즈니스용 Skype 통화를 수행 하 되 오디오를 위해 PBX 데스크 전화 사용</span><span class="sxs-lookup"><span data-stu-id="f84ac-140">Make a Skype for Business call but use your PBX desk phone for audio</span></span>](https://support.office.com/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)

