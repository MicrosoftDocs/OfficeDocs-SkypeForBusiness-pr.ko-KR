---
title: 여러 사이트 및 풀 마이그레이션
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrating multiple sites and pools
ms:assetid: a6d726d2-564d-4b39-a97c-5656a673292a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205165(v=OCS.15)
ms:contentKeyID: 48185079
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bee98cdc88a836be8b629d76b5bed57af402a3ca
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756587"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-multiple-sites-and-pools"></a>여러 사이트 및 풀 마이그레이션

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-17_

Lync Server 2013에서는 다중 사이트 및 다중 풀 배포를 지원 합니다. Lync Server 2010에서 Lync Server 2013로 여러 풀을 마이그레이션하는 프로세스를 수행 하려면 다음 사항을 고려해 야 합니다.

1.  Lync Server 2013 파일럿 풀을 배포한 후에는 Lync Server 2013 풀로 이동할 파일럿 사용자의 하위 집합 및 사용자 기능의 유효성 검사 방법론을 정의 해야 합니다. 예를 들어 파일럿 풀로 사용자를 이동한 후에는 사용자의 회의 정책이 Lync Server 2013으로 이동 되었는지 확인 합니다.

2.  파일럿 풀에에 지 서버를 배포한 후에는 외부 사용자가 Lync Server 2013 풀과 통신할 수 있는지 확인 해야 합니다.

3.  Lync Server 2010에 지 서버에서 파일럿 Lync Server 2013에 지 서버로 연결 된 경로를 전환 하 고 나면 페더레이션 사용자가 Lync Server 2013 풀과 통신할 수 있는지 확인 해야 합니다.

4.  모든 사용자와 사용자가 아닌 대화 상대 개체를 이동한 후에는 Lync Server 2010 풀이 비어 있는지 확인 해야 합니다.

5.  Lync Server 2010 풀이 비어 있는지 확인 한 후에는 해당 풀을 비활성화할 수 있습니다.
    
    레거시 Lync Server 2010 풀 및 서버를 비활성화 하는 방법에 대 한 자세한 내용은 [Phase 8: 레거시 풀](phase-8-decommission-legacy-pools.md)해제를 참조 하십시오.

</div>

<span> </span>

</div>

</div>

</div>

