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
ms.openlocfilehash: 20a6897ae45964f3f179e951916dfb6bf7180641
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724948"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-domains-for-lync-server-2013"></a>Lync Server 2013에 대한 도메인 준비

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-29_

도메인 준비는 Lync Server 2013의 Active Directory 도메인 서비스를 준비 하는 마지막 단계입니다. 도메인 준비 단계에서는 도메인 내에서 사용자를 호스트 하 고 관리할 수 있는 권한을 부여 하는 유니버설 그룹에 필요한 Ace (액세스 제어 항목)를 추가 합니다. 도메인 준비는 도메인 루트 및 세 가지 기본 제공 컨테이너 (사용자, 컴퓨터 및 도메인 컨트롤러)에 Ace를 만듭니다.

Lync Server를 배포 하는 도메인의 모든 컴퓨터에서 도메인 준비를 실행할 수 있습니다. Lync Server 또는 사용자를 호스트 하는 모든 도메인을 준비 해야 합니다.

사용 권한 상속을 사용 하지 않거나 인증 된 사용자 권한을 조직에서 사용할 수 없는 경우에는 도메인을 준비 하는 동안 추가 단계를 수행 해야 합니다. 자세한 내용은 [Lync Server 2013에서 잠겨진 Active Directory 도메인 서비스 준비](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md)를 참조 하세요.

조직에서 세 가지 기본 제공 컨테이너 (즉, 사용자, 컴퓨터 및 도메인 컨트롤러) 대신 OU (조직 구성 단위)를 사용 하는 경우 인증 된 사용자 그룹의 Ou에 대 한 읽기 권한을 부여 해야 합니다. 도메인 준비에는 컨테이너에 대 한 읽기 권한이 필요 합니다. 인증 된 사용자 그룹에 OU에 대 한 읽기 권한이 없는 경우 다음 코드 예제에 나와 있는 것 처럼 **Grant-CsOuPermission** cmdlet을 실행 하 여 각 OU에 대 한 읽기 권한을 부여 합니다.

   ```PowerShell
    Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU > 
   ```

   ```PowerShell
    Grant-CsOuPermission -ObjectType "user","contact",inetOrgPerson" -OU "ou=Redmond,dc=contoso,dc=net"
   ```

**허용-CsOuPermission** cmdlet에 대 한 자세한 내용은 Lync Server 관리 셸 설명서를 참조 하세요.

<div class="">


> [!TIP]  
> 도메인 루트 및 사용자, 컴퓨터 및 도메인 컨트롤러 컨테이너에서 만든 Ace에 대 한 자세한 내용은 <A href="lync-server-2013-changes-made-by-domain-preparation.md">Lync Server 2013에서 도메인 준비를 통해 변경한 내용을</A>참조 하세요.



</div>

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013에 대한 도메인 준비 실행](lync-server-2013-running-domain-preparation.md)

  - [Lync Server 2013에 대해 cmdlet을 사용하여 도메인 준비 되돌리기](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

