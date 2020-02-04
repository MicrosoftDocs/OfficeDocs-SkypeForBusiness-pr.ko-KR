---
title: 'Lync Server 2013: 성능에 대 한 이동성 모니터링'
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
ms.openlocfilehash: 53bd9c3450617d4fd1db54b52efe0b0938c84c8b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756822"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-mobility-for-performance-in-lync-server-2013"></a><span data-ttu-id="61e26-102">Lync Server 2013의 성능에 대 한 이동성 모니터링</span><span class="sxs-lookup"><span data-stu-id="61e26-102">Monitoring mobility for performance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="61e26-103">_**마지막으로 수정한 주제:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="61e26-103">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="61e26-104">Lync (서버 이동성 서비스) 및 통합 커뮤니케이션 웹 API (Mcx)는 프런트 엔드 서버 및 프런트 엔드 풀의 부하를 늘립니다.</span><span class="sxs-lookup"><span data-stu-id="61e26-104">The Lync Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA) increase the load on Front End Servers and Front End pools.</span></span> <span data-ttu-id="61e26-105">Lync 및 lync 2013 Mobile을 실행 하는 android 및 Apple 장치는 물론 모바일 응용 프로그램이 2010 최소화 되는 경우에도 서버에 대 한 연결을 유지 하는 모바일 장치는 장치 보다 더 많은 부하를 할 수 있습니다. 모바일 응용 프로그램이 최소화 된 상태에서 서버에 대 한 연결을 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="61e26-105">Mobile devices that maintain a connection to the server even when the mobile application is minimized, such as Android and Nokia devices running Lync 2010 Mobile, as well as Android and Apple devices running Lync 2013 Mobile, impose a greater load than devices that terminate their connection to the server when the mobile application is minimized.</span></span> <span data-ttu-id="61e26-106">이동성 사용량이 증가 함에 따라 이동성 성능을 모니터링 하 여 용량을 늘려야 할 시기를 결정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61e26-106">As your mobility usage increases, you must monitor mobility performance to determine when you need to increase your capacity.</span></span>

<span data-ttu-id="61e26-107">이동성 성능에 영향을 주는 몇 가지 제한은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="61e26-107">Several limits influence mobility performance:</span></span>

  - <span data-ttu-id="61e26-108">사용 가능한 메모리</span><span class="sxs-lookup"><span data-stu-id="61e26-108">Available memory</span></span>

  - <span data-ttu-id="61e26-109">요청 큐 제한</span><span class="sxs-lookup"><span data-stu-id="61e26-109">Request queue limit</span></span>

  - <span data-ttu-id="61e26-110">동시 연결</span><span class="sxs-lookup"><span data-stu-id="61e26-110">Concurrent connections</span></span>

  - <span data-ttu-id="61e26-111">IIS 대기열 길이</span><span class="sxs-lookup"><span data-stu-id="61e26-111">IIS queue length</span></span>

<span data-ttu-id="61e26-112">이동성 성능에 영향을 줄 수 있는 서버의 다른 제한은 최대 12 개의 동시 로그인, 인증, 세션 갱신 및 종료입니다.</span><span class="sxs-lookup"><span data-stu-id="61e26-112">Other limits on servers that can influence mobility performance are a maximum of twelve concurrent sign-ins, authentications, session renewals, and terminations.</span></span> <span data-ttu-id="61e26-113">대부분의 배포의 경우 이러한 최대값을 수정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="61e26-113">These maximums do not need to be modified for most deployments.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="61e26-114">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="61e26-114">In This Section</span></span>

  - [<span data-ttu-id="61e26-115">Lync Server 2013의 서버 메모리 용량 한도 모니터링</span><span class="sxs-lookup"><span data-stu-id="61e26-115">Monitoring for server memory capacity limits in Lync Server 2013</span></span>](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)

  - [<span data-ttu-id="61e26-116">Lync Server 2013에서 모바일 서비스 및이에 대 한 사용 현황 모니터링</span><span class="sxs-lookup"><span data-stu-id="61e26-116">Monitoring Mobility Service and UCWA usage in Lync Server 2013</span></span>](lync-server-2013-monitoring-mobility-service-and-ucwa-usage.md)

  - [<span data-ttu-id="61e26-117">Lync Server 2013에서 고성능을 위한 모바일 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="61e26-117">Configuring Mobility Service for high performance in Lync Server 2013</span></span>](lync-server-2013-configuring-mobility-service-for-high-performance.md)

  - [<span data-ttu-id="61e26-118">Lync Server 2013에서 IIS 요청 추적 로그 파일 모니터링</span><span class="sxs-lookup"><span data-stu-id="61e26-118">Monitoring IIS request tracing log files in Lync Server 2013</span></span>](lync-server-2013-monitoring-iis-request-tracing-log-files.md)

  - [<span data-ttu-id="61e26-119">Lync Server 2013의 이동성 성능 카운터</span><span class="sxs-lookup"><span data-stu-id="61e26-119">Mobility performance counters in Lync Server 2013</span></span>](lync-server-2013-mobility-performance-counters.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

