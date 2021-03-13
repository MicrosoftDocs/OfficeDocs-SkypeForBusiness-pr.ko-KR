---
title: Microsoft Teams에서 앱 설정 정책 관리
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: rarang
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
description: 조직의 사용자를 위해 Microsoft Teams에서 앱 설치 정책을 사용 및 관리하는 방법에 대해 자세히 알아보고 있습니다.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: 94e33421043b0cad195489d78e2eb96c95bb222e
ms.sourcegitcommit: da2a70a9b5e05d0fd7ecc150b451f5805667514c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2021
ms.locfileid: "50756184"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a>Microsoft Teams에서 앱 설정 정책 관리

관리자는 앱 설정 정책을 사용하여 다음 작업을 수행할 수 있습니다.

- 팀을 사용자 지정하여 사용자에게 가장 중요한 앱을 강조 표시합니다. 앱을 선택하고 표시하는 순서를 고정하고 설정할 수 있습니다. 앱을 고정하면 타사 또는 조직의 개발자가 구축한 앱을 포함하여 조직의 사용자가 필요로 하는 앱을 선보일 수 있습니다.
- 사용자가 앱을 Teams에 고정할 수 있는지 여부를 제어합니다.
- 사용자를 대신하여 앱을 설치합니다. Teams를 시작할 때 기본적으로 사용자에게 설치되는 앱을 선택할 수 있습니다. 사용자에게 할당된 앱 사용 권한 정책이 허용하는 경우 사용자가 앱을 직접 설치할 수 있습니다. [](teams-app-permission-policies.md)

> [!Note]
> 관리자가 설치한 앱의 경우 사용자는 해당 앱을 제거할 수 없습니다.

앱이 앱 표시줄에 고정됩니다. 이 막대는 Teams 데스크톱 클라이언트의 측면과 Teams 모바일 클라이언트(iOS 및 Android)의 아래쪽에 있는 막대입니다.

