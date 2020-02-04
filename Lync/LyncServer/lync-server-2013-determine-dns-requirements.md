---
title: 'Lync Server 2013: DNS 요구 사항 확인'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Determine DNS requirements
ms:assetid: 95777017-6282-44c0-a685-f246af0501b4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398758(v=OCS.15)
ms:contentKeyID: 48184839
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd8c1c95c3b8ba3671735447f098eca9173111ba
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762486"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="determine-dns-requirements-for-lync-server-2013"></a>Lync Server 2013에 대한 DNS 요구 사항 확인

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-22_

다음 순서도를 사용 하 여 DNS (Domain Name System) 요구 사항을 확인 합니다. Lync Server 2013의 누적 업데이트에 대 한 변경 사항: 적용 되는 위치에는 2 월 2013이 표시 됩니다.

<div>


> [!IMPORTANT]  
> Microsoft Lync Server 2013는 IPv6 주소 지정 사용을 지원 합니다. IPv6 주소를 사용 하려면 IPv6 DNS에 대 한 지원도 제공 하 고 DNS 호스트 AAAA ("쿼드 A") 레코드를 구성 해야 합니다. IPv4 및 IPv6을 모두 사용 하는 배포에서 IPv4 용 호스트 A 레코드와 IPv6 용 호스트 AAAA를 모두 구성 하 고 유지 관리 하는 것이 좋습니다. 배포가 IPv6으로 완전히 전환 된 경우에도 외부 사용자가 IPv4를 계속 사용 중인 경우에는 IPv4 DNS 호스트 레코드가 계속 필요할 수 있습니다.



</div>

**DNS 요구 사항 확인 순서도**

![175782ac-363e-408a-912f-8991bf152970](images/Gg398758.175782ac-363e-408a-912f-8991bf152970(OCS.15).jpg "175782ac-363e-408a-912f-8991bf152970")

<div>


> [!IMPORTANT]  
> 기본적으로 도메인에 연결 되지 않은 컴퓨터의 컴퓨터 이름은 FQDN (정규화 된 도메인 이름)이 아닌 호스트 이름입니다. 토폴로지 작성기는 호스트 이름이 아닌 Fqdn을 사용 합니다. 따라서 도메인에 가입 되어 있지 않은 Edge 서버로 배포할 컴퓨터의 이름에 DNS 접미사를 구성 해야 합니다. Lync Server, Edge 서버 및 풀의 Fqdn을 할당할 때는 표준 문자 (-Z, a-z, 0 – 9, 하이픈 포함) <STRONG>만 사용</STRONG> 합니다. 유니코드 문자나 밑줄은 사용 하지 마세요. FQDN의 비표준 문자는 외부 DNS 및 공개 Ca (즉 FQDN을 인증서의 SN에 할당 해야 하는 경우)에서 지원 되지 않는 경우가 많습니다. 자세한 내용은 <A href="lync-server-2013-configure-dns-host-records.md">Lync Server 용 DNS 호스트 레코드 구성 2013</A> 을 참조 하세요.



</div>

<div>

## <a name="how-lync-clients-locate-services"></a>Lync 클라이언트가 서비스를 찾는 방법

Microsoft Lync 2010, Lync 2013, Lync Mobile은 클라이언트가 Lync Server 2013에서 서비스를 찾고 액세스 하는 방법과 비슷합니다. 주목할 만한 예외는 다른 서비스 위치 프로세스를 사용 하는 Lync Windows 스토어 앱입니다. 이 섹션에서는 클라이언트가 서비스를 찾는 방법에 대 한 두 가지 시나리오, 먼저 일련의 SRV 및 호스트 레코드를 사용 하는 기존 메서드, 자동 검색 서비스 레코드만을 사용 하 여 초에 대해 설명 합니다. 데스크톱 클라이언트에 대 한 누적 업데이트는 모든 클라이언트에 대 한 Lync Server 2010에서 DNS 위치 프로세스를 변경 하거나, 쿼리를 성공적으로 반환 하거나, 사용 가능 DNS 레코드 목록이 모두 소모 되 고, 최종 오류가 반환 됩니다. 클라이언트.

