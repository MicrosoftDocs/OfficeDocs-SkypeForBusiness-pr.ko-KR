---
title: 상태 및 사용 현황 보고서
author: altsou
ms.author: altsou
manager: serdars
ms.date: 04/07/2022
ms.reviewer: altsou
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_MTRP
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 보고서 상태 및 사용량에 대한 노드 데이터 보고
f1keywords: ''
ms.openlocfilehash: 9b1f3e1960cbe0089f498045922125b121679646
ms.sourcegitcommit: 64c01699022b47fdfec8dc6e2ca279e57eae3baa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/30/2022
ms.locfileid: "68243799"
---
# <a name="health-and-usage-reports"></a>상태 및 사용 현황 보고서

보고 노드에는 Pro 관리 포털에서 Microsoft Teams 룸 상태 및 사용에 대한 데이터가 포함됩니다. **개요** 는 회의실의 테넌트 전체 상태 추세를 보여 줍니다. **상태** 탭에는 해당 상태 데이터가 있는 회의실 목록이 표시됩니다. 일정 정보 및 통화 품질 데이터를 기반으로 하는 회의실 사용량은 **사용 탭** 아래에 표시됩니다.

## <a name="navigating-reports"></a>보고서 탐색

<!--![A screenshot of active tickets bar graph](../media/health-and-usage-002new.png)-->

개요 섹션에서는 회의실 관리의 중요한 측면에 대한 그래픽 표현을 제공합니다. 선택한 시간 범위 또는 선택한 그룹에 따라 차트가 변경됩니다. 시간 범위를 변경하려면 드롭다운 메뉴를 클릭합니다.

<!--!![A screenshot of a menu to choose a day](../media/health-and-usage-004.png)-->

그룹을 변경하려면 배너에서 그룹 선택 드롭다운 메뉴를 클릭합니다.

<!--!![A screenshot of the banner menu auto-generated](../media/health-and-usage-005.png)-->
### <a name="tickets-by-category"></a>범주별 티켓

도넛은 선택한 시간 범위 및 그룹에 대해 발생한 총 티켓을 표시합니다(기본값은 7일, 모든 그룹). 티켓은 오디오, 디스플레이, 주변 장치, 연결, 버전 관리 및 기록된 문제 등 주요 범주로 표시됩니다.

<!--!![A screenshot of pie chart tickets by category](../media/health-and-usage-006.png)-->

선택한 경우 해당 범주의 티켓에 대한 자세한 보기에 대한 플라이아웃이 표시됩니다.

<!--!![A screenshot of tickets and versioning side by side](../media/health-and-usage-007.png)-->

플라이아웃에서 도넛의 각 부분을 선택하여 하위 범주별로 티켓 목록을 필터링할 수 있습니다. 

<!--!![A screenshot tickets by subcategory automatically generated](../media/health-and-usage-008.png)-->

뒤로 이동하려면 도넛을 클릭하거나 왼쪽 상단의 이동 경로를 클릭합니다.

이 목록 보기에서 특정 티켓으로 이동하려면 **지원 티켓 열** 아래의 링크를 클릭합니다.

<!--### Ticket history

The ticket history graph shows a comparison of incidents assigned to you or Microsoft over the specified time period.

> [!NOTE]
> If a ticket changes owner in a day, whoever owns the assignment for the majority of that day will have the ticket counted towards them. For example, if you assign the ticket to Microsoft early in the day, the ticket counts towards **Assigned to Microsoft** for the day.

<!--![A screen shot of Tickets history by different periods](../media/health-and-usage-009.png)-->

### <a name="health-history"></a>상태 기록

이 그래프는 테넌트의 모든 회의실에 대한 평균 상태(상태 섹션의 정의)와 모든 MTR Pro 고객의 평균 상태를 매일 보여 줍니다. 최대 90일 동안의 평균 상태를 볼 수 있습니다.

<!--!![A screenshot of rooms health and average health](../media/health-and-usage-010.png)-->

### <a name="most-reliableleast-reliable-rooms"></a>가장 신뢰할 수 있는/가장 신뢰할 수 없는 회의실

두 개의 테이블은 상태에 따라 가장 안정적이고 가장 신뢰할 수 있는 회의실을 보여 줍니다. 전체 목록 보기의 경우 상태를 선택한 다음 상태 열을 기준으로 목록을 정렬합니다.

### <a name="rooms-history"></a>객실 기록

서비스에 등록된 객실의 과거 전망을 제공하며, 같은 기간에 정상이거나 모니터링되지 않은 객실의 비교 보기를 제공합니다.

## <a name="health"></a>건강

모든 회의실의 상태 보고서로 이동하려면 보고서를 선택한 다음  **상태를** 선택합니다.

<!--!![A screenshot of a Reports health percentage](../media/health-and-usage-001.png)-->

상태 점수는 최종 사용자 좌절을 일으킬 가능성이 가장 큰 회의실을 표시하도록 설계된 메트릭입니다. 객실은 하루 동안 건강하거나 비정상일 수 있습니다. 티켓이나 많은 티켓이 유지 보수 이외의 시간 동안 총 20 분 이상 방에 영향을 미친 경우 비정상으로 간주됩니다 (현지 시간 오전 5시 - 오후 9시 컴퓨터). 예를 들어 티켓이 오전 5:00에 열리지만 오전 5시 15분에 문을 닫는 경우 회의실은 여전히 정상으로 간주됩니다. 그러나 오전 09:00부터 오전 9시 10분까지 두 번째 티켓이 발생하면 방은 하루 동안 비정상으로 간주됩니다. 마찬가지로 오전 5시에서 오전 5시 21분까지 티켓이 발생한 경우 해당 날짜에 비정상으로 간주됩니다.

