---
title: Power BI를 사용하여 Microsoft Teams에 대한 CQD 데이터 분석
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: siunies
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- remotework
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: Power BI를 사용하여 Microsoft Teams에 대한 CQD 데이터를 분석합니다.
ms.openlocfilehash: 5ef98f75854cb4a255bf3f01aeb32de66c059b76
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096524"
---
# <a name="use-power-bi-to-analyze-cqd-data-for-microsoft-teams"></a>Power BI를 사용하여 Microsoft Teams에 대한 CQD 데이터 분석

2020년 1월 신규: [CQD용 Power BI 쿼리](https://www.microsoft.com/download/details.aspx?id=102291)템플릿 다운로드 CQD 데이터를 분석하고 보고하는 데 사용할 수 있는 사용자 지정 가능한 Power BI 템플릿입니다.

Teams의 CQD(통화 품질 대시보드) 보고서의 경우 Power BI를 사용하여 데이터를 쿼리하고 보고하려면 CQD Power BI 템플릿을 다운로드합니다. Power BI에서 템플릿을 열면 CQD 관리자 자격 증명으로 로그인하라는 메시지가 표시됩니다. 이러한 쿼리 템플릿을 사용자 지정하고 Power BI 라이선스 및 CQD 관리자 권한이 있는 조직의 모든 사용자에게 배포할 수 있습니다.

이러한 PBIT 파일을 사용하려면 먼저 다운로드에 포함된 *MicrosoftCallQuality.pqx* 파일을 사용하여 Microsoft [CQD용 Power BI 커넥터를](CQD-Power-BI-connector.md) 설치해야 [합니다.](https://www.microsoft.com/download/details.aspx?id=102291) 

Power BI 보고서에 액세스할 수 [있는 올바른 CQD](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd) 액세스 역할이 있는지 확인 합니다. 

|  |  |
|---------|---------|
|<strong>(New!)</strong> CQD Teams 자동 전화 교환 & 큐 기록 보고서.pbit     |  이 템플릿은 다음 세 가지 보고서를 제공 합니다.</p><li>자동 전화 교환 - 자동 참석자에 오는 통화에 대한 분석을 보여 넣습니다.</li><li>통화 큐 - 통화 큐로 오는 통화에 대한 분석을 보여 넣습니다.</li><li>에이전트 타임라인 – 통화 큐 호출에서 활성 상태인 에이전트의 타임라인 보기를 보여 입니다.</li><br>자세한 내용은 큐 [기록 자동 전화 교환 & 를 읽어보아야 합니다.](aa-cq-cqd-historical-reports.md)        |
|CQD Helpdesk Report.pbit     |건물 및 EUII 데이터를 통합하는 이 보고서는 단일 사용자로부터 드릴업하여 해당 사용자에 대한 불량 호출 품질의 업스트림 근본 원인을 찾을 수 있도록 설계됩니다(예: 사용자가 네트워크 문제가 발생하는 건물에 있습니다).         |
|CQD 위치 향상된 Report.pbit     | CQD SPD 위치 보고서를 다시 상상합니다. 9개 보고서가 포함되어 있으며, RMC(통화 품질, 건물 WiFi, 안정성 및 평가 내 통화) 정보를 건물 또는 사용자에 의해 추가 드릴 스루스로 제공합니다.  보고 환경을 최대화하기 위해 건물 데이터를 업로드해야 합니다.        |
|CQD 모바일 디바이스 보고서.pbit     | 통화 품질, 안정성 및 내 통화 속도 등 모바일 디바이스 사용자를 위해 특별히 조정된 인사이트를 제공합니다. 모바일 네트워크, WiFi 네트워크 및 모바일 운영 체제 보고서(Android, iOS)를 확인합니다.        |
|CQD PSTN 직접 라우팅 보고서.pbit     |직접 라우팅을 통과하는 PSTN 호출에 대한 인사이트를 제공합니다. 자세한 내용은 [CQD PSTN 직접](CQD-PSTN-report.md)라우팅 보고서 사용을 읽어보아야 합니다.         |
|CQD 요약 보고서.pbit     |더 나은 시각화, 향상된 프레젠테이션, 향상된 정보 밀도 및 롤링 날짜. 이러한 보고서를 통해 식별자 더 쉽게 식별할 수 있습니다. 사용하기 쉬운 대화형 지도를 사용하여 위치로 통화 품질을 드릴링합니다. 9개 새 보고서:</p>- 품질 전체<br>- 안정성 전반<br>- RMC(내 통화 속도) 전체<br>- 회의 품질<br>- P2P 품질<br>- 회의 안정성<br>- P2P 안정성<br>- 컨퍼런스 RMC<br>- P2P RMC         |
|<strong>(New!)</strong> CQD Teams 사용률 보고서.pbit     | 조직의 사용자가 Teams를 사용하는 방법과 얼마나 많은지 보여줍니다. 보고 환경을 최대화하기 위해 건물 데이터를 업로드해야 합니다. 자세한 내용은 [CQD Power BI 보고서를](CQD-teams-utilization-report.md)사용하여 Microsoft Teams 사용률을 볼 수 있습니다.        |
|CQD 사용자 피드백(내 통화 속도) 보고서.pbit     | 조직에 대한 호출을 지원하기 위해 쉽게 사용할 수 있는 방식으로 내 통화 데이터 평가를 보여줍니다. 언어와 상호 참조하여 최종 사용자 교육 기회를 식별합니다.        |

> [!TIP]
> CQD 데이터에 대한 Power BI 보고서를 설정한 후 채널에 탭으로 추가합니다. 채널에서 **+** 선택한 후 **Power BI를** 선택한 다음 보고서를 찾습니다. 자세한 내용은 Teams용 Power BI 탭을 사용하여 [Embed 보고서를 읽습니다.](/power-bi/service-embed-report-microsoft-teams) Power BI 라이선스 및 CQD 관리자 자격 증명이 있는 사용자만 이러한 보고서에 액세스할 수 있습니다.


## <a name="related-topics"></a>관련 항목

[통화 품질 대시보드에서 사용할 수 있는 차원 및 측정값](dimensions-and-measures-available-in-call-quality-dashboard.md)

[통화 품질 대시보드의 분류 간소화](stream-classification-in-call-quality-dashboard.md)

[비즈니스용 Skype 통화 분석 설정](set-up-call-analytics.md)

[통화 분석을 사용하여 통화 품질 저하 문제 해결](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[통화 분석 및 통화 품질 대시보드](./monitor-call-quality-qos.md)
