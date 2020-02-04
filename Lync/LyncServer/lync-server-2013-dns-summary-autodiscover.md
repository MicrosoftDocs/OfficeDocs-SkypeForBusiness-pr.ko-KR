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
ms.openlocfilehash: 6ed7d6edb44ebca8656a50aec432fe3c0ac669d8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737348"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---autodiscover-in-lync-server-2013"></a><span data-ttu-id="47c45-102">DNS 요약-Lync Server 2013의 자동 검색</span><span class="sxs-lookup"><span data-stu-id="47c45-102">DNS summary - Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="47c45-103">_**마지막으로 수정한 주제:** 2013-02-13_</span><span class="sxs-lookup"><span data-stu-id="47c45-103">_**Topic Last Modified:** 2013-02-13_</span></span>

<span data-ttu-id="47c45-104">자동 검색은 HTTP 또는 HTTPS를 통한 통신을 허용 하는 유연한 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="47c45-104">Autodiscover is a flexible service in that it will accept communication over HTTP or HTTPS.</span></span> <span data-ttu-id="47c45-105">이를 위해서는 DNS (domain name system) 및 자동 검색 서비스를 호스트 하는 서버에서 사용 하는 인증서가 올바르게 구성 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47c45-105">To accomplish this, the domain name system (DNS) and the certificates used by servers that host the Autodiscover service must be configured correctly.</span></span> <span data-ttu-id="47c45-106">인증서 요구 사항은 [Lync Server 2013의 인증서 요약-자동 검색](lync-server-2013-certificate-summary-autodiscover.md)에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47c45-106">Certificate requirements are covered in [Certificate summary - Autodiscover in Lync Server 2013](lync-server-2013-certificate-summary-autodiscover.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="47c45-107">Lync 서버 클라이언트에 대 한 DNS 조회 논리는 특정 해상도 순서를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="47c45-107">DNS lookup logic for the Lync Server clients uses a specific order of resolution.</span></span> <span data-ttu-id="47c45-108">항상 lyncdiscoverinternal를 포함 해야 합니다. &lt;도메인과&gt; lyncdiscover. &lt;DNS&gt; 의 도메인</span><span class="sxs-lookup"><span data-stu-id="47c45-108">You should always include both the lyncdiscoverinternal.&lt;domain&gt; and the lyncdiscover.&lt;domain&gt; in your DNS.</span></span> <span data-ttu-id="47c45-109">Lyncdiscoverinternal를 제외 합니다. &lt;도메인&gt; 레코드를 사용 하면 내부 클라이언트가 의도 한 서비스에 연결 되지 않거나 잘못 된 자동 검색 응답을 받을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="47c45-109">Excluding the lyncdiscoverinternal.&lt;domain&gt; record will cause internal clients to fail to connect to the intended services or receive the incorrect Autodiscover response.</span></span>



</div>

### <a name="internal-dns-records"></a><span data-ttu-id="47c45-110">내부 DNS 레코드</span><span class="sxs-lookup"><span data-stu-id="47c45-110">Internal DNS Records</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="47c45-111">레코드 종류</span><span class="sxs-lookup"><span data-stu-id="47c45-111">Record type</span></span></th>
<th><span data-ttu-id="47c45-112">호스트 이름</span><span class="sxs-lookup"><span data-stu-id="47c45-112">Host name</span></span></th>
<th><span data-ttu-id="47c45-113">(으)로 확인</span><span class="sxs-lookup"><span data-stu-id="47c45-113">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="47c45-114">CNAME</span><span class="sxs-lookup"><span data-stu-id="47c45-114">CNAME</span></span></p></td>
<td><p><span data-ttu-id="47c45-115">Lyncdiscoverinternal. &lt;내부 도메인 이름&gt;</span><span class="sxs-lookup"><span data-stu-id="47c45-115">Lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
<td><p><span data-ttu-id="47c45-116">디렉터 풀에 대 한 내부 웹 서비스 FQDN (있는 경우) 또는 디렉터가 없는 경우 프런트 엔드 풀에 대해 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="47c45-116">Internal Web Services FQDN for your Director pool, if you have one, or for your Front End pool if you do not have a Director.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47c45-117">A (host, if IPv6, AAAA)</span><span class="sxs-lookup"><span data-stu-id="47c45-117">A (host, if IPv6, AAAA)</span></span></p></td>
<td><p><span data-ttu-id="47c45-118">lyncdiscoverinternal. &lt;내부 도메인 이름&gt;</span><span class="sxs-lookup"><span data-stu-id="47c45-118">lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
<td><p><span data-ttu-id="47c45-119">디렉터 풀 (부하 분산 장치를 사용 하는 경우)의 내부 웹 서비스 IP 주소 (VIP (가상 IP) 주소) 또는 사용자가 디렉터를 보유 하 고 있지 않은 경우 프런트 엔드 풀 중 하나에 해당 하는 경우</span><span class="sxs-lookup"><span data-stu-id="47c45-119">Internal Web Services IP address (virtual IP (VIP) address if you use a load balancer) of your Director pool, if you have one, or of your Front End pool if you do not have a Director.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="47c45-120">다음 외부 DNS 레코드 중 하나를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47c45-120">You need to create one of the following external DNS records:</span></span>

### <a name="external-dns-records"></a><span data-ttu-id="47c45-121">외부 DNS 레코드</span><span class="sxs-lookup"><span data-stu-id="47c45-121">External DNS Records</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="47c45-122">레코드 종류</span><span class="sxs-lookup"><span data-stu-id="47c45-122">Record type</span></span></th>
<th><span data-ttu-id="47c45-123">호스트 이름</span><span class="sxs-lookup"><span data-stu-id="47c45-123">Host name</span></span></th>
<th><span data-ttu-id="47c45-124">(으)로 확인</span><span class="sxs-lookup"><span data-stu-id="47c45-124">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="47c45-125">CNAME</span><span class="sxs-lookup"><span data-stu-id="47c45-125">CNAME</span></span></p></td>
<td><p><span data-ttu-id="47c45-126">lyncdiscover. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="47c45-126">lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="47c45-127">디렉터 풀에 대 한 외부 웹 서비스 FQDN (있는 경우) 또는 디렉터가 없는 경우 프런트 엔드 풀에 대해 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="47c45-127">External Web Services FQDN for your Director pool, if you have one, or for your Front End pool if you do not have a Director.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47c45-128">A (host, if IPv6, AAAA)</span><span class="sxs-lookup"><span data-stu-id="47c45-128">A (host, if IPv6, AAAA)</span></span></p></td>
<td><p><span data-ttu-id="47c45-129">lyncdiscover. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="47c45-129">lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="47c45-130">역방향 프록시의 외부 또는 공용 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="47c45-130">External or public IP address of the reverse proxy.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="47c45-131">외부 트래픽은 리버스 프록시를 거칩니다.</span><span class="sxs-lookup"><span data-stu-id="47c45-131">External traffic goes through the reverse proxy.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="47c45-132">모바일 장치 클라이언트는 서로 다른 도메인의 여러 SSL (Secure Sockets Layer) 인증서를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="47c45-132">Mobile device clients do not support multiple Secure Sockets Layer (SSL) certificates from different domains.</span></span> <span data-ttu-id="47c45-133">따라서 HTTPS를 통해 다른 도메인으로의 CNAME 리디렉션이 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="47c45-133">Therefore, CNAME redirection to different domains is not supported over HTTPS.</span></span> <span data-ttu-id="47c45-134">예를 들어, director.contoso.net의 주소로 리디렉션하는 lyncdiscover.contoso.com에 대 한 DNS CNAME 레코드는 HTTPS를 통해 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="47c45-134">For example, a DNS CNAME record for lyncdiscover.contoso.com that redirects to an address of director.contoso.net is not supported over HTTPS.</span></span> <span data-ttu-id="47c45-135">이러한 토폴로지에서는 모바일 장치 클라이언트가 http를 통해 CNAME 리디렉션이 해결 되도록 첫 번째 요청에 대해 HTTP를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47c45-135">In such a topology, a mobile device client needs to use HTTP for the first request, so that the CNAME redirection is resolved over HTTP.</span></span> <span data-ttu-id="47c45-136">그런 다음 후속 요청에서 HTTPS를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="47c45-136">Subsequent requests then use HTTPS.</span></span> <span data-ttu-id="47c45-137">이 시나리오를 지원 하려면 포트 80 (HTTP)에 대 한 웹 게시 규칙을 사용 하 여 역방향 프록시를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47c45-137">To support this scenario, you need to configure your reverse proxy with a web publishing rule for port 80 (HTTP).</span></span> <span data-ttu-id="47c45-138">자세한 내용은 <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Lync Server 2013에서 이동성에 대 한 리버스 프록시를 구성 하는</A>"포트 80에 대 한 웹 게시 규칙 만들기"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="47c45-138">For details, see "To create a web publishing rule for port 80" in <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configuring the reverse proxy for mobility in Lync Server 2013</A>.</span></span> <span data-ttu-id="47c45-139">동일한 도메인으로의 CNAME 리디렉션은 HTTPS를 통해 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47c45-139">CNAME redirection to the same domain is supported over HTTPS.</span></span> <span data-ttu-id="47c45-140">이 경우 대상 도메인의 인증서가 원래 도메인을 덮습니다.</span><span class="sxs-lookup"><span data-stu-id="47c45-140">In this case, the destination domain's certificate covers the originating domain.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="47c45-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="47c45-141">See Also</span></span>


[<span data-ttu-id="47c45-142">Lync Server 2013에서 모바일 기능에 대해 역방향 프록시 구성</span><span class="sxs-lookup"><span data-stu-id="47c45-142">Configuring the reverse proxy for mobility in Lync Server 2013</span></span>](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md)  


[<span data-ttu-id="47c45-143">인증서 요약-Lync Server 2013의 자동 검색</span><span class="sxs-lookup"><span data-stu-id="47c45-143">Certificate summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

