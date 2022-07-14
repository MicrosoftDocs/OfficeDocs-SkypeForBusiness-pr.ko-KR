---
title: CQD(통화 품질 대시보드)란?
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: CQD(통화 품질 대시보드)와 이를 사용하여 Microsoft Teams에서 모임 및 통화 품질에 대한 보고서를 보는 방법에 대해 알아봅니다.
ms.openlocfilehash: 3bc3c9dcd83e4ff95a07fbffb6f07da39d254cde
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/14/2022
ms.locfileid: "66790073"
---
# <a name="what-is-call-quality-dashboard-cqd"></a>CQD(통화 품질 대시보드)란?

Microsoft CQD(통화 품질 대시보드) - [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) Microsoft Teams, 비즈니스용 Skype Online 및 비즈니스용 Skype 서버 2019의 통화 및 모임 품질을 **조직 전체 수준에서** 보여줍니다. 

  
최신 버전의 CQD는 [NRT(근 실시간) 데이터 피드](CQD-data-and-reports.md)를 제공합니다. 즉, 통화 레코드는 통화 종료 후 30분 이내에 CQD에서 사용할 수 있습니다.

CQD에 [EUII(최종 사용자 식별 정보) 데이터가](CQD-data-and-reports.md#euii-data) 포함되어 있는 경우 [Microsoft 365 전체에서 EUII](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview)와 동일한 방식으로 관리됩니다.

CQD는 Teams 관리자, 비즈니스용 Skype 관리자 및 네트워크 엔지니어가 조직 전체 수준에서 통화 및 모임 품질을 모니터링할 수 있도록 설계되었습니다. CQD를 사용하여 네트워크를 최적화하여 성능 품질을 높일 **수 있습니다** . **특정 사용자** 에 대한 통화 및 모임 정보를 조사해야 하는 경우 사용자별 [통화 분석](use-call-analytics-to-troubleshoot-poor-call-quality.md)과 함께 CQD 데이터를 사용합니다.

예를 들어 CQD를 사용하면 사용자의 통화 품질 저하(사용자별 통화 분석을 사용하여 관찰한)가 다른 많은 사용자에게도 영향을 주는 네트워크 문제로 인한 것임을 확인할 수 있습니다. CQD는 개별 통화 환경과 Teams 또는 비즈니스용 Skype 사용하여 수행한 전체 통화 품질을 모두 캡처합니다. CQD를 사용하면 전체 패턴이 명백해질 수 있으므로 네트워크 엔지니어는 통화 품질에 대한 정보에 입각한 평가를 수행할 수 있습니다. CQD는 전반적인 통화 품질, 서버-클라이언트 스트림, 클라이언트-클라이언트 스트림 및 음성 품질 [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252)에 대한 인사이트를 제공하는 통화 품질 메트릭에 대한 보고서를 제공합니다. 
  
![통화 품질 대시보드의 스크린샷.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

CQD에서는 Location-Enhanced 보고서를 사용하여 사용자 건물 내에서 통화 품질 및 안정성을 분석할 수 있는 빌드 및 엔드포인트 정보를 업로드하는 것이 좋습니다. 데이터를 평가하여 문제가 단일 사용자로 격리되었는지 아니면 더 큰 사용자 세그먼트에 영향을 미치는지 확인할 수 있습니다. CQD에서 빌드 또는 엔드포인트별 보기를 켜려면 관리자는 CQD **테넌트 데이터 업로드** 페이지에서 [빌드 또는 엔드포인트 정보를 업로드](CQD-upload-tenant-building-data.md)해야 합니다.

![통화 품질 대시보드의 Location-Enhanced 보고서의 스크린샷.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

Teams의 서비스 품질 관리를 담당하는 Teams 관리자 또는 지원 엔지니어에 대한 심층 지침을 제공하는 [통화 및 모임 품질 관리](quality-of-experience-review-guide.md) 문서를 놓치지 마세요.


## <a name="use-power-bi-to-analyze-cqd-data"></a>Power BI를 사용하여 CQD 데이터 분석

2020년 1월의 새로운 [기능: CQD용 Power BI 쿼리 템플릿을 다운로드합니다](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). CQD 데이터를 분석하고 보고하는 데 사용할 수 있는 사용자 지정 가능한 Power BI 템플릿입니다.

[자세한 내용은 Power BI를 사용하여 CQD 데이터를 분석](CQD-Power-BI-query-templates.md)합니다.



## <a name="related-topics"></a>관련 주제

[Teams의 통화 품질 개선 및 모니터링](monitor-call-quality-qos.md)

[CQD(통화 품질 대시보드) 설정](turning-on-and-using-call-quality-dashboard.md)

[테넌트 업로드 및 데이터 빌드](CQD-upload-tenant-building-data.md)

[CQD 데이터 및 보고서](CQD-data-and-reports.md)

[CQD를 사용하여 통화 및 모임 품질 관리](quality-of-experience-review-guide.md)

[CQD에서 사용할 수 있는 차원 및 측정값](dimensions-and-measures-available-in-call-quality-dashboard.md)

[CQD의 스트림 분류](stream-classification-in-call-quality-dashboard.md)

[Power BI를 사용하여 CQD 데이터 분석](CQD-Power-BI-query-templates.md)


[Teams 문제 해결](/MicrosoftTeams/troubleshoot/teams)
