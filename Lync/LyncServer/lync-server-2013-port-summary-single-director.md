---
title: 'Lync Server 2013: 포트 요약 - 단일 디렉터'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Single Director
ms:assetid: 079c1414-723f-4499-b7d4-a0d7121c1626
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204648(v=OCS.15)
ms:contentKeyID: 48183322
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0179d6fd27207d28caa10ffa01bea155f9b00c03
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725028"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---single-director-in-lync-server-2013"></a>Lync Server 2013의 포트 요약 - 단일 디렉터

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-20_

단일 디렉터에 대 한 방화벽 포트 요구 사항은 내부 인터페이스 또는 리버스 프록시의 내부 네트워크에서 디렉터와의 통신을 설정 하는 데 사용 되는 포트로 구성 됩니다. Microsoft Lync Server 2013에는 기본적으로 역방향 프록시, 디렉터에 대 한 HTTP/TCP 8080 및 HTTPS/TCP 4443가 프런트 엔드 풀 및 프런트 엔드 서버와 함께 열려 있어야 합니다. 또한 Edge Server 내부 인터페이스에서 디렉터 및 프런트 엔드 풀 및 프런트 엔드 서버로의 SIP (세션 초기화 프로토콜) 통신이 필요 합니다. SIP 프로토콜은 Edge 서버에서 프런트 엔드 풀 및 프런트 엔드 서버로 SIP/MTLS/TCP 5061를 사용 합니다. SIP/MTLS/TCP 5061 통신을 디렉터, 프런트 엔드 풀 및 프런트 엔드 서버와 Edge 서버 내부 인터페이스와 함께 만들어야 하는 규칙입니다.

### <a name="single-director-ports-and-protocols-for-firewall-definitions"></a>방화벽 정의에 대 한 단일 디렉터 포트 및 프로토콜

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>역할/프로토콜/TCP 또는 UDP/포트</th>
<th>원본 IP 주소</th>
<th>대상 IP 주소</th>
<th>상속자</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP 8080</p></td>
<td><p>리버스 프록시 내부 인터페이스</p></td>
<td><p>Director</p></td>
<td><p>처음에 리버스 프록시의 외부에서 수신 되어, 통신이 디렉터 및 프런트 엔드 서버 웹 서비스로 전송 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP 4443</p></td>
<td><p>리버스 프록시 내부 인터페이스</p></td>
<td><p>Director</p></td>
<td><p>처음에 리버스 프록시의 외부에서 수신 되어, 통신이 디렉터 및 프런트 엔드 서버 웹 서비스로 전송 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 444</p></td>
<td><p>Director</p></td>
<td><p>프런트 엔드 서버 또는 프런트 엔드 풀</p></td>
<td><p>디렉터와 프런트 엔드 서버 간의 서버 간 통신</p></td>
</tr>
<tr class="even">
<td><p>HTTP/TCP 80</p></td>
<td><p>내부 클라이언트</p></td>
<td><p>웹 서비스 감독</p></td>
<td><p>디렉터는 내부 및 외부 클라이언트에 웹 서비스를 제공 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 443</p></td>
<td><p>내부 클라이언트</p></td>
<td><p>웹 서비스 감독</p></td>
<td><p>디렉터는 내부 및 외부 클라이언트에 웹 서비스를 제공 합니다.</p></td>
</tr>
<tr class="even">
<td><p>SIP/MTLS/TCP 5061</p></td>
<td><p>Edge 서버 내부 인터페이스</p></td>
<td><p>Director</p></td>
<td><p>Edge 서버에서 디렉터 및 프런트 엔드 서버로의 SIP 통신.</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50001</p></td>
<td><p>이상</p></td>
<td><p>Edge 서버 내부 인터페이스</p></td>
<td><p>중앙 로깅 서비스 컨트롤러 (ClsController .exe) 또는 에이전트 (ClasAgent) 명령 및 로그 수집</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50002</p></td>
<td><p>이상</p></td>
<td><p>Edge 서버 내부 인터페이스</p></td>
<td><p>중앙 로깅 서비스 컨트롤러 (ClsController .exe) 또는 에이전트 (ClasAgent) 명령 및 로그 수집</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50003</p></td>
<td><p>이상</p></td>
<td><p>Edge 서버 내부 인터페이스</p></td>
<td><p>중앙 로깅 서비스 컨트롤러 (ClsController .exe) 또는 에이전트 (ClasAgent) 명령 및 로그 수집</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

