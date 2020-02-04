---
title: 'Lync Server 2013: Computer, User 또는 InetOrgPerson 컨테이너에서 권한 상속이 비활성화됨'
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
ms.openlocfilehash: da84454a6e02e02520206b5eb667edfcf4fce849
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755248"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers-in-lync-server-2013"></a>Lync Server 2013의 Computer, User 또는 InetOrgPerson 컨테이너에서 권한 상속이 비활성화됨

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-12-19_

잠겨진 Active Directory 도메인 서비스에서 사용자 및 컴퓨터 개체는 사용 권한을 상속 하는 특정 Ou (조직 구성 단위)에 배치 되어 관리 위임을 보호 하 고 Gpo (그룹 정책 개체) 사용을 사용 하도록 설정 하는 경우가 많습니다. 보안 정책을 적용 합니다.

도메인 준비 및 서버 활성화 Lync Server 2013에 필요한 Ace (액세스 제어 항목)를 설정 합니다. 사용 권한 상속을 사용 하지 않도록 설정한 경우 Lync Server 보안 그룹은 이러한 Ace를 상속할 수 없습니다. 이러한 권한이 상속 되지 않는 경우 Lync Server 보안 그룹은 설정에 액세스할 수 없으며 다음 두 가지 문제가 발생 합니다.

  - 사용자, InetOrgPersons, 연락처를 관리 하 고 서버를 운영 하려면 Lync Server 보안 그룹에 각 사용자의 속성 집합, 실시간 통신 (RTC), RTC 사용자 검색 및 공개 정보에 대 한 도메인 준비 절차에 따라 설정 된 Ace가 필요 합니다. . 사용 권한 상속을 사용 하지 않도록 설정한 경우 보안 그룹은 이러한 Ace를 상속 하지 않으며 서버 또는 사용자를 관리할 수 없습니다.

  - 서버와 풀을 검색 하려면 Lync Server를 실행 하는 서버는 Microsoft 컨테이너 및 서버 개체를 포함 하 여 컴퓨터 관련 개체에서 정품 인증을 통해 설정 된 Ace를 사용 합니다. 사용 권한 상속을 사용 하지 않도록 설정한 경우 보안 그룹, 서버 및 풀은 이러한 Ace를 상속 하지 않으며 이러한 Ace를 활용할 수 없습니다.

이러한 문제를 해결 하기 위해 Lync Server는 **부여-CsOuPermission** cmdlet을 제공 합니다. 이 cmdlet은 지정 된 컨테이너 및 조직 구성 단위와 컨테이너 또는 조직 구성 단위 내의 개체에 대 한 필수 Lync 서버 Ace를 직접 설정 합니다.

<div>

## <a name="set-permissions-for-user-inetorgperson-and-contact-objects-after-running-domain-preparation"></a>도메인 준비를 실행 한 후 사용자, InetOrgPerson, 연락처 개체에 대 한 사용 권한 설정

사용 권한 상속을 사용 하지 않도록 설정한 잠겨진 Active Directory 환경에서 도메인 준비는 사용자 또는 도메인 내 InetOrgPerson 개체를 보유 하는 조직 구성 단위 또는 컨테이너에 필요한 Ace를 설정 하지 않습니다. 이 경우 사용 권한 상속을 사용 하지 않도록 설정 된 사용자 또는 InetOrgPerson 개체가 있는 각 컨테이너 또는 OU에 대해 **부여-CsOuPermission** cmdlet을 실행 해야 합니다. 중앙 포리스트 토폴로지가 있는 경우 연락처 개체를 보유 하는 컨테이너 또는 Ou에 대해서도이 절차를 수행 해야 합니다. 중앙 포리스트 토폴로지에 대 한 자세한 내용은 지원 가능성 설명서의 [Lync Server 2013에서 지원 되는 Active Directory 토폴로지](lync-server-2013-supported-active-directory-topologies.md) 를 참조 하세요. ObjectType 매개 변수는 개체 형식을 지정 합니다. OU 매개 변수는 조직 구성 단위를 지정 합니다.

이 cmdlet은 지정 된 컨테이너 또는 Ou와 컨테이너 내의 사용자 또는 InetOrgPerson 개체에 직접 필수 Ace를 추가 합니다. 이 명령이 실행 되는 OU에 사용자 또는 InetOrgPerson 개체가 있는 하위 Ou가 있는 경우 해당 권한은 해당 권한이 적용 되지 않습니다. 각 하위 OU에서 개별적으로 명령을 실행 해야 합니다. 이는 Lync 호스팅 배포 (예: Parent OU = OCS 테 넌 트, DC = CONTOSO, DC = LOCAL 및 child OU = Tenant1, OU = OCS 테 넌 트, DC = CONTOSO, DC = LOCAL)와 같은 일반적인 시나리오입니다.

이 cmdlet을 실행 하려면 도메인 관리자 그룹 구성원 자격에 해당 하는 사용자 권한이 필요 합니다. 인증 된 사용자 Ace도 잠긴 환경에서 제거 된 경우, [Lync Server 2013에서](lync-server-2013-authenticated-user-permissions-are-removed.md) 설명한 대로 포리스트 루트 도메인의 관련 컨테이너 또는 ou에 대 한 읽기 액세스 ace를이 계정에 부여 해야 해당 사용자에 게 해당 계정이 표시 되거나 Enterprise 관리자 그룹의 구성원 인 계정을 사용할 수 있습니다.

