---
title: Microsoft 팀 관리 센터에서 사용자 지정 앱 업로드
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: joglocke, vaibhava
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
description: Microsoft 팀 관리 센터에서 조직의 앱 스토어에 사용자 지정 앱을 업로드 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: d43b19f4ada3ce6f0424a324cdea6f194575325b
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583647"
---
# <a name="publish-a-custom-app-by-uploading-an-app-package"></a>앱 패키지를 업로드 하 여 사용자 지정 앱 게시

> [!NOTE]
> 사용자 지정 팀 앱을 게시 하면 조직의 앱 스토어에 있는 사용자가 사용할 수 있습니다. 두 가지 방법으로 사용자 지정 앱을 게시할 수 있으며, 사용 하는 방법은 앱을 가져오는 방법에 따라 다릅니다. **이 문서에서는 개발자가 사용자에 게 전송 하는 앱 패키지 (.zip 형식)를 업로드 하 여 사용자 지정 앱을 게시 하는 방법에 대해 설명**합니다. 개발자가 팀 앱 제출 API를 통해 앱 <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">관리</a> 페이지에 직접 앱을 제출 하는 경우 사용자 지정 앱을 승인 하는 다른 방법이 사용 됩니다. 해당 방법에 대해 자세히 알아보려면 <a href="https://docs.microsoft.com/microsoftteams/submit-approve-custom-apps" target="_blank">팀 앱 제출 API를 통해 제출 된 사용자 지정 앱 게시</a>를 참조 하세요.

이 문서에서는 팀 앱을 개발에서 배포로 가져오는 방법에 대 한 종단 간 지침을 제공 합니다. 이 가이드는 앱의 팀 측면에 중점을 둔 것 이며 관리자 및 IT 전문가를 대상으로 합니다. 팀 앱을 개발 하는 방법에 대 한 자세한 내용은 <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">팀 개발자 설명서</a>를 참조 하세요.

![개발에서 배포 까지의 앱 개요](media/upload-custom-apps.png)

## <a name="develop"></a>개발

### <a name="create-your-app"></a>앱 만들기

Microsoft 팀 개발자 플랫폼을 사용 하면 개발자가 자신의 앱과 서비스를 쉽게 통합 하 여 생산성을 개선 하 고, 의사 결정을 더 빠르게 하 고, 기존 콘텐츠 및 워크플로를 통해 공동 작업을 만들 수 있습니다. 팀 플랫폼에 빌드된 앱은 팀 클라이언트와 서비스 및 워크플로 간의 브리지로 공동 작업 플랫폼의 컨텍스트로 직접 전환 됩니다. 자세한 내용은 <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">팀 개발자 설명서</a>를 참조 하세요.

## <a name="validate"></a>Validate

### <a name="get-the-app-package"></a>앱 패키지 다운로드

앱을 프로덕션에 사용할 준비가 되 면 개발자는 앱 패키지를 생성 해야 합니다. 이를 위해 <a href="https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio" target="_blank">앱 Studio</a> 를 사용할 수 있습니다. .Zip 형식으로 파일을 전송 합니다.

Microsoft는 <a href="https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-approval" target="_blank">이러한 지침</a> 을 사용 하 여 앱이 전역 팀 앱 스토어의 품질 및 보안 표준을 준수 하도록 합니다.

### <a name="allow-trusted-users-to-upload-custom-apps"></a>신뢰할 수 있는 사용자가 사용자 지정 앱을 업로드 하도록 허용

프로덕션 테 넌 트에서 앱이 올바르게 작동 하는지 확인 하려면 자신 및 신뢰 하는 사용자가 프로덕션 테 넌 트에서 사용자 지정 앱을 업로드 하도록 허용 해야 합니다. <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">앱 설치 정책을</a> 사용 하 여이 작업을 수행 합니다.