DNS 조회 중에 Lync Windows 스토어 앱을 **제외한** 모든 클라이언트에 대해 SRV 레코드를 쿼리하여 다음 순서 대로 클라이언트에 반환 합니다.

1.  lyncdiscoverinternal. \<내부\> 웹 서비스의 자동 검색 서비스에 대 한 도메인 A (호스트) 레코드

2.  lyncdiscover. \<외부\> 웹 서비스의 자동 검색 서비스에 대 한 도메인 A (호스트) 레코드

3.  \_sipinternaltls. \_tcp. \<내부\> TLS 연결에 대 한 도메인 SRV (서비스 로케이터) 레코드

4.  \_sipinternal. \_tcp. \<내부\> TCP 연결에 대 한 도메인 SRV (서비스 로케이터) 레코드 (TCP가 허용 되는 경우에만 수행 됨)

5.  \_sip. \_tls. \<외부\> TLS 연결에 대 한 도메인 SRV (서비스 로케이터) 레코드

6.  sipinternal. \<프런트\> 엔드 풀 또는 디렉터에 대 한 도메인 A (호스트) 레코드로, 내부 네트워크 에서만 확인할만 있습니다.

7.  sip. \<내부\> 네트워크의 프런트 엔드 풀 또는 디렉터에 대 한 도메인 A (호스트) 레코드 또는 클라이언트가 외부에 있는 경우 액세스 경계 서비스

8.  sipexternal. \<클라이언트가\> 외부에 있는 경우 액세스에 지 서비스에 대 한 도메인 A (호스트) 레코드

Lync Windows 스토어 앱은 두 개의 레코드를 사용 하기 때문에 프로세스가 완전히 변경 됩니다.

1.  lyncdiscoverinternal. \<내부\> 웹 서비스의 자동 검색 서비스에 대 한 도메인 A (호스트) 레코드

2.  lyncdiscover. \<외부\> 웹 서비스의 자동 검색 서비스에 대 한 도메인 A (호스트) 레코드

다른 레코드 형식에 대 한 대체 기능은 없습니다.

이전 클라이언트와 비교 하 여 최신 클라이언트에 사용 되는 방법 간의 차이점은 자동 검색 서비스가 모든 서비스를 찾는 선호 되는 방법입니다.

연결에 성공 하면 자동 검색 서비스는 모바일 서비스 (IIS의 서비스에 대해 생성 된 가상 디렉터리의 Mcx), Microsoft Lync Web App 및 웹 스케줄러 Url을 포함 하 여 사용자의 홈 풀에 대 한 모든 웹 서비스 Url을 반환 합니다. 그러나 내부 모바일 서비스 URL과 외부 모바일 서비스 URL은 모두 외부 웹 서비스 FQDN과 연결 됩니다. 따라서 모바일 장치가 네트워크 내부 또는 외부에 있는지 여부에 관계 없이 디바이스는 항상 역방향 프록시를 통해 외부의 모바일 서비스에 연결 됩니다.

Lync Server 2013 2013의 누적 업데이트가 설치 된 경우 자동 검색 서비스는 내부/일부 WA, External/ldor와 함께 참조를 반환 합니다. 이러한 항목은 통합 커뮤니케이션 웹 API (웹 구성 요소)를 참조 합니다. 현재는 엔트리 셀만 사용 되며 웹 구성 요소의 URL에 대 한 참조를 제공 합니다. 이 (가) lync 2010 모바일 클라이언트에서 사용 하는 Mcx Mobility Service 대신 Lync 2013 모바일 클라이언트에서 사용 합니다.

<div>


