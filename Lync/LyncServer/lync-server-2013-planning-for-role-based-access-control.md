---
title: 'Lync Server 2013: 역할 기반 액세스 제어 계획'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for role-based access control (RBAC)
ms:assetid: 41204ba3-ce5b-41a8-a6c3-b444468fa328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425917(v=OCS.15)
ms:contentKeyID: 48183962
ms.date: 01/28/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d3e27f20d3a2b8b152b75e9c0760d38d7acafaff
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139309"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-role-based-access-control-in-lync-server-2013"></a>Lync Server 2013에서 역할 기반 액세스 제어 계획

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2015-01-27_

보안에 대 한 높은 표준을 유지 하면서 관리 작업을 위임할 수 있도록 하기 위해 Lync Server 2013에서는 RBAC (역할 기반 액세스 제어)를 제공 합니다. RBAC를 사용하면 사용자를 관리 역할에 지정하여 관리 권한을 부여할 수 있습니다. Lync Server 2013에는 다양 한 기본 제공 관리 역할 집합이 포함 되어 있으며, 새 역할을 만들고 각각의 새 역할에 대해 cmdlet의 사용자 지정 목록을 지정할 수도 있습니다. 또한 미리 정의된 RBAC 역할 및 사용자 지정 RBAC 역할 모두의 허용된 작업에 cmdlet 스크립트를 추가할 수도 있습니다.

<div>

## <a name="better-server-security-and-centralization"></a>향상된 서버 보안 및 중앙 집중화

RBAC에서는 액세스 및 권한 부여가 사용자의 Lync Server 역할을 정확히 기준으로 합니다. 따라서 "최소 권한"의 보안 원칙을 적용하고 관리자 및 사용자에게 해당 작업을 수행하는 데 필요한 권한만 부여할 수 있습니다.

<div>


> [!IMPORTANT]  
> RBAC 제한은 Lync Server 제어판 또는 Lync Server 관리 셸을 사용 하 여 원격으로 작동 하는 관리자 에게만 적용 됩니다. Lync Server를 실행 하는 서버에서 사용 하는 사용자는 RBAC에 따라 제한 되지 않습니다. 따라서 Lync Server의 물리적 보안은 RBAC 제한을 유지 하는 데 중요 합니다.



</div>

</div>

<div>

## <a name="roles-and-scope"></a>역할 및 범위

RBAC에서 *역할*은 특정 유형의 관리자 또는 기술자에게 유용하도록 디자인된 cmdlet 목록을 사용하도록 설정됩니다. *범위*는 역할에 정의된 cmdlet이 작업을 수행할 수 있는 개체 집합입니다. 이 범위의 영향을 받는 개체는 사용자 계정(조직 구성 단위별로 그룹화) 또는 서버(사이트별로 그룹화)일 수 있습니다.

다음 표에는 Lync Server의 미리 정의 된 역할과 각 역할에서 수행할 수 있는 작업 유형에 대 한 일반적인 개요가 나와 있습니다. 넷째 열에는 각 Lync Server 역할에 대 한 유사 Microsoft Exchange 서버 역할 (있는 경우)이 표시 됩니다.

