---
title: 'Lync Server 2013: DNS 요약 - DNS 및 HLB 부하 분산됨'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - DNS and HLB load balanced
ms:assetid: d2132695-1956-4190-a98e-cd7255cbded6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205273(v=OCS.15)
ms:contentKeyID: 48185447
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c5b84ccab2b3074662016a19c5f0a51d0cb70405
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737238"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a><span data-ttu-id="fc4d1-102">Lync Server 2013의 DNS 요약 - DNS 및 HLB 부하 분산됨</span><span class="sxs-lookup"><span data-stu-id="fc4d1-102">DNS summary - DNS and HLB load balanced in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fc4d1-103">_**마지막으로 수정한 주제:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="fc4d1-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="fc4d1-104">다음 표에는 DNS 부하 분산 및 하드웨어 부하 분산 디렉터를 지 원하는 데 필요한 DNS 레코드에 대 한 요약이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc4d1-104">The following table contains a summary of the DNS records that are required to support the DNS load balanced and hardware load balanced Director.</span></span> <span data-ttu-id="fc4d1-105">디렉터 역할에는 프런트 엔드 서버로 유사한 DNS 레코드가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc4d1-105">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="fc4d1-106">필요한 레코드 수는 디렉터 인증서에 필요한 주체 대체 이름에 반영 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc4d1-106">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="fc4d1-107">프런트 엔드 서버와 달리 디렉터 풀은 사용자 계정을 호스팅하거나 모바일 서비스를 호스트 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fc4d1-107">Different from the Front End Server, the Director pool does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director-pool-using-dns-load-balancing-and-hardware-load-balancer"></a><span data-ttu-id="fc4d1-108">DNS 부하 분산 및 하드웨어 부하 분산 장치를 사용 하는 디렉터 풀에 필요한 DNS 레코드</span><span class="sxs-lookup"><span data-stu-id="fc4d1-108">DNS Records Required for the Director Pool using DNS Load Balancing and Hardware Load Balancer</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fc4d1-109">위치/형식/포트</span><span class="sxs-lookup"><span data-stu-id="fc4d1-109">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="fc4d1-110">FQDN/DNS 레코드</span><span class="sxs-lookup"><span data-stu-id="fc4d1-110">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="fc4d1-111">IP 주소/FQDN</span><span class="sxs-lookup"><span data-stu-id="fc4d1-111">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="fc4d1-112">/메모에 매핑</span><span class="sxs-lookup"><span data-stu-id="fc4d1-112">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fc4d1-113">내부 DNS/A</span><span class="sxs-lookup"><span data-stu-id="fc4d1-113">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="fc4d1-114">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="fc4d1-114">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="fc4d1-115">Director</span><span class="sxs-lookup"><span data-stu-id="fc4d1-115">Director</span></span></p></td>
<td><p><span data-ttu-id="fc4d1-116">복제 및 서버에서 서버에 사용 되는 디렉터 호스트 레코드</span><span class="sxs-lookup"><span data-stu-id="fc4d1-116">Director host record used for replication and server to server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc4d1-117">내부 DNS/A</span><span class="sxs-lookup"><span data-stu-id="fc4d1-117">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="fc4d1-118">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="fc4d1-118">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="fc4d1-119">디렉터 풀</span><span class="sxs-lookup"><span data-stu-id="fc4d1-119">Director pool</span></span></p></td>
<td><p><span data-ttu-id="fc4d1-120">서버에 대 한 DNS 부하 분산 디렉터 풀의 호스트 레코드</span><span class="sxs-lookup"><span data-stu-id="fc4d1-120">Host record for the DNS load balanced Director pool for server to server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fc4d1-121">내부 DNS/A</span><span class="sxs-lookup"><span data-stu-id="fc4d1-121">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="fc4d1-122">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fc4d1-122">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="fc4d1-123">디렉터 풀</span><span class="sxs-lookup"><span data-stu-id="fc4d1-123">Director pool</span></span></p></td>
<td><p><span data-ttu-id="fc4d1-124">Edge 서버의 내부 인터페이스에 있는 SIP (인바운드 세션 초기화 프로토콜)</span><span class="sxs-lookup"><span data-stu-id="fc4d1-124">Inbound session initiation protocol (SIP) from the internal interface of the Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc4d1-125">내부 DNS/A</span><span class="sxs-lookup"><span data-stu-id="fc4d1-125">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="fc4d1-126">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fc4d1-126">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="fc4d1-127">디렉터 풀 HLB VIP</span><span class="sxs-lookup"><span data-stu-id="fc4d1-127">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="fc4d1-128">리버스 프록시에서 하드웨어 부하 분산 된 전화 접속 웹 서비스를 게시 했습니다.</span><span class="sxs-lookup"><span data-stu-id="fc4d1-128">Hardware load balanced published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fc4d1-129">내부 DNS/A</span><span class="sxs-lookup"><span data-stu-id="fc4d1-129">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="fc4d1-130">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fc4d1-130">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="fc4d1-131">디렉터 풀 HLB VIP</span><span class="sxs-lookup"><span data-stu-id="fc4d1-131">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="fc4d1-132">리버스 프록시에서 웹 서비스에 대 한 하드웨어 부하 분산 게시</span><span class="sxs-lookup"><span data-stu-id="fc4d1-132">Hardware load balanced published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc4d1-133">내부 DNS/A</span><span class="sxs-lookup"><span data-stu-id="fc4d1-133">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="fc4d1-134">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fc4d1-134">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="fc4d1-135">디렉터 풀 HLB VIP</span><span class="sxs-lookup"><span data-stu-id="fc4d1-135">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="fc4d1-136">디렉터 풀에 대 한 역방향 프록시 웹 티켓이 외부 웹 서비스에 의해 게시 되 고 정의 된 하드웨어 부하 분산</span><span class="sxs-lookup"><span data-stu-id="fc4d1-136">Hardware load balanced published and defined by the reverse proxy Web Ticket external web services for the Director pool</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

