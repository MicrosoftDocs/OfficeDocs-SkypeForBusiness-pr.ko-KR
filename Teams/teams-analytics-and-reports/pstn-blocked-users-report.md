---
title: Microsoft Teams PSTN 차단 사용자 보고서
author: CarolynRowe
ms.author: crowe
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
description: Microsoft Teams 관리 센터의 PSTN 차단 사용자 보고서를 사용하여 PSTN 호출이 차단된 조직의 Teams 사용자에 대한 개요를 확인할 수 있습니다.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d689d2696a20f51e232a581d45032d55da6deb6d
ms.sourcegitcommit: 4d88637f510a78d5709d1213c3e285d83a022014
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/14/2022
ms.locfileid: "66794146"
---
# <a name="microsoft-teams-pstn-blocked-users-report"></a>Microsoft Teams PSTN 차단 사용자 보고서

Microsoft Teams 관리 센터의 PSTN 차단 사용자 보고서에는 Teams에서 PSTN 호출이 차단된 조직의 사용자가 표시됩니다. 할당된 전화 번호 및 통화가 차단된 이유를 포함하여 차단된 각 사용자에 대한 자세한 정보를 볼 수 있습니다.

## <a name="view-the-pstn-blocked-users-report"></a>PSTN 차단 사용자 보고서 보기

Microsoft Teams 관리 센터의 왼쪽 탐색 영역에서 **분석 & 보고서** > **사용 현황 보고서를** 클릭합니다. **보고서 보기** 탭의 **보고서** 아래에서 **PSTN 차단 사용자를** 선택한 다음 **보고서 실행을** 클릭합니다.

![관리 센터의 PSTN 차단 사용자 보고서 보고서 스크린샷](../media/teams-reports-pstn-blocked-users-with-callouts.png "번호가 매겨진 설명선이 있는 Microsoft Teams 관리 센터의 PSTN 차단 사용자 보고서 스크린샷")

## <a name="interpret-the-report"></a>보고서 해석

|설명선 |설명  |
|--------|-------------|
|**1**   |각 보고서에는 생성된 날짜가 있습니다. 보고서는 일반적으로 활동 시간으로부터 24~48시간의 대기 시간을 반영합니다. |
|**2**   |X축은 날짜입니다. Y축은 사용자 수입니다. <br>지정된 날짜의 점 위로 마우스를 가져가서 해당 날짜에 차단된 사용자 수를 확인합니다. |
|**3**   |이 표에서는 PSTN 호출이 차단된 모든 사용자를 분석합니다.  전화 시스템 또는 오디오 회의가 할당된 모든 사용자를 표시하고 각 사용자에 대한 자세한 정보를 제공합니다. <ul><li>**표시 이름은** 사용자의 표시 이름입니다. 표시 이름을 클릭하여 Microsoft Teams 관리 센터의 사용자 설정 페이지로 이동합니다. </li> <li>**전화** 는 사용자에게 할당된 번호입니다.</li> <li>**차단된 이유는** 사용자가 호출을 차단한 이유입니다.</li><li>**차단된 작업은**  사용자가 Teams에서 PSTN 호출을 수행하지 못하도록 차단 또는 차단 해제되었는지 여부를 알려줍니다.</li> <li>**차단된 시간은** 사용자가 호출을 차단한 날짜 및 시간(UTC)입니다.</li></li> </ul>테이블에서 원하는 정보를 보려면 테이블에 열을 추가해야 합니다. |
|**4**   |**열 편집을** 선택하여 테이블에서 열을 추가하거나 제거합니다.|
|**5**   |**전체 화면을** 선택하여 전체 화면 모드에서 보고서를 봅니다.|

## <a name="related-topics"></a>관련 주제

- [Teams 분석 및 보고](teams-reporting-reference.md)