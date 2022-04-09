---
title: Microsoft Teams 관리 센터에서 앱 사용 권한 보기 및 관리자 동의 부여
author: guptaashish
ms.author: guptaashish
ms.reviewer: vaibhava
manager: prkosh
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Microsoft Teams 관리 센터의 앱 관리 페이지에서 앱에서 요청한 권한을 보고 앱에 대한 관리자 동의를 부여하는 방법을 알아봅니다.
ms.localizationpriority: medium
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 54fbd67fffa666e7f07719305075be264f077976
ms.sourcegitcommit: f3c380f745af4c3aaa2720234860b45696a0c333
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2022
ms.locfileid: "63442274"
---
# <a name="view-app-permissions-and-grant-admin-consent-in-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터에서 앱 사용 권한 보기 및 관리자 동의 부여

Microsoft Teams 관리 센터의 [앱 관리](manage-apps.md) 페이지에서 조직의 모든 Teams 앱을 보고 관리할 수 있습니다. 예를 들어 앱의 조직 수준 상태 및 속성을 확인하고, 조직의 앱 스토어에 새 사용자 지정 앱을 승인 또는 업로드하고, 조직 수준에서 앱을 차단 또는 허용하고, 조직 전체 앱 설정을 관리할 수 있습니다.

여기에서 데이터에 액세스하고 앱에 대한 RSC(리소스별 동의) 권한을 볼 수 있는 권한을 요청하는 앱에 조직 전체 관리자 동의를 부여할 수도 있습니다.

## <a name="grant-org-wide-admin-consent-to-an-app"></a>앱에 조직 전체 관리자 동의 부여

전역 관리자인 경우 조직의 모든 사용자를 대신하여 권한을 요청하는 앱에 대한 동의를 검토하고 부여할 수 있습니다. 이렇게 하면 사용자가 앱을 시작할 때 앱에서 요청한 권한을 검토하고 수락할 필요가 없습니다. 또한 Azure Active Directory(Azure AD)의 사용자 [동의 설정](/azure/active-directory/manage-apps/configure-user-consent)에 따라 일부 사용자는 회사 데이터에 액세스하는 앱에 동의를 부여할 수 없습니다.

앱에서 요청한 권한의 예로는 팀에 저장된 정보를 읽고, 사용자의 프로필을 읽고, 사용자를 대신하여 이메일을 보내는 기능이 있습니다. 자세한 내용은 [Microsoft ID 플랫폼 엔드포인트에서 사용 권한 및 동의를](/azure/active-directory/develop/v2-permissions-and-consent) 참조하세요.

**권한** 열은 앱에 동의가 필요한 권한이 있는지 여부를 나타냅니다. 동의가 필요한 권한이 있는 Azure AD에 등록된 각 앱에 대한 **세부 정보 보기** 링크가 표시됩니다. 이는 사용자 지정 및 타사 앱에만 적용됩니다. 이 링크가 표시되지 않거나 Microsoft에서 게시한 앱에 대한 관리자 동의를 부여해야 합니다.

:::image type="content" source="media/app-perm-admin-center-permissions-column.png" alt-text="앱 관리 페이지의 사용 권한 열 스크린샷":::

앱에 조직 전체 동의를 부여하려면 다음 단계를 수행합니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색 창에서 **Teams 앱** > **앱 관리** 로 이동합니다.
2. 다음 중 하나를 수행합니다.
    - 원하는 앱을 검색하고 앱 이름을 클릭하여 앱 세부 정보 페이지로 이동한 다음 **사용 권한 탭을** 선택합니다.
    - **권한** 열을 내림차순으로 정렬하여 앱을 찾은 다음 **세부 정보 보기를** 선택합니다. 이렇게 하면 앱 세부 정보 페이지의 **사용 권한** 탭으로 이동합니다.

3. **조직 전체 권한** 에서 **검토 권한 및 동의를** 선택합니다.

    :::image type="content" source="media/app-perm-admin-center-org-wide.png" alt-text="앱의 사용 권한 탭에 대한 조직 전체 권한의 스크린샷.":::

    이렇게 하려면 전역 관리자여야 합니다. 이 옵션은 Teams 서비스 관리자가 사용할 수 없습니다.

4. **사용 권한** 탭에서 앱에서 요청한 권한을 검토합니다.

    :::image type="content" source="media/app-perm-admin-center-org-wide-permissions.png" alt-text="앱에서 요청한 권한의 스크린샷.":::

    > [!IMPORTANT]
    > 앱에 조직 전체 동의를 부여하면 앱이 조직의 데이터에 액세스할 수 있습니다. 동의를 부여하기 전에 앱에서 요청한 사용 권한을 신중하게 검토합니다.
