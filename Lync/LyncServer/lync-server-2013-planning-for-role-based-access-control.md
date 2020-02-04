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
ms.openlocfilehash: b89e4bdc075783d33bebcfb85398b1b627e1bf1c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41750478"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-role-based-access-control-in-lync-server-2013"></a>Lync Server 2013의 역할 기반 액세스 제어 계획

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2015-01-27_

보안을 위해 높은 표준을 유지 하면서 관리 작업을 위임할 수 있도록 Lync Server 2013는 RBAC (역할 기반 액세스 제어)를 제공 합니다. RBAC를 사용 하는 경우 관리 역할에 사용자를 할당 하 여 관리 권한을 부여 받습니다. Lync Server 2013에는 다양 한 기본 제공 관리 역할이 포함 되어 있으며 새 역할을 만들고 새 역할에 대 한 cmdlet의 사용자 지정 목록을 지정할 수도 있습니다. 또한 미리 정의된 RBAC 역할 및 사용자 지정 RBAC 역할 둘 다에 대해 허용되는 작업에 cmdlet 스크립트를 추가할 수도 있습니다.

<div>

## <a name="better-server-security-and-centralization"></a>향상 된 서버 보안 및 중앙 집중화

RBAC를 사용 하는 경우 액세스 및 권한 부여는 사용자의 Lync 서버 역할에 정확히 따라 달라 집니다. 이렇게 하면 관리자와 사용자에 게 해당 작업에 필요한 권한만 부여 하는 "최소 권한"의 보안 방법을 사용할 수 있습니다.

<div>


> [!IMPORTANT]  
> RBAC 제한은 Lync Server 제어판 또는 Lync Server Management Shell을 사용 하 여 원격으로 작동 하는 관리자만 사용할 수도 있습니다. Lync Server를 실행 하는 서버에 앉아 있는 사용자는 RBAC에 의해 제한 되지 않습니다. 따라서 Lync 서버의 물리적 보안은 RBAC 제한을 유지 하는 것이 중요 합니다.



</div>

</div>

<div>

## <a name="roles-and-scope"></a>역할 및 범위

RBAC에서는 특정 유형의 관리자 또는 기술자에 게 유용 하도록 디자인 된 cmdlet 목록을 사용 하도록 *역할이* 설정 됩니다. *범위* 는 역할에 정의 된 cmdlet이 작동할 수 있는 개체 집합입니다. 범위에 영향을 주는 개체는 사용자 계정 (조직 단위에 따라 그룹화) 또는 서버 (사이트별로 그룹화 됨) 일 수 있습니다.

다음 표에는 Lync Server에 미리 정의 된 역할이 나열 되어 있으며 각 역할에 대해 수행할 수 있는 작업 유형에 대 한 일반적인 개요를 제공 합니다. 네 번째 열에는 각 Lync Server 역할 (있는 경우)에 대 한 유사한 Microsoft Exchange Server 역할이 표시 됩니다.

### <a name="predefined-administrative-roles"></a>미리 정의 된 관리 역할

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
<th>허용 된 작업</th>
<th>기본 Active Directory 그룹</th>
<th>교환 동급</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CsAdministrator</p></td>
<td><p>역할 만들기 및 역할에 사용자 지정 등 모든 관리 작업을 수행 하 고 모든 설정을 수정할 수 있습니다. 새 사이트, 풀 및 서비스를 추가 하 여 배포를 확장할 수 있습니다.</p></td>
<td><p>CSAdministrator</p></td>
<td><p>조직 관리</p></td>
</tr>
<tr class="even">
<td><p>CsUserAdministrator</p></td>
<td><p>Lync Server 사용자를 사용 하거나 사용 하지 않도록 설정 하 고 사용자를 이동 하 고 기존 정책을 사용자에 게 할당할 수 있습니다. 정책을 수정할 수 없습니다.</p></td>
<td><p>CSUserAdministrator</p></td>
<td><p>메일 받는 사람</p></td>
</tr>
<tr class="odd">
<td><p>CsVoiceAdministrator</p></td>
<td><p>음성 관련 설정 및 정책을 만들고, 구성 하 고, 관리할 수 있습니다.</p></td>
<td><p>CSVoiceAdministrator</p></td>
<td><p>해당 없음</p></td>
</tr>
<tr class="even">
<td><p>CsServerAdministrator</p></td>
<td><p>서버 및 서비스를 관리 하 고 모니터링 하 고 문제를 해결할 수 있습니다. 서버에 대 한 새 연결을 방지 하 고 서비스를 중지 및 시작 하 고 소프트웨어 업데이트를 적용할 수 있습니다. 전역 구성 영향을 변경 하 여 변경할 수 없습니다.</p></td>
<td><p>CSServerAdministrator</p></td>
<td><p>서버 관리</p></td>
</tr>
<tr class="odd">
<td><p>Csviewadministrator</p></td>
<td><p>배포 상태를 모니터링 하기 위해 사용자 및 서버 정보를 포함 하 여 배포를 볼 수 있습니다.</p></td>
<td><p>Csviewadministrator</p></td>
<td><p>보기 전용 조직 관리</p></td>
</tr>
<tr class="even">
<td><p>CsHelpDesk</p></td>
<td><p>사용자의 속성 및 정책을 포함 하 여 배포를 볼 수 있습니다. 특정 문제 해결 작업을 실행할 수 있습니다. 사용자 속성 또는 정책, 서버 구성 또는 서비스를 변경할 수 없습니다.</p></td>
<td><p>CSHelpDesk</p></td>
<td><p>기술</p></td>
</tr>
<tr class="odd">
<td><p>CsArchivingAdministrator</p></td>
<td><p>보관 구성 및 정책을 수정할 수 있습니다.</p></td>
<td><p>CSArchivingAdministrator</p></td>
<td><p>보존 관리, 법률 보류</p></td>
</tr>
<tr class="even">
<td><p>CsResponseGroupAdministrator</p></td>
<td><p>사이트 내에서 응답 그룹 응용 프로그램의 구성을 관리할 수 있습니다.</p></td>
<td><p>CSResponseGroupAdministrator</p></td>
<td><p>해당 없음</p></td>
</tr>
<tr class="odd">
<td><p>CsLocationAdministrator</p></td>
<td><p>9-1-1-1-1 위치 및 네트워크 식별자 만들기, 그리고 서로 연결을 비롯 한 향상 된 (E9-1) 관리 수준의 최소 권한입니다. 이 역할은 항상 전역 범위를 사용 하 여 할당 됩니다.</p></td>
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


