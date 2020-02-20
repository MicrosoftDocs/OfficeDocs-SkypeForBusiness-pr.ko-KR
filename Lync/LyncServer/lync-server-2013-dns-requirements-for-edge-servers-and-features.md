---
title: Lync Server 2013:에 지 서버 및 기능에 대 한 DNS 요구 사항
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for Edge Servers and features
ms:assetid: e3bf05c8-96fb-4dd2-acb1-f0d141c9e2ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721912(v=OCS.15)
ms:contentKeyID: 49733846
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3de2c3404a581d7cabb544a89eed43d3c4572a6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153840"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-edge-servers-and-features-in-lync-server-2013"></a><span data-ttu-id="1d1ef-102">Lync Server 2013의에 지 서버 및 기능에 대 한 DNS 요구 사항</span><span class="sxs-lookup"><span data-stu-id="1d1ef-102">DNS requirements for Edge Servers and features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1d1ef-103">_**마지막으로 수정 된 항목:** 2014-04-08_</span><span class="sxs-lookup"><span data-stu-id="1d1ef-103">_**Topic Last Modified:** 2014-04-08_</span></span>

<span data-ttu-id="1d1ef-104">Lync Server 2013 Edge 서버,에 지 풀 및 역방향 프록시에는 DNS (Domain Name System) 레코드에 대 한 특정 요구 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d1ef-104">Lync Server 2013 Edge Servers, Edge pools, and reverse proxies have specific requirements for Domain Name System (DNS) records.</span></span> <span data-ttu-id="1d1ef-105">Lync Server 2013에서 IPv4 및 IPv6을 사용 중인 경우 호스트 A 및 AAAA 레코드를 모두 계획 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d1ef-105">In Lync Server 2013 when IPv4 and IPv6 are in use, you must plan for both host A and AAAA records.</span></span>

<span data-ttu-id="1d1ef-106">다음에 나열된 항목에서는 배포 계획 시 DNS 레코드 사용을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1d1ef-106">The topics listed below define the use of DNS records for your deployment planning:</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="1d1ef-107">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="1d1ef-107">In This Section</span></span>

  - [<span data-ttu-id="1d1ef-108">Lync Server 2013의 DNS 요약-NAT를 사용 하는 개인 IP 주소의 단일 통합에 지</span><span class="sxs-lookup"><span data-stu-id="1d1ef-108">DNS summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-dns-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="1d1ef-109">Lync Server 2013의 DNS 요약-공용 IP 주소를 포함 하는 단일 통합에 지</span><span class="sxs-lookup"><span data-stu-id="1d1ef-109">DNS summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-dns-summary-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="1d1ef-110">Lync Server 2013의 DNS 요약-조정 된 통합에 지, NAT 사용 개인 IP 주소의 DNS 부하 분산</span><span class="sxs-lookup"><span data-stu-id="1d1ef-110">DNS summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="1d1ef-111">DNS 요약-조정 된 통합에 지, Lync Server 2013의 공용 IP 주소를 사용한 DNS 부하 분산</span><span class="sxs-lookup"><span data-stu-id="1d1ef-111">DNS summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [<span data-ttu-id="1d1ef-112">Lync Server 2013의 DNS 요약-하드웨어 부하 분산 장치로 확장 된 통합에 지</span><span class="sxs-lookup"><span data-stu-id="1d1ef-112">DNS summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [<span data-ttu-id="1d1ef-113">Lync Server 2013의 DNS 요약-역방향 프록시</span><span class="sxs-lookup"><span data-stu-id="1d1ef-113">DNS summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-dns-summary-reverse-proxy.md)

  - [<span data-ttu-id="1d1ef-114">DNS 요약-SIP, XMPP 페더레이션 및 Lync Server 2013의 공용 인스턴트 메시징</span><span class="sxs-lookup"><span data-stu-id="1d1ef-114">DNS summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

