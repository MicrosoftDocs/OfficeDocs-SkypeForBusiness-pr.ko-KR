---
title: 보관 및 모니터링 서버 마이그레이션
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating Archiving and Monitoring servers
ms:assetid: 8d879253-ad76-42b7-8386-e44b110239cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688124(v=OCS.15)
ms:contentKeyID: 49733722
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 799f2258344d94f4dcfc0e477bd3e77316c3a060
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148847"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-archiving-and-monitoring-servers"></a>보관 및 모니터링 서버 마이그레이션

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-02_

Office Communications Server 2007 r 2에 보관 서버 및 모니터링 서버를 배포한 경우 프런트 엔드 풀을 마이그레이션한 후 Lync Server 2013 환경에서 이러한 서버를 배포할 수 있습니다. 보관 및 모니터링 기능이 조직에 중요한 경우라도 마이그레이션 프로세스 중 기능을 사용할 수 있도록 마이그레이션하기 전에 보관 서버 및 모니터링 서버를 파일럿 풀에 추가해야 합니다.

마이그레이션 중에 그리고 동시 사용 단계 중에 보관 및 모니터링 기능을 사용할 수 있으려면 다음과 같은 사항을 고려하십시오.

  - 데이터 보관 및 모니터링 데이터가 Lync Server 2013 배포로 이동 되지 않습니다. 레거시 환경을 제거 하기 전에 백업 하는 데이터는 Office Communications Server 2007 r 2의 활동 기록이 됩니다.

  - Office Communications Server 2007 R2 버전의 보관 서버 및 모니터링 서버는 Office Communications Server 2007 R2 프런트 엔드 풀에만 연결할 수 있습니다. Lync Server 2013에서 보관 및 모니터링은 더 이상 서버 역할은 아니지만 Lync Server 2013 프런트 엔드 풀로 통합 된 서비스입니다.

  - 레거시 및 Lync Server 2013 배포가 공존할 때 Office Communications Server 2007 R2 버전의 보관 서버 및 모니터링 서버는 Office Communications Server 2007 R2 풀에 있는 사용자에 대 한 데이터를 수집 합니다. Lync server 2013 버전의 보관 서버 및 모니터링 서버는 Lync Server 2013 풀에 있는 사용자에 대 한 데이터를 수집 합니다.
    
    <div>
    

    > [!NOTE]  
    > 새 Lync Server 2013 파일럿 풀과 함께 레거시에 지 서버를 계속 사용 하는 경우 마이그레이션 단계에서 Office Communications Server 2007 R2 버전의 보관 서버는 Office Communications Server의 사용자에 대 한 데이터를 계속 수집 2007 R2 풀 및 Lync Server 2013 버전의 보관 서버는 Lync Server 2013 풀에 있는 사용자에 대 한 데이터를 수집 합니다.

    
    </div>

  - 보관 서버 및 모니터링 서버와 함께 타사 보관 및 모니터링 솔루션을 사용 하는 경우 타사 솔루션을 Lync Server 2013와 통합 해야 하는 시기 및 방법에 대 한 공급 업체에 문의 하십시오.

</div>

<span> </span>

</div>

</div>

</div>

