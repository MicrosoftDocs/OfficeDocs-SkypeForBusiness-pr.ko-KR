---
title: 'Lync Server 2013: 자동 검색 서비스에 대 한 DNS 레코드 만들기'
description: 'Lync Server 2013: 자동 검색 서비스에 대 한 DNS 레코드를 만듭니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating DNS records for the Autodiscover Service
ms:assetid: 3756ffe4-c6b1-492d-850e-42a832e06567
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690010(v=OCS.15)
ms:contentKeyID: 48183823
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6903e6b07001289db8b65e8cc962e8d8db4b248b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563104"
---
# <a name="creating-dns-records-for-the-autodiscover-service-in-lync-server-2013"></a>Lync Server 2013의 자동 검색 서비스에 대 한 DNS 레코드 만들기

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-06-20_

Lync Mobile 사용자는 자동 검색을 사용 하도록 설정 하 고 일부는 DNS (Domain Name System) 레코드를 만드는 과정을 수행 해야 합니다. 필요에 따라 다음이 필요 합니다.

  - 조직의 네트워크 내에서 연결 하는 모바일 사용자를 지원 하기 위한 내부 DNS 레코드입니다.

  - 인터넷에서 연결 하는 모바일 사용자를 지원 하기 위한 외부 또는 공용 DNS 레코드

두 가지 이유 각 SIP 도메인에 대해 내부 DNS 레코드 및 외부 DNS 레코드를 모두 만들어야 합니다.

만드는 DNS 레코드는 (호스트) 레코드나 CNAME 레코드 중 하나가 될 수 있습니다. 이를 위해 아래에서 이러한 내부 및 외부 DNS 레코드를 만드는 방법을 살펴보겠습니다. 모바일 사용자의 DNS 요구 사항에 대 한 추가 정보를 확인 해야 하는 경우 [Lync Server 2013에서 모바일 기능에 대 한 기술적 요구 사항을](lync-server-2013-technical-requirements-for-mobility.md)확인할 수 있습니다.

<div>

## <a name="creating-an-internal-dns-cname-record"></a>내부 DNS CNAME 레코드 만들기

1.  내부 DNS 레코드를 만들려면 Domain Admins 그룹의 구성원 이거나 DnsAdmins 그룹의 구성원 인 도메인 계정을 사용 하 여 네트워크의 DNS 서버에 로그온 해야 합니다.

2.  **시작**, **관리 도구**를 차례로 클릭한 다음 **DNS**를 클릭하여 DNS 관리 스냅인을 엽니다.

3.  DNS 서버의 콘솔 트리에서 Lync Server 2013 디렉터 풀 및 프런트 엔드 풀이 설치 된 Active Directory 도메인의 **정방향 조회 영역** 을 확장 합니다. (예: contoso. 로컬)

4.  확인 및 내부 DNS 레코드에 대 한 디렉터 풀에 대 한 호스트 A (AAAA for i p a p) 레코드가 있는 경우 디렉터 풀의 내부 웹 서비스 FQDN (정규화 된 도메인 이름)에 대 한 호스트 A 레코드가 있어야 합니다 (예:: lyncwebdir01.contoso.local). 여기에 없는 경우 디렉터 풀을 사용 하지 않고 프런트 엔드 풀 또는 단일 서버 FQDN (설치 인 경우)에 FQDN을 사용 해야 할 수 있습니다.

5.  이 점에 유의 하 고, 내부 DNS 레코드에 대 한 프런트 엔드 풀에 대해 호스트 a (AAAA for IPv6) 레코드가 있는지 확인 한 후 프런트 엔드 풀의 내부 웹 서비스 FQDN (예:: lyncwebpool01.contoso.local)에 대해 호스트 A (또는 AAAA) 레코드가 있어야 합니다. 그렇지 않은 경우에는 프런트 엔드 서버 또는 Standard Edition Server에 대 한 FQDN을 기록해 야 합니다.

6.  호스트 A (또는 AAAA) 레코드가 있는지 확인 한 다음 DNS 서버의 콘솔 트리에서 SIP 도메인 (예: contoso.com)에 대 한 **정방향 조회 영역** 을 확장 합니다.

7.  SIP 도메인 이름을 마우스 오른쪽 단추로 클릭한 다음 **새 별칭(CNAME)** 을 클릭합니다.

8.  **별칭 이름**에 내부 자동 검색 서비스 URL의 호스트 이름으로 lyncdiscoverinternal를 입력 합니다.

9.  **대상 호스트의 FQDN (정규화 된 도메인 이름)** 에서 디렉터 풀에 대 한 내부 웹 서비스 FQDN (예:: lyncwebdir01.contoso.local)을 입력 하거나 찾아본 다음 **확인**을 클릭 합니다.

10. Lync Server 2013 환경에서 지 원하는 각 SIP 도메인의 정방향 조회 영역에서 새 자동 검색 CNAME 레코드를 만들어야 합니다.

</div>

<div>

## <a name="creating-an-external-dns-cname-record"></a>외부 DNS CNAME 레코드 만들기

