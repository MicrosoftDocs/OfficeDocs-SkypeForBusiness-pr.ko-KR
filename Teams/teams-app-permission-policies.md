---
title: Microsoft Teams에서 앱 사용 권한 정책 관리
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: rarang
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams의 앱 사용 권한 정책 및 이를 사용하여 조직의 사용자가 사용할 수 있는 앱을 제어하는 방법에 대해 자세히 배워야 합니다.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.overview
- ms.teamsadmincenter.appsetuppolicies.addpinnedapp.permissions
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: aa11b21405079ab26bf1fa9572eb203560c4e461
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802498"
---
# <a name="manage-app-permission-policies-in-microsoft-teams"></a>Microsoft Teams에서 앱 사용 권한 정책 관리

관리자는 앱 권한 정책을 사용하여 조직의 Microsoft Teams 사용자가 사용할 수있는 앱을 제어할 수 있습니다. Microsoft, 타사 및 조직에서 게시한 모든 앱 또는 특정 앱을 허용하거나 차단할 수 있습니다. 앱을 차단하면 정책이 있는 사용자는 Teams 앱 스토어에서 goekd 앱을 설치할 수 없습니다. 이러한 정책을 관리하려면 전역 관리자 또는 Teams 서비스 관리자여야 합니다.

Microsoft Teams 관리 센터에서 앱 사용 권한 정책을 관리합니다. 전역(전체 기본) 정책을 사용하거나 사용자 지정 정책을 만들고 할당할 수 있습니다. 사용자 지정 정책을 만들고 할당하지 않으면 조직의 사용자에게 전역 정책이 자동으로 적용됩니다. 정책을 편집하거나 할당한 후 변경 내용을 적용하는 데 몇 시간이 걸릴 수 있습니다.

![앱 사용 권한 정책 스크린샷](media/app-permission-policies.png)

> [!NOTE]
> 전체 앱 설정은 사용자가 만들고 사용자에게 할당하는 전역 정책 및 모든 사용자 지정 정책을 다시 정의합니다.

조직이 이미 Teams에 있는 경우 Microsoft 365 관리 센터의 테넌트 전체 설정에서 구성한 앱 설정이 앱 관리 페이지의 조직 전체 앱 설정에 [반영됩니다.](manage-apps.md)  Teams를 시작한 경우 기본적으로 모든 앱이 전역 정책에서 허용됩니다. 여기에는 Microsoft, 타사 및 조직에서 게시한 앱이 포함됩니다.

예를 들어 모든 타사 앱을 차단하고 조직의 HR 팀에 대해 Microsoft의 특정 앱을 허용하려는 경우를 예로 들 수 있습니다. 먼저 앱 관리 페이지로 이동하여 HR 팀에 허용하려는 앱이 구성 수준에서 허용되는지 확인하게 됩니다. [](manage-apps.md) 그런 다음, HR 앱 사용 권한 정책이라는 사용자 지정 정책을 만들고, 원하는 앱을 차단 및 허용하도록 설정하고, HR 팀의 사용자에게 할당합니다.

