---
title: Microsoft 팀 앱 사용 보고서
author: LolaJacobsen
ms.author: lolaj
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
description: Microsoft 팀 관리 센터에서 팀 앱 사용 현황 보고서를 사용 하는 방법에 대해 알아봅니다.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1a5d5c1bdb5b5bbe58ecdb90721ce24bd0081a65
ms.sourcegitcommit: a73df97a06ea860bfaf5387e0acbf3c724697e14
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2020
ms.locfileid: "44902364"
---
# <a name="microsoft-teams-app-usage-report"></a>Microsoft 팀 앱 사용 보고서

Microsoft 팀 관리 센터의 팀 앱 사용 보고서에서는 팀에서 사용 중인 앱에 대 한 정보를 제공 합니다.  

## <a name="view-the-app-usage-report"></a>앱 사용 현황 보고서 보기

1.  관리 센터의 왼쪽 탐색 창에서 <https://teams.admin.microsoft.com> **분석 & 보고서** \> **사용 현황 보고서**를 클릭 합니다. 보고서 **보기** 탭의 **보고서**에서 **앱 사용**을 선택 합니다.

     :::image type="content" source="media/app-usage-report1.png" alt-text="사용 현황 보고서 메뉴 항목의 스크린샷":::

2.  **날짜 범위**아래에서 범위를 선택 하 고 **보고서 실행**을 클릭 합니다.

      :::image type="content" source="media/app-usage-report2.png" alt-text="앱 사용 현황 보고서 스크린샷":::

## <a name="interpret-the-report"></a>보고서 해석

|호출 |설명  |
|--------|-------------|
|**1**   |팀 앱 사용 보고서는 지난 7, 30 또는 90 일 동안의 추세에 대해 볼 수 있습니다. |
|**2**   |각 보고서에는 보고서가 생성 된 날짜를 포함 합니다. 일반적으로이 보고서는 앱을 연 시점부터 24 시간 대기 시간을 반영 합니다. <br><br>![날짜 범위가 표시 된 앱 사용 현황 보고서의 스크린샷](media/app-usage-report3.png)|
|**3**    | <ul><li>차트의 X 축은 특정 보고서에 대해 선택 된 날짜 범위입니다.</li><li>Y 축은 차트에서 가리킨 날짜에 대 한 사용자 수 이며, 해당 사용자가 앱을 적어도 한 번만 연 다음 활성 사용자로 간주 하 고 마우스를 올려 놓은 총 부분을 향해 처리 됩니다.</li></ul>|
|**4(tcp/ipv4)**   |지정 된 날짜의 앱 사용을 나타내는 점을 마우스로 가리켜 해당 앱의 총 활성 사용자 인스턴스 수를 해당 날짜에 표시 합니다.  |
|**5mb**   |모든 앱이 포함 되지만 필터 아이콘을 선택 하면 추가 필터를 사용할 수 있습니다.  |
|**26**   |표에서는 활성 사용자와 팀을 분석 하 여 앱 이름을 제공 합니다.<br><ul><li>**앱 이름은** 팀에 사용 되는 앱의 표시 이름입니다.</li><li>**활성 사용자** 는 지정 된 기간 동안 적어도 한 번 앱을 연 사용자의 수입니다.</li><li>**앱 유형은** "Microsoft" 또는 "타사"의 정적 값입니다.</li><li>**활성 팀** 은 팀의 구성원 한 명 이상과 지정 된 기간 동안 앱을 연 팀의 수입니다.</li><li>**Publisher** 는 앱의 소프트웨어 게시자입니다.</li><li>**버전** 은 앱 게시자에서 앱의 소프트웨어 버전입니다.</li></ul><br>![앱 사용 현황 보고서 스크린샷](media/app-usage-report4.png)  |
|**7**  |**열 편집** 을 선택 하 여 테이블에 열을 추가 하거나 제거 합니다.<br><br>![열 편집 페이지의 스크린샷](media/app-usage-report5.png)  |
|**20cm(8**  |오프 라인 분석을 위해 보고서를 CSV 파일로 내보낼 수 있습니다. **Excel로 내보내기를**클릭 한 다음 **다운로드** 탭에서 **다운로드** 를 클릭 하 여 준비 된 보고서를 다운로드 합니다.<br>![다운로드 페이지 스크린샷](media/app-usage-report7.png)  |
|**되었는지**   |Excel에서 보고서를 볼 때 앱 ID를 나타내는 **Id** 열이 표시 됩니다. 팀 ID는 일반적으로 영숫자 문자열입니다. **Id** 열에 * * \n * * * *가 표시 되는 경우 사용자가 삭제 될 정보를 요청 했음을 의미 합니다.<br>![다운로드 한 Excel 보고서 스크린샷](media/app-usage-report8.png)  |

## <a name="related-topics"></a>관련 항목

- [팀 분석 및 보고](teams-reporting-reference.md)