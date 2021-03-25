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
description: 통화 품질 대시보드를 켜고 사용하는 방법에 대해 알아보고 통화 품질에 대한 요약 보고서를 얻을 수 있습니다.
ms.openlocfilehash: 2d671de0e2ddc5d4c2a4e321cf90e2e2f0dbe770
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51162683"
---
# <a name="set-up-call-quality-dashboard-cqd"></a>CQD(통화 품질 대시보드) 설정

관리자 자격 증명으로 로그인)에서 CQD(Microsoft 통화 품질 [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) 대시보드)를 를 를 클릭합니다. 또는 Teams 관리 센터로 이동하여 품질 대시보드 **호출 을 선택합니다.** 

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="Teams 관리 센터의 통화 품질 대시보드 단추 스크린샷":::

열리는 페이지에서 로그인을  클릭하고 전역 관리자 계정 또는 Microsoft Teams Service Administrator 계정 정보를 입력합니다. 처음 로그인한 후 CQD는 데이터 수집 및 처리를 시작할 것입니다. 보고서에 의미 있는 결과를 표시하기에 충분한 데이터를 처리하는 데 한 시간 이상이 걸릴 수 있습니다.

CQD는 Microsoft Teams, 비즈니스용 Skype Online 및 비즈니스용 Skype Server 2019의 전체 수준에서 통화 및 모임 품질을 보여줍니다. 

> [!IMPORTANT]
> 비즈니스용 Skype Server 2019에서 CQD를 사용하 는 통화 데이터 커넥터를 [구성해야 합니다.](/skypeforbusiness/hybrid/configure-call-data-connector) 시작하기 [전에 통화 데이터 커넥터](/skypeforbusiness/hybrid/plan-call-data-connector) 계획 을 참조합니다.


## <a name="assign-admin-roles-for-access-to-cqd"></a>CQD에 대한 액세스에 대한 관리자 역할 할당

CQD를 사용해야 하는 사용자에게 CQD에 액세스하기 위한 역할을 할당합니다. [](/microsoft-365/admin/add-users/about-admin-roles)

관리자가 아닌 사용자(예: 지원 엔지니어 및 헬프데스크 에이전트)가 통화 품질 대시보드를 사용하려면 해당 사용자에게 다음 역할 중 하나를 할당하여 CQD에 대한 액세스 권한을 부여할 수 있습니다. 


|  |보고서 보기  |EUII 필드 보기  |보고서 만들기  |건물 데이터 업로드  |
|---------|:-------:|:-------:|:-------:|:-------:|
|전역 관리자     |예         |예         |예         |예         |
|Teams 서비스 관리자     |예         |예         |예         |예         |
|Teams 커뮤니케이션 관리자     |예         |예         |예         |예         |
|Teams 커뮤니케이션 지원 엔지니어     |예         |예         |예         |아니요         |
|Teams Communications 지원 전문가     |예         |아니요         |예         |아니요         |
|비즈니스용 Skype 관리자     |예         |예         |예         |예         |
|전역 읽기 |예         |예         |예         |아니요         |
|보고서 읽기<sup>1</sup>     |예         |아니요         |예         |아니요         |

<sup>1</sup> 보고서 리더는 CQD 보고서를 읽는 것 [](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) 외에도 관리 센터의 모든 활동 보고서와 [Microsoft 365](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f)채택 콘텐츠 팩의 모든 보고서를 볼 수 있습니다.

> [!NOTE]
> [EUII(최종](CQD-data-and-reports.md#euii-data) 사용자 식별 정보)가 표시되지 않는 경우 이 정보를 볼 수 있는 역할 중 하나가 있는 경우 CQD는 28일 동안 EUII만 유지해야 합니다. 28일보다 오래된 모든 것이 삭제됩니다.

이러한 역할에 대한 자세한 내용은 [Office 365 관리자 역할 정보 를 참조하세요.](/office365/admin/add-users/about-admin-roles)


처음 로그인한 후 CQD는 데이터 수집 및 처리를 시작할 것입니다. 레거시 포털에서 최신 CQD(cqd.lync.com)에 대한 링크를 제공하긴 하지만 2019년 12월 현재 이전 버전의 CQD(cqd.lync.com)에 액세스할 수 cqd.teams.microsoft.com. 결국 이전 버전의 CQD가 해제됩니다. 2020년 7월 1일 현재 이전 버전의 CQD는 최신 CQD의 데이터에 액세스합니다.


## <a name="migrate-building-data-and-reports-from-previous-version-of-cqd"></a>이전 버전의 CQD에서 건물 데이터 및 보고서 마이그레이션

> [!IMPORTANT]
> 2020년 7월 1일부로 이전 CQD에서 더 이상 건물 데이터 및 보고서를 마이그레이션할 수 https://CQD.lync.com) 없습니다. 



## <a name="use-power-bi-to-analyze-cqd-data"></a>Power BI를 사용하여 CQD 데이터 분석

2020년 1월 신규: [CQD용 Power BI 쿼리](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)템플릿 다운로드 CQD 데이터를 분석하고 보고하는 데 사용할 수 있는 사용자 지정 가능한 Power BI 템플릿입니다.

자세한 [내용은 Power BI를 사용하여 CQD 데이터를](CQD-Power-BI-query-templates.md) 분석합니다.


## <a name="related-topics"></a>관련 항목

[Teams에 대한 통화 품질 개선 및 모니터링](monitor-call-quality-qos.md)

[CQD란?](CQD-what-is-call-quality-dashboard.md)

[테넌트 및 건물 데이터 업로드](CQD-upload-tenant-building-data.md)

[CQD 데이터 및 보고서](CQD-data-and-reports.md)

[CQD를 사용하여 통화 및 모임 품질 관리](quality-of-experience-review-guide.md)

[CQD에서 사용할 수 있는 차원 및 측정값](dimensions-and-measures-available-in-call-quality-dashboard.md)

[CQD의 스트림 분류](stream-classification-in-call-quality-dashboard.md)

[Power BI를 사용하여 CQD 데이터 분석](CQD-Power-BI-query-templates.md)