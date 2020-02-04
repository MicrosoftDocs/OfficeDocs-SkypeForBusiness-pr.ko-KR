---
title: 'Lync Server 2013: Enterprise Voice cmdlet'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enterprise Voice cmdlets
ms:assetid: 7d7c6d94-3ead-4d99-95f7-c31b448ab9e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415658(v=OCS.15)
ms:contentKeyID: 48184613
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc1c5516c80ed38839b795c92a5521be93711cad
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735398"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enterprise-voice-cmdlets-in-lync-server-2013"></a>Lync Server 2013의 엔터프라이즈 음성 cmdlet

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-03-19_

엔터프라이즈 음성은 Microsoft가 구현한 VoIP (Voice over IP)입니다. Microsoft Lync Server 2013에서 Enterprise Voice를 관리 하는 데 사용할 수 있는 cmdlet은 다이얼 플랜 (이전의 위치 프로필), 음성 정책, 경로 및 정규화 규칙을 만들고 수정할 수 있도록 합니다.

<div>

## <a name="enterprise-voice-cmdlets"></a>엔터프라이즈 음성 Cmdlet

기업 음성에 적용 되는 대부분의 관리 작업은 Lync Server 제어판에서 수행할 수 있습니다. 이러한 동일한 작업은 Lync Server Management Shell 또는 스크립트 내에서 cmdlet을 사용 하 여 수행할 수 있으며 특정 작업을 자동화 하도록 허용 합니다. 다음은 Enterprise Voice 관리와 직접 관련 된 cmdlet 목록입니다.

**[Lync Server 2013에서 엔터프라이즈 음성 cmdlet 문제 해결](lync-server-2013-troubleshooting-enterprise-voice-cmdlets.md)**

  - <span></span>  
    [Get-CsVoiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398815(v=OCS.15))

  - <span></span>  
    [제거-CsVoiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398804(v=OCS.15))

  - <span></span>  
    [Set-CsVoiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398967(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg412957(v=OCS.15))

  - <span></span>  
    [새로운 CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg398961(v=OCS.15))

  - <span></span>  
    [제거-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg412813(v=OCS.15))

  - <span></span>  
    [Set-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg398614(v=OCS.15))

  - <span></span>  
    [테스트-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg398260(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [테스트-CsDialPlan 플랜](https://technet.microsoft.com/en-us/library/Gg399024(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [테스트-CsVoiceNormalizationRule](https://technet.microsoft.com/en-us/library/Gg399003(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [테스트-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398310(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [테스트-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg425873(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [테스트-CsVoiceUser](https://technet.microsoft.com/en-us/library/Gg413013(v=OCS.15))

**[Lync Server 2013의 음성 정규화 규칙 cmdlet](lync-server-2013-voice-normalization-rules-cmdlets.md)**

  - <span></span>  
    [Get-CsVoiceNormalizationRule](https://technet.microsoft.com/en-us/library/Gg398393(v=OCS.15))

  - <span></span>  
    [새로운 CsVoiceNormalizationRule](https://technet.microsoft.com/en-us/library/Gg398240(v=OCS.15))

  - <span></span>  
    [제거-CsVoiceNormalizationRule](https://technet.microsoft.com/en-us/library/Gg398501(v=OCS.15))

  - <span></span>  
    [Set-CsVoiceNormalizationRule](https://technet.microsoft.com/en-us/library/Gg398491(v=OCS.15))

  - <span></span>  
    [테스트-CsVoiceNormalizationRule](https://technet.microsoft.com/en-us/library/Gg399003(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [새로운 CsVoiceRegex](https://technet.microsoft.com/en-us/library/Gg412751(v=OCS.15))

**[Lync Server 2013의 음성 정책 cmdlet](lync-server-2013-voice-policy-cmdlets.md)**

  - <span></span>  
    [가져오기-CsDialPlan 플랜](https://technet.microsoft.com/en-us/library/Gg413043(v=OCS.15))

  - <span></span>  
    [부여-CsDialPlan 플랜](https://technet.microsoft.com/en-us/library/Gg398547(v=OCS.15))

  - <span></span>  
    [새 CsDialPlan 플랜](https://technet.microsoft.com/en-us/library/Gg425860(v=OCS.15))

  - <span></span>  
    [CsDialPlan 플랜 제거](https://technet.microsoft.com/en-us/library/Gg398791(v=OCS.15))

  - <span></span>  
    [Set CsDialPlan 플랜](https://technet.microsoft.com/en-us/library/Gg398644(v=OCS.15))

  - <span></span>  
    [테스트-CsDialPlan 플랜](https://technet.microsoft.com/en-us/library/Gg399024(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [다운로드-CsPstnUsage](https://technet.microsoft.com/en-us/library/Gg412734(v=OCS.15))

  - <span></span>  
    [집합-CsPstnUsage 사용](https://technet.microsoft.com/en-us/library/Gg399069(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398101(v=OCS.15))

  - <span></span>  
    [부여-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398828(v=OCS.15))

  - <span></span>  
    [New-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg425856(v=OCS.15))

  - <span></span>  
    [제거-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398309(v=OCS.15))

  - <span></span>  
    [Set-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg399021(v=OCS.15))

  - <span></span>  
    [테스트-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398310(v=OCS.15))

**[Lync Server 2013의 음성 라우팅 cmdlet](lync-server-2013-voice-routing-cmdlets.md)**

  - <span></span>  
    [Get-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg425851(v=OCS.15))

  - <span></span>  
    [새-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg399056(v=OCS.15))

  - <span></span>  
    [-CsRoutingConfiguration 제거](https://technet.microsoft.com/en-us/library/Gg398643(v=OCS.15))

  - <span></span>  
    [Set-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg412811(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg425926(v=OCS.15))

  - <span></span>  
    [새로운 CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg398197(v=OCS.15))

  - <span></span>  
    [제거-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg398468(v=OCS.15))

  - <span></span>  
    [Set-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg412893(v=OCS.15))

  - <span></span>  
    [테스트-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg425873(v=OCS.15))

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 고급 엔터프라이즈 음성 cmdlet](lync-server-2013-advanced-enterprise-voice-cmdlets.md)  
[Lync Server 2013의 음성 응용 프로그램 cmdlet](lync-server-2013-voice-application-cmdlets.md)  


[Lync Server PowerShell 블로그](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

