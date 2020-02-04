---
title: 'Lync Server 2013: 미디어 바이패스 모드'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media bypass modes
ms:assetid: 38c06c81-7e45-4423-9e00-7fbfa4befe46
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425862(v=OCS.15)
ms:contentKeyID: 48183898
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f92d45099f39ec96724f8d0f6025f58e2dbccb2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41761954"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-bypass-modes-in-lync-server-2013"></a>Lync Server 2013의 미디어 바이패스 모드

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-05_

미디어 우회를 각 개별 PSTN 트렁크에 대해 전역적으로 또는 개별적으로 구성 해야 합니다. 미디어 우회를 전역적으로 사용 하는 경우 두 가지 선택이 가능 합니다. 항상 **사이트 및 지역 정보**를 **우회** 하 고 사용 합니다.

이름에서 알 수 있듯이, 모든 PSTN 호출에 대해 bypass을 시도 하는 것은 **항상 무시** 됩니다. **항상 바이패스** 는 통화 허용 제어를 사용할 필요가 없는 배포에 사용 되며 미디어를 우회 하는 경우에 대 한 자세한 구성 정보를 지정할 필요가 없습니다. 더욱이 클라이언트와 PSTN 게이트웨이 간에 완전 한 연결이 있는 경우 **항상 Bypass** 를 사용 합니다. 이 구성에서는 모든 서브넷이 한 번의 우회 ID로 매핑되고 시스템에서 계산 됩니다.

**사이트 및 지역 정보를 사용**하면 사이트 및 지역 구성과 연결 된 우회 ID를 사용 하 여 우회를 결정할 수 있습니다. 이 구성은 bypass이 발생 하는 경우에 대 한 세부적인 제어 기능을 제공 하 고 호출 허용 제어 (CAC)와의 상호 작용을 지원 하기 때문에 대부분의 일반적인 토폴로지에 대해 우회를 구성할 수 있습니다. 시스템은 다음과 같이 우회 Id를 자동으로 할당 하 여 작업을 간편 하 게 시도 합니다.

  - 시스템은 각 지역에 고유한 단일 우회 ID를 자동으로 할당 합니다.

  - 대역폭 제약 조건을 사용 하지 않고 WAN 링크를 통해 지역에 연결 된 모든 사이트는 지역과 동일한 우회 ID를 상속 합니다.

  - 제한 된 대역폭이 있는 WAN 링크를 통해 지역에 연결 된 사이트에는 지역과 다른 우회 ID가 지정 됩니다.

  - 각 사이트에 연결 된 서브넷은 해당 사이트의 우회 ID를 상속 합니다.

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 미디어 바이패스 개요](lync-server-2013-overview-of-media-bypass.md)  
[Lync Server 2013의 미디어 바이패스 및 통화 허용 제어 서비스](lync-server-2013-media-bypass-and-call-admission-control.md)  
[Lync Server 2013의 미디어 바이패스에 대한 기술 요구 사항](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

