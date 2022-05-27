---
title: 사용자 지정 앱 정책 및 설정 관리
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.reviewer: akino
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
description: 사용자 지정 앱 정책 및 설정을 관리하여 Microsoft Teams 사용자 지정 앱을 업로드할 수 있는 조직의 사용자를 제어하는 방법을 알아봅니다.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.allowsideloading
- ms.teamsadmincenter.appsetuppolicies.tooltip.allowsideloading
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- seo-marvel-mar2020
ms.openlocfilehash: 120f19472a0438c6bb76e98e0c8ef473c012c7b7
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681389"
---
# <a name="manage-custom-app-policies-and-settings-in-microsoft-teams"></a>Microsoft Teams 사용자 지정 앱 정책 및 설정 관리

> [!NOTE]
> App Studio를 사용하려면 [C#/.NET 및 App Studio를 사용하여 Microsoft Teams 플랫폼에서 시작](/microsoftteams/platform/get-started/get-started-dotnet-app-studio) 참조하세요. 마지막 단계가 아직 작동하지 않으므로 zip을 다운로드하여 [Microsoft Teams 앱 패키지를 업로드](/microsoftteams/platform/concepts/apps/apps-upload) 이전 방식으로 설치해야 합니다.

관리자는 사용자 지정 앱 정책 및 설정을 사용하여 조직에서 사용자 지정 앱을 Microsoft Teams 업로드할 수 있는 사용자를 제어할 수 있습니다. 관리자는 사용자 지정 앱을 업로드할 수 있는 사용자를 결정하고 관리자와 팀 소유자는 조직의 특정 팀이 사용자 지정 앱을 추가할 수 있도록 허용할지 여부를 결정할 수 있습니다.  사용자 지정 앱 정책을 편집한 후 변경 내용을 적용하는 데 몇 시간이 걸릴 수 있습니다. 이러한 정책을 관리하려면 전역 관리자 또는 Teams 서비스 관리자여야 합니다.

## <a name="overview-of-custom-apps"></a>사용자 지정 앱 개요

사용자는 팀 또는 개인 컨텍스트에서 앱 패키지(.zip 파일)를 직접 업로드하여 Teams 사용자 지정 앱을 추가할 수 있습니다. 이는 Teams 앱 스토어를 통해 앱을 추가하는 방법과 다릅니다. 테스트용 로드라고도 하는 앱 패키지를 업로드하여 사용자 지정 앱을 추가하면 널리 배포할 준비가 되기 전에 개발 중인 앱을 테스트할 수 있습니다. 또한 내부용으로만 앱을 빌드하고 Teams 앱 스토어의 Teams 앱 카탈로그에 제출하지 않고 팀과 공유할 수 있습니다.

![앱 스토어에서 사용자 지정 앱 업로드 옵션을 보여 주는 스크린샷](media/teams-custom-app-policy-and-settings-upload-app.png)

## <a name="custom-app-policy-and-settings"></a>사용자 지정 앱 정책 및 설정

세 가지 구성 요소는 사용자가 팀에 사용자 지정 앱을 업로드할 수 있는지 여부를 결정하여 팀에 사용자 지정 앱을 추가할 수 있는 사용자 지정 앱과 추가할 수 있는 팀을 세부적으로 제어합니다.

- [사용자 지정 앱 정책](#user-custom-app-policy)
- [팀 사용자 지정 앱 설정](#team-custom-app-setting)
- [조직 전체 사용자 지정 앱 설정](#org-wide-custom-app-setting)

이러한 설정은 타사 앱을 차단하는 기능에 영향을 주지 않습니다.  

### <a name="user-custom-app-policy"></a>사용자 지정 앱 정책

[앱 설정 정책](teams-app-setup-policies.md)의 일부로 관리자는 사용자 **지정 앱을 업로드** 정책 설정을 사용하여 사용자가 사용자 지정 앱을 Teams 업로드할 수 있는지 여부를 제어할 수 있습니다.

이 설정이 꺼져 있는 경우:

- 사용자는 조직의 팀이나 개인 컨텍스트에서 사용자 지정 앱을 업로드할 수 없습니다.
- 사용자는 조직 전체의 사용자 지정 앱 설정에 따라 사용자 지정 앱과 상호 작용할 수 있습니다.

이 설정이 켜져 있는 경우:

- 사용자는 조직 전체의 사용자 지정 앱 설정에 따라 사용자 지정 앱을 허용하는 팀과 소유자인 팀에 업로드할 수 있습니다.
- 사용자는 개인 컨텍스트에 사용자 지정 앱을 업로드할 수 있습니다.
- 사용자는 조직 전체의 사용자 지정 앱 설정에 따라 사용자 지정 앱과 상호 작용할 수 있습니다.

전역 앱 설정 정책에서 설정을 편집하여 원하는 앱을 포함할 수 있습니다. 조직의 여러 사용자 그룹에 대한 Teams 사용자 지정하려면 하나 이상의 사용자 지정 앱 설정 정책을 만들고 할당합니다.

#### <a name="set-a-user-custom-app-policy"></a>사용자 지정 앱 정책 설정

1. Microsoft Teams 관리 센터의 왼쪽 탐색에서 **Teams 앱** > **설정 정책** 으로 이동합니다.
2. **추가** 를 클릭합니다.
3. **업로드 사용자 지정 앱을** 켜거나 끕니다.
4. 정책에 대해 원하는 다른 설정을 선택합니다.
5. **저장** 을 클릭합니다.

### <a name="team-custom-app-setting"></a>팀 사용자 지정 앱 설정

관리자 및 팀 소유자는 팀에서 사용자 지정 앱을 추가할 수 있는지 여부를 제어할 수 있습니다. 이 설정은 **구성원이 사용자 지정 앱을 업로드하도록 허용** 하고 사용자의 사용자 지정 앱 정책과 함께 특정 팀에 사용자 지정 앱을 추가할 수 있는 사용자를 결정합니다.

이 설정이 꺼져 있는 경우:

- 팀 소유자는 사용자 지정 앱 정책에서 허용하는 경우 사용자 지정 앱을 추가할 수 있습니다.
- 팀 소유자가 아닌 팀 구성원은 팀에 사용자 지정 앱을 추가할 수 없습니다.

이 설정이 켜져 있는 경우:

- 팀 소유자는 사용자 지정 앱 정책이 허용하는 경우 사용자 지정 앱을 추가할 수 있습니다.
- 팀 소유자가 아닌 팀 구성원은 사용자 지정 앱 정책이 허용하는 경우 사용자 지정 앱을 추가할 수 있습니다.

#### <a name="configure-the-team-custom-app-setting"></a>팀 사용자 지정 앱 설정 구성

1. Teams 팀으로 이동하여 **추가 옵션을 클릭합니다.** >  **팀을 관리합니다**.
2. **설정** 클릭한 다음 **멤버 권한을 확장합니다**.
3. **구성원이 사용자 지정 앱을 업로드할 수 있도록** 허용 확인란을 선택하거나 선택 취소합니다.

    ![팀 사용자 지정 앱 설정을 보여 주는 스크린샷.](media/teams-custom-app-policy-and-settings-team.png)

### <a name="org-wide-custom-app-setting"></a>조직 전체 사용자 지정 앱 설정

앱 [관리](manage-apps.md) 페이지의 사용자 지정 앱 조직 전체 사용자 지정 앱 설정 **과의 상호 작용 허용** 은 조직의 모든 사용자에게 적용되며 사용자 지정 앱을 업로드하거나 상호 작용할 수 있는지 여부를 제어합니다. 이 설정은 사용자 및 팀 사용자 지정 앱 정책 설정에 대한 마스터 켜기/끄기 스위치 역할을 합니다. 보안 이벤트 중에 마스터 켜기/끄기 스위치 역할을 하기 위한 것입니다. 따라서 사용자 및 팀 사용자 지정 앱 정책 설정을 사용하도록 설정한 경우에도 조직 전체의 사용자 지정 앱 설정을 사용하도록 설정하지 않는 한 사용자 및 팀 사용자 지정 앱 정책 설정이 적용되지 않습니다.

#### <a name="configure-the-org-wide-custom-app-setting"></a>조직 전체 사용자 지정 앱 설정 구성

1. Microsoft Teams 관리 센터의 왼쪽 탐색 창에서 **Teams 앱** > **앱 관리** 로 이동합니다.
2. **조직 전체 앱 설정을** 클릭합니다.
3. **사용자 지정 앱에서 사용자 지정 앱****과의 상호 작용 허용** 을 켜거나 끕니다.

    ![조직 전체 사용자 지정 앱 설정을 보여 주는 스크린샷.](media/teams-custom-app-policy-and-settings-org-wide.png)

## <a name="how-custom-app-policies-and-settings-work-together"></a>사용자 지정 앱 정책 및 설정이 함께 작동하는 방법

이 표에는 사용자 지정 앱 정책 및 설정, 함께 작동하는 방법 및 조직에서 사용자 지정 앱을 Teams 업로드할 수 있는 사용자를 제어하는 데 미치는 결합된 영향이 요약되어 있습니다.

예를 들어 팀 소유자만 특정 팀에 사용자 지정 앱을 업로드하도록 허용하려고 합니다. 다음을 설정합니다.

- Microsoft Teams 관리 센터에서 **사용자 지정 앱 설정과의 상호 작용 허용** 을 켭니다.
- 구성원이 액세스를 제한하려는 모든 팀에 대해 **사용자 지정 앱을 업로드하도록 허용** 을 해제합니다.
- 업로드 사용자 지정 앱 설정이 켜져 있는 Microsoft Teams 관리 센터에서 **사용자 지정 앱** 설정 정책을 만들고 할당하고 팀 소유자에게 할당합니다.

|조직 전체 사용자 지정 앱 설정 |팀 사용자 지정 앱 설정 |사용자 지정 앱 정책 |효과  |
|---------|---------|---------|---------|
| 해제    | 해제    | 해제     |모든 사용자 지정 앱과의 상호 작용은 조직에 대해 차단됩니다. Teams Service 관리 또는 전역 관리자를 제외한 다른 사용자가 사용자 지정 앱을 업로드할 수 없습니다. PowerShell을 사용하여 사용자 지정 앱을 제거할 수 있습니다.   |
| 해제     | 해제     | 설정        |모든 사용자 지정 앱과의 상호 작용은 조직에 대해 차단됩니다. Teams Service 관리 또는 전역 관리자를 제외한 다른 사용자가 사용자 지정 앱을 업로드할 수 없습니다. PowerShell을 사용하여 사용자 지정 앱을 제거할 수 있습니다.         |
| 해제    | 설정        | 해제        |모든 사용자 지정 앱과의 상호 작용은 조직에 대해 차단됩니다. Teams Service 관리 또는 전역 관리자를 제외한 다른 사용자가 사용자 지정 앱을 업로드할 수 없습니다. Windows PowerShell 사용하여 사용자 지정 앱을 삭제할 수 있습니다.         |
| 해제    | 설정      | 설정       |모든 사용자 지정 앱과의 상호 작용은 조직에 대해 차단됩니다. Teams Service 관리 또는 전역 관리자를 제외한 다른 사용자가 사용자 지정 앱을 업로드할 수 없습니다. PowerShell을 사용하여 사용자 지정 앱을 제거할 수 있습니다.         |
| 설정    | 해제       | 해제         |  사용자가 사용자 지정 앱을 업로드할 수 없습니다.      |
| 설정     | 해제       | 설정         | 사용자가 팀 소유자인 경우 사용자 지정 앱을 팀에 업로드할 수 있습니다. 사용자가 팀 소유자가 아닌 경우 사용자 지정 앱을 팀에 업로드할 수 없습니다. 사용자는 개인 컨텍스트에서 사용자 지정 앱을 업로드할 수 있습니다.     |
| 설정     | 설정     | 해제         | 사용자가 사용자 지정 앱을 업로드할 수 없습니다.       |
| 설정    | 설정        | 설정        | 사용자가 팀 소유자인지 여부에 관계없이 사용자가 팀에 사용자 지정 앱을 업로드할 수 있습니다. 사용자는 개인 컨텍스트에서 사용자 지정 앱을 업로드할 수 있습니다.       |

## <a name="related-topics"></a>관련 항목

[Teams의 앱에 대한 관리 설정](admin-settings.md)

[Teams에서 사용자에게 정책 할당](assign-policies-users-and-groups.md)
