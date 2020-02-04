---
title: 'Lync Server 2013: 위임'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delegation
ms:assetid: 89e76e5c-3cfb-4504-8d0d-7509c8ba9815
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994045(v=OCS.15)
ms:contentKeyID: 51803956
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8da9568ae4cd613dcba0760fb4a8b20295fbb68d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739808"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delegation-in-lync-server-2013"></a>Lync Server 2013의 위임

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-03-09_

Lync의 위임 기능은 다음과 같은 방식으로 위치 기반 라우팅의 영향을 받습니다.

  - 위치 기반 라우팅이 사용 하도록 설정 된 대리인이 관리자를 대신 하 여 호출 하는 경우 대리인의 음성 정책이 통화를 승인 하는 데 사용 되 고 대리인의 사이트 음성 라우팅 정책은 통화를 라우팅하는 데 사용 됩니다.

  - 관리자에 게 수신 되는 PSTN 통화의 경우, 착신 전환 및 동시 연결에 적용 되는 것과 같은 규칙이 적용 됩니다.

  - 대리인이 PSTN 끝점을 동시 링 대상으로 설정 하는 경우, 관리자에 게 들어오는 호출에 대해 들어오는 트렁크에 연결 된 사이트의 음성 라우팅 정책은 호출을 대리인의 PSTN 끝점으로 라우팅하는 데 사용 됩니다.

  - 위임의 경우 관리자와 연결 된 대리인을 일반적으로 같은 네트워크 사이트에 배치 하는 것이 좋습니다.

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 위치 기반 라우팅 시나리오](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