Lync Server에 제공 되는 미리 정의 된 모든 역할에는 전역 범위가 있습니다. 최소 권한 사례를 따르려면 제한 된 서버 또는 사용자만 관리 하려는 경우 전역 범위를 사용 하 여 역할에 사용자를 할당 하지 않아야 합니다. 이 작업을 수행 하려면 기존 역할에 기반을 둔 역할을 만들 수 있지만 범위가 제한 됩니다.

<div>

## <a name="creating-a-scoped-role"></a>범위 역할 만들기

제한 된 범위 (범위 역할)를 사용 하 여 역할을 만드는 경우 범위를 기반으로 하는 기존 역할과 역할을 할당할 Active Directory 그룹을 지정 합니다. 사용자가 지정한 Active Directory 그룹을 이미 만들어야 합니다. 다음 cmdlet은 미리 정의 된 관리 역할 중 하나의 권한을 가진 역할을 만드는 예 이며 범위가 제한 됩니다. 새 역할을 만듭니다 `Site01 Server Administrators`. 역할에는 미리 정의 된 CsServerAdministrator 역할의 기능이 있지만, Site01 사이트에 있는 서버에만 해당 됩니다. 이 cmdlet이 작동 하려면 Site01 사이트를 이미 정의 하 고 명명 된 `Site01 Server Administrators` 유니버설 보안 그룹이 이미 존재 해야 합니다.

    New-CsAdminRole -Identity "Site01 Server Administrators" -Template CsServerAdministrator -ConfigScopes "site:Site01"

이 cmdlet을 실행 한 후에는 `Site01 Server Administrators` 그룹의 구성원 인 모든 사용자에 게 Site01의 서버에 대 한 서버 관리자 권한이 부여 됩니다. 또한 나중에이 유니버설 보안 그룹에 추가 되는 사용자도이 역할의 권한을 얻을 수 있습니다. 역할 자체와 자신에 게 할당 된 유니버설 보안 그룹이 호출 `Site01 Server Administrators`되는지 확인 합니다.

다음 예제에서는 서버 범위 대신 사용자 범위를 제한 합니다. 이는 영업 `Sales Users Administrator` 조직 구성 단위에서 사용자 계정을 관리 하는 역할을 만듭니다. 이 cmdlet을 사용 하려면 Sales Administrator 유니버설 보안 그룹을 이미 만들어야 합니다.

    New-CsAdminRole -Identity "Sales Users Administrator " -Template CsUserAdministrator -UserScopes "OU:OU=Sales, OU=Lync Tenants, DC=Domain, DC=com"

</div>

<div>

## <a name="creating-a-new-role"></a>새 역할 만들기

