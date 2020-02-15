---
title: 'Lync Server 2013: 모바일 기능에 대 한 기술 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for mobility
ms:assetid: 831be681-4de0-4e42-b04f-8879ca4dcd23
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690030(v=OCS.15)
ms:contentKeyID: 48184679
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb4c1eacf48940822ddb26ac41f238ccdb4452dd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028379"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-mobility-in-lync-server-2013"></a>Lync Server 2013의 모바일 기능에 대 한 기술 요구 사항

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-07-24_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

모바일 사용자는 특수한 계획을 세워야 하는 다양한 모바일 응용 프로그램 시나리오를 경험하게 됩니다. 예를 들어, 다른 사용자가 3G 네트워크를 통해 연결 하는 방식으로 모바일 응용 프로그램을 사용 하기 시작한 다음 회사 Wi-fi 네트워크로 전환한 다음, 건물에서 나가면 다시 3G로 전환할 수 있습니다. 이와 같은 네트워크 전환을 지원하고 일관된 사용자 환경을 보장할 수 있도록 환경을 계획해야 합니다. 이 섹션에서는 모바일 응용 프로그램을 지원 하 고 이동성 리소스를 자동으로 검색 하기 위해 필요한 인프라 요구 사항에 대해 설명 합니다.

<div>


> [!NOTE]  
> 모바일 응용 프로그램 에서도 다른 Lync Server 2013 서비스에 연결할 수 있지만 모든 모바일 응용 프로그램 웹 요청을 동일한 외부 웹 FQDN (정규화 된 도메인 이름)에 전송 해야 하는 요구 사항은 Lync Server 2013 Mobility Service에만 적용 됩니다. 다른 모바일 서비스에는이 구성이 필요 하지 않습니다.



</div>

하드웨어 부하 분산 장치의 쿠키 선호도에 대 한 요구 사항은 크게 줄어들며 Lync Server 2013와 함께 제공 되는 Lync Mobile을 사용 하는 경우 TCP (전송 제어 프로토콜) 선호도를 대체 합니다. 쿠키 선호도는 계속 사용할 수 있지만 웹 서비스에서 더 이상 필요 하지 않습니다.

<div>


> [!IMPORTANT]  
> 모든 모바일 서비스 트래픽은 시작 지점의 위치 (내부 또는 외부)에 관계 없이 역방향 프록시를 통해 진행 됩니다. 단일 역방향 프록시의 팜 또는 역방향 프록시 기능을 제공 하는 장치에 대 한 내부 트래픽이 인터페이스를 통과 하 고 동일한 인터페이스를 즉시 수신 하려고 하면 문제가 발생할 수 있습니다. 이로 인해 TCP 패킷 스푸핑 또는 스푸핑 이라는 보안 규칙 위반이 발생 하는 경우가 많습니다. 모바일이 작동 하려면 <EM>헤어 고정</EM> (패킷이나 패킷을 위한 송신 및 즉시 수신)을 허용 해야 합니다. 이 문제를 해결 하는 한 가지 방법은 방화벽에서 분리 된 역방향 프록시 (보안 목적을 위해 항상 방화벽에서 스푸핑 방지 규칙을 적용 해야 함)를 사용 하는 것입니다. 헤어핀은 방화벽 외부 인터페이스 대신 역방향 프록시의 외부 인터페이스에서 발생할 수 있습니다. 방화벽에서 스푸핑을 감지 하 고 역방향 프록시에서 규칙을 완화 하 여 모바일 기능에 필요한 헤어핀을 허용 합니다.<BR>가능한 경우 DNS (Domain Name System) 호스트 또는 CNAME 레코드를 사용 하 여 헤어핀 동작 (방화벽이 아님)에 대 한 역방향 프록시를 정의 합니다.



</div>

Lync Server 2013는 Lync 2010 모바일 및 Lync 2013 모바일 클라이언트용 모바일 서비스를 지원 합니다. 두 클라이언트 모두 Lync Server 2013 자동 검색 서비스를 사용 하 여 모바일 진입점을 찾았지만 사용 하는 모바일 서비스에 따라 다릅니다. Lync 2010 Mobile은 Lync Server 2010 용 누적 업데이트: 11 월 2011 일에 도입 된 *Mcx*라는 모바일 서비스를 사용 합니다. Lync 2013 모바일 클라이언트는 통합 커뮤니케이션 웹 API 또는 기타 *wa*를 모바일 서비스 공급자로 사용 합니다.

