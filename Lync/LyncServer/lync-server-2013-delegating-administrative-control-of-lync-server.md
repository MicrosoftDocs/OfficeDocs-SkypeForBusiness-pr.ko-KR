---
title: 'Lync Server 2013: Lync Server 관리 권한 위임'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delegating administrative control of Lync Server 2013
ms:assetid: 0f378eff-8ef4-4c60-9fd2-67d7ee259ef8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520951(v=OCS.15)
ms:contentKeyID: 48183418
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 134d5a4abae1173cc1d74cecb876951cea6d72c1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739818"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delegating-administrative-control-of-lync-server-2013"></a>Lync Server 2013 관리 권한 위임

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-22_

Lync Server 2013에서 관리 작업은 새 RBAC (역할 기반 액세스 제어) 기능을 사용 하 여 사용자에 게 위임 됩니다. Lync Server를 설치할 때 여러 개의 RBAC 역할이 만들어집니다. 이러한 역할은 Active Directory 도메인 서비스의 유니버설 보안 그룹에 해당 합니다. 예를 들어 RBAC 역할 CsHelpDesk는 Active Directory 도메인 서비스의 사용자 컨테이너에 있는 CsHelpDesk 그룹에 해당 합니다. 또한 각 RBAC 역할은 Lync Server Windows PowerShell cmdlet 집합과 연결 되어 있습니다. 이러한 cmdlet은 지정 된 RBAC 역할을 할당 받은 사용자가 수행할 수 있는 작업을 나타냅니다. 예를 들어 CsHelpDesk 역할에 잠금 CsClientPin과 UnlockCsClientPin cmdlet이 할당 되었습니다. 즉, CsHelpDesk 역할이 할당 된 사용자는 사용자 PIN 번호를 잠그고 잠금을 해제할 수 있습니다. 그러나 CsHelpDesk 역할에 새 CsVoicePolicy cmdlet이 할당 되지 않았습니다. 즉, CsHelpDesk 역할을 할당 받은 사용자는 새 음성 정책을 만들 수 없습니다.

<div>

## <a name="viewing-information-about-rbac-roles"></a>RBAC 역할에 대 한 정보 보기

Lync Server Management Shell 내에서 다음 명령을 실행 하 여 RBAC 역할에 대 한 기본 정보를 검색할 수 있습니다.

    Get-CsAdminRole

RBAC 역할 (예: CsVoiceAdministrator)의 Id에는 Active Directory 도메인 서비스의 사용자 컨테이너에 있는 보안 그룹에 대 한 직접 매핑이 포함 되어 있다는 점에 유의 하세요.

역할에 할당 된 cmdlet 목록을 보려면 다음과 같은 명령을 사용 합니다.

    Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets

</div>

<div>

## <a name="assigning-an-rbac-role-to-a-user"></a>사용자에 게 RBAC 역할 할당

사용자에 게 RBAC 역할을 할당 하려면 해당 사용자를 적절 한 Active Directory 보안 그룹에 추가 해야 합니다. 예를 들어 CsLocationAdministrator 역할을 사용자에 게 할당 하려면 해당 사용자를 CsLocationAdministrator 그룹에 추가 해야 합니다. 다음 절차를 수행 하 여이 작업을 수행할 수 있습니다.

**보안 그룹에 사용자를 할당 하려면**

1.  Active Directory 그룹의 구성원 자격을 수정할 권한이 있는 계정을 사용 하 여 Active Directory 사용자 및 컴퓨터가 설치 된 컴퓨터에 로그온 합니다.

2.  **시작**을 클릭 하 고 **모든 프로그램**을 클릭 한 다음 **관리 도구**를 클릭 하 고 **Active Directory 사용자 및 컴퓨터**를 클릭 합니다.

3.  Active Directory 사용자 및 컴퓨터에서 도메인의 이름을 확장 하 고 **사용자** 컨테이너를 클릭 합니다.

4.  보안 그룹 **Cslocationadministrator**를 마우스 오른쪽 단추로 클릭 한 다음 **속성**을 클릭 합니다.

5.  **속성** 대화 상자의 **구성원** 탭에서 **추가**를 클릭 합니다.

6.  **사용자, 컴퓨터, 연락처 또는 그룹 선택** 대화 상자에서 그룹에 추가할 사용자의 사용자 이름 또는 표시 이름 (예: **: 진구 Myer**)을 입력 하 고 **확인** **을** 클릭 합니다.

7.  **속성** 대화 상자에서 **확인**을 클릭 합니다.

RBAC 역할이 할당 되었는지 확인 하려면 [Get-CsAdminRoleAssignment 할당](https://docs.microsoft.com/powershell/module/skype/Get-CsAdminRoleAssignment) cmdlet을 사용 하 여 cmdlet을 사용자의 SamAccountName (Active Directory 로그온 이름)으로 전달 합니다. 예를 들어 Lync Server Management Shell 내에서 다음 명령을 실행 합니다.

    Get-CsAdminRoleAssignment  -Identity "kenmyer"

</div>

</div>

<span> </span>

</div>

</div>

</div>

