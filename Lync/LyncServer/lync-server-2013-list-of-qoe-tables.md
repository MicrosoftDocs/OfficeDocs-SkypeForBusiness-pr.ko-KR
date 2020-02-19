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
ms.openlocfilehash: d47dc5b2623467feec340a6c918e6b43917593ee
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134954"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="list-of-qoe-tables-in-lync-server-2013"></a>Lync Server 2013의 QoE 테이블 목록

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-02_

데이터베이스 스키마는 다음 테이블로 구성됩니다.

**지원 테이블**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>목차가</strong></th>
<th><strong>설명</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-appsharingmetricsthreshold-table.md">Lync Server 2013의 AppSharingMetricsThreshold 테이블</a></p></td>
<td><p>응용 프로그램 공유에 사용되는 체감 품질 메트릭에 대한 최적의 값과 적절한 값을 저장합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-codecdescription-table.md">Lync Server 2013의 CodecDescription 테이블</a></p></td>
<td><p>고유 코덱 식별자를 해당 코덱에 매핑합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-ipaddress-table.md">Lync Server 2013의 IPAddress 테이블</a></p></td>
<td><p>IP 주소를 체감 품질 데이터베이스의 다른 위치에서 사용되는 고유 IP 주소 식별자에 매핑합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013의 NetworkConnectionDetail 테이블</a></p></td>
<td><p>네트워크 연결 유형을 체감 품질 데이터베이스의 다른 위치에서 사용되는 네트워크 연결 식별자에 매핑합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-purgesettings-table-qoe.md">Lync Server 2013의 PurgeSettings 테이블 (QoE)</a></p></td>
<td><p>오래된 체감 품질 레코드가 QoE 데이터베이스에서 자동으로 삭제되는지 여부 및 삭제되는 시간을 지정하는 정보를 저장합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-traceroute-table.md">Lync Server 2013의 TraceRoute 테이블</a></p></td>
<td><p>통화 라우팅 정보를 저장합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013의 UserAgentDef 테이블 (QoE)</a></p></td>
<td><p>사용자 에이전트 식별자를 에이전트의 설명이 포함된 이름에 매핑합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-videometricsthreshold-table.md">Lync Server 2013의 VideoMetricsThreshold 테이블</a></p></td>
<td><p>비디오 통화에 사용되는 체감 품질 메트릭에 대한 최적의 값과 적절한 값을 저장합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-useragent-table.md">Lync Server 2013의 UserAgent 테이블</a></p></td>
<td><p>오디오 및 비디오 세션에서 사용되는 SIP(Session Initiation Protocol) UA(사용자 에이전트) 문자열 및 UA 유형을 저장합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-user-table.md">Lync Server 2013의 User 테이블</a></p></td>
<td><p>오디오 및 비디오 세션에서 사용되는 사용자, 회의 및 전화 URI를 저장합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-endpoint-table.md">Lync Server 2013의 끝점 테이블</a></p></td>
<td><p>오디오 및 비디오 세션에 참가하는 끝점의 FQDN 컴퓨터 이름을 저장합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-pool-table.md">Lync Server 2013의 Pool 테이블</a></p></td>
<td><p>메트릭 데이터가 속하는 풀 이름을 저장합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-device-table.md">Lync Server 2013의 장치 테이블</a></p></td>
<td><p>오디오/비디오 통화에서 사용되는 캡처 장치 및 렌더링 장치를 저장합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-devicedriver-table.md">Lync Server 2013의 DeviceDriver 테이블</a></p></td>
<td><p>오디오/비디오 통화에서 사용되는 캡처 장치 및 렌더링 장치에 대한 드라이버를 저장합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-conference-table.md">Lync Server 2013의 회의 테이블</a></p></td>
<td><p>회의 시나리오에 대한 회의 URI 또는 기타 시나리오에 대한 DialogID를 저장합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-sessioncorrelation-table.md">Lync Server 2013의 SessionCorrelation 관계 테이블</a></p></td>
<td><p>PSTN 통화에 대한 CorrelationID를 저장합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013의 PayloadDescription 테이블</a></p></td>
<td><p>오디오/비디오 통화에서 사용되는 코덱을 저장합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-appliedbandwidthsource-table.md">Lync Server 2013의 AppliedBandwidthSource 테이블</a></p></td>
<td><p>오디오/비디오 통화에서 사용되는 대역폭 소스를 저장합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-macaddress-table.md">Lync Server 2013의 (가) 테이블</a></p></td>
<td><p>오디오 및 비디오 세션에 참가하는 끝점의 MAC 주소를 저장합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-dialog-table.md">Lync Server 2013의 Dialog 테이블</a></p></td>
<td><p>오디오 및 비디오 세션의 대화 ID를 저장합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-region-table.md">Lync Server 2013의 Region 테이블</a></p></td>
<td><p>NCS 설정에 정의된 네트워크 영역을 저장합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-usersite-table.md">Lync Server 2013의 UserSite 테이블</a></p></td>
<td><p>NCS 설정에 정의된 네트워크 사이트를 저장합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-subnet-table.md">Lync Server 2013의 서브넷 테이블</a></p></td>
<td><p>NCS 설정에 정의된 서브넷을 저장합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-monitoredregionlink-table.md">Lync Server 2013의 Monitored지역 링크 테이블</a></p></td>
<td><p>NCS 설정에 정의된 영역 링크를 저장합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="monitoredusersitelink-table.md">MonitoredUserSiteLink 테이블</a></p></td>
<td><p>NCS 설정에 정의된 네트워크 사이트를 저장합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-endpointsubnet-table.md">Lync Server 2013의 EndpointSubnet 테이블</a></p></td>
<td><p>오디오 및 비디오 세션에 참가하는 끝점의 서브넷을 저장합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-server-table.md">Lync Server 2013의 Server 테이블</a></p></td>
<td><p>미디어가 통과하는 서버의 FQDN 또는 IP 주소를 저장합니다.</p></td>
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
<th><strong>목차가</strong></th>
<th><strong>설명</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-appsharingstream-table.md">Lync Server 2013의 AppSharingStream 테이블</a></p></td>
<td><p>응용 프로그램 공유에 사용되는 네트워크 스트림에 대한 체감 품질 메트릭을 저장합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-session-table.md">Lync Server 2013의 Session 테이블</a></p></td>
<td><p>오디오 또는 오디오/비디오 세션에 대한 전체 정보를 저장합니다. 세션은 두 끝점 사이의 오디오 또는 비디오 SIP 대화로 정의됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a></p></td>
<td><p>세션에서 각 미디어 회선에 대한 정보를 저장합니다. 미디어 회선은 하나 이상의 오디오 및 비디오 스트림의 모음입니다. 일반적으로 단일 미디어 회선에는 오디오 또는 비디오의 두 스트림이 포함됩니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-audiostream-table.md">Lync Server 2013의 오디오 스트림 테이블</a></p></td>
<td><p>미디어 회선에서 각 오디오 스트림에 대한 오디오 미디어 품질 메트릭을 저장합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-audiosignal-table.md">Lync Server 2013의 오디오 신호 테이블</a></p></td>
<td><p>미디어 회선에서 오디오 미디어 품질 메트릭을 저장합니다. 여기에는 AEC(음향 반향 취소) 및 AGC(자동 게인 컨트롤) 메트릭이 포함됩니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-videostream-table.md">Lync Server 2013의 VideoStream 테이블</a></p></td>
<td><p>미디어 회선에서 각 오디오 스트림에 대한 비디오 미디어 품질 메트릭을 저장합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-audioclientevent-table.md">Lync Server 2013의 오디오 Clientevent 테이블</a></p></td>
<td><p>클라이언트 이벤트에서 수집된 오디오 미디어 품질 메트릭을 저장합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-videoclientevent-table.md">Lync Server 2013의 VideoClientEvent 테이블</a></p></td>
<td><p>클라이언트 이벤트에서 수집된 비디오 미디어 품질 메트릭을 저장합니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DiagnosticData 테이블</strong></p></td>
<td><p>내부 전용인 진단 데이터를 저장합니다.</p></td>
</tr>
</tbody>
</table>