5. 앱에서 요청한 사용 권한에 동의하는 경우 동의를 클릭하여 동의를 부여 **합니다** . 앱에 대해 요청된 권한이 부여되었음을 알리기 위해 페이지 맨 위에 배너가 일시적으로 표시됩니다. 이제 앱은 조직의 모든 사용자에 대해 지정된 리소스에 액세스할 수 있으며 다른 사용자에게 사용 권한을 검토하라는 메시지가 표시되지 않습니다.

사용 권한을 수락하면 앱 세부 정보 페이지의 **조직 전체 권한** 아래에 동의가 부여되었음을 알리는 메시지가 표시됩니다. 앱의 권한에 대한 세부 정보를 보려면 **Azure Active Directory** 링크를 클릭하여 Azure AD 포털에서 앱 페이지로 이동합니다.

:::image type="content" source="media/app-perm-admin-center-org-wide-accepted-new.png" alt-text="동의가 부여될 때 표시되는 메시지의 스크린샷.":::

조직의 사용자가 동의를 부여할 수 있고 하나 이상의 사용자가 특정 앱에 대한 동의를 부여한 경우 동의가 부여되었음을 알리는 동일한 메시지와 Azure AD 포털의 앱 페이지에 대한 Azure Active Directory 링크도 표시됩니다.

> [!NOTE]
> Teams 서비스 관리자는 **검토 권한 및 동의** 옵션을 사용할 수 없으며 앱에 대한 조직 전체 관리자 동의를 부여할 수 없지만 Teams 서비스 관리자는 앱의 **사용 권한** 탭에서 콘텐츠를 볼 수 있습니다. 예를 들어 Teams 서비스 관리자는 **Azure Active Directory** 링크를 클릭하여 Azure AD 포털에서 앱 사용 권한 세부 정보를 볼 수 있습니다.

## <a name="view-resource-specific-consent-permissions-of-an-app"></a>앱의 리소스별 동의 권한 보기

RSC 권한을 통해 팀 소유자는 앱에 대한 동의를 부여하여 팀의 데이터에 액세스하고 수정할 수 있습니다. RSC 권한은 앱이 특정 팀에서 수행할 수 있는 작업을 정의하는 세분화된 Teams 특정 권한입니다. RSC 권한의 예로는 채널을 만들고 삭제하고, 팀에 대한 설정을 얻고, 채널 탭을 만들고 제거하는 기능이 있습니다.

RSC 권한은 Azure AD가 아닌 앱 매니페스트에 정의됩니다. 팀에 앱을 추가할 때 RSC 권한에 대한 동의를 부여합니다. 자세한 내용은 [RSC(리소스별 동의)](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)를 참조하세요.

전역 관리자 및 Teams 서비스 관리자는 앱 세부 정보 페이지의 **사용 권한** 탭에서 앱에 대한 RSC 권한을 볼 수 있습니다.

앱에 대한 RSC 권한을 보려면 다음 단계를 수행합니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색 창에서 **Teams 앱** > **앱 관리** 로 이동합니다.
2. 원하는 앱을 검색하고 앱 이름을 클릭하여 앱 세부 정보 페이지로 이동한 다음 **사용 권한 탭을** 선택합니다.
3. **Microsoft Graph RSC(리소스 관련 동의) 권한** 아래에서 앱에서 요청한 RSC 권한을 검토합니다.

    :::image type="content" source="media/app-perm-admin-center-rsc-new.png" alt-text="앱에 대한 RSC 권한의 스크린샷":::

## <a name="known-issues"></a>알려진 문제

### <a name="the-view-details-link-isnt-displayed-in-the-permissions-column-for-some-third-party-apps-that-request-permissions"></a>권한을 요청하는 일부 타사 앱의 사용 권한 열에 "세부 정보 보기" 링크가 표시되지 않습니다.

현재 권한을 검토하고 동의를 부여하는 기능은 권한을 요청하는 Azure AD에 등록된 모든 타사 앱에 사용할 수 없습니다. **세부 정보 보기** 링크 대신 **사용 권한** 열에 표시됩니다 **--**. 이 기능을 앱에 사용하도록 설정하기 위해 ISV와 협력하고 있습니다.

## <a name="related-topics"></a>관련 주제

- [Microsoft Teams 관리 센터에서 앱 관리](manage-apps.md)
- [Microsoft ID 플랫폼 엔드포인트의 사용 권한 및 동의](/azure/active-directory/develop/v2-permissions-and-consent)
- [Teams 리소스별 동의](resource-specific-consent.md)
- [RSC(리소스 관련 동의)](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)
- [Teams 앱 수명 주기 탐색](https://aka.ms/PR132)(Ignite 2020 세션)
