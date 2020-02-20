---
title: 'Lync Server 2013: 포트 요약-자동 검색'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Autodiscover
ms:assetid: 8bd16363-5e18-4e4b-be99-b3e6457b4c99
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945642(v=OCS.15)
ms:contentKeyID: 51541497
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 635f8fca3b267fa2366b66b990ec0621f58f58e4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152666"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---autodiscover-in-lync-server-2013"></a>포트 요약-Lync Server 2013의 자동 검색

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-03-05_

Lync Server 2013 자동 검색 서비스는 디렉터 및 프런트 엔드 풀 서버에서 실행 되 고, `lyncdiscover.<domain>` 및 `lyncdiscoverinternal.<domain>` 호스트 레코드를 사용 하 여 DNS에 게시 되 면 클라이언트에서 lync server 기능을 찾을 때 사용할 수 있습니다. Lync Mobile을 실행 하는 모바일 장치에서 자동 검색을 사용 하려면 먼저 자동 검색 서비스를 실행 하는 모든 디렉터 및 프런트 엔드 서버에서 인증서 주체 대체 이름 목록을 수정 해야 할 수 있습니다. 또한 역방향 프록시에 대한 외부 웹 서비스 게시 규칙에 사용되는 인증서에서도 주체 대체 이름 목록을 수정해야 할 수 있습니다.

역방향 프록시에서 주체 대체 이름 목록을 사용할지 여부에 대 한 결정은 포트 80 또는 포트 443에 자동 검색 서비스를 게시할지 여부에 따라 달라 집니다.

  - **모바일 장치용 포트 80**   에 게시 된 경우 자동 검색 서비스에 대 한 초기 쿼리가 포트 80를 통해 수행 되는 경우 인증서를 변경할 필요가 없습니다. Lync를 실행 하는 모바일 장치는 외부에서 포트 80의 역방향 프록시에 액세스 한 다음 내부적으로 포트 8080에서 디렉터 또는 프런트 엔드 서버로 리디렉션되도록 하기 때문입니다.

  - **게시 된 포트 443**   외부 웹 서비스 게시 규칙에서 사용 하는 인증서의 주체 대체 이름 목록에 조직 내의 `lyncdiscover.<sipdomain>` 각 SIP 도메인에 대 한 항목이 포함 되어 있어야 합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 모바일 기능을 배포한 Lync Server 2010에서 새로 설치 하거나 업그레이드 하는 경우에는 모바일 서비스의 자동 검색을 위해 Port 80을 사용 하거나 적절 한 주체 이름 및 주체 대체 이름을 사용 하 여 인증서를 다시 발급 해야 합니다. 디렉터 및 프런트 엔드 서버의 인증서를 검토 하 여 선택한 경로를 확인 합니다.

    
    </div>

### <a name="firewall-details-for-reverse-proxy-server-external-interface"></a>역방향 프록시 서버에 대한 방화벽 세부 정보: 외부 인터페이스

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>프로토콜/TCP 또는 UDP/포트</th>
<th>원본 IP 주소</th>
<th>대상 IP 주소</th>
<th>Notes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP/80</p></td>
<td><p>모두</p></td>
<td><p>역방향 프록시 수신기</p></td>
<td><p>반드시 사용자가 http://&lt;publishedSiteFQDN&gt;를 입력 한 경우 HTTPS로 리디렉션 또한 조직에서 외부 웹 서비스 게시 규칙 인증서를 수정 하지 않으려는 상황에서 Lync를 실행 하는 모바일 장치에 대 한 자동 검색 서비스와 회의에 Office Web Apps를 사용 하는 경우에도 필요 합니다.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/443</p></td>
<td><p>모두</p></td>
<td><p>역방향 프록시 수신기</p></td>
<td><p>주소록 다운로드, 주소록 웹 쿼리 서비스, 자동 검색, 클라이언트 업데이트, 모임 콘텐츠, 장치 업데이트, 그룹 확장, 회의를 위한 Office Web Apps, 전화 접속 회의 및 모임</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-details-for-reverse-proxy-server-internal-interface"></a>역방향 프록시 서버에 대한 방화벽 세부 정보: 내부 인터페이스

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>프로토콜/TCP 또는 UDP/포트</th>
<th>원본 IP 주소</th>
<th>대상 IP 주소</th>
<th>Notes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP/8080</p></td>
<td><p>내부 역방향 프록시 인터페이스</p></td>
<td><p>프런트 엔드 서버, 프런트 엔드 풀, 디렉터, 디렉터 풀, 회의를 위한 Office Web Apps</p></td>
<td><p>조직에서 외부 웹 서비스 게시 규칙 인증서를 수정 하지 않으려는 상황에서 Lync를 실행 하는 모바일 장치에 대 한 자동 검색 서비스를 사용 하는 경우 필요 합니다. 역방향 프록시 외부 인터페이스에서 포트 80으로 전송된 트래픽은 풀 웹 서비스에서 내부 웹 트래픽과 구분할 수 있도록 역방향 프록시 내부 인터페이스에서 포트 8080을 통해 풀로 리디렉션됩니다.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>내부 역방향 프록시 인터페이스</p></td>
<td><p>프런트 엔드 서버, 프런트 엔드 풀, 디렉터, 디렉터 풀, 회의를 위한 Office Web Apps</p></td>
<td><p>역방향 프록시 외부 인터페이스에서 포트 443으로 전송된 트래픽은 풀 웹 서비스에서 내부 웹 트래픽과 구분할 수 있도록 역방향 프록시 내부 인터페이스에서 포트 4443을 통해 풀로 리디렉션됩니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

