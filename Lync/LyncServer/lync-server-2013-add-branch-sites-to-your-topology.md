---
title: 'Lync Server 2013: 토폴로지에 분기 사이트 추가'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add branch sites to your topology
ms:assetid: b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412905(v=OCS.15)
ms:contentKeyID: 48185216
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fec919491872df8dc2ab0f843be84d4d0de1c280
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521575"
---
# <a name="add-branch-sites-to-your-topology-in-lync-server-2013"></a>Lync Server 2013에서 토폴로지에 분기 사이트 추가

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-05_

분기 사이트는 WAN 링크를 통해 본사에 연결되는 실제 지점을 나타냅니다. Lync 토폴로지에 분기 사이트를 추가하려면 중앙 사이트에서 다음 절차를 수행하십시오.

<div>

## <a name="to-add-branch-sites-to-your-topology"></a>토폴로지에 분기 사이트를 추가하려면

1.  **시작**, **모든 프로그램**, **Microsoft Lync Server**를 차례로 클릭한 다음 **Lync Server 토폴로지 작성기**를 클릭합니다.

2.  콘솔 트리에서 중앙 사이트를 확장하고 **분기 사이트**를 마우스 오른쪽 단추로 클릭한 다음 **새 분기 사이트**를 클릭합니다.

3.  **새 분기 사이트 정의** 대화 상자에서 **이름**을 클릭한 다음 분기 사이트의 이름을 입력합니다.

4.  (선택 사항) **설명**을 클릭한 다음 분기 사이트에 대한 의미 있는 설명을 입력합니다.

5.  **다음**을 클릭합니다.

6.  (선택 사항) 다음 **새 분기 사이트 정의** 대화 상자에서 다음 중 일부를 수행합니다.
    
      - **구/군/시**를 클릭한 다음 분기 사이트가 있는 구/군/시의 이름을 입력합니다.
    
      - **시/도/지역**을 클릭한 다음 분기 사이트가 있는 시/도/지역의 이름을 입력합니다.
    
      - 국가 코드를 클릭한 다음 분기 사이트가 있는 국가/지역에 대한 두 자리 국가/지역 번호를 입력합니다.

7.  **다음**을 클릭하고 다음 중 하나를 수행합니다.
    
      - 이 사이트에서 Sba (survivable Branch 어플라이언스 또는 서버를 사용 하는 경우에는 **이 마법사가 닫히면 새 Sba (survivable 마법사 열기** 확인란을 선택 하 고 **마침을**클릭 한 다음 마법사에서 열리는 지시를 따릅니다. 마법사 항목에 대 한 자세한 내용은 [Define a Sba (survivable Branch 어플라이언스 Or Server in a Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)을 참조 하십시오.
    
      - 이 사이트에서 SBA 또는 지속 가능 분기 서버를 사용하지 않는 경우에는 **이 마법사가 닫히면 새 지속 가능 마법사 열기** 확인란의 선택을 취소한 다음 **마침**을 클릭합니다.

8.  토폴로지에 추가할 각 분기 사이트에 대해 앞의 단계를 반복합니다.

**다음 단계:**

Sba (survivable 분기 어플라이언스 또는 Servers의 경우: [Lync Server 2013에서 Sba (survivable 분기 어플라이언스 또는 Server 정의](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)

탄성 이외의 PSTN 연결의 경우: lync server [2013에서 분기 사이트에 대 한 PSTN 게이트웨이를 정의](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)하거나 lync server [2013에서 미디어 바이패스를 사용 하 여 트렁크를 구성](lync-server-2013-configure-a-trunk-with-media-bypass.md)하거나 [lync server 2013에서 미디어 바이패스 없이 트렁크를 구성](lync-server-2013-configure-a-trunk-without-media-bypass.md) 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

