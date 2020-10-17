---
title: 중재 서버 마이그레이션
description: 중재 서버 마이그레이션
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate Mediation Server
ms:assetid: b0b77121-2c8f-413e-b276-dbf1038361d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205173(v=OCS.15)
ms:contentKeyID: 48185117
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31cc4c95f0e9c86b48594238218db22f3ec1a387
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570334"
---
# <a name="migrate-mediation-server"></a>중재 서버 마이그레이션

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-28_

병합 마법사를 실행 하면 중재 서버가 Lync Server 2013 파일럿 토폴로지에 병합 됩니다. 그러나 Office Communications Server 2007 R2 풀이 Lync Server 2013 중재 서버와 통신할 수 없으므로 모든 사용자가 마이그레이션된 후에 Lync Server 2013 중재 서버를 구성 합니다. 병렬 마이그레이션 중에 Lync Server 2013 풀은 Office Communications Server 2007 R2 중재 서버와 통신 합니다.

Lync Server 2013 중재 서버를 구성할 때는 Office Communications Server 2007 R2 게이트웨이도 업그레이드 하거나 교체 해야 합니다. Office Communications Server 2007 R2 게이트웨이는 Lync Server 2013 중재 서버를 지원 하지 않습니다. Lync Server 2013에 대 한 인증을 받은 게이트웨이를 배포 하 고 Lync Server 2013 중재 서버에 연결 해야 합니다. Office Communications Server 2007 R2 배포를 완전히 해제 하려면이 단계를 수행 해야 합니다.

이 섹션의 항목에서는 Lync Server 2013 중재 서버의 마이그레이션을 완료 한 후에 수행 해야 하는 구성 작업에 대해 설명 합니다. 배치 된 중재 서버를 독립 실행형 중재 서버로 전환 하는 것은 선택적 작업입니다.

  - [중재 서버 구성](configure-mediation-server.md)

  - [새 Lync Server 2013 중재 서버를 사용 하도록 음성 경로 변경](change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md)

  - [배치 된 중재 서버를 독립 실행형 중재 서버로 전환 (선택 사항)](transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional.md)

</div>

<span> </span>

</div>

</div>

</div>

