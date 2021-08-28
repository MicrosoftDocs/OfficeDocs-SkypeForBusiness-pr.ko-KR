---
title: Microsoft Teams 이벤트 사용 현황 보고서
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 관리 센터에서 Teams 라이브 이벤트 사용 보고서를 사용하여 Microsoft Teams 라이브 이벤트 활동에 대한 개요를 Teams 방법을 알아보습니다.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ea415e849f4255b38432d227a9d26452b3fc9275
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58631212"
---
# <a name="microsoft-teams-live-event-usage-report"></a>Microsoft Teams 이벤트 사용 현황 보고서

Teams 관리 센터의 Microsoft Teams 라이브 이벤트 사용 현황 보고서는 조직에서 개최되는 라이브 이벤트에 대한 활동 개요를 보여 줍니다. 각 이벤트에 대한 이벤트 상태, 시작 시간, 보기 및 프로덕션 유형을 비롯한 사용 현황 정보를 볼 수 있습니다. 사용량 추세에 대한 인사이트를 얻고 조직에서 라이브 이벤트를 일정, 발표 및 생성하는 사람에 대해 파악할 수 있습니다.

## <a name="view-the-live-event-usage-report"></a>라이브 이벤트 사용 보고서 보기

1. 관리 센터의 왼쪽 탐색에서 Microsoft Teams 분석 &  >  **보고서 를 클릭합니다.** 보고서 **보기** 탭의 보고서에서 **라이브** Teams **사용 을 선택합니다.**
2. 날짜 **범위에서** 미리 정의된 범위를 선택하거나 사용자 지정 범위를 설정합니다. 현재 날짜 전후 1년 6개월까지 데이터를 표시하는 범위를 설정할 수 있습니다.
3. (선택 사항) 이끌이 **아래에서** 특정 사용자가 구성한 라이브 이벤트만 표시하도록 선택할 수 있습니다.
4. 보고서 **실행 을 클릭합니다.**  

    ![콜아웃이 Teams 관리 센터의 Teams 라이브 이벤트 사용 보고서 스크린샷](../media/teams-live-event-usage-report-with-callouts.png "콜아웃이 Teams 관리 센터의 Teams 라이브 이벤트 사용 보고서 스크린샷")

## <a name="interpret-the-report"></a>보고서 해석

|콜아웃 |설명  |
|--------|-------------|
|**1**   |실시간 Teams 보고서는 지난 7일, 28일 또는 설정한 사용자 지정 날짜 범위의 추세를 볼 수 있습니다. |
|**2**   |각 보고서에는 생성된 날짜가 있습니다. 보고서는 페이지를 새로 고칠 때 거의 실시간 활동을 반영합니다. |
|**3**   |<ul><li>차트의 X축은 보고서에 대해 선택한 날짜 범위입니다.</li> <li> Y 축은 총 보기 수입니다.</li> </ul>주어진 날짜에 점 위에 마우스를 대고 그 날짜의 모든 라이브 이벤트의 보기 수를 볼 수 있습니다.|
|**4**   |이 표에서는 각 라이브 이벤트의 분석이 표시됩니다. <ul><li>**이벤트는** 라이브 이벤트의 표시 이름입니다. 이벤트 이름을 클릭하여 이벤트에 대한 자세한 [정보를](#view-event-details) 얻습니다. </li> <li>**시작 시간은** 이벤트의 시작 날짜 및 시간을 참조합니다.</li> <li>**이벤트 상태는** 이벤트가 발생한지 여부를 보여줍니다.  </li><li>**이끌이는** 이벤트 이끌이의 이름입니다.</li> <li>**발표자는** 이벤트 발표자 이름입니다.</li><li>**생산자는** 이벤트 생산자의 이름입니다.</li><li>**보기는** 이벤트가 완료된 후 고유 뷰의 수입니다.</li><li>**기록은** 녹화 설정이 설정 중인지 해제인지 여부를 보여줍니다.</li><li>**프로덕션 유형은** 이벤트가 Teams 또는 외부 애플리케이션 또는 디바이스에서 생성되는지 여부를 보여줍니다.</li></li> </ul>Azure AD에 사용자 계정이 더 이상 없는 경우 사용자 이름이 표에 "--"로 표시됩니다. <br><br>표에서 원하는 정보를 확인하려는 경우 테이블에 열을 추가해야 합니다. |
|**5**   |열 **편집을 선택하여** 표에 열을 추가하거나 제거합니다.|

## <a name="notes"></a>참고
현재 보고서 조건과 일치하는 최대 100개 라이브 이벤트를 표시합니다. 더 많은 라이브 이벤트를 표시하기 위해 날짜 필터를 적용하여 목록 크기를 줄입니다.

## <a name="view-event-details"></a>이벤트 세부 정보 보기

라이브 이벤트 세부 정보 페이지에서 라이브 이벤트의 세부 정보를 요약하고 이벤트와 연결된 전사 및 녹음 파일을 포함한 모든 파일을 나열합니다. 파일 이름을 클릭하여 파일을 보거나 다운로드합니다.

![라이브 이벤트의 세부 정보를 보여주는 스크린샷](../media/teams-live-event-usage-report-event-detail.png)

[조직에서 Hive](https://www.hivestreaming.com/partners/integration-partners/microsoft/) eCDN 또는 [Kollective](https://kollective.com) eCDN을 사용하도록 설정되어 있는 경우 파트너 보고서 링크를 클릭하여 추가 참석자 분석을 얻을 수 있습니다.

## <a name="related-topics"></a>관련 항목

- [Teams 분석 및 보고](teams-reporting-reference.md)
- [Teams 라이브 이벤트란 무엇인가요?](../teams-live-events/what-are-teams-live-events.md)
