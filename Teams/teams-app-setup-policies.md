---
title: Microsoft 팀에서 앱 설치 정책 관리
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: lajin,rarang
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Microsoft 팀에서 앱 설정 정책에 대해 알아보고, 앱을 고정 하는 데 사용 하 여 조직의 사용자를 위한 팀을 사용자 지정 하는 방법에 대해 알아봅니다.
f1keywords:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: e80cacb952bd456e742aa6da0fec32d50c5f3188
ms.sourcegitcommit: 5932ec62a42d7b392fa31c6a2a3462389ac24b73
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "41573800"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a>Microsoft 팀에서 앱 설치 정책 관리

> [!NOTE]
> 조직 전체 앱 권한 정책 설정을 사용 하도록 설정 하 고 **사용자 지정 앱과의 상호 작용을 허용**하는 경우 Microsoft 팀 관리 센터에 앱 설정 정책이 아직 표시 되지 않을 수 있습니다. 현재 출시 되 고 있으며 조직에서 곧 사용할 수 있게 됩니다.

관리자는 앱 설치 정책을 사용 하 여 Microsoft 팀을 사용자 지정 하 고 사용자에 게 가장 중요 한 앱을 강조 표시할 수 있습니다. 고정할 앱을 선택 하 고 표시 되는 순서를 설정 합니다. 앱 설정 정책을 사용 하 여 조직의 사용자에 게 제공 되는 앱을 포함 하거나 조직의 개발자가 조직에 따라 수행 해야 하는 앱을 전시 할 수 있습니다. 앱 설치 정책을 사용 하 여 사용자가 앱을 팀에 고정 하 고 기본 제공 기능이 표시 되는 방식을 관리할 수 있는지 여부를 제어할 수도 있습니다.

앱은 앱 표시줄에 고정 됩니다. 팀 데스크톱 클라이언트의 측면과 팀 모바일 클라이언트 (iOS 및 Android)의 맨 아래에 있는 막대입니다.

