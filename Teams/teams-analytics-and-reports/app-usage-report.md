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
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Microsoft Teams 관리 센터에서 Teams 앱 사용 현황 보고서를 사용하는 방법을 알아봅니다.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a8ef86a0387c3966b795c323d1c28d0e1ca788e1
ms.sourcegitcommit: e102d72e67ab1c440c29ae6a048fc2cf8545fe01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2022
ms.locfileid: "65217952"
---
# <a name="microsoft-teams-app-usage-report"></a>Microsoft Teams 앱 사용 현황 보고서

Microsoft Teams 관리 센터의 Teams 앱 사용 현황 보고서는 사용자가 Teams 사용하는 앱에 대한 정보를 제공합니다.  

## <a name="view-the-app-usage-report"></a>앱 사용 현황 보고서 보기

1. 관리 센터의 왼쪽 탐색 영역에서 <https://admin.teams.microsoft.com>**Analytics &** **reportsUsage** >  보고서를 클릭합니다.<br><br>![사용 현황 보고서 메뉴 항목의 스크린샷](media/app-usage-report1.png "사용 현황 보고서 메뉴 항목의 스크린샷")
2. **보고서 보기** 탭의 **보고서** 아래에서 **앱 사용량을** 선택합니다.

3. **날짜 범위** 에서 범위를 선택한 다음 **보고서 실행을** 클릭합니다. Teams 앱 사용 현황 보고서는 지난 7일, 30일 또는 90일 동안의 추세를 볼 수 있습니다.<br><br>![앱 사용 현황 보고서의 스크린샷.](media/app-usage-report2.png "앱 사용 현황 보고서의 스크린샷.")


## <a name="interpret-the-report"></a>보고서 해석

:::image type="content" alt-text="설명선이 있는 Teams 관리 센터의 Teams 앱 사용 현황 보고서 스크린샷" source="media/app-usage-report5.png" lightbox="media/app-usage-report5.png":::

각 보고서에는 보고서가 만들어진 시점을 보여 주는 날짜가 왼쪽 위에 있습니다. 보고서는 일반적으로 앱이 열린 시점의 24시간 대기 시간을 반영합니다.

차트의 Y축은 차트를 마우스로 가리켜 선택한 날짜에 대해 앱을 한 번 이상 열었기 때문에 활성 사용자로 간주되는 사용자 수입니다.

차트의 X축은 보고서에 대해 선택한 날짜 범위입니다.

날짜에 앱의 사용량을 나타내는 점(4)을 마우스로 가리키면 해당 날짜에 해당 앱의 활성 사용자 총 수가 표시됩니다.

다른 앱을 선택하려면 오른쪽 위에서 **필터** 아이콘(5)을 클릭하고 새 조건을 선택하거나 입력한 다음 **적용** 을 클릭합니다.

보고서 맨 아래에 있는 테이블(6)에는 앱 이름으로 활성 사용자 및 팀이 표시됩니다.

   - **앱 이름은** Teams 사용되는 앱의 표시 이름입니다.
   - **활성 사용자는** 지정된 기간 동안 앱을 한 번 이상 연 사용자 수입니다.
   - **앱 유형** 은 "Microsoft" 또는 "타사"의 정적 값입니다.
   - **활성 팀은** 한 명 이상의 팀원이 지정된 기간 동안 앱을 연 팀의 수입니다.
   - **Publisher** 앱의 소프트웨어 게시자입니다.
   - **버전은** 앱 게시자의 앱 소프트웨어 버전입니다.

   > [!NOTE]
   > **활성 사용자** 및 **활성 팀은** 채널에서만 사용되는 앱에 대해 계산됩니다.

표에서 열을 추가하거나 제거하려면 오른쪽 위에서 **열 편집** 아이콘(7)을 클릭하고 **열 편집** 탭에서 새 조건을 선택한 다음 **적용** 을 클릭합니다.

오프라인 분석을 위해 CSV 파일로 보고서를 내보내려면 오른쪽 위에서 **Excel 내보내기** 아이콘(8)을 선택한 다음 **상태** 아래 **의 다운로드** 탭에서 **다운로드** 를 클릭합니다.

   :::image type="content" alt-text="다운로드 창의 스크린샷." source="media/app-usage-report7.png" lightbox="media/app-usage-report7.png":::

Excel 보고서를 보면 앱 ID(일반적으로 영숫자 문자열)를 나타내는 **ID** 열도 표시됩니다. **ID** 가 **\n** 경우 사용자가 해당 정보를 삭제하도록 요청했음을 의미합니다.

   ![다운로드한 Excel 보고서의 스크린샷.](media/app-usage-report8.png "다운로드한 Excel 보고서의 스크린샷.")

## <a name="related-topics"></a>관련 항목

- [Teams 분석 및 보고](teams-reporting-reference.md)
