---
title: Microsoft Teams 앱 사용 보고서
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-quhur
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 관리 센터에서 Teams 앱 사용 보고서를 사용하는 Microsoft Teams 대해 자세히 알아보습니다.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7679652f0cb93e445e72af80307803b1e3197992
ms.sourcegitcommit: b57e19e20900ff02f3196c811bf1dd1acd149c79
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2021
ms.locfileid: "60596215"
---
# <a name="microsoft-teams-app-usage-report"></a>Microsoft Teams 앱 사용 보고서

Teams 관리 센터의 Microsoft Teams 앱 사용 현황 보고서는 사용자가 Teams.  

## <a name="view-the-app-usage-report"></a>앱 사용 보고서 보기

1. 관리 센터의 왼쪽 탐색에서 분석 & <https://admin.teams.microsoft.com> **보고서**  >  **를 클릭합니다.**<br><br>![사용 현황 보고서 메뉴 항목의 스크린샷.](media/app-usage-report1.png "사용 현황 보고서 메뉴 항목의 스크린샷.")
2. 보고서 보기 **탭의** **보고서에서** **앱 사용 을 선택합니다.**

3. **날짜 범위에서** 범위를 선택한 다음 보고서 실행 **을 클릭합니다.** 앱 Teams 최근 7일, 30일 또는 90일 동안의 추세를 볼 수 있습니다.<br><br>![앱 사용 보고서 스크린샷.](media/app-usage-report2.png "앱 사용 보고서 스크린샷.")


## <a name="interpret-the-report"></a>보고서 해석

:::image type="content" alt-text="콜아웃이 있는 Teams 관리 센터의 Teams 앱 사용 보고서 스크린샷." source="media/app-usage-report5.png" lightbox="media/app-usage-report5.png":::

1. 각 보고서에는 보고서가 생성된 날짜가 왼쪽 위에 있습니다. 보고서는 일반적으로 앱이 열리기 전의 24시간 대기 시간을 반영합니다.

2. 차트의 Y축은 앱을 한 번 이상 열기 때문에 차트 위에 마우스를 대어 선택한 날짜에 대해 활성 사용자로 간주되는 사용자 수입니다.

3. 차트의 X 축은 보고서에 대해 선택한 날짜 범위입니다.

4. 모든 날짜에 앱의 사용량을 나타내는 점 위에 마우스를 대고 해당 날짜에 해당 앱의 활성 사용자의 총 수를 볼 수 있습니다.

5. 다른 앱을 선택하려면 오른쪽 위에서 필터 아이콘을 **클릭하고** 새 조건을 선택하거나 입력한 다음 적용을 **클릭합니다.**

6. 보고서 맨 아래에 있는 표에는 앱 이름으로 활성 사용자 및 팀이 표시됩니다.

   - **앱 이름은** 앱에 사용되는 앱의 표시 Teams.
   - **활성 사용자는** 지정된 기간 동안 앱을 한 번 이상 연 사용자 수입니다.
   - **앱 형식은** "Microsoft" 또는 "타사"의 정적 값입니다.
   - **활성 팀은** 지정된 기간 동안 팀 구성원 중 하나 이상이 앱을 열고 있는 팀의 수입니다.
   - **Publisher** 앱의 소프트웨어 게시자입니다.
   - **버전은** 앱 게시자의 소프트웨어 버전입니다.

   > [!NOTE]
   > **활성 사용자** 및 **활성** 팀은 채널에서만 사용되는 앱에 대해 계산됩니다.

7. 표의 열을 추가하거나 제거하려면 오른쪽 위에서  열 편집 아이콘을  클릭하고 열 편집 탭에서 새 조건을 선택한 다음 적용을 **클릭합니다.**

8. 오프라인 분석을 위해 보고서를 CSV 파일로 내보내려면 오른쪽 위에서 내보내기 아이콘을 선택한 다음  Excel 아래 다운로드 **탭에서** **다운로드를** **클릭합니다.**

   :::image type="content" alt-text="다운로드 창의 스크린샷." source="media/app-usage-report7.png" lightbox="media/app-usage-report7.png":::

9. 보고서에서 Excel 앱 ID를 나타내는 ID 열(일반적으로 영수 문자열)도 표시됩니다.  ID가 \n **** 경우 사용자가 해당 정보를 삭제하도록 요청한 것입니다.

   ![다운로드한 보고서의 Excel 스크린샷입니다.](media/app-usage-report8.png "다운로드한 보고서의 Excel 스크린샷입니다.")

## <a name="related-topics"></a>관련 항목

- [Teams 분석 및 보고](teams-reporting-reference.md)
