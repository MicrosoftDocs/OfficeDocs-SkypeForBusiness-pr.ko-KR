---
title: 'Lync Server 2013: 호출 허용 제어 cmdlet'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call admission control cmdlets
ms:assetid: dd9d3912-b562-4839-a337-bfc5277cfb62
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415676(v=OCS.15)
ms:contentKeyID: 48185602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e192d30205a43d2bf13a347b7ee40f0ac424320
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984553"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-cmdlets-in-lync-server-2013"></a>Lync Server 2013의 통화 허용 제어 cmdlet

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-03-21_

CAC (Call 허용 제어)는 실시간 오디오 또는 비디오 세션을 허용 가능한 품질로 설정 하기에 충분 한 네트워크 대역폭이 있는지 여부를 결정 합니다. 네트워크, 사이트 및 서브넷 및 그 간의 상호 작용에 대 한 제한 사항 및 설정을 적용 하 여 CAC를 관리 합니다.

<div>

## <a name="call-admission-control-cmdlets"></a>통화 허용 제어 Cmdlet

다음 cmdlet을 사용 하 여 Lync Server 관리 셸에서 CAC를 관리 하세요.

**통화 허용 컨트롤**

  - <span></span>  
    [Get-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg412727(v=OCS.15))

  - <span></span>  
    [새로운 CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398175(v=OCS.15))

  - <span></span>  
    [제거-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398877(v=OCS.15))

  - <span></span>  
    [Set-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg412863(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/en-us/library/Gg425815(v=OCS.15))

  - <span></span>  
    [새로운 CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/en-us/library/Gg398675(v=OCS.15))

  - <span></span>  
    [제거-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/en-us/library/Gg398609(v=OCS.15))

  - <span></span>  
    [Set-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/en-us/library/Gg398338(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [새로운 CsNetworkBWAlternatePath](https://technet.microsoft.com/en-us/library/Gg398732(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [새-CsNetworkBWPolicy](https://technet.microsoft.com/en-us/library/Gg412916(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-Set-csnetworkconfiguration](https://technet.microsoft.com/en-us/library/Gg398140(v=OCS.15))

  - <span></span>  
    [제거-Set-csnetworkconfiguration](https://technet.microsoft.com/en-us/library/Gg398938(v=OCS.15))

  - <span></span>  
    [Set-Set-csnetworkconfiguration](https://technet.microsoft.com/en-us/library/Gg398927(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-Csnetworkinter국가 경로](https://technet.microsoft.com/en-us/library/Gg425817(v=OCS.15))

  - <span></span>  
    [새-Csnetworkinter국가 경로](https://technet.microsoft.com/en-us/library/Gg398779(v=OCS.15))

  - <span></span>  
    [제거-Csnetworkinter국가 경로](https://technet.microsoft.com/en-us/library/Gg398743(v=OCS.15))

  - <span></span>  
    [Set-Csnetworkinter국가 경로](https://technet.microsoft.com/en-us/library/Gg398410(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsNetworkInterSitePolicy](https://technet.microsoft.com/en-us/library/Gg412769(v=OCS.15))

  - <span></span>  
    [새로운 CsNetworkInterSitePolicy](https://technet.microsoft.com/en-us/library/Gg398994(v=OCS.15))

  - <span></span>  
    [제거-CsNetworkInterSitePolicy](https://technet.microsoft.com/en-us/library/Gg398963(v=OCS.15))

  - <span></span>  
    [Set-CsNetworkInterSitePolicy](https://technet.microsoft.com/en-us/library/Gg398772(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsNetworkRegion](https://technet.microsoft.com/en-us/library/Gg398406(v=OCS.15))

  - <span></span>  
    [새-CsNetworkRegion](https://technet.microsoft.com/en-us/library/Gg425829(v=OCS.15))

  - <span></span>  
    [CsNetworkRegion 제거](https://technet.microsoft.com/en-us/library/Gg398466(v=OCS.15))

  - <span></span>  
    [Set-CsNetworkRegion](https://technet.microsoft.com/en-us/library/Gg413089(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-Csnetwork국가 링크](https://technet.microsoft.com/en-us/library/Gg398972(v=OCS.15))

  - <span></span>  
    [새-Csnetwork국가 링크](https://technet.microsoft.com/en-us/library/Gg398437(v=OCS.15))

  - <span></span>  
    [-Csnetwork국가 링크 제거](https://technet.microsoft.com/en-us/library/Gg413012(v=OCS.15))

  - <span></span>  
    [Set-Csnetwork국가 링크](https://technet.microsoft.com/en-us/library/Gg412867(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398766(v=OCS.15))

  - <span></span>  
    [새-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398365(v=OCS.15))

  - <span></span>  
    [CsNetworkSite 사이트 제거](https://technet.microsoft.com/en-us/library/Gg398135(v=OCS.15))

  - <span></span>  
    [집합-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398295(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsNetworkSubnet](https://technet.microsoft.com/en-us/library/Gg412825(v=OCS.15))

  - <span></span>  
    [새-CsNetworkSubnet](https://technet.microsoft.com/en-us/library/Gg398226(v=OCS.15))

  - <span></span>  
    [CsNetworkSubnet 제거](https://technet.microsoft.com/en-us/library/Gg425726(v=OCS.15))

  - <span></span>  
    [Set-CsNetworkSubnet](https://technet.microsoft.com/en-us/library/Gg412739(v=OCS.15))

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 통화 허용 제어 개요](lync-server-2013-overview-of-call-admission-control.md)  


[Lync Server PowerShell 블로그](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

