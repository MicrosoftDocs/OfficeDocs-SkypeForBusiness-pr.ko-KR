---
title: 'Lync Server 2013: 회의 장치 연락처 개체 만들기 또는 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a conferencing device Contact object
ms:assetid: 62ed64be-379c-417d-9453-511881cf5604
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994035(v=OCS.15)
ms:contentKeyID: 51803945
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ff0a3dbc50b48994752e48ea8889508f2376068
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506175"
---
# <a name="create-or-modify-a-conferencing-device-contact-object-in-lync-server-2013"></a>Lync Server 2013에서 회의 장치 연락처 개체 만들기 또는 수정

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-10-02_

회의 대화방 개체를 만들려면 먼저 장치를 나타내는 Active Directory 사용자 계정을 만듭니다. 그런 다음 **enable-csmeetingroom** cmdlet을 사용 하 여 해당 계정이 회의 장치로 작동 하도록 설정 합니다. 기존 회의 장치의 속성을 변경 해야 하는 경우 **enable-csmeetingroom** cmdlet을 사용 합니다.

이러한 cmdlet은 Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.

<div>


> [!NOTE]  
> 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"를 참조 <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> 하세요.



</div>

<div>


<div>

## <a name="creating-a-conferencing-device"></a>회의 장치 만들기

  - 새 회의 장치를 나타내는 Active Directory 사용자 계정을 만든 후에는 **enable-csmeetingroom** cmdlet을 사용 하 여 사용 하도록 설정 합니다. 회의 장치 id, b) 대화방 계정이 있는 등록자 풀 및 c) 해당 계정에 할당할 SIP 주소를 포함 해야 합니다. 예제:
    
        Enable-CsMeetingRoom -Identity "Redmond Conferencing device" -RegistrarPool "atl-cs-001.litwareinc.com" -SipAddress "sip:RedmondMeetingRoom@litwareinc.com"

</div>

<div>

## <a name="modifying-a-conferencing-device"></a>회의 장치 수정

  - 기존 회의 장치의 속성 값을 수정 하려면 **enable-csmeetingroom** cmdlet을 사용 합니다. 예를 들어 다음 명령은 회의 장치와 연결 된 전화 번호 (LineUri)를 업데이트 합니다.
    
        Set-CsMeetingRoom -Identity "Redmond Conferencing device" -LineUri "tel:+12065551219"

</div>

자세한 내용은 [enable-csmeetingroom](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom) Cmdlet 및 [enable-csmeetingroom](https://docs.microsoft.com/powershell/module/skype/Set-CsMeetingRoom) Cmdlet에 대 한 도움말 항목을 참조 하십시오.

</div>

</div>

<span> </span>

</div>

</div>

</div>

