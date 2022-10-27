---
title: Microsoft 365에서 Teams 앱에 대한 액세스 관리
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-apps
audience: Admin
ms.date: 10/24/2022
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: high
search.appverid: MET150
description: Microsoft 365에서 Teams 앱에 대한 액세스를 관리하는 방법을 알아보세요.
ms.openlocfilehash: 01aee1ebd59b52f05db36303d60358b86b95cf84
ms.sourcegitcommit: c2d8c7f779f4f938f8355632ecfbfc9147b53bb2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2022
ms.locfileid: "68738804"
---
# <a name="manage-access-to-teams-apps-across-microsoft-365"></a>Microsoft 365에서 Teams 앱에 대한 액세스 관리

앱 개발자는 Teams에서 작동하는 앱 외에도 Outlook 및 Office.com에서 작동하도록 Microsoft Teams 앱을 개선할 수 있습니다. 최종 사용자는 향상된 후 Teams, Microsoft Outlook 및 Microsoft Office.com에서 향상된 앱을 사용할 수 있습니다. 현재 [대상 지정 릴리스](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true) 의 최종 사용자만 Teams, Outlook 및 Office.com 이러한 특정 앱을 보고 사용할 수 있습니다. 이 변경 내용에 대한 알림은 [메시지 센터](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter/:/messages/MC334280)에서 확인할 수 있습니다.

## <a name="manage-users-access-to-the-enhanced-apps"></a>향상된 앱에 대한 사용자의 액세스 관리

기존 Teams 관리 환경은 이러한 앱에 대한 액세스를 제어하는 ​​데 적용됩니다. Teams 관리자는 Teams 관리 센터를 사용하여 앱 액세스를 관리합니다. Teams 관리자는 특정 최종 사용자가 Teams, Outlook 및 Office.com에서 향상된 앱을 사용하거나 향상된 앱에 대한 액세스를 관리하도록 허용할 수 있습니다.

Outlook 및 Office.com에서 사용하기 위해 향상된 앱은 Teams에서 부여된 기존 권한을 계속 사용합니다. 향상된 앱의 권한은 변경되지 않습니다. Outlook 및 Office에서 동일한 앱의 기존 시장 내 추가 기능을 설치한 사용자는 계속해서 해당 앱을 사용합니다. 추가 기능은 Teams 앱이 아니며 Teams 관리자는 액세스를 제어할 수 없습니다.

Office Apps 관리자는 전역 관리자 또는 Teams 관리자에게 문의하여 향상된 앱의 액세스를 관리할 수 있습니다. 자세한 내용은 [Microsoft 365의 관리자 역할을 참조하세요](/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide&preserve-view=true).

다음 방법을 사용하여 최종 사용자 액세스를 제어할 수 있습니다.

