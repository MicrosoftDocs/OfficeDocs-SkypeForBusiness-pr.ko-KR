---
title: 'Lync Server 2013: 컴퓨터, 사용자 또는 InetOrgPerson 컨테이너에서 사용 권한 상속이 비활성화 됨'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers
ms:assetid: c472ad21-a93d-4fcb-a3d9-60a2134a87fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412970(v=OCS.15)
ms:contentKeyID: 48185348
ms.date: 12/19/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1340c76209667d705908f5012a8182eaf1c7c4cb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006926"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers-in-lync-server-2013"></a>Lync Server 2013의 컴퓨터, 사용자 또는 InetOrgPerson 컨테이너에서 사용 권한 상속이 비활성화 됨

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-12-19_

잠긴 Active Directory 도메인 서비스에서 사용자 및 컴퓨터 개체는 사용 권한 상속이 사용 하지 않도록 설정 된 특정 Ou (조직 구성 단위)에 포함 되는 경우가 많고, 관리 위임을 보호 하 고 Gpo (그룹 정책 개체)를 사용 하도록 설정 하는 데 도움이 됩니다. 보안 정책을 적용 하기 위해

도메인 준비 및 서버 정품 인증 Lync Server 2013에 필요한 Ace (액세스 제어 항목)를 설정 합니다. 사용 권한 상속이 사용 하지 않도록 설정 된 경우 Lync Server 보안 그룹은 이러한 Ace를 상속할 수 없습니다. 이러한 사용 권한이 상속 되지 않으면 Lync Server 보안 그룹은 설정에 액세스할 수 없으며 다음과 같은 두 가지 문제가 발생 합니다.

  - 사용자, InetOrgPersons 및 연락처를 관리 하 고 서버를 운영 하려면 Lync Server 보안 그룹에 각 사용자의 속성 집합, RTC (실시간 통신), RTC 사용자 검색 및 공용 정보에 대 한 도메인 준비 절차에 따라 설정 된 Ace가 필요 합니다. . 사용 권한 상속이 비활성화되면 보안 그룹이 이러한 ACE를 상속하지 못하며 서버나 사용자를 관리할 수 없습니다.

  - 서버 및 풀을 검색 하려면 Lync Server를 실행 하는 서버가 Microsoft 컨테이너 및 서버 개체를 포함 하는 컴퓨터 관련 개체에서 정품 인증을 통해 설정 된 Ace를 사용 합니다. 사용 권한 상속이 비활성화되면 보안 그룹, 서버 및 풀이 이러한 ACE를 상속하지 않으므로 이러한 ACE를 활용할 수 없습니다.

이러한 문제를 해결 하기 위해 Lync Server에서는 **부여-CsOuPermission** cmdlet을 제공 합니다. 이 cmdlet은 지정 된 컨테이너와 조직 단위 및 컨테이너 또는 조직 단위 내의 개체에 대해 필요한 Lync Server Ace를 직접 설정 합니다.

<div>

## <a name="set-permissions-for-user-inetorgperson-and-contact-objects-after-running-domain-preparation"></a>도메인 준비 실행 후 사용자, InetOrgPerson 및 연락처 개체에 대한 사용 권한 설정

사용 권한 상속이 비활성화된 경우 잠겨 있는 Active Directory 환경에서는 도메인 준비 중에 도메인 내의 사용자 또는 InetOrgPerson 개체를 보유하는 컨테이너나 조직 구성 단위에 대해 필요한 ACE가 설정되지 않습니다. 이 상황에서는 사용 권한 상속이 비활성화된 사용자 또는 InetOrgPerson 개체가 있는 각 컨테이너나 OU에 대해 **Grant-CsOuPermission** cmdlet를 실행해야 합니다. 중앙 포리스트 토폴로지가 있는 경우 대화 상대 개체를 보유하는 컨테이너나 OU에 대해서도 이 절차를 수행해야 합니다. 중앙 포리스트 토폴로지에 대 한 자세한 내용은 지원 가능성 설명서의 [Lync Server 2013에서 지 원하는 Active Directory 토폴로지](lync-server-2013-supported-active-directory-topologies.md) 를 참조 하세요. ObjectType 매개 변수는 개체 유형을 지정합니다. OU 매개 변수는 조직 구성 단위를 지정합니다.

이 cmdlet는 지정된 컨테이너나 OU 및 컨테이너 내의 사용자 또는 InetOrgPerson 개체에 대해 필요한 ACE를 직접 추가합니다. 이 명령이 실행 되는 OU에 User 또는 InetOrgPerson 개체가 있는 하위 Ou가 있으면 해당 권한이 해당 개체에 적용 되지 않습니다. 각 하위 OU에서 개별적으로이 명령을 실행 해야 합니다. 이것은 Lync 호스팅 배포 (예: 상위 OU = OCS 테 넌 트, DC = CONTOSO, DC = LOCAL 및 child OU = Tenant1, OU = OCS 테 넌 트, dc = LOCAL)와 같은 일반적인 시나리오입니다.

이 cmdlet를 실행하려면 Domain Admins 그룹의 구성원 자격과 동등한 사용자 권한이 필요합니다. 인증 된 사용자 Ace도 잠긴 환경에서 제거 된 경우에는 [Lync Server 2013에서 인증 된 사용자 사용 권한을 제거](lync-server-2013-authenticated-user-permissions-are-removed.md) 하거나 Enterprise Admins 그룹의 구성원 인 계정을 사용 하 여 포리스트 루트 도메인의 관련 컨테이너나 ou에 대 한 읽기 액세스 ace를이 계정에 부여 해야 합니다.

