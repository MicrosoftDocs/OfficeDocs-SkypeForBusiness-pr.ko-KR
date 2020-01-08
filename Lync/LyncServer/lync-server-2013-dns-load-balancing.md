---
title: 'Lync Server 2013: DNS 부하 분산'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS load balancing
ms:assetid: 7ed0ed20-33ad-4253-926d-21d392590ae7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398634(v=OCS.15)
ms:contentKeyID: 48184625
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4248815c2e896c6c4ce36d22fd6544c298527766
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977503"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-load-balancing-in-lync-server-2013"></a>Lync Server 2013의 DNS 부하 분산

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-01-15_

Lync Server는 네트워크의 부하 분산에 대 한 관리 오버 헤드를 크게 줄일 수 있는 소프트웨어 솔루션인 DNS 부하 분산을 사용 하도록 설정 합니다. DNS 로드 균형 조정은 SIP 서버와 유일 하 게 고유한 네트워크 트래픽 (예: SIP 트래픽 및 미디어 트래픽)의 균형을 유지 합니다.

DNS 부하 분산을 배포 하는 경우 하드웨어 부하 분산 장치에 대 한 조직의 관리 오버 헤드가 최소화 됩니다. 또한 SIP 트래픽에 대 한 부하 분산 장치를 잘못 구성 하는 것과 관련 된 문제에 대 한 복잡 한 문제 해결이 제거 됩니다. 서버 연결을 방지 하 여 서버를 오프 라인 상태로 만들 수도 있습니다. DNS 로드 균형 조정 기능을 사용 하면 하드웨어 로드 균형 조정기 문제가 기본 통화 라우팅과 같은 SIP 트래픽 요소에 영향을 주지 않습니다.

DNS 부하 분산을 사용 하는 경우 모든 유형의 트래픽에 대해 하드웨어 부하 분산 장치를 사용 하는 것 보다 저렴 한 하드웨어 부하 분산 장치를 구입할 수도 있습니다. Lync Server를 사용 하 여 상호 운용성 정규화 테스트를 통과 한 부하 분산 장치를 사용 해야 합니다. 부하 분산 장치 상호 운용성 테스트에 대 한 자세한 내용은의 "Lync Server 2010 부하 분산 [http://go.microsoft.com/fwlink/p/?linkId=202452](http://go.microsoft.com/fwlink/p/?linkid=202452)장치 파트너"를 참조 하세요.

DNS 부하 분산은 프런트 엔드 풀, Edge 서버 풀, 디렉터 풀 및 독립 실행형 중재 서버 풀에 대해 지원 됩니다.

<div>

## <a name="dns-load-balancing-on-front-end-pools-and-director-pools"></a>프런트 엔드 풀 및 디렉터 풀의 DNS 부하 분산

프런트 엔드 풀 및 디렉터 풀의 SIP 트래픽에 대 한 DNS 부하 분산을 사용할 수 있습니다. DNS 부하 분산을 배포 하는 경우에도 이러한 풀에 대해 하드웨어 부하 분산 장치를 사용 해야 하지만 클라이언트 간 HTTPS 트래픽에만 사용할 수 있습니다. 하드웨어 로드 균형 조정기는 포트 443 및 80을 통해 클라이언트의 HTTPS 트래픽에 사용 됩니다.

이러한 풀에 대 한 하드웨어 부하 분산 장치가 여전히 필요 하지만, 설정 및 관리는 주로 하드웨어 로드 균형 조정기의 관리자가 익숙한 HTTPS 트래픽에 대 한 것입니다.

<div>

## <a name="dns-load-balancing-and-supporting-older-clients-and-servers"></a>DNS 로드 균형 조정 및 이전 클라이언트 및 서버 지원

DNS 부하 분산은 Lync Server 2013 또는 Lync Server 2010를 실행 하는 서버와 Lync 2013 및 Lync 2010 클라이언트에 대해서만 자동 장애 조치를 지원 합니다. 이전 버전의 클라이언트와 Office Communications Server는 여전히 DNS 부하 분산을 실행 하는 풀에 연결할 수 있지만 DNS 부하 분산이이를 참조 하는 첫 번째 서버에 연결을 할 수 없는 경우에는 풀의 다른 서버로 장애 조치할 수 없습니다. .

또한 Exchange UM을 사용 하는 경우에는 최소한 Exchange 2010 SP1을 사용 하 여 Lync Server DNS 부하 분산에 대 한 지원을 받아야 합니다. 이전 버전의 Exchange를 사용 하는 경우 사용자는 다음 Exchange UM 시나리오에 대 한 장애 조치 기능을 사용할 수 없습니다.

  - 휴대폰에서 기업 음성 사서함 재생

  - Exchange UM 자동 전화 교환에서 통화 전송

