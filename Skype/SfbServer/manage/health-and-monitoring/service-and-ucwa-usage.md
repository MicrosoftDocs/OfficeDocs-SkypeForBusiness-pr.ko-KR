---
title: 비즈니스용 Skype 서버에서 Mobility Service 및 UCWA 사용 모니터링
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
ms.assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
description: '요약: 비즈니스용 Skype 서버에서 Mcx(Mobility Service) 및 UCWA(Unified Communications Web API)를 관리합니다.'
ms.openlocfilehash: 76bcf8727d3abbb417595f033ce9a59ec00a39ff
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814248"
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server"></a><span data-ttu-id="f6a3a-103">비즈니스용 Skype 서버에서 Mobility Service 및 UCWA 사용 모니터링</span><span class="sxs-lookup"><span data-stu-id="f6a3a-103">Monitor Mobility Service and UCWA usage in Skype for Business Server</span></span>
 
<span data-ttu-id="f6a3a-104">**요약:** 비즈니스용 Skype 서버에서 Mcx(Mobility Service) 및 UCWA(Unified Communications Web API)를 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="f6a3a-104">**Summary:** Manage the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="f6a3a-105">레거시 모바일 클라이언트에 대한 MCX(Mobility Service) 지원은 비즈니스용 Skype 서버 2019에서 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f6a3a-105">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="f6a3a-106">모든 현재 비즈니스용 Skype 모바일 클라이언트는 이미 UCWA(Unified Communications Web API)를 사용하여 IM(인스턴트 메시징), 현재 상태 및 연락처를 지원하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6a3a-106">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="f6a3a-107">MCX를 사용하는 레거시 클라이언트를 사용하는 사용자는 현재 클라이언트로 업그레이드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6a3a-107">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="f6a3a-108">정기적으로 비즈니스용 Skype 서버 모바일 서비스(Mcx) 및 UCWA(Unified Communications Web API)에서 사용하는 CPU 및 메모리를 모니터링해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6a3a-108">On an ongoing basis, you should monitor the CPU and memory that is used by the Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="f6a3a-109">사용 현황을 모니터링하기 위해 다음을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6a3a-109">To monitor usage, you can use the following:</span></span>
  
 <span data-ttu-id="f6a3a-110">**UCWA(Unified Communications Web API)의 경우:**</span><span class="sxs-lookup"><span data-stu-id="f6a3a-110">**For Unified Communications Web API (UCWA):**</span></span>
  
- <span data-ttu-id="f6a3a-111">IIS(인터넷 정보 서비스) 관리자의 **LyncUcwa** Worker 프로세스</span><span class="sxs-lookup"><span data-stu-id="f6a3a-111">The **LyncUcwa** worker process in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="f6a3a-112">**작업자 프로세스** 창에서 **CPU %** 및 **전용 바이트(KB)**(메모리) 열을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f6a3a-112">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="f6a3a-113">**CPU** 및 **프로세서** 성능 카운터</span><span class="sxs-lookup"><span data-stu-id="f6a3a-113">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="f6a3a-114">대부분의 배포에서 UCWA CPU 사용량은 평균적으로 15% 미만입니다.</span><span class="sxs-lookup"><span data-stu-id="f6a3a-114">For most deployments, UCWA CPU usage should be below 15 percent on average.</span></span> <span data-ttu-id="f6a3a-115">메모리 사용량은 비즈니스용 Skype 서버의 서버 메모리 용량 제한 모니터링에 설명된 제한 [내에 해당해야 합니다.](server-memory-capacity-limits.md)</span><span class="sxs-lookup"><span data-stu-id="f6a3a-115">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="f6a3a-116">CPU 및 메모리 사용 카운터 외에도 다음 성능 카운터를 사용하여 서버가 요청으로 오버로드되는 경우를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6a3a-116">In addition to CPU and memory usage counters, you can use the following performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="f6a3a-117">**LS:WEB - 스로틀 및 인증\WEB -** 처리 중인 총 요청 수로, 서버에서 보류 중인 웹 요청 수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f6a3a-117">**LS:WEB - Throttling and Authentication\WEB - Total Requests in Processing**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="f6a3a-118">이 카운터가 10,000에 도달하면 "503 - 서비스를 사용할 수 없습니다."라는 오류 메시지가 표시와 함께 후속 요청이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="f6a3a-118">When this counter reaches 10,000, subsequent requests will fail, with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="f6a3a-119">**ASP.NET\Requests Queued**(항상 0이어야 함).</span><span class="sxs-lookup"><span data-stu-id="f6a3a-119">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="f6a3a-120">이러한 값을 충족하거나 초과하는 경우 올바른 CPU 크기 조정, 웹 서비스를 호스팅하는 컴퓨터의 코어 수 및 메모리에 대한 용량 계획을 다시 계획해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6a3a-120">If you meet or exceed these values, you should revisit and re-compute your capacity planning for the correct sizing of CPU, number of cores and memory for the computers hosting the web services.</span></span> 
  
 <span data-ttu-id="f6a3a-121">**Mobility Service(Mcx)의 경우:**</span><span class="sxs-lookup"><span data-stu-id="f6a3a-121">**For the Mobility Service (Mcx):**</span></span>
  
