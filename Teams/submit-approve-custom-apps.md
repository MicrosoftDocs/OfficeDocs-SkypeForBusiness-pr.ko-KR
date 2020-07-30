---
title: 팀 앱 제출 API를 사용 하 여 사용자 지정 앱 제출 및 승인
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
description: Microsoft 팀에서 팀 앱 제출 API를 사용 하 여 제출한 사용자 지정 앱을 승인 하는 방법에 대해 알아봅니다.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 4c3563dc028c8566d29906e4e42a2002a197e71d
ms.sourcegitcommit: 8812db47b45d171d47e71f87e84ab1828590392d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2020
ms.locfileid: "46523727"
---
# <a name="publish-a-custom-app-submitted-through-the-teams-app-submission-api"></a>팀 앱 제출 API를 통해 제출 된 사용자 지정 앱 게시

[!INCLUDE [preview-feature](includes/preview-feature.md)]

## <a name="overview"></a>개요

> [!NOTE]
> 사용자 지정 팀 앱을 게시 하면 조직의 앱 스토어에 있는 사용자가 사용할 수 있습니다. 두 가지 방법으로 사용자 지정 앱을 게시할 수 있으며, 사용 하는 방법은 앱을 가져오는 방법에 따라 다릅니다. **이 문서에서는 개발자가 팀 앱 제출 API를 통해 제출 하는 사용자 지정 앱을 승인 하 고 게시 하는 방법에 대해 설명**합니다. 사용자 지정 앱을 업로드 하는 다른 방법은 개발자가 .zip 형식으로 앱 패키지를 보내는 경우에 사용 됩니다. 해당 방법에 대 한 자세한 내용은 [앱 패키지를 업로드 하 여 사용자 지정 앱 게시](manage-your-custom-apps.md)를 참조 하세요.
 
이 문서에서는 팀 앱을 개발에서 배포로 가져오는 방법에 대 한 종단 간 지침을 제공 합니다. 팀에서 앱 수명 주기 동안 제공 하는 연결 된 환경에 대해 개괄적으로 살펴보고 조직의 앱 스토어에서 사용자 지정 앱을 개발, 배포 및 관리 하는 방법을 간소화 합니다.

개발자가 팀 앱 제출 API를 사용 하 여 Microsoft 팀 관리 센터에 직접 사용자 지정 앱을 제출 하 고, 조직의 사용자에 대 한 앱을 관리 하는 정책을 설정 하 고, 사용자가 팀에서 검색 하는 방법을 비롯 하 여 주기의 각 단계를 다룹니다.

![개발에서 배포 까지의 앱 개요](media/custom-app-lifecycle.png)

이 가이드는 앱의 팀 측면에 중점을 둔 것 이며 관리자 및 IT 전문가를 대상으로 합니다. 팀 앱을 개발 하는 방법에 대 한 자세한 내용은 <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">팀 개발자 설명서</a>를 참조 하세요.

## <a name="develop"></a>개발

### <a name="create-the-app"></a>앱 만들기

Microsoft 팀 개발자 플랫폼을 사용 하면 개발자가 자신의 앱과 서비스를 쉽게 통합 하 여 생산성을 개선 하 고, 의사 결정을 더 빠르게 하 고, 기존 콘텐츠 및 워크플로를 통해 공동 작업을 만들 수 있습니다. 팀 플랫폼에 빌드된 앱은 팀 클라이언트와 서비스 및 워크플로 간의 브리지로 공동 작업 플랫폼의 컨텍스트로 직접 전환 됩니다. 자세한 내용은 <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">팀 개발자 설명서</a>를 참조 하세요.

### <a name="submit-the-app"></a>앱 제출

앱을 프로덕션에 사용할 준비가 되 면 개발자는 Graph API, Visual Studio 코드 등의 IDE (통합 개발 환경) 또는 플랫폼 (예: Power Apps 및 Power Virtual Agent)에서 호출할 수 있는 팀 앱 제출 API를 사용 하 여 앱을 제출할 수 있습니다. 이렇게 하면 Microsoft 팀 관리 센터의 <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">앱 관리</a> 페이지에서 앱을 사용할 수 있으며, 여기에서 관리자는이를 검토 하 고 승인할 수 있습니다. 

