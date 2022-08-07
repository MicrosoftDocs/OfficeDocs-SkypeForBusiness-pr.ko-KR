---
title: Microsoft 365에서 Teams 앱에 대한 액세스 관리
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
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: high
search.appverid: MET150
description: Microsoft 365에서 Teams 앱에 대한 액세스를 관리하는 방법을 알아보세요.
ms.openlocfilehash: 114b16dad2a574b217ebc9bf815f42e579b740e8
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271413"
---
# <a name="manage-access-to-teams-apps-across-microsoft-365"></a>Microsoft 365에서 Teams 앱에 대한 액세스 관리

앱 개발자는 Teams에서 작동하는 앱 외에도 Outlook 및 Office.com에서 작동하도록 Microsoft Teams 앱을 개선할 수 있습니다. 최종 사용자는 향상된 후 Teams, Microsoft Outlook 및 Microsoft Office.com에서 향상된 앱을 사용할 수 있습니다. 현재 Targeted 릴리스의 최종 사용자만 Teams, Outlook 및 Office.com에서 이러한 특정 앱을 보고 사용할 수 있습니다. 기존 Teams 관리 환경은 이러한 앱에 대한 액세스를 제어하는 ​​데 적용됩니다. 이 변경 내용에 대한 알림은 [메시지 센터](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter/:/messages/MC334280)에서 확인할 수 있습니다. Teams 관리자는 특정 최종 사용자가 Teams, Outlook 및 Office.com에서 향상된 앱을 사용하거나 향상된 앱에 대한 액세스를 관리하도록 허용할 수 있습니다. Teams 관리자는 Teams 관리 센터를 사용하여 앱 액세스를 관리합니다.

Outlook 및 Office.com에서 사용하기 위해 향상된 앱은 Teams에서 부여된 기존 권한을 계속 사용합니다. [향상된 앱의 권한에는 변경 사항이 없습니다](https://devblogs.microsoft.com/microsoft365dev/ignite-2021-building-apps-for-collaboration-in-a-hybrid-world/#personal-tabs).

다음은 향상된 앱 목록입니다.

* [Monday.com](https://teams.microsoft.com/l/app/eab2d3ce-6d6a-4415-abc4-5f40a8317b1f)
* [Mural](https://teams.microsoft.com/l/app/c738b607-88dd-4f16-aefe-6a824c65d25d)
* [Power BI](https://teams.microsoft.com/l/app/1c4340de-2a85-40e5-8eb0-4f295368978b)
* [SurveyMonkey](https://teams.microsoft.com/l/app/0fd925a0-357f-4d25-8456-b3022aaa41a9)
* [Zoho Projects](https://teams.microsoft.com/l/app/4a39aea9-8537-4c2f-b66d-ca364eb3b80d)
* [YouTube](https://teams.microsoft.com/l/app/com.microsoft.teamspace.tab.youtube)

다음 방법을 사용하여 Teams 앱에 대한 최종 사용자 액세스를 제어할 수 있습니다. Office 앱 관리자인 경우 전역 관리자 또는 Teams 관리자에게 문의하여 앱 액세스를 관리하세요.

| 액세스 관리 옵션 |Portal|전역 관리자|Teams 관리자|
|--|---|---|--|
| 대상 지정된 릴리스의 최종 사용자만 새 앱에 액세스할 수 있습니다. 사용자를 표준 릴리스로 이동합니다. [표준 또는 대상 출시 옵션 설정](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true)을 참조하세요. | Microsoft 365 관리 센터 | 예 | 아니요 |
| 특정 최종 사용자의 새 앱에 대한 액세스를 관리합니다. [사용자 지정 권한 정책 추가](teams-app-permission-policies.md#create-a-custom-app-permission-policy) 및 [사용자에게 사용자 지정 정책 할당](policy-assignment-overview.md)을 참조하세요. | Teams 관리 센터 | 예 | 예 |
| 조직 전체의 모든 최종 사용자에 대한 새 앱에 대한 액세스를 관리합니다. [앱 허용 또는 차단](manage-apps.md#allow-and-block-apps)을 참조하세요. | Teams 관리 센터 | 예 | 예 |

> [!NOTE]
> 최종 사용자 액세스를 관리하려면 [표준 릴리스 옵션](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true)을 사용하는 것이 좋습니다. 다른 옵션은 최종 사용자 액세스를 제거하며 더 이상 Teams에서 기존 앱을 사용할 수 없습니다.

> [!NOTE]
> Outlook 및 Office에 동일한 앱의 기존 시장 내 추가 기능을 설치한 사용자는 해당 앱을 계속 사용합니다. 추가 기능은 Teams 앱이 아니며 Teams 관리자는 액세스를 제어할 수 없습니다.

## <a name="see-also"></a>참고 항목

* [Microsoft 365용으로 설계된 Microsoft Teams 앱은 Outlook 및 Office.com에서 미리 보기로 제공됩니다.](https://techcommunity.microsoft.com/t5/microsoft-365-blog/microsoft-teams-apps-designed-for-microsoft-365-coming-in/ba-p/3269538)
* [Microsoft 365의 관리자 역할 이해](/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide&preserve-view=true)  
* [Outlook 추가 기능 정보](/office/dev/add-ins/outlook/outlook-add-ins-overview)
* [개발자가 Microsoft 365에서 작동하도록 Teams 앱을 확장하는 방법](/microsoftteams/platform/m365-apps/overview)
