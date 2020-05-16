---
title: Microsoft 팀의 자원 관련 승인
author: LanaChin
ms.author: v-lanac
ms.reviewer: nkramer
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 조직의 팀 소유자가 앱에 동의 하도록 할 수 있는지 여부를 제어 하기 위해 구성 해야 하는 설정에 대해 알아봅니다.
localization_priority: Normal
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 54a0565f5126c899ed5fbf9527aa30f83c3bee3b
ms.sourcegitcommit: 296aeac481f901eb9d52b4f12a8c037afc49fa77
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2020
ms.locfileid: "44256600"
---
# <a name="resource-specific-consent-in-microsoft-teams"></a>Microsoft 팀의 자원 관련 승인

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Microsoft 팀의 자원 관련 동의를 통해 팀 소유자는 팀 데이터에 액세스 하는 앱에 동의 합니다. 이러한 액세스의 예로는 채널 메시지를 읽고, 채널을 만들고, 삭제 하 고, 채널 탭을 만들고 제거할 수 있습니다.

관리자는 조직의 팀 소유자가 azure AD (azure Active Directory) PowerShell 모듈 또는 Azure 포털 및 Microsoft 팀 관리 센터를 사용 하 여 구성 하는 설정을 통해 승인을 제공할 수 있는지 여부를 제어 합니다.  

## <a name="set-whether-team-owners-can-give-consent-to-apps"></a>팀 소유자가 앱에 동의 하도록 지정할 수 있는지 여부 설정

팀 소유자가 앱에 동의 하도록 할 수 있는지 여부를 제어 하기 위해 설정 해야 하는 설정은 다음과 같습니다. 다음 설정을 모두 검토 하세요.

### <a name="settings-in-azure-ad"></a>Azure AD의 설정

다음 두 설정은 팀 소유자가 앱에 동의 하는지 여부를 결정 합니다.

> [!IMPORTANT]
> 이러한 설정을 변경 해도 이미 동의 하는 앱에 대 한 데이터 액세스는 영향을 받지 않습니다. 예를 들어 팀 소유자가 동의 하지 않도록 이러한 설정을 구성 하는 경우에는 이미 부여 된 데이터 액세스는 제거 되지 않습니다.

#### <a name="the-users-can-consent-to-apps-accessing-company-data-on-their-behalf-setting"></a>"사용자를 대신 하 여 회사 데이터에 액세스 하는 앱에 동의할 수 있음" 설정

이 설정은 조직의 사용자가 앱에 동의할 수 있는지 여부를 제어 합니다. 팀 소유자가 동의를 제공할 수 있도록 하려면이 설정을 **Yes**로 설정 해야 합니다. 이 설정을 관리 하려면 다음을 수행 합니다.

1. Azure 포털에서 **엔터프라이즈 응용 프로그램**  >  **사용자 설정**으로 이동 합니다.
2. **엔터프라이즈 응용 프로그램**에서 사용자를 대신 **하 여** **회사 데이터에 액세스 하는 앱에 동의** 하는 것을 **설정 합니다.**

PowerShell을 사용 하 여이 설정을 관리할 수도 있습니다. 자세한 내용은 [응용 프로그램에 사용자 콘텐츠 구성을](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-user-consent-to-applications)참조 하세요.

#### <a name="the-enablegroupspecificconsent-setting"></a>"EnableGroupSpecificConsent" 설정

이 설정은 조직의 사용자가 소유 하 고 있는 그룹에 대 한 회사 데이터에 액세스 하는 앱에 동의할 수 있는지 여부를 제어 합니다. 팀 소유자가 동의를 제공 하려면이 설정을 사용 하도록 설정 해야 합니다. PowerShell을 사용 하 여이 설정을 관리 하는 방법에 대 한 단계는 [그룹 데이터에 액세스 하는 앱에 대 한 그룹 소유자 동의 구성을](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-group-owner-consent-to-apps-accessing-group-data)참조 하세요.

### <a name="settings-in-the-microsoft-teams-admin-center"></a>Microsoft 팀 관리 센터의 설정

