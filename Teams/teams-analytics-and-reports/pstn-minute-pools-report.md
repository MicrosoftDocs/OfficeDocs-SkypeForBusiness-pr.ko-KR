---
title: Microsoft 팀 PSTN 통화 시간 풀 보고서
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
description: Microsoft 팀 관리 센터에서 팀 PSTN 통화 시간 단위 보고서를 사용 하 여 현재 월에 조직 내에서 사용 된 분을 확인 하는 방법을 알아보세요.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d00e6f76258caad7899ddd589e037718928741e0
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43904900"
---
# <a name="microsoft-teams-pstn-minute-pools-report"></a>Microsoft 팀 PSTN 통화 시간 풀 보고서

Microsoft 팀 관리 센터의 팀 PSTN 통화 시간 단위 보고서에는 현재 달 중 사용 된 시간의 수를 표시 하 여 조직의 오디오 회의 및 착신 작업에 대 한 개요가 제공 됩니다. 통화에 사용 된 라이선스, 사용 가능한 총 시간 (분), 사용한 시간, 위치 기준으로 라이선스 사용량을 비롯 한 작업 분석을 확인할 수 있습니다.

## <a name="view-the-pstn-minute-pools-report"></a>PSTN 시간 풀 보고서 보기

Microsoft 팀 관리 센터의 왼쪽 탐색 모음에서 **분석 & 보고서** > **사용 현황 보고서**를 클릭 합니다. **보고서 보기** 탭의 **보고서**에서 **PSTN**시간 단위를 선택한 다음 **보고서 실행**을 클릭 합니다.

![관리 센터의 팀 PSTN-은행 시간 단위 보고서의 스크린샷](../media/teams-reports-pstn-minute-pools-with-callouts.png "번호가 매겨진 설명선이 있는 Microsoft 팀 관리 센터의 팀 PSTN 분 단위 보고서의 스크린샷")

## <a name="interpret-the-report"></a>보고서 해석

|호출 |설명  |
|--------|-------------|
|**1**   |각 보고서에는 생성 된 날짜를 포함 합니다. 일반적으로이 보고서에는 활동 시간부터 24 ~ 48 시간 대기 시간이 반영 됩니다. |
|**2**   |권한 (라이선스)을 클릭 하 여 해당 접근 권한 작업을 볼 수 있습니다. |
|**3**   |X 축은 국가 또는 지역입니다. Y 축은 분 수입니다. <br>차트의 막대 위에 마우스를 놓으면 해당 사용 위치에 대 한 활동이 표시 됩니다.  |
|**4(tcp/ipv4)**   |범례에서 항목을 클릭 하 여 차트에 표시 되는 내용을 필터링 할 수 있습니다. 예를 들어 사용 **되지**않음, **국내 사용자**, **데이터 없음**또는 **국제 통화** 를 클릭 하 여 각 항목에 관련 된 정보만 표시 합니다. |
|**5mb**   |표에서는 기능 및 사용 위치 별로 분 단위를 분류 하 여 보여 줍니다. <ul><li>**국가 또는 지역은** 사용 위치입니다. </li><li>**기능 설명은** 통화에 사용 되는 라이선스에 대 한 설명입니다.  이 보고서에 표시 될 수 있는 기능 설명은 다음과 같습니다. <ul><li>국내 및 국제 통화 요금제 (1200 국내 분)</li><li>국내 및 국제 통화 요금제 (3000 국내 분)</li><li>국내 및 국제 전화 요금제 (600 국제 통화)</li></ul></li><br><li>**총 통화** 시간은 해당 월에 사용할 수 있는 총 통화 수입니다.</li><li>**사용 시간 (** 분)은 매달 사용 되는 시간입니다.</li> <li>**사용할 수 있는 시간 (분)** 은 해당 월에 남아 있는 분 수입니다.</li><li>**접근 권한** 값은 통화에 사용 되는 라이선스입니다. 표시 될 수 있는 라이선스는 다음과 같습니다.<ul><li>**MCOPSTNPP** -통신 크레딧</li><li>**MCOPSTN1** -국내 통화 요금제 (3000 min US/1200 최소 EU 요금제)</li><li>**MCOPSTN2** -국제 통화 요금제</li><li>**MCOPSTN5** -국내 통화 요금제 (120 분 통화 요금제)</li><li>**MCOPSTN6** -국내 통화 요금제 (240 분 통화 요금제)</li><li>**Mcomeetadd** 오디오 회의</li><li>**MCOMEETACPEA** -분 당 오디오 회의 결제</li></ul></li> </ul> 표에 원하는 정보를 표시 하려면 표에 열을 추가 해야 합니다.|
|**26**   |**열 편집** 을 선택 하 여 테이블에 열을 추가 하거나 제거 합니다.|
|**7**   |전체 화면 모드에서 보고서를 보려면 **full screen** 을 선택 합니다.|

## <a name="related-topics"></a>관련 항목

- [팀 분석 및 보고](teams-reporting-reference.md)