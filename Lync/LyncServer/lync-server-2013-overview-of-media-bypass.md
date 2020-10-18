---
title: 'Lync Server 2013: 미디어 바이패스 개요'
description: 'Lync Server 2013: 미디어 바이패스 개요'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of media bypass
ms:assetid: 9ea090b3-f607-46f7-97dd-2510052524e5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412740(v=OCS.15)
ms:contentKeyID: 48184924
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3859c41a01ae5e7f1100a6872fd4e6747f45dbd8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577334"
---
# <a name="overview-of-media-bypass-in-lync-server-2013"></a>Lync Server 2013의 미디어 바이패스 개요

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-21_

미디어 바이패스는 배포할 중재 서버 수를 최소화할 때 유용합니다. 일반적으로 중재 서버 풀은 중앙 사이트에 배포되며 분기 사이트에서 게이트웨이를 제어합니다. 미디어 바이패스를 사용하도록 설정하면 분기 사이트에서 클라이언트의 PSTN(공중 전화망) 통화에 대한 미디어가 해당 사이트에서 게이트웨이를 통과해 바로 흐르도록 할 수 있습니다. Lync Server 2013 아웃 바운드 통화 경로 및 Enterprise Voice 정책을 적절 하 게 구성 해야 분기 사이트에 있는 클라이언트의 PSTN 통화가 해당 게이트웨이로 라우팅됩니다.

Wi-Fi 네트워크는 일반적으로 유선 네트워크보다 패킷 손실이 많습니다. 손실된 패킷을 복구하는 것은 일반적으로 게이트웨이에서 처리할 수 있는 사항이 아닙니다. 따라서 무선 서브넷에 대해 바이패스를 사용할지 여부를 결정하기 전에 Wi-Fi 네트워크 품질을 평가하는 것이 좋습니다. 대기 시간 감소와 손실된 패킷 복구 간 득실 관계를 고려해야 합니다. 중재 서버를 바이패스하지 않는 통화에 사용할 수 있는 코덱인 RTAudio는 패킷 손실을 처리하는 데 더 적합합니다.

Enterprise Voice 구조를 마련 하 고 나면 미디어 바이패스를 계획 하는 것은 간단 합니다.

  - 분기 사이트에 대한 WAN 링크가 없는 중앙화된 토폴로지가 있는 경우 세분화된 제어가 필요하지 않으므로 전역 미디어 바이패스를 사용하도록 설정할 수 있습니다.

  - 하나 이상의 네트워크 지역 및 관련 분기 사이트로 구성된 분산 토폴로지가 있는 경우에는 다음을 확인합니다.
    
      - 중재 서버 피어가 미디어 바이패스에 필요한 기능을 지원할 수 있는지 여부
    
      - 각 네트워크 지역에서 제대로 연결된 사이트
    
      - 네트워크에 적합한 미디어 바이패스 및 통합 허용 제어 결합

미디어 바이패스를 사용하도록 설정하면 해당 지역 내 대역폭 제약 조건 없이 모든 네트워크 사이트 및 네트워크 지역에 대해 고유한 바이패스 ID가 자동으로 생성됩니다. 지역 내 대역폭 제약 조건이 있는 사이트 및 대역폭 제한 조건이 있는 WAN 링크를 통해 지역에 연결된 사이트에는 각각 고유한 바이패스 ID가 할당됩니다.

사용자가 PSTN을 호출 하면 중재 서버가 클라이언트 서브넷의 바이패스 ID와 게이트웨이 서브넷의 우회 ID를 비교 합니다. 두 개의 바이패스 ID가 일치할 경우 통화에 미디어 바이패스가 사용됩니다. 바이패스 Id가 일치 하지 않으면 통화에 사용 되는 미디어는 중재 서버를 통해 이동 해야 합니다.

사용자가 PSTN을 통해 전화를 받으면 사용자의 클라이언트가 클라이언트의 바이패스 ID와 PSTN 게이트웨이의 바이패스 ID를 비교합니다. 두 바이패스 Id가 일치 하는 경우에는 미디어를 게이트웨이에서 클라이언트에 직접 연결 하 여 중재 서버를 건너뜁니다.

Lync 2010 이상 클라이언트 및 장치만 중재 서버와의 미디어 바이패스 상호 작용을 지원 합니다.

<div>


> [!IMPORTANT]  
> 미디어 바이패스를 전역적으로 사용하도록 설정하는 것 외에도 각 PSTN 트렁크에서 미디어 바이패스를 개별적으로 사용하도록 설정해야 합니다. 바이패스가 전역적으로 사용하도록 설정되었지만 특정 PSTN 트렁크에 대해 사용하지 않도록 설정된 경우에는 해당 PSTN 트렁크와 관련된 통화에 대해 미디어 바이패스가 호출되지 않습니다. 또한 미디어 바이패스가 <STRONG>사이트 및 지역 정보 사용</STRONG>으로 설정된 경우에는 라우팅할 수 있는 모든 서브넷을 서브넷이 있는 사이트에 연결해야 합니다. 바이패스가 필요하지 않은 사이트에 라우팅 가능한 서브넷이 있는 경우 미디어 바이패스를 사용하도록 설정하기 전에 새 사이트 내에서 이 서브넷을 그룹화해야 합니다. 이렇게 하면 라우팅할 수 없는 서브넷에 다른 바이패스 ID가 할당됩니다.



</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 미디어 바이패스 모드](lync-server-2013-media-bypass-modes.md)  
[Lync Server 2013의 미디어 바이패스 및 통화 허용 제어 서비스](lync-server-2013-media-bypass-and-call-admission-control.md)  
[Lync Server 2013의 미디어 바이패스에 대 한 기술 요구 사항](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

