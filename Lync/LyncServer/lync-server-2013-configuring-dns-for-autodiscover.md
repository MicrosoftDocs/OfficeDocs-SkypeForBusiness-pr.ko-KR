---
title: 'Lync Server 2013: 자동 검색을 위한 DNS 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring DNS for Autodiscover
ms:assetid: f07a634c-3cf3-4958-8556-84596319ef54
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945656(v=OCS.15)
ms:contentKeyID: 51541528
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ff6e72d13ddfb80369a0a522abc14a1de459536
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202994"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-dns-for-autodiscover-in-lync-server-2013"></a>Lync Server 2013에서 자동 검색을 위한 DNS 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-12-12_

Lync 클라이언트에 대해 자동 검색을 지원 하려면 다음 DNS (Domain Name System) 레코드를 만들어야 합니다.

  - 조직 네트워크 내에서 연결 하는 Lync 클라이언트를 지원 하기 위한 내부 DNS 레코드

  - 인터넷에서 연결 하는 Lync 클라이언트를 지원 하기 위한 외부 또는 공용 DNS 레코드

각 SIP 도메인에 대해 내부 DNS 레코드 및 외부 DNS 레코드를 만들어야 합니다.

DNS 레코드는 추가 SAN (주체 대체 이름)을 사용 하 여 새 인증서를 만드는 기능을 기반으로 하는 (호스트) 레코드나 CNAME 레코드가 될 수 있습니다. Lyncdiscover를 사용 하 여 새 외부 (공개) 인증서를 요청 하 고 배포할 수 없는 경우 \<도메인 이름\> SAN에서는 HTTP/TCP 포트 80을 사용 하는 절차를 사용 합니다. 다음 절차에서는 내부 및 외부 DNS 레코드를 만드는 방법을 설명합니다.

<div>

## <a name="to-create-dns-cname-records"></a>DNS CNAME 레코드를 만들려면

1.  다음과 같이 DNS 서버에 로그온합니다.
    
      - 내부 DNS 레코드를 만들려면 Domain Admins 그룹 또는 DnsAdmins 그룹의 구성원으로 네트워크의 DNS 서버에 로그온합니다.
    
      - 외부 DNS레코드를 만들려면 공용 DNS 공급자에 연결합니다.

2.  **시작**, **관리 도구**를 차례로 클릭한 다음 **DNS**를 클릭하여 DNS 관리 스냅인을 엽니다.

3.  다음 중 하나를 수행합니다.
    
      - 내부 DNS 레코드의 경우 DNS 서버의 콘솔 트리에서 Active Directory 도메인(예: contoso.local)의 **정방향 조회 영역**을 확장합니다.
        
        <div>
        

        > [!NOTE]  
        > 이 도메인은 Lync Server 2013&nbsp;디렉터 풀 및 프런트 엔드 풀이 설치 된 Active Directory 도메인입니다.

        
        </div>
    
      - 외부 DNS 레코드의 경우 DNS 서버의 콘솔 트리에서 SIP 도메인(예: contoso.com)의 **정방향 조회 영역**을 확장합니다.

4.  디렉터 풀에 대 한 호스트 A 레코드가 다음과 같이 존재 하는지 확인 합니다.
    
      - 내부 DNS 레코드의 경우 디렉터 풀에 대 한 내부 웹 서비스 FQDN (정규화 된 도메인 이름)에 대 한 호스트 A 레코드가 있어야 합니다 (예:: lyncwebdir01.contoso.local).
    
      - 외부 DNS 레코드의 경우에는 디렉터 풀에 대 한 외부 웹 서비스 FQDN (예: lyncwebextdir.contoso.com)에 대 한 호스트 A 레코드가 있어야 합니다.

