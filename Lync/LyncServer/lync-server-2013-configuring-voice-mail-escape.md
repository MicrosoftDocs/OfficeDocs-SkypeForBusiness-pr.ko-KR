---
title: 'Lync Server 2013: 음성 메일 이스케이프 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring voice mail escape
ms:assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688157(v=OCS.15)
ms:contentKeyID: 49733761
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c3faf28bdd85f32de1560d35aaf35392fef9746
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516955"
---
# <a name="configuring-voice-mail-escape-in-lync-server-2013"></a>Lync Server 2013에서 음성 메일 이스케이프 구성

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-22_

사용자가 휴대폰에 대한 동시 전화 신호 울림 기능을 구성한 경우 휴대폰이 꺼져 있거나, 배터리가 방전되었거나, 망 범위를 벗어나 있는 경우 일반적으로 발신자가 사용자의 개인 음성 메일로 라우팅됩니다. Lync Server 2013를 사용 하는 경우 사용자는 회사 음성 메일 시스템으로 라우팅되는 비즈니스 관련 통화가 있을 수 있습니다. 특히 타이머를 구성할 수 있고 통화를 정의 된 시간 범위 내에서 반송파의 음성 메일로 응답 하는 경우에는 Lync Server가 반송파의 음성 메일 시스템과 사용자의 개인 음성 사서함에서 연결을 끊고 회사 시스템의 나머지 끝점이 계속 해 서 울릴 것입니다. 이렇게 해서 발신자가 자동으로 사용자의 회사 음성 메일로 라우팅됩니다.

다음 매개 변수를 사용 하 여 음성 정책 수준에서 Lync Server 관리 셸 cmdlet **set-csvoicepolicy**을 사용 하 여이 구성을 수행 합니다.

<div>

## <a name="to-configure-voice-mail-escape"></a>음성 메일 이스케이프를 구성 하려면

1.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

2.  **Set-CsVoicePolicy**에 다음 매개 변수를 지정합니다.
    
      - **EnableVoicemailEscapeTimer** - 이스케이프 타이머를 사용하거나 사용하지 않도록 설정합니다.
    
      - **PSTNVoicemailEscapeTimer** - 시간 제한 값을 밀리초 단위로 지정합니다. 기본값은 1500밀리초이며 0~8000밀리초 범위에서 값을 지정할 수 있습니다.

</div>

<div>

## <a name="example"></a>예제

    Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
    
    Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 호출 기능 및 권한을 부여 하도록 음성 정책 및 PSTN 사용 레코드 구성](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

