---
title: 'Lync Server 2013: 자동 검색을 위한 DNS 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring DNS for Autodiscover
ms:assetid: f07a634c-3cf3-4958-8556-84596319ef54
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945656(v=OCS.15)
ms:contentKeyID: 51541528
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c490cac475f3b9a9c8038636f4ac7f6670f22637
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980115"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-dns-for-autodiscover-in-lync-server-2013"></a>Lync Server 2013에서 자동 검색을 위한 DNS 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-12-12_

Lync 클라이언트에 대 한 자동 검색을 지원 하려면 다음 DNS (Domain Name System) 레코드를 만들어야 합니다.

  - 조직의 네트워크 내에서 연결 하는 Lync 클라이언트를 지 원하는 내부 DNS 레코드

  - 인터넷에서 연결 하는 Lync 클라이언트를 지 원하는 외부 또는 공용 DNS 레코드

각 SIP 도메인에 대 한 내부 DNS 레코드와 외부 DNS 레코드를 만들어야 합니다.

DNS 레코드는 추가 SAN (주체 대체 이름)을 사용 하 여 새 인증서를 만들 수 있는 기능을 기반으로 하는 (호스트) 레코드 또는 CNAME 레코드 중 하나가 될 수 있습니다. Lyncdiscover를 사용 하 여 새 외부 (공개) 인증서를 요청 하 고 배포할 수 없는 경우 \<도메인 이름\> SAN에서는 HTTP/TCP 포트 80 사용에 대 한 절차를 사용 합니다. 다음 절차에서는 내부 및 외부 DNS 레코드를 만드는 방법에 대해 설명 합니다.

<div>

## <a name="to-create-dns-cname-records"></a>DNS CNAME 레코드를 만들려면

1.  아래와 같이 DNS 서버에 로그온 합니다.
    
      - 내부 DNS 레코드를 만들려면 Domain Admins 그룹의 구성원 또는 DnsAdmins 그룹의 구성원으로 네트워크의 DNS 서버에 로그온 합니다.
    
      - 외부 DNS 레코드를 만들려면 공용 DNS 공급자에 연결 합니다.

2.  **시작**을 클릭 하 고 **관리 도구**를 클릭 한 다음 **DNS**를 클릭 하 여 dns 관리 스냅인을 엽니다.

3.  다음 중 하나를 수행 합니다.
    
      - 내부 DNS 레코드의 경우 DNS 서버의 콘솔 트리에서 Active Directory 도메인에 대 한 **정방향 조회 영역** 을 확장 합니다 (예: contoso).
        
        <div>
        

        > [!NOTE]  
        > 이 도메인은 Lync Server 2013&nbsp;디렉터 풀과 프런트 엔드 풀이 설치 된 Active Directory 도메인입니다.

        
        </div>
    
      - 외부 DNS 레코드의 경우 DNS 서버의 콘솔 트리에서 SIP 도메인에 대 한 **정방향 조회 영역** 을 확장 합니다 (예: contoso.com).

4.  아래와 같이 디렉터 풀에 대 한 레코드가 호스트에 있는지 확인 합니다.
    
      - 내부 DNS 레코드의 경우 호스트는 디렉터 풀의 내부 웹 서비스 FQDN (정규화 된 도메인 이름)에 대해 존재 해야 합니다 (예: lyncwebdir01).
    
      - 외부 DNS 레코드의 경우 호스트 a 레코드가 디렉터 풀에 대 한 외부 웹 서비스 FQDN에 대해 존재 해야 합니다 (예: lyncwebextdir.contoso.com).

5.  다음과 같이 프런트 엔드 풀에 대 한 레코드가 호스트에 있는지 확인 합니다.
    
      - 내부 DNS 레코드의 경우 프런트 엔드 풀의 내부 웹 서비스 FQDN에 대 한 호스트 A 레코드가 있어야 합니다 (예: lyncwebpool01).
    
      - 외부 DNS 레코드의 경우 호스트 a 레코드가 프런트 엔드 풀의 외부 웹 서비스 FQDN에 대해 존재 해야 합니다 (예: lyncwebextpool01.contoso.com).

6.  내부 DNS 레코드의 경우 DNS 서버의 콘솔 트리에서 SIP 도메인에 대 한 **정방향 조회 영역** 을 확장 합니다 (예: contoso.com).
    
    <div>
    

    > [!NOTE]  
    > 외부 DNS 레코드를 만드는 경우 3 단계의 SIP 도메인에 대해 <STRONG>정방향 조회 영역이</STRONG> 이미 확장 되어 있습니다.

    
    </div>

7.  SIP 도메인 이름을 마우스 오른쪽 단추로 클릭 한 다음 **새 별칭 (CNAME)** 을 클릭 합니다.

8.  **별칭 이름**에 다음 중 하나를 입력 합니다.
    
      - 내부 DNS 레코드의 경우 내부 자동 검색 서비스 URL에 대 한 호스트 이름으로 lyncdiscoverinternal를 입력 합니다.
    
      - 외부 DNS 레코드의 경우 외부 자동 검색 서비스 URL에 대 한 호스트 이름으로 lyncdiscover를 입력 합니다.

9.  **대상 호스트의 FQDN (정규화 된 도메인 이름)** 에서 다음 중 하나를 수행 합니다.
    
      - 내부 DNS 레코드의 경우 디렉터 풀에 대 한 내부 웹 서비스 FQDN (예: lyncwebdir01)을 입력 하거나 찾아본 다음 **확인**을 클릭 합니다.
    
      - 외부 DNS 레코드의 경우, 사용자의 디렉터 풀 (예: lyncwebextdir.contoso.com)에 대 한 외부 웹 서비스 FQDN을 입력 하거나 찾아본 다음 **확인**을 클릭 합니다.
    
    <div>
    

    > [!NOTE]  
    > 디렉터를 사용 하지 않는 경우 프런트 엔드 풀의 내부 및 외부 웹 서비스 FQDN을 사용 하 고, 단일 서버의 경우 프런트 엔드 서버 또는 Standard Edition 서버에 대 한 FQDN을 사용 합니다.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server 2013 환경에서 지 원하는 각 SIP 도메인의 정방향 조회 영역에서 새 자동 검색 CNAME 레코드를 만들어야 합니다.

    
    </div>

