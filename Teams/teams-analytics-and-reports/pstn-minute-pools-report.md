---
title: Microsoft Teams PSTN 분 풀 보고서
author: serdarsoysal
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
description: 관리 센터에서 Teams PSTN 분 풀 보고서를 사용하여 Microsoft Teams 조직 내에서 사용 중인 분을 보는 방법
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ef2e207352bf4ad7ee3d0f6c8fae674c4022e0b0
ms.sourcegitcommit: cfc48dc03550c093c4405fb5984648188f523699
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2021
ms.locfileid: "60045994"
---
# <a name="microsoft-teams-pstn-minute-pools-report"></a>Microsoft Teams PSTN 분 풀 보고서

Teams 관리 센터의 Microsoft Teams PSTN 분 풀 보고서는 현재 달에 소비된 분 수를 표시하여 조직의 오디오 회의 및 통화 활동에 대한 개요를 제공합니다. 통화에 사용되는 라이선스, 사용 가능한 총 분, 사용 분 및 위치별 라이선스 사용량을 포함하여 활동의 분석 정보를 볼 수 있습니다.

## <a name="view-the-pstn-minute-pools-report"></a>PSTN 분 풀 보고서 보기

관리 센터의 왼쪽 탐색에서 Microsoft Teams 분석 &  >  **보고서 를 클릭합니다.** 보고서 **보기** 탭의 **보고서에서** **PSTN 분 및 SMS(미리 보기)** 풀을 선택한 다음 보고서 **실행을 클릭합니다.**

![관리 센터에서 Teams PSTN 분 풀 보고서의 스크린샷입니다.](../media/teams-reports-pstn-minute-pools-with-callouts.png "번호 매기기 Teams 관리 센터의 PSTN 분 풀 보고서의 스크린샷 Microsoft Teams 관리 센터")

## <a name="interpret-the-report"></a>보고서 해석

|콜아웃 |설명  |
|--------|-------------|
|**1**   |각 보고서에는 생성된 날짜가 있습니다. 보고서는 일반적으로 활동 시간으로부터 24~48시간의 대기 시간을 반영합니다. |
|**2**   |해당 기능에 대한 활동을 보려면 기능(라이선스)을 클릭합니다. |
|**3**   |X 축은 국가 또는 지역입니다. Y축은 분 수입니다. <br>차트의 막대 위에 마우스를 대고 해당 사용 위치에 대한 활동을 볼 수 있습니다.  |
|**4**   |범례의 항목을 클릭하여 차트에 표시하는 항목을 필터링할 수 있습니다. 예를 들어 사용되지 **않은,** 국내 **사용자,**  데이터 없음 **또는** 각 사용자와 관련된 정보만 보는 데 사용되는 국제를 클릭합니다. |
|**5**   |이 표에서는 기능 및 사용 위치별 분 풀을 분석할 수 있습니다. <ul><li>**국가 또는 지역은** 사용 위치입니다. </li><li>**기능 설명은** 호출에 사용되는 라이선스에 대한 설명입니다.  이 보고서에 표시될 수 있는 기능 설명은 다음과 같습니다. <ul><li>국내 및 국제 통화 계획(국내 1200분)</li><li>국내 및 국제 통화 계획(국내 3000분)</li><li>국내 및 국제 통화 계획(600분)</li></ul></li><br><li>**총 분은** 월에 사용할 수 있는 총 분 수입니다.</li><li>**사용된 분은** 매월 사용된 분 수입니다.</li> <li>**사용 가능한 분은** 월에 남은 분 수입니다.</li><li>**기능은** 호출에 사용되는 라이선스입니다. 볼 수 있는 라이선스는 다음과 같습니다.<ul><li>**MCOPSTN1** - 국내 통화 계획(미국 3000분/ EU 1200분 요금제)</li><li>**MCOPSTN2** - 국제 통화 계획</li><li>**MCOPSTN5** - 국내 통화 계획(120분 통화 계획)</li><li>**MCOPSTN6** - 국내 통화 계획(240분 통화 계획)</li><li>**MCOMEETADD** - 오디오 회의</li></ul></li> </ul> 표에서 원하는 정보를 확인하려는 경우 테이블에 열을 추가해야 합니다.|
|**6**   |열 **편집을 선택하여** 표에 열을 추가하거나 제거합니다.|
|**7**   |전체 **화면을 선택하여** 전체 화면 모드에서 보고서를 볼 수 있습니다.|

## <a name="related-topics"></a>관련 항목

- [Teams 분석 및 보고](teams-reporting-reference.md)