5.  프런트 엔드 풀에 대 한 호스트 A 레코드가 다음과 같이 존재 하는지 확인 합니다.
    
      - 내부 DNS 레코드의 경우 프런트 엔드 풀의 내부 웹 서비스 FQDN (예:: lyncwebpool01.contoso.local)에 대 한 호스트 A 레코드가 있어야 합니다.
    
      - 외부 DNS 레코드의 경우 프런트 엔드 풀에 대 한 외부 웹 서비스 FQDN (예: lyncwebextpool01.contoso.com)에 대해 호스트 A 레코드가 있어야 합니다.

6.  내부 DNS 레코드의 경우 DNS 서버의 콘솔 트리에서 SIP 도메인(예: contoso.com)의 **정방향 조회 영역**을 확장합니다.
    
    <div>
    

    > [!NOTE]  
    > 외부 DNS 레코드를 만드는 경우에는 3단계에서 SIP 도메인에 대해 <STRONG>정방향 조회 영역</STRONG>이 이미 확장된 상태입니다.

    
    </div>

7.  SIP 도메인 이름을 마우스 오른쪽 단추로 클릭한 다음 **새 별칭(CNAME)** 을 클릭합니다.

8.  **별칭 이름**에 다음 중 하나를 입력합니다.
    
      - 내부 DNS 레코드의 경우 내부 자동 검색 서비스 URL의 호스트 이름으로 lyncdiscoverinternal을 입력합니다.
    
      - 외부 DNS 레코드의 경우 외부 자동 검색 서비스 URL의 호스트 이름으로 lyncdiscover를 입력합니다.

9.  **대상 호스트의 FQDN(정규화된 도메인 이름)** 에서 다음 중 하나를 수행합니다.
    
      - 내부 DNS 레코드의 경우 디렉터 풀에 대 한 내부 웹 서비스 FQDN (예:: lyncwebdir01.contoso.local)을 입력 하거나 찾아본 다음 **확인**을 클릭 합니다.
    
      - 외부 DNS 레코드의 경우에는 디렉터 풀에 대 한 외부 웹 서비스 FQDN (예: lyncwebextdir.contoso.com)을 입력 하거나 찾아본 다음 **확인**을 클릭 합니다.
    
    <div>
    

    > [!NOTE]  
    > 디렉터를 사용 하지 않는 경우 프런트 엔드 풀의 내부 및 외부 웹 서비스 FQDN을 사용 하거나 단일 서버에 대해 프런트 엔드 서버 또는 Standard Edition 서버의 FQDN을 사용할 수 있습니다.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server 2013 환경에서 지 원하는 각 SIP 도메인의 정방향 조회 영역에서 새 자동 검색 CNAME 레코드를 만들어야 합니다.

    
    </div>

</div>

<div>

## <a name="to-create-dns-a-records"></a>DNS A 레코드를 만들려면

1.  다음과 같이 DNS 서버에 로그온합니다.
    
      - 내부 DNS 레코드를 만들려면 Domain Admins 그룹 또는 DnsAdmins 그룹의 구성원으로 네트워크의 DNS 서버에 로그온합니다.
    
      - 외부 DNS 레코드를 만들려면 공용 DNS 공급자 또는 외부 DNS 서버에 연결 합니다.

2.  **시작**, **관리 도구**를 차례로 클릭한 다음 **DNS**를 클릭하여 DNS 관리 스냅인을 엽니다.

3.  다음 중 하나를 수행합니다.
    
      - 내부 DNS 레코드의 경우 DNS 서버의 콘솔 트리에서 Active Directory 도메인(예: contoso.local)의 **정방향 조회 영역**을 확장합니다.
        
        <div>
        

        > [!NOTE]  
        > 이 도메인은 Lync Server 2013&nbsp;디렉터 풀 및 프런트 엔드 풀이 설치 된 Active Directory 도메인입니다.

        
        </div>
    
      - 외부 DNS 레코드의 경우 DNS 서버의 콘솔 트리에서 SIP 도메인(예: contoso.com)의 **정방향 조회 영역**을 확장합니다.

