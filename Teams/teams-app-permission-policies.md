---
title: Microsoft Teams에서 앱 사용 권한 정책 관리
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-apps
audience: Admin
ms.date: 09/29/2022
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: high
search.appverid: MET150
description: Microsoft Teams의 앱 사용 권한 정책과 최종 사용자의 앱 가용성을 제어하는 방법에 대해 알아봅니다.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.overview
- ms.teamsadmincenter.appsetuppolicies.addpinnedapp.permissions
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: 24c4b85bb1c4b97597bad6a38e6a67c35dc1abb0
ms.sourcegitcommit: 6e85f3f70f8488ab827ac352c0f324b6dfd4b856
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/04/2022
ms.locfileid: "68377046"
---
# <a name="manage-access-to-teams-apps-using-app-permission-policies"></a>앱 권한 정책을 사용하여 Teams 앱에 대한 액세스 관리

관리자는 앱 권한 정책을 사용하여 조직의 각 사용자가 사용할 수 있는 앱을 제어할 수 있습니다. 모든 앱 또는 특정 앱을 허용하거나 차단하도록 설정한 권한은 [Teams의 모든 앱 유형에](deploy-apps-microsoft-teams-landing-page.md) 적용됩니다. 이러한 정책을 관리하려면 전역 관리 또는 Teams 서비스 관리자여야 합니다.

