---
title: 'Lync Server 2013: DNS 부하 분산'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS load balancing
ms:assetid: 7ed0ed20-33ad-4253-926d-21d392590ae7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398634(v=OCS.15)
ms:contentKeyID: 48184625
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d08c56e8b88f13a965f7ab24c8f497e01f10400
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135104"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-load-balancing-in-lync-server-2013"></a>Lync Server 2013의 DNS 부하 분산

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-01-15_

Lync Server에서는 네트워크의 부하 분산에 대 한 관리 오버 헤드를 크게 줄일 수 있는 소프트웨어 솔루션인 DNS 부하 분산을 사용 하도록 설정 합니다. DNS 부하 분산은 SIP 트래픽, 미디어 트래픽 등 Lync Server에 고유한 네트워크 트래픽의 균형을 조정 합니다.

DNS 부하 분산을 배포 하는 경우 하드웨어 부하 분산 장치에 대 한 조직의 관리 오버 헤드가 최소화 됩니다. 또한 SIP 트래픽에 대한 부하 분산 장치의 잘못된 구성과 관련된 복잡한 문제를 해결할 필요가 없게 됩니다. 또한 서버를 오프라인으로 설정할 수 있도록 서버 연결을 방지할 수도 있습니다. 또한 DNS 부하 분산은 하드웨어 부하 분산 장치 문제가 기본 통화 라우팅과 같은 SIP 트래픽 요소에 영향을 주지 않도록 합니다.

DNS 부하 분산을 사용하는 경우에는 모든 트래픽 유형에 대해 하드웨어 부하 분산 장치를 사용하는 경우에 비해 저렴한 가격에 하드웨어 부하 분산 장치를 구입할 수도 있습니다. Lync Server를 사용 하 여 상호 운용성 검증 테스트를 통과 한 부하 분산 장치를 사용 해야 합니다. 부하 분산 장치 상호 운용성 테스트에 대 한 자세한 내용은의 "Lync Server 2010 부하 분산 [https://go.microsoft.com/fwlink/p/?linkId=202452](https://go.microsoft.com/fwlink/p/?linkid=202452)장치 파트너"를 참조 하십시오.

DNS 부하 분산은 프런트 엔드 풀, 에지 서버 풀, 디렉터 풀 및 독립 실행형 중재 서버 풀에서 지원됩니다.

<div>

## <a name="dns-load-balancing-on-front-end-pools-and-director-pools"></a>프런트 엔드 풀과 디렉터 풀의 DNS 부하 분산

프런트 엔드 풀과 디렉터 풀의 SIP 트래픽에 DNS 부하 분산을 사용할 수 있습니다. DNS 부하 분산을 배포한 경우에는 이러한 풀에 클라이언트-서버 HTTPS 트래픽 전용 하드웨어 부하 분산 장치를 사용해야 합니다. 하드웨어 부하 분산 장치는 포트 443 및 80을 통해 클라이언트에서 전송되는 HTTPS 트래픽에 사용됩니다.

이러한 풀에 여전히 하드웨어 부하 분산 장치가 필요하지만 설치 및 관리는 주로 HTTP 트래픽에 대한 것이며, 이는 하드웨어 부하 분산 장치 관리자에게 익숙한 일입니다.

<div>

## <a name="dns-load-balancing-and-supporting-older-clients-and-servers"></a>DNS 부하 분산과 이전 클라이언트 및 서버 지원

DNS 부하 분산은 Lync Server 2013 또는 Lync Server 2010를 실행 하는 서버와 Lync 2013 및 Lync 2010 클라이언트에 대해서만 자동 장애 조치 (failover)를 지원 합니다. 이전 버전의 클라이언트 및 Office Communications Server에서는 여전히 DNS 부하 분산을 실행 하는 풀에 연결할 수 있지만 DNS 부하 분산이 참조 하는 첫 번째 서버에 연결을 설정할 수 없는 경우에는 풀의 다른 서버로 장애 조치 (failover) 할 수 없습니다. .

또한 Exchange UM을 사용 하는 경우에는 최소한의 Exchange 2010 SP1을 사용 하 여 Lync Server DNS 부하 분산을 지원 해야 합니다. 이전 버전의 Exchange를 사용 하는 경우 사용자에 게 이러한 Exchange UM 시나리오에 대 한 장애 조치 (failover) 기능이 제공 되지 않습니다.

  - 전화기에서 Enterprise Voice 음성 메일 재생

  - Exchange UM 자동 전화 교환의 통화 전송

