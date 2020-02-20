---
title: 'Lync Server 2013: 고정 라우팅 cmdlet'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Static routing cmdlets
ms:assetid: 71d5e0cd-8412-4383-818a-95b851a4da4b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg416492(v=OCS.15)
ms:contentKeyID: 48184496
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 230781ba898de502195d727aa4a2a9981dfdbeba
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142524"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="static-routing-cmdlets-in-lync-server-2013"></a>Lync Server 2013의 고정 라우팅 cmdlet

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-06-20_

관리자는 고정 경로를 사용하여 SIP 메시지에 사용할 네트워크 경로를 미리 결정할 수 있습니다. 메시지가 서버에 수신되면 서버는 메시지 주소를 확인한 다음 관리자가 미리 구성한 다음 홉 서버로 메시지를 전달합니다. 고정 경로를 제대로 구성한 경우에는 제시간에 정확하게 메시지를 전달하고 서버에 대한 오버헤드를 최소화할 수 있습니다.

<div>

## <a name="static-routing-cmdlets"></a>고정 라우팅 Cmdlet

Microsoft 지원 담당자가 달리 지시한 경우가 아니면 Microsoft Lync Server 2013에 대해 구성 된 고정 경로를 [새 CsStaticRoute](https://technet.microsoft.com/library/Gg398265(v=OCS.15)) cmdlet을 사용 하 여 만들어야 합니다. 경로를 만든 후 CsStaticRoutingConfiguration cmdlet를 사용하여 해당 경로를 고정 경로 컬렉션에 추가할 수 있습니다.

**고정 경로**

  - <span></span>  
    [Get-cssipresponsecodetranslationrule](https://technet.microsoft.com/library/Gg398130(v=OCS.15))

  - <span></span>  
    [Get-cssipresponsecodetranslationrule](https://technet.microsoft.com/library/Gg413041(v=OCS.15))

  - <span></span>  
    [Get-cssipresponsecodetranslationrule을 제거 합니다.](https://technet.microsoft.com/library/Gg412932(v=OCS.15))

  - <span></span>  
    [Get-cssipresponsecodetranslationrule](https://technet.microsoft.com/library/Gg425895(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [새-CsStaticRoute](https://technet.microsoft.com/library/Gg398265(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsStaticRoutingConfiguration](https://technet.microsoft.com/library/Gg398754(v=OCS.15))

  - <span></span>  
    [새-CsStaticRoutingConfiguration](https://technet.microsoft.com/library/Gg425811(v=OCS.15))

  - <span></span>  
    [제거-CsStaticRoutingConfiguration](https://technet.microsoft.com/library/Gg398668(v=OCS.15))

  - <span></span>  
    [설정-CsStaticRoutingConfiguration](https://technet.microsoft.com/library/Gg398724(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-cssipproxycustom](https://technet.microsoft.com/library/Gg425904(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-cssipproxyrealm](https://technet.microsoft.com/library/Gg413084(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-cssipproxytcp](https://technet.microsoft.com/library/Gg425745(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-cssipproxytls](https://technet.microsoft.com/library/Gg398629(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-cssipproxytransport](https://technet.microsoft.com/library/Gg398489(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-cssipproxyusedefault](https://technet.microsoft.com/library/Gg398274(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-cssipproxyusedefaultcert](https://technet.microsoft.com/library/Gg425858(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-csissuedcertid](https://technet.microsoft.com/library/Gg425814(v=OCS.15))

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

