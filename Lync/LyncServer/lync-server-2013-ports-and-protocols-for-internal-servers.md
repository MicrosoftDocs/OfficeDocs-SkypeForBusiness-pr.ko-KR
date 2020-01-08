---
title: 'Lync Server 2013: 내부 서버용 포트 및 프로토콜'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Ports and protocols for internal servers
ms:assetid: c94063f1-e802-4a61-be90-022fc185335e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398833(v=OCS.15)
ms:contentKeyID: 48185402
ms.date: 04/06/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 026843216e433ebea120384209ed90f38be3437b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983858"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ports-and-protocols-for-internal-servers-in-lync-server-2013"></a>Lync Server 2013의 내부 서버에 대 한 포트 및 프로토콜

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2016-04-06_

이 섹션에서는 서버, 부하 분산 장치 및 Lync Server 배포의 클라이언트에 사용 되는 포트와 프로토콜에 대해 간략하게 설명 합니다.

<div>


> [!IMPORTANT]  
> 1 ~ 1 통신에 참가 하는 Lync 및 Communicator 클라이언트는 종종 피어 투 피어 라고 합니다. 기술적으로 두 클라이언트는 중앙의 IMMCU (지점 제어 단위)를 사용 하 여 일대일 대화로 통신 합니다. IMMCU는 프런트 엔드 서버의 구성 요소입니다. 필요한 통신 워크플로에 IMMCU를 배치 하면 프런트 엔드 서버에서 사용할 수 있는 통화 정보 기록 및 기타 기능을 사용할 수 있습니다. 클라이언트의 동적 원본 포트에서 프런트 엔드 서버 포트 TLS/TCP/5061으로 통신 하는 것으로 간주 됩니다 (권장 전송 계층 보안을 사용 하는 경우). Lync Server와 IMMCU가 활성 상태이 고 사용할 수 있는 경우에만 피어 투 피어 통신 및 여러 파티 IM을 디자인할 수 있습니다.



</div>

<div>

## <a name="port-and-protocol-details"></a>포트 및 프로토콜 정보

<div>


> [!NOTE]  
> Lync server가 방화벽에서 필요한 포트를 여는 경우에는 서버에서 Lync Server 서비스를 시작 하기 전에 Windows 방화벽이 실행 중 이어야 합니다.



</div>

Edge 구성 요소의 방화벽 구성에 대 한 자세한 내용은 [Lync Server 2013에 대 한 외부 A/V 방화벽 및 포트 요구 사항 결정](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)을 참조 하세요.

다음 표에는 각 내부 서버 역할에 열려 있어야 하는 포트가 나열 되어 있습니다.

