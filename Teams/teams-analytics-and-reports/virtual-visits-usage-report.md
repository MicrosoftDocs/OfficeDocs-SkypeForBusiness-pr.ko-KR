---
title: Microsoft Teams 가상 방문 사용 현황 보고서
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
description: 관리 센터에서 가상 방문 사용 Microsoft Teams 보고서를 사용하여 조직의 가상 방문 활동에 대한 개요를 얻을 수 있는 방법을 알아보습니다.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1f00a8e0837ad4603fe38f664f94716aa8016aa9
ms.sourcegitcommit: 5ca04ee10e3f254e1b24506de116591fdfd51d18
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2022
ms.locfileid: "62929423"
---
# <a name="microsoft-teams-virtual-visits-usage-report"></a>Microsoft Teams 가상 방문 사용 현황 보고서

**미리 보기 기능입니다**.

관리 센터의 가상 방문 Microsoft Teams 보고서는 조직의 가상 방문 Teams 개요를 제공합니다. [Bookings](../expand-teams-across-your-org/bookings-virtual-visits.md) 앱 및 [EHR](../expand-teams-across-your-org/healthcare/teams-in-hc.md#virtual-visits-and-electronic-healthcare-record-ehr-integration)(전자 상태 레코드) 커넥터를 통해 예약된 가상 약속에 대한 Microsoft Teams 자세한 활동을 볼 수 있습니다.

보고서를 보기 위해 전역 관리자 또는 관리자 Teams 해야 합니다.

보고서에는 다음 탭이 포함되어 있습니다. 보고서에 표시될 정보는 Bookings 앱에 대한 라이선스가 있는지, EHR 커넥터에 대한 라이선스를 Teams 여부에 따라 결정됩니다.

|탭 |설명  |
|---------|---------|
|**[가상 방문](#virtual-visits)**     |총 가상 방문 수를 보여 주며, 예약 앱을 사용하여 예약된 방문 수를 분석하고 EHR 시스템에서 Teams EHR 통합 모임을 실행합니다.         |
|**[기간](#duration)**     |참가자의 평균 방문 기간 및 평균 로비 대기 시간을 보여줍니다.         |
|**[Bookings](#bookings)**     |Bookings 앱을 통해 예약된 방문 수를 보여줍니다.         |
|**[EHR](#ehr)**     |EHR 시스템에서 수행된 EHR Teams EHR 통합 방문 수를 보여줍니다.         |  

이 보고서를 사용하여 조직의 Virtual Visits 활동 및 추세에 대한 인사이트를 얻습니다. 이 정보는 가상 방문을 최적화하여 더 나은 비즈니스 결과를 제공하는 데 도움이 될 수 있습니다.

## <a name="view-the-virtual-visits-usage-report"></a>가상 방문 사용 보고서 보기

1. 관리 센터의 왼쪽 탐색에서 Microsoft Teams **분석 & 보고서** > **Usage 보고서를 선택하세요**. 보고서 **보기 탭** 의 **보고서에서** **가상 방문 사용량을 선택합니다**.
2. 날짜 **범위에서** 7일, 30일 또는 90일의 날짜 범위를 선택합니다. 그런 다음 보고서 **실행을 선택 합니다**.

> [!NOTE]
> 기본적으로 Virtual Visits 분석이 설정되어 있으며 보고서를 사용할 수 있습니다. 이 보고서를 사용하면 Microsoft에게 조직의 가상 방문에 대한 데이터를 수집할 수 있는 권한을 부여합니다. 데이터 보존 정책에 대한 자세한 내용은 데이터 보존[,](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview) 삭제 및 삭제를 Microsoft 365.
>
>조직의 보고서를 해제하려는 경우 페이지의 오른쪽 **위** 모서리에 있는 설정 할 수 있습니다.


## <a name="interpret-the-report"></a>보고서 해석

### <a name="virtual-visits"></a>가상 방문

여기에서 볼 수 있는 그래프는 Bookings 앱에 대한 라이선스가 있는지, EHR Teams 또는 둘 다에 따라 결정됩니다. 자세한 내용은 [예약](../bookings-app-admin.md) 앱 관리 및 [Cerner EHR](../expand-teams-across-your-org/healthcare/ehr-admin-cerner.md) 에 통합 또는 [Epic EHR 통합을 참조하세요](../expand-teams-across-your-org/healthcare/ehr-admin.md).

:::image type="content" source="../media/virtual-visits-usage-report-virtual-visits.png" alt-text="번호 매기기 콜아웃을 보여주는 가상 방문 사용 보고서의 가상 방문 탭 스크린샷." lightbox="../media/virtual-visits-usage-report-virtual-visits.png":::

|콜아웃 |설명  |
|--------|-------------|
|**1**   |각 보고서에는 보고서가 생성된 날짜가 있습니다. 보고서는 일반적으로 활동 시간으로부터 24~48시간의 대기 시간을 반영합니다. |
|**2**   |X 축은 보고서에 대해 선택한 날짜 범위입니다. Y축은 방문 횟수입니다.<br>주어진 날짜에 점 위에 마우스를 대고 그 날짜의 방문 수를 볼 수 있습니다.|
|**3**   |범례에서 항목을 선택하여 차트에 표시하는 항목을 필터링할 수 있습니다. 예를 들어 총 예약  가상 방문 또는 **총 EHR** 가상 방문을 선택하여 각 가상 방문과 관련된 정보만 볼 수 있습니다. 이 선택을 변경해도 표의 정보가 변경되지 않습니다. |
|**4**   |표는 선택한 날짜 범위 동안 이행된 각 방문에 대한 자세한 정보를 제공합니다. <ul><li>**시작 시간(UTC** )은 직원 구성원과 참가자가 모두 모임에 참석하거나 모임에서 첫 번째 활동이 발생한 날짜 및 시간입니다.  </li> <li>**모임 ID** 는 모임의 고유 ID입니다.</li> <li>**로비 대기 시간은** 참가자가 로비에 처음 참가할 때와 같은 참가자 또는 다른 참가자가 직원 구성원이 모임에 참가할 때의 시간입니다.</li><li>**기간** 은 시작 시간과 마지막 사람이 모임을 떠날 때의 시간 차이입니다. 직원 구성원과 참가자가 모임에 참가하지 않은 경우 기간은 0(0)으로 표시됩니다.</li> <li>**상태** 는 모임 상태를 보여줍니다. <ul><li>**완료**: 하나 이상의 직원 구성원 및 참가자가 모임에 참가하고 모임이 종료된 경우. 또는 하나 이상의 참가자가 모임에 참가하고 모임이 종료된 경우.</li> <li> **아니요**: 한 직원 구성원이 모임에 참가하지만 다른 사람이 참가하지 않지만 모임이 종료된 경우 </li></ul> </li> <li>**모임 형식** 은 Bookings 앱 또는 EHR 커넥터를 통해 가상 약속이 예약되어 있는지 Teams 나타냅니다.</li> <li>**참석자는** 모임의 총 직원 및 참가자 수입니다.</li> <li>**보낸 SMS** 는 참석자에 SMS 알림이 전송된지 여부를 나타냅니다. </li> </li> </ul> |
|**5**   |가상 **설정** 분석 창 **을** 를 를 선택합니다. 여기에서 조직의 가상 방문 보고를 끄거나 끄고 표에 열을 추가하거나 제거할 수 있습니다. 표에서 원하는 정보를 확인하려는 경우 테이블에 열을 추가해야 합니다.|
|**6**   |오프라인 분석을 위해 보고서를 CSV 파일로 내보낼 수 있습니다. 내보내 **기를 Excel** 선택한 다음 다운로드 탭에서 다운로드를 선택하여  준비가되면 보고서를 다운로드합니다.|

### <a name="duration"></a>기간

:::image type="content" source="../media/virtual-visits-usage-report-duration.png" alt-text="번호 매기기 설명을 보여주는 가상 방문 사용 보고서의 기간 탭 스크린샷." lightbox="../media/virtual-visits-usage-report-duration.png":::

|콜아웃 |설명  |
|--------|-------------|
|**1**   |각 보고서에는 보고서가 생성된 날짜가 있습니다. 보고서는 일반적으로 활동 시간으로부터 24~48시간의 대기 시간을 반영합니다. |
|**2**   |X 축은 보고서에 대해 선택한 날짜 범위입니다. Y 축은 분 수입니다.<br>주어진 날짜에 점 위에 마우스를 대고 주어진 날짜에 대한 평균 방문 기간 또는 평균 로비 대기 시간을 볼 수 있습니다.  |
|**3**   |범례에서 항목을 선택하여 차트에 표시하는 항목을 필터링할 수 있습니다. 예를 들어 평균 **가상** 방문 기간 또는 평균 로비  대기 시간을 선택하여 각 로비와 관련된 정보만 볼 수 있습니다. 이 선택을 변경해도 표의 정보가 변경되지 않습니다. |
|**4**   |표는 선택한 날짜 범위 동안 이행된 각 방문에 대한 자세한 정보를 제공합니다. <ul><li>**시작 시간(UTC** )은 직원 구성원과 참가자가 모두 모임에 참석하거나 모임에서 첫 번째 활동이 발생한 날짜 및 시간입니다.  </li> <li>**모임 ID** 는 모임의 고유 ID입니다.</li> <li>**로비 대기 시간은** 참가자가 로비에 처음 참가할 때와 같은 참가자 또는 다른 참가자가 직원 구성원이 모임에 참가할 때의 시간입니다.</li><li>**기간** 은 시작 시간과 마지막 사람이 모임을 떠날 때의 시간 차이입니다. 직원 구성원과 참가자가 모임에 참가하지 않은 경우 기간은 0(0)으로 표시됩니다.</li> <li>**상태** 는 모임 상태를 보여줍니다. <ul><li>**완료**: 하나 이상의 직원 구성원 및 참가자가 모임에 참가하고 모임이 종료된 경우. 또는 하나 이상의 참가자가 모임에 참가하고 모임이 종료된 경우.</li> <li> **아니요**: 한 직원 구성원이 모임에 참가하지만 다른 사람이 참가하지 않지만 모임이 종료된 경우 </li></ul> </li> <li>**모임 형식** 은 Bookings 앱 또는 EHR 커넥터를 통해 가상 약속이 예약되어 있는지 Teams 나타냅니다.</li> <li>**참석자는** 모임의 총 직원 및 참가자 수입니다.</li> <li>**보낸 SMS** 는 참석자에 SMS 알림이 전송된지 여부를 나타냅니다. </li> </li> </ul>|
|**5**   |가상 **설정** 분석 창 **을** 를 를 선택합니다. 여기에서 조직의 가상 방문 보고를 끄거나 끄고 표에 열을 추가하거나 제거할 수 있습니다. 표에서 원하는 정보를 확인하려는 경우 테이블에 열을 추가해야 합니다.|
|**6**   |오프라인 분석을 위해 보고서를 CSV 파일로 내보낼 수 있습니다. 내보내 **기를 Excel** 선택한 다음 다운로드 탭에서 다운로드를 선택하여  준비가되면 보고서를 다운로드합니다.|
### <a name="bookings"></a>Bookings

Bookings 앱이 포함된 라이선스가 있는 경우 이 탭이 표시됩니다. 자세한 내용은 [예약 앱 관리를 참조하세요](../bookings-app-admin.md).

:::image type="content" source="../media/virtual-visits-usage-report-bookings.png" alt-text="번호 매기기 설명을 보여주는 가상 방문 사용 보고서의 예약 탭 스크린샷입니다." lightbox="../media/virtual-visits-usage-report-bookings.png":::

|콜아웃 |설명  |
|--------|-------------|
|**1**   |각 보고서에는 보고서가 생성된 날짜가 있습니다. 보고서는 일반적으로 활동 시간으로부터 24~48시간의 대기 시간을 반영합니다. |
|**2**   |X 축은 보고서에 대해 선택한 날짜 범위입니다. Y축은 방문하는 예약 수입니다.<br>주어진 날짜에 점 위에 마우스를 대고 그 날짜에 발생한 예약 방문 수를 볼 수 있습니다.|
|**3**   |표는 선택한 날짜 범위 동안 이행된 각 방문에 대한 자세한 정보를 제공합니다. <ul><li>**시작 시간(UTC** )은 직원 구성원과 참가자가 모두 모임에 참석하거나 모임에서 첫 번째 활동이 발생한 날짜 및 시간입니다.  </li> <li>**모임 ID** 는 모임의 고유 ID입니다.</li> <li>**로비 대기 시간은** 참가자가 로비에 처음 참가할 때와 같은 참가자 또는 다른 참가자가 직원 구성원이 모임에 참가할 때의 시간입니다.</li><li>**기간** 은 시작 시간과 마지막 사람이 모임을 떠날 때의 시간 차이입니다. 직원 구성원과 참가자가 모임에 참가하지 않은 경우 기간은 0(0)으로 표시됩니다.</li> <li>**상태** 는 모임 상태를 보여줍니다. <ul><li>**완료**: 하나 이상의 직원 구성원 및 참가자가 모임에 참가하고 모임이 종료된 경우. 또는 하나 이상의 참가자가 모임에 참가하고 모임이 종료된 경우.</li> <li> **아니요**: 한 직원 구성원이 모임에 참가하지만 다른 사람이 참가하지 않지만 모임이 종료된 경우 </li></ul> </li> <li>**모임 형식** 은 Bookings 앱 또는 EHR 커넥터를 통해 가상 약속이 예약되어 있는지 Teams 나타냅니다.</li> <li>**참석자는** 모임의 총 직원 및 참가자 수입니다.</li> <li>**보낸 SMS** 는 참석자에 SMS 알림이 전송된지 여부를 나타냅니다. </li> </li> </ul>|
|**4**   |가상 **설정** 분석 창 **을** 를 를 선택합니다. 여기에서 조직의 가상 방문 보고를 끄거나 끄고 표에 열을 추가하거나 제거할 수 있습니다. 표에서 원하는 정보를 확인하려는 경우 테이블에 열을 추가해야 합니다.|
|**5**   |오프라인 분석을 위해 보고서를 CSV 파일로 내보낼 수 있습니다. 내보내 **기를 Excel** 선택한 다음 다운로드 탭에서 다운로드를 선택하여  준비가되면 보고서를 다운로드합니다.|
### <a name="ehr"></a>EHR

EHR 커넥터를 포함하는 라이선스가 있는 경우 이 Teams 표시됩니다. 자세한 내용은 [Cerner EHR](../expand-teams-across-your-org/healthcare/ehr-admin-cerner.md) 에 통합 또는 [Epic EHR 통합을 참조합니다](../expand-teams-across-your-org/healthcare/ehr-admin.md).

:::image type="content" source="../media/virtual-visits-usage-report-ehr.png" alt-text="번호 매기기 콜아웃을 보여주는 Virtual Visits 사용 보고서의 EHR 탭 스크린샷" lightbox="../media/virtual-visits-usage-report-ehr.png":::

|콜아웃 |설명  |
|--------|-------------|
|**1**   |각 보고서에는 보고서가 생성된 날짜가 있습니다. 보고서는 일반적으로 활동 시간으로부터 24~48시간의 대기 시간을 반영합니다. |
|**2**   |X 축은 보고서에 대해 선택한 날짜 범위입니다. Y 축은 EHR 방문 횟수입니다.<br>주어진 날짜에 점 위에 마우스를 대고 이 날짜에 방문하는 EHR의 수를 볼 수 있습니다.|
|**3**   |표는 선택한 날짜 범위 동안 이행된 각 방문에 대한 자세한 정보를 제공합니다. <ul><li>**시작 시간(UTC** )은 직원 구성원과 참가자가 모두 모임에 참석하거나 모임에서 첫 번째 활동이 발생한 날짜 및 시간입니다.  </li> <li>**모임 ID** 는 모임의 고유 ID입니다.</li> <li>**로비 대기 시간은** 참가자가 로비에 처음 참가할 때와 같은 참가자 또는 다른 참가자가 직원 구성원이 모임에 참가할 때의 시간입니다.</li><li>**기간** 은 시작 시간과 마지막 사람이 모임을 떠날 때의 시간 차이입니다. 직원 구성원과 참가자가 모임에 참가하지 않은 경우 기간은 0(0)으로 표시됩니다.</li> <li>**상태** 는 모임 상태를 보여줍니다. <ul><li>**완료**: 하나 이상의 직원 구성원 및 참가자가 모임에 참가하고 모임이 종료된 경우. 또는 하나 이상의 참가자가 모임에 참가하고 모임이 종료된 경우.</li> <li> **아니요**: 한 직원 구성원이 모임에 참가하지만 다른 사람이 참가하지 않지만 모임이 종료된 경우 </li></ul> </li> <li>**모임 형식** 은 Bookings 앱 또는 EHR 커넥터를 통해 가상 약속이 예약되어 있는지 Teams 나타냅니다.</li> <li>**참석자는** 모임의 총 직원 및 참가자 수입니다.</li> <li>**보낸 SMS** 는 참석자에 SMS 알림이 전송된지 여부를 나타냅니다. </li> </li> </ul>|
|**4**   |가상 **설정** 분석 창 **을** 를 를 선택합니다. 여기에서 조직의 가상 방문 보고를 끄거나 끄고 표에 열을 추가하거나 제거할 수 있습니다. 표에서 원하는 정보를 확인하려는 경우 테이블에 열을 추가해야 합니다.|
|**5**   |오프라인 분석을 위해 보고서를 CSV 파일로 내보낼 수 있습니다. 내보내 **기를 Excel** 선택한 다음 다운로드 탭에서 다운로드를 선택하여  준비가되면 보고서를 다운로드합니다.|

> [!NOTE]
> 조직에서 비즈니스 의사 결정권자가 이 보고서를 액세스하고 볼 수 있도록 관리자가 아닌 사용자를 위한 비공개 미리 보기에 참여하려면 문의 [하세요](mailto:tapmwtanalytics@microsoft.com).

## <a name="related-articles"></a>관련 기사

- [Teams 분석 및 보고](teams-reporting-reference.md)
- [가상 Teams 및 Bookings 앱을 통해 가상 방문](../expand-teams-across-your-org/bookings-virtual-visits.md)
- [가상 Teams - Epic EHR에 통합](../expand-teams-across-your-org/healthcare/ehr-admin.md)
- [가상 Teams - Cerner EHR에 통합](../expand-teams-across-your-org/healthcare/ehr-admin-cerner.md)
