---
title: 'Lync Server 2013: 백 엔드 서버 고가용성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Back End Server high availability
ms:assetid: c559aacb-4e1d-4e78-9582-41f966ad418d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205248(v=OCS.15)
ms:contentKeyID: 48185358
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5708212aa2eb30cfcc3c3d40894ca2340475bd8b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740138"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="back-end-server-high-availability-in-lync-server-2013"></a>백 엔드 서버의 Lync Server 2013에서 높은 가용성을 제공 합니다.

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-08-12_

백 엔드 서버의 가용성을 높이기 위해 동기 SQL 미러링 또는 SQL 클러스터링을 사용할 수 있습니다. 이러한 솔루션 중 하나를 선택 하는 것이 좋지만 조직의 비즈니스 연속성을 유지 관리 하는 것이 좋습니다. Lync Server 2013에서 백 엔드 서버 가용성을 높일 수 있는 비동기 SQL 미러링이 지원 되지 않습니다. 이 문서의 나머지 부분에서 SQL 미러링은 명시적으로 명시 되지 않는 한 동기 SQL 미러링을 의미 합니다.

토폴로지 작성기를 사용 하 여 SQL 미러링을 쉽게 설정할 수 있습니다. SQL 장애 조치(failover) 클러스터링의 경우 설정을 위해 SQL Server를 사용해야 합니다.

재해 복구를 위해 다른 프런트 엔드 풀과 쌍을 이루는 풀에서 SQL 미러링 또는 SQL 클러스터링을 사용 하는 경우 두 풀에서 동일한 백 엔드 고가용성 솔루션을 사용 해야 합니다. Sql 미러를 사용 하 여 풀을 연결 하는 경우에만 SQL 클러스터링을 사용할 수 있습니다.

SQL 미러링을 배포 하는 경우 중앙 관리 저장소를 포함 하 여 해당 풀에 있는 모든 Lync Server 데이터베이스가 미러링 되며 응답 그룹 응용 프로그램 데이터베이스 및 통화 공원 응용 프로그램 데이터베이스 풀에서 실행 되 고 있습니다.

SQL 미러링에서는 서버에 공유 저장소를 사용할 필요가 없습니다. 각 서버는 로컬 저장소에 데이터베이스 복사본을 유지 합니다.

미러링 모니터 서버와 함께 SQL 미러링을 배포 하도록 선택할 수 있습니다. 미러링 모니터 서버를 사용 하 여 백 엔드 서버의 장애 조치를 자동으로 수행할 수 있도록 하는 것이 좋습니다. 그렇지 않으면 관리자가 장애 조치를 수동으로 호출 해야 합니다. 미러링 모니터 서버가 배포 된 경우에도 관리자는 필요한 경우 백 엔드 서버 장애 조치를 수동으로 호출할 수 있습니다.

미러링 모니터 서버를 사용 하는 경우 백 엔드 서버의 여러 쌍에 단일 미러링 모니터를 사용할 수 있습니다. 백 엔드 서버와 witnesses의 짝이 엄격한 1:1 대응 기능은 없습니다. 여러 백 엔드 서버 쌍에 단일 미러링 모니터를 사용 하는 배포는 각 백 엔드 서버 쌍에 대해 별도의 감시가 있는 토폴로지로 탄력적으로 복구 되지 않습니다.

SQL 클러스터링 지원에 대 한 자세한 내용은 [Lync Server 2013의 데이터베이스 소프트웨어 지원을](lync-server-2013-database-software-support.md)참조 하세요. SQL 클러스터링을 배포 하는 방법에 대 한 자세한 내용은 [Lync server 2013에 대 한 Sql Server 클러스터링 구성을](lync-server-2013-configure-sql-server-clustering.md)참조 하세요.

<div>

## <a name="recovery-time-for-automatic-back-end-server-failover-with-sql-mirroring"></a>SQL 미러링으로 자동 백 엔드 서버 장애 조치 복구 시간

SQL 미러링의 자동 백 엔드 장애 조치의 경우, RTO (복구 시간 목표)에 대 한 엔지니어링 대상이 5 분입니다. 동기 SQL 미러링 때문에, 서버 간에 데이터를 이동 하는 동안 프런트 엔드 서버와 백 엔드 서버가 동시에 종료 되는 경우를 제외 하 고는 백 엔드 서버 오류 시 데이터 손실이 예상 되지 않습니다. RPO (복구 시점 목표)에 대 한 엔지니어링 대상은 5 분입니다.

</div>

<div>

## <a name="user-experience-during-back-end-server-failure-with-sql-mirroring"></a>SQL 미러링과 함께 백 엔드 서버 오류 발생 시 사용자 환경

오류 발생 시 사용자 환경은 오류의 성격 및 토폴로지에 따라 달라 집니다.

SQL 미러링을 사용 하 고 미러링 모니터 서버가 구성 되어 있는 경우 주 서버가 실패 하면 백 엔드 서버 장애 조치는 자동으로 신속 하 게 처리 됩니다. 활성 사용자는 진행 중인 세션을 크게 중단 하지 않아야 합니다.

미러링 모니터가 구성 되어 있지 않은 경우 관리자가 장애 조치를 수동으로 호출 하는 데 시간이 걸릴 수 있습니다. 이 기간 동안에는 활성 사용자에 게 영향을 줄 수 있습니다. 약 30 분 동안에는 세션을 계속 합니다. 기본 상태가 복원 되지 않거나 관리자가 백업으로 장애 조치 되지 않으면 사용자가 복원 모드로 전환 되어 Lync Server (예: 대화 상대 추가)에 영구적으로 변경 해야 하는 작업을 수행할 수 없습니다.

주 서버와 미러 백 엔드 서버가 둘 다 실패 하거나 이러한 서버와 미러링 모니터 서버가 실패 한 경우 백 엔드 서버를 사용할 수 없게 됩니다 (아직 작동 중인 주에 포함). 이 경우 활성 사용자는 잠시 후에 복원 모드로 전환 됩니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

