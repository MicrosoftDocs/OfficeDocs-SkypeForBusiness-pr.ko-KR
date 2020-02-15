---
title: 'Lync Server 2013: 통화 허용 제어에 대 한 모범 사례'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Best practices for call admission control
ms:assetid: 97173cca-8175-4ae2-a247-eb7ef809da93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398770(v=OCS.15)
ms:contentKeyID: 48184913
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c00dbaa2f47d34f06424c9013a5b691caab56499
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041127"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-call-admission-control-in-lync-server-2013"></a>Lync Server 2013의 통화 허용 제어에 대 한 모범 사례

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-22_

성능을 향상시키고 배포를 용이하게 하려면 통화 허용 제어 배포 시 다음과 같은 유용한 정보를 적용합니다.

  - 현재 및 예상 미디어 트래픽에 대해 WAN이 적절하게 프로비전되어 있는지 확인합니다.
    
    <div>
    

    > [!NOTE]  
    > 대역폭 제한에 대해 버퍼를 고려하는 것이 좋습니다. 사용되는 총 대역폭에 영향을 주고 대역폭 제한이 초과되는 상황을 초래할 수 있는 경합 상태와 같은 시나리오가 있습니다. 예를 들어 두 통화가 미디어 트래픽이 대역폭 제한에 근접하는 동안 시작되려고 하는 경우 한 통화가 먼저 시작되기 때문에 다른 한 통화가 거부될 수 있습니다.

    
    </div>

  - 최적의 CAC 설정을 선택하고 네트워크 사용량이 변경됨에 따라 CAC 설정을 업데이트할 수 있도록 네트워크 사용량 및 통화 정보 기록을 모니터링합니다.

  - CAC 대역폭 정책을 사용하여 QoS 설정을 보완합니다.

  - 차단된 통화를 PSTN으로 다시 라우팅하려면 PSTN 기능 및 용량을 확인합니다. 자세한 내용은 [Lync Server 2013에서 아웃 바운드 음성 라우팅 계획](lync-server-2013-planning-outbound-voice-routing.md)을 참조 하십시오.
    
    <div>
    

    > [!NOTE]  
    > 용량은 잠재적 PSTN 재라우팅을 지원하기 위해 열어야 하는 포트 수를 가리킵니다.

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

