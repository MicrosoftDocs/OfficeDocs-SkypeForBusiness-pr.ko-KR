---
title: 'Lync Server 2013: 사용자 용 통화 파킹 사용'
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
ms.openlocfilehash: cd89ba10f5cae16e88c65e6e56178fc517c71213
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736248"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-call-park-for-users-in-lync-server-2013"></a>Lync Server 2013에서 사용자 용 통화 공원 사용

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-11_

음성 정책에서 통화 대기를 사용할 수 있을 때까지 사용자는 통화를 대기 시 키 지 않거나 파킹 된 통화를 검색 하지 못합니다.

<div>


> [!NOTE]  
> 기본적으로 모든 사용자에 대해 통화 대기를 사용할 수 없습니다.



</div>

전역 범위 또는 사이트 범위 또는 사용자 범위에서 통화 파킹 기능을 사용 하도록 설정할 수 있습니다. 사용자 범위는 사이트 범위 보다 우선 하며 사이트 범위는 전역 범위 보다 우선 합니다. 음성 정책이 여러 개 있는 경우 모든 정책을 검토 하 여 전역 정책만이 아닌 통화 대기 기능을 사용 하도록 설정 하세요.

<div>

## <a name="to-use-lync-server-control-panel-to-enable-call-park-for-users"></a>Lync Server 제어판을 사용 하 여 사용자를 위한 통화 파킹 사용

1.  **RTCUniversalServerAdmins** 그룹의 구성원 또는 **CsVoiceAdministrator**, **Csserveradministrator**또는 **csadministrator** 관리 역할의 구성원으로 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **음성 라우팅을**클릭 합니다.

4.  **음성 정책** 탭을 클릭 합니다.

5.  기존 음성 정책을 두 번 클릭 하 여 **음성 정책 편집** 대화 상자를 엽니다.

6.  **호출 기능**에서 **통화 공원 사용**을 선택 합니다.

7.  **확인** 을 클릭 하 여 음성 정책 저장

</div>

<div>

## <a name="to-use-cmdlets-to-enable-call-park-for-users"></a>Cmdlet을 사용 하 여 사용자를 위한 통화 파킹 사용

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 관리 역할의 구성원으로 컴퓨터에 로그온 합니다.

2.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

3.  런
    
        Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
    
    예를 들어 기본 전역 음성 정책에 대 한 통화 파킹 기능을 사용 하도록 설정 하려면 다음을 수행 합니다.
    
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

