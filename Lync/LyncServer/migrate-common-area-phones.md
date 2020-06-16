---
title: 공통 영역 전화 마이그레이션
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate Common Area Phones
ms:assetid: 31bd26fc-861b-45c6-8221-18df16e575de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688015(v=OCS.15)
ms:contentKeyID: 49733604
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 138068c73264ded3483d8d9f0902d403833a306d
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756999"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-common-area-phones"></a>공통 영역 전화 마이그레이션

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-29_

공통 영역 전화는 공유 작업 영역 또는 일반적인 영역 (예를 들어, 로비, 주방 또는 공장 바닥)에 있는 IP 전화입니다. Lync Server UC 기능을 제공 하기 위해 일반 영역 전화를 컴퓨터에 연결할 필요는 없습니다. Lync server 2010 배포를 Lync Server 2013로 마이그레이션한 후에는 레거시 공통 영역 전화와 연결 된 대화 상대 개체도 마이그레이션해야 합니다. Lync Server 관리 셸을 사용 하 여 먼저 Lync server 2010 공통 영역 전화와 연결 된 모든 대화 상대 개체를 검색 한 후 해당 개체를 Lync Server 2013 풀로 이동 합니다.

**공통 지역 전화 마이그레이션**

1.  Lync Server 2013 프런트 엔드 서버에서 Lync Server 관리 셸을 엽니다.

2.  명령줄에 다음을 입력합니다.
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net

3.  모든 대화 상대 개체가 Lync Server 2013 풀로 이동 되었는지 확인 하려면 Lync Server 관리 셸에서 다음을 입력 합니다.
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
    
    모든 대화 상대 개체가 Lync Server 2013 풀과 연결 되어 있는지 확인 합니다.

</div>

<span> </span>

</div>

</div>

</div>

