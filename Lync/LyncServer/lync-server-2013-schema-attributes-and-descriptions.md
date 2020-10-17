---
title: 'Lync Server 2013: 스키마 특성 및 설명'
description: 'Lync Server 2013: 스키마 특성 및 설명입니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Schema attributes and descriptions
ms:assetid: b009df76-9c22-471d-b57a-bda009a98261
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412841(v=OCS.15)
ms:contentKeyID: 48185083
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18888d20a772b3e84970e7d874bd6b6964affc75
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557194"
---
# <a name="schema-attributes-and-descriptions-in-lync-server-2013"></a>Lync Server 2013의 스키마 특성 및 설명

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-06_

이 섹션에서는 Lync Server 2013에서 사용 되는 모든 스키마 특성에 대해 설명 합니다. 특성과 관련 된 클래스의 경우 [Lync Server 2013에서 클래스별 스키마 특성](lync-server-2013-schema-attributes-by-class.md)을 참조 하십시오. Lync Server 2013의 새로운 클래스 및 특성 목록은 [Lync server 2013의 스키마 변경 사항을](lync-server-2013-schema-changes-in-lync-server-2013.md)참조 하세요.

연결 된 쌍의 특성은 정방향 링크 또는 역방향 링크로 지정 됩니다. 다른 개체를 참조 하는 특성은 정방향 링크입니다. 첫 번째 개체를 다시 참조 하는 다른 개체의 특성은 역방향 링크입니다. 정방향 링크는 업데이트할 수 있으며, 역방향 링크는 읽기 전용입니다.

