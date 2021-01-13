---
title: Microsoft Teams의 리소스별 동의
author: cichur
ms.author: v-cichur
ms.reviewer: nkramer
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 조직의 팀 소유자가 앱에 동의할 수 있는지 여부를 제어하도록 구성해야 하는 설정에 대해 자세히 배워야 합니다.
localization_priority: Normal
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d6267f4b42890716ca31fd1b44de435af50ad6ae
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815678"
---
# <a name="resource-specific-consent-in-microsoft-teams"></a>Microsoft Teams의 리소스별 동의

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Microsoft Teams의 리소스별 동의를 통해 팀 소유자는 앱에 동의하여 팀 데이터에 액세스할 수 있습니다. 이러한 액세스의 예로는 채널 메시지를 읽고, 채널을 만들고 삭제하고, 채널 탭을 만들고 제거하는 기능을 들 수 있습니다.

관리자는 조직의 팀 소유자가 Azure AD(Azure Active Directory) PowerShell 모듈 또는 Azure Portal 및 Microsoft Teams 관리 센터를 사용하여 구성한 설정을 통해 동의할 수 있는지 여부를 제어합니다.  

## <a name="set-whether-team-owners-can-give-consent-to-apps"></a>팀 소유자가 앱에 동의할 수 있는지 여부 설정

다음은 팀 소유자가 앱에 동의할 수 있는지 여부를 제어하기 위해 설정해야 하는 설정입니다. 다음 설정을 모두 검토해야 합니다.

### <a name="settings-in-azure-ad"></a>Azure AD의 설정

다음 두 설정은 팀 소유자가 앱에 동의할 수 있는지 여부를 확인합니다.

> [!IMPORTANT]
> 이러한 설정을 변경해도 이미 동의가 부여된 앱의 데이터 액세스에는 영향을 주지 않습니다. 예를 들어 팀 소유자가 동의하지 못하도록 이러한 설정을 구성하는 경우 이러한 변경 내용은 이미 부여된 데이터 액세스를 제거하지 않습니다.

#### <a name="the-users-can-consent-to-apps-accessing-company-data-on-their-behalf-setting"></a>"사용자가 사용자를 대신하여 회사 데이터에 액세스하는 앱에 동의할 수 있습니다." 설정

이 설정은 조직의 사용자가 대신 앱에 동의할 수 있는지 여부를 제어합니다. 팀 소유자가 동의할 수 있도록 설정하려면 이 설정을 예로 설정해야 **합니다.** 이 설정을 관리하기 위해 다음을 합니다.

1. Azure Portal에서 엔터프라이즈 애플리케이션 **사용자**  >  **설정으로 이동합니다.**
2. 엔터프라이즈 **애플리케이션에서**  사용자를 대신하여 회사 데이터에 액세스하는 앱에 동의할 수 있도록 **설정하여 아니요** 또는 예로 **설정할 수 있습니다.**

PowerShell을 사용하여 이 설정을 관리할 수 있습니다. 자세한 내용은 애플리케이션에 [대한 사용자 콘텐츠 구성을 참조하세요.](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-user-consent-to-applications)

#### <a name="the-enablegroupspecificconsent-setting"></a>"EnableGroupSpecificConsent" 설정

이 설정은 조직의 사용자가 소유한 그룹의 회사 데이터에 액세스하는 앱에 동의할 수 있는지 여부를 제어합니다. 팀 소유자가 동의를 제공하려면 이 설정을 사용하도록 설정해야 합니다. PowerShell을 사용하여 이 설정을 관리하는 방법에 대한 단계는 그룹 데이터에 액세스하는 앱에 대한 그룹 소유자 동의 [구성을 참조하세요.](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-group-owner-consent-to-apps-accessing-group-data)

### <a name="settings-in-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터의 설정