Microsoft Graph를 기반으로 하는 팀 앱 제출 API는 조직이 선택한 플랫폼에서 개발 하 고 팀의 사용자 지정 앱에 대 한 제출 승인 프로세스를 자동화할 수 있도록 합니다.

다음은이 앱 제출 단계가 Visual Studio 코드에서 보여 주는 예입니다.

![Visual Studio 코드에서 앱을 제출 하는 스크린샷](media/custom-app-lifecycle-submit-app.png)

이는 아직 조직의 app store에 앱을 게시 하지 않는다는 점에 유의 하세요. 이 단계에서는 앱을 조직의 앱 스토어에 게시 하기 위해 승인할 수 있는 Microsoft 팀 관리 센터에 제출 합니다.

## <a name="validate"></a>Validate

Microsoft 팀 관리 센터의 <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">앱 관리</a> 페이지 (왼쪽 탐색에서 **팀 앱**  >  **관리**로 이동)에서 조직의 모든 팀 앱에 대 한 보기를 제공 합니다. 페이지 위쪽의 **보류 중인 승인** 위젯은 사용자 지정 앱이 승인을 위해 제출 되는 시기를 알 수 있습니다.

표에서 새로 제출 된 앱에는 **제출** 됨의 **게시 상태** 와 **차단** **상태가** 자동으로 표시 됩니다. **게시 상태** 열을 내림차순으로 정렬 하 여 앱을 빠르게 찾을 수 있습니다.

![보류 중인 요청 및 앱 상태를 보여 주는 앱 관리 페이지의 스크린샷 ](media/custom-app-lifecycle-validate-app.png)

앱 이름을 클릭 하 여 앱 세부 정보 페이지로 이동 합니다. **정보** 탭에서 설명, 상태, 제출자, 앱 ID를 포함 하 여 앱에 대 한 세부 정보를 볼 수 있습니다.

![제출 된 앱에 대 한 앱 세부 정보 페이지 스크린샷](media/custom-app-lifecycle-app-details.png)

## <a name="publish"></a>부분만

사용자가 앱을 사용할 수 있도록 설정 하려면 앱을 게시 합니다.

1. Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **팀 앱**으로  >  **앱 관리**로 이동 합니다.
2. 앱 이름을 클릭 하 여 앱 세부 정보 페이지로 이동한 다음 **게시 상태** 상자에서 **게시**를 선택 합니다.

    앱을 게시 하면 게시 **상태가** **게시** 로 변경 되 고 **상태가** 자동으로 **허용**으로 변경 됩니다.

## <a name="set-up-and-manage"></a>설정 및 관리

### <a name="control-access-to-the-app"></a>앱에 대 한 액세스 제어

기본적으로 조직의 모든 사용자가 조직의 app store에서 앱에 액세스할 수 있습니다. 앱을 사용할 권한이 있는 사용자를 제한 하 고 제어 하기 위해 앱 사용 권한 정책을 만들고 할당할 수 있습니다. 자세히 알아보려면 <a href="https://docs.microsoft.com/microsoftteams/teams-app-permission-policies" target="_blank">팀에서 앱 권한 정책 관리</a>를 참조 하세요.

### <a name="pin-and-install-the-app-for-users-to-discover"></a>사용자가 검색할 수 있도록 앱을 고정 하 고 설치 합니다.

기본적으로 사용자는 조직의 app store로 이동 하 여 해당 앱을 찾거나 검색 해야 합니다. 사용자가 앱에 쉽게 액세스할 수 있도록 하려면 팀의 앱 표시줄에 앱을 고정 하면 됩니다. 이렇게 하려면 앱 설치 정책을 만들어 사용자에 게 할당 합니다. 자세히 알아보려면 <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">팀에서 앱 설정 정책 관리</a>를 참조 하세요.

## <a name="discover-and-adopt"></a>검색 및 채택

앱에 대 한 사용 권한이 있는 사용자는 조직의 앱 스토어에서 찾을 수 있습니다. 조직의 사용자 지정 앱을 찾을 수 있도록 앱 페이지에서 ** *조직 이름* 으로 기본** 설정으로 이동 합니다.