| 액세스 관리 옵션 |Portal|전역 관리자|Teams 관리자|
|--|---|---|--|
| 대상 지정된 릴리스의 최종 사용자만 새 앱에 액세스할 수 있습니다. 사용자를 표준 릴리스로 이동합니다. [표준 또는 대상 출시 옵션 설정](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true)을 참조하세요. | Microsoft 365 관리 센터 | 예 | 아니요 |
| 특정 최종 사용자의 새 앱에 대한 액세스를 관리합니다. [사용자 지정 권한 정책 추가](teams-app-permission-policies.md#create-an-app-permission-policy) 및 [사용자에게 사용자 지정 정책 할당](policy-assignment-overview.md)을 참조하세요. | Teams 관리 센터 | 예 | 예 |
| 조직 전체의 모든 최종 사용자에 대한 새 앱에 대한 액세스를 관리합니다. [앱 허용 또는 차단](manage-apps.md#allow-and-block-apps)을 참조하세요. | Teams 관리 센터 | 예 | 예 |

> [!NOTE]
> 최종 사용자 액세스를 관리하려면 [표준 릴리스 옵션](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true)을 사용하는 것이 좋습니다. 다른 옵션은 최종 사용자 액세스를 제거하며 더 이상 Teams에서 기존 앱을 사용할 수 없습니다.

## <a name="list-of-enhanced-apps"></a>향상된 앱 목록

향상된 앱 목록은 다음과 같습니다.

* [Adobe Acrobat Sign](https://teams.microsoft.com/l/app/0f56a9d1-f502-40f9-a9e8-816d7adbb68b?source=app-details-dialog)
* [더 큰 두뇌 eLearning](https://teams.microsoft.com/l/app/12345514-afee-abcd-acde-c5b34109abcd?source=app-details-dialog)
* [Bookings](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=app-details-dialog)
* [e2e-assure](https://teams.microsoft.com/l/app/8bdf3437-e038-4a93-abdc-00461630f6c3?source=app-details-dialog)
* [ESi-Tik](https://teams.microsoft.com/l/app/fe9627db-f23e-42b1-b454-d4d1ca5af33e?source=app-details-dialog)
* [렌즈](https://teams.microsoft.com/l/app/cfaeb687-adc7-4e36-a847-39bb35bfb631?source=app-details-dialog)
* [Monday.com](https://teams.microsoft.com/l/app/eab2d3ce-6d6a-4415-abc4-5f40a8317b1f)
* [Mural](https://teams.microsoft.com/l/app/c738b607-88dd-4f16-aefe-6a824c65d25d)
* [내 스티커](https://teams.microsoft.com/l/app/46fae4d0-faf5-11e9-80f3-53ad33b77bce?source=app-details-dialog)
* [PDF 도구](https://teams.microsoft.com/l/app/ca4b5141-5c46-47bc-a05e-2733d9bd69aa?source=app-details-dialog)
* [Power BI](https://teams.microsoft.com/l/app/1c4340de-2a85-40e5-8eb0-4f295368978b)
* [Priority Matrix](https://teams.microsoft.com/l/app/5be2b320-a5b7-4221-893c-dee506e4e365?source=app-details-dialog)
* [Jira용 Smart Connect](https://teams.microsoft.com/l/app/6402de97-ce33-4386-bf28-b37e9e139c09?source=app-details-dialog)
* [곧 예약](https://teams.microsoft.com/l/app/bf280b0d-b87d-4158-9f2a-70b63674cd27?source=app-details-dialog)
* [간소화](https://teams.microsoft.com/l/app/aa6e7fb6-34ac-4947-9c13-3565c66e368b?source=app-details-dialog)
* [SurveyMonkey](https://teams.microsoft.com/l/app/0fd925a0-357f-4d25-8456-b3022aaa41a9)
* [전사 도우미 TNA2](https://teams.microsoft.com/l/app/32c31ccd-b878-470e-9259-98c079ae5528?source=app-details-dialog)
* [움비코 주](https://teams.microsoft.com/l/app/23fc1de6-dda0-4043-9ebb-a555e845843d?source=app-details-dialog)
* [왈도](https://teams.microsoft.com/l/app/1d041f16-ab49-4627-bfda-6b60ad2cab6a?source=app-details-dialog)
* [YouTube](https://teams.microsoft.com/l/app/com.microsoft.teamspace.tab.youtube)
* [Zoho Projects](https://teams.microsoft.com/l/app/4a39aea9-8537-4c2f-b66d-ca364eb3b80d)

## <a name="related-articles"></a>관련 기사

* [Microsoft 365용으로 설계된 Microsoft Teams 앱은 Outlook 및 Office.com에서 미리 보기로 제공됩니다.](https://techcommunity.microsoft.com/t5/microsoft-365-blog/microsoft-teams-apps-designed-for-microsoft-365-coming-in/ba-p/3269538)
* [Microsoft 365의 관리자 역할 이해](/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide&preserve-view=true)  
* [Outlook 추가 기능 정보](/office/dev/add-ins/outlook/outlook-add-ins-overview)
* [개발자가 Microsoft 365에서 작동하도록 Teams 앱을 확장하는 방법](/microsoftteams/platform/m365-apps/overview)