다른 모든 Exchange UM 시나리오는 제대로 적용됩니다.

</div>

<div>

## <a name="deploying-dns-load-balancing-on-front-end-pools-and-director-pools"></a>프런트 엔드 풀과 디렉터 풀에 DNS 부하 분산 배포

프런트 엔드 풀과 디렉터 풀에 DNS 부하 분산을 배포하려면 FQDN 및 DNS 레코드와 관련된 몇 가지 추가 단계를 수행해야 합니다.

  - DNS 부하 분산을 사용하는 풀에는 두 개의 FQDN이 있어야 합니다. 하나는 DNS 부하 분산에 사용되고 풀에 있는 서버의 실제 IP를 확인하는 일반적인 풀 FQDN(예: pool01.contoso.com)이고, 또 하나는 풀의 가상 IP 주소를 확인하는 풀의 웹 서비스에 대한 FQDN(예: web01.contoso.com)입니다.
    
    토폴로지 작성기에서 풀에 대 한 DNS 부하 분산을 배포 하려는 경우 해당 풀의 웹 서비스에 대해이 추가 FQDN을 만들려면 **내부 웹 서비스 풀 Fqdn 재정의** 확인란을 선택 하 고 **이 풀에 대 한 웹 서비스 url 지정** 페이지에서 FQDN을 입력 해야 합니다.

  - DNS 부하 분산에 사용되는 FQDN을 지원하려면 풀 FQDN(예: pool01.contoso.com)을 풀에 있는 모든 서버의 IP 주소(예: 192.168.1.1, 192.168.1.2 등)로 확인하는 DNS를 프로비전해야 합니다. 이때 현재 배포된 서버의 IP 주소만 포함해야 합니다.
    
    <div>
    

    > [!WARNING]  
    > 프런트 엔드 풀 또는 프런트 엔드 서버가 두 개 이상 있는 경우에는 외부 웹 서비스 FQDN이 고유 해야 합니다. 예를 들어 프런트 엔드 서버의 외부 웹 서비스 FQDN을 <STRONG>pool01.contoso.com</STRONG>로 정의 하는 경우 다른 프런트 엔드 풀 또는 프런트 엔드 서버에 대해 <STRONG>pool01.contoso.com</STRONG> 를 사용할 수 없습니다. 디렉터를 배포 하는 경우에는 모든 디렉터 또는 디렉터 풀에 대해 정의 된 외부 웹 서비스 FQDN은 모든 프런트 엔드 풀 또는 프런트 엔드 서버 뿐만 아니라 다른 디렉터 또는 디렉터 풀에서 고유 해야 합니다. 내부 웹 서비스를 자체 정의 된 FQDN으로 다시 정의 하려는 경우 각 FQDN은 다른 프런트 엔드 풀, 디렉터 또는 디렉터 풀에서 고유 해야 합니다.

    
    </div>

</div>

</div>

<div>

## <a name="dns-load-balancing-on-edge-server-pools"></a>에지 서버 풀의 DNS 부하 분산

에지 서버 풀에 DNS 부하 분산을 배포할 수 있습니다. 이 경우 몇 가지 사항을 고려해야 합니다.

에지 서버에서 DNS 부하 분산을 사용하면 다음과 같은 시나리오에서 장애 조치 기능이 손실됩니다.

  - Lync Server 2010 이전 버전의 Office Communications Server를 실행 하는 조직과의 페더레이션

  - 공용 IM (인스턴트 메시징) 서비스\!와 기타 사용자와의 인스턴트 메시지 교환 (예: Google 대화 같은 xmpp 기반 공급자 및 서버 포함)
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P>Google 토크는 현재 지원 되는 XMPP 파트너 뿐입니다.</P>
    > <LI>
    > <P>2012 년 9 월 1 일, Microsoft Lync 공용 IM 연결 사용자 구독 라이선스 ("PIC USL")를 신규 또는 갱신 동의를 위해 더 이상 구매할 수 없습니다. 활성 라이선스를 사용 하는 고객은 Yahoo!에 계속 페더레이션 할 수 있습니다. 서비스 종료 날짜까지 메신저 AOL 및 Yahoo!의 6 월 2014 일 종료 날짜 이 발표 되었습니다. 자세한 내용은 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013에서 공용 인스턴트 메신저 연결에 대 한 지원을</A>참조 하세요.</P></LI></UL>

    
    </div>

