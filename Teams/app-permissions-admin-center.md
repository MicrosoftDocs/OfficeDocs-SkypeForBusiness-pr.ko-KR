---
title: Microsoft 팀 관리 센터에서 앱 사용 권한 보기 및 관리자 동의 허용
author: LanaChin
ms.author: v-lanac
ms.reviewer: vaibhava
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 앱에서 요청 하는 사용 권한을 확인 하 고 Microsoft 팀 관리 센터의 앱 관리 페이지에서 앱에 관리자 동의를 부여 하는 방법에 대해 알아봅니다.
localization_priority: Normal
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 50a9abbd7e5872229c09d7d80c00c5d432723da1
ms.sourcegitcommit: c79b83e03a89649e2b6e494a741a392819baf2d2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/13/2020
ms.locfileid: "48433051"
---
# <a name="view-app-permissions-and-grant-admin-consent-in-the-microsoft-teams-admin-center"></a>Microsoft 팀 관리 센터에서 앱 사용 권한 보기 및 관리자 동의 허용

Microsoft 팀 관리 센터의 [앱 관리](manage-apps.md) 페이지에서 조직의 모든 팀 앱을 보고 관리할 수 있습니다. 예를 들어 앱의 조직 수준 상태 및 속성을 확인 하 고, 조직의 앱 스토어에 새 사용자 지정 앱을 승인 또는 업로드 하 고, 조직 수준의 앱을 차단 하거나 허용 하 고, 조직 전체 앱 설정을 관리할 수 있습니다.

여기서는 데이터에 액세스 하 고 앱에 대 한 RSC (리소스 관련 승인) 권한을 볼 수 있는 권한을 요청 하는 앱에 조직 전체 관리자 동의를 부여할 수도 있습니다.

## <a name="grant-org-wide-admin-consent-to-an-app"></a>앱에 조직 전체 관리자 동의 허용

전역 관리자 인 경우 조직의 모든 사용자를 대신 하 여 권한을 요청 하는 앱에 대 한 동의를 검토 하 고 부여할 수 있습니다. 이렇게 하면 사용자가 앱을 시작할 때 앱에서 요청 하는 사용 권한을 검토 하 고 수락할 필요가 없습니다. 또한 azure AD (Active Directory)의 사용자 [동의 설정](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent) 에 따라 일부 사용자는 회사 데이터에 액세스 하는 앱에 동의를 허용 하지 않을 수 있습니다.

앱에서 요청 하는 권한에는 팀에 저장 된 정보를 읽고, 사용자 프로필을 읽고, 사용자를 대신 하 여 전자 메일을 보낼 수 있는 권한이 포함 됩니다. 자세한 내용은 [Microsoft id 플랫폼 끝점의 사용 권한 및 동의](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent)를 참조 하세요. 

**사용 권한** 열은 앱에 동의가 필요한 권한이 있는지 여부를 나타냅니다. 동의를 필요로 하는 권한이 있는 Azure AD에 등록 된 각 앱에 대 한 **세부 정보 보기** 링크가 표시 됩니다. 이는 사용자 지정 및 타사 앱에만 적용 됨을 염두에 두어야 합니다. Microsoft에서 게시 한 앱에 대해이 링크가 표시 되지 않거나 관리자 동의를 부여 해야 합니다.

:::image type="content" source="media/app-perm-admin-center-permissions-column.png" alt-text="앱 관리 페이지의 사용 권한 열 스크린샷":::

앱에 조직 전체 동의를 부여 하려면 다음 단계를 따릅니다.

1. Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **팀 앱**으로  >  **앱 관리**로 이동 합니다.
2. 다음 중 하나를 수행합니다.
    - 원하는 앱을 검색 하 고 앱 이름을 클릭 하 여 앱 세부 정보 페이지로 이동한 다음 **사용 권한** 탭을 선택 합니다.
    - **사용 권한** 열을 내림차순으로 정렬 하 여 앱을 찾은 다음 **세부 정보 보기**를 선택 합니다. 이 작업을 수행 하면 앱 세부 정보 페이지의 **사용 권한** 탭으로 이동 합니다.

3. **조직 전체 사용 권한**아래에서 **사용 권한 검토 및 동의**를 선택 합니다.

    :::image type="content" source="media/app-perm-admin-center-org-wide.png" alt-text="앱에 대 한 사용 권한 탭의 조직 전체 사용 권한 스크린샷":::

    이 작업을 수행 하려면 전역 관리자 여야 합니다. 이 옵션은 팀 서비스 관리자가 사용할 수 없습니다.

4. **사용 권한** 탭에서 앱에 요청 된 사용 권한을 검토 합니다.

    :::image type="content" source="media/app-perm-admin-center-org-wide-permissions.png" alt-text="앱에서 요청 하는 사용 권한의 스크린샷":::

    > [!IMPORTANT]
    > 앱에 조직 전체 승인을 부여 하면 앱에서 조직의 데이터에 액세스할 수 있습니다. 동의를 부여 하기 전에 앱에서 요청한 권한을 신중 하 게 검토 합니다.
