---
title: 'Lync Server 2013: Lync Online을 사용 하 여 페더레이션 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure federation with Lync Online
ms:assetid: a10bd1d5-c003-46db-9f57-7d55d3fa08da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205126(v=OCS.15)
ms:contentKeyID: 48184946
ms.date: 08/15/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb679f8bf0fae046bea0177daab22203bbf9aef1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028539"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-federation-of-lync-server-2013-with-lync-online"></a>Lync Online을 사용 하 여 Lync Server 2013의 페더레이션 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2016-08-15_

온-프레미스 배포와 비즈니스용 Skype Online 간의 상호 운용성을 구성 하려면이 섹션의 단계를 수행 합니다.

<span id="a"></span>

<div>

## <a name="configure-your-on-premises-edge-service-for-federation-with-skype-for-business-online"></a>비즈니스용 Skype 온라인과의 페더레이션에 대 한 온-프레미스에 지 서비스 구성

페더레이션을 사용 하면 온-프레미스 배포의 사용자가 조직의 Office 365 사용자와 통신할 수 있습니다. 페더레이션을 구성 하려면 다음 cmdlet을 실행 합니다.

   ```powershell
    Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $True
   ```

   ```powershell
    New-CSHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
   ```

</div>

<span id="b"></span>

<div>

## <a name="configure-your-skype-for-business-online-tenant-for-a-shared-sip-address-space"></a>공유 SIP 주소 공간에 대 한 비즈니스용 Skype Online 테 넌 트 구성

SIP (Session 착수 프로토콜) 주소는 전화 번호나 전자 메일 주소와 마찬가지로 네트워크의 각 사용자에 대 한 고유 식별자입니다. Lync 사용자를 온-프레미스에서 비즈니스용 Skype Online으로 이동 하기 전에 공유 세션 시작 프로토콜 (SIP) 주소 공간을 온-프레미스 배포와 공유 하도록 Office 365 테 넌 트를 구성 해야 합니다. 이 구성을 구성 하지 않으면 다음과 같은 오류 메시지가 표시 될 수 있습니다.

Move-CsUser: HostedMigration fault: Error = (510), Description = (이 사용자의 테 넌 트는 공유 sip 주소 공간에 대해 사용 하도록 설정 되지 않았습니다.)

공유 SIP 주소 공간을 구성 하려면 비즈니스용 Skype Online을 사용 하 여 원격 PowerShell 세션을 설정한 후 다음 cmdlet을 실행 합니다.
```powershell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```
비즈니스용 Skype Online을 사용 하 여 원격 PowerShell 세션을 설정 하려면 먼저 비즈니스용 Skype 온라인 모듈 for Windows PowerShell을 설치 해야 [http://go.microsoft.com/fwlink/p/?LinkId=391911](http://go.microsoft.com/fwlink/p/?linkid=391911)합니다.

모듈을 설치한 후에는 다음 cmdlet을 사용 하 여 원격 세션을 설정할 수 있습니다.

   ```powershell
    Import-Module LyncOnlineConnector
   ```

   ```powershell
    $cred = Get-Credential
   ``` 

   ```powershell
    $CSSession = New-CsOnlineSession -Credential $cred
   ```

   ```powershell
    Import-PSSession $CSSession -AllowClobber
   ```

비즈니스용 Skype Online을 사용 하 여 원격 PowerShell 세션을 설정 하는 방법에 대 한 자세한 내용은 [Windows PowerShell을 사용 하 여 비즈니스용 Skype online에 연결](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)을 참조 하세요.

비즈니스용 Skype Online PowerShell 모듈을 사용 하는 방법에 대 한 자세한 내용은 [Windows PowerShell을 사용 하 여 비즈니스용 Skype online 관리](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)를 참조 하세요.

</div>

<div>

## <a name="see-also"></a>참고 항목


[새-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

