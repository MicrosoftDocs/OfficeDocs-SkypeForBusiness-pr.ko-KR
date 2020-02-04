---
title: 'Lync Server 2013: 공통 영역 전화 정보 보기'
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
ms.openlocfilehash: 38614b2993ddd9ad3fe3a662a334440a1d1287b7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757462"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-common-area-phone-information-in-lync-server-2013"></a>Lync Server 2013에서 공통 영역 전화 정보 보기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-20_

**CsCommonAreaPhone** cmdlet을 사용 하 여 조직에서 사용 하도록 구성 된 공통 영역 전화에 대 한 정보를 볼 수 있습니다. 매개 변수 없이 사용 하면이 cmdlet은 모든 공통 지역 전화에 대 한 정보를 반환 합니다. 선택적 매개 변수는 다양 한 방법으로 정보를 필터링 하는 방법을 제공 합니다. 예를 들어 지정 된 조직 구성 단위 (OU) 또는 지정 된 건물에 위치한 모든 연락처 개체에 연락처 개체가 있는 공통 영역 전화기를 모두 반환할 수 있습니다. **Get-CsCommonAreaPhone** 매개 변수에 대 한 자세한 내용은 [get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone)을 참조 하세요.

Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 **CsCommonAreaPhone** 를 실행 합니다.

<div>


<div>

## <a name="viewing-information-about-all-your-common-area-phones"></a>모든 공통 지역 전화에 대 한 정보 보기

  - 모든 공통 지역 전화에 대 한 정보를 보려면 Lync Server 관리 셸에서 다음 명령을 입력 한 다음 enter 키를 누릅니다.
    
        Get-CsCommonAreaPhone
    
    다음과 같은 정보를 얻을 수 있습니다.
    
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

자세한 내용은 Get-help cmdlet에 대 한 도움말 항목을 [CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

