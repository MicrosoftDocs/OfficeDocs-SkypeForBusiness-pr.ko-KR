---
title: 앱을 허용하는 관리자에 대한 사용자 요청
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
ms.subservice: teams-apps
audience: admin
ms.collection:
- M365-collaboration
- m365-frontline
ms.reviewer: mhayrapetyan
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.manageapps.overview
description: 조직에서 차단된 앱을 허용하도록 최종 사용자 요청을 관리하고 구성하는 방법을 알아봅니다.
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: 122d41de6f1cb5ea67a5ce85ba9f8f7d02e26339
ms.sourcegitcommit: 41a75f1ba5ceb09f8db7d468aa41b63a89ab9c30
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2022
ms.locfileid: "67647542"
---
# <a name="manage-user-requests"></a>사용자 요청 관리

조직에서 차단하는 앱은 최종 사용자 생산성 및 협업에 영향을 줄 수 있습니다. Teams 스토어에서 사용할 수 있지만 조직에서 차단된 앱은 최종 사용자가 사용할 수 없습니다. 그러나 정보를 유지하기 위해 최종 사용자는 차단된 앱을 보고, 앱의 정보를 보고, 서버의 사용 사례를 볼 수 있습니다. 사용자는 요청을 평가한 후 Teams에서 이러한 앱을 사용하도록 관리자 승인을 요청합니다.

이 기능은 조직 내에서 앱에 대한 수요에 대한 신호를 제공합니다. 앱에 대한 총 요청 수를 쉽게 볼 수 있습니다. 이를 통해 조직에서 허용할 앱에 대해 정보에 입각한 결정을 내릴 수 있습니다.

사용자에게 허용되거나 차단된 앱에 대한 완전한 제어를 유지합니다. 앱을 허용하도록 선택하는 경우 컨트롤 및 UI에서 앱을 관리하는 것은 동일하게 유지됩니다.

