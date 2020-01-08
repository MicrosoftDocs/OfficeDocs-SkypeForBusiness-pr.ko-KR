---
title: 'Lync Server 2013: 스키마 특성 및 설명'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Schema attributes and descriptions
ms:assetid: b009df76-9c22-471d-b57a-bda009a98261
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412841(v=OCS.15)
ms:contentKeyID: 48185083
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc18b4b074302ba3c233670f21fd8479bbd0b0f8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984070"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="schema-attributes-and-descriptions-in-lync-server-2013"></a>Lync Server 2013의 스키마 특성 및 설명

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-06_

이 섹션에서는 Lync Server 2013에서 사용 되는 모든 스키마 특성에 대해 설명 합니다. 특성과 관련 된 클래스의 경우 [Lync Server 2013에서 클래스별 스키마 특성](lync-server-2013-schema-attributes-by-class.md)을 참조 하세요. Lync Server 2013의 새로운 클래스 및 특성 목록은 [Lync server 2013의 스키마 변경을](lync-server-2013-schema-changes-in-lync-server-2013.md)참조 하세요.

연결 된 쌍의 특성은 전방 링크 또는 뒤로 링크로 지정 됩니다. 다른 개체를 참조 하는 특성은 전방 링크입니다. 첫 번째 개체를 다시 참조 하는 다른 개체의 특성은 뒤로 링크입니다. 전방 링크는 업데이트할 수 있으며, 역방향 링크는 읽기 전용입니다.

일부 특성에는 비트 마스크 값이 있습니다. 이러한 특성의 경우 각 설정이 비트로 표시 되 고 표시 되는 10 진수 값이 비트 위치를 나타냅니다. 비트 위치는 비트 0으로 시작 합니다. 예를 들어 1 (이진수)는 비트 0으로 설정 되 고 1만 (이진수)는 비트 4로 설정 됩니다. 각 비트는 속성을 나타냅니다. 다음은 몇 가지 예입니다.

  - 1만 (이진수)의 10 진수 값이 16 (즉, 비트 4가 설정 됨)입니다.

  - 1억 (이진수)에 256의 10 진수 값 (즉, 비트 8이 설정 됨)이 있습니다.

  - 1100 (이진수)의 10 진수 값이 12입니다 (즉, bits 2와 3이 설정 되 고, 두 비트로 표현 된 속성을 사용할 수 있음).

  - 1111000001 (이진수)의 10 진수 값 961 (즉, 비트 0, 6, 7, 8, 9가 설정 되 고 각 비트에 대 한 속성을 사용할 수 있습니다.)

<div id="sectionSection0" class="section">

