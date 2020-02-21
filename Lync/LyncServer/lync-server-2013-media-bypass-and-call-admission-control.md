---
title: 'Lync Server 2013: 미디어 바이패스 및 통화 허용 제어'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media bypass and call admission control
ms:assetid: 120b2a2b-5f97-4735-a2ee-0f849feb8c1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398203(v=OCS.15)
ms:contentKeyID: 48183454
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10915a298fe2e50abdef09dc5acf92927a43cc65
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42185301"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="media-bypass-and-call-admission-control-in-lync-server-2013"></a>Lync Server 2013의 미디어 바이패스 및 통화 허용 제어 서비스

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-05_

미디어 바이패스 및 CAC(통화 허용 제어)는 함께 작동하여 통화 미디어에 대한 대역폭 제어를 관리합니다. 미디어 바이패스는 정상적으로 연결된 링크를 통한 미디어 흐름을 원활하게 하고, CAC는 대역폭 제약 조건이 있는 링크에 대한 트래픽을 관리합니다. 미디어 바이패스 및 CAC는 함께 사용할 수 없으므로 한 기능을 계획할 때는 다른 기능을 고려해야 합니다. 다음과 같은 조합이 지원됩니다.

  - CAC와 미디어 바이패스를 둘 다 사용하도록 설정. 미디어 바이패스는 **사이트 및 지역 정보 사용**으로 설정해야 합니다. 이 사이트 및 지역 정보는 CAC에 사용되는 것과 같습니다.
    
    CAC를 사용하도록 설정하는 경우에는 **항상 바이패스**를 선택할 수 없으며 그 반대의 경우도 마찬가지입니다. 이 두 구성은 함께 사용할 수 없기 때문입니다. 즉, 지정된 PSTN 통화에는 두 구성 중 하나만 적용됩니다. 먼저 미디어 바이패스가 통화에 적용되는 지를 확인한 다음, 적용되는 경우에는 CAC가 사용되지 않습니다. 통화를 바이패스할 수 있는 경우에는 기본적으로 CAC가 필요하지 않은 연결을 사용하기 때문입니다. 통화에 바이패스를 적용할 수 없는 경우(클라이언트 및 게이트웨이의 바이패스 ID가 일치하지 않는 경우) CAC가 통화에 적용됩니다.

  - CAC는 사용하도록 설정하지 않고 미디어 바이패스를 **항상 바이패스**로 설정
    
    이 구성에서는 클라이언트와 트렁크 서브넷이 모두 단일 바이패스 ID에 매핑됩니다. ID는 이 항목 하나뿐이며, 시스템에서 자동으로 계산됩니다.

  - CAC는 사용하도록 설정하지 않고 미디어 바이패스를 **사이트 및 지역 정보 사용**으로 설정
    
    **사이트 및 지역 정보 사용**을 사용하도록 설정하면 CAC가 사용하도록 설정되어 있는지 여부에 관계없이 바이패스 결정도 기본적으로 같은 방식으로 작동합니다. 즉, 지정된 PSTN 통화에 대해 클라이언트 서브넷이 특정 사이트로 매핑되고 해당 서브넷의 바이패스 ID가 추출됩니다. 마찬가지로, 게이트웨이 서브넷이 특정 사이트로 매핑되고 해당 서브넷의 바이패스 ID가 추출됩니다. 두 바이패스 ID가 동일한 경우에만 통화에 대해 바이패스가 수행되며, ID가 동일하지 않은 경우에는 미디어 바이패스가 수행되지 않습니다.
    
    CAC를 전역적으로 사용하지 않도록 설정하더라도, 사이트 및 지역 구성을 사용하여 바이패스 결정을 제어하려면 각 사이트 및 링크에 대해 대역폭 정책을 정의해야 합니다. 대역폭 제약 조건의 실제 값과 해당 형식은 관계가 없습니다. 최종적인 목표는 시스템에서 서로 다른 바이패스 ID를 자동으로 계산하여 정상적으로 연결되지 않은 각 로캘에 연결하도록 하는 것입니다. 정의를 통해 대역폭 제약 조건을 정의하는 경우에는 링크가 정상적으로 연결되지 않은 것입니다.

  - CAC는 사용하도록 설정하고 미디어 바이패스는 사용하도록 설정하지 않음. 모든 게이트웨이 및 IP-PBX가 정상적으로 연결되어 있지 않거나 미디어 바이패스를 위한 기타 요구 사항을 충족하지 않는 경우에만 적용됩니다. 미디어 바이패스 요구 사항에 대 한 자세한 내용은 [Lync Server 2013의 미디어 바이패스에 대 한 기술 요구 사항을](lync-server-2013-technical-requirements-for-media-bypass.md)참조 하세요.

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 미디어 바이패스 개요](lync-server-2013-overview-of-media-bypass.md)  
[Lync Server 2013의 미디어 바이패스 모드](lync-server-2013-media-bypass-modes.md)  
[Lync Server 2013의 미디어 바이패스에 대 한 기술 요구 사항](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

