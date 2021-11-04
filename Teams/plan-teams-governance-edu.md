---
title: 관리자용 Microsoft 교육 거버넌스 FAQ
author: cichur
ms.author: v-mahoffman
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Microsoft Education 그룹을 사용하는 관리자로부터 자주 묻는 질문에 대한 Teams.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 1e9af313bc24919f96008d7f1ff5bf7383df3260
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60774448"
---
# <a name="microsoft-education-governance-faq-for-admins"></a>관리자용 Microsoft 교육 거버넌스 FAQ

> [!Tip]
> 다음 세션에서 관리에 대한 자세한 Microsoft Teams: 거버넌스, 관리 및 [수명 주기에 Microsoft Teams](https://aka.ms/teams-governance)

## <a name="how-do-i-control-team-creation-im-worried-students-are-going-to-create-inappropriate-teams"></a>팀 만들기를 제어하는 방법 학생들이 부적절한 팀을 만들지 걱정됩니다.

부적절하거나 잘못된 이름을 방지하거나 팀 이름을 지정하는 방법에 대한 더 많은 구조를 제공하기 위해 Microsoft 365 그룹 명명 정책(현재 미리 보기)을 사용할 수 있습니다.

-   **접두사-접미사 이름 이름 정책** 접두사 또는 접미사를 사용하여 팀(그룹)의 이름 **규칙을 정의할 수 GRP_US_My Group_Engineering.** 접두사 및 접미사는 팀을 만드는 사용자를 기반으로 이름에 추가되는 문자열 또는 사용자 특성(예: **[부서])일** 수 있습니다.
-   **사용자 지정 차단된 단어** 특정 조직의 사용자가 만든 팀의 이름으로 사용이 차단된 단어 집합을 업로드할 수 있습니다. 예를 들어 **CEO,** **급여** 및 **HR** 용어가 적용되지 않는 그룹의 팀 이름에서 사용되는 것을 차단할 수 있습니다.
-   **분류** 조직에서 사용자가 그룹 그룹을 만들 때 설정할 수 있는 분류를 Microsoft 365 있습니다. 

> [!IMPORTANT]
> 그룹 Microsoft 365 이름을 Azure Active Directory Premium P1 하나 이상의 그룹 구성원인 각 고유 사용자에 대한 라이선스 또는 Azure AD Basic EDU 라이선스가 Microsoft 365 필요합니다.

자세한 지침은 그룹 [Office 정책 을 참조하세요.](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)

> [!Note]
> 다른 시스템의 입력을 사용하여 팀을 자동으로 만든 경우(예: 학교 데이터 동기화) 입력 데이터가 구성한 이름 정책을 준수하는지 확인해야 합니다. 그렇지 않은 경우 팀 만들기가 실패합니다.

## <a name="can-i-see-who-created-a-team"></a>팀을 만든 사람도 볼 수 있나요?

특정 팀을 만든 사용자에 대해 확인하려면 의 이벤트에 대한 감사 [로그 검색을 Microsoft Teams.](audit-log-events.md)

## <a name="can-i-control-who-can-create-teams"></a>팀을 만들 수 있는 사용자도 제어할 수 있나요?

일반적으로 모든 사용자가 팀을 만드는 것을 방지하는 것이 좋습니다. 모든 사용자가 팀을 만들 수 Teams 널리 채택될 가능성이 더 습니다. 교직원, 교사 또는 학생은 학습 그룹을 Teams 그룹을 만들 수 있습니다. 이렇게 하면 교실 Teams 수락할 수 있습니다.

사용자 교육을 통해 책임감 있는 사용 Teams 수 있습니다. 사용자가 팀을 만드는 것이 익명이 아니라는 것을 이해하면 부적절하게 팀을 만드는 의미를 이해하고 도구를 오용하지 않는 경향이 있습니다.

팀을 만들 수 있는 사용자에 대해 제어하려는 경우 그룹 그룹을 만들 수 있는 Microsoft 365 [참조합니다.](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618)

## <a name="how-do-i-automatically-create-a-team-for-each-course-at-the-beginning-of-the-semester-or-quarter"></a>학기 또는 분기 초에 각 과정에 대한 팀을 자동으로 만들 수 있나요?

각학기 또는 분기가 시작될 때 새 팀이 여러 개 필요합니다. 이러한 팀을 자동으로 만들고, 올바른 사용자로 채우고, 올바른 권한을 설정하는 자동화된 접근 방식을 취하는 것이 맞을 수 있습니다.

-   학교 데이터 동기화 온라인 및 Microsoft 365 그룹Exchange Online SharePoint 수업용 수업 팀, Microsoft Teams 및 OneNote Intune용 학교 그룹 및 SSO(등록 및 Single Sign-On) 통합을 만들 수 있습니다. 다른 많은 타사 애플리케이션에 대해 자세한 내용은 의 개요 [에서 학교 데이터 동기화.](/schooldatasync/overview-of-school-data-sync)
-   PowerShell을 사용하면 팀 및 채널을 만들고 설정을 자동으로 구성할 수 있습니다. 자세한 [Microsoft Teams PowerShell을](/powershell/module/teams/?view=teams-ps) 참조하세요.
-   Microsoft Graph API(현재 베타)를 사용하여 팀을 만들고, 구성하고, 복제하고, 보관할 수 있습니다. 자세한 [내용은 Microsoft Graph API를 사용하여](/graph/api/resources/teams-api-overview) Microsoft Teams 참조하세요.

> [!TIP]
> 학교 데이터 동기화 동기화된 각 Microsoft 365 그룹을 만들고 숨겨진 그룹 [](https://techcommunity.microsoft.com/t5/School-Data-Sync/HiddenGroupMembershipEnabled-SDS-setting/td-p/159945) 멤버 자격을 사용할 수 있으므로 수업 내의 교사와 학생만 해당 수업의 구성원을 볼 수 있습니다. 다른 프로세스를 사용하여 클래스 그룹을 만드는 경우 동일한 개인 정보 New-UnifiedGroup cmdlet의 HiddenGroupMembershipEnabled 매개 변수를 사용합니다.

## <a name="how-do-i-deal-with-teams-when-the-semester-or-quarter-ends"></a>한학기 또는 분기가 끝나면 팀을 어떻게 처리하나요?

학교 학기 또는 분기가 Teams 데이터를 처리하려는 방법에 대해 먼저 생각해 보는 것이 좋습니다. 수업을 완료한 후에도 해당 데이터를 삭제하거나 학생이 사용할 수 있도록 유지할지 여부입니다. 설정한 정책이 공휴일과 충돌하지 않습니다. 다음 도구를 사용하여 전략을 구현할 수 있습니다.

-   **보존 정책:** 이 옵션을 사용하여 지정한 연령보다 오래된 모든 데이터를 삭제하여 채팅(전체 또는 일부 사용자의 경우) 및 채널에서 이전 데이터가 제거되어 있는지 확인하세요. 콘텐츠를 삭제할 수 Teams 유지하도록 구성할 수도 있습니다. 자세한 내용은 에 대한 [보존 정책을 Microsoft Teams.](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Retention-policies-for-Microsoft-Teams/ba-p/178011)
-   **만료 정책:** 특정 일 수 후에 만료하도록 팀을 구성합니다. 만료 30일 전에 팀의 모든 소유자에게 팀을 갱신해야 하다가 삭제됩니다(관리자가 삭제된 팀을 추가로 30일 동안 복구할 수 있습니다). 이 설정은 사용되지 않는 팀이 일몰된지 확인하는 데 매우 유용합니다. 자세한 내용은 Microsoft 365 [만료 정책 에서 자세히 알아보고](https://support.office.com/article/office-365-group-expiration-policy-8d253fe5-0e09-4b3c-8b5e-f48def064733)

-   **보관 팀:** 이 설정은 팀을 읽기 전용 모드로 전환합니다. 검색 및 검색할 수 있지만 새 게시물을 추가할 수 있는 사람은 없습니다. [팀의](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7) 보관 또는 복원은 팀 소유자가 팀을 보관할 수 있는 방법을 설명합니다. 팀 소유자는 팀의 Graph [API(베타)를](/graph/api/resources/teams-api-overview) 사용하여 팀을 보관하거나 복원할 수도 있습니다.
 
> [!IMPORTANT]
> 그룹 Microsoft 365 만료 정책을 사용하려면 하나 이상의 Azure Active Directory Premium P1 그룹의 구성원인 각 고유 사용자에 대한 Microsoft 365 필요합니다.

## <a name="are-there-team-templates-for-my-faculty-members-to-use-when-creating-a-team"></a>팀을 만들 때 사용할 교직원용 팀 템플릿이 있나요?

예. 사용자는 **새** 팀을 만들 때 기존 템플릿에서 팀 만들기를 선택할 수 Teams 소유자는 Graph [API(베타)를](/graph/api/resources/teams-api-overview) 사용하여 사용 가능한 템플릿에서 새 팀을 만들 수도 있습니다.

## <a name="what-tasks-can-i-automate-via-powershell-or-graph"></a>PowerShell을 통해 자동화할 수 있는 작업은 Graph?

[Microsoft Graph API(베타)는](/graph/api/resources/teams-api-overview) 다음을 할 수 있습니다.

-   팀을 만들 수 있습니다.
-   구성원 및 소유자를 추가합니다.
-   채널을 추가합니다.
-   앱을 추가합니다.
-   기존 팀을 복제하여 해당 단계를 바로 가기하고 탭도 얻습니다.
-   방금 만든 팀에 대한 링크를 사용자에게 제공합니다.
-   더 이상 필요하지 않습니다. 멤버, 소유자, 채널 및 앱을 제거합니다.
-   더 이상 활성 상태일 때 팀을 보관합니다. 
-   팀을 삭제합니다.
-   채널 스레드 만들기

[PowerShell은](/powershell/module/teams/?view=teams-ps) 다음을 할 수 있습니다.

-   팀을 만들 수 있습니다.
-   구성원 및 소유자를 추가합니다.
-   채널을 추가합니다.
-   더 이상 필요하지 않습니다. 멤버, 소유자 및 채널을 제거합니다.
-   팀을 삭제합니다.

> [!TIP]
> Graph API 및 PowerShell cmdlet은 지속적으로 기능을 추가합니다. 기능 향상을 위해 Microsoft Graph [API(베타)](/graph/api/resources/teams-api-overview) 및 [PowerShell](/powershell/module/teams/?view=teams-ps) 문서를 자주 확인해야 합니다.  


## <a name="can-i-control-what-teams-features-my-faculty-and-students-have-access-to"></a>교직원 및 Teams 액세스할 수 있는 기능을 제어할 수 있나요?

예. 정책을 사용하여 사용자가 액세스할 수 있는 특정 메시징, 모임, 통화 및 라이브 이벤트 기능을 제어할 수 있습니다. 테넌트 전체 설정을 사용하여 모두에 동일한 설정을 적용하거나 필요한 경우 사용자 수준 정책을 적용할 수 있습니다. 

정책에 대한 Teams 자세한 내용은 조직의 Microsoft Teams [설정 관리를 참조하세요.](enable-features-office-365.md)
 
## <a name="can-i-control-what-external-parties-my-faculty-and-students-collaborate-with"></a>교직원 및 학생들이 공동 작업하는 외부 당사자를 제어할 수 있나요?

게스트 액세스를 사용하여 테넌트 외부의 사용자를 초대할 수 있습니다. 이는 연구 공동 작업 또는 게스트 강의에 유용할 수 있습니다.

-   도메인 허용 목록을 사용하여 도메인에 따라 게스트를 허용하거나 차단합니다.
-   특정 그룹 및 Microsoft 365 게스트 액세스를 켜고 끄고 게스트를 초대할 수 있는 팀을 제어합니다.
-   감사 로그를 사용하여 초대된 게스트에게 전송된 경고를 볼 수 있습니다.

자세한 내용은 그룹 의 [게스트 Microsoft 365 참조하세요.](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6#PickTab=Manage)

## <a name="what-information-can-i-review-about-existing-teams"></a>기존 팀에 대해 어떤 정보를 검토할 수 있나요?

감사 로그를 확인하여 다음을 확인할 수 있습니다.

-   Who 게스트로 초대된 팀입니다.
-   Who 팀을 만들 수 있습니다.

자세한 내용은 의 이벤트에 대한 감사 [로그 검색을 Microsoft Teams.](audit-log-events.md)

## <a name="teams-evolves-so-quickly-how-can-i-stay-up-to-date"></a>Teams 빠르게 진화합니다. 최신을 유지 어떻게 할 수 있나요?

다음 리소스를 통해 최신 업데이트를 Teams.

-   [새로운 Microsoft Teams](https://support.office.com/article/What-s-new-in-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)
-   [Microsoft Teams 블로그](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)