### <a name="required-server-ports-by-server-role"></a>필요한 서버 포트 (서버 역할별)

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>서버 역할</th>
<th>서비스 이름</th>
<th>포트</th>
<th>프로토콜별</th>
<th>상속자</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>모든 서버</p></td>
<td><p>SQL 브라우저</p></td>
<td><p>1434</p></td>
<td><p>UDP</p></td>
<td><p>중앙 관리 저장소 데이터베이스의 복제 된 로컬 복사본에 대 한 SQL 브라우저입니다.</p></td>
</tr>
<tr class="even">
<td><p>프런트 엔드 서버</p></td>
<td><p>Lync Server 프런트 엔드 서비스</p></td>
<td><p>5060</p></td>
<td><p>NET.TCP</p></td>
<td><p>필요에 따라 원격 통화 제어 서버와 같은 신뢰할 수 있는 서비스에 대 한 고정 경로에 대 한 표준 버전 서버 및 프런트 엔드 서버에서 사용 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>프런트 엔드 서버</p></td>
<td><p>Lync Server 프런트 엔드 서비스</p></td>
<td><p>5061</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>서버와 클라이언트 (MTLS) 간의 SIP 통신 및 프런트 엔드 서버와 조정 서버 (MTLS) 간의 SIP 통신에 대 한 모든 내부 SIP 통신에 대 한 표준 버전 서버 및 프런트 엔드 풀에 사용 됩니다. 모니터링 서버와 통신 하는 데도 사용 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>프런트 엔드 서버</p></td>
<td><p>Lync Server 프런트 엔드 서비스</p></td>
<td><p>444</p></td>
<td><p>HTTPS</p>
<p>NET.TCP</p></td>
<td><p>포커스 (회의 상태를 관리 하는 Lync Server 구성 요소)와 개별 서버 간의 HTTPS 통신에 사용 됩니다.</p>
<p>이 포트는 Survivable Branch 기기 및 프런트 엔드 서버 간의 TCP 통신에도 사용 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>프런트 엔드 서버</p></td>
<td><p>Lync Server 프런트 엔드 서비스</p></td>
<td><p>135</p></td>
<td><p>DCOM 및 RPC (원격 프로시저 호출)</p></td>
<td><p>사용자 이동, 사용자 복제기 동기화, 주소록 동기화 등의 DCOM 기반 작업에 사용 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>프런트 엔드 서버</p></td>
<td><p>Lync Server 메신저 회의 서비스</p></td>
<td><p>5062</p></td>
<td><p>NET.TCP</p></td>
<td><p>인스턴트 메시징 (IM) 회의에 들어오는 SIP 요청에 사용 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>프런트 엔드 서버</p></td>
<td><p>Lync Server 웹 회의 서비스</p></td>
<td><p>8057</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>클라이언트의 PSOM (영구 공유 개체 모델) 연결을 수신 대기 하는 데 사용 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>프런트 엔드 서버</p></td>
<td><p>Lync Server 웹 회의 호환성 서비스</p></td>
<td><p>8058</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>Live Meeting 클라이언트 및 이전 버전의 Lync Server에서 영구 공유 개체 모델 (PSOM) 연결을 수신 대기 하는 데 사용 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>프런트 엔드 서버</p></td>
<td><p>Lync Server 오디오/비디오 회의 서비스</p></td>
<td><p>5063</p></td>
<td><p>NET.TCP</p></td>
<td><p>오디오/비디오 (A/V) 회의에 대 한 들어오는 SIP 요청에 사용 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>프런트 엔드 서버</p></td>
<td><p>Lync Server 오디오/비디오 회의 서비스</p></td>
<td><p>57501-65535</p></td>
<td><p>TCP/UDP</p></td>
<td><p>비디오 회의에 사용 되는 미디어 포트 범위</p></td>
</tr>
<tr class="odd">
<td><p>프런트 엔드 서버</p></td>
<td><p>Lync Server 웹 호환성 서비스</p></td>
<td><p>80</p></td>
<td><p>HTTP</p></td>
<td><p>HTTPS를 사용 하지 않을 때 프런트 엔드 서버에서 웹 팜 Fqdn (IIS 웹 구성 요소에 사용 되는 Url)으로 통신 하는 데 사용 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>프런트 엔드 서버</p></td>
<td><p>Lync Server 웹 호환성 서비스</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
<td><p>프런트 엔드 서버에서 웹 팜 Fqdn으로 통신 하는 데 사용 됩니다 (IIS 웹 구성 요소에 사용 되는 Url).</p></td>
</tr>
<tr class="odd">
<td><p>프런트 엔드 서버</p></td>
<td><p>Lync Server 웹 호환성 서비스</p></td>
<td><p>8080</p></td>
<td><p>TCP 및 HTTP</p></td>
<td><p>외부 액세스를 위한 웹 구성 요소에 사용 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>프런트 엔드 서버</p></td>
<td><p>웹 서버 구성 요소</p></td>
<td><p>4443</p></td>
<td><p>HTTPS</p></td>
<td><p>자동 검색 로그인을 위한 HTTPS (역방향 프록시) 및 HTTPS 프런트 엔드 풀 간 통신</p></td>
</tr>
<tr class="odd">
<td><p>프런트 엔드 서버</p></td>
<td><p>웹 서버 구성 요소</p></td>
<td><p>8060</p></td>
<td><p>TCP (MTLS)</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>프런트 엔드 서버</p></td>
<td><p>웹 서버 구성 요소</p></td>
<td><p>8061</p></td>
<td><p>TCP (MTLS)</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>프런트 엔드 서버</p></td>
<td><p>Mobility Services 구성 요소</p></td>
<td><p>5086</p></td>
<td><p>TCP (MTLS)</p></td>
<td><p>모바일 서비스 내부 프로세스에서 사용 하는 SIP 포트</p></td>
</tr>
<tr class="even">
<td><p>프런트 엔드 서버</p></td>
<td><p>Mobility Services 구성 요소</p></td>
<td><p>5087</p></td>
<td><p>TCP (MTLS)</p></td>
<td><p>모바일 서비스 내부 프로세스에서 사용 하는 SIP 포트</p></td>
</tr>
<tr class="odd">
<td><p>프런트 엔드 서버</p></td>
<td><p>Mobility Services 구성 요소</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>프런트 엔드 서버</p></td>
<td><p>Lync Server 회의 수행자 서비스 (전화 접속 회의)</p></td>
<td><p>5064</p></td>
<td><p>NET.TCP</p></td>
<td><p>전화 접속 회의에 대 한 수신 SIP 요청에 사용 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>프런트 엔드 서버</p></td>
<td><p>Lync Server 회의 수행자 서비스 (전화 접속 회의)</p></td>
<td><p>5072</p></td>
<td><p>NET.TCP</p></td>
<td><p>전화 교환의 수신 SIP 요청에 사용 됨 (회의에 전화 걸기).</p></td>
</tr>
<tr class="even">
<td><p>Collocated 중재 서버도 실행 하는 프런트 엔드 서버</p></td>
<td><p>Lync Server 중재 서비스</p></td>
<td><p>5070</p></td>
<td><p>NET.TCP</p></td>
<td><p>프런트 엔드 서버에서 중재 서버로 들어오는 요청에 대 한 조정 서버에서 사용 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>Collocated 중재 서버도 실행 하는 프런트 엔드 서버</p></td>
<td><p>Lync Server 중재 서비스</p></td>
<td><p>5067</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>PSTN 게이트웨이에서 중재 서버로 들어오는 SIP 요청에 사용 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>Collocated 중재 서버도 실행 하는 프런트 엔드 서버</p></td>
<td><p>Lync Server 중재 서비스</p></td>
<td><p>5068</p></td>
<td><p>NET.TCP</p></td>
<td><p>PSTN 게이트웨이에서 중재 서버로 들어오는 SIP 요청에 사용 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>Collocated 중재 서버도 실행 하는 프런트 엔드 서버</p></td>
<td><p>Lync Server 중재 서비스</p></td>
<td><p>5081</p></td>
<td><p>NET.TCP</p></td>
<td><p>중재 서버에서 PSTN 게이트웨이로 보내는 SIP 요청에 사용 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>Collocated 중재 서버도 실행 하는 프런트 엔드 서버</p></td>
<td><p>Lync Server 중재 서비스</p></td>
<td><p>5082</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>중재 서버에서 PSTN 게이트웨이로 보내는 SIP 요청에 사용 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>프런트 엔드 서버</p></td>
<td><p>Lync Server 응용 프로그램 공유 서비스</p></td>
<td><p>5065</p></td>
<td><p>NET.TCP</p></td>
<td><p>응용 프로그램 공유에 대 한 수신 SIP 수신 요청에 사용 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>프런트 엔드 서버</p></td>
<td><p>Lync Server 응용 프로그램 공유 서비스</p></td>
<td><p>49152-65535</p></td>
<td><p>NET.TCP</p></td>
<td><p>응용 프로그램 공유에 사용 되는 미디어 포트 범위입니다.</p></td>
</tr>
<tr class="odd">
<td><p>프런트 엔드 서버</p></td>
<td><p>Lync 서버 회의 알림 서비스</p></td>
<td><p>5073</p></td>
<td><p>NET.TCP</p></td>
<td><p>Lync Server 회의 알림 서비스에 대 한 들어오는 SIP 요청에 사용 됩니다 (즉, 전화 접속 회의의 경우).</p></td>
</tr>
<tr class="even">
<td><p>프런트 엔드 서버</p></td>
<td><p>Lync Server 통화 공원 서비스</p></td>
<td><p>5075</p></td>
<td><p>NET.TCP</p></td>
<td><p>통화 공원 응용 프로그램에 대 한 수신 SIP 요청에 사용 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>프런트 엔드 서버</p></td>
<td><p>Lync Server 오디오 테스트 서비스</p></td>
<td><p>5076</p></td>
<td><p>NET.TCP</p></td>
<td><p>오디오 테스트 서비스에 대 한 들어오는 SIP 요청에 사용 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>프런트 엔드 서버</p></td>
<td><p>해당 없음</p></td>
<td><p>5066</p></td>
<td><p>NET.TCP</p></td>
<td><p>아웃 바운드 향상 9-1-1 (E9-1-1) 게이트웨이에 사용 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>프런트 엔드 서버</p></td>
<td><p>Lync Server 응답 그룹 서비스</p></td>
<td><p>5071</p></td>
<td><p>NET.TCP</p></td>
<td><p>응답 그룹 응용 프로그램에 대 한 들어오는 SIP 요청에 사용 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>프런트 엔드 서버</p></td>
<td><p>Lync Server 응답 그룹 서비스</p></td>
<td><p>8404</p></td>
<td><p>TCP (MTLS)</p></td>
<td><p>응답 그룹 응용 프로그램에 대 한 들어오는 SIP 요청에 사용 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>프런트 엔드 서버</p></td>
<td><p>Lync Server 대역폭 정책 서비스</p></td>
<td><p>5080</p></td>
<td><p>NET.TCP</p></td>
<td><p>대역폭 정책 서비스에 의해 통화 허용 제어에 사용 됩니다 (A/V Edge TURN 트래픽).</p></td>
</tr>
<tr class="even">
<td><p>프런트 엔드 서버</p></td>
<td><p>Lync Server 대역폭 정책 서비스</p></td>
<td><p>448</p></td>
<td><p>NET.TCP</p></td>
<td><p>Lync Server 대역폭 정책 서비스에의 한 통화 허용 제어에 사용 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>중앙 관리 저장소가 상주 하는 프런트 엔드 서버</p></td>
<td><p>Lync Server 마스터 복제기 에이전트 서비스</p></td>
<td><p>445</p></td>
<td><p>NET.TCP</p></td>
<td><p>중앙 관리 저장소의 구성 데이터를 Lync Server를 실행 하는 서버에 푸시하는 데 사용 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>모든 서버</p></td>
<td><p>SQL 브라우저</p></td>
<td><p>1434</p></td>
<td><p>UDP</p></td>
<td><p>로컬 SQL Server 인스턴스에서 중앙 관리 저장소 데이터의 로컬 복제 복사본에 대 한 SQL 브라우저</p></td>
</tr>
<tr class="odd">
<td><p>모든 내부 서버</p></td>
<td><p>다양 한</p></td>
<td><p>49152-57500</p></td>
<td><p>TCP/UDP</p></td>
<td><p>모든 내부 서버에서 오디오 회의에 사용 되는 미디어 포트 범위 오디오를 종료 하는 모든 서버 (Lync Server 회의 수행자 서비스, Lync server 회의 알림 서비스, lync Server 오디오/비디오 회의 서비스의 경우) 및 중재 서버에 사용 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>Office Web Apps 서버</p></td>
<td></td>
<td><p>443</p></td>
<td></td>
<td><p>Lync Server 2013에서 Office Web Apps 서버에 연결 하는 데 사용 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>이사</p></td>
<td><p>Lync Server 프런트 엔드 서비스</p></td>
<td><p>5060</p></td>
<td><p>NET.TCP</p></td>
<td><p>필요에 따라 원격 통화 제어 서버와 같은 신뢰할 수 있는 서비스에 대 한 고정 경로에 사용 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>이사</p></td>
<td><p>Lync Server 프런트 엔드 서비스</p></td>
<td><p>444</p></td>
<td><p>HTTPS</p>
<p>NET.TCP</p></td>
<td><p>프론트 엔드 및 디렉터 간의 서버 간 통신. 또한 클라이언트 인증서가 프런트 엔드 서버로 게시 되거나 클라이언트 인증서가 이미 게시 되었는지 확인 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>이사</p></td>
<td><p>Lync Server 웹 호환성 서비스</p></td>
<td><p>80</p></td>
<td><p>NET.TCP</p></td>
<td><p>디렉터에서 웹 팜 Fqdn으로 초기 통신 하는 데 사용 됩니다 (IIS 웹 구성 요소에 사용 되는 Url). 정상 작업에서 포트 443 및 프로토콜 유형 TCP를 사용 하 여 HTTPS 트래픽으로 전환 합니다.</p></td>
</tr>
<tr class="even">
<td><p>이사</p></td>
<td><p>Lync Server 웹 호환성 서비스</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
<td><p>디렉터에서 웹 팜 Fqdn으로 통신 하는 데 사용 됩니다 (IIS 웹 구성 요소에 사용 되는 Url).</p></td>
</tr>
<tr class="odd">
<td><p>이사</p></td>
<td><p>Lync Server 프런트 엔드 서비스</p></td>
<td><p>5061</p></td>
<td><p>NET.TCP</p></td>
<td><p>서버 간 내부 통신 및 클라이언트 연결에 사용 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>중재 서버</p></td>
<td><p>Lync Server 중재 서비스</p></td>
<td><p>5070</p></td>
<td><p>NET.TCP</p></td>
<td><p>프런트 엔드 서버에서 들어오는 요청에 대해 조정 서버에서 사용 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>중재 서버</p></td>
<td><p>Lync Server 중재 서비스</p></td>
<td><p>5067</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>PSTN 게이트웨이에서 들어오는 SIP 요청에 사용 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>중재 서버</p></td>
<td><p>Lync Server 중재 서비스</p></td>
<td><p>5068</p></td>
<td><p>NET.TCP</p></td>
<td><p>PSTN 게이트웨이에서 들어오는 SIP 요청에 사용 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>중재 서버</p></td>
<td><p>Lync Server 중재 서비스</p></td>
<td><p>5070</p></td>
<td><p>TCP (MTLS)</p></td>
<td><p>프런트 엔드 서버의 SIP 요청에 사용 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>영구 채팅 프런트 엔드 서버</p></td>
<td><p>영구 채팅 SIP</p></td>
<td><p>5041</p></td>
<td><p>TCP (MTLS)</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>영구 채팅 프런트 엔드 서버</p></td>
<td><p>WCF (Windows Communication Foundation) 영구 채팅</p></td>
<td><p>881</p></td>
<td><p>TCP (TLS) 및 TCP (MTLS)</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>영구 채팅 프런트 엔드 서버</p></td>
<td><p>영구 채팅 파일 전송 서비스</p></td>
<td><p>443</p></td>
<td><p>TCP (TLS)</p></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 일부 원격 통화 제어 시나리오는 프런트 엔드 서버 또는 디렉터와 PBX 간의 TCP 연결이 필요 합니다. Lync Server는 더 이상 TCP 포트 5060를 사용 하지 않지만 원격 통화 제어 배포 중에는 RCC 회선 서버 FQDN을 프런트 엔드 서버 또는 디렉터가 PBX 시스템에 연결 하는 데 사용할 TCP 포트와 연결 하는 신뢰할 수 있는 서버 구성을 만듭니다. 자세한 내용은 Lync Server 관리 셸 설명서의 <STRONG>CsTrustedApplicationComputer</STRONG> cmdlet을 참조 하세요.



