---
title: 'Lync Server 2013: 자동 검색 계획'
description: 'Lync Server 2013: 자동 검색 계획'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Autodiscover
ms:assetid: 51f1ff94-1d64-4e6d-a878-b86fa07edc2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945628(v=OCS.15)
ms:contentKeyID: 51541474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e28a6a3a317f063151eadde7c5de51b02a46b482
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544634"
---
# <a name="planning-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="e3390-103">Lync Server 2013의 자동 검색 계획</span><span class="sxs-lookup"><span data-stu-id="e3390-103">Planning for Autodiscover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3390-104">_**마지막으로 수정 된 항목:** 2013-02-16_</span><span class="sxs-lookup"><span data-stu-id="e3390-104">_**Topic Last Modified:** 2013-02-16_</span></span>

<span data-ttu-id="e3390-105">Lync server 2010 용 누적 업데이트에는 Lync Server에 대 한 자동 검색이 도입 되었습니다 2011.</span><span class="sxs-lookup"><span data-stu-id="e3390-105">Autodiscover was introduced for Lync Server in the Cumulative Update for Lync Server 2010: November 2011.</span></span> <span data-ttu-id="e3390-106">이 초기 자동 검색 구현의 기본 목적은 Lync Mobile이 이동성 서비스 (Mcx)를 찾을 수 있도록 하는 것 이었습니다.</span><span class="sxs-lookup"><span data-stu-id="e3390-106">The primary purpose for this initial implementation of Autodiscover was to provide a means for Lync Mobile to locate the Mobility service (Mcx).</span></span> <span data-ttu-id="e3390-107">Lync Server 2013의 자동 검색 서비스는 이제 모든 클라이언트에서 서버 및 사용자 서비스를 찾는 데 사용 하는 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="e3390-107">The Autodiscover service in Lync Server 2013 is now a service used by all clients to locate server and user services.</span></span> <span data-ttu-id="e3390-108">Microsoft Lync Server 2013 자동 검색 서비스는 디렉터 및 프런트 엔드 서버에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3390-108">The Microsoft Lync Server 2013 Autodiscover service runs on Directors and Front End Servers.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="e3390-109">자동 검색 및 클라이언트와 통신 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-understanding-autodiscover.md">Lync Server 2013의 자동 검색 이해</A>를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e3390-109">For a more technical understanding of Autodiscover and what is communicated to clients, see <A href="lync-server-2013-understanding-autodiscover.md">Understanding Autodiscover in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="e3390-110">이동성은 여전히 고유한 시나리오 이며, 모바일 서비스에는 여전히 특별 한 계획이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3390-110">Mobility is still a distinct scenario and the Mobility services still require some special planning.</span></span> <span data-ttu-id="e3390-111">자세한 내용은 <A href="lync-server-2013-planning-for-mobility.md">Lync Server 2013에서 모바일 기능 계획</A>을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e3390-111">For additional details, see <A href="lync-server-2013-planning-for-mobility.md">Planning for mobility in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="e3390-112">Lync Server 2010에 자동 검색이 도입 된 경우 기존 서버 배포에 대 한 잠재적인 인증서 변경이 필요한 서비스를 구현 하기 위해 수행 해야 하는 손상이 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="e3390-112">When Autodiscover was introduced in Lync Server 2010, there were compromises that needed to be made in order to implement a service that required potential certificate changes to existing server deployments.</span></span> <span data-ttu-id="e3390-113">자동 검색은 HTTPS에 대 한 포트 TCP 443 또는 HTTP에 대 한 포트 TCP 80를 통해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3390-113">Autodiscover could be used over port TCP 443 for HTTPS or over port TCP 80 for HTTP.</span></span> <span data-ttu-id="e3390-114">HTTPS를 사용 하기로 결정 한 경우 필요한 및 DNS 레코드를 수용할 수 있도록 역방향 프록시, 디렉터 및 프런트 엔드 서버의 인증서를 다시 발급 해야 `lyncdiscover.<domain>` `lyncdiscoverinternal.<domain>` 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3390-114">If the decision was made to use HTTPS, certificates on reverse proxies, Directors, and Front End Servers needed to be reissued in order to accommodate the required `lyncdiscover.<domain>` and `lyncdiscoverinternal.<domain>` DNS records.</span></span> <span data-ttu-id="e3390-115">결정이 HTTP를 사용 하는 경우에는 DNS CNAME (또는 별칭) 레코드를 사용 하 여 인증서의 기존 이름을 사용 하 여 인증서를 다시 발급 하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3390-115">If the decision was to use HTTP, the reissue of certificates could be avoided by using DNS CNAME (or alias) records to use existing names on the certificates.</span></span> <span data-ttu-id="e3390-116">HTTP를 사용 하는 경우 초기 통신이 암호화 되지 않았음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3390-116">Using HTTP did mean that the initial communications were unencrypted.</span></span>

