---
title: 'Lync Server 2013: 부하 분산을 위한 DNS 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS for load balancing
ms:assetid: 1b2e8414-8676-4872-8ecf-ea07196f74de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398251(v=OCS.15)
ms:contentKeyID: 48183540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d8b2059048823c1a8f063d0d7832759ec64e6341
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204514"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-dns-for-load-balancing-in-lync-server-2013"></a>Lync Server 2013에서 부하 분산을 위한 DNS 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-01_

이 절차를 성공적으로 완료하려면 서버 또는 도메인에 최소한 Domain Admins 그룹의 구성원 또는 DnsAdmins 그룹의 구성원으로 로그온해야 합니다.

DNS (Domain Name System) 부하 분산은 SIP 트래픽 및 미디어 트래픽 같은 Lync Server 2013에 고유한 네트워크 트래픽의 균형을 조정 합니다. DNS 부하 분산은 프런트 엔드 풀, 에지 풀, 디렉터 풀 및 독립 실행형 중재 풀에 대해 지원됩니다. DNS 부하 분산을 사용 하도록 구성 된 풀에는 DNS 부하 분산에 사용 되는 일반 풀 FQDN (예: pool1.contoso.com)이 정의 되어 있어야 하며 풀에 있는 서버의 실제 Ip로 확인 됩니다. 및 풀의 웹 서비스 (예: web1.contoso.net)에 대 한 또 다른 FQDN은 풀의 가상 IP 주소로 확인 됩니다. DNS 부하 분산에 대 한 자세한 내용은 계획 설명서에서 [Lync Server 2013의 dns 부하 분산](lync-server-2013-dns-load-balancing.md) 을 참조 하십시오.

<div>


> [!NOTE]  
> 클라이언트에서 서버로의 HTTPS 트래픽에는 하드웨어 부하 분산을 계속 수행해야 합니다.



</div>

DNS 부하 분산을 사용하려면 다음을 수행해야 합니다.

1.  내부 웹 서비스 풀 FQDN을 재정의 합니다.
    
    <div>
    

    > [!WARNING]  
    > 내부 웹 서비스를 자체 정의 된 FQDN으로 다시 정의 하려는 경우 각 FQDN은 다른 프런트 엔드 풀, 디렉터 또는 디렉터 풀에서 고유 해야 합니다.

    
    </div>

2.  풀 FQDN이 풀에 있는 모든 서버의 IP 주소로 확인되도록 DNS A 호스트 레코드를 만듭니다.

3.  IP 주소 임의화를 사용하도록 설정하거나, Windows Server DNS의 경우 라운드 로빈을 사용하도록 설정합니다.
    
    <div>
    

    > [!NOTE]  
    > 라운드 로빈은 기본적으로 사용하도록 설정해야 합니다.

    
    </div>

<div>

## <a name="to-override-internal-web-services-fqdn"></a>내부 웹 서비스 FQDN을 재정의하려면

1.  토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.

2.  콘솔 트리에서 Enterprise Edition 프런트 엔드 풀 노드를 확장합니다.

3.  풀을 마우스 오른쪽 단추로 클릭하고 **속성 편집**을 클릭한 후에 **웹 서비스**를 클릭합니다.

4.  **내부 웹 서비스** 아래에서 **FQDN 다시 정의** 확인란을 선택합니다.

5.  풀에 있는 서버의 실제 IP 주소로 확인되는 풀 FQDN을 입력합니다.

6.  **외부 웹 서비스**아래에 풀의 가상 IP 주소로 확인되는 외부 풀 FQDN을 입력하고 **확인**을 클릭합니다.

7.  콘솔 트리에서 **Lync Server 2013**을 클릭 한 다음 **작업** 창에서 **토폴로지 게시**를 클릭 합니다.

</div>

<div>

## <a name="to-create-dns-host-a-records-for-all-internal-pool-servers"></a>모든 내부 풀 서버에 대해 DNS 호스트(A) 레코드를 만들려면

1.  **시작**을 클릭하고 **모든 프로그램**과 **관리 도구**를 차례로 클릭한 다음 **DNS**를 클릭합니다.

2.  **DNS 관리자**에서 레코드를 관리하는 DNS 서버를 클릭하여 확장합니다.

3.  **정방향 조회 영역**을 클릭하여 확장합니다.

4.  레코드를 추가해야 하는 DNS 도메인을 마우스 오른쪽 단추로 클릭하고 **새 호스트(A 또는 AAAA)** 를 클릭합니다.

5.  **이름** 상자에 호스트 레코드의 이름을 입력 합니다 (도메인 이름은 자동으로 추가 됨).

6.  IP 주소 상자에 개별 프런트 엔드 서버의 IP 주소를 입력하고 **연결된 PTR(포인터) 레코드 만들기** 또는 해당하는 경우 **인증된 사용자는 누구든지 DNS 레코드를 같은 소유자 이름으로 업데이트할 수 있도록 허용**을 클릭합니다.

7.  계속해서 DNS 부하 분산에 참가할 모든 구성원 프런트 엔드 서버에 대해 레코드를 만듭니다.
    
    예를 들어 풀 이름이 pool1.contoso.com이고 프런트 엔드 서버가 세 개 있는 경우에는 다음과 같은 DNS 항목을 만듭니다.
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>FQDN</th>
    <th>유형</th>
    <th>데이터</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Pool1.contoso.com</p></td>
    <td><p>호스트(A)</p></td>
    <td><p>192.168.1.1</p></td>
    </tr>
    <tr class="even">
    <td><p>Pool1.contoso.com</p></td>
    <td><p>호스트(A)</p></td>
    <td><p>192.168.1.2</p></td>
    </tr>
    <tr class="odd">
    <td><p>Pool1.contoso.com</p></td>
    <td><p>호스트(A)</p></td>
    <td><p>192.168.1.3</p></td>
    </tr>
    </tbody>
    </table>
    
    DNS 호스트 (A) 레코드를 만드는 방법에 대 한 자세한 내용은 [CONFIGURE Dns Host records For Lync Server 2013](lync-server-2013-configure-dns-host-records.md)을 참조 하십시오.

</div>

<div>

## <a name="to-enable-round-robin-for-windows-server"></a>Windows Server에 대해 라운드 로빈을 사용하도록 설정하려면

1.  **시작**을 클릭하고 **모든 프로그램**과 **관리 도구**를 차례로 클릭한 다음 **DNS**를 클릭합니다.

2.  **DNS**를 확장하고 구성할 DNS 서버를 마우스 오른쪽 단추로 클릭한 후에 **속성**을 클릭합니다.

3.  **고급** 탭을 클릭하고 **라운드 로빈 사용** 및 **네트워크 마스크 순서 사용**을 선택한 후에 **확인**을 클릭합니다.
    
    ![DNS 라운드 로빈 대화 상자](images/Gg398251.e7bf6125-8d78-4460-8401-0a8e7e21d305(OCS.15).jpg "DNS 라운드 로빈 대화 상자")

<div>


> [!NOTE]  
> 이 기능은 기본적으로 사용하도록 설정해야 합니다.



</div>

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 DNS 부하 분산](lync-server-2013-dns-load-balancing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

