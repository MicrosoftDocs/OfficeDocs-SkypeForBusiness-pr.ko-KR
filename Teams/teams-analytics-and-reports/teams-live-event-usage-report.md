---
title: Microsoft 팀 실시간 이벤트 사용 보고서
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
- M365-collaboration
description: Microsoft 팀 관리 센터에서 팀 실시간 이벤트 사용 보고서를 사용 하 여 조직의 팀 live 이벤트 활동에 대 한 개요를 확인 하는 방법에 대해 알아봅니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3c391370e757aedcf9ede889fc46f165cfc636f4
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37571150"
---
# <a name="microsoft-teams-live-event-usage-report"></a>Microsoft 팀 실시간 이벤트 사용 보고서

Microsoft 팀 관리 센터의 팀 실시간 이벤트 사용 보고서에는 조직에 보관 된 라이브 이벤트에 대 한 활동 개요가 표시 됩니다. 이벤트 상태, 시작 시간, 보기, 각 이벤트에 대 한 프로덕션 유형 등의 사용 정보를 볼 수 있습니다. 사용 추세에 대 한 통찰력을 얻고 조직의 누가 일정을 예약 하 고, 표시 하 고, 라이브 이벤트를 생성 하는지 확인할 수 있습니다.

## <a name="view-the-report"></a>보고서 보기

1. Microsoft 팀 관리 센터의 왼쪽 탐색 모음에서 **분석 & 보고서** > **사용 현황 보고서**를 클릭 합니다. 보고서 **보기** 탭의 **보고서**에서 **팀 실시간 이벤트 사용**을 선택 합니다.
2. **날짜 범위**아래에서 미리 정의 된 범위를 선택 하거나 사용자 지정 범위를 설정 합니다. 범위를 설정 하 여 현재 날짜의 6 개월 전부터 1 년 까지의 데이터를 표시할 수 있습니다.
3. ) **이끌이**에서 특정 사용자가 구성한 라이브 이벤트만 표시 하도록 선택할 수 있습니다.
4. **보고서 실행**을 클릭 합니다.  

    ![팀 관리 센터에서 설명선이 포함 된 팀 실시간 이벤트 사용 보고서 스크린샷](../media/teams-live-event-usage-report-with-callouts.png "팀 관리 센터에서 설명선이 포함 된 팀 실시간 이벤트 사용 보고서 스크린샷")

## <a name="interpret-the-report"></a>보고서 해석

|호출 |설명  |
|--------|-------------|
|**raid-1**   |팀 실시간 이벤트 보고서는 지난 7 일, 28 일 또는 사용자 지정 날짜 범위를 통해 추세를 볼 수 있습니다. |
|**2**   |각 보고서에는 생성 된 날짜를 포함 합니다. 페이지를 새로 고치면 보고서에 거의 실시간 작업이 반영 됩니다. |
|**3-4**   |<ul><li>차트의 X 축은 보고서에 대해 선택 된 날짜 범위입니다.</li> <li> Y 축은 총 뷰 수입니다.</li> </ul>지정 된 날짜의 점을 마우스로 가리켜 해당 날짜의 모든 라이브 이벤트에 대 한 보기 수를 확인 합니다.|
|**4(tcp/ipv4)**   |표에서는 각 라이브 이벤트의 분석 결과를 보여 줍니다. <ul><li>**이벤트** 는 라이브 이벤트의 표시 이름입니다. 이벤트 이름을 클릭 하 여 이벤트에 대 한 [자세한 정보를 가져옵니다](#view-event-details) . </li> <li>**시작 시간은** 이벤트의 시작 날짜 및 시간을 나타냅니다.</li> <li>이벤트 **상태** 는 이벤트가 발생 했는지 여부를 표시 합니다.  </li><li>**이끌이** 는 이벤트 이끌이의 이름입니다.</li> <li>**발표자** 는 이벤트 발표자의 이름입니다.</li><li>**생산자** 는 이벤트 제작자의 이름입니다.</li><li>**보기** 는 고유한 보기의 수입니다.</li><li>**녹화** 는 녹음/녹화 설정이 켜져 있는지 여부를 표시 합니다.</li><li>**프로덕션 유형** 이벤트가 팀에서 생성 되는지 외부 응용 프로그램 또는 장치에 의해 발생 하는지를 표시 합니다.</li></li> </ul>사용자 계정이 더 이상 Azure AD에 존재 하지 않는 경우에는 테이블에 사용자 이름이 "--"로 표시 됨을 참고 하세요. <br><br>표에 원하는 정보를 표시 하려면 표에 열을 추가 해야 합니다. |
|**5mb**   |**열 편집** 을 선택 하 여 테이블에 열을 추가 하거나 제거 합니다.|

## <a name="view-event-details"></a>이벤트 세부 정보 보기

실시간 이벤트 세부 정보 페이지에는 라이브 이벤트의 세부 정보에 대 한 요약이 표시 되며 이벤트와 연결 된 기록 및 녹음/녹화를 비롯 한 모든 파일이 나열 됩니다. 파일을 보거나 다운로드 하려면 파일 이름을 클릭 합니다.

![라이브 이벤트의 세부 정보를 보여 주는 스크린샷](../media/teams-live-event-usage-report-event-detail.png)

조직이 [Hive](https://www.hivestreaming.com/partners/integration-partners/microsoft/) ecdn 또는 [Kollective](https://kollective.com) ecdn에 대해 사용 하도록 설정 된 경우 파트너 보고서 링크를 클릭 하 여 추가 참석자 분석을 받을 수 있습니다.

## <a name="related-topics"></a>관련 항목

- [팀 분석 및 보고](teams-reporting-reference.md)
- [팀 라이브 이벤트는 무엇 인가요?](../teams-live-events/what-are-teams-live-events.md)