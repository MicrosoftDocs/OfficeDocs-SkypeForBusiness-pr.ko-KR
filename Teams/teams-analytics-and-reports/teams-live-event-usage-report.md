---
title: Microsoft Teams 라이브 이벤트 사용 현황 보고서
author: CarolynRowe
ms.author: crowe
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
description: Microsoft Teams 관리 센터에서 Teams 라이브 이벤트 사용 현황 보고서를 사용하여 조직의 Teams 라이브 이벤트 활동에 대한 개요를 가져오는 방법을 알아봅니다.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 29a255c9248f07db00d4295e99d4062116ca4e76
ms.sourcegitcommit: 4d88637f510a78d5709d1213c3e285d83a022014
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/14/2022
ms.locfileid: "66794096"
---
# <a name="microsoft-teams-live-event-usage-report"></a>Microsoft Teams 라이브 이벤트 사용 현황 보고서

Microsoft Teams 관리 센터의 Teams 라이브 이벤트 사용 현황 보고서에는 조직에서 개최되는 라이브 이벤트에 대한 활동 개요가 표시됩니다. 각 이벤트에 대한 이벤트 상태, 시작 시간, 보기 및 프로덕션 유형을 포함한 사용량 정보를 볼 수 있습니다. 사용량 추세에 대한 인사이트를 얻고 조직에서 누가 라이브 이벤트를 예약, 발표 및 생성하는지 확인할 수 있습니다.

## <a name="view-the-live-event-usage-report"></a>라이브 이벤트 사용 현황 보고서 보기

1. Microsoft Teams 관리 센터의 왼쪽 탐색 영역에서 **분석 & 보고서** > **사용 현황 보고서를** 클릭합니다. **보고서 보기** 탭의 **보고서** 아래에서 **Teams 라이브 이벤트 사용량을** 선택합니다.
2. **날짜 범위** 에서 미리 정의된 범위를 선택하거나 사용자 지정 범위를 설정합니다. 현재 날짜 전후 6개월까지 데이터를 표시하도록 범위를 설정할 수 있습니다.
3. (선택 사항) **이끌이** 에서 특정 사용자가 구성한 라이브 이벤트만 표시하도록 선택할 수 있습니다.
4. **보고서 실행을** 클릭합니다.  

   :::image type="content" alt-text="설명선이 있는 Teams 관리 센터의 Teams 라이브 이벤트 사용 현황 보고서 스크린샷." source="../media/teams-live-event-usage-report-with-callouts.png" lightbox="../media/teams-live-event-usage-report-with-callouts.png":::

## <a name="interpret-the-report"></a>보고서 해석

|설명선 |설명  |
|--------|-------------|
|**1**   |Teams 라이브 이벤트 보고서는 지난 7일, 28일 동안의 추세 또는 설정한 사용자 지정 날짜 범위를 볼 수 있습니다. |
|**2**   |각 보고서에는 생성된 날짜가 있습니다. 보고서는 페이지를 새로 고칠 때 거의 실시간으로 활동을 반영합니다. |
|**3**   |<ul><li>차트의 X축은 보고서에 대해 선택한 날짜 범위입니다.</li> <li> Y축은 총 뷰 수입니다.</li> </ul>지정된 날짜의 점 위로 마우스를 가져가서 해당 날짜의 모든 라이브 이벤트의 보기 수를 확인합니다.|
|**4**   |테이블은 각 라이브 이벤트에 대한 분석을 제공합니다. <ul><li>**이벤트는** 라이브 이벤트의 표시 이름입니다. 이벤트 이름을 클릭하여 이벤트에 대한 [자세한 내용을 확인](#view-event-details) 합니다. </li> <li>**시작 시간은** 이벤트의 시작 날짜와 시간을 나타냅니다.</li> <li>**이벤트 상태는** 이벤트가 발생했는지 여부를 표시합니다.  </li><li>**이끌** 이는 이벤트 이끌이의 이름입니다.</li> <li>**발표자** 는 이벤트 발표자의 이름입니다.</li><li>**생산자는** 이벤트 생산자의 이름입니다.</li><li>**보기** 는 이벤트가 완료된 후의 고유 보기 수입니다.</li><li>**녹음/녹화** 는 녹음/녹화 설정이 켜졌는지 또는 꺼져 있는지를 보여 줍니다.</li><li>**프로덕션 유형** 은 이벤트가 Teams에서 생성되는지 아니면 외부 애플리케이션 또는 디바이스에서 생성되는지를 보여줍니다.</li></li> </ul>사용자 계정이 더 이상 Azure AD 없는 경우 사용자 이름은 테이블에 "--"로 표시됩니다. <br><br>테이블에서 원하는 정보를 보려면 테이블에 열을 추가해야 합니다. |
|**5**   |**열 편집을** 선택하여 테이블에서 열을 추가하거나 제거합니다.|

## <a name="notes"></a>참고
현재 보고서 조건과 일치하는 최대 100개의 라이브 이벤트가 표시됩니다. 더 많은 라이브 이벤트를 보려면 날짜 필터를 적용하여 목록 크기를 줄입니다.

익명 발표자는 보고서에 포함되지 않습니다.

이벤트 또는 요청 시 이벤트 기록을 시청하는 사람은 보기 수에 포함되지 않습니다. 

## <a name="view-event-details"></a>이벤트 세부 정보 보기

라이브 이벤트 세부 정보 페이지에서는 라이브 이벤트의 세부 정보에 대한 요약을 제공하고 이벤트와 연결된 기록 및 녹음/녹화를 포함한 모든 파일을 나열합니다. 파일을 보거나 다운로드하려면 파일 이름을 클릭합니다.

:::image type="content" alt-text="라이브 이벤트의 세부 정보를 보여 주는 스크린샷" source="../media/teams-live-event-usage-report-event-detail.png" lightbox="../media/teams-live-event-usage-report-event-detail.png":::

조직에서 [Hive](https://www.hivestreaming.com/partners/integration-partners/microsoft/) eCDN 또는 [Kollective](https://kollective.com) eCDN을 사용하도록 설정된 경우 파트너 보고서 링크를 클릭하여 추가 참석자 분석을 가져올 수 있습니다.

## <a name="related-topics"></a>관련 주제

- [Teams 분석 및 보고](teams-reporting-reference.md)
- [Teams 라이브 이벤트란 무엇인가요?](../teams-live-events/what-are-teams-live-events.md)
