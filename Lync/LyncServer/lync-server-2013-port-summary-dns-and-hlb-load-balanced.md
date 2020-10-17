---
title: 'Lync Server 2013: 포트 요약-DNS 및 HLB 부하 분산 됨'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - DNS and HLB load balanced
ms:assetid: b07c37e4-820e-46ee-a678-1da95d1b87af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205179(v=OCS.15)
ms:contentKeyID: 48185149
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b6ba03a73538426b9c820388f65e728c36881148
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527945"
---
# <a name="port-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a>포트 요약-Lync Server 2013에서 DNS 및 HLB 부하 분산

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-22_

단일 디렉터에 대 한 방화벽 포트 요구 사항은 내부 인터페이스 또는 역방향 프록시의 내부 연결 네트워크에서 디렉터와의 통신을 설정 하는 데 사용 되는 포트로 구성 됩니다. 기본적으로 Microsoft Lync Server 2013은 프런트 엔드 풀 및 프런트 엔드 서버 뿐만 아니라 역방향 프록시에서 디렉터로의 포트 HTTP/TCP 8080 및 HTTPS/TCP 4443을 사용할 것으로 예상 합니다. 또한에 지 서버 내부 인터페이스에서 디렉터 및 프런트 엔드 풀 및 프런트 엔드 서버로의 SIP (session 착수 프로토콜) 통신이 있어야 합니다. SIP 프로토콜은에 지 서버에서 프런트 엔드 풀 및 프런트 엔드 서버로의 SIP/MTLS/TCP 5061를 사용 합니다. 디렉터, 프런트 엔드 풀 및 프런트 엔드 서버에서에 지 서버 내부 인터페이스에 대 한 SIP/MTLS/TCP 5061 통신을 허용 하는 규칙을 만들어야 합니다.

### <a name="single-director-ports-and-protocols-for-firewall-definitions"></a>방화벽 정의를 위한 단일 디렉터 포트 및 프로토콜

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
<th>참고</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP 8080</p></td>
<td><p>역방향 프록시 내부 인터페이스</p></td>
<td><p>디렉터 하드웨어 부하 분산 장치 VIP</p></td>
<td><p>역방향 프록시의 외부 쪽에서 처음 수신 되는 통신은 디렉터 HLB VIP 및 프런트 엔드 서버 웹 서비스로 전송 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP 4443</p></td>
<td><p>역방향 프록시 내부 인터페이스</p></td>
<td><p>디렉터 하드웨어 부하 분산 장치 VIP</p></td>
<td><p>역방향 프록시의 외부 쪽에서 처음 수신 되는 통신은 디렉터 HLB VIP 및 프런트 엔드 서버 웹 서비스로 전송 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 444</p></td>
<td><p>Director</p></td>
<td><p>프런트 엔드 풀 또는 프런트 엔드 서버</p></td>
<td><p>디렉터 HLB VIP와 프런트 엔드 서버 또는 프런트 엔드 서버 간의 서버 간 통신</p></td>
</tr>
<tr class="even">
<td><p>HTTP/TCP 80</p></td>
<td><p>내부 클라이언트</p></td>
<td><p>디렉터 하드웨어 부하 분산 장치 VIP</p></td>
<td><p>디렉터는 내부 및 외부 클라이언트에 대해 웹 서비스를 제공 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 443</p></td>
<td><p>내부 클라이언트</p></td>
<td><p>디렉터 하드웨어 부하 분산 장치 VIP</p></td>
<td><p>디렉터는 내부 및 외부 클라이언트에 대해 웹 서비스를 제공 합니다.</p></td>
</tr>
<tr class="even">
<td><p>SIP/MTLS/TCP 5061</p></td>
<td><p>에 지 서버 내부 인터페이스</p></td>
<td><p>Director</p></td>
<td><p>에 지 서버에서 디렉터로의 SIP 통신 및 프런트 엔드 서버</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50001</p></td>
<td><p>모두</p></td>
<td><p>Director</p></td>
<td><p>중앙 로깅 서비스 컨트롤러 (ClsController.exe) 또는 에이전트 (ClsAgent.exe) 명령 및 로그 수집</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50002</p></td>
<td><p>모두</p></td>
<td><p>Director</p></td>
<td><p>중앙 로깅 서비스 컨트롤러 (ClsController.exe) 또는 에이전트 (ClsAgent.exe) 명령 및 로그 수집</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50003</p></td>
<td><p>모두</p></td>
<td><p>Director</p></td>
<td><p>중앙 로깅 서비스 컨트롤러 (ClsController.exe) 또는 에이전트 (ClsAgent.exe) 명령 및 로그 수집</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