> [!NOTE]  
> SRV 레코드를 만들 때 DNS SRV 레코드를 만드는 동일한 도메인에서 DNS A 및 AAAA (IPv6 주소 사용을 하는 경우) 레코드를 가리켜야 한다는 점에 유의 해야 합니다. 예를 들어 SRV 레코드가 contoso.com 인 경우 A 및 AAAA (IPv6 주소를 사용 하는 경우) 레코드는 fabrikam.com에 있을 수 없습니다.



</div>

<div>


> [!TIP]  
> 기본 구성은 외부 사이트를 통해 모든 모바일 클라이언트 트래픽을 안내할 수 있습니다. 요구 사항에 더 적합 한 경우 내부 URL만 반환 하도록 설정을 수정할 수 있습니다. 이 구성을 사용 하면 사용자가 회사 네트워크 내에 있는 경우에만 모바일 장치에서 Lync 모바일 응용 프로그램을 사용할 수 있습니다. 이 구성을 정의 하려면 <STRONG>Set-CsMcxConfiguration</STRONG> cmdlet을 사용 합니다.



</div>

<div>


> [!NOTE]  
> 모바일 응용 프로그램 에서도 주소록 서비스와 같은 다른 Lync Server 2013 서비스에 연결할 수 있지만 내부 모바일 응용 프로그램 웹 요청은 모바일 서비스에 대 한 외부 웹 FQDN으로 이동 합니다. 주소록 요청과 같은 다른 서비스 요청은이 구성을 요구 하지 않습니다.



</div>

모바일 장치는 서비스의 수동 검색을 지원 합니다. 이 경우 각 사용자는 다음과 같이 프로토콜 및 경로를 포함 하 여 전체 내부 및 외부 자동 검색 서비스 Uri를 사용 하 여 모바일 장치 설정을 구성 해야 합니다.

  - 외부\<액세스를 위한\>Https://extpoolfqdn/Autodiscover/autodiscoverservice.svc/Root

  - 내부\<액세스용 Https://intpoolfqdn\>/AutoDiscover/AutoDiscover.svc/Root

수동 검색 대신 자동 검색을 사용 하는 것이 좋습니다. 그러나 수동 설정은 모바일 장치 연결 문제를 해결 하는 데 유용할 수 있습니다.

</div>

<div>

## <a name="configuring-split-brain-dns-with-lync-server"></a>Lync Server를 사용 하 여 분할 두뇌 DNS 구성

분할 하는 dns는 여러 이름 (예: DNS 분할 또는 분할-수평 DNS)에 의해 알려져 있습니다. 단지 같은 네임 스페이스를 가진 두 개의 DNS 영역이 있지만, 하나의 DNS 영역 서비스 내부 전용 요청과 다른 DNS 영역 서비스 외부만 요청이 있는 DNS 구성을 설명 합니다. 그러나 내부 DNS에 포함 된 많은 DNS SRV 및 레코드는 외부 DNS에 포함 되지 않으며 반대의 경우도 마찬가지입니다. 내부 및 외부 DNS에 동일한 DNS 레코드가 있는 경우 (예: www.contoso.com), 반환 되는 IP 주소는 쿼리가 시작 된 위치 (내부 또는 외부)에 따라 달라 집니다.

<div>


> [!IMPORTANT]  
> 현재, 이동성, 특히 LyncDiscover DNS 레코드에 대 한 분할 두뇌 DNS가 지원 되지 않습니다. LyncDiscover는 외부 DNS 서버에서 정의 해야 하며, 내부 DNS 서버에서 LyncDiscoverInternal를 정의 해야 합니다.



</div>

이러한 항목의 목적에 따라 분할의 두뇌 DNS가 사용 됩니다.

분할 두뇌 DNS를 구성 하는 경우 다음 내부 및 외부 영역에 각 영역에 필요한 DNS 레코드의 종류에 대 한 요약이 포함 됩니다. 자세한 내용은 [Lync Server 2013에서 외부 사용자 액세스에 대 한 시나리오](lync-server-2013-scenarios-for-external-user-access.md)를 참조 하세요.

