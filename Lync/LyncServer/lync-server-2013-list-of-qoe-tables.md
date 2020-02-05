---
title: 'Lync Server 2013: QoE 테이블 목록'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of QoE tables
ms:assetid: 176194d7-d184-4e23-94bb-cb62b4db47f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398236(v=OCS.15)
ms:contentKeyID: 48183512
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c3161415b65c8e85ace7968ab29d86c0d0c5387a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765396"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-qoe-tables-in-lync-server-2013"></a>Lync Server 2013의 QoE 테이블 목록

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-02_

데이터베이스 스키마는 다음 테이블로 구성 됩니다.

**지원 테이블**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>테이블로</strong></th>
<th><strong>설명</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-appsharingmetricsthreshold-table.md">Lync Server 2013의 AppSharingMetricsThreshold 테이블</a></p></td>
<td><p>응용 프로그램 공유에 사용 되는 경험 메트릭의 품질 기준에 대해 최적 및 허용 가능한 값을 저장 합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-codecdescription-table.md">Lync Server 2013의 CodecDescription 테이블</a></p></td>
<td><p>고유 코덱 식별자를 해당 하는 코덱에 매핑합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-ipaddress-table.md">Lync Server 2013의 IPAddress 테이블</a></p></td>
<td><p>환경 데이터베이스의 다른 위치에서 사용 되는 고유한 IP 주소 식별자에 IP 주소를 매핑합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013의 NetworkConnectionDetail 테이블</a></p></td>
<td><p>네트워크 연결 형식을 경력 데이터베이스의 다른 곳에 사용 되는 네트워크 연결 식별자에 매핑합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-purgesettings-table-qoe.md">Lync Server 2013의 PurgeSettings 테이블 (체감 품질)</a></p></td>
<td><p>오래 된 경력 품질 레코드가 체감 품질 데이터베이스에서 자동으로 삭제 되는지 여부를 지정 하는 정보를 저장 합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-traceroute-table.md">Lync Server 2013의 TraceRoute 테이블</a></p></td>
<td><p>통화에 대 한 라우팅 정보를 저장 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013의 UserAgentDef 테이블 (체감 품질)</a></p></td>
<td><p>사용자 에이전트 식별자를 에이전트의 설명 이름에 매핑합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-videometricsthreshold-table.md">Lync Server 2013의 VideoMetricsThreshold 테이블</a></p></td>
<td><p>영상 통화에 사용 되는 경험 메트릭의 품질 기준에 대 한 최적 및 허용 가능한 값을 저장 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-useragent-table.md">Lync Server 2013의 UserAgent 테이블</a></p></td>
<td><p>오디오 및 비디오 세션에 사용 되는 SIP (세션 초기화 프로토콜) 및 ua (Session User Agent) 문자열 및 UA 형식을 저장 합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-user-table.md">Lync Server 2013의 User 테이블</a></p></td>
<td><p>오디오 및 비디오 세션에 사용 되는 사용자, 회의 및 전화 Uri를 저장 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-endpoint-table.md">Lync Server 2013의 Endpoint 테이블</a></p></td>
<td><p>오디오 및 비디오 세션에 참가 하는 끝점의 FQDN 컴퓨터 이름을 저장 합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-pool-table.md">Lync Server 2013의 Pool 테이블</a></p></td>
<td><p>메트릭 데이터가 속한 풀의 이름을 저장 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-device-table.md">Lync Server 2013의 Device 테이블</a></p></td>
<td><p>오디오/비디오 통화에 사용 되는 캡처 장치 및 렌더링 장치를 저장 합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-devicedriver-table.md">Lync Server 2013의 DeviceDriver 테이블</a></p></td>
<td><p>캡처 디바이스의 드라이버와 오디오/비디오 통화에 사용 되는 렌더링 장치를 저장 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-conference-table.md">Lync Server 2013의 Conference 테이블</a></p></td>
<td><p>다른 시나리오의 경우 컨퍼런스 시나리오 또는 DialogID 용 전화 회의 Uri를 저장 합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-sessioncorrelation-table.md">Lync Server 2013의 SessionCorrelation 테이블</a></p></td>
<td><p>PSTN 통화에 대 한 CorrelationID을 저장 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013의 PayloadDescription 테이블</a></p></td>
<td><p>오디오/비디오 통화에 사용 되는 코덱을 저장 합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-appliedbandwidthsource-table.md">Lync Server 2013의 AppliedBandwidthSource 테이블</a></p></td>
<td><p>오디오/비디오 통화에 사용 되는 대역폭 원본을 저장 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-macaddress-table.md">Lync Server 2013의 MacAddress 테이블</a></p></td>
<td><p>오디오 및 비디오 세션에 참가 하는 끝점의 MAC 주소를 저장 합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-dialog-table.md">Lync Server 2013의 Dialog 테이블</a></p></td>
<td><p>오디오 및 비디오 세션의 대화 상자 ID를 저장 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-region-table.md">Lync Server 2013의 Region 테이블</a></p></td>
<td><p>NC 설정에 정의 된 네트워크 지역을 저장 합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-usersite-table.md">Lync Server 2013의 UserSite 테이블</a></p></td>
<td><p>NC 설정에 정의 된 네트워크 사이트를 저장 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-subnet-table.md">Lync Server 2013의 Subnet 테이블</a></p></td>
<td><p>NC 설정에 정의 된 서브넷을 저장 합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-monitoredregionlink-table.md">Lync Server 2013의 MonitoredRegionLink 테이블</a></p></td>
<td><p>NC 설정에 정의 된 지역 링크를 저장 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="monitoredusersitelink-table.md">MonitoredUserSiteLink 테이블</a></p></td>
<td><p>NC 설정에 정의 된 네트워크 사이트 링크를 저장 합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-endpointsubnet-table.md">Lync Server 2013의 EndpointSubnet 테이블</a></p></td>
<td><p>오디오 및 비디오 세션에 참여 하는 끝점의 서브넷을 저장 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-server-table.md">Lync Server 2013의 Server 테이블</a></p></td>
<td><p>미디어가 거치는 서버의 FQDN 또는 IP 주소를 저장 합니다.</p></td>
</tr>
</tbody>
</table>