![게시 된 앱을 보여 주는 앱 페이지 스크린샷 ](media/custom-app-lifecycle-discovery.png)

앱 설치 정책을 만들고 할당 한 경우 앱은 정책에 할당 된 사용자에 게 쉽게 액세스할 수 있도록 팀의 앱 표시줄에 고정 됩니다.

## <a name="update"></a>Update

앱을 업데이트 하려면 개발자가 [개발](#develop) 섹션의 단계를 계속 수행 해야 합니다.

개발자가 게시 된 사용자 지정 앱에 대 한 업데이트를 제출 하면 <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">앱 관리</a> 페이지의 **보류 중인 승인** 위젯에 알림 메시지가 표시 됩니다. 표에서 앱의 **게시 상태가** **제출 됨 업데이트로**설정 됩니다.

![보류 중인 요청 및 앱 상태를 보여 주는 앱 관리 페이지의 스크린샷 ](media/custom-app-lifecycle-update-submitted.png)

앱 업데이트를 검토 하 고 게시 하려면 다음을 수행 합니다.

1. Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **팀 앱**으로  >  **앱 관리**로 이동 합니다.
2. 앱 이름을 클릭 하 여 앱 세부 정보 페이지로 이동한 다음 업데이트 **가능** 을 선택 하 여 업데이트 세부 정보를 검토 합니다.

    ![보류 중인 요청 및 앱 상태를 보여 주는 앱 관리 페이지의 스크린샷 ](media/custom-app-lifecycle-update-app.png)
3. 준비가 완료 되 면 **게시** 를 선택 하 여 업데이트를 게시 합니다. 이렇게 하면 기존 앱이 바뀌며 버전 번호를 업데이트 하 고 **게시 상태** 를 **게시 됨**으로 변경 합니다. 모든 앱 사용 권한 정책 및 앱 설치 정책은 업데이트 된 앱에 적용 됩니다.

    업데이트를 거부 하면 이전 버전의 앱이 게시 된 상태로 유지 됩니다.

다음 사항에 유의 하세요.

- 앱이 승인 되는 경우에는 언제 든 지 앱에 대 한 업데이트를 제출할 수 있습니다. 즉, 앱을 원래 제출한 개발자를 비롯 한 다른 개발자가 앱에 업데이트를 제출할 수 있습니다.
- 개발자가 앱을 제출 하 고 요청이 보류 중인 경우 해당 개발자만 앱에 업데이트를 제출할 수 있습니다. 다른 개발자는 앱이 승인 된 후에만 업데이트를 제출할 수 있습니다.

### <a name="update-experience-for-users"></a>사용자에 대 한 업데이트 환경

대부분의 경우 앱 업데이트를 게시 하면 사용자에 대 한 새 버전이 자동으로 표시 됩니다. 그러나 사용자에 게 완료 해야 하는 <a href="https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft 팀 매니페스트에</a> 대 한 몇 가지 업데이트가 있습니다.

* 봇이 추가 되거나 제거 되었습니다.
* 기존 봇의 "botId" 속성이 변경 됨
* 기존 봇의 "isNotificationOnly" 속성이 변경 됨
* Bot "supportsFiles" 속성이 변경 되었습니다.
* 메시징 확장이 추가 또는 제거 됨
* 새 커넥터가 추가 되었습니다.
* 새 정적 탭이 추가 되었습니다.
* 구성 가능한 새 탭이 추가 되었습니다.
* "WebApplicationInfo" 내의 속성 변경 됨

![새 버전을 사용할 수 있는 앱을 보여 주는 스크린샷](media/manage-your-custom-apps-update1.png)

![앱의 업그레이드 옵션 스크린샷](media/manage-your-custom-apps-update2.png)

## <a name="related-topics"></a>관련 항목

- [Microsoft 팀 관리 센터에서 앱 관리](manage-apps.md)
- [Teams에서 사용자 지정 앱 정책 및 설정 관리](teams-custom-app-policies-and-settings.md)
- [Teams에서 앱 사용 권한 정책 관리](teams-app-permission-policies.md)
- [Teams에서 앱 설정 정책 관리](teams-app-setup-policies.md)
