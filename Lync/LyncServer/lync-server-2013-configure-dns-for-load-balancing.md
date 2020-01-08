---
title: 'Lync Server 2013: 부하 분산을 위한 DNS 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure DNS for load balancing
ms:assetid: 1b2e8414-8676-4872-8ecf-ea07196f74de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398251(v=OCS.15)
ms:contentKeyID: 48183540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e370d3b66e82b02bd5668fc1c9cab4ee41da759
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985181"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-for-load-balancing-in-lync-server-2013"></a>Lync Server 2013에서 부하 분산을 위한 DNS 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-01_

이 절차를 완료 하려면 Domain Admins 그룹의 구성원 또는 DnsAdmins 그룹의 구성원으로 최소한 서버나 도메인에 로그온 해야 합니다.

DNS (Domain Name System) 부하 분산은 SIP 서버 2013에 고유한 네트워크 트래픽 (예: SIP 트래픽 및 미디어 트래픽)의 균형을 유지 합니다. DNS 부하 분산은 프런트 엔드 풀, Edge 풀, 디렉터 풀 및 독립 실행형 중재 풀에 대해 지원 됩니다. DNS 부하 분산을 사용 하도록 구성 된 풀에는 DNS 부하 분산 (예: pool1.contoso.com)에서 사용 되 고 풀에 있는 서버의 실제 Ip로 확인 되는 일반 풀 FQDN이 정의 되어 있어야 합니다. 풀의 가상 IP 주소를 확인 하는 풀의 웹 서비스 (예: web1.contoso.net)에 대 한 다른 FQDN. DNS 부하 분산에 대 한 자세한 내용은 계획 설명서의 [Lync Server 2013에서 dns 부하 분산](lync-server-2013-dns-load-balancing.md) 을 참조 하세요.

<div>


> [!NOTE]  
> 클라이언트에서 서버 HTTPS 트래픽에 대해 하드웨어 로드 균형 조정이 여전히 필요 합니다.



</div>

DNS 부하 분산을 사용 하려면 먼저 다음을 수행 해야 합니다.

1.  내부 웹 서비스 풀 FQDN을 재정의 합니다.
    
    <div>
    

    > [!WARNING]  
    > 내부 웹 서비스를 자체 정의 FQDN으로 재정의 하기로 결정 한 경우 각 FQDN은 다른 프런트 엔드 풀, 디렉터 또는 디렉터 풀에서 고유 해야 합니다.

    
    </div>

2.  DNS 호스트 레코드를 만들어 풀에 있는 모든 서버의 IP 주소에 대 한 풀 FQDN을 확인 합니다.

3.  IP 주소 임의 사용 또는 Windows Server DNS의 경우 라운드 로빈 기능을 사용 하도록 설정 합니다.
    
    <div>
    

    > [!NOTE]  
    > 라운드 로빈은 기본적으로 사용 하도록 설정 되어 있어야 합니다.

    
    </div>

<div>

## <a name="to-override-internal-web-services-fqdn"></a>내부 웹 서비스 FQDN을 재정의 하려면

1.  토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.

2.  콘솔 트리에서 Enterprise Edition 프런트 엔드 풀 노드를 확장 합니다.

3.  풀을 마우스 오른쪽 단추로 클릭 하 고 **속성 편집**을 클릭 한 다음 **웹 서비스**를 클릭 합니다.

4.  **내부 웹 서비스**아래에서 **FQDN 재정의** 확인란을 선택 합니다.

5.  풀에 있는 서버의 실제 IP 주소로 확인 되는 풀 FQDN을 입력 합니다.

6.  **외부 웹 서비스**아래에서 풀의 가상 IP 주소로 확인 되는 외부 풀 FQDN을 입력 한 다음 **확인**을 클릭 합니다.

7.  콘솔 트리에서 **Lync Server 2013**을 클릭 한 다음 **작업** 창에서 **토폴로지 게시**를 클릭 합니다.

</div>

<div>

## <a name="to-create-dns-host-a-records-for-all-internal-pool-servers"></a>모든 내부 풀 서버에 대 한 DNS 호스트 (A) 레코드를 만들려면

1.  **시작**을 클릭 하 고 **모든 프로그램**을 클릭 한 다음 **관리 도구**를 클릭 하 고 **DNS**를 클릭 합니다.

2.  **Dns 관리자**에서 레코드를 관리 하는 dns 서버를 클릭 하 여 확장 합니다.

3.  **정방향 조회 영역** 을 클릭 하 여 확장 합니다.

4.  레코드를 추가 해야 하는 DNS 도메인을 마우스 오른쪽 단추로 클릭 한 다음 **새 호스트 (A 또는 AAAA)** 를 클릭 합니다.

5.  **이름** 상자에 호스트 레코드의 이름을 입력 합니다 (도메인 이름이 자동으로 추가 됨).

6.  IP 주소 상자에 개별 프런트 엔드 서버의 IP 주소를 입력 한 다음 **연결 된 포인터 (PTR) 레코드 만들기** 를 선택 하거나, 해당 되는 경우 **인증 된 모든 사용자가 동일한 소유자 이름을 사용 하 여 DNS 레코드를 업데이트 하도록 허용**합니다.

7.  DNS 부하 분산에 참여 하는 모든 구성원 프런트 엔드 서버에 대 한 레코드를 계속 만듭니다.
    
    예를 들어 pool1.contoso.com 및 프런트 엔드 서버 3 대의 풀을 보유 하 고 있는 경우 다음과 같은 DNS 항목을 만듭니다.
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Q</th>
    <th>유형</th>
    <th>데이터</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Pool1.contoso.com</p></td>
    <td><p>Host (A)</p></td>
    <td><p>192.168.1.1</p></td>
    </tr>
    <tr class="even">
    <td><p>Pool1.contoso.com</p></td>
    <td><p>Host (A)</p></td>
    <td><p>192.168.1.2</p></td>
    </tr>
    <tr class="odd">
    <td><p>Pool1.contoso.com</p></td>
    <td><p>Host (A)</p></td>
    <td><p>192.168.1.3</p></td>
    </tr>
    </tbody>
    </table>
    
    DNS 호스트 (A) 레코드를 만드는 방법에 대 한 자세한 내용은 [Lync Server 2013에 대 한 Dns 호스트 레코드 구성을](lync-server-2013-configure-dns-host-records.md)참조 하세요.

</div>

<div>

## <a name="to-enable-round-robin-for-windows-server"></a>Windows Server에서 라운드 로빈 사용

1.  **시작**을 클릭 하 고 **모든 프로그램**을 클릭 한 다음 **관리 도구**를 클릭 하 고 **DNS**를 클릭 합니다.

2.  **Dns**를 확장 하 고 구성 하려는 dns 서버를 마우스 오른쪽 단추로 클릭 한 다음 **속성**을 클릭 합니다.

3.  **고급** 탭을 클릭 하 고 **라운드 로빈 사용** 및 **넷마스크 순서 지정 사용**을 선택한 다음 **확인**을 클릭 합니다.
    
    ![Dns 라운드 로빈 대화 상자](images/Gg398251.e7bf6125-8d78-4460-8401-0a8e7e21d305(OCS.15).jpg "dns 라운드 로빈 대화 상자")

<div>


> [!NOTE]  
> 이 기능은 기본적으로 사용 하도록 설정 되어 있어야 합니다.



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

