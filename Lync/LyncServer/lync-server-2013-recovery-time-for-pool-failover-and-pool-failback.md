---
title: Lync Server 2013 풀 장애 조치(Failover) 및 풀 장애 복구(Failback)를 위한 복구 시간
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
ms.openlocfilehash: 3fff6f74b5d486c05d01bcd3a911ae674b4f0708
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724456"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="recovery-time-for-pool-failover-and-pool-failback-in-lync-server-2013"></a>Lync Server 2013의 풀 장애 조치(Failover) 및 풀 장애 복구(Failback)를 위한 복구 시간

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-10_

풀 장애 조치 및 풀 장애 복구를 위해 RTO (복구 시간 목표)에 대 한 엔지니어링 대상은 30 분입니다. 관리자가 재난을 확인 하 고 장애 조치 절차를 시작 했을 때 장애 조치를 수행 하는 데 필요한 시간입니다. 관리자가 상황을 평가 하 고 의사 결정을 내리는 시간을 포함 하지 않으며 장애 조치 완료 후 사용자가 다시 로그인 하는 시간도 포함 하지 않습니다.

풀 장애 조치 및 풀 장애 복구를 위해 RPO (복구 시점 목표)에 대 한 엔지니어링 대상은 30 분입니다. 이는 백업 서비스의 복제 지연으로 인해 재해가 발생 하 여 손실 될 수 있는 데이터의 시간 측정값을 나타냅니다. 예를 들어 풀이 오전 10:00 시에 중단 되 고 RPO가 30 분인 후 오전 9:30 시에 풀에 기록 된 데이터 10:00. M .이 (가) 백업 풀에 복제 되지 않았을 수 있으며, 손실 됩니다.

이 문서의 모든 RTO 및 RPO 번호는 두 개의 데이터 센터가 동일한 월드 지역 내에 있으며, 두 사이트 간에 고속, 짧은 지연 전송을 사용 한다고 가정 합니다. 이러한 번호는 데이터 복제에 백로그가 없는 미리 정의 된 사용자 모델에 대해 4만 동시 활성 사용자 및 20만 사용자가 Lync에 대해 사용 하도록 설정 된 풀에 대해 측정 됩니다. 성능 테스트 및 유효성 검사에 따라 변경 될 수 있습니다.

</div>

<span> </span>

</div>

</div>

</div>