> [!NOTE]
> 하루의 상태는 UTC 시간 오전 12:00에 하루에 한 번 집계됩니다. 국제 날짜 줄 근처의 고객의 경우 근무일 중간에 상태 집계가 발생할 수 있습니다.

> [!NOTE]
> 온보딩 중인 회의실은 상태 탭의 회의실 목록에 대해 숨겨져 있으며 테넌트 평균 상태에 포함되지 않습니다.

이 보기에 나열된 회의실을 클릭하면 자세한 내용이 표시됩니다.

막대 그래프는 매일 티켓 수를 표시합니다. 해당 날짜에 열린 티켓은 파란색으로 표시됩니다. 해당 날짜 이전에 열린 티켓은 주황색으로 표시됩니다. 그래프에서 하루를 클릭하면 원형 차트와 테이블이 관련 티켓으로 필터링됩니다. 필터를 되돌리려면 이동 경로로 이동하거나 그래프를 클릭합니다.

티켓 분류는 도넛형 차트에 표시됩니다. 이와 상호 작용하면 타임라인 그래프와 테이블이 필터링됩니다. 필터를 되돌리려면 이동 경로로 이동하거나 그래프를 클릭합니다.

<!--!![A screenshot of a Reports health bar graph](../media/health-and-usage-014.png)-->

모임 영향 보기에는 심각도가 "중요" 또는 "중요"인 티켓이 열려 있는 예약된 모임이 표시됩니다. 이 보기의 목적은 참가자가 문제를 경험할 수 있는 모임의 근사치를 제공하는 것입니다.

모임 영향 보기에는 심각도가 "중요" 또는 "중요"인 티켓이 열려 있는 예약된 모임이 표시됩니다. 이 보기의 목적은 참가자가 문제를 경험할 수 있는 모임의 근사치를 제공하는 것입니다.

<!--![A screenshot of a Reports meeting impact](../media/health-and-usage-015.png)-->

설정 탭에는 하드웨어 정보, 디바이스 설정, BIOS 정보, 앱 설정 및 위치와 같은 회의실의 메타데이터가 표시됩니다.

## <a name="usage"></a>사용

모든 회의실의 사용 현황 보고서를 보려면 **보고서 >사용량을** 선택합니다.

<!--!![A screenshot of all rooms' usage by health](../media/health-and-usage-011.png)-->

헤드라인은 다음과 같은 몇 가지 인사이트를 제공합니다.

- 테넌트 내 총 회의실 수
- 오프라인 또는 온라인에서 예약된 모임이 없는 수
- 테넌트 전체의 회의실 사용률 백분율
- 교환을 통해 예약된 총 모임 수
- Skype 또는 Teams 링크가 포함된 예약된 모임의 백분율
- 회의실 참여가 있는 총 통화 수
- "양수" 품질로 분류된 모든 호출에서 모든 호출에 대한 호출 성능 점수를 집계합니다. 

헤드라인 메트릭 아래에는 해당 메트릭이 있는 회의실 테이블이 있습니다. 사용량 세부 정보를 볼 회의실을 선택합니다. 테이블의 메트릭은 다음 표에 설명되어 있습니다.

|열|설명|
|---|---|
|사용률|선택한 기간 동안 업무 시간 동안 객실을 예약한 시간의 백분율입니다. 전. 7일로 설정된 기간입니다. 32/40시간 동안 객실을 예약한 평균 사용률 80%|
|온라인 예약|예약된 모임 중 Teams에서 사용하도록 설정된 비율입니다. 전. 모임 10개가 예약되었습니다. 그 중 8개에는 Teams 링크가 있었습니다. 온라인 예약 = 80%|
|예약된 모임|회의실에서 예약된 모임의 절대 수|
|총 호출 수|회의실을 참가자로 사용하는 절대 통화 수입니다.|
통화 성능|"양수" 등급의 통화 비율입니다. 각 호출이 평가되고 양수, 불량, 알 수 없는 등급을 받습니다. 이 메트릭은 양수 호출/총 호출에서 계산됩니다.|

사용량은 회의실 장치의 현지 시간 자정(00:00)에 매일 종료 시 계산됩니다. 사용률은 해당 날짜의 총 예약된 모임 시간을 8시간으로 나눈 값에 따라 계산됩니다.

## <a name="usage-details-of-a-room"></a>회의실의 사용량 세부 정보

목록 보기에서 회의실을 클릭하면 자세한 정보가 포함된 플라이아웃이 표시됩니다. 플라이아웃의 사용률 탭 아래에는 지난 5일의 사용 시간을 보여 주는 그래프가 있습니다. 매일 두 개의 막대가 있습니다. 파란색은 예약된 모임 시간을 나타냅니다. purple은 Teams/Skype 사용 모임의 예약된 시간을 나타냅니다. 맨 아래에는 지난 5일 동안의 평균 모임 예약 및 기간이 계산됩니다.

<!--![A screenshot of utilization by hours per day](../media/health-and-usage-012.png)-->

**통화** 테이블에는 회의실이 Teams 통화에 참여한 모임이 표시됩니다. 회의실 오디오 품질은 모든 참가자가 아닌 회의실에 대해서만 평가됩니다. 특정 통화의 모든 참가자에 대한 통화 품질을 보려면 시작 시간을 클릭하여 통화를 선택합니다.

<!--!![A screenshot of room audio quality](../media/health-and-usage-016.png)-->

회의실의 스트림 세부 정보를 보려면 세션 시작 시간을 클릭합니다.