</div>

DNS 부하 분산이 아닌 하드웨어 로드 균형 조정만 사용 하는 풀의 경우 다음 표에는 하드웨어 로드 균형 조정기를 여는 데 필요한 포트가 나와 있습니다.

### <a name="hardware-load-balancer-ports-if-using-only-hardware-load-balancing"></a>하드웨어 부하 분산만 사용 하는 경우 하드웨어 부하 분산 장치 포트

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>부하 분산 장치</th>
<th>포트</th>
<th>프로토콜별</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>프런트 엔드 서버 부하 분산 장치</p></td>
<td><p>5061</p></td>
<td><p>TCP (TLS)</p></td>
</tr>
<tr class="even">
<td><p>프런트 엔드 서버 부하 분산 장치</p></td>
<td><p>444</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="odd">
<td><p>프런트 엔드 서버 부하 분산 장치</p></td>
<td><p>135</p></td>
<td><p>DCOM 및 RPC (원격 프로시저 호출)</p></td>
</tr>
<tr class="even">
<td><p>프런트 엔드 서버 부하 분산 장치</p></td>
<td><p>80</p></td>
<td><p>HTTP</p></td>
</tr>
<tr class="odd">
<td><p>프런트 엔드 서버 부하 분산 장치</p></td>
<td><p>8080</p></td>
<td><p>TCP-프런트 엔드 서버에서 루트 인증서의 클라이언트 및 장치 검색-NTLM으로 인증 된 클라이언트 및 장치</p></td>
</tr>
<tr class="even">
<td><p>프런트 엔드 서버 부하 분산 장치</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="odd">
<td><p>프런트 엔드 서버 부하 분산 장치</p></td>
<td><p>4443</p></td>
<td><p>HTTPS (역방향 프록시)</p></td>
</tr>
<tr class="even">
<td><p>프런트 엔드 서버 부하 분산 장치</p></td>
<td><p>5072</p></td>
<td><p>NET.TCP</p></td>
</tr>
<tr class="odd">
<td><p>프런트 엔드 서버 부하 분산 장치</p></td>
<td><p>5073</p></td>
<td><p>NET.TCP</p></td>
</tr>
<tr class="even">
<td><p>프런트 엔드 서버 부하 분산 장치</p></td>
<td><p>5075</p></td>
<td><p>NET.TCP</p></td>
</tr>
<tr class="odd">
<td><p>프런트 엔드 서버 부하 분산 장치</p></td>
<td><p>5076</p></td>
<td><p>NET.TCP</p></td>
</tr>
<tr class="even">
<td><p>프런트 엔드 서버 부하 분산 장치</p></td>
<td><p>5071</p></td>
<td><p>NET.TCP</p></td>
</tr>
<tr class="odd">
<td><p>프런트 엔드 서버 부하 분산 장치</p></td>
<td><p>5080</p></td>
<td><p>NET.TCP</p></td>
</tr>
<tr class="even">
<td><p>프런트 엔드 서버 부하 분산 장치</p></td>
<td><p>448</p></td>
<td><p>NET.TCP</p></td>
</tr>
<tr class="odd">
<td><p>중재 서버 부하 분산 장치</p></td>
<td><p>5070</p></td>
<td><p>NET.TCP</p></td>
</tr>
<tr class="even">
<td><p>프런트 엔드 서버 부하 분산 장치 (풀에서 중재 서버도 실행 되는 경우)</p></td>
<td><p>5070</p></td>
<td><p>NET.TCP</p></td>
</tr>
<tr class="odd">
<td><p>디렉터 부하 분산 장치</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="even">
<td><p>디렉터 부하 분산 장치</p></td>
<td><p>444</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="odd">
<td><p>디렉터 부하 분산 장치</p></td>
<td><p>5061</p></td>
<td><p>NET.TCP</p></td>
</tr>
<tr class="even">
<td><p>디렉터 부하 분산 장치</p></td>
<td><p>4443</p></td>
<td><p>HTTPS (역방향 프록시)</p></td>
</tr>
</tbody>
</table>


