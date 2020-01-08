---
title: 'Lync Server 2013: 백업 및 복원 모범 사례'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Best practices for backup and restoration
ms:assetid: abbce0e4-973a-4624-a0c1-e0f22e1d348b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202184(v=OCS.15)
ms:contentKeyID: 51541500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4fc7a926bd8fd5c61f87d5e8252c30f40e5a6a69
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984362"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-backup-and-restoration-for-lync-server-2013"></a>Lync Server 2013의 백업 및 복원 모범 사례

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-21_

이 섹션에는 두 가지 모범 사례 유형이 포함 되어 있습니다.

  - 백업 및 복원 모범 사례

  - 재해가 발생 한 영향을 최소화 하는 모범 사례입니다.

<div>

## <a name="best-practices-for-backup-and-restoration"></a>백업 및 복원 모범 사례

백업 및 복원 프로세스를 용이 하 게 하려면 데이터를 백업 하거나 복원할 때 다음과 같은 모범 사례를 적용 하세요.

  - 적절 한 간격으로 정기적인 백업을 수행 합니다. 가장 간단 하 고 자주 사용 하는 백업 유형 및 회전 일정은 전체 SQL Server 데이터베이스의 전체 야간 백업입니다. 그런 다음 복원이 필요한 경우 복원 프로세스에는 하나의 백업만 필요 하며 일일 데이터만 손실 되어서는 안 됩니다.

  - Cmdlet 또는 Lync Server 제어판을 사용 하 여 구성을 변경 하는 경우에는 **내보내기-csconfiguration** cmdlet을 사용 하 여 변경 후 토폴로지 구성 파일 (Xds)의 스냅숏 백업을 수행 하 여 데이터베이스를 복원 해야 하는 경우 변경 내용이 손실 되지 않도록 합니다. 이 구성은 XML 형식으로 백업 되며 ZIP 파일로 압축 됩니다.

  - Lync Server를 백업 하는 데 사용할 공유 폴더에 백업 된 모든 데이터를 저장할 충분 한 디스크 공간이 있는지 확인 합니다.

  - Lync Server 사용이 일반적으로 낮을 때 백업을 예약 하 여 서버 성능 및 사용자 환경을 개선 합니다.

  - 데이터를 백업 하는 위치가 안전한 지 확인 합니다 (원격 위치 권장).

  - 데이터를 복원 해야 하는 경우 백업 파일을 사용할 수 있는 위치에 유지 합니다.

  - 조직에서 지 원하는 복원 프로세스의 주기적인 테스트를 계획 하 고 예약 합니다.

  - 백업 및 복원 프로세스를 미리 확인 하 여 예상 대로 작동 하는지 확인 합니다.

</div>

<div>

## <a name="best-practices-for-minimizing-the-impact-of-a-disaster"></a>재해의 영향을 최소화 하는 모범 사례

정전 또는 갑작스런 하드웨어 오류와 같은 관리 되지 않는 이벤트로 인해 발생 하는 치명적인 서비스 중단을 처리 하는 가장 좋은 전략은 이러한 문제가 발생 하는 것으로 가정 하 고 적절 하 게 계획 하는 것입니다.

최소한의 중단 및 중단을 포함 한 Lync services가 조직에 중요 한 역할을 하는 경우에는 [Lync Server 2013의 고가용성 및 재해 복구 계획](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)에서 설명한 대로 프런트 엔드 서버의 연결 된 풀을 구현 하는 것이 좋습니다. 그런 다음 이러한 풀 중 하나에 재해가 발생 한 경우 관리자는 최소 가동 중지 시간으로 해당 풀의 사용자를 다른 풀에서 제공 하도록 전환할 수 있습니다.

백업 및 복원 전략의 일부로 개발 하는 재해 관리 계획에는 다음이 포함 되어야 합니다.

  - 소프트웨어 미디어 및 소프트웨어와 펌웨어 업데이트를 즉시 사용할 수 있도록 유지 합니다.

  - 하드웨어 및 소프트웨어 기록 유지 관리.

  - 정기적으로 데이터를 백업 하 고 백업의 무결성을 모니터링 합니다.

  - 재난 복구, 절차 문서화, 재해 복구 시뮬레이션 연습 구현에서 직원 교육

  - 여분의 하드웨어를 사용할 수 있도록 유지 하거나 SLA (서비스 수준 계약)가 있는 경우에는 프롬프트 대체를 위해 하드웨어 공급 업체 및 공급 업체와 계약을 체결 합니다.

  - 트랜잭션 로그 파일 (.ldf 파일) 및 데이터베이스 파일 (.mdf 파일)의 위치를 구분 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

