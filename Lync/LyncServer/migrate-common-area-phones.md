---
title: 공통 지역 전화 마이그레이션
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate Common Area Phones
ms:assetid: 31bd26fc-861b-45c6-8221-18df16e575de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688015(v=OCS.15)
ms:contentKeyID: 49733604
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cba32f8aa95b870190280aebd94d51bdbeec0f2b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762956"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-common-area-phones"></a>공통 지역 전화 마이그레이션

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-29_

일반적인 지역 전화는 가장 자주 공유 작업 영역 또는 일반 영역에 거주 하는 IP 전화기입니다 (예: 대기실, 주방 또는 공장 바닥). 일반 지역 전화는 Lync Server UC 기능을 제공 하기 위해 컴퓨터에 연결 되어 있지 않아도 됩니다. Lync Server 2010 배포를 Lync Server 2013로 마이그레이션한 후에는 레거시 공통 영역 휴대폰과 연결 된 연락처 개체도 마이그레이션해야 합니다. Lync Server Management Shell을 사용 하 여 먼저 Lync Server 2010 공통 지역 휴대폰과 연결 된 모든 contact 개체를 검색 한 다음 해당 개체를 Lync Server 2013 풀로 이동 합니다.

**공통 지역 전화 마이그레이션**

1.  Lync Server 2013 프런트 엔드 서버에서 Lync Server Management Shell을 엽니다.

2.  명령줄에서 다음을 입력 합니다.
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net

3.  모든 연락처 개체가 Lync Server 2013 풀로 이동 되었는지 확인 하려면 Lync Server 관리 셸에서 다음을 입력 합니다.
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
    
    모든 연락처 개체가 Lync Server 2013 풀에 연결 되어 있는지 확인 합니다.

</div>

<span> </span>

</div>

</div>

</div>

