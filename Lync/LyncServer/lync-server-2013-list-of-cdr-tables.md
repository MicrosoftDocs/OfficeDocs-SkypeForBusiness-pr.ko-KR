---
title: 'Lync Server 2013: CDR 테이블 목록'
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
ms.openlocfilehash: b0c620eaf6b54a89604071a18f445d20816178bf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765436"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-cdr-tables-in-lync-server-2013"></a>Lync Server 2013의 CDR 테이블 목록

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-18_

CDR (통화 정보 기록) 데이터베이스 스키마는 다음 테이블로 구성 됩니다.

<div>

## <a name="static-tables"></a>정적 테이블


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>테이블로</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-callpriorities-table.md">Lync Server 2013의 CallPriorities 테이블</a></p></td>
<td><p>긴급, 긴급, 일반, 비 긴급 등의 가능 통화 우선 순위 목록을 저장 합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencejointimethresholds-table.md">Lync Server 2013의 ConferenceJoinTimeThresholds 테이블</a></p></td>
<td><p>컨퍼런스 참가 시간 요약 보고서에 사용 되는 분류 경계를 저장 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-deregistertype-table.md">Lync Server 2013의 DeRegisterType 테이블</a></p></td>
<td><p>&quot;&quot; &quot;클라이언트 시작, 등록 만료,&quot; &quot;클라이언트 손상&quot; 등의 사용 가능 사용자 등록 취소의 목록을 저장 합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-medialist-table.md">Lync Server 2013의 MediaList 테이블</a></p></td>
<td><p>데이터베이스에 항목을 생성할 수 있는 미디어 유형 목록 (예: IM, 오디오, 비디오, 파일 전송)을 저장 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-purgesettings-table.md">Lync Server 2013의 PurgeSettings 테이블</a></p></td>
<td><p>오래 된 통화 정보 레코드가 CDR 데이터베이스에서 자동으로 삭제 되는지 여부를 지정 하는 정보를 저장 합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-roles-table.md">Lync Server 2013의 Roles 테이블</a></p></td>
<td><p>가능한 컨퍼런스 역할 목록 (예: 참석자 및 발표자)을 저장 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-sipresponsemetadata-table.md">Lync Server 2013의 SIPResponseMetaData 테이블</a></p></td>
<td><p>SIP 응답 코드와 이러한 코드의 분류 및 정의 목록을 저장 합니다.</p></td>
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
<th>테이블로</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-clientversions-table.md">Lync Server 2013의 ClientVersions 테이블</a></p></td>
<td><p>이 데이터베이스에서 캡처한 정보를 사용 하 여 호출에 참여 하는 각 클라이언트의 클라이언트 (클라이언트 유형 및 버전 번호)를 저장 합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013의 ConferenceUris 테이블</a></p></td>
<td><p>전화 회의 관련 통화에 사용 되는 ConferenceURIs 목록을 저장 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-contenttypes-table.md">Lync Server 2013의 ContentTypes 테이블</a></p></td>
<td><p>피어 투 피어 통화와 전화 회의에 사용 되는 SIP (세션 초기화 프로토콜) 콘텐츠 형식 목록을 저장 합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-devices-table.md">Lync Server 2013의 Devices 테이블</a></p></td>
<td><p>제조업체, 하드웨어 버전, MAC 주소 등 장치 목록을 저장 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 테이블</a></p></td>
<td><p>데이터베이스의 각 세션에 대 한 대화 상자 ID에 대 한 정보를 저장 합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-edgeservers-table.md">Lync Server 2013의 EdgeServers 테이블</a></p></td>
<td><p>외부 통화에 사용 되는 Edge 서버의 목록을 저장 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-gateways-table.md">Lync Server 2013의 Gateways 테이블</a></p></td>
<td><p>VoIP (Voice over 인터넷 프로토콜) 통화에 사용 되는 게이트웨이 목록을 저장 합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-hardwareversions-table.md">Lync Server 2013의 HardwareVersions 테이블</a></p></td>
<td><p>장치 (일반 전화기)의 하드웨어 버전 목록을 저장 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-manufacturers-table.md">Lync Server 2013의 Manufacturers 테이블</a></p></td>
<td><p>장치 제조업체 (일반 전화기) 목록을 저장 합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-mcus-table.md">Lync Server 2013의 Mcus 테이블</a></p></td>
<td><p>다양 한 A/V 회의 서버와 해당 Uri에 대 한 정보를 저장 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-mediationservers-table.md">Lync Server 2013의 MediationServers 테이블</a></p></td>
<td><p>VoIP 통화에 사용 되는 중재 서버 목록을 저장 합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-phones-table.md">Lync Server 2013의 Phones 테이블</a></p></td>
<td><p>보관 되었거나 통화 정보가 기록 된 VoIP 통화에 사용 된 모든 전화 번호를 저장 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-pools-table.md">Lync Server 2013의 Pools 테이블</a></p></td>
<td><p>메신저 대화 메시지가 캡처되는 풀의 이름을 저장 합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-servers-table.md">Lync Server 2013의 Servers 테이블</a></p></td>
<td><p>통화에 관련 된 서버의 이름을 저장 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tenants-table.md">Lync Server 2013의 Tenants 테이블</a></p></td>
<td><p>현재 배포에서 지원 되는 테 넌 트를 저장 합니다. 엔터프라이즈 사용자, 페더레이션 사용자, 공용 IM 연결 사용자, 익명 사용자를 위한 일부 빌드 비 테 넌 트가 있습니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-useragentdef-table.md">Lync Server 2013의 UserAgentDef 테이블</a></p></td>
<td><p>사용자 에이전트 식별자를 에이전트의 설명 이름에 매핑합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-users-table.md">Lync Server 2013의 Users 테이블</a></p></td>
<td><p>이 데이터베이스에 기록 되거나 보관 된 세션에 참가 한 사용자의 사용자 Uri를 저장 합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-userstatistics-table.md">Lync Server 2013의 UserStatistics 테이블</a></p></td>
<td><p>시스템의 개별 사용자 사용에 대 한 정보를 저장 합니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-specific-to-conference-cdr-records"></a>컨퍼런스 CDR 레코드에 해당 하는 테이블


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>테이블로</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-conferences-table.md">Lync Server 2013의 Conferences 테이블</a></p></td>
<td><p>보관 되었거나 ConferenceURI, 시작 및 종료 시간을 비롯 한 세부 정보가 기록 된 모든 컨퍼런스에 대 한 정보를 저장 합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencesessiondetails-table.md">Lync Server 2013의 ConferenceSessionDetails 테이블</a></p></td>
<td><p>시작 및 종료 시간, 사용자 ID, 응답 코드, 각 세션에 대 한 진단 ID 등 모든 SIP 기반 회의 세션에 대 한 정보를 저장 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-focusjoinsandleaves-table.md">Lync Server 2013의 FocusJoinsAndLeaves 테이블</a></p></td>
<td><p>사용자 역할 및 클라이언트 버전을 포함 하 여 컨퍼런스 참가 및 탈퇴에 대 한 정보를 저장 합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-mcujoinsandleaves-table.md">Lync Server 2013의 McuJoinsAndLeaves 테이블</a></p></td>
<td><p>회의와 관련 된 A/V 회의 서버와 사용자 참가 및 종료 시간에 대 한 정보를 저장 합니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-messages-in-im-conferences"></a>메신저 대화 회의의 메시지 표


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>테이블로</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-conferencemessagecount-table.md">Lync Server 2013의 ConferenceMessageCount 테이블</a></p></td>
<td><p>각 메신저 대화 회의에 대해 각 사용자가 보낸 메시지 수를 저장 합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-imreportsummary-table.md">Lync Server 2013의 IMReportSummary 테이블</a></p></td>
<td><p>조직에 보관 된 인스턴트 메시징 세션에 대 한 전체 보고서를 제공 합니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-peer-to-peer-sessions"></a>피어 투 피어 세션 표


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>테이블로</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-sessiondetails-table.md">Lync Server 2013의 SessionDetails 테이블</a></p></td>
<td><p>시작 및 종료 시간, 사용자 ID, 응답 코드, 각 사용자의 메시지 수 등 모든 피어 투 피어 세션에 대 한 정보를 저장 합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-filetransfers-table.md">Lync Server 2013의 FileTransfers 테이블</a></p></td>
<td><p>파일 이름 및 결과 (수락, 거부 또는 취소 됨)를 포함 하 여 파일 전송 세션에 대 한 정보를 저장 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-media-table.md">Lync Server 2013의 Media 테이블</a></p></td>
<td><p>피어 투 피어 세션에 관련 된 다양 한 미디어 형식에 대 한 정보를 저장 합니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-voip-call-details"></a>VoIP 통화 정보 표


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>테이블로</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-voipdetails-table.md">Lync Server 2013의 VoipDetails 테이블</a></p></td>
<td><p>두 개의 파티 VoIP/PSTN 통화에 대해 VoIP 전화기의 전화 ID, 게이트웨이 사용, 그리고 연결 끊긴 파티와 같은 통화에 대 한 정보를 저장 합니다. <a href="lync-server-2013-sessiondetails-table.md">Lync Server 2013에서</a> 통화 시작/종료 시간 및 응답 코드에 대 한 sessiondetails 테이블을 참조 합니다.</p>
<div>

