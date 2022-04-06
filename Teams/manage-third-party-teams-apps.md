---
title: Microsoft 365 Teams 앱에 대한 액세스 관리
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.reviewer: v-tbasra
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Microsoft 365 Teams 앱에 대한 액세스를 관리합니다.
ms.openlocfilehash: 336c550c4fdf506898d6471cb618652fada95a4f
ms.sourcegitcommit: c2a77ef9c1c9e6f00b3a4589bf02b100c37f5801
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2022
ms.locfileid: "64648987"
---
# <a name="manage-access-to-teams-apps-across-microsoft-365"></a>Microsoft 365 Teams 앱에 대한 액세스 관리

앱 개발자는 Teams 작동하는 앱 외에도 Outlook 및 Office.com에서 작동하도록 Microsoft Teams 앱을 향상시킬 수 있습니다. 최종 사용자는 개선된 후에 Microsoft Outlook 및 Microsoft Office.com에서 Teams 향상된 앱을 사용할 수 있습니다. 현재 대상 릴리스의 최종 사용자만 Teams, Outlook 및 Office.com에서 이러한 특정 앱을 보고 사용할 수 있습니다. 기존 Teams 관리자 환경은 이러한 앱에 대한 액세스를 제어하는 데 적용됩니다. 이 변경에 대한 알림은 [메시지 센터에서](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter/:/messages/MC334280) 사용할 수 있습니다. Teams 관리자는 특정 최종 사용자가 향상된 앱을 사용하거나 Teams, Outlook 및 Office.com에서 향상된 앱에 대한 액세스를 관리하도록 허용할 수 있습니다. Teams 관리자는 Teams 관리 센터를 사용하여 앱 액세스를 관리합니다.

Outlook 및 Office.com에서 사용하기 위해 향상된 앱은 Teams 부여된 기존 권한을 계속 사용합니다. [향상된 앱의 권한은 변경되지 않습니다](https://devblogs.microsoft.com/microsoft365dev/ignite-2021-building-apps-for-collaboration-in-a-hybrid-world/#personal-tabs).

다음은 향상된 앱 목록입니다.

* [벽화](https://teams.microsoft.com/l/app/c738b607-88dd-4f16-aefe-6a824c65d25d?source=app-details-dialog)
* [Power BI](https://teams.microsoft.com/l/app/1c4340de-2a85-40e5-8eb0-4f295368978b?source=app-details-dialog)
* [SurveyMonkey](https://teams.microsoft.com/l/app/0fd925a0-357f-4d25-8456-b3022aaa41a9?source=app-details-dialog)
* [Zoho 프로젝트](https://teams.microsoft.com/l/app/4a39aea9-8537-4c2f-b66d-ca364eb3b80d?source=app-details-dialog)
* [YouTube](https://teams.microsoft.com/l/app/com.microsoft.teamspace.tab.youtube?source=app-details-dialog)

다음 방법을 사용하여 Teams 앱에 대한 최종 사용자 액세스를 제어할 수 있습니다. Office 앱 관리자인 경우 전역 관리자 또는 Teams 관리자에게 문의하여 앱 액세스를 관리합니다.

| 액세스를 관리하는 옵션 |포털|전역 관리자|Teams 관리자|
|--|---|---|--|
| 대상 릴리스의 최종 사용자만 새 앱에 액세스할 수 있습니다. 사용자를 표준 릴리스로 이동합니다. [표준 또는 대상 릴리스 옵션 설정](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true) 참조 | Microsoft 365 관리 센터 | 예 | 아니요 |
| 특정 최종 사용자에 대한 새 앱에 대한 액세스를 관리합니다. [사용자 지정 권한 정책 추가](teams-app-permission-policies.md#create-a-custom-app-permission-policy) 및 [사용자 지정 정책 할당을 참조하세요](policy-assignment-overview.md). | Teams 관리 센터 | 예 | 예 |
| 조직 전체의 모든 최종 사용자에 대한 새 앱에 대한 액세스를 관리합니다. [앱 허용 또는 차단](manage-apps.md#allow-and-block-apps)을 참조하세요. | Teams 관리 센터 | 예 | 예 |

> [!NOTE]
> [표준 릴리스 옵션을](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true) 사용하여 최종 사용자 액세스를 관리하는 것이 좋습니다. 다른 옵션은 최종 사용자 액세스를 제거하고 더 이상 Teams 기존 앱을 사용할 수 없습니다.

> [!NOTE]
> Outlook 및 Office 동일한 앱의 기존 시장 내 추가 기능을 설치한 사용자는 해당 앱을 계속 사용합니다. 추가 기능은 Teams 앱이 아니며 Teams 관리자가 액세스를 제어할 수 없습니다.

## <a name="see-also"></a>참고 항목

* [Outlook 및 Office.com에 미리 보기로 제공되는 Microsoft 365 위해 설계된 Microsoft Teams 앱](https://techcommunity.microsoft.com/t5/microsoft-365-blog/microsoft-teams-apps-designed-for-microsoft-365-coming-in/ba-p/3269538)
* [Microsoft 365 관리자 역할 이해](/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide&preserve-view=true)  
* [Outlook 추가 기능 정보](/office/dev/add-ins/outlook/outlook-add-ins-overview)
* [개발자가 Teams 앱을 확장하여 Microsoft 365](/microsoftteams/platform/m365-apps/overview)
