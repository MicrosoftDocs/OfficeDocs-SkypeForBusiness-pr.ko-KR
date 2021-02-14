---
title: 비즈니스용 Skype 서버에서 서버 메모리 용량 제한 모니터링
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1697ea71-6fcf-480d-b4e9-cd79f94d247e
description: '요약: 비즈니스용 Skype 서버에서 서버 메모리 용량 제한을 모니터링하는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: f1423d840fdf690332081a8083617c3a072b373c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814298"
---
# <a name="monitor-for-server-memory-capacity-limits-in-skype-for-business-server"></a><span data-ttu-id="d1029-103">비즈니스용 Skype 서버에서 서버 메모리 용량 제한 모니터링</span><span class="sxs-lookup"><span data-stu-id="d1029-103">Monitor for server memory capacity limits in Skype for Business Server</span></span>
 
<span data-ttu-id="d1029-104">**요약:** 비즈니스용 Skype 서버에서 서버 메모리 용량 제한을 모니터링하는 방법에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="d1029-104">**Summary:** Learn how to monitor for server memory capacity limits in Skype for Business Server.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="d1029-105">용량 계획을 참조하는 이 항목의 정보는 Lync 2010 Mobile 클라이언트 및 Mobility Service(Mcx)에만 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="d1029-105">The information in this topic that refers to Capacity Planning pertains only to Lync 2010 Mobile clients and the Mobility Service (Mcx).</span></span> <span data-ttu-id="d1029-106">Lync 2013 Mobile 클라이언트에서 사용하는 UCWA(Unified Communications Web API)에 대한 용량 계획은 Lync Server 2013 계획 도구에서 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d1029-106">Capacity Planning for the Unified Communications Web API (UCWA), used by the Lync 2013 Mobile clients, is provided by the Lync Server 2013, Planning Tool.</span></span> 

> [!NOTE]
> <span data-ttu-id="d1029-107">레거시 모바일 클라이언트에 대한 MCX(Mobility Service) 지원은 비즈니스용 Skype 서버 2019에서 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d1029-107">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="d1029-108">모든 현재 비즈니스용 Skype 모바일 클라이언트는 이미 UCWA(Unified Communications Web API)를 사용하여 IM(인스턴트 메시징), 현재 상태 및 연락처를 지원하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1029-108">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="d1029-109">MCX를 사용하는 레거시 클라이언트를 사용하는 사용자는 현재 클라이언트로 업그레이드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1029-109">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="d1029-110">두 모바일 성능 카운터를 사용하면 현재 사용량을 파악하고 비즈니스용 Skype 서버 모바일 서비스(Mcx)의 용량을 계획하고 UCWA의 메모리 사용량을 모니터링하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1029-110">Two mobility performance counters can help you to determine your current usage and help you plan capacity for the Skype for Business Server Mobility Service (Mcx), as well as to monitor memory usage for UCWA.</span></span> <span data-ttu-id="d1029-111">UCWA의 경우 카운터 범주는 **LS:WEB - UCWA입니다.**</span><span class="sxs-lookup"><span data-stu-id="d1029-111">For UCWA, the counter category is **LS:WEB - UCWA**.</span></span> <span data-ttu-id="d1029-112">Mcx(Mobility Service)의 경우 카운터는 **LS:WEB - Mobile Communication Service 범주에 속합니다.**</span><span class="sxs-lookup"><span data-stu-id="d1029-112">For the Mobility Service (Mcx), the counters are under the category **LS:WEB - Mobile Communication Service**.</span></span> <span data-ttu-id="d1029-113">모니터링할 카운터는 다음입니다.</span><span class="sxs-lookup"><span data-stu-id="d1029-113">The counters to monitor are:</span></span>
  
- <span data-ttu-id="d1029-114">**현재 활성** 상태 구독이 있는 활성 세션 수입니다. 이는 활성 현재 상태 구독이 있는 UCWA 또는 Mcx(Mobility Service)를 통해 등록된 현재 끝점 수(항상 연결된 모바일 사용자 수)입니다.</span><span class="sxs-lookup"><span data-stu-id="d1029-114">**Currently Active Session Count with Active Presence Subscriptions**, which is the current number of endpoints registered through UCWA or the Mobility Service (Mcx) that have active presence subscriptions (number of always-connected mobile users)</span></span>
    
- <span data-ttu-id="d1029-115">**현재 활성 세션** 수로, UCWA 또는 Mobility Service를 통해 등록된 현재 끝점 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d1029-115">**Currently Active Session Count**, which is the current number of endpoints registered through UCWA or the Mobility Service</span></span>
    
<span data-ttu-id="d1029-116">시간이 지날  때 현재 활성 세션 수와  현재 활성 세션 수의 차이가 작은 경우 이는 대부분의 모바일 장치 사용자에게 Android 또는 Nokia 모바일 장치와 같은 항상 연결된 장치가 있는 것입니다(Mcx에만 해당).</span><span class="sxs-lookup"><span data-stu-id="d1029-116">If the difference between **Currently Active Session Count with Active Presence Subscriptions** and **Currently Active Session Count** is small over time, this means that most mobile device users have an always-connected device, such as an Android or Nokia mobile device (for Mcx only).</span></span> <span data-ttu-id="d1029-117">UCWA 항상 연결된 장치에는 Lync 2013 Mobile 클라이언트를 실행하는 Apple 및 Android 장치가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1029-117">UCWA always-connected devices include Apple and Android devices running Lync 2013 Mobile clients).</span></span> <span data-ttu-id="d1029-118">현재 **활성 세션** 수가 현재 **활성** 상태 구독이 있는 활성 세션 수보다 훨씬 높은 경우 Mcx에서 Apple iOS 장치 또는 Windows Phone과 같은 백그라운드 끝점 장치를 사용하는 사용자가 더 많음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d1029-118">If **Currently Active Session Count** is much higher than **Currently Active Session Count with Active Presence Subscriptions**, this indicates that more users are using a background endpoint device, such as an Apple iOS device or Windows Phone under Mcx.</span></span> <span data-ttu-id="d1029-119">(Windows Phone은 이 클라이언트로 등록하는 유일한 Lync 2013 Mobile 클라이언트입니다.)</span><span class="sxs-lookup"><span data-stu-id="d1029-119">(Windows Phone is the only Lync 2013 Mobile client that will register as this).</span></span>
  