<div>

## <a name="internal-and-external-dns-configuration"></a>내부 및 외부 DNS 구성

모바일 서비스 Mcx (Lync Server 2010:11 월 2011) 및 (Lync Server 용 누적 업데이트에 도입 되었습니다. 2013 2013 년 2 월)에는 동일한 방식으로 DNS를 사용 합니다.

자동 검색을 사용 하는 경우 모바일 장치는 DNS를 사용 하 여 리소스를 찾습니다. DNS 조회 중에는 내부 DNS 레코드 (lyncdiscoverinternal)와 연결 된 FQDN을 먼저 연결 하려고 시도 합니다.\< 내부 도메인 이름\>) 내부 DNS 레코드를 사용 하 여 연결을 설정할 수 없는 경우에는 외부 DNS 레코드 (lyncdiscover)를 사용 하 여 연결\< 을 시도 합니다. microsoft.rtc.management.xds.sipdomain object\>) 네트워크 내부의 모바일 장치가 내부 자동 검색 서비스 URL에 연결 되 고 네트워크 외부의 모바일 장치가 외부 자동 검색 서비스 URL에 연결 됩니다. 외부 자동 검색 요청은 역방향 프록시를 통과 합니다. Lync Server 2013 자동 검색 서비스는 모바일 서비스 (Mcx 및 인천 wa) Url을 포함 하 여 사용자의 홈 풀에 대 한 모든 웹 서비스 Url을 반환 합니다. 그러나 내부 Mobility Service URL과 외부 Mobility Service URL은 모두 외부 웹 서비스 FQDN에 연결됩니다. 따라서 모바일 장치가 네트워크 내부에 있든 외부에 있는지 여부에 관계 없이 장치는 항상 역방향 프록시를 통해 외부 Lync Server 2013 Mobility Service에 연결 됩니다.

<div>


> [!NOTE]  
> 배포는 내부 및 외부에서 사용 하기 위해 여러 개의 고유한 네임 스페이스로 구성 될 수 있다는 점을 이해 하는 것이 중요 합니다. SIP 도메인 이름은 내부 배포 도메인 이름과 다를 수 있습니다. 예를 들어 SIP 도메인은 <STRONG>contoso.com</STRONG>수 있지만 내부 배포가 <STRONG>contoso.net</STRONG>될 수 있습니다. Lync Server에 로그인 하는 사용자는 <STRONG>john@contoso.com</STRONG>와 같은 SIP 도메인 이름을 사용 합니다. 외부 웹 서비스에 주소를 지정 하는 경우 (토폴로지 작성기에서 <STRONG>외부 웹 서비스로</STRONG>정의 됨) 도메인 이름 및 SIP 도메인 이름은 DNS에 정의 된 대로 일치 합니다. 내부 웹 서비스를 처리할 때 (토폴로지 작성기에 <STRONG>내부 웹 서비스로</STRONG>정의 됨) 내부 웹 서비스의 기본 이름은 프런트 엔드 서버, 프런트 엔드 풀, 디렉터 또는 디렉터 풀의 FQDN이 됩니다. 내부 웹 서비스 이름을 재정의 하는 옵션이 있습니다. 내부 웹 서비스에 대 한 내부 도메인 이름을 사용 하 고 (SIP 도메인 이름이 아님) DNS 호스트 A (또는 i p v 6) 레코드를 정의 하 여 재정의 된 이름을 반영 해야 합니다. 예를 들어 기본 내부 웹 서비스 FQDN은 <STRONG>pool01.contoso.net</STRONG>일 수 있습니다. 재정의 된 내부 웹 서비스 FQDN은 <STRONG>webpool.contoso.net</STRONG>일 수 있습니다. 이러한 방식으로 웹 서비스를 정의 하면 서비스의 내부 및 외부 집약성을 사용 하는 사용자의 집약성이 관찰 되는 것을 방지할 수 있습니다.<BR>그러나 웹 서비스가 토폴로지 작성기에 정의 되 고 내부 웹 서비스 이름을 다시 정의할 수 있으므로 (예를 들어 웹 서비스 이름을 확인 하는 인증서 및이를 정의 하는 DNS 레코드를 정의 하는 경우)에는 일관성을 유지할 수 있습니다. 원하는 도메인 이름 (SIP 도메인 이름 포함)을 가진 내부 웹 서비스 궁극적으로 IP 주소에 대 한 이름 확인은 DNS 호스트 레코드 및 일관성 있는 네임 스페이스에 의해 결정 됩니다.<BR>이 항목 및 예제를 위해 내부 도메인 이름을 사용 하 여 토폴로지와 DNS 정의를 보여 줍니다.



