---
title: 'Lync Server 2013: 사용자가 호스팅된 음성 메일을 사용할 수 있도록 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable users for hosted voice mail
ms:assetid: fa559f8f-ef99-43a1-b580-9e998b95efb8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413062(v=OCS.15)
ms:contentKeyID: 48185919
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6dc71125b42fab144b1c6ba15064e84c6be50b57
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138039"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-users-for-hosted-voice-mail-in-lync-server-2013"></a>Lync Server 2013에서 호스팅된 음성 메일에 대해 사용자를 사용 하도록 설정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-24_

호스팅된 Exchange UM (통합 메시징) 서비스에서 Lync Server 2013 사용자가 음성 메일을 사용할 수 있도록 설정 하는 절차를 수행 합니다.

자세한 내용은 계획 설명서의 [Lync Server 2013에서 호스팅된 Exchange 사용자 관리](lync-server-2013-hosted-exchange-user-management.md) 를 참조 하십시오.

[CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) cmdlet에 대 한 자세한 내용은 Lync Server 관리 셸 설명서를 참조 하세요.

<div>


> [!IMPORTANT]  
> Lync Server 2013 사용자를 호스팅된 음성 메일에 대해 사용 하도록 설정 하기 전에 해당 사용자 계정에 적용 되는 호스팅된 음성 메일 정책을 배포 해야 합니다. 자세한 내용은 <A href="lync-server-2013-hosted-voice-mail-policies.md">Lync Server 2013에서 호스팅된 음성 메일 정책</A>를 참조 하십시오.



</div>

<div>

## <a name="to-enable-users-for-hosted-voice-mail"></a>사용자가 호스팅된 음성 메일을 사용할 수 있도록 설정하려면

1.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

2.  Set-CsUser cmdlet를 실행하여 호스팅된 음성 메일에 대한 사용자 계정을 구성합니다. 예를 들어 다음을 실행합니다.
    
        Set-CsUser -HostedVoiceMail $True -Identity "contoso\kenmyer"
    
    위의 예는 다음 매개 변수를 설정합니다.
    
      - **HostedVoiceMail**은 사용자의 음성 사서함 통화를 호스팅된 Exchange UM으로 라우팅할 수 있도록 해줍니다. 또한 Microsoft Lync 2013에서 "음성 메일 통화" 표시기를 밝게 표시 합니다.
    
      - **Identity**는 수정할 사용자 계정을 지정합니다. Identity 값은 다음 형식 중 하나를 사용하여 지정할 수 있습니다.
        
          - 사용자의 SIP 주소
        
          - 사용자의 Active Directory 사용자 계정 이름
        
          - 사용자의 도메인\\로그온 이름 (예: contoso\\kenmyer)
        
          - 사용자의 Active Directory 도메인 서비스 표시 이름(예: Ken Myer). 표시 이름을 Id 값으로 사용 하는 경우 별표 (\*) 와일드 카드 문자를 사용할 수 있습니다. 예를 들어 Id "\* smith"는 문자열 값 "smith"로 끝나는 표시 이름을 가진 모든 사용자를 반환 합니다.
        
        <div>
        

        > [!NOTE]  
        > SAM 계정 이름은 포리스트에서 고유하지 않아도 되므로 사용자의 Active Directory SAM 계정 이름을 Identity 값으로 사용할 수 없습니다.

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