<span data-ttu-id="e3390-117">Lync Server 2013에서는 모든 클라이언트에 자동 검색을 사용 하기 때문에 주요 시나리오는 HTTPS를 독점적으로 사용 하 고 lyncdiscover를 사용 하 여 인증서를 만드는 것입니다.\<domain\></span><span class="sxs-lookup"><span data-stu-id="e3390-117">Because Lync Server 2013 uses Autodiscover for all clients, the main scenario is to use HTTPS exclusively and to create certificates with lyncdiscover.\<domain\></span></span> <span data-ttu-id="e3390-118">역방향 프록시, 디렉터 및 프런트 엔드 서버 구성의 일부분입니다.</span><span class="sxs-lookup"><span data-stu-id="e3390-118">as part of the configuration of reverse proxies, Directors and Front End Servers.</span></span> <span data-ttu-id="e3390-119">Lync Server 2010에서 업그레이드 된 배포에 자동 검색을 구현 하는 경우 HTTP를 사용 하 여 인증서를 재발급 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3390-119">If you are implementing Autodiscover into an upgraded deployment from Lync Server 2010, you may want to use HTTP to avoid reissuing certificates.</span></span> <span data-ttu-id="e3390-120">두 시나리오에 대 한 지침은 다음 섹션에서 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3390-120">Guidance for both scenarios is provided in the following sections.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e3390-121">외부 웹 서비스 게시 규칙에서 사용 하는 인증서의 주체 대체 이름 목록에는 <EM>lyncdiscover가 포함 되어야 합니다. &lt; 조직 &gt; </EM> 내의 각 SIP 도메인에 대 한 microsoft.rtc.management.xds.sipdomain object 항목</span><span class="sxs-lookup"><span data-stu-id="e3390-121">The subject alternative name list on certificates used by the external web services publishing rule must contain a <EM>lyncdiscover.&lt;sipdomain&gt;</EM> entry for each SIP domain within your organization.</span></span> <span data-ttu-id="e3390-122">디렉터, 프런트 엔드 서버 및 역방향 프록시에 필요한 주체 대체 이름 항목에 대 한 자세한 내용은 <A href="lync-server-2013-certificate-summary-autodiscover.md">Lync Server 2013의 인증서 요약-자동 검색</A>을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e3390-122">For details about the subject alternative name entries that are required for Directors, Front End Servers, and reverse proxies, see <A href="lync-server-2013-certificate-summary-autodiscover.md">Certificate summary - Autodiscover in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e3390-123">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="e3390-123">In This Section</span></span>

  - [<span data-ttu-id="e3390-124">Lync Server 2013의 인증서 요약-자동 검색</span><span class="sxs-lookup"><span data-stu-id="e3390-124">Certificate summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-autodiscover.md)

  - [<span data-ttu-id="e3390-125">포트 요약-Lync Server 2013의 자동 검색</span><span class="sxs-lookup"><span data-stu-id="e3390-125">Port summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-port-summary-autodiscover.md)

  - [<span data-ttu-id="e3390-126">Lync Server 2013의 DNS 요약-자동 검색</span><span class="sxs-lookup"><span data-stu-id="e3390-126">DNS summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-dns-summary-autodiscover.md)

  - [<span data-ttu-id="e3390-127">Lync Server 2013의 하이브리드 및 분할 도메인 자동 검색</span><span class="sxs-lookup"><span data-stu-id="e3390-127">Hybrid and split-domain - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-hybrid-and-split-domain-autodiscover.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

