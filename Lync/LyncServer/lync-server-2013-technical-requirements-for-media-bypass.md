---
title: 'Lync Server 2013: 미디어 바이패스에 대 한 기술 요구 사항'
description: 'Lync Server 2013: 미디어 바이패스에 대 한 기술 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for media bypass
ms:assetid: 6162a204-0e7c-460a-8eb2-e592c6590a8a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398435(v=OCS.15)
ms:contentKeyID: 48184321
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dee594139031966342fcec2bc1296a603055b4cc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559444"
---
# <a name="technical-requirements-for-media-bypass-in-lync-server-2013"></a>Lync Server 2013의 미디어 바이패스에 대 한 기술 요구 사항

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-21_

PSTN에 대 한 각 통화에 대해 중재 서버는 중재 서버를 통과 하지 않고 원본에 대 한 온 미디어를 중재 서버 피어로 직접 보낼 수 있는지 여부를 확인 합니다. 피어는 통화가 라우팅될 때 중재 서버 간 트렁크와 연결된 PSTN 게이트웨이, IP-PBX 또는 ITSP(인터넷 전화 통신 서비스 공급업체)의 SBC(세션 경계 컨트롤러)일 수 있습니다.

다음 요구 사항이 충족되는 경우 미디어 바이패스를 적용할 수 있습니다.

  - 중재 서버 피어는 미디어 바이패스를 위해 필요한 기능을 지원 해야 하며, 가장 중요 한 이유는 여러 분기 응답 ("이전 대화" 라고 함)을 처리할 수 있는 기능입니다. 게이트웨이, PBX 또는 SBC에서 수락할 수 있는 최대 초기 대화 상자 수를 구하려면 게이트웨이나 PBX 제조업체에 문의 하거나 ITSP를 사용 합니다.

  - 중재 서버 피어는 Lync 끝점에서 직접 미디어 트래픽을 수락 해야 합니다. 대부분의 ITSPs에서는 SBC가 중재 서버의 트래픽만 수신할 수 있습니다. ITSP에 문의 하 여 SBC가 Lync 끝점에서 직접 미디어 트래픽을 수락 하는지 확인 합니다.

  - Lync 클라이언트와 중재 서버 피어가 연결 되어 있어야 하며, 이러한 피어는 동일한 네트워크 지역에 있거나 대역폭 제한이 없는 WAN 링크를 통해 지역에 연결 되는 네트워크 사이트에 있는 것을 의미 합니다.

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 미디어 바이패스 모드](lync-server-2013-media-bypass-modes.md)  
[Lync Server 2013의 미디어 바이패스 및 통화 허용 제어 서비스](lync-server-2013-media-bypass-and-call-admission-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

