---
title: 'Lync Server 2013: 보안 cmdlet'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Security cmdlets
ms:assetid: 9a6c654d-287d-434e-8d93-409f0d623f5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398799(v=OCS.15)
ms:contentKeyID: 48184968
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d7ba707c613bcfafb23dd158025d253f9a03ac9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510455"
---
# <a name="security-cmdlets-in-lync-server-2013"></a>Lync Server 2013의 보안 cmdlet

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-09_

Microsoft Lync Server 2013에 포함 된 보안 cmdlet은 주로 인증을 관리 하는 데 사용 되며 사용자 권한 및 사용 권한을 제공 합니다. 인증서 및 PIN(개인 식별 번호) 인증을 위한 cmdlet 등 인증 관리에 사용할 수 있는 다양한 cmdlet가 있습니다. 또한 많은 cmdlet을 사용 하 여 새 RBAC (역할 기반 액세스 제어) 기능을 통해 Lync Server의 관리 제어를 위임할 수 있습니다.

<div>

## <a name="security-cmdlets"></a>보안 Cmdlet

보안 설정에 적용 되는 대부분의 관리 작업은 Lync Server 제어판에서 실행할 수 있습니다. 한 가지 주요 예외는 사용자 권한 cmdlet입니다. 그러나 모든 보안 관리 작업은 Lync Server 관리 셸 또는 스크립트 내에서 cmdlet을 사용 하 여 수행할 수 있습니다. 스크립트를 사용 하면 특정 작업을 자동화할 수 있습니다. 다음은 보안 설정 관리에 직접적으로 관련된 cmdlet 목록입니다.

