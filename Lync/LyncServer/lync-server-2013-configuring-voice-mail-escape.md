---
title: 'Lync Server 2013: 음성 메일 이스케이프 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring voice mail escape
ms:assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688157(v=OCS.15)
ms:contentKeyID: 49733761
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f08e12b97c51d68b4b08d10692802cb035ce8f0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979914"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-voice-mail-escape-in-lync-server-2013"></a>Lync Server 2013에서 음성 메일 esc 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-22_

사용자가 휴대폰으로 동시 신호음을 구성 하는 경우, 휴대 전화를 끄거나, 배터리 전원이 꺼져 있거나, 범위를 벗어나면 일반적으로 발신자가 사용자의 개인 음성 메일로 라우팅됩니다. Lync Server 2013을 사용 하면 사용자가 회사 음성 메일 시스템으로 라우팅되는 비즈니스 관련 통화를 선택할 수 있습니다. 특히 타이머를 구성할 수 있으며, 통화를 지정 된 시간 범위 내에서 반송파의 음성 메일을 통해 수신 되는 경우, Lync Server는 해당 통신 회사의 음성 메일 시스템 (및 사용자의 개인 음성 메일)과 사용자의 남은 상태를 연결 해제 합니다. 회사 시스템의 끝점은 계속 해 서 울립니다. 이 방법으로 발신자는 자동으로 사용자의 회사 음성 메일로 라우팅됩니다.

이 구성은 다음 매개 변수를 사용 하 여 음성 정책 수준에서 Lync Server 관리 셸 cmdlet, **Set-CsVoicePolicy**를 사용 하 여 수행 됩니다.

<div>

## <a name="to-configure-voice-mail-escape"></a>음성 메일 esc를 구성 하려면

1.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

2.  다음 매개 변수를 **CsVoicePolicy**로 지정 합니다.
    
      - **EnableVoicemailEscapeTimer** -이탈 타이머를 사용 하거나 사용 하지 않도록 설정 합니다.
    
      - **PSTNVoicemailEscapeTimer** -제한 시간 값 (밀리초)을 지정 합니다. 기본값은 1500 밀리초 이며, 값의 범위는 0 밀리초 ~ 8000 밀리초입니다.

</div>

<div>

## <a name="example"></a>예

    Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
    
    Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 통화 기능 및 권한을 부여하도록 음성 정책 및 PSTN 사용 레코드 구성](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