앱 관리 페이지에서 Azure AD의 설정 [, 앱](manage-apps.md#manage-org-wide-app-settings) 이 차단 되거나 허용 되는지 [Manage apps](manage-apps.md) 여부, 팀 소유자에 게 할당 된 [앱 권한 정책](teams-app-permission-policies.md) 에 따라 [Manage apps](manage-apps.md#allow-and-block-apps) 팀 소유자가 동의를 제공할 수 있는지 여부가 결정 됩니다.

> [!IMPORTANT]
> 이러한 설정을 변경 해도 이미 동의 하는 앱에 대 한 데이터 액세스는 영향을 받지 않습니다. 예를 들어 조직 전체에서 타사 앱을 사용 하지 않도록 설정 하거나 특정 앱을 차단 하 여 팀 소유자가 동의 하지 않도록 하는 경우 이러한 변경 내용은 이미 부여 된 데이터 액세스를 제거 하지 않습니다.  

#### <a name="the-allow-third-party-apps-setting-in-org-wide-app-settings"></a>조직 전체 앱 설정의 "타사 앱 허용" 설정

이 조직 전체 앱 설정은 조직의 사용자가 타사 앱을 사용할 수 있는지 여부를 제어 합니다. 팀 소유자가 동의 하도록 설정 하려면이 설정을 지정 해야 합니다. 이 설정을 관리 하려면 다음을 수행 합니다.

1. Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **팀 앱**으로 이동 하 여  >  **앱을 관리**하 고 **조직 전체 앱 설정을**클릭 합니다.
2. 타사 **앱**에서 타사 **앱 허용**을 설정 하거나 해제 합니다.

    !["팀에서 타사 앱 허용" 설정의 스크린샷](media/resource-specific-consent-org-wide-setting.png)

변경 내용이 적용되는 데 최대 24시간이 걸릴 수 있습니다.

#### <a name="allow-or-block-the-app-at-the-org-level"></a>조직 수준에서 앱 허용 또는 차단

앱 [관리](manage-apps.md#allow-and-block-apps) 페이지에서 앱을 차단 하거나 허용 하면 해당 앱이 차단 되거나 조직의 모든 사용자에 게 허용 됩니다. 앱이 허용 되는 경우 팀 소유자는 앱에 대 한 동의만 부여할 수 있습니다. 조직 수준에서 앱을 허용 하거나 차단 하려면 다음을 수행 합니다.

1. Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **팀 앱**으로  >  **앱 관리**로 이동 합니다.
2. 앱 관리 페이지에서 앱을 선택한 다음 **차단** 을 클릭 하 여 차단 하거나 허용 하도록 **허용** 을 클릭 합니다.

    ![조직 전체 설정의 차단 된 앱 스크린샷](media/resource-specific-consent-allow-block-apps.png)

#### <a name="app-permission-policy-assigned-to-the-team-owner"></a>팀 소유자에 게 할당 된 앱 권한 정책

팀 소유자는 앱 권한 정책에서 실행할 수 있도록 허용 하는 앱에만 동의를 부여할 수 있습니다. 팀 소유자에 게 할당 된 앱 권한 정책을 보고 관리 하려면 다음을 수행 합니다.

1. Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **사용자**로 이동 합니다.
2. 팀 소유자의 표시 이름을 두 번 클릭 한 다음 **정책을**클릭 합니다.
3. 팀 소유자에 게 할당 된 정책이 **앱 권한 정책**아래에 나열 됩니다.
    - 다른 정책을 할당 하려면 **편집**을 클릭 한 다음 할당 하려는 정책을 선택 합니다.
    - 팀 소유자에 게 할당 된 정책의 설정을 편집 하려면 정책 이름을 클릭 한 다음 원하는 대로 변경 합니다.  

## <a name="uploading-custom-apps"></a>사용자 지정 앱 업로드

리소스 관련 승인을 사용 하는 사용자 지정 앱 (또한 테스트용으로 생성 됨)을 업로드 하는 경우 앱이 설치 되는 테 넌 트에서 가져와야 합니다. 즉, Azure AD 앱 등록은이 테 넌 트에서 가져와야 합니다. 전역 관리자는이 제한에서 제외 되며, 팀 (테스트용 로드) 또는 테 넌 트 앱 카탈로그로 직접 모든 테 넌 트에서 사용자 지정 앱을 업로드할 수 있습니다.

## <a name="related-topics"></a>관련 항목

- [Microsoft Graph](https://developer.microsoft.com/graph)
- [Microsoft 팀 관리 센터에서 앱 관리](manage-apps.md)
- [Teams에서 앱 사용 권한 정책 관리](teams-app-permission-policies.md)
