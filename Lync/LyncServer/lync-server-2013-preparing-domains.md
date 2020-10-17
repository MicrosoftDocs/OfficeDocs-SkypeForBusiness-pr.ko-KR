---
title: 'Lync Server 2013: 도메인 준비'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing domains
ms:assetid: 8eea541c-5f9d-4afc-92a8-a31d6f742544
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398721(v=OCS.15)
ms:contentKeyID: 48184816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a37c365732785198e45a546f2352c51ccb42f9dc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506945"
---
# <a name="preparing-domains-for-lync-server-2013"></a>Lync Server 2013에 대 한 도메인 준비

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-29_

도메인 준비는 Lync Server 2013에 대 한 Active Directory 도메인 서비스 준비의 마지막 단계입니다. 도메인 준비 단계에서는 호스트에 권한을 부여하고 도메인 내의 사용자를 관리하는 유니버설 그룹에 필요한 ACE(액세스 제어 항목)를 추가합니다. 도메인 준비는 도메인 루트와 세 개의 기본 제공 컨테이너인 사용자, 컴퓨터 및 도메인 컨트롤러에 ACE를 만듭니다.

Lync Server를 배포 하는 도메인의 모든 컴퓨터에서 도메인 준비를 실행할 수 있습니다. Lync Server 또는 사용자를 호스트 하는 모든 도메인을 준비 해야 합니다.

조직에서 권한 상속이 비활성화되어 있거나 인증된 사용자 권한을 비활성화해야 하는 경우 도메인 준비 작업 중에 추가 단계를 수행해야 합니다. 자세한 내용은 [Lync Server 2013에서 잠긴 Active Directory 도메인 서비스 준비](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md)를 참조 하세요.

조직에서 세 개의 기본 제공 컨테이너(즉, 사용자, 컴퓨터 및 도메인 컨트롤러) 대신에 OU(조직 구성 단위)를 사용하는 경우 OU에 Authenticated Users 그룹에 대한 읽기 권한을 부여해야 합니다. 컨테이너에 대한 읽기 권한은 도메인을 준비하는 데 필요합니다. Authenticated Users 그룹에 OU에 대한 읽기 권한이 없는 경우 각 OU에 읽기 권한을 부여하는 다음 코드 예제와 같이 **Grant-CsOuPermission** cmdlet을 실행합니다.

   ```PowerShell
    Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU > 
   ```

   ```PowerShell
    Grant-CsOuPermission -ObjectType "user","contact",inetOrgPerson" -OU "ou=Redmond,dc=contoso,dc=net"
   ```

**부여-CsOuPermission** cmdlet에 대 한 자세한 내용은 Lync Server 관리 셸 설명서를 참조 하세요.

<div class="">


> [!TIP]  
> 도메인 루트와 사용자, 컴퓨터 및 도메인 컨트롤러 컨테이너에서 만들어진 Ace에 대 한 자세한 내용은 <A href="lync-server-2013-changes-made-by-domain-preparation.md">Lync Server 2013에서 도메인 준비로 인 한 변경 내용을</A>참조 하십시오.



</div>

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013에 대 한 도메인 준비 실행](lync-server-2013-running-domain-preparation.md)

  - [Cmdlet을 사용 하 여 Lync Server 2013에 대 한 도메인 준비 되돌리기](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

