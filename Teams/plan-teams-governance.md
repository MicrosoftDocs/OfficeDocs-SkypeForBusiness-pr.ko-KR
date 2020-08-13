---
title: 팀에서 관리 계획-Microsoft 팀
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 08/10/2018
ms.topic: reference
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 이 문서에서는 팀에서 관리 기능을 구현 하기 위해 계획 하는 방법에 대해 설명 합니다.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: ea48b4df3313784cf129cf483aebac341917cb21
ms.sourcegitcommit: 875c854547b5d3ad838ad10c1eada3f0cddc8e66
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/13/2020
ms.locfileid: "46656359"
---
# <a name="plan-for-governance-in-teams"></a>Teams에서 거버넌스 계획

팀은 조직에서 요구할 수 있는 모든 관리 기능을 구현 하는 다양 한 도구 집합을 제공 합니다. 이 문서에서는 IT 전문가에 게 관리 요구 사항 및이를 충족 하는 방법에 대 한 질문을 안내 합니다. 

> [!Tip] 
> Microsoft 팀의 경영진에 대 한 자세한 정보를 알아보려면 [Microsoft 팀의 지배 구조, 관리, 수명](https://aka.ms/teams-governance) 등 세션을 시청 하세요.

## <a name="group-and-team-creation-naming-classification-and-guest-access"></a>그룹 및 팀 만들기, 이름 지정, 분류, 게스트 액세스

조직에서 팀의 이름을 지정 하 고 분류 하는 방법, 게스트를 팀 구성원으로 추가할 수 있는지 여부, 그리고 팀을 만들 수 있는 사람에 게 엄격한 컨트롤을 구현 해야 할 수 있습니다. Azure AD (Active Directory)를 사용 하 여 이러한 영역을 각각 구성할 수 있습니다. 

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting decision points"/>  |의사 결정 지점|<ul><li>조직에 팀의 특정 명명 규칙이 필요 한가요?</li><li>팀 작성자에 게 조직 고유의 분류를 팀에 할당할 수 있는 기능이 필요 한가요?</li><li>팀에 게 게스트를 추가 하는 기능에 대 한 권한을 제한 해야 하나요?</li><li>조직에서 팀을 만들 수 있는 사람을 제한 해야 하나요?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next steps"/>|다음 단계|<ul><li>조직의 팀 만들기, 이름 지정, 분류 및 게스트 액세스에 대 한 요구 사항을 문서화 합니다.</li><li>이러한 요구 사항을 팀의 일부로 구현 하는 계획을 세워야 합니다.</li><li>팀 사용자에 게 예상할 수 있는 동작을 알리기 위해 정책을 전달 하 고 게시 합니다.</li></ul>|

> [!TIP]
> 조직의 요구 사항을 캡처하려면 다음 표를 사용 합니다.

|기능 |세부 정보 |Azure AD Premium <br> 라이선스 필요 |덕분 |
|---------|---------|---------|---------|
|팀 이름 지정 정책 | 접두사-접미사 기반, 사용자 지정 차단 된 단어를 사용 합니다. |P1 |TBD |
|팀 분류 |팀에 분류를 할당 합니다. |P1 |TBD |
|팀 게스트 액세스 |팀에 게스트를 추가 하는 것을 허용 하거나 금지 합니다. |아니요 |TBD |
|팀 만들기 |팀 만들기를 관리자로 제한 합니다. |아니요 |TBD|
|팀 만들기 |팀 만들기를 보안 그룹 구성원으로 제한 합니다. |P1 |TBD|

> [!NOTE]
> 미리 계획 하는 데 도움이 되도록 [이러한 정책 설정 및 필요한 라이선스에 대해 자세히 알아보세요](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets#template-settings).
> 
> [!NOTE]
> 그룹 및 팀 만들기를 제한 하면 많은 Microsoft 365 및 Office 365 서비스에서 서비스 기능을 위해 그룹을 만들어야 하기 때문에 사용자 생산성을 높일 수 있습니다. 추가 정보를 보려면 [Microsoft 365 그룹을 만드는 사용자를 제어 하는 이유](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618#why)를 찾아 확장 합니다.


#### <a name="additional-information"></a>추가 정보

요구 사항을 결정 한 후에는 Azure AD 컨트롤을 사용 하 여이를 구현할 수 있습니다. 이러한 설정을 구현 하는 방법에 대 한 기술 지침은 다음을 참조 하세요.

- [그룹 설정 구성을 위한 Azure Active Directory cmdlet](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)

- [Azure Active Directory에서 Microsoft 365 그룹에 대 한 이름 지정 정책을 적용](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-naming-policy)합니다.

- [Microsoft 365 그룹 이름 지정 정책](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)


## <a name="group-and-team-expiration-retention-and-archiving"></a>그룹 및 팀 만료, 보존 및 보관

조직에 만료, 보존 및 보관 팀과 팀 데이터 (채널 메시지 및 채널 파일)에 대 한 정책을 설정 하는 데 필요한 추가 요구 사항이 있을 수 있습니다. 필요에 따라 정보를 보존 하거나 삭제 하기 위해 그룹 및 보존 정책의 수명 주기를 자동으로 관리 하 고 팀을 읽기 전용 모드로 설정 하 여 더 이상 활성 상태가 아닌 팀의 특정 시점 보기를 유지 하도록 그룹 만료 정책을 구성할 수 있습니다.

|           |            |
|-----------|------------|
| ![의사 결정 지점을 묘사하는 아이콘](media/audio_conferencing_image7.png) <br/>의사 결정 지점|<ul><li>조직에서 팀에 대해 만료 날짜를 지정 해야 하나요?</li><li>조직의 특정 데이터 보존 정책을 팀에 적용 해야 하나요?</li><li>조직에서 비활성 팀을 보관 하 여 콘텐츠를 읽기 전용 상태로 유지 하는 기능이 필요 한가요?</li></ul>|
| ![다음 단계를 묘사하는 아이콘](media/audio_conferencing_image9.png)<br/>다음 단계|<ul><li>조직의 팀 만료, 데이터 보존 및 보관에 대 한 요구 사항을 문서화 합니다.</li><li>이러한 요구 사항을 팀의 일부로 구현할 계획을 수립 합니다.</li><li>팀 사용자에 게 예상할 수 있는 동작을 알리기 위해 정책을 전달 하 고 게시 합니다.</li></ul>|

> [!TIP]
> 조직의 요구 사항을 캡처하려면 다음 표를 사용 합니다.

|기능 |세부 정보 |Azure AD Premium 라이선스 필요 |덕분 |
|---------|---------|---------|---------|
|만료 정책 |만료 정책을 설정 하 여 Microsoft 365 그룹의 수명 주기를 관리 합니다. |P1 |TBD|
|보존 정책 |보안 & 준수 센터에서 팀에 대 한 보존 정책을 설정 하 여 특정 기간에 대 한 데이터를 보존 하거나 삭제 합니다. **참고**:이 기능을 사용 하려면 Microsoft 365 또는 Office 365 Enterprise e m m 이상에 대 한 라이선스가 필요 합니다. |아니요 |TBD |
|보관 및 복원 |더 이상 활성 상태가 아닌 팀을 보관 하 되 참조를 위해 유지 하거나 나중에 다시 활성화 하려는 경우 |아니요 |TBD |

> [!Note]
> 그룹 만료는 Azure AD Premium 기능입니다. 이 기능을 사용 하려면 테 넌 트에 설정 및 영향을 받는 그룹의 구성원을 구성 하는 관리자에 대 한 Azure AD Premium 및 라이선스 구독이 있어야 합니다.

#### <a name="additional-information"></a>추가 정보

이러한 설정을 구현 하는 방법에 대 한 기술 지침은 다음을 참조 하세요.

- [Microsoft 365 그룹 만료를 설정](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle)합니다.

- [팀 보존 정책을 설정](retention-policies.md)합니다.

- [팀을 보관 하거나 복원](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)합니다.

## <a name="group-and-team-membership-management"></a>그룹 및 팀 구성원 관리

프로젝트 기반 구성원을 일관 되 게 관리 하거나, 빠른 온 보 딩 및 오프 보 딩 또는 사용자 및 게스트가 필요한 팀에 제한 된 그룹이 필요 합니다. 조직에서 현재 모든 회원 들이 팀에 있는 비즈니스 근거를 보유 하 고 있는지도 확인 해야 할 수도 있습니다. 팀 소유자는 프로젝트를 종료 하거나 역할을 변경할 때 사용자의 고유한 accord에 그룹을 남기지 않기 때문에 구성원을 관리 하는 것은 어려울 수 있습니다. 사용자가 필요에 따라 액세스할 수 있도록 하는 그룹 구성원을 관리 하는 가장 좋은 방법은 그룹에 게 자격 부여 관리 및 액세스 검토와 같은 두 개의 학구 프로세스가 있는 것이 아닌지 확인 하는 것입니다.

[자격 관리](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview) 를 사용 하면 프로젝트 관리자와 같은 사용자에 게 위임 하 여 팀 구성원을 포함 하 여 필요한 모든 리소스를 단일 패키지로 모을 수 있습니다. 또한 테 넌 트 또는 다른 연결 된 조직의 사용자가 요청할 수 있는 사람을 정의할 수도 있습니다. 프로젝트 관리자는 전자 메일에 액세스 요청을 받고 MyAccess 포털에서 요청을 승인 하거나 거부 합니다. 관리자는 access가 갱신 되지 않는 한 팀에서 사용자 또는 게스트를 제거할 때 만료 날짜 또는 기간을 포함 하도록 액세스 조건을 구성할 수 있습니다. 관리자는 또한 팀과 연결 된 그룹을 설정 하 여 access 리뷰에 참여할 수 있습니다. [Access 리뷰](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)의 경우 그룹 소유자는 팀 구성원을 검토 하기 위한 정기적인 미리 알림을 받게 됩니다. Access 리뷰에는 그룹 소유자가 일반 증명 프로세스를 쉽게 이동할 수 있도록 하는 권장 사항이 포함 되어 있습니다.

||||
|:-|:-|:-|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting decision points"/>  | 의사 결정 지점 | 조직에서 하나 이상의 팀 구성원을 관리 하기 위해 일관 된 프로세스가 필요 한가요? <br> 조직에서 한 명 이상의 팀 구성원을 정기적으로 정당화 하기 위해 소유자 또는 구성원 자체를 필요로 하나요? <br> 조직에서 팀, 그룹, SharePoint 사이트, 앱을 비롯 한 리소스에 대 한 액세스 권한을 요청 하는 사용자 및 게스트가 승인 해야 합니까? |
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next steps"/>| 다음 단계 | 회원 가입 만료를 위해 각 팀 또는 특정 팀에 대 한 조직 요구 사항을 문서화 합니다.<br>조직이 access 패키지에서 팀, 그룹, SharePoint 사이트 및 앱을 함께 묶을 수 있는 방법을 계획 합니다.<br>요청자의 관리자, 프로젝트 관리자, 연결 된 조직에 대 한 스폰서 또는 조직의 보안 담당자가 액세스 요청을 승인 하거나 거부 해야 하는 사람을 계획 합니다. |

> [!TIP]
> 조직의 요구 사항을 캡처하려면 다음 표를 사용 합니다.

| 기능 | 세부 정보 | Azure AD Premium 라이선스 필요 | 덕분 |
|:-|:-|:-|:-|
| Access 리뷰 | 일정 한 시간 간격으로 특정 팀의 구성원 자격을 recertify 하는 access 리뷰 설정 | 즉 | TBD |
| 자격 관리 | 사용자와 게스트가 팀에 대 한 액세스를 요청할 수 있도록 액세스 패키지 설치 | 즉 | TBD |

> [!NOTE]
> 미리 계획 하는 데 도움이 되도록 [필요한 라이선스에 대해 자세히 알아보세요](https://azure.microsoft.com/pricing/details/active-directory/).

### <a name="additional-information"></a>추가 정보

이러한 설정을 구현 하는 방법에 대 한 기술 지침은 다음을 참조 하세요.

- [자격 관리](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)
- [Access 리뷰](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)

## <a name="teams-feature-management"></a>팀 기능 관리

팀에 대 한 관리 및 수명 주기 관리의 또 다른 중요 한 측면은 사용자가 액세스할 수 있는 기능을 제어 하는 기능입니다. Microsoft 365 또는 Office 365 조직 수준 또는 사용자 단위로 메시지, 모임, 통화 기능을 관리할 수 있습니다.


|         |         |
|---------|---------|
| ![의사 결정 지점을 묘사하는 아이콘](media/audio_conferencing_image7.png) <br/>의사 결정 지점|<ul><li>조직에서 전체 테 넌 트에 대 한 팀의 기능을 제한 해야 하나요?</li><li>조직에서 특정 사용자를 위해 팀의 기능을 제한 해야 하나요?</li></ul>|
| ![다음 단계를 묘사하는 아이콘](media/audio_conferencing_image9.png)<br/>다음 단계|<ul><li>테 넌 트 및 사용자 수준에서 팀 기능을 제한 하기 위한 조직의 요구 사항을 문서화 합니다.</li><li>팀의 일환으로 특정 요구 사항을 구현할 계획을 수립 합니다.</li><li>팀 사용자에 게 예상할 수 있는 동작을 알리기 위해 정책을 전달 하 고 게시 합니다.</li></ul>|

### <a name="teams-feature-management-focus-areas"></a>팀 기능 관리 포커스 영역

팀은 정책에 의해 메시징, 모임, 통화, 라이브 이벤트 기능 등을 제어 하는 세부적인 기능을 제공 합니다. 기본적으로 또는 조직에 필요한 경우 사용자 기준으로 모든 사용자에 게 다른 정책을 적용할 수 있습니다. 

조직에 맞게 구현 하는 방법에 대 한 기술 지침을 포함 하 여 모든 설정에 대 한 자세한 목록은 다음 문서를 참조 하세요.

- [조직에서 Microsoft Teams 설정 관리](enable-features-office-365.md)
- [새 Microsoft Teams 관리 센터로 전환하는 동안 팀 관리](manage-teams-skypeforbusiness-admin-center.md)
- [팀에서 모임 정책 관리](meeting-policies-in-teams.md)
- [팀에서 메시징 정책 관리](messaging-policies-in-teams.md)

또한 채널에 대 한 중재를 설정 하 고 특정 사용자에 게 블로그 게시물을 만들고 응답할 수 있는 사람을 제어할 수 있도록 중재자 기능을 제공할 수 있습니다. 자세한 내용은 [Microsoft 팀에서 채널 중재 설정 및 관리](manage-channel-moderation-in-teams.md) 를 참조 하세요.

## <a name="security-and-compliance"></a>보안 및 규정 준수

팀은 Microsoft 365 및 Office 365의 고급 보안 및 규정 준수 기능을 기반으로 하며 감사 및 보고, 준수 콘텐츠 검색, e-검색, 법적 보류, 보존 정책을 지원 합니다.

> [!Important]
> 조직에 준수 및 보안 요구 사항이 있는 경우 [Microsoft 팀의 보안 및 준수에](security-compliance-overview.md)대 한 개요 문서에서 해당 항목에 대해 제공 되는 심층적인 콘텐츠를 검토 하세요.

## <a name="related-topics"></a>관련 주제

[Teams에 대한 거버넌스 빠른 시작](teams-adoption-governance-quick-start.md)

<!--
## Teams lifecycle management

In addition to planning for governance, your organization might also be interested in planning for Teams lifecycle management. For practical guidance on planning for teams lifecycle management, see [Plan for lifecycle management in Teams](plan-teams-lifecycle.md).
-->
