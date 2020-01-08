---
title: 'Lync Server 2013: 하이브리드 배포에서 사용자 관리'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Administering users in a hybrid deployment
ms:assetid: 6924ed7b-30a9-4be7-b952-90655625f2c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204967(v=OCS.15)
ms:contentKeyID: 48184381
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7804aacb226d06fbf239939658b6592d438a84f9
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40979931"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="administering-users-in-a-hybrid-lync-server-2013-deployment"></a>하이브리드 Lync Server 2013 배포에서 사용자 관리

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-05-29_

Microsoft Office 365 Online 포털에서 사용할 수 있는 사용자 관리 기능을 사용 하 여 Lync Online으로 마이그레이션한 사용자에 대 한 사용자 설정 및 정책을 관리할 수 있습니다. 테 넌 트 관리자 계정을 사용 하 여 로그인 해야 관리 작업을 수행할 수 있습니다.

<div>

## <a name="moving-users-back-to-on-premises"></a>사용자를 온-프레미스로 다시 이동

<div class="">


> [!IMPORTANT]  
> 이 섹션은 Lync 온-프레미스로 만들고 설정한 후 온-프레미스 배포에서 Lync Online으로 이동한 사용자 에게만 적용 됩니다. Lync Online에서 만든 사용자를 이동 하려는 경우 (온-프레미스 배포에서 Lync를 사용할 수 없는 경우) <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Lync Server 2013에서 Lync online에서 lync 온-프레미스로 사용자 이동</A>을 참조 하세요.



</div>

  - Lync Online의 사용자를 lync 온-프레미스로 다시 이동 하려면 다음 cmdlet을 실행 합니다.
    
       ```PowerShell
        $cred=Get-Credential
       ```
    
       ```PowerShell
        Move-CsUser -Identity username@contoso.com -Target localpool.contoso.com -Credential $cred -HostedMigrationOverrideUrl <URL>
       ```

**HostedMigrationOverrideUrl** 매개 변수에 대해 지정 된 Url 형식은 호스트 된 마이그레이션 서비스가 실행 되는 풀의 url 이어야 합니다 (다음 형식).

Https://\<풀 FQDN\>/HostedMigration/hostedmigrationService.svc. Office 365 테 넌 트 계정에 대 한 Lync Online 제어판의 URL을 보고 호스팅된 마이그레이션 서비스의 URL을 확인할 수 있습니다.

**Office 365 테 넌 트에 대 한 호스팅된 마이그레이션 서비스 URL을 확인 하려면**

1.  관리자 권한으로 Office 365 테 넌 트에 로그인 합니다.

2.  **Lync 관리 센터**를 엽니다.

3.  **Lync 관리 센터** 를 표시 한 상태에서 주소 표시줄의 URL을 선택 하 여 **lync.com**에 복사 합니다. URL 예제는 다음과 같습니다.
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  URL의 **webdir** 을 **admin**으로 바꾸면 다음과 같은 결과가 나타납니다.
    
    `https://admin0a.online.lync.com`

5.  URL에 다음 문자열을 추가 합니다. **/HostedMigration/hostedmigrationservice.svc**.
    
    **HostedMigrationOverrideUrl**의 값인 결과 URL은 다음과 같이 표시 됩니다.
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

</div>

</div>

<span> </span>

</div>

</div>

</div>