|Teams 데스크톱 클라이언트  |Teams 모바일 클라이언트 |
|---------|---------|
|![Teams 데스크톱 클라이언트](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![Teams 모바일 클라이언트](media/mobile-app-ui.png)      |

관리자가 설치한 앱을 표시하려면 앱 표시줄에서 ...를 **선택합니다.** Teams 데스크톱 및 웹 클라이언트의 더 많은 앱과 모바일 클라이언트에서 스 와이프합니다.

Microsoft Teams 관리 센터에서 앱 설정 정책을 관리합니다. 전역(Org-wide 기본값) 정책을 사용하거나 사용자 지정 정책을 만들고 할당합니다.  사용자 지정 정책을 만들고 할당하지 않으면 조직의 사용자에게 전역 정책이 자동으로 적용됩니다. 이러한 정책을 관리하려면 전역 관리자 또는 Teams 서비스 관리자여야 합니다.

전역 정책의 설정을 편집하여 원하는 앱을 포함합니다. 조직의 다른 사용자 그룹에 대해 Teams를 사용자 지정하기 위해 하나 이상의 사용자 지정 정책을 만들고 할당합니다.

![앱 설정 정책 페이지](media/app-setup-policies.png)

> [!NOTE]
> 교육용 Teams가 있는 경우 할당 앱이 현재 글로벌 정책에 기본적으로 고정되어 있는 경우 전역 정책에 나열되지 않습니다. Teams 클라이언트의 고정된 앱 목록에 있는 네 번째 앱입니다.

## <a name="create-a-custom-app-setup-policy"></a>사용자 지정 앱 설정 정책 만들기

Microsoft Teams 관리 센터를 사용하여 사용자 지정 정책을 만들 수 있습니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색에서 **Teams 앱** 설치 정책  >  **으로 이동하세요.**

2. **추가** 를 선택합니다.

   ![앱 설정 정책 추가 페이지](media/app-setup-policies-add.png)

3. 정책의 이름과 설명을 입력합니다.

4. 사용자가 Teams에 사용자 지정 앱을 업로드할지 여부에 따라 사용자 지정 앱 업로드를 설정하거나 해제합니다. 타사 앱 허용이 [org-wide](manage-apps.md#manage-org-wide-app-settings)앱 설정에서 해제된 경우 이 설정을 변경할 수 없습니다. 

5. 앱에 앱을 고정하여 사용자가 앱 표시줄을 개인 설정하도록 할지 여부에 따라 사용자 고정 허용을 설정하거나 끄습니다.

   > [!NOTE]
   > 사용자 **고정** 허용 설정은 Microsoft 365 GCC(정부 커뮤니티 클라우드) 환경(GCC, GCC High 및 DoD)의 Teams 관리 센터에서 사용할 수 있지만 현재는 효과가 없습니다.

6. 사용자를 위한 앱을 설치하려면 다음 작업을 수행합니다.

    1. 설치된 **앱에서** 앱 **추가를 선택합니다.**

    2. 설치된 **앱** 추가 창에서 Teams를 시작할 때 자동으로 설치하려는 앱을 검색합니다. 앱 사용 권한 정책에 따라 앱을 필터링할 수 있습니다. 앱 목록을 선택한 경우 추가를 **선택합니다.**

       ![설치된 앱 추가 창](media/app-setup-policies-add-installed-apps.png)

7. 앱을 고정하기 위해 다음 단계를 수행합니다.

    1. 고정된 **앱 아래에서** 앱 **추가를 선택합니다.**

    2. 고정된  앱 추가 창에서 추가할 앱을 검색한 다음 추가를 **선택합니다.** 앱 사용 권한 정책에 따라 앱을 필터링할 수 있습니다. 고정할 앱 목록을 선택한 경우 추가를 **선택합니다.**

       ![고정된 앱 추가 창](media/app-setup-policies-add-apps.png)

    3. 앱을 Teams에 표시하려는 순서대로 정렬한 다음 저장을 **선택합니다.**

       ![고정된 앱 섹션](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a>앱 설정 정책 편집

Microsoft Teams 관리 센터를 사용하여 만든 전역(Org-wide default) 정책 및 사용자 지정 정책을 포함하여 정책을 편집할 수 있습니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색에서 **Teams 앱** 설치 정책  >  **으로 이동하세요.**

2. 정책 이름의 왼쪽을 클릭하여 정책을 선택한 다음 **편집을 선택합니다.**

3. 여기서 원하는 내용을 변경합니다.

4. 저장을 **선택합니다.**

## <a name="assign-a-custom-app-setup-policy-to-users"></a>사용자에게 사용자 지정 앱 설정 정책 할당

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="faq"></a>FAQ

### <a name="working-with-app-setup-policies"></a>앱 설정 정책 작업

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터에 포함된 기본 제공 앱 설정 정책

- **전역(조직** 전체 기본값) : 이 기본 정책은 다른 정책을 할당하지 않는 한 조직의 모든 사용자에게 적용됩니다. 전역 정책을 편집하여 사용자에게 가장 중요한 앱을 고정합니다.

- **FrontlineWorker**: 이 정책은 Frontline Workers에 대한 것입니다. 조직의 Frontline Workers에 할당할 수 있습니다. 만드는 사용자 지정 정책과 마찬가지로 설정이 활성화될 수 있도록 사용자에게 정책을 할당해야 합니다. 자세한 내용은 이 문서의 사용자에게 사용자 지정 앱 설정 정책 할당 섹션으로 이동하세요. [](#assign-a-custom-app-setup-policy-to-users)

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>고정된 앱 추가 창에서 앱을 찾을 수 없는 이유

앱 설정 정책을 통해 모든 앱을 Teams에 고정할 수 있는 것은 없습니다. 일부 앱은 이 기능을 지원하지 않을 수 있습니다. 고정할 수 있는 앱을 찾으면 고정된 앱 추가 창에서 앱을 **검색합니다.** 개인 범위(고정 탭)와 봇이 있는 탭은 Teams 데스크톱 클라이언트에 고정할 수 있으며 이러한 앱은 고정된 앱 추가 창에서 **사용할 수** 있습니다.

Teams 앱 스토어에는 모든 Teams 앱이 나열됩니다. 고정된 **앱** 추가 창에는 정책을 통해 Teams에 고정할 수 있는 앱만 포함됩니다.

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a>저는 교육용 Teams 관리자입니다. Teams for Education의 앱 설정 정책에 대해 알아야 할 일

전화 걸기 앱은 교육용 Teams에서 사용할 수 없습니다. 새 사용자 지정 앱 설정 정책을 만들 때 호출 앱이 앱 목록에 표시됩니다. 그러나 앱이 Teams 클라이언트에 고정되지 않습니다. 교육용 Teams 사용자는 Teams에서 호출 앱이 표시되지 않습니다.

#### <a name="how-many-pinned-apps-can-be-added-to-a-policy"></a>정책에 추가할 수 있는 고정된 앱 수

Teams 모바일 클라이언트(iOS 및 Android)에 최소 2개의 앱을 고정해야 합니다. 정책에 앱이 두 개 미만인 경우 모바일 클라이언트는 정책 설정을 반영하지 않고 기존 구성을 계속 사용합니다.

정책에 추가할 수 있는 고정된 앱 수에는 제한이 없습니다.

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a>정책 변경이 적용하는 데 얼마나 오래 걸릴 수 있습니다.

정책을 편집하거나 할당한 후 변경 내용을 적용하는 데 몇 시간이 걸릴 수 있습니다.

### <a name="user-experience"></a>사용자 환경

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a>사용자가 Teams에서 고정된 모든 앱을 볼 수 있는 방법

사용자에 대해 고정된 모든 앱을 표시하기 위해 사용자는 설치된 앱 수와 Teams 클라이언트 창의 크기에 따라 다음을 해야 할 수 있습니다.

|Teams 데스크톱 클라이언트 |Teams 모바일 클라이언트 |
|---------|---------|
|Teams 쪽의 앱 표시줄에서 ...를 **선택합니다. 더 많은 앱**.| Teams의 아래쪽에 있는 앱 표시줄에서 위쪽으로 으로 아|
|![Teams 데스크톱 클라이언트의 더 많은 앱](media/app-setup-policies-desktop-more-apps.png)<br>   |![Teams 모바일 클라이언트에서 더 많은 앱](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a>Teams 모바일 경험에 대해 알아야 할 일

현재 Teams 모바일 클라이언트(iOS 및 Android)는 정적 탭이 있는 개인 앱을 지원하지 않습니다. 정책에 설정된 앱에 따라 Teams 데스크톱 클라이언트에 고정된 앱이 Teams 모바일 클라이언트에 나타나지 않을 수 있습니다. 모바일 클라이언트의 채팅에 개인 봇이 계속 표시됩니다.

Teams 모바일 클라이언트를 사용하면 사용자는 활동, 채팅, Teams와 같은 핵심 Teams 앱을 볼 수 있으며 Shifts와 같은 Microsoft의 일부 파티 앱을 고정할 수 있습니다.

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a>사용자가 정책을 통해 고정된 앱의 순서를 변경할 수 있습니다.

사용자 고정 허용 옵션이 켜져 있는 경우 Teams 데스크톱  및 모바일 클라이언트에서 고정된 앱의 순서를 변경할 수 있습니다. 사용자는 Teams 웹 클라이언트에서 고정된 앱의 순서를 변경할 수 없습니다.

#### <a name="does-user-pinning-take-precedence"></a>사용자 고정이 우선 순위를 적용하는가

사용자에게 할당된 앱 설정 정책이 사용자 앱 고정을 차단하도록 변경된 경우 Teams는 앱 표시줄에 고정된 모든 앱을 제거합니다. 그런 다음 사용자 앱 고정을 허용하도록 정책이 변경된 경우 사용자가 이전에 고정한 앱을 다시 입력해야 합니다.

### <a name="custom-teams-apps"></a>사용자 지정 Teams 앱

내 조직은 사용자 지정 Teams 앱을 만들어 AppSource 또는 테넌트 앱 카탈로그에 게시했지만 앱이 Teams의 앱 표시줄에 고정될 때 앱 아이콘이 예상대로 표시되지 않습니다. 해결 방법

앱을 제출하기 전에 로고 지침을 준수해야 합니다. 자세한 내용은 판매자 대시보드 제출 [확인 목록을 참조하세요.](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview)

## <a name="related-topics"></a>관련 항목

[Teams의 앱에 대한 관리 설정](admin-settings.md)

[Teams에서 사용자에게 정책 할당](assign-policies.md)