일부 특성에는 비트 마스크 값이 있습니다. 이러한 특성의 경우 각 설정은 비트로 표시 되 고, 표시 되는 10 진수 값은 비트 위치를 나타냅니다. 비트 위치는 비트 0으로 시작 합니다. 예를 들어 1 (이진수)은 비트 0 이며, 1만 (이진수)는 비트 4입니다. 각 비트는 속성을 나타냅니다. 다음은 몇 가지 예입니다.

  - 1만 (이진수)은 10 진수 값 16입니다 (비트 4가 설정 됨).

  - 1억 (이진수)은 10 진수 값 256 (비트 8이 설정 됨)입니다.

  - 1100 (이진수)은 10 진수 값 12입니다 (비트 2 및 3이 설정 되 고 두 비트에 의해 표시 되는 속성은 사용 하도록 설정 됨).

  - 1111000001 (이진수)은 10 진수 값 961 (비트 0, 6, 7, 8 및 9를 설정 하며 이러한 각 비트에 대 한 속성을 사용할 수 있습니다.)

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
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>dnsHostName</p></td>
<td><p>이제 <strong>msrtcsip-gateways</strong> 및 <strong>msrtcsip-gateways</strong> 클래스와 연결 된 Active Directory 도메인 서비스의 기존 특성을 사용 합니다. 이 특성은 풀 또는 모니터링 서버의 FQDN (정규화 된 도메인 이름)을 지정 합니다.</p>
<p>각 세그먼트의 유효한 값은 63 자입니다. 전체 FQDN의 유효한 값은 255 자입니다.</p></td>
<td><p>Microsoft Office Live Communications Server 2005의 새로운 정보</p></td>
</tr>
<tr class="even">
<td><p>Msds-alloweddnssuffixesexadnomk-Msds-sourceobjectdn</p></td>
<td><p>이 특성에는이 개체에 해당 하는 다른 포리스트에 있는 개체의 DN (고유 이름)을 나타내는 문자열이 포함 됩니다. 이 특성은 메일 그룹 확장 및 자동 참석자에 게 사용 됩니다. 이 특성은 Windows Server 2003 r 2에 대 한 기본 Active Directory 스키마에 정의 됩니다.</p>
<p>AD DS를 Windows Server 2003 R2로 업그레이드할 필요가 없도록 Active Directory 스키마 준비는이 특성 정의를 사용 하 여 Windows Server 2003 스키마를 확장 합니다.</p></td>
<td><p>Microsoft Office Communications Server 2007의 새로운 정보</p></td>
</tr>
<tr class="odd">
<td><p>msExchUCVoiceMailSettings</p></td>
<td><p>이 다중 값 특성은 음성 메일 설정을 포함 합니다. 이 특성은 Exchange UM (통합 메시징)과 공유 됩니다.</p></td>
<td><p>Microsoft Lync Server 2010의 새로운 방법</p></td>
</tr>
<tr class="even">
<td><p>msExchUserHoldPolicies</p></td>
<td><p>이 다중값 특성은 사용자에 적용되는 유지 정책의 ID를 보유합니다. 유지 정책은 유지 기간 동안 사용자의 사서함 항목을 보존합니다. 이 특성은 Exchange 2013와 공유 됩니다.</p></td>
<td><p>Lync Server 2013의 새로운 방법</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-AcpInfo</p></td>
<td><p>이 특성은 사용자에 대 한 오디오 회의 공급자 정보를 저장 합니다.</p></td>
<td><p>Lync Server 2010의 새로운 방법</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-ApplicationDestination</p></td>
<td><p>이 특성은 응용 프로그램 대화 상대에 대 한 신뢰할 수 있는 서비스 항목을 가리킵니다.</p></td>
<td><p>Microsoft Office Communications Server 2007 r 2의 새로운 정보</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-ApplicationList</p></td>
<td><p>이 특성은 응용 프로그램 서버에 있는 호스팅된 응용 프로그램의 목록을 포함 합니다.</p></td>
<td><p>Office Communications Server 2007 r 2의 새로운 정보</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-ApplicationOptions</p></td>
<td><p>이 특성은 응용 프로그램 대화 상대에 대 한 옵션을 지정 합니다.</p></td>
<td><p>Office Communications Server 2007 r 2의 새로운 정보</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-ApplicationPrimaryLanguage</p></td>
<td><p>이 특성은 응용 프로그램 대화 상대에 대 한 기본 언어를 포함 합니다.</p></td>
<td><p>Office Communications Server 2007 r 2의 새로운 정보</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-ApplicationSecondaryLanguages</p></td>
<td><p>이 다중 값 특성은 응용 프로그램 대화 상대에 대 한 보조 언어를 포함 합니다.</p></td>
<td><p>Office Communications Server 2007 r 2의 새로운 정보</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-ApplicationServerBL</p></td>
<td><p>이 특성은이 풀에 속한 응용 프로그램 서버 목록을 포함 합니다. 이 역방향 링크에 대 한 해당 정방향 링크 특성은 <strong>msrtcsip-gateways-ApplicationServerPoolLink</strong>입니다.</p></td>
<td><p>Office Communications Server 2007 r 2의 새로운 정보</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-ApplicationServerPoolLink</p></td>
<td><p>이 특성은이 응용 프로그램 서버가 속한 풀을 가리킵니다. 다음은 정방향 연결입니다. 해당 하는 역방향 링크는 <strong>msrtcsip-gateways-ApplicationServerBL</strong>입니다.</p></td>
<td><p>Office Communications Server 2007 r 2의 새로운 정보</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-Msrtcsip-archivedefault (더 이상 사용 되지 않음)</p></td>
<td><p>-</p></td>
<td><p>Live Communications Server 2005의 새로운 정보</p>
<p>Office Communications Server 2007에서 더 이상 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-Msrtcsip-archivedefaultflags (더 이상 사용 되지 않음)</p></td>
<td><p>이 특성은 모든 사용자 통신을 보관 하기 위한 포리스트 경계 내의 전역 기본값을 지정 합니다. 이는 보관 에이전트 계층에 의해 적용 됩니다. 이 특성 값의 범위는 다음과 같습니다.</p>
<ul>
<li><p><strong>TRUE</strong>: 모든 사용자 보관</p></li>
<li><p><strong>FALSE</strong>: 모든 사용자 보관 안 함</p></li>
</ul>
<p>이 특성은 포리스트 경계 내에서 내부 네트워크의 사용자 통신을 보관 하는 방법을 전역적으로 제어 합니다.</p>
<p><strong>Live Communications Server 2005 동작 (현재는 폐기 됨)</strong></p>
<p>이 특성 값의 범위는 다음과 같습니다.</p>
<ul>
<li><p>0: 메시지 본문 보관 [비트 0]</p></li>
<li><p>1: 메시지 본문 보관 안 함 [비트 0]</p></li>
</ul>
<p><strong>Office Communications Server 2007 동작</strong></p>
<p>이 특성 값의 범위는 다음과 같습니다.</p>
<ul>
<li><p>0: ArchiveFederationDefaultWithoutBody (폐기 됨)</p></li>
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
<td><p>Live Communications Server 2005의 새로운 정보</p>
<p>Lync Server 2010에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-Msrtcsip-archivefederationdefault (더 이상 사용 되지 않음)</p></td>
<td><p>-</p></td>
<td><p>Live Communications Server 2005의 새로운 정보</p>
<p>Office Communications Server 2007에서 더 이상 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-Msrtcsip-archivefederationdefaultflags (더 이상 사용 되지 않음)</p></td>
<td><p>-</p></td>
<td><p>Live Communications Server 2005의 새로운 정보</p>
<p>Office Communications Server 2007에서 더 이상 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-ArchivingEnabled</p></td>
<td><p>이 특성은 단일 사용자의 통신을 보관할지 여부를 제어 하기 위해 비트 필드로 사용 되는 정수입니다. 이 컨트롤은 보관 에이전트 계층에 의해 적용 됩니다. 이는 글로벌 카탈로그 복제로 표시 됩니다.</p>
<p>이 특성의 범위는 단일 사용자 또는 연락처에 따라 다릅니다. Lync Server의 유효한 값 및 관련 비트 위치는 다음과 같습니다.</p>
<ul>
<li><p>0: 보관 안 함 (비트 설정 안 함)</p></li>
<li><p>1: 폐기 됨 (비트 위치 0)</p></li>
<li><p>2: 폐기 됨 (비트 위치 1)</p></li>
<li><p>4: 내부 통신 보관 (비트 위치 2)</p></li>
<li><p>8: 페더레이션 통신 보관 (비트 위치 3)</p></li>
</ul>
<p>Live Communications Server 2005의 이전 유효 값은 다음과 같습니다.</p>
<ul>
<li><p>0: <strong>msrtcsip-gateways-msrtcsip-archivedefault</strong> 및 <strong>msrtcsip-gateways-msrtcsip-archivefederation</strong> 에 의해 정의 된 기본값을 다음과 같은 우선 순위에 따라 사용 합니다.</p>
<ul>
<li><p>1: 보관</p></li>
<li><p>2: 보관 안 함</p></li>
<li><p>3: 메시지 본문을 제외 하 고 보관</p></li>
</ul></li>
</ul></td>
<td><p>Live Communications Server 2005의 새로운 정보</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-Msrtcsip-archivingserverdata (더 이상 사용 되지 않음)</p></td>
<td><p>이 특성은 나중에 사용 하도록 예약 되어 있습니다.</p></td>
<td><p>Lync Server 2010에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-Msrtcsip-archivingserverversion (더 이상 사용 되지 않음)</p></td>
<td><p>이 특성은 보관 서비스의 버전을 정의 합니다. 이 특성은 각 공식 제품 릴리스로 증가 하는 monotonously 증가 정수 유형입니다. 가능한 유효한 값은 다음과 같습니다.</p>
<ul>
<li><p>정의 되지 않음: Live Communications Server 2003</p>
<p>                 Live Communications Server 2005</p>
<p>                 Live Communications Server 2005 (SP1)</p></li>
<li><p>3: Office Communications Server 2007</p></li>
<li><p>4: Office Communications Server 2007 R2</p></li>
</ul></td>
<td><p>Office Communications Server 2007의 새로운 정보</p>
<p>Lync Server 2010에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-BackEndServer</p></td>
<td><p>이 특성은 풀 백 엔드 서버의 FQDN을 지정 합니다. 풀 당 하나의 백 엔드 서버만 있을 수 있으므로이는 단일 값 특성입니다.</p>
<p>각 세그먼트의 유효한 값은 63 자입니다. 전체 FQDN의 유효한 값은 255 자입니다.</p></td>
<td><p>Live Communications Server 2005의 새로운 정보</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-ConferenceDirectoryHomePool</p></td>
<td><p>이 특성은 전화 회의 디렉터리를 호스팅하는 풀의 식별자를 포함 합니다.</p></td>
<td><p>Office Communications Server 2007 r 2의 새로운 정보</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-ConferenceDirectoryId</p></td>
<td><p>이 특성은 전화 회의 디렉터리의 식별자를 포함 합니다.</p></td>
<td><p>Office Communications Server 2007 r 2의 새로운 정보</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-ConferenceDirectoryTargetPool</p></td>
<td><p>이 특성은 전화 회의 디렉터리를 이동할 풀의 식별자를 포함 합니다.</p></td>
<td><p>Office Communications Server 2007 r 2의 새로운 정보</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-기본값</p></td>
<td><p>이 부울 특성은 전화 사용이 기본 사용 인지 여부를 정의 합니다. 이 특성을 <strong>TRUE</strong>로 설정 하면 전화 사용량이 기본 사용 이며 관리자가 삭제할 수 없습니다. 이 특성을 <strong>FALSE</strong>로 설정 하면 사용을 삭제할 수 있습니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 정보</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-DefaultCWAExternalURL</p></td>
<td><p>이 특성은 조직 외부의 사용자에 대 한 Communicator Web Access URL을 식별 합니다.</p></td>
<td><p>Office Communications Server 2007 r 2의 새로운 정보</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-DefaultCWAInternalURL</p></td>
<td><p>이 특성은 조직 내에 있는 사용자에 대 한 Communicator Web Access URL을 식별 합니다.</p></td>
<td><p>Office Communications Server 2007 r 2의 새로운 정보</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-DefaultLocationProfileLink (더 이상 사용 되지 않음)</p></td>
<td><p>이 단일 값 특성은 할당 된 위치 프로필 클래스 개체의 DN (고유 이름)을 포함 합니다.</p>
<p>정방향 연결: <strong>연결 ID 11036</strong></p>
<p>해당 하는 역방향 링크는 <strong>msrtcsip-gateways-ServerReferenceBL</strong>입니다.</p></td>
<td><p>Lync Server 2010에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-DefaultPolicy (더 이상 사용 되지 않음)</p></td>
<td><p>이 부울 특성은 정책이 기본 정책 인지 여부를 지정 합니다. 정책이 <strong>TRUE</strong>로 설정 되 면 기본 정책입니다.</p></td>
<td><p>Office Communications Server의 새로운 정보 2007</p>
<p>Lync Server 2010에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-Msrtcsip-defaultroutetoedgeproxy (더 이상 사용 되지 않음)</p></td>
<td><p>이 특성은 액세스에 지 서비스를 실행 하는에 지 서버의 FQDN (직접 액세스할 수 있는 경우) 또는 액세스에 지 서비스를 실행 하는 서버 풀의 하드웨어 부하 분산 장치를 지정 합니다. 액세스에 지 서비스를 실행 하는 서버에 하나 이상의 디렉터를 통해서만 액세스할 수 있으면이 특성은 FQDN을 지정 하 고, 선택적으로 디렉터 또는 디렉터 풀을 처리 하는 하드웨어 부하 분산 장치에 대 한 포트 번호입니다.</p>
<p>각 세그먼트의 유효한 값은 63 자입니다. 전체 FQDN의 유효한 값은 255 자입니다.</p></td>
<td><p>Live Communications Server 2005의 새로운 정보</p>
<p>Lync Server 2010에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-Msrtcsip-defaultroutetoedgeproxyport (더 이상 사용 되지 않음)</p></td>
<td><p>이 특성은 액세스에 지 서비스를 실행 하는 서버에 연결 하는 데 사용 해야 하는 포트 번호를 나타냅니다.</p>
<p>유효한 값은 사용할 포트를 지정 하는 정수 값입니다. 기본값은 5061입니다.</p></td>
<td><p>Live Communications Server 2005의 새로운 정보</p>
<p>Lync Server 2010에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-Msrtcsip-defpresencesubscriptiontimeout (더 이상 사용 되지 않음)</p></td>
<td><p>이 특성은 기본 현재 상태 구독 제한 시간을 나타냅니다.</p></td>
<td><p>Lync Server 2010에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-DefRegistrationTimeout (더 이상 사용 되지 않음)</p></td>
<td><p>이 특성은 기본 등록 시간 제한 창을 나타냅니다.</p></td>
<td><p>Lync Server 2010에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-Msrtcsip-defroamingdatasubscriptiontimeout (더 이상 사용 되지 않음)</p></td>
<td><p>이 특성은 기본 로밍 데이터 구독 제한 시간 기간을 나타냅니다.</p></td>
<td><p>Lync Server 2010에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-DeploymentLocator</p></td>
<td><p>이 특성은 분할 도메인 토폴로지에서 사용 되며 FQDN (정규화 된 도메인 이름)을 포함 합니다.</p></td>
<td><p>Lync Server 2010의 새로운 방법</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-Description (더 이상 사용 되지 않음)</p></td>
<td><p>이 단일 값 유니코드 문자열 특성은 해당 전화 경로 또는 정규화 규칙에 대 한 간단한 설명을 포함 합니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 정보</p>
<p>Lync Server 2010에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-DomainData</p></td>
<td><p>이 특성은 나중에 사용 하도록 예약 되어 있습니다.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-DomainName</p></td>
<td><p>이 특성은 등록자에 대해 구성 된 도메인을 나타냅니다.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-EdgeProxyData</p></td>
<td><p>이 특성은 나중에 사용 하도록 예약 되어 있습니다.</p></td>
<td><p>Live Communications Server 2005의 새로운 정보</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-EdgeProxyFQDN</p></td>
<td><p>이 특성은 액세스에 지 서비스를 실행 하는 서버의 FQDN을 지정 합니다.</p>
<p>각 세그먼트의 유효한 값은 63 자입니다. 전체 FQDN의 유효한 값은 255 자입니다.</p></td>
<td><p>Live Communications Server 2005의 새로운 정보</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-Msrtcsip-enablebesteffortnotify (더 이상 사용 되지 않음)</p></td>
<td><p>이 특성은 클라이언트의 구독 요청에 대 한 응답으로 서버에서 알림 요청 대신 BENOTIFY (최고 작업량 알림) 요청을 생성할지 여부를 제어 합니다. BENOTIFY은 일반 알림 요청 대신 서버가 BENOTIFY 요청을 생성 하는 구독 알림 핸드셰이크에 대 한 성능 향상 확장입니다. 성능상의 이점은 BENOTIFY 요청에는 알림 요청이 수행 하는 대로 클라이언트의 200 정상 응답이 필요 하지 않을 수 있다는 것입니다.</p>
<p>유효한 값은 <strong>TRUE</strong> 또는 <strong>FALSE</strong>입니다.</p>
<div>