DNS 부하 분산을 사용 하는 프런트 엔드 풀 및 디렉터 풀에도 하드웨어 부하 분산 장치를 배포 해야 합니다. 다음 표에는 이러한 하드웨어 부하 분산 장치에서 열려 있어야 하는 포트가 나와 있습니다.

### <a name="hardware-load-balancer-ports-if-using-dns-load-balancing"></a>DNS 부하 분산을 사용 하는 경우 하드웨어 부하 분산 장치 포트

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>부하 분산 장치</th>
<th>포트</th>
<th>프로토콜별</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>프런트 엔드 서버 부하 분산 장치</p></td>
<td><p>80</p></td>
<td><p>HTTP</p></td>
</tr>
<tr class="even">
<td><p>프런트 엔드 서버 부하 분산 장치</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="odd">
<td><p>프런트 엔드 서버 부하 분산 장치</p></td>
<td><p>8080</p></td>
<td><p>TCP-프런트 엔드 서버에서 루트 인증서의 클라이언트 및 장치 검색-NTLM으로 인증 된 클라이언트 및 장치</p></td>
</tr>
<tr class="even">
<td><p>프런트 엔드 서버 부하 분산 장치</p></td>
<td><p>4443</p></td>
<td><p>HTTPS (역방향 프록시)</p></td>
</tr>
<tr class="odd">
<td><p>디렉터 부하 분산 장치</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td><p>디렉터 부하 분산 장치</p></td>
<td><p>4443</p></td>
<td><p>HTTPS (역방향 프록시)</p></td>
</tr>
</tbody>
</table>


