---
title: 'Lync Server 2013: 위치 기반 라우팅 개요'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Location-Based Routing
ms:assetid: 4aa494bd-0d66-4335-b9e8-f758d44a7202
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994032(v=OCS.15)
ms:contentKeyID: 51803941
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 85d24aeb94a0c16e93d885c5b6db20385cdf0f26
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216251"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-location-based-routing-in-lync-server-2013"></a>Lync Server 2013의 위치 기반 라우팅 개요

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-21_

위치 기반 라우팅은 유료 바이패스를 방지 하기 위해 국내 및 국제 PSTN 통화의 라우팅을 수정 하는 새로운 규칙 집합을 소개 합니다. 위치 기반 라우팅은 이러한 규칙을 특정 지역, 특정 게이트웨이 또는 특정 사용자 에게만 범위를 지정 하는 데 사용할 수 있는 유연성을 제공 합니다.

다음 시나리오에서는 위치 기반 라우팅이 적용할 수 있는 주요 제한 유형을 보여 줍니다.

  - 송신 통화-위치 기반 라우팅은 발신자가 PSTN 전화 바이패스를 방지 하는 것과 같은 지역에 있는 PSTN 게이트웨이에서 송신 전화를 보낼 수 있도록 하 여 다른 지역에 있는 PSTN 게이트웨이에서 발신을 호출 하지 못하게 합니다. 최초.

  - 수신 통화-수신 전화가 호출 된 Lync 사용자와 같은 지역에 없는 경우 위치 기반 라우팅은 들어오는 PSTN 호출이 전화를 걸 수 없도록 합니다.

  - 알 수 없는 지역-위치 기반 라우팅은 인터넷에서 연결 하거나 알 수 없는 지역에 있는 원격 사용자와의 들어오고 나가는 PSTN 통화를 결정 되지 않은 위치에 있는 사용자로 제한 합니다.

  - 국제 지역-위치 기반 라우팅은 사용자의 위치에 대 한 로컬 게이트웨이를 찾을 수 없는 경우 국제 PSTN 게이트웨이를 통해 발신 전화의 라우팅을 적용 합니다.

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 위치 기반 라우팅 계획](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