5. 앱에서 요청 하는 사용 권한에 동의 하는 경우 **수락** 을 클릭 하 여 동의를 부여 합니다. 앱에 대해 요청 된 사용 권한이 부여 되었음을 알 수 있도록 페이지 맨 위에 잠시 배너가 표시 됩니다. 이제 앱이 조직의 모든 사용자에 대해 지정 된 리소스에 액세스할 수 있으며 그 외에는 사용 권한을 검토 하 라는 메시지가 표시 되지 않습니다.

사용 권한을 수락 하면 앱 세부 정보 페이지에 대 한 **조직 전체 사용 권한** 아래에 메시지가 표시 되어 동의가 승인 되었음을 알 수 있습니다. 앱의 사용 권한에 대 한 세부 정보를 보려면 azure AD 포털에서 앱의 페이지로 이동 하려면 **Azure Active Directory** 링크를 클릭 합니다.

:::image type="content" source="media/app-perm-admin-center-org-wide-accepted.png" alt-text="동의를 허용 했을 때 표시 되는 메시지 스크린샷":::

조직의 사용자에 게 동의를 허용 하 고 특정 앱에 대 한 동의를 부여한 사용자가 한 명 이상에 게 부여 되는 경우,이를 알리는 메시지가 표시 되며 Azure AD portal에서 앱의 페이지에 대 한 Azure Active Directory 링크가 승인 되었음을 알려 줍니다.

> [!NOTE]
> 그러나, **사용 권한 및 승인** 옵션은 팀 서비스 관리자가 사용할 수 없으며, 앱에 대 한 조직 전체 관리자 동의를 부여할 수는 없습니다. 팀 서비스 관리자는 앱에 대 한 **사용 권한** 탭의 콘텐츠를 볼 수 있습니다. 예를 들어 팀 서비스 관리자는 azure AD 포털에서 앱 사용 권한 세부 정보를 볼 수 있는 **Azure Active Directory** 링크를 클릭할 수 있습니다. 

## <a name="view-resource-specific-consent-permissions-of-an-app"></a>앱에 대 한 리소스 관련 승인 사용 권한 보기

RSC 권한을 통해 팀 소유자는 팀 데이터에 액세스 하 고 수정할 수 있는 앱에 대 한 동의를 부여 합니다. RSC 권한은 앱이 특정 팀에서 수행할 수 있는 작업을 정의 하는 세부적인 팀 관련 권한입니다. RSC 권한의 예로는 채널을 만들고 삭제 하 고, 팀에 대 한 설정을 가져오고, 채널 탭을 만들고 제거할 수 있습니다. 

RSC 권한은 Azure AD가 아니라 앱 매니페스트에서 정의 됩니다. 앱을 팀에 추가할 때 RSC 권한에 대 한 동의를 부여 합니다. 자세한 내용은 [RSC (리소스 관련 승인)](https://docs.microsoft.com/microsoftteams/platform/graph-api/rsc/resource-specific-consent)를 참조 하세요.

전역 관리자 및 팀 서비스 관리자는 앱 세부 정보 페이지의 **사용 권한** 탭에서 앱에 대 한 RSC 권한을 볼 수 있습니다. 

앱에 대 한 RSC 권한을 보려면 다음 단계를 수행 합니다.

1. Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **팀 앱**으로  >  **앱 관리**로 이동 합니다.
2. 원하는 앱을 검색 하 고 앱 이름을 클릭 하 여 앱 세부 정보 페이지로 이동한 다음 **사용 권한** 탭을 선택 합니다.
3. **Microsoft Graph (리소스 관련 승인) 사용 권한**아래에서 앱에 의해 요청 된 rsc 권한을 검토 합니다.

    :::image type="content" source="media/app-perm-admin-center-rsc.png" alt-text="앱에 대 한 RSC 권한 스크린샷":::

## <a name="known-issues"></a>알려진 문제

### <a name="the-view-details-link-isnt-displayed-in-the-permissions-column-for-some-third-party-apps-that-request-permissions"></a>"자세히 보기" 링크가 사용 권한을 요청 하는 일부 타사 앱에 대 한 사용 권한 열에 표시 되지 않습니다.

현재 사용 권한을 요청 하는 Azure AD에 등록 된 모든 타사 앱에 대 한 권한 부여 및 동의 허용 기능을 사용할 수 없습니다. **세부 정보 보기** 링크 대신 **--** **사용 권한** 열에 표시 됩니다. Isv와 협력 하 여 앱에 대해이 기능을 사용 하도록 설정 하 고 있습니다.

## <a name="related-topics"></a>관련 항목

- [Microsoft 팀 관리 센터에서 앱 관리](manage-apps.md)
- [Microsoft id 플랫폼 끝점의 사용 권한 및 승인](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent)
- [팀의 자원 관련 승인](resource-specific-consent.md)
- [RSC (리소스 관련 승인)](https://docs.microsoft.com/microsoftteams/platform/graph-api/rsc/resource-specific-consent)
- [팀 앱 수명 주기 탐색](https://aka.ms/PR132) (Ignite 2020 세션)


