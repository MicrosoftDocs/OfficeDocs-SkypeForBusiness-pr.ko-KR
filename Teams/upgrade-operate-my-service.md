---
title: Microsoft Teams에 대한 작업| 서비스 관리 | 품질
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 서비스 상태 모니터링, 네트워크 품질 및 사용량 평가 및 보장을 포함하여 Teams 서비스 관리에 필요한 작업 및 활동
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7da8db4b8ba281082d7f1565800a9f4d543dcb97
ms.sourcegitcommit: 0760416ee0bead3ada93f4d37f8aebc74222bd3c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2022
ms.locfileid: "69019434"
---
# <a name="operate-your-service"></a>서비스 운영

![운영 우수성 단계를 강조하는 업그레이드 경험 다이어그램](media/upgrade-banner-op-excellence.png "운영 우수성 단계에 중점을 둔 업그레이드 경험의 단계")

이 문서는 비즈니스용 Skype Teams로의 업그레이드를 완료하는 즉시 시작되는 업그레이드 경험의 운영 우수성 단계의 일부입니다.

이 문서에서는 업그레이드한 후 조직의 Teams를 성공적으로 운영하기 위한 요구 사항에 대한 개요를 제공합니다. Teams 서비스를 올바르게 운영함으로써 조직에 고품질의 신뢰할 수 있는 환경을 제공하고 있는지 확인할 수 있습니다.

## <a name="introduction-to-the-operations-guide"></a>운영 가이드 소개

운영 가이드에서는 Microsoft Teams의 서비스 관리 기능의 일부로 필요한 모든 작업 및 활동에 대한 개요를 제공합니다.

서비스 관리는 사용자가 배포하고 사용하도록 설정한 후 Microsoft Teams 서비스의 일상적인 작업을 다루는 광범위한 항목입니다. Teams 서비스에는 Microsoft 365 또는 Office 365 및 온-프레미스에 배포된 인프라 구성 요소(예: 네트워킹)가 포함됩니다.

서비스 관리 개념은 대부분의 조직에서 새로운 개념이 아닐 가능성이 높습니다. 기존 서비스와 연결된 프로세스 및 태스크를 이미 구현했을 수 있습니다. 즉, 향후 Teams를 지원하기 위해 오늘 서비스 관리를 계획할 때 현재 프로세스를 보강할 수 있습니다.

서비스 관리에는 Teams 종단 간 관리에 관련된 모든 활동과 프로세스가 포함됩니다. 앞에서 설명한 것처럼 Microsoft 365 또는 Office 365 서비스 자체가 구성하는 인프라인 서비스 관리의 일부 구성 요소는 Microsoft의 책임인 반면, 고객은 사용자가 제공하는 Teams, 네트워크 및 엔드포인트의 다양한 측면을 관리할 책임이 있습니다.

이 가이드의 작업 및 활동은 다음 다이어그램에 표시된 것처럼 8개 범주로 그룹화됩니다. 이러한 각 범주는 다음 섹션에서 확장됩니다.

![작업 및 활동의 범주 목록을 보여 주는 다이어그램](media/operate-my-service-image1.png "Teams의 서비스 관리가 구성하는 작업 및 활동의 범주 목록을 보여 주는 다이어그램 또한 다이어그램은 서비스 관리가 주로 고객 작업임을 보여 줍니다.")

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>의사 결정 지점</td><td><ul><li>Teams에 대한 작업을 구현하는 방법을 결정합니다.</li></ul></td></tr>

<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>다음 단계</td><td><ul><li>운영 가이드를 전체적으로 검토합니다.</li><li>Teams 워크로드의 품질과 안정성을 제공하기 위해 조직의 목표에 부합하는 운영 전략을 구현합니다.</li><li>환경 품질 검토 가이드를 검토합니다.</li><li> Teams 배포가 최대 기능에서 작동하는지 확인하기 위해 정기적으로 환경 품질 검토를 수행하는 운영 전략을 구현합니다.</li></ul></td></tr>

</table>

### <a name="operational-role-mapping"></a>운영 역할 매핑

첫 번째 파일럿 사용자가 사용하도록 설정되면 작업 작업이 시작되므로 구상 단계 중에 작업을 계획하는 것이 중요합니다. 이 가이드에서는 고품질 Teams 배포를 유지하기 위해 매일, 매주, 매월 또는 필요에 따라 수행해야 하는 활동 및 작업을 나열합니다. 이 가이드에서는 이러한 중요한 활동 및 작업을 수행하는 방법에 대한 지식과 지침을 제공합니다.

성공적인 배포의 중요한 구성 요소 중 하나는 구상 단계 초기에 수행하는 계획에 특정 활동을 수행할 담당자를 결정하는 것이 포함되도록 하는 것입니다. 배포에 적용되는 작업 및 활동을 파악한 후에는 해당 작업을 이해하고 할당한 그룹 또는 개인을 따라야 합니다.

사용자가 식별하는 각 팀은 확인된 작업 및 책임에 대해 검토하고 동의해야 하며 준비를 시작해야 합니다. 여기에는 교육 및 준비 상태, 직원 배치 계획에 대한 업데이트 제공 또는 외부 공급자가 제공할 준비가 되도록 하는 것이 포함될 수 있습니다.

이 가이드에 정의된 활동 및 역할은 대부분의 시나리오에서 유효해야 하지만 모든 Teams 배포는 고유합니다. 따라서 이 가이드를 시작점으로 사용하여 요구 사항에 맞게 활동 및 기본 역할을 사용자 지정할 수 있습니다.

각 책임 있는 팀이 서비스를 실행하는 데 필요한 활동을 잘 이해하고 있는지 확인합니다. 첫 번째 파일럿이 시작되기 전에 각 팀이 조직에서 책임을 수락하고 서명하는 것이 중요합니다.

계약이 체결되면 해당 팀이 역할을 운영하기 시작해야 합니다.

<table>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>다음 단계</td>
<td><ul><li>이 문서를 사용하여 운영 역할 매핑 연습을 용이하게 합니다.</li><li>각 지원 팀과 만나 필요한 활동 목록의 각 항목에 이름을 할당합니다.</li><li>할당된 역할에 대한 수락 또는 로그오프를 얻습니다.</li><li>해당 팀에 필요한 활동을 완료할 수 있는 적절한 교육, 준비 상태 및 리소스가 있는지 확인합니다.</li></ul></td></table>

### <a name="teams-service-dependencies"></a>Teams 서비스 종속성

Microsoft Teams는 Microsoft 365 및 Office 365 기술을 결합하여 팀워크를 위한 허브를 제공합니다. 예를 들면 다음과 같습니다.

- Azure AD(Azure Active Directory)는 Teams에 대한 인증 및 권한 부여 서비스를 제공합니다.

- Exchange Online 법적 보존 및 전자 검색과 같은 고급 기능을 제공합니다.

- SharePoint Online은 채널에서 파일을 공유하는 기능을 제공하며, 비즈니스용 OneDrive 비공개 채팅 내에서 파일을 공유하는 메커니즘을 제공합니다.

