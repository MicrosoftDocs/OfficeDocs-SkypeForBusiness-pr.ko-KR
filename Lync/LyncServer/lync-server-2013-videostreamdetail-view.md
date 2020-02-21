---
title: 'Lync Server 2013: VideoStreamDetail 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VideoStreamDetail view
ms:assetid: ec8c45e1-307d-40ec-a75e-6083306105f2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721928(v=OCS.15)
ms:contentKeyID: 49733863
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e9b6cc13721ff249d9f8bd8bc0c38260c4ca7f55
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211624"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="videostreamdetail-view-in-lync-server-2013"></a>Lync Server 2013의 VideoStreamDetail 보기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-03_

VideoStreamDetail 보기는 데이터베이스에 각 비디오 스트림에 대한 정보를 저장합니다. 이 보기는 Microsoft Lync Server 2013에 도입 되었습니다.


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
<td><p>datetime</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a>에서 참조 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>SessionSeq</p></td>
<td><p>int</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a>에서 참조 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>MediaLineLabel</p></td>
<td><p>tinyint</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a>에서 참조 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>StreamId</p></td>
<td><p>int</p></td>
<td><p>미디어 회선 내의 고유 ID입니다.</p></td>
</tr>
<tr class="odd">
<td><p>StartTime</p></td>
<td><p>datetime</p></td>
<td><p>세션 시작 시간입니다.</p></td>
</tr>
<tr class="even">
<td><p>EndTime</p></td>
<td><p>datetime</p></td>
<td><p>세션 종료 시간입니다.</p></td>
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
<td><p>발신자의 사용자 에이전트 형식입니다. 자세한 내용은 <a href="lync-server-2013-useragent-table.md">Lync Server 2013의 UserAgent 테이블</a> 을 참조 하십시오.</p></td>
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
<td><p>발신자의 끝점 CPU 코어 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCPUNumberOfCores</p></td>
<td><p>smallint</p></td>
<td><p>수신자의 끝점 CPU 코어 수입니다.</p></td>
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
<td><p>ConnectivityIce</p></td>
<td><p>tinyint</p></td>
<td><p>직접 또는 중계와 같은 미디어 경로에 대한 정보입니다. 자세한 내용은 <a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a> 를 참조 하십시오.</p></td>
</tr>
<tr class="odd">
<td><p>CallerIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>비트 플래그로 설명된 발신자 측 ICE(Interactive Connectivity Establishment) 프로세스에 대한 정보입니다. 자세한 내용은 체감 품질 모니터링 서버 프로토콜 사양을 참조하십시오.</p></td>
</tr>
<tr class="even">
<td><p>CalleeIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>비트 플래그로 설명된 수신자 측 ICE(Interactive Connectivity Establishment) 프로세스에 대한 대한 정보입니다. 자세한 내용은 체감 품질 모니터링 서버 프로토콜 사양을 참조하십시오.</p></td>
</tr>
<tr class="odd">
<td><p>전송</p></td>
<td><p>int</p></td>
<td><p>전송 종류: 0은 UDP, 1은 TCP입니다.</p></td>
</tr>
<tr class="even">
<td><p>CallerIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>발신자의 IP 주소입니다. 이 주소는 IPv4 또는 IPv6 주소일 수 있습니다.</p></td>
</tr>
<tr class="odd">
<td><p>CallerPort</p></td>
<td><p>int</p></td>
<td><p>발신자가 사용하는 포트입니다.</p></td>
</tr>
<tr class="even">
<td><p>CallerInside</p></td>
<td><p>비트만</p></td>
<td><p>발신자가 조직 네트워크 내부에 있는지 여부를 나타냅니다. 1은 발신자가 회사 네트워크 내에 있음을 의미하고 0은 발신자가 네트워크 외부에 있음을 의미합니다.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>수신자의 IP 주소입니다. 이 주소는 IPv4 또는 IPv6 주소일 수 있습니다.</p></td>
</tr>
<tr class="even">
<td><p>CalleePort</p></td>
<td><p>int</p></td>
<td><p>수신자가 사용하는 포트입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeInside</p></td>
<td><p>비트만</p></td>
<td><p>수신자가 조직 네트워크 내부에 있는지 여부를 나타냅니다. 1은 발신자가 회사 네트워크 내에 있음을 의미하고 0은 발신자가 네트워크 외부에 있음을 의미합니다.</p></td>
</tr>
<tr class="even">
<td><p>CallerUserSite</p></td>
<td><p>name</p></td>
<td><p>발신자 사이트 이름입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CallerRegion</p></td>
<td><p>name</p></td>
<td><p>발신자 사이트의 국가/지역 이름입니다.</p></td>
</tr>
<tr class="even">
<td><p>CalleeUserSite</p></td>
<td><p>name</p></td>
<td><p>수신자 사이트 이름입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRegion</p></td>
<td><p>name</p></td>
<td><p>수신자 사이트의 국가/지역 이름입니다.</p></td>
</tr>
<tr class="even">
<td><p>CallerRelayIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>A/V 에지 서비스에서 발신자가 사용하는 IP 주소입니다. 자세한 내용은 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013의 IPAddress 표</a> 를 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p>CallerRelayPort</p></td>
<td><p>int</p></td>
<td><p>A/V 에지 서비스에서 발신자가 사용하는 포트입니다.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRelayIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>A/V 에지 서비스에서 수신자가 사용하는 IP 주소 키입니다. 자세한 내용은 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013의 IPAddress 표</a> 를 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRelayPort</p></td>
<td><p>int</p></td>
<td><p>A/V 에지 서비스에서 수신자가 사용하는 포트입니다.</p></td>
</tr>
<tr class="even">
<td><p>CallerCaptureDev</p></td>
<td><p>varchar (256)</p></td>
<td><p>발신자의 캡처 장치 이름입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CallerRenderDev</p></td>
<td><p>varchar (256)</p></td>
<td><p>발신자의 렌더링 장치 이름입니다.</p></td>
</tr>
<tr class="even">
<td><p>CallerCaptureDevDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>발신자의 캡처 장치 드라이버 이름입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CallerRenderDevDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>발신자의 렌더링 장치 드라이버 이름입니다.</p></td>
</tr>
<tr class="even">
<td><p>CalleeCaptureDev</p></td>
<td><p>varchar (256)</p></td>
<td><p>수신자의 캡처 장치 이름입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRenderDev</p></td>
<td><p>varchar (256)</p></td>
<td><p>수신자의 렌더링 장치 이름입니다.</p></td>
</tr>
<tr class="even">
<td><p>CalleCaptureDevDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>수신자의 캡처 장치 드라이버 이름입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRenderDevDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>수신자의 렌더링 장치 드라이버 이름입니다.</p></td>
</tr>
<tr class="even">
<td><p>CallerNetworkConnectionType</p></td>
<td><p>tinyint</p></td>
<td><p>발신자의 네트워크 연결 형식입니다. 0은 유선, 1은 무선입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CallerVPN</p></td>
<td><p>비트만</p></td>
<td><p>발신자가 VPN(가상 사설망)을 통해 연결되었는지 여부를 나타냅니다. 1은 VPN(가상 사설망), 0은 비VPN입니다.</p></td>
</tr>
<tr class="even">
<td><p>CallerLinkSpeed</p></td>
<td><p>10 진수 (18,)</p></td>
<td><p>발신자의 끝점에 대한 네트워크 연결 속도(bps)입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeNetworkConnectionType</p></td>
<td><p>tinyint</p></td>
<td><p>수신자의 네트워크 연결 형식입니다. 0은 유선, 1은 무선입니다.</p></td>
</tr>
<tr class="even">
<td><p>CalleeVPN</p></td>
<td><p>비트만</p></td>
<td><p>수신자가 VPN(가상 사설망)을 통해 연결되었는지 여부를 나타냅니다. 1은 VPN(가상 사설망), 0은 비VPN입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeLinkSpeed</p></td>
<td><p>10 진수 (18, 0)</p></td>
<td><p>수신자의 끝점에 대한 네트워크 연결 속도(bps)입니다.</p></td>
</tr>
<tr class="even">
<td><p>ConversationalMOS</p></td>
<td><p>10 진수 (3, 2)</p></td>
<td><p>오디오 세션의 협대역 대화 MOS입니다(두 오디오 스트림을 모두 기반으로 함).</p></td>
</tr>
<tr class="odd">
<td><p>AppliedBandwidthLimit</p></td>
<td><p>int</p></td>
<td><p>다양한 정책 설정(TURN, API, SDP, 정책 서버 등)이 제공된 지정된 송신측 스트림에 적용되는 실제 대역폭입니다. 이 대역폭은 대역폭 예상에 따라 유효 대역폭이 더 낮을 수 있으므로 유효 대역폭과 혼동해서는 안됩니다. 이 대역폭은 기본적으로 대역폭 예상치로 지정된 한도를 제외하고 송신 스트림이 사용할 수 있는 최대 대역폭입니다.</p></td>
</tr>
<tr class="even">
<td><p>JitterInterArrival</p></td>
<td><p>int</p></td>
<td><p>RTCP(Real Time Control Protocol) 통계로부터 가져온 평균 네트워크 지터입니다.</p></td>
</tr>
<tr class="odd">
<td><p>JitterInterArrivalMax</p></td>
<td><p>int</p></td>
<td><p>통화 중 최대 네트워크 지터입니다.</p></td>
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
<td><p>PacketLossRate</p></td>
<td><p>10 진수 (5, 4)</p></td>
<td><p>통화 중 평균 패킷 손실 비율입니다.</p></td>
</tr>
<tr class="odd">
<td><p>PacketLossRateMax</p></td>
<td><p>10 진수 (5, 4)</p></td>
<td><p>통화 중 관측된 최대 패킷 손실입니다.</p></td>
</tr>
<tr class="even">
<td><p>PacketUtilization</p></td>
<td><p>int</p></td>
<td><p>비디오 스트림에 대한 패킷 수입니다(실시간 전송 프로토콜, RTP).</p></td>
</tr>
<tr class="odd">
<td><p>BandwidthEst</p></td>
<td><p>int</p></td>
<td><p>오디오 스트림에 대한 대역폭 예상치입니다.</p></td>
</tr>
<tr class="even">
<td><p>PayloadDescription</p></td>
<td><p>int</p></td>
<td><p><a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013의 PayloadDescription 테이블</a>에서 참조 되는 통화에 사용 되는 오디오 코덱입니다.</p></td>
</tr>
<tr class="odd">
<td><p>VideoResolution</p></td>
<td><p>char (9)</p></td>
<td><p>픽셀 너비와 픽셀 높이를 곱한 수치의 비디오 해상도입니다. 문자열로 보고됩니다.</p></td>
</tr>
<tr class="even">
<td><p>VideoBitRateAvg</p></td>
<td><p>int</p></td>
<td><p>비디오 스트림의 평균 비트 전송률입니다.</p></td>
</tr>
<tr class="odd">
<td><p>InboundVideoFrameRateAvg</p></td>
<td><p>10 진수 (9, 4)</p></td>
<td><p>수신된 비디오의 프레임 속도입니다.</p></td>
</tr>
<tr class="even">
<td><p>OutboundVideoFrameRateAvg</p></td>
<td><p>10 진수 (9, 4)</p></td>
<td><p>전송된 비디오의 프레임 속도입니다.</p></td>
</tr>
<tr class="odd">
<td><p>ViideoBitRateMax</p></td>
<td><p>int</p></td>
<td><p>비디오 세션 중의 최대 비디오 비트 전송률입니다.</p></td>
</tr>
<tr class="even">
<td><p>VideoPacketLossRate</p></td>
<td><p>10 진수 (9, 4)</p></td>
<td><p>비디오 패킷이 손실된 비율입니다.</p></td>
</tr>
<tr class="odd">
<td><p>VideoFrameLossRate</p></td>
<td><p>소수 (9.4)</p></td>
<td><p>총 비디오 프레임 중 손실된 백분율입니다.</p></td>
</tr>
<tr class="even">
<td><p>VideoFEC</p></td>
<td><p>비트만</p></td>
<td><p>사용되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>VideoAllocateBWAvg</p></td>
<td><p>int</p></td>
<td><p>비디오에 할당된 평균 대역폭 양입니다.</p></td>
</tr>
<tr class="even">
<td><p>VideoLocalFrameLossPercentageAvg</p></td>
<td><p>소수 (9.4)</p></td>
<td><p>총 비디오 프레임 중 손실된 백분율입니다.</p></td>
</tr>
<tr class="odd">
<td><p>SenderIsCallerPAI</p></td>
<td><p>비트만</p></td>
<td><p>p-어설션된 ID 정보에 대한 스트림 방향입니다. 1은 발신자에서 수신자로 방향이며, 0은 수신자에서 발신자로 방향입니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

