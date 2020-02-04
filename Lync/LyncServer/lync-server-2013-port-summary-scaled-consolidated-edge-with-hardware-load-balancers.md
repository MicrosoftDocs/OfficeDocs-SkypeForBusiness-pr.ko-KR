---
title: 포트 요약 - 하드웨어 부하 분산 장치를 사용하는 조정된 통합 에지
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
ms.openlocfilehash: 6260a4ad7f2717e0b4eb2446fc5b17671c3e45a5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725038"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a>Lync Server 2013의 포트 요약 - 하드웨어 부하 분산 장치를 사용하는 조정된 통합 에지

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2015-04-27_

이 시나리오 아키텍처에서 설명 하는 Lync Server 2013, Edge 서버 기능은 Lync Server 2010에서 구현 된 것과 매우 유사 합니다. 가장 주목할 만한 추가 기능은 XMPP (extensible messaging 및 현재 상태 프로토콜)에 대 한 포트 **5269 (TCP over** )입니다. Lync Server 2013는 Edge 서버 또는 Edge 풀의 XMPP 프록시와 프런트 엔드 서버 또는 프런트 엔드 풀의 XMPP 게이트웨이 서버를 선택적으로 배포 합니다.

IPv4 외에도 Edge 서버는 이제 IPv6을 지원 합니다. 명확 하 게 하기 위해 시나리오에 IPv4만 사용 됩니다.

**하드웨어 부하 분산을 사용 하 여 크기가 조정 된 통합 된 가장자리**

![에지 서버 경계 네트워크 포트 및 프로토콜](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "에지 서버 경계 네트워크 포트 및 프로토콜")

<div>

## <a name="port-and-protocol-details"></a>포트 및 프로토콜 정보

외부 액세스를 제공 하는 기능을 지 원하는 데 필요한 포트만을 여는 것이 좋습니다.

모든 edge 서비스에 대 한 원격 액세스의 경우 인바운드/아웃 바운드에 지 트래픽 그림에 표시 된 대로 SIP 트래픽이 directionally으로 이동 하도록 허용 해야 합니다. 또 다른 방법으로, 액세스에 지 서비스에 대 한 SIP 메시징은 인스턴트 메시징 (IM), 현재 상태, 웹 회의, 오디오/비디오 (A/V) 및 페더레이션에 관련 됩니다.

### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-external-interface--node-1-and-node-2-example"></a>축소 된 통합 된 가장자리에 대 한 방화벽 요약, 하드웨어 부하 분산: 외부 인터페이스-노드 1 및 노드 2 (예제)

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
<td><p>Access/HTTP/TCP/80</p></td>
<td><p>Edge 서버 액세스에 지 서비스 공용 IP 주소</p></td>
<td><p>이상</p></td>
<td><p>인증서 해지/i p 확인 및 검색</p></td>
</tr>
<tr class="even">
<td><p>Access/DNS/TCP/53</p></td>
<td><p>Edge 서버 액세스에 지 서비스 공용 IP 주소</p></td>
<td><p>이상</p></td>
<td><p>TCP를 통한 DNS 쿼리</p></td>
</tr>
<tr class="odd">
<td><p>Access/DNS/UDP/53</p></td>
<td><p>Edge 서버 액세스에 지 서비스 공용 IP 주소</p></td>
<td><p>이상</p></td>
<td><p>UDP를 통한 DNS 쿼리</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-59999</p></td>
<td><p>Edge 서버 A/V Edge 서비스 IP 주소</p></td>
<td><p>이상</p></td>
<td><p>Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 및 Lync Server 2013를 실행 하는 파트너와 페더레이션 하는 데 필요 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/UDP/50000-59999</p></td>
<td><p>Edge 서버 A/V Edge 서비스 공용 IP 주소</p></td>
<td><p>이상</p></td>
<td><p>Office Communications Server 2007을 실행 하는 파트너와 페더레이션 하는 경우에만 필요 합니다.</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-59999</p></td>
<td><p>이상</p></td>
<td><p>Edge 서버 A/V Edge 서비스 공용 IP 주소</p></td>
<td><p>Office Communications Server 2007을 실행 하는 파트너와의 페더레이션에만 필요</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/UDP/50000-59999</p></td>
<td><p>이상</p></td>
<td><p>Edge 서버 A/V Edge 서비스 공용 IP 주소</p></td>
<td><p>Office Communications Server 2007을 실행 하는 파트너와의 페더레이션에만 필요</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Edge 서버 A/V Edge 서비스 공용 IP 주소</p></td>
<td><p>이상</p></td>
<td><p>3478 아웃 바운드는 Lync Server와 통신 하는 Edge 서버의 버전과 Edge 서버 간 미디어 소통에 대 한 정보를 확인 하는 데 사용 됩니다. Lync Server 2010, Windows Live Messenger 및 Office Communications Server 2007 R2와 페더레이션 하는 데 필요 하며, 여러 Edge 풀이 회사 내에 배포 된 경우에도 필수적입니다.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>이상</p></td>
<td><p>Edge 서버 A/V Edge 서비스 공용 IP 주소</p></td>
<td><p>STUN/UDP/3478에서 후보자의 협상을 설정 합니다.</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/TCP/443</p></td>
<td><p>이상</p></td>
<td><p>Edge 서버 A/V Edge 서비스 공용 IP 주소</p></td>
<td><p>TCP/443을 통해 후보의 협상을 STUN/설정 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/TCP/443</p></td>
<td><p>Edge 서버 A/V Edge 서비스 공용 IP 주소</p></td>
<td><p>이상</p></td>
<td><p>TCP/443을 통해 후보의 협상을 STUN/설정 합니다.</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-node-1-and-node-2"></a>축소 된 통합 된 가장자리에 대 한 방화벽 요약, 하드웨어 부하 분산: 내부 인터페이스 노드 1 및 노드 2

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
<td><p>XMPP/MTLS/TCP/23456</p></td>
<td><p>Any (프런트 엔드 서버 주소 또는 XMPP 게이트웨이 서비스를 실행 하는 프런트 엔드 풀 가상 IP 주소로 정의할 수 있음)</p></td>
<td><p>Edge 서버 내부 인터페이스</p></td>
<td><p>프런트 엔드 서버 또는 프런트 엔드 풀에서 실행 되는 XMPP 게이트웨이 서비스의 아웃 바운드 XMPP 트래픽</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>Any (중앙 관리 저장소를 보유 하는 프런트 엔드 서버 서버 IP 또는 풀로 정의할 수 있음)</p></td>
<td><p>Edge 서버 내부 인터페이스</p></td>
<td><p>중앙 관리 저장소의 변경 내용을 Edge 서버로 복제</p></td>
</tr>
<tr class="odd">
<td><p>PSOM/MTLS/TCP/8057</p></td>
<td><p>임의 (디렉터 IP, 프런트 엔드 서버 IP 또는 풀 가상 IP로 정의할 수 있음)</p></td>
<td><p>Edge 서버 내부 인터페이스</p></td>
<td><p>내부 배포에서 내부에 지 서버 인터페이스로 웹 회의 소통량</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/UDP/3478</p></td>
<td><p>임의 (디렉터 IP, 프런트 엔드 서버 IP 또는 풀 가상 IP로 정의할 수 있음)</p></td>
<td><p>Edge 서버 내부 인터페이스</p></td>
<td><p>내부 및 외부 사용자 간 Survivable Branch 기기 또는 Survivable Branch 서버 간의 A/V 미디어 전송에 대 한 기본 설정 경로</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>임의 (디렉터 IP, 프런트 엔드 서버 IP 또는 풀 가상 IP로 정의할 수 있음)</p></td>
<td><p>Edge 서버 내부 인터페이스</p></td>
<td><p>내부 및 외부 사용자 간 A/V 미디어 전송의 대체 경로, Survivable Branch 기기 또는 Survivable Branch 서버 UDP 통신을 설정할 수 없는 경우 TCP는 파일 전송 및 데스크톱 공유에 사용 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50001</p></td>
<td><p>이상</p></td>
<td><p>Edge 서버 내부 인터페이스</p></td>
<td><p>Lync Server Management Shell 및 중앙 로깅 서비스 cmdlet, ClsController 명령줄 (ClsController .exe) 또는 에이전트 (Clscontroller .exe) 명령 및 로그 수집을 사용 하는 중앙 로깅 서비스 컨트롤러</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50002</p></td>
<td><p>이상</p></td>
<td><p>Edge 서버 내부 인터페이스</p></td>
<td><p>Lync Server Management Shell 및 중앙 로깅 서비스 cmdlet, ClsController 명령줄 (ClsController .exe) 또는 에이전트 (Clscontroller .exe) 명령 및 로그 수집을 사용 하는 중앙 로깅 서비스 컨트롤러</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50003</p></td>
<td><p>이상</p></td>
<td><p>Edge 서버 내부 인터페이스</p></td>
<td><p>Lync Server Management Shell 및 중앙 로깅 서비스 cmdlet, ClsController 명령줄 (ClsController .exe) 또는 에이전트 (Clscontroller .exe) 명령 및 로그 수집을 사용 하는 중앙 로깅 서비스 컨트롤러</p></td>
</tr>
</tbody>
</table>


