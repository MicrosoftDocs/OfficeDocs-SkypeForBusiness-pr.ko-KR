---
title: 'Lync Server 2013: 위치 정책 범위 할당'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assigning location policy scope
ms:assetid: e4c66517-c593-4253-b900-7b4dd8bddf2f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205360(v=OCS.15)
ms:contentKeyID: 48185734
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 090c0d4e7ce65f633458860f0c488e4257d15b5a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499425"
---
# <a name="assigning-location-policy-scope-in-lync-server-2013"></a>Lync Server 2013에서 위치 정책 범위 할당

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-06-06_

다른 Lync Server 정책과 마찬가지로 위치 정책은 전역, 사이트 및 사용자의 여러 범위 수준에서 할당할 수 있습니다. 그러나 사용자 수준 위치 정책의 범위는 다른 Lync Server 정책과 약간 다르게 동작 합니다. 사용자 또는 공통 영역 전화 연락처 개체와 같은 끝점 개체에는 사용자별 위치 정책을 적용 하는 것 뿐만 아니라 Lync Server 네트워크 사이트에도 적용할 수 있습니다. 네트워크 사이트는 지리적 위치와 연결 된 클라이언트 서브넷의 그룹으로, 전체 중앙 사이트 또는 분기 사이트의 모든 서브넷 일 필요는 없습니다. 네트워크 사이트의 서브넷에 연결 된 클라이언트는 자동으로 해당 네트워크 사이트에 할당 되는 위치 정책을 선택 합니다. 사용자 수준 위치 정책이 사용자와 네트워크 사이트에 모두 할당 되는 경우 네트워크 사이트 기반 위치 정책이 사용자별 정책 설정 보다 우선 합니다.

각 네트워크 사이트에는 위치 정책이 할당되어 있으며 각 정책에는 서로 다른 PSTN 사용, 알림 URI 및 회의 URI 값이 할당됩니다.

<div>


> [!NOTE]  
> 이 특수 정책 범위 지정 동작이 발생 하는 이유는 한 office 사이트의 풀에 있는 사용자가 다른 사이트를 방문 하 고 긴급 통화를 해야 하는 경우 해당 네트워크 사이트에 적합 한 E9-1-1 통화 라우팅 설정이 사용자가 할당 된 풀 또는 사이트에 관계 없이 적용 되도록 하는 것입니다.



</div>

</div>

<span> </span>

</div>

</div>

</div>

