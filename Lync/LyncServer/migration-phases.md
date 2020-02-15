---
title: 마이그레이션 단계
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migration phases
ms:assetid: cb7747ba-b872-42ca-ab41-76e3c4e77d06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205336(v=OCS.15)
ms:contentKeyID: 48185642
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 08379ec217cc684ae9b6bc11c44b89a3d642f6df
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030702"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-phases"></a>마이그레이션 단계

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-17_

Lync Server 2013에서는 Lync Server 2013 구성 요소를 포함 하는 네트워크의 사이트를 정의 합니다. 사이트는 단일 LAN(Local Area Network)이나 고속 광섬유 네트워크로 연결된 두 개의 네트워크와 같이 고속, 저지연 네트워크로 견고하게 연결된 컴퓨터 집합입니다.

*프런트 엔드 풀*은 동일하게 구성된 프런트 엔드 서버 집합으로서, 이러한 서버가 함께 작동하여 일반 사용자 그룹에 대한 서비스를 제공합니다. 풀은 사용자에게 확장성 및 장애 조치 기능을 제공합니다. 풀의 각 서버는 동일한 서버 역할을 실행해야 합니다. 소규모 조직을 위해 설계 된 Standard Edition 서버는 풀을 정의 하 고 단일 서버에서 실행 됩니다. 이를 통해 Lync Server 2013 기능을 저렴 한 비용으로 사용할 수 있지만, 진정한 고가용성 솔루션은 제공 되지 않습니다.

다음 단계에서는 Lync Server 2010에서 Lync Server 2013로의 풀 마이그레이션 프로세스에 대해 설명 합니다. 여러 풀을 포함하는 다중 사이트의 경우 각각의 개별 풀에서 이러한 단계별 접근 방식을 따라야 합니다.

1.  [1 단계: Lync Server 2010에서 마이그레이션 계획](phase-1-plan-your-migration-from-lync-server-2010.md)

2.  [2 단계: 마이그레이션 준비](phase-2-prepare-for-migration.md)

3.  [3 단계: Lync Server 2013 파일럿 풀 배포](phase-3-deploy-lync-server-2013-pilot-pool.md)

4.  [4 단계: 테스트 사용자를 파일럿 풀로 이동](phase-4-move-test-users-to-the-pilot-pool.md)

5.  [단계 5: Lync Server 2013에 지 서버를 파일럿 풀에 추가](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

6.  [6 단계: 파일럿 배포에서 프로덕션으로 이동](phase-6-move-from-pilot-deployment-into-production.md)

7.  [단계 7: 마이그레이션 후 작업 완료](phase-7-complete-post-migration-tasks.md)

8.  [8 단계: 레거시 풀 해제](phase-8-decommission-legacy-pools.md)

</div>

<span> </span>

</div>

</div>

</div>

