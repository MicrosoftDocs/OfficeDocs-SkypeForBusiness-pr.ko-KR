---
title: 'Lync Server 2013: Lync Server의 상태 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Health configuration in Lync Server 2013
ms:assetid: c00a8c8e-c2d2-4557-8c42-211c7cc96550
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205234(v=OCS.15)
ms:contentKeyID: 48185305
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 831dd021799f658ae9ce332935ff2381e5d79bef
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030281"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="health-configuration-in-lync-server-2013"></a>Lync Server 2013의 상태 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-22_

다양 한 웹 사이트, Microsoft 기술 자료 문서 및 Lync Server Resource Kit 도구 간에 Lync Server 실행 시 문제가 발생 하는 관리자는 이러한 문제를 해결 하는 방법에 대해 어느 정도 되지 않습니다.

예를 들어 Lync Server는 네트워크 중단 및 하드웨어 오류와 같이 제품 자체에서 제어할 수 없는 여러 가지 요인의 영향을 받을 수 있기 때문에 Lync Server 2013에 문제가 발생 하지 않도록 보장할 수 없습니다. 관리자는 상태 모니터링을 구현 하 여 실제 문제가 발생 하기 전에 잠재적 문제를 파악할 수 있습니다. 예를 들어 관리자는 Lync Server 모니터링을 사용 하 여 경향 및 tendencies를 파악할 수 있습니다. 예를 들어 오디오/비디오 회의 수를 일정 하 게 높이면 시스템을 과부하 하기 전에 용량을 추가 해야 할 수도 있습니다.

비슷한 방식으로 관리자는 System Center Operations Manager를 사용 하 여 지정 된 이벤트가 발생 하는 경우 실시간 경고를 표시 하 고 시스템을 사전에 테스트 하는 가상 트랜잭션을 실행할 수 있습니다. Lync Server에서는 가상 트랜잭션을 사용 하 여 사용자가 시스템에 로그온 하거나, 인스턴트 메시지를 교환 하거나, PSTN (공중 전화망)에 있는 전화기를 호출 하는 등의 일반적인 작업을 성공적으로 완료할 수 있는지 확인 합니다. 예를 들어 이러한 테스트를 주기적으로 실행 하면 Lync Server에 로그온 하는 사용자에 게 잠재적 문제가 발생 하는 것을 알릴 수 있으며, 지원 팀이 사용자의 전화를 통해 연결을 설정할 수 없게 되기 전에 문제를 해결할 수도 있습니다. System Center Operations Manager를 사용 하 여 이러한 가상 트랜잭션을 실행 함으로써 관리자는 매일 24 시간 동안 Lync Server의 배포를 주기적으로 모니터링할 수 있습니다. 실행 해야 합니다.

<div>


> [!NOTE]  
> Lync Server 2013의 경우 System Center Operations Manager 용 관리 팩은 Lync Server에 악영향을 줄 수 있는 "외부" 문제를 검색할 수도 있습니다. 예를 들어 IIS (인터넷 정보 서비스)가 오프 라인 상태가 되거나 Lync Server 컴퓨터의 시스템 리소스가 지정 된 크기 보다 크거나 Lync Server 컴퓨터에 하드웨어 오류가 발생 하는 경우 관리자에 게 알림을 보낼 수 있습니다.



</div>

Lync Server 2013의 상태 구성은 System Center Operations Manager와 Lync Server 관리 팩 사용을 기반으로 합니다. 이러한 관리 팩에는 다음과 같은 여러 가지 새로운 기능과 향상된 기능이 포함되어 있습니다.

  - **모든 위치의 시나리오 가용성.** Lync Server 2010 관리 팩에는 가상 트랜잭션으로 최종 사용자 시나리오 가용성을 모니터링 하는 개념이 도입 되었습니다. Lync Server 2013에서 이러한 에이전트에는 더 많은 가상 트랜잭션이 포함 되며, 지점 사무소 및 Lync Server 2010에 대해 기업 외부의 원격 지리적 위치에서 실행 될 수 있습니다. 레거시에 지 배포에 대 한 검사를 추가 하기 위한 배포

  - **가상 트랜잭션 로그** 가상 트랜잭션이 실패 하면 오류를 확인 하는 데 도움이 되도록 관리자가 HTML 로그에 액세스할 수 있습니다. 여기에는 실패 한 작업, 각 작업의 대기 시간, 테스트를 실행 하는 데 사용한 명령줄 및 발생 한 오류에 대 한 이해가 포함 됩니다.

  - **통화 안정성 모니터링 범위 증가.** Lync Server 2010 관리 팩은 호출 안정성 경고를 도입 하 여 최종 사용자의 오디오 통화에 영향을 주는 심각한 연결 문제를 감지 합니다. Lync Server 2013 관리 팩은 피어 투 피어 IM (인스턴트 메시징) 및 기타 기본 회의 기능에 대 한 범위를 추가 하 여 노이즈를 줄이면서 검사 범위를 최대화 합니다.

  - **의존 관계 모니터링.** Lync Server 시나리오는 IIS와 같은 다양 한 외부 요인, CPU 및 메모리 리소스 및 디스크 문제로 인해 실패할 수 있습니다. 새로운 관리 팩은 여러 가지 중요한 의존 관계를 확인하여 관리자가 이러한 외부 요인의 영향을 인식할 수 있도록 합니다.

  - **향상된 보고.** 일련의 보고서를 통해 관리자가 시나리오 가용성을 예측하고 용량을 계획하며 문제가 가장 많이 발생하는 구성 요소를 확인할 수 있습니다.

