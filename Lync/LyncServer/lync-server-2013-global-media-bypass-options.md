---
title: 'Lync Server 2013: 전역 미디어 바이패스 옵션'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Global media bypass options
ms:assetid: 1bd35f90-8587-48a1-b0c2-095a4053fc77
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398255(v=OCS.15)
ms:contentKeyID: 48183551
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ebe39b6faeffd36f0dfc9e25959fe7a0b356153
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977459"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="global-media-bypass-options-in-lync-server-2013"></a>Lync Server 2013의 글로벌 미디어 우회 옵션

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-04_

<div>


> [!NOTE]  
> 이 항목에서는 특정 사이트 또는 서비스에 대해 피어 (공공 교환 전화 네트워크 (PSTN) 게이트웨이, IP-PBX 또는 인터넷 전화 통신 서비스 공급자의 세션 경계 컨트롤러 (SBC)에 대 한 trunks에 미디어 bypass을 이미 구성 했다고 가정 합니다. 미디어에서 중재 서버를 우회 하도록 할 수 있습니다.



</div>

피어에 연결 된 개별 트렁크 연결에 대해 미디어 바이패스를 사용 하도록 설정 하는 것 외에도 미디어 우회를 전역적으로 사용 하도록 설정 해야 합니다. 전역 미디어 우회 설정에서는 미디어 bypass을 PSTN에 대 한 통화에 항상 시도 하도록 지정할 수 있으며, 호출 허용 제어에서 수행 하는 것과 유사 하 게 네트워크 사이트 및 네트워크 영역에 대 한 서브넷 매핑을 사용 하 여 미디어 바이패스를 적용 하는 방법도 있습니다. 고급 음성 기능. 미디어 바이패스 및 통화 허용 제어를 모두 사용 하는 경우에는 미디어 바이패스를 사용할지 여부를 결정할 때 호출 허용 컨트롤에 대해 지정 되는 네트워크 지역, 네트워크 사이트 및 서브넷 정보가 자동으로 사용 됩니다. 즉, 통화 허용 제어를 사용 하는 경우 PSTN에 대 한 통화에 대 한 미디어 바이패스를 항상 시도 하도록 지정할 수 없습니다.

이 항목에서는 Lync Server 제어판 및 Lync Server Management Shell을 함께 사용 하 여 전역 미디어 바이패스 설정을 구성 하는 방법을 설명 합니다.

<div>


> [!NOTE]  
> 이러한 단계를 사용 하 여 미디어 바이패스를 구성 하는 경우 클라이언트와 중재 서버 피어 (예: PSTN 게이트웨이, IP PBX 또는 SIP 트렁크 공급자의 SBC) 간에 적절 한 연결을 설정 하는 것으로 가정 합니다. 링크에 대역폭이 제한 되어 있으면 미디어 우회를 통화에 적용할 수 없습니다. 미디어 바이패스는 모든 PSTN 게이트웨이, IP PBX, SBC와 상호 작용 하지 않습니다. Microsoft는 인증 된 파트너와 함께 PSTN 게이트웨이 및 SBCs 집합을 테스트 했으며 Cisco IP-Pbx를 사용 하 여 테스트를 완료 했습니다. 미디어 바이패스는 통합 커뮤니케이션 오픈 상호 운용성 프로그램 –의 Lync Server에 나열 된 제품 및 버전 에서만 <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>지원 됩니다.



</div>

<div>

## <a name="next-steps-choose-global-media-bypass-settings"></a>다음 단계: 전역 미디어 무시 설정 선택

특정 사이트 또는 서비스에 대 한 피어에 대 한 트렁크 연결에서 미디어 바이패스를 사용 하도록 설정한 후에 다음 콘텐츠를 사용 하 여 다음 중 하나를 수행 합니다.

  - 항상 조정 [서버를 우회 하도록 Lync server 2013에서 미디어 바이패스 구성](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md)에 설명 된 대로 미디어 바이패스를 사용 하도록 설정 합니다.

  - 또는 사이트 및 지역 [정보 사용에 대 한 Lync Server 2013의 미디어 건너뛰기 전역 설정](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md)에서 설명한 대로 미디어 우회를 사이트 및 지역 정보에 사용 하도록 구성 합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 미디어 바이패스를 사용 하 여 트렁크 구성](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Lync Server 2013 에서 네트워크 사이트에 서브넷 연결](lync-server-2013-associate-a-subnet-with-a-network-site.md)  


[Lync Server 2013에서 미디어 바이패스 구성](lync-server-2013-configure-media-bypass.md)  
[Lync Server 2013의 미디어 바이패스 및 중재 서버](lync-server-2013-media-bypass-and-mediation-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

