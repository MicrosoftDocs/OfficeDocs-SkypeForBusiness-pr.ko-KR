---
title: Microsoft 팀 PSTN으로 차단 된 사용자 보고서
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-rifer
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
MS.collection:
- M365-voice
description: Microsoft 팀 관리 센터의 PSTN 차단 사용자 보고서를 사용 하 여 PSTN 통화를 차단 하는 조직의 팀 사용자에 대 한 개요를 얻을 수 있습니다.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e6055533138f08bafbdc9c39b03350612075840f
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43140689"
---
# <a name="microsoft-teams-pstn-blocked-users-report"></a>Microsoft 팀 PSTN으로 차단 된 사용자 보고서

Microsoft 팀 관리 센터의 PSTN 차단 사용자 보고서에는 팀에서 PSTN 통화를 할 수 없도록 차단 된 조직의 사용자가 표시 됩니다. 지정 된 전화 번호를 포함 하 여 차단 된 각 사용자에 대 한 자세한 정보와 전화를 거는 차단 이유를 볼 수 있습니다.

## <a name="view-the-report"></a>보고서 보기

Microsoft 팀 관리 센터의 왼쪽 탐색 모음에서 **분석 & 보고서** > **사용 현황 보고서**를 클릭 합니다. **보고서 보기** 탭의 **보고서**에서 **PSTN 차단 된 사용자**를 선택한 다음 **보고서 실행**을 클릭 합니다.

![관리 센터의 PSTN 차단 사용자 보고서 보고서 스크린샷](../media/teams-reports-pstn-blocked-users-with-callouts.png "Microsoft 팀 관리 센터에서 번호가 매겨진 설명선이 포함 된 PSTN 차단 사용자 보고서 스크린샷")

## <a name="interpret-the-report"></a>보고서 해석

|호출 |Description  |
|--------|-------------|
|**1**   |각 보고서에는 생성 된 날짜를 포함 합니다. 일반적으로이 보고서에는 활동 시간부터 24 ~ 48 시간 대기 시간이 반영 됩니다. |
|**2**   |X 축은 날짜입니다. Y 축은 사용자 수입니다. <br>지정 된 날짜의 점을 마우스로 가리켜 해당 날짜에 대해 차단 된 사용자 수를 확인 합니다. |
|**3**   |이 표는 PSTN 통화를 차단 하는 모든 사용자의 분석 결과를 제공 합니다.  전화 시스템 또는 오디오 회의가 할당 된 모든 사용자를 보여 주고 각 사용자에 대 한 자세한 정보를 제공 합니다. <ul><li>**표시 이름은** 사용자의 표시 이름입니다. 표시 이름을 클릭 하 여 Microsoft 팀 관리 센터의 사용자 설정 페이지로 이동할 수 있습니다. </li> <li>**Phone** 은 사용자에 게 할당 된 번호입니다.</li> <li>**차단 된 이유** 는 사용자가 전화를 거는 것을 차단 하는 이유입니다.</li><li>**차단 된 작업** 은 사용자가 팀에서 PSTN 호출을 차단 또는 해제 했는지 여부를 알려줍니다.</li> <li>**차단 된 시간은** 사용자가 전화를 걸 수 없도록 차단 된 날짜 및 시간 (UTC)입니다.</li></li> </ul>표에 원하는 정보를 표시 하려면 표에 열을 추가 해야 합니다. |
|**4(tcp/ipv4)**   |**열 편집** 을 선택 하 여 테이블에 열을 추가 하거나 제거 합니다.|
|**5mb**   |전체 화면 모드에서 보고서를 보려면 **full screen** 을 선택 합니다.|

## <a name="related-topics"></a>관련 항목

- [팀 분석 및 보고](teams-reporting-reference.md)