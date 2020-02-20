---
title: 'Lync Server 2013: 위치 기반 라우팅에 대 한 기술 고려 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical considerations for Location-Based Routing
ms:assetid: 2e2a9199-7c6f-48d3-9adb-3873fc4f8c4e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994027(v=OCS.15)
ms:contentKeyID: 51803936
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e672e35771ec3cc4ecbd3655af350231f1583b52
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141894"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="technical-considerations-for-location-based-routing-in-lync-server-2013"></a>Lync Server 2013의 위치 기반 라우팅에 대 한 기술적 고려 사항

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-03-09_

위치 기반 라우팅을 계획할 때는 다음 시나리오에 미치는 영향을 고려해 야 합니다.

<div>

## <a name="disaster-recovery"></a>재해 복구

기본 풀에서 백업 풀로 장애 조치 (failover) 하는 동안과 정상 작업을 기본 풀로 복원 하는 동안 재해 및 복구 절차 중에 항상 위치 기반 라우팅이 계속 해 서 적용 됩니다.

</div>

<div>

## <a name="survivable-branch-appliance"></a>Survivable Branch Appliance

위치 기반 라우팅 구성은 Sba (survivable 분기 기기와 연결 된 게이트웨이를 배포 하는 계획에 영향을 줍니다. SBA와 연결 된 게이트웨이는 Sba (survivable 분기 기기와 동일한 네트워크 사이트에 있어야 합니다. 그렇지 않으면 위치 기반 라우팅이 구성 된 경우 Sba (survivable 분기 기기에 속한 사용자가 아웃 바운드 호출을 수행할 수 없습니다. Sba (survivable 분기 어플라이언스와 중앙 사이트 간의 WAN 연결이 다운 되 면 위치 기반 라우팅 제한이 적용 됩니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 위치 기반 라우팅 계획](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

