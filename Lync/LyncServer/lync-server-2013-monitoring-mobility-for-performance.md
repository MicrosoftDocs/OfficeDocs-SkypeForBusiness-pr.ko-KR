---
title: 'Lync Server 2013: 성능에 대 한 모바일 기능 모니터링'
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
ms.openlocfilehash: 0e217e28545eea15a61bf4b4470472cc9944e9b0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531825"
---
# <a name="monitoring-mobility-for-performance-in-lync-server-2013"></a><span data-ttu-id="52194-102">Lync Server 2013의 성능에 대 한 모바일 기능 모니터링</span><span class="sxs-lookup"><span data-stu-id="52194-102">Monitoring mobility for performance in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52194-103">_**마지막으로 수정 된 항목:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="52194-103">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="52194-104">Lync Server Mobility Service (Mcx) 및 통합 커뮤니케이션 웹 API (FWA)는 프런트 엔드 서버 및 프런트 엔드 풀에 대 한 부하를 증가 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="52194-104">The Lync Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA) increase the load on Front End Servers and Front End pools.</span></span> <span data-ttu-id="52194-105">Lync 2013 Mobile을 실행 하는 android 및 Apple 장치와 2010 같이 모바일 응용 프로그램을 최소화 한 경우에도 서버에 대 한 연결을 유지 하는 모바일 장치는 모바일 응용 프로그램을 최소화할 때 서버에 대 한 연결을 종료 하는 장치 보다 부하가 더 많이 부과 됩니다.</span><span class="sxs-lookup"><span data-stu-id="52194-105">Mobile devices that maintain a connection to the server even when the mobile application is minimized, such as Android and Nokia devices running Lync 2010 Mobile, as well as Android and Apple devices running Lync 2013 Mobile, impose a greater load than devices that terminate their connection to the server when the mobile application is minimized.</span></span> <span data-ttu-id="52194-106">이동성 사용량이 증가 함에 따라 모바일 기능 성능을 모니터링 하 여 용량을 늘려야 하는 시기를 결정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52194-106">As your mobility usage increases, you must monitor mobility performance to determine when you need to increase your capacity.</span></span>

<span data-ttu-id="52194-107">다음과 같은 다양한 제한이 모바일 성능에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="52194-107">Several limits influence mobility performance:</span></span>

  - <span data-ttu-id="52194-108">사용 가능한 메모리</span><span class="sxs-lookup"><span data-stu-id="52194-108">Available memory</span></span>

  - <span data-ttu-id="52194-109">요청 큐 제한</span><span class="sxs-lookup"><span data-stu-id="52194-109">Request queue limit</span></span>

  - <span data-ttu-id="52194-110">동시 연결 수</span><span class="sxs-lookup"><span data-stu-id="52194-110">Concurrent connections</span></span>

  - <span data-ttu-id="52194-111">IIS 큐 길이</span><span class="sxs-lookup"><span data-stu-id="52194-111">IIS queue length</span></span>

<span data-ttu-id="52194-112">이동성 성능에 영향을 줄 수 있는 서버의 다른 제한은 최대 12 개의 동시 로그인, 인증, 세션 갱신 및 종료입니다.</span><span class="sxs-lookup"><span data-stu-id="52194-112">Other limits on servers that can influence mobility performance are a maximum of twelve concurrent sign-ins, authentications, session renewals, and terminations.</span></span> <span data-ttu-id="52194-113">대부분의 배포에서는 이러한 최대값을 수정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="52194-113">These maximums do not need to be modified for most deployments.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="52194-114">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="52194-114">In This Section</span></span>

  - [<span data-ttu-id="52194-115">Lync Server 2013의 서버 메모리 용량 제한 모니터링</span><span class="sxs-lookup"><span data-stu-id="52194-115">Monitoring for server memory capacity limits in Lync Server 2013</span></span>](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)

  - [<span data-ttu-id="52194-116">Lync Server 2013에서 모바일 서비스 및 c u에 대 한 모니터링 사용</span><span class="sxs-lookup"><span data-stu-id="52194-116">Monitoring Mobility Service and UCWA usage in Lync Server 2013</span></span>](lync-server-2013-monitoring-mobility-service-and-ucwa-usage.md)

  - [<span data-ttu-id="52194-117">Lync Server 2013에서 고성능을 위한 모바일 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="52194-117">Configuring Mobility Service for high performance in Lync Server 2013</span></span>](lync-server-2013-configuring-mobility-service-for-high-performance.md)

  - [<span data-ttu-id="52194-118">Lync Server 2013에서 IIS 요청 추적 로그 파일 모니터링</span><span class="sxs-lookup"><span data-stu-id="52194-118">Monitoring IIS request tracing log files in Lync Server 2013</span></span>](lync-server-2013-monitoring-iis-request-tracing-log-files.md)

  - [<span data-ttu-id="52194-119">Lync Server 2013의 모바일 기능 성능 카운터</span><span class="sxs-lookup"><span data-stu-id="52194-119">Mobility performance counters in Lync Server 2013</span></span>](lync-server-2013-mobility-performance-counters.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

