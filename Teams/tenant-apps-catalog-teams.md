---
title: Microsoft 팀 테 넌 트 앱 카탈로그에서 앱 게시
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.date: 06/20/2019
ms.topic: article
ms.service: msteams
ms.reviewer: prem
audience: admin
description: Microsoft 팀 테 넌 트 앱 카탈로그에서 앱을 게시 하기 위한 지침입니다.
localization_priority: Normal
search.appverid: MET150
f1keywords: ms.teamsadmincenter.apppolicies.publishtenantapps
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b8f239a136ae3a2242dba45da5a68e22b8fb29c4
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235101"
---
<a name="publish-apps-in-the-microsoft-teams-tenant-apps-catalog"></a>Microsoft 팀 테 넌 트 앱 카탈로그에서 앱 게시
=======================================================

Microsoft 팀 테 넌 트 앱 카탈로그를 사용 하 여 조직에 lob (기간 업무) 응용 프로그램을 테스트 하 고 배포할 수 있습니다.

팀 테 넌 트 앱 카탈로그를 사용 하면 조직에 맞게 특별히 작성 하 고 중요 한 비즈니스 기능을 완료 하는 데 의존 하는 lob (기간 업무) 응용 프로그램을 배포할 수 있습니다.

조직에 대 한 앱을 게시 하려면 전역 관리자 또는 팀 서비스 관리자 역할이 있는 계정을 사용 하 여 팀 클라이언트에 로그인 한 후 아래 지침을 따르세요.

## <a name="publish-an-app-in-the-tenant-apps-catalog-from-the-teams-client"></a>팀 클라이언트에서 테 넌 트 앱 카탈로그에 앱 게시

> [!NOTE]
> 조직의 앱을 게시 하는 데 전역 관리자 또는 팀 서비스 관리자 역할이 설정 된 계정을 사용 하 여 Microsoft 팀 클라이언트에 로그인 해야 합니다. [관리자 역할을 사용 하 여 팀을 관리](https://docs.microsoft.com/MicrosoftTeams/using-admin-roles)하는 방법에 대해 자세히 알아보세요.

### <a name="get-a-teams-app-package"></a>팀 앱 패키지 가져오기

팀 앱 패키지는 [팀 앱 Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)를 사용 하 여 만듭니다. 앱 패키지를 사용 하는 경우 엔터프라이즈 앱 카탈로그에 추가할 수 있습니다. 테 넌 트에서 모든 사용자는 앱 카탈로그를 볼 수 있지만, 전역 관리자 및 팀 서비스 관리자만이를 게시 및 관리할 수 있습니다.

### <a name="go-to-the-tenant-apps-catalog"></a>테 넌 트 앱 카탈로그로 이동

Microsoft 팀 클라이언트를 시작 하 고 전역 또는 팀 서비스 관리자 자격 증명을 사용 하 여 로그인 합니다. Microsoft 팀 스토어에서 특정 조직 (이 예에서는 Contoso)에 대해 이름이 지정 된 새 섹션을 선택 합니다. 조직의 사용자는 카탈로그에서 앱을 보고 자신이 구성원으로 속해 있는 팀을 위해 설치할 수 있습니다.

![앱 카탈로그를 보여 주는 팀 앱 스토어의 스크린샷](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-tenant-apps-catalog"></a>테 넌 트 앱 카탈로그에 앱 추가

1. 스토어에서**Contoso에 대 한** **사용자 지정 앱** > 업로드 업로드를 선택 합니다.

    ![앱 카탈로그를 보여 주는 팀 앱 스토어의 스크린샷](media/private-app-store-teams-image02.png)

    ( **또는 my에 대 한 업로드**( *테스트용 로드*라고도 함)를 선택할 수도 있습니다. 테스트용 로드를 통해 팀 또는 선택한 팀 에서만 앱을 사용할 수 있습니다.

2. 앱 패키지로 이동 하 여 선택한 다음 **열기**를 클릭 합니다.

    ![앱 카탈로그를 보여 주는 팀 앱 스토어의 스크린샷](media/private-app-store-teams-image03.png)

테 넌 트 앱 카탈로그로 돌아오면 새 엔터프라이즈 앱이 닫힙니다. 사용자와 조직의 구성원만이 앱 카탈로그에 액세스할 수 있다는 것을 염두에 두어야 합니다.

### <a name="update-an-app-in-the-tenant-apps-catalog"></a>테 넌 트 앱 카탈로그에서 앱 업데이트

1. 테 넌 트 앱 카탈로그에서 "..."를 선택**합니다**. 업데이트 하려는 앱의 오른쪽 위에 있습니다.

2. 업데이트 된 앱 패키지로 이동 하 여 선택한 다음 **열기**를 클릭 합니다.

    ![앱 카탈로그를 보여 주는 팀 앱 스토어의 스크린샷](media/private-app-store-teams-image04.png)

앱이 버전 2.0으로 수정 됩니다. 이 메뉴에서 전체 회사에 대 한 앱을 삭제할 수도 있습니다.

## <a name="use-the-office-365-admin-portal-to-manage-the-tenant-apps-catalog"></a>Office 365 관리 포털을 사용 하 여 테 넌 트 앱 카탈로그 관리

버그 수정이 필요한 앱이 있는 경우 Office 365 관리 포털을 통해 앱을 일시적으로 사용 하지 않도록 설정할 수 있습니다. **설정** > **서비스 & 추가 기능** > **Microsoft 팀**을 선택 합니다. 이전 설정 외에도 이제 회사의 앱 전용 섹션이 있습니다. 사용 하거나 사용 하지 않을 앱을 선택할 수 있습니다.

![앱 카탈로그를 보여 주는 팀 앱 스토어의 스크린샷](media/private-app-store-teams-image05.png)

앱을 사용 하지 않도록 설정 하면 앱이 완전히 삭제 되지 않고 사용자가 앱과 상호 작용 하지 못하도록 차단 합니다. 이러한 컨트롤을 통해 엔터프라이즈에서 앱을 관리할 때 유연성과 제어권을 추가로 얻을 수 있습니다.
