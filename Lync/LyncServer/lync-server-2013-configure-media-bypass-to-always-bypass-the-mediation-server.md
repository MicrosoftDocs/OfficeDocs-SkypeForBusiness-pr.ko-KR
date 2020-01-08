---
title: 'Lync Server 2013: 중재 서버를 항상 우회 하도록 미디어 우회 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure media bypass to always bypass the Mediation Server
ms:assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425846(v=OCS.15)
ms:contentKeyID: 48183819
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7aca094110036692c5ac5327b166a3f81e4b769f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981620"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-in-lync-server-2013-to-always-bypass-the-mediation-server"></a>Lync Server 2013에서 미디어 바이패스를 구성 하 여 항상 중재 서버를 우회 하도록 설정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-25_

<div>


> [!NOTE]  
> 이 항목에서는 특정 사용자가 피어 (공공 교환 전화 네트워크 (PSTN) 게이트웨이, IP-PBX 또는 인터넷 통신 서비스 공급자 (ITSP)의 세션 경계 컨트롤러 (SBC)에 대 한 모든 트렁크 연결에 미디어 바이패스를 이미 구성 했다고 가정 합니다. 미디어를 사용 하 여 중재 서버를 우회 하려는 사이트 또는 서비스<BR>호출 허용 제어를 사용 하는 동안 항상 중재 서버를 우회 하도록 미디어를 구성할 수 없습니다. 이러한 설정은 호환 되지 않으므로 Lync Server 제어판 사용자 인터페이스의 상호 배타적인 설정입니다.



</div>

피어에 연결 된 개별 트렁크 연결에 대해 미디어 바이패스를 사용 하도록 설정 하는 것 외에도 미디어 바이패스에 대 한 전역 설정을 구성 해야 합니다. 이 항목의 단계를 사용 하 여 미디어 바이패스에 대 한 전역 설정을 구성 하는 경우, 트렁크 연결에서 미디어 바이패스를 구성한 Lync 끝점과 피어 간에 연결이 양호한 것으로 가정 합니다.

Lync Server 끝점 및 모든 피어가 미디어 바이패스에 대해 사용 하도록 설정 된 중재 서버에 연결 되어 있지 않은 경우에는 다음 경우에 사이트 및 지역 정보를 사용 하도록 글로벌 미디어 우회 설정을 구성 해야 합니다. 미디어 바이패스를 사용 합니다. 이를 통해 미디어가 중재 서버를 우회 하는 시기를 결정 하는 데 더 많은 제어가 가능 합니다. 이렇게 하려면 [Lync server 2013에서 미디어 구성 건너뛰기 전역 설정의 단계를 사용 하 여 사이트 및 지역 정보를 사용 하](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md) 고 [lync server 2013의 네트워크 사이트에 서브넷을 연결](lync-server-2013-associate-a-subnet-with-a-network-site.md) 합니다.

<div>

## <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a>항상 중재 서버를 우회 하기 위해 미디어 우회를 전역적으로 사용 하도록 설정 하려면

1.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

2.  왼쪽 탐색 모음에서 **네트워크 구성을**클릭 합니다.

3.  목록에서 **전역** 구성을 두 번 클릭 합니다.

4.  **전역 설정 편집** 페이지에서 **미디어 무시 사용** 확인란을 선택 합니다.

5.  **항상 무시**를 클릭 합니다.

6.  **커밋**을 클릭합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 미디어 바이패스 구성](lync-server-2013-configure-media-bypass.md)  
[Lync Server 2013의 글로벌 미디어 우회 옵션](lync-server-2013-global-media-bypass-options.md)  
[Lync Server 2013의 미디어 바이패스 및 중재 서버](lync-server-2013-media-bypass-and-mediation-server.md)  


[Lync Server 2013의 미디어 바이패스 계획](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

