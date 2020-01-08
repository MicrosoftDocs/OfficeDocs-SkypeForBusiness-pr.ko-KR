---
title: 'Lync Server 2013: 포트 요약 - 조정된 통합 에지, NAT 사용 개인 IP 주소의 DNS 부하 분산'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT
ms:assetid: a296c2af-54d4-4b4f-9795-9191baf688cb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412756(v=OCS.15)
ms:contentKeyID: 48184955
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d7e9a142e478674f4be369ace5551b2b628db83
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983596"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a>Lync Server 2013의 포트 요약 - 조정된 통합 에지, NAT 사용 개인 IP 주소의 DNS 부하 분산

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-12-04_

이 시나리오 아키텍처에서 설명 하는 Lync Server 2013, Edge 서버 기능은 Lync Server 2010에서 구현 된 것과 매우 유사 합니다. 가장 주목할 만한 추가 기능은 XMPP (extensible messaging 및 현재 상태 프로토콜)에 대 한 포트 **5269 (TCP over** )입니다. Lync Server 2013는 Edge 서버 또는 Edge 풀의 XMPP 프록시와 프런트 엔드 서버 또는 프런트 엔드 풀의 XMPP 게이트웨이 서버를 선택적으로 배포 합니다.

IPv4 외에도 Edge 서버는 이제 IPv6을 지원 합니다. 명확 하 게 하기 위해 시나리오에 IPv4만 사용 됩니다.

**NAT를 사용 하 여 개인 IP 주소에 맞게 크기가 조정 된 통합 된 가장자리의 엔터프라이즈 경계 네트워크**

