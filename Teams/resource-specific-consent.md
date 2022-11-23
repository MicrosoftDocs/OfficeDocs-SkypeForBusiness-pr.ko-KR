---
title: 마이크로소프트 Teams의 리소스별 동의
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
audience: admin
ms.service: msteams
ms.subservice: teams-apps
ms.date: 09/26/2022
search.appverid: MET150
description: 조직의 팀 소유자가 앱에 대한 동의를 제공할 수 있는지를 제어하기 위해 구성해야 하는 설정에 대해 알아봅니다.
ms.localizationpriority: high
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 374cda125d688c4e38797f1afbee4ae3a55bb064
ms.sourcegitcommit: d95a3408e31d3dec37c534c110b09a8847bec724
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2022
ms.locfileid: "69156824"
---
# <a name="resource-specific-consent-in-microsoft-teams"></a>마이크로소프트 Teams의 리소스별 동의

RSC(리소스별 동의)는 앱이 API 엔드포인트를 사용하여 조직 내 팀의 특정 리소스를 관리할 수 있도록 하는 Microsoft Teams 및 Microsoft Graph API 통합입니다. RSC 권한을 사용하면 팀 소유자가 애플리케이션에 대한 동의를 부여하여 팀의 데이터에 액세스하고 수정할 수 있습니다. 마이크로소프트 Teams의 리소스별 동의를 통해 팀 소유자는 팀 데이터에 액세스하는 앱에 대한 동의를 얻을 수 있습니다. 이러한 액세스의 예로는 채널 메시지 읽기, 채널 만들기 및 삭제, 채널 탭 만들기 및 제거 기능이 있습니다.

관리자는 조직의 팀 소유자가 Azure AD(Azure Active Directory) PowerShell 모듈 또는 Azure Portal 및 Microsoft Teams 관리 센터를 사용하여 구성한 설정을 통해 동의 여부를 제어합니다.  

## <a name="set-whether-team-owners-can-give-consent-to-apps"></a>팀 소유자가 앱에 동의할 수 있는지 설정

다음은 팀 소유자가 앱에 대해 동의할 수 있는지를 제어하기 위해 설정해야 하는 설정입니다. 다음 설정을 모두 검토해야 합니다.

### <a name="settings-in-azure-active-directory-portal"></a>Azure Active Directory 포털의 설정

다음 두 가지 설정에 따라 팀 소유자가 앱에 대해 동의할 수 있는지가 결정됩니다.

> [!IMPORTANT]
> 이러한 설정을 변경해도 이미 동의가 부여된 앱의 데이터 액세스에는 영향을 주지 않습니다. 예를 들어, 팀 소유자가 동의하지 못하도록 이러한 설정을 구성해도 이미 부여된 데이터 액세스 권한은 제거되지 않습니다.

#### <a name="the-users-can-consent-to-apps-accessing-company-data-on-their-behalf-setting"></a>사용자는 대신 회사 데이터에 액세스하는 앱 설정에 동의할 수 있습니다.

이 설정은 조직의 사용자가 대신 앱에 동의할 수 있는지를 제어합니다. 팀 소유자가 동의할 수 있도록 하려면, 이 설정을 **예** 로 설정해야 합니다. 이 설정을 관리하려면 다음을 수행합니다.

1. Azure Portal에서 **엔터프라이즈 응용 프로그램** > **사용자 설정** 으로 이동합니다.
2. **엔터프라이즈 응용 프로그램** 에서 **Users can consent to apps accessing company data on their behalf**(사용자는 회사 데이터에 액세스하는 앱에 대신 동의할 수 있음)를 **아니요** 또는 **예** 로 설정합니다.

