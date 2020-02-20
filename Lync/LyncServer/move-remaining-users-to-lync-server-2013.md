---
title: Lync Server 2013로 나머지 사용자 이동
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move remaining users to Lync Server 2013
ms:assetid: 72025e1b-97d1-40e9-8a98-28c018942b48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688090(v=OCS.15)
ms:contentKeyID: 49733689
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27b95ad3ba755839090cb74a174789c71b16d9eb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148617"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-remaining-users-to-lync-server-2013"></a>Lync Server 2013로 나머지 사용자 이동

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-29_

Lync Server 제어판 또는 Lync Server 관리 셸을 사용 하 여 새 Lync Server 2013 배포로 사용자를 이동할 수 있습니다. Lync Server 2013로 원활 하 게 전환 하려면 몇 가지 요구 사항을 충족 해야 합니다. 이 항목의 절차를 완료 하는 데 필요한 필수 구성 요소에 대 한 자세한 내용은 [Configure clients for migration](configure-clients-for-migration.md)을 참조 하십시오. 사용자 이동에 대 한 자세한 단계는 [Phase 4: test users to the 파일럿 풀로 이동](phase-4-move-test-users-to-the-pilot-pool.md)을 참조 하십시오.

<div>


> [!IMPORTANT]  
> Active Directory 사용자 및 컴퓨터 스냅인 또는 Lync Server 2010 관리 도구를 사용 하 여 사용자를 레거시 환경에서 Lync Server 2013로 이동할 수는 없습니다.



</div>

사용자를 Lync Server 2013 풀로 이동 하면 사용자에 대 한 데이터가 새 풀과 연결 된 백 엔드 데이터베이스로 이동 됩니다.

<div>


> [!IMPORTANT]  
> 여기에는 레거시 사용자가 만든 활성 모임이 포함됩니다. 예를 들어 레거시 사용자가 <STRONG>내 모임</STRONG> 회의를 구성한 경우 사용자가 이동 된 후에도 해당 회의를 새 Lync Server 2013 풀에서 계속 사용할 수 있습니다. 이 모임에 액세스하기 위한 세부 정보도 동일한 <STRONG>회의 URL 및 회의 ID</STRONG>가 됩니다. 유일한 차이점은 회의가 Lync Server 2010 풀이 아닌 Lync Server 2013 풀에서 호스트 된다는 것입니다.



</div>

<div>


> [!NOTE]  
> Lync Server 2013의 호 사용자는 업그레이드 된 클라이언트를 동시에 배포할 필요가 없습니다. 새로운 기능은 사용자가 새 클라이언트 소프트웨어로 업그레이드한 경우에만 사용할 수 있습니다.



</div>

<div>

## <a name="post-migration-task"></a>마이그레이션 후 작업

1.  사용자를 이동한 후에는 사용자에게 지정된 회의 정책을 확인합니다.

2.  Lync Server 2013에 있는 사용자가 구성한 모임이 Lync Server 2010에 있는 페더레이션 사용자와 원활 하 게 작동 하도록 하려면 마이그레이션된 사용자에 게 할당 된 회의 정책에서 익명 참가자를 허용 해야 합니다.

3.  익명 참가자를 허용 하는 회의 정책에서는 참가자가 Lync server 2013 제어판에서 선택 된 **익명 사용자를 초대할 수 있도록 허용** 하 고 Lync Server 관리 셸에서 **get-csconferencingpolicy** Cmdlet의 출력에서 **AllowAnonymousParticipantsInMeetings** 를 **True** 로 설정 해야 합니다.

4.  Lync Server 관리 셸을 사용 하 여 회의 정책을 구성 하는 방법에 대 한 자세한 내용은 Lync Server Management Shell 설명서의 [get-csconferencingpolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingPolicy) 를 참조 하십시오.

</div>

</div>

<span> </span>

</div>

</div>

</div>

