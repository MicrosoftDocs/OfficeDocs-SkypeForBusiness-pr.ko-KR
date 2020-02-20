---
title: 'Lync Server 2013: 미디어 바이패스 및 중재 서버'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media bypass and Mediation Server
ms:assetid: 8ed35f95-05cd-4b5d-8470-442d2323df71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398719(v=OCS.15)
ms:contentKeyID: 48184774
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a33ed2c9b3494e9c67e8ac4a658b6aee75ff7649
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149858"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="media-bypass-and-mediation-server-in-lync-server-2013"></a>Lync Server 2013의 미디어 바이패스 및 중재 서버

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-21_

미디어 바이패스는 관리자가 중재 서버를 통과 하지 않고 사용자 끝점과 PSTN (공중 전화망) 게이트웨이 간에 직접 흐르도록 전화 라우팅을 구성할 수 있도록 하는 Lync Server 기능입니다. 미디어 바이패스는 대기 시간, 불필요 한 변환, 패킷 손실 가능성 및 잠재적 실패 지점 수를 줄여 통화 품질을 향상 시킵니다. 중재 서버가 없는 원격 사이트가 제한 된 대역폭을 사용 하는 하나 이상의 WAN 링크에 의해 중앙 사이트에 연결 되는 경우 미디어 바이패스는 원격 사이트의 클라이언트에서 미디어를 사용 하 여 로컬 게이트웨이로 바로 이동 하 여 대역폭 요구 사항을 줄입니다. 먼저 WAN 링크에서 중앙 사이트의 중재 서버로 이동 하 고 다시 해야 합니다. 이 미디어 처리 절감은 또한 중재 서버의 여러 게이트웨이를 제어 하는 기능을 보완 합니다.

미디어 바이패스와 CAC(통화 허용 제어)는 함께 사용할 수 없습니다. 통화에 미디어 바이패스가 사용되는 경우 해당 통화에 대해 CAC가 수행되지 않습니다. 통화에 관련된 제한된 대역폭에 대한 링크가 없다고 가정합니다.

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 통화 허용 제어 및 중재 서버](lync-server-2013-call-admission-control-and-mediation-server.md)  


[Lync Server 2013의 미디어 바이패스 계획](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

