---
title: 'Lync Server 2013: 신뢰할 수 있는 응용 프로그램 목록 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View a list of trusted applications
ms:assetid: f09300b3-67cf-4e70-a51a-23d62479b913
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182604(v=OCS.15)
ms:contentKeyID: 48185844
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d5f9d112e045e753147f7fcffa875177a6feb0d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757502"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-a-list-of-trusted-applications-in-lync-server-2013"></a>Lync Server 2013에서 신뢰할 수 있는 응용 프로그램 목록 보기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-21_

Lync Server 2013 제어판을 사용 하 여 Lync Server 2013 환경에서 배포한 신뢰할 수 있는 응용 프로그램 목록을 볼 수 있습니다. 신뢰할 수 있는 응용 프로그램은 Lync Server 2013에서 신뢰 하는 Microsoft 통합 커뮤니케이션 관리 API (인스턴스 MA) 3.0 Core SDK를 기반으로 하는 응용 프로그램입니다. 이 신뢰 관계는 다음 목록에 요약 되어 있습니다.

  - 신뢰할 수 있는 응용 프로그램이 Lync Server의 인증에 대해 문제가 되지 않습니다.

  - 신뢰할 수 있는 응용 프로그램은 SIP 트랜잭션, 연결 또는 VoIP (인터넷 프로토콜) 전화를 통해 보내는 Voice 용 Lync 서버에 의해 제한 되지 않습니다.

  - 신뢰 하는 응용 프로그램은 모든 사용자를 가장할 수 있으며 rosters에 표시 하지 않고 회의에 참가할 수 있습니다.

  - 신뢰할 수 있는 응용 프로그램은 가용성이 높고 탄력적입니다.

Lync Server 제어판에서 응용 프로그램 이름, 실행 중인 풀, 사용 하는 포트 등을 볼 수 있습니다.

<div>

## <a name="to-view-a-list-of-trusted-applications"></a>신뢰할 수 있는 응용 프로그램 목록 보기

1.  CsServerAdministrator, CsAdministrator, CsHelpDesk 또는 Csserveradministrator 관리자 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다. Lync Server 2013에서 사용할 수 있는 미리 정의 된 관리 역할에 대 한 자세한 내용은 [Lync server 2013의 역할 기반 액세스 제어 계획](lync-server-2013-planning-for-role-based-access-control.md)을 참조 하세요.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **토폴로지** 를 클릭 하 고 **신뢰할 수 있는 응용 프로그램**을 클릭 합니다.

4.  필요한 경우 **신뢰할 수 있는 응용 프로그램** 페이지에서 열 머리글을 클릭 하 여 응용 프로그램을 정렬 합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013 토폴로지 관리](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

