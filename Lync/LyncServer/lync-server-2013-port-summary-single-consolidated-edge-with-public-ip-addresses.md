---
title: 포트 요약-공용 IP 주소의 단일 통합에 지
description: 포트 요약-공용 IP 주소의 단일 통합에 지입니다.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Single consolidated edge with public IP addresses
ms:assetid: 28407acc-8b92-4f78-875c-fd6b4323b602
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204756(v=OCS.15)
ms:contentKeyID: 48183685
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82ab2d89404fb174994d8e5b798f64bb68768326
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566404"
---
# <a name="port-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a>포트 요약-Lync Server 2013의 공용 IP 주소를 포함 하는 단일 통합에 지

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-21_

이 시나리오 아키텍처에서 설명 하는 Lync Server 2013, Edge Server 기능은 Lync Server 2010에서 구현 된 것과 매우 비슷합니다. 가장 큰 차이점은 XMPP(Extensible Messaging and Presence Protocol)에 대한 포트 **5269 over TCP** 항목이 추가되었다는 점입니다. Lync Server 2013는 선택적으로에 지 서버 또는에 지 풀 및 프런트 엔드 서버 또는 프런트 엔드 풀의 XMPP 게이트웨이 서버에 XMPP 프록시를 배포 합니다. 역방향 프록시와 페더레이션에 대 한 계획 정보는 lync server [2013의 역방향 프록시](lync-server-2013-scenarios-for-reverse-proxy.md) 에 대 한 시나리오와 [lync server 2013 섹션의 SIP, xmpp 페더레이션 및 공용 인스턴트 메시징](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md) 에 대 한 계획에서 찾을 수 있습니다.

이제에 지 서버는 IPv4 외에도 IPv6을 지원 합니다. 명확한 이해를 위해 시나리오에서는 IPv4만 사용됩니다.

**공용 IP 주소 지정을 사용 하는 단일 통합에 지에 대 한 엔터프라이즈 경계 네트워크**

