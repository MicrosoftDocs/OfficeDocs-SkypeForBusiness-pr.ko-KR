---
title: 'Lync Server 2013: PSTN 게이트웨이 위치'
description: 'Lync Server 2013: PSTN 게이트웨이의 위치입니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN gateway's location
ms:assetid: 49693a35-fad3-49ee-a71e-c7e4537b79aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994031(v=OCS.15)
ms:contentKeyID: 51803940
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f793249908bd1f064f9038ddd90c7f5b01a61d5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565604"
---
# <a name="pstn-gateways-location-in-lync-server-2013"></a>Lync Server 2013의 PSTN 게이트웨이 위치

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-03-09_

PSTN 게이트웨이와 Pbx를 통해 라우팅되는 통화에는 이러한 시스템의 위치에 따라 Location-Based 라우팅 제한이 필요할 수 있습니다. Location-Based 라우팅은 트렁크 기준에 따라 세분성에서 사용 하도록 설정할 수 있습니다.

Location-Based 라우팅에서 트렁크에서 사용 하도록 설정 된 경우 다음과 같은 규칙 집합을 소개 합니다.

  - 트렁크에 따라 Location-Based 라우팅을 사용 하는 경우 해당 트렁크에 정의 된 규칙은 해당 트렁크를 통해 라우팅되는 통화에만 적용 됩니다.

  - Pstn 게이트웨이가 있는 네트워크 사이트와는 다른 네트워크 사이트에서 호출이 시작 되는 경우 PSTN 유료 전화 우회를 방지 하기 위해 라우팅 Location-Based 네트워크 사이트를 지정 된 트렁크에 연결 하는 것을 소개 합니다. 이는 통화를 지정 된 트렁크로 라우팅할 수 있도록 하는 네트워크 사이트를 정의 합니다.

트렁크는 다음과 같은 두 가지 방법으로 Location-Based 라우팅을 사용 하도록 설정할 수 있습니다.

  - 트렁크는 PSTN에 대 한 통화를 egresses 하는 PSTN 게이트웨이에 대해 정의 됩니다. 이 유형의 트렁크가 라우팅하는 수신 전화는 트렁크와 같은 네트워크 사이트 내에 있는 끝점에만 라우팅됩니다.

  - 트렁크는 고정 위치 (예: PBX 전화)에서 PSTN 및 서비스 사용자에 게 전화를 거는 것을 방해 하지 않는 중재 서버 피어에 대해 정의 됩니다. 이 특정 구성에서는이 유형의 트렁크가 라우팅하는 모든 수신 전화를 트렁크와 같은 네트워크 사이트에서 보내는 것으로 간주 합니다. PBX 사용자의 통화는 트렁크와 같은 네트워크 사이트에 있는 Lync 사용자와 같은 Location-Based 라우팅 적용이 됩니다. 별도 네트워크 사이트에 있는 두 대의 PBX 시스템이 Lync Server를 통해 연결 된 경우에 Location-Based 라우팅은 한 네트워크 사이트의 PBX 끝점에서 다른 네트워크 사이트의 다른 PBX 끝점으로의 라우팅을 허용 합니다. 이 시나리오는 Location-Based 라우팅에서 차단 되지 않습니다. 이 시나리오 외에도 동일한 위치에 있는 Lync 사용자와 비슷한 방식으로이 구성을 사용 하 여 중재 서버 피어에 연결 된 끝점은 중재 서버 피어가 연결 된 네트워크 사이트에 관계 없이 PSTN으로 통화를 라우팅 하지 않는 다른 중재 서버 피어에서 전화를 걸거나 받을 수 있습니다 (즉, 다른 PBX에 연결 된 끝점). 모든 인바운드 통화, 아웃 바운드 통화, 통화 전송 및 PSTN 끝점 관련 통화 전달은 해당 중재 서버 피어에 로컬로 정의 된 PSTN 게이트웨이를 사용 하기 위해 위치 기반 라우팅을 따릅니다.

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 Location-Based 라우팅에 대 한 지침](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

