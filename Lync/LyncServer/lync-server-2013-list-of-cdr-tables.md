---
title: 'Lync Server 2013: CDR 테이블 목록'
description: 'Lync Server 2013: CDR 테이블 목록입니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of CDR tables
ms:assetid: 031843fd-c7ff-4534-9b02-8847aad70807
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398084(v=OCS.15)
ms:contentKeyID: 48183254
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21d0f683ffeb0f5f1cbba5db4c45d248aa14e8e4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558704"
---
# <a name="list-of-cdr-tables-in-lync-server-2013"></a>Lync Server 2013의 CDR 테이블 목록

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-18_

CDR(통화 정보 기록) 데이터베이스 스키마는 다음과 같은 테이블로 구성됩니다.

<div>

## <a name="static-tables"></a>정적 테이블


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>목차가</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-callpriorities-table.md">Lync Server 2013의 CallPriorities 순위 테이블</a></p></td>
<td><p>응급, 긴급, 정상, 일반 등 가능한 통화 우선 순위 목록을 저장합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencejointimethresholds-table.md">Lync Server 2013의 ConferenceJoinTimeThresholds 테이블</a></p></td>
<td><p>회의 참가 시간 요약 보고서에서 사용하는 분류 경계를 저장합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-deregistertype-table.md">Lync Server 2013의 DeRegisterType 테이블</a></p></td>
<td><p>&quot;클라이언트 시작, &quot; &quot; 등록 만료, &quot; &quot; 클라이언트 손상 &quot; 등의 가능한 사용자 등록 취소 이유 목록을 저장 합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-medialist-table.md">Lync Server 2013의 MediaList 테이블</a></p></td>
<td><p>데이터베이스에 항목을 생성할 수 있는 미디어 유형 목록(예: IM, 오디오, 비디오 및 파일 전송)을 저장합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-purgesettings-table.md">Lync Server 2013의 PurgeSettings 테이블</a></p></td>
<td><p>오래된 통화 정보 기록이 CDR 데이터베이스에서 자동으로 삭제되는지 여부 및 삭제되는 시간을 지정하는 정보를 저장합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-roles-table.md">Lync Server 2013의 역할 테이블</a></p></td>
<td><p>가능한 회의 역할 목록(예: 참석자 및 발표자)을 저장합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-sipresponsemetadata-table.md">Lync Server 2013의 SIPResponseMetaData 테이블</a></p></td>
<td><p>SIP 응답 코드 목록과 이러한 각 코드의 분류 및 정의를 저장합니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supporting-tables"></a>지원 테이블


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>목차가</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-clientversions-table.md">Lync Server 2013의 ClientVersions 테이블</a></p></td>
<td><p>이 데이터베이스에서 캡처된 정보와 함께 통화에 포함된 각 클라이언트의 클라이언트 정보(클라이언트 유형 및 버전 번호 모두)를 저장합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013의 ConferenceUris 테이블</a></p></td>
<td><p>회의 관련 통화에 사용되는 ConferenceURIs 목록을 저장합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-contenttypes-table.md">Lync Server 2013의 ContentTypes 테이블</a></p></td>
<td><p>피어 투 피어 통화 및 회의 통화에 모두 사용되는 SIP(Session Initiation Protocol) 콘텐츠 유형의 목록을 저장합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-devices-table.md">Lync Server 2013의 Devices 테이블</a></p></td>
<td><p>제조업체, 하드웨어 버전 및 MAC 주소를 포함하는 장치 목록을 저장합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 테이블</a></p></td>
<td><p>데이터베이스에 있는 각 세션의 대화 ID에 대한 정보를 저장합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-edgeservers-table.md">Lync Server 2013의 EdgeServers 테이블</a></p></td>
<td><p>외부 통화에 사용되는 에지 서버 목록을 저장합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-gateways-table.md">Lync Server 2013의 게이트웨이 테이블</a></p></td>
<td><p>VoIP(Voice over Internet Protocol) 통화에 사용되는 게이트웨이 목록을 저장합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-hardwareversions-table.md">Lync Server 2013의 HardwareVersions 테이블</a></p></td>
<td><p>장치(일반 전화)의 하드웨어 버전 목록을 저장합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-manufacturers-table.md">Lync Server 2013의 제조업체 테이블</a></p></td>
<td><p>장치(일반 전화)의 제조업체 목록을 저장합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-mcus-table.md">Lync Server 2013의 Mcus 테이블</a></p></td>
<td><p>다양한 A/V 회의 서버 및 해당 URL에 대한 정보를 저장합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-mediationservers-table.md">Lync Server 2013의 MediationServers 테이블</a></p></td>
<td><p>VoIP 통화에 사용되는 중재 서버 목록을 저장합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-phones-table.md">Lync Server 2013의 전화 테이블</a></p></td>
<td><p>보관된 VoIP 통화에 사용되거나 해당 통화 세부 정보가 기록된 모든 전화 번호를 저장합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-pools-table.md">Lync Server 2013의 풀 테이블</a></p></td>
<td><p>IM 메시지가 캡처되는 풀의 이름을 저장합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-servers-table.md">Lync Server 2013의 Servers 테이블</a></p></td>
<td><p>통화에 연관된 서버 이름을 저장합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 테이블</a></p></td>
<td><p>현재 배포에서 지원되는 테넌트를 저장합니다. 엔터프라이즈 사용자, 페더레이션 사용자, 공용 IM 연결 사용자 및 익명 사용자를 위한 몇 가지 기본 제공 테넌트가 있습니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-useragentdef-table.md">Lync Server 2013의 UserAgentDef 테이블</a></p></td>
<td><p>사용자 에이전트 식별자를 에이전트의 설명이 포함된 이름에 매핑합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-users-table.md">Lync Server 2013의 Users 테이블</a></p></td>
<td><p>이 데이터베이스에 기록 및 보관된 세션에 참여한 사용자의 사용자 URI를 저장합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-userstatistics-table.md">Lync Server 2013의 UserStatistics 테이블</a></p></td>
<td><p>개별 사용자의 시스템 사용에 대한 정보를 저장합니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-specific-to-conference-cdr-records"></a>회의 CDR 레코드 관련 테이블


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>목차가</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-conferences-table.md">Lync Server 2013의 회의 테이블</a></p></td>
<td><p>ConferenceURI 및 시작/종료 시간을 포함하여 보관된 회의 또는 세부 정보가 기록된 회의에 대한 모든 정보를 저장합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencesessiondetails-table.md">Lync Server 2013의 ConferenceSessionDetails 테이블</a></p></td>
<td><p>시작 및 종료 시간, 사용자 ID, 응답 코드 및 각 세션에 대한 진단 ID를 포함하여 모든 SIP 기반 회의 세션에 대한 정보를 저장합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-focusjoinsandleaves-table.md">Lync Server 2013의 FocusJoinsAndLeaves 테이블</a></p></td>
<td><p>사용자의 역할 및 클라이언트 버전을 포함하여 회의 참가 및 종료에 대한 정보를 저장합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-mcujoinsandleaves-table.md">Lync Server 2013의 McuJoinsAndLeaves 테이블</a></p></td>
<td><p>회의에 관련된 A/V 회의 서버 및 사용자의 참가 및 종료 시간에 대한 정보를 저장합니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-messages-in-im-conferences"></a>IM 회의의 메시지 테이블


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>목차가</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-conferencemessagecount-table.md">Lync Server 2013의 ConferenceMessageCount 테이블</a></p></td>
<td><p>각 IM 회의에 대해 각 사용자가 전송한 메시지 수를 저장합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-imreportsummary-table.md">Lync Server 2013의 IMReportSummary 테이블</a></p></td>
<td><p>조직에서 보관하는 인스턴트 메시징 세션에 대한 전체 보고서를 제공합니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-peer-to-peer-sessions"></a>피어 투 피어 세션 테이블


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>목차가</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-sessiondetails-table.md">Lync Server 2013의 SessionDetails 테이블</a></p></td>
<td><p>시작 및 종료 시간, 사용자 ID, 응답 코드 및 각 사용자에 대한 메시지 수를 포함하여 모든 피어 투 피어 세션에 대한 정보를 저장합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-filetransfers-table.md">Lync Server 2013의 FileTransfers 테이블</a></p></td>
<td><p>파일 이름 및 결과(수락, 거절 또는 취소)를 포함하여 파일 전송 세션에 대한 정보를 저장합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-media-table.md">Lync Server 2013의 미디어 테이블</a></p></td>
<td><p>피어 투 피어 세션에 포함된 여러 미디어 유형에 대한 정보를 저장합니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-voip-call-details"></a>VoIP 통화 세부 정보 테이블


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>목차가</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-voipdetails-table.md">Lync Server 2013의 VoipDetails 테이블</a></p></td>
<td><p>각 두 사용자 간 VoIP/PSTN 통화에 대해 VoIP 전화의 전화 ID, 사용된 게이트웨이 및 연결을 해제한 사용자 등 통화에 대한 정보를 저장합니다. 통화 시작/종료 시간 및 응답 코드에 대 한 <a href="lync-server-2013-sessiondetails-table.md">Lync Server 2013의 Sessiondetails 테이블</a> 을 참조 합니다.</p>
<div>

