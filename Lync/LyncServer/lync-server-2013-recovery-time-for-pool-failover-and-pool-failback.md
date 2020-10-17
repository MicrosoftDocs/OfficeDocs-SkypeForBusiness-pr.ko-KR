---
title: 풀 장애 조치 (failover) 및 풀 장애 복구를 위한 Lync Server 2013 복구 시간
description: Lync Server 2013 풀 장애 조치 (failover) 및 풀 장애 복구 (failback)를 위한 복원 시간
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Recovery time for pool failover and pool failback
ms:assetid: 902c658f-8442-4d0d-b3ad-bf795ecd550d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205079(v=OCS.15)
ms:contentKeyID: 48184786
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1bb09c32ac4d062358a511464dc21aa7346ee034
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559174"
---
# <a name="recovery-time-for-pool-failover-and-pool-failback-in-lync-server-2013"></a>Lync Server 2013의 풀 장애 조치 (failover) 및 풀 장애 복구 (failback)

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-10_

풀 장애 조치 (failover) 및 풀 장애 복구 (failback)의 경우, RTO (복구 시간 목표)에 대 한 엔지니어링 대상이 30 분입니다. 관리자가 재해가 발생 했으며 장애 조치 (failover) 절차를 시작한 후에 장애 조치 (failover)를 수행 하는 데 소요 되는 시간입니다. 여기에는 관리자가 상황을 평가 하 고 결정을 내리는 시간이 포함 되지 않으며 장애 조치 (failover)가 완료 된 후 사용자가 다시 로그인 하는 시간도 포함 되지 않습니다.

풀 장애 조치 (failover) 및 풀 장애 복구 (failback)의 경우, RPO (복구 지점 목표)에 대 한 엔지니어링 대상이 30 분입니다. 백업 서비스의 복제 대기 시간으로 인해 재해로 인해 손실 될 수 있는 데이터 측정 시간을 나타냅니다. 예를 들어 풀이 오전 10:00 시에 다운 되 고 RPO가 30 분 후에는 풀에 데이터를 기록 하는 시간: 오전 9:30 및 10:00이 백업 풀로 복제 되지 않아 손실 될 수 있습니다.

이 문서의 모든 RTO 및 RPO 번호는 두 개의 데이터 센터가 같은 세계 지역 내에 있는 것으로 가정 합니다. 이러한 수치는 데이터 복제에 백로그가 없는 미리 정의 된 사용자 모델과 관련 하 여, 4만 동시 활성 사용자 및 20만 사용자가 Lync를 사용할 수 있는 풀에 대해 측정 됩니다. 성능 테스트 및 유효성 검사에 따라 변경 될 수 있습니다.

</div>

<span> </span>

</div>

</div>

</div>

