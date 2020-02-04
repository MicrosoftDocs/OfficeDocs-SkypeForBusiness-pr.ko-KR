---
title: 'Lync Server 2013: Lync Server 환경에 대 한 모범 사례'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Best practices for Lync Server environments
ms:assetid: b0e45d84-09c8-4d3e-aad0-bc6f34ce233b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720348(v=OCS.15)
ms:contentKeyID: 63969642
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf207f4cd0303330ccb01dc56e28b949c1df22f9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737558"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-lync-server-2013-environments"></a>Lync Server 2013 환경에 대 한 모범 사례

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-08-04_

다음과 같은 일반적인 원칙은 시스템의 진행 중인 작업에 적용 해야 합니다.

  - **Mof mof를 이해 하 고 활용**   하는 것은 일일 Lync Server 2013 작업과 같은 IT 자산 관리에 대 한 조직 기술 지침을 제공 하는 모범 사례, 원칙 및 모델 모음입니다. 다음 MOF 지침을 참조 하면 Microsoft 제품에 대 한 중요 한 프로덕션 시스템 안정성, 가용성, 지원 가능성 및 관리 효율성을 달성할 수 있습니다. 자세한 내용은 [Microsoft Operations Framework 4.0](http://go.microsoft.com/fwlink/p/?linkid=40939)을 참조 하세요.

  - **Lync server 2013**   모범 사례에 대 한 자세한 정보 lync server 2013를 관리 하는 실용적인 및 입증 된 절차를 구현 하는 것이 좋습니다. 테스트를 사용 하 여 작업을 수행 하면 메서드를 직접 개발 하는 것 보다 더 효율적으로 관리 되는 방법을 사용할 수 있습니다.

  - **매일, 매주, 매월 프로세스**   에 대해 작업을 수행 하면 정기적으로 수행할 필수 작업을 문서로 나눌 수 있습니다. 작업을 수행 하는 방법을 문서화 하면 새 기술이 배포 되거나 직원 변경 사항이 발생 하는 경우와 같이 운영 환경에 변화가 있을 때 정보가 유지 되도록 할 수 있습니다. 작업을 매일, 매주, 매월 수행 하는 관리 작업 부하로 운영 작업을 구분 하는 것이 좋습니다. 일일 작업은 시스템 작동에 집중 되며, 월간 작업은 시스템의 장기간 상태를 보장 하는 데 초점을 둘 것입니다.
    
    이 문서는 기업용 Voice를 사용 하 여 인스턴트 메시징/현재 상태 (IM/P) 구성 요소 또는 IM/P만 배포 하는 환경에서 사용할 수 있습니다. 작업 또는 검사 목록 항목이 엔터프라이즈 음성에만 해당 되는 경우이를 언급 하 고 환경에 엔터프라이즈 음성이 포함 되지 않은 경우 해당 부분을 건너뛸 수 있습니다.

  - **작동 lync server 2013**   에 필요한 도구 배포 여러 도구를 사용 하 여 문제를 해결 하 고, 작업을 자동화 하 고, Lync Server 2013 환경을 모니터링 및 유지 하는 데 도움이 됩니다. 운영 팀에서 수행 하는 작업이 제어 되는 방식으로 정확 하 고 효율적으로 수행 되도록 조직에 대 한 표준 도구 집합을 정의 합니다. 또한 인시던트 및 주요 구성 변경 사항을 추적 하는 프로세스도 구현 해야 합니다.

<div>

## <a name="reference"></a>참조

일반적으로 서버 관리의 기본 사항에 대해 잘 모르는 독자의 혜택을 얻으려면 서버 관리 방법에 대 한 개요를 제공 합니다. 이미 서버 관리에 익숙한 독자는이 구역을 생략 하도록 선택할 수 있습니다.

모범 사례는 IT 전문가가 다양 한 환경에서 얻은 지식과 경험을 기반으로 하는 권장 사항입니다. Lync Server 관리자가 매일 수행 해야 하는 일반적인 작업에 대 한 표준 절차를 제공 하 고 Lync Server 환경을 관리 하는 데 사용할 도구를 나열 합니다.

Lync 관리자의 일반적인 작업에는 다음이 포함 됩니다.

  - **용량 및 가용성 관리**   는 향후 용량 요구 사항을 예측 하 고 시스템의 용량, 안정성 및 가용성에 대해 보고 하는 방법 및 측정 하는 방법을 정의 합니다. Lync Server를 실행 하는 서버는 시스템의 로드를 처리 하도록 크기가 조정 되 고, 계획 되지 않은 가동 중지가 SLA (서비스 수준 계약)에 정의 된 수준으로 유지 되는지 확인 해야 합니다. 또한 정의 된 요구 사항을 계속 충족 하기 위해 하드웨어를 업그레이드 해야 합니다.

  - **변경 관리 및 구성 관리**   IT 시스템에 대 한 변경 사항을 적용 하는 방법을 제어 합니다. 여기에는 테스트, 응용 프로그램 피드백 및 긴급 복구 계획, 모든 변경 내용에 대 한 문서, 문제가 발생 하는 경우 관리의 승인을 포함 해야 합니다. 소프트웨어 및 하드웨어 자산 및 해당 구성을 기록해 둡니다.

  - **시스템 관리**   데이터베이스 관리, 사이트 관리 등의 관리 작업을 수행 하는 표준 방법에 대해 간략하게 설명 합니다.

  - **보안 관리**   에는 IT 인프라의 데이터 기밀성, 데이터 무결성, 데이터 가용성을 보호 하는 상세 정책 및 계획이 있습니다. 여기에는 IT 보안 인프라 유지 관리 및 조정과 관련 된 일상 활동 및 작업이 포함 됩니다.

  - ****   향후 유사한 문제를 방지 하는 단계를 포함 하 여 예기치 않은 문제를 처리 하는 시스템 문제 해결 개요 방법입니다.

  - **서비스 수준 계약은**   IT 시스템의 성능에 대 한 목표 집합을 유지 하 고 이러한 목표에 대 한 성과를 정기적으로 측정 합니다.

  - **설명서**   문서에는 구성 정보 및 교훈 등의 표준 절차가 있으며,이를 필요로 하는 교직원 들이 사용할 수 있도록 합니다. 구성이 변경 되 면 그에 따라 설명서를 업데이트 합니다.

</div>

<div>

## <a name="related-sections"></a>관련 단원

계속 하기 전에 시스템 작업과 관련 하 여 다음 항목을 검토 하세요.

  - [Lync Server 2013의 용량 및 가용성 관리](lync-server-2013-capacity-and-availability-management.md)

  - [Lync Server 2013의 변경 관리](lync-server-2013-change-management.md)

  - [Lync Server 2013의 구성 관리](lync-server-2013-configuration-management.md)

  - [Lync Server 2013의 시스템 관리](lync-server-2013-system-administration.md)

  - [Lync Server 2013의 서비스 수준 계약](lync-server-2013-service-level-agreements.md)

  - [Lync Server 2013의 설명서](lync-server-2013-documentation.md)

  - [Lync Server 2013의 표준 절차](lync-server-2013-standard-procedures.md)

  - [Lync Server 2013의 응급 절차](lync-server-2013-emergency-procedures.md)

</div>

<div>

## <a name="see-also"></a>참고 항목


[Microsoft Operations 프레임 워크 4.0](http://go.microsoft.com/fwlink/p/?linkid=40939)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

