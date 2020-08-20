---
title: 앱 사용 권한 보기 및 Microsoft Teams 관리 센터에서 관리자 동의
author: LanaChin
ms.author: v-lanac
ms.reviewer: vaibhava
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 앱에서 요청된 사용 권한을 보고 Microsoft Teams 관리 센터의 앱 관리 페이지에서 앱의 동의를 할당하는 방법을 알아보세요.
localization_priority: Normal
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 737052ba5794b221caa08fa8ccfabec0d597c3ad
ms.sourcegitcommit: 34f407a6a40317056005e3bf38ce58f792c04810
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814617"
---
# <a name="view-app-permissions-and-grant-admin-consent-in-the-microsoft-teams-admin-center"></a>앱 사용 권한 보기 및 Microsoft Teams 관리 센터에서 관리자 동의

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Microsoft [Teams 관리 센터의](manage-apps.md) 앱 관리 페이지는 조직의 모든 Teams 앱을 보고 관리할 수 있습니다. 예를 들어 앱의 조직 수준 상태 및 속성을 보고, 조직의 앱 스토어에 새 사용자 지정 앱을 승인 또는 업로드하고, 조직 수준에서 앱을 차단하거나 허용하고, 조직 전체 앱 설정을 관리할 수 있습니다.

여기에서는 데이터에 액세스하고 앱에 대한 RSC(리소스별 동의) 권한을 볼 수 있는 앱에 대한 관리자 동의를 부여할 수도 있습니다.

## <a name="grant-org-wide-admin-consent-to-an-app"></a>조직 전체 관리 동의를 앱에 부여

관리자는 조직의 모든 사용자를 대신하여 권한을 요청하는 앱에 대한 동의를 검토하고 부여할 수 있습니다. 이렇게 하면 다른 사용자가 앱을 시작할 때 앱에서 요청한 권한을 검토하고 수락할 필요가 없습니다. 또한 일부 사용자는 Azure [consent settings](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent) AD(Azure Active Directory)의 사용자 동의 설정에 따라 일부 사용자는 회사 데이터에 액세스하는 앱에 동의하지 못할 수 있습니다.

앱에서 요청하는 사용 권한의 예로는 팀에 저장된 정보를 읽고, 사용자의 프로필을 읽고, 사용자를 대신하여 전자 메일을 보내는 기능이 있습니다. 자세한 내용은 [Microsoft ID 플랫폼 끝점에서 사용 권한 및 동의를 참조하세요.](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent) 

조직 전체의 동의를 부여하려면 전역 관리자여야 합니다. 사용 **권한 열은** 앱에 동의하는 사용 권한이 있는지 여부를 나타내는 중입니다. Azure AD에 **의해 동의가** 필요한 사용 권한이 있는 Azure AD에 등록된 각 앱에 대한 세부 정보 보기 링크가 표시됩니다. 이러한 변경은 사용자 지정 및 타사 앱에만 적용됩니다. 이 링크가 표시되지 않거나 Microsoft에서 게시한 앱에 대해 관리자 동의를 설정해야 합니다.

:::image type="content" source="media/app-perm-admin-center-permissions-column.png" alt-text="앱 관리 페이지의 사용 권한 열 스크린샷":::

앱에 대비하여 전체 동의를 부여하려면 다음 단계를 따르세요.

1. Microsoft Teams 관리 센터의 왼쪽 탐색에서 Teams 앱 관리 **앱으로**  >  **이동합니다.**
2. 다음 중 하나를 수행합니다.
    - 원하는 앱을 검색하고 앱 이름을 클릭하여 앱 세부 정보 페이지로 이동한 다음 사용 권한 **탭을 선택합니다.**
    - 사용 권한 **열을** 내림차순으로 정렬하여 앱을 찾은 다음 세부 정보 **보기를 선택합니다.** 이렇게 하면 앱 세부 정보 **페이지의 사용** 권한 탭으로 이동합니다.

3. 구성 **전체 사용 권한에서 권한** **검토와 동의를 선택합니다.** 이 작업을 수행하려면 전역 관리자여야 합니다. 이 옵션은 Teams 서비스 관리자에게는 사용할 수 없습니다.

    :::image type="content" source="media/app-perm-admin-center-org-wide.png" alt-text="앱에 대한 사용 권한 탭에 대한 전체 사용 권한 스크린샷":::