**[Lync Server 2013의 인증서 및 인증 cmdlet](lync-server-2013-certificate-and-authentication-cmdlets.md)**

  - <span></span>  
    [Set-cscertificate](https://technet.microsoft.com/library/Gg398227(v=OCS.15))

  - <span></span>  
    [Set-cscertificate](https://technet.microsoft.com/library/Gg398688(v=OCS.15))

  - <span></span>  
    [Set-cscertificate을 제거 합니다.](https://technet.microsoft.com/library/Gg412895(v=OCS.15))

  - <span></span>  
    [요청-Set-cscertificate](https://technet.microsoft.com/library/Gg425723(v=OCS.15))

  - <span></span>  
    [Set-cscertificate](https://technet.microsoft.com/library/Gg398518(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-cscertificateconfiguration](https://technet.microsoft.com/library/Gg398647(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-csclientcertificate](https://technet.microsoft.com/library/Gg398143(v=OCS.15))

  - <span></span>  
    [Get-csclientcertificate](https://technet.microsoft.com/library/Gg425748(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [잠금-CsClientPin](https://technet.microsoft.com/library/Gg398650(v=OCS.15))

  - <span></span>  
    [설정-CsClientPin](https://technet.microsoft.com/library/Gg398929(v=OCS.15))

  - <span></span>  
    [잠금 해제-CsClientPin](unhttps://technet.microsoft.com/library/Gg398650(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsClientPinInfo](https://technet.microsoft.com/library/Gg425947(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [새-C고 Ercosaccount](https://technet.microsoft.com/library/Gg398485(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg398526(v=OCS.15))

  - <span></span>  
    [Get-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg398074(v=OCS.15))

  - <span></span>  
    [Get-cskerberosaccountassignment을 제거 합니다.](https://technet.microsoft.com/library/Gg413052(v=OCS.15))

  - <span></span>  
    [Get-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg398232(v=OCS.15))

  - <span></span>  
    [Get-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Set-CsKerberosAccountPassword](https://technet.microsoft.com/library/Gg398659(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-cspinpolicy](https://technet.microsoft.com/library/Gg398262(v=OCS.15))

  - <span></span>  
    [Get-cspinpolicy](https://technet.microsoft.com/library/Gg398871(v=OCS.15))

  - <span></span>  
    [Get-cspinpolicy](https://technet.microsoft.com/library/Gg398935(v=OCS.15))

  - <span></span>  
    [Get-cspinpolicy을 제거 합니다.](https://technet.microsoft.com/library/Gg398431(v=OCS.15))

  - <span></span>  
    [Get-cspinpolicy](https://technet.microsoft.com/library/Gg412997(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsProxyConfiguration](https://technet.microsoft.com/library/Gg399011(v=OCS.15))

  - <span></span>  
    [새-CsProxyConfiguration](https://technet.microsoft.com/library/Gg398335(v=OCS.15))

  - <span></span>  
    [CsProxyConfiguration 제거](https://technet.microsoft.com/library/Gg398553(v=OCS.15))

  - <span></span>  
    [설정-CsProxyConfiguration](https://technet.microsoft.com/library/Gg425796(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-cssipdomain](https://technet.microsoft.com/library/Gg398701(v=OCS.15))

  - <span></span>  
    [New-cssipdomain](https://technet.microsoft.com/library/Gg425857(v=OCS.15))

  - <span></span>  
    [New-cssipdomain을 제거 합니다.](https://technet.microsoft.com/library/Gg398865(v=OCS.15))

  - <span></span>  
    [New-cssipdomain](https://technet.microsoft.com/library/Gg412949(v=OCS.15))

**[Lync Server 2013의 사용자 권한 및 사용 권한 cmdlet](lync-server-2013-user-rights-and-permissions-cmdlets.md)**

  - <span></span>  
    [Get-CsAdminRole](https://technet.microsoft.com/library/Gg399050(v=OCS.15))

  - <span></span>  
    [새-CsAdminRole](https://technet.microsoft.com/library/Gg398271(v=OCS.15))

  - <span></span>  
    [제거-CsAdminRole](https://technet.microsoft.com/library/Gg413036(v=OCS.15))

  - <span></span>  
    [설정-CsAdminRole](https://technet.microsoft.com/library/Gg399066(v=OCS.15))

  - <span></span>  
    [업데이트-CsAdminRole](https://technet.microsoft.com/library/JJ204851(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsAdminRoleAssignment](https://technet.microsoft.com/library/Gg398434(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [부여-CsOUPermission](https://technet.microsoft.com/library/Gg425739(v=OCS.15))

  - <span></span>  
    [CsOUPermission](https://technet.microsoft.com/library/Gg398977(v=OCS.15))

  - <span></span>  
    [테스트-CsOUPermission](https://technet.microsoft.com/library/Gg398787(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [부여-CsSetupPermission](https://technet.microsoft.com/library/Gg398569(v=OCS.15))

  - <span></span>  
    [CsSetupPermission](https://technet.microsoft.com/library/Gg425834(v=OCS.15))

  - <span></span>  
    [테스트-CsSetupPermission](https://technet.microsoft.com/library/Gg398428(v=OCS.15))

**[Lync Server 2013의 상호 운용성 cmdlet](lync-server-2013-interoperability-cmdlets.md)**

  - [Get-CsOAuthConfiguration](https://technet.microsoft.com/library/JJ205155(v=OCS.15))

  - [Set-CsOAuthConfiguration](https://technet.microsoft.com/library/JJ204841(v=OCS.15))

<!-- end list -->

  - [Get-CsOAuthServer](https://technet.microsoft.com/library/JJ205238(v=OCS.15))

  - [새-CsOAuthServer](https://technet.microsoft.com/library/JJ205206(v=OCS.15))

  - [CsOAuthServer 제거](https://technet.microsoft.com/library/JJ205408(v=OCS.15))

  - [Set-CsOAuthServer](https://technet.microsoft.com/library/JJ204896(v=OCS.15))

<!-- end list -->

  - [Get-cspartnerapplication](https://technet.microsoft.com/library/JJ205128(v=OCS.15))

  - [Get-cspartnerapplication](https://technet.microsoft.com/library/JJ204628(v=OCS.15))

  - [Get-cspartnerapplication을 제거 합니다.](https://technet.microsoft.com/library/JJ204820(v=OCS.15))

  - [Get-cspartnerapplication](https://technet.microsoft.com/library/JJ204755(v=OCS.15))

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server PowerShell 블로그](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

