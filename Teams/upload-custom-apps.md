---
title: Microsoft Teams 관리 센터에서 사용자 지정 앱 업로드
author: cichur
ms.author: v-cichur
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
description: Microsoft Teams 관리 센터에서 조직의 앱 스토어에 사용자 지정 앱을 업로드하는 방법을 배워야 합니다.
ms.openlocfilehash: f1b5267fe1003d69c0d91349f5b6bc425df2b038
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831168"
---
# <a name="publish-a-custom-app-by-uploading-an-app-package"></a>앱 패키지를 업로드하여 사용자 지정 앱 게시

> [!NOTE]
> 사용자 지정 Teams 앱을 게시하면 조직의 앱 스토어에 있는 사용자가 사용할 수 있습니다. 사용자 지정 앱을 게시하는 방법에는 두 가지가 있으며 사용하는 방법은 앱을 다운로드하는 방법에 따라 다를 수 있습니다. 이 문서에서는 개발자가 보내는 앱 패키지(.zip 형식)를 업로드하여 사용자 지정 앱을 **게시하는 방법을 중점적으로 다겼습니다.** 사용자 지정 앱을 확인하는 다른 방법은 개발자가 Teams 앱 제출 API를 <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank"></a> 통해 앱 관리 페이지에 직접 앱을 제출할 때 사용됩니다. 해당 방법에 대한 자세한 내용은 Teams 앱 제출 API를 통해 제출된 사용자 지정 <a href="https://docs.microsoft.com/microsoftteams/submit-approve-custom-apps" target="_blank">앱 게시를 참조하세요.</a>

이 문서에서는 Teams 앱을 개발에서 배포로 검색하는 방법에 대한 전체 지침을 제공합니다. 이 지침은 앱의 Teams 측면을 중점적으로 설명하며 관리자와 IT 팀을 위한 것입니다. Teams 앱 개발에 대한 자세한 내용은 Teams 개발자 <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">설명서를 참조하세요.</a>

![개발에서 배포까지의 앱 개요](media/upload-custom-apps.png)

## <a name="develop"></a>개발

### <a name="create-your-app"></a>앱 만들기

Microsoft Teams 개발자 플랫폼을 사용하면 개발자가 자신의 앱과 서비스를 쉽게 통합하여 생산성을 개선하고, 의사 결정을 빠르게 내리고, 기존 콘텐츠 및 워크플로에 대한 공동 작업을 만들 수 있습니다. Teams 플랫폼에서 구축된 앱은 Teams 클라이언트와 서비스 및 워크플로 간의 브리지로, 공동 작업 플랫폼의 컨텍스트로 직접 연결됩니다. 자세한 내용은 Teams 개발자 <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">설명서로 이동하세요.</a>

## <a name="validate"></a>유효성 검사

### <a name="get-the-app-package"></a>앱 패키지 다운로드

앱이 프로덕션에서 사용할 준비가 되면 개발자는 앱 패키지를 생성해야 합니다. 이에 대해 <a href="https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio" target="_blank">App Studio를 사용할</a> 수 있습니다. 파일이 .zip 형식으로 전송됩니다.

Microsoft는 이러한 <a href="https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-approval" target="_blank">지침을 사용하여</a> 앱이 글로벌 Teams 앱 스토어의 품질 및 보안 표준을 준수하도록 합니다.

### <a name="allow-trusted-users-to-upload-custom-apps"></a>신뢰할 수 있는 사용자가 사용자 지정 앱을 업로드하도록 허용

앱이 프로덕션 테넌트에서 올바르게 작동하고 있는지 확인하려면 자신 및/또는 신뢰할 수 있는 사용자가 프로덕션 테넌트에 사용자 지정 앱을 업로드하도록 허용해야 합니다. 앱 설정 <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">정책을 사용하여</a> 이 작업을 실행합니다.

