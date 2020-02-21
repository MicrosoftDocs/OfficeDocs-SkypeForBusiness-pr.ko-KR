---
title: Lync Server 2013 포트 요구 사항
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port requirements
ms:assetid: 9a6c1300-ef88-4181-a8f1-43cd3093962b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398798(v=OCS.15)
ms:contentKeyID: 48184886
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a4ac38534f7d52aca3df9c24cac10be10dee5be6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183951"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-requirements-for-lync-server-2013"></a><span data-ttu-id="47710-102">Lync Server 2013의 포트 요구 사항</span><span class="sxs-lookup"><span data-stu-id="47710-102">Port requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="47710-103">_**마지막으로 수정 된 항목:** 2013-03-27_</span><span class="sxs-lookup"><span data-stu-id="47710-103">_**Topic Last Modified:** 2013-03-27_</span></span>

<span data-ttu-id="47710-104">Lync Server를 사용 하려면 방화벽에서 특정 포트를 열어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47710-104">Lync Server requires that specific ports on the firewall be open.</span></span> <span data-ttu-id="47710-105">또한 IPSec(인터넷 프로토콜 보안)를 조직에 배포한 경우 오디오, 비디오 및 파노라마 비디오의 배달에 사용되는 포트 범위에서 IPSec를 사용하지 않도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47710-105">Additionally, if Internet Protocol security (IPsec) is deployed in your organization, IPsec must be disabled over the range of ports used for the delivery of audio, video, and panorama video.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="47710-106">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="47710-106">In This Section</span></span>

<span data-ttu-id="47710-107">이 섹션에는 다음 항목이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47710-107">This section includes the following topics:</span></span>

  - [<span data-ttu-id="47710-108">Lync Server 2013의 내부 서버에 대 한 포트 및 프로토콜</span><span class="sxs-lookup"><span data-stu-id="47710-108">Ports and protocols for internal servers in Lync Server 2013</span></span>](lync-server-2013-ports-and-protocols-for-internal-servers.md)

  - [<span data-ttu-id="47710-109">Lync Server 2013의 IPsec 예외</span><span class="sxs-lookup"><span data-stu-id="47710-109">IPsec exceptions in Lync Server 2013</span></span>](lync-server-2013-ipsec-exceptions.md)

  - [<span data-ttu-id="47710-110">포트 요약-Lync Server 2013에서 NAT를 사용 하는 개인 IP 주소의 단일 통합에 지</span><span class="sxs-lookup"><span data-stu-id="47710-110">Port summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-port-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="47710-111">포트 요약-Lync Server 2013의 공용 IP 주소를 포함 하는 단일 통합에 지</span><span class="sxs-lookup"><span data-stu-id="47710-111">Port summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-port-summary-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="47710-112">포트 요약-조정 된 통합에 지, Lync Server 2013에서 NAT를 사용 하는 개인 IP 주소의 DNS 부하 분산</span><span class="sxs-lookup"><span data-stu-id="47710-112">Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="47710-113">포트 요약-조정 된 통합에 지, Lync Server 2013의 공용 IP 주소를 사용한 DNS 부하 분산</span><span class="sxs-lookup"><span data-stu-id="47710-113">Port summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [<span data-ttu-id="47710-114">포트 요약-Lync Server 2013의 하드웨어 부하 분산 장치로 확장 된 통합에 지</span><span class="sxs-lookup"><span data-stu-id="47710-114">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [<span data-ttu-id="47710-115">포트 요약-Lync Server 2013의 역방향 프록시</span><span class="sxs-lookup"><span data-stu-id="47710-115">Port summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-port-summary-reverse-proxy.md)

  - [<span data-ttu-id="47710-116">포트 요약-SIP, XMPP 페더레이션 및 Lync Server 2013의 공용 인스턴트 메시징</span><span class="sxs-lookup"><span data-stu-id="47710-116">Port summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