하드웨어 로드 균형 조정기에는 Lync Server에 대 한 가용성 및 부하 분산을 제공 하기 위해 배포 되는 특정 요구 사항이 있습니다. 요구 사항은 다음 그림과 표에 정의 되어 있습니다. 제 3 자 공급 업체는 여기에 정의 된 요구 사항에 대해 다른 용어를 사용할 수 있습니다. Lync Server의 요구 사항을 하드웨어 부하 분산 장치 공급 업체에서 제공 하는 기능 및 구성 옵션에 매핑하는 것이 필요 합니다.

하드웨어 부하 분산 장치를 구성할 때 다음 요구 사항을 고려 하세요.

  - HLB (하드웨어 부하 분산 장치)에서 액세스에 지 서비스 및 웹 회의에 지 서비스에 대 한 원본 네트워크 주소 변환 (SNAT)을 구성할 수 있습니다.

  - SNAT은 A/V에 지 서비스에 대해 구성할 수 없습니다. A/V Edge 서비스는 HLB (STUN) over NAT를 사용 하 여 UDP의 단순 트래버스를 위한 VIP (가상 IP)가 아닌 실제 서버 주소로 응답 해야 하며, 릴레이 NAT (TURN)/페더레이션 회전 (FTURN)을 올바르게 작동 하려면
    
      - 클라이언트가 HLB에 대 한 요청을 보내는 경우, HLB VIP에서 응답을 다시 가져와야 합니다.
    
      - 클라이언트가 Edge에 요청을 보내는 경우에는 Edge IP에서 응답을 다시 가져와야 합니다.

  - 공용 IP 주소는 각 서버 인터페이스와 HLB의 Vip에 사용 되며, 공용 IP 주소 요구 사항은 N + 1 이며 각 실제 서버 인터페이스에 대 한 공용 IP 주소와 각 HLB VIP에 대해 하나씩 있습니다. 풀에 두 개의 Edge 서버가 있는 경우,이는 HLB Vip에 3이 사용 되 고 각 Edge 서버 인터페이스 (서버에 대해 총 6 개)에 대해 9 개의 공용 IP 주소를 반환 합니다.

  - 액세스에 지 서비스 및 웹 회의에 지 서비스의 경우, 클라이언트가 VIP에 접속 하 여 VIP가 클라이언트에서 자신의 IP 주소로 원본 IP 주소를 변경 합니다. 서버 인터페이스는 VIP로 반환 주소를 처리 하 고, VIP는 서버 인터페이스 IP 주소에서 원본 주소를 변경 하 고 패킷을 클라이언트로 보냅니다.

  - A/V Edge 서비스의 경우 VIP는 원본 IP 주소를 변경 하지 않아야 하며, 실제 서버 주소는 클라이언트에 직접 반환 되며, AV 트래픽에 대 한 HLB에서 NAT를 구성할 수 없습니다.
    
      - 클라이언트가 HLB VIP에 대 한 요청을 보내는 경우, HLB VIP에서 응답을 다시 가져와야 합니다.
    
      - 클라이언트가 Edge IP에 요청을 보내는 경우에는 Edge IP에서 응답을 다시 가져와야 합니다.

  - AV의 경우 외부 방화벽은 모든 패킷에 대 한 실제 서버 공개 IP 주소를 유지 합니다.

  - 일단 설정한 후에는 클라이언트가 A/V Edge 서비스 통신을 HLB 아닌 실제 서버에 게 전달 됩니다.

  - 내부에 지 내부 서버 및 클라이언트는 라우팅 되어야 하 고, 서버 또는 클라이언트를 호스트 하는 모든 내부 네트워크에 대해 영구 경로가 설정 됩니다.

  - HLB 액세스에 지 서비스 VIP가 각 Edge 서버 인터페이스에 대 한 기본 게이트웨이의 역할을 합니다.

<div>


> [!NOTE]
> NAT 계획 및 기능에 대 한 자세한 내용은 <A href="lync-server-2013-hardware-load-balancer-requirements.md">Lync Server 2013의 하드웨어 부하 분산 장치 요구 사항</A>을 참조 하세요.



</div>

![에지 서버 포트 및 프로토콜 세부 정보](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "에지 서버 포트 및 프로토콜 세부 정보")

