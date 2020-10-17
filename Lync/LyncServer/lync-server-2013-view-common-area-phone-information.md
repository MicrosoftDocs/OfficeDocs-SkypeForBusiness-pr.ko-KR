---
title: 'Lync Server 2013: 공통 영역 전화 정보 보기'
description: 'Lync Server 2013: 공통 영역 전화 정보를 확인 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View common area phone information
ms:assetid: e652240c-6a3f-4be7-a083-32f24c08e655
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994081(v=OCS.15)
ms:contentKeyID: 51803992
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e4debe9a76118ac0bf1ca711426ce5487009a053
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572474"
---
# <a name="view-common-area-phone-information-in-lync-server-2013"></a>Lync Server 2013에서 공통 영역 전화 정보 보기

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-20_

**Move-cscommonareaphone** cmdlet을 사용 하 여 조직에서 사용 하도록 구성 된 공통 영역 전화에 대 한 정보를 확인할 수 있습니다. 이 cmdlet은 매개 변수 없이 사용 하면 모든 공통 영역 전화에 대 한 정보를 반환 합니다. 선택적 매개 변수를 통해 정보를 필터링 하는 다양 한 방법을 사용할 수 있습니다. 예를 들어 특정 OU (조직 구성 단위) 또는 지정 된 건물에 위치한 모든 대화 상대 개체에 연락처 개체가 있는 모든 공통 영역 전화를 반환할 수 있습니다. **Move-cscommonareaphone** 매개 변수에 대 한 자세한 내용은 [get-move-cscommonareaphone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone)를 참조 하십시오.

Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 **move-cscommonareaphone** 를 실행 합니다.

<div>


<div>

## <a name="viewing-information-about-all-your-common-area-phones"></a>모든 공통 영역 전화에 대 한 정보 보기

  - 모든 공통 영역 전화에 대 한 정보를 보려면 Lync Server 관리 셸에서 다음 명령을 입력 하 고 enter 키를 누릅니다.
    
        Get-CsCommonAreaPhone
    
    다음과 같은 정보가 표시 됩니다.
    
        Identity           : CN=Building 14 Lobby,OU=Redmond,
                             DC=litwareinc,DC=com
        RegistrarPool      : atl-cs-001.litwareinc.com
        Enabled            : True
        SipAddress         : sip:4714e34b-9781-421d-b07a-
                             52056b5b4a56@litwareinc.com
        ClientPolicy       :
        PinPolicy          :
        VoicePolicy        :
        MobilityPolicy     :
        GroupChatPolicy    :
        ConferencingPolicy :
        LineURI            : tel:+14255550712
        DisplayNumber      : 1-425-555-0712
        DisplayName        : Building 14 Lobby
        Description        :
        ExUmEnabled        : False

</div>

자세한 내용은 [move-cscommonareaphone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone) cmdlet에 대 한 도움말 항목을 참조 하십시오.

</div>

</div>

<span> </span>

</div>

</div>

</div>

