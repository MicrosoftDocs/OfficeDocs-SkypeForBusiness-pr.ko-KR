---
title: 'Lync Server 2013: 포트 요약-자동 검색'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Autodiscover
ms:assetid: 8bd16363-5e18-4e4b-be99-b3e6457b4c99
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945642(v=OCS.15)
ms:contentKeyID: 51541497
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7a40d86799b4922a819642aedf2461f038330593
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982834"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---autodiscover-in-lync-server-2013"></a>포트 요약-Lync Server 2013의 자동 검색

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-03-05_

Lync Server 2013 자동 검색 서비스는 디렉터 및 프런트 엔드 풀 서버에서 실행 되며, `lyncdiscover.<domain>` `lyncdiscoverinternal.<domain>` 호스트 레코드를 사용 하 여 DNS에 게시 되 면 클라이언트가 lync server 기능을 찾을 수 있습니다. Lync Mobile을 실행 하는 모바일 장치에서 자동 검색을 사용 하려면 먼저 자동 검색 서비스를 실행 하는 모든 디렉터 및 프런트 엔드 서버에서 인증서 주체 대체 이름 목록을 수정 해야 할 수 있습니다. 또한 역방향 프록시에서 외부 웹 서비스 게시 규칙에 사용 되는 인증서의 주체 대체 이름 목록을 수정 해야 할 수 있습니다.

리버스 프록시에서 주체 대체 이름 목록을 사용할지 여부에 대 한 결정은 포트 80 또는 포트 443에 자동 검색 서비스를 게시할지 여부에 따라 달라 집니다.

  - **포트**   80에 대 한 자동 검색 서비스에 대 한 초기 쿼리가 발생 하는 경우 모바일 장치에 대 한 포트 80에 게시 된 인증서 변경은 필요 하지 않습니다. Lync를 실행 하는 모바일 장치는 포트 80의 역방향 프록시에 액세스 한 다음 내부적으로 포트 8080의 디렉터 또는 프런트 엔드 서버로 리디렉션되 때문입니다.

  - **포트 443**   에 게시 됨 외부 웹 서비스 게시 규칙에 사용 되는 인증서의 주체 대체 이름 목록은 조직 내 `lyncdiscover.<sipdomain>` 각 SIP 도메인에 대 한 항목을 포함 해야 합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 이동성을 배포 하는 Lync Server 2010의 새 설치 또는 업그레이드의 경우 모바일 서비스의 자동 검색을 위해 포트 80을 사용 하거나 올바른 주체 이름 및 주체 대체 이름을 사용 하 여 인증서를 다시 발급 합니다. 디렉터 및 프런트 엔드 서버의 인증서를 검토 하 여 선택한 경로를 확인 합니다.

    
    </div>

### <a name="firewall-details-for-reverse-proxy-server-external-interface"></a>리버스 프록시 서버에 대 한 방화벽 세부 정보: 외부 인터페이스

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
<th>상속자</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP/80</p></td>
<td><p>이상</p></td>
<td><p>역방향 프록시 수신기</p></td>
<td><p>) 사용자가 http://&lt;publishedSiteFQDN&gt;를 입력 하는 경우 HTTPS로 리디렉션. 회의에 Office Web Apps를 사용 하는 경우 및 조직에서 외부 웹 서비스 게시 규칙 인증서를 수정 하지 않으려는 경우 Lync를 실행 하는 모바일 장치에 대 한 자동 검색 서비스를 사용할 때도 필요 합니다.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/443</p></td>
<td><p>이상</p></td>
<td><p>역방향 프록시 수신기</p></td>
<td><p>주소록 다운로드, 주소록 웹 쿼리 서비스, 자동 검색, 클라이언트 업데이트, 모임 콘텐츠, 장치 업데이트, 그룹 확장, 회의 용 Office Web Apps, 전화 접속 회의, 모임</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-details-for-reverse-proxy-server-internal-interface"></a>리버스 프록시 서버에 대 한 방화벽 세부 정보: 내부 인터페이스

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
<th>상속자</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP/8080</p></td>
<td><p>내부 리버스 프록시 인터페이스</p></td>
<td><p>프런트 엔드 서버, 프론트 엔드 풀, 이사, 이사 풀, 회의를 위한 Office Web Apps</p></td>
<td><p>조직에서 외부 웹 서비스 게시 규칙 인증서를 수정 하지 않으려는 경우 Lync를 실행 하는 모바일 장치에 대 한 자동 검색 서비스를 사용 하는 경우 필요 합니다. 역방향 프록시 외부 인터페이스에서 포트 80로 전송 된 트래픽은 역방향 프록시 내부 인터페이스에서 포트 8080의 풀로 리디렉션되어,이는 풀 웹 서비스가 내부 웹 트래픽과 구별할 수 있도록 합니다.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>내부 리버스 프록시 인터페이스</p></td>
<td><p>프런트 엔드 서버, 프론트 엔드 풀, 이사, 이사 풀, 회의를 위한 Office Web Apps</p></td>
<td><p>역방향 프록시 외부 인터페이스에서 포트 443로 전송 된 트래픽은 역방향 프록시 내부 인터페이스에서 포트 4443의 풀로 리디렉션되어,이는 풀 웹 서비스가 내부 웹 트래픽과 구별할 수 있도록 합니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

