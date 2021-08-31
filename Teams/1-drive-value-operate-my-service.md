---
title: 에 대한 작업 Microsoft Teams
author: rmw2890
ms.author: Rowille
audience: admin
manager: serdars
ms.date: 06/11/2019
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 서비스 상태를 모니터링하고 네트워크 Teams 및 사용을 평가하고 보장하는 등 서비스 관리에 필요한 작업 및 활동입니다.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: feb801bb1e9ed7d573bee48a44d0796f8891221b
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58728423"
---
# <a name="operate-my-service"></a>내 서비스 운영

이 문서에서는 조직의 클라우드 음성 서비스를 성공적으로 운영하기 위한 요구 사항에 대한 개요를 제공합니다. 클라우드 음성 서비스를 올바르게 운영하면 조직에 고품질의 신뢰할 수 있는 환경을 제공해야 합니다.

## <a name="introduction-to-the-operations-guide"></a>작업 가이드 소개

작업 가이드에서는 서비스 관리 함수의 일부로 필요한 모든 작업 및 활동에 대한 개요를 Microsoft Teams.

서비스 관리는 사용자가 배포하고 사용하도록 설정된 Microsoft Teams 서비스의 매일 작업을 다루는 광범위한 토픽입니다. 이 Teams 서비스는 Microsoft 365 Office 365 인프라 구성 요소(예: 네트워킹)를 포함합니다.

서비스 관리의 개념은 대부분의 조직에서 새로운 개념이 아 않을 가능성이 가장 높습니다. 기존 서비스와 연결된 프로세스 및 작업을 이미 구현한 것일 수 있습니다. 즉, 향후 서비스 관리를 지원하기 위해 오늘 서비스 관리를 계획할 때 현재 프로세스를 Teams 수 있습니다.

서비스 관리에는 종단과 종단을 관리하는 데 관련된 Teams 모든 활동과 프로세스가 포함됩니다. 앞에서 설명한 대로 서비스 관리의 일부 구성 요소인 Microsoft 365 Office 365 서비스 자체가 구성하는 인프라는 Microsoft의 책임입니다. 반면 고객은 사용자가 제공하는 네트워크 및 엔드포인트의 다양한 측면을 Teams 책임이 있습니다.

이 가이드의 작업 및 활동은 다음 다이어그램에 설명된 8개의 범주로 그룹화됩니다. 이러한 각 범주는 다음 섹션에서 확장됩니다.

![작업 및 활동의 범주 목록을 설명하는 다이어그램입니다.](media/operate-my-service-image1.png "서비스 관리가 구성하는 작업 및 활동의 범주 목록을 Teams 다이어그램입니다. 또한 이 다이어그램에서는 서비스 관리가 크게 고객 작업입니다.")


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>의사 결정 지점</td><td><ul><li>작업을 구현하는 방법을 Teams.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>다음 단계</td><td><ul><li>작업 가이드 전체를 검토합니다.</li><li>클라우드 음성 워크로드의 품질 및 안정성을 제공하기 위해 조직의 목표에 부합하는 운영 전략을 구현합니다.</li><li>검토 [모니터 통화 품질 입니다.](monitor-call-quality-qos.md)</li><li> 클라우드 음성 배포가 최고 기능에서 작동하고 있는지 확인하기 위해 환경 품질 검토를 정기적으로 수행하기 위한 작업 전략을 구현합니다.</li></ul></td></tr>
</table>


### <a name="operational-role-mapping"></a>운영 역할 매핑

첫 번째 파일럿 사용자가 사용하도록 설정될 때 작업 작업이 시작하기 때문에 Envision 단계에서 작업을 수행하기 위한 계획이 중요합니다. 이 가이드에서는 고품질 배포를 유지 관리하기 위해 매일, 매주, 매월 또는 필요한 기준으로 수행해야 하는 활동 및 작업을 Teams 나열합니다. 이 가이드에서는 이러한 중요한 활동 및 작업을 수행하는 방법에 대한 지식과 지침을 제공합니다.

성공적인 배포의 한 가지 중요한 구성 요소는 Envision 단계에서 초기에 수행하는 계획에 특정 작업을 수행할 책임이 있는 사용자 결정이 포함되도록 하는 것입니다. 배포에 어떤 작업과 활동이 적용될지 확인한 후 해당 작업을 이해하고 그 다음에 할당한 그룹 또는 개인을 이해해야 합니다.

식별하는 각 팀은 식별된 작업 및 책임에 대해 검토하고 동의하고 준비를 시작해야 합니다. 여기에는 교육 및 준비, 직원 계획에 대한 업데이트를 제공하거나 외부 공급자가 제공할 준비가 되어 있는 것이 포함됩니다.

이 가이드에 정의된 활동 및 역할은 대부분의 시나리오에서 유효해야 하지만 모든 Teams 고유합니다. 따라서 이 가이드를 시작점으로 사용하여 요구 사항을 충족하기 위해 활동 및 기본 역할을 사용자 지정할 수 있습니다.

각 책임 팀이 서비스를 실행하기 위해 필요한 활동에 대해 잘 이해해야 합니다. 각 팀은 첫 번째 파일럿이 시작되기 전에 조직의 책임에 동의하고 서명하는 것이 중요합니다.

협약이 체결된 후 해당 팀은 해당 역할을 운영하기 시작해야 합니다.

<table>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>다음 단계</td>
<td><ul><li>이 문서를 사용하여 운영 역할 매핑 연습을 용이하게 합니다.</li><li>필요한 활동 목록에서 각 항목에 이름을 할당하려면 각 지원 팀과 만나야 합니다.</li><li>할당된 역할에 대한 수락 또는 사인오프를 얻습니다.</li><li>해당 팀이 필요한 작업을 완료하기 위해 적절한 교육, 준비 및 리소스를 확보해야 합니다.</li></ul></td></table>

### <a name="teams-service-dependencies"></a>Teams 종속성

Microsoft Teams 팀워크를 위한 허브를 제공하기 위해 Microsoft 365 Office 365 기술을 함께 제공합니다. 예제는 다음과 같습니다.

-   Azure Active Directory(Azure AD)는 인증 및 권한 부여 서비스를 Teams.

-   Exchange Online 법적 보류 및 전자 검색과 같은 고급 기능을 제공합니다.

-   SharePoint Online은 채널에서 파일을 공유할 수 있는 기능을 제공하며, 비즈니스용 OneDrive 채팅 내에서 파일을 공유하는 메커니즘을 제공합니다.

조직은 또한 프레미스 인프라에 대한 기존 투자를 활용할 수도 있습니다. 예를 들어 기존온-프레미스 Active Directory 계정을 Azure AD 계정을 사용하여 인증에 사용할 수 커넥트. 특정 버전의 Exchange Server 대신 사용할 수 Exchange Online.

이러한 기술은 사용자에 대한 풍부하고 공동 작업적이고 지능적인 통신 제품군을 제공하기 위해 함께 제공됩니다. 이러한 긴밀한 통합은 이러한 Teams 주요 이점이지만 이러한 기술에서 서비스 관리에 대한 요구 사항도 주도합니다.

이 가이드에서는 서비스 관리에 중점을 두는 주요 Teams 다루고 있습니다. 대부분의 경우 지원 기술에 대한 서비스 관리 계획이 Teams 있습니다. 그렇지 않은 경우 이러한 기술 구성 요소(온-프레미스 및 온라인 모두)에 대한 적절한 서비스 관리 계획을 수립해야 합니다. 이렇게 하면 사용자가 고품질의 신뢰할 수 있는 환경을 즐길 수 Teams.

#### <a name="references"></a>참조 

[개요 Microsoft Teams](teams-overview.md)

[Exchange와 Microsoft Teams의 상호 작용 방법](exchange-teams-interact.md)