**내부 DNS:**

  - 권한이 있는 contoso.com 이라는 DNS 영역 포함

  - 내부 contoso.com 영역에는 다음이 포함 됩니다.
    
      - DNS A 및 AAAA (IPv6 주소를 사용 하는 경우) 및 내부 Lync Server 2013 클라이언트 자동 구성에 대 한 SRV 레코드 (선택 사항)
    
      - DNS A 및 AAAA (IPv6 주소를 사용 하는 경우) 또는 Lync Server 2013 웹 서비스의 자동 검색을 위한 CNAME 레코드 (선택 사항)
    
      - DNS A 및 AAAA (IPv6 주소를 사용 하는 경우) 레코드를 프런트 엔드 풀 이름, 디렉터 또는 디렉터 풀 이름 및 회사 네트워크에서 Lync Server 2013을 실행 하는 모든 내부 서버
    
      - 각 Lync Server 2013, Edge 서버의 경계 네트워크에 대 한 Edge 내부 인터페이스에 대 한 DNS A 및 AAAA (IPv6 주소를 사용 하는 경우) 레코드
    
      - 경계 네트워크에서 각 역방향 프록시 서버의 내부 인터페이스에 대 한 DNS A 및 AAAA (IPv6 주소를 사용 하는 경우) 레코드 (리버스 프록시 관리의 경우 선택 사항)
    
      - 주변 네트워크의 모든 Lync Server 2013 Edge 서버 내부 Edge 인터페이스 contoso.com에 대 한 쿼리 확인을 위해 내부 DNS 영역 사용
    
      - 회사 네트워크에서 lync 2013를 실행 하는 Lync Server 2013 및 클라이언트를 실행 하는 모든 서버는 contoso.com에 대 한 쿼리를 확인 하거나 각 Edge 서버에서 HOSTS 파일을 사용 하거나 목록 A 및 AAAA (IPv6 주소를 사용 하는 경우) 레코드에 대 한 내부 DNS 서버를 가리킵니다. 다음 홉 서버, 구체적으로 디렉터 또는 디렉터 VIP, 프론트 End pool VIP 또는 Standard Edition 서버

**외부 DNS:**

  - 권한이 있는 contoso.com 이라는 DNS 영역 포함

  - 외부 contoso.com 영역에는 다음이 포함 됩니다.
    
      - DNS A 및 AAAA (IPv6 주소를 사용 하는 경우) 및 Lync Server 2013 클라이언트 자동 구성에 대 한 SRV 레코드 (선택 사항)
    
      - DNS A 및 AAAA (IPv6 주소를 사용 하는 경우) 또는 모바일에서 사용할 Lync Server 2013 웹 서비스의 자동 검색을 위한 CNAME 레코드
    
      - DNS A 및 AAAA (IPv6 주소를 사용 하는 경우) 및 경계 네트워크의 각 Lync Server 2013, Edge 서버 또는 하드웨어 부하 분산 장치 VIP (가상 IP)의 Edge 외부 인터페이스에 대 한 SRV 레코드
    
      - 경계 네트워크의 역방향 프록시 서버 풀의 외부 인터페이스에 대 한 DNS A 및 AAAA (IPv6 주소를 사용 하는 경우) 레코드

</div>

<div>

## <a name="automatic-configuration-without-split-brain-dns"></a>분할 하는 DNS 없이 자동 구성

