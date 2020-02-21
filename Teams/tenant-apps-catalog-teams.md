---
title: Microsoft 팀 테 넌 트 앱 카탈로그에서 앱 게시
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: prem
audience: admin
description: Microsoft 팀 테 넌 트 앱 카탈로그에서 앱을 게시 하기 위한 지침입니다.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.publishtenantapps
- ms.teamsadmincenter.apppolicies.publishtenantapps
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1f3d4f5937c766c1c4f6f54a6a38872e793a3825
ms.sourcegitcommit: 10046048a670b66d93e8ac3ba7c3ebc9c3c5fc2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/20/2020
ms.locfileid: "42161617"
---
<a name="publish-apps-in-the-microsoft-teams-tenant-app-catalog"></a>Microsoft 팀 테 넌 트 앱 카탈로그에서 앱 게시
=======================================================

Microsoft 팀 테 넌 트 앱 카탈로그를 사용 하 여 조직에 lob (기간 업무) 응용 프로그램을 테스트 하 고 배포할 수 있습니다.

팀 테 넌 트 앱 카탈로그를 사용 하면 조직에 맞게 특별히 빌드되고 중요 한 비즈니스 기능을 완료 하는 데 의존 하는 lob (기간 업무) 응용 프로그램을 배포할 수 있습니다.

조직에 대 한 앱을 게시 하려면 전역 관리자 또는 팀 서비스 관리자 역할이 있는 계정을 사용 하 여 팀 클라이언트에 로그인 한 후 아래 단계를 따르세요.

## <a name="publish-an-app-in-the-tenant-app-catalog-from-the-teams-client"></a>팀 클라이언트에서 테 넌 트 앱 카탈로그에 앱 게시

> [!NOTE]
> 이 단계에서는 팀 클라이언트를 사용 하 여 앱을 게시 하는 방법을 설명 합니다. Microsoft 팀 관리 센터의 **앱 관리** 페이지에서 앱을 게시할 수도 있습니다. 자세히 알아보려면 [팀에서 앱 관리](manage-apps.md)를 참조 하세요.

### <a name="get-a-teams-app-package"></a>팀 앱 패키지 가져오기

팀 앱 패키지는 [팀 앱 Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)를 사용 하 여 만듭니다. 앱 패키지를 사용 하는 경우 테 넌 트 앱 카탈로그에 추가할 수 있습니다. 조직의 모든 사용자가 앱 카탈로그를 볼 수 있지만, 전역 관리자 및 팀 서비스 관리자만이를 게시 및 관리할 수 있습니다.

### <a name="go-to-the-tenant-app-catalog"></a>테 넌 트 앱 카탈로그로 이동

팀을 시작 하 고 전역 또는 팀 서비스 관리자 자격 증명을 사용 하 여 로그인 합니다. 앱의 왼쪽에서 **앱** 을 선택 하 고 특정 조직 (이 예제에서는 Contoso)에 대해 이름이 지정 된 새 섹션을 선택 합니다. 조직의 사용자는 카탈로그에서 앱을 보고 자신이 구성원으로 속해 있는 팀을 위해 설치할 수 있습니다.

![앱 카탈로그를 보여 주는 팀 앱 스토어의 스크린샷](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-tenant-app-catalog"></a>테 넌 트 앱 카탈로그에 앱 추가

1. Apps ( **앱** ) 페이지에서**Contoso에 대 한** **사용자 지정 앱** > 업로드 업로드를 선택 합니다.

    ![앱 카탈로그를 보여 주는 팀 앱 스토어의 스크린샷](media/private-app-store-teams-image02.png)

    ( **또는 my에 대 한 업로드**( *테스트용 로드*라고도 함)를 선택할 수도 있습니다. 테스트용 로드를 통해 팀 또는 선택한 팀 에서만 앱을 사용할 수 있습니다.

2. 앱 패키지로 이동 하 여 선택한 다음 **열기**를 클릭 합니다.

    ![앱 카탈로그를 보여 주는 팀 앱 스토어의 스크린샷](media/private-app-store-teams-image03.png)

테 넌 트 앱 카탈로그로 돌아오면 새 엔터프라이즈 앱이 닫힙니다. 사용자와 조직의 구성원만이 앱 카탈로그에 액세스할 수 있다는 것을 염두에 두어야 합니다.

### <a name="update-an-app-in-the-tenant-app-catalog"></a>테 넌 트 앱 카탈로그에서 앱 업데이트

1. 테 넌 트 앱 카탈로그에서 "..."를 선택**합니다**. 업데이트 하려는 앱의 오른쪽 위에 있습니다.

2. 업데이트 된 앱 패키지로 이동 하 여 선택한 다음 **열기**를 클릭 합니다.

    ![앱 카탈로그를 보여 주는 팀 앱 스토어의 스크린샷](media/private-app-store-teams-image04.png)

앱이 버전 2.0으로 수정 됩니다. 이 메뉴에서 전체 회사에 대 한 앱을 삭제할 수도 있습니다.

## <a name="use-the-microsoft-teams-admin-center-to-manage-the-tenant-app-catalog"></a>Microsoft 팀 관리 센터를 사용 하 여 테 넌 트 앱 카탈로그 관리

버그 수정이 필요한 앱이 있는 경우 앱 권한 정책에서 사용자 용 앱을 일시적으로 사용 하지 않도록 설정할 수 있습니다.

1. Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **팀 앱** > **권한 정책**으로 이동 합니다.
2. 편집 하려는 앱 권한 정책을 선택 하 고 **편집**을 클릭 합니다.
3. **테 넌 트 앱**에서 **특정 앱 차단 및 다른 모든 항목 허용**을 선택한 다음 차단 하려는 앱을 추가 합니다.

앱을 사용 하지 않도록 설정 하면 앱이 완전히 삭제 되지 않고 사용자가 앱과 상호 작용 하지 못하도록 차단 합니다. 이러한 컨트롤을 통해 조직의 앱을 관리할 때 유연성과 제어권을 추가로 얻을 수 있습니다.

자세히 알아보려면 [팀에서 앱 권한 정책 관리](teams-app-permission-policies.md)를 참조 하세요.