> [!NOTE]  
> 통화에서 한 사용자가 VoIP 사용자이거나 통화에 중재 서버가 포함된 경우 이 테이블에 레코드가 만들어집니다. 공중 전화망 (PSTN) 전화와 관련 되지 않은 VoIP/VoIP 통화에 대 한 정보는 <A href="lync-server-2013-sessiondetails-table.md">Lync Server 2013의 Sessiondetails 테이블</A>에 캡처됩니다.


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-e9-1-1-call-auditing"></a>E9-1-1 통화 감사 테이블


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>목차가</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-locations-table.md">Lync Server 2013의 위치 테이블</a></p></td>
<td><p>E9-1-1(Enhanced 9-1-1) 통화와 같은 각 긴급 통화에 대해서는 통화에 대한 위치 정보를 저장합니다. 통화 시작/종료 시간 및 응답 코드에 대 한 <a href="lync-server-2013-sessiondetails-table.md">Lync Server 2013의 Sessiondetails 테이블</a> 을 참조 합니다.</p>
<div>

> [!NOTE]  
> 이 테이블에는 E9-1-1 통화에 대한 위치 BLOB만 포함됩니다. 통화에 대한 다른 세부 정보는 SessionDetails 테이블을 참조하십시오.


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-troubleshooting"></a>문제 해결 테이블


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>목차가</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-application-table.md">Lync Server 2013의 응용 프로그램 테이블</a></p></td>
<td><p>라우팅 및 연결과 관련 된 Lync Server 2013 내의 다양 한 프로세스에 대 한 정보를 저장 합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-calltype-table.md">Lync Server 2013의 CallType 테이블</a></p></td>
<td><p>"오디오", "인스턴트 메시징", "오디오 및 비디오" 및 "응용 프로그램 공유"와 같은 통화 유형에 대한 정보를 저장합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-errorcategory-table.md">Lync Server 2013의 ErrorCategory 테이블</a></p></td>
<td><p>각 Microsoft Lync Server 2013 진단 분류의 이름을 저장 합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-errordef-table.md">Lync Server 2013의 ErrorDef 테이블</a></p></td>
<td><p>오류 유형 및 정의에 대한 정보를 저장합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-errorreport-table.md">Lync Server 2013의 ErrorReport 테이블</a></p></td>
<td><p>발생한 오류에 대한 정보를 저장합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-progressreport-table.md">Lync Server 2013의 ProgressReport 테이블</a></p></td>
<td><p>Lync Server 2013 프로세스에 포함 된 다양 한 단계의 진행 상황 보고서에 대 한 정보를 저장 합니다.</p></td>
</tr>
</tbody>
</table>


