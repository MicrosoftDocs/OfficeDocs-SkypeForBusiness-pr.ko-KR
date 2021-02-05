---
title: CQD(통화 품질 대시보드) 설정
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
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
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: 통화 품질 대시보드를 켜고 사용하는 방법을 알아보고 통화 품질에 대한 요약 보고서를 얻을 수 있습니다.
ms.openlocfilehash: 60363ed86e4e073b7ca5a752261ac806188900b1
ms.sourcegitcommit: ac73536f790f83a61eeb2eb8c6b71662f7bd26fc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2021
ms.locfileid: "50112842"
---
# <a name="set-up-call-quality-dashboard-cqd"></a>CQD(통화 품질 대시보드) 설정

(관리자 자격 증명으로 로그인)에서 Microsoft CQD(통화 품질 대시보드)를 [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) 열 수 있습니다. 또는 Teams 관리 센터로 이동하여 통화 품질 **대시보드를 선택합니다.** 

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="Teams 관리 센터의 통화 품질 대시보드 단추 스크린샷":::

열리면 로그인을 **클릭하고** 전역 관리자 계정 또는 Microsoft Teams 서비스 관리자 계정 정보를 입력합니다. 처음 로그인하면 CQD가 데이터 수집 및 처리를 시작하게 됩니다. 보고서에 의미 있는 결과를 표시하기에 충분한 데이터를 처리하기까지 한 시간 이상이 걸릴 수 있습니다.

CQD는 Microsoft Teams, 비즈니스용 Skype Online 및 비즈니스용 Skype Server 2019에 대한 전체 수준에서 통화 및 모임 품질을 보여줍니다. 

> [!IMPORTANT]
> 비즈니스용 Skype Server 2019에서 CQD를 사용하기 위해 통화 데이터 커넥터를 [구성해야 합니다.](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-call-data-connector) 시작하기 [전에 계획 호출 데이터 커넥터를](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-call-data-connector) 참조합니다.


## <a name="assign-admin-roles-for-access-to-cqd"></a>CQD에 대한 액세스에 대한 관리자 역할 할당

CQD에 액세스하기 위한 역할을 사용해야 하는 사용자에게 할당합니다. [](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)

관리자가 아닌 사용자(예: 지원 엔지니어 및 기술 지원 팀 에이전트)가 통화 품질 대시보드를 사용하려면 해당 사용자에게 다음 역할 중 하나를 할당하여 CQD에 액세스할 수 있습니다. 


|  |보고서 보기  |EUII 필드 보기  |보고서 만들기  |건물 데이터 업로드  |
|---------|:-------:|:-------:|:-------:|:-------:|
|전역 관리자     |예         |예         |예         |예         |
|Teams 서비스 관리자     |예         |예         |예         |예         |
|Teams 커뮤니케이션 관리자     |예         |예         |예         |예         |
|Teams 커뮤니케이션 지원 엔지니어     |예         |예         |예         |아니요         |
|Teams Communications 지원 전문가     |예         |아니요         |예         |아니요         |
|비즈니스용 Skype 관리자     |예         |예         |예         |예         |
|글로벌 판독기 |예         |예         |예         |아니요         |
|보고서 읽기<sup>1</sup>     |예         |아니요         |예         |아니요         |

<sup>1</sup> 보고서 읽기는 CQD 보고서를 읽는 것 [](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) 외에도 관리 센터의 모든 활동 보고서와 [Microsoft 365](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f)채택 콘텐츠 팩의 모든 보고서를 볼 수 있습니다.

> [!NOTE]
> [EUII(최종](CQD-data-and-reports.md#euii-data) 사용자 식별 정보)가 표시되지 않는 경우 이 정보를 볼 수 있는 역할 중 하나만 있는 경우 CQD는 28일 동안 EUII만 유지해야 합니다. 28일이 지난 모든 것은 삭제됩니다.

이러한 역할에 대한 자세한 내용은 [Office 365 관리자](/office365/admin/add-users/about-admin-roles)역할 정보를 참조하세요.


처음 로그인하면 CQD가 데이터 수집 및 처리를 시작하게 됩니다. 2019년 12월을 현재 레거시 포털에서 최신 CQD(cqd.teams.microsoft.com)에 대한 링크를 제공하긴 하지만 이전 버전의 CQD(cqd.lync.com)에 계속 액세스할 수 cqd.teams.microsoft.com. 결국 이전 버전의 CQD는 해제됩니다. 2020년 7월 1일 현재 이전 버전의 CQD는 최신 CQD의 데이터에 액세스합니다.


## <a name="migrate-building-data-and-reports-from-previous-version-of-cqd"></a>이전 버전의 CQD에서 건물 데이터 및 보고서 마이그레이션

> [!IMPORTANT]
> 2020년 7월 1일을 기점으로 이전 CQD(. https://CQD.lync.com) 



## <a name="use-power-bi-to-analyze-cqd-data"></a>Power BI를 사용하여 CQD 데이터 분석

2020년 1월의 새로운 사항: [CQD용 Power BI 쿼리 템플릿을 다운로드합니다.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true) CQD 데이터를 분석하고 보고하는 데 사용할 수 있는 사용자 지정 가능한 Power BI 템플릿

Power [BI를 사용하여 CQD 데이터를](CQD-Power-BI-query-templates.md) 분석하여 자세히 알아보는 방법을 읽어 읽습니다.


## <a name="related-topics"></a>관련 항목

[Teams의 통화 품질 개선 및 모니터링](monitor-call-quality-qos.md)

[CQD란?](CQD-what-is-call-quality-dashboard.md)

[테넌트 업로드 및 데이터 구축](CQD-upload-tenant-building-data.md)

[CQD 데이터 및 보고서](CQD-data-and-reports.md)

[CQD를 사용하여 통화 및 모임 품질 관리](quality-of-experience-review-guide.md)

[CQD에서 사용할 수 있는 차원 및 측정값](dimensions-and-measures-available-in-call-quality-dashboard.md)

[CQD의 스트림 분류](stream-classification-in-call-quality-dashboard.md)

[Power BI를 사용하여 CQD 데이터 분석](CQD-Power-BI-query-templates.md)
