---
title: Teams 거버넌스 계획 - Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: reference
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 이 문서에서는 이 문서에서 거버넌스 기능을 구현하기 위해 계획하는 방법을 Teams.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 96052f270bb0b4a9c5a9da94131e55abf314fbf4
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58631282"
---
# <a name="plan-for-governance-in-teams"></a>Teams에서 거버넌스 계획

Teams 조직에서 요구할 수 있는 거버넌스 기능을 구현하는 다양한 도구 집합을 제공합니다. 이 문서에서는 IT전문가가 거버넌스에 대한 요구 사항과 이를 충족하는 방법을 결정하기 위해 올바른 질문을 하는 방법을 안내합니다. 

> [!Tip] 
> 다음 세션을 시청하여 Microsoft Teams 거버넌스, 관리 및 수명 주기에 대해 [자세히 Microsoft Teams](https://aka.ms/teams-governance)

## <a name="group-and-team-creation-naming-classification-and-guest-access"></a>그룹 및 팀 만들기, 이름, 분류 및 게스트 액세스

조직에서 팀 이름을 지정하고 분류하는 방법, 게스트를 팀 구성원으로 추가할 수 있는지, 누가 팀을 만들 수 있는지에 대한 엄격한 제어를 구현해야 할 수 있습니다. Azure AD(Azure Active Directory) 및 민감도 레이블을 사용하여 이러한 영역을 구성할 수 있습니다. 

<br>

|-        |-        |-        |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting decision points"/>  |의사 결정 지점|<ul><li>조직에 팀에 대한 특정 이름 지정 규칙이 필요합니까?</li><li>팀 크리에이터가 팀에 조직별 분류를 할당할 수 있는 능력이 필요합니까?</li><li>팀당 게스트를 팀에 추가할 수 있는 기능을 제한해야 하나요?</li><li>조직에서 팀을 만들 수 있는 사용자 제한이 필요한가요?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next steps"/>|다음 단계|<ul><li>팀 만들기, 이름, 분류 및 게스트 액세스에 대한 조직의 요구 사항을 문서화합니다.</li><li>이러한 요구 사항을 롤아웃의 일부로 구현할 Teams 계획합니다.</li><li>정책을 통신하고 게시하여 Teams 사용자에게 예상할 수 있는 동작을 알릴 수 있습니다.</li></ul>|

> [!NOTE]
> 미리 계획을 세우기 위해 이러한 정책 설정 및 필요한 [라이선스에 대해 자세히 알아보아야 합니다.](/azure/active-directory/users-groups-roles/groups-settings-cmdlets#template-settings)
> 
> [!NOTE]
> 그룹 및 팀 만들기를 제한하면 많은 Microsoft 365 Office 365 서비스를 위해 그룹을 만들어야 하기 때문에 사용자의 생산성이 저하될 수 있습니다. 자세한 내용은 그룹 을 만드는 이유를 Microsoft 365 [확장합니다.](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618#why)


#### <a name="additional-information"></a>추가 정보

요구 사항을 확인한 후 Azure AD 컨트롤을 사용하여 구현할 수 있습니다. 이러한 설정을 구현하는 방법에 대한 기술 지침은 다음을 참조하세요.

- [Azure Active Directory 설정 구성을 위한 Azure Active Directory cmdlet](/azure/active-directory/users-groups-roles/groups-settings-cmdlets)

- [Microsoft 365 그룹에 대한 이름 Azure Active Directory](/azure/active-directory/users-groups-roles/groups-naming-policy)

- [Microsoft 365 그룹 이름 정책](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)

- [민감도 레이블을 사용하여 Microsoft Teams 그룹 및 Microsoft 365 사이트의 콘텐츠를 SharePoint](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

- [그룹, 팀 및 사용자에 대한 수명 주기 옵션의 Yammer](/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer)

## <a name="group-and-team-expiration-retention-and-archiving"></a>그룹 및 팀 만료, 보존 및 보관

조직에는 만료, 보존 및 팀 데이터(채널 메시지 및 채널 파일)에 대한 정책 설정에 대한 추가 요구 사항이 있을 수 있습니다. 그룹 만료 정책을 구성하여 그룹 및 보존 정책의 수명 주기를 자동으로 관리하여 필요한 경우 정보를 보존하거나 삭제할 수 있으며, 팀을 보관(읽기 전용 모드로 설정)하여 더 이상 활성이 없는 팀의 시점 시점 보기를 보존할 수 있습니다. 보관된 팀은 만료 정책이 계속 적용되고 제외되거나 갱신되지 않는 한 삭제될 수 있습니다.

|-          |-           |
|-----------|------------|
| ![의사 결정 지점을 묘사하는 아이콘](media/audio_conferencing_image7.png) <br/>의사 결정 지점|<ul><li>조직에서 팀에 대한 만료 날짜를 지정해야 하나요?</li><li>조직에서 팀에 특정 데이터 보존 정책을 적용해야 하나요?</li><li>조직에서 읽기 전용 상태로 콘텐츠를 보존하기 위해 비활성 팀을 보관할 수 있는 기능을 요구해야 하나요?</li></ul>|
| ![다음 단계를 묘사하는 아이콘](media/audio_conferencing_image9.png)<br/>다음 단계|<ul><li>팀 만료, 데이터 보존 및 보관에 대한 조직의 요구 사항을 문서화합니다.</li><li>이러한 요구 사항을 롤아웃의 일부로 구현할 Teams 계획합니다.</li><li>정책을 통신하고 게시하여 Teams 사용자에게 예상할 수 있는 동작을 알릴 수 있습니다.</li></ul>|

> [!TIP]
> 다음 표를 사용하여 조직의 요구 사항을 캡처합니다.

|기능 |세부 정보 |Azure AD Premium 라이선스 필요 |판단 |
|---------|---------|---------|---------|
|만료 정책 |만료 정책을 설정하여 Microsoft 365 그룹의 수명 주기를 관리합니다. |P1 |TBD|
|보존 정책 |보안 Teams 규정 준수 센터에서 보존 정책을 설정하여 특정 & 데이터를 유지하거나 삭제합니다. **참고**: 이 기능을 사용하려면 E3 이상의 Microsoft 365 Office 365 Enterprise 라이선스가 필요합니다. |아니요 |TBD |
|보관 및 복원 |팀이 더 이상 활성화되지 않지만 참조를 위해 유지하거나 향후 다시 활성화하려는 경우 팀을 보관합니다. |아니요 |TBD |

> [!Note]
> 그룹 만료는 Azure AD Premium 기능입니다. 이 기능을 사용하려면 테넌트에 영향을 받는 Azure AD Premium 구성하는 관리자에 대한 구독과 라이선스가 있어야 합니다.

#### <a name="additional-information"></a>추가 정보

이러한 설정을 구현하는 방법에 대한 기술 지침은 다음을 참조하세요.

- [그룹 Microsoft 365 을 설정합니다.](/azure/active-directory/users-groups-roles/groups-lifecycle)

- [보존 정책 Teams 설정](retention-policies.md)

- [팀을 보관하거나 복원합니다.](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)

## <a name="group-and-team-membership-management"></a>그룹 및 팀 멤버 자격 관리

신속한 온보드 및 오프보드가 필요한 팀이나 사용자 및 게스트를 기반으로 하는 프로젝트 기반 또는 제한된 그룹의 구성원을 일관되게 관리해야 합니다. 또한 조직은 현재 모든 구성원이 팀에 있을 비즈니스 명분을 들이고 있는지 확인해야 할 수도 있습니다. 팀 소유자는 팀 소유자를 떠날 수 있으며 사용자가 일반적으로 프로젝트가 종료되거나 역할을 변경할 때 그룹을 자체적으로 떠날 수 있기 때문에 구성원 관리가 어려워질 수 있습니다. 사용자가 필요할 때 액세스 권한을 얻을 수 있지만 그룹에 부적절한 액세스 위험이 없는지 보장하는 그룹 멤버 자격을 관리하는 가장 좋은 방법은 두 가지 지구 프로세스를 통해 권한 관리 및 액세스 검토를 통해 진행됩니다.

[자격 관리를](/azure/active-directory/governance/entitlement-management-overview) 사용하면 프로젝트 관리자와 같은 다른 사람에게 위임하여 팀 멤버 자격을 포함하여 필요한 모든 리소스를 단일 패키지로 수집할 수 있습니다. 또한 요청을 할 수 있는 사용자(테넌트의 사용자 또는 다른 연결된 조직의 사용자)를 정의할 수도 있습니다. 프로젝트 관리자는 전자 메일에서 액세스 요청을 수신하고 MyAccess 포털에서 요청을 승인하거나 거부합니다. 관리자는 액세스가 갱신되지 않는 한 사용자 또는 게스트가 팀에서 제거될 때 만료 날짜 또는 기간을 포함하도록 액세스 조건을 구성할 수 있습니다. 관리자는 액세스 검토에 참여하기 위해 팀과 연결된 그룹을 설정할 수 있습니다. 액세스 [검토의 경우](/azure/active-directory/governance/access-reviews-overview)그룹 소유자는 팀 구성원을 검토하기 위한 정기적인 미리 알림을 받게됩니다. 액세스 검토에는 그룹 소유자가 일반 평가 프로세스를 보다 쉽게 진행할 수 있는 권장 사항이 포함되어 있습니다.

|-|-|-|
|:-|:-|:-|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting decision points"/>  | 의사 결정 지점 | 조직에서 하나 이상의 팀의 멤버 자격을 관리하기 위한 일관된 프로세스가 필요합니까? <br> 조직에서 정기적으로 하나 이상의 팀의 계속 멤버 자격을 정당화하기 위해 소유자 또는 구성원 자체가 필요합니까? <br> 조직에서 사용자와 게스트가 팀, 그룹, 사이트 및 앱을 포함한 리소스에 SharePoint 승인을 요구하나요? |
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next steps"/>| 다음 단계? | 멤버 자격 만료에 대한 각 팀 또는 특정 팀에 대한 조직 요구 사항을 문서화합니다.<br>조직에서 액세스 패키지에서 팀, 그룹, SharePoint 사이트 및 앱을 함께 번들할 수 있는 방법을 계획합니다.<br>요청자 관리자, 프로젝트 관리자, 연결된 조직의 스폰서 또는 조직의 보안 담당자와 같은 사용자에 대한 액세스 요청을 승인하거나 거부해야 하는 사용자 계획을 세우는 것입니다. |

> [!TIP]
> 다음 표를 사용하여 조직의 요구 사항을 캡처합니다.

| 기능 | 세부 정보 | Azure AD Premium 라이선스 필요 | 판단 |
|:-|:-|:-|:-|
| 액세스 검토 | 특정 팀의 멤버 자격을 정기적으로 다시 인증하기 위한 액세스 검토 설정 | P2 | TBD |
| 자격 관리 | 사용자와 게스트가 팀에 대한 액세스를 요청할 수 있도록 액세스 패키지 설정 | P2 | TBD |

> [!NOTE]
> 미리 계획을 세우기 위해 필요한 라이선스에 [대해 자세히 알아보면 됩니다.](https://azure.microsoft.com/pricing/details/active-directory/)

### <a name="additional-information"></a>추가 정보

이러한 설정을 구현하는 방법에 대한 기술 지침은 다음을 참조하세요.

- [자격 관리](/azure/active-directory/governance/entitlement-management-overview)
- [액세스 검토](/azure/active-directory/governance/access-reviews-overview)

## <a name="teams-feature-management"></a>Teams 기능 관리

거버넌스 및 수명 주기 관리의 또 다른 Teams 사용자가 액세스할 수 있는 기능을 제어하는 기능입니다. 조직 수준 또는 사용자당 메시지, 모임 및 Microsoft 365 Office 365 관리할 수 있습니다.


|-        |-        |
|---------|---------|
| ![의사 결정 지점을 묘사하는 아이콘](media/audio_conferencing_image7.png) <br/>의사 결정 지점|<ul><li>조직에서 전체 테넌트에 Teams 기능을 제한해야 하나요?</li><li>조직에서 특정 사용자에 Teams 기능을 제한해야 하나요?</li></ul>|
| ![다음 단계를 묘사하는 아이콘](media/audio_conferencing_image9.png)<br/>다음 단계|<ul><li>테넌트 및 사용자 수준에서 Teams 제한하기 위한 조직의 요구 사항을 문서화합니다.</li><li>롤아웃의 일부로 특정 요구 사항을 구현할 Teams 계획합니다.</li><li>정책을 통신하고 게시하여 Teams 사용자에게 예상할 수 있는 동작을 알릴 수 있습니다.</li></ul>|

### <a name="teams-feature-management-focus-areas"></a>Teams 관리 포커스 영역

Teams 정책을 통해 메시징, 모임, 통화 및 라이브 이벤트 기능을 제어하기 위한 세분화된 기능을 제공합니다. 조직에서 요구하는 경우 기본적으로 또는 사용자당 다른 정책을 적용할 수 있습니다. 

조직에 대해 구현하는 방법에 대한 기술 지침을 포함하여 모든 설정의 자세한 목록은 다음 문서를 참조하세요.

- [조직에서 Microsoft Teams 설정 관리](enable-features-office-365.md)
- [새 Microsoft Teams 관리 센터로 전환하는 동안 팀 관리](manage-teams-skypeforbusiness-admin-center.md)
- [Microsoft Teams의 비공개 채널](private-channels.md)
- [Teams에서의 모임 정책 관리](meeting-policies-in-teams.md)
- [Teams에서 메시지 정책 관리](messaging-policies-in-teams.md)
- [관리 센터에서 앱 Microsoft Teams 관리](manage-apps.md)

또한 채널에 대한 중재를 설정하고 특정 사용자에게 중재자 기능을 제공하여 채널 게시물을 만들고 응답할 수 있는 사용자를 제어할 수 있습니다. 자세한 내용은 Microsoft Teams 채널 중재 설정 [및](manage-channel-moderation-in-teams.md) 관리를 참조하세요.

## <a name="security-and-compliance"></a>보안 및 규정 준수

Teams 보안 및 규정 준수 기능의 고급 보안 및 Microsoft 365 Office 365, 규정 준수 콘텐츠 검색, 전자 검색, 법적 보존 및 보존 정책을 지원합니다.

> [!Important]
> 조직 [Microsoft Teams에](security-compliance-overview.md)규정 준수 및 보안 요구 사항이 있는 경우 이 항목에 대해 제공된 심층적인 콘텐츠를 검토합니다.

## <a name="related-topics"></a>관련 주제

[Teams에 대한 거버넌스 빠른 시작](teams-adoption-governance-quick-start.md)

[Microsoft 365 준수를 위한 & 라이선스 지침](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)

<!--
## Teams lifecycle management

In addition to planning for governance, your organization might also be interested in planning for Teams lifecycle management. For practical guidance on planning for teams lifecycle management, see [Plan for lifecycle management in Teams](plan-teams-lifecycle.md).
-->