### <a name="predefined-administrative-roles"></a>미리 정의된 관리 역할

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>역할</th>
<th>허용되는 작업</th>
<th>기본 Active Directory 그룹</th>
<th>해당 Exchange 역할</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CsAdministrator</p></td>
<td><p>모든 관리 작업을 수행하고 역할 만들기, 역할에 사용자 지정 등의 모든 설정을 수정할 수 있습니다. 새 사이트, 풀 및 서비스를 추가하여 배포를 확장할 수 있습니다.</p></td>
<td><p>CSAdministrator</p></td>
<td><p>조직 관리</p></td>
</tr>
<tr class="even">
<td><p>CsUserAdministrator</p></td>
<td><p>Lync Server에 대해 사용자를 사용 하거나 사용 하지 않도록 설정 하 고 사용자를 이동 하 고 기존 정책을 사용자에 게 할당할 수 있습니다. 정책을 수정할 수는 없습니다.</p></td>
<td><p>CSUserAdministrator</p></td>
<td><p>메일 받는 사람</p></td>
</tr>
<tr class="odd">
<td><p>CsVoiceAdministrator</p></td>
<td><p>음성 관련 설정 및 정책을 만들고 구성하고 관리할 수 있습니다.</p></td>
<td><p>CSVoiceAdministrator</p></td>
<td><p>해당 없음</p></td>
</tr>
<tr class="even">
<td><p>CsServerAdministrator</p></td>
<td><p>서버 및 서비스를 관리 및 모니터링하고 관련 문제를 해결할 수 있습니다. 서버에 대한 새 연결을 방지하고, 서비스를 시작하거나 중지하고, 소프트웨어 업데이트를 적용할 수 있습니다. 전역 구성에 영향을 주는 변경 작업은 수행할 수 없습니다.</p></td>
<td><p>CSServerAdministrator</p></td>
<td><p>서버 관리</p></td>
</tr>
<tr class="odd">
<td><p>CsViewOnlyAdministrator</p></td>
<td><p>사용자 및 서버 정보를 포함하여 배포를 보고 배포 상태를 모니터링할 수 있습니다.</p></td>
<td><p>CSViewOnlyAdministrator</p></td>
<td><p>보기 전용 조직 관리</p></td>
</tr>
<tr class="even">
<td><p>CsHelpDesk</p></td>
<td><p>사용자의 속성 및 정책을 포함하여 배포를 볼 수 있으며, 특정 문제 해결 작업을 실행할 수 있습니다. 사용자 속성 또는 정책, 서버 구성 또는 서비스를 변경할 수는 없습니다.</p></td>
<td><p>CSHelpDesk</p></td>
<td><p>HelpDesk</p></td>
</tr>
<tr class="odd">
<td><p>CsArchivingAdministrator</p></td>
<td><p>보관 구성 및 정책을 수정할 수 있습니다.</p></td>
<td><p>CSArchivingAdministrator</p></td>
<td><p>보유 관리, 법적 보유</p></td>
</tr>
<tr class="even">
<td><p>CsResponseGroupAdministrator</p></td>
<td><p>사이트 내에서 응답 그룹 응용 프로그램 구성을 관리할 수 있습니다.</p></td>
<td><p>CSResponseGroupAdministrator</p></td>
<td><p>해당 없음</p></td>
</tr>
<tr class="odd">
<td><p>CsLocationAdministrator</p></td>
<td><p>E9-1-1(Enhanced 9-1-1) 위치 및 네트워크 식별자를 만들고 서로 연결하는 등 E9-1-1 관리에 대한 최하위 수준의 권한을 가집니다. 이 역할은 항상 전역 범위로 지정됩니다.</p></td>
<td><p>CSLocationAdministrator</p></td>
<td><p>해당 없음</p></td>
</tr>
<tr class="even">
<td><p>CsResponseGroupManager</p></td>
<td><p>특정 응답 그룹을 관리할 수 있습니다.</p></td>
<td><p>CSResponseGroupManager</p></td>
<td><p>해당 없음</p></td>
</tr>
<tr class="odd">
<td><p>CsPersistentChatAdministrator</p></td>
<td><p>영구 채팅 기능 및 특정 영구 채팅방을 관리할 수 있습니다.</p></td>
<td><p>CSPersistentChatAdministrator</p></td>
<td><p>해당 없음</p></td>
</tr>
</tbody>
</table>


Lync Server에서 제공 되는 미리 정의 된 모든 역할에는 전역 범위가 있습니다. 최소 권한 원칙을 따르기 위해서는 제한된 서버 또는 사용자 집합만 관리하려는 경우 전체 범위로 설정된 역할에 사용자를 지정해서는 안됩니다. 이를 위해서는 기존 역할을 기반으로 하지만 보다 제한된 범위를 갖는 역할을 만들 수 있습니다.

<div>

## <a name="creating-a-scoped-role"></a>범위가 지정된 역할 만들기

제한된 범위를 갖는 역할(범위가 지정된 역할)을 만들 때는 역할의 기반이 되는 기존 역할 및 역할에 지정할 Active Directory 그룹과 함께 범위를 지정합니다. 지정하는 Active Directory 그룹은 이미 만들어져 있어야 합니다. 다음 cmdlet은 미리 정의된 관리 역할 중 하나의 권한을 갖지만 범위가 제한된 역할을 만드는 예를 보여줍니다. 라는 `Site01 Server Administrators`새 역할을 만듭니다. 이 역할은 미리 정의된 CsServerAdministrator 역할의 기능을 갖지만 Site01 사이트에 있는 서버로만 범위가 제한됩니다. 이 cmdlet이 작동 하려면 Site01 사이트가 이미 정의 되어 있어야 하며, 라는 `Site01 Server Administrators` 유니버설 보안 그룹이 있어야 합니다.

    New-CsAdminRole -Identity "Site01 Server Administrators" -Template CsServerAdministrator -ConfigScopes "site:Site01"

이 cmdlet이 실행 된 후에는 `Site01 Server Administrators` 그룹의 구성원 인 모든 사용자에 게 Site01 서버에 대 한 서버 관리자 권한이 부여 됩니다. 또한 나중에이 유니버설 보안 그룹에 추가 되는 모든 사용자는이 역할의 권한을 얻게 됩니다. 역할 자체와 자신에 게 할당 된 유니버설 보안 그룹이 호출 `Site01 Server Administrators`된다는 점에 유의 하십시오.

다음 예에서는 서버 범위 대신 사용자 범위를 제한합니다. 영업 조직 구성 `Sales Users Administrator` 단위에서 사용자 계정을 관리 하는 역할을 만듭니다. 이 cmdlet이 작동 하려면 Sales사용자 관리자 유니버설 보안 그룹이 이미 만들어져 있어야 합니다.

    New-CsAdminRole -Identity "Sales Users Administrator " -Template CsUserAdministrator -UserScopes "OU:OU=Sales, OU=Lync Tenants, DC=Domain, DC=com"

</div>

<div>

## <a name="creating-a-new-role"></a>새 역할 만들기

