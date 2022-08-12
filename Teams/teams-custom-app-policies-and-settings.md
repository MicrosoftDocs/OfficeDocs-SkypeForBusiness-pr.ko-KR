---
title: 사용자 지정 앱 정책 및 설정 관리
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 사용자 지정 앱 정책 및 설정을 관리하여 조직에서 Microsoft Teams에 사용자 지정 앱을 업로드할 수 있는 사람을 제어하는 방법을 알아봅니다.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.allowsideloading
- ms.teamsadmincenter.appsetuppolicies.tooltip.allowsideloading
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- seo-marvel-mar2020
ms.openlocfilehash: 45b6ec9809fe0c86f1a4acb69ef78c5c5f30f230
ms.sourcegitcommit: 63dcc92b2d5d50e2c0c074a1209625e16086ca45
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/10/2022
ms.locfileid: "67299137"
---
# <a name="manage-custom-app-policies-and-settings-in-microsoft-teams"></a>Microsoft Teams에서 사용자 지정 앱 정책 및 설정 관리

관리자는 사용자 지정 앱 정책 및 설정을 사용하여 조직에서 Microsoft Teams에 사용자 지정 앱을 업로드할 수 있는 사람을 제어할 수 있습니다. 관리자는 사용자 지정 앱을 업로드할 수 있는 사용자를 결정하고 관리자와 팀 소유자는 조직의 특정 팀에서 사용자 지정 앱을 추가하도록 허용할지 여부를 결정할 수 있습니다.  사용자 지정 앱 정책을 수정한 후 변경 사항이 적용되는 데 몇 시간이 걸릴 수 있습니다. 이러한 정책을 관리하려면 전역 관리자 또는 Teams 서비스 관리자여야 합니다.

조직의 개발자는 앱 패키지(.zip 파일)를 팀 또는 개인 컨텍스트에 직접 업로드하여 Teams에 사용자 지정 앱을 추가할 수 있습니다. 이 작업은 Teams 앱 스토어를 통해 앱을 추가하는 방법과 다릅니다. 사이드로딩이라고도 하는 앱 패키지 업로드를 통해 사용자 지정 앱을 추가하면 앱이 널리 배포될 준비가 되기 전에 조직 내의 특정 사용자가 개발 중인 앱을 테스트할 수 있습니다.

## <a name="custom-app-policy-and-settings"></a>사용자 지정 앱 정책 및 설정

세 가지 구성 요소는 사용자가 사용자 지정 앱을 팀에 업로드할 수 있는지 여부를 결정하여 팀에 사용자 지정 앱을 추가할 수 있는 사용자 및 사용자 지정 앱을 추가할 수 있는 팀에 대한 세부적인 제어를 제공합니다.

