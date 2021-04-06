---
title: CQD(통화 품질 대시보드)란?
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.assetid: 553fa13c-92d2-4d5c-a3d5-41a073cb047c
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: CQD(통화 품질 대시보드)와 이를 사용하여 Microsoft Teams에서 모임 및 통화 품질에 대한 보고서를 보는 방법에 대해 자세히 알아보습니다.
ms.openlocfilehash: d262449394d9ad880d13897988e40e26dd98578c
ms.sourcegitcommit: f223b5f3735f165d46bb611a52fcdfb0f4b88f66
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51593836"
---
# <a name="what-is-call-quality-dashboard-cqd"></a>CQD(통화 품질 대시보드)란?

CQD(Microsoft Call Quality 대시보드) - Microsoft Teams, 비즈니스용 Skype Online 및 [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) 비즈니스용 Skype 서버 2019의 전체 수준에서 통화 및 모임 품질을 보여줍니다.  

  
최신 버전의 CQD는 [거의 실시간(NRT)](CQD-data-and-reports.md)데이터 피드를 제공합니다. 즉, 통화가 종료된 후 30분 이내에 CQD에서 통화 레코드를 사용할 수 있습니다.

CQD에 [EUII(최종](CQD-data-and-reports.md#euii-data)사용자 식별 정보) 데이터가 포함되어 있는 경우 [Microsoft 365 전체에서 EUII와](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview)동일한 방식으로 관리됩니다.

CQD는 Teams 관리자, 비즈니스용 Skype 관리자 및 네트워크 엔지니어가 전체 수준에서 통화 및 모임 품질을 모니터링할 수 있도록 디자인됩니다. CQD를 사용하여 네트워크 최적화를 통해 성능 품질을 향상할 수 있습니다.  특정 사용자의 통화 및 모임 정보를 살펴봐야 하는 경우 **사용자별** 통화 분석과 함께 CQD 데이터를 [사용하세요.](use-call-analytics-to-troubleshoot-poor-call-quality.md)

예를 들어 CQD를 사용하면 사용자의 부실한 통화 품질(사용자당 통화 분석을 사용하여 관찰한)이 다른 많은 사용자에게도 영향을 주는 네트워크 문제 때문인지 확인할 수 있습니다. CQD는 개별 통화 환경과 Teams 또는 비즈니스용 Skype를 사용하여 통화한 전체 품질을 캡처합니다. CQD를 사용하여 전체 패턴이 명백해질 수 있으므로 네트워크 엔지니어는 통화 품질에 대한 정보를 평가할 수 있습니다. CQD는 전체 통화 품질, 서버-클라이언트 스트림, 클라이언트-클라이언트 스트림 및 음성 품질 SLA에 대한 인사이트를 제공하는 통화 품질 메트릭 보고서를 [제공합니다.](https://go.microsoft.com/fwlink/p/?linkid=846252) 
  
![통화 품질 대시보드 스크린샷.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

CQD에서는 사용자 건물 내에서 통화 품질 및 안정성을 분석하기 위해 Location-Enhanced 보고서를 사용할 수 있는 건물 및 엔드포인트 정보를 업로드하는 것이 권장됩니다. 데이터를 평가하여 문제가 단일 사용자에게 격리되어 있는지 또는 더 큰 사용자 세그먼트에 영향을 미치는지 확인할 수 있습니다. **CQD에서** 건물 또는 엔드포인트별 보기를 켜기 [](CQD-upload-tenant-building-data.md) 위해 관리자는 CQD 테넌트 데이터 업로드 페이지에서 건물 또는 엔드포인트 정보를 업로드해야 합니다.

![통화 품질 대시보드의 보고서 Location-Enhanced 스크린샷.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

Teams의 서비스 [](quality-of-experience-review-guide.md) 품질 관리를 담당하는 Teams 관리자 또는 지원 엔지니어에 대한 심층적인 지침을 제공하는 통화 및 모임 품질 관리 문서를 놓치지 마세요.

## <a name="legacy-version-of-cqd-cqdlynccom"></a>레거시 버전의 CQD(CQD.lync.com)

CQD의 현재 버전(은 CQD의 레거시 버전을 https://CQD.Teams.microsoft.com) https://CQD.lync.com) 대체합니다. 비즈니스용 skype CQD.lync.com 사용할 수 있지만 2020년 7월 1일 현재 CQD의 데이터를 사용하고 있습니다. Teams.microsoft.com 이전 CQD(데이터)에서 건물 또는 쿼리 데이터를 더 이상 보거나 수정할 수 CQD.lync.com. 이 데이터를 아직 마이그레이션하지 않은 CQD.lync.com 여전히 필요한 경우 지원 티켓을 기록합니다.

> [!IMPORTANT]
> 2021년 7월 31일 현재 레거시 버전의 CQD(CQD.lync.com)를 사용 중지합니다. 해당 날짜 이후에는 CQD로 자동으로 리디렉션됩니다. Teams.microsoft.com 액세스하려고 하면 CQD.lync.com 데이터가 손실됩니다.

## <a name="use-power-bi-to-analyze-cqd-data"></a>Power BI를 사용하여 CQD 데이터 분석

2020년 1월 신규: [CQD용 Power BI 쿼리](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)템플릿 다운로드 CQD 데이터를 분석하고 보고하는 데 사용할 수 있는 사용자 지정 가능한 Power BI 템플릿입니다.

자세한 [내용은 Power BI를 사용하여 CQD 데이터를](CQD-Power-BI-query-templates.md) 분석합니다.



## <a name="related-topics"></a>관련 항목

[Teams에 대한 통화 품질 개선 및 모니터링](monitor-call-quality-qos.md)

[CQD(통화 품질 대시보드) 설정](turning-on-and-using-call-quality-dashboard.md)

[테넌트 및 건물 데이터 업로드](CQD-upload-tenant-building-data.md)

[CQD 데이터 및 보고서](CQD-data-and-reports.md)

[CQD를 사용하여 통화 및 모임 품질 관리](quality-of-experience-review-guide.md)

[CQD에서 사용할 수 있는 차원 및 측정값](dimensions-and-measures-available-in-call-quality-dashboard.md)

[CQD의 스트림 분류](stream-classification-in-call-quality-dashboard.md)

[Power BI를 사용하여 CQD 데이터 분석](CQD-Power-BI-query-templates.md)


[Teams 문제 해결](/MicrosoftTeams/troubleshoot/teams)