### <a name="schema-attributes-for-lync-server-2013"></a>Lync Server 2013의 스키마 특성

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>특성</th>
<th>설명</th>
<th>메모</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>dnsHostName</p></td>
<td><p>이제 <strong>msRTCSIP</strong> 및 <strong>msRTCSIP</strong> 클래스와 연결 된 Active Directory 도메인 서비스의 기존 특성입니다. 이 특성은 풀 또는 모니터링 서버의 정규화 된 도메인 이름 (FQDN)을 지정 합니다.</p>
<p>각 세그먼트에 대 한 유효한 값은 63 자입니다. 전체 FQDN에 대 한 유효한 값은 255 자입니다.</p></td>
<td><p>Microsoft Office Live Communications Server 2005의 새로운 방법입니다.</p></td>
</tr>
<tr class="even">
<td><p>msDS-SourceObjectDN</p></td>
<td><p>이 특성은이 개체에 해당 하는 다른 포리스트의 개체에 대 한 DN (고유 이름)의 문자열 표현을 포함 합니다. 이 특성은 메일 그룹 확장과 자동으로 참석 하는 데 사용 됩니다. 이 특성은 Windows Server 2003 R2의 기본 Active Directory 스키마에서 정의 됩니다.</p>
<p>AD DS를 Windows Server 2003 R2로 업그레이드 하지 않도록 하기 위해 Active Directory 스키마 준비에서이 특성 정의를 사용 하 여 Windows Server 2003 스키마를 확장 합니다.</p></td>
<td><p>Microsoft Office 통신 서버 2007의 새로운 방법.</p></td>
</tr>
<tr class="odd">
<td><p>msExchUCVoiceMailSettings</p></td>
<td><p>이 다중 값 특성에는 음성 메일 설정이 포함 됩니다. 이 특성은 Exchange UM (통합 메시징)와 공유 됩니다.</p></td>
<td><p>Microsoft Lync Server 2010의 새로운 방법.</p></td>
</tr>
<tr class="even">
<td><p>msExchUserHoldPolicies</p></td>
<td><p>이 다중 값 특성에는 사용자에 게 적용 되는 보류 정책에 대 한 식별자가 저장 됩니다. 보존 정책은 보류 기간 동안 사용자의 사서함 항목을 보존 합니다. 이 특성은 Exchange 2013와 공유 됩니다.</p></td>
<td><p>Lync Server 2013의 새로운 방법.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-AcpInfo</p></td>
<td><p>이 특성은 사용자에 대 한 오디오 회의 공급자 정보를 저장 합니다.</p></td>
<td><p>Lync Server 2010의 새로운 방법.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationDestination</p></td>
<td><p>이 특성은 응용 프로그램 대화 상대에 대 한 신뢰할 수 있는 서비스 항목을 가리킵니다.</p></td>
<td><p>Microsoft Office Communications Server 2007 R2의 새로운 방법입니다.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationList</p></td>
<td><p>이 특성에는 응용 프로그램 서버에서 호스팅되는 응용 프로그램의 목록이 포함 됩니다.</p></td>
<td><p>Office Communications Server 2007 R2의 새로운 방법</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationOptions</p></td>
<td><p>이 특성은 응용 프로그램 연락처에 대 한 옵션을 지정 합니다.</p></td>
<td><p>Office Communications Server 2007 R2의 새로운 방법</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationPrimaryLanguage</p></td>
<td><p>이 특성에는 응용 프로그램 연락처의 기본 언어가 포함 됩니다.</p></td>
<td><p>Office Communications Server 2007 R2의 새로운 방법</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationSecondaryLanguages</p></td>
<td><p>이 여러 값 특성에는 응용 프로그램 연락처의 보조 언어가 포함 됩니다.</p></td>
<td><p>Office Communications Server 2007 R2의 새로운 방법</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationServerBL</p></td>
<td><p>이 특성에는이 풀에 속한 응용 프로그램 서버 목록이 포함 되어 있습니다. @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ <strong>뒤로 링크</strong></p></td>
<td><p>Office Communications Server 2007 R2의 새로운 방법</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationServerPoolLink</p></td>
<td><p>이 특성은이 응용 프로그램 서버가 속한 풀을 가리킵니다. 전방 링크입니다. 해당 역방향 링크는 <strong>msRTCSIP-ApplicationServerBL</strong>입니다.</p></td>
<td><p>Office Communications Server 2007 R2의 새로운 방법</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchiveDefault (구식)</p></td>
<td><p>-</p></td>
<td><p>실시간 통신 서버 2005의 새로운 방법.</p>
<p>Office Communications Server 2007에서 더 이상 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ArchiveDefaultFlags (구식)</p></td>
<td><p>이 특성은 모든 사용자 통신을 보관할 포리스트 경계 내의 전역 기본값을 지정 합니다. 이는 보관 에이전트 계층에서 적용 됩니다. 이 특성에 대 한 값의 범위는 다음과 같습니다.</p>
<ul>
<li><p><strong>TRUE</strong>: 모든 사용자 보관</p></li>
<li><p><strong>FALSE</strong>: 모든 사용자 보관 안 함</p></li>
</ul>
<p>이 특성은 포리스트 경계 내에서 내부 네트워크 내의 사용자 통신을 보관 하는 방법을 전역적으로 제어 합니다.</p>
<p><strong>Live Communications Server 2005 동작 (현재 사용 중지)</strong></p>
<p>이 특성에 대 한 값의 범위는 다음과 같습니다.</p>
<ul>
<li><p>0: 메시지 본문 보관 [비트 0]</p></li>
<li><p>1: 메시지 본문을 보관 하지 않음 [비트 0]</p></li>
</ul>
<p><strong>Office Communications Server 2007 동작</strong></p>
<p>이 특성에 대 한 값의 범위는 다음과 같습니다.</p>
<ul>
<li><p>0: ArchiveFederationDefaultWithoutBody (사용 중지)</p></li>
<li><p>1-2: ArchiveInternalCommunications</p></li>
<li><p>3-4: ArchiveFederatedCommunications</p></li>
<li><p>5: RecordPresenceRegistrations</p></li>
<li><p>6: RecordIMCallDetails</p></li>
<li><p>7: RecordGroupIMCallDetails</p></li>
<li><p>8: RecordFileTransferInstances</p></li>
<li><p>9: Record오디오 Ocalldetails</p></li>
<li><p>10: RecordVideoCallDetails</p></li>
<li><p>11: RecordRemoteAssistanceCallDetails</p></li>
<li><p>12: RecordApplicationSharingDetails</p></li>
<li><p>13: RecordMeetingInstantiations</p></li>
<li><p>14: RecordMeetingJoins</p></li>
<li><p>15: RecordDataJoins</p></li>
<li><p>16: RecordAVJoins</p></li>
</ul></td>
<td><p>실시간 통신 서버 2005의 새로운 방법.</p>
<p>Lync Server 2010에서 더 이상 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchiveFederationDefault (구식)</p></td>
<td><p>-</p></td>
<td><p>실시간 통신 서버 2005의 새로운 방법.</p>
<p>Office Communications Server 2007에서 더 이상 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ArchiveFederationDefaultFlags (구식)</p></td>
<td><p>-</p></td>
<td><p>실시간 통신 서버 2005의 새로운 방법.</p>
<p>Office Communications Server 2007에서 더 이상 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchivingEnabled</p></td>
<td><p>이 특성은 단일 사용자의 통신을 보관할지 여부를 제어 하는 비트 필드로 사용 되는 정수입니다. 이 컨트롤은 보관 에이전트 계층에서 적용 됩니다. 이는 글로벌 카탈로그 복제로 표시 됩니다.</p>
<p>이 특성의 범위는 단일 사용자 또는 연락처와 관련이 있습니다. Lync Server의 유효한 값 (및 연결 된 비트 위치)은 다음과 같습니다.</p>
<ul>
<li><p>0: 보관 안 함 (비트 집합 없음)</p></li>
<li><p>1: 사용 중지 (비트 위치 0)</p></li>
<li><p>2: 사용 중지 (비트 위치 1)</p></li>
<li><p>4: 내부 통신 보관 (비트 위치 2)</p></li>
<li><p>8: 페더레이션 통신 보관 (비트 위치 3)</p></li>
</ul>
<p>Live Communications Server 2005의 이전 유효한 값은 다음과 같습니다.</p>
<ul>
<li><p>0: 우선 순위에 따라 <strong>msRTCSIP-ArchiveDefault</strong> 및 <strong>msRTCSIP-ArchiveFederation</strong> 에 의해 정의 된 기본값을 사용 합니다.</p>
<ul>
<li><p>1: 보관</p></li>
<li><p>2: 보관 안 함</p></li>
<li><p>3: 메시지 본문 없이 보관</p></li>
</ul></li>
</ul></td>
<td><p>실시간 통신 서버 2005의 새로운 방법.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ArchivingServerData (구식)</p></td>
<td><p>이 특성은 나중에 사용 하기 위해 예약 되어 있습니다.</p></td>
<td><p>Lync Server 2010에서 더 이상 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchivingServerVersion (구식)</p></td>
<td><p>이 특성은 보관 서비스의 버전을 정의 합니다. 이 특성은 공식적인 각 제품 릴리스로 증가 하는 monotonously 증가 하는 정수 형식입니다. 가능한 유효한 값은 다음과 같습니다.</p>
<ul>
<li><p>Undefined: Live Communications Server 2003</p>
<p>                 Live Communications Server 2005</p>
<p>                 실시간 통신 서버 2005 (SP1)</p></li>
<li><p>3: Office Communications Server 2007</p></li>
<li><p>4: Office Communications Server 2007 R2</p></li>
</ul></td>
<td><p>Office Communications Server 2007의 새로운 방법.</p>
<p>Lync Server 2010에서 더 이상 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-BackEndServer</p></td>
<td><p>이 특성은 풀 백 엔드 서버의 FQDN을 지정 합니다. 풀 당 하나의 백 엔드 서버만 사용할 수 있기 때문에 단일 값 특성입니다.</p>
<p>각 세그먼트의 유효한 값은 63 자입니다. 전체 FQDN에 대 한 유효한 값은 255 자입니다.</p></td>
<td><p>실시간 통신 서버 2005의 새로운 방법.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ConferenceDirectoryHomePool</p></td>
<td><p>이 특성에는 컨퍼런스 디렉터리를 호스팅하는 풀의 식별자가 포함 되어 있습니다.</p></td>
<td><p>Office Communications Server 2007 R2의 새로운 방법</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ConferenceDirectoryId</p></td>
<td><p>이 특성에는 컨퍼런스 디렉터리의 식별자가 포함 되어 있습니다.</p></td>
<td><p>Office Communications Server 2007 R2의 새로운 방법</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ConferenceDirectoryTargetPool</p></td>
<td><p>이 특성에는 회의 디렉터리가 이동 되는 풀의 식별자가 포함 됩니다.</p></td>
<td><p>Office Communications Server 2007 R2의 새로운 방법</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-기본값</p></td>
<td><p>이 부울 특성은 전화 사용이 기본 사용 인지 여부를 정의 합니다. 이 특성을 <strong>TRUE</strong>로 설정 하면 전화 사용이 기본 사용 이므로 관리자가 삭제할 수 없습니다. 이 특성을 <strong>FALSE</strong>로 설정 하면 사용을 삭제할 수 있습니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 방법.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefaultCWAExternalURL</p></td>
<td><p>이 특성은 조직 외부의 사용자에 대 한 Communicator Web Access URL을 식별 합니다.</p></td>
<td><p>Office Communications Server 2007 R2의 새로운 방법</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefaultCWAInternalURL</p></td>
<td><p>이 특성은 조직 내에 있는 사용자의 Communicator Web Access URL을 식별 합니다.</p></td>
<td><p>Office Communications Server 2007 R2의 새로운 방법</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefaultLocationProfileLink (구식)</p></td>
<td><p>이 단일 값 특성에는 할당 된 위치 프로필 클래스 개체의 DN (고유 이름)이 포함 됩니다.</p>
<p>전달 링크: <strong>링크 ID 11036</strong></p>
<p>해당 역방향 링크는 <strong>msRTCSIP-ServerReferenceBL</strong>입니다.</p></td>
<td><p>Lync Server 2010에서 더 이상 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefaultPolicy (구식)</p></td>
<td><p>이 부울 특성은 정책이 기본 정책 인지 여부를 지정 합니다. 정책이 <strong>TRUE</strong>로 설정 되 면 기본 정책입니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 방법</p>
<p>Lync Server 2010에서 더 이상 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefaultRouteToEdgeProxy (구식)</p></td>
<td><p>이 특성은 액세스에 지 서비스를 실행 하는 Edge 서버의 FQDN을 지정 하 고, 직접 액세스할 수 있는 경우에는 액세스에 지 서비스를 실행 하는 서버 풀의 하드웨어 부하 분산 장치입니다. 액세스에 지 서비스를 실행 하는 서버에 하나 이상의 디렉터만 액세스할 수 있는 경우,이 특성은 FQDN을 지정 하 고, 선택적으로 디렉터의 포트 번호 또는 디렉터 풀을 처리 하는 하드웨어 부하 분산 장치를 지정 합니다.</p>
<p>각 세그먼트의 유효한 값은 63 자입니다. 전체 FQDN에 대 한 유효한 값은 255 자입니다.</p></td>
<td><p>실시간 통신 서버 2005의 새로운 방법.</p>
<p>Lync Server 2010에서 더 이상 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefaultRouteToEdgeProxyPort (구식)</p></td>
<td><p>이 특성은 액세스에 지 서비스를 실행 하는 서버에 연결 하는 데 사용 해야 하는 포트 번호를 나타냅니다.</p>
<p>유효한 값은 사용할 포트를 지정 하는 정수 값입니다. 기본값은 5061입니다.</p></td>
<td><p>실시간 통신 서버 2005의 새로운 방법.</p>
<p>Lync Server 2010에서 더 이상 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefPresenceSubscriptionTimeout (구식)</p></td>
<td><p>이 특성은 기본 현재 상태 구독 시간 초과 기간을 나타냅니다.</p></td>
<td><p>Lync Server 2010에서 더 이상 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefRegistrationTimeout (구식)</p></td>
<td><p>이 특성은 기본 등록 시간 초과 창을 나타냅니다.</p></td>
<td><p>Lync Server 2010에서 더 이상 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefRoamingDataSubscriptionTimeout (구식)</p></td>
<td><p>이 특성은 기본 로밍 데이터 구독 시간 초과 창을 나타냅니다.</p></td>
<td><p>Lync Server 2010에서 더 이상 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DeploymentLocator</p></td>
<td><p>이 특성은 분할 된 도메인 토폴로지에 사용 되며 FQDN (정규화 된 도메인 이름)을 포함 합니다.</p></td>
<td><p>Lync Server 2010의 새로운 방법.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-설명 (구식)</p></td>
<td><p>이 단일 값 유니코드 문자열 특성에는이 전화 경로 또는 정규화 규칙에 대 한 간단한 설명이 포함 되어 있습니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 방법.</p>
<p>Lync Server 2010에서 더 이상 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-도메인 데이터</p></td>
<td><p>이 특성은 나중에 사용 하기 위해 예약 되어 있습니다.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DomainName</p></td>
<td><p>이 특성은 등록 기관에 대해 구성 된 도메인을 나타냅니다.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EdgeProxyData</p></td>
<td><p>이 특성은 나중에 사용 하기 위해 예약 되어 있습니다.</p></td>
<td><p>실시간 통신 서버 2005의 새로운 방법.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EdgeProxyFQDN</p></td>
<td><p>이 특성은 액세스에 지 서비스를 실행 하는 서버의 FQDN을 지정 합니다.</p>
<p>각 세그먼트의 유효한 값은 63 자입니다. 전체 FQDN에 대 한 유효한 값은 255 자입니다.</p></td>
<td><p>실시간 통신 서버 2005의 새로운 방법.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EnableBestEffortNotify (구식)</p></td>
<td><p>이 특성은 서버에서 클라이언트의 구독 요청에 대 한 응답으로 알림 요청 대신 BENOTIFY (최고 작업량 알림) 요청을 생성할지 여부를 제어 합니다. BENOTIFY는 일반 알림 요청 대신 서버가 BENOTIFY 요청을 생성 하는 구독 알림 핸드셰이크에 대 한 성능 향상 확장입니다. 성능상의 이점은 BENOTIFY 요청에 알림 요청이 수행 하는 것 처럼 클라이언트의 200 OK 응답을 요구 하지 않는다는 것입니다.</p>
<p>유효한 값은 <strong>TRUE</strong> 또는 <strong>FALSE</strong>입니다.</p>
<div>

