---
title: Lync Server 2013 와일드카드 인증서 지원
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Wildcard certificate support
ms:assetid: 0bae2aa8-b6dc-46f5-a3be-3fe7581809d4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202161(v=OCS.15)
ms:contentKeyID: 48183382
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9422c3bebbb5fb32be88cfe5c41968207bbed2ec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982821"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="wildcard-certificate-support-in-lync-server-2013"></a>Lync Server 2013의 와일드카드 인증서 지원

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-03-21_

Lync 서버 2013는 인증서를 사용 하 여 통신 암호화 및 서버 id 인증을 제공 합니다. 리버스 프록시를 통한 웹 게시와 같은 경우에는 서비스를 제공 하는 서버의 FQDN (정규화 된 도메인 이름)과 일치 하는 강력한 주체 대체 이름 (SAN) 항목이 필요 하지 않습니다. 이러한 경우 와일드 카드 SAN 항목 (일반적으로 "와일드 카드 인증서")에 인증서를 사용 하 여 공개 인증 기관에서 요청한 인증서의 비용을 줄이고 인증서에 대 한 계획 프로세스의 복잡성을 줄일 수 있습니다. .

<div>


> [!WARNING]  
> 통합 커뮤니케이션 (UC) 디바이스 (예: 일반 전화기)의 기능을 유지 하려면 배포 된 인증서를 주의 깊게 테스트 하 여 와일드 카드 인증서를 구현한 후에 장치가 올바르게 작동 하는지 확인 해야 합니다.



</div>

와일드 카드 항목은 모든 역할에 대 한 주체 이름 (일반 이름이 나 CN이 라고도 함)으로 지원 되지 않습니다. SAN에서 와일드 카드 항목을 사용할 때 다음과 같은 서버 역할이 지원 됩니다.

  - <span></span>  
    **역방향 프록시.**    와일드 카드 SAN 항목은 간단한 URL (모임 및 전화 접속) 게시 인증서에 대해 지원 됩니다.

  - <span></span>  
    **역방향 프록시.**    와일드 카드 san 항목은 게시 인증서에 대 한 LyncDiscover에 대 한 SAN 항목에 지원 됩니다.

  - <span></span>  
    **이사.**    와일드 카드 SAN 항목은 간단한 url (모임 및 전화 접속)과 디렉터 웹 구성 요소의 LyncDiscover 및 LyncDiscoverInternal에 대 한 SAN 항목에 대해 지원 됩니다.

  - <span></span>  
    **프런트 엔드 서버 (Standard Edition) 및 프런트 엔드 풀 (Enterprise Edition).** 와일드 카드 SAN 항목은 간단한 Url (모임 및 전화 접속)과 프런트 엔드 웹 구성 요소에 대 한 LyncDiscover 및 LyncDiscoverInternal의 SAN 항목에 대해 지원 됩니다.

  - <span></span>  
    **Exchange UM (통합 메시징)**    독립 실행형 서버로 배포 하는 경우 서버에서 SAN 항목을 사용 하지 않습니다.

  - <span></span>  
    **Microsoft Exchange Server 클라이언트 액세스 서버.**    내부 및 외부 클라이언트에 대해 SAN의 와일드 카드 항목이 지원 됩니다.

  - <span></span>  
    **동일한 서버의 exchange UM (통합 메시징) 및 Microsoft Exchange Server 클라이언트 액세스 서버**    와일드 카드 SAN 항목이 지원 됩니다.

이 항목에서 해결 되지 않는 서버 역할은 다음과 같습니다.

  - 내부 서버 역할 (중재 서버, 보관 및 모니터링 서버, Survivable Branch 기기 또는 Survivable Branch 서버는 포함 하지만 제한 되지 않음)

  - 외부에 지 서버 인터페이스

  - 내부에 지 서버
    
    <div>
    

    > [!NOTE]  
    > 내부에 지 서버 인터페이스의 경우 와일드 카드 항목을 SAN에 할당할 수 있으며 지원 됩니다. 내부에 지 서버의 SAN이 쿼리 되지 않고 와일드 카드 SAN 항목의 값이 제한 됩니다.

    
    </div>

인증서에 와일드 카드를 사용 하는 것을 포함 하 여 인증 구성에 대 한 자세한 내용은 다음 항목을 참조 하세요.

  - [Lync Server 2013의 내부 서버에 대한 인증서 요구 사항](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [Lync Server 2013의 외부 사용자 액세스에 대한 인증서 요구 사항](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [인증서 요약 - Lync Server 2013에서 DNS 및 HLB 부하 분산됨](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [Lync Server 2013의 인증서 요약 - 단일 디렉터](lync-server-2013-certificate-summary-single-director.md)

  - [Lync Server 2013의 인증서 요약 - 조정된 디렉터 풀, 하드웨어 부하 분산 장치](lync-server-2013-certificate-summary-scaled-director-pool-hardware-load-balancer.md)

  - [Lync Server 2013의 인증서 요약 - 역방향 프록시](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [온-프레미스 통합 메시징과 Lync Server 2013의 통합에 대한 지침](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)

와일드 카드 사용을 포함 하 여 Exchange의 인증서를 구성 하는 방법에 대 한 자세한 내용은 Exchange 2013 제품 설명서를 참조 하세요.

</div>

<span> </span>

</div>

</div>

</div>

