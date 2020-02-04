---
title: 'Lync Server 2013: 전화 접속에 대한 회의 정책 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure conferencing policy for dial-in
ms:assetid: 9bf926d6-0248-4352-98c3-9c5a333debbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398810(v=OCS.15)
ms:contentKeyID: 48184979
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 107c5fcf4b341c652cd4044fe47f4b650cf5adb4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739348"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-conferencing-policy-for-dial-in-in-lync-server-2013"></a>Lync Server 2013에서 전화 접속에 대한 회의 정책 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-03-21_

회의 정책은 참가자의 회의 환경을 지정 하는 사용자 계정 설정입니다. 사이트 범위 또는 사용자 범위를 사용 하 여 회의 정책을 만들 수 있습니다. 회의 정책 설정에는 회의 예약 및 참여의 여러 측면이 포함 됩니다. 여러 회의 정책 설정이 참가자에 대 한 전화 접속 회의를 지원 합니다. 전화 접속 회의를 구성 하는 경우 이러한 필드가 조직에 맞게 적절 하 게 설정 되어 있는지 확인 하 고 필요에 따라 수정 해야 합니다.

회의 정책에서 다음 필드를 확인 합니다.

  - **참가자가 익명 사용자**   를 초대할 수 있도록 허용이 설정을 사용 하면 모임 이끌이가 익명 (인증 되지 않은) 참가자를 모임에 초대할 수 있습니다. 이 설정은 전화 접속 회의에 선택 사항입니다. 기본 전역 회의 정책에이 설정이 기본적으로 선택 되어 있습니다.

  - **Pstn 전화 접속 회의**   설정이 설정을 사용 하면 사용자가 pstn에서 전화 접속을 통해 컨퍼런스의 오디오 부분에 참가할 수 있습니다. 이 설정은 전화 접속 회의에 필요 합니다. 기본 전역 회의 정책에이 설정이 기본적으로 선택 되어 있습니다.

  - **익명 참가자가 전화를 걸 수 있도록 허용**   이 설정을 사용 하면 이미 모임에 참가 한 익명 사용자가 전화 번호로 전화를 걸어 회의의 오디오 부분에 참가할 수 있습니다. 이 설정은 전화 접속 회의에 선택 사항입니다. 기본 전역 회의 정책에서는이 설정이 기본적으로 선택 되어 있지 않습니다.

  - **엔터프라이즈 음성에 대해 참가자가 설정 되지 않은 경우 전화를 걸 수 있음**   이 설정을 사용 하면 엔터프라이즈 음성에 대해 설정 되지 않은 모임 참가자와 이끌이는 전화 번호로 전화를 걸어 회의 오디오 부분에 참가할 수 있습니다. 전화 접속 통화는 이끌이의 지정 된 음성 정책에 따라 승인 됩니다. 기본 전역 회의 정책에서는이 설정이 기본적으로 선택 되어 있지 않습니다. 설정 기본값을 사용할 수 없습니다.
    
    <div>
    

    > [!NOTE]  
    > 이 접근 권한 값을 사용 하도록 설정 하려면 Enterprise Voice에 대해 설정 되지 않은 모임 이끌이는 해당 사용자가 구성한 회의 로부터 전화를 받지 않도록 적절 한 음성 정책을 할당 받아야 합니다. 음성 정책은 Lync Server 관리 셸에서 엔터프라이즈 음성에 대해 설정 되지 않은 사용자에 게 할당할 수 있습니다. 사용자가 자신에 게 명시적으로 할당 된 음성 정책이 없는 경우 사이트 음성 정책이 전화 접속 요청에 권한을 부여 하는 데 사용 됩니다. 사이트 음성 정책이 없는 경우 전역 음성 정책이 사용 됩니다.&nbsp;

    
    </div>

이 섹션의 절차에서는 회의 정책을 수정 하는 방법에 대해 설명 합니다. 기본 회의 정책에서 참가자 환경을 정의 하는 모든 설정을 구성 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 모임 구성 설정 모음 만들기 또는 수정을](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md)참조 하세요. 특정 사용자 또는 사용자 그룹에 대해 회의 정책을 만드는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 회의 정책 만들기 또는 수정을](lync-server-2013-create-or-modify-a-conferencing-policy.md)참조 하세요. 사용 가능한 모든 회의 정책 설정 목록은 [Lync Server 2013에 대 한 회의 정책 설정 참조](lync-server-2013-conferencing-policy-settings-reference.md)를 참조 하세요.

<div>

## <a name="to-modify-the-conferencing-policy-for-dial-in"></a>전화 접속에 대 한 회의 정책을 수정 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 **Cs-serveradministrator** 또는 **csadministrator** 역할의 구성원으로 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **회의**를 클릭 합니다.

4.  **회의 정책** 탭에서 회의 정책 이름을 두 번 클릭 하 여 **회의 정책 편집** 대화 상자를 엽니다.

5.  전화 접속 회의 필드가 조직에 적합 한지 확인 하 고 필요한 경우 설정을 수정 합니다.

6.  **커밋**을 클릭합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