> [!NOTE]  
> 한 통화에 대 한 한 자가 VoIP 사용자 이거나 중재 서버가 통화에 참여 하 고 있는 경우에는이 테이블에 레코드가 생성 됩니다. PSTN (공개 전환 전화 네트워크)과 관련 되지 않은 VoIP/VoIP 통화에 대 한 정보는 <A href="lync-server-2013-sessiondetails-table.md">Lync Server 2013의 Sessiondetails 테이블</A>에 캡처됩니다.


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-e9-1-1-call-auditing"></a>E9-1-1 통화 감사 표


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>테이블로</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-locations-table.md">Lync Server 2013의 Locations 테이블</a></p></td>
<td><p>향상 된 9-1-1 (E9-1) 통화와 같은 각 비상 통화에 대해 통화에 대 한 위치 정보를 저장 합니다. <a href="lync-server-2013-sessiondetails-table.md">Lync Server 2013에서</a> 통화 시작/종료 시간 및 응답 코드에 대 한 sessiondetails 테이블을 참조 합니다.</p>
<div>

> [!NOTE]  
> 이 표에는 E9-1-1 통화에 대 한 위치 blob만 포함 되어 있습니다. 통화에 대 한 기타 자세한 정보를 보려면 SessionDetails 테이블을 참조 하세요.


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-troubleshooting"></a>문제 해결 표


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>테이블로</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-application-table.md">Lync Server 2013의 Application 테이블</a></p></td>
<td><p>라우팅 및 연결과 관련 된 Lync Server 2013 내의 다양 한 프로세스에 대 한 정보를 저장 합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-calltype-table.md">Lync Server 2013의 CallType 테이블</a></p></td>
<td><p>"오디오", "인스턴트 메시징", "오디오 및 비디오" 및 "응용 프로그램 공유"와 같은 통화 유형에 대 한 정보를 저장 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-errorcategory-table.md">Lync Server 2013의 ErrorCategory 테이블</a></p></td>
<td><p>각 Microsoft Lync Server 2013 진단 분류에 대 한 친숙 한 이름을 저장 합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-errordef-table.md">Lync Server 2013의 ErrorDef 테이블</a></p></td>
<td><p>오류 유형과 해당 정의에 대 한 정보를 저장 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-errorreport-table.md">Lync Server 2013의 ErrorReport 테이블</a></p></td>
<td><p>발생 한 오류에 대 한 정보를 저장 합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-progressreport-table.md">Lync Server 2013의 ProgressReport 테이블</a></p></td>
<td><p>Lync Server 2013 프로세스에 포함 된 다양 한 단계의 진행 상황 보고서에 대 한 정보를 저장 합니다.</p></td>
</tr>
</tbody>
</table>


