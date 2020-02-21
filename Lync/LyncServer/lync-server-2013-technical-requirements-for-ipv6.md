---
title: Lync Server 2013 IPv6에 대 한 기술 요구 사항
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for IPv6
ms:assetid: caff0123-ce41-4a62-87a0-00b1d118b72b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205278(v=OCS.15)
ms:contentKeyID: 48185465
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a5565080f2b5fab0f47cc944f9569f55e8721c4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194891"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-ipv6-in-lync-server-2013"></a><span data-ttu-id="b2247-102">Lync Server 2013의 i p v 6에 대 한 기술 요구 사항</span><span class="sxs-lookup"><span data-stu-id="b2247-102">Technical requirements for IPv6 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b2247-103">_**마지막으로 수정 된 항목:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="b2247-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="b2247-104">Lync Server 2013 for IPv6을 구성 하려는 경우에는 다음 요구 사항을 염두에 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2247-104">If you plan to configure Lync Server 2013 for IPv6, keep the following requirements in mind:</span></span>

  - <span data-ttu-id="b2247-105">Lync Server에서 IPv6 주소를 사용 하려면 검색 하 고 IPv6 주소로 확인 해야 하는 레코드에 대해 DNS (domain name system) 레코드를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2247-105">To use IPv6 addresses with Lync Server, you need to create domain name system (DNS) records for records that must be discovered and resolved to an IPv6 address.</span></span> <span data-ttu-id="b2247-106">IPv6 DNS는 호스트 AAAA(4개의 A) 레코드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b2247-106">IPv6 DNS uses host AAAA (quad-A) records.</span></span> <span data-ttu-id="b2247-107">배포 환경에 IPv4 및 IPv6를 모두 사용하는 경우 IPv4에 대한 호스트 A 레코드 및 IPv6에 대한 호스트 AAAA 레코드를 모두 구성하고 유지 관리하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b2247-107">If you use both IPv4 and IPv6 in your deployment, it is best to configure and maintain both host A records for IPv4 and host AAAA records for IPv6.</span></span> <span data-ttu-id="b2247-108">배포 환경을 IPv6로 완전히 전환하는 경우라도 IPv4를 계속 사용하는 외부 사용자를 위해 IPv4 DNS 호스트 레코드가 계속 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2247-108">Even when you fully transition your deployment to IPv6, you may still require IPv4 DNS host records for external users who still use IPv4.</span></span>
    
    <span data-ttu-id="b2247-109">IPv6의 사용을 시작하기 전에 IPv6 DNS 호스트 레코드를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2247-109">You can deploy IPv6 DNS host records before you start using IPv6.</span></span> <span data-ttu-id="b2247-110">클라이언트 또는 서버가 IPv6를 사용하지 않는 경우 레코드는 참조되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b2247-110">If the client or server doesn't use IPv6, the record will not be referenced.</span></span> <span data-ttu-id="b2247-111">변환 기술 구성 및 정책에 기반하여 사용할 레코드가 변환 기술에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2247-111">Transitional technologies will make the decision about which record to use, based on transition technology configuration and policies.</span></span>

  - <span data-ttu-id="b2247-112">각 IPv6 주소에는 범위가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2247-112">Each IPv6 address has a scope.</span></span> <span data-ttu-id="b2247-113">IPv6 주소 지정에 사용할 수 있는 세 가지 범위는 IPv6 글로벌 주소 (공용 IPv4 주소와 유사함), ipv6 고유 로컬 주소 (개인 IPv4 주소 범위와 비슷함) 및 IPv6 링크 로컬 주소 (의 자동 개인 IP 주소와 비슷함) IPv4 용 Windows Server).</span><span class="sxs-lookup"><span data-stu-id="b2247-113">The three scopes that you can use for IPv6 addressing are IPv6 global addresses (similar to public IPv4 addresses), IPv6 unique local addresses (similar to the private IPv4 address ranges), and IPv6 link-local addresses (similar to automatic private IP addresses in Windows Server for IPv4).</span></span> <span data-ttu-id="b2247-114">풀 내의 모든 서버는 동일한 범위의 IPv6 주소를 보유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2247-114">All the servers within a pool should have IPv6 addresses with the same scope.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b2247-115">IPv6은 복잡 한 주제 이며, Windows Server 수준 및 Lync Server 2013 수준에서 할당 하는 주소가 예상 대로 작동 하는지 확인 하는 데 도움이 되도록 네트워킹 팀과 인터넷 공급자를 신중 하 게 계획 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2247-115">IPv6 is a complex topic and requires careful planning with your networking team and your Internet provider to help ensure that the addresses that you assign at the Windows Server level and at the Lync Server 2013 level work as expected.</span></span> <span data-ttu-id="b2247-116">IPv6 주소 지정 및 계획에 대한 추가 리소스는 이 항목의 끝에 있는 링크를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b2247-116">See the links at the end of this topic for additional resources on IPv6 addressing and planning.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b2247-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b2247-117">See Also</span></span>


[<span data-ttu-id="b2247-118">IP 버전 6 주소 지정 아키텍처</span><span class="sxs-lookup"><span data-stu-id="b2247-118">IP Version 6 Addressing Architecture</span></span>](https://tools.ietf.org/html/rfc4291)  
[<span data-ttu-id="b2247-119">IPv6 글로벌 유니캐스트 주소 형식</span><span class="sxs-lookup"><span data-stu-id="b2247-119">IPv6 Global Unicast Address Format</span></span>](https://tools.ietf.org/html/rfc3587)  
[<span data-ttu-id="b2247-120">고유한 로컬 IPv6 유니캐스트 주소</span><span class="sxs-lookup"><span data-stu-id="b2247-120">Unique Local IPv6 Unicast Addresses</span></span>](https://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

