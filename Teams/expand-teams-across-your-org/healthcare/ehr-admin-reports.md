---
title: Microsoft Teams EHR 커넥터 가상 약속 보고서
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
- m365solution-healthcare
- m365solution-scenario
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Microsoft Teams 관리 센터에서 Teams EHR 커넥터 가상 약속 보고서를 사용하여 조직에서 EHR 통합 가상 약속 사용에 대한 개요를 가져오는 방법을 알아봅니다.
ms.openlocfilehash: 0e78b89c934eac101b863bd7b5ba9957939f994b
ms.sourcegitcommit: cf2f2d23e6dcda0c03f22a5800a210a1c88e583f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/03/2022
ms.locfileid: "65883541"
---
# <a name="microsoft-teams-ehr-connector-virtual-appointments-report"></a>Microsoft Teams EHR 커넥터 가상 약속 보고서

Microsoft Teams 관리 센터의 Microsoft Teams EHR(전자 건강 기록) 커넥터 가상 약속 보고서를 통해 조직에서 Teams EHR 통합 가상 약속 사용량을 빠르고 쉽게 볼 수 있습니다.

보고서를 보려면 전역 관리자, Teams 관리자, 전역 읽기 권한자 또는 보고서 읽기 권한자여야 합니다.

## <a name="view-the-report"></a>보고서 보기

Teams 관리 센터에서 보고서에 액세스하고 보는 방법에는 두 가지가 있습니다.

- 대시보드의 [EHR 커넥터 사용 카드를](#the-ehr-connector-usage-card) 통해
- **분석 & 보고서****사용 현황 보고서에서** >  [**EHR 커넥터 가상 약속을**](#the-teams-ehr-connector-virtual-appointments-report) 선택하여 직접

### <a name="the-ehr-connector-usage-card"></a>EHR 커넥터 사용 카드

Microsoft Teams 관리 센터의 왼쪽 탐색 영역에서 **대시보드** 를 선택한 다음 **EHR 커넥터 가상 약속** 카드로 이동합니다.

여기에서 완료된 약속, 남은 할당, 월간 한도를 초과했는지 여부(라이선스에 따라 다름)를 포함하여 매월 Teams EHR 통합 가상 약속 활동을 한눈에 볼 수 있습니다.

:::image type="content" source="../../media/ehr-connector-report-card.png" alt-text="Teams 관리 센터 대시보드의 EHR 커넥터 사용 카드 스크린샷." lightbox="../../media/ehr-connector-report-card.png":::

**세부 정보 보기를** 선택하여 보고서 세부 정보를 확인합니다. 더 많은 라이선스를 구입하려면 **더 많은 구매** 를 선택합니다.

### <a name="the-teams-ehr-connector-virtual-appointments-report"></a>Teams EHR 커넥터 가상 약속 보고서

1. Teams 관리 센터의 왼쪽 탐색 영역에서 **분석 & 보고서****사용 현황 보고서** > 로 이동합니다.
1. **보고서 보기** 탭에서 **EHR 커넥터 가상 약속** 및 날짜 범위를 선택합니다. 그런 다음 **보고서 실행을** 선택합니다.

    :::image type="content" source="../../media/ehr-connector-report.png" alt-text="Teams 관리 센터의 Teams EHR 커넥터 가상 약속 보고서 스크린샷." lightbox="../../media/ehr-connector-report.png":::

#### <a name="interpret-the-report"></a>보고서 해석

|설명선 |설명  |
|--------|-------------|
|**1**   |각 보고서에는 보고서가 생성된 날짜와 선택한 날짜 범위가 표시됩니다.|
|**2**   |이 표에서는 선택한 날짜 범위 동안 발생한 각 약속에 대한 자세한 정보를 제공합니다. 직원 또는 환자가 참가하지 않은 약속에 대한 항목은 표시되지 않습니다. <ul><li>**시작 시간(UTC)** 은 직원 구성원과 참가자가 모두 약속에 있는 날짜 및 시간입니다.  </li> <li>**기간** 은 시작 시간과 마지막 사용자가 약속을 떠날 때의 시간 차이입니다.</li> <li>**기본은** 모임 이끌이의 이름입니다. <li>**기본 전자 메일** 은 모임 이끌이의 전자 메일 주소입니다.</li> <li> **부서** 가 약속에 대한 부서 정보입니다. 정보가 올바르게 표시되지 않으면 EHR 지원 팀에 문의하세요. Epic과의 통합을 위해 공급자 통합 레코드의 일부인지 확인 ```&departmentId=%PERFDEPID;;; ; ;;NONE;%``` 합니다. </li></li> <li>**참석자** 는 약속의 직원 및 참가자의 총 수입니다.</li> <li>**제한 내에서** 약속이 할당 한도 내에 있는지 여부를 나타냅니다. </li> </ul> |
|**3**   |오프라인 분석을 위해 보고서를 CSV 파일로 내보낼 수 있습니다. **Excel로 내보내기를** 선택하여 보고서를 다운로드합니다. |
|**4**   |**필터** 를 선택하여 보고서 세부 정보 보기를 필터링합니다. |
|**5**   |**전체 화면을** 선택하여 전체 화면 모드에서 보고서를 봅니다. |
|**6**   |**열 편집을** 선택하여 테이블에서 열을 추가하거나 제거합니다. |

> [!NOTE]
> Teams EHR 통합 가상 약속에 대한 자세한 분석은 [가상 방문 사용 현황 보고서를 참조하세요](../../teams-analytics-and-reports/virtual-visits-usage-report.md). 가상 방문 사용 현황 보고서를 사용하면 총 약속, 로비 대기 시간, 약속 기간 및 쇼 없음과 같은 주요 메트릭을 볼 수 있습니다. 이 정보를 사용하여 사용량 추세에 대한 인사이트를 확보하여 더 나은 비즈니스 결과를 제공하기 위해 가상 약속을 최적화할 수 있습니다.

## <a name="related-articles"></a>관련 기사

- [Teams를 사용하여 가상 약속 - Cerner EHR에 통합](ehr-admin-cerner.md)
- [Teams를 사용하여 가상 약속 - Epic EHR에 통합](ehr-admin.md) 