조직은 온-프레미스 인프라에 대한 기존 투자를 활용할 수도 있습니다. 예를 들어 기존 온-프레미스 Active Directory 계정은 Azure AD Connect를 활용하여 인증에 사용할 수 있습니다. 특정 버전의 Exchange Server Exchange Online 대신 사용할 수 있습니다.

이러한 기술은 사용자에게 풍부하고 협업적이며 지능적인 통신 제품군을 제공하기 위해 함께 제공됩니다. 이러한 긴밀한 통합은 Teams의 주요 이점이지만 이러한 기술 전반에서 서비스 관리에 대한 요구 사항도 유도합니다.

이 가이드에서는 Teams 서비스를 관리하는 데 중점을 두는 주요 영역을 설명합니다. 대부분의 경우 Teams가 의존하는 지원 기술에 대한 서비스 관리 계획이 있습니다. 그렇지 않은 경우 해당 기술 구성 요소(온-프레미스 및 온라인 모두)에 대한 적절한 서비스 관리 계획을 수립해야 합니다. 이렇게 하면 사용자가 Teams에서 고품질의 신뢰할 수 있는 환경을 누릴 수 있습니다.

#### <a name="references"></a>참조

[Microsoft Teams 개요](teams-overview.md)

[Exchange와 Microsoft Teams의 상호 작용 방법](exchange-teams-interact.md)

[SharePoint Online 및 비즈니스용 OneDrive Microsoft Teams와 상호 작용하는 방법](sharepoint-onedrive-interact.md)

