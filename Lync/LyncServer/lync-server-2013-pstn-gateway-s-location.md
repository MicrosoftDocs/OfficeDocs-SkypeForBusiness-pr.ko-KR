---
title: 'Lync Server 2013: PSTN 게이트웨이 위치'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: PSTN gateway's location
ms:assetid: 49693a35-fad3-49ee-a71e-c7e4537b79aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994031(v=OCS.15)
ms:contentKeyID: 51803940
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b897d9ce438844cde7617bb7c3e1dae086605f09
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983804"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-gateways-location-in-lync-server-2013"></a>Lync Server 2013의 PSTN 게이트웨이 위치

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-03-09_

PSTN 게이트웨이와 Pbx를 통해 라우팅되는 통화는 해당 시스템의 위치에 따라 위치 기반 라우팅 제한이 필요할 것입니다. 위치 기반 라우팅은 각 트렁크 기준으로 세분성에서 사용 하도록 설정할 수 있습니다.

위치 기반 라우팅은 트렁크에서 사용 하도록 설정 된 경우 다음 규칙 집합을 소개 합니다.

  - 위치 기반 라우팅이 트렁크 기준에 따라 사용 되는 경우, 해당 트렁크에 정의 된 규칙은 해당 트렁크를 통해 라우팅되는 통화에만 적용 됩니다.

  - Pstn 게이트웨이가 있는 네트워크 사이트와 다른 네트워크 사이트에서 발생 하는 호출이 발생 하는 경우 PSTN tolls 우회를 방지 하기 위해 위치 기반 라우팅은 지정 된 트렁크에 대 한 네트워크 사이트의 연결을 소개 합니다. 이는 전화를 지정 된 트렁크로 라우팅할 수 있는 네트워크 사이트를 정의 합니다.

Trunks는 다음과 같은 두 가지 방법으로 위치 기반 라우팅에 대해 사용 하도록 설정할 수 있습니다.

  - 트렁크는 PSTN에 대 한 통화를 egresses 하는 PSTN 게이트웨이에 대해 정의 됩니다. 이 유형의 트렁크가 라우팅된 걸려오는 전화는 트렁크와 같은 네트워크 사이트 내에 있는 끝점 으로만 라우팅됩니다.

  - 트렁크는 고정 장소 (예: PBX 전화기)의 PSTN 및 서비스 사용자에 게는 전송 되지 않는 중재 서버 피어에 대해 정의 되어 있습니다. 이 특정 구성의 경우,이 유형의 트렁크로 라우팅된 모든 수신 전화는 트렁크와 동일한 네트워크 사이트에서 전송 되는 것으로 간주 됩니다. PBX 사용자의 통화는 트렁크와 같은 네트워크 사이트에 있는 Lync 사용자와 동일한 위치 기반 라우팅 적용을 할 수 있습니다. 별도의 네트워크 사이트에 있는 두 개의 PBX 시스템이 Lync Server를 통해 연결 된 경우 위치 기반 라우팅은 한 네트워크 사이트의 한 PBX 끝점에서 다른 네트워크 사이트의 다른 PBX 끝점으로 라우팅을 허용 합니다. 이 시나리오는 위치 기반 라우팅에 의해 차단 되지 않습니다. 이 시나리오 외에도 Lync 사용자와 비슷한 방식으로이 구성을 사용 하 여 중재 서버 피어에 연결 된 끝점은 PSTN (i)으로 호출을 라우팅 하지 않는 다른 중재 서버 피어로 전화를 걸거나 받을 수 있습니다. e. 중재 서버 피어가 연결 된 네트워크 사이트에 관계 없이 다른 PBX에 연결 된 끝점입니다. PSTN 끝점을 포함 하는 모든 인바운드 통화, 아웃 바운드 통화, 통화 전송 및 착신 통화 전달에 따라 해당 중재 서버 피어에 로컬으로 정의 된 PSTN 게이트웨이만 사용할 수 있는 위치를 기반으로 하는 라우팅이 적용 됩니다.

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 위치 기반 라우팅에 대한 지침](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

