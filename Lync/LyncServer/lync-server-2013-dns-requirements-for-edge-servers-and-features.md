---
title: 'Lync Server 2013: Edge 서버 및 기능에 대 한 DNS 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS requirements for Edge Servers and features
ms:assetid: e3bf05c8-96fb-4dd2-acb1-f0d141c9e2ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721912(v=OCS.15)
ms:contentKeyID: 49733846
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18c5069e82da9d063cc19e230db7503cd1bc640e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983655"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-edge-servers-and-features-in-lync-server-2013"></a><span data-ttu-id="04f4e-102">Lync Server 2013의 Edge 서버 및 기능에 대 한 DNS 요구 사항</span><span class="sxs-lookup"><span data-stu-id="04f4e-102">DNS requirements for Edge Servers and features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="04f4e-103">_**마지막으로 수정한 주제:** 2014-04-08_</span><span class="sxs-lookup"><span data-stu-id="04f4e-103">_**Topic Last Modified:** 2014-04-08_</span></span>

<span data-ttu-id="04f4e-104">Lync Server 2013 Edge 서버, Edge 풀 및 역방향 프록시에는 DNS (Domain Name System) 레코드에 대 한 특정 요구 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04f4e-104">Lync Server 2013 Edge Servers, Edge pools, and reverse proxies have specific requirements for Domain Name System (DNS) records.</span></span> <span data-ttu-id="04f4e-105">Lync Server 2013에서 IPv4 및 IPv6을 사용 하는 경우 호스트 A 및 AAAA 레코드 모두에 대해 계획을 세워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04f4e-105">In Lync Server 2013 when IPv4 and IPv6 are in use, you must plan for both host A and AAAA records.</span></span>

<span data-ttu-id="04f4e-106">배포 계획에 대 한 DNS 레코드 사용을 정의 하는 아래 항목은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="04f4e-106">The topics listed below define the use of DNS records for your deployment planning:</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="04f4e-107">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="04f4e-107">In This Section</span></span>

  - [<span data-ttu-id="04f4e-108">Lync Server 2013의 DNS 요약 - NAT 사용 개인 IP 주소의 단일 통합 에지</span><span class="sxs-lookup"><span data-stu-id="04f4e-108">DNS summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-dns-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="04f4e-109">Lync Server 2013의 DNS 요약 - 공용 IP 주소의 단일 통합 에지</span><span class="sxs-lookup"><span data-stu-id="04f4e-109">DNS summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-dns-summary-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="04f4e-110">Lync Server 2013의 DNS 요약 - 조정된 통합 에지, NAT 사용 개인 IP 주소의 DNS 부하 분산</span><span class="sxs-lookup"><span data-stu-id="04f4e-110">DNS summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="04f4e-111">Lync Server 2013의 DNS 요약 - 조정된 통합 에지, 공용 IP 주소의 DNS 부하 분산</span><span class="sxs-lookup"><span data-stu-id="04f4e-111">DNS summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [<span data-ttu-id="04f4e-112">Lync Server 2013의 DNS 요약 - 하드웨어 부하 분산 장치를 사용하는 조정된 통합 에지</span><span class="sxs-lookup"><span data-stu-id="04f4e-112">DNS summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [<span data-ttu-id="04f4e-113">Lync Server 2013의 DNS 요약 - 역방향 프록시</span><span class="sxs-lookup"><span data-stu-id="04f4e-113">DNS summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-dns-summary-reverse-proxy.md)

  - [<span data-ttu-id="04f4e-114">DNS 요약-SIP, XMPP 페더레이션 및 Lync Server 2013의 공개 인스턴트 메시지</span><span class="sxs-lookup"><span data-stu-id="04f4e-114">DNS summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

