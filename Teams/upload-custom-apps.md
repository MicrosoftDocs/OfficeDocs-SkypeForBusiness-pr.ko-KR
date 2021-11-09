---
title: 업로드 관리 센터에서 사용자 Microsoft Teams 앱 관리
author: HowlinWolf-92
ms.author: v-mahoffman
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
ms.localizationpriority: medium
search.appverid: MET150
description: 사용자 지정 앱을 관리 센터의 조직의 앱 스토어에 업로드하는 Microsoft Teams 대해 자세히 알아보습니다.
ms.openlocfilehash: 3869019d9becaf85da9c54ebc0ccca801980ec8a
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60846011"
---
# <a name="publish-a-custom-app-by-uploading-an-app-package"></a>앱 패키지를 업로드하여 사용자 지정 앱 게시

> [!NOTE]
> 사용자 지정 Teams 게시할 때 조직의 앱 스토어의 사용자가 사용할 수 있습니다. 사용자 지정 앱을 게시하는 방법에는 두 가지가 있으며, 사용하는 방식은 앱을 다운로드하는 방법에 따라 다를 수 있습니다. 이 문서에서는 개발자가 를 보내는 앱 패키지(.zip 형식)를 업로드하여 사용자 지정 앱을 게시하는 **방법에 대해 중점적으로 다를 수 있습니다.** 사용자 지정 앱을 사용하는 다른 방법은 개발자가 앱 제출 API를 통해 <a href="/microsoftteams/manage-apps" target="_blank"></a> 앱 관리 페이지에 직접 앱을 제출할 Teams 사용됩니다. 해당 방법에 대한 자세한 내용은 앱 제출 API 를 통해 제출된 사용자 지정 앱 <a href="/microsoftteams/submit-approve-custom-apps" target="_blank">게시를 Teams 참조하세요.</a>

이 문서에서는 개발에서 배포로 배포에 Teams 앱으로 데려오는 방법에 대한 종단 Teams 지침을 제공합니다. 이 지침은 앱의 Teams 측면에 중점을 두며 관리자 및 IT 프로를 위한 것입니다. 앱 개발에 대한 Teams 자세한 내용은 개발자 Teams <a href="/microsoftteams/platform" target="_blank">참조하세요.</a>

![개발에서 배포까지 앱의 개요입니다.](media/upload-custom-apps.png)

## <a name="develop"></a>개발

### <a name="create-your-app"></a>앱 만들기

개발자 Microsoft Teams 플랫폼을 사용하면 개발자가 사용자 자신의 앱 및 서비스를 통합하여 생산성을 향상하고, 더 빠르게 의사 결정을 내릴 수 있으며, 기존 콘텐츠 및 워크플로에 대한 공동 작업을 쉽게 만들 수 있습니다. Teams 플랫폼에 구축된 앱은 Teams 클라이언트와 서비스 및 워크플로 간의 브리지로, 공동 작업 플랫폼의 컨텍스트로 바로 연결됩니다. 자세한 내용은 개발자 Teams <a href="/microsoftteams/platform" target="_blank">로 이동하세요.</a>

## <a name="validate"></a>유효성 검사

### <a name="get-the-app-package"></a>앱 패키지 다운로드

앱이 프로덕션에서 사용할 준비가 된 경우 개발자는 앱 패키지를 생성해야 합니다. 이 경우 <a href="/microsoftteams/platform/get-started/get-started-app-studio" target="_blank">App Studio를 사용할</a> 수 있습니다. 파일 형식에 따라 .zip 합니다.

Microsoft는 이러한 <a href="/microsoftteams/platform/publishing/office-store-approval" target="_blank">지침을</a> 사용하여 앱이 글로벌 앱 스토어의 품질 및 보안 Teams 확인합니다.

### <a name="allow-trusted-users-to-upload-custom-apps"></a>신뢰할 수 있는 사용자가 사용자 지정 앱을 업로드하도록 허용

앱이 프로덕션 테넌트에서 올바르게 작동하고 있는지 확인하려면 자신 및/또는 신뢰할 수 있는 사용자가 프로덕션 테넌트에서 사용자 지정 앱을 업로드하도록 허용해야 합니다. 앱 설정 <a href="/microsoftteams/teams-app-setup-policies" target="_blank">정책을 사용하여</a> 이 작업을 실행합니다.

