---
title: 'Lync Server 2013: 향상 된 9-1-1 cmdlet'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enhanced 9-1-1 cmdlets
ms:assetid: e560c688-7b34-4bd7-8104-24f390644105
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415678(v=OCS.15)
ms:contentKeyID: 48185650
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 674f74d9027789c63d76b8d8f280099b596b62b4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983465"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enhanced-9-1-1-cmdlets-in-lync-server-2013"></a>Lync Server 2013의 향상 된 9-1-1 cmdlet

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-06-20_

Microsoft Lync Server 2013에는 엔터프라이즈 음성 솔루션의 향상 된 9-1-1 (E9-1) 구현을 구현 하 고 관리 하는 데 사용할 수 있는 cmdlet이 제공 됩니다. 이러한 cmdlet을 사용 하 여 연결 지점을 실제 주소로 매핑하고 엔터프라이즈 음성 사용자에 게 긴급 통화를 성공적으로 완료 하는 데 필요한 설정을 구성 하 고 비상 서비스 공급자에 게 자동으로 위치를 보낼 수 있습니다. Lync Server 제어판의 E9-1-1을 구성할 수 없습니다. cmdlet을 사용 해야 합니다.

<div>

## <a name="enhanced-9-1-1-cmdlets"></a>향상 된 9-1-1 Cmdlet

다음 cmdlet을 사용 하 여 E9를 구성 합니다-1-1

**향상 된 9-1-1**

  - <span></span>  
    [Get-CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/en-us/library/Gg412877(v=OCS.15))

  - <span></span>  
    [제거-CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/en-us/library/Gg425810(v=OCS.15))

  - <span></span>  
    [Set-CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/en-us/library/Gg398620(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsLisCivicAddress](https://technet.microsoft.com/en-us/library/Gg398459(v=OCS.15))

  - <span></span>  
    [테스트-CsLisCivicAddress](https://technet.microsoft.com/en-us/library/Gg425914(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Export-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398539(v=OCS.15))

  - <span></span>  
    [가져오기-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398380(v=OCS.15))

  - <span></span>  
    [디버그-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398710(v=OCS.15))

  - <span></span>  
    [Test-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398497(v=OCS.15))

  - <span></span>  
    [게시-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398364(v=OCS.15))

  - <span></span>  
    [게시 취소-CsLisConfiguration](unhttps://technet.microsoft.com/en-us/library/Gg398364(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsLisLocation](https://technet.microsoft.com/en-us/library/Gg412834(v=OCS.15))

  - <span></span>  
    [제거-CsLisLocation](https://technet.microsoft.com/en-us/library/Gg425722(v=OCS.15))

  - <span></span>  
    [Set-CsLisLocation](https://technet.microsoft.com/en-us/library/Gg398757(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsLisPort](https://technet.microsoft.com/en-us/library/Gg398820(v=OCS.15))

  - <span></span>  
    [제거-CsLisPort](https://technet.microsoft.com/en-us/library/Gg412899(v=OCS.15))

  - <span></span>  
    [Set-CsLisPort](https://technet.microsoft.com/en-us/library/Gg398700(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsLisServiceProvider](https://technet.microsoft.com/en-us/library/Gg398116(v=OCS.15))

  - <span></span>  
    [제거-CsLisServiceProvider](https://technet.microsoft.com/en-us/library/Gg398904(v=OCS.15))

  - <span></span>  
    [Set-CsLisServiceProvider](https://technet.microsoft.com/en-us/library/Gg425911(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsLisSubnet](https://technet.microsoft.com/en-us/library/Gg398473(v=OCS.15))

  - <span></span>  
    [제거-CsLisSubnet](https://technet.microsoft.com/en-us/library/Gg413053(v=OCS.15))

  - <span></span>  
    [Set-CsLisSubnet](https://technet.microsoft.com/en-us/library/Gg399016(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsLisSwitch](https://technet.microsoft.com/en-us/library/Gg425769(v=OCS.15))

  - <span></span>  
    [제거-CsLisSwitch](https://technet.microsoft.com/en-us/library/Gg398352(v=OCS.15))

  - <span></span>  
    [Set-CsLisSwitch](https://technet.microsoft.com/en-us/library/Gg412823(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsLisWirelessAccessPoint](https://technet.microsoft.com/en-us/library/Gg398117(v=OCS.15))

  - <span></span>  
    [제거-CsLisWirelessAccessPoint](https://technet.microsoft.com/en-us/library/Gg398461(v=OCS.15))

  - <span></span>  
    [Set-CsLisWirelessAccessPoint](https://technet.microsoft.com/en-us/library/Gg412723(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg398911(v=OCS.15))

  - <span></span>  
    [허용-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg413049(v=OCS.15))

  - <span></span>  
    [New-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg398231(v=OCS.15))

  - <span></span>  
    [Remove-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg398727(v=OCS.15))

  - <span></span>  
    [Set-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg412987(v=OCS.15))

  - <span></span>  
    [Test-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg425962(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398766(v=OCS.15))

  - <span></span>  
    [새-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398365(v=OCS.15))

  - <span></span>  
    [CsNetworkSite 사이트 제거](https://technet.microsoft.com/en-us/library/Gg398135(v=OCS.15))

  - <span></span>  
    [집합-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398295(v=OCS.15))

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

