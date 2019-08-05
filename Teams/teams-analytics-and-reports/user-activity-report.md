---
title: Microsoft 팀 사용자 활동 보고서
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: Microsoft 팀 관리 센터에서 팀 사용자 활동 보고서를 사용 하 여 조직의 사용자가 팀을 사용 하는 방법을 확인 하는 방법에 대해 알아봅니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: b1d152657dc658e6b10da5da3147dd4a695383b7
ms.sourcegitcommit: 5791b98589e64df2e2bcd96f05fd2f869a65861f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2019
ms.locfileid: "36184616"
---
# <a name="microsoft-teams-user-activity-report"></a>Microsoft 팀 사용자 활동 보고서

팀 사용자 활동 보고서는 조직의 사용자가 팀에서 수행 하는 활동 유형에 대 한 통찰력을 제공 합니다. 예를 들어 1:1 통화를 통해 통신 하는 사용자의 수, 채널 메시지를 통해 통신 하는 사용자 수, 개인 채팅 메시지에 참가 하는 사용자의 수를 확인할 수 있습니다.

![팀 사용자 활동 보고서] 스크린샷 (../media/teams-reports-user-activity.png "Microsoft 팀 관리 센터의 팀 사용자 활동 보고서 스크린샷")

## <a name="view-the-report"></a>보고서 보기

1. Microsoft 팀 관리 센터로 이동 하 고 왼쪽 탐색 창에서 **분석 & 보고서**를 클릭 한 다음 **보고서**에서 **팀 사용자 활동**을 선택 합니다. 
2. **날짜 범위**아래에서 범위를 선택 하 고 **보고서 실행**을 클릭 합니다. 

## <a name="interpret-the-report"></a>보고서 해석

![번호가 매겨진 설명선이 있는 팀 사용자 활동 보고서 스크린샷] (../media/teams-reports-user-activity-with-callouts.png "번호가 매겨진 설명선이 있는 Microsoft 팀 관리 센터의 팀 사용자 활동 보고서 스크린샷")

|호출 |설명  |
|--------|-------------|
|**raid-1**   |팀 사용자 활동 보고서는 지난 7 일 또는 28 일 동안의 추세에 대해 볼 수 있습니다. |
|**2**   |각 보고서에는이 보고서가 생성 된 날짜에 대 한 날짜가 있습니다. 일반적으로이 보고서에는 활동 시간부터 24 ~ 48 시간 대기 시간이 반영 됩니다. |
|**3-4**   |<ul><li>차트의 X 축은 특정 보고서에 대해 선택 된 날짜 범위입니다. </li><li>Y 축은 활동에 참가 한 사용자 수입니다.</li></ul>지정 된 날짜의 활동을 나타내는 점을 마우스로 가리켜 해당 활동의 인스턴스 수를 해당 날짜에 표시 합니다. |
|**4(tcp/ipv4)**   |범례에서 항목을 클릭 하 여 차트에 표시 되는 내용을 필터링 할 수 있습니다. 예를 들어 **1:1 통화**, **채널 메시지**또는 **채팅 메시지** 를 클릭 하면 각 항목에 관련 된 정보만 볼 수 있습니다. 선택 영역을 변경 해도 표의 정보는 변경 되지 않습니다. |
|**5mb**   |테이블을 통해 사용자의 사용을 분류 합니다.   <ul><li>**표시 이름은** 사용자의 표시 이름입니다. 표시 이름을 클릭 하 여 Microsoft 팀 관리 센터의 사용자 설정 페이지로 이동할 수 있습니다.</li><li>**1:1 통화** 는 사용자가 지정 된 기간에 참가 한 1:1 통화 수입니다.</li><li>**채널 메시지** 는 사용자가 지정 된 기간에 팀 채팅에 게시 한 고유 메시지 수입니다.</li> <li>**채팅 메시지** 는 사용자가 지정 된 기간 동안 비공개 채팅에 게시 한 고유 메시지 수입니다.</li>  <li>**마지막 활동** 은 사용자가 팀 활동에 참여 한 마지막 날짜 (UTC)입니다.</li> </ul>사용자 계정이 더 이상 Azure AD에 존재 하지 않는 경우에는 테이블에 사용자 이름이 "--"로 표시 됨을 참고 하세요. <br><br>표에 원하는 정보를 표시 하려면 표에 열을 추가 해야 합니다.
|**26**   |**열 편집** 을 선택 하 여 테이블에 열을 추가 하거나 제거 합니다. |
|**7**   |오프 라인 분석을 위해 보고서를 CSV 파일로 내보낼 수 있습니다. **Excel로 내보내기를**클릭 한 다음 **다운로드** 탭에서 **다운로드** 를 클릭 하 여 준비 된 보고서를 다운로드 합니다.<br>![내보낸 보고서를 다운로드 하 여 표시 하는 다운로드 탭 스크린샷](../media/teams-reports-export-to-csv.png) <br>Excel에서 보고서를 볼 때 팀 ID를 나타내는 **Id** 열이 표시 됩니다. 팀 ID는 일반적으로 영숫자 문자열입니다. **Id** 열이 **\n**으로 표시 되는 경우 사용자가 삭제 될 정보를 요청 했음을 의미 합니다. ||

## <a name="related-topics"></a>관련 항목
- [팀 분석 및 보고](teams-reporting-reference.md)