> [!NOTE]  
> Live Communications Server 2003는 BENOTIFY 요청을 지원 하지 않습니다. Live communications Server 2005 및 타사 서버에서 실행 되는 Live Communications Server 2003 server API를 사용 하 여 작성 된 서버 응용 프로그램과 상호 운용 하려면 해당 값을 <STRONG>FALSE</STRONG>로 설정 하 여 BENOTIFY 요청을 사용 하지 않도록 설정할 수 있습니다. BENOTIFY는 현재 IETF (인터넷 엔지니어링 작업 포스) SIP 표준화 프로세스에 포함 되어 있지 않습니다.


</div></td>
<td><p>실시간 통신 서버 2005의 새로운 방법.</p>
<p>Lync Server 2010에서 더 이상 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EnableFederation (구식)</p></td>
<td><p>이 특성은 사용자가 다른 조직의 사용자와 통신할 수 있는지 여부를 구성 하는 데 사용 되는 전역 스위치입니다. 관리자가 개별 사용자의 <strong>FederationEnabled</strong> 특성을 덮어쓸 수 있도록 합니다. 이 특성은 웜, 바이러스 또는 회사의 대상 공격으로 인해 발생할 수 있는 인터넷 공격 으로부터 내부 네트워크를 보호 하는 데 유용할 수 있습니다.</p>
<p>유효한 값 (및 연결 된 비트 위치)은 다음과 같습니다.</p>
<ul>
<li><p>1: 공용 IM 연결에 사용 (비트 위치 0)</p></li>
<li><p>2: 예약 됨 (비트 위치 1)</p></li>
<li><p>4: 예약 됨 (비트 위치 2)</p></li>
<li><p>8: 예약 됨 (비트 위치 3)</p></li>
<li><p>16: 원격 통화 제어 사용 [전화 통신] (비트 위치 4)</p></li>
<li><p>64: AllowOrganizeMeetingWithAnonymousParticipants (사용자가 모임에 익명 사용자를 초대 하도록 허용 (비트 위치 6)</p></li>
<li><p>128: 작업 사용 (통합 커뮤니케이션에 대해 사용자 사용) (비트 위치 7)</p></li>
<li><p>256: EnabledForEnhancedPresence (공용 IM 연결에 사용자 사용) (비트 위치 8)</p></li>
<li><p>512: RemoteCallControlDualMode (비트 위치 9)</p></li>
</ul></td>
<td><p>실시간 통신 서버 2005의 새로운 방법.</p>
<p>Lync Server 2010에서 더 이상 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EnterpriseServices</p></td>
<td><p>이 특성은 엔터프라이즈 서비스가 지정 된 서버에 로드 되는지 여부를 나타냅니다.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ExtensionData</p></td>
<td><p>이 특성은 나중에 사용 하기 위해 예약 되어 있습니다.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ExternalAccessCode</p></td>
<td><p>이 특성에는 외부 액세스를 위한 전화 번호가 포함 됩니다.</p></td>
<td><p>Office Communications Server 2007 R2의 새로운 방법</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-FederationEnabled</p></td>
<td><p>이 특성은 단일 사용자가 페더레이션을 사용할 수 있는지 여부를 제어 합니다. 엔터프라이즈 서비스 계층에서 적용 됩니다. 이는 글로벌 카탈로그 복제로 표시 됩니다.</p>
<p>유효한 값은 <strong>TRUE</strong> 또는 <strong>FALSE</strong>입니다.</p></td>
<td><p>실시간 통신 서버 2005의 새로운 방법.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-FrontEndServers</p></td>
<td><p>이 특성은 풀과 연결 된 모든 Enterprise Edition 서버의 도메인 이름에 대 한 다중값 목록입니다.</p>
<p>뒤로 링크: <strong>링크 ID 11023</strong></p>
<p>이 역방향 링크에 해당 하는 전방 링크는 <strong>msRTCSIP-PoolAddress</strong>입니다.</p></td>
<td><p>실시간 통신 서버 2005의 새로운 방법.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-게이트웨이 (구식)</p></td>
<td><p>이 다중 값 문자열 특성에는 게이트웨이 별 게이트웨이 및 포트 목록이 포함 됩니다.</p></td>
<td><p>Lync Server 2010에서 더 이상 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-GlobalSettingsData (구식)</p></td>
<td><p>이 특성은 이름: 값 쌍을 저장 합니다. 이미 정의 된 이름: 값 쌍은 <strong>현재 상태 폴링 허용</strong> 설정에 대 한 것입니다.</p></td>
<td><p>Lync Server 2010에서 더 이상 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-GroupingID</p></td>
<td><p>이 특성은 주소록 항목을 그룹화 하는 데 사용 되는 그룹의 고유 식별자입니다.</p></td>
<td><p>Lync Server 2010의 새로운 방법.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-HomeServer (구식)</p></td>
<td><p>-</p></td>
<td><p>Live Communications Server 2003 (사용 되지 않음)의 새로운 방법.</p>
<p>Live Communications Server 2005에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-HomeServerString (구식)</p></td>
<td><p>-</p></td>
<td><p>실시간 통신 서버 2003의 새로운 방법.</p>
<p>Live Communications Server 2005에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-HomeUsers (구식)</p></td>
<td><p>-</p></td>
<td><p>Live Communications Server 2003 (사용 되지 않음)의 새로운 방법.</p>
<p>Live Communications Server 2005에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-InternetAccessEnabled</p></td>
<td><p>이 특성은 외부 사용자 액세스에 대해 단일 사용자를 사용할 수 있는지 여부를 제어 합니다. 엔터프라이즈 서비스 계층에서 적용 됩니다. 이는 글로벌 카탈로그 복제로 표시 됩니다.</p>
<p>유효한 값은 <strong>TRUE</strong> 또는 <strong>FALSE</strong>입니다.</p></td>
<td><p>실시간 통신 서버 2005의 새로운 방법.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-IsMaster (구식)</p></td>
<td><p>-</p></td>
<td><p>실시간 통신 서버 2003의 새로운 방법</p>
<p>Live Communications Server 2005에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP 선</p></td>
<td><p>이 단일 값 특성에는 장치 ID (사용자 컨트롤을 사용 하는 SIP URI 또는 휴대폰의 TEL URI)가 전화 통신을 위해 Lync에서 사용할 것입니다. 이 특성은 글로벌 카탈로그 복제용으로 표시 되며 인덱싱되어 있습니다. 사용자가 엔터프라이즈 음성을 사용할 수 있도록 설정 되어 있는 경우이 특성은 사용자의 전화 번호의 164 정규화 된 버전을 저장 합니다.</p></td>
<td><p>Microsoft Office Live Communications Server 2005 SP1에서 새로 만들기</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LineServer</p></td>
<td><p>이 단일 값 특성에는 CSTA-SIP 게이트웨이 서버의 SIP URI가 포함 됩니다. 이 특성은 글로벌 카탈로그 복제에 대해 표시 되지만 인덱싱되지 않습니다.</p></td>
<td><p>Microsoft Office Live Communications Server 2005 SP1에서 새로 만들기</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocalNormalizationData (구식)</p></td>
<td><p>이 특성은 나중에 사용 하기 위해 예약 되어 있습니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 방법.</p>
<p>Lync Server 2010에서 더 이상 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocalNormalizationLinks (구식)</p></td>
<td><p>이 다중 값 특성에는이 위치 프로필에 연결 된 DN (local 정규화 고유 이름) 목록이 포함 됩니다. 이 특성의 형식은 DN 이진입니다. 위치 프로필과 로컬 정규화 규칙 사이에는 일대다 관계가 있습니다. 로컬 정규화 DNs 목록의 순서는 관리자가 지정한 순서 대로 유지 관리 해야 합니다. 순서 보존은 주문 인덱스를 지정 하는 DN 이진의 이진 부분에 의해 유지 관리 됩니다.</p>
<p>전달 링크: <strong>링크 ID 11034</strong></p>
<p>이 전방 링크 특성에 해당 하는 역방향 링크는 <strong>msRTCSIP-LocationProfileBL</strong>입니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 방법.</p>
<p>Lync Server 2010에서 더 이상 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocalNormalizationOptions</p></td>
<td><p>이 특성에는 정규화 규칙에 대 한 옵션 목록이 포함 되어 있습니다.</p></td>
<td><p>Office Communications Server 2007 R2의 새로운 방법</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocationName (구식)</p></td>
<td><p>이 단일 값 특성에는이 프로필이 나타내는 위치를 나타내는 위치 프로필에 대 한 친근 한 이름이 포함 됩니다. 여러 위치 프로필을 사용할 수 있기 때문에 관리자는 여러 프로필을 구분 하는 방법이 필요 합니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 방법.</p>
<p>Lync Server 2010에서 더 이상 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-locationProfileBL (구식)</p></td>
<td><p>이 다중 값 특성에는 위치 프로필의 고유 이름 목록이 포함 됩니다. 이 특성은 하나 이상의 위치 프로필에 대 한 역방향 링크를 지정 합니다.</p>
<p>뒤로 링크: <strong>링크 ID 11035</strong></p>
<p>이 특성은 전방 링크 <strong>msRTCSIP-LocalNormalizationLinks</strong>에 해당 합니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 방법.</p>
<p>Lync Server 2010에서 더 이상 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocationProfileData (구식)</p></td>
<td><p>이 특성은 나중에 사용 하기 위해 예약 되어 있습니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 방법.</p>
<p>Lync Server 2010에서 더 이상 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocationProfileOptions</p></td>
<td><p>이 특성에는 위치 프로필에 대 한 옵션이 포함 되어 있습니다.</p></td>
<td><p>Office Communications Server 2007 R2의 새로운 방법</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MappingContact</p></td>
<td><p>이 다중 값 특성에는 응용 프로그램 연락처 목록이 들어 있습니다.</p></td>
<td><p>Office Communications Server 2007 R2의 새로운 방법</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MappingLocation</p></td>
<td><p>이 다중 값 특성에는 위치 프로필 목록이 들어 있습니다.</p></td>
<td><p>Office Communications Server 2007 R2의 새로운 방법</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MaxNumOutstandingSearchPerServer (구식)</p></td>
<td><p>이 특성은 서버 당 해결 되지 않은 최대 검색 요청 수를 나타냅니다.</p></td>
<td><p>Lync Server 2010에서 더 이상 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MaxNumSubscriptionsPerUser (구식)</p></td>
<td><p>사용자 당 최대 구독 수를 나타내는 특성입니다.</p></td>
<td><p>Lync Server 2010에서 더 이상 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MaxPresenceSubscriptionTimeout (구식)</p></td>
<td><p>이 특성은 최대 구독 시간 초과 기간을 나타냅니다.</p></td>
<td><p>Lync Server 2010에서 더 이상 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MaxRegistrationsTimeout (구식)</p></td>
<td><p>이 특성은 최대 등록 시간 초과 기간을 나타냅니다.</p></td>
<td><p>Lync Server 2010에서 더 이상 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MaxRoamingDataSubscriptionTimeout (구식)</p></td>
<td><p>이 특성은 최대 로밍 데이터 구독 시간 초과 기간을 나타냅니다.</p></td>
<td><p>Lync Server 2010에서 더 이상 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUData</p></td>
<td><p>이 특성은 나중에 사용 하기 위해 예약 되어 있습니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 방법.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUFactoryAddress</p></td>
<td><p>이 특성은 해당 링크가 속한 MCU (multipoint control unit) Factory에 대 한 링크를 다시 지정 하는 컴퓨터 클래스의 서비스 제어 지점 특성입니다. 이 서비스 제어 지점과 특성은 모든 Microsoft MCU에 대해 만들어집니다. 각 Microsoft MCU는 해당 그룹에서 풀 수준 설정을 검색 하기 위해 자신이 속해 있는 풀의 백 엔드 서버를 찾아야 합니다.</p>
<p>이 특성의 값은 MCU 팩터리의 DN (고유 이름)입니다. 이것은 단일 값 특성이 며 글로벌 카탈로그 복제로 표시 됩니다.</p>
<p>전달 링크: <strong>링크 ID 11026</strong></p>
<p>이 전방 링크 특성에 해당 하는 역방향 링크는 <strong>msRTCSIP-MCUServers</strong>입니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 방법.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUFactoryData</p></td>
<td><p>다중 문자열 예약 된 특성입니다. 이 특성에 저장 된 설정은 이름/값 쌍으로 표현 됩니다. 현재 정의 된 이름/값 쌍은 다음과 같습니다.</p>
<ul>
<li><p>FactoryURL = &lt;URL&gt;</p></li>
</ul></td>
<td><p>Office Communications Server 2007의 새로운 방법.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUFactoryPath</p></td>
<td><p>풀과 연결 된 단일 MCU 팩터리의 DN (고유 이름)을 포함 하는 단일 값 특성입니다.</p>
<p>전달 링크: <strong>링크 ID 11024</strong></p>
<p>이 전방 링크 특성에 해당 하는 역방향 링크는 <strong>msRTCSIP-PoolAddresses</strong>입니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 방법.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUFactoryProviderID</p></td>
<td><p>이 특성은 MCU factory provider의 GUID를 지정 하는 단일 값 문자열입니다. GUID 값을 기준으로 MCU factory 프로세스는이 MCU 형식을 서비스 하는지 여부를 결정 합니다. GUID 값이 <strong>{F0810510-424F-46ef-84FE-6CC720DF1791}</strong>인 경우 MCU factory 프로세스 (Lync Server에서 기본적으로 사용 가능)가 처리 됩니다. 다른 GUID 값에 대해서는 MCU factory 프로세스가 MCU 형식을 서비스 하지 않습니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 방법.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUServers</p></td>
<td><p>이 특성은 DN (고유 이름)의 다중 값 목록입니다. 이 특성에는이 MCU 팩터리에 연결 된 동일한 종류 및 공급 업체의 모든 MCU 서버 목록이 포함 됩니다. 각 세그먼트의 유효한 값은 63 자입니다. 전체 FQDN에 대 한 유효한 값은 255 자입니다.</p>
<p>뒤로 링크: 링크 ID 11027</p>
<p>이 후방에 해당 하는 전방 링크는 <strong>msRTCSIP-MCUFactoryAddress</strong>입니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 방법.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-M가공선</p></td>
<td><p>이 특성은 MCU가 처리할 수 있는 매체를 지정 하는 단일 값 문자열입니다.</p>
<p>지원 되는 유효한 유형은 다음과 같습니다.</p>
<ul>
<li><p>모임을</p></li>
<li><p>오디오-영상</p></li>
<li><p>채트</p></li>
<li><p>휴대폰-회의</p></li>
</ul></td>
<td><p>Office Communications Server 2007의 새로운 방법.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUVendor 공급 업체</p></td>
<td><p>이 특성은 MCU 공급 업체의 이름을 지정 하는 단일 값 문자열입니다. 모든 Microsoft MCUs는이 특성을 <strong>Microsoft Corporation</strong>으로 지정 합니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 방법.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MeetingFlags (구식)</p></td>
<td><p>이 특성은 모든 사용자 또는 연락처 개체에 전체적으로 사용할 수 있는 다른 모임 옵션을 정의 합니다. 이 특성은 정수 형식의 비트 마스크 값입니다.</p>
<p>유효한 값 (및 연결 된 비트 위치)은 다음과 같습니다.</p>
<ul>
<li><p>0: AllowOrganizeMeetingWithAnonymousParticipants가 없음 (사용자가 익명 사용자를 모임에 초대 하지 않도록 허용 하지 않음) (비트가 설정 되지 않음)</p></li>
<li><p>4: AllowOrganizeMeetingWithAnonymousParticipants는 Everyone (모든 사용자가 익명 사용자를 모임에 초대할 수 있도록 허용) (비트 위치 2)</p></li>
<li><p>8: AllowOrganizeMeetingWithAnonymousParticipants는 UsePerUserSetting (사용자가 사용자별 설정에 기반 하 여 모임에 익명 사용자를 초대 하도록 허용) (비트 위치 3)</p></li>
<li><p>16: UserPerUserMeetingPolicy (모임 정책이 사용자 당 정의 됨) (비트 위치 4)</p></li>
</ul></td>
<td><p>Office Communications Server 2007의 새로운 방법.</p>
<p>Lync Server 2010에서 더 이상 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MeetingPolicy (구식)</p></td>
<td><p>이 특성은 관리자가이 사용자에 게 할당 한 정책의 DN (고유 이름)을 단일 값 특성으로 지정 합니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 방법.</p>
<p>Lync Server 2010에서 더 이상 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MinPresenceSubscriptionTimeout (구식)</p></td>
<td><p>이 특성은 최소 현재 상태 구독 시간 초과 창을 나타냅니다.</p></td>
<td><p>Lync Server 2010에서 더 이상 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MinRegistrationTimeout (구식)</p></td>
<td><p>이 특성은 최소 등록 시간 초과 창을 나타냅니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 방법.</p>
<p>Lync Server 2010에서 더 이상 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MinRoamingDataSubscriptionTimeout (구식)</p></td>
<td><p>이 특성은 최소 로밍 데이터 구독 시간 초과 창을 나타냅니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 방법.</p>
<p>Lync Server 2010에서 더 이상 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MirrorBackEndServer</p></td>
<td><p>이 특성은 프런트 엔드 풀에 사용 되는 미러된 SQL Server 백 엔드를 저장 하는 데 사용 됩니다.</p></td>
<td><p>Lync Server 2013의 새로운 방법.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MobilityFlags</p></td>
<td><p>이 특성은 이동성 설정을 정의 하는 옵션과 플래그를 포함 합니다.</p></td>
<td><p>Office Communications Server 2007 R2의 새로운 방법</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MobilityPolicy</p></td>
<td><p>이 특성은 이동성 정책 개체의 DN을 포함 합니다.</p></td>
<td><p>Office Communications Server 2007 R2의 새로운 방법</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-NumDevicesPerUser (구식)</p></td>
<td><p>이 특성은 사용자가 SIP 통신을 등록 하 고 현재 상태를 구독할 수 있는 허용 되는 장치 수를 나타냅니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 방법.</p>
<p>Lync Server 2010에서 더 이상 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP 플래그</p></td>
<td><p>이 특성은 사용자 또는 연락처 개체에 대해 사용 하도록 설정 된 옵션을 지정 합니다. 이 특성은 integer 형식의 비트 마스크 값입니다. 각 옵션은 비트로 표시 됩니다. 이 특성은 글로벌 카탈로그 복제용으로 표시 되어 있습니다.</p>
<p>유효한 값 (및 연결 된 비트 위치)은 다음과 같습니다.</p>
<ul>
<li><p>1: 공용 인스턴트 메시징 (IM) 연결에 사용 (비트 위치 0)</p></li>
<li><p>2: 예약 됨 (비트 위치 1)</p></li>
<li><p>4: 예약 됨 (비트 위치 2)</p></li>
<li><p>8: 예약 됨 (비트 위치 3)</p></li>
<li><p>16: 원격 통화 제어 사용 [전화 통신] (비트 위치 4)</p></li>
<li><p>64: AllowOrganizeMeetingWithAnonymousParticipants (사용자가 모임에 익명 사용자를 초대 하도록 허용 (비트 위치 6)</p></li>
<li><p>128: 작업 사용 (UC 사용자 사용) (비트 위치 7)</p></li>
<li><p>256: EnabledForEnhancedPresence (공용 IM 연결에 사용자 사용) (비트 위치 8)</p></li>
<li><p>512: RemoteCallControlDualMode (비트 위치 9)</p></li>
</ul></td>
<td><p>실시간 통신 서버 2005 (SP1)에서 새로 만들기.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-OriginatorSID</p></td>
<td><p>이 특성은 Windows NT Server principal 계정에서 사용자의 ObjectSID이 리소스 또는 중앙 포리스트의 해당 사용자 또는 연락처 개체의이 특성으로 복사 될 때 single sign-on을 사용 하도록 설정 하기 위해 리소스 및 중앙 포리스트 토폴로지에 사용 됩니다. Communicator Web Access는이 특성 또는 사용자의 ObjectSID를 사용 하 여 AD DS에 있는 사용자를 검색 합니다. 이 특성은 글로벌 카탈로그 복제용으로 표시 되어 있습니다.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-소유자 Urn</p></td>
<td><p>이 특성은 응용 프로그램 연락처에 대 한 소유자의 URN (Uniform Resource Name)입니다.</p></td>
<td><p>Lync Server 2010의 새로운 방법.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-패턴 (구식)</p></td>
<td><p>이 단일 값 문자열 특성에는 다이얼 번호와 일치 하는 데 사용 되는 패턴이 전자 164 형식으로 포함 됩니다. 전화 번호가이 패턴과 일치 하는 경우에는 전화를 건 번호에 번역이 적용 됩니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 방법.</p>
<p>Lync Server 2010에서 더 이상 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PhoneRouteBL (구식)</p></td>
<td><p>이 다중 값 특성에는 DN (전화 경로 고유 이름) 목록이 포함 됩니다. 이 특성은 하나 이상의 휴대폰 경로에 대 한 역방향 링크를 지정 합니다.</p>
<p>뒤로 링크: <strong>링크 ID 11033</strong></p>
<p>이 특성은 전방 링크 <strong>msRTCSIP-RouteUsageLinks</strong>에 해당 합니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 방법.</p>
<p>Lync Server 2010에서 더 이상 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PhoneRouteData (구식)</p></td>
<td><p>이 특성은 나중에 사용 하기 위해 예약 되어 있습니다.</p></td>
<td><p>Lync Server 2010에서 더 이상 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PhoneRouteName (구식)</p></td>
<td><p>이 단일 값으로 된 UNICODE 문자열 특성은 전화 경로의 친숙 한 이름을 지정 하므로 관리자가 쉽게 참조할 수 있습니다.</p></td>
<td><p>Lync Server 2010에서 더 이상 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PhoneUsageData (구식)</p></td>
<td><p>이 특성은 나중에 사용 하기 위해 예약 되어 있습니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 방법.</p>
<p>Lync Server 2010에서 더 이상 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PolicyContent (구식)</p></td>
<td><p>이 특성은 단일 값 유니코드 문자열입니다. 이 문자열 특성은 XML 형식의 정책 정의를 포함 합니다. XML 스키마 정의는 여러 정책 형식에서 공통 되며 각 정책 유형에 대 한 설정만 다릅니다.</p>
<p>XSD (XML 스키마 정의)는 다음과 같이 정의 됩니다.</p>
<pre><code>&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;
&lt;xs:schema id=&quot;instance&quot; xmlns=&quot;&quot; xmlns:xs=&quot;http://www.w3.org/2001/XMLSchema&quot; xmlns:msdata=&quot;urn:schemas-microsoft-com:xml-msdata&quot;&gt;
  &lt;xs:element name=&quot;instance&quot; msdata:IsDataSet=&quot;true&quot;&gt;
    &lt;xs:complexType&gt;
      &lt;xs:choice maxOccurs=&quot;unbounded&quot;&gt;
        &lt;xs:element name=&quot;property&quot; nillable=&quot;true&quot;&gt;
          &lt;xs:complexType&gt;
            &lt;xs:simpleContent msdata:ColumnName=&quot;property_Text&quot; msdata:Ordinal=&quot;1&quot;&gt;
              &lt;xs:extension base=&quot;xs:string&quot;&gt;
                &lt;xs:attribute name=&quot;name&quot; type=&quot;xs:string&quot; /&gt;
              &lt;/xs:extension&gt;
            &lt;/xs:simpleContent&gt;
          &lt;/xs:complexType&gt;
        &lt;/xs:element&gt;
      &lt;/xs:choice&gt;
    &lt;/xs:complexType&gt;
  &lt;/xs:element&gt;
&lt;/xs:schema&gt;</code></pre></td>
<td><p>Office Communications Server 2007의 새로운 방법.</p>
<p>Lync Server 2010에서 더 이상 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PolicyData (구식)</p></td>
<td><p>이 특성은 나중에 사용 하기 위해 예약 되어 있습니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 방법.</p>
<p>Lync Server 2010에서 더 이상 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PolicyType (구식)</p></td>
<td><p>이 단일 값 유니코드 문자열 특성에는 정책 형식이 포함 되어 있습니다. 유효한 정책 유형은 다음과 같습니다.</p>
<ul>
<li><p>모임을</p></li>
<li><p>통신</p></li>
</ul></td>
<td><p>Office Communications Server 2007의 새로운 방법.</p>
<p>Lync Server 2010에서 더 이상 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolAddress</p></td>
<td><p>이 특성은 컴퓨터가 속한 풀로 돌아가는 링크를 지정 합니다. 이 특성은 컴퓨터에서 Lync Server의 Standard Edition 또는 Enterprise Edition을 실행 하 고 있는지 여부에 관계 없이 설정 됩니다. 이 특성은 글로벌 카탈로그 복제용으로 표시 되어 있습니다.</p>
<p>유효한 값은 풀의 도메인 이름입니다.</p>
<p>전달 링크: <strong>링크 ID 11022</strong></p>
<p>이 전방 링크 특성에 해당 하는 역방향 링크는 <strong>msRTCSIP-FrontEndServers</strong>입니다.</p></td>
<td><p>실시간 통신 서버 2005의 새로운 방법.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PoolAddresses</p></td>
<td><p>이는 MCU 팩터리가 연결 된 풀의 DN (고유 이름) 목록이 포함 된 다중 값 특성입니다.</p>
<p>뒤로 링크: <strong>링크 ID 11025</strong></p>
<p>이 후방에 해당 하는 전방 링크는 <strong>msRTCSIP-MCUFactoryPath</strong>입니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 방법.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolData</p></td>
<td><p>이 특성은 나중에 사용 하기 위해 예약 되어 있습니다.</p></td>
<td><p>실시간 통신 서버 2005 (SP1)에서 새로 만들기.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PoolDisplayName</p></td>
<td><p>이 특성은 관리 콘솔에 표시 되는 풀에 대 한 임의 이름을 지정 합니다. 이 이름은 관리자가 변경할 수 있습니다.</p>
<p>유효한 값은 풀의 이름을 나타내는 문자열입니다.</p></td>
<td><p>실시간 통신 서버 2005의 새로운 방법.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolDomainFQDN</p></td>
<td><p>이 특성은 단일 값 문자열 값입니다. 이 특성의 값이 있으면 관리자가 프런트 엔드 풀을 만든 Active Directory 도메인 구조에 맞지 않는 FQDN을 사용 하 여 프런트 엔드 풀을 만들려는 경우 풀의 도메인 FQDN을 나타냅니다 (예: SIP DNS (Domain Name System) 네임 스페이스에 대 한 네임 스페이스의 가입이 해제 되었습니다.</p>
<p>프런트 엔드 풀 도메인 FQDN을 해당 풀이 있는 Active Directory 도메인으로 도메인 이름 부분에 매핑하는 것이 좋습니다. 따라서이 특성에 값이 없는 경우에는 <strong>dnsHostName</strong> 특성이 표시 하는 것 처럼 프런트 엔드 풀 FQDN이 Active Directory 도메인 이름 구조를 기본값으로 합니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 방법.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PoolFunctionality</p></td>
<td><p>풀과 연결 된 모든 Lync Server 엔터프라이즈 버전 서버의 도메인 이름에 대 한 다중 값 목록입니다. 이 integer 형식의 특성은 풀이 인스턴트 메시지 (IM)와 현재 상태, 모임을 사용할 수 있는지 여부를 정의 합니다.</p>
<p>가능한 유효한 값 형식은 다음과 같습니다.</p>
<ul>
<li><p>정의 되지 않음: IM 및 현재 상태 서비스 (Live Communications Server 2005 및 2003)</p></li>
<li><p>1: IM 및 현재 상태 서비스 (Lync 서버)</p></li>
<li><p>2: IM 및 현재 상태 및 모임 서비스 (Lync 서버)</p></li>
</ul></td>
<td><p>Office Communications Server 2007의 새로운 방법.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolType</p></td>
<td><p>이 특성은 서버 풀이 Standard Edition server 또는 Enterprise Edition 서버를 실행 하 고 있는지 여부를 지정 합니다. 이 특성은 integer 형식의 비트 마스크 값입니다. 각 옵션은 비트로 표시 됩니다.</p>
<p>유효한 값 (및 연결 된 비트 위치)은 다음과 같습니다.</p>
<ul>
<li><p>1: 스탠더드 버전 서버, 호스트 사용자 (비트 위치 0)</p></li>
<li><p>2: Enterprise Edition server, 호스트 사용자 (비트 위치 1)</p></li>
<li><p>4: 스탠더드 버전 서버, 호스트 응용 프로그램 (비트 위치 2)</p></li>
<li><p>8: Enterprise Edition server, 호스트 응용 프로그램 (비트 위치 3)</p></li>
</ul>
<p>Lync Server는 응용 프로그램을 호스트 하는 풀을 지원 하지 않으므로 유효한 값은 다음과 같습니다.</p>
<ul>
<li><p>5: Standard Edition 서버, 호스트 사용자 및 응용 프로그램 (비트 위치 0 및 2)</p></li>
<li><p>10: Enterprise Edition server, 호스트 사용자 및 응용 프로그램 (비트 위치 1 및 3)</p></li>
</ul></td>
<td><p>실시간 통신 서버 2005의 새로운 방법.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PoolVersion</p></td>
<td><p>이 특성은 풀 버전을 정의 합니다. 각 주요 제품 릴리스로 증가 하는 정수 형식입니다.</p>
<p>가능한 유효한 값 형식은 다음과 같습니다.</p>
<ul>
<li><p>0: Live Communications Server 2003</p></li>
<li><p>1: Live Communications Server 2005</p></li>
<li><p>2: 실시간 통신 서버 2005 (SP1)</p></li>
<li><p>3: Office Communications Server 2007</p></li>
<li><p>4: Office Communications Server 2007 R2</p></li>
<li><p>5: Lync Server 2010</p></li>
</ul></td>
<td><p>실시간 통신 서버 2005 (SP1 포함).</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PresenceFlags</p></td>
<td><p>이 특성은 현재 상태 설정을 정의 하는 옵션과 플래그를 포함 합니다.</p></td>
<td><p>Office Communications Server 2007 R2의 새로운 방법</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PresencePolicy</p></td>
<td><p>이 특성에는 현재 상태 정책 개체의 DN이 포함 됩니다.</p></td>
<td><p>Office Communications Server 2007 R2의 새로운 방법</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PrimaryHomeServer</p></td>
<td><p>이 특성은 SIP 메시지에 대 한 사용자 또는 연락처를 활성화 합니다. 중앙 포리스트 토폴로지에서는 사용자 개체가 아닌 연락처 개체는 SIP를 사용할 수 있기 때문에 contact 클래스에 추가 됩니다.</p>
<p>유효한 값은 사용자가 속한 Standard Edition server 또는 Enterprise Edition 프런트 엔드 풀의 DN입니다.</p></td>
<td><p>실시간 통신 서버 2005의 새로운 방법.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PrimaryUserAddress</p></td>
<td><p>이 특성에는 특정 사용자의 SIP 주소가 포함 됩니다.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PrivateLine</p></td>
<td><p>이 특성에는 개인 회선 디바이스의 디바이스 ID가 포함 되어 있습니다.</p></td>
<td><p>Lync Server 2010의 새로운 방법.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-라우팅 가능</p></td>
<td><p>이 특성은 Lync Server에서 GRUU 주소를 사용 하 여이 서비스로 라우팅할 권한이 있는지 여부를 결정 하는 데 사용 되는 부울 특성입니다. 이 값을 <strong>TRUE</strong>로 설정 하는 경우 Lync Server에이 서비스로 라우팅할 수 있는 권한이 부여 됩니다. 이 값을 <strong>FALSE</strong>로 설정 하는 경우 Lync Server에는이 서비스로 라우팅할 수 있는 권한이 없습니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 방법.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-RouteUsageAttribute (구식)</p></td>
<td><p>이 단일 값 유니코드 문자열 특성은 전화 경로의 사용을 정하는 특성을 정의 합니다. 전화 경로의 선택은 두 가지 요소, 즉 전화 경로에 할당 된 사용 특성과 호출자가 허용 되는 정책 사용 특성을 기준으로 결정 됩니다. 호출자의 허용 사용이 일치 하는 사용 특성이 있는 첫 번째 전화 경로가 선택 됩니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 방법.</p>
<p>Lync Server 2010에서 더 이상 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-RouteUsageLinks (구식)</p></td>
<td><p>이 다중 값 고유 이름 (DN) 특성에는 경로 사용 고유 이름 목록이 포함 되어 있습니다.</p>
<p>전달 링크: <strong>링크 ID 11032</strong></p>
<p>이 특성은 해당 하는 뒤로 링크 <strong>msRTCSIP-PhoneRouteBL</strong>에 대 한 전방 링크입니다.</p></td>
<td><p>Lync Server 2010에서 더 이상 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-RoutingPoolDN</p></td>
<td><p>이 특성에는이 MCU 또는 신뢰할 수 있는 서비스로 주소가 지정 된 모든 SIP 트래픽이 통과 해야 하는 풀을 가리키는 DN이 포함 됩니다.</p></td>
<td><p>Office Communications Server 2007 R2의 새로운 방법</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-RuleName (구식)</p></td>
<td><p>이 단일 값 유니코드 문자열 특성은 정규화 규칙의 이름을 지정 하 여 관리자가 쉽게 참조할 수 있도록 합니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 방법.</p>
<p>Lync Server 2010에서 더 이상 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-SchemaVersion</p></td>
<td><p>이 특성은 현재 조직에 배포 된 스키마 버전을 나타냅니다.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-SearchMaxRequests (구식)</p></td>
<td><p>이 특성은 사용자가 Communicator를 사용 하 여 연락처를 검색할 때 디렉터리 검색에서 반환 되는 검색 결과의 수를 제한 합니다. 이 특성은 클라이언트에서 제공 하는 값을 재정의 합니다.</p></td>
<td><p>Lync Server 2010에서 더 이상 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-SearchMaxResults (구식)</p></td>
<td><p>이 특성은 반환 되는 검색 요청 수를 제한 합니다.</p></td>
<td><p>Lync Server 2010에서 더 이상 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ServerBL</p></td>
<td><p>이 다중 값 특성은 DN (고유 이름) 목록을 포함 하는 역방향 링크입니다. 이러한 DNs는 풀이나 <strong>서비스</strong> 개체를 가리킵니다.</p>
<p>이 특성은 전방 링크 <strong>msRTCSIP-TrustedServiceLinks</strong>에 해당 합니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 방법.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ServerData</p></td>
<td><p>이 특성은 나중에 사용 하기 위해 예약 되어 있습니다.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ServerReferenceBL (구식)</p></td>
<td><p>이 다중값 특성에는 고유 이름 목록이 포함 되어 있습니다. 이러한 고유 이름은 기본 위치 프로필을 할당할 수 있는 다른 서버 개체를 참조 하는 역방향 링크입니다.</p>
<p>뒤로 링크: <strong>링크 ID 11037</strong></p>
<p>이 후방 링크에 해당 하는 전방 링크는 <strong>msRTCSIP-DefaultLocationProfileLink</strong>입니다.</p>
<p>이 뒤로 링크 특성은 풀 및 중재 서버만 참조 합니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 방법.</p>
<p>Lync Server 2010에서 더 이상 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ServerVersion</p></td>
<td><p>이 특성은 서버의 버전 정보를 정의 합니다. 이 버전 번호는 모든 서버 역할에 적용 됩니다. 이는 각 공식 제품 릴리스로 증가 하는 monotonously 증가 하는 정수입니다.</p>
<p>가능한 유효한 값은 다음과 같습니다.</p>
<ul>
<li><p>Undefined: Live Communications Server 2003</p>
<p>                 Live Communications Server 2005</p>
<p>                 실시간 통신 서버 2005 (SP1)</p></li>
<li><p>3: Office Communications Server 2007</p></li>
<li><p>4: Office Communications Server 2007 R2</p></li>
<li><p>5: Lync Server 2010</p></li>
<li><p>6: Lync Server 2013</p></li>
</ul></td>
<td><p>Office Communications Server 2007의 새로운 방법.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-SourceObjectType</p></td>
<td><p>정수 형식의이 단일 값 특성은 다음과 같이 <strong>msDS-SourceObjectDN</strong> 가 가리키는 개체의 유형을 지정 합니다.</p>
<ul>
<li><p>null | 0x00000001: 다른 포리스트의 Windows NT Server principal 사용자 개체를 나타냅니다.</p></li>
<li><p>다음 특성은 메일 그룹 확장에 대해 다른 포리스트의 그룹 유형을 나타냅니다.</p>
<ul>
<li><p>0x00000002: ADS_GROUP_TYPE_GLOBAL_GROUP</p></li>
<li><p>0x00000004: ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</p></li>
<li><p>0x00000004: ADS_GROUP_TYPE_LOCAL_GROUP</p></li>
<li><p>0x00000008: ADS_GROUP_TYPE_UNIVERSAL_GROUP</p></li>
<li><p>0x80000000: ADS_GROUP_TYPE_SECURITY_ENABLED</p></li>
<li><p>0x90000000: 같은 포리스트나 다른 포리스트의 자동 전화 교환 또는 구독자 액세스 개체를 나타냅니다.</p></li>
</ul></li>
</ul></td>
<td><p>Office Communications Server 2007의 새로운 방법.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-SubscriptionAuthRequired (구식)</p></td>
<td><p>-</p></td>
<td><p>실시간 통신 서버 2003의 새로운 방법.</p>
<p>Live Communications Server 2005에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TargetHomeServer</p></td>
<td><p>이 특성을 사용 하면 사용자 또는 연락처 개체를 Lync 서버 풀 간에 이동할 수 있습니다. 중앙 포리스트 토폴로지에서는 사용자 개체가 아닌 contact 개체를 SIP로 설정 하기 때문에이 특성은 contact 클래스에 추가 됩니다.</p>
<p>유효한 값은 사용자가 이동할 대상 Standard Edition server 또는 프런트 엔드 풀의 DN입니다.</p></td>
<td><p>실시간 통신 서버 2005의 새로운 방법.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TargetPhoneNumber (구식)</p></td>
<td><p>이 단일 값 문자열 특성에는 <strong>msRTCSIP</strong>에 정의 된 특정 게이트웨이로 라우팅하기 위한 전화 번호 패턴 또는 범위가 포함 됩니다.</p></td>
<td><p>Lync Server 2010에서 더 이상 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TargetUserPolicies</p></td>
<td><p>이 특성은 Lync Server 사용자의 대상 정책에 대 한 이름-값 쌍을 저장 합니다.</p></td>
<td><p>Lync Server 2010의 새로운 방법.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TenantId</p></td>
<td><p>이 특성은 테 넌 트에 대 한 고유 식별자를 저장 합니다.</p></td>
<td><p>Lync Server 2010의 새로운 방법.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-번역 (구식)</p></td>
<td><p>이 특성은 Lync Server의 음성 기능에 사용 되며, 일치 하는 항목을 찾은 경우, 전화를 건 번호에 적용할 번역 문자열을 포함 합니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 방법.</p>
<p>Lync Server 2010에서 더 이상 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Trustedm데이터</p></td>
<td><p>이 특성은 나중에 사용 하기 위해 예약 되어 있습니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 방법.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Trustedm의 Fqdn</p></td>
<td><p>이 특성은 MCU의 FQDN을 포함 하는 문자열 값입니다. 이것은 단일 값 특성입니다. 각 세그먼트의 유효한 값은 63 자입니다. 전체 FQDN에 대 한 유효한 값은 255 자입니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 방법.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP Proxydata</p></td>
<td><p>이 특성은 나중에 사용 하기 위해 예약 되어 있습니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 방법.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-을 (를)로 하는 Proxyfqdn</p></td>
<td><p>이 특성은 프록시 서버를 실행 하는 서버의 FQDN을 포함 하는 문자열 값입니다. 이 특성은 단일 값을 갖습니다. 각 세그먼트의 유효한 값은 63 자입니다. 전체 FQDN에 대 한 유효한 값은 255 자입니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 방법.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP Serverdata</p></td>
<td><p>이 특성은 나중에 사용 하기 위해 예약 되어 있습니다.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-로 비트 하는 Serverfqdn</p></td>
<td><p>이 특성은 신뢰할 수 있는 서버의 FQDN을 나타내는 단일 값 특성입니다.</p></td>
<td><p>실시간 통신 서버 2005의 새로운 방법.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP Serverversion</p></td>
<td><p>이 특성은 신뢰 된 서버 목록에 있는 서버의 버전 번호를 지정 합니다.</p>
<p>가능한 유효한 값은 다음과 같습니다.</p>
<ul>
<li><p>NULL: Live Communications Server 2003</p></li>
<li><p>2: Live Communications Server 2005</p></li>
<li><p>3: Office Communications Server 2007</p></li>
<li><p>4: Office Communications Server 2007 R2</p></li>
<li><p>5: Lync Server 2010</p></li>
<li><p>6: Lync Server 2013</p></li>
</ul></td>
<td><p>실시간 통신 서버 2005의 새로운 방법.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-(비트)로가는 플래그</p></td>
<td><p>이 특성은 신뢰 된 서비스에 대해 사용 하도록 설정 된 옵션을 정의 합니다.</p></td>
<td><p>Office Communications Server 2007 R2의 새로운 방법</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServiceLinks</p></td>
<td><p>이 다중 값 특성에는 미디어 릴레이 인증 서비스와 같이 신뢰할 수 있는 서비스 개체를 참조 하는 DN (고유 이름) 목록이 포함 됩니다. 미디어 릴레이 인증 서비스 (A/V 회의 서비스를 실행 하는 Edge 서버를 물리적으로 collocated)는 원격 사용자를 위한 오디오 시나리오를 지원 하기 위해 풀에 연결 되어 있어야 합니다.</p>
<p>이 전방 링크 특성에 해당 하는 역방향 링크는 <strong>msRTCSIP-ServerBL</strong>입니다.</p></td>
<td><p>UC</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-(와)로 이루어진 Serviceport</p></td>
<td><p>이 특성은이 GRUU 서비스에 연결 하는 데 사용 되는 포트 번호를 정의 하는 정수입니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 방법.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP의로이는 Servicetype</p></td>
<td><p>이 특성은 해당 속성이 나타내는 GRUU 서비스의 형식을 정의 하는 문자열 값입니다.</p>
<p>유효한 GRUU 서비스 유형은 다음과 같습니다.</p>
<ul>
<li><p>MediationServer</p></li>
<li><p>게이트웨이와</p></li>
<li><p>MRAS (미디어 릴레이 인증 서비스)</p></li>
<li><p>QoSM</p></li>
<li><p>msRTCSIP-UserExtension CWA</p></li>
</ul></td>
<td><p>Office Communications Server 2007의 새로운 방법.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedWebComponentsServerData</p></td>
<td><p>이 특성은 나중에 사용 하기 위해 예약 되어 있습니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 방법.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedWebComponentsServerFQDN</p></td>
<td><p>이 특성은 Lync Server Web Services를 실행 하는 IIS의 FQDN을 포함 하는 문자열 값입니다. 이것은 단일 값 특성입니다. 각 세그먼트의 유효한 값은 63 자입니다. 전체 FQDN에 대 한 유효한 값은 255 자입니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 방법.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP 플래그 (구식)</p></td>
<td><p>이 특성은 모든 사용자 또는 연락처 개체에 전역적으로 사용할 수 있는 다른 UC 옵션을 정의 합니다. 이 특성은 정수 형식의 비트 마스크 값입니다. 각 옵션은 비트의 현재 상태에 따라 표시 됩니다.</p>
<p>가능한 유효한 값 (및 연결 된 비트 위치)은 다음과 같습니다.</p>
<ul>
<li><p>4: Useperuser작업 정책 (비트 위치 2)</p></li>
</ul>
<p>이 비트가 설정 되 면 사용자 당 UC 정책이 정의 됩니다.</p></td>
<td><p>Lync Server 2010에서 더 이상 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP 정책 (구식)</p></td>
<td><p>이 단일 값 특성은 관리자가이 사용자에 대해 할당 한 UC 정책의 DN (고유 이름)을 포함 합니다.</p></td>
<td><p>Lync Server 2010에서 더 이상 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP Domainlist (구식)</p></td>
<td><p>이 특성은 SIP 사용 가능 사용자를 호스팅하는 포리스트의 모든 도메인 목록을 제공 합니다. 기본값은 포리스트의 모든 도메인이 SIP를 사용할 수 있음을 나타내는 빈 목록입니다.</p>
<p>유효한 값은 개별 도메인의 도메인 이름을 나타내는 여러 문자열입니다.</p></td>
<td><p>실시간 통신 서버 2005의 새로운 방법.</p>
<p>Lync Server 2010에서 더 이상 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-UserEnabled</p></td>
<td><p>이 특성은 사용자가 현재 Lync Server를 사용할 수 있는지 여부를 결정 합니다.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>UserExtension msRTCSIP</p></td>
<td><p>이 다중 값 특성에는 &quot;name = value 형식의 이름-값 쌍 목록이 포함 됩니다. &quot; 이 특성은 글로벌 카탈로그 복제용으로 표시 되어 있습니다.</p></td>
<td><p>실시간 통신 서버 2005 (SP1)에서 새로 만들기.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-UserLocationProfile</p></td>
<td><p>이 특성은 위치 프로필 개체를 가리키는 DN (고유 이름)을 포함 합니다.</p></td>
<td><p>Office Communications Server 2007 R2의 새로운 방법</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserPolicies</p></td>
<td><p>이 특성은 사용자 정책에 대 한 이름-값 쌍을 저장 합니다.</p></td>
<td><p>Lync Server 2010의 새로운 방법.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-UserPolicy</p></td>
<td><p>이는 서로 다른 유형의 전역 사용자 정책을 가리키는 binary (DN_WITH_BINARY)를 사용 하 여 고유 이름 목록을 포함 하는 다중 값 특성입니다. 이진 부분은 DN 부분이 가리키는 정책의 유형을 나타냅니다.</p>
<p>유효한 이진 값은 다음과 같습니다.</p>
<ul>
<li><p>0x00000001: 모임 정책</p></li>
<li><p>0x00000002: UC 정책</p></li>
<li><p>0x00000005: 현재 상태 정책</p></li>
</ul></td>
<td><p>Office Communications Server 2007의 새로운 방법.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserRoutingGroupId</p></td>
<td><p>SIP 라우팅 그룹 ID입니다. 같은 그룹의 사용자가 동일한 프런트 엔드 서버에 등록 됩니다.</p></td>
<td><p>Lync Server 2013의 새로운 방법.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-WebComponentsData</p></td>
<td><p>다중값 특성입니다. 이 특성은 나중에 사용 하기 위해 예약 되어 있습니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 방법.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-WebComponentsPoolAddress</p></td>
<td><p>이 단일 값 특성은 웹 구성 요소가 속해 있는 풀 또는 Standard Edition 서버를 가리킵니다.</p>
<p>전달 링크: <strong>링크 ID 11028</strong></p>
<p>이 전방 링크 특성에 해당 하는 역방향 링크는 <strong>msRTCSIP-WebComponentsServers</strong>입니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 방법.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-WebComponentsServers</p></td>
<td><p>이 특성은 고유 이름에 대 한 다중값 목록입니다. 이 특성에는이 풀과 연결 된 모든 웹 서버의 목록이 포함 됩니다.</p>
<p>뒤로 링크: <strong>링크 ID 11029</strong></p>
<p>이 후방에 해당 하는 전방 링크는 <strong>msRTCSIP-WebComponentsPoolAddress</strong>입니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 방법.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-WMIInstanceId (구식)</p></td>
<td><p>-</p></td>
<td><p>실시간 통신 서버 2003의 새로운 방법.</p>
<p>Live Communications Server 2005에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>OtherIPPhone</p></td>
<td><p>전화 통신에서이 기존 Active Directory 특성을 사용 하 여 전화기에 대 한 대체 TCP/IP 주소 목록을 지정 합니다.</p></td>
<td><p>Windows Server 2008 운영 체제의 새로운 방법.</p></td>
</tr>
<tr class="even">
<td><p>PhoneOfficeOther</p></td>
<td><p>이 기존 Active Directory 특성은 연락처 개체만을 위해 Lync Server의 음성 구성 요소에 사용 되며, 통합 메시징 자동 전화 교환 및 구독자 액세스 번호로의 라우팅에는 해당 용도로만 사용할 수 있습니다. 무조건 통화 전달 주소는이 다중값 특성에 저장 됩니다. 이 계정은 자동 전화 교환 및 구독자 액세스의 특정 목적을 위해 만들어집니다. 관리자가이 계정의 특성을 수정 해서는 안 됩니다.</p></td>
<td><p>Windows 2000 운영 체제의 새로운 방법.</p></td>
</tr>
<tr class="odd">
<td><p>ProxyAddresses</p></td>
<td><p>이 기존 Active Directory 다중 값 특성은 Windows 2000에서 도입 된 기본 Active Directory 스키마의 일부입니다. 이 특성에는 사용자의 전자 메일에 대 한 다양 한 X400, X500 및 SMTP 주소가 포함 됩니다. Live Communications Server 2003 이상에서는 &quot;sip:&quot; 태그를 사용 하 여 사용자의 sip URI가이 목록에 추가 됩니다.</p>
<p>다음 응용 프로그램은 사용자의 SIP URI를이 특성에서 검색 합니다.</p>
<ul>
<li><p>Microsoft Office Outlook 2003 메시징 및 공동 작업 클라이언트</p></li>
<li><p>Microsoft Office SharePoint Server 2007</p></li>
</ul></td>
<td><p>Windows 2000 운영 체제의 새로운 방법.</p></td>
</tr>
<tr class="even">
<td><p>TelephoneNumber</p></td>
<td><p>이 기존 Active Directory 특성은 사용자의 전화 번호를 포함 합니다.</p></td>
<td><p>Windows 2000 운영 체제의 새로운 방법.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

