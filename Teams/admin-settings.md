---
title: Microsoft Teams의 앱에 대한 관리자 설정
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: ritikag, rarang
description: Microsoft Teams에서 조직의 앱을 관리하는 데 사용할 수 있는 정책 및 설정에 대해 자세히 알아보습니다.
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.adminsettings
- ms.teamsadmincenter.apppermspolicies.orgwideapps.thirdpartyapps
- ms.teamsadmincenter.apppolicies.adminsettings
- NewAdminCenter_Update
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0594317c21f3ef2a30d1772959458f33bef393eb
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094384"
---
<a name="admin-settings-for-apps-in-microsoft-teams"></a>Microsoft Teams의 앱에 대한 관리자 설정
==========================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

앱은 조직에서 Teams를 더 많이 활용하기 위해 사용할 수 있는 도구를 제공합니다. 이러한 앱은 타사 또는 조직의 개발자가 Microsoft에서 제공하는 탭, 메시징 확장, 커넥터 및 봇의 기능을 결합합니다.

관리 센터의 Teams **앱에서** 조직의 앱을 관리합니다. (Teams 관리자 역할 사용을 참조하여 [Teams를](./using-admin-roles.md) 관리하여 관리자 역할 및 사용 권한 부여에 대해 읽습니다.) 예를 들어 조직 수준에서 앱을 허용하거나 차단하고, Teams 사용자가 사용할 수 있는 앱을 제어하도록 정책을 설정하고, 사용자에게 가장 중요한 앱을 고정하여 Teams를 사용자 지정할 수 있습니다.

Teams에서 앱 환경을 지속적으로 개선하고 기능 및 기능을 추가하고 있습니다. 시간이 지날 때 추가 앱 관리 기능을 구축할 예정이니 앱 정책에 대한 최신 정보를 다시 확인하세요.

## <a name="manage-apps"></a>앱 관리

앱 관리 **페이지를** 사용하여 조직의 앱 카탈로그에서 모든 Teams 앱을 보고 관리합니다. 앱의 구성 수준 상태 및 속성을 보고, 구성 수준에서 앱을 차단하거나 허용하고, 테넌트 카탈로그에 새 사용자 지정 앱을 업로드하고, 전체 앱 설정을 관리할 수 있습니다.

앱 **관리** 페이지에서 테넌트 카탈로그에서 사용 가능한 모든 앱에 대한 보기를 제공하여 조직 전체에서 허용하거나 차단할 앱을 결정하는 데 필요한 정보를 제공합니다. 그런 다음 앱 권한 [정책,](#app-permission-policies)앱 [](#custom-app-policies-and-settings) 설정 정책 [및](#app-setup-policies)사용자 지정 앱 정책 및 설정을 사용하여 조직의 특정 사용자에 대한 앱 환경을 구성할 수 있습니다.

자세한 내용은 [Teams에서 앱 관리를 참조하세요.](manage-apps.md)

## <a name="app-permission-policies"></a>앱 사용 권한 정책

앱 사용 권한 정책을 사용하면 조직의 특정 사용자가 사용할 수 있는 앱을 제어할 수 있습니다. 모든 앱 또는 Microsoft, 타사 및 조직에서 게시한 특정 앱을 허용하거나 차단할 수 있습니다.

예를 들어 앱 사용 권한 정책을 사용하여 다음을 사용할 수 있습니다.

- 특정 사용자에게 새 타사 또는 사용자 지정 기본 앱을 점진적으로 롤아웃합니다.
- 특히 조직 전체에서 Teams를 롤아웃하기 시작할 때 사용자 환경을 간소화합니다.

자세한 내용은 Teams 에서 앱 [권한 정책 관리로 이동하세요.](teams-app-permission-policies.md)

## <a name="app-setup-policies"></a>앱 설정 정책

앱 설정 정책을 사용하면 사용자에 대한 앱 환경을 사용자 지정할 수 있습니다. Teams 클라이언트의 앱 표시줄에 고정할 앱과 웹, 데스크톱 및 모바일 클라이언트에 나타나는 순서를 선택할 수 있습니다.

앱 설정 정책을 사용하는 방법에 대한 몇 가지 예는 다음과 같습니다.

- 핵심 앱 인식 및 채택을 주도합니다. 예를 들어 HR 팀의 사용자를 위한 사용자 지정 채용 및 인재 관리 앱을 고정합니다.
- 채팅, Teams 및 통화와 같은 핵심 Teams 기능을 선택적으로 고정합니다. 이렇게 하면 사용자가 Teams 내에서 특정 활동에 참여하도록 할 수 있습니다.

자세한 내용은 Teams 에서 앱 [설정 정책 관리를 확인하세요.](teams-app-setup-policies.md)

## <a name="custom-app-policies-and-settings"></a>사용자 지정 앱 정책 및 설정

Teams를 사용하면 조직의 개발자가 다른 사용자에게 사용자 지정 앱을 빌드, 테스트 및 배포할 수 있습니다. 사용자 지정 앱은 .zip 파일에서 팀 또는 개인 상황에 직접 앱 패키지를 업로드하여 Teams에 추가할 수 있습니다. 앱 설정 정책을 사용하여 조직에서 사용자 지정 앱을 업로드할 수 있는 사용자 지정을 제어할 수 있습니다. 또한 사용자가 특정 사용자 지정 앱과 상호 작용할 수 있는지 여부를 제어하도록 org-wide 설정을 설정할 수도 있습니다.

자세한 내용은 Teams 에서 사용자 지정 앱 정책 [및 설정 관리로 이동합니다.](teams-custom-app-policies-and-settings.md)