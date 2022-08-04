---
title: Microsoft Teams 관리 센터에서 앱 관리
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
ms.subservice: teams-apps
ms.custom: intro-get-started
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: vaibhava
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.manageapps.overview
description: Teams 앱을 관리하는 방법을 알아봅니다. 앱 허용 또는 차단, 조직 수준 상태 및 앱 속성 확인, 사용자 지정 앱 업로드 및 앱 설정 관리에 대해 알아봅니다.
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: 51874c55cf9a3e6dd77af40447dcaf6d21932668
ms.sourcegitcommit: a64574da14969a33a77c7d979ffde452b5b3a531
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/02/2022
ms.locfileid: "67175682"
---
# <a name="manage-teams-apps-in-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터에서 Teams 앱 관리

Teams 관리 센터 포털의 **Teams 앱** 페이지에서 조직의 앱을 관리합니다. 앱 관리 페이지에서 조직의 앱 카탈로그에 있는 모든 Teams 앱을 보고 관리하며, 앱 관리에 대한 주요 사용 사례에 맞추고, 정책을 통해 앱에 대한 액세스를 정의하는 등의 작업을 수행할 수 있습니다.

:::image type="content" source="media/manage-apps.png" alt-text="앱 관리 페이지 스크린샷" lightbox="media/manage-apps.png":::

앱을 관리하려면 정책을 사용하여 사용자 사용 권한, 앱 설치 및 조직 내에서 생성된 사용자 지정 앱 업로드를 제어합니다. 정책을 이해하려면 [앱 정책 개요](app-policies.md)를 참조하세요.

Teams 관리 센터를 사용하려면 전역 관리자 또는 Teams 관리자 역할이 있어야 합니다. 자세한 내용은 [Teams 관리자 역할](./using-admin-roles.md) 및 [Microsoft 365 관리자 역할](/microsoft-365/admin/add-users/about-admin-roles)을 참조하세요.

> [!NOTE]
> 앱 관리 페이지는 Teams의 Microsoft 365 GCCH(정부 커뮤니티 클라우드 High) 또는 DoD(미국방부) 배포에서 사용할 수 없습니다.

앱을 만드는 동안 개발자는 앱 ID를 생성하고 매니페스트 파일에 추가합니다. 열 설정에서 `External app ID` 열을 사용하도록 설정한 후 앱 관리 페이지에서 이 외부 앱 ID를 볼 수 있습니다. 사용자 지정 앱의 앱 세부 정보 페이지에서도 볼 수 있습니다. ID는 사용자 지정 앱에만 적용됩니다.

## <a name="app-management-use-cases-and-the-available-interfaces"></a>앱 관리 사용 사례 및 사용 가능한 인터페이스

대부분의 앱 관리 사용 사례를 수행하는 옵션은 Teams 관리 센터에서 사용할 수 있습니다. 또한 일부 옵션은 다른 포털 또는 동일한 포털의 다른 관리 센터 페이지에서 사용할 수 있습니다.

