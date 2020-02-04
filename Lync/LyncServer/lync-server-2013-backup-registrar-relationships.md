---
title: Lync Server 2013 백업 등록자 관계
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup Registrar relationships
ms:assetid: 7e078271-84b9-4666-989c-c4507a0cdf4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205033(v=OCS.15)
ms:contentKeyID: 48184631
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44111dbdec945e525b1ef54d910e1cf7f3b5a5d0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730348"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-registrar-relationships-in-lync-server-2013"></a>Lync Server 2013의 백업 등록자 관계

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-06-28_

재해 복구 기능을 제공 하는 것 외에도 쌍을 두 번 연결 하는 풀은 서로에 대 한 백업 등록 기관 역할을 합니다. Lync Server 2013에서는 프런트 엔드 풀 간의 등록자에 대 한 백업본이 항상 1:1 and 상호 관계입니다. 즉, P1이 P2에 대 한 백업이 면 P2는 P1에 대 한 백업 이어야 하며 다른 프런트 엔드 풀에 대 한 백업만 가능 하지 않습니다. 이는 프런트 엔드 풀의 백업 관계가 다를 수 있는 Lync Server 2010의 변경 사항입니다.

두 프런트 엔드 풀 간의 백업 관계는 1:1 및 대칭 이어야 하지만, Lync Server 2010 에서처럼 각 프런트 엔드 풀은 여러 Survivable 분기 기기에 대 한 백업 등록 기관 일 수도 있습니다.

Lync Server 2013는 Survivable Branch 기기에 속한 사용자에 게 재해 복구 지원을 확장 하지 않습니다. Survivable Branch 기기에 대 한 백업 역할을 하는 프런트 엔드 풀이 다운 되 면 Survivable Branch 기기에 로그인 한 사용자는 프런트 엔드 풀에 속한 사용자가 백업 프런트 엔드 풀로 장애 조치 된 후에도 복원 모드로 전환 됩니다.

</div>

<span> </span>

</div>

</div>

</div>