> [!NOTE]
> 직접 또는 신뢰할 수 있는 사용자에 대해 프로덕션 테넌트에 앱을 업로드하는 것이 불편한 경우 이 단계를 건너뛰고 업로드 [](#set-up-and-manage) 섹션을 설정하고 관리하여 평가되지 않은 앱을 조직의 앱 스토어에 게시할 수 있습니다. [](#upload) 그런 다음, 자신과 신뢰하는 사용자만 해당 앱에 대한 액세스를 제한합니다. 그런 다음 이러한 사용자는 조직의 앱 스토어에서 앱을 다운로드하여 유효성 검사를 수행할 수 있습니다. 앱이 유효성을 검사한 후 동일한 권한 정책을 사용하여 액세스를 열고 프로덕션 사용을 위해 앱을 롤아웃합니다.

신뢰할 수 있는 사용자가 사용자 지정 앱을 업로드할 수 있도록 허용하려면 다음 단계를 따릅니다.

1. 사용자 지정 앱 또는 전체 **앱** 설정과의 상호 작용 허용을 켜습니다. 이 작업을 위해:
    1. 관리 센터의 왼쪽 탐색 Microsoft Teams 앱 관리 Teams 앱 관리로 이동한 다음,  >   **Org-wide 앱** 설정을 클릭합니다.
    2. 사용자 **지정 앱에서** 사용자 지정 **앱과의 상호 작용 허용을 켜고** 저장을 **클릭합니다.**
2. 전역 앱 **업로드 설정에서** 사용자 지정 앱 설정을 해제합니다. 이 작업을 위해:
    1. 관리 센터의 왼쪽 탐색에서 Microsoft Teams 앱 Teams 설정 정책으로 이동한 다음  >   **전역(org-wide default)** 정책을 클릭합니다.
    2. 사용자 **업로드 앱을 끄고** 저장을 **클릭합니다.**
3. 사용자 지정 앱을 업로드하고 신뢰할 수 있는 사용자 집합에 할당할 수 있는 새 앱 설정 정책을 만들 수 있습니다. 이 작업을 위해:
    1. 관리 센터의 왼쪽 탐색에서 Microsoft Teams 앱 설치 정책으로 Teams 이동한 다음 추가를  >   **클릭합니다.** 새 정책에 이름과 설명을 지정하고 사용자 **업로드** 설정한 다음 저장을 **클릭합니다.**
    2. 만든 새 정책을 선택한 다음 사용자 **관리를 클릭합니다.** 사용자를 검색하고 **추가를** 클릭한 다음 적용을 **클릭합니다.** 이 단계를 반복하여 신뢰할 수 있는 모든 사용자에게 정책을 할당합니다.

        !["앱 설정 정책 추가" 페이지의 스크린샷](media/manage-your-lob-apps-new-app-setup-policy.png)

    이제 이러한 사용자는 앱 매니페스트를 업로드하여 앱이 프로덕션 테넌트에서 올바르게 작동하고 있는지 확인할 수 있습니다.

## <a name="upload"></a>업로드

조직의 앱 스토어의 사용자가 앱을 사용할 수 있도록하려면 앱을 업로드합니다. 관리 센터의 앱 <a href="/microsoftteams/manage-apps" target="_blank"></a> 관리 페이지에서 Microsoft Teams 수 있습니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색 창에서 **Teams 앱** > **앱 관리** 로 이동합니다.
2. 업로드 클릭하고 파일 선택을 **클릭한** 다음 개발자로부터 받은 앱 패키지를 선택합니다.

   ![관리 센터에 앱을 업로드하는 스크린샷.](media/manage-your-lob-apps-upload-new-app.png) 

## <a name="set-up-and-manage"></a>설정 및 관리

### <a name="control-access-to-the-app"></a>앱에 대한 액세스 제어

기본적으로 조직의 모든 사용자는 조직의 앱 스토어에서 앱에 액세스할 수 있습니다. 앱을 사용할 권한이 있는 사용자에 대한 제한 및 제어를 위해 앱 사용 권한 정책을 만들고 할당할 수 있습니다. 자세한 내용은 <a href="/microsoftteams/teams-app-permission-policies" target="_blank">Teams에서 앱 권한 정책 관리</a>를 참조하세요.

### <a name="pin-and-install-the-app-for-users-to-discover"></a>사용자가 검색할 앱 고정 및 설치

기본적으로 사용자가 조직의 앱 스토어로 이동하여 찾아보거나 검색해야 하는 앱을 찾으면 됩니다. 사용자가 앱에 쉽게 도착할 수 있도록 앱 표시줄에 앱을 고정할 수 Teams. 이렇게하려면 앱 설정 정책을 만들고 사용자에게 할당합니다. 자세한 내용은 <a href="/microsoftteams/teams-app-setup-policies" target="_blank">Teams에서 앱 설정 정책 관리</a>를 참조하세요.

### <a name="search-the-audit-log-for-teams-app-events"></a>앱 이벤트에 대한 감사 Teams 검색

감사 로그를 검색하여 조직의 앱 Teams 볼 수 있습니다. 감사 로그를 검색하고 감사 로그에 Teams 활동 목록을 보는 방법에 대한 자세한 내용은 감사 로그에서 이벤트에 대한 감사 <a href="/microsoftteams/audit-log-events" target="_blank">로그 검색을 Teams.</a>

감사 로그를 검색하려면 먼저 <a href="https://protection.office.com" target="_blank">보안 및 준수 센터</a>에서 감사를 켜야 합니다. 자세한 내용은 <a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">감사 로그 검색 설정 및 해제</a>를 참조하세요. 감사 데이터는 감사가 켜진 시점부터만 사용할 수 있습니다.

## <a name="discover-and-adopt"></a>검색 및 채택

앱에 대한 권한이 있는 사용자는 조직의 앱 스토어에서 찾을 수 있습니다. 앱 **페이지에서** 조직 이름에 대한 기본 제공 페이지로 이동하여 조직의 사용자 지정 앱을 찾으십시오.

![게시된 앱을 보여주는 앱 페이지의 스크린샷.](media/custom-app-lifecycle-discovery.png)

앱 설치 정책을 만들어 할당한 경우 앱이 정책에 할당된 사용자에 Teams 앱 표시줄에 고정됩니다.

## <a name="update"></a>업데이트

앱을 업데이트하기 위해 개발자는 개발 및 [](#develop) 유효성 검사 섹션의 단계를 계속 [따라야](#validate) 합니다.

관리 센터의 앱 관리 페이지에서 앱을 Microsoft Teams 수 있습니다. 이렇게하려면 관리 센터의 왼쪽 Microsoft Teams 앱 관리 **Teams**  >  **로 이동하세요.** 앱 이름을 클릭한 다음 업데이트를 **클릭합니다.** 이렇게 하면 기존 앱이 대체되어 업데이트된 앱에 대한 모든 앱 사용 권한 정책 및 앱 설정 정책이 계속 적용됩니다.

### <a name="end-user-update-experience"></a>최종 사용자 업데이트 환경

대부분의 경우 앱 업데이트를 완료한 후 최종 사용자에게 새 버전이 자동으로 나타납니다. 그러나 사용자 수락을 <a href="/microsoftteams/platform/resources/schema/manifest-schema" target="_blank"></a> 완료해야 하는 Microsoft Teams 매니페스트에 대한 몇 가지 업데이트가 있습니다.

* 봇이 추가되거나 제거되었습니다.
* 기존 봇의 "botId" 속성이 변경된 경우
* 기존 봇의 "isNotificationOnly" 속성이 변경된 경우
* 봇의 "supportsFiles" 속성이 변경된 경우
* 메시징 확장이 추가되거나 제거되었습니다.
* 새 커넥터가 추가되었습니다.
* 새 정적 탭이 추가되었습니다.
* 새 구성 가능한 탭이 추가되었습니다.
* "webApplicationInfo" 내부 속성이 변경되었습니다.

![새 버전을 사용할 수 있는 앱을 보여 주며 앱 목록의 스크린샷입니다.](media/manage-your-custom-apps-update1.png)

![앱에 대한 업그레이드 옵션 스크린샷.](media/manage-your-custom-apps-update2.png)

## <a name="related-topics"></a>관련 항목

- [앱 제출 API를 통해 제출된 사용자 Teams 게시](submit-approve-custom-apps.md)
- [관리 센터에서 앱 Microsoft Teams 관리](manage-apps.md)
- [Teams에서 사용자 지정 앱 정책 및 설정 관리](teams-custom-app-policies-and-settings.md)
- [Teams에서 앱 사용 권한 정책 관리](teams-app-permission-policies.md)
- [Teams에서 앱 설정 정책 관리](teams-app-setup-policies.md)