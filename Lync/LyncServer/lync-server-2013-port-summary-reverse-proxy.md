---
title: 'Lync Server 2013: 포트 요약-역방향 프록시'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Reverse proxy
ms:assetid: 59b9ac3c-3e6f-4776-b366-174f0dd1f2eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204932(v=OCS.15)
ms:contentKeyID: 48184251
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 203acca41c3e759bb05787c2bc23fd0ac773355f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043190"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---reverse-proxy-in-lync-server-2013"></a>포트 요약-Lync Server 2013의 역방향 프록시

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-15_

역방향 프록시는 방화벽 및 포트/프로토콜에 대한 최소 요구 사항을 갖고 있습니다.

  - 외부 방화벽 요구 사항은 HTTPS/TCP/443, 선택적 HTTP/TCP/80입니다. HTTPS는 역방향 프록시를 통한 SSL 및 TLS 보안 통신에 사용 됩니다. 인증서를 수정할 때 자동 검색 서비스에 대 한 액세스를 허용 하도록 선택한 경우 HTTP를 사용 하는 것이 좋습니다.

  - 클라이언트는 HTTPS에서 Office Web Apps 서버에 연결할 것으로 예상 합니다. Office Web Apps 서버는 HTTPS/TCP/443의 내부 클라이언트와 통신을 필요로 합니다. 권장 구성은 역방향 프록시에서 Office Web Apps 서버로의 HTTPS/TCP/443을 허용 하는 것입니다.

  - 포트 8080은 역방향 프록시 내부 인터페이스에서 프런트 엔드 서버, 프런트 엔드 풀 VIP (가상 IP) 또는 선택 사항인 디렉터 또는 디렉터 풀 VIP로 트래픽을 라우팅하는 데 사용 됩니다. 외부 웹 서비스 게시 규칙 인증서를 수정 하는 경우 (예: SIP 도메인이 많은 경우) 자동 검색 서비스를 찾기 위해 Lync를 실행 하는 모바일 장치에는 포트 TCP 8080이 필요 합니다. 필요한 SAN 항목이 포함된 새 인증서를 가져오도록 선택한 경우 포트 TCP 8080은 필수가 아니라 선택 사항입니다.

  - 포트 4443은 역방향 프록시 내부 인터페이스에서 프런트 엔드 서버, 프런트 엔드 풀 VIP (가상 IP) 또는 디렉터 풀 VIP로의 트래픽에 사용 됩니다.
    
    ![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")  
    
    <div>
    

    > [!WARNING]  
    > 서버에서 중앙 관리 저장소 역할을 관리 하는 프런트 엔드 풀 또는 Standard Edition server에서 TCP 트래픽을 통해 포트 4443에 대 한 내부 배포에서 TCP를 통한 4443을 혼동 하지 마십시오.

    
    </div>

<div>

## <a name="port-and-protocol-details"></a>포트 및 프로토콜 세부 정보

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
<td><p>반드시 사용자가 http://&lt;publishedSiteFQDN&gt;를 입력 한 경우 HTTPS로 리디렉션</p>
<p>또한 조직에서 외부 웹 서비스 게시 규칙 인증서를 수정 하지 않으려는 상황에서 Lync를 실행 하는 모바일 장치에 대 한 자동 검색 서비스와 회의에 Office Web Apps를 사용 하는 경우에도 필요 합니다.</p></td>
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
<td><p>프런트 엔드 서버, 프런트 엔드 풀, 디렉터, 디렉터 풀</p></td>
<td><p>조직에서 외부 웹 서비스 게시 규칙 인증서를 수정 하지 않으려는 상황에서 Lync를 실행 하는 모바일 장치에 대 한 자동 검색 서비스를 사용 하는 경우 필요 합니다.</p>
<p>역방향 프록시 외부 인터페이스에서 포트 80으로 전송된 트래픽은 풀 웹 서비스에서 내부 웹 트래픽과 구분할 수 있도록 역방향 프록시 내부 인터페이스에서 포트 8080을 통해 풀로 리디렉션됩니다.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>내부 역방향 프록시 인터페이스</p></td>
<td><p>프런트 엔드 서버, 프런트 엔드 풀, 디렉터, 디렉터 풀</p></td>
<td><p>역방향 프록시 외부 인터페이스에서 포트 443으로 전송된 트래픽은 풀 웹 서비스에서 내부 웹 트래픽과 구분할 수 있도록 역방향 프록시 내부 인터페이스에서 포트 4443을 통해 풀로 리디렉션됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP/443</p></td>
<td><p>내부 역방향 프록시 인터페이스</p></td>
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

