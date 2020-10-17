---
title: 'Lync Server 2013: DNS 요약-확장 된 디렉터 풀, 하드웨어 부하 분산 장치'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Scaled Director pool, hardware load balancer
ms:assetid: 08ba48e6-bfa1-4ab0-bc89-d58ddb9c20af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204655(v=OCS.15)
ms:contentKeyID: 48183340
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c7755acc815da690312d2f60c2348076b2231cc5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501265"
---
# <a name="dns-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="0660b-102">Lync Server 2013의 DNS 요약-조정 된 디렉터 풀, 하드웨어 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="0660b-102">DNS summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0660b-103">_**마지막으로 수정 된 항목:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="0660b-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="0660b-104">다음 표에는 하드웨어 부하 분산 디렉터를 지 원하는 데 필요한 DNS 레코드에 대 한 요약이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0660b-104">The following table contains a summary of the DNS records that are required to support the hardware load balanced Director.</span></span> <span data-ttu-id="0660b-105">디렉터 역할에는 프런트 엔드 서버로 서 유사한 DNS 레코드가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="0660b-105">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="0660b-106">필요한 레코드 수는 디렉터 인증서에 필요한 주체 대체 이름에 반영 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0660b-106">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="0660b-107">프런트 엔드 서버와는 다른 디렉터 풀은 사용자 계정을 호스트 하거나 모바일 서비스를 호스트 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0660b-107">Different from the Front End Server, the Director pool does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director-pool-using-a-hardware-load-balancer-and-dns-load-balancing"></a><span data-ttu-id="0660b-108">하드웨어 부하 분산 장치 및 DNS 부하 분산을 사용 하는 디렉터 풀에 필요한 DNS 레코드</span><span class="sxs-lookup"><span data-stu-id="0660b-108">DNS Records Required for the Director pool using a Hardware Load Balancer and DNS Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0660b-109">Location/TYPE/Port</span><span class="sxs-lookup"><span data-stu-id="0660b-109">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="0660b-110">FQDN/DNS 레코드</span><span class="sxs-lookup"><span data-stu-id="0660b-110">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="0660b-111">IP 주소/FQDN</span><span class="sxs-lookup"><span data-stu-id="0660b-111">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="0660b-112">매핑 대상/설명</span><span class="sxs-lookup"><span data-stu-id="0660b-112">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0660b-113">내부 DNS/A</span><span class="sxs-lookup"><span data-stu-id="0660b-113">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="0660b-114">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="0660b-114">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="0660b-115">Director</span><span class="sxs-lookup"><span data-stu-id="0660b-115">Director</span></span></p></td>
<td><p><span data-ttu-id="0660b-116">복제 및 서버 간 통신에 사용 되는 디렉터 호스트 레코드</span><span class="sxs-lookup"><span data-stu-id="0660b-116">Director host record used for replication and server to server communication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0660b-117">내부 DNS/A</span><span class="sxs-lookup"><span data-stu-id="0660b-117">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="0660b-118">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="0660b-118">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="0660b-119">디렉터 풀 HLB VIP</span><span class="sxs-lookup"><span data-stu-id="0660b-119">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="0660b-120">DNS 부하 분산 디렉터 풀에 대 한 호스트 레코드</span><span class="sxs-lookup"><span data-stu-id="0660b-120">Host record for the DNS load balanced Director pool</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0660b-121">내부 DNS/A</span><span class="sxs-lookup"><span data-stu-id="0660b-121">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="0660b-122">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0660b-122">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0660b-123">디렉터 풀 HLB VIP</span><span class="sxs-lookup"><span data-stu-id="0660b-123">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="0660b-124">에 지 서버의 내부 인터페이스에서 인바운드 SIP (세션 시작 프로토콜)를</span><span class="sxs-lookup"><span data-stu-id="0660b-124">Inbound session initiation protocol (SIP) from the internal interface of the Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0660b-125">내부 DNS/A</span><span class="sxs-lookup"><span data-stu-id="0660b-125">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="0660b-126">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0660b-126">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0660b-127">디렉터 풀 HLB VIP</span><span class="sxs-lookup"><span data-stu-id="0660b-127">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="0660b-128">역방향 프록시의 하드웨어 부하 분산되어 게시된 전화 접속 웹 서비스</span><span class="sxs-lookup"><span data-stu-id="0660b-128">Hardware load balanced published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0660b-129">내부 DNS/A</span><span class="sxs-lookup"><span data-stu-id="0660b-129">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="0660b-130">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0660b-130">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0660b-131">디렉터 풀 HLB VIP</span><span class="sxs-lookup"><span data-stu-id="0660b-131">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="0660b-132">역방향 프록시의 하드웨어 부하 분산되어 게시된 모임 웹 서비스</span><span class="sxs-lookup"><span data-stu-id="0660b-132">Hardware load balanced published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0660b-133">내부 DNS/A</span><span class="sxs-lookup"><span data-stu-id="0660b-133">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="0660b-134">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0660b-134">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0660b-135">디렉터 풀 HLB VIP</span><span class="sxs-lookup"><span data-stu-id="0660b-135">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="0660b-136">디렉터 풀에 대 한 역방향 프록시 웹 티켓 외부 웹 서비스에서 게시 및 정의한 하드웨어 부하 분산</span><span class="sxs-lookup"><span data-stu-id="0660b-136">Hardware load balanced published and defined by the reverse proxy Web Ticket external web services for the Director pool</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

