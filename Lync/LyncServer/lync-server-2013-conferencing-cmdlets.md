---
title: 'Lync Server 2013: 회의 cmdlet'
description: 'Lync Server 2013: 회의 cmdlet'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferencing cmdlets
ms:assetid: 7ff94637-6319-4c45-9230-be34e8d81ede
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398641(v=OCS.15)
ms:contentKeyID: 48184640
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b7cd9843c971d5bf8611c4e64548b2ff608f1b0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561184"
---
# <a name="conferencing-cmdlets-in-lync-server-2013"></a>Lync Server 2013의 회의 cmdlet

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-09_

Microsoft Lync Server 2013에서는 사용자가 Lync 2013 같은 회의 응용 프로그램을 사용 하거나 전화를 사용 하 여 전화를 걸어 서로 다른 두 가지 방법으로 회의에 참가할 수 있습니다. 전화 접속 사용자는 슬라이드를 보거나 인스턴트 메시지를 교환하는 등의 작업을 할 수 없지만 회의의 오디오 부분에는 완벽하게 참가할 수 있습니다.

<div>

## <a name="conferencing-cmdlets"></a>회의 Cmdlet

**CsDialInConferencing** cmdlet는 사용자가 회의에 참가하기 위해 전화를 걸 수 있는 전화 번호를 지정하는 것에서부터 사용자가 회의에 참가한 후 키패드 명령을 사용(예: 전화를 음소거 또는 음소거 해제하기 위해 6을 누르는 것)할 수 있는 것에 이르기까지 모든 것을 포함하는 전화 접속 회의 속성을 구성하는 데 사용됩니다. 회의의 다른 대부분의 기능(예: 사용자가 회의를 녹음/녹화하는 것, 사용자가 회의 도중 응용 프로그램을 공유하는 것 등)은 **CsConferencingPolicy** cmdlet를 사용하여 관리합니다.

