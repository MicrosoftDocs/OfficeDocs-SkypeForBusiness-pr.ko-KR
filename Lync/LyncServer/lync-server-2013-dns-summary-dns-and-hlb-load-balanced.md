---
title: 'Lync Server 2013: DNS 요약-DNS 및 HLB 부하 분산 됨'
description: 'Lync Server 2013: DNS 요약-DNS 및 HLB 부하 분산 됨'
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
ms.openlocfilehash: 81c191d653ce4025618e135b4c69bc673f79a6d9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574264"
---
# <a name="dns-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a><span data-ttu-id="1ae96-103">DNS 요약-Lync Server 2013에서 DNS 및 HLB 부하 분산</span><span class="sxs-lookup"><span data-stu-id="1ae96-103">DNS summary - DNS and HLB load balanced in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ae96-104">_**마지막으로 수정 된 항목:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="1ae96-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="1ae96-105">다음 표에는 DNS 부하 분산 및 하드웨어 부하 분산 디렉터를 지 원하는 데 필요한 DNS 레코드에 대 한 요약이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ae96-105">The following table contains a summary of the DNS records that are required to support the DNS load balanced and hardware load balanced Director.</span></span> <span data-ttu-id="1ae96-106">디렉터 역할에는 프런트 엔드 서버로 서 유사한 DNS 레코드가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ae96-106">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="1ae96-107">필요한 레코드 수는 디렉터 인증서에 필요한 주체 대체 이름에 반영 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ae96-107">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="1ae96-108">프런트 엔드 서버와는 다른 디렉터 풀은 사용자 계정을 호스트 하거나 모바일 서비스를 호스트 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1ae96-108">Different from the Front End Server, the Director pool does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director-pool-using-dns-load-balancing-and-hardware-load-balancer"></a><span data-ttu-id="1ae96-109">DNS 부하 분산 및 하드웨어 부하 분산 장치를 사용 하는 디렉터 풀에 필요한 DNS 레코드</span><span class="sxs-lookup"><span data-stu-id="1ae96-109">DNS Records Required for the Director Pool using DNS Load Balancing and Hardware Load Balancer</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1ae96-110">Location/TYPE/Port</span><span class="sxs-lookup"><span data-stu-id="1ae96-110">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="1ae96-111">FQDN/DNS 레코드</span><span class="sxs-lookup"><span data-stu-id="1ae96-111">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="1ae96-112">IP 주소/FQDN</span><span class="sxs-lookup"><span data-stu-id="1ae96-112">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="1ae96-113">매핑 대상/설명</span><span class="sxs-lookup"><span data-stu-id="1ae96-113">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1ae96-114">내부 DNS/A</span><span class="sxs-lookup"><span data-stu-id="1ae96-114">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="1ae96-115">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="1ae96-115">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="1ae96-116">Director</span><span class="sxs-lookup"><span data-stu-id="1ae96-116">Director</span></span></p></td>
<td><p><span data-ttu-id="1ae96-117">복제 및 서버 간 서버에 사용 되는 디렉터 호스트 레코드</span><span class="sxs-lookup"><span data-stu-id="1ae96-117">Director host record used for replication and server to server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ae96-118">내부 DNS/A</span><span class="sxs-lookup"><span data-stu-id="1ae96-118">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="1ae96-119">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="1ae96-119">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="1ae96-120">디렉터 풀</span><span class="sxs-lookup"><span data-stu-id="1ae96-120">Director pool</span></span></p></td>
<td><p><span data-ttu-id="1ae96-121">서버 간 DNS 부하 분산 디렉터 풀에 대 한 호스트 레코드</span><span class="sxs-lookup"><span data-stu-id="1ae96-121">Host record for the DNS load balanced Director pool for server to server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ae96-122">내부 DNS/A</span><span class="sxs-lookup"><span data-stu-id="1ae96-122">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="1ae96-123">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ae96-123">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1ae96-124">디렉터 풀</span><span class="sxs-lookup"><span data-stu-id="1ae96-124">Director pool</span></span></p></td>
<td><p><span data-ttu-id="1ae96-125">에 지 서버의 내부 인터페이스에서 인바운드 SIP (세션 시작 프로토콜)를</span><span class="sxs-lookup"><span data-stu-id="1ae96-125">Inbound session initiation protocol (SIP) from the internal interface of the Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ae96-126">내부 DNS/A</span><span class="sxs-lookup"><span data-stu-id="1ae96-126">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="1ae96-127">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ae96-127">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1ae96-128">디렉터 풀 HLB VIP</span><span class="sxs-lookup"><span data-stu-id="1ae96-128">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="1ae96-129">역방향 프록시의 하드웨어 부하 분산되어 게시된 전화 접속 웹 서비스</span><span class="sxs-lookup"><span data-stu-id="1ae96-129">Hardware load balanced published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ae96-130">내부 DNS/A</span><span class="sxs-lookup"><span data-stu-id="1ae96-130">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="1ae96-131">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ae96-131">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1ae96-132">디렉터 풀 HLB VIP</span><span class="sxs-lookup"><span data-stu-id="1ae96-132">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="1ae96-133">역방향 프록시의 하드웨어 부하 분산되어 게시된 모임 웹 서비스</span><span class="sxs-lookup"><span data-stu-id="1ae96-133">Hardware load balanced published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ae96-134">내부 DNS/A</span><span class="sxs-lookup"><span data-stu-id="1ae96-134">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="1ae96-135">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1ae96-135">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1ae96-136">디렉터 풀 HLB VIP</span><span class="sxs-lookup"><span data-stu-id="1ae96-136">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="1ae96-137">디렉터 풀에 대 한 역방향 프록시 웹 티켓 외부 웹 서비스에서 게시 및 정의한 하드웨어 부하 분산</span><span class="sxs-lookup"><span data-stu-id="1ae96-137">Hardware load balanced published and defined by the reverse proxy Web Ticket external web services for the Director pool</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

