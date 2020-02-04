---
title: Lync Server 2013 와일드카드 인증서 지원
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Wildcard certificate support
ms:assetid: 0bae2aa8-b6dc-46f5-a3be-3fe7581809d4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202161(v=OCS.15)
ms:contentKeyID: 48183382
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a3e64dcfd16212e618a8ebe152bd2516a25b26d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727498"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="wildcard-certificate-support-in-lync-server-2013"></a><span data-ttu-id="eb78a-102">Lync Server 2013의 와일드카드 인증서 지원</span><span class="sxs-lookup"><span data-stu-id="eb78a-102">Wildcard certificate support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eb78a-103">_**마지막으로 수정한 주제:** 2013-03-21_</span><span class="sxs-lookup"><span data-stu-id="eb78a-103">_**Topic Last Modified:** 2013-03-21_</span></span>

<span data-ttu-id="eb78a-104">Lync 서버 2013는 인증서를 사용 하 여 통신 암호화 및 서버 id 인증을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb78a-104">Lync Server 2013 uses certificates to provide communications encryption and server identity authentication.</span></span> <span data-ttu-id="eb78a-105">리버스 프록시를 통한 웹 게시와 같은 경우에는 서비스를 제공 하는 서버의 FQDN (정규화 된 도메인 이름)과 일치 하는 강력한 주체 대체 이름 (SAN) 항목이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eb78a-105">In some cases, such as web publishing through the reverse proxy, strong subject alternative name (SAN) entry matching to the fully qualified domain name (FQDN) of the server presenting the service is not required.</span></span> <span data-ttu-id="eb78a-106">이러한 경우 와일드 카드 SAN 항목 (일반적으로 "와일드 카드 인증서")에 인증서를 사용 하 여 공개 인증 기관에서 요청한 인증서의 비용을 줄이고 인증서에 대 한 계획 프로세스의 복잡성을 줄일 수 있습니다. .</span><span class="sxs-lookup"><span data-stu-id="eb78a-106">In these cases, you can use certificates with wildcard SAN entries (commonly known as “wildcard certificates”) to reduce the cost of a certificate requested from a public certification authority and to reduce the complexity of the planning process for certificates.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="eb78a-107">통합 커뮤니케이션 (UC) 디바이스 (예: 일반 전화기)의 기능을 유지 하려면 배포 된 인증서를 주의 깊게 테스트 하 여 와일드 카드 인증서를 구현한 후에 장치가 올바르게 작동 하는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb78a-107">To retain the functionality of unified communications (UC) devices (for example, desk phones), you should test the deployed certificate carefully to ensure that devices function properly after you implement a wildcard certificate.</span></span>



</div>

<span data-ttu-id="eb78a-108">와일드 카드 항목은 모든 역할에 대 한 주체 이름 (일반 이름이 나 CN이 라고도 함)으로 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eb78a-108">There is no support for a wildcard entry as the subject name (also referred to as the common name or CN) for any role.</span></span> <span data-ttu-id="eb78a-109">SAN에서 와일드 카드 항목을 사용할 때 다음과 같은 서버 역할이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb78a-109">The following server roles are supported when using wildcard entries in the SAN:</span></span>

  - <span></span>  
    <span data-ttu-id="eb78a-110">**역방향 프록시.**    와일드 카드 SAN 항목은 간단한 URL (모임 및 전화 접속) 게시 인증서에 대해 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb78a-110">**Reverse proxy.**   Wildcard SAN entry is supported for Simple URL (meet and dialin) publishing certificate.</span></span>

  - <span></span>  
    <span data-ttu-id="eb78a-111">**역방향 프록시.**    와일드 카드 san 항목은 게시 인증서에 대 한 LyncDiscover에 대 한 SAN 항목에 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb78a-111">**Reverse proxy.**   Wildcard SAN entry is supported for the SAN entries for LyncDiscover on the publishing certificate.</span></span>

  - <span></span>  
    <span data-ttu-id="eb78a-112">**이사.**    와일드 카드 SAN 항목은 간단한 url (모임 및 전화 접속)과 디렉터 웹 구성 요소의 LyncDiscover 및 LyncDiscoverInternal에 대 한 SAN 항목에 대해 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb78a-112">**Director.**   Wildcard SAN entry is supported for Simple URLs (meet and dialin) and for SAN entries for LyncDiscover and LyncDiscoverInternal in Director web components.</span></span>

  - <span></span>  
    <span data-ttu-id="eb78a-113">**프런트 엔드 서버 (Standard Edition) 및 프런트 엔드 풀 (Enterprise Edition).**</span><span class="sxs-lookup"><span data-stu-id="eb78a-113">**Front End Server (Standard Edition) and Front End pool (Enterprise Edition).**</span></span> <span data-ttu-id="eb78a-114">와일드 카드 SAN 항목은 간단한 Url (모임 및 전화 접속)과 프런트 엔드 웹 구성 요소에 대 한 LyncDiscover 및 LyncDiscoverInternal의 SAN 항목에 대해 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb78a-114">Wildcard SAN entry is supported for Simple URLs (meet and dialin) and for SAN entries for LyncDiscover and LyncDiscoverInternal in Front End web components.</span></span>

  - <span></span>  
    <span data-ttu-id="eb78a-115">**Exchange UM (통합 메시징)**    독립 실행형 서버로 배포 하는 경우 서버에서 SAN 항목을 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eb78a-115">**Exchange Unified Messaging (UM).**   The server does not use SAN entries when deployed as a stand-alone server.</span></span>

  - <span></span>  
    <span data-ttu-id="eb78a-116">**Microsoft Exchange Server 클라이언트 액세스 서버.**    내부 및 외부 클라이언트에 대해 SAN의 와일드 카드 항목이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb78a-116">**Microsoft Exchange Server Client Access server.**   Wildcard entries in the SAN are supported for internal and external clients.</span></span>

  - <span></span>  
    <span data-ttu-id="eb78a-117">**동일한 서버의 exchange UM (통합 메시징) 및 Microsoft Exchange Server 클라이언트 액세스 서버**    와일드 카드 SAN 항목이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb78a-117">**Exchange Unified Messaging (UM) and Microsoft Exchange Server Client Access server on same server.**   Wildcard SAN entries are supported.</span></span>