**사용자, InetOrgPerson 및 연락처 개체에 대해 필요한 Ace를 설정 하려면**

1.  Domain Admins 그룹의 구성원 이거나 해당 사용자 권한이 있는 계정을 사용 하 여 도메인에 연결 된 컴퓨터에 로그온 합니다.

2.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

3.  런
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    Domain 매개 변수를 지정 하지 않으면 로컬 도메인이 기본값이 됩니다.
    
    예를 들면 다음과 같습니다.
    
        Grant-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net"

4.  로그 파일에서 각 작업의 끝에 있는 ** \<성공\> ** 실행 결과를 찾아 권한이 설정 되었는지 확인 한 다음 로그 창을 닫습니다. 또는 다음 명령을 실행 하 여 사용 권한이 설정 되었는지 여부를 확인할 수 있습니다.
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>] [-Report <fully qualified path and name of file to create>]
    
    예를 들면 다음과 같습니다.
    
        Test-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net" -Report "C:\Log\OUPermissionsTest.html"

</div>

<div>

## <a name="set-permissions-for-computer-objects-after-running-domain-preparation"></a>도메인 준비를 실행 한 후 컴퓨터 개체에 대 한 사용 권한 설정

권한 상속을 사용 하지 않도록 설정한 잠겨진 Active Directory 환경에서 도메인 준비는 도메인 내 컴퓨터 개체를 보유 하는 컨테이너나 Ou에 필요한 Ace를 설정 하지 않습니다. 이 경우 사용 권한 상속을 사용 하지 않도록 설정 하는 Lync Server를 실행 하는 컴퓨터가 있는 각 컨테이너 또는 OU에 대해 **부여-CsOuPermission** cmdlet을 실행 해야 합니다. ObjectType 매개 변수는 개체 형식을 지정 합니다.

이 절차에서는 지정 된 컨테이너에 필요한 Ace를 직접 추가 합니다.

이 cmdlet을 실행 하려면 도메인 관리자 그룹 구성원 자격에 해당 하는 사용자 권한이 필요 합니다. 인증 된 사용자 Ace도 제거 된 경우에는 인증 된 사용자 사용 권한에서 설명한 대로 포리스트 루트 도메인의 관련 컨테이너에 대 한이 계정 읽기 액세스 Ace를 [Lync Server 2013에서 제거](lync-server-2013-authenticated-user-permissions-are-removed.md) 되거나 Enterprise Admins 그룹의 구성원 인 계정을 사용 해야 합니다.

**컴퓨터 개체에 대해 필요한 Ace를 설정 하려면**

1.  Domain Admins 그룹의 구성원 이거나 해당 사용자 권한이 있는 계정을 사용 하 여 도메인 컴퓨터에 로그온 합니다.

2.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

3.  런
    
        Grant-CsOuPermission -ObjectType <Computer> 
        -OU <DN name for the computer OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>][-Report <fully qualified path and name of output report>]
    
    Domain 매개 변수를 지정 하지 않으면 로컬 도메인이 기본값이 됩니다.
    
    예를 들면 다음과 같습니다.
    
        Grant-CsOuPermission -ObjectType "Computer" -OU "ou=Lync Servers,dc=litwareinc,dc=com" -Report "C:\Logs\OUPermissions.xml"

4.  예제 로그 파일 C:\\로그\\를 사용 하 여 각 작업의 끝에서 ** \<성공\> ** 실행 결과를 찾고 오류가 없는지 확인 한 다음 로그를 닫습니다. 다음 cmdlet을 실행 하 여 사용 권한을 테스트할 수 있습니다.
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    예를 들면 다음과 같습니다.
    
        Test-CsOuPermission -ObjectType "user","contact" -OU "cn=Bellevue,dc=contoso,dc=net" -Domain "contoso.net"
    
    <div>
    

    > [!NOTE]  
    > Active directory 환경에서 포리스트 루트 도메인에 대 한 도메인 준비를 실행 하는 경우 Lync Server에 활성 디렉터리 스키마 및 구성 컨테이너에 대 한 액세스 권한이 필요 하다는 점에 유의 하세요.<BR>인증 된 기본 사용자 권한이 AD&nbsp;DS의 스키마 또는 구성 컨테이너에서 제거 되는 경우 스키마 관리자 그룹 (스키마 컨테이너의 경우) 또는 엔터프라이즈 관리자 그룹 (구성 컨테이너의 경우)만 지정 된 컨테이너에 액세스할 수 있습니다. Setup.exe, Lync Server 관리 셸 cmdlet 및 Lync Server 제어판에는 이러한 컨테이너에 대 한 액세스가 필요 하므로 설치를 실행 하는 사용자에 게 스키마와 동일한 사용자 권한이 없으면 관리 도구의 설정 및 설치가 실패 합니다. 관리자 및 엔터프라이즈 관리자 그룹 구성원.<BR>이 문제를 해결 하려면 스키마 및 구성 컨테이너에 대 한 RTCUniversalGlobalWriteGroup 그룹 읽기, 쓰기 액세스 권한을 부여 해야 합니다.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