**사용자, InetOrgPerson 및 연락처 개체에 대해 필요한 ACE를 설정하려면**

1.  Domain Admins 그룹의 구성원이거나 이와 동등한 사용자 권한을 가진 계정을 사용하여 도메인에 가입된 컴퓨터에 로그온합니다.

2.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

3.  를 실행합니다.
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    Domain 매개 변수를 지정하지 않는 경우에는 로컬 도메인이 기본값으로 사용됩니다.
    
    예:
    
        Grant-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net"

4.  로그 파일에서 각 작업 끝에 ** \<있는\> 성공** 실행 결과를 찾아서 사용 권한이 설정 되었는지 확인 한 다음 로그 창을 닫습니다. 또는 다음 명령을 실행하여 사용 권한이 설정되었는지 확인할 수 있습니다.
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>] [-Report <fully qualified path and name of file to create>]
    
    예를 들면 다음과 같습니다.
    
        Test-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net" -Report "C:\Log\OUPermissionsTest.html"

</div>

<div>

## <a name="set-permissions-for-computer-objects-after-running-domain-preparation"></a>도메인 준비 실행 후 컴퓨터 개체에 대한 사용 권한 설정

사용 권한 상속이 비활성화된 경우 잠겨 있는 Active Directory 환경에서는 도메인 준비 중에 도메인 내의 컴퓨터 개체를 보유하는 컨테이너나 OU에 대해 필요한 ACE가 설정되지 않습니다. 이러한 상황에서는 사용 권한 상속이 사용 하지 않도록 설정 된 Lync Server를 실행 하는 컴퓨터가 있는 각 컨테이너 또는 OU에서 **Grant-CsOuPermission** cmdlet을 실행 해야 합니다. ObjectType 매개 변수는 개체 유형을 지정합니다.

이 절차는 지정된 컨테이너에 대해 필요한 ACE를 직접 추가합니다.

이 cmdlet를 실행하려면 Domain Admins 그룹의 구성원 자격과 동등한 사용자 권한이 필요합니다. 인증 된 사용자 Ace도 제거 된 경우에는 [Lync Server 2013에서 인증 된 사용자 사용 권한을 제거](lync-server-2013-authenticated-user-permissions-are-removed.md) 하거나 Enterprise Admins 그룹의 구성원 인 계정을 사용 하 여 포리스트 루트 도메인의 관련 컨테이너에 대해이 계정에 대 한 읽기 액세스 ace를 부여 해야 합니다.

**컴퓨터 개체에 대해 필요한 ACE를 설정하려면**

1.  Domain Admins 그룹의 구성원이거나 이와 동등한 사용자 권한을 가진 계정을 사용하여 도메인 컴퓨터에 로그온합니다.

2.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

3.  를 실행합니다.
    
        Grant-CsOuPermission -ObjectType <Computer> 
        -OU <DN name for the computer OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>][-Report <fully qualified path and name of output report>]
    
    Domain 매개 변수를 지정하지 않는 경우에는 로컬 도메인이 기본값으로 사용됩니다.
    
    예:
    
        Grant-CsOuPermission -ObjectType "Computer" -OU "ou=Lync Servers,dc=litwareinc,dc=com" -Report "C:\Logs\OUPermissions.xml"

4.  예제 로그 파일 C:\\로그\\의 사용 권한 xml에서는 각 작업의 끝에서 ** \<성공\> ** 실행 결과를 확인 하 고 오류가 없는지 확인 한 다음 로그를 닫습니다. 다음 cmdlet를 실행하여 사용 권한을 테스트할 수 있습니다.
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    예를 들면 다음과 같습니다.
    
        Test-CsOuPermission -ObjectType "user","contact" -OU "cn=Bellevue,dc=contoso,dc=net" -Domain "contoso.net"
    
    <div>
    

    > [!NOTE]  
    > 잠긴 Active Directory 환경의 포리스트 루트 도메인에서 도메인 준비를 실행 하는 경우 Lync Server에 Active Directory 스키마 및 구성 컨테이너에 대 한 액세스 권한이 있어야 합니다.<BR>인증 된 기본 사용자 권한이 AD&nbsp;DS의 스키마 또는 구성 컨테이너에서 제거 된 경우에는 schema Admins 그룹의 구성원 (스키마 컨테이너) 또는 Enterprise Admins 그룹 (구성 컨테이너)만 지정 된 컨테이너에 액세스할 수 있습니다. Setup.exe, Lync Server 관리 셸 cmdlet 및 Lync Server 제어판에는 이러한 컨테이너에 대 한 액세스 권한이 필요 하기 때문에 설치를 실행 하는 사용자에 게 스키마와 동일한 사용자 권한을 부여 하지 않으면 관리 도구의 설치 및 설치가 실패 합니다. 관리자 및 엔터프라이즈 관리자 그룹 구성원 자격<BR>이 문제를 해결하려면 RTCUniversalGlobalWriteGroup 그룹에 해당 스키마 및 구성 컨테이너에 대한 읽기/쓰기 권한을 부여해야 합니다.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