<span data-ttu-id="eb78a-118">이 항목에서 해결 되지 않는 서버 역할은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="eb78a-118">Server roles that are not addressed in this topic:</span></span>

  - <span data-ttu-id="eb78a-119">내부 서버 역할 (중재 서버, 보관 및 모니터링 서버, Survivable Branch 기기 또는 Survivable Branch 서버는 포함 하지만 제한 되지 않음)</span><span class="sxs-lookup"><span data-stu-id="eb78a-119">Internal server roles (including, but not limited to the Mediation Server, Archiving and Monitoring Server, Survivable Branch Appliance, or Survivable Branch Server)</span></span>

  - <span data-ttu-id="eb78a-120">외부에 지 서버 인터페이스</span><span class="sxs-lookup"><span data-stu-id="eb78a-120">External Edge Server interfaces</span></span>

  - <span data-ttu-id="eb78a-121">내부에 지 서버</span><span class="sxs-lookup"><span data-stu-id="eb78a-121">Internal Edge Server</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="eb78a-122">내부에 지 서버 인터페이스의 경우 와일드 카드 항목을 SAN에 할당할 수 있으며 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb78a-122">For the internal Edge Server interface, a wildcard entry can be assigned to the SAN, and is supported.</span></span> <span data-ttu-id="eb78a-123">내부에 지 서버의 SAN이 쿼리 되지 않고 와일드 카드 SAN 항목의 값이 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb78a-123">The SAN on the internal Edge Server is not queried, and a wildcard SAN entry is of limited value.</span></span>

    
    </div>

<span data-ttu-id="eb78a-124">인증서에 와일드 카드를 사용 하는 것을 포함 하 여 인증 구성에 대 한 자세한 내용은 다음 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="eb78a-124">For details about certificate configurations, including the use of wildcards in certificates, see the following topics:</span></span>

  - [<span data-ttu-id="eb78a-125">Lync Server 2013의 내부 서버에 대한 인증서 요구 사항</span><span class="sxs-lookup"><span data-stu-id="eb78a-125">Certificate requirements for internal servers in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [<span data-ttu-id="eb78a-126">Lync Server 2013의 외부 사용자 액세스에 대한 인증서 요구 사항</span><span class="sxs-lookup"><span data-stu-id="eb78a-126">Certificate requirements for external user access in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [<span data-ttu-id="eb78a-127">인증서 요약 - Lync Server 2013에서 DNS 및 HLB 부하 분산됨</span><span class="sxs-lookup"><span data-stu-id="eb78a-127">Certificate summary - DNS and HLB load balanced in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [<span data-ttu-id="eb78a-128">Lync Server 2013의 인증서 요약 - 단일 디렉터</span><span class="sxs-lookup"><span data-stu-id="eb78a-128">Certificate summary - Single Director in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-single-director.md)

  - [<span data-ttu-id="eb78a-129">Lync Server 2013의 인증서 요약 - 조정된 디렉터 풀, 하드웨어 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="eb78a-129">Certificate summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-director-pool-hardware-load-balancer.md)

  - [<span data-ttu-id="eb78a-130">Lync Server 2013의 인증서 요약 - 역방향 프록시</span><span class="sxs-lookup"><span data-stu-id="eb78a-130">Certificate summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [<span data-ttu-id="eb78a-131">온-프레미스 통합 메시징과 Lync Server 2013의 통합에 대한 지침</span><span class="sxs-lookup"><span data-stu-id="eb78a-131">Guidelines for integrating on-premises Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)

<span data-ttu-id="eb78a-132">와일드 카드 사용을 포함 하 여 Exchange의 인증서를 구성 하는 방법에 대 한 자세한 내용은 Exchange 2013 제품 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="eb78a-132">For details about configuring certificates for Exchange, including the use of wildcards, see the Exchange 2013 product documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

