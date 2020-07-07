---
title: Microsoft 팀에서 앱 권한 정책 관리
author: lanachin
ms.author: v-lanac
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
description: Microsoft 팀에서 앱 권한 정책에 대해 알아보고,이를 사용 하 여 조직의 사용자가 사용할 수 있는 앱을 제어 하는 방법에 대해 알아봅니다.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.overview
- ms.teamsadmincenter.appsetuppolicies.addpinnedapp.permissions
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: 15698c7eeb12187ccc510a42b9a6e2120a7907cc
ms.sourcegitcommit: 2467ece95e100a3a3cc2be3538d8eb7d878b3663
ms.contentlocale: ko-KR
ms.lasthandoff: 07/06/2020
ms.locfileid: "45042997"
---
# <a name="manage-app-permission-policies-in-microsoft-teams"></a>Microsoft 팀에서 앱 권한 정책 관리

관리자는 앱 권한 정책을 사용하여 조직의 Microsoft Teams 사용자가 사용할 수있는 앱을 제어할 수 있습니다. Microsoft, 타사, 조직에서 게시 한 앱 또는 특정 앱을 모두 허용 하거나 차단할 수 있습니다. 앱을 차단하면 정책이 있는 사용자는 Teams 앱 스토어에서 goekd 앱을 설치할 수 없습니다. 이러한 정책을 관리하려면 전역 관리자 또는 Teams 서비스 관리자여야 합니다.

Microsoft 팀 관리 센터에서 앱 권한 정책을 관리 합니다. 전역 (조직 차원의 기본) 정책을 사용 하거나 사용자 지정 정책을 만들고 할당할 수 있습니다. 사용자 지정 정책을 만들고 할당하지 않으면 조직의 사용자에게 전역 정책이 자동으로 적용됩니다. 정책을 편집 하거나 할당 한 후 변경 내용을 적용 하는 데 몇 시간이 걸릴 수 있습니다.

![앱 사용 권한 정책의 스크린샷](media/app-permission-policies.png)

> [!NOTE]
> 조직 전체 앱 설정은 전역 정책 및 사용자가 만들고 할당 하는 사용자 지정 정책을 재정의 합니다.

조직이 이미 팀에 있는 경우 Microsoft 365 관리 센터의 **테 넌 트 전체 설정** 에서 구성한 앱 설정은 [앱 관리](manage-apps.md) 페이지의 조직 전체 앱 설정에 반영 됩니다. 팀을 처음 접하는 경우에는 기본적으로 모든 앱을 전역 정책에서 사용할 수 있습니다. 여기에는 Microsoft, 타사, 조직에서 게시 한 앱이 포함 됩니다.

예를 들어 모든 타사 앱을 차단 하 고 조직의 HR 팀에 대해 Microsoft의 특정 앱을 허용 하려는 경우를 가정해 보겠습니다. 먼저 [앱 관리](manage-apps.md) 페이지로 이동 하 여 HR 팀에 허용 하려는 앱이 조직 수준에서 허용 되는지 확인 합니다. 그런 다음 HR 앱 권한 정책 이라는 사용자 지정 정책을 만들고, 원하는 앱을 차단 하 고 허용 하도록 설정한 다음 HR 팀에서 사용자에 게 할당 합니다.

