---
title: 'Lync Server 2013: lync Online에서 Lync 온-프레미스로 사용자 마이그레이션을 시작 하기 전의 첫 번째 단계'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: First steps before you start migrating users from Lync Online to Lync on-premises
ms:assetid: 98245b04-ded4-4186-8da3-ba1c554b5c39
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689118(v=OCS.15)
ms:contentKeyID: 62258123
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac0377c12cbda0d6080ecfe9b8e64fae08cbed59
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40989133"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="first-steps-before-you-start-migrating-users-from-lync-online-to-lync-on-premises-in-lync-server-2013"></a>Lync Online에서 lync 온-프레미스로 사용자 마이그레이션을 시작 하기 전의 첫 번째 단계는 Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-05-08_

Lync Online 사용자를 온-프레미스 환경으로 이동 하기 전에 다음이 모두 참인 지 확인 합니다.

  - Lync Server 온-프레미스 환경이 완벽 하 게 배포 되 고 유효성을 검사 해야 합니다. 자세한 내용은 [Lync Server 2013 배포](lync-server-2013-deploying-lync-server.md)를 참조 하세요.

  - Lync Online 테 넌 트가 원격 PowerShell 액세스용으로 구성 되어 있어야 합니다.
    
    이렇게 하려면 먼저 다음 [http://go.microsoft.com/fwlink/p/?LinkId=391911](http://go.microsoft.com/fwlink/p/?linkid=391911)을 수행할 수 있는 Windows PowerShell 용 Lync Online 모듈을 설치 합니다.
    
    모듈을 설치한 후 Lync Server 관리 셸에 다음 cmdlet을 입력 하 여 원격 세션을 설정할 수 있습니다.
    
       ```PowerShell
        Import-Module LyncOnlineConnector
       ```  
    
       ```PowerShell
        $cred = Get-Credential
       ``` 
    
       ```PowerShell
        $CSSession = New-CsOnlineSession -Credential $cred
       ```
    
       ```PowerShell
        Import-PSSession $CSSession -AllowClobber
       ```
    
    Lync Online에서 원격 PowerShell 세션을 설정 하는 방법에 대 한 자세한 내용은 [Windows PowerShell을 사용 하 여 Lync online에 연결](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)을 참조 하세요.
  
    Lync Online PowerShell 모듈을 사용 하는 방법에 대 한 자세한 내용은 [Windows PowerShell을 사용 하 여 Lync online 관리](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)를 참조 하세요.

  - Lync Online은 공유 SIP 주소 공간에 대해 구성 되어 있어야 합니다. 이렇게 하려면 먼저 Lync Online을 사용 하 여 원격 Powershell 세션을 시작 합니다. 그런 후 다음 cmdlet을 실행 합니다.
    
        Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True

이러한 단계를 완료 한 후 lync [Server 2013에서 Lync Online 사용자를 lync 온-프레미스로 마이그레이션하기](lync-server-2013-migrating-lync-online-users-to-lync-on-premises.md)위해 이동할 수 있습니다.

</div>

<span> </span>

</div>

</div>

</div>

