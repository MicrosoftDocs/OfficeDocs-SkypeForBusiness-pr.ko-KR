---
title: 'Lync Server 2013: VideoStreamDetail 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: VideoStreamDetail view
ms:assetid: ec8c45e1-307d-40ec-a75e-6083306105f2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721928(v=OCS.15)
ms:contentKeyID: 49733863
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95cc003a0e136a4a4c123355548b95c9566b4b31
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975314"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videostreamdetail-view-in-lync-server-2013"></a>Lync Server 2013의 VideoStreamDetail 보기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-03_

VideoStreamDetail 보기에는 데이터베이스의 각 비디오 스트림에 대 한 정보가 저장 됩니다. 이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.


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
<th>설명</th>
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
<td><p>MediaLineLabel</p></td>
<td><p>tinyint</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialine 테이블</a>에서 참조 합니다.</p></td>
</tr>
<tr class="even">
<td><p>StreamId</p></td>
<td><p>int</p></td>
<td><p>미디어 라인 내의 고유 ID.</p></td>
</tr>
<tr class="odd">
<td><p>StartTime</p></td>
<td><p>dmtf</p></td>
<td><p>세션 시작 시간입니다.</p></td>
</tr>
<tr class="even">
<td><p>EndTime</p></td>
<td><p>dmtf</p></td>
<td><p>세션 종료 시간입니다.</p></td>
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
<td><p>호출 수신자의 끝점에 대 한 CPU 코어 수입니다.</p></td>
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
<td><p>ConnectivityIce</p></td>
<td><p>tinyint</p></td>
<td><p>미디어 경로에 대 한 정보 (예: 직접 또는 릴레이)입니다. 자세한 내용은 <a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialine 테이블</a> 을 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p>CallerIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>호출자의 bits 플래그에 설명 된 ICE (대화형 연결 설정) 프로세스에 대 한 정보입니다. 자세한 내용은 경험의 품질 모니터링 서버 프로토콜 사양을 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p>CalleeIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>호출 수신자의 bits 플래그에 설명 된 ICE (대화형 연결 설정) 프로세스에 대 한 정보입니다. 자세한 내용은 경험의 품질 모니터링 서버 프로토콜 사양을 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p>운송</p></td>
<td><p>int</p></td>
<td><p>전송 종류: 0은 UDP이 고, 1은 TCP입니다.</p></td>
</tr>
<tr class="even">
<td><p>CallerIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>발신자의 IP 주소입니다. IPv4 또는 IPv6 주소 일 수 있습니다.</p></td>
</tr>
<tr class="odd">
<td><p>CallerPort</p></td>
<td><p>int</p></td>
<td><p>호출자가 사용 하는 포트입니다.</p></td>
</tr>
<tr class="even">
<td><p>CallerInside</p></td>
<td><p>다소</p></td>
<td><p>호출자가 조직 네트워크 내에 있는지 여부를 나타냅니다. 1은 발신자가 엔터프라이즈 네트워크 내에 있음을 의미 하 고, 0 이면 발신자가 네트워크 외부에 있음을 의미 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>호출 수신자의 IP 주소입니다. IPv4 또는 IPv6 주소 일 수 있습니다.</p></td>
</tr>
<tr class="even">
<td><p>CalleePort</p></td>
<td><p>int</p></td>
<td><p>호출 수신자가 사용 하는 포트입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeInside</p></td>
<td><p>다소</p></td>
<td><p>호출자가 조직 네트워크 내에 있는지 여부를 나타냅니다. 1은 호출 수신자가 엔터프라이즈 네트워크 내에 있음을 의미 하 고 0은 호출 수신자가 네트워크 외부에 있음을 의미 합니다.</p></td>
</tr>
<tr class="even">
<td><p>CallerUserSite</p></td>
<td><p>name</p></td>
<td><p>호출자 사이트의 이름입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CallerRegion</p></td>
<td><p>name</p></td>
<td><p>발신자 사이트의 국가/지역 이름입니다.</p></td>
</tr>
<tr class="even">
<td><p>CalleeUserSite</p></td>
<td><p>name</p></td>
<td><p>피호출자 사이트의 이름입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRegion</p></td>
<td><p>name</p></td>
<td><p>피호출자 사이트의 국가/지역 이름입니다.</p></td>
</tr>
<tr class="even">
<td><p>CallerRelayIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>발신자가 사용 하는 A/V Edge 서비스의 IP 주소입니다. 자세한 내용은 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013의 IPAddress 테이블</a> 을 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p>CallerRelayPort</p></td>
<td><p>int</p></td>
<td><p>호출자가 사용 하는 A/V에 지 서비스의 포트입니다.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRelayIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>호출 수신자가 사용 하는 A/V Edge 서비스의 IP 주소 키입니다. 자세한 내용은 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013의 IPAddress 테이블</a> 을 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRelayPort</p></td>
<td><p>int</p></td>
<td><p>호출 수신자가 사용 하는 A/V에 지 서비스의 포트입니다.</p></td>
</tr>
<tr class="even">
<td><p>CallerCaptureDev</p></td>
<td><p>varchar (256)</p></td>
<td><p>발신자의 캡처 장치 이름입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CallerRenderDev</p></td>
<td><p>varchar (256)</p></td>
<td><p>발신자의 렌더링 장치 이름.</p></td>
</tr>
<tr class="even">
<td><p>CallerCaptureDevDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>발신자의 캡처 장치 드라이버 이름.</p></td>
</tr>
<tr class="odd">
<td><p>CallerRenderDevDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>호출자의 렌더링 장치 드라이버 이름입니다.</p></td>
</tr>
<tr class="even">
<td><p>CalleeCaptureDev</p></td>
<td><p>varchar (256)</p></td>
<td><p>호출 수신자의 캡처 디바이스 이름입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRenderDev</p></td>
<td><p>varchar (256)</p></td>
<td><p>피호출자의 렌더링 디바이스 이름입니다.</p></td>
</tr>
<tr class="even">
<td><p>CalleCaptureDevDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>피호출자의 캡처 장치 드라이버 이름입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRenderDevDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>피호출자의 렌더링 장치 드라이버 이름입니다.</p></td>
</tr>
<tr class="even">
<td><p>CallerNetworkConnectionType</p></td>
<td><p>tinyint</p></td>
<td><p>발신자의 네트워크 연결 유형: 0이 유선 인 경우 1은 무선입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CallerVPN</p></td>
<td><p>다소</p></td>
<td><p>호출자가 가상 개인 네트워크를 통해 연결 되었는지 여부를 나타냅니다. 1은 VPN (가상 사설망)이 고 0은 VPN이 아닙니다.</p></td>
</tr>
<tr class="even">
<td><p>CallerLinkSpeed</p></td>
<td><p>10 진수 (18,)</p></td>
<td><p>Bps의 호출자 끝점에 대 한 네트워크 링크 속도입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeNetworkConnectionType</p></td>
<td><p>tinyint</p></td>
<td><p>피호출자의 네트워크 연결 형식: 0이 유선 인 경우 1은 무선입니다.</p></td>
</tr>
<tr class="even">
<td><p>CalleeVPN</p></td>
<td><p>다소</p></td>
<td><p>호출 수신자가 가상 개인 네트워크를 통해 연결 되었는지 여부를 나타냅니다. 1은 VPN (가상 사설망)이 고 0은 VPN이 아닙니다.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeLinkSpeed</p></td>
<td><p>10 진수 (18, 0)</p></td>
<td><p>호출 수신자의 끝점에 대 한 네트워크 링크 속도 (bps)입니다.</p></td>
</tr>
<tr class="even">
<td><p>ConversationalMOS</p></td>
<td><p>10 진수 (3, 2)</p></td>
<td><p>오디오 세션의 Narrowband 대화 SPECIALIST (두 오디오 스트림 모두 기준).</p></td>
</tr>
<tr class="odd">
<td><p>AppliedBandwidthLimit</p></td>
<td><p>int</p></td>
<td><p>다양 한 정책 설정 (TURN, API, SDP, 정책 서버 등)을 지정 하 여 지정 된 보내기 쪽 스트림에 실제 대역폭을 적용 했습니다. 대역폭 예측을 기준으로 낮은 유효 대역폭을 사용할 수 있기 때문에 효과적인 대역폭과 혼동 하지 않는 것이 좋습니다. 이 값이 기본적으로 최대 대역폭입니다. 송신 스트림은 대역폭 추정치에 의해 부과 된 제한을 받을 수 있습니다.</p></td>
</tr>
<tr class="even">
<td><p>JitterInterArrival</p></td>
<td><p>int</p></td>
<td><p>RTCP (실시간 제어 프로토콜) 통계의 평균 네트워크 지터입니다.</p></td>
</tr>
<tr class="odd">
<td><p>JitterInterArrivalMax</p></td>
<td><p>int</p></td>
<td><p>통화 중 최대 네트워크 지터.</p></td>
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
<td><p>PacketLossRate</p></td>
<td><p>10 진수 (5, 4)</p></td>
<td><p>통화 중의 평균 패킷 손실 율입니다.</p></td>
</tr>
<tr class="odd">
<td><p>PacketLossRateMax</p></td>
<td><p>10 진수 (5, 4)</p></td>
<td><p>통화 중에 최대 패킷 손실이 관찰 되었습니다.</p></td>
</tr>
<tr class="even">
<td><p>PacketUtilization</p></td>
<td><p>int</p></td>
<td><p>비디오 스트림의 패킷 개수 (리얼 시간 전송 프로토콜, RTP).</p></td>
</tr>
<tr class="odd">
<td><p>BandwidthEst</p></td>
<td><p>int</p></td>
<td><p>오디오 스트림의 대역폭을 예측 합니다.</p></td>
</tr>
<tr class="even">
<td><p>PayloadDescription</p></td>
<td><p>int</p></td>
<td><p><a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013의 PayloadDescription 테이블</a>에서 참조 하는 통화에 사용 되는 오디오 코덱입니다.</p></td>
</tr>
<tr class="odd">
<td><p>VideoResolution</p></td>
<td><p>char (9)</p></td>
<td><p>픽셀 너비를 픽셀 높이로 곱한 비디오 해상도입니다. 문자열로 보고 되었습니다.</p></td>
</tr>
<tr class="even">
<td><p>VideoBitRateAvg</p></td>
<td><p>int</p></td>
<td><p>비디오 스트림의 평균 비트 전송률입니다.</p></td>
</tr>
<tr class="odd">
<td><p>InboundVideoFrameRateAvg</p></td>
<td><p>10 진수 (9, 4)</p></td>
<td><p>수신 된 비디오의 프레임 속도입니다.</p></td>
</tr>
<tr class="even">
<td><p>OutboundVideoFrameRateAvg</p></td>
<td><p>10 진수 (9, 4)</p></td>
<td><p>전송 된 비디오의 프레임 속도입니다.</p></td>
</tr>
<tr class="odd">
<td><p>ViideoBitRateMax</p></td>
<td><p>int</p></td>
<td><p>비디오 세션 중에 최대 비디오 비트 전송률입니다.</p></td>
</tr>
<tr class="even">
<td><p>VideoPacketLossRate</p></td>
<td><p>10 진수 (9, 4)</p></td>
<td><p>비디오 패킷이 손실 된 속도입니다.</p></td>
</tr>
<tr class="odd">
<td><p>VideoFrameLossRate</p></td>
<td><p>10 진수 (9.4)</p></td>
<td><p>손실 된 총 비디오 프레임의 백분율입니다.</p></td>
</tr>
<tr class="even">
<td><p>VideoFEC</p></td>
<td><p>다소</p></td>
<td><p>사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>VideoAllocateBWAvg</p></td>
<td><p>int</p></td>
<td><p>비디오에 대해 할당 된 평균 대역폭 양입니다.</p></td>
</tr>
<tr class="even">
<td><p>VideoLocalFrameLossPercentageAvg</p></td>
<td><p>10 진수 (9.4)</p></td>
<td><p>손실 된 총 비디오 프레임의 백분율입니다.</p></td>
</tr>
<tr class="odd">
<td><p>SenderIsCallerPAI</p></td>
<td><p>다소</p></td>
<td><p>P-어설션된 id 정보에 대 한 스트림 방향입니다. 1은 스트림 방향이 호출자에서 호출 수신자 까지의 것임을 의미 합니다. 0은 스트림 방향이 피호출자부터 호출자에 게 있음을 의미 합니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

