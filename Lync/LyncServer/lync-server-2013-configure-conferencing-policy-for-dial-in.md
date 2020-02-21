---
title: 'Lync Server 2013: 전화 접속에 대 한 회의 정책 구성'
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
ms.openlocfilehash: 33f84ec3cb900b4283f30d67e318ab10d3625326
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204934"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-conferencing-policy-for-dial-in-in-lync-server-2013"></a>Lync Server 2013에서 전화 접속에 대 한 회의 정책 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-03-21_

회의 정책은 참가자의 회의 환경을 지정하는 사용자 계정 설정이며, 사이트 범위나 사용자 범위에서 만들 수 있습니다. 회의 정책 설정에는 회의 예약 및 참가와 관련된 여러 측면이 포함됩니다. 여러 회의 정책 설정에서는 참가자를 위한 전화 접속 회의가 지원됩니다. 전화 접속 회의를 구성할 경우 이 필드가 조직에 적절하게 설정되어 있는지 확인하고 필요한 경우 필드를 수정해야 합니다.

회의 정책에서 다음 필드를 확인합니다.

  - **참가자가 익명 사용자**   를 초대할 수 있도록 허용이 설정을 사용 하면 모임 이끌이가 익명의 인증 되지 않은 참가자를 모임에 초대할 수 있습니다. 이 설정은 전화 접속 회의에 대해 선택 사항입니다. 이 설정은 기본 전역 회의 정책에서 기본적으로 선택 됩니다.

  - **Pstn 전화 접속 회의**   사용 사용자가 pstn에서 전화 접속을 통해 회의의 오디오 부분에 참가할 수 있도록 허용 합니다. 이 설정은 전화 접속 회의에 필요 합니다. 이 설정은 기본 전역 회의 정책에서 기본적으로 선택 됩니다.

  - **익명 참가자가 전화를 걸 수 있도록 허용**   이 설정을 사용 하면 모임에 이미 가입한 익명 사용자가 전화를 걸어 회의의 오디오 부분에 참가할 수 있습니다. 이 설정은 전화 접속 회의에 대해 선택 사항입니다. 이 설정은 기본 전역 회의 정책에서 기본적으로 선택 되어 있지 않습니다.

  - **Enterprise voice에 대해 사용 하도록 설정 되지 않은 참가자가 전화를 걸 수 있도록 허용**   이 설정을 사용 하면 enterprise Voice를 사용 하도록 설정 되지 않은 모임 참가자 및 이끌이는 전화를 걸어 회의의 오디오 부분에 참가할 수 있습니다. 전화 걸기 통화는 이끌이의 할당 된 음성 정책에 따라 권한이 부여 됩니다. 이 설정은 기본 전역 회의 정책에서 기본적으로 선택 되어 있지 않습니다. 설정 기본값은 사용 안 함입니다.
    
    <div>
    

    > [!NOTE]  
    > 이 기능을 사용 하려면 Enterprise Voice를 사용 하도록 설정 되지 않은 모임 이끌이가 해당 사용자가 구성한 회의에서 전화를 걸 수 있는 권한을 부여 하기 위해 적절 한 음성 정책을 할당 받아야 합니다. Lync Server 관리 셸에서 Enterprise Voice를 사용 하도록 설정 하지 않은 사용자에 게 음성 정책을 할당할 수 있습니다. 사용자에 게 자신에 게 명시적으로 할당 된 음성 정책이 없는 경우 사이트 음성 정책이 전화 걸기 요청에 권한을 부여 하는 데 사용 됩니다. 사이트 음성 정책이 없으면 전역 음성 정책이 사용 됩니다.&nbsp;

    
    </div>

이 섹션의 절차에서는 회의 정책을 수정하는 방법에 대해 설명합니다. 기본 회의 정책에서 참가자 환경을 정의 하는 모든 설정을 구성 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 모임 구성 설정 모음 만들기 또는 수정을](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md)참조 하십시오. 특정 사용자 또는 사용자 그룹에 대 한 회의 정책을 만드는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 회의 정책 만들기 또는 수정을](lync-server-2013-create-or-modify-a-conferencing-policy.md)참조 하십시오. 사용 가능한 모든 회의 정책 설정 목록은 [Lync Server 2013에 대 한 회의 정책 설정 참조](lync-server-2013-conferencing-policy-settings-reference.md)를 참조 하십시오.

<div>

## <a name="to-modify-the-conferencing-policy-for-dial-in"></a>전화 접속 회의 정책을 수정하려면

1.  RTCUniversalServerAdmins 그룹의 구성원이나 **Cs-ServerAdministrator** 또는 **CsAdministrator** 역할의 구성원으로 컴퓨터에 로그온합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **회의**를 클릭합니다.

4.  **회의 정책** 탭에서 회의 정책 이름을 두 번 클릭하여 **회의 정책 편집** 대화 상자를 엽니다.

5.  전화 접속 회의 필드가 조직에 적절하게 설정되어 있는지 확인하고 필요한 경우 설정을 수정합니다.

6.  **커밋**을 클릭합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

