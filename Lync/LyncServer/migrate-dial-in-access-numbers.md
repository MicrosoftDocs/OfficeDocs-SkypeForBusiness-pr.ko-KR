---
title: 전화 접속 액세스 번호 마이그레이션
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate dial-in access numbers
ms:assetid: e0dfaed2-64c7-45cb-aaa9-d6117a26625d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721909(v=OCS.15)
ms:contentKeyID: 49733843
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0638ae76a9aa1108b11c1d1ff98fdd3eef08c938
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762946"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-dial-in-access-numbers"></a>전화 접속 액세스 번호 마이그레이션

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-19_

Lync Server 2010에서 전화 접속 액세스 번호를 Lync Server 2013으로 마이그레이션하면 contact 개체를 마이그레이션하기 위해 **CsApplicationEndpoint** cmdlet을 실행 해야 합니다. Lync server 2010 및 Lync Server 2013 공존 기간 중에 Lync Server 2013에서 만든 전화 접속 액세스 번호는이 섹션에서 설명 하는 대로 Lync Server 2010에서 만든 전화 접속 액세스 번호와 유사 하 게 작동 합니다.

Lync server 2010에서 만든 전화 접속 액세스 번호로, lync server 2013로 이동 하거나, 이전에 또는 마이그레이션 중에 Lync Server 2013에서 만든 연결에는 다음과 같은 특징이 있습니다.

  - Office Communications Server 2007 R2 모임 초대 및 전화 접속 액세스 번호 페이지에는 나타나지 않습니다.

  - Lync Server 2010 모임 초대 및 전화 접속 액세스 번호 페이지에 표시 됩니다.

  - Lync Server 2013 모임 초대 및 전화 접속 액세스 번호 페이지에 표시 됩니다.

  - Office Communications Server 2007 R2 관리 도구에서 보거나 수정할 수 없습니다.

  - Lync Server 2010 제어판 및 Lync Server 2010 관리 셸에서 보고 수정할 수 있습니다.

  - Lync Server 2013 제어판 및 Lync Server 2013 관리 셸에서 보고 수정할 수 있습니다.

  - CsDialinConferencingAccessNumber cmdlet을 Priority 매개 변수를 사용 하 여 영역 내에서 다시 시퀀싱 될 수 있습니다.

Lync Server 2010 풀의 역할을 해제 하기 전에 Lync Server 2010 풀을 가리키는 전화 접속 액세스 번호 마이그레이션을 완료 해야 합니다. 다음 절차에 설명 된 대로 전화 접속 액세스 번호 마이그레이션을 완료 하지 않은 경우에는 액세스 번호로 수신 되는 호출이 실패 합니다.

<div>


> [!IMPORTANT]  
> Lync Server 2010 풀의 역할을 해제 하기 전에이 절차를 수행 해야 합니다.



</div>

<div>


> [!NOTE]  
> 짧은 서비스 중단 기간이 있는 경우 네트워크 사용량이 낮을 때 전화 접속 액세스 번호를 이동 하는 것이 좋습니다.



</div>

**전화 접속 액세스 번호를 확인 하 고 이동 하려면**

1.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

2.  각 전화 접속 액세스 번호를 Lync Server 2013에서 호스팅되는 풀로 이동 하려면 명령줄 실행에서 다음을 수행 합니다.
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

3.  Lync Server 제어판을 엽니다.

4.  왼쪽 탐색 모음에서 **회의**를 클릭 합니다.

5.  **전화 접속 액세스 번호** 탭을 클릭 합니다.

6.  마이그레이션하는 Lync Server 2010 풀에 대 한 전화 접속 액세스 번호가 남아 있지 않은지 확인 합니다.
    
    <div>
    

    > [!NOTE]  
    > 모든 전화 접속 액세스 번호가 Lync Server 2013 풀을 가리키는 경우 Lync Server 2010 풀을 해제할 수 있습니다.

    
    </div>

**Lync Server 제어판을 사용 하 여 전화 접속 액세스 번호 마이그레이션 확인**

1.  **Csuseradministrator** 역할 또는 **csadministrator** 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.

2.  Lync Server 제어판을 엽니다.

3.  왼쪽 탐색 모음에서 **회의**를 클릭 합니다.

4.  **전화 접속 액세스 번호** 탭을 클릭 합니다.

5.  모든 전화 접속 액세스 번호가 Lync Server 2013에서 호스트 되는 풀로 마이그레이션 되었는지 확인 합니다.

**Lync Server Management Shell을 사용 하 여 전화 접속 액세스 번호 마이그레이션 확인**

1.  Lync Server Management Shell을 엽니다.

2.  마이그레이션된 모든 전화 접속 회의 액세스 번호를 명령줄 실행에서 반환 하려면 다음을 수행 합니다.
    
        Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}

3.  모든 전화 접속 액세스 번호가 Lync Server 2013에서 호스트 되는 풀로 마이그레이션 되었는지 확인 합니다.

</div>

<span> </span>

</div>

</div>

</div>