[온라인 SharePoint 및 비즈니스용 OneDrive 상호 작용하는 Microsoft Teams](sharepoint-onedrive-interact.md)

[Microsoft Teams 및 비즈니스용 Skype 및 상호운용성](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

<!--ENDOFSECTION-->

## <a name="operations-guide-activities"></a>작업 가이드 활동

다음 섹션에서는 서비스를 성공적으로 운영하는 데 필요한 활동에 Microsoft Teams 제공합니다. 여기에는 활동을 이해하고 준비 이니셔티브를 지원하기 위해 도구, 상황에 맞는 정보 및 추가 콘텐츠에 대한 참조가 포함됩니다.

<!--ENDOFSECTION-->

## <a name="monitor-service-health"></a>서비스 상태 모니터링

서비스에 영향을 주는 모든 이벤트의 조직에서 다른 Microsoft Teams 사전 경고할 수 있도록 서비스의 전반적인 상태는 이해하는 것이 중요합니다. 앞에서 설명한 Teams 서비스는 Microsoft 365 Office 365, Azure Active Directory, Exchange Online SharePoint 및 비즈니스용 OneDrive. 이 때문에 종속 서비스의 상태도 모니터링하는 것이 중요합니다.

이 작업을 인시던트 관리 프로세스에 통합하여 사용자, 헬프데스크 및 운영 팀에 사전 알리고 사용자 에스컬레이터를 처리할 준비를 합니다.

다음 섹션에서는 서비스 인시던트에 영향을 [](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity#Anchor_1) 미치는 서비스 인시던트에 대해 모니터링하는 데 활용할 수 있는 도구를 Teams 설명합니다. 각 도구의 이점 및 각 도구를 사용해야 하는 경우의 요약은 다음 표에 포함됩니다.

| 모니터링 도구                       | 이점                                            | 사용 하는 경우                                                                                  |
|---------------------------------------|-----------------------------------------------------|----------------------------------------------------------------------------------------------|
| Microsoft 365 관리 센터                     | 지원되는 브라우저가 있는 모든 장치에서 사용할 수 있습니다. | 실시간 알림이 필요하지 않은 경우 사용할 수 있습니다.                                          |
| Microsoft 365 또는 Office 365 관리자 앱                  | 모바일 디바이스에 푸시 알림을 제공합니다.  | 이동하는 동안 서비스 인시던트에 대한 알림을 제공해야 하는 경우를 사용 합니다.                  |
| Microsoft System Center               | Microsoft System Center.           | 고급 모니터링 기능 및 알림 지원이 필요한 경우 사용                       |
| Microsoft 365 또는 Office 365 Api | 서비스 상태 또는 Microsoft 365 Office 365 프로그래밍식 액세스입니다.   | 타사 모니터링 도구와 통합해야 하는 경우 또는 자체 솔루션을 빌드하려는 경우 사용합니다. |

> [!NOTE]
> 전역 관리자 또는 서비스  관리자  역할이 할당된 개인만 서비스 상태는 볼 수 있습니다.

### <a name="monitoring-with-the-microsoft-365-admin-center"></a>Microsoft 365 관리 센터

이 [Microsoft 365 관리 센터](https://portal.office.com/) 종속 서비스 외에도 Teams 상태의 현재 상태도 볼 수 있는 Service [Health](https://portal.office.com/adminportal/home#/servicehealth) 대시보드를 제공합니다.

### <a name="monitoring-with-the-mobile-app"></a>모바일 앱으로 모니터링

앱 Microsoft 365 또는 Office 365 관리자 앱은 Apple iOS, Android 및 Windows(PC 및 모바일)에서 사용할 수 있습니다. 앱은 서비스 상태 및 예정된 변경 내용에 대한 서비스 관리자 정보를 제공합니다. 앱은 권고가 게시된 직후에 경고할 수 있는 푸시 알림을 지원합니다. 이렇게 하면 서비스 상태, 상태 및 예정된 변경 내용에 대한 최신 상태를 유지하게 됩니다. 알림 지원은 관리자에게 권장되는 모니터링 도구입니다. 자세한 내용은 다음을 참조하세요.

[Office 365 관리자 모바일 앱](https://support.office.com/article/Office-365-Admin-Mobile-App-e16f6421-2a1a-4142-bf9d-9846600a060a)

[모바일 Office 365 관리자 다운로드](https://products.office.com/business/manage-office-365-admin-app)

### <a name="monitoring-with-microsoft-system-center"></a>Microsoft System Center

Microsoft System Center 데이터 센터, 클라이언트 디바이스 및 하이브리드 클라우드 IT 환경을 관리하는 데 도움이 되는 통합 관리 플랫폼입니다. Office 365 관리자에게 System Center 관리 팩을 가져오는 옵션이 Office 365 관리 팩을 가져올 수 있습니다. 그러면 관리 관리자 내의 모든 서비스 통신을 볼 수 System Center. 이 도구를 사용하면 구독된 서비스, 활성 및 해결된 서비스 인시던트 및 Message Center 통신(예정된 변경 내용)에 액세스할 수 있습니다. 자세한 내용은 다음 블로그 게시물 [을 참조하세요.](https://blogs.office.com/2014/07/29/new-office-365-admin-tools/?eu=true)

서비스 System Center 모니터링하기 위해 Teams 서비스 상태(및 종속 서비스)를 모니터링하는 경우 인시던트에 대응하기 위해 식별된 특정 그룹 또는 개인에게 경고하거나 알릴 관리 팩을 추가로 사용자 지정할 수 있습니다.
이러한 그룹에는 조직의 서비스 소유자, 헬프데스크, 2차 및 3차 지원 그룹 및 인시던트 관리자가 포함할 수 있습니다.

### <a name="monitoring-for-advanced-scenarios"></a>고급 시나리오에 대한 모니터링

서비스 상태 및 변경 내용을 프로그래밍 Office 365 서비스 통신 API를 사용하여 서비스 상태 및 예정된 변경 Office 365 모니터링할 수 있습니다. 이 API를 사용하여 자체 모니터링 도구를 만들거나 기존 모니터링 도구를 연결하여 서비스 Office 365 모니터링하는 방법을 간소화할 수 있습니다. 자세한 내용은 Office 365 개발자에 Enterprise [참조하세요.](https://developer.microsoft.com/office)

### <a name="dailyweeklymonthlyas-needed-tasks"></a>일일/매주/월간/필요한 작업

| 활동               | 설명                                                                                                                                                                                                               | 케이던스   | 팀 할당 |
|------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| 서비스 상태 모니터링 | 사용 가능한 도구를 사용하여 Microsoft Teams 서비스 상태 및 종속 서비스)를 사전 예방적으로 모니터링합니다. 종속 서비스에는 Exchange Online, SharePoint, 비즈니스용 OneDrive, Azure Active Directory. | 실시간 |               |
| 인시던트 알림  | 서비스에 영향을 주는 이벤트에 대한 내부 Teams 알릴 수 있습니다. 내부 이해 관계자는 사용자, 헬프데스크 및 인시던트 관리자를 포함할 수 있습니다.                                                                          | 필요한 경우 |               |

### <a name="references"></a>참조 

[서비스 Office 365 확인 방법](https://support.office.com/article/How-to-check-Office-365-service-health-932AD3AD-533C-418A-B938-6E44E8BC33B0)

[서비스 상태 확인 Microsoft Teams](service-health.md)

[서비스 상태 및 연속성](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity)

<!--ENDOFSECTION-->

## <a name="manage-organizational-change"></a>조직 변경 관리

Microsoft Teams 클라우드 기반 서비스입니다. 이를 통해 새로운 기능과 기능을 빠른 속도로 제공할 수 있습니다. 지속적인 혁신을 제공하는 것은 조직에 분명한 이점을 제공하지만 이러한 변경 내용은 사용자 저항 또는 지원 데스크로의 에스컬레이터를 방지하기 위해 조직 내에서 적절하게 관리해야 합니다.

업데이트는 Teams 자동으로 롤아웃됩니다. 사용자는 항상 최신 클라이언트 및 기능을 Teams 있습니다. 사용자에 대한 업데이트의 롤아웃을 관리할 수 Teams 수 있으므로 효과적인 통신, 교육 및 채택 프로그램을 통해 변경을 관리하는 것이 매우 중요합니다. 사용자가 변경을 인식하고, 이점에 대해 교육하고, 새로운 기능을 활용할 수 있는 권한을 부여하면 더 빠르게 적응하고 변경을 환영할 &mdash; 수 있습니다.

### <a name="monitoring-for-change"></a>변경에 대한 모니터링

변경 관리의 첫 번째 단계는 변경 내용을 모니터링하는 Teams. 이러한 변경 내용을 모니터링하는 가장 [](https://products.office.com/business/office-365-roadmap)좋은 Office 365 로드맵은 현재 개발 중, 고객에게 롤아웃되거나 완전히 시작된 기능을 나열하는 로드맵입니다. 제공된 필터를 사용하여 Teams 특정 기능을 검색하거나 추가 분석을 위해 로드맵을 Excel 수 있습니다. 각 기능에 대해 로드맵은 예상 릴리스 날짜와 함께 간략한 설명을 제공 합니다.

웹 [Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)업데이트에 대한 모범 사례, 추세 및 뉴스에 대해 Teams 있습니다. 여기에서 발표할 주요 기능 Teams 찾을 수 있습니다. RSS 피드를 통해 블로그를 구독할 수 있습니다. 그런 다음, [RSS](https://techcommunity.microsoft.com/gxcuf89792/rss/board?board.id=MicrosoftTeamsBlog) 피드를 Teams 채널에 직접 추가할 수 있으므로 중요한 모든 뉴스가 Teams.

릴리스된 모든 기능은 에 대한 릴리스 [Microsoft Teams.](https://support.office.com/article/Release-notes-for-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)
다음은 데스크톱, 웹 및 모바일 디바이스에 대해 릴리스된 기능 목록입니다. 동일한 릴리스 정보 집합은 도움말  의 새 탭에서도 사용할 [수 있습니다.](get-help-in-microsoft-teams.md)

사용 가능한 리소스에 익숙해지고 변경을 모니터링할 해당 소유자를 할당해야 합니다.

### <a name="planning-for-change"></a>변경 계획

이제 서비스에서 다가오는 변경 사항을 알고 Teams 준비하고 그에 따라 계획을 세우는 것입니다. 각 변경 내용을 평가하여 사용자와의 통신, 인식 캠페인, 지원 팀 또는 사용자에 대한 교육 또는 기능 평가 및 채택 캠페인이 필요한 변경 내용을 파악합니다. 조직의 변경 관리 팀의 기본 역할입니다. 다음은 변경을 계획하는 데 도움이 되는 샘플 테이블 모음입니다.

#### <a name="feature-cloud-recording-release-date-january-2018"></a>기능: 클라우드 기록(릴리스 날짜: 2018년 1월)

**일반 트랙**

| 준비 변경 | 상태   | 노트/다음 단계 | 소유자 |
|----|----|----|-----|
| 법적 검토   | 완료되었습니다.     | 이 기능은 교육 팀을 온보드하기 위한 전제적인 기능입니다. | Project 팀  |

**기술 변경 관리**

|       준비 변경       | 상태 |                      노트/다음 단계                      |    소유자     |
|------------------------------|--------|------------------------------------------------------------|--------------|
|     IT 변경 필요      |  예   | 관리자는 식별된 사용자에 대해 기록을 사용하도록 설정해야 합니다. | 지원 팀 |
| 기술 준비 완료 |  예   |                                                            | 지원 팀 |
|                              |        |                                                            |              |

**사용자 변경 관리** 

| 준비 변경 | 상태   | 노트/다음 단계 | 소유자 |
|----|----|----|-----|
| 사용자 영향                  | 낮음                  |                                                                 |                        |
| 사용자 준비 필요      | 예                  |                                                                 |                        |
| 통신 준비         | 아니요                   | 통신 전자 메일이 초안이 작성된 상태입니다. 검토 보류 중입니다.            | 통신 팀    |
| 교육 준비               | 예                  | 교육은 기존 Microsoft 비디오를 활용합니다.                | 교육 팀          |

**상태 트랙**

| 준비 변경 | 상태   | 노트/다음 단계 | 소유자 |
|----|----|----|-----|
| 릴리스 상태               | 진행 중          | 임원 후원자에 의해 검토 보류 중입니다.               | 변경 관리 팀 |
| 릴리스 사인오프             |                      |                                                                 |                        |
| 릴리스 날짜                 |                      |                                                                 |                        |

변경 관리에 대한 계획에 대한 자세한 내용은 Teams 에 대한 변경 관리 전략 [만들기를 Microsoft Teams.](change-management-strategy.md)

### <a name="dailyweeklymonthlyas-needed-tasks"></a>일일/매주/월간/필요한 작업

| 활동               | 설명                                                                                                                                                                                                                | 케이던스   | 팀 할당 |
|------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| 변경에 대한 모니터링     | 서비스에서 다가오는 변경 내용을 Microsoft Teams 모니터링합니다.                                                                                                                                                                   | 매일     |               |
| 변경 계획    | 통신 계획, 인식 캠페인 및 교육을 비롯한 새로운 기능 및 기능을 평가하고 계획합니다.                                                                                                     | 필요한 경우 |               |
| 사용자 준비             | 사용자가 다가오는 변경에 대한 준비가 되도록 대상 통신, 인식 또는 교육 캠페인을 수행합니다.                                                                                                        | 필요한 경우 |               |
| 팀 준비 지원 | 지원 팀이 준비가 되도록 대상 통신, 인식 또는 교육 캠페인을 수행합니다. 지원 팀은 "화이트 글러브" 팀, 헬프데스크, 계층 2 또는 계층 3 지원, 외부 파트너를 포함할 수 있습니다. | 필요한 경우 |               |

<!--ENDOFSECTION-->

## <a name="assess-teams-usage"></a>사용 Teams 평가

초기 파일럿이 시작된 후 실제 사용량을 측정하기 위한 Teams 중요합니다. 이렇게 하면 조직에서 실제 사용량이 Envision 단계에서 예측한 사용량과 어떻게 일치하는지 파악할 수 있습니다. 이 섹션에서는 사용 현황을 Teams 전반적인 사용량을 측정하고 평가하기 위한 광범위한 Office 365 해야 합니다.

배포 초기에 자주 사용량을 검토하면 다음을 할 수 있습니다.

-   사용자가 사용 중인지 Teams.

-   조직 전체에서 중요한 문제를 발생하기 전에 잠재적인 채택 문제를 식별합니다.

-   Envision 단계 요구 사항과 실제 사용량 간에 불일치가 있는지 여부를 이해합니다.

사용량이 예상과 다른 경우 배포 문제로 인해 이 문제가 발생하거나 채택 계획이 제대로 실행되지 못하거나 다른 문제가 있을 수 있습니다. 사용량이 낮은 실제 이유에 따라 서비스 관리자는 사용 장벽을 제거하기 위해 관련 팀과 공동 작업해야 합니다.

### <a name="measuring-usage-with-the-microsoft-365-admin-center"></a>사용 현황을 Microsoft 365 관리 센터

보고서 Teams 사용 현황 데이터는 보고 대시보드에서 사용할 수 있습니다. Teams 사용 현황 데이터는 세 가지 다른 보고서에서 찾을 수 있습니다. 첫 번째 보고서는 사용자가 다양한 서비스를 사용하여 통신하고 공동 작업하는 방법에 대한 제품 간 보기를 Office 365. 이 보고서는 활성 사용자 보고서의 Office 365 [있습니다.](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Active-Users-FC1CF1D0-CD84-43FD-ADB7-A4C4DFA8112D)

다른 두 보고서는 Teams 관련이 있으며 사용자 및 디바이스 관점에서 Teams 자세한 정보를 제공합니다. 두 보고서 모두 여기에서 찾을 수 있습니다.

[Microsoft Teams 사용 보고서](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Microsoft-Teams-device-usage-917b3e1d-203e-4439-8539-634e80196687)

[Microsoft Teams 작업 보고서](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Microsoft-Teams-user-activity-07f67fc4-c0a4-4d3f-ad20-f40c7f6db524)

#### <a name="required-permissions"></a>필수 사용 권한

관리 센터의 사용 보고서는 전역 관리자 역할 또는  제품별 관리자 역할(Exchange 관리자,비즈니스용 Skype 관리자 및 관리자)에 의해 액세스할 **수 SharePoint 있습니다.**

또한 보고서  읽기 권한자 역할은 보고서에 대한 액세스가 필요하지만 관리자 수준 권한이 필요한 작업을 수행하지 않는 사용자에게 사용할 수 있습니다. 이 역할을 할당하여 이해 관계자인 모든 사용자에게 사용 보고서를 제공하여 채택을 모니터링하고 주도합니다. 사용 가능한 다양한 역할에 대한 자세한 내용은 관리자 역할 [Office 365 참조하세요.](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)

### <a name="assessing-usage"></a>사용 현황 평가

보고 대시보드를 사용하여 사용량을 측정한 후 프로젝트의 Envision 단계에서 정의한 주요 성공 지표(KSIS)와 측정된 사용량을 비교하는 것이 중요합니다. 활성 사용으로 정의될 수 있는 KSI 또는 간접적으로 활성 사용과 연결된 KSI를 정의할 수 있습니다.

추가 사이트 또는 사용자에게 롤아웃을 다시 시작하기 전에 실제 사용량과 계획된 사용량 간의 차이를 식별하는 것이 중요합니다. 이 활동의 일부로 조직 학습을 식별하여 다음 사이트 또는 사용자의 일괄 처리에서 동일한 문제가 발생하지 않도록 할 수 있습니다.

먼저 이 문제가 채택인지 아니면 기술적인 문제인지를 의문으로 해결합니다. 먼저 아래 항목을 조사하여 문제의 위치를 파악합니다.

1.  환경 품질 검토를 수행하여 품질 [](monitor-call-quality-qos.md) 유효성을 검사합니다(자세한 내용은 통화 품질 Teams 참조).

2.  지원팀 팀에 문의하여 사용자가 서비스에 액세스하거나 사용할 수 없는 최신 기술 문제가 없는지 확인합니다. 문제 추세가 있는 경우 [](#endpoint-troubleshooting) 이 문서의 의 1부에서 엔드포인트 문제 해결 섹션을 사용하여 지원을 참여하기 전에 문제를 해결합니다.

3.  교육 및 채택 팀과 함께 사용자로부터 직접 [](#assess-user-sentiment) 피드백을 수집합니다(이 문서의 나중에 사용자 감정 평가 참조) 인식 및 채택 활동의 효과를 확인하세요.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>일일/매주/월간/필요한 작업

| 활동                         | 설명                                                                                                                      | 케이던스   | 팀 할당 |
|----------------------------------|----------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| 사용량 측정(사용 단계) | 사이트가 Teams 동안 계속 온보드될 때 사용량을 측정하고 평가합니다. 필요한 경우 사용 현황 문제를 해결합니다. | 매주    |               |
| 사용량 측정(드라이브 값 단계)                           | 드라이브 Teams 단계(배포가 완료된 후)에서 사용량을 측정하고 평가합니다. 필요한 경우 사용 현황 문제를 해결합니다. | Biweekly  |               |
| 채택 계획 업데이트             | 사용량이 계획 목표와 비교되는 방식에 따라 채택 계획을 업데이트합니다.                                         | 필요한 경우 |               |

### <a name="references"></a>참조 

[Microsoft 365 관리 센터](https://support.office.com/article/About-the-Office-365-admin-center-758befc4-0888-4009-9f14-0d147402fd23)

[작업 보고서의 Microsoft 365 관리 센터](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)

<!--ENDOFSECTION-->

## <a name="assess-user-sentiment"></a>사용자 감정 평가

사용자 정서 이해는 배포의 성공을 측정하는 주요 Teams 수 있습니다. 사용자 피드백은 조직의 변경을 구동할 수 있습니다. 여기에는 통신 계획, 교육 프로그램 또는 사용자에게 지원을 제공하는 방식이 변경될 수 있습니다.

피드백을 조기 수집하고 프로젝트 수명 주기 전반에 걸쳐 사용자 정서 평가를 계속 진행하는 것이 중요합니다. 다음 지침을 사용하여 조직에서 피드백을 구할 간격을 결정할 수 있습니다.

-   **프로젝트 시작:** 프로젝트 시작 시 사용자 감정을 평가하여 사용자가 자신의 경험에 대해 어떻게 느끼는지 초기 Teams 있습니다.

-   **주요 이정표** 후 : 프로젝트 수명 주기 전반에 걸쳐 피드백을 수집하여 사용자 감정을 지속적으로 측정하고 필요한 경우 변경할 수 있습니다. 이 기능은 주요 중요 시점 이후에 특히 유용합니다.

-   **Project** 결론 : 프로젝트가 끝날 때 사용자 감정을 평가하면 얼마나 잘 했는지, 작업을 계속해야 하는지 알려 주며, 이전 설문 조사와 결과를 비교할 수 있습니다.

-   **진행 중**: 사용자 감정을 무기한으로 계속 측정합니다. 사용자 정서의 변화는 조직의 환경의 변경 또는 서비스 변경으로 Teams 있습니다. 정기적인 간격으로 사용자 감정을 파악하여 서비스 관리 팀이 얼마나 잘 수행하고 조직이 서비스 변경에 응답하는지 Teams 수 있습니다.

사용자 감정은 다양한 방법을 통해 평가할 수 있습니다. 여기에는 전자 메일 설문 조사, 대면 또는 전화 스타일 인터뷰를 포함하거나 사용자 의견 채널을 만드는 것만으로도 Teams Yammer. 자세한 내용은 에서 사용자 피드백 방법에 대한 모범 [사례를](best-practices-feedback.md)Microsoft Teams.

다음 섹션에 설명된 NPS(순 홍보자 점수)라는 사용자 감정을 평가하기 위해 업계 전반의 접근 방식을 사용할 수도 있습니다.

### <a name="nps"></a>NPS 

NPS(순 프로모터 점수)는 업계 전반의 고객 충성도 메트릭이자 사용자 감정을 평가하는 데 사용할 수 있는 좋은 접근 방식입니다. NPS는 다음 두 가지 질문을 통해 계산할 수 있습니다. "동료에게 Teams 추천할 가능성이 Teams?", "왜?" 자유형 질문과 함께 계산할 수 있습니다.

NPS는 –100에서 100까지의 인덱스로, 회사의 제품 또는 서비스를 추천할 고객의 의중을 측정합니다. NPS는 전자 메일 또는 기타 전자적 수단을 통해 사용자에게 전달된 익명 설문 조사를 기반으로 합니다. NPS는 공급자와 소비자 간의 충성도를 측정합니다. 이 질문은 사용자가 1에서 10까지의 경험을 평가할 수 있도록 요청하는 하나의 질문으로 구성됩니다. 추가 설명을 제공하는 옵션이 있습니다. 그런 다음 사용자는 다음 등급에 따라 분류됩니다.

-   9 또는 10은 프로모션자입니다. 서비스를 홍보하고 다른 사용자들에게 연료를 공급할 충성도 매니아입니다.

-   7 또는 8은 수동적입니다. 만족하지만 unenthusiastic, 다른 서비스 또는 제공에 취약합니다.

-   1에서 6까지는 Detractors: 서비스를 손상하고 성장을 방해할 수 있는 불행한 고객입니다.

![NPS 확장을 보여주는 다이어그램입니다.](media/operate-my-service-image2.png "이 다이어그램은 NPS 확장을 보여 주었다. 0에서 6까지의 순위는 디트랙터, 7~8은 수동, 9~10의 순위는 프로모터입니다.")

기본 NPS 번호가 유용하겠지만 사용자 의견 분석에서 가장 많은 값을 얻을 수 있습니다. 사용자가 다른 사용자에게 추천하는 이유를 Teams 도움이 됩니다. 이러한 의견은 프로젝트 또는 서비스 관리 팀이 양질의 서비스를 제공하는 데 필요한 조정을 이해하는 데 도움이 되는 귀중한 피드백을 제공할 수 있습니다.

조직에 NPS 설문 조사를 제공하려면 선호하는 온라인 설문 조사 도구를 활용할 수 있습니다.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>일일/매주/월간/필요한 작업

| 활동              | 설명                                                                                                                                                                         | 케이던스   | 팀 할당 |
|-----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| 사용자 감정 평가 | 설문 조사 또는 인터뷰를 사용하여 사용자 정서 캡처 및 평가 또는 Teams 또는 Yammer.                                                                 | 필요한 경우 |               |
| 채택 계획 업데이트 | 사용자 피드백에 따라 조직의 변경을 드라이브합니다. 여기에는 통신 계획, 교육 프로그램 또는 사용자에게 지원을 제공하는 방식이 변경될 수 있습니다. | 필요한 경우 |               |

### <a name="references"></a>참조 

[순 프로모터 점수](https://en.wikipedia.org/wiki/Net_Promoter)

[사용자 Yammer 사용하여 피드백을 수집합니다.](https://techcommunity.microsoft.com/t5/Yammer-Blog/The-Microsoft-Teams-team-uses-Yammer/ba-p/55210)

[사용자 피드백에 대한 모범 사례](best-practices-feedback.md)

<!--ENDOFSECTION-->

## <a name="manage-network-quality"></a>네트워크 품질 관리

많은 핵심 계획 요소는 네트워크 인프라를 최적화, 오른쪽 크기 조정 및 수정하여 서비스에서 고품질의 효율적인 경로를 Microsoft Teams 합니다. 계획 작업 및 요구 사항은 네트워크 준비 지침에 [설명됩니다.](3-envision-evaluate-my-environment.md#network-readiness) 네트워크는 종종 업그레이드, 확장 또는 기타 비즈니스 요구 사항으로 인해 시간이 지날 때 발전합니다. 네트워크 계획 활동에 대한 요구 사항을 Teams 중요합니다.

네트워크 계획은 배포의 중요한 Teams 비즈니스 또는 기술 요구 사항에 따라 네트워크가 정상 상태로 유지되도록 하는 것이 중요합니다.

네트워크의 상태 확인을 위해 정기적으로 여러 작업 작업을 수행해야 합니다.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>일일/매주/월간/필요한 작업

| 활동                                                       | 설명                                                                                                                                                                                                                                                                                                                                                                 | 케이던스                | 팀 할당 |
|----------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------|---------------|
| OFFICE 365 및 URL 모니터링                                | 제공된 [RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) [피드를](/microsoft-365/enterprise/urls-and-ip-address-ranges) Office 365 URL 및 IP 주소 범위에 대한 변경 내용을 모니터링하고 해당 네트워킹 그룹에 대한 변경 요청을 시작합니다.                                                                                                                                | 매일                  |               |
| 변경 내용에 따라 네트워크 업데이트 Office 365 URL | 해당 네트워크 구성 요소(방화벽, 프록시 서버, VPN, 클라이언트 쪽 방화벽 등)를 업데이트하여 URL 및 IP 주소 범위에 대한 Office 365 [반영합니다.](/microsoft-365/enterprise/urls-and-ip-address-ranges)                                                                                                                                                              | 필요한 경우              |               |
| 건물 데이터 제공                                          | [CQD의](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information) 건물 정의를 최신으로 유지하도록 품질 챔피언(또는 관련 이해 관계자)에게 업데이트된 서브넷 정보를 제공합니다. | 필요한 경우              |               |
| 변경 구현                                               | 변경되는 비즈니스 및 기술 요구 사항을 지원하기 위해 Teams 변경 사항을 구현합니다. 네트워크 요소는 다음을 포함할 수 있습니다.<ul><li>방화벽</li><li>VPN</li><li>유선 및 Wi-Fi 네트워크</li><li>인터넷 연결 및 ExpressRoute</li><li>DNS</li></ul>     | 필요한 경우              |               |
| 네트워크 모니터링 및 보고                               | 네트워크 공급자에서 사용할 수 있는 기존 타사 네트워크 관리 도구 및 보고 기능을 사용하여 가용성, 사용률 및 용량 추세에 대한 네트워크 엔드 엔드를 모니터링합니다. 네트워크 용량 계획에 추세 데이터를 사용 합니다.                                                                                                            | 매일, 매주, 월간 |               |
| 용량 계획                                              | 추가 용량 변경을 Teams 수 있는 변화하는 비즈니스 및 기술 요구 사항을 이해하기 위해 서비스 소유자와 공동 작업합니다.                                | 필요한 경우              |               |
| 네트워크 문제 해결 및 수정                        | 지원 Teams, 서비스 소유자 및 주요 이해 관계자를 지원하여 연결, 안정성 또는 품질과 관련된 문제를 Teams 해결합니다. 네트워크 요소는 다음을 포함할 수 있습니다.<ul><li>방화벽</li><li>VPN</li><li>유선 및 Wi-Fi 네트워크</li><li>인터넷 연결 및 ExpressRoute</li><li>DNS</li></ul>    | 필요한 경우              |               |
| 재해 복구 및 고가용성 테스트                | 네트워크 인프라에서 정기적인 고가용성 및 재해 복구 테스트를 수행하여 서비스 서비스에 대해 SLA(서비스 수준 목표) 또는 SLA(서비스 수준 계약)를 충족하는지 Teams 합니다.                                                                                                                                                  | 월간                |               |


### <a name="references"></a>참조 

[Office 365 URL 및 IP 주소 범위](/microsoft-365/enterprise/urls-and-ip-address-ranges)

[데이터척도 구축](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#tenant-data-file-format-and-building-data-file-structure)

<!--ENDOFSECTION-->

## <a name="assess-and-ensure-quality"></a>품질 평가 및 보장 

모든 조직은 품질에 대한 책임이 있는 그룹 또는 개인이 필요합니다. 서비스 관리에서 가장 중요한 역할입니다. Quality Champion 역할은 사용자 경험에 열정을 가지고 있는 개인 또는 그룹에 할당됩니다.
이 역할은 환경의 추세를 식별하고 다른 팀과 함께 작업하여 수정을 주도하는 스폰서십을 식별해야 합니다. 품질 챔피언에 가장 적합한 후보는 일반적으로 고객 서비스 소유자입니다. 조직의 크기와 복잡성에 따라 고품질 사용자 환경을 보장하기 위한 열정을 가지고 있는 사람이나 그룹일 수 있습니다.

품질 챔피언은 CQD(통화 품질 대시보드)와 같은 기존 도구 및 문서화된 프로세스를 활용하여 사용자 환경을 모니터링하고, 품질 추세를 식별하고, 필요한 경우 수정을 구동합니다.
품질 챔피언은 각 팀과 함께 해결 작업을 진행하고 진행률 및 공개 문제에 대한 운영 위원회에 보고해야 합니다.

사용자 [환경 Teams](monitor-call-quality-qos.md)가장 큰 영향을 미치는 주요 영역에서 수정 지침을 평가하고 제공하는 활동이 포함된 에 대한 통화 품질 향상 및 모니터링 을 읽어보아야 합니다. 이 문서에서 제공하는 지침은 CQD를 기본 도구로 사용하여 각 영역을 보고하고 조사하는 데 중점을 두며, 채택 및 영향을 최대화하기 위해 오디오에 초점을 맞추고 있습니다. 오디오 환경을 개선하기 위해 네트워크에 대한 최적화는 비디오 및 데스크톱 공유의 개선으로 직접 변환됩니다.

품질 챔피언을 초기에 지명하는 것이 좋습니다. 지명된 후 통화 품질 모니터링 콘텐츠 [](monitor-call-quality-qos.md) 및 관련 교육 자료에 익숙해지기 시작해야 합니다.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>일일/매주/월간/필요한 작업

| 활동                               | 설명                                                                                                                                                                                                                                                                                                 | 케이던스                             | 팀 할당 |
|----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------|---------------|
| 품질 챔피언 지명 및 교육 | 품질 챔피언을 지명하고 교육합니다.                                                                                                                                                                                                                                                                   | 필요한 경우                           |               |
| QERS(환경 품질 검토) 수행     | QER을 수행하여 품질 및 안정성의 추세를 식별하고, 정의된 대상에 대해 검토하고 조직의 주요 이해 관계자에게 보고합니다.                                                                                                                            | 월간(배포 중 매주) |               |
| 드라이브 수정                      | QER 평가 및 결과에 따라 조직 전체에서 수정 작업을 조정합니다.                                                                                                                                                                                                           | 필요한 경우                           |               |
| CQD에서 건물 데이터 업데이트            | 네트워크에 변경이 적용될 때 CQD에서 새 건물 정의를 업데이트하거나 추가합니다(업로드 [참조).](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information) | 필요한 경우                           |               |
| Quality Champion 역할 채우기      | 조직의 품질에 대한 종단일 책임. 여기에는 다음이 포함됩니다.<ul><li>QER이 정기적으로 수행되고 있는지 확인</li><li>품질 상태에 대한 주요 이해 관계자에게 보고합니다.</li><li>건물 데이터 정의가 최신이 되도록 합니다.</li><li>조직 전체에서 수정 작업을 조정하여 사용자가 사용자와 함께 고품질의 환경을 Teams.</li></ul>          | 매일                               |               |



### <a name="references"></a>참조 


[업로드 CQD에서 테넌트 및 건물 데이터 저장](CQD-upload-tenant-building-data.md)

[통화 품질 향상 및 모니터링 Teams](monitor-call-quality-qos.md)

<!--ENDOFSECTION-->

## <a name="manage-endpoints"></a>엔드포인트 관리

Microsoft Teams 엔드포인트는 클라이언트를 실행하는 PC, Mac, 태블릿 또는 모바일(또는 기타) 디바이스로 정의할 Teams 있습니다. 용어 *엔드포인트는* 디바이스 자체뿐만 아니라 사용자가 디바이스에 연결하는 방법(예: 디바이스의 기본 제공 마이크 또는 스피커, 이어버드 또는 최적화된 헤드셋을 사용하여)을 포위합니다. 배포된 후 엔드포인트를 잊어버려야 합니다. Teams 엔드포인트에는 지속적인 관리 및 유지 관리가 필요합니다. 다음 섹션에서는 집중할 특정 영역을 설명합니다.

### <a name="endpoint-requirements"></a>엔드포인트 요구 사항

클라이언트가 Teams 주요 이점 중 하나는 클라이언트가 자동으로 최신으로 유지되는 것입니다. PC 및 Mac의 클라이언트는 새 빌드를 확인하고 앱이 유휴일 때 새 클라이언트를 다운로드하는 백그라운드 프로세스를 사용하여 업데이트됩니다. 모바일 Teams 앱이 해당 앱 스토어를 통해 최신으로 유지됩니다.

Teams 클라이언트에는 기반 소프트웨어 플랫폼 측면에서 최소 요구 사항이 있습니다. 이러한 요구 사항은 시간이 지날 때 변경될 수 있으므로 변경 내용을 모니터링하는 것이 중요합니다. 예를 들어 Teams 클라이언트에는 최소 iOS 버전이 있습니다. 클라이언트가 인터넷 브라우저를 사용하는 경우 브라우저도 최신으로 유지해야 합니다. 지원되는 플랫폼의 목록은 에 대한 클라이언트 [Microsoft Teams.](get-clients.md)

### <a name="endpoint-firewalls"></a>엔드포인트 방화벽

클라이언트 쪽 방화벽은 사용자 환경에 상당한 영향을 줄 수 있습니다.
클라이언트 쪽 방화벽은 통화 품질에 영향을 주며 통화를 설정하지 못하게 할 수도 있습니다. 클라이언트 방화벽에 대한 적절한 제외를 구성한 후 URL 및 IP 주소 범위의 정보를 Office 365 유지해야 [합니다.](/microsoft-365/enterprise/urls-and-ip-address-ranges) 타사 공급업체는 제외를 업데이트하는 방법에 대한 특정 지침을 제공합니다.

### <a name="wi-fi-drivers"></a>Wi-Fi 드라이버

Wi-Fi 드라이버가 문제가 될 수 있습니다. 예를 들어 드라이버는 액세스 지점 간에 매우 공격적인 로밍 동작이 있을 수 있습니다. 이는 불필요한 액세스 지점 전환을 유도하여 통화 품질이 좋지 않을 수 있습니다. 성능이 좋지 않은 드라이버가 Wi-Fi 품질 검토를 통해 검색될 [](monitor-call-quality-qos.md) 수 있습니다(자세한 내용은 통화 품질 Teams 참조). 새로운 드라이버를 모니터링하고 일반 Wi-Fi 배포하기 전에 테스트되도록 하는 품질 중심 프로세스를 구현해야 합니다.

### <a name="endpoint-management"></a>엔드포인트 관리

지원되는 엔드포인트 및 인터페이스 디바이스(예: 헤드셋)의 카탈로그를 사용 가능하고 유지 관리해야 합니다. 이 카탈로그에는 Envision 및 Onboard 단계의 일부로 선택되어 유효성이 검사된 승인된 디바이스 목록이 포함됩니다. 일반적으로 특정 디바이스는 해당 사용자 특성의 요구 사항을 충족하기 위해 조직의 각 persona 유형에 대해 선택됩니다. 모든 엔드포인트에는 수명 주기가 있으며 이러한 디바이스와 연결된 공급업체 계약, 보증, 교체, 배포 및 복구 정책을 관리해야 합니다.

### <a name="endpoint-troubleshooting"></a>엔드포인트 문제 해결

이전 지침을 따르는 경우에도 조직의 사용자는 여전히 사용자와 관련한 문제가 Teams. 문제는 엔드포인트 자체에 있지 않을 수 있습니다. 일반적으로 클라이언트를 통해 사용자에게 문제의 증상이 나타나고 있습니다. 다음 지침은 문제를 해결하기 위해 취할 수 있는 일반적인 단계를 제공하기 위한 것입니다. 포괄적인 문제 해결 가이드가 아닙니다. 단계는 특정 순서로 제공되지만 명시적으로 따를 필요가 없습니다. 문제의 특성에 따라 적용되지 않을 수 있습니다.

1.  **서비스 상태의 유효성 검사:** 사용자가 경험할 수 있는 문제는 서비스 또는 종속 서비스에 부정적인 영향을 Teams 이벤트와 관련될 수 있습니다. 첫 번째 단계에서는 활성 서비스 문제가 없는지 확인하는 것이 좋습니다. 서비스 [상태 를 Office 365 방법을 문의합니다.](https://support.office.com/article/How-to-check-Office-365-service-health-932AD3AD-533C-418A-B938-6E44E8BC33B0)
    종속 서비스의 상태(예: Exchange, SharePoint, 비즈니스용 OneDrive. 서비스 상태 모니터링은 이전 섹션인 서비스 상태 모니터링 에서 자세히 [설명합니다.](#monitor-service-health)

2.  **클라이언트 연결의 유효성 검사:** 연결 문제로 인해 네트워크에서 기능 또는 로그인 문제가 Teams. 서비스에 대한 연결의 유효성을 검사하는 것이 좋습니다(특히 새 사이트 또는 위치의 경우). 각 사이트에 Office 365 URL 및 [IP](/microsoft-365/enterprise/urls-and-ip-address-ranges) 주소 범위 지침이 따라야 합니다. [Microsoft 네트워크](https://www.microsoft.com/download/details.aspx?id=53885) 평가 도구를 활용하여 연결 테스트를 수행하여 클라우드 음성 기능에 대해 미디어 포트가 올바르게 열렸다는 유효성을 검사할 수 있습니다. 연결 테스트를 실행하는 방법에 대한 자세한 단계는 네트워크 준비 [지침에 제공됩니다.](3-envision-evaluate-my-environment.md#network-readiness)

3.  **알려진 문제 목록을 선택합니다.** 이러한 [Teams](/MicrosoftTeams/troubleshoot/teams) 사용자에 부정적인 영향을 미쳤는지 확인을 위해 문제 해결을 문의합니다. 제공된 해결 방법을 따라(있는 경우) 문제를 해결합니다.

4.  **다음 Microsoft Teams 방문하세요.** Microsoft Teams [커뮤니티는](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams) 전용 공간을 Teams. Teams 커뮤니티는 토론 목록, 블로그 게시물 및 공지 사항을 Teams. 문제를 해결하기 위해 질문을 게시하거나 이전 토론을 검색할 수 있습니다.

5.  **Microsoft 지원에 문의:** 온라인 또는 전화로 Teams Microsoft 지원에 문의할 수 있습니다. 자세한 내용은 비즈니스 제품 [지원에 문의를 참조하세요.](/microsoft-365/admin/contact-support-for-business-products)
    프리미어 고객의 경우 지원 요청은 고객 지원 [담당자(프리미어 고객)의 Microsoft Teams 따라 시작할 수 있습니다.](https://support.microsoft.com/premier/contacts)

### <a name="dailyweeklymonthlyas-needed-tasks"></a>일일/매주/월간/필요한 작업

| 활동                 | 설명                                                                                                                                                                                                                                                                                                                                                                     | 케이던스   | 팀 할당 |
|--------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| 엔드포인트 요구 사항    | 클라이언트 Teams 에 나열된 모든 소프트웨어 요구 사항을 Teams 엔드포인트가 계속 [Microsoft Teams.](get-clients.md)                                                                                                                                                                                       | 월간   |               |
| 엔드포인트 방화벽       | URL 및 IP 주소 범위의 정보를 기반으로 엔드포인트 Office 365 적절한 [제외를 유지 관리합니다.](/microsoft-365/enterprise/urls-and-ip-address-ranges) 타사 공급업체는 제외를 유지하는 방법에 대한 특정 지침을 제공합니다. 변경 내용을 자동으로 알림을 [RSS](https://support.office.com/o365ip/rss) 피드에 구독합니다. | 필요한 경우 |               |
| Wi-Fi 드라이버            | PC에서 Wi-Fi 드라이버를 테스트하고 업데이트합니다. CQD를 사용하여[결과의 유효성을 검사합니다(호출](monitor-call-quality-qos.md)품질 향상 및 Teams.                                                                                                                                                                                                                                                                   | 필요한 경우 |               |
| 엔드포인트 관리      | 지원되는 엔드포인트 및 인터페이스 디바이스(예: 헤드셋)의 카탈로그를 유지 관리합니다. 공급업체 계약, 보증, 배포, 교체 및 복구 정책을 관리합니다.                                                                                                                                                                                                        | 월간   |               |
| 엔드포인트 문제 해결 | 문제 해결 작업에는 연결 확인, 알려진 문제 목록 컨설팅, 로그 수집, 분석 및 Microsoft 지원 또는 타사 공급업체로의 에스컬레이터가 포함됩니다.                                                                                                                                                                                               | 필요한 경우 |               |

### <a name="references"></a>참조 

[Office 365 URL 및 IP 주소 범위](/microsoft-365/enterprise/urls-and-ip-address-ranges)

[Microsoft Teams용 클라이언트 다운로드](get-clients.md)

[Microsoft Teams 커뮤니티](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams)

[Teams 문제 해결](/MicrosoftTeams/troubleshoot/teams)

[서비스 상태 확인 Microsoft Teams](service-health.md)

[비즈니스용 제품에 대한 고객 지원 센터 문의 - 관리자 도움말](/microsoft-365/admin/contact-support-for-business-products)

[프리미어 지원에 문의](https://support.microsoft.com/premier/contacts)

[비디오 Teams 문제 해결](https://www.youtube.com/watch?v=4O4d_7uZTQY)

<!--ENDOFSECTION-->

## <a name="manage-teams"></a>Teams 관리

서비스 Microsoft Teams 배포한 후 관리와 관련된 여러 작업을 수행해야 합니다. 활동 범위는 서비스 및 개별 사용자를 관리하는 것에서 용량 계획 및 프로비전 라이선싱 및 전화 번호까지 다양합니다. 다음 섹션에서는 이러한 일반적인 관리 작업 중 일부를 다 설명합니다.

### <a name="service-administration"></a>서비스 관리

Teams 서비스에는 테넌트 전체를 구성할 수 있는 여러 설정이 있습니다.
테넌트 설정에 대한 변경 내용은 테넌트 설정에 대해 사용하도록 설정된 모든 Teams. 이러한 설정의 자세한 목록은 조직의 설정 Microsoft Teams [관리 를 참조하세요.](enable-features-office-365.md)

### <a name="user-administration"></a>사용자 관리

사용자를 지원하려면 조직에서 관련 작업을 수 없이 요구할 수 있습니다. 특정 작업은 조직마다 다를 수 있습니다. 궁극적으로 이러한 작업은 이러한 운영 업무가 할당된 지원 팀에서 관리해야 합니다. 다음 작업은 일반적으로 사용자 지원에 Teams.

#### <a name="general-tasks"></a>일반 작업

[사용자 액세스 관리 Microsoft Teams](user-access.md)

#### <a name="common-tasks-for-phone-system"></a>일반적인 작업 전화 시스템

[사용자의 전화 번호 할당, 변경 또는 제거](./assign-change-or-remove-a-phone-number-for-a-user.md)

[사용자에 대한 긴급 주소 할당 또는 변경](/skypeforbusiness/what-are-calling-plans-in-office-365/assign-or-change-an-emergency-address-for-a-user)

[조직의 응급 위치 추가, 변경 또는 제거](/skypeforbusiness/what-are-calling-plans-in-office-365/add-change-or-remove-an-emergency-location-for-your-organization)

[다이얼 플랜 만들기 및 관리](create-and-manage-dial-plans.md)

#### <a name="common-tasks-for-audio-conferencing"></a>오디오 회의에 대한 일반적인 작업

[오디오 회의 브리지의 설정 변경](change-the-settings-for-an-audio-conferencing-bridge.md)

[오디오 회의 브리지에서 전화 번호 변경](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)

[사용자의 오디오 회의 설정 관리](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)

[오디오 회의 PIN 재설정](reset-the-audio-conferencing-pin-in-teams.md)

### <a name="license-management"></a>라이선스 관리

조직이 성장하거나 계약할 때 현재 및 미래의 요구에 대한 라이선스를 계획하는 것이 중요합니다. 클라우드 음성 기능(Teams 및 오디오[회의)에](here-s-what-you-get-with-phone-system.md) 대한 라이선스 외에도 기본 전화 시스템 [있습니다.](https://products.office.com/skype-for-business/audio-conferencing)

Teams 경우 전화 시스템 라이선스에 연결된 호출 계획 [라이선스가](calling-plan-landing-page.md) 필요합니다. 계획 라이선스를 호출하면 국내 및/또는 국제 전화 통화를 걸고 받을 수 있습니다. 이러한 계획은 사용량에 따라 설정하고 해당 계획과 연결된 분 풀을 습니다. Communications [크레딧을 프로비전하면](what-are-communications-credits.md) 서비스에서 절대로 실행되지 않습니다.

오디오 회의를 사용하면 전화 접속 회의 및 국내 전화 접속 회의 서비스를 사용할 수 있습니다. 무료 전화 접속 회의 또는 국내외 전화 접속 시나리오로 인해 통신 크레딧이 필요한 추가 요금이 발생할 [수](what-are-communications-credits.md) 있습니다.

통신 크레딧은 통화 계획 및 오디오 회의 라이선스를 모두 보완할 수 있습니다. 호출 계획 라이선스 및 통신 크레딧은 사용량 기반이기 때문에 이에 따라 모니터링 및 프로비전해야 합니다.

[PSTN](/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report) 사용 보고서를 활용하여 통화 계획 분 및 통신 크레딧의 사용량을 모니터링할 수 있습니다. 이 활동의 결과에 따라 라이선스를 그에 따라 조정할 수 있습니다. 곧 이 작업을 보다 효과적으로 지원하기 위해 [PSTN](/skypeforbusiness/skype-for-business-online-reporting/pstn-minute-pools-report) 분 풀 보고서를 제공할 예정입니다.

### <a name="telephone-number-management"></a>전화 번호 관리

다른 공급자의 전화 번호를 포트할 수 Teams 두 가지 방법이 있습니다. 또는 Microsoft의 번호 인벤토리에서 직접 번호를 프로비전할 수 있습니다. 두 메서드는 사용자에 대한 전화 [번호 지우기 에 설명되어 있습니다.](getting-phone-numbers-for-your-users.md)

Microsoft의 번호 인벤토리에서 프로비전할 수 있는 전화 번호 수에는 제한이 있습니다. 제한은 얼마나 많은 전화 번호를 얻을 수 있나요?에 자세히 설명된 여러 [요인에 따라 결정됩니다.](how-many-phone-numbers-can-you-get.md)
제한은 무료 서비스 번호, 무료 서비스 번호 및 구독자(사용자) 번호의 유형에 따라 다릅니다. 각각에는 자체 제한이 있으며 독립적으로 관리해야 합니다. 제한에 가까운 경우(또는 한도에 도달한 경우) 한도로 증분을 신청할 수 있습니다. 이 프로세스는 이전 단락의 문서에 설명되어 있습니다.

서비스를 사용할 수 있는 지역에서 번호를 프로비전할 수 없는 경우도 있습니다. 숫자를 요청하는 프로세스에 대한 자세한 내용은 조직의 전화 번호 [관리를 참조하세요.](/skypeforbusiness/what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)

### <a name="team-creation-optional"></a>팀 만들기(선택 사항)

기본적으로 사서함이 있는 모든 사용자에게는 Exchange Online 그룹을 만들 수 있는 권한이 Microsoft 365, 따라서 팀이 Microsoft Teams. 더 긴밀하게 제어하고 [](assign-roles-permissions.md#permissions-to-create-teams) 새 팀 만들기를 제한하려는 경우(따라서 새 Microsoft 365 그룹 만들기) 그룹 만들기 및 관리 권한을 관리자 집합에 위임할 수 있습니다. 조직에서 이 옵션을 추구하려는 경우 사용자가 할당된 팀에서 처리되는 요청을 제출할 수 있도록 이 문서에 설명된 프로세스를 참조하세요.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>일일/매주/월간/필요한 작업

| 활동                    | 설명                                                                                                                                                                                                                                                                                                                                                                                                             | 케이던스   | 팀 할당 |
|-----------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| 서비스 관리      | 테넌트 전체 Teams 관리합니다.                                                                                                                                                                                                                                                                                                                                                                           | 필요한 경우 |               |
| 사용자 관리         | 사용자 기반 설정 및 라이선스 관리에서 Teams.                                                                                                                                                                                                                                                                                                                                                           | 필요한 경우 |               |
| 라이선스 관리          | [PSTN](/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report) 사용 보고서 및 [PSTN](/skypeforbusiness/skype-for-business-online-reporting/pstn-minute-pools-report) 분 풀 보고서를 활용하여 사용자 및 사용량 기반 라이선스(통화 계획 및 통신 크레딧)에 대한 현재 및 향후 요구 사항을 계획합니다. | 매주    |               |
| 전화 번호 관리 | 향후 증가에 사용할 수 있는 전화 번호를 관리하고 조직의 요구 사항을 충족하기 위해 재고 수준을 조정합니다.                                                                                                                                                                                                                                                                                                | 매주    |               |
| 팀 만들기(선택 사항)    | 팀 만들기 요청을 검토하고 처리합니다.                                                                                                                                                                                                                                                                                                                                                                          | 필요한 경우 |               |

<!--ENDOFSECTION-->

## <a name="improve-and-monitor-call-quality"></a>통화 품질 개선 및 모니터링

[아래와](monitor-call-quality-qos.md) 같은 Teams 개선 및 모니터링에는 사용자 환경 개선에 가장 큰 영향을 미치는 주요 영역에서 수정 지침을 평가하고 제공하는 활동 집합이 포함되어 있습니다.

![환경 품질 검토 중에 검사할 영역의 다이어그램입니다.](media/plan-my-service-management-image2.png "경험 품질 검토 중에 검사할 주요 영역: 오디오, 안정성 및 사용자 설문 조사 결과입니다.")

가이드에 설명된 영역을 지속적으로 평가하고 수정하여 사용자 경험에 부정적인 영향을 줄 수 있습니다. 배포에서 발생하는 대부분의 사용자 환경 문제는 다음 범주로 그룹화할 수 있습니다.

-   불완전한 방화벽 또는 프록시 구성

-   불량 Wi-Fi 적용 범위

-   대역폭 부족

-   VPN

-   미사용 또는 기본 제공 오디오 디바이스 사용

-   문제가 있는 서브넷 또는 네트워크 디바이스

통화 품질 향상 [및](monitor-call-quality-qos.md) 모니터링에 Teams 지침은 CQD(전화 품질 대시보드) Online을 기본 도구로 사용하여 설명된 각 영역을 보고하고 조사하는 데 중점을 두며, 오디오에 중점을 두어 채택 및 영향을 극대화합니다. 오디오 환경을 개선하기 위해 네트워크에 대한 최적화는 비디오 및 데스크톱 공유의 개선으로 직접 변환됩니다.

품질 챔피언을 초기에 지명하는 것이 좋습니다. 지명된 후 에 대한 통화 품질 향상 및 모니터링의 콘텐츠에 [익숙해지기 시작해야 Teams.](monitor-call-quality-qos.md)

<!--ENDOFSECTION-->