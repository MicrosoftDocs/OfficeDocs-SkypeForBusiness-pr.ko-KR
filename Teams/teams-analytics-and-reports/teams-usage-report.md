---
title: Microsoft Teams 사용 현황 보고서
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kojika
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Microsoft Teams 관리 센터에서 Teams 사용 현황 보고서를 사용하여 조직의 Teams 활동에 대한 개요를 확인하려면 어떻게 하세요.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 993c1b124737a0f335e9c9b1e720af72fcc88a8e
ms.sourcegitcommit: 93d84e172cb4b19acde4b8bae9b77efe96c44c00
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122258"
---
# <a name="microsoft-teams-usage-report"></a>Microsoft Teams 사용 현황 보고서

Microsoft Teams 관리 센터의 Teams 사용 현황 보고서에서는 활성 사용자 및 채널 수를 포함하여 Teams의 사용 활동에 대한 개요를 제공하면 조직의 사용자가 Teams를 사용하여 통신하고 공동 작업하는 횟수를 빠르게 확인할 수 있습니다. 각 팀의 활성 사용자 및 채널, 게스트 및 메시지 수를 포함하여 팀의 사용 현황 정보를 볼 수 있습니다.

## <a name="view-the-usage-report"></a>사용 현황 보고서 보기

1. Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 Analytics & **보고서를**  >  **클릭합니다.** 보고서 **보기 탭의** **보고서에서** **Teams 사용량을 선택합니다.**
2. 날짜 **범위에서** 범위를 선택한 다음 보고서 **실행을 클릭합니다.**

    ![설명선이 있는 Teams 관리 센터의 Teams 사용 현황 보고서 스크린샷](../media/teams-reports-teams-usage-with-callouts.png "설명선이 있는 Teams 관리 센터의 Teams 사용 현황 보고서 스크린샷")

## <a name="interpret-the-report"></a>보고서 해석

|Callout |설명  |
|--------|-------------|
|**1**   |Teams 사용 활동 보고서에서 지난 7일, 30일 또는 90일간의 추세를 볼 수 있습니다. |
|**2**   |각 보고서에는 이 보고서가 생성된 날짜가 있습니다. 보고서는 일반적으로 활동 시간으로부터 24~48시간의 대기 시간을 반영합니다. |
|**3**   |<ul><li>차트의 X축은 보고서에 대해 선택한 날짜 범위입니다.</li> <li> Y축은 활성 항목 또는 활동의 수입니다.</li> </ul>주어진 날짜의 항목 또는 활동을 나타내는 점 위에 마우스를 대면 해당 날짜에 해당 항목 또는 활동의 인스턴스 수를 볼 수 있습니다.|
|**4**   |범례의 항목을 클릭하여 차트에 표시하는 항목을 필터링할 수 있습니다. 예를 들어 총 활성 사용자 **수,** Teams & **채널** 활성  **사용자,** 활성 채널 또는 메시지를 클릭하여 각 사용자와 관련된 정보만 볼 수 있습니다. 이 선택을 변경해도 표의 정보는 변경되지 않습니다. |
|**5**   |이 표에서는 팀별 사용 현황을 분석합니다. <ul><li>**팀 이름은** 팀의 표시 이름입니다. 팀 이름을 클릭하여 Microsoft Teams 관리 센터의 팀 설정 페이지로 이동하면 됩니다. </li> <li>**개인** 정보 보호는 팀이 비공개 팀인지 아니면 공개 팀인지를 말합니다.</li> <li>**활성 사용자는** 지정된 기간에 팀의 활성 사용자 수입니다.</li><li>**게스트는** 지정된 기간에 팀의 게스트 수입니다.</li> <li>**활성 채널은** 지정된 기간에 활성 사용자가 하나 이상 있는 채널의 수입니다.</li> <li>**메시지 게시는** 지정된 기간에 채널의 모든 게시물 메시지 수입니다.</li> <li>**회신 메시지는** 지정된 기간에 채널의 모든 회신 메시지 수입니다.</li> <li>**구성되는** 모임은 지정된 기간 동안 사용자가 구성한 예약된 모임 및 애드워즈 모임의 수입니다. </li><li>**긴급 메시지는** 지정된 기간에 있는 모든 긴급 메시지의 수입니다.</li><li>**반응은** 지정된 기간에 메시지에 대한 모든 반응의 수입니다.</li><li>**Mentions는** 지정된 기간에 메시지에 사용된 모든 언급의 수입니다.</li><li>**채널 메시지는** 팀 사용자가 지정된 기간 동안 팀 채팅에 게시한 고유 메시지 수입니다.</li> </li> </ul>사용자 계정이 Azure AD에 더 이상 없는 경우 사용자 이름은 테이블에 "--"로 표시됩니다. <br><br>표에서 원하는 정보를 확인하려는 경우 테이블에 열을 추가해야 합니다. |
|**6**   |열 **편집을 선택하여** 표에서 열을 추가하거나 제거합니다.|
|**7**   |오프라인 분석을 위해 보고서를 CSV 파일로 내보낼 수 있습니다. **Excel로 내보내기를** 클릭한  다음 다운로드 탭에서 다운로드를 클릭하여 준비가 되면 보고서를 다운로드합니다. <br><br>![다운로드할 내보낼 보고서를 보여주는 다운로드 탭의 스크린샷](../media/teams-reports-export-to-csv.png)|

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="related-topics"></a>관련 항목

- [Teams 분석 및 보고](teams-reporting-reference.md)
