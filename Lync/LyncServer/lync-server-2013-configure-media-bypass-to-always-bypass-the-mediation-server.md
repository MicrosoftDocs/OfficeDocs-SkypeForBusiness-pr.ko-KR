---
title: 'Lync Server 2013: 중재 서버를 항상 바이패스 하도록 미디어 바이패스 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure media bypass to always bypass the Mediation Server
ms:assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425846(v=OCS.15)
ms:contentKeyID: 48183819
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 376ce5c00b4d326f283d1fde204d6c1bd17dd1de
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038300"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-in-lync-server-2013-to-always-bypass-the-mediation-server"></a>Lync Server 2013에서 미디어 바이패스를 구성 하 여 항상 중재 서버를 바이패스 하도록 설정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-25_

<div>


> [!NOTE]  
> 이 항목에서는 미디어가 중재 서버를 바이패스하도록 할 특정 사이트 또는 서비스에 대해 모든 트렁크 연결에 대한 미디어 바이패스를 피어(ITSP(인터넷 전화 통신 서비스 공급자)의 SBC(Session Border Controller), IP-PBX 또는 공중 전화망(PSTN) 게이트웨이)로 이미 구성했다고 가정합니다.<BR>통화 허용 제어를 사용하도록 설정하는 동시에 중재 서버를 항상 바이패스하도록 미디어를 구성할 수는 없습니다. 이러한 설정은 호환 되지 않으므로 Lync Server 제어판 사용자 인터페이스의 상호 배타적인 설정입니다.



</div>

피어와 연결된 개별 트렁크 연결에 대해 미디어가 중재 서버를 바이패스하도록 설정하는 것 외에, 미디어 바이패스를 위한 전역 설정도 구성해야 합니다. 이 항목의 단계를 사용 하 여 미디어 바이패스에 대 한 전역 설정을 구성 하는 경우에는 Lync 끝점과 트렁크 연결에서 미디어 바이패스를 구성한 피어 사이에 적절 한 연결이 설정 되어 있는 것으로 가정 합니다.

Lync Server 끝점과 모든 피어가 미디어 바이패스를 사용할 수 있도록 설정 된 중재 서버에 대 한 적절 한 연결을 사용 하지 않는 경우에는 다음 경우에 사이트 및 지역 정보를 사용 하도록 전역 미디어 바이패스 설정을 구성 해야 합니다. 미디어 바이패스를 사용 합니다. 이렇게 하면 미디어가 중재 서버를 바이패스하는 경우를 보다 정밀하게 제어할 수 있습니다. 이렇게 하려면 [Lync server 2013의 미디어 바이패스 전역 설정 구성의 단계를 사용 하 여 사이트 및 지역 정보를 사용 하](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md) 고 대신 [lync server 2013에서 서브넷을 네트워크 사이트에 연결](lync-server-2013-associate-a-subnet-with-a-network-site.md) 합니다.

<div>

## <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a>항상 중재 서버를 바이패스하도록 전역적으로 미디어 바이패스를 설정하려면

1.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

2.  왼쪽 탐색 모음에서 **네트워크 구성**을 클릭합니다.

3.  목록에서 **전역** 구성을 두 번 클릭합니다.

4.  **전역 설정 편집** 페이지에서 **미디어 바이패스 사용** 확인란을 선택합니다.

5.  **항상 바이패스**를 클릭합니다.

6.  **커밋**을 클릭합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 미디어 바이패스 구성](lync-server-2013-configure-media-bypass.md)  
[Lync Server 2013의 글로벌 미디어 바이패스 옵션](lync-server-2013-global-media-bypass-options.md)  
[Lync Server 2013의 미디어 바이패스 및 중재 서버](lync-server-2013-media-bypass-and-mediation-server.md)  


[Lync Server 2013의 미디어 바이패스 계획](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

