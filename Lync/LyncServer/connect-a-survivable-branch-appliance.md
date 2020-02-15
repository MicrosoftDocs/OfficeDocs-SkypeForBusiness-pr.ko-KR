---
title: Sba (survivable 분기 기기 연결
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Connect a Survivable Branch Appliance
ms:assetid: fe3167e2-d1b1-4cd4-bf30-262e0e7d14e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721948(v=OCS.15)
ms:contentKeyID: 49733886
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77382343fa7736c90ac208f8d13f81bc74969efa
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006524"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connect-a-survivable-branch-appliance"></a>Sba (survivable 분기 기기 연결

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-19_

모든 SBA(Survivable Branch Appliance)는 SBA용 백업 고급 등록자로 작동하는 프런트 엔드 풀과 연결됩니다. 프런트 엔드 풀을 Lync Server 2013로 마이그레이션하면 해당 풀이 업그레이드 되는 동안 Lync Server 2010 프런트 엔드 풀에서 SBA를 분리 해야 하 고, 풀이 Lync Server 2013로 마이그레이션된 후에는 SBA를 업그레이드 된 프런트 엔드 풀과 다시 연결할 수 있습니다. 토폴로지 작성기의 레거시 Lync Server 2010 토폴로지에서 SBA를 삭제 한 다음 SBA를 Lync Server 2013 토폴로지에 추가 하는 것이 여기에 해당 합니다. 레거시 Lync Server 2010 SBA에서 홈 사용자를 먼저 다른 프런트 엔드 풀로 이동한 후 토폴로지에서 해당 SBA를 제거 해야 합니다. Lync Server 2013 토폴로지에서 SBA를 추가한 후에는 해당 사용자를 SBA로 다시 이동할 수 있습니다. 이러한 단계는 아래에 요약되어 있습니다.

1.  레거시 SBA Lync Server 2010에 있는 분기 사용자를 다른 프런트 엔드 풀로 이동 합니다.

2.  레거시 Lync Server 2010 토폴로지에서 SBA를 제거 하 여 백업 등록자를 기존 프런트 엔드 풀과 연결 해제 합니다.

3.  Lync Server 2013 토폴로지에 SBA를 추가 하 고이 새 프런트 엔드 풀을 백업 등록자로 구성 합니다.

4.  분기 사용자를 새 Lync Server 2013 SBA로 이동 합니다.

**Lync Server 2010 SBA 분기 사이트를 토폴로지에 추가**

1.  **토폴로지 작성기**를 엽니다.

2.  왼쪽 창에서 **분기 사이트**를 마우스 오른쪽 단추로 클릭하고 **새 분기 사이트**를 클릭합니다.

3.  **새 분기 사이트 정의** 대화 상자에서 **이름**을 클릭한 다음 분기 사이트의 이름을 입력합니다.

4.  (선택 사항) **설명**을 클릭한 다음 분기 사이트에 대한 의미 있는 설명을 입력합니다.

5.  **다음**을 클릭합니다.

6.  (선택 사항) 다음 **새 분기 사이트 정의** 대화 상자에서 다음 중 일부를 수행합니다.
    
    1.  **구/군/시**를 클릭한 다음 분기 사이트가 있는 구/군/시의 이름을 입력합니다.
    
    2.  **시/도/지역**을 클릭한 다음 분기 사이트가 있는 시/도/지역의 이름을 입력합니다.
    
    3.  국가 코드를 클릭한 다음 분기 사이트가 있는 국가/지역에 대한 두 자리 국가/지역 번호를 입력합니다.

7.  **다음**을 클릭하고 다음 중 하나를 수행합니다.
    
    1.  이 사이트에서 Lync 2010 SBA(Survivable Branch Appliance) 또는 Server를 사용 중인 경우 **이 마법사가 닫히면 새 SBA(Survivable Branch Appliance) 마법사를 엽니다.** 옵션의 선택을 취소해야 합니다. **마침**을 클릭합니다.

8.  레거시 Lync Server 2010 SBA를 Lync Server 2013 프런트 엔드 풀에 연결 하려면 다음을 수행 합니다.
    
    1.  만들어진 분기 사이트를 확장합니다.
    
    2.  **Lync Server 2010**을 마우스 오른쪽 단추로 클릭하고 **새로 만들기**를 클릭합니다.
    
    3.  **SBA(Survivable Branch Appliance)…** 를 클릭합니다.

9.  표시되는 마법사의 지침을 따르십시오. 마법사 항목에 대 한 자세한 내용은 [Define a Sba (survivable Branch 어플라이언스 Or Server in a Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)을 참조 하십시오.
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2010 Sba (survivable Branch 어플라이언스는 Lync Server 2010 모니터링 저장소에만 연결할 수 있습니다.

    
    </div>

10. 이 사이트에서 SBA 또는 지속 가능 분기 서버를 사용하지 않는 경우에는 **이 마법사가 닫히면 새 지속 가능 마법사 열기** 확인란의 선택을 취소한 다음 **마침**을 클릭합니다.

11. 토폴로지에 추가할 각 분기 사이트에 대해 이전 단계를 반복합니다.

</div>

<span> </span>

</div>

</div>

</div>

