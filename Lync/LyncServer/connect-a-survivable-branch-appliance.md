---
title: SBA(Survivable Branch Appliance) 연결
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Connect a Survivable Branch Appliance
ms:assetid: fe3167e2-d1b1-4cd4-bf30-262e0e7d14e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721948(v=OCS.15)
ms:contentKeyID: 49733886
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c76e70278d709b52388c22714db85f9bae4610d9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976239"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connect-a-survivable-branch-appliance"></a>SBA(Survivable Branch Appliance) 연결

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-19_

모든 Survivable Branch 기기 (SBA)는 SBA에 대 한 백업 등록 기관 역할을 하는 프런트 엔드 풀과 연결 되어 있습니다. 프런트 엔드 풀을 Lync Server 2013로 마이그레이션할 때 풀을 업그레이드 하는 동안에는 Lync Server 2010 프런트 엔드 풀에서 연결 되어야 합니다. 풀을 Lync Server 2013로 마이그레이션한 후에는 SBA를 업그레이드 된 프런트 엔드 풀에 다시 연결할 수 있습니다. 여기에는 토폴로지 작성기에서 레거시 Lync Server 2010 토폴로지에서의 SBA를 삭제 한 다음 Lync Server 2013 토폴로지에 추가 됩니다. 레거시 Lync Server 2010 SBA의 사용자가 먼저 다른 프런트 엔드 풀로 이동한 후에는 토폴로지에서 SBA를 제거 해야 합니다. Lync Server 2013 토폴로지에 추가 된 후에는 해당 사용자를 다시 SBA로 이동할 수 있습니다. 이러한 단계는 다음과 같이 요약할 수 있습니다.

1.  레거시 SBA Lync Server 2010에 있는 분기 사용자를 다른 프런트 엔드 풀로 이동 합니다.

2.  기존 프런트 엔드 풀을 백업 등록 기관으로 연결 해제 하려면 레거시 Lync Server 2010 토폴로지에서 SBA를 제거 합니다.

3.  Lync Server 2013 토폴로지에 SBA를 추가 하 고이 새 프런트 엔드 풀을 백업 등록 기관으로 구성 합니다.

4.  분기 사용자를 새 Lync Server 2013 SBA로 이동 합니다.

**사용자의 토폴로지에 Lync Server 2010 SBA 분기 사이트 추가**

1.  **토폴로지 작성기**를 엽니다.

2.  왼쪽 창에서 **분기 사이트**를 마우스 오른쪽 단추로 클릭 한 다음 **새 분기 사이트**를 클릭 합니다.

3.  **새 분기 사이트 정의** 대화 상자에서 **이름을**클릭 한 다음 분기 사이트의 이름을 입력 합니다.

4.  ) **설명을**클릭 한 다음 분기 사이트에 대 한 의미 있는 설명을 입력 합니다.

5.  **다음**을 클릭 합니다.

6.  ) 다음 **새 분기 사이트 정의** 대화 상자에서 다음 중 하나를 수행 합니다.
    
    1.  **도시**를 클릭 한 다음 지점 사이트가 있는 도시의 이름을 입력 합니다.
    
    2.  **상태/지역을**클릭 한 다음 분기 사이트가 있는 상태 또는 지역의 이름을 입력 합니다.
    
    3.  **국가 코드**를 클릭 한 다음 분기 사이트가 있는 국가/지역에 대 한 두 자리 통화 코드를 입력 합니다.

7.  **다음**을 클릭 하 고 다음 중 하나를 수행 합니다.
    
    1.  이 사이트에서 Lync 2010 Survivable Branch 기기 또는 서버를 사용 하는 경우 **마법사를 닫을 때 새 Survivable 마법사 열기** 옵션을 선택 취소 해야 합니다. **마침**을 클릭합니다.

8.  레거시 Lync Server 2010 SBA를 Lync Server 2013 프런트 엔드 풀에 연결 하려면 다음을 수행 합니다.
    
    1.  생성 된 분기 사이트를 확장 합니다.
    
    2.  **Lync Server 2010** 을 마우스 오른쪽 단추로 클릭 한 다음 **새로 만들기**를 클릭 합니다.
    
    3.  **Survivable Branch 기기 ...** 를 클릭 합니다.

9.  열리는 마법사의 지침을 따릅니다. 마법사 항목에 대 한 자세한 내용은 [Lync Server 2013에서 Survivable Branch 기기 또는 서버 정의](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)를 참조 하세요.
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2010 Survivable Branch 기기는 Lync Server 2010 모니터링 저장소에만 연결할 수 있습니다.

    
    </div>

10. 이 사이트에서 Survivable Branch 기기 또는 서버를 사용 하 고 있지 않은 경우 마법사를 **닫을 때 새 Survivable 마법사 열기** 확인란의 선택을 취소 하 고 **마침을**클릭 합니다.

11. 토폴로지에 추가 하려는 각 분기 사이트에 대해 앞의 단계를 반복 합니다.

</div>

<span> </span>

</div>

</div>

</div>

