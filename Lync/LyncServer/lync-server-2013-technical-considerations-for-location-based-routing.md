---
title: 'Lync Server 2013: Location-Based 라우팅에 대 한 기술적 고려 사항'
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
ms.openlocfilehash: 80364f35ffaf361353815988bcae12f29bca019c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536185"
---
# <a name="technical-considerations-for-location-based-routing-in-lync-server-2013"></a>Lync Server 2013의 Location-Based 라우팅에 대 한 기술적 고려 사항

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-03-09_

Location-Based 라우팅을 계획할 때는 다음 시나리오에 미치는 영향을 고려해 야 합니다.

<div>

## <a name="disaster-recovery"></a>재해 복구

기본 풀에서 백업 풀로 장애 조치 (failover) 하는 동안과 (와) 정상 작업 Location-Based을 기본 풀로 복원 하는 동안 재해 복구 절차 중에 항상 라우팅이 계속 해 서 적용 됩니다.

</div>

<div>

## <a name="survivable-branch-appliance"></a>Survivable Branch Appliance

Location-Based 라우팅을 구성 하면 Sba (survivable 분기 기기와 연결 된 게이트웨이를 배포 하는 계획에 영향을 줍니다. SBA와 연결 된 게이트웨이는 Sba (survivable 분기 기기와 동일한 네트워크 사이트에 있어야 합니다. 그렇지 않으면 Location-Based 라우팅이 구성 된 경우 Sba (survivable 분기 기기에 있는 사용자가 아웃 바운드 호출을 수행할 수 없습니다. Sba (survivable 분기 어플라이언스와 중앙 사이트 간의 WAN 연결이 다운 되 면 Location-Based 라우팅 제한이 적용 된 상태로 유지 됩니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 Location-Based 라우팅 계획](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

