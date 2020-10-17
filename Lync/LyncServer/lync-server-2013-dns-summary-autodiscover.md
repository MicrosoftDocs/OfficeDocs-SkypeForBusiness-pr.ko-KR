---
title: 'Lync Server 2013: DNS 요약-자동 검색'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Autodiscover
ms:assetid: b336a2ae-0e58-4b74-b606-aedbbd411587
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945644(v=OCS.15)
ms:contentKeyID: 51541504
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc30b787d938825f229f28b10d54907ad26a4d35
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501325"
---
# <a name="dns-summary---autodiscover-in-lync-server-2013"></a><span data-ttu-id="bcfe3-102">Lync Server 2013의 DNS 요약-자동 검색</span><span class="sxs-lookup"><span data-stu-id="bcfe3-102">DNS summary - Autodiscover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bcfe3-103">_**마지막으로 수정 된 항목:** 2013-02-13_</span><span class="sxs-lookup"><span data-stu-id="bcfe3-103">_**Topic Last Modified:** 2013-02-13_</span></span>

<span data-ttu-id="bcfe3-104">자동 검색은 HTTP 또는 HTTPS를 통한 통신을 허용 하는 유연한 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="bcfe3-104">Autodiscover is a flexible service in that it will accept communication over HTTP or HTTPS.</span></span> <span data-ttu-id="bcfe3-105">이를 위해 DNS (domain name system) 및 자동 검색 서비스를 호스트 하는 서버에서 사용 하는 인증서를 올바르게 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcfe3-105">To accomplish this, the domain name system (DNS) and the certificates used by servers that host the Autodiscover service must be configured correctly.</span></span> <span data-ttu-id="bcfe3-106">인증서 요구 사항은 [Lync Server 2013의 인증서 요약-자동 검색](lync-server-2013-certificate-summary-autodiscover.md)에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bcfe3-106">Certificate requirements are covered in [Certificate summary - Autodiscover in Lync Server 2013](lync-server-2013-certificate-summary-autodiscover.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="bcfe3-107">Lync Server 클라이언트의 DNS 조회 논리는 구체적인 확인 순서를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcfe3-107">DNS lookup logic for the Lync Server clients uses a specific order of resolution.</span></span> <span data-ttu-id="bcfe3-108">항상 lyncdiscoverinternal를 모두 포함 해야 합니다. &lt; 도메인 &gt; 및 lyncdiscover &lt; &gt; DNS의 도메인</span><span class="sxs-lookup"><span data-stu-id="bcfe3-108">You should always include both the lyncdiscoverinternal.&lt;domain&gt; and the lyncdiscover.&lt;domain&gt; in your DNS.</span></span> <span data-ttu-id="bcfe3-109">Lyncdiscoverinternal를 제외 합니다. &lt; 도메인 레코드를 사용 하면 &gt; 내부 클라이언트가 의도 한 서비스에 연결 하지 못하거나 잘못 된 자동 검색 응답을 받을 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bcfe3-109">Excluding the lyncdiscoverinternal.&lt;domain&gt; record will cause internal clients to fail to connect to the intended services or receive the incorrect Autodiscover response.</span></span>



</div>

### <a name="internal-dns-records"></a><span data-ttu-id="bcfe3-110">내부 DNS 레코드</span><span class="sxs-lookup"><span data-stu-id="bcfe3-110">Internal DNS Records</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bcfe3-111">레코드 종류</span><span class="sxs-lookup"><span data-stu-id="bcfe3-111">Record type</span></span></th>
<th><span data-ttu-id="bcfe3-112">호스트 이름</span><span class="sxs-lookup"><span data-stu-id="bcfe3-112">Host name</span></span></th>
<th><span data-ttu-id="bcfe3-113">확인 대상</span><span class="sxs-lookup"><span data-stu-id="bcfe3-113">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bcfe3-114">CNAME</span><span class="sxs-lookup"><span data-stu-id="bcfe3-114">CNAME</span></span></p></td>
<td><p><span data-ttu-id="bcfe3-115">&lt;Lyncdiscoverinternal 내부 도메인 이름&gt;</span><span class="sxs-lookup"><span data-stu-id="bcfe3-115">Lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
<td><p><span data-ttu-id="bcfe3-116">디렉터 풀에 대 한 내부 웹 서비스 FQDN (있는 경우) 또는 디렉터가 없는 경우 프런트 엔드 풀에 대해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bcfe3-116">Internal Web Services FQDN for your Director pool, if you have one, or for your Front End pool if you do not have a Director.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bcfe3-117">A (호스트, if IPv6, AAAA)</span><span class="sxs-lookup"><span data-stu-id="bcfe3-117">A (host, if IPv6, AAAA)</span></span></p></td>
<td><p><span data-ttu-id="bcfe3-118">&lt;lyncdiscoverinternal 내부 도메인 이름&gt;</span><span class="sxs-lookup"><span data-stu-id="bcfe3-118">lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
<td><p><span data-ttu-id="bcfe3-119">디렉터 풀에 대 한 내부 웹 서비스 IP 주소 (부하 분산 장치를 사용 하는 경우 VIP (가상 IP) 주소)가 있고 디렉터가 없는 경우 프런트 엔드 풀이 하나 이상 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcfe3-119">Internal Web Services IP address (virtual IP (VIP) address if you use a load balancer) of your Director pool, if you have one, or of your Front End pool if you do not have a Director.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="bcfe3-120">다음 외부 DNS 레코드 중 하나를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcfe3-120">You need to create one of the following external DNS records:</span></span>

### <a name="external-dns-records"></a><span data-ttu-id="bcfe3-121">외부 DNS 레코드</span><span class="sxs-lookup"><span data-stu-id="bcfe3-121">External DNS Records</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bcfe3-122">레코드 종류</span><span class="sxs-lookup"><span data-stu-id="bcfe3-122">Record type</span></span></th>
<th><span data-ttu-id="bcfe3-123">호스트 이름</span><span class="sxs-lookup"><span data-stu-id="bcfe3-123">Host name</span></span></th>
<th><span data-ttu-id="bcfe3-124">확인 대상</span><span class="sxs-lookup"><span data-stu-id="bcfe3-124">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bcfe3-125">CNAME</span><span class="sxs-lookup"><span data-stu-id="bcfe3-125">CNAME</span></span></p></td>
<td><p><span data-ttu-id="bcfe3-126">lyncdiscover &lt; microsoft.rtc.management.xds.sipdomain object&gt;</span><span class="sxs-lookup"><span data-stu-id="bcfe3-126">lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="bcfe3-127">디렉터 풀에 대 한 외부 웹 서비스 FQDN (있는 경우) 또는 디렉터가 없는 경우 프런트 엔드 풀의 경우.</span><span class="sxs-lookup"><span data-stu-id="bcfe3-127">External Web Services FQDN for your Director pool, if you have one, or for your Front End pool if you do not have a Director.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bcfe3-128">A (호스트, if IPv6, AAAA)</span><span class="sxs-lookup"><span data-stu-id="bcfe3-128">A (host, if IPv6, AAAA)</span></span></p></td>
<td><p><span data-ttu-id="bcfe3-129">lyncdiscover &lt; microsoft.rtc.management.xds.sipdomain object&gt;</span><span class="sxs-lookup"><span data-stu-id="bcfe3-129">lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="bcfe3-130">역방향 프록시의 외부 또는 공용 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="bcfe3-130">External or public IP address of the reverse proxy.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="bcfe3-131">외부 트래픽은 역방향 프록시를 통과합니다.</span><span class="sxs-lookup"><span data-stu-id="bcfe3-131">External traffic goes through the reverse proxy.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="bcfe3-132">모바일 장치는 서로 다른 도메인에서 여러 SSL(Secure Sockets Layer) 인증서를 지원할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bcfe3-132">Mobile device clients do not support multiple Secure Sockets Layer (SSL) certificates from different domains.</span></span> <span data-ttu-id="bcfe3-133">따라서 HTTPS를 통해서는 다른 도메인으로의 CNAME 리디렉션이 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bcfe3-133">Therefore, CNAME redirection to different domains is not supported over HTTPS.</span></span> <span data-ttu-id="bcfe3-134">예를 들어 director.contoso.net 주소로 리디렉션되는 lyncdiscover.contoso.com의 DNS CNAME 레코드는 HTTPS에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bcfe3-134">For example, a DNS CNAME record for lyncdiscover.contoso.com that redirects to an address of director.contoso.net is not supported over HTTPS.</span></span> <span data-ttu-id="bcfe3-135">이러한 토폴로지에서는 HTTP를 통해 CNAME 리디렉션이 확인되도록 모바일 장치 클라이언트가 첫 번째 요청에 대해 HTTP를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcfe3-135">In such a topology, a mobile device client needs to use HTTP for the first request, so that the CNAME redirection is resolved over HTTP.</span></span> <span data-ttu-id="bcfe3-136">후속 요청에서는 HTTPS를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bcfe3-136">Subsequent requests then use HTTPS.</span></span> <span data-ttu-id="bcfe3-137">이 시나리오를 지원하려면 포트 80(HTTP)에 대한 웹 게시 규칙을 사용하여 역방향 프록시를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcfe3-137">To support this scenario, you need to configure your reverse proxy with a web publishing rule for port 80 (HTTP).</span></span> <span data-ttu-id="bcfe3-138">자세한 내용은 <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Lync Server 2013에서 모바일 기능에 대 한 역방향 프록시 구성</A>의 "포트 80에 대 한 웹 게시 규칙을 만들려면"을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="bcfe3-138">For details, see "To create a web publishing rule for port 80" in <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configuring the reverse proxy for mobility in Lync Server 2013</A>.</span></span> <span data-ttu-id="bcfe3-139">동일한 도메인으로의 CNAME 리디렉션은 HTTPS를 통해 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="bcfe3-139">CNAME redirection to the same domain is supported over HTTPS.</span></span> <span data-ttu-id="bcfe3-140">이 경우 대상 도메인의 인증서가 원래 도메인을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcfe3-140">In this case, the destination domain's certificate covers the originating domain.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bcfe3-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bcfe3-141">See Also</span></span>


[<span data-ttu-id="bcfe3-142">Lync Server 2013에서 모바일 기능에 대 한 역방향 프록시 구성</span><span class="sxs-lookup"><span data-stu-id="bcfe3-142">Configuring the reverse proxy for mobility in Lync Server 2013</span></span>](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md)  


[<span data-ttu-id="bcfe3-143">Lync Server 2013의 인증서 요약-자동 검색</span><span class="sxs-lookup"><span data-stu-id="bcfe3-143">Certificate summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

