---
title: 'Lync Server 2013: 포트 요약 - 역방향 프록시'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Reverse proxy
ms:assetid: 59b9ac3c-3e6f-4776-b366-174f0dd1f2eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204932(v=OCS.15)
ms:contentKeyID: 48184251
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a86b993a35210934f5ebef61464c11a153bf297
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985800"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---reverse-proxy-in-lync-server-2013"></a>Lync Server 2013의 포트 요약 - 역방향 프록시

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-15_

역방향 프록시에는 방화벽과 포트/프로토콜에 대 한 최소 요구 사항이 있습니다.

  - 외부 방화벽 요구 사항은 HTTPS/TCP/443 및 선택적 HTTP/TCP/80입니다. HTTPS는 역방향 프록시를 통해 SSL 및 TLS 보안 통신에 사용 됩니다. HTTP는 인증서를 수정 하는 것이 어렵거나 비용을 정당화 하지 않을 때 자동 검색 서비스에 대 한 액세스를 허용 하도록 선택한 경우에 사용 됩니다.

  - 클라이언트가 HTTPS의 Office Web Apps 서버에 접속 하는 것으로 예상 됩니다. Office Web Apps 서버는 HTTPS/TCP/443의 내부 클라이언트 통신이 필요 합니다. 권장 되는 구성은 역방향 프록시에서 Office Web Apps 서버로 HTTPS/TCP/443을 허용 하는 것입니다.

  - 포트 8080는 역방향 프록시 내부 인터페이스의 트래픽을 프런트 엔드 서버, 프론트 엔드 풀 VIP (가상 IP) 또는 선택 디렉터 또는 디렉터 풀 VIP로 라우팅하는 데 사용 됩니다. Lync를 실행 하는 모바일 장치에서는 외부 웹 서비스 게시 규칙 인증서 (예: 많은 수의 SIP 도메인이 있는 경우)를 수정 하는 경우 자동 검색 서비스를 찾기 위해 TCP 8080 포트가 필요 합니다. 필요한 SAN 항목을 사용 하 여 새 인증서를 획득 하도록 선택 하는 경우 포트 TCP 8080이 필요 하지 않으며 선택 사항입니다.

  - 포트 4443는 역방향 프록시 내부 인터페이스에서 프런트 엔드 서버로의 트래픽, 프론트 엔드 풀 VIP (가상 IP) 또는 선택 사항인 디렉터 또는 디렉터 풀 VIP에 사용 됩니다.
    
    ![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")  
    
    <div>
    

    > [!WARNING]  
    > 원본 버전 서버 또는 중앙 관리 저장소 역할을 관리 하는 프런트 엔드 풀의 TCP 트래픽을 통해 포트 4443에서 TCP를 통해 4443를 역방향 프록시에서 내부 배포로 혼동 하지 마세요.

    
    </div>

<div>

## <a name="port-and-protocol-details"></a>포트 및 프로토콜 정보

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
<td><p>) 사용자가 http://&lt;publishedSiteFQDN&gt;를 입력 하는 경우 HTTPS로 리디렉션.</p>
<p>회의에 Office Web Apps를 사용 하는 경우 및 조직에서 외부 웹 서비스 게시 규칙 인증서를 수정 하지 않으려는 경우 Lync를 실행 하는 모바일 장치에 대 한 자동 검색 서비스를 사용할 때도 필요 합니다.</p></td>
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
<td><p>프런트 엔드 서버, 프론트 엔드 풀, 이사, 이사 풀</p></td>
<td><p>조직에서 외부 웹 서비스 게시 규칙 인증서를 수정 하지 않으려는 경우 Lync를 실행 하는 모바일 장치에 대 한 자동 검색 서비스를 사용 하는 경우 필요 합니다.</p>
<p>역방향 프록시 외부 인터페이스에서 포트 80로 전송 된 트래픽은 역방향 프록시 내부 인터페이스에서 포트 8080의 풀로 리디렉션되어,이는 풀 웹 서비스가 내부 웹 트래픽과 구별할 수 있도록 합니다.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>내부 리버스 프록시 인터페이스</p></td>
<td><p>프런트 엔드 서버, 프론트 엔드 풀, 이사, 이사 풀</p></td>
<td><p>역방향 프록시 외부 인터페이스에서 포트 443로 전송 된 트래픽은 역방향 프록시 내부 인터페이스에서 포트 4443의 풀로 리디렉션되어,이는 풀 웹 서비스가 내부 웹 트래픽과 구별할 수 있도록 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP/443</p></td>
<td><p>내부 리버스 프록시 인터페이스</p></td>
<td><p>회의를 위한 Office Web Apps</p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