다음 목록의 표는 Lync Server에서 내부적으로 사용 됩니다. 세부 정보는이 문서에 설명 되어 있지 않습니다.

</div>

<div>

## <a name="tables-for-internal-use-by-lync-server"></a>Lync 서버에서 내부용으로 사용 하는 테이블


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>테이블로</th>
<th>설명</th>
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
<td><p><strong>DbErrorMessage</strong></p></td>
<td><p>내부용 으로만 사용 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>프런트 엔드 테이블</strong></p></td>
<td><p>내부용 으로만 사용 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MSMQProcessing 테이블</strong></p></td>
<td><p>내부용 으로만 사용 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>SummaryTableConfiguration</strong></p></td>
<td><p>내부용 으로만 사용 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Syndicators 테이블</strong></p></td>
<td><p>내부용 으로만 사용 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>SyndicatorsTenantMap 테이블</strong></p></td>
<td><p>내부용 으로만 사용 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>작업 테이블</strong></p></td>
<td><p>내부용 으로만 사용 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserStatistics</strong></p></td>
<td><p>내부용 으로만 사용 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UsageSummary_UQ</strong></p></td>
<td><p>내부용 으로만 사용 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>Usagesmary</strong></p></td>
<td><p>내부용 으로만 사용 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DaylightSavingYears</strong></p></td>
<td><p>내부용 으로만 사용 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>TimeZoneConfiguration</strong></p></td>
<td><p>내부용 으로만 사용 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>시간대</strong></p></td>
<td><p>내부용 으로만 사용 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>FailureSummary_UQ</strong></p></td>
<td><p>내부용 으로만 사용 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FailureSummary</strong></p></td>
<td><p>내부용 으로만 사용 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>ServerSummary</strong></p></td>
<td><p>내부용 으로만 사용 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagMetaData</strong></p></td>
<td><p>내부용 으로만 사용 됩니다.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

