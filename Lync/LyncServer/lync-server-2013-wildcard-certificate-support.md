---
title: Lync Server 2013 와일드 카드 인증서 지원
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
ms.openlocfilehash: 9d48ba92ffd18e385be95d6218357303a67f892c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149087"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="wildcard-certificate-support-in-lync-server-2013"></a><span data-ttu-id="c17f5-102">Lync Server 2013의 와일드 카드 인증서 지원</span><span class="sxs-lookup"><span data-stu-id="c17f5-102">Wildcard certificate support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c17f5-103">_**마지막으로 수정 된 항목:** 2013-03-21_</span><span class="sxs-lookup"><span data-stu-id="c17f5-103">_**Topic Last Modified:** 2013-03-21_</span></span>

<span data-ttu-id="c17f5-104">Lync Server 2013에서는 인증서를 사용 하 여 통신 암호화 및 서버 id 인증을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c17f5-104">Lync Server 2013 uses certificates to provide communications encryption and server identity authentication.</span></span> <span data-ttu-id="c17f5-105">역방향 프록시를 통한 웹 게시와 같은 일부 경우에 서버의 FQDN(정규화된 도메인 이름)에 대해 강력한 SAN(주체 대체 이름) 항목이 일치하는지 비교할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c17f5-105">In some cases, such as web publishing through the reverse proxy, strong subject alternative name (SAN) entry matching to the fully qualified domain name (FQDN) of the server presenting the service is not required.</span></span> <span data-ttu-id="c17f5-106">이러한 경우 와일드카드 SAN 항목(일반적으로 "와일드카드 인증서"라고 함)에 인증서를 사용하여 공용 인증 기관에서 요청되는 인증서 비용을 줄이고 인증서에 대한 계획 프로세스의 복잡성을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c17f5-106">In these cases, you can use certificates with wildcard SAN entries (commonly known as “wildcard certificates”) to reduce the cost of a certificate requested from a public certification authority and to reduce the complexity of the planning process for certificates.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="c17f5-107">UC(통합 통신) 장치(예: 일반 전화기)의 기능을 보존하려면 와일드카드 인증서를 구현한 다음 장치가 올바르게 작동하도록 보장하기 위해 배포된 인증서를 신중하게 테스트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c17f5-107">To retain the functionality of unified communications (UC) devices (for example, desk phones), you should test the deployed certificate carefully to ensure that devices function properly after you implement a wildcard certificate.</span></span>



</div>

<span data-ttu-id="c17f5-p102">와일드카드 항목은 어떠한 역할에 대해서도 주체 이름(및 CN(공용 이름)이라고도 함)으로 지원되지 않습니다. 다음은 SAN에서 와일드카드 항목을 사용할 때 지원되는 서버 역할입니다.</span><span class="sxs-lookup"><span data-stu-id="c17f5-p102">There is no support for a wildcard entry as the subject name (also referred to as the common name or CN) for any role. The following server roles are supported when using wildcard entries in the SAN:</span></span>

  - <span></span>  
    <span data-ttu-id="c17f5-110">**역방향 프록시**    와일드 카드 SAN 항목은 단순 URL (모임 및 전화 접속) 게시 인증서에 대해 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c17f5-110">**Reverse proxy.**   Wildcard SAN entry is supported for Simple URL (meet and dialin) publishing certificate.</span></span>

  - <span></span>  
    <span data-ttu-id="c17f5-111">**역방향 프록시**    와일드 카드 san 항목은 게시 인증서에서 LyncDiscover의 san 항목에 대해 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c17f5-111">**Reverse proxy.**   Wildcard SAN entry is supported for the SAN entries for LyncDiscover on the publishing certificate.</span></span>

  - <span></span>  
    <span data-ttu-id="c17f5-112">**디렉터입니다.**    와일드 카드 SAN 항목은 디렉터 웹 구성 요소에서 단순 url (모임 및 전화 걸기)과 LyncDiscover 및 LYNCDISCOVERINTERNAL의 SAN 항목에 대해 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c17f5-112">**Director.**   Wildcard SAN entry is supported for Simple URLs (meet and dialin) and for SAN entries for LyncDiscover and LyncDiscoverInternal in Director web components.</span></span>

  - <span></span>  
    <span data-ttu-id="c17f5-113">**프런트 엔드 서버 (Standard Edition) 및 프런트 엔드 풀 (Enterprise Edition)**</span><span class="sxs-lookup"><span data-stu-id="c17f5-113">**Front End Server (Standard Edition) and Front End pool (Enterprise Edition).**</span></span> <span data-ttu-id="c17f5-114">와일드 카드 SAN 항목은 프런트 엔드 웹 구성 요소에서 단순 Url (모임 및 전화 걸기)과 LyncDiscover 및 LyncDiscoverInternal의 SAN 항목에 대해 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c17f5-114">Wildcard SAN entry is supported for Simple URLs (meet and dialin) and for SAN entries for LyncDiscover and LyncDiscoverInternal in Front End web components.</span></span>

  - <span></span>  
    <span data-ttu-id="c17f5-115">**Exchange UM (통합 메시징)**    독립 실행형 서버로 배포 하는 경우 서버에서 SAN 항목을 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c17f5-115">**Exchange Unified Messaging (UM).**   The server does not use SAN entries when deployed as a stand-alone server.</span></span>

  - <span></span>  
    <span data-ttu-id="c17f5-116">**Microsoft Exchange Server 클라이언트 액세스 서버**    SAN의 와일드 카드 항목은 내부 및 외부 클라이언트에 대해 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c17f5-116">**Microsoft Exchange Server Client Access server.**   Wildcard entries in the SAN are supported for internal and external clients.</span></span>

  - <span></span>  
    <span data-ttu-id="c17f5-117">**Exchange UM (통합 메시징) 및 Microsoft Exchange Server 클라이언트 액세스 서버가 동일한 서버에 있는 경우**    와일드 카드 SAN 항목이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c17f5-117">**Exchange Unified Messaging (UM) and Microsoft Exchange Server Client Access server on same server.**   Wildcard SAN entries are supported.</span></span>

