---
title: Microsoft Teams 관리 센터에서 앱 관리
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: vaibhava
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.manageapps.overview
description: Microsoft Teams 관리 센터의 앱 관리 페이지에서 Teams 앱을 관리하는 방법 배우기
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 23ff7cc90d30dc931b0677ce5ec5aa8db98981fb
ms.sourcegitcommit: e0e089f0ab217d920e128377af653f7dbfdedacf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46818187"
---
<a name="manage-your-apps-in-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터에서 앱 관리
======================================================

관리자는 Microsoft Teams 관리 센터의 앱 관리 페이지에서 조직의 모든 Teams 앱을 보고 관리할 수 있습니다. 여기에서 앱의 조직 수준 상태 및 속성을 확인하고, 조직의 앱 스토어에 새 사용자 지정 앱을 승인 또는 업로드하고, 조직 수준에서 앱을 차단하거나 허용하고, 타사 앱에 대한 서비스를 구입하고, 조직 전체 앱 설정을 관리할 수 있습니다.

앱 관리 페이지는 사용 가능한 모든 앱에서 보기로 제공하며, 조직 전체에서 허용 또는 차단하는 앱을 결정하는 데 필요한 정보를 제공합니다. 그런 다음 앱 [사용 권한 정책, 앱 설정](teams-app-permission-policies.md) [정책,](teams-app-setup-policies.md)사용자 지정 앱 정책 및 설정을 사용하여 조직의 특정 사용자에 대한 앱 환경을 구성할 수 있습니다. [custom app policies and settings](teams-custom-app-policies-and-settings.md)

Microsoft Teams 관리 센터의 왼쪽 탐색에서 Teams 앱 관리 **앱으로**  >  **이동합니다.** 페이지에 액세스하려면 전역 관리자 또는 Teams 서비스 관리자여야 합니다.

> [!NOTE]
> Teams의 GCC(정부 커뮤니티 클라우드) 배포에서는 앱 관리 페이지를 아포게 사용할 수 없습니다.

## <a name="view-apps"></a>앱 보기

각 앱에 대한 다음 정보를 포함한 모든 앱을 볼 수 있습니다.

![관리되는 앱 페이지의 스크린샷](media/manage-apps.png)

- **이름:** 앱 이름입니다. 앱 에대한 자세한 내용을 보려면 앱 이름을 클릭합니다. 여기에는 앱에 대한 설명, 버전 의여부, 앱에 적용되는 인증 상태, 지원되는 기능, 앱 ID 등이 포함됩니다. 예를 들면 다음과 같습니다:

  ![앱에 대한 앱 세부 정보 페이지 스크린샷](media/manage-apps-app-details.png)
  
