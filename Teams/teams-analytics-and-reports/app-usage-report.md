---
title: Microsoft Teams 앱 사용 현황 보고서
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: vapati
ms.date: 09/27/2022
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Microsoft Teams 관리 센터에서 Teams 앱 사용 현황 보고서를 사용하는 방법을 알아봅니다.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c437676df215ead9b588091f2cb58c19d1e136fd
ms.sourcegitcommit: 8dd36e1e30a47316c15c99e964d0464715bcd742
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2022
ms.locfileid: "68532268"
---
# <a name="microsoft-teams-app-usage-report"></a>Microsoft Teams 앱 사용 현황 보고서

Microsoft Teams 관리 센터의 Teams 앱 사용 현황 보고서는 사용자가 Teams에서 사용하는 앱에 대한 인사이트를 제공합니다. 다양한 Microsoft(Viva Learning, Shifts 등), 타사(Polly, Trello 등) & LOB(기간 업무) Teams 앱에 대한 조직의 앱 활동에 대한 인사이트를 얻을 수 있습니다.   

이 보고서를 사용하여 정확히 다른 앱이 사용되는 위치를 파악하고 앱별 사용률 데이터에 대해 자세히 알아볼 수 있습니다.

이 보고서에 표시된 데이터는 다음 질문에 대한 답변을 제공합니다.

-  사용자 환경에 설치된 앱은 몇 개입니까?
-  유형(Microsoft, 타사 및 LOB)에 따라 사용자 환경에 활성 사용자가 하나 이상 있는 앱은 몇 개입니까?
-  플랫폼당 사용 중인 앱(Windows, Mac, 웹 또는 모바일)은 몇 개입니까?
-  앱을 사용하는 활성 사용자 및 활성 팀 수

> [!NOTE]
> **테스트용으로 로드된** LOB 앱의 사용량은 이 보고서에 포함되지 않습니다.

이 문서에서는 보고서에 액세스하고 보고서 내의 다양한 메트릭을 보고 해석하는 방법을 설명합니다. 

## <a name="view-the-app-usage-report"></a>앱 사용 현황 보고서 보기

Microsoft Teams 관리 센터에서 보고서를 보려면 전역 관리자, 전역 읽기 권한자 또는 Teams 서비스 관리자여야 합니다. 관리 역할 및 사용 권한 가져오기에 대한 내용은 [Teams 관리자 역할 사용](../using-admin-roles.md)을 참조하세요.

1. Microsoft Teams 관리 센터의 왼쪽 탐색 영역에서 **분석 & 보고서****사용 현황 보고서를** >  선택합니다. **보고서 보기** 탭의 **보고서** 아래에서 **앱 사용량을** 선택합니다.

2. **날짜 범위** 에서 범위를 선택한 다음 **보고서 실행을** 선택합니다.

:::image type="content" alt-text="설명선이 있는 Teams 관리 센터의 Teams 앱 사용 현황 보고서 스크린샷" source="media/app-usage2-report10.png" lightbox="media/app-usage2-report10.png":::

## <a name="interpret-the-report"></a>보고서 해석

