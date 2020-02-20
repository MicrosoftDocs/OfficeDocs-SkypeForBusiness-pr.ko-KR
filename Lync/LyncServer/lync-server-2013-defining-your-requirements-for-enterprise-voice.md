---
title: 'Lync Server 2013: Enterprise Voice에 대 한 요구 사항 정의'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organization's requirements for Enterprise Voice
ms:assetid: 3310f78e-c658-4557-95fa-159ce3c22953
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425826(v=OCS.15)
ms:contentKeyID: 48183816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0406286f4f9d8251743fe6ff3a4807dff277fe92
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154710"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-enterprise-voice-in-lync-server-2013"></a>Lync Server 2013에서 Enterprise Voice에 대 한 요구 사항 정의

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-08-07_

이 항목에서는 영역, 사이트 및 토폴로지의 사이트 간 링크 및 Enterprise Voice를 배포할 때의 중요 한 고려 사항에 대 한 개요를 제공 합니다. 이러한 결정을 내리는 데 도움이 되는 자세한 내용은 계획 설명서에서 [Lync Server 2013의 Advanced Enterprise Voice 기능에 대 한 네트워크 설정을](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md) 참조 하십시오.

<div>

## <a name="sites-and-regions"></a>사이트 및 지역

먼저 엔터프라이즈 Voice를 배포할 토폴로지의 사이트와 해당 사이트가 속한 네트워크 지역을 식별 합니다. 특히, 각 사이트에 공중 전화망(PSTN) 연결을 제공할 방법을 고려합니다. 관리 편의성 및 물류상의 이유로, 이러한 사이트가 속하는 지역은 중요한 요인이 될 수 있습니다. 게이트웨이를 로컬로 배포할 위치를 결정 합니다 (Sba (survivable Branch 기기 (SBAs)이 배포 되 고, SIP 트렁크 (로컬 또는 중앙 사이트에서)를 ITSP (인터넷 전화 통신 서비스 공급자)로 구성할 수 있습니다.

</div>

<div>

## <a name="network-links-between-sites"></a>사이트 간의 네트워크 링크

또한 중앙 사이트와 해당 분기 사이트 간의 네트워크 링크에 대해 예상 되는 대역폭 사용량을 고려해 야 합니다. 사이트 간 WAN 링크를 보유 하 고 있거나 배포를 계획 하는 경우에는 각 분기 사이트에 게이트웨이를 배포 하 여 해당 사이트의 사용자에 대 한 로컬 직접 안쪽 전화 걸기 (연결) 종료를 제공 하는 것이 좋습니다. 탄력적인 WAN 링크는 있지만 해당 WAN 링크의 대역폭이 제한될 것으로 예상된다면 해당 링크에 대해 통화 허용 제어를 구성합니다. 복구 가능한 WAN 링크가 없는 경우 분기 사이트에서 1000 명 미만의 사용자를 호스트 하 고 로컬에 숙련 된 Lync Server 관리자를 사용할 수 없는 경우 분기 사이트에서 Sba (survivable Branch 기기를 배포 하는 것이 좋습니다. 분기 사이트에서 1000와 5000 사용자 간에 호스트 하는 경우, 복원 가능한 WAN 연결이 부족 하 고 교육 된 Lync Server 관리자를 사용할 수 있는 경우 분기 사이트에 작은 게이트웨이로 Sba (survivable 분기 서버를 배포 하는 것이 좋습니다. 또한 미디어 바이패스를 지원하는 게이트웨이 피어가 있는 경우에는 제한된 링크에 대해 미디어 바이패스를 사용하도록 설정하는 것도 고려하십시오.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 고급 Enterprise Voice 기능에 대 한 네트워크 설정](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