### <a name="external-port-settings-required-for-scaled-consolidated-edge-hardware-load-balanced-external-interface-virtual-ips"></a>크기가 조정 된 통합 된 가장자리에 필요한 외부 포트 설정, 하드웨어 부하 분산: 외부 인터페이스 가상 Ip

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
<td><p>TLS (액세스/SIP)/TCP/443</p></td>
<td><p>이상</p></td>
<td><p>액세스에 지 서비스 공용 VIP 주소</p></td>
<td><p>외부 사용자 액세스를 위한 클라이언트 대 서버 SIP 트래픽</p></td>
</tr>
<tr class="even">
<td><p>MTLS (액세스/SIP)/TCP/5061</p></td>
<td><p>이상</p></td>
<td><p>액세스에 지 서비스 공용 VIP 주소</p></td>
<td><p>SIP를 사용 하 여 SIP 신호, 페더레이션 및 공용 인스턴트 메시지 연결</p></td>
</tr>
<tr class="odd">
<td><p>MTLS (액세스/SIP)/TCP/5061</p></td>
<td><p>액세스에 지 서비스 공용 VIP 주소</p></td>
<td><p>페더레이션 파트너</p></td>
<td><p>SIP를 사용 하 여 SIP 신호, 페더레이션 및 공용 인스턴트 메시지 연결</p></td>
</tr>
<tr class="even">
<td><p>웹 회의/PSOM (TLS)/TCP/443</p></td>
<td><p>이상</p></td>
<td><p>Edge 서버 웹 회의에 지 서비스 공개 VIP 주소</p></td>
<td><p>웹 회의 미디어</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>이상</p></td>
<td><p>Edge 서버 A/V Edge 서비스 공개 VIP 주소</p></td>
<td><p>STUN/UDP/3478에서 후보자의 협상을 설정 합니다.</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/TCP/443</p></td>
<td><p>이상</p></td>
<td><p>Edge 서버 A/V Edge 서비스 공개 VIP 주소</p></td>
<td><p>TCP/443을 통해 후보의 협상을 STUN/설정 합니다.</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-virtual-ips"></a>축소 된 통합 된 가장자리에 대 한 방화벽 요약, 하드웨어 부하 분산: 내부 인터페이스 가상 Ip

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
<td><p>임의 (디렉터, 디렉터 풀 가상 IP 주소, 프런트 엔드 서버 또는 프런트 엔드 풀 가상 IP 주소로 정의할 수 있음)</p></td>
<td><p>Edge 서버 내부 VIP 인터페이스</p></td>
<td><p>아웃 바운드 SIP 트래픽 (디렉터, 디렉터 풀 가상 IP 주소, 프런트 엔드 서버 또는 프런트 엔드 풀 가상 IP 주소)에서 내부 경계 VIP로</p></td>
</tr>
<tr class="even">
<td><p>MTLS (액세스/SIP)/TCP/5061</p></td>
<td><p>Edge 서버 내부 VIP 인터페이스</p></td>
<td><p>임의 (디렉터, 디렉터 풀 가상 IP 주소, 프런트 엔드 서버 또는 프런트 엔드 풀 가상 IP 주소로 정의할 수 있음)</p></td>
<td><p>Edge Server 내부 인터페이스에서 인바운드 SIP 트래픽 (디렉터, 디렉터 풀 가상 IP 주소, 프런트 엔드 서버 또는 프런트 엔드 풀 가상 IP 주소)</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5062</p></td>
<td><p>Any (프런트 엔드 서버 IP 주소 또는 프론트 엔드 풀 IP 주소 또는 Survivable Branch 기기 또는이 Edge 서버를 사용 하는 Survivable Branch 서버를 정의할 수 있음)</p></td>
<td><p>Edge 서버 내부 VIP 인터페이스</p></td>
<td><p>이 Edge 서버를 사용 하 여 프론트 엔드 서버 또는 프론트 엔드 풀 IP 주소 또는 Survivable Branch 기기 또는 Survivable Branch 서버에서 A/V 사용자 (A/V 인증 서비스) 인증</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/UDP/3478</p></td>
<td><p>이상</p></td>
<td><p>Edge 서버 내부 VIP 인터페이스</p></td>
<td><p>내부 및 외부 사용자 간의 A/V 미디어 전송에 대 한 기본 경로</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>이상</p></td>
<td><p>Edge 서버 내부 VIP 인터페이스</p></td>
<td><p>내부 및 외부 사용자 간 A/V 미디어 전송에 대 한 대체 경로 UDP 통신을 설정할 수 없는 경우 파일 전송 및 데스크톱 공유에 TCP가 사용 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>Edge 서버 내부 VIP 인터페이스</p></td>
<td><p>이상</p></td>
<td><p>내부 및 외부 사용자 간 A/V 미디어 전송에 대 한 대체 경로 UDP 통신을 설정할 수 없는 경우 파일 전송 및 데스크톱 공유에 TCP가 사용 됩니다.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