<span data-ttu-id="d1029-120">**예상되는** 사용 현황, 용량 계획 결과 및 Mobility  Service 및 기타 프런트 엔드 서버 카운터의 지속적인 모니터링을 기반으로 활성 현재 활성 세션 수 성능 카운터 및 현재 활성 세션 수 성능 카운터에 대한 제한을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1029-120">You should set a limit on the **Currently Active Session Count with Active Presence Subscriptions** and **Currently Active Session Count** performance counters based on your expected usage, capacity planning results, and ongoing monitoring of Mobility Service and other Front End Server counters.</span></span> <span data-ttu-id="d1029-121">설정한 제한을 통해 서버 용량을 평가하고 용량이 초과된 경우 경고를 발생하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1029-121">The limits you set should enable you to evaluate server capacity and raise alerts when capacity is exceeded.</span></span>
  
<span data-ttu-id="d1029-122">적절한 제한을 결정하려면 먼저 Mobility Service용 프런트 엔드 서버에서 사용할 수 있는 메모리의 수를 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1029-122">To determine the appropriate limits, you need to first determine how much memory is available on the Front End Server for the Mobility Service.</span></span> <span data-ttu-id="d1029-123">카운터를 모니터링하여 다음 수식에 따라 추가 용량을 계획해야 하는 경우를 파악합니다.</span><span class="sxs-lookup"><span data-stu-id="d1029-123">Monitor the counters to determine when you need to plan for extra capacity, according to the following formula:</span></span>
  
<span data-ttu-id="d1029-124">Mcx Mobility Service(MB) = 164 + (400 + 134) / 1024 \* **현재 활성** 상태 구독이 있는 활성 세션 수 + 400 /1024 \* **(현재** 활성 세션 수 현재 활성 세션 수(현재 활성 상태 구독의 활성 세션  -  수)</span><span class="sxs-lookup"><span data-stu-id="d1029-124">Total memory used by the Mcx Mobility Service (MB) = 164 + (400 + 134) / 1024 \* **Currently Active Session Count with Active Presence Subscriptions** + 400 / 1024 \* ( **Currently Active Session Count** - **Currently Active Session Count with Active Presence Subscriptions**)</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d1029-125">Microsoft Lync Server 2010 용량 계산기는 플래너가 CPU, 메모리 및 하드 드라이브를 포함하여 비즈니스용 Skype 서버의 요구 사항을 결정할 수 있도록 하는 모든 수식이 미리 채운 스프레드시트입니다.</span><span class="sxs-lookup"><span data-stu-id="d1029-125">The Microsoft Lync Server 2010 Capacity Calculator is a spreadsheet that is prepopulated with all of the formulas that enable a planner to determine what the requirements will be for the Skype for Business servers, including CPU, memory, and hard drive.</span></span> <span data-ttu-id="d1029-126">스프레드시트와 관련 [문서를 다운로드할 수 있습니다.](https://go.microsoft.com/fwlink/p/?LinkID=212657)</span><span class="sxs-lookup"><span data-stu-id="d1029-126">You can [download the spreadsheet and an associated document](https://go.microsoft.com/fwlink/p/?LinkID=212657).</span></span> 
  
<span data-ttu-id="d1029-127">프런트 엔드 서버에는 장애 조치(failover) 상황에서 Mobility Service를 지원하기에 충분한 사용 가능한 메모리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d1029-127">The Front End Server needs enough available memory to support the Mobility Service in failover situations.</span></span> <span data-ttu-id="d1029-128">**Memory\Available Mbytes** 카운터를 사용하여 프런트 엔드 서버에서 현재 사용 가능한 메모리를 모니터링하거나 앞에서 설명한 수식을 사용하여 Mobility Service에서 사용할 것으로 예상되는 메모리 양을 계획할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1029-128">You can monitor the current available memory on the Front End Server by using the **Memory\Available Mbytes** counter, or by using the equation mentioned earlier, to plan for the amount of memory that you expect the Mobility Service to use.</span></span>
  
<span data-ttu-id="d1029-129">예상 모바일 사용자 수를 계획할 때 프런트 엔드 서버에서 사용할 수 있는 메모리 양이 1,500MB보다 낮을 경우 Mobility Service를 지원하기 위해 하드웨어를 더 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1029-129">If the amount of memory available on the Front End Server is lower than 1,500 MB when you plan for the expected number of mobility users, you need to add more hardware to support the Mobility Service.</span></span> <span data-ttu-id="d1029-130">자세한 내용은 작업 설명서에서 비즈니스용 [Skype 서버의](monitor-mobility-performance.md) 성능에 대한 모바일 모니터링을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d1029-130">For more details, see [Monitor mobility for performance in Skype for Business Server](monitor-mobility-performance.md) in the Operations documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d1029-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d1029-131">See also</span></span>

[<span data-ttu-id="d1029-132">비즈니스용 Skype 서버에서 모바일 성능 모니터링</span><span class="sxs-lookup"><span data-stu-id="d1029-132">Monitor mobility for performance in Skype for Business Server</span></span>](monitor-mobility-performance.md)
