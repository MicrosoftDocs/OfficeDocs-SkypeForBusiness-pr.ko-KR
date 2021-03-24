---
title: 온보드 검사 목록 - 핵심 기능 구성 - Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 조직에 대해 Teams를 구성할 때 이 검사 목록에서 핵심 할 일 작업 및 활동을 수행합니다.
ms.custom: seo-marvel-apr2020
localization_priority: Normal
f1.keywords:
- NOCSH
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7c28f33cb8d3c3823f74deb8f6540a39482f68b9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098034"
---
# <a name="configure-microsoft-teams-core-capabilities"></a>Microsoft Teams 핵심 기능 구성

| 아니요 | 활동 또는 작업 | 설명 | 완료 됐나요? | 추가 정보 |
|----|-----------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | 환경에 모든 Teams 구성 구성이 포함되어 있는지 확인 | 팀은 종단-종단 공동 작업 솔루션을 구성하기 위해 다른 플랫폼에 따라 달라 진다. IT 팀과 함께 Exchange, SharePoint Online 및 비즈니스용 OneDrive를 배포하고 적절하게 구성되었는지 확인합니다. | | [SharePoint Online 및 비즈니스용 OneDrive가 Microsoft Teams와 상호 작용하는 방법](sharepoint-onedrive-interact.md) <br/><br/>[Exchange와 Microsoft Teams의 상호 작용 방법](exchange-teams-interact.md) |
| 2  | 테넌트에 Teams가 사용하도록 설정되어 있는지 확인 | 모든 조직에 대해 기본적으로 팀이 켜져 있습니다. Microsoft **365** & 관리 센터의 서비스 추가 기능 페이지를 확인하여 Teams가 조직에 대해 사용하도록 설정되어 있는지 확인하고 필요한 경우 사용하도록 설정합니다. | | [Microsoft 365 또는 Office 365에서 Microsoft Teams 설정](office-365-set-up.md) |
| 3  | 역할 및 사용 권한 구성 | 팀은 멤버 및 소유자의 두 가지 역할을 지원합니다. <br/><br/>팀에 멤버를 추가한 후 소유자는 구성원을 소유자 역할로 승격할 수 있습니다. 모범 사례로 각 팀에 할당된 소유자가 2명 이상 있는 것이 좋습니다. <br/><br/>기본적으로 Exchange Online에 호스트된 사서함이 있는 조직의 모든 사람이 팀을 만들 수 있습니다. 새 팀을 만드는 사용자에게는 해당 팀에 대한 소유자 역할이 자동으로 부여됩니다. <br/><br/>필요한 경우 특정 사용자가 새 팀을 만들도록 Microsoft 365 그룹 설정을 구성할 수 있습니다. | | [Microsoft Teams에서 역할 및 사용 권한 할당](assign-roles-permissions.md) <br/><br/>[Microsoft 365 그룹 및 Microsoft Teams](office-365-groups.md) <br/><br/>[Microsoft 365 그룹을 만들 수 있는 사용자 관리](https://support.office.com/article/Manage-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618) |
| 4  | 테넌트 전체 Teams 설정 구성 | 테넌트 수준에서 일부 Teams 설정을 구성할 수 있습니다. Teams에 사용하도록 설정된 사용자는 테넌트 구성에서 이러한 설정을 상속합니다.<ul><li>일반</li><li>전자 메일 통합</li><li>앱</li><li>사용자 지정 클라우드 저장소</li><li>통화 및 모임</li><li>메시징</li></ul>| | [조직에서 Microsoft Teams 설정 관리](enable-features-office-365.md) |
| 5  | 선택 사항: 게스트 액세스 구성 | Teams에서 게스트 액세스를 사용하여 팀 및 채널에 대한 액세스 권한을 부여하여 조직 외부 사용자와 공동 작업할 수 있습니다. 게스트 액세스는 Teams의 테넌트 수준 설정입니다. 이는 기본적으로 해제되어 있습니다. <br/>조직에서 해당 기능을 사용할 계획인 경우 게스트 액세스를 사용하도록 설정하고 테넌트 전체 게스트 설정을 구성합니다. | | [Microsoft Teams의 게스트 액세스](guest-access.md) |
| 6  | 선택 사항: Teams 이름 정책 구성 | Teams는 사용자가 팀 이름을 만들거나 편집할 때 Microsoft 365 그룹에 대한 명명 정책을 활용합니다. <br/><br/>기본적으로 사용자가 팀을 만드는 경우 이름 제한이 적용되지 않습니다. <br/><br/>팀 이름에 대한 규칙을 적용해야 하는 경우 조직에 적용되는 Microsoft 365 그룹 명명 정책을 구성합니다. 필수 접두사 및 접미사를 설정하고 차단된 단어를 지정할 수 있습니다. | | [Microsoft Teams에서 팀을 만들 때 Microsoft 365 그룹 계획](plan-office-365-groups.md) <br/><br/>[Microsoft 365 그룹 이름 정책](https://support.office.com/article/Office-365-Groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552) |
| 7  | Teams SMTP 도메인에 대한 Exchange 구성 | Teams는 Exchange Online을 사용하여 SMTP 도메인을 사용하여 팀 구성원에게 알림을 email.teams.microsoft.com 추가되거나 제거된 경우 팀 구성원에게 알림을 전송합니다. <br/><br/>Exchange 인프라에서 허용되는 도메인 목록에 이 SMTP 도메인을 추가해야 합니다. | | [Exchange에서 안전한 보낸 사람 목록 만들기](/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365?view=o365-worldwide) |
| 8  | Teams에 대한 사용자 액세스 구성 및 관리 | Teams에 대해 모든 사용자를 사용하도록 설정하는 것이 좋습니다. Teams 제품 라이선스를 할당하거나 제거하여 사용자당 Teams에 대한 액세스를 허용하거나 허용하지 않습니다. | | [Microsoft Teams에 대한 사용자 액세스 관리](user-access.md) |
| 9  | 사용자에게 라이선스 할당 | 오디오 회의, 전화 시스템 및 통화 계획과 같은 기능에 대해 사용자에게 라이선스 할당 | | [Microsoft Teams 추가 기능 라이선스 할당](teams-add-on-licensing/assign-teams-add-on-licenses.md)|
| 10 | 선택 사항: PowerShell을 사용하여 Teams 관리 | Microsoft 365 관리 센터가 아닌 PowerShell cmdlet을 사용하여 Teams 설정을 관리하고 관리할 수 있습니다. | | [Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) |