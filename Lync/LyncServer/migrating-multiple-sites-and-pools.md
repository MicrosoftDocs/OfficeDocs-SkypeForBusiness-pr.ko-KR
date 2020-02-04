---
title: 여러 사이트 및 풀 마이그레이션
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating multiple sites and pools
ms:assetid: a6d726d2-564d-4b39-a97c-5656a673292a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205165(v=OCS.15)
ms:contentKeyID: 48185079
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b2f01303c7fe137253d8e993edb05e9562d963ff
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765256"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-multiple-sites-and-pools"></a>여러 사이트 및 풀 마이그레이션

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-17_

Lync Server 2013는 다중 사이트 및 다중 풀 배포를 지원 합니다. Lync Server 2010에서 Lync Server 2013로 여러 풀을 마이그레이션하는 과정에는 다음 고려 사항이 필요 합니다.

1.  Lync Server 2013 파일럿 풀을 배포한 후에는 Lync Server 2013 풀로 이동할 파일럿 사용자의 하위 집합을 정의 하 고 사용자의 기능을 확인 하기 위한 방법론을 지정 해야 합니다. 예를 들어 파일럿 풀로 사용자를 이동한 후 사용자의 컨퍼런스 정책이 Lync Server 2013로 이동 되었는지 확인 합니다.

2.  파일럿 풀에 Edge 서버를 배포한 후에는 외부 사용자가 Lync Server 2013 풀과 통신할 수 있는지 확인 해야 합니다.

3.  Lync Server 2010 Edge 서버에서 파일럿 Lync Server 2013 Edge 서버로 연결 된 경로를 전환 하 고 나면 페더레이션 사용자가 Lync Server 2013 풀과 통신할 수 있는지 확인 해야 합니다.

4.  모든 사용자 및 사용자가 아닌 연락처 개체를 이동한 후에는 Lync Server 2010 풀이 비어 있는지 확인 해야 합니다.

5.  Lync Server 2010 풀이 비어 있는지 확인 한 후에는 풀을 비활성화할 수 있습니다.
    
    레거시 Lync Server 2010 풀 및 서버를 비활성화 하는 방법에 대 한 자세한 내용은 [8 단계: 레거시 풀 서비스](phase-8-decommission-legacy-pools.md)해제를 참조 하세요.

</div>

<span> </span>

</div>

</div>

</div>

