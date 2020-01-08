---
title: 'Lync Server 2013: Lync Server의 상태 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Health configuration in Lync Server 2013
ms:assetid: c00a8c8e-c2d2-4557-8c42-211c7cc96550
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205234(v=OCS.15)
ms:contentKeyID: 48185305
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a719a5e8695dbbd0705aa649d72a32a2bfdc7d38
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985768"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="health-configuration-in-lync-server-2013"></a>Lync Server 2013의 상태 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-22_

다양 한 웹 사이트, Microsoft 기술 자료 문서, Lync Server Resource Kit 도구 사이에서 Lync Server를 실행할 때 문제가 발생 하는 관리자는 이러한 문제를 해결 하는 방법에 대해 크게 알지 못합니다.

예를 들어 lync Server는 네트워크 중단 및 하드웨어 오류 등의 여러 가지 기능에 영향을 받을 수 있으며, 이렇게 하면 제품 자체에서 제어할 수 없기 때문에 Lync Server 2013의 문제가 발생 하지 않는다는 보장이 없습니다 관리자는 상태 모니터링을 구현 하 여 실제 문제로 전환 하기 전에 잠재적인 문제를 확인할 수 있습니다. 예를 들어 관리자는 Lync Server 모니터링을 사용 하 여 추세와 추세을 확인할 수 있습니다. 예를 들어 오디오/비디오 컨퍼런스 수가 일정 하 게 증가 함에 따라서 시스템을 오버 로드 하기 전에 용량을 추가 해야 하는 것이 좋습니다.

비슷한 방식으로, 관리자는 지정 된 이벤트가 발생할 경우 실시간 알림을 표시 하 고 시스템을 사전에 테스트 하는 가상 트랜잭션을 실행 하도록 System Center Operations Manager를 사용할 수 있습니다. Lync Server에서 사용자가 시스템에 로그인 하거나 인스턴트 메시지를 교환 하거나 PSTN (공개 통신 네트워크)에 있는 전화기로 전화 하는 등의 일반적인 작업을 성공적으로 완료할 수 있는지 확인 하기 위해 가상 트랜잭션을 사용 합니다. 예를 들어 이러한 테스트를 정기적으로 실행 하면 Lync Server에 로그온 하는 사용자에 게 잠재적인 문제가 발생할 수 있으며, 지원 팀이 연결을 설정할 수 없는 사용자의 전화 때문에 문제를 해결할 기회가 생깁니다. System Center Operations Manager를 사용 하 여 이러한 가상 트랜잭션을 실행 하면 관리자가 모든 메시지에 응답 하는 것 보다 많은 작업을 수행 하지 않고도 매일 24 시간 동안 지속적으로 Lync Server의 배포를 정기적으로 모니터링할 수 있습니다. 실행할 수 있습니다.

<div>


> [!NOTE]  
> Lync Server 2013의 경우 System Center Operations Manager 용 관리 팩은 Lync Server에 좋지 않은 영향을 줄 수 있는 "외부" 문제를 검색할 수도 있습니다. 예를 들어 관리자는 IIS (인터넷 정보 서비스)가 오프 라인 상태 이거나 Lync Server 컴퓨터의 시스템 리소스가 지정 된 금액 이하로 떨어지면 Lync Server 컴퓨터에 하드웨어 오류가 발생 하는 경우 알림을 받을 수 있습니다.



</div>

Lync Server 2013의 상태 구성은 System Center Operations Manager 및 Lync Server 관리 팩 사용을 기반으로 합니다. 이러한 관리 팩에는 다음과 같은 여러 가지 새로운 기능과 향상 된 기능이 포함 되어 있습니다.

  - **모든 위치의 시나리오 가용성.** Lync Server 2010 관리 팩에는 가상 트랜잭션으로 최종 사용자 시나리오 가용성을 모니터링 하는 개념이 도입 되었습니다. Lync Server 2013에서 이러한 에이전트는 더 많은 가상 트랜잭션을 사용 하며 엔터프라이즈 내의 다양 한 위치, 기업 외부의 원격 지리적 위치, 지사 기기 및 Lync Server 2010에서 실행할 수 있습니다. 레거시 Edge 배포에 적용 범위를 추가 하는 배포

  - **가상 트랜잭션 로그.** 가상 트랜잭션이 실패 하는 경우, 관리자는 HTML 로그에 액세스 하 여 실패 한 내용을 확인 하는 데 도움을 줍니다. 여기에는 실패 한 작업, 각 작업의 대기 시간, 테스트를 실행 하는 데 사용 된 명령줄 및 발생 한 오류에 대 한 이해가 포함 됩니다.

  - **향상 된 통화 안정성 범위.** Lync Server 2010 관리 팩은 호출 안정성 경고를 도입 하 여 최종 사용자의 오디오 통화에 영향을 주는 심각한 연결 문제를 감지 합니다. Lync Server 2013 관리 팩은 피어 투 피어 인스턴트 메시징 (IM) 및 기타 기본 회의 기능에 대 한 적용 범위를 추가 하 여 노이즈를 줄이면서 검사 범위를 최대화 합니다.

  - **종속성 모니터링.** Lync Server 시나리오는 IIS (오프 라인 상태), 제한 된 CPU 및 메모리 리소스, 디스크 문제 등 다양 한 외부 요인으로 인해 실패할 수 있습니다. 새 관리 팩은 관리자가 영향을 인식 하도록 몇 가지 중요 한 종속성을 검사 합니다.

  - **향상 된 보고.** 관리자가 시나리오 가용성을 예측 하 고, 용량을 계획 하 고, 문제가 발생 하는 구성 요소를 확인 하는 데 도움이 되는 보고서 집합입니다.

