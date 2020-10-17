---
title: 확장 된 디렉터 풀-DNS 부하 분산 및 하드웨어 부하 분산 장치
description: 확장 된 디렉터 풀-DNS 부하 분산 및 하드웨어 부하 분산 장치입니다.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scaled Director pool - DNS load balancing and hardware load balancer
ms:assetid: a1f6ffc0-9e6e-4217-a923-025c9679e154
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205142(v=OCS.15)
ms:contentKeyID: 48185023
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b30dfcc3515420ffb34343e4653e9518b1b9c3ed
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563464"
---
# <a name="scaled-director-pool---dns-load-balancing-and-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="d533d-103">Lync Server 2013의 확장 된 디렉터 풀-DNS 부하 분산 및 하드웨어 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="d533d-103">Scaled Director pool - DNS load balancing and hardware load balancer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d533d-104">_**마지막으로 수정 된 항목:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="d533d-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="d533d-105">확장 된 디렉터 풀-추가 용량을 처리 하 고 고가용성을 제공 하기 위해 배포 된 디렉터가 두 개 이상 있는 경우 부하 분산을 사용 하 여 클라이언트 및 서버 통신을 풀의 모든 구성원에 게 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d533d-105">A scaled Director pool, where there are more than one Director deployed to handle additional capacity and to provide high availability, requires load balancing to distribute client and server communication to all members of the pool.</span></span> <span data-ttu-id="d533d-106">디렉터는 프런트 엔드 풀과 매우 비슷한 방식으로 웹 서비스를 호스팅합니다.</span><span class="sxs-lookup"><span data-stu-id="d533d-106">A Director hosts web services much like a Front End pool.</span></span> <span data-ttu-id="d533d-107">부하 분산을 제공하기 위해 하드웨어 분산이나 DNS(도메인 이름 시스템) 부하 분산 및 하드웨어 부하 분산을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d533d-107">To provide the load balancing, you can use either hardware load balancing or domain name system (DNS) load balancing and hardware load balancing.</span></span> <span data-ttu-id="d533d-108">하드웨어 부하 분산은 웹 서비스에 필요하며 DNS 부하 분산만으로는 웹 서비스에 필요한 기능이 제공되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d533d-108">Hardware load balancing is required for the web services, and DNS load balancing alone does not provide the capabilities required for the web services.</span></span>

<span data-ttu-id="d533d-109">다음 항목에서는 하드웨어 부하 분산과 함께 DNS 부하 분산을 사용 하 여 디렉터 풀을 배포 하기 위한 계획 고려 사항에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d533d-109">The following topics describe the planning considerations for deploying a Director pool using DNS load balancing in conjunction with hardware load balancing.</span></span> <span data-ttu-id="d533d-110">하드웨어 부하 분산을 사용 하지만 디렉터 풀에 대 한 DNS 부하 분산은 해당 토폴로지의 계획 요구 사항을 설명 하는 [Lync Server 2013에서 확장 된 디렉터 풀-하드웨어 부하 분산](lync-server-2013-scaled-director-pool-hardware-load-balancer.md) 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d533d-110">If you intend to use hardware load balancing, but not DNS load balancing for the Director pool, see the topic [Scaled Director pool - hardware load balancer in Lync Server 2013](lync-server-2013-scaled-director-pool-hardware-load-balancer.md) that describes the planning requirements for that topology.</span></span>

<span data-ttu-id="d533d-111">![확장된 디렉터 풀](images/JJ205142.35a78a7a-b781-4c8f-951e-168451ba6a65(OCS.15).jpg "확장된 디렉터 풀")</span><span class="sxs-lookup"><span data-stu-id="d533d-111">![Scaled Director Pool](images/JJ205142.35a78a7a-b781-4c8f-951e-168451ba6a65(OCS.15).jpg "Scaled Director Pool")</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d533d-112">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="d533d-112">In This Section</span></span>

  - [<span data-ttu-id="d533d-113">인증서 요약-Lync Server 2013에서 DNS 및 HLB 부하 분산</span><span class="sxs-lookup"><span data-stu-id="d533d-113">Certificate summary - DNS and HLB load balanced in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [<span data-ttu-id="d533d-114">포트 요약-Lync Server 2013에서 DNS 및 HLB 부하 분산</span><span class="sxs-lookup"><span data-stu-id="d533d-114">Port summary - DNS and HLB load balanced in Lync Server 2013</span></span>](lync-server-2013-port-summary-dns-and-hlb-load-balanced.md)

  - [<span data-ttu-id="d533d-115">DNS 요약-Lync Server 2013에서 DNS 및 HLB 부하 분산</span><span class="sxs-lookup"><span data-stu-id="d533d-115">DNS summary - DNS and HLB load balanced in Lync Server 2013</span></span>](lync-server-2013-dns-summary-dns-and-hlb-load-balanced.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