미리 정의된 역할 중에서 찾을 수 없는 cmdlet 집합에 액세스하거나 스크립트 또는 모듈 집합에 액세스하는 역할을 만들려는 경우에도 미리 정의된 역할 중 하나를 템플릿으로 사용해서 작업을 시작합니다. 역할이 실행할 수 있어야 하는 스크립트 및 모듈은 다음 위치에 저장되어 있어야 합니다.

  - Lync\\모듈 경로 (기본적으로 C: 프로그램 파일\\공용 파일\\) Microsoft lync Server 2013\\Modules Lync\\

  - 사용자 스크립트\\경로 (기본적으로 C: Program Files\\Common files\\Microsoft Lync Server 2013 \adminscripts\\

새 역할을 만들려면 **New-CsAdminRole** cmdlet을 사용합니다. **새-CsAdminRole**을 실행 하기 전에 먼저이 역할과 연결 될 기본 유니버설 보안 그룹을 만들어야 합니다.

다음 cmdlet은 새 역할을 만드는 예를 보여줍니다. 라는 `MyHelpDeskScriptRole`새 역할 유형을 만듭니다. 이 새 역할은 미리 정의된 CsHelpDesk 역할의 기능을 포함하며 추가적으로 “testscript”라는 스크립트의 기능을 실행할 수 있습니다.

    New-CsAdminRole -Identity "MyHelpDeskScriptRole" -Template CsHelpDesk -ScriptModules @{Add="testScript.ps1"}

이 cmdlet이 작동 하려면 먼저 유니버설 보안 그룹 MyHelpDeskScriptRole를 만들어야 합니다.

이 cmdlet이 실행된 후에는 이 역할에 사용자를 직접 지정하거나(전역 범주를 갖는 경우), 이 문서의 앞 부분에 있는 범위가 지정된 역할 만들기에서 설명한 대로 이 역할을 기반으로 범위가 지정된 역할을 만들 수 있습니다.

</div>

<div>

## <a name="assigning-roles-to-users"></a>사용자에게 역할 지정

각 Lync Server 역할은 기본 Active Directory 유니버설 보안 그룹과 연결 됩니다. 기본 그룹에 추가하는 모든 사용자는 해당 역할의 기능을 갖습니다.

이전 섹션의 예에서는 새 역할을 만들고 기존 유니버설 보안 그룹을 새 역할에 할당 했습니다. 한 명 이상의 사용자에게 기존 역할을 지정하려면 해당 역할과 연결된 그룹에 사용자를 추가합니다. 개별 사용자와 유니버설 보안 그룹을 모두 이러한 그룹에 추가할 수 있습니다.

예를 들어 **Csadministrator** 역할은 Active Directory의 **CS Administrators** 유니버설 보안 그룹에 자동으로 부여 됩니다. 이 유니버설 보안 그룹은 Lync Server를 배포할 때 Active Directory에 만들어집니다. 사용자 또는 그룹에 이 권한을 부여하려면 해당 사용자 또는 그룹을 **CS Administrators** 그룹에 추가하기만 하면 됩니다.

각 역할에 해당하는 기본 Active Directory 그룹에 사용자를 추가하여 사용자에게 여러 RBAC 역할을 부여할 수 있습니다.

역할을 만든 경우 기본 Active Directory 그룹에 나중에 추가되는 사용자에게도 해당 역할의 권한이 부여됩니다.

</div>

<div>

## <a name="modifying-the-abilities-of-a-role"></a>역할의 기능 수정

역할이 실행할 수 있는 cmdlet 및 스크립트 목록을 수정할 수 있습니다. 사용자 지정 역할이 실행할 수 있는 cmdlet 및 스크립트를 모두 수정할 수 있지만 미리 정의된 역할의 경우 스크립트만 수정할 수 있습니다. 입력하는 각 cmdlet은 cmdlet 또는 스크립트를 추가, 제거 또는 대체할 수 있습니다.

역할을 수정하려면 **Set-CsAdminRole** cmdlet을 사용합니다. 다음 cmdlet은 역할에서 스크립트 하나를 제거 합니다.

    Set-CsAdminRole -Identity "MyHelpDeskScriptRole" -ScriptModules @{Remove="testScript.ps1"}

</div>

</div>

<div>

## <a name="planning-for-rbac"></a>RBAC 계획

Lync Server 배포에 대 한 관리 권한을 부여할 각 사용자에 대해 수행 해야 하는 작업을 정확 하 게 고려 하 고 작업에 필요한 최소 권한 및 범위를 가진 역할에 할당 합니다. 필요에 따라 **Set-CsAdminRole** cmdlet을 사용해서 이 사용자의 작업에 필요한 cmdlet만 포함된 새 역할을 만들 수 있습니다.

CsAdministrator 역할을 가진 사용자는 CsAdministrator를 기반으로 하는 역할을 포함하여 모든 유형의 역할을 만들고 각 역할에 사용자를 지정할 수 있습니다. 따라서 신뢰할 수 있는 소수의 사용자에게만 CsAdministrator 역할을 지정하는 것이 좋습니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

