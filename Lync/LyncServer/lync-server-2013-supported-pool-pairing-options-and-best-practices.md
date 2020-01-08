---
title: Lync Server 2013 지원 되는 풀 페어링 옵션 및 모범 사례
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Supported pool pairing options and best practices
ms:assetid: 142caf34-0f20-47f3-9d32-ce25ab622fad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204697(v=OCS.15)
ms:contentKeyID: 48183478
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 00202aeb4db74ec81671e557a0679a9f41046b98
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976663"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-pool-pairing-options-and-best-practices-for-lync-server-2013"></a>Lync Server 2013에 대 한 지원 되는 풀 페어링 옵션 및 모범 사례

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2017-03-09_

서로 쌍을 이루는 프런트 엔드 풀을 포함 하는 두 데이터 센터 사이의 거리에는 제한이 없습니다. 동일한 월드 지역에는 두 개의 데이터 센터를 사용 하는 것이 좋으며 그 사이에 고속 연결이 있습니다. 두 데이터 센터가 동시에 단일 재해가 발생 하는 것을 방지 하기에 충분 한 경우에 사용 하는 것이 좋습니다.

전역 영역에 두 개의 데이터 센터를 사용할 수 있지만 데이터 복제의 대기 시간으로 인해 데이터가 더 손실 될 수 있습니다.

연결할 풀을 계획 하는 경우 다음 쌍만 지원 된다는 점에 유의 해야 합니다.

  - Enterprise Edition 풀은 다른 Enterprise Edition 풀과만 쌍으로 연결 될 수 있습니다. 마찬가지로, 표준 버전 풀은 다른 스탠더드 버전 풀과만 쌍으로 연결 될 수 있습니다.

  - 실제 풀은 다른 물리적 풀과만 쌍으로 연결 될 수 있습니다. 마찬가지로 가상 풀은 다른 가상 풀과만 쌍으로 연결 될 수 있습니다.

  - 함께 쌍을 이루는 풀은 동일한 운영 체제를 실행 해야 합니다.

토폴로지 작성기와 토폴로지 유효성 검사가 모두 이러한 권장 사항을 따르지 않는 방식으로 두 풀을 페어링 하지 못하게 됩니다. 예를 들어 토폴로지 작성기를 사용 하면 Enterprise Edition 풀을 스탠더드 버전 풀과 쌍으로 연결할 수 있습니다. 그러나 이러한 유형의 쌍은 지원 되지 않습니다.

한 쌍의 각 풀에는 재해가 발생 한 경우 두 풀의 모든 사용자를 처리할 수 있는 용량이 있어야 합니다.

Enterprise Edition 풀을 쌍으로 하는 경우 백 엔드 서버에서 높은 가용성을 구현할 수 있지만, 스탠더드 버전 풀 쌍에서는 재해 복구 측정값만 사용할 수 있습니다.

</div>

<span> </span>

</div>

</div>

</div>