분할 하는 DNS를 사용 하는 경우 내부 DNS 영역에 \_sipinternaltls 포함 된 경우 내부적으로 로그인 하는 Lync Server 2013 사용자가 자동 구성을 활용할 수 있습니다. \_사용 중인 각 SIP 도메인에 대 한 tcp SRV 레코드. 그러나 분할 하는 DNS를 사용 하지 않는 경우이 섹션의 뒷부분에 설명 된 해결 방법 중 하나를 구현 하지 않으면 Lync를 실행 하는 클라이언트의 내부 자동 구성이 작동 하지 않습니다. 이는 Lync Server 2013에서 자동 구성에 대해 지정 된 프런트 엔드 풀의 도메인과 일치 시키기 위해 사용자의 SIP URI가 필요 하기 때문입니다. 이전 버전의 Communicator를 사용 하는 경우에도이 문제가 발생 합니다.

예를 들어 두 개의 SIP 도메인을 사용 하는 경우 다음 DNS 서비스 (SRV) 레코드가 필요 합니다.

  - 사용자가 bob@contoso.com로 로그인 하는 경우 사용자의 SIP 도메인 (contoso.com)이 자동 구성 프런트 엔드 풀의 도메인과 일치 하기 때문에 다음 SRV 레코드가 자동 구성에 대해 작동 합니다.
    
     \_sipinternaltls. \_tcp.contoso.com. SRV 0 0 5061 pool01.contoso.com의 86400

  - 사용자가 alice@fabrikam.com로 로그인 하는 경우 다음 DNS SRV 레코드는 두 번째 SIP 도메인의 자동 구성에 사용할 수 있습니다.
    
     \_sipinternaltls. \_tcp.fabrikam.com. SRV 0 0 5061 pool01.fabrikam.com의 86400

비교할 때, 클라이언트의 SIP 도메인 (litwareinc.com)이 풀이 있는 도메인 (fabrikam.com)과 일치 하지 않기 때문에 사용자가 tim@litwareinc.com로 로그인 하는 경우 자동 구성에 대해 다음 DNS SRV 레코드가 작동 하지 않습니다.

 \_sipinternaltls. \_tcp.litwareinc.com. SRV 0 0 5061 pool01.fabrikam.com의 86400

Lync를 실행 하는 클라이언트에 자동 구성이 필요한 경우 다음 옵션 중 하나를 선택 합니다.

  - **그룹 정책 개체**   는 gpo (그룹 정책 개체)를 사용 하 여 올바른 서버 값을 채웁니다.
    
    <div>
    

    > [!NOTE]  
    > 이 옵션은 자동 구성을 사용 하지 않지만 수동 구성 프로세스를 자동화 하므로이 방법을 사용 하는 경우 자동 구성에 연결 된 SRV 레코드가 필요 하지 않습니다.

    
    </div>

  - **일치 하는 내부 영역**   외부 dns 영역 (예: contoso.com)과 일치 하는 내부 dns에 영역을 만들고 자동 구성에 사용 되는 Lync Server 2013 풀에 해당 하는 DNS a 및 AAAA (IPv6 주소를 사용 하는 경우)를 만듭니다. 예를 들어 사용자가 pool01.contoso.net에 있는 경우 Lync에 bob@contoso.com에 로그인 하 고, contoso.com 이라는 내부 DNS 영역을 만들고, DNS A 및 AAAA (IPv6 주소 지정이 사용 되는 경우)를 pool01.contoso.com에 대 한 레코드를 만듭니다.

  - **핀 포인트 내부 영역**   내부 DNS에서 전체 영역을 만드는 경우 자동 구성에 필요한 SRV 레코드에 해당 하는 pin 포인트 (즉, 전용) 영역을 만들고 dnscmd를 사용 하 여 해당 영역을 채울 수 있습니다. DNS 사용자 인터페이스가 pin 포인트 영역 만들기를 지원 하지 않으므로 Dnscmd이 필요 합니다. 예를 들어 SIP 도메인이 contoso.com이 고 두 프런트 엔드 서버를 포함 하는 pool01 라는 프런트 엔드 풀을 사용 하는 경우에는 내부 DNS에 다음과 같은 핀 위치 영역과 레코드가 필요 합니다.
    
        dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
        dnscmd . /zoneadd pool01.contoso.com. /dsprimary
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
    
    환경에 두 번째 SIP 도메인 (예: fabrikam.com)이 포함 되어 있는 경우에는 내부 DNS에 다음과 같은 핀 위치 영역과 레코드가 필요 합니다.
    
        dnscmd . /zoneadd _sipinternaltls._tcp.fabrikam.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.fabrikam.com. @ SRV 0 0 5061 pool01.fabrikam.com.
        dnscmd . /zoneadd pool01.fabrikam.com. /dsprimary
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.91
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>

