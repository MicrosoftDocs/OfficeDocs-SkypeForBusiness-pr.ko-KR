---
title: Microsoft Teams 관리 센터에서 사용자 지정 앱 업로드
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-apps
audience: Admin
ms.date: 09/26/2022
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
description: 조직의 Teams 앱 스토어에 사용자 지정 앱을 업로드하는 방법을 알아봅니다.
ms.openlocfilehash: 8886c2c0904e7ca9c9e0de1e5641b8587ffe50bf
ms.sourcegitcommit: c2d8c7f779f4f938f8355632ecfbfc9147b53bb2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2022
ms.locfileid: "68738584"
---
# <a name="publish-a-custom-app-by-uploading-an-app-package"></a>앱 패키지를 업로드하여 사용자 지정 앱 게시

> [!NOTE]
> 사용자 지정 Teams 앱을 게시하면 조직의 앱 스토어에 있는 사용자가 사용할 수 있습니다. 사용자 지정 앱을 게시하는 방법에는 두 가지가 있으며 사용 방법은 앱을 얻는 방법에 따라 다릅니다. **이 문서에서는 개발자가 보낸 앱 패키지(.zip 형식)를 업로드하여 사용자 지정 앱을 게시하는 방법에 대해 중점적으로 설명합니다**. 사용자 지정 앱을 승인하는 다른 방법은 개발자가 Teams App Submission API를 통해 [앱 관리](manage-apps.md) 페이지에 직접 앱을 제출할 때 사용됩니다. 이 방법에 대한 자세한 내용은 [Teams App Submission API를 통해 제출된 사용자 지정 앱 게시](submit-approve-custom-apps.md)를 참조하세요.

이 문서에서는 Teams 앱을 개발에서 배포, 검색으로 전환하는 방법에 대한 종단 간 지침을 제공합니다. 이 지침은 앱의 Teams 측면에 중점을 두고 있으며 관리자와 IT 전문가를 대상으로 합니다. Teams 앱 개발에 대한 자세한 내용은 [Teams 개발자 설명서](/microsoftteams/platform/)를 참조하세요.

:::image type="content" source="media/upload-custom-apps.png" alt-text="개발에서 배포까지의 앱 개요.":::

## <a name="create-your-app"></a>앱 만들기

Microsoft Teams 개발자 플랫폼을 사용하면 개발자가 자신의 앱과 서비스를 쉽게 통합하여 생산성을 높이고 더 빠르게 의사 결정을 내리며 기존 콘텐츠 및 워크플로를 중심으로 공동 작업을 수행할 수 있습니다. Teams 플랫폼에 구축된 앱은 Teams 클라이언트와 서비스 및 워크플로를 연결하여 공동 작업 플랫폼의 컨텍스트로 직접 가져옵니다. 자세한 내용은 [Teams 개발자 문서](/microsoftteams/platform/)를 참조하세요.

## <a name="validate"></a>확인

### <a name="receive-the-app-package"></a>앱 패키지 받기

앱이 프로덕션 환경에서 사용할 준비가 되면 개발자는 [개발자 포털](/microsoftteams/platform/concepts/build-and-test/manage-your-apps-in-developer-portal)을 사용하여 앱 패키지를 생성합니다. 개발자는 앱 패키지를 .zip 형식으로 공유합니다.

Teams 스토어의 모든 앱은 Teams 앱 스토어의 앱 품질 및 보안 표준을 준수하기 위해 필수 앱 [유효성 검사를](overview-of-app-validation.md) 통과합니다. 또한 Microsoft는 앱 개발자가 향상된 규정 준수, 보안 및 개인 정보 보호 제어를 나타내는 선택적 [앱 규정 준수 프로그램](overview-of-app-certification.md)에 참여할 것을 적극 권장합니다. 자세한 내용은 [Teams 앱 유효성 검사 가이드라인](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/teams-store-validation-guidelines)을 참조하세요.

### <a name="allow-trusted-users-to-upload-custom-apps"></a>신뢰할 수 있는 사용자가 사용자 지정 앱을 업로드하도록 허용

앱이 프로덕션 테넌트에서 올바르게 작동하는지 확인하려면 자신 및/또는 신뢰할 수 있는 사용자가 프로덕션 테넌트에서 사용자 지정 앱을 업로드하도록 허용해야 합니다. 이를 위해 [앱 설정 정책](teams-app-setup-policies.md)을 사용합니다.

