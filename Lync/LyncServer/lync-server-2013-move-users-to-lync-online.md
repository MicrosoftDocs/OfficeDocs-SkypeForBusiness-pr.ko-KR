---
title: 'Lync Server 2013: 사용자를 Lync Online으로 이동'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move users to Lync Online
ms:assetid: 6a523c86-2eac-4fa4-973a-4406872c9a7d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204969(v=OCS.15)
ms:contentKeyID: 48184392
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5106d4e27921d9407b2663410cc0872892479ebb
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43779855"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-users-to-lync-online-in-lync-server-2013"></a>Lync Server 2013에서 사용자를 Lync Online으로 이동

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-05-29_

사용자를 Lync Online으로 마이그레이션하기 전에 이동할 계정에 연결 된 사용자 데이터를 백업 해야 합니다. 사용자 계정을 사용 하 여 모든 사용자 데이터를 이동 하는 것은 아닙니다. 자세한 내용은 [Lync Server 2013의 백업 및 복원 요구 사항: 데이터](lync-server-2013-backup-and-restoration-requirements-data.md)를 참조 하세요.

<div>

## <a name="migrate-user-settings-to-lync-online"></a>Lync Online으로 사용자 설정 마이그레이션

사용자 설정은 사용자 계정과 함께 이동 됩니다. 일부 온-프레미스 설정이 사용자 계정으로 이동 되지 않습니다.

</div>

<div>

## <a name="moving-pilot-users-to-lync-online"></a>파일럿 사용자를 Lync Online으로 이동

사용자를 Lync Online으로 이동 하기 전에 몇 가지 파일럿 사용자를 이동 하 여 환경이 올바르게 구성 되어 있는지 확인할 수 있습니다. 그런 다음 추가 사용자 이동을 시도 하기 전에 Lync 기능 및 서비스가 예상 대로 작동 하는지 확인할 수 있습니다.

온-프레미스 사용자를 Lync Online 테 넌 트로 이동 하려면 Microsoft Office 365 조 직에 대 한 관리자 자격 증명을 사용 하 여 Lync Server 관리 셸에서 다음 cmdlet을 실행 합니다. 이동 하려는 사용자에 대 한 정보로 "username@contoso.com"를 바꿉니다.

   ```PowerShell
    $creds=Get-Credential
   ```

   ```PowerShell
    Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>
   ```

**HostedMigrationOverrideUrl** 매개 변수에 대해 지정 된 url의 형식은 호스트 되는 마이그레이션 서비스가 실행 되는 풀의 url 이어야 하며 HTTPS://\<pool FQDN\>/HostedMigration/hostedmigrationService.svc.입니다.

Office 365 조직 계정에 대 한 Lync Online 제어판의 URL을 확인 하 여 호스팅된 마이그레이션 서비스에 대 한 URL을 확인할 수 있습니다.

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

<div>

## <a name="moving-users-to-lync-online"></a>사용자를 Lync Online으로 이동

- [Csuser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) cmdlet을 – Filter 매개 변수를 사용 하 여 여러 사용자를 이동 하 여 RegistrarPool와 같은 사용자 계정에 특정 속성이 할당 된 사용자를 선택할 수 있습니다. 그런 다음 다음 예제와 같이 반환 된 사용자를 [csuser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) cmdlet에 파이프 합니다.

    Get-CsUser -Filter {UserProperty -eq "UserPropertyValue"} | Move-CsUser -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>

-OU 매개 변수를 사용 하 여 다음 예제와 같이 지정 된 OU의 모든 사용자를 검색할 수도 있습니다.

    Get-CsUser -OU "cn=hybridusers,cn=contoso.." | Move-CsUser -Target sipfed.online.lync.com -Credentials $creds -HostedMigrationOverrideUrl <URL>

</div>

<div>

## <a name="verify-lync-online-user-settings-and-features"></a>Lync Online 사용자 설정 및 기능 확인

사용자가 다음과 같은 방식으로 이동 되었는지 확인할 수 있습니다.

  - Lync Online 제어판에서 사용자의 상태를 확인 합니다. 온-프레미스 사용자 및 온라인 사용자의 시각적 표시기는 서로 다릅니다.

  - 다음 cmdlet을 실행합니다.
    
        Get-CsUser -Identity

</div>

</div>

<span> </span>

</div>

</div>

</div>