<span data-ttu-id="c17f5-118">이 항목에서 다루지 않는 서버 역할:</span><span class="sxs-lookup"><span data-stu-id="c17f5-118">Server roles that are not addressed in this topic:</span></span>

  - <span data-ttu-id="c17f5-119">내부 서버 역할 (예를 들어, 중재 서버, 보관 및 모니터링 서버, Sba (survivable Branch 어플라이언스 또는 Sba (survivable 분기 서버에 제한 되지 않음)</span><span class="sxs-lookup"><span data-stu-id="c17f5-119">Internal server roles (including, but not limited to the Mediation Server, Archiving and Monitoring Server, Survivable Branch Appliance, or Survivable Branch Server)</span></span>

  - <span data-ttu-id="c17f5-120">외부에 지 서버 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c17f5-120">External Edge Server interfaces</span></span>

  - <span data-ttu-id="c17f5-121">내부에 지 서버</span><span class="sxs-lookup"><span data-stu-id="c17f5-121">Internal Edge Server</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c17f5-122">내부에 지 서버 인터페이스의 경우에는 와일드 카드 항목을 SAN에 할당할 수 있으며이를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="c17f5-122">For the internal Edge Server interface, a wildcard entry can be assigned to the SAN, and is supported.</span></span> <span data-ttu-id="c17f5-123">내부에 지 서버의 SAN이 쿼리 되지 않으며 와일드 카드 SAN 항목은 제한 된 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c17f5-123">The SAN on the internal Edge Server is not queried, and a wildcard SAN entry is of limited value.</span></span>

    
    </div>

<span data-ttu-id="c17f5-124">인증서의 와일드 카드 사용을 비롯 한 인증서 구성에 대 한 자세한 내용은 다음 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c17f5-124">For details about certificate configurations, including the use of wildcards in certificates, see the following topics:</span></span>

  - [<span data-ttu-id="c17f5-125">Lync Server 2013의 내부 서버에 대 한 인증서 요구 사항</span><span class="sxs-lookup"><span data-stu-id="c17f5-125">Certificate requirements for internal servers in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [<span data-ttu-id="c17f5-126">Lync Server 2013의 외부 사용자 액세스에 대 한 인증서 요구 사항</span><span class="sxs-lookup"><span data-stu-id="c17f5-126">Certificate requirements for external user access in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [<span data-ttu-id="c17f5-127">인증서 요약-Lync Server 2013에서 DNS 및 HLB 부하 분산</span><span class="sxs-lookup"><span data-stu-id="c17f5-127">Certificate summary - DNS and HLB load balanced in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [<span data-ttu-id="c17f5-128">인증서 요약-Lync Server 2013의 단일 디렉터</span><span class="sxs-lookup"><span data-stu-id="c17f5-128">Certificate summary - Single Director in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-single-director.md)

  - [<span data-ttu-id="c17f5-129">Lync Server 2013의 인증서 요약-확장 된 디렉터 풀, 하드웨어 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="c17f5-129">Certificate summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-director-pool-hardware-load-balancer.md)

  - [<span data-ttu-id="c17f5-130">인증서 요약-Lync Server 2013의 역방향 프록시</span><span class="sxs-lookup"><span data-stu-id="c17f5-130">Certificate summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [<span data-ttu-id="c17f5-131">온-프레미스 통합 메시징과 Lync Server 2013의 통합 지침</span><span class="sxs-lookup"><span data-stu-id="c17f5-131">Guidelines for integrating on-premises Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)

<span data-ttu-id="c17f5-132">와일드 카드 사용을 포함 하 여 Exchange 용 인증서를 구성 하는 방법에 대 한 자세한 내용은 Exchange 2013 제품 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c17f5-132">For details about configuring certificates for Exchange, including the use of wildcards, see the Exchange 2013 product documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

