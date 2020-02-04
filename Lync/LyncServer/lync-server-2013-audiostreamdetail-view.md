---
title: 'Lync Server 2013: 오디오 Streamdetail 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AudioStreamDetail view
ms:assetid: b6a435b3-103c-41c4-96ed-33c3784534c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721859(v=OCS.15)
ms:contentKeyID: 49733792
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77cebcd47d735f1779396c0272877c0ec64a6189
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722588"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiostreamdetail-view-in-lync-server-2013"></a>Lync Server 2013의 오디오 Streamdetail 보기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-03_

오디오 Streamdetail 보기에는 데이터베이스의 각 오디오 스트림에 대 한 정보가 저장 됩니다. 이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>열</th>
<th>데이터 형식</th>
<th>세부적인</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>SessionTime</p></td>
<td><p>dmtf</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialine 테이블</a>에서 참조 합니다.</p></td>
</tr>
<tr class="even">
<td><p>SessionSeq</p></td>
<td><p>int</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialine 테이블</a>에서 참조 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>StreamId</p></td>
<td><p>int</p></td>
<td><p>미디어 라인 내의 고유 ID.</p></td>
</tr>
<tr class="even">
<td><p>StartTime</p></td>
<td><p>dmtf</p></td>
<td><p>세션 시작 시간입니다.</p></td>
</tr>
<tr class="odd">
<td><p>EndTime</p></td>
<td><p>dmtf</p></td>
<td><p>세션 종료 시간입니다.</p></td>
</tr>
<tr class="even">
<td><p>DialogCategory</p></td>
<td><p>다소</p></td>
<td><p>대화 상자 범주: 0은 서버 레그를 중재 하는 Lync 서버입니다. 1은 PSTN 게이트웨이 레그에 대 한 중재 서버입니다.</p></td>
</tr>
<tr class="odd">
<td><p>MediationServerBypassFlag</p></td>
<td><p>다소</p></td>
<td><p>통화가 바이패스 되었는지 여부를 나타내는 플래그입니다.</p></td>
</tr>
<tr class="even">
<td><p>MediaBypassWarningFlag</p></td>
<td><p>int</p></td>
<td><p>바이패스 Id가 일치 하는 경우에도 통화가 무시 되지 않은 이유를 표시 합니다. 하나의 값만 정의 된 경우:</p>
<p>0x0001-기본 네트워크 어댑터에 대 한 알 수 없는 바이패스 ID.</p></td>
</tr>
<tr class="odd">
<td><p>CallPriority</p></td>
<td><p>int</p></td>
<td><p>통화의 우선 순위입니다.</p></td>
</tr>
<tr class="even">
<td><p>CallerPool</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>발신자 풀 FQDN.</p></td>
</tr>
<tr class="odd">
<td><p>CalleePool</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>호출 수신자 풀 FQDN입니다.</p></td>
</tr>
<tr class="even">
<td><p>호출인</p></td>
<td><p>nvarchar (450)</p></td>
<td><p>호출자의 URI입니다.</p></td>
</tr>
<tr class="odd">
<td><p>피호출자</p></td>
<td><p>nvarchar (450)</p></td>
<td><p>호출 수신자의 URI입니다.</p></td>
</tr>
<tr class="even">
<td><p>CallerUserAgent</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>호출자의 사용자 에이전트 문자열입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CallerUserAgentType</p></td>
<td><p>smallint</p></td>
<td><p>호출자의 사용자 에이전트 유형입니다. 자세한 내용은 <a href="lync-server-2013-useragent-table.md">Lync Server 2013의 UserAgent 테이블</a> 을 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p>CallerUserAgentCategory</p></td>
<td><p>nvarchar (64)</p></td>
<td><p>호출자의 사용자 에이전트 범주입니다. 자세한 내용은 <a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013의 Useragentdef 테이블 (체감 품질)</a> 을 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserAgent</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>호출 수신자의 사용자 에이전트 문자열입니다.</p></td>
</tr>
<tr class="even">
<td><p>CalleeUserAgentType</p></td>
<td><p>smallint</p></td>
<td><p>호출 수신자의 사용자 에이전트 유형입니다. 자세한 내용은 <a href="lync-server-2013-useragent-table.md">Lync Server 2013의 UserAgent 테이블</a> 을 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserAgentCategory</p></td>
<td><p>nvarchar (64)</p></td>
<td><p>호출 수신자의 사용자 에이전트 범주입니다. 자세한 내용은 <a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013의 Useragentdef 테이블 (체감 품질)</a> 을 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p>CallerEndpoint</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>호출자의 끝점 이름입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeEndpoint</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>호출 수신자의 끝점 이름입니다.</p></td>
</tr>
<tr class="even">
<td><p>CallerOS</p></td>
<td><p>name</p></td>
<td><p>호출자 끝점의 OS (운영 체제)입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeOS</p></td>
<td><p>name</p></td>
<td><p>호출 수신자의 끝점에 대 한 OS (운영 체제)입니다.</p></td>
</tr>
<tr class="even">
<td><p>CallerCPUName</p></td>
<td><p>name</p></td>
<td><p>호출자 끝점의 CPU 이름입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCPUName</p></td>
<td><p>name</p></td>
<td><p>호출 수신자의 끝점에 대 한 CPU 이름입니다.</p></td>
</tr>
<tr class="even">
<td><p>Callercpunum<c13> Of코어</p></td>
<td><p>smallint</p></td>
<td><p>호출자 끝점의 CPU 코어 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCPUNumberOfCores</p></td>
<td><p>smallint</p></td>
<td><p>호출 수신자의 끝점에 있는 CPU 코어 수입니다.</p></td>
</tr>
<tr class="even">
<td><p>CallerCPUProcessorSpeed</p></td>
<td><p>int</p></td>
<td><p>호출자 끝점의 CPU 프로세서 속도입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCPUProcessorSpeed</p></td>
<td><p>int</p></td>
<td><p>호출 수신자의 끝점에 대 한 CPU 프로세서 속도입니다.</p></td>
</tr>
<tr class="even">
<td><p>CallerVirtualizationFlag</p></td>
<td><p>tinyint</p></td>
<td><p>호출자의 시스템이 가상화 된 환경에서 실행 중인지 여부를 나타냅니다. 자세한 내용은 <a href="lync-server-2013-endpoint-table.md">Lync Server 2013의 끝점 테이블</a> 을 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVirtualizationFlag</p></td>
<td><p>tinyint</p></td>
<td><p>호출 수신자의 시스템이 가상화 된 환경에서 실행 중인지 여부를 나타냅니다. 자세한 내용은 <a href="lync-server-2013-endpoint-table.md">Lync Server 2013의 끝점 테이블</a> 을 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p>CorrelationKey</p></td>
<td></td>
<td><p>상관 관계 키입니다. <a href="lync-server-2013-sessioncorrelation-table.md">Lync Server 2013의 Sessioncorrelation 관계 테이블</a>에서 참조 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>ConnectivityIce</p></td>
<td><p>tinyint</p></td>
<td><p>미디어 경로에 대 한 정보 (예: 직접 또는 릴레이)입니다. 자세한 내용은 <a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialine 테이블</a> 을 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p>CallerIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>호출자의 bits 플래그에 설명 된 ICE (대화형 연결 설정) 프로세스에 대 한 정보입니다. 자세한 내용은 경험의 품질 모니터링 서버 프로토콜 사양을 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>호출 수신자의 bits 플래그에 설명 된 ICE (대화형 연결 설정) 프로세스에 대 한 정보입니다. 자세한 내용은 경험의 품질 모니터링 서버 프로토콜 사양을 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p>운송</p></td>
<td><p>tinyint</p></td>
<td><p>전송 종류: 0은 UDP이 고, 1은 TCP입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CallerIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>발신자의 IP 주소입니다. IPv4 또는 IPv6 주소 일 수 있습니다.</p></td>
</tr>
<tr class="even">
<td><p>CallerPort</p></td>
<td><p>int</p></td>
<td><p>호출자가 사용 하는 포트입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CallerInside</p></td>
<td><p>다소</p></td>
<td><p>호출자가 간격 네트워크 내에 있는지 여부를 나타냅니다. 1은 호출자가 엔터프라이즈 네트워크 내에 있음을 의미 하 고 0 이면 호출자가 네트워크 외부에 있음을 의미 합니다.</p></td>
</tr>
<tr class="even">
<td><p>CalleeIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>호출 수신자의 IP 주소입니다. IPv4 또는 IPv6 주소 일 수 있습니다.</p></td>
</tr>
<tr class="odd">
<td><p>CalleePort</p></td>
<td><p>int</p></td>
<td><p>호출 수신자가 사용 하는 포트입니다.</p></td>
</tr>
<tr class="even">
<td><p>CalleeInside</p></td>
<td><p>다소</p></td>
<td><p>호출 수신자가 간격 네트워크 내에 있는지 여부를 나타냅니다. 1은 호출 수신자가 엔터프라이즈 네트워크 내에 있음을 의미 하 고 0은 호출 수신자가 네트워크 외부에 있음을 의미 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>CallerUserSite</p></td>
<td><p>name</p></td>
<td><p>호출자 사이트의 이름입니다.</p></td>
</tr>
<tr class="even">
<td><p>CallerRegion</p></td>
<td><p>name</p></td>
<td><p>발신자 사이트의 국가/지역 이름입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserSite</p></td>
<td><p>name</p></td>
<td><p>피호출자 사이트의 이름입니다.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRegion</p></td>
<td><p>name</p></td>
<td><p>피호출자 사이트의 국가/지역 이름입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CallerRelayIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>발신자가 사용 하는 A/V Edge 서비스의 IP 주소입니다. 자세한 내용은 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013의 IPAddress 테이블</a> 을 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p>CallerRelayPort</p></td>
<td><p>int</p></td>
<td><p>호출자가 사용 하는 A/V Edge 서비스에 사용 되는 포트입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRelayIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>호출 수신자가 사용 하는 A/V Edge 서비스의 IP 주소 키입니다. 자세한 내용은 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013의 IPAddress 테이블</a> 을 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRelayPort</p></td>
<td><p>int</p></td>
<td><p>호출 수신자가 사용 하는 A/V Edge 서비스에 사용 되는 포트입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CallerCaptureDev</p></td>
<td><p>varchar (256)</p></td>
<td><p>발신자의 캡처 장치 이름입니다.</p></td>
</tr>
<tr class="even">
<td><p>CallerRenderDev</p></td>
<td><p>varchar (256)</p></td>
<td><p>발신자의 렌더링 장치 이름.</p></td>
</tr>
<tr class="odd">
<td><p>CallerCaptureDevDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>발신자의 캡처 장치 드라이버 이름.</p></td>
</tr>
<tr class="even">
<td><p>CallerRenderDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>호출자의 렌더링 장치 드라이버 이름입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCaptureDev</p></td>
<td><p>varchar (256)</p></td>
<td><p>호출 수신자의 캡처 디바이스 이름입니다.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRenderDev</p></td>
<td><p>varchar (256)</p></td>
<td><p>피호출자의 렌더링 디바이스 이름입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCaptureDevDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>피호출자의 캡처 장치 드라이버 이름입니다.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRenderDevDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>피호출자의 렌더링 장치 드라이버 이름입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CallerNetworkConnectionType</p></td>
<td><p>tinyint</p></td>
<td><p>발신자의 네트워크 연결 유형: 0이 유선 인 경우 1은 무선입니다.</p></td>
</tr>
<tr class="even">
<td><p>CallerVPN</p></td>
<td><p>다소</p></td>
<td><p>가상 개인 네트워크를 통해 연결 된 호출자가 VPN (가상 사설망) 인 경우 0이 고 VPN이 아닌 경우를 나타냅니다.</p></td>
</tr>
<tr class="odd">
<td><p>CallerLinkSpeed</p></td>
<td><p>10 진수 (18, 0)</p></td>
<td><p>Bps의 호출자 끝점에 대 한 네트워크 링크 속도입니다.</p></td>
</tr>
<tr class="even">
<td><p>CalleeNetworkConnectionType</p></td>
<td><p>tinyint</p></td>
<td><p>피호출자의 네트워크 연결 형식: 0이 유선 인 경우 1은 무선입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVPN</p></td>
<td><p>다소</p></td>
<td><p>가상 개인 네트워크를 통해 연결 된 호출자가 VPN (가상 사설망) 인 경우 0이 고 VPN이 아닌 경우를 나타냅니다.</p></td>
</tr>
<tr class="even">
<td><p>CalleeLinkSpeed</p></td>
<td><p>10 진수 (18, 0)</p></td>
<td><p>Bps의 호출 수신자 끝점에 대 한 네트워크 링크 속도입니다.</p></td>
</tr>
<tr class="odd">
<td><p>ConversationalMOS</p></td>
<td><p>10 진수 (3, 2)</p></td>
<td><p>오디오 세션의 Narrowband 대화 SPECIALIST (두 오디오 스트림 모두 기준).</p></td>
</tr>
<tr class="even">
<td><p>AppliedBandwidthLimit</p></td>
<td><p>int</p></td>
<td><p>다양 한 정책 설정 (TURN, API, SDP, 정책 서버 등)을 지정 하 여 지정 된 보내기 쪽 스트림에 실제 대역폭을 적용 했습니다. 대역폭 예측을 기준으로 낮은 유효 대역폭을 사용할 수 있기 때문에 효과적인 대역폭과 혼동 하지 않는 것이 좋습니다. 이 값은 기본적으로 전송 스트림에 의해 대역폭 예상에 의해 적용 되는 최대 대역폭을 제한할 수 있습니다.</p></td>
</tr>
<tr class="odd">
<td><p>JitterInterArrival</p></td>
<td><p>int</p></td>
<td><p>RTCP (실시간 제어 프로토콜) 통계의 평균 네트워크 지터입니다.</p></td>
</tr>
<tr class="even">
<td><p>JitterInterArrivalMax</p></td>
<td><p>int</p></td>
<td><p>통화 중 최대 네트워크 지터.</p></td>
</tr>
<tr class="odd">
<td><p>PacketLossRate</p></td>
<td><p>10 진수 (5, 4)</p></td>
<td><p>통화 중의 평균 패킷 손실 율입니다.</p></td>
</tr>
<tr class="even">
<td><p>PacketLossRateMax</p></td>
<td><p>10 진수 (5, 4)</p></td>
<td><p>통화 중에 최대 패킷 손실이 관찰 되었습니다.</p></td>
</tr>
<tr class="odd">
<td><p>BurstDensity</p></td>
<td><p>10 진수 (9, 4)</p></td>
<td><p>통화 중에 손실이 발생 한 경우 패킷 손실의 평균 밀도입니다.</p></td>
</tr>
<tr class="even">
<td><p>BurstDuration</p></td>
<td><p>int</p></td>
<td><p>통화 중에 손실 되는 패킷 손실의 평균 지속 시간입니다.</p></td>
</tr>
<tr class="odd">
<td><p>BurstGapDensity</p></td>
<td><p>10 진수 (9, 4)</p></td>
<td><p>패킷 손실의 버스트 간에 간격을 두는 경우 패킷 손실의 평균 밀도.</p></td>
</tr>
<tr class="even">
<td><p>BurstGapDuration</p></td>
<td><p>int</p></td>
<td><p>패킷 손실의 버스트 간 평균 간격 기간입니다.</p></td>
</tr>
<tr class="odd">
<td><p>PacketUtilization</p></td>
<td><p>int</p></td>
<td><p>오디오 스트림의 패킷 수입니다.</p></td>
</tr>
<tr class="even">
<td><p>BandwidthEst</p></td>
<td><p>int</p></td>
<td><p>오디오 스트림의 대역폭을 예측 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>DegradationAvg</p></td>
<td><p>10 진수 (3, 2)</p></td>
<td><p>전체 통화에 대 한 네트워크 SPECIALIST 성능이 저하 됩니다. 범위는 0.0 ~ 5.0입니다. 이 메트릭은 지터 및 패킷 손실로 인해 네트워크 SPECIALIST 감소 된 양을 표시 합니다. 허용 되는 품질은 0.5 미만 이어야 합니다.</p></td>
</tr>
<tr class="even">
<td><p>DegradationMax</p></td>
<td><p>10 진수 (3, 2)</p></td>
<td><p>통화 중에 최대 네트워크 SPECIALIST 저하 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>DegradationJitterAvg</p></td>
<td><p>10 진수 (3, 2)</p></td>
<td><p>지터로 인해 네트워크 SPECIALIST 저하 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>DegradationPacketLossAvg</p></td>
<td><p>10 진수 (3, 2)</p></td>
<td><p>패킷 손실로 인해 네트워크 SPECIALIST 저하 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>PayloadDescription</p></td>
<td><p>int</p></td>
<td><p><a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013의 PayloadDescription 테이블</a>에서 참조 되는 통화에 사용 되는 오디오 코덱입니다.</p></td>
</tr>
<tr class="even">
<td><p>AudioSampleRate</p></td>
<td><p>int</p></td>
<td><p>오디오 스트림의 샘플링 속도입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CallerSendSignalLevel</p></td>
<td><p>int</p></td>
<td><p>발신자가 보낸 오디오에 대 한 아날로그 게인 포스트 컨트롤 오디오 신호 수준입니다. 이 메트릭의 단위는 dBmo입니다. 적절 한 품질을 위해서는 30 dBmo 이상 이어야 합니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>CallerRecvSignalLevel</p></td>
<td><p>int</p></td>
<td><p>발신자가 받은 오디오에 대 한 오디오 신호 수준입니다. 이 메트릭의 단위는 dBmo입니다. 적절 한 품질을 위해서는 30 dBmo 이상 이어야 합니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>CallerSendNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>발신자가 보낸 오디오에 대 한 아날로그 게인 사후 제어 오디오 노이즈 수준입니다. 이 메트릭의 단위는 dBmo입니다. 적절 한 품질을 위해서는 35 dBmo 미만 이어야 합니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>CallerRecvNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>발신자가 받은 오디오에 대 한 아날로그 게인 포스트 컨트롤 오디오 잡음 수준입니다. 이 메트릭의 단위는 dBmo입니다. 적절 한 품질을 위해서는 35 dBmo 미만 이어야 합니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>CallerEchoReturn</p></td>
<td><p>int</p></td>
<td><p>호출자에 대 한 에코 반환 손실 보정. 이 메트릭의 단위는 dB입니다. 값이 낮을수록 화면 표시 수준이 낮아집니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>CallerSpeakerGlitchRate</p></td>
<td><p>int</p></td>
<td><p>호출자의 스피커 렌더링에 대 한 5 분 당 평균 결함입니다. 좋은 품질을 위해서는 5 분에 1 보다 작아야 합니다. A/V 회의 서버, 중재 서버 또는 IP 전화기에서 보고 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>CallerMicGlitchRate</p></td>
<td><p>int</p></td>
<td><p>발신자의 마이크 캡처에 대 한 5 분 당 평균 결함. 좋은 품질을 위해서는 5 분에 1을 미만 이어야 합니다. A/V 회의 서버, 중재 서버 또는 IP 전화기에서 보고 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>CallerTimestampDriftRateMic</p></td>
<td><p>10 진수 (9, 2)</p></td>
<td><p>발신자의 마이크 장치 시계 드리프트 속도 (CPU 클록 기준).</p></td>
</tr>
<tr class="odd">
<td><p>CallerTimestampDriftRateSpk</p></td>
<td><p>10 진수 (9, 2)</p></td>
<td><p>호출자의 스피커 장치 시계 드리프트 속도 (CPU 클록 기준)입니다.</p></td>
</tr>
<tr class="even">
<td><p>CallerTimestampErrorMicMs</p></td>
<td><p>10 진수 (9, 2)</p></td>
<td><p>평균 마이크 캡처 스트림 타임 스탬프 (밀리초) (통화의 마지막 20 초)</p></td>
</tr>
<tr class="odd">
<td><p>CallerTimestampErrorSpkMs</p></td>
<td><p>10 진수 (9, 2)</p></td>
<td><p>호출자의 스피커 평균 마지막 20 초 동안 스트림 타임 스탬프 오류를 밀리초 단위로 렌더링 합니다.</p></td>
</tr>
<tr class="even">
<td><p>CallerVsEntryCauses</p></td>
<td><p>smallint</p></td>
<td><p>음성 스위치는 인터럽트 감소 기능이 있는 반 양방향 모드입니다. 자세한 내용은 <a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialine 테이블</a> 을 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p>CallerEchoEventCauses</p></td>
<td><p>tinyint</p></td>
<td><p>호출자에 대 한 에코 이벤트의 원인입니다. 자세한 내용은 <a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialine 테이블</a> 을 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p>CallerEchoPercentMicIn</p></td>
<td><p>10 진수 (5, 2)</p></td>
<td><p>발신자의 마이크 캡처 스트림에서 반향을 감지 하는 시간의 백분율입니다. 헤드셋을 사용 하는 경우 값이 작아야 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>CallerEchoPercentSend</p></td>
<td><p>10 진수 (5, 2)</p></td>
<td><p>발신자의 전송 된 스트림에서 반향을 감지 하는 시간의 백분율입니다. 송신 스트림의 화면 표시 백분율 에코 누수를 나타냅니다.</p></td>
</tr>
<tr class="even">
<td><p>CallerRxAGCSignalLevel</p></td>
<td><p>int</p></td>
<td><p>게이트웨이에서 호출자 오디오에 대 한 중재 서버의 신호 수준을 수신 했습니다. 이는 중재 서버에만 적용 됩니다. 이 메트릭의 단위는 dBoV입니다. 좋은 품질을 위해서는 허용 되는 범위는-30 ~-18 dBoV 이어야 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>CallerRxAGCNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>발신자의 오디오에 대 한 게이트웨이에서 중재 서버에 대 한 신호 수준을 수신 했습니다. 이는 중재 서버에만 적용 됩니다. 이 메트릭의 단위는 dBoV입니다. 좋은 품질을 위해서는 허용 되는 범위가-50 dBoV 미만 이어야 합니다.</p></td>
</tr>
<tr class="even">
<td><p>CallerRxAGCGain</p></td>
<td><p>int</p></td>
<td><p>조정 서버 쪽의 자동 게인 제어 (AGC)를 호출자의 오디오에 적용 했습니다.</p></td>
</tr>
<tr class="odd">
<td><p>CallerInitialSignalLevelRMS</p></td>
<td><p>o</p></td>
<td><p>통화의 처음 30 초까지 호출자에 게 들어오는 신호에 대 한 루트 평균 제곱근 (RMS).</p></td>
</tr>
<tr class="even">
<td><p>CalleeSendSignalLevel</p></td>
<td><p>int</p></td>
<td><p>호출 수신자가 보낸 오디오에 대 한 아날로그 게인 포스트 컨트롤 오디오 신호 수준을 나타냅니다. 이 메트릭의 단위는 dBmo입니다. 적절 한 품질을 위해서는 30 dBmo 이상 이어야 합니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRecvSignalLevel</p></td>
<td><p>int</p></td>
<td><p>호출 수신자가 받은 오디오에 대 한 오디오 신호 수준입니다. 이 메트릭의 단위는 dBmo입니다. 적절 한 품질을 위해서는 30 dBmo 이상 이어야 합니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>CalleeSendNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>호출 수신자가 보낸 오디오에 대 한 아날로그 게인 사후 제어 오디오 노이즈 수준입니다. 이 메트릭의 단위는 dBmo입니다. 적절 한 품질을 위해서는 35 dBmo 미만 이어야 합니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRecvNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>호출 수신자가 받은 오디오에 대 한 아날로그 게인 사후 제어 오디오 노이즈 수준입니다. 이 메트릭의 단위는 dBmo입니다. 적절 한 품질을 위해서는 35 dBmo 미만 이어야 합니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>CalleeEchoReturn</p></td>
<td><p>int</p></td>
<td><p>호출 수신자에 대 한 에코 반환 손실 보정. 이 메트릭의 단위는 dB입니다. 값이 낮을수록 화면 표시 수준이 낮아집니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeSpeakerGlitchRate</p></td>
<td><p>int</p></td>
<td><p>호출 수신자의 스피커 렌더링에 대 한 5 분 당 평균 결함입니다. 좋은 품질을 위해서는 5 분에 1 보다 작아야 합니다. A/V 회의 서버, 중재 서버 또는 IP 전화기에서 보고 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>CalleeMicGlitchRate</p></td>
<td><p>int</p></td>
<td><p>호출 수신자의 마이크 캡처에 대 한 5 분 당 평균 결함입니다. 좋은 품질을 위해서는 5 분에 1을 미만 이어야 합니다. A/V 회의 서버, 중재 서버 또는 IP 전화기에서 보고 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeTimestampDriftRateMic</p></td>
<td><p>10 진수 (9, 2)</p></td>
<td><p>CPU 클록을 기준으로 피호출자의 마이크 장치 시계 드리프트 속도입니다.</p></td>
</tr>
<tr class="even">
<td><p>CalleeTimestampDriftRateSpk</p></td>
<td><p>10 진수 (9, 2)</p></td>
<td><p>CPU 클록을 기준으로 호출 수신자의 스피커 장치 시계 드리프트 속도입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeTimestampErrorMicMs</p></td>
<td><p>10 진수 (9, 2)</p></td>
<td><p>평균 마이크 캡처 스트림 타임 스탬프 (밀리초) (통화의 마지막 20 초)</p></td>
</tr>
<tr class="even">
<td><p>CalleeTimestampErrorSpkMs</p></td>
<td><p>10 진수 (9, 2)</p></td>
<td><p>호출 수신자의 스피커 평균 마지막 20 초 동안 밀리초 단위의 렌더링 스트림 타임 스탬프 오류</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVsEntryCauses</p></td>
<td><p>smallint</p></td>
<td><p>음성 스위치는 인터럽트 감소 기능이 있는 반 양방향 모드입니다. 자세한 내용은 <a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialine 테이블</a> 을 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p>CalleeEchoEventCauses</p></td>
<td><p>tinyint</p></td>
<td><p>호출 수신자에 대 한 에코 이벤트의 원인입니다. 자세한 내용은 <a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialine 테이블</a> 을 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeEchoPercentMicIn</p></td>
<td><p>10 진수 (5, 2)</p></td>
<td><p>호출 수신자의 마이크 캡처 스트림에서 화면 표시를 감지 하는 시간의 백분율입니다. 헤드셋을 사용 하는 경우 값이 작아야 합니다.</p></td>
</tr>
<tr class="even">
<td><p>CalleeEchoPercentSend</p></td>
<td><p>10 진수 (5, 2)</p></td>
<td><p>호출 수신자의 전송 된 스트림에서 반향을 감지 하는 시간의 백분율입니다. 송신 스트림의 화면 표시 백분율 에코 누수를 나타냅니다.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRxAGCSignalLevel</p></td>
<td><p>int</p></td>
<td><p>게이트웨이에서 호출 수신자의 오디오에 대 한 중재 서버의 신호 수준을 수신 했습니다. 이는 중재 서버에만 적용 됩니다. 이 메트릭의 단위는 dBoV입니다. 좋은 품질을 위해서는 허용 되는 범위는 [-30 ~-18] dBoV 이어야 합니다.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRxAGCNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>게이트웨이에서 호출 수신자의 오디오에 대 한 조정 서버의 신호 수준을 수신 했습니다. 이는 중재 서버에만 적용 됩니다. 이 메트릭의 단위는 dBoV입니다. 좋은 품질을 위해서는 허용 되는 범위가-50 dBoV 미만 이어야 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRxAGCGain</p></td>
<td><p>int</p></td>
<td><p>조정 서버 쪽의 자동 게인 제어 (AGC)를 호출 수신자의 오디오에 적용 했습니다.</p></td>
</tr>
<tr class="even">
<td><p>CalleeInitialSignalLevelRMS</p></td>
<td><p>o</p></td>
<td><p>호출의 처음 30 초까지 수신자에 대 한 수신 신호에 대 한 루트 평균 제곱근 (RMS)입니다.</p></td>
</tr>
<tr class="odd">
<td><p>RatioConcealedSamplesAvg</p></td>
<td><p>10 진수 (5, 2)</p></td>
<td><p>오디오 치유에서 생성 한 숨겨진 샘플의 평균 비율을 일반적인 샘플입니다.</p></td>
</tr>
<tr class="even">
<td><p>RatioStretchedSamplesAvg</p></td>
<td><p>10 진수 (5, 2)</p></td>
<td><p>표준 샘플에 대 한 오디오 치유에서 생성 된 늘이기 샘플의 평균 비율입니다.</p></td>
</tr>
<tr class="odd">
<td><p>RatioCompressedSamplesAvg</p></td>
<td><p>10 진수 (5, 2)</p></td>
<td><p>오디오 치유에서 생성 한 압축 샘플의 평균 비율을 일반적인 샘플로 나타낸 것입니다.</p></td>
</tr>
<tr class="even">
<td><p>왕복이</p></td>
<td><p>int</p></td>
<td><p>RTCP 통계에서 왕복 시간을 계산 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>RoundTripMax</p></td>
<td><p>int</p></td>
<td><p>오디오 스트림의 최대 라운드트립 시간입니다.</p></td>
</tr>
<tr class="even">
<td><p>OverallAvgNetworkMOS</p></td>
<td><p>10 진수 (3, 2)</p></td>
<td><p>통화에 대 한 평균 광대역 네트워크 SPECIALIST. 이 메트릭은 사용 되는 패킷 손실, 지터 및 코덱에 따라 달라 집니다. 범위는 1.0 ~ 5.0입니다.</p></td>
</tr>
<tr class="odd">
<td><p>OverallMinNetworkMOS</p></td>
<td><p>10 진수 (3, 2)</p></td>
<td><p>통화에 대 한 최소 광대역 네트워크 SPECIALIST.</p></td>
</tr>
<tr class="even">
<td><p>SendListenMOS</p></td>
<td><p>10 진수 (3, 2)</p></td>
<td><p>음성 수준, 노이즈 수준 및 캡처 장치 특성을 포함 하 여 전송 되는 오디오에 대 한 평균 예측 광대역 SPECIALIST 점수입니다.</p></td>
</tr>
<tr class="odd">
<td><p>SendListenMOSMin</p></td>
<td><p>10 진수 (3, 2)</p></td>
<td><p>통화에 대 한 최소 SendListenMOS.</p></td>
</tr>
<tr class="even">
<td><p>RecvListenMOS</p></td>
<td><p>10 진수 (3, 2)</p></td>
<td><p>음성 수준, 소음 수준, 코덱, 네트워크 상태 및 캡처 장치 특성을 포함 하 여 네트워크에서 받은 오디오에 대 한 평균 예측 광대역 SPECIALIST 점수입니다.</p></td>
</tr>
<tr class="odd">
<td><p>RecvListenMOSMin</p></td>
<td><p>10 진수 (3, 2)</p></td>
<td><p>통화에 대 한 최소 RecvListenMOS.</p></td>
</tr>
<tr class="even">
<td><p>오디오 및 사용</p></td>
<td><p>다소</p></td>
<td><p>오디오 FEC 통화에 사용 되었는지 여부를 나타냅니다.</p></td>
</tr>
<tr class="odd">
<td><p>SenderIsCallerPAI</p></td>
<td><p>다소</p></td>
<td><p>P-어설션된 식별 정보의 방향을 나타냅니다. 1은 스트림 방향이 호출자에서 호출 수신자 까지의 것임을 의미 합니다. 0은 스트림 방향이 피호출자부터 호출자에 게 있음을 의미 합니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

