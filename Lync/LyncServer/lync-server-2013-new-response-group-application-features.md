---
title: 'Lync Server 2013: 새 응답 그룹 응용 프로그램 기능'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New Response Group application features
ms:assetid: 569544b4-fa97-429b-97e6-568afab6c19b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398373(v=OCS.15)
ms:contentKeyID: 48184196
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bddf1f670ef2a0a246100564962b2f69db741186
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755902"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-response-group-application-features-in-lync-server-2013"></a>Lync Server 2013의 새 응답 그룹 응용 프로그램 기능

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-29_

응답 그룹 응용 프로그램을 사용 하면 고객 서비스, 내부 지원 센터 또는 부서에 대 한 일반 전화 지원과 같은 특별 한 목적을 위해 지정 된 사용자에 게 수신 전화를 라우팅하고 대기 시킬 수 있습니다.

Lync Server 2013의 새로운 응답 그룹 응용 프로그램 기능은 다음과 같습니다.

  - **관리자 역할**
    
    Lync Server 2013에는 새 응답 그룹 관리자 역할이 도입 되었습니다. 이제 응답 그룹에 대 한 두 가지 관리 역할인 응답 그룹 관리자 및 응답 그룹 관리자가 있습니다. 응답 그룹 관리자는 응답 그룹에 대 한 요소를 계속 구성할 수 있지만, 관리자는 자신이 소유한 응답 그룹에 대해서만 특정 요소만 구성할 수 있습니다.
    
    관리 모델의 이러한 향상으로 인해 응답 그룹 확장성, 특히 대규모 배포 시나리오에 도움이 됩니다.

  - **고가용성**
    
    SQL Server 미러링 형태의 응답 그룹 응용 프로그램에 대 한 고가용성 지원은 Lync Server 2013의 높은 사용 가능성에 대 한 전체 구성 및 배포의 일부로 사용 됩니다. 고가용성을 위해 구성 하 고 기본 백 엔드 서버에 대 한 연결이 끊어지면 응답 그룹 기능은 미러 백 엔드 서버를 활용 해도 영향을 받지 않습니다.
    
    응답 그룹 응용 프로그램에 대 한 SQL Server 미러링 지원은 전체 Lync Server 2013 고가용성 구성의 범위 밖에 개별적으로 설정 하거나 구성할 수 없습니다.

  - **재해 복구**
    
    응답 그룹 응용 프로그램에 대 한 재해 복구 지원은 전체 Lync Server 2013 재해 복구 구성의 일부인 페어링 된 프런트 엔드 풀의 구성 및 배포의 일부로 사용 됩니다. 또한 응답 그룹 가져오기 및 cmdlet은 백업 풀에 대 한 장애 조치 및 복구 프로세스를 기본 풀이나 새 풀로 지원 합니다. 기본 풀에서 작동 중지가 발생 하는 경우, 응답 그룹을 백업 풀로 장애 조치 (가) 할 수 있으며, 중단을 할 때 주 풀 또는 새 풀로 장애 복구를 다시 시도 합니다.

<div id="sectionSection0" class="section">

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 응답 그룹 계획](lync-server-2013-planning-for-response-groups.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

