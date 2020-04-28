---
title: 온 보 딩 검사 목록-핵심 기능 구성-Microsoft 팀
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 조직의 팀을 구성할 때이 검사 목록의 핵심, 할 일 작업 및 활동을 따릅니다.
ms.custom: seo-marvel-apr2020
localization_priority: Normal
f1.keywords:
- NOCSH
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 69874e9d75cea1377b0aae110b5e1b3ce681d84f
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43903903"
---
# <a name="configure-microsoft-teams-core-capabilities"></a>Microsoft 팀 핵심 기능 구성

| 아니요 | 활동 또는 작업 | 설명 | 완료? | 추가 정보 |
|----|-----------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | 환경에 모든 팀 필수 구성 요소가 포함 되어 있는지 확인 | 팀은 다른 플랫폼에 의존 하 여 종단 간 공동 작업 솔루션을 구성 합니다. IT 팀과 협력 하 여 Exchange, SharePoint Online, 비즈니스용 OneDrive를 배포 하 고 올바르게 구성 했는지 확인 합니다. | | [SharePoint Online 및 비즈니스용 OneDrive가 Microsoft 팀과 상호 작용 하는 방법](sharepoint-onedrive-interact.md) <br/><br/>[Exchange 및 Microsoft 팀의 상호 작용 방식](exchange-teams-interact.md) |
| 2  | 팀이 테 넌 트에 대해 사용 하도록 설정 되었는지 확인 | 팀은 기본적으로 모든 조직에 대해 설정 됩니다. Microsoft 365 관리 센터의 **서비스 & 추가 기능** 페이지를 확인 하 여 팀이 테 넌 트에 대해 사용 하도록 설정 되어 있는지 확인 하 고 필요한 경우 사용 하도록 설정 합니다. | | [Microsoft 365 또는 Office 365에서 Microsoft 팀 설정](office-365-set-up.md) |
| 3  | 역할 및 사용 권한 구성 | 팀은 구성원 및 소유자 라는 두 가지 역할 유형을 지원 합니다. <br/><br/>팀에 구성원을 추가 하 고 나면 소유자는 구성원을 소유자 역할로 승격할 수도 있습니다. 가장 좋은 방법은 각 팀에 두 개 이상의 소유자를 할당 하는 것입니다. <br/><br/>기본적으로 Exchange Online에서 사서함을 호스팅하는 조직의 모든 사용자가 팀을 만들 수 있습니다. 새 팀을 만드는 사용자에 게 해당 팀의 소유자 역할이 자동으로 부여 됩니다. <br/><br/>필요한 경우 특정 사용자만 새 팀을 만들 수 있도록 Office 365 그룹 설정을 구성할 수 있습니다. | | [Microsoft 팀에서 역할 및 사용 권한 할당](assign-roles-permissions.md) <br/><br/>[Microsoft 365 그룹 및 Microsoft 팀](office-365-groups.md) <br/><br/>[Microsoft 365 그룹을 만들 수 있는 사용자 관리](https://support.office.com/article/Manage-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618) |
| 4(tcp/ipv4)  | 테 넌 트 전체 팀 설정 구성 | 테 넌 트 수준에서 일부 팀 설정을 구성할 수 있습니다. 팀에 대해 사용 하도록 설정 된 사용자는 테 넌 트 구성에서 이러한 설정을 상속 합니다.<ul><li>일반</li><li>전자 메일 통합</li><li>앱</li><li>사용자 지정 클라우드 저장소</li><li>통화 및 모임</li><li>메시징</li></ul>| | [조직에서 Microsoft Teams 설정 관리](enable-features-office-365.md) |
| 5mb  | 선택 사항: 게스트 액세스 구성 | 팀에서 게스트 액세스를 사용 하 여 조직 외부 사용자와 팀 및 채널에 대 한 액세스 권한을 부여 하 여 공동 작업을 수행 합니다. 게스트 액세스는 팀의 테 넌 트 수준 설정입니다. 이는 기본적으로 해제되어 있습니다. <br/>조직에서 해당 기능을 사용할 계획인 경우 게스트 액세스를 사용 하도록 설정 하 고 테 넌 트 전체 게스트 설정을 구성 합니다. | | [Microsoft Teams의 게스트 액세스](guest-access.md) |
| 26  | 선택 사항: 팀 명명 정책 구성 | 사용자가 팀 이름을 만들거나 편집할 때 Microsoft 365 그룹에 대 한 이름 지정 정책을 활용 하는 팀 <br/><br/>기본적으로 사용자가 팀을 만들 때 명명 제한이 적용 되지 않습니다. <br/><br/>팀 이름에 대 한 규칙을 적용 해야 하는 경우 조직에 적용 되는 Microsoft 365 그룹 명명 정책을 구성 합니다. 필수 접두사와 접미사를 설정 하 고 차단 된 단어를 지정할 수 있습니다. | | [Microsoft 팀에서 팀을 만들 때 Microsoft 365 그룹에 대 한 계획](plan-office-365-groups.md) <br/><br/>[Microsoft 365 그룹 이름 지정 정책](https://support.office.com/article/Office-365-Groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552) |
| 7  | 팀 SMTP 도메인에 대 한 Exchange 구성 | 팀은 Exchange Online을 사용 하 여 SMTP 도메인 (email.teams.microsoft.com)이 추가 또는 제거 된 경우이를 사용 하 여 팀 구성원에 게 알림을 보냅니다. <br/><br/>이 SMTP 도메인을 Exchange 인프라의 허용 도메인 목록에 추가 해야 합니다. | | [Exchange Online에서 Microsoft 팀 SMTP 도메인을 허용 도메인으로 추가](smtp-accepted-domain.md) |
| 20cm(8  | 팀에 대 한 사용자 액세스 구성 및 관리 | 팀의 모든 사용자를 사용 하도록 설정 하는 것이 좋지만 팀 제품 라이선스를 할당 하거나 제거 하 여 사용자 별로 팀에 대 한 액세스를 허용 하거나 허용 하지 않을 수 있습니다. | | [Microsoft 팀에 대 한 사용자 액세스 관리](user-access.md) |
| 되었는지  | 사용자에 게 라이선스 할당 | 오디오 회의, 전화 시스템, 통화 요금제 등의 기능에 대 한 라이선스를 사용자에 게 할당 | | [비즈니스용 Skype 및 Microsoft 팀 라이선스 할당](assign-teams-licenses.md)|
| 1천만 | 선택 사항: PowerShell을 사용 하 여 팀 관리 | Microsoft 365 관리 센터 대신 PowerShell cmdlet을 사용 하 여 팀 설정을 관리 하 고 관리할 수 있습니다. | | [Microsoft 팀 PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) |
