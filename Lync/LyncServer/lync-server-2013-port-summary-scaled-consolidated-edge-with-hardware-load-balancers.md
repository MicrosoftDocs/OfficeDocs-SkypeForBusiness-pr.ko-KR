---
title: 포트 요약-하드웨어 부하 분산 장치로 확장 된 통합에 지
description: 포트 요약-하드웨어 부하 분산 장치로 확장 된 통합에 지
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Scaled consolidated edge with hardware load balancers
ms:assetid: 91213b1e-f875-464b-83e8-fe3a351595a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398739(v=OCS.15)
ms:contentKeyID: 48184841
ms.date: 04/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1a03acb3644d83669bcf0065ebb20c526ef5fa32
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564594"
---
# <a name="port-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a>포트 요약-Lync Server 2013의 하드웨어 부하 분산 장치로 확장 된 통합에 지

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2015-04-27_

이 시나리오 아키텍처에서 설명 하는 Lync Server 2013, Edge Server 기능은 Lync Server 2010에서 구현 된 것과 매우 비슷합니다. 가장 큰 차이점은 XMPP(Extensible Messaging and Presence Protocol)에 대한 포트 **5269 over TCP** 항목이 추가되었다는 점입니다. Lync Server 2013는 선택적으로에 지 서버 또는에 지 풀 및 프런트 엔드 서버 또는 프런트 엔드 풀의 XMPP 게이트웨이 서버에 XMPP 프록시를 배포 합니다.

이제에 지 서버는 IPv4 외에도 IPv6을 지원 합니다. 명확한 이해를 위해 시나리오에서는 IPv4만 사용됩니다.

**하드웨어 부하 분산을 사용 하 여 확장 된 통합에 지**

![에 지 서버 경계 네트워크 포트 및 프로토콜](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "에 지 서버 경계 네트워크 포트 및 프로토콜")

<div>

## <a name="port-and-protocol-details"></a>포트 및 프로토콜 세부 정보

외부 액세스를 제공할 기능을 지원하는 데 필요한 포트만 여는 것이 좋습니다.

원격 액세스가 에지 서비스에 작동하려면 SIP 트래픽이 인바운드/아웃바운드 에지 트래픽 그림에서처럼 양방향으로 전달될 수 있어야 합니다. 다른 방식으로 시작될 경우, 액세스 에지 서비스와 주고 받는 SIP 메시징에는 IM(인스턴트 메시징), 현재 상태, 웹 회의, A/V(오디오/비디오) 및 페더레이션이 수반됩니다.

### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-external-interface--node-1-and-node-2-example"></a>확장 통합에 지에 대 한 방화벽 요약, 하드웨어 부하 분산: 외부 인터페이스-노드 1 및 노드 2 (예제)

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
<td><p>Access/HTTP/TCP/80</p></td>
<td><p>에 지 서버 액세스에 지 서비스 공용 IP 주소</p></td>
<td><p>모두</p></td>
<td><p>인증서 해지/CRL 검사 및 검색</p></td>
</tr>
<tr class="even">
<td><p>Access/DNS/TCP/53</p></td>
<td><p>에 지 서버 액세스에 지 서비스 공용 IP 주소</p></td>
<td><p>모두</p></td>
<td><p>TCP를 통한 DNS 쿼리</p></td>
</tr>
<tr class="odd">
<td><p>Access/DNS/UDP/53</p></td>
<td><p>에 지 서버 액세스에 지 서비스 공용 IP 주소</p></td>
<td><p>모두</p></td>
<td><p>UDP를 통한 DNS 쿼리</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-59999</p></td>
<td><p>에 지 서버 A/V에 지 서비스 IP 주소</p></td>
<td><p>모두</p></td>
<td><p>Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 및 Lync Server 2013를 실행 하는 파트너와의 페더레이션에 필요 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/UDP/50000-59999</p></td>
<td><p>에 지 서버 A/V에 지 서비스 공용 IP 주소</p></td>
<td><p>모두</p></td>
<td><p>Office Communications Server 2007를 실행 하는 파트너와의 페더레이션에만 필요 합니다.</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-59999</p></td>
<td><p>모두</p></td>
<td><p>에 지 서버 A/V에 지 서비스 공용 IP 주소</p></td>
<td><p>Office Communications Server 2007를 실행 하는 파트너와의 페더레이션에만 필요</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/UDP/50000-59999</p></td>
<td><p>모두</p></td>
<td><p>에 지 서버 A/V에 지 서비스 공용 IP 주소</p></td>
<td><p>Office Communications Server 2007를 실행 하는 파트너와의 페더레이션에만 필요</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>에 지 서버 A/V에 지 서비스 공용 IP 주소</p></td>
<td><p>모두</p></td>
<td><p>3478 아웃 바운드는 Lync Server가 통신 중인에 지 서버 및에 지 서버-에 지 서버에서의 미디어 트래픽에 대 한 버전을 확인 하는 데 사용 됩니다. Lync Server 2010, Windows Live Messenger 및 Office Communications Server 2007 R2와의 페더레이션, 그리고 여러 개의에 지 풀이 회사 내에 배포 된 경우에 필요 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>모두</p></td>
<td><p>에 지 서버 A/V에 지 서비스 공용 IP 주소</p></td>
<td><p>UDP/3478을 통한 STUN/TURN 후보 협상</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/TCP/443</p></td>
<td><p>모두</p></td>
<td><p>에 지 서버 A/V에 지 서비스 공용 IP 주소</p></td>
<td><p>TCP/443을 통한 STUN/TURN 후보 협상</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/TCP/443</p></td>
<td><p>에 지 서버 A/V에 지 서비스 공용 IP 주소</p></td>
<td><p>모두</p></td>
<td><p>TCP/443을 통한 STUN/TURN 후보 협상</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-node-1-and-node-2"></a>확장 통합에 지에 대 한 방화벽 요약, 하드웨어 부하 분산: 내부 인터페이스 노드 1 및 노드 2

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
<td><p>XMPP/MTLS/TCP/23456</p></td>
<td><p>Any (프런트 엔드 서버 주소 또는 XMPP 게이트웨이 서비스를 실행 하는 프런트 엔드 풀 가상 IP 주소로 정의할 수 있음)</p></td>
<td><p>에 지 서버 내부 인터페이스</p></td>
<td><p>프런트 엔드 서버 또는 프런트 엔드 풀에서 실행 되는 XMPP 게이트웨이 서비스의 아웃 바운드 XMPP 트래픽</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>Any (중앙 관리 저장소를 포함 하는 프런트 엔드 서버 서버 IP 또는 풀로 정의 가능)</p></td>
<td><p>에지 서버 내부 인터페이스</p></td>
<td><p>중앙 관리 저장소에서 에지 서버로 변경 내용 복제</p></td>
</tr>
<tr class="odd">
<td><p>PSOM/MTLS/TCP/8057</p></td>
<td><p>모두 (디렉터 IP, 프런트 엔드 서버 IP 또는 풀 가상 IP로 정의할 수 있음)</p></td>
<td><p>에지 서버 내부 인터페이스</p></td>
<td><p>내부 배포에서 내부 에지 서버 인터페이스로의 웹 회의 트래픽</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/UDP/3478</p></td>
<td><p>모두 (디렉터 IP, 프런트 엔드 서버 IP 또는 풀 가상 IP로 정의할 수 있음)</p></td>
<td><p>에지 서버 내부 인터페이스</p></td>
<td><p>내부 및 외부 사용자 간의 A/V 미디어 전송에 대 한 기본 설정 경로, Sba (survivable Branch 어플라이언스 또는 Sba (survivable Branch Server</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>모두 (디렉터 IP, 프런트 엔드 서버 IP 또는 풀 가상 IP로 정의할 수 있음)</p></td>
<td><p>에지 서버 내부 인터페이스</p></td>
<td><p>내부 및 외부 사용자 간 A/V 미디어 전송에 대 한 대체 경로, Sba (survivable Branch 어플라이언스 또는 Sba (survivable Branch Server UDP 통신을 설정할 수 없는 경우 파일 전송 및 데스크톱 공유에 TCP가 사용 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50001</p></td>
<td><p>모두</p></td>
<td><p>에 지 서버 내부 인터페이스</p></td>
<td><p>Lync Server 관리 셸 및 중앙화 된 로깅 서비스 cmdlet, ClsController 명령줄 (ClsController.exe) 또는 에이전트 (ClsAgent.exe) 명령 및 로그 수집을 사용 하는 중앙 로깅 서비스 컨트롤러</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50002</p></td>
<td><p>모두</p></td>
<td><p>에 지 서버 내부 인터페이스</p></td>
<td><p>Lync Server 관리 셸 및 중앙화 된 로깅 서비스 cmdlet, ClsController 명령줄 (ClsController.exe) 또는 에이전트 (ClsAgent.exe) 명령 및 로그 수집을 사용 하는 중앙 로깅 서비스 컨트롤러</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50003</p></td>
<td><p>모두</p></td>
<td><p>에 지 서버 내부 인터페이스</p></td>
<td><p>Lync Server 관리 셸 및 중앙화 된 로깅 서비스 cmdlet, ClsController 명령줄 (ClsController.exe) 또는 에이전트 (ClsAgent.exe) 명령 및 로그 수집을 사용 하는 중앙 로깅 서비스 컨트롤러</p></td>
</tr>
</tbody>
</table>


하드웨어 부하 분산 장치는 Lync Server에 대 한 가용성 및 부하 분산을 제공 하기 위해 배포할 때 특정 요구 사항을 충족 합니다. 요구 사항은 다음 그림 및 표에 정의 되어 있습니다. 타사 공급 업체는 여기에 정의 된 요구 사항에 서로 다른 용어를 사용할 수 있습니다. Lync Server의 요구 사항을 하드웨어 부하 분산 장치 공급 업체에서 제공 하는 기능 및 구성 옵션에 매핑해야 합니다.

하드웨어 부하 분산 장치를 구성 하는 경우 다음 요구 사항을 고려 하십시오.

  - 액세스에 지 서비스 및 웹 회의에 지 서비스에 대 한 HLB (하드웨어 부하 분산 장치)에서 원본 네트워크 주소 변환 (SNAT)을 구성할 수 있습니다.

  - SNAT가 A/V에 지 서비스에서 구성 될 수 없음-A/V에 지 서비스는 HLB VIP (가상 IP)가 아니라 실제 서버 주소를 사용 하 여 응답 해야 하며, STUN (relay NAT를 통한 UDP (TURN)/페더레이션 사용 (FTURN)이 정상적으로 작동 하려면이를 수행 합니다.
    
      - 클라이언트가 HLB에 요청을 보내면 응답은 HLB VIP에서 반환 되어야 합니다.
    
      - 클라이언트가 Edge에 요청을 보내면 응답은에 지 IP에서 반환 되어야 합니다.

  - 공용 IP 주소는 각 서버 인터페이스 및 HLB의 Vip에서 사용 되며, 공용 ip 주소 요구 사항은 N + 1 이며 각 실제 서버 인터페이스에 대 한 공용 IP 주소와 각 HLB VIP에 대해 하나씩 있습니다. 풀에에 두 개의에 지 서버가 있는 경우에는 HLB Vip에 대해 3이 사용 되 고 각에 지 서버 인터페이스 (서버에 대 한 총 6 개)에 대해 9 개의 공용 IP 주소가 생성 됩니다.

  - 액세스에 지 서비스 및 웹 회의에 지 서비스의 경우와 HLB에서 NAT를 사용 하는 경우 클라이언트는 VIP에 연결 하 고, VIP는 클라이언트의 원본 IP 주소를 자체 IP 주소로 변경 합니다. 서버 인터페이스는 보낸 사람 주소를 VIP로, VIP는 서버 인터페이스 IP 주소에서 원본 주소를 변경 하 고 해당 패킷을 클라이언트에 게 전송 합니다.

  - A/V에 지 서비스의 경우 VIP가 원본 IP 주소를 변경 하지 않아야 하며, 실제 서버 주소가 클라이언트에 직접 반환 되며, AV 트래픽에 대해 HLB에 NAT를 구성할 수 없습니다.
    
      - 클라이언트가 HLB VIP로 요청을 보내면 응답은 HLB VIP에서 반환 되어야 합니다.
    
      - 클라이언트에서에 지 IP로 요청을 전송 하는 경우에는에 지 IP에서 응답을 다시 받아야 합니다.

  - AV의 경우 외부 방화벽은 모든 패킷에 대해 실제 서버 공용 IP 주소를 유지 합니다.

  - 일단 설정 되 면 클라이언트에서 A/V에 지 서비스 통신은 HLB가 아니라 실제 서버에 연결 됩니다.

  - 내부에 지/내부 서버 및 클라이언트를 라우팅해야 하며, 서버 또는 클라이언트를 호스트 하는 모든 내부 네트워크에 대해 영구 경로가 설정 되어 있어야 합니다.

  - HLB 액세스에 지 서비스 VIP가 각에 지 서버 인터페이스에 대 한 기본 게이트웨이 역할을 합니다.

<div>


> [!NOTE]
> NAT 계획 및 기능에 대 한 자세한 내용은 <A href="lync-server-2013-hardware-load-balancer-requirements.md">Lync Server 2013의 하드웨어 부하 분산 장치 요구 사항을</A>참조 하세요.



</div>

![에 지 서버 포트 및 프로토콜 세부 정보](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "에 지 서버 포트 및 프로토콜 세부 정보")

### <a name="external-port-settings-required-for-scaled-consolidated-edge-hardware-load-balanced-external-interface-virtual-ips"></a>확장 통합에 지에 필요한 외부 포트 설정, 하드웨어 부하 분산: 외부 인터페이스 가상 Ip

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
<td><p>XMPP/TCP/5269</p></td>
<td><p>XMPP 프록시 서비스 (액세스에 지 서비스를 사용 하는 공유 IP 주소)</p></td>
<td><p>모두</p></td>
<td><p>XMPP 프록시 서비스는 정의 된 XMPP 페더레이션에서 XMPP 연락처로 트래픽을 보냅니다.</p></td>
</tr>
<tr class="odd">
<td><p>TLS (액세스/SIP)/TCP/443</p></td>
<td><p>모두</p></td>
<td><p>액세스에 지 서비스 공용 VIP 주소</p></td>
<td><p>외부 사용자 액세스를 위한 클라이언트-서버 SIP 트래픽</p></td>
</tr>
<tr class="even">
<td><p>MTLS (액세스/SIP)/TCP/5061</p></td>
<td><p>모두</p></td>
<td><p>액세스에 지 서비스 공용 VIP 주소</p></td>
<td><p>Sip를 사용한 SIP 신호, 페더레이션 및 공용 IM 연결</p></td>
</tr>
<tr class="odd">
<td><p>MTLS (액세스/SIP)/TCP/5061</p></td>
<td><p>액세스에 지 서비스 공용 VIP 주소</p></td>
<td><p>페더레이션 파트너</p></td>
<td><p>Sip를 사용한 SIP 신호, 페더레이션 및 공용 IM 연결</p></td>
</tr>
<tr class="even">
<td><p>Web 회의/PSOM (TLS)/TCP/443</p></td>
<td><p>모두</p></td>
<td><p>에 지 서버 웹 회의에 지 서비스 공용 VIP 주소</p></td>
<td><p>웹 회의 미디어</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>모두</p></td>
<td><p>에 지 서버 A/V에 지 서비스 공용 VIP 주소</p></td>
<td><p>UDP/3478을 통한 STUN/TURN 후보 협상</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/TCP/443</p></td>
<td><p>모두</p></td>
<td><p>에 지 서버 A/V에 지 서비스 공용 VIP 주소</p></td>
<td><p>TCP/443을 통한 STUN/TURN 후보 협상</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-virtual-ips"></a>확장 통합에 지에 대 한 방화벽 요약, 하드웨어 부하 분산: 내부 인터페이스 가상 Ip

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
<td><p>모두 (디렉터, 디렉터 풀 가상 IP 주소, 프런트 엔드 서버 또는 프런트 엔드 풀 가상 IP 주소로 정의할 수 있음)</p></td>
<td><p>에 지 서버 내부 VIP 인터페이스</p></td>
<td><p>내부에 지 VIP로의 아웃 바운드 SIP 트래픽 (디렉터, 디렉터 풀 가상 IP 주소, 프런트 엔드 서버 또는 프런트 엔드 풀 가상 IP 주소)</p></td>
</tr>
<tr class="even">
<td><p>MTLS (액세스/SIP)/TCP/5061</p></td>
<td><p>에 지 서버 내부 VIP 인터페이스</p></td>
<td><p>모두 (디렉터, 디렉터 풀 가상 IP 주소, 프런트 엔드 서버 또는 프런트 엔드 풀 가상 IP 주소로 정의할 수 있음)</p></td>
<td><p>에 지 서버 내부 인터페이스에서 디렉터, 디렉터 풀 가상 IP 주소, 프런트 엔드 서버 또는 프런트 엔드 풀 가상 IP 주소에 대 한 인바운드 SIP 트래픽</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5062</p></td>
<td><p>Any (프런트 엔드 서버 IP 주소, 또는 프런트 엔드 풀 IP 주소 또는이에 지 서버를 사용 하는 Sba (survivable 분기 서버로 정의할 수 있음)</p></td>
<td><p>에 지 서버 내부 VIP 인터페이스</p></td>
<td><p>이에 지 서버를 사용 하 여 프런트 엔드 서버 또는 프런트 엔드 풀 IP 주소 또는 Sba (survivable Branch 기기 또는 Sba (survivable 분기 서버에서 A/V 사용자 인증 (A/V 인증 서비스)</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/UDP/3478</p></td>
<td><p>모두</p></td>
<td><p>에 지 서버 내부 VIP 인터페이스</p></td>
<td><p>내부 사용자와 외부 사용자 간의 A/V 미디어 전송을 위한 기본 경로</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>모두</p></td>
<td><p>에 지 서버 내부 VIP 인터페이스</p></td>
<td><p>UDP 통신을 설정할 수 없는 경우 내부 사용자와 외부 사용자 간 A/V 미디어 전송을 위한 대체 경로, TCP는 파일 전송 및 데스크톱 공유용으로 사용됨</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>에 지 서버 내부 VIP 인터페이스</p></td>
<td><p>모두</p></td>
<td><p>UDP 통신을 설정할 수 없는 경우 내부 사용자와 외부 사용자 간 A/V 미디어 전송을 위한 대체 경로, TCP는 파일 전송 및 데스크톱 공유용으로 사용됨</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