1.  외부 DNS CNAME 레코드를 만들려면 공용 DNS 공급자에 연결 하 고 단계를 수행 해야 합니다. 외부 DNS를 관리 하는 방법에는 여러 가지가 있을 수 있으므로 DNS 공급자 환경에서 어떤 위치를 정확히 설명할 수는 없지만, 이러한 단계를 도움이 되길 바랍니다.

2.  해당 환경에서 DNS 레코드를 만들 수 있는 계정을 사용 하 여 외부 DNS 공급자에 로그인 합니다.

3.  이 환경에 대 한 SIP 도메인이 이미 만들어져 있어야 합니다. 이 SIP 도메인에 대 한 **정방향 조회 영역** 을 확장 하거나 사용 중인 외부 DNS 인터페이스에 따라이를 선택 합니다.

4.  디렉터 풀 (예: lyncwebexdir01.contoso.com)에 대 한 호스트 A (AAAA for IPv6) 레코드가 이미 표시 되어 있는지 확인 해야 합니다. 그렇지 않은 경우에는 디렉터 풀을 사용 하지 않는 것일 수 있습니다. 이 경우 프런트 엔드 풀의 FQDN을 사용 하거나, Front-End 서버 또는 Standard Edition server에 대 한 단일 서버에 대해이 작업을 수행 해야 합니다.

5.  프런트 엔드 풀의 외부 웹 서비스 FQDN (정규화 된 도메인 이름) (예: lyncwebextpool01.contoso.com) 또는 프런트 엔드 풀이 없는 경우 단일 서버 FQDN에 대 한 FQDN에 대해 호스트 A (AAAA for IPv6) 레코드가 있는지도 확인 해야 합니다. 이전 단계에서 설명한 것 처럼 디렉터 풀이 없는 경우 아래와 같은 사항이 필요 합니다.

6.  이제 외부 DNS 공급자에 적합 한 형식으로 **새 별칭 (CNAME)** 을 만드는 옵션을 선택 합니다 (DNS 공급자의 형식에 따라 메뉴 옵션이 나 링크 일 수 있음).

7.  내부 DNS와 마찬가지로 **별칭 이름** 텍스트 상자의 형태가 필요한 경우 외부 자동 검색 서비스 URL의 호스트 이름으로 lyncdiscover를 입력 해야 합니다.

8.  또한 **대상 호스트의 fqdn (정규화 된 도메인 이름)** 텍스트 상자에는 디렉터 풀에 대 한 외부 웹 서비스 FQDN (예: lyncwebexdir01.contoso.com)을 입력 하 고 확인을 클릭 하거나 외부 DNS에서이 항목 만들기를 허용 하는 모든 작업을 수행 하는 것이 좋습니다. 위의 4 단계에 나와 있는 것 처럼, 디렉터 풀이 없는 경우에는 프런트 엔드 풀 FQDN 또는 설정한 단일 서버 FQDN (해당 하는 경우)을 사용 해야 합니다.

9.  Lync 2013 환경에서 지원 되는 각 SIP 도메인의 정방향 조회 영역에 새 자동 검색 CNAME 레코드를 설정 해야 합니다.

</div>

<div>

## <a name="creating-an-internal-dns-a-record"></a>내부 DNS A 레코드 만들기

1.  내부 DNS 레코드를 만들려면 Domain Admins 그룹의 구성원 이거나 DnsAdmins 그룹의 구성원 인 도메인 계정을 사용 하 여 네트워크의 DNS 서버에 로그온 합니다.

2.  **시작**, **관리 도구**를 차례로 클릭한 다음 **DNS**를 클릭하여 DNS 관리 스냅인을 엽니다.

3.  내부 DNS 레코드의 경우 DNS 서버의 콘솔 트리에서 Lync Server 2013 디렉터 풀 및 프런트 엔드 풀이 설치 되어 있는 Active Directory 도메인 (예: contoso)에 대해 **정방향 조회 영역** 을 확장 합니다.

4.  확인 및 내부 DNS 레코드에 대 한 디렉터 풀에 대 한 호스트 A (AAAA for i p a p) 레코드가 있는 경우 디렉터 풀의 내부 웹 서비스 FQDN (정규화 된 도메인 이름)에 대 한 호스트 A 레코드가 있어야 합니다 (예:: lyncwebdir01.contoso.local). 여기에 없는 경우 디렉터 풀을 사용 하지 않고 프런트 엔드 풀 또는 단일 서버 IP 주소 (설치 인 경우)에 대해 IP 주소를 사용 해야 할 수 있습니다.

5.  이 점에 유의 하 고, 내부 DNS 레코드에 대 한 프런트 엔드 풀에 대해 호스트 a (AAAA for IPv6) 레코드가 있는지 확인 한 후 프런트 엔드 풀의 내부 웹 서비스 FQDN (예:: lyncwebpool01.contoso.local)에 대해 호스트 A (또는 AAAA) 레코드가 있어야 합니다. 그렇지 않으면 프런트 엔드 서버 또는 Standard Edition 서버에 대 한 IP 주소를 기록해 야 합니다.

