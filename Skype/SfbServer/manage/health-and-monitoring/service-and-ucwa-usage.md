---
title: 비즈니스용 Skype 서버에서 이동성 서비스 및 함께 사용 모니터링
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
description: '요약: 비즈니스용 Skype 서버에서 모바일 서비스 (Mcx) 및 통합 커뮤니케이션 웹 API (c)를 관리 합니다.'
ms.openlocfilehash: 7c41e92b144e1bd4d198c5e9d9f90913ce41400e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817687"
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server"></a><span data-ttu-id="c8d6a-103">비즈니스용 Skype 서버에서 이동성 서비스 및 함께 사용 모니터링</span><span class="sxs-lookup"><span data-stu-id="c8d6a-103">Monitor Mobility Service and UCWA usage in Skype for Business Server</span></span>
 
<span data-ttu-id="c8d6a-104">**요약:** 비즈니스용 Skype 서버에서 모바일 서비스 (Mcx) 및 통합 커뮤니케이션 웹 API (c)를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d6a-104">**Summary:** Manage the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="c8d6a-105">이전 모바일 클라이언트에 대 한 MCX (Mobility Service) 지원은 더 이상 비즈니스용 Skype 서버 2019에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c8d6a-105">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="c8d6a-106">현재 모든 비즈니스용 Skype 모바일 클라이언트는 이미 통합 커뮤니케이션 웹 API (인스턴트 메시징 (IM), 현재 상태, 대화 상대 지원)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d6a-106">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="c8d6a-107">MCX를 사용 하는 레거시 클라이언트가 있는 사용자는 현재 클라이언트로 업그레이드 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d6a-107">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="c8d6a-108">지속적으로 비즈니스용 Skype Server Mobility Service (Mcx) 및 통합 커뮤니케이션 웹 API (c)가 사용 하는 CPU 및 메모리를 모니터링 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d6a-108">On an ongoing basis, you should monitor the CPU and memory that is used by the Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="c8d6a-109">사용 현황을 모니터링 하려면 다음을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8d6a-109">To monitor usage, you can use the following:</span></span>
  
 <span data-ttu-id="c8d6a-110">**통합 커뮤니케이션 웹 API (c):**</span><span class="sxs-lookup"><span data-stu-id="c8d6a-110">**For Unified Communications Web API (UCWA):**</span></span>
  
- <span data-ttu-id="c8d6a-111">IIS (인터넷 정보 서비스) 관리자의 **L C인천** 작업자 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="c8d6a-111">The **LyncUcwa** worker process in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="c8d6a-112">**작업자 프로세스** 창에서 **CPU%** 및 **전용 바이트 (KB)** 열을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d6a-112">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="c8d6a-113">**CPU** 및 **프로세서** 성능 카운터입니다.</span><span class="sxs-lookup"><span data-stu-id="c8d6a-113">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="c8d6a-114">대부분의 배포의 경우 fwa CPU 사용이 평균적으로 15% 미만 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d6a-114">For most deployments, UCWA CPU usage should be below 15 percent on average.</span></span> <span data-ttu-id="c8d6a-115">메모리 사용은 [비즈니스용 Skype 서버의 서버 메모리 용량 제한에 대 한 모니터](server-memory-capacity-limits.md)에 설명 된 제한 내에 속해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d6a-115">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="c8d6a-116">CPU 및 메모리 사용 카운터 외에도 다음 성능 카운터를 사용 하 여 서버에서 요청을 오버 로드할 때이를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8d6a-116">In addition to CPU and memory usage counters, you can use the following performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="c8d6a-117">**LS: 웹 제한 및 인증 \ 웹-** 서버에서 보류 중인 웹 요청 수를 나타내는 처리 중인 총 요청.</span><span class="sxs-lookup"><span data-stu-id="c8d6a-117">**LS:WEB - Throttling and Authentication\WEB - Total Requests in Processing**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="c8d6a-118">이 카운터가 1만에 도달 하면 후속 요청이 실패 하 고 "503-서비스를 사용할 수 없습니다." 라는 오류 메시지가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="c8d6a-118">When this counter reaches 10,000, subsequent requests will fail, with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="c8d6a-119">**대기 중인 ASP. \Requests** (항상 0 이어야 함).</span><span class="sxs-lookup"><span data-stu-id="c8d6a-119">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="c8d6a-120">이러한 값을 만족 하거나 초과 하는 경우 적절 한 CPU 크기 조정에 대 한 용량 계획을 다시 계산 하 고 웹 서비스를 호스팅하는 컴퓨터에 대 한 코어 및 메모리의 수를 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d6a-120">If you meet or exceed these values, you should revisit and re-compute your capacity planning for the correct sizing of CPU, number of cores and memory for the computers hosting the web services.</span></span> 
  
 <span data-ttu-id="c8d6a-121">**모바일 서비스 (Mcx)의 경우:**</span><span class="sxs-lookup"><span data-stu-id="c8d6a-121">**For the Mobility Service (Mcx):**</span></span>
  
