---
title: Microsoft Teams의 앱 업데이트 환경
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-apps
audience: Admin
ms.date: 10/22/2022
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 이 문서에서는 Microsoft Teams의 Microsoft 앱, 사용자 지정 앱 및 타사 앱을 업데이트하는 방법과 관리자가 이를 용이하게 하는 방법을 알아봅니다.
ms.openlocfilehash: d419e1ed29c6a1cd7a7390bdc0d5eb69371d8547
ms.sourcegitcommit: 22f66e314e631b3c9262c5c7dc5664472f42971e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2022
ms.locfileid: "68912797"
---
# <a name="role-of-an-admin-in-upgrading-teams-apps"></a>Teams 앱을 업그레이드하는 관리자 역할

Teams 관리자는 최종 사용자가 최신 버전의 앱을 가져오는 데 도움을 줄 수 있습니다. 이렇게 하려면 다음 작업 중 하나 또는 둘 다를 수행합니다.

* 앱 개발자 또는 공급업체가 새 버전을 제공하는 경우 Teams 스토어에서 사용할 수 있는 타사 앱을 [업데이트](#updates-to-third-party-apps)합니다.
* 개발자가 새 버전을 제출할 때 조직에서만 사용할 수 있는 [사용자 지정 앱을 업데이트](#updates-to-custom-apps)합니다.

## <a name="updates-to-third-party-apps"></a>타사 앱에 업데이트

사용자가 앱을 설치하고 사용하려면 앱에 필요한 서비스 및 정보에 액세스할 수 있는 권한을 부여해야 합니다. 대부분의 경우 Teams 스토어에서 설치된 앱의 새 버전을 사용할 수 있는 경우 모든 사용자에 대해 앱이 자동으로 업데이트됩니다. 그러나 새 버전의 앱에서 몇 가지 특정 변경 내용을 변경하려면 사용자 권한이 다시 필요합니다. 이 반복 사용자 동의는 기능 또는 개인 정보에 대한 액세스와 같은 변경 내용에 대한 인식을 보장합니다. Teams 관리자는 [사용자를 대신하여 앱에 권한을 제공할](app-permissions-admin-center.md) 수 있습니다.

앱 개발자가 앱에 대해 다음 중 하나 이상을 변경하는 경우 최종 사용자는 앱 업데이트를 승인해야 합니다.

* 봇을 추가합니다. 속성을 사용하여 봇의 ID를 변경합니다 `botId` .
* 봇의 `isNotificationOnly` 알림을 변경할 수 있는 기존 봇의 속성을 변경합니다.
* 기존 봇의 , `SupportsVideo`및 `SupportsFiles` 속성을 변경`SupportsCalling`하여 파일을 호출, 비디오 재생 및 업로드 또는 다운로드하는 기능을 추가합니다.
* 권한 부여에서 사용 권한을 추가하거나 제거합니다.
* 메시징 확장을 추가하거나 제거하거나, 그룹 탭을 추가하거나, 커넥터를 추가하거나, 채널을 추가합니다.
* 매니페스트 파일의 에서 [`webApplicationInfo`](/microsoftteams/platform/resources/schema/manifest-schema#webapplicationinfo) 매개 변수를 변경합니다.

<!--- image update
:::image type="content" source="media/manage-your-custom-apps-update1.png" alt-text="New version available." lightbox="media/manage-your-custom-apps-update1.png":::

:::image type="content" source="media/manage-your-custom-apps-update2.png" alt-text="Upgrade option for an app." lightbox="media/manage-your-custom-apps-update2.png":::
--->

## <a name="updates-to-custom-apps"></a>사용자 지정 앱에 업데이트

조직 내에서 생성되고 배포된 사용자 지정 앱은 테넌트 또는 조직의 사용자가 사용할 수 있습니다. Teams 관리자는 조직의 개발자가 새 버전을 제공하는 경우 사용자 지정 앱을 새 버전으로 업데이트합니다. 자세한 내용은 [관리자가 사용자 지정 앱을 관리하는 방법을 참조하세요](custom-app-overview.md).

## <a name="related-articles"></a>관련 기사

* [앱에서 수행된 업데이트에 대한 매니페스트 스키마를 이해합니다.](/microsoftteams/platform/resources/schema/manifest-schema).
* [사용자 지정 앱 관리에 대해 알아봅니다](custom-app-overview.md).
