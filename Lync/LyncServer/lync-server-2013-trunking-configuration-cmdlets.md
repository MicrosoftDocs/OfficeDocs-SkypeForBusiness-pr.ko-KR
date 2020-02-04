---
title: 'Lync Server 2013: 트렁크 구성 cmdlet'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Trunking configuration cmdlets
ms:assetid: 2c36b03a-b80f-4321-a448-6ba26b9357f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg416489(v=OCS.15)
ms:contentKeyID: 48183703
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26b3bb328b3567cb9a8826412838d7aad0ada386
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744978"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="trunking-configuration-cmdlets-in-lync-server-2013"></a>Lync Server 2013의 트렁크 구성 cmdlet

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-08_

트렁크 구성 cmdlet은 서비스 공급자의 PSTN (공개 교환 전화 네트워크) 게이트웨이, IP-공용 분기 교환 (PBX) 또는 세션 경계 컨트롤러 (SBC) 등 트렁크 피어 엔터티에 대 한 설정을 정의 하는 데 사용 됩니다. 이러한 설정은 이 트렁크에서 미디어 우회를 사용하도록 설정할지 여부, 특정 상황에서 RTCP(Real-time Transmission Control Protocol) 패킷을 보낼지 여부, SRTP(Secure Real-Time Protocol) 암호화를 요구할지 여부 등을 구성합니다.

<div>

## <a name="trunking-configuration-cmdlets"></a>트렁크 구성 Cmdlet

트렁크 구성에 다음 cmdlet을 사용 합니다.

**트렁크 구성**

  - [Test-CsInterTrunkRouting](https://technet.microsoft.com/en-us/library/JJ204741(v=OCS.15))

<!-- end list -->

  - [Get-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/en-us/library/JJ204962(v=OCS.15))

  - [새로운 CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/en-us/library/JJ205097(v=OCS.15))

  - [제거-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/en-us/library/JJ204836(v=OCS.15))

  - [Set-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/en-us/library/JJ205400(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsOutboundTranslationRule](https://technet.microsoft.com/en-us/library/Gg398104(v=OCS.15))

  - <span></span>  
    [New-CsOutboundTranslationRule](https://technet.microsoft.com/en-us/library/Gg412803(v=OCS.15))

  - <span></span>  
    [제거-CsOutboundTranslationRule](https://technet.microsoft.com/en-us/library/Gg398556(v=OCS.15))

  - <span></span>  
    [Set-CsOutboundTranslationRule](https://technet.microsoft.com/en-us/library/Gg413073(v=OCS.15))

<!-- end list -->

  - [Get-CsTrunk](https://technet.microsoft.com/en-us/library/JJ205244(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg398224(v=OCS.15))

  - <span></span>  
    [새로운 Set-cstrunkconfiguration](https://technet.microsoft.com/en-us/library/Gg413021(v=OCS.15))

  - <span></span>  
    [제거-Set-cstrunkconfiguration](https://technet.microsoft.com/en-us/library/Gg425943(v=OCS.15))

  - <span></span>  
    [Set-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg398238(v=OCS.15))

  - <span></span>  
    [테스트-Set-cstrunkconfiguration](https://technet.microsoft.com/en-us/library/Gg398137(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [새로운 CsVoiceRegex](https://technet.microsoft.com/en-us/library/Gg412751(v=OCS.15))

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

