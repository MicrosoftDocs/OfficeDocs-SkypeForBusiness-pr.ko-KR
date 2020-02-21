---
title: Lync Server 2013 와일드 카드 인증서 지원
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Wildcard certificate support
ms:assetid: 0bae2aa8-b6dc-46f5-a3be-3fe7581809d4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202161(v=OCS.15)
ms:contentKeyID: 48183382
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 998787b3f052d2271eb2323bcdb71ddc106b57f6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42210234"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="wildcard-certificate-support-in-lync-server-2013"></a>Lync Server 2013의 와일드 카드 인증서 지원

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-03-21_

Lync Server 2013에서는 인증서를 사용 하 여 통신 암호화 및 서버 id 인증을 제공 합니다. 역방향 프록시를 통한 웹 게시와 같은 일부 경우에 서버의 FQDN(정규화된 도메인 이름)에 대해 강력한 SAN(주체 대체 이름) 항목이 일치하는지 비교할 필요는 없습니다. 이러한 경우 와일드카드 SAN 항목(일반적으로 "와일드카드 인증서"라고 함)에 인증서를 사용하여 공용 인증 기관에서 요청되는 인증서 비용을 줄이고 인증서에 대한 계획 프로세스의 복잡성을 줄일 수 있습니다.

<div>


> [!WARNING]  
> UC(통합 통신) 장치(예: 일반 전화기)의 기능을 보존하려면 와일드카드 인증서를 구현한 다음 장치가 올바르게 작동하도록 보장하기 위해 배포된 인증서를 신중하게 테스트해야 합니다.



</div>

와일드카드 항목은 어떠한 역할에 대해서도 주체 이름(및 CN(공용 이름)이라고도 함)으로 지원되지 않습니다. 다음은 SAN에서 와일드카드 항목을 사용할 때 지원되는 서버 역할입니다.

  - <span></span>  
    **역방향 프록시**    와일드 카드 SAN 항목은 단순 URL (모임 및 전화 접속) 게시 인증서에 대해 지원 됩니다.

  - <span></span>  
    **역방향 프록시**    와일드 카드 san 항목은 게시 인증서에서 LyncDiscover의 san 항목에 대해 지원 됩니다.

  - <span></span>  
    **디렉터입니다.**    와일드 카드 SAN 항목은 디렉터 웹 구성 요소에서 단순 url (모임 및 전화 걸기)과 LyncDiscover 및 LYNCDISCOVERINTERNAL의 SAN 항목에 대해 지원 됩니다.

  - <span></span>  
    **프런트 엔드 서버 (Standard Edition) 및 프런트 엔드 풀 (Enterprise Edition)** 와일드 카드 SAN 항목은 프런트 엔드 웹 구성 요소에서 단순 Url (모임 및 전화 걸기)과 LyncDiscover 및 LyncDiscoverInternal의 SAN 항목에 대해 지원 됩니다.

  - <span></span>  
    **Exchange UM (통합 메시징)**    독립 실행형 서버로 배포 하는 경우 서버에서 SAN 항목을 사용 하지 않습니다.

  - <span></span>  
    **Microsoft Exchange Server 클라이언트 액세스 서버**    SAN의 와일드 카드 항목은 내부 및 외부 클라이언트에 대해 지원 됩니다.

  - <span></span>  
    **Exchange UM (통합 메시징) 및 Microsoft Exchange Server 클라이언트 액세스 서버가 동일한 서버에 있는 경우**    와일드 카드 SAN 항목이 지원 됩니다.

이 항목에서 다루지 않는 서버 역할:

  - 내부 서버 역할 (예를 들어, 중재 서버, 보관 및 모니터링 서버, Sba (survivable Branch 어플라이언스 또는 Sba (survivable 분기 서버에 제한 되지 않음)

  - 외부에 지 서버 인터페이스

  - 내부에 지 서버
    
    <div>
    

    > [!NOTE]  
    > 내부에 지 서버 인터페이스의 경우에는 와일드 카드 항목을 SAN에 할당할 수 있으며이를 지원 합니다. 내부에 지 서버의 SAN이 쿼리 되지 않으며 와일드 카드 SAN 항목은 제한 된 값입니다.

    
    </div>

인증서의 와일드 카드 사용을 비롯 한 인증서 구성에 대 한 자세한 내용은 다음 항목을 참조 하십시오.

  - [Lync Server 2013의 내부 서버에 대 한 인증서 요구 사항](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [Lync Server 2013의 외부 사용자 액세스에 대 한 인증서 요구 사항](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [인증서 요약-Lync Server 2013에서 DNS 및 HLB 부하 분산](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [인증서 요약-Lync Server 2013의 단일 디렉터](lync-server-2013-certificate-summary-single-director.md)

  - [Lync Server 2013의 인증서 요약-확장 된 디렉터 풀, 하드웨어 부하 분산 장치](lync-server-2013-certificate-summary-scaled-director-pool-hardware-load-balancer.md)

  - [인증서 요약-Lync Server 2013의 역방향 프록시](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [온-프레미스 통합 메시징과 Lync Server 2013의 통합 지침](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)

와일드 카드 사용을 포함 하 여 Exchange 용 인증서를 구성 하는 방법에 대 한 자세한 내용은 Exchange 2013 제품 설명서를 참조 하십시오.

</div>

<span> </span>

</div>

</div>

</div>

