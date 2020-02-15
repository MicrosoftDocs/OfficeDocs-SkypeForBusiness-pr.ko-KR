---
title: 'Lync Server 2013: 전역 미디어 바이패스 옵션'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Global media bypass options
ms:assetid: 1bd35f90-8587-48a1-b0c2-095a4053fc77
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398255(v=OCS.15)
ms:contentKeyID: 48183551
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b6a5f0d7a6a89b30b0ef08f8631b06fb9047616
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007817"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="global-media-bypass-options-in-lync-server-2013"></a>Lync Server 2013의 글로벌 미디어 바이패스 옵션

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-04_

<div>


> [!NOTE]  
> 이 항목에서는 특정 사이트 또는 서비스에 대해 모든 트렁크에 대 한 미디어 바이패스를 피어 (IP (공중 전화망) 게이트웨이, ip-pbx 또는 인터넷 전화 통신 서비스 공급자의 SBC (세션 경계 컨트롤러)에 이미 구성 했다고 가정 합니다. 미디어에서 중재 서버를 바이패스 하도록 하려는 경우



</div>

피어와 연결 된 개별 트렁크 연결에 미디어 바이패스를 사용 하도록 설정 하는 것 외에도 미디어 바이패스를 전역적으로 사용 하도록 설정 해야 합니다. 전역 미디어 바이패스 설정에서는 미디어 바이패스를 PSTN 통화에 대해 항상 시도 하도록 지정할 수도 있고, 통화 허용 제어에서 수행 하는 것과 비슷한 방식으로 네트워크 사이트 및 네트워크 지역에 서브넷 매핑을 사용 하 여 미디어 바이패스가 적용 됨을 지정 하는 방법 고급 음성 기능 미디어 바이패스 및 통화 허용 제어를 둘 다 사용 하는 경우 통화 허용 제어에 지정 된 네트워크 지역, 네트워크 사이트 및 서브넷 정보는 미디어 바이패스를 사용할지 여부를 결정할 때 자동으로 사용 됩니다. 즉, 통화 허용 제어를 사용 하도록 설정 된 경우 PSTN을 호출 하는 경우에는 미디어 바이패스를 항상 시도 하도록 지정할 수 없습니다.

이 항목에서는 Lync Server 제어판과 Lync Server 관리 셸을 함께 사용 하 여 전역 미디어 바이패스 설정을 구성 하는 방법에 대해 설명 합니다.

<div>


> [!NOTE]  
> 여기서 설명하는 단계를 사용하여 미디어 바이패스를 구성하는 경우, 클라이언트와 중재 서버 피어(예: SIP 트렁크 공급자의 SBC, IP-PBX 또는 PSTN 게이트웨이) 간의 연결이 원활하다고 가정합니다. 링크에 대한 대역폭 제한이 있는 경우에는 미디어 바이패스를 통화에 적용할 수 없습니다. 미디어 바이패스가 모든 PSTN 게이트웨이, IP-PBX 및 SBC에서 작동하지는 않습니다. Microsoft는 인증 된 파트너와의 PSTN 게이트웨이 및 국내 집합을 테스트 했으며 Cisco IP-Pbx를 사용 하 여 몇 가지 테스트를 수행 했습니다. 미디어 바이패스는 통합 커뮤니케이션 오픈 상호 운용성 프로그램-Lync Server에 <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>나열 된 제품 및 버전 에서만 지원 됩니다.



</div>

<div>

## <a name="next-steps-choose-global-media-bypass-settings"></a>다음 단계: 전역 미디어 바이패스 설정 선택

특정 사이트 또는 서비스에서 피어로의 트렁크 연결에 미디어 바이패스를 사용하도록 설정한 후에는 다음 콘텐츠를 참조하여 각 작업을 수행하십시오.

  - 항상 [중재 서버를 바이패스 하도록 Lync server 2013의 Configure media bypass](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md)에 설명 된 대로 미디어 바이패스를 사용 하도록 설정 합니다.

  - 또는 [사이트 및 지역 정보를 사용 하도록 Lync Server 2013의 미디어 바이패스 전역 설정 구성](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md)에 설명 된 대로 사이트 및 지역 정보를 사용 하도록 미디어 바이패스를 구성 합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 미디어 바이패스로 트렁크 구성](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Lync Server 2013에서 서브넷을 네트워크 사이트에 연결](lync-server-2013-associate-a-subnet-with-a-network-site.md)  


[Lync Server 2013에서 미디어 바이패스 구성](lync-server-2013-configure-media-bypass.md)  
[Lync Server 2013의 미디어 바이패스 및 중재 서버](lync-server-2013-media-bypass-and-mediation-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

