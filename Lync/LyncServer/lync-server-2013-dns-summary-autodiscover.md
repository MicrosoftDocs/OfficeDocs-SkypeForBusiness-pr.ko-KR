---
title: 'Lync Server 2013: DNS 요약-자동 검색'
description: 'Lync Server 2013: DNS 요약-자동 검색'
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
ms.openlocfilehash: eef9bd6a2489561145718c7bbf2f710ab0b1f248
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574284"
---
# <a name="dns-summary---autodiscover-in-lync-server-2013"></a><span data-ttu-id="333fc-103">Lync Server 2013의 DNS 요약-자동 검색</span><span class="sxs-lookup"><span data-stu-id="333fc-103">DNS summary - Autodiscover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="333fc-104">_**마지막으로 수정 된 항목:** 2013-02-13_</span><span class="sxs-lookup"><span data-stu-id="333fc-104">_**Topic Last Modified:** 2013-02-13_</span></span>

<span data-ttu-id="333fc-105">자동 검색은 HTTP 또는 HTTPS를 통한 통신을 허용 하는 유연한 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="333fc-105">Autodiscover is a flexible service in that it will accept communication over HTTP or HTTPS.</span></span> <span data-ttu-id="333fc-106">이를 위해 DNS (domain name system) 및 자동 검색 서비스를 호스트 하는 서버에서 사용 하는 인증서를 올바르게 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="333fc-106">To accomplish this, the domain name system (DNS) and the certificates used by servers that host the Autodiscover service must be configured correctly.</span></span> <span data-ttu-id="333fc-107">인증서 요구 사항은 [Lync Server 2013의 인증서 요약-자동 검색](lync-server-2013-certificate-summary-autodiscover.md)에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="333fc-107">Certificate requirements are covered in [Certificate summary - Autodiscover in Lync Server 2013](lync-server-2013-certificate-summary-autodiscover.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="333fc-108">Lync Server 클라이언트의 DNS 조회 논리는 구체적인 확인 순서를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="333fc-108">DNS lookup logic for the Lync Server clients uses a specific order of resolution.</span></span> <span data-ttu-id="333fc-109">항상 lyncdiscoverinternal를 모두 포함 해야 합니다. &lt; 도메인 &gt; 및 lyncdiscover &lt; &gt; DNS의 도메인</span><span class="sxs-lookup"><span data-stu-id="333fc-109">You should always include both the lyncdiscoverinternal.&lt;domain&gt; and the lyncdiscover.&lt;domain&gt; in your DNS.</span></span> <span data-ttu-id="333fc-110">Lyncdiscoverinternal를 제외 합니다. &lt; 도메인 레코드를 사용 하면 &gt; 내부 클라이언트가 의도 한 서비스에 연결 하지 못하거나 잘못 된 자동 검색 응답을 받을 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="333fc-110">Excluding the lyncdiscoverinternal.&lt;domain&gt; record will cause internal clients to fail to connect to the intended services or receive the incorrect Autodiscover response.</span></span>



</div>

### <a name="internal-dns-records"></a><span data-ttu-id="333fc-111">내부 DNS 레코드</span><span class="sxs-lookup"><span data-stu-id="333fc-111">Internal DNS Records</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="333fc-112">레코드 종류</span><span class="sxs-lookup"><span data-stu-id="333fc-112">Record type</span></span></th>
<th><span data-ttu-id="333fc-113">호스트 이름</span><span class="sxs-lookup"><span data-stu-id="333fc-113">Host name</span></span></th>
<th><span data-ttu-id="333fc-114">확인 대상</span><span class="sxs-lookup"><span data-stu-id="333fc-114">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="333fc-115">CNAME</span><span class="sxs-lookup"><span data-stu-id="333fc-115">CNAME</span></span></p></td>
<td><p><span data-ttu-id="333fc-116">&lt;Lyncdiscoverinternal 내부 도메인 이름&gt;</span><span class="sxs-lookup"><span data-stu-id="333fc-116">Lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
<td><p><span data-ttu-id="333fc-117">디렉터 풀에 대 한 내부 웹 서비스 FQDN (있는 경우) 또는 디렉터가 없는 경우 프런트 엔드 풀에 대해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="333fc-117">Internal Web Services FQDN for your Director pool, if you have one, or for your Front End pool if you do not have a Director.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="333fc-118">A (호스트, if IPv6, AAAA)</span><span class="sxs-lookup"><span data-stu-id="333fc-118">A (host, if IPv6, AAAA)</span></span></p></td>
<td><p><span data-ttu-id="333fc-119">&lt;lyncdiscoverinternal 내부 도메인 이름&gt;</span><span class="sxs-lookup"><span data-stu-id="333fc-119">lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
<td><p><span data-ttu-id="333fc-120">디렉터 풀에 대 한 내부 웹 서비스 IP 주소 (부하 분산 장치를 사용 하는 경우 VIP (가상 IP) 주소)가 있고 디렉터가 없는 경우 프런트 엔드 풀이 하나 이상 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="333fc-120">Internal Web Services IP address (virtual IP (VIP) address if you use a load balancer) of your Director pool, if you have one, or of your Front End pool if you do not have a Director.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="333fc-121">다음 외부 DNS 레코드 중 하나를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="333fc-121">You need to create one of the following external DNS records:</span></span>

### <a name="external-dns-records"></a><span data-ttu-id="333fc-122">외부 DNS 레코드</span><span class="sxs-lookup"><span data-stu-id="333fc-122">External DNS Records</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="333fc-123">레코드 종류</span><span class="sxs-lookup"><span data-stu-id="333fc-123">Record type</span></span></th>
<th><span data-ttu-id="333fc-124">호스트 이름</span><span class="sxs-lookup"><span data-stu-id="333fc-124">Host name</span></span></th>
<th><span data-ttu-id="333fc-125">확인 대상</span><span class="sxs-lookup"><span data-stu-id="333fc-125">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="333fc-126">CNAME</span><span class="sxs-lookup"><span data-stu-id="333fc-126">CNAME</span></span></p></td>
<td><p><span data-ttu-id="333fc-127">lyncdiscover &lt; microsoft.rtc.management.xds.sipdomain object&gt;</span><span class="sxs-lookup"><span data-stu-id="333fc-127">lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="333fc-128">디렉터 풀에 대 한 외부 웹 서비스 FQDN (있는 경우) 또는 디렉터가 없는 경우 프런트 엔드 풀의 경우.</span><span class="sxs-lookup"><span data-stu-id="333fc-128">External Web Services FQDN for your Director pool, if you have one, or for your Front End pool if you do not have a Director.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="333fc-129">A (호스트, if IPv6, AAAA)</span><span class="sxs-lookup"><span data-stu-id="333fc-129">A (host, if IPv6, AAAA)</span></span></p></td>
<td><p><span data-ttu-id="333fc-130">lyncdiscover &lt; microsoft.rtc.management.xds.sipdomain object&gt;</span><span class="sxs-lookup"><span data-stu-id="333fc-130">lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="333fc-131">역방향 프록시의 외부 또는 공용 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="333fc-131">External or public IP address of the reverse proxy.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="333fc-132">외부 트래픽은 역방향 프록시를 통과합니다.</span><span class="sxs-lookup"><span data-stu-id="333fc-132">External traffic goes through the reverse proxy.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="333fc-133">모바일 장치는 서로 다른 도메인에서 여러 SSL(Secure Sockets Layer) 인증서를 지원할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="333fc-133">Mobile device clients do not support multiple Secure Sockets Layer (SSL) certificates from different domains.</span></span> <span data-ttu-id="333fc-134">따라서 HTTPS를 통해서는 다른 도메인으로의 CNAME 리디렉션이 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="333fc-134">Therefore, CNAME redirection to different domains is not supported over HTTPS.</span></span> <span data-ttu-id="333fc-135">예를 들어 director.contoso.net 주소로 리디렉션되는 lyncdiscover.contoso.com의 DNS CNAME 레코드는 HTTPS에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="333fc-135">For example, a DNS CNAME record for lyncdiscover.contoso.com that redirects to an address of director.contoso.net is not supported over HTTPS.</span></span> <span data-ttu-id="333fc-136">이러한 토폴로지에서는 HTTP를 통해 CNAME 리디렉션이 확인되도록 모바일 장치 클라이언트가 첫 번째 요청에 대해 HTTP를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="333fc-136">In such a topology, a mobile device client needs to use HTTP for the first request, so that the CNAME redirection is resolved over HTTP.</span></span> <span data-ttu-id="333fc-137">후속 요청에서는 HTTPS를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="333fc-137">Subsequent requests then use HTTPS.</span></span> <span data-ttu-id="333fc-138">이 시나리오를 지원하려면 포트 80(HTTP)에 대한 웹 게시 규칙을 사용하여 역방향 프록시를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="333fc-138">To support this scenario, you need to configure your reverse proxy with a web publishing rule for port 80 (HTTP).</span></span> <span data-ttu-id="333fc-139">자세한 내용은 <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Lync Server 2013에서 모바일 기능에 대 한 역방향 프록시 구성</A>의 "포트 80에 대 한 웹 게시 규칙을 만들려면"을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="333fc-139">For details, see "To create a web publishing rule for port 80" in <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configuring the reverse proxy for mobility in Lync Server 2013</A>.</span></span> <span data-ttu-id="333fc-140">동일한 도메인으로의 CNAME 리디렉션은 HTTPS를 통해 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="333fc-140">CNAME redirection to the same domain is supported over HTTPS.</span></span> <span data-ttu-id="333fc-141">이 경우 대상 도메인의 인증서가 원래 도메인을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="333fc-141">In this case, the destination domain's certificate covers the originating domain.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="333fc-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="333fc-142">See Also</span></span>


[<span data-ttu-id="333fc-143">Lync Server 2013에서 모바일 기능에 대 한 역방향 프록시 구성</span><span class="sxs-lookup"><span data-stu-id="333fc-143">Configuring the reverse proxy for mobility in Lync Server 2013</span></span>](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md)  


[<span data-ttu-id="333fc-144">Lync Server 2013의 인증서 요약-자동 검색</span><span class="sxs-lookup"><span data-stu-id="333fc-144">Certificate summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