- [사용자 사용자 지정 앱 정책](#user-custom-app-policy)
- [팀 사용자 지정 앱 설정](#team-custom-app-setting)
- [조직 전체 사용자 지정 앱 설정](#org-wide-custom-app-setting)

이러한 설정은 타사 앱 차단 기능에 영향을 미치지 않습니다.  

### <a name="user-custom-app-policy"></a>사용자 사용자 지정 앱 정책

[앱 설정 정책](teams-app-setup-policies.md)의 일부로 관리자는 정책 설정인 **사용자 지정 앱 업로드** 를 사용하여 사용자가 사용자 지정 앱을 Teams에 업로드할 수 있는지를 제어할 수 있습니다.

이 설정이 꺼져 있는 경우:

- 사용자는 조직의 팀이나 개인 컨텍스트에서 사용자 지정 앱을 업로드할 수 없습니다.
- 사용자는 조직 전체의 사용자 지정 앱 설정에 따라 사용자 지정 앱과 상호 작용할 수 있습니다.

이 설정이 켜져 있는 경우:

- 사용자는 조직 전체의 사용자 지정 앱 설정에 따라 사용자 지정 앱을 허용하는 팀과 자신이 소유자인 팀에 업로드할 수 있습니다.
- 사용자는 개인 컨텍스트에 사용자 지정 앱을 업로드할 수 있습니다.
- 사용자는 조직 전체의 사용자 지정 앱 설정에 따라 사용자 지정 앱과 상호 작용할 수 있습니다.

전역 앱 설정 정책의 설정을 편집하여 원하는 앱을 포함할 수 있습니다. 조직의 여러 사용자 그룹에 대해 Teams를 사용자 지정하려면 하나 이상의 사용자 지정 앱 설정 정책을 만들고 할당합니다.

#### <a name="set-a-user-custom-app-policy"></a>사용자 사용자 지정 앱 정책 설정

1. Microsoft Teams 관리 센터의 왼쪽 탐색에서 **Teams 앱** > **설정 정책** 으로 이동합니다.
2. **추가** 를 클릭합니다.
3. **사용자 지정 앱 업로드** 를 켜거나 끕니다.
4. 정책에 대해 원하는 다른 설정을 선택합니다.
5. **저장** 을 클릭합니다.

### <a name="team-custom-app-setting"></a>팀 사용자 지정 앱 설정

관리자와 팀 소유자는 팀에서 사용자 지정 앱을 추가하도록 허용할지 여부를 제어할 수 있습니다. **구성원이 사용자 지정 앱을 업로드하도록 허용** 설정은 사용자의 사용자 지정 앱 정책과 함께 특정 팀에 사용자 지정 앱을 추가할 수 있는 사람을 결정합니다.

이 설정이 꺼져 있는 경우:

- 팀 소유자는 사용자 지정 앱 정책에서 허용하는 경우 사용자 지정 앱을 추가할 수 있습니다.
- 팀 소유자가 아닌 팀원은 팀에 사용자 지정 앱을 추가할 수 없습니다.

이 설정이 켜져 있는 경우:

- 팀 소유자는 사용자 지정 앱 정책에서 허용하는 경우 사용자 지정 앱을 추가할 수 있습니다.
- 팀 소유자가 아닌 팀원은 사용자 지정 앱 정책에서 허용하는 경우 사용자 지정 앱을 추가할 수 있습니다.

#### <a name="configure-the-team-custom-app-setting"></a>팀 사용자 지정 앱 설정 구성

1. Teams에서 팀으로 이동하여 **기타 옵션...**  >  **팀 관리** 를 클릭합니다.
2. **설정** 을 클릭한 다음 **구성원 권한** 을 확장합니다.
3. **구성원이 사용자 지정 앱을 업로드하도록 허용** 확인란을 선택하거나 선택 취소합니다.

    ![팀 사용자 지정 앱 설정을 보여 주는 스크린샷](media/teams-custom-app-policy-and-settings-team.png)

### <a name="org-wide-custom-app-setting"></a>조직 전체 사용자 지정 앱 설정

[앱 관리](manage-apps.md) 페이지의 **사용자 지정 앱과의 상호작용 허용** 조직 전체 사용자 지정 앱 설정은 조직의 모든 사용자에 적용되며 이들이 사용자 지정 앱을 업로드하거나 앱과 상호작용할 수 있는지 제어합니다. 이 설정은 사용자 및 팀 사용자 지정 앱 정책 설정에 대한 마스터 켜기/끄기 스위치 역할을 합니다. 보안 이벤트 중에 마스터 켜기/끄기 스위치 역할을 하기 위한 것입니다. 따라서 사용자 및 팀 사용자 지정 앱 정책 설정을 사용하도록 설정한 경우에도 조직 전체의 사용자 지정 앱 설정을 사용하도록 설정하지 않으면 사용자 및 팀 사용자 지정 앱 정책 설정이 적용되지 않습니다.

#### <a name="configure-the-org-wide-custom-app-setting"></a>조직 전체 사용자 지정 앱 설정 구성

1. Microsoft Teams 관리 센터의 왼쪽 탐색 창에서 **Teams 앱** > **앱 관리** 로 이동합니다.
2. **조직 전체 앱 설정** 을 클릭합니다.
3. **사용자 지정 앱** 에서 **사용자 지정 앱과의 상호 작용 허용** 을 켜거나 끕니다.

    ![조직 전체의 사용자 지정 앱 설정을 보여 주는 스크린샷](media/teams-custom-app-policy-and-settings-org-wide.png)

## <a name="how-custom-app-policies-and-settings-work-together"></a>사용자 지정 앱 정책 및 설정이 함께 작동하는 방식

이 테이블에는 사용자 지정 앱 정책 및 설정, 함께 작동하는 방식, 사용자 지정 앱을 Teams에 업로드할 수 있는 조직 내 사용자 제어에 대한 결합된 효과가 요약되어 있습니다.

예를 들어 팀 소유자만 특정 팀에 사용자 지정 앱을 업로드할 수 있도록 허용한다고 가정합니다. 다음을 설정합니다.

- Microsoft Teams 관리 센터에서 **사용자 지정 앱과의 상호 작용 허용** 설정을 켭니다.
- 액세스를 제한하려는 모든 팀에 대해 **구성원이 사용자 지정 앱을 업로드하도록 허용** 을 끕니다.
- **사용자가 사용자 지정 앱을 업로드할 수 있음** 설정이 켜져 있는 Microsoft Teams 관리 센터에서 사용자 지정 앱 설정 정책을 만들고 할당하고 이를 팀 소유자에게 할당합니다.

|조직 전체 사용자 지정 앱 설정 |팀 사용자 지정 앱 설정 |사용자 사용자 지정 앱 정책 |결과  |
|---------|---------|---------|---------|
| 해제    | 해제    | 해제     |조직에서 모든 사용자 지정 앱과의 상호 작용이 차단됩니다. Teams 서비스 관리자나 전역 관리자를 제외하면 아무도 사용자 지정 앱을 업로드할 수 없습니다. PowerShell을 사용해 사용자 지정 앱을 제거할 수 있습니다.   |
| 해제     | 해제     | 설정        |조직에서 모든 사용자 지정 앱과의 상호 작용이 차단됩니다. Teams 서비스 관리자나 전역 관리자를 제외하면 아무도 사용자 지정 앱을 업로드할 수 없습니다. PowerShell을 사용해 사용자 지정 앱을 제거할 수 있습니다.         |
| 해제    | 설정        | 해제        |조직에서 모든 사용자 지정 앱과의 상호 작용이 차단됩니다. Teams 서비스 관리자나 전역 관리자를 제외하면 아무도 사용자 지정 앱을 업로드할 수 없습니다. Windows PowerShell을 사용해 사용자 지정 앱을 삭제할 수 있습니다.         |
| 해제    | 설정      | 설정       |조직에서 모든 사용자 지정 앱과의 상호 작용이 차단됩니다. Teams 서비스 관리자나 전역 관리자를 제외하면 아무도 사용자 지정 앱을 업로드할 수 없습니다. PowerShell을 사용해 사용자 지정 앱을 제거할 수 있습니다.         |
| 설정    | 해제       | 해제         |  사용자는 사용자 지정 앱을 업로드할 수 없습니다.      |
| 설정     | 해제       | 설정         | 사용자가 팀 소유자인 경우 사용자 지정 앱을 팀에 업로드할 수 있습니다. 사용자가 팀 소유자가 아닌 경우 사용자 지정 앱을 팀에 업로드할 수 없습니다. 사용자는 개인 컨텍스트에서 사용자 정의 앱을 업로드할 수 있습니다.     |
| 설정     | 설정     | 해제         | 사용자는 사용자 지정 앱을 업로드할 수 없습니다.       |
| 설정    | 설정        | 설정        | 사용자는 사용자가 팀 소유자인지 여부에 관계없이 팀에 사용자 지정 앱을 업로드할 수 있습니다. 사용자는 개인 컨텍스트에서 사용자 정의 앱을 업로드할 수 있습니다.       |

## <a name="related-topics"></a>관련 주제

[Teams의 앱에 대한 관리 설정](admin-settings.md)

[Teams에서 사용자에게 정책 할당](assign-policies-users-and-groups.md)