다음 목록의 표에는 Lync Server에서 내부적으로 사용 하는 테이블이 나와 있습니다. 이러한 테이블의 세부 정보는 이 문서에서 설명하지 않습니다.

</div>

<div>

## <a name="tables-for-internal-use-by-lync-server"></a>Lync Server 내부용 테이블


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>목차가</th>
<th>설명</th>
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
<td><p><strong>DbErrorMessage</strong></p></td>
<td><p>내부 용도로만 사용됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>FrontEnd 테이블</strong></p></td>
<td><p>내부 용도로만 사용됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MSMQProcessing 테이블</strong></p></td>
<td><p>내부 용도로만 사용됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>SummaryTableConfiguration</strong></p></td>
<td><p>내부 용도로만 사용됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Syndicators 테이블</strong></p></td>
<td><p>내부 용도로만 사용됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>SyndicatorsTenantMap 테이블</strong></p></td>
<td><p>내부 용도로만 사용됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Task 테이블</strong></p></td>
<td><p>내부 용도로만 사용됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserStatistics</strong></p></td>
<td><p>내부 용도로만 사용됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UsageSummary_UQ</strong></p></td>
<td><p>내부 용도로만 사용됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>UsageSummary</strong></p></td>
<td><p>내부 용도로만 사용됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DaylightSavingYears</strong></p></td>
<td><p>내부 용도로만 사용됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>TimeZoneConfiguration</strong></p></td>
<td><p>내부 용도로만 사용됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>TimeZones</strong></p></td>
<td><p>내부 용도로만 사용됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>FailureSummary_UQ</strong></p></td>
<td><p>내부 용도로만 사용됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FailureSummary</strong></p></td>
<td><p>내부 용도로만 사용됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>ServerSummary</strong></p></td>
<td><p>내부 용도로만 사용됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagMetaData</strong></p></td>
<td><p>내부 용도로만 사용됩니다.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