[Microsoft Teams 및 비즈니스용 Skype 공존 및 상호 운용성](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

<!--ENDOFSECTION-->

## <a name="operations-guide-activities"></a>작업 가이드 활동

다음 섹션에서는 Microsoft Teams 서비스를 성공적으로 운영하는 데 필요한 활동에 대한 개요를 제공합니다. 여기에는 활동을 이해하고 준비 이니셔티브를 지원하는 데 도움이 되는 도구, 컨텍스트 정보 및 추가 콘텐츠에 대한 참조가 포함됩니다.

<!--ENDOFSECTION-->

## <a name="monitor-service-health"></a>서비스 상태 모니터링

Microsoft Teams 서비스의 전반적인 상태를 이해하여 서비스에 영향을 주는 모든 이벤트를 조직의 다른 사람에게 사전에 경고할 수 있도록 하는 것이 중요합니다. 앞에서 설명한 대로 Teams는 Azure Active Directory, Exchange Online, SharePoint Online 및 비즈니스용 OneDrive 같은 다른 Microsoft 365 및 Office 365 서비스에 의존합니다. 이 때문에 종속 서비스의 상태를 모니터링하는 것이 똑같이 중요합니다.

이 활동을 인시던트 관리 프로세스에 통합하여 사용자, 기술 지원팀 및 운영 팀이 사용자 에스컬레이션 처리 준비를 사전에 알릴 수 있습니다.

다음 섹션에서는 Teams 서비스에 영향을 주는 [서비스 인시던트](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity#Anchor_1) 모니터링에 활용할 수 있는 도구에 대해 설명합니다. 각 도구의 이점과 각 도구를 사용해야 하는 경우에 대한 요약이 다음 표에 포함되어 있습니다.

| 모니터링 도구 | 이점 | 사용 시기 |
|---|---|---|
| Microsoft 365 관리 센터 | 지원되는 브라우저가 있는 모든 디바이스에서 사용할 수 있습니다. | 실시간 알림이 필요하지 않은 경우 를 사용합니다. |
| Microsoft 365 관리 앱 | 모바일 디바이스에 푸시 알림을 제공합니다. | 이동 중 서비스 인시던트에 대한 알림을 받아야 할 때 사용합니다. |
| Microsoft System Center | Microsoft System Center와 통합 | 고급 모니터링 기능 및 알림 지원이 필요한 경우 를 사용합니다. |
| Microsoft 365 서비스 통신 API | Microsoft 365 또는 Office 365 서비스 상태에 프로그래밍 방식으로 액세스합니다. | 타사 모니터링 도구와 통합해야 하거나 고유한 솔루션을 빌드하려는 경우에 사용합니다. |

> [!NOTE]
> **전역 관리자** 또는 **서비스 관리자** 역할이 할당된 개인만 서비스 상태를 볼 수 있습니다.

### <a name="monitoring-with-the-microsoft-365-admin-center"></a>Microsoft 365 관리 센터 사용하여 모니터링

[Microsoft 365 관리 센터](https://portal.office.com/) 종속 서비스 외에도 Teams 서비스의 현재 상태를 볼 수 있는 Service [Health 대시보드](https://portal.office.com/adminportal/home#/servicehealth)를 제공합니다.

### <a name="monitoring-with-the-mobile-app"></a>모바일 앱으로 모니터링

Microsoft 365 관리 앱은 Apple iOS, Android 및 Windows(PC 및 모바일)에서 사용할 수 있습니다. 앱은 관리자에게 서비스 상태 및 향후 변경 내용에 대한 정보를 제공합니다. 앱은 권고가 게시된 직후에 경고할 수 있는 푸시 알림을 지원합니다. 이렇게 하면 상태, 상태 및 서비스에 대한 향후 변경 내용을 최신 상태로 유지할 수 있습니다. 알림 지원을 통해 관리자에게 권장되는 모니터링 도구가 됩니다. 자세한 내용은 다음을 참조하세요.

[모바일 앱 Microsoft 365 관리](https://support.office.com/article/Office-365-Admin-Mobile-App-e16f6421-2a1a-4142-bf9d-9846600a060a)

[Microsoft 365 관리 모바일 앱 다운로드](https://products.office.com/business/manage-office-365-admin-app)

### <a name="monitoring-with-microsoft-system-center"></a>Microsoft System Center를 사용하여 모니터링

Microsoft System Center는 데이터 센터, 클라이언트 디바이스 및 하이브리드 클라우드 IT 환경을 관리하는 데 도움이 되는 통합 관리 플랫폼입니다. 이제 System Center를 사용하는 Microsoft 365 또는 Office 365 관리자에게 관리 팩을 가져올 수 있는 옵션이 있으므로 System Center의 Operations Manager 내에서 모든 서비스 통신을 볼 수 있습니다. 이 도구를 사용하면 구독된 서비스의 상태, 활성 및 해결된 서비스 인시던트 및 메시지 센터 통신(예정된 변경 내용)에 액세스할 수 있습니다. 자세한 내용은 다음 [블로그 게시물을 참조하세요](https://www.microsoft.com/en-us/microsoft-365/blog/2014/07/29/new-office-365-admin-tools/).

System Center를 활용하여 Teams 서비스 상태(및 종속 서비스)를 모니터링하는 경우 관리 팩을 추가로 사용자 지정하여 특정 그룹 또는 인시던트에 대응하도록 식별된 개인에게 경고하거나 알릴 수 있습니다.
이러한 그룹에는 서비스 소유자, 기술 지원팀, 2단계 및 3단계 지원 그룹, 조직의 인시던트 관리자가 포함될 수 있습니다.

### <a name="monitoring-for-advanced-scenarios"></a>고급 시나리오 모니터링

Service Communications API를 활용하여 서비스 상태 및 변경 내용에 프로그래밍 방식으로 액세스하여 서비스 상태 및 향후 변경 내용을 모니터링할 수 있습니다. 이 API를 사용하여 사용자 고유의 모니터링 도구를 만들거나 기존 모니터링 도구를 Microsoft 365 또는 Office 365 서비스 통신에 연결하여 환경을 모니터링하는 방법을 간소화할 수 있습니다. 자세한 내용은 [엔터프라이즈 개발자용 Microsoft 365 또는 Office 365 참조하세요](/office/developer-program/microsoft-365-developer-program-faq).

### <a name="dailyweeklymonthlyas-needed-tasks"></a>매일/매주/매월/필요한 작업

| 활동 | 설명 | 보조 | 팀 할당 |
|---|---|---|---|
| 서비스 상태 모니터링 | 사용 가능한 도구를 사용하여 Microsoft Teams 서비스 상태(및 종속 서비스)를 사전에 모니터링합니다. 종속 서비스에는 Exchange Online, SharePoint Online, 비즈니스용 OneDrive, Azure Active Directory가 포함됩니다. | 실시간 | |
| 인시던트 알림 | Teams 서비스에 영향을 주는 이벤트를 내부 관련자에게 알립니다. 내부 이해 관계자에는 사용자, 기술 지원팀 및 인시던트 관리자가 포함될 수 있습니다. | 필요에 따라 | |

### <a name="references"></a>참조

[Microsoft 365 또는 Office 365 서비스 상태를 확인하는 방법](https://support.office.com/article/How-to-check-Office-365-service-health-932AD3AD-533C-418A-B938-6E44E8BC33B0)

[Microsoft Teams의 서비스 상태 확인](service-health.md)

[Service Health 및 연속성](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity)

<!--ENDOFSECTION-->

## <a name="manage-organizational-change"></a>조직 변경 관리

Microsoft Teams는 클라우드 기반 서비스입니다. 이를 통해 빠른 속도로 새로운 기능과 기능을 제공할 수 있습니다. 지속적인 혁신을 제공하는 것은 조직에 명백한 이점을 제공하지만, 이러한 변경 내용은 사용자 저항 또는 기술 지원팀으로의 에스컬레이션을 방지하기 위해 조직 내에서 적절하게 관리되어야 합니다.

Teams에 대한 업데이트 사용자에게 자동으로 롤아웃됩니다. 사용자는 항상 Teams 서비스에서 사용할 수 있는 최신 클라이언트와 기능을 갖습니다. 사용자에게 Teams 업데이트 출시를 관리할 수 없으므로 효과적인 커뮤니케이션, 교육 및 채택 프로그램을 통해 변경을 관리하는 것이 매우 중요합니다. 사용자가 변화를 인식하고, 이점에 대해 교육하고, 새로운 기능을&mdash;활용할 수 있는 권한을 부여받은 경우 더 빨리 적응하고 변화를 환영할 수 있습니다.

### <a name="monitoring-for-change"></a>변경 모니터링

변경 관리의 첫 번째 단계는 Teams에 대해 계획된 변경 내용을 모니터링하는 것입니다. 이러한 변경 내용을 모니터링하는 가장 좋은 소스는 현재 개발 중이거나 고객에게 배포되거나 완전히 시작된 기능을 나열하는 [Microsoft 365 로드맵](https://www.microsoft.com/microsoft-365/roadmap)입니다. 제공된 필터를 사용하여 Teams 관련 기능을 검색하거나 추가 분석을 위해 Excel 파일에 로드맵을 다운로드할 수 있습니다. 각 기능에 대해 로드맵은 예상되는 릴리스 날짜와 함께 간단한 설명을 제공합니다.

[Microsoft Teams 블로그](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)에서 Teams 제품 업데이트에 대한 모범 사례, 추세 및 뉴스에 대해 알아볼 수 있습니다. Teams에 대한 주요 기능 업데이트는 여기에서 발표될 예정입니다. RSS 피드를 통해 블로그를 구독할 수도 있습니다. 그런 다음 [, RSS 피드를](https://techcommunity.microsoft.com/gxcuf89792/rss/board?board.id=MicrosoftTeamsBlog) Teams 채널에 직접 추가할 수 있으므로 모든 중요한 뉴스가 Teams 내부에서 직접 전달됩니다.

릴리스된 모든 기능은 [Microsoft Teams 릴리스 정보에](https://support.office.com/article/Release-notes-for-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de) 설명되어 있습니다.
여기서는 데스크톱, 웹 및 모바일 디바이스용으로 릴리스된 기능 목록을 찾을 수 있습니다. [도움말](get-help-in-microsoft-teams.md)의 **새로운 기능** 탭에서도 동일한 릴리스 정보 집합을 사용할 수 있습니다.

사용 가능한 리소스를 숙지하고 변경 사항을 모니터링할 해당 소유자를 할당해야 합니다.

### <a name="planning-for-change"></a>변경 계획

Teams 서비스의 향후 변경 내용을 알고 있으므로 다음 단계는 그에 따라 준비하고 계획하는 것입니다. 각 변경 내용을 평가하여 사용자에 대한 커뮤니케이션, 인식 캠페인, 지원 팀 또는 사용자 교육 또는 기능 평가 및 채택 캠페인이 필요한 변경 내용을 결정합니다. 조직에서 변경 관리 팀의 주요 역할입니다. 다음은 변경을 계획하는 데 도움이 되는 샘플 테이블 모음입니다.

#### <a name="feature-cloud-recording-release-date-january-2018"></a>기능: 클라우드 기록(릴리스 날짜: 2018년 1월)

**일반 트랙**

| 준비 상태 변경 | 상태 | 참고/다음 단계 | 소유자 |
|---|---|---|---|
| 법적 검토 | 완료 | 이 기능은 교육 팀을 온보딩하기 위한 필수 구성 요소입니다. | 프로젝트 팀 |

**기술 변경 관리**

| 준비 상태 변경 | 상태 | 참고/다음 단계 | 소유자 |
|---|---|---|---|
| IT 변경 필요 | 예 | 관리 식별된 사용자에 대해서만 기록을 사용하도록 설정해야 합니다. | 지원 팀 |
| 기술 준비 완료 | 예 | | 지원 팀 |
| | | | |

**사용자 변경 관리**

| 준비 상태 변경 | 상태 | 참고/다음 단계 | 소유자 |
|---|---|---|---|
| 사용자 영향 | 낮은 | | |
| 사용자 준비 필요 | 예 | | |
| 통신 준비 | 아니요 | 통신 전자 메일이 초안 작성되었습니다( 검토 보류 중). | 커뮤니케이션 팀 |
| 학습 준비 | 예 | 교육은 기존 Microsoft 비디오를 활용합니다. | 교육 팀 |

**상태 추적**

| 준비 상태 변경 | 상태 | 참고/다음 단계 | 소유자 |
|---|---|---|---|
| 릴리스 상태 | 진행 중 | 임원 스폰서의 검토 보류 중입니다. | 변경 관리 팀 |
| 릴리스 로그오프 | | | |
| 릴리스 날짜 | | | |

Teams를 사용하여 변경 관리를 계획하는 방법에 대한 자세한 내용은 [Microsoft Teams에 대한 변경 관리 전략 만들기를 참조하세요](change-management-strategy.md).

### <a name="dailyweeklymonthlyas-needed-tasks"></a>매일/매주/매월/필요한 작업

| 활동| 설명| 보조| 팀 할당 |
|---|---|---|---|
| 변경 모니터링| Microsoft Teams 서비스에 대한 향후 변경 내용을 모니터링합니다.| 매일||
| 변경 계획| 커뮤니케이션 계획, 인식 캠페인 및 교육을 비롯한 새로운 기능과 기능을 평가하고 계획합니다.| 필요에 따라 ||
| 사용자 준비 상태| 대상 통신, 인식 또는 교육 캠페인을 수행하여 사용자가 향후 변경에 대비할 수 있도록 합니다.| 필요에 따라 ||
| 지원 팀 준비 상태 | 지원 팀이 준비되었는지 확인하기 위해 대상 통신, 인식 또는 교육 캠페인을 수행합니다. 지원 팀에는 "화이트 글러브" 팀, 기술 지원팀, 계층 2 또는 계층 3 지원, 외부 파트너 등이 포함될 수 있습니다. | 필요에 따라 ||

<!--ENDOFSECTION-->

## <a name="assess-teams-usage"></a>Teams 사용량 평가

초기 파일럿이 시작된 후에는 실제 Teams 사용량을 측정하기 위한 정기적인 주기를 설정하는 것이 중요합니다. 이를 통해 조직은 실제 사용량이 구상 단계에서 예측한 사용량과 어떻게 일치하는지에 대한 인사이트를 얻을 수 있습니다. 이 섹션에서는 Teams 사용에 중점을 두지만 Microsoft 365를 측정하고 평가하거나 전체 사용량을 Office 365 광범위한 노력의 일환이어야 합니다.

배포 초기에 자주 사용량을 검토하면 다음을 수행할 수 있습니다.

- 사용자가 Teams를 사용하고 있는지 확인합니다.

- 조직 전체에서 중요한 문제를 만들기 전에 잠재적인 채택 문제를 식별합니다.

- 구상 단계 요구 사항과 실제 사용량 간에 불일치가 있는지 여부를 이해합니다.

사용량이 예상과 다른 경우 배포 문제 또는 채택 계획이 제대로 실행되지 않거나 다른 문제 때문일 수 있습니다. 사용량이 적은 실제 이유에 따라 관리자는 관련 팀과 협력하여 사용 장벽을 제거해야 합니다.

### <a name="measuring-usage-with-the-microsoft-365-admin-center"></a>Microsoft 365 관리 센터 사용량 측정

Teams의 사용량 현황 데이터는 보고 대시보드에서 사용할 수 있습니다. Teams 사용량 데이터는 세 가지 보고서에서 찾을 수 있습니다. 첫 번째 보고서는 Microsoft 365 또는 Office 365 다양한 서비스를 사용하여 사용자가 통신하고 공동 작업하는 방법에 대한 제품 간 보기를 제공합니다. 이 보고서는 [관리 센터의 Microsoft 365 보고서 - 활성 사용자에서](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Active-Users-FC1CF1D0-CD84-43FD-ADB7-A4C4DFA8112D) 찾을 수 있습니다.

다른 두 보고서는 Teams 관련 보고서이며 사용자 및 디바이스 관점에서 Teams 사용에 대한 자세한 정보를 제공합니다. 두 보고서 모두 여기에서 찾을 수 있습니다.

[Microsoft Teams 디바이스 사용 현황 보고서](/microsoftteams/teams-analytics-and-reports/device-usage-report)

[Microsoft Teams 사용자 활동 보고서](/microsoft-365/admin/activity-reports/microsoft-teams-user-activity-preview)

#### <a name="required-permissions"></a>필요한 사용 권한

관리 센터의 사용량 보고서에는 **전역 관리자** 역할이 할당된 사용자 또는 제품별 관리자 역할(**Exchange 관리자**, **비즈니스용 Skype 관리자**, **SharePoint 관리자**)이 액세스할 수 있습니다.

또한 **보고서 읽기** 권한자 역할은 보고서에 액세스해야 하지만 관리자 수준 권한이 필요한 작업을 수행하지 않는 사용자에게 사용할 수 있습니다. 이 역할을 할당하여 이해 관계자인 모든 사람에게 사용 현황 보고서를 제공하여 채택을 모니터링하고 추진합니다. 사용 가능한 다양한 역할에 대한 자세한 내용은 [Microsoft 365 관리자 역할 정보를 참조하세요](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).

### <a name="assessing-usage"></a>사용량 평가

보고 대시보드를 사용하여 사용량을 측정한 후에는 측정된 사용량을 프로젝트의 구상 단계에서 정의한 KSI(주요 성공 지표)와 비교하는 것이 중요합니다. 활성 사용으로 정의될 수 있는 KSI 또는 활성 사용과 간접적으로 연결된 KSI를 정의할 수 있습니다.

추가 사이트 또는 사용자에게 롤아웃을 다시 시작하기 전에 실제 사용량과 계획된 사용량 간의 차이를 식별하는 것이 중요합니다. 다음 사이트 또는 사용자 일괄 처리에서 동일한 문제가 발생하지 않도록 하기 위해 활용할 수 있는 이 활동의 일부로 조직 학습을 식별할 수 있습니다.

먼저 이것이 채택 또는 기술적 문제인지를 정확히 파악합니다. 먼저 아래 항목을 조사하여 문제가 있는 위치를 확인합니다.

1. 환경 품질 검토를 수행하여 [품질 유효성을 검사합니다](upgrade-monitor-quality.md).

2. 기술 지원팀과 협력하여 사용자가 서비스에 액세스하거나 사용하지 못하도록 하는 추세 기술 문제가 없는지 확인합니다. 문제 추세가 있는 경우 이 문서의 뒷부 [분에 있는 엔드포인트 문제 해결](#endpoint-troubleshooting) 섹션을 사용하여 지원을 진행하기 전에 문제를 해결해 보세요.

3. 교육 및 채택 팀과 협력하여 사용자로부터 직접 피드백을 수집하고(이 문서의 뒷부분에서 [사용자 감정 평가](#assess-user-sentiment) 참조), 인식 및 채택 활동의 효과를 확인합니다.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>매일/매주/매월/필요한 작업

| 활동 | 설명 | 보조 | 팀 할당 |
|---|---|---|---|
| 사용량 측정(사용 단계) | 사용 단계 중에 사이트가 계속 온보딩됨에 따라 Teams 사용량을 측정하고 평가합니다. 필요에 따라 사용 문제를 해결합니다. | 주간 | |
| 사용량 측정 | 배포가 완료된 후 드라이브 값 단계에서 Teams 사용량을 측정하고 평가합니다. 필요에 따라 사용 문제를 해결합니다. | 격주 | |
| (드라이브 값 단계) | | | |
| 채택 계획 업데이트 | 측정된 사용량이 계획 목표와 비교되는 방식에 따라 채택 계획을 업데이트합니다. | 필요에 따라 | |

### <a name="references"></a>참조

[Microsoft 365 관리 센터 정보](https://support.office.com/article/About-the-Office-365-admin-center-758befc4-0888-4009-9f14-0d147402fd23)

[Microsoft 365 관리 센터 활동 보고서](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)

<!--ENDOFSECTION-->

## <a name="assess-user-sentiment"></a>사용자 감정 평가

사용자 감정을 이해하면 Teams 배포의 성공을 측정하기 위한 핵심 지표로 작용할 수 있습니다. 사용자 피드백은 조직의 변경 내용을 유도할 수 있습니다. 여기에는 통신 계획, 교육 프로그램 또는 사용자에게 지원을 제공하는 방식이 포함될 수 있습니다.

피드백을 조기에 받고 프로젝트의 수명 주기 동안 그리고 그 이후에도 사용자 감정을 계속 평가하는 것이 중요합니다. 다음 지침을 사용하여 조직에서 피드백을 검색할 간격을 결정합니다.

- **프로젝트 시작: 프로젝트** 시작 시 사용자 감정을 평가하여 사용자가 Teams 환경에 대해 어떻게 생각하는지 조기에 확인할 수 있습니다.

- **주요 중요 시점 이후**: 프로젝트 수명 주기 전반에 걸쳐 피드백을 수집하여 사용자 감정을 지속적으로 측정하고 필요에 따라 변경할 수 있습니다. 이는 주요 마일스톤 이후에 특히 유용합니다.

- **프로젝트 결론**: 프로젝트 종료 시 사용자 감정을 평가하면 얼마나 잘 수행했는지, 작업을 수행해야 하는 위치를 알려주고 이전 설문 조사와 결과를 비교할 수 있습니다.

- **진행 중**: 사용자 감정을 무기한으로 측정합니다. 사용자 감정의 변경은 조직의 환경 변경 또는 Teams 서비스의 변경으로 인해 발생할 수 있습니다. 정기적으로 사용자 감정을 측정하여 서비스 관리 팀이 얼마나 잘 수행하고 있으며 조직이 Teams 서비스의 변경에 어떻게 대응하고 있는지 이해할 수 있습니다.

사용자 감정은 다양한 방법을 통해 평가할 수 있습니다. 여기에는 이메일 설문 조사, 대면 또는 전화 스타일 인터뷰 또는 Teams 또는 Yammer에서 피드백 채널 만들기가 포함될 수 있습니다. 자세한 내용은 [Microsoft Teams의 사용자 피드백 방법에 대한 모범 사례를 참조하세요](best-practices-feedback.md).

다음 섹션에 설명된 NPS(Net Promotor Score)라는 사용자 감정을 평가하는 업계 전반의 접근 방식을 사용할 수도 있습니다.

### <a name="nps"></a>Nps

NPS(순 프로모터 점수)는 업계 전반의 고객 충성도 메트릭이며 사용자 감정을 평가하는 데 사용할 수 있는 좋은 방법입니다. NPS는 "동료에게 Teams를 추천할 가능성이 얼마나 됩니까?"라는 두 가지 질문을 하고 자유형 질문인 "왜?"를 질문하여 계산할 수 있습니다.

NPS는 -100에서 100 사이의 인덱스로, 고객의 회사 제품 또는 서비스 추천 의지를 측정합니다. NPS는 이메일 또는 기타 전자 수단을 통해 사용자에게 전달되는 익명 설문 조사를 기반으로 합니다. NPS는 공급자와 소비자 간의 충성도를 측정합니다. 이는 사용자에게 1에서 10까지의 경험을 평가하도록 요청하는 하나의 질문으로 구성되며 추가 설명을 제공하는 옵션으로 구성됩니다. 그러면 사용자는 다음 등급에 따라 분류됩니다.

- 9 또는 10은 프로모터: 서비스를 홍보하고 다른 사람들에게 연료를 공급할 충성스러운 매니아입니다.

- 7 또는 8은 수동: 만족하지만 열정적이지 않고 다른 서비스 또는 제안에 취약합니다.

- 1에서 6까지는 비방자: 서비스를 손상시키고 성장을 저해할 수 있는 불행한 고객입니다.

![NPS 배율을 보여 주는 다이어그램입니다.](media/operate-my-service-image2.png "이 다이어그램은 NPS 배율을 보여 줍니다. 0에서 6까지의 순위는 비방이고, 7~8은 수동이며, 9~10은 프로모터임을 보여줍니다.")

기본 NPS 번호는 유용하지만 사용자 주석 분석에서 가장 많은 값을 얻을 수 있습니다. 사용자가 Teams를 다른 사람에게 추천하는 이유를 이해하는 데 도움이 됩니다. 이러한 주석은 프로젝트 또는 서비스 관리 팀이 양질의 서비스를 제공하는 데 필요한 조정을 이해하는 데 도움이 되는 귀중한 피드백을 제공할 수 있습니다.

조직에 NPS 설문 조사를 제공하려면 선호하는 온라인 설문 조사 도구를 활용할 수 있습니다.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>매일/매주/매월/필요한 작업

| 활동 | 설명 | 보조 | 팀 할당 |
|---|---|---|---|
| 사용자 감정 평가 | 설문 조사 또는 인터뷰를 사용하거나 Teams 또는 Yammer의 피드백 채널을 통해 사용자 감정을 캡처하고 평가합니다. | 필요에 따라 | |
| 채택 계획 업데이트 | 사용자 피드백에 따라 조직의 변화를 주도합니다. 여기에는 통신 계획, 교육 프로그램 또는 사용자에게 지원을 제공하는 방식이 포함될 수 있습니다. | 필요에 따라 | |

### <a name="references"></a>참조

[순 프로모터 점수](https://en.wikipedia.org/wiki/Net_Promoter)

[Yammer를 사용하여 피드백 수집](https://techcommunity.microsoft.com/t5/Yammer-Blog/The-Microsoft-Teams-team-uses-Yammer/ba-p/55210)

[사용자 피드백에 대한 모범 사례](best-practices-feedback.md)

<!--ENDOFSECTION-->

## <a name="manage-network-quality"></a>네트워크 품질 관리

많은 핵심 계획 요소는 Microsoft Teams 서비스에 대한 고품질의 효율적인 경로를 보장하기 위해 네트워크 인프라를 최적화, 오른쪽 크기 조정 및 수정하는 데 사용됩니다. 계획 작업 및 요구 사항은 [네트워크 준비](prepare-network.md) 지침에서 다룹니다. 업그레이드, 확장 또는 기타 비즈니스 요구 사항으로 인해 시간이 지남에 따라 네트워크가 발전하는 경우가 많습니다. 네트워크 계획 활동에서 Teams에 대한 요구 사항을 고려해야 합니다.

네트워크 계획은 Teams 배포의 중요한 측면이지만 변화하는 비즈니스 또는 기술 요구 사항에 따라 네트워크를 정상 상태로 유지하고 최신 상태를 유지하는 것이 똑같이 중요합니다.

네트워크의 상태를 확인하려면 정기적으로 여러 작업 작업을 수행해야 합니다.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>매일/매주/매월/필요한 작업

| 활동 | 설명 | 보조 | 팀 할당 |
|---|---|---|---|
| Microsoft 365 또는 Office 365 IP 및 URL 모니터링 | 제공된 [RSS 피드](https://go.microsoft.com/fwlink/p/?linkid=236301)를 사용하여 [Office 365 URL 및 IP 주소 범위에](/microsoft-365/enterprise/urls-and-ip-address-ranges) 대한 변경 내용을 모니터링하고 해당 네트워킹 그룹에 대한 변경 요청을 시작합니다. | 매일 | |
| Microsoft 365 또는 Office 365 IP 및 URL 변경 내용에 따라 네트워크 업데이트 | 해당 네트워크 구성 요소(방화벽, 프록시 서버, VPN, 클라이언트 쪽 방화벽 등)를 업데이트하여 [Office 365 URL 및 IP 주소 범위](/microsoft-365/enterprise/urls-and-ip-address-ranges)의 변경 내용을 반영합니다. | 필요에 따라 | |
| 빌드 데이터 제공 | [CQD의 건물 정의를](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information) 최신 상태로 유지할 수 있도록 품질 챔피언(또는 관련 관련자)에게 업데이트된 서브넷 정보를 제공합니다. | 필요에 따라 | |
| 변경 구현 | 변경된 Teams 비즈니스 및 기술 요구 사항을 지원하기 위해 네트워크의 변경 내용을 구현합니다. 네트워크 요소는 다음을 포함할 수 있습니다.<ul><li>방화벽</li><li>Vpn</li><li>유선 및 Wi-Fi 네트워크</li><li>인터넷 연결 및 ExpressRoute</li><li>DNS</li></ul> | 필요에 따라 | |
| 네트워크 모니터링 및 보고 | 기존 타사 네트워크 관리 도구 및 네트워크 공급자에서 사용할 수 있는 보고 기능을 사용하여 네트워크 엔드 투 엔드에서 가용성, 사용률 및 용량 추세를 모니터링합니다. 네트워크 용량 계획에 추세 데이터를 사용합니다. | 매일, 매주, 매월 | |
| 용량 계획 | Teams 서비스 소유자와 협력하여 추가 용량 변경을 유도할 수 있는 변화하는 비즈니스 및 기술 요구 사항을 이해합니다.  | 필요에 따라 | |
| 네트워크 문제 해결 및 수정 | Teams 지원팀, 서비스 소유자 및 주요 이해 관계자가 Teams 연결, 안정성 또는 품질과 관련된 문제를 해결하고 수정할 수 있도록 지원합니다. 네트워크 요소는 다음을 포함할 수 있습니다.<ul><li>방화벽</li><li>Vpn</li><li>유선 및 Wi-Fi 네트워크</li><li>인터넷 연결 및 ExpressRoute</li><li>DNS</li></ul> | 필요에 따라 | |
| 재해 복구 및 고가용성 테스트 | 네트워크 인프라에서 정기적인 고가용성 및 재해 복구 테스트를 수행하여 Teams 서비스에 대해 명시된 SLO(서비스 수준 목표) 또는 SLA(서비스 수준 계약)를 충족하는지 확인합니다. | 월별 | |

### <a name="references"></a>참조

[Office 365 URL 및 IP 주소 범위](/microsoft-365/enterprise/urls-and-ip-address-ranges)

[데이터 스키마 빌드](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#tenant-data-file-format-and-building-data-file-structure)

<!--ENDOFSECTION-->

## <a name="assess-and-ensure-quality"></a>품질 평가 및 보장

모든 조직에는 품질에 대한 책임을 져야 하는 그룹 또는 개인이 필요합니다. 이는 서비스 관리에서 가장 중요한 역할입니다. 품질 챔피언 역할은 사용자의 경험에 열정적 인 사람 또는 그룹에 할당됩니다.
이 역할에는 환경의 추세를 식별하는 기술과 다른 팀과 협력하여 수정을 추진하기 위한 스폰서쉽이 필요합니다. 품질 챔피언에 가장 적합한 후보는 일반적으로 고객 서비스 소유자입니다. 조직의 규모와 복잡성에 따라 고품질 사용자 환경을 보장하려는 열정이 있는 사람 또는 그룹이 될 수 있습니다.

품질 챔피언은 CQD(통화 품질 대시보드) 및 [Teams의 통화 품질 개선 및 모니터링](monitor-call-quality-qos.md)과 같은 기존 도구 및 문서화된 프로세스를 활용하여 사용자 환경을 모니터링하고, 품질 추세를 식별하고, 필요한 경우 수정을 추진합니다.
품질 챔피언은 각 팀과 협력하여 수정 조치를 추진하고 진행 상황 및 공개 문제에 대해 운영 위원회에 보고해야 합니다.

[Teams의 통화 품질 개선 및 모니터링](monitor-call-quality-qos.md) 에는 사용자 환경 개선에 가장 큰 영향을 미치는 주요 영역에서 수정 지침을 평가하고 제공하는 활동이 포함됩니다. 품질 환경 검토 가이드에 제공된 지침은 채택 및 영향을 극대화하기 위해 오디오에 중점을 두고 각 영역을 보고하고 조사하는 기본 도구로 CQD Online을 사용하는 데 중점을 둡니다. 오디오 환경을 개선하기 위해 네트워크에 대한 모든 최적화는 비디오 및 데스크톱 공유의 개선으로 직접 변환됩니다.

일찍부터 품질 챔피언을 지명하는 것이 좋습니다. 지명되면 Teams 및 관련 교육 자료에 [대한 통화 품질 개선 및 모니터링](monitor-call-quality-qos.md) 의 콘텐츠에 익숙해져야 합니다.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>매일/매주/매월/필요한 작업

| 활동 | 설명 | 보조 | 팀 할당 |
|---|---|---|---|
| 품질 챔피언 지명 및 훈련 | 품질 챔피언을 지명하고 훈련합니다. | 필요에 따라 | |
| QRS(경험 품질 검토) 수행 | QER를 수행하여 품질 및 안정성 추세를 식별하고, 정의된 대상에 대해 검토하고, 조직의 주요 관련자에게 보고합니다. | 월별(배포 중 매주) | |
| 드라이브 수정 | QER 평가 및 결과에 따라 조직 전체의 수정 작업을 조정합니다. | 필요에 따라 | |
| CQD에서 빌드 데이터 업데이트 | 네트워크를 변경할 때 CQD에서 새 건물 정의를 업데이트하거나 추가합니다( [빌드 정보 업로드](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information) 참조). | 필요에 따라 | |
| 품질 챔피언 역할 채우기 | 조직의 품질에 대한 종단 간 책임입니다. 여기에는 다음이 포함됩니다.<ul><li>QER가 정기적으로 수행되고 있는지 확인합니다.</li><li>품질 상태에 대해 주요 관련자에게 보고합니다.</li><li>빌드 데이터 정의가 최신 상태인지 확인합니다.</li><li>조직 전체에서 수정 작업을 조정하여 사용자가 Teams에 대한 고품질 환경을 갖출 수 있도록 합니다.</li></ul> | 매일 | |

### <a name="references"></a>참조

[건물 정보 업로드](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information)

[Teams의 통화 품질 개선 및 모니터링](monitor-call-quality-qos.md)

<!--ENDOFSECTION-->

## <a name="manage-endpoints"></a>엔드포인트 관리

Microsoft Teams 엔드포인트는 Teams 클라이언트를 실행하는 모든 PC, Mac, 태블릿 또는 모바일(또는 기타) 디바이스로 정의할 수 있습니다. *엔드포인트* 라는 용어는 디바이스 자체뿐만 아니라 디바이스의 기본 제공 마이크 또는 스피커, 이어버드 또는 최적화된 헤드셋을 사용하여 사용자가 디바이스에 연결하는 방법을 포함합니다. 배포된 후에는 엔드포인트를 잊어서는 안 됩니다. Teams 엔드포인트에는 지속적인 관리 및 유지 관리가 필요합니다. 다음 섹션에서는 집중해야 할 특정 영역에 대해 설명합니다.

### <a name="endpoint-requirements"></a>엔드포인트 요구 사항

Teams의 주요 이점 중 하나는 클라이언트가 자동으로 최신 상태로 유지된다는 것입니다. PC 및 Mac의 클라이언트는 새 빌드를 확인하고 앱이 유휴 상태일 때 새 클라이언트를 다운로드하는 백그라운드 프로세스를 사용하여 업데이트됩니다. Teams 모바일 앱은 해당 앱 스토어를 통해 최신 상태로 유지됩니다.

Teams 클라이언트에는 기본 소프트웨어 플랫폼 측면에서 최소 요구 사항이 있습니다. 이러한 요구 사항은 시간이 지남에 따라 변경될 수 있으므로 변경 내용을 모니터링하는 것이 중요합니다. 예를 들어 Teams 클라이언트에는 최소 iOS 버전이 있습니다. 클라이언트가 인터넷 브라우저를 사용하는 경우 브라우저도 최신 상태로 유지해야 합니다. 지원되는 플랫폼 목록은 [Microsoft Teams용 클라이언트 가져오기](get-clients.md)에서 찾을 수 있습니다.

### <a name="endpoint-firewalls"></a>엔드포인트 방화벽

클라이언트 쪽 방화벽은 사용자 환경에 상당한 영향을 미칠 수 있습니다.
클라이언트 쪽 방화벽은 통화 품질에 영향을 줄 수 있으며 호출이 설정되지 않도록 방지할 수도 있습니다. 클라이언트 방화벽에 대한 적절한 제외가 구성되면 [Office 365 URL 및 IP 주소 범위](/microsoft-365/enterprise/urls-and-ip-address-ranges)의 정보를 기반으로 최신 상태로 유지되어야 합니다. 타사 공급업체에는 제외를 업데이트하는 방법에 대한 특정 지침이 있습니다.

### <a name="wi-fi-drivers"></a>Wi-Fi 드라이버

Wi-Fi 드라이버가 문제가 될 수 있습니다. 예를 들어 드라이버는 액세스 지점 간에 매우 공격적인 로밍 동작을 통해 불필요한 액세스 지점 전환을 유도하여 통화 품질이 저하될 수 있습니다. 성능이 저하된 Wi-Fi 드라이버는 품질 검토(자세한 내용은 [Teams 통화 품질 개선 및 모니터링](monitor-call-quality-qos.md) 참조)를 통해 검색할 수 있습니다. 새 Wi-Fi 드라이버를 모니터링하고 일반 사용자 모집단에 배포하기 전에 테스트되었는지 확인하는 품질 기반 프로세스를 구현해야 합니다.

### <a name="endpoint-management"></a>엔드포인트 관리

지원되는 엔드포인트 및 인터페이스 디바이스(예: 헤드셋)의 카탈로그를 사용할 수 있고 유지 관리해야 합니다. 이 카탈로그에는 구상 및 온보딩 단계의 일부로 선택되고 유효성이 검사된 승인된 디바이스 목록이 포함됩니다. 일반적으로 조직의 각 가상 사용자 유형에 대해 특정 디바이스가 선택되어 해당 가상 사용자의 특성 요구 사항을 충족합니다. 모든 엔드포인트에는 수명 주기가 있으며 이러한 디바이스와 연결된 공급업체 계약, 보증, 교체, 배포 및 수리 정책을 관리해야 합니다.

### <a name="endpoint-troubleshooting"></a>엔드포인트 문제 해결

이전 지침을 따랐더라도 조직의 사용자는 여전히 Teams에 문제가 발생할 수 있습니다. 엔드포인트 자체에 문제가 없을 수도 있지만 문제의 증상은 일반적으로 클라이언트를 통해 사용자에게 표시됩니다. 다음 지침은 문제를 해결하기 위해 수행할 수 있는 일반적인 단계를 제공하기 위한 것입니다. 포괄적인 문제 해결 가이드가 아닙니다. 단계는 특정 순서로 제공되지만 명시적으로 따를 필요는 없으며 문제의 특성에 따라 적용되지 않을 수 있습니다.

1. **서비스 상태 유효성 검사:** 사용자에게 발생할 수 있는 문제는 Teams 서비스 또는 종속 서비스에 부정적인 영향을 미치는 이벤트와 관련이 있을 수 있습니다. 첫 번째 단계로 활성 서비스 문제가 없는지 확인하는 것이 좋습니다. [Microsoft 365 서비스 상태를 확인하는 방법을](/office365/enterprise/view-service-health) 참조하세요. 종속 서비스의 상태(예: Exchange, SharePoint, 비즈니스용 OneDrive)를 확인해야 합니다. 서비스 상태에 대한 모니터링은 이전 섹션인 [서비스 상태 모니터링](#monitor-service-health)에서 자세히 설명합니다.

2. **클라이언트 연결 유효성 검사:** 연결 문제로 인해 Teams의 기능 또는 로그인 문제가 발생합니다. 서비스에 대한 연결의 유효성을 검사하는 것이 좋습니다(특히 새 사이트 또는 위치의 경우). 각 사이트에 대해 다음 [Office 365 URL 및 IP 주소 범위](/microsoft-365/enterprise/urls-and-ip-address-ranges) 지침을 따르는지 확인합니다. [Microsoft 네트워크 평가 도구를](https://www.microsoft.com/download/details.aspx?id=53885) 활용하여 연결 테스트를 수행하여 Teams 기능에 대해 미디어 포트가 올바르게 열려 있는지 확인할 수 있습니다. 연결 테스트를 실행하는 방법에 대한 자세한 단계는 [네트워크 준비](prepare-network.md) 지침에 제공됩니다.

3. **알려진 문제 목록을 확인합니다** . 사용자가 이러한 문제 중 하나에 의해 부정적인 영향을 받았는지 확인하려면 [Teams 문제 해결](/MicrosoftTeams/troubleshoot/teams) 을 참조하세요. 제공된 해결 방법(있는 경우)에 따라 문제를 해결합니다.

4. **Microsoft Teams 커뮤니티를 방문하세요** . [Microsoft Teams 커뮤니티는 Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams) 전용 공간을 제공합니다. Teams 커뮤니티는 Teams를 중심으로 토론 목록, 블로그 게시물 및 공지 사항을 제공합니다. 질문을 게시하거나 문제에 대한 해결 방법을 찾기 위해 이전 토론을 검색할 수 있습니다.

5. **Microsoft 지원 문의:** 온라인 또는 전화로 Teams 관련 문제에 대해 Microsoft 지원 문의할 수 있습니다. 자세한 내용은 [비즈니스 제품 지원 문의 - 관리 도움말을 참조하세요](/microsoft-365/admin/contact-support-for-business-products). 프리미어 고객의 경우 [Microsoft Teams(프리미어 고객)에 대한 고객 지원 문의](https://support.microsoft.com/premier/contacts)의 지침에 따라 지원 요청을 시작할 수 있습니다.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>매일/매주/매월/필요한 작업

| 활동 | 설명 | 보조 | 팀 할당 |
|---|---|---|---|
| 엔드포인트 요구 사항 | Teams 엔드포인트가 Microsoft Teams용 [클라이언트 가져오기](get-clients.md)에 나열된 Teams의 모든 소프트웨어 요구 사항을 계속 충족하는지 확인합니다. | 월별 | |
| 엔드포인트 방화벽 | [Office 365 URL 및 IP 주소 범위](/microsoft-365/enterprise/urls-and-ip-address-ranges)의 정보를 기반으로 엔드포인트 방화벽에서 적절한 제외를 유지 관리합니다. 타사 공급업체에는 제외를 유지하는 방법에 대한 특정 지침이 있습니다. [RSS 피드](https://support.office.com/o365ip/rss)를 구독하여 변경 내용을 자동으로 알릴 수 있습니다. | 필요에 따라 | |
| Wi-Fi 드라이버 | PC에서 Wi-Fi 드라이버를 테스트하고 업데이트합니다. CQD를 사용하여 결과의 유효성을 검사합니다([Teams의 통화 품질 개선 및 모니터링](monitor-call-quality-qos.md)). | 필요에 따라 | |
| 엔드포인트 관리 | 지원되는 엔드포인트 및 인터페이스 디바이스(예: 헤드셋)의 카탈로그를 유지 관리합니다. 공급업체 계약, 보증, 배포, 교체 및 수리 정책을 관리합니다. | 월별 | |
| 엔드포인트 문제 해결 | 문제 해결 작업에는 연결 확인, 알려진 문제 목록 컨설팅, 로그 수집, 분석 및 Microsoft 지원 또는 타사 공급업체로의 에스컬레이션이 포함될 수 있습니다. | 필요에 따라 | |

### <a name="references"></a>참조

[Office 365 URL 및 IP 주소 범위](/microsoft-365/enterprise/urls-and-ip-address-ranges)

[Microsoft Teams용 클라이언트 다운로드](get-clients.md)

[Microsoft Teams 커뮤니티](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams)

[Teams 문제 해결](/MicrosoftTeams/troubleshoot/teams)

[Microsoft Teams의 서비스 상태 확인](service-health.md)

[비즈니스용 제품에 대한 고객 지원 센터 문의 - 관리자 도움말](https://support.office.com/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)

[프리미어 지원에 문의](https://support.microsoft.com/premier/contacts)

[Teams 문제 해결 비디오](https://www.youtube.com/watch?v=4O4d_7uZTQY)

<!--ENDOFSECTION-->

## <a name="manage-teams"></a>Teams 관리

Microsoft Teams 서비스가 배포된 후에는 해당 관리와 관련된 여러 활동을 수행해야 합니다. 활동은 서비스 및 개별 사용자 관리에서 용량 계획 및 라이선스 및 전화 번호 프로비전에 이르기까지 다양합니다. 다음 섹션에서는 이러한 일반적인 관리 작업 중 일부를 다룹니다.

### <a name="service-administration"></a>서비스 관리

Teams 서비스에는 테넌트 전체로 구성할 수 있는 여러 설정이 있습니다.
테넌트 설정을 변경하면 Teams를 사용하도록 설정된 모든 사용자에게 영향을 줍니다. 이러한 설정의 자세한 목록은 [조직의 Microsoft Teams 설정 관리를 참조하세요](enable-features-office-365.md).

### <a name="user-administration"></a>사용자 관리

사용자를 지원하기 위해 조직에는 여러 관련 작업이 필요할 수 있습니다. 특정 작업은 조직마다 다릅니다. 궁극적으로 이러한 작업은 이러한 운영 업무가 할당된 지원 팀에서 관리해야 합니다. Teams에서 사용자를 지원하려면 일반적으로 다음 작업이 필요합니다.

#### <a name="general-tasks"></a>일반 작업

[Microsoft Teams에 대한 사용자 액세스 관리](user-access.md)

### <a name="team-creation-optional"></a>팀 만들기(선택 사항)

기본적으로 Exchange Online 사서함이 있는 모든 사용자에게는 Microsoft 365 그룹 및 Microsoft Teams 팀을 만들 수 있는 권한이 있습니다. 더 엄격하게 제어하고 [새 팀 만들기](assign-roles-permissions.md) (따라서 새 Microsoft 365 그룹 만들기)를 제한하려는 경우 그룹 만들기 및 관리 권한을 관리자 집합에 위임할 수 있습니다. 조직에서 이 옵션을 사용하려는 경우 사용자가 할당된 팀에서 처리한 요청을 제출할 수 있도록 이 문서에 설명된 프로세스를 참조하세요.

<!--ENDOFSECTION-->

### <a name="dailyweeklymonthlyas-needed-tasks"></a>매일/매주/매월/필요한 작업

| 활동 | 설명 | 보조 | 팀 할당 |
|---|---|---|---|
| 서비스 관리 | 테넌트 전체 Teams 설정 관리. | 필요에 따라 | |
| 사용자 관리 | Teams에서 사용자 기반 설정 및 라이선스 관리. | 필요에 따라 | |
| 라이선스 관리 | [PSTN 사용량 보고서](/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report) 및 [PSTN 분 풀](/skypeforbusiness/skype-for-business-online-reporting/pstn-minute-pools-report) 보고서를 활용하여 사용자 및 소비 기반 라이선스(통화 플랜 및 통신 크레딧)에 대한 현재 및 미래의 요구 사항을 계획합니다. | 주간 | |
| 전화 번호 관리 | 향후 증가에 사용할 수 있는 전화 번호를 관리하고 조직의 요구에 맞게 재고 수준을 조정합니다. | 주간 | |
| 팀 만들기(선택 사항) | 팀 만들기에 대한 요청을 검토하고 처리합니다. | 필요에 따라 | |

<!--ENDOFSECTION-->