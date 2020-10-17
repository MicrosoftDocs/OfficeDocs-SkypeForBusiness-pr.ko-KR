---
title: 'Lync Server 2013: 스키마 클래스 및 설명'
description: 'Lync Server 2013: 스키마 클래스 및 설명'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Schema classes and descriptions
ms:assetid: 7d43b920-ac37-40cc-adfe-be289bda6e9e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398625(v=OCS.15)
ms:contentKeyID: 48184612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec27c2e00a7f969dbc13c91b06313c8045894a9e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557104"
---
# <a name="schema-classes-and-descriptions-in-lync-server-2013"></a>Lync Server 2013의 스키마 클래스 및 설명

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-30_

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
<th>클래스</th>
<th>설명</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Mail-Recipient</p></td>
<td><p>Exchange UM (통합 메시징) 전자 메일 받는 사람</p></td>
<td><p>이 보조 클래스는 Exchange UM과 공유 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-ApplicationContacts</p></td>
<td><p>이 클래스는 여러 응용 프로그램 대화 상대에 대한 컨테이너이고 자체적으로 특성을 포함하지는 않습니다.</p></td>
<td><p>Microsoft Office Communications Server 2007 r 2의 새로운 정보</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-ApplicationServer</p></td>
<td><p>이 클래스는 UCAS(통합 통신 응용 프로그램 서비스) 인스턴스의 서비스 제어 지점에 대한 항목을 포함하고 있습니다.</p></td>
<td><p>Office Communications Server 2007 r 2의 새로운 정보</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-ApplicationServerService</p></td>
<td><p>이 클래스는 특정 풀에서 해당 응용 프로그램 서비스로의 연결을 제공 합니다.</p></td>
<td><p>Communications Server 2007 r 2의 새로운 정보</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-ApplicationServerSettings</p></td>
<td><p>이 보조 클래스는 응용 프로그램 서비스의 인스턴스에 대 한 설정을 나타내는 특성을 보유 합니다 (Msrtcsip-gateways).</p></td>
<td><p>Communications Server 2007 r 2의 새로운 정보</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Archive(사용되지 않음)</p></td>
<td><p>msRTCSIP-GlobalContainer에 대한 이 보조 클래스는 보관과 관련된 모든 설정을 포함하고 있습니다.</p></td>
<td><p>Lync Server 2010에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchivingServer(사용되지 않음)</p></td>
<td><p>이 클래스는 단일 인스턴트 메시징 보관 서버를 나타냅니다. 이 클래스의 인스턴스는 컴퓨터(예: 인스턴트 메시징 보관 서비스가 설치된 컴퓨터)가 인스턴트 메시징 보관 서버로 활성화될 때 만들어집니다.</p></td>
<td><p>Lync Server 2010에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-Microsoft.rtc.management.writableconfig.settings.pstnconf.conferencedirectories</p></td>
<td><p>이 클래스는 전화 회의 디렉터리의 여러 인스턴스에 대한 컨테이너이고 자체적으로 특성을 포함하지는 않습니다.</p></td>
<td><p>Communications Server 2007 r 2의 새로운 정보</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-ConferenceDirectory</p></td>
<td><p>이 클래스는 특정 전화 회의 디렉터리에 대한 설정을 나타내는 특성을 포함하고 있습니다.</p></td>
<td><p>Communications Server 2007 r 2의 새로운 정보</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-Msrtcsip-connectionpoint</p></td>
<td><p>컴퓨터를 Lync Server를 실행 하는 서버로 지정 하는 SCP (일반 서비스 제어 지점)</p></td>
<td><p>Lync 2010의 새로운 방법</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-DefaultCWABank</p></td>
<td><p>이 보조 클래스에는 Microsoft Lync Web App 은행의 설정이 포함 됩니다.</p></td>
<td><p>Communications Server 2007 r 2의 새로운 정보</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-도메인</p></td>
<td><p>이 클래스는 SIP 등록자의 구성된 도메인을 정의하는 특성을 포함하고 있습니다.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-EdgeProxy</p></td>
<td><p>이 클래스 컨테이너는 단일 액세스에 지 서비스를 나타냅니다. 액세스에 지 서비스는 경계 네트워크에 배포 되 고, 고객은 일반적으로 경계 네트워크에서 Active Directory 도메인 서비스 액세스를 허용 하지 않으므로 액세스에 지 서비스의 인스턴스가 인트라넷의 Active Directory 네트워크에 연결 되지 않습니다. 따라서 액세스 프록시는 자동으로 AD DS에 등록되지 않습니다. 관리자는 AD DS에 각 액세스에 지 서비스 인스턴스가 있는지 여부를 수동으로 구성 해야 합니다.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-EnterpriseMCUSettings</p></td>
<td><p>msRTCSIP-MCU에 대한 이 보조 클래스는 회의 서버에 대한 설정을 나타내는 특성을 포함하고 있습니다.</p></td>
<td><p>Microsoft Office Communications Server 2007의 새로운 정보</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-EnterpriseMediationServerSettings</p></td>
<td><p>msRTCSIP-MediationServer에 대한 이 보조 클래스는 중재 서버에 대한 설정을 나타내는 특성을 포함하고 있습니다.</p></td>
<td><p>Office Communications Server 2007의 새로운 정보</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-EnterpriseServerSettings</p></td>
<td><p>msRTCSIP-Server에 대한 이 보조 클래스는 SIP 서버에 대한 설정을 나타내는 특성을 포함하고 있습니다.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-페더레이션</p></td>
<td><p>msRTCSIP-GlobalContainer에 대한 이 보조 클래스는 페더레이션과 관련된 모든 설정을 포함하고 있습니다.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-GlobalContainer</p></td>
<td><p>이 클래스에는 Lync Server 배포 전체에 적용 되는 모든 설정이 포함 됩니다.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-GlobalUserPolicy(사용되지 않음)</p></td>
<td><p>이 클래스는 단일 Office Communications Server meeting policy를 나타냅니다.</p></td>
<td><p>Lync Server 2010에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-GlobalTopologySetting</p></td>
<td><p>로컬 전역 토폴로지 설정 개체입니다.</p></td>
<td><p>Lync Server 2010의 새로운 방법</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-GlobalTopologySettings</p></td>
<td><p>전역 토폴로지 설정 개체를 포함할 컨테이너입니다.</p></td>
<td><p>Lync Server 2010의 새로운 방법</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-LocalNormalization</p></td>
<td><p>이 클래스는 위치 정규화 규칙의 인스턴스를 나타내는 컨테이너입니다.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-Location연락처 매핑</p></td>
<td><p>이 클래스는 회의 전화 교환 응용 프로그램에서 만들어지며 지역별 전화 번호를 분류 하는 데 사용 되는 특성을 보유 합니다.</p></td>
<td><p>Communications Server 2007 r 2의 새로운 정보</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-Location연락처 매핑</p></td>
<td><p>이 클래스는 위치 대화 상대 매핑의 여러 인스턴스에 대한 컨테이너이고 자체적으로 특성을 포함하지는 않습니다.</p></td>
<td><p>Communications Server 2007 r 2의 새로운 정보</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-LocationProfile</p></td>
<td><p>이 클래스는 특정 위치 프로필을 나타내는 컨테이너입니다.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocationProfiles(사용되지 않음)</p></td>
<td><p>이 클래스는 여러 위치 프로필에 대한 컨테이너이고 자체적으로 특성을 포함하지는 않습니다.</p></td>
<td><p>Lync Server 2010에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocalNormalizations(사용되지 않음)</p></td>
<td><p>이 클래스는 여러 로컬 정규화 규칙에 대한 컨테이너이고 자체적으로 특성을 포함하지는 않습니다.</p></td>
<td><p>Lync Server 2010에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-MCU</p></td>
<td><p>이 클래스는 단일 회의 서버를 나타냅니다.</p></td>
<td><p>Communications Server 2007의 새로운 정보</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-MCUFactories</p></td>
<td><p>이 클래스는 여러 msRTCSIP-MCUFactory 클래스를 포함하며 자체적으로 특성을 포함하지는 않습니다.</p></td>
<td><p>Communications Server 2007의 새로운 정보</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-MCUFactory</p></td>
<td><p>이 클래스는 단일 미디어 유형에 대한 회의 서버 센터를 나타내는 컨테이너입니다. 이 특정 유형 및 공급업체에 대한 첫 번째 회의 서버가 활성화될 경우 이 클래스의 인스턴스가 만들어집니다.</p></td>
<td><p>Communications Server 2007의 새로운 정보</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-MCUFactoryService</p></td>
<td><p>이 클래스는 특정 풀에서 해당 회의 서버 센터까지의 연결을 제공합니다.</p></td>
<td><p>Communications Server 2007의 새로운 정보</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-MediationServer</p></td>
<td><p>이 클래스는 중재 서버의 서비스 제어 지점에 대한 항목을 포함하고 있습니다.</p></td>
<td><p>Communications Server 2007의 새로운 정보</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Meeting(사용되지 않음)</p></td>
<td><p>msRTCSIP-GlobalContainer에 대한 이 보조 클래스는 구성 가능한 모임 설정을 나타내는 특성을 포함하고 있습니다.</p></td>
<td><p>Lync Server 2010에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-모바일</p></td>
<td><p>전역 모바일 설정을 저장하는 컨테이너입니다.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-MonitoringServer</p></td>
<td><p>이 클래스는 단일 모니터링 서버에 대 한 설정을 나타내는 특성을 포함 합니다.</p></td>
<td><p>Communications Server 2007 r 2의 새로운 정보</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PhoneRoute(사용되지 않음)</p></td>
<td><p>이 클래스는 특정 게이트웨이 또는 게이트웨이 집합에 대한 최소 비용 경로의 인스턴스를 나타내는 컨테이너입니다. 모든 엔터프라이즈 풀 또는 Standard Edition을 실행하는 서버는 가장 비용 효과적인 방법으로 발신 전화를 PSTN(공중 전화망)으로 라우팅하기 위해 이 정보를 사용합니다.</p></td>
<td><p>Lync Server 2010에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PhoneRoutes(사용되지 않음)</p></td>
<td><p>이 클래스는 여러 최소 비용 경로에 대한 컨테이너이고 자체적으로 특성을 포함하지는 않습니다.</p></td>
<td><p>Lync Server 2010에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Policies(사용되지 않음)</p></td>
<td><p>이 클래스는 여러 Lync Server 정책 클래스를 포함 하며 자체적으로 특성을 포함 하지는 않습니다.</p></td>
<td><p>Lync Server 2010에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-풀</p></td>
<td><p>이 클래스는 단일 Lync Server 풀을 나타냅니다.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-풀</p></td>
<td><p>이 클래스는 여러 Lync Server 풀을 포함 하며 자체적으로 특성을 포함 하지는 않습니다.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-PoolService</p></td>
<td><p>이 클래스는 풀의 서비스 제어 지점을 나타냅니다. 풀에서 호스팅되는 사용자는 이 클래스의 인스턴스를 가리키는 msRTCSIP-PrimaryHomeServer 특성을 가지고 있습니다.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-현재 상태</p></td>
<td><p>전역 현재 상태 설정을 저장하는 컨테이너입니다.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-등록자</p></td>
<td><p>msRTCSIP-GlobalContainer에 대한 이 보조 클래스는 SIP 등록자 서버에서 유지 관리하는 사용자 설정을 나타내는 특성을 포함하고 있습니다.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-RouteUsage(사용되지 않음)</p></td>
<td><p>이 클래스는 전화 경로 사용의 인스턴스를 나타내는 컨테이너입니다. 전화 경로 사용 클래스는 특성 필드 및 설명 필드로 구성됩니다. 특정 필드는 사용 유형을 정의합니다. 설명 필드를 사용하면 관리자는 전화 경로에서 이 특성의 사용을 설명할 수 있습니다.</p></td>
<td><p>Lync Server 2010에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-RouteUsages(사용되지 않음)</p></td>
<td><p>이 클래스는 msRTCSIP-RouteUsage 클래스의 여러 인스턴스를 포함하며 자체적으로 특성을 포함하지는 않습니다.</p></td>
<td><p>Lync Server 2010에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-검색</p></td>
<td><p>msRTCSIP-GlobalContainer에 대한 이 보조 클래스는 검색 결과의 범위를 제한 및 제어하는 특성을 포함하고 있습니다.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-Server</p></td>
<td><p>이 클래스는 Lync Server를 실행 하는 단일 서버를 나타냅니다.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-서비스</p></td>
<td><p>이 클래스는 전역 설정 컨테이너 및 msRTCSIP-Domain 개체를 포함하고 있습니다.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways로이 Mcu</p></td>
<td><p>이 클래스는 트러스트된 회의 서버에 대한 설정을 나타내는 특성을 포함하고 있습니다.</p></td>
<td><p>Communications Server 2007의 새로운 정보</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-TrustedMCUs</p></td>
<td><p>이 클래스는 msRTCSIP-TrustedMCU 클래스의 여러 인스턴스를 포함하며 자체적으로 특성을 포함하지는 않습니다.</p></td>
<td><p>Communications Server 2007의 새로운 정보</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways 프록시</p></td>
<td><p>이 클래스는 여러 msRTCSIP-TrustedProxy 클래스를 포함하며 자체적으로 특성을 포함하지는 않습니다.</p></td>
<td><p>Communications Server 2007의 새로운 정보</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways 프록시</p></td>
<td><p>이 클래스는 프록시 서버를 실행하는 서버를 나타내는 컨테이너입니다. AD DS에 가입된 컴퓨터에서 새 프록시 서버를 활성화할 경우 이 클래스의 인스턴스가 만들어집니다.</p></td>
<td><p>Communications Server 2007의 새로운 정보</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways 서버</p></td>
<td><p>이 클래스는 트러스트된 서버에 대한 설정을 나타내는 특성을 포함하고 있습니다.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways 서비스</p></td>
<td><p>이 클래스는 GRUU(Globally Routable User Agent URI) 주소를 사용하여 라우팅할 수 있는 트러스트된 서비스를 나타내는 컨테이너입니다. 이 클래스의 인스턴스는 Lync Server에서 신뢰 하는 새 서버가 활성화 될 때 만들어집니다. 이 트러스트된 서버는 Active Directory 도메인에 가입해야 합니다.</p></td>
<td><p>Communications Server 2007의 새로운 정보</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways 서비스</p></td>
<td><p>이 클래스는 여러 GRUU 서버에 대한 컨테이너이고 자체적으로 특성을 포함하지는 않습니다.</p></td>
<td><p>Communications Server 2007의 새로운 정보</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-TrustedWebComponentsServer</p></td>
<td><p>이 클래스는 트러스트된 웹 구성 요소에 대한 설정을 나타내는 특성을 포함하고 있습니다.</p></td>
<td><p>Communications Server 2007의 새로운 정보</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-TrustedWebComponentsServers</p></td>
<td><p>이 클래스는 msRTCSIP-TrustedWebComponentServer 클래스의 여러 인스턴스를 포함하며 자체적으로 특성을 포함하지는 않습니다.</p></td>
<td><p>Communications Server 2007의 새로운 정보</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UnifiedCommunications(사용되지 않음)</p></td>
<td><p>msRTCSIP-GlobalContainer에 대한 이 보조 클래스는 통합 통신과 관련된 특성을 포함하고 있습니다.</p></td>
<td><p>Lync Server 2010에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-WebComponents</p></td>
<td><p>이 클래스는 IIS(Internet Information Server)의 서비스 제어 지점을 포함하고 있으며 서버를 웹 구성 요소 서버로 식별합니다.</p></td>
<td><p>Communications Server 2007의 새로운 정보</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-gateways-WebComponentsService</p></td>
<td><p>이 클래스는 특정 풀에서 해당 풀이 사용하는 웹 구성 요소까지의 연결을 제공합니다.</p></td>
<td><p>Communications Server 2007의 새로운 정보</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-gateways-WebComponentSettings</p></td>
<td><p>msRTCSIP-WebComponents에 대한 이 보조 클래스는 웹 구성 요소에 대한 설정을 나타내는 특성을 포함하고 있습니다.</p></td>
<td><p>Communications Server 2007의 새로운 정보</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

