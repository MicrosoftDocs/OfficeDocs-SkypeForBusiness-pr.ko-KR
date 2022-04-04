---
title: 모든 Teams 앱에 대한 액세스 Microsoft 365
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
description: 모든 Teams 앱에 대한 액세스를 Microsoft 365.
ms.openlocfilehash: 981dd4a36cad46085aa7e620ea893f5b62bbaa96
ms.sourcegitcommit: 9e868a155bcd20dd5dafdedcff091ff77ca7398b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/31/2022
ms.locfileid: "64584323"
---
# <a name="manage-access-to-teams-apps-across-microsoft-365"></a>모든 Teams 앱에 대한 액세스 Microsoft 365

앱 개발자는 Microsoft Teams 앱을 업데이트하여 Outlook Office.com에서 작업할 수 Teams. 최종 사용자는 업데이트 후 Microsoft Teams 및 Outlook Microsoft Office.com에서 업데이트된 앱을 사용할 수 있습니다. 현재 대상 릴리스의 최종 사용자만 이러한 특정 앱을 Teams, Outlook 및 Office.com에서 볼 수 있습니다. 기존 Teams 관리 환경이 이러한 앱에 대한 액세스를 제어하는 데 적용됩니다. 이 변경에 대한 알림은 메시지 센터 [에서 사용할 수 있습니다](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter/:/messages/MC334280). Teams 관리자로서 특정 최종 사용자가 업데이트된 앱을 사용하거나 업데이트된 앱에 대한 액세스를 Teams, Outlook 및 Office.com에서 관리할 수 있습니다. Teams 관리자는 관리자 Teams 관리 센터를 사용하여 앱 액세스를 관리합니다.

Outlook 및 Office.com에서 사용하려면 업데이트된 앱이 계속 사용자에 부여된 기존 권한을 Teams. 업데이트 [된 앱의 사용 권한은 변경되지 않습니다](https://devblogs.microsoft.com/microsoft365dev/ignite-2021-building-apps-for-collaboration-in-a-hybrid-world/#personal-tabs).

다음 메서드를 사용하여 Teams 앱에 대한 최종 사용자 액세스를 제어할 수 있습니다. 앱 관리자인 Office 글로벌 관리자 또는 Teams 관리자에게 문의하여 앱 액세스를 관리합니다.

| 액세스 관리 옵션 |포털|전역 관리자|Teams 관리자|
|--|---|---|--|
| 대상 릴리스의 최종 사용자만 새 앱에 액세스할 수 있습니다. 사용자를 표준 릴리스로 이동합니다. 표준 [또는](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true) 대상 릴리스 옵션 설정 참조 | Microsoft 365 관리 센터 | 예 | 아니요 |
| 특정 최종 사용자의 새 앱에 대한 액세스를 관리합니다. 사용자 [지정 권한 정책 추가를 참조](teams-app-permission-policies.md#create-a-custom-app-permission-policy) 하고 사용자 지정 정책을 [사용자에게 할당합니다](policy-assignment-overview.md). | Teams 관리 센터 | 예 | 예 |
| 조직 전체의 모든 최종 사용자에 대한 새 앱에 대한 액세스를 관리합니다. 앱 [허용 또는 차단을 참조하세요](manage-apps.md#allow-and-block-apps). | Teams 관리 센터 | 예 | 예 |

> [!NOTE]
> 표준 [릴리스 옵션을](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true) 사용하여 최종 사용자 액세스를 관리하는 것이 좋습니다. 다른 옵션은 최종 사용자 액세스를 제거하고 더 이상 기존 앱을 사용할 수 Teams.

> [!NOTE]
> 동일한 앱의 기존 시장 내 추가 기능을 Outlook Office 사용자는 해당 앱을 계속 사용할 수 있습니다. 추가 기능은 앱에 Teams 아니며 Teams 관리자가 액세스를 제어할 수 없습니다.

다음은 여러 표면에서 작동되는 업데이트된 앱 Microsoft 365 있습니다.

* [벽화](https://teams.microsoft.com/l/app/c738b607-88dd-4f16-aefe-6a824c65d25d?source=app-details-dialog)
* [SurveyMonkey](https://teams.microsoft.com/l/app/0fd925a0-357f-4d25-8456-b3022aaa41a9?source=app-details-dialog)

## <a name="see-also"></a>참고 항목

* [관리자 역할 이해 Microsoft 365](/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide&preserve-view=true)  
* [추가 Outlook 정보를 제공합니다.](/office/dev/add-ins/outlook/outlook-add-ins-overview)
* [개발자가 여러 Teams 앱을 확장하는 Microsoft 365](/microsoftteams/platform/m365-apps/overview)