|팀 데스크톱 클라이언트  |팀 모바일 클라이언트 |
|---------|---------|
|![팀 데스크톱 클라이언트를 보여 주는 스크린샷](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![팀 모바일 클라이언트를 보여 주는 스크린샷](media/app-setup-policies-mobile-app-bar.png)      |

Microsoft 팀 관리 센터에서 앱 설치 정책을 관리할 수 있습니다. 전역 (조직 차원의 기본) 정책을 사용 하거나 사용자 지정 정책을 만들어 사용자에 게 할당할 수 있습니다. 사용자 지정 정책을 만들고 할당 하지 않으면 조직의 사용자가 자동으로 전역 정책을 받습니다.

전역 정책의 설정을 편집 하 여 원하는 앱을 포함할 수 있습니다. 조직의 다른 사용자 그룹에 대해 팀을 사용자 지정 하려면 하나 이상의 사용자 지정 정책을 만들고 할당 합니다. 사용자가 사용자 지정 정책을 할당 한 경우 해당 정책이 사용자에 게 적용 됩니다. 사용자가 사용자 지정 정책을 할당 하지 않으면 전역 정책이 사용자에 게 적용 됩니다.

![앱 설정 정책 페이지를 보여 주는 스크린샷](media/app-setup-policies.png)

> [!NOTE]
> 교육 팀이 있는 경우 현재 글로벌 정책에는 할당 앱이 기본적으로 고정 되어 있지만,이는 전역 정책에 나열 되지 않은 경우에도 확인 하는 것이 중요 합니다. 팀 클라이언트의 고정 된 앱 목록에서 네 번째 앱이 됩니다.

## <a name="create-a-custom-app-setup-policy"></a>사용자 지정 앱 설정 정책 만들기

Microsoft 팀 관리 센터를 사용 하 여 사용자 지정 정책을 만들 수 있습니다.

1. Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **팀 앱** > **설정 정책**으로 이동 합니다.
2. **추가**를 클릭 합니다.
    ![앱 설정 정책 추가 페이지를 보여 주는 스크린샷](media/app-setup-policies-add.png)
3. 정책의 이름 및 설명을 입력 합니다.
4. 사용자 지정 앱을 팀에 업로드 하도록 허용할지 여부에 따라 **사용자 지정 앱 업로드**를 설정 하거나 해제 합니다. 앱 권한 정책의 [조직 전체 앱 설정](teams-app-permission-policies.md#manage-org-wide-app-settings) 에서 타사 **앱 허용** 이 해제 되어 있는 경우이 설정을 변경할 수 없습니다.
5. 사용자에 게 앱을 고정 하 여 앱 표시줄을 개인 설정할 수 있도록 할지 여부에 따라 **사용자 고정 허용**을 설정 하거나 해제 합니다.
6. **앱 추가**를 클릭 합니다.
7. 고정 된 **앱 추가** 창에서 추가 하려는 앱을 검색 한 다음 **추가**를 클릭 합니다. 앱 사용 권한 정책을 기준으로 앱을 필터링 할 수도 있습니다. 앱 목록을 선택한 후 **추가**를 클릭 합니다.

     ![고정 된 앱 추가 창을 보여 주는 스크린샷](media/app-setup-policies-add-apps.png)

8. 팀에 표시할 순서 대로 앱을 정렬 한 다음 **저장**을 클릭 합니다.

    ![고정 된 앱 섹션을 보여 주는 스크린샷](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a>앱 설치 정책 편집

Microsoft 팀 관리 센터를 사용 하 여 전역 (조직 전체 기본값) 정책 및 직접 만든 사용자 지정 정책을 비롯 한 정책을 편집할 수 있습니다.

1. Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **팀 앱** > **설정 정책**으로 이동 합니다.
2. 정책 이름 왼쪽을 클릭 하 여 정책을 선택한 다음 **편집**을 클릭 합니다.
3. 여기서 원하는 대로 변경 합니다. 앱의 순서를 추가, 제거 및 변경할 수 있습니다.
4. **저장**을 클릭 합니다.

## <a name="assign-a-custom-app-setup-policy-to-users"></a>사용자에 게 사용자 지정 앱 설정 정책 할당

Microsoft 팀 관리 센터를 사용 하 여 사용자 지정 정책을 개인 사용자 또는 비즈니스용 Skype PowerShell 모듈에 할당 하 여 보안 그룹 또는 메일 그룹과 같은 사용자 그룹에 사용자 지정 정책을 할당할 수 있습니다.

### <a name="assign-a-custom-app-setup-policy-to-users"></a>사용자에 게 사용자 지정 앱 설정 정책 할당

1. Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **사용자**로 이동한 다음 사용자를 클릭 합니다.
2. 사용자 이름 왼쪽의을 클릭 하 여 사용자를 선택 하 고 **설정 편집**을 클릭 합니다.
3. **앱 설정 정책**에서 할당 하려는 앱 설정 정책을 선택한 다음 **적용**을 클릭 합니다.

한 번에 여러 사용자에 게 정책을 할당 하려면 [팀 사용자 설정을 일괄적으로 편집](edit-user-settings-in-bulk.md)을 참조 하세요.

또는 다음을 수행할 수도 있습니다.

1. Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **팀 앱** > **설정 정책**으로 이동 합니다.
2. 정책 이름 왼쪽에 있는을 클릭 하 여 정책을 선택 합니다.
3. **사용자 관리**를 선택 합니다.
4. **사용자 관리** 창에서 표시 이름 또는 사용자 이름을 사용 하 여 사용자를 검색 하 고 이름을 선택한 다음 **추가**를 선택 합니다. 추가 하려는 각 사용자에 대해이 단계를 반복 합니다.
5. 사용자 추가를 마쳤으면 **저장**을 선택 합니다.

### <a name="assign-a-custom-app-setup-policy-to-users-in-a-group"></a>그룹의 사용자에 게 사용자 지정 앱 설정 정책 할당

이미 식별 한 여러 사용자에 게 사용자 지정 앱 설정 정책을 할당 하려고 할 수 있습니다. 예를 들어 보안 그룹의 모든 사용자에 게 정책을 할당 하려고 할 수 있습니다. 그래프 모듈의 Azure Active Directory PowerShell 및 비즈니스용 Skype PowerShell 모듈에 연결 하 여이 작업을 수행할 수 있습니다. PowerShell을 사용 하 여 팀을 관리 하는 방법에 대 한 자세한 내용은 [팀 Powershell 개요](teams-powershell-overview.md)를 참조 하세요.

이 예제에서는 Contoso 금강 HR 프로젝트 그룹의 모든 사용자에 게 HR 앱 설정 정책 이라는 사용자 지정 앱 설정 정책을 할당 합니다.  

> [!NOTE]
> 먼저 [단일 Windows powershell 창에서 모든 Office 365 서비스에 연결](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)의 단계를 따라 Graph 모듈 및 비즈니스용 Skype powershell 모듈에 대 한 Azure Active Directory powershell에 연결 해야 합니다.

특정 그룹의 GroupObjectId를 가져옵니다.
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Pharmaceuticals HR Project"
```
지정 된 그룹의 구성원을 가져옵니다.
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
그룹의 모든 사용자를 특정 앱 설정 정책에 할당 합니다. 이 예제에서는 HR 앱 설정 정책입니다.
```PowerShell
$members | ForEach-Object { Grant-CsTeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $_.UserPrincipalName}
``` 
그룹의 구성원 수에 따라이 명령을 실행 하는 데 몇 분 정도 걸릴 수 있습니다.

## <a name="faq"></a>FAQ

### <a name="working-with-app-setup-policies"></a>앱 설정 정책 사용

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a>Microsoft 팀 관리 센터에 포함 된 기본 제공 앱 설정 정책은 무엇 인가요?

- **전역 (조직 전체 기본값)**: 다른 정책을 할당 하지 않는 한이 기본 정책은 조직의 모든 사용자에 게 적용 됩니다. 전역 정책을 편집 하 여 사용자에 게 가장 중요 한 앱을 고정 합니다.
- **Firstlineworker**:이 정책은 최초 작업자를 위한 것입니다. 조직의 첫 번째 작업자에 게 할당할 수 있습니다. 사용자 지정 정책과 마찬가지로, 설정이 활성화 되도록 사용자에 게 정책을 할당 해야 한다는 것을 이해 하는 것이 중요 합니다. 자세한 내용은이 문서의 [사용자에 게 사용자 지정 앱 설정 정책](#assign-a-custom-app-setup-policy-to-users) 지정 섹션을 참조 하세요.

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>고정 된 앱 추가 창에서 앱을 찾을 수 없는 이유는 무엇 인가요?

앱 설치 정책을 통해 일부 앱을 팀에 고정 시킬 수 있는 것은 아닙니다. 일부 앱은이 기능을 지원 하지 않을 수 있습니다. 고정 될 수 있는 앱을 찾으려면 **고정 된 앱 추가** 창에서 앱을 검색 합니다. 개인 범위 (정적 탭) 및 bot이 있는 탭은 팀 데스크톱 클라이언트에 고정 될 수 있으며, 이러한 앱은 **고정 된 앱 추가** 창에 있습니다.

팀 앱 스토어에는 모든 팀 앱이 나열 되는 반면, **고정 된 앱 추가** 창에는 정책을 통해 팀에 고정 될 수 있는 앱만 포함 된다는 점에 유의 하세요. 

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a>저는 교육 관리자를 위한 팀입니다. 교육용 팀에서 앱 설정 정책에 대해 알아야 할 사항

교육 팀에서는 호출 앱을 사용할 수 없습니다. 새 사용자 지정 앱 설치 정책을 만들면 앱 목록에 호출 앱이 표시 됩니다. 그러나 앱이 팀에 고정 되어 있지 않으며 교육용 사용자 용 팀에 팀의 통화 앱이 표시 되지 않습니다.

#### <a name="how-many-apps-can-be-added-to-a-policy"></a>정책에 추가할 수 있는 앱은 몇 개입니까?

최소 두 개의 앱을 팀 모바일 클라이언트 (iOS 및 Android)에 고정 해야 합니다. 정책에 두 개 미만의 앱이 있는 경우 모바일 클라이언트에는 정책 설정이 반영 되지 않으며 대신 기존 구성을 계속 사용할 수 있습니다.

정책에 추가할 수 있는 앱 수에는 제한이 없습니다.

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a>정책 변경 내용이 적용 되는 데 걸리는 시간

전역 정책을 편집 하거나 정책을 할당 한 후 변경 내용이 적용 되는 데 최대 24 시간이 걸릴 수 있습니다.

### <a name="user-experience"></a>사용자 환경

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a>사용자가 팀에서 모든 고정 된 앱을 볼 수 있는 방법

사용자에 대해 고정 된 모든 앱을 보려면 설치 된 앱 수와 팀 클라이언트 창의 크기에 따라 사용자가 다음을 수행 해야 할 수 있습니다.

|팀 데스크톱 클라이언트 |팀 모바일 클라이언트 |
|---------|---------|
|팀 측면의 앱 바에서을 클릭 **합니다. 앱이 더**있습니다.| 팀 아래쪽 근처에 있는 앱 바에서 위로 살짝 밉니다.|
|![팀 데스크톱 클라이언트의 더 많은 앱을 보여 주는 스크린샷](media/app-setup-policies-desktop-more-apps.png)<br>   |![팀 모바일 클라이언트의 더 많은 앱을 보여 주는 스크린샷](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a>팀 모바일 환경에 대해 알아야 할 사항

팀 모바일 클라이언트 (iOS 및 Android)는 현재 정적 탭이 있는 개인 앱을 지원 하지 않습니다. 정책에 설정 된 앱에 따라 팀 데스크톱 클라이언트에 고정 된 앱이 팀 모바일 클라이언트에 표시 되지 않을 수 있습니다. 개인 봇이 모바일 클라이언트의 채팅에 계속 표시 됩니다.

팀 모바일 클라이언트를 사용 하는 경우 사용자에 게 활동, 채팅, 팀 등의 핵심 팀 앱이 표시 되며, Microsoft에서 일부 자사 앱 (예: 이동)을 고정할 수 있습니다. 

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a>사용자가 정책을 통해 고정 된 앱의 순서를 변경할 수 있나요?

현재 사용자는 팀 모바일 클라이언트에서 고정 된 앱의 순서를 변경할 수 있지만 팀 바탕 화면 또는 웹 클라이언트에는 해당 되지 않습니다. 

### <a name="custom-teams-apps"></a>사용자 지정 팀 앱

#### <a name="my-organization-built-a-custom-teams-app-and-published-it-either-to-appsource-or-the-tenant-app-catalog-but-the-app-icon-isnt-displayed-as-expected-when-the-app-is-pinned-to-the-app-bar-in-teams-how-do-i-fix-it"></a>조직에서 사용자 지정 팀 앱을 작성 하 고 AppSource 또는 테 넌 트 앱 카탈로그에 게시 했지만 앱이 팀의 앱 표시줄에 고정 되어 있는 경우 앱 아이콘이 예상 대로 표시 되지 않습니다. 이 문제를 해결 하려면 어떻게 하나요? 

앱을 제출 하기 전에 로고 지침을 따르고 있는지 확인 합니다. 자세한 내용은 [판매자 대시보드 제출에 대 한 검사 목록](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview)을 참조 하세요. 

 ## <a name="related-topics"></a>관련 항목
- [Team에서 앱의 관리 설정](admin-settings.md)
- [팀 클라이언트에서 앱을 테 넌 트 앱 카탈로그에 게시](tenant-apps-catalog-teams.md)
