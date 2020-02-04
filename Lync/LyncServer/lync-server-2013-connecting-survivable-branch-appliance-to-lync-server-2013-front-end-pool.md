---
title: Lync Server 2013 프런트 엔드 풀에 SBA(Survivable Branch Appliance) 연결
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Connecting Survivable Branch Appliance to Lync Server 2013 Front End pool
ms:assetid: 3c7ca33f-5295-4d82-9152-41d8bc6f35cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688026(v=OCS.15)
ms:contentKeyID: 49733616
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d73806f481cfe7c44a5eb9507d043565765a08f9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740578"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connecting-survivable-branch-appliance-to-lync-server-2013-front-end-pool"></a>Lync Server 2013 프런트 엔드 풀에 SBA(Survivable Branch Appliance) 연결

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-05_

모든 Survivable Branch 기기 (SBA)는 SBA에 대 한 백업 등록 기관 역할을 하는 프런트 엔드 풀과 연결 되어 있습니다. 프런트 엔드 풀을 Lync Server 2013으로 업그레이드 한 경우 프런트 엔드 풀을 업그레이드 하는 동안에는 SBA를 프런트 엔드 풀에서 분리 해야 합니다. 프런트 엔드 풀을 업그레이드 한 후에는 프런트 엔드 풀을 사용 하 여 reassociated 수 있습니다. 여기에는 토폴로지 작성기의 토폴로지에서 SBA를 삭제 한 다음 토폴로지 작성기에 SBA를 다시 추가 하는 작업이 포함 됩니다. SBA의 사용자를 다른 프런트 엔드 풀로 이동한 후에는 토폴로지에서 SBA를 제거 해야 합니다. SBA가 토폴로지에 다시 추가 된 후 해당 사용자는 다시 SBA로 이동할 수 있습니다.

이러한 단계는 다음과 같이 요약할 수 있습니다.

1.  SBA에 속한 분기 사용자를 다른 프런트 엔드 풀로 이동 합니다.

2.  토폴로지에서 기존 프런트 엔드 풀을 제거 하 여 백업 등록 기관으로 분리할 수 있습니다.

3.  프런트 엔드 풀을 Microsoft Lync Server 2013로 업그레이드 합니다.

4.  토폴로지에 다시 추가 합니다.

5.  새 프런트 엔드 풀을 백업 등록 기관으로 SBA에 연결 합니다.

6.  분기 사용자를 다시 SBA로 이동 합니다.

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [토폴로지에 Lync Server 2013 SBA(Survivable Branch Appliance) 분기 사이트 추가](lync-server-2013-add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology.md)

  - [토폴로지에 Lync Server 2010 SBA(Survivable Branch Appliance) 분기 사이트 추가](lync-server-2013-add-lync-server-2010-survivable-branch-appliance-branch-site-to-your-topology.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