다른 모든 Exchange UM 시나리오는 제대로 작동 합니다.

</div>

<div>

## <a name="deploying-dns-load-balancing-on-front-end-pools-and-director-pools"></a>프런트 엔드 풀 및 디렉터 풀에 DNS 부하 분산 배포

프런트 엔드 풀 및 디렉터 풀에 DNS 부하 분산을 배포 하려면 Fqdn 및 DNS 레코드를 사용 하 여 몇 가지 추가 단계를 수행 해야 합니다.

  - DNS 부하 분산을 사용 하는 풀에는 DNS 로드 균형 조정 (예: pool01.contoso.com)에서 사용 되는 일반 풀 FQDN과 풀에 있는 서버의 실제 Ip 및 풀의 웹 서비스에 대 한 또 다른 FQDN (다음과 같은 경우)이 포함 되어야 합니다. web01.contoso.com ()로 풀의 가상 IP 주소를 확인 합니다.
    
    토폴로지 작성기에서 풀에 대 한 DNS 부하 분산을 배포 하려는 경우 해당 풀의 웹 서비스에 대 한이 추가 FQDN을 만들려면 **내부 웹 서비스 풀 Fqdn 재정의** 확인란을 선택 하 고 **이 풀에 대 한 웹 서비스 url 지정** 페이지에서 fqdn을 입력 해야 합니다.

  - DNS 부하 분산에 사용 되는 FQDN을 지원 하려면 DNS를 프로 비전 하 여 풀의 모든 서버 (예: 192.168.1.1, 192.168.1.2 등)의 IP 주소에 대 한 풀 FQDN (pool01.contoso.com)을 확인 해야 합니다. 현재 배포 된 서버의 IP 주소만 포함 해야 합니다.
    
    <div>
    

    > [!WARNING]  
    > 프런트 엔드 풀 또는 프런트 엔드 서버를 두 개 이상 사용 하는 경우에는 외부 웹 서비스 FQDN이 고유 해야 합니다. 예를 들어 프런트 엔드 서버의 외부 웹 서비스 FQDN을 <STRONG>pool01.contoso.com</STRONG>로 정의 하는 경우 다른 프런트 엔드 풀 또는 프런트 엔드 서버에 대해 <STRONG>pool01.contoso.com</STRONG> 를 사용할 수 없습니다. 디렉터를 배포 하는 경우 모든 디렉터 또는 디렉터 풀에 대해 정의 된 외부 웹 서비스 FQDN은 모든 프론트 엔드 풀 또는 프런트 엔드 서버 뿐만 아니라 다른 모든 디렉터 또는 디렉터 풀에서 고유 해야 합니다. 내부 웹 서비스를 자체 정의 FQDN으로 재정의 하기로 결정 한 경우 각 FQDN은 다른 프런트 엔드 풀, 디렉터 또는 디렉터 풀에서 고유 해야 합니다.

    
    </div>

</div>

</div>

<div>

## <a name="dns-load-balancing-on-edge-server-pools"></a>Edge 서버 풀의 DNS 부하 분산

Edge 서버 풀에 DNS 부하 분산을 배포할 수 있습니다. 이렇게 하는 경우 몇 가지 사항을 고려해 야 합니다.

Edge 서버에서 DNS 부하 분산을 사용 하면 다음과 같은 경우 장애 조치 (failover) 기능이 손실 됩니다.

  - Lync Server 2010 이전에 릴리스된 Office Communications Server 버전을 실행 하는 조직이 있는 페더레이션

  - Google 대화와 같은 XMPP 기반 공급자 및 서버 외에도 사용자가 공용 인스턴트\!메시징 (IM) 서비스를 사용 하 여 인스턴트 메시지를 교환 합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P>Google 대화가 현재만 지원 되는 XMPP 파트너입니다.</P>
    > <LI>
    > <P>2012 년 9 월 1 일부 터, Microsoft Lync 공용 IM 연결 사용자 구독 라이선스 ("PIC USL")는 신규 또는 갱신 계약에 대해 더 이상 구매할 수 없습니다. 활성 라이선스가 있는 고객은 계속 Yahoo!에 페더레이션 할 수 있습니다. 서비스 종료 날짜가 될 때까지 메신저를 종료 합니다. AOL 및 Yahoo!에 대 한 6 월 2014의 기간 종료 날짜 님이 발표 되었습니다. 자세한 내용은 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013에서 공개 인스턴트 메신저 연결 지원을</A>참조 하세요.</P></LI></UL>

    
    </div>

