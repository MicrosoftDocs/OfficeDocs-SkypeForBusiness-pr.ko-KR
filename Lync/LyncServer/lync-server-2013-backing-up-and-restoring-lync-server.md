---
title: 'Lync Server 2013: Lync Server 백업 및 복원'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up and restoring Lync Server 2013
ms:assetid: 07dc1f5e-af66-4e18-bf39-881dceff8bc3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202160(v=OCS.15)
ms:contentKeyID: 51541443
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 43a96f47bfe9d28fdbc37eea0ae62ef6cd763098
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740148"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backing-up-and-restoring-lync-server-2013"></a>Lync Server 2013 백업 및 복원

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-21_

이 섹션에서는 Lync Server 2013 데이터를 백업 하 고 오류가 발생 한 경우 복원 하는 모범 사례를 알아봅니다. 이러한 모범 사례는 다음 상황에 적용 됩니다.

  - 모든 종류의 Lync Server 풀 (프런트 엔드 서버, Edge 서버, 중재 서버, 영구 채팅 서버 또는 디렉터) 또는 이러한 풀 중 하나의 개별 서버

  - 중앙 관리 서버

  - 스탠더드 버전 서버

  - Enterprise Edition 백 엔드 서버

  - 파일 저장소

  - 보관 데이터베이스, 모니터링 데이터베이스 또는 영구 채팅 데이터베이스

이 섹션에는 전체 사이트 복원 또는 대기 사이트 개발에 대 한 정보가 포함 되어 있지 않습니다. 페어링된 프런트 엔드 풀을 사용 하 여 재해 복구 솔루션을 개발 하는 방법에 대 한 자세한 내용은 [Lync Server 2013의 고가용성 및 재해 복구 계획](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)을 참조 하세요. 이 방법은 재난 복구를 계획 하는 데 권장 되는 방법입니다.

페어링된 프런트 엔드 풀을 배포한 경우 이러한 풀 중 하나에 오류가 발생 하 여 복구할 수 없게 되 면 해당 쌍의 풀에서 새 FQDN (정규화 된 도메인 이름)을 사용 하 여이 풀을 복원할 수 있습니다. 이 복구를 수행 하는 단계에 대 한 자세한 내용은 [Lync Server 2013에서 풀 장애](lync-server-2013-failing-over-a-pool.md)조치 (failover)를 참조 하세요. 또한 나중에 프런트 엔드 쌍의 일부인 실패 했거나 복구 불가능 한 풀을 다시 만들려는 경우 [Lync Server 2013에서 ABC 프런트 엔드 풀 장애 조치를 수행](lync-server-2013-performing-an-abc-front-end-pool-failover.md)하는 단계를 사용할 수 있습니다.

이 문서에 설명 된 방법론에는 계획 단계 중에 특별 한 고려 사항이 포함 되어 있습니다. 자세한 내용은 [Lync Server 2013에 대 한 백업 및 복원 계획 수립](lync-server-2013-establishing-a-backup-and-restoration-plan.md)을 참조 하세요.

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013 백업 및 복원 준비](lync-server-2013-preparing-for-lync-server-backup-and-restoration.md)

  - [Lync Server 2013에서 데이터 및 설정 백업](lync-server-2013-backing-up-data-and-settings.md)

  - [Lync Server 2013에서 데이터 및 설정 복원](lync-server-2013-restoring-data-and-settings.md)

  - [Lync Server 2013의 워크시트 백업 및 복원](lync-server-2013-backup-and-restoration-worksheets.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

