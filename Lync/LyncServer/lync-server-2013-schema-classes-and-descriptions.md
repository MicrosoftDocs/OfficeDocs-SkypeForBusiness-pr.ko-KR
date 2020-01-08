---
title: 'Lync Server 2013: 스키마 클래스 및 설명'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Schema classes and descriptions
ms:assetid: 7d43b920-ac37-40cc-adfe-be289bda6e9e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398625(v=OCS.15)
ms:contentKeyID: 48184612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 39bd0b3ff3c99e7de731f94eda0d3775ac4bd7cb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985325"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="schema-classes-and-descriptions-in-lync-server-2013"></a>Lync Server 2013의 스키마 클래스 및 설명

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-30_

이 섹션에서는 Lync Server 2013에서 사용 되는 모든 스키마 클래스에 대해 설명 합니다.

<div>

## <a name="schema-classes-and-descriptions"></a>스키마 클래스 및 설명


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>클래스만</th>
<th>설명</th>
<th>메모</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>메일 받는 사람</p></td>
<td><p>Exchange UM (통합 메시징) 전자 메일 받는 사람입니다.</p></td>
<td><p>이 보조 클래스는 Exchange UM과 공유 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationContacts</p></td>
<td><p>이 클래스는 여러 응용 프로그램 대화 상대에 대 한 컨테이너 이며 특성 자체를 포함 하지 않습니다.</p></td>
<td><p>Microsoft Office Communications Server 2007 R2의 새로운 방법입니다.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationServer</p></td>
<td><p>이 클래스는 통합 커뮤니케이션 응용 프로그램 서비스 (c)의 인스턴스에 대 한 서비스 제어 지점의 항목을 보유 합니다.</p></td>
<td><p>Office Communications Server 2007 R2의 새로운 방법</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationServerService</p></td>
<td><p>이 클래스는 특정 풀과 해당 응용 프로그램 서비스의 연결을 제공 합니다.</p></td>
<td><p>통신 서버 2007 R2의 새로운 방법</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationServerSettings</p></td>
<td><p>이 보조 클래스에는 응용 프로그램 서비스의 인스턴스에 대 한 설정을 나타내는 특성이 msRTCSIP-ApplicationServer에 포함 됩니다.</p></td>
<td><p>통신 서버 2007 R2의 새로운 방법</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-보관 (구식)</p></td>
<td><p>이 보조 클래스를 msRTCSIP-GlobalContainer에는 보관에 관련 된 모든 설정이 포함 되어 있습니다.</p></td>
<td><p>Lync Server 2010에서 더 이상 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchivingServer (구식)</p></td>
<td><p>이 클래스는 단일 인스턴트 메시징 보관 서버를 나타냅니다. 이 클래스의 인스턴스는 메신저 대화 서비스가 설치 된 컴퓨터와 같은 인스턴트 메시징 보관 서버로 컴퓨터가 활성화 될 때 만들어집니다.</p></td>
<td><p>Lync Server 2010에서 더 이상 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ConferenceDirectories</p></td>
<td><p>이 클래스는 회의 디렉터리의 여러 인스턴스에 대 한 컨테이너 이며 특성 자체를 포함 하지 않습니다.</p></td>
<td><p>통신 서버 2007 R2의 새로운 방법</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ConferenceDirectory</p></td>
<td><p>이 클래스는 특정 회의 디렉터리에 대 한 설정을 나타내는 특성을 보유 합니다.</p></td>
<td><p>통신 서버 2007 R2의 새로운 방법</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ConnectionPoint</p></td>
<td><p>컴퓨터를 Lync Server를 실행 하는 서버로 지정 하는 SCP (일반 서비스 제어 지점)</p></td>
<td><p>Lync 2010의 새로운 방법.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefaultCWABank</p></td>
<td><p>이 보조 클래스에는 Microsoft Lync Web App 은행에 대 한 설정이 포함 되어 있습니다.</p></td>
<td><p>통신 서버 2007 R2의 새로운 방법</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-도메인</p></td>
<td><p>이 클래스에는 SIP 등록자의 구성 된 도메인을 정의 하는 특성이 포함 됩니다.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EdgeProxy</p></td>
<td><p>이 클래스 컨테이너는 단일 액세스에 지 서비스를 나타냅니다. 경계 네트워크에 액세스에 지 서비스가 배포 되 고 일반적으로 경계 네트워크에서 Active Directory 도메인 서비스 액세스를 허용 하지 않기 때문에 액세스에 지 서비스 인스턴스가 인트라넷의 Active Directory 네트워크에 가입 되어 있지 않습니다. 따라서 Access 프록시는 AD DS에 자동으로 등록 되지 않습니다. 관리자는 AD DS에 각 액세스에 지 서비스 인스턴스의 존재를 수동으로 구성 해야 합니다.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EnterpriseMCUSettings</p></td>
<td><p>MsRTCSIP-MCU에 대 한이 보조 클래스는 회의 서버의 설정을 나타내는 특성을 보유 합니다.</p></td>
<td><p>Microsoft Office 통신 서버 2007의 새로운 방법.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EnterpriseMediationServerSettings</p></td>
<td><p>MsRTCSIP-MediationServer에 대 한이 보조 클래스는 중재 서버의 설정을 나타내는 특성을 보유 합니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 방법.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EnterpriseServerSettings</p></td>
<td><p>MsRTCSIP에 대 한이 보조 클래스는 SIP 서버 설정을 나타내는 특성을 보유 합니다.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-페더레이션</p></td>
<td><p>MsRTCSIP-GlobalContainer에 대 한이 보조 클래스는 페더레이션과 관련 된 모든 설정을 저장 합니다.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-GlobalContainer</p></td>
<td><p>이 클래스에는 Lync Server 배포 전체에 적용 되는 모든 설정이 포함 되어 있습니다.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-GlobalUserPolicy (구식)</p></td>
<td><p>이 클래스는 단일 Office 커뮤니케이션 서버 모임 정책을 나타냅니다.</p></td>
<td><p>Lync Server 2010에서 더 이상 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-GlobalTopologySetting</p></td>
<td><p>로컬 전역 토폴로지 설정 개체입니다.</p></td>
<td><p>Lync Server 2010의 새로운 방법.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-GlobalTopologySettings</p></td>
<td><p>전역 토폴로지 설정 개체를 보관할 컨테이너입니다.</p></td>
<td><p>Lync Server 2010의 새로운 방법.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocalNormalization</p></td>
<td><p>이 클래스는 위치 정규화 규칙의 인스턴스를 나타내는 컨테이너입니다.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Location연락처 매핑</p></td>
<td><p>이 클래스는 회의 수행자 응용 프로그램에서 생성 되며 전화 회의 전화 번호를 지역별로 분류 하는 데 사용 되는 특성을 보유 합니다.</p></td>
<td><p>통신 서버 2007 R2의 새로운 방법</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Location연락처 매핑</p></td>
<td><p>이 클래스는 위치 대화 매핑의 여러 인스턴스에 대 한 컨테이너 이며 특성 자체를 포함 하지 않습니다.</p></td>
<td><p>통신 서버 2007 R2의 새로운 방법</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocationProfile</p></td>
<td><p>이 클래스는 특정 위치 프로필을 나타내는 컨테이너입니다.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocationProfiles (구식)</p></td>
<td><p>이 클래스는 여러 위치 프로필에 대 한 컨테이너 이며 특성 자체를 포함 하지 않습니다.</p></td>
<td><p>Lync Server 2010에서 더 이상 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocalNormalizations (구식)</p></td>
<td><p>이 클래스는 여러 로컬 정규화 규칙에 대 한 컨테이너 이며 특성 자체를 포함 하지 않습니다.</p></td>
<td><p>Lync Server 2010에서 더 이상 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCU</p></td>
<td><p>이 클래스는 단일 회의 서버를 나타냅니다.</p></td>
<td><p>통신 서버 2007의 새로운 방법.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUFactories</p></td>
<td><p>이 클래스는 여러 msRTCSIP MCUFactory 클래스를 보유 하 고 있으며 특성 자체를 포함 하지 않습니다.</p></td>
<td><p>통신 서버 2007의 새로운 방법.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUFactory</p></td>
<td><p>이 클래스는 단일 미디어 형식에 대 한 회의 서버 팩토리를 나타내는 컨테이너입니다. 이 클래스의 인스턴스는이 특정 유형 및 공급 업체에 대 한 첫 번째 회의 서버가 활성화 될 때 만들어집니다.</p></td>
<td><p>통신 서버 2007의 새로운 방법.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUFactoryService</p></td>
<td><p>이 클래스는 특정 풀과 해당 하는 회의 서버 팩터리에 대 한 연결을 제공 합니다.</p></td>
<td><p>통신 서버 2007의 새로운 방법.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MediationServer</p></td>
<td><p>이 클래스는 중재 서버에 대 한 서비스 제어 지점의 항목을 보유 합니다.</p></td>
<td><p>통신 서버 2007의 새로운 방법.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-모임 (구식)</p></td>
<td><p>MsRTCSIP-GlobalContainer에 대 한이 보조 클래스는 구성 가능한 모임 설정을 나타내는 특성을 보유 합니다.</p></td>
<td><p>Lync Server 2010에서 더 이상 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-이동성</p></td>
<td><p>전역 이동성 설정을 저장 하는 컨테이너입니다.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MonitoringServer</p></td>
<td><p>이 클래스에는 단일 모니터링 서버의 설정을 나타내는 특성이 포함 됩니다.</p></td>
<td><p>통신 서버 2007 R2의 새로운 방법</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PhoneRoute (구식)</p></td>
<td><p>이 클래스는 게이트웨이 또는 게이트웨이 집합에 대 한 최소 순위의 경로의 인스턴스를 나타내는 컨테이너입니다. 이 정보는 모든 엔터프라이즈 풀 또는 표준 버전을 실행 하는 서버에서 가장 비용 효율적인 방법으로 PSTN (공개 통신 네트워크)로 나가는 호출을 라우팅하는 데 사용 됩니다.</p></td>
<td><p>Lync Server 2010에서 더 이상 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PhoneRoutes (구식)</p></td>
<td><p>이 클래스는 최소 순위의 여러 경로에 대 한 컨테이너 이며 특성 자체를 포함 하지 않습니다.</p></td>
<td><p>Lync Server 2010에서 더 이상 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-정책 (구식)</p></td>
<td><p>이 클래스는 여러 Lync Server 정책 클래스를 보유 하며 특성 자체는 없습니다.</p></td>
<td><p>Lync Server 2010에서 더 이상 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-풀</p></td>
<td><p>이 클래스는 단일 Lync Server 풀을 나타냅니다.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-풀</p></td>
<td><p>이 클래스는 여러 Lync Server 풀을 보유 하며 특성 자체는 없습니다.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolService</p></td>
<td><p>이 클래스는 풀의 서비스 제어 포인트 서비스 제어점을 나타냅니다. 풀에 호스팅되는 사용자의 msRTCSIP-PrimaryHomeServer 특성 점이이 클래스의 인스턴스에 해당 합니다.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-현재 상태</p></td>
<td><p>전역 현재 상태 설정을 저장 하는 컨테이너입니다.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-등록자</p></td>
<td><p>MsRTCSIP-GlobalContainer에 대 한이 보조 클래스는 SIP 등록자 서버에서 유지 관리 하는 사용자 설정을 나타내는 특성을 보유 합니다.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-RouteUsage (구식)</p></td>
<td><p>이 클래스는 전화 경로 사용의 인스턴스를 나타내는 컨테이너입니다. 전화 경로 사용 클래스는 특성 필드와 설명 필드로 구성 됩니다. 특성 필드는 사용 유형을 정의 합니다. 관리자는 설명 필드를 사용 하 여 전화 라우트에이 특성에 대 한 사용량을 설명할 수 있습니다.</p></td>
<td><p>Lync Server 2010에서 더 이상 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-RouteUsages (구식)</p></td>
<td><p>이 클래스는 msRTCSIP-RouteUsage 클래스의 여러 인스턴스를 포함 하며 특성 자체는 포함 하지 않습니다.</p></td>
<td><p>Lync Server 2010에서 더 이상 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-검색</p></td>
<td><p>MsRTCSIP-GlobalContainer에 대 한이 보조 클래스는 검색 결과 범위를 제한 하 고 제어 하는 특성을 보유 합니다.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-서버</p></td>
<td><p>이 클래스는 Lync Server를 실행 하는 단일 서버를 나타냅니다.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-서비스</p></td>
<td><p>이 클래스에는 전역 설정 컨테이너 및 msRTCSIP 도메인 개체가 포함 됩니다.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP 된 Mcu</p></td>
<td><p>이 클래스에는 신뢰할 수 있는 회의 서버의 설정을 나타내는 특성이 포함 됩니다.</p></td>
<td><p>통신 서버 2007의 새로운 방법.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedMCUs</p></td>
<td><p>이 클래스에는 msRTCSIP로 거는 Mcu 클래스의 여러 인스턴스가 저장 되며 특성 자체는 없습니다.</p></td>
<td><p>통신 서버 2007의 새로운 방법.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP 프록시</p></td>
<td><p>이 클래스는 여러 msRTCSIP 프록시 클래스를 보유 하며 특성 자체를 포함 하지 않습니다.</p></td>
<td><p>통신 서버 2007의 새로운 방법.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP 프록시</p></td>
<td><p>이 클래스는 프록시 서버를 실행 하는 서버를 나타내는 컨테이너입니다. 이 클래스의 인스턴스는 AD DS에 연결 된 컴퓨터에서 새 프록시 서버를 활성화할 때 만들어집니다.</p></td>
<td><p>통신 서버 2007의 새로운 방법.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP 서버</p></td>
<td><p>이 클래스는 신뢰할 수 있는 서버에 대 한 설정을 나타내는 특성을 보유 합니다.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP 서비스</p></td>
<td><p>이 클래스는 전역적으로 라우팅할 수 있는 GRUU (사용자 에이전트 URI) 주소를 사용 하 여 라우팅할 수 있는 서비스를 나타내는 컨테이너입니다. 이 클래스의 인스턴스는 Lync Server에서 신뢰 하는 새 서버가 활성화 될 때 만들어집니다. 이 신뢰할 수 있는 서버는 Active Directory 도메인에 가입 되어 있어야 합니다.</p></td>
<td><p>통신 서버 2007의 새로운 방법.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP 서비스</p></td>
<td><p>이 클래스는 여러 GRUU 서버에 대 한 컨테이너 이며 특성 자체를 포함 하지 않습니다.</p></td>
<td><p>통신 서버 2007의 새로운 방법.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedWebComponentsServer</p></td>
<td><p>이 클래스에는 신뢰할 수 있는 웹 구성 요소에 대 한 설정을 나타내는 특성이 포함 됩니다.</p></td>
<td><p>통신 서버 2007의 새로운 방법.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedWebComponentsServers</p></td>
<td><p>이 클래스는 msRTCSIP Webcomponentserver 클래스의 여러 인스턴스를 보유 하며 특성 자체를 포함 하지 않습니다.</p></td>
<td><p>통신 서버 2007의 새로운 방법.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UnifiedCommunications (구식)</p></td>
<td><p>MsRTCSIP-GlobalContainer에 대 한이 보조 클래스는 통합 커뮤니케이션 관련 특성을 유지 합니다.</p></td>
<td><p>Lync Server 2010에서 더 이상 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-WebComponents</p></td>
<td><p>이 클래스는 IIS (Internet Information Server)에 대 한 서비스 제어 포인트 서비스 제어 지점을 보유 합니다. 서버를 웹 구성 요소 서버로 식별 합니다.</p></td>
<td><p>통신 서버 2007의 새로운 방법.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-WebComponentsService</p></td>
<td><p>이 클래스는 특정 풀과 풀에서 사용할 웹 구성 요소에 대 한 연결을 제공 합니다.</p></td>
<td><p>통신 서버 2007의 새로운 방법.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-WebComponentSettings</p></td>
<td><p>MsRTCSIP 구성 요소에 대 한이 보조 클래스는 웹 구성 요소 설정을 나타내는 특성을 보유 합니다.</p></td>
<td><p>통신 서버 2007의 새로운 방법.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

