---
title: 'Lync Server 2013: 하이브리드 배포에서 사용자 관리'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Administering users in a hybrid deployment
ms:assetid: 6924ed7b-30a9-4be7-b952-90655625f2c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204967(v=OCS.15)
ms:contentKeyID: 48184381
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b09ca3c5a80215c0a2d63a018150361671df6859
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43779604"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="administering-users-in-a-hybrid-lync-server-2013-deployment"></a>하이브리드 Lync Server 2013 배포에서 사용자 관리

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-05-29_

Microsoft Office 365 Online 포털에서 제공 되는 사용자 관리 기능을 사용 하 여 Lync Online으로 마이그레이션된 사용자에 대 한 사용자 설정 및 정책을 관리할 수 있습니다. 테 넌 트 관리자 계정을 사용 하 여 로그인 해야 관리 작업을 수행할 수 있습니다.

<div>

## <a name="moving-users-back-to-on-premises"></a>사용자를 온-프레미스로 다시 이동

<div class="">


> [!IMPORTANT]  
> 이 섹션은 Lync 온-프레미스에 대해 만들고 사용 하도록 설정한 후 온-프레미스 배포에서 Lync Online으로 이동한 사용자 에게만 적용 됩니다. Lync Online에서 만든 사용자를 이동 하려는 경우 온-프레미스 배포에서 Lync를 사용 하도록 설정 하지 않은 경우 lync <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Server 2013에서 Lync online에서 lync 온-프레미스로 사용자 이동</A>을 참조 하세요.



</div>

  - Lync Online에서 Lync 온-프레미스로 사용자를 이동 하려면 다음 cmdlet을 실행 합니다.
    
       ```PowerShell
        $cred=Get-Credential
       ```
    
       ```PowerShell
        Move-CsUser -Identity username@contoso.com -Target localpool.contoso.com -Credential $cred -HostedMigrationOverrideUrl <URL>
       ```

**HostedMigrationOverrideUrl** 매개 변수에 대해 지정 된 url 형식은 다음과 같은 형식으로 호스팅된 마이그레이션 서비스를 실행 하는 풀의 url 이어야 합니다.

Https://\<풀 FQDN\>/HostedMigration/hostedmigrationService.svc. Office 365 조직 계정에 대 한 Lync Online 제어판의 URL을 확인 하 여 호스팅된 마이그레이션 서비스에 대 한 URL을 확인할 수 있습니다.

**Office 365 조 직에 대 한 호스팅된 마이그레이션 서비스 URL을 확인 하려면**

1.  관리자로 Office 365 조직에 로그인 합니다.

2.  **Lync 관리 센터**를 엽니다.

3.  **Lync 관리 센터** 를 표시 하 고 주소 표시줄의 URL을 선택 하 여 **lync.com**에 복사 합니다. URL의 예는 다음과 같습니다.
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  URL의 **webdir** 을 **admin**으로 바꾸면 다음과 같은 결과가 나타납니다.
    
    `https://admin0a.online.lync.com`

5.  URL에 다음 문자열을 추가 합니다: **/HostedMigration/hostedmigrationservice.svc**.
    
    **HostedMigrationOverrideUrl**값을 나타내는 결과 URL은 다음과 같습니다.
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

</div>

</div>

<span> </span>

</div>

</div>

</div>