> [!NOTE]  
> Live Communications Server 2003에서는 BENOTIFY 요청을 지원 하지 않습니다. Live Communications Server 2005 및 타사 서버에서 실행 되는 Live Communications Server 2003 server API를 사용 하 여 작성 된 서버 응용 프로그램과 상호 운용 되도록 하려면 해당 값을 <STRONG>FALSE</STRONG>로 설정 하 여 BENOTIFY 요청을 사용 하지 않도록 설정할 수 있습니다. BENOTIFY가 현재 IETF (인터넷 엔지니어링 작업 포스) SIP 표준화 프로세스에 포함 되어 있지 않습니다.


</div></td>
<td><p>Live Communications Server 2005의 새로운 정보</p>
<p>Lync Server 2010에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-EnableFederation (더 이상 사용 되지 않음)</p></td>
<td><p>이 특성은 사용자가 다른 조직의 사용자와 통신할 수 있는지 여부를 구성 하는 데 사용 하는 전역 스위치입니다. 이를 통해 관리자가 개별 사용자의 <strong>FederationEnabled</strong> 특성을 덮어쓸 수 있습니다. 이 특성은 회사의 웜, 바이러스 또는 대상이 지정 된 공격으로 인해 내부 네트워크가 인터넷 공격 으로부터 보호 되도록 하는 데 유용할 수 있습니다.</p>
<p>유효한 값 및 관련 비트 위치는 다음과 같습니다.</p>
<ul>
<li><p>1: 공용 IM 연결에 사용 (비트 위치 0)</p></li>
<li><p>2: 예약 됨 (비트 위치 1)</p></li>
<li><p>4: 예약 됨 (비트 위치 2)</p></li>
<li><p>8: 예약 됨 (비트 위치 3)</p></li>
<li><p>16: 원격 통화 제어 사용 [전화 통신] (비트 위치 4)</p></li>
<li><p>64: AllowOrganizeMeetingWithAnonymousParticipants (사용자가 익명 사용자를 모임에 초대 하도록 허용 (비트 위치 6)</p></li>
<li><p>128: 이동 가능 (사용자가 통합 통신을 사용 하도록 설정) (비트 위치 7)</p></li>
<li><p>256: EnabledForEnhancedPresence (사용자가 공용 IM 연결을 사용 하도록 설정) (비트 위치 8)</p></li>
<li><p>512: RemoteCallControlDualMode (비트 위치 9)</p></li>
</ul></td>
<td><p>Live Communications Server 2005의 새로운 정보</p>
<p>Lync Server 2010에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-EnterpriseServices</p></td>
<td><p>이 특성은 엔터프라이즈 서비스가 지정 된 서버에 로드 되는지 여부를 나타냅니다.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-ExtensionData</p></td>
<td><p>이 특성은 나중에 사용 하도록 예약 되어 있습니다.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-ExternalAccessCode</p></td>
<td><p>이 특성은 외부 액세스에 대 한 전화 걸기 코드를 포함 합니다.</p></td>
<td><p>Office Communications Server 2007 r 2의 새로운 정보</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-FederationEnabled</p></td>
<td><p>이 특성은 단일 사용자가 페더레이션을 사용할 수 있는지 여부를 제어 합니다. 엔터프라이즈 서비스 계층에 의해 적용 됩니다. 이는 글로벌 카탈로그 복제로 표시 됩니다.</p>
<p>유효한 값은 <strong>TRUE</strong> 또는 <strong>FALSE</strong>입니다.</p></td>
<td><p>Live Communications Server 2005의 새로운 정보</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-Msrtcsip-frontendservers</p></td>
<td><p>이 특성은 풀과 연결 된 모든 Enterprise Edition 서버의 도메인 이름으로 이루어진 다중 값 목록입니다.</p>
<p>역방향 연결: <strong>연결 ID 11023</strong></p>
<p>이 역방향 링크에 해당 하는 정방향 링크는 <strong>msrtcsip-gateways-PoolAddress</strong>입니다.</p></td>
<td><p>Live Communications Server 2005의 새로운 정보</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-게이트웨이 (더 이상 사용 되지 않음)</p></td>
<td><p>이 다중 값 문자열 특성에는 게이트웨이 및 포트 목록이 포함 되어 있습니다.</p></td>
<td><p>Lync Server 2010에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-GlobalSettingsData (더 이상 사용 되지 않음)</p></td>
<td><p>이 특성은 이름: 값 쌍을 저장 합니다. 이미 정의 된 이름: 값 쌍은 <strong>현재 상태에 대 한 폴링 허용</strong> 설정에 대 한 것입니다.</p></td>
<td><p>Lync Server 2010에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-Msrtcsip-groupingid</p></td>
<td><p>이 특성은 주소록 항목을 그룹화 하는 데 사용 되는 그룹의 고유 식별자입니다.</p></td>
<td><p>Lync Server 2010의 새로운 방법</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-Msrtcsip-homeserver (더 이상 사용 되지 않음)</p></td>
<td><p>-</p></td>
<td><p>Live Communications Server에서 새로 만들기 2003 (사용 되지 않음)</p>
<p>Live Communications Server 2005에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-Msrtcsip-homeserverstring (더 이상 사용 되지 않음)</p></td>
<td><p>-</p></td>
<td><p>Live Communications Server 2003의 새로운 정보</p>
<p>Live Communications Server 2005에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-Msrtcsip-homeusers (더 이상 사용 되지 않음)</p></td>
<td><p>-</p></td>
<td><p>Live Communications Server에서 새로 만들기 2003 (사용 되지 않음)</p>
<p>Live Communications Server 2005에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-InternetAccessEnabled</p></td>
<td><p>이 특성은 외부 사용자 액세스에 대해 단일 사용자를 사용할 수 있는지 여부를 제어 합니다. 엔터프라이즈 서비스 계층에 의해 적용 됩니다. 이는 글로벌 카탈로그 복제로 표시 됩니다.</p>
<p>유효한 값은 <strong>TRUE</strong> 또는 <strong>FALSE</strong>입니다.</p></td>
<td><p>Live Communications Server 2005의 새로운 정보</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-IsMaster (더 이상 사용 되지 않음)</p></td>
<td><p>-</p></td>
<td><p>Live Communications Server 2003의 새로운 새</p>
<p>Live Communications Server 2005에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-Line</p></td>
<td><p>이 단일 값 특성에는 Lync에서 전화 통신에 사용 하는 장치 ID (사용자 컨트롤에 해당 하는 통화 URI 또는 SIP URI)가 포함 됩니다. 이 특성은 글로벌 카탈로그 복제를 위해 표시 되며 인덱싱되어 있습니다. 사용자가 Enterprise Voice를 사용할 수 있도록 설정 되어 있으면이 특성은 사용자의 전화 번호를 사용 하 여 전자 164 개의 정규화 된 버전을 저장 합니다.</p></td>
<td><p>Microsoft Office Live Communications Server 2005 SP1의 새로운 정보</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-LineServer</p></td>
<td><p>이 단일 값 특성은 CSTA-SIP 게이트웨이 서버의 SIP URI를 포함 합니다. 이 특성은 글로벌 카탈로그 복제를 위해 표시 되지만 인덱싱되지 않습니다.</p></td>
<td><p>Microsoft Office Live Communications Server 2005 SP1의 새로운 정보</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-Msrtcsip-localnormalizationdata (더 이상 사용 되지 않음)</p></td>
<td><p>이 특성은 나중에 사용 하도록 예약 되어 있습니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 정보</p>
<p>Lync Server 2010에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-Msrtcsip-localnormalizationlinks (더 이상 사용 되지 않음)</p></td>
<td><p>이 다중 값 특성은이 위치 프로필에 연결 된 로컬 정규화 DN (고유 이름) 목록을 포함 합니다. 이 특성의 형식은 DN 이진입니다. 위치 프로필과 로컬 정규화 규칙 사이에는 일대다 관계가 있습니다. 로컬 정규화 DNs 목록의 순서는 관리자가 지정한 순서 대로 유지 관리 해야 합니다. 순서 보존은 주문 인덱스를 지정 하는 DN 이진의 이진 부분에 의해 유지 관리 됩니다.</p>
<p>정방향 연결: <strong>연결 ID 11034</strong></p>
<p>이 정방향 연결 특성에 해당 하는 역방향 링크는 <strong>msrtcsip-gateways-LocationProfileBL</strong>입니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 정보</p>
<p>Lync Server 2010에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-LocalNormalizationOptions</p></td>
<td><p>이 특성은 정규화 규칙에 대 한 옵션 목록을 포함 합니다.</p></td>
<td><p>Office Communications Server 2007 r 2의 새로운 정보</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-LocationName (사용 되지 않음)</p></td>
<td><p>이 단일 값 특성은이 프로필이 나타내는 위치를 나타내는 위치 프로필의 이름을 포함 합니다. 위치 프로필이 여러 개 있을 수 있으므로 관리자는 서로 다른 프로필을 구분 하는 방법이 필요 합니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 정보</p>
<p>Lync Server 2010에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-locationProfileBL (더 이상 사용 되지 않음)</p></td>
<td><p>이 다중 값 특성은 위치 프로필 고유 이름의 목록을 포함 합니다. 이 특성은 하나 이상의 위치 프로필에 대 한 역방향 연결을 지정 합니다.</p>
<p>역방향 연결: <strong>연결 ID 11035</strong></p>
<p>이 특성은 정방향 연결 <strong>msrtcsip-gateways-msrtcsip-localnormalizationlinks</strong>에 해당 합니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 정보</p>
<p>Lync Server 2010에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-LocationProfileData (더 이상 사용 되지 않음)</p></td>
<td><p>이 특성은 나중에 사용 하도록 예약 되어 있습니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 정보</p>
<p>Lync Server 2010에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-LocationProfileOptions</p></td>
<td><p>이 특성은 위치 프로필에 대 한 옵션을 포함 합니다.</p></td>
<td><p>Office Communications Server 2007 r 2의 새로운 정보</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-MappingContact</p></td>
<td><p>이 다중 값 특성은 응용 프로그램 대화 상대 목록을 포함 합니다.</p></td>
<td><p>Office Communications Server 2007 r 2의 새로운 정보</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-MappingLocation</p></td>
<td><p>이 다중 값 특성은 위치 프로필의 목록을 포함 합니다.</p></td>
<td><p>Office Communications Server 2007 r 2의 새로운 정보</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-Msrtcsip-maxnumoutstandingsearchperserver (더 이상 사용 되지 않음)</p></td>
<td><p>이 특성은 서버당 해결 되지 않은 최대 검색 요청 수를 나타냅니다.</p></td>
<td><p>Lync Server 2010에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-MaxNumSubscriptionsPerUser (더 이상 사용 되지 않음)</p></td>
<td><p>이 특성은 사용자 당 최대 구독 수를 나타냅니다.</p></td>
<td><p>Lync Server 2010에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-Msrtcsip-maxpresencesubscriptiontimeout (더 이상 사용 되지 않음)</p></td>
<td><p>이 특성은 최대 구독 제한 시간 기간을 나타냅니다.</p></td>
<td><p>Lync Server 2010에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-Msrtcsip-maxregistrationstimeout (더 이상 사용 되지 않음)</p></td>
<td><p>이 특성은 최대 등록 시간 제한 기간을 나타냅니다.</p></td>
<td><p>Lync Server 2010에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-Msrtcsip-maxroamingdatasubscriptiontimeout (더 이상 사용 되지 않음)</p></td>
<td><p>이 특성은 최대 로밍 데이터 구독 제한 시간 기간을 나타냅니다.</p></td>
<td><p>Lync Server 2010에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-MCUData</p></td>
<td><p>이 특성은 나중에 사용 하도록 예약 되어 있습니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 정보</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-Msrtcsip-mcufactoryaddress</p></td>
<td><p>이 특성은이 특성이 속한 MCU (multipoint control unit) 팩터리에서 돌아가는 링크를 지정 하는 컴퓨터 클래스 아래에 있는 서비스 제어 지점 특성입니다. 이 서비스 제어 지점 및 특성은 모든 Microsoft MCU에 대해 만들어집니다. 각 Microsoft MCU는 해당 그룹에서 풀 수준 설정을 검색 하기 위해 해당 서버가 속해 있는 풀의 백 엔드 서버를 찾아야 합니다.</p>
<p>이 특성의 값은 MCU 팩터리의 DN (고유 이름)입니다. 이는 단일 값 특성이 며 글로벌 카탈로그 복제로 표시 됩니다.</p>
<p>정방향 연결: <strong>연결 ID 11026</strong></p>
<p>이 정방향 연결 특성에 해당 하는 역방향 링크는 <strong>msrtcsip-gateways-msrtcsip-mcuservers</strong>입니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 정보</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-MCUFactoryData</p></td>
<td><p>이는 다중 문자열 예약 특성입니다. 이 특성에 저장 된 설정은 이름 = 값 쌍으로 표현 됩니다. 현재 정의 된 이름 = 값 쌍은 다음과 같습니다.</p>
<ul>
<li><p>FactoryURL = &lt; URL&gt;</p></li>
</ul></td>
<td><p>Office Communications Server 2007의 새로운 정보</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-Msrtcsip-mcufactorypath</p></td>
<td><p>풀과 연결 된 단일 MCU 팩터리의 DN (고유 이름)을 포함 하는 단일 값 특성입니다.</p>
<p>정방향 연결: <strong>연결 ID 11024</strong></p>
<p>이 정방향 연결 특성에 해당 하는 역방향 링크는 <strong>msrtcsip-gateways-PoolAddresses</strong>입니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 정보</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-MCUFactoryProviderID</p></td>
<td><p>이 특성은 MCU 팩터리 provider의 GUID를 지정 하는 단일 값 문자열입니다. GUID 값을 기반으로 하 여 MCU 팩터리 프로세스는이 MCU 유형을 처리할 것인지 여부를 결정 합니다. GUID 값이 <strong>{F0810510-424F-46ef-84FE-6CC720DF1791}</strong>인 경우에는 MCU 팩터리 프로세스 (Lync Server에서 기본적으로 사용 가능)가 처리 됩니다. 다른 GUID 값의 경우 MCU 팩터리 프로세스는 MCU 형식을 지원 하지 않습니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 정보</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-Msrtcsip-mcuservers</p></td>
<td><p>이 특성은 다중 값의 DN (고유 이름) 목록입니다. 이 특성은이 MCU 팩터리에 연결 된 것과 동일한 유형 및 공급 업체의 모든 MCU 서버 목록을 포함 합니다. 각 세그먼트의 유효한 값은 63 자입니다. 전체 FQDN의 유효한 값은 255 자입니다.</p>
<p>역방향 연결: 연결 ID 11027</p>
<p>이 역방향 링크에 해당 하는 정방향 링크는 <strong>msrtcsip-gateways-msrtcsip-mcufactoryaddress</strong>입니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 정보</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-M가공선</p></td>
<td><p>이 특성은 MCU가 처리할 수 있는 미디어를 지정 하는 단일 값 문자열입니다.</p>
<p>지원 되는 유효한 유형은 다음과 같습니다.</p>
<ul>
<li><p>모임</p></li>
<li><p>오디오-비디오</p></li>
<li><p>채팅</p></li>
<li><p>전화 회의</p></li>
</ul></td>
<td><p>Office Communications Server 2007의 새로운 정보</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-M가는 공급 업체</p></td>
<td><p>이 특성은 MCU 공급 업체의 이름을 지정 하는 단일 값 문자열입니다. 모든 Microsoft MCUs는이 특성을 <strong>Microsoft Corporation</strong>으로 지정 합니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 정보</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-Msrtcsip-meetingflags (더 이상 사용 되지 않음)</p></td>
<td><p>이 특성은 모든 사용자 또는 연락처 개체에 대해 전역적으로 사용 하도록 설정 되는 다양 한 모임 옵션을 정의 합니다. 이 특성은 정수 형식의 비트 마스크 값입니다.</p>
<p>유효한 값 및 관련 비트 위치는 다음과 같습니다.</p>
<ul>
<li><p>0: AllowOrganizeMeetingWithAnonymousParticipants가 None (사용자가 익명 사용자를 모임에 초대 하도록 허용 하지 않음) (비트 설정 안 함)</p></li>
<li><p>4: AllowOrganizeMeetingWithAnonymousParticipants는 모든 사용자 (익명 사용자를 모임에 초대 하도록 허용) 모든 사람 (비트 위치 2)</p></li>
<li><p>8: AllowOrganizeMeetingWithAnonymousParticipants은 UsePerUserSetting (사용자가 사용자별 설정에 따라 익명 사용자를 모임에 초대 하도록 허용) (비트 위치 3)</p></li>
<li><p>16: UserPerUserMeetingPolicy (사용자별로 모임 정책 정의) (비트 위치 4)</p></li>
</ul></td>
<td><p>Office Communications Server 2007의 새로운 정보</p>
<p>Lync Server 2010에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-Microsoft.rtc.management.writableconfig.policy.meeting.meetingpolicy (더 이상 사용 되지 않음)</p></td>
<td><p>이 특성은 관리자가이 사용자에 대해 단일 값 특성으로 할당 한 정책의 DN (고유 이름)을 지정 합니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 정보</p>
<p>Lync Server 2010에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-Msrtcsip-minpresencesubscriptiontimeout (더 이상 사용 되지 않음)</p></td>
<td><p>이 특성은 최소 현재 상태 구독 제한 시간 범위를 나타냅니다.</p></td>
<td><p>Lync Server 2010에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-MinRegistrationTimeout (더 이상 사용 되지 않음)</p></td>
<td><p>이 특성은 최소 등록 제한 시간 기간을 나타냅니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 정보</p>
<p>Lync Server 2010에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-Msrtcsip-minroamingdatasubscriptiontimeout (더 이상 사용 되지 않음)</p></td>
<td><p>이 특성은 최소 로밍 데이터 구독 제한 시간 기간을 나타냅니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 정보</p>
<p>Lync Server 2010에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-MirrorBackEndServer</p></td>
<td><p>이 특성은 프런트 엔드 풀에서 사용 하는 미러링된 SQL Server 백 엔드를 저장 하는 데 사용 됩니다.</p></td>
<td><p>Lync Server 2013의 새로운 방법</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-MobilityFlags</p></td>
<td><p>이 특성은 이동성 설정을 정의 하는 옵션과 플래그를 포함 합니다.</p></td>
<td><p>Office Communications Server 2007 r 2의 새로운 정보</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-MobilityPolicy</p></td>
<td><p>이 특성은 모바일 정책 개체의 DN을 포함 합니다.</p></td>
<td><p>Office Communications Server 2007 r 2의 새로운 정보</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-Msrtcsip-numdevicesperuser (더 이상 사용 되지 않음)</p></td>
<td><p>이 특성은 사용자가 SIP 통신에 등록 하 고 현재 상태를 구독 하는 데 사용할 수 있는 장치 수를 나타냅니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 정보</p>
<p>Lync Server 2010에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways 플래그</p></td>
<td><p>이 특성은 user 또는 contact 개체에 대해 사용 되는 옵션을 지정 합니다. 이 특성은 integer 형식의 비트 마스크 값입니다. 각 옵션은 비트로 표시 됩니다. 이 특성은 글로벌 카탈로그 복제로 표시 됩니다.</p>
<p>유효한 값 및 관련 비트 위치는 다음과 같습니다.</p>
<ul>
<li><p>1: 공용 IM (인스턴트 메시징) 연결을 사용 하도록 설정 (비트 위치 0)</p></li>
<li><p>2: 예약 됨 (비트 위치 1)</p></li>
<li><p>4: 예약 됨 (비트 위치 2)</p></li>
<li><p>8: 예약 됨 (비트 위치 3)</p></li>
<li><p>16: 원격 통화 제어 사용 [전화 통신] (비트 위치 4)</p></li>
<li><p>64: AllowOrganizeMeetingWithAnonymousParticipants (사용자가 익명 사용자를 모임에 초대 하도록 허용 (비트 위치 6)</p></li>
<li><p>128: 작업 중 (사용자가 UC를 사용 하도록 설정) (비트 위치 7)</p></li>
<li><p>256: EnabledForEnhancedPresence (사용자가 공용 IM 연결을 사용 하도록 설정) (비트 위치 8)</p></li>
<li><p>512: RemoteCallControlDualMode (비트 위치 9)</p></li>
</ul></td>
<td><p>Live Communications Server 2005 SP1의 새로운 정보</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-OriginatorSID</p></td>
<td><p>이 특성은 Windows NT Server 보안 주체 계정에서 사용자의 ObjectSID를 리소스 또는 중앙 포리스트의 해당 사용자 또는 연락처 개체의이 특성으로 복사할 때 single sign-on을 사용 하도록 설정 하는 데 사용 됩니다. Communicator Web Access는이 특성 또는 사용자의 ObjectSID를 사용 하 여 AD DS에서 사용자를 검색 합니다. 이 특성은 글로벌 카탈로그 복제로 표시 됩니다.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways Urn</p></td>
<td><p>이 특성은 응용 프로그램 대화 상대 소유자의 URN (Uniform Resource Name)입니다.</p></td>
<td><p>Lync Server 2010의 새로운 방법</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-Pattern (더 이상 사용 되지 않음)</p></td>
<td><p>이 단일 값 문자열 특성은 다이얼 번호를 전자 164 형식으로 일치 시키는 데 사용 되는 패턴을 포함 합니다. 전화 번호가이 패턴과 일치 하면 번역은 전화 건 번호에 적용 됩니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 정보</p>
<p>Lync Server 2010에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-Msrtcsip-phoneroutebl (더 이상 사용 되지 않음)</p></td>
<td><p>이 다중 값 특성은 전화 경로 DN (고유 이름) 목록을 포함 합니다. 이 특성은 하나 이상의 전화 경로에 대 한 역방향 연결을 지정 합니다.</p>
<p>역방향 연결: <strong>연결 ID 11033</strong></p>
<p>이 특성은 정방향 연결 <strong>msrtcsip-gateways-msrtcsip-routeusagelinks</strong>에 해당 합니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 정보</p>
<p>Lync Server 2010에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-Msrtcsip-phoneroutedata (더 이상 사용 되지 않음)</p></td>
<td><p>이 특성은 나중에 사용 하도록 예약 되어 있습니다.</p></td>
<td><p>Lync Server 2010에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-Msrtcsip-phoneroutename (더 이상 사용 되지 않음)</p></td>
<td><p>이 단일 값 유니코드 문자열 특성은 관리자가 쉽게 참조할 수 있도록 전화 경로의 식별 이름을 지정 합니다.</p></td>
<td><p>Lync Server 2010에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-Msrtcsip-phoneusagedata (더 이상 사용 되지 않음)</p></td>
<td><p>이 특성은 나중에 사용 하도록 예약 되어 있습니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 정보</p>
<p>Lync Server 2010에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-PolicyContent (더 이상 사용 되지 않음)</p></td>
<td><p>이 특성은 단일 값 유니코드 문자열입니다. 이 string 특성은 XML 형식의 정책 정의를 포함 합니다. XML 스키마 정의는 여러 가지 정책 유형에 따라 공통적으로 설정 되며 각 정책 유형에 대 한 설정만 다릅니다.</p>
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
<td><p>Office Communications Server 2007의 새로운 정보</p>
<p>Lync Server 2010에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-PolicyData (더 이상 사용 되지 않음)</p></td>
<td><p>이 특성은 나중에 사용 하도록 예약 되어 있습니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 정보</p>
<p>Lync Server 2010에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-Msrtcsip-policytype (더 이상 사용 되지 않음)</p></td>
<td><p>이 단일 값 유니코드 문자열 특성에는 정책 유형이 포함 됩니다. 유효한 정책 유형은 다음과 같습니다.</p>
<ul>
<li><p>모임</p></li>
<li><p>통신과</p></li>
</ul></td>
<td><p>Office Communications Server 2007의 새로운 정보</p>
<p>Lync Server 2010에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-PoolAddress</p></td>
<td><p>이 특성은 컴퓨터가 속한 풀로 돌아가는 링크를 지정 합니다. 이 특성은 컴퓨터에서 Lync Server의 Standard Edition 또는 Enterprise Edition을 실행 하 고 있는지 여부에 관계 없이 설정 됩니다. 이 특성은 글로벌 카탈로그 복제로 표시 됩니다.</p>
<p>유효한 값은 풀의 도메인 이름입니다.</p>
<p>정방향 연결: <strong>연결 ID 11022</strong></p>
<p>이 정방향 연결 특성에 해당 하는 역방향 링크는 <strong>msrtcsip-gateways-msrtcsip-frontendservers</strong>입니다.</p></td>
<td><p>Live Communications Server 2005의 새로운 정보</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-PoolAddresses</p></td>
<td><p>이 속성은 MCU 팩터리가 연결 된 풀의 DN (고유 이름) 목록을 포함 하는 다중 값 특성입니다.</p>
<p>역방향 연결: <strong>연결 ID 11025</strong></p>
<p>이 역방향 링크에 해당 하는 정방향 링크는 <strong>msrtcsip-gateways-msrtcsip-mcufactorypath</strong>입니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 정보</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-PoolData</p></td>
<td><p>이 특성은 나중에 사용 하도록 예약 되어 있습니다.</p></td>
<td><p>Live Communications Server 2005 SP1의 새로운 정보</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-PoolDisplayName</p></td>
<td><p>이 특성은 관리 콘솔에 표시 되는 풀의 임의 이름을 지정 합니다. 이 이름은 관리자가 변경할 수 있습니다.</p>
<p>유효한 값은 풀의 이름을 나타내는 문자열입니다.</p></td>
<td><p>Live Communications Server 2005의 새로운 정보</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-PoolDomainFQDN</p></td>
<td><p>이 특성은 단일 값 문자열입니다. 이 특성의 값이 있으면 관리자가 프런트 엔드 풀을 만든 Active Directory 도메인 구조를 따르지 않는 프런트 엔드 풀 (예: DNS (Domain Name System) 네임 스페이스에 있는 SIP 네임 스페이스)을 만들려는 경우 해당 풀의 도메인 FQDN을 나타냅니다.</p>
<p>프런트 엔드 풀 도메인 FQDN을 해당 풀이 상주 하는 Active Directory 도메인으로 도메인 이름 부분에 매핑하는 것이 좋습니다. 따라서이 특성에 값이 없는 경우에는 <strong>dnsHostName</strong> 특성으로 표시 되는 대로 프런트 엔드 풀 FQDN이 Active Directory 도메인 이름 구조를 기본값으로 합니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 정보</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-PoolFunctionality</p></td>
<td><p>풀과 연결 된 모든 Lync Server Enterprise Edition server의 도메인 이름에 대 한 다중값 목록입니다. 정수 형식의이 특성은 풀에서 IM (인스턴트 메시징) 및 현재 상태, 회의를 수행할 수 있는지 여부를 정의 합니다.</p>
<p>사용할 수 있는 유효한 값 유형은 다음과 같습니다.</p>
<ul>
<li><p>정의 되지 않음: IM 및 현재 상태 서비스 (Live Communications Server 2005 및 2003)</p></li>
<li><p>1: IM 및 현재 상태 서비스 (Lync Server)</p></li>
<li><p>2: IM 및 현재 상태 및 모임 서비스 (Lync Server)</p></li>
</ul></td>
<td><p>Office Communications Server 2007의 새로운 정보</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-PoolType</p></td>
<td><p>이 특성은 서버 풀이 Standard Edition server 또는 Enterprise Edition server를 실행 하 고 있는지 여부를 지정 합니다. 이 특성은 integer 형식의 비트 마스크 값입니다. 각 옵션은 비트로 표시 됩니다.</p>
<p>유효한 값 및 관련 비트 위치는 다음과 같습니다.</p>
<ul>
<li><p>1: Standard Edition server, 사용자 호스트 (비트 위치 0)</p></li>
<li><p>2: Enterprise Edition server, 사용자 호스트 (비트 위치 1)</p></li>
<li><p>4: Standard Edition server, 응용 프로그램 호스트 (비트 위치 2)</p></li>
<li><p>8: Enterprise Edition server, 응용 프로그램 호스트 (비트 위치 3)</p></li>
</ul>
<p>Lync Server에서는 응용 프로그램만 호스트 되는 풀을 지원 하지 않으므로 유효한 값은 다음과 같습니다.</p>
<ul>
<li><p>5: Standard Edition server, 사용자 및 응용 프로그램 호스트 (비트 위치 0 및 2)</p></li>
<li><p>10: Enterprise Edition server, 사용자 및 응용 프로그램 호스트 (비트 위치 1 및 3)</p></li>
</ul></td>
<td><p>Live Communications Server 2005의 새로운 정보</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-PoolVersion</p></td>
<td><p>이 특성은 풀 버전을 정의 합니다. 이 형식은 각 주요 제품 릴리스로 증가 되는 정수 형식입니다.</p>
<p>사용할 수 있는 유효한 값 유형은 다음과 같습니다.</p>
<ul>
<li><p>0: Live Communications Server 2003</p></li>
<li><p>1: Live Communications Server 2005</p></li>
<li><p>2: Live Communications Server 2005 SP1</p></li>
<li><p>3: Office Communications Server 2007</p></li>
<li><p>4: Office Communications Server 2007 R2</p></li>
<li><p>5: Lync Server 2010</p></li>
</ul></td>
<td><p>Live Communications Server 2005 (SP1)</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-PresenceFlags</p></td>
<td><p>이 특성은 현재 상태 설정을 정의 하는 옵션과 플래그를 포함 합니다.</p></td>
<td><p>Office Communications Server 2007 r 2의 새로운 정보</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-New-cspresencepolicy는 microsoft.rtc.management.writableconfig.policy.clientversion.clientversionpolicy</p></td>
<td><p>이 특성은 현재 상태 정책 개체에 대 한 DN을 포함 합니다.</p></td>
<td><p>Office Communications Server 2007 r 2의 새로운 정보</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-Msrtcsip-primaryhomeserver</p></td>
<td><p>이 특성을 사용 하면 SIP 메시징에 대해 사용자 또는 연락처를 사용할 수 있습니다. 중앙 포리스트 토폴로지에서는 사용자 개체가 아니라 대화 상대 개체가 SIP를 사용 하기 때문에 연락처 클래스에 추가 됩니다.</p>
<p>유효한 값은 사용자가 홈으로 사용 되는 Standard Edition server 또는 Enterprise Edition 프런트 엔드 풀의 DN입니다.</p></td>
<td><p>Live Communications Server 2005의 새로운 정보</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-Msrtcsip-primaryuseraddress</p></td>
<td><p>이 특성은 지정 된 사용자의 SIP 주소를 포함 합니다.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-PrivateLine</p></td>
<td><p>이 특성은 전용 회선 장치의 장치 ID를 포함 합니다.</p></td>
<td><p>Lync Server 2010의 새로운 방법</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-라우팅할 수 있는</p></td>
<td><p>이 특성은 Lync Server에 해당 GRUU 주소를 사용 하 여이 서비스로 라우팅할 권한이 있는지 여부를 확인 하는 데 사용 되는 부울 특성입니다. 이 값을 <strong>TRUE</strong>로 설정 하면 Lync Server에이 서비스로 라우팅할 수 있는 권한이 부여 됩니다. 이 값을 <strong>FALSE</strong>로 설정 하면 Lync Server에이 서비스로 라우팅할 수 있는 권한이 없습니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 정보</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-Msrtcsip-routeusageattribute (더 이상 사용 되지 않음)</p></td>
<td><p>이 단일 값 유니코드 문자열 특성은 전화 경로의 사용을 정규화 하는 특성을 정의 합니다. 전화 경로 선택은 전화 경로 및 발신자에 게 허용 되는 정책 사용 특성에 따라 두 가지 요소를 기준으로 결정 됩니다. 호출자가 허용 되는 사용 현황과 일치 하는 사용 특성이 포함 된 첫 번째 전화 경로가 선택 됩니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 정보</p>
<p>Lync Server 2010에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-Msrtcsip-routeusagelinks (더 이상 사용 되지 않음)</p></td>
<td><p>이 다중 값 DN (고유 이름) 특성은 경로 사용 고유 이름의 목록을 포함 합니다.</p>
<p>정방향 연결: <strong>연결 ID 11032</strong></p>
<p>이 특성은 해당 역방향 링크 <strong>msrtcsip-gateways-msrtcsip-phoneroutebl</strong>에 대 한 정방향 링크입니다.</p></td>
<td><p>Lync Server 2010에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-RoutingPoolDN</p></td>
<td><p>이 특성은이 MCU 또는 Trusted Service로 주소가 지정 된 모든 SIP 트래픽이 통과 해야 하는 풀을 가리키는 DN을 포함 합니다.</p></td>
<td><p>Office Communications Server 2007 r 2의 새로운 정보</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-Msrtcsip-rulename (더 이상 사용 되지 않음)</p></td>
<td><p>이 단일 값 유니코드 문자열 특성은 관리자가 쉽게 참조할 수 있도록 정규화 규칙의 이름을 지정 합니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 정보</p>
<p>Lync Server 2010에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-SchemaVersion</p></td>
<td><p>이 특성은 조직에 현재 배포 된 스키마 버전을 나타냅니다.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-SearchMaxRequests (더 이상 사용 되지 않음)</p></td>
<td><p>이 특성은 사용자가 Communicator를 사용 하 여 대화 상대를 검색할 때 디렉터리 검색에서 반환 되는 검색 결과의 수를 제한 합니다. 이 특성은 클라이언트에서 제공한 값을 재정의 합니다.</p></td>
<td><p>Lync Server 2010에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-Msrtcsip-searchmaxresults (더 이상 사용 되지 않음)</p></td>
<td><p>이 특성은 반환 되는 검색 요청 수를 제한 합니다.</p></td>
<td><p>Lync Server 2010에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-Msrtcsip-serverbl</p></td>
<td><p>이 다중 값 특성은 DN (고유 이름) 목록을 포함 하는 역방향 링크입니다. 이러한 DNs는 풀이나 <strong>서비스</strong> 개체를 가리킵니다.</p>
<p>이 특성은 정방향 연결 <strong>msrtcsip-gateways-msrtcsip-trustedservicelinks</strong>에 해당 합니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 정보</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways 데이터</p></td>
<td><p>이 특성은 나중에 사용 하도록 예약 되어 있습니다.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-ServerReferenceBL (더 이상 사용 되지 않음)</p></td>
<td><p>이 다중 값 특성은 고유 이름의 목록을 포함 합니다. 이러한 고유 이름은 기본 위치 프로필을 할당할 수 있는 다른 서버 개체를 참조 하는 역방향 링크입니다.</p>
<p>역방향 연결: <strong>연결 ID 11037</strong></p>
<p>이 역방향 링크에 해당 하는 정방향 링크는 <strong>msrtcsip-gateways-DefaultLocationProfileLink</strong>입니다.</p>
<p>이 역방향 링크 특성은 풀 및 중재 서버만 참조 합니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 정보</p>
<p>Lync Server 2010에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-ServerVersion</p></td>
<td><p>이 특성은 서버의 버전 정보를 정의 합니다. 이 버전 번호는 모든 서버 역할에 적용 됩니다. 이 값은 각 공식 제품 릴리스로 증가 하는 monotonously 증가 정수입니다.</p>
<p>가능한 유효한 값은 다음과 같습니다.</p>
<ul>
<li><p>정의 되지 않음: Live Communications Server 2003</p>
<p>                 Live Communications Server 2005</p>
<p>                 Live Communications Server 2005 (SP1)</p></li>
<li><p>3: Office Communications Server 2007</p></li>
<li><p>4: Office Communications Server 2007 R2</p></li>
<li><p>5: Lync Server 2010</p></li>
<li><p>6: Lync Server 2013</p></li>
</ul></td>
<td><p>Office Communications Server 2007의 새로운 정보</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways Objecttype</p></td>
<td><p>정수 형식의이 단일 값 특성은 다음과 같이 <strong>msds-alloweddnssuffixesexadnomk-msds-sourceobjectdn</strong> 가 가리키는 개체의 형식을 지정 합니다.</p>
<ul>
<li><p>null | 0x00000001: 다른 포리스트의 Windows NT Server 보안 주체 사용자 개체를 나타냅니다.</p></li>
<li><p>다음 특성은 메일 그룹 확장에 대 한 다른 포리스트의 그룹 유형을 나타냅니다.</p>
<ul>
<li><p>0x00000002: ADS_GROUP_TYPE_GLOBAL_GROUP</p></li>
<li><p>0x00000004: ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</p></li>
<li><p>0x00000004: ADS_GROUP_TYPE_LOCAL_GROUP</p></li>
<li><p>0x00000008: ADS_GROUP_TYPE_UNIVERSAL_GROUP</p></li>
<li><p>0x80000000: ADS_GROUP_TYPE_SECURITY_ENABLED</p></li>
<li><p>0x90000000: 동일한 포리스트 또는 다른 포리스트의 자동 전화 교환 또는 구독자 액세스 개체를 나타냅니다.</p></li>
</ul></li>
</ul></td>
<td><p>Office Communications Server 2007의 새로운 정보</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-SubscriptionAuthRequired (더 이상 사용 되지 않음)</p></td>
<td><p>-</p></td>
<td><p>Live Communications Server 2003의 새로운 정보</p>
<p>Live Communications Server 2005에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-TargetHomeServer</p></td>
<td><p>이 특성을 사용 하면 사용자 또는 연락처 개체를 Lync Server 풀 하나로 이동할 수 있습니다. 이 특성은 중앙 포리스트 토폴로지에서는 사용자 개체가 아니라 대화 상대 개체가 SIP를 사용 하기 때문에 연락처 클래스에 추가 됩니다.</p>
<p>유효한 값은 사용자가 이동 될 대상 Standard Edition 서버 또는 프런트 엔드 풀의 DN입니다.</p></td>
<td><p>Live Communications Server 2005의 새로운 정보</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-Msrtcsip-targetphonenumber (더 이상 사용 되지 않음)</p></td>
<td><p>이 단일 값 문자열 특성은 <strong>msrtcsip-gateways</strong>에 정의 된 특정 게이트웨이로 라우팅할 전화 번호 패턴이 나 범위를 포함 합니다.</p></td>
<td><p>Lync Server 2010에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-TargetUserPolicies</p></td>
<td><p>이 특성은 Lync Server 사용자의 대상 정책에 대 한 이름-값 쌍을 저장 합니다.</p></td>
<td><p>Lync Server 2010의 새로운 방법</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-TenantId</p></td>
<td><p>이 특성은 테 넌 트의 고유 식별자를 저장 합니다.</p></td>
<td><p>Lync Server 2010의 새로운 방법</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-번역 (더 이상 사용 되지 않음)</p></td>
<td><p>이 특성은 Lync Server의 음성 기능에 사용 되며, 일치 하는 경우 전화 건 번호에 적용할 변환 문자열을 포함 합니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 정보</p>
<p>Lync Server 2010에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways Trustedmdata</p></td>
<td><p>이 특성은 나중에 사용 하도록 예약 되어 있습니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 정보</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-Trustedm된 Fqdn</p></td>
<td><p>이 특성은 MCU의 FQDN을 포함 하는 string 값입니다. 이는 단일 값 특성입니다. 각 세그먼트의 유효한 값은 63 자입니다. 전체 FQDN의 유효한 값은 255 자입니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 정보</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways Proxydata</p></td>
<td><p>이 특성은 나중에 사용 하도록 예약 되어 있습니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 정보</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways에 대 한 Proxyfqdn</p></td>
<td><p>이 특성은 프록시 서버를 실행 하는 서버의 FQDN을 포함 하는 string 값입니다. 이 특성은 단일 값을 가집니다. 각 세그먼트의 유효한 값은 63 자입니다. 전체 FQDN의 유효한 값은 255 자입니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 정보</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways Serverdata</p></td>
<td><p>이 특성은 나중에 사용 하도록 예약 되어 있습니다.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways 서버 Fqdn</p></td>
<td><p>이 특성은 트러스트 된 서버의 FQDN을 나타내는 단일 값 특성입니다.</p></td>
<td><p>Live Communications Server 2005의 새로운 정보</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways Serverversion</p></td>
<td><p>이 특성은 트러스트 된 서버 목록에 있는 서버의 버전 번호를 지정 합니다.</p>
<p>가능한 유효한 값은 다음과 같습니다.</p>
<ul>
<li><p>NULL: Live Communications Server 2003</p></li>
<li><p>2: Live Communications Server 2005</p></li>
<li><p>3: Office Communications Server 2007</p></li>
<li><p>4: Office Communications Server 2007 R2</p></li>
<li><p>5: Lync Server 2010</p></li>
<li><p>6: Lync Server 2013</p></li>
</ul></td>
<td><p>Live Communications Server 2005의 새로운 정보</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways를 사용 하는 Serviceflags</p></td>
<td><p>이 특성은 트러스트 된 서비스에 대해 사용할 수 있는 옵션을 정의 합니다.</p></td>
<td><p>Office Communications Server 2007 r 2의 새로운 정보</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-Msrtcsip-trustedservicelinks</p></td>
<td><p>이 다중 값 특성은 미디어 릴레이 인증 서비스와 같은 트러스트 된 서비스 개체를 참조 하는 DN (고유 이름) 목록을 포함 합니다. 원격 사용자에 대 한 오디오 시나리오를 지원 하려면 미디어 릴레이 인증 서비스 (A/V 회의 서비스를 실행 하는에 지 서버에서 실제로 배치 된)가 풀과 연결 되어 있어야 합니다.</p>
<p>이 정방향 연결 특성에 해당 하는 역방향 링크는 <strong>msrtcsip-gateways-msrtcsip-serverbl</strong>입니다.</p></td>
<td><p>UC</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways를 사용 하는 Serviceport</p></td>
<td><p>이 특성은이 GRUU 서비스에 연결 하는 데 사용 되는 포트 번호를 정의 하는 정수입니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 정보</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways를 사용 하는 Servicetype</p></td>
<td><p>이 특성은이 특성이 나타내는 GRUU 서비스의 유형을 정의 하는 문자열 값입니다.</p>
<p>유효한 GRUU 서비스 유형은 다음과 같습니다.</p>
<ul>
<li><p>MediationServer</p></li>
<li><p>게이트웨이</p></li>
<li><p>MRAS (미디어 릴레이 인증 서비스)</p></li>
<li><p>QoSM</p></li>
<li><p>Msrtcsip-gateways UserExtension NM-CWA-NO-VERSION</p></li>
</ul></td>
<td><p>Office Communications Server 2007의 새로운 정보</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-TrustedWebComponentsServerData</p></td>
<td><p>이 특성은 나중에 사용 하도록 예약 되어 있습니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 정보</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-TrustedWebComponentsServerFQDN</p></td>
<td><p>이 특성은 Lync Server 웹 서비스를 실행 하는 IIS의 FQDN을 포함 하는 string 값입니다. 이는 단일 값 특성입니다. 각 세그먼트의 유효한 값은 63 자입니다. 전체 FQDN의 유효한 값은 255 자입니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 정보</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways 플래그 (더 이상 사용 되지 않음)</p></td>
<td><p>이 특성은 모든 사용자 또는 연락처 개체에 대해 전역적으로 사용 하도록 설정 되는 다양 한 UC 옵션을 정의 합니다. 이 특성은 정수 형식의 비트 마스크 값입니다. 각 옵션은 비트가 있다고 표시 됩니다.</p>
<p>사용할 수 있는 유효한 값 및 관련 비트 위치는 다음과 같습니다.</p>
<ul>
<li><p>4: Useperuser작업 정책 (비트 위치 2)</p></li>
</ul>
<p>이 비트가 설정 되 면 사용자 당 UC 정책이 정의 됩니다.</p></td>
<td><p>Lync Server 2010에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways 정책 (더 이상 사용 되지 않음)</p></td>
<td><p>이 단일 값 특성은 관리자가이 사용자에 대해 할당 한 UC 정책의 DN (고유 이름)을 포함 합니다.</p></td>
<td><p>Lync Server 2010에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways UserDomainList (사용 되지 않음)</p></td>
<td><p>이 특성은 포리스트에서 SIP 사용 가능 사용자를 호스팅하는 모든 도메인의 목록을 제공 합니다. 기본값은 포리스트에 있는 모든 도메인이 SIP를 사용할 수 있음을 나타내는 빈 목록입니다.</p>
<p>유효한 값은 개별 도메인의 도메인 이름을 나타내는 여러 개의 문자열입니다.</p></td>
<td><p>Live Communications Server 2005의 새로운 정보</p>
<p>Lync Server 2010에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-UserEnabled</p></td>
<td><p>이 특성은 사용자가 현재 Lync Server를 사용 하도록 설정 되어 있는지 여부를 결정 합니다.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-UserExtension</p></td>
<td><p>이 다중 값 특성에는 name = 값 형식의 이름-값 쌍 목록이 들어 있습니다 &quot; . &quot; 이 특성은 글로벌 카탈로그 복제로 표시 됩니다.</p></td>
<td><p>Live Communications Server 2005 SP1의 새로운 정보</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-UserLocationProfile</p></td>
<td><p>이 특성은 위치 프로필 개체를 가리키는 DN (고유 이름)을 포함 합니다.</p></td>
<td><p>Office Communications Server 2007 r 2의 새로운 정보</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-UserPolicies</p></td>
<td><p>이 특성은 사용자 정책의 이름-값 쌍을 저장 합니다.</p></td>
<td><p>Lync Server 2010의 새로운 방법</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-UserPolicy</p></td>
<td><p>이는 서로 다른 형식의 전역 사용자 정책을 가리키는 이진 (DN_WITH_BINARY)의 고유 이름 목록을 포함 하는 다중 값 특성입니다. 이진 부분은 DN 부분이 가리키는 정책의 형식을 나타냅니다.</p>
<p>유효한 이진 값은 다음과 같습니다.</p>
<ul>
<li><p>0x00000001: 모임 정책</p></li>
<li><p>0x00000002: UC 정책</p></li>
<li><p>0x00000005: 현재 상태 정책</p></li>
</ul></td>
<td><p>Office Communications Server 2007의 새로운 정보</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-UserRoutingGroupId</p></td>
<td><p>이는 SIP 라우팅 그룹 ID입니다. 동일한 그룹의 사용자는 동일한 프런트 엔드 서버에 등록됩니다.</p></td>
<td><p>Lync Server 2013의 새로운 방법</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-WebComponentsData</p></td>
<td><p>다중값 특성입니다. 이 특성은 나중에 사용 하도록 예약 되어 있습니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 정보</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-Msrtcsip-webcomponentspooladdress</p></td>
<td><p>이 단일 값 특성은 웹 구성 요소가 속하는 풀 또는 Standard Edition server를 가리킵니다.</p>
<p>정방향 연결: <strong>연결 ID 11028</strong></p>
<p>이 정방향 연결 특성에 해당 하는 역방향 링크는 <strong>msrtcsip-gateways-msrtcsip-webcomponentsservers</strong>입니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 정보</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-Msrtcsip-webcomponentsservers</p></td>
<td><p>이 특성은 여러 개의 값을 갖는 고유 이름의 목록입니다. 이 특성은이 풀과 연결 된 모든 웹 서버 목록을 포함 합니다.</p>
<p>역방향 연결: <strong>연결 ID 11029</strong></p>
<p>이 역방향 링크에 해당 하는 정방향 링크는 <strong>msrtcsip-gateways-msrtcsip-webcomponentspooladdress</strong>입니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 정보</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-Msrtcsip-wmiinstanceid (더 이상 사용 되지 않음)</p></td>
<td><p>-</p></td>
<td><p>Live Communications Server 2003의 새로운 정보</p>
<p>Live Communications Server 2005에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>OtherIPPhone</p></td>
<td><p>이 기존 Active Directory 특성은 전화 통신에서 전화기의 대체 TCP/IP 주소 목록을 지정 하는 데 사용 됩니다.</p></td>
<td><p>Windows Server 2008 운영 체제의 새로운 기능이 있습니다.</p></td>
</tr>
<tr class="even">
<td><p>PhoneOfficeOther</p></td>
<td><p>이 기존 Active Directory 특성은 통합 메시징 자동 전화 교환 및 구독자 액세스 번호로의 라우팅 호출을 위해 Lync Server의 음성 구성 요소에서 대화 상대 개체만 사용 합니다. 무조건 통화 전달 주소는이 다중 값 특성에 저장 됩니다. 이 계정은 자동 전화 교환 및 구독자 액세스와 관련 하 여 특정 목적을 위해 만들어집니다. 이 계정의 특성은 관리자가 수정할 수 없습니다.</p></td>
<td><p>Windows 2000 운영 체제의 새로운 기능이 있습니다.</p></td>
</tr>
<tr class="odd">
<td><p>ProxyAddresses</p></td>
<td><p>이 기존 Active Directory 다중 값 특성은 Windows 2000에서 도입 된 기본 Active Directory 스키마의 일부입니다. 이 특성은 사용자 전자 메일의 다양 한 X400, X500 및 SMTP 주소를 포함 합니다. Live Communications Server 2003 이상에서는 sip: 태그를 사용 하 여 사용자의 SIP URI가이 목록에 추가 됩니다 &quot; &quot; .</p>
<p>다음 응용 프로그램은이 특성에서 사용자의 SIP URI를 검색 합니다.</p>
<ul>
<li><p>Microsoft Office Outlook 2003 메시징 및 공동 작업 클라이언트</p></li>
<li><p>Microsoft Office SharePoint Server 2007</p></li>
</ul></td>
<td><p>Windows 2000 운영 체제의 새로운 기능이 있습니다.</p></td>
</tr>
<tr class="even">
<td><p>TelephoneNumber</p></td>
<td><p>이 기존 Active Directory 특성은 사용자의 전화 번호를 포함 합니다.</p></td>
<td><p>Windows 2000 운영 체제의 새로운 기능이 있습니다.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