> [!NOTE]
> 자신의 사용자나 신뢰할 수 있는 사용자라도 유효성 검사를 위해 앱을 프로덕션 테넌트에 업로드하는 것이 불편한 경우 [](#upload) 이 [](#set-up-and-manage) 단계를 건너뛰고 업로드 및 설정 및 관리 섹션의 단계에 따라 확인되지 않은 앱을 조직의 앱 스토어에 게시할 수 있습니다. 그런 다음, 자신과 신뢰하는 사용자로만 해당 앱에 대한 액세스를 제한합니다. 이러한 사용자는 조직의 앱 스토어에서 앱을 다운로드하여 유효성 검사를 수행할 수 있습니다. 앱의 유효성이 검사된 후 동일한 사용 권한 정책을 사용하여 액세스를 열고 프로덕션 사용을 위해 앱을 롤아웃합니다.

신뢰할 수 있는 사용자가 사용자 지정 앱을 업로드할 수 있도록 허용하려면 다음 단계를 수행합니다.

1. 사용자 지정 **앱과의** 상호 작용 허용을 설정하는 전체 앱 설정. 이 작업을 위해:
    1. Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 **Teams** 앱 관리 앱으로 이동한 다음, 전체 앱 설정을  >   **클릭합니다.**
    2. 사용자 **지정 앱에서** 사용자 지정 **앱과의** 상호 작용 허용을 켜고 저장을 **클릭합니다.**
2. 전역 앱 **설정** 정책에서 사용자 지정 앱 업로드 설정을 해제합니다. 이 작업을 위해:
    1. Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 **Teams** 앱 설정 정책으로 이동한 다음  >  전역(전체 **기본)** 정책을 클릭합니다.
    2. 사용자 지정 앱 **업로드를 끄고** 저장을 **클릭합니다.**
3. 사용자 지정 앱을 업로드할 수 있는 새 앱 설정 정책을 만들고 신뢰할 수 있는 사용자 집합에 할당합니다. 이 작업을 위해:
    1. Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 **Teams** 앱 설정 정책으로 이동한 다음  >  추가를 **클릭합니다.** 새 정책에 이름과 설명을 지정하고 사용자 **지정** 앱 업로드를 설정한 다음 저장을 **클릭합니다.**
    2. 만든 새 정책을 선택한 다음 사용자 **관리를 클릭합니다.** 사용자를 검색하고 추가를 **클릭한** 다음 적용을 **클릭합니다.** 이 단계를 반복하여 신뢰할 수 있는 모든 사용자에게 정책을 할당합니다.

        !["앱 설정 정책 추가" 페이지의 스크린샷](media/manage-your-lob-apps-new-app-setup-policy.png)

    이제 이러한 사용자는 앱 매니페스트를 업로드하여 앱이 프로덕션 테넌트에서 올바르게 작동하고 있는지 확인할 수 있습니다.

## <a name="upload"></a>업로드

조직의 앱 스토어에서 사용자가 앱을 사용할 수 있도록 설정하려면 앱을 업로드합니다. Microsoft Teams 관리 <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank"></a> 센터의 앱 관리 페이지에서 이 작업을 할 수 있습니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 Teams 앱 **관리**  >  **앱으로 이동하세요.**
2. **업로드를** 클릭하고 **파일** 선택을 클릭한 다음 개발자로부터 받은 앱 패키지를 선택합니다.

   ![관리 센터에서 앱 업로드 스크린샷](media/manage-your-lob-apps-upload-new-app.png) 

## <a name="set-up-and-manage"></a>설정 및 관리

### <a name="control-access-to-the-app"></a>앱에 대한 액세스 제어

기본적으로 조직의 모든 사용자는 조직의 앱 스토어에서 앱에 액세스할 수 있습니다. 앱을 사용할 수 있는 권한이 있는 사용자들을 제한하고 제어하려면 앱 사용 권한 정책을 만들고 할당할 수 있습니다. 자세한 내용은 <a href="https://docs.microsoft.com/microsoftteams/teams-app-permission-policies" target="_blank">Teams에서 앱 사용 권한 정책 관리를 참조하세요.</a>

### <a name="pin-and-install-the-app-for-users-to-discover"></a>사용자가 검색할 수 있도록 앱 고정 및 설치

기본적으로 사용자가 조직의 앱 스토어로 이동하여 찾아보거나 검색해야 하는 앱을 찾을 수 있습니다. 사용자가 앱을 쉽게 사용할 수 있도록 Teams의 앱 바에 앱을 고정할 수 있습니다. 이렇게하려면 앱 설정 정책을 만들고 사용자에게 할당합니다. 자세한 내용은 <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">Teams에서 앱 설정 정책 관리를 참조하세요.</a>

### <a name="search-the-audit-log-for-teams-app-events"></a>Teams 앱 이벤트에 대한 감사 로그 검색

감사 로그를 검색하여 조직의 Teams 앱 활동을 볼 수 있습니다. 감사 로그를 검색하고 감사 로그에 기록된 Teams 활동 목록을 보는 방법에 대한 자세한 내용은 Teams에서 이벤트에 대한 감사 로그 검색을 <a href="https://docs.microsoft.com/microsoftteams/audit-log-events" target="_blank">참조하세요.</a>

감사 로그를 검색하려면 먼저 Security & 준수 센터에서 감사를 <a href="https://protection.office.com" target="_blank">켜야 합니다.</a> 자세한 내용은 감사 로그 검색 설정 <a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">또는 해제를 참조합니다.</a> 감사 데이터는 감사를 설정한 시점에서만 사용할 수 있습니다.

## <a name="discover-and-adopt"></a>검색 및 채택

앱에 대한 사용 권한이 있는 사용자는 조직의 앱 스토어에서 찾을 수 있습니다. 앱 **페이지에서  조직** 이름에 대한 기본 제공으로 이동하여 조직의 사용자 지정 앱을 찾을 수 있습니다.

![게시된 앱을 보여주는 앱 페이지의 스크린샷 ](media/custom-app-lifecycle-discovery.png)

앱 설정 정책을 만들어 할당한 경우 앱이 Teams의 앱 바에 고정되어 정책이 할당된 사용자를 쉽게 액세스할 수 있습니다.

## <a name="update"></a>업데이트

앱을 업데이트하기 위해 개발자는 개발 및 유효성 검사 섹션의 단계를 [계속](#develop) [따라야](#validate) 합니다.

Microsoft Teams 관리 센터의 앱 관리 페이지에서 앱을 업데이트할 수 있습니다. 이렇게하려면 Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 Teams 앱 **관리**  >  **앱으로 이동하세요.** 앱 이름을 클릭한 다음 업데이트를 **클릭합니다.** 이렇게 하면 기존 앱이 대체되어 모든 앱 사용 권한 정책 및 앱 설정 정책이 업데이트된 앱에 계속 적용됩니다.

### <a name="end-user-update-experience"></a>최종 사용자 업데이트 환경

대부분의 경우 앱 업데이트를 완료하면 최종 사용자에 대해 새 버전이 자동으로 나타납니다. 그러나 완료하려면 사용자 동의가 필요한 <a href="https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft Teams</a> 매니페스트에 대한 몇 가지 업데이트가 있습니다.

* 봇이 추가 또는 제거되었습니다.
* 기존 봇의 "botId" 속성이 변경
* 기존 봇의 "isNotificationOnly" 속성이 변경
* 봇의 "supportsFiles" 속성이 변경
* 메시징 확장이 추가 또는 제거되었습니다.
* 새 커넥터가 추가되었습니다.
* 새 정적 탭이 추가되었습니다.
* 구성 가능한 새 탭이 추가되었습니다.
* "webApplicationInfo" 내부 속성이 변경되었습니다.

![새 버전을 사용할 수 있는 앱을 보여 주며 앱 목록의 스크린샷](media/manage-your-custom-apps-update1.png)

![앱에 대한 업그레이드 옵션 스크린샷](media/manage-your-custom-apps-update2.png)

## <a name="related-topics"></a>관련 항목

- [Teams 앱 제출 API를 통해 제출된 사용자 지정 앱 게시](submit-approve-custom-apps.md)
- [Microsoft Teams 관리 센터에서 앱 관리](manage-apps.md)
- [Teams에서 사용자 지정 앱 정책 및 설정 관리](teams-custom-app-policies-and-settings.md)
- [Teams에서 앱 사용 권한 정책 관리](teams-app-permission-policies.md)
- [Teams에서 앱 설정 정책 관리](teams-app-setup-policies.md)