**메트릭 데이터 테이블**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>테이블로</strong></th>
<th><strong>설명</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-appsharingstream-table.md">Lync Server 2013의 AppSharingStream 테이블</a></p></td>
<td><p>응용 프로그램 공유에 사용 되는 네트워크 스트림에 대 한 경험 메트릭의 품질 기준을 저장 합니다. 응용 프로그램 공유에 사용 되는 네트워크 스트림에 대 한 경험 메트릭의 품질 메트릭입니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-session-table.md">Lync Server 2013의 Session 테이블</a></p></td>
<td><p>오디오 또는 오디오/비디오 세션에 대 한 전체 정보를 저장 합니다. 세션은 두 끝점 간의 오디오 또는 비디오 SIP 대화 상자로 정의 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 MediaLine 테이블</a></p></td>
<td><p>세션의 각 미디어 라인에 대 한 정보를 저장 합니다. 미디어 선은 하나 이상의 오디오 및 비디오 스트림 모음입니다. 일반적으로 단일 미디어 회선에는 두 개의 스트림 (오디오 또는 비디오)이 있습니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-audiostream-table.md">Lync Server 2013의 AudioStream 테이블</a></p></td>
<td><p>미디어 라인에 각 오디오 스트림에 대 한 오디오 미디어 품질 메트릭을 저장 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-audiosignal-table.md">Lync Server 2013의 AudioSignal 테이블</a></p></td>
<td><p>미디어 라인에 오디오 미디어 품질 메트릭을 저장 합니다. 여기에는 AEC (음향 반향 제거) 및 AGC (자동 게인 제어) 메트릭이 포함 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-videostream-table.md">Lync Server 2013의 VideoStream 테이블</a></p></td>
<td><p>미디어 라인의 각 오디오 스트림에 대 한 비디오 미디어 품질 기준을 저장 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-audioclientevent-table.md">Lync Server 2013의 AudioClientEvent 테이블</a></p></td>
<td><p>클라이언트 이벤트에서 수집 된 오디오 미디어 품질 메트릭을 저장 합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-videoclientevent-table.md">Lync Server 2013의 VideoClientEvent 테이블</a></p></td>
<td><p>클라이언트 이벤트에서 수집 된 비디오 미디어 품질 메트릭을 저장 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DiagnosticData 테이블</strong></p></td>
<td><p>내부용 으로만 사용 되는 진단 데이터를 저장 합니다.</p></td>
</tr>
</tbody>
</table>


**요약 데이터 표**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>테이블로</strong></th>
<th><strong>설명</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ServerSummary 테이블</strong></p></td>
<td><p>서버에 대 한 요약 데이터를 저장 하 고, 이러한 데이터는 경력 (체감 품질) 보고용 으로만 사용 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserSummary 테이블</strong></p></td>
<td><p>사용자에 대 한 요약 데이터를 저장 하 고, 이러한 데이터는 체감 품질 보고에만 사용 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Call유형 Ummary 테이블</strong></p></td>
<td><p>통화 형식에 대 한 요약 데이터를 저장 하는 경우 이러한 데이터는 체감 품질 보고에만 사용 됩니다.</p></td>
</tr>
</tbody>
</table>


**모니터링 서버에서 내부용으로 사용 되는 테이블**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>테이블로</strong></th>
<th><strong>설명</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>DbConfigDateTime</strong></p></td>
<td><p>내부용 으로만 사용 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>DbConfigInt</strong></p></td>
<td><p>내부용 으로만 사용 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>프런트 엔드 테이블</strong></p></td>
<td><p>내부용 으로만 사용 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>작업 테이블</strong></p></td>
<td><p>내부용 으로만 사용 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SummaryTableConfiguration</strong></p></td>
<td><p>내부용 으로만 사용 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>DbErrorMessage</strong></p></td>
<td><p>내부용 으로만 사용 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MetricsThreshold</strong></p></td>
<td><p>내부용 으로만 사용 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>DaylightSavingYears</strong></p></td>
<td><p>내부용 으로만 사용 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>TimeZoneConfiguration</strong></p></td>
<td><p>내부용 으로만 사용 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>시간대</strong></p></td>
<td><p>내부용 으로만 사용 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallSummary 테이블</strong></p></td>
<td><p>내부용 으로만 사용 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceCallSumary 테이블</strong></p></td>
<td><p>내부용 으로만 사용 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>테 넌 트 테이블</strong></p></td>
<td><p>내부용 으로만 사용 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoCallSummaryTable</strong></p></td>
<td><p>내부용 으로만 사용 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ascall요약 테이블</strong></p></td>
<td><p>내부용 으로만 사용 됩니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

