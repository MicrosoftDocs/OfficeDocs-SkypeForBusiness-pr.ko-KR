---
title: 'Lync Server 2013: 페더레이션 및 외부 액세스 cmdlet'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Federation and external access cmdlets
ms:assetid: 4a384a57-257f-47a6-98d9-54cea2c647b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415651(v=OCS.15)
ms:contentKeyID: 48184018
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc44d6d8dbd196e720d836ba8c3417e06a44c988
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983765"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="federation-and-external-access-cmdlets-in-lync-server-2013"></a>Lync Server 2013의 페더레이션 및 외부 액세스 cmdlet

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-06-26_

페더레이션 및 외부 액세스는 사용자가 조직 외부 사용자와 통신할 수 있도록 하는 반면, 외부 액세스를 통해 사용자는 내부 네트워크 외부에서 Microsoft Lync Server 2013에 연결할 수 있습니다. Lync Server 2013에서 페더레이션 및 외부 액세스를 관리 하는 데 사용할 수 있는 cmdlet을 사용 하면 사용자가 통신할 수 있는 사람을 결정 하 고, 내부에 로그온 할 필요 없이 이러한 사용자가 Lync Server에 연결할 수 있는지 여부를 결정 합니다. 사설망.

<div>

## <a name="federation-and-external-access-cmdlets"></a>페더레이션 및 외부 액세스 Cmdlet

페더레이션 및 외부 액세스에 적용 되는 대부분의 관리 작업은 Lync Server 제어판에서 수행할 수 있습니다. 이러한 동일한 작업은 Lync Server 관리 셸에서 또는 스크립트 내에서 cmdlet을 사용 하 여 수행할 수 있습니다. 스크립트를 사용 하 여 특정 작업을 자동화할 수 있습니다. 다음은 페더레이션 및 외부 액세스를 관리 하는 것과 직접적으로 관련 된 cmdlet의 목록입니다.

  - <span></span>  
    [Get-CsAllowedDomain](https://technet.microsoft.com/en-us/library/Gg398164(v=OCS.15))

  - <span></span>  
    [New-CsAllowedDomain](https://technet.microsoft.com/en-us/library/Gg398628(v=OCS.15))

  - <span></span>  
    [CsAllowedDomain 제거](https://technet.microsoft.com/en-us/library/Gg398913(v=OCS.15))

  - <span></span>  
    [Set-CsAllowedDomain](https://technet.microsoft.com/en-us/library/Gg398931(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsBlockedDomain](https://technet.microsoft.com/en-us/library/Gg398424(v=OCS.15))

  - <span></span>  
    [새로운 CsBlockedDomain](https://technet.microsoft.com/en-us/library/Gg398822(v=OCS.15))

  - <span></span>  
    [제거-CsBlockedDomain](https://technet.microsoft.com/en-us/library/Gg425832(v=OCS.15))

  - <span></span>  
    [Set-CsBlockedDomain](https://technet.microsoft.com/en-us/library/Gg398090(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg425805(v=OCS.15))

  - <span></span>  
    [부여-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg425942(v=OCS.15))

  - <span></span>  
    [New-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg398441(v=OCS.15))

  - <span></span>  
    [Remove-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg399057(v=OCS.15))

  - <span></span>  
    [Set-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg398916(v=OCS.15))

<!-- end list -->

  - [Get-CsFIPSConfiguration](https://technet.microsoft.com/en-us/library/JJ204904(v=OCS.15))

  - [새-CsFIPSConfiguration](https://technet.microsoft.com/en-us/library/JJ205114(v=OCS.15))

  - [-CsFIPSConfiguration 제거](https://technet.microsoft.com/en-us/library/JJ205201(v=OCS.15))

  - [Set-CsFIPSConfiguration](https://technet.microsoft.com/en-us/library/JJ205084(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Disable-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398481(v=OCS.15))

  - <span></span>  
    [Enable-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398166(v=OCS.15))

  - <span></span>  
    [Get-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg413078(v=OCS.15))

  - <span></span>  
    [신규-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398490(v=OCS.15))

  - <span></span>  
    [제거-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg425809(v=OCS.15))

  - <span></span>  
    [Set-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398532(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Disable-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg398984(v=OCS.15))

  - <span></span>  
    [Enable-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg398780(v=OCS.15))

  - <span></span>  
    [Get-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg412945(v=OCS.15))

  - <span></span>  
    [New-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg398161(v=OCS.15))

  - <span></span>  
    [제거-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg412906(v=OCS.15))

  - <span></span>  
    [Set-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg413087(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [테스트-CsFederatedPartner](https://technet.microsoft.com/en-us/library/Gg398281(v=OCS.15))

<!-- end list -->

  - [Get-CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ204981(v=OCS.15))

  - [새-CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ204631(v=OCS.15))

  - [-CsXmppAllowedPartner 제거](https://technet.microsoft.com/en-us/library/JJ205055(v=OCS.15))

  - [Set-CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ204686(v=OCS.15))

<!-- end list -->

  - [Get-Csxmpp게이트웨이 구성](https://technet.microsoft.com/en-us/library/JJ204869(v=OCS.15))

  - [Set-Csxmpp게이트웨이 구성](https://technet.microsoft.com/en-us/library/JJ204769(v=OCS.15))

<!-- end list -->

  - [Test-CsXmppIM](https://technet.microsoft.com/en-us/library/JJ205423(v=OCS.15))

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server PowerShell 블로그](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