</div>

다음 다이어그램에서는 내부 및 외부 DNS 구성을 사용 하는 경우 자동 검색 서비스와 모바일 서비스에 대 한 모바일 응용 프로그램 웹 요청의 흐름을 보여 줍니다.

**자동 검색을 사용 하는 모바일 서비스 흐름**

![cdb96424-96f2-4abf-88d7-1d32d1010ffd](images/Hh690030.cdb96424-96f2-4abf-88d7-1d32d1010ffd(OCS.15).jpg "cdb96424-96f2-4abf-88d7-1d32d1010ffd")

<div>


> [!NOTE]  
> 이 다이어그램은 일반 웹 서비스를 보여 줍니다. Mobility 라는 가상 디렉터리는 Mobility services Mcx 및/또는 WA를 나타냅니다. Lync Server 2013:2 월 2013에 대 한 누적 업데이트를 적용 하지 않은 경우 내부 및 외부 웹 서비스에 정의 된 가상 디렉터리를 정의할 수 있습니다. 가상 디렉터리 자동 검색을 갖게 되 고 가상 디렉터리 Mcx가 있을 수 있습니다.<BR>배포 된 모바일 서비스 기술에 관계 없이 동일한 방식으로 자동 검색 및 서비스 검색이 동일 하 게 작동 합니다.



</div>

회사 네트워크 내부와 외부에서 모두 모바일 사용자를 지원하려면 내부 및 외부 웹 FQDN이 몇 가지 선행 조건을 충족해야 합니다. 또한 구현하도록 선택하는 기능에 따라 다른 요구 사항도 충족해야 할 수 있습니다.

  - 자동 검색을 위한 새 DNS, CNAME 또는 A (호스트, if IPv6, AAAA) 레코드

  - 새 방화벽 규칙 (Wi-fi 네트워크를 통한 푸시 알림을 지원 하려는 경우)

  - 자동 검색을 위한 내부 서버 인증서 및 역방향 프록시 인증서의 주체 대체 이름입니다.

  - 프런트 엔드 서버 하드웨어 부하 분산 장치 구성에서 원본 선호도를 변경 합니다.

모바일 서비스 및 자동 검색 서비스를 지원 하려면 토폴로지가 다음 요구 사항을 충족 해야 합니다.

  - 프런트 엔드 풀 내부 웹 FQDN은 프런트 엔드 풀 외부 웹 FQDN과 고유 해야 합니다.

  - 내부 웹 FQDN은 회사 네트워크 내부에서만 확인되어야 하며 액세스 가능해야 합니다.

  - 외부 웹 FQDN은 인터넷을 통해서만 확인 되 고 액세스할 수 있어야 합니다.

  - 회사 네트워크 내부 사용자의 경우 Mobility Service URL의 주소는 외부 웹 FQDN으로 지정되어야 합니다. 이는 Mobility Service에 대한 요구 사항으로, 이 URL에만 적용됩니다.

  - 회사 네트워크 외부에 있는 사용자의 경우에는 요청이 프런트 엔드 풀 또는 디렉터의 외부 웹 FQDN으로 이동 해야 합니다.

자동 검색을 지원하는 경우 각 SIP 도메인에 대해 다음 DNS 레코드를 만들어야 합니다.

  - 조직 네트워크 내에서 연결 하는 모바일 사용자를 지원 하기 위한 내부 DNS 레코드

  - 인터넷에서 연결 하는 모바일 사용자를 지원 하기 위한 외부 또는 공용 DNS 레코드

내부 자동 검색 URL은 네트워크 외부에서 주소를 지정할 수 없습니다. 외부 자동 검색 URL은 네트워크 내에서 주소를 지정할 수 없습니다. 그러나 외부 URL에 대해이 요구 사항을 충족할 수 없는 경우에는 내부 URL이 항상 먼저 시도 되므로 모바일 클라이언트 기능에 영향을 주지 않을 수 있습니다.