![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")

<div>

## <a name="port-and-protocol-details"></a>포트 및 프로토콜 정보

외부 액세스를 제공 하는 기능을 지 원하는 데 필요한 포트만을 여는 것이 좋습니다.

모든 edge 서비스에 대 한 원격 액세스의 경우 인바운드/아웃 바운드에 지 트래픽 그림에 표시 된 대로 SIP 트래픽이 directionally으로 이동 하도록 허용 해야 합니다. 또 다른 방법으로, 액세스에 지 서비스에 대 한 SIP 메시징은 인스턴트 메시징 (IM), 현재 상태, 웹 회의, 오디오/비디오 (A/V) 및 페더레이션에 관련 됩니다.

### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-external-interface--node-1-and-node-2-example"></a>NAT를 사용 하는 개인 IP 주소가 포함 된 DNS 로드 균형 조정 통합 Edge의 크기 조정에 대 한 방화벽 요약: 노드 1 및 노드 2 (예제)

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
<td><p>XMPP/TCP/5269</p></td>
<td><p>이상</p></td>
<td><p>XMPP 프록시 서비스 (액세스에 지 서비스가 있는 공유 IP 주소)</p></td>
<td><p>XMPP 프록시 서비스는 정의 된 XMPP 페더레이션에서 XMPP 연락처의 트래픽을 허용 합니다.</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>XMPP 프록시 서비스 (액세스에 지 서비스가 있는 공유 IP 주소)</p></td>
<td><p>이상</p></td>
<td><p>XMPP 프록시 서비스는 정의 된 XMPP 페더레이션에서 XMPP 연락처로 트래픽을 보냅니다.</p></td>
</tr>
<tr class="odd">
<td><p>Access/HTTP/TCP/80</p></td>
<td><p>Edge 서버 액세스에 지 서비스</p></td>
<td><p>이상</p></td>
<td><p>인증서 해지/i p 확인 및 검색</p></td>
</tr>
<tr class="even">
<td><p>Access/DNS/TCP/53</p></td>
<td><p>Edge 서버 액세스에 지 서비스</p></td>
<td><p>이상</p></td>
<td><p>TCP를 통한 DNS 쿼리</p></td>
</tr>
<tr class="odd">
<td><p>Access/DNS/UDP/53</p></td>
<td><p>Edge 서버 액세스에 지 서비스</p></td>
<td><p>이상</p></td>
<td><p>UDP를 통한 DNS 쿼리</p></td>
</tr>
<tr class="even">
<td><p>TLS (액세스/SIP)/TCP/443</p></td>
<td><p>이상</p></td>
<td><p>Edge 서버 액세스에 지 서비스</p></td>
<td><p>외부 사용자 액세스를 위한 클라이언트 대 서버 SIP 트래픽</p></td>
</tr>
<tr class="odd">
<td><p>MTLS (액세스/SIP)/TCP/5061</p></td>
<td><p>이상</p></td>
<td><p>Edge 서버 액세스에 지 서비스</p></td>
<td><p>SIP를 사용 하는 페더레이션 및 공용 IM 연결</p></td>
</tr>
<tr class="even">
<td><p>MTLS (액세스/SIP)/TCP/5061</p></td>
<td><p>Edge 서버 액세스에 지 서비스</p></td>
<td><p>이상</p></td>
<td><p>SIP를 사용 하는 페더레이션 및 공용 IM 연결</p></td>
</tr>
<tr class="odd">
<td><p>웹 회의/PSOM (TLS)/TCP/443</p></td>
<td><p>이상</p></td>
<td><p>Edge 서버 웹 회의에 지 서비스</p></td>
<td><p>웹 회의 미디어</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-59999</p></td>
<td><p>Edge 서버 A/V Edge 서비스</p></td>
<td><p>이상</p></td>
<td><p>Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 및 Lync Server 2013를 실행 하는 파트너와 페더레이션 하는 데 필요 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/UDP/50000-59999</p></td>
<td><p>Edge 서버 A/V Edge 서비스</p></td>
<td><p>이상</p></td>
<td><p>Office Communications Server 2007을 실행 하는 파트너와 페더레이션 하는 경우에만 필요 합니다.</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-59999</p></td>
<td><p>이상</p></td>
<td><p>Edge 서버 A/V Edge 서비스</p></td>
<td><p>Office Communications Server 2007을 실행 하는 파트너와의 페더레이션에만 필요</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/UDP/50000-59999</p></td>
<td><p>이상</p></td>
<td><p>Edge 서버 A/V Edge 서비스</p></td>
<td><p>Office Communications Server 2007을 실행 하는 파트너와의 페더레이션에만 필요</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Edge 서버 A/V Edge 서비스</p></td>
<td><p>이상</p></td>
<td><p>3478 아웃 바운드는 Lync Server와 통신 하는 Edge 서버의 버전과 Edge 서버 간 미디어 소통에 대 한 정보를 확인 하는 데 사용 됩니다. Lync Server 2010, Windows Live Messenger 및 Office Communications Server 2007 R2와 페더레이션 하는 데 필요 하며, 여러 Edge 풀이 회사 내에 배포 된 경우에도 필수적입니다.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>이상</p></td>
<td><p>Edge 서버 A/V Edge 서비스</p></td>
<td><p>STUN/UDP/3478에서 후보자의 협상을 설정 합니다.</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/TCP/443</p></td>
<td><p>이상</p></td>
<td><p>Edge 서버 A/V Edge 서비스</p></td>
<td><p>TCP/443을 통해 후보의 협상을 STUN/설정 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/TCP/443</p></td>
<td><p>Edge 서버 A/V Edge 서비스</p></td>
<td><p>이상</p></td>
<td><p>TCP/443을 통해 후보의 협상을 STUN/설정 합니다.</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-internal-interface--node-1-and-node-2-example"></a>NAT를 사용 하 여 개인 IP 주소가 있는 DNS 로드 균형 조정 통합 된 Edge의 크기 조정에 대 한 방화벽 요약: 내부 인터페이스-노드 1 및 노드 2 (예제)

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
<th>메모</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/MTLS/TCP/23456</p></td>
<td><p>Any (프런트 엔드 서버 주소 또는 XMPP 게이트웨이 서비스를 실행 하는 프런트 엔드 풀 IP 주소로 정의할 수 있음)</p></td>
<td><p>Edge 서버 내부 인터페이스 IP 주소</p></td>
<td><p>프런트 엔드 서버 또는 프런트 엔드 풀에서 실행 되는 XMPP 게이트웨이 서비스의 아웃 바운드 XMPP 트래픽</p></td>
</tr>
<tr class="even">
<td><p>SIP/MTLS/TCP/5061</p></td>
<td><p>임의 (디렉터, 디렉터 풀 IP 주소, 프런트 엔드 서버 또는 프런트 엔드 풀 IP 주소로 정의할 수 있음)</p></td>
<td><p>Edge 서버 내부 인터페이스</p></td>
<td><p>아웃 바운드 SIP 트래픽 (디렉터, 디렉터 풀 IP 주소, 프런트 엔드 서버 또는 프런트 엔드 풀 IP 주소)에서 Edge Server 내부 인터페이스로</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5061</p></td>
<td><p>Edge 서버 내부 인터페이스</p></td>
<td><p>임의 (디렉터, 디렉터 풀 IP 주소, 프런트 엔드 서버 또는 프런트 엔드 풀 IP 주소로 정의할 수 있음)</p></td>
<td><p>Edge Server 내부 인터페이스에서 인바운드 SIP 트래픽 (디렉터, 디렉터 풀 IP 주소, 프런트 엔드 서버 또는 프런트 엔드 풀 IP 주소)</p></td>
</tr>
<tr class="even">
<td><p>PSOM/MTLS/TCP/8057</p></td>
<td><p>Any (프런트 엔드 서버 IP 주소 또는 프런트 엔드 풀의 각 프런트 엔드 서버 IP 주소를 정의할 수 있음)</p></td>
<td><p>Edge 서버 내부 인터페이스</p></td>
<td><p>프런트 엔드 서버 또는 풀의 각 프런트 엔드 서버에서 Edge Server 내부 인터페이스로의 웹 회의 트래픽</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5062</p></td>
<td><p>Any (프런트 엔드 서버 IP 주소 또는 프론트 엔드 풀 IP 주소 또는 Survivable Branch 기기 또는이 Edge 서버를 사용 하는 Survivable Branch 서버를 정의할 수 있음)</p></td>
<td><p>Edge 서버 내부 인터페이스</p></td>
<td><p>이 Edge 서버를 사용 하 여 프론트 엔드 서버 또는 프론트 엔드 풀 IP 주소 또는 Survivable Branch 기기 또는 Survivable Branch 서버에서 A/V 사용자 (A/V 인증 서비스) 인증</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/UDP/3478</p></td>
<td><p>이상</p></td>
<td><p>Edge 서버 내부 인터페이스</p></td>
<td><p>내부 및 외부 사용자 간 Survivable Branch 기기 또는 Survivable Branch 서버 간의 A/V 미디어 전송에 대 한 기본 설정 경로</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>이상</p></td>
<td><p>Edge 서버 내부 인터페이스</p></td>
<td><p>내부 및 외부 사용자 간 A/V 미디어 전송의 대체 경로, Survivable Branch 기기 또는 Survivable Branch 서버 UDP 통신을 설정할 수 없는 경우 TCP는 파일 전송 및 데스크톱 공유에 사용 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>Any (중앙 관리 저장소를 보유 하는 프런트 엔드 서버 IP 주소 또는 풀로 정의할 수 있음)</p></td>
<td><p>Edge 서버 내부 인터페이스</p></td>
<td><p>중앙 관리 저장소의 변경 내용을 Edge 서버로 복제</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50001</p></td>
<td><p>이상</p></td>
<td><p>Edge 서버 내부 인터페이스</p></td>
<td><p>Lync Server Management Shell 및 중앙 로깅 서비스 cmdlet, ClsController 명령줄 (ClsController .exe) 또는 에이전트 (Clscontroller .exe) 명령 및 로그 수집을 사용 하는 중앙 로깅 서비스 컨트롤러</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50002</p></td>
<td><p>이상</p></td>
<td><p>Edge 서버 내부 인터페이스</p></td>
<td><p>Lync Server Management Shell 및 중앙 로깅 서비스 cmdlet, ClsController 명령줄 (ClsController .exe) 또는 에이전트 (Clscontroller .exe) 명령 및 로그 수집을 사용 하는 중앙 로깅 서비스 컨트롤러</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50003</p></td>
<td><p>이상</p></td>
<td><p>Edge 서버 내부 인터페이스</p></td>
<td><p>Lync Server Management Shell 및 중앙 로깅 서비스 cmdlet, ClsController 명령줄 (ClsController .exe) 또는 에이전트 (Clscontroller .exe) 명령 및 로그 수집을 사용 하는 중앙 로깅 서비스 컨트롤러</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a>페더레이션에 대 한 방화벽 요약


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
<td><p>MTLS (액세스/SIP)/TCP/5061</p></td>
<td><p>액세스에 지 서비스 공용 IP 주소</p></td>
<td><p>이상</p></td>
<td><p>SIP를 사용 하는 페더레이션 및 공용 IM 연결</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a>방화벽 요약-공용 인스턴트 메시지 연결


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
<td><p>MTLS (액세스/SIP)/TCP/5061</p></td>
<td><p>공용 IM 연결 파트너</p></td>
<td><p>Edge 서버 액세스에 지 서비스</p></td>
<td><p>SIP를 사용 하는 페더레이션 및 공용 IM 연결</p></td>
</tr>
<tr class="even">
<td><p>MTLS (액세스/SIP)/TCP/5061</p></td>
<td><p>Edge 서버 액세스에 지 서비스</p></td>
<td><p>공용 IM 연결 파트너</p></td>
<td><p>SIP를 사용 하는 페더레이션 및 공용 IM 연결</p></td>
</tr>
<tr class="odd">
<td><p>TLS (액세스/SIP)/TCP/443</p></td>
<td><p>클라이언트</p></td>
<td><p>Edge 서버 액세스에 지 서비스</p></td>
<td><p>외부 사용자 액세스를 위한 클라이언트 대 서버 SIP 트래픽</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-59999</p></td>
<td><p>Edge 서버 A/V Edge 서비스</p></td>
<td><p>실시간 메신저 클라이언트</p></td>
<td><p>공용 메신저 연결이 구성 되어 있는 경우 Windows Live Messenger를 사용 하 여 A/V 세션에 사용 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Edge 서버 A/V Edge 서비스</p></td>
<td><p>실시간 메신저 클라이언트</p></td>
<td><p>Windows Live Messenger를 사용 하 여 공용 인스턴트 메시지 연결에 필요 합니다.</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>실시간 메신저 클라이언트</p></td>
<td><p>Edge 서버 A/V Edge 서비스</p></td>
<td><p>Windows Live Messenger를 사용 하 여 공용 인스턴트 메시지 연결에 필요 합니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a>확장 가능한 메시징 및 현재 상태 프로토콜에 대 한 방화벽 요약


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
<th>원본 (IP 주소)</th>
<th>대상 (IP 주소)</th>
<th>메모</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/TCP/5269</p></td>
<td><p>이상</p></td>
<td><p>Edge 서버 액세스에 지 서비스 인터페이스 IP 주소</p></td>
<td><p>XMPP 용 표준 서버 대 서버 통신 포트. 페더레이션된 XMPP 파트너의 Edge 서버 XMPP 프록시에 대 한 통신을 허용 합니다.</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>Edge 서버 액세스에 지 서비스 인터페이스 IP 주소</p></td>
<td><p>이상</p></td>
<td><p>XMPP 용 표준 서버 대 서버 통신 포트. Edge 서버 XMPP 프록시에서 페더레이션된 XMPP 파트너와의 통신을 허용 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>XMPP/MTLS/TCP/23456</p></td>
<td><p>이상</p></td>
<td><p>각 내부에 지 서버 인터페이스 IP</p></td>
<td><p>프런트 엔드 서버 또는 프런트 엔드 풀의 XMPP 게이트웨이에서 Edge Server 내부 IP 주소 또는 각 Edge 풀 구성원의 내부 IP 주소로의 내부 XMPP 트래픽</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

