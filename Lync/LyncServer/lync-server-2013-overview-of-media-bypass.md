---
title: 'Lync Server 2013: 미디어 바이패스 개요'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of media bypass
ms:assetid: 9ea090b3-f607-46f7-97dd-2510052524e5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412740(v=OCS.15)
ms:contentKeyID: 48184924
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 84c70cae521deebecf30e7c8ec6505b18e9842fa
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755502"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-media-bypass-in-lync-server-2013"></a>Lync Server 2013의 미디어 바이패스 개요

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-21_

미디어 바이패스는 배포 된 중재 서버 수를 최소화 하려는 경우에 유용 합니다. 일반적으로 중재 서버 풀은 중앙 사이트에 배포 되며 지점 사이트에서 게이트웨이를 제어 합니다. 미디어 바이패스를 사용 하도록 설정 하면 지점 사이트에서 클라이언트의 PSTN (공개 통신 네트워크) 호출에 대 한 미디어가 해당 사이트의 게이트웨이를 통해 직접 흐를 수 있습니다. Lync Server 2013 아웃 바운드 통화 경로와 엔터프라이즈 음성 정책을 적절 하 게 구성 하 여 지점 사이트의 클라이언트에 대 한 PSTN 호출이 해당 게이트웨이로 라우팅되도록 합니다.

Wi-fi 네트워크에는 일반적으로 유선 네트워크 보다 더 많은 패킷 손실이 발생 합니다. 이 패킷 손실에 대 한 복구는 일반적으로 게이트웨이에서 수용할 수 있는 것이 아닙니다. 따라서 무선 서브넷에 대해 우회를 사용 해야 하는지 여부를 결정 하기 전에 Wi-fi 네트워크의 품질을 평가 하는 것이 좋습니다. 대기 시간 감소와 패킷 손실에 대 한 복구도 고려해 야 합니다. 중재 서버를 우회 하지 않는 호출에 사용할 수 있는 RTAudio는 패킷 손실 처리에 더 적합 합니다.

엔터프라이즈 음성 구조가 준비 된 후 미디어 바이패스 계획은 간단 합니다.

  - 지점 사이트에 대 한 WAN 링크 없이 중앙 집중화 된 토폴로지가 있는 경우 세밀 하 게 조정 된 컨트롤이 필요 하지 않으므로 전역 미디어 바이패스를 사용 하도록 설정할 수 있습니다.

  - 하나 이상의 네트워크 지역 및 관련 지점 사이트로 구성 된 분산 토폴로지가 있는 경우 다음을 결정 합니다.
    
      - 중재 서버 피어가 미디어 바이패스에 필요한 기능을 지원할 수 있는지 여부
    
      - 각 네트워크 영역에 제대로 연결 된 사이트
    
      - 미디어 우회 및 통화 허용 제어의 조합은 네트워크에 적합 합니다.

미디어 바이패스를 사용 하도록 설정 하면 네트워크 영역과 해당 지역 내에서 대역폭 제약 조건이 없는 모든 네트워크 사이트에 대해 고유한 우회 ID가 자동으로 생성 됩니다. 지역 내에서 대역폭 제약 조건이 있는 사이트 및 대역폭 제약 조건이 있는 WAN 링크를 통해 지역에 연결 된 사이트에는 각각 고유한 우회 Id가 할당 됩니다.

사용자가 PSTN에 전화를 거는 경우 중재 서버는 클라이언트 서브넷의 우회 ID를 게이트웨이 서브넷의 우회 ID와 비교 합니다. 두 우회 Id가 일치 하는 경우 통화에 미디어 바이패스를 사용 합니다. 우회 Id가 일치 하지 않는 경우, 통화에 대 한 미디어는 중재 서버를 통해 전달 되어야 합니다.

사용자가 PSTN에서 전화를 받으면 사용자의 클라이언트는 우회 ID를 PSTN 게이트웨이의 해당 사용과 비교 합니다. 두 우회 Id가 일치 하는 경우에는 클라이언트가 게이트웨이에서 클라이언트에 게 직접 전달 하 고 중재 서버를 건너뜁니다.

Lync 2010 이상 클라이언트 및 장치만 미디어 조정 서버와의 상호 작용을 지원 합니다.

<div>


> [!IMPORTANT]  
> 미디어 우회를 전역적으로 사용 하도록 설정 하는 것 외에, 각 PSTN 트렁크에서 미디어 우회를 개별적으로 사용 하도록 설정 해야 합니다. Bypass을 전역으로 사용 하도록 설정 했지만 특정 PSTN 트렁크에 대해 사용 하도록 설정 하지 않은 경우에는 해당 PSTN 트렁크와 관련 된 모든 통화에 대해 미디어 바이패스를 호출 하지 않습니다. 또한, 미디어 바이패스가 <STRONG>사이트 및 지역 정보를 사용</STRONG>하도록 설정 된 경우에는 라우팅할 수 있는 모든 서브넷을 해당 사용자가 위치한 사이트와 연결 해야 합니다. 사이트 내에서 bypass이 필요 하지 않은 라우팅 가능한 서브넷이 있는 경우 미디어 바이패스를 사용 하도록 설정 하기 전에 이러한 서브넷을 새 사이트 내에서 그룹화 해야 합니다. 이렇게 하면 unroutable 서브넷에 다른 우회 ID가 할당 됩니다.



</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 미디어 바이패스 모드](lync-server-2013-media-bypass-modes.md)  
[Lync Server 2013의 미디어 바이패스 및 통화 허용 제어 서비스](lync-server-2013-media-bypass-and-call-admission-control.md)  
[Lync Server 2013의 미디어 바이패스에 대한 기술 요구 사항](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