4. 사용 **권한 탭에서** 앱에서 요청한 사용 권한을 검토합니다.

    :::image type="content" source="media/app-perm-admin-center-org-wide-permissions.png" alt-text="앱에서 요청한 사용 권한 스크린샷":::

    > [!IMPORTANT]
    > 앱에 조직 전체 동의를 부여하면 앱에서 조직 데이터에 액세스할 수 있습니다. 동의를 부여하기 전에 앱에서 요청한 사용 권한을 신중히 검토하세요.
5. 앱에서 요청한 사용 권한에 동의하는 경우 **동의를** 클릭하여 동의를 부여합니다. 페이지 맨 위에 일시적으로 배너가 표시되어 앱에 대해 요청된 사용 권한이 부여된 사이를 알 수 있습니다. 이제 앱이 조직의 모든 사용자에 대해 지정된 리소스에 액세스할 수 있고 사용 권한을 검토하라는 메시지가 다른 사람도 액세스할 수 없습니다.

사용 권한을 수락하면 앱 세부 정보 페이지에 있는 **조직** 전체 의료 사용 권한 아래에 동의해야 한다는 내용이 사용자에게 표시됩니다. 앱의 사용 권한에 대한 세부 정보를 보려면 **Azure Active Directory** 링크를 클릭하여 Azure AD 포털의 앱 페이지로 이동합니다.

:::image type="content" source="media/app-perm-admin-center-org-wide-accepted.png" alt-text="동의가 전송된 경우 표시되는 메시지 스크린샷":::

조직의 사용자가 동의를 부여할 수 있으며 한 명 이상의 사용자가 특정 앱에 동의할 수 있는 경우 동의가 허용되었고 Azure Active Directory 링크만 있음을 알리는 메시지만 표시됩니다. 

## <a name="view-resource-specific-consent-permissions-of-an-app"></a>앱에 대한 리소스별 동의 사용 권한 보기

RSC 권한을 부여하면 팀 소유자가 앱에 대한 동의를 부여하여 팀의 데이터에 액세스하고 수정할 수 있습니다. RSC 사용 권한은 특정 팀에서 수행할 수 있는 작업을 정의하는 Teams 전용 권한의 일반적인 사용 권한입니다. RSC 사용 권한의 예로는 채널을 만들고 삭제하고, 팀의 설정을 가져올 수 있는 권한을 가져올 수 있는 권한을 비동기, 채널 탭을 만들고 제거하는 기능이 있습니다. RSC 권한은 Azure AD에 있지 만며 앱 매니메이션에 정의됩니다.

팀에 앱을 추가하는 경우 RSC 사용 권한에 동의합니다. 자세한 내용은 [Teams에서 리소스 관련 동의(RSC) 및](https://docs.microsoft.com/microsoftteams/platform/graph-api/rsc/resource-specific-consent) [리소스 관련 동의를 참조하세요.](resource-specific-consent.md)

전역 관리자 및 Teams 서비스 관리자는 RSC 사용 권한을 볼 수 있습니다. 앱용 RSC 권한을 보려면 다음 단계를 따릅니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색에서 Teams 앱 관리 **앱으로**  >  **이동합니다.**
2. 원하는 앱을 검색하고 앱 이름을 클릭하여 앱 세부 정보 페이지로 이동한 다음 사용 권한 **탭을 선택합니다.**
3. **Microsoft Graph Resource(Conph Resource-specific consent) 권한에서**앱에서 요청한 RSC 권한을 검토합니다.

    :::image type="content" source="media/app-perm-admin-center-rsc.png" alt-text="앱에 대한 RSC 사용 권한 스크린샷":::

## <a name="related-topics"></a>관련 항목

- [Microsoft Teams 관리 센터에서 앱 관리](manage-apps.md)
- [Microsoft ID 플랫폼 끝점의 사용 권한 및 동의](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent)
- [Teams에서 리소스별 동의](resource-specific-consent.md)
- [RSC(Resource-specific 동의)](https://docs.microsoft.com/microsoftteams/platform/graph-api/rsc/resource-specific-consent)


