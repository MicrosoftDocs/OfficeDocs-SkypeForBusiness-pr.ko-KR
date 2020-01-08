---
title: Lync Server 2013에서 사용자가 호스팅된 음성 사서함을 사용할 수 있도록 설정
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable users for hosted voice mail
ms:assetid: fa559f8f-ef99-43a1-b580-9e998b95efb8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413062(v=OCS.15)
ms:contentKeyID: 48185919
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45872df26989d8d264ce77406bfbce86f321ccf8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982379"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-users-for-hosted-voice-mail-in-lync-server-2013"></a>Lync Server 2013에서 사용자가 호스팅된 음성 사서함을 사용할 수 있도록 설정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-24_

호스트 된 Exchange UM (통합 메시징) 서비스에서 Lync Server 2013 사용자가 음성 메일을 사용 하도록 설정 하려면 다음 절차를 따르세요.

자세한 내용은 계획 설명서의 [Lync Server 2013에서 호스트 된 Exchange 사용자 관리](lync-server-2013-hosted-exchange-user-management.md) 를 참조 하세요.

[집합-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) cmdlet에 대 한 자세한 내용은 Lync Server 관리 셸 설명서를 참조 하세요.

<div>


> [!IMPORTANT]  
> Lync Server 2013 사용자가 호스트 된 음성 메일을 사용 하도록 설정 하기 전에 해당 사용자 계정에 적용 되는 호스팅 음성 메일 정책을 배포 해야 합니다. 자세한 내용은 <A href="lync-server-2013-hosted-voice-mail-policies.md">Lync Server 2013의 호스팅된 음성 메일 정책을</A>참조 하세요.



</div>

<div>

## <a name="to-enable-users-for-hosted-voice-mail"></a>사용자가 호스팅되는 음성 메일을 사용할 수 있도록 설정

1.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

2.  Set-CsUser cmdlet을 실행 하 여 호스팅된 음성 메일에 대 한 사용자 계정을 구성 합니다. 예를 들어 다음을 실행합니다.
    
        Set-CsUser -HostedVoiceMail $True -Identity "contoso\kenmyer"
    
    위의 예는 다음 매개 변수를 설정합니다.
    
      - **HostedVoiceMail** 를 사용 하면 사용자의 음성 메일 통화를 호스트 된 Exchange UM로 라우팅할 수 있습니다. 또한 Microsoft Lync 2013에 "음성 메일 전화 걸기" 표시기가 표시 되도록 신호를 보냅니다.
    
      - **Id** 수정할 사용자 계정을 지정 합니다. Id 값은 다음 형식 중 하나를 사용 하 여 지정할 수 있습니다.
        
          - 사용자의 SIP 주소
        
          - 사용자의 Active Directory 사용자-주 이름
        
          - 사용자의 도메인\\로그온 이름 (예: contoso\\kenmyer)
        
          - 사용자의 Active Directory 도메인 서비스 표시 이름 (예:: 진구 Myer) 표시 이름을 Id 값으로 사용 하는 경우 별표 (\*) 와일드 카드 문자를 사용할 수 있습니다. 예를 들어 Id "\* smith"는 "smith" 문자열 값으로 끝나는 표시 이름을 가진 모든 사용자를 반환 합니다.
        
        <div>
        

        > [!NOTE]  
        > SAM-계정 이름이 포리스트에서 고유 하지 않아도 되므로 사용자의 Active Directory SAM-계정 이름을 Id 값으로 사용할 수 없습니다.

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

