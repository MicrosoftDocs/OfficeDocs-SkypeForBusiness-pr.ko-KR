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
ms.openlocfilehash: 91f20a5a1df722e92454e0200a0c8174ff37d4dc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533205"
---
# <a name="enterprise-voice-cmdlets-in-lync-server-2013"></a>Lync Server 2013의 Enterprise Voice cmdlet

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-03-19_

Enterprise Voice는 Microsoft의 VoIP(Voice over IP)에 대한 구현입니다. Microsoft Lync Server 2013에서 Enterprise Voice를 관리 하는 데 사용할 수 있는 cmdlet을 사용 하면 다이얼 플랜 (이전의 위치 프로필), 음성 정책, 경로 및 정규화 규칙을 만들고 수정할 수 있습니다.

<div>

## <a name="enterprise-voice-cmdlets"></a>Enterprise Voice Cmdlet

Enterprise Voice에 해당 되는 대부분의 관리 작업은 Lync Server 제어판에서 수행할 수 있습니다. 이러한 동일한 작업은 Lync Server 관리 셸 또는 스크립트 내에서 cmdlet을 사용 하 여 수행 하거나 특정 작업을 자동화할 수 있습니다. 다음은 Enterprise Voice 관리와 직접 관련 된 cmdlet 목록입니다.

**[Lync Server 2013의 Enterprise Voice cmdlet 문제 해결](lync-server-2013-troubleshooting-enterprise-voice-cmdlets.md)**

  - <span></span>  
    [CsVoiceConfiguration](https://technet.microsoft.com/library/Gg398815(v=OCS.15))

  - <span></span>  
    [CsVoiceConfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg398804(v=OCS.15))

  - <span></span>  
    [CsVoiceConfiguration](https://technet.microsoft.com/library/Gg398967(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [수정한 구성은 test-csvoicetestconfiguration](https://technet.microsoft.com/library/Gg412957(v=OCS.15))

  - <span></span>  
    [수정한 구성은 test-csvoicetestconfiguration](https://technet.microsoft.com/library/Gg398961(v=OCS.15))

  - <span></span>  
    [수정한 구성은 test-csvoicetestconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg412813(v=OCS.15))

  - <span></span>  
    [수정한 구성은 test-csvoicetestconfiguration](https://technet.microsoft.com/library/Gg398614(v=OCS.15))

  - <span></span>  
    [수정한 구성은 test-csvoicetestconfiguration](https://technet.microsoft.com/library/Gg398260(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [테스트-CsDialPlan 플랜](https://technet.microsoft.com/library/Gg399024(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-csvoicenormalizationrule](https://technet.microsoft.com/library/Gg399003(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Set-csvoicepolicy](https://technet.microsoft.com/library/Gg398310(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-csvoiceroute](https://technet.microsoft.com/library/Gg425873(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [CsVoiceUser](https://technet.microsoft.com/library/Gg413013(v=OCS.15))

**[Lync Server 2013의 음성 정규화 규칙 cmdlet](lync-server-2013-voice-normalization-rules-cmdlets.md)**

  - <span></span>  
    [Get-csvoicenormalizationrule](https://technet.microsoft.com/library/Gg398393(v=OCS.15))

  - <span></span>  
    [Get-csvoicenormalizationrule](https://technet.microsoft.com/library/Gg398240(v=OCS.15))

  - <span></span>  
    [Get-csvoicenormalizationrule을 제거 합니다.](https://technet.microsoft.com/library/Gg398501(v=OCS.15))

  - <span></span>  
    [Get-csvoicenormalizationrule](https://technet.microsoft.com/library/Gg398491(v=OCS.15))

  - <span></span>  
    [Get-csvoicenormalizationrule](https://technet.microsoft.com/library/Gg399003(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [CsVoiceRegex](https://technet.microsoft.com/library/Gg412751(v=OCS.15))

**[Lync Server 2013의 음성 정책 cmdlet](lync-server-2013-voice-policy-cmdlets.md)**

  - <span></span>  
    [Get-CsDialPlan 플랜](https://technet.microsoft.com/library/Gg413043(v=OCS.15))

  - <span></span>  
    [부여-CsDialPlan 플랜](https://technet.microsoft.com/library/Gg398547(v=OCS.15))

  - <span></span>  
    [새 CsDialPlan 플랜](https://technet.microsoft.com/library/Gg425860(v=OCS.15))

  - <span></span>  
    [CsDialPlan 다이얼 플랜 제거](https://technet.microsoft.com/library/Gg398791(v=OCS.15))

  - <span></span>  
    [설정-CsDialPlan 플랜](https://technet.microsoft.com/library/Gg398644(v=OCS.15))

  - <span></span>  
    [테스트-CsDialPlan 플랜](https://technet.microsoft.com/library/Gg399024(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [G-CsPstnUsage 사용](https://technet.microsoft.com/library/Gg412734(v=OCS.15))

  - <span></span>  
    [설정-CsPstnUsage](https://technet.microsoft.com/library/Gg399069(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Set-csvoicepolicy](https://technet.microsoft.com/library/Gg398101(v=OCS.15))

  - <span></span>  
    [Set-csvoicepolicy](https://technet.microsoft.com/library/Gg398828(v=OCS.15))

  - <span></span>  
    [Set-csvoicepolicy](https://technet.microsoft.com/library/Gg425856(v=OCS.15))

  - <span></span>  
    [Set-csvoicepolicy을 제거 합니다.](https://technet.microsoft.com/library/Gg398309(v=OCS.15))

  - <span></span>  
    [Set-csvoicepolicy](https://technet.microsoft.com/library/Gg399021(v=OCS.15))

  - <span></span>  
    [Set-csvoicepolicy](https://technet.microsoft.com/library/Gg398310(v=OCS.15))

**[Lync Server 2013의 음성 라우팅 cmdlet](lync-server-2013-voice-routing-cmdlets.md)**

  - <span></span>  
    [Get-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg425851(v=OCS.15))

  - <span></span>  
    [새-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg399056(v=OCS.15))

  - <span></span>  
    [제거-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg398643(v=OCS.15))

  - <span></span>  
    [설정-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg412811(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-csvoiceroute](https://technet.microsoft.com/library/Gg425926(v=OCS.15))

  - <span></span>  
    [Get-csvoiceroute](https://technet.microsoft.com/library/Gg398197(v=OCS.15))

  - <span></span>  
    [Get-csvoiceroute을 제거 합니다.](https://technet.microsoft.com/library/Gg398468(v=OCS.15))

  - <span></span>  
    [Get-csvoiceroute](https://technet.microsoft.com/library/Gg412893(v=OCS.15))

  - <span></span>  
    [Get-csvoiceroute](https://technet.microsoft.com/library/Gg425873(v=OCS.15))

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 고급 Enterprise Voice cmdlet](lync-server-2013-advanced-enterprise-voice-cmdlets.md)  
[Lync Server 2013의 음성 응용 프로그램 cmdlet](lync-server-2013-voice-application-cmdlets.md)  


[Lync Server PowerShell 블로그](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

