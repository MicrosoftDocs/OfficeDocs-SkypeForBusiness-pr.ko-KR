---
title: CQD (통화 품질 대시보드) 설정
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
description: 통화 품질 대시보드를 켜고 사용 하는 방법과 통화 품질에 대 한 요약 보고서를 받는 방법을 알아봅니다.
ms.openlocfilehash: 9a864b0ad0f48e3a0bd8665b8dfeb917e67f4062
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2020
ms.locfileid: "48918640"
---
# <a name="set-up-call-quality-dashboard-cqd"></a>CQD (통화 품질 대시보드) 설정

[https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com)(관리자 자격 증명으로 로그인)에서 CQD (Microsoft 통화 품질 대시보드)를 엽니다. 또는 팀 관리 센터로 이동 하 여 **통화 품질 대시보드** 를 선택 합니다. 

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="팀 관리 센터의 통화 품질 대시보드 단추 스크린샷":::

열리는 페이지에서 **로그인** 을 클릭 하 고 전역 관리자 계정 또는 Microsoft 팀 서비스 관리자 계정 정보를 입력 합니다. 처음 로그인 하면 CQD가 데이터 수집과 처리를 시작 합니다. 보고서에 의미 있는 결과를 표시 하기에 충분 한 데이터를 처리 하는 데 시간이 한 시간 이상 걸릴 수 있다는 점에 유의 하세요.

CQD는 조직 전체 수준, Microsoft 팀, 비즈니스용 Skype Online, 비즈니스용 Skype 서버 2019 등의 통화 및 모임 품질을 보여줍니다. 

> [!IMPORTANT]
> 비즈니스용 Skype 서버 2019에서 CQD를 사용 하려면 [Call Data Connector를 구성](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-call-data-connector)해야 합니다. 시작 하기 전에 [요금제 호출 데이터 커넥터](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-call-data-connector) 를 참조 하세요.


## <a name="assign-admin-roles-for-access-to-cqd"></a>CQD에 대 한 액세스 관리자 역할 할당

사용 해야 하는 사용자에 게 CQD에 액세스 하기 위한 [역할](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) 을 할당 합니다.

관리자가 아닌 사용자 (예: 지원 엔지니어 및 헬프데스크 에이전트)가 통화 품질 대시보드를 사용 하 게 하려면 다음 역할 중 하나를 할당 하 여 CQD에 대 한 액세스 권한을 부여할 수 있습니다. 


|  |보고서 보기  |EUII 필드 보기  |보고서 만들기  |빌드 데이터 업로드  |
|---------|:-------:|:-------:|:-------:|:-------:|
|Office 365 전역 관리자     |예         |예         |예         |예         |
|Teams 서비스 관리자     |예         |예         |예         |예         |
|Teams 커뮤니케이션 관리자     |예         |예         |예         |예         |
|Teams 커뮤니케이션 지원 엔지니어     |예         |예         |예         |아니요         |
|팀 의사 소통 지원 전문가     |예         |아니요         |예         |아니요         |
|비즈니스용 Skype 관리자     |예         |예         |예         |예         |
|Azure AD 전역 읽기 프로그램 |예         |예         |예         |아니요         |
|Office 365 보고서 리더기<sup>1</sup>     |예         |아니요         |예         |아니요         |

<sup>1</sup> CQD 보고서 읽기 외에도, Office 365 보고서 구독자는 관리 센터의 모든 [활동 보고서](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) 와 [Microsoft 365 채택 콘텐츠 팩](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f)의 모든 보고서를 볼 수 있습니다.

> [!NOTE]
> [EUII (최종 사용자 식별 가능 정보)](CQD-data-and-reports.md#euii-data) 가 표시 되지 않고 이러한 정보를 볼 수 있는 역할 중 하나가 있는 경우 CQD는 28 일간 EUII을 유지 한다는 점에 유의 하세요. 28 일이 지난 모든 항목은 삭제 됩니다.

이러한 역할에 대 한 자세한 내용은 [Office 365 관리자 역할](/office365/admin/add-users/about-admin-roles)정보를 참조 하세요.


처음 로그인 하면 CQD가 데이터 수집과 처리를 시작 합니다. 2019 년 12 월 이전에는 레거시 포털에서 최신 CQD (cqd.teams.microsoft.com)에 대 한 링크를 제공 하지만이 경우에도 cqd.lync.com (c)의 오래 된 버전에 액세스할 수 있습니다. 결과적으로 CQD의 이전 버전이 서비스 해제 됩니다. 2020 년 7 월 1 일부 터, 이전 버전의 CQD는 최신 CQD의 데이터에 액세스 합니다.


## <a name="migrate-building-data-and-reports-from-previous-version-of-cqd"></a>이전 버전의 CQD에서 데이터 및 보고서 작성 마이그레이션

> [!IMPORTANT]
> 2020 년 7 월 1 일 현재 이전 CQD ()의 데이터 및 보고서 빌드를 더 이상 마이그레이션할 수 없습니다 https://CQD.lync.com) . 



## <a name="use-power-bi-to-analyze-cqd-data"></a>Power BI를 사용 하 여 CQD 데이터 분석

T e 2020의 새로운 [기능: CQD 용 POWER BI 쿼리 서식 파일을 다운로드](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)합니다. CQD 데이터를 분석 하 고 보고 하는 데 사용할 수 있는 사용자 지정 가능한 Power BI 서식 파일입니다.

자세한 내용은 [POWER BI를 사용 하 여 CQD 데이터 분석을](CQD-Power-BI-query-templates.md) 참조 하세요.


## <a name="related-topics"></a>관련 항목

[팀의 통화 품질 개선 및 모니터링](monitor-call-quality-qos.md)

[CQD 란 무엇 인가요?](CQD-what-is-call-quality-dashboard.md)

[테 넌 트 업로드 및 데이터 빌드](CQD-upload-tenant-building-data.md)

[CQD 데이터 및 보고서](CQD-data-and-reports.md)

[CQD를 사용 하 여 통화 및 모임 품질 관리](quality-of-experience-review-guide.md)

[CQD에서 사용할 수 있는 차원과 측정값](dimensions-and-measures-available-in-call-quality-dashboard.md)

[CQD의 스트림 분류](stream-classification-in-call-quality-dashboard.md)

[Power BI를 사용 하 여 CQD 데이터 분석](CQD-Power-BI-query-templates.md)
