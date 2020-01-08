---
title: 'Lync Server 2013: 새로운 재해 복구 및 고가용성 기능'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New disaster recovery and high availability features
ms:assetid: 4fa7cd0f-784b-4d3f-b839-432c2ecaf7c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204892(v=OCS.15)
ms:contentKeyID: 48184130
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e93e2265d401c6dca16f5c00c339fbdc893aba0a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981618"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-disaster-recovery-and-high-availability-features-in-lync-server-2013"></a>Lync Server 2013의 새로운 재해 복구 및 고가용성 기능

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-20_

Lync Server 2010에서와 마찬가지로 Lync Server 2013의 기본 고가용성 (HA) 체계는 풀링을 통한 서버 중복성을 기반으로 합니다. 특정 서버 역할을 실행 하는 서버에 오류가 발생 하는 경우 동일한 역할을 실행 하는 풀의 다른 서버에서 해당 서버의 로드를 수행 합니다. 이는 프런트 엔드 서버, Edge 서버, 중재 서버 및 디렉터에 적용 됩니다.

Lync Server 2013는 두 데이터 센터에 있는 프런트 엔드 풀을 쌍으로 할 수 있도록 하 여 새 재해 복구 조치를 추가 합니다. 연결 된 풀 중 하나가 다운 되 면 관리자는 해당 풀의 사용자를 해당 쌍의 다른 풀로 장애 조치 하 여 서비스를 계속 제공할 수 있습니다. 이 기능은 저장소 네트워크 또는 공유 디스크와 같은 비싼 네트워크 또는 하드웨어 솔루션은 필요 하지 않습니다.

또한 Lync Server 2013는 백 엔드 서버 고가용성을 추가 합니다. 이는 프런트 엔드 풀에 대해 두 백 엔드 서버를 배포 하 고 백 엔드 서버에서 실행 되는 모든 Lync 데이터베이스에 대해 동기 SQL 미러링을 설정 하는 선택적 토폴로지입니다. 미러에 미러링 모니터를 배포할지 여부를 선택할 수 있습니다.

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 고가용성 및 재해 복구 계획](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