- **인증: 앱에서**인증을 통과한 경우 **Microsoft 365 인증** 또는 **Publisher 참고 시나이 올 수 있습니다.** 이 링크를 클릭하여 앱의 인증 세부 정보를 확인할 수 있습니다. **--**""가 표시되면 앱에 대한 인증 정보가 없는 경우 Teams에서 인증된 앱에 대해 자세히 알아보려면 [Microsoft 365 앱 인증 프로그램을 읽어보세요.](https://docs.microsoft.com/teams-app-certification/all-apps)  
- **퍼블리셔:** 게시자의 이름입니다.
- **게시 상태:** 사용자 지정 앱의 게시 상태입니다.
- **상태:** 태그 수준에서 앱 상태로, 다음 중 하나일 수 있습니다.

    - **허용됨:** 조직의 모든 사용자가 이 앱을 사용할 수 있습니다.
    
    - **차단됨:** 앱이 차단되어 조직의 모든 사용자가 사용할 수 없습니다.
    
    - **차단된 방향:** 앱은 전역 앱 설정에서 차단됩니다.
    
      조직 전체 설정 창에 있어 조직 전체 설정 창에 있어 차단된 앱의 허용 및 차단 상태를 **나타내는 점을 아는 중요합니다.** 이제 앱 관리 페이지의 조직 전체에서 앱을 **Manage apps** 보고 차단하고 허용합니다. 
- **라이선스:** 앱에서 구매에 대한 SaaS(Software as a Service) 구독을 제공하는지 여부를 나타내고 있습니다. 이 열은 타사 앱에만 적용됩니다. 각 타사 앱에는 다음 값 중 하나가 포함됩니다.
    - **지금 구매:** 앱에서 SaaS 구독을 제공하고 구입할 수 있습니다.  
    - **구입됨:** 앱에서 SaaS 구독을 제공하고 라이선스를 구매했습니다.
    - **-**- 앱에서 SaaS 구독을 제공하지 않습니다.
- **사용자 지정**앱: 앱이 사용자 지정 앱인지 여부
- **범주: 앱에**적용되는 범주입니다.
- **버전**: 앱 버전.

표에서 원하는 정보를 보려면 오른쪽 **Edit Column** 위 모서리에서 열 편집을 클릭하여 표에 열을 추가하거나 제거합니다.

## <a name="publish-a-custom-app-to-your-organizations-app-store"></a>조직의 앱 스토어에 사용자 지정 앱 게시

앱 관리 페이지를 사용하여 조직에 기본적으로 제공되는 앱을 게시합니다. 사용자 지정 앱을 퍼블리싱한 후에는 조직의 앱 스토어에 있는 사용자가 이 앱을 사용할 수 있습니다. 두 가지 방법으로 조직의 앱 스토어에 사용자 지정 앱을 게시할 수 있습니다. 사용하는 방법은 앱을 얻는 방법에 따라 다를 수 있습니다.

- [사용자 지정 앱 은도서히 승인:](#approve-a-custom-app)개발자가 Teams 앱 제출 API를 사용하여 앱 관리 페이지에 직접 앱을 제출하면 이 방법을 사용합니다. 그런 다음 앱 세부 정보 페이지에서 직접 앱을 검토하고 게시(또는 거부)할 수 있습니다.
- [앱 패키지를 업로드합니다.](#upload-an-app-package)개발자가 앱 패키지를 .zip 형식으로 보내면 이 메서드를 사용합니다. 앱 패키지를 업로드하여 앱을 게시합니다.

###  <a name="approve-a-custom-app"></a>사용자 지정 앱 승인

앱 **관리 페이지의 승인** 보류 중인 위젯은 개발자가 Teams 앱 제출 API를 사용하여 앱을 제출하면 이를 알립니다. 새로 제출된 앱이 제출됨의 **Publishing status** 게시 상태와 차단됨 **상태가** **표시됩니다.** **Status** 앱 세부 정보 페이지로 이동하여 앱에 대한 자세한 내용을 확인한 후 게시하려면 게시 **상태를 게시하도록 게시 상태를** **설정합니다.**

또한 개발자가 사용자 지정 앱에 업데이트를 제출하면 알림을 받습니다. 그런 다음 앱 세부 정보 페이지에서 업데이트를 검토하고 게시하거나 거부할 수 있습니다. 업데이트된 앱에 대해 모든 앱 사용 권한 정책 및 앱 설정 정책이 그대로 유지됩니다.

자세한 내용은 [Teams 앱 제출 API를 통해 제출한 사용자 지정 앱 게시를 참조하세요.](submit-approve-custom-apps.md)

### <a name="upload-an-app-package"></a>앱 패키지 업로드

개발자가 Teams 앱 [Studio를](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)사용하여 Teams 앱 패키지를 만들어 .zip 형식으로 보냅니다. 앱 패키지가 있는 경우 조직의 앱 스토어에 업로드할 수 있습니다.

새 사용자 지정 앱을 업로드하려면 업로드를 **선택하여** 앱 패키지를 업로드합니다. 앱이 업로드된 후에는 강조 표시되지 않으므로 앱 관리 페이지에서 앱 목록을 검색하여 찾어해야 합니다.

앱이 업로드된 후 업데이트하려면 앱 관리 페이지의 앱 목록에서 앱 이름을 클릭하고 **업데이트를 클릭합니다.** 이렇게 하면 기존 앱 및 모든 앱 사용 권한 정책 및 앱 설정 정책이 자동으로 변경되어 업데이트된 앱에 대해서도 유지됩니다.

자세한 내용은 앱 [패키지를 업로드하여 사용자 지정 앱 게시를 참조하세요.](upload-custom-apps.md)

## <a name="allow-and-block-apps"></a>앱 허용 및 차단

앱 관리 페이지에서는 조직 수준에서 개별 앱을 허용하거나 차단할 수 있습니다. 여기에는 사용 가능한 앱 및 현재 조직 수준 앱 상태를 표시합니다. (조직 수준에서 앱을 차단하고 허용하는 앱이 여기에 있습니다.) **Org-wide app settings**

앱을 허용하거나 차단하려면 앱을 선택한 다음 허용 또는 **차단을** **클릭합니다.** 앱을 차단하면 해당 앱과 의해 모든 상호 작용이 사용되지 않으며 조직의 사용자가 Teams에 앱이 나타나지 않습니다.

앱 관리 페이지에서 앱을 차단하거나 허용하면 해당 조직의 모든 사용자가 앱이 차단 또는 허용됩니다.  Teams 앱 사용 권한 정책에서 앱을 차단하거나 허용하면 해당 정책이 할당된 사용자에게 앱이 차단 또는 허용됩니다. 사용자가 앱을 설치하고 상호 작용할 수 있도록 하려면 앱 관리 페이지의 조직 수준 및 사용자에게 할당된 앱 사용 권한 정책에서 앱을 허용해야 합니다.

 > [!NOTE]
 > 앱을 제거하려면 앱을 마우스 오른쪽 단추로 클릭한 다음 **제거를** 클릭하거나 왼쪽의 **추가 앱** 메뉴를 사용합니다.

## <a name="purchase-services-for-third-party-apps"></a>타사 앱에 대한 서비스 구매

앱 관리 페이지에서 직접 조직에 있는 타사 앱에서 제공하는 서비스의 라이선스를 검색하고 구입할 수 있습니다. **표의** 라이선스 열은 앱이 유료 SaaS 구독을 제공하는지 여부를 나타내고 있습니다. 지금 **구입을** 클릭하여 사용자를 위한 계획 및 가격 정보를 보고 라이선스를 구매하세요. 자세히 알아보려면 [Microsoft Teams 관리 센터에서 Teams 타사 앱의 구매 서비스를 참조하세요.](purchase-third-party-apps.md)

## <a name="manage-org-wide-app-settings"></a>조직 전체 앱 설정 관리

조직 전체 앱 설정을 사용하여 사용자가 타사 앱을 설치할 수 있는지 여부 및 사용자가 조직의 사용자 지정 앱을 업로드하거나 이에 대한 서비스를 이용할 수 있는지 여부를 제어합니다. 조직 전체 앱 설정은 모든 사용자에게 할당되는 동작을 제어하고 사용자에게 할당된 다른 모든 앱 사용 권한 정책을 재정의합니다. 이 앱을 사용하여 악성 앱 또는 문제가 있는 앱을 제어할 수 있습니다.

> [!NOTE]
> Microsoft 365 Government에서 앱 설정을 사용하는 방법에 대해 알아보려면 [Teams에서 앱 권한 정책 관리를 참조하세요.](teams-app-permission-policies.md)

1. 앱 관리 페이지에서 조직 전체 **앱 설정을 선택합니다.** 그런 다음 패널에서 원하는 설정을 구성할 수 있습니다.

    ![전역 앱 설정 스크린샷](media/manage-apps-org-wide-app-settings.png)
    
2. 타사 **앱에서 타사 앱에**대한 액세스를 제어하는 다음 설정을 해제하거나 켜세요.

    - **타사 앱 허용:** 이 토대는 사용자가 타사 앱을 사용할 수 있는지 여부를 제어합니다. 이 설정을 꺼면 사용자가 타사 앱을 설치하거나 사용할 수 없고 이러한 앱의 앱 상태는 테이블의 조직 **차원으로 차단된 것으로** 표시됩니다.

        > [!NOTE]
        > 타사 **앱을 해제하면 보내는** 웹 사이트가 [outgoing webhooks](https://docs.microsoft.com/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) 해제됩니다. 즉, 사용자가 앱을 만들 수 없습니다. 이 설정이 설정되면 모든 사용자가 오는 웹 연결 웹 연결을 사용할 수 있고 사용자 수준에서 앱 사용 권한 정책을 통해 보내거나 차단하여 사용자 수준에서 이를 [제어할 수 있습니다.](teams-app-permission-policies.md) <br><br>특정 앱 허용 및 다른 [모든](teams-app-permission-policies.md) 설정을 **차단하는 Microsoft** 앱에 대한 기존 앱 사용 권한 정책이 **있는** 경우 사용자에 대해 나오는 웹 호크를 사용하도록 설정하려면 목록에 보내는 웹부 앱을 추가해야 합니다.
    - **스토어에 게시되는 새 타사**앱을 기본적으로 허용합니다. 이 토대로 Teams 앱 스토어에 게시되는 새 타사 앱을 Teams에서 자동으로 사용할 수 있는지를 제어합니다. 타사 앱을 허용하는 경우 이 옵션만 설정할 수 있습니다.

3. 사용자 **지정 앱에서**사용자 지정 앱과의 상호 **작용 허용을 끄거나 설정 해제합니다.** 이 설정은 사용자가 사용자 지정 앱과 상호 작용할 수 있는지 여부를 제어합니다. 자세한 내용은 [Teams에서 사용자 지정 앱 정책 및 설정 관리를 참조하세요.](teams-custom-app-policies-and-settings.md)
4. 전체 **앱** 설정에 대해 저장을 클릭하여 적용합니다.

## <a name="related-topics"></a>관련 항목

- [Team에서 앱의 관리 설정](admin-settings.md)