> [!NOTE]
> Microsoft 365의 GCC (정부 커뮤니티 클라우드) 환경에서 팀을 배포한 경우 GCC에 고유한 제 3 자 앱 설정에 대 한 자세한 내용은 [microsoft 365 정부용 조직 전체 앱 설정 관리](#manage-org-wide-app-settings-for-microsoft-365-government) 를 참조 하세요.

## <a name="create-a-custom-app-permission-policy"></a>사용자 지정 앱 권한 정책 만들기

조직의 다른 사용자 그룹에 대해 사용할 수 있는 앱을 제어 하려는 경우 하나 이상의 사용자 지정 앱 권한 정책을 만들고 할당 합니다. 앱이 Microsoft, 타사 또는 조직에 의해 게시 되었는지 여부에 따라 별도의 사용자 지정 정책을 만들고 할당할 수 있습니다. 사용자 지정 정책을 만든 후에는 조직 전체 앱 설정에서 타사 앱을 사용 하지 않도록 설정한 경우 변경할 수 없다는 것을 알아야 합니다.

1. Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **팀 앱**  >  **권한 정책**으로 이동 합니다.
2. **추가**를 클릭 합니다. <br>
    ![새 앱 권한 정책의 스크린샷](media/app-permission-policies-new-policy.png)
3. 정책의 이름과 설명을 입력합니다.
4. **Microsoft 앱**, 타사 **앱**및 **사용자 지정 앱**에서 다음 중 하나를 선택 합니다.

    - **모든 앱 허용**
    - **특정 앱 허용 및 다른 사용자 모두 차단**
    - **특정 앱을 차단 하 고 다른 사용자 허용**
    - **모든 앱 차단**

5. **특정 앱 허용 및 다른 사용자 차단**을 선택한 경우 허용 하려는 앱을 추가 합니다.

    1. **앱 허용**을 선택 합니다.
    1. 허용 하려는 앱을 검색 한 다음 **추가**를 클릭 합니다. 검색 결과가 앱 게시자 (**Microsoft 앱**, 타사 **앱**또는 **사용자 지정 앱**)로 필터링 됩니다.
    1. 앱 목록을 선택 했으면 **허용**을 클릭 합니다. 

6. 마찬가지로 **특정 앱을 차단 하 고 다른 모든 사용자 허용**을 선택한 경우 차단 하려는 앱을 검색 하 여 추가한 다음 **차단을**클릭 합니다.
7. **저장**을 클릭합니다.

## <a name="edit-an-app-permission-policy"></a>앱 권한 정책 편집

Microsoft 팀 관리 센터를 사용 하 여 글로벌 정책 및 만든 사용자 지정 정책을 비롯 한 정책을 편집할 수 있습니다.

1. Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **팀 앱**  >  **권한 정책**으로 이동 합니다.
2. 정책 이름 왼쪽을 클릭 하 여 정책을 선택한 다음 **편집**을 클릭 합니다.
3. 여기서 원하는 대로 변경 합니다. 앱 게시자에 따라 설정을 관리 하 고 허용/차단 설정에 따라 앱을 추가 및 제거할 수 있습니다.
4. **저장**을 클릭합니다.

## <a name="assign-a-custom-app-permission-policy-to-users"></a>사용자에 게 사용자 지정 앱 권한 정책 할당

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="manage-org-wide-app-settings-for-microsoft-365-government"></a>Microsoft 365 정부용 조직 전체 앱 설정 관리  

팀의 Microsoft 365 정부-GCC 배포에서 GCC에 고유한 제 3 자 앱 설정에 대 한 다음 사항을 알고 있어야 합니다.

GCC에서는 모든 타사 앱이 기본적으로 차단 됩니다. 또한 Microsoft 팀 관리 센터의 앱 사용 권한 정책 페이지에서 타사 앱을 관리 하는 방법에 대 한 참고 사항을 확인할 수 있습니다.

![GCC의 앱 사용 권한 정책 스크린샷](media/app-permission-policies-gcc.png)

조직 전체 앱 설정을 사용 하 여 사용자가 타사 앱을 설치할 수 있는지 여부를 제어 합니다. 조직 전체 앱 설정은 모든 사용자의 동작을 제어 하 고 사용자에 게 할당 된 다른 앱 사용 권한 정책을 재정의 합니다. 이를 사용 하 여 악의적 이거나 문제가 있는 앱을 제어할 수 있습니다.

1. **사용 권한 정책** 페이지에서 **조직 전체 앱 설정을**선택 합니다. 그런 다음 패널에서 원하는 설정을 구성할 수 있습니다.

    ![조직 전체 앱 설정 스크린샷](media/app-permission-policies-gcc-org-wide.png)
    
2. 타사 앱에 대 한 액세스를 제어 하기 위해이 설정을 설정 하거나 **해제 합니다.**

    - 타사 **앱 허용**:이는 사용자가 타사 앱을 사용할 수 있는지 여부를 제어 합니다. 이 설정을 해제 하는 경우 사용자는 타사 앱을 설치 하거나 사용할 수 없게 됩니다. 팀의 Microsoft 365 정부-GCC 배포에서이 설정은 기본적으로 해제 되어 있습니다.
    - **기본적으로 저장소에 게시 된 새 타사 앱 허용**: 팀 앱 스토어에 게시 되는 새로운 타사 앱을 팀에서 자동으로 사용할 수 있는지 여부를 제어 합니다. 타사 앱을 허용 하는 경우에만이 옵션을 설정할 수 있습니다.

3. **차단 된 앱**에서 조직 간에 차단할 앱을 추가 합니다. 팀의 Microsoft 365 정부-GCC 배포에서는 기본적으로이 목록에 모든 타사 앱이 추가 됩니다. 조직에서 허용 하려는 타사 앱에 대해 차단 된 앱 목록에서 앱을 제거 합니다. 앱을 조직 전체에서 차단 하면 앱 권한 정책에서 허용 되는지 여부에 관계 없이 앱이 모든 사용자에 대해 자동으로 차단 됩니다.
4. **저장** 을 클릭 하 여 조직 전체 앱 설정을 적용 합니다.

앞에서 설명한 대로, 타사 앱을 허용 하려면 전역 (조직 차원의 기본) 정책을 편집 하 고 사용 하거나 사용자 지정 정책을 만들어 할당할 수 있습니다.

## <a name="faq"></a>FAQ

### <a name="working-with-app-permission-policies"></a>앱 권한 정책 사용

#### <a name="what-app-interactions-do-permission-policies-affect"></a>권한 정책의 영향을 받는 앱 조작
권한 정책은 최종 사용자의 설치, 검색, 조작 등을 제어 하 여 앱 사용을 관리 합니다. 관리자는 할당 된 권한 정책에 관계 없이 Microsoft 팀 관리 센터에서 앱을 계속 관리할 수 있습니다.

#### <a name="can-i-control-line-of-business-lob-apps"></a>LOB (기간 업무) 앱을 제어할 수 있나요?
예, 앱 사용 권한 정책을 사용 하 여 사용자 지정 (LOB) 앱의 출시 및 배포를 제어할 수 있습니다. 사용자 지정 정책을 만들거나 전역 정책을 편집 하 여 조직의 요구 사항에 따라 사용자 지정 앱을 허용 하거나 차단할 수 있습니다.

#### <a name="how-do-app-permission-policies-relate-to-pinned-apps-and-app-setup-policies"></a>앱 권한 정책은 고정 된 앱 및 앱 설정 정책과 어떻게 관련 되나요?

앱 설치 정책은 앱 권한 정책과 함께 사용할 수 있습니다. 미리 고정 된 앱은 사용자의 활성화 된 앱 집합에서 선택 합니다. 또한 사용자에 게 앱 설정 정책에서 앱을 차단 하는 앱 권한 정책이 있는 경우 해당 앱은 팀에 표시 되지 않습니다.

#### <a name="can-i-use-app-permission-policies-to-restrict-uploading-custom-apps"></a>앱 권한 정책을 사용 하 여 사용자 지정 앱 업로드를 제한할 수 있나요?

**앱 관리** 페이지 또는 앱 설정 정책에서 조직 전체 설정을 사용 하 여 조직의 사용자 지정 앱 업로드를 제한할 수 있습니다.  

특정 사용자가 사용자 지정 앱을 업로드 하지 못하도록 제한 하려면 사용자 지정 앱 정책을 사용 합니다. 자세히 알아보려면 [팀에서 사용자 지정 앱 정책 및 설정 관리](teams-custom-app-policies-and-settings.md)를 참조 하세요.

#### <a name="does-blocking-an-app-apply-to-teams-mobile-clients"></a>앱이 팀 모바일 클라이언트에 적용 되는 것을 차단 합니까?

예, 앱을 차단 하면 모든 팀 클라이언트에서 앱이 차단 됩니다.  

### <a name="user-experience"></a>사용자 환경

#### <a name="what-does-a-user-experience-when-an-app-is-blocked"></a>앱이 차단 되는 경우 사용자 환경

사용자는 차단 된 앱 또는 인공 지능, 탭, 메시징 확장과 같은 기능을 조작할 수 없습니다. 팀 또는 그룹 채팅 같은 공유 컨텍스트에서이는 해당 컨텍스트의 모든 참가자에 게 메시지를 보낼 수 있습니다. 앱이 차단 되 면 팀에서 사용자에 게 표시 됩니다.

예를 들어 앱이 차단 되 면 사용자는 다음을 수행할 수 없습니다.

- 개인적으로 또는 채팅 또는 팀에 앱 추가
- 앱의 bot에 메시지 보내기
- 처리 가능한 메시지 등의 정보를 앱으로 다시 보내는 단추 작업 수행  
- 앱의 탭 보기
- 알림을 받도록 커넥터 설정
- 앱의 메시징 확장 사용

레거시 포털은 조직 수준에서 앱을 제어할 수 있으며,이는 앱이 차단 되는 경우 조직의 모든 사용자에 대해 차단 됨을 의미 합니다. [앱 관리](manage-apps.md) 페이지에서 앱을 차단 하는 방법은 동일 하 게 작동 합니다.

특정 사용자에 게 할당 된 앱 권한 정책의 경우, 봇 또는 커넥터 기능이 있는 앱이 허용 된 후 차단 되며,이 앱이 공유 컨텍스트의 일부 사용자 에게만 허용 되는 경우 해당 앱에 대 한 권한이 없는 그룹 채팅 또는 채널의 구성원은 봇 또는 커넥터에 의해 게시 된 메시지 기록 및 메시지를 볼 수 있습니다. 있지만 대화형 작업을 할 수 없습니다.

## <a name="related-topics"></a>관련 항목

[Team에서 앱의 관리 설정](admin-settings.md)

[팀에서 사용자에 게 정책 할당](assign-policies.md)
