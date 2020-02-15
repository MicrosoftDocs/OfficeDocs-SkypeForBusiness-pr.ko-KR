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
ms.openlocfilehash: 88e0d822e14ea1792751338bd3606766cc98ab96
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006704"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-ipv6-in-lync-server-2013"></a>Lync Server 2013의 i p v 6에 대 한 기술 요구 사항

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-30_

Lync Server 2013 for IPv6을 구성 하려는 경우에는 다음 요구 사항을 염두에 두어야 합니다.

  - Lync Server에서 IPv6 주소를 사용 하려면 검색 하 고 IPv6 주소로 확인 해야 하는 레코드에 대해 DNS (domain name system) 레코드를 만들어야 합니다. IPv6 DNS는 호스트 AAAA(4개의 A) 레코드를 사용합니다. 배포 환경에 IPv4 및 IPv6를 모두 사용하는 경우 IPv4에 대한 호스트 A 레코드 및 IPv6에 대한 호스트 AAAA 레코드를 모두 구성하고 유지 관리하는 것이 가장 좋습니다. 배포 환경을 IPv6로 완전히 전환하는 경우라도 IPv4를 계속 사용하는 외부 사용자를 위해 IPv4 DNS 호스트 레코드가 계속 필요할 수 있습니다.
    
    IPv6의 사용을 시작하기 전에 IPv6 DNS 호스트 레코드를 배포할 수 있습니다. 클라이언트 또는 서버가 IPv6를 사용하지 않는 경우 레코드는 참조되지 않습니다. 변환 기술 구성 및 정책에 기반하여 사용할 레코드가 변환 기술에 따라 결정됩니다.

  - 각 IPv6 주소에는 범위가 있습니다. IPv6 주소 지정에 사용할 수 있는 세 가지 범위는 IPv6 글로벌 주소 (공용 IPv4 주소와 유사함), ipv6 고유 로컬 주소 (개인 IPv4 주소 범위와 비슷함) 및 IPv6 링크 로컬 주소 (의 자동 개인 IP 주소와 비슷함) IPv4 용 Windows Server). 풀 내의 모든 서버는 동일한 범위의 IPv6 주소를 보유해야 합니다.

<div>


> [!IMPORTANT]  
> IPv6은 복잡 한 주제 이며, Windows Server 수준 및 Lync Server 2013 수준에서 할당 하는 주소가 예상 대로 작동 하는지 확인 하는 데 도움이 되도록 네트워킹 팀과 인터넷 공급자를 신중 하 게 계획 해야 합니다. IPv6 주소 지정 및 계획에 대한 추가 리소스는 이 항목의 끝에 있는 링크를 참조하십시오.



</div>

<div>

## <a name="see-also"></a>참고 항목


[IP 버전 6 주소 지정 아키텍처](http://tools.ietf.org/html/rfc4291)  
[IPv6 글로벌 유니캐스트 주소 형식](http://tools.ietf.org/html/rfc3587)  
[고유한 로컬 IPv6 유니캐스트 주소](http://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

