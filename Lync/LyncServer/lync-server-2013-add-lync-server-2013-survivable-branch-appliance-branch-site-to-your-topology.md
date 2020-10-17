---
title: Lync Server 2013 Sba (survivable Branch 기기 분기 사이트를 토폴로지에 추가
description: Lync Server 2013 Sba (survivable Branch 기기 분기 사이트를 토폴로지에 추가 합니다.
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
ms.openlocfilehash: 1b50c03dd53c7637fcf0914db290b3e452b64b83
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572034"
---
# <a name="add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology"></a>Lync Server 2013 Sba (survivable Branch 기기 분기 사이트를 토폴로지에 추가

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-07_

Microsoft Lync Server 2013 Sba (survivable Branch 기기 (SBA)는 Microsoft Lync Server 2010 프런트 엔드 풀 (백업 등록자)에 연결할 수 없습니다. SBA는 Microsoft Lync Server 2013 프런트 엔드 풀과 연결 되어 있어야 합니다. 이 단계에서는 Microsoft Lync Server 2013 SBA를 가정 합니다. 이 절차는 중앙 사이트에서 수행합니다.

<div>

## <a name="to-add-branch-sites-with-microsoft-lync-server-2013-sba-to-your-topology"></a>토폴로지에 Microsoft Lync Server 2013 SBA가 있는 분기 사이트를 추가 하려면

1.  토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.

2.  콘솔 트리에서 중앙 사이트를 확장 하 고 **분기 사이트**를 확장 한 다음 **새 분기 사이트**를 클릭 합니다.

3.  **새 분기 사이트 정의** 대화 상자에서 **이름을**클릭 한 다음 새 분기 사이트의 이름을 입력 합니다.

4.  (선택 사항) **설명**을 클릭한 다음 분기 사이트에 대한 의미 있는 설명을 입력합니다.

5.  **다음**을 클릭합니다.

6.  (선택 사항) 다음 **새 분기 사이트 정의** 대화 상자에서 다음 중 일부를 수행합니다.
    
      - **구/군/시**를 클릭한 다음 분기 사이트가 있는 구/군/시의 이름을 입력합니다.
    
      - **시/도/지역**을 클릭한 다음 분기 사이트가 있는 시/도/지역의 이름을 입력합니다.
    
      - 국가 코드를 클릭한 다음 분기 사이트가 있는 국가/지역에 대한 두 자리 국가/지역 번호를 입력합니다.

7.  **다음**을 클릭하고 다음 중 하나를 수행합니다.
    
      - 이 사이트에서 Sba (survivable Branch 기기나 Sba (survivable Branch Server를 사용 하는 경우 **이 마법사를 닫을 때 새 Sba (survivable 마법사 열기** 확인란을 선택 해야 합니다.
    
      - 이 사이트에서 Sba (survivable Branch 기기나 Sba (survivable Branch Server를 사용 하지 않는 경우 **이 마법사를 닫을 때 새 Sba (survivable 마법사 열기** 확인란의 선택을 취소 합니다.
    
      - **마침을**클릭 하 고 마법사에서 열리는 지시를 따릅니다. 마법사 항목에 대 한 자세한 내용은 [Define a Sba (survivable Branch 어플라이언스 Or Server in a Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)을 참조 하십시오.

8.  토폴로지에 추가할 각 분기 사이트에 대해 앞의 단계를 반복합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 Sba (survivable Branch 기기 또는 서버 정의](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)  
[Lync Server 2013에서 분기 사이트에 대 한 PSTN 게이트웨이 정의](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)  
[Lync Server 2013의 미디어 바이패스로 트렁크 구성](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Lync Server 2013에서 미디어 바이패스 없이 트렁크 구성](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

