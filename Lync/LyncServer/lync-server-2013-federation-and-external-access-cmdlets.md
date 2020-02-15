---
title: 'Lync Server 2013: 페더레이션 및 외부 액세스 cmdlet'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Federation and external access cmdlets
ms:assetid: 4a384a57-257f-47a6-98d9-54cea2c647b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415651(v=OCS.15)
ms:contentKeyID: 48184018
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 032258e6fe7d77808b3bf4731049ee9df49d1162
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042595"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="federation-and-external-access-cmdlets-in-lync-server-2013"></a>Lync Server 2013의 페더레이션 및 외부 액세스 cmdlet

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-06-26_

페더레이션 및 외부 액세스는 두 가지 중요 한 기능을 제공 하며, 페더레이션에서는 사용자가 조직 외부의 사용자와 통신할 수 있으며, 외부 액세스를 통해 내부 네트워크 외부에서 Microsoft Lync Server 2013에 연결할 수 있습니다. Lync Server 2013에서 페더레이션 및 외부 액세스를 관리 하는 데 사용할 수 있는 cmdlet을 사용 하면 사용자가 내부에 로그온 하 고 연결할 수 없는 사람을 결정 하 고, 해당 사용자가 내부적으로 로그인 할 필요 없이 Lync Server에 연결 될 수 있는지 여부를 결정 사설망.

<div>

## <a name="federation-and-external-access-cmdlets"></a>페더레이션 및 외부 액세스 Cmdlet

페더레이션 및 외부 액세스에 적용 되는 대부분의 관리 작업은 Lync Server 제어판에서 수행할 수 있습니다. 이러한 동일한 작업은 Lync Server 관리 셸에서 또는 스크립트 내에서 cmdlet을 사용 하 여 수행할 수 있습니다. 스크립트를 사용 하면 특정 작업을 자동화할 수 있습니다. 다음은 페더레이션 및 외부 액세스 관리와 직접 관련 된 cmdlet 목록입니다.

  - <span></span>  
    [Get-CsAllowedDomain](https://technet.microsoft.com/library/Gg398164(v=OCS.15))

  - <span></span>  
    [새-CsAllowedDomain](https://technet.microsoft.com/library/Gg398628(v=OCS.15))

  - <span></span>  
    [제거-CsAllowedDomain](https://technet.microsoft.com/library/Gg398913(v=OCS.15))

  - <span></span>  
    [설정-CsAllowedDomain](https://technet.microsoft.com/library/Gg398931(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-csblockeddomain](https://technet.microsoft.com/library/Gg398424(v=OCS.15))

  - <span></span>  
    [Get-csblockeddomain](https://technet.microsoft.com/library/Gg398822(v=OCS.15))

  - <span></span>  
    [Get-csblockeddomain을 제거 합니다.](https://technet.microsoft.com/library/Gg425832(v=OCS.15))

  - <span></span>  
    [Get-csblockeddomain](https://technet.microsoft.com/library/Gg398090(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-csexternalaccesspolicy](https://technet.microsoft.com/library/Gg425805(v=OCS.15))

  - <span></span>  
    [Get-csexternalaccesspolicy](https://technet.microsoft.com/library/Gg425942(v=OCS.15))

  - <span></span>  
    [Get-csexternalaccesspolicy](https://technet.microsoft.com/library/Gg398441(v=OCS.15))

  - <span></span>  
    [Get-csexternalaccesspolicy을 제거 합니다.](https://technet.microsoft.com/library/Gg399057(v=OCS.15))

  - <span></span>  
    [Get-csexternalaccesspolicy](https://technet.microsoft.com/library/Gg398916(v=OCS.15))

<!-- end list -->

  - [Get-CsFIPSConfiguration](https://technet.microsoft.com/library/JJ204904(v=OCS.15))

  - [새-CsFIPSConfiguration](https://technet.microsoft.com/library/JJ205114(v=OCS.15))

  - [제거-CsFIPSConfiguration](https://technet.microsoft.com/library/JJ205201(v=OCS.15))

  - [설정-CsFIPSConfiguration](https://technet.microsoft.com/library/JJ205084(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [사용 안 함-CsHostingProvider](https://technet.microsoft.com/library/Gg398481(v=OCS.15))

  - <span></span>  
    [Enable-CsHostingProvider](https://technet.microsoft.com/library/Gg398166(v=OCS.15))

  - <span></span>  
    [Get-CsHostingProvider](https://technet.microsoft.com/library/Gg413078(v=OCS.15))

  - <span></span>  
    [새-CsHostingProvider](https://technet.microsoft.com/library/Gg398490(v=OCS.15))

  - <span></span>  
    [제거-CsHostingProvider](https://technet.microsoft.com/library/Gg425809(v=OCS.15))

  - <span></span>  
    [Set-CsHostingProvider](https://technet.microsoft.com/library/Gg398532(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [사용 안 함-Disable-cspublicprovider](https://technet.microsoft.com/library/Gg398984(v=OCS.15))

  - <span></span>  
    [Enable-Disable-cspublicprovider](https://technet.microsoft.com/library/Gg398780(v=OCS.15))

  - <span></span>  
    [Disable-cspublicprovider](https://technet.microsoft.com/library/Gg412945(v=OCS.15))

  - <span></span>  
    [Disable-cspublicprovider](https://technet.microsoft.com/library/Gg398161(v=OCS.15))

  - <span></span>  
    [Disable-cspublicprovider을 제거 합니다.](https://technet.microsoft.com/library/Gg412906(v=OCS.15))

  - <span></span>  
    [Disable-cspublicprovider](https://technet.microsoft.com/library/Gg413087(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-csfederatedpartner](https://technet.microsoft.com/library/Gg398281(v=OCS.15))

<!-- end list -->

  - [Get-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ204981(v=OCS.15))

  - [새-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ204631(v=OCS.15))

  - [제거-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ205055(v=OCS.15))

  - [설정-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ204686(v=OCS.15))

<!-- end list -->

  - [Get-CsXmppGatewayConfiguration](https://technet.microsoft.com/library/JJ204869(v=OCS.15))

  - [설정-CsXmppGatewayConfiguration](https://technet.microsoft.com/library/JJ204769(v=OCS.15))

<!-- end list -->

  - [테스트-CsXmppIM](https://technet.microsoft.com/library/JJ205423(v=OCS.15))

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