DNS 레코드는 CNAME 레코드 또는 A (호스트, if IPv6, AAAA) 레코드가 될 수 있습니다.

<div>


> [!NOTE]  
> 모바일 장치는 서로 다른 도메인에서 여러 SSL(Secure Sockets Layer) 인증서를 지원할 수 없습니다. 따라서 HTTPS를 통해서는 다른 도메인으로의 CNAME 리디렉션이 지원되지 않습니다. 예를 들어 director.contoso.net 주소로 리디렉션되는 lyncdiscover.contoso.com의 DNS CNAME 레코드는 HTTPS에서 지원되지 않습니다. 이러한 토폴로지에서는 HTTP를 통해 CNAME 리디렉션이 확인되도록 모바일 장치 클라이언트가 첫 번째 요청에 대해 HTTP를 사용해야 합니다. 후속 요청에서는 HTTPS를 사용합니다. 이 시나리오를 지원하려면 포트 80(HTTP)에 대한 웹 게시 규칙을 사용하여 역방향 프록시를 구성해야 합니다. 자세한 내용은 <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Lync Server 2013에서 모바일 기능에 대 한 역방향 프록시 구성</A>의 "포트 80에 대 한 웹 게시 규칙을 만들려면"을 참조 하십시오.<BR>동일한 도메인으로의 CNAME 리디렉션은 HTTPS를 통해 지원됩니다. 이 경우 대상 도메인의 인증서가 원래 도메인을 포함 합니다.



</div>

시나리오에 필요한 DNS 레코드에 대 한 자세한 내용은 [Lync Server 2013에서 dns 요약-자동 검색](lync-server-2013-dns-summary-autodiscover.md)을 참조 하세요.

</div>

<div>

## <a name="port-and-firewall-requirements"></a>포트 및 방화벽 요구 사항

