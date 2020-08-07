---
title: CQD (통화 품질 대시보드) 란?
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
description: 통화 품질 대시보드 (CQD) 및이를 사용 하 여 Microsoft 팀의 모임 및 통화 품질에 대 한 보고서를 확인 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 9ba1956533887314a9ffa7ad994cbb4c81ffe103
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583487"
---
# <a name="what-is-call-quality-dashboard-cqd"></a>CQD (통화 품질 대시보드) 란?

Microsoft 통화 품질 대시보드 (CQD)는 [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) **조직 전체 수준**, Microsoft 팀의 skype Online, 비즈니스용 skype 서버 2019 등의 통화 및 모임 품질이 표시 됩니다. 

  
최신 버전의 CQD는 [실시간 (NRT) 데이터 피드](CQD-data-and-reports.md)기능을 의미 하며,이는 통화를 종료 한 30 분 내에 CQD에서 통화 기록을 사용할 수 있습니다.

모든 CQD에는 [EUII (최종 사용자 식별 가능 정보) 데이터가](CQD-data-and-reports.md#euii-data)포함 되며, [Microsoft 365의 EUII](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview)와 같은 방식으로 관리 됩니다.

CQD는 팀 관리자, 비즈니스용 Skype 관리자, 네트워크 엔지니어가 조직 차원의 수준에서 통화와 모임 품질을 모니터링 하도록 설계 되었습니다. CQD를 사용 하 여 성능 품질을 드라이브에 맞게 **네트워크를 최적화할** 수 있습니다. **특정 사용자**에 대 한 통화 및 모임 정보를 확인 해야 하는 경우 CQD 데이터를 사용자별 [통화 분석](use-call-analytics-to-troubleshoot-poor-call-quality.md)을 통해 함께 사용 합니다.

예를 들어 CQD를 사용 하는 경우 사용자의 잘못 된 통화 품질 (사용자 단위 통화 분석 사용)이 다른 많은 사용자에 게 영향을 미치는 네트워크 문제로 인해 발생 하는 것을 확인할 수 있습니다. CQD는 개별 통화 환경과 팀 또는 비즈니스용 Skype를 사용 하 여 생성 되는 전체 통화 품질을 모두 캡처합니다. CQD를 사용 하면 전체 패턴이 명확 하 게 나타날 수 있으므로 네트워크 엔지니어가 통화 품질 평가를 할 수 있습니다. CQD는 전체 통화 품질, 서버 클라이언트 스트림, 클라이언트-클라이언트 스트림, 음성 품질 [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252)에 대 한 정보를 제공 하는 통화 품질 메트릭의 보고서를 제공 합니다. 
  
![통화 품질 대시보드의 스크린샷](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

CQD에는 빌드 및 끝점 정보를 업로드 하는 것이 좋습니다 .이를 통해 위치 향상 보고서를 사용 하 여 사용자의 빌드 내에서 통화 품질과 안정성을 분석할 수 있습니다. 데이터를 평가 하 여 문제가 단일 사용자에 게 격리 되었는지 또는 대규모 사용자 세그먼트에 영향을 미치는지 확인할 수 있습니다. CQD에서 빌드 또는 끝점 관련 보기를 설정 하려면 관리자가 CQD **테 넌 트 데이터 업로드** 페이지에서 [빌드 또는 끝점 정보를 업로드](CQD-upload-tenant-building-data.md) 해야 합니다.

![통화 품질 대시보드의 위치 향상 보고서 스크린샷.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

팀에서 서비스 품질 관리를 담당 하는 팀 관리자 또는 지원 엔지니어에 대 한 자세한 지침을 제공 하는 [관리 통화 및 모임 품질](quality-of-experience-review-guide.md) 문서를 놓치지 마세요.

## <a name="older-version-of-cqd-cqdlynccom"></a>이전 버전의 CQD (CQD.lync.com)

현재 버전의 CQD (의 https://CQD.Teams.microsoft.com) 이전 버전을 대체 하 고 https://CQD.lync.com) 있습니다. CQD.lync.com (비즈니스용 Skype 관리 센터에서 사용 가능)를 계속 사용할 수 있지만, 2020 년 7 월 1 일부 터는 CQD의 데이터를 사용 하 고 있습니다. Teams.microsoft.com. CQD.lync.com에 대 한 액세스가 곧 해제 되므로 CQD로 이동 해야 합니다. 아직 수행 하지 않은 경우 Teams.microsoft.com.

> [!IMPORTANT]
> 2020 년 7 월 1 일 현재 이전 CQD (CQD.lync.com)에서 더 이상 건물 또는 쿼리 데이터를 보거나 수정할 수 없습니다. CQD.lync.com에서이 데이터를 아직 마이그레이션하지 않은 경우에도 지원 티켓을 기록 합니다.

## <a name="use-power-bi-to-analyze-cqd-data"></a>Power BI를 사용 하 여 CQD 데이터 분석

T e 2020의 새로운 [기능: CQD 용 POWER BI 쿼리 서식 파일을 다운로드](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)합니다. CQD 데이터를 분석 하 고 보고 하는 데 사용할 수 있는 사용자 지정 가능한 Power BI 서식 파일입니다.

자세한 내용은 [POWER BI를 사용 하 여 CQD 데이터 분석을](CQD-Power-BI-query-templates.md) 참조 하세요.



## <a name="related-topics"></a>관련 항목

[팀의 통화 품질 개선 및 모니터링](monitor-call-quality-qos.md)

[CQD (통화 품질 대시보드) 설정](turning-on-and-using-call-quality-dashboard.md)

[테 넌 트 업로드 및 데이터 빌드](CQD-upload-tenant-building-data.md)

[CQD 데이터 및 보고서](CQD-data-and-reports.md)

[CQD를 사용 하 여 통화 및 모임 품질 관리](quality-of-experience-review-guide.md)

[CQD에서 사용할 수 있는 차원과 측정값](dimensions-and-measures-available-in-call-quality-dashboard.md)

[CQD의 스트림 분류](stream-classification-in-call-quality-dashboard.md)

[Power BI를 사용 하 여 CQD 데이터 분석](CQD-Power-BI-query-templates.md)


[Teams 문제 해결](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)