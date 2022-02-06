---
title: Microsoft Teams PSTN 차단된 사용자 보고서
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-rifer
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
search.appverid: MET150
MS.collection:
  - M365-voice
description: 관리 센터의 PSTN 차단된 Microsoft Teams 보고서를 사용하여 PSTN 호출을 차단하는 조직의 Teams 개요를 확인할 수 있습니다.
appliesto:
  - Microsoft Teams
ms.custom: seo-marvel-apr2020
---
# <a name="microsoft-teams-pstn-blocked-users-report"></a>Microsoft Teams PSTN 차단된 사용자 보고서

관리 센터의 PSTN 차단된 사용자 Microsoft Teams 조직에서 PSTN 호출을 차단한 사용자를 Teams. 할당된 전화 번호와 통화가 차단된 이유를 포함하여 차단된 각 사용자에 대한 자세한 정보를 볼 수 있습니다.

## <a name="view-the-pstn-blocked-users-report"></a>PSTN 차단된 사용자 보고서 보기

관리 센터의 왼쪽 탐색에서 Microsoft Teams **보고서 & 클릭합니다** > . 보고서 **보기 탭** 의 **보고서** 에서 **PSTN** 차단된 사용자를 선택한 다음 보고서 실행 **을 클릭합니다**.

![관리 센터의 PSTN 차단된 사용자 보고서 보고서 스크린샷.](../media/teams-reports-pstn-blocked-users-with-callouts.png "번호 매기기 콜아웃이 있는 Microsoft Teams 관리 센터의 PSTN 차단된 사용자 보고서 스크린샷")

## <a name="interpret-the-report"></a>보고서 해석

|콜아웃 |설명  |
|--------|-------------|
|**1**   |각 보고서에는 생성된 날짜가 있습니다. 보고서는 일반적으로 활동 시간으로부터 24~48시간의 대기 시간을 반영합니다. |
|**2**   |X축은 날짜입니다. Y축은 사용자 수입니다. <br>해당 날짜에 차단된 사용자 수를 표시하기 위해 특정 날짜의 점 위에 마우스를 다. |
|**3**   |표는 PSTN 호출을 차단하는 모든 사용자의 분석 정보를 제공합니다.  할당된 오디오 회의 또는 전화 시스템 모든 사용자를 표시하고 각 사용자에 대한 자세한 정보를 제공합니다. <ul><li>**표시 이름은** 사용자의 표시 이름입니다. 표시 이름을 클릭하여 관리자 센터의 사용자 설정 페이지로 Microsoft Teams 있습니다. </li> <li>**전화** 사용자에게 할당된 숫자입니다.</li> <li>**차단된 이유는** 사용자가 통화를 차단하는 데 차단된 이유입니다.</li><li>**차단된 작업은** 사용자가 PSTN 호출을 차단하거나 차단 해제되어 있는지 여부를 Teams.</li> <li>**차단된 시간은** 사용자가 통화를 차단한 날짜 및 시간(UTC)입니다.</li></li> </ul>표에서 원하는 정보를 확인하려는 경우 테이블에 열을 추가해야 합니다. |
|**4**   |열 **편집을 선택하여** 표에 열을 추가하거나 제거합니다.|
|**5**   |전체 **화면을 선택하여** 전체 화면 모드에서 보고서를 볼 수 있습니다.|

## <a name="related-topics"></a>관련 항목

- [Teams 분석 및 보고](teams-reporting-reference.md)