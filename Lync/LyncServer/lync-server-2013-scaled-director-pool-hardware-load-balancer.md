---
title: 'Lync Server 2013: 확장 된 디렉터 풀-하드웨어 부하 분산 장치'
description: 'Lync Server 2013: 확장 된 디렉터 풀-하드웨어 부하 분산 장치입니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scaled Director pool - hardware load balancer
ms:assetid: cf34759a-b384-479c-855f-ea5e80a234b6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205316(v=OCS.15)
ms:contentKeyID: 48185585
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 022c5afb67687149f8ba24655be2a1461d4371f2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578704"
---
# <a name="scaled-director-pool---hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="ef6f2-103">확장 된 디렉터 풀-Lync Server 2013의 하드웨어 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="ef6f2-103">Scaled Director pool - hardware load balancer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ef6f2-104">_**마지막으로 수정 된 항목:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="ef6f2-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="ef6f2-105">확장 된 디렉터 풀: 추가 용량을 처리 하 고 고가용성을 제공 하기 위해 두 개 이상의 디렉터를 배포 하는 경우 부하 분산을 사용 하 여 풀의 모든 구성원에 게 클라이언트 및 서버 통신을 분산 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef6f2-105">A scaled Director pool, where there are more than one Director is deployed to handle additional capacity and to provide high availability, requires load balancing to distribute client and server communication to all members of the pool.</span></span> <span data-ttu-id="ef6f2-106">디렉터는 프런트 엔드 풀과 매우 비슷한 방식으로 웹 서비스를 호스팅합니다.</span><span class="sxs-lookup"><span data-stu-id="ef6f2-106">A Director hosts web services much like a Front End pool.</span></span> <span data-ttu-id="ef6f2-107">웹 서비스에는 하드웨어 부하 분산이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef6f2-107">Hardware load balancing is required for the web services.</span></span>

<span data-ttu-id="ef6f2-108">다음 항목에서는 하드웨어 부하 분산을 사용 하 여 디렉터 풀을 배포 하기 위한 계획 고려 사항에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef6f2-108">The following topics describe the planning considerations for deploying a Director pool using hardware load balancing.</span></span> <span data-ttu-id="ef6f2-109">디렉터 풀에 대 한 하드웨어 부하 분산 및 DNS 부하 분산을 사용 하려는 경우에는 해당 토폴로지의 계획 요구 사항을 설명 하는 [확장 된 디렉터 풀-dns 부하 분산 및 하드웨어 부하 분산 장치 (Lync Server 2013)](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md) 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ef6f2-109">If you intend to use hardware load balancing and DNS load balancing for the Director pool, see the topic [Scaled Director pool - DNS load balancing and hardware load balancer in Lync Server 2013](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md) that describes the planning requirements for that topology.</span></span>

<span data-ttu-id="ef6f2-110">![cfa892b9-5b24-4245-b5bd-c5da21984eeb](images/JJ205316.cfa892b9-5b24-4245-b5bd-c5da21984eeb(OCS.15).jpg "cfa892b9-5b24-4245-b5bd-c5da21984eeb")</span><span class="sxs-lookup"><span data-stu-id="ef6f2-110">![cfa892b9-5b24-4245-b5bd-c5da21984eeb](images/JJ205316.cfa892b9-5b24-4245-b5bd-c5da21984eeb(OCS.15).jpg "cfa892b9-5b24-4245-b5bd-c5da21984eeb")</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ef6f2-111">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="ef6f2-111">In This Section</span></span>

  - [<span data-ttu-id="ef6f2-112">Lync Server 2013의 인증서 요약-확장 된 디렉터 풀, 하드웨어 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="ef6f2-112">Certificate summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-director-pool-hardware-load-balancer.md)

  - [<span data-ttu-id="ef6f2-113">Lync Server 2013의 포트 요약-확장 된 디렉터 풀, 하드웨어 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="ef6f2-113">Port summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-director-pool-hardware-load-balancer.md)

  - [<span data-ttu-id="ef6f2-114">Lync Server 2013의 DNS 요약-조정 된 디렉터 풀, 하드웨어 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="ef6f2-114">DNS summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-director-pool-hardware-load-balancer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

