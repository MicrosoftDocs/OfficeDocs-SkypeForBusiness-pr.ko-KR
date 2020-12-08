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
ms.openlocfilehash: a06a3cb76cd778c132b3e8745b279035e875f16e
ms.sourcegitcommit: f122c078b6458754500f3cc68086d6ccfa62d183
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/08/2020
ms.locfileid: "49588331"
---
# <a name="use-power-bi-to-analyze-cqd-data-for-microsoft-teams"></a>Power BI를 사용하여 Microsoft Teams에 대한 CQD 데이터 분석

2020년 1월의 새로운 사항: [CQD용 Power BI 쿼리 템플릿을 다운로드합니다.](https://www.microsoft.com/download/details.aspx?id=102291) CQD 데이터를 분석하고 보고하는 데 사용할 수 있는 사용자 지정 가능한 Power BI 템플릿

Teams의 통화 품질 대시보드(CQD) 보고서의 경우 Power BI를 사용하여 데이터를 쿼리하고 보고하려면 CQD Power BI 템플릿을 다운로드하세요. Power BI에서 템플릿을 열면 CQD 관리자 자격 증명으로 로그인하라는 메시지가 표시됩니다. 이러한 쿼리 템플릿을 사용자 지정하고 Power BI 라이선스 및 CQD 관리자 권한이 있는 조직의 모든 사용자에게 배포할 수 있습니다.

이러한 PBIT 파일을 사용하려면 먼저 다운로드에 포함된 *MicrosoftCallQuality.pqx* 파일을 사용하여 Microsoft [CQD용 Power BI](CQD-Power-BI-connector.md) 커넥터를 설치해야 [합니다.](https://www.microsoft.com/download/details.aspx?id=102291) 

Power BI 보고서에 액세스할 수 있는 [올바른 CQD](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd) 액세스 역할이 있는지 확인 

|  |  |
|---------|---------|
|<strong>(New!)</strong> CQD Teams 자동 전화 교환 & 기록 Report.pbit 호출     |  이 템플릿은 다음 세 가지 보고서를 제공 합니다.</p><li>자동 전화 교환 - 자동 전화 회의로 들어오는 통화에 대한 분석을 보여 넣습니다.</li><li>통화 큐 – 통화 큐로 들어오는 호출에 대한 분석을 보여 주며,</li><li>에이전트 타임라인 - 호출 큐 호출에서 활성 상태인 에이전트의 타임라인 보기를 보여 줄 수 있습니다.</li><br>자세한 내용은 호출 [큐 자동 전화 교환 & 보고서를 읽어 읽습니다.](aa-cq-cqd-historical-reports.md)        |
|CQD Helpdesk Report.pbit     |건물 및 EUII 데이터를 통합하는 이 보고서는 단일 사용자로부터 드릴업하여 해당 사용자의 호출 품질이 좋지 않은 업스트림 근본 원인(예: 사용자가 네트워크 문제가 발생하는 건물에 있는 경우)을 찾을 수 있도록 디자인됩니다.         |
|CQD 위치 향상된 Report.pbit     | CQD SPD 위치 보고서를 다시 이미징합니다. 작성 또는 사용자에 의해 추가 드릴스루와 함께 통화 품질, WiFi 작성, 안정성 및 평가 내 통화(RMC) 정보를 제공하는 9개 보고서가 포함되어 있습니다.  보고 환경을 최대화하려면 건물 데이터를 업로드해야 합니다.        |
|CQD 모바일 디바이스 Report.pbit     | 통화 품질, 안정성 및 통화 평가를 포함하여 모바일 장치 사용자에 맞게 특별히 조정된 인사이트를 제공합니다. 모바일 네트워크, WiFi 네트워크 및 모바일 운영 체제 보고서(Android, iOS)를 확인합니다.        |
|CQD PSTN 직접 라우팅 Report.pbit     |직접 라우팅을 통과하는 PSTN 호출에 대한 인사이트를 제공합니다. 자세한 내용은 CQD PSTN 직접 라우팅 보고서를 [사용하여 읽어보아야 합니다.](CQD-PSTN-report.md)         |
|CQD 요약 보고서.pbit     |향상된 시각화, 향상된 프레젠테이션, 향상된 정보 밀도 및 롤링 날짜. 이러한 보고서를 통해 더 쉽게 식별할 수 있습니다. 사용하기 쉬운 대화형 지도를 사용하여 위치로 통화 품질을 드릴다운합니다. 9개 새 보고서:</p>- 전체 품질<br>- 안정성 전반<br>- RMC(내 통화 평가) 전체<br>- 컨퍼런스 품질<br>- P2P 품질<br>- 컨퍼런스 안정성<br>- P2P 안정성<br>- 컨퍼런스 RMC<br>- P2P RMC         |
|<strong>(New!)</strong> CQD Teams 사용률 보고서.pbit     | 조직의 사용자가 Teams를 사용하는 방법과 얼마나 많은지 보여줍니다. 보고 환경을 최대화하려면 건물 데이터를 업로드해야 합니다. 자세한 내용은 [CQD Power BI 보고서를 사용하여 Microsoft Teams 사용률을 읽습니다.](CQD-teams-utilization-report.md)        |
|CQD 사용자 피드백(내 통화 평가) Report.pbit     | 조직에 대한 통화를 지원하기 위해 쉽게 사용할 수 있는 방식으로 내 통화 속도 데이터를 보여 줄 수 있습니다. 최종 사용자 교육 기회를 식별하기 위해 대문자를 통해 상호 참조합니다.        |

> [!TIP]
> CQD 데이터에 대한 Power BI 보고서를 설정한 후 채널에 탭으로 추가합니다. 채널에서 **+** 선택한 후 **Power BI를 선택한** 다음 보고서를 찾습니다. 자세한 내용은 [Teams용 Power BI 탭을 사용하여 Embed 보고서를 읽습니다.](https://docs.microsoft.com/power-bi/service-embed-report-microsoft-teams) Power BI 라이선스 및 CQD 관리자 자격 증명이 있는 사용자만 이러한 보고서에 액세스할 수 있습니다.


## <a name="related-topics"></a>관련 항목

[통화 품질 대시보드에서 사용할 수 있는 차원 및 측정값](dimensions-and-measures-available-in-call-quality-dashboard.md)

[통화 품질 대시보드의 분류 간소화](stream-classification-in-call-quality-dashboard.md)

[비즈니스용 Skype 통화 분석 설정](set-up-call-analytics.md)

[통화 분석을 사용하여 통화 품질 저하 문제 해결](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[통화 분석 및 통화 품질 대시보드](difference-between-call-analytics-and-call-quality-dashboard.md)
 
