---
title: 가상 방문 사용 현황 보고서 Microsoft Teams
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ''
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Microsoft Teams 관리 센터에서 가상 방문 사용 현황 보고서를 사용하여 조직의 가상 약속 활동에 대한 개요를 가져오는 방법을 알아봅니다.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 91f1aa8ff25b591305c8d5ca41485f7ceec9faca
ms.sourcegitcommit: 68162a8c9dee9a27af596353baabeda9b8fa64f3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2022
ms.locfileid: "64853219"
---
# <a name="microsoft-teams-virtual-visits-usage-report"></a>가상 방문 사용 현황 보고서 Microsoft Teams

Microsoft Teams 관리 센터의 가상 방문 사용 현황 보고서는 조직의 Teams 가상 약속 활동에 대한 개요를 제공합니다. [Bookings 앱 및 Microsoft Teams](../expand-teams-across-your-org/bookings-virtual-visits.md) [EHR(전자 건강 기록) 커넥터](../expand-teams-across-your-org/healthcare/teams-in-hc.md#virtual-appointments-and-electronic-healthcare-record-ehr-integration)를 통해 예약된 가상 약속에 대한 자세한 활동을 볼 수 있습니다.

보고서를 보려면 전역 관리자 또는 Teams 관리자여야 합니다.

보고서에는 다음 탭이 포함되어 있습니다. 보고서에 표시되는 정보는 Bookings 앱에 대한 라이선스, Teams EHR 커넥터 또는 둘 다에 따라 달라집니다.

|탭 |설명  |
|---------|---------|
|**[가상 방문](#virtual-visits)**     |Bookings 앱을 사용하여 예약된 약속 수와 EHR 시스템에서 수행된 EHR 통합 모임을 Teams 총 가상 약속 수를 보여 줍니다.         |
|**[기간](#duration)**     |약속의 평균 기간 및 참가자의 평균 로비 대기 시간을 표시합니다.         |
|**[Bookings](#bookings)**     |Bookings 앱을 통해 예약된 약속 수를 표시합니다.         |
|**[EHR](#ehr)**     |EHR 시스템에서 수행된 Teams EHR 통합 약속 수를 표시합니다.         |  

이 보고서를 사용하여 조직의 가상 약속 활동 및 추세에 대한 인사이트를 얻을 수 있습니다. 이 정보는 더 나은 비즈니스 결과를 제공하기 위해 가상 약속을 최적화하는 데 도움이 될 수 있습니다.

## <a name="view-the-virtual-visits-usage-report"></a>가상 방문 사용 현황 보고서 보기

1. Microsoft Teams 관리 센터의 왼쪽 탐색 영역에서 **Analytics &** **reportsUsage** >  보고서를 선택합니다. **보고서 보기** 탭의 **보고서** 아래에서 **가상 방문 사용량을** 선택합니다.
2. **날짜 범위** 에서 7일, 30일 또는 90일의 날짜 범위를 선택합니다. 그런 다음 **보고서 실행을** 선택합니다.

> [!NOTE]
> 기본적으로 가상 방문 분석은 켜지고 보고서를 사용할 수 있습니다. 이 보고서를 사용하여 조직의 가상 약속에 대한 데이터를 수집할 수 있는 권한을 Microsoft에 부여합니다. 데이터 보존 정책에 대한 자세한 내용은 [Microsoft 365 데이터 보존, 삭제 및 소멸을](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview) 참조하세요.
>
>조직의 보고서를 해제하려는 경우 페이지의 오른쪽 위 모서리에 **있는 설정** 이 작업을 수행할 수 있습니다. 이 설정을 변경한 후 적용하려면 0~2시간이 걸릴 수 있습니다.

## <a name="interpret-the-report"></a>보고서 해석

### <a name="virtual-visits"></a>가상 방문

여기에서 볼 수 있는 그래프는 Bookings 앱에 대한 라이선스가 있는지, Teams EHR 커넥터인지 또는 둘 다에 따라 달라집니다. 자세한 내용은 [Bookings 앱 관리](../bookings-app-admin.md) 및 [Cerner EHR에 통합](../expand-teams-across-your-org/healthcare/ehr-admin-cerner.md) 또는 [Epic EHR 통합을](../expand-teams-across-your-org/healthcare/ehr-admin.md) 참조하세요.

:::image type="content" source="../media/virtual-visits-usage-report-virtual-visits.png" alt-text="번호가 매겨진 설명선이 표시된 가상 방문 사용 현황 보고서의 가상 방문 탭 스크린샷." lightbox="../media/virtual-visits-usage-report-virtual-visits.png":::

|설명선 |설명  |
|--------|-------------|
|**1**   |각 보고서에는 보고서가 생성된 날짜가 있습니다. 보고서는 일반적으로 활동 시간으로부터 24~48시간의 대기 시간을 반영합니다. |
|**2**   |X축은 보고서에 대해 선택한 날짜 범위입니다. Y축은 약속 수입니다.<br>지정된 날짜의 점 위로 마우스를 가져가서 해당 날짜의 약속 수를 확인합니다.|
|**3**   |범례에서 항목을 선택하여 차트에 표시되는 내용을 필터링할 수 있습니다. 예를 들어 **총 Bookings 가상 방문** 또는 **총 EHR 가상 방문을** 선택하여 각 방문과 관련된 정보만 확인합니다. 이 선택을 변경해도 테이블의 정보는 변경되지 않습니다. |
|**4**   |이 표에서는 선택한 날짜 범위 동안 발생한 각 약속에 대한 자세한 정보를 제공합니다. <ul><li>**시작 시간(UTC)** 은 직원과 참가자가 모두 모임에 참가하거나 모임에서 첫 번째 활동이 발생한 날짜와 시간입니다.  </li> <li>**모임 ID는 모임** 의 고유 ID입니다.</li> <li>**로비 대기 시간은** 참가자가 처음으로 로비에 참가하는 시점과 동일한 참가자 또는 다른 참가자가 교직원에 의해 모임에 입장할 때까지의 시간입니다.</li><li>**기간** 은 시작 시간과 마지막 사용자가 모임을 떠날 때의 시간 차이입니다. 교직원 구성원과 참가자가 모두 모임에 참가하지 않은 경우 기간은 0으로 표시됩니다.</li> <li>**상태는** 모임 상태를 표시합니다. <ul><li>**완료** 됨: 하나 이상의 교직원과 참가자가 모임에 참가하고 모임이 종료된 경우 또는 한 명 이상의 참가자가 모임에 참가하고 모임이 종료된 경우</li> <li> **노쇼**: 한 명의 직원이 모임에 참가하지만 다른 사람이 참가하지 않고 모임이 종료된 경우 </li></ul> </li> <li>**모임 유형** 은 Bookings 앱 또는 Teams EHR 커넥터를 통해 가상 약속이 예약되었는지 여부를 나타냅니다.</li> <li>**참석자는** 모임의 총 교직원 및 참가자 수입니다.</li> <li>**보낸 SMS** 는 SMS 알림이 참석자에게 전송되었는지 여부를 나타냅니다. </li> </li> </ul> |
|**5**   |**설정** 선택하여 **가상 방문 분석** 창을 엽니다. 여기에서 조직에 대한 가상 방문 보고를 끄거나 켜고 테이블에 열을 추가하거나 제거할 수 있습니다. 테이블에서 원하는 정보를 보려면 테이블에 열을 추가해야 합니다.|
|**6**   |오프라인 분석을 위해 보고서를 CSV 파일로 내보낼 수 있습니다. **Excel 내보내기를** 선택한 다음 **다운로드** 탭에서 **다운로드** 를 선택하여 준비가 되면 보고서를 다운로드합니다.|

### <a name="duration"></a>기간

:::image type="content" source="../media/virtual-visits-usage-report-duration.png" alt-text="번호가 매겨진 설명선이 표시된 가상 방문 사용 현황 보고서의 기간 탭 스크린샷" lightbox="../media/virtual-visits-usage-report-duration.png":::

|설명선 |설명  |
|--------|-------------|
|**1**   |각 보고서에는 보고서가 생성된 날짜가 있습니다. 보고서는 일반적으로 활동 시간으로부터 24~48시간의 대기 시간을 반영합니다. |
|**2**   |X축은 보고서에 대해 선택한 날짜 범위입니다. Y축은 분 수입니다.<br>지정된 날짜의 점 위로 마우스를 가져가서 지정된 날짜의 평균 약속 기간 또는 평균 로비 대기 시간을 확인합니다.  |
|**3**   |범례에서 항목을 선택하여 차트에 표시되는 내용을 필터링할 수 있습니다. 예를 들어 **평균 가상 방문 기간** 또는 **평균 로비 대기 시간을** 선택하여 각 대기 시간과 관련된 정보만 확인합니다. 이 선택을 변경해도 테이블의 정보는 변경되지 않습니다. |
|**4**   |이 표에서는 선택한 날짜 범위 동안 발생한 각 약속에 대한 자세한 정보를 제공합니다. <ul><li>**시작 시간(UTC)** 은 직원과 참가자가 모두 모임에 참가하거나 모임에서 첫 번째 활동이 발생한 날짜와 시간입니다.  </li> <li>**모임 ID는 모임** 의 고유 ID입니다.</li> <li>**로비 대기 시간은** 참가자가 처음으로 로비에 참가하는 시점과 동일한 참가자 또는 다른 참가자가 교직원에 의해 모임에 입장할 때까지의 시간입니다.</li><li>**기간** 은 시작 시간과 마지막 사용자가 모임을 떠날 때의 시간 차이입니다. 교직원 구성원과 참가자가 모두 모임에 참가하지 않은 경우 기간은 0으로 표시됩니다.</li> <li>**상태는** 모임 상태를 표시합니다. <ul><li>**완료** 됨: 하나 이상의 교직원과 참가자가 모임에 참가하고 모임이 종료된 경우 또는 한 명 이상의 참가자가 모임에 참가하고 모임이 종료된 경우</li> <li> **노쇼**: 한 명의 직원이 모임에 참가하지만 다른 사람이 참가하지 않고 모임이 종료된 경우 </li></ul> </li> <li>**모임 유형** 은 Bookings 앱 또는 Teams EHR 커넥터를 통해 가상 약속이 예약되었는지 여부를 나타냅니다.</li> <li>**참석자는** 모임의 총 교직원 및 참가자 수입니다.</li> <li>**보낸 SMS** 는 SMS 알림이 참석자에게 전송되었는지 여부를 나타냅니다. </li> </li> </ul>|
|**5**   |**설정** 선택하여 **가상 방문 분석** 창을 엽니다. 여기에서 조직에 대한 가상 방문 보고를 끄거나 켜고 테이블에 열을 추가하거나 제거할 수 있습니다. 테이블에서 원하는 정보를 보려면 테이블에 열을 추가해야 합니다.|
|**6**   |오프라인 분석을 위해 보고서를 CSV 파일로 내보낼 수 있습니다. **Excel 내보내기를** 선택한 다음 **다운로드** 탭에서 **다운로드** 를 선택하여 준비가 되면 보고서를 다운로드합니다.|
### <a name="bookings"></a>Bookings

Bookings 앱을 포함하는 라이선스가 있는 경우 이 탭이 표시됩니다. 자세한 내용은 [Bookings 앱 관리를 참조하세요](../bookings-app-admin.md).

:::image type="content" source="../media/virtual-visits-usage-report-bookings.png" alt-text="번호가 매겨진 설명선이 표시된 가상 방문 사용 현황 보고서의 Bookings 탭 스크린샷" lightbox="../media/virtual-visits-usage-report-bookings.png":::

|설명선 |설명  |
|--------|-------------|
|**1**   |각 보고서에는 보고서가 생성된 날짜가 있습니다. 보고서는 일반적으로 활동 시간으로부터 24~48시간의 대기 시간을 반영합니다. |
|**2**   |X축은 보고서에 대해 선택한 날짜 범위입니다. Y축은 Bookings 약속의 수입니다.<br>지정된 날짜의 점 위로 마우스를 가져가서 해당 날짜에 발생한 Bookings 약속 수를 확인합니다.|
|**3**   |이 표에서는 선택한 날짜 범위 동안 발생한 각 약속에 대한 자세한 정보를 제공합니다. <ul><li>**시작 시간(UTC)** 은 직원과 참가자가 모두 모임에 참가하거나 모임에서 첫 번째 활동이 발생한 날짜와 시간입니다.  </li> <li>**모임 ID는 모임** 의 고유 ID입니다.</li> <li>**로비 대기 시간은** 참가자가 처음으로 로비에 참가하는 시점과 동일한 참가자 또는 다른 참가자가 교직원에 의해 모임에 입장할 때까지의 시간입니다.</li><li>**기간** 은 시작 시간과 마지막 사용자가 모임을 떠날 때의 시간 차이입니다. 교직원 구성원과 참가자가 모두 모임에 참가하지 않은 경우 기간은 0으로 표시됩니다.</li> <li>**상태는** 모임 상태를 표시합니다. <ul><li>**완료** 됨: 하나 이상의 교직원과 참가자가 모임에 참가하고 모임이 종료된 경우 또는 한 명 이상의 참가자가 모임에 참가하고 모임이 종료된 경우</li> <li> **노쇼**: 한 명의 직원이 모임에 참가하지만 다른 사람이 참가하지 않고 모임이 종료된 경우 </li></ul> </li> <li>**모임 유형** 은 Bookings 앱 또는 Teams EHR 커넥터를 통해 가상 약속이 예약되었는지 여부를 나타냅니다.</li> <li>**참석자는** 모임의 총 교직원 및 참가자 수입니다.</li> <li>**보낸 SMS** 는 SMS 알림이 참석자에게 전송되었는지 여부를 나타냅니다. </li> </li> </ul>|
|**4**   |**설정** 선택하여 **가상 방문 분석** 창을 엽니다. 여기에서 조직에 대한 가상 방문 보고를 끄거나 켜고 테이블에 열을 추가하거나 제거할 수 있습니다. 테이블에서 원하는 정보를 보려면 테이블에 열을 추가해야 합니다.|
|**5**   |오프라인 분석을 위해 보고서를 CSV 파일로 내보낼 수 있습니다. **Excel 내보내기를** 선택한 다음 **다운로드** 탭에서 **다운로드** 를 선택하여 준비가 되면 보고서를 다운로드합니다.|
### <a name="ehr"></a>EHR

Teams EHR 커넥터를 포함하는 라이선스가 있는 경우 이 탭이 표시됩니다. 자세한 내용은 [Cerner EHR에 통합](../expand-teams-across-your-org/healthcare/ehr-admin-cerner.md) 또는 [Epic EHR 통합을](../expand-teams-across-your-org/healthcare/ehr-admin.md) 참조하세요.

:::image type="content" source="../media/virtual-visits-usage-report-ehr.png" alt-text="번호가 매겨진 설명선이 표시된 가상 방문 사용 현황 보고서의 EHR 탭 스크린샷" lightbox="../media/virtual-visits-usage-report-ehr.png":::

|설명선 |설명  |
|--------|-------------|
|**1**   |각 보고서에는 보고서가 생성된 날짜가 있습니다. 보고서는 일반적으로 활동 시간으로부터 24~48시간의 대기 시간을 반영합니다. |
|**2**   |X축은 보고서에 대해 선택한 날짜 범위입니다. Y축은 EHR 약속의 수입니다.<br>지정된 날짜의 점 위로 마우스를 가져가서 해당 날짜의 EHR 약속 수를 확인합니다.|
|**3**   |이 표에서는 선택한 날짜 범위 동안 발생한 각 약속에 대한 자세한 정보를 제공합니다. <ul><li>**시작 시간(UTC)** 은 직원과 참가자가 모두 모임에 참가하거나 모임에서 첫 번째 활동이 발생한 날짜와 시간입니다.  </li> <li>**모임 ID는 모임** 의 고유 ID입니다.</li> <li>**로비 대기 시간은** 참가자가 처음으로 로비에 참가하는 시점과 동일한 참가자 또는 다른 참가자가 교직원에 의해 모임에 입장할 때까지의 시간입니다.</li><li>**기간** 은 시작 시간과 마지막 사용자가 모임을 떠날 때의 시간 차이입니다. 교직원 구성원과 참가자가 모두 모임에 참가하지 않은 경우 기간은 0으로 표시됩니다.</li> <li>**상태는** 모임 상태를 표시합니다. <ul><li>**완료** 됨: 하나 이상의 교직원과 참가자가 모임에 참가하고 모임이 종료된 경우 또는 한 명 이상의 참가자가 모임에 참가하고 모임이 종료된 경우</li> <li> **노쇼**: 한 명의 직원이 모임에 참가하지만 다른 사람이 참가하지 않고 모임이 종료된 경우 </li></ul> </li> <li>**모임 유형** 은 Bookings 앱 또는 Teams EHR 커넥터를 통해 가상 약속이 예약되었는지 여부를 나타냅니다.</li> <li>**참석자는** 모임의 총 교직원 및 참가자 수입니다.</li> <li>**보낸 SMS** 는 SMS 알림이 참석자에게 전송되었는지 여부를 나타냅니다. </li> </li> </ul>|
|**4**   |**설정** 선택하여 **가상 방문 분석** 창을 엽니다. 여기에서 조직에 대한 가상 방문 보고를 끄거나 켜고 테이블에 열을 추가하거나 제거할 수 있습니다. 테이블에서 원하는 정보를 보려면 테이블에 열을 추가해야 합니다.|
|**5**   |오프라인 분석을 위해 보고서를 CSV 파일로 내보낼 수 있습니다. **Excel 내보내기를** 선택한 다음 **다운로드** 탭에서 **다운로드** 를 선택하여 준비가 되면 보고서를 다운로드합니다.|

> [!NOTE]
> 조직에서 비즈니스 의사 결정자와 같은 관리자가 아닌 사용자가 이 보고서에 액세스하고 볼 수 있도록 비공개 미리 보기에 참여하려는 경우 [문의하세요](mailto:tapmwtanalytics@microsoft.com).

## <a name="related-articles"></a>관련 기사

- [Teams 분석 및 보고](teams-reporting-reference.md)
- [Teams 및 Bookings 앱을 사용하여 가상 약속](../expand-teams-across-your-org/bookings-virtual-visits.md)
- [Teams 가상 약속 - Epic EHR에 통합](../expand-teams-across-your-org/healthcare/ehr-admin.md)
- [Teams 가상 약속 - Cerner EHR에 통합](../expand-teams-across-your-org/healthcare/ehr-admin-cerner.md)
