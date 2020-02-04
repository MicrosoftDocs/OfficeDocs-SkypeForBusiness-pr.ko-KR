---
title: 보관 및 모니터링 서버 마이그레이션
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating Archiving and Monitoring servers
ms:assetid: 77831579-df45-4697-b8c5-207b74a07a40
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205015(v=OCS.15)
ms:contentKeyID: 48184550
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 572cbee046ed960017a3b60b7ae68c58ec67cf23
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762886"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-archiving-and-monitoring-servers"></a>보관 및 모니터링 서버 마이그레이션

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-02_

Lync Server 2010 환경에서 보관 서버 및 모니터링 서버를 배포한 경우 프런트 엔드 풀을 마이그레이션한 후 Lync Server 2013 환경에서 이러한 서버를 배포할 수 있습니다. 그러나 보관 및 모니터링 기능이 조직에 중요 한 경우 마이그레이션을 시작 하기 전에 먼저 Lync Server 2013 파일럿 풀에 보관 및 모니터링을 추가 하 여 마이그레이션 프로세스 동안 기능을 사용할 수 있도록 해야 합니다.

마이그레이션 프로세스 중 보관 및 모니터링 기능을 원하는 경우 다음 고려 사항을 염두에 두어야 합니다.

  - 데이터 보관 및 모니터링 데이터는 Lync Server 2013 배포로 이동 되지 않습니다. 레거시 환경을 서비스 해제 하기 전에 백업 하는 데이터는 Lync Server 2010 환경에서 활동의 기록이 됩니다.

  - Lync Server 2010 버전의 보관 서버 및 모니터링 서버는 Lync Server 2010 프런트 엔드 풀에만 연결할 수 있습니다. Lync Server 2013에서 보관 및 모니터링은 더 이상 서버 역할이 아니지만 Lync Server 2013 프런트 엔드 풀에 통합 된 서비스입니다.

  - 레거시 및 Lync Server 2013 배포가 공존할 때 Lync Server 2010 버전의 보관 서버와 모니터링 서버는 Lync Server 2010 풀에 있는 사용자에 대 한 데이터를 수집 합니다. Lync Server 2013에서 보관 및 모니터링을 통해 Lync Server 2013 풀에 속한 사용자의 데이터를 수집 합니다.
    
    <div>
    

    > [!NOTE]  
    > 새로운 Lync Server 2013 파일럿 풀로 레거시 Edge 서버를 사용 하는 동안에도 마이그레이션 단계를 진행 하는 동안 lync Server 2010 버전의 보관 서버는 lync server 2010 풀에 있는 사용자의 데이터를 계속 수집 합니다. lync server 2013 Lync Server 2013 풀에 속한 사용자에 대 한 데이터를 수집 합니다.

    
    </div>

  - 타사 보관 및 모니터링 솔루션을 Lync Server 2013의 보관 및 모니터링과 함께 사용 하는 경우, 타사 솔루션을 Lync Server 2013와 통합 해야 하는 시기와 방법에 대 한 공급 업체에 문의 하세요.

</div>

<span> </span>

</div>

</div>

</div>

