---
title: (선택 사항) 회의 참가/나가기 알림 활성화/비활성화
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Enable and disable conference join and leave announcements
ms:assetid: c9529568-e66c-48d8-aef2-9072f9c336ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398834(v=OCS.15)
ms:contentKeyID: 48185403
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b8e75a0d2ed81a515540f2a8a1811998a85d44c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755752"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-enable-and-disable-conference-join-and-leave-announcements-in-lync-server-2013"></a>(선택 사항) Lync Server 2013에서 회의 참가/나가기 알림 활성화/비활성화

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-30_

전화 접속 사용자가 회의에 참가 하거나 나갈 때, 회의 알림 응용 프로그램은 소리를 재생 하거나 자신의 이름을 말하기 때문에 해당 입구 또는 종료를 알릴 수 있습니다. Cmdlet을 실행 하 여 알림이 작동 하는 방식을 변경할 수 있습니다. 이 단계는 선택 사항입니다.

<div>

## <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a>회의 참가를 수정 하 고 알림 동작을 종료 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 **Cs-serveradministrator** 또는 **csadministrator** 역할의 구성원으로 컴퓨터에 로그온 합니다.

2.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

3.  명령 프롬프트에서 다음을 실행 합니다.
    
        Get-CsDialinConferencingConfiguration
    
    이 cmdlet은 참가자가 전화 접속 회의에 참가 하거나 나갈 때 Lync 서버가 응답 하는 방법 및 회의 참가 시 사용자의 이름을 기록 하는 데 필요한 지 여부에 대 한 정보를 검색 합니다.

4.  명령 프롬프트에서 다음을 실행 합니다.
    
        Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
        [-EnableNameRecording <$true | $false>]
        [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
        [-EntryExitAnnouncementsType <UseNames | ToneOnly]
    
    **EnableNameRecording**   는 회의를 시작 하기 전에 익명 참가자가 자신의 이름을 기록해 달라고 요청 하는지 여부를 결정 합니다. 기본값은 "$true" 이며,이는 익명 참가자가 회의에 참가할 때 이름을 명시 하 라는 메시지를 표시 하는 것을 의미 합니다. (인증 된 참가자는 해당 사용자의 표시 이름이 대신 사용 되므로 이름을 기록 하지 않습니다.)
    
    **EntryExitAnnouncementsEnabledByDefault**   는 알림을 기본적으로 설정 또는 해제 하는지 여부를 나타냅니다. 기본값은 "$false" 이며,이는 기본적으로 참가자가 회의에 참가 하거나 나갈 때 공지 사항이 없음을 의미 합니다. 모임 이끌이는 모임을 예약할 때이 설정을 무시할 수 있습니다.
    
    **EntryExitAnnouncementsType**   는 참가자가 참여 하거나 알림을 사용할 수 있는 전화 회의를 떠날 때마다 수행 되는 작업을 나타냅니다. 기본값은 "UseNames" 이며, 공지 사항이 설정 된 경우 ": 진구 Myer 님이 회의에 참가 했습니다" 라는 알림을 의미 합니다.
    
    전역 범위 또는 사이트 범위에서 이러한 설정을 구성할 수 있습니다. 사이트 범위에서 구성 된 설정은 전역 범위에서 구성 된 설정 보다 우선 합니다.
    
    예를 들면 다음과 같습니다.
    
        Set-CsDialinConferencingConfiguration -Identity site:Redmond
        -EnableNameRecording $false
        -EntryExitAnnouncementsEnabledByDefault $true
        -EntryExitAnnouncementsType ToneOnly
    
    이 예제에서는 사이트 범위에서 Redmond에 대 한 설정을 구성 합니다. 알림은 설정 되어 있지만 참가자가 회의에 참가할 때 이름을 말할 것인지 묻는 메시지가 표시 되지 않습니다. 참가자가 회의를 시작 하거나 종료할 때 신호음이 재생 됩니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