관리 팩에는 Lync Server 배포 상태에 대 한 실시간 가시성을 감지 하 고 진단 하는 데 도움이 되는 다양 한 기능이 포함 되어 있습니다. 이러한 기능은 다음 표에 나열 되어 있습니다.

### <a name="management-pack-features"></a>관리 팩 기능

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>기능</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>가상 트랜잭션</p></td>
<td><p>다양 한 위치에서 실행할 수 있는 Windows PowerShell cmdlet을 사용 하 여 로그인, 현재 상태, 메신저 대화, 회의 등의 최종 사용자 시나리오가 최종 사용자에 게 즉시 제공 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>호출 안정성 알림</p></td>
<td><p>CDR (통화 정보 레코드)에 대 한 데이터베이스 쿼리 이 레코드는 최종 사용자가 통화에 연결할 수 있는지 여부 또는 통화가 종료 된 이유를 반영 하도록 프런트 엔드 서버에서 기록 됩니다. 이러한 쿼리는 다양 한 최종 사용자가 피어 투 피어 통화 또는 기본 회의 기능에 대 한 연결 문제가 발생 하는 경우를 나타내는 경고를 생성 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>미디어 품질 알림</p></td>
<td><p>각 호출이 끝날 때 클라이언트가 게시 한 체감 품질 (환경 품질) 보고서를 보고 하는 데이터베이스 쿼리 이러한 쿼리는 사용자가 통화와 회의 중에 잘못 된 미디어 품질을 발생 시킬 수 있는 시나리오를 정확 하 게 알려 주는 경고를 생성 합니다. 이 데이터는 패킷 대기 시간, 손실, 통화 음질에 직접 참가 하는 것으로 알려진 메트릭과 같은 주요 메트릭에 따라 작성 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>구성 요소 상태</p></td>
<td><p>개별 서버 구성 요소는 이벤트 로그 및 성능 카운터를 사용 하 여 알림을 발생 시킵니다. 이러한 경고는 하나 이상의 최종 사용자 시나리오에 심각한 영향을 줄 수 있는 오류 조건을 나타냅니다. 이러한 알림은 실행 되지 않는 서비스, 높은 오류율 속도, 높은 메시지 대기 시간 또는 연결 문제를 포함 하 여 다양 한 오류 조건을 표시할 수도 있습니다.</p></td>
</tr>
<tr class="odd">
<td><p>종속성 상태</p></td>
<td><p>다양 한 외부 이유로 실패가 발생할 수 있습니다. 이제 관리 팩은 IIS 가용성, 서버와 프로세스의 CPU 및 메모리 사용, 디스크 메트릭의 등 심각한 문제를 나타내는 중요 한 외부 종속성에 대 한 데이터를 모니터링 하 고 수집 합니다.</p></td>
</tr>
</tbody>
</table>


시스템에서 발급 하는 알림은 다음과 같은 세 가지 일반 범주로 분류 되어 있습니다.

  - **우선 순위가 높은 알림** 이러한 알림은 대규모 사용자 그룹에 대 한 서비스 중단을 발생 시키는 조건을 나타냅니다. 예를 들어 Lync Server 2013에는 고가용성 기능이 기본적으로 제공 되므로 단일 컴퓨터의 구성 요소 오류는 우선 순위가 높은 알림이 아닙니다. 그 대신 우선 순위가 높은 알림은 "야간 모드의 관리자를 종료 하는 데 매우 심각한" 문제를 표시 합니다. 통합 된 트랜잭션 및 오프 라인 서비스 (예: 오디오/비디오 회의)가 중단 하는 경우 우선 순위가 높은 알림으로 인식 됩니다.

  - **보통 우선 순위의 알림.** 이러한 알림은 사용자의 하위 집합에 영향을 주거나 통화 품질 저하를 표시 하는 조건을 나타냅니다. 여기에는 구성 요소 오류, 통화 대기 시간 설정, 통화 중 저하 된 오디오 음질 등의 문제가 포함 됩니다. 이 범주의 알림은 상태를 저장 하 고 문제의 현재 상태를 나타냅니다. 예를 들어 통화 성립 시간이 알림 임계값을 초과 한다고 가정 합니다. 통화 설정 시간이 일반으로 반환 되는 경우 System Center Operations Manager에서 이러한 알림이 자동으로 해결 됩니다. 이러한 알림은 관리자가 같은 영업일에 확인할 수 있습니다.

  - **다른 알림.** 이는 특정 사용자 또는 사용자의 하위 집합에 영향을 줄 수 있는 구성 요소의 알림입니다. 예를 들어 주소록 서비스에서 지정 된 사용자의 Active Directory 항목을 구문 분석할 수 없는 경우가 있습니다. 이러한 알림은 관리자가 사용할 수 있는 시간에 도달 하는 것이 가장 좋습니다.

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013에서 System Center Operations Manager와 작동 하도록 구성](lync-server-2013-configuring-lync-server-to-work-with-system-center-operations-manager.md)

  - [Lync Server 2013에서 종합 거래에 대 한 풍부한 로깅 사용](lync-server-2013-using-rich-logging-for-synthetic-transactions.md)

  - [Lync Server 2013의 System Center Operations Manager 데이터베이스로 Microsoft SQL Server 2008 R2를 사용 하는 경우](lync-server-2013-using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