| 앱 관리 사용 사례 | 인터페이스에 연결 | 설명서 |
|:----|:----|:----|
| **Teams 관리 센터에서** | | |
| 앱을 허용 및 차단하여 조직의 사용자가 사용할 수 있는 프로그램을 제어합니다. 사용자 지정 앱을 업로드하고 승인할 수도 있습니다. 이 페이지에서 앱을 관리한 후 앱 사용 권한 및 앱 설정 정책을 사용하여 조직의 앱 저장소에서 특정 사용자가 사용할 수 있는 앱을 구성할 수 있습니다. | [Teams 관리 센터에서 앱 관리](https://admin.teams.microsoft.com/policies/manage-apps) | 현재 문서 |
| 앱 사용 권한 정책은 조직의 Teams 사용자가 사용할 수 있는 앱을 제어합니다. 전역(조직 전체) 기본 정책을 사용하고 사용자 지정하거나 혹은 조직의 요구 사항을 충족하는 하나 이상의 정책을 만들 수 있습니다. | [사용 권한 정책](https://admin.teams.microsoft.com/policies/app-permission) | [앱 사용 권한 정책 관리](teams-app-permission-policies.md) |
| 앱 설정 정책은 Teams 앱을 사용하여 사용자가 앱을 사용할 수 있도록 하는 방법을 제어합니다. 전역(조직 전체 기본값) 정책을 사용하여 사용자 지정하거나 사용자 지정 정책을 만들어 사용자 집합에 할당합니다. | [정책 설정](https://admin.teams.microsoft.com/policies/app-setup) | [앱 설정 정책 관리](teams-app-setup-policies.md) |
| 사용자 지정 앱을 앱 패키지로 개발 및 업로드하고 조직의 앱 스토어에서 사용할 수 있도록 할 수 있습니다. | [앱 관리](https://admin.teams.microsoft.com/policies/manage-apps)의 조직 전체 앱 설정 | [사용자 지정 앱 정책 관리](teams-custom-app-policies-and-settings.md) |
| 조직의 로고, 사용자 지정 배경 또는 색상으로 Teams 앱 스토어를 사용자 지정할 수 있습니다. | [저장소 사용자 지정](https://admin.teams.microsoft.com/policies/customize-appstore) | [조직의 앱 스토어 사용자 지정](customize-your-app-store.md) |
| Teams 앱 사용 현황 보고서는 사용 중인 앱, 활성 사용자 및 기타 앱 사용 정보에 관한 정보를 제공합니다. | [사용 현황 보고서](https://admin.teams.microsoft.com/analytics/reports) | [Teams 앱 사용 현황 보고서](teams-analytics-and-reports/app-usage-report.md) |
| 사용자는 게스트와의 모임을 호스트하거나 게스트와 채팅할 때 앱을 추가할 수 있습니다. 외부에서 호스트되는 모임이나 채팅에 참여할 때 게스트가 공유하는 앱을 사용할 수도 있습니다. 호스팅 사용자 조직의 데이터 정책과 해당 사용자 조직에서 공유하는 타사 앱의 데이터 공유 사례가 적용됩니다. | [외부 액세스](https://admin.teams.microsoft.com/company-wide-settings/external-communications) | [사용자 유형에 따른 앱 동작](non-standard-users.md) |
| 게스트 액세스를 사용하면 회사 데이터에 대한 제어권을 유지하면서 조직 외부 사용자에게 응용 프로그램 및 기타 Teams 기능에 대한 액세스를 제공할 수 있습니다. | [게스트 액세스](https://admin.teams.microsoft.com/company-wide-settings/guest-configuration) | [Teams의 게스트 액세스](guest-access.md) |
| 업데이트 정책은 Teams 앱의 시험판 또는 미리 보기 기능을 볼 수 있는 Teams 및 Office 미리 보기 사용자를 관리하는 데 사용됩니다.  | [Teams 업데이트 정책](https://admin.teams.microsoft.com/policies/updatemanagement) | [Teams 공개 미리 보기](public-preview-doc-updates.md) |
| **Teams 관리 센터 외부** | | |
| Microsoft 365 관리 센터에서 타사 앱의 라이선스와 구독을 관리합니다. | [Microsoft 365 관리 센터](https://admin.microsoft.com/#/licenses) | [타사 앱 구독 관리](/microsoft-365/commerce/manage-saas-apps) |
| Microsoft Purview 규정 준수 포털에서 Teams 앱 이벤트를 감사합니다. | [감사](https://compliance.microsoft.com/auditlogsearch?viewid=Async%20Search) | [Teams 활동](audit-app-management-activities.md) |
| 응용 프로그램은 다음 세 가지 방법으로 조직 및 해당 데이터에 대한 사용 권한을 부여할 수 있습니다. 관리자가 모든 사용자에 대한 응용 프로그램에 동의하거나, 사용자가 응용 프로그램에 동의하거나, 관리자가 응용 프로그램을 통합하여 셀프 서비스 액세스를 활성화하거나 사용자를 응용 프로그램에 직접 할당하여 권한을 부여할 수 있습니다. 앱에 대한 그래프 권한을 확인합니다. 사용자가 제공했거나 관리자가 위임한 사용 권한을 확인합니다. | [Azure AD 포털](https://aad.portal.azure.com/) | [응용 프로그램에 부여된 사용 권한 검토](/azure/active-directory/manage-apps/manage-application-permissions) |

<!---
| xxx | [Manage users](https://admin.teams.microsoft.com/users) | [Add users and assign licenses](/microsoft-365/admin/add-users/add-users?view=o365-worldwide) |  
--->

## <a name="allow-and-block-apps"></a>앱 허용 및 차단

앱 관리 페이지에서는 조직 수준에서 개별 앱을 허용하거나 차단할 수 있습니다. 페이지에 사용 가능한 모든 앱과 현재 조직 수준 앱 상태가 표시됩니다. 앱 목록에는 Microsoft, 타사 개발자 및 조직 내 개발자가 제공하는 앱이 포함됩니다.

앱을 허용하거나 차단하려면 다음을 수행합니다.

1. Teams 관리 센터에 로그인합니다.
1. **Teams 앱** > **[앱 관리](https://admin.teams.microsoft.com/policies/manage-apps)** 페이지에 액세스합니다.
1. 앱 목록에서 앱을 선택합니다. 앱 이름으로 검색한 다음 선택할 수 있습니다.
1. **허용** 또는 **차단** 옵션을 선택합니다.

Teams 관리 센터의 [앱 관리](https://admin.teams.microsoft.com/policies/manage-apps) 페이지에서 앱을 허용(또는 차단)하면 조직의 모든 사용자에게 특정 앱이 허용(또는 차단)됩니다. 이 방법은 사용 권한 정책을 통해 앱을 허용(또는 차단)하면 정책이 할당된 특정 사용자에게만 영향을 미친다는 점에서 앱 사용 권한 정책과 다릅니다.

테넌트 전체 설정을 통해 앱이 허용되고 사용 권한 정책을 통해 사용자에게 허용되는 경우에만 사용자가 앱을 설치하고 사용할 수 있습니다.

## <a name="manage-user-requests-to-unblock-apps"></a>앱 차단을 해제하기 위한 사용자 요청 관리

차단된 앱을 사용할 수 있도록 하는 요청을 볼 수 있습니다. 요청은 Teams 관리 센터에서 사용자 요청을 보고 관리할 수 있는 IT 관리자에게 전송됩니다.

  :::image type="content" source="media/user-request.png" alt-text="차단된 앱 승인 요청하기":::

### <a name="view-a-request"></a>요청 보기

 1. Teams 관리 센터에 로그인하고 [앱 관리](https://admin.teams.microsoft.com/policies/manage-apps)를 선택합니다.

    :::image type="content" source="media/requested-apps1.png" alt-text="차단된 앱에 대한 최종 사용자 요청은 Teams 관리 센터의 사용자 요청 열에 표시됩니다." lightbox="media/requested-apps.png":::

 1. 각 앱의 요청 수를 보고 확인하려면 **사용자별 요청** 열에 요청을 정렬합니다.
 1. 차단을 해제할 앱의 이름을 선택하면 앱 세부 정보 페이지가 열립니다.
 1. **요청 관리** 를 선택하고 팝업 대화 상자에 표시된 단계를 완료합니다. 앱을 승인하는 단계는 앱을 차단하는 방법에 따라 다릅니다.

    * 사용 권한 정책을 통해 앱이 차단된 경우 [사용 권한 정책](teams-app-permission-policies.md)을 수정하여 앱을 허용합니다.
    * 모든 사용자에 대해 앱이 차단된 경우 [앱을 허용](#allow-and-block-apps)합니다.
    * 모든 사용자에 대해 모든 앱이 차단된 경우 [조직 전체 설정](#manage-org-wide-app-settings)을 수정합니다.

 관리자가 앱을 허용하면 최종 사용자에게 요청이 수행되었음을 알리지 않습니다. 스토어에서 앱을 방문하여 앱 차단 해제 여부를 확인해야 합니다.

### <a name="dismiss-a-user-request"></a>사용자 요청 거부

 1. 사용자 요청을 거부할 앱의 이름을 선택합니다.
 1. **요청 관리** 를 선택하고 대화 상자에서 **모든 요청 거부** 를 선택합니다.
 1. 요청이 거부되면 사용자 요청을 0으로 설정합니다.

  :::image type="content" source="media/reject.png" alt-text="차단된 앱 거부"border="true":::

관리자가 요청을 거부해도 최종 사용자에게 요청이 수행되었음을 알리지 않습니다. 스토어에서 앱을 방문하여 앱 차단 해제 여부를 확인해야 합니다.

## <a name="allow-the-apps-that-are-blocked-by-the-developers"></a>개발자가 차단한 앱을 허용합니다.

개발자가 Teams 앱 저장소에 앱을 게시할 때 앱 환경을 구성하거나 사용자 지정할 관리자가 필요할 수 있습니다. 관리자는 앱을 설정할 때 최종 사용자가 사용할 수 있는 환경을 만듭니다.

예를 들어, Contoso Electronics는 Microsoft Teams용 지원 센터 앱을 만든 ISV입니다. Contoso Electronics는 사용자가 앱과 상호 작용할 때 예상대로 작동할 수 있도록 앱의 특정 속성을 설정하기를 원합니다. 관리자가 응용 프로그램을 허용하거나 차단하기 전에, 응용 프로그램은 Teams 관리 센터에 **게시자에 의해 차단됨** 으로 표시되며, 기본적으로 최종 사용자에게 숨겨집니다. 게시자의 지침에 따라 앱을 설정한 후 상태를 **허용됨** 으로 변경하여 사용자가 앱을 사용할 수 있도록 설정할 수 있습니다.

:::image type="content" source="media/blocked-by-publisher.png" alt-text="Teams 관리 센터에서 게시자에 의해 차단됨 상태의 스크린샷":::

## <a name="manage-org-wide-app-settings"></a>조직 전체 앱 설정 관리

조직 전체 앱 설정을 사용하여 [F 라이선스](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt)를 가진 사용자가 맞춤화된 일선 앱 환경을 얻을지 여부, 타사 앱을 설치할 수 있는지 여부, 조직에서 사용자 지정 앱을 업로드하거나 상호 작용할 수 있는지 여부를 제어합니다. 조직 전체 앱 설정은 모든 사용자의 동작을 관리하고 사용자에게 할당된 다른 모든 앱 사용 권한 정책을 재정의합니다. 악의적이거나 문제가 있는 앱을 제어하는 데 사용할 수 있습니다.

> [!NOTE]
> Microsoft 365 Government(정부 커뮤니티 클라우드 High GCCH 및 DoD(미국방부)) Teams 배포에서 조직 전체 앱 설정을 사용하는 방법에 대한 자세한 내용은 [Teams에서 앱 사용 권한 정책 관리](teams-app-permission-policies.md)를 참조하세요.

1. 앱 관리 페이지에서 **조직 전체 앱 설정** 을 선택합니다. 그런 다음 창에서 원하는 설정을 구성할 수 있습니다.

    :::image type="content" source="media/manage-apps-org-wide-app-settings.png" alt-text="앱 관리 페이지의 조직 전체 앱 설정 창 스크린샷":::

1. **맞춤형 앱** 에서 **맞춤형 앱 표시** 를 끄거나 켭니다. 이 설정이 켜져 있으면 [F 라이선스](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt)가 있는 사용자는 맞춤형 최전방 앱 환경을 사용할 수 있습니다. 이 환경은 최전방 직원을 위해 Teams에서 가장 관련성이 높은 앱을 고정합니다. 자세한 내용은 [최전방 직원을 위한 맞춤형 Teams 앱](pin-teams-apps-based-on-license.md)을 참조하세요.

    이 기능은 F 라이선스에 사용할 수 있습니다. 다른 라이선스 유형은 나중에 지원될 예정입니다.
1. **타사 앱** 에서 이 설정을 끄거나 켜면 타사 앱에 대한 액세스를 제어할 수 있습니다.

    * **타사 앱 허용**: 사용자가 타사 앱을 사용할 수 있는지 여부를 제어합니다. 이 설정을 해제하면 사용자가 타사 앱을 설치하거나 사용할 수 없으며 이러한 앱의 앱 상태가 표에 **차단됨 또는 조직 전체** 로 표시됩니다.

        > [!NOTE]
        > **타사 앱 허용** 이 꺼져 있는 경우에도 [발신 웹후크](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)는 여전히 모든 사용자가 사용하도록 설정되지만 [앱 사용 권한 정책](teams-app-permission-policies.md)을 통해 발신 웹후크 앱을 허용하거나 차단하여 이를 사용자 수준에서 제어할 수 있습니다. **Microsoft 앱** 에 대해 **특정 앱 허용 및 다른 모든 앱 차단** 설정을 사용하는 기존 [앱 사용 권한 정책](teams-app-permission-policies.md)이 있고 사용자에 대해 나가는 웹후크를 사용 가능으로 설정하려면 목록에 나가는 웹후크 앱을 추가하세요.

        > [!NOTE]
        > Teams 사용자는 다른 조직의 사용자와 모임 또는 채팅을 호스트할 때 앱을 추가할 수 있습니다. 또한 해당 조직에서 호스트하는 모임 또는 채팅에 참가할 때 다른 조직의 사용자가 공유하는 앱을 사용할 수도 있습니다. 호스팅 사용자 조직의 데이터 정책과 해당 사용자 조직에서 공유하는 타사 앱의 데이터 공유 사례가 적용됩니다.

    * **기본적으로 스토어에 게시된 새 타사 앱 허용**: Teams 앱 스토어에 게시된 새 타사 앱이 Teams에서 자동으로 제공될지 여부를 제어합니다. 타사 앱을 허용하는 경우에만 이 옵션을 설정할 수 있습니다.

1. **사용자 지정 앱** 에서 **사용자 지정 앱과의 상호 작용 허용** 을 끄거나 켭니다. 이 설정은 사용자가 사용자 지정 앱과 상호 작용할 수 있는지 여부를 제어합니다. 자세한 내용은 [Teams에서 사용자 지정 앱 정책 및 설정 관리](teams-custom-app-policies-and-settings.md)를 참조하세요.
1. 조직 전체 앱 설정을 적용하려면 **저장** 을 선택합니다.

## <a name="related-article"></a>관련 문서

* [비즈니스용 Skype 관리 센터에서 전환하는 동안 Teams 관리](manage-teams-skypeforbusiness-admin-center.md)
