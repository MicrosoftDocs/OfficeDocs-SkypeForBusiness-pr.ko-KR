---
title: 'Lync Server 2013: 포리스트 준비로 인 한 변경 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by forest preparation
ms:assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425791(v=OCS.15)
ms:contentKeyID: 48183734
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e31e088d34bae2e136d86751c71f45754dc9db07
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043940"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-forest-preparation-in-lync-server-2013"></a>Lync Server 2013에서 포리스트 준비로 인 한 변경 사항

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-30_

이 섹션에서는 포리스트 준비 단계를 통해 만들어지는 전역 설정과 개체, 유니버설 서비스 및 관리 그룹에 대해 설명합니다.

<div>

## <a name="active-directory-global-settings-and-objects"></a>Active Directory 전역 설정 및 개체

전역 설정을 구성 컨테이너에 저장 하는 경우 (모든 새 Lync Server 2013 배포의 경우) 포리스트 준비에서는 기존 서비스 컨테이너를 사용 하 고 구성\\서비스 개체 아래에 **RTC 서비스** 개체를 추가 합니다. 포리스트 준비에서는 RTC Service 개체 아래에 msRTCSIP-GlobalContainer 유형의 **Global Settings** 개체를 추가합니다. 전역 설정 개체에는 Lync Server 배포에 적용 되는 모든 설정이 포함 됩니다. 시스템 컨테이너에 전역 설정을 저장 하는 경우 포리스트 준비에서는 루트 도메인 시스템 컨테이너 아래의 Microsoft 컨테이너와 시스템\\microsoft 개체 아래에 RTC 서비스 개체를 사용 합니다.

또한 포리스트 준비에서는 절차가 실행되는 루트 도메인에 대한 새로운 **msRTCSIP-Domain** 개체를 추가합니다.

</div>

<div>

## <a name="active-directory-universal-service-and-administration-groups"></a>Active Directory 유니버설 서비스 및 관리 그룹

포리스트 준비에서는 지정한 도메인을 기반으로 유니버설 그룹을 만들고 이러한 그룹에 대한 ACE(액세스 제어 항목)를 추가합니다. 이 단계에서 유니버설 그룹은 지정하는 도메인의 User 컨테이너에 만들어집니다.

유니버설 그룹에서는 관리자가 전역 설정 및 서비스를 액세스하고 관리할 수 있습니다. 포리스트를 준비하면 다음 유형의 유니버설 그룹이 추가됩니다.

  - **관리 그룹**   이러한 그룹은 Lync Server 네트워크에 대 한 관리자 역할을 정의 합니다.

  - **인프라 그룹**   이러한 그룹은 Lync Server 인프라의 특정 영역에 액세스할 수 있는 권한을 제공 합니다. 이 그룹은 관리 그룹의 구성 요소로 작동합니다. 이러한 그룹을 수정하거나 여기에 사용자를 직접 추가해서는 안 됩니다.

  - **서비스 그룹**   이러한 그룹은 다양 한 Lync Server 서비스에 액세스 하는 데 필요한 서비스 계정입니다.

다음 표에서는 관리 그룹에 대해 설명합니다.

### <a name="administrative-groups-created-during-forest-preparation"></a>포리스트 준비 중에 생성되는 관리 그룹

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
<td><p>구성원이 모든 서버 역할, 전역 설정 및 사용자를 포함하여 서버 및 풀 설정을 관리할 수 있습니다.</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>구성원이 사용자 설정을 관리하고 한 서버 또는 풀에서 다른 서버 또는 풀로 사용자를 이동할 수 있습니다.</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalReadOnlyAdmins</p></td>
<td><p>구성원이 서버, 풀 및 사용자 설정을 읽을 수 있습니다.</p></td>
</tr>
</tbody>
</table>


다음 표에서는 인프라 그룹에 대해 설명합니다.

