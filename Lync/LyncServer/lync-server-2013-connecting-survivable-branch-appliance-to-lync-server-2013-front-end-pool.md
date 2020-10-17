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
ms.openlocfilehash: b7a637716f1e5b1a2082f694554951d42f36978f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502025"
---
# <a name="connecting-survivable-branch-appliance-to-lync-server-2013-front-end-pool"></a>Lync Server 2013 프런트 엔드 풀에 SBA(Survivable Branch Appliance) 연결

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-05_

모든 Sba (survivable Branch 기기 (SBA)는 SBA의 백업 등록자 역할을 하는 프런트 엔드 풀과 연결 됩니다. 프런트 엔드 풀이 Lync Server 2013로 업그레이드 될 때 프런트 엔드 풀을 업그레이드 하는 동안 SBA를 프런트 엔드 풀에서 분리 해야 합니다. 프런트 엔드 풀을 업그레이드 한 후 SBA는 프런트 엔드 풀과 reassociated 될 수 있습니다. 이렇게 하려면 토폴로지 작성기를 사용하여 토폴로지에서 SBA를 삭제한 후 다시 SBA를 토폴로지 작성기에 추가해야 합니다. SBA에서 홈 사용자를 다른 프런트 엔드 풀로 이동한 후 토폴로지에서 해당 SBA를 제거 해야 합니다. SBA를 토폴로지에 다시 추가한 후에는 해당 사용자를 다시 SBA로 이동할 수 있습니다.

이러한 단계는 아래에 요약되어 있습니다.

1.  SBA에 있는 분기 사용자를 다른 프런트 엔드 풀로 이동 합니다.

2.  토폴로지에서 SBA를 제거 하 여 백업 등록자와 기존 프런트 엔드 풀의 연결을 해제 합니다.

3.  프런트 엔드 풀을 Microsoft Lync Server 2013로 업그레이드 합니다.

4.  토폴로지에 다시 SBA를 추가합니다.

5.  새 프런트 엔드 풀을 백업 등록자 인 SBA에 연결 합니다.

6.  분기 사용자를 다시 SBA로 이동합니다.

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013 Sba (survivable Branch 기기 분기 사이트를 토폴로지에 추가](lync-server-2013-add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology.md)

  - [Lync Server 2010 Sba (survivable Branch 기기 분기 사이트를 토폴로지에 추가](lync-server-2013-add-lync-server-2010-survivable-branch-appliance-branch-site-to-your-topology.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