|설명선 |설명  |
|--------|-------------|
|**1**   |앱 사용 현황 보고서는 지난 7일, 30일, 90일 및 180일 동안의 추세를 볼 수 있습니다. |
|**2**   |각 보고서에는 이 보고서가 생성된 날짜가 있습니다. 보고서는 일반적으로 앱이 사용된 시간부터 24~48시간의 대기 시간을 반영합니다. 예를 들어 1월 10일에 대한 데이터는 1월 12일 경에 보고서에 표시됩니다. |
|**3**   |<ul><li>차트의 X축은 보고서에 대해 선택한 날짜 범위입니다.</li> <li> Y축은 항목 수입니다.</li> </ul>지정된 날짜의 항목을 나타내는 점 위로 마우스를 가져가서 해당 지정된 날짜에 해당 항목의 인스턴스 수를 확인합니다.|
|**4**   |범례에서 항목을 선택하여 차트에 표시되는 내용을 필터링할 수 있습니다. 예를 들어 **활성 Microsoft 앱**, **설치된 총 앱** 등을 선택하여 각 앱과 관련된 정보만 확인합니다. 이 선택을 변경해도 테이블의 정보는 변경되지 않습니다. <ul><li>**활성 Microsoft 앱** 은 조직 전체에서 사용되는 Microsoft 앱(예: Viva Learning)의 수입니다. </li> <li>**활성 타사 앱** 은 조직 전체에서 사용되는 타사 앱(예: Polly)의 수입니다.  </li> <li>**활성 LOB 앱** 은 조직 전체에서 사용되는 기간 업무 앱 수입니다. </li><li>**총 활성 앱** 은 조직 전체에서 사용되는 총 앱 수입니다. </li><li>**총 비활성 앱** 은 조직에서 사용되지 않는 앱의 수입니다. </li><li>**설치된 총 앱** 수는 조직 내에 설치된 총 앱 수입니다. 모든 설치 메트릭의 시작 날짜는 2021년 10월입니다. 해당 날짜 이후에 설치된 앱만 계산됩니다.</li></ul> 차트는 선택한 기간 내에 매일 조직 전체에서 집계된 메트릭을 보여 줍니다. 예를 들어 1월 28일 및 메트릭 **활성 타사 앱을** 선택하는 경우 차트에는 조직 내에서 1월 28일에 사용된 총 타사 앱 수가 표시됩니다.  |
|**5**   |이 표에서는 각 앱의 사용 현황을 분석합니다. <ul><li>**앱 ID는 앱** 매니페스트에 있는 외부 앱 식별자입니다. <br/>앱에 대한 자세한 내용은 [Teams 관리 센터의 앱 관리 섹션에서](/microsoftteams/manage-apps) 이 외부 앱 ID를 사용하여 참조하여 찾을 수 있습니다.</li> <li>**앱 이름은 앱** 매니페스트에 있는 것처럼 이 애플리케이션의 이름입니다. </li> <li>**게시** 자는 앱 매니페스트에 있는 것처럼 이 애플리케이션의 게시자입니다. 전역 스토어에 게시된 앱에서만 사용할 수 있습니다.</li> <li>**이 앱을 사용하는 Teams** 는 이 앱을 사용하는 사용자가 한 명 이상 있는 고유한 Teams 팀의 수입니다. </li><li>**이 앱을 사용하는 사용자는 이 앱을** 사용하는 조직의 고유 사용자 수입니다.</li> <li>**Windows에서 사용되는** 앱은 조직의 한 명 이상의 사용자가 Windows에서 사용되었는지 여부를 나타냅니다.</li><li>**Mac에서 사용되는** 앱은 조직에서 하나 이상의 사용자가 MAC에서 사용되었는지 여부를 나타냅니다.</li><li>**웹에서 사용되는** 앱은 조직에서 하나 이상의 사용자가 웹에서 사용되었는지 여부를 나타냅니다. </li> <li>**마지막으로 사용한 날짜** 는 조직의 모든 사용자가 해당 앱을 마지막으로 사용한 날짜입니다. </li></ul> |
|**6**   |**열 편집을** 선택하여 테이블에서 열을 추가하거나 제거합니다.|
|**7**   |오프라인 분석을 위해 보고서를 CSV 파일로 내보냅니다. **Excel로 내보내기 아이콘을** 선택하면 보고서가 브라우저 내에서 다운로드됩니다.|
|**8** |위쪽 그래프에 표시되는 시계열 데이터는 전체 테넌트에 대해 집계된 다양한 사용 메트릭을 보여 줍니다.|
|**9** |하위 절반에 표시되는 테이블 형식 데이터는 팀별로 집계된 다양한 사용 메트릭을 보여 줍니다.|


## <a name="managing-apps-in-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터에서 앱 관리

Teams 앱을 관리하는 방법에 대한 자세한 내용은 [Microsoft Teams의 앱 정보를](/microsoftteams/deploy-apps-microsoft-teams-landing-page.md) 참조하세요.

이 보고서의 앱을 Microsoft Teams 관리 센터의 앱 관리 환경에 연결하려면 다음을 사용할 수 있습니다.

- 앱 이름
- 외부 앱 ID

외부 앱 ID는 스토어 앱에 대한 앱 관리 페이지의 ID와 동일합니다. LOB 앱의 경우 [Teams 관리 센터 열 설정의 앱 관리 섹션에서](/microsoftteams/manage-apps) **외부 앱 ID** 열을 사용하도록 설정할 수 있습니다. 사용자 지정 LOB 앱의 앱 세부 정보 페이지에서 볼 수도 있습니다.

## <a name="related-articles"></a>관련 기사

- [Teams 분석 및 보고](teams-reporting-reference.md)
