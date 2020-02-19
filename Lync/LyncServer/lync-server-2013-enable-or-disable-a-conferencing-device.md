---
title: 'Lync Server 2013: 회의 장치 사용 또는 사용 안 함'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable a conferencing device
ms:assetid: d5140e38-d015-4706-9bde-cf2fa748c36b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994070(v=OCS.15)
ms:contentKeyID: 51803981
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 81525ef622285f3e17db92948a639ba9f2d1db25
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136235"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-a-conferencing-device-in-lync-server-2013"></a>Lync Server 2013에서 회의 디바이스 사용 또는 사용 안 함

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-20_

**Enable-csmeetingroom** Cmdlet 및 **enable-csmeetingroom** cmdlet을 사용 하 여 회의 장치를 사용 하도록 설정 하 고 사용 하지 않도록 설정 합니다. 이러한 cmdlet은 Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.

<div>


> [!NOTE]  
> 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.



</div>

<div>


<div>

## <a name="enabling-a-conferencing-device"></a>회의 장치 사용

  - 회의 장치를 사용 하도록 설정 하려면 **enable-csmeetingroom** cmdlet을 사용 합니다. 회의 장치를 사용 하도록 설정 하는 경우에는 회의 장치 id, b) 채팅방 계정을 배치할 등록자 풀 및 c) 해당 계정에 할당할 SIP 주소를 포함 해야 합니다.
    
        Enable-CsMeetingRoom -Identity "Redmond Conferencing device" -RegistrarPool "atl-cs-001.litwareinc.com" -SipAddress "sip:RedmondMeetingRoom@litwareinc.com"

</div>

<div>

## <a name="disabling-a-conferencing-device"></a>회의 장치 사용 안 함

  - 회의 장치를 사용 하지 않도록 설정 하려면 **enable-csmeetingroom** cmdlet을 사용 합니다. 사용 하지 않도록 설정할 회의 장치의 id를 지정 했는지 확인 합니다.
    
        Disable-CsMeetingRoom -Identity "sip:RedmondMeetingRoom@litwareinc.com"

</div>

자세한 내용은 [enable-csmeetingroom](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom) Cmdlet 및 [enable-csmeetingroom](https://docs.microsoft.com/powershell/module/skype/Disable-CsMeetingRoom) Cmdlet에 대 한 도움말 항목을 참조 하십시오.

</div>

</div>

<span> </span>

</div>

</div>

</div>