PowerShell을 사용하여 이 설정을 관리할 수도 있습니다. 자세한 내용은 [Configure user content to applications](/azure/active-directory/manage-apps/configure-user-consent#configure-user-consent-to-applications)(응용 프로그램에 대한 사용자 콘텐츠 구성)를 참조하세요.

#### <a name="control-to-let-group-owners-consent-to-apps-that-access-company-data"></a>그룹 소유자가 회사 데이터에 액세스하는 앱에 동의하도록 제어

이 설정은 조직의 사용자가 자신이 소유한 그룹의 회사 데이터에 액세스하는 앱에 동의할 수 있는지를 제어합니다. 팀 소유자가 동의하려면 이 설정을 동의로 설정해야 합니다. PowerShell을 사용하여 이 설정을 관리하는 방법에 대한 단계는 [그룹 데이터에 액세스하는 앱에 대한 그룹 소유자 동의 구성](/azure/active-directory/manage-apps/configure-user-consent#configure-group-owner-consent-to-apps-accessing-group-data)을 참조하세요.

### <a name="settings-in-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터의 설정

Azure AD의 설정뿐만 아니라 [앱 관리](manage-apps.md) 페이지의 [조직 전체 앱 설정](manage-apps.md#manage-org-wide-app-settings), [앱 관리](manage-apps.md#allow-and-block-apps) 페이지의 앱 차단 또는 허용 여부 및 팀 소유자에게 할당된 [앱 권한 정책](teams-app-permission-policies.md)에 따라 팀 소유자가 동의 여부를 결정합니다.

> [!IMPORTANT]
> 이러한 설정을 변경해도 이미 동의가 부여된 앱의 데이터 액세스에는 영향을 주지 않습니다. 예를 들어 타사 앱을 조직 전체에서 사용하지 않도록 설정하거나 특정 앱을 차단하여 팀 소유자가 동의하지 못하도록 하는 경우 이러한 변경 사항으로 인해 이미 부여된 데이터 액세스가 제거되지는 않습니다.  

#### <a name="the-allow-third-party-apps-option-in-org-wide-app-settings"></a>조직 전체 앱 설정에서 타사 앱 허용 옵션

이 조직 전체 앱 설정은 조직의 사용자가 타사 앱을 사용할 수 있는지를 제어합니다. 팀 소유자가 동의할 수 있으려면 이 설정이 켜져 있어야 합니다. 이 설정을 관리하려면 다음을 수행합니다.

1. Teams 관리 센터에 로그인하고 **Teams 앱** > **[앱 관리](https://admin.teams.microsoft.com/policies/manage-apps)** 에 액세스합니다.
1. **조직 전체 앱 설정을** 선택하고 **타사 앱에서 타사 앱** **허용** 을 끄거나 켭니다.

   :::image type="content" source="media/resource-specific-consent-org-wide-setting.png" alt-text="Teams에서 타사 앱 허용 설정을 보여 주는 스크린샷":::

변경 내용을 적용하는 데 최대 24시간이 걸릴 수 있습니다.

#### <a name="allow-or-block-the-app-at-the-org-level"></a>조직 수준에서 앱 허용 또는 차단

[앱 관리](manage-apps.md#allow-and-block-apps) 페이지에서 앱을 차단하거나 허용하면 해당 앱이 조직의 모든 사용자에 대해 차단되거나 허용됩니다. 팀 소유자는 앱이 허용된 경우에만 앱에 동의 할 수 있습니다. 조직 수준에서 앱을 허용하거나 차단하려면 다음을 수행합니다.

1. Teams 관리 센터에 로그인하고 **Teams 앱** > **[앱 관리](https://admin.teams.microsoft.com/policies/manage-apps)** 에 액세스합니다.
1. 앱 관리 페이지에서 앱을 선택한 다음 **차단을 선택하여** 차단하거나 **허용** 을 선택하여 허용을 선택합니다.

#### <a name="app-permission-policy-assigned-to-the-team-owner"></a>팀 소유자에게 할당된 앱 권한 정책

팀 소유자는 자신의 앱 권한 정책이 실행을 허용하는 앱에만 동의할 수 있습니다. 팀 소유자에게 할당된 앱 사용 권한 정책을 보고 관리하려면 다음을 수행합니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색 창에서 **사용자** 로 이동합니다.
1. 팀 소유자의 표시 이름을 두 번 클릭한 다음 **정책을** 선택합니다.
1. 팀 소유자에게 할당된 정책은 **앱 권한 정책** 에 나열됩니다.

    * 다른 정책을 할당하려면 **편집** 을 선택한 다음 할당할 정책을 선택합니다.
    * 팀 소유자에게 할당된 정책의 설정을 편집하려면 정책 이름을 선택한 다음 원하는 대로 변경합니다.  

## <a name="upload-custom-apps"></a>사용자 지정 앱 업로드

리소스별 동의를 사용하는 사용자 지정 앱(측면 로드라고도 함)을 업로드할 때는 해당 앱이 설치되는 테넌트에서 제공되어야 합니다. 즉, Azure AD 앱 등록은 이 테넌트에서 온 것이야 합니다. 전역 관리자는 이 제한에서 제외되며, 모든 테넌트에서 직접 팀(측면 로드) 또는 테넌트 앱 카탈로그에 사용자 지정 앱을 업로드할 수 있습니다.

## <a name="related-articles"></a>관련 기사

* [Microsoft Graph에서 Teams의 데이터를 활용하는 RSC 권한](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)
* [Microsoft Graph](https://developer.microsoft.com/graph)
* [Microsoft Teams 관리 센터에서 앱 관리](manage-apps.md)
* [Teams에서 앱 사용 권한 정책 관리](teams-app-permission-policies.md)
