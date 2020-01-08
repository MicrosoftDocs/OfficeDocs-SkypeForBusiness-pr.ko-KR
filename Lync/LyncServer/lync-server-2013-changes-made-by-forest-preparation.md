---
title: 'Lync Server 2013: 포리스트 준비로 변경한 내용'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changes made by forest preparation
ms:assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425791(v=OCS.15)
ms:contentKeyID: 48183734
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef94ea82f31871cf90939aa25a130903f15ef756
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979328"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-forest-preparation-in-lync-server-2013"></a>Lync Server 2013의 포리스트 준비에의 한 변경 사항

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-30_

이 섹션에서는 포리스트 준비 단계에서 만든 전역 설정 및 개체와 유니버설 서비스 및 관리 그룹에 대해 설명 합니다.

<div>

## <a name="active-directory-global-settings-and-objects"></a>Active Directory 전역 설정 및 개체

전역 설정을 구성 컨테이너에 저장 하는 경우 (모든 새 Lync Server 2013 배포의 경우) 포리스트 준비는 기존 서비스 컨테이너를 사용 하 고 구성\\서비스 개체 아래에 **RTC 서비스** 개체를 추가 합니다. RTC 서비스 개체에서 포리스트 준비는 msRTCSIP-GlobalContainer 유형의 **전역 설정** 개체를 추가 합니다. 전역 설정 개체에는 Lync Server 배포에 적용 되는 모든 설정이 포함 되어 있습니다. 시스템 컨테이너에 전역 설정을 저장 하는 경우 포리스트 준비는 루트 도메인 시스템 컨테이너 아래에 Microsoft 컨테이너를 사용 하 고 시스템\\microsoft 개체 아래에 RTC 서비스 개체를 사용 합니다.

또한 포리스트 준비는 프로시저가 실행 되는 루트 도메인에 대 한 새 **MsRTCSIP 도메인** 개체를 추가 합니다.

</div>

<div>

## <a name="active-directory-universal-service-and-administration-groups"></a>Active Directory 유니버설 서비스 및 관리 그룹

포리스트 준비는 사용자가 지정 하는 도메인을 기반으로 유니버설 그룹을 만들고 이러한 그룹에 대 한 Ace (액세스 제어 항목)를 추가 합니다. 이 단계에서는 지정 하는 도메인의 사용자 컨테이너에 유니버설 그룹을 만듭니다.

유니버설 그룹을 통해 관리자는 전역 설정 및 서비스에 액세스 하 고 관리할 수 있습니다. 포리스트 준비는 다음 유형의 유니버설 그룹을 추가 합니다.

  - **관리 그룹**   이러한 그룹은 Lync Server 네트워크의 관리자 역할을 정의 합니다.

  - **인프라 그룹**   이러한 그룹은 Lync Server 인프라의 특정 영역에 대 한 액세스 권한을 제공 합니다. 관리 그룹의 구성 요소로 작동 합니다. 이러한 그룹을 수정 하거나 직접 사용자를 추가 해서는 안 됩니다.

  - **서비스 그룹**   이러한 그룹은 다양 한 Lync Server 서비스에 액세스 하는 데 필요한 서비스 계정입니다.

다음 표에서는 관리 그룹에 대해 설명 합니다.

### <a name="administrative-groups-created-during-forest-preparation"></a>포리스트 준비 중에 만든 관리 그룹

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>관리 그룹</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCUniversalServerAdmins</p></td>
<td><p>구성원이 모든 서버 역할, 전역 설정 및 사용자를 비롯 한 서버 및 풀 설정을 관리할 수 있도록 합니다.</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>구성원이 사용자 설정을 관리 하 고 사용자를 한 서버나 풀에서 다른 서버로 이동할 수 있도록 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalReadOnlyAdmins</p></td>
<td><p>구성원이 서버, 풀 및 사용자 설정을 읽을 수 있도록 허용 합니다.</p></td>
</tr>
</tbody>
</table>


다음 표에서는 인프라 그룹에 대해 설명 합니다.

### <a name="infrastructure-groups-created-during-forest-preparation"></a>포리스트 준비 중 만들어진 인프라 그룹

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>인프라 그룹</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCUniversalGlobalWriteGroup</p></td>
<td><p>Lync Server의 전역 설정 개체에 대 한 쓰기 권한을 부여 합니다.</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalGlobalReadOnlyGroup</p></td>
<td><p>Lync Server의 전역 설정 개체에 대 한 읽기 전용 액세스 권한을 부여 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Lync Server 사용자 설정에 대 한 읽기 전용 액세스 권한을 부여 합니다.</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Lync 서버 설정에 대 한 읽기 전용 액세스 권한을 부여 합니다. 이 그룹은 풀 수준 설정에 대 한 액세스 권한이 없으며 개별 서버에만 해당 하는 설정에만 액세스할 수 있습니다.</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalSBATechnicians</p></td>
<td><p>Lync Server 구성에 대 한 읽기 전용 액세스 권한을 부여 하 고 설치 중에 survivable 분기 기기의 로컬 관리자 그룹에 배치 됩니다.</p></td>
</tr>
</tbody>
</table>


다음 표에서는 서비스 그룹에 대해 설명 합니다.

