---
title: Microsoft Teams에서 앱 설정 정책 관리
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.subservice: teams-apps
ms.service: msteams
audience: Admin
ms.date: 09/26/2022
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 앱을 고정하고, 앱을 설치하고, 사용자가 사용자 지정 앱을 업로드할 수 있도록 앱 설정 정책을 만들고, 편집하고, 관리하는 방법에 대해 알아봅니다.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: b9dfe2ad2598e47175a0af433c0febac17255c09
ms.sourcegitcommit: 22f66e314e631b3c9262c5c7dc5664472f42971e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2022
ms.locfileid: "68912467"
---
# <a name="use-app-setup-policies-to-pin-and-auto-install-apps-in-teams"></a>앱 설정 정책을 사용하여 Teams에서 앱 고정 및 자동 설치

관리자는 앱 설정 정책을 사용하여 앱을 설치 및 고정하고 사용자 지정 앱을 업로드할 수 있는 특정 사용자를 제어합니다. 고정은 조직의 관련 앱에 대한 빠른 액세스를 촉진하고 채택을 촉진하는 데 도움이 됩니다.

* **[앱 고정](#pin-apps):** 앱 설정 정책을 사용하면 고정할 앱을 선택하고 Teams 앱 모음 또는 메시지 작성 영역에서 앱이 사용자에게 표시되는 순서를 설정할 수 있습니다. 관리자는 또한 최종 사용자가 자신의 앱을 고정할 수 있는지를 제어할 수 있습니다.

* **[앱 설치](#install-apps):** 앱 설정 정책을 사용하면 Teams를 시작할 때와 모임 중에 사용자를 대신하여 허용된 앱을 설치할 수 있습니다.

* **사용자 지정 앱 업로드:** 앱 설정 정책을 사용하면 Teams에 사용자 지정 앱을 업로드할 수 있는 사용자를 제어할 수 있습니다. [사용자 지정 앱 업로드](teams-custom-app-policies-and-settings.md) 문서를 참조하세요.

Microsoft Teams 관리 센터에서 기본적으로 다음과 같은 기본 제공 앱 설정 정책을 사용할 수 있습니다.

* **글로벌(조직 전체 기본값)**: 이 기본 정책은 다른 정책을 할당하지 않는 한 조직의 모든 사용자에게 적용됩니다. 사용자에게 가장 중요한 앱을 고정하도록 글로벌 정책을 편집합니다.

* **최전방 인력**: 이 정책은 최전방 인력용입니다. 정책을 사용자 지정할 수 없습니다. 조직의 최전방 인력에 할당할 수 있습니다.

## <a name="pin-apps"></a>앱 고정

앱을 고정하면 Teams 클라이언트의 앱 표시줄에 앱이 표시됩니다. 관리자는 앱을 고정할 수 있으며 사용자가 고정하도록 허용할 수 있습니다. 고정은 사용자가 가장 많이 필요로 하는 앱을 강조 표시하고 접근성을 높이는 데 사용됩니다. 고정은 [Teams의 모든 유형의 앱(핵심 앱](deploy-apps-microsoft-teams-landing-page.md) , Microsoft 제공 앱, 타사 앱 및 조직 내에서 개발된 사용자 지정 앱)에서 작동합니다.

관리자는 앱 설정 정책을 통해 앱을 고정할 수 있습니다. 관리자가 고정한 앱은 앱이 허용되는 사용자를 위해 자동으로 설치됩니다. 이러한 앱은 최종 사용자가 제거할 수 없습니다. 앱 설정 정책을 사용하여 다음 작업을 수행할 수 있습니다.

* 최종 사용자를 위해 Teams를 사용자 지정하여 가장 중요한 앱을 강조 표시합니다. 고정할 앱과 앱이 표시되는 순서를 선택합니다.
* 사용자가 앱을 고정할 수 있는지를 제어합니다.

앱은 Teams 데스크톱 클라이언트의 왼쪽과 Teams 모바일 클라이언트의 하단에 있는 앱 바에 고정되어 있습니다. 메시징 확장은 메시지 작성 영역의 맨 아래에 있습니다.

|Teams 데스크톱 클라이언트  |Teams 모바일 클라이언트 |
|---------|---------|
|![Teams 데스크톱 클라이언트의 앱 바를 보여 주는 스크린샷](media/app-setup-policies-desktop-app-bar.png).  |   ![Teams 모바일 클라이언트의 앱 바를 보여 주는 스크린샷](media/mobile-app-ui.png)      |

앱 설정 정책을 사용하여 앱을 고정하려면 다음 단계를 수행합니다.

1. Teams 관리 센터에 로그인하고 **Teams 앱** > **[정책 설정](https://admin.teams.microsoft.com/policies/app-setup)** 에 액세스합니다.

1. **추가** 를 선택합니다.

1. 정책의 이름과 설명을 입력합니다.

1. 필요에 따라 **사용자가 앱을 고정하고 고정** 된 앱의 순서를 변경할 수 있도록 사용자 고정을 켭니다.

1. **고정된 앱** 에서 **앱 추가** 를 선택합니다.

1. **고정된 앱 추가** 창에서 추가할 앱을 검색한 다음 **추가** 를 선택합니다.

    :::image type="content" source="media/add-pinned-apps-trimmed.png" alt-text="스크린샷은 앱 설정 정책에 고정된 앱을 추가하는 방법을 보여줍니다." lightbox="media/add-pinned-apps-large.png":::

1. **추가** 를 선택합니다.

1. **앱 바** 또는 **메시징 확장** 아래에서 Teams 클라이언트에 앱을 표시할 순서대로 앱을 정렬합니다.

   :::image type="content" source="media/pin-messaging-extensions.png" alt-text="설치 정책에서 고정된 앱 및 고정된 메시징 확장의 스크린샷":::

1. **저장** 을 선택합니다.

> [!NOTE]
> 교육용 Teams에서 과제 앱은 글로벌 정책에 나열되지 않더라도 기본적으로 글로벌 정책에 고정됩니다.

> [!NOTE]
> 조직의 최전방 인력에게는 맞춤형 일선 앱 환경을 사용하는 것이 좋습니다. 이 기능은 [F 라이선스](https://www.microsoft.com/en-us/microsoft-365/enterprise/frontline)를 보유한 사용자를 위해 Teams에서 가장 관련성이 높은 앱을 고정합니다. 자세한 내용은 [최전방 직원을 위한 맞춤형 Teams 앱](/microsoft-365/frontline/pin-teams-apps-based-on-license?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json)을 참조하세요.

## <a name="install-apps"></a>앱 설치

관리자는 앱 설정 정책을 사용하여 다음 작업을 수행할 수 있습니다.

* 개인 Teams 환경에 최종 사용자를 위한 앱을 설치합니다.
* 최종 사용자를 위한 앱을 [메시징 확장](/microsoftteams/platform/messaging-extensions/what-are-messaging-extensions)으로 설치합니다.

최종 사용자는 [앱 사용 권한 정책을 통해 앱을](teams-app-permission-policies.md) 설치할 수 있고 Teams 관리자가 앱을 허용하는 경우 앱을 직접 설치할 수 있습니다. 앱이 차단되면 최종 사용자가 [관리자 승인을 요청할](user-requests-approve-apps.md) 수 있습니다.

앱 설정 정책을 사용하여 앱을 설치하려면 다음 단계를 수행합니다.

1. Teams 관리 센터에 로그인하고 **Teams 앱** > **[정책 설정](https://admin.teams.microsoft.com/policies/app-setup)** 에 액세스합니다.

1. **추가** 를 선택합니다.

1. 정책의 이름과 설명을 제공합니다.

1. **설치된 앱** 에서 **앱 추가** 를 선택합니다.

1. **설치된 앱 추가** 창에서 사용자를 위해 설치할 앱을 검색합니다. 앱 권한 정책으로 앱을 필터링할 수도 있습니다.

1. **추가** 를 선택합니다.

:::image type="content" source="media/install-apps-in-meeting.png" alt-text="앱 정책을 통해 앱을 설치하는 스크린샷":::

## <a name="manage-app-setup-policies"></a>앱 설정 정책 관리

Microsoft Teams 관리 센터에서 앱 설정 정책을 관리합니다. 글로벌(조직 전체 기본값) 정책을 사용하거나 사용자 지정 정책을 만들어 할당합니다. 최종 사용자는 글로벌 정책을 받습니다. 사용자 지정 정책을 생성하면 글로벌 정책이 재정의됩니다. 전역 관리자 또는 Teams 서비스 관리자가 이러한 정책을 관리할 수 있습니다.

글로벌 정책의 설정을 편집하여 원하는 앱을 포함할 수 있습니다. 조직의 여러 사용자 그룹에 대해 Teams를 사용자 지정하려면 하나 이상의 사용자 지정 정책을 만들고 할당합니다.

:::image type="content" source="media/app-setup-policies-update.png" alt-text="정책을 관리하거나 새 정책을 추가하는 옵션이 있는 앱 설정 정책 페이지를 보여 주는 스크린샷":::

### <a name="edit-an-app-setup-policy"></a>앱 설정 정책 편집

Microsoft Teams 관리 센터를 사용하여 글로벌(조직 전체 기본값) 정책 및 사용자가 만든 사용자 지정 정책을 포함하여 정책을 편집할 수 있습니다. 정책을 편집하거나 할당한 후 변경 내용을 적용하는 데 몇 시간이 걸릴 수 있습니다.

1. Teams 관리 센터에 로그인하고 **Teams 앱** > **[정책 설정](https://admin.teams.microsoft.com/policies/app-setup)** 에 액세스합니다.

1. 편집할 정책을 선택한 다음 **편집** 을 선택합니다.

1. 원하는 대로 변경합니다.

1. **저장** 을 선택합니다.

### <a name="assign-a-custom-policy-in-app-setup-policy-to-users-and-groups"></a>사용자 및 그룹에 앱 설정 정책의 사용자 지정 정책 할당

최종 사용자 및 그룹에 정책을 할당하는 방법을 알아보려면 [사용자 및 그룹에 정책을 할당하는 방법](assign-policies-users-and-groups.md)을 참조하세요.

## <a name="considerations-and-limitations"></a>고려 사항 및 제한 사항

* 앱 설정 정책을 사용하여 구성 가능한 탭으로 사용자 지정 앱을 설치할 수 없습니다.

* 최종 사용자는 관리자가 설치한 앱을 제거할 수 없습니다.

* 최종 사용자는 정책에서 사용자 고정이 허용되는 경우 앱 설정 정책을 통해 고정되는 앱을 고정 해제할 수 있습니다.

* 사용자는 사용자 고정 옵션이 켜져 있는 경우 Teams 데스크톱 및 모바일 클라이언트에서 고정된 앱의 순서를 변경할 수 있습니다. 사용자는 Teams 웹 클라이언트에서 고정된 앱의 순서를 변경할 수 없습니다.

* 관리자 핀이 항상 우선적으로 적용됩니다. 사용자 고정 옵션이 켜져 있으면 사용자가 고정한 앱이 관리자가 고정한 앱 아래에 표시됩니다. 사용자 고정 옵션이 꺼져 있으면 사용자가 기존 핀을 잃고 관리자가 고정한 앱만 앱 바에서 사용할 수 있습니다.

* 사용자 고정 설정은 Microsoft 365 GCC(Government Community Cloud) 환경(GCC, GCC High 및 DoD)의 Teams 관리 센터에서 사용할 수 있지만 아무런 효과가 없습니다.

* 교육용 Teams에서 과제 앱은 글로벌 정책에 나열되지 않더라도 기본적으로 글로벌 정책에 고정됩니다.

* 정책에 추가할 수 있는 최대 고정 앱 수에는 제한이 없습니다. 그러나 적어도 두 개의 앱이 Teams 모바일 클라이언트(iOS 및 Android)에 고정되어 있어야 합니다. 정책에 앱이 두 개 미만인 경우 모바일 클라이언트는 정책 설정을 반영하지 않고 기존 구성을 계속 사용합니다.

* 정책을 편집하거나 할당한 후 변경 내용을 적용하는 데 몇 시간이 걸릴 수 있습니다.

* 앱 설정 정책을 통해 모든 앱을 Teams에 고정할 수 있는 것은 아닙니다. 일부 앱은 이 기능을 지원하지 않을 수 있습니다. 고정할 수 있는 앱을 찾으려면 **고정된 앱 추가** 창에서 앱을 검색합니다. 개인 범위(정적 탭)와 봇이 있는 탭은 Teams 데스크톱 클라이언트에 고정할 수 있으며, 이러한 앱은 **고정된 앱 추가** 창에서 사용할 수 있습니다. Teams 앱 스토어에는 모든 Teams 앱이 나열됩니다. **고정된 앱 추가** 창에는 정책을 통해 Teams에 고정될 수 있는 앱만 포함됩니다.

* 교육용 Teams 통화 앱을 사용할 수 없습니다. 앱 설정 정책에서 새 사용자 지정 정책을 만들면 앱 목록에 통화 앱이 표시됩니다. 그러나 이 앱은 Teams 클라이언트에 고정되어 있지 않으며 교육용 Teams 사용자는 Teams에서 통화 앱을 볼 수 없습니다.

## <a name="related-articles"></a>관련 기사

* [Teams의 앱에 대한 관리 설정](admin-settings.md)
* [Teams에서 최종 사용자에게 정책 할당](assign-policies-users-and-groups.md)