- <span data-ttu-id="f6a3a-122">IIS(인터넷 정보 서비스) 관리자의 **CSIntMcxAppPool** 및 **CSExtMcxAppPool** worker 프로세스</span><span class="sxs-lookup"><span data-stu-id="f6a3a-122">The **CSIntMcxAppPool** and **CSExtMcxAppPool** worker processes in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="f6a3a-123">**작업자 프로세스** 창에서 **CPU %** 및 **전용 바이트(KB)**(메모리) 열을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f6a3a-123">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="f6a3a-124">**CPU** 및 **프로세서** 성능 카운터</span><span class="sxs-lookup"><span data-stu-id="f6a3a-124">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="f6a3a-125">대부분의 배포에서 Mobility Service CPU 사용량은 평균적으로 15% 미만입니다.</span><span class="sxs-lookup"><span data-stu-id="f6a3a-125">For most deployments, Mobility Service CPU usage should be below 15 percent, on average.</span></span> <span data-ttu-id="f6a3a-126">메모리 사용량은 비즈니스용 Skype 서버의 서버 메모리 용량 제한 모니터링에 설명된 제한 [내에 해당해야 합니다.](server-memory-capacity-limits.md)</span><span class="sxs-lookup"><span data-stu-id="f6a3a-126">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="f6a3a-127">CPU 및 메모리 사용량 카운터 외에 다음 ASP.NET 성능 카운터를 사용하여 서버가 너무 많은 요청으로 인해 오버로드되었는지를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6a3a-127">In addition to CPU and memory usage counters, you can use the following ASP.NET performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="f6a3a-128">ASP.NET 보류 중인 웹 요청 수를 나타내는 **v2.0.50727\Requests Current를** 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f6a3a-128">**ASP.NET v2.0.50727\Requests Current**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="f6a3a-129">이 카운터가 5,000에 도달하면 "503 - 서비스를 사용할 수 없습니다."라는 오류 메시지와 함께 후속 요청이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="f6a3a-129">When this counter reaches 5,000, subsequent requests will fail with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="f6a3a-130">**ASP.NET\Requests Queued**(항상 0이어야 함).</span><span class="sxs-lookup"><span data-stu-id="f6a3a-130">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="f6a3a-131">이러한 값을 충족하거나 초과하는 경우 웹 서비스를 호스팅하는 컴퓨터의 CPU, 코어 수 및 메모리의 올바른 크기 조정을 위해 용량 계획을 다시 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6a3a-131">If you meet or exceed these values, you should revisit and recompute your capacity planning for the correct sizing of CPU, number of cores, and memory for the computers hosting the web services.</span></span> 

> [!NOTE]
> <span data-ttu-id="f6a3a-132">레거시 모바일 클라이언트에 대한 MCX(Mobility Service) 지원은 비즈니스용 Skype 서버 2019에서 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f6a3a-132">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="f6a3a-133">모든 현재 비즈니스용 Skype 모바일 클라이언트는 이미 UCWA(Unified Communications Web API)를 사용하여 IM(인스턴트 메시징), 현재 상태 및 연락처를 지원하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6a3a-133">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="f6a3a-134">MCX를 사용하는 레거시 클라이언트를 사용하는 사용자는 현재 클라이언트로 업그레이드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6a3a-134">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f6a3a-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f6a3a-135">See also</span></span>

[<span data-ttu-id="f6a3a-136">비즈니스용 Skype 서버에서 서버 메모리 용량 제한 모니터링</span><span class="sxs-lookup"><span data-stu-id="f6a3a-136">Monitor for server memory capacity limits in Skype for Business Server</span></span>](server-memory-capacity-limits.md)