이러한 시나리오는 풀의 모든 에지 서버가 작동되고 실행 중인 한 적용되지만 하나의 에지 서버를 사용할 수 없는 경우 이 서버로 전송되는 요청은 다른 에지 서버로 라우팅되지 않고 실패합니다.

Exchange UM을 사용 하는 경우에는 최소 Exchange 2013을 사용 하 여 Edge에서 Lync Server DNS 부하 분산을 지원 해야 합니다. 이전 버전의 Exchange를 사용 하는 경우 원격 사용자에 게 다음과 같은 Exchange UM 시나리오에 대 한 장애 조치 (failover) 기능이 없습니다.

  - 전화기에서 Enterprise Voice 음성 메일 재생

  - Exchange UM 자동 전화 교환의 통화 전송

다른 모든 Exchange UM 시나리오는 제대로 적용됩니다.

내부 에지 인터페이스와 외부 에지 인터페이스는 같은 유형의 부하 분산을 사용해야 합니다. 즉, 한 에지 인터페이스에서는 DNS 부하 분산을 사용하고 다른 에지 인터페이스에서는 하드웨어 부하 분산을 사용할 수는 없습니다.

<div>

## <a name="deploying-dns-load-balancing-on-edge-server-pools"></a>에지 서버 풀에 DNS 부하 분산 배포

에지 서버 풀의 외부 인터페이스에 DNS 부하 분산을 배포하려면 다음 DNS 항목이 필요합니다.

  - 액세스에 지 서비스의 경우 풀의 각 서버에 대해 하나의 항목이 필요 합니다. 각 항목은 액세스에 지 서비스의 FQDN (예: sip.contoso.com)을 풀에 있는에 지 서버 중 하나에 있는 액세스에 지 서비스의 IP 주소로 확인 해야 합니다.

  - 웹 회의에 지 서비스의 경우 풀의 각 서버에 대해 항목이 하나씩 필요 합니다. 각 항목은 웹 회의에 지 서비스의 FQDN (예: webconf.contoso.com)을 풀에 있는에 지 서버 중 하나에 있는 웹 회의에 지 서비스의 IP 주소로 확인 해야 합니다.

  - 오디오/비디오에 지 서비스의 경우 풀의 각 서버에 대해 하나의 항목이 필요 합니다. 각 항목은 오디오/비디오에 지 서비스의 FQDN (예: av.contoso.com)을 풀에 있는에 지 서버 중 하나에 있는 A/V에 지 서비스의 IP 주소로 확인 해야 합니다.

에지 서버 풀의 내부 인터페이스에 DNS 부하 분산을 배포하려면 에지 서버 풀의 내부 FQDN을 풀에 있는 각 서버의 IP 주소로 확인하는 DNS A 레코드를 추가해야 합니다.

</div>

</div>

<div>

## <a name="using-dns-load-balancing-on-mediation-server-pools"></a>중재 서버 풀에서 DNS 부하 분산 사용

독립 실행형 중재 서버 풀에서 DNS 부하 분산을 사용할 수 있습니다. 모든 SIP 및 미디어 트래픽은 DNS 부하 분산에 의해 균형이 조정됩니다.

중재 서버 풀에 DNS 부하 분산을 배포하려면 풀 FQDN(예: mediationpool1.contoso.com)을 풀에 있는 모든 서버의 IP 주소(예: 192.168.1.1, 192.168.1.2 등)로 확인하는 DNS를 프로비전해야 합니다.

</div>

<div>

## <a name="blocking-traffic-to-a-server-with-dns-load-balancing"></a>DNS 부하 분산을 사용 하 여 서버에 대 한 트래픽 차단

DNS 부하 분산을 사용 하는 경우 특정 컴퓨터로의 트래픽을 차단 해야 하는 경우에는 풀 FQDN에서 IP 주소 항목을 제거 하는 것 만으로는 충분 하지 않습니다. 또한 컴퓨터에 대 한 DNS 항목도 제거 해야 합니다.

서버 간 트래픽의 경우 Lync Server 2013에서는 토폴로지를 지 원하는 부하 분산을 사용 합니다. 서버는 중앙 관리 저장소에서 게시 된 토폴로지를 읽어 토폴로지의 서버 Fqdn을 가져오고 서버 간에 트래픽을 자동으로 분산 합니다. 서버에서 서버 간 트래픽을 수신 하지 못하도록 차단 하려면 토폴로지에서 서버를 제거 해야 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

