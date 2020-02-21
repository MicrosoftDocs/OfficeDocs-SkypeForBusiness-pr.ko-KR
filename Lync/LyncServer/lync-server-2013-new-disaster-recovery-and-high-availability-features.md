---
title: 'Lync Server 2013: 새로운 재해 복구 및 고가용성 기능'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New disaster recovery and high availability features
ms:assetid: 4fa7cd0f-784b-4d3f-b839-432c2ecaf7c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204892(v=OCS.15)
ms:contentKeyID: 48184130
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7845f919f04985e67d6825b8722904a9158606b7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216954"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-disaster-recovery-and-high-availability-features-in-lync-server-2013"></a>Lync Server 2013의 새로운 재해 복구 및 고가용성 기능

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-20_

Lync Server 2010에서와 마찬가지로 Lync Server 2013에 대 한 기본 고가용성 (HA) 체계는 풀링을 통한 서버 중복성을 기반으로 합니다. 특정 서버 역할을 실행하는 서버에서 오류가 발생하면 같은 역할을 실행하는 풀의 다른 서버가 해당 서버의 부하를 대신 처리합니다. 이는 프런트 엔드 서버, 에지 서버, 중재 서버 및 디렉터에 적용됩니다.

Lync Server 2013에서는 두 데이터 센터에 있는 프런트 엔드 풀을 연결할 수 있도록 하 여 새로운 재해 복구 조치를 추가 합니다. 쌍으로 연결된 풀 중 하나가 다운되면 관리자가 사용자를 해당 풀에서 다른 풀로 장애 조치(failover)하여 서비스를 계속해서 제공할 수 있습니다. 이 기능에는 저장소 네트워크 또는 공유 디스크와 같이 고비용의 네트워크 또는 하드웨어 솔루션이 필요하지 않습니다.

Lync Server 2013도 백 엔드 서버 고가용성을 추가 합니다. 프런트 엔드 풀에 대해 두 개의 백 엔드 서버를 배포 하 고 백 엔드 서버에서 실행 되는 모든 Lync 데이터베이스에 대해 동기 SQL 미러링을 설정 하는 선택적 토폴로지입니다. 미러에 대해 미러링 모니터를 배포할지 여부를 선택할 수 있습니다.

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 고가용성 및 재해 복구 계획](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

