---
title: Microsoft 팀에서 lob (기간 업무) 앱 관리
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: joglocke
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
description: 개발에서 배포에 이르기까지 사용자 지정 팀 앱을 사용 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: f8c5a7dcc12bc9b3823285138d15a0ccdf11c52a
ms.sourcegitcommit: 7093388425b34c80e444a50d062290187b80047d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/22/2020
ms.locfileid: "42229938"
---
# <a name="manage-your-line-of-business-apps-in-microsoft-teams"></a>Microsoft 팀에서 lob (기간 업무) 앱 관리

이 문서에서는 개발에서 배포에 이르기까지 팀 앱을 사용 하는 방법에 대 한 종단 간 지침을 제공 합니다. 이 지침은 앱의 팀 측면에 중점을 둔 것 이며 IT 전문가를 위한 것입니다. 팀 앱을 개발 하는 방법에 대 한 자세한 내용은 <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">여기</a>를 참조 하세요.

![개발에서 배포 까지의 앱 개요](media/manage-your-lob-apps.png)

## <a name="getting-started"></a>시작

팀에서 LOB (기간 업무) 앱을 만들고 관리 하려면 두 개의 테 넌 트, 즉 개발에 대 한 테스트 테 넌 트와 프로덕션 테 넌 트가 필요 합니다.

> [!NOTE]
> 테스트 테 넌 트가 아직 없는 경우에는 신속 하 게 만들고 Office 365 개발자 프로그램을 사용 하 여 테스트 데이터로 채울 수 있습니다. <a href="https://developer.microsoft.com/office/dev-program" target="_blank">자세한 내용은 여기를 참조</a>하세요.

## <a name="step-1-develop-and-test"></a>1 단계: 개발 및 테스트

### <a name="create-test-users"></a>테스트 사용자 만들기

사내 또는 외부에 있든 관계 없이 개발자가 테스트 테 넌 트에 계정이 있는지 확인 합니다. <a href="https://docs.microsoft.com/office365/admin/add-users/add-users" target="_blank">사용자 추가에 대해 자세히 알아보세요</a>.

### <a name="allow-custom-apps-in-the-test-tenant"></a>테스트 테 넌 트에서 사용자 지정 앱 허용

개발자에 게 테스트에 필요한 액세스 권한을 부여 하려면 테스트 테 넌 트의 모든 사용자가 사용자 지정 앱 (테스트용 로드 라고도 함)을 업로드 하도록 허용 합니다. 이를 통해 개발자는 팀 앱 스토어에 앱을 제출할 필요 없이 개인적으로 사용 하거나 테스트 테 넌 트를 통해 사용자 지정 앱을 업로드할 수 있습니다. 사용자 지정 앱을 업로드 하면 개발자가 앱을 테스트 한 후 보다 광범위 하 게 배포할 수 있습니다.

사용자가 사용자 지정 앱을 업로드 하도록 허용 하려면 다음 단계를 따릅니다.

1. **사용자 지정 앱과 상호 작용 허용** 조직 전체 앱 설정을 사용 합니다. 실행할 작업:
    1. <a href="https://admin.teams.microsoft.com/" target="_blank">Microsoft 팀 관리 센터</a>의 왼쪽 탐색 창에서 **팀 앱** > 으로 이동 하 여**앱을 관리**하 고 **조직 전체 앱 설정을**클릭 합니다.
    2. **사용자 지정 앱**에서 **사용자 지정 앱과의 상호 작용 허용**을 켠 다음 **저장**을 클릭 합니다.

    !["사용자 지정 앱과 상호 작용 허용" 조직 전체 앱 설정의 스크린샷](media/manage-your-lob-apps-org-wide-custom-apps.png)

2. 전역 앱 설정 정책에서 **사용자 지정 앱 업로드** 설정을 켭니다. 실행할 작업:
    1. <a href="https://admin.teams.microsoft.com/" target="_blank">Microsoft 팀 관리 센터</a>의 왼쪽 탐색 창에서 **팀 앱** > **설정 정책**으로 이동한 다음 **전역 (조직 전체 기본값)** 정책을 클릭 합니다.
    2. **사용자 지정 앱 업로드**를 켠 다음 **저장**을 클릭 합니다.

    !["사용자 지정 앱 업로드" 앱 설치 정책 설정의 스크린샷](media/manage-your-lob-apps-app-setup-custom-apps.png)