Azure AD의 설정 외에도 [](manage-apps.md#manage-org-wide-app-settings) 앱 관리 페이지의 전체 앱 설정, 앱 관리 페이지에서 앱이 차단되거나 허용되는지 [](teams-app-permission-policies.md) 여부 및 팀 소유자에게 할당된 앱 사용 권한 정책에 따라 팀 소유자가 동의할 수 있는지 여부가 결정됩니다. [](manage-apps.md) [](manage-apps.md#allow-and-block-apps)

> [!IMPORTANT]
> 이러한 설정을 변경해도 이미 동의가 부여된 앱의 데이터 액세스에는 영향을 주지 않습니다. 예를 들어, 타사 앱을 전체적으로 사용하지 않도록 설정하거나 팀 소유자가 동의하지 못하도록 특정 앱을 차단하는 경우 이러한 변경 내용은 이미 부여된 데이터 액세스를 제거하지 않습니다.  

#### <a name="the-allow-third-party-apps-setting-in-org-wide-app-settings"></a>전체 앱 설정의 "타사 앱 허용" 설정

이 조직 전체 앱 설정은 조직의 사용자가 타사 앱을 사용할 수 있는지 여부를 제어합니다. 팀 소유자가 동의할 수 있도록 이 설정을 설정해야 합니다. 이 설정을 관리하기 위해 다음을 합니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 **Teams** 앱 관리 앱으로 이동한 다음, 전체 앱 설정을  >   **클릭합니다.**
2. 타사 **앱에서** 타사 앱 허용을 끄거나 **끄면 됩니다.**

    !["Teams에서 타사 앱 허용" 설정 스크린샷](media/resource-specific-consent-org-wide-setting.png)

변경 내용이 적용되는 데 최대 24시간이 걸릴 수 있습니다.

#### <a name="allow-or-block-the-app-at-the-org-level"></a>Or block the app at the or block the or block the app at the or block the app at

앱 관리 페이지에서 앱을 차단하거나 허용하면 해당 앱이 차단되거나 조직의 모든 사용자에게 허용됩니다. [](manage-apps.md#allow-and-block-apps) 팀 소유자는 앱이 허용되는 경우 앱에 동의할 수 있습니다. Or block an app at the or block the or block the app, do the following:

1. Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 **Teams 앱 관리**  >  **앱으로 이동하세요.**
2. 앱 관리 페이지에서 앱을 선택한 다음 차단을 클릭하여 차단하거나  허용을 클릭합니다. 

    ![전체 설정에서 차단된 앱의 스크린샷](media/resource-specific-consent-allow-block-apps.png)

#### <a name="app-permission-policy-assigned-to-the-team-owner"></a>팀 소유자에게 할당된 앱 사용 권한 정책

팀 소유자는 앱 사용 권한 정책이 실행할 수 있도록 허용하는 앱에만 동의할 수 있습니다. 팀 소유자에게 할당된 앱 사용 권한 정책을 보고 관리하려면 다음을 실행합니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 사용자로 **이동하세요.**
2. 팀 소유자의 표시 이름을 두 번 클릭한 다음 정책을 **클릭합니다.**
3. 팀 소유자에게 할당된 정책은 앱 사용 권한 정책 **아래에 나열됩니다.**
    - 다른 정책을 할당하려면 **편집을** 클릭한 다음 할당할 정책을 선택합니다.
    - 팀 소유자에게 할당된 정책 설정을 편집하려면 정책 이름을 클릭한 다음 원하는 내용을 변경합니다.  

## <a name="uploading-custom-apps"></a>사용자 지정 앱 업로드

리소스별 동의를 사용하는 사용자 지정 앱(사이드로드라고도 하는)을 업로드할 때 앱이 설치되는 테넌트에서 제공되어야 합니다. 즉, Azure AD 앱 등록은 이 테넌트에서 제공되어야 합니다. 전역 관리자는 이 제한에서 제외되고, 모든 테넌트에서 직접 팀(사이드로드) 또는 테넌트 앱 카탈로그에 사용자 지정 앱을 업로드할 수 있습니다.

## <a name="related-topics"></a>관련 항목

- [사용 가능한 RSC 권한](https://aka.ms/teams-rsc)
- [Microsoft Graph](https://developer.microsoft.com/graph)
- [Microsoft Teams 관리 센터에서 앱 관리](manage-apps.md)
- [Teams에서 앱 사용 권한 정책 관리](teams-app-permission-policies.md)