</div>

<div>

## <a name="to-create-dns-a-records"></a>DNS A 레코드를 만들려면

1.  아래와 같이 DNS 서버에 로그온 합니다.
    
      - 내부 DNS 레코드를 만들려면 Domain Admins 그룹의 구성원 또는 DnsAdmins 그룹의 구성원으로 네트워크의 DNS 서버에 로그온 합니다.
    
      - 외부 DNS 레코드를 만들려면 공용 DNS 공급자나 외부 DNS 서버에 연결 합니다.

2.  **시작**을 클릭 하 고 **관리 도구**를 클릭 한 다음 **DNS**를 클릭 하 여 dns 관리 스냅인을 엽니다.

3.  다음 중 하나를 수행 합니다.
    
      - 내부 DNS 레코드의 경우 DNS 서버의 콘솔 트리에서 Active Directory 도메인에 대 한 **정방향 조회 영역** 을 확장 합니다 (예: contoso).
        
        <div>
        

        > [!NOTE]  
        > 이 도메인은 Lync Server 2013&nbsp;디렉터 풀과 프런트 엔드 풀이 설치 된 Active Directory 도메인입니다.

        
        </div>
    
      - 외부 DNS 레코드의 경우 DNS 서버의 콘솔 트리에서 SIP 도메인에 대 한 **정방향 조회 영역** 을 확장 합니다 (예: contoso.com).

4.  다음과 같이 디렉터 풀에 대 한 호스트 A (IPv6, AAAA) 레코드가 있는지 확인 합니다.
    
      - 내부 DNS 레코드의 경우 디렉터 풀에 대 한 내부 웹 서비스 FQDN (예: lyncwebdir01)에 대 한 호스트 A (IPv6, AAAA) 레코드가 있어야 합니다.
    
      - 외부 DNS 레코드의 경우, 디렉터 풀 (예: lyncwebextdir.contoso.com)에 대 한 외부 웹 서비스 FQDN에 대해 호스트 A (IPv6, AAAA) 레코드가 있어야 합니다.

5.  프런트 엔드 풀에 대 한 호스트 A (IPv6, AAAA) 레코드가 있는지 확인 합니다.
    
      - 내부 DNS 레코드의 경우 프런트 엔드 풀의 내부 웹 서비스 FQDN (예: lyncwebpool01)에 대 한 호스트 A (IPv6, AAAA) 레코드가 있어야 합니다.
    
      - 외부 DNS 레코드의 경우 프런트 엔드 풀의 외부 웹 서비스 FQDN (예: lyncwebextpool01.contoso.com)에 대 한 호스트 A (IPv6, AAAA) 레코드가 있어야 합니다.

6.  내부 DNS 레코드의 경우 DNS 서버의 콘솔 트리에서 SIP 도메인에 대 한 **정방향 조회 영역** 을 확장 합니다 (예: contoso.com).
    
    <div>
    

    > [!NOTE]  
    > 외부 DNS 레코드를 만드는 경우 3 단계의 SIP 도메인에 대해 <STRONG>정방향 조회 영역이</STRONG> 이미 확장 되어 있습니다.

    
    </div>

7.  SIP 도메인 이름을 마우스 오른쪽 단추로 클릭 한 다음 **새 호스트 (A 또는 AAAA)** 를 클릭 합니다.

8.  **이름**에 다음과 같이 호스트 이름을 입력 합니다.
    
      - 내부 DNS 레코드의 경우 내부 자동 검색 서비스 URL에 대 한 호스트 이름으로 lyncdiscoverinternal를 입력 합니다.
    
      - 외부 DNS 레코드의 경우 외부 자동 검색 서비스 URL에 대 한 호스트 이름으로 lyncdiscover를 입력 합니다.
    
    <div>
    

    > [!NOTE]  
    > 도메인 이름은 레코드가 정의 된 영역에서 가정 되며, 따라서 A 레코드의 일부로 입력할 필요가 없습니다.

    
    </div>

9.  **Ip 주소**에 다음과 같이 ip 주소를 입력 합니다.
    
      - 내부 DNS 레코드에 대해 디렉터의 내부 웹 서비스 IP 주소를 입력 하거나, 부하 분산 장치를 사용 하는 경우 디렉터 부하 분산 장치의 VIP (가상 IP)를 입력 합니다.
        
        <div>
        

        > [!NOTE]  
        > 디렉터를 사용 하지 않는 경우 프런트 엔드 서버 또는 Standard Edition 서버의 IP 주소를 입력 하거나 부하 분산 장치를 사용 하는 경우 프런트 엔드 풀 부하 분산 장치의 VIP를 입력 합니다.

        
        </div>
    
      - 외부 DNS 레코드의 경우 역방향 프록시의 외부 또는 공용 IP 주소를 입력 합니다.

10. **호스트 추가**를 클릭 한 다음 **확인**을 클릭 합니다.

11. 추가 레코드를 만들려면 8 ~ 10 단계를 반복 합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server 2013 환경에서 지 원하는 각 SIP 도메인의 정방향 조회 영역에서 새 lyncdiscover 및 lyncdiscoverinternal 레코드를 만들어야 합니다.

    
    </div>

12. (IPv6, AAAA) 레코드 만들기를 마쳤으면 **완료**를 클릭 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

