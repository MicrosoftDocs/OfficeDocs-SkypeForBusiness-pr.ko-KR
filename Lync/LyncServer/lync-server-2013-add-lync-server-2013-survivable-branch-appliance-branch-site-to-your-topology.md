---
title: 토폴로지에 Lync Server 2013 SBA(Survivable Branch Appliance) 분기 사이트 추가
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add Lync Server 2013 Survivable Branch Appliance branch site to your topology
ms:assetid: d3142a37-4606-456d-8ea9-6cc0e51e55f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721896(v=OCS.15)
ms:contentKeyID: 49733830
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b4fc2dd7426006d0c8f19b38b85ba778744fff2e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735018"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology"></a>토폴로지에 Lync Server 2013 SBA(Survivable Branch Appliance) 분기 사이트 추가

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-07_

Microsoft Lync Server 2013 Survivable Branch 기기 (SBA)는 백업 등록 기관으로 Microsoft Lync Server 2010 프런트 엔드 풀에 연결할 수 없습니다. SBA는 Microsoft Lync Server 2013 프런트 엔드 풀에 연결 되어 있어야 합니다. 이 단계에서는 Microsoft Lync Server 2013 SBA를 가정 합니다. 중앙 사이트에서이 절차를 수행 합니다.

<div>

## <a name="to-add-branch-sites-with-microsoft-lync-server-2013-sba-to-your-topology"></a>Microsoft Lync Server 2013 SBA를 사용 하 여 지점 사이트를 토폴로지에 추가 하려면

1.  토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.

2.  콘솔 트리에서 중앙 사이트를 확장 하 고, **분기 사이트**를 확장 한 다음, **새 분기 사이트**를 클릭 합니다.

3.  **새 분기 사이트 정의** 대화 상자에서 **이름을**클릭 한 다음 새 분기 사이트의 이름을 입력 합니다.

4.  ) **설명을**클릭 한 다음 분기 사이트에 대 한 의미 있는 설명을 입력 합니다.

5.  **다음**을 클릭 합니다.

6.  ) 다음 **새 분기 사이트 정의** 대화 상자에서 다음 중 하나를 수행 합니다.
    
      - **도시**를 클릭 한 다음 지점 사이트가 있는 도시의 이름을 입력 합니다.
    
      - **상태/지역을**클릭 한 다음 분기 사이트가 있는 상태 또는 지역의 이름을 입력 합니다.
    
      - **국가 코드**를 클릭 한 다음 분기 사이트가 있는 국가/지역에 대 한 두 자리 통화 코드를 입력 합니다.

7.  **다음**을 클릭 하 고 다음 중 하나를 수행 합니다.
    
      - 이 사이트에서 Survivable Branch 기기 또는 Survivable Branch 서버를 사용 하는 경우 **마법사를 닫을 때 새 Survivable 마법사 열기** 확인란을 선택 해야 합니다.
    
      - 이 사이트에서 Survivable Branch 기기 또는 Survivable Branch 서버를 사용 하지 않는 경우 **이 마법사를 닫을 때 새 Survivable 마법사 열기** 확인란의 선택을 취소 합니다.
    
      - **마침을**클릭 한 다음 열리는 마법사의 지침을 따릅니다. 마법사 항목에 대 한 자세한 내용은 [Lync Server 2013에서 Survivable Branch 기기 또는 서버 정의](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)를 참조 하세요.

8.  토폴로지에 추가 하려는 각 분기 사이트에 대해 앞의 단계를 반복 합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 SBA(Survivable Branch Appliance) 또는 지속 가능 분기 서버 정의](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)  
[Lync Server 2013에서 분기 사이트에 대한 PSTN 게이트웨이 정의](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)  
[Lync Server 2013에서 미디어 바이패스를 사용 하 여 트렁크 구성](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Lync Server 2013에서 미디어 바이패스 없이 트렁크 구성](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

