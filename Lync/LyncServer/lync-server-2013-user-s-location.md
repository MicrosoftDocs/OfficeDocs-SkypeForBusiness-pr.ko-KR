---
title: 'Lync Server 2013: 사용자의 위치'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User's location
ms:assetid: ce57941d-086b-448e-8ada-c7d636a2a1c9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994073(v=OCS.15)
ms:contentKeyID: 51803984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9754b75b941944a445da33750190b9347aeb9313
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744438"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="users-location-in-lync-server-2013"></a>Lync Server 2013에서 사용자의 위치

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-03-09_

위치 기반 라우팅은 E9-1-1, CAC 및 Media Bypass에서 사용 하는 Lync Server에 정의 된 것과 동일한 네트워크 지역, 사이트 및 서브넷을 활용 하 여 PSTN 유료 바이패스를 방지 하기 위해 통화 라우팅 제한을 적용 합니다. 사용자의 위치는 사용자의 Lync 끝점에 연결 된 IP 서브넷에 따라 결정 됩니다. 각 IP 서브넷은 관리자가 정의한 네트워크 지역으로 집계 되는 네트워크 사이트에 연결 됩니다. 위치 기반 라우팅은 사용자의 네트워크 사이트를 기준으로 적용 됩니다.

위치 기반 라우팅 규칙은 각 네트워크 사이트 기준에 적용 되며 지정 된 규칙 집합이 동일한 네트워크 사이트 내에 있는 위치 기반 라우팅에 대해 사용 하도록 설정 되어 있는 모든 끝점에 적용 됩니다. 관리자는 위치 기반 라우팅을 필요로 하는 네트워크 사이트에 적용할 수 있습니다.

네트워크 사이트에 있는 모든 사용자가 PSTN 전화 번호를 호출 하는 데 사용 해야 하는 특정 PSTN 게이트웨이를 정의 하기 위해 각 사이트별 사이트 기준으로 음성 라우팅 정책을 정의할 수 있습니다. 이러한 음성 라우팅 정책은 사용자가 위치 기반 라우팅에 대해 사용 하도록 설정 된 네트워크 사이트에 있을 때 사용자의 음성 정책에 의해 정의 된 라우팅 보다 우선 하며, 사용 하도록 설정 되어 있는 다른 PSTN 게이트웨이를 통한 전화 라우팅이 방지 됩니다. 위치 기반 라우팅. Lync 사용자가 PSTN 통화를 하는 경우 사용자의 음성 정책은 사용자에 게 전화를 걸 수 있는 권한을 부여할지 여부를 결정 합니다. 사용자의 음성 정책으로 사용자가 전화를 걸 수 있도록 허용 하는 경우 위치 기반 라우팅은 해당 통화가 송신 하는 PSTN 게이트웨이를 결정 합니다. 위치 기반 라우팅은 사용자의 위치에 따라이 결정을 수행 합니다.

사용자 위치는 다음과 같은 방식으로 분류할 수 있습니다.

  - 사용자가 위치 기반 라우팅에 대해 사용 하도록 설정 된 알려진 네트워크 사이트에 있으며, 같은 네트워크 사이트 (예: office)에 있는 PSTN 게이트웨이에서 종료 된 (직접 안쪽 전화 접속) 번호입니다. 아웃 바운드 통화 라우팅은 사용자가 위치한 네트워크 사이트의 음성 라우팅 정책을 통해 전달 됩니다. 사용자에 게 들어오는 PSTN 호출은 PSTN 게이트웨이와 동일한 네트워크 사이트에 있는 끝점으로 라우팅됩니다.

  - 사용자가 PSTN 게이트웨이가 있는 네트워크 사이트와 다른 알려진 네트워크 사이트에 있습니다. (즉, 사용자가 다른 회사 사무실로 이동한 것입니다.) 아웃 바운드 통화 라우팅은 사용자가 위치한 네트워크 사이트의 음성 라우팅 정책을 사용 하 게 됩니다. PSTN이 비 전화를 우회 하지 못하도록 하기 위해 사용자에 게 보내는 PSTN 호출은 PSTN 게이트웨이를 사용 하는 것과 다른 사이트에 있는 끝점으로 라우팅되지 않습니다.

  - 사용자가 Lync Server 배포에 알려지지 않은 네트워크 사이트에 있는 경우, 아웃 바운드 통화 라우팅은 위치 기반 라우팅 제한에 연결 되지 않은 PSTN 게이트웨이에 대해 사용자에 게 할당 된 음성 정책을 기반으로 하 게 됩니다. PSTN 전화를 우회 하는 것을 방지 하기 위해 수신 PSTN 통화가 알려지지 않은 네트워크 사이트에 있는 끝점으로 라우팅되지 않습니다.

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 위치 기반 라우팅에 대한 지침](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