* 기본 옵션은 사용자 요청을 [보고 요청된 앱을 허용할](#view-user-requests) 수 있는 Teams 관리 센터에서 사용자 요청을 보냅니다.

   :::image type="content" source="media/user-request-blocked-apps.png" alt-text="관리자에게 차단된 앱을 승인하도록 요청하는 옵션을 보여 주는 스크린샷":::

* 사용자 지정을 사용하면 조직에 가장 적합한 [최종 사용자 환경을 구성할](#modify-the-default-setting-to-receive-end-user-requests) 수 있습니다. Teams 앱 스토어에서 차단된 앱의 최종 사용자에게 표시되는 사용자 지정 지침을 제공하고 사용자를 내부 사이트로 보내 요청을 수집하도록 할 수 있습니다.

   :::image type="content" source="media/user-request-blocked-apps-redirected.png" alt-text="관리자가 허용 앱 요청 URL을 내부 사이트로 리디렉션할 때 저장소의 앱에 대한 최종 사용자 환경을 보여 주는 스크린샷.":::

## <a name="modify-the-default-setting-to-receive-end-user-requests"></a>최종 사용자 요청을 받도록 기본 설정 수정

사용자 지정 메시지를 구성하고 사용자를 조직별 URL로 리디렉션하여 앱 승인을 요청하려면 다음 단계를 수행합니다.

1. Teams 관리 센터에 로그인하고 **Teams 앱** > **[관리](https://admin.teams.microsoft.com/policies/manage-apps)** 페이지에 액세스합니다.

1. 조직 전체 앱 설정을 선택합니다.

1. Teams 클라이언트 저장소에 사용자 지정 메시지 또는 명령을 표시하려면 사용자 요청 구성에 문자 메시지를 제공합니다.

1. 조직별 URL을 제공하여 사용자 요청을 수집하려면 다음을 수행합니다.

   1. 외부 도구 옵션으로 리디렉션 요청을 켜기로 변경합니다.
   1. 조직별 사용자 지정 URL을 제공합니다.

      :::image type="content" source="media/user-request-config-org-wide-setting.png" alt-text="조직 전체 설정 UI에서 앱 차단을 해제하도록 사용자 요청에 대한 URL 사용자 지정을 토글하는 스크린샷.":::

1. **저장** 을 선택합니다.

## <a name="view-user-requests"></a>사용자 요청 보기

기본 방법으로 받은 최종 사용자 요청은 Teams 관리 센터에 표시됩니다. 요청을 쉽게 보고 관리할 수 있습니다. 최종 사용자 요청을 확인하기 위해 정기적인 심사를 수행하는 것이 좋습니다. 앱을 보고 허용하려면 다음 단계를 수행합니다.

1. Teams 관리 센터에 로그인하고 **Teams 앱** > **[관리](https://admin.teams.microsoft.com/policies/manage-apps)** 페이지에 액세스합니다.

1. **사용자별 요청** 열을 표시하도록 선택합니다. 열을 정렬할 수도 있습니다.

   :::image type="content" source="media/user-requests-tac.png" alt-text="Teams 관리 센터에서 사용자 요청에 대한 열과 정렬할 수 있는 열을 보여 주는 스크린샷" lightbox="media/user-requests-tac-expanded.png":::

1. 허용하려는 앱 세부 정보 페이지를 열려면 앱의 이름을 선택합니다.

1. **요청 관리를** 선택합니다.

   :::image type="content" source="media/apps-manage-user-requests.png" alt-text="앱 세부 정보 페이지의 요청 관리 옵션을 보여 주는 스크린샷" lightbox="media/apps-manage-user-requests-expanded.png":::

1. 팝업 대화 상자에 표시된 대로 다음 단계 중 하나 이상을 수행합니다. 앱을 승인하는 단계는 앱을 차단하는 방법에 따라 다릅니다.

   * 권한 정책을 사용하여 앱이 차단된 경우 [권한 정책을 수정합니다](teams-app-permission-policies.md).
   * 모든 사용자에 대해 앱이 차단된 경우 [앱을 허용](manage-apps.md#allow-and-block-apps)합니다.
   * 모든 사용자에 대해 모든 앱이 차단된 경우 [조직 전체 설정을 수정](manage-apps.md#manage-org-wide-app-settings)합니다.

1. 필요에 따라 사용자 지정 구성을 조직별 URL로 전환하려면 사용자 요청 관리 대화 상자에서 사용자 요청 구성 링크를 선택합니다. [최종 사용자 요청 환경을 구성할](#modify-the-default-setting-to-receive-end-user-requests) 수 있는 조직 전체 앱 설정 창이 열립니다.

Teams 관리 센터에서 요청을 받은 후 앱을 허용하는 경우 Teams는 최종 사용자에게 요청이 수행됨을 알리지 않습니다. 사용자는 Teams 스토어에서 앱을 확인하여 앱이 허용되는지 확인할 수 있습니다. 앱 추가 옵션은 사용자가 앱을 허용한 후에 사용할 수 있습니다. 조직별 방법을 통해 요청을 받은 후 앱을 허용하는 경우 최종 사용자에게 상태 업데이트를 제공하는 내부 메커니즘이 적용됩니다.

앱 요청 수를 0으로 다시 설정하려면 요청을 해제합니다. 앱만 허용해도 요청 카운터는 0으로 다시 설정되지 않습니다.

## <a name="dismiss-user-requests"></a>사용자 요청 해제

앱을 허용하는 요청을 해제하려면 다음 단계를 수행합니다.

1. 사용자 요청을 거부할 앱의 이름을 선택합니다.
1. **요청 관리** 를 선택하고 대화 상자에서 **모든 요청 거부** 를 선택합니다.

   :::image type="content" source="media/dismiss-user-requests-apps.png" alt-text="관리자는 앱을 허용해 사용자 요청을 승인하거나 요청을 거부한 채 아무 조치도 취하지 않을 수 있습니다.":::

요청을 해제하는 경우 최종 사용자에게 요청이 수행됨을 알리지 않습니다. 앱을 허용하는 요청을 해제하면 관리 센터의 요청 수가 0으로 다시 설정됩니다. 또한 요청을 해제한 후 몇 시간 후에 최종 사용자가 동일한 앱의 허용을 다시 요청할 수 있습니다.

## <a name="related-article"></a>관련 문서

* [타사 앱을 관리하는 방법에 대한 개요](manage-apps.md)입니다.
