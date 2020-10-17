---
title: 'Lync Server 2013: 성능에 대 한 모바일 기능 모니터링'
description: 'Lync Server 2013: 성능을 위해 모바일 기능을 모니터링 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring mobility for performance
ms:assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690033(v=OCS.15)
ms:contentKeyID: 48184908
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6c366542e88406df043ba1a782ee12cd64bd804
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562904"
---
# <a name="monitoring-mobility-for-performance-in-lync-server-2013"></a><span data-ttu-id="89aaa-103">Lync Server 2013의 성능에 대 한 모바일 기능 모니터링</span><span class="sxs-lookup"><span data-stu-id="89aaa-103">Monitoring mobility for performance in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="89aaa-104">_**마지막으로 수정 된 항목:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="89aaa-104">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="89aaa-105">Lync Server Mobility Service (Mcx) 및 통합 커뮤니케이션 웹 API (FWA)는 프런트 엔드 서버 및 프런트 엔드 풀에 대 한 부하를 증가 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="89aaa-105">The Lync Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA) increase the load on Front End Servers and Front End pools.</span></span> <span data-ttu-id="89aaa-106">Lync 2013 Mobile을 실행 하는 android 및 Apple 장치와 2010 같이 모바일 응용 프로그램을 최소화 한 경우에도 서버에 대 한 연결을 유지 하는 모바일 장치는 모바일 응용 프로그램을 최소화할 때 서버에 대 한 연결을 종료 하는 장치 보다 부하가 더 많이 부과 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89aaa-106">Mobile devices that maintain a connection to the server even when the mobile application is minimized, such as Android and Nokia devices running Lync 2010 Mobile, as well as Android and Apple devices running Lync 2013 Mobile, impose a greater load than devices that terminate their connection to the server when the mobile application is minimized.</span></span> <span data-ttu-id="89aaa-107">이동성 사용량이 증가 함에 따라 모바일 기능 성능을 모니터링 하 여 용량을 늘려야 하는 시기를 결정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89aaa-107">As your mobility usage increases, you must monitor mobility performance to determine when you need to increase your capacity.</span></span>

<span data-ttu-id="89aaa-108">다음과 같은 다양한 제한이 모바일 성능에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="89aaa-108">Several limits influence mobility performance:</span></span>

  - <span data-ttu-id="89aaa-109">사용 가능한 메모리</span><span class="sxs-lookup"><span data-stu-id="89aaa-109">Available memory</span></span>

  - <span data-ttu-id="89aaa-110">요청 큐 제한</span><span class="sxs-lookup"><span data-stu-id="89aaa-110">Request queue limit</span></span>

  - <span data-ttu-id="89aaa-111">동시 연결 수</span><span class="sxs-lookup"><span data-stu-id="89aaa-111">Concurrent connections</span></span>

  - <span data-ttu-id="89aaa-112">IIS 큐 길이</span><span class="sxs-lookup"><span data-stu-id="89aaa-112">IIS queue length</span></span>

<span data-ttu-id="89aaa-113">이동성 성능에 영향을 줄 수 있는 서버의 다른 제한은 최대 12 개의 동시 로그인, 인증, 세션 갱신 및 종료입니다.</span><span class="sxs-lookup"><span data-stu-id="89aaa-113">Other limits on servers that can influence mobility performance are a maximum of twelve concurrent sign-ins, authentications, session renewals, and terminations.</span></span> <span data-ttu-id="89aaa-114">대부분의 배포에서는 이러한 최대값을 수정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="89aaa-114">These maximums do not need to be modified for most deployments.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="89aaa-115">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="89aaa-115">In This Section</span></span>

  - [<span data-ttu-id="89aaa-116">Lync Server 2013의 서버 메모리 용량 제한 모니터링</span><span class="sxs-lookup"><span data-stu-id="89aaa-116">Monitoring for server memory capacity limits in Lync Server 2013</span></span>](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)

  - [<span data-ttu-id="89aaa-117">Lync Server 2013에서 모바일 서비스 및 c u에 대 한 모니터링 사용</span><span class="sxs-lookup"><span data-stu-id="89aaa-117">Monitoring Mobility Service and UCWA usage in Lync Server 2013</span></span>](lync-server-2013-monitoring-mobility-service-and-ucwa-usage.md)

  - [<span data-ttu-id="89aaa-118">Lync Server 2013에서 고성능을 위한 모바일 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="89aaa-118">Configuring Mobility Service for high performance in Lync Server 2013</span></span>](lync-server-2013-configuring-mobility-service-for-high-performance.md)

  - [<span data-ttu-id="89aaa-119">Lync Server 2013에서 IIS 요청 추적 로그 파일 모니터링</span><span class="sxs-lookup"><span data-stu-id="89aaa-119">Monitoring IIS request tracing log files in Lync Server 2013</span></span>](lync-server-2013-monitoring-iis-request-tracing-log-files.md)

  - [<span data-ttu-id="89aaa-120">Lync Server 2013의 모바일 기능 성능 카운터</span><span class="sxs-lookup"><span data-stu-id="89aaa-120">Mobility performance counters in Lync Server 2013</span></span>](lync-server-2013-mobility-performance-counters.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