- <span data-ttu-id="c8d6a-122">IIS (인터넷 정보 서비스) 관리자의 **Csintmcxapppool** 및 **csextmcxapppool** 작업자 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="c8d6a-122">The **CSIntMcxAppPool** and **CSExtMcxAppPool** worker processes in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="c8d6a-123">**작업자 프로세스** 창에서 **CPU%** 및 **전용 바이트 (KB)** 열을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d6a-123">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="c8d6a-124">**CPU** 및 **프로세서** 성능 카운터입니다.</span><span class="sxs-lookup"><span data-stu-id="c8d6a-124">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="c8d6a-125">대부분의 배포의 경우 모바일 서비스 CPU 사용량은 평균적으로 15% 미만 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d6a-125">For most deployments, Mobility Service CPU usage should be below 15 percent, on average.</span></span> <span data-ttu-id="c8d6a-126">메모리 사용은 [비즈니스용 Skype 서버의 서버 메모리 용량 제한에 대 한 모니터](server-memory-capacity-limits.md)에 설명 된 제한 내에 속해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d6a-126">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="c8d6a-127">CPU 및 메모리 사용 카운터 외에도 다음 ASP.NET 성능 카운터를 사용 하 여 서버에서 요청을 오버 로드할 때이를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8d6a-127">In addition to CPU and memory usage counters, you can use the following ASP.NET performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="c8d6a-128">\**ASP.NET v 2.0.50727 \**서버에서 보류 중인 웹 요청 수를 나타내는 Current 요청입니다.</span><span class="sxs-lookup"><span data-stu-id="c8d6a-128">**ASP.NET v2.0.50727\Requests Current**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="c8d6a-129">이 카운터가 5000에 도달 하면 "503-서비스를 사용할 수 없음" 오류 메시지와 함께 후속 요청이 실패 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8d6a-129">When this counter reaches 5,000, subsequent requests will fail with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="c8d6a-130">**대기 중인 ASP. \Requests** (항상 0 이어야 함).</span><span class="sxs-lookup"><span data-stu-id="c8d6a-130">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="c8d6a-131">이러한 값을 만족 하거나 초과 하는 경우 적절 한 CPU 크기 조정, 코어 수, 웹 서비스를 호스팅하는 컴퓨터의 메모리에 대 한 용량 계획을 다시 계산 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d6a-131">If you meet or exceed these values, you should revisit and recompute your capacity planning for the correct sizing of CPU, number of cores, and memory for the computers hosting the web services.</span></span> 

> [!NOTE]
> <span data-ttu-id="c8d6a-132">이전 모바일 클라이언트에 대 한 MCX (Mobility Service) 지원은 더 이상 비즈니스용 Skype 서버 2019에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c8d6a-132">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="c8d6a-133">현재 모든 비즈니스용 Skype 모바일 클라이언트는 이미 통합 커뮤니케이션 웹 API (인스턴트 메시징 (IM), 현재 상태, 대화 상대 지원)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d6a-133">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="c8d6a-134">MCX를 사용 하는 레거시 클라이언트가 있는 사용자는 현재 클라이언트로 업그레이드 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d6a-134">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c8d6a-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c8d6a-135">See also</span></span>

[<span data-ttu-id="c8d6a-136">비즈니스용 Skype 서버에서 서버 메모리 용량 한도 모니터링</span><span class="sxs-lookup"><span data-stu-id="c8d6a-136">Monitor for server memory capacity limits in Skype for Business Server</span></span>](server-memory-capacity-limits.md)