또한 관리 팩에는 Lync Server 배포 상태를 감지 하 고 진단 하는 데 도움이 되는 다양 한 기능이 포함 되어 있습니다. 다음 표에는 이러한 기능이 나열되어 있습니다.

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
<td><p>다양 한 위치에서 실행 될 수 있는 Windows PowerShell cmdlet을 사용 하 여 최종 사용자가 로그인, 현재 상태, IM 및 회의와 같은 최종 사용자 시나리오를 즉시 사용할 수도 있는지 확인 합니다.</p></td>
</tr>
<tr class="even">
<td><p>통화 안정성 알림</p></td>
<td><p>CDR(통화 정보 레코드)에 대한 데이터베이스 쿼리를 실행합니다. 이 레코드는 최종 사용자가 통화에 연결할 수 있는지 또는 통화가 종료 된 이유를 반영 하도록 프런트 엔드 서버에서 작성 됩니다. 이러한 쿼리를 통해 광범위한 최종 사용자가 피어 투 피어 통화 또는 기본적인 전화 회의 기능에 대한 연결 문제를 경험한 때를 나타내는 알림이 생성됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>미디어 품질 알림</p></td>
<td><p>각 통화가 끝날 때 클라이언트에서 게시한 QoE(체감 품질) 보고서를 보도록 데이터베이스 쿼리를 실행합니다. 이러한 쿼리를 통해 사용자가 통화 및 전화 회의 중 불량 미디어 품질을 경험한 시나리오를 정확하게 나타내는 알림이 생성됩니다. 이러한 데이터는 통화 품질에 직접적인 영향을 미치는 것으로 알려진 패킷 대기 시간 및 손실과 같은 핵심 메트릭을 기반으로 합니다.</p></td>
</tr>
<tr class="even">
<td><p>구성 요소 상태</p></td>
<td><p>개별 서버 구성 요소에서 이벤트 로그와 성능 카운터를 사용하여 알림을 생성합니다. 이러한 알림은 하나 이상의 최종 사용자 시나리오에 심각한 영향을 미칠 수 있는 오류 상태를 나타냅니다. 또한 이러한 알림은 서비스 실행 안 됨, 높은 오류율, 높은 메시지 대기 시간, 연결 문제 등의 다양한 기타 오류 상태를 나타낼 수 있습니다.</p></td>
</tr>
<tr class="odd">
<td><p>의존 관계 상태</p></td>
<td><p>오류는 다양한 외부 요인으로 인해 발생할 수 있습니다. 관리 팩은 이제 IIS 가용성, 서버와 프로세스의 CPU 및 메모리 사용량, 디스크 메트릭을 비롯한 심각한 문제를 나타낼 수 있는 중요한 외부 의존 관계에 대한 데이터를 모니터링하고 수집합니다.</p></td>
</tr>
</tbody>
</table>


시스템에서 생성되는 알림은 크게 세 가지 범주로 분류됩니다.

  - **높은 우선 순위 알림.** 이러한 알림은 대규모 사용자 그룹에 대한 서비스 중단을 야기하는 상태를 나타냅니다. 예를 들어 Lync Server 2013에는 고가용성 기능이 기본적으로 제공 되므로 단일 컴퓨터의 구성 요소 오류는 우선 순위가 높은 경고가 아닙니다. 높은 우선 순위 알림은 "밤에 관리자를 깨울" 만큼 심각한 문제를 나타냅니다. 가상 트랜잭션을 통해 감지된 중단과 서비스(오디오/비디오 회의) 오프라인 상태는 높은 우선 순위 알림으로 처리됩니다.

  - **보통 우선 순위 알림.** 이러한 경고는 사용자 하위 집합에 영향을 주거나 통화 품질 저하를 나타내는 조건을 나타냅니다. 여기에는 구성 요소 오류, 통화 설정의 대기 시간 또는 통화에 저하 된 오디오 품질 등의 문제가 포함 됩니다. 이 범주의 경고는 상태 저장 이며 문제의 현재 상태를 나타냅니다. 예를 들어 통화 설정 시간이 경고 임계값을 초과 하는 경우를 가정해 보겠습니다. 통화 설정 시간이 보통으로 돌아가면 이러한 경고는 System Center Operations Manager에서 자동으로 확인 됩니다. 이러한 경고는 관리자가 당일에 확인 합니다.

  - **기타 알림.** 특정 사용자 또는 일부 사용자에게 영향을 미칠 수 있는 알림입니다. 예를 들어 주소록 서비스가 특정 사용자의 Active Directory 항목을 구문 분석할 수 없는 경우 생성되는 알림이 이 범주에 해당합니다. 이러한 알림은 관리자가 시간이 있을 때 확인하면 됩니다.

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [System Center Operations Manager에서 작동 하도록 Lync Server 2013 구성](lync-server-2013-configuring-lync-server-to-work-with-system-center-operations-manager.md)

  - [Lync Server 2013에서 가상 트랜잭션에 대 한 리치 로깅 사용](lync-server-2013-using-rich-logging-for-synthetic-transactions.md)

  - [Lync Server 2013에 Microsoft SQL Server 2008 R2를 System Center Operations Manager 데이터베이스로 사용](lync-server-2013-using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

