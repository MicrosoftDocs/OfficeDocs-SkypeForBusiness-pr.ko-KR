---
title: 'Lync Server 2013: 네트워크 미디어 바이패스 사용'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling network media bypass
ms:assetid: 95c4fa06-49d3-41ac-acdc-7dcda66e5508
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182552(v=OCS.15)
ms:contentKeyID: 48184846
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e4caab36c57c3c8901bd0691e5623f232879bd03
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528525"
---
# <a name="enabling-network-media-bypass-in-lync-server-2013"></a>Lync Server 2013에서 네트워크 미디어 바이패스 사용

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-11-01_

미디어 바이패스 설정은 Microsoft Lync Server 2013 배포 전체에서 전역적으로 적용 됩니다. 미디어 바이패스는 통화가 중재 서버를 바이패스하도록 허용합니다. 미디어 바이패스를 사용 하는 경우에 대 한 자세한 내용은 계획 섹션에서 [Lync Server 2013의 미디어 바이패스 계획](lync-server-2013-planning-for-media-bypass.md) 을 참조 하십시오.

Lync Server 제어판에서 미디어 바이패스를 사용 하도록 설정 하 고 구성할 수 있습니다.

<div>

## <a name="to-enable-and-configure-media-bypass"></a>미디어 바이패스를 사용하도록 설정 및 구성하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정 (또는 이와 동등한 사용자 권한 포함) 또는 CsAdministrator 역할이 할당 되 면 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **네트워크 구성**을 클릭하고 **전역**을 클릭합니다.

4.  **전역** 페이지에서 **전역** 구성을 클릭합니다. 구성은 항상 하나뿐이며 이름은 항상 전역입니다.

5.  **편집** 메뉴에서 **자세히 보기**를 클릭합니다.

6.  **전역 설정 편집** 페이지에서 **미디어 바이패스 사용** 확인란을 클릭합니다.

7.  다음 옵션 중 하나를 선택합니다.
    
      - **항상 바이패스**     모든 통화에 미디어 바이패스를 시도 하려면이 옵션을 선택 합니다. CAC (통화 허용 제어)가 사용 하도록 설정 된 경우에는이 옵션을 사용할 수 없습니다. CAC가 사용 되지 않는 경우에는 다음과 같은 상황에서이 옵션을 선택 합니다.
        
          - 대역폭을 제어할 필요가 없는 경우
        
          - 바이패스가 발생하는 시기를 확인하기 위해 세분화된 구성이 필요하지 않은 경우
        
          - 게이트웨이와 클라이언트가 완전히 연결된 경우
    
      - **사이트 및 지역 구성 사용**     CAC가 사용 하도록 설정 된 경우이 옵션은 기본적으로 선택 되며 변경할 수 없습니다. 이 옵션을 선택하면 네트워크 구성 사이트 및 지역이 미디어 바이패스가 가능한 때를 확인하는 데 사용됩니다. 이 옵션을 선택하면 매핑되지 않은 사이트에 바이패스를 사용할 수 있습니다. 대역폭 제약 조건이 없는 동일한 지역과 연결된 대규모 사이트가 하나 이상 있고(예: 대규모 중앙 사이트) 대역폭 제약 조건이 있는 동일한 지역과 연결된 분기 사이트도 몇 군데 있는 경우에만 **매핑되지 않은 사이트에 대해 바이패스 사용** 확인란을 클릭합니다. 매핑되지 않은 사이트에 대해 바이패스를 사용하도록 설정하면, 모든 서브넷이 모든 사이트와 연결되도록 지정할 필요 없이 서브넷이 분기 사이트와 연결되도록만 지정하면 되므로 구성이 능률적이게 됩니다. CAC를 사용하도록 설정한 경우에는 **매핑되지 않은 사이트에 대해 바이패스 사용** 확인란을 선택하지 않는 것이 좋습니다.

8.  **커밋**을 클릭하여 변경 내용을 저장합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 네트워크 미디어 바이패스 사용 안 함](lync-server-2013-disabling-network-media-bypass.md)  


[Lync Server 2013의 글로벌 미디어 바이패스 옵션](lync-server-2013-global-media-bypass-options.md)  


[Lync Server 2013의 미디어 바이패스 계획](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

