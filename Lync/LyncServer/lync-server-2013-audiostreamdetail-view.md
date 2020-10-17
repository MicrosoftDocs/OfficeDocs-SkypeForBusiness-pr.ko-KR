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
ms.openlocfilehash: 4a9abfbc214e72cf059250910ecec4ad3bcdba33
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515785"
---
# <a name="audiostreamdetail-view-in-lync-server-2013"></a>Lync Server 2013의 오디오 Streamdetail 보기

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-03_

AudioStreamDetail 보기에는 데이터베이스의 각 오디오 스트림에 대한 정보가 저장됩니다. 이 보기는 Microsoft Lync Server 2013에 도입 되었습니다.


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
<th>세부 정보</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>SessionTime</p></td>
<td><p>datetime</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a>에서 참조 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>SessionSeq</p></td>
<td><p>int</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a>에서 참조 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>StreamId</p></td>
<td><p>int</p></td>
<td><p>미디어 회선 내의 고유 ID입니다.</p></td>
</tr>
<tr class="even">
<td><p>StartTime</p></td>
<td><p>datetime</p></td>
<td><p>세션 시작 시간입니다.</p></td>
</tr>
<tr class="odd">
<td><p>EndTime</p></td>
<td><p>datetime</p></td>
<td><p>세션 종료 시간입니다.</p></td>
</tr>
<tr class="even">
<td><p>DialogCategory</p></td>
<td><p>비트만</p></td>
<td><p>대화 상자 범주: 0은 Lync server를 중재 서버 다리에 대 한 것입니다. 1은 PSTN 게이트웨이 레그에 대 한 중재 서버입니다.</p></td>
</tr>
<tr class="odd">
<td><p>MediationServerBypassFlag</p></td>
<td><p>비트만</p></td>
<td><p>통화가 바이패스되었는지 여부를 나타내는 플래그입니다.</p></td>
</tr>
<tr class="even">
<td><p>MediaBypassWarningFlag</p></td>
<td><p>int</p></td>
<td><p>이 필드는(제공된 경우) 바이패스 ID가 일치한 경우에도 통화가 바이패스되지 않은 이유를 나타냅니다. 하나의 값만 정의되어 있습니다.</p>
<p>0x0001 -  기본 네트워크 어댑터에 대한 알 수 없는 바이패스 ID입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CallPriority</p></td>
<td><p>int</p></td>
<td><p>통화 우선 순위입니다.</p></td>
</tr>
<tr class="even">
<td><p>CallerPool</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>발신자 풀 FQDN입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CalleePool</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>수신자 풀 FQDN입니다.</p></td>
</tr>
<tr class="even">
<td><p>최초</p></td>
<td><p>nvarchar (450)</p></td>
<td><p>발신자의 URI입니다.</p></td>
</tr>
<tr class="odd">
<td><p>피호출자</p></td>
<td><p>nvarchar (450)</p></td>
<td><p>수신자의 URI입니다.</p></td>
</tr>
<tr class="even">
<td><p>CallerUserAgent</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>발신자의 사용자 에이전트 문자열입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CallerUserAgentType</p></td>
<td><p>smallint</p></td>
<td><p>발신자의 사용자 에이전트 유형입니다. 자세한 내용은 <a href="lync-server-2013-useragent-table.md">Lync Server 2013의 UserAgent 테이블</a> 을 참조 하십시오.</p></td>
</tr>
<tr class="even">
<td><p>CallerUserAgentCategory</p></td>
<td><p>nvarchar (64)</p></td>
<td><p>발신자의 사용자 에이전트 범주입니다. 자세한 내용은 <a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013의 Useragentdef 테이블 (QoE)</a> 을 참조 하십시오.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserAgent</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>수신자의 사용자 에이전트 문자열입니다.</p></td>
</tr>
<tr class="even">
<td><p>CalleeUserAgentType</p></td>
<td><p>smallint</p></td>
<td><p>수신자의 사용자 에이전트 형식입니다. 자세한 내용은 <a href="lync-server-2013-useragent-table.md">Lync Server 2013의 UserAgent 테이블</a> 을 참조 하십시오.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserAgentCategory</p></td>
<td><p>nvarchar (64)</p></td>
<td><p>수신자의 사용자 에이전트 범주입니다. 자세한 내용은 <a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013의 Useragentdef 테이블 (QoE)</a> 을 참조 하십시오.</p></td>
</tr>
<tr class="even">
<td><p>CallerEndpoint</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>발신자의 끝점 이름입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeEndpoint</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>수신자의 끝점 이름입니다.</p></td>
</tr>
<tr class="even">
<td><p>CallerOS</p></td>
<td><p>name</p></td>
<td><p>발신자의 끝점 OS(운영 체제)입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeOS</p></td>
<td><p>name</p></td>
<td><p>수신자의 끝점 OS(운영 체제)입니다.</p></td>
</tr>
<tr class="even">
<td><p>CallerCPUName</p></td>
<td><p>name</p></td>
<td><p>발신자의 끝점 CPU 이름입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCPUName</p></td>
<td><p>name</p></td>
<td><p>수신자의 끝점 CPU 이름입니다.</p></td>
</tr>
<tr class="even">
<td><p>CallerCPUNumberOfCores</p></td>
<td><p>smallint</p></td>
<td><p>발신자 끝점의 CPU 코어 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCPUNumberOfCores</p></td>
<td><p>smallint</p></td>
<td><p>수신자 끝점의 CPU 코어 수입니다.</p></td>
</tr>
<tr class="even">
<td><p>CallerCPUProcessorSpeed</p></td>
<td><p>int</p></td>
<td><p>발신자의 끝점 CPU 프로세서 속도입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCPUProcessorSpeed</p></td>
<td><p>int</p></td>
<td><p>수신자의 끝점 CPU 프로세서 속도입니다.</p></td>
</tr>
<tr class="even">
<td><p>CallerVirtualizationFlag</p></td>
<td><p>tinyint</p></td>
<td><p>발신자의 시스템이 가상화된 환경에서 실행 중인 여부를 나타냅니다. 자세한 내용은 <a href="lync-server-2013-endpoint-table.md">Lync Server 2013의 Endpoint table</a> 를 참조 하십시오.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVirtualizationFlag</p></td>
<td><p>tinyint</p></td>
<td><p>수신자의 시스템이 가상화된 환경에서 실행 중인 여부를 나타냅니다. 자세한 내용은 <a href="lync-server-2013-endpoint-table.md">Lync Server 2013의 Endpoint table</a> 를 참조 하십시오.</p></td>
</tr>
<tr class="even">
<td><p>CorrelationKey</p></td>
<td></td>
<td><p>상관 관계 키입니다. <a href="lync-server-2013-sessioncorrelation-table.md">Lync Server 2013의 Sessioncorrelation 관계 테이블</a>에서 참조 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>ConnectivityIce</p></td>
<td><p>tinyint</p></td>
<td><p>직접 또는 중계와 같은 미디어 경로에 대한 정보입니다. 자세한 내용은 <a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a> 를 참조 하십시오.</p></td>
</tr>
<tr class="even">
<td><p>CallerIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>비트 플래그로 설명된 발신자 측 ICE(Interactive Connectivity Establishment) 프로세스에 대한 정보입니다. 자세한 내용은 체감 품질 모니터링 서버 프로토콜 사양을 참조하십시오.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>비트 플래그로 설명된 수신자 측 ICE(Interactive Connectivity Establishment) 프로세스에 대한 대한 정보입니다. 자세한 내용은 체감 품질 모니터링 서버 프로토콜 사양을 참조하십시오.</p></td>
</tr>
<tr class="even">
<td><p>전송</p></td>
<td><p>tinyint</p></td>
<td><p>전송 종류: 0은 UDP, 1은 TCP입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CallerIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>발신자의 IP 주소입니다. 이 주소는 IPv4 또는 IPv6 주소일 수 있습니다.</p></td>
</tr>
<tr class="even">
<td><p>CallerPort</p></td>
<td><p>int</p></td>
<td><p>발신자가 사용하는 포트입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CallerInside</p></td>
<td><p>비트만</p></td>
<td><p>발신자가 내부 네트워크에 있는지 여부를 나타냅니다. 1은 발신자가 회사 네트워크 내에 있음을 의미하고 0은 발신자가 네트워크 외부에 있음을 의미합니다.</p></td>
</tr>
<tr class="even">
<td><p>CalleeIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>수신자의 IP 주소입니다. 이 주소는 IPv4 또는 IPv6 주소일 수 있습니다.</p></td>
</tr>
<tr class="odd">
<td><p>CalleePort</p></td>
<td><p>int</p></td>
<td><p>수신자가 사용하는 포트입니다.</p></td>
</tr>
<tr class="even">
<td><p>CalleeInside</p></td>
<td><p>비트만</p></td>
<td><p>수신자가 내부 네트워크에 있는지 여부를 나타냅니다. 1은 수신자가 회사 네트워크 내에 있음을 의미하고 0은 수신자가 네트워크 외부에 있음을 의미합니다.</p></td>
</tr>
<tr class="odd">
<td><p>CallerUserSite</p></td>
<td><p>name</p></td>
<td><p>발신자 사이트 이름입니다.</p></td>
</tr>
<tr class="even">
<td><p>CallerRegion</p></td>
<td><p>name</p></td>
<td><p>발신자 사이트의 국가/지역 이름입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserSite</p></td>
<td><p>name</p></td>
<td><p>수신자 사이트 이름입니다.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRegion</p></td>
<td><p>name</p></td>
<td><p>수신자 사이트의 국가/지역 이름입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CallerRelayIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>A/V 에지 서비스에서 발신자가 사용하는 IP 주소입니다. 자세한 내용은 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013의 IPAddress 표</a> 를 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p>CallerRelayPort</p></td>
<td><p>int</p></td>
<td><p>발신자가 사용하는 A/V 에지 서비스에서 사용되는 포트입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRelayIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>A/V 에지 서비스에서 수신자가 사용하는 IP 주소 키입니다. 자세한 내용은 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013의 IPAddress 표</a> 를 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRelayPort</p></td>
<td><p>int</p></td>
<td><p>수신자가 사용하는 A/V 에지 서비스에서 사용되는 포트입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CallerCaptureDev</p></td>
<td><p>varchar (256)</p></td>
<td><p>발신자의 캡처 장치 이름입니다.</p></td>
</tr>
<tr class="even">
<td><p>CallerRenderDev</p></td>
<td><p>varchar (256)</p></td>
<td><p>발신자의 렌더링 장치 이름입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CallerCaptureDevDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>발신자의 캡처 장치 드라이버 이름입니다.</p></td>
</tr>
<tr class="even">
<td><p>CallerRenderDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>발신자의 렌더링 장치 드라이버 이름입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCaptureDev</p></td>
<td><p>varchar (256)</p></td>
<td><p>수신자의 캡처 장치 이름입니다.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRenderDev</p></td>
<td><p>varchar (256)</p></td>
<td><p>수신자의 렌더링 장치 이름입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCaptureDevDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>수신자의 캡처 장치 드라이버 이름입니다.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRenderDevDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>수신자의 렌더링 장치 드라이버 이름입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CallerNetworkConnectionType</p></td>
<td><p>tinyint</p></td>
<td><p>발신자의 네트워크 연결 형식입니다. 0은 유선, 1은 무선입니다.</p></td>
</tr>
<tr class="even">
<td><p>CallerVPN</p></td>
<td><p>비트만</p></td>
<td><p>발신자가 가상 사설망을 통해 연결되어 있는지 여부를 나타냅니다.1은 VPN(가상 사설망), 0은 VPN 외입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CallerLinkSpeed</p></td>
<td><p>10 진수 (18, 0)</p></td>
<td><p>발신자의 끝점에 대한 네트워크 연결 속도(bps)입니다.</p></td>
</tr>
<tr class="even">
<td><p>CalleeNetworkConnectionType</p></td>
<td><p>tinyint</p></td>
<td><p>수신자의 네트워크 연결 형식입니다. 0은 유선, 1은 무선입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVPN</p></td>
<td><p>비트만</p></td>
<td><p>수신자가 가상 사설망을 통해 연결되어 있는지 여부를 나타냅니다.1은 VPN(가상 사설망), 0은 VPN 외입니다.</p></td>
</tr>
<tr class="even">
<td><p>CalleeLinkSpeed</p></td>
<td><p>10 진수 (18, 0)</p></td>
<td><p>수신자의 끝점에 대한 네트워크 연결 속도(bps)입니다.</p></td>
</tr>
<tr class="odd">
<td><p>ConversationalMOS</p></td>
<td><p>10 진수 (3, 2)</p></td>
<td><p>오디오 세션의 협대역 대화 MOS입니다(두 오디오 스트림을 모두 기반으로 함).</p></td>
</tr>
<tr class="even">
<td><p>AppliedBandwidthLimit</p></td>
<td><p>int</p></td>
<td><p>다양한 정책 설정(TURN, API, SDP, 정책 서버 등)이 제공된 지정된 송신측 스트림에 적용되는 실제 대역폭입니다. 이 대역폭은 대역폭 예상에 따라 유효 대역폭이 더 낮을 수 있으므로 유효 대역폭과 혼동해서는 안됩니다. 이 대역폭은 기본적으로 대역폭 예상치로 지정된 한도를 제외하고 송신 스트림이 사용할 수 있는 최대 대역폭입니다.</p></td>
</tr>
<tr class="odd">
<td><p>JitterInterArrival</p></td>
<td><p>int</p></td>
<td><p>RTCP(Real Time Control Protocol) 통계로부터 가져온 평균 네트워크 지터입니다.</p></td>
</tr>
<tr class="even">
<td><p>JitterInterArrivalMax</p></td>
<td><p>int</p></td>
<td><p>통화 중 최대 네트워크 지터입니다.</p></td>
</tr>
<tr class="odd">
<td><p>PacketLossRate</p></td>
<td><p>10 진수 (5, 4)</p></td>
<td><p>통화 중 평균 패킷 손실 비율입니다.</p></td>
</tr>
<tr class="even">
<td><p>PacketLossRateMax</p></td>
<td><p>10 진수 (5, 4)</p></td>
<td><p>통화 중 관측된 최대 패킷 손실량입니다.</p></td>
</tr>
<tr class="odd">
<td><p>버스트 밀도</p></td>
<td><p>10 진수 (9, 4)</p></td>
<td><p>통화 중 손실량이 많아지는 기간 동안의 평균 패킷 손실 밀도입니다.</p></td>
</tr>
<tr class="even">
<td><p>BurstDuration</p></td>
<td><p>int</p></td>
<td><p>통화 중 손실량이 많아지는 기간 동안의 평균 패킷 손실 기간입니다.</p></td>
</tr>
<tr class="odd">
<td><p>BurstGapDensity</p></td>
<td><p>10 진수 (9, 4)</p></td>
<td><p>패킷 손실이 최고치인 기간 사이의 간격 중에 발생하는 평균 패킷 손실 밀도입니다.</p></td>
</tr>
<tr class="even">
<td><p>BurstGapDuration</p></td>
<td><p>int</p></td>
<td><p>패킷 손실이 최고치인 기간 사이의 간격에 대한 평균 기간입니다.</p></td>
</tr>
<tr class="odd">
<td><p>PacketUtilization</p></td>
<td><p>int</p></td>
<td><p>오디오 스트림에 대한 패킷 수입니다.</p></td>
</tr>
<tr class="even">
<td><p>BandwidthEst</p></td>
<td><p>int</p></td>
<td><p>오디오 스트림에 대한 대역폭 예상치입니다.</p></td>
</tr>
<tr class="odd">
<td><p>DegradationAvg</p></td>
<td><p>10 진수 (3, 2)</p></td>
<td><p>전체 통화에 대한 네트워크 MOS 저하입니다. 범위는 0.0에서 5.0까지입니다. 이 메트릭은 지터 및 패킷 손실로 인해 감소된 네트워크 MOS의 양을 보여 줍니다. 적정 품질을 위해서는 0.5 미만이어야 합니다.</p></td>
</tr>
<tr class="even">
<td><p>DegradationMax</p></td>
<td><p>10 진수 (3, 2)</p></td>
<td><p>통화 중 최대 네트워크 MOS 저하입니다.</p></td>
</tr>
<tr class="odd">
<td><p>DegradationJitterAvg</p></td>
<td><p>10 진수 (3, 2)</p></td>
<td><p>지터로 인해 발생한 네트워크 MOS 저하입니다.</p></td>
</tr>
<tr class="even">
<td><p>DegradationPacketLossAvg</p></td>
<td><p>10 진수 (3, 2)</p></td>
<td><p>패킷 손실로 인해 발생한 네트워크 MOS 저하입니다.</p></td>
</tr>
<tr class="odd">
<td><p>PayloadDescription</p></td>
<td><p>int</p></td>
<td><p><a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013의 PayloadDescription 테이블</a>에서 참조 되는 통화에 사용 되는 오디오 코덱입니다.</p></td>
</tr>
<tr class="even">
<td><p>AudioSampleRate</p></td>
<td><p>int</p></td>
<td><p>오디오 스트림에 대한 샘플링 속도입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CallerSendSignalLevel</p></td>
<td><p>int</p></td>
<td><p>발신자가 전송한 오디오의 포스트 아날로그 게인 컨트롤 오디오 신호 수준입니다. 이 메트릭의 단위는 dBmo입니다. 적정 품질을 위해서는 최소 30 dBmo여야 합니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>CallerRecvSignalLevel</p></td>
<td><p>int</p></td>
<td><p>발신자가 수신한 오디오의 오디오 신호 수준입니다. 이 메트릭의 단위는 dBmo입니다. 적정 품질을 위해서는 최소 30 dBmo여야 합니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>CallerSendNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>발신자가 전송한 오디오의 포스트 아날로그 게인 컨트롤 오디오 소음 수준입니다. 이 메트릭의 단위는 dBmo입니다. 적정 품질을 위해서는 35 dBmo 미만이어야 합니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>CallerRecvNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>발신자가 수신한 오디오의 포스트 아날로그 게인 컨트롤 오디오 소음 수준입니다. 이 메트릭의 단위는 dBmo입니다. 적정 품질을 위해서는 35 dBmo 미만이어야 합니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>CallerEchoReturn</p></td>
<td><p>int</p></td>
<td><p>발신자의 에코 반환 손실 향상 메트릭입니다. 이 메트릭의 단위는 dB입니다. 값이 낮으면 에코가 적습니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>CallerSpeakerGlitchRate</p></td>
<td><p>int</p></td>
<td><p>발신자의 스피커 렌더링에 대한 5분당 평균 결함 비율입니다. 적정 품질을 위해서는 5분당 1 미만이어야 합니다. A/V 회의 서버, 중재 서버 또는 IP 전화에서 보고되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>CallerMicGlitchRate</p></td>
<td><p>int</p></td>
<td><p>발신자의 마이크 캡처에 대한 5분당 평균 결함 비율입니다. 적정 품질을 위해서는 5분당 1 미만이어야 합니다. A/V 회의 서버, 중재 서버 또는 IP 전화에서 보고되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>CallerTimestampDriftRateMic</p></td>
<td><p>10 진수 (9, 2)</p></td>
<td><p>CPU 클럭 대비 발신자 마이크 장치의 클럭 드리프트 비율입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CallerTimestampDriftRateSpk</p></td>
<td><p>10 진수 (9, 2)</p></td>
<td><p>CPU 클럭 대비 발신자 스피커 장치의 클럭 드리프트 비율입니다.</p></td>
</tr>
<tr class="even">
<td><p>CallerTimestampErrorMicMs</p></td>
<td><p>10 진수 (9, 2)</p></td>
<td><p>통화의 최근 20초 동안 발생한 평균 마이크 캡처 스트림 타임스탬프 오류(밀리초)입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CallerTimestampErrorSpkMs</p></td>
<td><p>10 진수 (9, 2)</p></td>
<td><p>통화의 최근 20초 동안 발생한 발신자의 평균 스피커 렌더링 스트림 타임스탬프 오류(밀리초)입니다.</p></td>
</tr>
<tr class="even">
<td><p>CallerVsEntryCauses</p></td>
<td><p>smallint</p></td>
<td><p>음성 스위치는 중단 기능이 감소된 반이중 모드입니다. 자세한 내용은 <a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a> 를 참조 하십시오.</p></td>
</tr>
<tr class="odd">
<td><p>CallerEchoEventCauses</p></td>
<td><p>tinyint</p></td>
<td><p>발신자의 에코 이벤트의 원인입니다. 자세한 내용은 <a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a> 를 참조 하십시오.</p></td>
</tr>
<tr class="even">
<td><p>CallerEchoPercentMicIn</p></td>
<td><p>10 진수 (5, 2)</p></td>
<td><p>발신자의 마이크 캡처 스트림에서 에코가 감지되는 시간의 비율입니다. 헤드셋을 사용할 경우 값이 낮아집니다.</p></td>
</tr>
<tr class="odd">
<td><p>CallerEchoPercentSend</p></td>
<td><p>10 진수 (5, 2)</p></td>
<td><p>발신자의 전송된 스트림에서 에코가 감지되는 시간의 비율입니다. 전송 스트림에서 에코 비율이 높으면 에코 누출을 나타낼 수 있습니다.</p></td>
</tr>
<tr class="even">
<td><p>CallerRxAGCSignalLevel</p></td>
<td><p>int</p></td>
<td><p>중재 서버에서 발신자 오디오 게이트웨이로부터 수신된 신호 수준입니다. 중재 서버에만 적용됩니다. 이 메트릭의 단위는 dBoV입니다. 적정 품질을 위해 허용되는 범위는 [-30 ~ -18] dBoV입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CallerRxAGCNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>중재 서버에서 발신자 오디오 게이트웨이로부터 수신된 신호 수준입니다. 중재 서버에만 적용됩니다. 이 메트릭의 단위는 dBoV입니다. 적정 품질을 위해 허용되는 범위는 -50 dBoV 미만입니다.</p></td>
</tr>
<tr class="even">
<td><p>CallerRxAGCGain</p></td>
<td><p>int</p></td>
<td><p>발신자 오디오에 적용되는 중재 서버 쪽의 AGC(자동 게인 컨트롤)입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CallerInitialSignalLevelRMS</p></td>
<td><p>식</p></td>
<td><p>통화 초반의 최대 30초 동안 발신자에게 수신되는 신호의 RMS(제곱 평균 오차)입니다.</p></td>
</tr>
<tr class="even">
<td><p>CalleeSendSignalLevel</p></td>
<td><p>int</p></td>
<td><p>수신자가 전송한 오디오의 포스트 아날로그 게인 컨트롤 오디오 신호 수준을 나타냅니다. 이 메트릭의 단위는 dBmo입니다. 적정 품질을 위해서는 최소 30 dBmo여야 합니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRecvSignalLevel</p></td>
<td><p>int</p></td>
<td><p>수신자가 수신한 오디오의 오디오 신호 수준입니다. 이 메트릭의 단위는 dBmo입니다. 적정 품질을 위해서는 최소 30 dBmo여야 합니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>CalleeSendNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>수신자가 전송한 오디오의 포스트 아날로그 게인 컨트롤 오디오 소음 수준입니다. 이 메트릭의 단위는 dBmo입니다. 적정 품질을 위해서는 35 dBmo 미만이어야 합니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRecvNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>수신자가 수신한 오디오의 포스트 아날로그 게인 컨트롤 오디오 소음 수준입니다. 이 메트릭의 단위는 dBmo입니다. 적정 품질을 위해서는 35 dBmo 미만이어야 합니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>CalleeEchoReturn</p></td>
<td><p>int</p></td>
<td><p>수신자의 에코 반환 손실 향상 메트릭입니다. 이 메트릭의 단위는 dB입니다. 값이 낮으면 에코가 적습니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeSpeakerGlitchRate</p></td>
<td><p>int</p></td>
<td><p>수신자의 스피커 렌더링에 대한 5분당 평균 결함 비율입니다. 적정 품질을 위해서는 5분당 1 미만이어야 합니다. A/V 회의 서버, 중재 서버 또는 IP 전화에서 보고되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>CalleeMicGlitchRate</p></td>
<td><p>int</p></td>
<td><p>수신자의 마이크 캡처에 대한 5분당 평균 결함 비율입니다. 적정 품질을 위해서는 5분당 1 미만이어야 합니다. A/V 회의 서버, 중재 서버 또는 IP 전화에서 보고되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeTimestampDriftRateMic</p></td>
<td><p>10 진수 (9, 2)</p></td>
<td><p>CPU 클럭 대비 수신자 마이크 장치의 클럭 드리프트 비율입니다.</p></td>
</tr>
<tr class="even">
<td><p>CalleeTimestampDriftRateSpk</p></td>
<td><p>10 진수 (9, 2)</p></td>
<td><p>CPU 클럭 대비 수신자 스피커 장치의 클럭 드리프트 비율입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeTimestampErrorMicMs</p></td>
<td><p>10 진수 (9, 2)</p></td>
<td><p>통화의 최근 20초 동안 발생한 평균 마이크 캡처 스트림 타임스탬프 오류(밀리초)입니다.</p></td>
</tr>
<tr class="even">
<td><p>CalleeTimestampErrorSpkMs</p></td>
<td><p>10 진수 (9, 2)</p></td>
<td><p>통화의 최근 20초 동안 발생한 수신자의 평균 스피커 렌더링 스트림 타임스탬프 오류(밀리초)입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVsEntryCauses</p></td>
<td><p>smallint</p></td>
<td><p>음성 스위치는 중단 기능이 감소된 반이중 모드입니다. 자세한 내용은 <a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a> 를 참조 하십시오.</p></td>
</tr>
<tr class="even">
<td><p>CalleeEchoEventCauses</p></td>
<td><p>tinyint</p></td>
<td><p>수신자의 에코 이벤트의 원인입니다. 자세한 내용은 <a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a> 를 참조 하십시오.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeEchoPercentMicIn</p></td>
<td><p>10 진수 (5, 2)</p></td>
<td><p>수신자의 마이크 캡처 스트림에서 에코가 감지되는 시간의 비율입니다. 헤드셋을 사용할 경우 값이 낮아집니다.</p></td>
</tr>
<tr class="even">
<td><p>CalleeEchoPercentSend</p></td>
<td><p>10 진수 (5, 2)</p></td>
<td><p>수신자의 전송된 스트림에서 에코가 감지되는 시간의 비율입니다. 전송 스트림에서 에코 비율이 높으면 에코 누출을 나타낼 수 있습니다.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRxAGCSignalLevel</p></td>
<td><p>int</p></td>
<td><p>중재 서버에서 수신자 오디오 게이트웨이로부터 수신된 신호 수준입니다. 중재 서버에만 적용됩니다. 이 메트릭의 단위는 dBoV입니다. 적정 품질을 위해 허용되는 범위는 [-30 ~ -18] dBoV입니다.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRxAGCNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>중재 서버에서 수신자 오디오 게이트웨이로부터 수신된 신호 수준입니다. 중재 서버에만 적용됩니다. 이 메트릭의 단위는 dBoV입니다. 적정 품질을 위해 허용되는 범위는 -50 dBoV 미만입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRxAGCGain</p></td>
<td><p>int</p></td>
<td><p>수신자 오디오에 적용되는 중재 서버 쪽의 AGC(자동 게인 컨트롤)입니다.</p></td>
</tr>
<tr class="even">
<td><p>CalleeInitialSignalLevelRMS</p></td>
<td><p>식</p></td>
<td><p>통화 초반의 최대 30초 동안 수신자에게 수신되는 신호의 RMS(제곱 평균 오차)입니다.</p></td>
</tr>
<tr class="odd">
<td><p>RatioConcealedSamplesAvg</p></td>
<td><p>10 진수 (5, 2)</p></td>
<td><p>일반 샘플에 대한 오디오 힐링으로 생성된 숨겨진 평균 샘플 비율입니다.</p></td>
</tr>
<tr class="even">
<td><p>RatioStretchedSamplesAvg</p></td>
<td><p>10 진수 (5, 2)</p></td>
<td><p>일반 샘플에 대한 오디오 힐링으로 생성된 평균 늘임 샘플 비율입니다.</p></td>
</tr>
<tr class="odd">
<td><p>RatioCompressedSamplesAvg</p></td>
<td><p>10 진수 (5, 2)</p></td>
<td><p>일반 샘플에 대한 오디오 힐링으로 생성된 숨겨진 압축 샘플 비율입니다.</p></td>
</tr>
<tr class="even">
<td><p>왕복</p></td>
<td><p>int</p></td>
<td><p>RTCP 통계로부터의 왕복 시간입니다.</p></td>
</tr>
<tr class="odd">
<td><p>RoundTripMax</p></td>
<td><p>int</p></td>
<td><p>오디오 스트림에 대한 최대 왕복 시간입니다.</p></td>
</tr>
<tr class="even">
<td><p>OverallAvgNetworkMOS</p></td>
<td><p>10 진수 (3, 2)</p></td>
<td><p>통화에 대한 평균 광대역 네트워크 MOS입니다. 이 메트릭은 패킷 손실, 지터 및 사용된 코덱에 따라 달라집니다. 범위는 1.0 ~ 5.0입니다.</p></td>
</tr>
<tr class="odd">
<td><p>OverallMinNetworkMOS</p></td>
<td><p>10 진수 (3, 2)</p></td>
<td><p>통화에 대한 최소 광대역 네트워크 MOS입니다.</p></td>
</tr>
<tr class="even">
<td><p>SendListenMOS</p></td>
<td><p>10 진수 (3, 2)</p></td>
<td><p>음성 수준, 잡음 수준 및 캡처 장치 특성을 포함하여 전송된 오디오에 대한 평균 예측 광대역 청취 MOS 점수입니다.</p></td>
</tr>
<tr class="odd">
<td><p>SendListenMOSMin</p></td>
<td><p>10 진수 (3, 2)</p></td>
<td><p>통화에 대한 최소 SendListenMOS입니다.</p></td>
</tr>
<tr class="even">
<td><p>RecvListenMOS</p></td>
<td><p>10 진수 (3, 2)</p></td>
<td><p>음성 수준, 잡음 수준, 코덱, 네트워크 조건 및 캡처 장치 특성을 포함하여 수신된 오디오에 대한 평균 예측 광대역 청취 MOS 점수입니다.</p></td>
</tr>
<tr class="odd">
<td><p>RecvListenMOSMin</p></td>
<td><p>10 진수 (3, 2)</p></td>
<td><p>통화에 대한 최소 RecvListenMOS입니다.</p></td>
</tr>
<tr class="even">
<td><p>오디오 \ Ecused</p></td>
<td><p>비트만</p></td>
<td><p>통화에 오디오 FEC가 사용되었는지 여부를 나타냅니다.</p></td>
</tr>
<tr class="odd">
<td><p>SenderIsCallerPAI</p></td>
<td><p>비트만</p></td>
<td><p>P-Asserted-Identity 정보의 방향을 나타냅니다. 1은 스트림 방향이 발신자에서 수신자의 방향임을 의미하고, 0은 스트림 방향이 수신자에서 발신자의 방향임을 의미합니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

