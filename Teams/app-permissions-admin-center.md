---
title: Microsoft Teams 관리 센터에서 앱 사용 권한 보기 및 관리자 동의 권한 부여
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
audience: admin
ms.service: msteams
ms.subservice: teams-apps
search.appverid: MET150
description: Microsoft Teams 관리 센터의 앱 관리 페이지에서 앱에서 요청한 권한을 보고 앱에 관리자 동의를 부여하는 방법을 알아보세요.
ms.localizationpriority: medium
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6ba381d5d6806c1abd7a2766228ff74f843b156a
ms.sourcegitcommit: ceba5fd8f098c8d0eafaffe5c5301c845a3ae7ab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/20/2022
ms.locfileid: "67837518"
---
# <a name="view-app-permissions-and-grant-admin-consent-in-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터에서 앱 사용 권한 보기 및 관리자 동의 권한 부여

관리자는 Teams 관리 센터의 앱 관리 페이지에서 모든 Teams 앱을 보고 관리합니다. 조직 내에서 만든 사용자 지정 앱을 관리하고 최종 사용자에게만 사용할 수 있으며 Teams 앱 스토어에서 사용할 수 있는 타사 앱을 관리할 수 있습니다. 예를 들어 앱의 조직 수준 상태 및 속성을 보고, 조직의 앱 스토어에 새 사용자 지정 앱을 승인 또는 업로드하고, 조직의 수준에서 또는 개별 최종 사용자에 대해 앱을 허용할 수 있습니다.

여기에서는 데이터 액세스 권한을 요청하고 앱에 대한 RSC(리소스별 동의) 권한을 요청하는 앱에 조직 전체의 관리자 동의를 부여할 수도 있습니다.

## <a name="grant-org-wide-admin-consent-to-an-app"></a>앱에 조직 전체 관리자 동의 부여

전역 관리자인 경우 조직의 모든 사용자를 대신하여 권한을 요청하는 앱을 검토하고 동의를 부여할 수 있습니다. 이렇게 하면 사용자가 앱을 시작할 때 앱에서 요청한 권한을 검토하고 수락할 필요가 없습니다. 또한 Azure AD(Azure Active Directory)의 사용자 [동의 설정](/azure/active-directory/manage-apps/configure-user-consent)에 따라 일부 사용자는 회사 데이터에 액세스하는 앱에 동의를 부여하지 못할 수 있습니다.

앱에서 요청하는 권한의 예로는 팀에 저장된 정보 읽기, 사용자 프로필 읽기, 사용자 대신 이메일 보내기 등이 있습니다. 자세한 내용은 [Microsoft ID 플랫폼 엔드포인트의 권한 및 동의](/azure/active-directory/develop/v2-permissions-and-consent)를 참조하세요.

**권한** 열은 앱에 동의가 필요한 권한이 있는지 여부를 나타냅니다. 동의가 필요한 권한이 있는 Azure AD에 등록된 각 앱에 대한 **세부 정보 보기** 링크가 표시됩니다. 이는 사용자 지정 및 타사 앱에만 적용됩니다. Microsoft에서 제공하는 앱에는 링크를 사용할 수 없습니다. 또한 관리자는 이러한 앱에 대한 동의를 부여할 필요가 없습니다.

앱에 조직 전체의 동의를 부여하려면 다음 단계를 따르세요.

