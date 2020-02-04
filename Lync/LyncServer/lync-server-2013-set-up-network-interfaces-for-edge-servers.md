---
title: 'Lync Server 2013: 에지 서버에 대한 네트워크 인터페이스 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up network interfaces for Edge Servers
ms:assetid: b0aecdf6-4ae2-46f6-b9b6-948bfc3df11e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412847(v=OCS.15)
ms:contentKeyID: 48185152
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfbae47a5f5e99e603e3f095a2e07dbb9b49515f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764644"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-network-interfaces-for-edge-servers-in-lync-server-2013"></a>Lync Server 2013에서 에지 서버에 대한 네트워크 인터페이스 설정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-08_

각 Edge 서버는 외부 및 내부 인터페이스를 사용 하는 멀티홈 컴퓨터입니다. 어댑터 DNS (Domain Name System) 설정은 주변 네트워크에 DNS 서버가 있는지 여부에 따라 달라 집니다. DNS 서버가 경계에 있으면 다음 홉 서버 또는 풀 (즉, 디렉터 또는 지정 된 프런트 엔드 풀)에 대 한 DNS A 레코드가 하나 이상 포함 된 영역이 있어야 하 고, 외부 쿼리를 위해 다른 공용 DNS 서버에 대 한 이름 조회를 참조 하 게 됩니다. 경계에 DNS 서버가 없는 경우에는 Edge 서버에서 외부 DNS 서버를 사용 하 여 인터넷 이름 조회를 확인 하 고 각 Edge 서버는 호스트를 사용 하 여 다음 홉 서버 이름을 IP 주소로 확인 합니다.

<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="보안이" alt="security" />보안 참고 사항:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>보안상의 이유로, Edge 서버가 내부 네트워크에 있는 DNS 서버에 액세스 하지 않는 것이 좋습니다.</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="to-configure-interfaces-with-dns-servers-in-the-perimeter-network"></a>경계 네트워크에서 DNS 서버를 사용 하 여 인터페이스를 구성 하려면

1.  각 Edge 서버에 대 한 두 개의 네트워크 어댑터, 즉 내부 인터페이스와 외부 인터페이스에 대해 각각 하나씩 설치 합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 내부 및 외부 서브넷을 서로 라우팅할 수 없어야 합니다.

    
    </div>

2.  외부 인터페이스에서 외부 경계 네트워크 (DMZ, 완충 지역 및 스크린 된 서브넷이 라고도 함) 서브넷에 세 개의 고정 IP 주소를 구성 하 고, 외부 방화벽의 내부 인터페이스에 대 한 기본 게이트웨이를 가리킵니다. 경계 DNS 서버 쌍을 가리키도록 어댑터 DNS 설정을 구성 합니다.
    
    <div>
    

    > [!NOTE]  
    > 이 인터페이스에 대해 단 하나의 IP 주소를 사용할 수 있지만, 이렇게 하려면 포트 할당을 비표준 값으로 변경 해야 합니다. 토폴로지 작성기에서 토폴로지를 만들 때이를 결정 합니다.

    
    </div>

3.  내부 인터페이스에서 내부 경계 네트워크 서브넷에 하나의 고정 IP 주소를 구성 하 고 기본 게이트웨이를 설정 하지 않습니다. 하나 이상의 DNS 서버를 가리키도록 어댑터 DNS 설정을 구성 하 고, 가능 하면 경계 DNS 서버 쌍을 만듭니다.

4.  내부 인터페이스에서 클라이언트, Lync Server 2013 및 Exchange UM (통합 메시징) 서버가 상주 하는 모든 내부 네트워크에 대 한 영구 고정 경로를 만듭니다.

</div>

<div>

## <a name="to-configure-interfaces-without-dns-servers-in-the-perimeter-network"></a>경계 네트워크에서 DNS 서버 없이 인터페이스를 구성 하려면

1.  각 Edge 서버에 대 한 두 개의 네트워크 어댑터, 즉 내부 인터페이스와 외부 인터페이스에 대해 각각 하나씩 설치 합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 내부 및 외부 서브넷을 서로 라우팅할 수 없어야 합니다.

    
    </div>

2.  외부 인터페이스에서 외부 경계 네트워크 서브넷에 세 개의 고정 IP 주소를 구성 합니다. 또한 외부 인터페이스에서 기본 게이트웨이를 구성 합니다. 예를 들어 인터넷 연결 라우터 또는 외부 방화벽을 기본 게이트웨이로 정의 합니다. Dns 서버를 가리키도록 DNS 설정 (특히 외부 DNS 서버 쌍을 연결)을 구성 합니다.
    
    <div>
    

    > [!NOTE]  
    > 외부 인터페이스에 대해 하나의 IP 주소를 사용 하는 것은 불가능 하지만 권장 하지는 않습니다. 이 작업을 허용 하려면 포트 할당을 비표준 값으로 변경 하 고, 일반적으로 클라이언트 통신용으로 "방화벽에 맞게 표시" 하는 기본 포트 443에서 멀리 야 합니다. 토폴로지 작성기에서 토폴로지를 만들 때 IP 주소 설정과 포트 설정을 결정 합니다.

    
    </div>

3.  내부 인터페이스에서 내부 경계 네트워크 서브넷에 하나의 고정 IP 주소를 구성 하 고 기본 게이트웨이를 설정 하지 않습니다. 어댑터 DNS 설정을 비워 둡니다.

4.  Lync Server 2013을 실행 하는 Lync 클라이언트나 서버가 상주 하는 모든 내부 네트워크에 대 한 내부 인터페이스에 영구 고정 경로를 만듭니다.

5.  각 Edge 서버에서 호스트 파일을 편집 하 여 다음 홉 서버나 VIP (가상 IP)에 대 한 레코드를 포함 합니다 (이 레코드는 디렉터, Standard Edition Server 또는 Edge 서버 다음 홉 주소로 구성 된 프런트 엔드 풀 (토폴로지 작성기)). DNS 부하 분산을 사용 하는 경우 다음 홉 풀의 각 구성원에 대 한 회선을 포함 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