4.  디렉터 풀에 대해 호스트 A (i p v 6의 경우 AAAA) 레코드가 있는지 확인 합니다.
    
      - 내부 DNS 레코드의 경우 디렉터 풀에 대 한 내부 웹 서비스 FQDN (예:: lyncwebdir01.contoso.local)에 대해 호스트 A (i p v 6의 경우 AAAA) 레코드가 있어야 합니다.
    
      - 외부 DNS 레코드의 경우에는 디렉터 풀에 대 한 외부 웹 서비스 FQDN (예: lyncwebextdir.contoso.com)에 대해 호스트 A (i p v 6의 경우 AAAA) 레코드가 있어야 합니다.

5.  프런트 엔드 풀에 대해 호스트 A (i p v 6에 AAAA) 레코드가 있는지 확인 합니다.
    
      - 내부 DNS 레코드의 경우 프런트 엔드 풀의 내부 웹 서비스 FQDN (예:: lyncwebpool01.contoso.local)에 대해 호스트 A (i p v 6의 경우 AAAA) 레코드가 있어야 합니다.
    
      - 외부 DNS 레코드의 경우 프런트 엔드 풀의 외부 웹 서비스 FQDN (예: lyncwebextpool01.contoso.com)에 대해 호스트 A (i p v 6의 경우 AAAA) 레코드가 있어야 합니다.

6.  내부 DNS 레코드의 경우 DNS 서버의 콘솔 트리에서 SIP 도메인(예: contoso.com)의 **정방향 조회 영역**을 확장합니다.
    
    <div>
    

    > [!NOTE]  
    > 외부 DNS 레코드를 만드는 경우에는 3단계에서 SIP 도메인에 대해 <STRONG>정방향 조회 영역</STRONG>이 이미 확장된 상태입니다.

    
    </div>

7.  SIP 도메인 이름을 마우스 오른쪽 단추로 클릭한 다음 **새 호스트(A 또는 AAAA)** 를 클릭합니다.

8.  **이름**에 호스트 이름을 다음과 같이 입력합니다.
    
      - 내부 DNS 레코드의 경우 내부 자동 검색 서비스 URL의 호스트 이름으로 lyncdiscoverinternal을 입력합니다.
    
      - 외부 DNS 레코드의 경우 외부 자동 검색 서비스 URL의 호스트 이름으로 lyncdiscover를 입력합니다.
    
    <div>
    

    > [!NOTE]  
    > 도메인 이름은 레코드가 정의된 영역에서 가져온 것으로 가정되므로 A 레코드의 일부로 입력할 필요는 없습니다.

    
    </div>

9.  **IP 주소**에 IP 주소를 다음과 같이 입력합니다.
    
      - 내부 DNS 레코드의 경우 디렉터의 내부 웹 서비스 IP 주소를 입력 하거나, 부하 분산 장치를 사용 하는 경우 디렉터 부하 분산 장치의 VIP (가상 IP)를 입력 합니다.
        
        <div>
        

        > [!NOTE]  
        > 디렉터를 사용 하지 않는 경우에는 프런트 엔드 서버 또는 Standard Edition 서버의 IP 주소를 입력 하거나, 부하 분산 장치를 사용 하는 경우 프런트 엔드 풀 부하 분산 장치의 VIP를 입력 합니다.

        
        </div>
    
      - 외부 DNS 레코드의 경우 역방향 프록시의 외부(공용) IP 주소를 입력합니다.

10. **호스트 추가**를 클릭한 다음 **확인**을 클릭합니다.

11. A 레코드를 추가로 만들려면 8-10단계를 반복합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server 2013 환경에서 지 원하는 각 SIP 도메인의 정방향 조회 영역에 새 llyncdiscoverinternal cdiscover 및 A 레코드를 만들어야 합니다.

    
    </div>

12. A(IPv6의 경우 AAAA) 레코드를 모두 만든 후에 **완료**를 클릭합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