![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")

<div>

## <a name="port-and-protocol-details"></a>포트 및 프로토콜 세부 정보

외부 액세스를 제공하는 기능을 지원하는 데 필요한 포트만 여는 것이 좋습니다.

원격 액세스가 모든 에지 서비스에 대해 작동하도록 하려면 SIP 트래픽이 인바운드/아웃바운드 에지 트래픽 그림에 표시된 대로 양방향으로 이동할 수 있어야 합니다. 즉, 액세스 에지 서비스로의/서비스로부터의 SIP 메시징이 IM(인스턴트 메시징), 현재 상태, 웹 회의, A/V(오디오/비디오) 및 페더레이션에 포함되어야 합니다.

### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-external-interface"></a>공용 IP 주소를 포함하는 단일 통합 에지에 대한 방화벽 요약 정보: 외부 인터페이스

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
<td><p>XMPP/TCP/5269</p></td>
<td><p>모두</p></td>
<td><p>XMPP 프록시 서비스 (액세스에 지 서비스를 사용 하는 공유 IP 주소)</p></td>
<td><p>정의된 XMPP 페더레이션의 XMPP 연락처로부터 들어오는 트래픽을 XMPP 프록시 서비스에서 허용</p></td>
</tr>
<tr class="even">
<td><p>Access/HTTP/TCP/80</p></td>
<td><p>에 지 서버 액세스에 지 서비스 공용 IP 주소</p></td>
<td><p>모두</p></td>
<td><p>인증서 해지/CRL 검사 및 검색</p></td>
</tr>
<tr class="odd">
<td><p>Access/DNS/TCP/53</p></td>
<td><p>에 지 서버 액세스에 지 서비스 공용 IP 주소</p></td>
<td><p>모두</p></td>
<td><p>TCP를 통한 DNS 쿼리</p></td>
</tr>
<tr class="even">
<td><p>Access/DNS/UDP/53</p></td>
<td><p>에 지 서버 액세스에 지 서비스 공용 IP 주소</p></td>
<td><p>모두</p></td>
<td><p>UDP를 통한 DNS 쿼리</p></td>
</tr>
<tr class="odd">
<td><p>TLS (액세스/SIP)/TCP/443</p></td>
<td><p>모두</p></td>
<td><p>에 지 서버 액세스에 지 서비스 공용 IP 주소</p></td>
<td><p>외부 사용자 액세스를 위한 클라이언트-서버 SIP 트래픽</p></td>
</tr>
<tr class="even">
<td><p>MTLS (액세스/SIP)/TCP/5061</p></td>
<td><p>모두</p></td>
<td><p>에 지 서버 액세스에 지 서비스 공용 IP 주소</p></td>
<td><p>SIP를 사용한 페더레이션 및 공용 IM 연결용</p></td>
</tr>
<tr class="odd">
<td><p>MTLS (액세스/SIP)/TCP/5061</p></td>
<td><p>에 지 서버 액세스에 지 서비스 공용 IP 주소</p></td>
<td><p>모두</p></td>
<td><p>SIP를 사용한 페더레이션 및 공용 IM 연결용</p></td>
</tr>
<tr class="even">
<td><p>Web 회의/PSOM (TLS)/TCP/443</p></td>
<td><p>모두</p></td>
<td><p>에 지 서버 웹 회의에 지 서비스 공용 IP 주소</p></td>
<td><p>웹 회의 미디어</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/TCP/50000-59999</p></td>
<td><p>에 지 서버 액세스에 지 서비스 공용 IP 주소</p></td>
<td><p>모두</p></td>
<td><p>Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 및 Lync Server 2013를 실행 하는 파트너와의 페더레이션에 필요 합니다.</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/UDP/50000-59999</p></td>
<td><p>에 지 서버 A/V에 지 서비스 공용 IP 주소</p></td>
<td><p>모두</p></td>
<td><p>Office Communications Server 2007를 실행 하는 파트너와의 페더레이션에만 필요</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/TCP/50000-59999</p></td>
<td><p>모두</p></td>
<td><p>에 지 서버 A/V에 지 서비스 공용 IP 주소</p></td>
<td><p>Office Communications Server 2007를 실행 하는 파트너와의 페더레이션에만 필요 합니다.</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/UDP/50000-59999</p></td>
<td><p>모두</p></td>
<td><p>에 지 서버 A/V에 지 서비스 공용 IP 주소</p></td>
<td><p>Office Communications Server 2007를 실행 하는 파트너와의 페더레이션에만 필요 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>에 지 서버 A/V에 지 서비스 공용 IP 주소</p></td>
<td><p>모두</p></td>
<td><p>3478 아웃 바운드는 Lync Server가 통신 중인에 지 서버 및에 지 서버-에 지 서버에서의 미디어 트래픽에 대 한 버전을 확인 하는 데 사용 됩니다. Lync Server 2010, Windows Live Messenger 및 Office Communications Server 2007 R2와의 페더레이션, 그리고 여러 개의에 지 풀이 회사 내에 배포 된 경우에 필요 합니다.</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>모두</p></td>
<td><p>에 지 서버 A/V에 지 서비스 공용 IP 주소</p></td>
<td><p>UDP/3478을 통한 STUN/TURN 후보 협상</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/TCP/443</p></td>
<td><p>모두</p></td>
<td><p>에 지 서버 A/V에 지 서비스 공용 IP 주소</p></td>
<td><p>TCP/443을 통한 STUN/TURN 후보 협상</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/TCP/443</p></td>
<td><p>에 지 서버 A/V에 지 서비스 공용 IP 주소</p></td>
<td><p>모두</p></td>
<td><p>TCP/443을 통한 후보 STUN/TURN 협상</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-internal-interface"></a>공용 IP 주소를 포함하는 단일 통합 에지에 대한 방화벽 요약 정보: 내부 인터페이스

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Protocol/TCP 또는 UDP/포트</th>
<th>원본 IP 주소</th>
<th>대상 IP 주소</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/MTLS/TCP/23456</p></td>
<td><p>Any (Standard Edition server IP, Standard Edition server IP 주소 또는 XMPP 게이트웨이 서비스를 실행 하는 풀 IP 주소로 정의할 수 있음)</p></td>
<td><p>에 지 서버 내부 인터페이스</p></td>
<td><p>프런트 엔드 서버 또는 프런트 엔드 풀에서 실행 되는 XMPP 게이트웨이 서비스의 아웃 바운드 XMPP 트래픽</p></td>
</tr>
<tr class="even">
<td><p>SIP/MTLS/TCP/5061</p></td>
<td><p>모두 (디렉터, 디렉터 풀 IP 주소, 프런트 엔드 서버 또는 프런트 엔드 풀 IP 주소로 정의할 수 있음)</p></td>
<td><p>내부 인터페이스를 보유 하는에 지 서버 IP 또는 풀</p></td>
<td><p>아웃 바운드 SIP 트래픽 (디렉터, 디렉터 풀 IP 주소, 프런트 엔드 서버 또는 프런트 엔드 풀 IP 주소)에서에 지 서버 내부 인터페이스</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5061</p></td>
<td><p>에 지 서버 내부 인터페이스</p></td>
<td><p>모두 (디렉터, 디렉터 풀 IP 주소, 프런트 엔드 서버 또는 프런트 엔드 풀 주소로 정의할 수 있음)</p></td>
<td><p>에 지 서버 내부 인터페이스에서 디렉터, 디렉터 풀 IP 주소, 프런트 엔드 서버 또는 프런트 엔드 풀 IP 주소에 대 한 인바운드 SIP 트래픽</p></td>
</tr>
<tr class="even">
<td><p>PSOM/MTLS/TCP/8057</p></td>
<td><p>Any (프런트 엔드 서버 IP 주소 또는 프런트 엔드 풀의 각 프런트 엔드 서버 IP 주소로 정의할 수 있음)</p></td>
<td><p>에 지 서버 내부 인터페이스</p></td>
<td><p>프런트 엔드 서버 또는 풀의 각 프런트 엔드 서버에서에 지 서버 내부 인터페이스로의 웹 회의 트래픽</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5062</p></td>
<td><p>Any (프런트 엔드 서버 IP 주소, 또는 프런트 엔드 풀 IP 주소 또는이에 지 서버를 사용 하는 Sba (survivable 분기 서버로 정의할 수 있음)</p></td>
<td><p>에 지 서버 내부 인터페이스</p></td>
<td><p>이에 지 서버를 사용 하 여 프런트 엔드 서버 또는 프런트 엔드 풀 IP 주소 또는 Sba (survivable Branch 기기 또는 Sba (survivable 분기 서버에서 A/V 사용자 인증 (A/V 인증 서비스)</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/UDP/3478</p></td>
<td><p>모두</p></td>
<td><p>에 지 서버 내부 인터페이스</p></td>
<td><p>내부 및 외부 사용자 간의 A/V 미디어 전송에 대 한 기본 설정 경로, Sba (survivable Branch 어플라이언스 또는 Sba (survivable Branch Server</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>모두</p></td>
<td><p>에 지 서버 내부 인터페이스</p></td>
<td><p>내부 및 외부 사용자 간 A/V 미디어 전송에 대 한 대체 경로, Sba (survivable Branch 어플라이언스 또는 Sba (survivable Branch Server UDP 통신을 설정할 수 없는 경우 파일 전송 및 데스크톱 공유에 TCP가 사용 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>Any (프런트 엔드 서버 IP 주소 또는 중앙 관리 저장소를 보유 하는 풀로 정의할 수 있음)</p></td>
<td><p>에 지 서버 내부 인터페이스</p></td>
<td><p>중앙 관리 저장소에서 에지 서버로 변경 내용 복제</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50001</p></td>
<td><p>모두</p></td>
<td><p>에 지 서버 내부 인터페이스</p></td>
<td><p>Lync Server 관리 셸 및 중앙화 된 로깅 서비스 cmdlet, ClsController 명령줄 (ClsController.exe) 또는 에이전트 (ClsAgent.exe) 명령 및 로그 수집을 사용 하는 중앙 로깅 서비스 컨트롤러</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50002</p></td>
<td><p>모두</p></td>
<td><p>에 지 서버 내부 인터페이스</p></td>
<td><p>Lync Server 관리 셸 및 중앙화 된 로깅 서비스 cmdlet, ClsController 명령줄 (ClsController.exe) 또는 에이전트 (ClsAgent.exe) 명령 및 로그 수집을 사용 하는 중앙 로깅 서비스 컨트롤러</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50003</p></td>
<td><p>모두</p></td>
<td><p>에 지 서버 내부 인터페이스</p></td>
<td><p>Lync Server 관리 셸 및 중앙화 된 로깅 서비스 cmdlet, ClsController 명령줄 (ClsController.exe) 또는 에이전트 (ClsAgent.exe) 명령 및 로그 수집을 사용 하는 중앙 로깅 서비스 컨트롤러</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a>페더레이션에 대한 방화벽 요약


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
<td><p>MTLS (액세스/SIP)/TCP/5061</p></td>
<td><p>액세스 에지 서비스 공용 IP 주소</p></td>
<td><p>모두</p></td>
<td><p>SIP를 사용한 페더레이션 및 공용 IM 연결용</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a>방화벽 요약 - 공용 인스턴트 메시징 연결


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
<td><p>MTLS (액세스/SIP)/TCP/5061</p></td>
<td><p>공용 IM 연결 파트너</p></td>
<td><p>에 지 서버 액세스에 지 서비스</p></td>
<td><p>SIP를 사용한 페더레이션 및 공용 IM 연결용</p></td>
</tr>
<tr class="even">
<td><p>MTLS (액세스/SIP)/TCP/5061</p></td>
<td><p>에 지 서버 액세스에 지 서비스</p></td>
<td><p>공용 IM 연결 파트너</p></td>
<td><p>SIP를 사용한 페더레이션 및 공용 IM 연결용</p></td>
</tr>
<tr class="odd">
<td><p>TLS (액세스/SIP)/TCP/443</p></td>
<td><p>클라이언트</p></td>
<td><p>에 지 서버 액세스에 지 서비스</p></td>
<td><p>외부 사용자 액세스를 위한 클라이언트-서버 SIP 트래픽</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-59999</p></td>
<td><p>에 지 서버 A/V에 지 서비스</p></td>
<td><p>Live Messenger 클라이언트</p></td>
<td><p>공용 IM 연결이 구성된 경우 Windows Live Messenger와의 A/V 세션에 사용됨</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>에 지 서버 A/V에 지 서비스</p></td>
<td><p>Live Messenger 클라이언트</p></td>
<td><p>Windows Live Messenger와의 공용 IM 연결 시 필수</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Live Messenger 클라이언트</p></td>
<td><p>에 지 서버 A/V에 지 서비스</p></td>
<td><p>Windows Live Messenger와의 공용 IM 연결 시 필수</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a>확장 가능 메시징 및 현재 상태 프로토콜에 대한 방화벽 요약


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
<th>원본(IP 주소)</th>
<th>대상(IP 주소)</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/TCP/5269</p></td>
<td><p>모두</p></td>
<td><p>에 지 서버 액세스에 지 서비스 인터페이스 IP 주소</p></td>
<td><p>XMPP용 표준 서버 간 통신 포트입니다. 페더레이션 XMPP 파트너의에 지 서버 XMPP 프록시에 대 한 통신을 허용 합니다.</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>에 지 서버 액세스에 지 서비스 인터페이스 IP 주소</p></td>
<td><p>모두</p></td>
<td><p>XMPP용 표준 서버 간 통신 포트입니다. 에 지 서버 XMPP 프록시에서 페더레이션 XMPP 파트너와의 통신을 허용 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>XMPP/MTLS/TCP/23456</p></td>
<td><p>모두</p></td>
<td><p>각 내부에 지 서버 인터페이스 IP</p></td>
<td><p>프런트 엔드 서버 또는 프런트 엔드 풀의 XMPP 게이트웨이에서에 지 서버 내부 IP 주소 또는 각에 지 풀 구성원의 내부 IP 주소로 내부 XMPP 트래픽</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

