---
title: 'Lync Server 2013: IP 및 네트워킹 프로토콜 지원'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IP and networking protocol support
ms:assetid: b0cffb10-3478-445c-89c7-8cb8b5027424
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412848(v=OCS.15)
ms:contentKeyID: 48185128
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a9792ea8365dcd8941b831c43ab0406f9e33b90
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046141"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ip-and-networking-protocol-support-in-lync-server-2013"></a><span data-ttu-id="4777b-102">Lync Server 2013의 IP 및 네트워킹 프로토콜 지원</span><span class="sxs-lookup"><span data-stu-id="4777b-102">IP and networking protocol support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4777b-103">_**마지막으로 수정 된 항목:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="4777b-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="4777b-104">Lync Server 2013에서는 다음과 같은 IP 및 네트워킹 프로토콜을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="4777b-104">Lync Server 2013 supports the following IP and networking protocols:</span></span>

  - <span data-ttu-id="4777b-105">**IP 프로토콜**    Lync Server 2013는 서버 네트워크에 대해 IPV4 (ip 버전 4) 또는 IPV6 (ip 버전 6)을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="4777b-105">**IP Protocols.**   Lync Server 2013 supports either IP version 4 (IPv4) or IP version 6 (IPv6) for the server network.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4777b-106">Lync Server 2013는 이중 IP 스택이 설정 된 네트워크에서 작동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4777b-106">Lync Server 2013 can function in a network with dual IP stack enabled.</span></span>

    
    </div>

  - <span data-ttu-id="4777b-107">**SIP 전송 프로토콜입니다.**    일반적으로 SIP는 사용자 데이터 그램 프로토콜 (UDP), TCP (전송 제어 프로토콜) 및 TLS (전송 계층 보안)를 세 가지 이상의 전송 유형으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4777b-107">**SIP Transport Protocols.**   Generically, SIP can use at least three transport types: User Datagram Protocol (UDP), Transmission Control Protocol (TCP), and Transport Layer Security (TLS).</span></span> <span data-ttu-id="4777b-108">기본 SIP 전송 구성에서는 TLS가 TCP를 통해 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4777b-108">In the default SIP transport configuration, TLS runs over TCP.</span></span> <span data-ttu-id="4777b-109">TLS는 Lync Server 2013 네트워크 내에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4777b-109">TLS is used within the Lync Server 2013 network.</span></span> <span data-ttu-id="4777b-110">네트워크의 경계에서 Lync Server 2013는 TCP를 통해 상호 운용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4777b-110">At the edge of the network, Lync Server 2013 can interoperate over TCP.</span></span> <span data-ttu-id="4777b-111">Lync Server 2013에서는 엔터프라이즈 통신 보안, 안정성 및 확장성에 대 한 최소 표준을 충족 하지 않으므로 SIP 전송에 대 한 UDP를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4777b-111">Lync Server 2013 does not support UDP for SIP transport because it doesn’t meet the minimum standards for enterprise communications security, reliability, and scalability.</span></span> <span data-ttu-id="4777b-112">자세한 내용은 다음 홉 블로그 문서, "udp 또는 UDP를 참조 하세요 [http://go.microsoft.com/fwlink/p/?linkId=185369](http://go.microsoft.com/fwlink/p/?linkid=185369)." (해당 되는 경우)를 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="4777b-112">For details, see the NextHop blog article, "To UDP, or not to UDP, that is the question," at [http://go.microsoft.com/fwlink/p/?linkId=185369](http://go.microsoft.com/fwlink/p/?linkid=185369).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4777b-113">각 블로그의 콘텐츠와 해당 URL은 사전 통지 없이 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4777b-113">The content of each blog and its URL are subject to change without notice.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

