---
title: IT 관리자를 위한 Microsoft Education FAQ
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Teams를 사용하는 Microsoft Education 그룹의 관리자가 자주 묻는 질문에 대한 답변입니다.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6970cb95ff85ace99cc70cb81620e7a5de322496
ms.sourcegitcommit: c19ac3be42cc4b8409c8d512bbe3156736af0309
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/24/2022
ms.locfileid: "67426855"
---
# <a name="microsoft-education-faq-for-it-admins"></a>IT 관리자를 위한 Microsoft Education FAQ

> [!Tip]
> Microsoft Teams의 관리, [거버넌스, 관리 및 수명 주기](https://aka.ms/teams-governance)에 대해 자세히 알아보려면 다음 세션을 시청하세요.

## <a name="how-do-i-control-team-creation-im-worried-students-are-going-to-create-inappropriate-teams"></a>제어 팀 만들기를 어떻게 할까요?? 학생들이 부적절한 팀을 만들까 봐 걱정되나요?

부적절하거나 오해의 소지가 있는 이름을 방지하거나 팀 이름을 지정하는 방법에 대한 더 많은 구조를 제공하기 위해 Microsoft 365 그룹 명명 정책(현재 미리 보기 상태)을 사용할 수 있습니다.

- **접두사 접미사 명명 정책** 접두사 또는 접미사를 사용하여 팀(그룹)의 명명 규칙(예: **GRP_US_My Group_Engineering**)을 정의할 수 있습니다. 접두사와 접미사는 팀을 만드는 사용자를 기반으로 이름에 추가되는 고정 문자열 또는 사용자 특성(예: **[Department]**)일 수 있습니다.
- **사용자 지정 차단 단어** 특정 조직의 사용자가 만든 팀의 이름에서 사용할 수 없도록 차단된 단어 집합을 업로드할 수 있습니다. 예를 들어 **CEO**, **급여** 및 **HR** 이 적용되지 않는 그룹의 팀 이름에 사용되지 않도록 차단할 수 있습니다.
- **분류** 조직의 사용자가 Microsoft 365 그룹을 만들 때 설정할 수 있는 분류를 만들 수 있습니다.

> [!IMPORTANT]
> Microsoft 365 그룹 명명 정책을 사용하려면 하나 이상의 Microsoft 365 그룹의 구성원인 각 고유 사용자에 대해 Azure Active Directory Premium P1 라이선스 또는 Azure AD 기본 EDU 라이선스가 필요합니다.

자세한 지침은 [Office 그룹 명명 정책을](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552) 참조하세요.

> [!NOTE]
> 다른 시스템(예: 학교 데이터 동기화)의 입력을 사용하여 팀이 자동으로 만들어지는 경우 입력 데이터가 구성한 명명 정책을 준수하는지 확인합니다. 그렇지 않으면 팀 만들기가 실패합니다.

## <a name="can-i-see-who-created-a-team"></a>팀을 만든 사람을 볼 수 있나요?

특정 팀을 만든 사람을 확인하려면 [Microsoft Teams의 이벤트에 대한 감사 로그 검색을 참조하세요](audit-log-events.md).

## <a name="can-i-control-who-can-create-teams"></a>팀을 만들 수 있는 사용자를 제어할 수 있나요?

일반적으로 모든 사용자가 팀을 만들지 못하도록 방지하는 것이 좋습니다. 모든 사람이 팀을 만들 수 있다면 Teams가 널리 채택될 가능성이 높습니다. 교직원, 교사 또는 학생은 Teams를 사용하여 연구 그룹 또는 특수 관심 그룹을 만들 수 있습니다. 이 기능은 Teams가 교실 안팎에서 수락되는 데 도움이 됩니다.

이 환경에서 사용자 교육은 책임 있는 Teams 사용을 보장하는 데 도움이 됩니다. 사용자가 팀을 만드는 것이 익명이 아니라는 것을 이해하자마자 부주의하게 팀을 만드는 것의 의미를 이해하고 도구를 잘못 사용하는 것을 부끄러워하는 경향이 있습니다.

팀을 만들 수 있는 사용자를 제어하려는 경우 [Microsoft 365 그룹 만들 수 있는 사용자 관리를](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618) 참조하세요.

## <a name="how-do-i-automatically-create-a-team-for-each-course-at-the-beginning-of-the-semester-or-quarter"></a>어떻게 할까요? 학기 또는 분기가 시작될 때 각 과정에 대한 팀을 자동으로 만들 수 있나요?

각 학기 또는 분기가 시작될 때 새 팀이 필요합니다. 이러한 팀을 자동으로 만들고, 적절한 사용자로 채우고, 올바른 권한을 설정하는 자동화된 접근 방식을 사용하는 것이 합리적일 수 있습니다.

- 학교 데이터 동기화는 Exchange Online 및 SharePoint Online용 Microsoft 365 그룹, Microsoft Teams 및 OneNote 수업용 수업용 수업용 팀, 교육용 Intune 위한 학교 그룹, 다른 많은 타사 애플리케이션에 대한 명단 및 SSO(Single Sign-On) 통합을 만들 수 있습니다. [학교 데이터 동기화 개요](/schooldatasync/overview-of-school-data-sync)에서 자세히 알아보세요.
- PowerShell을 사용하면 팀과 채널을 만들고 설정을 자동으로 구성할 수 있습니다. 자세한 내용은 [Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps)을 참조하세요.
- Microsoft Graph API(현재 미리 보기 상태)를 사용하여 팀을 만들고, 구성하고, 복제하고, 보관할 수 있습니다. 자세한 내용은 [Microsoft Graph API 사용하여 Microsoft Teams 작업을 참조하세요](/graph/api/resources/teams-api-overview).

> [!TIP]
> School Data Sync는 동기화된 각 수업에 대해 Microsoft 365 그룹을 만들고 [숨겨진 그룹 멤버 자격을 사용하도록 설정](https://techcommunity.microsoft.com/t5/School-Data-Sync/HiddenGroupMembershipEnabled-SDS-setting/td-p/159945) 하므로 수업 내의 교사와 학생만 해당 수업의 구성원을 볼 수 있습니다. 다른 프로세스를 사용하여 클래스 그룹을 만드는 경우 New-UnifiedGroup cmdlet의 HiddenGroupMembershipEnabled 매개 변수를 사용하여 동일한 개인 정보 요구 사항을 충족합니다.

## <a name="how-do-i-deal-with-teams-when-the-semester-or-quarter-ends"></a>학기 또는 쿼터가 끝나면 팀과 거래할 어떻게 할까요? 있나요?

학교 학기 또는 분기가 끝났을 때 Teams 데이터를 처리하는 방법을 먼저 생각하는 것이 좋습니다. 이 데이터를 삭제할지 아니면 학생이 과정을 완료한 후에도 사용할 수 있도록 유지할지 여부를 고려해야 합니다. 설정한 정책이 휴일과 충돌하지 않도록 학교 일정을 염두에 두어야 합니다. 다음 도구를 사용하여 전략을 구현할 수 있습니다.

- **보존 정책:** 이 정책을 사용하여 지정한 연령보다 오래된 모든 데이터를 삭제하여 채팅(모든 사용자 또는 일부 사용자) 및 채널에서 이전 데이터가 제거되도록 합니다. 콘텐츠를 삭제할 수 없도록 Teams를 구성할 수도 있습니다. 자세한 내용은 [Microsoft Teams에 대한 보존 정책을 참조하세요](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Retention-policies-for-Microsoft-Teams/ba-p/178011).
- **만료 정책:** 설정된 날짜에 만료되도록 팀을 구성합니다. 만료 30일 전에 팀의 모든 소유자는 팀을 갱신해야 한다는 알림을 받으며, 그렇지 않으면 삭제됩니다. 관리자는 30일 동안 삭제된 팀을 복구할 수 있습니다. 이 설정은 사용되지 않는 팀이 사용 중지되도록 하는 데 유용합니다. [Microsoft 365 그룹 만료 정책에](https://support.office.com/article/office-365-group-expiration-policy-8d253fe5-0e09-4b3c-8b5e-f48def064733) 대해 자세히 알아보세요.

- **보관 팀:** 이 설정은 팀을 읽기 전용 모드로 전환합니다. 검색하고 검색할 수 있지만 아무도 새 게시물을 추가할 수 없습니다. [팀 보관 또는 복원은 팀 소유자가 팀을](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7) 보관하는 방법을 설명합니다. 팀 소유자는 [Graph API(미리 보기)](/graph/api/resources/teams-api-overview)를 사용하여 팀을 보관하거나 복원할 수도 있습니다.

> [!IMPORTANT]
> Microsoft 365 그룹 만료 정책을 사용하려면 하나 이상의 Microsoft 365 그룹의 구성원인 각 고유 사용자에 대해 Azure Active Directory Premium P1 라이선스가 필요합니다.

## <a name="are-there-team-templates-for-my-faculty-members-to-use-when-creating-a-team"></a>교직원 구성원이 팀을 만들 때 사용할 팀 템플릿이 있나요?

예. 사용자는 새 **팀을 만들 때 기존 템플릿에서 팀 만들기** 를 선택할 수 있으며 Teams 소유자는 [Graph API(미리 보기)](/graph/api/resources/teams-api-overview)를 사용하여 사용 가능한 템플릿에서 새 팀을 만들 수도 있습니다.

## <a name="what-tasks-can-i-automate-via-powershell-or-graph"></a>PowerShell 또는 Graph를 통해 자동화할 수 있는 작업은 무엇인가요?

[Microsoft Graph API(미리 보기)](/graph/api/resources/teams-api-overview)는 다음 작업을 수행할 수 있습니다.

- 팀을 만듭니다.
- 멤버 및 소유자를 추가합니다.
- 채널을 추가합니다.
- 앱을 추가합니다.
- 기존 팀을 복제하여 해당 단계를 바로 가기하고 해당 탭도 가져옵니다.
- 사용자가 만든 팀에 대한 링크를 사용자에게 제공합니다.
- 더 이상 필요하지 않은 경우 구성원, 소유자, 채널 및 앱을 제거합니다.
- 더 이상 활성 상태가 되지 않을 때 팀을 보관합니다.
- 팀을 삭제합니다.
- 채널 스레드 만들기

[PowerShell은](/powershell/module/teams/?view=teams-ps) 다음 작업을 수행할 수 있습니다.

- 팀을 만듭니다.
- 멤버 및 소유자를 추가합니다.
- 채널을 추가합니다.
- 더 이상 필요하지 않은 경우 구성원, 소유자 및 채널을 제거합니다.
- 팀을 삭제합니다.

> [!TIP]
> Graph API 및 PowerShell cmdlet은 지속적으로 기능을 추가합니다. 기능 향상에 대한 [Microsoft Graph API(미리 보기)](/graph/api/resources/teams-api-overview) 및 [PowerShell](/powershell/module/teams/?view=teams-ps) 문서를 자주 확인해야 합니다.  

## <a name="can-i-control-what-teams-features-my-faculty-and-students-have-access-to"></a>교직원과 학생이 액세스할 수 있는 Teams 기능을 제어할 수 있나요?

예. 정책을 사용하여 사용자가 액세스할 수 있는 특정 메시징, 모임, 통화 및 라이브 이벤트 기능을 제어할 수 있습니다. 테넌트 전체 설정을 사용하여 모두에 동일한 설정을 적용하거나 필요한 경우 사용자 수준 정책을 적용할 수 있습니다.

Teams 정책에 대한 자세한 내용은 [조직의 Microsoft Teams 설정 관리를 참조하세요](enable-features-office-365.md).

## <a name="can-i-control-what-external-parties-my-faculty-and-students-collaborate-with"></a>교직원과 학생이 공동 작업하는 외부 파티를 제어할 수 있나요?

게스트 액세스를 사용하여 테넌트 외부에서 사용자를 초대할 수 있습니다. 이는 연구 공동 작업 또는 게스트 강의에 유용할 수 있습니다.

- 도메인 허용 목록을 사용하여 해당 도메인에 따라 게스트를 허용하거나 차단합니다.
- 특정 Microsoft 365 그룹 및 팀에 대한 게스트 액세스를 켜고 끄면 게스트를 초대할 수 있는 팀과 초대할 수 없는 팀을 제어할 수 있습니다.
- 감사 로그를 사용하여 초대된 게스트에게 어떤 경고가 전송되었는지 확인합니다.

자세한 내용은 [Microsoft 365 그룹 게스트 액세스를](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6#PickTab=Manage) 참조하세요.

## <a name="what-information-can-i-review-about-existing-teams"></a>기존 팀에 대해 어떤 정보를 검토할 수 있나요?

감사 로그를 확인하여 다음을 확인할 수 있습니다.

- 어떤 팀의 게스트로 초대된 사람입니다.
- 누가 어떤 팀을 만들었는가?

자세한 내용은 [Microsoft Teams의 이벤트에 대한 감사 로그 검색을 참조하세요](audit-log-events.md).

## <a name="teams-evolves-so-quickly-how-can-i-stay-up-to-date"></a>Teams는 매우 빠르게 진화합니다. 최신 상태를 유지하려면 어떻게 해야 하나요?

Teams에서 최신 업데이트를 받으려면 다음 리소스를 사용하는 것이 좋습니다.

- [Microsoft Teams의 새로운 기능](https://support.office.com/article/What-s-new-in-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)
- [Microsoft Teams 블로그](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)
