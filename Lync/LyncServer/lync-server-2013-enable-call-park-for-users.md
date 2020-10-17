---
title: 'Lync Server 2013: 사용자에 대해 통화 대기를 사용 하도록 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Call Park for users
ms:assetid: 9430763f-3394-467c-9c6d-426bf761604e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398753(v=OCS.15)
ms:contentKeyID: 48184814
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9345cdf2665a5a02d04a372606b95111d870a727
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528785"
---
# <a name="enable-call-park-for-users-in-lync-server-2013"></a>Lync Server 2013의 사용자에 대해 통화 대기를 사용 하도록 설정

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-11_

음성 정책에서 통화 대기를 사용 하도록 설정 하기 전까지 사용자는 통화를 대기 시키거나 대기 중인 통화를 검색할 수 없습니다.

<div>


> [!NOTE]  
> 기본적으로 모든 사용자에 대해 통화 대기를 사용 하지 않도록 설정 되어 있습니다.



</div>

전역 범위나 사이트 범위 또는 사용자 범위에서 통화 대기를 사용 하도록 설정할 수 있습니다. 사용자 범위는 사이트 범위보다 우선하고 사이트 범위는 전역 범위보다 우선합니다. 음성 정책이 여러 개인 경우에는 모든 정책을 검토 하 여 전역 정책 뿐 아니라 통화 대기를 사용 하도록 설정 합니다.

<div>

## <a name="to-use-lync-server-control-panel-to-enable-call-park-for-users"></a>Lync Server 제어판을 사용 하 여 사용자에 대해 통화 대기를 사용 하도록 설정 하려면

1.  **RTCUniversalServerAdmins** 그룹의 구성원이나 **CsVoiceAdministrator**, **CsServerAdministrator** 또는 **CsAdministrator** 관리 역할의 구성원으로 컴퓨터에 로그온합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **음성 라우팅**을 클릭합니다.

4.  **음성 정책** 탭을 클릭합니다.

5.  기존 음성 정책을 두 번 클릭하여 **음성 정책 편집** 대화 상자를 엽니다.

6.  **전화 걸기 기능**에서 **통화 대기 사용**을 선택합니다.

7.  **확인**을 클릭하여 음성 정책을 저장합니다.

</div>

<div>

## <a name="to-use-cmdlets-to-enable-call-park-for-users"></a>Cmdlet을 사용 하 여 사용자에 대 한 통화 대기를 설정 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원이나 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 관리 역할의 구성원으로 컴퓨터에 로그온합니다.

2.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

3.  을 실행합니다.
    
        Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
    
    예를 들어 기본 전역 음성 정책에 대해 통화 대기를 사용 하도록 설정 하려면 다음을 수행 합니다.
    
        Set-CsVoicePolicy -EnableCallPark $true

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 음성 정책 만들기 및 PSTN 사용 레코드 구성](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

