---
title: 'Lync Server 2013: 토폴로지에 분기 사이트 추가'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Add branch sites to your topology
ms:assetid: b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412905(v=OCS.15)
ms:contentKeyID: 48185216
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 029627060ff03b804d0d2f76f40fdd4052f0d1c6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981515"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-branch-sites-to-your-topology-in-lync-server-2013"></a>Lync Server 2013에서 토폴로지에 분기 사이트 추가

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-05_

지점 사이트는 WAN 링크를 통해 메인 사무실에 연결 된 지사의 실제 지점을 나타냅니다. Lync 토폴로지에 분기 사이트를 추가 하려면 중앙 사이트에서이 절차를 수행 합니다.

<div>

## <a name="to-add-branch-sites-to-your-topology"></a>토폴로지에 지점 사이트를 추가 하려면

1.  **시작**을 클릭 하 고 **모든 프로그램**, **Microsoft Lync server**를 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.

2.  콘솔 트리에서 중앙 사이트를 확장 하 고 **분기 사이트**를 마우스 오른쪽 단추로 클릭 한 다음 **새 분기 사이트**를 클릭 합니다.

3.  **새 분기 사이트 정의** 대화 상자에서 **이름을**클릭 한 다음 분기 사이트의 이름을 입력 합니다.

4.  ) **설명을**클릭 한 다음 분기 사이트에 대 한 의미 있는 설명을 입력 합니다.

5.  **다음**을 클릭 합니다.

6.  ) 다음 **새 분기 사이트 정의** 대화 상자에서 다음 중 하나를 수행 합니다.
    
      - **도시**를 클릭 한 다음 지점 사이트가 있는 도시의 이름을 입력 합니다.
    
      - **상태/지역을**클릭 한 다음 분기 사이트가 있는 상태 또는 지역의 이름을 입력 합니다.
    
      - **국가 코드**를 클릭 한 다음 분기 사이트가 있는 국가/지역에 대 한 두 자리 통화 코드를 입력 합니다.

7.  **다음**을 클릭 하 고 다음 중 하나를 수행 합니다.
    
      - 이 사이트에서 Survivable Branch 기기 또는 서버를 사용 하는 경우 **마법사를 닫을 때 새 Survivable 마법사 열기** 확인란을 선택 하 고 **마침을**클릭 한 다음 마법사에서 열리는 지침을 따릅니다. 마법사 항목에 대 한 자세한 내용은 [Lync Server 2013에서 Survivable Branch 기기 또는 서버 정의](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)를 참조 하세요.
    
      - 이 사이트에서 Survivable Branch 기기 또는 서버를 사용 하 고 있지 않은 경우 마법사를 **닫을 때 새 Survivable 마법사 열기** 확인란의 선택을 취소 하 고 **마침을**클릭 합니다.

8.  토폴로지에 추가 하려는 각 분기 사이트에 대해 앞의 단계를 반복 합니다.

**다음 단계:**

Survivable Branch 기기 또는 서버의 경우: [Lync Server 2013에서 Survivable Branch 기기 또는 서버 정의](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)

회복성 있지 않은 PSTN 연결의 경우: [Lync server 2013에서 지점 사이트에 대 한 PSTN 게이트웨이를 정의](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)하 고, [lync server 2013에서 미디어 바이패스를 사용 하 여 트렁크를 구성](lync-server-2013-configure-a-trunk-with-media-bypass.md)하거나, [lync server 2013에서 미디어 바이패스 없이 트렁크를 구성](lync-server-2013-configure-a-trunk-without-media-bypass.md) 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

