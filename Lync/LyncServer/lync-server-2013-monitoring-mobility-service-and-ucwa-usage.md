---
title: 'Lync Server 2013: Mobility Service 및 c;에 대 한 모니터링 사용'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring Mobility Service and UCWA usage
ms:assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690025(v=OCS.15)
ms:contentKeyID: 48184683
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e8fbdd2e411f3613519278f807caed334955810
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048011"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-mobility-service-and-ucwa-usage-in-lync-server-2013"></a><span data-ttu-id="7a58b-102">Lync Server 2013에서 모바일 서비스 및 c u에 대 한 모니터링 사용</span><span class="sxs-lookup"><span data-stu-id="7a58b-102">Monitoring Mobility Service and UCWA usage in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7a58b-103">_**마지막으로 수정 된 항목:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="7a58b-103">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="7a58b-104">지속적으로 Lync Server Mobility Service (Mcx) 및 통합 커뮤니케이션 웹 API (c)에서 사용 하는 CPU 및 메모리를 모니터링 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a58b-104">On an ongoing basis, you should monitor the CPU and memory that is used by the Lync Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="7a58b-105">사용 현황을 모니터링 하려면 다음을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a58b-105">To monitor usage, you can use the following:</span></span>

<span data-ttu-id="7a58b-106">**통합 커뮤니케이션 웹 API (c):**</span><span class="sxs-lookup"><span data-stu-id="7a58b-106">**For Unified Communications Web API (UCWA):**</span></span>

  - <span data-ttu-id="7a58b-107">IIS (인터넷 정보 서비스) 관리자의 **Lyncucwa** 작업자 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="7a58b-107">The **LyncUcwa** worker process in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="7a58b-108">**작업자 프로세스** 창에서 **CPU %** 및 **전용 바이트(KB)**(메모리) 열을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7a58b-108">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>

  - <span data-ttu-id="7a58b-109">**CPU** 및 **프로세서** 성능 카운터</span><span class="sxs-lookup"><span data-stu-id="7a58b-109">The **CPU** and **Processor** performance counters.</span></span>

<span data-ttu-id="7a58b-110">대부분의 배포의 경우에는 평균적으로 15% 미만 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a58b-110">For most deployments, UCWA CPU usage should be below 15 percent on average.</span></span> <span data-ttu-id="7a58b-111">메모리 사용량은 [Lync server 2013의 서버 메모리 용량 제한 모니터링](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)에 설명 된 제한 내에 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a58b-111">Memory usage should fall within the limits described in [Monitoring for server memory capacity limits in Lync Server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).</span></span>

<span data-ttu-id="7a58b-112">CPU 및 메모리 사용 카운터 외에, 다음 성능 카운터를 사용 하 여 서버가 요청에 따라 오버 로드 되는 시기를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a58b-112">In addition to CPU and memory usage counters, you can use the following performance counters to help determine when a server is overloaded with requests:</span></span>

  - <span data-ttu-id="7a58b-113">**LS: 웹 – 제한 및 인증\\웹 –** 서버의 보류 중인 웹 요청 수를 나타내는 총 요청이 처리 중입니다.</span><span class="sxs-lookup"><span data-stu-id="7a58b-113">**LS:WEB – Throttling and Authentication\\WEB – Total Requests in Processing**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="7a58b-114">이 카운터가 1만에 도달 하면 후속 요청이 실패 하 고 "503-서비스를 사용할 수 없습니다." 라는 오류 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a58b-114">When this counter reaches 10,000, subsequent requests will fail, with the error message, "503 - Service Unavailable."</span></span>

  - <span data-ttu-id="7a58b-115">**ASP.NET\\요청** (항상 0 이어야 함)</span><span class="sxs-lookup"><span data-stu-id="7a58b-115">**ASP.NET\\Requests Queued** (should always be zero).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7a58b-116">이러한 값을 충족 하거나 초과 하는 경우에는 웹 서비스를 호스트 하는 컴퓨터에 대 한 올바른 CPU 크기 조정, 코어 수 및 메모리에 대 한 용량 계획을 다시 확인 하 고 계산 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a58b-116">If you meet or exceed these values, you should revisit and re-compute your capacity planning for the correct sizing of CPU, number of cores and memory for the computers hosting the Web services.</span></span>



</div>

<span data-ttu-id="7a58b-117">**모바일 서비스 (Mcx)에 대해 다음을 수행 합니다.**</span><span class="sxs-lookup"><span data-stu-id="7a58b-117">**For the Mobility Service (Mcx):**</span></span>

  - <span data-ttu-id="7a58b-118">IIS (인터넷 정보 서비스) 관리자의 **Csintmcxapppool** 및 **csextmcxapppool** 작업자 프로세스</span><span class="sxs-lookup"><span data-stu-id="7a58b-118">The **CSIntMcxAppPool** and **CSExtMcxAppPool** worker processes in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="7a58b-119">**작업자 프로세스** 창에서 **CPU %** 및 **전용 바이트(KB)**(메모리) 열을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7a58b-119">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>

  - <span data-ttu-id="7a58b-120">**CPU** 및 **프로세서** 성능 카운터</span><span class="sxs-lookup"><span data-stu-id="7a58b-120">The **CPU** and **Processor** performance counters.</span></span>

<span data-ttu-id="7a58b-121">대부분의 배포에서 이동성 서비스 CPU 사용량은 평균적으로 15% 미만 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a58b-121">For most deployments, Mobility Service CPU usage should be below 15 percent, on average.</span></span> <span data-ttu-id="7a58b-122">메모리 사용량은 [Lync server 2013의 서버 메모리 용량 제한 모니터링](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)에 설명 된 제한 내에 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a58b-122">Memory usage should fall within the limits described in [Monitoring for server memory capacity limits in Lync Server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).</span></span>

<span data-ttu-id="7a58b-123">CPU 및 메모리 사용량 카운터 외에 다음 ASP.NET 성능 카운터를 사용하여 서버가 너무 많은 요청으로 인해 오버로드되었는지를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a58b-123">In addition to CPU and memory usage counters, you can use the following ASP.NET performance counters to help determine when a server is overloaded with requests:</span></span>

  - <span data-ttu-id="7a58b-124">**ASP.NET v 2.0.50727\\Requests Current**-서버에서 보류 중인 웹 요청 수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7a58b-124">**ASP.NET v2.0.50727\\Requests Current**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="7a58b-125">이 카운터가 5000에 도달 하면 "503-서비스를 사용할 수 없습니다." 라는 오류 메시지가 표시 되 고 후속 요청이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a58b-125">When this counter reaches 5,000, subsequent requests will fail with the error message, "503 - Service Unavailable."</span></span>

  - <span data-ttu-id="7a58b-126">**ASP.NET\\요청** (항상 0 이어야 함)</span><span class="sxs-lookup"><span data-stu-id="7a58b-126">**ASP.NET\\Requests Queued** (should always be zero).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7a58b-127">이러한 값을 충족 하거나 초과 하는 경우에는 웹 서비스를 호스트 하는 컴퓨터의 정확한 CPU 크기 조정, 코어 수 및 메모리에 대 한 용량 계획을 다시 계산 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a58b-127">If you meet or exceed these values, you should revisit and recompute your capacity planning for the correct sizing of CPU, number of cores, and memory for the computers hosting the Web services.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7a58b-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7a58b-128">See Also</span></span>


[<span data-ttu-id="7a58b-129">Lync Server 2013의 서버 메모리 용량 제한 모니터링</span><span class="sxs-lookup"><span data-stu-id="7a58b-129">Monitoring for server memory capacity limits in Lync Server 2013</span></span>](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