6.  호스트 A (또는 AAAA) 레코드가 있는지 확인 한 다음 DNS 서버의 콘솔 트리에서 SIP 도메인 (예: contoso.com)에 대 한 **정방향 조회 영역** 을 확장 합니다.

7.  SIP 도메인 이름을 마우스 오른쪽 단추로 클릭한 다음 **새 호스트(A 또는 AAAA)** 를 클릭합니다.

8.  **이름**에 내부 자동 검색 서비스 URL의 호스트 이름으로 lyncdiscoverinternal를 입력 합니다.

9.  **IP 주소**에 디렉터의 내부 웹 서비스 IP 주소를 입력 하거나, 부하 분산 장치를 사용 하는 경우 디렉터 부하 분산 장치의 VIP (가상 IP)를 입력 합니다. 위의 4 단계에서 설명한 것 처럼 디렉터를 사용 하지 않는 경우에는 프런트 엔드 서버 또는 Standard Edition 서버의 IP 주소를 입력 하거나, 부하 분산 장치를 사용 하는 경우 프런트 엔드 풀 부하 분산 장치의 VIP를 입력 해야 할 수 있습니다.

10. **호스트 추가**를 클릭한 다음 **확인**을 클릭합니다.

11. 추가 A 또는 AAAA 레코드를 만들려면 8 ~ 10 단계를 반복 하 여 Lync Server 2013 환경에서 지원 되는 각 SIP 도메인의 정방향 조회 영역에서 새 자동 검색 A 또는 AAAA 레코드를 만들어야 한다는 것을 염두에 두어야 합니다.

12. A(IPv6의 경우 AAAA) 레코드를 모두 만든 후에 **완료**를 클릭합니다.

</div>

<div>

## <a name="creating-an-external-dns-a-record"></a>외부 DNS A 레코드 만들기

1.  외부 DNS 레코드를 만들려면 공용 DNS 공급자에 연결 하 고 다음 단계를 수행 합니다. 외부 DNS를 관리 하는 방법에는 여러 가지가 있을 수 있으므로 DNS 공급자 환경에서 어떤 위치를 정확히 설명할 수는 없지만, 이러한 단계를 도움이 되길 바랍니다.

2.  해당 환경에서 DNS 레코드를 만들 수 있는 계정으로 로그인 해야 합니다.

3.  외부 DNS 레코드의 경우 DNS 서버의 콘솔 트리에서 SIP 도메인(예: contoso.com)의 **정방향 조회 영역**을 확장합니다. 외부 DNS 레코드의 경우 DNS 서버의 콘솔 트리에서 SIP 도메인(예: contoso.com)의 **정방향 조회 영역**을 확장합니다.

4.  디렉터 풀 (예: lyncwebexdir01.contoso.com)에 대 한 호스트 A (AAAA for IPv6) 레코드가 이미 표시 되어 있는지와 IP 주소가 있는지 확인 해야 합니다. 그렇지 않은 경우에는 디렉터 풀을 사용 하지 않는 것일 수 있습니다. 이 경우 프런트 엔드 풀의 IP 주소를 사용 하거나, Front-End 서버 또는 Standard Edition server에 대 한 단일 서버에 대해이 작업을 수행 해야 합니다. 서버가 부하 분산 장치 또는 역방향 프록시를 사용 하는 중일 수도 있습니다. 아래 단계를 수행 하는 경우에도 IP 주소를 기록해 둡니다.

5.  프런트 엔드 풀의 외부 웹 서비스 FQDN (정규화 된 도메인 이름) (예: lyncwebextpool01.contoso.com) 또는 프런트 엔드 풀이 없는 경우 단일 서버 Lync 설치의 IP 주소에 대해 호스트 A (AAAA for IPv6) 레코드가 있는지도 확인 해야 합니다. 이전 단계에서 설명한 것 처럼 디렉터 풀이 없는 경우 아래와 같은 사항이 필요 합니다.

6.  이제 외부 DNS 공급자에 적합 한 형식으로 **새 호스트 a 또는 AAAA** 를 만드는 옵션 (DNS 공급자의 형식에 따라 메뉴 옵션 또는 링크 일 수 있음)을 선택 합니다.

7.  **이름을**입력 하 고 외부 자동 검색 서비스 URL의 호스트 이름으로 lyncdiscover를 입력 합니다.

8.  또한 **Ip 주소** 텍스트 상자가 있어야 하며, 여기에는 디렉터 풀 (예: lyncwebexdir01.contoso.com)에 대 한 ip를 입력 하거나 풀의 부하 분산 장치 (또는 같은 작업을 수행 하는 역방향 프록시 ip)를 입력할 수 있습니다 .를 클릭 하 고 확인 또는 외부 DNS를 사용 하 여이 항목 만들기를 수락 합니다. 위의 4 단계에 나와 있는 것 처럼, 디렉터 풀이 없는 경우에는 설정 했던 프런트 엔드 풀 IP 주소나 단일 서버 IP 주소를 적절 하 게 사용 해야 합니다.

9.  Lync 2013 환경에서 지원 되는 각 SIP 도메인의 정방향 조회 영역에 새 자동 검색 A 또는 AAAA 레코드를 설정 해야 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