이러한 시나리오는 풀의 모든 Edge 서버가 작동 중이 고 실행 되지만 Edge 서버를 사용할 수 없는 경우에는 다른 Edge 서버로 라우팅 하는 대신이 시나리오에 대해 보내는 모든 요청이 실패 합니다.

Exchange UM을 사용 하는 경우에는 최소 Exchange 2013를 사용 하 여 Edge에서 Lync Server DNS 부하 분산을 지원 해야 합니다. 이전 버전의 Exchange를 사용 하는 경우 원격 사용자에 게 이러한 Exchange UM 시나리오에 대 한 장애 조치 기능이 없습니다.

  - 휴대폰에서 기업 음성 사서함 재생

  - Exchange UM 자동 전화 교환에서 통화 전송

다른 모든 Exchange UM 시나리오는 제대로 작동 합니다.

내부 에지 인터페이스와 외부 에지 인터페이스는 같은 유형의 부하 분산을 사용해야 합니다. 즉, 한 에지 인터페이스에서는 DNS 부하 분산을 사용하고 다른 에지 인터페이스에서는 하드웨어 부하 분산을 사용할 수는 없습니다.

<div>

## <a name="deploying-dns-load-balancing-on-edge-server-pools"></a>Edge 서버 풀에 DNS 부하 분산 배포

Edge 서버 풀의 외부 인터페이스에 DNS 부하 분산을 배포 하려면 다음 DNS 항목이 필요 합니다.

  - 액세스에 지 서비스의 경우 풀의 각 서버에 대해 하나의 항목이 필요 합니다. 각 항목은 액세스 경계 서비스의 FQDN (예: sip.contoso.com)을 풀의 Edge 서버 중 하나에 있는 액세스에 지 서비스의 IP 주소로 확인 해야 합니다.

  - 웹 회의에 지 서비스의 경우 풀의 각 서버에 대해 하나의 항목이 필요 합니다. 각 항목은 웹 회의 경계 서비스의 FQDN (예: webconf.contoso.com)을 풀의 Edge 서버 중 하나에서 웹 회의에 지 서비스의 IP 주소로 확인 해야 합니다.

  - 오디오/비디오에 지 서비스의 경우 풀의 각 서버에 대해 하나의 항목이 필요 합니다. 각 항목은 오디오/비디오에 지 서비스의 FQDN (예: av.contoso.com)을 풀의 Edge 서버 중 하나에서 A/V Edge 서비스의 IP 주소로 확인 해야 합니다.

Edge 서버 풀의 내부 인터페이스에 DNS 부하 분산을 배포 하려면 Edge 서버 풀의 내부 FQDN을 풀에 있는 각 서버의 IP 주소로 확인 하는 하나의 DNS 레코드를 추가 해야 합니다.

</div>

</div>

<div>

## <a name="using-dns-load-balancing-on-mediation-server-pools"></a>중재 서버 풀에서 DNS 부하 분산 사용

독립 실행형 중재 서버 풀에서 DNS 부하 분산을 사용할 수 있습니다. 모든 SIP 및 미디어 트래픽은 DNS 부하 분산에 의해 조정 됩니다.

중재 서버 풀에 DNS 부하 분산을 배포 하려면 DNS를 프로 비전 하 여 풀의 모든 서버 (예: 192.168.1.1, 192.168.1.2 등)의 IP 주소에 대해 mediationpool1.contoso.com를 확인 해야 합니다.

</div>

<div>

## <a name="blocking-traffic-to-a-server-with-dns-load-balancing"></a>DNS 부하 분산을 사용 하 여 서버로 트래픽 차단

DNS 부하 분산을 사용 하는 경우 특정 컴퓨터로의 트래픽을 차단 해야 하는 경우에는 풀 FQDN에서 IP 주소 항목을 제거 하는 것 만으로는 충분 하지 않습니다. 컴퓨터 에서도 DNS 항목을 제거 해야 합니다.

서버 간 트래픽에 대 한 자세한 내용은 Lync Server 2013에서 토폴로지 인식 부하 분산을 사용 합니다. 서버는 중앙 관리 저장소에서 게시 된 토폴로지를 읽어 토폴로지에 있는 서버의 Fqdn을 확보 하 고 서버 간에 트래픽을 자동으로 배포 합니다. 서버에서 서버 간 트래픽을 받지 못하도록 차단 하려면 토폴로지에서 서버를 제거 해야 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