<div>


> [!NOTE]  
> 프런트 엔드 풀 FQDN은 두 개의 서로 다른 IP 주소를 사용 하 여 두 번 표시 됩니다. DNS 부하 분산을 사용 하지만 하드웨어 부하 분산을 사용 하는 경우에는 프런트 엔드 풀 항목을 하나만 사용할 수 있습니다. 또한 contoso.com 예제와 fabrikam.com 예제 간에 프런트 엔드 풀 FQDN 값이 변경 되지만 IP 주소는 동일 하 게 유지 됩니다. 이는 사용자가 SIP 도메인 중 하나에서 로그인 한 후 자동 구성에 동일한 프런트 엔드 풀을 사용 하기 때문입니다.



</div>

자세한 내용은 DMTF 블로그 문서, "Communicator 자동 구성 및 분할-두뇌 DNS"를 참조 하세요 [http://go.microsoft.com/fwlink/p/?linkId=200707](http://go.microsoft.com/fwlink/p/?linkid=200707).

<div>


> [!NOTE]  
> 각 블로그 및 해당 URL의 콘텐츠는 예 고 없이 변경 될 수 있습니다.



</div>

</div>

<div>

## <a name="configuring-the-domain-name-system-dns-for-disaster-recovery"></a>재해 복구를 위해 DNS (domain name system) 구성

Lync Server 2013 웹 트래픽을 재해 복구 및 장애 조치 사이트로 리디렉션하도록 DNS를 구성 하려면 GeoDNS를 지 원하는 DNS 공급자를 사용 해야 합니다. 장애 복구를 지원 하도록 웹에 대 한 DNS 레코드를 설정 하 여 전체 프런트 엔드 풀 하나가 다운 되는 경우에도 웹 서비스를 사용 하는 기능이 계속 작동 하도록 할 수 있습니다. 이 재해 복구 기능은 자동 검색 (Lyncdiscover URL), 모임 및 전화 접속 간단한 Url을 지원 합니다.

GeoDNS 공급자에서 웹 서비스의 내부 및 외부 해상도에 대 한 추가 DNS 호스트 (A 및 IPv6을 사용 하는 경우 AAAA) 레코드를 정의 하 고 구성 합니다. 다음 세부 정보는 라운드 로빈 DNS를 사용 하 여 공급자가 지 원하는 쌍의 풀, 지리적으로 분산 된 연결 및 Pool1를 기본으로 사용할 수 있도록 구성 하 고 통신 손실 또는 하드웨어 오류 발생 시 Pool2로 장애 조치를 수행 한다고 가정 합니다.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>GeoDNS 레코드 (예)</th>
<th>풀 레코드 (예)</th>
<th>CNAME 레코드 (예)</th>
<th>DNS 설정 (한 옵션 선택)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Meet-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com에 Meet.contoso.com 별칭</p>
<p>Pool2InternalWebFQDN.contoso.com에 Meet.contoso.com 별칭</p></td>
<td><p>풀 간의 라운드 로빈</p>
<p>기본 사용, 보조 if 실패에 연결</p></td>
</tr>
<tr class="even">
<td><p>Meet-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com에 Meet.contoso.com 별칭</p>
<p>Pool2ExternalWebFQDN.contoso.com에 Meet.contoso.com 별칭</p></td>
<td><p>풀 간의 라운드 로빈</p>
<p>기본 사용, 보조 if 실패에 연결</p></td>
</tr>
<tr class="odd">
<td><p>Dialin-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com에 Dialin.contoso.com 별칭</p>
<p>Pool2InternalWebFQDN.contoso.com에 Dialin.contoso.com 별칭</p></td>
<td><p>풀 간의 라운드 로빈</p>
<p>기본 사용, 보조 if 실패에 연결</p></td>
</tr>
<tr class="even">
<td><p>Dialin-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com에 Dialin.contoso.com 별칭</p>
<p>Pool2ExternalWebFQDN.contoso.com에 Dialin.contoso.com 별칭</p></td>
<td><p>풀 간의 라운드 로빈</p>
<p>기본 사용, 보조 if 실패에 연결</p></td>
</tr>
<tr class="odd">
<td><p>Lyncdiscoverint-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com에 Lyncdiscoverinternal.contoso.com 별칭</p>
<p>Pool2InternalWebFQDN.contoso.com에 Lyncdiscoverinternal.contoso.com 별칭</p></td>
<td><p>풀 간의 라운드 로빈</p>
<p>기본 사용, 보조 if 실패에 연결</p></td>
</tr>
<tr class="even">
<td><p>Lyncdiscover-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com에 Lyncdiscover.contoso.com 별칭</p>
<p>Pool2ExternalWebFQDN.contoso.com에 Lyncdiscover.contoso.com 별칭</p></td>
<td><p>풀 간의 라운드 로빈</p>
<p>기본 사용, 보조 if 실패에 연결</p></td>
</tr>
<tr class="odd">
<td><p>Scheduler-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com에 Scheduler.contoso.com 별칭</p>
<p>Pool2InternalWebFQDN.contoso.com에 Scheduler.contoso.com 별칭</p></td>
<td><p>풀 간의 라운드 로빈</p>
<p>기본 사용, 보조 if 실패에 연결</p></td>
</tr>
<tr class="even">
<td><p>Scheduler-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com에 Scheduler.contoso.com 별칭</p>
<p>Pool2ExternalWebFQDN.contoso.com에 Scheduler.contoso.com 별칭</p></td>
<td><p>풀 간의 라운드 로빈</p>
<p>기본 사용, 보조 if 실패에 연결</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-load-balancing"></a>DNS 부하 분산

DNS 부하 분산은 일반적으로 응용 프로그램 수준에서 구현 됩니다. 응용 프로그램 (예: Lync를 실행 하는 클라이언트)은 DNS A 및 AAAA (IPv6 주소 지정을 사용 하는 경우)에서 반환 되는 IP 주소 중 하나에 연결 하 여 풀의 서버에 연결 하려고 시도 합니다. FQDN (정규화 된 도메인 이름)에 대 한 쿼리 기록

예를 들어 pool01.contoso.com 이라는 풀에 프런트 엔드 서버가 세 개 있는 경우 다음이 발생 합니다.

  - Pool01.contoso.com 용 Lync 쿼리 DNS를 실행 하는 클라이언트 쿼리는 세 개의 IP 주소를 반환 하 고 다음과 같이 캐시 합니다 (이 순서는 필요 하지 않음).
    
    pool01.contoso.com 192.168.10.90
    
    pool01.contoso.com 192.168.10.91
    
    pool01.contoso.com 192.168.10.92

  - 클라이언트가 IP 주소 중 하나에 대 한 TCP (전송 제어 프로토콜) 연결을 설정 하려고 시도 합니다. 이 오류가 발생 하면 클라이언트는 캐시에서 다음 IP 주소를 시도 합니다.

  - TCP 연결이 성공 하면 클라이언트는 pool01.contoso.com의 기본 등록 기관에 연결 하도록 TLS를 협상 합니다.

  - 클라이언트가 연결 되지 않고 모든 캐시 된 항목을 시도 하는 경우, 현재 Lync Server 2013을 실행 하는 서버를 사용할 수 없다는 알림을 사용자에 게 알립니다.

<div>


> [!NOTE]  
> DNS 기반 부하 분산은 dns를 사용 하 여 풀의 서버에 해당 하는 IP 주소를 서로 다른 순서로 제공 하 여 로드 균형 조정을 가리키는 DNS 라운드 로빈 (DNS RR)과 다릅니다. 일반적으로 DNS RR은 로드 배포만 가능 하지만 장애 조치를 사용 하도록 설정 하지는 않습니다. 예를 들어 DNS A와 AAAA (IPv6 주소 지정을 사용 하는 경우)에 의해 반환 된 하나의 IP 주소에 대 한 연결에 실패 하면 연결이 실패 합니다. 따라서 dns 라운드 로빈 자체는 DNS 기반 부하 분산 보다 안정성이 적습니다. Dns 부하 분산을 함께 사용 하 여 DNS 라운드 로빈을 사용할 수 있습니다.



</div>

DNS 부하 분산은 다음에 사용 됩니다.

  - 서버 간 SIP의 부하 분산을 Edge 서버로

  - 회의 자동 전화 교환, 응답 그룹, 통화 공원 등 통합 커뮤니케이션 응용 프로그램 서비스 (c) 응용 프로그램 로드 균형 조정

  - 다른 항목에 대 한 새 연결을 응용 프로그램으로 방지 ("드레이닝"이 라고도 함)

  - 클라이언트와 Edge 서버 간의 모든 클라이언트 간 트래픽 부하 분산

DNS 부하 분산은 다음에 사용할 수 없습니다.

  - 디렉터 또는 프런트 엔드 서버에 대 한 클라이언트 대 서버 웹 트래픽

DNS 부하 분산 및 페더레이션 트래픽:

DNS SRV 쿼리에서 여러 DNS 레코드를 반환 하는 경우 액세스에 지 서비스가 항상 가장 낮은 숫자 우선 순위와 가장 높은 숫자 가중치를 사용 하 여 DNS SRV 레코드를 선택 합니다. 인터넷 엔지니어링 작업 강제 문서 "서비스 위치를 지정 하는 DNS RR (DNS SRV)" <http://www.ietf.org/rfc/rfc2782.txt> 은 정의 된 dns srv 레코드가 여러 개 있는 경우 우선 순위를 먼저 사용한 다음 weight를 지정 합니다. 예를 들어 DNS SRV 레코드 A의 가중치가 20이 고 우선 순위가 40이 고 DNS SRV 레코드 B의 가중치가 10이 고 우선 순위가 50입니다. 우선 순위가 40 인 DNS SRV 레코드 A가 선택 됩니다. DNS SRV 레코드 선택에는 다음과 같은 규칙이 적용 됩니다.

  - 우선 순위가 가장 먼저 고려 됩니다. 클라이언트가 DNS SRV 레코드가 정의한 대상 호스트에 연결 하는 데 사용할 수 있는 가장 낮은 우선 순위로 연결을 시도 해야 합니다. 우선 순위가 같은 대상은 weight 필드에 정의 된 순서 대로 시도해 야 합니다.

  - Weight 필드는 우선 순위가 동일한 항목에 대 한 상대적 가중치를 지정 합니다. 가중치가 클수록 선택 되는 확률을 비례적으로 높일 수 있습니다. DNS 관리자는 수행할 서버 선택이 없는 경우 가중치 0을 사용 해야 합니다. 가중치가 0 보다 큰 레코드가 있는 경우 가중치가 0 인 레코드는 선택할 확률이 매우 낮습니다.

우선 순위와 가중치가 같은 DNS SRV 레코드가 여러 개 반환 되는 경우 액세스에 지 서비스가 DNS 서버에서 먼저 받은 SRV 레코드를 선택 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

