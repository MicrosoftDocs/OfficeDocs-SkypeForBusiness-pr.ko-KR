---
title: 'Lync Server 2013: 네트워크 미디어 바이패스 사용'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling network media bypass
ms:assetid: 95c4fa06-49d3-41ac-acdc-7dcda66e5508
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182552(v=OCS.15)
ms:contentKeyID: 48184846
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff18c69d6d257a520d2413bff266c97879d4963e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982977"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-network-media-bypass-in-lync-server-2013"></a>Lync Server 2013에서 네트워크 미디어 바이패스 사용

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-11-01_

미디어 무시 설정은 Microsoft Lync Server 2013 배포 전체에서 전역적으로 적용 됩니다. 미디어 바이패스는 호출을 사용 하 여 중재 서버를 무시할 수 있습니다. 미디어 바이패스를 사용 하는 경우에 대 한 자세한 내용은 계획 섹션의 [Lync Server 2013에서 미디어 바이패스 계획](lync-server-2013-planning-for-media-bypass.md) 을 참조 하세요.

Lync Server 제어판에서 미디어 바이패스를 사용 하도록 설정 하 고 구성할 수 있습니다.

<div>

## <a name="to-enable-and-configure-media-bypass"></a>미디어 바이패스를 사용 하도록 설정 하 고 구성 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **네트워크 구성을** 클릭 한 다음 **전역**을 클릭 합니다.

4.  **전역** 페이지에서 **전역** 구성을 클릭 합니다. 항상 하나의 구성만 있으며 항상 전역 이라는 이름으로 지정 됩니다.

5.  **편집** 메뉴에서 **세부 정보 보기**를 클릭 합니다.

6.  **전역 설정 편집** 페이지에서 **미디어 무시 사용** 확인란을 클릭 합니다.

7.  다음 옵션 중 하나를 선택 합니다.
    
      - **항상 건너뛰기**   이 옵션을 선택 하 여 모든 통화에서 미디어를 우회 하도록 합니다. 호출 허용 제어 (CAC)를 사용 하는 경우이 옵션을 사용할 수 없습니다. CAC를 사용 하도록 설정 하지 않은 경우 다음과 같은 경우이 옵션을 선택 합니다.
        
          - 대역폭 제어는 필요 하지 않습니다.
        
          - 우회가 발생 하는 경우를 결정할 때는 세밀 한 구성이 필요 하지 않습니다.
        
          - 게이트웨이와 클라이언트 간에는 완전 한 연결이 있습니다.
    
      - **사이트 및 지역 구성**   사용 CAC를 사용 하는 경우이 옵션은 기본적으로 선택 되어 있으며 변경할 수 없습니다. 이 옵션을 선택 하면 네트워크 구성 사이트 및 지역이 미디어 바이패스 가능 여부를 결정 하는 데 사용 됩니다. 이 옵션을 선택 하면 매핑되지 않은 사이트에 대해 바이패스를 사용 하도록 선택할 수 있습니다. 대역폭 제약 조건이 없는 (예: 대규모 중앙 사이트) 동일한 지역과 연결 된 대규모 사이트가 하나 이상 있는 경우에만 **매핑되지 않은 사이트에 사용 안 함** 확인란을 클릭 하 고 대역폭 제약 조건이 있는 동일한 지역에 연결 된 일부 지점 사이트를 보유 하 고 있는 경우에만 적용 됩니다. 매핑되지 않은 사이트에 대 한 바이패스를 사용 하도록 설정 하면 모든 사이트와 연결 된 모든 서브넷을 지정 하는 대신 지점 사이트와 연결 된 서브넷만 지정 하므로 구성이 간소화 됩니다. CAC를 사용 하는 경우 **매핑되지 않은 사이트에 바이패스 사용** 확인란을 선택 하지 않는 것이 좋습니다.

8.  **커밋을** 클릭 하 여 변경 내용을 저장 합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 네트워크 미디어 바이패스를 사용 하지 않도록 설정](lync-server-2013-disabling-network-media-bypass.md)  


[Lync Server 2013의 글로벌 미디어 우회 옵션](lync-server-2013-global-media-bypass-options.md)  


[Lync Server 2013의 미디어 바이패스 계획](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

