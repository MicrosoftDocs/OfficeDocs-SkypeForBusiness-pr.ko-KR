---
title: Power BI를 사용 하 여 Microsoft 팀에 대 한 CQD 데이터 분석
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: siunies
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: Power BI를 사용 하 여 Microsoft 팀에 대 한 CQD 데이터를 분석 하세요.
ms.openlocfilehash: d737f321ea8684ffe99b50575b1b2e8d044804d0
ms.sourcegitcommit: 98fcfc03c55917d0aca48b7bd97988f81e8930c1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/07/2020
ms.locfileid: "42559622"
---
# <a name="use-power-bi-to-analyze-cqd-data-for-microsoft-teams"></a>Power BI를 사용 하 여 Microsoft 팀에 대 한 CQD 데이터 분석

T e 2020의 새로운 [기능: CQD 용 POWER BI 쿼리 서식 파일을 다운로드](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)합니다. CQD 데이터를 분석 하 고 보고 하는 데 사용할 수 있는 사용자 지정 가능한 Power BI 서식 파일입니다.

팀의 CQD 보고서의 경우 Power BI를 사용 하 여 데이터를 쿼리하고 보고 하려면 CQD Power BI 서식 파일을 다운로드 합니다. Power BI에서 서식 파일을 열면 CQD 관리자 자격 증명을 사용 하 여 로그인 하 라는 메시지가 표시 됩니다. 이러한 쿼리 서식 파일을 사용자 지정 하 고 Power BI 라이선스 및 CQD 관리자 권한이 있는 조직의 모든 사용자에 게 배포할 수 있습니다.

이러한 .PBIX 파일을 사용 하려면 [다운로드](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)에 포함 된 *MicrosoftCallQuality* 파일을 사용 하 여 [Microsoft CQD 용 Power BI 커넥터를 설치](CQD-Power-BI-connector.md) 해야 합니다. 


|  |  |
|---------|---------|
|CQD 헬프데스크 보고서. .pbix     |빌드 및 EUII 데이터 통합이 보고서는 단일 사용자에 게 드릴 다운 하 여 해당 사용자에 대 한 잘못 된 통화 품질의 업스트림 근본 원인을 찾을 수 있도록 설계 되었습니다 (예: 사용자가 네트워크 문제가 발생 하는 건물에 있는 경우).         |
|CQD 위치 향상 보고서. .pbix     | CQD SPD 위치 보고서를 다시 구상. 건물 또는 사용자를 기준으로 추가 드릴 thrus와의 통화 음질, WiFi 빌드, 안정성, 내 통화 속도 (RMC) 정보를 제공 하는 9 개의 보고서가 포함 되어 있습니다.        |
|CQD 모바일 장치 보고서. .pbix     | 통화 음질, 안정성, 내 통화 요금을 비롯 한 모바일 장치 사용자에 게 구체적으로 조정 되는 정보를 제공 합니다. 모바일 네트워크, WiFi 네트워크, 모바일 운영 체제 보고서 (Android, iOS)를 봅니다.        |
|CQD PSTN 다이렉트 라우팅 보고서. .pbix     |직접 라우팅을 통과 하는 PSTN 호출에 대 한 정보를 제공 합니다. 자세한 내용은 [CQD PSTN 다이렉트 라우팅 보고서를 사용 하](CQD-PSTN-report.md)여 읽어 보세요.         |
|CQD 요약 보고서. .pbix     |향상 된 시각화, 향상 된 프레젠테이션, 증가 하는 정보 조밀도 및 롤링 날짜 이러한 보고서를 사용 하면 식별자가 이상 이상 하 게 됩니다. 편리한 대화형 지도를 사용 하 여 통화 품질을 위치에 따라 드릴 하세요. 9 개의 새 보고서:</p>-전체 품질<br>-안정성 전반적<br>-RMC (통화 요금 평가) 전체<br>-컨퍼런스 음질<br>-P2P 품질<br>-컨퍼런스 안정성<br>-P2P 안정성<br>-컨퍼런스 RMC<br>-P2P RMC         |
|**(신규!)** CQD 팀 이용률 보고서. .pbix     | 조직의 사용자가 팀을 사용 하는 방법과 사용량을 보여 줍니다. 자세한 내용은 [CQD POWER BI 보고서를 참조 하 여 Microsoft 팀의 이용률을 확인](CQD-teams-utilization-report.md)하세요.        |
|CQD 사용자 피드백 (내 통화 요금) 보고서. .pbix     | 조직에 대 한 통화 지원에 쉽게 사용할 수 있는 방식으로 내 통화 데이터의 요금을 표시 합니다. Verbatims와 상호 참조를 사용 하 여 최종 사용자 교육 기회를 식별 합니다.        |


## <a name="related-topics"></a>관련 항목

[통화 품질 대시보드에서 사용할 수 있는 차원 및 측정값](dimensions-and-measures-available-in-call-quality-dashboard.md)

[통화 품질 대시보드의 분류 간소화](stream-classification-in-call-quality-dashboard.md)

[비즈니스용 Skype 통화 분석 설정](set-up-call-analytics.md)

[통화 분석을 사용하여 통화 품질 저하 문제 해결](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[통화 분석 및 통화 품질 대시보드](difference-between-call-analytics-and-call-quality-dashboard.md)
 