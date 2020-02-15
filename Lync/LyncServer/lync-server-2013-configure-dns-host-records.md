---
title: 'Lync Server 2013: DNS 호스트 레코드 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS Host records
ms:assetid: 78a1afcf-41c8-4da5-8740-c6570c19078c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398593(v=OCS.15)
ms:contentKeyID: 48184577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54ae1e2502ec1618f007ba76255ae6d01ebb66f5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028589"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-host-records-for-lync-server-2013"></a>Lync Server 2013에 대 한 DNS 호스트 레코드 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-01_

이 절차를 성공적으로 완료하려면 서버 또는 도메인에 최소한 Domain Admins 그룹의 구성원 또는 DnsAdmins 그룹의 구성원으로 로그온해야 합니다.

<div>

## <a name="to-configure-dns-host-a-records"></a>DNS 호스트 A 레코드를 구성하려면

1.  DNS(Domain Name System) 서버에서 **시작**, **관리 도구**를 차례로 클릭한 다음 **DNS**를 클릭합니다.

2.  도메인의 콘솔 트리에서 **정방향 조회 영역**을 확장 한 다음 Lync Server 2013을 설치할 도메인을 마우스 오른쪽 단추로 클릭 합니다.

3.  **새 호스트(A 또는 AAAA)** 를 클릭합니다.

4.  **이름**을 클릭하고 풀의 호스트 이름을 입력합니다(도메인 이름은 레코드가 정의된 영역에서 가져온 것으로 가정되며 A 레코드의 일부로 입력할 필요는 없음).

5.  **IP 주소**를 클릭 하 고 프런트 엔드 풀에 대 한 부하 분산 장치의 VIP (가상 IP)를 입력 합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 디렉터 풀을 사용하는 배포에서 단순 URL에 대한 호스트(A) 레코드는 디렉터 부하 분산 장치의 VIP를 가리켜야 합니다.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > 부하 분산 장치가 없는 토폴로지에 연결된 하나의 Enterprise Edition 서버 또는 디렉터를 배포하는 경우 Enterprise Edition 서버, Standard Edition 서버 또는 디렉터의 IP 주소를 입력합니다. 풀에 둘 이상의 Enterprise Edition 서버 또는 디렉터를 배포하는 경우 부하 분산 장치가 필요합니다. Standard Edition 서버에는 부하 분산 장치를 사용하지 않습니다.

    
    </div>

6.  **호스트 추가**를 클릭한 다음 **확인**을 클릭합니다.

7.  A 레코드를 추가로 만들려면 4단계와 5단계를 반복합니다.

8.  필요한 A 레코드를 모두 만들었으면 **완료**를 클릭합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