### <a name="required-client-ports"></a>필수 클라이언트 포트

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>요소가</th>
<th>포트</th>
<th>프로토콜별</th>
<th>상속자</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>클라이언트</p></td>
<td><p>67/68</p></td>
<td><p>서버의</p></td>
<td><p>Lync Server에서 등록자 FQDN을 찾는 데 사용 됩니다 (즉, DNS SRV에 장애가 발생 하 여 수동 설정이 구성 되지 않은 경우).</p></td>
</tr>
<tr class="even">
<td><p>클라이언트</p></td>
<td><p>443</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>외부 사용자 액세스를 위한 클라이언트 대 서버 SIP 트래픽에 사용 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>클라이언트</p></td>
<td><p>443</p></td>
<td><p>TCP (PSOM/TLS)</p></td>
<td><p>웹 회의 세션에 대 한 외부 사용자 액세스에 사용 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>클라이언트</p></td>
<td><p>443</p></td>
<td><p>TCP (STUN/MSTURN)</p></td>
<td><p>A/V 세션 및 미디어 (TCP)에 대 한 외부 사용자 액세스에 사용 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>클라이언트</p></td>
<td><p>3478</p></td>
<td><p>UDP (STUN/MSTURN)</p></td>
<td><p>A/V 세션 및 미디어 (UDP)에 대 한 외부 사용자 액세스에 사용 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>클라이언트</p></td>
<td><p>5061</p></td>
<td><p>TCP (MTLS)</p></td>
<td><p>외부 사용자 액세스를 위한 클라이언트 대 서버 SIP 트래픽에 사용 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>클라이언트</p></td>
<td><p>6891-6901</p></td>
<td><p>NET.TCP</p></td>
<td><p>Lync 클라이언트와 이전 클라이언트 간의 파일 전송 (Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007 및 Live Communications Server 2005의 클라이언트)에 사용 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>클라이언트</p></td>
<td><p>1024-65535 *</p></td>
<td><p>TCP/UDP</p></td>
<td><p>오디오 포트 범위 (최소 20 개의 포트가 필요 함)</p></td>
</tr>
<tr class="odd">
<td><p>클라이언트</p></td>
<td><p>1024-65535 *</p></td>
<td><p>TCP/UDP</p></td>
<td><p>비디오 포트 범위 (최소 20 개 포트 필요).</p></td>
</tr>
<tr class="even">
<td><p>클라이언트</p></td>
<td><p>1024-65535 *</p></td>
<td><p>NET.TCP</p></td>
<td><p>피어 투 피어 파일 전송 (회의 파일 전송의 경우 클라이언트는 PSOM 사용).</p></td>
</tr>
<tr class="odd">
<td><p>클라이언트</p></td>
<td><p>1024-65535 *</p></td>
<td><p>NET.TCP</p></td>
<td><p>응용 프로그램 공유</p></td>
</tr>
<tr class="even">
<td><p>Aastra 6721ip 공용 지역 전화</p>
<p>Aastra 6725ip 일반 전화기</p>
<p>HP 4110 IP 전화 (공통 지역 전화)</p>
<p>HP 4120 IP 전화기 (일반 전화기)</p>
<p>Polycom CX500 IP 일반 지역 전화</p>
<p>Polycom CX600 IP 일반 전화기</p>
<p>Polycom CX700 IP 일반 전화기</p>
<p>Polycom CX3000 IP 컨퍼런스 전화</p></td>
<td><p>67/68</p></td>
<td><p>서버의</p></td>
<td><p>나열 된 디바이스에서 Lync Server 인증서, 프로비저닝 FQDN 및 등록자 FQDN을 찾는 데 사용 됩니다.</p></td>
</tr>
</tbody>
</table>


**\*** 이러한 미디어 형식에 대 한 특정 포트를 구성 하려면 CsConferencingConfiguration cmdlet (ClientMediaPortRangeEnabled, ClientMediaPort 및 ClientMediaPortRange parameters)을 사용 합니다.

<div>


> [!NOTE]  
> Lync 클라이언트에 대 한 프로그램 설정에서는 클라이언트 컴퓨터에서 필요한 운영 체제 방화벽 예외를 자동으로 만듭니다.



</div>

<div>


> [!NOTE]  
> 외부 사용자 액세스에 사용 되는 포트는 클라이언트가 조직의 방화벽을 통과 해야 하는 모든 시나리오 (예: 다른 조직에서 호스팅하는 외부 통신 또는 모임)에 필요 합니다.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