> [!NOTE]
> Microsoft 365 GCC(Government Community Cloud) 환경에 Teams를 배포한 경우 GCC에 고유한 타사 앱 설정에 대한 자세한 내용은 [Microsoft 365 Government의](#manage-org-wide-app-settings-for-microsoft-365-government) 전체 앱 설정 관리를 참조하세요.

## <a name="create-a-custom-app-permission-policy"></a>사용자 지정 앱 사용 권한 정책 만들기

조직의 다른 사용자 그룹에 사용할 수 있는 앱을 제어하려면 하나 이상의 사용자 지정 앱 사용 권한 정책을 만들고 할당합니다. Microsoft, 타사 또는 조직에서 앱을 게시하는지 여부에 따라 별도의 사용자 지정 정책을 만들고 할당할 수 있습니다. 사용자 지정 정책을 만든 후 전체 앱 설정에서 타사 앱을 사용하지 않도록 설정한 경우 변경할 수 없습니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 Teams 앱 사용 **권한**  >  **정책으로 이동하세요.**
2. 추가를 **클릭합니다.** <br>
    ![새 앱 사용 권한 정책의 스크린샷](media/app-permission-policies-new-policy.png)
3. 정책의 이름과 설명을 입력합니다.
4. **Microsoft 앱,** **타사** 앱 및 사용자 지정 **앱 아래에서** 다음 중 하나를 선택합니다.

    - **모든 앱 허용**
    - **특정 앱 허용 및 다른 모든 앱 차단**
    - **특정 앱 차단 및 다른 모든 앱 허용**
    - **모든 앱 차단**

5. 특정 앱 **허용을 선택한 경우** 다른 앱을 차단한 경우 허용하려는 앱을 추가합니다.

    1. 앱 **허용을 선택합니다.**
    1. 허용할 앱을 검색한 다음 추가를 **클릭합니다.** 검색 결과는 앱 게시자(Microsoft **앱,** 타사 앱 또는 사용자 지정 앱)로 **필터링됩니다.**
    1. 앱 목록을 선택한 경우 허용을 **클릭합니다.** 

6. 마찬가지로 특정 앱 차단을 선택한 경우 다른 모든 앱을 허용한 경우 차단할 앱을 검색하여 추가한 다음 차단을 **클릭합니다.**
7. **저장** 을 클릭합니다.

## <a name="edit-an-app-permission-policy"></a>앱 사용 권한 정책 편집

Microsoft Teams 관리 센터를 사용하여 만든 전역 정책 및 사용자 지정 정책을 포함하여 정책을 편집할 수 있습니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 Teams 앱 사용 **권한**  >  **정책으로 이동하세요.**
2. 정책 이름 왼쪽을 클릭하여 정책을 선택한 다음 편집을 **클릭합니다.**
3. 여기에서 원하는 내용을 변경합니다. 앱 게시자를 기반으로 설정을 관리하고 허용/차단 설정에 따라 앱을 추가 및 제거할 수 있습니다.
4. **저장** 을 클릭합니다.

## <a name="assign-a-custom-app-permission-policy-to-users"></a>사용자에게 사용자 지정 앱 사용 권한 정책 할당

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="manage-org-wide-app-settings-for-microsoft-365-government"></a>Microsoft 365 Government에 대한 전체 앱 설정 관리  

Microsoft 365 Government - Teams의 GCC 배포에서는 GCC에 고유한 타사 앱 설정에 대해 다음을 알아야 합니다.

GCC에서 모든 타사 앱은 기본적으로 차단됩니다. 또한 Microsoft Teams 관리 센터의 앱 사용 권한 정책 페이지에서 타사 앱 관리에 대한 다음 메모가 표시됩니다.

![GCC의 앱 사용 권한 정책 스크린샷](media/app-permission-policies-gcc.png)

전체 앱 설정을 사용하여 사용자가 타사 앱을 설치할 수 있는지 여부를 제어합니다. 전체 앱 설정은 모든 사용자에 대한 동작을 관리하고 사용자에게 할당된 다른 모든 앱 사용 권한 정책을 수정합니다. 악의적 또는 문제가 있는 앱을 제어하는 데 사용할 수 있습니다.

1. 사용 권한 **정책 페이지에서** 전체 앱 설정을 **선택합니다.** 그런 다음 패널에서 원하는 설정을 구성할 수 있습니다.

    ![전체 앱 설정 스크린샷](media/app-permission-policies-gcc-org-wide.png)
    
2. 타사 **앱에서** 다음 설정을 끄거나 켜 타사 앱에 대한 액세스를 제어합니다.

    - **타사 앱 허용:** 사용자가 타사 앱을 사용할 수 있는지 여부를 제어합니다. 이 설정을 해제하면 사용자가 타사 앱을 설치하거나 사용할 수 없습니다. Teams의 Microsoft 365 Government - GCC 배포에서 이 설정은 기본적으로 해제되어 있습니다.
    - **기본적으로** 스토어에 게시된 새 타사 앱을 허용합니다. Teams 앱 스토어에 게시된 새 타사 앱을 Teams에서 자동으로 사용할 수 있는지 여부를 제어합니다. 타사 앱을 허용하는 경우 이 옵션을 설정할 수 있습니다.

3. 차단된 **앱 아래에서** 조직 전체에서 차단하려는 앱을 추가합니다. Microsoft 365 Government - Teams의 GCC 배포에서는 기본적으로 모든 타사 앱이 이 목록에 추가됩니다. 조직에서 허용하려는 타사 앱의 경우 차단된 앱 목록에서 앱을 제거합니다. 앱 전체를 차단하면 앱 사용 권한 정책에 허용되는지 여부에 관계없이 모든 사용자에 대해 앱이 자동으로 차단됩니다.
4. 전체 **앱** 설정에 대해 저장을 클릭하여 적용합니다.

앞에서 설명한 대로 타사 앱을 허용하기 위해 전역(전체 기본) 정책을 편집 및 사용하거나 사용자 지정 정책을 만들고 할당할 수 있습니다.

## <a name="faq"></a>FAQ

### <a name="working-with-app-permission-policies"></a>앱 사용 권한 정책 작업

#### <a name="what-app-interactions-do-permission-policies-affect"></a>권한 정책은 어떤 앱 상호 작용에 영향을 주나요?
사용 권한 정책은 최종 사용자에 대한 설치, 검색 및 상호 작용을 제어하여 앱 사용량을 제어합니다. 관리자는 할당된 사용 권한 정책에 관계없이 Microsoft Teams 관리 센터에서 앱을 관리할 수 있습니다.

#### <a name="can-i-control-line-of-business-lob-apps"></a>LOB(사업부) 앱을 제어할 수 있나요?
예, 앱 사용 권한 정책을 사용하여 사용자 지정(LOB) 앱의 롤아웃 및 배포를 제어할 수 있습니다. 조직의 요구에 따라 사용자 지정 앱을 허용하거나 차단하도록 사용자 지정 정책을 만들거나 전역 정책을 편집할 수 있습니다.

#### <a name="how-do-app-permission-policies-relate-to-pinned-apps-and-app-setup-policies"></a>앱 사용 권한 정책은 고정된 앱 및 앱 설정 정책과 어떻게 관련이 있나요?

앱 사용 권한 정책과 함께 앱 설정 정책을 사용할 수 있습니다. 미리 고정된 앱은 사용자에 대해 활성화된 앱 집합에서 선택됩니다. 또한 사용자에게 앱 설정 정책에서 앱을 차단하는 앱 사용 권한 정책이 있는 경우 해당 앱이 Teams에 나타나지 않습니다.

#### <a name="can-i-use-app-permission-policies-to-restrict-uploading-custom-apps"></a>앱 사용 권한 정책을 사용하여 사용자 지정 앱 업로드를 제한할 수 있나요?

앱 관리 페이지에서 조직 전체 설정을 사용할 수 **있습니다.** 또는 앱 설정 정책을 사용하여 조직에 대한 사용자 지정 앱 업로드를 제한할 수 있습니다.  

특정 사용자를 사용자 지정 앱 업로드를 제한하려면 사용자 지정 앱 정책을 사용하세요. 자세한 내용은 Teams에서 사용자 [지정 앱 정책 및 설정 관리를 참조하세요.](teams-custom-app-policies-and-settings.md)

#### <a name="does-blocking-an-app-apply-to-teams-mobile-clients"></a>앱 차단이 Teams 모바일 클라이언트에 적용하나요?

예, 앱을 차단하면 모든 Teams 클라이언트에서 해당 앱이 차단됩니다.  

### <a name="user-experience"></a>사용자 환경

#### <a name="what-does-a-user-experience-when-an-app-is-blocked"></a>앱이 차단된 경우 사용자 환경은 어떻게 하나요?

사용자는 차단된 앱 또는 해당 기능(예: 봇, 탭 및 메시징 확장)과 상호 작용할 수 없습니다. 팀 또는 그룹 채팅과 같은 공유 컨텍스트에서 봇은 해당 컨텍스트의 모든 참가자에게 메시지를 보낼 수 있습니다. 앱이 차단되면 Teams가 사용자에게 나타냅니다.

예를 들어 앱이 차단된 경우 사용자는 다음 중 어떤 작업을 할 수 없습니다.

- 개인적으로 또는 채팅 또는 팀에 앱 추가
- 앱의 봇에 메시지 보내기
- 실행 가능한 메시지와 같은 정보를 앱으로 다시 보내는 단추 작업 수행  
- 앱의 탭 보기
- 알림을 받기 위해 커넥터 설정
- 앱의 메시징 확장 사용

레거시 포털은 조직 수준에서 앱을 제어하도록 허용했습니다. 즉, 앱이 차단된 경우 조직의 모든 사용자에 대해 차단됩니다. 앱 관리 페이지에서 [](manage-apps.md) 앱을 차단하는 것은 정확히 동일한 방식으로 작동합니다.

특정 사용자에게 할당된 앱 사용 권한 정책의 경우, 봇 또는 커넥터 기능이 있는 앱이 허용된 다음 차단된 경우, 앱이 공유 컨텍스트의 일부 사용자에 대해만 허용되는 경우 해당 앱에 대한 권한이 없는 그룹 채팅 또는 채널의 구성원은 봇 또는 커넥터에 의해 게시된 메시지 기록 및 메시지를 볼 수 있습니다. 으로는 상호 작용할 수 없는 경우

## <a name="related-topics"></a>관련 항목

[Team에서 앱의 관리 설정](admin-settings.md)

[Teams에서 사용자에게 정책 할당](assign-policies.md)