**요약 데이터 테이블**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>목차가</strong></th>
<th><strong>설명</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ServerSummary 테이블</strong></p></td>
<td><p>서버에 대한 요약 데이터를 저장합니다. 이러한 데이터는 QoE(체감 품질) 보고용으로만 사용됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserSummary 테이블</strong></p></td>
<td><p>사용자에 대한 요약 데이터를 저장합니다. 이러한 데이터는 QoE 보고용으로만 사용됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallTypeSummary 테이블</strong></p></td>
<td><p>호출 유형에 대한 요약 데이터를 저장합니다. 이러한 데이터는 QoE 보고용으로만 사용됩니다.</p></td>
</tr>
</tbody>
</table>


**모니터링 서버에서 사용하는 내부용 테이블**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>목차가</strong></th>
<th><strong>설명</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>DbConfigDateTime</strong></p></td>
<td><p>내부 용도로만 사용됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>DbConfigInt</strong></p></td>
<td><p>내부 용도로만 사용됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FrontEnd 테이블</strong></p></td>
<td><p>내부 용도로만 사용됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>Task 테이블</strong></p></td>
<td><p>내부 용도로만 사용됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SummaryTableConfiguration</strong></p></td>
<td><p>내부 용도로만 사용됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>DbErrorMessage</strong></p></td>
<td><p>내부 용도로만 사용됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MetricsThreshold</strong></p></td>
<td><p>내부 용도로만 사용됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>DaylightSavingYears</strong></p></td>
<td><p>내부 용도로만 사용됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>TimeZoneConfiguration</strong></p></td>
<td><p>내부 용도로만 사용됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>TimeZones</strong></p></td>
<td><p>내부 용도로만 사용됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallSummary 테이블</strong></p></td>
<td><p>내부 용도로만 사용됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceCallSumary 테이블</strong></p></td>
<td><p>내부 용도로만 사용됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tenant 테이블</strong></p></td>
<td><p>내부 용도로만 사용됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoCallSummaryTable</strong></p></td>
<td><p>내부 용도로만 사용됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ascall요약 테이블</strong></p></td>
<td><p>내부 용도로만 사용됩니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

