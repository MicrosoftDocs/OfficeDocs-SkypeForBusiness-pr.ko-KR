---
title: 'Lync Server 2013: 사용자를 Lync Online으로 이동'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Move users to Lync Online
ms:assetid: 6a523c86-2eac-4fa4-973a-4406872c9a7d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204969(v=OCS.15)
ms:contentKeyID: 48184392
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6172c526816a3572d6c364b714d5d4e7e5323cac
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991373"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-users-to-lync-online-in-lync-server-2013"></a>Lync Server 2013에서 Lync Online으로 사용자 이동

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-05-29_

Lync Online으로 사용자 마이그레이션을 시작 하기 전에 이동할 계정에 연결 된 사용자 데이터를 백업 해야 합니다. 모든 사용자 데이터가 사용자 계정으로 이동 되는 것은 아닙니다. 자세한 내용은 [Lync Server 2013: data의 백업 및 복원 요구 사항을](lync-server-2013-backup-and-restoration-requirements-data.md)참조 하세요.

<div>

## <a name="migrate-user-settings-to-lync-online"></a>Lync Online으로 사용자 설정 마이그레이션

사용자 설정은 사용자 계정으로 이동 합니다. 일부 온-프레미스 설정이 사용자 계정으로 이동 되지 않습니다.

</div>

<div>

## <a name="moving-pilot-users-to-lync-online"></a>파일럿 사용자를 Lync Online으로 이동

사용자를 Lync Online으로 옮기기 시작 하기 전에 몇 가지 파일럿 사용자를 이동 하 여 환경이 올바르게 구성 되었는지 확인할 수 있습니다. 그런 다음 추가 사용자 이동을 시도 하기 전에 Lync 기능 및 서비스가 예상 대로 작동 하는지 확인할 수 있습니다.

온-프레미스 사용자를 Lync Online 테 넌 트로 이동 하려면 Microsoft Office 365 테 넌 트에 대 한 관리자 자격 증명을 사용 하 여 Lync Server 관리 셸에서 다음 cmdlet을 실행 합니다. "Username@contoso.com"를 이동 하려는 사용자의 정보로 바꿉니다.

   ```PowerShell
    $creds=Get-Credential
   ```

   ```PowerShell
    Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>
   ```

**HostedMigrationOverrideUrl** 매개 변수에 대해 지정 된 Url 형식은 호스팅된 마이그레이션 서비스가 실행 되는 풀의 url 이어야 하며, HTTPS://\<pool FQDN\>/HostedMigration/hostedmigrationService.svc. 형식입니다.

Office 365 테 넌 트 계정에 대 한 Lync Online 제어판의 URL을 보고 호스팅된 마이그레이션 서비스의 URL을 확인할 수 있습니다.

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

<div>

## <a name="moving-users-to-lync-online"></a>Lync Online으로 사용자 이동

[Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) cmdlet을 – Filter 매개 변수를 사용 하 여 사용자 계정에 할당 된 특정 속성이 있는 사용자를 선택 하 여 여러 사용자를 이동할 수 있습니다 (예: RegistrarPool). 그런 다음 다음 예제에 표시 된 대로 [이동-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) cmdlet에 반환 된 사용자를 파이프 할 수 있습니다.

    Get-CsUser -Filter {UserProperty -eq "UserPropertyValue"} | Move-CsUser -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>

다음 예와 같이 – OU 매개 변수를 사용 하 여 지정 된 OU의 모든 사용자를 검색할 수도 있습니다.

    Get-CsUser -OU "cn=hybridusers,cn=contoso.." | Move-CsUser -Target sipfed.online.lync.com -Credentials $creds -HostedMigrationOverrideUrl <URL>

</div>

<div>

## <a name="verify-lync-online-user-settings-and-features"></a>Lync Online 사용자 설정 및 기능 확인

사용자가 다음 방법으로 성공적으로 이동 했는지 확인할 수 있습니다.

  - Lync Online 제어판에서 사용자의 상태를 봅니다. 온-프레미스 사용자 및 온라인 사용자의 시각적 표시기는 서로 다릅니다.

  - 다음 cmdlet을 실행 합니다.
    
        Get-CsUser -Identity

</div>

</div>

<span> </span>

</div>

</div>

</div>

