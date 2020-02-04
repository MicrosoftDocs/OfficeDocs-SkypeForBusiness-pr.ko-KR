---
title: 'Lync Server 2013: Enterprise Voice에 대한 요구 사항 정의'
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
ms.openlocfilehash: 8987905d2b117eb889486882b7d74ce4e52659a8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739938"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-enterprise-voice-in-lync-server-2013"></a>Lync Server 2013에서 Enterprise Voice에 대한 요구 사항 정의

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-08-07_

이 항목에서는 영역, 사이트 및 토폴로지의 사이트 간 링크와 엔터프라이즈 음성을 배포 하는 경우의 중요 한 고려 사항에 대 한 개요를 제공 합니다. 이러한 결정을 내리는 데 도움이 되는 자세한 내용은 계획 설명서의 [Lync Server 2013의 고급 엔터프라이즈 음성 기능에 대 한 네트워크 설정을](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md) 참조 하세요.

<div>

## <a name="sites-and-regions"></a>사이트 및 지역

먼저 엔터프라이즈 음성과 해당 사이트가 속한 네트워크 지역을 배포할 토폴로지에서 사이트를 식별 합니다. 특히, 각 사이트에 대 한 PSTN (공개 교환 전화 네트워크) 연결을 제공 하는 방법을 고려 하세요. 관리 효율성 및 logistical 이유로 이러한 사이트가 속한 지역은 결정 요인이 될 수 있습니다. 게이트웨이가 로컬로 배포 되는 위치 (Survivable Branch 기기 (SBAs)가 배포 되 고 SIP trunks (로컬 또는 중앙 사이트에서)를 인터넷 전화 통신 서비스 공급자 (ITSP)에 구성할 수 있는 위치를 결정 합니다.

</div>

<div>

## <a name="network-links-between-sites"></a>사이트 간 네트워크 링크

또한 중앙 사이트와 해당 지점 사이트 간의 네트워크 연결에 대해 예상 되는 대역폭 사용량을 고려해 야 합니다. 사이트 간 WAN 연결을 보유 하 고 있거나 배포 하려는 경우 각 지점 사이트에서 게이트웨이를 배포 하 여 해당 사이트의 사용자에 대 한 로컬 직접 안쪽 다이얼 (의) 종료를 제공 하는 것이 좋습니다. 복원성 WAN 링크가 있지만 WAN 링크의 대역폭이 제한 될 가능성이 높은 경우 해당 링크에 대 한 통화 허용 제어를 구성 합니다. 회복성 있지 않은 WAN 연결이 없는 경우 지사 사이트에서 1000 사용자 보다 적은 수의 호스트를 사용 하 고 로컬의 숙련 된 Lync Server 관리자가 없는 경우, 지점 사이트에서 Survivable Branch 기기를 배포 하는 것이 좋습니다. 지점 사이트에서 1000와 5000 사용자 간 호스팅, 복원성 WAN 연결이 부족 하 고 교육 된 Lync Server 관리자를 사용할 수 있는 경우, 지점 사이트에 small gateway를 사용 하 여 Survivable Branch 서버를 배포 하는 것이 좋습니다. 미디어 바이패스를 지 원하는 게이트웨이 피어가 있는 경우 제한 된 링크에서 미디어 바이패스를 사용 하도록 설정 하는 것도 고려해 야 합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 고급 엔터프라이즈 음성 기능에 대 한 네트워크 설정](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

