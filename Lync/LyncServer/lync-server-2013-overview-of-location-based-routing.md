---
title: 'Lync Server 2013: 위치 기반 라우팅 개요'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of Location-Based Routing
ms:assetid: 4aa494bd-0d66-4335-b9e8-f758d44a7202
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994032(v=OCS.15)
ms:contentKeyID: 51803941
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82b3a5cb2e89376a356daf54c6e5bc443ab52207
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982889"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-location-based-routing-in-lync-server-2013"></a>Lync Server 2013의 위치 기반 라우팅 개요

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-21_

위치 기반 라우팅은 유료 바이패스를 방지 하기 위해 국가 및 국제 PSTN 통화의 라우팅을 수정 하는 새로운 규칙 집합을 소개 합니다. 위치 기반 라우팅은 특정 지역, 특정 게이트웨이 또는 특정 사용자 집합에 대해 이러한 규칙의 범위를 지정 하는 유연성을 제공 합니다.

다음 시나리오는 위치 기반 라우팅이 적용할 수 있는 주요 제한 유형에 대해 설명 합니다.

  - 송신 통화 – 위치 기반 라우팅은 호출자가 PSTN 유료 바이패스를 방지 하 여 다른 지역에 있는 pstn 게이트웨이에서 송신에 대 한 호출을 차단 하는 PSTN 게이트웨이에서 송신 전화를 보낼 수 있습니다. 호출인.

  - 수신 통화 – 들어오는 호출이 있는 PSTN 게이트웨이 라우팅이 호출 된 Lync 사용자와 동일한 지역에 있지 않은 경우 위치 기반 라우팅이 들어오는 PSTN 호출을 통해 Lync 끝점에 연결 되지 않도록 할 수 있습니다.

  - 알 수 없는 영역 – 위치 기반 라우팅은 결정 되지 않은 위치에 있는 사용자와의 수신 및 발신 PSTN 통화 (즉, 인터넷에서 연결 되거나 알 수 없는 지역에 있는 원격 사용자)와 주고 받을 수 있도록 제한 합니다.

  - 국제 지역 – 위치 기반 라우팅은 사용자의 위치에 로컬로 연결 된 게이트웨이를 찾을 수 없는 경우 국제 PSTN 게이트웨이를 통해 나가는 호출의 라우팅을 적용 합니다.

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 위치 기반 라우팅 계획](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