미리 정의 된 역할 중 하나 또는 스크립트 또는 모듈 집합에 없는 cmdlet 집합에 액세스할 수 있는 역할을 만들려면 미리 정의 된 역할 중 하나를 템플릿으로 사용 하 여 다시 시작 합니다. 역할을 실행할 수 있는 스크립트와 모듈은 다음 위치에 저장 되어 있어야 합니다.

  - Lync\\모듈 경로-기본적으로 C: 프로그램 파일\\공통 파일\\Microsoft lync Server 2013\\모듈 Lync\\

  - 사용자 스크립트\\경로-기본적으로 C: 프로그램 파일\\공통 파일\\Microsoft Lync Server 2013 AdminScripts\\

새 역할을 만들려면 **새 CsAdminRole** cmdlet을 사용 합니다. **새-CsAdminRole**을 실행 하기 전에 먼저이 역할과 연결 될 기본 유니버설 보안 그룹을 만들어야 합니다.

다음 cmdlet은 새 역할을 만드는 예제 역할을 합니다. 라는 `MyHelpDeskScriptRole`새 역할 유형을 만듭니다. 새 역할에는 미리 정의 된 CsHelpDesk 역할의 기능이 있으며 "testscript" 라는 스크립트에서 함수를 추가로 실행할 수 있습니다.

    New-CsAdminRole -Identity "MyHelpDeskScriptRole" -Template CsHelpDesk -ScriptModules @{Add="testScript.ps1"}

이 cmdlet이 제대로 작동 하려면 먼저 유니버설 보안 그룹 MyHelpDeskScriptRole를 만들어야 합니다.

이 cmdlet을 실행 한 후에는이 역할에 사용자를 직접 할당 하거나 (전역 범위를 포함 하는 경우)이 역할을 기반으로 하는 범위 역할을 만들 수 있습니다 (이 경우에는이 문서의 이전에 범위 역할을 만들 때 설명).

</div>

<div>

## <a name="assigning-roles-to-users"></a>사용자에 게 역할 지정

각 Lync Server 역할이 기본 Active Directory 유니버설 보안 그룹과 연결 되어 있습니다. 기본 그룹에 추가 하는 모든 사용자는 해당 역할의 기능을 얻게 됩니다.

이전 섹션의 예제에서는 새 역할을 만들고 기존 유니버설 보안 그룹을 새 역할에 할당 했습니다. 한 명 이상의 사용자에 게 기존 역할을 할당 하려면 해당 사용자를 역할과 연결 된 그룹에 추가 합니다. 개별 사용자와 유니버설 보안 그룹을 이러한 그룹에 추가할 수 있습니다.

예를 들어 **Csadministrator** 역할은 Active Directory의 **CS 관리자** 유니버설 보안 그룹에 자동으로 부여 됩니다. 이 유니버설 보안 그룹은 Lync Server를 배포할 때 Active Directory에 만들어집니다. 사용자 또는 그룹에 게이 권한을 부여 하려면, 간단히 **CS 관리자** 그룹에 추가 하면 됩니다.

각 역할에 해당 하는 기본 Active Directory 그룹에 추가 되는 여러 RBAC 역할이 사용자에 게 제공 될 수 있습니다.

역할을 만들 때 나중에 기본 Active Directory 그룹에 추가 되는 사용자는 해당 역할의 기능을 얻게 된다는 점에 유의 하세요.

</div>

<div>

## <a name="modifying-the-abilities-of-a-role"></a>역할의 기능 수정

역할이 실행할 수 있는 cmdlet 및 스크립트 목록을 수정할 수 있습니다. 사용자 지정 역할이 실행할 수 있는 cmdlet 및 스크립트를 수정할 수 있지만 미리 정의 된 역할에 대 한 스크립트만 수정할 수 있습니다. 입력 하는 각 cmdlet은 cmdlet 또는 스크립트를 추가, 제거 또는 대체할 수 있습니다.

역할을 수정 하려면 **Set-CsAdminRole** cmdlet을 사용 합니다. 다음 cmdlet은 역할에서 하나의 스크립트를 제거 합니다.

    Set-CsAdminRole -Identity "MyHelpDeskScriptRole" -ScriptModules @{Remove="testScript.ps1"}

</div>

</div>

<div>

## <a name="planning-for-rbac"></a>RBAC에 대 한 계획

Lync Server 배포에 대 한 모든 종류의 관리자 권한을 부여할 각 사용자에 대해 수행 해야 하는 작업을 정확히 고려 하 고 해당 작업에 필요한 최소 권한 및 범위를 가진 역할에 할당 합니다. 필요한 경우 **Set-CsAdminRole** cmdlet을 사용 하 여이 사용자의 작업에 필요한 cmdlet만 사용 하 여 새 역할을 만들 수 있습니다.

CsAdministrator 역할이 있는 사용자는 CsAdministrator를 기반으로 하는 역할을 포함 하 여 모든 유형의 역할을 만들고 사용자에 게 할당할 수 있습니다. 가장 좋은 방법은 신뢰할 수 있는 사용자의 소규모 집합에 CsAdministrator 역할을 할당 하는 것입니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

