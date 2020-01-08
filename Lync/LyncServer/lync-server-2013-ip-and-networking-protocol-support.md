---
title: 'Lync Server 2013: IP 및 네트워킹 프로토콜 지원'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: IP and networking protocol support
ms:assetid: b0cffb10-3478-445c-89c7-8cb8b5027424
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412848(v=OCS.15)
ms:contentKeyID: 48185128
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a35395c9bb7eb8d90e5618ba6afde17defdbbcfd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981513"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ip-and-networking-protocol-support-in-lync-server-2013"></a><span data-ttu-id="158d9-102">Lync Server 2013의 IP 및 네트워킹 프로토콜 지원</span><span class="sxs-lookup"><span data-stu-id="158d9-102">IP and networking protocol support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="158d9-103">_**마지막으로 수정한 주제:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="158d9-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="158d9-104">Lync Server 2013는 다음 IP 및 네트워킹 프로토콜을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="158d9-104">Lync Server 2013 supports the following IP and networking protocols:</span></span>

  - <span data-ttu-id="158d9-105">**IP 프로토콜.**    Lync server 2013는 서버 네트워크에 대 한 ip 버전 4 (IPv4) 또는 IPV6 (ip 버전 6)를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="158d9-105">**IP Protocols.**   Lync Server 2013 supports either IP version 4 (IPv4) or IP version 6 (IPv6) for the server network.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="158d9-106">Lync Server 2013는 이중 IP 스택을 사용 하는 네트워크에서 작동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="158d9-106">Lync Server 2013 can function in a network with dual IP stack enabled.</span></span>

    
    </div>

  - <span data-ttu-id="158d9-107">**SIP 전송 프로토콜.**    일반적으로 SIP는 UDP (사용자 데이터 그램 프로토콜), TCP (전송 제어 프로토콜), TLS (전송 계층 보안)의 세 가지 전송 유형을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="158d9-107">**SIP Transport Protocols.**   Generically, SIP can use at least three transport types: User Datagram Protocol (UDP), Transmission Control Protocol (TCP), and Transport Layer Security (TLS).</span></span> <span data-ttu-id="158d9-108">기본 SIP 전송 구성에서 TLS는 TCP를 통해 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="158d9-108">In the default SIP transport configuration, TLS runs over TCP.</span></span> <span data-ttu-id="158d9-109">TLS는 Lync Server 2013 네트워크 내에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="158d9-109">TLS is used within the Lync Server 2013 network.</span></span> <span data-ttu-id="158d9-110">네트워크의 가장자리에서 Lync Server 2013는 TCP를 통해 상호 작용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="158d9-110">At the edge of the network, Lync Server 2013 can interoperate over TCP.</span></span> <span data-ttu-id="158d9-111">Lync Server 2013는 엔터프라이즈 통신 보안, 안정성 및 확장성에 대 한 최소 표준을 충족 하지 않으므로 SIP 전송에 대 한 UDP를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="158d9-111">Lync Server 2013 does not support UDP for SIP transport because it doesn’t meet the minimum standards for enterprise communications security, reliability, and scalability.</span></span> <span data-ttu-id="158d9-112">자세한 내용은 NextHop 블로그 문서, "UDP 또는 udp에는 해당 하지 않음 (질문은")을 참조 하세요 [http://go.microsoft.com/fwlink/p/?linkId=185369](http://go.microsoft.com/fwlink/p/?linkid=185369).</span><span class="sxs-lookup"><span data-stu-id="158d9-112">For details, see the NextHop blog article, "To UDP, or not to UDP, that is the question," at [http://go.microsoft.com/fwlink/p/?linkId=185369](http://go.microsoft.com/fwlink/p/?linkid=185369).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="158d9-113">각 블로그 및 해당 URL의 콘텐츠는 예 고 없이 변경 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="158d9-113">The content of each blog and its URL are subject to change without notice.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

