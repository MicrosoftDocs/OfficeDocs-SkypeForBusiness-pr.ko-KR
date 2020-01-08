---
title: 'Lync Server 2013: 풀 장애 복구(failback)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing back a pool
ms:assetid: 6232b644-ef57-4c9c-abec-14ff8ffc9fe7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204945(v=OCS.15)
ms:contentKeyID: 48184289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cade83015f57e86e08978ac3bfd9fb848dae9563
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984576"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-back-a-pool-in-lync-server-2013"></a>Lync Server 2013에서 풀 장애 복구(failback)

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-11-01_

재해가 발생 한 풀이 온라인 상태가 된 후 (즉,이 예제에서 Pool1) 다음 단계를 수행 하 여 배포를 정상 작업 상태로 복원 합니다.

장애 복구 프로세스가 완료 되기까지 몇 분이 소요 됩니다.참조용으로 2만 사용자 풀에 대해 최대 60 분이 소요 될 것으로 예상 됩니다.

1.  Pool1에서 원래 홈 이었던 사용자와 다음 cmdlet을 입력 하 여 Pool2에 장애 조치 (Fail over)를 다시 실행 합니다.
    
        Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

다른 단계는 필요 하지 않습니다. 중앙 관리 서버를 장애 조치 (Pool2) 한 경우에는 그대로 둘 수 있습니다.

</div>

<span> </span>

</div>

</div>

</div>

