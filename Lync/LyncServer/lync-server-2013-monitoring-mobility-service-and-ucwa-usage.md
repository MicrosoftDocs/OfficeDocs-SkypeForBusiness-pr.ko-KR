---
title: 'Lync Server 2013: 모바일 서비스 및 기타 WA 사용 현황 모니터링'
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
ms.openlocfilehash: d4968c1a3b3dc30bdab2a3c19fd8e930da6122cb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756812"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-mobility-service-and-ucwa-usage-in-lync-server-2013"></a><span data-ttu-id="41ace-102">Lync Server 2013에서 모바일 서비스 및이에 대 한 사용 현황 모니터링</span><span class="sxs-lookup"><span data-stu-id="41ace-102">Monitoring Mobility Service and UCWA usage in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41ace-103">_**마지막으로 수정한 주제:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="41ace-103">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="41ace-104">지속적으로 Lync Server Mobility Service (Mcx) 및 통합 커뮤니케이션 웹 API (c)에 사용 되는 CPU와 메모리를 모니터링 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41ace-104">On an ongoing basis, you should monitor the CPU and memory that is used by the Lync Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="41ace-105">사용 현황을 모니터링 하려면 다음을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41ace-105">To monitor usage, you can use the following:</span></span>

<span data-ttu-id="41ace-106">**통합 커뮤니케이션 웹 API (c):**</span><span class="sxs-lookup"><span data-stu-id="41ace-106">**For Unified Communications Web API (UCWA):**</span></span>

  - <span data-ttu-id="41ace-107">IIS (인터넷 정보 서비스) 관리자의 **L C인천** 작업자 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="41ace-107">The **LyncUcwa** worker process in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="41ace-108">**작업자 프로세스** 창에서 **CPU%** 및 **전용 바이트 (KB)** 열을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="41ace-108">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>

  - <span data-ttu-id="41ace-109">**CPU** 및 **프로세서** 성능 카운터입니다.</span><span class="sxs-lookup"><span data-stu-id="41ace-109">The **CPU** and **Processor** performance counters.</span></span>

<span data-ttu-id="41ace-110">대부분의 배포의 경우 fwa CPU 사용이 평균적으로 15% 미만 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41ace-110">For most deployments, UCWA CPU usage should be below 15 percent on average.</span></span> <span data-ttu-id="41ace-111">메모리 사용은 [Lync server 2013의 서버 메모리 용량 제한에 대 한 모니터링](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)에 설명 된 제한 내에 속해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41ace-111">Memory usage should fall within the limits described in [Monitoring for server memory capacity limits in Lync Server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).</span></span>

<span data-ttu-id="41ace-112">CPU 및 메모리 사용 카운터 외에도 다음 성능 카운터를 사용 하 여 서버에서 요청을 오버 로드할 때이를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41ace-112">In addition to CPU and memory usage counters, you can use the following performance counters to help determine when a server is overloaded with requests:</span></span>

  - <span data-ttu-id="41ace-113">**LS: 웹 – 제한 및 인증\\웹 –** 서버의 보류 중인 웹 요청 수를 나타내는 총 요청이 처리 중입니다.</span><span class="sxs-lookup"><span data-stu-id="41ace-113">**LS:WEB – Throttling and Authentication\\WEB – Total Requests in Processing**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="41ace-114">이 카운터가 1만에 도달 하면 후속 요청이 실패 하 고 "503-서비스를 사용할 수 없습니다." 라는 오류 메시지가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="41ace-114">When this counter reaches 10,000, subsequent requests will fail, with the error message, "503 - Service Unavailable."</span></span>

  - <span data-ttu-id="41ace-115">**ASP.NET\\요청 대기열** (항상 0 이어야 함).</span><span class="sxs-lookup"><span data-stu-id="41ace-115">**ASP.NET\\Requests Queued** (should always be zero).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="41ace-116">이러한 값을 만족 하거나 초과 하는 경우 적절 한 CPU 크기 조정에 대 한 용량 계획을 다시 계산 하 고 웹 서비스를 호스팅하는 컴퓨터에 대 한 코어 및 메모리의 수를 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41ace-116">If you meet or exceed these values, you should revisit and re-compute your capacity planning for the correct sizing of CPU, number of cores and memory for the computers hosting the Web services.</span></span>



</div>

<span data-ttu-id="41ace-117">**모바일 서비스 (Mcx)의 경우:**</span><span class="sxs-lookup"><span data-stu-id="41ace-117">**For the Mobility Service (Mcx):**</span></span>

  - <span data-ttu-id="41ace-118">IIS (인터넷 정보 서비스) 관리자의 **Csintmcxapppool** 및 **csextmcxapppool** 작업자 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="41ace-118">The **CSIntMcxAppPool** and **CSExtMcxAppPool** worker processes in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="41ace-119">**작업자 프로세스** 창에서 **CPU%** 및 **전용 바이트 (KB)** 열을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="41ace-119">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>

  - <span data-ttu-id="41ace-120">**CPU** 및 **프로세서** 성능 카운터입니다.</span><span class="sxs-lookup"><span data-stu-id="41ace-120">The **CPU** and **Processor** performance counters.</span></span>

<span data-ttu-id="41ace-121">대부분의 배포의 경우 모바일 서비스 CPU 사용량은 평균적으로 15% 미만 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41ace-121">For most deployments, Mobility Service CPU usage should be below 15 percent, on average.</span></span> <span data-ttu-id="41ace-122">메모리 사용은 [Lync server 2013의 서버 메모리 용량 제한에 대 한 모니터링](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)에 설명 된 제한 내에 속해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41ace-122">Memory usage should fall within the limits described in [Monitoring for server memory capacity limits in Lync Server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).</span></span>

<span data-ttu-id="41ace-123">CPU 및 메모리 사용 카운터 외에도 다음 ASP.NET 성능 카운터를 사용 하 여 서버에서 요청을 오버 로드할 때이를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41ace-123">In addition to CPU and memory usage counters, you can use the following ASP.NET performance counters to help determine when a server is overloaded with requests:</span></span>

  - <span data-ttu-id="41ace-124">서버에서 보류 중인 웹 요청 수를 나타내는 **ASP.NET v 2.0.50727\\Requests Current**</span><span class="sxs-lookup"><span data-stu-id="41ace-124">**ASP.NET v2.0.50727\\Requests Current**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="41ace-125">이 카운터가 5000에 도달 하면 "503-서비스를 사용할 수 없음" 오류 메시지와 함께 후속 요청이 실패 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="41ace-125">When this counter reaches 5,000, subsequent requests will fail with the error message, "503 - Service Unavailable."</span></span>

  - <span data-ttu-id="41ace-126">**ASP.NET\\요청 대기열** (항상 0 이어야 함).</span><span class="sxs-lookup"><span data-stu-id="41ace-126">**ASP.NET\\Requests Queued** (should always be zero).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="41ace-127">이러한 값을 만족 하거나 초과 하는 경우 적절 한 CPU 크기 조정, 코어 수, 웹 서비스를 호스팅하는 컴퓨터의 메모리에 대 한 용량 계획을 다시 계산 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41ace-127">If you meet or exceed these values, you should revisit and recompute your capacity planning for the correct sizing of CPU, number of cores, and memory for the computers hosting the Web services.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="41ace-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="41ace-128">See Also</span></span>


[<span data-ttu-id="41ace-129">Lync Server 2013의 서버 메모리 용량 한도 모니터링</span><span class="sxs-lookup"><span data-stu-id="41ace-129">Monitoring for server memory capacity limits in Lync Server 2013</span></span>](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

