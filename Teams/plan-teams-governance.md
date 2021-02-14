---
title: Teams의 거버넌스 계획 - Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: reference
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 이 문서에서는 Teams에서 거버넌스 기능을 구현하기 위한 계획을 세우는 방법을 배웠습니다.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2180c819491b3067225ada993aec60ec052bc69f
ms.sourcegitcommit: 43823358e7e1c1cece72a69a2ceb4eff86d3f927
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/10/2020
ms.locfileid: "48416909"
---
# <a name="plan-for-governance-in-teams"></a>Teams에서 거버넌스 계획

Teams는 조직에서 요구할 수 있는 거버넌스 기능을 구현하는 풍부한 도구 집합을 제공합니다. 이 문서에서는 IT 프로가 거버넌스에 대한 요구 사항과 이를 충족하는 방법을 결정하기 위해 올바른 질문을 하는 방법을 안내합니다. 

> [!Tip] 
> Microsoft Teams의 거버넌스, 관리 및 수명 주기에 대해 자세히 알아보는 다음 세션을 [시청합니다.](https://aka.ms/teams-governance)

## <a name="group-and-team-creation-naming-classification-and-guest-access"></a>그룹 및 팀 만들기, 이름, 분류 및 게스트 액세스

조직에서는 팀의 명명 및 분류 방법, 게스트를 팀 구성원으로 추가할 수 있는지 여부 및 팀을 만들 수 있는 사용자에 대한 엄격한 제어를 구현해야 할 수 있습니다. Azure AD(Azure Active Directory) 및 민감도 레이블을 사용하여 이러한 영역을 구성할 수 있습니다. 

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting decision points"/>  |의사 결정 지점|<ul><li>조직에 팀에 대한 특정 이름 지정 규칙이 필요한가요?</li><li>팀 작성자에게 조직별 분류를 팀에 할당할 수 있는 능력이 필요한가요?</li><li>팀에 게스트를 팀에 추가하는 기능을 제한해야 하나요?</li><li>조직에서 팀을 만들 수 있는 사용자 제한이 필요한가요?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next steps"/>|다음 단계|<ul><li>팀 만들기, 이름, 분류 및 게스트 액세스에 대한 조직의 요구 사항을 문서화합니다.</li><li>Teams 롤아웃의 일부로 이러한 요구 사항을 구현할 계획입니다.</li><li>정책을 전달하고 게시하여 Teams 사용자에게 예상할 수 있는 행동을 알릴 수 있습니다.</li></ul>|

> [!TIP]
> 다음 표를 사용하여 조직의 요구 사항을 캡처합니다.

|기능 |세부 정보 |Azure AD Premium <br> 라이선스 필요 |의사 결정 |
|---------|---------|---------|---------|
|팀 이름 정책 | 접두사-접미사 기반 사용자 지정 차단 단어를 사용 합니다. |P1 |TBD |
|팀 분류 |팀에 분류를 할당합니다. |P1 |TBD |
|팀 게스트 액세스 |게스트가 팀에 추가되는 것을 허용하거나 방지합니다. |아니요 |TBD |
|팀 만들기 |팀 만들기를 관리자로 제한합니다. |아니요 |TBD|
|팀 만들기 |팀 만들기를 보안 그룹 구성원으로 제한합니다. |P1 |TBD|
|민감도 레이블|개인 정보 및 게스트 공유 구성|아니요|TBD|

> [!NOTE]
> 미리 계획할 수 있도록 이러한 정책 설정 및 필요한 라이선스에 [대해 자세히 알아보고](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets#template-settings)
> 
> [!NOTE]
> 많은 Microsoft 365 및 Office 365 서비스가 작동하려면 그룹을 만들어야 하기 때문에 그룹 및 팀 만들기를 제한하면 사용자의 생산성이 저하될 수 있습니다. 자세한 내용은 [Microsoft 365](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618#why)그룹을 만드는 이유 제어로 이동하여 확장합니다.


#### <a name="additional-information"></a>추가 정보

요구 사항을 결정한 후 Azure AD 컨트롤을 사용하여 구현할 수 있습니다. 이러한 설정을 구현하는 방법에 대한 기술 지침은 다음을 참조하세요.

- [그룹 설정 구성을 위한 Azure Active Directory cmdlet](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)

- [Azure Active Directory에서 Microsoft 365 그룹에 대한 이름 정책 적용](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-naming-policy)

- [Microsoft 365 그룹 이름 정책](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)

- [민감도 레이블을 사용하여 Microsoft Teams, Microsoft 365 그룹 및 SharePoint 사이트의 콘텐츠 보호](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

- [그룹, 팀 및 그룹에 대한 수명 주기 Yammer](https://docs.microsoft.com/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer)

## <a name="group-and-team-expiration-retention-and-archiving"></a>그룹 및 팀 만료, 보존 및 보관

조직에는 만료, 보존 및 팀 및 팀 데이터(채널 메시지 및 채널 파일)에 대한 정책 설정에 대한 추가 요구 사항이 있을 수 있습니다. 필요한 경우 정보를 보존하거나 삭제하도록 그룹 만료 정책 및 보존 정책의 수명 주기를 자동으로 관리하도록 그룹 만료 정책을 구성할 수 있으며 팀을 보관(읽기 전용 모드로 설정)하여 더 이상 활성화되지 않은 팀의 특정 시점 보기를 보존할 수 있습니다. 보관된 팀은 만료 정책을 계속 적용하고 제외되거나 갱신되지 않는 한 삭제될 수 있습니다.

|           |            |
|-----------|------------|
| ![의사 결정 지점을 묘사하는 아이콘](media/audio_conferencing_image7.png) <br/>의사 결정 지점|<ul><li>조직에서 팀의 만료 날짜를 지정해야 하나요?</li><li>조직에서 특정 데이터 보존 정책을 팀에 적용해야 하나요?</li><li>조직에서 콘텐츠를 읽기 전용 상태로 보존하기 위해 비활성 팀을 보관할 수 있는 기능을 요구하나요?</li></ul>|
| ![다음 단계를 묘사하는 아이콘](media/audio_conferencing_image9.png)<br/>다음 단계|<ul><li>팀 만료, 데이터 보존 및 보관에 대한 조직의 요구 사항을 문서화합니다.</li><li>Teams 롤아웃의 일부로 이러한 요구 사항을 구현할 계획입니다.</li><li>정책을 전달하고 게시하여 Teams 사용자에게 예상할 수 있는 행동을 알릴 수 있습니다.</li></ul>|

> [!TIP]
> 다음 표를 사용하여 조직의 요구 사항을 캡처합니다.

|기능 |세부 정보 |Azure AD Premium 라이선스 필요 |의사 결정 |
|---------|---------|---------|---------|
|만료 정책 |만료 정책을 설정하여 Microsoft 365 그룹의 수명 주기를 관리합니다. |P1 |TBD|
|보존 정책 |Security & 준수 센터에서 Teams에 대한 보존 정책을 설정하여 특정 기간 동안 데이터를 유지하거나 삭제합니다. **참고:** 이 기능을 사용하려면 Microsoft 365 또는 Office 365 Enterprise E3 이상의 라이선스가 필요합니다. |아니요 |TBD |
|보관 및 복원 |팀이 더 이상 활성화되지 않지만 참조를 위해 유지하거나 향후 다시 활성화하려는 경우 팀을 보관합니다. |아니요 |TBD |

> [!Note]
> 그룹 만료는 Azure AD Premium 기능입니다. 이 기능을 사용하려면 테넌트에 Azure AD Premium에 대한 구독과 설정을 구성하는 관리자 및 영향을 받는 그룹의 멤버에 대한 라이선스가 있어야 합니다.

#### <a name="additional-information"></a>추가 정보

이러한 설정을 구현하는 방법에 대한 기술 지침은 다음을 참조하세요.

- [Microsoft 365 그룹 만료를 설정합니다.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle)

- [Teams 보존 정책을 설정합니다.](retention-policies.md)

- [팀을 보관하거나 복원합니다.](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)

## <a name="group-and-team-membership-management"></a>그룹 및 팀 멤버 자격 관리

신속한 온보드 및 오프보드 또는 사용자 및 게스트가 필요한 팀에는 프로젝트 기반 또는 제한된 그룹의 구성원을 일관되게 관리해야 합니다. 또한 조직은 모든 현재 구성원이 팀에 있을 비즈니스 타당성에 있는지도 확인해야 할 수 있습니다. 팀 소유자가 떠날 수 있으며 프로젝트가 종료되거나 역할이 변경될 때 일반적으로 사용자가 그룹을 나갈 수 있기 때문에 구성원 관리가 어려워질 수 있습니다. 필요한 경우 사용자가 액세스할 수 있지만 그룹에 부적절한 액세스 위험이 없는지 확인하도록 그룹 멤버 자격을 관리하는 가장 좋은 방법은 권한 관리 및 액세스 검토의 두 가지 지역 프로세스를 통한 것입니다.

[자격 관리를](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview) 사용하면 프로젝트 관리자와 같은 사람에게 위임하여 팀 멤버 자격을 포함하여 필요한 모든 리소스를 단일 패키지로 수집할 수 있습니다. 또한 테넌트의 사용자 또는 다른 연결된 조직에서 요청할 수 있는 사용자를 정의할 수도 있습니다. 프로젝트 관리자는 전자 메일로 액세스 요청을 받고 MyAccess 포털에서 요청을 승인하거나 거부합니다. 관리자는 액세스가 갱신되지 않는 한 사용자 또는 게스트가 팀에서 제거될 때 만료 날짜 또는 기간을 포함하도록 액세스 조건을 구성할 수 있습니다. 관리자는 액세스 검토에 참여하기 위해 팀과 연결된 그룹을 설정할 수 있습니다. 액세스 [검토의 경우](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)그룹 소유자는 팀 구성원을 검토하는 정기 미리 알림을 받게됩니다. 액세스 검토에는 그룹 소유자가 정기적인 확인 프로세스를 보다 쉽게 진행할 수 있는 권장 사항이 포함되어 있습니다.

||||
|:-|:-|:-|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting decision points"/>  | 의사 결정 지점 | 조직에 하나 이상의 팀의 멤버 자격을 관리하기 위한 일관된 프로세스가 필요한가요? <br> 조직에서 정기적으로 하나 이상의 팀의 계속 멤버 자격을 정당화하기 위해 소유자 또는 구성원 자체가 필요한가요? <br> 조직에서 사용자 및 게스트가 팀, 그룹, SharePoint 사이트 및 앱을 포함한 리소스에 대한 액세스를 요청하는 승인을 요구하나요? |
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next steps"/>| 다음 단계인가요? | 멤버 자격 만료에 대한 각 팀 또는 특정 팀에 대한 조직 요구 사항을 문서화합니다.<br>조직에서 액세스 패키지에 팀, 그룹, SharePoint 사이트 및 앱을 함께 묶는 방법을 계획합니다.<br>요청자 관리자, 프로젝트 관리자, 연결된 조직의 후원자 또는 조직의 보안 담당자와 같은 사람이 액세스 요청을 승인하거나 거부해야 하는 사람에 대해 계획합니다. |

> [!TIP]
> 다음 표를 사용하여 조직의 요구 사항을 캡처합니다.

| 기능 | 세부 정보 | Azure AD Premium 라이선스 필요 | 의사 결정 |
|:-|:-|:-|:-|
| 액세스 검토 | 정기적으로 특정 팀의 멤버 자격을 다시 인증하도록 액세스 검토 설정 | P2 | TBD |
| 자격 관리 | 사용자와 게스트가 팀에 대한 액세스를 요청할 수 있도록 액세스 패키지 설정 | P2 | TBD |

> [!NOTE]
> 미리 계획할 수 있도록 필요한 라이선스에 [대해 자세히 알아보면 됩니다.](https://azure.microsoft.com/pricing/details/active-directory/)

### <a name="additional-information"></a>추가 정보

이러한 설정을 구현하는 방법에 대한 기술 지침은 다음을 참조하세요.

- [자격 관리](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)
- [액세스 검토](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)

## <a name="teams-feature-management"></a>Teams 기능 관리

Teams의 거버넌스 및 수명 주기 관리의 또 다른 중요한 측면은 사용자가 액세스할 수 있는 기능을 제어하는 기능입니다. Microsoft 365 또는 Office 365 조직 수준 또는 사용자당 메시징, 모임 및 통화 기능을 관리할 수 있습니다.


|         |         |
|---------|---------|
| ![의사 결정 지점을 묘사하는 아이콘](media/audio_conferencing_image7.png) <br/>의사 결정 지점|<ul><li>조직에서 전체 테넌트에 대한 Teams 기능을 제한해야 하나요?</li><li>조직에서 특정 사용자에 대한 Teams 기능을 제한해야 하나요?</li></ul>|
| ![다음 단계를 묘사하는 아이콘](media/audio_conferencing_image9.png)<br/>다음 단계|<ul><li>테넌트 및 사용자 수준에서 Teams 기능을 제한하기 위한 조직의 요구 사항을 문서화합니다.</li><li>Teams 롤아웃의 일부로 특정 요구 사항을 구현하도록 계획합니다.</li><li>정책을 전달하고 게시하여 Teams 사용자에게 예상할 수 있는 행동을 알릴 수 있습니다.</li></ul>|

### <a name="teams-feature-management-focus-areas"></a>Teams 기능 관리 주요 영역

Teams는 정책을 통해 메시징, 모임, 통화 및 라이브 이벤트 기능을 제어하는 세부적인 기능을 제공합니다. 조직에서 요구하는 경우 기본적으로 모든 사용자에게 또는 사용자당 다른 정책을 적용할 수 있습니다. 

조직에 대해 구현하는 방법에 대한 기술 지침을 포함하여 모든 설정의 자세한 목록은 다음 문서를 참조하세요.

- [조직에서 Microsoft Teams 설정 관리](enable-features-office-365.md)
- [새 Microsoft Teams 관리 센터로 전환하는 동안 팀 관리](manage-teams-skypeforbusiness-admin-center.md)
- [Microsoft Teams의 비공개 채널](private-channels.md)
- [Teams에서 모임 정책 관리](meeting-policies-in-teams.md)
- [Teams에서 메시징 정책 관리](messaging-policies-in-teams.md)
- [Microsoft Teams 관리 센터에서 앱 관리](manage-apps.md)

또한 채널에 대한 중재를 설정하고 특정 사용자에게 중재자 기능을 제공하여 채널 게시물을 만들고 응답할 수 있는 사용자를 제어할 수 있습니다. 자세한 [내용은 Microsoft Teams에서](manage-channel-moderation-in-teams.md) 채널 중재 설정 및 관리를 참조하세요.

## <a name="security-and-compliance"></a>보안 및 규정 준수

Teams는 Microsoft 365 및 Office 365의 고급 보안 및 규정 준수 기능을 구축하고 감사 및 보고, 규정 준수 콘텐츠 검색, e-discovery, 법적 보존 및 보존 정책을 지원합니다.

> [!Important]
> 조직에 규정 준수 및 보안 요구 사항이 있는 경우 Microsoft Teams의 보안 및 규정 준수 개요 문서에서 이 항목에 대해 제공된 심층 콘텐츠를 [검토합니다.](security-compliance-overview.md)

## <a name="related-topics"></a>관련 주제

[Teams에 대한 거버넌스 빠른 시작](teams-adoption-governance-quick-start.md)

<!--
## Teams lifecycle management

In addition to planning for governance, your organization might also be interested in planning for Teams lifecycle management. For practical guidance on planning for teams lifecycle management, see [Plan for lifecycle management in Teams](plan-teams-lifecycle.md).
-->