> [!NOTE]
> 팀 수준의 업로드 사용자 지정 앱 설정도 있습니다. 기본적으로이 설정은 설정 되어 있습니다. 그러나 개발자가 팀에 사용자 지정 앱을 업로드할 수 없는 경우에는 다음 단계를 따라 설정을 <a href="https://docs.microsoft.com/microsoftteams/teams-custom-app-policies-and-settings#configure-the-team-custom-app-setting" target="_blank">확인 합니다.</a>

### <a name="create-your-app"></a>앱 만들기

이제 개발자에 게 앱을 만드는 데 필요한 사항이 있습니다. 여기에 대 한 지침을 보려면 <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">여기</a> 를 참조 하세요.

## <a name="step-2-validate-in-production"></a>2 단계: 프로덕션에서 유효성 검사

### <a name="get-the-app-package"></a>앱 패키지 다운로드

앱을 프로덕션에 사용할 준비가 되 면 개발자는 앱 패키지를 생성 해야 합니다. 이를 위해 <a href="https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio" target="_blank">앱 Studio</a> 를 사용할 수 있습니다. .Zip 형식으로 파일을 전송 합니다.

Microsoft는 <a href="https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-approval" target="_blank">이러한 지침</a> 을 사용 하 여 앱이 전역 팀 앱 스토어의 품질 및 보안 표준을 준수 하도록 합니다.

### <a name="allow-trusted-users-to-upload-custom-apps-in-the-production-tenant"></a>신뢰할 수 있는 사용자가 프로덕션 테 넌 트에서 사용자 지정 앱을 업로드 하도록 허용

프로덕션 테 넌 트에서 앱이 올바르게 작동 하는지 확인 하려면 조직에서 자신 및/또는 신뢰할 수 있는 사용자가 사용자 지정 앱을 업로드 하도록 허용 해야 합니다.  앞의 <a href="https://docs.microsoft.com/microsoftteams/manage-your-lob-apps#allow-custom-apps-in-the-test-tenant" target="_blank">단계</a>에서와 같이이 작업을 수행 하는 데 앱 설치 정책을 사용 합니다.

> [!NOTE]
> 유효성 검사를 위해 앱을 프로덕션 테 넌 트에 업로드 하는 것이 불편 하거나 신뢰 하는 사용자 라도이 단계를 건너뛰고 3-4 단계를 수행 하 여 unvalidated 앱을 테 넌 트 앱 스토어에 업로드할 수 있습니다. 그런 다음 자신 및 신뢰 하는 사용자만 해당 앱에 대 한 액세스를 제한 합니다. 그러면 이러한 사용자가 테 넌 트 앱 스토어에서 앱을 다운로드 하 여 유효성 검사를 수행할 수 있습니다. 앱의 유효성을 검사 한 후에는 동일한 권한 정책을 사용 하 여 access를 열고 앱을 프로덕션에 사용할 수 있도록 롤포워드합니다.

신뢰할 수 있는 사용자가 사용자 지정 앱을 업로드 하도록 허용 하려면 다음 단계를 따릅니다.

1. **사용자 지정 앱과 상호 작용 허용** 조직 전체 앱 설정을 사용 합니다. 실행할 작업:
    1. <a href="https://admin.teams.microsoft.com/" target="_blank">Microsoft 팀 관리 센터</a>의 왼쪽 탐색 창에서 **팀 앱** > 으로 이동 하 여**앱을 관리**하 고 **조직 전체 앱 설정을**클릭 합니다.
    2. **사용자 지정 앱**에서 **사용자 지정 앱과의 상호 작용 허용**을 켠 다음 **저장**을 클릭 합니다.
2. 전역 앱 설정 정책에서 **사용자 지정 앱 업로드** 설정을 해제 합니다. 실행할 작업:
    1. <a href="https://admin.teams.microsoft.com/" target="_blank">Microsoft 팀 관리 센터</a>의 왼쪽 탐색 창에서 **팀 앱** > **설정 정책**으로 이동한 다음 **전역 (조직 전체 기본값)** 정책을 클릭 합니다.
    2. **사용자 지정 앱 업로드**를 해제 한 다음 **저장**을 클릭 합니다.