### <a name="service-groups-created-during-forest-preparation"></a>포리스트 준비 중에 만든 서비스 그룹

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>서비스 그룹</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>프런트 엔드 서버 및 Standard Edition 서버를 실행 하는 데 사용 되는 서비스 계정이 포함 됩니다. 이 그룹은 서버에서 Lync Server 전역 설정 및 Active Directory 사용자 개체에 대 한 읽기/쓰기 액세스를 허용 합니다.</p></td>
</tr>
<tr class="even">
<td><p>RTCComponentUniversalServices</p></td>
<td><p>A/V 회의 서버, 웹 서비스, 중재 서버, 보관 서버, 모니터링 서버를 실행 하는 데 사용 되는 서비스 계정을 포함 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>RTCProxyUniversalServices</p></td>
<td><p>Lync Server Edge 서버를 실행 하는 데 사용 되는 서비스 계정이 포함 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalConfigReplicator</p></td>
<td><p>Lync Server 중앙 관리 저장소 복제에 참가할 수 있는 서버를 포함 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>RTCSBAUniversalServices</p></td>
<td><p>Lync Server 설정에 대 한 읽기 전용 액세스 권한을 부여 하지만, survivable branch 서버 설치 및 survivable branch 기기 배포에 대 한 구성을 허용 합니다.</p></td>
</tr>
</tbody>
</table>


그런 다음 포리스트 준비는 다음과 같이 해당 인프라 그룹에 서비스 및 관리 그룹을 추가 합니다.

  - RTCUniversalServerAdmins는 RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup, RTCUniversalUserReadOnlyGroup에 추가 됩니다.

  - RTCUniversalUserAdmins는 RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup, RTCUniversalUserReadOnlyGroup의 구성원으로 추가 됩니다.

  - RTCHSUniversalServices, RTCComponentUniversalServices 및 RTCUniversalReadOnlyAdmins는 RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup, RTCUniversalUserReadOnlyGroup의 구성원으로 추가 됩니다.

포리스트 준비는 또한 다음과 같은 RBAC (역할 기반 액세스 제어) 그룹을 만듭니다.

  - CSAdministrator

  - CSArchivingAdministrator

  - CSHelpDesk

  - CSLocationAdministrator

  - CSResponseGroupAdministrator

  - CSServerAdministrator

  - CSUserAdministrator

  - Csviewadministrator

  - CSVoiceAdministrator

  - CsPersistentChatAdministator

  - CsResponseGroupManager

각 항목에 대해 허용 된 RBAC 역할 및 작업에 대 한 자세한 내용은 계획 문서에서 [Lync Server 2013의 역할 기반 액세스 제어 계획](lync-server-2013-planning-for-role-based-access-control.md) 을 참조 하세요.

포리스트 준비는 개인 Ace를 모두 만듭니다. Lync Server에서 사용 하는 전역 설정 컨테이너에 개인 Ace를 만듭니다. 이 컨테이너는 Lync Server 에서만 사용 되며 전역 설정을 저장 하는 위치에 따라 루트 도메인의 구성 컨테이너 또는 시스템 컨테이너에 있습니다. 포리스트 준비로 만든 공개 Ace는 다음 표에 나열 되어 있습니다.

### <a name="public-aces-created-by-forest-preparation"></a>포리스트 준비로 만든 공개 Ace

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>ACE</th>
<th>RTCUniversalGlobalReadOnlyGroup</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>루트 도메인 시스템 컨테이너 읽기 (상속 되지 않음)<strong>*</strong></p></td>
<td><p>축</p></td>
</tr>
<tr class="even">
<td><p>구성의 DisplaySpecifiers 컨테이너 읽기 (상속 되지 않음)</p></td>
<td><p>축</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <STRONG>*</STRONG>상속 되지 않은 Ace는 이러한 컨테이너 아래의 자식 개체에 대 한 액세스를 허용 하지 않습니다. 상속 된 Ace는 이러한 컨테이너 아래에 있는 자식 개체에 대 한 액세스 권한을 부여 합니다.



</div>

구성 컨테이너의 구성 명명 컨텍스트 아래에서 포리스트 준비는 다음 작업을 수행 합니다.

  - 사용자, 연락처 및 InetOrgPersons에 대 한 언어 표시 지정자의 adminContextMenu 및 adminPropertyPages 특성 아래에 **RTC 속성** 페이지의 **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** 항목을 추가 합니다 (예: Cn = USER-display, CN = 409, cn = displayspecifiers).

  - 사용자 및 연락처 클래스에 적용 되는 **확장 권한** 바로 아래에 **Controlaccessright** 의 **RTCPropertySet** 개체를 추가 합니다.

  - 사용자, 연락처, OU 및 DomainDNS 클래스에 적용 되는 **확장 권한** 바로 아래에 **Controltype** 의 **RTCUserSearchPropertySet** 개체를 추가 합니다.

  - 각 OU (조직 구성 단위) 표시 지정자의 **extraColumns** 특성 아래에 **msRTCSIP-PrimaryUserAddress** 를 추가 합니다 (예: Cn = ORGANIZATIONALUNIT-display, CN = 409, cn = displayspecifiers). 기본 디스플레이의 **extraColumns** 특성 값을 복사 합니다 (예: CN = default-DISPLAY, Cn = 409, cn = displayspecifiers).

  - 사용자, 연락처 및 InetOrgPerson 개체에 대 한 각 언어 표시 지정자의 **Attributedisplaynames** 특성 아래에 **msRTCSIP-PrimaryUserAddress**, **msRTCSIP, PrimaryHomeServer**, **msRTCSIP-userenabled** 필터링 특성을 추가 합니다 (예를 들어 영어: CN = 사용자-Display, cn = 409, cn = display지정자).

</div>

</div>

<span> </span>

</div>

</div>

</div>

