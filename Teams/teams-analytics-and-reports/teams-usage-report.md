---
title: Microsoft 팀 사용 보고서
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: Microsoft 팀 관리 센터에서 팀 사용 보고서를 사용 하 여 조직의 팀 활동에 대 한 개요를 확인 하는 방법에 대해 알아봅니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: d530ba8009cd113354a511b61589b409958ec276
ms.sourcegitcommit: a5cde2df1aceed9d919ef53281dd0d75f1f5e183
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/29/2019
ms.locfileid: "36667121"
---
# <a name="microsoft-teams-usage-report"></a>Microsoft 팀 사용 보고서

Microsoft 팀 관리 센터의 팀 사용 보고서에서는 활성 사용자 및 채널 수를 비롯 한 팀의 사용 현황 작업에 대 한 개요를 제공 하므로 조직에서 팀을 사용 하 여 통신 하는 사용자 수를 빠르게 확인할 수 있습니다. 사람들과. 각 팀의 활성 사용자 및 채널, 게스트 및 메시지 수를 비롯 한 팀의 사용 정보를 볼 수 있습니다.

## <a name="view-the-report"></a>보고서 보기

1. Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **분석 & 보고서**를 클릭 한 다음 **보고서**에서 **팀 사용량**을 선택 합니다.
2. **날짜 범위**아래에서 범위를 선택 하 고 **보고서 실행**을 클릭 합니다.

![팀 관리 센터에서 설명선이 포함 된 팀 사용 보고서 스크린샷] (../media/teams-reports-teams-usage-with-callouts.png "팀 관리 센터에서 설명선이 포함 된 팀 사용 보고서 스크린샷")

## <a name="interpret-the-report"></a>보고서 해석

|호출 |설명  |
|--------|-------------|
|**raid-1**   |팀 사용 활동 보고서는 지난 7 일 또는 28 일간의 추세에 대해 볼 수 있습니다. |
|**2**   |각 보고서에는이 보고서가 생성 된 날짜에 대 한 날짜가 있습니다. 일반적으로이 보고서에는 활동 시간부터 24 ~ 48 시간 대기 시간이 반영 됩니다. |
|**3-4**   |<ul><li>차트의 X 축은 보고서에 대해 선택 된 날짜 범위입니다.</li> <li> Y 축은 활성 항목 또는 활동의 수입니다.</li> </ul>지정 된 날짜에 항목이 나 활동을 나타내는 점을 가리켜 해당 항목 또는 해당 날짜에 대 한 활동의 인스턴스 수를 확인 합니다.|
|**4(tcp/ipv4)**   |범례에서 항목을 클릭 하 여 차트에 표시 되는 내용을 필터링 할 수 있습니다. 예를 들어 **총 활성 사용자**, **팀 & 채널 활성 사용자**, **활성 채널**또는 **메시지** 를 클릭 하 여 각 항목에 관련 된 정보만 표시 합니다. 이 선택을 변경 해도 표의 정보는 변경 되지 않습니다. |
|**5mb**   |이 표는 팀의 사용량을 분류 하 여 보여 줍니다. <ul><li>**팀 이름은** 팀의 표시 이름입니다. 팀 이름을 클릭 하 여 Microsoft 팀 관리 센터의 팀 설정 페이지로 이동할 수 있습니다. </li> <li>**개인 정보** 는 팀이 비공개 팀 인지 또는 공용 팀 인지를 나타냅니다.</li> <li>**활성 사용자** 는 지정 된 기간에 팀의 활성 사용자 수입니다.</li><li>**게스트** 는 지정 된 기간에 팀의 게스트 수입니다.</li> </li> </ul>사용자 계정이 더 이상 Azure AD에 존재 하지 않는 경우에는 테이블에 사용자 이름이 "--"로 표시 됨을 참고 하세요. <br><br>표에 원하는 정보를 표시 하려면 표에 열을 추가 해야 합니다. |
|**26**   |**열 편집** 을 선택 하 여 테이블에 열을 추가 하거나 제거 합니다.|
|**7**   |오프 라인 분석을 위해 보고서를 CSV 파일로 내보낼 수 있습니다. **Excel로 내보내기를**클릭 한 다음 **다운로드** 탭에서 **다운로드** 를 클릭 하 여 준비 된 보고서를 다운로드 합니다.<br><br>![내보낸 보고서를 다운로드 하 여 표시 하는 다운로드 탭 스크린샷](../media/teams-reports-export-to-csv.png)|

## <a name="related-topics"></a>관련 항목

- [팀 분석 및 보고](teams-reporting-reference.md)