> [!NOTE]
> 유효성 검사를 위해 앱을 프로덕션 테 넌 트에 업로드 하는 것이 불편 하거나 신뢰 하는 사용자 에게도 문제가 되지 않는 경우이 단계를 건너뛰고 [업로드](#upload) 및 [설정 및 관리](#set-up-and-manage) 섹션의 단계를 수행 하 여 unvalidated 앱을 조직의 앱 스토어에 게시 하면 됩니다. 그런 다음 자신 및 신뢰 하는 사용자만 해당 앱에 대 한 액세스를 제한 합니다. 그러면 이러한 사용자가 조직의 app store에서 앱을 다운로드 하 여 유효성 검사를 수행할 수 있습니다. 앱의 유효성을 검사 한 후에는 동일한 권한 정책을 사용 하 여 access를 열고 앱을 프로덕션에 사용할 수 있도록 롤포워드합니다.

신뢰할 수 있는 사용자가 사용자 지정 앱을 업로드 하도록 허용 하려면 다음 단계를 따릅니다.

1. **사용자 지정 앱과 상호 작용 허용** 조직 전체 앱 설정을 사용 합니다. 실행할 작업:
    1. Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **팀 앱**으로 이동 하 여  >  **앱을 관리**하 고 **조직 전체 앱 설정을**클릭 합니다.
    2. **사용자 지정 앱**에서 **사용자 지정 앱과의 상호 작용 허용**을 켠 다음 **저장**을 클릭 합니다.
2. 전역 앱 설정 정책에서 **사용자 지정 앱 업로드** 설정을 해제 합니다. 실행할 작업:
    1. Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **팀 앱**  >  **설정 정책**으로 이동한 다음 **전역 (조직 전체 기본값)** 정책을 클릭 합니다.
    2. **사용자 지정 앱 업로드**를 해제 한 다음 **저장**을 클릭 합니다.
3. 사용자 지정 앱을 업로드 하 고 신뢰할 수 있는 사용자 집합에 할당할 수 있는 새 앱 설정 정책을 만듭니다. 실행할 작업:
    1. Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **팀 앱**  >  **설치 정책**으로 이동한 다음 **추가**를 클릭 합니다. 새 정책에 이름 및 설명을 지정 하 고, **사용자 지정 앱 업로드**를 설정한 다음 **저장**을 클릭 합니다.
    2. 만든 새 정책을 선택한 다음 **사용자 관리**를 클릭 합니다. 사용자를 검색 하 고 **추가**를 클릭 한 다음 **적용**을 클릭 합니다. 이 단계를 반복 하 여 모든 신뢰할 수 있는 사용자에 게 정책을 할당 합니다.

        !["앱 설치 정책 추가" 페이지의 스크린샷](media/manage-your-lob-apps-new-app-setup-policy.png)

    이러한 사용자는 이제 앱 매니페스트를 업로드 하 여 앱이 프로덕션 테 넌 트에서 올바르게 작동 하는지 확인할 수 있습니다.

## <a name="upload"></a>업로드가

조직의 app store 사용자가 앱을 사용할 수 있도록 하려면 앱을 업로드 합니다. Microsoft 팀 관리 센터의 <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">앱 관리</a> 페이지에서이 작업을 수행할 수 있습니다.

1. Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **팀 앱**으로  >  **앱 관리**로 이동 합니다.
2. **업로드**를 클릭 하 고 **파일 선택을**클릭 한 다음 개발자 로부터 받은 앱 패키지를 선택 합니다.

   ![관리 센터에서 앱을 업로드 하는 스크린샷](media/manage-your-lob-apps-upload-new-app.png) 

## <a name="set-up-and-manage"></a>설정 및 관리

### <a name="control-access-to-the-app"></a>앱에 대 한 액세스 제어

기본적으로 조직의 모든 사용자가 조직의 app store에서 앱에 액세스할 수 있습니다. 앱을 사용할 권한이 있는 사용자를 제한 하 고 제어 하기 위해 앱 사용 권한 정책을 만들고 할당할 수 있습니다. 자세히 알아보려면 <a href="https://docs.microsoft.com/microsoftteams/teams-app-permission-policies" target="_blank">팀에서 앱 권한 정책 관리</a>를 참조 하세요.

### <a name="pin-and-install-the-app-for-users-to-discover"></a>사용자가 검색할 수 있도록 앱을 고정 하 고 설치 합니다.

기본적으로 사용자는 조직의 app store로 이동 하 여 해당 앱을 찾거나 검색 해야 합니다. 사용자가 앱에 쉽게 액세스할 수 있도록 하려면 팀의 앱 표시줄에 앱을 고정 하면 됩니다. 이렇게 하려면 앱 설치 정책을 만들어 사용자에 게 할당 합니다. 자세히 알아보려면 <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">팀에서 앱 설정 정책 관리</a>를 참조 하세요.

### <a name="search-the-audit-log-for-teams-app-events"></a>팀에 대 한 감사 로그 앱 이벤트 검색

감사 로그를 검색 하 여 조직의 팀 앱 활동을 볼 수 있습니다. 감사 로그를 검색 하 고 감사 로그에 기록 된 팀 활동 목록을 확인 하는 방법에 대 한 자세한 내용은 <a href="https://docs.microsoft.com/microsoftteams/audit-log-events" target="_blank">팀에서 이벤트 감사 로그 검색</a>을 참조 하세요.

감사 로그를 검색 하려면 먼저 <a href="https://protection.office.com" target="_blank">보안 & 준수 센터</a>에서 감사를 설정 해야 합니다. 자세히 알아보려면 <a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">감사 로그 검색 설정 또는 해제</a>를 참조 하세요. 감사 데이터는 감사를 설정한 지점 에서만 사용할 수 있다는 점에 유의 하세요.

## <a name="discover-and-adopt"></a>검색 및 채택

앱에 대 한 사용 권한이 있는 사용자는 조직의 앱 스토어에서 찾을 수 있습니다. 조직의 사용자 지정 앱을 찾을 수 있도록 앱 페이지에서 ** *조직 이름* 으로 기본** 설정으로 이동 합니다.

![게시 된 앱을 보여 주는 앱 페이지 스크린샷 ](media/custom-app-lifecycle-discovery.png)

앱 설치 정책을 만들고 할당 한 경우 앱은 정책에 할당 된 사용자에 게 쉽게 액세스할 수 있도록 팀의 앱 표시줄에 고정 됩니다.

## <a name="update"></a>Update

앱을 업데이트 하려면 개발자가 계속 해 서 [개발](#develop) 및 [유효성 검사](#validate) 섹션의 단계를 따르세요.

Microsoft 팀 관리 센터의 앱 관리 페이지에서 앱을 업데이트할 수 있습니다. 이렇게 하려면 Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **팀 앱**앱으로 이동  >  **Manage apps**합니다. 앱 이름을 클릭 한 다음 **업데이트**를 클릭 합니다. 이렇게 하면 기존 앱이 바뀌며, 모든 앱 사용 권한 정책 및 앱 설치 정책은 업데이트 된 앱에 적용 됩니다.

### <a name="end-user-update-experience"></a>최종 사용자 업데이트 환경

대부분의 경우 앱 업데이트를 완료 하면 최종 사용자에 게 새 버전이 자동으로 표시 됩니다. 그러나 사용자에 게 완료 해야 하는 <a href="https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft 팀 매니페스트에</a> 대 한 몇 가지 업데이트가 있습니다.

* 봇이 추가 되거나 제거 되었습니다.
* 기존 봇의 "botId" 속성이 변경 됨
* 기존 봇의 "isNotificationOnly" 속성이 변경 됨
* Bot "supportsFiles" 속성이 변경 되었습니다.
* 메시징 확장이 추가 또는 제거 됨
* 새 커넥터가 추가 되었습니다.
* 새 정적 탭이 추가 되었습니다.
* 구성 가능한 새 탭이 추가 되었습니다.
* "WebApplicationInfo" 내의 속성 변경 됨

![새 버전을 사용할 수 있는 앱을 표시 하는 앱 목록 스크린샷](media/manage-your-custom-apps-update1.png)

![앱의 업그레이드 옵션 스크린샷](media/manage-your-custom-apps-update2.png)

## <a name="related-topics"></a>관련 항목

- [팀 앱 제출 API를 통해 제출 된 사용자 지정 앱 게시](submit-approve-custom-apps.md)
- [Microsoft 팀 관리 센터에서 앱 관리](manage-apps.md)
- [Teams에서 사용자 지정 앱 정책 및 설정 관리](teams-custom-app-policies-and-settings.md)
- [Teams에서 앱 사용 권한 정책 관리](teams-app-permission-policies.md)
- [Teams에서 앱 설정 정책 관리](teams-app-setup-policies.md)