### <a name="infrastructure-groups-created-during-forest-preparation"></a>포리스트 준비 중에 생성되는 인프라 그룹

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
<td><p>Lync Server에 대 한 전역 설정 개체에 대 한 쓰기 권한을 부여 합니다.</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalGlobalReadOnlyGroup</p></td>
<td><p>Lync Server에 대 한 전역 설정 개체에 대 한 읽기 전용 액세스 권한을 부여 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Lync Server 사용자 설정에 대 한 읽기 전용 액세스 권한을 부여 합니다.</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Lync Server 설정에 대 한 읽기 전용 액세스 권한을 부여 합니다. 이 그룹은 풀 수준 설정에는 액세스할 수 없고 개별 서버와 관련된 설정에만 액세스할 수 있습니다.</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalSBATechnicians</p></td>
<td><p>Lync Server 구성에 대 한 읽기 전용 액세스 권한을 부여 하 고 설치 중에 sba (survivable 분기 기기의 로컬 관리자 그룹에 위치 합니다.</p></td>
</tr>
</tbody>
</table>


다음 표에서는 서비스 그룹에 대해 설명합니다.

### <a name="service-groups-created-during-forest-preparation"></a>포리스트 준비 중에 생성되는 서비스 그룹

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
<td><p>프런트 엔드 서버 및 Standard Edition 서버를 실행 하는 데 사용 되는 서비스 계정을 포함 합니다. 이 그룹은 서버가 Lync Server 전역 설정 및 Active Directory 사용자 개체에 대 한 읽기/쓰기 액세스를 허용 합니다.</p></td>
</tr>
<tr class="even">
<td><p>RTCComponentUniversalServices</p></td>
<td><p>A/V 회의 서버, 웹 서비스, 중재 서버, 보관 서버 및 모니터링 서버를 실행 하는 데 사용 되는 서비스 계정을 포함 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>RTCProxyUniversalServices</p></td>
<td><p>Lync Server에 지 서버를 실행 하는 데 사용 되는 서비스 계정을 포함 합니다.</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalConfigReplicator</p></td>
<td><p>Lync Server 중앙 관리 저장소 복제에 참가할 수 있는 서버를 포함 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>RTCSBAUniversalServices</p></td>
<td><p>Lync Server 설정에 대 한 읽기 전용 액세스 권한을 부여 하지만 sba (survivable 분기 서버 및 sba (survivable branch 기기 배포의 설치를 위한 구성을 허용 합니다.</p></td>
</tr>
</tbody>
</table>


그런 다음 포리스트 준비에서는 다음과 같이 해당 인프라 그룹에 서비스 및 관리 그룹을 추가합니다.

  - RTCUniversalServerAdmins는 RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup 및 RTCUniversalUserReadOnlyGroup에 추가됩니다.

  - RTCUnversalUserAdmins는 RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup 및 RTCUniversalUserReadOnlyGroup의 구성원으로 추가됩니다.

  - RTCHSUniversalServices, RTCComponentUniversalServices 및 RTCUniversalReadOnlyAdmins는 RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup 및 RTCUniversalUserReadOnlyGroup의 구성원으로 추가됩니다.

또한 포리스트 준비에서는 다음과 같은 RBAC(역할 기반 액세스 제어) 그룹을 만듭니다.

  - CSAdministrator

  - CSArchivingAdministrator

  - CSHelpDesk

  - CSLocationAdministrator

  - CSResponseGroupAdministrator

  - CSServerAdministrator

  - CSUserAdministrator

  - CSViewOnlyAdministrator

  - CSVoiceAdministrator

  - CsPersistentChatAdministator

  - CsResponseGroupManager

각 항목에 대해 허용 되는 RBAC 역할 및 작업에 대 한 자세한 내용은 계획 설명서의 [Lync Server 2013에서 역할 기반 액세스 제어 계획](lync-server-2013-planning-for-role-based-access-control.md) 을 참조 하십시오.

포리스트 준비에서는 개인 및 공용 ACE를 모두 만듭니다. Lync Server에서 사용 하는 전역 설정 컨테이너에 개인 Ace를 만듭니다. 이 컨테이너는 Lync Server 에서만 사용 되며 전역 설정을 저장 하는 위치에 따라 루트 도메인의 구성 컨테이너나 시스템 컨테이너에 있습니다. 아래 표에 포리스트 준비에서 만들어지는 공용 ACE가 나와 있습니다.

### <a name="public-aces-created-by-forest-preparation"></a>포리스트 준비에서 만들어지는 공용 ACE

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
<td><p>루트 도메인 System 컨테이너 읽기(상속되지 않음)<strong>*</strong></p></td>
<td><p>X</p></td>
</tr>
<tr class="even">
<td><p>구성의 DisplaySpecifiers 컨테이너 읽기(상속되지 않음)</p></td>
<td><p>X</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <STRONG>*</STRONG>상속 되지 않은 Ace는 이러한 컨테이너의 하위 개체에 대 한 액세스 권한을 부여 하지 않습니다. 상속 된 Ace는 이러한 컨테이너 아래의 자식 개체에 대 한 액세스 권한을 부여 합니다.



</div>

구성 명명 컨텍스트 아래의 구성 컨테이너에서 포리스트 준비는 다음 작업을 수행합니다.

  - 사용자, 연락처 및 InetOrgPersons에 대한 언어 표시 지정(예: CN=user-Display,CN=409,CN=DisplaySpecifiers)의 adminContextMenu 및 adminPropertyPages 특성 아래에 **RTC property** 페이지의 항목 **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** 를 추가합니다.

  - **Extended-Rights** 아래에 User 및 Contact 클래스에 적용되는 **controlAccessRight** 유형의 **RTCPropertySet** 개체를 추가합니다.

  - **Extended-Rights** 아래에 User, Contact, OU 및 DomainDNS 클래스에 적용되는 **controlAccessRight** 유형의 **RTCUserSearchPropertySet** 개체를 추가합니다.

  - 각 언어 OU(조직 구성 단위) 표시 지정자(예: CN=organizationalUnit-Display,CN=409,CN=DisplaySpecifiers)의 **extraColumns** 특성 아래에 **msRTCSIP-PrimaryUserAddress**를 추가하고, 기본 표시(예: CN=default-Display, CN=409,CN=DisplaySpecifiers)의 **extraColumns** 특성 값을 복사합니다.

  - Users, Contacts 및 InetOrgPerson 개체에 대한 각 언어 표시 지정자(예: 영어인 경우 CN=user-Display,CN=409,CN=DisplaySpecifiers)의 **attributeDisplayNames** 특성 아래에 **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer** 및 **msRTCSIP-UserEnabled** 필터링 특성을 추가합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