푸시 알림을 지원하며 Apple 모바일 장치에서 Wi-Fi 네트워크를 통해 푸시 알림을 받도록 하려면 엔터프라이즈 Wi-Fi 네트워크에서 포트 5223도 열어야 합니다. 포트 5223은 APNS(Apple 푸시 알림 서비스)에서 사용되는 아웃바운드 TCP 포트입니다. 모바일 장치가 연결을 시작 합니다. 자세한 내용은를 참조 [http://support.apple.com/kb/TS1629](http://support.apple.com/kb/ts1629) 하세요.

<div>


> [!WARNING]  
> Lync 2013 모바일 클라이언트를 사용 하는 Apple 장치에는 푸시 알림이 필요 하지 않습니다.



</div>

사용자가 SBA (Sba (survivable Branch 기기)에 있는 경우에는 다음 포트가 필요 합니다.

  - UcwaSipExternalListeningPort에는 포트 5088이 필요 합니다.

  - UcwaSipPrimaryListeningPort에는 포트 5089이 필요 합니다.

자동 검색을 위한 포트 및 프로토콜 요구 사항에 대 한 자세한 내용 및 지침은 [포트 요약-자동 검색에서 Lync Server 2013](lync-server-2013-port-summary-autodiscover.md)를 참조 하세요.

</div>

<div>

## <a name="certificate-requirements"></a>인증서 요구 사항

Lync 모바일 클라이언트에 대해 자동 검색을 지원하는 경우에는 모바일 클라이언트로부터의 보안 연결을 지원하기 위해 인증서의 주체 대체 이름 목록을 수정해야 합니다. 이 섹션에서 설명 하는 각 프런트 엔드 서버와 자동 검색 서비스를 실행 하는 디렉터에 대 한 주체 대체 이름 항목을 추가 하 여 새 인증서를 요청 하 고 할당 해야 합니다. 이 경우 역방향 프록시용 인증서에서도 주체 대체 이름 목록을 수정하는 것이 좋습니다. 조직의 모든 SIP 도메인에 대해 주체 대체 이름 항목을 추가해야 합니다.

내부 인증 기관을 통해 인증서를 다시 발급하는 과정은 일반적으로는 간단하지만, 역방향 프록시에서 사용되는 공용 인증서에 여러 주체 대체 이름 항목을 추가하려면 비용이 많이 들 수 있습니다. SIP 도메인이 여러 개인 경우 주체 대체 이름 추가 비용이 매우 크므로, HTTPS를 사용하는 포트 443(기본 구성)이 아닌 HTTP를 사용하는 포트 80을 통해 초기 자동 검색 서비스 요청을 수행하도록 역방향 프록시를 구성할 수 있습니다. 그러면 요청이 디렉터 또는 프런트 엔드 풀의 포트 8080로 리디렉션됩니다. 포트 80에서 초기 자동 검색 서비스 요청을 게시할 때는 요청에서 HTTPS가 아닌 HTTP를 사용하므로 역방향 프록시용 인증서를 변경할 필요가 없습니다. 이 방법이 지원 되지만 권장 되지 않습니다.

</div>

<div>

## <a name="internet-information-services-iis-requirements"></a>IIS(인터넷 정보 서비스) 요구 사항

모바일 기능에 IIS 7.5, IIS 8.0 또는 IIS 8.5을 사용 하는 것이 좋습니다. 모바일 서비스 설치 관리자는 성능을 개선 하기 위해 ASP.NET에서 플래그를 설정 합니다. IIS 7.5은 windows Server 2008 r 2에 기본적으로 설치 되 고, IIS 8.0은 Windows Server 2012에 설치 되며, IIS 8.5은 Windows Server 2012 r 2에 설치 됩니다. 모바일 서비스 설치 관리자가 자동으로 ASP.NET 설정을 변경 합니다.

</div>

<div>

## <a name="hardware-load-balancer-requirements"></a>하드웨어 부하 분산 장치 요구 사항

프런트 엔드 풀을 지 원하는 하드웨어 부하 분산 장치에 대해 웹 서비스 트래픽용 외부 웹 서비스 Vip (가상 Ip)를 원본에 대해 구성 해야 합니다. 원본 선호도는 단일 클라이언트 로부터의 여러 연결이 세션 상태를 유지 하기 위해 하나의 서버로 전송 되도록 하는 데 도움이 됩니다. 선호도 요구 사항에 대 한 자세한 내용은 [Lync Server 2013의 부하 분산 요구 사항](lync-server-2013-load-balancing-requirements.md)를 참조 하세요.

내부 Wi-fi 네트워크를 통해서만 Lync 모바일 클라이언트를 지원 하려는 경우에는 외부 웹 서비스 Vip에 대해 설명 된 대로 원본에 대 한 내부 웹 서비스 VIP를 구성 해야 합니다. 이러한 상황에서는 하드웨어 부하 분산 장치에서\_내부 웹 서비스 vip에 대해 원본 주소 선호도를 사용 해야 합니다. 자세한 내용은 [Lync Server 2013의 부하 분산 요구 사항](lync-server-2013-load-balancing-requirements.md)를 참조 하세요.

</div>

<div>

## <a name="reverse-proxy-requirements"></a>역방향 프록시 요구 사항

Lync 모바일 클라이언트에 대 한 자동 검색을 지 원하는 경우 현재 게시 규칙을 다음과 같이 업데이트 해야 합니다.

  - 역방향 프록시 인증서에서 주체 대체 이름 목록을 업데이트 하 고 초기 자동 검색 서비스 요청에 HTTPS를 사용 하기로 결정 한 경우에는 lyncdiscover에 대 한 웹 게시 규칙을 업데이트 해야 합니다. \<microsoft.rtc.management.xds.sipdomain object\> 일반적으로 프런트 엔드 풀의 외부 웹 서비스 URL에 대 한 게시 규칙과 함께 사용 됩니다.

  - 역방향 프록시 인증서에서 주체 대체 이름 목록을 업데이트 하지 않아도 되도록 초기 자동 검색 서비스 요청에 대해 HTTP를 사용 하려는 경우에는 포트 HTTP/TCP 80에 대 한 새 웹 게시 규칙 (아직 없는 경우)을 만들어야 합니다. HTTP/TCP 80에 대 한 규칙이 이미 있는 경우에는 lyncdiscover를 포함 하도록 해당 규칙을 업데이트할 수 있습니다. \<microsoft.rtc.management.xds.sipdomain object\> 항목

</div>

</div>

<span> </span>

</div>

</div>

</div>