1. Microsoft Teams 관리 센터의 왼쪽 탐색에서 **Teams 앱** > **[앱 관리](https://admin.teams.microsoft.com/policies/manage-apps)** 로 이동합니다.

1. 다음 중 하나를 수행합니다.
    * 원하는 앱을 검색하고 앱 이름을 선택하여 앱 세부 정보 페이지로 이동한 다음 **사용 권한 탭을** 선택합니다.
    * **권한** 열을 내림차순으로 정렬하여 앱을 찾은 다음 **세부 정보 보기** 를 선택합니다. 이렇게 하면 앱 세부 정보 페이지의 **권한** 탭으로 이동합니다.

1. **조직 전체 권한** 에서 **권한 검토 및 동의** 를 선택합니다.

    :::image type="content" source="media/app-perm-admin-center-org-wide.png" alt-text=" 앱의 사용 권한 탭에 있는 조직 전체 권한의 스크린샷입니다.":::

    이렇게 하려면 전역 관리자여야 합니다. 이 옵션은 Teams 서비스 관리자가 사용할 수 없습니다.

1. **권한** 탭에서 앱에서 요청한 권한을 검토합니다.

    :::image type="content" source="media/app-perm-admin-center-org-wide-permissions.png" alt-text="앱에서 요청한 권한의 스크린샷.":::

    > [!IMPORTANT]
    > 앱에 조직 전체에 대한 동의를 부여하면 앱에서 조직의 데이터에 액세스할 수 있습니다. 동의하기 전에 앱에서 요청한 권한을 주의 깊게 검토하세요.

1. 앱에서 요청한 사용 권한에 동의하는 경우 **동의** 를 선택하여 동의를 부여합니다. 요청한 권한이 앱에 부여되었음을 알리는 배너가 페이지 상단에 일시적으로 나타납니다. 이제 앱에서 조직의 모든 사용자에 대해 지정된 리소스에 액세스할 수 있으며 권한을 검토하라는 메시지가 표시되지 않습니다.

권한을 수락하면 앱 세부 정보 페이지의 **조직 전체 권한** 아래에 동의가 부여되었음을 알리는 메시지가 표시됩니다. 앱의 권한에 대한 세부 정보를 보려면 **Azure Active Directory** 링크를 선택하여 Azure AD 포털에서 앱 페이지로 이동합니다.

:::image type="content" source="media/app-perm-admin-center-org-wide-accepted-new.png" alt-text="동의가 승인되었을 때 표시되는 메시지의 스크린샷.":::

조직의 사용자가 동의를 부여할 수 있고 한 명 이상의 사용자에게 특정 앱에 대한 동의가 부여된 경우 동의가 부여되었음을 알려주는 동일한 메시지와 Azure AD 포털의 앤 페이지에 대한 Azure Active Directory 링크가 표시됩니다.

> [!NOTE]
> Teams 서비스 관리자는 **권한 검토 및 동의** 옵션을 사용할 수 없으며 앱에 조직 전체 관리자 동의를 부여할 수 없지만 팀 서비스 관리자는 앱의 **권한** 탭에서 콘텐츠를 볼 수 있습니다. 예를 들어 Teams 서비스 관리자는 **Azure Active Directory** 링크를 클릭하여 Azure AD 포털에서 앱 권한 세부 정보를 볼 수 있습니다.

## <a name="view-resource-specific-consent-permissions-of-an-app"></a>앱의 리소스별 동의 권한 보기

RSC 권한을 통해 팀 소유자는 앱이 팀 데이터에 액세스하고 수정하는 데 동의할 수 있습니다. RSC 권한은 앱이 특정 팀에서 수행할 수 있는 작업을 정의하는 세분화된 팀별 권한입니다. RSC 권한의 예로는 채널 생성 및 삭제, 팀 설정 가져오기, 채널 탭 생성 및 제거 등이 있습니다.

RSC 권한은 Azure AD가 아닌 앱 매니페스트에 정의됩니다. 앱을 팀에 추가할 때 RSC 권한에 동의합니다. 자세한 내용은 [리소스별 동의(RSC)](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)를 참조하세요.

전역 관리자 및 Teams 서비스 관리자는 앱 세부 정보 페이지의 **권한** 탭에서 앱에 대한 RSC 권한을 볼 수 있습니다.

앱에 대한 RSC 권한을 보려면 다음 단계를 따르세요.

1. Microsoft Teams 관리 센터의 왼쪽 탐색 창에서 **Teams 앱** > **앱 관리** 로 이동합니다.
1. 원하는 앱을 검색하고 앱 이름을 선택하여 앱 세부 정보 페이지로 이동한 다음 **사용 권한 탭을** 선택합니다.
1. **Microsoft Graph 리소스별 동의(RSC) 권한** 에서 앱에서 요청한 RSC 권한을 검토합니다.

    :::image type="content" source="media/app-perm-admin-center-rsc-new.png" alt-text="앱에 대한 RSC 권한 스크린샷.":::

## <a name="known-issues"></a>알려진 문제

### <a name="the-view-details-link-isnt-displayed-in-the-permissions-column-for-some-third-party-apps-that-request-permissions"></a>권한을 요청하는 일부 타사 앱의 권한 열에 "세부 정보 보기" 링크가 표시되지 않습니다.

일부 타사 앱에서는 사용 권한을 검토하고 동의하는 기능을 사용할 수 없습니다. 일반적으로 타사 앱은 앱에서 사용 권한을 요청할 때 Azure Active Directory에 등록됩니다. **세부 정보 보기** 링크 대신 권한 열에 **`--`** 이(가) 표시됩니다.

## <a name="related-articles"></a>관련 기사

* [Microsoft Teams 관리 센터에서 앱 관리](manage-apps.md)
* [Microsoft ID 플랫폼 엔드포인트의 권한 및 동의](/azure/active-directory/develop/v2-permissions-and-consent)
* [Teams의 리소스별 동의](resource-specific-consent.md)
* [리소스별 동의(RSC)](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)
* [Teams 앱 수명 주기 탐색](https://aka.ms/PR132)(Ignite 2020 세션)