> [!NOTE]
> 유효성 검사를 위해 프로덕션 테넌트에 앱을 업로드하는 것이 불편한 경우 자신이나 신뢰할 수 있는 사용자라도 이 단계를 건너뛰고 [업로드](#upload) 및 [설정 및 관리](#set-up-and-manage) 섹션의 단계에 따라 유효성이 검사되지 않은 앱 스토어를 조직의 앱에 게시할 수 있습니다. 그런 다음 해당 앱에 대한 액세스를 자신과 신뢰할 수 있는 사용자에게만 제한하세요. 그런 다음 이러한 사용자는 조직의 앱 스토어에서 앱을 가져와 유효성 검사를 수행할 수 있습니다. 앱이 검증된 후 동일한 권한 정책을 사용하여 액세스를 열고 프로덕션 용도로 앱을 출시합니다.

신뢰할 수 있는 사용자가 사용자 지정 앱을 업로드하도록 허용하려면 다음 단계를 따르세요.

1. **사용자 지정 앱과의 상호 작용 허용** 조직 전체 앱 설정을 켭니다. 이를 수행하려면 다음을 수행하세요.

    1. Microsoft Teams 관리 센터의 왼쪽 탐색 영역에서 **Teams 앱** > **앱 관리** 로 이동한 다음 **조직 전체 앱 설정을** 선택합니다.

    1. **사용자 지정 앱** 에서 **사용자 지정 앱과의 상호 작용 허용을** 켜고 **저장** 을 선택합니다.

1. 전역 앱 설정 정책에서 **사용자 지정 앱 업로드** 설정을 끕니다. 이를 수행하려면 다음을 수행하세요.

    1. Microsoft Teams 관리 센터의 왼쪽 탐색 영역에서 **Teams 앱** > **설정 정책** 으로 이동한 다음 **전역(조직 전체 기본값)** 정책을 선택합니다.

    1. **사용자 지정 앱 업로드** 를 끈 다음 **저장** 을 선택합니다.

1. 사용자 지정 앱 업로드를 허용하는 새 앱 설정 정책을 만들고 신뢰할 수 있는 사용자 집합에 할당합니다. 이를 수행하려면 다음을 수행하세요.

    1. Microsoft Teams 관리 센터의 왼쪽 탐색 영역에서 **Teams 앱** > **설정 정책** 으로 이동한 다음 **추가** 를 선택합니다. 새 정책에 이름과 설명을 지정하고 **사용자 지정 앱 업로드** 를 켜고 **저장** 을 선택합니다.

    1. 만든 새 정책을 선택한 다음 **, 사용자 관리를** 선택합니다. 사용자를 검색하고 **추가** 를 선택한 다음 **적용** 을 선택합니다. 이 단계를 반복하여 신뢰할 수 있는 모든 사용자에게 정책을 할당합니다.

       :::image type="content" source="media/manage-your-lob-apps-new-app-setup-policy.png" alt-text="앱 설정 정책 추가 페이지의 스크린샷.":::

이제 이러한 사용자는 앱 매니페스트를 업로드하여 앱이 프로덕션 테넌트에서 올바르게 작동하는지 확인할 수 있습니다.

## <a name="upload"></a>업로드

조직의 앱 스토어에서 사용자가 앱을 사용할 수 있도록 하려면 앱을 업로드하세요.

1. Microsoft Teams 관리 센터의 왼쪽 탐색 메뉴에서 **Teams 앱** > **[앱 관리](https://admin.teams.microsoft.com/policies/manage-apps)** 로 이동합니다.

1. **업로드** 를 선택하고 **, 업로드** 를 선택하고, 개발자로부터 받은 앱 패키지를 선택하고, **열기** 를 선택합니다.

   :::image type="content" source="media/manage-your-lob-apps-upload-new-app.png" alt-text="관리 센터의 사용자 지정 앱 업로드 스크린샷":::

## <a name="set-up-and-manage"></a>설정 및 관리

### <a name="control-access-to-the-app"></a>앱에 대한 액세스 제어

기본적으로 조직의 모든 사용자는 조직의 앱 스토어에서 앱에 액세스할 수 있습니다. 앱 사용 권한이 있는 사용자를 제한하고 제어하기 위해 앱 권한 정책을 만들고 할당할 수 있습니다. 자세한 내용은 [Teams에서 앱 권한 정책 관리](teams-app-permission-policies.md)를 참조하세요.

### <a name="pin-and-install-the-app-for-users-to-discover"></a>사용자가 검색할 수 있도록 앱을 고정하고 설치하세요.

기본적으로 사용자가 앱을 찾으려면 조직의 앱 스토어로 이동하여 찾아보거나 검색해야 합니다. 사용자가 앱에 쉽게 액세스할 수 있도록 Teams의 앱 표시줄에 앱을 고정할 수 있습니다. 앱을 고정하려면 앱 설정 정책을 만들고 사용자에게 할당합니다. 자세한 내용은 [Teams에서 앱 설정 정책 관리](teams-app-setup-policies.md)를 참조하세요.

### <a name="search-the-audit-log-for-teams-app-events"></a>Teams 앱 이벤트에 대한 감사 로그 검색

감사 로그를 검색하여 조직의 Teams 앱 활동을 볼 수 있습니다. Teams 활동 감사에 대한 자세한 내용은 [팀에서 이벤트에 대한 감사 로그 검색](audit-app-management-activities.md)을 참조하세요.

감사 로그를 검색하려면 먼저 [보안 및 준수 센터](https://sip.protection.office.com/homepage)에서 감사를 켜야 합니다. 자세한 내용은 [감사 로그 검색 설정 및 해제](/microsoft-365/compliance/turn-audit-log-search-on-or-off)를 참조하세요. 감사 데이터는 감사가 켜진 시점부터만 사용할 수 있습니다.

## <a name="discover-and-adopt"></a>발견 및 채택

앱에 대한 권한이 있는 최종 사용자는 조직의 앱 스토어에서 앱을 찾을 수 있습니다. 조직의 사용자 지정 앱을 찾으려면 앱 페이지에서 ***조직 이름*** 용으로 빌드로 이동하세요.

:::image type="content" source="media/custom-app-lifecycle-discovery.png" alt-text="조직용으로 게시된 사용자 지정 앱을 보여주는 Teams 스토어 스크린샷" lightbox="media/custom-app-lifecycle-discovery.png":::

앱 설정 정책을 만들고 할당한 경우 정책이 할당된 사용자가 쉽게 액세스할 수 있도록 앱이 Teams의 앱 표시줄에 고정됩니다.

## <a name="update-a-custom-app"></a>사용자 지정 앱 업데이트

앱을 업데이트하려면 개발자는 [앱 만들기](#create-your-app) 및 [확인](#validate) 섹션의 단계를 따릅니다.

Microsoft Teams 관리 센터의 앱 관리 페이지에서 앱을 업데이트할 수 있습니다. 앱을 업데이트하려면 Microsoft Teams 관리 센터의 왼쪽 탐색 영역에서 **Teams 앱****앱 관리** 로  >  이동합니다. 앱 **이름을 선택한 다음** 업데이트를 선택합니다. 앱을 업데이트하면 기존 앱이 대체되고 모든 앱 사용 권한 정책 및 앱 설정 정책이 업데이트된 앱에 계속 적용됩니다.

### <a name="end-user-update-experience"></a>최종 사용자 업데이트 환경

대부분의 경우 새 버전의 앱을 게시한 후 Teams 클라이언트에 앱을 추가한 최종 사용자에 대해 자동으로 업데이트됩니다. 자세한 내용은 [최종 사용자 앱 업데이트 환경을 참조하세요](apps-update-experience.md).

## <a name="remove-a-custom-app-from-your-organizations-store"></a>조직의 스토어에서 사용자 지정 앱 제거

앱을 제거하려면 다음 단계를 따르세요.

1. Teams 관리 센터에 로그인합니다.
1. **Teams 앱** > **[앱 관리](https://admin.teams.microsoft.com/policies/manage-apps)** 페이지에 액세스합니다.
1. 앱 이름을 클릭하여 앱 세부 정보 페이지를 엽니다.
1. 앱 배너 옆에 있는 **작업** > **삭제** 를 선택합니다.
1. 대화 상자에서 **삭제** 를 선택합니다.

## <a name="related-articles"></a>관련 기사

* [Teams 앱 제출 API를 통해 제출된 사용자 지정 앱 게시](submit-approve-custom-apps.md)
* [Microsoft Teams 관리 센터에서 앱 관리](manage-apps.md)
* [사용자 지정 앱에 대한 정책 및 설정 관리](teams-custom-app-policies-and-settings.md)
* [Teams에서 앱 사용 권한 정책 관리](teams-app-permission-policies.md)
* [Teams에서 앱 설정 정책 관리](teams-app-setup-policies.md)
