---
title: Microsoft Teams 앱 사용 현황 보고서
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-quhur
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Microsoft Teams 관리 센터에서 Teams 앱 사용 현황 보고서를 사용하는 방법을 배워야 합니다.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 91af37ed9c19a1d3e8d32cdf296cf32e90818564
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583797"
---
# <a name="microsoft-teams-app-usage-report"></a>Microsoft Teams 앱 사용 현황 보고서

Microsoft Teams 관리 센터의 Teams 앱 사용 현황 보고서는 사용자가 Teams에서 사용하는 앱에 대한 정보를 제공합니다.  

## <a name="view-the-app-usage-report"></a>앱 사용 보고서 보기

1.  관리 센터의 왼쪽 탐색 모음에서 Analytics & <https://admin.teams.microsoft.com> **보고서를** \> **클릭합니다.** 보고서 보기 **탭의** **보고서에서** 앱 **사용 현황을 선택합니다.**

     :::image type="content" source="media/app-usage-report1.png" alt-text="사용 현황 보고서 메뉴 항목의 스크린샷":::

2.  날짜 **범위에서** 범위를 선택한 다음 보고서 **실행을 클릭합니다.**

      :::image type="content" source="media/app-usage-report2.png" alt-text="앱 사용 현황 보고서 스크린샷":::

## <a name="interpret-the-report"></a>보고서 해석

|Callout |설명  |
|--------|-------------|
|**1**   |Teams 앱 사용 현황 보고서에서 지난 7일, 30일 또는 90일간의 추세를 볼 수 있습니다. |
|**2**   |각 보고서에는 보고서가 생성된 날짜가 있습니다. 보고서는 일반적으로 앱을 열 때부터 24시간의 대기 시간을 반영합니다. <br><br>![날짜 범위를 보여주는 앱 사용량 보고서의 스크린샷](media/app-usage-report3.png)|
|**3**    | <ul><li>차트의 X축은 특정 보고서에 대해 선택한 날짜 범위입니다.</li><li>Y축은 주어진 날에 차트에 마우스를 놓은 사용자 수로, 해당 사용자가 앱을 한 번 이상 열고 활성 사용자로 간주하여 마우스로 마우스를 놓을 때의 합계에 누적됩니다.</li></ul>|
|**4**   |주어진 날짜에 앱 사용량을 나타내는 점 위에 마우스를 대면 해당 날짜에 해당 앱의 총 활성 사용자 수를 볼 수 있습니다.  |
|**5**   |모든 앱이 포함되지만 필터 아이콘을 선택하면 추가 필터를 사용할 수 있습니다.  |
|**6**   |이 표에서는 앱 이름으로 활성 사용자 및 팀을 분석합니다.<br><ul><li>**앱 이름은** Teams에서 사용되는 앱의 표시 이름입니다.</li><li>**활성 사용자는** 지정된 기간 동안 앱을 한 번 이상 연 사용자 수입니다.</li><li>**앱 유형은** "Microsoft" 또는 "타사"의 정적 값입니다.</li><li>**활성 팀은** 지정된 기간 동안 하나 이상의 팀 구성원이 앱을 연 팀의 수입니다.</li><li>**Publisher는** 앱의 소프트웨어 게시자입니다.</li><li>**버전은** 앱 게시자가 제공한 앱의 소프트웨어 버전입니다.</li></ul><br>![앱 사용 현황 보고서 스크린샷](media/app-usage-report4.png)  |
|**7**  |열 **편집을 선택하여** 표에서 열을 추가하거나 제거합니다.<br><br>![열 편집 페이지의 스크린샷](media/app-usage-report5.png)  |
|**8**  |오프라인 분석을 위해 보고서를 CSV 파일로 내보낼 수 있습니다. **Excel로 내보내기를** 클릭한  다음 다운로드 탭에서 다운로드를 클릭하여 준비가 되면 보고서를 다운로드합니다. <br>![다운로드 페이지의 스크린샷](media/app-usage-report7.png)  |
|**9**   |Excel에서 보고서를 볼 때 앱 **ID를** 나타내는 ID 열도 표시됩니다. 팀 ID는 일반적으로 영문자 문자열입니다. ID **열이** **\n****로 표시되면 사용자가 해당 정보를 삭제하도록 요청한 것입니다.<br>![다운로드한 Excel 보고서의 스크린샷](media/app-usage-report8.png)  |

## <a name="related-topics"></a>관련 항목

- [Teams 분석 및 보고](teams-reporting-reference.md)