앱을 허용하려면 [조직 전체 앱 설정](manage-apps.md#manage-org-wide-app-settings), 개별 앱 설정 및 앱 권한 정책에서 [앱을](manage-apps.md#allow-and-block-apps) 허용해야 합니다. 다른 두 가지 방법은 조직에서 앱을 사용할 수 있도록 허용하지만 사용 권한 정책을 사용하면 특정 앱을 사용할 수 있는 사용자를 제어할 수 있습니다. 특정 사용자에게 정책을 만들고 적용하여 사용자별 및 앱별로 액세스를 제어할 수 있습니다.

Teams 관리 센터를 사용하면 다음 두 가지 유형의 사용 권한 정책을 만들 수 있습니다.

* `Global (Org-wide default)` 정책은 기본적으로 존재하며 모든 사용자에게 적용됩니다. 이 정책을 변경하면 기본적으로 모든 사용자에게 이 정책이 적용되므로 모든 사용자에게 영향을  미칩니다.
* 관리자가 만든 정책은 적용되는 사용자에게만 적용됩니다. 특정 사용자 또는 사용자 그룹에 대한 앱을 허용하는 새 정책을 만듭니다.

   :::image type="content" source="media/app-permission-policy-trimmed.png" alt-text="만들어지는 새 앱 권한 정책을 보여 주는 스크린샷" lightbox="media/app-permission-policy.png":::

조직이 이미 Teams에 있는 경우 Microsoft 365 관리 센터 **테넌트 전체 설정** 에서 구성한 앱 설정이 Teams 관리 센터의 [앱 관리](https://admin.teams.microsoft.com/policies/manage-apps) 페이지의 조직 전체 앱 설정에 반영됩니다. Teams를 익숙하지 않은 경우 기본적으로 모든 앱이 조직 전체 전역 설정에서 허용됩니다. 여기에는 Microsoft, 타사 소프트웨어 공급자 및 자신의 조직에서 게시한 앱이 포함됩니다.

> [!NOTE]
> Microsoft 365 Government Community Cloud High(GCCH) 및 국방부(DoD) 환경의 타사 앱 설정에 대해 알아보려면 [Microsoft 365 Government에 대한 조직 전체 앱 설정 관리를](manage-apps.md#manage-org-wide-app-settings-for-microsoft-365-government) 참조하세요.

## <a name="create-an-app-permission-policy"></a>앱 사용 권한 정책 만들기

서로 다른 사용자 그룹에 사용할 수 있는 앱을 제어하려면 하나 이상의 사용자 지정 앱 사용 권한 정책을 이용합니다. 앱이 Microsoft, 타사 또는 조직에 의해 게시되는지 여부에 따라 별도의 사용자 지정 정책을 만들고 할당할 수 있습니다. 사용자 지정 정책을 만든 후에는 조직 전체 앱 설정에서 타사 앱을 사용하지 않도록 설정한 경우 이를 변경할 수 없습니다.

1. Teams 관리 센터에 로그인하고 **Teams 앱** > **[사용 권한 정책에 액세스합니다](https://admin.teams.microsoft.com/policies/app-permission)**.
1. **추가** 를 선택합니다.
1. 정책의 이름과 설명을 제공합니다.
1. **Microsoft 앱**, **타사 앱** 및 **사용자 지정 앱** 에서 다음 옵션 중 하나를 선택합니다.

    * `Allow all apps`
    * `Allow specific apps and block all others`
    * `Block specific apps and allow all others`
    * `Block all apps`

1. **특정 앱 허용 및 다른 모든 앱 차단** 을 선택한 경우 허용하려는 앱을 추가합니다.

    1. **앱 허용** 을 선택합니다.
    1. 허용할 앱을 검색한 다음 **추가** 를 선택합니다. 검색 결과는 앱 개발자(**Microsoft 앱**, **타사 앱** 또는 **사용자 지정 앱**)로 필터링됩니다.
    1. 하나 이상의 앱을 선택한 후 **[허용**]을 선택합니다.

1. **특정 앱 차단을 선택하고 다른 모든 앱을 허용** 한 경우 차단하려는 앱을 검색하여 선택한 다음 **차단** 을 선택합니다.

1. **저장** 을 선택합니다.

## <a name="edit-an-app-permission-policy"></a>앱 사용 권한 정책 편집

Teams 관리 센터를 사용하여 전역 정책 또는 만든 사용자 지정 정책을 편집할 수 있습니다.

1. Teams 관리 센터에 로그인하고 **Teams 앱** > **[사용 권한 정책에 액세스합니다](https://admin.teams.microsoft.com/policies/app-permission)**.
1. 정책 이름 왼쪽을 클릭하여 정책을 선택한 다음 **편집** 을 선택합니다.
1. 세 가지 범주 각각에서 특정 앱을 허용하거나 차단하도록 변경합니다.
1. **저장** 을 선택합니다.

## <a name="assign-a-custom-app-permission-policy-to-users"></a>사용자에게 사용자 지정 앱 사용 권한 정책 할당

앱 권한 정책은 사용자 또는 사용자 그룹에 정책을 적용하는 경우에만 적용됩니다. [사용자에게 정책을 할당](policy-assignment-overview.md#ways-to-assign-policies)하는 다양한 방법을 참조하세요.

## <a name="considerations-when-using-app-permission-policies"></a>앱 권한 정책을 사용할 때 고려 사항

다음은 앱 권한 정책을 사용하여 액세스 권한을 부여하거나 앱에 대한 액세스를 허용하지 않는 경우 몇 가지 고려 사항입니다.

* 앱 권한 정책은 사용자 또는 사용자 그룹에 정책을 적용하는 경우에만 적용됩니다.

* 정책을 편집하거나 할당한 후 변경 내용을 적용하는 데 몇 시간이 걸릴 수 있습니다.

* 최종 사용자는 사용자가 사용할 수 없는 앱의 기능과 상호 작용할 수 없습니다.

* 사용자는 차단된 앱을 검색하고 관리자 승인을 요청할 수 있습니다. 관리자는 [사용자 요청을 승인하거나 무시할](user-requests-approve-apps.md) 수 있는 완전한 제어권을 유지합니다.

* 앱 설정 정책은 앱 권한 정책과 함께 작동합니다. 허용되는 앱 집합에서 설치 정책에 고정할 앱을 선택합니다. 그러나 사용자에게 고정된 앱의 사용을 차단하는 앱 사용 권한 정책이 있는 경우 사용자는 앱을 사용할 수 없습니다.

* 앱 정책은 웹, 모바일 또는 데스크톱에서 Teams를 사용하는 사용자에게 적용됩니다.

## <a name="related-articles"></a>관련 기사

* [Teams의 앱에 대한 관리 설정](admin-settings.md)
* [Teams에서 사용자에게 정책 할당](policy-assignment-overview.md)
* [Teams 기능 가용성 비교](/office365/servicedescriptions/teams-service-description#feature-availability)