**[Lync Server 2013의 전화 접속 회의 cmdlet](lync-server-2013-dial-in-conferencing-cmdlets.md)**

  - <span></span>  
    [Get-csconferencedirectory](https://technet.microsoft.com/library/Gg425771(v=OCS.15))

  - <span></span>  
    [이동-Get-csconferencedirectory](https://technet.microsoft.com/library/Gg412968(v=OCS.15))

  - <span></span>  
    [Get-csconferencedirectory](https://technet.microsoft.com/library/Gg413080(v=OCS.15))

  - <span></span>  
    [Get-csconferencedirectory을 제거 합니다.](rehttps://technet.microsoft.com/library/Gg412968(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-csdialinconferencing](https://technet.microsoft.com/library/Gg399013(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-csdialinconferencingaccessnumber](https://technet.microsoft.com/library/Gg413015(v=OCS.15))

  - <span></span>  
    [Get-csdialinconferencingaccessnumber](https://technet.microsoft.com/library/Gg398818(v=OCS.15))

  - <span></span>  
    [Get-csdialinconferencingaccessnumber을 제거 합니다.](https://technet.microsoft.com/library/Gg412782(v=OCS.15))

  - <span></span>  
    [Get-csdialinconferencingaccessnumber](https://technet.microsoft.com/library/Gg425770(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-csdialinconferencingconfiguration](https://technet.microsoft.com/library/Gg398575(v=OCS.15))

  - <span></span>  
    [Get-csdialinconferencingconfiguration](https://technet.microsoft.com/library/Gg412816(v=OCS.15))

  - <span></span>  
    [Get-csdialinconferencingconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg398174(v=OCS.15))

  - <span></span>  
    [Get-csdialinconferencingconfiguration](https://technet.microsoft.com/library/Gg425825(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Set-csdialinconferencingdtmfconfiguration](https://technet.microsoft.com/library/Gg398578(v=OCS.15))

  - <span></span>  
    [Set-csdialinconferencingdtmfconfiguration](https://technet.microsoft.com/library/Gg425792(v=OCS.15))

  - <span></span>  
    [Set-csdialinconferencingdtmfconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg425894(v=OCS.15))

  - <span></span>  
    [Set-csdialinconferencingdtmfconfiguration](https://technet.microsoft.com/library/Gg398860(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-csdialinconferencinglanguagelist](https://technet.microsoft.com/library/Gg425869(v=OCS.15))

**[Lync Server 2013의 웹 회의 cmdlet](lync-server-2013-web-conferencing-cmdlets.md)**

  - <span></span>  
    [Get-csconferencedisclaimer](https://technet.microsoft.com/library/Gg425714(v=OCS.15))

  - <span></span>  
    [Get-csconferencedisclaimer을 제거 합니다.](https://technet.microsoft.com/library/Gg398243(v=OCS.15))

  - <span></span>  
    [Get-csconferencedisclaimer](https://technet.microsoft.com/library/Gg398776(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Set-csconferenceserver](https://technet.microsoft.com/library/Gg398738(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-csconferencingconfiguration](https://technet.microsoft.com/library/Gg398965(v=OCS.15))

  - <span></span>  
    [Get-csconferencingconfiguration](https://technet.microsoft.com/library/Gg412967(v=OCS.15))

  - <span></span>  
    [Get-csconferencingconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg412767(v=OCS.15))

  - <span></span>  
    [Get-csconferencingconfiguration](https://technet.microsoft.com/library/Gg412969(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-csconferencingpolicy](https://technet.microsoft.com/library/Gg398293(v=OCS.15))

  - <span></span>  
    [Get-csconferencingpolicy](https://technet.microsoft.com/library/Gg425937(v=OCS.15))

  - <span></span>  
    [Get-csconferencingpolicy](https://technet.microsoft.com/library/Gg413019(v=OCS.15))

  - <span></span>  
    [Get-csconferencingpolicy을 제거 합니다.](https://technet.microsoft.com/library/Gg398728(v=OCS.15))

  - <span></span>  
    [Get-csconferencingpolicy](https://technet.microsoft.com/library/Gg425788(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-csmeetingconfiguration](https://technet.microsoft.com/library/Gg425875(v=OCS.15))

  - <span></span>  
    [Get-csmeetingconfiguration](https://technet.microsoft.com/library/Gg398065(v=OCS.15))

  - <span></span>  
    [Get-csmeetingconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg412775(v=OCS.15))

  - <span></span>  
    [Get-csmeetingconfiguration](https://technet.microsoft.com/library/Gg398648(v=OCS.15))

<!-- end list -->

  - [사용 안 함-Enable-csmeetingroom](https://technet.microsoft.com/library/JJ204723(v=OCS.15))

  - [Enable-Enable-csmeetingroom](https://technet.microsoft.com/library/JJ205062(v=OCS.15))

  - [Enable-csmeetingroom](https://technet.microsoft.com/library/JJ205277(v=OCS.15))

  - [이동-Enable-csmeetingroom](https://technet.microsoft.com/library/JJ204889(v=OCS.15))

  - [Enable-csmeetingroom](https://technet.microsoft.com/library/JJ204831(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [테스트-CsASConference](https://technet.microsoft.com/library/JJ205227(v=OCS.15))

  - <span></span>  
    [CsAVConference 테스트](https://technet.microsoft.com/library/Gg412749(v=OCS.15))

  - <span></span>  
    [Test-csdataconference](https://technet.microsoft.com/library/JJ205219(v=OCS.15))

  - <span></span>  
    [Test-cswebapp](https://technet.microsoft.com/library/Hh689989(v=OCS.15))

  - <span></span>  
    [Test-cswebappanonymous](https://technet.microsoft.com/library/Hh690041(v=OCS.15))

  - <span></span>  
    [테스트-CsWebScheduler](https://technet.microsoft.com/library/JJ204829(v=OCS.15))

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