3. 사용자 지정 앱을 업로드 하 고 신뢰할 수 있는 사용자 집합에 할당할 수 있는 새 앱 설정 정책을 만듭니다. 실행할 작업:
    1. <a href="https://admin.teams.microsoft.com/" target="_blank">Microsoft 팀 관리 센터</a>의 왼쪽 탐색 창에서 **팀 앱** > **설치 정책**으로 이동한 다음 **추가**를 클릭 합니다. 새 정책에 이름 및 설명을 지정 하 고, **사용자 지정 앱 업로드**를 설정한 다음 **저장**을 클릭 합니다.
    2. 만든 새 정책을 선택한 다음 **사용자 관리**를 클릭 합니다. 사용자를 검색 하 고 **추가**를 클릭 한 다음 **적용**을 클릭 합니다. 이 단계를 반복 하 여 모든 신뢰할 수 있는 사용자에 게 정책을 할당 합니다.

        !["앱 설치 정책 추가" 페이지의 스크린샷](media/manage-your-lob-apps-new-app-setup-policy.png)

    이러한 사용자는 이제 앱 매니페스트를 업로드 하 여 앱이 프로덕션 테 넌 트에서 올바르게 작동 하는지 확인할 수 있습니다.

## <a name="step-3-upload-to-the-tenant-app-catalog"></a>3 단계: 테 넌 트 앱 카탈로그에 업로드

테 넌 트 앱 스토어의 사용자가 앱을 사용할 수 있도록 하려면 앱을 업로드 합니다. Microsoft 팀 관리 센터의 [앱 관리](manage-apps.md) 페이지에서이 작업을 수행할 수 있습니다.

![관리 센터의 앱 관리 페이지 스크린샷](media/manage-your-lob-apps-upload-new-app.png)

## <a name="step-4-configure-and-assign-permissions"></a>4 단계: 사용 권한 구성 및 할당

### <a name="control-access-to-the-app"></a>앱에 대 한 액세스 제어

기본적으로 모든 사용자는 팀 앱 스토어에서이 앱에 액세스할 수 있습니다. 앱을 사용할 권한이 있는 사용자를 제한 하 고 제어 하려면 새 앱 사용 권한 정책을 만들고 할당할 수 있습니다. 단계 <a href="https://docs.microsoft.com/microsoftteams/teams-app-permission-policies#create-a-custom-app-permission-policy" target="_blank">를 따르세요.</a>

!["앱 권한 정책 추가" 페이지의 스크린샷](media/manage-your-lob-apps-new-app-permission-policy.png)

### <a name="pin-the-app-for-users-to-discover"></a>사용자가 검색할 수 있도록 앱 고정

기본적으로 사용자가이 앱을 찾으려면 팀 앱으로 이동 하 여 저장 하 고 찾아보거나 검색 해야 합니다. 사용자가 앱에 쉽게 액세스할 수 있도록 하려면 팀의 앱 표시줄에 앱을 고정 하면 됩니다. 이렇게 하려면 새 앱 설치 정책을 만들어 사용자에 게 할당 합니다. 단계 <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies#create-a-custom-app-setup-policy" target="_blank">를 따르세요.</a>

!["고정 된 앱 추가" 창의 스크린샷](media/manage-your-lob-apps-pinned-apps.png)

## <a name="step-5-update-the-app"></a>5 단계: 앱 업데이트

![개발에서 배포 까지의 앱 개요](media/manage-your-lob-apps-update.png)

앱을 업데이트 하려면 개발자가 [1 단계](#step-1-develop-and-test) 와 [2 단계](#step-2-validate-in-production)를 계속 수행 해야 합니다.

테 넌 트 앱 카탈로그를 통해 앱을 업데이트할 수 있습니다. 이렇게 하려면 Microsoft 팀 관리 센터에서 **팀 앱** > 앱**관리**로 이동 합니다. 앱 목록에서 앱 이름을 클릭 한 다음 **업데이트**를 클릭 합니다. 이렇게 하면 테 넌 트 앱 카탈로그의 기존 앱이 바뀌고, 모든 앱 권한 정책 및 앱 설정 정책은 업데이트 된 앱에 적용 됩니다.

## <a name="related-apps"></a>관련 앱

- [Microsoft 팀 관리 센터에서 앱 관리](manage-apps.md)